---
title: React & Material-UI, recently breaking changes.
author: saumya
date: 2016-04-17
template: article.jade
---
Here we will talk about the recent changes in [Material-UI][2] and how it affects our [React][1] code.

Before moving further, if you have not yet started with [Material-UI][2], [here is my first post][3] describing the details. 

Current version of [React][1] is `15.0.1`. To make [Material-UI][2] compatible with this version of [React][1], a new version of [Material-UI][2] which is `0.15.0-beta.1` is released recently. However there are some breaking changes in this release of [Material-UI][2] if you are coming from the last version which is `0.15.0-alpha.2`. The complete [release note is here][4] along with the change logs.

There are couple of things to change in our [React][1] application code.

### import / require

The syntax for getting a component from [Material-UI][2] is changed. 

```javascript
// Use
var AppBar = require('material-ui/AppBar')['default'] ;
// Or
import AppBar from 'material-ui/AppBar';
// instead of
var AppBar = require('material-ui/lib/app-bar'); // deprecated
```

Notice 
 - there is no `lib` in between `material-ui` and `AppBar`
 - if using `require` , there is a `['default']` at the end

### default theme handling

The [default theme handling has changed][5] for components and for that, some changes are required in application code.

In the RootControllerView / MainControllerView, import the following.
```javascript
import baseTheme from 'material-ui/styles/baseThemes/lightBaseTheme';
import getMuiTheme from 'material-ui/styles/getMuiTheme';
```
In the same RootControllerView / MainControllerView, inside component declaration add
```javascript
childContextTypes:{
  muiTheme: React.PropTypes.object.isRequired,
},
getChildContext() {
  return {muiTheme: getMuiTheme(baseTheme)};
},
```
Here is [a little more][6] in-depth view of the scenario.



Happy Reacting.          













[1]: http://facebook.github.io/react/
[2]: http://www.material-ui.com/
[3]: http://saumya.github.io/ray/articles/63/
[4]: https://github.com/callemall/material-ui/releases
[5]: https://github.com/callemall/material-ui/pull/3820
[6]: https://github.com/callemall/material-ui/issues/4021














