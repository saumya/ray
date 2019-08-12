---
title: Maintaining a React Native application on iOS.
author: saumya
date: 2017-03-23
template: article.pug
---

 That may sound just an easy job. Surprisingly its not! Its because [React Native][1]is evolving at a very high speed. The community is vibrant and [React][2] itself is also moving at a very high speed. Though there are minimal API changes but there are changes and sometimes there are breaking changes. Well as for iOS, we know it also comes with API changes and sometimes breaking changes. 

<span class="more"></span>

 The absolute minimum one has to do, to maintain a [React Native][1] project on iOS is to check for all the tool chain is upto date. Being said that, there are dependent libraries and there are chances that these things may not sync and your project may break.

 As of today [React Native][1] is 0.42 and to compile an iOS project, it seems the bare minimum is 
  - [Watchman][4]
  - [Brew][5] 
  - Update the `react-native-cli`


The code reference to update the `react-native-cli` would be just to re-install it.

```
sudo npm install -g react-native-cli
```

To know the version of both, its as simple as this.

```
react-native --version
```

Hopefully that opens up the idea as to maintaining a project is also a time consuming process. And with projects which evolve, if one has develop its own project, then the time and effort to maintain it will be exponential.

Happy Coding.











[1]: https://facebook.github.io/react-native/
[2]: https://facebook.github.io/react/
[3]: https://saumya.github.io
[4]: https://facebook.github.io/watchman/
[5]: https://brew.sh/












