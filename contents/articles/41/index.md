---
title: Getting started with, Dojo Toolkit
author: saumya
date: 2014-09-29
template: article.pug
---

To begin with, [Dojo Toolkit][1] or simply referred to as [Dojo][1] is one of many libraries in javascript. First thing to do is, like any other javascript libraries, make sure which version of library you are studying and using. [Dojo][1] has gone through major upgrades and if you are trying to do things the new way of [Dojo][1] then better get to know the [new version][2]. We will be focusing on the new version only(currently `1.10`) and referring to old one, wherever necessary.

[Dojo Toolkit][1] has got a combination following
- A bare bone of functionality ( `dojo` )
- A widget library ( `dijit` )
- An experimental library ( `dojox` )
- An Unit testing framework
- A compiler to do the minification and optimisation

A lot of javascript libraries try to implement the classical programming concepts and [Dojo][1] is another one of them. So, if you are a purist in Javascript, [Dojo][1] will dissapoint you. The functional nature of Javascript is also eliminated here. [Dojo][1] clearly disagrees to say that `function` is `a first class citizen`, which is again denying another nice feature of javascript. Well, but if you are coming from a classical programming background, that means from a programming language which is class based like Java, then [Dojo][1] will seem natural. So, we will refer them in classical terms rather than Javascript terms.

The core functionality of the toolkit is wrapped in a package called `dojo`. Everythig that runs in the toolkit depends on this basic package. Next is `dijit`, which can be called as a component library or in dojo's terms these are widgets. Now `dojox` is a package containing experimental widgets, which will eventually go into `dijit` , once they are stable enough. Since widgets have to live a life of their own, there is a flow of lifecycle events. It is now obvious that any application using these widgets have to abide to these lifecycle events and some rules as a whole. In Dojo's terms these are framework rules.


Happy Coding.












[1]: http://dojotoolkit.org/
[2]: http://dojotoolkit.org/documentation/tutorials/1.10/modern_dojo/