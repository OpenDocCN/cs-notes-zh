# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p04 3_超文本传输协议(HTTP).zh_en -BV1Lr421A75d_p4-

![](img/66a321e18f22d84d0a8668feb2c2ad65_0.png)

![](img/66a321e18f22d84d0a8668feb2c2ad65_1.png)

So now we're going to talk about how web pages get constructed now you might say why are we looking at all this detail？

Partly because what I want you really understand is how web applications work because web applications and frankly many mobile applications have multiple layers of components。

 multiple parts that work together in the web browser。

 you got the browser and then you got server and then you got a database server and so what I want you to understand is I want you to be able to as you write code know what part of this multiystem system that you're working with。

And so。The browser is the thing that runs on your on your hard drive。

 it might run on your phone or something， and the things the technologies that we're going to learn are like HTML and CSS Later we'll learn about the document object model。

 which is a wave HTML is what formats this CS kind of，Picks the fonts and things。

 and the document object model is the way the JavaScript goes in and plays with stuff， changes words。

 we'll learn that how that happens and JQury makes that even easier。

And so we have a lot of technologies in the browser that we're going to learn。

 and then we're going to have a lot of technologies in the server that we're going to learn。

 we're going to learn about PhHP so that we can write code in the server， we're going to write SQL。

 so we can find stuff hidden throughout in our databases and bring that all out and send it back。

And then we're going to learn about the request response cycle。

 and that is where the browser is talking to the server and we're writing code in the server to respond and what goes back and forth and that's HTTP Hypertext transport protocol Also JON。

Is part of what we're going to do back and forth。 So when we have ja talking and getting data back and forth。

 it uses JSON And so in this first I have to start somewhere right and so where I want to start is I want to start to give you a sense of what happens here because this is the basic separation point between what goes on in the browser and what goes on in the server room talk a little bit about the hypertext transport protocol。

 but mostly I'm trying to give you a way to realize that there are different pieces of code and technologies that are being used in these applications。



![](img/66a321e18f22d84d0a8668feb2c2ad65_3.png)

So HTTP is the dominant application layer protocol， it was invented in 1989。

 1990 by Tim Burnernners Lee and Robert Kayu when they invented the web。

 and it's probably there's other protocols that predate HTTP like FTP for file transfer， TNet。

 SMTP for simple mail transfer。These are all well developed。But Tim Bs Lee and Robert Kayu。

 they wanted a。Easy protocol mostly because they weren't protocol developers they just wanted to build an application that could show pages and let people edit those pages。

 so they kind of built the simplest possible protocol so these protocols go back and forth and back and forth in HtTP it makes a connection it asks for a document and it gets a document back it's really quite simple and I'm not sure it was engineered to be simple but what happened was is we were able to layer on top of this simple things like。

Web services and other things that are kind of just a slight variation on it。

 And so most of the new protocols that we use are simply protocols that sort of take a different convention on top of HttP。

 so it's it's beautiful in its elegance and it's the only one that we can hack because it's so simple that we can hack it。

 I used to be able to hack the mail protocol but then security got in the way I made it difficult to use Another of the core contributions of HttP again by Tim and Robert in the early 1990s is that the notion of uniform resource locator。

 Now you'll find this on， you know you'll pick up a brochure be the HP called bla b， b。

 bla blah and you're like oh okay I know what that is。

 And I type that into my browser and I go get a document or a set of documents。

But there's actually some science that goes into these uniform resource locators。 and before the web。

 you had to know what host to go to， what protocol， what set of commands to to that host。

 and then what kind of things on that host that you might want to retrieve。

 The URL just comes up with a convention and then concatenates these things together。

 So HttP con s is the protocol。 There are more than just that one。 This server that you talk to。

 And there's like out in the cloud。 There's like server server， server server server server。

 Which of these servers has the document。 What protocol is what we do to talk to it。

 and then within the server， there's files。 And so this document within the server tells us what we're going to look at。

 Now it's more complex than that， you can put parameters on the end of this。

 You can put what are called anchors on the end of it。 So there's all kinds of things。 X equals 2。

But that's the basic idea of a URL is how to get it， where to go get it， and what to get。

All concatenated into one long string。And so the idea is as if we have one of these URLs and we type it in the browser。

 we get it The other way that we can do this is not just typing the URL in the browser。

 but embedded in the HTML are what are called anchor tags which are clickable links that have an HF hypertext reference inside that and we'll talk about this in the next HTTP lecture。

 the HF that says oh when someone clicks on this link。

 go throw this page away and go to a different page and so it's the hypertext aspect of it。

 so you click on a link and then you go to the next link。And so the link turns into a get request。

 which retrieves a page which gives us back new HTML， which then is shown in our browser。



![](img/66a321e18f22d84d0a8668feb2c2ad65_5.png)

And so the first thing we're going to do is type a URL， so if you type data。pr4。org/page 1。

htm and then you hit enter， you have told it to go get a get request and if I take a look at the source code here。

View page source you might have to you might have to put like a developer mode on or something to see view page source。

 but we can see the page source here。 You see this， this markup。 This is HTML。

 talk about this in some detail， and this is an anchor tag that says when this second page is clicked on。

 go and get this URL。 So we're on page1。 Hm and this is page 2。 Hm。And so if I click on this。

 it'll just be like instantaneous。But。We've been to another page and there's a link back to the first page back to the second page。

 back to the first page。 Okay， And so that's basically hypertext navigation。

 But our browsers are doing things and seeing these little clicks and then doing something gettinging a different page。

 Now， of course， it's far more complex than that and we'll see that in just a moment。

 But I want to go and take a very close look at exactly the steps that happen with this simple hypertext navigation。

 So at some point。

![](img/66a321e18f22d84d0a8668feb2c2ad65_7.png)

We typed our URL into the browser。We did hit the enter key， and that caused a get request to happen。

 And now we see this page。 And now we have an anchor tag in there。 that's a hypertext reference。

 And in the early days， they were all colored blue and they all were underlined because people needed permission to click on things。

 We're so used to looking at pages that you couldn't click。 Now everyone thinks hypertext is right。

 And you know， its just you'll just click on everything。 See what， what can I click on here。

 Well in the old days， we used blue text and underlines to say， click here。

 So when you click on this。Your browser is a piece of code that's running on your computer。

 So this this big white box is your computer， whether it's your phone or whatever browser is a piece of software like Chrome。

Firrefox Internet Explorer， I guess they called edgedge now。Safri。Ura。lots of browsers。

 Those are software applications that are your client that views the web。 They're a browser。

 So the browsers an application， it's the thing that is showing you this page。

 And when you click on it， the browser on your computer says， oh。

 somebody clicked on a link and it goes and looks to figure out what link you want and then when it knows what link you asked for。

 it it then makes a connection based on parsing that link。

It makes a connection to the right web server on a port called port 80。

 which is the normal port for Web servers to live on。 And then it sends a request。

 It sends a little line of text that looks just like this。

 sends this whole line says that is the document I want。 Then somehow in this web server。

 This is the Internet。 right。 This is the Internet and some on this web server either generates the response or reads it off of a disk or something and out comes the response。

 and it comes back to us。And that response itself is in the format Hm hyperpertext markup language。

 just like I showed you in the view source， these are tags， N tag， tag， tag。

 and then there is a hypertext reference here that turns this second page into。Hang on。

 turns this first page into a hypertext link and this was purple because I clearly clicked on it before I took the screenshot。

 So when this HTML comes back your browser parses it and then renders it。

 there is the document object model that's kind of in the middle here that it pars it。

 puts a document object model and it comes to your page but that's the basic idea。

 you click request page is done response parsed shown and you get the page click requestquest response click request response Now it's going to be way more complex by the time we're done。

 that'll be like many request response cycles okay but that's the basic request response cycle。



![](img/66a321e18f22d84d0a8668feb2c2ad65_9.png)

Now this is all governed by internet standards， and the internet standards come from a very open source and a very open culture。

They were developed by a group called the Internet Engineering Task Force that predates what we think of as the modern internet。

 which is mid-80s， the IETFs came from even the 70s in an earlier network called the ARPpant。

And they came up with the idea of the IETF Internet engineering task force and these standards。

 and these standards are open， they're free。 They're unencumbered。

 meaning that anyone can read them and implement things that comply with these standards and then as such build yourself a web browser or build yourself a web server。

 if such a thing doesn't exist， Of course， these days， all these things exist。

 and we just download them， But the sort of thing that governs the protocols that we all use so that our code interoperates are these ITs。

 There's other sources of standards like the web Webwide Web consortium for things like HTML CSs。

 but the protocol stuff is very much through IetTF。

 Now the fun thing about this is these are the name of these things are called RFcs。

 which stands for request for comments。 And that's kind of a nerdy engineering acknowledgement that no standard is ever perfect。

 And even when they're done and they are 10 or 15 years old or。Like 1981 to 2017。

 that's like30 some years old now， they still might need to be improved so that even though it's。

30 years old plus it's still waiting for comments if you have a comment。

 if you find something wrong or you have a better way to build it then engineers want to hear about that so that's kind of a fun ironic naming conventions for these internet stands with RFCs。

And so if you were to pick up， there's many standards that govern HTTP。

 the hypertext transferfer protocol， you go read them and you could page down page page page and you will realize quickly that you don't want to write a browser。

 you'd much rather use a browser， but eventually you'll get down to a page way， way。

 way down that basically says how to make a request。



![](img/66a321e18f22d84d0a8668feb2c2ad65_11.png)

And if you keep looking， it tells you that you're supposed to put the method followed by the URI。

 a protocol version and then end with a character trend to line feed。

 that's what it's saying right here。The method token， which is going to be get in our case。

 followed by the URL URL。

![](img/66a321e18f22d84d0a8668feb2c2ad65_13.png)

Ening with a character to turn line feed etc， ettera， et ce。

 and so if you read long enough you could eventually see how we're supposed to do that and so based on how we're supposed to do that up next I'm going to show you how to manually hack an HTTP request。

