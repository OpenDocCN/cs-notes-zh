# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p20 -20-Wireless Adhoc Networks _ Week 5 _ Network Simulation.zh_en -BV1aQmtYZEPr_p20-

Hi， Lenas， welcome to elements of network simulation。In this session。

 we are going to see a topic on wireless auto。So also called us mobile lot print， called us magnets。

This is what we are going to discuss in this topic。

So the overview of this session is what is wireless or packs。

 what are the different routing protocols， who they are categorized。

 reactive routing and proactive routing protocols， performance comparison of these protocols and simple simulation results for Y Dv。

And DSSDb， this is what we are going to see。的确。So parallel after this session over。

 so we will be doing some experimentation using N3 for comparing these protocols。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_1.png)

So what is wireless or network， So it is a collection of wireless mobile nodes dynamically forming a temporary network。

Without the use of any existing network infrastructure or centralized administration。

So that means that so this kind of network is infrastructureless。

 So that means they do not have an infrastructure directly。

 let's say one good example is so you have a laptop with you。Similarly。

 there are some laptops like this。They are having a w Fi driver in it。So using that three laptops。

 they can able to form a network。Without any access point or any routeors。 So that is what。

We call ourduct box。 So how we from our how do we do that is for the challenge behind the ro protocols。

So this is what colors wireless product networks and ubiquitous type of computing often refer to as pervasive or invisible computing。

 So thats what。And present appearing are found everywhere and per you spread through or into every part of。

 So this network lies everywhere。 So one good example here is you are using hardpot nowadays。So。

 a hard part means。You can use your Wifi device to share the hardpot there， so using this hard spot。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_3.png)

That are also considered under wireless or print bookss。

So properties of attack networks so require devices to cooperate autonomously without any user intervention so that means that these networks operate autonomously all the nodes in the devices network will be operating on their own without any user intervention a rapid selforgan wireless network so rapid selforgan means if there is any failure in the particular node automatically they form alternative path automatically they form another network。

Thats what will self organizing independent of infrastructure。 as we discussed。

 there is no need of access point， but there are two modes with access point。Without access point。

 there are two modes without access point means all the nodes form a head themselves。 Okay。

 so heterogeneous and adaptive。 So they are heterogeneous means each and every node could be a different manufacturer。

 different energy levels， different medium access control， but still they can talk to each other。

 and adaptive means they can adapt to the。Networking behavior。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_5.png)

So adult networking， so a mode of loosely connected networking characterized by the following qualities。

 lack of fixed infrastructure。 So we don't need any fixed infrastructure peer to peer。

 All node access routers。 So here this is what one of the challenging thing。

 So all the node can act as a a router。 So multihub routing。 So multihub routing means， let's say。

 for example， if this is a source node。And there are node here。And there are nodes。 And here。

 there are nodes。 here， there are nodes。And this is the destination not。 So this destination。

 and this is the source。 Now， when the packet is been sent to here。So the packet from here to here。

The packet has to be sent。But this packet。This note they are not reachable from this social destination。

 so what it will do is it will send a packet from directly here here the packet will be sent。

This note forward the packet。 So forwarding node， forwarding node。

 and this node can forward here and then finally forward here。So this is what one in another way。

 this also will be one path。In another way， this also will be one part。So even if this node fails。

 then automatically this path this path will be taken care。

 So this is what we call us multi multi bin half number one， half number two。Hp number 3， H number 4。

 So here we have totally four hubs。 So this is what we call multi hub。Roouting。

 so there are various protocols operating under multip routing。

Then frequent connection and topology changes so usually the topology changes frequently because of the node mobility so here this node can move this node can move or even the destination itself can move or the source can move so any node in the network can move so obviously the disconnection so automatically the topology also will be changing。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_7.png)

So what are the challenges in Auto networks is security the main challenge？So what kind of security。

 whether we put whether we consider information security as network security。

 we have to categories both and we have to there is a very great challenge here。 scalability。

 So if the number of nodes are increasing in the network。

 how do we handle the scalability issues then load balancing integrate between the host So that means that between the host to host connection。

 how they can exchange packet between them。 So there are some call us。Trus based node。

 So that means that each node will have a trust value based on the trust good trust means the packet will be forwarded between the nodes。

 bad trust meanss the node will will not forward the through a particular。Not。

 and quality service is one of the greatest challenge here。

So usually wireless networks have less quality of service and combat wide network。

 but how do we ensure quality of service So there is again one of the challenge。

CPU memory overheader， so usually CPU and that memory will be occupied very few。

Effect on devices battery life。 So this is one of the greatest thing is the battery life。

 so how long the battery can withstand。For this particular kinds are。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_9.png)

These are the different challenges。Then protocol design。 So how do we design a protocol。

So it is must run in distributed environment， So the first issue is the entire network is distributed。

Must to provide look free routes that means air。 Let's say， for example。Between source destination。

 the packet should not be loop。So it should be it should not be in the loop that is a loop free route。

 so the routes should be compute in such a way that there should not be any loop Tell what happened the packet will be rotating in the loop。

Must be able to find multiple routes， so this is one of the again next issue in descending protocol so as I showed in the previous diagram。

We can we have computer three routes so similarly we have to have multiple routes must establish routes quickly So here this is again one of the issues is the protocol should find the effective routes immediately in a fast survey must must minimize overhead in its communication reaction to topology change so this overhead is always a challenge in wireless networks so overhead meanss because of some frequent disconnection in what way the network come up again so in that case what is the overhead occurs over that。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_11.png)

So this also one of the you design day protocol。So。

 what are the different protocols available here So as far as this subject will consider only main four protocols。

 the protocols are based on E Dv。Dr。DSDV， and finally， oilerser。

 These are the four protocols we are going to compare。

So so proactive and reactive to topology changes so this is what the first categor is productive protocol and reactive routing protocol so this is where most of the protocols all these four protocols rise in any any of these productive and reactive and we have flat versus hierarchical architecture and table based demand driven associivity driven so these are the different categories of protocol implementation。

So table based means the routing protocol will be based on the table。

 So so no destination or how the packet will be sent based on the table only the data will be the packet will be routed。

 So， for example， DSDV。It's based on table driven and demand driven means whenever there is a demand。

 the packet will be transmitted。 So Y would is based on demand driven and in fact。

 Ds are also based on demand driven。 So this way we can have the implementation in various。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_13.png)

So in the classification of routing protocols， so we have proactive routing protocol and reactive ro protocol in the proactive routing protocol we have OSr under DSDV in reactive we have DSr and EODv。

So what is proactive what is reactive we will be seeing it。

 So these are the four protocols we are going to evaluate on this entire next two weeks we will be doing only on these two on these four protocols。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_15.png)

Okay， so now priority routing means usually table driven。

 so table driven means based on the routing table， so we usually have a routing table for these protocol。

 so usually based on the routing table。The packet will be routed。

 So here in this fourth point is the route is already known before a packet is forwarder that we said already the routing table is computed they help various parameters。

 So based on the source destination another thing information。

 the routing table is completely filled and based on the routing table。

The data or packet will be forwarded。Whenever any node is dead in between or whenever any node is out of battery or out of this energy。

 then the routing table will be compute again so further we have a higher overhead so because of the routing not only the routing table a and other stuff So we have the overhead happens here。

Have lower latency due to maintenance of routes at all time。

 So maintenance of the route will be at all the time。 So we have lower latency here。

 So this is the problem of this proactive ro。

![](img/f98930a217fe8b8ef7b05e79e2fb54bd_17.png)

Reactive routing is usually on demand so on demand means whenever there is a demand the route will be selected the path will be selected higher latency since the routes have been to be computer on demand that means that latency is higher saying that usually the route will be computer on demand so that means whenever there is a need the path will be computer so it takes more time to get trigger first lower overhead since routes are maintain on demand so the overhead is higher but it here it is low。

Determine a route only when there is a data to。 So this is the advantage of react ro。

So the path will be sent only when there is a data to be sent。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_19.png)

So two protocols will be comparing now because after we understand these two protocols we can able to get knowledge on the remaining two protocols So here would be under re ro and DSDV under productive ro so DSDV means。

Destination sequenced distance vector algorithm Y means are dark on demand。

Dis transor algorithm algorithm。 Okay， so we have another two protocols called us DSR。

 So DSSR is called us。Dynamic source routing。 So this is one of the protocol。 It's similar like E。

 but slightly。Some type powerful than Ne TV and lesser object link state rout。Link state routing。

 So this is the next protocol。 So all these four protocol friendly we are going to evaluate。

The performances。So Y DV， So Y D is purely on demand， as the name says it is on demand。

 so it is reactive。So no roots determined until needed each node contains routing table of next hub information for how to get to every other node。

 so that means that a node will have a path information of other node。

 this node has the information of other node， this node has the information like that the path will be found so accordingly the packet will be。

Send between notes like this。 So each elevator will be having the information about the next two notes。

So here， this is how the way happens here。 So here you can consider this a source。

And this is a destination， destination resource。 So we have a path n 1 and 3 and 5。

Then N 7 thing and here via end1 n4 and like this and n2 n5 and n it like this。

 So we have this three path available So when the YDV packet is been sent first time when they form the network。

So the source initiated the packet and it will send to all the neighbors。

 the neighbors are n3 n4 and the n2。 So once the packet are being sent to the neighbors。

 usually the packet room colors R Ts。Usually， it is call R T S that win a request to strand。

Theres a name of the packet request to send usually RTS is broadcast。

 so this packet is broadcast so broadcast means he will send to all the neighbor nodes。

 Now once n2 is n to sends again some Rt is to each own neighbors。

 So likewise every RtS packet will be across the entire network。 After that。

 the destination will respond via the shutest path possible So in their case we call we called us R E So there is a route records what。

Given him。Route a request。So RQ is route a request。Here's out response。

SoRo response is the next level first level is RC is request first usually when they form an network。

 usually R message will be flooded across the entire network and the clear to send will be their means so only which are node wanted to sending the packet so they will be sending the C message so CT message will be any cost。

So C T is any cost。And R T S is multicast。Asri broadcast。

So this is what happened in RC after this is established， then we will send a route request respond。

 It is R Eq。 So R Eq also again the same way it is on a broadcast channel。 So every every network。

Every node in the network will be sending packets to everywhere till it reaches a destination。

 but see the destination is sending only via one path。

Maybe the shutest path or maybe the path with the limited currency。

 maybe the path with the very low latency， maybe the path with any of the parent I mean good quality of service。

 So based on all this stuff the route response will be sent back to the source。

 then the source will fixed This is the path for the next packet。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_21.png)

L West network farms India， what be。See this source code initiates the discovery process by sending it out request。

to his neighbors， which in turn to their neighbors and so on till it reaches us a destination。

Roout broadcast is usually broadcast and it has the broadcast ID and the IP address it contains two values one is Is。

 another is a broadcast ID Once the neighbors are ready they can send back the RVP to the source node which initiated the RVQ usually RVP is Unicast it will send it to via a path to the source node which initiated the RVQ so which are part it is used the same part the RVP will be responded。

So that is what in your handles。

![](img/f98930a217fe8b8ef7b05e79e2fb54bd_23.png)

Next thing is DSSDV， so which is on the proactive voting protocol。

 it is called as destination sequence distance vector， so it is based on distance vector algorithm。

So it is mainly on destination。Aviidance of routing loops is the main feature in this protocol。

 So routing loops routing loops will be avoid here because the entire ro table is computed。

Pre computer。Each node maintains a roing table to the destination。

 It also contains the number of hubs needed to reach the destination。 So that means that there are。

3 nerves like this each not have a roing table like this。

So this routine table maintain the data like this， so it contains a number of options to the destination it maintains the their value of the route。

Sequence number numbers are used to differentiate between the world and the new rules。

 So every time when a packet is sent， there will be a sequence number。

 the sequence number impairment like this。 So sequence nu。

Plus plus every time when the sequence number is sent it will be added one value extra so that means based on the sequence number you can identify whether the packet has been reached or not。

 So accordingly the world and the new route can be computed using the sequence number。

Updates in the routes are sent periodically to all notes。 So that means that suppose， for example。

 if lets say。If this not fails。tThen how this node can be sent back to packet of this node so this update will be sent periodically to all the node so to update their routing tables so this is a main challenge here in productive routing for operation of the routing table it takes some time to update update and again the update settings are periodically happening。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_25.png)

So here， the broadcast of the route contains a destination address。

Number of hops sequence number of the information and new sequence number。

 So always the highest sequence number will be used。 if the updates have same sequence number。

 then the route will smaller H count will be used。 So that is what the number of smaller hop code will be used。

 So， for example，1，2，3，4，5。 it is a destination node。This is the source， and this is the destination。

 And we have。One word note here。So now， in this case， this is one part。It goes by this。

 And there is another path here。So this is the1，2 hops， but where here is  one，2，3。ForTo four hopps。

 So whenever the sequence number comes here， So the route with the smaller half points will be used they。

This route will be used。Because it has only two hops so two hub strings we are disturbing only two intermediate nodes and here in this case only one intermediate nodes here when we want to go where this path maybe this path when we want to go so how many node we are disturbing node number one。

2，3 so we are disturbing three nodes apart from the source of the destination。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_27.png)

So this is what happened in DSDV protocol。So then performance comparison。

 so anyway we will be dealing the performance comparison using NS3 in detail。

 I will just rush through some of the performance characteristics。

The following characteristics shows the comparison will be Y DGb protocol for various number of nodes start from 10 nodes to 100 nodes so which deliver 10 to00 notess it is compared So what are the different metrics we have already discussed P packet delivery ratio。

아 들어봇。Then we have an N to end delay e to e delay then routing overheadhead So these are the four parameters that we are evaluating for these two protocols。

 Now first thing is packet delivery ratio we can see that the packet delivery ratio should be high for a good network the period should always be high for a good network。

Now in this case， the value here is 0。005 this is in X axis number of nodes in Y axis you can see that the red color indicates here over TV。

On the green indicate， it is DSDV。So in that case， so the YODB has a veteran packet delivery ratio compared to the DSDB protocol。

 So in this case YDB have a apprehena。So， you D。However hand Okay， so this is unpack delivery ratio。

 So PdR is higher than inevitably compared to DSDb。 So P is a ratio between。

Pet received research packet and since the period is high for a indicates the avoid reliability of receiving packets。

PDR determines one of the important material performanceal of the wireless protocols。

 So this is for the P。Next thing is average throughput。 So throughput here。

 So based on the number of notes and number of packets here。

 So average throughput in bits per second year。Now， again， you can see this is for D in。Red colour。

And this is D D in green。So again you can see throughput also is very less in。DSGV。

 whereas it is good in compared to Y D， but some places the throughput is very less here you can see for these number of nodes and run node 90 notess。

So 90 notes，160 notess and 40 notes， there was some issue because of that the throughddhists two less。

But still， it is higher than the DSDV protocol。 So there is an average throughput for the entire node。

So throughput determines the number of packets sent per second of time。

So a good network should always have a higher through compared to the slow network。

So in the in thebo figure， we have seen the outperforms DSTV。So this is the result forex。 So again。

 we have。It would be upper hand。Okay， so two places。 Third thing is end to end delay。

 So delay here is delay should be less， so the delay battle should be less。

So again you can see in in this diagram， represents the delay here。

So this Y Dv and the green thepress sensor theDb， so the average delay just see very less。

 so it is from 0 to 0。1。Second， so this is the delay here。 but here。Up to 0 and0。

7 seconds that is D again， we D our performs。DSD in the case of delay into inter。

So already if we have discussed about this in this also innovative protocol maintain delay variation slightly in the number of nodes are small medium are high。

 so even the according to the number of nodes。

![](img/f98930a217fe8b8ef7b05e79e2fb54bd_29.png)

Size， so even see that。30。So in this case， the number of node is 10， even is00 so。

The slight variation in your。 whereas here， there is a huge variation in。BSD B protocol。

So routing overhead so this is one parameter here。 So the routing overhead here is E D we have a overhead here is up to one。

The routing warrant almost indicates the same as a packet delivery ratio。

 So routing warrant also similar like Pd。The overheaderhead in sending and receiving packets is called routing over it。

 So the overheaderhead in sending and receiving packets。

So that's why this value is almost point number one， but here it is09 to this not much difference。

 but still it is here what be here。Outpers E DV。 So this is what happening in roing over it。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_31.png)

So there are two different protocols we compared namely reactive and routing。

Proactive both routing methods of their pros and cons this presentation also includes the performance comparison of two famous protocols A and DSDV under the active routing As per the results for most of the application AD is preferred over DSSDV as AD is having higher throughput Le delay and good packet delivery ratio of course the routing over it also good。

But E if we also perform filling in case when the notes are good with the energy and non broken ruless。

 non broken ruless。 So that mean non broken root means the。Lo free routes。So， the rules are。

L free in DSDV。 So for those reasons， we can use DSDV protocol because the routing table is fixed so we can use the protocol use this protocol for these applications。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_33.png)

So these are the references。 I have just taken this。Graphs and some content here。

So we will be seeing tomorrow I will publish one more video based on the comparison of various for protocols with all our metrics。



![](img/f98930a217fe8b8ef7b05e79e2fb54bd_35.png)

Thanks for listening。 Thank you very much。