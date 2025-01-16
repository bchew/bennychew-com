---
id: 117
title: Windows Live Messenger works again
date: 2006-10-19T17:32:01+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/2006/10/19/windows-live-messenger-works-again/
permalink: /2006/10/19/windows-live-messenger-works-again/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Web
  - Windows
---
Since googling didn&#8217;t work <a target="_blank" href="https://bennychew.com/blog/2006/10/12/windows-live-messenger-stopped-working/">the last time</a> I tried to find a fix, I went through <a target="_blank" href="http://www.microsoft.com/">M$</a>&#8216;s <a target="_blank" href="http://www.microsoft.com/communities/newsgroups/en-us/default.aspx?dg=microsoft.public.windows.live.messenger">Windows Live Messenger&#8217;s newsgroup</a> earlier today and actually found a fix to the problem I had! Here&#8217;s the fix which worked for me (Credit to <a target="_blank" href="http://butterflysays.spaces.live.com/">Jonathan Yaniv</a> for the steps below):

  1. Go to Start, run, then type &#8220;regedit&#8221;
  2. Navigate to HKEY\_CURRENT\_USER\Software\microsoft\MSNMessenger\Policies
  3. Delete the key &#8220;contacts.msn.com&#8221;
  4. Then, try launching Windows Live Messenger again.

Apparently the full uninstallation I did the last time did not remove any of the messenger registry keys (I forgot to check on that either).

I guess you could say this is probably one of the very few M$ software which I would gladly choose to use over other alternative software. :P Do try out the excellent <a target="_blank" href="http://www.msgpluslive.net/">Messenger Plus! Live</a> extension if you&#8217;re already using WLM (adds heaps of features like tabbed chats, etc). Just remember to refuse the installation of the sponsor program unless you want adware/spyware installed on your machine. ;)