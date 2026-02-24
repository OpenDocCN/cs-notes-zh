# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P16：-15- Congestion Control Goals, Problems, Approaches.2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Good morning。 everyone。 Let's get started。 So topic for today， we're going to get started on。😊。

Congestion control。 And why is my clicker not working。Okay so this is one。

 as I mentioned last time why kind of one of the core topics in networking very much like routing It's also I think here at Berkeley we probably cover congestion control in far more depth than any other undergraduate class I've seen but I think it's both an important one and also a fun one so hopefully you agree with me at the end of this。

 The plan is for today we're going just go over the basic building blocks So the concepts in congestion control very much like we did with reliability and then Thursday's lecture we're going to do a deep dive on how these are used in TCP。

And it's very intertwined with how we do liability in TCP。

 so if you're still a little confused over sliding windows and timers and duplicate acts。

 we're going to be looking at the two in combination in Thursday's lecture kind of stepping through examples and then Tuesday's lecture next week we're going to touch on advanced topics in congestion control。



![](img/11018edd8a792c462a618f6dca42f598_1.png)

So with that， you know congestion is an issue that we raised way back when we started this class in lecture3 where if you remember we said if you're at a router and you get two packets arriving at the same time。

 the router buffers one packet and transmits the other and we said if the router is getting too many of these packets coming in back to back then your queue is going to build up。

 you're going to get increased packet delay and eventually you're going to have to drop a packet or you get lost and so that's the regime in which we say that the router is experiencing congestion or your network is congested and avoiding getting into that situation is exactly what this topic is about。



![](img/11018edd8a792c462a618f6dca42f598_3.png)

And， you know， why is congestion something we worry about， Why is it harmful， It's obvious。

 but just to reiterate， it's because congestion can actually quite significantly impact performance。

And so to give you some intuition for this， you know what this graph here is showing you is a theoretical model if you modeled the network as a queue where you have a link of a certain capacity and a queue sitting in front of it。

 And if you said you have traffic coming in that is bursty in nature。

 which you we've said that internet traffic is bursty。

Then what you get if you plot the average packet delay on the y axis as you increase the load on that cube on the x axis and the dotted line here。

 the vertical dotted line is the capacity of the link。

 what you get is delay that looks like what this graph is showing you here where it's really rising up and the two things to take away from this graph know without getting into queing here here or any of that is one is that you know fundamentally what we're looking at is a trade off。

That as I increase the network load， we would all like to run a network at the maximum capacity。

 It have perfect utilization。 What this graph tells us is you're not going to get that without trading off delay。

 without incur actually pretty bad delay as you get close to the capacity of the link。

And so a lot of congestion control is finding kind of that sweet spot where you want to operate where you're getting full utilization of your network。

 but you're not going to to a point that's unacceptable for applications。Okay。

 so that's one takeaway from here is internalize that there's no。

Perfect utilization and perfect delays where you want to operate on this curve。

 And the second is that what I'm plotting here is delay。And remember， that loss follows delay。

So by the time you see a packet loss， you're already in this bad regime of delay。

 So loss is actually really bad if you care about delay because you've already suffered the delay if you're seeing loss in your network。

嗯。A little bit， I just wanted to start with some history on where congestion control as a solution as a field came up。

 you know TCP， interestingly in the early from the when people started developing it。

 so we talked about Perf and others building TCP in the late 70s。All the way up to the mid80s。

 TCP actually implemented no form of congestion control。

The only thing that determined the rate at which aender would send traffic into the network was the flow control that we discussed last time。

Where the receiver has an advertised window， depending on how much buffer space it has。

 and it tells that advertised window to the send。 And then in the old versions of TCP。

 the send would just dump an entire advertised window worth of traffic into the network when it had a time out。

 it would just keep retransting an entire window of traffic into the network and the Internet was working just fine with this kind of behavior until about the mid。

It is where there was a series for period of time of what the users of the Internet and the people developing the internet observed what they called congestion collapses。

 and I just cut pastted the text here from a few of the people who were observing this and dealing with it and how their description of what they were observing。

 So this was Michael Kagggels and Van Jacobson who were both working on the Berkeley Uni system and developing TCPIP within Berkeley Unis here at Berkeley。

And what they saw here， as you can tell， is that the throughput going between the loggans Bkeley Labs which just up the hill from Soda Hall and Berkeley dropped from 32 kilo Bs per second to 40 Bs per second。

 And they were seeing this persistently for weeks。And so， you know，40 Bs per second is pretty much。

 it's a non functioning network。 I know you're probably thinking even 32 kiloBs per second doesn't sound like much。

 but that's what the Internet was doing。 or that's the performance you were getting from the Internet at that time。

 So it was a thousandfold drop in throughput。And they were curious。 So they， as you can tell here。

 they say they were fascinated by the thousandfold drop in Tput。

 and they set out to try and understand what was going on on the Internet。And， you know。

 these were the folks building the networking stack。

 So they were concerned that they had put a bug or done something wrong in the implementation。

 And along the way， they found a bunch of couple of issues that they fixed。

 One was with time of estimation。 So the time of estimation you studied in section with covered in section。

That you did in section just yesterday， you should have learned how you were doing adaptive time of estimation。

 The original TCP implementation didn't have that。And so especially as the network was getting congested。

 delay was building up， but the timeout value was not adapting。

 And so it continued to have this short timeout and was dumping traffic into the network。

And so Cas and Jacobson fixed the time of estimation algorithms。 But in the process， also。

 what they realized is that as more users were using the Internet。

 sources were not slowing down the rate at which they were putting traffic into the network。

 So they were not doing any of what we now call congestion control。 And so they put in。

Series of algorithms that we now call congestion control and it's an entire field into the TCPIP stack in the BSD system。

 So if you look up on Wikipedia Michael Cas and Jacobson are both wellknown figures in computer science。

 Michael Cas was actually an undergrad here at Berkeley at the time he did this work He was in the bio department of microbiology department I believe but he discovered that he enjoyed hacking and so he kind of drifted over into computer science and Van Jacobson was a more senior researcher at the Lawins Berkeley labb and Kas。

 if you look him up， he was actually ended up being the chief architect for Berkeley Unix So direct impact on Mis Windows。

 Linux， all of those systems have a legacy that comes from Kas Van Jacobson is know as famous in many ways as I wanted to elaborate a bit because his contributions to networking and congestion control in particular really noteworthy he was leading the networking group at LBL at the time when they did this work about putting in congestion control。



![](img/11018edd8a792c462a618f6dca42f598_5.png)

Hes has since had many contributions to the early TCP I stack and is the creator of many of the tools on the Internet that we use trace that you used。

 TCP Dump is another tool that allows you to look at TCP packets。

 bookley packet filter that is widely used everywhere that allows you to filter out certain traffic depending on certain patterns in your OS。

 He left LBL after quite a while there that ended up as cheap scientists at Cisco did a bunch of startups along the way and now like many people is at Google where he has interestingly enough。

 he's fairly senior at this point。Worked it continues to work in congestion control。

 So his latest piece of work a few years ago was BBL。

 It's a new congestion control protocol will very briefly touch on it。

 This is the congestion control protocol that is now underneath YouTube。

 Google search and really an increasing fraction of traffic on the Internet。



![](img/11018edd8a792c462a618f6dca42f598_7.png)

So really quite remarkable in his contributions to congestion control。 So with that。

 what was their approach， their approach is beautiful in a certain sense of simplicity was an incremental extension to what TCP was doing already。

 So they said looking at what TCP had in place TCP already had ways of detecting loss we discuss this when we did a liability either you time out or you have duplicate acts but TCP had that mechanism。

😊，And TCP also already had a mechanism in place for Windows。

That controls how much traffic the sender puts into the network。

 So their basic idea was to have the source adjust its window size based on loss。

So it's clearly as simple as that at some level I think what was great about the solution was it was both a pragmatic solution for reasons I'll get into it was also an effective solution the minute that patch was in congestion collapse went away and the Internet started functioning well again we've never had a congestion collapse incident happened on the Internet ever since since the mid-80s it was pragmatic in the sense that the solution they came up with required no upgrades to routes or applications。

And actually， you don't even have to upgrade both sides of the TCP connection。

 You just need to upgrade the sender side。And it was clearly a patch of a few lines of code in the Berkeley UniX code piece。

 and so in a matter of months， pretty much everyone on the Internet had adopted their congestion control algorithm and was gunning it。

So it's a nice lesson on wisdom and system design。 There's always you're always here。

 and I also strongly believe this that the best solutions in computer science emerge from a real need and a concrete understanding of the problem。

 this is one of those nice examples of Kaggs and Jacobson doing that。

 and it kind of goes beyond because Jacobson was a physicist by training。

 And so when you read his papers on congestion control。

 especially the early paper that I showed you a snippet from。😊。

He thinks very much in a way like a physicist he has in his head this you know。

 not complicated but fairly sophisticated model of the internet as a feedback control system that has to respect what he calls a conservation of packet principles so as to avoid congestion。

 but he doesn't try and build that complicated mathematical model into TCPO into Linux Unix at the time。

Instead， what he took from that fairly fancy model was a heuristic that captured the core intuition of what that model was trying to do and when we'll get to it next lectures。

 clearly a few lines of code changed， probably 10 lines of code that changed in their network stack。

So quite impressive in that sense。 since that work。

 its congestion control has been extensively researched and improved upon over the years。

 going back to 86， there are many， many variants of how TCP does congestion control。

 We are not going to talk about all of them。 Were going to talk about one fairly prototypical solution。

 If you understand one solution in depth。 It's not easy difficult to go from one variant to the other。

 You can pick up other variants quite easily。There are also radically different approaches that address congestion control completely differently from how TCP does that。

 and we're going to touch on them in advanced congestion control topic a lot of those ideas are actually now increasingly relevant in the context of data centers and now that we have more advanced routes。

 some of them look increasingly practical and so I think it's useful to know those。



![](img/11018edd8a792c462a618f6dca42f598_9.png)

So without congestion control more generally there's a huge literature on the problem。

 This is one of those topics that everyone likes to work on so the systems people have been doing congestion control forever。

 the control theory folks that studiedqueuing theory and feedback control systems also have worked on congestion control the game theoryists you know when I was a student there was an entire course at Berkeley on the Internet and game theory taught by Krystos Papa Metu who was a theory professor so that's how congestion control occupied 50% of those lectures。

And theres folks in statistics， as well as economics。Essential。

 you can think of bandwidth as a commodity or resource here。

 So you can see why economists would be interested in this question as well。Within the industry。

 there's always been people working on congestion control if you work know if you vendor of an operating system。

 if you cloud provider， if your content provider congestion control impacts performance。

 and so this is an area they look at the last five to 10 years has been a real increase in that interest in industry。

 So if you look at any of the large cloud providers or content providers or Netflix， Facebook。

 Google， Microsoft， they all have fairly large teams that are really just working on congestion control。

 So the last congestion control meeting I joined at Google there are about 80 people in that group meeting So that's how much of the topic it still is。

The reason why you know we see the return of interest shouldn't be too surprising。

 it's that everyone's competing on performance， so there's just huge pressure to improve your performance and congestion impacts your network performance and your network performance impacts the performance of all your applications。

 So getting at that foundational level is important to all of these providers。

The other is that new contexts are notably in that data centers。

 because congestion control was originally designed for the Internet。

Where you have large number of users， you have round trip times that vary from microseconds to hundreds of milliseconds。

 you have just a very wide range of behavior and environments。

 Data centers actually people know a lot more about that environment。

 your round trip times are typically tens of microseconds。 You know the sources。 you control them。

 And so there are certain aspects to a data center that you can exploit in designing your congestion control scheme that allows you to further optimize it for your specific environment。

 So data center congestion control is almost a sub area in itself these days。And then finally。

 we just have new methods。 So many one of the hot topics areas in congestion control is applying machine learning to actually do congestion control because if you think of congestion control。

 it's kind of you know you're getting packets coming out of the network。 They have a certain delay。

 They have a certain amount of loss。 It's like a lot of noisy signals or noisy data。

 And M is a great way of extracting the truth from that noisy data。

 And so people are trying to apply M to do congestion control。So with that。

 that's all kind of contacts any questions before we get to the nuts and bolts of things。



![](img/11018edd8a792c462a618f6dca42f598_11.png)

Okay so topics we're going to cover what makes congestion control a hard problem。

 the goals for a good solution， the design space of possible congestion control solutions。

 and then the components of a solution that are kind of the components for what that go into a TCP solution and finally we're going to do TCP's approach at a high level that we'll then dig into next week。

 next lecture under。

![](img/11018edd8a792c462a618f6dca42f598_13.png)

So with that just to， I wanted to start by just having you build some intuition for what's going on when we do congestion control and why is this a little bit hard。

 So let's take this example here where we have the link capacities， routeers and whose that you see。

And if you ask the question at what rate should host ASN traffic in this picture。

Your first thought should probably be， well， you know， it depends on the destination。

If a is sending traffic， C。You could send potentially， let's say，10 gigab per second。

Looking at the bottleneck along that path。 But if you're talking to F。

 then maybe a should send it no more than 2 GB per second。

But it also doesn't just depend on the destination。 It also changes with routing dynamics。

 So if you said A is talking to E， we would have looked at the path and said。

Tan gigabitzper second looks reasonable。But if under the hood， routing had changed。Remember。

 en hosts don't participate in routing， so it doesn't know when the path changes。

Then if the gout had changed and now went over the blue path。

A should have changed its rate and started sending it in this case，1 gig per second。

 because that's the bottleneck along the path。So this is already telling us a few pieces of information One is that any solution we come up with has to have this discovery we face because we don't know what the entire topology of the internet looks like。

 we don't know what link capacities are， what the bottleneck is so you kind of have to discover what the capacity on the path to a particular destination is。

And secondly， that it has to be adapted。Because that capacity can change。

 This is a simple example where yoga changed， but there are other reasons why the available capacity can change。

One of those reasons is it's not just the topology that determines the rate at which you send。

 It's also what other flows are in the system。So if I took going back to that example。

 if let's say A is talking to F here。And so as we said before， it could send that， let's say。

2 gig per second。But what happens when B starts talking to Eno。

And what good do you think a should send in this case。One gig seems reasonable。

 One is bes bottleneck。So we can't send any more than1 gig per second。

And they're sharing the link here。And if let's say we want each one to get a fair share。

Then it's reasonable intuitively to say a should be sending at one gig per second gigabit per second at this point。

So competing flows are flows that cross the same link that have a link in common along their path。

It doesn't mean the entire path is the same。 So as you can see here。

 these two flows are only sharing one link。 So theyre only competing on one link。

So a given flow is competing with different。Flow other flows at each link in its path。

If I extended that a little bit now and said that G is a new flow that comes up and wants to send to D。

Now， at what rate do we think it should be ascending。1。

 a should be sending at1 A is only sending to F。 So a should be sending at 1。5。

 How many people think。那s过ラ子。So this is sorry。2 no no you were right with 11。51。5 was a good answer。

 So a should be standing at 1。5 is going to be our argument。

 And why is that Because now the blue and the purple floor are competing on this one gig link。😊。

So each one should get about 0。5 gig of that link。 So what that means is that the purple flow now cannot send at more than 05 gigab per second。

But if the purple flow is standing at 0。5， then why drop the red flow or the pink flow from。

Using up all the remaining capacity。So the pink floor should send at 1。5 gig a second。

Does that make sense， Ru？嗯。So think about what just happened here。 We had a new flow come up。

 the blue flu。That wasn't competing with the pink flow at all。

 at no link was it sharing resources with the pink flow。 And yet， the blue flow coming up。

Didn't actually decrease。 It actually increased the pink flows allocation。

And so what this means is that we don't just have to think about what flows are going to be competing with My flow。

It's really potentially any indirect competitions。 it's really any flow in the network that comes。

 enters or leaves the network can change the allocation that my flow should receive。

And that's in many ways， what makes congestion control such a hard problem。 It's fundamentally。

 what we're talking about here is a resource allocation problem。

That the resource allocation we're talking about here is how much bandwidth or capacity should my flow be assigned on every link along its path。

 What's your share of flus share of the link bandwidth。If you've taken CS162。

 resource allocation should be a very familiar idea to you， you've done CPU scheduling。

 you've done memory allocation， network bandwidth allocation is far more complex than any of those traditional resource allocation problems。

One of the reasons is because of what we just discussed that if you change one flow or one links allocation。

 this can have a ripple effect， a global impact on all the flows in your network。

That's not at all the case with CPU scheduling。 When I assign a job to a CPU on server 1。

 it has zero impact on a job that's running on a different CPU on a different server in my data center。

 I never have to think about。The other is that we're changing these allocations every time a flow enters or leaves the system。

And this happens quite frequently， and it also happens without any control， any central control。

In a data center context， for example， when you do scheduling。

 you know when a job is submitted or when a job needs to be scheduled。

 doesn't just happen without anyone being aware of it on the Internet。 That is the case。 And finally。

 there's no single entity that has a complete view of the topology or of the flows。

 It is no one entity that controls what flows in the network or that even sees all flows in the network。

 So again， it's a little bit going back to the analogy of CPU scheduling。

 It's like telling your OS scheduler you have to schedule jobs you don't know about。

 It would just sound absurd。So scheduling and CPU scheduling， you have a queue。

 Jobs arrive at the queue and they get scheduled by a scheduler。

 There's no ambiguity about what you're scheduling。But in network congestion。

 that's not a luxury we have。 The one exception I would point out is within a data center that within a data center。

 the data center operator controls what jobs are running。 And so implicitly。

 they also know what flows are going to be generated when you launch a job。

 like a map produce use or spark job。 You have a pretty good idea what flows you're going to expect to see when you launch that job。

And this is something that folks in the data center will exploit to some degree。

 not as much as they could， I think。So trying to summarize all that is that allocations in our context are highly interdependent and also not under any kind of centralized or global control and this is kind of the cuux of what makes congestion control so hard。



![](img/11018edd8a792c462a618f6dca42f598_15.png)

So with that， let's move into any questions on that before we move on。Okay， so let's start designing。

 so as always， you know before we design， we ask ourselves what the goals are。

 what do you think should be good goals for a congestion control solution。哎不。

Optimal bandwidth utilization。What else？嗯。Because to be practical in in an Internet context。

 distributed anything else。If all we care about was high link utilization。

We would just blast traffic into the network grid。 Every link would be perfectly utilized。

Why do we not do that。Fairness， we want fair sharing。

 That's what we were doing when we were adjusting all the flows there。

 We were saying everyone needs to get some fair capacity。我。Y。Like performance。

 we want low delay and low loss。 That is the trade off with utilization。

 The reason we don't have 100 percent utilization is because we would end up with high delay or high loss。

So from a resource allocation perspective， and what I mean by that is if you're viewing this as a resource allocation problem and you're looking at the output or the allocations you've been given。

 how do we decide if those are good allocations is if we have low packet delay in loss。

 highlink utilization and some notion of fair sharing。Between the flows。

 Not this is not saying anything about the solution itself， like properties of the solution。

 It as the properties of the allocation that I'm being given。

If these are the goals we would like to achieve。 And as I mentioned earlier。

 we know we can't get all of them。You perfectf utilization and zero delay。 That's just not possible。

 And so we're really looking for a good trade off between these goals。from a systems perspective。

 So now when we talk about， the nature of the solution we are designing things we want。

 as someone pointed out， we want it to be practical， which means it has to be scalable。

 decentralized， adaptive， all of the things that come with the Internet and environment。

Any questions on those good。 so let's go into the design space of possible approaches。

 And I'm going to just walk through a few， you know。

 just to kind of check them off and then we'll dig a little deeper on the direction path we're going to go down。

 So the first approach， which is not an approach， but I just want to reiterate。

 So it's clear to everyone is you just don't have congestion control you send as much traffic as you want。

 And in this example over here if we said a sending to F and the bottleneck link is one gig And a just sends traffic at 10 gigs per second。

9 gig would get dropped。But weve said TCP is reliable reliableable。 TCP will recover。

 So it will get one gig worth of good。Data 2。And it would be reliable。 So from As perspective。

 this actually might be a fine solution。 The reason we don't like it is we've just wasted 9 GB per second of bandwidth on all the other links。

 the links other than the bottleneck。So this is。Cllausible from one sender's viewpoint。

 but it's a non starter end。This kind of solution we're looking for， because you're not。

Making very good use of your bandwidth in this case。

The other approach one might come up with is our old friend of reservations。

 so we talked the earlier lectures about when I start a flow。

 I'm going to send this reservation request through the network。

 I'm going to reserve bandwidth at every routeer。Clearly， if I'm doing reservations。

 I'm not going to have congestion because I only use my reservation。 And if the network is full。

 your reservation would be declined。And so we never overloaded the network。

This would have solved congestion control and indeed when there was congestion collapse on the internet。

 there were immediately a bunch of proposals from people who said I told you we needed to have reservations。

 It's now time to roll out reservations so this is why Van was not popular with the folks that wanted to do reservations for a while so it would have been a solution to the problem for all the reasons we've discussed in the past this is not what the internet could does other than as we've discussed for certain private users ISPs will go and provision reserve bandwidth。

The second mooc other approach that comes out is to rely on pricing or priorities。

 This is really the solution that if you ask an economist。

This is what they think is the right solution kind of the systems approach that we've taken with congestion control makes no sense to them and the argument is actually a fairly reasonable one。

 Their argument is if you think of network bandwidth and it's a scarce commodity。

 then the way we deal with scarce commodities in the real world is through a pricing structure around them。

That when something is scarce， you raise the price， demand goes down。

 And so you get these market factors where demand and pricing。

A in this nice loop where you avoid overloading or you avoid you deal with the scarcity in a resource。

 And so that would be and one can actually prove that that is in many ways the optimal solution。

 So this notion of exploiting pricing or priority takes a few different forms。

 the one one more practical or easy to realize solution is to say you have certain customers that are higher priority they pay more。

 And so you prioritize their traffic。 So when the network is overloaded。

 high priority traffic goes through and low priority does not。

This is a reasonable approach it is deployed in certain contexts like in data centers or ISP backbones where you have high priorityote traffic。

 there is some notion of coote on the internet。 The other approach that this is the one that folks will argue is optimal is that you should charge users based on cognitive congestion levels。

So think of this as you're watching Netflix and you're getting really bad performance。

 and you had a boost。Button on your Netflix viewer。 And when you press it。

 you get charged a little bit more。For， let's say one hour。

So that's kind of the mental picture of how we as users would pay more for during times of congestion。

What do people think is this a reasonable idea？I'm getting a lot of。Head shaking。

So this is when I have to confess when I first heard this line of work about 10，15 years ago。

 this sounded you know absurd， like cute， but I was never going to be deployed。

 It looks less ridiculous over the years。 And part of it is if you think about it。

 Use are more used to the idea of congestion pricing in the real world these days。

 there many cities notably London， for example， where congestion pricing for traffic is the norm。

 So if you drive through downtown London at rush hour。

 there are certain streets where you have to pay more to drive down those streets。

If you drive down 880 these days， there is congestion pricing on the fast track lane。

 the amount you pay to be on the fast track lane depends in real time on the traffic on that lane。

So we as users are kind of getting used to congestion pricing。

But the other reason it seems less ridiculous is that there is now an ecosystem of micropay and digital currency。

Which makes this， again， more plausible。Otherwise， this idea that you're going to be。

In final granularity for bandwidth on a hourly basis would have seemed much。And still。

 to some degree seems much less realistic anyway， so this is kind of the method of choice if you take an economic view of congestion。

 not clearly deployed that much。 the congestion pricing is not deployed at all as far as I know not yet on the Internet。

 The main drawback with these is it requires a business model and a payment model that didn't exist on the Internet back in the day and even today doesn't a business model that backs this up doesn't quite exist other than in data center context。

So the third approach， which is， you know， what we were working towards。

 is just this notion of dynamic adjustment。 It's the idea that hosts are going to dynamically learn the current level of congestion in the network。

And they're going to adjust their sending it accordingly。Okay。

That's implicitly what we were doing when we were all of us staring at that graph and saying how much a should send。

The many options for how to implement this basic idea we'll get to them in a minute。

In practice what dynamic adjustment has won， it is how all congestion control solutions work。

 And it's one， I would say， and it' reason we like it is the generality of this approach。

 It doesn't presume a business model。 It doesn't assume that we know application requirements or user priorities or user preferences。

 It just carries the least baggage with it， in some sense。What it does assume， though。

 is a notion of good citizenship。 What do I mean by this is in that example， we said， you know。

 A is going to adjust its grade to one gig and then a is going to adjust its grade to 1。5。

 And these two flows are sharing the link。 And so each one is going to get 0。5。

This is assuming that senders are going to do the right thing， and cut their weight。咩。

So they're actually going to share。 this is why to economists。

 this solution makes no sense because there is， sadly。

 very few real world examples where users do the altruistic thing in sharing。Where you say， no no。

 know I'm going to take my salary and divide it equally across the company。

 that's just not how the work world works。 And so while this seems absurd。

 this is actually how the Internet works。 And to this day the Internet is relying on the fact that we don't have too many malicious actors When we get to advanced congestion control。

 we'll talk a little bit about why this state of the world has kind of survived and it does's okay。

For the most part， and why it might change as well going forward。 so with that。

 let's dig a little bit。 the path we're going to go down is designing a dynamic adjustment scheme。

 yeah。

![](img/11018edd8a792c462a618f6dca42f598_17.png)

Yeah， so the question it's a great question the question is why can routers enforce a correct share for we're going to talk about this a little bit when we talk about fakequeuing and router assisted congestion control。

 it's actually a pretty hard problem。😊，Because for one router to know what is the correct trail of a flow？

It doesn't actually have all the information it needs to know that， because， for example。

 let's say one flow is getting very consuming very little bandwidth or at that router。

 It could be that the reason for that is that that flow is the sender is on some really bad connection and has very limited access bandwidth And so it actually cannot consume more。

 But a router deep in the network doesn't know that。 So what looks like unfairness to that router。

Is actually not correct。 It could give it far more bandwidth。

 but that source would not be able to exploit it。 So it's clearly knowing exactly what the right share is。

Is each routeer doesn't have the full picture。 The other reason is it's actually。

 and this might be changing over time。 It's computationally quite expensive for routeer to do those calculations。

 route is， if you remember what we talked about， they just do IP lookups update check send packets and they have their hands full just doing that。

 So asking them to track how many flows。 What is their share。

 What is the corrector is actually nontrivi for routeer。But it's， it's a great idea thought。

 And we'll come back to it when we do more advanced topics。Any other questions？Okay。

 so let's dig into dynamic adjustment。 What do I mean by that first。

 And I'm going to go through this fairly quickly because I think I hope we all have a pretty good picture at this point。

 So what I mean by that is let's say we had that example where A was talking to E。 So step1。

 the hostier would have to somehow discover that it can send a 10 gig。When the route changes。

 it doesn't know that the route change。 But what it should be able to detect is that the rate it was sending at。

 which was10 gig is now congeesting the network。And then it should be able to somehow discover that it should cut its rate to some lower。

Late of 1 gig per second。When another floor joins the network。

What a should discover is now that even 1 GB per second is congeesting the network。

And then a finally should say that it somehow discover that ideally。

 it should cut its rate to half a gigabit per second。So that's what we want to have happen。

 how we're going to make it happen。 we haven't gotten into that yet。



![](img/11018edd8a792c462a618f6dca42f598_19.png)

How do you think we could make it happen？how could A know that information it needed at each of those steps。

 There's kind of two broad classes of solutions。Yeah。Number of packet drops it could observe。

 the host could observe the performance itself。So I'm going to call that host based。

Congestion control， where the host is looking at the performance it's getting and adapting。

That name gives away the other。The great acknowledgeknowments。

 I would lump that into the same category。 It's looking at what performance I'm getting。

And so the other class of solutions is what we call a routeer assisted congestion control。

 whether the routeer is going to help the host figure out whether it's congested or not。

 And so those are the two kind of broad classes of solutions。 The host based congestion control。

 there's no special support from goers。 they're completely oblivious or they don't communicate any feedback back。

To the host。The host and adjust their based on what I'm calling implicit feedback from routeers and implicit in the sense that you do have a sense of whether your network is congested based on the as you're getting back know are you losing packets。

 What is the delay of your packets because remember we're doing round trip time estimation if you see your round trip time go up that's a pretty good indicator that you're experiencing congestion So this is kind of implicit feedback from the network or from the routers。

Rooututer assisted congestion control is an approach in which the routers are going to explicitly signal congestion back to host。

And so it's an explicit signal in that you think of it as a packet as going through the network。

 A router is going to put something in the header。That is then going to be returned back to the host。

 And that information in the header is going to tell the host something about congestion。

What that signal could be can vary from something very co screen。

 like a single bit that just says I was congested。All the way to something much more advanced where the router tells the host。

 this is the rate you should send that。 I'm actually going to calculate your fair。

So Valja Ebson's original TCP approach is a host based solution。

 we are going to study a host based approach in detail。

 we are going to adjust do a little bit of how assisted congestion control。



![](img/11018edd8a792c462a618f6dca42f598_21.png)

So just to give you a view of where we are in the design space。

 we've talked about you could do reservations pricing， dynamic adjustment going down that path。

 we've gotten to host based and goto based and the path we're going to actually focus on is this particular one。

Yeah。So the question is whether having the goouers send feedback。Actually， adds to the network。

 So the way this is typically implemented is you don't send extra traffic or signals back to the host。

 You set a bit in the header。And so when the acknowledgement comes back to you。

 that information is reflected back to the center。And we'll do a little bit of this when we do route assisted congestion control。

 So let's start to build out what that solution should look like。

Asumm I hope you have a fairly clear idea in your head already about what this is going to do。

 But let's actually work， work it out。 So each source is going to independently run the following。

 And the independently is important here。 That's what makes it practical。

 And that's what makes it scalable。 There's no coordination of host at all。

 And there's no coordination with the network either。So independently。

 what each source is going to do is it's going to try sending at some rate R。

Into the network for some period of time。At the end of that period of time， it's going to ask。

 did I experience congestion during this last period。If it did。

 then it's going to reduce its rate in the next iteg。

 but didnt it's going to increase its rate in the next it。And it's going to repeat。

So this is a very basic dynamic adjustment。The one thing that's missing here is what is the initial You need to start at some initial radar。

 How do you pick this。And so those are kind of the three components of our solution。

 How do we pick this initial rate。

![](img/11018edd8a792c462a618f6dca42f598_23.png)

How do we detect congestion and then how do we adjust to congestion。

 What are these increased decrease wounds。

![](img/11018edd8a792c462a618f6dca42f598_25.png)

So components of a solution discovering that rate， detecting congestion and reacting to congestion。

Any questions on the components。So detecting congestion。

 how do we detect  one we talked about was packet loss that this was already in place in TCP。

 This is the approach commonly used by TCP。 What is nice about loss as a signal。Instead of。Yeah。

 so in a way， it's a faila signal。 when most cases。

 with one exception that or few exceptions I we'll get to。If you dropped a packet。

 that's a pretty unambiguous signal that there's a router along your path that's congested。

There's not much ambiguity about it， so that's great。In addition。

 had the site implementation or engineering benefit that was already something。

 The mechanisms for detecting loss were already in TCP So why not exploit it。The cons， any thoughts。

 wise loss not a good signal。要。Yeah， let me your your argument that it came at some price to the host。

 I would agree with that。 That price I would have said is delay。Because you。

 you suffer delay before you suffer loss。 And so you've already incurred delay in your sending the other observation。

 which you have to have sent a certain number of packets and incurred some loss。Before you。

 you actually discovered。What that congestion level was。Any others。有。Yeah， actually。

 that's a good point。 It's， it's a very binary signal。 You， you lost a packet。

 It's not telling you exactly at what rate you should send。

 though the congestion control algorithm is going to learn that around loss， but yes。

The other complication， which， you know， in a way， we've not quite covered is you could sometimes have loss for reasons other than congestion。

 one of them being check some errors。If your packet arrive I。

 you drop it because there was a checkum。 this is gay enough that people weren't concerned about this。

 that this is not a common cause for loss。 Congestion is a much more common loss with one exception。

 which is wireless links。 So wireless links you were sending packets and someone turned on a microwave too close to your tower and there was interference on the signal and you the packet was corrupt and you lost the packet。

 So this is actually quite common in wireless links and wireless links will not use they do additional mechanisms to mask those errors。

 But so that's one reason why we don't like loss。s because sometimes loss is not a signal of congestion。

 It's a signal of。It happens due to interferenceference， or other reasons。

The other complication and this is very TCP specific is that loss is can get confused with reordering。

 So if you remember the way TCP the liability works， TCP uses cumulative acknowledgecments。

 And so let's say that all your packets up to packet 5 had been received at the receiver。

 And so the receiver is sending acknowledgements saying I'm expecting number 6。

 and now you had send packets number 6，7 and 8， but the network reordered them。

So they arrive at the receiver in the order 8，7，6。This is a very silly TCP thing。 but TCP will。

 when it receives 8 will say I'm waiting for 6。 It's a duplicate Act。 when it receives 7。

 will' say I'm waiting for 6。 Another duplicate Act。

 And if you remember what TCP will liability does is it says if I get a certain number of duplicate acts。

That's a loss。 I'm going to assume that that's a loss because at the TCP layer， not the network。

 TCP is assuming there's not that that much ordering。

And so sometimes if you have a lot of reordering in your network。

 the sender will get confused that there was packet loss and it'll slow its rate。

 even though the reason you were getting those duplicate acts was reordering and not actually loss。

 This is one of those examples of where bad design decision can have ramifications that are very painful because when we design the network or the IP layer。

 we were fine with reordering And then TCP made this decision about cumulative acts and treating multiple duplicate acts as a sign of loss And because of that now network operators try very hard not to reorder packets because they know that if they reorder packets。

 congestion control at the TCP layer gets confused and will slow its rate and then users are not happy。

And so network designers are now kind of artificially constrained to not being able to reor packets。

Where this has never really troubled people because there's something natural if you're sending all your data on one part。

 it's quite natural that you don't be order packets。

 So reordering was pretty rare until we got to data centers， where data centers as we study。

 have lots of parallel parts。 and so operators would like to be able to load balance traffic across all those path。

The minute you load balance， you get reordering。 the minute you get reordering， TCP gets unhappy。

 And so data center operators are now thinking about ways to actually fix this。 But anyway。

 long story short， sometimes these design decisions。

With there's no end to thinking about them deep enough or hard enough because they have these implications。

So that's another downside to loss。 Is that sometimes T CB gets confused between loss and reordering。

And the last one， which somebody touched upon is that loss follows delay。

 So you've already suffered delay by the time you'll see a packet loss。This， again。

 the early days was considered fine in the context of data center applications in modern internet services where we care about low latency。

 So if you think about selfr cars， this idea of incurring delay is not something that's very pleasant to people thinking about self driving cars and realtime automation and so on。

Okay， so any other ideas to how we could detect congestion， if not loss。And remember。

 we are a host based。U， what else could the host be looking at。Long trip time。 So delay。

So as a sender， I could be looking at the ground trip time I'mestimating。 and if I see an increase。

 I could say， aha， I'd suspect that's congestion。For a long time。

 the idea of using delay in congestion control is a very old one。

 even Van Jacobson's paper in the 80s talked about potentially using delay。

It was often dismissed because it was considered too tricky to get right。

 You have to get good delay samples。 You have to say I'm getting an increase in delay。

 but an increase relative to what right， you have to have a pretty good idea of what your normal。

 uncontrasted delay is like。 And then also， delay was considered a noisy signal because you accumulate delay along the way。

 Any。Note along the path can add a little bit of delay。

 And then it looks like you have a lot of delay， even though there wasn't really bad congestion。

 So for these reasons， for the longest time， people thought delay would be an interesting signal to exploit because it's an earlier signal than loss。

But kind of hard to get right because you need to have a lot of delay measurements to get a good。

 accurate indicator of when delay causes congestion。

This has changed quite recently because Google's new BR protocol is based on delay。

And their starting observation， they were doing this in the context of YouTube。

 Their starting observation was that they get a lot of data samples。

 a lot of long tripp time samples because if you're the YouTube server。

 you're sending out so many packets to so many clients all over the Internet that they have a wealth of delay readings that they can build off of。

 And so they've shown that actually delay as a congestion signal works pretty well。

 This is still a little debated。 This is what BBO does。

 There's a fair amount of research showing that there are certain pitfalls to this。

 And so I' would say it's new， but certainly a very convincing proof point that you can do delaybased congestion control。

We might touch on BR very briefly next week， but for now we're going to stay in the dream of losses。

 the other observation I wanted to make on losses is that not all losses are the same as we've discussed in the context of TCP liability。

 we detect losses one of two ways。 One is when we get a certain number of duplicate acknowledgements。

 This is kind of an indicator of it's an isolated loss the fact that I'm getting duplicate acknowledgeledments means my packets are still going through。

So it probably means that there's a mild congestion， but it's not severe。

The other way we detected loss was through timeouts。

And so timeouts are pretty good indication of severe congestion because you sent a whole bunch of packets and you got no duplicate acknowledgements。

 So your packets didn't make it through you。Now either your packets can make it through or your acknowledgeknowments are not making it through。

 but whatever the case， you're getting a fair amount of loss。

 And so this must be pretty severe congestion。And so when we get into T CPPF for now。

 I just want you to file this away that we have， you know， not all losses are the same。

 We distinguish between。A little bit of loss versus fairly severe loss。

 And TCP will react differently in those two cases。 So we'll cover this when we cover TCP。



![](img/11018edd8a792c462a618f6dca42f598_27.png)

So taking stock again， where we are in our design space， we've expanded the host based。

 and we're going to focus on loss based， host based dynamic adjustment， congestion control。

 so with that。Where we we had our three design steps， One was detecting congestion。

 which we've now decided we're going to look at doing so with loss， discovering an initial rate。

 which we'll do now。 And then what are your increased decreased goals。

 So discovering an initial rate is fairly easy。 The goal is to estimate what is the available bandwidth on this path。

For this flow， when it starts up， what is a reasonable estimate of the available bandwidth。You。

 the way we're going to want to do it is to start slow right because we don't want to conge the network。

 So we want to be fairly conservative。 So for safety reasons。

 we're going to start by sending a small amount。On that path。 But we want to ramp up quickly。

 because if it takes too long to discover how much capacity you have the available bandwidth。

 then you're just wasting time and wasting that bandwidth。What do I mean by that？

 So let's take an example。 Let's say what would happen， you know， starting small。

Fly easy to understand， to speak a value that's not unlikely to congest any path and start with that。

Vamping up quickly， you know， here's an example of what if we did a linear increase where we said I'm going to add half a megabit per second every 100 milliseconds。

Until we detect laws。The problem with this is if your available bandwidth is say1 mebit per second。

s you're going to discover your weight in 200 milliseconds， two gus， that's fine。

 But if your available bandwidth was1 gig per second， it would have taken you 200 seconds。

To discover that you could be sending at a gigabit the second。And on the Internet。

 any of these could be equally possible。So something。

 this is just an example to show you that linear increase would be way too slow for what we want to do。

 because the range of possible available bandwidth is too large。



![](img/11018edd8a792c462a618f6dca42f598_29.png)

So the solution we work with in TCP is something that's。Very poorly named， It's called Slow Start。

The reason it's called slow start is because you start with a small rate。

 I think small start would have been a better name。So you start with a low value。Which would be much。

 much less than the actual bandwidth。But then because linear increase takes too long to ramp up。

 slowlow start is actually going to do。Go exponentially first。So what that means is， for example。

 it's going to double the gate。Until you experiences loss。

 So let's say that you had a source that decides to start at 00 Mbit per second。

 So it's going to send it 100 mi for a while。 and then it's going to send it 200。

 if there's no congestion， then 400， then 800。And then let's say at 800 MB per second。

 there was no loss。 So you're fine。 So now it's going to send at 1。6 GB per second。And then at 1。

6 gigab per second， it experiences loss。So what the center has learnedt at this point is that a safe rate was 800 megabits per second。

Does this make sense to people？So slow start means you start small and you scale up exponentially。



![](img/11018edd8a792c462a618f6dca42f598_31.png)

![](img/11018edd8a792c462a618f6dca42f598_32.png)

Any questions for that？So the last question is this question of by how much should we increase or decrease when we have congestion？

 So this is the great adjustment phase of congestion control。

 This is probably the most critical part part of the solutions we've developed so far because how quickly you adapt and how much you adapt by is going to determine how a host adapts to changes in the available bandwidth if you're too slow to adapt。

 you're going to be very inefficient in consuming bandwidth。



![](img/11018edd8a792c462a618f6dca42f598_34.png)

And if you're too。Slow as well to adapt。 It also determines how bandwidth is shared in terms of fairness。

So think about this as I had a link。 It was one gigabit the second。

There was one flow consuming that link。 It had the entire gigabit per second。

 And now another flow joins on that link。If I'm going to be very slow to adjust。

 then it's going to take a very long time for this new flow to get its half gigabit per second。

So how quickly you adjust impacts Venness， It also impacts how if it。Efficiently。

 you're using your link。 Let's say you started out at 100 me and you were not。

 your capacity was one gig and you were adjusting very slowly。

 You probably gonna't take way too long to fill that link。

So we want a good set of increase and decrease goals in order to balance these two goals。

 We want efficiency。

![](img/11018edd8a792c462a618f6dca42f598_36.png)

High utilization of the link bandwidth。 And we want fairness， which is how each。

The share of the link that each flow is getting。So how should we adjusted it。

 there no you could imagine any options， you know something is quadratic or the cube root of some loss。

 whatever we wanted to come up with at a high level， this gal do you increase faster。

 do you increase slow。And the two canonical approaches are either you increase or decrease multiplicatively。

Which means， you know， you increase or decrease by let's say2 x or 3 x。 So whatever my rate was now。

 I'm going to double it in the next database。Or I'm going to cut it by half in the next situation。

 Or a slow increase or decrease would be to add or add or remove a constant amount。So I add。

 for example， you know， plus one to migrate or I remove plus one for my rate。



![](img/11018edd8a792c462a618f6dca42f598_38.png)

So this gives us four design options based on how you're increasing or decreasing。

 So AI AD's additive increase， additive decrease means you increase additively。

 you decrease additively。 So a little bit you increase slowly， you decrease slowly。

AI M D is additive increase， so I increase slowly。But， I decrease very rapidly。MIad is the opposite。

 I increase very aggressively， and I decrease slowly。And MI IMD is。

 I both increase and decrease very rapidly。Which do you think is the right of approach just intuitively。

好的。The last one。I'm going to tell you that the answer is the second one。 AIM D。

 that you increase gently and you decrease rapidly。 And we'll talk about why the intuition is that。

 you know， if you。

![](img/11018edd8a792c462a618f6dca42f598_40.png)

Kind of getting it wrong and sending too much is usually worse than sending too little because if you send too much。

 you cange a network， you get lost and you get delete。 if you send too little。

 you're just getting somewhat lower throughput。And so the general approach that we take is that we do a gentle increase when you're uncongested。

 So it's gently exploring。 but when you hit congestion， you cut down very quickly。

So that's additive increase。 I increase slowly。Multipplicationicative degrees。

 which has I dropped very quickly。

![](img/11018edd8a792c462a618f6dca42f598_42.png)

The most of the rest of this lecture is going to be going into this Y AIMD in more detail so the way we like to explain this is through a very simple model that I think captures this intuition really nicely。

 which is let's say we have two flows that are going over a single link of capacity C。

And the share of each flow is x1 and x2 respectively。

 So we're going to use x 1 and x 2 to denote the share that flow 1 and flow 2 are getting。

What did we say we want here， We're saying that when x1 plus x2 is greater than C。

 then the network is congested。If X1 plus x2 is less in seat， then the network is underloaded。

 so we could be increasing。And what we would like is both that x1 plus x2 is equal to c。

 So were fully at capacity。And that x1 is equal to x2。

 which means we're sharing fairly between the two flows。That's in an idealized world。

 that's our goal。

![](img/11018edd8a792c462a618f6dca42f598_44.png)

So let's look at what this looks graphically。 know， with a simple model where we say capacity is one。

 What I'm showing you here is the weight that each user has。 So x1 and x2 on the Y axis。

And so two users us with grades x1 then x2。 We say that you're congested if x1 plus x 2 is greater than1。

So what is and you have unused capacity or you're underloaded when x1 plus x2 is less than1。

So on this graph， if you look at the line， you know where is the line where x1 plus x2 is equal to1？

That's this blue line that we have here。We call this the efficiency line。

If you're at any point on this line。We have perfect efficiency。

 We are completely using the capacity of the link。Does that make sense？If you're above it。

 you're congested， if you're below it， you're underloaded。And then we have a fairness line。

 We say that we study your fail if x1 is equal to x 2 on this graph， that's the green line here。

That's the line of x1 is equal to x2。 So really where we want to be operating is at the intersection of those two lines。

 That's why efficiency meets fairness。

![](img/11018edd8a792c462a618f6dca42f598_46.png)

And that's a good。So let's look at a few just example allocations。

 if I said we had an allocation of x1 and x2 is 02 and。5。We are underutilized， right。

 This is inefficient use of the network。If we at X1 plus x is 1。2， we are congested。

 We are overloading the network。If we were at this point here with 07 and 。3。

 we are actually perfectly efficient， but we're not fair。That they don't have an equal share。

 And so really， the only place where you get both again is when x1 and x2 are both。5。

So that's going to be our goal。we're gonna walk through all of the different four different design options here。

 but let's just recap this。 Im not trying to be patronizing。

 but I know that I sometimes have to rethink how I calculate the slope of a line。

 So I'm just going remind you if we have a point x1 x2 over here。

 And I say that I'm adding or subtracting some amount from x1 and x 2。

 So I'm going from x1 x2 to x1 minus a and x2 minus a or adding B to both x 1 and x2。

 What I'm doing is I'm moving along a line that has a slope of1。Okay。

 so adding the moving a constant to x1 and x2 all I'm doing is moving along a line that has a slope of1。

 If I said I'm you know multiplying x1 and x2 by some factor or dividing x1 and x2 by some factor。

 then I'm going moving along a line that has a slope that you can achieve by drawing。

 connecting x1 x2 to the origin。Okay。So think back to additive increase decrease， yeah。

Do you necessarily have to affect both equally in practice， Yes。

 Because think about how would we decide how much you get to increase， you know。

 which horse get to increase by different amounts。 That would be a slippery slope to go down。

 It would probably wouldn't be fair。And certainly in this idealelized model， we' are assuming that。

Okay， so in this case， were moving along a line that has a slope of x2 over x1。



![](img/11018edd8a792c462a618f6dca42f598_48.png)

Right， that was just the reminders and slopes。 So we're going to take these four different algorithms and see how they far in terms of efficiency and fairness。



![](img/11018edd8a792c462a618f6dca42f598_50.png)

Okay， so a simple model， let's start with AI A D。 So that's additive increase， additive decrease。

 Let's start with a very simple example。 We are going to say， we are going to increase by one。

 decrease by2。We had a simple example why we start with x1 equal to1 and x to equal to 3。

 And let's say that the capacity of the link was 5。So in the first iteration。

 there's no congestion rate because one plus3 is 4， less than5。 I'm not congested。

 So both of them are going to increase。So we now go to 2 and 4。At this point， we all congested。

So in the second integration， were going to decrease。 Theyre each of them is going to decrease by 2。

So x 1 is now0。 x2 is 2。Were underutilized。 So in the next situation， there's no congestion。

 We're going to increase。 So we're going to have x 1 equal to 1。 X 2 is equal to 3。

 everyone's good with this。行。The thing to notice is we've not improved fairness at all。

 The gap we had between x 1 and x 2。Has stayed the same throughout。From a efficiency perspective。

 you could say we're doing the right thing， right， You're never going to land exactly at the efficiency point。

 So sometimes you're going over， then you're going under， then you're going over。

 then you're going under。 You're oscillating around。Full capacity。 And that's fine。

But you're oscillating around without improving fairness at all。 And that's not okay。

What that looks like in graph here is that if you started with X 1 x2 and you're doing AI D。

 when you decrease， you move down along a line that has a slope of one。 When you increase。

 you're going back up along the same line with a slope of one。

 So you're never moving your operating point towards the fairness line。



![](img/11018edd8a792c462a618f6dca42f598_52.png)

Does that make sense to everyone？So it doesn't converge to fairness。

If we do the same kind of example with MI I MD， and I'm going to do it fairly fast。

 but stop me if you have any questions。Right if we said now M I MD， I'm going to increase。

 let's say in this example，2 x。And I'm going to decrease by dividing by， let's say 4。

And if I start with a rate where x1 is half and x2 is 1， and my capacity is 5。

 and let's walk through that again in the first iteration， no congestion rate。

 one and a half is way less than 5。 So they're both going to multiplicatively increase。

 multiply by  two。 you get x1 is1， x2 is 2。So one plus2 three， less than 5， we still not congested。

 So in the next it， we multiplicatively increase again。 So now we get 2 and4。2 plus 46。

 we are congested， so now we need to drop。So we're x1 has half， x2 has1。And you could continue on。

Same as before， we are oscillating around congesesting and not congeesting。

 congeesting and not congesesting， which is good。 That's what we want to do for efficiency。

But we're not again， reducing the gap in fairness between x1 and X 2。



![](img/11018edd8a792c462a618f6dca42f598_54.png)

Makes sense。Going back to our picture of why that is。

 we're just moving along the line that has a slope。Of x to over x 1。But again。

 we're never moving that line closer to fairness。Again， doesn't converge to Fness。

 I want you to do MI I A D。啊。Play with it and see what happens。

Let's say I'm going to make it easy and give you an example。Take2 minutes。哦，怪是你。Those closed start。

Because when you're bursty and as you increase the load。

 and this is actually like an MM M1 queue with persona arrivals。

 So the model it has is of infinite buffal queue。And so U delaylogy just keeps going。

Because once you're bursty， you you kind of as you go to high load and you have bursts。

 you fill the queue and then you never have a chance to drain it。When you're at high load。

 so every bus just keeps adding to the kid。ACon therapistorist would clingjure that explanation， but。

喂，我就。Tos， how does在 my a feel。What did you find。Less fair， exactly any。How how unfair。Yeah。

 so let's walk through an example here。 So in the first irigation， we had X1 and x to1 and 3。

 There was no congestion， so they both multiplicatively increased to 8。6 plus 2。

 So second integration we have congestion， theyll cut down。 Third it， cut down again。 Four iteg。

 No congestion go up。 Now， look at what has happened here。 X1 is at 0， and x 2 at 8。

And so you could keep working through any of these examples that you take different values。

 different numbers of steps。 where you will end up is always that one of the flows gets  zero allocation。

 And so M AD is actually maximally unfair。 And if you look at it in terms of the graph。

 what you'll see is it moves along a direction that will take you to either the x or the Y axis。

So play with it on your own。 But what you should always find is that one of the flows gets 0 and the other one gets all the capacity。

 So MI I A is the worst of all these options。 Let's walk to what AI M D does。

 So let's consider here that you had an increase of one and a decrease of two。



![](img/11018edd8a792c462a618f6dca42f598_56.png)

And if we start again with the same example， x1 is1 x2s 2， you have a capacity of 5。

 I'm not going to actually step through all of these， but you can do it offline。

 calculate the x1s and x2s you end up with each time what you're going to find if you look at as you go forward and you look at the difference between x1 and x2 we started out with x1 being half or1 off from x2 and as you continue to proceed。

 you're going to see that the difference drops。

![](img/11018edd8a792c462a618f6dca42f598_58.png)

Overtime。So just like the other schemes， we are oscillating above and below the efficiency line。

 But now the gap between x1 and x2 is shrinking， they're getting closer to fairness。

 And so the difference between x1 and x2 decreases， it stays constant when you're increasing。

 but every time you decrease， the difference hubs。And this is very clear when we look at the picture。

 because what's happening now is when you decrease。

 you move along that line that had a slope of x2 over x1。But now， when you increase。

You're increasing along a line that has a slope of one。So you're shrinking the gap。

To the fairness line by this angle over here。And as you continue to decrease and increase。

 what we start seeing is that you're moving x1 and x2 towards that point。啊。

And so AIMD is the only one of these options that we can show converges to fairness。

Any questions on this。

![](img/11018edd8a792c462a618f6dca42f598_60.png)

So the answer to why AIMD it embodies this sort of gentle increase rapid decrease philosophy。

 and it's the only choice that's going to drive us to get both fairness and efficiency。 Now。

 the example that we walked through with this model is it's kind of a toy model in the sense that only two flows。

 they're both reacting in lockstep， but the general intuition holds for why AIMD is a right solution。

Okay，So out of the four options， AI A D and MI I M D retain unfairness。 They don't improve it。

 MI I A D makes it worse。 It's maximally unfair， and AI MD achieves both of them。



![](img/11018edd8a792c462a618f6dca42f598_62.png)

Any questions on that？So with that， we now have a。Fairly good sketch of a solution。 right。

 We said that each source is going to independently run this algorithm here。

 where you pick an initial rate， try sending at that rate。 Check if you had congestion。

 and then adjust。RightWhat we now know， and this is a sketch of TCP's solution is that the way in which you pick that initial rate is based on slow start。

And you pick a small value and you exponentially increase it until you see loss。

And we also know that the way you decide whether you experience congestion is whether you had loss during that time interval。

And we now know that the way you reduce your weight is you multiplicatively decrease by some factor in TCP's implementation。

 that's 2 x。And if there's no congestion， you increase your weight additively。AIMD。 So in TCP again。

 that's plus one。Yeah。Plus one M S per ground trip time。

 which we'll do when we get to the details of TCP。Any questions on this basic approach。



![](img/11018edd8a792c462a618f6dca42f598_64.png)

Okay， and so if you play that out one of the things you'll hear when people talk about TCP and the throughput you know you expect to see when you get TCP。

 so a fun ways to actually run an experiment， open a TCP connection and look at the throughput you're getting you should see something that looks people will say TCP has a sore tooth behavior and what that tends to mean is that if you look at over time what is the weight or throughput that you're getting from your TCP connection you'll get a graph that looks like this where the initial phase is the exponential slow start So you're exponentially increasing your weight。

Until you have a drop。At which point you multiplicatively decrease your weight。

 So you get this9 coming down。And then finally， you increase your weight additively。

So you're linearly increasing your heat until you get another loss event when you cut down again multiplicatively and then increase linearly and drop。

So you get what people call a so tooth。Looking go。Any questions。



![](img/11018edd8a792c462a618f6dca42f598_66.png)

So with that， next time， details of TCP。Congestion control is really pretty much what we've talked about。

 but we're going to step through it in a fair amount of detail。

 The few key differences is that TCP doesn't think in terms of rates with things in terms of windows so are you increasing your window or reducing your window。

And it's going to do everything we said that I'm， I'm going to try sending at this rate and decide whether I have congestion or not。

 The time scale for that is going to be a long trip time。So every round trip time。

 you're going to try and adjust your window， either double it or hve it or increase by one and so on。

And we're going get into certain details。 like TCP has different reactions for loss based because of timeouts versus duplicate acts。

And TP does reuse closed style。 So it's not just at the beginning of a connection。

 And we'll get into that as well。With that any questions？I think I'm done for the day then。

 Thank you。Yeah。

![](img/11018edd8a792c462a618f6dca42f598_68.png)

I thank。

![](img/11018edd8a792c462a618f6dca42f598_70.png)