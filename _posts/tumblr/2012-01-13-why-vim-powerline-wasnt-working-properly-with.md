---
layout: post
title: Why vim-powerline wasn't working properly with some of my files
date: '2012-01-13T23:31:02-08:00'
tags:
- highlighting
- mango.vim
- syntax
- vim
- vim-powerline
- vimrc
tumblr_url: http://www.goatslacker.com/post/15818413221/why-vim-powerline-wasnt-working-properly-with
---
Recently I’ve been using this vim plugin called vim-powerline which has plenty of nice features like

Which git branch you’re currently on
Filetype and encoding
Line number/Character
Changes color for Insert mode
I highly recommend it.

Anyways, vim-powerline wasn’t working properly on my laptop though. Some files like .gitignore would work whereas others like sample.coffee wouldn’t. If I removed my ~/.vim/ftdetect folder most files would work but that wasn’t the solution.

I finally narrowed it down to my custom syntax highlighting colour scheme mango.vim. The offending line was this:

highlight clear


After looking into it I found out that highlight clear was clearing all of vim-powerline''s styles so for files where syntax highlighting was turned on, the plugin wasn’t working as expected.

So if you’re having difficulties installing vim-powerline, check to make sure your color scheme isn’t clearing highlights. Dark color schemes commonly have this set.

Installing vim-powerline is fairly easy. You’ll need to be on an 88 || 256 color terminal — so if you’re on OSX I definitely recommend iTerm2.

In your .vimrc file you’ll set the following

set nocompatible
set t_Co=256


Make sure Powerline.vim is in ~/.vim/plugin/ and Pl folder and Pl.vim is in ~/.vim/autoload/ and you should be all set.
