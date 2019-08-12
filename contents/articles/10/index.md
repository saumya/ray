---
title: Distribute iOS app on your web site
author: saumya
date: 2014-01-15
template: article.pug
---


Its not that difficult as it sounds.   
First of all, there are distribution services out there. I am not going to name them here, but they are available. A simple web search will show you that. 
Now, the question is, how do they do it, or the more significant question is, can we do it ourselves. The answer is yes.
There are 3 basic things required for distribution.
- .ipa file ( iOS app )
- .plist file ( manifest file for the app )
- .html file ( html file for showing the link to the user )


The iOS app must be compiled with the Ad-HOC distribution certificate with the device(where the app will be installed) UDIDs included. Thats the same procedure, as one would follow, while distributing through other stores. Once its compiled, you say `Archive for distribution` in XCode, which will create the `.ipa` file. The manifest file defines the application meta data, if you go through the manifest file below, there is a place to point to the `.ipa` file, make sure, you provide `full URL to .ipa` file. The download link on HTML file will point to this manifest file. Here is the boilerplate for a typical manifest file (which is a .plist file). The HTML file, is simply  having a link pointing to the `.plist` file.     
<script src="https://gist.github.com/saumya/8440357.js"></script>     
Now simply link to the plist file in the HTML file as below.
```
 <a href="itms-services://?action=download-manifest&url=https://myServer/iOS-dist/iOSAppDist.plist" class="button">Install My App</a>
```
Now visit the URL through iPhone, where your HTML file is stored. Once you click the link, it will download and install the iOS app.

Happy hacking.