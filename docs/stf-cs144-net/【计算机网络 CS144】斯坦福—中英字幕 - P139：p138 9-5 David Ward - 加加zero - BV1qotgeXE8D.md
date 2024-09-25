# 【计算机网络 CS144】斯坦福—中英字幕 - P139：p138 9-5 David Ward - 加加zero - BV1qotgeXE8D

 So， hey David， thanks for making this call。 Hey， you've got Phil。 Good to see you again。

 Good to see you。 So first of all， funny story。 We're trying to do this online video call recording。

 I tried lots of stuff and then of course， David， given who he is， just snap some fingers。

 and then some magical people made it all happen， you think， some pretty awesome technology。 So。

 David， what do you do and how did you get there？ So。

 I'm the Chief Architect at Cisco and the story how I got here is actually quite， it's。

 probably longer than it is interesting to be honest， but nonetheless， I started off in。

 grad school back at the University of Minnesota in the mid 90s and I was working on a project。

 directing a research center trying to prove that a cluster of workstations around the。

 University of Minnesota connected over a high speed network could outcompute and outcompute。

 supercomputers。 And so， what was interesting about this is that we ended up building and deploying the world's。

 first production ATM network amongst a bunch of son and SGI workstations。

 I know most people on this call probably have only heard about those companies perhaps in。

 the annals of history or in some。c textbook。 But nonetheless， we proved in fact。

 given the right experiment that we could outcompute， a supercomputer。

 But the problem was to be able to prove this， we needed to connect supercomputers together。 So。

 to do that， we built the first production wide area network ATM network to connect Pittsburgh。

 supercomputer Minnesota， San Diego， all the big ones together。

 But then there was a small problem that once we built this out， this high speed network。

 was called VBNS， again， one of the very first big WAN networks。

 But the problem was that supercomputers spoke to each other over this protocol called HIPI。

 high performance parallel interface。 And there weren't a whole lot of HIPI interfaces available for supercomputers。

 So， we had to invent a HIPI switch and then we， with a group of folks that have started。

 to invent a HIPI over ATM。 Now， what was really interesting about this bill actually from an engineering point of。

 view is that a HIPI packet in those days was two gigs。 And an ATM fell out of 53 bytes。

 And across the wide area network， when you dropped 53 bytes， here comes two gigs again。 And so。

 we learned a whole lot about how to build extremely good wide area network package， generators。

 But as I move forward， I found out in my experiment， in my work that we also needed。

 to upgrade the Midwest University network， which was called CICNet， and how the University。

 of Minnesota was connected to the Internet， which was NSFNet in those days。 And so。

 we started working and upgraded Minnesota's connection to NSFNet。 Again。

 this is all pre-commercial Internet， which again， are down in the end of history。 So。

 we had to do an upgrade of that wide area network。 And towards this end， we started building， again。

 more WAN interfaces and more high speed， LAN pieces。 And then I found， you know。

 scratching my head while the PhD I was getting in physical organic， chemistry， that's hard。

 And this networking stuff is kind of easier and it's really kind of cool。

 And while doing all the high speed networking， I actually met the woman who became my wife。

 So I'm like， wow， you can pick up girls too。 You know， this is all working out well。

 So then I went to a startup that was building these hippie switches。

 And we thought we had a great business plan。 We are going to network all of the supercomputers on the planning。

 There was one small problem with this business plan。

 One was that you only need one switch to connect like all of NASA Goddard。

 All of these massive supercomputers。 You only need one switch。 Second business problem。

 If it wasn't volume， it was that a supercomputer goes for $35 million or some ungodly number。

 of tens of millions of dollars。 And a switch goes for about $350，000。 And we sold 12 of them。

 And so we're like， oh man， you know， that didn't quite work out。 But wait a minute。

 there's this whole like internet thing going on over here that looks， kind of popular。 You know。

 the internet had just gone commercial out of NSFNet and we had built this distributed。

 processing or distributed boarding switch thing that again had the first FPGAs and then the。

 first ASIX to build out these distributed line cards。 And wait a minute。

 if we had a Unix machine controlling this where the Unix machine was。

 actually running BSD and open source operating system that was really popular at the time。

 And we were using open source tools and routing tools like Gate D which most folks don't use。

 now but nonetheless was super popular then and actually ran NSFNet。

 And so we built a Unix machine on top of this cage of ASIX and FPGAs building and built the。

 first world's first distributed forwarding router at that time。

 Then what ended up kind of happening was that， wait a minute， this thing actually works really。

 really kind of well and is really fast and has a much different scaling property than。

 other centralized switches at the time or centralized routers at the time。

 And that startup ended up getting sold to a company called Ascend Communications which。

 back in the day was the world's biggest ISDN modem builder which everyone had in their。

 homes at the time， upgrading from those old dial up modus and stuff。

 They went to ISDN and then they went on to cable and other technologies of course as。

 well but nonetheless I left Ascend and went to a small startup that Cisco acquired in。

 1999 and I've been designing systems and ASIX and operating systems for quite a while but。

 one thing I just wanted to mention about that bit of history was that when I was doing my。

 PhD work and I was working on this cluster of high performance servers connected to a。

 high speed networking， my real work was in parallel programming and parallel processing。

 and operating systems and built out parallel virtual machine which was using IPCs and RPCs。

 across the high speed network in different QoS levels for the different types of messages。

 So I was a major league OS head and yeah I know well back in the day it was cool and no。

 offense to my other friends over there in Stanford but what ended up coming out of this。

 was a deep understanding for multi-threading， modular operating systems and that in turn。

 with the systems experience I had building chips and systems like I just described when。

 I showed up at Cisco in 1999 or just November 20th 1999 in fact at 8am over in the big exact。

 U-Office they handed me a pen and they said okay tell us what the next router is going。

 to be and from there it's just been a great opportunity to explore the different design。

 patterns that I've learned about and that I truly believe in and turn that into a lot。

 of equipment that is now running on the internet。 Cool yeah。

 well it's funny you said about chemistry is hard instead of writing code。

 and fun to give it an idea whose faculty here once said he started as an AFMA。

 You know math is kind of harder writing programs are fun right so that's really going into。

 computer science。 Cool and so you did a lot of work on a bunch of Cisco's major routers。

 Do you want to just mention a little bit about that or？

 Sure so I was the designer of the NCHEAP architect of iOS XR which is the current multi-chassis。

 parallel programming modular operating system running on the service provider line but also。

 was the co-architect of the CRS-1 which then turned into the CRS-3 which then turned into。

 the CRS-10 as we advanced ASIM designs have designed and helped do the functional design。

 of probably on the order about 60-86 now also worked on the ASR 9K the ASR 1000 most of the。

 optical kit that we sell as I was very much into optics and physics in the day and incorporating。

 in particular I think I'm sorry optical processing and routers themselves and taking the transponder。

 shelves which are such a huge cost of building the internet and building those effectively。

 directly into routers to reduce cost from there and all the while even back at Ascend and doing。

 things at the university you have to realize that the NSFNet community and regional meetings。

 turned into the North American network operators group and so I would。

 So I had to be deeply involved in there and then as we were building out NSFNet and then。

 building out the internet with all the providers when I went commercial we needed a lot of。

 protocol extensions to be able to peer with each other and build up services and came。

 up with effectively the current network architecture of the internet which includes exchange points。

 and how to do regional pairing and how to do settlement free pairing and frankly this。

 all we we invented all the protocols of now what we know of being BGP OSPF， ISI， MTECAST。

 MPLS etc to fundamentally solve some of the problems that we are facing on the internet。

 we when you couldn't get circuits delivered fast enough and you had constrained bandwidth。

 on your link you needed to be able to reserve bandwidth and have traffic engineering here。

 comes MPLS when you want to connect businesses in their own address space it's really really。

 hard to have overlapping address space in the correct and do the correct IP routing and。

 voila here come layer 3 VPNs and so it was a lot of invention by necessity at the time。

 and just having a ton of fun not only of course writing the code to finding the specs but watching。

 it all gets deployed really really fast and so that was it was a ton of fun and it still。

 is a ton of fun I'm still cranking away on new stuff you know I work with a lot of folks。

 there at Stanford and helped get open flow out of Gates 104 and build up the O&F and now。

 really focusing a lot out of the embedded OSPs and focusing at controller layers orchestration。

 network function virtualization and trying together trying to tie together server storage。

 switching and routing and get more services on the internet I mean basically Phil my red。

 and white blood cells are completely packatized and IP packets I never thought about our blood。

 being packed but actually Martin casado came in David gets left in the class talk about。

 SPN the whole sort of SPN vision of having controllers and global graph which you can。

 operate on to then push out to the switches and sort of that separation of control logic。

 and forwarding logic and so I think a lot of what you said will make sense actually to。

 a bunch of the students in this class they're pretty excited about the SPN so well I have。

 a slightly different view maybe than Martin and certainly when he was working at Stanford。

 is that having a centralized view of the topology is a great augmentation of the current dynamically。

 routed system and if you don't mind me to all pine just for a little bit second just。

 on this philosophic point a distributed route in autonomous acting set of routers forming。

 the internet in my opinion is does provide the fastest protection and restoration for。

 topology failures now when we started out or the the forefathers before me the internet。

 started up they were worried about frankly thermonuclear war and they wanted to have。

 a consistent communication platform that no matter what happened to any city or any。

 node the network could stay up well this translates into modern time hopefully we don't have to。

 worry about that problem anymore but what we do have to worry about our back hose and。

 other real problems of of things in our transmission network which as far as the networks concern。

 they can't tell the difference what caused a fiber cut whether it's a backhoe or or you。

 know whatever it is somebody with a forklift in a data center so I still firmly believe。

 in the in the tenants and power of a distributed routed network and we can get into this more。

 than just a second but I really find polar conversations that everything is distributed。

 the routed and or everything is essentially managed as really something best left for。

 the bar it it's not an interesting conversation for me in a nice conversation because when。

 you build and deploy transport networks or ATM networks or frame relay networks or even。

 X25 networks if I really want to date myself you do this with a centralized planner and。

 you what you what you get to see is you get to see across summarization boundaries and。

 to scale the internet we've got summarization boundaries of IP addressing all over the place。

 between autonomous systems whether it's Comcast AT&T or wherever you are in the world between。

 those big providers but also within those networks there are multiple autonomous systems。

 and within those those autonomous systems there's multiple areas like OSPF areas and。

 frankly those are the definitions of IP address summarization now all that's cool scaling。

 is great we all have a bigger bigger better internet but if I wanted to build a tunnel。

 between me and you using MCLS or using anything and I don't and I can't see your IP address。

 because it's been summarized into a into a larger block man we spent years inventing。

 42 different ways to leak prefixes and do all this all this fancy stuff in protocols。

 when what's the answer have a logically centralized view of the entire topology and if I want。

 to build a path between Dave and Phil I see your address and your topology behind your。

 area boundary and your summarization boundary and I can see mine over on this side and voila。

 I can build an end-to-end path with quality of service etc etc and that augmentation of。

 a centralized SDN controller or centralized controller in addition to a dynamically routed。

 network is something that I'm really focusing on and frankly it might be an expected conversation。

 you might expect to have with a guy like me given that I kind of came out of that world。

 but I also came out of the world where trying to do everything centralized for ATM or frame。

 and I was building in and or we were building permanent virtual circuits all across the planet。

 I watched the scaling properties of that just explode and when you're trying to deal with。

 not just tens of thousands but millions of potential circuits or slices you know in current。

 parlance because you know circuits are bad and now slices are good the scaling properties。

 to scale to internet sized stuff is really something that has to be well understood and。

 that's what dynamic routing and topology exchange is really really good at it's just。

 really really bad at seeing across the summarization boundaries so that two together the two together。

 are just rock and roll you know there's no disco involved in that one they are just they're。

 just cranking away。 Oh well so you know we talked a lot about the past and kind of maybe some of the things。

 that's the end of topping now but what are the things that you're most excited about that's。

 going on in routing and sort of the wide area in the internet today I know for a little。

 while you're working on securing BGP is that work still going on or what are you doing now？

 So I am still working on securing BGP but that's turned into a political quagmire of who's。

 going to hold it？ Who owns it？ Yeah I mean and is it the Department of Commerce which actually has the same call the IANA function。

 which holds all the roots of you know all of our naming and numbering you know I mean。

 it's just a political nightmare internationally and nationally because nobody can figure it。

 frankly I'll summarize it this way Phil nobody can figure out who's going to make money off。

 it and I'm not interested in solving that problem because that problem is a outside you。

 know commercial space somebody needs to hold the root somebody needs to handle all the。

 addressing somebody needs to handle all the certificates associated with BGP routes and。

 I continue to work on this with the FCC and other governmental organizations whether it's。

 the EU or others and the regional registries but it didn't make enough progress it didn't。

 go fast enough for me to get through these these issues so instead what I want to talk。

 to you about today of things that are extremely cool going on in the internet especially if。

 you ask me have to do with a technology called segment routing and what's different about。

 this and my goal with this technology and our goal the group of folks who are working on。

 it including lots and lots of providers is to simplify MPOX networking traffic engineering。

 and VPN services by actually removing protocol and the reason why this is a bit of a shocker。

 is that look I've spent decades of my career actually extending and advancing these protocols。

 so you'd think that I might be a guy who would just hold on to them religiously like this is。

 a hammer everything is a nail let me go find more nails or at least things that look close。

 enough like nails that I can go beat them but in fact what's really interesting is that。

 when you take a look at traffic engineering and wide area networking the operational overhead。

 and the complexity of it is in fact a major league problem and and the part of the problem。

 is that we require the network to hold state so when I set up an RSVP traffic engineer tunnel。

 I use RSVP hence the name but I use RSVP which signals hop by hop through the entire network。

 I'd like to reserve a gig I'd like to reserve a gig I'd like to reserve a gig when everybody。

 says there's a gig and make up your favorite number if you want more bandwidth then you。

 get go start sending traffic and every device in this path holds that state and so then we。

 are running into issues that well how many midpoint labels can you hold and how much。

 state can you hold and then we invented protocols that didn't require that kind of state and。

 they were called the label distribution protocol where we'd say hey here are all the labels。

 I'm advertising and another protocol we'd say like always PFRIS we'd say here are all。

 the next tops that you're supposed to bind them to and we built a stateless ampullis network。

 out of that but the problem was labels and traffic engineer tunnels only or the sorry。

 those tunnels were only following past path routing well what about all those other paths。

 out there that aren't passing my traffic what am I going to do now I've got all this。

 bandwidth deployed in the network I'd really like to use it oh and as a matter of fact。

 you know what if I would what if I would like to also use equal cost multi path and when。

 you take a look philosophically at if you want to think about that way philosophically。

 at how emphyllis networks are built the notion that there are link aggregation groups that。

 L2 like multiple ethernet interfaces in between routers or at equal cost multi path。

 which is multiple layer three connectivity between routers best of luck trying to balance。

 out your traffic across those equal cost multi path links one because they've been summarized。

 in your IGP and you can actually see all those multiple adjacencies and two how are you going。

 to organize a hashing algorithm network wide across lots and lots of boxes of different。

 eras and different different vendors and different a six and all the rest of it and。

 so ampullis I would say right now fundamentally doesn't solve the one of the major tenants of。

 the way the internet's built which is equal cost multi path adding lots and lots of bandwidth。

 between two routers for example if you need 400 gigs of bandwidth between two routers let's。

 say whatever between Boston and New York you can use 40 10 gig interfaces or 400 gig interfaces。

 or whatever the cases now how do I balance traffic across those that's the problem that。

 I'm trying to solve so what segment routing does is let's not use RSVP and hold all that。

 state let's not use LDP and try and match up and only use best path routing instead when。

 I pass the IP address of a router and I pass the IP addresses of all the interfaces off。

 the router no SPF and flood that information between all the other routers so that way we。

 know quote the topology of the network and all the adjacencies I'm already passing here's。

 here's the interface here's the adjacency and here's the IP address well what if I also。

 just snuck in you know what's four bytes between friends what if I snuck in a label in there。

 two I fundamentally fundamentally haven't added really a whole lot of traffic to the control。

 plane obviously you know it's it's literally individual megs of RAM on a router versus the。

 hundreds of megs of RAM or gigs of RAM required to hold the state for our SPB tunnels so let。

 me back up so what I've done is I've now flooded IP addresses for all the routers IP。

 addresses for all the interfaces and adjacencies and I've flooded a label for everything so。

 now I've flooded a complete link state topology including IP connectivity and label connectivity。

 and what I do differently and here's how SDN becomes involved what I do differently is。

 instead of sending what would be called an explicit route object to the head end to trigger。

 RSVPTE which says I'm going to follow this route this link to that router and that link。

 to that router and that link to that router that's the explicit route object that defines。

 that I instead programmed the head end with a label stack and that label stack I've already。

 learned from the network I've allocated every device and voila I can use just by programming。

 the head end label stack a complete path through the network utilizing eukocos multipath using。

 protection restoration and I think this is although not being discussed at the usual SDN。

 places and not being discussed maybe lots and lots within academia yet this is without。

 a doubt perhaps the biggest revolution to happen in routing and routing protocol since MPLS。

 was invented simply because it solves some fundamental architectural problems of eukocos。

 multipath but it preserves fast reroute traffic engineering and it does it all SDN。

 but instead of passing down say a classifier you're passing down a label stack easy peasy。

 and so what I've been working on is of course pardon me how to link this up into RSVP networks。

 how to link this up within LDP based networks or labeled BGP networks and what this allows。

 me to do and the way I'd like folks to think about it and you to think about it when I。

 combine dynamically routing networks with a centralized view of the topology and a full。

 known explicit path of labels through the network programming that head and label stack。

 I sorry this technology fundamentally would be called a soft permanent virtual circuit。

 in ATM or frame terms it's a soft PVC program the head ends and let signaling figure out。

 the path in between and believe it or not so it's interesting that we're going to sign。

 me we have the line with packet that can be packed and that can underneath but just for。

 needs of I mean core ISP and traffic engineering and all of this stuff in the middle we want。

 to go to soft circuit well let's face it what we should have remembered that the most popular。

 feature of those of those technologies was in fact soft PVCs and we never invented it。

 for IPMPLS it was a huge gaping hole in my opinion instead we jumped all the way to switch。

 virtual circuits which was fully full topology awareness of everybody at the head end now filled。

 the other thing I wanted to mention and this is again a philosophic point is that it's a。

 different point about SDN and the requirement for logically centralized control than others。

 make but I think it's just because it hasn't entered the conversation on the internet yet。

 which is that today's IPMPLS networks do load design via head end only views of the topology。

 and so by doing head end load。 I'm not sure I'm not sure I wish doing what quite get what that means。

 Yeah so what that means is what I want to build a path between me and you and I want to and。

 I want to understand where can I how can I fit 10 gig circuit or a 10 gig tunnel between。

 me and you I have no idea about the load on the rest of the network I have no idea of。

 the load that any other entry point into the network would be putting on to the network。

 all I know is what I see and all I see is a set of the topology I don't know I don't。

 know the utilization I only know the reserved bandwidth what if I don't care about the reserve。

 bandwidth what if I actually just want to know where can I place 10 gigs of load on the network。

 you can't do this from a head end based approach and all of MPLS and all of IP is based upon。

 the head end having full information about the network on how to place load。

 So by that the head end you mean the person is initiating the tunnel that's good saying。

 I'm the head of this tunnel and therefore I must not be out of your absolute right full。

 so on the head end of this tunnel I'm the originator of this tunnel and I have to have。

 full knowledge of load on the network the second thing that's a problem with a current。

 IP MPLS networks and why a combination of a centralized view and the distributed routing。

 is critical is that there is zero admission control today available onto the wide area。

 network the only notion of admission control is on load engineering using historical mechanisms。

 and trying to use past history to predict future performance now it doesn't work very。

 well in the stock market and it doesn't work very well on networks because we are subject。

 to complete instantaneous unknown unknowingly caused fluctuations in load on the network。

 yes we can see diurnal patterns but we don't want to engineer only to diurnal patterns but。

 why did we ever leave admission control and loaded mission control out of IP MPLS you know。

 I can't tell you I've been working on this stuff for 20 years why didn't we ever do soft。

 PVCs I can't tell you we just we went all all the way to switch you know to switch virtual。

 circuits and left a couple of the most fundamental building blocks of network engineering and network。

 planning not even on the table but on the issue you go back to you go back to the original。

 you know the design of the internet protocol you know David Clark's paper he talks about。

 here are the design considerations and goals and certainly resource accounting is one of。

 them but it's low down on the list and so it kind of didn't end up being taken care。

 of very much but really nice a couple weeks ago he gave a I guess lecture and went sort。

 of and went back and revisited these these principles and his ideas and kind of their。

 charts and hey we never thought about security maybe that's something we should have thought。

 of virtually right I mean I think you know back when it was starting didn't seem like a big。

 deal but now some of those principles which were not you know weren't given a high priority。

 are now becoming more and more important oh yeah and frankly load based engineering is。

 one of them now let's talk just a quick trip down history lane back in the day even before。

 there was NSF net there was ARPANET and a lot of my a lot of my colleagues worked on ARPANET。

 and what they tried to do was based upon delay or queuing you know queuing delay across the。

 network they would fiddle with an IGP metric like OSPF and if there was high delay they。

 would give a link worse preference and if there was low delay they would give it very。

 high preference meaning attracting traffic now yeah of course but you know what man that。

 was back in the 80s and to this day from that lesson we have we have not been able to have。

 an adult conversation between consenting adults even about engineering and look it's it's taken。

 I'll be honest the next thing that I want to get to the next topic but the next thing。

 we've been working on of course is adding useful information into these protocols that。

 are flooding this around the network so here's where I'm building this up we just added here's。

 the shocker fill the delay of a link to be passed with the traffic engineering mechanism。

 traffic engineering metrics here is the utilization of a link here is the jitter in fact here's。

 some packet loss information that you know frankly we're dropping packets across this。

 link now without getting into the ARPANET war I said look I'm not even trying to create。

 an SPF out of this I'm not even trying to run a Dijkstra and reroute your traffic instead。

 if you could use this really modern computer science idea of pushing this data out of the。

 network up to a centralized controller instead of that goddamn protocol SNMP where I need。

 to go pull every device to get the load and then somehow through some serious machinations。

 match that up with a topology to understand what the load engine the load looks like on。

 my network hey man I'm pushing traffic out I'm pushing this data out in real time I'm。

 pushing this data out and I see the real time state of the topology and the utilization。

 and the delay and the packet loss I now can take that centralized controller and do some。

 really cool shit and what I can do is place traffic on the network overcoming best path。

 routing or shortest path routing and I can fully utilize all the bandwidth that I have。

 deployed and I can make new protection restoration decisions but what becomes really interesting。

 is if I know when I want to place load on the network I can program that load to be placed。

 on the network basic stuff back up my data centers load my content caches here comes。

 an elephant of traffic that I want to send down my network man I just can't do this dialing。

 all the way back I just can't do this with a head end of view of load engineering onto。

 a network I can't do this via pulling interfaces to 10，000 or more devices and trying to you。

 know create some crazy matrix in the sky that'll never be real time instead we'll use these。

 modern computer science concepts and I'm tongue is a my cheek of push the information out。

 of the network that you want to have it in a logically centralized place and in particular。

 start removing state because once I have that centralized view and I'm not doing head end。

 traffic engineering or load engineering I don't need RSVP I don't need to do I don't。

 need these protocols I can do them in a much much more efficient way and so this these。

 fundamental concepts are really at the forefront of routing protocols routing technology。

 in the wind。 This was as always the fire hose of fantastically cool information David I。

 can't thank you enough but I think I've taken enough of your time you got to go save you've。

 got to go save the internet so I got to go do something that's for sure but all right。

 hey you know if if you've got students out there that or other folks that want to get。

 involved in this type work we're doing it all in the open it's all in standards bodies it's。

 all you know we're doing quite a bit open source and and a lot of it is available again。

 I'd like to move the conversation about SDN and orchestration away from say just the。

 data center stuff and what you can do with some of these other projects but routing a。

 stool cool man。 Well David， well have a great night and thank you again so much。 Hey Dr。 Intel。

 Well。 (sighs)。