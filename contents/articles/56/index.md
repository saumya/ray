---
title: AngularJS, BackboneJS, similarities and differences.
author: saumya
date: 2015-11-26
template: article.jade
---
When learning a new framework or library, its very difficult to look at the same problem from a different perspective. But when you hear a lot like 'ohh, that library is similar to this', then the tendency comes to compare it. And when you see similar terminology in both the frameworks, then you are absolutely sure that both are doing the same thing in the same way. I think, thats the main problem here with learning the frameworks like [AngularJS][1] and [BackboneJS][2]. Both of these have their own share of `how to` and `where to`, overall they seem completely different, even though the terminolgies seem completely same.         

One such thing is `Module`. Both these frameworks define `Module` and use it. Both of them tell to use `Module` to separate concerns. But then both of them seem completely different while implementing the `Module`. Umm, Why?!          

The `difference` is in the `Module` definition of both the frameworks. And that pushes back someone very new to the frameworks, thinking something wrong either in the frameworks or in the understanding of them. While the truth is something simpler than that.            

[AngularJS][1] uses [CommonJS][3] module declaration.          
[BackboneJS][2] uses [AMD][4] module declaration.          

Once you know this difference, things get a lot easier to understand and will take lesser time than before to get upto speed in either of these. Have a look at the [Module Definition][5] documentation, it explains the difference of the module definitions. The bottom line is Javascript eco-system gives us `two` different kind of `Module` systems. Frameworks use one over the other depending upon their opinion. For example [NodeJS][7] uses [CommonJS][3] approach, while [DOJO toolkit][6] uses [AMD][4] way.          

Now lets understand why this difference matters us as a developer. In [CommonJS][3] style declaration, each file is supposed to be a module which is same as [AMD][4] way too. The [CommonJS][3] module can expose as many Objects as one wants, to the application level. So that once one [CommonJS][3] module is included, the application has access to all the exposed Objects in that module. For that matter you can understand, why just adding a `some-ng-file.js` and including that `ModuleName` in the dependency of an [AngularJS][1] application, gives a lot of `ngObject` to play with. Where in [AMD][4] each module is exposing just one Object. If you want to play with the internals of that Object, you have to call that Object's properties and methods. This way makes you feel like as if you are working in a Classical (Class based) language rather than Prototypical language. [BackboneJS][2] is doing exactly the same thing. Once you have got a [BackboneJS][2] module Object, you deal with it as if you are dealing with an Object from a Class. You invoke methods and properties of that Object.           

So one `Module` in [AngularJS][1] is exposing a lot to play with and one `Module` in [BackboneJS][2] gives you just one Object to play with. The similarity goes to other frameworks and libraries as I mentioned earlier about [DOJO Toolkit][6] and [NodeJS][7].


Happy coding with modules.













[1]: https://angularjs.org/
[2]: http://backbonejs.org/
[3]: http://requirejs.org/docs/whyamd.html#commonjs
[4]: http://requirejs.org/docs/whyamd.html#amd
[5]: http://requirejs.org/docs/whyamd.html#definition
[6]: http://dojotoolkit.org/
[7]: https://nodejs.org/en/

