# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P8：-8- Routing 3 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Good morning。And welcome to routing lecture number four。嗯。Routing and addressing really。

Okay so quick today in computing in February 13th 74 years ago was the first demonstration of EnIAC which was the electronic numerical integrator in computer。

 it was really the first real programmable electronic computer I think it was today there seems to be some disagreement on this subject the actual dedication of it is the 15th and there's a lot of people who mentioned there being a demonstration on the 14th but there are also some references to there being a demonstration late at night on the 13th so I think maybe today it was designed at University of Pennsylvania it's still there at least part of it is in fact the part that you can see in this picture I think is still there if you visit Uen you can go look at it and so yeah there's a picture of part of it the whole thing was much bigger I think a lot of it has been lost at this point those are two of the original programmers of it standing there。

😊，So it had 20，000 vacuum tubes and drew 150，000 watts， so something like 3。

000 times more electricity than your laptop。😊，EACs birthday Ih。

It's also the birthday William Shockley who's dead now， but in 1910 was born on this day。

 he was a major player in the development of the transistor。

 he won the Nobel Prize War along with a couple of his colleagues at Bell Labs in a lab that he directed there so to commercialize the transistor。

 moved from New Jersey to Mountain View， and this was the first Semiconductor Company in the Bay Area。

 this was the beginning of the Silicon Valley was him。😊，And yeah。

 so just to pull things together last time I mentioned Mike Markla。

 who I mentioned worked at two companies， Fairchild and Intel before he worked for Apple。

 and before that talking about Jack Kilby who invented the first integrated circuit and then the guy who invented the second integrated circuit was Bob Noce。

 Bob Noyis also worked at Fairchild and Intel was a founder of Intel。

 but before that he worked for Shockley， and he and eight others rebelled。

 left Shockley started Fairchild then he left Fairchild and started Intel。

 so all of this ties together， the Silicon Valley history here。😊，All right。So today in 168。

I going to do a project update。We're going to finish up talking about learning switches and the Spanish protocol。

😊，Then' going to talk about addressing and then if we have time， which I don't think we will。

 we will play the Spning Te game。So starting with that first one。

 an introduction to Project one by Lloyd， who is the lead TA on that project。😊，Maybe this will work。

Is this working， can you guys hear me okay？Okay， so today we're releasing Project one。

 like the announcement I sent out last night， it's going to be about distance inspectors so you're going to be implementing a variant of distance inspector just a couple logistics related things I sent a post on Piazza detailing。

 can you guys not hear me？The back。Okay， okay， I'll get close so we put a post on Piazza detailing where you can find all the project related materials which includes a write up。

 please go through the write up as you're doing the project it will help you immensely also we have worked hard to put a bunch of demos in place that allow you to see what's going on with your router on a bunch of different apologies please go through the demos for each of the stages as you're going through the project it'll help you not only understand what's going on in the project in total which will help you get a better grade on it。

 but it will also help you for the exams too to understand how to implement distance vector。嗯。

A couple other things so on Piazza we will be of course you guys answer or ask whatever questions you want if you have questions about the project we will be doing all setup related things on Piazza we will not be doing any setup like installing Python and all that kind of stuff in office hours Lastly regular office hours should not be used for project related questions those should all go to our new product office hours which are now updated on the course schedule。

If you have any other questions， please feel free to either pig me on Piaza or the other TAs and come to office hours and we can work on distance vector。

Okay， thank you guys。Any questions for Lloyd right now off the top？2。Thank you。All right。

So learning switches and the Spry protocolto， which is where we left off last time。

 I'll sort of recap where we were， which was getting through most of learning switches。

 and then we'll move on to the Spanishry protocol。😊，All right。

We'd been looking at disinspecor and Li state protocols where the tables are kind of filled in by this ongoing routing process with plays like ongoing routing messages and for both of those protocols we sort of seeded the routes with you like static routes which then got sort of propagated and these two types of routing protocol are really common for working with L3 for the network layer with IP addresses and then we decided we're going to look at something really different which are learning switches and in those the tables are filled in sort of opportunistically by the data packets。

 there's no separate routing packets that fill in the tables。😊。

And there's no seeding with these static routes。😊，AndThese are really common to do essentially routing at L2。

 some people won't call that routing， but it fills in the tables， so I'm going to call that routing。

The way it works really quickly is that when a data packet arrives at a switch from some neighbor。

 like here we're showing a data packet。😊，From A to B arriving at the switchitch S1。

When that packet arrives。You know。That you can reach the source of that packet。

By following that packet backwards， right， if you use the neighbor that you got the packet from。

 you should be able to get to the source。And so we use the source address in the packet to fill in a table entry for packets destined for that address。

 so in this case that's a so we populate the table entry for A at S1。😊。

Now this packet is going to be， and we don't have a table entry for B。

And so in everything we've looked at so far， we run to this case， we would just drop the packet。

 we'd say we don't have a table entry， we don't know what to do with this。😊，But what we do here is。

Instead， we flood it， we send it to all of the neighbors。It's sort of。

 we're you being optimistic that B is out there somewhere。

 and if we just kind of send it to everybody， then it'll get there。So S2 and S4。

 at this point see the packet and they say， well， it came from a and it came from S1。

 so I should be able to reach a through S1， right？😊。

They also don't know what to do with packetet from B， so they flood it。

So S3 learns that it can reach A through S2。S5 learns that it can reach A through S4。

They don't have entries for B， and so they flood the packet。And B ends up getting。

 the packet ends up getting to B， right， which is where it was supposed to get to。

So now if B wants to reply to A。It can just follow the table entries straight back to A。 right。

 It doesn't need to flood it anymore because there's now table entries to A， moreover。

As this packet progresses from right to left here， it's like leaving behind table entries that point to B using that same process。

 right？So the next time A wants to send a packet to B。It doesn't need to flood it either， right。

 It can now send it directly using those table entries straight to B。

So the big problem here was what？Cyclees， yes， the big problem here is cycles right。

 as we learned last time we saw the video， when you have loops in your network。

 flooding runs you into some problems。😊，So I said our previous solution for flooding doesn't work in this case and that I would come back to it。

😊，So first I wanted to point out that the decision of whether you know to flood or not is like made on a switch by switch basis right it's not like a given packet is like going to be necessarily flooded across the entire network or sent sort of point to point and cross the entire network。

 it's every time it gets to a switch， you look at the table， if there's a table entry。

 you just send it to that neighbor， if there's no table entry， you flood it right？

And so here I said with some pseudocode and who am I kidding this is Python of basically the algorithm for a learning switch right。

 so a packet arrives from some neighbor which we'll call the previous hop。😊。

And the first thing you do is learn from that neighbor， right， you've got some table。

 you use the source address in the packet to pick the table entry。

And you set the next top to be the previous hop right if you're trying to go to that address。😊。

Then you use the hop that you got this packet from。

You also set a TTL so that these things eventually time out and you can learn new ones。

 which you might want to do because the topology might change or the host might migrate from one place to another or something like that。

And。Next， we do this forwarding part where if the destination。

 if we have a table entry for that destination。Then we look up the next top。

If that next hop is the previous hop。Meaning the table entry is telling us to send the packet back the way we came。

We don't do that， we just drop the packet and stop there。Because of course， if we sent it back。

To the switch that just sent us the packet， they're probably just going to send it right back to us。

 right， They had just sent the packet to us in the first place。 So we don't want to send it back。

Otherwise。We'll use that next top， we will send， we'll forward the packet there to that next top。

If the destination wasn't in the table， then we're going to flood the packet to all the neighbors except the one that we just got the packet from。

So is that pretty clear what？What this algorithm is。All right。So back to this。

 I said our previous solution for dealing with loopy topologies doesn't work in this case。

 so first question， what was our previous solution to dealing with loopy topologies and flooding？😊。

This was in the context of how we flood in Li state， you know。

 we need to spread that local information globally in Li state and we do that by flooding。😊。

And so how do we solve the loops in the flood problem for Li state？Sequence number， right。

 like we have this rule basically where like the first time we see this packet， we flood it。😊。

If we see it again， we don't。 And we know that we've seen it again because basically for each router。

 we're keeping like。Track of its highest sequence number。

 which it increments every time it sends a packet right so if we've seen a sequence number。

 if we see a packet with a lower or equal sequence number to the most recent one we've seen。

Then this is an old packet， if the sequence number on the packet is higher than the most recent one we've seen then it's a new packet。

 right？But this doesn't work for this case。So。Why not？There's probably several answers here， anybody。

Anybody have an idea of why this wouldn't work for this case？So the senders。

 in the case of Link state， who was sending the packets？The packets that were flooding。

 who originated those？Yeah。You were。I think you're almost there。So you know。

 is it because the sequence number should be on the routers and not on the packets and maybe a scaling problem of some sort？

So in Link state， we were like you know the problem we had were these looping like route update messages。

 right， so who sent the route update messages？Was it。Was it a host？

See some shaking heads thumbs up if it was a host。Thumbs down， it with something else。All right。

 so what was it？It was a router， right， the router sent。

 and so you're keeping track every router needs to keep track of the sequence number for every other router。

😊，Now in this case， we're not talking about routing messages， right， this is powered by data packets。

 right， so who are the sender of these packets？😊，Hosts， right？Potentially every host。Right。

In your network， how many routers are there， I don't know， some number。

How many hosts might be sending data through your network？Potentially a very， very。

 very large number， right， you probably can't keep track of all the sequence numbers for every host。

You also have this problem that data packets don't necessarily even have a sequence number。

 and it's too late to do anything about that now yeah。Yeah二。Yeah。

 so could you do that and to some degree that would probably just happen except again。

 it gets to sort of the and for reasons that we'll kind of get into earlier。😊。

These might be L2 packets right and L2 packets don't have a TTL， at least at this point。

 so there is that， but you're right， you could potentially do that。

 you could say here's a new version of the L2 header that has one， and so that would work。😊。

Some of my research is actually in this area and I use that amongst other approaches as part of it。

 so there are things that you could do。😊，Yeah， so there are definitely alternate approaches。

 but in general， you know the one that we used for routing doesn't work for Li state。Right。

 I'd say there's a different approach， the one that we use for Li state doesn't work。

 you could come up with something else， absolutely。

But the solution that was sort of decided upon for this for various reasons。Is。

To disable links in the network。Until there are no loops， but you're still connected。

So essentially you turn the network into a spanning tree， just getting rid of all the loops。😊。

Once you do that， you can flood safely， because you can flood safely on a network with no loops。😊。

So does that make sense what the approach is， take your network with loops。

 disable links until it doesn't have loops。And so to do this。

 we have this protocol imaginly called the spanning tree protocol。

 And so how it works is it basically does three things。😊。

The first one is it finds least cost paths to every switch from every switch to the root。嗯。

And then it disables data delivery on all of the links that aren't on a path to the root。

 a best path to the route。And then when the tree breaks， it starts over。

So looking at these in some more detail here， the first step。

 we find least cost pads from every switch to the root。And。

This should probably sound pretty familiar right like as we talked about in the first grrouting lecture know like essentially we're forming these trees to every destination when we're doing destinationbased roouting right so we already have talked about a couple algorithms or protocols for solving this particular problem and essentially it turns out that the span tree protocol ends up being incredibly similar to distance vector。

😊，The big difference is that it only makes a single tree right when we talk about distance Specor。

 we had a tree basically rooted at every destination and now we just have one single tree。

 in a bunch of our examples， we were only looking at one destination at a time just because it was the same for every the same process for every other destination。

 but in this there literally is just one destination。😊，And that destination， that root of the tree。

 the spanning tree that we're constructing。😊，Is basically it's the switch with the lowest numbered ID so every switch has a sort of intrinsic ID and you pick the root by just using the one with the lowest one and so it turns out that you can basically with a slight tweak to distancespecor。

 you simultaneously both get best paths to the root while also finding the lowest numbered switch to use as the root。

 so you actually do those two things at exactly the same time。😊，So in detail here。😊。

The algorithm looks kind of like this。 All switches start out by thinking they're the root as far as they know they have the lowest I。

They advertise essentially like a route to themselves to all their neighbors。

 just like we did in distance Spec， right？😊，And so that message says something along the lines of。😊。

The root is， and at the beginning of time， they decide say my own ID。

And I can reach in zero hops because it's me， right？

So everybody starts out by saying that to their neighbors。

And then when you receive one of these spanning tree messages。

 which is like a route in distance vector， like a route advertisement。

The first thing you do is compare the advertised route to what you think the route is。

If it's smaller than what you think the current route is， though advertise one is smaller。

 then that's a better route right because you're trying to get the smallest one。

 so now that's going to be your route。If it's bigger than what you think the root is。

 then you ignore it， right。That's not what you're looking for you're trying to find the smallest route。

And if it's the same。If the advertised route， this advertisement comes with the same route as you think the route is。

 then you essentially just do the normal distance inspectspecor type update or if it's smaller than the one you have。

 then you choose the smaller one and keep track of which neighbor to use。😊。

One little difference here is how you break ties， right。

 if you have two neighbors that are telling you the same distance to the same route。😊。

Then you break the ties by preferring the advertisement from the neighbor with the lower ID。

 so you never end up actually having a tie， you can always end up saying this one is closer。

Does that make sense？Yeah。Yeah。They both think they're at the room and they both tell each other their ID。

 So if you're one of the switches， I'm one of the switches， I say。😊，I think the route is zero。

And the distance to it is zero。And you say， I think the root is three。And the distance is zero。Yes。

你哋看。Right， so how do you decide where the root is in sort of right and so one answer to how you decide where the root is is who cares。

 it doesn't matter all you're looking for is a tree。So which actual node happens to be at the root？

Maybe it doesn't matter practice。To some degree。Every switch。

 the way it works modern un switches for the version of spanry that's deployed is every switch actually has a number of addresses。

 ethernet addresses， which are like kind of burned into the hardware。

When it's manufactured and those are all unique。And so you actually just use like the lowest one。

 and so that ends up being your ID， but essentially just intrinsically every switch has an ID operators also the way the protocol works。

 can modify it so they can kind of override it if they do decide that some switch is better than others to act as the route。

😊，But this is actually a management problem if you， as an operator， say， oh。

 I want this switch right here to be the root， right， what happens when that switch fails？😊，Well。

 that's not the root of any tree anymore， it's going to be something else。

 and so did you plan for that if you've planned something saying it's vital that the switch be the root。

 and then there's some sort of failure and it's not the root anymore， how far ahead did you plan。

Yeah。Any other questions on？What this algorithm looks like。

 and we'll walk through some examples yeah。If it's smaller and current。

 it's saying compare the advertised route to what we think the route is。

 so it's comparing IDs of the root。😊，All right。So when things update。

 you send a triggered update so all your neighbors know that your route or your distance to it has changed。

And another difference from the distancespecor that we talked about， you know。

 and the one we talked about， every switch was like periodically telling its neighbors advertising to its neighbors。

 spanning tree just a little detail is that it works a little bit differently。

 only the one that thinks only ones， only switches that think they're the root。😊，Actually generate。

These spanning tree messages， these sort of like periodic updates。

And the other switches just forward them， and so there's only sort of like one source of these things。

 but it has sort of the same effect， if ever a link goes down between two。

 they'll stop being passed from the root through those links。😊。

So the second step was to disable data delivery on every link that's not on a shortest path to the route。

😊，And so。We're going to look at the algorithm by which you decide that and I want you to kind of remember that you can think of every neighbor as either being closer or farther from the root than you are。

 there are no ties right like you they may tie in terms of the distance but you can always break that tie because you then compare the IDs and IDs are always unique。

 so you never really end up with a tie you can always say if they have the same distance。

 the one that's closer is the one with the lower ID。😊，So to do this， each switch。Basically。

 enables the link that's along the best path to the route。

 you're definitely going to turn that one on。😊，And then every other link that's to a neighbor that's closer to the root than you are。

 you're going to disable that one， so you only have one link like pointing towards the root。

Every other。Link you have is pointing to a switch that's farther away from the root than you are。

And so you don't do anything about those onces， you let them decide because they're going to decide。

 you're going to be nearer and so they're going to make the decision about which one to enable or disable。

You also。Enable all the links to hosts。And any link that's not to a switch。

How do you know which links don't lead？To other switches。Yeah。Well。

 you don't necessarily have any static routes with you know we haven't seeed this algorithm like we do with the other one。

 so good thinking but not in this case， yeah。You never heard an advertisement from there， right。

 because they're not participating in the Spning T protocol because they're a host。All right。

 so we'll do an example here， so here's a little topology。

 we're going to have these gray dash links for unknown or like indeterminate links。

 we're going to use black for when they're enabled and red messy links for when they're disabled。😊。

S1 is going to be the root here， right， lowest ID。So from S one's perspective。This link here。

Enabled or disabled。Thumbs up， enabled。I see some thumbs up Yeah， it's enabled， right。

 this is along the best path to the route。😊，Nope， sorry， what am I thinking。

 I was thinking from S2's perspective， which is not what it says。 So this link S1 S2。😊。

From S1's perspective this is pointing away from the root right。

 like S2 is farther from the root because S1 is the root route。

 every link is going to be farther away right so it's going to be in this unknown indeterminate state right we're not going to decide on links that are pointing to routers that are farther away from where are。

😊，All right， so what about this one？Enabled disabled。Yeah， disabled， right。

 like it's the exact same thing as the other one， like this is not towards the root。😊，All right。

 S2's perspective， this is what I was thinking last time， so what about this link enabled？😊，Enables。

 right？Becauseuse。Because this is on the best path from S2 to the root。How about this one？Right。No。

 right， like we're not going to deal with that one because it's pointing to one that's farther away。

How about this one？So right like this one is the same distance away from the root。😊。

But it's got a higher ID。So it's pointing away， so we're not going to decide on this one either。

S4 is the same distance。Like the distance that S4 advertised is the same distance， right？

Exlorra is not advertising the route。We're going to assume that they actually know who the root is。

 where they've already figured out who the root is， so it does know who the root is， sorry。

So this one。This link from S3 to S2。A。Yeah， right。😊，You know， it's closer to the root than S4。

 I mean， S4 is also closer to the root， right？😊，We've broken the tie between S2 and S4。

 right these both kind of look like the same except we've broken the tie by going with the lowest ID。

 yes。No， you're looking at the ID of the one that gave you the advertisement。

So the one that gave you the， the root。The route。So you're looking， you know。

 like if you get an advertisementr from S2 that says， you know。

 I think the root is S1 at a distance of1 and you're going to get one that's from S4 that says I think the root is S1 with a distance of1。

 it's the two versus four that breaks the tie。😊，So that one is enabled。This one here。You know。

 it's also closer than S3 is， but it's not on the shortest path， so we disable this one too， or yeah。

 this one we disable。😊，All right， this one here。It然。Is it on the shortest path from？

As forward to the route。It is， right？Yeah。Yeah， so from S3's perspective， right。

 both like if you look at distances like you know， pure distances。

 S2 and S4 are both sort of telling you that they're like one hop away from the root， right？😊。

AhFrom S2 is perspective to SparR， sorry。😊，Where is that？Yeah， S2's perspective to S4。

So in that case。Right。S 2。And。Yeah， so S4 is the same distance。As S2。They both are one hop。

But we're going to say it's farther because we break the tie， we're saying S4。Is greater than S2。

Therefore， we decide that it's on the far side。W反 don。Not through this path， right。

 S 4 is talking about from its perspective， like it。It has heard the advertisement from S1。

 also directly from S1。So S4 knows that it's one hop from S1。

We're assuming that they've all actually figured out who the roots are。Prices， why wouldn？外国证。They。

Is a tie break only in order to decide whether you're going to disable this link or not？

Because our for the rules for disabling links are on here， and so it's like。

 you enable a link if it's on the best path。To the root？And you disable it if the other neighbor。I。

Closer。To the root than you are。But not on your best path to the route。RightAnd so this one。

If it was。You know，S1 and a half， we would consider it to be closer because it's the same distance。

But then we break the tie between them。Does that kind of make sense？Yeah。

 it's a sort of confusing algorithm， but yeah。Yes， S1 was chosen to be the root because it's the lowest ID。

All right， so from a force perspective。S1 is on the shortest path to the route。

 so it's going to be enabled。So from S4's perspective， this link S3 and S4。What do you do with it？

Is S3 closer to the root？No， it's not right， so we're going to ignore this one。

 it's already disabled， but we're just going to leave it alone。呃。S4s perspective。Yeah。Right。

 what that means is essentially data traffic should not be flowing along that link。

 so like S4 you know S3 won't forward traffic along that link， it'll instead forward to S2。😊，Yeah。

 so what about S4 to S2， is that the shortest path to the route？No， right。

 that was through S1 directly is S2 closer to the root than S4 is。Yes， right？Same number of hops。

But smaller ID， so it's closer to the root。So what do you do with this one？Enable， disabled。Yeah。

 you disable this， right？😊，And so now you take these links that everybody has disabled。

And remove them and you get this spanning tree。Yeah。个 same没。全です。我开始时。

To assume that sending to yourself。Yeah， so you're not actually considering like the distance as if you sent to them。

 you're just considering。Where they are forward or behind you in this sort of like absolute order。

啊说实的。I觉得那。U。Yes， I mean， that's true if you were to send through there。

 but you're not actually sending to them， right， you're just deciding which links to disable or disable。

So you can just go by whether what their distance is from the root versus your distance from the route。

That so for。我。Back there。It's got a lower ID， so it's towards the root。

But it's not on the best path to the route。So you enable the one that's on the best path and you dissit。

They're trying to find the。In this case we're assuming that they've already they've decided。

 they've already come up with what is I mean that's just distance spectra essentially right。

 they've already decided what the best path is now we're just trying to figure out which links we're enabling and which ones we're disabling。

That's kind of a separate part of the problem the first part over just sharing the updates telling them advertising。

 et cetera， right that's the normal distance vector part。

 this part is the second stage where we're taking that information that we got and we are deciding which links to enable and disable。

最条的白。Well， so like if you're at S2， right？Then。The best path to the route。Is also doesn't include S3。

So if you just use the thing of I'm only going to disable things that are on the best path。

Then S2 would say， okay， well， S3 isn't on the best path either， so I'm going to disable that。

But you don't want to disable that because that link actually is useful， right？😊。

Because S3 needs that link。Does that kind of make sense？Other question？Yeah。Yeah， so essentially。😊。

You know， from a given switchess perspective， it's only going to decide on ones that are closer to the root than it is。

And it's going to leave the other ones。It's not going to make a decision on those ones。

 the ones that are further away will make a decision on those ones。So like from S2's perspective。

 this link to S3。It's not its responsibility because S3 is farther away from the root than it is。

Right。Yeah， it doesn't even have to mark as unknown， it doesn't do anything。 I mean。

 it actually it leaves it enabled and then lets it be S3's responsibility to disable it。

At what stage does？What good do they？At S3 and S4， I mean， they're doing it kind of on their own。

RightLike they're deciding on this asynchronously， so just whenever you know they have there's actually essentially a timer where after they figure out the paths that they think are the paths to the root。

 they essentially say okay， I've now believed this to be true for a few seconds。

 you know that this is the best path to the root， et cetera。

 and then after that goes off then they disable the links that they're going to disable。😊。

Kind of makes sense？嗯。You can come to office hours， we can discuss it to your heart's content。

All right。I going to move on to step three here， which was when a tree breaks when a link fails。

 you start over and so basically when your route expires。

 like when you haven't heard a Sp tree message from the root for a while。

 then basically you just pretend you're the route again。😊，Advertiisees if you were the root again。

And this basically will just start， you know， like another process of trying to converge and find the route everybody will tell their neighbors and you will hopefully find new links to enable and dis to get a new tree。

So to sort of sum this up， Spry protocolcol is basically distance vectoror。

 except you're always figuring out like the route to a single switch。

 which is the switch with the lowest ID and you don't use those roots that you found directly。

 instead you use them to figure out which links to enable or disable。😊，And after disabling links。

 your topology is logically a tree， and your learning switches can flood freely on that tree。

 not having to worry about there being loops。😊，So。Spanture protocolcol learning switches are generally only used in layer two networks。

 in layer two local networks bandwidth is usually plentiful。

 the number of nodes that you have to deal with are relatively small。

 so flood is feasible right you wouldn't want to flood on the entire internet。😊。

Flooding lets you reach destinations like without having routing information at all。

 right you actually don't need to have any table entries in order to reach from one host to another。

 but they're nice right because they let you take direct paths and not use links that you don't need to use to get from one place to another。

😊，Floodding lets you sort of find hosts， you don't need to have state these the statically configured routes。

 because if you flood and the host is out there， the packet will reach it one way or another。😊。

And finally， once a switch is seen a packet from a host， it has a table entry for it。

 right because it's a learned one， and if all switches see a packet from a host。

 then there's not going to be any need to flood anymore。😊，Any questions on Spanish protocol？Yeah。

So what if some switches think that you need to？Find a new tree and others don't Yeah so it basically works out right I mean when we're looking at distance vector it's this like really asynchronous protocol right like if you kind of you know have if you reset a switch in the middle of a distance vector network。

 you it'll send updates to its neighbors and it'll get updates from its neighbors and eventually they will sort out you a new path so you can certainly have points of like where you need to converge in spanning tree protocol where different switches have different ideas but as we saw the distance vector algorithm and as you'll see in the project with any luck。

 this sort of distance vector approach does eventually stabilize on the correct answer。😊，Yeah。

So in this we're assuming that we know the root， but I mean we're just making one up essentially right like how it's decided isn't important and so in this inspector you have a destination have however many destinations you essentially have like static routes or other routes that are propagating hopefully like one for every host or something that will cover every host and in this you only just have the one。

 but it doesn't really matter because you don't really care about forwarding to any particular node all you care about is that you're only forwarding on a tree right？

😊，The actual destination。Is irrelevant？You don't even necessarily forward following the path to that destination。

 you forward following the paths that you've learned。

We just needed to have one node that we decided was going to be the root of this tree。Yeah。

Is there always the smallest idea by default， yes， it can be overridden， but in general。

 that's the way that it's found。Yeah。第二。How does that happen。

 So everybody starts thinking they're the root。 And then somehow we end up narrowing it down and finding the one that's actually the root。

 right， And the way is basically， it looks very much like the distance vector update when you get an advertisement。

 they tell you what they think the route is。And you compare it to what you think the root is。

And if what they said is lower than yours。Then you use theirs， if it's higher than yours。

 then you stick with yours。Yeahや。Yeah。Right so the example we started knowing the route and I guess I should have been clear about this。

 we started partway through right there's there's two stages to this algorithm well I mean there's actually three right but the first part was we find the least cost paths from every switch to the root right that's the first part of spanning tree protocol and this is the part that's like just like distance vector right。

😊，Where just find what these are。The second part is where you disable the links that aren't on those shortest paths。

 And so the examples that I were doing。That I was doing were examples of a second part there once you know once you've already spread this information around。

 you found what your next top is on the path， how do you know which links to enable or disable and so that's what this was an example of is that second part where we've already figured out our best paths we're just figuring out which links to enable or disable。

Does that maybe clear some things up， I think you were not the only one with this misunderstanding。

 so am I that， yeah？they can definitely be meshing over。 I mean。

 they're certainly not synchronized between different switches， right， Yeah， so the actual way。

 there are actually like a few states that they go in。😊，You know。

 right now I'm just trying to decide what my paths are and then after it does that for a while。

 then it switches to another state where it's going to enable or disable things so it's a little bit tricky but not super important。

 but they can happen at once， certainly across different switches。Yeah。Why would you use？Yeah。

 so why would you use not a minimum spanning tree and so what's the difference between the two？😊。

Yeah， so if you have edges that actually have weights right， then you can choose a minimum fan tree。

 if you don't have edge weights， then the two are equivalent。

 right every spanning tree is a minimum spanning tree。

 and so in the original version of spanning tree， it didn't include weights。

 modern versions actually do but we were kind of ignoring them。😊。

So the modern versions do actually come up with。Not necessarily a minimum spanning tree。

 I think they do find least cost paths to the root。

 but I believe it's been a while since I thought about this。

 but I think to have a minimum spanish tree you actually need to choose the root well right and in this we don't have any algorithm for figuring out what the best possible route is we pick the root kind of at random and then can just get the best path at that route so that's kind of I think the answer is we don't have a good way of figuring out what the ideal route is。

All right， I'm going to move on from。From this。Questions on Piazza office hours。All right。

 final thing about Sp Te protocol Sp Te Pro protocolto was invented by a Rad Perman who also worked on ISIS which is one of the Li state protocols that we talked about and she tells this story about the development of Spanishry Pro which goes something like this her company needed a solution to the problem of loops in its network you know the problem they were kind of facing was you know it's really easy for an operator just like plug in a cable in the wrong place and create a loop in the network and bring down the network right and they were struggling with figuring out this so her boss gave her the problem on like a Friday before he was going out of town for a week he says I'm going out of time why don't you take a crack at this problem and so she solved the problem over the weekend。

😊，So the whole next week her boss was gone， and so she spent the entire time writing up the algorithm in the form of a poem。

 or as she calls italgarrime。And so it goes something like。

 I think that I shall never see a graph more lovely than a tree。

 a tree whose crucial property is loopfr connectivity。

 a tree that must be sure to span so packets can reach every land。😊，First。

 the root must be selected by ID， it is elected， least cost paths from root are traced in the tree。

 these paths are placed， a mesh is made by folks like me， then bridges find a spanning tree。😊。

So radiopromon's alerime， know Leon was referring to an L2 network， mesh。

 she was talking about a network with a high degree of connectivity， lots of loops。

 and a bridge is sort of a dated term for a switch。😊，Spanish T tree protocol。All right。

 moving on to addressing。😊，I'll also talk a little bit about how interior gateway protocols and exterior gateway protocols interplay。

 All right， So a number of people asked this question。

How do routing and forwarding scale to the size of internet。

 you know like can you actually have a table entry for every host and how long would it take distance specor to converge when it's sending all these messages and has to deal with speed of light delays and can a Lake state router really build a graph of the entire network to run Dyexster's algorithm on and how long would it take to run Dyexster's algorithm on a graph of the entire internet right？

et cetera， et cetera and so you know I've mentioned that Intro domainomain and In domainin routing protocols use different algorithms and work kind of differently and we've mostly talked about intro domain so far。

 so you know maybe the magic of routing， maybe the exterior gateway protocols that do routing at the level of the internet have some magic。

 they scale much better for some reason。😊，But it turns out that the magic of scaling is actually mostly in addressing。

😊，So we're going to talk about addressing and specifically about IP version 4 addressing IPV6 is pretty similar。

 I' not going to talk about it too much in this class and without talking too much about the details of BGP。

 we're also going to talk a little bit about how and interdomain routing interact。

 at least conceptually， I'm not going to say anything about L2 addresses today。😊，All right。

 so starting with a little internet history and this is a bit simplified but I'm hoping to get the basic points across。

 remember the internet is a network of networks right so like here we see that network of networks。

 you know the internet。😊，And here we can see the internet networks too right。

 you know sometimes we call these individual networks domains or autonomous systems。

 and so note that this really naturally leads to this sort of two-lel hierarchy right and hierarchy is one of our major tools to address issues of scaling in CS and in routing but like in everything。

😊，So one can imagine a scheme like this where every host has an identifier。

 and that's pretty similar to everything we've been looking at so far， right。

 the host has a unique identifier。😊，But networks also have identifiers。

And so an address could look something like network dot。Host。So like this host here。

 you could say it was 37， right， it's in this network3 and it's the seventh host and the one next to it could be 3。

6。😊，And so thinking through the implications for routing here。😊。

The border routers doing interd routing don't need to know anything about host addresses。

 They only need to know about how to reach the other networks。

And so this limits like the number of table entries used for forwarding， right like at R9。At R9。

 everything going to an address starting in four goes to R6。Like the star is like a wild card。

 so anything4 dot， whatever goes to R6。And this also limits like whatever other routing state you might need。

 right like if we don't use Li state at the inter domain level， but if we did。

 we wouldn't need a graph including every host， we just need a graph including these domains。

This also limits churnern， right， if a link goes down in some domain。

The inter domain routing doesn't necessarily need to know anything about it， right。

 It doesn't change how the routing between the domains is done。

So like the number of routing messages that you care about goes down， this also helps you scale。

 right？So。If you assume。That there are many more hosts than networks。

 Then this is a big improvement on scaling。So what about the internal routers？Well。

 they need routes for all the hosts in the same network， right？So like looking at R4 here。

 it needs to have routes for 3，1，3，2， 3，3， et cetera， right？😊。

So this scales with the number of hosts in the network。And it needs to have those routes。

 those routes， to other networks， right， like if R4 gets a packet to like 1。6。

 it's going to need to know something to do with that packet。

But all it needs to know is send it to R9。So。How does that happen？

And we've talked about how know we sort of seed our distance vector in Li state protocol with like static routes。

 right？But these are the routes that we care about。

 right these are the same routes that the interdomain protocol got that tells us how to get to another domain。

 right？So essentially we can use those to seed the routing table at R9 with those intradomain routes and then the intra domainomain routing protocol distributes them the same way we distribute any route in the interior gateway protocol right。

 the same way we would have distributed static routes， those will propagate telling you， oh okay。

 well they started at R9 and so they'll learn that the best path is back through R9。😊。

So that lets us create table entries for the one， two and four networks throughout our three。

 so does that make sense when I'm saying about about how these interact。

A9 is communicating with other exterior border routers。

 figuring out what the inter domain route should be。

And then it's basically using the interior gateway protocol to propagate those to all the routers inside network three here。

All right。So also note that you know R9 is also doing internal routing right it's going to get packets from outside that are going to go to one of these you know 3。

1 or 3。2， so it also needs to have routes for you the other hosts inside R3， I just didn't show them。

So the total state scales with the number of hosts in this network， right。

 we don't know anything specifically about hosts and other networks。😊，Plus。

The number of other networks。Does that make sense as a starting point here？

So a final note on this is you know， you actually for this network。

 you don't even need to know about the individual routes to the other networks。

 in this case there's only one way to get to any network besides three。

 and so you could have a default route that just matches on anything and says if you don't match one of these3 do whatever ones。

 then you're definitely just going to head to R9 and leave this domain， go somewhere else。😊，嗯。R9。

 of course， still does need to have those routes for all the different networks。

Because it needs to know， is it sending them to R6 or R8 in this example？

So does that kind of make sense what's going on there with this kind of two levels of routing。

 you're routing between networks， I then you're routing between hosts within each network。

 and the two are getting kind of spliced together。U。

So I want to point out here the addresses aren't assigned totally randomly right there's a structure to how we're assigning addresses。

 all the hosts that are in some sense close to each other on the same network。

Their addresses all share something too。 They all share the same network part of the address。

 and we're leveraging the structure in order to make routing and forwarding scale better。嗯。

We do this sort of thing all the time we use these structured addresses right like Soda Hall 417 is a much easier way to work with you know my office number than like if every office just had like a unique number and I said oh。

 I'm an office 982 million403 and you're like okay。

 where is that that in this state I have no idea right so you have this sort of two levels of addressing there。

😊，This also explains why hosts don't generally participate in routing protocols because a human had to decide how to allocate these networks。

 how these things grouped together， so they had to type in at some point， how that worked。

 your computer doesn't have an IP address that follows it around， wherever you move your computer。

 instead when you move your computer to a different network。

 it changes its address to network to an address in that network。😊，So it's sort of like， you know。

 when you move apartments。Your address doesn't go with you。

 you switch to the address where you moved。嗯。So the way that that happens automatically in IP is through a protocol called DHCP that we're going to talk about later in the semester。

😊，So to recap here， we're assuming that addresses have two parts， a network part and a host part。

 and the board of routers run an EGP routing protocol to figure out the routes between networks。

And the internal routers are running IGPs to figure out the host routes for the hosts in that network。

 and also to propagate the network routes that it learned from the EGP。

This scales a whole lot better than flat routing， you know the border routers don't see the churn inside all the networks。

 the internal routers don't see the churn in other networks。

And routers only need state for the hosts in their network。And for other networks themselves。

 not the hosts in them。 Does that make sense？Ths up， kind of makes sense。Thumbs down in。All right。

So that's basically how addresses worked in the early internet。😊。

I want to before we dig into how things have sort of evolved。

 just take a step to look at IP addresses themselves in a bit of detail and so first off they're 32 bits long。

 every host has a unique one at a particular time more or less in the early internet。

 those 32 bits were broken into an eight bit host part。

 an  eight bit network part and a 24 bit host part， they were always broken down like that。

 and when an organization wanted to get on the internet， they would get their own network part。

 for example， Apple got 17 and that's still true today， any IP address starting with 17 is Apple。😊。

So this is all still true right here， they're still 32 bits long。😊。

This stuff has gotten a little bit more complicated。AndWe'll talk about that in a second。

 but first let's just talk about how your right IP addresses。

And so you could have just represented them as like a big old integer it's just a 32 bit number and in fact on a lot of systems you can still do this。

 you can know p or open a web browser and just enter a number and it'll work but it's much more common to write them in this form that we call a dotted quad or a dot quad and basically you just take each of the four bytes in this address。

 you convert it to decimal。😊，You throw dots between the four of them。

And that's what an IP address looks like。You know in the old internet。

 this one would always be the network part， the rest would always be the host part right。

 and so like I said， if they start with 17， they are still to this day Apple。😊，U。And you can in fact。

 write them also with one dot。 this is a weird way to do it， but you can do it。

 you can write like a network number and then a dot， and then just a 24 bit number。嗯。All right。So。

Think about how this has evolved， you may have noticed that only  eight bits were allocated to the network part。

 So how many possible networks could there be？😊，256。So like， you know？

256 networks that I guess that seemed like enough at the time。I think they were probably your wrong。

So it became clear that we needed more networks pretty early on。😊。

And so what they did was invent class addressing， and so basically it breaks up the bits and the address in different ways。

 depending on the prefix here， so like every address where the top bit is a zero。😊。

The top eight bits， including that zero， so seven more bits。Or the network number。

And luckily when they made this up， they hadn't gotten to network numbers like higher than 127。

 so all of the old ones still work， that's why Apple got 17 and still 17 or why that's possible anyway。

😊，That you have this essentially8 bit network number and then 24 bits worth of hosts。

 so you have 126 networks， they each have about 16 million hosts。

Class B is any address where the first two bits are 10。

And so the rest of that is the network part and so you end up with about 16。

000 networks and they all have about 65，000 hosts and Class C， if it starts with 110。

 then the rest of the first 24 bits are the network number after that is the hosts。

 so you have about 2 million networks that have about 254 hosts each 254， not  not 256 because。😊。

The zero， like all the bits zero， all the bets one， those are reserved for different reasons。

 so it's always like you know when you have a network of some size。

 you subtract two to find the actual number of hosts you could have。

So now we have a lot more network numbers available right there's like over 2 million here right there's 2 million just of the class C networks and then you've got the other ones there are some other classes too but these are the three big ones so when an organization wanted to get on internet they basically figure out how many hosts they think they're going to need and then they get a network number that's sort of like appropriate to their needs right to one of these sizes。

😊，This plan ran into problem with its own。So the first one is that the size of the classes。

 they're nice， they follow in these like light boundaries， right， that's nice。

 it makes them easy to read， but like they're not super useful sizes， right， class A。😊。

We got 16 million hosts， right， like not a whole lot of organizations have 16 million hosts， right？😊。

Class C， on the other hand， is like way too small for a lot of organizations。

 right it's only got 256 hosts， right， There's probably 256 hosts in this room。😊，So you know。

 the best option for a lot of people was Class B， and there aren't that many class B networks， right。

 There's only like 16000。😊，So it's sort of the way they broke this up。Was not great。And。

There's another thing here， the second problem is sort of hinted at by the fact that they were worried about running out of Class B networks。

😊，The fact that they were worried about running out of ClassB networks implies that they were getting close to having 16。

000 networks right so at the inter domain level， the inter domainoma routing。😊。

You were routing with tables of like 16，000 entries。

 and this was starting to be taxing for the routers of the day and the whole point of the way we broke up addresses was to make the interdomain routing table smaller and they were certainly smaller。

 but they were getting too big。Number of interdamine routes was going up。

And so this was really happening， a graph of the growth of interdomain routes by year looked something like this between 89 and 94。

 so it was growing， it was growing super linearly right， like look at 1993。

 it almost doubled just in the year 1993 here。😊，And look at where it ended up at like 15000 ish。

 right。 Remember， there were 16000 class B networks。 So if most of these were class B networks。

 then we'd already spent most of them。And of course， if we run out of class B networks。

 what are we going to do for an organization that needs more hosts。

 we're going to give it a whole bunch of class C networks。

 right that's how we're going to make up for that yeah。😊，あせ。被二康。あせたです。They are networkable based。少点。

How you。Thank to。The addresses are all the same length。 So the question is， how do you， I guess。

 interact with ones with different ones， The addresses are all the same length。

It's just how many bits you use for the network part， right？So basically。

 if you have a address that starts with a zero， right。

 then its network number has to be less than 128， right。

 in order to fit in that remaining seven bits。And so networks like that。😊，Have。

24 bits worth of hosts。So you can just tell by looking at this address how many what the network number is and what the host part is。

 the bits associated with the hosts。好。Well， I don't know if everybody would optimally want class A right。

 I mean it doesn't really matter， what matters is do they have enough do their hosts fill it right I mean what you really want is you want to probably choose the you want to conserve the bits sort of right if I have 10 hosts in my company。

Then giving me a class A would be a huge waste， right？

There are roughly 60 million hosts will fit in a class A network。 and I'm going to use 10 of them。

Nobody's going to use the others， So you would much rather give me a class C。Network。

I'm not sure that's answering your question， but I think you'll have to wait till next time or office hours or something because I think。

 no， we still got time。Yeah， so is that answering your question。

 I'm not positive Im understanding the question。Yeah so。这地。So。It's really just a number。I mean。

 all the addresses are 32 bits。It's just how do you want to break up the bits between a host part？

And the network part。Right。嗯。If you。One solution to this problem would have been say。

 you know if we made。Addresses 256 Bs， right， then。128 bits of the address could be for the network。

 128 bits could be for the host。Like surely that's enough for the number of networks that you could possibly have and the number of hosts that you could possibly have。

 if you had that many bits。To work with。Is that believable？

Like 128 bits gets you like the number of atoms in the universe or something like that right you're not going to fill up that many hosts or that many networks right so if you had if you wanted to spend the bits。

 you just have a giant number for the network， giant number for the hosts right but they didn't want to do that instead they had 32 bits to work with。

😊，And so you know sort of what they did is they started with this sort of static thing and they said okay8 bits。

8 bit host number， 24248 bit network number， 24 bit host number right。

 so that was where they started， but what they found was well that's not enough bits for。😊。

For the number of networks we have right， so they could have said， well okay。

 we got it wrong instead we're going to have 16 bits assigned to the network， 16 bits for the hosts。

 right？But well， now we only have 65，000 possible networks and each network can only have 65。

000 hosts， right？😊，Like and if we have some network that only has two hosts。

 then we've just wasted almost 65，000 addresses， right？

And some network is probably going to want to have more than 65，000 hosts。

 so this was an attempt to sort of say ah well， some networks are going to be one size。

 other networks are going to be another size， other networks are going to be another size still。

 and so we've just sort of broken up the space。😊，So that the network number sort of determines which of those classes of address you have。

 the low network numbers are going to say you have a lot of hosts， the medium ones are going to say。

 you have this intermediate number of hosts and the large。

The large network numbers are associated with a smaller number of hosts。Does that kind of make sense？

O看。If it doesn't， we'll come back to it， let's talk about in office hours。

Or everybody complain on Piazza and we will go through it all right。😊，So。Where were we here？

So they needed a new solution here， right because of the problems with。😊。

These two problems with classical addressing。And so that was this thing cider。

 which is classless interdomain routing and this is still what we used today。

 this is what we've used since the early mid-90s and it solved both of these problems the same way by doing two things。

 and so first of all， it introduced this hierarchical process for the assignment of addresses and secondly it gives up on this simple notion between like a static assignment between the number of network bits and the number of host bits。

😊，So starting with this hierarchical assignment of addresses， you know like I mentioned earlier。

 it used to be that when you wanted to get your organization on internet。

 you would go to ICN or at the time it was probably Aana。

 ICN is the Internet corporation for assigned names and numbers。

 Aana was a sort of its predecessor sort of， which is the Internet assigned numbers authority and they're the people who kind of are in charge of addresses and port number assignments and that sort of thing and so if you want to get your organization on internet you would go to them and say I want a network number and they would say。

 okay， here's a network number。And so。Under cider， this got delegated in this hierarchical way。

So it started with ICN taking a bunch of the unused Class C networks。

 a bunch of the contiguous IP address space。And giving them to these organizations called RIRs or regional Internet registries。

 and so there were five of them， I think theres still five of them， Aaron is the American one。

 and they are responsible for IP address assignment in mostly the US and Canada， Aroic is Africa。

 Apnek is Asia Pacific， Lachnni is Latin America and the Caribbean， and Re is like everybody else。

 So Europe， Russia。😊，The rest of Asia。And so I can give some big chunk of IP addresses to them。😊。

And then they give out portions of those big chunks。To large organizations like ISPs。

And those organizations give out chunks to smaller organizations。

 so like AATT&T might give out some chunk of their addresses to UC Berkeley。😊。

So running through an example here of how this might work and this is completely made up。

 these numbers are definitely wrong， but just to kind of show you how it works。

 we'd say I can decide that the US and Canada should have 5 million addresses。

 so they need to give them 28 bits to get up to 500 million， right？😊。

So ICN chooses the remaining four bits， with the top four bits of the address as a prefix。😊。

And they say1101， I'm going to give that to Aaron who is in charge of addresses for US and Canada。

 says every address you allocate is's going to start with 1101。😊。

And Aaron then is responsible for delegating stuff to companies in North America like AT&T。

 and so maybe AT&T wants8 million of these addresses。😊，So that requires 23 bits。So Aaron picks。

Five more bits for the prefix。And so any address starting with 1101。

11001 is going to be an AT&T address。😊，And AT&T might allocate 16，000 addresses to UC Berkeley。

That's required four， 14 bits， so AT&T picks the next nine bits of the prefix。😊。

And then it gives those to UCB and Berkeley now has its own block with a prefix of 18 bits and the remaining 14 bits it can use to assign to hosts。

 so every host at Berkeley would start with this prefix of 18 specific bits。😊，That makes sense。

Each one of these below is sort of a subset， it's a part of the space of the one above it。

These are inconvenient to write out in binary as a binary prefix and so we often use this notation。

 which is sort of a variation of dotted quad and so to do it。

 you just pad the rest of it with zero so you have another 32 bit number， like an IP address。😊。

And then you convert it to a dotted quad， which I've done for each of these。

Another problem is that from these just dotted quad， you can't tell like how long is the prefix。

 right？And so we use what's called slash notation where we just write slash and then how long the prefix is。

And so now you know， this is what this prefix is actually referring to， right。

 it's these bits and's this number of them are significant。😊，Does that make sense？

Each of these allocations is contained in the one above。So besides slash notation。

 there's this other notation， net mask notation。😊，Which is totally equivalent it's just a different way of writing it and so it's basically a bitm of the prefix bits so you just turn the prefix bits into one and then convert it to a dot quad so using the same ones from before 1101 this was the prefix we just turned all the prefix bits into one convert that into a dot quad and we get。

😊，240。0。0。0， and you just put a slash and put that after the dot quad of the network address。

 and that tells you the same information， right It's just a different way of writing it。

And so we can do that。With all the rest of these two。That makes sense。Everyrebody clear on this。

All right， then with that， I think we will resume here next time。



![](img/58bfda3304fab1c7d24d24fcf23b51a3_1.png)

![](img/58bfda3304fab1c7d24d24fcf23b51a3_2.png)

The date's that beautiful for perfect aesthetic for。Sorry number。Sorry。



![](img/58bfda3304fab1c7d24d24fcf23b51a3_4.png)