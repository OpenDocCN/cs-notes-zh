# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p05 4_请求响应周期.zh_en -BV1Lr421A75d_p5-

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_0.png)

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_1.png)

So now we're going to do is we're going to try to dig even a little bit deeper in how these HtP requests。

Work， and we're going to make one up by hand。'll show you how to talk talk to one by hand。

 So if we look at the RSC， we see that we make a connection to the server。In this case。

 we're going to go to data。pr4。org and I'm using the original old protocol from 1990 and increasingly servers are refusing to serve documents using the old protocol。

 they want the at least HttP 1。1 but so not all servers do this but does data。pr4。

org I got it on a special ancient server， so it always talks HttP 1。0 so I can do this demonstration。

HTP 1。1 is similar， It's just a little more sophisticated。

 but it's harder to type it by hand Okay and so that's why I use an old server that does HtP1。

0 The HB 1。1 still has a get thing and a URL and it just has more stuff afterwards that you got to put in so but let's go back to the basics back to the way it was in 1990。

 1991 and that is you talk to your server you send a get request and hit enter and then a way you go Okay so here's kind of what I'm going to show you。

I'm going to use a command on my Macintosh called Tnet。Telnet predates the Internet。

 It's one of the early protocols。 FTP file transfer protocol， SMMTP simple mail transfer protocol。

 Telnet was the way we logged into servers， but I'm going connect to this server。

 but instead of connecting to the normal login port。 I'm going to connect to port 80。

 port 80 is where we expect a web server to be listening。 And so if there's a web server。

 then it will connect。 and then it will stop， and then I will type this command。

 Hopefully I'll type it fast enough for the server to not run out of patience with me。

 They'll hit the enter。 And this is exactly what the server is going to do。

 So I'm typing this and the server is going to respond。 This。 This is the request。

And this is the response。And you can do this， too， but realize that。

Fewer and fewer servers talk the classic HTTP 1。0 protocol。 It's so sad。So but I keep this。

 this is my antique server that I can talk the old protocol。 Okay， so I'm going to start this up Oh。

 by the way。

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_3.png)

If you're on Windows， it doesn't come with Tnet， but the bashhe probably might come with Tnet。

 I don't know about that。 but you can you can Google how to make Tnetwork on Windows。

 And so then you can do this on Windows Also you can make tnet host name。

 space port name and it should work。 you should be able to eventually do this on Windows you just can't do it out of the box。

 Linux， of course， this works perfectly on Linux and Macintosh right out of the box。

 And so now I want to show this to you in Tnet。 Now again。

 you have to do something little weird on Windows but on the Macintosh it's easy。

 So I'm going to type the command Tnet。 This is just a local command data PR 4 org So that's the server I'm going to talk to in port 80。

 And so there's all these web servers or mail servers or whatever servers and there are ports which are like phone extensions that tell you what application to talk to and I'm trying to talk to a web server。

 and you'll see it's going to use that information to find the IP address。

 the actual address of the web server， which is 192241。

136170 Now it is waiting for me to type an HtTP command and I got type get which which is the verb that's give me a document and then I have to take type the UI or URL Co/data。

 PRr4。org。Page1 dot HM。 So this is what your browser is sending H TTP slash 1 do0。

 Now I have to hit enter。And then I have to enter again。

So now the server responded and so if you look。This is what I typed。 I typed that。

 and I typed this blank line。 I typed that， and then。The server came back。

 This is the entire server response， and then the server connect closed the connection。

 That's tnet telling me that the connection got closed。 So this is a super simple protocol。

 I type two lines， and I get all this data back from the server。

 and this data can be broken into two parts。The data can be broken into a header part and a body part。

 and so there's a blank line here and that's exactly what the protocol says there is a blank line between the header of the response and the body of the response。

And so the header is all metadata。That the browser knows things like how big this file is。

 that's how big it's going to be， it knows that it's not supposed to be cached it knows that it was last modified on this date and what kind of a server we're talking to an Apache server remember I was talking about Apache in a previous thing and this running on a Linux operatinging system called abutu and one of the more important things in here is this content type which tells basically the kind of information So right now this is an HTML page and so it says the thing I'm about to give you after this blank line is HTML but this could be an image。

Or something else。 And then we wouldn't be able to look at this very well if we look like but it would be really the image。

 And so if you're taking bringing pictures down or PDFfs down or whatever。

 you get the actual picture of the PDF here。 But because this is HTML。

 we get HTML which has tags in it and it's got its own little anchor tag then an HR and some new clickable text etc cetera。

 et cetera， et cetera。 And so。

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_5.png)

This is sort of what the browser is doing on your behalf when you click on a link。Okay。

 so that's what happens。Those of you had classes from me before。

 you know that I am obsessed with the command line。

And you may or may have be told the story This is a movie scene that was written by one of my former students。

 His name's also Chuck， and it was initially in the Ma reloaded。

 where Trinity is breaking into the power grid to shut everything down。

 And this is actually command line hacking。 The scene was originally written for some kind of minority report like UI And he said that's not how people hack people hack in the command line just like I just did。

 And so part of all cool security hacking movies now is doing something in the command line。

 and that just reinforces how much I love the command line and how much I want you to be able to know how the command line works just because it's super cool。

 And you can also take a look at the URL and watch that。

Another part of this class ultimately is to get to know our browsers and so I just showed you how to hack it。

 but you don't really need to do that that's the hardcore way。

 even though sometimes I do that to figure out what's really wrong because I have to type the HtB11 protocol which is harder than the HTB10 protocol that I just showed you and so our browsers have this developer mode。

Safari has preferences， sometimes you have to turn these things on so I want you to go turn them on and I want you to be able to look at this stuff because this is where you as a normal web developer are going to diagnose problems with your application because like did it screw up in the client that it screw up in the server was there bad data going back and forth and so you're going to get used to this believe me by the time you're all done and concepted developer mode even if you're not right in the application。

 it's fun to go figure out when stuff breaks what's going wrong in someone else's application and so。



![](img/5b4f3ef3a7e90f441636c78dee8ca15e_7.png)

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_8.png)

Let's take a look at this， so let me bring up my browser here。



![](img/5b4f3ef3a7e90f441636c78dee8ca15e_10.png)

Take a look at a webpage， wwwD。dchuck。com。When I type that URL， that goes and does a get request。

 but this is a much more complex page because it has pictures and stuff and they don't come down as to all all with one request。

 and so I can do De viewDevelop console。

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_12.png)

And I can see things and so I'm going to go and take a look at my network tab and I'm going to do this again and so I'm going to type I highlight it and type enter。

 which causes that initial get request to happen again。

 and then you can see all of the network requests that happen。Okay。

 and so what happened is to generate this page， it did 71 request response cycles。

 and if I scroll all the way back up to the top here， this was the first one。

 the first one was a get request。Okay this was a get request。

 it was a get request to this URL and 200 okay。 Oh， I forgot to show you。

 let me see if I still got it。

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_14.png)

I forgot to show you that the first line of this header response is an indication of its good or not。

404， for example， says I didn't find it。 So this was it did find it。

 If I type made a typo mistake here， I could have got a 404。 Well， let me do this。

 I'll make it go a 404。I'm going to say get h slash slash data do PR4 e。 org slash page4。t htm。

 which I know doesn't exist。 HP slash1。0。 So this is a URL it doesn't exist。

 This is what happens when your browser sends a request and it doesn't get a page back。See。

404 not found this first line of the header。 again， I typed this stuff。

 first line of header 404 not found then the blank line not says something about， hey。

 I couldn't find it， but also it sends 404 not found。Like I said， you don't have to do this by hand。

 You do it here。 and it says， oh， you got a 200。 And then it got remember the headers。

 The headers are sitting right here。 Re headers。 If I go to data dot PR 4 e do org s page1 dot HM。

 There we go。 So this is that page。 and look。

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_16.png)

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_17.png)

We asked for this URL， this is what we asked for。We got did a get。

 we got a 200 okay the address this was the address away we go and here's the response headers。

 We saw those response headers。 they're pretty much the same as these response headers and the Httb 1。

1。 we use the Htb 1。1 in this one and we actually send a bunch of other stuff this stuff here that says you know what my preferred language is what kind of browser I'm using etc etc etc。

 And so that's some of the data this request header stuff it actually goes right here remember when I type that enter key you know there's a bunch of stuff that goes here and then you type the enter key and it's all these request headers that are communicating to the browser something about communicating to the server something about what your browser is doing you'll get better at this So there's the request headers then there is the response which is the body part that's it's showing you the headers over here and then the body over here and then the preview if it has a preview but we're not going worry about that。

 So now let's go back to this one。

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_19.png)

So it was。It got some page wwwDchuck。com it was a get request 200 okay。

 this is the IP address of that server。And we can take a look at the response。

 and it's a bunch of HTML， blah， blah， blah， some CSs， blah， blah， blah， blah， blah， blah， blah。

 blah， and that's the first page。 Now the problem was is the in this page。You know。

 we haven't done HTM all yet， but in this page somewhere， somewhere。

There is a picture that says load this image。 And so it reads this as your browser is reading and parsing this。

 It's， oh， I got to go get a picture。 So it goes and does another request response cycle。

 So here's the request for Doctor Chuck dot com and often in small JPg。

 which is that little picture in the upper left hand corner and it got a 200 okay because it already received at once。

 And the response， it was an image Jpeg。 Remember， the other one was an image text Hm。

 And so that's the response headers。 I don't know if I can see a preview。 Yes， you got see a preview。

It would look yucky， so we don't see their actual text of the actual response。

 So there's the second request。 Then it went to this rate。

 my professor picture then some other thing and， you know， on and on and on away it goes。

 And it just， it just read that。 And it just had to get all kinds of other things。

 Javascript and widgets。 Now， we will eventually write applications as you know。

 that do lots of these things。 And like I said， eventually。You know， it did 78 requests。

To get this page constructed so there's a lot of things that you can do and a lot of some of the early assignments will be asking you to do things with this developer console again so that you can really get to understand the request response cycle。



![](img/5b4f3ef3a7e90f441636c78dee8ca15e_21.png)

So we have so much more to learn。Technologies in the browser， HTMLml， CSS， the Dom and ja。

 JQury in the web server， we got our web server， PhP， my SQl， all these things。

 we got so many things。 and this is the picture that you're going to get tired of because this is my favorite picture in the whole world because I can tell you in this picture about the browser that has a document object model and I'll draw pictures that look like this And don't worry So this is where HttP happens。

 So there's the network and then often the database server and the web server on different servers and there's SQl that goes back and forth between them even if they're on the same server。

 it's kind of like a virtual network connection。 there's the SQl software。

 there's the Apache web server。

![](img/5b4f3ef3a7e90f441636c78dee8ca15e_23.png)

So you will click on a request， that request will be sent to a server using HTTP。

 then maybe that will have some the PhP that comes in， it goes and runs the PhP。

 it makes a connection to the database， the database reads some data， comes back。

 sends some stuff back， does a response， the response populates the object model。

 maybe runs some JavaScript， which also messes with the document object model。

 and then you see the document object model。You don't have to know this right now。

 I I will hit this almost every single lecture because in a web application。

 the notion that there's a browser， there's a web server。

 there's a database server and there are different things going back and forth。

 and that web developer console is really looking at this area right here。

 And so you have to debug so many things and there's way to debug these things and debug these things。



![](img/5b4f3ef3a7e90f441636c78dee8ca15e_25.png)

There's just so much more。 And it's so cool。 It's so cool。 when you really understand how this works。

 then you can use any web framework， any browser framework and this notion of database backend。

 web server， middle and browser。😊，So again， this is not the only way to write applications。

 but the concept of the web browser and even mobile applications have kind of like these three layers sometimes where they have code that runs in in the mobile device。

 server code and then database code and so there's a lot to understand and we'll just start picking this up one thing at a time。

 build a whole bunch of building blocks and then put them all together so you really understand how web applications work。

