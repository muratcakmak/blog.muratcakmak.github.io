---
layout:     post
title:      When Podfile is missing
date:       2016-02-14 08:31:19
summary:    What to do when your podfile is missing, and only have Podfile.lock- recreation of a Podfile from ashes
categories: cocoapod
---
It happened to me somehow, I lost my Podfile. It was missing. Whatever I tried, I couldn't find it anywhere in the computer :(

<iframe src="//giphy.com/embed/Z1qmSgenLVrwc" width="480" height="269" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="http://giphy.com/gifs/dude-publishing-enlightened-Z1qmSgenLVrwc"></a></p>

Some day, I needed to install a new pod. Then, I had two choices, either I would install it manually, or with cocoapods dependency manager. First one could save the day, but it was lack of sustainability. I have no idea with the other, but it would become nice practice.

My plan was to create a new `Podfile`, copy all the dependencies from `Podfile.lock`, install pod. Actually it worked. But somehow new updates broke my app. Navigation controller started to block the content.

When I googled for `Podfile.lock`, [cocoapods](https://guides.cocoapods.org/using/using-cocoapods.html) was very informative. Actually, it is for protecting project from changes in the dependency, one can think it as a snapshot of your existing project, and it is super helpful.

Then on iOS Side Projects group, Cathy Chen cleared my mind with this explanation:

when you see this on your `Podfile.lock`
{% highlight text %}
DEPENDENCIES:
  - AFNetworking (~> 2.0)
{% endhighlight %}

corresponding podfile looks like this:

{% highlight text %}
  - pod 'AFNetworking', '~> 2.0'
{% endhighlight %}

Then I copied all my dependencies with keeping their version, and made the changes. Installing, and starting again were straighforward then :)

Bonus:
If you have time, I suggest you not to miss the video about `Podfile.lock`

<iframe width="560" height="315" src="https://www.youtube.com/embed/H-zK1mEwTe0" frameborder="0" allowfullscreen >Great Explanation</iframe>
