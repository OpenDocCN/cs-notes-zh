# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p17 -17-3.3 Connectionless Transport_ UDP.zh_en -BV1UMtueiEaA_p17-

Let's continue our study of the transport layer now by looking at UDP。

 the user Datagram protocol and hey I've got great newsfe this is going to be relatively short because as we'll see。

 UDP doesn't do too much more than frame and reframe multiplex and demplex data that's headed up to and down from the application layer so the topics will take a look at are what happens at a UDP sender and receiver what does the UDP Datagram format actually look like and then finally we'll take a look at the Internet checkum so let's get started by looking at actions that the UDP sender and receiver。

UDP is a really simple。 no frills bare bones protocol。

 and it can be so simple because of the service that it provides is just best effort service。

 UDP basically sends segments and hopes they get to the other side， those segments can be lost。

 They could be delivered out of order。 And so UDP doesn't really have to just do that much。

 And because of this really simple service， there's no need for handhaking between a UDP sender and receiver。

 no need for the sender and receiver to have shared state。 In that sense。

 UDP is referred to as being connectionless。 Also， each UDP segments going to be handled independently of all of the other arriving segments。

Given how simple UDP is one might actually ask why is there even a UDP in the first place Well。

 there's actually a lot of good reasons for this， first of all。

 there's no connection establishment delay， the time between when a UDP sender wants to talk to a UDP receiver and when data can actually flow we'll see that a UDP sender just sends a datagram without waiting for any connection establishment delay so there is no connection state shared between a sender and receiver as a result。

 the UDP headers are also relatively simple so there's little overhead and then maybe most importantly UDP does not provide congestion control that is a UDP sender can blast away as fast as it desires and should the network become congested can still function in the face of a congested network。

 something we'll see that TCP has more trouble with。

So these very characteristics of UDP make it useful for a certain set of applications， for example。

 streaming multimedia applications are tolerant to a certain amount of segment loss。

 but they're also rate sensitive so we can't congestion control them too strongly for DNS and SNM。

 it's important that they be able to operate when the network is in a compromised or some kind of congested state。

 and then finally we note that well if you need reliable transfer。

 it's possible to build that in the application level on top of UDP and that's exactly the approach taken by HTTP3 as we'll see later on in this chapter。

UDP is defined in request for comment number 768 and actually I think it's always a good idea for everyone to read at least one RFC to see what an internet protocol specification looks like in UDP being simple means it's short。

 I think it's only three pages so you might want to take a look if you're going to read one internet RFC this might be the easiest one to read。

Let's next take a look at the actions of a UDP sender and receiver and let's start with the UDP sender everything begins when an application passes an application layer message down to UDP。

UDP is then going to form a UDP segment by filling out certain set of header field values and including the message from above in this example an SNMP message as payload in the UDP segment。

 creating the UDP segment and then passing it down to IP IP in turn is then going to forward that IP datagram onto the receiving IP host on the receiving side。

 a UDP receiver will receive a segment from the network layer below。

 it will perform a check of the UDP checkum， extract the application layer message and then demplex that message up to the appropriate application layer socket。

Well， it's admittedly boring， pretty boring to take a look at packet formats。

 in this case the UDP segment format， but really like eating vegetables like eating broccoli it's something that's actually good for you and when you think about it there's a lot of ideas and principles that go behind what's actually contained in each of those header fields so let's take a look at the UDP segment format。

We see here the structure of the UDP segment and as promised it's pretty simple。

 the header only has four fields， two of those fields are the source port number field and the destination port number field used for multiplexing and demxing as we just studied there's also a length field and we need that because the application data。

 the payload part of the UDP segment can be a variable length and so UDP needs to know exactly how long that UDP segment is。

 and then finally there's a checkum field。One of the fields we just encountered in the UDP header was the internet checkum field。

 let's take a look now at what actually goes into that field and how the internet checkum is actually computed and you should pay close attention here because this is going to come back again when we look at TCP and also when we look at the IP protocol。

 so pay attention here。The role of the UDP checkum is to detect errors that is flipped bits in the transmitted segment between sender and receiver。

 And here's the way to think about it。 Imagine I want to send you two numbers。

I send you those two numbers， but in addition I also send you the sum of those two numbers。

 so you now receive three numbers， any of those three might have been changed during transmission。

 you take the first number you received and the second number you received， you add them together。

 you check whether that sum equals the check sum， the receive check sum that I had sent to you。

If they're different， you know there's a problem。 So imagine I send you the numbers 5 and6 in the sum11。

 you receive the numbers 4， so the five got changed to a 4，6 and 11 you add4 and 6 together。

 you get 10 you check 10 against the check sum 11 that I sent you and you say hey。

 there's a problem with this And so the UDP centerer and receiver operate in a completely analogous way on the sending side。

 the sender treats the contents of the UDp segment that includes the UDP header fields and also includes the source and destination IP addresses of the datagram as a sequence of 16 bit integers adds them together and takes the one complement sum will take a look at that in just a second of the segment contents computes the checkum puts that value in the UDP checkum field and then drops the segment down to IP on the receiving side the receiver computes the check sum of the receive。

Segment again， that includes the header and the IP addresses。

 It checks whether that computed checkum equals the check some field value that was placed there by the sender。

 If they're not equal， as we just saw， then there's an indication of an error What if they're equal Well。

 no errors been detected but might there be errors otherwise， Well， more on that in just a second。

Let's now take a look at how the Internet checkum is actually computed and imagine we want to compute the checkum over216 bit integers。

 In reality， we're going to be computing the checkum over much more data。

 but let's just imagine in the simple case we've got two 16 bit integers that we want to protect with an internet checkum。

 So I take the  two 16 B integers that we see here， I add them together， starting at the right。

0 and1 and base to arithmetic is 1，1 in0 is 1，1 in1 is0 carrying a1，00 plus the carrier is 1，01 is1。

1 in0 is1 and so on。 After we add the 16 bits together， we see we have a one on the lefthand side。

 that's going to be a wrap around。 we're going to add that back into the 16 bit sum that we created to get the final sum that's shown here。

 and then finally to compute the checkum we're going to take the ones complement that's flipped zeros to ones and ones to zeros and we get the Internet checkum shown here。

And so we see that the computation of the internet checkum is relatively simple。

Now here's something you might want to think about。

 What kind of protection does the Internet checkum actually provide against flip bits？

 Let's take a look at an example thatll shed some light into this and imagine that we've already computed the checkum of the 216 bit integers that we saw before。

 and imagine now during the transmission the first number and the second number are actually flipped during transmission。

 So for the first number， the rightmost two bits， the 10 are flipped to 01 and for the second number。

 the rightmost bits 0 and 1 are flipped to 1 and0。So you should convince yourself that the internet receiver。

 having received now two incorrect numbers with the bitfs shown here。

 will compute a checkum which is exactly the same as the checkum that was computed and transmitted by the sender。

 and so in this case， these errors go undetected。Now we'll see later when we look at the link layer and also when we look at security。

 we'll see that there are actually much stronger ways to both detect and also correct errors in bits that are transmitted。

 but I think the take home message here， the internet checks some is a form of protection but it's not going to be foolproof。

Let's wrap up our study of UDP by summarizing what we learned here。

 We learned that UDP is a no frills protocol that with UDP segments can be lost。

 they can be delivered out of order， we've even seen that the internet checkum doesn't provide 100% guarantees against bitfs。

 we also learned that UDP does have its uses， it's valuable in the sense that there's no RtT delay incurred due to handhaking or set and that UDP can function even when network service compromise。

 for instance when the network is congested or overloaded because there is no built in congestion control and we've seen that UDP can help with reliability through the use of the checkum。

 Now if this no frills best effort service isn't enough an application programmer can always use TCP or as we've seen earlier。

 an application programmer can build the additional functionality on top of UDP up in the application layer and this。

is exactly what HtTP3， for example， does as we'll see shortly。

So that wraps up our study of the user data grant protocol we took a look at the sender and receiver actions for UDP senders and receivers。

 we took a look at the UDP segment format and then we also took a look at the Internet checkum now before we actually move on to TCP the other internet transport protocol we're going to want to take a careful look at reliable how do we actually provide mechanisms for reliable data transfer over an unreliable medium because that's what TCP is going to have to do so that's coming up next。



![](img/7d5126cbc5ee2f45171bd77b83fed012_1.png)

![](img/7d5126cbc5ee2f45171bd77b83fed012_2.png)