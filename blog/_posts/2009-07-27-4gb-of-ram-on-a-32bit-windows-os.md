---
id: 260
title: 4GB of RAM on a 32bit Windows OS
date: 2009-07-27T21:36:49+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/?p=260
permalink: /2009/07/27/4gb-of-ram-on-a-32bit-windows-os/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - General Tech
---
Most machines now configured with 4GB of RAM but continue to be bundled with the 32-bit version of Windows. You might&#8217;ve noticed that in this situation it does not fully utilise all of it, but here&#8217;s a simple fix to work around this issue instead of putting a 64-bit OS instead:

> To enable PAE mode, you have to add PAE to the boot entry in the BCD file. Open an elevated command prompt. Type <span>BCDEDIT /SET PAE ForceEnable</span>.

via: <a href="http://support.microsoft.com/kb/929580" target="_blank">Microsoft&#8217;s help article</a>