---
title: Referring Global variables and DOM Nodes in {{Vue}} application
author: saumya
date: 2020-08-02
template: article.pug
---





We know [Vue basics][ref1] and how it works.
However there are times when in a [Vue][vue] application we need to refer to some global variables. May be these are loaded in the `script` tag in the `.html` file or defined somewhere else.

<span class="more"></span>

### Global Variables

If we directly refer them, then the compiler will throw error and will not compile forward.

The way is to declare them initially while initialising the [Vue][vue] application itself. This is the `main.js` which is generally the entry point to the application. However to clear it further, let's say this is the file where we have this code.

```
new Vue({
  el: '#app',
  router: router,
  store: store,
  render: (h) => h(AppContainer)
})
```

Any `Gloabl` variable which need to be accessed inside the [Vue][vue] application has to be added just before this `new Vue()` call.

```
Vue.prototype.GloablVar = window.GloablVar;
//
new Vue({
  el: '#app',
  router: router,
  store: store,
  render: (h) => h(AppContainer)
})
```

Now this `GlobalVar` is available inside the [Vue][vue] application.

```
const GloablVar = window.GloablVar
```

Even this can be written and executed without any errors.

```

<div>{{ GloablVar.someBooleanVar ? "Yes" : "No" }}</div>
```


### DOM Nodes

There are times when some DOM nodes from inside the `<template>` is required to be addressed inside the `methods`. This is done with `refs`. 

In template it looks like this.

```
<div ref="appContainer">
</div>
```

In the methods it can be referred with `this.$refs`.

```
onSomeMethod: function(){
	console.log( this.$refs.appContainer )
}
```




Happy coding.





























[vue]: https://vuejs.org/
[vuex]: https://vuex.vuejs.org/guide/actions.html

[ref1]: https://saumya.github.io/ray/articles/94







