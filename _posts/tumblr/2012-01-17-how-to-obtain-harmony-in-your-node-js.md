---
layout: post
title: How to obtain harmony in your node.js
date: '2012-01-17T00:12:00-08:00'
tags:
- ecmascript
- es6
- esnext
- harmony
- javascript
- node.js
- v8
tumblr_url: http://www.goatslacker.com/post/16000243520/how-to-obtain-harmony-in-your-node-js
---
UPDATE! 3rdEden has pointed out that it’s possible to get harmony in node 0.6
You can get it by using a flag when invoking node through the command line
node --harmony_typeof --harmony_block_scoping --harmony_proxies --harmony_weakmaps file.js
Or if you’re using node 0.7.x
node --harmony file.js
Harmony!!!!1
Enable ECMAScript’s new features and syntax in node point javascript.
Node unstable has just been released and with that V8 has been upgraded to 3.8.6 which contains flags for experimental language features.
By default those flags are turned off, but you can always turn them on. Here’s how:
Download node 0.7.0.
If you’ve got it cloned on git run a git fetch and then git checkout v0.7.0 otherwise read the release notes for instructions on where to download.
Set harmony flag to true in V8
Once you’ve got the source code, open up deps/v8/src/flag-definitions.h and look for Line 115
Change the flag from false to true.
DEFINE_bool(harmony, true, "enable all harmony features")
Compile Node
./configure && make && make install

Have fun!
function foo() {
  "use strict";
  let i = -1;

  for (let i = 0; i < 10; i += 1) {
    console.log(i); // 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
  }

  console.log(i); // -1
}

foo();

NOTE: you’ll need to use "use strict"; otherwise the code above will not run.
By doing this you’ll get:
Sets, Maps, and Weak Maps
Block scoping
Proxies
New typeof semantics
Learn more about ES harmony
