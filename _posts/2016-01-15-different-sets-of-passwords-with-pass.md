---
layout: post
title: Use different sets of passwords with pass
categories:
- linux
- pgp
- gpg
- pass
tags: []
---

Pass is great. GPG and git for easy password access.

The commands (that I copy and paste) for setting up a new machine are:

```
pass init F1136F54
pass git init 
pass git remote add origin git@powers.tech:fijimunkii/password-store.git
pass git pull
pass git branch --set-upstream-to=origin/master master
pass git pull
cd ~/.password-store && git submodule update --init --recursive && git submodule foreach git checkout master && cd -
```

Submodules contain passwords for work. Passwords in the submodule are encrypted with the PGP key(s) in the respective .gpg-id file. This id can point to a GPG group.


Here are some examples


```
# list all keys
pass
# copies my password to clipboard (using my pgp key))
pass apple.com/harrisonpowers@gmail.com -c
# create a multiline password (using work pgp key)
pass insert work/project/development.json -m
# edit the password in your editor
pass edit work/project/development.json
# copies silently to clipboard
pass work/project/production.json -c
```
