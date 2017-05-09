---
title: Five OpenFL Extensions for Android
author: saumya
date: 2017-05-09
template: article.jade
---

Native Extensions for [OpenFL][1] are the things which bind [OpenFL][1] applications with the native platform it is running on. There are some extensions provided from [OpenFL][1] itself. If you go to [OpenFL][1] repository on github, you can find for yourself extensions, such as [In-App Purchase][e2] and [Google AdMob][e1].

<span class="more"></span>

Previously it was a lot to do to make an extension for yourself. But as [OpenFL][1] and Android platform matured, the getting started with extensions became easier.      

Here is a [tutorial in detail about the making][t1] of Extensions.


There are 2 steps to it.

 1. create
 ```
 lime create extension MyExtension
 ```

 2. Make it ready to use
 ```
 lime rebuild MyExtension android
 ```
 Or, if you are calling `rebuild` from inside the extension folder
 ```
 lime rebuild . android
 ```

Thats all for an extension to be ready to use in an OpenFL Android Application. 

To use the extension in your [OpenFL][1] project, add this to your `project.xml` as below.
```
<include path="../relative/path/to/MyExtension" />
```
And then, from inside your project, you can call the methods as `MyExtension.myMethod()`.

I have written down some of my own extensions for Android.

 - [AnCam][a1]
 - [RayToast][a2]
 - [AnWebView][a3]
 - [AnAppLaunch][a4]
 - [AnCall][a5]

The [example implementation][ExampleImp] for the extnsions are [present here][ExampleImp].


Happy Coding.










[1]: http://www.openfl.org/
[2]: http://haxe.org/

[e1]: https://github.com/openfl/extension-admob
[e2]: https://github.com/openfl/extension-iap

[t1]: https://player03.com/2014/08/09/openfl-extensions/

[ExampleImp]: https://github.com/saumya/OpenFL-AnExt
[a1]: https://github.com/saumya/AnCam
[a2]: https://github.com/saumya/RayToast
[a3]: https://github.com/saumya/AnWebView
[a4]: https://github.com/saumya/AnAppLaunch
[a5]: https://github.com/saumya/AnCall










