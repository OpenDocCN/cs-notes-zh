# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p29 -29-4.2 Whats inside a router_  Part 2..zh_en -BV1UMtueiEaA_p29-

。Well now that we've got a really good appreciation for the pieces of the router， the input ports。

 the output ports and the switching fabric， we're going to dive down deep into the topics of packet scheduling and buffer management and we've seen how important these are with the internet's best effort service model。

 packet loss and packet delay have had a profound effect on what has to happen the transport layers and the application layers。

 so now we're going to dive down deep into the topics of packet scheduling and buffer management and we'll take a look at how those can be used to control and also mitigate packet loss and packet delay。

Well， let's get started by first taking a look at input port queuing。

 Remember that we saw earlier that input port queuing can happen when the router switching fabric is less than the combined rates of its incoming links。

 In this case， more packets can arrive in a unit time than the switching fabric can possibly move from the input side of the fabric to the output side。

 and so queuing can occur on the input side。A cuing phenomena that's unique to the input side of the switching fabric is what's known as head of the line blocking or HOL head of the line blocking occurs when packets at different input ports want to go to the same output port。

If only one packet at a time can be transferred from an input to a given output port。

 and if there are k packets that want to go to the same output port。

 then K minus one of those packets are going to have to wait on the input side of the switch。

And if packets have to wait， they can also block the packets behind them in their input queue from moving forward。

 and this is what's known as head of the line blocking。

Take a look at this example here where the colors of the packets correspond to the output port to which they're destined。

In this example， say at time T， we see the top and bottom input ports have a red packet destined to the upper output port。

In one clock tick， the upper red packet is transferred from the input to the output side of the switch。

The blue pack in the middle， it's also able to move from its input port to its output port。

The red packet at the bottom， however， is blocked from moving to the red output port since the packet at the top was already transferred there。

 And so the green packet behind this lower red packet experiences head of the line blocking。

Let's now focus on the output port side， since this is really where the action is。

 and let's start by seeing why buffering is needed in the first place。

At this output port we have a link with transmission rate of R bits per second and let's say we have a non blocking switch capable of delivering n times R bits per second to the output port now we can see why buffering occurs。

Bits can be arriving at a rate of n times R， but bits can only be drained or transmitted out at a rate of R。

 When the arrival rate exceeds the departure rate， the buffer will fill。 And since buffers of finite。

 there may not be enough buffer space to store all of the packets that need buffering and packets will have to be dropped。

 there simply isn't enough memory to hold all of the packets that need buffering。

 So right here at the output port is where congestive packet loss occurs。 And， you know。

 it may be tempting to say， well， it's really the switch fabric's fault。

 It's theing packets too fast at a rate of n times R， when the link can only drain at rate R。

 So we should slow the fabric down。 but that's not really the cause of the problem。 Is it。

 Think back to our earlier discussion of principles of congestion control。

 The real cause of the problem。 Congestion is that there are too many transport layer senders at the edge of the network sending too many packets too。

Packetsoo pass cross at this congested output port。In the face of buffering and congestion。

 there are a couple of decisions that will need to be made at the output port。First。

 if there's not enough room for all arriving packets。

 a packet drop policy will be needed to determine which packets are going to be dropped。

And if there are multiple packets in the buffer awaiting transmission。

 a packet's scheduling discipline will be needed to choose which packets among the many queued packets will be transmitted。

 next。 We'll look at both drop and scheduling policies in just a second。 Now。

 there are a lot of really important ideas that we just talked about here on this slide。

 So make sure you've got it all。 It's really important。Well， you might be thinking。

Given buffering is such a big concern how much buffering should a router have and more to the point。

 you might also be thinking， well， hey， shouldn't it be a good idea to invest in a lot of buffering with a lot of buffering。

 there'd be less packet loss since there'll be more buffers to observe the burstiness in packet flows。

 having more buffering must be a good thing， right。Well。

 it might surprise you that even after 50 years， the question of how much buffering is the right amount of buffering is still pretty much an unresolved issue。

 there are some recommendations。You can take a look at RFC 3439 and find a rule of thumb that says the amount of buffering should equal a typical RTT。

 say a couple hundred milliseconds， times the output link capacity。

There's also been more recent theoretical research that assumes that transport layer senders are generally independent of each other and recommends dividing the RFC 3439 amount of buffering by the square root of n where n is the number of flows crossing the link。

 and that's a lot less buffering。And while you might have the sense that large buffers will generally result in less loss。

 and you could be right， Large buffers do have a downside。

 Large buffers mean larger delays and larger R T Ts。

 Large delays are bad for gamers and for interactive teleconferencing users where tens of milliseconds really do matter。

But maybe even more importantly， large RTT delays mean that TCP senders will be slower to detect and therefore react to congestion。

You might recall that when we studied delay based congestion control。

 we encountered the saying that we want to keep the bottleneck link just full enough to keep the link busy。

 but no fuller。 But that was from the perspective of the sending hosts。

 When we think about the amount of buffering， we really do want buffers to absorb short term statistical fluctuation and packet an arrival rates and to keep the link busy。

 but not to have so much buffering that congestion control reaction times becomes slow and sluggish。

 Well， buffering sort of like salt in cooking。 You've got to find the right amount just the right amount makes things better。

 but too much can really ruin things。Well， who would have thought that buffering and queuing at an output port could actually be so complicated and so subtle。

 And you may ask yourself， why is that， And it's really because it's here at an output port buffer that the global behavior of potentially thousands of active senders worldwide are converging as their flows all pass through this single output link。

 we see the convergence of global internet scale behavior at this one location deeply inside the internet。

 That's pretty cool。Well， we're next going to move on to the mechanisms for the buffer management and packet scheduling and we'll find it useful to think of an output port abstractly as a queue as shown here。

 Of course we're all familiar with queuing systems in our daily lives， at banks， at buses。

 at bus stops at food stores at metros and many other places。

 Think about how many cus you've been in today。Packets arrive to the queue。 They wait for service。

 and they're eventually selected for service， receive service， and then leave the queue。

 The link layer functions as the server when a packet's bits are being transmitted over the outgoing link。

 that packet's in service。If an arriving packet emerges from the switching fabric to find there's no free buffer space。

 either that packet's going to be dropped， and that's known as taild or an already cud packet could be removed from the buffer and dropped to make room for this newly arriving packet。

 say according to some kind of priority mechanism， for example。

 there might be a policy to drop low priority packets。

 say carrying end user TCP traffic rather than high priority packets。

 say carrying network management and control packets for the ISP。

As we also learned when we studied network assisted congestion control。

 a buffered packet may also be marked with a congestion indication to signal that the link is becoming congested。

 We learned earlier that for the internet's explicit congestion notification ECN mechanism。

2 bits in the I header type of service field are used for ECN marking。

 we'll see these bits in the IP Datagram header in the next section when we study IPV4 but it's here at the output ports and where congestion occurs that these bits are going to be set。

We can now look at several packet scheduling disciplines that are used in practice under first come first serve scheduling。

 packets are transmitted simply in the order in which they arrive to the output port。

 We're all familiar with first come first serve queuing。 I'm guessing it's what people do the most。

 We all join the back of the queue and customers are serve from the front of the queue。

 samee thing with packets。We're all familiar with priority cues。 You get that with airlines。

 Platinum， D， gold， silver or bronze， class of service。 They all sound pretty fancy and great。

 but you'd definitely rather be platinum than bronze。

 And I think we all probably have an intuitive understanding of how priority disciplines work having been in the lower priority class of service and seeing later arriving people in higher priority classes。

 getting service before us。Under priority scheduling。

 packets arriving at the output link are classified into priority classes on arrival at the queue。

 as shown here， where we have a high priority red class of traffic and a lower priority green class of traffic。

The priority queuing discipline will transmit a packet from the highest priority class that has a non empty queue。

 that is has packets waiting for transmission。 The choice among packets in that same priority class is typically done in a first come first serve manner。

 This animation shows packets arriving from the top。 And during service。

 according to a priority discipline and then leaving the queue。In this example， packetet1 arrives。

 finds the queue empty and enters service。While packetet1 is in service。

 packetet 2 and3 arrive when packetet 1 finishes， both packets 2 and 3 are buffered。

 but packet 3 is chosen for transmission even though it arrived after packetet 2。

 since it has higher priority than packetet 2 and so on。



![](img/e9529736823a223c3d030240f0abb947_1.png)

Well， we've now learned about the priorityqueuing mechanism。

 but you may still be wondering what is it that defines a priority class in the first place。

 How is it determined what goes into priority class 1 or priority class2， for example。

 and this is actually determined by the network operator by the ISP。 the ISP may decide that well。

 network management traffics really important， it's the highest priority class voiceover IP gets higher priority than email and so on。

 And you remember that by looking at the transport layer port numbers。

 one can determine what type of traffic is being carried by that datagram Now。

 traffic type is one way in which priority could be determined another way might be on the basis of source or even destination addresses。

So here's another possible way to classify traffic into priority classes。

 Imagine that a company is willing to pay an internet service provider to give its packets better service。

 its packets are less likely to be dropped， its packets suffer less delay as a result。

 it's a search company， its search results get to users faster if its voiceover IP the voice is more responsive。

 if it's streaming video， there's less spinning wheels。 Well。

 we've got the scheduling mechanisms to do that whether or not a company is able to pay for that kind of better service。

 actually gets us into the topic of what's known as network neutrality。

 we're going to cover that in just a second， but first let's wrap up by looking at a few more scheduling disciplines。



![](img/e9529736823a223c3d030240f0abb947_3.png)

So we've seen first come for serve and priority scheduling under round Robin scheduling。

 packets are assigned to classes as with priority scheduling。 However。

 rather than there being a strict service priority among classes。

 a round Robin scheduler alternates service among classes。 For example。

 a round Robin scheduler would choose a packet from class 1， followed by a packet from class 2。

 followed by a packet from class 3 and so on。 And if there's no packet of a given class。

 the scheduler moves on to the next class in the schedule。

A generalized form of round robin queuing that's been widely implemented in routers in practice is known as weighted fairqueuing W FQ。

 like priority and round robin scheduling， arriving packets are classified and queued in the appropriate per class waiting area。

 We see here， red， green and blue packets waiting for their service。

 awaited fairqueuing schedulers schedules classes in a round robin like manner for serving class 1。

 then serving class 2， then serving class 3， and then assuming there are just three classes repeating that service pattern。

 weighted fairqueuing differs from round Robin in that each class can receive a different amount of service in any interval of time。

 And here's how it works ideally。Each class of packets I has a weight W subi。

Let's assume that all of the weights， the sum of WJ， say sum up to one。Under weighted fare queuing。

 during any interval of time during which there are class I packets to send。

 Class I will then be guaranteed to receive a fraction of service W sub I。

 That means if the link has a rate R， then each class of service will get a guaranteed minimum amount of bandwidth W sub I times R。

 And so we can see how weighted farequeuing allows some type of a bandwidth guarantee to be made on a per class basis。

Network neutrality is an area where our technical interests in computer networking intersect with social。

 political and economic considerations well we've already seen the mechanisms for sharing resources。

 but what about the social， political and economic considerations about how those resources are shared。

 let's take a look。Network neutrality is about the laws and policies that govern how an Internet service provider can use the traffic control mechanism that we've just learned about packet scheduling in particular。

 to control network traffic。 So what are some of the questions that network neutrality addresses。

 Well， it's about a number of different things。 It's about free speech， For example。

 Can an ISP refuse to carry some types of traffic。 For example。

 certain types of news or political opinion。It's also about encouraging innovation and about encouraging competition。

 For example， must and ISP give all companies big and small， equal treatment of their traffic。

 As you probably know，  different countries have been adopting different stances with respect to these questions。

 We're going to take a look at what's happening in the United States since this is well documented and has all been playing out pretty publicly。

 Our textbook's got some interesting references about net neutrality worldwide that you might want to take a look at。

In 2015， the United States Federal Communications Commission Order on Pro and Pro an open internet defined three clear bright line rules associated with network neutrality。

 Let's take a look at what they are。The first bright line rule is no blocking。

 And here's what it says。 It says that an ISP unquote， shall not block lawful content， applications。

 services or non harmfulmful devices subject to reasonable network management Now there's a lot packed in there。

 the word lawful and applications， services and devices。 Well， this rule about blocking traffic。

 And there actually was a case involving an ISP that had a practice of blocking its customers from using Voage。

 which is a voice over I P service that competed with this ISP's own telephone service that would not be allowed。

And notice the phrase subject to reasonable network management。

 We'll cover network management when we cover the network layer control plane。

 but note here that it is allowable to block traffic for network management purposes。

 Sa if the network's been degraded and only trickles of traffic can get through。

 then it's best that network management traffic be able to get through。 Of course。

 the question of what reasonable network management is is left open to interpretation。

The second bright line rule is no throtling， that is an ISP quote unquote。

 shall not impair or degrade lawful internet traffic on the basis of internet content。

 application or service， or use of a non harmfulmful device， again。

 subject to reasonable network management。Note here the words impair or degrade。

 There was a case not too long ago where an ISP was judged to be interfering with bit torrent peer to peer traffic。

 And it was doing this by internally creating and sending TCP reset packets to bit torrent client and servers。

 executing at the end host。 This caused the host to close their bittorrrent connections。 Basically。

 the ISP was closing the TCP connection underneath the bittorrrent application whose traffic it really didn't want。

 And then finally， there's the bright line rule of no paid prioritization。This means， for example。

 that video streaming traffic from all video streaming service providers must be treated the same。

 For example， that one streaming video service provider cannot pay to get its packets better service on their way to the customer。

 And， of course， we've seen how this can be done from a technical point of view via priority queuing。

 Well， you might ask， why no paid prioritization since paying for a priority service seems， well。

 almost like a fact of life， at least here in the United States。 Well。

 one of the arguments is that if say a video streaming service provider can pay for better service。

 And if that successful incumbent， the existing service provider can pay a lot。

 then this introduces a high barrier to entry for new competitors。 And， of course。

 some countries want to encourage market competition。

But there are counterarguments to this claiming that creating additional revenues for an ISP by having paid prioritization is a good thing from a competitive point of view。

 since that makes the ISP marketplace more lucrative。

 and so more companies will want to invest in the ISP market or ISPs will want to invest more in their infrastructure。

And then finally， there are laws going back almost 100 years that have regulated the telephone network as a telecommunications service provider。

 but there's much less regulation of information service providers。 So what is an ISP。

 Is it a telecommunication service provider or an information service provider。 Well。

 it turns out from a regulatory standpoint。 the answer to this question matters a lot in the US。

 but the answer to this question has really not yet been finally determined。

Well these bright line rules are from a 2015 US FCC order。

 more recent FCC orders have actually rewritten much of that 2015 order。

 so until laws are written and until there's further litigation and case law adopted。

 I think it's fair to simply say that the situation continues to evolve。

 and I think that's true in many countries。It's interesting that we've had the ability to do traffic priorvaitization since the internet first became public nearly 30 years ago。

 so although the Internet has a strong technical foundation， as we've seen three decades later。

 our social， political and economic policies governing this creation have not yet been fully defined or agreed upon。

Well that wraps up our discussion of packet scheduling and packet buffering and also what I hope was an interesting sidebar into the topic of network neutrality and more generally it wraps up our discussion of what's inside a router。

 remember we also looked at input ports， output ports and switching fabrics coming up next we're going to take a look at the internet protocol IPV4 so stay tuned for that。

🎼。

![](img/e9529736823a223c3d030240f0abb947_5.png)

![](img/e9529736823a223c3d030240f0abb947_6.png)