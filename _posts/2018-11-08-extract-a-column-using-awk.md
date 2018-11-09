---
published: true
layout: post
tags: Awk terminal TIL
---
Awk makes it easy to extract a column in a csv or text file. Here's an example:

`awk -F"," '{print $1}' ~/Documents/filename.txt > ~/Desktop/newfile.txt`

`-F` definds the file delimiter. In this case, the file is comma-delimited.<br />`'{print $1}'` defines the field we want to extract. In this case, we want the first field.

The rest is straightforward. We specify the input file, and use `>` to pipe it into a new file.
