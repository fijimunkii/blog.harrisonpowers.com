---
layout: post
title: CLI - Variations on ls
categories:
- cli
tags: []
---
We use ls to list the directory. Here are some operators you use to extend the functionality of ls.


{% highlight bash %}
ls -1 # sort by name
ls -1r # sort by name in reverse order
ls -1r --group-directories-first # display folders before filez
ls -t # sort by modified date
ls -tr # oldest first
ls -S # sort by filesize
ls -Sr # smallest first
ls -X # sort by extension
ls -l # long listing (file attributes)
ls -l | sort -k 3 # pipes the listing through sort (by column 3 - owner name)
ls -l | sort -k 3, 3 -k 9 # sort by owner and filename
ls -lisa | awk '{print $5, $7, $11}' | sort # pipes the detailed listing through awk, which prunes the output, and then piped through sort
{% endhighlight %}
