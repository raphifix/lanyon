---
published: false
layout: post
tags: R tidyverse TIL
---
You can change the data type of all columns in an R dataframe by useing `mutate_all`.

For example, if you want to change the columns to character, you can use `mutate_all(df, as.character)`.
