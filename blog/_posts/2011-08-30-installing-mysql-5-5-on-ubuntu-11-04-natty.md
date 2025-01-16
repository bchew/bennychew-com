---
id: 299
title: Installing MySQL 5.5 on Ubuntu 11.04 (Natty)
date: 2011-08-30T19:22:43+00:00
author: Benny Chew
layout: post
guid: http://blog.siansiew.com/?p=299
permalink: /2011/08/30/installing-mysql-5-5-on-ubuntu-11-04-natty/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:3;}'
categories:
  - Coding/Development
  - Linux
  - Open Source
tags:
  - mysql 5.5
  - natty
  - ubuntu 11.04
---
Steps I used to get MySQL 5.5 working on Ubuntu 11.04 AMD64 (behind Aptitude&#8217;s back sadly since it&#8217;s still not packaged up due to <a href="https://bugs.launchpad.net/ubuntu/+source/mysql-5.1/+bug/690925" target="_blank">copyright statuses</a>..):

  * Download the following from <a href="http://people.debian.org/~nobse/mysql-5.5/" target="_blank">here</a>.

    * mysql-common\_5.5.13-2\_all.deb
    * libmysqlclient18\_5.5.13-2\_amd64.deb
    * libmysqlclient-dev\_5.5.13-2\_amd64.deb
    * mysql-client-5.5\_5.5.13-2\_amd64.deb
    * libmysqld-dev\_5.5.13-2\_amd64.deb
    * libmysqld-pic\_5.5.13-2\_amd64.deb
    * mysql-server-core-5.5\_5.5.13-2\_amd64.deb
    * mysql-server-5.5\_5.5.13-2\_amd64.deb

  * Run the following to remove older versions of MySQL client/server:

    ```
    sudo aptitude remove mysql-client mysql-client-5.1 mysql-client-core-5.1 mysql-common mysql-server mysql-server-5.1 mysql-server-core-5.1
    ```

  * From the directory you downloaded the files above to:

    ```
    sudo aptitude install libmysqld-dev
    sudo dpkg -i mysql-common_5.5.13-2_all.deb
    sudo dpkg -i libmysqlclient18_5.5.13-2_amd64.deb
    sudo aptitude install zlib1g-dev
    sudo dpkg -i libmysqlclient-dev_5.5.13-2_amd64.deb
    sudo aptitude install libdbi-perl libdbd-mysql-perl
    sudo dpkg -i mysql-client-5.5_5.5.13-2_amd64.deb
    sudo dpkg -i libmysqld-dev_5.5.13-2_amd64.deb
    sudo dpkg -i libmysqld-pic_5.5.13-2_amd64.deb
    sudo dpkg -i mysql-server-core-5.5_5.5.13-2_amd64.deb
    sudo dpkg -i mysql-server-5.5_5.5.13-2_amd64.deb
    ```

Took me awhile of messing around to get the sequence right, hope this helps!

Reference/links from blog post/comments [here](http://geek.co.il/wp/2011/03/02/mysql-5-5-on-ubuntu-10-10).