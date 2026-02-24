# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P12：-11- IP Forwarding (Rob Shakir - Google).2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

そ都。돈 내 말 and大。Okay， and what time does it finish？12 think well be。I've been through a few times。

 I was saying Alex。have we this flash， you should go。She's heard。Was listening。Make my play。很し。

So back。I'm sure when a short comess， he'll have meetings。Always like yeah。But if I produce。

She looks it really well。The方。The way to argue with a show is just to let him talk。see。

 he disagrees with it。You just to sit back and then eventually comes around to it and you tune back in。

You don' really do now。Good stuff to do。Good morning everyone， we're going to get started。

So it's a pleasure and an honor to introduce today's guest speaker。 We have Robb Sha here with us。

 and we really couldn't have found someone。😊，More perfect to lecture on this topic。

 So Rob is one of the key technical leads at Google's global networking team。

 This is the team that runs the entire wide area backbone network that Google operates。

 but he's also responsible for with other folks in doing the technical evaluation of router equipment and deciding what Google runs in that wide area network backbone。

 He's also one of the lead authors on openconfig， which is pretty much becoming the de facto standard for how you can figure and manage routers in the network and also sorry it's a long achievements one of the main authors on segment routing。

 which is probably the cutting edge in routing protocols that's for the IETF standard。

 which is I think at this point of standard right。So without any further delay。

 thanks Rob for being here and welcome。 Thank you very much。 I think it's funny。

 I really wish that at some point I'd done a computer science course and been taught about routes at all。

 but I'm going to talk about something that I've been working on for about 20 years， which is。😊。

large number to think about and just kind of share。

 I think some of the background and some of the information about things that I've spent a lot of my life thinking about。

 but you other people might not know about or think that it's just a box in the corner of their apartment that deals with their broadband。

So'll start out。 And I think you've seen this picture before。 What's the purpose of an I router。

 an I router is there to be able to take a packet， figure out where it should go and router along the right link。

 So， you know， in this case， a packet comes in with the specific destination address。

 It's got a specific link it needs to go down。 And so we're going to talk about how does it actually do that。

 What's the。You know， look at what the what what a router does and talk a bit about， oh。

 and I'm just going to disclaim this。 I say router and British。In America， they say router。

 I'm not going to try and say that that's something that cuts grooves in wood in the UK。

 So stick to the one that moves packets。 So it's things that perform IP before look ups against the destination I of a packet well remember or talking about that they were in routing protocols。

 which is how they learn about routes that are going to be tell where things are where to root towards and roots I also say root not route again。

 British disclaimer routes are sets of destination IP addresses。

 So today we're going to talk about what is a router。

 And to start with going to take a little bit of a step back。

 this the things when we start talking about router can often be quite dry and not really know how it fits into the real world。

 So these are a couple of photos I've taken or maybe I took the one on the left and not the one on the right。

 sorry and we'll talk about a little bit about what makes up the Internet。

 The Internet is really just a bunch of networks connected together and what's connecting those networks together is routers。

 when we deploy those routers， we put them into some facility。



![](img/e98db17db9b24c6be7d77eb28bed8684_1.png)

Like these ones， know they're buildings that are specialized to have the power。

 the cooling and everything that we need to be able to put routers in there and interconnect with each other so when Google interconnects with Comcast or Google internects with Horizon。

 that's in a building like this most likely and these buildings you know if you go into them。

 it's just racks flooraws and floors of air conditioning racks that contain these routers that what we actually use to build the internet to kind of connect things together。

And so here's a couple of photos these are relatively historical photos because these are the ones that I can share they're from a network that I worked on a few years ago。

 and this is what a router looks like know and we'll come back and talk through what a router is and we'll come back to one of these photos and have a look and say。

 okay， how does that map and what is a router really Well it's just a computer that is really specialized for forwarding packets？

And there's many different sizes of that router。 You know， these are two different ones。

 You can see that one's got horizontal slots。 The other ones got vertical slots。

 There's various reasons that they look a bit different。 But really at the end of the day。

 that's what a router is。 It's just something， just a computer that we've designed to be really specialized to forward packets。

And they come in different sizes。 So you you've got everything from the small blue thing here might be a home router that's got w-fi and it's got the small number of ports might have things that are one rack unit tall that's unit that we use to measure things inside a cabinet is a rack unit a couple of inches and you'll see here that this one is one rack unit we might call that pizza box because it looks like a pizza box and then the larger case on the right hand side of this slide is something larger that has more line cards and the dimensions that we have in terms of these routers we kind of measure the physical size We also think about well how many ports does it have the pole point of this thing is to forward packets and interconnect then it really needs to have how many ports how many times can I interconnect with other systems。

And then the bandwidth， the bandwidth is how much， how much capacity does this have。

 this router have to actually forward packets。 And obviously， that's a really key thing。

 as we're looking at a certain data volume， we need to know how much data can we put through a specific router。



![](img/e98db17db9b24c6be7d77eb28bed8684_3.png)

And so if we think about the definitions， how we kind of talk about routers。

 we talked about them in these different dimensions。

 so we have a the number of external ports that's there。

 there might be internal ports and things that are used to connect bits of the routes together but we don't think about those really think about the ports on the outside and sometimes in the industry they'll be called revenue ports because the vendors that you buy them from what they're the ports they can actually sell。

 they can actually charge you for。Then each port has some form of speed has a speed of that port。

 We often to refer that to that as the line rate。 So sometimes ports run at different speeds。

 You know， you could have a port that was 10 gigab that was also able to run at 40 gigab or it's able to run at 10 gig。

 But when we're talking about the capacity of a router。 then we think about what the line rate。

 what's the maximum rate of that port。 and then there's the capacity of the router。

 So the capacity of the router is just the number of ports times by the speed of those ports。

 So if we think about this kind of small little router here that you might have at home。

 maybe it's got a couple of different types of ports。

 it has400 ports that gives you400 of connectivity there。

 and then you might have one1 gig port So that gives you a gigab of capacity there。

 So the overall capacity is this 400 plus a gig。 So it's a 1。

4 gig a second router probably can't actually do that because of how it's forwarding。

 but that would be the capacity of it。

![](img/e98db17db9b24c6be7d77eb28bed8684_5.png)

We think about what we actually deploy in in a network like Google's today。This is an8 slot system。

 It has8 line cards。 We'll come on to what a line card actually is。 Each one of those has 36 ports。

 So and the number of ports here is 288。 We have 36 times 8 ports。

 Each one of those ports can run at 400 gigab per second。

 So the rootr capacity we have today is those 288 ports times 400 gig。 which about 115。

2ter per second。Which is a lot more than your home router。

These numbers continue to get kind of interestingly bigger。 and why do they get bigger？ Well。

 you know， in this same size of physical deployment。We don't increase the number of ports。

 That's kind of limited by the amount of space we have on the front of the slot。 You know。

 there's only so much physical space。 And if we have to plug an optical module into it。

 there's only that much space for those ports。 So it stays at 36 ports。 We still have the 8 lahouse。

 we can make the shafty any bigger or smaller， but we can then put different lahouse。

 different modules into it to rather than run it 400 gig per port。 We can run 800 gig per port。

 And that gives us a doubling of the capacity 288 times。

800 gig now looking at about 230ter per second through this router。



![](img/e98db17db9b24c6be7d77eb28bed8684_7.png)

These numbers change over time。 So from this is a view that we put together a few years ago in Google which is now sufficiently old。

 I can share it。 But if you see here， can we started out with these systems on the left hand side of the slide。

 the juniper system there。 It's 1。6，1。7ters per second。 You know， then we got bigger routes。

 So the one along， it was physically larger， It had more line cards， which means I more ports。

 which then increased the capacity。Same again we increase the number of ports and the capacity goes up。

 But you'll see here that really at some point， we run out space。 A rack is about 7 or8 feet tall。

 depending on what exact size you have。 And that's about the amount of physical space you get to put things in There's then a physical size of optics。

 So that's how many ports you can get on each line card。

 But there's also some constraints around how much power can put the rack。

 of these systems will be pulling 50 kiloW of power。

 So there's a significant power draw all that power going in a heat。 So you have to it。

 So a lot of the physical constraints we have about how route what the maximum capacity is going to be is really around how much can we fit into that rack。

 And you'll see here that the numbers go up but things't necessarily get bigger between the Cisco device than S 9000 and aristo 7500 the thing got smaller but the capacity went up And that's a result when we increase the speed of the ports。

 So there we went from。1 gigabit based system to 100 gigabit based system。

 and as we go to 400 gigabit systems and 800 gigabit systems as we kind of talked through on the previous slide。

 that's when we the capacity of the router continues to increase over time。



![](img/e98db17db9b24c6be7d77eb28bed8684_9.png)

Okay， so that's kind of like the photos of what routes kind of look like。

 So let's talk about what actually is inside a router。 So once we kind of peeled the metal skin off。

 what would we find and we'll use this conceptual picture and we'll iterate on it a little bit to talk through what it does。

 So we have some chassis。 That's the overall unit of router。

 It's the thing that collects all theline cards together we would talk about a chassis having a capacity because the chassis is the overall router。

That Chassis has two different types of cards within it， has a controller card。

And then it has line cards。 Control the cards are where the control processor。

 It's usually a X 86 processor probably running Linux that that run that sits in that that device and its job is to。

Exchange routes with things to do those controlled management plane software jobs and program the line cards。

The line cards themselves the things that are dedicated to forwarding so you've got the ports。

 the input and output ports on that line card input and output ports it's the same set of ports port is bidirectional and the same port be the input and output can be port can be different ports on the same line card it can be different on different line cards the line card itself might have its own control plane processor its own CPU and that will be there to do anything that's local to the line card maybe it's managing whether links are up or down or responding to any kind of local protocols that are running there and then there's some way that we know once a packets come in。

 we can interconnect to another line card I'm of drawn as a mesh here。

Where every port can talk to every other port。 and then on the other side。

 we have more than one line card in the system in some systems or in the smaller ones。

 maybe they just have one。 and then we have the output line card。

 which is doing the processing of packets before they're rooted out out into the rest of the network。

And when we talk about routes， we kind of really talk about them in terms of planes。

 like that's the sets of functionality that the router implements。

 and so the first one of those is the data plane， the real one that we care about right these are computers that we want to forward packets quickly。

So really we care about how is it forwarding packets and that's made up of mainly the line cards there's between one in 20 line cards in a system。

 usually that's constrained by how big we can build the fabric。

 the thing that interconnects the line cards and the physical size at some point is too difficult there's not enough space in that rack to fit more line cards in and that helps you choose the capacity of router you can choose how many line cards the router might have on a line card itself。

 you'll have some specialized hardware to forward packets。

 that's something that's designed really to do the packet forwarding will go into a lot more detail about that and then something rather than having this full me of wires between every port we want to have the line card is a removable unit so we want to have something on the chip on the line card that thing that we can remove then packages packets to be able to be transmitted to other line cards and that thing that interconnects all the line cards we call the fabric of the router。

Here we've got a fabric， there might be multiple fabric cards in a router that help that interconnection。

 achieve the right bandwidth help us have the right reliability。

 but then the forwarding chips and the fabric chips make up the data plane of the router the thing that really does the me and edgege of the job and forwards forwards packing we then have the control plane the control plane I think talked about a bit in terms of it gives you the way that you talk to other routes。

 the thing that runs the control the control protocols。

 the roing protocols to be able to talk to other routers and figure out what routes to have so it might be running BGP or an IGP like OSPF or IIS and then exchanges those routes。

 it figures out what we need what the routes we want to use are and then responsible for disseminating those routes down to the line cards so the line cards themselves don't really know anything about how to figure out what routes to take what they know is how to forward packets along those routes but the control plane is what figures out what routes we should forward down and。



![](img/e98db17db9b24c6be7d77eb28bed8684_11.png)

That's really pushing the forwarding tables down to the line cards。

 so its job is to go and take that external interaction with other systems and then program the line cards to make sure they're forwarding in the right direction。

Alex。Between1 and 20 so it depends on the kind of size of the system here so you have know the control plane is also responsible for making sure those line cars are consistently programmed because we want to make sure that they've got the right routes。

 everyone on the Shassis kind of understands the same view of the chassis。



![](img/e98db17db9b24c6be7d77eb28bed8684_13.png)

Then something that doesn't get mentioned very often when we're talking about routeuters。

 but as Sylvia mentioned， I spent a lot of my wealth about the last six or seven years thinking about a lot is how we manage theis the router。

 So we put the rid in we said okay it's got some control plane protocols。

 But who does it speak to And then when we've got it running。

 then how do we know what it's doing is it dropping packet。 doesn't need to be repair。

 So those whole sets of consideration。 So it's something that we would callcapsulated by the management plane functionality of the device。

 and the management plane is of has two arms。 One is that configuration It's external systems or humans interacting with the device and telling it。

 okay if you need an I address on this link， it's going to be this。

 you should speak to this BGP you should run an OSPF on this port。

 those kind of configuration operations are part of the management plane。

And the other side is monitoring or sometimes we call it telemetry and that's where the router is telling us things about what it's doing。

 how many packets is it forwarding， is this BGP neighbor up or down does this line card have a fault this is really critical for actually running the network because when we put this thing out in the ground and it's forwarding some packets we kind of need to know that it's doing the right thing so that if it isn't we can repair the network otherwise you have outages。



![](img/e98db17db9b24c6be7d77eb28bed8684_15.png)

So let's have a look at one of those pictures that I kind of put up earlier。

And this is this is a real router a few years old。 Now it's Cisco 7606。

 06 means there's six slots in it。 two of those are control plane processor。

 of them four of them line cards。 So you can see here the white ones with ports on them。

 These aren all fully populated。 But you can see those are the line cards。

 That's where we the input and output port。 got these two gray cards at the bottom。

 you can don' have very many ports on them。 They have a few they've things like a slot for putting compact flashcard in for storage。

 Those the controller cards that we talked about。 And then a bunch of other ancillary things that go into the shaft。

 which actually don't really like on the left hand side of here。

 you've got a fan tray this hardware produces a lot of heat。

 And so you want something that's removing it on the back of it's a couple of power supplies。

 But that's what a router looks like。 And if you we can it's a computer thats。

Specialized for forwarding。 But we said， there's actually like line cards might have their own CPU。

 The control plane talks to the line cards。 So actually， it's really like a set of computers。

 They are all in this common metal tin that's used coordinating with each other to forward packets。

 And so they're a little bit more complicated than some of our pictures kind of show。

 But this this is the how it might look in a real network。😊。

So at least's just recap those definitions that we went through， so we've got the control plane。

 it runs roing protocols， allows the route to understand where to route packets。

 is figuring out what should the route to be doing in terms of forwarding。

've got the management plane that's interacting with systems or humans to configure and monitor the device。

 increasingly the systems these days， although historically these things were configured by humans typing at them。

And then the data plane， which actually forwards packets and you cant need all of these things to run a router in a real network if you can't manage it if you don't know what it's doing。

 then you don't know whether it's doing the right thing so thats you can't configure it to tell it what to do not a good thing if's not there any of the control plane then it doesn't know where to route packets And if it doesn't have the data plane that does not actually forwarding packet so not that useful。



![](img/e98db17db9b24c6be7d77eb28bed8684_17.png)

So let's think a bit about specifically in the data plane。 so specifically forwarding packets。

 what's important and what types of different packets do we have。Now。

 and this is kind of the thing you would expect every router to do。

 it's the key thing you've got packets for users the packets that were actually forwarding。

 And so they will come in on an input line card。 We'll have some looker mechanics that say take that packet and route it according to some installed route and then。

Forward it across the forwarding chips， the fabrics， out to whatever other the output port。

 use these are the standards or packets that are being forwarded by the device。

Also have control plane packets。 So if you can imagine we're talking BGP to some of the device。

 then there's some packets that are coming in and they are to do with that BGP session。

 So there are actually packets that we need to pay attention to。

 And so in that scenario the packet comes in and it's not something that we should forward out。

 It's actually to us。 So we then will send that packet from the line card up to the control plane。

 the control plane then deals with that and handles that in terms of being a packet that we should listen to and takes whatever action based on that。

And then there's a set of packets that are not really expected。

 So we have packets whereby it comes in and there's things like the IP TTL has expired。

 and we need to do something to them， but we don't know necessarily or we need to respond to them in some way。

 So we need to be able to tell the control plane Hey you need to do something with this packet。

 We got those punt packets So it's packets that we take we receive it a line card we say oh we don't know what to do with this or you need to do something with it and we pun it up to the control plane to deal with it。



![](img/e98db17db9b24c6be7d77eb28bed8684_19.png)

So let's think about like why this architecture， you know， clearly and we would have。

Weve invented something very complex here and so we asking ourselves like why did we do that If we think about the smallest ethernet packet we can have so the smallest packet we're going to link is about 64 bys Currently we're looking at 400 gigs per second which means we've got about 781 million packets per second per direction and we've got 36 ports on the line card so we're now going into 56 billion packets the second that we would need to look at per line card。

In the practice， they're a little bit lower because not every packet is that small。

 but that's a lot of packets。 So a lot of things that we need to do。

 And it's not really achievable in a general purpose CPU。 In general purpose CPU， can probably do。

Millions of packages per second。 but we really think about this as the slow path。

 So you know only when we have to do we rely on that。And otherwise。

 we want this forwarding hardware because we need to be able to scale to that number。

 to be able to meet that bandwidth requirement， to meet that kind of number of lookup operations。

 And so that's the fast path we would think about。 and there's also another set of design constraints。

 these things can be lower power， they can be lower cost overall the order of cost of a device like this the ones that is in the millions of dollars So we really do care about the cost if the things going to be iss going to be more costly。

 it's much more expensive for us to build capacity。

 We can't scale to you don't pay any more for your broad bill as you use more traffic。

 And so you want to be able to make sure that you can manage the cost of these things And actually we really expect there's a cost efficiency year on year for the devices。



![](img/e98db17db9b24c6be7d77eb28bed8684_21.png)

So I'll pause here， any questions that you'd like to ask。

 please we can dig into them now and then we'll kind of dive and a look at some of the forwarding in more detail。



![](img/e98db17db9b24c6be7d77eb28bed8684_23.png)

Great。😊，Oakcle。Oh you're too shy， see。So let's think about when we're thinking about the user traffic。

 so we're thinking about forwarding these packets。Well。

 we need to think about what the input line card does。 You know。

 that's the first place that this packet is going to be received。

 And we kind of will step through a few things。First up。

 we also have to receive that packet from another system。

It comes in and it's either an electrical or an optical systems signal。

 depending on whether it came in on a copper wire or on a fiber optic。

 we have to do some decoding of the packet because it's been put into a certain format to be put on the wire。

do some functions around the IP header。 So you have to think about things like decreasing the TTL or checking the checks on maybe options or fragmentation。

 Then we have to do the lookup， like figure out where this packet should go。

And the real key thing about this lookup is speed。 we talked about that packet rate。

 even if we increase that packet size away from the minimum to something that would be more typical for an average packet size。

 we still have very long to actually go and do that lookup。

' we've got packets arriving at a very quick rate。 and we need to run quickly for each port know in the order of gigahertz per second to be able to even spend one cycle per packet on that。

But we need to do multiple operations。 You know， we just said there's a bunch of things that we have to do with the packet in terms of look up and check the IP header and those kind of things。

So we have to think about how we're gonna scale this thing。 So this speed is a real key thing。 Now。

 if we look at solutions for that。 Well， we could parallelize， right， we could say， okay。

 rather than have one chip， go and do every packet。 Why don' we have just lots of chips。

 But then we start running into lots of power requirements We need a more physical space on on the board。

 It produces more heat。 And so that's why we've ended out with specialized forwarding chips。

 Those specialized forwarding chips are essentially。

Processses that are designed to be really efficient in dealing with packet forwarding。

And what they what they do is they compromise a bit on the flexibility of what they can do。

 You can't run a general purpose program on these chips。

 You can only run things that are kind of within the constraints of packet forwarding。

 and we have some programability in some chips， and some we have none。

 but they have that really limited feature set。And then we say， well。

 if there's anything we can't do in that limited feature set that we have。

 well that's what the control plane general purpose processor is for。 So we then say。

 well that's why we want things like the punt traffic flow because we want to say。

 well we couldn't implement this in the specialized forwarding hardware that we have。

 but that's okay because it's not every packet and so we rather we'll ask the control plane processor to go and do it。

 and that might be a distributed thing there's a processor on the line card that can help us。

 but it's actually outside of the key the forwarding hardware。

So we think about that packet coming in， we kind of divide it down a little bit into how the layers are dealt with So layer one。

 you know the electrical or the optical signal here。

 we have some form of physical chip a p or a physical logical block at least that it's going to deal with decoding that signal from whatever it was on the wire in terms of physical signal into a stream of bits。

Then have something that's doing the handling at the link layer。 So the layer too。

 where we're dealing with， there was an ethernet frame that came in。

 and we need to check the validity of that。 Do any ethernet operations that we need。

 And these things are implemented in hardware。 They're fairly standard。

 They're fairly constrained in terms of the things that they need to be。

 So we can implement these in hardware。 It can do these a fast rate。

We then sort of skip over the forwarding because we'll spend a bunch more time there。

 then we have the fabric incate， you know well have a chip on the line card。

 this job it is is to transmit packets to other line cards。And again。

 this tends to be a dedicated chip， tends to be a different chip than the forwarding chip because it does slightly different things。

 it doesn't have complex roing decisions to make， it only has to figure out what other line cards make to send to。

 but it does things like split packets up so that they can be fairly sent across a lot of different physical traces。

 physical wires that are on the PCB in the chassis so once we've done with the forwarding。

 we know where that packet should go then we'll use this fabric chip to be able to interconnect to other line cards within the system。

So then forwarding。The thing that we really care about。

 the thing that the router is really there to do tends to be broken up into a few different stages The first of those is a parer we look up。

 we get a packet in， the packet needs to be red and needs to be divided down into the constituent past is it IPV4 is it IPB6 is there other headers around that we'll talk about just IPV4 and IP6 but there's other encapsulations that we look at other ways that the packet can be formed No so we want to break it down into the parts that we need to look at。

Then have here's exactly what know the block that does the actual look at。

 and then something that does any action。 So you know。

 adjust adjusting the packet in any way that we need。 And know。

 the basic things that you'll do there are things like the T TL， the checkum。

 but you might do more complex things in other networks might where you're not just doing straight I forwarding。

 you might put another header on or these kind of things。



![](img/e98db17db9b24c6be7d77eb28bed8684_25.png)

Now， the actions in hardware kind of break down into into two sets。

 Some of them are really easy to do in hardware。 You know， like decreasing the T T L。

 It's pretty clear where we do it。 We know it's a certain place in the IP header。

 We know that we just need to decrease it， Perf， We can do that in hardware easily。 Check some again。

 We know exactly what we need to do， More difficult whether there's more flexibility。

 And so things like I options， That gives us a problem where we have to think about what is the option。

 What should we do with it。And so and we don't really have that many that much time。

 that many cycles， that much work that we can do per packet。

 so in these cases we essentially try and avoid them， we can deal with them， but in general we say。

 well there shouldn't be IP options either shouldn't use them。

 we shouldn't put them into packets or allow them into some networks even filter to them。

And then fragmentation。 this ischievable。 So this is where we've got packet。 That's big。

 Now the link we're trying to send onto is smaller than that。

 So we need we need to be able to break it down。 And so this is achievable in hardware。 know。

 we we can figure out where to slice it and where to add the right headers。

 but we typically try and avoid it because it comes at some cost。

 some cost over and above just forwarding the packet。

And so the way that this is achieved usually is rather than is having some agreement as to what the MTU。

 the maximum transmission unit should be across the network。

 And so on the Internet that's 1500 bys across internally to the networks。

 it might be much bigger but inside people's networks。

 they might have their own agreement to say oh we allow 5000 bytes， we allow 9000 bytes。

 its various different values it's sort the domain local choice。 but across the internet。

 we say well it's only 1500 bytes and this is fairly baked at this point I think it would be an extremely difficult thing to coordinate changes to allow this to increase。

 but we do that having these kind of mutually agreed standards gives us a way to be able to avoid this functionalityity and be able to keep the routes as efficient as possible。



![](img/e98db17db9b24c6be7d77eb28bed8684_27.png)

But we want to focus on lookups， lookups of where we really need to know what happens。

 and this is really the core functionality of a reus， so let's dive into a bit more detail。



![](img/e98db17db9b24c6be7d77eb28bed8684_29.png)

So what is what is look lookup in the end of the day， Well。

 it's figuring out where this packet should go。 So we have to do a look up based on what output port is it。

Now， the ideal would be that we do one lookup and we get the forwarding entry that we need to do and off we go。

Which means that we need an exact match on the destination I P。 You know。

 we have the full I that comes in and we look it up in in some form map， some form of flash map。

 Okay， great。Off we go， send out this packet， Order one looker， perfect。Other than， well。

 we have two to the 32 IP address， IPV4 address， we have two to the 128 IPV6 addresses。

I'm not even going to try and figure out how to see the numbers， but the IP6 number。

 but they're big numbers right， we would have to have a really really large forwarding table with all these entries in to be able to do these exact matches equally we have to figure out updating these tables and keeping them current the these large tables a lot of work to be able to keep keep current。

Andor ignores a fundamental thing about I addresses。

 which is the hierarchical when I want to start a network， say let's say I'm Google。

 I go to some internet registry's the people that assign I addresses and they said to me hey Google。

 here's a big block of I addresses。 You go and figure out what you're gonna to do internally We don't care。

 but here's your block。 So give me an IP prefix of some size。

 and then internally I assign it maybe go to the guys in search and I say okay this is your。

 this is your prefix your IP prefix。 I go to the guys in YouTube and I say something similar and we kind of divide it down like that。

 But from everybody else's perspective。 they don't care that I assign a search or to YouTube that these need to go to Google and Google can figure out where it should send the packets itself。

There is this kind of inherent hierarchy to the way that we have IP addresses and practically on the internet。

 we don't use any smaller blocks than 256 addresses。

 you cannot go and announce a block of smaller block than 256 a s 24 prefix to another internet network you just won' to listen to you。

 it'll filter it。Internally to networks， we do have to think about it， though， because。

 you know you might have an IP address that is just one IP address a slash 32 prefix that we have to care about。

In general， we can think about how to exploit this hierarchy to give us to give us more compact tables at the expense lookup complexity。

 know， we can't just do this single lookup on the exact destination IP address。 Now。

 We have to think about how can we do。How can we look up something more than that？So。

What does that work， What does that mean， It means we have to try and find the I prefix that matches the。

 the packet that we're trying to trying to root， trying to forward。So let's look at this example。

We've got Verizon， they are connected to AT&T。 AT&T's got a bunch of downstream customers。

We've got a packet here that's coming going to AB XY。So in that scenario， we're saying， okay。

 the destination of the packet is A B X Y。And we want to go and look that each network has to look at its forwarding table to say。

 well， where should I send that， And what it's trying to find is the prefix that matches that address。

So Hizon here has a slash8。 then says， well， I don't know anything other than that should go to AT and T。

ATT and T then has inside it says， well I own a slash8， but actually internally to my routing table。

 I know that UCSF should have A D， LBL should have A B， and UCB should have A。So in this case。

 AT and T does some lookup and it says， well， what prefix in my root table matches In this case。

 it's something that starts A B。 A slash 16 means that the first twoocts of this address are fixed。

 so it knows that it needs to send it to the LBO next top。

So that's all very nice when there's just one route。😡，But in practice， we have in the Internet。

 we don't just connect with one person and have this kind of tree structure。

 We have a mesh of different networks， All the networks interconnect to each other differently and can interconnect with each other in much more meshy fashion。

 So let's like think about a simple case of that where。

Here we have LBL that decides it wants to connect directly to Verizon。

So Verizon now has roots that it's got this A slash A route that says， well。

 everything in it that starts with A， that should go to AT and T。ATT&T still got the same table。

 it's still got all those individual networks knowing where the downstream bits of the subdivisions of that prefix are。

 but now Verorizon also knows that LBL has got AB16 so it knows that anything that starts AB。

 those first twooctfi should go to to LBL so in that scenario well we actually need to know not just what prefix matches。

 but what's the longest prefix that matches so that we can send the packet to the right network。

And this is longest prefix match。So essentially it says take the most specific route that matches the destination of this packet multiple if the address matches multiple purposeses。

 take the longest， the most specific， if it doesn't match anything then we have a default route so that's the route that says well if we don't know anywhere else we'll just send it to this to this other next thought that might be able to do it some cases we might not have a default route。

 if we don't have any route for the packet we just drop it， we don't know where it's got。

So LPM is the mechanism that gives us the way to do those lookouts。😡。

So we'll spend a bit of time stepping through a few examples。

 So let's think about this pretty simple network here。Where we have four different ports。

Each one of them hass got a prefix， they don't overlap， P1 here it's got the 2011。300 slash 22。

And so on through the other ports。 you can see there's individual ports mapped to each previous。

 one per port。And so we want to find a matching route。 So we have this packet that comes in。

 it's going to 201，143，7，2，10。And we want to figure out， well。Where should that go。

 what port do we put that out of， that's the lookup mechanism that we're trying to do。



![](img/e98db17db9b24c6be7d77eb28bed8684_31.png)

So how do we do that？What we will do start is we start by converting the addresses to binary。

Rather than think about this as 201143， we'll think about as 11，lah bh blah， blah。

So and then we do the same thing in the routing table and in the routing table we have some concept here of wild cut know bits that aren't fixed so you can see here whether the hyphens are whether the horizontal lines are in the address Welllash22 has the first 22 bits but the rest of the mobile cut know that's what we said the prefix means prefix is this many bits are fixed and everything else is variable So we convert the routing table into that form where now each one of these entries has the full specification in binary of what what the mask that we should look at is。

And if we think about if we kind of ignore the first set of parts of this address because at least the first two octares are completely fixed and even the first half of the third one is fixed and we think about these three bits。

 then what we start to do is we look at each bit as we go along and we say here okay we've got a one So look through our table and say。

 well what matches here well this one doesn't because there's a zero in this bit position。

But the remaining three do， they all match in， you know， they all match the one here。

So then we move on to the next bit， we say， okay， there's a one there。Now， in this scenario。

 like we look again， we say， oh， well， we look through these prefixes and we say， well。

 this next one， this top one's got a。Got zero here， but we wanted a one。

 so that's not the same prefix。Again， we look at the next one， something similar。

 we can say there's a  zero there。This last one has a one here。 Ie。 we match this。

 and it's got wild cut afterwards。 So we know is going to anything is going to match。



![](img/e98db17db9b24c6be7d77eb28bed8684_33.png)

So in a naive implementation here， we could say， let's check the incoming address and binary against every。

Prefix that's in the table and select the longest one that it matches with。

But no this isn't check the address against all prefixes and find the one it matches the most bits with。

 We really care that it's got a fixed bit string， know the prefix matches。

 not just that these two prefixes have most in common。So we need to do this bit by bit comparison。



![](img/e98db17db9b24c6be7d77eb28bed8684_35.png)

诶。你系做。So now were trying we want to do that lookup， but it's kind of easy when we had four prefixes。

 right， we could just step through each one， each of them。

 The lookup is on the order is on average in the order of the number of entries。

But the IPV4 internet is about a million prefixes。 So every time we get a packet and do a look at we'd have to look through one average a million different entries。

 scales really poorly。So what we want to look at is how might we use the structure of addresses？

To be able to to be able to improve the efficiency of that lookup。

 And so we can leverage the fact that there's a tree structure of binary strings。

 So here we can see like we've got every one of these these addresses that we were talking about before converted into into a binary string。

And and a mapping of them。 And we'll just really think about these three bits in the middle because I think we。

 if I spend the morning reading out binary strings， it's probably going to be tricky to follow。

So let's think about these three bits， the blue ones here and the orange ones here。

 and the mappings that they go to port。So we'll look here that this is just those three bits pulled out。

 we'll focus on where the differences are in the addresses。

 that's why we're throwing away the rest of them and so we have four different entries。

 we have a one that starts with zero and then two wildcard 100。

 a 101 and a11 and then a wild card switched to using an asterisk for the wild card here。

And what we could do is we can take those and we can draw those into a binary tree。

So we can start out with nothing and then say， well， if the first digit is a0。

 take the left hand branch， if the first digits are one。

 take the right hand one and go through these three bits and draw the binary tree that describes them all。

Now at each point in the tree that we have a forwarding action that we associate with it。

 we can attach that to that node in the tree。So here you can see this orange note up here。That's go。

 that's where we said， well， it matched the0。 And then there were two wild cuts on the right hand side。

 where we didn't have anything that said it was a one and matched if there was a one， then wild cut。

 it didn't have an entry there。 So don't have anything。On the rightmost branch on the one。

 Well we did have something that said there was one，1 on then a wild。

 So we attached the pot 4 action there。 And then down on the other branch， we have， well it was a0。

 And then we have exact matches for the three bit。 the three bits there。

 So we have two right the leaves of the tree。 we have two forwarding actions that we installed。

 So that kind of looks like this。 If we ignore the bits that didn't have many actions attached to them。

 this is what we end up。 We end up with this tree that's got different points in it。

 It's got the forwarding actions that we're going to take there。

So now we want to do a prefix match in that tree。 So we were saying before that we're going to step through the bits and do a comparison。

 So here we say， okay， this is 1，1，1。 So now we walk down the tree from the top。 we start to say。

 okay， matches everything。 We's got a one is the first digit。

Then next digit is a one and now we've got wildcard， so this matches is this case。

 so this one on one would go out port4。So that's you know。

 and if we were to take something similar in other scenarios。

 we would if there were different bits here， we would walk the right branches of the tree。

 if it just had， anything starting with zero， we would find that port1 match that exactly know then for 100 or 101。

 we would have exact matches for those so we can walk down the tree and compare the bits that we're looking at against the actions that we should take。

But let's think about this multihoming case， you know where we've had this network that decided to connect to both Verizon and AT& T。

 so we didn't just have these individual actions in the tree。

 We had ones that potentially overlapped。So a mechanism of walking down the tree and just finding the action that that exactly matches。

 that might not be the right one。So let's look at what changes we might make because in this case。

 we've got some prefixes the overlap， you know， that if we think about the Verizon case。

 we're not going to think about exactly the case。 we're just going to add something to our three bit example here。

 Keep things simple。 And so here we've got port1。That has got  zero， wild Cup wild Cup and port 5。

 that's got 00，1。 You， those two overlap with each other。

 So let's think about how we might represent that in the tree。

And so what we end up with is adding just taking the same approach。

 putting these things in a binary tree and then going and adding these forwarding actions。

 still in the tree as to as they were where they were。

 But rather than having just one thing in this branch now， one on the left hand branch， we've got a。

We've got now overlapping entries，'ve got two entries that could be matched。On the right hand side。

 we don't have that overlapping。 So we've got the same approach that we had before。

 So now when we go and look at that packet， we go and take the comparison。

 We'd still walk down the tree and we say， okay， it's a 0。Next time we also hit a zero。

 so we match that port one action。 then we'd say， okay， well let's compare the third one， it's a one。

 Okay， we found the port5 action。 So for this exact match。

 we know okay we should forward out of port5。Bs when we get 0，0，0， we walk down the tree， we say。

 okay， there's a zero here， let's go to port one。To that0 wild Cup wild Cup。 It's going to be port 1。

 We hit a0。 and then we find a node that's got no action associated with it。

So well in our previous model， if we just look up the exact thing。

 then we're going to end up in a scenario where we don't know where to forward this packet。

 So we need to tweak our design a little bit， we need to say rather than walking down the tree and finding the exact match。

 walk down the tree， remember the last action that you found。



![](img/e98db17db9b24c6be7d77eb28bed8684_37.png)

And then if you reach a stage where you don't find an action。In that hop， but you match the packet。

 then use the at the last action that you remembered。And so that gives you then a way to say， well。

 in the scenario that you have a exact。An exact match。

 you find you overwrite the last action when you find the exact match。 And when you don't。

 you just use the action that you previously found。 So if we look here， then we would have said。



![](img/e98db17db9b24c6be7d77eb28bed8684_39.png)

Okay， we hit port 1 with 000。 We remember port1。 We hit the 0，0 wildcard。 we say， oh。

 there's not a match hit。But that's okay because we already found port one。

But differently on the right hand side of the street， if we take the same thing。

 if we got to the10 case， the 110 case then we might。

If we had got to a case where we didn't find a match。

 we wouldn't have found something earlier in the tree to be able to look at。

 So we wouldn't necessarily know where to for that packet only when there was is an action associated earlier。

So。That's。That's essentially the fundamentals of the longest prefix matching。 but it's not the。

You know， this case where we have one prefix per pole， it's not really typical in the Internet。

 it' not really how things look really we end up with you know we've got even those 280 poles。

 even if they connect to different people， there's a kind of inherent hierarchy in the in the Internet where some networks have routes to a lot of other networks。

 So you're very likely to get multiple prefixes because even if you think about my Google example。

 maybe I Ive signed some addresses and I use them all for search I some addresses and I use them for YouTube。

 I might be announcing two prefix。Beal， you might perhaps overlapping prefixes like our previous example。

 so we might have several prefixes that are going to route to the same port。

So if we draw that out and look at this example， so you can see here they've got zero wildka World going to port one。

Two exact matches，100 going to port 2，101 going to port 1， and then one，1 wild going to port 1。

 So you see here that most packets go to port 1。Other than if they're an exact match。

When they go to Portu。So if we draw that out on the prefix tree， we will attach， you know。

 we'll go and pick the right node in the tree。 this is the full tree again and we'll say。

 okay at zero wildca wild card over here， there's port one。101， there's port one down here。

 There the third port one is over on the1 and wild card， and then our exact match for 1，0。

0 is over here in Port。So that would be the way that we can lay that out。

This is the the the layout that we just talked about。 You know。

 we just now pruned the pruned the things that didn't have actions associated with them。

 So same same approach we've been taking。But we can think about that in terms of a more compact representation。

 if we look here， then you know， most actions。The zero wild cow Wild got here。

The 11 wildcard here and the 101 here or go to port 1。 And it's only this specific case of 1。

00 that goes to port2。 So we can we don't really need to have this full representation of the tree。

 We can think about how to make it more compact。 And so we can just say， well， if we match anything。

Then it's port one， you know， any any option was was down port one。

 but now compare the bits down the tree。And if you do find a match in the tree。 Well。

 that's the we port to it。 So in this case， weve minimized the size of the tree by not having to store all the different actions to it by taking。

 exploiting the fact that we could tell something about how those prefix are assigned and choosing something that minimizes the number of lookups that we need to do。

And so every real router has this longest prefix match functionality。

 it's an extremely core part of the router。 know we think a lot about how the efficiency of it is。

 the memory utilization of it is because we really want to scale， like I said。

 there's about a million IPP4 prefixes， you can have more internally as you divide out IP prefixes down。

 IP6 prefixes too。 So we really want this longest prefix match solution。

 But this case is one optimization。 but there's different optimizations and complexity of。

Have solutions that you can take。So。We then have。Various heuristics and optimizations that we can make based on seeing what's actually out there。

 like as manufacturers look at what the deployments that they see in the network are。

 or they observe the global network or as folks like us do or we say， well。

 we don't need to have the exact matches here or we can exploit the fact that some destinations are more popular than others。

 we can exploit the fact that some ports on the route to have more destinations associated with them。

We can think about prefix sizes because or we know that the cases isn very likely that the internet prefixes are all can't be longer than s 24。

 so we don't necessarily need to worry about more bits。

 same 536 is's very unlikely that we have a prefix longer than a slash 48 that's going on the internet So those give us ways to be able to say。

 well let's design the way that the LPM lookup works in order to see what we fit in with what we actually see。

Another kind of key thing to think about is how quick it is to update you know with the control plane and running。

 we're running BGP and the internet， we've got a lot of updates happening and we need to go and update that tree in order to be able to keep it current with what the state of the actual network is and so it's not just how it's not just how quickly we can look up。

 We're also care about how we can update that tree and it current with the state of the world。



![](img/e98db17db9b24c6be7d77eb28bed8684_41.png)

Okay， so we've done some lookups and we now know what packets， what port something should go out of。

That's great。 Those can be the core functionality of， of。Of a router， right。

 we said at the start that the point of the router is to look up a packet and forward it based on the destination。

But。That's not all the router does。 and the systems are increasingly complex based on the more functionality that you put in。

 the kind of basic IP router we just talked about。It has subset functionality。

 it will limit know the hardware that you need as well as the software complexity。

 but there's more and more features that are used in routers to be able to implement different things and different business objectives。

 And so one of those things is queuing。So rather than just saying， okay， well。

 we'll take this packet and we'll forward out this port。And if the port is busy， well， you know。

That's bad。 We We'll have to figure out。 We'll just put packets onto the link in whatever order。

 We might want to think about， well。Actually， this packet is more important than this other packet。

 So maybe that customer is paying us more money。 maybe that customer is maybe that traffic is related with to voice traffic。

 which has a latency bound worked on networks where that certain packets are keeping broadcast TV online and they're very delay sensitive so they need to be got quickly to the destination and we don't want to lose them because you lose enough with them and people's TV screens go black and they get pretty unhappy。

 And so the queuing mechanisms in the line card which are。Implement it as a kind of output function。

 give us ways to be able to knowing something about the IP packet。



![](img/e98db17db9b24c6be7d77eb28bed8684_43.png)

To be able to figure out how to send that trap。And so。There's kind of three stages to that。

First of is classification。 I said there， well， maybe this packet is more important than another packet。

 maybe this is a voice packet， maybe this is a TV packet。Well， those things are classification。

 they're about how do we tell for a packet， what cue。

 what subset of function of forwarding behavior we should put it into。And we might have， you know。

 different strategies for that。 We might say， well， this whole port， if a packet came in on port 1。

 then it's a really important。In too， it might be less important。But for other cases。

 we might want to look and， what's the mix of traffic on this port？

Maybe this voice packet has also got some HTP traps and web traffic alongside it。

 so we might need to look at something that tells us about the packet。

And so that might be other fields of the IP header， like the Dserv code point， the DSCP。

 some fields in the IP header that lets us do that marking。We don't have。

 some management of the buffers。 So we' said， well， okay， there's a lot of traffic coming in。

 maybe there's， know，2 10 gigabit ports coming in， and we need to forward them out the same 10 gigabit port。

Too much traffic to send into that link， now we could just put it into some memory。

Hold onto those packets and send them if there is capacity。

But have to figure out how to manage that memory。 Maybe we want to say， well。

 we shouldn't let that memory get completely full or we should reserve some room in case we need to hold onto an important packet。

 So we end up with some。Some mechanisms on the output link on the output decision to be able to say。

 like how do we really classify， how do we really want to deal with the fact that we've got too we've got to deal with this packet。

 You know， we've got too many moon packets to send by this link and not use all the memory in a uniform way。

 So that buffer management is another thing。And then the third part of queing is scheduling。

 So now we've got all these packets in memory。 How do we choose what order to send them out。

 know if we've had different packets， then we should maybe if we'd had different cues。

 maybe the voice packets are really important。 we should get to those first really are delay sensitive。

 So we need to get them out into the wire as quickly as possible。

 Maybe other packets we don't come till later on， maybe let more delay to E should we let all the voice traffic go or should we drop some of that should we say there's no capacity for the web traffic。

 Those different classifications and different scheduling behaviors of how to put the packets on the wire again introduce complexity into the router。

And you can kind of see here that we talked about， well。Look。

 we don't have very much time to do these very many cycles to do these functions。

 the more things that we introduce the route needs to do， likely the fewer packets it can forward。

Or the more cycles will need like the less capacity it's going to end up with maybe have the same chip。

 but it can't do as many ports it's got to do because it's doing more operations per packet。

 So the overall complexity of these systems。Especially because they're designed to work。You know。

In many different deployments ends up being pretty high。

 And so some of the advances in the capacity are to do with limiting that functionality。Today。

 Google doesn't on the Internet。 essentially So the question was I'll just repeat it。

 It was who gets to set the DSSCP bits， Who gets to say the classification of a packet Now。

 on the Internet， we essentially just don't trust anybody right if you can send me a packet and tell me it's really important。

It's really important to you， but is it really important to me？😡，Probably not。

 like or maybe it's not。 So what we do is we bleach the packet。Anything that comes in。

 we rewrite all the bits to 0。 and we say， sorry， it's just as important as every other packet。

 no matter what you thought about it。 So there's not really any idea of this kind of。

Differentiated services on the Internet。Now， I've worked at providers that are selling private networks to people。

 And so if I have a customer they're running their office network and I'm providing interconnection。

 then they can pay me and say， well actually this voice is this voice packet is more important than another。

 So in those scenarios， that's where you might allow the customer to set the marking and they would choose well this packet is really important to me。

 But it ends up being part of the service that you sell。

 So if the service is basic Internet connectivity usually you don't have any ability to do this control and but in private networks are more premium products in the way the industry would have historically looked at them。

 you get to choose Now a lot of these things are really to deal with。

Not in having engineered a solution to work on the Internet。So， you know， services like Skype。 Well。

 people said， well， I get actually better voice quality here。V Skype， then I got from my phone line。

 So why wouldn't I just use Skype and Skype was engineered in terms of the codeex users in terms of the encoding it's using in the packet to work well without having this prioritization historical phone networks that we're doing weren't engineered that way。

 And so it's becoming increasingly irrelevant， I would say to have this kind of prioritization but it's often used as a way to manage priority between different bits of the business。

 So when I was British Telecom for example， then if you were a commercial customer a business customer than you were more important on the core network than you were if it was a broadband customer。

 So that kind of business priority is enforced rather this rather than letting customers differentiate。

So this being said， along aside to say there are many complexities that come in that's one of them kind of mentioned throughout。

 there's also a few other things that might make this more complex， you know。

 especially when we're not just forwarding a packet based on its destination。

 we're doing more actions， we're maybe having to take headers off the packet that's got more stacks of headers on it。

 other things like that we might need to do more， but we're just going to assume that the kind of simplest possible picture。

Which is there is no classification， every packet as important as the other。As every other one。

We'll deal with buffer management in the time on tradition of if it's full， we'll just drop it。

 So we call that drop tail， tail dropping。 So if it's full。

And there's no room for us to store this packet， the links full。

 so we can't immediately put it onto the packet well， just throw it on the floor。

And then we'll think about a PO scheduler。 So the first packet that turned up is the first packet that we said。

 and that just gives us the simplest possible setup to be able to think about forwarding and as I kind of described through a couple of the apps then there's just many complex scenarios here and they're really used to kind of implement some of these business objectives that we have for the networks that we run on just forward packets as fast as possible。

 their forward packets and think about the service a little bit。 and that's why queuing and comes in。

So。To recap。Tals about routes， they have different planes。

 we talked about the three different planes， the control plane that is used for programming the forwarding entries。

And dealing with exception。So that's where we're running our routing protocols。

 we're telling the forwarding plane the data plane what to do。Of the management plane。

 the often neglected interfacing with the device telling it what to do， who it is。

And sitting hearing from it what's going on in the network for us to be able to know what the network is running like。

And then the data plane， which is really， the thing that we want from a route to the packet forward。

The data plane itself leverages those trade offs in software and hardware。

 where we can use hardware in a。We can live with the inflexibility， but we get the speed。

 then we use that hardware。 We have dedicated forwarding chips， so they're doing that。

But where we need flexibility， we end up with software。

 but we have to deal with the fact that it's slower。And the main data plane challenges is speed。

 You know， we want to scale to those systems that are 230ter per second。

 And next year will be 400 per。 in a few years will be 400 per second。 We want to deal with that。

 So we need to be really， really efficient in terms of packet processing。And really， you know。

 updating the packet header， the things that we restrictd ourselves to。

 it's pretty easy and hardware。But the LPM lookup， the real forwarding of packets。

 according to internet， those routes they installed， those IP routes they installed。

 That's the more difficult bit。 And that's where we kind of talk through the LPM process。

 the longest。So， unexpectedly。Did not use the whole time。Questions。Yes， it usually。

 so how this kind of actually ends up tending to work is that you have the fairly。First processing。

 they're breaking down of the packet， get into into the chip and the voiding chip。 And in this case。

 we just needed to do an LPM lookup。 we just need to one lookup。

 but sometimes we have to do multiple lookups in different databases to be able to figure things out。

 So that's really where the core of the cycles end up being spent the fabric is also quick。

 So the real constraint when we're looking at these routes is usually about how fast can that chip go and do the functionality that it needs per packet。

 And we look at that and we think about how many packets are going to arrive And why we talk about things like the size of the packets because 400 gig link that's got 1500 by packets many fewer packets than if there's 64 by packet。

 So what we do is we spend essentially a fixed amount of time per head or over a packet。

Not the size of the packet。 So we really care about it when we're talking and doing some of these design analyses on these forwarding chips。

 we're saying， well at 200 by average packet size， we can achieve this rate。

 And so that's where sometimes the number we talked about the capacity。

 the R number of people link might not actually be the number that you saw on the line。

 it might be lower than that。 It's like the little links this route I put up。

 There's no way that forward 1。4 gigab。Because it's doing a lot of things in software。

 so even though you could give it one4 gigabits a second of traffic。

 just not doing it because they're spending a lot more time in the phase and the lookup phase and in the forwarding than it would need to do to sustain that line rate。

Sure on the right hand。So historically， yeah， how that works is this is Internet interconnection。

 It's called peering。 It's when two networks connect to each other。

 And there's a few different ways they work。 One is that you buy from somebody else。

 So I go to a provider and they say， hey， level 3， I want to buy access to the Internet。

 and they sell me access to all of the Internet， and they charge me for that link。

But then there's also connections where I say to， you know。

 maybe I say to a Verizon or I say to Sonic or my IP here。 and I say， hey， I'm Google。

 I'd like to extend you traffic for YouTube， and I'd like not to pay for it。 Thank you。

 and you'd like not to pay for it。 So we have a negotiation and we say， okay， great。

 we'll interconect with each other privately。And how that tends to work is that then we agree where it's going to be。

Maybe we'll do it multiple places across the country and we'll go and then yeah。

 somebody goes and physically plugs in a cable， one of the things we've done at Google and why we've spent so much time with the management place。

 we have a lot of links like that。Thousands of links like that。

 And they all need capacity upgrading things。 So we've actually worked on a way that that software automated。

 So a lot of the time when somebody comes and asks us for a link。

 the first time it really reaches a human is when the human is plugging something in。

 And then everything else is machine drums or robot driven from there。

 But yeah there's kind of the commercial negotiations that go into it and then the practical technically setting it up and why the management plane is really important in this space is because someone needs to tell it like we' this link is going to go between Sonic and Google or AT and T and Google。

 we're going run BGP on it。 So we have to tell the route of what to be doing in terms of control plane protocols on those links。

Sure。Yeah， so that's why we're kind of picking the， the the simplest possible model。

 There's a lot of sort of。Ways that we think about how to manage that buffer occupancy。

 So you might take that into even if it was just a single class， you might say， well。

 I don't want to be full and some things like TCP。 Well。

 it's better if I drop some packets and they back off and they don't keep sending me。

 So you might do randomly dropping packets before the buffer was completely full。

 But then if you've got different classifications， you might say， well。

 why would I want to drop this really important packet before I drop this other one。

 So you have a weighted weighted random early detect。

 That's what we call the random dropping that gives you a way to manage that buffer。To say， okay。

 well， the buffer can be this full of these packets， and if it gets greater than this amount of fall。

 then start dropping those packets。And you end up with these slopes that kind of give you a complex algorithm to say。

 based on the classification， how should I use the memory that's available to me？No。

 I think that there are local networks where flooding when you don't know what to do is okay like you might learn there's some learning but in IP routing。

 we don't do that right we don't look and say， well I saw this packet on this port so therefore it must like that address lives out there we have the control plane protocol to deal with it So what would happen if we flood the packet well probably we send out the same port we just got it in and the guy on the other side or the rid on the other side would say。

 well you usually be forward in that and so then we end up with routing loops So we just have routers or different parts of networks that are just passing the same packet backward and forwards until the TTL expires。

Why the details are really important， We don't want that infinitely。But now， in general。

 we want to drop the packet。 It's usually a good signal。 And if you don't want to drop the packet。

 that's why you have the default route。 that's so know when your laptop is connected to a network。

 well it doesn't need to know about the hot internet。And if we think about it just needs to know。

 well。Its the Internet is via that routes are over there。

 So the next top everything is set to that the default route。

 And so if you don't want to drop a packet and you want to have somebody else handle it for you。

 then the default route gives you that rather than flitting。That depends on the hardware。

 So and this is somewhere else where we make hardware trade offs。

 So if we're thinking about the kind of chips that we might be building and talking about doing 400 gigabs second on 36 ports or maybe there's two chips。

 the line cards are 18。Pooruls then。88 buckets per port is probably normal。

 But if we think about something that takes in some device that connects a lot of broadband subscribes。

 a lot of homes to it。 then in that case， we've got lots of individual subscribers。

 lots of individuals that are all connected to the same thing。

 we might want to classify between them。 So at that point， we can get up to 64，256000。

Classifications put。And what does that come with， Well it comes with it。Bunch of memory。

Comes with a bunch more complexity for managing them。

And so that then means that the complexity of the line card goes up。

 Usually what that means is then the throughput goes there because we've got much more to do per packet。

 but also we just used a bunch of that we've essentially got something that's probably 60 centimeters by 40 centimeters2 by four and a half the whole amount of PCB that we can deal with。

 So the more things that we put on it that are doing not forwarding， the less forwarding we do。

And so the， the density， the kind of capacity of those routes tends to be lower。 But in those cases。

 yeah， we can end up with extremely complex scenarios。

 And theyre usually in this kind of subscriber management where we're dealing with individuals rather than port。

Now， if you're into network， you're really only dealing with ports and you're probably dealing with one class per port。

 So you maybe don't even use those internally into a network like Googles。

 though we have different things that are on the network。We have net traffic that's to do with。

Copying between machines。Well， maybe they can just come back when the net was less busy。

But then we have traffic that's you did a search on Google dot com。

 and you get really annoyed if we don't deliver that。

 So we want that to be more important than others。 That's where we have some level of classification。

 even though we're carrying just Internet traffic。 And that's cases it's our business objective。

I make the joke that I don't know what's past the headers of the packet。 like for rooting。

 I just that we don't care。 So we for sticking for these like IP roots。

 where we're doing layer3 forwarding only， we just look at the headers。

 Anything else there it actually is great。 It's bigger because that means that we get some more。

 you know， get fewer of the packets。But these systems really。

 they might be able to do some looking into the into the packet， but they really don't。

 we really don't want to get involved in that because we really want IP to be transparent to what people do on top of。

So what we do tend to look at sometimes is we look at like we say， oh， this is IP。

 but actually inside it。 it's got TCP。 and we want to look at things like the source and destination port。

 but we usually use that for entropy when we're trying to like you can imagine that we didn't really mention it here。

 but you can have a route that goes by two different ports and we want to figure out how to share like load balance traffic across the two different ports。

 So we might look a little bit into the header。 we generally try not to。

 So and then if we're trying to do things that。Line rate， about 400 gigabit line rate。

 extremely likely that you can do anything with the header。

 So when you see things that do the firewalls， which might need to look further。

The the more complex they get， the less。they end up being。

 and we might be able to do some things here。 Like we might be able to do what we called access controller。

 So that's where like we don't allow any packet that has TCP port1，47。47 minutes。Apparently。

 we're going to drop it。So in that scenario， we would say， okay， there's this offset into the packet。

 if you match that this is a TCP。Protocol in the IP header。 Then look at this offset in the packet。

 which is the port number and drop it。 So we can do those kind of simple kind of equality checks。

But it's another thing that comes at some cost。 Actually。

 what we end up doing is having more hardware and a lookup table to be able to do those kind of exact match look up tables earlier in the process。

 And so it's another place where。The more complex you want those。

 those inspection of the packet to be， either the more complex you make the router。

whichch probably comes at the cost of capacity， or you just say， well。

 I don't do them and I hand it to something else that goes slower to be able to do that more complex one。

But we don't really look at this。I passed the packet ahead as it tool。Good question。

 It depends on your capacity planning approach。 So when we look at network， what do we really do。

 when we're building a graph of bunch of nodes， bunch of edges。

 and then we've got some demands on the graph So the demands are where the traffics coming from and where it's going to。

 And so what we'll do is we say， well， you know we think that there's going to be this much traffic coming in in New York。

 And we think it's going to be served out of this data center in Tulsa， Oklahoma。

And so we then build enough capacity。And so if we built enough capacity， well， it shouldn't get full。

But if we haven't， then it does。 And then you can then say， well， you know。

Do I build all the capacity that I have to。So I could go and build like every time I I could think about those guys in search over there。

 they really want to copy these big amounts of data apart know， across the network。

 So I should always have the capacity available to do them E， it can a bit smarter and say， well。

 rather than giving them completely all the capacity that they want because TCP will ramp up and try and use as much as they can。

 I can say， well， I'm only gonna give it。I'm just getting a capacity plan that they can do 200 gigabs a second of copy traffic from Tulsa。

 Oklahoma to Council Bluffs， Iowa。 These are the kind of places that Google has data centers that I。

 as a Brit was not aware of。Have been to Council Bluffs Iowa multiple times。

 which is not a sentence I ever thought I would say。nothing against it。 I just hadn hadn't heard of。

 So in this scenario， we've got a， you know， we didn't necessarily build all the capacity for them to do that kind of copying of traffic。

 So in that case， we do have pretty buffers because someone's trying to use all the capacity possible。

 And one of the metrics that we look at in the networks that we build is because we're trying to build these scales that are really。

 really challenging。 We're we're looking at 400 gig。 We've already got。 We're looking at 800 gig。

 Theyre not being produced yet， but we're already planning on them being there。

 So we're always at the edge of trying to get the maximum capacity that we can。

 And so we want to use that asset as well as we can。 So we're really trying to say， you know。

 if the networks's 100% full， That's awesome。Because then we're really using that infrastructure that we build as efficiently as possible。

 So for us， they're pretty full。 in other networks that Ive worked in。 you know。

 we had lots of business customers they're paying a bunch。

 And they they pay us for 10 gig of capacity。 but they just never use it。

 but they want it there just in case。 And so in that case。

 those networks had extremely low utilization。 And so it really depends on what the network looks like and how much of it you build if you can scale about something and then how you want to manage traffic on it。

 So it's kind of an overall view of both the service you're trying to provide like your broadband network provider probably says well。

 on average a user uses about this much traffic。 So I'll build the network according to this with some error margin。

 but。What we used to worry about in the UK was we got streaming deal for British for soccer football。

That one took some look up。 and it wasn't order one So at that point。

 everyone's watching these games on YouTube or on our streaming service。

 And so we hadn't built enough capacity for it。 Sos there's just different types of network have different times where it is usually Internet traffic is kind of diagonnal。

 So you end up with like a spike in at some point And then two spikes a day， basically。

Business traffic tends to offset。 So you can do things trips like how much of the network do I build based on these different customers and sort of overlay the two to get the best utilization out of the network。

 But it's fairly common that we're dropping package。 Even just spikes of traffic make it happen。

 There there's some statistic where I've looked We have a counter all the traffic we're dropping in Google。

 And that is more traffic than some networks have worked on。I can't give you what the numbers are。

 but you would be surprised how many packets Google does it isn't carrying that we maybe could。Sure。

Yes， that so essentially， when I'm talking about that。

 it it's internal business It might be an internal business decision。

 So when I was a British telecom， for example， you know。

 we'd have business customers and consumer customers。 But that said， well。

 all Internet traffic is the same because it's。😊，Custom based on the customer， right。

 It doesn't matter who's sending the package。It's to do with it。

 But the net neutrality discussion is about， well， if I have ways to be able to classify traffic internally to my network。

 how do I choose and to drop them And one thing you could say is well。

 if someone comes along and pays me more， then I'll carry their traffic。 And so you have to pay me。

Now， that has implications。 So it has implications for how the Internets worked。

 Like if if Netflix would got charged or YouTube would got charged for every time that it tried to do these。

 these startups would never have produced a service because they would never have been able to afford to have a decent quality service。

And so that， that whole yeah， is extremely intertwined between the how to classify package。

And then the commercial negotiations around them that then has these regulatory implications。

I think my observation is。Telcos like to the people that provide bulb connects。 like to be say， oh。

 it's really hard right。 We have to carry all this traffic。 People keep sending all this traffic。

But what your customers doing， they're buying an internet connection so they can get all that traffic。

Your commercial models should probably work like your product is being sold based on the fact that there is like YouTube or those kind of things available。

 So the whole practice is an interesting discussion about who's perceived to be taking the value out of the the。

Out of Internet connectivity， and。The classification really is the technical means by which you could do that。

Honestly， is a footnote on a footnote to the whole discussion。Yeah， so essentially。

 you end up with most networks that that see this， switch is essentially every new。These days。

 some mechanism by which you mitigate those Ds。So you have an attack。

 ands the whole similar thing to this Qing thing， right， We have to go to classify。

 Lets say what is the DD。 What does it look like And then we have to then we want to be able to say。

 well， where can we drop that now， the ideal is you drop it outside of your network。

 Maybe not possible。 Some places you can you can ask an upstream providers signal to them。 Hey。

 I don't actually want traffic to this destination address。But in that case。

 you're saying per destination address。 So you've kept the the lookup complexity just on the destination address。

Then maybe at the edge of your network， you say， okay， well。

 same thing I could make the same destination based thing。

 Maybe I could do a simple port based one if you're trying to Ddos something in Google and you're sending just a port same destination I in a single port。

 Well we can probably filter that in the complexity of the routes。 but above that。

 we need something that can look into the body of the packet to be able to do more classification and so in that case it tends to be that you have we call scrubbing services or mitigation services where you say well any traffic that's going to somewhere that is getting DDOS。

ぱいっています。Redirected to some other service， that is more capable of being able to look into the packet and probably do that in a parallel way because I don't think you know。

 the numbers these days for these kind of attacks。Mind blowingly astronomical。

And so that's then how you， you end up with that that mitigation。 Now， at the end of the day。

 like if you send more traffic， then there there is input capacity。

There's not much we can do because you've already drop the packet on the other side of the link before you could even do anything with it。

 And so that's part of the capacity planning process。

 Sometimes you you're already trying to build these networks to be reliable。

 So if we want 100 gig of capacity into another network we're definitely building 200 gig because all kinds of things could fail on those links。

 But we've got some bulk there。 But at some point， you essentially run out you potentially run out to capacity。

 And that's one of the challenges about dealing with attack traffic like that is to be able to say。

 well， how much capacity do I want to build ahead of time。

 increasing my cost the cost of my network increasing the number of things that have to manage to be able to absorb something that might rarely。

And when you see somebody get kind of knocked off line through this is generally because they ran out either scrubbing capacity or they ran out。

 link capacity into the network。It's actually quite an involved set of interactions between networks to figure out how to help mitigate them。

我在。

![](img/e98db17db9b24c6be7d77eb28bed8684_45.png)