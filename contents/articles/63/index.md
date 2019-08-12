---
title: React with Router and Material UI
author: saumya
date: 2016-03-11
template: article.pug
---



This is a little more than just the basics. If you do not have any idea about [React][React-link], here are two links to get started with.          

 - [React Basics][blog-React-link]
 - [How to React][blog-HowToReactNow-link]          


Now that we know what is [React][React-link] and how to do the basics. Lets go a little further.<span class="more"></span>          

The best part of [React][React-link] is its all components and the whole application architecture is upon us. Being said that, once the application gets little complex, soon we need a structure. Either we do it ourselves or take a ready one. Same goes with the UI of the application. Fortunately there are several solutions available for both of these. We are going to focus on two today.           

 - [react-router][ReactRouter-link]
 - [Material-UI][MaterialUI-link]           

### react-router ###          

This takes care of the routing of the [React][React-link] application on frontend. It plays nice with other [React][React-link] components. Instead of manually keeping track of the addition and removal of components, its a nice solution to start with for only this purpose, though adding a router in frontend has its added advantages too.
 
> There are couple of tips here to use latest version(2.0) of [react-router][ReactRouter-link].

- Firstly there is no default `history` created, so we have to pass it on while creating our router.
- Secondly provide the `contextTypes` property to the components

```javascript
// Router creation
var ReactDOM = require('react-dom');
var hashHistory = require('react-router').hashHistory;
var routes = (
            <Route path="/" component={AppComponent}>
              <IndexRoute component={IndexComponent} />
              <Route path="see" component={ViewComponent} />
              <Route path="add" component={AddComponent} />
            </Route>
          );
var App = ReactDOM.render(<Router routes={routes} history={hashHistory} />,
							document.getElementById('react-app'));
```
In our component code, we have to provide the `contenxtTypes` propert as below.
```javascript
// contextTypes property setting in components
contextTypes: {
    router: React.PropTypes.object.isRequired,
  },
```
Now the programmatic routing is done through the `router` property of the `context` object. Once we put `contextTypes` property, we can get the `router` from it and through that, we can make our application to move to any other route. 
Here is an example.
```javascript
// programmatic routing
this.context.router.push('/see');
```          

### Material-UI ###          

This is directly an implemention of [Material design][Mdesign-google-link] guidelines from Google. Once we put this to use, application automatically abides to the design principles. This is a library of [react][React-link] components. So all we have to do is install the library and start using it by using its components.



Happy Reacting.


[React-link]: http://facebook.github.io/react/
[ReactRouter-link]: https://github.com/reactjs/react-router
[MaterialUI-link]: http://www.material-ui.com/
[Mdesign-google-link]: https://www.google.com/design/spec/material-design/introduction.html

[npm-link]: https://www.npmjs.com/
[node-link]: https://nodejs.org/en/

[blog-React-link]: http://saumya.github.io/ray/articles/57/
[blog-HowToReactNow-link]: http://saumya.github.io/ray/articles/58/















