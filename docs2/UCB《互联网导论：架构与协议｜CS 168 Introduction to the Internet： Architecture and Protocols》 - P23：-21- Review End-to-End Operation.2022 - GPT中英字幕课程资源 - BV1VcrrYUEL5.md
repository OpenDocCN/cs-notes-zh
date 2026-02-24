# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P23：-21- Review End-to-End Operation.2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Okay， let's get started。 I hope this attendance record attendance is due to voting or something。So7。

 are you going to split today's flip lecture。Make sure you get all your questions in and you understand this completely。

 This is the perfect venue to make sure you understand things。 The plan was for us to， you know。

 we've got four lectures by viewing， but we're really going to focus on this question of how all the pieces fit together and kind of the end to end operation。

 And we're going to do that through a mix of review examples and actually hands on illustration showing you how you can do this in practice。

😊，I suspect we'll get mostly through the end to end operation。 If we have time。

 we'll actually do HTTP and DN S in more detail。So with that for today。

 we're going to start by looking at this question of how L 2 and L3 work together。

To achieve and to end communication。 And we've kind of talked about each independently this very last lecture。

 which I hope you watched these lecture was actually about how the two work together。

 And we're going to focus on that because we found that that tends to be where people get most the most confused。

 And so simplified view of the Internet for today is that we have L3 that serves to interconnect a bunch of L2 or Ethernet networks。

 So we're going assume all L2 networks are ethernet for today's lecture。

reason this gets confusing is L2 and L3 have separate addressing structures。

 separate ways of doing forwarding and routing。 and yet they work together。

 every packet is carrying in L2 and L3 header as it makes its weird every step in the network。

 and both addresses and both styles of forwarding come into play。

 And so knowing exactly when one kicks in versus the other and what goal each one is playing is he I found that's where people tend to get confused。

So let's start with addressing。 So we have， as I said。

 separate addressing at the L2 ethernet Mac addresses and IP addresses。

 which for today we're gonna to say IPV4 addresses at L3。

 they are different in that when you think about where they come from Mac addresses are kind of hard coded in your device adapter。

 your network interface hardware that you plug into your machine whereas IP addresses we've said it depends on where you are in the network topology So they are actually assigned by operators。

 it's either manually configured or we've they assigned dynamically through DHCP。In Mac addresses。

 we tend to think of them as flat addresses。 So they're not aggregation friendly。

 whereas I addresses， you know， everything we've studied， they have this hierarchical structure。

 they're hierarchically allocated， and you allocate them in this way so you can aggregate or combine a whole range of I addresses into one single prefix。

Again， Mac addresses are portable when you take your laptop and go to a different place。

 you take your Mac address with you。 That's not the same for your I address。

 If you move from Berkeley to some place in San Francisco and plug into a different network there。

 you're going get a different I address。And finally， the role they play is， again， very different。

 Your L2 address is used to get you between two host that are on the same ethernet or local network。

 whereas I addresses， this is the Internet's end to end addressing scheme。

 This is what gets you across the Internet。AndSo they have very different properties。

 as you can tell， these properties are not， I would say， independent。 They are interrelatedd。

 So the fact， for example， that your Mac address is hard coded in your hardware implies that when you move your machine。

 your Mac address goes with you。RightThe fact that your address goes with you means you can't aggregate them because you could have any addresses on your network。

 So you can' rely on a clean allocation that you can combine into one prefix。And this。

 the inverse is true when you look at the properties for I P addresses。

The fact that we want them to be aggregated implies that you have to assign them based on where you are in the network。

 which means you have to assign them dynamically， given that who can come and go。

Any questions on addressing so far。Okay， I have a few why do we need both L3 and L2 addresses？

Any thoughts。嗯。是。对。So there two kind of sides to this story， And let's look at it both ways。

 First is why not use Mac addresses as a global identifier。

 And that's exactly the reason that was stated you can't aggregate them。 So it's not going to scale。

We have a billion plus entities on the Internet。 You would have to have one entry in your forwarding table for each one。

 So Mac addresses are a non starter because it just doesn't scale。Why not use I P addresses at L 2。

And I think you're getting at an answer。But more crisply， do you。

 do we think it's fundamentally impossible。To have I be addresses it out to。嗯。

It's definitely the part about it's sufficient to use an L2 address is true。

 I would say it's stronger than that that it's convenient to use an L2 address。

 And so the goal of why we have or why we like L2 is it solves this bootstrapping problem。

 We've said L through your address depends on where you are in the network。

 which means you have to be assigned an address。And if you remember even the early steps of how end to end operation works。

 you have to get to your first hop router。 So there's an initial bootstrap phase by which your host discovers its IP address。

 discovers how to get to its first hop router。 And you could imagine。

 we use Lto as a very convenient way to do this because it has that broadcast discovery mechanism。

 you can reach your first hop IP router once you know it Mac address。

 So it's a very convenient way of bootstrapping。 If you ask me whether I think it's fundamental。

 I say probably not， but you would have to extend IP in order to do the functions that Lto is currently doing it would need a flooding mechanism you wouldn' need to be careful about bootstrapping routing within your domain before you can get out of it and so on。

 And so by the time you're done doing that。 I think I would have had a lot of the functionality that Ethannet had。

So the fact that Ethernet and Lone does that for you is just it' convenient。 We have bootstping L3。

Some of it is also， would say historical。 The fact that by the time people started stitching together networks。

 we already had a number of ethernet networks。 So it made complete sense historically to reuse it。So。

 you know， recap the answer， why do we need both， They kind of had do different tasks for us under different constraints。

 We need L to scale。 We need this hierarchical assignment of addresses。

 which is what holds out Mac addresses。But the， on the other hand。

 we like the fact that L2 networks have this plug and play or configuration free operation。

 And so that's very useful for bootstrapping L3。Does that make sense？

Yeah so bootsrapping and discovery general， what is the problem here is that a host。

 if you think about it when you bring it up， the only thing it knows is its Mac address。

 It's L2 address。 That's all it comes with。 And so everything else you have to discover before you can communicate with the remote host。

 And that is the role of Al and DHCP。 So very quicklycap of open DHCP discovery protocols is address resolution and DHCPs dynamic host configuration protocol。

 They both operate important to remember within the hosts local or L2 network。

And they both rely heavily on the fact that we have this broadcast capability。

 which when you think about it。That's a very sensible primitive by which to bootstrap something。

 If you don't know addresses dress， if you don't know where things are， broadcasting is convenient。

But again， it doesn't scale。 So doing it within a local network makes sense。

A very simple in operation。 the initiating host broadcast a packet saying who has this IP address and the everyone hears it。

 the host that has or the entity that has that address respond with its Mac address。

 So the request is broadcast， the response is kind of uncast。 but at the Ethernet layer。

 DHCP is how a host kind of learns or when it comes up， discovers its context in the I 3 world。

So this means its I address， its neck mask， the I address of its first H router。

 and typically the I address of its DN S goes over。It's a quick review of how DHCP works。

 It's pretty simple protocol。 The client starts by saying。

Sending a discover message saying I need to be configured。

 usually you have multiple DHCP servers on the same local network。 But for now。

 let's say one of them responds saying here is my offer。

 So this is a potential IP address your net mask and so on。

 all the parameters we talked about the client then picks one responds with broadcast saying I'm going to request this particular offer and the server response again saying I acknowledge you now have this IP address By the time we're done with all four messages。

 that is the point at which the client has its IP address until that point it can't claim to own that IP address。

We said a few listened carefully to Muphy that DHCP uses UDP。 It's built on top of I P。

So this should give you samples because it doesn't know the I P address of the DHCP server。

It doesn't know the Mac address， either。嗯。It doesn't know its own address yet。

 And so how does this actually work。The answer is broadcast。

 All of these four messages are broadcast。And they broadcasted both the IP La in the sense that you use a special broadcast IP address。

 which in turn translates to a broadcast Ethernet address。Okay。

 so we're not actually broadcasting at the I level that that isn't a capability of I P。

 The only reason we have that。Broadcast I P address is it tells us stack to put in a broadcast ethernet address。

And then， you' actually broadcasting。At the Internet network。Yeah， so why did D HP build on top of I。

 Why did it not build directly on top of Why is it not an ethernet level protocol。Its great question。

s actually historical reasons。 it's a protocol that's used to bootstrap I。

 And so the designers wanted it to be only I dependent， not dependent on a particular L2 technology。

 So if we built it on top of Ethernet， we would have had to build a DHCP on top of every possible L2 technology。

And certainly， at the time， Ethernet was one， but certainly not the obvious winner as an L2 technology。

 And so this way， you have a general protocol。That only mostly only speaks I P。

 And then you just have this last translation from an I to a local broadcast address。Makes sense。

So key ideas in both our and DHP， we use broadcasting heavily。And that's fine。

 it's broadcasting in general doesn't scale， but it's fine here because we use it locally。

 And then we use caching to remember the results。 So when you get back the response to an a query you cache that in your a table for a while。

 The same thing with DHCP Murphy talked about you have a lease So you get a response you get your IP address you hold it for a time。

 That's a lease period。And then you periodically， you refresh fresh it。 If you don't give fresh it。

 the DHCP server takes it back。嗯。So you repeat the question。Yeah。

 so this is DHCP will only actually get broadcast on your local network。

 So the only value for that IP address is it tells you you're stack to convert it to a layer to broadcast address。

 which in this case would be the ethernet broadcast。

 But you're never actually you don't have a router that is looking at the broadcast I address and saying what's my next hop and then at the I layer sending it out over multiple interfaces。

 You actually rely on L to broadcast。Yeah。嗯。嗯。Yeah， this is your。

 your question underlying this of I'm following where you're going correctly is this would be a way of doing I P without needing L2。

Is that what where you were going with that question that we all send our packets to the goer and the goer knows where all the hooks are。

 So why did we need L to。So， you know， think about it this way。

 What if you were multiple hops away from that goto。Guy。

 how would you know you might know the IP address of that route， but how would you know to get there。

You would have had to bring up your。IP level routing protocol。Before anything else can work。

 But you guide that you could do it。 I think if we added flooding to an I P network。

Some kind of scope flooding。 And we had this kind of strict ordering where you said。

 I am going to bring up inter internal routing before I can do things like DH CPPO connect host to my first top router。

 Then， yes， we would have had the equivalent of what L2 does。

 But it's mechanism that I P doesn't have and doesn't need when you have Ethernet。Where was that。

 Okay， Okay， Caching， What happens if your client， you get a DH CPP address and then you go down。

What happens to your address。I just want to hammer home the value of this kind of lease。

 this notion of a time to live her lease。So got an IP address。It has a leaves， and then I clash。

 however。There's no problem， right the DHCP server after the lease expires。

 it's not hearing a refresh fresh request。 So it reclaims the IP address。

 so we've not lost any IP addresses。What if the DHCP silver crushed。Yeah。Right， so typically。

 you would refresh fresh your。 But if the DHCP server is down at some point in time。

 you won't get a refresh， So you would run out of， you would not have an IP address anymore。

 So you could even just bring up a DHCP server from a cold start。And or everything restarts itself。

 Just fine。 You， you would have some outage time。But it would the system would bring itself back to a correct state。

 People avoid having the outage time by having multipleHP servers。 But even if you didn't。

The system would come back to a correct state。 That's the nice thing about this。

 what we call soft state that I have stayed for a certain amount of time。 and then I refresh it。

 And if I don't can't refresh it， then I just delete it。Ptra and discovery。

 So we said a host is born with only its Mac address， and it had to discover additional information。

 So we should now know， let's say this is a host A。

 Where does host A get its I address should now know that's DHP。Where does Hoste get Bs IP P address。

 So A wants to talk to B。We did that， too， but it was not a bootsrapput。Ds。You have some name。

 You resolvedd it into Bs IP address。 What is B's Mac address， if B S local。We used O。嗯。

What is your first Hs Voer's IP address？How did we get that？It's too much of a protocol too。DHCP。

 so DHCP gives me my I P address， my net mask， which is my prefix。

My first hop route is IP P address and my DNS resolvers IP address。

All of them I P addresses because DHCP is bootstrapping healthy。 It's bootstrapping I IP。

So it's giving me I addresses for all of these。TCP tries quite hard to be agnostic to L2。

What is my first hope route's Mac address。Where did I get that。U。Any questions。

 the examples of the walk tool we do is not going to make sense of。These answers don't make sense。

You you're thinking of like a router with two links with a link connecting it to another router or。

はい。对。 okay， great。 so you， you are a host to it。 You have your host。

 It has one interface connecting it。 The only thing that host knows initially is its Mac address that is burnt into that interface。

So what's the first thing the host is going to do It's going to come up。 and it's going to say。

 I need I P level information。 It's going to broadcast a DHC P request saying。

 give me an I P address。 It's going to get back a response that gives it an I P address。

The I P address of its first hop routeer and then other stuff that we ignore for now。

So I have those two I addresses。Now， if I want to get out of my network。

So somehow I have an I address of some destination。 Let's not well know about where you got it。

 And so I want to send a packet。So I， I take that packet， and I say it's not in my network。

What is it that tells me whether it's on my network or not。The subnet， the mask。 Okay。

 so I look at my own I address， which I now have。 I look at the I address of the destination。

 and I compare it to my mask。 and I say this， this host is not on my network。

That tells me I need to go to my goer。 My first stop goer， because my go is going to get me out。

But I only know the I P address of my first talk about。So what am I going to do。

 I'm going to out saying， I'm going to broadcast again on my local network saying what is the Mac address of my first helicopterpo。

And so my first talk about just going to be sponsoring， this is my Mac address。So at this point。

 I have all the information I need to get the packet to that router。

I'm going to put create a back I P packet to the destination。

 put the Mac address of the first top route and send it over Ethernet。

And the Ether L2 network is going to carry it to the first helicopter。

And then the first talk out is going take it from there。Yeah。

And we' will step through that in a minute。You want the routeer to broadcast the。

When let's not go into malicious goers。 if you wanted to be a malicious goer。

There's just so much you could do that。Just drop packets， it's probably the easiest。

Was your question limited to malicious voters， or。OkaySo let me。

 I think let me maybe go jump between the examples and。Actually， let's keep going through this。

 if it's not clear the step by step operation when we get to the examples， hold me back。

It's more questions。 What's the difference between broadcast and flood。

We've talked about flooding when we did spanning trees and so on。Not quite。

 So the difference is actually that broadcast is a communication abstraction。That says。

 I want this packet delivered to everyone。 Fllooding is actually a mechanism。

That forwards the packet to everyone。But it doesn't necessarily mean you can use flooding to implement broadcast。

 It's a natural way of implementing broadcast。But sometimes if you remember from learning switches and so on。

 when you didn't know where the destination was， you flooded it。

But your goal was not to reach everyone。 Your goal was to reach the one destination that you didn't know where it was。

So flooding was a technique that we used to get the packet to everyone。

 broadcast the goal is actually to deliver the packet to everyone。So it's a very subtle difference。

 And typically， we use flooding to implement broadcast。So in terms of communication abstractions。

 at this point， we've studied four of them， Unicast。Any cast in the context of DN S。

 when we said you want to get to any one of the good name servers。Remember your DNS lecture。

Multicast was when we said we want to get a packet to a group of receivers。

 We don't talk too much about multicast in this class So don't worry about it。 And broadcast is。

 we want to get the packet to everyone。That's the goal of the communication abstraction。

So you can think of broadcast as a special taste of multicast in the sense。

It's a group with everyone in it。What packets does a host operating system see？SoNow。

 let's say we're in a shared Ethernet context and there are all these packets going around on the cable。

 on the shared media。What packets is the network interface card actually going pick up and send up to the host to us。

How do you know whether they're supposed to be for that？And the layer to， the Mac address。

So your network interface card or L2s listening to a shared Ethernet medium or listening to its cable。

Looking at all the packets that come in。Is going to pick up a packet if the destination Mac address matches the horsemic address。

All of the destination Mac address was a broadcast Mac Mac address。Also。

 if it's a multiclass Mac address for a group that the host belongs to。

 but we're not going into multicast， so don't worry about that。Okay。

 so this is your network interface card。 looking at all the packets going back and forth， flooded。

 Unicast， whatever packets， the ones it picks up are ones destined for itself。

 which is basically my address or broadcast packet。

So if you flooded a packet with a destination Mac address。That was not yours。

That host should not pick up the packet。 Or itll see the packet on the wire。

 but it's not going to send it up to the host operating system。

What if I sent a packet that had say as my address， Let's say。 But Alex's IP P address。

 What would happen， What would say as。Operating systems C that juveov but another juant。

So if you are a host， you receive a packet。 It's your Mac address。But it's not your IP address。

What would happen to that packet？Okay， so you will。

 The network interface card will pick up the packet because it has the right Mac address。

 It will pass it up to your O S where your I P implementation is。

 There you're going to look at the I address and say this was not my packet and drop it。

Last one of these slightly tricky questions is open L2 O and L3 protocol。要就。

It's a little confusing as an answer。 It's an L2 protocol。 If you go back and look at more slides。

 you have an ethernet headdo。 There is no I P head on an out packet。 It's just an ethernet packet。

 but it tends to get confusing to people because I is translating between an I P address。

And an L Mac address。So the IP address is like a parameter or a protocol。 But on the wire。

 if you look at the packet， it's， it's a ethernet packet。There's no IP header。On and off， I。关生。

L2 and L we have separate forwarding and gouting。 We know this at L2。 We've done learning switches。

 SDP， flooding all of that。 If you have a shared medium ethernet， which honestly。

 I don't think there are very many of them left these days。 Gouting is kind of trivial。

 You just put the packet on the wire and you're done。I pay。

 we've learned about all the ways in which you do I routing from， you know。

 having configured routing entries， either static entries or default route entries or whatever we've learned through routing protocols like OBF。

 PGP and so on。Remember， always a packet。 Data packet generally contains both an L 2 and an L3 header。

With L2 and L3 dresses in each。Eth addresses are global。

 That means they stay the same from the source to the destination。The network doesn't mess with。

For the most part， with I P addresses。But the L2 addresses， and we're gonna to see examples of this。

 They change as you go from one L2 network to another along the N to end path。

And so packet is generally forwarded on this combination of L2 and L3。 We'll get to it in a minute。

 So what about routers， This is something that might have been easy to miss from of his lecture。

 He had this example up here， and he had a router。 And he， if you notice。

 you have his router has two interfaces， and it also has an L2 and an L3 address for each interface。

Okay， so on this side， the route is participating in this L to network。 And on this side。

 the route is。Thece on this L2 network。And it has an I address for this interface that belongs to this subnet。

And an I P address on this interface that belongs to this subnet。

So we have an L2 and an L T address for Ger interface。 So a goer might interconnect to L2 networks。

 That was this example。There's another one that I want you to think about。

 which is that you can have two routers interconnected by a quote unquote， Ethernet network。

 It's not。 It's really just a single link。But from the way the protocols work。

 it's effectively a separate ethernet network。 So this is like one ethernet network that has two。

Posts on it or two Mac addresses on it。 This is a separate Ethernet network with two Mac addresses on it。

呀。Yeah， that's the next slide。 We'll on to the question for just a minute。Okay。

 does this picture make sense to everyone？行。If it's confusing， think about it this way。

 that the job of a router is to connect multiple to our local networks。

And so that's why it has multiple interfaces。 right It's connecting to different networks。

 And each of those interfaces is a participant in the local network that it's connecting to。

So more questions。 Why do let us get their I P addresses for this class。

 We're gonna say they're configured。You could also have something like THCP。

 but that's where those interfaces on each of the router， each router interface got its IP address。

 We're going to assume the operator configured them。

How do routers discover then neighboring routers L2L3 addresses。

 so this is going back to this picture？How does our discover Mac 2 A and IP2 a Again。

 you could be doing。 you could manually configure them。 That's going to be our assumption。

You could be doing up。There are also a whole bunch of specialized protocols， something called L LDP。

 which is linked level discovery protocol and so on。

 by which a router could discover its neighbors addresses。 We're not going to go into those。

 So for this cluster just say， we're going to assume the network operator went in and configured them。

3官。Okay， so this is starting to get at the question of when are we switching between the two。

 Let's think about a packet at a host going down the layers。

And this will tell you when you're going between L 3 or L 2。 So you started the application。

 It had some data to L 4。With a destination address， Lfo， this is your transport。

 Just packetizes data and hands of packet with a destination I P address to L 3。

What is L P going to do， It's going to look at that destination IP P address。

 and it's going to decide if that destination is on the same network as itself。People getting it。

 So this host is on some local L2 network。 So it's going look at their destination and say。

 is this on my network。How is it going to do that by looking at the subnet mask？

If it is on the same network， then your next top is the destination。And at this point。

 how are you going to reach that destination to L2。Because it's on your L2 network。If it's not。

 then you're going to look at what your next routeer should be。Okay。

 because that's going to take you closer towards the destinations network。Yep。Right。

 that would be from one routeer to another。 We are now talking here about a host。And how it gets。

The packet to， where should it send it to the routeer or should it send it directly over the ethernet network to the destination。

Make sense。So other the host， it's deciding whether it should send it directly to the destination or the goer。

And that's based on looking at whether。The destination is as the samely fixed as yourself。If it does。

So at that point， you know what your next top is。 It's either the destination or the routeer。

 But in either case， you know the IP address of your next stop。So you then hand the packet to L2。

El is going to out。For the I address， for the Mac address， I'm sorry。

 And then send the packet out over L2。Makes sense。Al。So we got the the Mac address。

 and we're good to go。 Let's think about traveling up the layers at a vouer。

 And this is going to get to。Where the routing protocols and so on come in。

 So now let's say that a packet arrives at the interface for routeer。

And it's now at the L2 implementation at that route。That interface had a Mac address。

What is the routeer going to do， It's going to say if the destination Mac。Matches。

The Mac address of this interface。哎。What is that telling me， It's telling me that at the L2 layer。

This packet was destined for the routeer。So reached its destination at L 2。Is this making sense？行。

So at this point， you're done roing at L2。 So what should you do。

 You strip off the L 2 head and pass it up to L 3。嗯。

And now I look at the destination IP address in my I level gouting table。

 How did I build that through all of the gouting protocols we talked about。

So I now have the outgoing interface at the Lhel。And now how I just send the packet out over that interface using exactly the same steps as from the previous slide for how you send a packet down the layers。

Making sense。哎。If it's not， so that means the destination Mac address was not the Mac address of this routeer。

That means that you're still traveling through your L2 network。

So you're going to look up the destination Mac address and figure out what the next top is。

But you're now making an L2 forwarding decision。What is the case where I got a packet？

An ethernet packet with a destination Mac address。 That was not my Mac address。

It means I'm E net switch。And so at L 2， I have an L2 forwarding table。

 and I'm forwarding based on that。So what is this telling us， if you look at this top level， this。

 what's going on here is the packet is crossing from one L2 network to another。It reached the高。

You were done with one L2 network， the router passed it up to L 3。

 and then the routeer passed it down to a different L2 network。This is， you know， inter networking。

 This is literally jumping between 2 L2 networks。This step down here is the packet going across an L2 network。

Car， Let's walk through an example。 I'm happy to come back to this after we've done the example and let me know where things are not clear。

 So let's put this。 start putting this all together。

 Let's say that we have this figure here with this is Soda hall。

 Soda hall whatever reason is gunning She Ethernet。 We have a bunch of host。 I'm using Mac and I。

 that notation just to make it slightly simpler。😊，And we want Ho state to send a packet to Hoby。

They're on the same network。 So what are the steps， Let me do this one， And then this one's actually。

 I think simpler。 And then I'll hand it over to you guys。 What path does a packet take in this case。

 It's directly a to be over the shared ethernet。A just has to put the packet down。

 B has to pick it up。What are the L2 and elderly addresses in this packet。

So think first of the L addresses。 It's going to be the destination is the I P address of B。

 So is the I P address of E。That's always the case， It's the source and destinations。

And the Mac addresses are just going to be their Mac addresses。来。

If you think about the routing decision in this case， it was made by host。

The way it was done was Hosale looked at B's IP P address。

 said my I address and Bs IP address share the same subnet mask。 They have the same prefix。

And hence B is on my network。So， I need to up for。Bs Mac address。And then I got be's Mac address。

 and then I sent a packet out over Ethernet with bes Mac address and my Mac address。要。

In this particular example， this is the shared Ethernet example for Muphy's lecture。

 where this is not switched to Ethernet that we studied earlier。

So it's actually a shared medium link。 Everything that gets put on the link gets goes everywhere。

Any questions here？Okay， so now let's make it a little bit more complicated。

 Let's say Coy Hall has a switched Ethernet network。But it's still L2。

These are now a bunch of ethernet switches as one as2 S3。Its the same notation that Muphy was using。

And S1 is connected to routeer 1。And so because of that。

 we now have the routeto one has yet another Mac address and IP address associated with that interface。

And now we say that Ho A wants to send a packet to host C。ok。So first， what path does the packet say。

 And let's say， you know， we're going to make up a spanning tree。

 Let's say that the part is going from a to r1 to S1， S3 and C。Okay， that's our part。

So now let's talk about how it， what the packets look like at each step。

 Can you think about what the。L2 and L 3 source and destination will look like on a packet when it is arriving at our1。

 So that means along this link。What are this， Let's start with the I addresses。 That's always easier。

 What's the source I P address， You can just say that。Okay， what's the destination IP address？C。

 I P is end to end。 So you need Cs IP P address。 What is the source Mac address for a packet that's here。

诶。And what is the destination Mac address。Oh one， right， exactly。

 because we're getting across one L2 network。And we needed the Mac address of our one。

 How did we get it， We out。How did we get our one's IP P address， THCP。直たつ。At that point， what about。

 based on what address now is our one making its forwarding decision。

 So now think back to the layering we talked about。 So packet came in at our1。

It said this was my Mac address。So I'm going to take off the Internet header。

Pas the IP head up to my gouting layer。Inside this routeer。

 I'm now going to look at I C's IP address。And let's assume that we had statically configured routes at R1。

That said。This subnets prefix code this way and this subnet prefix go up。Okay。

 so those are the IP prefix table that I'm going to look up at our one。

And I'm going to say my next top interface is going out on this interface。For。

I P for the Cs IP P address。Are we good with that？I see some smiles and some noise。

Where can I clarify。嗯。Yes。Yeah， we're getting there。 We're getting there。 right。

 So how did our ones you're arguing about， How did our one get its those I entries in its IP table。

 we static configured them in this case。No， no， no。 So all these switches are just running L 2。

 There's only one routeer。 There's only one I P route in this。

So we had an entry that said C prefix goes out over this interface。

And now what does it do If you go back to walking through the layers。

 It looks at the prefix mask for this interface。And the prefix。Corresponding to IP P address C。

 So you ask yourself the question， is this destination I P within my local network here。

The answer is yes。So how do I， how am I going to reach C。

 I'm going to reach it by ethernet switching by L 2 forwarding。

For which I need to know C's Mac address。For which our one is going to up。For C's Mac dress。

 Once it gets it back， it's going to forward the packet overea it。Okay，So the decision。

 the address that I is making the decision based on is the IP address because it's acting as a routeer。

's connecting to networks。And if you ask what routing entries does our one have。

 I think that was your question here。 It has static routes for the prefixes for solarda halls subnet and Cogi Hall subnet。

And now we're assuming they're statically configured。か喱？

What are the addresses when the packet arrives at S 3。So this is a harder one now。

 What are the IP addresses， What's a source IP。The IP address is always easy。The IP addresses。

 source IP addresses in。Destination I P。C， never changes。 source Mac address。I want。

 I want to be a great destination Mac address。C， perfect good。Okay， great。

 Now let's make this a little bit more complicated。

 So now let's say our one is connected to a campus route or out to。And just for simplicity。

 these are I'm further simplifying my notation here。

And let's auto to assume our is connected to other routeers， but our one isn't。

Continuing a little bit with our configuration， we're going to say， you know。

 what static routes would we add to our one。好子。I don't want to run a gouting protocol just yet。

Someone is put a go at our one。So remember I already had entry to go up to Soda hall at another entry to go down to Kobe Hall。

 You need one more entry at our one。A default route that says any other prefix on the Internet go to out to。

喂。What route would we want it out to。What go through do you want to configure。So run。

 So we would say sos prefix go this way。 Call prefix go that way。 if they aggregate get even better。

You didn't have to。 You could have run a routing protocol between our1 and hour2。

 We could have run a SF。For example。This is， I'm just simplifying it for this example。

So now let's get to the overall picture。 So now let's say Bkeley connects to about to R 3 in AT And T's network。

And maybe also connects to another goer in some different network。

 But let's not worry about that now。 So now Berkeley' is connected to the rest of the Internet。

What does this mean is that Alto and al organic BGP。So now we're back in that end to end world。

And then expand all the way out。 Let's say there was another switched L2 network here that also is connecting to A T T and so on。

Is this picture making sense。嗯。And were out here。 This is another switched L2 network。

And this is actually in practice how networks tend to look。

 You'll have L2 networks kind of on the edge。 And then you'll have the code that is not that much。

 You won't find switched ethernets。 know in the middle of the A T's network。Typically。

 we have Ethernet。 if we think of this as one ethernet network， But otherwise。

 we don't tend to have these large switched ethernet networks in the code。So scenario 4，5， last one。

 And then so I will hand off to you Ho A sends a packet to host D。 Okay。

 let's look at what are the L2 and L3 addresses in the packet when it arrives at all 2。

So I'm going to simplify IP addresses you have is the source De is the destination。

That is always the case。 What about the Mac addresses。What's the sourcemic address。No。

A1 C and destination。Out to it， exactly。 So we're treating this like its own Ethernet network。

So it's kind of like a redundant。Highly sancrified path school and Internet network just going between across that link。

嗯。What about the。Addresses when the packet arrives at S 6。Again。

 I'm going to tell you the source and I destination I stay the same。 What about the Mac addresses。So。

 we're now here。What's the source my address。有。All 20 B， great and destination。Yeah， perfect。

 Any questions on this yeah。You could certainly have multiple routes within like multiple gateways here。

 you mean。Over here。You could。 This gets back to the question of， you know， that in that case。

 this would not be your L2 network。 It would be an I P network。 And you could be running something。

Like OSPF or something within this here。对。对。对。Yeah， so think about it this way。

 You always have L2 connectivity between any two nodes。 because when you put a packet out。

 there's always an ethernet header and an I P header。 So even if I put a packet here。

 look at a packet over here。 it has an ethernet header， and it has an I P header。So the question is。

 really， are you forwarding at L 2 or are you forwarding at L 3。Okay。

 I think that's maybe when I take this switch over here， it's only forwarding based on L2。

 It never looks at an I address。 because I， if I look at these routers。

 they are always looking at E I address。And then they are also putting the ethernet source and destination map。

The L 2 forwarding is trivial in this case， but it exists。Your ethernet header is there on the water。

And that is exactly what confuses people。So that is the rules about when you're forwarding at L2 versus L3。

はい。You always， in ato， you always look at L3 and you always pick your L2 addresses as well。So Ge。

 the question is， when you only look at L2， and it's one of these switches。In your Ldo network。

Does that make sense？Sa that。有。Right， so you could have done。

 That was the question on the routers and how did how。

 how do routers discover their neighbors IP address and Mac address。

 We said we're going assume they're configured。But you could be doing help。

If I sent an out message over here saying， what's the Mac address for the IP address on the other end。

That interface should send me back a response saying this is my Mac address。Any other。Qu。



![](img/4fccff6e5797a36b1eecea2c4e2030f2_1.png)

Yeah， so I'll go through a couple demos。 I'm actually going skip over Sylvia's next part of the lecture so that you guys can see both。

 So first we'll talk about these bootstrapping things that we were just discussing。

 I do want to note that what I'm going to show you is a lot uglier than the pictures that we look at。

 but this is hopefully to allow you to relate what you can actually see on your own computer to the prettier pictures of things that we've looked at in class。

😊，So we're going to see what DHCP and A look like on my own computer when I'm connecting to my Wifi at home。



![](img/4fccff6e5797a36b1eecea2c4e2030f2_3.png)

They're going to let me click。There we go Yeah， so this is wirere shark。

 a common tool used for networking things if you haven't used it before。

 hopefully this is large enough that you can read it。😊。

But the exact details don't really matter here it's just that this is the like homepage of it。

 you have a bunch of interfaces， you can select them to look at all the packets on that interface and we'll be doing that in a second in particular。

 what we're going to look at is the Wifi interface and zero。

So first let's look at what our Wi-fi interface is actually doing so I'm going to use IF config in the terminal。

 so this will give me a bunch of information about that interface。

 a lot of it is not important here again， things are dirtier in the real life but what's important here is that it's both inactive and we can see it's ethernet address because regardless of whether it's up or not you will always know your Mac address since it's burned into the interface。

So I can also look at。The routing table for my computer， I will note that right now。

 because this Wifi interface is inactive。 I turned off my Wifi。

 like the way you do in the dropdown menu。 So when I show my routing table。

 it's gonna have a lot going on here。 That's all IPV6 stuff。 Let's ignore it。

 I have the IPV 4 highlighted here。 Let's only， let's pretend that's the only thing here。😊。

And you'll see that all the routes go out on this loop back interface， L00。

 This is a purely logical interface。 It's not yeah。

 it's not actually a physical thing on my computer。 That's why it's still here。

 It's used a lot for like web development。 So you can host something locally at like 127 do do0 do0。

 but that's all that really matters here。Okay， so next we can look at my arc table as well。

And what that will look like is nothing for out。 I'm not connected to the internet。

 so there's nothing in my art table or not connected to anything。系啊。

So now let's go back to wirere shark and start collecting packets on my Wi-fi interface before I start turning it back on。

 So what will happen is I'll see every single packet that touches this interface going in and out。

So if I drop down and turn on my wfi， then。We're going to see all of this。

 This is a lot of information。 We're only going to look at a few select packets here。 Again。

 I just show this to show you that there are other things going on。 but yeah。

 we'll show how to filter this later。 But right now I want you to kind of see that there will be outputs like this。

嗯。So first we can look at this our request and is's asking for who has this 192 address and if we go back。

To the interface config for my Wi Fi interface， we can see the ethernet address。

 It ends in this 7 E 19。And if we go back to this R request。

 we can see that's where it's coming from。 Wireshark is resolving sort of the beginning part of that to make it more human readable。

 So it has Apple 3 C and then the last four digits there。

 but yeah so it just resolves it to make it more human readable。 That is my Mac address。Okay。

 so then in this bottom pane of wire shark， we can look at specific fields in the headers of the packets that we're looking at。

 And so here in this art request， we can actually look into the art fields and see what's going on there。

 So unsurprising things are that the S Mac address is that Mac address that I just talked about。

 and the target one is unknown。 So we just fill it with a bunch of zeros。

 but there are two things shown on this screen right now in the bottom pane that are not quite what we would expect。

 Does anyone know what they are。😊，Okay， I'll give you one for one。

 if you look at the ethernet header right above this a header that I have highlighted。

 there is a destination address。 This surprised me too。

 I think this goes into limitations of my Wi-fi knowledge。

 I think because I have connected to this w-fi before and have gone through like the authentication process。

 It does know the Mac address of my router。 Another surprising thing is in the art header。

 Any guesses。😊，Okay， I have a sender I address， but I have not done any DHCP yet again。

 this is my home Wi-fi。 I connect to it a lot。 so I already had a lease for this IP address。

 even though I wasn't connected right before we started this。 we'll see in a moment that there is。

 in fact DHCP。 I make sure I'm still allowed to have this IP address。

 but for right now assume I have it。Okay， so now if we move on。

That was just to look through all of that。Oh yeah。 so now we can look at the D， I should go back。

We can look at the DHCP request and so since my computer already had a lease for this。

Asks for that specific I address that it already had。

 We can look at the like specific internals of this request。 A lot of it is not that interesting。

 there's just a lot of information。 but the more we scroll down， like we can see my Mac address。

 We can see the I that I'm requesting。 We can also see see that I'm requesting a lease time of 90 days。

 we will learn that I will not get that。唉。Okay， so then next in the list of packets that we're going to look at that are interesting is our response。

 So my router replied and said I have this IP address。 So that's all set up now。 I know that mapping。

And we can also look at the DHCP response again， lots of fields。

 but we can scroll down and see that I did in fact get the IP address that I wanted。

 I only got a lease of eight hours and the domain it also gave me my DNS server so that's critical information for the future because if you look down a little bit。

 I do then send some DNS request， this is just some stuff that my computer was doing for whatever reason it's not caused by any request I started。

 but we can also look inside the DNS request as well as the response。Okay。

 so now let's go back to terminal and look at what changed。 So if I look at my interface， or sorry。

 we already looked at my interface。 If we look at my art table， now there's a bunch of entries。

 in particular， there are other Mac addresses on my subnet。That is my home。

And then we can also check the route table again again we're going to get a lot of IPC IPV6 output。

 let's ignore that。 let's go back up to IPV4。 The table has gotten bigger。

 you'll notice a lot of the outgoing interfaces are now my Wifi interface。

 The most important thing here is that first route I have a default route through my router as my gateway and it goes out on my Wi-fi interface。



![](img/4fccff6e5797a36b1eecea2c4e2030f2_5.png)

Okay， any questions on any of this？第。So you can， I think if you go into your network settings。

 you can specify a particular DNS server， I think that would be a rather special case thing in general。

 DHCP tells you where to go for DNS resolvers。嗯。Why was there in our request？Yeah。

 I think this is another artifact of the fact that I have connected to this network several times。

 So as we saw， I knew both what I expected my I address to be and what I expected the gateway I to be。

 And so I think it was resolving that I。 But yeah， again。

 this is just showing that if you ches this out in your own home network。

 You're going to see things that don't quite match like our perfect view of starting from zero state。

 as there is some preexist same state， especially in like your home PC。

I don't know if I'll make a blanket statement， but it seems like in like Mac implementations。

 they try to keep their consistent IP if they can。

![](img/4fccff6e5797a36b1eecea2c4e2030f2_7.png)

Okay， cool， then I will move on to the second demo。Just so that we can make sure we get it in。



![](img/4fccff6e5797a36b1eecea2c4e2030f2_9.png)

So a little bit of a topic change。 where now we're going to get into web things。 again。

 I want to show how to make this look real。 So first I'm going to take a look at this just through the lens of HTTP。

 we're going to ignore packet level things for right now。



![](img/4fccff6e5797a36b1eecea2c4e2030f2_11.png)

So I have this example website that I made。 it is just a very small HTML file with an image in it。

 that is all that's going on。So I'll begin by opening the inspector tab on Chrome if you're not familiar with this。

 it's really useful again for web development， so for example。

 I can look at the HTML and as I hover over it it will show me what that actually looks like in the web page。

😊。

![](img/4fccff6e5797a36b1eecea2c4e2030f2_13.png)

But what we care about is the network tab so I'll go over there and we can see what the browser is using the network to do with this at first it's empty because it doesn't record unless it has to and this will give us a lens into how the page is loaded at the HTPP level keep in mind these are not packet。

So I'll reload the page。And so you can see that we sent two requests， one for the website overall。

 and then one for the image resource within it。So then we can look specifically at what's going on within these requests。

 So you can see the the headers in particular， we can see that this was a get request that we got a status 304。

 So what does this mean Does anyone want to know。Yes。Right。

 so I have obviously loaded this page before， so it hasn't changed since I got it。 So I got a 304。

And then there's a whole long list of HTDP information that you can look through if you care about。

 but it's all there。And then we can look at the preview。

 it's the HTML file without the image inside it。And then the last interesting tab that we'll look at here is the timing tab。

 where you can see how long it took for different phases of the request。

 So here the content download dominated in all the different ways you could spend time。Okay。

 so now we can look at the image request， same thing。 If we look at this headers tab。

 we can see that we got a 200 response。 and actually it was from the memory cache。

 So since I had loaded this page before， Chrome cache the image for me so that when I reloaded it。

 it just loaded it locally。Again， we can look at all the headers。

 the only notable thing here is that when we get to the bottom we'll see the request headers are provisional。

 this is essentially just pretending what it would have been if we actually had sent a requests。

 but because it was stored locally， we didn't。And then again。

 we can see a preview of the file and if we go to the timing tab。

 we can see that we spent essentially no time downloading the content since it was stored locally。

So we can disable the cache at the top of this inspect tab。

 and then we can reload the page and see what happens。 So now we have 200s for both requests。

 We're only going to look at the image one， but now you can see it wasn't allowed to use the locally cached version。

 So it no longer says it came from the memory cache， and it actually grabbed it from the server。

 which yeah。So now let's see what happens if we load a much more complex website， so Google do com。



![](img/4fccff6e5797a36b1eecea2c4e2030f2_15.png)

There's all these assets， a bunch of HTTP requests， all doing a bunch of different things。

 so you can play around with this on your own time on any website there is。

 but yeah our initial one was just for cleanliness。Okay。

 so now let's take a look at the exact same thing。 but at the packet。So again。

 I'm going to bring up wire shark。 I want to note I'm no longer on my home Wifi here。

 I'm now in Soda Hall， so I have two active interfaces。

 I have my Wifi interface and a wired ethernet interface。 So that's E N 0。

 and then this Tunderbolt E N 6。So let's first see what's going on on my Wi-fi interface and the answer is a lot。

 you'll see those black TCP ones， those are retransmits。

 so this just demonstrates to you that this happens a lot。 You're going to see a bunch of protocols。

 there are also color coded so quick is a protocol we haven't actually talked about but it's built on UDP There's a lot of TCP going on。

And yeah， I could scroll like this forever。 But the point being that this is pretty hard to read。

 So we're going to do some filtering to make this easier to look at so that if I load this page on the right。

 I can actually find what's happening。So we can close that out and then we'll look at the inspection In tab on the right。

 and we'll get some information that we can filter on in order to not be overwhelmed。In particular。

 this remote address in the top， as well as the port will be good things for us to filter on。

 we can only grab packets with those fields。And so wirere shark lets you set up filters。

 We don't have to get into the exact semantics or syntax of it。 but I'll just insert this。

This filter so that we get everything on TCP port 443 and at this IP address。

So now if I listen on my Wi-fi interface again and I reload the page。There's nothing， any ideas why。

Good guess。 But no I actually still had the caching turned off。So the reason is a little bit tricky。

 I knew when I created this filter that filtering on an IP address was probably a bad idea because I'm using Gitthub hosting。

 I don't know how they do it。 They can move it around servers arbitrarily。

 So if we look at the IP address of the new request， it actually slightly changed the IP address。

So now I'm just going to edit the filter to that slight change。

 And now we can see everything that's within。Those requests。So taking a closer look。

 we can again see all the packet header information in the bottom pane， there's a lot going on here。

 but you can drop down based on which protocol it is。And in particular。

 there's all this TCP information inside of it。And in particular。

 we can see if we look at the top that the connection does in fact start with a S synynak act。

 as we've always talked about。 and yeah， so that's one of the clean parts that actually did't make it through here。

And then we can look at what goes on after that， we get some application data。

 there's also some additional connection set up at the TLS level。

 so like the two ends decide on a cipher。We don't have to care about that too much in this class。

 but just to help you understand what's going on。And then we can also look at the application data。

 but since we are using TLS， it's not very exciting， it looks like nonsense。

 I can open the TLS part of the packet and there's just nothing to look at in wirehar。

 it's not going to be readable in any way。So I can close this。Out。

And then we can try to do this on a website with no TLS。

So we will hop over to Sylvia's very old website to her credit。

 she didn't even know the department was still hosting this。😊。

If I then filter on the I and from the In tab for this website and then open up my Wi-fi interface and load the page。

I呃。Again， get no traffic。Any ideas on why this is， This is a bit tricky。呀。44，3 is for HTTPS。

So it's port 80 for HTTP。Okay， so this is a bit nuanced。

 but if I close the session out and I try it on my wired ethernet， it will if we retry。



![](img/4fccff6e5797a36b1eecea2c4e2030f2_17.png)

It'll work。So I gave you what fixed it。 Do you guys know why。呀。Exactly， yeah。Oh。

 so all of this is recorded， but。Yeah because the wi-fi in here is flaky and if I wasn't going to trust it So yes。

 this is exactly。 I mentioned at the beginning very briefly that my wired connection is in Soda it makes sense that this website at e。

berkeley。edduu is also hosted probably in the same building definitely in the same subnet and so when the packets with a destination IP for this IP showed up on the interface。

 the route that was chosen longest prefix match was on the interface that's also on that same subnet。

So yeah， now we can look at application data， looking more specifically at this， you can see。

 for instance， there's that get and we can actually look inside it as well since there's no TLS。😊。

And yeah， you can see all the HTP information we saw in Chrome originally。

So one thing I do want to note before we move on， there's no Sac handshake at the top。

 Any guesses for why。呀。Yeah， so browsers typically will keep your。

Your TCP connection going for like 60 ish seconds。 And so when I loaded the page the first time and it didn't work。

 that initiated a connection， there was probably a handshake then， but then when I reloaded it。

 it was in a short enough amount of time that Chrome just used the connection it had to the server。

Okay， so now we can look into all the application data we want to， you can see the response header。

 look inside of that， most of it is pretty human readable。

 it gets pretty ugly when it's at the level， but it's all there。

And then I also want to note that just in these boring TCP packets with just some random application data in them。

 you can see a bunch of interesting information like the advertised window size。

 what the sequence and act numbers are， wirere Shark also gives it in relative form so that you can reason about it a bit more easily。

And then we also can see things like we get a separate request for the actual image。

 as follows as what we talked about at the HTTP level。

And we can scroll all the way down through all these packets to see some fin packets。

And the eventual termination of all the connections that were a part of these HTTP requests。Okay。

 any questions？Yeah， so you can Google Wire Shark， download it， play with this yourself。

 see what does and does not match your understanding of things。

I gave Sylvia a very small amount of time。嗯。嗯，对。我一个。



![](img/4fccff6e5797a36b1eecea2c4e2030f2_19.png)