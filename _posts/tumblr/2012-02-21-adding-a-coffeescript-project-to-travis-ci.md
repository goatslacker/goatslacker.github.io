---
layout: post
title: Adding a CoffeeScript project to Travis-CI
date: '2012-02-21T20:54:00-08:00'
tags:
- coffeescript
- node.js
- travis-ci
- continuous integration
- cakefile
- npm
tumblr_url: http://www.goatslacker.com/post/18056109174/adding-a-coffeescript-project-to-travis-ci
---
Say you have this project you wrote in CoffeeScript and you want to add it to Travis-CI
but you do not want to include the compiled output in your code repository. Well, you will need to tell Travis to compile your project first before running the tests otherwise they would fail.
But how?
Add this to your .travis.yml
before_script:
  coffee -c -o lib src
Commands under before_script run before the unit tests are ran. So use CoffeeScript to compile your project before running the tests.
You will obviously need coffee-script as a dev_dependency in your package.json
"devDependencies": {
  "coffee-script": "latest"
}
Alternatively you can just use this Cakefile and add the following to your package.json instead
"scripts": {
  "test": "cake test"
}
