---
layout:     post
title:      One Step Further; Swift Alternatives for Cpp-style for-in loop
date:       2016-04-11
summary:    Apple remove C-style for-loop, why don't we also remove Cpp-style for-in loop?
categories: functional
---

As all knows, Apple decided to remove C-style for-loop from Swift. Most important reasons are it is too old and not intuitive for the new programmers. 

Since the programming languages is progressing, there is no explanation for not exploiting functional programming stuff in Swift. Instead of using Cpp-style for-in loop, we can do for-loop more Swifty, functional and better.


{% highlight swift %}
var str = "Hello, playground"

//Converting a string into an array
var arr = Array(str.characters)
{% endhighlight %}

I have written all code in playground. And I have also used their example.

{% highlight swift %}
//Looping n times
(0..<10).forEach({num in print(num)})

//old version 
for var i = 0, i < 10; i += 1{
	print(i)
}
/*
It prints from 0 to 10 exclusively to the console
*/
{% endhighlight %}
Isn't is more intuitive!


{% highlight swift %}
//Looping n time reverse
(0..<10).reverse().forEach({number in print(number)})

(0..<10).reverse().forEach({print($0)})

//old version 
for var i = 10, i > 0; i -= 1{
	print(i)
}
/*
It prints from 10 to 0 exclusively to the console
*/
{% endhighlight %}

{% highlight swift %}
//Looping with stride
(0.stride(to: 10, by: 2)).forEach({print($0, terminator: " ")})
/*
0 2 4 6 8
*/
{% endhighlight %}

{% highlight swift %}
//Looping through array values
//I want to print them in one line
arr.forEach({char in print(char, terminator: " ")})
/*
H e l l o ,   p l a y g r o u n d 
*/
{% endhighlight %}

{% highlight swift %}
//Reverse looing through array values
arr.reverse().forEach({char in print(char, terminator: " ")})
/*
d n u o r g y a l p   , o l l e H 
*/
{% endhighlight %}

{% highlight swift %}
//Looping through an array with index
arr.enumerate().forEach({(index,char) in print("\(index):\(char)", terminator: ";")})
/*
0:H;1:e;2:l;3:l;4:o;5:,;6: ;7:p;8:l;9:a;10:y;11:g;12:r;13:o;14:u;15:n;16:d;
*/
{% endhighlight %}

{% highlight swift %}
//Looping through array indices
arr.indices.forEach({index in print("i:\(index)", terminator: " | ")})
/*
i:0 | i:1 | i:2 | i:3 | i:4 | i:5 | i:6 | i:7 | i:8 | i:9 | i:10 | i:11 | i:12 | i:13 | i:14 | i:15 | i:16 | 
*/
{% endhighlight %}


{% highlight swift %}
var airports = ["YYZ": "Toronto Pearson", "DUB": "Dublin"]

//Looping through a dictonary
airports.forEach({(key,value) in print("\(key): \(value)")})
/*
DUB: Dublin
YYZ: Toronto Pearson
*/
{% endhighlight %}
Let's talk about iterating over a dictionary.

{% highlight swift %}
//Looping through key in a dict
airports.keys.forEach({(key) in print("\(key)")})
/*
DUB
YYZ
*/
{% endhighlight %}

{% highlight swift %}
//Looping through values in a dict
airports.values.forEach({(value) in print("\(value)")})
/*
Dublin
Toronto Pearson
*/
{% endhighlight %}

Happy coding!
