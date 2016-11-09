---
title: React Native, Android and Loading embeded HTML pages in WebView
author: saumya
date: 2016-11-09
template: article.jade
---
The problem is in Android release builds, where the local HTML files do not load. This is not a problem in debug builds. I have not tested the final iOS builds. Loading of a local html file in a webview in [React Native][1] is as simple as this.

```
<WebView source={{ uri: '../assets/generic.html' }} />
```    

<span class="more"></span>

First thing is, the code above might not work. Why I say `might` is, it sometimes works ! Well, the fix to this situation is to use a `require` as shown below. Which works everywhere, all the time.

```
<WebView source={ require('../assets/generic.html') } />
```    

All is fine till you are building and testing from your machine with USB debugging. Once you move forward to a release build and test the app on a device, the HTML pages stop to load! Un/Fortunately its a known issue, look [here][4] and [here][3]. If you have gone through the links, then probably got the solution. I will just keep a note here for easy reference.     

The fix is a two step process.

 1. Manully copy the HTML pages to `android/app/src/main/assets` folder
 2. Change the reference in code to `file:///android_asset` instead of `./ or ../` for example `file:///android_asset/generic.html`       

We are done. Build and release your Android app.           


Just remember that, whatever is available inside `android/app/src/main/assets` folder can be referenced with `file:///android_asset/` URL and life is good. The WebView code looks as below.         

```
<WebView source={{ uri: 'file:///android_asset/generic.html' }} />
``` 

Cheers











[1]: https://facebook.github.io/react-native/
[2]: https://facebook.github.io/react-native/docs/webview.html
[3]: https://github.com/facebook/react-native/issues/6004
[4]: https://github.com/facebook/react-native/issues/505














