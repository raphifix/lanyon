---
published: false
layout: post
tags: Redshift SQL
---
There is a particular field in a key table in our Redshift DB that contains HTML. This makes it tricky to export to a file and open in R or Python. Prior to export, it is important to remove the new line characters.

To do so, you might think you would be able to use `REPLACE(html_column, '\n', ' ')` but this does not work. You need to specify the character via ASCII representation inside the `CHR` function. [Here is a lookup table](https://www.asciitable.com/) of ASCII for other characters. The new line character is represented by the number 10, so we can replace the new line characters like so:

`REPLACE(html_column, CHR(10), ' ')`
