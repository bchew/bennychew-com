---
id: 191
title: Javascript setInterval() issues
date: 2007-07-02T23:27:26+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/2007/07/02/javascript-setinterval-issues/
permalink: /2007/07/02/javascript-setinterval-issues/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Coding/Development
  - Javascript
---
I decided to use AJAX calls to get the browser to make keep-alive calls every 2 minutes (using setInterval) and somehow stumbled into an issue where it makes the call once, and then stops. After talking the Javascript and Flash _god_ in the office, we found out that it was because the script goes out of scope and thus stops looping as it should.

A quick fix for this can be found <a href="http://killustar.blogspot.com/2005/04/javascript-setinterval-problem.html" target="_blank">here</a>. It&#8217;s been working for me without any adverse effects since. ;)