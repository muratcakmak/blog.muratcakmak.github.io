---
layout:     post
title:      Web Request
date:       2015-09-30
summary:    Web Request basics in iOS
categories: jekyll pixyll
---

Web request is composed of just four(yeah, it is true, just 4(for Romans it is IV)) operations. These are POST, GET, UPDATE, and DELETE.

When you write a text, or take a picture from your device and submit it to your favourite app, under the hood, the app talks with a cloud server, then cloud server save the data to its database. This is the high level picture of the how client server architect works.

Most of the application we use everyday on smart phones, are just capable of the GET request. It means they asks for the server for the data, and server give them the data they requested. It is just that. For the code snippets below, I will show how this kind of web request works.

Applications

Web request can be challenging and sometimes difficult to debug, because you have to differentiate problem source is whether your code or your request. To eliminate the possibilities of having a bad request, it is nice to check to request before put it into the code. For this aim, I use postman. You can click the link at the end of the page. You can read the comments in order to have better idea about the process.

{% highlight swift %}
//It is better to call this function in your view controller
func webRequest(){

//It is our request. I check it with the postman app before I put the code
       let urlString = "http://jsonplaceholder.typicode.com/comments/5"
       //I create shared session in order to start request
let session = NSURLSession.sharedSession()
//This is for our session need NSURL kind of url, it looks like just parsing
       let url = NSURL(string: urlString)!

       session.dataTaskWithURL(url) { (let data: NSData?, let response: NSURLResponse?, let error: NSError?) -> Void in
           if let responseData = data {
               do {
                   let json = try NSJSONSerialization.JSONObjectWithData(responseData, options: NSJSONReadingOptions.AllowFragments)
                   print(json)
               }
               catch {
                   print("There is an error")
               }
           }

       }.resume()
       }
}

{% endhighlight %}

The apps & technologies used for web requests

Postman



JSON



HTTP



NSURL

Note: For further information read this answer on stackoverflow.
