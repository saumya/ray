---
title: Migration checklist for Cordova(Phonegap) application from version 2.x to 3.x 
author: saumya
date: 2014-02-27
template: article.jade
---


There might be chances that you are re-writing a project or simply maintainig an old codebase of a [Cordova][3](phonegap) application. In both the cases, its ideal to go for the lastest version of the library. Being said that, its not that straight forward to migrate a phonegap 2.x application to Phonegap 3.x. And if, the project uses a 1.x version of [jQuery][1] with [jQuerymobile][2], you might want to update that to 2.x too, which adds up to more confusion and work, than solution. I will be focusing on [Cordova][3] rather than [Phonegap][4] here. Yes, they are different! They are supposed to be the same but there are differences.      

### Here is a checklist to keep things in perspective.
### Cordova
- Get used to [NodeJS][5]. Yes, thats now mandatory to use.
- Get used to [Cordova][3] and [Phonegap][4], they are different.
- Know the difference between [Cordova][3] and [Phonegap][4], at-least what they do internally.
- [Read completely the getting started][6] with [Cordova][3].
- Do not confuse with [Web Project Dev][7] work flow, if possible avoid it altogether.
- Start with [Native Platform Dev][7] workflow. This is the one, which is closer to the older version workflow.
- Do not use [CLI][8] for creating project. You can download the [whole archive for a version][9] as you used to in the previous versions and still can create project with it.
- Get used to [Plugman][10] to manage plugins. Everything is now a plugin. That means, a default project created, is nothing more than a website. If you need to interact with a device, you have to add plugin. In [Native Platform Dev][7], these are managed by [Plugman][10].
- For the first couple of trials, [add all the plugins][11]. That will make the project, behave as the older version projects, where everything is set by default. The document to install plugin is misleading.     

`Instead` of

```
plugman --platform --project --plugin org.apache.cordova.battery-status
```

`Use`, the commands as below. The document is missing `--install` from the command!
```
plugman --install --platform --project --plugin org.apache.cordova.battery-status
```
The actual code will look as
```
plugman --install --ios --path/to/project/folder --plugin org.apache.cordova.battery-status
```
- Get used to `config.xml`, [for configuring the whole project][12]

### jQuery and jQueryMobile
- Update the [page change code][13] to remove the deprecated one and use the new one.
- Update the event listener code from deprecated [live()][14] to [on()][15].
- Keep an eye on all the [deprecated][16] APIs of jQuery

That should make you compile your old project in the new code.

Happy transitioning.





[1]: http://jquery.com
[2]: https://jqueryui.com/
[3]: https://cordova.apache.org/
[4]: http://phonegap.com/
[5]: http://nodejs.org/
[6]: http://cordova.apache.org/docs/en/3.4.0/guide_overview_index.md.html#Overview
[7]: http://cordova.apache.org/docs/en/3.4.0/guide_overview_index.md.html#Overview_development_paths
[8]: http://cordova.apache.org/docs/en/3.4.0/guide_cli_index.md.html#The%20Command-Line%20Interface
[9]: http://archive.apache.org/dist/cordova/
[10]: http://cordova.apache.org/docs/en/3.4.0/plugin_ref_plugman.md.html#Using%20Plugman%20to%20Manage%20Plugins
[11]: http://cordova.apache.org/docs/en/3.4.0/plugin_ref_plugman.md.html#Using%20Plugman%20to%20Manage%20Plugins_installing_core_plugins
[12]: http://cordova.apache.org/docs/en/3.4.0/config_ref_index.md.html#The%2520config.xml%2520File
[13]: http://api.jquerymobile.com/jQuery.mobile.changePage/
[14]: http://api.jquery.com/live/
[15]: http://api.jquery.com/on/
[16]: http://api.jquery.com/category/deprecated/




