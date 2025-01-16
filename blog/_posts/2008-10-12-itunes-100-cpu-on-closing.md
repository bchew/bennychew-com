---
id: 226
title: 'iTunes 100% CPU on closing'
date: 2008-10-12T12:32:12+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/?p=226
permalink: /2008/10/12/itunes-100-cpu-on-closing/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - 'Tips &amp; Tweaks'
  - Windows
tags:
  - '100% cpu'
  - apple
  - itunes
  - nod32
---
After I got my <a href="http://www.apple.com/iphone/" target="_blank">iPhone 3G</a> a couple about 2 months ago, I had no other choice but to use <a href="http://www.apple.com/itunes/" target="_blank">iTunes</a> for all the syncing, backups, music etc as Apple wants total control of what you can or can&#8217;t do with its devices (was using YamiPod previously, writeup <a href="http://spherebox.com/2007/07/09/yamipod-yet-another-ipod-manager/" target="_blank">here</a>). :|

My loathing for it got worse as it didn&#8217;t seem to be closing gracefully on quitting besides causing software restores which all ended up with iTunes.exe taking up 100% CPU. I decided to stop swearing at it and search around for the root cause as this behaviour wasn&#8217;t replicated on my work machine and on colleague&#8217;s variety of machines.

Turns out it wasn&#8217;t iTunes, but the antivirus (<a href="http://www.eset.com/" target="_blank">NOD32</a> 2.7) which wasn&#8217;t playing nice. After adding various iTunes paths to AMON/IMON exclusion lists, there has not been crashes or 100% CPU since (instructions on how to do this <a href="http://training.eset.com/kb/index.php?option=com_kb&Itemid=29&page=articles&articleid=760" target="_blank">here</a>). Guess I was cursing the wrong software but anyhow..

Just a note, this is a fairly belated post as I was having this issue with iTunes 7.x and have since upgraded to 8.0.1 which may no longer require this workaround. ;)