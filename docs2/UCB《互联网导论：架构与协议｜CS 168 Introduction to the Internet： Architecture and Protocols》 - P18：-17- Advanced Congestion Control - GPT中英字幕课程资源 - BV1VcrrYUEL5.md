# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P18：-17- Advanced Congestion Control - GPT中英字幕课程资源 - BV1VcrrYUEL5

![](img/146bf0454029d3cf36fb91fdc7713fe5_0.png)

Good morning， everyone。 Let's start。 Today， we are releasing Project2。

 and Tenzan is here to introduce it。Hi， so Project 2 is going to be about transport。

 so you're going to implement the core parts of a TPCP socket using a network simulator developed by Murphy。

 This network simulator is going to be different from the project one so is this is like apox simulator POX that's the name that'll help you test and validate and interact with your socket implementation This project is split into nine stages similar to how we have 10 stages in the last project。

And it's going to be due on November 11 at midnight。 come to office hours if you need any help。

Project office hours， not the content onces。哭。Can I ask folks to move down。

 just makes for slightly more。Compact lecture。

![](img/146bf0454029d3cf36fb91fdc7713fe5_2.png)

While we're doing that quick announcement following four lectures。

 we're going to go back to the pattern we tried earlier， we're going to release four lectures。

 These are again recordings by Muphy from 2020 the topics are covering the DNS HTP。

 Ethernet and various discovery， bootstrap protocols like DHCPNR so that you can start to reason kind of end to end from the time you set up your laptop to you download a page all the steps along the way that involved these are again Mufi is a fantastic lectures all of you know I think the feedback we got from the survey was that。

The recordings were welcome。 Everyone enjoyed them。

 There were some mixed feelings about having you know a flipped lecture。

 every other lecture because I was adding to time。 So we're going to do one flipped lecture at the end of the four sessions。

 we're probably going to do a slightly more handson walkthrough of the protocols and the set DHCP DNS and so on that we would have covered in these four lectures。

 So just to repeat no inper lectures starting this coming Thursday and the following week。

Do watch the recordings。 We will have quizzes， as usual。 the following Tuesday。

 we'll have a flip lecture and do watch the recording before coming to lecture。

 will be the flip lecture will assume you've watched it。

All of this reminders and details on this will be posted on it。

 Any questions or thoughts on this before on the logistics side。



![](img/146bf0454029d3cf36fb91fdc7713fe5_4.png)

Okay， so today then is our last lecture on the topic of congestion control。 So this is lecture 3。

 Now on congestion control。 The last time what we did was really， the recording you watched。

 I hope is the goy details of how TCP congestion control works and actually stepping through the rules for how you inement your window。

 how you slide it forward when you retransmit and so on。



![](img/146bf0454029d3cf36fb91fdc7713fe5_6.png)

Today's lecture is going to be quite different。 We're kind of going to take a step back at slightly higher level the topics we cover we're both going to look at trying to model the performance of TCP。

 So moving away from these detailed one second act and so on。

As well as a little bit of a critique of TCP， What does it do well， What does it not do well。

 which motivates some of the changes in evolution we've seen that are being deployed in TCP。

And then finally， we're going to talk about route assisted congestion control and some of this is in practice。

 some of it is in more development research phase， so we'll talk about all of those ideas。

Just to get your head in the right， we're going to cover a pretty broad range of design ideas。

Some of them are fairly， even they're still in the research phase。

 so we're not expecting you in this class to fully understand the idea。

 but what you should know is what problem is that design trying to address and the high level idea for how it's trying to go about solving it。

But unlike the TCP congestion control we did， we're not expecting you to know the details of how these ideas work。

跟。So with that， the first topic for today is this TCP throughput equation and the problem it's trying to answer is the following。

 which is you know we've talked about exactly how TCP works， congestion controls。

 sliding windows and so on， AIMD increasing， decreasing your window。But if I ask you a question。

 you know， given a path。What TCP throughput can you expect as an application developer or as a user。

Would you be able to answer。Tripe。if I tell you， here's your part。

 you know there's certain long trip time。Certain properties， let's say loss weight。It's very hard。

 right because we've studied very low level mechanisms of how TCP works。

 I would you'd probably be able to tell me， well， you know。

 if your window size was 17 and you got three duplicate as， you would cut your window size so much。

 and then you would be able to so many packets in the network at this point in time。

 But that's not very satisfying。 That's not how we like to reason about performance at a higher level。

 We want something a little more compact， a little more general as a way of reasoning about performance。

 And so that is what the TCP throughput equation tries to give us。 So it is a simple model。

 it makes certain simplifying assumptions because as you can imagine。

 there is no clean closed form equation for exactly precisely what TCP throughput you could expect。

But what is going the question is going to answer is。

 if I tell you you have a path between a source and a destination。

 And I tell you this is roughly what the ground trip time of that path is。

 And P is the loss rate of the path。Then the equation is going to tell you what throughput you can expect as an application developer or as a user。



![](img/146bf0454029d3cf36fb91fdc7713fe5_8.png)

So let's start stepping through how that works， So the simple model starts by the assumption that let's say that we get a loss every time the sender's congestion window reaches is this parameter W max。

 that's the max window size at which you experience loss。

And we're further going to assume that loss is detected using the duplicate Act mechanism。

What this means is we have no timeouts。 It means we have one isolated loss。 So again。

 just another assumption。And so then if you think about how at the center size。

 your window is going to evolve。Step one， you get three duplicate acts， you've detected a loss。

 the first thing you should do cut your window size in half。After this。

 the phase we should enter is AIM D。 So additive increase multiplicative decrease。

 So one go trip time after we detect the loss， we would expect our window size to be W max by  two plus  one。

2 ground trip time。 So plus one additional round trip time later， we add plus2。

Yet another counter trip of time， we add plus 3。Until in our model， we go up to Wmax。

That's the max window size。 where again， we're going to experience a loss。

That's by the assumptions of our model。And then at that point， again。

 cut our window size in half and re repeat。And so really the evolution of our window size is we're going from W max cutting in half to W max by two。

 increasing by one every round trip time until we hit W max again and then again cut in half。

So we're increasing by one for W max over two ground trip times。

Y W max over two gotri times because we cut in half to w max by2。

 and then we go by one every ground trip time till we hit W max。

 So that means we've gone through W max by two ground trip times。And then， we repeat over and over。

So with this very simple assumption， what this tells us is the average window size in a roundrap time。

 assuming we are always in this study behavior going up and down between half and full。

The average window size pergram trip time is three quarters， W max。And so the toolput， right。

 the window is just how many of these packets you've sent。 So the toolput is three quarters W max。

Multiplily by MS， that's just how many bytes you send in one packet。Divideed by the ground trip done。

Because we' are sending on average three quarters of the window。On in one ground trip time。

 So bytes divided by a time。 We're getting the throughput。Are we good up to this point？Any questions？

So this is already giving us W max expressed in terms of the long trip time。

 we sorry not W max throughput expressed in terms of the long trip time。

But we still have this term W max over there。 That's not really a path property。

 So the next step is to the place W max by something。And that's an expression of the loss grade。看。

Any questions up to this point？

![](img/146bf0454029d3cf36fb91fdc7713fe5_10.png)

Okay， so that's going to be a step  two of the model。

 So this is now what we I'm showing you is the size of the congestion window in terms of number of packets。

On the Y axis with time on the x axis。And so we started with this slow start phase。

 we reached W max one loss cut by half， and then we keep going up and down。

 doing AIMD between those two points。We're going to focus。 We said we're。

Assuming we stay in this AIMD phase forever。 So we're knowing the initial slow start。

 And so let's focus now on one of these periods here。That Ive highlighted in blue with a。

And so if we think about our loss rate now in this picture， we've dropped exactly one packet。

For every one of the a packets， the packets that we've sent in that shaded region。So on average。

 we're losing one packet for that entire shaded region。And so our loss rate is one over a。

 where a is the total number of packets that was sent in that shaded region。行。

So packet drop P is one over a。 All that's left to do is calculate how many packets are actually in that traded region。

 a。And we just said that。This period of time is W max over two ground trip times。诶。

Does that make sense to everyone， That's because in every account trip time， we're increasing by one。

And we increased。 We went from W max by 2 to W max。So we had W max by two go trip times。Yeah。

And we also said that， on average， we have three quarters。Of W max packets per ground trip time。Yeah。

So the total number of packets in that shaded region is just the product of those two。

And so it's taking three quarters W max multiplied by half W max creates W max square。

That's a loss grade in terms of the number of packets。So if I now just replace place， you know。

 move the terms around， I get W max in terms of the loss rate。

 I plugged that into the formula we had earlier for the throughput in terms of W max。

And what that gives us now is。This function here， that is throughput in terms of the round trip time of the path and the loss rate。

Let me pause for。Any questions or anyone would anyone like me to repeat。Any aspect of this？行。

Maximum segment size。 That's the number of bytes that in a packet。

 So all the accounting until we put in M S S is in terms of packets。Po time。

 So when we multiply by M S， we're getting to bits per second。

Any other questions or any point in this that anyone would like me to repeat。

We're going to be using this equation a bit。The slides that follow。 So it's good to get it， right。

Right because we are increasing linearly between half and one。

 So the average is headquarters quarters。嗯。

![](img/146bf0454029d3cf36fb91fdc7713fe5_12.png)

Okay， so given a path， what TCP throughput can we expect。

 we now know that that throughput is going to be proportional to one of our R TT inversely proportional to the ground trip time and inversely proportional to the square root of the loss rate along that path。

You can look through the devation offline。 It there's nothing complicated really there， but。

Think about it in terms of intuition。 This should make complete sense。

 Why is it inversely proportional to the round trip time， Because remember everything we did in T CP。

 we said you're clocked by ax。 You wait for the round trip time for an act to come back and then you react。

So if my gun trip time is smaller， I'm getting as back faster。 And so I'm reacting faster。

 I'm increasing faster。 So it makes sense that throughput is inversely proportional or short ground trip time means I'm reacting faster。

The same with the loss rate。 If I have a high loss rate loss on the path。

 then I'm going to be cutting back more often。 So it makes sense that I have lower throughput。

 If if I have very low loss， then I'm going to be increasing and staying there without cutting down。

 And so again， makes sense that it's inversely proportional to the loss rate。

So the model makes a number of simplifying assumptions in particular。 we ignore close start。

 which is typically fine if you have a long lived connection where you know you slow start once。

 and then you're mostly doing AIMD。 So that's a fine assumption。 It does assume a fixed counter time。

 It does assume that you have this know very clean loss pattern where I drop exactly one packet every time I hit W max。

But all of those assumptions aside， this is actually useful because it allows us to kind of take a step back and get away from thinking about individual acts and thinking about the overall behavior of TCP。

Okay， so as well see in a few slides coming up， this， you can actually look at this。

Just looking at this equation gives you a number of insights on what TCP both does well。

 but also doesn't do so well。 And we'll get to that in a minute。



![](img/146bf0454029d3cf36fb91fdc7713fe5_14.png)

So just to take stock， we've kind of wrapped up TCP congestion control。

 and we're going to be moving into， you know， what does TCP not do Well。

Remind ourselves of the main features of how TCP is doing congestion control。

So one it's host based with no support from routers。 In fact， it's sender based。

 All of the intelligence is at the sender。It's lost paced。

That's what we're using as an indicative congestion。

We're adapting the time scale at which we adapt is the ground trip time。We start out in slow start。

 We said we start small with a sea wind of one and we double it every ground trip time until you have loss。

And then in study state， this kind of the way we adapt to find the correctorators we do this additive increase。

 multiplicative decrease。 That's a very gentle increase。

Very conservative drop when you experience loss。And finally。

 we said that the throughput depends on the counter of time in the loss rate。

 according to the equation which is direct。So if you look at this now and you know。

 I ask you to shift your hat a little bit and be a little critical。Any thoughts on what？

What in this setup or in this design， the set of design choices do we not like or could be problematic or could be idiosyntic or something to comment on。

好。So we changed the way throughout the process。 We're constantly either increasing， decreasing。

 whenever never at a steady state3 point。 Yes， that's one。在曼林。Others。The fact that it's loss based。

S know， there are many things about loss ma that can be。 so loss could be not due to congestion。

 absolutely okay。Anything else about to setup？Anything about Sands？Its purelyurely ho space。

 which is both a blessing and a curse。 We'll get to them。Anything else？Okay。

 let's look at some of them。 I think I have about eight of them。

 but so implication number one is actually comes directly from looking at the TCP throughput equation。



![](img/146bf0454029d3cf36fb91fdc7713fe5_16.png)

We've said that flows get through put that is inversely proportional to the long trip time。

This is kind of by design。 Weve decided to wait for acknowledgeknowments to come back and decide how to adapt a congestion window based on that。

 But this has certain implicationsplification。 So if I showed you a very simple example like this。

And I said A1 is talking to B1 over a ground trip time of 100 milliseconds and A2 to B to over a round trip time of 200 milliseconds。

 What would the TCP throughput equation tell us， what。

 what would you expect in terms of the throughput A1 is getting versus A2。Everyone has twice the two。

 all else being equal。A1 is getting twice the throughput of it。

So TCP is actually unfair in the face of heterogeneous ground trip times。 You know。

 we talked about AIMD and how it converges to efficiency and fairness。

 If you go back to that example， youll realize we were assuming they have the same ground trip time。

 They're reacting at the same time。 And so we converge on perfect fairness。 But in practice。

 if you have a short ground trip time。 you are ramping up faster。

 so you are getting you being greedier and getting your share of the bandwidth。

 So TCP is not perfectly fair。Right， so for example， if sitting in Berkeley。

 if you're downloading a file from a server in San Francisco and assuming you know round trip time is proportional to geodistance。

 you will have higher throughput than if you were downloading it from。The East Coast， for example。

 because you're round trip time is smaller。 And in fact， when we talk about the web and HtP。

 you'll hear mu we talk about content distribution networks。

 These are companies like Akaai or Cloudflare that actually cache content very close to users。

 And it's for a few different reasons， one is just your propagation delay is lower。

 But you get this additional boost because TCP ramps up faster and gives you better throughput。

 And so in practice， that's why there's so much of a push amongst other reasons there is a push towards moving content。

 know edge computing and moving content and computation close to users。Any questions on this？

So this is one of the， you know， you can call it a problem or not a problem， but there is really。

 there's no solution to it， per se this is just how this is actually TCP as we experience it as Internet users。



![](img/146bf0454029d3cf36fb91fdc7713fe5_18.png)

second implication that comes out of looking at the TCP groupput equation is this question of high speed TCP and here the setup is as follows。

 let's say you had a path on the internet where your bottleneck capacity or the capacity at which as a sender you could send was 100 gigabits per second。

And your gun trip time， let's say is 100 milliseconds。 And you have， you know。

 your usual M S 1500 by， let's say。If I plug these values into the TCP throughput equation。

 what this would tell me is that the loss rate I need in order to achieve a throughput of 100 gigab per second。

Is2 until you know 10 to the -12， which is just a ridiculously low loss rate。

 This is saying you have to drop one in like 50 billion packets。

Or if you do the calculation of how many round trip times it would take you。To ramp up to that rate。

 you'd be within hours。And so what's going on here。

 I'm saying that the setup I want is that one flu get 100 gigabits per second。

And it has to be able to ramp up。 if you put in the numbers here and compute how many packets in a congestion window for this kind of bandwidth delay product。

 it's in the thousand tens of thousands。 So I forget what the exact numbers is。

 but 80 or 100000 packets。 And so if you think about it， what happens is。

 let's say I had a congestion window for 10000 packets。 And I lose one packet。

TCP is going cut its congestion window by half to down to 50000 packets。

 And now it's going to add one packet every 100 milliseconds。But you have 50000 order 50000 packets。

To ramp back up to。 So it's going to take you 50000 long track times to。

Get back up to that high rate。50000 ground trip times so you know multiply by 100 milliseconds。

 you'll see that you're spending hours trying to ramp back up to 100 gigabbits per second。

So basically， these numbers are not practical。 and even a loss rate of 10 to the -12。

 that's approaching the biter weight of most communication media。

 So you're pretty much going to guaranteed to encounter loss while you're trying to ramp up to that rate。

And so the fundamental problem here that TCP is facing is that in order to scale a single flow to a very high throughput or very high speed link。

It's very slow if you're going to do this additive increase where I'm adding one packet every round trip time。

And so the usual questions， if somebody will ask me at this point， anyone have any questions。

The usual question somebody will ask is how common is this。

 Like how often do we have one flow that needs to occupy 100 gigabit per second path。

 The answer is it's not very common。 So this is not a problem that everyone on the Internet faces。

 even though we have 100 gig or 10abit per second links。 they shared by millions of users。

 but the scenario， for example， where this comes up。 In fact。

 the teams that brought up this issue and this is being addressed in the standards bodies was actually the Enet ESnet is the energy Sciences network。

 This is a network built that connects the national labs in the US and connects them also to the Department of Energy。

So these are physicists and astrophysicists。 They have particle simulators。

 and they have huge data sets collected from outer space and so on that they need to transfer。

 And so it is quite common that they really have these very large transfers that they need to move data between sites。

 and they have built a network that is just for them， not just for them。 It goes over the Internet。

 but they've provisioned 100 gigabit per second links between all these labs and they they would like to be able to use them。

 So it's a really bad situation in which you've deployed this highspe network and you effectively can't use it because TCP is getting in the way of achieving that kind of high throughput。

 And so the solution they've curved know that they've been working on is know it's one of these it's in the process of been in the process of being standardized for a very long time。

 It's called high speed TCP。 and does a very simple change to TCP。

 What would you do if you are in this scenario。

![](img/146bf0454029d3cf36fb91fdc7713fe5_20.png)

If you were being asked to modify TCP's congestion control to fix this issue。Yeah。At more than one。

 That's one little absolutely right。 So increase faster than one with one additional condition。

Remember， you have to be careful to not stomp on， you know， other flows。

So very close to what you said that the flow， the center monitors its congestion window。

 And once it's passed a certain threshold。Then it says， okay， I'm in a high speed regime where。

 you know， I'm not competing for 100 mebits per second。

 I I'm competing for large amounts of bandwidth。 I can start ramping up fast because there's a lot of bandwidth available。

 And so typically what high speed TCP will do is a low additive increase up to a threshold。

 And then after that， it will kind of increase as a function of the congestion window。

 So it's going superlinely after that point。And even when it decreases。

 it will decrease a little more modestly than cut half so you're not expected to know the again。

 the details of how high speed TCP works， but the idea is to know what the problem is that TCP increases too slowly if you're trying to occupy these high speed links and the basic idea would be increased faster。

Faster than linearly。Are there other approaches you could think of to solve this problem？

Without changing TP。And this happens all the time on the Internet。嗯。Send more flows。

 open multiple simultaneous connections。And the other approach that people have proposed is using route assisted congestion control。

 which we'll get to in a bit。What do people think about opening multiple connections。

 Any downside to that as a solution。Kin of solve the problem。

 You could open 00 connections get 100 x0。There's one little reason why it's painful to do so。系。You。

 you're getting at it， which is from the viewpoint of an application developer。

 The nice thing about TCP was it gave us this nice by stream attraction。 You just said。

 I have this data to send。😊，Go， send it， open a connection， sendend it over the connection。

 you're done。If you're going to open multiple connections。

 the application now has to reason about how it's partitioning application data across connections。

 It has to keep track of this particular connection God reset let me restart open it and resend that data or maybe one connection is going slow and the other one's going fast。

 maybe you have to repartition data across the connections So there's a little bit more work to do as an application developer。

 but it's certainly over。Yeah， I would probably say it's maybe easier than taking your program to be multi threaded initially。

 but yes。That's a good analogy of。

![](img/146bf0454029d3cf36fb91fdc7713fe5_22.png)

Implication3 is this notion we call weight based congestion control。

 And so here this is exactly what someone alluded to earlier。

 which is that TCP through is choppy we keep that sortoo pattern that we talked about where you ramp up。

 you cut down， you ramp up， you cut down。 there are certain applications that this is not the natural way for the application to be behaving in particular。

 if you think about audio or video streaming applications。

 there's a certain rate at which they're sampling audio or video and the natural behavior for the application is to pick a weight and just transmit data at that rate。

And so the one solution by which you can support such applications comes directly out of the throughput equation。

 It's what we call equation based congestion control。

And so this is for imagine that you are an application developer that doesn't actually want to use TCP because of this choppy behavior。

So what you could do is send a few packets， measure the counter trip time， estimate the loss rate。

 P those values into the TCP throughput equation。 And then that's the rate at which you send。

There's also earlier on in the lecture， somebody asked。

 what about if you have a UDP application and UDP is not doing any congestion control。

 Should't we be worried about how UDP is competing with TCP。

 The right way to build a UDP application would be to do exactly this。

 which is to say what share of the bandwidth would TCP take。 I'm going to take the same share。

 And then I'm just going to send it that weight。Any questions on this？

And so the reason we're doing this following the equation is telling us that we allowing a different way of being TCP friendly without actually following TCP's congestion control behavior。

要。This would typically the when you， there is a standard， again。

 the RFC number there that is called equation based congestion control。 It doesn't have to be TCP。

So you could take the TCP header and you could do TC liability if you want。

 but have the rate be determined。By the the equation rather than the sliding window。

 or it could also be a UDP based implementation。 So it doesn't have to be T。



![](img/146bf0454029d3cf36fb91fdc7713fe5_24.png)

Other limitations of TCP congestion control， One that came up earlier。

 we've talked about this in the past， TCP。Will confuse loss due to other reasons as being lost due to congestion for T CP。

 any loss means it's congestion。 It will cut its weight。

So if you have something like you had corruption along the link or something。

 TCP is not going to know that。 It's still going to behave like you it has congestion and it's going to cut its weight。

 So you get lower performance than was necessary。This， again。

 not necessarily something we have a solution to。Yet another question。

 How do you think short flows would faile if we do， if we when we have TCP。

 So and the reason this is particularly relevant is most of the measurements will show that most flows are actually very short。

There are few packets。 So， for example， this is a data point from， I believe。

 a Google study a few years ago that 50% of flows have one packet to send or less than one packet of data。

If you think about why this is the case， you know， you think about a lot of data center applications。

 for example， it's a key value to all look up。 that you're saying。

 give me the value corresponding to this key。That's not a long flu。 It's a request response。

 very short flow。And like 80% of flows have less than 100 kB to cent。 So that's roughly， you know。

 less than 10 packets in a connection。So if we have a vast majority of flows that are just a small number of packets。

What do you think TCP congestion control is going to do？

 What do you think is the downside to doing it to how TCP does congestion control。Let's start with。

 what would TCP do。Yeah。 so GCP starts a connection in slow start。

 So imagine if had four packets to send。I'm going to send one packet， wait for the act。

 send two packets， wait for the act。 sendend the fourth packet。

So I took three round trip times to send four packets。That's ridiculously low throughput。

 It's roughly one packet per ground trip time is our throughput。

 And we've just said that something like 80% of or 50% of flows。 That is the throughput theyagon。

They're going to see。And so this could be a problem because one。

 many flows are just never going to leave slow start。

 So we've done all this work in TCP to find your fair share and to maintain that fair share and to adapt to it。

 But in fact， most short flows just going to be in slow start。

 They're going to take longer than they should have。

And that's just what short flows are going to experience。The other issue that turns up。

 and this is going into the specifics of how T speed has congestion control is remember。

 we rely heavily on duplicate acts to avoid timeouts。 But let's say I have you know。

 five or six packets in a flow。 and the fourth or the fifth packet got lost。

I just don't have enough packets in the pipe to trigger duplicate as。

And so it's often the case that a short flow， if you have a loss。

You're going to see your timeout and timeouts are very long compared to typical ground trip times。

 And so again， you're going to get poor performance if you have a short flow。How would you fix this。

 So first， you know， how much of a problem is this， You might be thinking， wow。

 if 50% of flows are one packet， why did we do all this work in TCP in the first place。

 Because when you look at the measurements a different way，50% of flows are very short。

One or two or five packets。But 99 or 90% of bys on the network are coming from long flows。

So we call this elephant and mice， where most of the bites are in these long flows。

Even though most flows are these short mice flows and this elephant versus mice is something we'll come back to when we talk about data centers。

But back to this problem。 So we have lots of short flows。 They never leave slow start。

 They see for performance。 and we would like， They suffer from timeouts。What's a quick。

 somewhat hacky fix that you could imagine doing。对。Yes， just start with a larger initial window。

 So this was actually， Google lobbied the standards bodies a few years ago。

 something called initial window 10， which says， let's start with an initial window of 10。 So now。

 if you have fewer than 10 packets to send， you just dump them in the network and you're done。

So very pragmatic。Quick fix to the problem。It doesn't entirely solve the problem because it doesn't solve the problem of not having enough duplicate acts。

To trigger re transmission。 So you still in timeouts， But otherwise。

 it solves the problem of slow start long trip times。That's a great question。

 Why would you not have a different protocol for short flows？ And， in fact， in the data center world。

 there is a lot of work on being able to just send if you have a short flow。

 send it off quickly in practice， you know。This works well enough， right What is Gong。

 which is saying， I'm going to give you a congestion window of 10。 And then its。

 it kind of fixes the problem。 And you don't have to go and rewrite the networking stack and your。

 So from a pragmatic standpoint， this solves the problem。 There's no particular reason one should。



![](img/146bf0454029d3cf36fb91fdc7713fe5_26.png)

yet another problem。 TCP fills up queuees。 This came。 This is， again。

 related to using loss as an indicator of delay。 So if you remember the way TCP works by design。

 it is deliberately trying to find the maximum weightd consent。

 And the way it's doing that is by causing loss to happen。And so by design。

 TCP is going to fill up the cure at the bottleneck。Link。And if you remember。

 we said loss follows delay。 That means by the time you experience loss。

 you have definitely experienced delay because you filled the queue and your packets were sitting in a queue。

Incoring delay， you know， before you even saw loss。

And this means that delays are large and they' are large for everyone。 So imagine that you had。

 you know， bottleneck link and you had a number of these short flows。

 have one or two packets to send。And if there were no long flows in the network。

 they would see zero queuing delay。They would just be going through。

 And now you have this large flow that fires up that's transferring。 Let's say this 10 GB file。

And so that one long flow is filling up all the queuees。It's causing delay not just for itself。

 but for all the flows in the network， because those short flows are also now stuck。

Behind the long close and the sitting in the queue and Co delay。And a particular this is again。

 this is how TCP was designed to behave。 And so it's not like the designers were unaware that this was the behavior。

 But what really caused this to be a problem was the fact that a lot of vendors started to add more and more memory on goers。

 and in particular， the very low and home goers that we have in our home。

 they have a ridiculous amount of buffer space。And the idea here was that。

The home go of vendors just didn't want to have cost packet drops at the home。

 So they started putting in large buffers。 And so we started seeing these very large delays。And so。

 now this。Backet delayed due to queuing can actually be significant。On the Internet。

 this is a problem that's called buffer bloat。And this was particularly problematic for people for service content or Internet services that cared about latency。

 And the canonical example of when this really annoyed people was when Google started running YouTube。

What they found was that the search response time was going down when the home user users at home were simultaneously watching YouTube。

 So if you were watching a YouTube video and you someone was doing a search in your home。

 the search they would see search delays or search response times that were much worse because sometimes there was seconds of buffering at the home router users。

So this is actually， is the problem clear。行。Right， so think about what is the router doing。

Sending packets out over the link。And TCP by design is going to increase its rate until you cause a drop。

 So what does that mean， I the sender is going to keep， let's say's YouTube in this case。

 is's going to keep trying to send traffic at a higher rate。

 which means that at your homeger going towards your the user。

 the queue at the homeg starts filling up。But TP is going to continue to increase that rate until it sees a drop。

Which means that your queue at that router is full。So now when a packet comes in at that route。

 it's going to sit at the top of the queue and wait for that queue to be drained。 But if I had。

 let's say，10000 worth of packets。That could sit in the queue。

That's a very long time for that packet to be delayed。Yeah。Any other questions。



![](img/146bf0454029d3cf36fb91fdc7713fe5_28.png)

So this is exactly what LED to was the reason why Google started working on this new congestion control algorithm called Bibia。

 And the idea here， what do you think you would do if you were。Google trying to fix this problem。

You want loadly。Because if you think about it， what is the benefit to sitting in a buffero at a go。

No benefit from performance or a throughput perspective。

We put buffers in because we said traffic is bursty。 We want to absorb temporary bursts。But now。

 if we say we' are always running with this queue full。It's not helping me in any way， really。

What would you do to try and fix this？哎。You go to the move the queue。 There's a slide。

Concerned with that， which you could the move will shrink the queue。

 So there is a move for you know telling outer vendors， not， especially home outer vendors。

 not to put so much buffering on home routeers。 There is a slight concern then that if you have bursts。

 you cause drops。要。Right， so that's actually a neat idea。 Not the one was not the what BB did。

 but you're absolutely right。 And this was an idea called random early detection。

 which are saying as your queue starts filling up， let's proactively toss a packet to tell the center to slow down。

 Q idea。 Not the one。 Let me rerase the question。 What would you do without changing route us。

You know， if you're YouTube or Google， that's the only option you have， yeah。It's an interesting car。

 What if you don't have bursty flus， But would that fix the problem。

 Because the problem here is that TCP is deliberately trying to increase its rate。

That's its only way it knows how to stop is to first fill the cube。嗯。Yeah。

 so the idea here is delay what we call delay based congestion control。

 This is a very simplified version of what TCP does。

 So here's what you should understand is what is sorry in our TCP BBR of what BBR is trying to do。

 What I would like you to understand is the idea that of what BBR is trying to do。

 And so what BBR is trying to do is to say we still want to run at the maximum throughput possible The bottleneck or the available capacity of the link。

But we want to do that without building up the queue。

And so what BBL's insight is to say that as the queue builds up。

 the signal that I get as a sender manifests in Dly。

So if I was measuring the delay that a packet takes from the time I send it to the time the app comes back。

If I'm starting to build a queue， packets are starting to sit in the queue。

I should be able to see it by measuring the delay in packets。And so their main idea is to say。

 rather than wait for loss。 Let's measure delay。 Let's get a good idea of what the minimum delay of the path is。

 So if I could measure delay often enough。The lowest measurement I get。

 the minimum delay is an indicator of reasonable approximation to the delay I can expect without queuing。

If I start to see my delay go up beyond that， then I can cut my weight。

So it's cutting its rate early when it detects an increase in delay。As opposed to loss。But otherwise。

 the basic idea of TCP of adapting and searching for going up and going down。

 searching for the right rate at which to send that remains inbaia。

 The main idea is look for measure the delay and see whether that's going and react to delay rather than loss。

Any questions？So again， we don't have I don't expect you to know the details of how BBR works。

 but understand the problem it's solving， which is that TCP builds up queuees and understand the core kind of nugget behind it。

 which is we're going to measure delay and react to increases in delay。cheating with D， can we。

Are there different ways to cheat with TB。Right， so why are we measuring the minimum mark T T。

 so the idea in B， is that your question。 Yeah， So the idea in BBR is we don't want packets the queue to build up。

 And when the queue builds up delay increases。 But I need to know some idea。

 I need to have a baseline。 What am I comparing to。I need to know what a good delay was like。

 That good delay is going to be the minimum L T T that I've ever seen。

And I'm going to guess or hope that that minimum R T T is correspond to when I had no queuing。

Any other questions。

![](img/146bf0454029d3cf36fb91fdc7713fe5_30.png)

Cing ways in which you can cheat as a TCP centerer。Tos。这个老子。

If all you controlled was the center side of your TCP connection。

What are things you could do to get higher higher through。So don't cut your weight in half。

 That's certainly one。 The other one increased by more than one M S every long trip time。 So。

 in fact， if you walk through the kind of efficiency fairness curves we did last time。

And if you said x is going to increase by two every round of time。

 while Y is going to increase by one every round of time， you'll see that x gets twice the rate of y。

It's a very easy way to get more than your fasci。

![](img/146bf0454029d3cf36fb91fdc7713fe5_32.png)

Yet other ways just open multiple connections。

![](img/146bf0454029d3cf36fb91fdc7713fe5_34.png)

Again， going back here， if a starts 10 connections to B and D starts one connection。

 then a is going to get 10 times the through of D。Not of this is probably the easiest way to get more than your fair。



![](img/146bf0454029d3cf36fb91fdc7713fe5_36.png)

Use a large initial window。 Nothing stops you from starting with a window of  hundred0 packets。

 Basically， nothing in TCP stops you from。Not following the rules。

And just sending more than you should。

![](img/146bf0454029d3cf36fb91fdc7713fe5_38.png)

Does that make sense to people？So natural question everyone usually asks here is。

 why has the Internet not suffered congestion collapse。

We started congestion control by talking about how。

The reason people put in congestion control was because they experienced congestion collapse。

We now have this very sophisticated congestion control algorithm。

But we also know we live in a world where there are lots of malicious actors on the Internet。

 And we just said， you don't have to follow that congestion control algorithm。

Why why do you think were we're doing okay。And at least as far as I know。

 there has never been a report of congestion collapse on the Internet since the 80s。

certainly if send us there isn't a clean answer， by the way to this question。 Certainly。

 if you had a set of sources that were sending way too much traffic。

 it would be treated as a denial of service attack and ISps would probably wait limited。

 the other reason is， you know even people who cheat on congestion control， they do back off。

 So if you go back to know the early cause of congestion control。

 the TCP implementations at the time they had a fixed timeout。

 So they never adapted their timeout and they never cut back on the weight。

 So every time there was a time out and it could be a short value。

 It would just dump an entire window into the network。Whereas today you， you can。

 even if you open 10 connections， those 10 connections are going to back off when they experience congestion。

 or even if you， you know start with a larger initial congestion window。 when you have drop。

 you will drop， you will do multiplative decrease。 So while in principle， you could just blast。

Packets into the network。 That's usually an attack。 And that gets very limited。

 If you're actually trying to just modify TCP a little bit to get an unfair advantage。

That's going to give you an unfair advantage， But it's not going to cause congestion collapse。So。

 that's。Speculation of why we haven't yet suffered a congestion collapse。

 The second question then you should ask is， okay， so we don't have congestion collapse， but is。

Fairness or unfairness， common on the Internet。The answer to that is we actually don't know。

 There is there are anecdotal the reportss that turn up in the press once in a while。 So。

 for example， few years ago， there was a study that people did showing that BBR actually is not fair。

 that if you are in certain scenarios where BBR is competing with know some other legacy T C P connection。

 BBR is going to share take more than its share of the bandwidth。And so this caused you know。

 some news reports and and Google worked with these researchers to fix BBR and so on。

 But this does happen。 What I would not be able to tell you is how common it is。Across the Internet。

 what is the degree of unfairness。 And you can imagine this is actually a hard question to answer。

 In the case of Google and Bbiia， they open source the system so people could grab it。

 experiment with it。But we don't really know what Netflix does。

Or I'm picking on Netflix for no particular reason。

 but many of these content providers that have close close source implementations。

 we just wouldn't know question。BBR is actually， so if you're talking to a YouTube server。

 this server when it's sending you packets is gonna BBR。Bria is TCP。

 it's just a different algorithm for congestion control within TCP。

So this is the trick that congestion control is just an algorithm gunning at the center。

 So it's still TCP。 That's a great point。Okay， yeah。呃。Soorrry。The Google is。 so， you know。

 the original implementation for BBR was in addition。

 a modification to the congestion control algorithms in Linux， for example。

 And then it's open sourced。 So at this point， you could go grab the source code and run BBR on your laptop。

Yeah。

![](img/146bf0454029d3cf36fb91fdc7713fe5_40.png)

Last point， this is less to do， you know， moving on from cheating and so on。

 This is partly more a software engineering kind of practice is that congestion control is deeply intertwined with liability。

 And we talked about this， you know， at length that if you look at how congestion control is implemented in TCP。

The mechanisms are deeply related to how TCP is doing reliability。

 So we use duplicate acknowledgements， We use acknowledgements， timeouts。

 We have this notion of window。 We have rules around fast street transmit and fast recovery that are all type to how TCP is doing reliability。

And when I first introduced it， I kind of talked about this as being an attractive aspect to how TCP does congestion control。

 It was a few lines of code change in the TCP implementations at the time。This。

 that is true positive。 The downside is， it complicates evolution。

So when you think about how you of modularity in your implementation。

 we like to have a certain separationation of concerns。So， for example。

 if I wanted to move from cumulative acknowledgecments to selective acknowments。

That should be a problem for how we did reliability。But in T CP。

 it also affects how we do congestion control。 We then have to go back and revisit all our faster recovery faster rate transmit roads around congestion control。

So this is not necessarily a performance issue。 It's more a maintainability of the code issue and the modularity of the software issue。

Why， you know， this is relevant is sometimes we want congestion control， but not reliability。

 If you have real time audio or video。But there's no easy way in TCP to turn off the liability and get the congestion control。

 You get both。The flip， the universeverse is also true。 You know。

 I have had struggled to come up with an example application， but sometimes in principle。

 we could want reliability and not congestion control。Let's say we had that simple request response。

 So one key value look up。I don't really need congestion control， but I do want reliability。 Again。

 there's no easy way to turn off congestion control and keep reliability in T CP。

So just from a software much load。嗯。Standpoint， this may not have been the best decision。



![](img/146bf0454029d3cf36fb91fdc7713fe5_42.png)

So quick recap TCP problems， you know misled by non congestive losses fills up queuees which leads to high delays。

 short flows don't really benefit from much of congestion control AIMD impractical for high speed links。

 the sort too pattern of is choppy which is not ideal for certain applications。

 unfair under heterogeneous RTTs， we don't really。Have a new solution for that。 tightly。

 coupled with how we do the liability and find the end host can。That might seem like a long list。

You might feel like， wow， that's a major list of issues with TCP。

I actually think with the exception of the possibility that end hostss can cheat。

 most of these other issues， they're not show stoppers。

 We have ways of dealing with them or workarounds that are reasonable。

 which is probably why TCP has persisted so long。What do people think is this reasonable。我听。

The one other observation though to make here is that， in fact。

 we and this brings us to the last part of what we were going to cover is that most of these issues。

 you could very cleanly fix them if we had some help from voterss and several of you have got this point up throughout。



![](img/146bf0454029d3cf36fb91fdc7713fe5_44.png)

For example。We are misled by loss。 or， you know， you have to wait。To fill up queuees to get lost。

 Well， routes know the level of congestion they're experiencing。

 They could just tell and host if they congested。Likewise。

 if we are unsure of exactly the end host is， the sender is unsure of what rate it should send at。

 maybe the router could just tell you what rate。It can accommodate。

The routers could send feedback directly back to the senders。 And finally， if endjose can cheat。

You know， one strategy is to have goers enforce isolation between flows to make sure that cheating is not an option。

And that's kind of at a high level three ways in which what we call Ger assisted congestion control。

There are many， this is again， a large design space， but three ways in which it seems most helpful。

 One is to enforce fairness。 So we don't rely on sends doing the right thing。

The second is to have a more precise rate adaptation。

 so we're not constantly sends are not constantly searching for the right rate。

 And the last is just to have a very direct， explicit way of detecting congestion。



![](img/146bf0454029d3cf36fb91fdc7713fe5_46.png)

So we're going to start with the first one asking how can routes ensure that each flow gets what we call its fair shell and Ive been kind of appealing to your sense of intuition of what fairness meant。

 we are actually going to make define fairness more rigorous at last。So the basic idea here。

 what's the setup behind fairness， And you should kind of understand this before we move forward。

The setup is， think of it from the viewpoint of a single goer and you're getting a lot of traffic coming in at that goer。

 Those packets belong to certain flows。Certainty speak connections。 And we， as a router。

 you want to make sure that whatever capacity you have on the link。

 you're going to share it fairly across those connections or those flows。

That's kind of the setup of what we're trying to do。 And so consider from everything next few slides。

 we in the viewpoint of a single router and what that router is trying to do。

And the way in which the jungle setup is that Avato receives these incoming packets。

The first thing the router has to do is know what fluid it belongs to or what TCP connection。

So if you remember way back in the earlier lectures。

 we said theres this five tu that identifies a flow。 the source address， source I， destination， I。

 source port， destination port， protocol field。走。Think of it as packet comes in。

 I look at those five fields， and I decide what flow or connection this packet belongs to。

Each flow is then going to have its own queue at the routeer。It's going to be a 50 cure。

 first and first out。So now we're changing the setup。 in the past。

 we've talked about routers as I pick up a packet， do a look up， send it on。Now。

 we're saying this kind of goto。 if it's going to do fairness， it's going to have a queue。

 a separate queue for every flow。When a packet comes in， it's going to say， you belong to flow 59。

 and it's going to put you and put that packet into 59 cube。

So now the routeta has a flow for a Q for every flow。

And then its main problem is it's going to decide which queue it's going to service。

 meaning it's first going to pick a queue。It's going to say which flows needs to be have its's packet sent in order for me to be fair。

 So it's going to pick a queue and then send the first packet in that queue out。

I still haven't told you what faire is and how it's going to decide which queue it should pick。

 But that's the overall setup。Is that that up clear to everyone， Any questions there。行。

You could in IPV 6， right， And that was exactly what it was in IPV 6。

 That's the intent of the field is you could look at the flow Id filling up that back in IPV， Foland。

So now the key question is， Gil， what does fair mean exactly。Roughly， intuitively。

 it means every flu get it gets。

![](img/146bf0454029d3cf36fb91fdc7713fe5_48.png)

Kind of the same。 But more formally， what we， the form of fairness that we talk about。 And again。

 there are many definitions of fairness。 But in networking。

 the one we typically use is something we call maximum fairness。

And the way we define it is as follows， let's say that the available bandwidth that the router is allocating is C。

And let's say that each flow has a demand。 each flow I has a demand Albi。

This is how the rate at which the flow would like to send。And so， you know。

 visually think of it as a pipe there。 I get demands R 1 out2 or3。 so on。

 I'm trying to compute the routeer what allocation of that bandwidth I should give each flu。

So the question we have is， what is a fair allocation AI， So AI is the portion of C。

 the capacity C that's going to be assigned to flow I。

So what allocation AI of the bandwidth should I give to each flow eye？

And so maximummen bandwidth allocation say that each flow I should get an allocation AI。

That is the minimum of its demand， R I。And some value more call F， which is its fair share。

Where F is a unique value such that， you know， assumingum demands exceed the capacity。

 the sum of AI is equal to C。So let's break that down a little bit。 What is this telling me。

 This tells me that if I'm a flow eye， I either get what I asked for。That's all I。

Or if I get something less than what I asked for， I get a value F。

But I'm guaranteed that no one else in this system got more than F。

That's what this equation is telling me。 And if the total demand exceeded the capacity。

 I'm completely using the capacity。 That's just for efficiency。



![](img/146bf0454029d3cf36fb91fdc7713fe5_50.png)

Let's do an example， and then we'll come back to the definition。

 and you can tell me if it's making sense or not。 So let's say that C is 10。I have three flows。

 and their demands are 8，6 and2。How would I do maximum far allocations。

 I would start by saying the fair share。 I have three flows。 I have a capacity of 10。

 So the fair shares I give。Every flow， I offer every flow 3。33。So that's my first guess。 I take 3。33。

 But then I see that R three only needs two。Units， so I'm not going give it 3。

3 when it doesn't need it。 So I'm now going give all three only two。

And so now I'm left to the capacity of8， and I've fully met Al keys demand。

So now I have a capacity of eight。To assign to the remaining two flows， our1 and R2。

So if I have eight units of capacity to assign to two flows， that means I could to be fair。

 assign each one a value of four。4 is less than the demand for either flow1 or flow 2。

So that is the allocation。 The value of f is4。And so the final allocations are going to be four to。

And if you go back to， you know， where we said that your allocation has to be the minimum of this fail。

Shall or your demand。And you'll see that that holds Fs 1 and 2 are getting4。

 and flow3 is getting 2 because its demand was less than 4。Yep。Because the last the question is。

 why is the last one's allocation 2， as opposed to 3。33。

Because it's the minimum of your demand and the fair share F。

 the value of F that we arrived at and the value of F was 4。The final value of F， that 3。

3 p was just an intermediate step in arriving at the final value of F， which is4。

It's nobody will have more than the fair share in the allocation。 Yes， that'。No。

 you mean it can it not be a fraction， It can be a fraction if we wanted to hear。I can have。

 you know，10。4 megabits per second or something。

![](img/146bf0454029d3cf36fb91fdc7713fe5_52.png)

So the key property of maximum fairness is that if you don't get full demand。

 So if you get something less than your demand， no one gets more than you。That's what it's fair。

Does this make sense to everyone？If you think about it， this is what ground robin gives you。

 If we set all packets of the same size and you basically did a ground robin。

One at a time scheduling， you would get maximum funds。Does that make sense for。

Round Robbin is a fair scheduler。

![](img/146bf0454029d3cf36fb91fdc7713fe5_54.png)

And so the key question is， how do we deal with packets of different sizes？

Because if I have a packet that's 1500 Bte and you have a packet of 40 Btes， it really isn't fair。

 It could be highly unfair that we get the say we both get to send one packet each one at a time。

 So this question of different packet sizes actually matters in terms of ensuring fairness。And so。

 the mentor。The crux of the problem that vacuumqueuing， which we're going to discuss in a minute。

 tries to address， is how do we do maximum fairness。

 So think of it as how do we do ground Robbin if we have packets of different sizes。

 That's really the intuition here。And the mental picture you should have is that if I have packets of different sizes。

 the fair way to treat those packets would be to do round robin on a bit by bit basis。

 I would send one bit from every packet。And， of course， this is not practical。 We can't do that。

 We have to send packets， but your mental picture should be， we want to do bit by bit ground w。

We cannot do this in practice， but we're going to approximate it by using an algorithm we call fairqueuing。



![](img/146bf0454029d3cf36fb91fdc7713fe5_56.png)

Because so what is the idea behind faircuing。The idea is that， in fact， Euing。

 imagine that the router is going to simulate。Bit by bit ground Robbin。

And I'm not going to tell you exactly how it does this calculation。 But the idea here is。

Given a set of packets， I'm going to simulate if I did bit by bit round Robbin。

 at what point in time would the last bit in the packet have been transmitted。Okay。

And that point in time where the last bit would have been transmitted is what we call the packet deadline。

And then fairqueuing is just going to service packets in increasing order of their deadlines。

Does this the intuition make sense to everyone。 Don't worry about how I do that simulation。

 But the basic idea is， packets are coming in They're very different length。

 I'm going to pretend I could do bit by bit ground robin and say。

 if I could do it at what time would this packet， the last bit have been sent。

And then I'm going to order the packets based on that time when the last bit could have been sent。

 And that's the order in which I'm going to send it out。And if I do that， then I'm， I'm maximum。Okay。

 so think of it as basically a form of round robin that's extended to the case where not all packets are the same size。

K of Gober's moment here。 This is the the paper that introduced Fequeuing。 It is you know， Scott I。

 of course， is on the faculty， though at the time he did the work。 he was at Xox Park。

 Srini Keav was a graduate student at UC Berkeley when he did this work。

 This is one of the most cited papers in computer science。 This idea of fairqueuing。

 know the idea of maximum fairness and。Doing kind of this fluid model。

 what we call bit by bit ground Robbin had been proposed by actually many years before the decades before that by someone called Negel when he introduced the idea of packet switching。

 but no one knew how to make it practical with different packet sizes。

 And that's what the fair queuing algorithm gives us。



![](img/146bf0454029d3cf36fb91fdc7713fe5_58.png)

Here's a quick example。 Let's say you have these two flows and what I'm showing you here is the arrival time。

What vacuumuing would try to do is to simulate。 again。

 think of this as just a theoretical calculation that's happening。

What would how packets would have been transmitted if I were doing it by Bi ground Wa。

And then I would look at the simulation time and say， okay， when was I done sending the packet？

 And so I would say， okay， the first of numbers  one and two from the blue。 That's very clean。

And then I would say， well， actually， now I need to send the first packet from the yellow flu。

Because it was done sending before three。And then the second packet from the yellow flow and the third packet so packet number two from the yellow flow and three from the blue flow。

 both finish at the same time。And so just to break ties。

 I'm going to service the packet that arrived first。 So I'm going to send。Blue3。

 followed by yellow2 and so on。

![](img/146bf0454029d3cf36fb91fdc7713fe5_60.png)

So fecuuing versus 5fold， things to remember， the advantage of fecuuing。

 if there's one word you should remember， it's isolation。

There is no a routeer is going to enforce your fair share。 It really doesn't matter as a sender。

 What you are trying to do to cheat。 It doesn't work because the route is going to say。

 here's your fair。 That's as much bandwidth as you get。

There's nothing the sender can do to cheat or get more than its' fair air。So you。

 the share you get doesn't depend on the ground trip time。 It doesn't depend on any of the you know。

 details of what rate adjustment scheme the send used and so on。It's just a simple calculation。

 local calculation by the goer。Based on the capacity it has。Disadvantages of vacuumcuuing。

 We didn't actually go into the details of that algorithm of how you simulate。

The fluid model or the bit by bit ground。 It is far more complex。As a bookkeeping mechanism。

 It's computationally more complex， you also have to routeers now have per flow queues or per flow state。

 You have to do this extra step of classification and determining what the deadlines are。

 So it is a much more complicated solution。 And as we'll see it。

Important to remember that vacuumcuing doesn't。Sove congestion control。

 It helps congestion control by providing isolation。 And we'll get to that in a minute。



![](img/146bf0454029d3cf36fb91fdc7713fe5_62.png)

So vacuumuing in practice， well， you know what you actually see， pure vacuumuing as I described it。

 and as the original paper described it， is computationally too expensive to implement at high speeds。

 but over the years there have been several approximations defined。In particular。

 one of them is called deficit round Robin。 We're not going to discuss it。

 but good to know it exists。 And so today， pretty much every router that you can hire end router that you can buy implements deficit round Robin。

 So it implements some form of fairqueuing。What it does not do is it does not implement poor flow fairequeuing。

 theres as far as I know no routeer that would have enough queuees that it could actually do fairqueuing for every TCP connection。

 So instead， there's some number of queuees， you know， the hundreds or so on。

 and what ISP will use it for is to provide isolation to certain VIP customers or certain classes of traffic。

So there's a certain class of traffic， let's see， particular prefixes that will have their own queue。

And that queue is guaranteed to have its share of the capacity。



![](img/146bf0454029d3cf36fb91fdc7713fe5_64.png)

Any questions？So vacuumuing in the big picture， the point I want you to remember is that vacuumcuuing does not eliminate congestion。

 It helps us manage congestion。 And it's best to see this with an example。

 So let's say I had this topology here。 And I had the green flow and the blue flow。

And they're sharing this  one gig per second link。In the network。

 what is fair queuing at that router going to do， It's going to enforce that the blue blue gets half a gig and green gets half a gig。

 Any excess is going to be dropped。 And there's nothing blue or green can do to get more than half a gig。

But that is all that that router can do。 It's enforcing its， the fair share for each flow。

What this router doesn't know and can't do anything about is the fact that， for example。

 if I look at the green flu further down its path。Its bottleneck link is 100 megabits per second。

So that green flow I just going to lose。 It's going to drop 400 Mbit per second。

 one hop down from this router that gave it half a gig per second。Is this example clear。

 So this character worked very hard to give the green floats fair air。

 and then the flow continued down and。

![](img/146bf0454029d3cf36fb91fdc7713fe5_66.png)

It's getting less that fair。So the point here to remember is。

 we're going to drop an additional 400 megabits per second。

The important takeaway is vacuumcuuing is not telling the sender at what rate it should be sending traffic。

 So we still need all of the kind of congestion detection and the data adaptation of the send。

This says is Meson， yeah。

![](img/146bf0454029d3cf36fb91fdc7713fe5_68.png)

Fers， yeah， hold onto that thought。 We get it。 So the benefit of fair queuing again， is gaziilience。

You cannot cheat it。 It's not subject to all these vags and ground trip times and so on。

 But it's not。 you can still get congestion。 You can still get packet drops。

 and senders still need to adapt。Discover and attack to their weight。

 So it's it's really in that list of problems。 that last one about senders cheating。

 That's the problem that fairqueuing is really very effectively solving， I would say。



![](img/146bf0454029d3cf36fb91fdc7713fe5_70.png)

One thing that should be mentioned。Perlo fairness。 you've probably SAT through this discussion thinking。

Would be great to have per flow fairness and to have the network enforce it， because。

 of course we would want per flow fairness。 You should know， you know。

 we're not going to go deep into this that Per flow fairness and fairness in general has long been a controversial goal on the Internet。

 And if you think about it， it's you know， the idea that every flow should get its fair share at some level is non intuitivetu right because what if I have8 flows and you have flow。

Why should I get more。Sharll than you， just because I opened up more connections。

 That's not quite fair。Or what if my flow is going over， know。

4 hops in the network and your flow is going over one hop。In some sense。

 one might argue that's not fair either， because I'm consuming bandwidth at four length and you're consuming bandwidth only at one link。

 So maybe you should be getting more of that one link than I am getting。Yet。

 another reason IP will tell you is I have certain customers that are willing to pay more。

 That's the kind of fairness I want， not this。Bal fairness。Though that particular one， there。

 there is something called weighted vacuumuing that could help。 But nonetheless。

 these are all reasons why many people will tell you， you know。I don't care about fairness。

 but what everyone cares about is isolation。The ability to make sure that in the worst case。

 you're not going to starve a particular floor or starve a particular customer。

 That is highly useful。What you should know about this that perflow fairness is not this perfect goal or perfect target to achieve necessarily。



![](img/146bf0454029d3cf36fb91fdc7713fe5_72.png)

Two other things I wanted to touch on with related to router assisted congestion control。

 One is this exactly what someone just brought up。 this idea of having more using routers to have more precise data adaptation。



![](img/146bf0454029d3cf36fb91fdc7713fe5_74.png)

And the idea here has actually exactly what was just brought up。

We just discussed how every router could compute the fair share that every float deserves。

 You' got this vacuumuing algorithm。 and you decide what fair share a particular flow has to。

I then also told you that actually， this isn't enough to solve the problem of congestion because flows still don't know which weight they should send at。

But one way to fix this is what if we said a packet carries a great field。

And a go inserts of lows fair share。In the bucket head。And so think of as the source sensor packet。

 That packet is traveling through the network， and every router looks at the fair share that that flow is going to get。

 And if it thinks it has a lower fair share， it overris it。

 So as the packet travels through and the app comes back。

 I learn what the minimum rate or my minimum fair share is along the entire path。

And then as a sender， you just send at that rate。Does this make intuitive sense to everyone。

 It's actually a pretty powerful idea if you could do it。

And so then the end host just set the sending rate to F。

 So this is kind of routers really working with sends to achieve congestion control。

 This is the basic idea behind a proposal called rate control protocol LCCP that came out of a group from Stanford And I'd like to show you one result on why LCCP was so interesting to people at the time。

 it was proposed。 came out 10 plus years ago。 But this finding has inspired many follow on efforts。

 So there's a lot going on in this slide。 So let me tell you what you should actually look at why access here。



![](img/146bf0454029d3cf36fb91fdc7713fe5_76.png)

ThisG is showing the flow completion time。 So this is the time when all the bys in the flow were successfully transmitted。

And on the X axis here， it's showing that flow completion time for a particular flow size。

 So if you wanted to read a point on this graph， you could say a flow size of 4000 with TCP LCCP。

 which is in red， had a flow completion time of I'm going to make this up 0250。3 or something。

In terms of time。 so low on this graph is good because it means I'm finishing。

 I'm seeing a shorter flow completion time。And ignore all the black points。

 That's a protocol called XP that we're not going to discuss。

But what this graph is showing is the flow completion time for TCP and green。

And comparing it to this。Proposal we just had for LCCP， which ist red。

And the only thing to take away here， you know， is what this graph was showing people was if you had something like LCCP。

 you could be doing as much as 10 X better than TCP。

And this was kind of a shock to many people about how much performance T CP is leaving on the table。

And so this is why this idea of router assisted congestion control learning your weight directly from routers。



![](img/146bf0454029d3cf36fb91fdc7713fe5_78.png)

Most people today will think it's a very powerful idea。 So skipping that slide， you know。

 where is LCCP， It's not something that's actually deployed into practice because very much like fairqueuing。

 it has a certain computational overhead。But this idea。

 and actually maybe something very LC CP like is being evaluated in data centers。

 So this is an idea that many folks in data centers continue to play with。

Last one of the Gto assisted congestion controls。 the ideas this is a very simple one and widely deployed is that you could use gos just to detect congestion。

 And so this is the idea behind a proposal we call ECN or explicit congestion notification。

And it's a very simple idea。 Let's say youre a single bit in the packet He。And when you pack it。

 hits a congested router， it just sets that bit。And when the gaze receives a data packet that has a congestion bit set or the ECN bit set。

It just the setback in the acknowledgeknowment of the centre。Is a basic idea clear。

I send it dear a packet。If there's a routeer that's congested， it sets a bit。

The sender learns about that bit。One bit of information， just a routeer saying I'm congested。

 And so the many， there's a design space here about exactly when should the routeer send the bit。

 you know， I it when your average Q utilization is over 75% or your standard deviation is something or the other。

 Were not going to worry about that。 Let every routeer decide when it thinks it's congested。

 set a bit。 And there's also a whole design space of how host should react when they get that congestion bit said。

The easiest way to react is to treat it as loss。 It's like an early indication of loss of congestion。

Advantages of having ECN， you don't confuse corruption with congestion。

It's an early indicator of congestion。 You can set the bit before you actually fill your cues。

 So this is another way of avoiding large delays is to use something like E CN。

 And unlike fairqueuing and unlike R CP， this is a very lightweight mechanism。

It's just a about just flipping a bit in the packet header。So ECN is widely implemented in routers。

 it's also quite widely used， particularly in data center congestion control algorithms。

 Microsoft Azure， for example， uses ECN for its congestion control within the data center。



![](img/146bf0454029d3cf36fb91fdc7713fe5_80.png)

One final crazy idea， just to。Share， so you would know it exists。

 Is this notion of congestion based charging。The idea has not really It's not a technical change so much as it's a change in business model。

 The idea was， what if we used EN as congestion markers and then users or senders have to pay more depending on the number of EN bits。

That they get back。The idea here is the number of EN bits you get back is a direct indicator of how much you as a sender are congesesting the network。

 And so if you pay in proportion。To that， the level of congestion you've caused。

 then that's actually fair。And it also has a way of naturally regulating demand。 So in this。

 the appealing thing about this is a elegant。Intellectual idea。

 There's no debate of water flow is or what far is。

 It does require an entirely new kind of business model around how the Internet works。

 But theoretically， you can prove that， you know， if you have a notion of network utility as user happiness in the sense of。

As a user， what maximizes your happiness as a combination of the performance you're getting and the amount of money you're paying？

Then actually， congestion pricing is optimal that if you do congestion pricing。

 you maximize user happiness。

![](img/146bf0454029d3cf36fb91fdc7713fe5_82.png)

Or the network utility。We're not going to。 So recap routeer assisted congestion control fairqueuing is routers enforcing per flow fairness。

 LCCP is routers informing end host of their fair share。

ECcN is just routes informing end host of whether they're congested or not。

 not of the actual fair share。And congestion pricing is the idea that users pay based on congestion。



![](img/146bf0454029d3cf36fb91fdc7713fe5_84.png)

Pulling all of that together， you know， perspective on goer assisted congestion control as you saw from that RCP graph。

 highly effective， can actually be optimal in many ways， but the deployment is more challenging。

 We need to upgrade routeers。Some of these mechanisms are heavyweight to actually put in routers。

 but you know。Computational technology and algorithms are improving every day。

 So maybe the day will come。And some of them actually acquire deployment at every router。

 which can be difficult to deploy on the Internet。That said。

 all of these constraints are much less of a concern in data centers。

 So many of these ideas are actually still under investigation or have been adopted in some cases in data centers。



![](img/146bf0454029d3cf36fb91fdc7713fe5_86.png)

So finally wrapping all of this up perspective onpe control， it's not perfect。 It's a little ad hoc。

 You know， there are certain rules that you say y3， why not 4。

 Why do you start with an initial window of 10， So there are certain ad hoc choices。

 It is deeply practical and deployable。 The basic idea that drove Van Jacobson's thinking remains and has held。

And it's good enough to have raised the bar on deployment for more optimal approaches。 So。

 for example， if I queuing on paper might seem like the perfect thing to go deploy。

But until you really need it， no one's going to go and put that level of complexity into routes。

And finally， when we get to data centers， we'll revisit some of these ideas because a lot of the constraints around。

 you know， you can't deploy all routeers or you can't have all centers do the same thing go away in data centers where you have one operator kind of controlling the end to end picture。

Without any questions？

![](img/146bf0454029d3cf36fb91fdc7713fe5_88.png)

If not， next topic will be the TN S Muphy's lecturecs。

 Well be releasing those recordings and remember no in person lecture on Thursday。Thank you。



![](img/146bf0454029d3cf36fb91fdc7713fe5_90.png)