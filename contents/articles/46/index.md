---
title: Cake and Coffee
author: saumya
date: 2015-1-1
template: article.pug
---

While working with [CoffeeScript][1], we generally tend to do the following,
- write something in a .coffee file
- compile that file with coffee compiler to .js file         

Well, if we are a little smarter, then use the following command to compile all the .coffee files in a particular folder to respective .js file in another folder.

```coffeescript
coffee --compile --output outputFolder/ inputFolder/
```         

That may seem enough now, but actually there are a lot of things we could automate. The native way to do this in [CoffeeScript][1] is called `Cake`. We can look at it as a build system. Nice thing about this is, we can write every instruction in [CoffeeScript][1] itself.         

- Cake is an utility comes with [CoffeeScript][1]
- its a task runner or build system
- all the instructions are saved in a file with name `Cakefile`
- `Cakefile` is the file name and there is no extension to it
- Everything inside the `Cakefile` is a [CoffeeScript][1] expression         

To run the `Cake` task runner, navigate to the folder, where our `Cakefile` is residing and fire up the command as below.        

```coffeescript
cake
```        

That will display all the tasks available in that file to be run. To run a specific task, run

```coffeescript
cake taskName
```        

While defining tasks, we can make a relation between tasks. That means we can say taskOne is dependent on taskTwo. The [basics of CoffeeScript project][2] has a Cakefile for reference.        

The direct link to the sample `Cakefile` [is here][3]. All the code are commented for easy reference.       






Happy Coding.












[1]: http://coffeescript.org/#top
[2]: https://github.com/saumya/CoffeeScript101
[3]: https://github.com/saumya/CoffeeScript101/blob/master/Cakefile
[4]: http://coffeescript.org/#cake




