# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P17：-16- Congestion Control TCP Design.2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Good morning everyone and welcome to our second lecture on the topic of congestion control If you remember this is a topic that we started last time where the last time we talked about at length about you know what is the problem of congestion control。

 Why is it important that we address it and then we also talked about kind of the broader space for this congestion control solutions as well as identified kind of one slice through the space of design options that we said would be how TCP does congestion control。

And again just recall that slice that we identified was based on three characteristics。

 the first was that we were going to look at solutions that were host based congestion control This means that the sender in particular is on its own figuring out what rate it should send traffic at without any assistance from goers along the path。

The second aspect we said was that the manner in which we implement congestion control is going to be to have the source dynamically and constantly discover and adapt the rate at which it's sending traffic into the network。

And the third dimension was we said that in order to know whether the network is congested or not。

 the sender was going to be looking at packet loss as an indicator of congestion。

 and we talked about the pros and cons of loss as well as other options like delay。

 but we said going forward we're going to be kind of honing in on loss as an indicator of congestion。

And so the plan for today is to you know kind of look at how the same approach that we've discussed last time。

 but how TCP implements that approach， so there's no new algorithms or you know design options really that we consider its really deep dive into one particular way of implementing that design option that we identified the last time around。



![](img/38c9eac229dafc89f7933b637fde605c_1.png)

And so the plan for the lecture is， I'm going to start by actually reviewing how TCP's window based operation proceeds and how it does reliability in this kind of sliding window paradigm。

And part of why I'm doing that is because when we talked about TCP reliability。

 we didn't really step through in detail how TCP reliability works， so we're going to do that today。

 even though the basic building blocks we step through we didn't really step through the TCP design for reliability so we'll start there the view how the windowbased operation works and then we'll talk about how that operation of that design is extended to do congestion control and as you'll see the way in which TCP does congestion control is very intertwined with how it does reliability for better or for worse that is how TCP is implemented and so it's very hard to tease apart how TCP does congestion control without also actually talking about how we do reliability。



![](img/38c9eac229dafc89f7933b637fde605c_3.png)

So with that just a quick review。Again， as we've said many times。

 the sendo maintains a window of packets and flight。

 these are packets that it has transmitted but hasn't yet received an acknowledgement for。

And we said this window size is based or picked to balance three goals。

 so this is the actual value of the window size。And those three goals were to fill the pipe to avoid overloading the receiver receiver。

 which we call flow control and to avoid overloading links in the network。

 which is today's topic of congestion control。We first said that the last goal subsumes the first one。

 and so really we just have to worry about flow control and congestion control。

In terms of implementation， we said that flow control is achieved by having the send maintain what we called was the advertised window。

I'm now telling you that our advertised window also sometimes called receiver window and the typical parameter that we use to denote this value of the window that the sender learns is Rwind。

 which stands for receiver window so advertised window receiver window they mean exactly the same thing the parameter R windd refers to either of those。

And then to implement congestion control， we have an additional parameter。

 which is this congestion window or sea wind。

![](img/38c9eac229dafc89f7933b637fde605c_5.png)

I'm going to repeat this one more time because you know all these windows can be confusing congestion window or sea wind is how many bytes the sender can put into the network without fear of overloading the links in the network This is computed or the value for sea wind is computed by the sender using a congestion control algorithm and that's what we're going to talk about in the rest of this lecture。

The flow control window or our wind is how many bys the sender can receive without overflowing the receiver's buffers。

And this was implemented very simply by having the receiver tell the sender what its advertised window value should be。

And it does so by communicating that value through the x。And then finally， at the send side。

 the true window size that it uses is the minimum of sea wind and our wind， that's intuitive， I hope。

For this lecture we're going to assume that flow control is not the bottleneck that it's instead sea wind so we're going to assume our wind is much greater than sea wind and so everything we're talking about here the sender's window size is going to be determined by sea wind in practice this is also fairly true which is typically the sender's rate is determined by its congestion window but not always and so we have to remember to keep both of those values in mind。



![](img/38c9eac229dafc89f7933b637fde605c_7.png)

Another note is recall that TCP operates on byte streams。

 so we said all of the accounting that TCP does in terms of sequence numbers。

 acknowledgements and so on are in terms of an offset in the by stream that the senders was sending the receiver。

In real implementations， sea windd will be maintained in bytes。

 it's the number of bytes that the sender can put into the network。For our convenience。

 this lecture we're going to talk about sea wind in terms of units of MSS so MSS again a reminder was the maximum segment size。

 This was the maximum number of bytes of data that one TB packet could carry in its payload so roughly intuitively you can think of you know units of MSS as being roughly the same as packets in terms of the discussion we're going to have in this class but remember that real implementations and also problems on the exams and all we would be asking you to do sea wind in terms of bytes。



![](img/38c9eac229dafc89f7933b637fde605c_9.png)

So I'd like to start with a quick review of TCP reliability and in particular this notion of a sliding window and how that protocol works and so going back a few lectures we said that a sender maintains a sliding window of w contiguous bytes and so in this figure here of my window at the sender starts at a byte offset of I and my window size is w then this range of bytes from I to I plus w that constitutes the sender's current window。

What this means is that any bytes less or you know lower than the left hand side of this window。

 less than I， the sender has already sent them。 the receiver has acted them and the sender has received the ae。

 So these are bytes that the sender understands have been reliably transferred。

 We're kind of we're done with these bys， the sender is free to release the buffer space associated with those bytes。

On the other hand， the bytes above I WO over the right hand side of the window。

 these are bys that the centerer has never yet transmitted and it's not allowed to transmit it either given the rules of the sliding window protocol。

And so the sender is only allowed to transmit this range of bytes that are between I to I+ w。

 whether they've been act or not， we don't know at this point。In addition。

 the sender we said associates a single timer that's associated with the left hand side of the window。

 So if you remember we said that TCP， you don't have a timer per packet or a timer per by offset instead we just have one timer associated with the left hand side。

And when that timer files or you have a timeout， then the sender is going to retransmit the bys。

 though the set of bytes starting at the offset of I。

And so that was the basic sender side behavior on the receiver side。

 we said that TCP reliability implements cumulative acknowledgements。

 so it's going to acknowledge the next expected byte and we said that the sender counts the number of duplicate acts it has received。

We also said that when the sender has received a certain number of duplicate acts。

 which we said was three。It was going to retransmit again。

 from the left hand side or the first set of bys that I'm missing at the receiver。

I don't think we introduced this term before this process of retransmitting when you receive three acts。

 that is called fast retransmit so this mechanism of I'm going to count the number of duplicate acts if I receive three acts I'm going to treat it as a loss and retransmit。

 we call that fast retransmit。If the sender receives an acknowledgement for new data。

 so let's say that the receiver is saying that my next expected byte is G for some J greater than I。

Then what the sender is going to do is it's going to slide the window right。

 so now the left hand side of the window starts at J J is the first byte that the sender can send and it can send up to J plus w。

And this is where the kind of sliding window analogy comes from every time you get a new act。

 you slide your window guide。And it's all， remember， always W contiguous bytes that the send consent。

So that was a quick view of how TCP reliability works and this notion of a sliding window protocol。



![](img/38c9eac229dafc89f7933b637fde605c_11.png)

Moving forward， what we're going to be looking at is how we extend TCP and that sliding window design in order to incorporate congestion control。

And so step one， as we've mentioned， is we add a parameter that we call the congestion window or sea wind。

And beyond that， the general idea is going to be that we adapt sea wind based on the co congestion level。

And you know how should we adapt C if you recall from last lecture we were talking about the sender adapting its transmission rates what you said when you addly increase and you increase your rate。

 when you multiplicatively decrease you decrease your rate。

So what is that rate and how does TCP do it in TCP。

 the sender's rate is simply the congestion window divided by the ground trip time。😊。

This should I hope make sense and again this is ignoring the receiver window what is the rate after all。

 The rate is just how many bits you can send or how many bits you're sending per unit time right 10 megabits per second。

 100 megabits per second， whatever it's bits per unit time。😊，In TCP， the sender。

 if you think about it， is sending a sea wind worth of bites。

And it's sending se worth of bytes on the timescale of a round trip time right that's how many bytes I can as a sender I can put into the network and then in a round trip time I will start receiving acknowledgements back that will allow me to send more bytes。

But so the sends great in TCP language or in TCP parameters is simply sea wind。

That's the in terms of number of bytes divided by the ground trip time， which is in units of time。

 and so that's giving us kind of the bits per second or the sender's rate。

And so if the center rate is sea wind divided by the round trip time。

 then the way in which TCP is going to adjust its rate is simply by adjusting this parameter of sea wind every round trip time。

And when it adapts sea wind every round trip time， effectively。

 this send is adapting its rate exactly like we talked about in the last lecture。



![](img/38c9eac229dafc89f7933b637fde605c_13.png)

Okay， so again， we're calling， you know， last time we said that the congestion control had three basic components to its design。

 There was how you detect congestion， which we were going to say was going to be loss based。

There's how you discover your initial rate for which we had slow start。

 Remember this idea of you start small and then you exponentially increase。And lastly， how you adapt。

To congestion， your weight to congestion， these increased decrease rules。

 and we talked last time at length about why AIMDO additive increase multiplicative decrease is the correct approach。

So what follows in all of our slides is really how TCP implements the above solutions。

And the theme you're going to see in how TCP does this is that all updates to sea wind because remember we said adapting your weight means updating sea wind。

 all updates to sea wind are going to be driven by receiving acknowledgements so if you think of this in terms of kind of event programming。

 your events here is the arrival of acknowledgements。And of course。

 timeouts as being you know the absence of acknowledgements， but other than timeouts。

 all other updates are going to be based on receivingce and acknowledgement。



![](img/38c9eac229dafc89f7933b637fde605c_15.png)

We call this ac clocking and this idea of a clocking and that TCP exhibits ac clocking behavior is something you'll hear quite commonly when you look into talk to people who do networking。

And what do we mean by act talking， I just want to take a couple slides to elaborate on that。

The idea is that when you receive a new acknowledgement。

 we slide our window forward and the process of sliding the window allows us to send some new data into the network。

And so we end up with this behavior where when I get a new acknowledgement。

 I'm allowed to send new data。 so I put new data in。 And so in some sense。

 you can think of it as the transmission of data。By the centers clocked by the arrivalival of acknowledgeknowledments。

And that doing so has some nice properties that we I'm going to get to that with an example in a minute。

 but in a nutshell the benefit of doing a clocking is that the sender ends up kind of selfpacing or it paces its transmissions at exactly the rate of available bandwidth。

😊，So whatever bandwidth is available in the network， the sender transmits at that rate。

But it's also transmitting at that rate in a very paced manner or in a non bursty manner。



![](img/38c9eac229dafc89f7933b637fde605c_17.png)

So let's look at a figure， I think it's easier to understand when you kind of see it visually and in action。

So let's take here in this example， a very simple scenario in which I have a source in a destination。

😊，And they have three links along the path between the the two and the bottleneck link is 1 gigB per second。

 which is。10 x lower than the other two links。And for now， for this example。

 just to demo at clocking， we don't even have to worry about competing flows or you know congestion along the path。

 let's just say the source has the entire path to itself going to the destination。

And let's look at this in what our old pipe view of the network where the width of the pipe denotes the capacity of that link。

 and so here we have the skinny pipe is correspond to the one gigabit per second bandwidth。

And I'm also splitting the forward direction each direction of that part。

 so the forward direction is on top and then acknowledgements travel in the reverse direction on the bottom。

And I' would say that the source had a burst of packets to send。 and so it sends a burst of packets。

 It's on this high bandwidth link。 So those packets are traveling back to back in a burst。

They travel through that link until they arrive at a bottleneck。

And now they're arriving way too fast for that bottleneck。

 so though that burst of packets is going to be cud。At that bottleneck link。

And then the bottleneck link is going to service those packets or drain the queue at that much lower rate of that bottleneck link。

 And so what we see is that those packets that were cued are now being transmitted over the bottleneck link。

 And as they travel the bottleneck， they're kind of being spread out simply because the transmission time is lower on that bottleneck link。

 And so it takes。In our view of this pipe capacity view。

 it takes up more time and more space on the bottleneck link。

And so what happens when those packets get onto the next link is that you again have。

 you know it's a high bandwidth link and so the packets are looking skinny again。

 but they maintain the space between them， which is the space that was set by the bottleneck link。

 so the gap now between these packets。Corresponds to the gap that was introduced by the bottleneck link。

Again， this should make sense we effectively have a 1 gigabit per second link feeding into a 10 gigabit per second link。

 so you're going to have these idle times between packets。

So these packets now arrive at the destination and what is the destination going to do。

 it's going to pick up each of these packets and it's going to send an acknowledgement。

 So when a packet arrives， pick it up。Send out an acknowledment。

And so when we look at the acknowledgments as they are travelling back。

 what we see is that they maintain that spread。Between them or the gap between these acknowledgements is kind of determined by that bottleneck link on the forward direction when data packets are going from the source to the destination。

And that gap is going to be maintained， let's say on the return path and so here in this figure you know the only reason that the acts are not occupying the full bottleneck link is simply because acknowledgements have fewer bytes in them than the data packet。

But the important part here is to notice that the acknowledgeknowledments in the gap between acknowledgeledments or the spacing between acknowledgements。

When it arrives back at the source is reflective of the bottleneck capacity on the forward path。

And so in a clocking behavior， what happens is now what is the source doing。

 it receives an acknowledgement and it puts in a new data packet on the network。😊。

And so now after one trip， one ground trip time， if you look at the weight at which。

Or the pattern of the sender sending putting in new data packets into the network。

 we see that these new packets are kind of cloed or they're maintaining the spread。

That was determined by the bottleneck link。 so the source is no longer sending these buss。

Of packets instead of sending them out nicely paste。And so in steady state。

 what we would expect to see is something that looks， you know visually， none of this is to scale。

 obviously， but visually what we would see is that were fully the send is fully occupying the available bandwidth as determined by that bottleneck link。

But it's sending out these packets paste in such a way that we require no queuing at that bottleneck link。

So the sender is sending at an ideal rate。But we're not incurring any queuing。

 And so the reason people like this is now， you know， it kind of gets rid of some of the burstiness。

😊，And remember that bursty traffic is what sometimes causes these transient queuing。

 and sometimes you end up losing a packet when multiple bursts arrive at the same time。

That's much less likely to have happen if you have this kind of self piecing or these nicely spread out packets arriving。



![](img/38c9eac229dafc89f7933b637fde605c_19.png)

Okay， so a bit of a direction。 But that is， I wanted you to have a mental picture of what a clocking is and why it's useful。

 Okay， so that was a clocking。 And as you'll see。All of TCP's implementation is kind of geared around this notion of clocking out data packets by using the rate at which acknowledgements are coming in。

😊，And you going back to something I said in the last lecture where I talked about Van Jacobsson and Kagel's paper on congestion control and how they had in their head。

 this model of the internet or congestion as a feedback control system and this principle that it should or this notion that any congestion control solution should maintain this kind of conservation principle。

 where the notion was that in steady state when you're going at the right rate。

The sender should maintain conservation in the sense that it pulls out one packet from the network。

 it should add， then only then can it add another packet into the network so we're conserving the number of packets currently in the network。

And at clocking is the very elegant way by which they achieve that kind of conservation。

 And I pick up an act， I put a new data packet in。And as long as I'm being driven by the weight at which I'm receiving Xs。

 then I'm very naturally。Letting the network tell me at what rate I can put back its back。



![](img/38c9eac229dafc89f7933b637fde605c_21.png)

Okay， enough for that clocking going back to a question。

 so as we said we had three components to the design， detecting loss。

Discovering an initial rate and adapting that rate。 So how we detect how TCP are the detects slot。

 we've already covered this two ways either you can have three duplicate act。

This typically indicates an isolated loss。Or the second mechanism was that we would have a timeout。

 which typically indicates a fairly severe network congestion where you've lost several packets in the network。



![](img/38c9eac229dafc89f7933b637fde605c_23.png)

The second design component was this question of how you discover your initial rate and we said we were going to do this with slow start and again。

 the slow start basic idea was you started a slow rate and then you increase your rate exponentially until you experience loss。

So in TCP， how TCP implements slow Start is， it's going to start with a very small sea of one MSS worth of data。

So this means that the starting rate for TCP center is MSS overground trip time。

 So it's really sending one packet every ground trip time。 This is a very low rate。

And then TCP is going to double its congestion window。

 the sea wind parameter every ground trip time until the first loss。

How is CCP actually going to implement this going back to our act clocking notion is that every time it receives an acknowledgement。

 it's going to add one MSS to the sea wind。Why does this end up doubling sea wind over the course of a ground trip time if you think about it。

 it's because every time we were saying before that every time you receive an acknowledgement you've taken one packet out of the network and so you can put one new packet into the network。

That's what we were doing when we wanted to maintain the same the window size。

 not change the window size。If instead now I say every time I pull out an acknowledgement。

 I can send two packets into the network。Then I'm effectively doubling the number of packets I'm putting into the network every round trip time。

 and so I'm doubling my sea windd。

![](img/38c9eac229dafc89f7933b637fde605c_25.png)

Let's see it in action， Okay， so the goal again is to double your sea wind every ground trip time and we're saying that the way you implement this is you add plus one to your sea wind every time you receive an acknowledgement。

Okay，So let's say the soul started with this event of one， and it sent one packet。

When it receives an acknowledgement， it increases7 by one， so it's not two。

 so it gets to send two packets because there were no other packets in flight。

When you receive the acknowledgement for the second packet， the sea wind is now three。

And so the source is allowed to send two additional packets in a white two because you're allowed to have three outstanding packets。

 you just received one of the previous two， so you only had one outstanding packet left and so you can add two new packets into the network。

So the source will then send those two packets。When the acknowledgement for D3 comes in。

 it's going to increase even to 4。It's going to see that it only has two packets already in flight。

 So it's allowed to send plus two packets。 And so now you have kind of these four packets that are all currently in flight and it'll go on and so on and so forth。

 but it add one to its sea every time。 And so if you look at this。

 you see that you know in our first round trip time。

 your see was one in the second round trip time was two in the third， it was four。

Next one will be 8 and so on。But notice that it isn't the way this is implemented。

 We aren't kind of we don't have these abrup jumps or doubling in sea wind where in one ground tripp time。

 let's say my sea wind was 8。 And then in the next round tripp time it was 16。

 Then I suddenly dumped8 packets into the network。 That's not what TCP is doing。

It is doubling its ground trip time over the course of a go trip time。

 but it's sending out those additional packets spaced out as the acts come in。

And so there isn't this overly bursty behavior， again， at clocking in action。



![](img/38c9eac229dafc89f7933b637fde605c_27.png)

Next is how TCP implements slow start so just to continue so what we said so far is that we are doubling the sea wind every round trip time until you experience loss but remember we said that the goal of slow start is to discover you know a good initial rate and so far we've just said oh we're doubling our rate every round trip time where is that good initial rate that good initial rate is remembered or maintained by a new parameter that I'm introducing now which we call the slow start threshold parameter its denoted as SS threshold and this is the parameter that's going to remember what we call a good rate which is the last safe rate that the sender had experienced。

Okay， so the way SS crashsh is set is that remember。

 we were doubling our sea wind until we experienced packet loss。When we experience packet loss。

 we say that we set SS fresh to be half of the current congestion window。

What's the rationale behind this， You know， this should make complete sense。

 but here's the the reasoning。 Let's say I was increasing my sea wind。 and it was at 4。

 and I had no loss。 So over the next round trip time， I increased it to 8。 and that's still no loss。

 So next round tripp time， I increased it to 16。Still no loss。 Yet another round trip time。

 I increased it to 32， let's say。And now I experienced a loss。So what does that tell me as a send。

 it does me that 32 is not a good weight because I'm experiencing loss I've congested the network。

But I also know that at 16， I was fine。At 16， I had not experienced any congestion。

I didn't have any packet loss。 So 16 is actually a good rate。

 It's a known safe rate at which the sender can send。And so SS s is going to remember7 by2。

 which would be 32 by 2， it's going to remember that rate of 16 as being a good rate。

And we'll see when this plays out， but you know just as a preview。

 slow start the very first at the beginning of time。

 you're going to set your SS S to be a very high value。

And the center is going to start with this even of one， and it's going to double it。

Until we experience loss。And then it's going to set SS F to be half of the congestion window。

The next time the sender ends up having to do slow start and we'll get in a few slides。

 we'll get into when that is。 But let's just say the next time that the sender finds itself doing slow start。

 it's going to again start with a c of one。And it's going to double its window size。

Until it hits as S th。So it's going to slow start up to the SS F value。

And once it reaches the SS crash value， it's going to stop doing slow start because it's going to say if I go beyond this rate。

 there's a possibility that I'm going to overshoot my capacity and cause loss。

So instead I'm going to very quickly exponentially ramp up to SSC。

 and then I'm going to be more cautious about how I increase my rate。

And we'll get to that in a few slides from now。

![](img/38c9eac229dafc89f7933b637fde605c_29.png)

So the last part of the design of how TCP works is that this question of how adapt the。

 how you adapt your rate to congestion， I'm sorry， and we said that the way in which we're going to do that is AIMD。

So our next question is， how does TCP implement AIMD？

So let's walk through that the first part of how you do AIMD is your additive increase。

This is when you have no loss， you additively increase or you add some constant to your sea wind in TCP。

 this is just one MSS everyground trip time so in TCP there's no loss。

The sender is going to increase its sea wind by one MSS every round trip time。

And then the other part of AIMD is the multiplicative decrease and the way TCP does this is it says when I detect a loss via threedup x。

 then you're going to halve your congestion window so multiplicative decrease with a factor of two。

 that's what TCP does。You might be thinking， what about timeouts？When you have timeouts。

 what TCP is going to do is it's actually going to exit AIM D。

 So what TCP does on timeouts is to say。The rate I have is bad。

 This is not a I I don't actually know whether I'm anywhere close to a good weight。

 So it's going to do the conservative thing and we start the learning process。

 And so we'll do that in a few slides from now。

![](img/38c9eac229dafc89f7933b637fde605c_31.png)

So how does TCP implement additive increase， So we said that we want to increase sea wind by one MSS every ground trip time。

The way this is going to be implemented is you over one ground trip time we get a large number of acknowledgegments and we only want to increase by one MSS over that entire window or over all of those aknowgments and so in order to implement this in an at clock manner we're going to add a fraction of an MSS every time we receive an act。

So more specifically， when a TCP center receives an act， and here I'm assuming an act for new data。

 it's going to increase its sea wind by 1 over sea wind。

The one over sea1 is in terms of units of MSS。 so if you wanted to think about this correctly in terms of bytes。

 you'd be increasing it as per this gray equation here that I added I just wanted to put it here。

 you know we've been doing all our calculations in terms of MSS units of MSS。

 this is the one place where I wanted to put in bytes because this is the one place where I found。

It's easy to get confused and so why is it what this equation says。

 So if you take one over sea wind and you say how many I want to do that calculation in terms of bytes。

The one here corresponds to one MSS， which is why we have the first term MSS here。

And then we want to increase by a fraction over the number every time we receive an a。

 we want to increase by one over MSS rate， so we want to divide this by the number of as that we would expect and the number of acts that you would expect is the sea that's the total number of bytes interval around trip time。

Divided by the MS， which is how many bytes you can fit in any one particular packet。

That's going to be the number of acts you receive。And so we would have divided to get the fraction that we have to add。

Each time you receive an a， we would divide MSS by the number of acts。

 which means we would divide MSS by Cwe over MSS， which is why we get this term here where we are multiplying by MSS over seawin。

I hope that was clear。So moving on。After the reason this works is because after a full window or after we've received sea wind worth of packets。

 we would have increased。ASed by exactly one MSS。And so if we're increasing over the course of an entire sea when we are increasing by one MSS。

😊，Remember that we send a even over the period of a long trip time。

So that means we've increased by one MSS pull down trip time。

 which is exactly the behavior we were hoping for。

![](img/38c9eac229dafc89f7933b637fde605c_33.png)

So how does CCP implement multiplicative decrease， this is very straightforward when you receive your third two pack。

 we simply cut the congestion window by two。And then lastly， when we have a timeout。

 how does DCPU react， the rationale here again， as I alluded to earlier， is you know。

 when you get a timeout， you get a timeout when you've lost multiple packets in a window。

And this tells the sender that the current congestion window might be quite incorrect or quite far off from where it needs to be。

 and there's multiple reasons this might be the case it could be you had some other competing flows that suddenly came up。

 it could be that you had a routing change and your bottleneck link is no longer the same any number of reasons the send doesn't know all it knows is that it lost a whole bunch of packets and so it's unsure whether the current value it has for sea wind is any good。

And so what TCP is going to do or the particular design choice that TCP decided to do was that to say I'm going to basically I'm going to throw this c value out and I'm going to restart。

 so I'm going to rediscover a good weight from scratch。It didnn't have to be implemented this way。

 this might have been overly conservative It's。Particularly way that TCP。

 the design decision TCP made is errving on the side of caution。And so on time out。

 what TCP is going to do is retransm that first missing packet， this is what we always do。

It's going to set S cl to be half of the current congestion window。 Remember。

 because this is the congestion window that has caused。Pretty severe loss。

 so it's going to go remember half of that rate。As being the value of SS threshold or safe rate。

It's then going to set sea all the way down to one MSS， so we're starting from scratch again。

And it's going to enter close start mode。So send us back at a place where it has one MSS and it's doubling or going through slow startud。



![](img/38c9eac229dafc89f7933b637fde605c_35.png)

Doubling its sea wind every long trip time。And now this is where SSS comes into place is to ask yourself when does a sender stop doing slow start and start doing additive increase again？

And that is determined by this parameter， as S crash。

So when your congestion window exceeds your SS fresh value。

 that is when the sender is going to switch from increasing its rate as per slow start to this more gentle additive increase that we have in AIMD。

And let me repeat that one more time。What is the sender going to do in this case。

 the sender has started out with a c wind of1。 It's going to do this very exponential increase of slow starts。

 it's going to double its sea wind every long trip time。Until it reaches us S square。

At S s it says I knew this was a safe weight。 if I double it one more time。

 there's a very good chance I'm going to cause packet drops or cause congestion。

And so instead I'm going to stop doubling my congestion window。

 I'm going to do something much less aggressive， which is additive increase。

And so that's when the sender is exiting this slow start behavior and starting to enter this AIMD behavior。



![](img/38c9eac229dafc89f7933b637fde605c_37.png)

So let's summarize the rules we've discussed so far。

 the summary of the decreased rules are the ways in which TCP updates its parameters。

To decrease its weight is that it's going to cut its congestion window in half when it receives three duplicate acts。

 that means any loss that's detected by doing receiving three duplicate act。

It's going to cut its congestion window all the way down to one when it was on a timeout， so one MSS。

But there's no scenario under which it's going to drop its congestion window below one。

 so congestion window minimum is always one MSS if you find yourself tempted on an exam to have a congestion window of 0。

1 MSS or 0。5 MS， don't do that。Some you have the increased rules。

 when you're in the scroll start phase， you increase even by one MSS every time you see when you act。

Net effect is you w your see when long trip time。When you're in the AIMD phase。

 you increase know by a fraction of the MSS for every accuracy and so in effect。

Over the course of a ground trip time when you've sent a full se worth of data。

 you would have increased your se by one MSS full ground trip time。So with that at this by now。

 let's actually switch to talking about。We're not switching so we're continuing with how TCP does congestion control。

 but we're going to look at it from a much more implementation。

 almost pseudocode centric view of how TCP does congestion control one of the things that's nice about doing this is you know your second project is going to be implementing TCP reliability and how you're actually going to implement everything we've talked about with sliding windows do back timeouts and so on in order to implement reliability what we're going to be talking about now is not part of the project。

 but this is really the lines of code in some sense that you could add to your project in order to have implemented congestion control So if you're looking for a little coding project over the break consider extending project to do congestion control。

And as I go forward， again， we are referring to see wind units of MSS， and I'm going to be using red。

 I think and hope I've done this consistently， but I'm going to be using red。

To denote the changes you have to make to TCP's reliability protocol in order to implement congetion control。

So with that， the implementation the state at the sender。

 there are four basic forms of state we the sender maintains to implement。

 not just congestion control， actually this is liability and congestion control in some sense。



![](img/38c9eac229dafc89f7933b637fde605c_39.png)

The congestion window， which we see， which we initialized to1 MSS SS cache。

 which at the beginning of time， we initialized to a very large constant。

This and then as before we things we had for reliability。

 a duac counter initialize to0 and then timers again， as we had before for reliability。

The events that you have to react to at the send， there's X for new data。Dups。

 which are duplicate acknowledgements for old data and timeouts。In terms of the receiver。

 exactly the same behavior as we've talked about so far。

 that there's no change for congestion control， you just send acknowledgements and specifically intrinsic cumulative aments just like before。



![](img/38c9eac229dafc89f7933b637fde605c_41.png)

Let's step through this in terms of the events and how the center has to react to them。

So a first event is an acknowledgement for new data。

If the center receives an acknowledgement for new data while it is in the slow start mode of operating。

 then the only update it has to make is to say sea windd is equal to sea wind plus1 mS so wind you receive sea wind packets per RTT so after one RTT if you had no drops your sea windd would have effectively doubled。

And so this is the slow start phase of TCP congestion control。

 So when we get to the TCP state tiggger， this is the slow start state。

If the gaze sorry the sender was not in slow start。

 then that means it's doing additive increase and so then the update is C wind is equal to C plus1 over C。

This was reacting a fraction of one MSS。To on every act arrival。Since we receive Sewin。

Packets per ground trip time after one ground trip time， we would have invoked this rule sea times。

 and so we would have increased the sea wind by one。This phase and I'm introducing a new term here。

 this phase we call is the congestion avoidance phase okay this is what we've been calling additive increase in terms of the TCP state diagram that we're going to get to in a few slides。

 this is what we call congestion avoidance。And then in addition to these two rules。

 everything else is the usual， meaning what we've talked about doing for liability。

 you reset your timers， you reset your twoac counter because this is a new acknowledgement。

 you send you data packets if your see allows it and so on。



![](img/38c9eac229dafc89f7933b637fde605c_43.png)

So the next event is a timeout， this is very simple when you get a timeout we set SS flash to be the current congestion window divided by two this is for all the reasons we discussed just now。

You then set your sea wind all the way down to one。And you re transplant packets and other stuff。

 like always。So the third event is when you receive a duplicate duplicate a or Dac。

So when you receive a duac， you increment your duac counter by one。

And if your do back counter is equal to three。Then you enter fast speed transmit everything up to this point is exactly what we've talked about doing for。

The change now is you're going to set SSre to be equal to sea wind by 2。Okay， because again。

 we've detected a loss。Where we know this is no longer a safe weight。

 so we set SS s to half the current congestion window。In this case。

 we also set the congestion window to be half。Okay， so we do c1 by 2。

But no less than never less than one， right so take the ceiling of those。

And you re transmitm the packet and so on， as always。

What this is doing here is we're saying we have an isolated loss。

So we're going to do AIMD and this is the multiplicative decrease phase of AM andD。

So you're doing AIMD after a pho transmission。

![](img/38c9eac229dafc89f7933b637fde605c_45.png)

I'm going to pause here， I can't actually ask if you have any questions。

 but we'll have a chance to do questions in our next lecture。So where does that bring us。

 I want to now go back to last lecture we talked about TCP has a saw tooth pattern。

 I want to go back to that and。Make sure that you're now following that so too in the context of how TCP is actually updating all these parameters and so on。

so what are we showing here， we're plotting the current window slide at the send on the Y axis over time as the TCP connection proceeds on the X axis。

And so we see this initial exponential curve， this is slow start。

And then we see these two events where we dropped our window size in half。

This was caused by fast wheat transmission。How do we know it was caused by fast heat transmission？

We know because if we'd had a timeout versus just3 two packs telling us we had a loss。

 we would have dropped the congestion window all the way down to one。

The fact that we cut it in half tells us this was isolated loss。And then again。

 we have this additive increase or linear increase phase。After we do a multiplicative decrease。

And then now here， let's say we have a timeout。So what you should expect to see is your congestion window drops all the way to one。

That is what I'm showing here。We're also going to remember SSCsh as being set to half of that congestion window。

And now remember we dropped to one and as for the TCP rules we've discussed today。

 we're going to restart in slow Start。Oh sorry， not restart and slow start， the sender is going to。

Again， once again， go back to doing slow start。And it's going to do slow start until its current value of C wind crosses this value we've remembered for SS slash。

At which point is going to switch to doing linear increase again。Okay。

 so this is the at this point of。Understood mostly the。

 or we've seen most of the TCP sorted behavior， which is goes back and forth between being this exponential growth of slow start。

Dropping your congestion window either by half or all the way to one。

 and then ramping up doing either a linear increase or by a restarting slow start。Yeah。



![](img/38c9eac229dafc89f7933b637fde605c_47.png)

So we have one final phase in how TCP does congestion control that we need to discuss and that's something we call fast recovery and fast recovery is an optimization really to the congestion control logic and algorithm that we've discussed so far and what it's trying to optimize or the problem it's really trying to address is this issue that arises in congestion avoidance where when you have really a single packet drop in a fairly large window and congestion avoidance this process of additive increase and having cut your window by half is really too slow to recover it stops the center from sending as fast as it could have and we're going to do a detailed example to show what the problem here is it is an optimization it is a bit of a hack at some level but it's also kind of cute and effective I would say so fun to walk through we're going let me walk through an example and then come back and recap at a high level what the issue was and this example again we're counting。



![](img/38c9eac229dafc89f7933b637fde605c_49.png)

ets not bys， you can always just multiply by the MSS to obtain the same example。

 but working in terms of bys。And in this example， we're going to consider a TCP connection in which we're going to say that the congestion window at the sender was said to be10 packets or had achieved a size of10 packets and we're going to say that the last act that the send of the was for packet 101 so this is the next packet it's expecting is a packet that has a sequence number of 101。

And so currently the sender has 10 packets in flight， that's packets 101 to 110。

And the scenario we're going to walk through is where packet 101 is dropped。

And the steps we're going to reason through is asking ourselves what acts are going to be generated by the receiver。

And when the sender receives those acts， how is it going to respond and again。

 we're assuming the only packet or act that's no x dropped and the only packet that's dropped is 101。

And at this point， I would encourage you to actually pause the video here and first try working through it on your own and then move forward with me once you had a chance to think about it on your own。



![](img/38c9eac229dafc89f7933b637fde605c_51.png)

But so moving forward， what I'm going to show you here in this example is the timeline of events and actions at the senddo。

 and so we call what we have in flight are packets from 101 to 110。

 those that had already been transmitted by the senddo when we first stepped into this example and packet number 101 has been lost。

Okay and we're going to walk through the timeline where we're going to say what the sender does so here's the first step the sender is going to receive an acknowledgement that says act 101 it receive this acknowledgement because at the gazeva packet 102 made it through and remember the receiverva always does cumulative act and says what the next expected packet is and so the gazer sent an act that says act 101 to the sender。

In parenthees here， I'm saying due to 102 so that you realize。

That the center is receiving this act because the receiverr corresponding to packet it1 equal2 when it made it through to the receiver。

So at this point in time， the center has received act 101。It was because of data packet 102。

 it had a congestion window that was set to 10， and this is a duplicate acknowledgement。

 so it's the first duplicate acknowledgement。So the center is not going to transmit or do anything at this point。

It's going to receive another duplicate Act this time due to packet it103。

 so it's going to increase its due back counter。And yet another act 101 this time due to 104。

 and so it's going to increase its two pack counter again at this point it has three duplicate acts and so it's going to do fast heat transmit。

What this means is the send is now going to retransmit packet 101。

And then if you follow the rules we had for fast retrans and congestion avoidance and so on。

 at this point the sender sets SSre to be half of its current congestion window value。

 so it's set to be five。And then it cuts its congestion window， sea wind in half。

 and so sea wind is also five。And now let's look at what happens at the center。

What happens next is the sender receives another act 101 this time you to packet 105。

But it doesn't transmit， it can't transmit， it has a c window of five and it has more than that number of packets outstanding。

Same thing due to 106 and 107。I just want to point out that notice we do not restart the duac counter on the same packet okay so if you're not going to do fast retransit a second time the duac counter does not get reset you only retransmit when you have three du packs so if you actually lost the same packet twice you would be falling back to a timeout to retransmit it。

Okay so we did not restart the twoac counter so we're going to keep going and this time the sender receives yet another act 101 this time due to packet 108。

 same thing for 109，110， and it's only when 101 makes it to the receiver。

 then the sender receives an act that says act 111 that's because 101 filled a hole at the receiver。



![](img/38c9eac229dafc89f7933b637fde605c_53.png)

By the time it got the heat transmission it had received everything up to 110。

 and so the receiver sent Act 111。You do  one， they one。And so at this point。

 the sender now has a congestion window of fight。And it has no packets in flight。

 and so it can actually start to transmit new packets。

The main problem here is that this was a long time to wait at the sender。

 spent all of these du packs coming in， which are a clear sign that the network is delivering packets to the receiver。

 but the sender just stalled and you can imagine if you have a window of thousand packets how much worse this could be。

A somewhat secondary issue， I would say is that in effect， we've drained the network pipe。

 we've drained the pipe， there are normal packets in flight and we've lost all of that a clocking。

That we had going。 And so now the sender has to rebuild that a clocking。 So at this point in time。

With a C window of five and zero outstanding packets。

 the sender would just dump another five packets straight into the network in a burst so all that we were trying so hard to avoid bursty behavior well we've just undone it。

But this is the problem that fast recovery is trying to resolve the two questions to ask yourself before you move forward first is do you understand the problem okay the  krks was that the sender had to wait a long time before it was able to resume sending and secondarily that once it was finally when it could finally send when the retransmitted back it made it through we had lost act clocking and so the sender was just dumping a full window into into the network。

If you haven't understood this， I would say Paso，ll go back to the previous example and work through it until you do understand it。

And once you do then second question is how would you fix it。

 and again I would encourage you to pause here， think about how you would fix it before proceeding and having me tell you how to fix it。



![](img/38c9eac229dafc89f7933b637fde605c_55.png)

So with that， the fix we do have is this technique called Fast recovery。

 and the basic idea is very much what you might expect。

 which is we're going to give the standard temporary credit for every duplicate act that comes in。

This allows us to keep packets in flight， this allows the sender to continue to send new packets as long as these duplicate acts are coming in and again the intuition here is that if the sender is receiving duplicate acts。

 this kind of tells the sender that the network is functioning pretty well because the receivers receiving packets and sending acts and the as are making it through。

So exactly how do we do this， the rules as follows under fast recovery when we have three duplicate acts。

 we now as before we're going to set SS threshold to be half of the congestion window。

But we're going to now give the congestion window credit for those three duplicate acts。

 so we're going to say that the congestion window is SS， that's cutting in half plus three。

And then for as long as we are in fast recovery， every time we receive a duplicate attack。

We're going to increase our congestion window by one。The intuition of the hope here。

 what this is trying to achieve is that this allows the source to send an additional packet。

That is kind of in the conservation principle， it's a one is for one for the packet that arrived。

 so the packet that generated the du packac left the network and so we're allowing the sender to put in a new packet。

And we're going to let the sender keep doing this until it exits fast recovery and the condition under which it exits fast recovery is when it receives a new act。

 so when it's received a new act this tells the sender that this issue with this isolated loss is resolved and it can now go back to what it originally intended。

 which was to get back into AIMD but to do it with a reduced congestion window so we set the congestion window to be SS slash。

 the original half that we had saved。

![](img/38c9eac229dafc89f7933b637fde605c_57.png)

So let's go to example and see that in action and I think it should be clear I hope so here's again the timeline at the center same scenario。

101 was lost， the other packets make it through， but now we're going to do fast recovery。

So just like before， we get Act 1010 to 102。Due to 103 due to 104 at this point we have three duplicate acts。

 and so like before we're going to retransmit 101。Also like before we cut we said SSC to be half of the congestion window。

 so it's five。But now because of fast recovery， we're going to set C to be eight， which is five。

Plus the three dus that we're giving it credit for。

And now the subsequent steps are where things continue to be different。

 so the next act or duplicate act 101 that arrives at the center。

 it's going to increase its sea by one， so the congestion window is now9。

That's still smaller than the number of packets in flight， so the sender is not going to transmit。

Same thing when it receives yet another duplicate act due to 106， the sea is 10， but the send。

 remember already has 10 packets in flight so it can't send more than that。

But the next act that comes in due to 107， the congestion window is now 11。

And the sender only had 10 packets in flight， so now the sender is allowed to send one more packet。

 so it sends a new packet， 1，11。Okay， that was the next one in order。

Same thing for the next two pack， your congestion Windows 12， sender gets to send。One more packet。

Again， the next one congestion window is 13， so it sends 113 and so on。Until finally。

 packet 1 equal1， the retrans of 101 makes it to the receiver。

 and then the receiver sends an act that says act 111。Okay。

 this is due to the wheat transmitted 101 arriving at the gazebo。

So at this point this is a new acknowledgement right so no this is no longer duplicate x coming in。

 and so this is the point at which we exit fast recovery。

And exiting fast recovery remember means that we now set the congestion window to be5。

 which is equal to be assessed cl because recall the original intent was we were going to do multiplicative decrease and drew up our congestion window in half we were just。

Temper regularly inflating the congestion window to allow the sender to keep going。

But now we're going to do multiplicative decrease， so we set c equal to SS3， which is5。

And you can transmit 115。Okay， why 115 because your see is five and we already had four packets。

 111 to 114 that were in flight， and so we allowed to send one more packet in order to have those five packets in flight。

And so what would happen next just to make sure you see where this is going to go。

 the next step the sender would receive an act 112。

this is due to the packet 111 arriving at the receiver。

So at this point it would update its congestion window in a accordance with the congestion avoidance school so it would be5 plus1 over51 of even and so on and from here on it would continue to do the normal additive increase and so on so this is the end of the example of fast recovery I hope you see why we needed it in order to not stall the sender when all you had was you bad luck one packet that got dropped and also how it works by temporarily giving the sender credit or inflating its congestion window in proportion to the number of duplicate acknowledgegments that are coming in。



![](img/38c9eac229dafc89f7933b637fde605c_59.png)

So let's see how that updates the rules we had or the pseudocode we kind of had for how congestion control works and the changes are again you know it's clever the changes are not widespread。

 they're fairly surgical to what we had before so here's the changes on the first event where you receive an a with new data。



![](img/38c9eac229dafc89f7933b637fde605c_61.png)

If you were in the only changes we now have this check that says if you were in fast recovery。

 then you need to exit fast recovery， because remember we said you exit fast recovery when you finally get a new act。

 which means that that hole you are trying to plug has been filled。

So if you get an act on your data and you are currently in fast recovery。

 then we set the congestion window to be equal to SS crash。



![](img/38c9eac229dafc89f7933b637fde605c_63.png)

That implies we're going to leave fast recovery。The other is when you receive a duplicate Act the changes are again in red over here if this is your third duac。

 then just like when we had fast Street announcement。

 we're going to cut setSS there to be half the congestion window。

 we're going to h a congestion window now the only changes we're adding this credit plus three due to the three du packs that were received。

And then beyond that， anytime your duplicate act is。Counter is above three。

 that means you are currently in the fast recovery phase。

 and so at that point you said c is equal to7 plus1 MSS。Okay。And this， of course。

 when you get a new app， yourtu counter will be reset。

 you will set your congestion window to half as we discussed and you' proceed。

 so you automatically get out of fast recovery。

![](img/38c9eac229dafc89f7933b637fde605c_65.png)

With that one final topic that kind of brings this entire lecture together on one slide is to take a look at the TCP state machine again the TCP state machine is really just capturing everything we've covered in this lecture it's just doing it in a very different format in the style of a state machine and transitions between those states so we have three states as we've covered these are slow start congestion avoidance and fast recovery and we're going to look at what events because。



![](img/38c9eac229dafc89f7933b637fde605c_67.png)

The send took transition between these states。And so the first one， just the easy one。

 anytime you get a timeout。From whatever state you're in。

 you fall back or you move back into this slow start phase so no matter where you start out。

 you get a timeout， you end up in slow start。Now let's look a little bit at the slow start state what happens if you get a new acknowledgement and you're in slow start。

 you just increment your congestion window as per the new ahole so you add plus one every time you get a new act but you stay in slow start this is your exponential growth。

Until you， so you're updating your every time you get a new act。

 if your congestion window exceeds your SS threshold。

 that's when you move from slow start to congestion avoidance。

So if you remember this was the discussion about I've reached up to a safe rate beyond this point I'm going to be more cautious and move to additive increase so if you see when it's greater than as I said move to congestion avoidance。

And then the last event that can occur at in the slow start phase is that you receive a duplicate acknowledgement so when you receive a do backQ and come at your counter and you stay in slow start until you receive three duplicate acts if you receive three duplicate acts。

 you transition to fast recovery so now we would be in the fast recovery state。

Let's move on and take a closer look at the congestion avoidance state so we said if you get a timeout you go to slow start。

 if you get a new act and you're in congestion avoidance， you just stay in congestion avoidance。

 you update your congestion window accordingly and so on， but we stay in congestion avoidance。

If you get a duplicate act， again， you stay in congestion avoidance， you know。

 increasing your twoac counter until once again， if your twoac counter is three。

 then you transition to the fast recovery phase。When you're in the fast recovery state。

As long as you're receiving du packs， you're staying in fast recovery。

 this is when we're going to be inflating the sea wind。

And you're going to stay in fast recovery until such a point that you receive a new act and if you receive a new act。

 you move to the congestion avoidance state as we just discussed and of course。

 if you're in fast recovery and you time out， then you move to stay slow start。And so this is really。

 you know， if you understand these states and all of the transitions that are in this figure。

 this is a great way of checking that you've correctly understood what's going on in TCP。

 this state machine together with the rules for how you update sea wind within each of these states。

😊，That really tells you everything you need to know about TP congestion control。



![](img/38c9eac229dafc89f7933b637fde605c_69.png)

One last point to make is you know I mentioned this last time there are many variants to TCP congestion control and we've discussed one particular implementation。

 just to give you an example， TCP Tahoe for example is a variant on TCP that's a very old one where even when you got a three duplicate acts。

 it would set the congestion window to one so a highly conservative it would just fall back。

To slow start every time you got a loss。TisPino does pretty much what we described today。

 it has a congestion window of one on time out and cuts its congestion window in half on three2 bagss just like we do。

TCP new does everything TCP Reno did， but it adds faster recovery， which we just discussed。

A slightly different variant is TCP selective acknowledgements。

 this incorporates a different type of acknowledgement in which you now carry these selective acknowledgeknowgments that enumerate the byte ranges that the receiver has received and this would be carried as a special option field in the TCP header。

And so this is selective acknowledgements are nice because it takes away a lot of the ambiguity that we saw with cumulative acknowledgements。

 however it does require this new type of acknowledgement field and it does require options in the TCP header and so the implementation is a bit more detailed and a bit more involved。

You might be wondering what's with the Tahoe know， it's that the Berkeley UniX group used to have these retreats in Tahoe and they would name what ideas they came up with or the changes that came out of those retreats based on the location where they'd had their meetings。

Fun fact is that many of the research groups at Berkeley in the systems side continue to have these annual retreats at Tahoe。

 so that tradition is continuing till today。Anyway， in this class， unless we tell you otherwise。

 you can assume that we are basically。Describing if we say TCP congestion control。

 we are assuming everything that I've described in today's lecture， this is effectively TCP Neguino。

And that's going to be our default assumption。

![](img/38c9eac229dafc89f7933b637fde605c_71.png)

One question you might have about all of these variants is interoperability if everyone's running a different variant how can all these algorithms coexist and don't we need a single uniform standard that we all agree on for how you implement and update your congestion window so specifically what happens if I'm using TP you know and you are using TP Taho and there's a question of fairness that we'll get to in the next lecture but for now the question was just basic interoperability will the connection even work can we communicate？

If we're runninging two different variants of TCP。If you think about it for a second。

 you'd see that the answer is yes， because the only thing that these wagons are changing like Re versus Tahoe is the rules by which the sender is updating its seawin and the number of packets it's putting in。

 but we're not requiring or demanding any kind of different behavior on the receiverva the receiverva is just sending cumulative acts like it always did。

 so the gazeva side of the connection is oblivious to what the sender side is doing to update its congestion window and so it all just works。

That is true for all of these TP， reo， TP Tahoe， Newguo。

 and so on that are just changing the update rules but not changing how acknowledgement works。

Acknowledgements work if I asked you the same question about aganning TCP newguino and Uagganning TCP Sac。

 can we actually exchange packets so do we have interopability。

 The answer would be no and that's because with selective acknowledgements were actually changing the acknowledgement field。

And so we need both ends of the connection to agree and understand what that change is。

 we need the gazeba has to be able to send selective agments and the sender has to know how to update its sea wind based on those selective agments。

 it has to know how to par them what the semantics are， what the logic around updating sea wind is。

So we do have interoperability， but only between variants that don't actually change what goes into the TP header or the acknowledgecments that get carried between them。



![](img/38c9eac229dafc89f7933b637fde605c_73.png)

And so with that， at this point， I hope you have a pretty detailed understanding of how both congestion control and reliability are implemented in TCP and topic for next lecture will be getting into some of the more advanced congestion control techniques。

 including a little bit of goto assististed congestion control as well as a little bit of kind of trying to derive the simple analytical model for the performance we can expect from TCP。

With that， thank you and I hope to see you next week in class。



![](img/38c9eac229dafc89f7933b637fde605c_75.png)