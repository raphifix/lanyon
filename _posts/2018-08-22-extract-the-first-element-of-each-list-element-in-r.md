---
published: true
layout: post
tags: R TIL
---
The family of apply functions (including sapply, lapply, etc) allow for some pretty powerful data manipulation in R. Today I was able to use `sapply` to quickly solve a problem without using a loop.

One of the files I'm using for a project contains time ordered data. Instead of a single date per line, however, it also specifies the end date as such: `Jan 01 2018 - Jan 07 2018`. This makes reformating as a date impossible without munging. I'm only concerned with the first date on each row, so I needed a way to extract `Jan 01 2018`.

First, I split each row on ` - ` using the `strsplit` function. This returned a list, with each list element containing a character vector containg the start and end dates. But how do we extract just the first element?

That's where the apply functions come in. We'll use `sapply`, which can return a vactor, matrix, or array depending on the user's preference. The final call looks like this: ``` sapply(strsplit(df$date, ' - '), `[[`, 1) ```

So what's going on here? Well, the inner function `strsplit(df$date, ' - ')` does the date splitting. The `sapply` takes the list that `strsplit` returns and passes 2 arguments: ``` `[[` ``` and `1`, shorthand for `function(x) x[1]`. This is what tells sapply to extract the first element from each list element, which is a vector.
