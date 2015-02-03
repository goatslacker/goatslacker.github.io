---
layout: post
title: Adding node.js project that uses git-submodules to travis-ci
date: '2011-12-10T00:45:00-08:00'
tags:
- code
- continuous
- integration
- javascript
- node.js
- quality
- ruby
- travis-ci
tumblr_url: http://www.goatslacker.com/post/14007739279/adding-node-js-project-that-uses-git-submodules-to
---
Recently, I added my projects node-fixmyjs jshint-autofix to Travis-CI which is excellent. Travis is a build system for the open source community, I recommend you take a look at it if you haven’t.
Anyways, both of my projects depended on submodules and the tests were initially failing because I didn’t know how to tell Travis to download the submodules before running the unit tests.
So here’s what you’re supposed to put in your .travis.yml file:
language: node_js
node_js:
  - 0.6
before_install:
  git submodule init && git submodule --quiet update
