---
layout: post
title: Hash - Throwaway passwords
date: '2011-11-22T19:09:39-08:00'
tags:
- bootstrap
- coffeescript
- cryptography
- hash
- javascript
- online
- password
- security
- sha
- sha256
- twitter
tumblr_url: http://www.goatslacker.com/post/13187872163/hash-throwaway-passwords
---
Hash - Throwaway passwordsStaying secure online is a difficult task.

When you sign up for a service, you’re giving someone your password so recycling passwords is usually a bad idea. If you use the same password everywhere all it takes is one security breach.

But, managing an entire drawer of passwords is really difficult. There are solutions available both online and natively that allow you to manage multiple passwords, but I’ve yet to come accross a solution that works everywhere and I feel ok about it.

So this afternoon I created this web application which will take a domain name, and a master password and return you a hash. The password is generated on your computer using JavaScript so nothing is sent over the network. You can then use the hash, or part of the hash, as your password. There is also a bookmarklet available which automatically detects password fields and fills them in for you.

This isn’t 100% bulletproof as there are still other ways you may be attacked like phishing and keyloggers, but at least it’s better than recycling passwords or trying to remember a dozen different passwords.

The site is built with Twitter’s Bootstrap library and uses Stanford’s JavaScript Cryptography Library the app itself is built in CoffeeScript.

Give it a whirl and I’d appreciate some feedback.
