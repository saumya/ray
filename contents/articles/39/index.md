---
title: AngularJS 101
author: saumya
date: 2014-06-24
template: article.pug
---



It took me sometime to make me comfortable in [AngularJS][1]. There are a lot of tutorials, discussions and videos out there about [AngularJS][1]. I would suggest, go through them and go through as many as you can, before jumping into code with this framework. We will be looking at the very basics of the framework here and for `version 1.3` and above, of the framework.    
You must heard about MVC or Model-View-Controller architecture and [AngularJS][1]. While thats true, lets keep that for a little late.          
First of all, just remember that `$scope` is model object and sometimes referred to as `ViewModel`. Then there are `Views`, which are either HTML tags or full html files. And then `Controllers`, which are javascript files. At this point always remember that [AngularJS][1] revolves arround these `View` and `Controller`. The data this `View` displays is the same as the data the `Controller` modifies and is available through `$scope`. No matter what, `$scope` remains in the middle as this     
`View <---$scope---> Controller`      
Now, since [AngularJS][1] already uses `2-way data binding` any changes to data or `$scope` in `View` or `Controller` is reflected by each other.       
An [AngularJS][1] application begins with a module named `ng-app` and this `ng-app` is generally only one. So what is a module ? Module is kind of self contained small applications inside a big application. The special module `ng-app` is the only exception as its the big application and everything else in [AngularJS][1] world happens inside it. All other modules generally go inside `ng-view`, have a look at [this html page][2] for the reference.In terms of [AngularJS][1], a module is a combination of a `View-$scope-Controller`. Everytime you need to load this module, the View gets loaded in the `ng-view` and its Controller gets initialised along with the `$scope`. All these mapping are written in a `Route`, which maps `View with Controller`, [take a look at this][3]. Route is a separate module as of [AngularJS][1] version 1.3. So, one need to include the JS file and the dependency. A quick reference of an [AngularJS][1] application looks as below        
 - HTML page
 - ng-app (root module)
 - ng-view (sub modules load here)
 - first JS file for Route and other things
 - Route maps URL paths with sub-views and their controllers
 - sub-views(HTML partials or pages) are loaded inside the ng-view and initialied with their controllers        

So far we are good. The next thing is, we can still make it more modularised. [AngularJS][1] allows, something called as `Directives`, you may think of it as components. Inside a `Module`, we can write our custom directives, which are `custom HTML tags` along with its `controller`. But always remember, `Directives` are part of `View`. So the `$scope` is also available to them. Now, there are different pre-built modules with [AngularJS][1] for different job in hand, like `$http` is for interacting with `web services`.         
[Refer to the project here][4], which I have created to better understand the basic of an [AngularJS][1] application. Always remember, anything in [AngularJS][1] that we write falls upon either `View` or `Controller` and there is always `$scope` available to both of these.        

I would love to listen your inputs on this, please leave a comment for discussion.         


Happy Coding.







[1]: https://angularjs.org/
[2]: https://github.com/saumya/ng-101/blob/master/index.html
[3]: https://github.com/saumya/ng-101/blob/master/js/saumyaApp.js
[4]: https://github.com/saumya/ng-101
