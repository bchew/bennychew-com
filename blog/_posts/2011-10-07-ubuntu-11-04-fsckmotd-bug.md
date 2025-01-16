---
id: 308
title: Ubuntu fsck/MOTD bug/issue
date: 2011-10-07T16:43:39+00:00
author: Benny Chew
layout: post
guid: http://blog.siansiew.com/?p=308
permalink: /2011/10/07/ubuntu-11-04-fsckmotd-bug/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:3;}'
categories:
  - Coding/Development
  - Linux
  - Open Source
  - 'Tips &amp; Tweaks'
tags:
  - aws
  - ec2
  - fsck
  - linux
  - MOTD
  - ubuntu
  - ubuntu 11.04
---
Recently this message popped up on the MOTD of the Ubuntu servers on EC2:

`*** /dev/xvda1 will be checked for errors at next reboot ***`

After proceeding to do a fsck and restarting, the message still kept appearing. After some debugging with wk, it apparently was due to a stale fsck-at-reboot file left around causing the message to keep popping up.

Here are the steps I used to make sure they stopped popping up again:

```
sudo touch /forcefsck
sudo shutdown -r now
sudo rm /var/lib/update-notifier/fsck-at-reboot
cd /usr/lib/update-notifier/
sudo ./update-motd-fsck-at-reboot
sudo rm /forcefsck
```

Thanks wk!