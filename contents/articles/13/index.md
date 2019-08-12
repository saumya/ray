---
title: Author details on Wintersmith
author: saumya
date: 2014-01-22
template: article.pug
---


This is probably exciting and why I moved, to [Wintersmith][1]. Part of the blogging itself, is learning the engine and the [Jade template engine][2].      

Here is a tip to configure the author name.      

With every blog post, there is an author name, below the title, which reads as "written by author". This comes from the blog itself as you probably know already. Thats fine and thats the default behaviour. If one needs to change it and which could be changed, here is the thing.      

The details are populated from the `authors` folder. The `author` name specified in the blog meta data,ie; the top section, when writing the blog, is mapped to a file with the `same name as author`. So the file name is `author.json` in the `authors` folder, where `author` is specified in the blog meta-data. If it finds the file, then the `author name` below the `title` of the post is updated with the new data from the file and an email link is attached with it which is also taken from the `.json` file. This is interesting, if it does not find the file, simply the autor name from the blog meta data, is put out in the blog, without the email link.      

Happy hacking.      


[1]: https://github.com/jnordberg/wintersmith
[2]: http://jade-lang.com/