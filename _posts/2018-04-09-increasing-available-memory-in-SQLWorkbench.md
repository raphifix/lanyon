---
published: true
layout: post
tags: SQL terminal TIL
---
Every now and then I need to select a large number of rows from a database. Occasionally the amount of memory necessary will outstrip the amount allocated by the underlying JVM. We can get around this by launching SQLWorkbench from the commandline with an argument specifying the amount of RAM we want to allocate.

First, navigate to the directory with the SQLWorkbench jar file. In my case this is `Applications/SQLWorkbenchJ.app/Contents/Java`.

Then, run the following: `java -Xmx4g -jar sqlworkbench.jar`. `Xmx4g` is the key argument. Change it to the amount of memory you want to allocate. `Xmx4g` will allocate 4GB, `Xmx5g` 5GB, etc.

The app will look slightly different - the menubar will be inside the window - but otherwise it's  the same, just with more RAM!
