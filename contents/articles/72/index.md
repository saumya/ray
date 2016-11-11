---
title: React Native on Android, changing app name, package name and version code
author: saumya
date: 2016-11-11
template: article.jade
---

There are things one may need to change in the release build for Android. 
Things like `App Name` are a case here. Suppose you start developing by initialising to a generic `App Name` and at the time of release one need to change to the actual `App Name`. Same goes for `package name`, which is visible in `Google Play Store` and as well in the `App details` of the Android phone. 
<span class="more"></span>



### App Name

Lets start with `App Name`. This is the name thats visible in users screen. To change this name, you have to change it in `strings.xml`.

Full path is 

```
android/app/src/main/res/values/strings.xml
```          

and the entry is 
```
<string name="app_name">My Android App</string>
```



### Package name

This is shown in the `Play Store` and the details in `About App` of your Android device. This should say something like `com.myapp` or `com.company.appname` or something similar. 

To change this, you have to edit four files. 

 - android/app/src/main/java/com/reactNativeSampleApp/MainActivity.java
 - android/app/src/main/java/com/reactNativeSampleApp/MainApplication.java
 - android/app/src/main/AndroidManifest.xml ( optional as per my experience )
 - android/app/build.gradle

The first two Java files have the package name as something like below.
```
package com.ReactNativeApp;
```

Change it to your desired package name.
```
package com.myComp.MyApp;
```

At this point it should be required to make the physical changes to the Java files in the proper package. But somehow it does not work! Rather it breaks the build. Just keep in mind, that we have changed the `package` names and that should reflect in the actual package. Incase the builds break, you know where to find.

### Version Code

This is a number which Google Playstore recognises and does not allow to upload another APK having the same value. Just think of this as build number. The same build can not be uploaded twice. So the point is everytime, you make a build or release-apk, you must have a different number or more specifically incremental number. If your first version of the application has a version code of 5, then the second version must have a version code which is more than 5. 

Along with version code, you might need to update the `version name` also. Which is the version number of your application and visible in Google Play Store. 

While `version code` is used by `Play Store` to manage your APK, `version name` is used by `Play Store` to notify user that an update to your app is available.

To change these two values, you need to edit 
 
 - android/app/build.gradle
 - android/app/src/main/AndroidManifest.xml ( optional as per my experience )

These settings are taken from `build.gradle` while making a build with `gradle` but for the purpose of sanity, its better to change in both of the files above. 

[Here is a reference change][2].

### Making the release build

Finally making a release build is done from inside the `android` folder of the `React Native` application. The commands are as below.


```
./gradlew clean
./gradlew assembleRelease
```



Cheers











[1]: https://facebook.github.io/react-native/
[2]: https://github.com/saumya/aRnDot36One/commit/7c1855bc1e5eee29294278e5a849ef9693730902
[3]: https://github.com/saumya/aRnDot36One/blob/7f52ce50368aaa2f2207f2dc70c72b90d584a0d7/android/app/src/main/res/values/strings.xml














