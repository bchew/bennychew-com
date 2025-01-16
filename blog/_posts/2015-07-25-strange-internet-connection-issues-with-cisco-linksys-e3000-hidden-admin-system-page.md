---
id: 440
title: 'Cisco Linksys E3000 &#8211; strange internet connection issues? Hidden admin system page??'
date: 2015-07-25T18:51:03+00:00
author: Benny Chew
layout: post
guid: https://bennychew.com/blog/?p=440
permalink: /2015/07/25/strange-internet-connection-issues-with-cisco-linksys-e3000-hidden-admin-system-page/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - General Tech
  - 'Tips &amp; Tweaks'
tags:
  - e3000
  - router
---
I&#8217;ve had the Cisco Linksys E3000 for quite awhile now and it has been a reliable router, internet connection wise, weak in the wireless department but decent enough to live with.

So first off, the power adaptor blew, quickly resolved it by switching it out with an older power adaptor which came with the Linksys WAG354G (yes, I actually did like Linksys routers.. till now &#8211; eyeing the Asus RT-AC3200). Sometime after, I started noticing strange behaviours with the Facebook app on my Nexus 5 &#8211; the news feed would load, but certain images would just end up with an endless loading spinner, and soon after the app would no longer refresh. Switching from WiFi to 4G/LTE got it working fine which was baffling considering everything else works fine on Wifi. Coincidentally, Netflix launched in Australia then and I jumped on the free trial to test it out &#8211; however, I got a black screen on the Chromecast and a cryptic error message before I got booted back out to the main Chromecast screen.

Started googling around and initial results were on potentially IPv6 issues. However, looking around my router admin pages had nothing on disabling IPv6 which was baffling as <a href="http://testipv6.com/" target="_blank">testipv6</a> says I had an IPv6 IP! More digging then led me to more sites on 6to4 being enabled by default on the router: <a href="http://www.reddit.com/r/networking/comments/z6b51/surprised_to_see_an_ipv6_address/" target="_blank">reddit</a>, <a href="https://productforums.google.com/d/msg/chromecast/4p7GmZIXh6I/_GMgJ1yFoBkJ" target="_blank">chromecast help forum</a>, <a href="http://www.gossamer-threads.com/lists/nsp/ipv6/28915" target="_blank">forum</a>, <a href="http://willscorner.net/?p=86" target="_blank">blog</a>

> you go to http://your\_router’s\_ip/System.asp. Set Vista Premium to disabled and the router will stop broadcast 6to4. 

That&#8217;s pretty much the fix to get everything working as it should. I suppose this doesn&#8217;t help with IPv6 adoption, but I would probably stick with just IPv4 and move to IPv6 when I&#8217;m able to get a native IPv6 IP from my ISP.

Seems bizarre to have a hidden admin system page for this..