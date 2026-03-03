# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P45：44_应用层技术解析.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

So now we're going to talk about the application layer。

And up to now we've been talking about these bottom layers and we've been sort of working our way up。

 we talked about the link layer， the IP layer and the TCP layer。

 and each of these layers works with the other， the IP layer depends on a link layer。

 the TCP layer depends on and adds value to the IP layer。

 and now we're going to talk about the application layer that is going to make use of the services of the TCP layer。

And the services of the TCP layer are basically to give us a reliable sequenced end to end stream that can start in one application in one computer and end in an application in a different computer and have a two way communication so I can send the word hello。

Hello。From one application， and then all kinds of billions of dollars of hardware。

 hundreds of thousands of engineers， 40 years of engineering design。

 and out comes hello on the other end。And what's beautiful and this is the beauty of the four layer architecture is we just pretend this is magic。

This is magic。We send something and out it comes。With that magic available。

 with that billions of dollars and 40 years of research magic available， now what would we do？

Right now what would we do with that magic if we had it available to us？

So TCP is giving us this reliable pipe。We're going to think about now we're going to ignore all the rest of it。

 right， we're going to ignore。All this part， we're going to put。

 All we're going to say is we have an application on this into our computer。 Now， remember。

 this is your computer and say this is the server， right， So this is you。And this is the server。

And all the software runs in it in every， all the software is running in your computer and all the software is running in the server。

So the question is what are we going to do between these two things。

 okay how are we going to ask for data and this application is the client application。

And this application is the server application client and server are not necessarily the same very much the same client and server are likely very different applications。

 the client is like give me information and the server is responsible for giving giving the information to the client so the client is often making a request and then the server is making a response back。

And so this client server mechanism， this application to application communication。

 we can build a mail system with it World web， or we can stream videos much likely to be streaming this lecture back and forth。

 but we're going to focus on the World wide web because it's really simple and really elegant and it's probably the easiest one to understand。

 and it's the most popular。But there are many other protocols going on， file transfer and others。

 but the World W Web protocol， HTTPD is the protocol that is the most popular。So。

There are two basic questions that the application layer has to solve。

 one is which application gets the data。And this is done using a mechanism called ports。

And ports allow a Ip address or a single computer or a single server to serve up multiple services。

 And then for a client to be able to dial up much like a telephone extension and pick the service that they're interested in。

Once you've connected to the service that you're interested in， like the World Web service。

 then you have to know the protocol to talk to that。

Ports and TCP are like a telephone extension number again meant like I said。

 you can connect to an IP address， but then you can connect to a port within it。

 and so if you think about a telephone number and an extension it's sort of a further refinement and IP address gives us a particular server。

 a piece of hardware connected to the internet and then a port within that tells us what application we're going to talk to。

So let's talk about ports and connections。So if I have a server and this is kind of an arbitrary server here。

 here is a single server， wwwm。edduu and it has one IP address connected into the cloud we can have many clients talking to it and we have many services running on this server like sending email or logging into that server or retrieving webp pages or retrieving my mail from that server and there are ports so incoming email is done General import 25 remote login is 22 or 23 web servers depending on whether secure or not or 80 or 443 and。

The personal mailbox is on ports 109 or 110， and so these computers don't just connect to an IP address。

 but they connect to a port within an IP address。So some common TCP ports that we have are the ones I just mentioned。

 and you can take a look at these on the internet， the various ports， okay now。

Once we have a connection to the web server or to the mail server or to the post office server。

 we have to know how to talk to it， and that's what's called an application protocol and that is the rules for conversation。

 the rules for conversionverr。

![](img/717453ba6088343d27d38bf6f33aad7d_1.png)

So TCP gives us this reliable connection， we now can connect to the server that we desire to connect to by using ports。

 and the question is， what are we going to say across that connection and what we say across that connection who talks first。

 what do you send what comes back， depends on the kind of server that you're talking to。

 we're going to play mostly with the the World wide web click the wrong button there。

 the World wide web server because it's the simplest and it's the most obvious as to what's going on。

So the World web clients and the world， which are otherwise known as browsers。

 the World Web clients and the World Web servers communicate using a protocol called HTTP as a matter of fact。

 if you look at the top of your URL， it's HttP calling// something du du right？And so basically。

There is a specification for how this is done， so when they wrote down I'm going to write the first web browser in the first web survey。

 they also wrote a document about how that piece of software would talk to this other piece of software and it's a very simple concept HTTP has a protocol where you make a connection from the client to the server。

 the client requests the document the server feeds out the document and then the connection is dropped so it's very simple and we'll actually simulate this This is called the HTTP request response cycle。

And so the way it works is you're in a browser and you click on a link， the browser's an application。

 it's the client running on your computer， so this is kind of your computer down here。Okay。

 you click on a link。Then the browser makes a connection to the web server。And sends a request。

For the document， the web server looks up， does whatever， and sends the document back。

 and then the document is displayed on your screen。Okay， so let me show you sort of how this works。

With a web browser。So here is a canonical web page。 So here's a browser。

 Here's the URL that I went and got。 You can get this URL as well。 You can even look at the source。

 So if you look at this source， there is。My HTML， but one of the things that's in this source is a link。

And if I hover over top of this link。s look like that to hover up top of link。

 you can see at the bottom of my screen， you can see it's going to tell you that we're about to go retrieve page2。

htm。Now this browser is running on my laptop， it is a web client， it is an HTTP client。

 and I'm about to click on this piece of software running on my computer and then it is going to make a connection out the back of it。

 retrieve a document and then show me the other document， so it's going to happen real fast。

 I'll click on second page。It requested and got a document back and showed me the document。

 so that's the contents of the second document。And so that is the request response cycle that is triggered。



![](img/717453ba6088343d27d38bf6f33aad7d_3.png)

That is triggered by me making a click somewhere in my browser， the browser sees the click。

 it opens a connection， this is sort of the internet over here， it makes a connection。

 request a document， the document comes back and then the new document is displayed the request response cycle。

 click， request response display， click request response displayed so let's take a look in some more detail as to what's really going on here。

So the command that is being sent。😡，Up to the server。Across this connection。

 remember this part here is the internet right there， the command is a get command。

And the document is based on the URL I clicked on that the browser knows about and says get/page2。

htm， and then what comes back is HTML。And that is a markup language that describes how this page is supposed to be shown。

So let's say that we wanted some more detail on how this really worked。

RightLet's say we want to write a web browser and we want to be a good citizen and we want to talk properly to the web。

 Well， we would go back to the IETF， the Internet engineering taskask force。

And we would go grab the document that says， hey， if you want to write a browser。

 this is what you do。😡，This is what you do if you want to write a browser， go grab RFFCC 1945。

 which is the hyperpertext transportport Pro version 1。

0 Now I'm sure there's more complex superseded versions of it。

But if we read it and read it and read it， we spend a lot of time， we'd get down to section 5。1。2。

 and it would say if you are making a request for a document， this is the request line。

 it has the letters GET， followed by a space， followed by the URL you're looking for。

 followed by a space， followed by the version。Okay， so that is the rule。

 that is what you're supposed to send down this connection。

It'll give us some more examples on page 24 and so we could read all this and we could write a web browser。

But what we're going to do is we're going to fake being a web browser， we're going to cheat。

 we're going to hack it。We're going to pretend to be a web browser。

 we are going to send the commands to the web browser。

Now I'm going to do this on a Macintosh you could also do it on Windows if you install a Tnet client okay so the key is you install a Tnet client Now most people would say Tnet is insecure and it is it's a very old protocol because all it does is it opens a TCP connection to a host on a port that I specify and whatever I type goes across that TCP connection so it's a great way to hack especially older less secure protocols so because HtTP is generally a public protocol it's not really highly protected so it's much simpler to hack it hacking secure protocols is requires writing software rather than typing commands So if you're on Windows you have to install Tnet TL N ET。

So what I'm going to show you in a second is I'm going to show you hacking and I'm going to tell Me to www。

doctorchuck。com port 80， what I'm saying is connect me to this server on the internet。

And connect me to port 80 because I want to do HDP connections。And then I will send one command。

 I'm going to send that command， and then the web server will give me back the page。

It's probably easier for me to just do it。So let's take a look。I am going to simulate。

What the web browser does when it's requesting， well。

 actually you will go to the second page and when it's requesting the first page， it's doing a get。

For page one， okay， so that's what we're going to do， except now we are going to do it。In a terminal。

 so I'm going to type tellnet。Oops， I was like this wrong， T， E， L， N， E T， w w， Doctor Dash Chuck。

Dot com。40。ok。😊，So now I am connected to the web server on Drchuck。com。I could， for example， type。

You， what。Is up。Dude。Now that would suggest I have not read the protocol specification for the HTTP protocol。

 so I do not know that I'm supposed to type the word get here， I'm going to type yo what is up dude。

And it goes。You are not from my country， you are not from my planet， I do not know what you said。

 of course that the way web servers are saying this is they're saying bad request your browser sent a request that this server could not understand it is the request header is missing a colon separator you do not comply。

 go away。But we did talk， it just told us that。Whatever we were saying is gibberish to it。

 and that's okay because we have read the document and so we can do it， so let's do it。

So now I'm going to do a tellnet to Dr。chuck。com on port 80， go to Dr。 Chuck。

Hook onto port 80 so we can talk to the web server。And now I am going to behave。

 I read the specification I'm going to type。G T， get space one space， HttP con slashlashwww。 Chuck。

 co。Slash page 1 dot H T M， H T TP space 1 dot。 I think there's a slash there。 Oops， oh， no， no， no。

 get it right。 Juty right， slash 1 dot 0。 I think I got that right。

So that is what I'm supposed to type if I am a real browser。

 and I have to actually type another new line， so I'll type another new line。😡，And now， whoa。Oh。

 I gave it the wrong page。 look， look， look， look， look， look。I wanted to do。

 I told it to get page at H TM。 So let's do it again。 do it again。 I'm not very good at this。

 My browser is much better added。 So I type get H TV calling slashlash dot doctor dash Chuck dot。

Chuck。com s page1。hM。Space H TTP slash 1。0。 I believe that's it。Let's hope I got it right this time。

 and then another enter。

![](img/717453ba6088343d27d38bf6f33aad7d_5.png)

耶。I got it。So this time I you know I type this， then I type this Now it gave me some header information saying things like。

200 okay means I like you。What the time is， when this file was last modified。

 it's an HTML file and it actually shows me the HTML text。And so we have just hacked a web server。

You can do this to like Facebook。com and do a get。If you get the right thing， it'll give you stuff。

 you could go to various sites， you can fake browsers。Now。

 you're only going to get so far because at some point。

 these servers know that you're not a browser because the browser actually sends a little more stuff than what we just sent。

 but youll get the picture。 Okay， it's a protocol where we have rules。

 And if we type the right thing。If we type the right thing。

 we know what the specification tells us to type， we are rewarded。

With the information on that server， if we comply with the server's request。We can talk to it。

If we know how to we know what port to talk to and we know what protocol to talk to that port。

 we can write a client that meets the needs of that server and extract the data。So this is， I like。

 I like command lines， I like sort of old school user interfaces， and this is a scene。

From one of the Matrix movies。That you may recall， I can't put it in here because of copyright requirements I might have the URL or maybe students will come up with the URL。

 you can probably search for the Trinity hacking scene。

 people put it up and then it gets taken down and someone else puts it up。

So let me tell you a little story about this scene。

 this scene was actually written by a former student of mine who worked in all three matrix movies doing IT work on the movies。

 and they were in Australia shooting the second set of three movies and he saw this scene and the scene was supposed to use a minority report style way for her to hack into the power grid and shut it down he said。

That's not the way that you hack into computers。All good hackers use a text based interface。

 some old thing， and that's a throwback interface。So the whatchaski brothers told him。Rewrite it。

So we actually downloaded the exact hacking software it's called EndMap。

 which stands for Network Maap， it is mapping the ports。

 it probes the ports and sees what's on the ports， see what version of the software is on each of the ports。

 figures out what the weaknesses of those things are， and even automatically exploits the weaknesses。

So he wrote a script that downloaded this thing that automatically breaks into computers， by the way。

 the good guys use this and the bad guys use this same thing。

 good guys use it to test all the computers on their campus and make sure that they're okay and the bad guys use to break into the ones that the good guys aren't smart enough to fix。

And so this was kind of cool and the people who wrote EndMap were really quite amazed when they saw the movie。

 they even figured out what version it was and things like that。

 and so it actually triggered a series of follow on scenes that used actual real hacking software。

 endMap hacking software。I don't know if we've got a URL for this or not。

 whatever our URL I come up with， even the one that endmap people come up with。

 whatever it is it goes away because of copyright， but you can find it because someone always puts it back up so okay so。

You can go and maybe the Nmap people will know it or maybe you just have to search for the Trinity hacking scene。

 so you can use Teleelmed and you can hack legitimately hack a web server。

So basically the application layer is a rich place and there's lots of things that happen in the application layer。

 we have this pipe abstraction it's kind of like a string with two tin cans and we can shout into one end and stuff comes out the other end later we'll talk about adding security to that。

And we use these port numbers to allow multiple different servers or services on a computer that we can connect to。

So we've kind of now reached the top of the architecture of the internet。

 we've talked about ethernet， the link layer and the fiber and all the diverse wireless。

 all the wonderful things that happened there， the internet layer。

 which is this kind of geographical hopping thing that's unreliable。

 the TCP layer that retransmits automatically if necessary， and then the application layer。

 which is what we do with all this networks， it's really impressive that this came out of research work from the 1970s and that most of the architectures that were really present。

 most the ideas of the architecture from the 70s are really still present with us today。

As the NSF net came out， these architectures evolved a little bit the last few tweaks。

 and there have been tweaks going on ever since， but really the last few critical tweaks happened in the late 1980s。

The啊。The number of web hosts。Or the number of hosts on the internet goes from six in 1969 to sort of a billion in 2011。

 and it's pretty impressive that roughly the same architecture that was designed with six computers is still mostly functioning in mostly the same patterns。

All these years later with the billions of computers。And so if you start looking at the network now。

 it almost looks like a live creature with veins and nerves and and it sort of almost pulses。

 And youd see things like you can search on the Internet for how the Internet reacted to Hurricane Sandy when like New York City was just like shut off for three days。

 Internet just kind of like。Roouted around it。 Yeah。

 a lot of stuff went across the Atlantic Ocean from New York City。 And yeah， I found different paths。

 And， you know， yeah， New York was down， but the rest of it wasn't in many ways， pretty amazing。

 And we certainly see other situations where governments try to shut the Internet down by going into the server rooms and shutting off you know。

 what they think is the only connections。 But and more connections pop up。 And so it's。

 it's very much a almost a living thing。It's billions of computers and hundreds of thousands of routers。

 and it's hundreds of millions of simultaneous connections going on all the time。

 including the one we're doing right now， probably。边。It's trillions of bytes of data moving across。

And it's。😊，It's not perfect but it kind of works。You can think of it as like the largest collective engineering thing that we've done together is humanity。

 We built this。 It's all one thing and yet it's so many different pieces。

 and we just kind of keep gluing them together and gluing more things on more things。

 And it was it really was created almost like life itself。 It's very organic。

 It's designed to heal itself。 rather than be perfect because things that try to be perfect are fragile and they break too easily。

 but things that are designed to heal can heal。 and you're never perfectly correct。

 You're never all the way up and you're never all the way down。

 And so that's what's interesting about the Internet。Yous good the wrong way。

And so we kind of come to the end of this where we started out with like machines and pulleys and gears and spraying oil at Bletchley Park and typing a few characters on our keyboard to this thing where we sort of just take for granted that we can watch basketball anywhere on the planet just with a couple of swipes of the key in a sense it's just that same human urge to communicate at a distance。

And so the last thing that I'll close with is another video from Van Jacobson Now this is about a technique he calls content centric networking。

And not everybody agrees with Van Jacobson on this， you can ask people and they'll， oh。

 that's a good idea。I don't present this as the future。

I present this more to get you thinking that there is a future that might be different than the present。

 that what I just told you that seems。Seems like， oh， it's perfect and in Vince Surf in 1969。

 he figured this out and it was the perfect thing， right？

The answer is it might not be and we as engineers and we as the people of the internet。

 we must understand that in 20 years it might be all different because 20 years ago it was all different and 30 years before that it was different yet again。

 and so nothing's perfect and so we should never be complacent and assume that what we have is trivial or perfect or even the right answer so we should continue to question and so it's really interesting to hear again from Van Jacobson who sort of did this great innovation in 1987 that saved us and yet he thinks that these are issues and their issues that need to be saved again。

And I think in many ways he's right， the question is not so much whether he's right or wrong。

 the question is what will the ultimate solution that we pick be produced so take a look at Vanance Jacobson and what he is thinking about as terms of the issues in the future that we're going to need to solve when he talks about content centered networking。

