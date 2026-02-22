# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p22 -22-Network performance metrics _ week 4 _ Online Course.zh_en -BV1aQmtYZEPr_p22-

![](img/2c3a9258c30ab0836b5a9be01dc4edac_0.png)

Hi， Les， welcome to elementsementments of network accumulationulation。

We are in week number four so in this week we are going to see a topic on network performance metrics so what are the different performance metrics available for any networking you take for reasonable wide or wireless networking so the theoretical concernss behind the wireless network and wide network performance metrics we are going to discuss now。

In this week itself， we will do lot of examples based on these performance metrics。

 So we will I ask all the learners to。Go through all the videos in detail so that you can understand better about the metrics involved behind the network performance。



![](img/2c3a9258c30ab0836b5a9be01dc4edac_2.png)

So what are the different metrics that we are going to see today is throughput。So through put。

Inindu in delay。Response team latency。Packet drop packet loss， packet delivery ratio and Gi。

 So these are the tools that we are going to see in this session。



![](img/2c3a9258c30ab0836b5a9be01dc4edac_4.png)

So first thing is throughput， so throughput here it is quantity of the data that is being sent in a unit of time okay。

So that means the amount of data that is been sent in a network between two different computers or two different nodes in a given unit of time。

So usually it is measured in bits per second。 So that is we have kilobits per second。

 the small B refers this this B refers the。bits。And capital B usually refers bytes so that's how we just deal the things here usually through Buddh method in terms of Bps。

Bits per second。It refers effective transmission rate。

 so throughput refers effective transmission rate， so that been said the rate at which the packets are been transmitted。

 that is what we call the effective transmission rate across multiple nodes。

Goodput there is another world like throughput called we call as goodput so goodput is the usefulness of the data sometimes called as application late throughput since the useful data is sent to the receiving application。

 so there are two different things called as goodput versus。2不。

So outputput is something we call as usefulness of data。

So that means the receiving application will get a good number of packets。

 throughput means any packet that is come across the node will be the throughput so it could be in the network layer。

 it could be the transport layer， it could be the session presentation application layer。

 but goodput mainly happens at the application layer。

Instantaneous throughput burn average throughput。 So what we can able to see instantaneous average throughput。

 So that's all we are going to see。

![](img/2c3a9258c30ab0836b5a9be01dc4edac_6.png)

So now an the example is， I will just take a node， said say node as 0。And then node one here。Okay。

 so lets say if these two nodes are while wide node。

 so wide not means they have a physical connection between。So we have a connection here。

 So usually we represent two parameters here。 one parameter is the data rate。And there is the delay。

 so usually we mention two parameters for a wide link。 so data red means5 MBps。Coma 2 milliseconds。

 So this is what the two parameters。 So5 M B means5 B is a bandwidth。

 or we call as data rate and 2 millisecond is a delay。

 So delay means every2 millisecond a packet can transmit in this network。Between this node0 and1。

 okay， so now for example， the node0 is a source node and this is the destination。So。

 this is a source。So in this case， what happens is this was not generates packet it generates。

Andcense， unc to destination。That's a bit packet。 So the packets have been sent。我要的。

Or link like this。Its the speed of 2 millisecond。The maximum data can hold its pi MB P so the data goes here。

 Okay， so now at this end， we can enable to calculate on what time or how many packets have been reached the node number one that is called as a throughput。

 So usually that sort throughput。 So this throughput we call it as instantaneous。

Instaneous throughput。 So thats been said between node0 and 1， So we call instantaneous throughput。

Now， suppose， for example， we have another node here to node number 2。

Where again another link is here， So now this node 0 is wanting to send it2 don not number。2。

 so in that case， also， after one is receiving， it will also send the package to the。

It will have another instant in throughput。So average throughput will be， so the T1。

And T2 developed by these tool So that is what we call as the average throughput so the throughput across each and every link will be calculated and the total divider will be the average throughput so this is how the way the throughput will be calculated mainly on the networking So throughput is a powerful metric for any network so let's say wired or wireless network so mainly throughput is affected because of the delay factor because of the network congestion because of the congestion control is not presented in the network so all these reasons have cost on this throughput factor so throughput is the ultimate and the basic any requirement of any network for measuring their performance。



![](img/2c3a9258c30ab0836b5a9be01dc4edac_8.png)

Next thing is end to end delay。So end to end delay means So the delay between multiple notess。

 that is what we call end to end delay delay of an end to end path is sum of delays on all links and intermediate nodes。

 please see that are immediate notess as well as on all links So this is called as the delay usually delays are configured into two transmission delays and propagation delays usually。

So trans delay means during the transmission of packet in a particular link we call trans delay if B bits are sent in R against then B by r is a delay in that link so we have a link like this。

If B bits are in， so B by R we be there。Delay in that particular length。

 So B bits are been set hours against proation delay will be depends on the length of the wire。

 So what is the size of the air， the length of the wear。

 what we use and the speed of the light in the medium， etc cetera。 these things。

matters a lot when the propagation delay happens。 So end to a delay is another network performance metric that is very useful for most of the network。

Again， I'll show you a diagram。 So I have note number 0。系 hell啊。Not number3， for example， so。

This is the destination D， and this is a source， yes。Now I have two intermediate nodes。 So like this。

 it I have three intermediate notes。 So for example， Ill take one。I'll take 2。 I'll take 4。Okay。

 so now in this case， what I do is I have a wide connection here。I between 12，2。

 I have a wireless connection and between 224， I have a wire connection。4 to 3。 Also。

 I am having avoid connection。 So the number need not be order whether the notes could be in any order。

 So please remember that between1，2，2。We have only。Wireless connection。

So they experience wireless connection。 So that mindset said。

 So there is a wireless interface available in node 1 and2 so that they can talk to each other in a wireless way。

 Okay， now， for example， in wide network， I have a data rate is data rate and delay。Usually。

 so usually data return delay will be like this。We write like this。

 So I just use ten B 2 milliseconds。And here I can say1 N，1 will second。And here I will write100 Mps。

Comma，1 will second。So among this， which line could be the fastest line is， this is the fastest line。

This line is a fastest test1 because 1 millisecond， but the bandwidth is100 Mps。

 so that means a very huge line。 So let's say for example， this is IP。 So from this IP。

 this node is getting the internet。 So this could be you are。

 let's say if you are working in a corporate campus you will have a gateway。

 So from the IP to the gateway1 millisecond was the delay and 100 Mps was the bandwidth。Okay。

 it is coming here。 So here between this gateway to a particular switch。

 the data is 1 M 1 millisecon， which is one of the slowest network。This is lowest in slow link。 Okay。

 After the two， it talks to the note number one wirelessly。

 So wireless involves so many other parameters。 we cannot fix the constant。And delay factor here。

 but there could be introducing some， some delay over here。

 So some delay will be happening here based on so many packets。

 So we will be seeing in detail during the wireless network， So we call R Ts。B Cts packets。

 we called hello messages。Then we have wfi issues and all these things matters a lot when we are dealing with the delay and finally from this one the another switch to this node number0。

 we have a 2 millisecond 10 MB basis slightly a better network better link will come let So now。

 for example， delay one。And delay to。And delay 3。And delay for now， the end to end delay will be。

So for example， into and delay calculation will be between。He source note to the destination note。

So including all these things will be taken care。 So that is called we call as a end to end delay。

 So end to end delay means the delay factor between。

The source node to destination node and the time the delay taken in between the particular path so that's what we call as a end to end delay so usually this we call only a delay it's not an end end delay so between 0 to one it not into end delay it simply a delay similarly 122 iss a delay 2 to32 to4 is a delay and 423 it's a delay so into end delay means between the source to destination node how many nodes are involved in between so that is called the end to end delay so that means at what we mean into a delay is when the source is sending a packet after at what time the destination receives the packet so till the time it will calculate the delay factor so that's what Now for example the node one and two if they are moving so the delay might be increasing because the mobility nodes the nodes could be in mobility so they can able to move here and there so further also the delay might be。

Increasing， so this concept is the next concept。 very important in the terms of a network performance。



![](img/2c3a9258c30ab0836b5a9be01dc4edac_10.png)

So next thing is response time and latency so response time in the sense that a response time can be defined in so many places in the computer architecture in em systems in networking we call so many things but response time and latency are use use the both words are assumed to be same in when network when networks are considered in embedded systems what we say is the time difference between。

The set of appearance of the inputs and the associated outputs is called as the response strand。

 so that been that node is sending some data。On what time the packet the node is been received again by the same source the time difference between them is called as the response stream latency also measure the same in case of networking so just see that latency is a measure of delay。

In a network latency measures the time it takes for some data to get its destination across the network it is usually measured as a round trip delay。

 so we call it as R Tt。Maybe I will show you another video on how to use this performance metrics on a real network I'll just show you in now we can see the next video。

So here we call us usually call us round trip type。roundund trip time。So that's what we usually call。

 So maybe you might have seen the pink command in some of the operating system。

 we can use pink command。 just check out some of the。

IPSS of or any Google site or anything even youing it it will be sendinging you the round trip time so that means the time taken by the by your node from to the particular server how long it takes so that is what this the peak command below so this is what we call as latency or the round trip time So if the latency is very good enough that means it the value is very small that means you have a better internal connection you have a better。

Latency system so that is what we call usually it is measured in milliseconds。

 usually the latency measured in milliseconds because for each and every query your query might be going across the globe so you will let say for example if I use this commander p。

Ww，w dot。Google dot com， when you type this command。

In Linux or Windows or Macin any machine in a terminal if you tried this command。

 you may be getting a delay something let's say 5 milliseconds delay and 10 millisecond delay。

 So every packet will have a different delay factor。

 So maybe I'll just show you a demo in the next video so you can able to see that So what happens to the latency of this particular system So if the delay is very less then you can understand that Google servers are very good enough that your internet is also very good enough sometimes because of your internet connection it might be getting a factor。

So， that is what we call latency throughput mainly gets affected because of the latency the latency is very high throughput also gets affected because of the congestion in the particular path。



![](img/2c3a9258c30ab0836b5a9be01dc4edac_12.png)

So that's what we call latency， Okay， so usually latency means let's say I have a source node。

I have a destination more。Okay， I will send a packet。usually called pink packets。

Use sleepinging packets。 And from there， I get another packet here。So T P， so I call it T P。And T R。

 So Ill calculate。T P plusier。Equal to。R TD around two time。 So that means the time taken。

From reaching the source to destination。And the time taken again coming from a destination to the source。

 So that is what we call as a round trip take。 So based on this time factor only I can able calculate the latency of a particular。

Network， if latencies keep on increasing to a higher value that means your network performance is day by is decreasing decreasing you need to change the network or change any parameters or anything to improve the。

Latency so latency is again one of the greatest thing in the network performance。

 so most of the concernss what we are discussing here all of the very important network performance metrics as far as the network is concerned。



![](img/2c3a9258c30ab0836b5a9be01dc4edac_14.png)

Next thing is packet loss packet drop so again this is one of the great concept again in the networking so packet loss and drop so you might have studied packet loss and packet drop you may be thinking that both are same but there is a difference between the packet loss and the packet drop。

So， a packet class means it occurs when owner or more packets of data traveling across a computer network fail to reach the destination。

 so that means that sometimes it fail to reach a destination。

 some the destination sends a packet back the source might be。Might not be receiving the packet。

 So that's how the packetet loss happens。 Packcket drop is on an interface。

 whereas packetet loss is last packets that were dropped in the path。

 So I'll just show you in a demonstration here。 So let's say there are two node here。Okay。

 so node 0 and node 1， I just use it here。So node0 is inning a packet。Somewhere when it goes。

 there was congestion in the network your packet gets dropped。So this called us。

 and this node one is waiting for the packet。 It doesn't receive。

 So that winner this is called us a loss of packet。Lo a packet So the entire packet get lost。

 so this is packet last because the destination doesn not receive the packet data and at later point of time this node send a packet here。

The packet is received here， but usually in any node。Yeah。In any note。We will be having a queue here。

 so usually all the notess at this point here I'll say there will be a queue。

So whenever the packet is being sent by the node， the packet will be put into the queue so Q means E E first in first out so that been set the insert will be at the back so that been set。

So， every time。The packet is added here and then the packet will move。

 so suppose if the queue is full。Q is full。 What happens to this notice in any new packet comes。

 there is no space in the queue。 So obviously。The packet gets dropped。

 so once it reaches a destination and it gets lost， then we call this as。Dropped。Okay。

 so that is what packet glass。 so packet rub is due to size of the cube is full。

And due to malicious behavior at the north suppose okay Ill show in the next slide packet loss due to link congestion and radio frequency interference。

 So that is what these two differences between packet loss and drop maybe well just explain you again。

Norode 0。Not what， okay。So usually these nodes will be having a queue。So。

 totally the typicalq size is 50 bytes， usually the network optimized size of the queue is 50 bytes similarly this node also have a queue。

Okay， so now I assume both are connected via in the on wide network with some delay and some data rate。

Okay， so now the packet is been sent via this node when the packet is been sent。When it goes here。

 suddenly， the packet gets dropped。So the packet gets dropped like this。

So that means that note number one is waiting for the packet。 it doesn't get。Reach the destination。

 So in that case， we call it as packetla。Because it get lost somewhere。

 So even the packet can be reaching here again， it gets up， still it is lost。Facilities， packetless。

Okay， so this is packet loss。 whereas us in the next time when the packets are been sent。

And the packets have been sent。It comes here。It comes to it。 But now the entire queue is full。

The packet reaches the destination， So it reaches the destination。Reachs the destination。But。

No place to hold。No place to hold the packets。In that case。

 what happens this packet after it reaches destination， it gets。This we call it a packet drop。

This is one reason。 Other reason would be this node will this node is here。Maicious node。

 So that means that it could be another reason called malicious node。

So malicious wind the job of the malicious node is to drop the packets the whatever packet it receives it just drops many packets so it is malicious activity in this case we call it as a packet drop so packet last and packet drop there is a main difference packet last pins it lasts somewhere before it reaches a destination the packet may be getting last packet drop pins it reacheses a destination but there is Q size are because the malicious activity the packet is getting。

Interrupted。But what is the reason for this packet last stop。What is the reason。

 One reason is the congetion of the network。So congestion means for example， link congestion。

 So this link， for example， there is another node here。And there is another node。 Okay。

 so this node also sending packet via this node。And sending data via this to this north via the same line in their case。

 what happens both are in the same line so there could be congestion that is one reason Another reason is a ready frequency。

Radio difference。So because of the radiode that been set if it is wireless nodes if there are wireless nodes。

 so across two different multiple nodes like this， so there will be in everywhere。

So that's how this radio interference will be a major reason。

 So usually what happens in a wireless node， we have a node like this。About this node。

 we have another area， above this node， we have another area。This is called us this area。 I mean。

 this area is called us。Transmission range。And this area is called interference range。So。

 because of this interference， if any node is there in interference range of this node。

 there could be chances that the packet might be getting lost。Because of the interference。

 So that's how happens。 So went when there is a power line。When the when there is a power line goes。

 so obviously what happens near the telephone line and the power line， this will be。

Packet glass will be more big of the power lane crossing the telephone line。

 so that is what this packet glass central will do。



![](img/2c3a9258c30ab0836b5a9be01dc4edac_16.png)

So next thing is packet delivery ratio。 So what the packet delivery ratio will do is。

The number of packets received divided by the number of packets sent that is what we call packet delivery ratio。

The packet delivery ratio is the ratio of packets successfully received to the total packets sent。

 So as per this formula sigma number of packet received de by sigma number of packets send。

 it is desired that maximum number of data packets has to be raised to the destination。

 So a good network is the P the higher the P higher is the performance of the network。

So good P good network So we call so thats what packet delivery ratio and P increases the performance of the network also improves so thats what we call as a P so packet delivery ratio usually will always be should be high so only then we can able to understand that whatever is been generated and sent it has been received at the receiver side。



![](img/2c3a9258c30ab0836b5a9be01dc4edac_18.png)

Our last parameter is a jitter， so jitter is again one of the important concepts in the networking。

So Jitter usually occurs in wireless systems on Vvop。 So Vyp。

 you know that Y is over intendedended protocol。So one good example nowadays， we use Whatsapp calls。

And we use telegram and we use so many applications。

 So most of them are using vivovo E P technology for this。

 So usually j occurs in wireless systems and wipe system where multimedia packets are usually。

Usually or multimedia packets。 So jitter is when certain packets of information are dropped。

Are sent out of order leading to a jumbled conversation。 Please understand whenever you just。

Talk to somebody over Whatsapp or any other call so what there happens is there there might be some call disturbance or some kind of amount of packet you may not get it there could be reason because of the jitter so either in your internet connection the jitter could be not good enough。

Or because of the higher the jter value， so you made some packets might be getting dropped。

 there could be one reason。Typical value of the jitters should be less than 40 millisecond。

 So if you have a broadband connection or if you have any 3G or 4G connection， So 3G4G broadband。

Wifi connection you have。 Please check。The network speed with Gi。

Sppirit if it is more than 40 milliseconds， then being said。A more than 5040 to 50 milliseconds。

 if it is more than that then that means you need to change your internet connection because the jitter is very high。

 So that's what the j calculation is。So what causes jter。

 so mainly jitter is caused by retro congestion。Wireless networkss and bad hardware。

 usually wireless networks have higher j。Because of radio interference。

Then quality of service so because Q O is is very less in wireless networks。

 So because of this reason the digital could be very high and bad hardware。

 So if you have a very old hardware。 So let's say a user router here。So let's say I have a one，2，3。

4 that totally 300 Mps router， for example， if I have 300 Mps router。

Before 300 M I was having only 1，50 M B S router for wfi。 Okay， so in this case。

 the jitter is let's say170 milliseconds。 sometimestime it happens 170。

 but after I replace to this router， the jitter came down to 60 milliseconds。

Still 60 milliseconds is less。 I need to go for another routeor。

 but maybe the source what I'm getting could be having some issues so because of that I could not simply change it。

 but why I'm telling here is because of the bad hardware also your jetter value will be so in the same internal connectivity earlier I was getting 170 milliseconds now I am getting only 60 milliseconds so that means that almost because of the improved hardware I jetter values comes down so that's what here upgrade the internal connection upgrade the network hardware So I have upgrade the network hardware in still if you feel the 60 milliseconds and 780 if it goes on increasing then I could be changing the internal connection to so that I can upgrade the package so that I can have higher bandwidth so that。

He speed so that I will get a better internal connection or I can use a jter buffer So jitter buffer means I will be having j buffer all the packet will be put into it when someone calls me the pack before reaches a destination the packet will be put into the queue or put into buffer。

 So from this buffer everything will be fed taken one by one and then give it。

 So in this case we can use a jter buffer。 So in these methods I can use jitter。😊，Latency。

 end to end delay and packet delivery ratio， packet loss， packet drop and throughput。

 all these performance metrics are very important of analyzing any networks。



![](img/2c3a9258c30ab0836b5a9be01dc4edac_20.png)