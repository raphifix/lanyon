---
published: false
layout: post
tags: R TIL
---
I was helping a coworker setup R today. She was having problems because R kept trying to install packages to locations which required admin rights (which she doesn't have on her machine).

It's possible to change the install path on a per-package basis: `install.packages('package_name', lib = 'C:/my/library/folder')`.

But obviously this would be a chore to remember to do every time. Instead, we changed it system-wide by creating a personal library folder on which she has write permissions. Here's how:

1.Create a folder in a directory that you have write permissions in. Make note of the path
2.Go to `Control Panel > User Accounts > Change my environment variables`.
3.Create a new user variable and name it `R_LIBS_USER`.
4.Set the value to the path: `C:\my\library\folder`.
5.Now press `OK` and restart RStudio if it's still open (or just restart the R session: `Session > Restart R`)

Voila!