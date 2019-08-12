---
title: iOS, customising top and bottom bar inside UINavigationController
author: saumya
date: 2014-02-13
template: article.pug
---


This may seem a difficult or simple task, depending upon what and how you want to do it.     
[UINavigationController][1] is simply a controller to manage all the UIViewControllers inside it. Now, customising each and every [UIViewController][2] could be done by code or InterfaceBuilder, depending upon what you want to achieve. We will be seeing here, as to how, to customise the Navigation bar (top bar) and the Tab bar (bottom bar) of the respective [UIViewController][2].     
These are the references to look for while customising [UIViewController][2] through InterfaceBuilder.     
Hide the Tab bar (bottom bar)     
<iframe src="http://www.flickr.com/photos/saumyaray/12479138795/player/" width="408" height="477" frameborder="0" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>     
The above setting is on the same [UIViewController][2].         
To display custom text on the back button in a UIViewController, look for the setting as below     
<iframe src="http://www.flickr.com/photos/saumyaray/12476698994/player/" width="500" height="408" frameborder="0" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>     
Just remember that the above setting is done on the `previous` [UIViewController][2] for the next [UIViewController][2], `its tricky` that way.     
Now the code reference for [UIViewController][2] is as below.          
<script src="https://gist.github.com/saumya/8969920.js"></script>     



Happy customising.





[1]: https://developer.apple.com/library/ios/documentation/uikit/reference/UINavigationController_Class/Reference/Reference.html
[2]: https://developer.apple.com/library/ios/documentation/uikit/reference/UIViewController_Class/Reference/Reference.html#//apple_ref/doc/c_ref/UIViewController