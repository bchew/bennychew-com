---
id: 202
title: Obscure Java error
date: 2007-10-28T18:45:09+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/2007/10/28/obscure-java-error/
permalink: /2007/10/28/obscure-java-error/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Coding/Development
  - Java
  - 'Tips &amp; Tweaks'
---
Got a &#8220;java.lang.InternalError:Can&#8217;t connect to window server&#8221; while trying to get <a href="https://glassfish.dev.java.net/" target="_blank">Glassfish</a> up and running on a Mac G5 running Mac OS X recently at work which was pretty odd as our application and Glassfish do not fire up any GUIs. After some <a href="http://jira.atlassian.com/browse/CONF-2075" target="_blank">googling</a>, problem was fixed by adding a &#8216;-Djava.awt.headless=true&#8217; to the list of system variables.

Although it was fixed relatively easily, it seems rather odd that Java would actually try to access the X server even though I was running it through a SSH terminal window (PuTTY)..