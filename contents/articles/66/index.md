---
title: React and understanding Redux, Thunk, Router.
author: saumya
date: 2016-05-12
template: article.jade
---
[React][15] is the view as they call it in a MVC (Model-View-Controller) world. Actually it is enough to build the whole frontend with [React][15] and its components. One does not need anything else to make a [React][15] application. Then comes a time, when one thinks of organising the code. Well, then and only then the things we talk now will make sense.

<span class="more"></span>
I asked and you may too, "so what are these fancy terms are for?" 
### TL;TR What is what ?

 - [Redux][14] is Model or Data or State (Whatever you call it) 
 - [Thunk][3] is helping [Redux][14] for communicating with Servers and getting data
 - [Router][10] is making the application to display specific things on navigating to specific URL

Now for those who need details about each.

### React and its universe

The best thing is, about pick and choose. Instead of a monolithic application framework, if the things are so nicely done that one can pick and choose between them to use in an application, it would be really nice. Most importantly at anypoint one should be able to swap between different implementations of the same thing. And [React][15] universe is full of these kind of implementations.

[React][15] is just to make visual components. There is nothing else to it. The exciting thing is there exists a whole universe arround [React][15] which does a lot of things to help build the application. There are different frameworks which use [React][15] and guidelines from facebook known as [Flux][16]. The community is building a lot of things arround [React][15] too. 

Once components are done and you are ready to work with data, instead of putting the data logic all arround the place, it feels right to put them at one place. [Redux][14] which follows the [Flux][16] guidlines makes it possible to do data management easier. If you know a little about [Flux][16] then the difference is [Flux][16] deals with a lot of `stores` in the application, while [Redux][14] deals with a `single store`. Do not be afraid to the term `store`, as simply speaking a `store` is the `model` or `data`. So we can say [Flux][16] deals with a lot of models while [Redux][14] deals with a single model. In [Redux][14] you design your application in such a way that anywhere in the application, the data is coming from one single model / store.

Now we know that we have view and model on frontend. We need a way to communicate with backend to get data and give back data. There comes in [Thunk][3]. It helps our [Redux][14] applications to sync with server. Talking about [Thunk][3], its actually a middleware to [Redux][14]. Which means, [Redux][14] has a concept of `middleware`. Simply put we can plugin different functionality to [Redux][14] with our own code.

Well, we got data from server and created our application with components. Now a full application can be built using just these. However, we need a way to show different user interfaces when going to different URLs. As we can develop whole application without a Model layer, we can do the same here too. But the thing is [Router][10] makes our life easier in these scenarios. If we want to navigate to different URLs depending upon our usecase and show different UI, then [Router][10] makes it very easy for us.

Combining all these together, we get a framework consisting of traditional model,view and controller or whatever you call it.

The nice thing about [Redux][14] and [Router][10] is they play nicely with each other so that you play nicely with [React][15].

Happy Reacting.          













[21]: http://facebook.github.io/react/
[16]: http://www.material-ui.com/
[17]: http://saumya.github.io/ray/articles/63/
[18]: https://github.com/callemall/material-ui/releases
[19]: https://github.com/callemall/material-ui/pull/3820
[20]: https://github.com/callemall/material-ui/issues/4021

[1]: http://redux.js.org/docs/basics/ExampleTodoList.html
[2]: http://redux.js.org/docs/advanced/AsyncActions.html
[3]: https://github.com/gaearon/redux-thunk
[4]: github.com/reactjs/redux/blob/master/examples
[5]: https://medium.com/@firasd/quick-start-tutorial-using-redux-in-react-apps-89b142d6c5c1
[6]: https://github.com/fusenlabs/20v
[7]: https://react.rocks
[8]: https://github.com/saumya/react-redux-thunk-101
[9]: https://github.com/acdlite/redux-router#differences-with-react-router-redux
[10]: https://www.npmjs.com/package/react-router
[11]: https://github.com/reactjs/react-router-redux
[12]: https://github.com/StevenIseki/react-router-redux-example
[13]: https://github.com/reactjs/react-router-tutorial/tree/master/lessons/12-navigating#navigating-programatically
[14]: https://github.com/reactjs/redux
[15]: https://github.com/facebook/react
[16]: https://facebook.github.io/flux/














