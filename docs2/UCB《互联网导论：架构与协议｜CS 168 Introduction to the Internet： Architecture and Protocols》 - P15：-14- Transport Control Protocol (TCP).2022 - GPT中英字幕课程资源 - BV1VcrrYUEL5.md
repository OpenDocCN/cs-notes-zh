# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P15：-14- Transport Control Protocol (TCP).2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Let's get started。 We're gonna be a really cozy group today。 Maybe some of you want to move down。

Do you want to move down？Take two minutes。Thank you。

So no update here to the midterm grading is underway you should have that to you before too long congratulations on surviving though I hear it wasn't too difficult so that's good news topic for today we are moving on to transport and TCP in particular we're going to focus on two questions what does the transport layer do and then specifically the design of TCP and as you'll see once we get into TCP we start getting pretty specific and in the details so I'm going to try and drag out the kind of more general discussion for a while before we get into the specifics of TCP。

So with that， the transport layer， this， you know， we've talked about the transport layer already。

 We've put up this figure where we said， you know， the transport layer implemented at the end host。

 usually in the operating system between the network layer and the application layer。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_1.png)

![](img/9dd914a828c6ba8b6ebecfaa076116ae_2.png)

We're going to dig into that a little bit in a little more detail what this looks like also we've covered this but just to recap is that at the transport layer you can have multiple transport layer protocols so TCP。

 UDP， SC CTTP， but there is a longer list than this so unlike IP。

And you can simultaneously at your end host， You can have multiple flows or applications talking to。

The network or through the internet going through different ones of these transport level protocols。

 they all go through the IP layer， but above that at the layer4。

 you can have multiple flows going through any one protocol implementation select TCP。

 but you can also have different applications talking to different transport layer protocols。跟。

So simultaneously in your end host， as shown here， you can have different applications talking to different transport layer protocols。

 multiple applications using the same TP implementation and so on。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_4.png)

Again， we've said this as well in the past， but I want to reiterate that the role of the transport layer is to bridge the gap between the abstractions that the application level wants or people who write application level code。

 the way the abstraction they want to work with。Versus what the abstractions of the network can support。

And again， we've said this in the past。 we build our transport layer into the operating system because it kind of acts as a common service for all applications。

 If we didn't have the transport layer or something like TCP。

 every application would have to deal with all the idiosyncrasies of what we get from the Internet or the network layer。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_6.png)

So let's take into that a little bit more。 What exactly does this mean。

 So if you look at your application layer， your application code。

 what what goes into that application layer。You have all of your application logic， of course。

 your ML computation， your key value stores， whatever it is you're doing at the application layer。

 But from a communication standpoint， you do also have these application layer protocols。

 but they are designed and defined to service the needs of that particular application。

So if you look at some of the examples of application layer protocols and there are many of them。

 we're going to study HGTP， but there are many application layer protocols。

 even just looking at the name， you see something like file transfer protocol。

It's a protocol defined for file transfer or the network time protocol。

 It's an application layer protocol that's designed and defined for time synchronization。

 So they're pretty specific。 Theyre designed for a particular application specific need。

At the network layer， however， we had a very minimal abstraction， Best effort delivery of a packet。

 an I P packet。So everything you need to bridge between this kind of application specific communication protocol and what the network gives you goes into the transport layer。

And as you'll see there's a little bit of a shift in attitude as well so when we were designing IP we were going for this very minimal you very clean interface。

 we don't want to put anything that's not needed into the network When we start to design things like TCP。

 there's a little bit more would it be useful to applications and if it's useful it's plausible to implement it at the transport layer。

Okay， so with that， what is the transport layer address。

 We've actually covered all the pieces that are needed in various discussions。

 I'm going just want to pull it in one particular place。 Any， anyone who remembers。

Some of the things we said， the transport layer has to do。Yep。Vability。Others， I think I fight。

The first one was demxing。We always have this as we go up the stack。

 which application when you receive。Some data from the other endpoint。

 you have to know which application does this data go to。 So that's the demxing rule。

We actually touched on this with the idea of ports in lecture number three。Reliability。

 That was our last lecture， and well revisit some of it again。

Translating from packets to application level abstractions， right。

 we said applications don't want to think in terms of packets and I headers and all of that。

 So we're going to think of what abstractions an application layer wants to think about。

 And then translating between packets and that is going to be the job of the transport layer。

Anything else you remember？There were two that came up very briefly。When we talked about reliability。

We talked about sizing windows。Everyone's in midtermlet。

 we said that we want to pick the amount of data that the sender should send should be picked with paying attention to two considerations。

 One is you don't want to overload the receiverce。That's we're going to cover this in today's lectures。

 something we call flow control。 And the last one was we said， we don't want to overload the network。

That's a topic that we call congestion control。 We're going to have multiple lectures on that。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_8.png)

Okay， so let's first talk about how we do these issues in general。

 and then we'll get to how TCP specifically implements them。 Any questions before I go forward。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_10.png)

So first， the question of de multixing， if you remember from and again， what is the problem here。

 The problem is I've received traffic coming in from the network。

 It's been passed from your network interface card up into your operating system。

 It's gone through the I layer at the I layer。 We looked at a protocol field and said this is TCP。

 So you sent it to the TCP。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_12.png)

Ocean for processing。 Now， TCP is done processing。 It's done reliability。 All of that。

 It has to know which application do I send this data to。Is it an email， Is it Slack。

 Is it something else？ And so for that， we said we had this concept of ports。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_14.png)

Or logical ports。We said a port identifies where an application process attaches to the operating system。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_16.png)

And if you remember， we also said that port numbers were going to be carried by packet headers。

At the time when we talked about this， we hadn't talked about layer 3， layer 4 and so on。

 So now understand that the place where you carry that port number is in the layer 4 header。

So if your layer 4 implementation is TCP， then it's part of the TCP header。

 It's U repeat and it's part of the UP header。Any questions on this？

And you also should be able to relate this to the sockets interface that you did in section。

So now packet it comes in， you look at the port number。

 you send it up to the corresponding application。Reliability we covered in our last lecture。

 so I'm not going to cover the concepts again， but just a quick recap of what we covered。

 we talked about the various techniques or the building blocks that go into building a reliability protocol。

 things like check sums， acknowledgements， negative acknowledgements， timers， Windows。

 sequence numbers and so on。We also talked about different trade offs about how you could combine these into an actual design。

We'll get back to how TCP does them， But I was not going to recap them here， if anyone wants。

Has questions or wants a quick review or reminder of something。 nows your time。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_18.png)

No， good。Okay。So the last thing not the last thing with the next one is this notion of application layer abstractions that the application does not want to have to reason about duplicate packets。

 reach transmissions， corruptrup packets， I packets， any of that。 And so instead。

 we want a higher level abstraction that the application is happy to reason with。

 Any thoughts on what would be a good abstraction for applications。

 Theyre basically two that are the canonical ones we've used for。30，40 years now， but。

There' certainly is space for more。Thoughts， what is the good if you were writing an application。

On top of the Internet。Let's say you're transferring data from host A to host B。

How do you want to think about the Internet as the service it gives you what would make life easier for you as an application developer。

Yeahep。Well， sorry， if it's the last bit。So you just want to send the bites over。

What is that What would we call that abstraction。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_20.png)

I think大 had someone问。A by stream。 So the by stream abstraction is。

Probably the most intuitive for many applications。 So we said。

 and this is what TCP does is a reliable in order by stream abstraction。 And we're going to。

Go into it in more detail in a bit。 But lot at a high level。

 the way you can think of it conceptually is you have a sending application and a receiving application。

Ideally， the abstraction you want between them is think of it as just a pipe。That is reliableable。

 so it never drops anything， and it never reorders anything。

 So you put bytes into this pipe in some order， and the receiver just receives every bite in order。

If that was your abstraction， you don't have to think about headers。

You don't have to think about specific protocols。 It's just the bytes you want to transfer。

 You don't have to worry about things that get lost。

 You don't have to worry about things that get corrupted。

 You don't want have to worry about things that get reordered。

So is it clear why this would be a good abstraction for application developers。

 We've just abstracted away all the complexity of the network。Does that make sense？

So this is the abstraction that TCP wants to give to applications。

 so it's what we call the north bound abstraction。The the abstraction that TCP itself has to deal with or the southbound abstraction is the IP abstraction of packets of retransmissions of things that get lost。

 reorder， delayed and so on。So that's why TCP plays such a crucial role。

 That's why it's so much easier for people who build applications on the Internet to actually be fairly。

 I would say， 90% of developers don't really appreciate or understand all of the complexity that lives underneath that abstraction。

给。Any other ideas of other abstractions that would be useful？

Because there's a lot that goes into implementing the TCP abstraction。 we're giving a liability。

 We're giving in order。 We're giving a by stream。Attraction。This's a a simpler one。

The second abstraction that's very common is just an individual message delivery。

 It's what a protocol called UDP implements， and it's just it's unreliable。

 It's just saying I have some bag of bytes to send to the other end。 It's a single message。

 I'm just going to send it to the other end。 No guarantee on reliability。

Why do we we use this Because sometimes， as you'll see。

 there's a certain amount of complexity that goes into TCP and providing the TCP abstraction。

 And for certain applications， you don't need it。 So， for example。

 think of you have an Io T sensor in your house。 It's taking some temperature reading。

And every two minutes， you need to send an update saying， this is my current reading。

If you drop a reading， it doesn't matter。 There's another one that's going to come soon。

And you don't have a whole lot of data to sense。 So all of the complexity we're going to see where I keep track of counters and reordering and timers。

 you don't really need to implement all of that。So for those kinds of applications。

 they go build on top of UDP。It's just， I have expites to send。 I'm just going to send it。

Does that make sense？有。So the UDP abstraction is actually just a single bucket message。

 You just send one。Message。是呀。The M U could fragment it the IP layer could fragment it under the hood。

 in which case， if any fragment got lost， you would just lose the entire message。

 But at the UDP level with interaction with the application， it's just a message。

 And if you did want something like ordering or sequence numbers like this is message1。

 this is message2 you have now have to do it at the application layer on top of UDP because the UDP abstraction doesn't give it to you。

 And so applications that build on top of UDP will often do a little bit of sequence numbers or even maybe a little bit of liability。

 but it's the job of the application developer。Any other questions。

So we're going to cover TCP in depth today， we're going to in future lectures touch a little bit on UDP。

 but there's actually not that much to say about UDP。

 so it's going to be a brief discussion in a future lecture。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_22.png)

So then the last two points we have avoid overloading the receiver and avoid overloadloading the network so let's dig into those a little bit more today so the first one if you go just to call you back to where this came up we had this question in our last lecture the lecture on reliability where we asked this question of how big should the window be so reminder here what was the window the window was the set of bytes that at the center it's saying these are the bytes that I can send into the network。

These are the packets I can send into the network that may or may not be acknowledged just yet。

 but this is how much I can sense。 So it's kind of the rate at which the sender can send traffic into the network。

And if you remember from my discussion， we started out with this very simple protocol where I send one packet。

 and then I wait for it to be acknowledged。 then I send the second， and I wait for it。

 And we said that's too slow。 And so instead， we wanted to be able to send lots of packets in parallel。

And we said how many packets you can send is going to be dictated by this window parameter。

 which is how many packets can I dump into the network without having them acknowledged。

 And we said that we're going to pick that window size to balance three goals。

 One is to make full use of the network capacity。 what we call filling the pipe。

The second was we said we don't want to overload the receiver。 flow control。

 And the third was we said， don't overload the network congestion control。

 And then in our last lecture， we said， we're going to ignore the second two。Conditions or the goals。

 And if you just focus on the first goal， we worked out that the window size you would want is proportional to the round trip times the bandwidth of the bottleneck link along your path。

Does this make sense to people。Want to repeat of the intuition for that。Yeah。

 so the interactionition was， if I take the path from the source to the destination。

 every link along that path has a certain bandwidth。One of those links。

 which we call the bottleneck has the least bandwidth or the least capacity。

 I can never send faster than the bottleneck capacity That's as much as I can send。

But I also want to keep the pipe full。 So I want to be able to keep sending as much data as I can。

The time how So the duration for which I can send at the rate B is my ground trip time。So ideally。

 I would like a center to be sending at that rate be。 That's the bottleneck weight。

For the entire duration of the ground trip time。That means I send a packet by the time that packets Act comes back。

That's how many bytes I could have sent into the network。Is that thing about。

People are good with that？If I were sending that if my window was sized to be that。

 I would be sending at the full capacity that the network is allowing me to at the center。

 So this is an upper bound on the size of your window at the center。

 You cannot possibly send more than that without dropping packets。

But that was ignoring those second two goals of not overloading the receiver and not overloading the network。

 So we're now going to consider those two goals。 The first one is to not overload the receiver。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_24.png)

And let's first talk about why this is a problem in the first place。 Like。

 why is this even a concern。 And it comes from， you know。

 if you think about the receiving side of the TCP implementation or the transport layer implementation。

 we've said that， you know。The abstraction we're going to give the app the the application is one of in order reliable delivery。

Okay， so what that means is that at that transport layer implementation on the receiving side。

If your packets are not coming in in order， you have to buffer them。

You have to hold on to them until packets are coming in order， because I can only， let's say I was。

 I had packets number 2，3，84 and 5。 I'd already received one and sent it to the application。

 And now packet 2。Has not arrived at the receiver。But back as 34 and5 have arrived。

I cannot send packet number 3 or the data in packet number3 up to the application。

 because I promise the application。 I'm only going to send data in order。

So instead at your transport layer implementation， you have to buffer packets 3，4。

 and 5 until you get2。Okay， does that make sense to people？Yeah， and so if I have to buffer them。

I have a finite amount of buffer space at the receiver。

And so there's always a risk that I overgu that buffer space。 and I don't want to do that。

 And so the receiver needs to be able to tell the sender this is how much buffer space I have available。

 Don't send me more than that。So that is the goal of flow control。

 so because packets can receive be received out of order。

 you can only deliver them to the application in order， you have to add the transport layer。

TCP side of that implementation at the receiver buffer these incoming packets。

And you have to do so until you receive that gap or the packet that was missing。

 So packet number two， in my example。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_26.png)

And that ensures that the receiver is not going to run out of buffer space。 How would you do this。

 The actual flow control mechanism is really simple。嗯。Exact。

 So the receiver is going to tell the sender how much space it has left。

This is done in TCP through a field we call the advertised window。

Is transmitted from the receiver to the center in every acknowledgeknowment that the receiver sends the center。

Okay you available buffer space。 This advertised window is changing dynamically over time as packets come in。

 but you're also communicating it back to the send very frequently in every app。And accordingly。

 the sender is going to adjust its window based on the advertised window its from the receiver。

 Any questions on this。对。Usually， when you configure your O S， or you configure your。

Your machine on the the side。And so it varies very much。

 I think there's a related question of is this earlier problem don't we have tons of memory in systems these days。

 It's true that flow control often is not the limiting factor to the rate at which a center can transmit。

 but there are certain cases to go back to， for example。

 an IoT sensor that doesn't have very much memory on it or a cheaper low end smartphone that doesn't have a whole lot of memory on it if you're doing a software upgrade or downloading a large file。

 you could actually overrun the buffer capacity at the receiver。

 So there are cases where it doesnt matter。Any other questions？对。You would end up dropping。

Was the question about Ogobo malicious？Any other。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_28.png)

Okay， so then the the last one of these transport layer functions was to not overload the network。

 So previously， we said the sender can send。Will set its window size to fully consume the bottleneck link capacity。

 So if I take this example that I have here。You know，From going from the source to the destination。

 your bottleneck capacity is 1 GB per second。When we were saying I'm going to set your window size to be the bottlenecks of1 gigabit per second times the ground trip time。

 that was assuming that this source is going to wholly consume that bottleneck link。

That it's filling it。In reality， that's unlikely to be the case because on the internet。

 there are lots of flows， lots of sources and destinations。

 and so it's very unlikely you get that entire bottleneck link to yourself。So instead， so。

 for example， in this。Example here， we have two other flows that are sending at 150 and 200 MB per second across that bottleneck link。

And so what we want actually， is that a sender only consumes its shell of that bottleneck link。

But what is that show。Like in this case， what would you have said the source and destination。

What weight or what fraction of that bottleneck link should it have been given。

This one is actually an easier case。投子。Sure that let me pause you there。

 because you're getting into congestion control design。 But however you get there。

 what grade would you like the source to be able to send that。So we did whatever you said you do。

 but。If you could magically look at this picture。有。使。

At the fastest that you could have where you were going， Yeah， So if I looked at this， I could say。

 well， I had one gig。 I'm consuming 3，50。 So everything beyond that 3，50。

 this source could have centerd。That这个意思。Calculation。

 but what if those two flows were already fully occupying that 1 gig per second link。

If they were sending at 500 meg each。What would we have told us so， sorry， there's no capacity left。

 no。What we would have done is to say the other two flows have to consume less so that the source and the destination can consume more。

Every time a new flow starts。On that link。Everyone else would have to adjust a little bit and go down Every time a flow finishes。

 or the other flows could consume a little bit more。

So I'm just saying all of this to give you the understanding that actually。

 this question of what is your share is a pretty complicated one to figure out。

It's why we're going have three lectures talking about this question of congestion control。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_30.png)

Because every source has to independently figure out。What its share of the network capacity is。

 And it has to be dynamically adjusting that as different sources come and go and different flows come and go。

 So for today's lecture， we're not going to worry about how this gets done。

That's going to be the topic for congestion control。

 Congestion control is kind of to semester the second half of the semester。

 what routing was to the first half。 It's going to take us a while。

 We're going to go through all the ways in which you can do it poses and cons。

 So let's not worry today about how congestion control gets implemented。

The way in which it's going to work to just abstract out that complexity is that at the sender side。

 you're going to be running at your transport layer。

 We're going to be running an algorithm that we call the congestion control algorithm。

That is figuring out for that send， and for this flu。

What your rate you should be sending at in order to share the network reasonably with other senders。

 The output of that algorithm is going to be something we call the senders's congestion window or sea wind。

This is the size of the window that the sender should have in order to share the network reasonably with other flows。

Are people comfortable with this level of abstraction。 We haven't talked about how we're doing it。

 There's this magical algorithm。What comes out of it is this one value。

 which is your congestion window or sea wind。That C is going to be computed to balance multiple goals。

 You want to maximize the performance of this flow。

 You want to make sure you're not overloading any link because otherwise。

 you're going to get packet at drops and you need to share your bandwidth。By some definition of fear。

Faairly with other sources。So as I mentioned， this is the topic for multiple future lectures。

 But this lecture， just assume we have this algorithm。

 It spits out this sea wind that we're going to run with。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_32.png)

So putting all of those pieces back together and going back to our original question of how big should this window be And we had the three goals。

 we now know that if you just look at the first goal。

 you would set your window size to be your gotri times the bottleneckling capacity。

 If you just looked at the second goal， you would say your window should be no larger than the receiver's advertised window。

And if you looked at the third goal， you would say your window should be no larger than the sender's congestion window。

So given these three goals， what how would you combine them into one window size。Yeah， it has。

 So the desired window size at the center is the minimum of the windows that you compute these threeway。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_34.png)

In practice， your congestion window will always be less than or equal to the ground trip times the bottleneckling capacity。

 Remember， we said that's an upper bound。And so in practice， also。

 it's a little difficult to actually know what that bottleneck link capacity is。 It's not。

 Rers don't tell you this is my capacity。And so in practice， when we implement window sizing。

 it's the minimum of the receiver advertised window and the congestion window。Any questions on this？

Very good Okay， so quick recap， what the transport layer tackles demxing。

 which we do through logical ports， reliability， for which we have everything we talked about in our last lecture。

 translation between abstractions， specifically we're going to focus more on between packets and by streams。

Avoid overloading the receiver， which we do with the receiver's advertised window and avoiding。

Avoid overloading the network， which we do through this congestion window。Good。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_36.png)

你个东他。For any application that either doesn't need reliability has very short messages。

 so it doesn't have to worry about sequencing and in order delivery。 There is the UDP。

 which is the user data cr protocol。 It's a very minimal protocol。

 It basically just has source and destination ports。

It's just acting to pass back data through to the application。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_38.png)

So with that， I was going to start on TCP。 Are there any questions lingering questions on the transport layer in general。

So questions， do TCP and UDP share the same links yes。Right， so that's actually a great question。

 but it's also something we'll get to when we talk about congestion control is that in TCP you have a congestion control algorithm that's trying very hard to do the right thing and to be fair in how it shares resources。

 UDP has no congestion control algorithm gun so in principle。

 if we had a large number of applications gunning UDP gunning on top of UDP that were not worrying about how much of the network resources they're consuming they could cause congestion and they could in fact be unfair to TCP。

 So there is a lot of work。 there's also a lot of watchdog monitoring that happens to make sure that there isn't someone hogging。

All of the network capacity and ISP will have certain ways of weight limiting。 But in principle。

 this is something that has happened and can happen。

 which is if tomorrow YouTube decides to run without congestion control， we'd be in trouble。

That's a good typically when you open your， you have a certain amount of buffer space and you would allocate it on a per connection basis as you set up connections。

It's really up to how your operating system， how it's configured。

How you want to assign that bufferet space。没有。So typically when you'd open a socket。

 you open a socket that is of an either connection or connection list and that tells you。Any。

So moving on to TCP and you know， when you start on TCP。

 you have to pay us back to Windsorf and Bob Gn who were the two who actually wrote the first TCP implementation that you've probably heard or。

Of them， they were toing Award winners for the work they did on TCP。 they won the Ting Award。

 They won the Presidential Medal of Freedom Medal of Freedom Medal of Honor my lack of being born in the US is showing here which is basically the highest civilian award that the president gives they've won pretty much every award you can imagine for the work they did on TCP。

 interesting， they actually started building TCP when they were students when they were graduate students was at UCLA continued the work on when they were doing they were at Stanford if you ever meet a networking person who is French。

 they will tell you that actually their job description when they started was to port an implementation of the liability that had been done for the French research network。

 the equivalent of the research network that was being built in the US and that became the Internet that is actually true but be that as it may probably the most interesting and impactful porting job ever done So they really built what is the baseline for。

DcP implementations today。Why do we study T P Fe， I think for two reasons， the one， you know。

 the obvious reason is。It's not an exaggeration to say that pretty much the entire internet runs on top of TCP。

So clearly， it's a critical part of the infrastructure。 It's， you know。

 if you think about somebody who's a developer for Linux or Microsoft Windows。

It is they probably lose sleep over the thought that maybe there's a bug or there's a security of vulnerability in their TCP implementation because if you have one of those。

 you're not just taking down one application， you're taking down all applications so TCP really does play this crucial role。

 and also you know I is the other part of the story。

 But if you look at your operating system or the end host IP is pretty simple in its implementation at the end hosts。

 in all of the complexityities in the network and the control plane of the network BGP routing and so on。

 whereas in TCP， all of that complexity really is at the end hosts。

 So particularly from a security standpoint， it's that much more crucial。

The other reason we like to talk about TCP is it actually is a good exercise in kind of engineering excellence and paying attention to detail。

 We talk a lot about high level approaches and design principles， and even design solutions。

But it really， when you work through the details of TCP。

 you get an appreciation how even a fairly simple design actually needs a lot of attention to detail in how it's implemented。

And lastly， your second project is on basically implementing a TCP compatible reliability protocol。

 So the protocol you implement will actually be TCP compatible that it could speak。

To a realtyP implementation on the other side。And so。

 we go into a fair amount of detail so that the project is also easier。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_40.png)

With that， where I wanted to start was the TCP abstraction。So we've said this a few times。

That TCP delivers a reliable in order by stream。 So let's unpack that a little bit。

 What that means is that if you're at the application layer。You see a stream of bytes。

 application data that you're sending from whose day to Who speed。There's a bite。Stream or byte。

 So every bitete， you can think of it as having a number。

 and you're going to deliver it in order to the receiver。

If we dig into how that's actually implemented a little bit now， you know。

 you clearly you're not sending one byte at a time to the receiver。 Instead。

 you're taking a set of these bytes from the application and you're going to put it into what we call a TP segment。

And we send TCP segments over to the receiving side。

So D CP segment is the actual application data or the TCP data that's being sent between hosts。

 typically you'd accumulate you know how many bytes do you send at one time or what's the size of the segment。

 You'd have a value that we call the maximum segment size， and I'll get to in a minute。

 So typically you send bytes and chunks of either you accumulate a maximum segment size or MS worth of bytes and you send it over or until a timer goes off。

YouWhy do we have the timer for the obvious reason。

 What if your application had only 10 by to send and your M S S was 500 by。

 You're not going to sit there forever waiting for more bys。 So you have a timer that says。

This is as many bytes as I have to send in this time， I'm going to send it out as a TCP segment。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_42.png)

So digging into the TCP segment a little bit more， you know， when we talk about a TCP packet。

 it looks like what I have up here。And the TCP packet is always an IP packet because all packets are IP packets。

 but inside the payload of the IP packet， you have a TCP header。And you have a TCP segment。

 which is the actual application data we're carrying。

So we know that the IP packet should be no bigger than the maximum transmission unit of the link at the center。

 the MT U。 And so that tells us that a TCP segment or the MSS size has to be set to be the m U minus the length of the IP header minus the length of the TCP header。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_44.png)

Any questions here？Al right， so this is pretty straightforward。 Let's go back to our picture。

 So we said we're going to transfer bytes or this by stream from A to B。In these TCP segment chunks。

That's the TCP data。 We're going to put a TCP header in the front because you have to be able to explain what those bys are to the receiving end。

And in particular， the。Feel that we're going to have to carry in that header is a sequence number that tells the receiverce where in that by stream。

These bites fit in。嗯。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_46.png)

Does this make sense？ai， so now we're going to just change notation because TCP does things a little specifically in a rather。

Specific to DCP。 We here。The notation change we're going to have is that previously we focused on packets。

 We send， I send packet number 1，2，3。 When I get an acknowledgement at saying I acknowledge packet number 1。

2，3。 So we were saying there's like a number associated with every one of these packets。

The thing toli internalize is that TCP doesn't think about packet numbers。

TCP just thinks in terms of bytes and that by stream。

And so a packet is identified by the bys that it carries where they belong in that by stream。

So sequence number is， I am by 158 in the B stream。And an acknowledgement says。

 I got all received all bys up to 259， as an example。And when I talk about Windows。

 it's not about how many packets you can send into the network。

 It's about how many bytes you can send into the network。This trips people up invariably。

 especially in exams。 You should be comfortable reasoning in terms of packets or bys。

 particularly when we talk about T CP， it's usually we're talking about bites and by streams。

But if we ask you about you know， the liability protocol we're making up where you have packet numbers。

 you should be comfortable going back and forth between those。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_48.png)

So let's walk through what these sequence numbers look like in a little bit more detail。

 And let me first step through what it does。 And then we'll come back to why it does things this way or how So in TCP。

 your byte stream doesn't start out as being numbered by 0 by 1 by2 by 3。Instead。

 what we say is that every connection， you start numbering at what we call an initial sequence number or ISN。

This is randomly picked。For every time you start a connection， you pick a new random ISN number。

And your first byte in that byte stream is number ISN plus1。Okay， so not I n plus 0， I n plus 1。

 and I'll get to y in a minute。When you then take a chunk of those bytes and send it out as a TP packet。

 your sequence number is the offset of the first byte in that segment。So if you were。

Bs past the beginning， U' be I Slaky。娘。And when you acknowledge what TCP will do is it the sequence number that it sends back in its acknowledgement to the sender。

Is the first bite after all the bites that have been received。Okay。

 so it's what we call the next expected by。So in this picture。

 if the deceivva is received all bytes up to this point。Whatever the offset is for that green bite。

 that is what the acknowledgement number is going to tell you。

Any questions on just clarifying what this is doing。 I'll get into why， in a minute。Okay。

So idioyncrases of TCP， start with an ISN。First byte is numbered I N plus1。

 S number is the offset of the first byte in the packet。

 and your acknowledgement is the next expected by。Or the first unacknowledged bite。

So why does TP do things this way， Anyone can guess。

 why would you pick a random initial sequence number as opposed to just starting from 0。

Prevent overlapping any other。YouCan't just fake a connection by。 Yes， you're absolutely right。

 Let me get to that in a minute。 So the original motivation for having an initial sequence number was the scenario that surf and K were worried about was。

 let's say I opened a connection between a source destination。 And then I killed the connection。

 And immediately we started。For whatever reason， the application decided to kill it and restarted。

 If you just restarted with the same initial sequence number。

 everything else that defines that connection is also the same。 The So and destination port。

 the So and destination IP address。 So they were worried about we a connection。

 It's a new connection。 But I have packets in the network that belong to the old incarnation of that connection。

So that was why they first had this initial sequence number。

Then the initial TCP implementation actually had the initial sequence number would be plus one what the previous initial sequence number was。

 or it was augmenting by some time value。And then people found that you could actually launch an attack by this by guessing what the initial sequence number was。

 It's a fairly involved attack for those of you who are interested Google that you will find the description there's actually an AFC that describes it。

 but it was very sneaky because it would allow you to appear to be the client talking to a server。

 even if your client actually could not hijack or snoop on the original client's traffic。

So it's pretty involved in the setup because you have to first manage to hide traffic from the true client and then at the same time。

 be able to look like a legit client to the server。

 So that's the reason why we have now randomized initial sequence numbers。Any questions on that？

 I don't expect you to know the security attack。 I don't think I could recreate it myself。Okay。

 the ISN plus1， why do we start numbering at IN plus1。

 we'll get to that when we talk about how you set up a TCP connection。

 but basically kind of the zero label is reserved for your request to set up a TCP connection。

Any questions on the sequence number and the acknowledgecment。没。

I just made up the K just as an example， just to show you that you're somewhere in the by stream。

Yeah， so I sent plus case just to tell you your K in。K bytes into the byte stream。

 actually K -1 to be collected。And then the why， if you。

 the question was why I S plus K plus length of data， It's because if this was I n plus K。

And the number of bytes in this segment。Was length of data。

Then the next byte that is expected is I n plus K plus the length of data。Okay。

 that's the first unacknowledged bite at the receiver。Does that extent。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_50.png)

Okay， so that's our reliable in auto byte stream。The second part of the TCP abstraction is。

To realize that， you know， if you're going to implement a liability in this way and you're storing out of order packets and so on。

 you have to be maintaining state for that connection at both the center and the receiverce。

So there's state associated with this transfer now。

 initialial sequence numbers actually buffers for stowing packets。

 timeouts for doing so timers to do reliability and so on。

 And so we say that TCP is actually a connection oriented protocol。 Youll read this everywhere。

 This idea that TCP is a connection oriented protocol。

 We call each of these by streams a connection or a session。It's associated。

 Every one of these by streams has their own associated connection state。

This is state that's set up in the host。 So if you go all the way back to when we talked about reservations and we didn't like per flow state or per connection state。

 that was per connection state in the network。But we do have per connection state at the end host。

 And that's O because we don't have that many connections。

At the endho would have been impossible to have that state in the network。

 But we're fine keeping it at the endho。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_52.png)

Okay so if you're comfortable with this idea that TCP requires maintaining state per connection at the end host。

 then there's two things to note here one is that in order you need to initialize that state when you set up a connection at both ends。

 you need to allocate some buffer space， you need to pick these initial sequence numbers。

 you need to initialize timers and so on。And so in order to do that。

 T CP is going to actually include explicit connection set up and tear down。

Fse where you initialize that state。 and when you're done with your transfer。

 you delete or you garbage collect all of that state。We'll get to the details of that in just a bit。

The other thing， and this is another one of these kind of subtle points that trips people up is that TCP connections are what we call full duplex。

And the way we've been talking about TCP and the transport layers so far is that I have a send side and I have a receiver side。

And the sender sending data or transferring data to the receiver。In a TCP connection actually。

 when we say a full duplex， it's that each side of that connection can be both a sender and a receiver simultaneously using one connection。

RightSo if I have a TCP connection from host A to host B。A can be sending data。

 a file or whatever data from A to B。 at the same time。

 B could be sending some different data from B to A。

Which also means a can be sending data to B while acknowledging data that B has sent to A。

And B can be sending acknowledgements back to a while sending new data from B to A。

Is it clear what we mean by full duplex。For the most part。

 we can actually ignore this fact other than when we get to connection establishment。

 because there you'll see the full duplex nature of connection establishment。

It's also important to remember that TCP was designed before the web before client server。

 if you just went in with a mental model of client server。

 you would say I don't need a full duplex connection and you're mostly right， but for example。

 if you had multimedia session between two hosts where both each side has something to send the other side then a full duplex connection is a pretty natural way to want to go about。

 so we'll get to connection establishment in a bit。 But so coming back。

 our TP abstractions two points to note as understand this reliable in order by stream。

 And there's an implication to each one of these words that you should understand and understand that TP is connection oriented。

 So we set up connection state。 We initialize connection state。 We tie it down and so on。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_54.png)

![](img/9dd914a828c6ba8b6ebecfaa076116ae_55.png)

And so when we get to all the functions we talked about for the transport layer for TCP I'm going to add this connection set and tear down phase。

So now we what we're going to do is walk through these functions again。The first time we did it。

 we did it in a pretty general transport layer fashion。

 now we're going to do it with the specifics of how TCP does things。

I'm going to go a little fast on things that I'll repeat。 So just stop me if it's not very clear。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_57.png)

So demxing and ports in TCP ports are 16 bits， nothing very deeper sophisticated here it's just 16 bits that are in in the header。

 the one thing to know is that some ports are well known while others are Victor to randomam so typically when you connect to say Google do com。

You know， Google dot com， the service is running on a well known port。HDP Po or the HTPS port。

On your client side， you just pick a randomam port because it doesn't really matter。

 So wellknow ports are used typically for services where you need to be found by clients。

 And so having a wellknow port makes it easy for a client to connect you。

I know this description isn't 100% clear because there's also how did you find Googleo。com。

 how did you find the IP address when we cover the DNS。

 you'll see the remaining parts of that picture。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_59.png)

So let's start looking at what the TCP header looks like。 So at the top here is our old friend。

 the I header。 remember， we had a protocol field that we said if the value was 6。

 then your transport layer protocol was TCP。 So what this means now is that the first。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_61.png)

![](img/9dd914a828c6ba8b6ebecfaa076116ae_62.png)

Set of bytes in the I P payload I O TCP H。And if we now go poke at that TCP header。

 what you'll see here are the source port and the destination port。We use this two Mus and Dms。

Typically， not。If you demarked on the protocol field and the port number， yes。

 but I don't believe that's how。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_64.png)

跟。So that's our Mark D marks。 moving on to the liability and how does TCP handle the liability。

 This is a busy slide。 So let's take it one at a time。

 It's all of the basic building blocks we talked about in our last lecture。

 but they used one at selecting certain design options from the things we talked about。

 and there are some key differences。 So first is sequence numbers are by offsets。

 Okay we covered this already。When we talked about reliability liability， we had packet 1， packet 2。

 we now know actually sequence numbers are going to be by offsets。

DCP uses cumulative acknowledgements。 So if you remember from last time we talked about individual full information and cumulative acknowledgegments。

TCP uses cumulative acknowledgement。 So it's saying， I have received all bites up to this point。

It might have received some bys beyond that point， but it's not going to tell you about that in the acknowledgeknowment。

Okay， the semantics here's the next expected bitete。This is my first unacknowledged bite。

Uses a sliding window。 So your window is W consecutive or contiguous bys that you can have in flight。

 So just to look at what that looks like at the center。

 if you were keeping track of which bys have been sent。In green here。

 when I get an acknowledgement that says this is my next expected bite at the center。

 What that tells me is all bites up to that point。Have been successfully transferred。

 so you can reclaim that buffer space。And then you'll have a window that says， depending on your W。

 the value of your window， the next W bytes。Any of those bytes you can transmit。

That's the maximum number of bytes you can have in flight。 So you can。

 the sender can go ahead and send those。It can't reclaim this buffer space。

Because it hasn't received an acknowledgement yet。So this is the buffer space needed at the center。

Can we call this a sliding window， Because as acknowledgeledments come in。

 you kind of slide your window to the to the right。嗯。Questions。

Wetransmissions and TCP are triggered by timeouts just like we discussed。

 and they also triggered by duplicate Xs。 if you remember last time we said if you get K duplicate X。

 that's a pretty good indication that your packet you're waiting for is lost。

 so in TCP K is equal to three， but it does use if you get three duplicate acts。

 TCP will assume that packet the next packet you were waiting for is lost。

Next bite you were waiting first his lost。We have a single timer。

 So in the way we discuss things in the reliability lecture。

 we were thinking of it as a timer per packet。 We're clearly not going to have a timer per byte。

 So instead in TCP， you have a single timer that is corresponds to the first byte in your window。

 So when your timer fires， you will resend。The bites corresponding to the left side of your window。

Any questions on that？你看。也。It doesn't。 So you have one timer。That， you know， when you don't have the。

 you're waiting for these bytes， you sent these bytes。And you set your timer。When your time of fires。

 you rescin these bikes。困面。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_66.png)

And then finally， a window size we now know is a function of the congestion window and the advertised window。

 which we gloss over when we talked about reliability。

 There is some special accounting that gets done for duplicate acknowledgecgments。

 We will cover that when we talk about congestion control。And finally。

 the timeouts are computed from LTT measurements。 So you cover this in section。

 but let me give you the intuition here。 So the last time we talked about timeouts and how do you set this time of value Because your delays on the Internet can go from microseconds to hundreds of milliseconds。

 So there's many orders of magnitude。 And we said that ideally you would want your timeout。

 So remember your timeout is how long do you wait before you decide okay， this packet really is lost。

 I've not received an acknowledgement and you we transmitted。 And we said that ideally。

 that time of value should be based on the groundtri time。Well， so in TCP。

 you're sending data and you're getting acknowledgegments。 So in principle， you could take a times。

 you could look at the time when you sent the data and look at the time when you receive the acknowledgement and use that as a sample of what your gun trip time measurement is。

And you're getting one of these samples or measurements。

 potentially every time you get an acknowledgement。

So you have a pretty good indicator of what your ground trip time is。

Gets a little tricky when you think about things that are retransmissions。 you know， should you。

 what is a clean sample， How often should you take them and so on。

So that the details of how you do time or estimation willll cover in section。

But the basic idea is this that you're going to use the time from when you send data to the time you get an act back to estimate what your long trip time。

I want to just cover acting and sequence numbers。A little bit since this is different from how we liability。

 So let's say in TCP now that the center center packet。

And the data in that packet started with a sequence number x。And that packet included B bytes。

 so the bytes x x plus 1 up to x plus b minus1。咁。Cl， so when you。

 let's say the receiver receives this packet correctly， and it wants to send an acknowledgement。

What is going to be the sequence number， the number that gets acknowledged from the receiver。对。

Exlessly you mean。Ex plus B， that's one correct answer。 There's another one。

What if these B bys were not in order that there were some bys missing。At the。Some bites before it。

Yeah。So if all data up to x had already been received at the receiver。

It has now received bytes x up to x plus B plus -1。 So your act is going to be for x plus B。

The reason it's X plus B is the member， TCP says I'm acknowledging the next expected bite。Okay。

But what if actually the byte， the bytes that you were to received。

 you hadn't received all the bytes before X。 So you have some gaps at the receiver。In that case。

 let's say that y was the highest contiguous byte received。 So you have received all bytes up to y。

And then between Y and x， there was some missing bytes。And now， you have X。From x to x plus B。

So then in that case， TCP is going to acknowledge y plus one。

This is the consequence of using cumulative acts。I cannot acknowledge X plus B because I'm missing some bites before that。

Is this you？And know it sounds easy。 Sometimes when we walk through detailed TCP examples。

 this trips people。 So make sure it's。Clear what gets acknowledged。

 It's driven by the fact that we're using cumulative acts and the fact that we're the semantics Open an act。

 This is the next expected bite。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_68.png)

So keep those two holes in mind。So let's just reiterate at this one more time if I had only one packet in flight。

 what would my packets look like the from the send side， a data packet。

 let's say my sequence number was x and the length was X B。Then your act would be for expy。

Your next data packet， the sequence number would be x plus B。And again， if the length was B。

 then your act would be x plus 2 B。Packet after that， would' start at X plus 2 B。

And the act would be， again， express3B and so on。Okay。

 so the sequence number of your next packet is the same as what your the next expected bite that your previous acknowledgement gave you。

In this， I'm assuming no packet loss。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_70.png)

Does this make sense？Okay。So going back to our TP header， we've now filled in the sequence number。

 This is the offset of the first bitete。 We've filled in the acknowledgement。

 which is the next expected byte。So the first first unacknowledged bite。

 such that all previous bites were acknowledged。And then finally for liability。

 we also have a checkum and the check some and TCP is over the data。

 as well as actually a few fields from the I header。 But we're not going to get into that in detail。

 So we need check somes for liability。 We covered that in a previous lecture。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_72.png)

Moving on any questions on reliability in TCP。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_74.png)

So if flow control， we have the advertised window as promised。

 and the way we're going to use it is that the center maintains a window。

The left edge of this window is the first unacknowledged bite。 You've seen this figure before。

 The right edge， if we ignore congestion control， you cannot go further than the advertised window。

That was what we said was flow control。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_76.png)

So what's left in this header， we have a header length。Field， just like an I。

 this is in units of 4 bys。It covers the length of the header。What about the length of the data。

It's a bit of a trick question。 The length of the data you actually get from the I header gave you the length of the entire I packet。

 So you go， you take that length and you subtract out the TCP header length。

 And that gives you how TCP bys。 Data bys are in the TCP payload。

Ignore0 there's something called an urgent pointer which I'm just going to mention it here。

 but we don't worry about it in this class。 The urgent pointer。

 the idea here when they designed it was let's say you'd sent a bunch of data to a receiver that it was processing that data and then you have the equivalent of a controls here you want to stop processing。

It's important that the receiving and stop taking in the data and processing it。

 You will had the ability to then send some data。With this urgent。Bite flag or the urgent flag set。

 And the urgent pointer saying。Here's this data is urgent。

 you need to pass it up to the application immediately and it would bypass any bytes that had arrived before it。

 and it would not necessarily wait for all the bytes to be received。

As far as I know not used very widely， but that was the original reason for having it。

We have some options that again， we are not going to go into those either。

 but there's a set of options to specify additional things， one that as an example。

 we've talked about selective acknowledgecledments as something that approximates full information acknowledgegments that was added to TCP later as an option。

So TCP options are there to allow evolution of the protocol。 But again。

 we're not going to talk about them in discuss class。 So that leaves us with these flags。

 And I'll get to that just in a minute when we talk about the connection setup。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_78.png)

And da。Next one on our list was congestion control。 Were now going to talk about that today。

 There's one question for you， those the congestion window。 there's no place for it in the head。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_80.png)

Did we need it？Why do we not have a congestion window in the head of？Yeah。

 the congestion window is the sender figuring out at what rate it should send。

Traffic into the network。The receiver doesn't need to know it。 It's irrelevant to the receiver。

 and the receiver doesn't have input into that congestion window calculation。

 So congestion window is just this algorithm again at the center。

We don't need to communicate it between send and receiverce。 So it has no place。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_82.png)

In the DCP header。So the last one is connection establishment and sequence numbers。

 So let's start with this at a fairly high level。 and then we'll actually look at what headers look like as you're setting up connections。

 This， again， is sometimes confusing to people because there's a fair amount of detail in what's happening。

 So the high level TP connection establishment follows what we call a threeway handshake。😊，Okay。

 and it's used to initialize state at both ends， but also to exchange initial sequence numbers between A and B。

 So the way this looks at a high level is it starts。

 And this is why it's called a threeway handshake。 That three steps。

 The first step is Hoste is going to tell B， I would like to open a TCP connection。

 It does this by sending a S message。 This is a synchronized to set up a TP connection。

So we call this a sin packet。B responds if assuming B is O， setting up a connection。

 B responds with what we call a sin act。And the reason it's both is it's doing two things。

 It is one acknowledging be is acknowledging that it received is request for a connection。

 That's the a part of it。But B is also sending its own send message because remember。

 we said TCP is bidirectal。So the first sin going from A to B。A is telling me。

 I would like to send you data。 And here's my initial sequence number。The S Act B is telling A。

 got it。 You can send me data。 And here's my initial sequence number。

 because I would like to be able to send you data as well。So it's both a sin and an acknowledgement。

 And then finally， a will acknowledge。B initial sequence number saying。

 I got your initial sequence number。 I'm ready to receive data from you， as well。

So this is where we see the full duplex nature。Any questions on the high level setup。

 we'll then step through headers and how this gets done。So it's a handshake。

 They've agreed to set up a connection。TheyEach one has each side has told the other side what initial sequence number it wants to use。

 and each side has also acknowledged to the other side that they've received the initial sequence number firm the other。

Enpoint。And then once you have this clleway handshake is set up， you can start sending data。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_84.png)

So let's look at that in in terms of the TCP header。 And now we're going to expand。

This field here that we had called flags。 And so ignore the bottom4。 for now。

 just focus on there are two flags。 So theyre 1 bit each。 One is a sin flag。

 and the other one is an act flag。 When you set it to one。

 it tells you that this packet is either a syn packet or an act packet or both。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_86.png)

So let's start with the first step in that three way handshake。 And first。

 let's get a few things out of the way。 So what is in this header， We have A sport and B sport。

 right We know what those are。 We have no options。 And so the header is length is just 20 B。

And now let's focus on this is the first packet in the first packet in that handshake。

 So it's a Sim packet going from A to B。 So the source is A port。 D is Bs port。 The Sim flag is set。

All of the other flags are not set because it's not an acknowledgement message and ignore the other folk。

And now look at what these fields are。 The field here for sequence numbers is initial sequence number。

Okay， so this is how A And B are going to synchronize on the sequence numbers that a is going to send to be。

The acknowledgement field is not relevant， because we've not set。The acknowledgeknowledment that。Sa。

 okay。对。No。So there's no payload because you're not sending data yet。Okay， I'm on step two now。

So now we are at the stage where B has received the sin。

 and remember it's sending back what we call a S act right so let's step through this。

 It's coming from B。 So the source is B port。 The destination is a's port。 Important。

 we are now setting two bits in the flag。 So it says that it's both a send message and an act message。

The sequence number is now B's initial sequence number。对。

This is how B is going to start numbering its by stream。And at the same time。

 it is acknowledging iss initial sequence number plus one， the plus one。

 because we're doing next expected byte。This is also why when a starts sending data。

 the very first byte in A's byte stream is going to be initial sequence number plus one。

Anyone want me to repeat this？是て。So at this point， B has told A that it accepts。

 and it's ready to hear the next bite。嗯呃。I think I step up and so on receiving this packet。

 A now knows that it's good to start receiving。 It can start sending data because B knows what what the by stream numbering should look like。

And so， the last。Step in this threeway handshake is， A is now acknowledging the synyac。

So this is kind of his way of telling the， I heard your initial sequence number。

 You can start sending me data。 And so what this looks like now， we have only the a bit set。

There's no sin here。 We're not exchanging initial sequence numbers anymore。

And so this is coming from a。 So A is port， source port， B is the destination port。

The sequence number doesn't matter because it's only an act and the number that A is acknowledging is B's initial sequence number plus one。

行。Are we good。Good question。I believe you would get it fear from on the ax。 Well， is it set on this。

 Let me get back to you on that1。 I don't know。 I know when you start sending data and you're acting data bys。

 your advertise window would be a valid field there。

 I actually don't know whether you set the advertise window as part of the handshke。 any of you know。

Okay， we'll get back to you on that。你看。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_88.png)

Any other questions？Okay， so last bit is we're going to now talk about tearing down that connection。

 So we've set up all this state You do need at some point to delete the state when your transfer is done or for whatever reason。

 you want to tear down the connection。 So this is where the last。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_90.png)

Two flags that we are going to consider come into play the Fin。

 which is the finished and the reset flag。

![](img/9dd914a828c6ba8b6ebecfaa076116ae_92.png)

the way this works is actually pretty straightforward。

 though it's been exploited for byseity attacks so many times that it took a few iterations to get it completely right。

 So in your connection here we've done the threeway handshake。

 we've sent data we've gotten X and now let's say that a is done。

 It's finished sending all of its data。So what it's going to do is， it's going to send a finish。

 This is kind of a graceful termination or what we call normal termination。So a is going to send a f。

Which is a Finn message to be。This is going to acknowledge。That f。 So it's going to say， I get it。

 You're done。 You have no more data to send me。At this point。

 we say that the TCP connection is half closed。Okay， we understand that A has no more data to send B。

We don't know anything about whether B was done， which is why it's half closed。

 You cannot delete your state at this point。 Okay， so it cannot just tear down the TCP connection and say I'm done。

OkaySo instead， a is going to wait at some point， B is going to send a thin message to a。

This is now B telling a， I'm done sending you whatever data I wanted。

At which point A will acknowledge that it received the Finn。

And then it waits for some time out period and then deletes all of the connection state。

So this is one normal termination where each side is taking turns to tear down or close the connection whenever it's done sending data。

There are more complicated wagons where both sides can be sending fins at the same time。

 We're not going to get into that。看。Oh。Yeah， either side。 So I should have said this。

 either side can send a f whenever it's done。But it would play out in theosland。Yes， so B。

 let's walk through that。 So if B sent a f to A， what is that telling us。

 That is telling us that B has no more data to send A。

 but B is still expected to be up and acknowledge any data that A sends it。

And only when A is done sending， which is why we say the connection is half closed。

Because a side is still open。 and it doesn't matter which side is done first。Does that。Make sense。

Okay， so then the other type of termination that's relevant is what we call an abrupt termination。

 or you've probably heard of your TP connection being reset。 That's where this comes in。

 This is gallly when a pretty drastic form of terminating a TP connection。

 either side can just send a reset message to the other side。And when you send a reset message。

 that's it。 So typically， the the。Example your people give Oh actually。

 let me get to that in a minute。 So the behavior is just either side can send a reset。

You don't have to acknowledge the reset if the reset is not delivered reliably， that's fine。

 Any data and flight， there is no guarantee that it gets delivered。

 if the other side continues to send data， you can continue to send resets back to it。

Why would this seem useful？That was the intended use， and then there's the current use。

 But let's first talk about the intended use。The intended use， you know。

 typically imagine that A had rebooted or restart or your process crashed and you reset。

So when A rebos and comes up， it no longer has that connection state。But B doesn't know this。

 And so B is sending data to a。So sometimes A receives a TP packet from B that it has no connection state for。

 It doesn't know what to do with this packet。 so it just sends a reset message back to B。

So it's a way of telling me， I don't know what you're talking about。 We close your TP connection。

 Stop sending me data。The way this is often used today is for censorship。 So， you know， China。

 Iran is a lot of them。 they are looking at data going through and usually they will let your connection open because just looking at。

 let's say you have a connection from a censored country leaving the country。

The censorship or the like the firewall is going to let the connection be established because just setting up a connection。

 you don't know whether the client is violating you know what the censorship rules they're trying to impose。

 You don't know that until later in the connection。

 So they let the connection get established once they've decided they don't want that connection to continue the。

The firewall or， the censorship。Box that's implementing censorship will send a reset to the server side。

Not the intended use， but。Not an ideal use either， but that's where you see a lot of resets。

Any questions？I was just animating that if you continue to send data， you'll continue to send resets。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_94.png)

So this is actually， if you put all of what we've talked。About in terms of how TCP gets implemented。

 this is a partial view of the state item。 And TCP is actually not complete， even in this。Figure。

 as you can see， it's pretty complicated。It's also worth pointing out that all data messages and acknowledgegments will take place within this established state of the TCP state AA。

 so there's a whole lot of additional complexity internally within that established state。

 so acts and congestion control， all of that is buried in there。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_96.png)

So pretty complicated， we're not going to do stare at it offline if see how much of it you can。

Figure out。 We will typically work with this more simplified view of the client side。

 So let's step through that。 If you're closed， you send a sin message。

 This is the beginning of the threeway handshake。 at which point you enter this S sent state where you're waiting for the acknowledgement when you receive a S act。

 you send an act in turn。 and then you're in this established state。

You send data and acts while you're in this established state。Finally， when you're done。

 you send a fin， you wait。 when you receive an act， you can't send anything more。

 You are now waiting for the other side。To be done when you receive the f from the other side。

 then you send an app。 You wait for some time， and youre closed。

So this is at the client side or at the centre side， kind of a simpler。View of the DCP State Dago。

Any questions？

![](img/9dd914a828c6ba8b6ebecfaa076116ae_98.png)

So， with that， then。In summary way I think we're mostly done with TCP other than the congestion control part which we'll do in the next few lectures overall I think TCP is not perfect but an elegant piece of engineering there's a lot of thought that goes into TCP and actually every time I teach it I look at this and I'm like why did they do it this way again and I have to myself go back and read some of the history of why it was done a certain way。

 I think a nice thought experiment for you to do on your own time。

 Think about whether you think TCP will continue to be a good solution。

I actually don't know the answer to this。 I think it's an interesting one to think。

 it's kind of remarkable that TCP predates even the web and pretty much any use that we have for the Internet today。

But the world has changed right we have ML， we have IOT， we have security concerns。

 we have sub drivingiving cause。 is TCP really the transport layer protocol that's going to carry us through that。

 There have been many times where people say TCP is not the ideal solution。

 but it's actually done pretty well。 So think about why TCP there will be the answer or will not be the answer if you have thoughts I would love to hear them。

There has been in terms of the history of TCP。 What we've studied is actually pretty much a large fraction of。

A pretty good snapshot of what TCP actually does in practice。

 There has been lots of evolution in individual pieces of it。 So in particular。

 congestion control is an area that has seen tremendous evolution and innovation and continues to have it。

But a lot of the core building blocks are just the way that's divided up the problem with by streams and windows and being connectional weiented setting up and tearing downstate。

That's how TCP continues to work。 And so Winsurf and Bo K vote the TCP implementation， I believe。

 in the late 70s。So it's actually quite remarkable that it's held up as well as it does。With that。

 any last questions on TCP or transport or anything yet。Yeah。

 I actually did not tell you how the IN gets exploited as a vulnerability。

 It's a pretty long and complicated attack。 We're not going to cover it。

But what it was exploiting was the fact that you could have， let's say， host A talking to a host B。

 So it's a client opening a connection to a server， and you could have the attacker。

If it knew roughly at what time the the A has opened the connection to B。

It could guess what that initial sequence number was going to be， and it could inject。The S act。

And provide its own initial sequence number。 And then the server would actually talk。

To the attack again。There's a bit here about， you know， don't the voice messages go back？

To the the victim or。 And that's why the complexity is。

 is that they exploited a fact by which the reset could get ignored by the server。By。

 this was exploiting a particular implementation artifact at the server side where if you had a lot of traffic。

 it would actually let the reset be lingering somewhere the back of the queue。

 So we're not going to cover that attack。 It's much more involved than what we're doing。

 And it's not just TCP。 It's also how the O was implementing TCP。And no， so the。

I'm not going to be able to re create。 It doesn't have to do with the reset having the ISN。

 The fact what it was exploiting was that the attacker could guess what the ISN from the server was。

That if the attacker had opened a connection to the server， they knew what its ISN at point A was。

 And because it could predict how the server was going to increment its ISN number。

 it could guess how another client。Connection what I S N value it was going to see。

 And then it could hijack that side of the connection。You would have to be able to。 one。

 you would have to。Be able to。Spoof the source that you're resetting from。

 which if you're like the great firewall or something， you actually are on the path。

So you have to kind of see the connection to be able to send asa。Any other questions？Thank you。들 걸。



![](img/9dd914a828c6ba8b6ebecfaa076116ae_100.png)