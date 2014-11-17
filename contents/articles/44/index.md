---
title: RequireJS, Load timeout for modules!
author: saumya
date: 2014-11-17
template: article.jade
---

Working with [BackboneJS][3], will make you work with [RequireJS][4]. And if you are working with [BackboneJS][3] for a little time, then you probably know what I am talking about. Sometimes, the modules we are loading through [RequireJS][4] throw errors saying
```javascript
Error: Load timeout for modules
```     
I will suggest to have a look at [RequireJS][2] documentation for detailed explanation.     
The most common and which may hit you in the begining is the `timeout` for timeout itself. There are ways to fix this. The options are
- increase the timeout limit
- reload the page or the module on timeout error

The [RequireJS][4] configuration has an option called `waitSeconds`, which defaults to `7`. Now if the module does not load in 7 seconds, it will giveup and throw the error. If `waitSeconds` is set to `0`, it will wait for `infinite`. Well, along with that setting, set the `enforceDefine` to `true` for reliability in all browsers and scenarios. This setting will look as below.
```javascript
requirejs.config({
    enforceDefine: true,
    waitSeconds: 0,
```
Thats a quickfix. But again, it may hit the performace of the application.      
The otherway is [Errbacks][1] as per [RequireJS][4]. so what are they. They are simply callbacks but since it happens in errors, its called `Errbacks`. We can do stuff like reloading the whole application or the specified module or other error handling on these.
```javascript
require(['modules/one','modules/two'],
       	function(One,Two){
			//Application logic
		},
        function(error){
            console.log('Custom ERROR handler',error);
            //error.requireModules : is Array of all failed modules
            var failedId = error.requireModules && error.requireModules[0];
            console.log(failedId);
            console.log(error.message);
        });
```



Happy Coding.












[1]: http://requirejs.org/docs/api.html#errbacks
[2]: http://requirejs.org/docs/errors.html
[3]: http://backbonejs.org/
[4]: http://requirejs.org/




