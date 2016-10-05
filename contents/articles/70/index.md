---
title: Fixing NPM permissions
author: saumya
date: 2016-10-05
template: article.jade
---
The problem is to use `sudo` everywhere and try to fix things that way. Especially while dealing with global [NPM][2] modules. Sometimes it may happen that `sudo` also will fail to install.   

`TL;DR:` The fix I am using is to `change` the `user permission` to `current user`.   

<span class="more"></span>

Here are some basic commads to get the things going.         

Get the global npm modules path 
```
npm config get prefix
```
Details about all the files and their permission to owners
```
ls -la /usr/local/lib/node_modules
```

Change the owner of the files recursively to the new user name
```
sudo chown -R user_name /usr/local/
```

Prints the current user
```
whoami
```

When you are using `sudo` to install anything, it will create a folder named `.staging` as `root` owner, inside the `node_modules` folder and keep the installed module there but could not move the module to actual folder and so eventually fail. 

The fix is to change the permission of the `/usr/local/` recursively to the current user. Then install the modules `without` `sudo`.  Well, the [official video on the doc][1] says you can actually just change the permission of below three directories inside `/usr/local/` instead of all the directories inside `/usr/local/`
 
 - /user/local/lib/node_modules
 - /usr/local/bin/
 - /usr/local/share/



<iframe width="560" height="315" src="https://www.youtube.com/embed/bxvybxYFq2o" frameborder="0" allowfullscreen></iframe>

Happy nodding.












[1]: https://docs.npmjs.com/getting-started/fixing-npm-permissions
[2]: https://www.npmjs.com/














