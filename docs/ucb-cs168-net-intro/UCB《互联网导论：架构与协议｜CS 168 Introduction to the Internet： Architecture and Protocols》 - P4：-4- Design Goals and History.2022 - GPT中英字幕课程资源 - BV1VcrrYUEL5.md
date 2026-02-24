# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P4：-4- Design Goals and History.2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Okay。Good morning everyone， thank you for br it in the heat。Let's get started。

 So today's lecture for today's our last lecture on kind of this broad overview of the Internet and just a quick recap of where we were we were in our topdown approach to understanding how the internet works We said there were three major tasks defining the problem which we said was very simply to transfer data from one end host to another and then decompose a breakdown the jobs that you the tasks that you need to implement in order to get the internet working and we had walked through that and what we had arrived at was a breakdown of tasks that looked like this where we said we have five layers。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_1.png)

At the very top， we have applications。 That's the application layer that's built on top of having reliable data delivery。

 So we're not talking about packets yet。That builds on top of this global best effort packet delivery。

 So we've moved to packets and we've moved to best effort。Which， in turn。

 builds on top of our best effort， local packet delivery， which。

Bus on top of just physically moving bits， putting bits on a wire。IBefore moving on。

 I wanted to spend a little bit of time expanding on this distinction between global and local packet delivery because the last time around。

 I think I saw a few confused faces， and it can be tricky to get in the first pass through this。

 And so here's what I mean by this distinction between local versus global delivery。

 So let's say we started with you know a picture very much like the ones we've been looking at throughout we have Endhos connected by switches。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_3.png)

In practice， you'd be using different link technologies to build those links and switches。So。

 for example， in this particular network， there's a portion of the network that is made up of ethernet links。

 Ethernet is a particular link technology。 I'm sure you've heard the term before。

But then you might have a portion， for example， when you're going across a long distance。

 you might have a portion that's built out of some kind of optical technology。

 So OTN or optical transport network is one such technology。

 You're not expected to know the details of what OTN is or at this point， even what Ethernet is。

 Just think of it as it's a particular type of link technology。

And then as you go further in the network， you might have more ethernet links and you might have some cellular links and a cellular network at the edge。

And so when I think about going through from one host to the other。

 each one of these link level technologies quite often has its own way of doing addressing and routing or having a path through just that portion of the network that is made up of that link technology。

So here in this example， you could see you could have a path going from that host there that is going through the ethernet portion of the network。

Then there's a separate portion that's going through the optical。Portion of the network。

 And then down there again， I have a different Ethernet network。Okay。

So in each of these portions of the network， I have a link technology specific way of getting a packet or getting data from one point to the other。

That's what I mean by best effort， local packet delivery。

That ethernet network at the top has no idea how to get a packet all the way through to the destination。

 but it knows how to get a packet across a series of ethernet links。 It only speaks ethernet。

It doesn't understand how to speak the optical technology。Okay，But that is best effort。

 local packet delivery， a across， a particular packet using some link technology specific way of getting a across that network。

嗯。And if you remember the very first lecture， we said the Internet interconnects networks。

 That's what we mean。 It's going to interconnect that ethernet portion， the optical portion。

 and again， that last ethernet portion。But each individually only knows how to Ethernet only knows how to go across an ethernet network。

 optical only knows how to go across an optical network。

 so we need another level that you know can take that ability to deliver packets across an ethernet network and the ability to deliver packets across the optical network and then again。

 the ability to deliver packets across the Ethernet network。

 We need another layer of functionality that's going to be able to take those capabilities and stitch them together into an end to end path。

And that is what the network layer does。 That's this global end to end packet delivery that Ip implements。

And it implements it by using what each of these link level technology networks give you。

That's a large part of the power of Ip is It doesn't reinvent the wheel。

 It doesn't say I'm going to re do link technology and every single network。

 It knows how to stitch them together。I haven't told you how it's going to stitch them together。

 So you don't have to know it at this point， but that's the breakdown of tasks。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_5.png)

So that's how we came at this particular layering architecture。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_7.png)

Does that make sense， any questions before I move on？Okay， so moving on。

So what we've done is we've broken down。This end to end task that the internet has。

 which we start with applications talking to applications all the way down to bits on the wire。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_9.png)

The next。Step we have to consider is how how are we going to actually tie those pieces together and how are we going to make all these layers work end to end。

And for that， I want to take you back to this example we had in the last lecture where we said。

 you know， we had this analogy of CEOs want to talk to each other and the way they talk to each other is by going through these layers that now I hope you can relate to internet layers。

But that at each layer， we said that peers understand the same things。

So CEOs understand what CEOs say the aide understands what the other Aide says。

 and FedEx the delivery infrastructure， they know how to speak to each other。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_11.png)

It's going to be very much the same on with our Internet layers。 So peers。At the same level。

 are going to be able to understand each other。And the way they're going to be able to understand each other is because were going to define a protocol。

And if you go back again to our first lecture， we talked about what a protocol is。

 but so the communication between pure layers on different systems is defined by these protocols。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_13.png)

And a protocol going back to lecture one is simply a specification on agreement between two entities on how they communicate。

 It's kind of like speaking the same language。But more formally。

 it means that there's a syntax for communication。That syntax tells you this is in those headers exactly what fields you should expect for that protocol。

Right，So for example， you'd say I have， you know，64 by header。 the first 32 Bs。

 tell me what the destination address and so on。 So you're going to specify exactly what the format of that header is。

And we're also going to define the semantics， which is when you receive this packet。

 here are the steps youre expected to take。So every protocol definition is going to come with the syntax and the semantics。

They are lots of protocols as you've seen we have lots of layers so it's reasonable to expect at least one protocol at each layer in practice theyga far more and we'll get into that in a minute What you should know is that protocols exist at multiple layers some of them are actually implemented in hardware。

 some of them completely in software there's a wide variety of them they tend to be defined and standardized by some standard body。

 some international standard body the most common one that you'll see is the ITF which is the internet engineering task force so it's a body made up of representatives from companies from research from pretty much it's open to anyone who wants to participate and in those committees they define these protocol standards。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_15.png)

So here's just one snapshot of protocols you can expect to see at different layers。

Some of these should look familiar to you HGTP a level 7 protocol， Ethernet。

 what we just talked about is a layer one， layer  two protocol。The network we've talked about， IP。

 TCP， UDP layer 4 protocols。 There are a few things to observe here。

 One is that you can have different protocols at the same layer。This might seem surprising to you。

 All it means is that you have a different implementation of the task that had to be implemented at that layer。

And if you think about it， it makes sense。 You'd have an ethernet protocol at layer 2。

Because you want to know how to speak over Ethernet links。

But you also want to speak over optical links。 So you have an OTN protocol that knows how to speak over optical links。

At layer 7， if I look， you have HTTP as a protocol that we use for web transfers。

 It's used on the web。But we also have a protocol NP that's used for network time synchronization between two entities over network。

 That's the network time protocol。But it's still an application level protocol。Similarly。

 if I look at at layer 4， the transport layer TCP， which I'm sure many of you have heard of。

 what it does is itll take data from the application， turn it into packets and implement reliability。

 make sure that all of those packets are reliably delivered between the two end hosts。

UDP is another transport layer protocol that does the same thing in terms of taking data and converting it into packets。

But it doesn't worry about reliability。 So it provides no reliability guarantees。

So if you're looking at this and you thinking， but you know。

 we said that protocols work because you have to speak the same language。

 we do still have to enforce that。 So I cannot， for example。

 have an ethernet send talking to an O TN receiver。 that's not going to work。

I can't have an HTTP client talking to an NTP server。 That's also not going to work。

The other thing you might worry about wonder about then is， you know， if you look at this diagram。

 I told you one day will use。The functionality provided by the lower layer。But now。

 if I have multiple possible implementations of the lower layer， what am I talking to。

And that's a choice that at every layer you will make。 So， for example。

 H TTP chooses to build on top of TCP， typically。So that will be a particular implementation。

TCP builds on top of IP P。IP might have to build on top of ethernet so it can talk to an ethernet network and at the same time know how to talk to an OTN implementation so that it can also connect to an optical network。

So there's no inconsistency with having multiple protocol implementations at the same level。

And typically you'll hear the term network stack， you can think of it's kind of an informal term but you hear it all the time。

 it's an instantiation of this protocol stack， it's an implementation based on implementing a particular protocol at every level in the stack and it's a stack because we're combining those implementations into a path by which network traffic is going to be processed。

There is one crucial thing though in this picture， which is we only have one IP protocol。

 So at the network layer， there is only one protocol。 It's IP。

 That's the glue that stitches together all of these other networks。

And all of the applications on top。Any questions？有。Yeah。Any others。 And again。

 these are all examples。 I'm not expecting you to know the details of any of these。

Some of them will dig into， but others we won't yeah。谁？Yes， great question。

 So IP version 4 and version 6， both are different versions of the same IP protocol。But again。

 IPV4 will talk to IPV4 and IPV6 we' talk to IPV6。I'll get back to that in just a second。

 any other questions？

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_17.png)

Okay so we have three important properties you should remember of layering。

 each layer depends on the layer below。 What that means is it uses the interface or the functionality provided by the layer below。

And at the same time， it implements an interface or functionality that is useful to the layer above。

It only interacts with the layer above and the layer below。 So that's strict layering。

And you can have multiple versions in a layer。 We talked to that at length， but only one IP。Protocol。

 that's the only protocol at the network layer。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_19.png)

It's why layering important。 What do you think。We said it's a form of modularity。

 It's a particular form of modularity。 Why is this a good。Form of mod loading。要。

You can abstract away the details of everything other than the layer underneath you pretty much。

 Why is that good。Why is this kind of strict separation of concerns useful。You know it。

 This is every time you get code。Right， so it's key what this enables is innovation。

 basically that innovation Act can proceed mostly in parallel。If you're at the application layer。

 for example， and somebody changes their network form。Optical generation one to satellite Gene2。

 you don't need to care。 Imagine if you had to reimplement your browser or reimment Skype or whatever your favorite application every time somebody changed a link on the Internet。

 It would be a complete disaster。But instead， with this kind of strict layering。

 you can have innovation that proceeds almost independently in individual layers。

And this is doubly crucial because the Internet is a vast system implemented by a huge variety of vendors and players。

 and so this allows very different communities to pursue innovation independently。

 The physicists who are figuring out how to build better links don't have to worry about security issues in your browser or any of the concerns that application developers might worry about。

And we see that because that's exactly what has LED to innovation at。

 I would say most levels in that layered architecture。

 We clearly we all know and enjoy a large number of applications。

 There's also a large variety of linked technologies these days， we have satellite that's coming up。

 We have millimeter。 We have all kinds of technologies that just didn't exist 40 years ago when we built the Internet。

The one layer that I would say is the exception to this is， you know as you might suspect。

 given we have only one， it's the IP layer， that network protocol layer and evolution of the IP layer has been painful over the years。

 so even going from IPV4 to IPV6 has been a 20 year process and we'll talk about IPV6 a little later in the semester。

 but it's not a terribly ambitious protocol it was not a huge change over IPV4 and even then it's taken many。

 many decades to actually roll it up。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_21.png)

Questions。Okay， so now， you know， all we've done so far is decompose the problem。

 We haven't said exactly who's implementing what and how。 Okay， so we're going to get to that next。

 And here the question is really distributing layers across the network。

 If all we were doing was taking those layers and running it in you know your laptop or somebody's server。

That we won't worry so much about exactly how we are assigning tasks。 So who's gunning what layer。

 The real challenge in the Internet comes because we have to partition that functionality between the end host and the network。

 and that is that partitioning is really going to determine what the network implements。

 What is the job of the network。Okay， and so that's what we're going to do next。

 Let's first think about the end host。And I want you to tell me what do you think which layers get implemented at the end hosts。

 And now， remember the layers， you know， the two ends of it。

 you have the application and then the very lowest layer is just the ability to put bits on a wire。

 So which of these functions do you think the end hosts has to implement。The application， for sure。

What else does the end host have to be able to put bits on the wire。You're nodding your heads。 Yes。

 if I stick an ethernet cable into my laptop， I expect my laptop to be able to actually send data over that Ethernet link。

 which means it must know how to put bits on the wire。

And so bits arrive on the while at your laptop or at your phone。

 which means you have to implement L1。And we also know we're running applications at the end host。

 So we know we're running L 7。We have a strictly layered architecture。

 This means you have to implement all layers at the end host。

All the way from picking bits up off the wire to handing it to an application。

So all layers gone at the end host。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_23.png)

What about when we think about the network， if I walk through that reasoning again， I would say。

 okay， it's coming coming in on the wire。 I have to implement L1。

I have to be able to move packets from one switch to another across links。 So I have to implement L2。

 and I have to do end to end delivery。 That is exactly what the network's job was。

So I have to do L3 as well。And we're going to talk about this at length。

 but the network does not implement layer 4 and layer 7。 so it doesn't crucially。

 you know no one expects the network to run applications that was never really on the table。

 But the important thing here is that the network does not implement reliability or reliability data transport。

And this is actually not what the first education of the Internet did。

 So this was an important change when they changed from Al。

 which was the government's first attempt to what is today， the Internet。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_25.png)

And so this gives us a very simple diagram that looks like this at the highest level where the end hostse。

 you see all five layers。😊，And a switch。Or routeer is implementing L1 to L3。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_27.png)

I'm going to dig in on both the end hostst and the network view a little bit more closely。 Now。

 Let's start with the end hostst。 right， So we said the end hostst， you。

 think of this as your laptop or server implements all five layers。What does that actually mean。

 Let's open up that end host if you look inside your laptop or your machine to first order what you have is your network interface card。

 This is where you go stick your cable in。Why again我要 lips。

And then you have things that come in on that network interface card get handed to your operating system。

And in particular， the networking stack within your operating system。

 what I mean by this are the portions of your operating system that handle processing traffic between applications and the network interface card。

Because the operating system does a lot of things。 So the networking stack is the relevant portion for us of the operating system。

And then， it also hands。So hands packet it up to the application。

 So we have these three major components。Within your end host。

Should not be too surprising when you think of which layers get implemented where we're going to put the application。

 layer is going to run at the application and the physical and data link layer going to run on your network interface car。

 This is really the job of putting bits out onto the wire or packets out onto the wire。

 Where do you think your network and your transport layer should be implemented。Video。哎。

In the operating system， any guesses on why and we now actually I should say in the realm of not you have to do it this way。

 where're more in the space of this is how common practice， Most systems you could look at。

 this is how they built。Why would you put the network in transport。P later into the operating system。

That's great example so you want to look， can I say you want to manage across applications。

 so you have all this traffic that different applications want to send out and you want to be able to maybe do something intelligent with that priorizing one application over another or making sure one application is not hogging all the traffic or the bandwidth。

Anything else？嗯。RightSo that's you know the primary driver， which is this is a pretty general task。

 Imagine if every application you would， every time you had to send write an application。

 you have to worry about how do I take this file or this key value so stole or this recording and I have to chunk it up into packets and then I have to worry about how to make sure that every packet gets delivered to the end host I have to implement a liability。

It would just be a lot of work for every application to redo it。You could。 Nothing stops you。

 but it's much more convenient to have that functionality in your operating system to implement it once in a general fashion。

 And it's a general service that all applications can use。In some sense。

 this is the role of the operating system is to have services and abstractions that are useful for applications built on top of it。

So that's why we have typically the network and the transport layer implemented in the US。

 It's not the only way to do things。 you can certainly find systems out there that either put this functionality at the application layer or even increasingly these days。

 for example， in data centers that push that functionality down into your network interface code。

And the reason they do that is simply to shrink the footprint to not consume CPU resources on doing network and transport layer processing。

Any questions on the end host？There is another trick that you have to think about when you're looking at the end hosts。

 So let me。Ask you to think now about， you know， that a packet is arriving at this end host。

And we said the packet contains the destination address。 This is the address。

 the unique address of this host on the Internet。This is what allowed the packet to make its way across the Internet and reach listen end host。

 Now the packet arrives at the network interface card。

 Let's say the network interface card does something like it raises and interrupt the operating system and sucks the packet up into the O from the NA。

And now the bucket is sitting at the all pleaing system。How should when this packet arrives。

 how does the operating system know which application it should hand this packet to。行。But exactly。

 So there should be some information in the header that allows the Os to know which application this packet has to go to。

In everything we've talked about。 So I haven't told you about this piece of information so far。

So you didn't actually have enough information to know how this packet makes it to the application。

 So now what we're going to do is introduce this concept of a port that in the header。

 there's going to be a port number that identifies which application you have to send the OS has to send the packet to。

In particular， that port identifies the attachment between an application and the operating system。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_29.png)

So let me just， this can be pretty confusing so let me clarify one thing in networking we have two different types of ports and it doesn't help in when students are trying to not be confused。

 so we have two different types of ports。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_31.png)

One is physical ports。 If I take a switch or if you take your laptop。

 you have the physical port where you connect a link to that device。

That's the ports I think many of us are familiar with。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_33.png)

But there is also a logical port， the operating support system support concept of a logical port that is very different。

 has nothing to do with the physical port on the switches。

The analogy is that this is where the application connects to your operating system。

That's why we call it a quote， but it's an entirely logical entity。Okay，So physical port。

 the thing on your device where you go plug in a cable。

 logical port where your application plugs in or connects to the operating system。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_35.png)

And so in your next section， you're going to talk about something called sockets and how this relates to ports Sockets is the operating system abstraction or API that allows an application to connect on application process to connect to the networking stack or your operating system。

So you'll study this interface in depth， but the way this works is that when an application wants to connect or wants to access the network。

 it going call it's going to open a socket。That's the abstraction the OS provides。

The O S is going to associate that socket with a unique port number。Not the physical port number。

 This is the logical port number。And so now when in fact port numbers get carriedgged in packets。

And so when a packet arrives at the O， it says。This is the port number。

 It looks it up to see what socket is associated。 It hands the packet to that socket。

 which is a way of handing it to the application。And you're going to see sockets in the interface。

 Socket interface in much more detail。 What I do want to focus on in this lecture。 However。

 is the implications for the packet header。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_37.png)

So far， we've said that a packet。Has to contain the destination address。

 This is the information the network needed to get that packet to your end host。Now。

 I'm telling you that package should also contain a destination port。

And this is used internally within your end system by the O to know which application to hand the packet to。

Any questions？行。It' it's a process。 So from the point of view of the US。

 it doesn't actually care what applications is running in that process。 It's a process。

 It just knows which process to hand it to。Typically， if you had a different， yeah。

 you would be writing different server applications for different websites to serve different applications。

 and then they would bind to different ports， but you could also build it either way。

So I think we went over this when a packet arrives at the end host it's delivered to the socket。

 which is a process associated with that packet's destination port。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_39.png)

So really what we've。Created here is a role for the operating system where it acts as an intermediary between the applications and the network interface card。

So the application has a very clear task， it thinks about data。

 it thinks about those key value throws， about files， about images。

 that's what the application is concerned with。On the other hand。

 the network interface card or the driver is the code that runs on the or interacts with the network interface card hardware has a very clear task。

 It has to think about packets and the link technology it's sending those packets over。

The O or the network stack within the operating system is what mediates between those two。

 what converts between those two。 It takes that data and converts it into packets that the N can send out。

That's the role of yours and the network stack within yours。 It's a very important role。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_41.png)

So I'm going to recap at the end of we have L 7， typically part of your app， L3 and L4。

 typically part of the OS and L1 L to typically implement in your network interface card。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_43.png)

Any questions before I move on to。The network。来。That's a great question。

 And I believe you covered that in section again。 But typically。

 the way this will work is that a server， the server side。

 the member server listens for connections from clients。 So a server will connect on a wellknow port。

 Po8 is probably the port you've heard about。 A client can locally then pick any port at once。

Connect to that well known port。 So that's how it knows which port to send a message to on the server。

 The server， when it receives the message from the client， knows what port it sent it on。

 So you just have to flip it around and you know how to get back。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_45.png)

Toplan。So moving on to the network side of things now so again recall we said we have this picture。

 all five layers at the end hostst， only layer one to layer3 in the network and we said layers on either side interact with the peers corresponding layer these are on the same protocol。

 We're going to dig down into that a little bit more now just to make this picture more useful and interesting I'm going to add an additional routers so you can see that that interaction is not just between end hostst and routers it's also between two routers。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_47.png)

And I'm going to start。Looking at what protocols we are running at each of these layers now。 Okay。

 so a very simple protocol diagram would say at the these are examples。 Again。

 these are not the only protocols you could be running。 These are very typical protocols that we run。

So at the application layer， we could be exchanging HGTP messages。Again。

 I'm not telling you at this point how that message is actually flowing through the network。

 I'm just telling you what message or what protocol both sides understand。

So what does it mean now that you know， we've talked about。Ptocols and where things gone。

 What this means is that the h T TP protocol implementation。

 that code is gunning at layer 7 at the two end host at the applications。

 your gunning code that implements the h TTP protocol。

 What that means is it knows how to create h T TP messages with the right format knows how to receive an ht TP message and pulse it correctly and so on。

Beneath that， we have TCP by streams。 Don't worry about what the term B streams means。 It's just。

 we'll get to it much later in the semester。 It's just how TCP。

 the terminology we use for how TCP thinks of data。So TCP by stream， again。

 this means you have the TCP implementation that's scanning in your OSs at both end host I exchanging TCP by streams。

When we get to I， we have this IP， the code that understands how to process IP packets runningning both at the end hosts in your O and in the switches and routeers。

 So now when we talk about peers。That speak the same language。

 Notice it's going not just between the end host， but also in the switches。

And the same with Ethernet， until， finally。And then the same with Ethernet。 And then below that。

 we're going to actually put bits out on the wire。 Again。

 so far I'm talking about logical communication。 what both sides understand。

What would you do if I said that actually that link was a transport， optical transport link。

 So it's an optical link， O TM。What would you change in this picture in terms of。

What protocols are running well。别。You're right。 You wouldn't have to change anything at the IP layer or the TCP layer or the HTTP layer。

 What about at the ethernet layer between those two routes。So I told you Ethernet。

 I can't have an ethernet send talking to an OTN receiver， and Ethernet doesn't understand OTN。

What would I do。你。有。Exactly， so the routers would implement both。

 And this is where it starts to be crucial that you can have multiple data protocol implementations at the same layer running。

Together on the same device， even。So here you would be running the OTN protocol implementation at those two routeers。

And those are the implementations that would put packets out onto that optical link。

You would also be running the ethernet protocol because they have to know how to speak to the ethernet links that are used to connect to the two end host。

So we're running both protocol implementations。Some any questions here。Within a routeer， yes。

 if you had a route， you know， and not all routers do this。

 but certain routers Porters will do this where they speak one。

 they have a particular type of interface on one side and a particular type on the other side。行。Yeah。

 hold on to that question。 We're going to get to it。

 I haven't told you exactly how a message flows through this yet。

 I've just told you what the two peers at particular have to understand。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_49.png)

Not how how to make that work。 So just to get to exactly that question， you。

 and this should become clearer， but I'll stop again and ask you if it is clearer。

I want to recap how we talked about physical communication。 So so far。

 what we've talked about is logical communication。Ps I exchanging messages that both sides understand。

 I haven't told you how those messages actually get there。

 That's the actual physical path that a message is going to take。 So we're going to do that now。

 I wanted to win you back to that analogy we had again with the CEO and the two CEO talking where we said you start with this letter this letter travels down the layers。

 So kind of down the stack then across the world and then back up the stack。

 that was the path of the letter。 And so we said that communication goes down to the physical network。

 That was the Fedex。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_51.png)

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_52.png)

Infrastructure in this that example。 and then goes back up to the relevant layer。

So now looking at that in the context of all layers， what that means is that this red line here。

Is the physical part the message is going to take。 It's going to start at the application on one side。

 Go down the stack， get out onto the wire， go to that router。 Go back up to the I P layer。Again。

 down， go out the next wire， up， down next wire， and then up the end host。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_54.png)

I'm now going to make this a little bit more complicated。

 but now you'll hopefully start to understand exactly how a message flows。

 Let's start to blow that up a little bit more。 So so far。

 we have been talking about that logical communication between peers。What does that mean。

 So here I'm going to start using these dashed lines to represent logical communication and solid lines to represent physical communication。

So we said we have these HTTP protocol implementations running at both end hosts。

So you have some application level message to send。

We also said HGTP builds on top of the TCP implementation or the layer 4 implementation。

At that system。 So the HttP。Code up there。 It's going to have a message。

 It's going to hand it to the TCP code。Just pass the message down or invoke the interface of the TCP code。

At that end host to the left。Same thing， passing it down to IP。

That IP logically is speaking to the IP layer in the other routeers and switch it。But physically。

 what that Ip layer is going to do is it's going to。

Send the message down to the data link layer implementation。In our case， that's Ethernet。

 that's gunning at that end host。And then that ethernet interface actually finally。

 is the thing that puts。Bits out onto the wire。So part of a message through this diagram looks like this。

While I started at the application level， I kept passing the message down the stack。

Then the message was transmitted over a while， and then it went back up the stack。

Important thing to notice here is what's going on in this router。系。

Where the message came in on the Internetthernet interface。Remember， I told you。

 Ethannet does not know how to talk to Otn。And it doesn't have to with the way we've wired these modules。

Ethan had just passes the packet up to IP。And then what is that IP module to do。

 it'll do something like it'll look at the destination address and say。

 if you remember that forwarding table， it'll say my next talk in this path is to go out over this OTN。

外。And that's why it hands it down to the O T N。Interface at the data link layer。

So there's no violation of layering here。 We don't have two protocols that don't understand each other speaking to each other。

Does that make sense？Right， so the HGTP message that's at the end host to the left。

Is effectively sending an HtTP message to that message to the HtTP implementation on the right。

 the end host At the end of the day， that's what we're trying to achieve。But in order to get there。

 it's not like HGTP doesn't have a wire to HGTP。 it has to go over that physical network at some point。

And the way it's going to do this is by passing it down these layers。

And I'm going to get to this in a bit， but each layer is going to add some information that helps the next layer down forward that packet on。

Yep。The OTN interface in this example is required because I have an OTN link。

Between those two routeers。 Thanks for raising that。I should have made that clear。

 The only reason I need that O TN interface and at the data link layer there is because I have an O TN link。

If I had a wireless link， I would have needed the Wifi protocol implementation。也。

 so the question here is， why did I have to go up to the I P layer。 And thank you。

 That's that's the crucial part in this picture。 So it's good to get it。

 Like the reason I had to go up to the I P layer。 Think about it。

 What if I did not have the I P layer。RightAnd I wanted to send a message directly from Ethernet to OtN。

In order to make that work， Ethernet would have to know what format or what interface O TN supports。

And so every link technology in the world would have to know how to convert between all possible link technologies。

Ethernet would have to know how to send a message to O TN。

 O TN would have to know how to receive a message from Ethernet and so on。

Instead of which what we're saying is the only thing that you need to know how to。

 if you're link technology， if you're Ethernet or ODN。

 the only thing you have to know how to do is hand a packet up to the IP layer and accept a packet from IP。

As long as we all know how to interface to IP， this can work。有。That's a great。

 What if that middle link was Ethernet， then you wouldn't have to go through IP。

 That's absolutely great because you will understand what's on the other end。

You had a follow up question。Saay the same person， okay。Other question， yet。Locally， as in a host。

What would look。2 end hosts connected to the same router。 Again。

 it depends on what the interface at the other end host was。 So if I got rid of the second router。

But I said the link between it。The first route and the last host was O T N。

 I would still need to do the conversion。 If it was Ethernet。

 I wouldn't have to go up to the I P layer。行。You could have。 So the question is。

 why is it an O TN interface， Could it have been in ethernet interface， typicallyypically。

 different links have different characteristics。 So for example， a wfi link is much lower bandwidth。

 and O TN link can be 100 tiabbit per second。 So the assumption in this example is the operator had a reason for putting a high bandwidth。

 low delay optical link in there。So， that's kind of。An assumption going into this picture。Yeah。Yes。

 so the question again is if that middle link was not an OTN link was an ethernet link。

 would I have needed to go up to IP。 The answer is no。

 because Ethernet would have known how to pass it between Ethernet。

 and I'm going to get to that explicitly in a few slides。有。Right。

 so this is jumping ahead to many lectures， which is how would Ethernet have done it。

 So within a link technology， Ethernet has its own addressing scheme and runs its own routing protocol。

 And so when you received the packet， you would have said。

 what is the Ethernet destination and do I know how to forward it。But in this case。

 there was no ethernet destination。 You had reached the destination。 You were done with Ethernet。

 So you hand it up to IP。If that didn't make complete sense。

 this should make sense when we talk about Ethernet later。Yeah。Right。

 so from the point of view of this ethernet。Interface here， you received a packet。 you're done。

And when you're done what you do， you take out the Ethernet header。

 which we're going to the next slides now and you send it up the stack， which in this case is IP。

So in the very first lecture， we said that the job of the Internet is to interconnect networks。

That it's a network of networks。 This implementation is exactly what makes that work。

The fact that you have IP there， if you look at the role of what IP is doing in this picture。

 it's interconnecting different link or different network technologies。And as long as we speak， IP。

Then we know how to jump between this Ethernet and OTN network。There's more。

 I haven't told you how I P has the information needed to know that it had to go out over that O TN interface。

 That's going to be the job of routing。 But that is exactly the role that I is playing。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_56.png)

So to recap physical communication。Are we， are we all good with that previous。Y。

 so to recap physical communication， we said communication goes down to the physical layer。

 a cosor network， and then up to the relevant layer。Okay。

So I've just told you what that physical path is。 I haven't told you how each layer knows what。

 what to do with a message and where to send it next。In going back to our CEO context。

 the way each layer knew what to do with with the message was through this notion of know taking a letter。

 putting it in an envelope， putting it in a Fedex envelope。

Every layer knew how to take something from a layer above it。

And then how to put it in a format or in a package such that the next layer knew what to do with it。

And similarly on the receiving side， like the aide knew that when you get the Fedex envelope。

 you open it up and you take the envelope， you open it up and you take the letter to the CEO。

RightSo each layer knows how to kind of unpack packaging and repack the message。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_58.png)

And we said， so communication goes down to the physical layer network and up。The layers。

 And at each level， we add some packaging。And the lowest layer。

 So that truck carrying the Fedex on group has the most packaging。

And the application has the least packaging。 It has the original message。

We're going to do the same thing on the Internet。 So at layer 7， the host。

 you take that application data。 And remember layer 7， we said was going to， for example。

 be implementing H T TP。 So you will add a layer 7 header to that application data。

 Youll add an H T TP header。This is what allows the HtTP Pu on the other side to understand what that message is。

You then hand it down to your layer 4 implementation or TCP。

TCP is going to put its own TCP header on top in addition to that HtTP header。

And then pass it down to the IP layer L3， which is going to put an IP。Head on top。

And down to the L1 L2， which is your data link layer and getting the bits out on the wire。

And then when you send this message along。The way occurs to the other end。

L 1 L2 is going to look only at the data link。 Layer header knows what to do with it。

 It's going to then take it off。Send it up to the Ip layer。

 IPp layer is going to look at the Ip header。 Send it up to TCP， and so on up。

Till you get to the application there。So that header is what allows these peer implementations to talk to each other。

And if you look at each of these layers， it's only looking at the header that's relevant to itself。

So the data link never looks at the HTP header， for example。

The I layer is not looking at the HttP header。It's only looking at the information in that I head。

We haven't yet talked about what goes into those headers。

 That's what we will be doing over the semester。So packets contain multiple headers。

 if you actually went and looked at a packet on the while。

 it would have all of those headers stacked one on top of the other。That making sense。行。嗯。Yeah。

 so I I I don't have just to not make this diagram I even more complicated。

 I don't have the routeer here。 What the router would do is exactly the same as the end host when it receives the full。

Packet， it would， the Ethernet implement going back to our previous example。

 the Ethernet implementation would look at the ethernet header。And then it would say， okay， I'm done。

This was the Ethernet destination。 So it takes off the Ethernet header， hands it to the IP layer。

 The IP layer would do what we have talked about in previous lectures。

 It would look at the destination I。Addres， that's the address of the end hosts。

 would look it up in a table to know which interface to send it back on and then send the message back down。

To the optical implementation。Okay。It would never look beyond the IP there。态度。

So it never looks at a TCPO and H GDP。快正。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_60.png)

Any other questions？So here's an exercise， and you'll be doing this in the discussion section as well。

 is take the previous slide where we were adding and removing headers。

And think about this physical path through this complicated protocol diagram and ask yourself at different points。

In this path， what headers do you expect to see。On the bucket。

It's a great exercise by which to make sure you're following all this。So， for example。

 if I told you the I。Implementation at this first routeer。

What headers are on the packet and what header is that module looking at。

The answer in this particular case would be that the packet at that point has no L2 header。

Has no data link header。 It does have an L3， L 4 and L7 header。 So it'll have an IP。

 TCP and H TtP header。But it's only going to look at the IP header， the LP header。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_62.png)

Yep。Yes。They would be routing on different headers。

 This is a subtlety that I think will be clearer when we get to Ethernet， the Ethernet。

 if I had two Ethan and actually have this example right here。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_64.png)

If I had two ethernet switches side by side。They would be looking at Ethernet addresses and deciding to go out to the next interface。

 They would not be looking at I P addresses。Yep。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_66.png)

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_67.png)

It depends at which layer at at this point。In the doctor yes。It would have all the headers。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_69.png)

You would take off the the ethernet header。 So if we go back to here。

 if you look on the receiving side as you move up the stack， you're taking off headers。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_71.png)

So at this point， you would have the ethernet header。 You would take it off。 At this point。

 there's no ethernet header。 When you send it back here， this interface adds a sonnet。

I have sonic here， so it does。Precursor to Oium， a sonnet header。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_73.png)

No。So if these were both Ethernet， so let me go- this was I have these slides to explain a historical side note and then I'll come back to your question which is you know we've said switches and routeers are the same don't worry about it。

 historically the reason we had those different terms was that you could buy Ethernet switches and Ethernet is the most common type of switch that we see in most deployments you could buy an Ethernet Sw that actually did not implement the IP header。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_75.png)

The IP layer， It was just able to switch ethernet packets。

 It has its own protocol by which you learn about parts through an ethernet network。

 And it does this gouting on ethernet headers。And so we would call the these switches and the ones that actually implemented IP。

 we would call routeers。We don't follow this distinction anymore， because at this point。

 you can go look at any ethernet switch that's sold on the market。 They also implement Ip。So。Yes。

It has access。 If it wanted those bits are there in the message it received。

 It's just as per the protocol， it should not be looking at the TP header。

There are violations of this in practice， but the protocol IP protocol does not require you to look at the DCP header。

It doesn't。 It can only get you across an Ethernet network。

The minute you try to leave the Ethernet network， it doesn't know what to do。 Then you need I P。

Within one ethernet network， which defined as a set of interconnected ethernet links。

 you would run an ethernet routing protocol， spanning tree or some more modern form of ethernet routing。

 which we haven't covered yet。 So you don't have to know。

So I'm going to continue in this class to use switch and route interchangeably。

 just wanted you to know where that distinction comes in。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_77.png)

So review， were kind of done with our top down。View of how the Internet works， as you can tell。

This concept of layering and adding headers and so on can get pretty tricky。

 so make sure you understood it。 we have these five layers。

 all five of them are implemented at Endhos and only three of them are implemented in the network before I move on。

 Any last questions on that。对。It the question。 does every header have the same size， No。

 not necessarily。 It depends on how that protocol is defined。 So Ip， for example。

 has something called Ip options that could make the header be different in length。

 But you have to know how to。As an I implementation。

 you have to know how to figure out what the length of your head is。Any other questions？

Let me take a two minute break。And then we'll continue on with the question I want you to think about is。

 why is this particular assignment of tasks good？AndSo we've said these this is a breakdown into layers。

 And we've said typically the end host implement all five layers。 the network only three。

We're going to take a more philosophical look at this now to talk about why that particular partitioning has been very useful on the Internet。

Let's continue， and I'm going to try and do a speed end to end principle in 20 minutes。

So let's try to make this work So the question of why is this assignment a good one and a lot of what we're going to be talking from here on the kinds of lessons and terminology we use comes from someone called Dave Clark。

 he was the chief protocolcol Archect for the Internet back in the 80s so back in the 80s there was this committee called the IAB。

 the Internet Architecture board。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_79.png)

They were not a standards body， but they were there to offer architectural guidance to the people developing protocols like TCP and IPA and so on。

And Dave Clark was the chief protocol architect there。

 so he's not the person that invented TCP IP BGP， but he's very much the person that gave us the language and the rationale for why the internet works this way and so there two papers in particular that are classics when you take a PhD level class on networking these are the first two papers every class I know of these are the first two papers that you'll go read Theyre both beautiful papers they're actually very accessible if you want to go peek at them there's a link at the bottom The second paper which is the design philosophy of the Internet protocols is the paper we're going to be reading later in the semester。

So I'm going to cover。Kind of the argument that is in his first paper。

 the end to end arguments paper， I'm going to do a first pass to trying to explain what the end to end argument is。

 We're going to come back to it much later in the semester because I find when you actually understood outing and TCP in more depth。

 then you better appreciate what Dave Clark is trying to say。

 So we're going to do a first pass now and an in depthth view of the end to end principle data。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_81.png)

So what is the end end to end principle mean it's。Guideline， it's not a rule。

 You don't have to follow the end to end principle。

 but it's a guideline that guides the debate about what functionality gets implemented where in any distributed system。

 So it's actually a fairly。建那个哦，建那个。Guideline。For how you should be。

Partitioning and assigning tasks to different pieces in distributedate system in this class in particular。

 we are going to be thinking or using it or thinking about the functionality that a network should implement。

 What does the end to end principle tell us about what the network should or should not implement。

Even one step more specific， we're going to be thinking in this lecture about should the network implement reliability。

Should it be the job of the network to worry about reliability， So before I even go there。

 what does it mean or what do I mean when I say that the network should implement reliability。

You could implement reliability in a number of different ways。

 I'm going to give you one just so you have a mental picture。

 The idea is that the network is going to do a little extra work to make sure that the packets it's trying to send are getting to where it's trying to send them。

 It's not just going to send it out and hope it gets there。 So， for example。

 typically what this would mean is something like router 1 will send the packet to router 2。

And then it'll wait for an acknowledgement to come back from Gtatu saying， I got this packet。

 You can now send me the next packet。And it'll not just be， I got this packet。

 It's actually going to send something like a checkum。

 Is everyone comfortable with the idea of a check some。

So it's kind of like a hash or fingerprint that says this is the actual。Content I received。

 So it's going to send that check check sum back to one。 And so then one can say。Will know that， yes。

 to receive the packet。 Yes， it received the correct packet。And yes， I can now send the next packet。

 This is actually what the first iteration of。The out the alpha net。

 which was the first iteration of the Internet implemented。And you're going to do this repeatedly。

 at every link。So this would be one example of a network that's trying to implement liability if it did not get that packet it would resend the first packet。

And maybe it will resend it five times or so。And just to set the stage。

 there is nothing we can do to guarantee 100% reliability in all cases。

If I have a go ahead and forbid a nuclear attack that takes out half the Internet， I'm just not。

 there's no path between A and B。 I'm just never going to be able to send a packet to B。

 Or if B crashes， I'm not going to be able to get the packet to B。

 So we're not talking about 100% in all possible cases liability。 We're talking about things。

 the network can do to increase the chance that your data will get there correctly。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_83.png)

And so the question we have at hand for the next 20 minutes or so。

What do you think should the network implement reliability， Is it a good idea or not。

And to frame that thought， here's an example that Dave Clark uses。

 which actually came out of there when they were building these systems， which is。

 let's say that the task I have at hand is to。Do a pretty good reliable transfer for file from host A to host B。

The steps this is going to take is you the application at host A is going to read this file from the disk。

 from the local disk at that machine。It's then going to send it to the operating system。

 which is going to then send it out over the network to the other end host。

Which is going to send it up to the application and then at host B。

 you're going to write that file to your local disk。So we're taking a very end to end view here。

It's not just the network， we're taking the end to end view of what is this application trying to achieve？

It's actually trying to mobile file from stable storage， the disc on one host。To the machine。

 the host。The。Storage the disc on the other host。That's kind of end to end view of what we are trying to do。

And what do we want to achieve， as I said， we can't guarantee that the file will get there。

 But if the file， we would like the file to get there with a pretty high chance。

 a good probability of getting there。 And importantly， we want to make sure that if the file reaches。

 that it's the correct。It's not coted。 It hasn't lost some bids， and so on。

If O B believes it has the file， it should be the correct file。

And so you can imagine two proposals for how to solve this。 One is implement liability at every step。

So make each of those five steps we've talked about reliable。Individually。

And then we've stitched together these gl steps to have end to end liability。 That's one proposal。

If this is the path we go down， we're going to be saying the network should implement liability。

Because we want a pretty good chance that the network is sending。

Getting packets too and that it's getting them too without them being corrupted。

A second proposal I'm going to put on the table is we don't do any of the things in step  one。

 Instead， what we're going to do is have an end to end check。And if the check fails， post AV tries。

What does that end to end check look like And again， end to end。

 So I'm not just think about the network。 So if I want to implement solution 2。

 what I'm going to do is that the application at host B。After it has written。

The data to disk is going to rewe the data。Computer checksa to again。

 a summary of the contents of that packet of that file。Send that check some back to host a。

Hote is again going to read the file。 make sure that the check sums match。

And if the check sums match， it's going to say， okay， you have the right file。

 you can go ahead and use it back to Ho B。So I want you to think now about which would you do and think about it a little bit in two dimension。

 Let's think about it first in one dimension， which is correctness。

If I was concerned about correctly getting the file across。To host B。

Which of these solutions do you think。I would want。And to kind of refine that question a little bit。

 If I had solution 1， do I need solution2。if I had solution 2， do I need solution1。

Does solutionution one work， Does solution2 work。投s。Which would you do。So the point is。

 what if the suggestion is， what if the check， the transfer of checkum field。

So I dropped the message that said， here's my check on。 What would happen in that case。

So Hope would not be able to use the file。Is that okay， we said。You know， we're not。

Guaranteeeing delivery。If I neither of these solutions can always guarantee delivery in the worst case。

So let's go， let's think about solution。 Is solution one clear first。What we're trying to do。

 we have these five steps， and we're going to try and make each step reliableable。

Any questions on what solution1 and solution 2 are doing。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_85.png)

So I'm going to， let's look at correctness。 I'm going to assume everyone's clear on what these true solutions are doing。

The problem is solution1， you cannot make it perfectly reliable。What if， for example， I。Actually。

 you know， in this case， the application at host B after it received the file。

 but before it votedd to disk， it crash。Then Hoby， you wouldn't have received the fight。

That's one possibility， a worse one。 Let's say you had a component that had a bug。

Let's say you misconfigured your network or you misconfigured the application。

 So it actually doesn't。Gung the check some calculation。And so you sent a corrupt file。

And who we accepted it， because it。Because of a bug did not。Actually， check the contents of the file。

 So you had the wrong file。In solution 1。What you would have is actually that host B would accept a buggy file。

 a corrupt file。So even though I got the bits across， I got the long bits across。

And so unless you could make every single component。Guante that it is correct。

 that it's implemented correctly and that it has no bugs and that it doesn't fail。

 unless you guarantee those things， you actually cannot guarantee the correctness of the file transfer。

And so in order to guarantee the correctness of the file transfer。

 you're going to end up doing the end to end check in any case。

But that's the only way to actually make sure that the file that reached at hostt B is the same as the file that was at hostt A。

So you're going to have to do that check in any case， or if you don't do it。

 the endpoint could be in the incorrect state。 What I mean by this is that host B has accepted a file that is actually a corrupt file。

Does that make sense as an argument？ solution 2 can also fail。 right So what if you know。

 I host B send the check some to A A checked it and said it' all good。 And then it said， okay。

 you can go ahead and use it。And then that you can go ahead and use it Me it got dropped。

Then HostB is not going to be able to use the file。So you can still fail with solution too。

 You can always create a scenario where either of these solutions fail。

But there's no scenario in which solution2 will allow Ho B to have the incorrect file。

Because the only way host B will use the file is after it gets a message from solution from host A saying。

 yes， you have the correct file。 You're okay。 You're good to go。

So you can have host B in a state where it doesn't have a file or it doesn't have a file it's allowed to use。

 but you cannot have host B in a。So now where it has the wrong file and it goes ahead and uses the wrong file。

Does that make sense？は。Any questions on this line of argument。行。

The end to end check that we' are adding at the end is sent separately after you've finished the transfer。

So I'm not sure I follow your did I get your question guys？



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_87.png)

So what's the impact of failures here， And I mean failures。

 not just in the sense of I dropped a packet， but I actually gobbled the bits。

 I corrupted the packet。If in solution1， if you had a network failure or bug。

It actually LED to incorrect behavior at the endpoints。

ItL to the wrong set of bits being transfer transferred to B。

And so if you want to trust solution One， you have to trust host A has to believe that host B is correctly implemented and the network is correctly implemented。

 This is a huge assumption。 we never want to assume that other components are bug free。

 especially application code。 very unlikely that you can always assume it's bug free。

In solution to the endpoint semantics， however， decoupled from the network failure。

 The network can still fail。 It can still cover bits。But when it does that。

 it doesn't lead to incorrect behavior at the application there。Instead。

 the host day is only relying on the fact that it has a correct implementation。

It is possible that Hoier has a buggy implementation and it got the wrong check summon and accepted it。

But you， you brought on your own failure， in some sense， or youulete only on your own。

Implementation being correct。OkaySo the intuition for what Dave Clark building on that example。

 his argument for why the network should not implement reliability is that there are certain application requirements。

Like correctness， reliable transfer， correctly transferring the bits in a file， for example。

 or security is another one， and I'll get to that in a minute。

 but there are certain functions that you can only correctly implement them if you take an end to end view。

 if you implement them end to end。That was a final check sum that we're calculating on that file。

And so in those cases， what we should think about is the end system。

 if the end system must implement that functionality for correctness。 So in this case。

 the end system was doing that end to end check and retransmission。

 it was going to retry if the end system has to do that in any case because it's the only way to。

In short collectness。And if in implementing it， you achieve liability， then his argument is。

 we should not implement those functions in the network。Because it's unnecessary。

 and it adds complexity to the network。So this was the argument for why taking。

One should not require the network to implement a liability。 We can take it out of the network。

Does that make sense？Any questions on this？有。Yes， let me rerase that question。 It's a good one。

The scenario is， what if the checkum that B had sent back to a was actually an incorrect checkum。

And the network happened to go this with such that that incorrect checks on now looked like a correct check on。

Would that cause the transfer to fail， Yes， it would。

 I think these are all probabilistic arguments that the probability that this happens is very low and this is why people will worry about how many bits do you have in your checkum and what's the probability that a bit gets flipped。

 But this is like the extreme extremely low probability worst case， if it happens， Yes。

 even solution two would fail。And they have been。A few cases where those things have happened and has led to an endless debugging pain。

Any other questions？有。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_89.png)

Yeah， hold that on。 So with that， okay， I hope the argument so far told us we had to implement reliability in the NO system。

 and you didn't have to do it in the network。 But is there ever a case where you would want to implement reliability in the network in addition。

To implementing it at the endhouse。 So we can't get away from having to build it at the end horse。

But is it ever a good idea to add it to the network， And you were getting at the answer there。投。

 so the bottom， the answer is performance that sometimes having some amount of raising the level of reliability in the network is going to help even the end to end systems。

 So the simple example is if you think of having 10 links。

 and I say that each link can drop a packet with a 10% chance。

Then the chance of getting my packet across the network is really low。

 I have a 65% don't bother with the math， but I have a 65% chance that that packet is going to get dropped。

Instead， if I said every link is going to resend the packet twice。Very simple reliability technique。

 My perar length probability of an error drops very low and my end to end reliability goes up really high。

 much higher。 So it's much better。 So in this case， you would say， you know。

 the answer to the question is， yes， sometimes you do want to put。The liability into the network。

 The reason we're doing it those as a performance optimization， not for correctness。

Even if I had a 65% chance of my network dropping packets。

 I would not have impacted the correctness of the。En to end system。

I' just helping it perform better at this point。And there's a lot of discussion on how do you evaluate whether。

 you know， it's a good idea to put in。Reliability for performance optimization and so on。

 This is tends to be a case by case analysis that people will do。And so famously。

 I think wireless links are the ones that will do a little bit extra work to be mobile liable。

And so just to recap the end to end principle， what it tells us is that implementing a particular functionality in the context we've been talking about。

 that's the liability in the network， it doesn't reduce and host complexity。

 You still have to implement the liability at the end host。

 You have to do that end to end check for correctness reasons。

It does increase network complexity because you are now doing this additional mechanism that you're putting in the network for reliability。

And whatever extra machinery you're putting in the network in order to make that link more reliable。

 that overhead is shared by all applications。 So you're sending a message waiting for the app。

Resending the next one。 and you're doing this at every link。 that adds delay， for example。

 it adds state in the switches。 And if you had an application that didn't care about reliability。

 it's still going to incur that overhead， whether you like it or not。And so bottom line。

 you can add some functionality， reliability into the network。

 but is more for performance enhancement。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_91.png)

And so this is the actual end to end argument in Clark's Word words。

 I'm not going to try and read it， I'm leaving it here on the slide so that you can read it offline。

 but it basically sumizes everything we've said so far。Which is think about correctness。

 think about completeness。 And most importantly， think about this end to end picture。

 This is tremendously useful。 even， you know， if you go out and on an internship or a job and you're asked to build a particular feature。

 understanding the end to end。Picture in which that feature operates is critical to helping you understand what capabilities need to go into the component you're building。

 and you'll find the endto end principle is referenced constantly when we when we talk about。

 slightly more complicated distributed systems。And so with that just to recap this portion of you know kind of the top down view of how the internet works。

 the key parts you should remember on the how， which is how do you decompose the system into modules。

 our answer was layering and strict layering in particular。Where are these layers then implemented。

 we had this partitioning between end hostss and the network。And crucially。

 we had this one unifying protocol IP。 That's what stitches together these different networks。



![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_93.png)

On why， why did we do it that way， layering because it enabled an innovation by having a clean separation of concerns and the end to end principle as a decision for what not to put into the network。

 sometimes the functionality you don't add is actually more important than the functionality you do add。

 It kept the network simple and has allowed the Internet to scale。With that in the last minute。

 any questions and we'll come back to the end to end principle with a more critical view of it at the end of the semester。

Any questions？Thank you， and I hope you also my poster on Sean's post rather on Ed about the next four lectures and how we're going to run them in a slightly different style。

 I suspect this mostly impacts those of you in this room here so we do want to make sure it's a good experience for you you know we'll check back at the end of the experiment and see how it goes。

Thank you。

![](img/4ccb03cf6d03dabe3c4a4f8a30d06e33_95.png)