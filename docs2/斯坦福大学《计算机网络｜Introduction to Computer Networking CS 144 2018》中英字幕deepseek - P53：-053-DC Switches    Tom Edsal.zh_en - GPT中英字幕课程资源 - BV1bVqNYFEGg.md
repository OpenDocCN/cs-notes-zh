# 斯坦福大学《计算机网络｜Introduction to Computer Networking CS 144 2018》中英字幕deepseek - P53：-053-DC Switches    Tom Edsal.zh_en - GPT中英字幕课程资源 - BV1bVqNYFEGg

So I'm here today with Tom Edtzel， who I've known for a number of years。

 Tom has been involved in the design of switches and routers for a long time now he was a masters student at Stanford and after that has worked through a number of companies。

 most notably at Cisco where he's arguably responsible for the design and deployment of more Ethernet switches and routers than anybody else on the planet。

 so he is extremely well qualified to talk to us today about the design of switches and routers Hi Tom。

谢你。So the first question I had for you Tom is so in CS144 we learn about Ethernet switches and IP routers and their basic functionality Can you tell us a little bit about the history of routers and ethernet switches and when they were first built and sold and were they based on CPUs or specialized hardware？

Okay， so I think the first。Either net switch or what maybe not the first。

 but certainly the first very， very successful one was。

A product that we designed here at Cisco called the Catalyst 5000。And the Cattle 5。

000 initially was a simple layer to switch in a multiport bridge， if you will。

 and it was based upon some custom silicon that we designed。

And there was one AsI or one application specific integrated circuit。

 if you don't know what an ASI is， one piece of custom silicon。

And that was repeated for every port in the system， and we had a line card that was 12 ports。

 so it had 12 of these Asics on it。And then there were several of these line cards in a chat seat。

 and all of those devices were connected with a common bus across the back point。

And that was built shortly after we came into Cisco in 19 well， that product came out in 1995。

And we were immediately trying to figure out how to add layer 3 capability。

 how to add routing to that。Cisco， meanwhile， had a router and we were a part of Cisco to say the main part of Cisco had a router。

 but it was based upon a microprocessor who's a MIPS processor all done in software。

And we began to investigate what it would take to do routing in hardware and the initial response was that it couldn't be done。

And then talking to people is like， yeah， but it's way too complicated and would take too long to explain and we couldn't quite understand what the problem was and we kept on asking and asking and asking。

And eventually we really came to a conclusion that it could be done and it was just people hadn't thought about doing any hardware work。

The initial product， what it did was it allowed。The first packet of a flow to be bridged to a router blade in the system or router on a line car in hardware。

That router was running in software on this MIPS processor。

 it would route the packet as it always has。But when that initial packet was sent to this software router。

 we learned in hardware。Or attached in hardware， the flow information。

About that packet and then when it returned from the software router。

 we compared the return flow with the one that went to the software router and we could see what was different about the packets and the thing that was different of course was it was a new layer2 header so then we would remember that layer2 header and then all subsequent packets we would just do the rewrite to layer2 header that we had learned from the software So the hardware and software were actually running almost completely independently and the hardware was essentially caching the layer3 rounds and that's how。

So is caching still used today？As far as you know。Yes。

It's used in depends on the product that in general， we think about a fast path and a slow path。

And you can think of as a fast path as a cache， sometimes that cache may be done in hardware。

 sometimes it may be done in software quite often the first packet will go to the slope path or alternative。

A packet that has a set of options would go to this slow path and sort of the normal packet。

 it could go through a fast path。嗯。But the technique of caching comes and goes over the years。

And it sort of depends off on the set of problems we're trying to solve and the constraints that we're solving those under I see。

 so in class we learn about the sort of the basic forwarding so you know learning for layer two addresses and then forwarding or broadcasting if you don't know the address and then for layer three。

Checking the version number， decrementing the TTL， updating the checksum and forwarding to the correct egress。

Presumably ethernet switches and routers have more features and functions than that and they do other things what are the main。

You know， what would be the sort of the main ticket items that really？

Make that box more complex or differentiate one box from another。

So the list of things that they do is' a daunting list。That basic function that you just mentioned。

Is essentially what we did in that very first hardware ro。That we were caching the information。

TheOther things that we do there's a lot of work done around security features。

Sometimes it's just simple things like checking to be sure that you don't have zero offset fragments。

 just simple security checks in addition to checking the version number。You， of course。

 when you decrement a TTL， you have to make sure that you redirect the packet to the local CPU if the TTL goes to a zero。

 you need to。Provide all sorts of protections of the internal CPU。

 you don't want to be susceptible to denial service attacks。

 and so there's all sorts of filtering and pasting that occurs on the control plane packets that go the local CPU。

There's you know。Monthlycast is a complete nightmare to implement and has 100 different features to make it work right。

 it's the most difficult thing that we do。There are a number of monitoring functions that have to occur in these switches。

Probably the most basic and arguably the most useful is something that we call a switch port analyzer where we can mirror all of the traffic going to a particular port on some other port or all the traffic coming in from a port to another port where it would be sent to some sort of analyzer。

And then， of course you want to have multiple of these analyzers running simultaneously and then you want to have an analyzer on a remote switch that can monitor the traffic on the local switch and so then you have to figure out how to tunnel that information across the network。

You know。Quality of service， active queue management that the list goes on and on with these。

These sources Yeah so they're really complex piece and I guess they used in all sorts of different places as well in the home。

 the enterprise， wide area networks， data centers， access networks， edge。

 are they substantially different the boxes， the systems and the way that they're built substantially different for those different contexts？

Yes， they are if you。Look at the router in your home。

 the feature set isn't particularly sophisticated the bandwidth are。Low。

 extremely low of course quite often they have wireless built into them and so you can those are usually built use things some sort merchant silicon and running an operating system they perhaps based upon Linux。

The bigger boxes they come in in either fixed form factors。

 meaning that the number of ports is fixed， you can't change out line cards。

 and then there's the big chassis modular chassis where you have multiple line cards and multiple。

Different kinds of thiner faces that can go in on each one of those line cards。嗯。And。

The architecture is internally for the small switches。

 it would typically be a switch on a chip on the bigger systems， of course that doesn't。

Because there's more parts and you can fit on a single chip or the entire system is spread across multiple line cards and sometimes even multiple chassis and multiple racks of chassis。

And those systems tend to。be based upon crossbar or some sort of centralized relatively simple high performance switching element that switches the traffic between the line cards or between the port devices。

 the port devices themselves or line cards。Our generally the silicon use there looks a lot wiped is the single switch on a chip in that one device may support 48 ports of 10 gigabit ethernet or 48 portts of 40 gigabit ethernet and that the emphasis in the data center will be on bandwidth and low cost。

 the emphasis on the campus that will be。Not as much on bandwidth。

 but it certainly be based upon cost and a number of access features around authentication。

And think theification of the endpoints in the w it's going to be a lot of emphasis around bandwidth and buffering and different kinds of interfaces as well as quality of service becomes an important factor。

 so yeah they're all different different flavor。So over the years as these switches and routers have evolved and developed。

 what have been the main advances in technology or architecture that have allowed them to scale？

Have they been primarily coming from the underlying technology like Moore's Law。

 have there been specific technologies that have helped networking switches and routers or specific architectures。

 what's allowed them to keep up with the performance demands？Well， yeah， you know。

 if we followed Moore's law strictly， probably the fastest link in the world would be 10 gigabits and of course know we're switching orders of magnitude faster than that today。

 so networks have had to go through and network boxes have had to go through architectural changes to overcome the limitations of Moore's Law。

 so absolutely we take advantage of Moore's law as much as we can。

 but if I look at some of the switches that I've been involved in designing and bear in mind that these switches。

Account for。60 to 70% of the entire switching market， so these are significant platforms。

The original catalysttalyt 5000 product line was based upon a bus， it was a common shared bus。

 the entire bandwidth of that switch was one gigabit per second。

 and it was an aggregvation of 10 megait links with some hundred megait links involved。

 but that bus quickly ran out of speed， it was the performance of the bus was based upon how fast you could signal on a single wire and how many of those wires you could put in parallel and that was the limit of the entire chassis。

The next generation of that platform， the cattle is 6000， which is still a。

 I think is still maybe a billion dollar product for Cisco， it was delivered in 1998， I believe。

 in 9899。It moved to a crossbar architecture and the crossbar architecture allowed us to have much faster signaling on each wire and to have signaling between。

For it's independent of one another， so it wasn't the bus based architecture。However。

 that was not an arbitrrated fabric， I know Nick you've done a lot of work on arbitration and the importance of arbitration but。

We actually most networks in the world in the 2010 actually did not have arbitration in that。

It was basically send that packet into the crossbar and hope for the best luck that it's delivered to the other end with no problems。

Much less expensive and much less complicated。In the 2010 timeframe， maybe 2008 timeframe。

 we were really starting to feel the pressure on that crossbar and we added arbitration to it to improve the performance of that cross bar。

And also allowed packets to be sprayed across the crossbar to get better performance such so that we had to do packet reoring on the on the egress side to guarantee packet order so those are some of the architectural changes。

 we've moved from external memories to onship memories use of an embedded DRAM was popular for a while now we're moving more back to embedded staticgram that's just following the technologies that are available to us from the silicon perspective。

But generally packaging on packaging on custom Asics has not advanced nearly as much as the silicon itself。

And so， it's。know， cheaperea to build a bigger die than to have multiple smaller devices that are connected。

Great thank you so in class we had one speaker that was talking about SDN software defined networking and basic idea is that opening up more programmatic control to the switching sort of forwarding plane from either from the customer。

 the owner operator or the network or at least software that's under their control so if this change or as this change happens will switches need to change how will they change do you think？

嗯。You know， that's that's a。A big point of some debate。

 I ultimately don't think that the underlying hardware is going to change。

In ways that a lot of people think it might change。One part of what we hear about this SDN is。呃。

Around。Open flow and open flow would indicate that maybe there should be some architectural changes to the underlying silicon and I'm not convinced that that's going to be what happens I think that the underlying silicon and the fields that it uses and how it's structured actually works quite well for us and whether that's being controlled through a centralized controller or not I think is。

It is completely orthogonal to whether you use open Fver or don't use openflow。However。

 there is another thing that's happening， which is I would care characterize worse than SDN。

As a virtualization of the network and that virtualization is done through overlay technologies。

A lot of different overlay technologies。BXLN is one， in BJ is another， STT is one， Lsp is one。

Fabric path， tri， there's a proliferation of these technologies。

 I do believe that the industry will settle on a small number of them。I have my bestts。

We won't go into exactly what I'm betting on right now。嗯。This overlay technology， I think。

 really does provide a fundamental。Value in the network and。A switch built。

Four years ago probably can't do it or can't do it at scale or can't do it with performance。

Performance and。Performance and scale， so。I think new hardware will。

Enable these overlay technologies and we'll continue to improve on what you can do with that open。

Great， thank you want to call it one last question so if students want to learn more about design of switches and routers I mean is there are there still lots of job opportunities。

 is it still a growing and expanding field， we hear all sorts of talk of you know a hardware side of switch and routers you know being becoming sort of a smaller field and you know we see everybody going off to work for Google and Facebook like is it still still an exciting and growing field to be working in？

😊，呃You know。It's an interesting question。 I've been doing this。Since 1985。

 so it's been quite a long time。And there have been periods of great excitement。First came up with。

you know， switchwitching technologies and the industry was happening and the internet was starting to become a good deal and networks came into their own that was a very exciting period of time and then I would say that there was a period where there wasn't a lot happening that it was yes。

 we're going to build a faster switch we're going to add a couple of knobs here and there。

And that was sort of the 2000 to 2010 time period。I think we are experiencing a bit of a revolution now。

 A lot of it actually has。I think that the catalyst for it has been some of the work that you have done with the open flow and this whole idea of SDN networks and oh let's do。

Some virtualization and it's not that that technology you know， came from one source necessarily。

 but was sort of。Being thought about baking in a lot of the labs。 And now it's really。You know。

 burstt onto the scene and。Its really。Has been intellectually challenging for me and very interesting doing。

You know，Eternet switch design。Again， you know when。

That technology will mature and will slow down and presumably something else will come along after that。

You is it a growing industry， You know， there are fewer and fewer。

Companies developing their own hardware。There is， Cisco of course does it。

 you know Juniper develop some of their own hardware， it's very difficult for a startup。

To get the funding to develop new hardware so they tend to use merchant silicon and so if you are looking to design switch hardware。

I think there are fewer opportunities in that space。However。

 I do think there are some pretty interesting things to do in that area。In my own case。

 I was lucky enough to be in a start and currently am in a startup that does do hardware development of switches。

You know， I've got a list kind of so long of。things that I want to do and I can't do all of them。

 and I'm sure other people have a list of ideas。Pretty cool things that can be done in those switches in the heart。

So it's not that。You know all of the great ideas have been thought of。Its's not that bad。

 but you know it's not as it was in the late9。And if you have some internship opportunities come out。

 send me some details and I'll forward them to the class。I absolutely would love to hire interns。

I would bring on many interns。Okay wonderful let's let's chat about that so thanks so much Tom really appreciate it。

 this is really interesting provided the kind of insight we that we can't get in the classroom or from textbooks normally so it's extremely useful thank you。

😊，Okay， thank you。