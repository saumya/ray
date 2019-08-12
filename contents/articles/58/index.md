---
title: How to React now.
author: saumya
date: 2015-11-28
template: article.pug
---
Here is the way to [React][1] now.        

 - Download [React][1]
 - Make a new html file
 - Include "react.js", this gives us 'React' Object
 - Include "react-dom.js", this gives us 'ReactDOM' Object
 - Write the a React component and use it. This is explained below.


The HTML file should look something as shown here.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>React!</title>
  </head>
  <body>
    <div id="myReactApp">
      <!-- React Application -->
    </div>
    <!-- React library -->
    <script src="js/lib/react/react.js" charset="utf-8"></script>
    <script src="js/lib/react/react-dom.js" charset="utf-8"></script>
    <!-- Application Code -->
    <script type="text/javascript">
    	// TODO
    </script>
  </body>
</html>
```

This HTML file has only a `div` with an id as `id="myReactApp"`. Now lets write a React Component. The component code is as below.

```javascript
var Component1 = React.createClass({
  render: function(){
    var reactComponent = React.DOM.span(null,"I am a Custom Span.");
    return reactComponent;
  }
});
```

Now lets add this component to our DOM. We are going to add this component in the `div` with id `myReactApp`.           
```javascript
ReactDOM.render( React.createElement(Component1), document.getElementById("myReactApp") );
```

So the final HTML file with the added javascripts and our code will look as below.
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>React!</title>
  </head>
  <body>
    <div id="myReactApp">
      <!-- React Application -->
    </div>
    <!-- React library -->
    <script src="js/lib/react/react.js" charset="utf-8"></script>
    <script src="js/lib/react/react-dom.js" charset="utf-8"></script>
    <!-- Application Code -->
    <script type="text/javascript">
		var Component1 = React.createClass({
								render: function(){
									var reactComponent = React.DOM.span(null,"I am a REACT Component Span");
									return reactComponent;
								}
							});
    	ReactDOM.render( React.createElement(Component1), document.getElementById("myReactApp") );
    </script>
  </body>
</html>
```          

Now, if you run this from a server and view the page in the browser. You can see our compent is rendered in the `div` and it displays the text as 'I am a REACT Component Span'.          

Thats all is there to [React][1]. After this point all that `remains` is the `APIs for Component` development. But as you can see, [React][1] is not telling or expecting anything else. It just makes reusable HTML components. The architecture of the application is upon the developers.




Happy Reacting.














[1]: http://facebook.github.io/react/
