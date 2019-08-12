---
title: Git, Forking and Syncing
author: saumya
date: 2015-5-19
template: article.pug
---

           
 
There are couple of things to understand before going to the commandline, just remember that we have assumed the name `UPSTREAM` as the repository, from where we have forked the project and `master` is our own remote repository where we save our changes.
Well, another important thing is to [configure][2] the `UPSTREAM` or simply configure a repository from where we want to sync.
```git
git remote -v
git remote add UPSTREAM https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git
```
For syncing forked repository, the commands are as below.
```git
git remote -v
git fetch UPSTREAM
git checkout master
git merge UPSTREAM/master
git push origin master
```          
This is a direct [tutorial from github][1].





Happy syncing.












[1]: https://help.github.com/articles/syncing-a-fork/
[2]: https://help.github.com/articles/configuring-a-remote-for-a-fork/


