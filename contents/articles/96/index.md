---
title: CORS for multiple Domains in Node and Express
author: saumya
date: 2020-07-12
template: article.pug
---


Cross-Origin Resource Sharing ([CORS][cors]) is a way / specification / standard, whatever you call it. It allows to use resources from one server in another server. Well simply said it enables to call, APIs on one server, from another server.

<span class="more"></span>

> [Enable-CORS][ecors] is a nice place to get information about the subject.

While working in [Node][node] and [Express][express] it is easy to enable this with a middleware. However, we can do it without them also.

Write a middleware function to enable CORS.

```
app.use(function (req, res, next) {
  res.setHeader('Access-Control-Allow-Origin', 'http://localhost:3001'); 
  res.setHeader('Access-Control-Allow-Methods', 'GET, POST, OPTIONS, PUT, PATCH, DELETE');
  res.setHeader('Access-Control-Allow-Headers', 'X-Requested-With,content-type, Accept');
  res.setHeader('Access-Control-Allow-Credentials', true);
  next();
})
```

This is very much a case where, API servers were running somewhere and give special permission to use their services to particular domains(example- localhost:3001). 


What if our API is going to be used by many endpoints. Hoe to enable them. Will the simplest is to use a `*` instead of a particular domain. That will allow any server to access the service. While it is open to all, it could be abused by anybody.

```
res.setHeader('Access-Control-Allow-Origin', '*'); 
```

To enable the service for only few domains, use an array of domains.

```
app.use(function (req, res, next) {

  var allowedDomains = ['http://localhost:3001','http://localhost:8080' ];
  var origin = req.headers.origin;
  if(allowedDomains.indexOf(origin) > -1){
    res.setHeader('Access-Control-Allow-Origin', origin);
  }

  res.setHeader('Access-Control-Allow-Methods', 'GET, POST, OPTIONS, PUT, PATCH, DELETE');
  res.setHeader('Access-Control-Allow-Headers', 'X-Requested-With,content-type, Accept');
  res.setHeader('Access-Control-Allow-Credentials', true);

  next();
})
```




Happy coding.


























[node]: https://nodejs.org/en/
[express]: http://expressjs.com/
[ecors]: https://enable-cors.org/
[cors]: https://en.wikipedia.org/wiki/Cross-origin_resource_sharing







