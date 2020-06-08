---
title: Database and doing things without the 'for' Loop
author: saumya
date: 2020-06-08
template: article.pug
---


This is valid for all the languages and database engines.
The thing is to create / read / update / delete somethings in database. So it is about multiple actions in a table inserts / reads / updates / deletes. The quick and easy solution is to put the actions in a 'for loop' and then try to solve the problems created by the loop itself! There are better ways. 

<span class="more">

This is problem is generic. However I will be talking about [Node.js][node], [Express][express] and [Sequelize][sequelize]. 

### Recursion / Make your own loop

I was developing an API where a call with an array of ids is expecting an array of objects. All that is needed is get the individual 'id' from the array and then process the database to find information about the 'id' and store it in another array. Finally return the resulting array. As I told you, in this case 'for loop' will create more problems than solving one. Whatever language you work with, in this case avoid 'for loop'.

The best way is to create your own loop and deal with the loop manually with events.

First make a `counter`, access the 'id' from the loop. Move to database, do your data manipulatioin, listen for the events and get the data from it. Then move to the next by increasing the counter.

Here is the code for it.

``` 
router.get('/getAllDoctorsByGroup/:groupId', (request,response) => {

	const onCallbackFromDB = function(dbResult){
		// Call the API to get the Doctors from the IDs we got in 'dbResult'
		var aDoctors = [];
		var ai = 0;
		var onGotDoctorFromDB = function(result_doctor){
			aDoctors.push(result_doctor);
			ai++;
			getNextDoctor();
		}
		var getNextDoctor = function(){
			if(ai<dbResult.length){
				modelFactory.getDoctorWithId(onGotDoctorFromDB, dbResult[ai] );	
			}else{
				response.send(aDoctors);
			}
		}
		// initiate the loop
		getNextDoctor();
	}
	// first call to get the array of ids
	modelFactory.getAllDoctorIdsByGroupId( onCallbackFromDB, request.params.groupId );
});
```

This is basically the API GET call 'getAllDoctorsByGroup' and passed in a 'groupId'. I have a table here with mapping for GroupId and DoctorId. So the first callback returns an array of 'ids' for the doctors. I have another table here with 'doctorId' and all the details for that 'id'. So initiating a loop with a call to the next table for getting data for one particular 'id' and once got the callback, the counter 'ai' is incremented and then moved to the same call for the next 'id'. Finally we got an array of all the 'details' for the 'doctors'.

This is straight forward and elegant. You could do the error checking and other things in the recursion and the flow is under your control. Rather than fixing the errors created by the 'for loop' and 'synchronous' methods.



Happy Coding.


























[sequelize]: https://sequelize.org/
[node]: https://nodejs.org/en/about/
[express]: http://expressjs.com/







