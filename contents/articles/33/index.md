---
title: jQuery and fixing AJAX cache for GET calls 
author: saumya
date: 2014-04-03
template: article.jade
---



It will come to you very soon, if you are trying to develop any decent webapp or phonegap mobile app using [jQuery][1].     
The problem is, if we have the same `GET` request multiple times, by default jQuery will cache the request. The end result is the response same as the first response!! Well, there is a setting in jQuery AJAX setup, where in we write `cache:false` and that should work. Well, depending upon how the API is written on the server side, this call might not work! There are many reasons as to why it may not work, one simple reason is, to understand, how [jQuery][1] behaves, when we set `cache:false` as below.

```javascript
var apiURL = "my/api/server/URI";
$.ajax({
    url:apiURL,
    cache: false,
    success:function(result){
    	//
    },
    error:function(data){           
        //            
    }   
});
``` 
Now, [jQuery][1] will append `_={timestamp}` to the GET parameters. Here is the [official documentation][2] of the same. The service call will fail, if this extra parameter is not handled properly. A little workarround, fixed this for me, which is appending the timestamp mannually by hand instead of setting `cache: false` in AJAX setup of [jQuery][1]. The modified code looks as this.
```javascript
var timeStamp = new Date().getTime();
var apiURL = "my/api/server/URI/"+timeStamp;
$.ajax({
    url:apiURL,
    //cache: false,//not needed now
    success:function(result){
    	//
    },
    error:function(data){           
        //            
    }   
});
```
Well, that worked for me as my API end point was not handling '_'(underscore) properly, but could handle the extra parameters.     
Depending upon the situations, find a right place and `add timestamp mannually`, to fix the AJAX cache instead of setting it in the setup.     

Happy Coding.





[1]: http://jquery.com/
[2]: https://api.jquery.com/jQuery.ajax/



