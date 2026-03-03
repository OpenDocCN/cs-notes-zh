# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p71 11_02_07_用Python构建简单HTTP服务器.zh_en -BV1Kt421V7EE_p71-

![](img/ff6928b67427fff626520a26f18f8625_0.png)

So we build a browser in Python， it's time to build a web server in Python。

So remember that what we've got here is we've got， you know the browser is an application and we've made this a Python application now that sends this gett request。

 so we have effectively like I said， built the world's simplest browser and that sends a gett request。

 that server does something and then it sends the response back and now we're going to kind of change this right。

 we're going to assume the browser exists and it's like okay because we're going to be the server folks right。

 so now we're going to look in greater detail at what goes on in the server。



![](img/ff6928b67427fff626520a26f18f8625_2.png)

![](img/ff6928b67427fff626520a26f18f8625_3.png)

![](img/ff6928b67427fff626520a26f18f8625_4.png)

![](img/ff6928b67427fff626520a26f18f8625_5.png)

And so here is a very， very simple web server， it's a few more lines than the simplest of web browser because we have to put a little bit of air checking in with some tries and accepts okay so let's walk through what this code does okay let me change the color again to black。



![](img/ff6928b67427fff626520a26f18f8625_7.png)

去。If you're from Microsoft and you can tell them to make a key to change the color on the scribbler。

 Id greatly appreciate it and then I went down a page too。



![](img/ff6928b67427fff626520a26f18f8625_9.png)

![](img/ff6928b67427fff626520a26f18f8625_10.png)

Okay， so we're going to pull in some more stuff from the socket。



![](img/ff6928b67427fff626520a26f18f8625_12.png)

We're going to pull in some stuff from the socket right here。

And so we're going to make a function called create server that we're going to call right down here and it's going to print out how you're supposed to access it and then start the server now the whole idea of the server。



![](img/ff6928b67427fff626520a26f18f8625_14.png)

Is the server is woke up to wait for incoming connections， so the server already exists。

 So when you start talking to a web server that server is in that computer already。

The service software is already running， registering its interest and incoming request。

 So that's what we do。 So when this Python program starts， it's going to sit there and wait。



![](img/ff6928b67427fff626520a26f18f8625_16.png)

In an infinite loop for incoming requests。So the first thing we do is we're going to make a socket。

 this looks very much like the time we made， it's an endpoint。

 it's not actually making the phone call where remember I said this socket call is making the phone。

So we're saying we're going to make a phone and it's up to us later。

To decide if we're going to make a phone call or receive phone calls。

 and then this next thing is like to connect。Except this is I am willing on port 90 to receive the phone calls。

 Now， it turns out there's only one program on port 90 that can receive phone calls。

 so this might blow up you might try to do this， I mean。

 port 9000 and if you run this twice and you can do it in two windows on your computer。

 the second one will blow up and say you can't have port 9000 because another piece of software has it。

 but as long as there's only one running away you go。

 and that's part of this whole try accept thing because if you run this twice gonna blow up the second time because you cannot receive phone calls on this server on port 9000 with two applications。

 one application gets the phone calls。 that's what socket listen says the five on there says dear operating system。

 if I'm busy handling one phone call， you can hold on to four more and queuee them and then I'll come back and get it for you and you're asking the operating system to queuee incoming calls。

 don't just say you're busy shut down if you didn't say this listen5。

If you were busy writing the data for phone call one and phone call two came in。



![](img/ff6928b67427fff626520a26f18f8625_18.png)

And you weren't ready for it write that instant， it would just deny the phone call。

 so that's what listen says is dear your operating system， hold hold those temporarily。

 I'll get back to you。Which is how it works。 And then what happens is we go into this accept now this accept is。

I'm at the phone， I've registered what my number is and what my extension is and I'm ready to pick the phone up let me know so this accept is blocking it stops and it just sits there and it can sit there forever you know just。

Literally forever， if nobody calls it， nothing happens。

 the next line never exit never runs until you blow it up。



![](img/ff6928b67427fff626520a26f18f8625_20.png)

Where the server goes down， so that's accept is a blocking， and the reason we do this except。Well。

 we have to establish the phone call first right So then this next line runs only when a phone call is received。

 So that means that we on the browser side， we already connected。

You know we made the phone call now we haven't sending data yet right and so this is just now at this point somewhere out there there's a piece of client software that has done us socket。

conn。And we have done accept and are accept is succeeded in the server。 The connect is succeeded。

 and we are ready to talk。 So the phone call has been made。 Now， the question is。

 who is going to say hello。 And this is where the H T TP protocol solves our problem。

 The server knows that the client must speak first。😊，So it just does a receive。

 now you'll notice the receive and the send are the same function calls。

Because it's a two way thing that whatever the browser is sending。

 the server is receiving and whatever the server sends the browser receives and they can do it simultaneously if they can figure it out。

 but usually you kind of like say it's your turn to listen and my turn to send and then I'll listen and usually they kind of go back and forth。

In this there's only one step， you， the server listens， gets the get request， sends the data back。



![](img/ff6928b67427fff626520a26f18f8625_22.png)

And so then we're going to read some data。And we're going to get 5000 characters。

 we're going to get the whole thing。 Remember it's one line， it has a get request in it。

 it has the optional parameters in it。 And so we're going to split it now again。

 we've received it as UTF 8， we've got to decode it for UTF 16 I mean not UTF 16 Unicode inside of。



![](img/ff6928b67427fff626520a26f18f8625_24.png)

Python and then we split it based on new lines because the get request is on one line， then header。

 header header， header， header， header and then the blank line to tell us that we're into the headers and we're only going to take in this we're just going to look at that first line。

 we're not going to do anything with it。 most servers actually like look at the line to figure out what document to send justs a very simple server。

 it sends the same document no matter what the URL is all we do with the URL is we print to it print it out to prove that we got it。



![](img/ff6928b67427fff626520a26f18f8625_26.png)

![](img/ff6928b67427fff626520a26f18f8625_27.png)

And then we construct a response and in this response， again。

 go back to RFC 26 2616 and it will tell you what this response is supposed to look like。

It sends back a 2000 okay， remember this is all the stuff we saw。

 probably I cut and pasted it from a working thing。

We tell it that we're sending it back in content type text HTML， character set UTF8。

 remember I was telling you that。A blank line。And then some HTML。Html body， hellello world body。

 and I'm throwing in these slash R slash ends， which is the network version of new lines。

And then you will notice that I encode it before I send it because it's Unicode inside of Python and it needs to be sent as UTF8 because the phone。

 when you're in a socket， the thing that's going across the socket almost always is supposed to be UTF8 so we encode it and then because the protocol says so as soon as we send the data we close the connection and remember that the client had to close the connection too so we close it it's half closed and then the client gets all of its data gets the indication that it closed and knows it's finished all the data and then the client shuts its side down and so there are two hang ups。



![](img/ff6928b67427fff626520a26f18f8625_29.png)

![](img/ff6928b67427fff626520a26f18f8625_30.png)

It's kind of like a phone call。 The person hangs up and then click you hang up Now there' you can't really keep talking。

 but you do want to have both sides hang up and that shutdown is what's going on。

 And then the rest of this is all try accept for various things。 so we clean up our socket。

 So we don't have to restart our server when our software blows up。

 And so the rest of it's pretty simple。 And then so this while one。

The first browser will talk and then it'll send some data and then it'll go back and wait for the next phone call and that's what's going on。

 The next phone call comes in it doesn sees a get request。

 it sends the data back then goes and waits for another phone call So this is an infinite loop that sits and waits for incoming phone calls and you know it answers the same thing So it's like you call this phone number and it goes and you go。



![](img/ff6928b67427fff626520a26f18f8625_32.png)

I would like a pizza and it says hellello world， and then click and then you call it up and say。

I would like a car and it says hellello world click and then you say I would like to register for this class and it says hellello world click。

 so this is not a very flexible server， you will build far more flexible servers。

But it's the one I could build and fit on a single page in a slide deck。



![](img/ff6928b67427fff626520a26f18f8625_34.png)

So to run this。If you you know you download this code and it's a tiny bit of code and you run it。

 so you go somewhere， maybe your laptop， maybe Python anywhere。

 I don't know if it works on Python probably doesn't work on Python anywhere because you can't actually talk to ports but let's just run this on your laptop and you start the server up。



![](img/ff6928b67427fff626520a26f18f8625_36.png)

Somewhere get a hold of my sample code or download it from here， server。pyy。

 and it's telling you this is just output from the server and this is the moment at which it's waiting right。

 it's waiting， the server could wait for hours at this point。

But I just give you this in a print statement so you can copy that and put it into your browser so you paste local hosts 9000 into your browser and then the server is printing that it got a get request for the slash document from this browser that's what the browser said。

 I mean， we're talking。From Firefox browser to the little web server that we just built Now there's another a second get request that you don't even know because you didn't ask for it and that's because the browser is built in to ask for a URL called favconicCO so that it can make an icon and that icon ends up in the tab or wherever in your browser and so that's like an icon for the website so you didn't ask the browser to do this but it's a thing browsers do and you'll see when you're looking your debug logs when you're building stuff that it's a fco and so this happens like blink link and now it's waiting again and you could hit refresh or you could go start a different browser and you would see these get request every get request you're going to see in your browser and your server so's so it's working and it works really well and you're welcome to go ahead and play with it and try it all out。



![](img/ff6928b67427fff626520a26f18f8625_38.png)

So now what we're going to do is build a simple web client and then it'll talk to our server。

So the other web client we made talk to data。pr4。org， this one is going to talk to yourself。

 so it's this it almost looks identical， right？

![](img/ff6928b67427fff626520a26f18f8625_40.png)

We're going make a phone we're making a phone， we're going connect to local host 127001 is the IPV4 connection what's called loop back right to the same host。

 We're talking to port 9000 because that's where we've got our web server running that little web server we just wrote and then we're going to send a get request。

 the valid gut request to this thing H10 and then two new lines and we're going encode it into UTFA before we send it then we send it and then we just have a loop to print it all out and then when the socket gets closed。

 we hit a break and then we close our end of the socket。

 So the server clicks the phone and then we know we're done with our data。

 but we've already printed it out and then we hang up the phone on our end to kind of clean everything up all the way in between everything else。

 So this is a very simple web client。

![](img/ff6928b67427fff626520a26f18f8625_42.png)

![](img/ff6928b67427fff626520a26f18f8625_43.png)

![](img/ff6928b67427fff626520a26f18f8625_44.png)

And so now you can run the web server。Just like we did before， and instead of talking in a browser。

 we run this client。And this client gets a header of HP 1 okay， it's content typey X HTML。

 it gets a new line and then the body and we're done now I mean it's not a browser。

 but it is client that's talking HttP and so now you'll notice that。

This server sort of sits in weights for incoming calls。

 you could run this over and over on the client， run the client over and over again right and then you would see more requests。

 but in general the server is destined to just sit and wait for hours potentially until a client connects to it。



![](img/ff6928b67427fff626520a26f18f8625_46.png)

Then at some point you'll just abort this server and then if you control C or blow this up somehow。

 this will fail， the client will fail and it will fail。It will fail in this connect code。

 So if you want to play with it， try to run this client without running the server and you'll see that to connect。

 which is the part of actually making the phone call， this will continue to work。

 which is make me a phone on my current computer and then connect is make a call to the remote computer that will blow up and then if you want it to play with this you could put some try accepts around it。

 say remote computer is not responding on port 9000 that' if you blew up。

 you put it could put a try and accept around that。

But I'm not doing it because it don't fit on my slides。

So here is an even simpler web client that we can use and again。

 you can get this code from my sample code。We don't talk to this we there's a higher level thing that so the previous client talked to sockets so I could show you the low level。

 but because we spend so much time talking about to URLs we then have a URLib so I'm just going to use URL Lib I'm going and this could be a local host or it could be whatever I'm just going to make a。

Four line URL Lib call， and so I just do a URL open of that same URL now we're operating at the HTP level because URL the concept of URL is not a socket concept。

 a concept of URL's HDP concept。

![](img/ff6928b67427fff626520a26f18f8625_48.png)

And we just get in effect what looks like a file handle to us。

 and we loop through it and print it all out。So we run our server and the server sort of says this and waits。

And then when we run our client， it basically hits our server and we can see in the server window。

 you got to do these these two things in two windows， right。

 you got to do these things in two separate windows So in the server window you'll it'll sit and wait and then in the client window when it runs。

 you'll see the client will make the request of the server。

or blow up with the server is not running and the server will see the get request and then the data will come back to the client so you sort of do this in two things and you can run the client over and over and over again and you'll see every time you run the client。

 the server sees it， responds in a away you go and again our server always says hellello world no matter what which is delightful and classic。



![](img/ff6928b67427fff626520a26f18f8625_50.png)

It's a classic。

![](img/ff6928b67427fff626520a26f18f8625_52.png)

So you actually can watch when you're running Django。

 there will be a way for you to see when you're running Django locally and you start the server up this managed3 don't'll do this later。

 manage Pi run server and then you talk to it and you will see all the get requests and so Django when you run it locally you can debug a lot of what's going on see you can see like the Favcon that it's asking for and that is five or six HTTP request to produce that little Django webp page and so that will be something that you will learn how to do。



![](img/ff6928b67427fff626520a26f18f8625_54.png)

And so。So that sums up what we are doing in this you know。

 at the beginning you look at it very simply pretty soon you'll just be looking at the developer console and it all make sense to you。

 I want you to be able to know that you can dig as deep as you want to and understand all of these protocols that are going back and forth okay。

 cheers。