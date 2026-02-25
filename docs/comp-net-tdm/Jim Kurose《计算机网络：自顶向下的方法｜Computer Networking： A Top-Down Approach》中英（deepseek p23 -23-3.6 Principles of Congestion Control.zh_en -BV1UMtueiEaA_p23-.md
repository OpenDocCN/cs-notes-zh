# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p23 -23-3.6 Principles of Congestion Control.zh_en -BV1UMtueiEaA_p23-

In this section we're going to take a big picture view of congestion control。

 really looking for a principled understanding of both the causes and the costs of congestion and we'll identify two basic approaches for dealing with congestion in the first place in the next section we're going to take a look at TCP and how it actually implements these principles but for now we're going to step back and take the big picture view so you can put your pens and pencils down and sit back think listen。

 put your thinking caps on as the saying goes， I think you're going to really enjoy this and remember congestion control really is a top five issue in computer networking so pay attention。

Well let's start by asking the most basic question what do we mean by congestion Well informally congestion is all about too many sources sending too many packets too fast for a congested network link somewhere in the network to handle Now remember。

 remember that links have a transmission rate and when the arrival rate of packets exceeds the transmission rate。

 queuees will start to build up and delays will get larger and larger。

And if the links's packet buffers fill up completely， arriving packets will be dropped and lost。

It's important to remember that congestion control is really all about multiple senders。

 multiple senders sending too fast an aggregate， while flow control。

 which we studied in the last section is really about speed matching between a single sender and a single receiver So with that is background。

 let's dive into the causes and the costs of congestion。We'll do this by starting with a simple。

 idealized scenario。You know， idealized scenarios are something that professors love to think about。

 and then we'll start adding increasingly more realistic assumptions。

 so let's start with the scenario shown here We'll look at the case of a single router where congestion will occur and first assume that there's an infinite amount of buffering that's idealized of course。

The router has input and output links of capacity R bits per second， and there are two flows。

 the red flow and the blue flow shown here。Let's take a careful look at the flow rates associated with the red flow on the sending side。

 there's a Lambda in， that's the rate at which data is being sent from the application layer down to the transport layer and at the receiving side there's a Lambda out which we'll refer to as the throughput that's the rate at which data is actually delivered up to the application layer at the receiver and well want to ask the question what happens to the throughput as we dial up the arrival rate on the sending side。

 assuming that we increase the arrival rate for the red and the blue flows similarly。Well。

 with the case of infinite buffering， no packets are lost。

 Every packet that' sent is eventually received。 And so the throughput at the receiver equals the sender's sending rate。

 as shown in the plot here。Note though here that the x axis ends at R over two。

Since if each sender were to be sending at a rate faster than R over 2。

 the throughput would simply max out at R over2 per flow。

 that's because the router's input and output links can't carry more than R bits per second of traffic R over2 for each of the two flows。

Well， this looks pretty good， at least from the throughput standpoint。

 but remember we learned in chapter 1 that when the arrival rate to a link comes close to the Ly's transmission rate。

 large queuing delays can occur as shown here。And so we see already that there are costs。

 in this case， delay costs， even in this idealized scenario。

 let's see now what happens when we drop this unrealistic assumption about infinite buffering。

So let's consider the same scenario except that now the amount of buffering is going to be finite。

Recall from our study reliable data transfer that we learn that senders are going to retransmit in the face of possible packet loss due to buffer overflows or corruption。

 so we're going to need to look a little bit more carefully now at the sending rate。In particular。

 well want to make a distinction between the rate of original data that's being passed down from the application。

 we'll denote that Lambda in and the overall rate at which the transport layer is sending data。

 including retransmissions， will denote this as Lambda N prime。

The rate at which packets arrive to the router is Lambda in prime， not Lambda n。

 make sure you've got this and the distinction between Lambda n and Lada in prime。

 it's really important。And as noted here， lambda n equals lambda out and lambda n prime is going to be greater than or equal to lambda n since it's going to include the retransmissions。

All right， for this case of finite buffers， let's start with an idealized scenario still。

 And let's imagine that somehow magically， the sender knows whether or not there will be free buffer space for transmitted packet。

 So in this case， no packets are going to be lost。 The source sends a packet。

 just buffered at the router， eventually transmitted and received at the receiver。 In this case。

 no packets are lost and the throughput lambda out here on the y axis equals lambda in。

 No problems here。 Well， except for the queuing delays as lambda in approaches R over2。

 just as in our first scenario。😊，So let's next relax this assumption that the sender somehow magically knows when there's going to be free buffer space and consider what happens when packets can be lost at the router when they arrive and there's no free buffer space here we see a packet arriving to find the buffers full。

 it's lost， and so a copy of the packet is retransmitted by the sender eventually。

 and in this case finds free buffer space advances through the buffer and is eventually transmitted by the router and received at the destination。

In this case， when retransmissions occur because of known loss。

 the plot showing the overall arrival rate versus throughput looks something like this。

At a low arrival rate， buffers will almost always be available。

 and every originally transmitted packet is going to make it through。 So in this low arrival region。

 the arrival rate， including retransmissions， which really don't occur very often essentially equals the receiver throughput and a unit increase in the overall arrival rate。

 Lambda in equals a unit increase in the throughput Lambda out。

 That's to say that the slope of this red curve here， is close to one。

 What's much more interesting as the high arrival rate region here here。

 the arriving packets increasingly include retransmit packets。

 And so the receiver throughput no longer increases one for one with an increase in the overall arrival rate。

And we see that as the overall arrival rate on the X axis approaches R over 2 can't go any higher。

 the maximum throughput at the receiver is actually less than R over2。This gap here。

 and this is important to note is because N retransmted copies of a packet take up to n times the transmission capacity of a single packet。

 but in the N， these n packet transmissions contribute only a single packet to the throughput。Well。

 now let's see what happens if we drop the unrealistic assumption that all of the retransmissions are actually needed。

 That's to say， let's assume the sender may time out prematurely as shown in the example here and actually deliver two copies of a packet to the receiver。

 In this example， the first packets delayed。 And so the sender times out eventually and retransmits in both packets here。

 eventually make it to the receiver。The receiver， of course。

 only delivers one segment's worth of data up to the application layer。

 even though two duplicate segments were received。With these unneeded retransmissions。

 this just means that there are more overall retransmitted segments in the flow， some needed。

 some duplicates， and so the maximum throughput drops even further from here to here。Well。

 we can summarize what we've learned from this second scenario by noting that congestion loss requires retransmission and that n retransmitted packets take up to n times the resources that means buffers transmission capacity as a single packet。

 but in the end these end packets contribute only a single packet to the throughput。

 and so the maximum end to end throughput can actually be significantly less than the actual transmission capacity of a congested router。

In our third scenario we'll consider four senders and four receivers with a sender receiver pair separated by two routers。

 the red flow now crosses two hops。There are again retransmissions。

 so we'll want to be able to distinguish between Lada in and Lada in prime as before。

 and again we'll be interested in the red flows in and throughput Lambda out。Now。

 the red flow shares a link with the blue flow here and the green flow here。

 And this is critical now for a red flow packet to be successfully transmitted from host A to host C。

 it must be successfully forwarded by both routers。

 and this is important because if a red packet makes it through the first router。

 but is lost at the second router， itll have to be retransmitted again by the red sender and cross that first router again。

Another way to look at this example is that the first packet of transmission。

 which is lost at the second hop， will have essentially wasted the link buffering and transmission capacity getting successfully through that first hop only to be lost at the second hop router。

So given this， the question we want to ask ourselves is what happens as Lambda in prime increases for all of the flows？

So heres one way to visualize and think about answering this question as Lada in prime increases。

 the arrival rate to the first hop router on the path will increase， increasing the loss rate。

 and now think about it asymptotically， asymptotically is the sending rate of the first hop sender。

 say the red sender here goes higher than R over 2。

 this first hop traffic will crowd out all of the second hop traffic and this dropping of second hop traffic will happen at all routers。

Meaning that the end to end， two hop throughput for all flows will go to zero as we dial up the sending rate。

 Who zero throughput， things really can't get any worse than zero throughput。

And so another lesson we learn is that in the multihop scenario。

 all of the upstream network resources， the buffers。

 the bandwidth used to carry a packet to a router where it's ultimately dropped are going to be wasted and since that packet won't make it to the destination in any case。

 it'll have to be retransmitted again and attempt to reuse all of the resources again on the end to end path。

So let's summarize what we've learned from these three scenarios。

We learned from a throughput point of view that the best that can happen is that the throughput equals the rate at which traffic's being passed down from the sender's application layers。

 and once a link reaches its capacity， sending more traffic can't increase the throughput beyond the link capacity。

And we saw again that as the link utilization approaches one。

 the arrival rate of traffic to the link approaches the link's capacity that delays can become very large。

When there is packet loss we saw that retransmitted segments， whether they're needed or not。

 can reduce the maximum end to end throughput since links are carrying both original and retransmitted traffic。

 remember， N retransmitted packets will use up to n times the transmission capacity and buffering as a single packet。

 but in the end only contribute a single packet to the throughput。And finally。

 we saw that in the multihop case， upstream resources， buffers。

 bandwidth used for packets that are eventually lost downstream are really wasted resources and that in overly congested scenarios。

 this can cause the end to end throughput to actually go to zero。

 a phenomena that's been referred to as congestion collapse。Well。

 so we've seen that congestion is definitely a bad thing。

 that's why we want congestion controls in the first place so we can avoid those costs that we just saw the next section we're going to take a look at how TCP actually does congestion control。

 but since we're looking at big principles here， let's step back and let's identify two basic approaches towards congestion control and as we'll see TCP implements both of these。

Well， the basic approach to congestion control is simple when a sender detects congestion。

 it should decrease its sending rate。 that would be lambda in prime in our previous examples。

 In the first approach towards congestion control。 The sender infers congestion by lost packet indications that might be timeouts or triple duplicateupate acts or by the measured RTT。

 In this case， the network layer provides no explicit help in indicating congestion。

 it simply drops or delays packets， and it's from these events that congestion is implicitly inferred at the sender。

This is the original approach towards congestion control taken by the TCP IP protocoltocol stack。

 and it remains a central part of TCP's congestion control algorithm today。

In the second approach towards congestion control， the network layer provides explicit feedback to the transport layer indicating congestion。

 and this can happen before there's actually loss or excessive delay。As we'll see。

 this feedback can be provided in several different ways。

 some more recent versions of TCP implement network Ased congestion control together with TCP's original and end congestion control。

 which is actually required。Well， I hope you found this material on the principles of congestion control to be interesting。

 we looked at the causes and also the costs of congestion and we identified two basic approaches towards dealing with congestion。

 a network assisted approach and an end to end approach and armed with these insights。

 I think we're ready now to dive into the details of how TCP actually performs congestion control we'll do that in the next section。



![](img/0dd85e9df9140e3736816b5c9cf25c0c_1.png)

![](img/0dd85e9df9140e3736816b5c9cf25c0c_2.png)