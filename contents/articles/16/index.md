---
title: Getting started with Wintersmith themes
author: saumya
date: 2014-01-25
template: article.pug
---

I am getting more and more conversant with the [Jade][1] templating engine and [Wintersmith][2]. Which I hope, is, what was one of the intentions, of moving from [Wordpress][3] to [Wintersmith][2]. Well, trying my hands on to customise the theme, I found its extemely easy to just add another CSS to the `layout` template ie; `layout.jade` and start putting in the styles there. It can not be simpler than this. The base style is taken from the style definition at `main.css`. If you look at the `layout.jade`, it will look something as this.
```javascript
link(rel='stylesheet', href='/css/main.css')
```
If you are following this blog, I have mentioned previously how to configure [Wintersmith][2] so as to make it working from any domain or subdomain. So the `layout.jade` in my case, looks as below.
```javascript
link(rel='stylesheet', href=locals.url+'/css/main.css')
```
Whatever the condition may be, whether you are using default settings or my settings, the point is, just add another CSS file(`theme.css`) below the default CSS.
So the default setting will be as this.
```javascript
link(rel='stylesheet', href='/css/main.css')
link(rel='stylesheet', href='/css/theme.css')
```
In my case, I am using a theme CSS file as `saumya.css` and with my configuration change, it looks as this.
```javascript
link(rel='stylesheet', href=locals.url+'/css/main.css')
link(rel='stylesheet', href=locals.url+'/css/saumya.css')
```
Now do the customisation in the `theme.css`.     

Hope you understand `the best practice of overriding styles` than manipulating directly the original CSS file.

Happy theming.



[1]: http://jade-lang.com
[2]: https://github.com/jnordberg/wintersmith
[3]: http://wordpress.org






