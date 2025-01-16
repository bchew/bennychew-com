---
id: 160
title: Combating comment spam
date: 2007-02-04T21:05:39+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/2007/02/04/combating-comment-spam/
permalink: /2007/02/04/combating-comment-spam/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Open Source
  - 'Tips &amp; Tweaks'
  - Web
  - WordPress
---
<p align="left">
  After the <a href="https://bennychew.com/blog/2006/12/31/server-issues/" target="_blank">major upgrade</a> by my webhost, there was a sudden surge in spam on the blogs on <a href="http://spherebox.com/" target="_blank">spherebox</a>, with a lot bypassing <a href="http://akismet.com/" target="_blank">Akismet</a>&#8216;s filtering. Apparently he did not configure the <a href="http://www.modsecurity.org/" target="_blank">ModSecurity</a> <a href="http://apache.org/" target="_blank">Apache</a> module (which did an excellent job previously) and was too lazy to do so as the new version he had installed had supposedly different configuration settings. :(
</p>

Since I got sick of getting the incessant email notifications of spam held in moderation queue, I decided to go looking around for fixes and came across <a href="http://codex.wordpress.org/Combating_Comment_Spam/Denying_Access#Deny_Access_to_No_Referrer_Requests" target="_blank">this</a> at <a href="http://codex.wordpress.org/Main_Page" target="_blank">WordPress&#8217;s Codex</a> which helped cut down the crazy amount of spam that kept going through by heaps. Basically it adds rules to the <a href="http://en.wikipedia.org/wiki/Htaccess" target="_blank">.htaccess</a> file which will check that any comments being submitted to wp-comments-post.php come from the comments page of the WordPress installation and not directly injected by spam bots.

Note that this did not stop the spam completely, but managed to reduce the volume enough so that Akismet could block it off appropriately.

If you&#8217;re encountering the same issue as I did, try it out. The instructions are fairly simple and requires few modifications. :)