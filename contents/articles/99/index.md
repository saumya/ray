---
title: Vuex Actions in Vue
author: saumya
date: 2020-07-27
template: article.pug
---




Vuex Actions in [Vue][vue] are part of the [Store][ref1] as we have seen in the [Vue basics][ref1].

<span class="more"></span>

From a [Vue][vue] component in order to dispatch actions, it is as simple as this.

```
this.$store.dispatch('auth/login_action', user)
```

However, [Vuex][vuex] provides helper and utilities to do it even in more readable manner. First of all, one has to get the [Vuex][vuex] into the component.

```
import { mapActions } from 'vuex'
```

Next is the actual map of the dispatch code to a function call.

```
methods : {
	...mapActions({ 
		login : 'auth/login_action'
	})
}
```

Now, wherever necessary one can call `login()` which will dispatch the action. The code will look something like calling a function.

```
login(user)
```

What is done by `mapActions` from [Vuex][vuex] is a mapping of `login` function to `this.$store.dispatch( 'auth/login_action', user )`. Wherever the `login(user)` is called, it is actually doing `this.$store.dispatch( 'auth/login_action', user )`.

```
// Now both are same

login(user)
 
this.$store.dispatch('auth/login_action', user)
```




Happy coding.





























[vue]: https://vuejs.org/
[2]: https://nklayman.github.io/vue-cli-plugin-electron-builder/
[vuex]: https://vuex.vuejs.org/guide/actions.html

[ref1]: https://saumya.github.io/ray/articles/94







