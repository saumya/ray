---
title: Go Modules.
author: saumya
date: 2021-01-14
template: article.pug
---


Writing [Go][go] Modules is as simple as writing code in a file inside a folder. The folder is known as the `module`.<span class="more">


 - A module is a folder
 
 - There could be more than one `.go` files in the module with module declaration at top `package gomodule`
 
 - Any function from any of the `.go` file inside a module can be called from any other file in the same module.
 
 - File names does not matter inside a module as far as importing a module is concerned.
 
 - While importing a module, the whole of the module is imported. That means all the `.go` files in that module is available, to call their `functions` from. The functions are called with the module name, not the file name.
 
 - While declaring a module the `.mod` file holds the key. It declares the URL and module name as `module saumya.learning/gomodule`.  The respective `.go` files in that module, must declare the package declaration as `package gomodule` and the URL must be a live URL.



Example of a `module` declaration in a `.mod` file
 
```
module saumya.learning/gomodule
```

The `.go` files in that module must declare the package declaration as below.

```
package gomodule
```

Just remember that these declarations are must be the first line in the respective files.

> The URL in the module declaration `saumya.learning/gomodule` must be a valid URL. Because while importing the module in another module, the [Go][go] is going to import the module from that URL. In this example, the URL is `saumya.learning` which must exist in the internet.

Well, there is a way to work with local modules. That is, importing modules from local file system. It has to be specifically declared in the `.mod` file as below.

```
replace saumya.learning/gomodule => ../2_ago
```

In this example, it is importing a `Go Module` from a folder, relative to our working folder.


### The `mod` Command

Creation of a `Go module` is done with `mod` command.

```
go mod init saumya.learning/hello

```

Here it is creating a `.mod` file with module declaration as `module saumya.learning/hello`.








Happy [Go][go]ing.












[mg]: https://github.com/saumya/Minstagram

[go]: https://golang.org/
[py]: https://www.python.org/
[de]: https://deno.land/
[ru]: https://www.rust-lang.org/
[kt]: https://kotlinlang.org/
[php]: https://www.php.net/









