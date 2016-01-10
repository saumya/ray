---
title: Cordova today
author: saumya
date: 2016-01-09
template: article.jade
---



During these years [Cordova][1] and the mobile phones have come a long way. Today it seems the mobiles are more powerful and can handle a web application quite nicely. On the other hand [Cordova][1] tool chain also has matured. Comparing to older versions of the tool chain, currently its purely [NPM][2] based, as long as we talk about cross platform development. So anything one needs is just a `npm install` away. 

<span class="more"></span>

There are two ways, as usual with [Cordova][1], to make a project.
 - CLI based
 - Platform based

> The difference is in, what an application needs from, the platform its deployed into. 


> > If one application does not depend upon things like Camera or Geolocation etc and can still serve itself, then its best to use CLI based approach. That way, it can be delivered to a lot of platforms with just few commands.   


> > On the otherhand, if an application requires a specific feature from the underlying platform, then its better to get started with the platform specific workflow. If its needed to write some custom hooks to only iOS devices, then its much easier to get started in platform specific development and customise the application for iOS platform.    


### Platform projects ###

For platform specific development, there are separate compressed files available and the projects start from there. Here is a list for iOS and Android.

 - iOS ( [https://github.com/apache/cordova-ios/releases][3] )
 - Android ( [https://github.com/apache/cordova-android/releases][4] )

### CLI projects ###

For CLI based applications, the basic need is [Node][5] and with that comes [NPM][2]. First thing to do is, intall Cordova from [NPM][2], once [Node][5] is installed in the system. From that point onwards the commands to start working on a Cordova project are as below.          


Make a cordova project
```
cordova create hello com.example.hello HelloWorld
```
Now move to the project folder, which is just created by the above command. All the `following commands` should `run` from inside the `project folder`.
```
cd hello
```
Check the number of platforms
```
cordova platforms ls
```
Add the required platforms
```
cordova platform add ios
cordova platform add android
cordova platform add browser
```
Remove platforms
```
cordova platform remove blackberry10
```
Build
```
cordova build ios ( this is equivalent as the below two commands combined together )

cordova prepare ios ( at this point, Xcode can be used to open the project )
cordova compile ios
```
Run
```
cordova emulate android ( run in emulator )
cordova run android ( run in device )
```
Help
```
cordova run --help
```

### Plugins command reference ###

List all the plugins installed in the project
```
cordova plugin ls
```

Add plugin
```
cordova plugin add cordova-plugin-console
```
Remove plugin
```
cordova plugin rm cordova-plugin-console
```
I hope that helps you get started with [Cordova][1]. For detailed documenation, its better to go to the official documentation. 



Happy coding.


[1]: https://cordova.apache.org/
[2]: https://www.npmjs.com/
[3]: https://github.com/apache/cordova-ios/releases
[4]: https://github.com/apache/cordova-android/releases
[5]: https://nodejs.org/en/
















