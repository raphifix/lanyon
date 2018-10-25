---
published: true
layout: post
tags: Git TIL
---
Today I was experimenting with some changes to a codebase I had recently updated in Github. I was reaching a deadend and decided to go ahead and overwrite the local changes with the latest code from Github. However, using `git pull` and `git fetch` did not work. I was still looking at my locally modified code.

In order to overwrite the changes with the latest commit, I had to do the following:

1.`git reset --hard` - this tells Git to point to the last commit
2.`git pull` - this tells Git to pull down the code from said commit
