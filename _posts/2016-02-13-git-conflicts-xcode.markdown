---
layout:     post
title:      When Merge Failed on Xcode
date:       2016-02-13 15:31:19
summary:    What to do when you are on a branch, and couln't merge it into your master branch on Xcode
categories: git
---

Recently, I was working on a project alone and create a new branch and kept on going with it. When it was time to upload and send for testing, I needed to merge into the master branch on Xcode. Boom! It didn't work. Because, after merge, head was on the master branch, but it couldn't be built and storyboards implemented on the branch are missing. And I thought I lost all my code base. It was a big relieve to see recent copy of the project in the folder. It was close!

Then I tried to merge on terminal, since Xcode is an IDE, and its integration with git could be problematic. Then, on the branch, `git add`. and `git commit -m "Last commit before merge` commands are applied. Then, I ran `git merge theBranch master` command. Although there were conflicts, it works. However, Xcode took the project as a Mac OS X project :( It couldn't be built and run.

Today, another solution came to my mind. Since I am the only person in the project, I decided to make the current branch as the master branch. I wasn't sure about the possiblity of this, at least, it was worth a shot. 

With the guidance of [@ashfurrow](https://twitter.com/ashfurrow), I have run these commands. The idea was basically, after backing up old master, deleting it, and making a new branch name `master` from 'theBranch'. And it worked :)

{% highlight unix %}
 3840  Feb 13 01:01 PM git add .
 3841  Feb 13 01:01 PM git commit -m "Preparing for merge"
 3842  Feb 13 01:02 PM git status
 3843  Feb 13 01:02 PM git checkout master
 3844  Feb 13 01:02 PM git checkout -b old-master
 3846  Feb 13 01:03 PM git checkout `theBranch`
 3847  Feb 13 01:04 PM git branch -d master
 3848  Feb 13 01:04 PM git checkout -b master
 3849  Feb 13 01:05 PM git log
{% endhighlight %}

