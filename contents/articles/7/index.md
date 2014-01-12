---
title: Wintersmith configuration
author: saumya
date: 2014-01-12
template: article.jade
---


[Wintersmith][1] is perfect on creating a static site, but the problem arises when one needs to configure it to meet a particular need. I think, thats true for any framework.   
The problem I encountered is, putting the static blog in any domain or sub-domain. [Wintersmith][1] generates urls which are default to root `/` and to change it to any domain means one has to change it to the domain one wishes to put the site on. Thats as simple as that. Well, for most parts. Then, there are places where it creates a relative URL.    

To solve this, I looked inside the templates and configuration. [Wintersmith][1] reads from the `config.json` file to get the base URL and make the other URLs. So I changed the `url` to my desired URL and added another parameter to the `locals` object of the `config.json` named `folder`, Then changed the URL in templates, from `/` to `locals.url` and at some places to `locals.url+'/'+locals.folder` and thats it. Its now perfectly alright to take my site to wherever I want. All I need to do is change these variables and build the site again with [Wintersmith][1] build command.    
Is this the rightway? Well, seriously I do not know, but it works.   

Happy Hacking ! 



[1]: https://github.com/jnordberg/wintersmith