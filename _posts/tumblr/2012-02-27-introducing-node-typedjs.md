---
layout: post
title: Introducing node-typedjs
date: '2012-02-27T08:00:05-08:00'
tags:
- javascript
- coffeescript
- type safety
- haskell
- type signatures
- code quality
- testing
- unit tests
- contracts
- node.js
- static typing
tumblr_url: http://www.goatslacker.com/post/18381591530/introducing-node-typedjs
---
node-typedjs is the node module, and more, for TypedJS
TypedJS is described as “lightweight program specifications for testing JavaScript”
In a nutshell you can annotate your functions with Haskell-like type signatures and then run a set of tests against those functions thus ensuring type safety. TypedJS will probably help you find some bugs in your code that you otherwise may not have found.
What it does
node-typedjs helps you test your JavaScript projects via the command line or programatically.
It gives you access to a few neat features like contracts via the enforce() method which enforce the types at runtime.
The contracts can be used along with your unit tests to assert that your functions are behaving as intended.
Similar to contracts.coffee, typedjs aims at solving the problem differently.
TypedJS is focused on JavaScript. But it also works on CoffeeScript just as well.
The type signatures are comments. So there is no extra compilation and the signatures are unobtrusive.
Examples
addition.js contains your function along with its type signature.
//+ add :: Number Number -> Number
function add(a, b) {
  return a + b;
}
addition-test.js is your unit test as well as the typedjs checks.
var typedjs = require(''typedjs'');
var fs = require(''fs'');
var assert = require(''assert'');

typedjs.enforce(fs.readFileSync(''addition.js'').toString());

typedjs.run(function (context) {
  assert.equal(context.square(3), 9); // pass
  assert.equal(context.square(''foo'', ''bar''), ''foobar''); // fail
});
Even though both assertions would pass, the typedjs check will fail on the second call since a number is expected.
node-typedjs will let you:
Run automated tests on your code.
Run automated tests on functions individually.
Extract all functions from a file (regardless of closures) and run automated tests on them.
Use it along with your unit tests to assert your functions are behaving correctly.
Getting node-typedjs
You will need node.js
Install using npm
Locally:
$ npm install typedjs
Globally
$ npm install typedjs -g
Standing on the shoulders of giants
node-typedjs would not be possible without open-source software such as
TypedJS by Ethan Fast
esprima by Ariya Hidayat
Resources
Fork this project on GitHub
Report Issues
Type Signatures Reference Manual
TypedJS website
Follow me on Twitter
License
MIT LICENSE
