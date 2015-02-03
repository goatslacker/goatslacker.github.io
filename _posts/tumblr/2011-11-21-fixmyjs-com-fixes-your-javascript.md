---
layout: post
title: Fixmyjs.com Fixes your JavaScript
date: '2011-11-21T00:29:13-08:00'
tags:
- javascript
- nodejs
- lint
- jshint
- jslint
- code quality
- programming
tumblr_url: http://www.goatslacker.com/post/13105614425/fixmyjs-com-fixes-your-javascript
---
Fixmyjs.com Fixes your JavaScriptI built this a couple weekends ago — it’s based off of my nodejs tool jshint-autofix `npm install fixmyjs` http://github.com/goatslacker/jshint-autofix which in turn sits on top of JSHint.
The goal is to detect errors in your code and automatically fix them while making sure your program still functions as intended. It’s a difficult goal to attain since I do have to destroy the code in some instances in order to “fix” it. This is why I have unit tests and include popular libraries such as jQuery and Backbone in the unit tests.
Check out the site and let me know what you think!
