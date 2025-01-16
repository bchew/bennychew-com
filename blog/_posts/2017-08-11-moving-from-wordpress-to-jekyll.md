---
title: 'Moving from WordPress to Jekyll'
date: 2017-08-11T21:00:00+10:00
author: Benny Chew
layout: post
permalink: /2017/08/11/moving-from-wordpress-to-jekyll/
tags:
  - static website hosting
  - wordpress
  - jekyll
  - s3
---
I've been contemplating converting my WordPress powered blog and photo site for quite awhile now, but as you can see from the amount of time from the last post, this blog has not been getting much attention (besides having to update the Ubuntu OS running on the EC2 instance and the endless WordPress updates..).

Unfortunately (or fortunately?), that smooth sailing came to an end recently when the usual apt-get update/upgrade failed to complete. After further investigation, it was due one of the WordPress's caching plugin I had installed which managed to use up all the inodes on the instance.

Following that issue, I decided to research on the migration (evaluated [Hugo](http://gohugo.io/) as well besides [Jekyll](https://jekyllrb.com/)) and spent time testing before making the changes over the weekend. The brunt of the work was mostly handled by the [Jekyll Exporter](https://wordpress.org/plugins/jekyll-exporter/) WordPress plugin which converted all posts and pages for use in Jekyll ([this site](http://www.codingpedia.org/ama/how-to-migrate-programming-blog-from-wordpress-to-jekyll/) was a good reference). Then came choosing the Jekyll theme and validating all the posts and pages were in order. To simplify things, I decided to merge the photo site posts into the blog as well. 

Overall the migration did involve quite a fair bit amount of work (I ended up implementing a continuous deployment workflow with Docker and Bitbucket pipeline which could have made it a lot bigger that originally planned.. would write up on this in the next post), but I believe it would be beneficial in the longer term with just relying on S3 to host static files (cost wise too). :)
