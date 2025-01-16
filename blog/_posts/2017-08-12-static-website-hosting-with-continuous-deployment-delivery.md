---
title: 'Static website hosting with continuous deployment/delivery'
date: 2017-08-12T21:00:00+10:00
author: Benny Chew
layout: post
permalink: /2017/08/12/static-website-hosting-with-continuous-deployment-delivery/
tags:
  - static website hosting
  - s3
  - jekyll
  - bitbucket
  - pipeline
  - ci
  - cd
  - continuous delivery
  - continuous deployment
  - cloudflare
  - docker
---
While I was researching on static web hosting with Jekyll, one of the most suggested ways to get it up and running for free is by relying on [GitHub Pages](https://pages.github.com/) if you're happy to have the source code for your site to be open sourced as well. However, I came across some write ups which suggested the use of BitBucket pipelines for getting the Jekyll site built and subsequently published. Intrigued, I spent some time figuring out the details and is now implemented as of this post!

What I've come up with is putting the source code for the site in a BitBucket git repository, created a base [Docker](https://www.docker.com/) image with Ruby, Node.js and Java, set up a [BitBucket](https://bitbucket.org/) pipeline which does a Jekyll build and publishing to S3 buckets with staging and production environments, and [CloudFlare](https://www.cloudflare.com/) for the DNS/CDN/SSL/etc. Just a note that this is not the most optimised solution, and is potentially (definitely..) overkill for a personal website but is something of a topic of interest and experimentation.

So first up, reasonings for the choices I came up with:
- BitBucket
  - I'm sure [GitHub](https://github.com) would be the first thing that pops up when I mention Git repository - but Atlassian's BitBucket was picked as they offered up to 5 private repositories and 50 minutes of 'build time' on their BitBucket pipeline as of time of writing.
- [Custom Docker image](https://hub.docker.com/r/bchew/jekyll-build/) based on [Alpine Linux](https://alpinelinux.org/) 3.6 with Ruby, Node.js and Java
  - BitBucket pipeline is able to use Docker Hub images, Jekyll requires ruby (and potentially Node.js depending on the theme), [s3_website](https://github.com/laurilehmijoki/s3_website) (2.x) gem requires Java due to Scala code and I was not able get an image which reliably worked for this setup. Besides that, I was able to fix the alpine package versions in use via the [Dockerfile](https://github.com/bchew/jekyll-build/blob/master/Dockerfile) and have everything required for the Jekyll site and publishing fixed in bundler for reliable consistent builds.
- [S3](https://aws.amazon.com/s3/)
  - An object store that works very reliably, supports static website hosting and relatively cheap to use.
- CloudFlare
  - I've been using them since they were in beta and works well to handle DNS, performance and security for free.

And here is the summary of steps which I went through to get to being able to write a new post in markdown, committing and pushing to a feature branch, reviewing the changes in a staging environment, merging the pull request and have the changes published to my site:

1. Create S3 buckets for 'staging' and 'production' (e.g. staging.yoursite.com for staging and yoursite.com for production) and configure CloudFlare accordingly, [this site](https://wsvincent.com/static-site-hosting-with-s3-and-cloudflare/) has a good set of setup instructions to be followed for this. Check [this SO answer](https://stackoverflow.com/questions/16267339/s3-static-website-hosting-route-all-paths-to-index-html/16877231#16877231) and [this site](http://blog.michaelcwright.com/2015/11/26/custom-404-pages-with-amazon-s3/) if you require 403/404 redirect rules on your site.
1. Create a BitBucket repo for your Jekyll site and you use the following code snippets for the `bitbucket-pipelines.yml` and `s3_website.yml` files:
  - `bitbucket-pipelines.yml`
        ```yaml
        image: bchew/jekyll-build

        pipelines:
          default:
            - step:
                script:
                  - bundle install
                  - bundle exec jekyll build
                  - bundle exec s3_website push
          branches:
            master:
              - step:
                  script:
                    - bundle install
                    - bundle exec jekyll build
                    - ENV=production bundle exec s3_website push
        ```
    - `s3_website.yml`
        ```ruby
        s3_id: <%= ENV['S3_ID'] %>
        s3_secret: <%= ENV['S3_SECRET'] %>

        <%
          if ENV['ENV'] == 'production'
            @s3_bucket = 'yoursite.com'
          else
            @s3_bucket = 'staging.yoursite.com'
          end
        %>
        s3_bucket: <%= @s3_bucket %>
        ```
    
    These configuration files would create a BitBucket pipeline which uses the `s3_website` gem to push the jekyll site to the staging environment on any pushes to a non master branch and to production on master branch pushes.

Hope this post would come in useful for anyone who would be inclined to go down this path, or even use this as a base for an improved process. :)

References:
- [Static Site Hosting with S3 and CloudFlare](https://wsvincent.com/static-site-hosting-with-s3-and-cloudflare/)
- [Continuous Deployment for Jekyll using Bitbucket Pipeline to deploy in Github](https://seenukarthi.com/pipeline/2017/06/22/jekyll-github-cicd-bitbucket-pipeline/)
- [Deploying websites to FTP or Amazon S3 with BitBucket Pipelines](https://www.savjee.be/2016/06/Deploying-website-to-ftp-or-amazon-s3-with-BitBucket-Pipelines/)
- [Building a Docker Image for BitBucket Pipelines](http://128bitstudios.com/2017/01/10/Building-a-Docker-Image-for-BitBucket-Pipelines/)
- [staging and production environment variables for s3_website](https://github.com/laurilehmijoki/s3_website/issues/223#issuecomment-294050121)
