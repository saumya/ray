---
title: Amazon S3 Sync with NodeJS
author: saumya
date: 2014-02-14
template: article.pug
---


This is my first practical cross-platform desktop application written in [NodeJS][1]. The application is a simple desktop client to upload the changed files in a folder automatically to a bucket in [Amazon S3][2]. The main components, which make this application, are     
 - [node-webkit][3]
 - [Amazon S3 SDK for browser][4]

Well, there is a [NodeJS][1] module as well for the SDK, but I prefer to take it only browser way at the moment.     

The [source code][5] is available here and to run it, get a copy of the [node-webkit][3] for your environment. And that makes a cross-platform application on [NodeJS][1].     

Currently the application keeps an eye on a folder, you specify. Once a file is changed in that folder, is automatically uploaded to the 'bucket' you specify in the beginning of the application. Note, currently it just uploads the files, which are changed. It does not upload a new file in the folder or any existing file.


Happy synching.





[1]: http://nodejs.org/
[2]: http://aws.amazon.com/s3/
[3]: https://github.com/rogerwang/node-webkit
[4]: http://docs.aws.amazon.com/AWSJavaScriptSDK/guide/browser-intro.html
[5]: https://github.com/saumya/AmazonS3Sync