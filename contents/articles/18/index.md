---
title: Git commit throws fatal error for line endings.
author: saumya
date: 2014-01-27
template: article.jade
---

This comes to me in a regular basis, thought it would be nice, to keep a note to me and anyone else dealing with same.     

The short answer to fix this is
```
git config core.safecrlf warn
```
There are more descriptive answers available and [here is a link to one of many solutions out there][1].


Happy hacking.



[1]: http://stackoverflow.com/questions/15467507/trying-to-commit-git-files-but-getting-fatal-lf-would-be-replaced-by-crlf-in






