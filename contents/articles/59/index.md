---
title: RequireJS is not require()
author: saumya
date: 2015-12-05
template: article.jade
---

It would have saved me time if I could have known this in the beginning. Like a lot of things in Javscript world, a same kind of name for two different functionalities makes a lot of confusion.          

[RequireJS][1] is used to load [AMD][2]          
require() is used to load [CommonJS][3]          

Well, to add to confusion the `require()` function is available to both the module definitions. But both the `require()` do different things. For [CommonJS][3] `require()` loads modules in a `synchronous` way, while the `require()` in [AMD][2] ie; in [RequireJS][1] the modules are loaded in `asynhronous` way.             
       

[AMD][2] style loading is
```javascript
require(['path/myModuleFileName.js'],function(MyModule){
  // Use MyModule
  MyModule.doSomething();
});
```        

In [CommonJS][3] its done as below
```javascript
var MyModule = require('path/myModuleFileName.js');
// the line below is same as above, just removed the file extention .js
//var MyModule = require('path/myModuleFileName');
```





Happy requiring.














[1]: http://requirejs.org/
[2]: http://requirejs.org/docs/whyamd.html#amd
[3]: http://requirejs.org/docs/whyamd.html#commonjs