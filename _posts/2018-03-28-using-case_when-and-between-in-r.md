---
published: false
---
I case across a new way to create a new variable with multiple groups in R using the `case_when` and `between` functions in dplyr.

Today I was attempting to create a column indicating the quarter based on a month column. Traditionally, I would be tempted to use a series of nested `ifelse` functions, but that can get difficult to interpret fairly quickly.

The syntax for 

I've included example syntax below. You can see how much more elegant the syntax is (as is the case for the "tidyverse" in general compared to base R).

```r
mutate(df, month = as.numeric(format(week, '%m')),
                quarter = case_when(
                  between(month, 1, 3) ~ "Q1",
                  between(month, 4, 6) ~ "Q2",
                  between(month, 7, 9) ~ "Q3",
                  between(month, 10, 12) ~ "Q4")
```