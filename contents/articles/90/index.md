---
title: Let's JAMstack.
author: saumya
date: 2020-01-30
template: article.pug
---


First project of 2020. A conversion of a portal from LAMP (Linux-Apache-MySQL-PHP) stack to [JAM stack][jamstack-1].

I have been doing static site development for a long time (this blog itself is an example), however the complexities of the project was a little more complex than this blog. <span class="more"> 

The project was not very complex in terms of the content and application. The only trick is to get the content from database to the Markdown and deploy it to the server. Once this is done, the whole project is just about moving the deployment from a full stack web server to a static site web server. 

The code is committed to a [GIT repository][git-1]. Next is to configure a [Continous Integration][ci-1] engine for [Continuous Deployment][cd-1]. Once this is done, all that is left is commit my content and code to the repository.

The frontend is developed with [React JS][react] and built with [serverless architecture][serverless]. The blog engine is done with [Hugo][hugo] and [Markdown][md]. Made the APIs with [Express][express] and datastorage is done with a cloud storage service. The authentication is done with one from the many authentication services available to use. And we have a running JAMStack application.

There could be serverless functions used, however for the time being it is not. I am happy to see that I could do it. The whole process took me arround 45 days.



Happy JAMStack-ing. 


















[jamstack-1]: https://jamstack.org/
[git-1]: https://git-scm.com/
[md-1]: https://www.markdownguide.org/

[ci-1]: https://en.wikipedia.org/wiki/Continuous_integration
[cd-1]: https://en.wikipedia.org/wiki/Continuous_delivery

[react]: https://reactjs.org/

[serverless]: https://en.wikipedia.org/wiki/Serverless_computing

[hugo]: https://gohugo.io/
[md]: https://www.markdownguide.org/

[express]: https://expressjs.com/







