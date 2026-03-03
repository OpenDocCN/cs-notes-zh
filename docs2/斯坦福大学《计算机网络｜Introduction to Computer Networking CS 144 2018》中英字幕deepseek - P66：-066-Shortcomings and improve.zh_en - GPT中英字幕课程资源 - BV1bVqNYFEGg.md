# 斯坦福大学《计算机网络｜Introduction to Computer Networking CS 144 2018》中英字幕deepseek - P66：-066-Shortcomings and improve.zh_en - GPT中英字幕课程资源 - BV1bVqNYFEGg

Today， I'm going to be talking to Dr Naanddiita ducappatti。

 Naandita did her PhD here at Stanford graduating a number of years ago。

 and she worked on TCP congestion control algorithms and alternatives to TCP。

 She popularized in particular， the term flow completion time as a metric for TCP。

 In addition to some of the other metrics we normally use like fair share high throughput。

 and she proposed specific alternatives to TCP that bring mechanisms into the network to try and reduce the flow completion time。

 Anyway， today， she works at Google where she continues to work on a number of different congestion control mechanisms。

 and I invited her here today to talk with us about some of the things she's learned along the way。

Nandita， what are the shortcomings of TCP and the congestion control algorithms that we learn about in class such as TCP。

 Reno， new Reno， etc？Yeah， so。Over time， essentially。

 whereas the network bandwidth increased and has various different kinds of applications。

Came over the internet， these networks and applications challenge TCPs in many new ways。

 let me give you a few examples。The first one being TCP Reno。

 new Reno and even the newer congestion control algorithms such as QBC are fundamentally loss-based algorithms wherein the pump bits into the network until the queuees in the network overflow and losses triggered。

 in response to which they modulate the rate， the problem is that these TCPs required the loss rate to be extremely small such as in 80。

000 segments to sustain a link rate of 10 gigabbits per second over a 200 milliseconds link。

 so that turned out to be one of the big problems a decade back when physics were transferring large amounts of data over transoceanate links but besides that we have a slew of newer problems for example。

 considered the web traffic which have，Trely short transactions。

 request response transactions such as one would find in HTTP or even RPCs that is remote procedure calls within a data center。

 these are all request response transactions The problem is consider every connection TCP connection starts with a one RPP overhead this can be significant if the request is just a single packet or if the response is just it's a 50% overhead or consider。

The slow start where the algorithm ramps up its congestion window over time。

 it starts with a small congestion window and ramps up in every runtra time that is to slow for short transfers。

 such as what you find in web transactions， not just that。

 even the loss mechanisms in PCB are not very optimal for short flow performance， in fact。

 measurements on Google servers show that loss HTTB responses take about 10 times longer than those which have experienced no losses over very similar networks。

So and then there are several other problems such as over the internet these days。

 switches and routers are vastly have large amounts of buffering now back in two decades back where throughput was a concern these congestion control algorithms were designed to fill up these buffers until the buffers actually overflow。

 but the problem is buffers have gotten larger， introduced and as a result these introduced large amounts of delays。

 especially for short transactions that just was by and lost and RTT or a couple of RTTs。

And there are also problems at the other extreme end。

 we also have switches and some browsers with extremely small amounts of buffering and that is also a problem for TCP because extremely small amounts of buffering causes losses in bursts for bursts of or packet trains of packet arriving lose a packet or two almost accidentally TCP things treats these burst related losses as congestion losses and drastically reduces its congestion window and as a result the links are not being able to be filled completely in both extremes TCP's congestion control actually does not work very well a more interesting problem that has come up in recent times is the interaction between browsers and TCP so the way browsers work today is the open several dozens of。

Conctions in order to be able to download the resources from the web pages。 so for example。

 if you go to images。 google。com and search for say cats and kittens then it makes several connections to images1 go docom images2 go docom and so on and so you have a sudden influx of these htV responses coming to your cable or DSL link it's almost like a flash crowd scenario there isn't much of congestion control。

 you can exert on each of these responses because each of these is a very tiny entity but taken together they actually create some bad problems such as overflowing the buffers increase cuuing latency and so on。

In addition to these， the new more mobile networks are also posing some performance challenges for congestion control in PCB。

 for example， the link fading and the link up and down。

 which is very common in layer two in cellular networks。

Tricks TCP to thinking that there is extreme congestion in the network and therefore it should back off and do an exponential retransmission timeout。

So these are the kind of problems that we actually routinely see for when TCP interacts with modern applications and networks。

What are some of the mechanisms and improvements that have been put in place over the years to try and overcome these limitations and shortcomings of TCP。

So one can think of these mechanisms as falling into three broad classes。

 so one can there are end hostst only mechanisms such as so these changes require only server side or only receive client side changes and then the second category of mechanisms are those which require only changes to the switches and routers。

 for example， the active queue management algorithms such as the most recent ones have been Cordell control delay and Pi。

 which selectively draw packets in order to in order to send a signal to the TCP centers that is there are queues being built up at the routers or switches and it's time to slow down and then there are these mechanisms such as RCP rate control protocol or XP MaxNe or DCTCP that actually require。

Changes for both the intermediary network devices as well as the end systems wherein the end systems get an explicit either a one-bed notification in case of ECN or a multibed notification in the case of RCP XAP that tells them explicitly how to modulate their rate however the most successful of amongst these categories have been have been the first one。

 which is really the end system changes primarily because they easier to deploy get through metal boxes and so on so forth and in this category we've seen a slew of new congestion control algorithms such as cubic TCP high speed TCP fast TCP。

 which aim to solve the problem of maintaining high throughput in large bandwidth delay product networks so the way they improve over Reno new reno is that they do not react as drastically。

Two losses and they ramp up much faster when there' is free available bandwidth。

 cubic TCP and high speed TCPs are still fundamentally lossbased TCPs in the sense they cut down the congestion window in response to losses whereas fast TCP is a delay based algorithm that is more agnostic to losses but modulates its congestion window based on the measured changes in the round track time。

And in addition to these of late， there been a slew of mechanisms to make short transactions over the internet faster。

Naturally to make the web pages download faster among these a few of these examples are TCP fast open fast open essentially allows you to send allows one to send data along with the send packet so one can imagine that if a client is issuing a web request and the request is typically fits within one packet you don't have to wait and a round trip time before actually being able to send a request to the server you can now send the request in the S packet itself so that's a significant reduction in the page load time when especially when you do this over and over again you actually begin to notice significant differences in the latencies in user experience latencies then there are a few other changes such as TCP's initial congestion window has has stood。

three segments for a long time recently it was it's been increased to 10 segments in many of the notable open source operating systems。

 there are changes， for example， proportional rate reduction。

 which actually makes the fast retrans algorithm more efficient。

 what the fast retransm algorithm in TCP has been found it's either extreme diversity or to timid。

 what proportional rate reduction does is it actually smooths out the fast retransit and the fast recovery to pump in just the amount of data that has been delivered to the receiver and therefore makes the recovery of losses in shortflows much smoother。

The final area where there has been improvement is in the retransmission timeout RTOs are painful for short flows and RTObased recovery is 10 to 100 times longer than the fast re of fast recovery and so recently there's a proposal called the tail loss probe which actually converts an RTO into a fast rate transmit even for short flows this is significant in reducing the tail latency of short flows because most of the losses in short transfers happen to be tail losses about 70% of an R tail losses and as a result the only way that they can recover is an RTO which often is too long。

In big data centers owned by companies like Google， where you work or Facebook， Amazon。

 Microsoft and so on， there's an opportunity to change it TCP at both ends of the connection。



![](img/6ce50297816cc7a2cd68e89b04c0d170_1.png)

![](img/6ce50297816cc7a2cd68e89b04c0d170_2.png)

![](img/6ce50297816cc7a2cd68e89b04c0d170_3.png)

Both at the server and at the client。This might be worthwhile if you're trying to overcome a limitation that is particular to data centres。



![](img/6ce50297816cc7a2cd68e89b04c0d170_5.png)

What are the sorts of things that companies are doing in data centers to try and improve TCP and congestion control So a lot of the problems in data centers are in many ways similar to the internet and and yet there are some significant differences。

 the similarities are the problems that I've spoken to you about the key performance metrics are the same we still care immensely about latencies。

 especially about tail latencies， either massive over buffering also known as the bufferbl or massive under bufferuffing are is still a problem but the major differences are that we can change now both the ends。

 the server and the receiver so some of the simple changes for example。

 over the internet you have to keep the RTO， the retransmission timeouts extremely conservative because you are。



![](img/6ce50297816cc7a2cd68e89b04c0d170_7.png)

You're trying to encompass a large category of networks such as mobile networks and even the regular wired networks。

 so the the initial RTOs are in the order of seconds， it's one second right now。

 whereas in data center networks， you know and there is no way that you don't need a retransmission timeout in the order of seconds because you know the RTD of the data center within the cluster within a data center is in the order few microseconds。

 so we've been able to so making these timers much more precise and much more tight has been very crucial to actually reduce the tail latencies of the remote procedure calls。

In addition to it， I think the recent work done in Microsoft research and actually in collaboration with Stanford on DCTCP has been has been significant because with just a single bit of information from from the switches。

 the endHs are able to make much better decisions on how to on how to modulate the rates。

 so I would say a better integration of timers， making the timers much tighter。

 as well as getting being able to deploy mechanisms that require some participation the switches in are ways in which data centers are different from that of the internet。

Thanks And Tern， so for my last question， all of the improvements you've described so far are modifications and variations on the basic AIMD based congestion control that was first proposed many years ago。

😊，They all use the same basic congestion control mechanism and modify the sliding window in different ways。

So if you look forward 15，20 years to the future， do you think we'll still be using the same slow start plus AIMD based congestion control that we do today。

 or do you think we'll have replaced it with one or more new schemes that work in very different ways。

 I that's a great question， actually， and I was kind of secretly hoping that you would ask me that question that I。

I sincerely hope that we don't actually continue to be using just AIMD based protocols or you know just slow start AIMD and continue in that route。

 the reason being we are already finding we are already finding not such limitations but ways means in which we can do better so so far we've been doing very pointbased solutions to each of these problems。

 we to we have different mechanisms for web transactions short short web flows for example they don't even rarely go through the AIMD phase they all finish in the slow start phase so we have a different we try to optimize the web transactions differently。

 we try to do something different for mobile networks。

 we try to do something different for video flows just because the video application patterns are very different from just long FTB flows or the short web transactions we treat the data center network。

Slightly differently just because of the extremely short latencies。

 similarly we treat the mobile networks differently。

 we try to do different TCPs for extremely over buffered networks or extremely under buffered network so really my hope is that we stop doing these point solutions to these point problems and instead look at step back and look at can we actually design congestion control that just works for all networks and for all application patterns instead of going about and treating every problem as of this is a special case problem because that's exactly what we're doing today and in that direction you know I think the recent work from MIT。

 the Remi program that generates congestion control algorithms adaptively based on machine learning algorithms I think that's an interesting direction。

And I would really like to see some of these automatically generated congestion control algorithms。

 how to play out in practice， it remains to be seen whether they can actually solve the problems of these very different variety of networks that I've spoken about。

😊，And in general， I think in the other direction， I think the router base。

 the router assisted congestion control haven't seen significant deployment just because they're harder to actually deploy it and do experiments on a large scale。

 but with the recent advances such as in openflow as well as in SDN。

 I think we will see more of the network participation even in congestion control。

 so I'm very hopeful about these two directions going forward。

Thank you very much for talking to us today， Naandita。 Thank you very much。 It was my pleasure。😊。

