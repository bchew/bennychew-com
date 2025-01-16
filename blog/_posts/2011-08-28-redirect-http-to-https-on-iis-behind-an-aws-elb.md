---
id: 281
title: Redirect HTTP to HTTPS on IIS behind an AWS ELB
date: 2011-08-28T11:40:33+00:00
author: Benny Chew
layout: post
guid: http://blog.siansiew.com/?p=281
permalink: /2011/08/28/redirect-http-to-https-on-iis-behind-an-aws-elb/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:1;}'
categories:
  - Coding/Development
  - 'Tips &amp; Tweaks'
tags:
  - aws
  - elb
  - iis
---
In recent times I&#8217;ve had to handle the Microsoft stack (.NET) among other things. One of the things I&#8217;ve faced recently was redirecting traffic hitting the application running on IIS behind an <a href="http://aws.amazon.com/elasticloadbalancing/" target="_blank">AWS Elastic Load Balancer</a> (ELB) from HTTP to HTTPS. Fairly easy on the Linux stacks which had <a href="http://nginx.org/" target="_blank">nginx</a> in front as a reverse proxy (just add a rewrite rule on your HTTP host to HTTPS), but after tinkering around a bit, finally got the correct rewrite rule working (with the help of IIS7&#8217;s .htaccess conversion utility).

The transform code you would want to stick into your Web.<transform>.config (was for a ASP.NET MVC project):

<pre>&lt;rewrite xdt:Transform="Insert"&gt;
      &lt;rules&gt;
        &lt;rule name="HTTPS rewrite behind ELB rule" stopProcessing="true"&gt;
          &lt;match url="^(.*)$" ignoreCase="false" /&gt;
          &lt;conditions&gt;
            &lt;add input="{HTTP_X_FORWARDED_PROTO}" pattern="^http$" ignoreCase="false" /&gt;
          &lt;/conditions&gt;
          &lt;action type="Redirect" redirectType="Found" url="https://{SERVER_NAME}{URL}" /&gt;
        &lt;/rule&gt;
      &lt;/rules&gt;
    &lt;/rewrite&gt;</pre>

This assumes you have the <a href="http://www.iis.net/download/urlrewrite" target="_blank">IIS URL Rewrite module</a> installed on your IIS server.

References:

[http://www.iis-aid.com/articles/how\_to\_guides/redirect\_http\_to\_https\_iis_7?page=1](http://www.iis-aid.com/articles/how_to_guides/redirect_http_to_https_iis_7?page=1)
[http://serverfault.com/questions/304621/endless-redirect-loop-with-aws-elb-and-wordpress-site-using-wordpress-https-plugi](http://serverfault.com/questions/304621/endless-redirect-loop-with-aws-elb-and-wordpress-site-using-wordpress-https-plugi)
[http://docs.amazonwebservices.com/ElasticLoadBalancing/latest/DeveloperGuide/index.html?SvcIntro.html](http://docs.amazonwebservices.com/ElasticLoadBalancing/latest/DeveloperGuide/index.html?SvcIntro.html)