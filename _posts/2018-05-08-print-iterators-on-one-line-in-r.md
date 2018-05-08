---
published: true
layout: post
tags: r TIL
---
Sometimes when diagnosing problems in a `for` loop or just trying to keep track of progress, it can be helpful to print the iterator as the loop progresses. It can be annoying (especially for longer loops) for each iteration to be given its own line.

We can rectify this by by wiping the line clean each time. Here's how we can do it using `cat`.

```r
for(i in 1:10){
   cat("\r", i)
}
```
