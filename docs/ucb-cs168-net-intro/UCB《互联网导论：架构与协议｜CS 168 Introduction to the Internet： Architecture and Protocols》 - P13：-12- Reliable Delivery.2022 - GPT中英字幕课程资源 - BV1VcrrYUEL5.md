# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P13：-12- Reliable Delivery.2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Okay， let's get started。 everyone。 Good morning。 Topics for today。

 we're going to wrap up the I P header。 We had two little topics left to cover there and start on reliability。

 This is the topic for your second project。So we're gonna to get started on that today and then continue it after the midterm。

 So on the question of designing I2 topics that were remaining one was we wanted to take a brief peek at IPV 6。

 really through the lens of what's changed， what's different going from IPV 4 to IPV6 and then spend a little bit of time again talking about the security implications of the IP header。

And so jumping straight into IPV6， I think Murphy touched on this a little bit in his lecture on addressing。

 but just to wecap know roughly about the late 90s。

 people started panicking that with 32 bit IPV4 addresses were going run out of a address space fairly quickly。

 And so IPV6 was an effort that started it was motivated by this concern about address exhaustion。

 And so IPV6 goes all the way to the other extreme addresses128 bits long。

 So there are four times more bits than in IPV4。 So seems very likely at this point that we're never going run out of addresses using IPV6。

 whereas IPV6， it has been a slow process of deployment at this point in time。

 I would say I think depending on which numbers you believe between 30 to 40% of the Internet is using IPV6。

But， you know， there have been major announcements， for example。

 all of China has said that they're moving to IPV 6。 All of the major cloud providers support IPV 6。

 So at this point in time， there's no question that IPV 6 will one day be the version of I P running on the Internet。

 It's just a question of， know how much time it's going to take to get deployed。

While IPV6 was primarily motivated by this concern about we need more address space。

 we've run out of addresses to allocate。The designers of IPV6 also took the opportunity to do a little bit of a cleanup on the IPV4 header。

 So we've talked as we went through the IPV4 header about why do we have this field。

 This field looks complicated。 Opera don't really turn on this other field and so on。

 So they did a little bit of let's call it spring cleaning on the IPV4 header and going from IPV4 to IPV6。

 That's about the extent to which the designers tried to effect change going from V4 to V6。

 So for example， some of the things they did not touch or did not address were things like security and concerns about IP address integrity and so on。

 which we touch on。 So overall， I would say IPV6 is a nicely designed。

 It's an elegant protocol and the changes they made make sense and a nicely done。

 It's not a particularly ambitious protocol。 So everything we've learned about IPV4 still applies to IPV6 with a few changes to the IP header that well talk about。



![](img/e4615fb309d2345ae939845e2643563f_1.png)

OkaySo with that KC IPV4 header， we talked about it last time。

 If you need a a reminder there are few fields up there， versions。

 header lenss and so on that were for passing， there's a source and destination address， of course。

 then there are few fields to deal with issues like fragmentation looping check sums if packets get corrupted and then there were few fields in there to deal with what if you wanted exception processing So type of service or this notion of options where you can ask for advanced functionality。

So if you， if you were doing IPV 6， what would you， What cleanup would you do。

 We're going to increase the size of the addresses。 So let's take that as a given。

But what else would you。Clean up change too differently。We'll move to check some。

Anything else that can go？Or that you don't like， you would do differently。

You don't have to know how to fix it。 Just things that didn't please you about the wayer。



![](img/e4615fb309d2345ae939845e2643563f_3.png)

Okay， we'll take the checksup。 Let's start with that。 So summary of changes。 we expanded addresses。

 We eliminated the check sum。 Why we did we eliminate the checkum， Because as we discussed in class。

 you could have just let a corrupted packet go all the way to the receiver and have the receiver check whether the check sum was correct。

 And if it wasn't， it could drop it。So strictly speaking。

 we didn't have to have every router recomputing and checking the checkum。

The only thing you wasted by having the corrupt packet go all the way to the receiver was a little bit of extra bandwidth along the path。

So that's why we eliminated the checkso。 I'm going to tell you that IPV 6 for fairly similar reason。

 reasoning， eliminated fragmentation。You've now done fragmentation in section。So。

How would you deal with a packet that is larger than the M U if you didn't have fragmentation support out about us。

一。The end host could which end host you're on the guide track。The sender。

 How would the sender know that it has to fragment。没。Yeah， so that's exactly what IPV6 does。

 So in IPV6， the way this works is if the sender sends a packet that is larger than the link M U。

 that packet is going to make its way through the network until it reaches the link where the M is smaller than the packet size。

 That route is going to drop the packet and send an error message back to the sender saying you need to send smaller packets。

 This is my MU。And then the sender is going to actually send out packets that of the correct size。

So again， trying to push work off to the endho。Did that make sense to everyone？

The other thing that IPV exchanges is the options， how options are handled。

 So if you remember when we talked about options， we said， well， because you have options。

 the header length is variable， which means you typically have more complicated processing at the route Rob were saying how typically at Google。

 for example， they don't even treat options。 They ignore them or they drop packets that have options。

 So options in general have been a little bit of a troublesome in the IPV4 header。

And so the way IPV 6 addresses this is it kind of says options are not part of the IPV 6 header。

 but it gives you a mechanism by which you can still have options somewhere else。

 And the way it does that is actually pretty clever。 If you remember going back to the IPV4 header。

 we had this protocol field， which we said we are going to use to tell the end hostst what is the layer 4 protocol you're going have。

And we said their well known protocol numbers。 So， for example， if you said my protocol field is 6。

 that was telling the receiver that your next header is a TCP header。Okay， so in IPV 6。

 this protocol field is now called a next header field。 and it still does the original job。

 So if your next header field says 6， that tells the receiver that your next header is T CP。

But in addition， what IPV 6 says is that you could， if you wanted to have options。 So let's say。

 for example， you have you wanted to do source routing as an option。

 Then the way you do that is you go define a source gruting header。

 You go to the standards body and you say I need an option for source routing。

 This is what my source routing header is going to look like and you get the equivalent of a protocol number。

That tells the router that your next header is a so scouting header。And so now。

 if you want to have options， the only thing you have to do in the IPV 6 header is that you say that your next header field。

Is a soloouting header。And then when you， the router can go look at the source gruting header。

And in the source gruting header， the next header field would tell you that the the header inside one level is TP。

And you could continue to do that。 You can start to chain these options。

 So you could have an IPV 6 header that's pointing to something like a soul scouting header。

 The source scouting header。 You know， this is another type of header could be an authentication header where you're checking that this is a valid packet and ultimately。

到这。The next header would be a TCP header。Okay， so the way to think about it is options have gone from the IPV 6 header。

 The IPV 6 header doesn't need to know about options。

 But there's this way of squeezing them in between the IPV 6 header and the layer for the TCP header。

Okay， any questions on that。Yeah。So going back to the fragmentation question， great question。

 What if I had an empty U on my， let's say the source was initially sending 1000 by packets and there's an empty U。

 a link that has an empty U of say 500 by。 And then after that。

 there's a link that has an empty of 250 by。 So you're right。 in that case。

 what would happen is you would send 1000 by packet。

 you would get back an error message saying you have to send something less than 500。

 if you then send 4，99， It's going to go to the next link which will send you another error message。

 So， yes， you're right。 that could happen。 And you know， it would happen once along the path。

Until the source learns it， the reason no one's too worried about that is at this point。

 everyone is kind of settled。 It's not official， but everyone kind of agrees that the Ethan attempt attempt to use。

The M U of the Internet。 So 1500 B。 So you'd have to be doing something pretty unusual to do that。

Any other。So that's a good question。 Can your next header field be empty。Is that。

 what would that mean。So your packet would make it every routeer would say， okay， there's no option。

 but it would make it all the way down to the destination。At the destination。

 I still need to know whether to hand it to TCP or UDP or some other protocol。 So you will。

 itll still play the field。 at the very least， the next header is the same as the protocol field in IPV4。

 It can be more than that， but nevertheless less than that。Any other questions？O。

So that was the options field。 The other change it makes is in IPV6 cell is no header length field。

This kind of follows why is that。没有。Like， the only reason we needed it in IPV4 was because of this options thing that could be variable end。

 We got rid of options from the IPV 6 header。 so we don't need a header length anymore。

And then the one thing that IPV6 add is this notion of a flow label。

 We haven't fully covered the context to explain a flow label。

 but let me try and we'll come back to it later。 So the reason we have a flow label is remember。

 we said earlier that often when you look at a source and destination。

 it's not just one stream of independent packets going back and forth between them at some higher level or application level。

 there's a stream of packets that are related to what the application is trying to do。 For example。

 you could have multiple packets coming in for one download or in a web browser session。

 you could actually have multiple flows and multiple connections and multiple packets that are all part of that users experience or the user' session。

And often in the Internet， there are these things called middle boxes like firewalls or censorship boxes or intrusion detection boxes。

 We're going to talk about them later in this semester。 But these are boxes that， for example。

 think of an appliance， a middle box that's trying to censor certain traffic。

 What it's going to try to do is to collect a set of packets that are all related and look inside that packet to say。

 is this traffic。Is this connection going someplace where I don't want my users to go。

 And then it's going to filter。And so the network， when youre talking about these kinds of functions。

 it needs to have some notion of which packets together。

For some application context or a stream of related packets that that box wants to look at。

With the IPV for header， there's no explicit way for the network to know this sequence of packets all related。

And so instead， what we've always on with IPP4 is all these ad hoc rules that say， well。

 for all traffic going from the same source I P to the same destination with the same port numbers。

 these must all be related。And it's pretty ad hoc。 And sometimes it goes wrong。

 But that's how people。 that's what people do。 So what IP V 6 instead said， okay， if the network。

 if there are boxes in the network that need to know which packets are kind of related。

 Let me have this notion of a flow label。And at the end host。

 I'm going to use the same flow label to denote a stream of packets that are all related。

So it's just taking the guesswork out for the network。Does that make sense。So for example。

 you might use the same flow label for all packets that are part of the same file download。

You could also use the same flow label for all packets that are part of one browsing session。

 So both the ads and the content and the video that are part of one browsing session。

 There no rules that limit end host on how they use the flow label。

But it's a hint to the network that the end host thinks of these packets as related。有。

As far as I know it it's up to what let me double check on that， I believe it's undefined。Or unitted。

 There might be some that are well set aside， but let me confirm that。I don't know if you guys。

Let me get back to you on that。Any questions about this？



![](img/e4615fb309d2345ae939845e2643563f_5.png)

Okay， so IPV 4 and IPV 6， Where does that lead us， This is the IPV 6 header so that you can compare it。

 Here's the IPV 4 header side by side。 And here's the color codinging。

 So let's go through these one at a time。 Yellows are the fields that are identical。

Semantic and not syntactic， but semantically from IPV 4 to IPV 6。

 It's pretty much the version number。 It's now value 6， but it's the same field。

 and the source and destination addresses。 Okay， as you can see， theyre four times larger。

Orange are all the fields that went away from the IPV for header。 So we have fragmentation。

 header and check sal and options。These are gone。Blues fields that have。Kind of they've stayed。

 we've either renamed them or slightly changed them how we use them。

 So type of service is now called traffic class payload length。

 we still need because the payload of a packet can still be different from one packet to another。

Next， header is playing the role of the protocol field and more。

And time to live was renamed hop limit as being people thought time to live was not quite capturing what the T T L was doing。

 It's actually a limit on the number of hops。 So it's now called hop limit。So， that's。Really the。

 the extent of the change going from v 4 to v 6， Any questions。



![](img/e4615fb309d2345ae939845e2643563f_7.png)

So。😊，Nice to think about， actually， what is the philosophy underlying all of these changes。

 What would you say， the designers of IPV 6， what。Princiipal。

 have they been applying and doing this cleanup。有。Yeah。

 it's a very aggressive use of application of the Nto end principle。

 Anything that could be pushed to the end host has been pushed to the end host。

 so fragmentation and checks are are gone。In fact， the only thing that's left is the T TO。

Why keep the detail。Is that something yeah。Yeah， because we needed T T L because of all these routing convergence issues and loops。

 It's really hard to imagine how an end host could help with us。

Gouting convergence truly is a network problem。There's also an emphasis on simplification。

 which is why they got rid of options and the I P headerland。But at the same time。

 I think the thing that's nice about the IPV6 header is they've kept in mind this need for extensibility。

 and they've done it actually very cleanly with just this kind of generalized next header approach。

 which allows you to over time define new functions for the network。

 as well as this notion of a general flow label， which is know the purest of IPV4 had this idea that you have a very strict division between what the network does and the end hoststs do。

 And the network should never look at anything more than the IPV4 header。

 Well 25 years of experience has taught that the network is looking at more than the IPV4 header。

 And so having a flow label is a nice way for end hosts to start communicating some of the application semantics into the network。

Without actually embedding application logic into the network。 So it's。

 it's a useful way of passing hints between the end host and the network。行。Yeah。

 so let me give you a specific example。 and we'll come back to this one in a much much later lecture when we do middle boxes。

 But as an example， let's say that you had an intrusion detection system that's sitting in your network that's run by your ISP。

 And what the intrusion detection system does is it looks at the URL that you're going to when you're browsing And it either says。

 you know， for whatever reason， parental control。 I'm going to drop this traffic or you know censorship I'm going to drop this traffic。

 So but what it needs to look at is the URL。The URL is not in the IPV4 header。

 It's actually not even in your TCP header。 It's in your application level， H T TP header。

 which we'll talk about when we get to it。But so the network。

 what it has to do is collect the first few packets in your flow。 reassemble them。

 reconstruct your H T TP headers， extract the URL and say， this is allowed or not allowed。

So what the network has to do is it has to piece together some number of packets in order to get at that URL。

For that， it needs to know which packets belong to the same user browsing session。And today。

 the way we do that is through kind of ad hoc heuristics。 we say， okay。

 if these packets have the same source and destination IP address and they have the same port numbers and they have the same protocol field。

 We call that a five double。Then they belong to the same flu。

And so I'm going to assemble packets that had that flow。It's a little ad hoc。 So， for example。

 if you had one browsing session where you're talking to two content providers for that webage。

 the network gets confused about whether they actually。

 it has no real easy way of knowing that they are related。So rather than have all these ad hoc rules。

 what IPV6 is saying is I will allow applications to put a flow label in。

And so then the network just has to look at the flow label and say these packets belong to the same user session or the same flow。

We'll get back to this when we talk about middle boxes， any other。Okay， so then moving on。

 let's look at a quick security analysis of the IP header。 So we're going to look at a fairly。

 as you probably realize by now， the original designers of the Internet didn't worry about security。

 So there are all kinds of things you can do at the network layer that are security threats。

 Well we're going look at today is one very narrow subset of them。

 which is imagine that you are a sender and you're sending an IPV for header packet it out and you get to do whatever you want with the IPV4 header。



![](img/e4615fb309d2345ae939845e2643563f_9.png)

What are some of the things that you could do？That would be a security problem。

That could be deemed as an attack or something。So remember， you get to fill these。

Feields here on this header， as you choose。There are many fields that can be exploited。刀子。Yeah。

So the TTL， and you've actually already done this in section。

 you could set the TTL to be fairly short so that you that's what tree Sc does。

 So then you get an error message back from the routeta and you're effectively tracing the internal topology of the ISB。

Yeahep。Even easier than that in a way， maybe not easier。要。You could spoof the destination。

 I was expecting the source， but you can spo addresses。 absolutelysolutely right。

 Let's we can get to a bit whether you're better off spoofing the destination of the source， yeah。

You could mess with the check sum so it gets rejected。 interestinging， You can certainly do that。

 Why would you do that。You're only getting your own packets rejected。It's doable。

 I would argue that it's not much of an attack。If the only effect is that you're dropping your own packets。

Any others？

![](img/e4615fb309d2345ae939845e2643563f_11.png)

Let's go through them。 IP address integrity， as someone pointed out。In IPV 4。

 you can put the addresses you want in the source and destination field。Ideally。

 let's start with the source， which is where more more problems arise。Ideally， as a sender。

 you should be putting your own address as the source field。But if you don't。

 there's nothing in the network that's actually checking that you are who you claim to be。

So you could be sending packets with any source that you want。What are the implications of this。

 Why would you actually claim to be a source that you're not。Why do you think someone might do this。

There's two reasons。 Why am I doing it。有。Yeah， okay， three reasons。 You。

 you might want to trick the destination。 How far would you go with that， though。

 Because here's what's going to happen， right， You send a packet， and I claim to be Sarah。

And I send it packet to Alex。 Alex， this response is going to go to seller not to me。做。

Marginal gains， though。So the most common reason people do this is。

 let's say you want to attack a destination。 So let's say I want to send tons and tons and tons of packets to Alex and overwhelm his machine and k it。

The minute， Alex is under attack。 What is he going to do， He's going to tell his ISP， hey。

 someone's attacking me。 you need to put a filter in your network and drop that traffic。

The most natural filter you would say is， hey， all these packets coming from Sylvia。

 she's attacking me drop all traffic coming from Sylvia。

But if Ipoof my source address and I choose a different address for every packet。

 then it's very hard for an ISB to filter traffic because they don't know where it's coming from。

All they see is。Somewhere close to Alex， packets are coming in for millions of different IP addresses。

 and Alex is being taken down。 So this is a very common attack on the Internet。

 And it's hard to know how to filter it。 if you can spoof addresses。Make sense。

There's another one you could do， which is to actually be a pain for the source address that you was poofing。

So this is a different one。 So let's say now I want to get a noisey say。

So what I could do is send packets to a million different destinations。

 claiming that they all come from seller。So those million destinations are all going to respond back to server and overwhelm her link。

So that's two ways in which you can exploit the source IP address。

 And there are all kinds of attacks people have done exploiting the fact that you can set whatever source I address you want。

implicationsmplication of the type of service field。This one's actually pretty simple。

 You can just ask for high priority traffic。So your attack traffic is now。

 not only are you generating attack traffic。 It's actually being treated better than other traffic on the Internet。

If the type of service or getting high priority traffic comes with an extra charge。

 you have to pay more for your service， then you can combine asking for high priority traffic with spoofing the source address。

 and you're now passing the bill off to your victim。This is why in practice， as Rob was saying。

 pretty much all operators， they either they set or use the type of service field themselves。

 they don't let end users or end host， actually she said it。Implications of fragmentation。

 I think we kind of cover this This。 if you send packets that are too large that are larger than the M U with IPV4。

 we know that the router has to fragment it， which means the router has additional work to do。

 So one way to actually attack a router is to send a lot of packets that are larger than the M U and force the router to do a lot of work。

Security I P options as well。 I think similar attack。 I P options， as God mentioned。

 require additional processing at the router。 Often this is done at the control plane of the router or what we call the slow path。

And so again， if you want to try and attack a router。

 send it packets with a lot of options and the route， you know。

 you're using more of the CPU resources at that router。And again。

 this is the reason why many routers will either ignore packets options or they just altogether together drop packets that have options in them。

Implications of the T T L。 we covered this already。 It allows discovery of the topology。

This is actually what gray Sc exploits。This is arguable。

 Some of us think trace is a great tool that you can use to discover your network topology。

 Some operators think it's a terrible tool because it allows others to discover their topology。

 Which side of that argument you come down on。Accordingly， operators will configure their routeers。

 If you run trace out， you'll often see that it doesn't make it that there are some routeers along the way that don't respond。

 It's because those operators have configured their routers to not respond to T TL exceeded messages。

So you can start to see a pattern here of。Fields that had security vulnerabilities。

 and operators have responded by disabling them。I could not think of any problem with the protocol field or the checkum field。

 if you come up with an attack， let me know thats always surprising things。But that aside。

 I think those were all the security issues I could think that you know。

 are notable and people have come up with。

![](img/e4615fb309d2345ae939845e2643563f_13.png)

Any other thoughts on security before I move on。

![](img/e4615fb309d2345ae939845e2643563f_15.png)

Okay， so with that， recap the I P header design， I hope you feel like it's actually more nuanced than it first seems。

 It's very easy to look at the I header and。Sort of walk through the fields and just say， okay。

 check， check， check， I get it。There's actually a fair amount of careful thought that goes into what is in that headover is not and why。

And all of this comes from， you're actually juggling multiple goals。

 You want an efficient implementation。 You want it to be secure。 And importantly。

 you also want to design in some ability to evolve to meet future needs。

The IP V4 header did a reasonable job at many of these。

 I think the IPV 6 header does a slightly better job。

 Securityity is the one area where there's still clearly a whole。Without any questions。

 we are leaving the network clear， otherwise。O。So with that next topic， were moving up a layer。

 we're going to the transport layer in L4， and we're going to start talking first about reliability and how do we implement reliability at that layer。

 Today's lecture we're going to cover the basic concepts and mechanisms。

 The next lecture we're going to talk about TCP in the protocol details。

 This is very similar to how we did BGP or how we did routing。

 we're first going to get the basic concepts Then we're going to assemble it into a protocol。

This material is not on the midterm。Please don't leave the class guide away。 I will cry or something。

 So sit through it。 It's actually useful for project 2。

 and it's going to be critical for understanding TCP。😊，So just， you know， basics。

 why do we need reliability？ I hope this is pretty obvious to everyone。

 If you're going to transfer a file on the Internet。 you want to know you got the file。

 you got it correctly。 You got it in its entirety。 So we need reliable transfer The challenge is how we're going to build this on top of a buggy network or best effort network。

 And so this is really an exercise in trying to reconcile kind of application abstractions。

 What is it that application developers want as an abstraction when they're building applications。

 versus what are the abstractions that we can easily support in the network we've already said we're going to do a best effort。

So quick recap of things we've said in the past about reliability。 We've said that reliability is。

The job of the end horse， not the network。 right And we went through this whole exercise with the end to end principle that LED us to conclude that we want reliability implemented at the endhor。

We also said that we were going to do the liability of the， the transport layer。

And that's implemented in the operating system。And the argument for why we are doing it there is one of convenience。

 Otherwise， every application would have to implement what we are about to discuss for the next two lectures。

 How do you actually we。Build a reliableable transfer on top of an unreliable network。So with that。

 what are the semantics of correct delivery at the network layer we've said the semantics we shooting for are best effort for delivery packet may or may not be delivered。

What you're going to see is that at the transport layer。

 the delivery semantics we're going to support are what we call at least once delivery。

So at the transport layer， the receiver is going to receive every packet at least once。

It might receive the same packet more than once。And you're going to see this as kind of。

 fundamentally。The， the model we have to live with， given a best effort network underneath。

And then later， when we get to things like H T TP and the application layer on top of TCP。

 you're going to get exactly one's delivery。 So when Ilily transfer file。

A from point A to point B at the application layer。

 it gets to just think that the entire file was delivered exactly once and reliably delivered。

The transport layer sitting underneath it is going to see certain packets or bits of that file multiple times。

 maybe， and it's going to have to learn to deal with that。跟。So goals for reliable transfer。

 anytime we start our design。 first， we talk about the goals。 So correctness。

 which is what we just covered， which is that the destination receives every packet。Uncorrupted。

 at least once。That's our correctness goal for the transport layer。 What else would we want。

At schools for reliable transport。Some'm trans。A bunch of packets of file from point A to point B。

I want it correctly transferred。 What else do I want here。你说。So timeliness。

 no one wants to sit around waiting forever for the packets to arrive。What else？Efficiency。

 that's the last one。I could implement reliability liability by sending every packet 10 times。

That might even be pretty quick。 It might would probably do the job。

 It's not a very good use of bandwidth to just say， I'm gonna consume 10 times more than I need。

 So we would like to avoid sending packets unnecessarily。One thing to note。

 our correctness condition said at least once， but there is never a guarantee on the Internet that you will for sure reliably transfer a file or reliably transfer。

 deliver a packet。There is always the possibility that the sender cannot reasonably deliver the packet。

 An extreme example would be if your network is partitioned。 you have no path to the destination。

So it's totally valid behavior for liability protocol to say I've tried enough。 I'm giving up。

I could not transfer this packet。The only thing that we ask in that case is that that the sender transport layer。

 the sender side has to tell the application I failed。This transfer field。

And under no circumstance should that transport layer implementation say。

 I succeeded in delivering the file when it actually failed。So it's okay to fail。

 but you should know that you failed。So with that best effort network。

 just to enumerate all the things that could go wrong。 We said packets can be lost。

We said that it could be coted。They can be reordered in case youve forgotten。

 you know let's say I was sending packet  one and followed by packet 2。 And then I had a go change。

 and packet 2 actually got to take a path that was faster than the one packet one was taking so。

Acceptable for packet 2 to arrive before packet1 at the receiver。Packets can be delayed。

 We've talked about queuees， packet sitting in queuees and incurringqueuing delay。

 and packets can be duplicated。 So it is actually possible for the network。To generate。

An unnecessary copy of a packet。 And we'll get to that in a minute。

These are all the things that can go wrong。 These are all the things that our liability protocol is going to have to fix。

Yes， so the way we're going to talk about as we develop the protocol。

 just a quick reminder of these kinds of diagram where we have time going down。

And we sent packets from a sender to a receiver。 They're going down in time and coming back to the receiver。

Half of that is the one way delay from send to receiver。The time for the packet to go and come。

Some kind of response to come back to the center is what we call the round trip time。Or the LDD。

Can we going to be using this as we go y？嗯。Not in this in what we're doing。

 So we would say it's the time for when the last bit went left to when the the act。

 the first bit came。 but we're also not doing these kind of microscopic calculations in here， y。Yes。

 it could。 So there's no reason why your one way delay has to be exactly half your go trip time。

 And all the examples we'll be doing here。 Yes， but on the Internet end to end， no， you're right。

 And we talked about this with B G P， that parts could be asymmetric， for example。

Any other questions。Okay， so let's get started designing a liability protocol。

 And we're going to start with a single packet。This is very simple。

 but it actually highlights most of the building blocks we're going to need。

 So let's step forward fairly slowly。 So remember， these are all the bad things that can happen to a packet。

And we're going to say we have a sender here that's trying to send a packet to the gazebo。

And the packet gets dropped。Here the packet got lost。What should the center do。

We've seen this already in a different context。Yeah， set a timer， right？

So the send is going to start a timer when it sends the packet after some amount of time。

 if it's not heard anything back from the receiver， it's going to time out。Or the timer will expire。

 and it's going to resend the packet。It's going to keep doing this。 So the receiver。

 when it receives the packet， is going to send back what we call an acknowledgement saying。

 I got the packet。When the acknowledgement reaches the sender， the sender is going to cancel。

It's time。This is kind of the very basic mechanism。Are we good with this？行。

What if the act got dropped。Do I need to do anything more than that， No， right？I just had a timer。

 I timed out， I sent the packet over。And this time it made it too， the act comes back。

 the center is heavy。So we will lively deliver the packet。

 but notice the receiver received the packet twice。This is fundamental。

 Can you think of a way we could have avoided having the gaze。See the packet， twice。

You actually can't because there's no way for the sender to be able to distinguish between the packet was lost versus the act was lost。

So the center has to retransmit to the receiver is going to see it twice。

This is not going to worry us。 This is correct Why our goals of at least once delivery。

 We got it there at least once。 We got it twice， but that's fine。跟。

This brings up the question of how do we set timers， If your time is too long， you're unnecessarily。

 you're going to delay delivery。 You're going to wait too long to read transmit。

 If your time is too short， you're going to unnecessarily send multiple packets when you didn't need to。

What is ideally what， what kind of timer do we want order what time scale。

What roughly would be a good timeout value。The same as your R TD。 So ideally。

 your timeout should be proportional to your go trip time。 In practice。

 this is actually not trivial to get right。 And we're going to talk about this when we talk about how TCP does this。

 because your gun trip time can be anywhere from know10 microseconds to hundreds of milliseconds。

 So you have many orders of magnitude。Diffences in your path。 So you， if you said it wrong。

 you could be。10000 times slower than you need to be， for example。

So we're going to have to learn that R T T， Also， it varies in time。

 depending on what the load on the network was， whether your packet was in a queue or not for how long it was in the queue and so on。

 So actually estimating a time good timeout is a nontri question In practice， your timeout is。

What you would， you know， it if all else has failed， then you would take a timeout。

 But you're never happy to actually have a timeout。

 We're going to try and work pretty hard to not have to rely on timeouts。But so with that。

 we now know how to deal with packets or acts that get lost。How about packets that got co。

 So now I sent this packet along。A few bits got flipped along the way。

What are we going to do to deal with that？ Again， we've seen the mechanism for this before。Yep。

 so we had this checkum。 So we're now going to computer check some at the destination。

 make sure that it matches what the packet sent。 This is not the same as the IPV4 header。 checkum。

 that check some was just over the header。 We now need a checkum over the entire contents of the packet。

 We're checking whether the file was actually correctly to transferred。

So we're going to need a check sum that covers the payload。If the jackum fails。

 youre going you could send back feedback to the sender saying this is a negative acknowledgement。

 You sent me a bad packet。 We call that an。For negative acknowledgecment。

 And then the sender can resend the packet， assuming it made it through this time you would correctly transfer。

跟。Is there something else you could have done instead of sending an act。Yeah， just do nothing。

 Just drop the bucket。And exactly the same mechanism we talked about with timeouts will work。

So if you believe that bit errors corruption is very。

 very rare and you don't want the additional mechanism， It's totally fine to not have nas。

 Just don't bother doing it。 And TCP， in fact， doesn't have negative acknowledgeledments。

So with that， we now know how to deal with packets that can be lost or corrupted。

 What about packets that get delayed。 So let's say this packet here gets delayed。

 makes it on its way to this receiverce。Check some worked out。 You got back an act。

Is there any problem？Not necessarily right if your packet was delayed。

 but got there before your time out， you're just fine。If it got there after your time out。

 what would you do， The send will send a duplicate。The gazeva will send a duplicate another a。

 So we now got both two packets。 The packet was delivered twice at the gazeva。

 and the act was delivered twice at the centerer。But it's not the end of the world。

 This is still a correct delivery of the packet。Okay， so were good。

 We don't need any new mechanisms to deal with delayed packet。If you walk through the same。

 but reason about delayed acts， you will see that were still fine。

So we can also deal with delayed packets。What about if packets are duplicated。

 So what does a duplicated packet mean here， It means that the network somehow generated a duplicate packet and sent it。

 It sent a copy of the packet to the destination。 You first thought really the only thing that's interesting about this case is why would this even happen。

 This is very， very rare。 But it has been seen to happen on the Internet。

 And it's usually because you have some kind of link technology that is doing reliability at that link。

And so at that link， one end， the sending side of that link decided to retransmit a packet because it thought the other end didn't get it。

 So to retransit the packet。 And then the receiving end of that。Link。

 forgot or it had deleted the state that told it that it had already forwarded that packet。

 And so it sends it twice。So it's really this corner case。Very。

 very few occurrencecs of anyone ever seeing it。 But actually she B Paxson。

 who was on the faculty here was the first to actually publish that this was a thing that happened。

 And he went to the routeer vendors and said， your。

 your router your link technology is duplicating packets。 and they were like， no way doesn't happen。

 And then he was I can show you that it happened。 And after much back and forth。

 He actually convinced them that they had a bug in their implementation and this could happen。

 So there what happens。From my point of view， let's not worry about how it happens。 If it happens。

 what， what do we do in terms of reliability。Is this something we have to worry about？No， exactly。

 You got a duplicate。 You sent another act。 The sender got two acts。 The sender was already easy。

Prepared to deal with that。 Okay， So we're good。So with that。

 we actually know how to deal with all the things that can happen when you have a single packet case。

 We don't have to worry about reordering。Just yet， because we're only talking about a single packet case。

So we now know how to reliably transfer one packet across the Internet。It's a very simple algorithm。

 Sender sends a packet， sets a timer。 If it doesn't receive an a in time， itll re sends a packet。

 He sets the timer。 Lucva， very simple。 You get a packet。 You send an act。跟。Any questions on this？

This should be really simple。 Okay， so what have we learned。

 What we have learned actually the building blocks for a solution， We now know about checkums。

 feedback， either positive or negative acts， V transmissions at the center and setting timers that when they file。

 we're going retransmit。We also have in place， semantics of a sed。

That both the center and the receiver could see more than once delivery。There are no questions。

 I'm going to move on to multiple sending multiple packets。

 So now we' are going to talk about sending multiple packets。

 What the only design component we actually have to add to the ones we had is the notion of sequence numbers。

So now we're going to say that data packets carry a sequence number。

 and the act tells you what sequence number is acting。 So like here you have packet  one。

 and then you have act1， then you send two and you're acting2。

That's really the only mechanism we absolutely require。 So with that。

 we have all the necessary building blocks to actually build。A reliable protocol on the Internet。

 This trauma man that all the textbooks will discuss。 and somewhat surprisingly。

 some people actually use this in practice， wouldn't advise it Def not on the Internet。

 is what we call a stop and wait protocol。the stop and wait protocol is as simple as can be。

 It uses the single packet solution we just delivered。

It says you wait for packet I to be acknowledged before you send the net next packet I plus one。

This is actually a correct reliable delivery protocol。It's also an extremely inefficient one。

 You're sending one packet every ground trip time， in the best case。So if you look at it visually。

 this is what we're doing。Sent packet one。 Wait for the act。

 When I was wait waiting for act 3 and I didn't receive it。 I took a timeout， resent it。

 And only after I got act 3， I sent packet 4。This is actually a reasonable protocol。

 If your ground trip times are really， really tiny。 So sometimes inside a machine。

 you will see different components on a server doing something like stop and wait。

But across the Internet， where you have hundreds of milliseconds long trip times。

 this is not something we want to do。So what would you do to make this go first。

Standard trick in computer science。Yeah， so paulism or by planning。

 Just send multiple packets out at the same time。We call this having multiple packets in flight。

What does that mean that the sender sent out multiple。

 It's okay to transmit lots of packets that have not yet been acknowledged。

So you can have multiple packets in flight。That are waiting to be acknowledged。

And so now things start to get a little bit more interesting。

 So this is what we call window based algorithms。 So basic idea is we're going to tell the sender you can send up to W some parameter W number of packets in flight at any time。

W is what we call the size of the window。And so a simple algorithm just extending what we did so far was to say the sendduct can now send W packets。

And when it gets one a back， it's going to send the next packet in line。So what does that look like。

 Let's say here we had a window4。So the sender got to send packets 1 to 4。 And now it's waiting。

So its window at this point is 1，2，3， and 4。 These are the packets in flight。 Again。

 packets that have been sent but not acknowledged。When I the send gets back act 1。

It's now O to send5。So now it's windows 2 to 5。 So we call this sliding the window forward。

When you get the act for two， you slide the window one more time and you're allowed to send6。

So at this point in time， your windows packet number 3 to 6。 These are packets。

 W packets that you were allowed to send your waiting for act。Everyone good with this。Okay。

 so going back to， we said we had all the necessary building blocks in practice。

 we have this one more parameter。Mechanism， that's the window and the window size。

 We do this for efficiency， not for correctness。The stop and wait protocol we had was correct。

It would correctly deliver packets。 This is all about performance and optimizing for efficiency。

 at this point。But once you have windows， a lot of design questions that open up。

 First is just what is that window size， How many in flight packets do you want。

The second is the nature of the feedback， because if you think about it now。

 the receiver is sending all of these acts one after the other back to the sender。

Could it be sending more useful information than simply， you know， I got I received packet 3。

 could be sending you something about the history of the packet it's received。

You could then use that to detect loss as we're going to see， depending on which act you get。

 it's a pretty good indicator of which packets the receiver did not receive。

 So maybe we can do better than waiting for timeouts。And finally， how do you respond to loss。阿照。

As you start seeing these acts come in。 So this is going to set up the kind of the questions that form what we call a window based reliable protocol。

Let's start with one of the first question。 How big should the window be。Thoughts。

 how big a window do you want， What are the considerations we have to worry about。嗯。

The bandwidth of the link， right， So you want to take advantage of network capacity。

 this notion of filling the pipe， sendend as many packets as you can。 At the same time， what do you。

 what should you worry about， maybe。要。The M U of your network。Yes。

 I wouldn't have said so much for liability because。Say more。

 because if you send something more than the empty U， the network will fragment it and send it out。

 which。The fragmentman school still arrive at the destination。

So remember that now we are up at the TCP at the transport layer。

 So all the reassembling of fragments and all of that has been done by your layer 3 implementation。

It得 at这个媳。So you at your transport layer， you're now receiving the full packet。

 So we actually don't have to worry about fragmentation at this layer。给。

So remember the go is just getting packets。 And so if your question is between two packets。

 one of them needs to be fragmented， the other not。没对。So your router is not seeing files。

 It's just seeing packets， and it's just taking one packet at a time and sending it out。

 And we could be doing more fancy scheduling。 But for most of this， suddenly for this discussion。

 we're saying that routers are just doing five for order scheduling。

 So whatever order the packets come in， I'm going to send them out。有。We're gonna get to that。

 Hol on to。 so other things you should worry about in terms of picking your window。

 you want to make full use of the pipe you have， but you also don't want to overload links because if you overload links。

 you're going to end up with dropped packets。 not a good idea。

 So this is a problem we call congestion control。And the other concern。

 which we haven't yet touched on， but we're going to start to worry about is you also don't want to overload the receiver。

Because the receiver can only pick up packets at some rate has a certain amount of buffer。Space。

So you don't want to overload to the receiver。 We call this flow control。

For this lecture and until we get to congestion control， ignore the first， the second two concerns。

 They are concerns。 We'll deal with them when we get to congestion control。So for this lecture。

 just say that we're focusing on the first goal， which is we want to keep， we want to fill the pipe。

Right，And if we want to fill the pipe and fully use network capacity。

 what does that mean in terms of the sender behavior that we are looking for。

What it means is we want the sender to always be sending for the entire round trip time。

 We want the sender to be busy transmitting。Okay， so for an entire round trip time。

 I want the sender to be busy。 What that means is that when an act comes in。

I want to be the sender should pick up the act and send out another packet。

Let's look at that visually。 I think it's。Much more intuitive when you look at it in terms of an example。

 So we said， in this case， your window was full。And the sender had sent forth packets。

 got these four acts。Your round trip time in this case is the time it took you for the packet to get to the receiver and the act to come back。

If you notice， there was a large fraction of that time that the sender was just sitting there doing nothing。

 waiting for the rack to come back because your window was too small in this case。

4 packets was not enough to keep the send busy。What we would have liked。Ideally。

 is that the center is always busy sending out a packet。

 and it had a larger window that allowed it to keep sending for the duration of the gun trip time。

So what does this mean when we think about it moreuously， what we're saying is。

 let's say that B is the minimum bandwidth of a link along the path。

 It's what we call the bottleneck bandwidth。So there's no case in which the sender can be sending faster than the bottleneck。

半主的。That's as fast as it could send。But you also， under the assumptions we've made。

 we don't want the center to be any slower than that bottle I create。Because otherwise。

 you're wasting capacity。And so what that means is that for this setup。

 we want the centerer to be sending at the rate B。 This is the bottleneck rate for the entire duration of the ground trip time。

So this gives us our condition that we want。Windows， the W parameter to be set。

Such that the window size， which is how many packets you can send times the packet size。

 Let's assume of constant packet size here。Is the ground trip times。

Delay times the bottleneck bandwidth。Is this making sense？Let's look at it visually， because。We。

 we all trip on this。 So in this case， what I'm showing you here is one link。

 but I'm showing it to you in a bidirectal lab。 split up the。

Part going from the center to the receiver and coming back from the receiver to the center because remember。

 a link is bidirectal。I can send B Bs per second， and I can receive B bits per second at the same time。

So in this case， I'm saying my window at the center should be six packets。系。

And if you look at the pipe， I have three packets on their way to the receiver。

 and I have three acts coming back。To the sender。 So there's six packets that the sender has sent。

But they're not acknowledged yet。So everyone， the， the thing that confuses。People they。

 look at the pipe， and they say。It can only hold three packets。 Why isn't my window size 3。喂。

But if you think about it， if we'd said the window size was 3。

 what is the sender doing while it's waiting for the as for those three packets to come back。

It's not doing anything。So if we really want what we call an act clocking behavior where every time I get a knife。

 I put a packet in。Then I need my window size to be the ground trip time。

The delay going to the receiver and coming back times that bandwidth。Any questions on this？느く요。行。

So that's the window size。 We're going to try and set the window size based on the ground trip delay。

So now let's talk about what we can do in terms of design options。

Now that we have multiple or W packets in flight。So what we've been talking about so long all this time is what we call individual packet acts。

Which is when the receiver gets back at I， it sends back an act saying act I。

 meaning I received back at I。If you look at this in the context of a window。

 you'd realize this we could be doing better。 So here's an example where I sent four packets。

 all four of them made it。But Act2 was dropped。With the protocol we've been designing so far。

 what would the sender do it would take a time out on packet to because it never received the act。

 and it would beended。But packet2 was actually received at the receiver。

And the gazeva sent me two other acts or a bunch of acts after that。

So this should tell you that you could put something into the ax。That would allow the send。

To kind of tolerate the loss of an act。To figure out that packet2 had reached even later。Thoughts。

 what would you do。You get to redesign acts now。A new type of act。

I'm going to take that and flip around。 You're getting there What you could do is something we call full information Act。

Which is when I send an act， I tell the sender all the packets I have received。So far。

 because why should I only tell you about one packet。

 I can tell you about all the packets I've gotten so far。

So the way this would work is you would give the highest cumulative act。

Which means that you've received all packets up to that sequence number。

And then any additional packets that you received。So something like I got everything up to sequence number 12。

And then I received packets 14 and 15。What would that look like here？ So with cumulative acts。

 your as would now look like what you have there on the right hand side。

You'd be saying I got everything up to one， everything up to 2， everything up to 3， up to 4。

So in this case， trivially， the minute the center received the Act for packet number  three or the act for packet number 4。

It also knows that you received two。 And so it doesn't have to read transmit2。给。

This was a pretty case。 It doesn't always look this pretty。 Let's say that in this case。

 you lost every other packet。 So you lost packet2。 you lost packet 4。

So what do your acts start to look like in this case。So when you got packet at one， you said。

 I got everything up to packet at one。But then the a when you got back at three says I got everything up to one and I got three。

When you got back at5， you say I got everything up to1。 I got back at 3， and I got back at 5。哎。

So you can see that the information you're starting to put into your act is not scaling so well。

 It's starting to get kind of long。Is this making sense to them。So， we like full acts。

Full information Acts， because they tell the send exactly what's going on at the receiver。

 There's no guesswork。But the problem with them is they don't scale very well。

 There's too much information in there。In the worst case， you could have as many。

The size of your full information Act could be on the order of your window size。

 which can be tens of thousands of packets in practice。So that brings us to our last type of act。

 which is kind of trying to achieve a sweet spot between the first two。

 It's what we call cumulative acts。Which is saying。

 I'm going to take the idea from full information Acts of telling you what's the highest sequence number I've received。

 such that I got all packets before that sequence number。

But it's going to drop that trailing edge of which other packets have you out of order packets have you received。

So it's just the high sequence number for which all previous packets have been received。

Any questions on what cumulative act meets？ so let's see them in action。 So in this。

 going back to that example here， where Act 2 was lost。 So in this case。

 the cumulative acts interestingly look exactly like the full information Acts。

And that's actually not surprising because we didn't lose any data packets。

So the Act is just telling me I got everything up to the packet number two， up to  three， up to 4。

And so in this case， cumulative acts。Behaves exactly the same as full information Acts。

The minute you get the Act for packet 3， you know that it also received2。

 the sender is not going to be transmit 2。In the case where I lost every other packet。

 like packet 2 and packet 4 in this case。This is where you start to see a difference between cumulative acts and full information acts。

Because in every case here。The receiver was just saying， I got all packets up to one。哎。

So cumulative acts， it scales better than full information acts。

 but it can be ambiguous about exactly what the destination received。

 We've lost some information there。And as you are going to see， when we start designing TCP。

 TCP uses cumulative act。And TCP tries to guess what the receiver has seen。

 And so things get a little tricky。There is one thing to note， though。

 that every time you get one of these acts， you are learning something about the receiver。

 you're learning that the receiver received some packet。

You're just not learning exactly which one it received。Let me recap the Act tradeoffs。

 And then let's pause to see the questions of individual acts。This is when I get back at I。

 I say a I。It's very simple。 It's very compact。The problem is， if you lose an act。

 you will always have to take retransmit that packet。

 You always have to take a time out and retransmit。And remember， we don't like time modes。

With full information Act， suppose you have all the information you want。 There's no ambiguity。

 You're completely resilient to act losses。The problem is it takes a lot of overhead in the act packetative to actually enumumerate all these packets。

 And so cumulative acts， they are compact。 They are as compact as individual acts。

They are more resilient to act lost。 So as you saw when that act was being lost。

 cumulative acts recovered from it。But it is incomplete information on which data packets were actually received。

You have a good indicator of how many packets were received， but not exactly which ones。

Any questions on this， let me pause you。要。Well， so， for example， in the case where you had the als。哎。

If I had individual acts， I was G transmitting packet2 here。

Because I never received any information about packetet2。But here。

 when I get the cumulative Act for packet 3。It's telling me I got everything up to bucket 3。

So the center knows not to。To resend。大概那么多。对。So for the next case， you're right。 It doesn't know。

 And this is going to come back to a trouble us， but it does tell us something。

 which is the presence of an act tells me that a new packet was received。

So I know how many packets will received， I don't know which ones。If you're feeling like。

I don't like cumulative acts。 I agree with you。But those are the trades that come with it， yeah。Yeah。

 so I think the question is， why don't we do a better job of trying to scale full information acts and say that I'm going to give you full information on some piece of it。

 I that yes， and so that is something it's approaching something called selective acknowledgeledments that TCP uses。

 The reason we talk about cumulative acts is TCP uses cumulative acts。

Because they were really concerned about keeping act small。Over time。

 there's been this new extension sack or selective acknowledgement that we'll also cover。 But yes。

 you're absolutely on the guide track。I think the question is all。

 there's a spectrum between cumulative and full information。 and it's an interesting design point。

 yeah。Why wouldn't you send which ones you didn't well。You could。

 It's a reasonable design to consider it's says。Youd， I would have to actually walk through the case。

 but here would be my intuition would be when I tell you which packets I received。

 that's correct information。 When I tell you which packets I didn't receive。

 it might just be delayed and coming in。 So if I tell you， I didn't receive two。

 and then I conceive two right after I send that。The send is going to be transmit to。If you。

 if you believe the information。Any other questions on act types？So we use these act types。

 some of them is， you know， theyre what is used in protocols。

 Some of them is also just to show you the design space。

It's not the only kinds of acts you could come up with for sure。

 but these are the ones we are runningning with and sort of analyzing。So with that。

 what do these act options mean for detecting laws So so far。

 we've been saying that the way you detect laws is that you have a timer that expires。

 So if the packet time， it times out， you assume it's lost and you resent。

 But now that we have all these acts coming in， as you've already started。Figuring out。

 you can actually look at the acts that you're receiving。

And use that to decide whether you think something is lost。Okay， so a reasonable rule is to say。

 I'm going to look when I receive case subsequent acts after the packet I was expecting。

So I was expecting a particular packet act。 And if I didn't get it。

 but I got case subsequent acts for other packets。Then maybe I can decide that that packet is actually lost。

So as an example， let's say that only packet5 was lost。

 So the sender had sent a whole bunch of packets。And I've received act up to 4， and I'm expecting 5。

 I'm expecting an act for 5。And I haven't received an act for 5。 But now I received an act for 6。

 So when I received the act for 6， you could think， well， okay。

 maybe there was a little bit of reordering。 Maybe the act for  five was delayed。

 I'm gonna to hold on。When you receive the act for7， you feel like， okay。

 that makes two acts I got that were beyond what I expected。 Maybe packet 5 or act 5 was really lost。

And so you can go on that way and you have some number of key。

Which is after you've gotten case subsequent acts， you decide， okay。

 the packet I was expecting is lost。 I'm going to treat it as lost， yeah。

It depends which a mechanism we're using。 So your guide。

 it will be a little different depending on what type of act we're using。

 But I will receive an act for that packet。 What I mean by that is that data packet6 arrived。

It caused the receiver to send me some a。And that I'm receiving an act corresponding to packet 6。

 It's not necessarily an act that's telling me this is packet 6 was received。

 And we're going to do that in just a second。Okay， so exactly how this looks depends on the act you're using。

 So let's actually walk through this。 So let's say we had individual acts。

And only packet  five was lost。If you look at this stream of acknowledgements that the sender is receiving now。

はい。This is individual act。 So I receive packet I， I send a I。

 You're gonna see a stream of acts that look like this。As you can see。

 we never got an act for backet 5。So after we've said case subsequent acts。 So in this case。

 let's say it's3。So after I've gotten an acknowledgement for packet 6，7 and 8。

The sender is going to say by this school， it's going to say packet 5 is lost。O。So this is。

 we're going to treat this as equivalent。To a timeout。At this point。

 we've decided back at five is gone。行。With full information， it's exactly the same story。

 except that it's even more explicit where the whole is。

Because the acts you're getting from the sender are going to tell you， I got up to 4。

 and then I got 6。And so on。And until you， when you receive that you got up to 4 and 6，7，8。

You can see that the deceo received。Pe packets。Beyond5。

 And so you can declare by this rule that packet 5 is lost。行。What about with cumulative acts。

 And this is where cumulative acts come back to bugs a bit。

 So what your as would look like in this case。Is when you had packet 6 arrive at the receiver。

 it sent back an act saying， I received all packets up to four。

we call these duplicate acts because they're saying the same thing。As when we received backet for。

 when we got the first act for backet for。And so the same rule in this case with cumulative acts is after we get three duplicate acts or du backs is what we call them。

Then we say that back at five is lost。行。Someone already pointed out。

There's a hitch here with cumulative acts， right， I got three duplicate acts。

It tells me that the receiver received three packets， but I don't know which packets these are。

 I don't know that it was 6，7 and 8。It could have been 7，8， and 9 for all I know。We don't know。

 We're going to have to deal with this。Any questions on this。

So this is just using the extra acts we're getting in to declare a packet as being lost or not。

So what we're going to do with this is now decide when we make this decision。That a packet was lost。

How do we respond to it。The thing we want to do is resend the。

Is weend the packet that was that we believe was lost。 But as we see。

 this can give be a little tricky。 So let's walk through that。 So response to loss， so far。

 we've said on timeout， always re transmitm the corresponding packet。Okay。

What about when act based rule files。So what we've seen so far is that when we have。

There so three subsequent packets that have been act。Event occur， you will re transmitmit the packet。

That you think is missing， right？With individual acts or with full information acts。

 which packet you should retrans is very clear。 The whole is very clear in the stream of acts that you got。

With cumulative acts， if you have a single packet loss， it's very clear。

But what we're going to see is that when you have multiple packet losses， it's sometimes not clear。

I have a detailed example in the backup that we'll walk through if we have the time。

 but otherwise I hope you can see the intuition here， which is I received duplicate acts。

 but I didn't actually know which packets were received as the receiver。

 And so I'm going to have to guess when I retransmit a packet。So the response cumulative acts issue。

 they don't have the sender exactly which packets were received。

 They do tell you how many packets will received。 That's the number of duplicate acts。

Not which ones to resend。And so that leads to some amount of guesswork around which one you should retransmit。

 And when we do TCP， we'll talk about how TCP does this in detail。

Let's come back to this if people want to actually walk through the example。 But for now。

 let's back up a level first and just taking stock of what we've done in terms of design building blocks。

 we have all of the design building blocks that we need to implement a reliable transport protocol。

 check sums， acts， snacks， timeouts， retranss， sequence numbers in windows。

They are trade offs in how you apply them， whether you have cumulative act versus full information and so on。

But what you can do now is take all of those design options and design a reliability protocol。 Okay。

 we've seen one stop and wait。 That was the one packet at a time。

There's another very simple variant called Go back end that you'll see in section。

It's another one of these canonical examples， not very useful in practice。

TCP is the one we will do in depth next time。But I think it's more important that you can reason about how to design a good liability protocol from these building blocks。

 because， in fact， as you see， TCP is not a perfect protocol in how it combines these building blocks。

It's starting with the fact that it does cumulative act so we can do better， and we'll do better。

Just a quick preview of what TCP does。 It actually uses all of these building blocks。

 Most of them that we've covered。 It does use check sums， uses as， no NAs， has Windows。

 sequence numbers， cumulative acts。And it counts the number of duplicate acts。

It does optionally have this option for a form of full information acts that we call selective acknowledgements。

 So we'll cover that as well， and then it has these time of estimation algorithms。Let me jump。

' going to skip this for today。 Let me jump to example of ambiguity with cumulative act。

 How many of you feel like you want to see the example。So let's see where the issue comes from。

 So let's first look at responses with individual acts。 Okay。

 The example we're going consider here is a center that has a window size of 6。

And we're using a value of k equal to 3 meaning when I get three subsequent acts。

Not the packet I expected。 I'm going to declare the packet as lost。So in this example。

 packets 1 and two have been sent in act。3 to 8 are in flight。

 So what I'm showing you here with these numbers are the sender's view of the window。

Where are the packets that it has sent。But not， they've not yet been acknowledged。

 And you can have up to six of them because that's your window size。

And now let's say that you had two packets that were dropped 3 and 5。

So now what happens at the sender when Act 4 arrives。 what is the center going to do？

 It's going to say， okay， packet 4 was delivered。 I have a window size of 6。

 so I can now send packet number 9。When Act6 arrives。It says， okay， packet 6 arrived。

 I'm allowed to send out have6。In flight packets， I'm going to send out 10。Are we good to that。Now。

 when the seventh act arrives， this is the third subsequent act。So the send is going to say， okay。

 packet3 is lost because I've gotten three acknowledgements after three。Without resing to。

So packet3 is gone， so that means I can resend3。Plus， I received an act for 7。

 so I can send one more packet so I can send 11。Doess everyone good with this stuff。

It's a window in the sense of how many outstanding packets can you have。没 good to that。

So when we do T CP， well do the actual how you maintain the variables and what range of windows you can。

Have outstanding。 But for now， it's six packets in flight。行。So what happens when Act 8 arrives。

So at this point， you've gotten three subsequent aknowments for back at 5。

 right you've gotten the act for 6， for 7 and for 8。So you're going to declare at this point。

 packet 5 is lost。So you're going to resend5。And you get to send12。

Is everyone comfortable with why I get to send two packets。有O可以。And then when 9 arrives。

 you you continue， you send 13 and so on。 So this is pretty clean。

If I did the same example with full information Acts。

 it would look exactly the same because you're getting the same information。 So we're going skip it。

 but。Walk to it in your heads。So now let's walk through this with cumulative X。ok。

So when you get the act corresponding to packet 4。What you receive at the center is something that says acknowledge。

 I'm acknowledging， too。Okay， so this is our first duplicate act。

But I did get one packet out of the network。 So I get to send one more。 so I send9。

When I get the act for packet 6， it is still saying acknowledgement2。

The number of duplicate acts I now have is2。So， I'm going to send in。Everyone good with it sofa。

When I get the acknowledgement corresponding to packet number 7 now， So at this point。

 I have three duplicate act。So this is the point at which I decide。Backet plea is lost。

And it's clear which one is lost， right， Because I've gotten everything up to2。

 The reason that number is not going up is because3 is lost。So I'm going to resend3 and send 11。

 similar to individual acts。Are we good so far。Yeah。

So where the trouble occurs is when you get the next。Ac 2。

 so when corresponding to packet 8 being received， you get yet another act 2。And at this point。

 you have four duplicate acts。 so you know that there's a packet that got three subsequent acts。

You know that since a packet was received， you are allowed to send 12。

But which packet should you resend， You have no way of knowing whether you should resend 4 or you should resend 5 or some other packet。

Is this making sense。Okay，And so when we talk about TCP， we talk about how TCP addresses this。

 But this is the problem that is being addressed。 And since I have two minutes more。

 let me go back in time and cover one other thing。 So everything we've been talking about so far is reliability based on this notion of I'm going to send a packet。

 Wait for acknowledgements。 Send another packet。 It's a based。

 Any other thoughts on how you else could you do。Reliability。

If I didn't want to do this per packet accounting， or just a completely different designer approach。

Clear your heads of everything。 We've talked about this。要。You， you're on the guy track。

 So you could just send packets， keep sending packets until the send receiver receiver tells you I got everything stopped。

 And you mean keep sending the same packets over and over。Could you do better than that？

 So if I had 10 packets to send， I could just keep sending one to 10，1 to 10。

1 to 10 until this receiver receiver tells me I got all 10 valid。

 It's a totally valid reliability protocol。 It's not very efficient。

So happy to see I tell you which packets at once。Yes。

 that that would be a little bit of a pull based。 We're kind of using ae to do that。

For those of you who've maybe taken some E E courses， what we could do is use coding theory。

 and there is a large amount of work in this space。

 which is you take the data and you encode it to be resilient to loss。

 So the way this works is you take say K packets。You include them as some number。

Of packets n larger than K。So let's say you took four packets and you could encode it as seven packets。

And these codes have a property where it says you took four packets and you encoded them as seven packets。

 if you receive any。5 of these packets。 I'm making up numbers。

 But if you received any five of these packets， you would be able to reconstruct those four packets。

So there is this entire literature in different coding。Schemes you can use。

That would allow you to tolerate some amount of loss。But still not， you know。

 send every packet 10 times。 So you could just keep sending packets with some amount of redundancy built into the packet。

 And you can reconstruct the original packets from。The encoded streams。 So these。

 there's a whole literature on codes that have very different efficiency trade offs。

 We don't cover them in this class。 I just wanted you to know that coding theory and coding packets is a reasonable approach to doing liability。

 It's not commonly used on the Internet。 Some of the video streaming protocols have used this at the application layer。

 but it's not one of the。It's not made it to one of the the Internet's transport layer protocols。

But it is an option if you wanted to do a slightly different form of liability。

 The benefit here is that you don't have this back and forth on acknowledgements。

 You can just send a stream of packets。And it's to into a certain level of loss。

So without any questions？Thanks。Next lecture is a review lecture， mid term review lecture。Thank you。

We should this was off the end dark。

![](img/e4615fb309d2345ae939845e2643563f_17.png)

![](img/e4615fb309d2345ae939845e2643563f_18.png)

![](img/e4615fb309d2345ae939845e2643563f_19.png)