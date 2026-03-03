# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P40：39_传输层技术解析.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

Hello and welcome to the transport layer。 We're working our way up from the bottom of our four layer architecture up to the top。

 So we're kind of at the halfway point。 We've covered the link layer like Ethernet。

 And then we covered the Internet work layer， which is kind of like the postcard layer。 So let's。

 let's review the magic of Ip。😊，The magic IP is this postcard layer that bounces these packets with from addresses and to addresses。

Through you know， 15 or so hops， getting them there。

 getting packets to their destination network from one network to another network as well as it can。

 and then when it gets to the destination network， it finds the final computer on that network。

The magic of this is there is no。Interim long term storage inside the network。

 all the long term storage is outside。 And now we're going to talk about that。

 So one of the things that makes I so fast is that it is not demanded to be perfect。

 It is not demanded to deliver data in order， and it's not demanded to there's no requirement that it doesn't lose data。

 It's fast and barely ever loses data。 But when it does， there's a layer to recover。

 And that's we're going to talk about。Next。So the internet protocol。Is this multi hopop？

Packets can take multiple paths， they can make use of all kinds of crazy links。

 but now we're going to move up one right， we're going to move up to the TCP layer。

So the TZP layer is both simple and complex。The purpose of the TCP layer is to compensate for the possible errors in the IP layer。

 as well as make best use of available resources。So if the network， if the overall network。

From the overall network from here to here is extremely fast。 We want to send data really fast。

 right， If， on the other hand， the overall network from here to here is really slow。

 we want to send data slowly and be efficient because remember。

 part of the goal of the TCPI networking is to share effectively。

 And so we need to be aware of whether our network is fast or slow。

 And those are the kind of problems we solve the TCP layer。 How fast is the underlying。Network。

 how reliable is it？And if something goes wrong， what do we do to deal with that？

So the key ID in TCPIP is that when we send some data， we break it into packets。

 and then we send each one。And then we keep them。Until。

They get an acknowledgement from the other side and then only then do we throw them away。

And at some point if a packet gets lost， it can be sent again and again and again until it finally is acknowledged in the destination system。

 and so that's basically what TCP does is it figures out which packets have or have not made it across the internet layer。

So here's an example scenario， so we got a message that's broken up into five packets。

 we got sort of the first100 characters， you first characters， the second and third packet now。



![](img/d741e22a48d72418e871625766eeff45_1.png)

![](img/d741e22a48d72418e871625766eeff45_2.png)

What TCP does is it speculatively sends a few packets， says， okay。

 let's let's get ahead because if you sent one and waited。

 then you might not make best use the network。 So you kind of guess and dump a few packets out there。

 And so you said let's say we send three packets， cue them up for sending And as fast as we can send them out the back of our network。

 we start sppoing them out the back of their network and somehow two of them make it across the internet to the destination。

 but somehow。

![](img/d741e22a48d72418e871625766eeff45_4.png)

![](img/d741e22a48d72418e871625766eeff45_5.png)

![](img/d741e22a48d72418e871625766eeff45_6.png)

![](img/d741e22a48d72418e871625766eeff45_7.png)

![](img/d741e22a48d72418e871625766eeff45_8.png)

![](img/d741e22a48d72418e871625766eeff45_9.png)

That poor second packet， just like every time I'm doing a lecture。

 the poor second packet never gets it， you don't want to be the second packet in one of my lectures because you're going to get it。

 but somehow the second packet。

![](img/d741e22a48d72418e871625766eeff45_11.png)

![](img/d741e22a48d72418e871625766eeff45_12.png)

Has gotten vaporized。Now time passes and the receiver gets this sensation that maybe maybe maybe something's missing。

 and so it sends an acknowledgeledment back and it says， I'm going to send a note back that says。

 look。

![](img/d741e22a48d72418e871625766eeff45_14.png)

![](img/d741e22a48d72418e871625766eeff45_15.png)

![](img/d741e22a48d72418e871625766eeff45_16.png)

I'm ready for 200， I do have 100 and I'm ready for 200。 matter of fact。

 I might even throw away 300 because it's been so long so I want you to start me over at 200。



![](img/d741e22a48d72418e871625766eeff45_18.png)

![](img/d741e22a48d72418e871625766eeff45_19.png)

![](img/d741e22a48d72418e871625766eeff45_20.png)

🤧。But sender all of a sudden knows that 100 has been sent and so it knows that it can throw this one away now。

 right it's been acknowledged， so there's an acknowledgement stream that goes back and forth。

 So now the sender。

![](img/d741e22a48d72418e871625766eeff45_22.png)

![](img/d741e22a48d72418e871625766eeff45_23.png)

![](img/d741e22a48d72418e871625766eeff45_24.png)

ItSays 200300， and then they make it across。

![](img/d741e22a48d72418e871625766eeff45_26.png)

The receiver says I've got 200， this the 300， and then they send 400 speculatively， 300 makes it。

 400 makes it， and the receiver says。

![](img/d741e22a48d72418e871625766eeff45_28.png)

I got 400， which means now it can cross off 300 and 400 right。

 check those off and throw them away and then send 500 cross and then at some point check those off。

 it's got 500 and another sender can sort of like empty check everything off everything's been sent and it's been acknowledged and we know and so that's kind of an oversimplified view of the kind of bookkeeping that's going on on both sides of a TCP connection。



![](img/d741e22a48d72418e871625766eeff45_30.png)

![](img/d741e22a48d72418e871625766eeff45_31.png)

![](img/d741e22a48d72418e871625766eeff45_32.png)

![](img/d741e22a48d72418e871625766eeff45_33.png)

And so。This right here is， in a sense， the genius of the internet。

 the storage requirements in the middle。The routers， this is the IP basically。

 the network of networks。We didn't design these to require a lot of storage。

 we wanted them to be fast， we wanted them to be agile， we wanted to be dynamic。

 we wanted to be clever but we also gave them right to fail， so we didn't demand storage。

 we didn't say hey， hold on to packets， you know all over the place， just store up piles of packets。

 piles of packets would pile up in these， we don't ask that。No router has to keep the packets。

 a matter of fact， routers are supposed to throw packets away to communicate back and forth between the system that maybe things aren't working so well and don't use me to get to California。

ThisOn the other hand， with hundreds， maybe hundreds of thousands or millions of routers。

 but billions of computers on the outside。So we need a way to make this reliable。

 so we need to have memory to store the packets while they're in flight so we can retransmit。

 but we store the packets in the computers that are outside and there are billions of these computers。

There are billions of them， every computer that you carry around， every laptop， yeah， come hear？

Every time we add another computer to the network， we add storage for packets that are being sent。

 so when your computer or phone is sending across the network， it is responsible。

For retaining its own copies， it does not expect the inner part of the network to do so。

And that is absolutely brilliant。It's what really makes this work。

And so that's kind of a great oversimplification of what's going on。

 and it turns out that there is still a lot of engineering to make that happen。

So I'd like to introduce you to another。Of the innovators that we meet in this class。

 his name is Van Jacobson and I met up with him at Xerox Park。

 he did the work we're going to talk about while he was at Berkeley。In the late 1980s。

 there was this prediction that the Internet was going to die。

And it seems obvious that it was it's a good idea now。

 but back then there was a bunch of folks that felt like。

Academics weren't smart enough to make a network。And and they were like IBM and digital equipment that thought they。

 the vendors should make the network， and we should just pay them to use their network。

And as the NSF net was coming up。And more and more computers were being connected and the backbone was so slow。

 it started to fail。And it looked like the predictions of all of the computer vendors that said academics couldn't build a robust。

 scalable network were going to be true。And so Van Jacobson tells the story very differently。

 but the way I saw the story happening and unfolding in 1987 is Van Jacobson saved us。

The network was crashing。And we all installed band Jacobs and patches， and the network got better。

 And in my recollection， this was the last time it appeared。

That the entire internet was going to crash。So we named it the Van Jacobson Proto。

 and he doesn't like to call the Van Jacobson Proto because he's a。A shy， unassuming guide。 But。

 I think he saved us。 And so this interview is him describing sort of that moment back in the late 80s where。

He invented the slow start algorithm that really is part and parcel of every TCP implementation that you have on every computer that you use。

 as a matter of fact， it's being used to flow control on this lecture right this second as we speak。

 So here's Van Jacobson。