---
layout: post
title: Introducing gister
date: '2011-12-11T05:57:00-08:00'
tags:
- cli
- gist
- github
- javascript
- node.js
- npm
tumblr_url: http://www.goatslacker.com/post/14063661035/introducing-gister
---
Introducing gisterA nodejs module for programmatic access to create, edit and retrieve gists from github.
There are quite a few gist libraries available from npm. Most were CLI apps to create new gists, others didn’t exactly meet my needs. So I set out to create gister which provides what I think is a simple API. It follows the observer pattern and uses request to talk to GitHub.
Read the annotated source or check out the code.
Using it is really simple. Here’s how you retrieve a gist with gist_id = 1:
var gist = new Gist({ gist_id: 1 });
gist.on(''get'', function (data) {
  // do something with data
});
gist.get();

Creating a new gist is similar, although you’ll need to provide Gist with your GitHub username and Secret API Token which can be found in your Account Settings
var gist = new Gist({ username: ''goatslacker'', token: ''abc123'' });
gist.on(''created'', function (data, gist_id) {
  // gist_id is the newly created gist id
  // data is what github returns in it''s reply
});
gist.create();

Available on npm. Install:
npm install gister
