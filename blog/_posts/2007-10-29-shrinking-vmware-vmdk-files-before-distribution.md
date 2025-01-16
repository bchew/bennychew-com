---
id: 203
title: Shrinking VMware VMDK files before distribution
date: 2007-10-29T21:55:30+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/2007/10/29/shrinking-vmware-vmdk-files-before-distribution/
permalink: /2007/10/29/shrinking-vmware-vmdk-files-before-distribution/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Coding/Development
  - 'Tips &amp; Tweaks'
tags:
  - virtualisation
  - vmware
---
Recently been researching and testing with <a href="http://www.vmware.com/" target="_blank">VMware </a>images for the deployment of our application at work which turned out to work pretty well (Ubuntu + Java 6 + MySQL + Glassfish). However, one thing which became bothersome was the overgrowing .vmdk images which didn&#8217;t seem to reduce in size even after file deletions were made in the virtual disk itself.

Again, Google came to the rescue for this, linking me to <a href="http://h0bbel.p0ggel.org/shrinking-vmdk-files" target="_blank">this site</a> which gave a 2 step process for doing the shrinking. Do note that the instructions are for those who are using Windows as their host OS.