---
layout:     post
title:      When Podfile is missing
date:       2016-02-14 08:31:19
summary:    What to do when your podfile is missing, and only have Podfile.lock- recreation of a Podfile from ashes
categories: cocoapod
---
It happened to me somehow, I lost my Podfile. It was missing. Whatever I tried, I couldn't find it anywhere in the computer :(

Some day, I needed to install a new pod. Then, I had two choices, either I would install it manually, or with cocoapods dependency manager. First one could save the day, but it was lack of sustainability. I have no idea with the other, but it would become nice practice.

My plan was to create a new `Podfile`, copy all the dependencies from `Podfile.lock`, install pod. Actually it worked. But somehow new updates broke my app. Navigation controller started to block the content. 

When I googled for `Podfile.lock`, [cocoapods](https://guides.cocoapods.org/using/using-cocoapods.html) was very informative.mfoamfom

<iframe width="420" height="315" src="https://www.youtube.com/watch?v=H-zK1mEwTe0
" frameborder="0" allowfullscreen></iframe>

[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/H-zK1mEwTe0/0.jpg)](http://www.youtube.com/watch?v=H-zK1mEwTe0)


````````````````
