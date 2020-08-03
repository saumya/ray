---
title: Putting Icons in Electron{{Vue}} application
author: saumya
date: 2020-08-03
template: article.pug
---



This is the next step once there is a basic [Electron][1] application in place.

 - Basics of [Vue][ref1]
 - [Desktop Application][ref2] in [Vue][ref1]
 - [Vue CLI Plugin Electron Builder][vueplugin]

<span class="more"></span>

### Setting Icons

Install `electron-icon-builder`, [which creates all the icons][electronplugin2] for all the platforms from a single file. Here is the documentation of [electron-icon-builder][vueplugin2] at [Vue ClI Plugin Electron Builder][vueplugin2]

 - Install electron-icon-builder
 ```
 npm install --save-dev electron-icon-builder
 ```
 - Place an image file with name 'icon.png' inside 'public' folder (public/icon.png). This file should be 1024px x 1024px or larger and 1 to 1 aspect ratio on width to height.
 - Add the 'npm' script
 ```
 "electron:generate-icons": "electron-icon-builder --input=./public/icon.png --output=build --flatten"
 ```
 - Run the script
 ```
 npm run electron:generate-icons
 ```
 - That is all to create the icons. The icons will be put inside the folder named 'build'
 - Next is to build the project
 ```
 npm run electron:build
 ```
 - That is all

Read more about it at the [Vue CLI Plugin Electron Builder][vueplugin2] documentation.





Happy coding.





























[vue]: https://vuejs.org/
[vuex]: https://vuex.vuejs.org/guide/actions.html
[vueplugin]: https://nklayman.github.io/vue-cli-plugin-electron-builder/
[vueplugin2]: https://nklayman.github.io/vue-cli-plugin-electron-builder/guide/recipes.html#icons
[electronplugin2]: https://www.npmjs.com/package/electron-icon-builder

[1]: https://www.electronjs.org/

[ref1]: https://saumya.github.io/ray/articles/94
[ref2]: https://saumya.github.io/ray/articles/98/







