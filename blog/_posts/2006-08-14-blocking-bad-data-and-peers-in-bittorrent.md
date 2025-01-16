---
id: 69
title: Blocking bad data (and peers) in BitTorrent
date: 2006-08-14T20:55:55+00:00
author: Benny Chew
layout: post
guid: https://bennychew.com/blog/2006/08/14/blocking-bad-data-and-peers-in-bittorrent/
permalink: /2006/08/14/blocking-bad-data-and-peers-in-bittorrent/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - BitTorrent
  - General Tech
  - 'Tips &amp; Tweaks'
  - Web
---
As [BitTorrent](http://www.bittorrent.com/index.html) checks the integrity of every piece of data it receives, some parties have resorted to &#8216;swarm poisoning&#8217; popular torrents which attempts to flood the peers with bad pieces of data which slows down the propagation of pieces as the client will have to re-download the pieces which failed the verification (hash checking). This leads to heaps of wasted bandwidth which is quite precious in some places like Australia where download quotas are enforced on most broadband plans. ;)

The following are the steps for [Azureus](http://azureus.sourceforge.net/) and [ÂµTorrent](http://www.utorrent.com/). I believe these are the best 2 BT clients at the moment which you switch to immediately if you aren&#8217;t using one of them already. :P

**Azureus (v2.4.0.2):**

  1. Start Azureus.
  2. Click &#8216;Plugins&#8217;->&#8217;Installation Wizard&#8217;
  3. Select &#8216;By list from sourceforge.net&#8217;, click &#8216;Next&#8217;
  4. Scroll down to &#8216;Safepeer&#8217; and check the checkbox on the left of it, click &#8216;Next&#8217;
  5. Select &#8216;Install plugin(s) for all users&#8217;, click &#8216;Finish&#8217;
  6. Click &#8216;Install&#8217; in the dialog box that appears
  7. Once download and installation is done, you can close all dialog boxes and remove the downloaded zip file from your seeding list

**ÂµTorrent (v1.6):**

  1. In ÂµTorrent, go to &#8216;Options&#8217;->&#8217;Preferences&#8217;->&#8217;Advanced&#8217;. Change the &#8216;ipfilter.enable&#8217; value to &#8216;True&#8217;.
  2. Go to [this site](http://tbg.iblocklist.com/), scroll down the page till you reach the &#8216;Other Lists&#8217; column header on the left navigation bar. Look for &#8216;<a href="http://tbg.iblocklist.com/Lists/ipfilter.dat.gz" target="_blank">ipfilter.dat.gz</a>&#8216;. Download that file to your PC (right-click->save target/link as).
  3. Extract the file your archive utility of choice such as [WinRAR](http://www.rarlabs.com/). A file with the name &#8216;nipfilter.dat&#8217; should be extracted.
  4. Rename that file to &#8216;ipfilter.dat&#8217;.
  5. Copy that file to &#8216;C:\Documents and Settings\your-username\Application Data\uTorrent&#8217;. If that file already exists, overwrite it.

Azureus&#8217; Safepeer plugin automatically updates itself with the latest but you would have to do the steps above on a periodic basis for ÂµTorrent if you wish to keep that filter file up-to-date. It&#8217;s probably not as critical as ensuring your virus definitions for your antivirus though, so you don&#8217;t have to do this on an extremely regular basis. :)

_**Edit**: Updated ipfilter.dat links to TBG blocklists instead of BISS_