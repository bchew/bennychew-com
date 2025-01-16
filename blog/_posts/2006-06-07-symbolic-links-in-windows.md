---
id: 17
title: Symbolic links in Windows
date: 2006-06-07T00:25:42+00:00
author: Benny Chew
layout: post
guid: https://bennychew.com/blog/2006/06/05/symbolic-links-in-windows/
permalink: /2006/06/07/symbolic-links-in-windows/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Coding/Development
  - 'Tips &amp; Tweaks'
  - Windows
---
Unfortunately <a target="_blank" href="http://filezilla.sourceforge.net/">FileZilla Server</a>&#8216;s logging option did not allow a change to the target directory where the logs will be stored. So instead of changing any bits of the program code, I created a symbolic link using a program called <a target="_blank" href="http://www.rekenwonder.com/linkmagic.htm">Junction Link Magic</a> which linked the default logs directory to another directory where I keep all my logfiles at. ;)

<a target="_blank" href="http://shell-shocked.org/article.php?id=284">Here</a>&#8216;s the link to an article on symbolic and hard links in Windows. :)