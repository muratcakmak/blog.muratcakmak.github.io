---
layout:     post
title:      Swift Scripting
date:       2016-04-30 08:31:19
summary:    Why don't you give a try to run Swifty scripts in terminal!
categories: swift
---

After I have seen the video of Ayaka’s [talk](https://realm.io/news/swift-scripting/) on Swift Summit London, as an old-school command line person, I couldn’t myself diving into the experiment with Swift scripting. It is both fun and educational.

I am writing this post for the newcomers to the command line. My plan is to enrich command line posts by time.

Let’s start with the basics. Please, apply the instructions with me. Open a blank text file which folder you want, save it as “hello-world.swift” and add interpreter directive to the top of the file. You are feel free to copy the next line:
{% highlight text %}
#!/usr/bin/env xcrun swift
{% endhighlight %}
It says I am a swift script in a way that interpreter can understand.

Then write our traditional Hello, World! statement in Swift.
{% highlight swift %}
print(“Hello, World!”)
{% endhighlight %}
You can whatever swift code you want to write.

In order to run this script, open terminal and navigate through the folder that you store. If you are unfamiliar with terminal, just use cd(change directory) command and go to the folder as you do with user interface.
As an example,
{% highlight shell %}
cd Desktop/Folder
{% endhighlight %}

We need to have required permission to execute the file. 
{% highlight shell %}
chmod +x hello-world.swift
{% endhighlight %}


The fun part is here. To run the script, run this command on terminal
{% highlight shell %}
./hello-world.swift
{% endhighlight %}

Here you go! If you follow the instructions in verbatim, you should see “Hello, World!” on the command line. 

One giant leap for me, one small step for mankind.
	
<iframe src="//giphy.com/embed/dE3dOmeBubbPi" width="480" height="354" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="http://giphy.com/gifs/nasa-apollo-11-apollo45-dE3dOmeBubbPi"></a></p>

Happy coding!
