# 【计算机体系结构】普林斯顿—中英字幕 p102 101_06_routing-and-flow-control -BV1ii421D7WR_p102-

Okay， so now let's briefly touch on routing protocols。

 There's lots of different routing protocols out there。

 and roughly let's split them into two different categories。

Olivious routing protocols where the routing path through the network is independent of the state of the network。

And the second one is adaptive routing。These are sort of smart networks。 They look for。

 they somehow look at the state of the network and make some decision。

 And if you build a good adaptive routing network， what you're going to try to do is look for the hotspots in the network。

And route around them。And this is where that path independence or multi path。

Networks come in if you only have one route from any point to any other given point。

The routing is basically deterministic， you can't go route in the wrong。

 you can't go route someplace else because you'll never be able to get to your destination。

But where this becomes interesting is if you look at just the basic mesh network。

 Our basic mesh network has many different points between many different routes between any two points。

 So we have a， let's say4 by4 grid， you can just sort of go across the top and then along the side。

 Let's say if're going in from the top to the bottom。

 or you can sort of zigzag along the middle or go the other way， go Y and then X or X and then y。

 There's lots of different choices along there。So that's where we start to get to decide about different routing networks。

嗯。Under Blis networks， there' there's two。Sort of sub。Points here， one is deterministic。

Which basically says， do the same thing。All the time versus a non deterministic design。

 and you might say what is a non deterministic oblivious routing algorithm？Well。

 it's typically a randomized routing algorithm。 And these can actually do slightly better than the deterministic。

 oblivious routing algorithms。 So let's take an example of this nondeterministic。

 but still doesn't look at the state of the network。

 So let's an example of this is something where you， let's say， choose。

Some node in the system at random and you route there first， and then once you route it there。

 you route X and then y to the destination。😡，Now I might say， why would you want to do this， Well。

 it' actually sort of scatters your traffic around the network and actually route in different directions and could potentially increase the delivered aggregate bandwidth through your network by doing this randomized choice at the beginning where you choose some other node which might be routing the wrong direction first。

 but then you'll have more aggregate bandwidth， let's say to a destination。

So you can actually have non deter herministic oblivious rabbit。嗯。Adaptive routing。

 I'm going to sort of not talk about in this class， because。It's a very active research area。

 I recommend you take 5，80 A if you want to learn more about that， because that's， that's。

Very broad topic where you try to。Look for congestion network and route around the congestion and if you try to do that。

 you have to make sure your network doesn't deadlock or have other bad conditions that happen。

 and to some extent usually these networks trade off let's say。

 ease of analysis at least for performance。I wanted to talk about one quick deterministic。

Olivious routing algorithm on a mesh。So let's draw a me here。Okay。So， we have our。16 node。

F area2 cube here。And we want to route， let's say， from a。To be。

The most basic or one of the more basic routing algorithms that we're going to look at here。

 we're going to call dimension ordered。Routing。And it's called dimension order routing because there's actually two dimensions here。

We'll label this as， let's say， x increasing， we'll label this as y increasing。

And dimension order routing says that we order the dimensions in which we route。

So we always route it in one of the dimensions before we go to route in the other dimension。

So if we want to get from here to here。And let's say we have。X。Then y is our routing。

We're going to route this way from A to B first。So now we've matched。Our x location to where B is。

 and then we're going to route down。So this is x and y。This is oblivious。

 It doesn't matter about the traffic， and it has some bed。Problems that show up if you do this。

If we have， let's say C and D and it's trying to route from C to D。

It needs to share this link with traffic going from A to B。And it can't route around it。

 I can't like， I dont use those links or something else。

 It's just not allowed in our oblivious routing algorithm and definitely not allowed in our dimension ordered。

Now， dimension ordered。There's networks there。 let's say X then y。 and you can also have。

 let's say Y and then X。 this also generalizes to three dimensional n dimensional sort of spaces。

 you do let's say X then y then Z。Or W， then x and y and then Z or something like that in a four dimensional cube。

嗯。But one of the good properties of dimension order routing is it's not going to deadlock。

 And we'll talk about that in a few slides。 But the network itself is never going to deadlock。

 That doesn't mean you can't get message dependent deadlock。

But if you wormhole through the network here。You can actually come up with a proof that shows that。

You will not ever deadlock this network， and the rough sketch of the proof goes like this。嗯。

By only using X links first。And then using Y links。You will only ever acquire。A next link。

And then acquire a Y link and then release an X link。And then release a Y link。

So you'll never actually grab。A resource that you you have needed before。

 and everyone else is doing that same。Algorithm， so they will never try to grab a resource in order that is is is faulty also。

 So if you go back to our sort of design dining philosopher's problem here。

 you're guaranteed that you're going to acquire resource  one and then acquire resource2 and everyone's doing that same algorithm so they will always acquire resource one or block waiting to acquire resource  one。

 and then you acquire resource2， but you'll never see a cycle。So because of that。

 you'll never acquire x and then y and then x。In this dimension order routing。

 so you'll never get a cycle in your dependency graph。That's the rough sketch。

 And the full sketch is a little more complicated， Usually these two dimensional。

Mesh networks without and around or without a Taurus。

 you have to sort of prove it in this direction and in that direction and sort of it decomposes into sort of X from west to east and X from east to west and vice versa。

 but that's the rough sketch of the proof。But just want to get across that。

It's a basic routing algorithm， but there's lots of other choices here。 As I sort of said。

 there's this nonterministic one， there's adaptive routing algorithms so a good adaptive one。

 sometimes called hot potato routing is that if you don't have any buffering in the network so you can't buffer along the way and if you get to a node which has a link which is congested。

 you just choose randomly some other direction and you route that direction。

The thinking here is at some point， you will actually be able to choose again。

And route towards the right direction and slowly you'll move your traffic or your packet will move to the end point。

 but it allows you to sort of go around traffic congestion points。

 but I don't want to go into too much detail this because this is a whole lecture of itself。Okay。

 so let's talk about flow control。This is a。Aspect of networking that I really enjoy， actually。

So flow control is making sure that you don't drop data。

Making sure that you have back pressure in your networks so that you don't lose。

 lose data in your network。 And this flow control can either be local on a link by link or a hop by hop basis。

Or could be。Round trip。 So a good example of round trip flow control is going back to something like TCPI。

 you actually want to rate limit the round trip flow control so you don't flood the network if a given link is too small。

 So there's actually a protocol in there which will rate limit the round trip flow control or a good example actually on chip network。

 So something like a minico。Is if you're trying to guarantee that you do not overrun a buffer。

In the memory controller， but lots of different nodes of trying to route to the memory controller。

 you can actually have some sort of counter which。Effectively is a roundtri flow control to the far away endpoint node and say。

 okay， you are allowed to have five outstanding memory transactions to the memory controller。

 if you try to send a sixth， you need to wait for the act to come back。So this is。

A end to end or long distance flow control。 But each of the hops along the network themselves may have localized flow control also。

 so you can actually layer these two things together。And。Typically， sort of for on chip networks。

 we like some properties and even in computer system networks。

 we typically like the networks to be resilient， so we don't want sort of data to be dropped。

 but that's not not necessarily a guarantee。 people have built networks where links can drop data。

 So that's another option is you can drop the data and try to retransmit it if you want reliable transmission from one point to another。

Okay， so let's look at。A quick example here of。Flow control in our networks。

 this is not in your handouts。So you guess to pay attention。

TheFirst type of flow controller to look at is basically a stall wire。😡，Or a big stop sign。

So hero is what we have is we have a sender。It was a Q， so Q subseer and Q sub R Q sub receiverceive。

And we've named sort of all the points along here。Let's say in this network we have。

A register in between the sender and the receiver。 And this is in our link。

 This is sort of our link cost。Takes a cycle， maybe pipeline the wire。Okay， so now。

Data arrives here into D。😡，Which is our sort of receive point into the receiver。And at some point。

 it decides。I can't take any more data。 I can't read that data。 I need to go process some of it。

 so I need to stall the network。So it says stop。So it says stop here。And in a perfect world。

 this goes through some combinational logic just completely。

 just like your pipeline stalls this point in the pipe， stalls。

This flipflop stalls that Q stalls the going this way， stalls A， stalls the sender。

 tells it not to actually send any more data。So it's a stall。We stop in D， C stops， B stops。

 A stops instantaneously。At some point。D unstalls because it can go redta more again。

 and the network keeps flowing again。So sorry， what this is showing is these are packets。

 these are not fits， these are complete packets gain center or complete Fits gain sense。

 this is our flow control unit， so we're looking at each one of these ABs and C's here and Ds are uniquely flow controllable units。

So that's on off flow control of our combinational stall signal。 Now。

 problem with this is it took us a cycle to send data this way because we had a flip flop going that way。

But our stall wire runs all the way back。嗯。that's not good from a cycle time perspective。

Because if you look at the combinational sort of path now， you're going to see， well。

 maybe you have an output of this which says there's data available that goes through some logic in D。

 and that generates a stall signal， and then it has to propagate physically a long distance away and go into lots of other logic。

And after having designed a couple of these sorts of networks。

 you're never going to be able to build that。 Thats if you want to have a high performance network。

That time is too long because if your cycle time is anywhere near the length of wire the delay of the length of wire you have。

 you're not going to be able to build that。Okay， so now we start to look at。

We switch to something and say， let's try to solve them， put a pipeline。Fop in here。

On the return path of the wire， the stall signal。Okay， so what happens Well， if we look at this。

For packet 0，1，2，3， at some point， D decides to stall but。🤧嗯。That is not able to stop。😡，Let's say。

A from sending the cycle before。Because we now have a flipflop in this path。

 so it doesn't know about that。Likewise， it doesn't know it can't stop。

B and A from moving forward one cycle either。So if we look at the pipeline diagram。

 what that really means is these arrows here， we can't stall this on a dime。 We have to wait。

 and we actually are not able to stall until the next packet。 Likewise。

 when not will install B and A until later， and this could even be worse if you have multiple pipeline registers going backwards here。

 which is pretty common。Now， the implication of this is。You were not able to stall sea it all。

So like it or not， the data is coming this direction。😡，From。R to Q sub bar。

So what do you go about doing at this point？So this is a tough one。😊，You could either drop the data。

😡，That's probably not very advantageous because you're going to drop random data in your network。

 networks like to actually deliver data。A better thing to do is to have extra buffering。In Qabbar。

 and we'll call this skid buffering。So that the data is called skid buffering because it's kind of like in a car。

 you hit the stop。Pedal or they hit the brake pedal。

You need some runway to skid into before you can actually stop。

So you hit the brake and you're sort of skid to a stop and you need that， that extra area。

 So we budget that into this queue here。 and you can actually build a network。

 build a flow control system where you have extra space and queue subbar to skid into。

And then when you unstall。You'll see actually that。There's basically。That should be a D， sorry。

 it takes a cycle to unstall also。So that's， that's kind of not good。 Comly。

 you have something to feed at that point because we have that extra value in Q sub bar。

 But there are cases you can come up with where you stall and not stall and then install and not stall where you can actually accidentally introduce bubbles with this type of flow control。

 I don't have a diagram of that here。 But that would show up as basically a bubble throughout the entire pipe and no data being red。

 But you can construct that with this sort of on off flow control。 pipeline flow control。🤧。

So you could also think about having。Onal flow control， partial pipeline stall control。

So what I mean by that is instead of feeding up into this register here。

 now we need two skid buffer entries over there because we can't stop。

B flowing into here or C flowing into there。 So we can't stop any of this stuff。

 If we need two entries now in that skid buffer。And we're running out of time。

 but I wanted to try to finish this flow control notion up here。

A good solution to this is called credit based flow control。So in credit based flow control。

You put a counter in the sender。And the counter counts how many entries there are in the receive FiIFO。

And then what it does is it starts sending data。And whenever data is removed from this FIFO。

 a credit gets sent back。 and it could be pipelined multiple levels deep here on the return point。

When the credit comes back， you increment the counter。 But when you send a word。

 you decrement the counter at the counter。Ever reaches zero you stop sending。

This is actually ends up being superior than。This sort of designed because you don't have funny stutters on the receive side when you go to build a credit based flow control system。

That's a little bit beyond showing that proves a little bit beyond this course。

 but I did want to say here that when you compute this。

 you need to compute how large the credit needs to be and how big this receive iPhoneO needs to be。

 and they need to be sized appropriately。If you size one of them wrong。In this case。

 if you size one of them wrong in the on off flow control， you're actually going to end up losing。

Data。If you skid into your skid buffer and you need two skid entry slots and you only have one skid entry slot。

 you're going to lose data。In the credit based flow control system， the counter。Just reaches zero。

So just impact your bandwidth， but you're not going to lose data。Now， having said that， you should。

 if you want high performance through this network。

 you should size this and this counter to be the same。

 and you should size it big enough to take into account the entire round trip latency of this communication。



![](img/f8d8dd59777ce0b9c45388c92d961762_1.png)

Let's stop here for today， I'll briefly finish up Delock next time and then we'll move on to building large many core systems or large multi core systems and coherence protocols for them next lecture。



![](img/f8d8dd59777ce0b9c45388c92d961762_3.png)