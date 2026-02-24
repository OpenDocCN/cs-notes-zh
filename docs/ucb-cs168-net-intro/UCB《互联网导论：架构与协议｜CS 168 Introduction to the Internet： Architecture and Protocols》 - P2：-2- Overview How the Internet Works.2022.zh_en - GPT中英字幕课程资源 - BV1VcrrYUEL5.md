# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P2：-2- Overview How the Internet Works.2022.zh_en - GPT中英字幕课程资源 - BV1VcrrYUEL5

Okay， so goal for today and actually the next few lectures， as I mentioned last time。

 is to try and give you a pretty broad overview of how the internet works。



![](img/b158913dc64b59abbf77cacc8d27c109_1.png)

As I mentioned again， last time， people tend to or textbooks。

 even tend to do this one of two ways either they go top down。

Meaning they start with this as the internet as a whole。 let's start looking at what's inside it。

 or they go bottom up， which is they say， here's a link。

 I'm going to get data across a link and build up from that to the internet。

We're going to do it both ways。 So this lecture， we're going to start bottom up。

 So we're going to start very low level with individual links and bits flowing across the link。



![](img/b158913dc64b59abbf77cacc8d27c109_3.png)

So goal for today is to cover four topics。The first is we're going to look at how is data organized or transferred across the Internet。

Then we're going to get to what is really a very， very fundamental question almost even before you start building a network。

 which is， how are we going to share network resources。

 So how are we going to share in terms of users in terms of applications。

 in terms of bits on the wire and so on。And along the way as we're going through this。

 we're going to start to understand what we call the life of a packet。

We haven't yet talked in lecture about what a packet is。

 I think your Ts gave you a preview and discovered it as the life of data as it flows through the network。

给。And。In that way， along the way， we're also going to identify what the core topics that we're going to cover this semester are that we're going to spend to a deep dive on as we go along。



![](img/b158913dc64b59abbf77cacc8d27c109_5.png)

So with that， let's start with this picture that we had from the last lecture about what internet infrastructure looks like and as I said that three main components we have EnHs。

 we have switches， and they're all interconnected by links。

And we also said that the Internet really has just one basic task that it performs。

 And that's to transfer data between endhor。And so we had this picture where we said we have data here。

 we have a path， data flows along that path。Can I ask you。Okay， so at the beginning for this lecture。

 we're actually going to ignore this entire big picture。

 and we're going to hone in here on this one teeny， tiny piece of this picture。



![](img/b158913dc64b59abbf77cacc8d27c109_7.png)

And that piece is we have an end hosts's connected by a link to a switch。

And we want to transfer some data across this one link。And we're going to start with， again。

 we said data that， you know， we're running applications on the Internet and applications have data。

So let's say that in this context， we have this image。

And the end hostt wants to send this image over the Internet。So very basically。

 the first thing it's going to do is it's going to construct what we call a packet。

And a packet is a unit of data that gets transferred across the Internet。

And maybe what we're going to do is take actually just a portion of that image。

And put those bits that represent that image into this packet。Why a portion。

 I'll get to that in just a minute。 But for now think of it if I'm going to take some chunk of that image and now I have a bag of bits that I'm calling a packet。

If I were to send this out into the network。What is the switch supposed to do with this， right， It's。

 it's just a bag of bits。 It represents an image。The switch doesn't actually know what to do with it。

And so we get to what is actually especially for us in this class， the most crucial part of a packet。

 which is we're going to have this little additional portion that we add to every packet where we're going to put metadata in。

 this is any information that tells the switch or tells the network how to handle this bag of this。

 how to handle this packet。And we call that a header。

And we're going to talk at length in this class about headers and what in goes into it。

 And why is it so important， This header， you can think of it as it carries the instructions。

That tell a switch what to do with a packet。So it's the set of instructions that the end hostst uses to tell the network。

 to tell switches what to do with the packet。And it's also the set of instructions that a switch will then use to tell other switches what to do with a packet。

So to repeat that when a switch receives a packet， it's going to look at the header。

In order to know what it has to do with this packet。

And it's also going to use the header to tell another switch what it should go on and do with this packet。

AndSo when you write code in general， you tend to think a lot about APIs and we've all heard a lot about the value of a good API。

 what parameters go into the API and so on and how crucial it is to actually writing a good function before you write the details of the function。

 you actually often write the API and you。Cirulated and ask people， is this about API。

You can think of the header in some sense， as the API to the network。

It's even more crucial than in your software because this is an end hostt telling us which they are two different entities built by two different parties what it should do with that packet。

And it's also much more crucial because this function is implemented by the Internet at large。

 by all the switches in the Internet。So that's why we obsess so much about headers。

The rest of the packet， those bits that came from that image， we're going to call a payload。

By and large， the payload is clearly application data。

 It's data that the network typically doesn't really care about。 It doesn't need to understand it。

 It's just what one end host wants to send to the other end host。The end host care about it。

But the switches don't have to。And that's actually part of where the generality of the Internet comes from。

The fact that you don't care about what application data is in the packet。

So one other point I should tell you is that typically packets are not all the same size。

But there is typically an upper limit on how big a packet can be。

That upper limit tends to come from a variety of different reasons。

 but typically because of the particular link technology that you used。

So the most common one is ethernet。And Ethernet has a what we call a max size。

 and we'll talk about this at length when we talk about ethernet， but has a max size of 1500 points。

And this is why if you go looking at packets on the Internet。

 there's a large number of packets that are 1，500 by。

The wfi has its own upper limit on how big a packet can be。

 Fiber technologies have their own upper limit， and some of this is also historical。

 the reasons why Ethernet had 1500 bytes doesn't quite apply anymore， but we're still just used to。

 it's worked out well and we' used to using it。This are not all packets are going to be the same size。

And but they can't be as large as you want them。 There is a gap。

 And that's why I had to take a portion of the image and put it in one packet。嗯。

Can will all packets be the max size， What do you think？

So I said Ethernet will allow you to send 1500 bycycl。Some' shaking the head。Right。

 so if the size of the image doesn't divide by 1500。 I'm going to have some leftover bys。

 I'm going to send them along。 Any other reason why I might have fewer than 1500 by in the by。

Balancing load in terms of how much load you put interesting。有。Close the book， Why not？

The header will take some bits。 So that's right。 when I say packet size。

 I'm actually usually referring to the sum of the header and the payload。

 So what I can put into the payload is the maximum minus the header， but very good points。该判断。

Any other thoughts？Good point。 Hol on to that thought because we'll get to that in a couple of lectures。

 but your point is correct， which is that there might be things other than pure application data that you wanted to send。

 you might have wanted to send， for example， to check some over the image to show that the bits were not corrupted or something to authenticate the data and so on。

 So yes， when I say application data at this point you know can think of it almost if anything the application wants to send it doesn't literally have to be those bits in that image。

Any other reason is all good reasons。Yeah， okay。 so the the point raised here was。

 I might just not have that much to send。 right If I'm just saying， yes， I got the data。

 maybe that's like 30 bys，40 bys。So I just want to send that data because what would have been the alternative。

 The alternative would have been to say， I can send 1500 bys。

 I'm going to wait until I have 1500 bys worth of data to send。And that's slowing the application。

 And I might never have that many partss。Or in something like an audio communication。

 I have a small number of bytes to send。 I really don't want to delay it。

 So I want that flexibility of sending fewer bytes in a packet。



![](img/b158913dc64b59abbf77cacc8d27c109_9.png)

So trust your hi packet you can think of it as a chunk of bits。

It's made up at a high level of two big pieces， payload and the header。The payload is meaningful。

 only to the endpoint。Could be bits from a file video， or whatever the application wants to send。

 The header， on the other hand， is meaningful to both the network and the endpoints。

So now let's start to think about what should go into the header。

What do you think is the most important piece of information that has to go into the head？

The location you're sending the packet to， can I call that a destination or a destination address。

 Yes， absolutely anything else， I would say that is the most crucial piece of information you have to get right and you have to get into the header。

 What else might you want to send in the header。Going to live himo。 What is。又回。Very good point。

 let me try to。 We're going to get to that many lectures from now。

 but the idea is that let's say your packet was having trouble going through the network and maybe it was going down in circles and the switches were confused about how to forward it。

 You don't want that packet to circle and loop in the network forever。

 So there's the idea of a time to live that well kind of say you know this packet has been in the network long enough。

Put it out， something's wrong with it。Anything else？So the source of the packet。

What do people think do we have to have that？For example， did we have to have the thankula as well？

That's completely， true。 I'm just。Trying to unpack the decision a little bit。

 Do we need the source address。Okay， so the answer is yes。

 because how else does the source know how to respond， Any other thoughts， anyone disagrees yep。Yeah。

 so the thought was， well， we don't strictly need it because if the end host is the one that needed the source address。

 I could have put it in the payload because remember。

 the destination is going to look at the payload。So the network did not need to know the source。有ep。

Nice one to catch Okay so if we don't think about TTL or error conditions。

 then I would say you're kind of both right in the sense that it is convenient to put the source address in the header because most communication tends to you know you send a piece of data then you have a response。

 so isn't it convenient to have the source address there。😊。

What you would expect to all communication needs。 Let's put it in the header。 That's absolutely true。

 It's about convenience。 So the person that said， well。

 it wasn't strictly required because I could have put it in the payload and that way the destination would have known how to send the response back it's also correct。

 So if we were saying that's a strict requirement。 No it's not a strict requirement that you have a source address But then we had yet someone else has said。

 well， actually if I combined what somebody said before。

 which was this packet has been in the network too long。

And I say that I want to send an ego message back to the source so that it knows。

 which is not necessarily what the Internet does。Then I would want the network would want or would need to know what the source address was。

So if the network sends a signal or an error back to the source。

Then I'm going to need a source address in the header。 So that's actually a strict requirement。

I'm walking you through all these things not to make it sound complicated。

 but to make you realize how even a decision like， do I need a source address？

You have to think why you need it。 And is it required， is it convenient why youre putting it in。

So we do have， for the most part， those addresses in the head。

 Is there any other reason you can think of that's not come up。We're changing fields now。

 protocol type， yes。他 enough反过。Sip explaining that in the interest of time。

 We'll get to protocol types。Down the line。 So this would be to tell the network。

 This is the type of protocol I'm running。 Is it IPP 4。 Is it IPP6， So I am actually explaining it。

 And it is useful because if we say that a protocol has to evolve。

It's kind of like a version number you have to know which version are you dealing with or what protocol are you dealing with。

 So having a protocol type would be useful as well。 And we do have that。Okay， I think of。

Cover this at length at this point， So we absolutely need the destination address。

No doubt about that one。In practice， a few simplifications that you we'll start getting into later in data sections。

 most packets will typically have multiple headers， not just one。But for today's lecture。

 let's just assume there's one header and there's payload。

And another concept that comes up repeatedly again and is very useful to know is this notion of a flu between two endpoint。

Because just as you saw that there was actually an image， an entire image to send。

 and I only got to pack a sub a portion of it into one packet。So in reality。

 there's going to be a stream of packets。That are kind of all were in the sense that they're all part of the same communication between the source and the destination。

And so we use the term flow to refer to this stream of packet。



![](img/b158913dc64b59abbf77cacc8d27c109_11.png)

With that， let's get to now actually putting that packet on a link and what's involved there。

 And so from now I'm going forward， you know， we started with this application data。

 but I'm only going to be talking about packet。And I hope in your heads。

 you understand the connection between application， data and packet。And if you don't。

 then stop me now。But so now let's get into， we have a packet。 It has an address。 for now。

 I'm going to say its address is UCB。 That's not what actual Internet addresses look like。

 but let's say this。And then there's some set of bits that we're not going to care about。

This is a good time actually， to talk a little bit about a link。

Let's look at what what goes into a link。 And typically。

 a link is characterizedized by three properties that。Capture the performance of that link。

The first is this term you've all heard about bandwidth。

 like we all say I have a gig of it the second。5 G is going to give me。5 gigab per second。

But you we we talk about network speeds in terms of bandwidth。

It's how many bits per second you're hoping to get out of a link。

So the bandwidth has given the number of bits per second that you can put onto the link。

If you think of it， the analogy I like to think of as a pipe and you're putting water into the pipe。

And so your bandwidth is like the width of that pipe。

 It's how quickly can you put water into that pipe， The wider it is。

 the faster you can put water into it。It's exactly the same with a network link。

The higher the bandwidth， the faster you can put bits the bits onto that link。

The second metric we talk about is the coag delay。 This is the time it takes for one bit of information to travel along the link。

 to go from the beginning of the link to the end of the link。Again。

 going back to our analogy of a water pipe， If I put a drop of water into the pipe at what time did it come out on the other end of the。

So this is dictated by physics。 It's just how long does it take a bit of information to flu on a pipe？

And then lastly， so you can think of that again as the length of the link。

 And then the last property is just the multiplication of those two。

 It's what we call the bandwidth delay product。If you take that bandwidth and you multiply it by the co delay。

 and that gives you your bandwidth delay product。 We use it on BP。Often to talk about this。

And when we get to congestion， control or sharing network resources。

 these concepts and PDP in particular， is important。What does the BDP signify， the BDP。

 you can think of it as the capacity of that link。 so again going back to our analogy of a water pipe。

 If I did not take any water out of the pipe， If I blocked it at one end and I filled water。

 how much water could I put into that pipe， thats。The BDP or the capacity of the link。

So I cut the link on the two ends and I looked at that link and I could see how many bits I could pack onto that link。

How much information is actually on that link， that's the。So those three。

 these three properties really critical that。You fully internalize what these mean because they have a lot to do with reliability。

 delay calculations， congestion control when we get to that later in the lecture。



![](img/b158913dc64b59abbf77cacc8d27c109_13.png)

And so let's actually walk through。One packet going across one leg in the context of these properties。

So let's say I have 100 byte packet， so 800 bits， and my length is a megabit per second and 1 millisecond。

One way that we're going to use to understand performance and know networking protocols in general is with the help of these kinds of timing diagrams。

So what I'm going to show you here is time going down。It's time， it's moving down。

 and as I go down the timeline。And I'm going to show you the time。

 the events that are taking place at the end hosts and the switch as we go down in time。

So let's say if I'm sending this 100 byte packet at time zero。

 let's say let's think about that very first bit of information we're putting on the link。

I said my link has a bandwidth of 1 MB per second。 That means I can put a million bit。In one second。

I can put a million bits onto the wire。That means that to send one bit。

 it takes me over a million or one microsecond。 So after one microsecond。

 I have that one bit on the wire。That bit is then going to travel across that link。

The time it's going to take to go across that link is the propag delay。 So that's 1 millisecond。

So at 1 millisecond plus at one microsecond， that first bit has a right to the packet at the。

I had 800 Bs to send。 So it's going to take 800 times one microsecond。

 So the end of 800 microseconds。嗯。I would have sent all of my 800 bits。

 This is the point at which I can say that the end host has finished transmitting the bucket。

That 800th B is then going to travel across that length。 It's going to take that 1 millisecond。

And so the last bit is going to reach be at that 800 microseconds plus 1 millise。

This is the point that 1。8 milliseconds is the point in time where I can say that the switch has received the packet。

It has rotate all the bit in that packet。

![](img/b158913dc64b59abbf77cacc8d27c109_15.png)

So that gives us this calculation where we say the packet delay is the transmission delay。

 That's the time to put the bits in the packet on the wire， plus the propagation delay。

 which is the time for those bits to travel across the wire。And the transmission delay， in turn。

 is the packet size divided by the link family。Okay， so this is my delay across a single link。

As we go in the semester， we're going to start talking about delays that packets experience as you go across a series of links。

 but it all builds on this。 Any questions。How do the bits actually get onto the link and how do they get transmitted？

 This is really the E physical layer side of a link。 Different links have different technologies。

 For example， a fiber link， it has a laser on it that is doing whatever lasers do to convey that light through the link。

AtWifi， you have different types of signals， even at has different。

We're not covering those in this class。Yeah， this is again actually a physical layer question different。

 if you actually dug into how a particular link works。

 different links has slightly different ways of doing this。

 some of them will take four bits and encode it slightly differently and then send out four bits and Bible others it really is a serial link it's one bit at a time。

 we tend to abstract that away for this class and we just say this is your bandwidth。

 which is you know for your purposes you can think of it as 1 million bits per cycle。

Without worrying about exactly how those bits got off。Any other questions？

So you'll be doing a lot of these calculations during sections。

 so you don't worry about the exact math of it， but I do want you to understand how these parameters fall link matter。



![](img/b158913dc64b59abbf77cacc8d27c109_17.png)

So here's a question， let's say I give you two links， you get to choose which of these two links。

You get in your house， for example， let's say your IP is offering you these tool link options。

 One of them has a bandwidth of 10 MB per second and a propag delay of 10 milliseconds。

The other has  one megabit per second， and the delay is 1 millisecond。

 So it's 10 times lower in bandwidth， but it's 10 times。Faster in terms of the coag delay。

 Which one do you think you want， Take1 seconds to think about it， and then。んですか。Buts。Which。Yep。Okay。

 so we have someone who like linked too better。 Anyone disagree or agree or want to add to that。De。

Right， as you say right， So the answer is it depends。 you were also right。

 the answer is still it depends。 So it depends on what workload you had in mind。

 So let's take an actual example to see that。 Let's say that I had computer。

 Let's compute the package delay for 10 B packet。Okay。

 that's the analogy to the doorbell that you had in your answer。 So if I had a 10 by packet to send。

 and if you readed the math。What you would say is that with link 1。

 it took you 10 milliseconds for exactly the reason you described。

 which is I only have 10 by by to send it。 It's not a wholes not a lot of bit。

 And so my transmission delay is not that high。But then the time for those bids to travel across the wire dominates。

And so in this case， link one， which had a high propagation delay， does worse than link2。

 with that time for those small number of bits to travel was just1 millisecond。Right，So in this case。

 link2 is looking better。On the other hand， if I said I have 10 kilobytes， 10。

000 bytes to send a class at Y。And if you redo the calculation。Now， actually。

 link one is looking much better。Because I have 80，000 beds to put on the wire。

And so my bandwidth starts to matter。 My bandwidth is， remember。

 how quickly can I put those bits on the wire。And so if I only had  megabit per second。

 I'm taking a long time to put those 80，000 bits on the wire。And yes， then they travel。

 But the dominant factor is the time it took me to actually transmit those。

This is why sometimes when you're on a Zoom call。And you're not， things are breaking up。

 you turn your video off。In that case， if you'd had a better。Higher bandwidth connection at home。

 that would have helped you。That video， which video consumes。A large amount of bandwidth。

Then your video would have performance would have been better。On the other hand。

 if you're on an audio call with someone that's across the globe and you can hear a delay that。

 you know， you say something to them and then clearly they hear it after some amount of time。

That communication， the reason it's not doing so well is because of the publication delay。

So you could go to your ISB and upgrade your link， it's not going to help you。

It's just the delay that it's taking across the Internet for those bitetes to go。

 That's what's causing you that effect。So both matter。 And what。



![](img/b158913dc64b59abbf77cacc8d27c109_19.png)

It matters on is how much data you're sending。I want to give you one other way of looking at packets on a link。

 So so far we've been talking about these timing diagrams。

 The timing diagrams are useful for you to understand the events happening at the two ends of a link。

It tells you what each different the different entities in the network when they're seeing different events。

A different way to look at it is to look at it from the length perspective。

So remember we going back to our picture of the link as a pipe。

The width of the link is the bandwidth， the length is the propagation delay。

 and the capacity is the bandwidth delay product。I could take exactly this picture on the left。

 and represent it。In the one on the right。Here's showing you packets occupying that link。

And where on the left I had the packet transmission time。

 This was the time it took at the end host to put the bits on the wire。

That time now turns up as the width。What portion of the link is that packet occupying。

That is your transmission time。When do you think we're going to use the figure on the right？

When is the peaceful。也。When you how are you sharing resources right from the picture on the left。

It's a little harder to get an impression of how busy is your link。

when you look at the one on the right， they actually tell you the same thing。

 So it's not that there's information one that's missing in the other。

 but when you look at the one on the right and you see a large number of different links。

The leftover space on that pipe immediately tells me how much capacity I have leftover。

 So it's visually a very easy way to get， I think。So both useful ways of looking at packets traveling through a network。

 and we're going to use both ways as we go through this semester。



![](img/b158913dc64b59abbf77cacc8d27c109_21.png)

Any other questions before I move on， actually I had one。

Let's pose for questions after this question。 So here's another exercise for。 here's my link。

 It's 1 mebit per second，10 milliseconds。As the propagation delay， I want you to think about just。

 you know in your head or Doodle， what would this picture look like if I said that my link is 1 mebit per second。

 but now has a propagation delay of 5 milliseconds。

And then also think about what this picture would look like。

If I told you you have 10 megabits per second or 10 times the bandwidth。

But your propagation delay is 1 millisecond。喂 pot。What should the one on the left look like。

1 megabit the second and propag delay of 5 milliseconds？Why should we have this shop， exactly。

Does this make sense to anyone， Does anyone want me to explain this？

All I've done is shrink of the applicationly， what about the one on the guide？

What should that one look like。So its this is not to scale， obviously。

 but it should be 10 times as wide and because I could send packets so quickly onto the pipe。

Each packet is the comeback skinny when I look at it on the pipe。

Kin of stretched up because I didn't take me much time to transmit it。

And that's why these Pakistan nowgo is tall and skin。



![](img/b158913dc64b59abbf77cacc8d27c109_23.png)

Okay， so to cut packets on a link， we have this packet has a header and a fieldload。

And we now know how this packet is going to make its way across that link and I guide to the switch。

So now think into a little bit， what are we going to do at that switch？So remember。

 a switch is defined by having a number of interconnecting links。

So it locally has a number of links that connected to other switches or enforce。

So when the packet arrive with the switch。What is the problem that this switch has to solve。

 So the packet it looks at the header and it says this packet is going to use CV。

UCB is somewhere on the Internet， somewhere in this network。

Some of its neighboring switches are going to take it towards B。Other than not。

So what the switch has to know is which of its links。

 and I'm going to number them here for convenience。It's going to take this packet towards Berkeley。

The switch doesn't really need to know exactly where Berkeley is。

 All it needs to know is at this point with this packet， which link should I forward it。

 sendend it out on。And in order to do that， the way we're going to do that is that every switch stores what we call a forwarding table。

This is just a table that for now， we're going to say all it has in that table is a destination。

And corresponding to every destination， which of my local links or my immediate links is going to take me towards that destination。

so now this packet is right。 I took out the switch take card UB。

 looked it up in the table and there's aha link number2。 I'm going to send the packet onto to link。

And then the next switch is going to do the same thing。

So this is what we call a forwarding table and what the switch has just done。

 we call this operation forwarding a packet。So switches forward backward。

That's what the O packet task data switch does is。So to Gicap。

 let's start to build that life of a packet now that we understand a little bit more。

 life of a packet， the source has some destination data that wants to send a destination。

 It chunks it up into packets。 Each packet has a payload and a header。

 the packet travels along a link。 It arrives at a switch。

 The switch looks up the destination and its forwarding table。

Forwards the packet to what we call the next。So it sents it out over one of its links。

And then I'm going to repeat these last two steps until the packet reaches the destinationation。

So this is。Kind of life of a packet as a starting point。

 You now understand how a packet goes from point A to point8。



![](img/b158913dc64b59abbf77cacc8d27c109_25.png)

Let's think about what are some of the fundamental challenges in this so you know I put this picture up and I said we have this packet。

 we have this forwarding table and so on I glossed over a large number of details when I put this picture up Anyone want to speculate on what some of the challenges I have。

So how at the scale， Am I really going to have a table that has an entry for every single destination？

 So how do I scale this forwarding table， Yep， anything else。

You might have two parts to the same destination。 fancy。 But your guys， absolutely。

 That's something we call load balancing。 we'll get into later。

 So what if I wanted to have more than just one link。That I could send， used to send。

that definition to the back。What happens if you lose data， Yeah， How do I。

Let me turn that around a little bit to say， when do I lose data。

 or what would cause me to lose data。In this context。あやep。Right。

 so what happens when a link goes done is my forwarding table， you know。

 I had a forwarding table that said got over link to， but maybe link2 was actually done right。

So how do I make this decisionep？But where did the stable come from。

 I just magically thought I have a forwarding table。How did I get it。How importantly。

 how do I maintain it at link。よ。I'm looking for one。Yeah。Loops， as I was forwarding。

 how do I know that my forwarding these w actually take me to the destination yes。Wellal。

 not the one I was talking。Okay correct。The one I was looking for was where did this address come from？

How did the source know what address to use for Berkeley and kind of cheated in the sense I said Berkeley so you can imagine that sources know where they want to send their packets。

 But in practice， we know we're not going to actually have books and destination address。

 So where did this address come from， What does it actually look like。

 How do end hosts discover the addresses of other end hosts that they want to talk to and so on。

And then just a whole host of information of challenges around this question of this forwarding table and many of you brought it up。

 where did it come from in the first place， How did we calculate it， how do we know it's correct。

 how do we maintain it as links go up and down， how do we make it scalable。

 how do we make it secure and so on。

![](img/b158913dc64b59abbf77cacc8d27c109_27.png)

Those者 some。Problems we're going to be studying in the next few weeks。

 So the first is addressing and naming。So in the real world。

 we all have names and we have addresses like my name is Sylvia， my office address is 413， Soda Hall。

When I， let's say I moved my office to now sit in Koy Hall。

 my name stays the same but my address changes。And in the other world we like， you know， you don't。

 I one referred to me as a person that's sit in so。You would rather talk to me about me as civil。

And so in the real world we have names and addresses and exactly the same way on the internet。

 we host have network addresses。 This is where on the Internet topology is this host。

 Where can I find this host on the Internet。And separate from that， that host will also have a name。

Which is， what is this host。So for example， when I say I want to talk to Google。com。

That means a server whose name is Google。com。But that serverber lives somewhere on the internet aology。

 that is its address。And so we need a naming and addressing scheme that works at Internets。

Because remember on the Internet， you can reach any host。

So unlike the real world where nobody outside a very small set of people know what my address is on the internet。

 in principle， we want to be able to reach any host of me。So how do we discover their names。

 how do we discover their addresses， how do we keep that up to date？

So idea addressing is the topic that's going to cover this it' will be in a few lectures from now。

 a related one though is mapping names to addresses so think about this when you access a web page let's say CNNN。

 co。What you really want when you're going to a browser and typing that out is you want to access the content。

That's being served or stored at a server that's associated with CNN。So really。

 what you want to do there is you want to take this user level name at CNN。com。

But the network doesn't understand these names。 It doesn't know anything about CNN。

So you want a way of taking that name and translating it to a network address。

Which is going to be an IP P address。And we'll talk about what IP addresses are。

 and so what you want is a system or a solution that allows you to map or resolve names to addresses。

That system is going to be something we call the DNS or the domain name system that does that translation for us。

Not as easy as it sounds again， because you know server us come up or down as。

Someone like CNNN maybe wants to have 10000 servers， not just one。

 And it wants to load balance sources across all of those。 So this gets pretty complicated as well。

So in a later lecture， we'll talk about DNS， that's actually in the second half of the semester。

The other challenge that came up was this question of the forwarding table and routing。

 So in general， when a packet arrives at a routeer。

 the forwarding table is going to tell you which outgoing link that packet is going to be sent out on。

Getting to that forwarding table。The problem of a routing problem。

 Like how do you compute that forwarding table that's necessary to deliver packet。

This topic of how do you do loing， We're going to spend many， many lectures on this。

At least three or four for basic routing， you're going to do a project on it。

 and then we're going to do inter domainin or more complicated routing later。

So I want you to have just conceptually in your head what。

What routing involves so that you start to build that picture。And so conceptually。

 we've been talking about network topologies。 and you can look at the figure I have on this slide。

 and you can。Visually， you can figure out a about。What are we actually doing when we talk about these switches and links and ends？

What we' showing you is the topology， how they're interconnected or in different was a graph。

This should be very familiar to all of us， it's a graph。

It's a graph who has switches and end hostsr notes and links are edges。

And we want to compute paths over that curve。We all know lots of graph algorithms from dike Str to Belman For。

 different ways of computing parts over graphs。That's really what gouting is except that this is now a distributed gouting algorithm that's going to run at an internet scale。

 and it's going to be run in a decentralized distributed fashion across all the switches and gos。

But you can actually conceptually think of it as。I have a gouting algorithm that's running at all the switches in the Internet。

And what that algorithm is going to do is it's going to learn what this topology or that graph looks like。

And then it's going to pick path through this topology。

And so the output of that louting algorithm is going to be a set of rules that say something like if the packet is going to destination X。

 use this link， if the packet is going to destination Y。

 use this other link and every loer is going to do this individually。

And so the output of running that routing algorithm is that every route is going to have this forwarding table。

That tells this routeer for each destination which of your local links you should forward the packet on。

Okay， this is the forwarding table。 So the output of computing。

 runningning that routing algorithm is this forwarding table。Any questions， here？Yes， for now。

 let's just say that that is our mental picture。 that for every。

Forget about the practical problems of stowing a table that's so large。

 It has every destination on the Internet。 Let's say that that's what we're going to do。

 We're going to learn the entire topropology of the Internet。

 We're going to compute this giant forwarding table。

 and each of out is going to store this forwarding。Clearly， this is not a workable solution。

 but it's a good enough mental picture for now。Any other questions？

So in this process that I just described where a goer learns the topology picks parts。

 and then computes a forwarding table。 The goouer is actually doing two different tasks。

 and that distinction between those two is actually very important。

 If you think about it is doing is figuring out how to compute。That forwarding table。

And then it's actually using that forwarding table。Clus packets to forward packets。

And we call the difference between this computing， the forwarding table and using the forwarding table。

 the distinction between the control plane and the data plane of what a routeo implements。

Here's a G worldd analogy。 Let' you all have a driving license。Where， how did you get that license。

There's an entire process for this。 You probably went to the DMMV。You filled out a bunch of forms。

 you showed what age you were， you gave them a Social Security number。

 When you were done with all of that， you got your driver's license。And now you use it all the time。

 You get on a flight， you show it。You want it to get a call I D。

 Maybe you show me your a driver's license。So there's obtaining that license。

 and then there's using it。 And if you think about it。

 theyre completely different processes for how you went about doing those two problems。

The people that issue at the DMV that issue your driver's license have nothing in common。

 or they operate independently from the people that are checking your driver's license at an airport。

You took you probably go get your driver's license one in 10 years。 It's a painful process。

But you do it， you get it over with， you don't have to do it again for 10 years。

You can use it almost every day。 You use it frequently。

So it's kind of the same in the control plane versus data plane distinction in the networking context so what about it us。

 So control plane is the mechanisms we use to actually compute that forwarding table。

It is inherently a global process where and it's inherently a somewhat complex。

What I mean by that is if you're a router in the middle of a network， what is your local state。

 What what is。The information you have locally without doing any additional work。

 You know what links you have and you know what switches are next to you。

In order to know which of those links to use to get to Berkeley。

 which is somewhere at the other end of the Internet。

I fundamentally had to know something about what the overallalthology looked like。

 what other destinations are in the network， but it was kind of a global view of the network。

So the control plane， this course of computing or forwarding table。

 inherently requires some amount of global information。

RightAnd so this routing algorithm that we're going to be discussing is part of the control plane。

 this process of what algorithm do I run across routeers to compute that forwarding table。

How often do you think I need to do this as a doctorr？

What's the time scale at which you we run these routing algorithms。

So let's say I discovered the topology。I big bo， I。Compiled down， I disturb my forwarding table。

When am I going to have to update it？Whenever something changes in the topology， like what you it。

To expand on that。So if a link is added or a link is removed or link fail。Anything else。

We can address changes。So basically， the timescale is per network event。And on topology。

 the scale of the internet。it's not。 We do have a lot of length going up and down。

 but it's not a million percent。So it's not once a year once in 1 years going to the DMV。

 but it's not also you have to do this every you know a million times every second you have to recompute your forwarding table。

By network time， it's relatively empty。The data plane， on the other hand。

 this is now the using the forwarding table。What is actually involved here， This is， again。

 inherently local in contrast to a control plane because the gouting algorithm has already told me this is your codinging table。

My job on the data plane is just I take a packet， look it up in the forwarding table。

 send the packet on。I don't have to know where Berkeley is or has Berkeley crash at this point in time。

 I'm just using that forwarding table。So the forwarding mechanisms of what we're going to call IP forwarding is part of the data plane。

So good question。 I should have clarified this earlier。

 The picture you should have here is that every switch holds a forwarding table that it has computed。

Every switch or every router。 I'm using the word switch and router interchangeably。This came up in。

 I think， lecture 1， we use switch and routeer interchangeably。 So they mean the same thing。

 It's the nodes inside your network that are。Helping end host communicate， forward back at across。

Okay， so does your home go to have a forwarding table。What do you think。

So I see a bunch of people nodding。 Yes， your home router does have a forwarding table。

 and your home router has to know how to reach every destination on the Internet。

That forwarding table， when we get to it， doesn't have to have it's not going to be this giant forwarding table with。

 you know， an entry for every destination。We can collapse down。

And the reason I'm this is just a small preview。 You know， you'll get to it when we talk about roing。

 The reason it can is because your home routeer has only one way of connecting to the Internet。

So its forwarding table is essentially a highly redundant thing。

 That is no matter what destination you're going to go。So there's a default route。

That really is what saves our home。But in principleia。Good question。 So how is， you know。

 I have this mental picture。 We have all of these switches。 They all。

 each one is participating and running。 this gouting algorithm independently。

 And then it's computing its forwarding table。 How do I learn when something has changed in the topology enough to change my forwarding table。

 That's what we're going to study in a if you like's。ExingGood question。

 Hol on to it for a few more lectures。What is the time scale at which the rear plane operates。

 So we said the control plane operates at the time scale of network events when links go up。

 or go down。When is the data plan taking action？How often am I？Using or invo of。

Doing a look up on this forwarding table。Anytime you send data， so can I say go packet it？

Every time I receive a bucket。The switch has to look up the forward table。Okay， so very。

 very different time skills。 It's full packet。 Every time I receive a packet。

 I need to exercise the data。

![](img/b158913dc64b59abbf77cacc8d27c109_29.png)

So control pill challenges computing routes at scale。As。ThGo up and down in the topology changes。

 This is going to be the topic we study when we talk about routing algorithms。

 How do we have these highly dynamic scalable routing algorithms。

Something I've not actually even brought up here is we have to do that while respecting IP autonomy。

 So if you remember from last lecture， we said the Internet。It comprised of a large number of ISPs。

 they act independently。Each ISP is going to want to make its own roing decisions。

 And it's not going to want to communicate that to other ISps。

 And so we somehow have to respect the autonomy of ISps while making sure we actually have a part。

ISP domains， this is going to be a topic that is。Protocol called PGP。

 And we're going to study that later in this method。跟实。Adding additional sophistication to welding。



![](img/b158913dc64b59abbf77cacc8d27c109_31.png)

On the data plane， what do you think is the biggest challenge。So we said on the control plane。

 it's learning all of this little bit topology， coordinating at you。They will lost corruption。嗯。

会上就在 one。Not try would to say it's the biggest challenge， but yes， it is a challenge。

 How do we make sure the data is not getting corrupted on the wire。

 That's actually if you ask the E folks， still say that。It's all about performance。 So the dataplay。

 the biggest concern is performance。 Let me give you an example to explain why。

 let's say I had a 0 bit per second link。 Okay so that's 10 to the 12 B per second coming in of the wire。

 This is a very standard link speed these days。 If you go look in the middle of the Internet somewhere。

And that they have 10 kilobit packets。 this is again， a pretty standard packet like。

What this means if you do the calculation is that you have a new packet coming in every 10 nanocyclds。

So every 10 nanoseconds， you have to。Read the packet of the wire force it so that you can find the address in the packet。

Then you have to look up the address in the forwarding table。

Do whatever other updating of the packet header that you might want to do。

And then any counters you have internally within the Gro， for example。

 you counting how much traffic you've been forwarding。 So basically， any bookkeeping you want to do。

And then you have to send the bike on that link。All of this in a second。

And this is an incredibly difficult engineering problem as a fun exercise。

 Try writing a little piece of code on your laptop that receives the packet and just send it back out。

 We call it an echo server。 all extreme is we a packet， send it out and try to time how long it take。

If you can get paid than 100 microseds， you deserve an award。

It's actually extremely hard to write very low latency。



![](img/b158913dc64b59abbf77cacc8d27c109_33.png)

And so this is what we talk about。Hence to recap important topics that we've discussed so far。

 how do we name hosts on the internet that's naming， how do we address them。

 that's the topic of IP addressing， how do we map names to addresses。

 this is going to be the DNS system， how do we compute those forwarding tables。

 we're going to have multiple lectures in one project on the routing control plane。And then finally。

 how do we forward packets， This is the design and implementation of IP forwarding and the IP data plane。



![](img/b158913dc64b59abbf77cacc8d27c109_35.png)

And with that。Okay， let's pickup again I've gone。Lower than I expected。

 so I might speed up a little bit。 Any questions on what we' have talked about so far。



![](img/b158913dc64b59abbf77cacc8d27c109_37.png)

Okay。So， let。Whichge a little bit and let's back up a level。 So we've talked about， you know。

 kind of zooming in packets across links。 And we've also talked about a stream of packets overflow going across a set of links in this network。

Backing up a level though， if you look at the network as a whole and we say。

 okay I have one flow going through this network and I have another one and yet another one inherently what this is telling us is that we have a number of packets of flows that are sharing this network。

 What I mean by that is they're sharing these links and switch resources。And in particular。

 when we talk about sharing， we tend to talk about sharing a link or sharing the bandwidth on that link。

And so a fundamental fact about networks that is what we're going to talk about next is the fact that network resources are shared。

 a network has to support simultaneous flows at the same time， simultaneous users。

 simultaneous applications， simultaneous flows。

![](img/b158913dc64b59abbf77cacc8d27c109_39.png)

And so this question of how do we actually share network resources is very fundamental before you even talk about protocols or how you do bing。

 you have to talk about the model you want to support in terms of how you share network resources of across flows or across users。



![](img/b158913dc64b59abbf77cacc8d27c109_41.png)

And if you you know， if you take in C162， but it's also just a very intuitive idea。

 what we say when you talk about this notion of sharing resources。

 what we're really talking about is this term called statistical multiplex。

Statistical multiplex things。 How many of you are familiar with？The idea of the concept of this。收款。

Okay。So statistical and multiplexing is just a fancy term for saying we're going to share resources。

And it's this idea that different users or different。

People that want to use that resource have a certain demand。For that resource。

 that's how much of the resource they would like to use。That's what we're calling the demand。

And statistical multiplxing is this idea that we're going to combine。

Those demands in order to share resources efficiently。

In contrast to statistical multiplexing as a way of sharing resources。

Is the idea that we would statically potition resources that there would be no sharing。

So let's take a few examples， your laptop。If I think of it in terms of users。

Would you say that your laptop is。Pition in the sense that only one user gets to use it or is it shared across all users？

What oh， okay， that was the one。 Yes， it's one user。

 It is not statistically multiplex at the level of users， right， one user， one laptop。

If you take a server in the cloud， would you say the same？Is it shared or is it。Sttically parted。

It's so this idea of statistical multiplexing。Having a set of resources and then listening or looking at what the demand for those resources is and accordingly allocating resources。

 this idea of statistical multiplexing has a very long history in computer science if you look at within your laptop there and you look at the codes on your laptop。

There are a number of processes that are all sharing access to that code。 I don't say。

 oh my browser only my browser gets to use code 1 and 2。 The file system has to use code 3。

 That's not how we use it。 Instead we say you have all of these processes and your operating system scheduler is going to decide which process gets to use which code at what point in time。

That's a form of statistical multiplexing。 Cloud computing is a great example of statistical multiplexing。

 as we're going to put together all of these thousands or millions of servers。

And then everyone could come and use them large number of cloud tenants。

 as opposed to what actually was a free cloud computing era where every company builds their own data center。

I have this idea that you would have a dedicated data center for just your company。え。

Made total sense to people pre cloud computing。I would say statistical multiplexing actually exists in the real world everywhere if you think about it。

 your car。Yess probably not statistically multiplex。ItY are you on it。A public bus or a flight。

 an airline jet is statistically multiplex。A restaurant。

You might have a cafeteria and an enterprise that is dedicated to people working at that company。

But another restaurant is open to the public， and everyone shares。Using that restaurant。

So that is basically statistical malfxing， this idea that we're going to have people with their varying demands for resources and we're going to figure out how to share those resources。

Why is statistical multiplexing a good idea。Why do we want to statistically multi resources？

So it emulates the real world。 Why does it work even in the real world， You're right。

 I' am trying to get it one。有。For saving resources， it is ultimately an efficiency or cost argument。

We don't each have our own private jet because we can' afford。 some people can。

 and they have their own private jet。 But for most of us。

 it is much more cost effective to have a jet that we can all share。

 and you only pay when you need to travel。Yep。I'll get to that in just a minute。

 Where does the word statistical multiplexing come from。 It's actually the next point。

 Why does statistical multiplexing make sense， Why does it work。

 Why is it so effective everywhere in life。Yeah， so what I'm going to pick up on this expectation that we expect not everyone needs。

That resource a lot of it at exactly the same time。So let's think about this in terms of bandwidth。

 so let I wake up in the morning， I upload a huge file and I go have lunch。

 so I'm not using any bandwidth， then I browse and then I take the evening off I。

So I'm not using any bird that Sean on the other hand comes sleep。

 So he wakes up at 3 in the morning and watch a Netflix all night song and then he sleeps all day。

So I maybe needed a gigabit per second in the morning， and then I needed0 at night。

 but Sean maybe needs a gigabit per second at night and 0 and the D。 So this worked out really well。

 I don't have to build a network that is provision for one gig for me and one gig for Sean。

Instead of provisioning a network for one gig plus one gig， I can say kind of need one。112。

 something closer to 1 Gi a second。So statistically， that is where the statistical comes in。

 is that if you take a large number of users or sources that need that resource。

And you look at their demand， and you say。That and that demand varies in time。 You say statistically。

 we're not going to need the worst case。 Everyone's not going to need the worst case at the same。

Okay， so that's both where statistical the term comes in， it's in expectation probabilically。

 we don't expect it to happen。And that's true for everything in the realroad。 And we don't。Well。

 sometimes we all descend on the same restaurant at the same time， but very often we don't。

So a little more formally， the reason statistical multiplexing works is that the peak of the aggregate demand is much。

 much less typically than the aggregate of the peak demand。 So what does this mean。

 Let me break that down if I took。All everyone's demand and I added up all the demands at every point in time。

 so as time is moving along， I say I'm going to take everyone's demand and add it up then everyone's demand and add it up And then if I say okay for that add it up or the combined demand。

 what was the peak of that combined demand I'm going to get the peak of the aggregate。So this was。

 you if you took Sean and my demands at every point in time。And you added them up。 Typically。

 we would be asking in combination， We would be asking for a little bit over a gigabit per second。

On the other hand， I could take Sean's demand and say， what is Sean's peak。 It's one gig。

 I could take my demand and say what is my peak。 It's one gig。 And then I add the peak。

That would be too big of it for a second。And typically。

 the peak of the combination or the peak of the aggregates is much less than adding up or aggregating the peaks。

关审。How do you know that the resources are shared in a fair manner。 Excellent question。 way ahead。

 We're going to get to that in。Many lectures。 So that's a great question。 How do we know。

know we have all of this demand， and we are going to share that with in some sensible fashion。

 in your operating system， it's your operating。Schedule it has a policy。That says。

 I'm going to give this process some time and then that。

So we're going to have to develop similar policies and ideas in the networking content。

Any other questions。yeah， so the question is building on the previous question， really。

 do the resources have to be shared fairly， Not necessarily。 It depends the question of policy。

Some people might want to some operators would want to share fairly， some might not。

 And so this is a question we'll get into when we talk about resource allocation。



![](img/b158913dc64b59abbf77cacc8d27c109_43.png)

Let me make this a little bit more formal still， so I'm going to say if I have a flow F。

I'm going to use P of F to denote its peak for that flow。

And so then the peak of an aggregate or a number of flows would be the。

say F1 and F2 would be P of F1 plus F2。Okay。So the aggregate of the peaks。

Would be adding up all the peaks。So it would be the sum over each flow of fever。On the other hand。

 the peak of the aggregate would just be that I first sum all the flows。And then I take the peak。

And so wed say that statistical multiplexing works。Because typically， the aggregate。Of the peaks。

Is much， much higher than。For summing them up and then taking the peak。And in fact。

 for many girl world distributions， you can show that actually the peak of the aggregate。

That means combining all the demands and taking the peak。Tends to be much closer to the average。

So if you're building a network and you believe this is going to be true。

You save significantly on how much bandwidth you have to put in it。That's the reason we like to。

Any questions before I move on， this notation。Stay at it for a little bit offline。

It's not actually complicated。 Really， all it's saying is you don't design for the absolute worst case。

The worst cases that all of us have a peak demand at the same time。And so instead。

 what statistical multiplexing says is you share resources and you kind of just hope。

That the peaks don't all occur at the same time。 Could this go wrong。

 Could this kind of premise or assumption。Thank you。Network in Berkeley has no excuse。

 I knew feel that was predictable。 I was guys。有。So actually。

 you guys are coming at an interesting distinction， which is。So Berkeley。

 you know the start semester or when we know that the load on the power grid is going to peak。

 I would have said in those cases， the operators knew that that peak was coming。

It was a very conscious decision not to provision for the fe， because it's just too expensive。

돈 third。Annoy their customers and don't know your power in your willing。Llackout and or buy the wfi。

What about unpredictable？Something goes viral， yeah。

So famously in the Bay Area when there was the last big earthquake everyone。

 the first thing everyone did was pick up their cell phones and the cell system went up。

So this happens。 It's very similar to insurance insurance companies。

 they give everyone home insurance， and then you have wildfires and everyone's claiming their insurance。

 and they never come out of bank。It's still considered though a very practical choice to make that this worst case happens grave enough。

And the alternative of actually provisioning for that worst case is so expensive。

That this is what most operators do。Who do you think doesn't do this？W buy the jet。

The military and the government， for sure， they don't want to take any chances， anyone else。

The super wealthy， which in the Internet context， would be the financial exchanges and so on。

 So the financial exchanges are not， for example。So far， so let's talk about it。

 They don't run on the。And they build their own networks because it's just worth it to them。

 The losses to。So we're going to do statistical multiplexing。Let's。Hopefully。

 we have all agreed this as a good way to go。 How are we going to do it。

I want to point out something， which is a hint， maybe。

 but something about statistical multiplexing that was kind of buried in all of those examples that I want to call it out explicitly。

So that is， and this is the idea that when we talk about statistical multiplexing。

The question really is， at what granularity are we statistically multixing things。So， for example。

 I said your laptop is not statistically multiplex because you're the only user。

 What that means is actually at the granularity of users， it is not statistically multipleed。

But if you look at your laptop at the gularity of processes or applications。

 it is statistically multiplepled。 if you're running to me applications more than you have goals。

 your laptop slows down， those applications are sharing the goals inside your laptop。

And so there's actually a question when we talk about statistical multiing at what granularity are we talking about sharing。

The same in the cloud， you can go and book a server to yourself。

And then you're not sharing it when you let it go， then that silver gets shared again。

AndSo there's always this question of at what granularity are we talking about sh。So with that。

 how do you train that quick resources？How would you think about sharing resources？

 I'm now talking about almost like a mechanism。 How would we go about sharing it。

Think about the real world， public transport。Restaurants。Clo computing。A quota。

 When would you get your quota。Would you just always have it， Because then we。you're getting at home。

So let me play that back to tell me if I got it right。 which is I have a quota。

 This is how much I want。 and I go and I try to book it。In a sense， and if the network has resources。

 that gives it to me。 and then I own that quota。And if not， then I can't use it， okay。

I'm going to call that a system called reservations。 I can reserve resources。If like a restaurant。

 you can call and say at like a reservation。Oakplan。おご用 joなル。Pot come first silk。

 which is you just don't up。And you hope that you get the resources。

 That's why large the two broad categories or approaches to sharing that we see。



![](img/b158913dc64b59abbf77cacc8d27c109_45.png)

You know， both on the Internet， but also in the discussion about how one should share resources more generally。

 One is this idea of reservation。That an end host or a user is going to explicitly reserve bandwidth when they need it。

So when you need bandwidth， you go to the network and you say。

 I would like to reserve 1 MBbit per second。Very， natural time scale at which to do this or which most people who tried to do this。

Approach is that when I have a flow of data， when I have some data to send， I'm going to say， hey。

 can I reserve some bandwidth？Then I'm going to actually send data over that reservation。

 And then I'm going to say I'm done。 My reservation is over。 You can take it back。

 You can take the resources back。And the other approach is what we've called previously best effort。

 which is you just send data packets and it's up to the network to try and get it across。

 and if they can't， because there were no resources left， they're going to drop a packet。

But they're going to try to send it along as we。So there's reservations and best effort。



![](img/b158913dc64b59abbf77cacc8d27c109_47.png)

When we talk about how would you actually implement reservations and best effort， best effort。

 how you implement it is this packet switching we've been talking about。

 I send a packet into the network。 The switch receives packets。

 If it has capacity on its outgoing link， it sends it。Otherwise， it's going to drop it。

Thats the best effort。 It's pretty straightforward。 We'll get to that in a bit。

 for the rest of this time， I wanted to。Give a little preview on the reservations and how would you do it。

 So let's set the problem of。 I have this network here。



![](img/b158913dc64b59abbf77cacc8d27c109_49.png)

And I think we're only going to get to。The broad approach。

 And then we'll do a deep dive on it in the next lecture。 So here I have a topology。

And I have these two blue and that want。To communicate。The network has run。

A gouting algorithm and has decided that it likes this red pot。Connecting those two ends。

So the network has done its job。 It has a path。 How would you now implement reservations？

So the Blue Hose now want。To reserve bandwidth along this path。So notice。

 I'm not saying that the reservation gets to pick。What part that was already decided by the network。

The job of the reservation is just to book。Bandth along that path。 How would you implement this。

So you could send and that's exactly what many of these protocols of these ideas have tried to do。

 you could send something that looks like a reservation packet。

 a request to reserve resources or what we call a reservation request through the network saying。

 for example， hey can you give me 10 megabits per second。

 can you give me10 can you give me 10 that reservation request will travel through the path？

Trying to book 10 minutes， if it's the second at every。If all the switches say yes。

Then you have your reservation or in the terminology that's used。

 we say you've established a circuit。So， soet means that you have。

Successfully got in your reservation。 You booked resources at every hop along the。

Where did the term circuit come from， It actually comes from the phone network。

 This is how the phone network worked。 And when you picked up your phone and the old fashioned phone network and you got a dialed tone and you dialed your number。

 and then it would send a reservation request。 It would try to set up a call。

Through the phone network， through the receiver。 And if you were successful。

 then you had a telephone circuit and you could talk over that circuit。So at this point。

 you would say you've established a circuit。You can then start sending data over that circuit up to your quota of 10 mebits per second。

And when you're done， you've sent the file you're done with your communication。

 then you send a tear down message back through the network。So you'd say I'm done， I'm done。

 I'm done， I'm done， and then the suck disappear。And now those resources that you would reserve are available to be used by someone else。



![](img/b158913dc64b59abbf77cacc8d27c109_51.png)

Let's contrast that with packet switching。 So in packet switching， I have this packet。

In packet switching， every switch is going to process a packet independently。

And it's going to process a packet independently along two dimensions。

 One is each switch is going to treat that packet independently。

 So this first hop here takes the packet， sends it on。 The second hop， takes the packet， sends it on。

 the third hop and so on。The switch， each switch doesn't care that previous switches have actually processed that packet or they accepted it to solve that packet。

 Each switch is going to independently say， am I willing to forward this packet or not。

It's also independent in the sense that it independent across packets。

 It's going to revisit that best effort decision every packet it gets。

So it doesn't care that I sent the first nine packets in this flow。 I ought to send the 10th packet。

 doesn't make any of those decisions。 It's truly independent per switch per packet。



![](img/b158913dc64b59abbf77cacc8d27c109_53.png)

So one last point that I want to emphasize here is that both approaches actually embodies statistical multiplexing。

 They're just different ways of supporting or implementing statistical multiplexing that have very different tradeoffs so circuit switching。

We're statistically multiplexing across the flows currently in the system。So every flow has a demand。

 It says this is how much this flow needs。 And then it books。

Those resources for the duration of that flow。So I'm taking the peak。

 So if I had a particular flow and it was very choppy。 let's say 10 GB and then 1 gig and then 10 GB。

 I'm going to say I'm going to book 10 GB for the duration of that flow。

But once I don't have that flow anymore， I'm going to give those resources back。

 So it's not like I booked that quota forever。 I wasn't just holding on to those resources forever。

On the other hand， with packet switching， resources are given out in a packet by packet basis。

 and you never whistle resources。 So you never actually say。

 I have 10 megabits per second guaranteed for me。You consume the resources for the durationition of that packet on the wire。

And that's it。So next lecture， we're going to talk at length about you know which one is better。

 And we're going to do a。Detailed design analysis of when or why is circuit switching better。

 when or why is packet switching better， We're going to talk about different metrics by which we should evaluate them。

 What I want to pause here for now is just to make sure you understood what circuit switching is。

Not but that's a good idea。But what is it trying to do？

Any questions on what is circuitcus which I'm trying to do。Or how it works at this high level。Yes。

 a good question。 I said， I'm going to send these reservation request along the path。

 And in the example I gave you， I said every switch along the path said， yes。

 you can have 10 mebit per second。 What if there was a switch that didn't。Then megabits a second。

What would then happen， you can think of it for now is you would decline the reservation。

 So the switches would return a response staying solely。You can't have your ten0ggits of a second。

 What should the end force do then another。Will it find a different path。

 You could certainly design a network where the network says this part didn't work。

 Resend me the reservation request。Use something in your packet header to tell me to try a different path。

 It's plausible。 none of the protocols I would design。 I knowt do this。 This would be fairly complex。

 Why would you， How could the source actually say， I want to use this path versus a different path。

You could try asking again。For the source to have to pick just to answer my own question。

 if for the source to have to pick a different path。

 the source would have to have some control over how packets are forwarded through the network。

 which so far at this all our discussion we've been saying the network decides but not the sources better regarding algorithms run。

By the network。 So it would be a fairly big leap to allow end hosts to say how their package should be allowed over the Internet operators。

That would probably make them very nervous。reasonable。I定。1， that has a lot of。

I'm going to pause here， think about circuit switching and whether you like it。

 we'll talk about why you should or shouldn't like it in our next election， Thank you。



![](img/b158913dc64b59abbf77cacc8d27c109_55.png)

![](img/b158913dc64b59abbf77cacc8d27c109_56.png)