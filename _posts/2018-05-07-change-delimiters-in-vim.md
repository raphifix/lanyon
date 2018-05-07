---
published: true
layout: post
tags: terminal TIL Vim
---
I was working with a coworker to change the delimiter in a very large dataset on an EC2 instance. Vim made this a very painless process using the [substitute](http://vim.wikia.com/wiki/Search_and_replace) command.

First we ran `:%s/|/,/gc` to replace all `|` characters with `,`. Little did we know that the `c` stood for "confirmation". Unfortunately we didn't have the time to confirm all 44 million replacements, so we ran the command again without confirmation. Vim was able to replace all the pipes with commas in under 5 seconds. Not bad!
