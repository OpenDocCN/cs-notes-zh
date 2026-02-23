# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p30 -30-4.3 The Internet Protocol, part 1.zh_en -BV1UMtueiEaA_p30-

In this section we're going to take a deep dive into the internet's network layer and because there's a lot to cover here。

 we're going to do this in two parts。 in the first part。

 we're going to cover the IPV4 protocol and addressing Now obviously IP is incredibly important but so too is addressing and actually addressings part of IPV4 you know I used to think that addressing was sort of cut and dry and maybe even a little bit boring but I've learned that addressing has a lot to do with relationships between ISP having to do with administrative boundaries。

 technical issues as small and local as what happens inside a routing table lookup and hardware to as global set of concerns how global addressing and forwarding is done so it turns out addressing is really important and also pretty interesting In the second part we're going to cover what's known as network at dress translation Na and a new version of IP known as IPV6 So I think you'll find this。

Interesting， stated。So let's start with a big picture view of the internet's network layer。 remember。

 we learned earlier about the network layer's control and data plane in the forwarding table that's the router local table that determines the output port to which a router will forward an incoming datagram。

And we also learned in the introduction to the network layer that the forwarding tables contents determined either by distributed routing protocols or by a router external SDN controller will cover routing algorithms and SDN controllers when we study the network layer's control plan。

A key part of the Internet's network layer is， of course， the I protocol， the celebrated I protocol。

 But what exactly is the I protocol。 Well， by looking at this diagram。

 you can see that the I protocol is not about routing algorithms or SDN controllers。

 Those are control plane functions。 Instead， the I protocols about the datagram format。

 It's about how I addresses are structured and interpreted。

 and it's about packet handling conventions， like how to fragment large packets into smaller packets。

 So I is really just a piece。 albeit a really important piece of the Internet's network layer。😊。

The ICMP protocol， which will cover as part of the network layerer control Plan。

 is also part of the network layer。Since the IP protocols about datagram formats。

 addressing and packet handling conventions， let's then start our study of IP by looking at the IP Datagram format。

Using this figure will walk through the fields of the I datagram。 Now。

 I know this might seem a little bit dry， but really anyone who takes a networking course really needs to know this。

 sort of like eating your vegetables。 You know， it's good for you。

 And so you really do have to do it。 and hopefully you'll even love it or find it interesting anyway。

Well， first， there's the version number field。 These four bits specify the IP protocol version of the datagram here。

 of course， we're looking at the IPV4 header。Because an IPV4 datagram can contain a variable number of options。

 which we see here in the Datagram header， the header length field indicates how many bytes are in the header。

 this lets the hoster router know where the payload actually begins in the IP datagram。

Most IP diagramograms don't contain options， so the typical IP Datagram header goes from here to here。

 a 20 byte header。The datagram length field indicates the total number of bytes in the I datagram header plus payload。

 This is needed because the payload can also be a variable size。 Since this field 16 B long。

 The theoretical maximum size of an I datagram is 64K Bs。

 But datagrams are usually no larger than 1500 Bs， which allows a Dgram to fit nicely inside the payload field of a maximally sized ethernet link layer frame。

 The type of service bits were included in the IPV4 header to allow different types of datagrams to be distinguished from each other。

 The definition in use of these bits is really evolved over time for our purposes。

 the most important type of service bits are the2 bits used for explicit congestion notification。

 E C N。 And remember， that's a topic we studied in detail in the transport layer。

 A router sets these two bits to indicate congestion。

 The remaining 6 type of service bits are used to。Differentiate among different classes of traffic。

 which can then be given different service based on their traffic class using the buffering and scheduling algorithms we just studied in the previous section。

The T T L field is a counter that deced by one。 each time a datagram passes through a router。

 If the T T L count ever reaches 0， the datagram must be dropped at the router。

 And so the T T L field is used to ensure that packets don't loop forever or even for a long time。

 if there are forwarding loops。 The upper layer protocol field indicates the transport layer protocol to which the payload in this I P datagram is going to be passed。

 For example， a value of 6 indicates that this datagram contains a TCP segment that will be passed up to TCP。

 A value of 17 indicates that the payload is a UDP segment。The IPI field， flags and fragment。

 offset field are used when a single large IP datagrams fragmented into multiple smaller datagrams。

 This doesn't happen often and actually these fields don't even show up in IP version 6 and so we won't say anything more about them here。

 you can read about them more by following the pointers in our textbook。

The header checkum is an Internet checkum computed over the contents of the IP header。

 remember we studied the Internet checkum earlier and note that since some of the IP header fields change each time a datagram passes through a router。

 the TTL fields decremented， for example， the checkum needs to be recomputed at each router that the datagram passes through。

 that can be time consuming and maybe as a result of this。

 the header checkum field was also removed in IPV6。

We've already talked about the 32 B source and destination IP address fields。

 remember that we just saw in destination based forwarding that an IP router uses the Datagram's destination IP address here to look up the appropriate router output port to which the datagram should be forwarded。

And then finally， there are a number of optional fields in the datagram header will skip those here。

 and then of course the datagrams payload itself， the payloads the data transport layer segment that IP will deliver up to the transport layerer protocol。

Well， that was a lot of fields to think about and to go through and as we mentioned。

 IPV6 is a lot more streamlined than IPV4， and so we'll find fewer header fields there。

Let's start our discussion of I addressing with a few basic concepts。

 The first important thing to know is that an IP address does not identify a host or a router per se。

 but rather an interface， a link layer interface on a host or router routers pretty much always have more than one interface。

 that is to say multiple incoming and outgoing links。 and hosts often do as well。 for example。

 my laptop has a wired ethernet interface and a wireless 8 or2。11 interface。

 each with a different I address。As we've seen， 32 bit IP addresses are written in so called dotted decimal notation with each decimal number corresponding to an 8 bit byte in the address field here。

 the 32 bit binary address is 223。1。1。1 in dotted decimal notation。Well， you know。

 looking at this diagram， it might be a little bit unsatisfying to you。

 It looks like the link layer interfaces， these black lines just sort of vaguely end up in a blue cloud。

 What's up with that。How are these interfaces actually connected together so that one interface can communicate directly with another interface that's attached to the same blue cloud。

 Well， remember that we're at the network layer right now。

 and the connection of these interfaces is done via link layer technologies。

 which are the layer below what we're studying right now。 So one answer to your question would be。

 well， be patient we'll get to that。 But if you're just dying to see what the complete picture looks like。

 Here's what it is。 The host and the router interfaces might be connected through wired ethernet switches or they might be connected through an 802。

11 wireless network。 But there will be a link layer。

 local area network or point to point link protocol。

 typicallyy ethernet or wfi in practice that will be used to connect the interfaces。

 And we really will learn about this just a bit later。 So stay tuned。 And for now。

 back to the network layer。😊，If you take a close look at this figure， in particular。

 the I addresses in this figure， you'll notice that the interfaces that are connected to each other have similar。

 but not identical IP addresses。 That's because they all belong to the same subnet。

 So what is a subnet。 Well， each subnet is a piece of the network that contains all devices that can reach each other without passing through an intervening layer 3 that is to say network layer router。

 that is， they're directly connected to each other via some link layer technology。

 And here's how that ties into addressing。 an IP address has two parts。

 a subnet part and a host part。 And if two interfaces are on the same subnet。

 their IP addresses must have a common subnet part。 And of course， they'll have different host parts。

So let's be very specific in defining subnets， to find a subnet。

 detach each interface from its host or router as we've done here。

 and this will leave islands of isolated networks。 and so in this example here we have three subnets。

Now let's look at the addressing。 remember that interfaces on the same subnet will have the same subnet part of their IP addresses。

 The so called subnet mask says how many high order bits they have in common。

 Let's assume that's 24 bits。In this case， this lower subnet here has a 24 bit address of 223 do1 do 3。

 We say 223。1。3 slash 24。 and these three interfaces。Have addresses that all start with 223。1。3。

The next subnet is 223。1。1/24 note that these four interfaces have addresses that start with 223。1。

1 and this third subnet address is 223。1。2/24。Let's take a look at this network with three routers and seven hosts。

 can you find the subnets， think about it。Well， let's disconnect the interfaces from their hoster router to see the subnets。

And here are the slash 24 subnet addresses。This s notation that we've been using has a name it's called Classless Interdomain routing。

 CIDR， and actually pronounced cider due to its historical origins。

The subnet portion of the address can be any number bits X。

 and a ciderized address is one of the form A dot B dot C dot D slash x。

 where x is the number of bits in the subnet address， and sometimes the D is omted when it's 0。

 Here's an example of a 32 B I address and its ciderized dotted decimal notation。Well。

 let's wrap up our discussion of IPV4 and addressing by posing a question that maybe you've been wondering about。

 how does one actually get an IP address in the first place， and really that's two questions。

 how does a host get an address within the subnet range associated with the subnet that it's going to be joining。

 and then sort of the bigger picture question， how does a network。

 how does a subnet get a range of addresses that are going to be used by devices by interfaces within that subnet。

 let's look at both of these questions。Well， let's start with the first question。

 How does a host get an IP address for its interface Well， back in the day。

 assisted menus to actually manually edit the IP address into a file on that host。

 but we've progressed a lot since then using a plug and play or what's sometimes known as a zerocomf zero configuration approach that's to say an approach that uses a protocol between a host and a server rather than manual configuration to get an IP address。

 the need for a zerocomf approach is hopefully obvious with billions of hosts worldwide more than half being mobile。

 and these are hosts that are constantly attaching to a network and then later detaching and then attaching over and over again。

 The protocol used by a host to get an IP address on a network is known as DHCP。

 the dynamic host configuration protocol。In order to allocate a plug and play IP address using DHCP。

 a network will need to have a DHCP server to perform that function and an arriving client that is a host wanting an IP address will request and receive an IP address from the DHCP server using the DHCP protocol when a host leaves the network。

 itll give up its IP address which can then later be reused by another host or reclaimed or may be renewed by this host at a later point in time。

We're going to take a look at four DHCP messages that well want to study， there are more。

 but these are really the key ones， discover， offer， request and acknowledgement。

 let's see how DHCP works。Here's the scenario we'll look at using the simple network that we've seen before。

 and in this network we see the DHCP server here。Well。

 typically a DHCP server would be collocated in a router and serving all of the subnets to which that router is attached。

 but we've shown it here as a separate server， which also happens with an IP address of 223。1。2。5。

And here's the arriving client that11 an IP address in the 223。1。

2/24 Snetit Now let's take a look at what the DHCP client server message exchange actually looks like。

In the first step， the arriving client broadcasts a DHCP message that will be received on the interfaces of all of the hosts and routers in the subnet to which it's attaching。

 The discover message basically says， hey， is there a DHCP server out there。

 This is a form of service discovery。 The host knows the service It needs DHCP。

 So it sends out a broadcast to discover the server that can provide DHCP server。 DHCP runs over UDP。

 The client uses port 68， and the server will use port 67。 In particular。

 the server will be listening on a socket associated with UDP port 67 for incoming DHCP messages。😊。

And here are the details of the fields in the DHCP Discover message。

 the client's source IP address containing the UDP segment that contains the DHCP Discover message is0 because the client doesn't have an I address yet。

And the destination IP address is the IP broadcast address that is all ones， 255。255。255。255。

And the UDP destination port number is 67， as we just noted before。 Hopefully。

 there will be a DHCP server sitting out there somewhere on the subnet。

 listening for this service discovery message。Note also that there's a transaction ID field。

 it's got a value 654 here， and this will be used by the client to match any reply to this request。

Here's the second step， any DHCP server that receives this broadcast Disc message and there might be several such servers can reply with a DHCP offer message。

 This message basically saysHey， I'm a DHCP server and here's an IP address that you can use。

If we look at the details of this offer message， we see that it comes from the DHCP server with an IP address of 223。

1。2。5， as in our figure earlier and from port number 67。

This offer message is being broadcast to all interfaces on the subnet。

 The DHCP message contains the I address that the requesting host can use。 That's the Y IA DDR。

 your Internet address field and a lifetime in this case of 3600 seconds that the address can be used for。

 Note that the transaction I D here matches the transaction I D of the initial offer message。

 That's to say this is a reply to that message。 A client can receive offers from multiple DHCP servers。

 and this might occur， for example， if there are multiple routers on that subnet。Now。

 the first two steps that we've seen here are actually optional。 The way to think of the third step。

 which could also be the first step if the two optional steps aren't taken。

 is that the arriving client comes in and says， hey。

 here's an IP address that I want to use maybe that's the IP address that it was told it could use in step2 if that step was executed or maybe it's an address that it already has。

 in which case the client is really renewing its use of that address。

 or perhaps it's an address that the client used before。

You can see here that this message is also broadcast and that it contains the IP address that the host is proposing to use and that there's a new transaction ID and a lifetime as well。

The final message is the AC message from the DHCP server saying basically，Okay。

 you can use that IP address with this given lifetime。Now。

 it turns out that a host needs more configuration parameters than just an I address in order to be able to function。

 in particular， it also needs to know the IP address of the first hop router since any outgoing packet from the client will need to be sent to that first hop router。

 it might also need the address of a DNS server to use and also need the net mask。

 the number of bits in its I address belonging to the subnet。Well。

 this could all be configured manually， but it can also be optionally specified in a DHCP message。

 and this is usually the case。So the other really big question that we still need to ask is how does a network get a range of addresses to assign to the devices。

 actually to the device interfaces in its network？Well， in many cases。

 it will be allocated a range of addresses in the IP address range that belongs to the ISP to which it is a customer network。

In this example here the higher level ISP has a/ 20 address range， this ISP could then for example。

 divide its address space up into8， say/23 address ranges as shown here and allocate each of these out to one of its eight client networks。

And now we can start to see a really critical tie between addressing and routing。

 something that we' come back to again when we get to the network layer control plane In this example。

 the parent ISP， which we'll call flyly by night ISP。

 And this example has8 client ISP as shown in the figure here。

 Fly by night need only advertise one address prefix。

200 23 do16 s 20 to the rest of the global internet。

 This single advertised address prefix will be sufficient for the rest of the Internet to be able to route to the two to the 12th addresses in this ISP address range。

This is an example of what's called address aggregation。

 sometimes also called route aggregation or route summarization Note that in this figure the second ISP。

 let's call it ISPs R us says， hey， send me anything in the address range 199。31/ 16。

 we'll come back to this in just a second。Well， this all looks very neat and orderly， but in life。

 well things just generally aren't so neat or ever so perfectly hierarchical。 In particular。

 let's ask ourselves what would happen hypothetically if one of the eight client ISps。

 say organizationization 1 wants to change ISps from fly by night to ISP are us while keeping its range of network addresses。

200。23。18/ 23。Well， fly by night continues to say， send me anything with address prefix 200 23 do 16 slash 20 as before。

 and as we can see here。 But here's the critical thing。 Now ISps R us says， Well。

 send me anything with address range 199 31lash 16 as before but now it also says also send me anything with address range 200 do 23 do 18 slash23 and note the slash 23 here and note that 200 23 do 18 s 23 is contained in flyby nights advertised200 23 16 s 20 address range。

 So what are we to do here。 Well， what's absolutely critical here is that ISps R us has advertised a longer。

23 bit prefix 200。23。18/23， a more specific prefix than the 20 bit prefix 200。

23/16/20 advertised by fly by night。And I hope， oh yeah。 Light bulb has just gone off in your head。

 Remember when we were studying forward tables， when we were looking at what's inside a router。

 when looking up a 32 B I P address， the matching forwarding table entry。

 I that with the longest prefix match。 That's precisely why packets with addresses in organization one's address range。

 will be forwarded to ISps R us， which has advertised。 the longer prefix。😊，Well。

 we've now seen how address allocation， forwarding table lookup using longest prefix matching and the BGP routing protocol that disseminates prefixes are all really intimately tied together。

 and if you've got all of this， you've really mastered and tied together a lot of key concepts。

 if it's still not 100% clear， we'll come back to this again when we study the control plane。

 but maybe think a little bit more about it now if you don't have it quite down。

So we've now seen how a host gets an IP address from a DHCP server and we've seen how customer ISPs can get an address range from their provider ISP。

 but we still haven't answered the basic question at the highest level。

 how does an ISP get a block of addresses， and the answer to this final question is that the IPV4 address Spaces owned。

 administered and allocated by an entity known as the Internet corporation for assigned names and numbers I can？

I can in turn allocates addresses out to five regional registries。

 which then allocate out their portions of the address space to ISPs。

ICN also performs a number of other critical internet functions like managing the root DNS servers。

 managing domain names and allocating protocol numbers。

 remember when we study the IPV4 Datagram format and said that the upper layer protocol number of6 corresponds to TCP and that the number 17 corresponds to UDP。

 those numbers are also controlled by ICN。Well， let's wrap up here by considering IPV4's 32 B address space In 2011。

 ICcanN Central allocated out the last of its available chunks of 32 B address space to the regional registries。

 ICN has no more address space to allocate out， although there's some unused address space still sitting in the regional registries in the next section we'll look at network address translation。

 a technique that allows a single IP address to be used by multiple IP devices and will' also look at IP version 6。

 which has a much larger 128 B address space。 IPV6 was begun in the 1990s specifically because the ITF foresaw the exhaustion of the IPV4 address space。

Well， you see this quote here from Vince Surf， who along with Bob Khan we can really credit as being one of the two founding fathers of the Internet if we had to choose just two。

 they've both been asked a lot about the early days of the experimental ARPpant that later grew into today's internet and about the 32 B IPV4 address space in particular。

And I love this quote from Vit， Who the hell knew how much address space we needed。 Remember。

 when today's Internet architecture was being defined in the 1970s。

 it was a relatively small Department of Defense project。😊。



![](img/f6c89b9b886fef021c5b44035a91bb19_1.png)

So let's leave the last words here to be from Vince Surf I heard him give a really great sort of fireside chat type of talk at Georgetown University in 2017 when I was working in DC and he talked about a lot of really interesting topics but one of them had to do with I's 32 B address space so let's hear it from Vint how did we actually end up with a 32 B address space What calculations did they go through Take a look。



![](img/f6c89b9b886fef021c5b44035a91bb19_3.png)

So now we have four different kinds of networks， the ethernet。

 the packet radiod the packets Ade net and the ArRP net， the original ArRP net。

So we sat down and tried to figure out how are we going to do that and after about six months we had designed the basic protocols that you used today。

 it was just TCP later on we split off the internet protocol for realtime communication。

So the question then was you know， how big did we expect this to be， well。

 honestly we sat down and said this is going to be used by the Defense Department。

 it has to work everywhere in the world because you never know where the Defense Department is going to have to operate。

So we said， okay。How big is this going to be， It got to be global。

 How many networks will there be per country。And we said， well， we had finished the ArRPpanet。

 which is a non trivial national scale network， so we thought， well。

 maybe there'll be two per country， so there'll be some competition。So we said， okay， too。

 and how many countries are there？And there wasn't any Google to ask back then。

So we guessed that 128 because that's a power of two， and that's what programmers thinking。

 So two times 128 is 256 networks。

![](img/f6c89b9b886fef021c5b44035a91bb19_5.png)

![](img/f6c89b9b886fef021c5b44035a91bb19_6.png)

And that's eight bits of identifier。 And then we said how many computers will there be per network？

And we said， remember this is 1973， these are giant air conditioned computers you know that serve  a00 people in time shared modes。

 so we're saying， how about 16 million？You know， what theck？So 16 million is 24 bits。

 so we ended up with a 32 bit address space and if you do the math it's 4。

3 billion possible terminations for the network in 1973 so the answer that was more than there were people in the world at the time I think。

So we thought， well， that ought to be enough to do this experiment， right？So that's what we use。So。

 people say。If you had it to do over again， you know， what would you do and one answer is well。

 I guess I would have chosen 128 bit address space so we don't have to go through this painful。

Transition， on the other hand， can you imagine making an argument of the forum， I need 3。

4 times 10 to the 38th addresses in order to do this experiment。



![](img/f6c89b9b886fef021c5b44035a91bb19_8.png)

How many networks do you have now？Three， how many computers do you have on the networks， 500？

He said something doesn't quite add out， does it so I didn't do it because I wouldn't pass the red face test。

 but I wish I could have。

![](img/f6c89b9b886fef021c5b44035a91bb19_10.png)

![](img/f6c89b9b886fef021c5b44035a91bb19_11.png)