---
title: BackboneJS, view and its events
author: saumya
date: 2014-01-20
template: article.jade
---


Working in [BackboneJS][1] is fun and easy to begin with. Slowly but steadily it gets complicated as we move on and add more to the project. Being said that, [BackboneJS][1] is not at all opinionated. So there is no rightway of doing something. If your solution works for your project, then its good to go. Well, then there are certain things, which may help you, better organise your code. One of such things is `View Events`.     
In a Backbone view, to listen to events and handle them, the general syntax is as this.
```javascript
events:{
		"click": "onClick"
		},
onClick: function(event){
	//Do something with the event
	//or
	//specifically do it for a target
	var btnID = event.target.id;
	if(btnID==='btn_one'){
		console.log('TODO:');
	}
}
```
Well, it may be easier at first, but we are listening for events for the whole view and then in the handler checking it. There is a way in [BackboneJS][1] that directly and listens for events for that particular target. The code looks as this.
```javascript
events:{
		"click #btn_one": "onClick"
		},
onClick: function(event){
	//btn_one is clicked
	//Do something with the event
}
```
Happy coding.      


[1]: http://backbonejs.org/