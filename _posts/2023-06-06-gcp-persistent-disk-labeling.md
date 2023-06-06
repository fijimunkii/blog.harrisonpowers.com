---
layout: post
title: How to deterministically mount persistent disks in Google Cloud
categories:
- gcp
- deterministic
tags: []
---

Adding additional disks to an instance in Google Cloud is straightforward. But, what if you want to mount these disks in a specific order? Or mount a particular additional disk to a specified folder? Using the generic `/dev/nvme..` path relies on the order the disks were attached to the instance.

The solution to this race condition is by specifying a "device name" when attaching disks. Here is an example:

```
gcloud compute instances attach-disk ${INSTANCE} \
  --disk=${DISK} \
  --device-name=${DISK} \
  --project=${PROJECT} \
  --zone=${ZONE}
```

Following this example, you should expect to see your disk identified by it's device name label in the directory `/dev/disk/by-id`, for example:

```
ls -l /dev/disk/by-id
google-persistent-disk-0 -> ../../sdb
google-mydevicename -> ../../sdc
```

Now partitioning and mounting can be performed deterministically:
```
disk_label="mydevicename"
partition_label="abcd"
partition_path="/abcd"

parted /dev/disk/by-id/$disk_label -s -a minimal mklabel gpt mkpart $partition_label ext4 0% 100%
PART=$(blkid -o device --match-token "PARTLABEL=$partition_label")
if ! mount -t ext4 -o nodev,noexec,nosuid $PART $partition_path; then
  mkfs.ext4 "$PART"
  mount -t ext4 -o nodev,noexec,nosuid $PART $partition_path
fi
```

### What if this /dev/disk/by-id folder doesn't exist?

Say you're using a custom disk image, this `/dev/disk/by-id` folder most likely won't exist. That is because Google has a custom script baked into their images that creates device paths based on device names. Here is the script for your own purposes:
[https://github.com/GoogleCloudPlatform/guest-configs/blob/master/src/lib/udev/rules.d/65-gce-disk-naming.rules](https://github.com/GoogleCloudPlatform/guest-configs/blob/master/src/lib/udev/rules.d/65-gce-disk-naming.rules)

If all you need is to deterministically mount disks, here is relevant piece from that script:
```
nvme_device="nvme0n2"
nvme_json=$(nvme id-ns -b /dev/$nvme_device | xxd -p -seek 384 | xxd -p -r)
nvme_device_name="$(echo "$nvme_json" | grep device_name | sed -e 's/.*"device_name":[  \t]*"\([a-zA-Z0-9_-]\+\)".*/\1/')"
```
