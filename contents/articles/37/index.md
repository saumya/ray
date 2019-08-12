---
title: Upgrading to Ruby 2.x from 1.x with rvm, on an upgrade from old OSX to Mavericks.
author: saumya
date: 2014-05-26
template: article.pug
---



This is a situation when you have updated the OS from a previous version of Mac OSX to the latest version of the OSX Mavericks. Generally OSX ships with a version of [Ruby][1], which is latest by the time the OS is released. But when it comes to OSX upgrade and in this case particularly to OSX Mavericks, the operating system upgrade does not bring in the [Ruby][1] upgrade. Rather, the old [Ruby][1] lives on the new OSX. Well, if you have a decent understanding of managing [Ruby][1] versions, you may be using one of the version management systems of [Ruby][1]. I used to have [rvm][2]. Now I have an upgraded OSX but need to have the latest version of [Ruby][1]. The steps are as below     
1. Upgrade [rvm][2]
2. Upgrade [Ruby][1]

Well, there are issues with these two steps as I found throughout the net. A simple search in the internet will make you aware of this fact. So the refined steps are as below.
1. Install XCode Commandline tools
2. Reinstall [rvm][2]
3. Upgrade [Ruby][1]

In my case, I do not have to install the XCode commandline tools, probably because I am an iOS developer and always updates to the latest version of XCode along with the commandline tools. The thing to note here is with the OSX upgrade, the commandline tools of XCode is removed by the system. Even if, one installs the new `XCode`, the `commandline tools` are not included by default. All one has to do is `install` it (`again`).     
Moving on, the next step is to upgrade the [rvm][2]. With the OSX upgrade, the normal [rvm][2] update does not work.

```
rvm get stable
```
So, the fix is to `install rvm` (you can call it `again`) as below.

```
\curl -sSL https://get.rvm.io | bash -s stable
```
Once this step is done everything else is just normal [Ruby][1] update thing. Update [Ruby][1] with the commad as below.

```
rvm install ruby-2.1.1
```
Now lets install a gem such as json, which can be done with the command as follows. I was suggesting ~~sudo gem install json~~, but never do that. Instead use

```
gem install json
```
It seems using `sudo` `is not advisable` to be used while using [rvm][2]. I got a reply in twitter for this blog post, from [@rvm_io][3] as 
> looks good, the only hint - never use sudo with RVM, sudo "disables" RVM controlled ruby, the gem most likely is installed in system    

Thats all to it. The important thing is, if we try to install the 2.x version of [Ruby][1] with old [rvm][2], it will not work. Actually, it does not show even in the known list of [Ruby][1].

Happy upgrading.







[1]: https://www.ruby-lang.org/en/
[2]: http://rvm.io/
[3]: https://twitter.com/rvm_io


