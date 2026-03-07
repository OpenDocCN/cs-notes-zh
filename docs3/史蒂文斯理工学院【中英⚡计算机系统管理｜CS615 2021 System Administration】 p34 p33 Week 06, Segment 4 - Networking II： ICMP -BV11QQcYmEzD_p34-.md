# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p34 p33 Week 06, Segment 4 - Networking II： ICMP -BV11QQcYmEzD_p34-

Hello and welcome back to CS615 System Administration。

This is week6 segment 4 and with this video we're continuing to illustrate different network protocols briefly covering ICMP。

 the Internet control Me protocol。I'm sure youve all used ICMP。

 but it's useful to show how we can observe and analyze even trivial communications。

We'll cover the two most commonly used ICMP applications， Ping and Trace route。

 as they help us answer at least some of the questions that had arisen in earlier videos。

Now Ping of course is about as trivial as a packet exchange can be。

 but let's quickly observe it in ourll host by capturing the IPV4 ICMP packets via a TCP dump。

And then having the P utility send us three echo requests over to www。yahooo。com。

We then inspect the captured packets。And see， indeed。

 just individual echo requests being sent by our host with each triggering an echo reply from the web server on the remote end。

We also see here that ICMP Echo request echochoply packets can apparently have an identifier to make it easier to differentiate packets that belong together。

But so perhaps there is a bit more to the packet format。

 so let's take a look at what the RFC tells us。As we see here， the packet is rather simple。

 We have a type which is set to 0 for an echo reply and set to 8 for an echo request。A code field。

 which is all0 for this type of message。We got to check some。The identifier， we just mentioned。

And a sequence number for the message being ping pong between the hosts。

But note that we also have a data section here， which perhaps is a bit weird and not something you may have used in the past。

Let's see what the manual page says。Here， the D P flag allows us to fill some data。

 which can be used to better identify and track packets when troubleshooting connections。

But note that， of course， this can also be used in perhaps unanticipated ways。

 Many organizations prohibit egress traffic from their systems to the internet， to。

 amongst other reasons， prevent data exfiltration。But ICMP messages are oftentimes permitted since ICMP is rather useful and important for all sorts of troubleshooting。

So you could encode the data and hide it an ICMP echo request packets。Like so。

We encode the data into hex。And then。Let's capture the packet so we can observe the data being exfiltrated。

Then send the pink packet with the extra data。So then when we read the captured packets。

 nothing looks particularly different。But if we ask for the full packets， via the dash X flag。

We notice that our packets now do contain the data as specified。

While this is not a major concern in most cases， this is just another example of how understanding the different protocols across the stack is important。

 and that there's usually a little bit more to dig into than initially meets the eye。Anyway。

 so this is IPV4 ICMP Echo request Echo Rely。What does this look like in the IPV6 world？

Turns out it's really not all that different。Let's capture some ICM PV6 packets and repeat the same p exercise from before。

Here we go。

![](img/5f9db81b03a1cb0e0ebb68974bc95ac1_1.png)

And yep， all this looks almost identical So sends an echo request to the destination。

 the destination replies with an echo reply， and that's about it easy Py。

So regardless of which IP version we're using， the packets look the same。Ego request and echo reply。

But here we go again， glossing over all that's going on in this silly internet cloud over here in the middle。

How do we get the packet from our AWS instance over to Yahoo's web server？



![](img/5f9db81b03a1cb0e0ebb68974bc95ac1_3.png)

Remember a few videos back， we looked at the different ASS numbers of the system that we determined from the trace route we ran。



![](img/5f9db81b03a1cb0e0ebb68974bc95ac1_5.png)

We didn't go into the details of just how traces or determined the path our packets are taking between two systems。

 but guess what， it involves ICMP。And what do we do when we want to know the details of the network communications。

 we go back to TCP dump。So here we are now82 instance ready to capture packets of type IPV4 that are either ICMP or UDP。

We use the dash V flag to get a little bit of extra information about each packet。

Then over here on the right， we're running the trace rod command。

 asking it to only send a single probe to make it easier for us to inspect the packets。

When we run this command， we immediately see the captured packetancy on the left。

So let's scroll back up to see just how tracer works。

The first packets we see up here are the DNS lookup for www。yaahhoo。 com， which we've seen before。

Then below， we see our IP address，10。10 do0。47， sending a UDP packet to port 33，43，5。

Whether TTL of one。We then see that we get back a packet from 216，1，822 3，8。

127 of type ICM time exceeded in transit。This is because every router will decrement the TtL and if the TTL reaches 0。

 it will generate this ICMP timing exceeded message。

 so we in effect trick the first hop to reply to us by setting the TTL of1。

 knowing that the next top must necessarily generate this message and we thereby learn its IP address。

We then repeat the same process。With a TTL set to2。

Thereby allowing the first top to pass the packet onto the next top。

 which then will generate the time exceeded message。Then we repeat again with a TDL set23。

To then again， have the first two hps pass it on。And the third to trigger the ICMP message。

And so on and so on。Finally， at the last top。We're setting a T T L of 16， now。

Which reaches the destination？But the destination won't generate a time exceeded message and there is no you have reached a destination ICMP type。

 so how do we know we have reached the destination？look at the packet here。

It says destination port unreachable。That is we again trick the system in sending us a message by picking this random UDP port here。

Which of course， means that if the host was listening on their port。

 we wouldn't be getting a response， so we once again really just being opportunistic。All right。

 so that's tracer and IPV4 now for IPV6。We want to avoid capturing some of the other ICMP noise we've seen。

 neighbor discovery， or route solicitation in IPV6 also happen over ICMP。

So we restrict our capture to only echocho request and echocho reply types。ok。

Let's run our trace route over IPV 6。

![](img/5f9db81b03a1cb0e0ebb68974bc95ac1_7.png)

Now， scroll back up。And here we go。Looks familiar， right？In IPV 6， the TTL is called the H limit。

So here we set the H limb to one。And the first router returning the time exceeded message。

The second message with nature Li， set to two。Who turned the second hop。And so on and so on。

Until down here， we again get the same destination。

 unreachable message when we hit the destination house。

To visualize how we tricked each router to tell us itsips along the way to the destination。

We send a packet with the HL set to one。The router decrements the HL， then checks if the H limb is0。

If so， it returns the timing seated message and we can record our first topic。

Then we send a new packet with an H limb of2。 Our first router decreementments the H limb to1 and forwards it。

 The second router decreementments the H limb finds it to be 0 and generates the time exceeded message。

 And we have a second hop。Once more， now with H limb equals 3。Which gets forwarded。And forward it。

 But then hit the limit。And we generate the exceeded message。And we have our third hop。

On our last packet， we repeat the same process until we hit the destination。

 which hopefully is not listening on anything on the random UDP port we had picked。

 and it will then generate the destination unreachable message。

 letting us know that we fit our target。Okay， time for our quick summary。

 we've seen some use of ICMP， most notably the ubiquitous echocho request echocho reply Me sent using Ping。

We've also seen the use of trace routeute， which uses a random UDP port， destination。

 and thenense package with an increasing TTL。Trerackking the routers along the way to send back ICMP time exceeded messages。

Until our destination tells her that the port we're trying to talk to cannot be reached。Now。

 since it's possible that something along the way blocks UDP， for example。

 you can also use ICMP or TCP packets to send to the destination。

One thing we haven't discussed is the IPV4 path MU discovery。

 This was used to determine the maximum packet size that will make it to the destination without fragmentation。

Look up why that would be useful and just how exactly it works。

 you should find that it works very similarly to tracero。

But ICMP is not just restricted to these use cases。 There are several other times。

 Go find out what they are。 And when you might want to use them。

 it'll soon help you understand why generally a bad idea to block ICMP across the board。

When you run your trace rods to different locations on the internet。

 you will likely encounter several that either include asterisks in the middle or that time out and do not reach the destination。

 Think about under what circumstances that happens。Finally。

 recall call that we can look up the ASS numbers of the networks along the way。

When you tracer a system from AWS， you may find several that are listed as being in A 0。

 What's up with that。Look at the IP allocation locationss for this AS and try to find an explanation for why we are seeing these here。

With all that， I hope you've gained a bit of an understanding of the Internet control message protocol and expanded your horizon beyond just UDP and TCP。

This letter two， we've already seen in an earlier video and we'll again observe them in future videos when we talk about different application layer protocols。

Until then， thanks for watching， cheer。

![](img/5f9db81b03a1cb0e0ebb68974bc95ac1_9.png)