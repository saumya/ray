---
title: Dojo Toolkit, require and events.
author: saumya
date: 2015-1-14
template: article.pug
---

Well, lets say this, if you are working on [Dojo Toolkit][1], you are working on a legacy application. Since [Dojo Toolkit][1] is releasing its newer versions, you need to change your application to newer codebase. Currently [Dojo Toolkit][1] is leveraging [AMD][2] for modules and Javascript files. Which is very new for this toolkit and veteran developers in this toolkit may find its very different.          

Previously, when we needed some JS code, its simply done by making a 'require' call.          

```javascript
dojo.require("dojo.string");
//then use it
dojo.string.trim("  I Like Trim Strings ");
```          
Now it looks as          

```javascript
require(["dojo/string", "dojo/domReady!"], function(string){
  string.trim("  I Like Trim Strings ");
});
```          
Well that may seems fine now, but then what happens when we need something inside that `require` itself? Actually, its simpler than it seems, we can have `require` inside another require too.          

```javascript
require(["dojo/domReady!"], function(){
	//DOM is ready, load another module
	require(["dojo/string"], function(string){
	  string.trim("  I Like Trim Strings ");
	});
});
```          

Thats nice. Here [is the official documentation][3]. The introduction to [modern dojo][4] is here.                   
Another nice utility is [topic][5]. This is kind of central event dispatching and listening station. All one has to do is, dispatch events through [topic][5] and listen through it too. These are called `publish` and `subscribe` of events.          

```javascript
require(["dojo/topic"], function(topic){
    topic.subscribe("some/topic", function(arguments){
        console.log("received:", arguments);
    });
    // ...
    topic.publish("some/topic", "one", "two");
});
```         
The other kind of events are DOM events and [they are handled with the 'on'][6] module.          






Happy coding.












[1]: http://dojotoolkit.org/
[2]: http://requirejs.org/docs/whyamd.html#amd
[3]: http://dojotoolkit.org/reference-guide/1.7/dojo/require.html
[4]: http://dojotoolkit.org/documentation/tutorials/1.10/modern_dojo/
[5]: http://dojotoolkit.org/reference-guide/1.10/dojo/topic.html
[6]: http://dojotoolkit.org/reference-guide/1.10/dojo/on.html#dojo-on


