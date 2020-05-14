---
title: Sequelize UPDATE call
author: saumya
date: 2020-05-14
template: article.pug
---


Working with [Sequelize ORM][sequelize] is just sweet. It makes working with RDBMS as if one is working in NoSQL. And the APIs are simple and on the spot. It just works. While making an API for the CRUD operations the work just gets faster and cleaner.<span class="more"> 

[Sequelize ORM][sequelize] provides two APIs for an UPDATE call to a Model. One is a *Static* method and the other one is an *Instance* method.


### Static method on the Model

This is called in the Model itself and not on the instance of the Model. Suppose we want to update one `PersonModel`, we can directly call `update` on Model.

```
PersonModel.update({
		name: person_name ,
		phone: person_phone ,
		email: person_email,
		address: person_address
	},{ where:{ id : person_id } })
	.then((result)=>{
		console.log('Number of rows updated=', result[0]); 
		})
	.catch((error)=>{});
```

### Instance method on the Model Instance (Object)

There may be a reason to call `UPDATE` on an instance of the MODEL. This is done by first getting the instance from database and then calling `UPDATE` on it.

```
PersonModel.findOne({ where:{id : person_id} })
.then((personInstanceFromDB)=>{
		personInstanceFromDB.update({
				name: person_name ,
				phone: person_phone ,
				email: person_email,
				address: person_address
			})
		.then((result)=>{
			console.log('The new Model Object=', result.toJSON());
			})
		.catch((error2)=>{});
	})
.catch((error1)=>{});
```

That is simple, is not it? As you can see the `static` method call on the Model is a little less code. However the `return` of the calls are different. The `static` method is returning the `number of rows` that has been updated, however the instance method returns `the whole object` itself.



Happy Coding.

























[react]: https://reactjs.org/
[sequelize]: https://sequelize.org/







