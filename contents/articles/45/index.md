---
title: CoffeeScript basics
author: saumya
date: 2015-1-1
template: article.jade
---

Just to set the expectations right, we need to know something before we begin here.         

When I first heard about `Class` in `Javascript` it created curiosity on me and the expectation increased as to work like a `Classical` language(Where Classes are the root of everything) instead of `Prototypical` language(like Javascript). But then slowly I understood that its not `Javascript` but other languages on top of Javascript which create somekind of `Class` concept to mimic `Classical` languages. The point is everything boils down to `Javascript` if a language is written to compile or transpile to `Javascript` . Well, that may seem like a spoiler right now, but its actually not as we will see. Just keep these things in mind all the time, even if we are doing [CoffeeScript][1].        

Here is the direct link to the [Github][2] repository for the code reference to this post.       

- CoffeeScript is generally written in a `.coffee` file
- Each `.coffee` file is compiled to a `.js` file
- Each space (a blank space) in code has a meaning in the `.coffee` file
- Semicolons are optional and generally avoided
- In the beginning you may write more than one classes in a single `.coffee` file, and thats perfectly alright here
- By default the [CoffeeScript][1] Classes you write are private            

When compiled to JS, the contents of each file, are put inside a self invoking function. This is intentional to not pollute the Global variables. So if the content has some classes inside them, then those classes will also be inside the self-invoking function, restricting the access from outside.                  
The classes in [CoffeeScript][1] are compiled to as usual JS functions and the inheritence is done through the prototypical inheritence concepts of Javascript. Since all this happens behind the scenes and as a [CoffeeScript][1] developer if you do not know, how its working, it would be a pain later to expect anything else from this language.          


Thats all to start with the new year. Happy new year.         


Happy Coding.












[1]: http://coffeescript.org/#top
[2]: https://github.com/saumya/CoffeeScript101




