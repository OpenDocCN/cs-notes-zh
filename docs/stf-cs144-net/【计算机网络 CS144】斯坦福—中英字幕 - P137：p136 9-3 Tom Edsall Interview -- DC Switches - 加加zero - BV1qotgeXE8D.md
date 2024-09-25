# 【计算机网络 CS144】斯坦福—中英字幕 - P137：p136 9-3 Tom Edsall Interview -- DC Switches - 加加zero - BV1qotgeXE8D

 So I'm here today with Tom Etzel， who I've known for a number of years。

 Tom has been involved in the design of switches and routers for a long time now。

 He was a master student at Stanford and after that has worked through a number of companies。

 most notably at Cisco， where he's arguably responsible for the design and deployment of more Ethernet switches。

 and routers than anybody else on the planet。 So he is extremely well qualified to talk to us today about the design of switches and routers。

 Hi， Tom。 So the first question I had for you， Tom， is。

 so in CS144 we learn about Ethernet switches and IP routers， and their basic functionality。

 Can you tell us a little bit about the history of routers and Ethernet switches。

 and when they were first built and sold and were they based on CPUs or specialized hardware？ Okay。

 So I think the first Ethernet switch or it wasn't maybe not the first， but certainly the first very。

 very successful one， was a product that we designed here in Cisco called the Catalyst 5000。

 And the Catalyst 5000 initially was a simple layer two switch， you know， a multi-port bridge。

 if you will。 And it was based upon some custom silicon that we designed。

 And there was one ASIC or one application specific integrated circuit。

 if you don't know what an ASIC is， one piece of custom silica。

 And that was repeated for every report in the system。 And we had a line card that was 12 ports。

 so we had 12 of these ASICs on it。 And then there were several of these line cards in a chassis。

 And all of those devices were connected with a common bus across the back point。

 And that was built shortly after we came into Cisco in 1995。

 And we were immediately trying to figure out how to add layer three capability。

 how to add routing to that。 Cisco meanwhile had a router and we were a part of Cisco。

 say the main part of Cisco had a router， but it was based on a microprocessor。

 It was a MIPS processor all done in software。 And we began to investigate what it would take to do routing in hardware。

 And the initial response was that it couldn't be done。 And then talking to people， "Yeah。

 but it's way too complicated。"， And it would take too long to explain。

 And we couldn't quite understand what the problem was。 We kept on asking and asking and asking。

 And eventually we really came to a conclusion that it could be done。

 And it was just people hadn't thought about doing it in hardware。 And it was a commercial product。

 It allowed the first packet of a flow to be bridged to a router blade in the system or router on a line card in hardware。

 That router was running in software on this MIPS processor。

 It would route the packet as it always has。 And that initial packet was sent to the software router。

 And then when it returned from the software router。

 we compared the return flow with the one that went to the software router。

 And we could see what was different about the packets。 And the thing that was different， of course。

 was it was a new layer 2-ketter。 So then we would remember that layer 2-ketter。

 And then all subsequent packets， we would just do the rewrite layer 2-ketter that we had learned from the software。

 So the hardware and software were actually running almost completely independently。

 And the hardware was essentially cashing the layer 3-grams。 So did caching still use today？

 Or is it not？ Yes。 It's used in -- it depends on the products。 In general。

 we think about a fast path and a slow path。 And you can think of as a fast path as a cache。

 Sometimes that cache may be done in hardware， sometimes it may be done in software。 Quite often。

 the first packet will go to the slow path or alternatively a packet that has a set of options。

 We go to this slow path and sort of a normal packet can go through a fast path。

 But the technique of caching comes and goes over the years。

 And it sort of depends on the set of problems we're trying to solve and the constraints that we're solving those on。

 So in class， we learn about the basic forwarding。 So learning for layer 2 addresses and then forwarding or broadcasting if you don't know the address。

 And then for layer 3， checking the version number。

 and then the data and then we learn about the data and what we're doing。

 So what we're doing is we're doing a lot of different things in the case of the data and the data and the data。

 And then we're doing a lot of different things in the case of the data。

 And we're doing a lot of different things in the case of the data。

 The list of things that they do is a daunting list。

 That basic function that you just mentioned is essentially what we did in that very first hardware wrapper that we were caching the information。

 The other things that we do is a lot of work done around security features。

 Sometimes it's just simple things like checking to be sure that you don't have zero offset fragments。

 Just simple security checks in addition to checking the version number。 Of course。

 when you decrement a TTL， you have to make sure that you redirect the packet to the local CPU。

 If the TTL goes to a zero， you need to provide all sorts of protections of the internal CPU。

 You don't want to be susceptible to denial of service attacks。

 And so there's all sorts of filtering and pasting that occurs on the control plane packets that go to the local CPU。

 There's， you know， method cast is a complete nightmare to implement and has 100 different features to make it work right。

 It's the most difficult thing that we do。 There are a number of monitoring functions that have to occur in these switches。

 Probably the most basic and arguably the most useful is something we call a switch port analyzer。

 where we can mirror all of the traffic going to a particular port on some other port。

 or all the traffic coming in from a port to another port where we send to some sort of analyzer。

 And then of course you want to have multiple of these analyzers running simultaneously。

 And then you want to have an analyzer on a remote switch that can monitor the traffic on the local switch。

 And so then you have to figure out how to tunnel that information across the network。 You know。

 quality of service， active to management that the list goes on and on with these these routers sources of the router。

 Yeah， so they're really complex piece and they， I guess they used in all sorts of different places as well in the in the home。

 the enterprise， wide area networks， data centers， access networks， edge。

 Are they substantially different the boxes， the systems and the way that they're built substantially different for those different different contexts？

 Yes， they are。 If you look at the router in your home。

 the feature set isn't particularly sophisticated。 The bandwidths are low， extremely low。 Of course。

 you know， quite often they have wireless built into them。 And so you can。

 those are usually built using some sort of merchant silicon and running an operating system there。

 perhaps based on Linux。 The bigger boxes， they come in in either fixed form factors。

 meaning that the number of ports is fixed。 You can't change out line cards。

 And then there's the big chassis， modular chassis where you have multiple line cards and multiple different kinds of interfaces that can go in on each one of those line cards。

 And the architecture is internally for the small switches。 It's typically a switch on a chip。

 On the bigger systems， of course， that doesn't work。

 So there's more ports than you can fit on a single chip or the entire system is spread across multiple line cards and sometimes even multiple chassis and multiple racks of chassis。

 And those systems tend to be based upon crossbars or some sort of centralized， relatively simple。

 high performance switching element that switches the traffic between the line cards or between the port devices。

 The port devices themselves or line cards are generally。

 the self can use their looks a lot like the single switch on a chip in that one device may support 48 ports of 10 gigabit ethernet or 48 ports of 40 gigabit ethernet。

 And then the emphasis in the data center will be on bandwidth and low cost。

 The emphasis on the campus will be not as much on bandwidth。

 but it will certainly be based upon cost and a number of access features around authentication。

 And the implication of the endpoints。 In the land。

 it's going to be a lot of emphasis around bandwidth and buffering and different kinds of interfaces as well as quality service becomes important factor。

 So yeah， they're all different different flavors。 The years of these switches and routers have evolved and developed would have been the main advances in technology or architecture that have allowed them to scale。

 Have they been primarily coming from the underlying technology like Moore's Law？

 Have they been specific technologies that have helped networking switches and routers or specific architectures？

 What's allowed them to keep up with the performance demands？ Well， yeah。

 if we follow Moore's Law strictly， probably the fastest link in the world would be 10 gigabits。

 And of course， we're switching orders of magnitude faster than that today。

 So networks have had to go through and network boxes have had to go through architectural changes to overcome the limitations of Moore's Law。

 So absolutely we take advantage of Moore's Law as much as we can。

 But if I look at some of the switches that I've been involved in designing。

 and bear in mind that these switches account for 60 to 70% of the entire switching market。

 So these are significant platforms。 The original countless 5。

000 in product line was based upon a bus。 It was a common shared bus。

 The entire bandwidth of that switch was one gigabit per second。

 And it was an aggregation of 10 megabit links with some hundred megabit links involved。

 But that bus quickly ran out of speed。 The performance of the bus was based upon how fast you could signal on a single wire and how many of those wires you could put in parallel。

 And that was the limit of the entire chassis。 The index generation of that platform， the title of 6。

000， which is still， I think is still maybe a billion dollar product for Cisco。

 It was delivered in 1998， I believe， in '98， '99。 It moved to a crossbar architecture。

 And the crossbar architecture allowed us to have much faster signaling on each wire and to have signaling between ports independent of one another。

 So it wasn't the bus base architecture。 However， that was not an arbitrated fabric。 I know Nick。

 you've done a lot of work on arbitration and the importance of arbitration。 But we actually。

 you know， most networks in the world in the 2000 to 2010 actually did not have arbitration in that。

 It was basically， you send it packets into the crossbar and hope for the best luck that it's delivered to the other end of no problems。

 Much less expensive and much less complicated。 In the 2010 timeframe， maybe 2008 timeframe。

 we really started to feel the pressure on that crossbar and we added arbitration to it to improve the performance of that crossbar。

 And also allowed packets to be sprayed across the crossbars to get better performance。

 So we had to do packet reordering on the egress side to guarantee packet order。

 So those are some of the architectural changes。 We've moved from external memories to on ship memories。

 You said that a DRAM was popular for a while。 Now we're moving more back to embedded static RAM。

 That's just following the technologies that are available to us from the silicon perspective。

 But generally packaging on silicon， packaging on custom。

 A6 has not advanced nearly as much as the silicon itself。

 And so it's cheaper to build a bigger die than to have multiple smaller devices that are connected。

 Great， thank you。 So in class， we had one speaker that was talking about SDN software defined networking。

 And basic idea is that opening up more programmatic control to the switching。

 sort of forwarding plane from either from the customer， the owner operator。

 the network or at least software。 That's under that control。

 So if this change or as this change happens， we'll switch his need to change。

 How will they change do you think？ You know， that's a big point of some debate。

 I ultimately don't think that the underlying hardware is going to change in ways that a lot of people think it might change。

 One part of what we hear about this SDN is around open flow。

 And open flow would indicate that maybe there should be some architectural changes to the underlying silicon。

 And I'm not convinced that that's going to be what happens。

 I think that the underlying silicon and the fields that it uses and how it's structured actually works quite well for us。

 And whether that's being controlled through a centralized controller or not。

 I think is completely orthogonal to whether you use open flow or don't use open stuff。 However。

 there is a another thing that's happening which is I would care for a place more than SDN as a virtualization of the network。

 And that virtualization is done through overlay technologies。

 There are a lot of different overlay technologies。 VXLAN is one， NVJRA is another， STT is one。

 LISP is one， fabric path， trill。 There's a proliferation of these technologies。

 I think the industry will settle on a small number of them。 I have my bets。

 but we won't go into exactly what I'm betting on right now。

 But this overlay technology I think really does provide a fundamental value in the network。

 And a switch built four years ago probably can't do it or can't do it at scale or can't do it with performance and performance and scale。

 So I think new hardware will enable these overlay technologies and will continue to improve on what you can do with that overlay technology。

 Great， thank you。 I want to call it SDN。 Sure。 One last question。

 So if students want to learn more about the design of switches and routers， I mean。

 are there still lots of job opportunities？ Is it still a growing and expanding field？

 We hear all sorts of talk of the hardware side of switching routers becoming a smaller field。

 And we see everybody going off to work for Google and Facebook。

 Is it still an exciting and growing field to be working in？ It's an interesting question。

 I've been doing this since 1985。 So it's been quite a long time。

 And there have been periods of great excitement。 And we first came up with switching technologies and the industry was happening and the internet was starting to become a good deal and networks came into their own。

 That was a very exciting period of time。 And then I would say that there was a period where there wasn't a lot happening。

 That it was， yes， we're going to build a faster switch。

 We're going to have a couple of knobs here and there。

 And that was sort of the 2000 to 2010 time period。

 I think we are experiencing a bit of a revolution now。 A lot of it actually has， I think。

 the catalyst for it has been some of the work that you have done。

 And with the open flow and this whole idea of SDN networks and let's do some virtualization。

 And it's not that that technology came from one source necessarily。

 but was sort of being thought about baking in a lot of the labs。

 And now it's really burst onto the sea。 And it has been intellectually challenging for me and very interesting doing the internet switch design。

 Again， and that technology will mature and will slow down and presumably something else will come along after that。

 And so， in the growing industry， there are fewer and fewer companies developing their own hardware。

 There is， Cisco， of course， does it。 Juniper developed some of their own hardware。

 It's very difficult for a startup to get the funding to develop new hardware so they tend to use merchant silken。

 And so if you are looking to design switch hardware。

 I think there are fewer opportunities in that space。 However。

 I do think there are some pretty interesting things to do in that area。 And in my own case。

 I was lucky enough to be in a startup and currently am in a startup that does do hardware development of switches。

 And I've got a list， kind of， so long of things that I want to do and I can't do all of them。

 And I'm sure other people have a list of ideas and pretty cool things that can be done in those switches in the hardware。

 So it's not that all of the great ideas have been thought of。 It's not that bad。

 but it's not as it was in the late 90s。 And if you have some internship opportunities come out。

 send me some details and I'll forward them to the class。 I absolutely would love to hire interns。

 I would bring on many interns。 Okay， wonderful。 Let's chat about that。 So thanks so much Tom。

 really appreciate it。 This is really interesting， provided the kind of insight that we can't get in the classroom or from textbooks normally。

 So it's extremely useful。 Thank you。 Okay， thank you。 I'd love to see you soon。

