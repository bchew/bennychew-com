---
id: 18
title: Improving the performance of USB drives/sticks
date: 2006-06-05T00:01:10+00:00
author: Benny Chew
layout: post
guid: https://bennychew.com/blog/2006/06/05/improving-the-performance-of-usb-drivessticks/
permalink: /2006/06/05/improving-the-performance-of-usb-drivessticks/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - 'Tips &amp; Tweaks'
  - Windows
---
Here&#8217;s a quick trick to boost the performance of your USB drive/stick which I came across while I was doing partitioning using Windows&#8217; built in disk management tool (click on the thumbnail images to view the full sized screenshot):

1. Get to &#8216;My Computer&#8217;, right click on your USB device and click &#8216;Properties&#8217;.
  
<a target="_blank" href="http://img186.imageshack.us/my.php?image=step19mt.png"><img border="0" alt="Free Image Hosting at www.ImageShack.us" src="http://img186.imageshack.us/img186/1491/step19mt.th.png" /></a>

2. In the dialog box that appears, click on the &#8216;Hardware&#8217; tab, select your USB device and click &#8216;Properties&#8217;.
  
<a target="_blank" href="http://img55.imageshack.us/my.php?image=step26ij.png"><img border="0" alt="Free Image Hosting at www.ImageShack.us" src="http://img55.imageshack.us/img55/6731/step26ij.th.png" /></a>

3. In the dialog box that appears, click on the &#8216;Policies&#8217; tab, select &#8216;Optimize for performance&#8217;, and click the &#8216;OK&#8217; button of the dialog boxes that have shown up.
  
<a target="_blank" href="http://img55.imageshack.us/my.php?image=step35lk.png"><img border="0" alt="Free Image Hosting at www.ImageShack.us" src="http://img55.imageshack.us/img55/1526/step35lk.th.png" /></a>

The performance increase is very apparent if you&#8217;re using an external hard drive which is connected via USB (my 200GB external hard disk is still running fine :P) and probably even with USB flash drives if you&#8217;re doing a lot of data transfers.

The downside in changing this setting is that you would have to ensure that you have to explicitly invoke the &#8216;Safely Remove Hardware&#8217; option (the green icon in the system tray) before unplugging your USB device as opposed to being able to just unplug it and most likely not suffer any data corruption.