---
id: 66
title: Reducing file sizes of videos captured using digital cameras
date: 2006-08-18T00:31:43+00:00
author: Benny Chew
layout: post
guid: https://bennychew.com/blog/2006/08/18/reducing-file-sizes-of-videos-captured-using-digital-cameras/
permalink: /2006/08/18/reducing-file-sizes-of-videos-captured-using-digital-cameras/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - General Tech
  - 'Tips &amp; Tweaks'
---
During my last trip to [Mt. Hotham](http://www.mthotham.com.au/), I discovered that the videos I took with my [IXUS 55](http://www4.canon-asia.com/index.cfm?fuseaction=digitalcamera&prod_type=ixus55) digital camera took up fairly substantial real estate on my 512MB [SD](http://en.wikipedia.org/wiki/Secure_Digital) card. For example, a 12 second clip took 21.9MB which when compared to videos available on the net these days, is extremely bloated (e.g. a TV show of about 40 minutes in length is about 350MB).

Checking the user manual of the camera reveals that it uses a [Motion JPEG](http://en.wikipedia.org/wiki/MJPEG) format for the video. [This format](http://www.afterdawn.com/glossary/terms/m-jpeg.cfm) stores each frame of the video separately which results in the much larger overall file size. Here are some results from the conversions which I did with the clips I have using [VirtualDub](http://www.virtualdub.org/)&#8216;s default [XviD](http://en.wikipedia.org/wiki/XviD) settings:

**Before:**
  
12 seconds, 21.9MB
  
1 min 3 seconds, 84.2MB
  
50 seconds, 57.3MB
  
7 seconds, 13.5MB
  
48 seconds, 75.0MB

**After:**
  
12 seconds, 1.75MB
  
1 min 3 seconds, 6.08MB
  
50 seconds, 3.67MB
  
7 seconds, 0.95MB
  
48 seconds, 5.61MB

As you can see, the results show quite a large reduction in size. Before following the steps below, you would need to ensure you have the XviD [codec](http://en.wikipedia.org/wiki/Codec) in your system. I&#8217;m using the [K-lite mega codec pack](http://www.codecguide.com/download_mega.htm) which bundles all the various codecs (including XviD), but you can also download XviD standalone [here](http://www.xvid.org/downloads.html). Steps:

  1. Download the latest VirtualDub from [here](http://virtualdub.sourceforge.net/).
  2. Extract the zip file that you have downloaded to your location of choice on your hard disk (e.g. C:\Program Files\VirtualDub).
  3. Run VirtualDub.exe from the directory you extracted to (e.g. C:\Program Files\VirtualDub\VirtualDub.exe).
  4. Open the video file you wish to convert using File->Open File or just drag and drop the file into the VirtualDub window.
  5. Click &#8216;Video&#8217;->&#8217;Full processing mode&#8217; (ensure there&#8217;s a dot on the left of Full processing mode).
  6. Click &#8216;Video&#8217;->&#8217;Compression&#8217;.
  7. Select &#8216;XviD MPEG4 Codec&#8217;, then click OK.
  8. Click &#8216;File&#8217;->&#8217;Save as AVI..&#8217;
  9. Choose the directory you want to save the converted video to, enter a filename and click &#8216;Save&#8217;.
 10. The [transcoding](http://en.wikipedia.org/wiki/Transcode) should now be in progress. The time taken for it to complete would depend on the speed of your processor and the length of the video.

It is possible to get even further file size reductions by tweaking configuration settings to sacrifice on quality. This usually requires some time in experimenting with various settings to get the best tradeoff which you want. You can read more about transcoding/encoding over [here](http://www.doom9.org/).

Do note that different camera manufacturers may use a different format for capturing video (for e.g. [Quicktime MOV](http://en.wikipedia.org/wiki/QuickTime#QuickTime_file_format)) which may already be optimised and would not attain the same amount of reduction in file size. ;)