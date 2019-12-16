---
title: Node, SQL and ORM.
author: saumya
date: 2019-12-16
template: article.pug
---

Finished a project having database, [Node][4] and web UI. While connecting the database from `Node` server is easy, there are as usual a lot of options here. First I used [mysql][1] but soon after realised there is an updated package to it called [mysql2][2]. So I have shifted to [mysql2][2]. Once its installed, it is straight forward to connect to any database. The docs are very helpful to get going.

Once database connection is done and one get used to the workflow, the need for an `ORM` arises. There are many options for this in `Node` land. After looking into different options, I started using [Sequelize][3]. It is as nice as `Node` itself and the docs of this library is very helpful and welcoming.

These two things makes life a lot easier, while working with database from a [Node][4] server. Next comes the time to write APIs for the frontend. I used [Express][5] to get things done for the APIs. There is one thing to keep in mind while working with JSON for the APIs in [Express][5]. The thing is one has to initialise [Express][5] application like below.

```
	const express = require('express');
	const app = express();
	const port = 3000;
	app.use(express.json());
	app.use(express.urlencoded({ extended: false }));
```

Once this is done, we are ready to take/give JSON from/to UI. If you are trying to host it on Heroku, then the following line is important.

```
 app.listen( process.env.PORT || port , () => console.log(`My App listening!`) );
```

This is required because, Heroku does not listen on port 3000 as we are trying to make it. But Heroku port is available for us at `process.env.PORT`. So we are using it here.

Next is making the APIs CORS enabled. Which is done as below.

```
	app.use(function (req, res, next) {
	    res.setHeader('Access-Control-Allow-Origin', 'http://localhost:1234');
	    res.setHeader('Access-Control-Allow-Methods', 'GET, POST, OPTIONS, PUT, PATCH, DELETE');
	    res.setHeader('Access-Control-Allow-Headers', 'X-Requested-With,content-type, Accept');
	    res.setHeader('Access-Control-Allow-Credentials', true);
	    next();
	});
```

Now we are ready to write the APIs. 

### Front End

The frontend I have done, is using [bulma][6] for CSS and [jQuery][7] for DOM manipulation. Well yes, I hava avoided all the frameworks and new toys of today. And still could do the project and finish it. I have iterated it a lot and it is all fun to see how time could be saved even if one does not use a framework! 

Here are the code repositories to have a look for frontend and backend.  

 - [Frontend][p-fe]
 - [Backend][p-be]



It is a very nice experience to see Javascript in all sides and almost no framework on frontend and still having a decent project running.












[1]: https://github.com/mysqljs/mysql#install
[2]: https://github.com/sidorares/node-mysql2#installation
[3]: https://sequelize.org/
[4]: https://nodejs.org/en/
[5]: https://expressjs.com/
[6]: https://bulma.io/
[7]: https://jquery.com/

[p-fe]: https://github.com/saumya/attendance_ui
[p-be]: https://github.com/saumya/NodeOrmApi_102





