---
title: Desktop {{Vue}} Application
author: saumya
date: 2020-07-26
template: article.pug
---


Writing [Vue.js][vue] application is a pleasure to do. It is simple and developer experience(DX) is just too good. There are times when web application is the way to go.

<span class="more"></span>

There are times when a Desktop application is better than a web application. In the [Vue.js][vue] eco-system there are many utilities available.


>  [Vue CLI Plugin Electron Builder][2] 

This [Vue CLI Plugin][2] is the simplest one. All one has to do is, `install` it as a `npm` package and you are ready to go. Though this project recommends to use `Yarn`, but `npm` also works. To add the plugin to the already build [VueJS][vue] web application project, use the `vue cli` as below.

```
vue add electron-builder
```

That is all. The next is to run the desktop application.

In development mode it is like this.

```
npm run electron:serve
```

The last is to build the application and that is done with this.

```
npm run electron:build
```




Happy coding.





























[vue]: https://vuejs.org/
[2]: https://nklayman.github.io/vue-cli-plugin-electron-builder/







