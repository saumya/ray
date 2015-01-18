---
title: HAXE and NodeJS
author: saumya
date: 2015-1-18
template: article.jade
---

Continuing the sudy of javascript target of [HAXE][1] we will focus on [NodeJS][2] this time. Before we move on, lets remind ourselves the things to expect from the [HAXE][1] toolchain by going through the previous two introductions, here is the [first][3] and the [second][4] post.          
Thats about [HAXE][1], now a little about [NodeJS][2]. In [NodeJS][2] the concept of modules is very common to make some re-usable code. In general, modules hide everything by default. In class based languages we can call them as `private` elements. To make something `public` , we have to use `exports` keyword in [NodeJS][2].           

For example, if we have a file names `one.js` as
```javascript
exports.publicFunction = function() {
  console.log('Hello World');
}
```          
Now, in [NodeJS][2], we can write something as          
```javascript
var oneObj = require('./one');
oneObj.publicFunction();
```          
Thats first kind of modules we have. There is another kind of modules in [NodeJS][2], where instead of exposing each individual elements from the modules, it exposes a `Constructor` function. This is done with `module.exports` in stead of only `exports`.          
```javascript
module.exports.MyObjConstructor = function() {
  console.log('New Object');
}
```          
This second one is looked at as classical concepts of programming, where each JS file is kind of a Class file.          
The dynamic and fun nature of javascript allows us to use the first way of exposing individual elements to actually expose a constructor function too. Is not it ?! Why we think about that! Because [HAXE][1] generated javascript is actually doing that. Smart.   
<span class="more"></span>       
Now, lets focus back in [HAXE][1] and here is the companion [Github project][5]. We have three classes in `.hx` as Animal, Jungle and Tree. But only Animal class is exposed by using `@:expose` just before the class declaration as           
```haxe      
@:expose("Animal")
class Animal 
```         
The application entry class `ApplicationEntry.hx` is actually using all these classes. Finally, we have the `.hxml` file, we name it `compile.hxml`, but could be given any name, to compile our application. Here is the code for quick reference.          
```haxe
# Generates one single application JS
-main ApplicationEntry
-js bin/hxApp.js
#
--next
# Generates JS file for individual hx files
-js bin/Tree.js 
-cp src 
com.jungle.Tree
--next
-js bin/Animal.js 
-cp src 
com.jungle.Animal
--next
-js bin/Jungle.js 
-cp src 
com.jungle.Jungle
#
```         
Once we run the [HAXE][1] compiler with
```haxe
haxe compile.hxml
```         
It generates a file with the name `hxApp.js`, which is enough for the [NodeJS][2] experiements. But we have the other generted JS files just to see, what actually [HAXE][1] is outputting. If you look at the `Animal.js` its actually getting exported as `exports.Animal` and thats exactly what we need to use as a [NodeJS][2] module.      
Lets write a simple [NodeJS][2] application. Get into our `bin` folder, where all the [HAXE][1] compiled JS files are. There we create a node application as `nodeApp.js` and the content of the file is 
```javascript
var app = require('./hxApp.js');
console.log(app);
```          
Now to run the [NodeJS][2] application, do this in commandline
```javascript
node nodeApp.js
```          
You can see now all the logs in the commadline, which is actually being run from the application we generated from [HAXE][1]. This is `the way` [HAXE][1] can be `used best`. Do all the code in [HAXE][1] and finally output to a single application javascript file. Then use the application file to launch the application.         
Now, lets see what else we can do with the generated code. If you remember we have exposed the 'Animal' class with `@:expose`. Lets modify our 'nodeApp.js' as
```javascript
var app = require('./hxApp.js');
var animal_1 = new app.Animal('CAT',9);
console.log(animal_1);
```         
Now run the [NodeJS][2] application with the same command as `node nodeApp.js`, this time if you look at the application log on the command promt, its actually created a new 'Animal'. The fun has just begun, I hope. Well, we can go on modifying our code to look it more beautiful. 
```javascript
var app = require('./hxApp.js');
var animal_1 = new app.Animal('CAT',9);
console.log(animal_1);
var Animal = app.Animal; // Store the Constructor
var animal_2 = new Animal('Tiger',6); // And use it
console.log(animal_2);
```         
We have a goodlooking constructor for 'Animal' in the name of 'Animal' now.

Thats all is happening from the only one generated Javascript file that is the final application javascript file. Lets see, what else we can do! If you remember we have actually generated all the resepective javascript files for individual `.hx` files. This time, lets forget our final or application javascript file. Lets modify our [NodeJS][2] application file by removing everything else from it and adding the following code.
```javascript
var o = require('./Animal');
var c = new o.Animal('Cat',4); // Directly using constructor
var Animal = o.Animal;//storing the constructor
var a2 = new Animal('Tiger',8);//using constructor
console.log(c);
console.log(a2);
```         
Now run the [NodeJS][2] application from command line as before. Sweat! That works too!         

Well, we now are ready for primetime [NodeJS][2] application using [HAXE][1] toolchain. The reference application and haxe code is at [this repo on Github][5].       

To summerise all this, we can create a final javascript output and use it to launch our [NodeJS][2] application. We can also just compile each [HAXE][1] file to respective javascript file and use that as a module for our application.         




Happy coding.












[1]: http://haxe.org/
[2]: http://nodejs.org/
[3]: http://saumya.github.io/ray/articles/47/
[4]: http://saumya.github.io/ray/articles/48/
[5]: https://github.com/saumya/HAXENode

