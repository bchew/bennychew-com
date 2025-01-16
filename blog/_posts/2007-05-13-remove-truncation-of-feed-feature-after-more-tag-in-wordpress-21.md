---
id: 177
title: Remove truncation of feed feature after more tag in WordPress 2.1
date: 2007-05-13T00:27:27+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/2007/05/13/remove-truncation-of-feed-feature-after-more-tag-in-wordpress-21/
permalink: /2007/05/13/remove-truncation-of-feed-feature-after-more-tag-in-wordpress-21/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Open Source
  - RSS
  - 'Tips &amp; Tweaks'
  - Web
  - WordPress
---
If you have already upgraded to <a href="http://wordpress.org/" target="_blank">WordPress</a> 2.1 and have the syndication feeds options set to &#8216;full text&#8217;, you might&#8217;ve noticed that the <a href="http://en.wikipedia.org/wiki/RSS" target="_blank">RSS</a> feed for your blog post gets truncated after the use of the <!â€“â€“moreâ€“â€“> tag. This is a change in behaviour as compared to previous version of WordPress (2.0 and below) which would show the whole post in an RSS feed if the feed option was set to full text.

Without going into the debate of <a href="http://www.google.com.au/search?hl=en&q=full+text+vs+summary+feeds&btnG=Google+Search&meta=" target="_blank">full vs. partial feeds</a> (I&#8217;m on the full feeds side though ;)), there&#8217;s a WordPress plugin which does not require any additional configuration apart from just dropping it into your WordPress&#8217;s plugins directory and activating it. Get it from <a href="http://cavemonkey50.com/code/full-feed/" target="_blank">here</a>.