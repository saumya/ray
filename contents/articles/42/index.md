---
title: Dojo Toolkit, Widget.
author: saumya
date: 2014-09-30
template: article.pug
---

[Dojo Toolkit][1] has a component library named as `Dijit`. Each component in this library is known as a `Widget`. It is better to know the `dijit` framework vocabulary before going further inside it. 

- Normally each `.js` file represents a `Class`.
- Each file, whose name starts with `_` (underscore) is `not a concrete` class. That means, this class is supposed to be extended to be used, `never directly used` as is.
- Members inside a class, properties and methods, whose name starts with `_` (underscore) are `private`
- A class is defined by `declare()` 

[Dojo][1] now supports AMD modules. So the module definition is pretty straight forward as in standard module definition. If you have ever used any other framework such as [BackboneJS][2], you already know, how to declare, extend, load and use a module and a class. 

Now, lets see what `Widget` brings to the rules table. Each Widget has a life-cycle of its own. The lifecycle methods are as below in sequence.

- constructor()
- postMixInProperties()
- buildRendering()
- setters and getters, example is set("myProperty",value)
- postCreate()
- startup()
- destroy()

There are few methods which also be called in some widgets, such as
- resize()

Each `Widget` is supposed to `Extend` the `_WidgetBase` class defined in `dijit/_WidgetBase` package. Sometimes, it is necessary to use template strings or templates inside a  Widget. In that case, the `Widget` extends `_WidgetBase` and `_TemplatedMixin`, defined in `dijit/_WidgetBase` and `dijit/_TemplatedMixin` package respectively.

After creation of each child `Widget` inside the parent Widget, its necessary to call the `startup()` method of the child Widget. Since `startup()` call goes through all the child widgets of a container Widget, its better to add all the child Widgets to the parent Widget and call parent's `startup()`, which will call `startup()` of each child Widget.
While writing a custom Widget, its necessary to override parent's lifecycle methods. At the sametime, it is necessary to continue the lifecycle of the Widget. So a call to parent's method is necessary. In most of all programming languages it is done with a `super()` call. In `dijit` framework its called as

- this.inherited(arguments);

So inside each of the above life-cycle methods, a call to `this.inherited(arguments);` is necessary, either in the beginning or as the last line of the method.

A custom `Widget` has either of the 2 properties below or sometimes both, to add child widgets to  itself.
- this.domNode
- this.containerNode

Now to add child widgets to the parent widget there are methods like
- addChild()


Well, this post may seem a lot but the idea is to make you aware of the vocabulary and some background to `dijit` infrastructure. For a basic and complete `example` [have a look at this widget][3].




Happy Coding.












[1]: http://dojotoolkit.org/
[2]: http://backbonejs.org/
[3]: https://github.com/saumya/dojo101/blob/master/dojo-release-1.10.0-src/myWidgets/rayWidget3.js


