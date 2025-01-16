---
id: 415
title: Simple Amazon DynamoDB backup and restore
date: 2014-01-04T17:02:49+00:00
author: Benny Chew
layout: post
guid: https://directblog.bennychew.com/?p=415
permalink: /2014/01/04/simple-amazon-dynamodb-backup-and-restore/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Coding/Development
tags:
  - aws
  - dynamodb
  - mysqldump
  - python
  - script
---
Wrote <a href="https://github.com/bchew/dynamodump" title="dynamodump" target="_blank">dynamodump</a> which is a simple backup and restore script for Amazon DynamoDB using boto to work similarly to mysqldump. It is suitable for DynamoDB usages of smaller data volume which do not warrant the usage of AWS Data Pipeline for backup/restores.

It includes features to help with managing backup/restores between various environments (e.g. production, staging, dev). Comments/suggestions to further improve on it are welcomed.

Perhaps a start to more open sourced stuff this year! :)