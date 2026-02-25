# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p31 -31-4.3 The Internet Protocol, part 2.zh_en -BV1UMtueiEaA_p31-

。

![](img/a188ce266271a2aa1809a90882130882_1.png)

In the last section， we spent quite a bit of time talking about IPV4 addressing and the limitations of a 32 B IPV4 address space In this section。

 the two topics were going to cover network address translation and IPV6 have their origins in the late mid to late 1990s when the networking community really began to understand that the exhaustion of the IPV4 address space was going to be an important concern as we'll see。

 both network address translation and IPV6 have a number of other important advantages as well and are seeing increasingly widespread deployment so let's take a look。

Well， let's start with network address translation known as net。 And here's how that works。

 The idea is pretty simple。 Within a local area network， a home network， an institutional network。

 an Internet cafe， all of the devices within that network have an I P address from a special range of addresses known as private I P addresses。

10。0。0。0 s 8 is an example of such an address range。Now。

 datagrams that are exchanged between hosts within this network use these addresses as always。

 there is no net involved， But what about communication outside of this local area network。

 that's where Na comes into play in particular， all datagrams from any of the hosts inside this network and there could be1s。

 hundreds or thousands of such devices that are sent to host outside of the network will all use the same single 32 B IP address。

 So for this example here， although all hosts have IP addresses of the form 10。0。0/ 24。

 when their datagrams emerge from the router here into the larger internet， they'll all have。

 they'll all use the same single source IP address of 138。 76 29。7。

The source port numbers of these outgoing datagrams will be remapped， as we'll see。

 the implementation and management of this translation is performed by this router here。

 which is referred to as a addedted router， a nat router， or sometimes just as a Nat box。So for Nat。

 all devices in the local network have a 32 bit address that comes from one of three what are called private IP address ranges that you see here。

 If you've looked at the IP address on your laptop tablet or computer when you're attached to a home network or institutional network or a cellularul network you may be seen it has an address in one of these ranges。

 Take a look。 and Nat has a number of advantages。 there will only be a single same 32 B source IP address that will be used for all datagrams coming from all hosts behind the net router。

 one can change the address of hosts within the local network without having to notify the outside world since they're all drawn from this private address range。

 the network can change ISP without having to change addresses of devices in the local area network。

 and there are security benefits as well。 devices inside the local network are not directly addressable by or visible to the outside world。



![](img/a188ce266271a2aa1809a90882130882_3.png)

So let's see how Nat is implemented。Well， there's three things a Nated router will need to do First。

 for the outgoing datagrams， the Nated router will need to replace the source IP address and port number for every outgoing datagram with the Nat IP address and a new source port number。

 It's important to know that NatT is transparent， both to the local host and to the remote hosts。

 All a remote host is going to see is an arriving datagram it's got an I address and a port number as usual。

 and the remote host is going to respond using that IP address and port number as usual。Second。

 the Nat router is going to need to remember every translation pair mapping the local source IP address and local source port number to the Nat IP address and a new sourceport number This translation will be stored in a Na translation table and third。

 when datagrams arrive from the external internet and are destined for a host within the local network。

 the Nated router will need to replace the destination IP address and port number for every incoming datagram with the corresponding IP address and source port number stored in the Na table This will all become clear if we take a look at Nat in action。



![](img/a188ce266271a2aa1809a90882130882_5.png)

In this example， the local network addresses are in the range 10。0。0/24。

 and the NAt address used by the router is 138。76。29。7。We see the net translation table here。

 which is initially empty。In step 1， host 10。0。0。1 sends a datagram with sourceport 3345 to destination IP address 128。

119。40。186 port 80 so webserv。The datagram reaches the net router。

 which then changes the datagrams source IP address from 10。0。0。

1 and sourceport 3345 to IP address 138。76。29。7 and sourceport number 5001 and updates the Na table accordingly as we see here。

 note that the destination address and port number are both unchanged in the outgoing datagram。

In step 3， the remote host has replied， note that the reply arrives with a destination address of 138。

 76。29。7。 that's the Nat IP address and destinationination port 5001。

So the Na router is now going to have to perform the inverse mapping When the datagram arrives。

 the router indexes into the Nat table using the destination IP address and destination port number to obtain the local IP address 10。

0。0。1 in the local destination port number 3345 for the host and the process on that host in the home network。

 The router then rewrites the datagram's destination address and destination port number and in step 4 forwards the datagram into the home network。

Well， let's wrap up our study of Nat by just noting that at least initially。

 Nat was pretty controversial。 We have a network layer device mucking around with port numbers。

 which are really an end host issue。 And a purist might say， Well， you know。

 if you really want to solve the IV 4 address based deletion problem。 then let's do it with I PV 6。

 After all， that's why I P6 was even developed in the first place。

 And there are complications created by Nat。 What if an external host wants to initiate contact to a host behind a addedted router。

 This problem is known as Nat traversal。 It can be done， But honestly， it's a pretty ugly hack。

So while NA does have advantages， it has disadvantages as well， however。

 network operators have really voted with their feet。

 thats widely deployed and very much here to stay for quite a while。



![](img/a188ce266271a2aa1809a90882130882_7.png)

Well next we're going to take a look at IP version 6 and as we've noted。

 the primary motivation for IPV6 was the much larger 128 bit address space。

 but there are a number of other important innovations in IPV6 as well and we'll encounter one really new important idea here known as tunneling when we study IP version 6。

 so let's get started。So， yes， absolutely， the main motivation for IPV6 was the need for a much larger address space。

 but there were some other motivations as well。 First。

 IP headers need to be processed at nanosecond speeds。

 This absolutely wasn't true back in 1981 when IV4 was standardized， but has been true for a while。

 given link line rates。 IPV6， as we'll see， enables fast I forwarding。

 by simplifying some of the more complicated aspects of IP V4 router processing。

 those arising from variable length headers， for example。

 Datagram fragmentation and reassembly and the need to recompute the checkum at every hop。

 And secondly， until the 1990s， the Internet was really conceived of as more of a datagram oriented network。

 The datagram was the primary abstraction。 However， more recently。

 the notion of a flow or we might say a connection between endpoints has become an increasingly important。

An abstraction there's been a desire as we've seen to provide services on a per flow basis。

 not just on a per datagram basis IPV6 raises this notion of a flow to a first class object by introducing the notion of a flow label into the IP header。

 as we'll see next。So let's take a quick look at the IPV6 Datagram format。

We see here the 128 B IPV6 source and destination addresses that we've been discussing。

 We also see the 16 B flow label field that we just mentioned。

 and it's important to realize that this field a mechanism for labeling flows。

 but that IPV6 doesn't mandate how flow is defined or how this fields to be used。

 These are really policy issues that are up to the ISP IPV6 provides mechanisms。

 but not policy for flow handling。The 8 B traffic class field is like the type of service field in IPV4。

 It can be used to give priority to certain datagrams within a flow or to a particular class of traffic。

 And like the flow label， this field is really about mechanism， not policy。 The version。

 payload length next header or upper layer fields and payload or just as we saw in IPV4。

 So all of this hopefully looks pretty familiar to you。 And given that this is pretty familiar then。

 perhaps the more interesting issue then， is what fields were in IPV4， but are not in IPV6。

 in particular， there's no checkum fragmentation reassembly or options fields。

 And as we mentioned earlier， this makes the header a fixed length and allows for faster processing。

 fragmentmentation and reassembly needs to be done at the endpoints and options can be accomplished by passing an IPV6 Datagram payload up to an upper layer protocol at the router。



![](img/a188ce266271a2aa1809a90882130882_9.png)

Let's wrap up our discussion of IPV6 by considering the following question。

If we currently have an IPV4 network but eventually want to transition to an IPV6 network。

 how do we actually accomplish that transmission， we've seen that IPV4 and IPV6 are very different protocols。

Well， do we have a flag day say where everyone transitions from IPV4 to IPV6 globally。

 turn off all of their IPV4 equipment and turn on all their IPV6 equipment Well that's difficult for a lot of reasons that you might want to think about。

Instead， we really want IPV4 and V6 to coexist to interoperate as routers and hosts continue to migrate to IPV6 as new equipment is introduced。

So what we'll have， what we do have today is an internet that has some routers that are IPV4 and some routers that are IPV6 and some routers that are both IPV4 and V6。

But how do we provide this coexistence while keeping the Internet running。

 It sort of seems like trying to change the engines on an airplane while the airplane is flying。

 Well， fortunately， it's not that hard。 And the key technique that's used to allow IV 4 and IV 6 networks to interop is known as tunneling。

 And we're going to take a look at that here。 And the key to tunneling as we'll see is for a datagram。

 say an IPV 4 datagram to contain as its payload an IPV6 datagram。 a datagram inside a datagram。

 But an IPV 6 datagram inside an IPV4 datagram， What's that about that just somehow doesn't sound right。

 Well， it's actually not as quite as odd as it might sound。 Let's see。😊。



![](img/a188ce266271a2aa1809a90882130882_11.png)

And here's the way to think about tunneling。 Remember what we learned earlier when we were looking at layering and encapsulation way back in our introduction to networking In this figure here。

 we see two IV 6 routers physically connected by ethernet。

The link layer ethernet frame between these two routers carries an IPV6 datagram as its payload。

 As we see here， This is 100% business as usual， nothing new here。 Well。

 now let's take a look at two IPV6 routers again， but assume that in addition to knowing how to do IPV6。

 they also know how to do IPV 4， just like they know how to do ethernet。And now。

 rather than being connected by Ethernet， these two routers are connected to each other。

 These two IPV6 routers are connected to each other by a network of IPV4 routers。

 How do these two IPV6 routers forward an IP datagram to each other。 Well， the answer， of course。

 is by using the IPV4 network that connects them。In this case。

 instead of sending their IPV6 datagram to each other in an ethernet frame。

 they simply put their IPV6 datagram into an IPV 4 datagram and address and send that IPV4 datagram to the other。

 This is the process that's known as tunneling。 Let's take a look at an example。



![](img/a188ce266271a2aa1809a90882130882_13.png)

Well， in this example， routers A and F are IPV6 only， routers C and D are IPV4 only。

 and routers B and E can do both IPV6 and IPV4。Let's suppose that IPV6 router A over here on the left needs to send a datagram。

 an IPV6gram to IPV6 router F。 Let's walk through what happened。 Well。

 A's forwarding table says that IPV6 router B is the next hop and so the IPV6 datagram here is forwarded to B。

 and note carefully that this is an IPV6 datagram。 The source address is a the destination address is F。

 those are both IPV6 addresses and there's also a flow I field here， which only exists in IPV6。

 So there's nothing new here in getting from a to B。

 but now let's take a look at what happens at router B and this is where it gets interesting。

 It receives the IPV6 datagram from A sees that the destination is F and that the next hop router in the IPV6 network is router E。

 So that's critical。 The next hop router in the IPV6 network。Is E， so B needs to say， well。

 how do I forward this IPV6 a to E？Well， remember now， B and E are connected by an IPV4 network。

 and that's good because B& E both speak IPV4 and IPV6 and are connected by an IPV4 tunnel。

 and in fact， in B's forwarding table， there will be an entry that says to get to F forward this through the outgoing interface that's an IPV4 tunnel to E。

So B creates an IPV4 datagram， addresses that datagram to ease IPV4 address， and that's critical。

Puts the IPV6 datagram as the payload into the IPV4 datagram and forwards that datagram into the tunnel。

And let's take a careful look at this IPV4 datagram that's being forwarded from B to C into the tunnel。

 Note that for the IPV4 datagram， the source is router B and the destination address is router E。

 that's for the IPV4 datagram and of course inside that IPV4 datagram is the IPV6 datagram。

 the original datagram that started from a， and that's got a source of a and a destination of F。

 but that's just the payload inside this outermost IPV4 red datagram shown here。

The IPV4 datagram is then forwarded through the IPV4 network and arrives at E using the mechanisms that we already know really well within the IPV4 network。

 This is really just another IPV4 datagram and it's addressed to E。

 there's nothing new here at IPV4 destination E E says。

 okay I'm the destination for this IPV4 datagram， the red datagram。

 and so it looks inside and finds an IPV6 datagram。

 it then extracts the IPV6 datagram looks at the IPV6 destination address F looks up F in its forwarding table and forwards the IPV6 datagram on the link towards F。



![](img/a188ce266271a2aa1809a90882130882_15.png)

So in this example we've seen that IPV4 is really sort of considered almost as a link layer technology that directly connects to IPV6 routers。

 the path through the IPV4 network can be thought of abstractly as a tunnel that directly connects the two IPV6 routers。

 and in this way through the use of tunneling both IPV4 and IPV6 can coexist to forward datagrams end to end along a path of mixed IPV4 and IPV6 routers。

 the key thing as we've seen here is that at the boundaries between the two types of technologies。

 IPV4 IPV6， we have routers that can do both IPV4 and IPV6 and this is true of all modern routers。

We'll see later that tunnelmings use extensively in cellular networks to support mobility。

 so it's a general and therefore an important concept。

 but you know I've found that sometimes it's a difficult concept for students to get their arms around it first。

 so you might want to think about it some or listen to this section again as it's an important technique that transcends just IPV4 IPV6 in operation。



![](img/a188ce266271a2aa1809a90882130882_17.png)

Well， we've seen that IPV6 was standardized in the late 1990s。 How widely is it deployed today。

 say 25 years later， Well， Google reports that almost 30% of the clients that access its services do so using IPV6 and in the US。

 the National Institute of Standards reports that about a third of all US government domains or IPV6 capable。

 So that's some progress， but IPV425 years later is still by far the more dominantly used technology and you might think well why is that the case。

 well certainly the widespread deployment of NAt has eased the pressure on the IPV4 address space and made the adoption of IPV6 less critical。

 but it's also interesting to think as a contrast about what's changed at the application layer in the last 25 years。

 the emergence of the Web social media media streaming gaming telepresence and more。

 it's an amazing amount of change at the。Aplication layer and it just shows how easy it is to build to innovate and to deploy at the application layer while building。

 innovating and deploying new well plumbing at the network layer takes a lot longer。



![](img/a188ce266271a2aa1809a90882130882_19.png)

In this section in the last， we've taken a deep dive into the Internet protocol IP。

 which lies at the heart of the Internet's network layer， and we've covered a huge amount of ground。

 We looked at the IPV4 datagram format。 we looked at IPV4 addressing。

 we looked at network address translation and we looked at IP version 6。

 And so maybe you're feeling almost a little exhausted now。

 but hopefully you've learned a lot coming up next。

 we're going to take a look at generalized forwarding。

 which will really set the foundation nicely for looking at software defineded networking when we take a look at the control plane。



![](img/a188ce266271a2aa1809a90882130882_21.png)