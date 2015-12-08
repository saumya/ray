---
title: What is Socket.IO ?
author: saumya
date: 2015-12-08
template: article.jade
---

Once one starts working on [NodeJS][1], very soon will come across a term called [Socket.IO][2]. It may feel as if just another [NodeJS][1] module available through [NPM][3]. Then it may feel like just another way to write a Javascript application for the browser. Then it may seem something else.          

So lets know what is it?          

 - Its two things, a server framework and client framework.
 - Its a [NodeJS][1] module ( install it from a [NPM][3] ) 
 - Its a client library ( .js file )
          
Now, lets understand a little more in detail.          

[Socket.IO][2] is built to take advantage of [WebSockets][4] for a two way communication between server and client.

Server Framework          

When you work on [NodeJS][1] to implement a socket server, [Socket.IO][2] makes your life easier by providing a [NodeJS module][5]. That means, without [Socket.IO][2] [server module][5] also, you can write a socket server with only [NodeJS][1]. That also means, you have to write and test your own socket server using [NodeJS][1]. This is possible with [NodeJS][1] provided built in modules but only take time and effort. In that sense we can say [Socket.IO][2] is a `server framework` for [NodeJS][1] to write socket servers.          

Client Framework

Now to write a client (basically a web application) we can incorporate [WebSockets][4] API. Well, its possible in the same manner that we can write a Socket server by our own using [NodeJS][1] as explained above. But then [Socket.IO][2] provides us a '.js' file with exposed APIs to use, which is cross-platform. That means [Socket.IO][2] gives a `frontend framework` too, to write our frontend Javascript applications.          







Happy Noding.














[1]: https://nodejs.org/
[2]: http://socket.io
[3]: https://www.npmjs.com
[4]: https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API
[5]: https://www.npmjs.com/package/socket.io

