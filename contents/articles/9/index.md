---
title: HTML5, requestAnimationFrame
author: saumya
date: 2014-01-14
template: article.jade
---


Making a javascript application, at somepoint, involves use of `setTimeout` and `setInterval` functions. Well, the possibility increases even more, when one needs to animate elements. So we know what it means to use these two functions.   
Fortunately we have a new method, called `requestAnimationFrame()`, which is elegant and effective. Now animations will not eat up mobile battery life, but still be smooth. This is optimised to takecare of the host environment, such as mobile browser, desktop browser etc. It even minimises the repeat call, if the application using it, is not visible or scrolled out of view, sweet.   
[Check, which browsers and versions support this function,][1] just to make yourself clear.    
Here are few links which explain `requestAnimationFrame` function in more detail.    
- [mozilla][2]
- [Paul Irish][3]
- [Creative JS][4]   

Its kind of `saying bye bye` to `setTimeout` and `setInterval`.    
Happy Animating.





[1]: http://caniuse.com/requestanimationframe
[2]: https://developer.mozilla.org/en/docs/Web/API/window.requestAnimationFrame
[3]: http://www.paulirish.com/2011/requestanimationframe-for-smart-animating/
[4]: http://creativejs.com/resources/requestanimationframe/