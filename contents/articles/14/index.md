---
title: Phonegap, jQuery, jQueryMobile and AJAX caching
author: saumya
date: 2014-01-23
template: article.jade
---


Developing for a fragmented landscape is not easy. Its even difficult, if you choose to use, a library or framework, which says `develop once and run everywhere` or something like `it makes your application look like native`.    
First thing first. With every new release, we have another step addition to test. Contrary to the belief that, the new Operating System is obviously capable of running the old running application, it adds one more fragment to the already fragmented landscape. So if you are a mobile developer, keep this in mind that `new OS, is a new test step`. Well, lets add one more device to this equation. Lets just focus on `Apple` devices, considering there `so called, minimum number of device types`. An iDevice is suppose to run the latest vesion of the iOS. But in the development environment, you might not able to keep up with new device types or OS updates. And only this can break your application. So make sure, you have `latest device and latest OS`. Ok, then test your application in this device, chances are your application `may run` but chances are `it might not` too. So the point is `search arround` the internet from the beginning itself, if there are known problems with the exact `device and OS` combination.<span class="more">           


Now, just think to add up to more OS, and more devices to the equation. Think of Android and the Windows mobile, you can imagine the complexity.
Ok. Lets add a library to the equation. Now it becomes `device + OS + library` and then different vesions of the library. The new versions of the library should run the old running code, but thats an expectation, not reality. So make sure, you have gone through the combined equation search too.     
`And thats the start`     
Here is `just one of many` examples. [Phonegap(Cordova)][1] and [jQuery][2] together caches the AJAX calls. Now, thats happening in iOS6 for me. But there are evidences that it happens on other  environments too.  
- [stackoverflow][4]
- [sencha][5]
- [ios6-0-caching-ajax-post-requests][6]
- [android issue][7]
- [phonegap forum][8]

It took me sometime to understand, what the problem is?! It was working fine with iOS 4 and 5! Well, here is the tip which solved it. Make the configuraton option of AJAX call in [jQuery][2], so that the AJAX call is not cached (else default is cache).
```javascript
headers : { "cache-control": "no-cache" },
```
The complete AJAX call will look somthing like this.
```javascript
$.ajax({
headers : { "cache-control": "no-cache" },
url : '',
success : function(result) {}
})
```     
Here is a [nice write up about how][6] you configure [jQuery][2] AJAX call, so that they are not cached.     

Keep an eye and check serously for at leat these     
- Operating system update
- Have not tested on this device before 
- use of particualr library and frameworks (and the problem they bring)
- used library does not update to the new OS
- used library does not support this device
It goes on and on. The matter of fact is, you can not ignore testing it in all the devices and OSs.

Happy fixing.      


[1]: http://cordova.com/
[2]: http://jquery.com/
[3]: http://jquerymobile.com/
[4]: http://stackoverflow.com/questions/12506897/is-safari-on-ios-6-caching-ajax-results
[5]: http://www.sencha.com/forum/showthread.php?244076-PhoneGap-and-iOS-6-Ajax-calls-weirdness
[6]: http://www.einternals.com/blog/web-development/ios6-0-caching-ajax-post-requests
[7]: http://www.grobmeier.de/android-does-not-fire-ajax-reqests-because-they-are-caches-ajax-requests-at-least-on-jquery-mobile-10072011.html#.UuE5CBC6bcs
[8]: http://community.phonegap.com/nitobi/topics/avoid_android_application_caching_on_ajax_calls_option_cache_false






