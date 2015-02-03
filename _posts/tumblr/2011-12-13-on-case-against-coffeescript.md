---
layout: post
title: On case against coffeescript...
date: '2011-12-13T17:17:00-08:00'
tags:
- coffeescript
- javascript
tumblr_url: http://www.goatslacker.com/post/14192251296/on-case-against-coffeescript
---
On case against coffeescript...There are basically a few arguments against using CoffeeScript and at the end of the article Ryan Florence suggests one to not use it. It basically boils down to these cases:
Debugging is an issue
Verbally Readable !== Quicker Comprehension
One liners are horrible
CoffeeScript has it’s bad parts
Significant whitespace + Spaghetti code is bad
CoffeeScript will never be supported natively.
Debugging is an issue
So yes, debugging is an issue. Hopefully this can be solved soon by  SourceMap.
Verbally Readable does not mean Quicker Comprehension.
I agree, in fact I comprehend Verbally Readable !== Quicker Comprehension quicker than I do the title. But the nice thing about CoffeeScript is that it’s just JavaScript so the lengthy wordy operators are optional.
You could always write in CoffeeScript:
one && two && three

instead of
one and two and three

One liners are horrible
Here’s an example from the blog:
scores = (student["assignment_#{@assignment.id}"].score for own idx, student of @gradebook.students when student["assignment_#{@assignment.id}"]?.score?)

Right, that’s not easy to comprehend. In this particular case I don’t blame the language but the author.
Sure the CoffeeScript documentation touts how it turns verbose JavaScript into “nice” and “sexy” one-liners but that doesn’t mean one should abuse it.
CoffeeScript has it’s bad parts
So does every other language. I  think the good parts of the language outweigh the bad parts.
Significant whitespace + spaghetti code is bad
Spaghetti code itself is bad. I don’t care what language you write it in. It’ll always look like shit.
It seems like now we’re talking about preferring one type of spaghetti over another type of spaghetti — it’s still spaghetti.
CoffeeScript will never be supported natively
Is that really a bad thing?
Overall
I still believe the expressiveness and useful features that CoffeeScript provides outweighs the biggest problem which is debugging.
