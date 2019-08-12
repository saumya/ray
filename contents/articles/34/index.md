---
title: Understanding BackboneJS View Event, jQuery Event and trigger()
author: saumya
date: 2014-04-18
template: article.pug
---



The fun in working with [BackboneJS][2] is freedom. The library is so decoupled that, one can really do any kind of architecture for an application. This freedom will come in your way if you do not know what is happening behind. We will be focusing on 'Event' here.      
Working with [BackboneJS][2] often involves working with [jQuery][1] too as a DOM manupilation library. When we work on HTML and DOM, in terms of [BackboneJS][2] we are working on View. At this point we must understand, that this BackboneView can dispatch event and the DOM we are dealing with also is capable of dispatching event. The point to note here is event dispatched through [BackboneJS][2] framework, does not bubble. Where as the default DOM events bubble. Well, since we generally work with [jQuery][1] for DOM manupilation, events fired through [jQuery][1] also has the same effect as DOM events, they bubble. Working with a [BackboneJS][2] ViewObject, we deal with `el` of the ViewObject. [BackboneJS][2] also provides a `$el` on each view. Take a note of this `$el`, which is a [jQuery][1] object.      
Dispatching an Event in [BackboneJS][2] is done as
```javascript
//somewhere inside the View
this.trigger('myEvent',{'data':'myValue'});
```
The basic syntax for [dispatching an event in BackboneJS][4] is
```javascript
object.trigger(event, [*args]) 
```
Remember that the `second parameter` in the `trigger` is `data` to be passed to the event-handler. Registering the listener for the event will be as 
```javascript
this.listenTo(this.viewObject, 'myEvent', this.onMyEvent);
```
Now writing a handler for this event will look as
```javascript
//handler
onMyEvent: function(eventdata){
    console.log(eventdata);//example: getting data from the event
}
```
So, we get the whole `data` ( passed to the `trigger()` method as second parameter ) , as the arguement to the handler. 

Now lets focus on the DOM event for the same scenario.
The dispatcher code will look as
```javascript
this.$el.trigger('myEvent',{'data':'myValue'});
```
Here, actually it seems that we are using [BackboneJS][2] Event, but since we are dealing with `$el`, we are actually [triggering a DOM event through jQuery][3]. Since this is a DOM event, it has all the three phases in its life cycle; capture, target and bubble. So, we can really catch this event on a parent view of [BackboneJS][2] and the code would be like 
```javascript
events: {
    'myEvent': 'onMyEvent' //this is actually listening to DOM event
}
```
The handler code will look as 
```javascript
onMyEvent : function(event,data){
    event.preventDefault();
    //code as required by application
    //But, see the second arguement is actually 'data', passed to 'trigger()'
    return false;
}
```
Note the difference in event handler here. We have now two arguements and the second arguement is the `data` that is passed in to `trigger()` call above.
All that is to it is, how you `trigger` the event, from the two ways below.
1. From the [BackboneJS] View
2. From the DOM element     

And then, writing a proper event-handler for the respective Event.     

In [BackboneJS][2], sometimes you need to deal with situations, where you just want to listen for events without knowing the other Views. That way de-coupling the application. There is Mediator design pattern to do a central event dispatching system for the whole [BackboneJS][2] application. Then there is this little but powerful thing, called bubbling, already available to native DOM.      

Here are the links to the two trigger methods;
1. [jQuery trigger][3]
2. [BackboneJS trigger][4]


Happy Bubbling.





[1]: http://jquery.com/
[2]: http://backbonejs.org/
[3]: http://api.jquery.com/trigger/
[4]: http://backbonejs.org/#Events-trigger



