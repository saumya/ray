---
title: NSNotification in Swift
author: saumya
date: 2016-06-30
template: article.jade
---
While Apple has put a lot of design patterns to develop applications for iOS, the flexibility of an event driven application development surely has its merits. The very de-coupled application is so nice to play around with. Well, the downside is to find where is what. For a strictly coupled application, one can definitely find the root of the roots. But for a de-coupled application its very difficult to find what is happening where. Then comes good practices of code commeting and logger messages to rescue. That topic is a separate post I hope.            


Lets see how in [swift][1] we could write an event driven application.

<span class="more"></span>

Here is a scenario. We have a ViewController1.swift and MyViewController.swift. First `ViewController1` is loaded in the application and then it navigates to `MyViewController`. Upon certain situation in `MyViewController` we want to do something on `ViewController1`. All we have to do is send an event from `MyViewController` to `ViewController1`. The events here in iOS is known as `NSNotification`. So the setup is as shown here.

```swift
// MyViewController.swift
// Dispatch Event from wherever necessary
let notification = NSNotification(name: "myNotification" , object: self, userInfo:nil )
NSNotificationCenter.defaultCenter().postNotification(notification)
```  

Then in the other file just add the listeners to listen to the events and call the methods to handle them.

```swift
// ViewController1.swift
override func viewDidLoad() {
    super.viewDidLoad()
	// Listen for Event
	NSNotificationCenter.defaultCenter().addObserver( self, selector: #selector(onGotNotification),name: "myNotification", object: nil )
}
private func onGotNotification(notification:NSNotification){
	print("name=",notification.name)
    print("object=",notification.object)
    //
    let myViewController:MyViewController = notification.object as! MyViewController
    myViewController.someMethod()
}
```

Happy coding.












[1]: https://developer.apple.com/swift/
[2]: https://www.npmjs.com/














