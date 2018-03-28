---
published: true
layout: post
tags: R TIL tidyverse
---
I case across a new way to create a new variable with multiple groups in R using the `case_when` and `between` functions in dplyr.

Today I was attempting to create a column indicating the quarter based on a month column. Traditionally, I would be tempted to use a series of nested `ifelse` functions with conditions specified using `<=` and `>=` operators, but that can get messy.

By comparison, the syntax for `case_when` is pretty straightforward:

`case_when(condition1 ~ 'group name 1', condition2 ~ 'group name 2')`

The `between` function is similarly easy to understand:

`between(x, lower bound inclusive, upper bound inclusive)`

I've included example syntax using the two functions in concert. You can see how elegant the syntax is (as is usually the case for tidyverse functions compared to base R).

```r
mutate(df, quarter = case_when(
                  between(month, 1, 3) ~ "Q1",
                  between(month, 4, 6) ~ "Q2",
                  between(month, 7, 9) ~ "Q3",
                  between(month, 10, 12) ~ "Q4"
                )
       )
```
