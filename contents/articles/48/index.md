---
title: HAXE JS 102
author: saumya
date: 2015-1-12
template: article.jade
---

We are going good with [HAXE][1], take a moment to go through the official [HAXE][1] documentation.           
This is a follow-up post to the [Haxe JS 101][3]. Its all about setting up the expectations from the language and the tool chain. Lets make some more things clear about the tooling and how the language works.          
 - [HAXE][1] will produce one single JS file
 - We can force it to create one JS file for one .hx file
 - The created JS file, is by no means is a module JS file as in CommonJS or AMD          

The contents of `.hxml` or the build file generally looks as        

```haxe
-main ApplicationEntry
-js app.js
```         
While forcing each `.hx` file for an individual `.js` file, the build file would contain something as         

```haxe
-js com/jungle/Tree.js 
-cp src 
com.jungle.Tree
--next
-js com/jungle/Animal.js 
-cp src 
com.jungle.Animal
```          
For a sample project and the options, have a look at [this repo][2] and the [sample .hxml][4] file is here with all the possible options for `.js` output.          

The important thing is to remember that finally every JS project is compiled to a single JS file and [HAXE][1] does it in one go. It does not provide module export or any fancy things that other JS frameworks do to support JS look like a classical programming language. [HAXE][1] works with its own tool chain and provides well made JS output. Do not fight it to mock JS libraries, [HAXE][1] is more powerful than that. Even for NodeJS output, [HAXE][1] produces the final JS output, just a single `.js` file. Work with [HAXE][1] packages and classes and then compile it to make the final output, no nothing in between.


Happy Haxing.












[1]: http://haxe.org/
[2]: https://github.com/saumya/HAXE-JS101
[3]: http://saumya.github.io/ray/articles/47/
[4]: https://github.com/saumya/HAXE-JS101/blob/master/compile.hxml



