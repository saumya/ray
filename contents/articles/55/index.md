---
title: AngularJS 102
author: saumya
date: 2015-11-25
template: article.pug
---
This is the part two of the study of [AngularJS][1]. The first part is [AngularJS 101][2].
This is focused on the vary basic concepts of [AngularJS][1] like how and where to write a `controller` or `directive` etc. The [sample project is here][5].          

First thing first, as of any Javascript framework, the nature of [AngularJS][1] is not different in terms of, where you should write what. This is understood, as Javascript itself is dynamic in nature. There are a lot of guidelines through out the web as to, which file to contain what. In the end it boils down to personal preference. So just go ahead and do some working samples of yours.

 - The first thing you need is `index.html` or some `.html` file, which will be your entry point to the project.
 - Include all the Javascript files in this `index.html` file as needed
 - [AngularJS][1] does not need [JQuery][3], but if you are using [Bootstrap][4], you will need [JQuery][3] library as the later uses it. So include them in the `index.html`
 - Include the CSS framework files in the `index.html`
 - All in all, include all the files necessary in the project in `index.html`

Well, there are ways to minify and combine all of them in a single file and all those tricks. We can focus on them later. For the timebeing lets focus on how to build [AngularJS][1] applications.
 
 - In the end include your `application.js` file, which will be your application entry file. Name of the file is not relevant, you can name it anything.

All of the application could be written in a single Javascript file or the application could be divided to be written in different Javascript files, each having a particular scope of work. Whatever the case may be, just remember each Javascript file should be an [AngularJS][1] module.
```javascript
(function(){'use strict';
var appModule = angular.module('app.Main',["ngRoute","ngResource"]);
})();
```           

The general convention is to wrap each module inside an immediately invoking function, just not to pollute the global space of the Javascript. As in the example above, we are using `ngRoute` and `ngResource` in our module `app.Main`. 
 - Each Javascript file should be an [AngularJS][1] Module
 - Each module can use another module as a dependency and that can be passed in as a parameter in the array as shown above
 - By now, you must have noticed, the name of the Javascript file and the name of the module might be different. As long as we provide proper name as dependecy and proper name for the script src, it is all good.          

Actually in the example above, the dependent modules `ngRoute` and `ngResource` is not present in the `angular.js` Javascript file . These modules are written in separate Javascript files as modules. So we need to include `angular-route.js` and `angular-resource.js` in our `.html` file to use them, else it will through error.       

```html
<script type="text/javascript" src="js/lib/angular-1.4.7/angular.js"></script>
<script type="text/javascript" src="js/lib/angular-1.4.7/angular-route.js"></script>
<script type="text/javascript" src="js/lib/angular-1.4.7/angular-resource.js"></script>
```       
Have a look at the [Sample Project][5].   
Lets define another module in a javascript file named `one.js`.
```javascript
(function(){'use strict';
  var mOne = angular.module('module.one',[]);
})();
```
Now lets expose a factory from this module.
```javascript
(function(){'use strict';
  var mOne = angular.module('module.one',[]);
  mOne.factory('oneFactory',function(){
    var service = {};
    return service;
  });
})();
```
To use this factory in our project. We have to 
 - include the `one.js` in our html file
 - add the module name `module.one` in our application entry file          

So the application entry file will look as below

```javascript
(function(){'use strict';
  var appModule = angular.module('app.Main',["ngRoute","ngResource","module.one"]);
  // Now, we can use 'oneFactory' here, as its exposed by 'module.one'
})();
```          
Each Javascript file should be an [AngularJS][1] module.
 - Each module could expose any number of anything. That means, any module could expose more than one Object. Those Objects could be any [AngluarJS][1] Object types, such as Controller, Factory, Service, Directive etc.
 - As long as we are providing a dependency of the module name in the Array and refering the proper name of the Objects, we can use them.

`Directives` in [AngularJS][1] are `visual elements`. They define custom HTML tags/elements as per their definition.

Take a look at the [Sample Project][5] and that should clear a lot of things, which might seem unclear here. [AngularJS][1] is modular in the sense, there are carefully separated modules for different purposes. When in need, we include those Javascript files and add the dependecies in the Array. The same goes for our own modules. Try to separate out functionalities into their own modules and use it when needed.   

Hopefully that will get you started with the framework.













[1]: https://angularjs.org/
[2]: http://saumya.github.io/ray/articles/39/
[3]: https://jquery.com/
[4]: http://getbootstrap.com/
[5]: https://github.com/saumya/ng-102