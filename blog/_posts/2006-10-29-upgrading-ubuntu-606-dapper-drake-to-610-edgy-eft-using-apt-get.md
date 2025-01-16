---
id: 126
title: Upgrading Ubuntu 6.06 (Dapper Drake) to 6.10 (Edgy Eft) using apt-get
date: 2006-10-29T01:07:21+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/2006/10/29/upgrading-ubuntu-606-dapper-drake-to-610-edgy-eft-using-apt-get/
permalink: /2006/10/29/upgrading-ubuntu-606-dapper-drake-to-610-edgy-eft-using-apt-get/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Linux
  - Open Source
  - 'Tips &amp; Tweaks'
---
This upgrade was released a day or 2 ago, and I thought I&#8217;ll give it a shot at upgrading using <a target="_blank" href="http://en.wikipedia.org/wiki/Apt-get">apt-get</a>&#8216;s distupgrade. The steps I used:

>   1. sudo sed -e â€™s/\sdapper/ edgy/gâ€™ -i /etc/apt/sources.list
>   2. sudo apt-get update
>   3. sudo apt-get dist-upgrade
>   4. sudo apt-get -f install
>   5. sudo dpkg â€“configure -a
>   6. Reboot.

_Steps taken from <a target="_blank" href="http://www.debianadmin.com/upgrade-ubuntu-dapper-to-ubuntu-edgy-eft.html">Debian Admin</a>._

The first step replaces all occurrences of &#8216;dapper&#8217; with &#8216;edgy&#8217; in the sources.list which has the list of repositories apt-get will use (e.g. I have mine pointed to my ISP&#8217;s FTP mirror instead), the next step updates the sources.list which is then followed by the upgrade. 5th and 6th step is to check that the process completes properly and the last step is pretty self explanatory.

Only issue I had with the upgrade was <a target="_blank" href="http://www.vmware.com/products/server/">VMware Server</a> stopped working, which I&#8217;ll probably have to reconfigure/reinstall it as I think some configuration stuff probably got overwritten.

<a target="_blank" href="https://help.ubuntu.com/community/">Ubuntu&#8217;s documentation wiki</a> has probably more comprehensive explanations on the <a target="_blank" href="https://help.ubuntu.com/community/EdgyUpgrades">upgrade steps</a> as well as alternative upgrade choices.