# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P21：-21-Lecture 23 - Networking.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Questions for me before we start？I have a question for you guys， where is everybody？

Seems like half the people here。嗯。Okay， I'll have to make sure there's questions from this lecture on interim two。

いいいいい。嗯。Okay， so yeah， so we are here 1120 and we're going to talk about networking today this week we're getting Project many updates and I've been at all of them I will be at the ones this afternoon。

You you know you。I really encourage you to come hear what your colleagues have to say if you can afford the time。

Because。These projects are just great， I mean， they're all kind of just only three weeks in。

It's amazing what's happening。And it's really fun to see it。

If you see what your colleagues are doing。I think it'll undoubtedly give you some ideas。

 so please feel free to come by if you do come by the lab。

 the lab is sort of has an awkward layout where there's。The presentation in the front。

 you have to walk right across the presentation to come in， don't worry。

 this is informal just walking。Nobody's going to mind。And。And this afternoon's lab is from four Phil。

It should be over by 630， I think。Schedule it all the way。7even。So。Okay。

 this is also my last lecture on Tuesday， I really strongly recommend coming for this。

Extremely interesting， very visionary， long term work。

So Jose Carmina is going to talk about brain machine interfacing。

 so the future of embedded systems is that you won't need these keyboards and screens and all that it'll all just get piped sprayed in and out of your brain。

嗯。So quite some visionary work going on and with lots of profound implications， of course about。

For example， security。What would a denial of service attack to the brain？Do。

A little scary proposition。And then then of course we have the Thanksgiving holiday and then Alberto will lead a midterm review on Tuesday and then the midterm will be second midterm will be held in class。

The second midterm will be cumulative， so it covers the entire semester。

 but the emphasis will be on the latter half。But， there's a sort of assumption of a backdrop of information from the first half。

So basically， the emphasis is from LTL on。Okay。IsThat set of topics。And。Oh， and logistically。

 since you already prepared one eight and a half by 11 inch sheet of paper。

 you can bring that same one plus one more。Okay， so you can bring two eight and a half by 11 inch sheets of paper。

To the midterm， but otherwise it's closed book。Any questions about that？



![](img/1e869af21e2f526599754dc45980069b_1.png)

Yes。There time since。

![](img/1e869af21e2f526599754dc45980069b_3.png)

Right。Yeah， or if you just go to the assignments page， there's a link to it。From there。Okay。

 on the projects， in fact， in some ways what I'm going to talk about today is really more focused on the projects than on midterm material。

And hopefully it'll give you some broader perspective on what's going on in the projects。

 I think almost all of the projects involve networking in one form or another。

With very few exceptions。So you know this comes from the unwritten networking chapter of Leon Seia。

But briefly， I wanted to talk about one aspect of the projects because it came up in several of the project presentations。

And I think it's really worth emphasizing proper professionalism requires that you give attribution to your sources。

It's not just academics。it's more professional to know where the stuff you're building off of came from。

😔，Okay。And so if you say， oh， I've found an LTE stack on the net。

And I'm using that for this particular platform。It seems to work。That's not proper attribution。Okay。

 proper attribution might look something like this。

 you know I got a Bluetooth stack reader for my credit card reader that was written by Sal creditit card thief。

And is available at the following website in Russia， httpsca。4u。 and it's free software。

 you should know the copyright of the software， you know just knowing it's free software。

That doesn't really tell you anything。So this particular piece of software by Sarah Kdear Fief。

It as All rights reserve， but he gar grants you permission to use， reproduce。

 and distribute this software provided to all users with the software。

Upload valid credit card numbers to this location。And he makes it very convenient because the Bluetooth stack will actually just do it for him。

know your sources。Okay。I mean， this is the kind of thing that could happen to you if you don't know your sources。

 right there's a lot of software out there。😔，And some of it's better than others。

Some of it's more trustworthy than others。嗯。You really。

 you need to know your sources and you need to bend over backwards to cite your sources。😔，嗯。

It's okay to build off of other people's stuff。And in this class we go much further than a lot of classes kind of say。

 oh， please don't do that， don't Google for this particular solution to this problem set。

And the reason for that， of course， is very pragmatic that it's very difficult to come up with good exercises。

 good programming exercises for a programming class。

And if you just find a illusion on the net and copy it， you haven't learned it。But in this past。

 we actually encourage you to build off with other people's stuff because it's a very rapidly changing field and we believe that there's no way that you're going to download a complete solution。

 and even if you did， you would find it very unsatisfying yourself。

 you're going to download stuff and then extend it。And build off it。But credit your sources。ok。

All right， so today is there's an alphabet soup， so I have a handout that has the alphabet soup and there'll be a quiz at the end。

 so I'll expect you to identify。All of these items in the alphabet soup。property。That way。

The diffusion process。保。You don't get one。So if you really want to impress someone at a party。

 after this lecture， you should be able to form a sentence like let me see if I can form an interesting one。

嗯。My AVB gateway extends 1588 into my WP using COAP like techniques combined with PARP。啊，号sorry。

And that sense。Will really impress people at parties。The。Okay。So。

One of the great things about networking is it's a language in and of itself。

And if you hear networking people having a conversation。

 it's really hard to tell what language they're speaking sometimes。嗯。So。

There's a lot going on in this field。 And so what I'm going to try to do is give you sort of a。

High level view that tries to relate to these technologies。knowMany of them， you know。

 you're actually kind of familiar with them， but maybe you haven't thought quite as much about how they relate to one another。

You know about Bluetooth， you know about Wifi， you know about Zigby。Why are there three？

And when would you use one over another？And those kinds of questions are what I'm hoping to kind of get at today。

Okay， so we're going to start with wired networks。And。

I'm going to build off of what Alberto was talking about on Tuesday a little bit。

 so he was focused on TTP time triggered protocols and on reasonably recent extension of these time triggered protocols to use Ethernet under the hood。

T Ethernet。TTP actually reflects a fairly long standing。Tradition in embedded systems。

 which is to use。Networking technologies that are by design more deterministic。

Than the general purpose networks that most of us are familiar with。So。Ethernet is。

Was originally designed very much as a best effort kind of network。At the time that it was designed。

 wiring was expensive， actually wiring is still expensive， in fact。

 in networking it's often the most expensive part。Here's a wiring。嗯。But as a consequence。

 there's a goal in these networks to share the wires， you don't want a lot of wires going around。

But then there's contention for resources， so many of the more specialized networks。

That are used in industry are designed to give you more deterministic behavior when there's contention for resources。

So the Can bus， for example， is a originally rather old technology。

 although it's matured and grown up in time， so there's reasonably modern versions of this。

When it was first introduced in 1983。One of the key ideas of the canvas was that it's a shared bus among them。

 a whole bunch of different machines， and there's an assumption that they could all。

Try to access this bus at the same time and that they could collide with one another。

 but it has an interesting twist。Which is the way the electrical interface works on a canvas。

Is it a device that connects to a can？Can pull down the voltage。On a wire。It never pulls it up。

 it just pulls it down。Okay， so there's a pull up resistor。

 so it's kind of like the open collector technique for GPI opens that we talked about eons ago。

AtThe beginning of the semester。Right。And the idea was that if a device writes something onto the canvas。

 it writes an apeit word。Then it should read it back。From the bus。Immediately。

And if there's a discrepancy between what it wrote and what it reads。

 then it knows that there was a collision。ok。And it。Reacts accordingly。

Okay so what do you think the consequences are of that style of electrical connection？

Is that a good way to do things， a bad way to do things， and why any ideas？Yeah， there's that。

 I mean， what you know， a key question is， what do you do if you detect a collision， right？嗯。

The way that people tend to use can buses is using reservation based schemes。

 so they try to avoid the collisions in the first place。

 use synchronize clocks so that you take turns。Yeah。Yeah， actually。

 so in many ways that's a good observation if two devices try to send the same data on the bus at the same time。

 they will both read it back and it'll be correct。And that was viewed as an optimization。

 that's very convenient because they both correctly successfully communicated what they wanted to communicate。

Right。So。That was viewed as a feature， not a bug。Okay。But there's a very practical。Downside。Yeah。

It actually has， it's pretty powerful。Yeah。嗯。It is pretty power hungryung。

It's also intrinsically pretty slow。ok。In fact， the bus length is limited by this technology。

This technology doesn't take advantage of the fact that signals propagate along wires。

It's treating the wires as completely static， so the idea is that when a voltage。

 when a signal is asserted on the wire， it's asserted simultaneously over the entire length of the wire。

ok。And that means when you pull down the voltage。At the Wi locally。Before you read it back。

 you should wait until you pull down the voltage over the entire length of the wire。

 but actually that takes time， it propagates out and if the wire is really long。

 it can take quite a long time， I a long time。Electrical term。So as a consequence。

 the bit rates that you can get with this technique are pretty low。

Because signals are not propagating along the way。Ethernet doesn't do that right。

 Ethernet you launch an electrical signal and you've stopped asserting the value on the wire。

Probably before it's reached the destination。So the signals could propagate along the wires。

 and as a consequence， you can get much higher。B。But at the expense of less coordination， right。

 so if you put a packet onto an ethernet bus。嗯。You don't know whether it collided with something。😔。

ok。It's actually kind of hard to tell from just looking at your electrical connection。Because。

It may hide you something after you。You're done with it， you've finished sending it。

And it collided at a receiver somewhere remotely。with another guy trying to send a packet from the other end of the wire。

That still hasn't even reached you。So。In eitherthernet networks。

 people overlay acknowledgement schemes， so when you send them。Some packet。哦。

If you don't get an acknowledgement after a certain amount of time， you resend back。

They assume that it somehow failed possibly because of an electrical。

So these are very different style。But the nice thing about the CA bus is that you can know immediately whether you successfully asserted your output on the bus。

And consently， canbues are used in safety critical systems， so they're used in， for example。

 factory Army。In fact， they've been almost universally used in factory automation until very recently。

Where people have started to use Ethernett by leveraging technologies that I'm going to tell you about today。

Okay。So media access control is all about the issue of， you know。

 you've got shared physical resources， how do you mediate access to those？Okay。And。

The technique that's used in Ethernet is CSNA/ca。Carrier sends multiple accesss。

 so what you do is you listen on the ethernet bus。If it's not being used， you can start transmit。

But when you start transmitting， you finish transmitting。

You launch an entire packet into the network。You don't continue listening for collisions。And。You。

Then if you fail to get an acknowledgement after some time。You retrans。Okay。嗯。

That's a very distinct style from the style that Alberto was talking about it on Tuesday。

 which is time division multiple access。Which is where you have predefined turns。

 every device that shares this resource as a turn。And you have to switch。

 you have to transmit only when it's your turn。嗯。One interesting thing about time division。

 multiple access is that it requires。It requires you to know when your turn starts。

Which means that you have to synchronize the box。ok。

And a brute forest technique to synchronized boxes。

Have a master on the network that broadcasts a lot and it tells you where yourre turn。

What's the downside of that？😔，Yes。Right， the clock has to propagate too。And you get skew。

 right if your path length to one device is different。And your path went to another device。

Then those two devices have a differing notion of when the turn starts。And。

That amount of difference has to be built into the headroom in your schema。😔，Okay。

 so you have to put a guard band between turns。To allow for the clock skew。

The guard band is a period of time when the network is effectively not used。

So it waste network resources， so that style of TMA also results in relatively slow。あね。

Relatively low utilization。So these are the kinds of tradeoffs that you get with。Yes。

I think you always。First， listen for an idle channel before you transmit it。

But the problem is that you have no assurance that the channel is actually idle because some other device may have already started transmitting on that channel and you just haven't heard of it。

Because you're physically separated。Transfer。So there's always that risk of collision if you're in fact。

 sharing the wire。These devices， by the way， in Ethernet。

 the way that people usually deal with this is。They don't share the wire。

 so you use a star topology where every device is connected with its own twisted wire pair。switch。

Which。Itself。hass contention for resources right so it gets packets coming in over multiple wires and it has to maybe transmit them out one twisted wire pair。

So the switch will typically have cus in it。Two packets come in at the same time that are going out the same port。

 they'll get cud， but the queue might overflow。 you get too many things queued up。

 you have a bounded amount of memory， you start dropping packets。

AndSo those packets will never get acknowledged， and that's the usual source of loss。😔。

In the wired networks that we have around here， for example。

 which are almost all wired in a star topology。All right， so Alberto talked about this TT Ethernet。

The key idea here is to use Ethernet， but to combine it with clock synchronization。

And so if all the devices that are connected to the same ethernet bus。Share。

Clocks that are tightly synchronized。Then。They can know their turn。You can pre assignsign terms。

And they'll use the network at the appropriate time。They'll avoid collisions on the physical medium。

And interestingly enough， you can also avoid buffer overflow。In the switches。

 using the same kind of technique。You just make sure that。You know。

 through routing algorithms that you're not going to overwhelm the buffers now in Tt Ethernet。

 the way that this is typically done。Is that there's a schedule that actually combines a variety of different access schemes。

So you have time triggered windows in the schedule。That are pre assignedsigned。

 so a particular device is allowed to use the bus at this time。

A different device is allowed to use the bus at this time。 so these are time triggered windows。

 these blue ones。But then you might also have。What are called rate constrained windows？

Which give you kind of a。Degraded quality of service， but only a little bit degraded。

 so in a rate constrained window。Any device can transmit。ok。But it should only transmit。So many bits。

Hard bound on that。And you assigns so that there's。Some significant headroom so that if you。

Need to transmit something unanticipated， if you don't have a reservation for it。

 you can use one of these rate constrained windows and you get some jitter。

Compared to the time triggered。Packets， but the jitter is a lot less than you get if you use instead one of the best effort windows。

So the best effort windows are also scheduled in this schema。

 so you have windows of time when anyone is allowed to transmit in the usual TCPI on eitherther that kind of way。

 you just listen if there' if there's no one transmitting you start transmitting。Okay。

And that's the best effort schemes， and those are not rate constrained。So GG Ethernet。

The way that you set up a network like this is you set up a schedule like this。

 and then you hope that all the devices obeyed the schedule。

Alberto mentioned that you can get what are called babbling idiot failures。

There are devices on the network that don't avabe the schedule。Yeah。Actually。

 I don't think that Tt Ethernet necessarily defines whether。

There's a protocol above this to wait for acknowledgement。That's it work。So， you know。

 one of the key things about networking is that the standards are defined in multiple layers。

The lowest layer is the electrical layer。' what are the voltages that you assert if you're if you're going to talk to the I robot serial port。

 it's a five volt signal and the embedD produces a three volt signal。

 some of you have run into this in your projects already。Okay。

And the electrical property is also telling you， for example， with the canvas。

That you should pull down the voltage， you never pull it up， if you pull it up。

 you're short circuiting， somebody else's pull down。Those are electrical level connections。

 and over above that you have media access control。And above that， you have higher level protocol。

And each of these layers defines a different level of service。

So whether acknowledgeledgments are sent。And whether you retransmit is one of the higher levels。

It's about。The company that developed this TT tech can sells hardware。

That will provide you an ethernet interface that actually guards against babbling idiots。

So the hardware itself will be cognizant of the schedule and will prevent a malfunctioning device。

From getting access to the network at the wrong。Of course。If that device malfunction。

We got a problem。Layers of protection。So their goal is really to be able to make Ethernet usable in safety critical systems。

On aircraft， for example。When。When the airplane manufacturer switched to fly by wire。

The weight of a commercial aircraft decreased by about 30。Because。

It turns out that all those hydraulic controls that are used to connect the stick back to the flaps and the pedals to the rudder and all that are really quite heavy compared to wires。

But it turns out that the wires are also pretty heavy and there's a lot of wires in those planes these days。

Way too many and so they're trying to。Reesign this and reduce the number of wires。Use， for example。

 ethernet buses。Not in a ST topology because a ST topology requires you to run a lot more wires。

But then you really need to take media access control seriously。

 and these are safety critical systems。We need these layers of protection。

 so hardware protection against a babbling idiot failure in some device。Becomes important。All right。

So routing layers， so if you have a bus， you have a physical shared medium。

And the Mac protocol dominates the performance。In star networks。

 the Mac protocol is less important because your failures will tend to be instead at the next level in the queuing that happens in the routers。

So the routing protocols become important in this case。So here's a question point。

Suppose it's a radio。Which of those do you have？Is that a star network or a bus？

It seemsms like a bus， right， because。You know， if you have an omnidirectional antenna。

And you start transmitting a wfi signal and everything within your range is sharing the same。Bandth。

 the same radio space， right， so it has that character of being a bus。But interestingly。

You know the designers of， for example， the cellular network。

Are trying to make it much more starlike。So they do beam forming at the。嗯。At the base station。

So when they connect to a particular device。They can form a beam。By using multiple antennas。

Which decreases interference。Other direction？You concentrate the radio energy to go in a particular direction。

And it starts to look a little more like a star of topology， right。

 because now you can use the same bandwidth。To communicate with another device off in that direction。

So this is being done in Bay stations。One of the interesting questions is can you do that in handsets？

And it's a little difficult， right， because the way you do beam forming is。

You have multiple antennas and you synchronize the radio signal so that there's constructive interference in one direction between the radio signal coming from each antenna。

And destructive interference。In a different direction， right so you have a null in that direction。

 so anything in that direction。We'll see the peaks in the troughs at the same time。

So they cancel each other out。You get no， that's the way you do beam for。

But if you try to do that in a phone， I put two antennas on opposite sides here actually。

If you put them at opposite sides here， that's about right for 2。4 gigahertz。

 I could do beam forming with two antennas at opposite ends of this phone。

But what direction is it going to transmitted？It's going to change as my phone。Moves around。

 so that's not all that useful because the central office is。In a particular direction。

 and you have limited steering ability electrically for these things。So people have talked about。

 well， what would it take instead？To use all the cell phones that are in this room to form a single beam。

If they all coordinated their radio signal， you could form a very precise beam to a central office。

But you need to synchronize the clocks on these things。Extremely high precision。

 sub nanosecond precision。to be able to do it。It's an interesting technical job。If you could do that。

 by the way， you could dramatically reduce the energy consumption of radio signals。

When you form a beam， you're concentrating all the energy in one direction instead of sending it willy nilly in all directions。

And。YouIf you can concentrate all the energy on a receiver that you're targeting。

 then it takes a lot less energy to communicate with that receiver。

 so you could quite dramatically reduce the overall energy consumption of radio communication。

We all our phones cooperated。ピ。For the band。People have developed actually lower level schemes。

' actually they're higher level in the sense that they operate more at the protocol level。

They use mesh networking。OkaySo you can form ad hoc networks between cell phones。

 there's apps you can install on your phone that' will do this。

So if any of you in the room are on this same ad hoc network， you've installed this app。

Then my phone can。Can route a wfi signal to your phone， which can then route it to another phone。

To another， as soon as you get critical mass on this， you can start to get wfi everywhere。

You don't need to be near a w Fi access point anymore to get a wF service。So the phone companies。

 the cell phone companies are pretty nervous。This technology。

 because this could bypass the cellular network。Route everything。WiF access points。

Undermining a lot of their business model。A lot of transitions have。嗯。Issues with routing buffers。

 routing tables to where if you receive a packet that comes in through one port。Atd a router。

What should you do with the packet？You got to send it somewhere， the router doesn't want it。

So where do you send it？You need a routing table to decide where to send it。Priorities。

Two packets come in， they both。Deestin to go out the same port， which one should you send first？

In general and purpose networks， the kind that we use every day here， priorities are not defined。

Things happen very accidentally。But if you can control priorities， you can affect things。

More interesting。So buffering effectss reliability， routing tables have major security issues。

There have been quite a number of interesting attacks。On networks that。Corrupt routing tables。

And they allow devices to masquerade as devices that they're not。We're not actually the dead。

And priorities are about quality of service。So let me zero in on priorities because there's a very interesting development happening in networking today。

Which is the emergence of networks that have genuine control over quality of service。

So one of the ones that has really started to catch on。嗯。Is called AVB for audio video bridging。

And this was renamed in 2012 to TSN time sensitive networking， but like many renames。

TheRename kind of failed。Everyone still calls it ABB。

But the Atrople committee that's responsible for standardizing this is called the TSN Committee。

So okay， two names for the same thing。But this was the name for this kind of tells you a little bit about its origin。

 it was started by media companies。😔，One of the companies pushing this originally was Comcast。

And the problem that they were trying to address was。You know。

 this mass of cables that arises in a lot of contexts in media。

 so this particular picture is from a broadcasting band。For television broadcasting。

Where every camera， every audio， every microphone， every piece of equipment has its own cable connecting it to every other piece of equipment。

And you end up with this real massive wiring。And so ABB was intended to solve this problem。

 but the technique that it uses is ethernet based。It uses clock synchronization。

And it uses standard networking protocols like PCPIP。So as a consequence。

 its applicability goes well beyond。没有。It can be used in any time sensitive network。

 which is why they renamed it。Okay so people are starting to use it， for example。

 in automotive system design to reduce the number of wires in a car to put you all of the devices on a single ethernet bus。

Okay， and get quality of service that enables you to be able to control the latency。

To prevent bumper over。错。So this is kind of what the network network， an AVB network looks like。

 first of all， it can be heterogeneous so it's by design compatible with existing ethernet based TCVID networks。

So you can put an ABB bridge。啊。That connects to a legacy。Internet switch。

This guy over here knows nothing about AVB。So there's no quality of service control between these AVB bridges。

That's just going to be best at。Factets might get lost because buffers overflow in this switch。

It's part of being transported across cities。Ass the network from here to here。

But within an ABB domain。You can prevent buffer overflows and you can control the priorities with which the switches route packed。

So if you have a safety critical connection between two devices。And you give the packets。

flow between those two devices highest priority and if they're genuinely the highest priority in the ABB domain。

 then those packets will never be lost。Never。At least。I mean。Unless there's a hardware fault。

They never get lost because they never get put to the end of a queue。😔，They will always go out。

Theport。Preempting whatever else might be waiting to use the port。And as a consequence。

 you can at least。At least with one connection， completely prevent back losses， moreover。

 more interestingly， you get control over the lakes。

So now you can actually measure the time that it takes for a packet to get from point A to point B。

 and it will pretty much take that amount of time every time you send a packet from。Yeah。

 net neutrality makes this illegal。嗯。I think this is going to happen whether net neutrality happens or not。

 it's just that you won't be able to call this network an internet。

So I think net neutrality is just going to force the creation of a parallel network。

Where quality of service matters。Which is sort of unfortunate in my view。

I think the way that that will be dealt。Now， today。

 this is not so much of an issue because AVB tends to be used only in local area network。

 so it's not being used on the open internet。But the vision is that it would be used on the open internet。

 in fact， one of the goals that companies like Comcast and ATMT that are Internet service providers had before this。

Is they want to provide quality of service， controlled services to the home。Okay， to do things like。

 for example， interactive gaming。Okay， acrosss the network。

So if you want to play games with real time feedback or a more interesting application from my perspective is。

Suppose you're a musician and you want to jam with your buddies。But they're not in the room。

In another city。Like so many of us are， right？It's pretty hard to do that on internet connections today。

But if you can control the latencies。And your only real constraints or speed of light constraints。

 you can do a pretty good job of doing collaborative jamming over a network。

But you need to be able to control quality of service to do that。

Net neutrality makes it illegal to do that on the internet。Sim fact。Sorry。Okay。

Here's an application of AVB that's deployed on a local network in the stadium here at Berkeley。

The stadium has these speakers that are called Cal and the reason that they're called Cal。

 they're actually a product by Meer Sound and the technology that they use was invented here at Berkeley at SinMAT。

 the Center for New Music and audio technology， so SinM developed this technology。

 Myyer Sound commercialized it and in a bow to Berkeley， they named the product Cal。

 for columnar Array Louspeaker。These are what the speakers look like in the context of the stadium and they're scattered around the rim of the stadium and they do collaborative beam forming of the sound。

 one of the things they do is they keep the sound within the stadium so you can have very loud sound in the stadium and it doesn't spill over into the neighborhood。

You can't hear it outside the stadium。And in addition。

 stadium sounds tend to be very dominated by the acoustics of being in a big。you know。

 bowl right you get echoes that can be really weird well with beam forming you can largely prevent these echoes so you get very crystal clear sound at all points in the stadium。

It's really quite dramatic compared to the older technologies。

These loudspeakers are connected by Ethan。to each other， and to the sound sources。

 and they use AVB to propagate the sound signal that's going digitally to the loudspeaker。

And they have synchronized clocks that are synchronized to precisions of a few nanoseconds。

 so if you ask two of these speakers at opposite ends of the stadium what time it is。Okay。

 they will agree to within a couple of nanoseconds。And I want to emphasize， you。

 at the speed of light， this is a nanosecond。Okay， so if you're talking about a physical dimension of the scale of the stadium。

Getting that degree of clock concurrence by just brute forest techniques like broadcasting a clock signal is very difficult because the clock skew will mess you up if you have two wires whose length differs by more than this。

Okay， then those two wires at the endpoints will disagree on the current time of day by nano。

 no matter how careful you are with the electronics。

 if the difference in the length of the wires is this much， they'll differ by eight nanoseds。

 right and so forth。So I'll show you how the clock inchronization works for this scheme。

 but it is not a boot forest clock distribution。スピー今？

And the beam forming relies on the clock synchronization。

 so basically you these speakers have to form signals that will。

Interfer destructively and constructively with the signals coming from the other speakers。Okay。

 so that they position all of the sound energy in the right places in the stadium and prevent the sound energy from being in the wrong places。

So the key enabler behind this is a technology called PTTP， that's one of your acronyms。

Slides here on your handout。It's answer for precision time protocol and 1588 is another one of the ones that is on here。

 this is because this for people in the know。The number 1588 means this。ok。

It's not the balance of your bank account or anything else。It means this technology。

And this technology was first developed actually in 2002。

 it got standardized in a first version through this slow laborious standardization process that is prevalent in the networking world。

 first products started to appear in 2007， this is an advertisement from。

One of the first ethernet Phis， in fact， actually the first ethernet Phi。

 the chip that does the physical interface that supported 1588。They claim here。

 you can't read this in the back of the room， but it says achieve eight nanosecond precision with maximum system flexibility。

So eight and9 a second was abound on a local area network of clock errors across this network at that time。

The technology has gotten a lot better since 2007， it's been progressing very rapidly。

 a fairly extreme example of an application of this technology is in the large Hadron Collider。

Which is a particle accelerator that straddles the border between France and Switzerland。

So it's an underground。Machine， this is about four stories high。

 and the circumference is 27 kilometers。So the diameter is about 10 kilometers。Okay。

And this white rabbit project is able to synchronize clocks 10 kilometers apart。

To precisions of tens of picoseconds。ok。And so you can coordinate machinery at opposite ends of this accelerator。

In ways that speed of light constraints would seem to imply or impossible。Okay。

But they're not impossible in that。This technology was also used you might remember。

I think it was two years ago there was a big hull of the Louo over the summer because a bunch of physicists had measured neutrinos going faster than the speed of light。

ok。A graduate student at CEern who was working with this technology。

Finally discovered the flaw in their experiment。😔，Using this technology to discover it。

Okay and it was， in fact a clock synchronization error now the physicists who did this were not naive。

The hardest part of doing that experiment was clock synchronization。

 they knew that right from the beginning。They had a very， very carefully designed experiment。

 they had characterized fully the clock synchronization that technology that they were using。

 it was a particularly challenging technology because one of the detectors。

Was very one kilometer under a mountain。Okay， and the gravitational effects of the mountain。

The relativity， combined with the gravitational effects of that mountain。

 affected their clock synchronization precision。And they had to take that into account in making these measurements。

Lo theistic effects。And。You knowWhen they first announced this。

 you know they were actually pretty circumspect in this paper that they said you know。

We believe this is probably wrong， but we cannot find the flaw in the experiment。Okay。

 it seems to indicate that everything。That these neutrinos are in fact。

 moving faster than the speed of light。And this grad student。

 what he did was he overlaid this f synchronization technology on top of theirs。

And discovered a discrepancy， and they ultimately traced the discrepancy to a loose connector。

Just a BNC connector that was loose needed to be tightengged up。All of a sudden。

 the neutrinos weren't going faster than the speed of light anymore。So it's an interesting story。

 so how does this work？嗯。So。Let me try to do this a little more interactively because。

It's really cute technology。And very， very simple。

![](img/1e869af21e2f526599754dc45980069b_5.png)

Let's see。If I can make this device work。Find the connector first。



![](img/1e869af21e2f526599754dc45980069b_7.png)

![](img/1e869af21e2f526599754dc45980069b_8.png)

You can do it。

![](img/1e869af21e2f526599754dc45980069b_10.png)

Okay。So。You got two devices on the network， a master and a slave。Okay， and by the way。

 there's a whole protocol overlaid on top of this to determine who's the master。Okay。

 and that protocol in and of itself is pretty interesting。

There's a strategy for finding the best master clock on our network。

There's a strategy for handling the disappearance of your master， the master suddenly dies。

 okay so you have to find a new best master clock and so forth。

 there's a lot of interesting protocol stuff that goes on。

But once you've got the master established and the slave， how do they synchronize their clocks？Well。

 the key thing is that they're both running local clocks。

And these clocks drift with respect to one another， no two clocks will run at exactly the same rate。

So the strategy is just to periodically make corrections。

To the slave's clock so that it locks to the master clock。😔，This is done entirely on top of PCCPIP。

So the way that it works。Is that the master sends a packet to the slave。At a time T1。Okay。

 so this is T1。And it has a local clock and it can measure， it has hardware。

That will measure time T1 as the time at which it asserts the electrical signal on the output wire。

So you need to latch the clock value close to the network interface， it's not going to work。

To set up an interrupt service routine， ask the system clock what time it is and record that time as P1。

There's too much variability in the timing of that for this to work so instead you have hardware that latches the value of your local clock at the time that the hardware is going to assert the signal on the network interface。

WThere's hardware support， interestingly enough， the protocol。

 that 1588 protocol is designed so that it doesn't require hardware to implement。

 you can implement the protocol correctly entirely in software。

And every year since the first establishment of the protocol， theres been a plug fest every year。

 where vendors that sell products that support 1588 get together and check compatibility。

And every year there's been some software implementations and some hardware assisted implementations。

 they're always， it's hardware assisted。It still involves software， a lot of software。

Or not a lot of software， but mostly software。It's actually a very small amount of hardware it takes to support this。

 a few dozen gates。And you're even at five。You have to be able to do things。You know， latch。

Collect into your latch， the current value of your clock when you're ready to。

transransmit the signal， and then that latch needs to be a memory map register so that the software can read it。

Okay。嗯。So。At these blood vessels。You know， the vendors are always competing with one another for the level of clock precision that they get。

Every year the software implementations。😔，Performed five to six orders of magnitude worse。

Then the hardware assisted implementation。Okay， so five to six orders of magnitude to put it in perspective is about 20 years of Moore's law。

Alpha window。So it's as if you choose to use a 20 year old microprocessor。To do your computations。

That' the level that's the amount of precision that you lose。

In the clock synchronization by doing the software implementation。The same protocol without。

That's ourcin。So five to six orders of magnitude means if the hardware gives you one nanosecond。

Concurrence between two clocks， the software implementation will give you one micro oh one millisecond。

 that's six orders of magnitude。Well， that's due to the variability in things like interrupt services。

a dedicated lineYeah you'll see in a minute exactly why the software pays this price。

 okay because when you understand how the protocol works， you can see， oh yeah。

 that's why you need hardware assistance to do this right okay so here's the way it works。

So the master has a clock and it timestamps。The launching of the message and the hardware also injects the timestamp itself into the packet。

 so the slave will receive in the packet， the value T1。

 which is the time at which the master believes that it's sent the packet according to its local club。

Now， the slave will receive it at some time T2。But it will think it received it at some time T2 plus an error E。

Because its local clock doesn't perfectly match the master clock。

So there's an error in its local clock。So as far as it's concerned。

 the packet actually came in at T2+ E， so it also has hardware when the packet comes in。

 a latch latches the value of its local clock and what goes into that latch is T2 plus E。Yes。Right。

 so T2 by definition here is the correct time， the master was able to see when the slave received it。

The master would say it was received at time T2。Okay。So the slave then sends a response。

and it records the time at which it sends the response， which is。According to the master clock T3。

 but according to its local clock T3 plus E。Okay， so it doesn't know T3， in fact。

 nobody knows at this point， nobody knows T3， nobody knows T2。But at this point。

 the slave has three numbers of ill， it's got T1， it's got T2 plus E， it's got T3 plus E。Okay。

 sends the acknowledgement back， the master timestamps that receipt of that message with T4。

 and then transmits T4 back to the slave。The slave now has four numbers。Okay， in fact。

 exactly it has these four numbers。T4， T1， T3 plus E and T2 plus E。Okay。So。

It can calculate from that the round trip delay。Because the round trip delay is this time。

 which it knows， that's t4 minus t1。Okay， minus this time。Which it also knows。That's this difference。

Okay。So it knows the round trip delay。Now it makes a very key assumption。

It assumes the channel is symmetric。It assumes that the propagation delay in one direction is the same as the propagation in the other delay。

 at which point now it knows the one way delay。It's just R over2。Okay。

So if it knows the one way delay。The one way delay， according to these numbers。Is。T2 minus t1。Okay。

 but it doesn't know T2。It knows T1， and in now it knows with this assumption of symmetric communication。

 it knows r over 2。So it can now calculate T2。Right T2 is just。R over 2 plus t1。So。

Now it knows T2 and it knows T2 plus E。So it can just subtract T2 plus E， subtract T2 from T2 plus E。

 and now it knows itss clock error E。So now it knows whether its clock is ahead of the master or behind the master。

And by how much？And so now it can correct its local clock， put it perfectly in sync with the master。

And proceed， and then by the time this happens again， the clocks will have drifted again。

So there will be error accumulated by the next time， but then it'll make the correction again。Okay。

 and so forth， it just keeps doing it。走过去了。Yeah。ThatYou're right， so there's a simplification here。

 so this assumes that you have reasonably stable clocks。😔，So that it takes a while for them to drift。

 right？And that the time lag between your receipt of this packet and the sending of the response is small。

But you're right， technically， these two errors should be slightly different。啊。You can't。ok。嗯。你。好。

The whole issue here is that the performance of this PTP protocol will depend on the degree to which your connection issymmetric。

The more asymmetric your connection。The more poorly this will perform。

This is why the software implementations don't work。Because。You know， first of all。

 there's a lot of variability in the timing， but in addition， you know。

 the receipt of a packet is handled by an interrupt service routine， the timetamping at the centerer。

 well， maybe you timetamp it in the interrupt service routine。

 but know there's kind of built in asymmetry there in the way you receive versus the way you transmit and it's hard to overcome that。

Now， what the white rabbit people did was to design the physical topology of their network to try to ensure。

Very good symmetry， so the way that they were able to get clock concurrence of tens of ecoseconds was by running ethernet over fire。

By running。The two directions in the same fiber， so they're subject to the same temperature effects。

 so the speed of light in the fiber is dependent on temperature。Okay。

 so the propagation delays will be dependent on temperature。

 but the two directions will be subject to the same temperature effects。

The electronics at the two ends becomes the real bottleneck， then， you have to really very。

 very carefully design the endpoints。对。Connect to the fiber。Okay。

 and you have to very carefully ensure that， in fact， in white rabbit。

 they actually temperature control the P chips so that you know these two five chips。

 10 kilometers apart are both operating at the same operating temperature。

So that the latency through the circuits。Until you get to that latch where you've latched your clock。

re very close to one another and so forth， so it takes a very careful design to get really tight。啊。

7even。But once you get that tight symmetry， you get very good concurrence now so the question then becomes。

 well how well can you do on a largely ad hoc network？Well。

If you spend a little extra money on the switches that you use。

 you can actually do pretty well with this。And in fact。

 one of the things that AVB does is AVB has another layer on top of this that enables you to control routing。

 so I mentioned， for example， that you can guarantee that you never lose a packet。

by giving it highest priority and that you can guarantee you can control the latency of a packet through a switch in ABB。

So once you can control the latency， if you give these PTP packets the top priority。

 the latencies are going to be very deterministic and very symmetric， if your routing is symmetric。

 the latencies will be symmetric as well。So you set up symmetric routing。

You set up the highest priority for the PTP packets and you get very good symmetry and consequently very good clock concur。

And it takes a little bit of hardware support to the switch to do that。

 you can't just go to Home Depot and buy a switch and expect it to work well。

But if you get an AVB cognizant switch。Then you can set up the routing and set up the priorities so that you get these symmetry。

And that's what people do。And you can get very deterministic networking。

 you can have set up a TCP IP network where you never have。

 you can dispense with the acknowledgeknowledments， you don't need them anymore。

You're not going to lose packets。吹牛。The master doesn't need to know any of these。Because the master。

 by definition， its clock is correct。Of。No， the slave this packet doesn't carry any meaningful payload。

There's no need to send anything back to the master。

The only reason for sending this is so that the master can report T4。Okay。Make sense。Yes。

All this is being done by the slave's job is to synchronize the the master。

So it's remarkably simple right by the way， this is essentially the same technique that's used in NTP。

 which is a much older protocol dating way back to the 1970s， it's used， for example。

 all Apple devices。Synchronize their clocks to a clock in Cupertino using NGP。

But therere theyre doing it over the open internet， so there's no control over the symmetry。😔。

So MTTP gives you clock precisions sub second， okay？

Maybe 100 millisecond of precision if I were to check whether my laptop and my phone agree on the current time of day。

Probably within about 100 milliseconds， they agree。 but not much better than this。不9。

This wouldnIt's the same program， so it doesn't do any better unless you。😔。

Have have some control over the physical。By the way， this is getting installed in all kinds of stuff。

 so Cisco is putting hardware support in all their equipment for this and not because they expect to provide this clock synchronization as a service。

 in fact we've been leaning on them that they should。Provdes their clocks as a service。

 but their goal is just to synchronize clocks to be able to do network forensic。

So switches log events in the network。And they want to timestamp those events and be able to play back a movie of what the network did。

Right。So you can understand the dynamics of a network， why do you get network storms。

 where are your routing problems， et cetera， yes。No。

 it just needs to be that current time D1 is the only payload fee。

On that direction on T4 on this link。The s calculates the round drift delay。Okay， first。

 it calculates。Right here， the round trip delay is that first formula。律 know？It does， it knows T1。

 T1 is the payload of the first packet from the master to the slave。Okay。Don't crash computer。

Don't crash。

![](img/1e869af21e2f526599754dc45980069b_12.png)

Worked。You talk to the computer nicely。All right， all right， let's talk a little bit about wireless。

就。Here's three。Acronyms。Okay， pens， lens and ws。So personal area networks have lower range。

 local area networks have bigger range and wide arant networks have even bigger range。Some of these。

 most of these， I think are probably familiar to everyone in the room with the possible exception of this one。

How many of you have heard of C Fox？Nobody， really？Wow。😮，こ。You're going to learn something。Yeah。

This is a French company that is making a cellular network that's actually been pretty widely deployed in。

Spain， France and in England。And is being deployed for the first time in San Francisco and on the peninsula。

The first deployment in the US。And it's a cellular technology that by design has very low bit rates。

Approximately 100 bits per second。It's what you can transmit。

 so you can't use it for voice communication， but who uses their phone for voice communication anyway？

I mean， nobody does that anymore。It's so 20th century。Use phones that way。

What are you going to use this for， whether youre going to use it to connect all kinds of other devices？

就是 Internet。And the goal of SigFox is to basically provide a cellular service to a device。

For about a dollar a year。That's the cost compare that to what you pay。

The phone company for your cellular service， right？It's a lot more than a dollar a year and in fact。

 you know all of the cellular providers today actually provide degraded service options for internet of Things applications。

That leverage their existing cellular network， but the cheapest ones I've seen are $8 a month。

So they're really still。Quite far from a dollar a year。

So Sbox business model is that the cost of the network access will be built into the cost of the device。

When you buy your car。There'll be a few dollars paid for network access for the lifetime of the car。

And the car will be able to send a few hundred bits per second from anywhere and receive a few hundred bits per second from anywhere。

That's their business model。So very different from the trend in cellular that's been towards ever more bandwidth。

Yeah。I don't know that。I don't know the answer to that question， I haven't dived into the low level。

It's also designed to be very power efficient so that a terminal that connects to this network can run off bat。

But。And part of the way it does that is by using very low bids。Okay， Bluetooth。

 you're all struggling with the lab， I don't have to tell you much about it， except。

Maybe a little bit of background， it was developed by Erickson in Lund， Sweden。And in 1994。

 and the original intent was to replace all those heavy cables that you use to connect your printer to your laptop。

 really they were competing with USB。Okay， that was the intent so that you didn't have to have cable connections to the things on your desk。

So by design， it was meant for short distances。One interesting application that is a fairly recent one is simply proximity sensing。

 using Bluetooth as a beacon， so it's a way that devices can just announce their presence to things that are nearby。

And that beacon technology was not originally anticipated by Ericson， I don't think。So Zigby。Is a。

Protocol built above。Lower level protocols。And there's a family of lower level protocols that are known as 802。

15。4， this is the IEE naming scheme essentially for the standardization body that standardizes these things。

And。嗯。So ZigB is one of the protocols built on top of this wireless heart。

That's a really weird acronym， highwayway addressable remote transducer protocol。

You can guess which industry？First drove the development of this。Amotive。

Communicating between infrastructure and cars， but it's being used in a lot of other things。

And it integrates a technology that was invented here at Berkeley by Chris Pester's group。

Which also is a clock synchronization mechanism called TSMP。And for time synchronized mesh protocol。

And I want to emphasize that this is a very interesting use of clock synchronization。

So GSMP was developed for battery powered network devices。

To solve the problem that you don't want your bat your radio on all the time。

Because if you have your radio on all the time， your batteries is going to last a week at best。😔，Bye。

But you do want your radio on all the time because you want a new mesh network。

You want every device to be able to relay messages。That way you don't have to send messages very far。

 which means you can consume less energy to send messages and you can extend the network without having to flood it with high power radio signals。

I would say you want to do mesh networking。You don't want your radio arm all the time。

 how do you reconcile those？Well， you synchronize clocks。Okay。

 if all of your devices have clocks that are synchronized， then they can all wake up at once。

 communicate， go back to sleep。Then wake up later， communicate， go back to sleep。

Each time you wake up， you correct for clockers。So you keep your clock synchronized this way。And。

In devices they use this protocol， they use very cheap clocks。

They use the same clocks that are used in watches， same crystal oscillators that consume an extremely small amount of energy。

 so the clock can be running continually on the battery power without having a significant impact on the life of the battery。

But it drifts by quite a lot because it's a pretty sloppy clock。

so you have to make these corrections periodically to your clocks。O。

So mesh networking is very interesting in wireless communication because of this ability to relay signals。

Right。Well， protocol， the clock synchronization mechanism used in TSMV is much more primitive than this。

It's a very simple mechanism。Wake up at a certain time that you think is the right time to turn on your radio。

And then the protocol says that you should receive a message some number of microseconds later。

 I don't remember what it is， right？So when you receive that message。It's a little off。

 it either came earlier， it came late。So you assume that the amount by which it's off is the amount by which your local clock is on。

Okay， and then you just correct your local clock。It's a much crude technique than 1588。

 and as a consequence it gets much lower precision， so the clock synchronization protocol called it。

DSSMV embodies。givesives you clock synchronization precision on the order of a millisecond。

So about six orders of magnitude works than 15。All right。嗯。So these are called slotted networks。

When devices wake up at free agreed times， communicate and then go back to sleep。

Versus unslaughtted networks where either all nodes are always listening or your leaf nodes could go to sleep。

You can't asynchronously send data to a leaf node。So the way you communicate with a leaf node is it communicates with you when it wakes up。

So you're a hub， for example。Your leaf node sends you a message saying， hey。

 have you got anything to tell me？And then the hub responds， yeah。

 I've been waiting for you to wake up， here's a message。Okay。So that can be used without clock。

That's a scar network。You have to have a powered hub whose radio is on all the time。

So the energy efficiency you can get from this is really quite dramatic。

 Chris Easterster claims that essentially the same device。😔，Without this clock synchronization。

 we'll run for a week on a coin cell battery and with the clock synchronization we'll run for five years。

な可いすど。That's what he claims， but he's trying to sell products through his company。

 does network so take it with a grain of salt。Okay。

So there's another layer of protocol on top of this to talk to energy constrained devices。

 this is called COAP for constrained application protocol。

 and this is addressing a very real problem， addressing a very real problem which is addressing。

Devices。As the number of devices gets big， you run out of addresses in the IPV4 address space。

 so the current prevalent internet protocol， which is called version 4， uses a 32 bit address。

 so these addresses that you see you know 128 dot blah dot blah dot blah。That's 32 bits。ok。

En coded as fouroc1s。And。There's only so many devices you can address with that。So I be me6。

There was no IPV5。But IBV6 uses 120 bit addressing。But that's deemed to be expensive for。

Low power energy constrained devices， so COAP is a gateway technology。

That assigns local 16 bit addresses on a local wireless network。

And does all the address translation to IPV6。So every one of these devices on a COAP network has an IPV6 address。

 you can talk to it as if it were on the internet。But in fact， it's only processing 16 bit addresses。

And the gateway is handling the extra overhead。For。The cause。Energy。

So processing lots of data cost energy。You were talking。

 these aren' the same of her battery power devices。Yeah。

 becauses itself it takes more bits on the packet， so there's more energy devoted to radio。

 more energy devoted to processing the packets once you get them。And these are also doing routing。

 these are mesh network。So you actually the addresses matter。

 you actually have to parse the addresses and process them to know where to send them in the packet。

And so forth so having smaller packets saves a considerable amount of better。Yes。不对。Yeah。

 the address has to be part of the payload because the intermediate nodes have to handle over routing。

Okay， wiF you all know about。And I'm running out of time， so I think let me just skip through。诶。Yeah。

 I think we're pretty much out of time， so I have more to say but。

Maybe if there's extra time on Tuesday after the midterm review I can vote。ButOtherwise。

 I think we should。Stop here。All right， thanks。

![](img/1e869af21e2f526599754dc45980069b_14.png)