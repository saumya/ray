---
title: HAXE JS 101
author: saumya
date: 2015-1-5
template: article.jade
---

Hope you know what is [HAXE][1], take a moment to go through the official [HAXE][1] documentation. We will discuss how and what to consider while working with JS in [HAXE][1].          
Generally other languages, which compile to JS, actually compile each specific file to a respective JS file. [HAXE][1] actually compiles to one single JS file for our application. We can further take the generated JS file and minify it using popular JS minifiers.        

The work flow for [HAXE][1] to JS is as simple as         
- Writing the normal [HAXE][1] application
- Use the package structure and class as usual
- Make a .hxml file difining what would be the final JS file
- Compile with [HAXE][1] compiler to produce the JS file         

```haxe
haxe compile.hxml
```         
The `.hxml` file looks something like
```haxe
-main ApplicationEntry
-js app.js
```        

Thats all to it. [HAXE][1] will take care of the `import` and `package` and `class` of the application. Finally the generted JS file is having everything our application needs. Include the JS file in the required HTML file and we are done.      

Here is a [sample basic application][2] showing all there is to it.


Happy Coding.












[1]: http://haxe.org/
[2]: https://github.com/saumya/HAXE-JS101



