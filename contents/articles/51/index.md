---
title: Making crossplatform CLI application with HAXE
author: saumya
date: 2015-1-19
template: article.jade
---

When I first heard about CLI applications, I thought it might be shipping with the OS itself. Then I found that we can write our own CLI applications. At that point I assume that well, just a CLI application, means it runs everywhere. But actually CLI applications by default are not crossplatform! Yes, I realised it much later. In order to have a crossplatform CLI app, one needs all the required environment to compile to and compile for a particular OS.         

[HAXE][1] comes in handy in this case. One can make a crossplatfom CLI app with just one code base. Ofcourse you need the required environment to compile to that particular environment. There is even a shorter way to this, compile for [NEKO][2] virtual machine. This [NEKO][2] VM ships with [HAXE][1]. Once you compile to [NEKO][2], all you do is package all the [NEKO][2] dependencies and there you have a crossplatform CLI for every OS. Here we will compile to [NEKO][2] and run through [NEKO][2], but just keep in mind that the same code can be compiled to CPP(C++) to produce true native CLI.           
Lets begin with the compiler settings or the build file. The `.hxml` file has the following content.
```haxe
# HAXE build
# Defining the application entry
-main MyCliApp
# NEKO : compilation
-neko bin/myCliApp.n
#
# CPP : compilation
#-cpp bin/cpp/
```          
We are setting up for compiling to [NEKO][2] but then we have the options commented out for compiling to CPP. If we want to compile for the C++ target, then comment out the [NEKO][2] target and enable the CPP(C++) target. Well, this compilation will create a file named `myCliApp.n` inside the 'bin' folder. To run the file, we have to navigate to the 'bin' folder and run with [NEKO][2] as below.  
```haxe
neko ./myCliApp.n
```          
Thats about compilation and running. Lets get back to coding. There is no surprise here as all we have to do is, get the right package and class from [HAXE][1] and use it. Here is the [Git repo][3] for this example. The application entry initialises 'PrintInfo' Class. That class prints the information that we want to show to the user and finally asks the name of the use. As user inputs the name, it greets the user and moves to our defined command prompt. We have setup some commands to display. Depending upon user input the necessary commands are executed. All these are happening in `MyCli.hx`  Class. The [code is commented][4] for easy reference in [this repo][3]. Here is the [direct link][4] to the class. 
         




Happy coding.












[1]: http://haxe.org/
[2]: http://nekovm.org
[3]: https://github.com/saumya/HAXE-CLI-101
[4]: https://github.com/saumya/HAXE-CLI-101/blob/master/com/saumya/cli/MyCli.hx

