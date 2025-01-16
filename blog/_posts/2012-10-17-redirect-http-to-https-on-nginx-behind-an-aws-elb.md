---
id: 373
title: Redirect HTTP to HTTPS on nginx behind an AWS ELB
date: 2012-10-17T10:55:31+00:00
author: Benny Chew
layout: post
guid: https://directblog.siansiew.com/?p=373
permalink: /2012/10/17/redirect-http-to-https-on-nginx-behind-an-aws-elb/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Coding/Development
tags:
  - aws
  - elb
  - linux
  - nginx
---
Much like my previous post on redirect HTTP to HTTPS for IIS behind AWS&#8217;s Elastic Load Balancer, I started googling around for a solution for nginx. What I&#8217;ve put in place works when placed in the server directive for HTTP traffic:

```
if ($http_x_forwarded_proto != 'https') {
	rewrite ^(.*) https://$host$1 permanent;
}
```

However, am wondering if there&#8217;s a better/cleaner way to do this? Acknowledging this <a href="http://wiki.nginx.org/IfIsEvil" target="_blank">nginx wiki entry</a>..