---
title: Native Android development and getting Key Hash for FaceBook
author: saumya
date: 2014-01-13
template: article.jade
---


If you are developing for native Android, and creating a Facebook login, then the fist thing which will come to you, is a setting on Facebook console called "Key Hashes".

<span class="more">

While trying to do the Facebook suggested way, I lost some time and could not really get it working perfectly. Searching the internet told me that people had been in that path and that the solution is not working. Well, then I got a script to get the hash key. Finally this worked for me, all the time. So quickly I wrapped it in a function and put it here for anyone trying to fight the "key hash".    

<script src="https://gist.github.com/saumya/8399013.js"></script>    

Now, all that remains is, put this function on the first activity of your Android project and call the function with your package name as a string arguement on the onCreation method. That will print out the hash key on logCat window. Just copy-paste that code in Facebook console. Then you can remove that call to the function.    

Happy Hacking ! 


