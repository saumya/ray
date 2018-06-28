---
title: Firebase Cloud FireStore and checking existance of a Document
author: saumya
date: 2018-06-28
template: article.jade
---

The thing is [Cloud FireStore][1] is still in beta. However, I find it quite stable to run my applications. It has got all the things to run a serverless application.

While this is a NoSQL database, there are `Documents` and `Collections`. I was suppose to check the existence of a `Document` before adding some values into it. There is an API which gives us exactly the same thing, [exists][2].

```
docSnapshot.exists
```

The trick here is, if there is no `Document` creation involved before but still there are data inside that `Document` path (its possible) then the `exists` will always return `false`. To know whether the `Document` is actually created or not Firebase `Console` is a good help. In the `Console` the `Documents` which are not created will be shown as *italics*. Its a subtle but very informative visual separation.

Just make sure, you created your `Document` before checking it with `exists`.

Here is [stackoverflow answer][so1], which helped me in this regard.




Happy Coding.












[1]: https://firebase.google.com/products/firestore/
[2]: https://firebase.google.com/docs/reference/js/firebase.firestore.DocumentSnapshot#~exists

[so1]: https://stackoverflow.com/questions/48068581/firebase-doc-exists-but-doc-exists-returns-false?answertab=active#tab-top









