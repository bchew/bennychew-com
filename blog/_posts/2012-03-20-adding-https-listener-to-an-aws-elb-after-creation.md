---
id: 338
title: Adding HTTPS listener to an AWS ELB after creation
date: 2012-03-20T17:16:28+00:00
author: Benny Chew
layout: post
guid: https://directblog.siansiew.com/?p=338
permalink: /2012/03/20/adding-https-listener-to-an-aws-elb-after-creation/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Coding/Development
  - 'Tips &amp; Tweaks'
tags:
  - aws
  - ec2
  - elb
---
Was searching for a way to get it done via the AWS web console, but that didn&#8217;t end up fruitful so had to resort to their CLI tools. In addition the ELB was already in production use which meant discarding and recreating it wasn&#8217;t really an option..

Prerequisites for the subsequent steps are the <a href="http://aws.amazon.com/developertools/2536" target="_blank">ELB API Tools</a> and <a href="http://aws.amazon.com/developertools/AWS-Identity-and-Access-Management/4143" target="_blank">IAM Command Line Toolkit</a> (which has to be configured with your AWS keys).

  1. Run &#8216;iam-servercertlistbypath&#8217; in the bin dir for IAMCLI (e.g. IAMCli-1.2.0\bin). This should give you a list of your SSL certs which are already in your AWS account.
  2. Run &#8216;elb-create-lb-listeners <lb-name> &#8211;headers &#8211;listener &#8220;lb-port=443,instance-port=<port>,protocol=https,cert-id=<cert-name>&#8221; &#8211;region=<aws-region>&#8217;. in the bin dir for ELB API Tools (e.g. ElasticLoadBalancing-1.0.15.1\bin). Replace:

    <lb-name> your ELB name
    <port> your EC2 instance port
    <cert-name> your SSL cert in your AWS account
    <aws-region> the region your ELB resides in (this seems to be missing from a lot of docs and was a major pain &#8211; I was retrieving empty result lists without this specified)

Something related to ELB which I had to look at sometime back which used these CLI tools was updating of expiring SSL certs. It&#8217;s been documented <a href="http://docs.amazonwebservices.com/ElasticLoadBalancing/latest/DeveloperGuide/US_UpdatingLoadBalancerSSL.html" target="_blank">here</a> now so I won&#8217;t be repeating it again! :)