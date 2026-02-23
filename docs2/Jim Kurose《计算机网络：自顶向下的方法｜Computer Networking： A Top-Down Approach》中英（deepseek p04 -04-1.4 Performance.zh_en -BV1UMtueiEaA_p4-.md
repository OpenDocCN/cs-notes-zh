# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p04 -04-1.4 Performance.zh_en -BV1UMtueiEaA_p4-

![](img/e75936b9f3cb25e06c8606ed0d3abe52_0.png)

In our discussion of the network core， we saw how packets can be delayed or lost at routers within the network In this section we'd like to take a little bit of a deeper dive into the issue of performance。

 we'll start off by looking at delay a little bit more carefully。

 looking at the different components of delay， we'll look at a tool called trace routeout which will actually allow us to measure and look at real delays in the live internet and finally we'll wrap up by introducing a new performance metric that's throughput so why don't we get started。

Recall that we learned in the last section that packets queue in router buffers waiting for their turn for transmission。

 we also learn that packet queuees grow longer at a router's output link when the arrival rate to that link。

 hopefully just temporarily exceeds the output links's capacity。

 and we learn that packet loss can occur when the memory needed to hold packet's fills up。

Let's now dive deeper into four components of delay that can happen at a router and the first of these components of delay are what we might call a processing delay。

 This is the delay associated with forwarding table lookup。

 forwarding a packet through the switch and doing some associated integrity checks。

 these delays are on the order of microseconds or less。

The second component of delay is thequeuing delay that we saw in the previous section。

 this is the amount of time that a packet has to wait to queuee at an output link for transmission。

 and as we saw earlier， the amount of time spent queuing and waiting for transmission is going to depend on the congestion level for the outgoing link。

We also saw earlier that once a packet begins transmission。

 it's being sent into the link at transmission rate R takes a certain amount of time for all of the bits in those packets to be pushed into that outgoing link。

 this is known as the transmission delay and as we saw earlier。

 the transmission delay is simply the number of bits in the packet L divided by the transmission rate R。

And finally， there's propagation delay。 This is the amount of time it takes from when a bit first enters the sending side of the link until it pops out at the receiving side of the link。

 Now bits generally propagate through media at close to the speed of light and so you might think that's fast。

 but in fact， you can actually notice propagation delays for instance。

 the amount of time it takes from a bit being transmitted on the earth up to a geosynchronous satellite 270 milliseconds for a transatlantic link。

 the delay from one side of say the east coast of the United States to Europe that's on the order of 30 milliseconds and these delays can actually become quite noticeable。

So there you have it， four components of delay， the processing delay， the queuing delay。

 the transmission delay， and also the propagation delay。

 Now I found that sometimes students confuse transmission delay with propagation delay。

 so let's look at that just a little bit more carefully and let's start by using an analogy。

As always， a real world analogy might help here。 Let's consider a caravan of cars。 Cars are the bits。

 The caravan as a packet and taking a toll and passing a car through a toll booth is like transmitting a bit。

A car then drives。 That is to say propagates onto the next toll booth。

 And here's the question we want to ask ourselves。 How long is it until the last car of the caravan leaves the first toll booth before the entire caravan is lined up before the second toll booth。

 In order to calculate a numerical example， let's make a couple of assumptions here。

 Let's assume that the toll booth takes 12 seconds to service a car that's equivalent to a bit transmission time。

 and let's assume that cars propagate at 100 kilometersm per hour。

 It's like a bit propagating through the medium。 And finally。

 let's assume that the toll booth are 100 kilometersm apart。 Well， with these as givens。

 we can compute the time to push an entire caravan through the toll booth and onto the highway。 Well。

 it's 12 seconds per car。 There are 10 cars per caravan。

 So that's 1 hundred 20 seconds to transmit the caravan， if you will。 Now。

 let's look at propagation delay。 The time for the last car。

from the first toll booth to the second toll booth。 Well， it's got to go 100 kilometers。

 It propagates at 100 kilometers per hour， So it takes an hour for that last bit to propagate from the first toll booth to the second toll booth。

 So in total， the total amount of time it takes until the caravans lined up before the second toll booth2 minutes。

 That's the transmission time plus 60 minutes， That's the propagation time for a total of 62 minutes。

Having taken a deeper dive into propagation delay， let's next take a closer look at queuing delay。

 And we want to get both a qualitative and a quantitative feel for queuing delay。 So to do so。

 let's define a as the average packet arrival rate and L is the length of a packet。

 So L times a is the arrival rates of bits to that link。 As before R is the length bandwidth。

 That is the transmission rate of bits。 Now， if we take the ratio of these two quantities。

 The arrival rates of bits divided by the transmission rate of bits。

 We get a quantity that's known as the traffic intensity。

 That's the ratio of the amount of arriving work， if you will。

 the bits to the systems capacity to do that work。 that is transmit the bits。😊。

And we all know intuitively that when the traffic intensity is low。

 that is l times A over R is small， there's seldom a Q。

 and when l times a over R is greater than one， there's more work arriving on average than the system's capacity to do that work。

 And so in this case， delays infinite。 The queue of backlog work just gets larger and larger and larger over time。

 The graph here shows the average queuing delay as a function of traffic intensity。

 and note when the traffic intensity gets close to one， delays get very large， very fast。

 And you're certainly used to this kind of phenomena on roadways。 It's exactly analogous here。

 except that we're interested in a communication network instead of a roadway and packets in bits instead of a car。

Throughout this course， we're going to use the live internet to illustrate and study the principles that we're learning。

 Well， we've learned about delay and there's a tool called trace Route which will actually allow us to measure and inspect what's happening in terms of delay on a path from a source to destination。

 Let's take a look at trace route。Traceroute is a program that runs on your laptop or computer。

 It provides live measurements of packet delay from the sender。

 your computer to routers along a path towards a destination。

 traceceroute works as follows first sends three packets to the first hop router first hop router sends a reply message in response to each of these packets。

 The trace routeute sender measures the roundtri time。

 the RtT from when it sends a message until when it gets the reply and then displays those three RtT measurements。

 It then sends three packets to the second hop router measures and displays the RtT to the second hop router and continues on until the final destination is reached。

Let's take a look at what the output of a trace route looks like。

 This is the result of a trace route I performed earlier from Gaia。cs。ummass。

edu in Emherst Massachusettssachetts to Ucom。 FR in France。

 and let's take a look at this trace in detail。Trace out first sends three packets from Gaia to the first hop router on the path to yourCO。

frR， that first hop routers in the computeruter science department network。

 and the measured RtT delays are1 millisecond， 1 millisecond， and two milliseconds。

Trace Rof then sends three packets from Gaia to the second hop router。

 which is still inside the UMass network， pretty close to the first hop router。

 and the RTT delays are again around  one millisecond，1 millisecond and two milliseconds。

If we go a little bit further down in the trace route。

 we see a 22 millisecond RTT delay to a UK router in Washington， DC。

 and then we next see an RTT of over 100 milliseconds to a router in the Jt network。

 that's a research network in France and if you look at the difference between 22 milliseconds to get to DC and 105 milliseconds to get into France。

 you see the effects of propagation delays across the Atlantic Ocean。

Sometimes the measured RTT decreases even though packets travel further， as we see here。

 and that's possible because the congestion level， the queuing delay upstream can change over time Lastly。

 we'll sometimes see stars and this is from a router that refuses to reply to a received trace route message from a source and so an RTT measurement can't be made。

This is mostly just a review slide。 We've been focusing on packet delay。

 but we need to remember that packet loss can also occur when router buffers fill up and an arriving packet has no place to be stored in high congestion scenarios。

 losses can be high。 I've measured times when 10 to 20% of my packets are being lost in Chapter 3。

 will'll see that there are a number of techniques that hosts can use to detect and recover from packet loss and to control the rate at which their sending to control congestion。

The final performance metric that we want to spend some time on is known as throughput。

 throughput is the rate bits per second that are being sent from a sender to a receiver。

 and throughput now also needs to be defined over an interval of time。

 it could be instantaneous or over a very short period of time。

 or it could be averaged over a much longer period of time。And to think about throughput。

 it's often useful to think about water flowing through pipes。 You can tell， I love analogies。

 You can think of a sender as sending fluid into a pipe at some rate。

 And each transmission link along a path as being able to carry fluid at some rate。 Some pipes fat。

 Some pipes are thin， And here's what you want to think about。

 when an end to end flow carries packets over multiple pipes serially。

 How does the capacity of each pipe， the maximum rate at which a pipe can carry a fluid determine the overall end to end throughput that a flow receives。

 And let's think about this in the context of the scenario here。

 where a sender is sending a large file to a receiver over two hops through two length。😊。

Let's look at a couple of examples in this first scenario。

 we have a thin pipe with capacity R sub S as is for server。

 followed by a thick pipe with a higher capacity R sub C C is for client。

The end to end throughput here will be limited to R sub S， the capacity of the first pipe。

 the thin pipe。In the second scenario， we have a fat pipe with larger capacity R subS。

 followed by a thinner pipe with smaller capacity of R sub C。

The throughput here will be limited by the capacity of the thinner pipe in this case， R sub C。

 And in general， when you think about the throughput that a source to destination path can receive。

 it's going to be limited by the capacity of the thinnest pipe。

 the pipe with the smallest transmission capacity in networking。

 this link sometimes known as the bottleneck link。And lastly。

 we need to think about how individual flows are going to all interact with each other inside the network in terms of their achievable throughput。

 So take a look at this diagram here。 What you see is we've got 10 servers and 10 clients and a single connection from each server to one of the clients Now the link at the edge of the network。

 let's just assume that they're dedicated。 But somewhere in the center of the network we've got a shared link of capacity R。

 Now， let's also assume that this shared link of capacity R is able to fairly share the bandwidth available among the 10 flows so that each sees a bandwidth available of R over 10。

 What is the per connection throughput in this particular scenario。Well。

 think about this in terms of pipes again， where each session now passes through three pipes seeing a capacity of R sub S R divided by 10 and R sub C。

 remember that middle link is going to be shared by 10 session so each session only gets one1th of the capacity Well。

 hopefully you can see that the per connection end to end throughput is going to be the minimum of these three values R sub C R sub S and R divided by 10 and you might be interested to know that in practice R sub C or R sub S is generally smaller than R divided by N that is bottleneck links tend to be at the edge of the network。

In this section we took a deeper dive into two aspects of network performance delay and throughput in the case of delay we identified four components of delay。

 processing delay， queuing delay， transmission delay and propagation delay and we used trace route to look at some real delays as measured in the internet and we also took a look at throughput and hopefully there you found the analogy between fluids and pipes to be interesting and useful。



![](img/e75936b9f3cb25e06c8606ed0d3abe52_2.png)