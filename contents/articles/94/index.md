---
title: Vue {{ it }}
author: saumya
date: 2020-06-09
template: article.pug
---


Working with [Vue][vue] is just sweet. 
The most important thing for me is less noise in the web.

> While the community is active, very active, no one is making a loud noise throughout the internet. I think that is because, no one is trying to please the corporates they are working for and they are targetting to. Which is a very good sign as far as the framework goes.

Appart from that, the documentation is just spot on. There is no way anyone will get to a wrong place and search for answers somewhere else. 

The eco-system for the framework is also just spot on and their documentation is as sweet. It all just works.

<span class="more"></span>

### Vue {{ Basics }}

The base of a [Vue][vue] application is a [Vue][vue] file. Yes, the extension is `.vue` so the file is 'filename.vue'. 

It has three parts.

 - template
 - script
 - style

Those are self explanatory. The `template` contains the 'html', `script` contains 'javascript' and `style` has the 'css'. Here is a basic [Vue][vue] file. Generally every [Vue][vue] file is a [Vue][vue] Component.

``` 
<template>
  <div class="one">
    <h1>One</h1>
    <h2>Home.</h2>
  </div>
</template>

<script>
export default {
  name: 'One'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
a {
  color: #42b983;
}
</style>

```

There are two main things one will need from the eco-system, [Vue Router][vr] and [VueX][vx].

 - [Vue Router][vr] is for making our URLs and mapping the URLs to respective components.
 - [Vuex][vx] is for using a global store / state / data, whatever you call it.

### Router {{ Example }}

```
export default new Router({
    routes: [
				{ path: '/home', component: HomeComponent },
				{ path: '/about', component: AboutComponent },
			]
```

Inside the first [Vue][vue] component of the application, that is the initial view of the application just have `router-view`, where the routing components will be rendered.

```
<div class="app_container">
	<router-view></router-view> 
</div>
```

### VueX {{ Example }}

A basic store / state / data file is like this.

```
//myData.js

const state = {};
const getters = {};
const actions = {};
const mutations = {};
export default { state, getters, actions, mutations }
```

Example with a basic working file. 

```
const state = {
	user_message : 'Nothing yet!',
};
const getters = {
	getUserMessage: state => {
		return state.user_message
	}
};
const actions = {
	doSomethingWithData: ({state,commit},payload) => {
			//payload is someDataObject that is explained below
			fetch( url_1, fetch_data ).then(function(result){}).catch(function(error){});
			commit('UPDATE_MESSAGE', 'Doing something');
		},
};
const mutations = {
	UPDATE_MESSAGE:  (state, message) => {
		state.user_message = message;
	}
};
export default { state, getters, actions, mutations }
```

From the [Vue][vue] file one just needs to dispatch actions like this.

```
this.$store.dispatch('doSomethingWithData', someDataObject);
```

In this example, `someDataObject` will be the `payload` inside the actions call. Inside the `action` one may need to call the `commit` if it is needed to change the store / state. Like we are calling `commit('UPDATE_MESSAGE', 'Doing something')`. That will go inside the `mutation` and run the respective function to change the state / store / data.

To get the data inside [Vue][vue] file, we have to do something like this.

```
<div> {{ getUserMessage }} </div>
```

The `{{ }}` is the thing that will convert the variable inside it to the value of it. Basically running javascript inside the template tags. 

The `most important` of all, is to add `store` and `router` to the initial part, where the Vue Application is initiated.

```
import Vue from 'vue'
import App from './App.vue'

import router from './router'
import store from './store'

new Vue({
  el: '#app',
  router: router,
  store: store,
  render: function(createElement){
    return createElement(App)
  }
})
```

As I have mentioned above, add the `router-view` component in the first [Vue][vue] file. In this case it is the 'App.vue'. Example is as mentioned here.

```
<template>
	<div class="app_container">
		<router-view></router-view> 
	</div>
</template>
<script>
export default {
  name: 'app',
}
</script>
```


Happy {{Vue}} coding.


























[sequelize]: https://sequelize.org/
[node]: https://nodejs.org/en/about/
[express]: http://expressjs.com/

[vue]: https://vuejs.org/
[vx]: https://vuex.vuejs.org/
[vr]: https://router.vuejs.org/







