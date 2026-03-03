# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p67 07_02_03_动态Web内容简介.zh_en -BV1Kt421V7EE_p67-

Hello and welcome to our lecture on dynamicy web content It may seem kind of weird to be talking about building web applications。

 but and to when we start out talking about buildinging web applications that we're going to talk about protocols and stuff。

But in a way， when you are building a web application。

 if you don't understand the protocol and you just sort of say。

 I changed this little bit of code and hit refresh and some magic happened， you really are。

cheheating yourself in terms of becoming a really good web application developer because ultimately these protocols are what enable web applications and as you go forward and use frameworks。

 you don't need to know all these things in detail but when you debug your applications you absolutely do and I don't know if you've had your Firefox console or looked at things and watched。

 there's so much complexity going on and when you're using a web application hopefully everything works and that complexity is hidden from you。

So if you have some interest in this and want to go even lower to sort of more the network protocols。

 not just the HTTP protocols， I've written a free book on networking。

 called Introduction to networking， how the Internet Works， that you are welcome。

 it' you can buy a print if you want， but it's also completely free。

 like every book that I write these days。

![](img/641ce97de18e66bbb0bbeb30d166f7e6_1.png)

And so if we take a look at what we're going to really be talking about in this lecture and in this web application course is the technologies。

 the different technologies that are used to in effect produce a web page right so we have a web page over here you go to URLdd data I mean data。

pr。 PRr4。org s page 1。htM and you know here comes a page and this is like a super simple page but there are so many technologies like how browsers work with jascript and jQury and CSS and eventually view and things like that that's a whole set of frontend technologies and then there're sort of backend technologies like jago or Flask and databases and we're going learn in this my focus in this classes less about how to make it all look beautiful all that's important and more about how to deal with the bit backend so what we're going to see is these technologies that define the look and feel and the interactivity of your web。



![](img/641ce97de18e66bbb0bbeb30d166f7e6_3.png)

But also then how data and HTMLC and JavaScript are served up by the remote server and so the internet here is in the middle。

 the browser is sitting on your laptop or your phone or whatever。

 and it has all these technologies built into it， it makes requests and then the server comes back with responses。



![](img/641ce97de18e66bbb0bbeb30d166f7e6_5.png)

And so the simplest version of this protocol is that you click on a tag and when you click on that tag you get a new web page now if you watch your Debar console you will see that sometimes it's 120 different request response cycles used to construct the page but in a sense they're all the same now as we move to things like HtTP2。

 there are ways to pull down multiple documents in a single connection。

 but we'll stick with the old HtTP one way of thinking about it。



![](img/641ce97de18e66bbb0bbeb30d166f7e6_7.png)

In the simplest form， the browser asks for a document and then retrieves the document and then shows the document and that is the basic request response cycle So if you look at how this works。



![](img/641ce97de18e66bbb0bbeb30d166f7e6_9.png)

That browser is an application running inside your computer on your laptop or your phone。

 That is a piece of code。 and in that it's got a connection to the screen or the keyboard or the mouse or whatever。

 and it's watching for events meaning that you're going to go and you're going to click somewhere and then this application is going to respond to the events。

 So in a web page in the simplest case， you got stuff that you can click on and stuff that you can't and you go find your way through whatever to click on part of that web page。

 and that click is intercepted by the application， whether it's Chrome or Firefox or safari running on your piece of equipment。

 and then that application then opens what's called a network socket a socket across the network to a web server and sends a request。



![](img/641ce97de18e66bbb0bbeb30d166f7e6_11.png)

And that request， as we'll see in a bit， is a specially formatted request， it has a git command。

 and then it has the URL that it wants to get from the web server。

 and then the web server does a bunch of work inside itself。

 a bunch of work inside itself may be reading disk filess and running the programs generating what it is that you want。

 and then it sends the response back on that same socket connection。

 so there's like this socket connection through which all of this stuff is viewed。



![](img/641ce97de18e66bbb0bbeb30d166f7e6_13.png)

And so the HTML is kind of the basic thing that comes back as we go further we'll see that it's not just HTML that comes back。

 but other things as well it come back and so when the browser receives that HTML， then it says。

 oh I know what HTML is， I've got this header one tag here let me change the color of this thing so you can see that see a little better。

Yellow is way better okay so when the browser receives this page it it sort of sees it and it looks at it and then it looks at all the HTML and so part of this course is to understand the syntax of HTML that itself is a you know how to build good HTML and CSS and how to make it look beautiful but ultimately something in the HTML plus its CSS plus its JavaScript leads to a visual display of the page and then that's the thing that you see and so this is the request response cycle。



![](img/641ce97de18e66bbb0bbeb30d166f7e6_15.png)

![](img/641ce97de18e66bbb0bbeb30d166f7e6_16.png)

So up next， we're going to talk about what these network sockets are or the things that fundamentally underlie this request response cycle。

🎼。