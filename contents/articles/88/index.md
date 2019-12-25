---
title: Node, MongoDB and Express.
author: saumya
date: 2019-12-25
template: article.pug
---

Working with databases from [Node][4] is easy. But then working with a support from ORM/ODM makes it more interesting. [Last time][s1] we saw `how we can work with SQL servers?`, this post is about NoSQL servers, specifically [MongoDB][8]. There is a nice ODM for [MongoDB][8] known as [mongoose][9]. 

This [mongoose][9] makes the database calls as simple as it could be. The concepts here are 
 
 - Define a schema
 - Get the Model from the Schema
 - Do the database operations on the Model


The [sample project is here][p-mongo] in `Github`.

The first call to [mongoose][9] is a connection to [MongoDB][8].

```
var mongoose = require('mongoose');
mongoose.connect( mongoURL , {useUnifiedTopology: true,useNewUrlParser: true},function(error){
		if(error){
			throw error
		}
		console.log('Connection : SUCCESS : ');
		
		// Go ahead with Database modifications
		//
	});
```

There are two ways to call `connect` function. The way it is shown above will give `error` object if there is an error in connection. One has to check for the availability of this object and do things accordingly. If not present, then we have a successful connection. Once that is done, one can call the CRUD methods of the model for modifying the database.


A model file(example: `dog.model.js`) will look as below.

```
const mongoose = require('mongoose');
const DogSchema = mongoose.Schema({
	name: String,
	description: String
});
const DogModel = mongoose.model('MyDog', DogSchema);
module.exports = DogModel;
```

This is how to get the model and from there on, you can use the [mongoose][9] API to modify the database through the model Object.


Happy Coding.












[1]: https://github.com/mysqljs/mysql#install
[2]: https://github.com/sidorares/node-mysql2#installation
[3]: https://sequelize.org/
[4]: https://nodejs.org/en/
[5]: https://expressjs.com/
[6]: https://bulma.io/
[7]: https://jquery.com/
[8]: https://www.mongodb.com/
[9]: https://mongoosejs.com/

[p-fe]: https://github.com/saumya/attendance_ui
[p-be]: https://github.com/saumya/NodeOrmApi_102
[p-mongo]: https://github.com/saumya/NodeOrmApi_103

[s1]: https://saumya.github.io/ray/articles/87/






