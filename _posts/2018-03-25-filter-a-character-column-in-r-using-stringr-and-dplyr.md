---
published: true
layout: post
tags: R TIL tidyverse
---
Using the `str_detect` function in the `stringr` package in concert with the `filter` function from `dplyr` allows you to quickly filter a character vector using regex.

Usage: `filter(df, str_detect(column1, 'pattern'))`
