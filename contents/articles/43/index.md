---
title: Upgrading to Cordova 3.4 and above
author: saumya
date: 2014-10-23
template: article.jade
---

While trying to upgrade, one of my previous Cordova Android application, to [Cordova][1] , noticed that [Cordova][1] now makes it very difficult to switch to a native development workflow. Its not the flow itself, which is difficult, but the information about the flow and to get started with a project which is the problem. If you have ever worked with the native development flow of [Cordova][1] , which I guess you must have, as that was the actual flow in the beginning. Then its exactly the same work flow, but the thing is, its not mentioned anywhere. And in between these, they had introduced a web development workflow and tried forcing to use it. Which itself is not clear and then combined the native workflow with it. Good that, that period is over. But its not clear at all from the docs.
Well, first of all, [Cordova][1] is saying its released the version 4 of the toolkit. When you go to [download][2] section for native development workflow, you will [not find a version 4][3] ! So, you have to go inside [platforms][4], there also you will not find version 4. So, I ended up downloading 3.6.4 for android and will suggest everyone to do that for the time being. After downloading the zipped file, extract it to a folder. Navigate to the folder and fireup the cordova create command to create a project.
Next is adding the plugins, because now [Cordova][1] does not include plugins by default. For that, one has to go back to Cordova CLI and that can be done with Node and NPM. But instead of running Cordova to add plugins, one has to run Plugman to install plugins.

The flow is 
- download Cordova Native development package
- download Node and NPM
- install Cordova and Plugman through NPM
- create project from inside the dowloaded Cordova folder
- navigate to the project folder
- run the Plugman command to add plugins to the project




Happy Coding.












[1]: http://cordova.apache.org/
[2]: http://cordova.apache.org/#download
[3]: https://www.apache.org/dist/cordova/
[4]: https://www.apache.org/dist/cordova/platforms/

