---
title: jQuerymobile, changePage is deprecated as of 1.4.0, will be removed in 1.5.0.
author: saumya
date: 2014-02-11
template: article.pug
---


This is really going to break things, if someone is updating the library to latest version. This is a very frequently used function and chances are, that, in a mobile web application its being used everywhere. Lets remind ourselves again that `jQuery.mobile.changePage` is `deprecated as of 1.4.0` and `will be removed in 1.5.0`.      
Now there are vaious ways to change page in a [jQuerymobile][2] application. Here are the 3 options to do the page change in the new API.
```javascript
$(":mobile-pagecontainer").pagecontainer("change", "target", { options });
//or
$.mobile.pageContainer.pagecontainer("change", "target", { options });
//or
$("body").pagecontainer("change", "target", { options });
```
[Here is the official document for reference][1]     

Happy coding.



[1]: http://api.jquerymobile.com/jQuery.mobile.changePage/
[2]: http://jquerymobile.com




