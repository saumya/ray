---
title: Making a RESTful API with NodeJS and Express
author: saumya
date: 2014-05-21
template: article.pug
---



Here we will be making a basic REST API using the [Express][2] framework for [NodeJS][1]. I am not going in detail of how [Express][2] works, but straight to the code, which is as below. While this may look as a regular [Express][2] application, the important thing is the API can be called from any web server.      
<script src="https://gist.github.com/saumya/402d2f035b23d7d08877.js"></script>
While developing APIs, the first thing came to me is, how to call this from another server?! For thats the only reason we are exposing the API. And the answer is enable [CORS][3], cross-origin resource sharing. It simply means, make the API available or expose to these servers. we can specify the domain names individually or in this partcular case, we have exposed the API to any sever by specifying * .       

```javascript
app.all('*', function(req, res, next) {
  res.header("Access-Control-Allow-Origin", "*");
  res.header("Access-Control-Allow-Headers", "X-Requested-With");
  next();
 });
```
This means, upon any API call, add these headers first. And the header says, its allowed from any `*` domain. So the result is, before the API call hits any route, it first comes into this `all` binding and sets the values and then goes to the respective route.


Happy Noding.







[1]: http://nodejs.org/
[2]: http://expressjs.com/
[3]: http://enable-cors.org/