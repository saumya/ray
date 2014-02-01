---
title: BackboneJS, making an event-dispatching Object.
author: saumya
date: 2014-02-01
template: article.jade
---


Making Views, Collections and Models in [BackboneJS][1] is as simple as extending the raw [BackboneJS][1] objects.
```javascript
var MyView = Backbone.View.extend({});
```
Making a generic object and make it dispatch events is also kind of same, but then the syntax is a little different.
```javascript
var myUtilLib = _.extend({},Backbone.Events);
```
Everything else remains the same, but then, this little syntax change for an event dispatching object may come in your way, if you are new to [BackboneJS][1].     
Here is a detailed example of an utility class for [BackboneJS][1].

<script src="https://gist.github.com/saumya/8755642.js"></script>


Happy coding.



[1]: http://backbonejs.org/





