---
layout: post
id: e4db1702-2846-40a4-bef8-559f9b065b44 
title : Base Framework For This Website
description: Description of the framework used for building this static website 
tags: website markdown jekyll html content static-website-generator github-pages
category: web
redirect_from:
  - /post/website-base/
---

The website is designed to work as [static website](https://en.wikipedia.org/wiki/Static_web_page), i.e all content is generated apriori and served as static content from a [web server](https://en.wikipedia.org/wiki/Web_server). Usually this works well with storage services providing wrapper for static websites like [Azure Storage](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-static-website) or [AWS S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html).

[Jekyll](https://jekyllrb.com/) is used as a static website generator so that content can be generated in Markdown. [Lanyon](http://lanyon.getpoole.com/) theme is used for the visual design. This is intended to be hosted using [GitHub Pages](https://help.github.com/en/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll)

Basic functionalities of the website like feed, seo, content-tags etc are used from Jekyll Plugins or written to use Jekyll framework. 