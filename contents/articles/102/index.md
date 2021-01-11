---
title: Andriod App Icons and Web apps with Back button.
author: saumya
date: 2021-01-11
template: article.pug
---


Android application development has come a long way since its beginning. There are different ways to do things now and new capabilities are coming in.<span class="more">

![Reflection](../89/saumya_2019_review.jpg)

While talking about the ways it was done, the major thing that changed is the language itself from Java to Kotlin. Then the IDE has moved to IDEA instead of Eclipse. AndroidStudio is matured enough and the process seems a lot easier than dealing with Eclipse. 

We can do much more with much less pain. 


### The App Icon

Creating an icon for the application was a challenge. Not in terms of design. But one had to make it for a lot of sizes and then put it inside the application. 

Now one AppIcon is not a single image! One is for background image and one is for foreground.

That may seem as more trouble, but in reality, AndroidStudio does the job. Jut remember to add the Image asset and choose the default naming convention. The IDE will generate different images and overrides the default one. This is true for both the images for the icon.

### WebApp with Back button

Let's talk about the Web applications inside Android Application. We could do that by pointing a WebView to a URL. While that was true, one had to do a lot of things to make the hardware `Back Button` work as a browser back button for that WebView. It always was a challenge.

Now, this is much more easier. The WebView itself has matured and it has API to do things like that. One has to just set the right parameters to enable history of the WebView and call the history API. If the Web application is done with a UI which matches the Native Android application, it just feels and works as a native application.


Happy Coding.




















