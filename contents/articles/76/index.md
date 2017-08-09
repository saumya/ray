---
title: Slim with Composer
author: saumya
date: 2017-08-09
template: article.jade
---

One of the nice frameworks of [PHP][php] is [Slim][slim]. Now its on its version 3. I started using it since version 1. And must admit that there are a lot of changes since its version 1. 

<span class="more"></span>

At the same time, [PHP][php] also has seen a lot of changes. One of the interesting thing that happened is package manager. There are a few options here but [Composer][composer] is probably oldest one here. It says "Dependency Manager for PHP" for itself. Well, whatever one calls it, the thing is it downloads the required packages (and its dependencies) for us. The installation also has two options, either install it locally in a folder (project folder) or could be installed globally in one machine. The difference is how you fire up the command `composer`. If its globally installed, one has to say `composer` but if its locally installed, then it would be called with `php composer`. The `php` executable must call the locally installed `composer`. 

Now to install a package, one has to run the command

```
composer require slim/slim "^3.0"
```

Alternatively one can write all the dependencies in `composer.json` file.

```
{
    "require": {
        "slim/slim": "^3.0"
    }
}
```

And then run the command

```
composer install
```

Now, everything that is listed in the `composer.json` file will be downloaded inside a folder named `vendor`. 

From there on, its all your code, the [reference app][app] is here.

Happy Coding.










[php]: https://secure.php.net/
[slim]: https://github.com/slimphp
[composer]: https://getcomposer.org/
[app]: https://github.com/saumya/Slim3Basics










