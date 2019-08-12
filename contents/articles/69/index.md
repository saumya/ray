---
title: Realm in Swift
author: saumya
date: 2016-07-08
template: article.pug
---
Working on a local storage for persistence in data has a lot of solutions. While we can definitely go ahead and just store `String` values and play with it, Apple provides some solutions to play with local data as if its a database. The thing is, its not that intuitive. Other solutions are there, but the simplicity of [Realm.io][3] is nice and addictive.            

Lets see how in [swift][1] we could play with [Realm][3].

<span class="more"></span>


```swift
do {

	// clear the whole DB if Realm throws Errors saying need to migrate
	Realm.Configuration.defaultConfiguration.deleteRealmIfMigrationNeeded = true
	// initiate DB and keep a ref
	self.realm = try Realm()

	// query to get all models of a Particular type
	let pModel = self.realm!.objects(MyModel.self)

	// check for already saved data
	if(pModel.count == 0){
	    print("=== No Saved Data Found === XXX ")

	    // initiate a Model
	    let appInfo:MyModel = MyModel()

	    //write a model to DB
	    try! self.realm?.write({
	        self.realm!.add(appInfo)
	    })

	}else{
	    print("=== Saved Data Found ===")
	    // get the first model 
	    let appInfo:MyModel = pModel.first!
	}

} catch let error as NSError {
    print("init : Realm : ERROR :")
    print(error)
}
```  

For writing into the database   

```swift
public func saveUserId(userId:String,AndPhone:String){
    
    // get the realm reference we saved above and start interacting with it
    
    do{

        self.realm?.beginWrite()
        
        self.pivdModel!.registeredUserId = userId
        self.pivdModel!.registeredMobileNumber = AndPhone
        
        try self.realm?.commitWrite()

    }catch let error as NSError{
        print(error)
    }
     
}
```

Happy coding.












[1]: https://developer.apple.com/swift/
[2]: https://www.npmjs.com/
[3]: https://realm.io/














