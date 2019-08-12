---
title: Slim Framework and Composer Autoload
author: saumya
date: 2019-01-29
template: article.pug
---

Like most of the PHP frameworks, [Slim framework][slim] uses [Composer][3] for developer experience. [Composer][3] does a lot of things which manually one has to do before. This post is specifically with regard to [Slim framework][slim]. However, this can also be refered to, for other frameworks which use [Composer][3].

<span class="more">

There is a specific configuration in `composer.json` which deals with autoloading of the classes. Its not necessary to do autoloading, one can do it manually as always.

```
require '../src/controllers/AppController.php';
```
This way, one has to do it all the time for each individual classes. The autoloading of classes does this automatically depending upon the settings and some conventions. Depending upon the folder structure and the namespaces, the setting could just be as below.

```
{
    "require": {
        "slim/slim": "^3.12"
    },
	"autoload": {
		"psr-4": { "rain\\" : ["src/"] }
	}
}
``` 

Here we are talking about `psr-4` standards. There are different standards in `psr` and they may have somethings in common. However there are differences between them also. So just keep this in mind we are talking about `psr-4` standards here.

```
"autoload": {
		"psr-4": { "rain\\" : ["src/"] }
	}
```

Well, now let's look at the standards of `psr-4` and how it finds the files.

 - [Composer][3] will load the files relative to `composer.json` file. In the setting above, it will load from the folder `src` which is at the same level as `composer.json`
 - The first setting `rain` in the `autoload` configuration is the namespace of the PHP Classes
 - PHP class `file name` and the `class name` should be exactly the same (except the `.php` extension)
 - PHP class file location and its namespace should exactly the same
 - PHP class namespace should be exactly the same as specified in the `autoload` configuration

A PHP class file for the above settings would look like below.

```
//location: src/configs/AppConfig.php

namespace rain\configs;

class AppConfig
{
	function getConfig()
	{
		return 'AppConfig';
	}
}
```

Once one is careful enough to map the `folder structure` and `namespace` the composer autoload functionality will load the classes. Here is a [nice explanation][ref1] of the concepts.

### After adding the **autoload field** in `composer.json`, one **has to** re-run `dump-autoload` to re-generate the vendor/autoload.php file.

This should takecare of autoloading of the class files. The `dump-autoload` is a critical step while updating the `composer.json`.

For windows

```
php composer.phar dump-autoload
```

For Unix, Linux and macOS

```
php composer dump-autoload
```
    
Happy coding.




[details]: long_story.html

[cake]: https://cakephp.org/
[slim]: https://www.slimframework.com/
[3]: https://getcomposer.org/

[ref1]: https://myshittycode.com/2018/03/14/slim-class-x-not-found/


