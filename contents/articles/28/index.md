---
title: jQuery Mobile, making change page work. 
author: saumya
date: 2014-02-15
template: article.jade
---


The [last post][1] about the [change page][1] API change of [jQuery Mobile][2] tells you as to, how to change a page, in the [new API][3]. I was hoping thats the only change, but there seems, some kind of fix necessary to make a page, change properly. I mean, there is this bug, where the page change actually does this. It goes to the page mentioned by the change page and then it comes back to the page again, from where it was moved. So the effect is, the page is not chaged at all and the user looks at a screen, where the application simply moves to another screen and comesback to the original screen.      
For me the fix that worked is send `changeHash:true` in the options object of the API.     
<script src="https://gist.github.com/saumya/9015917.js"></script>

Happy coding.





[1]: http://saumya.github.io/ray/articles/24/
[2]: http://jquerymobile.com
[3]: http://api.jquerymobile.com/jQuery.mobile.changePage/