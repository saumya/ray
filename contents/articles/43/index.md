---
title: Upgrading to Cordova 3.4 and above
author: saumya
date: 2014-10-23
template: article.jade
---

While trying to upgrade to one of my previous Android applications to [Cordova][1] , noticed that the [Cordova][1] now makes completely difficult to switch to a native development workflow. Its not the flow itself is difficult, but the information about the flow and to get started with a project is the problem. If you have ever worked with the native development flow of [Cordova][1] , which I guess you must have, as thats was the actual flow in the beginning. Then its exactly the same work flow, but the thing is, its not mentioned anywhere. And inbetween these, they had introduced a web development workflow and tried forcing using it. Which itself is not clear and then combined the native workflow with it. Good that, that period is over. But it not clear atall from the docs.
Well, first of all, [Cordova][1] is saying its released the version 4 of the toolkit. When you go to [download][2] section for native development workflow, you will [not find a version 4][3] ! So, you have to go inside [platforms][4], there also you will not find version 4. So, I ended up downloading 3.6.4 for android and will suggest evryone to do that for the timebeing. After downloading the zipped file, extract it to a folder. Navigate to the folder and fireup the cordova create command to create a project.
Next is adding the plugins, because now [Cordova][1] does not include plugins by default. For that, one has to go back to Cordova CLI and that can be done with Node and NPM. But instead of running Cordova to add plugins, one has to fire up Plugman to install plugins.

The flow is 
- download Cordova Native development package
- download Node and NPM
- install Cordova and Plugman from NPM
- create project from inside the dowloaded Cordova package
- navigate to the project folder
- run the Plugman command to add plugins to the project




Happy Coding.












[1]: http://cordova.apache.org/
[2]: http://cordova.apache.org/#download
[3]: https://www.apache.org/dist/cordova/
[4]: https://www.apache.org/dist/cordova/platforms/

