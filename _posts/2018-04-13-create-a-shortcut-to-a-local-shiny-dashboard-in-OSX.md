---
published: true
layout: post
tags: R Shiny terminal TIL
---
I was helping my mother with a copywriting project that required extracting specific tags from 200+ pages on a particular website. I was able to quickly whip up an in R using Shiny, but due to certain restrictions, I couldn't host the app online. Instead, I installed R and RStudio on her machine and showed her how to launch the app.

To make things easier, I decided to create a desktop shortcut to the app so she could avoid having to load RStudio and manually launch the app every time she needed it.

Luckily in OSX this process is relatviely straight-forward:
1. Create an empty plain-text file with the ".command" extension.
2. Inside the file, type the following: `R -e "shiny::runApp('/path/to/your/app.R', launch.browser = TRUE)"`
3. Save the file.
4. Open the terminal, and type: `chmod +x /path/to/your/shortcut.command`. This will make the shortcut executable.

That's it! When you double-click on the shortcut, a terminal instance will launch, R will run, and your Shiny app will open in your default browser.
