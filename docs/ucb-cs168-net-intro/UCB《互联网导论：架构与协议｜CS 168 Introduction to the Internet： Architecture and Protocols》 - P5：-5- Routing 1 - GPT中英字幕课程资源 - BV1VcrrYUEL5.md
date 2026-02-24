# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P5：-5- Routing 1 - GPT中英字幕课程资源 - BV1VcrrYUEL5

So。The actual subject for today is to get us started talking about one of these fundamental problems in networking。

 which Sylvia mentioned， which is routing。😊，So sort of you know setting the scene the game plan for today。

 we'll see how this actually works， I'm going to start out sort of setting the scene with a quick disclaimer。

 a quick statement on addresses， then I'll talk a little bit about what is a router。

 I'll talk a little bit about you know why we have routers at all，😊。

I'm going to then sort of present like the challenge of routing and then the challenge of forwarding。

Then I'm going to sort of compare and contrast the two of those。

Then going to get a little bit into theory， we're going to talk about sort of a graph representation of routing。

 we're going to talk about this notion of routing validity。

 and then we will see how to actually use that notion of ability to validate routing state。😊。

And then we will probably end up with this in class activity。

So the disclaimer here is that there are about a billion ways to do routing and I'm going to sort of constrain our initial discussion today to sort of like how the archetypal internet works。

 I'm going to make a lot of assumptions based on this and you know next week we'll talk about some alternatives。

😊，So if you cast your mind back to the salad days of two weeks ago。

 we talked about packet headers and we said that a packet header must contain a specific field。

 Does anyone remember what field we said packet header must contain。Yeah。

The destination Ip or more generally a destination address and so。

I think one can actually argue that you could build a network where this isn't true。

 but it's true for every networking technology I could easily think of。

 and it's certainly true of the internet。And I'm not sure that we've outrightstate this before。

 but this sort of implies that hosts have addresses thinking back to Sylvia's example with CEOs delivering letters。

 you know this CEOs had some address associated with them or like one infinite loop in Cupertino for Tim Cook or one hacker Way in Menlo Park for Marcus Zuckerberg。

 and in fact hosts might have more than one address。

 so why is that why might a host have more than one address？😊，Yeah。What was the second part？Yeah。

 so anybody else have another reason？😊，Yeah。MultipMultiple servers。那个安应该さ。在这。

So I think you're onto something though I might say it a little bit differently and so the sort of two reasons I think I'm interpreting kind of what you're getting at correctly。

 so one of them was that you might have different addresses for different layers like your cell phone or just any computer might have like an ethernet address on L2 local address and it might have an L3 IP address。

 a global address， so it might have addresses at different layers。

 the other one is I think what we were getting it over here which is you might be connected to multiple networks and you might have a different address on both of those networks。

 for example your phone you might be connected by Wi-fi and by cellular and each of those connections might have a different address。

😊，So。For now though， and for much of our discussion on routing。

 we'll be thinking a little bit more abstractly， so we'll just think of a host as having you know a single sort of abstract address。

 we'll get into some sort of technical details of addressing next week。

 but for now you know I'll probably draw hosts。😊，Something like this and say that a host drawn like this has the address F。

So moving on， let's ask a pretty basic question which is what is a router。

 there's a bunch of different ways to answer this question。

 you know again casting our minds back to lecture one。

 you know we had a diagram that looked something like this。😊。

And I had this thing labeled switch on it， as Sylvia has talked about when she and I say switch。

 we often kind of interchangeably with router， and so this thing is a router。

 a router is sort of an intermediary node that usually connects to multiple neighbors。😊。

From a very different perspective。😊，In this class， a router is often this。Sometimes it's this。

 we're probably not going to be 100% consistent， but it should be clear from the context。😊。

If you were to ask a network engineer what a router is， they might tell you that it's this。

 This is the schematic symbol that network engineers use to represent a router。Many of you。

 perhaps all of you are familiar with this being a router， a home Wifi router。This is also a router。

 this is a 24 port Cisco catalysts。😊，And this is a 96 port Cisco catalyst and so these two things are the kinds of things you might find somewhere in a campus network or maybe in a wiring closet somewhere the previous one looks a lot like what a lot of what are called top of rack switches in data centers look like and you know the big obvious distinction between these last two is the number of ports they have right each of these little holes is a place where you can plug in a cable or when we think about that logically it's a place where a link can exist right so this one supports a lot more links than the previous one。

😊，Another note is that these last two in particular。

 a lot of people would tell you that these are a switch， but they do routing。

 so I'm going to say they are also a router， so again。

 the distinction between the two is not really all that clear。😊，Another one。

 here's a thing called a Cisco CRS1 and it's like' it's called the carrier routing system and this is the kind of thing that you might find in a major ISP。

 and so these things are big， this is taller than I am， it can support many links。

 very high bandwidth links and so on。😊，So you know there are a lot of different kinds of actual routers。

 again， in this class to us， they're mostly just squares。😊，嗯。So。Any questions on those？So。Moving on。

 we have this question like why do we have routers at all， and maybe this ends up being obvious。

 but I thought we could sort of quickly just sort of think through a couple of the reasons。

So if you've got a couple hosts and you want to send data between them。

It's pretty easy to just put a cable between them and now A and B can directly communicate。

If you've got more hosts， though， what are you going to do。

 you could sort of continue that same pattern and just put a link between every host。

 and now everybody can directly communicate with everybody else。So is there a problem with this？Yeah。

It doesn't scale very well， why not？Yeah， like every time you add something there's a lot of work right。

 like there's a couple reasons to can think about why this doesn't scale， right like you know。

 for every host。Like in the network， there's that many hosts minus one links that exist in that network right so I mean first of all that doesn't probably scale to your home or your apartment right there's billions of devices on the internet you probably don't have room for all the cable in your house。

😊，You know， also anytime anybody added a new host right somebody would need to go to everybody's house and like hook up the new cable right so this obviously doesn't scale too well and also you know like most of these links would probably be idle most of the time right I mean。

 do you communicate with every single other host on the internet？

Are there any positives to this sort of design though？Yeah。Yeah。

 so connections are direct and low latency and not just the latency， even more like the bandwidth。

 right， you've got like dedicated bandwidth to everybody， so that's nice。😊。

Another thing is it's pretty robust， right， like if this link between A and B fails。

None of the other links are affected， right all the other pairs of hosts can still communicate just fine。

So if the scale is small and the need for your performance is great， this design might make sense。

Another way you could think about doing it is something like this where all the hosts are sharing like literally the same wire。

 So anything good or bad about this approach。Yeah。Yeah， so in some sense， it scales really well。

 right， like connecting a new host just means adding a little bit more wire， Any else。

 anything good or bad about this approach。Yeah。Yeah， so in some sense it's not very robust， right。

 like if this wire breaks anywhere， some of the hosts are going to get disconnected。

 potentially a lot。Any other thoughts good or bad about this approach？Yeah啊。Yeah。

 there could be a lot like as opposed to the other design where everybody had you know sort of like reserved link to everybody else here。

 everybody is sharing the same link， everybody's trying to fight for the same bandwidth right behind you。

 did you have know？Same thing Okay， so you know everybody's competing for the same bandwidth。

 maybe not very resistant to failures， you know， we had one argument that it scales well because you could just add a little bit more wire to add another host。

😊，It also， you maybe would say it doesn't scale to the size of the internet having just one giant wire that has to wrap around the earth and visit every single person。

So another good thing about it potentially is that maybe this is really cheap right like I mean it's just one wire。

 there's no extra nodes， there's no forking of wires。

 so you know again there are cases where maybe this makes sense。

 historically a lot of local networks have worked like this ethernet traditionally worked like this and so we may come back to this type of network a little bit in the future of this semester but you know here。

😊，We can kind of see the benefits of adding intermediate nodes to these routers， First of all。

 you know you don't need an exponential number of links， right？

You're also not trying to share a single link， so you've got sort of more bandwidth to go around。

 you know， like the traffic between A and C here doesn't affect the traffic between E and D at all。

And if a link goes down。You may be able to find alternative paths。

So this approach kind of solves some of those problems。

 and maybe you can see it as sort of like a nice middle ground。Any questions on this？All right。

 so now that we've talked about sort of the what and why of routers。

 let's start to dig into what I'll call the challenge of routing。

So the basic challenge of routing is when a packet arrives at a router。

 how does the router know where to send it next， such that it eventually gets to the intended destination？

Like if A is trying to send a packet to B on this network。

It's first going to arrive at this router R2。But should R2 send it to R1 or to r3？嗯。You know。

And when we make that sort of decision， you know we want to send the packets in a reasonable way right。

 you know using paths that are in some way good and good could mean a lot of different things。

 depending on the context， it could mean the lowest price， it could mean the fastest。

 it could mean the most reliable， it could mean not using a competitor's network。

 in some examples on Thursday， we'll think of it as the fewest number of hops in which case a path like this between C and B。

 which would work is not particularly good。And so this sort of takes some approaches off the board immediately。

 like imagine that routers know their neighboring hosts but nothing else。So then what if a router？

You know， when it gets a packet， if the host isn't directly attached。

What if it just forwarded to another router at random， another neighboring router at random？

Like that would work。Right。And it's really simple。And simple is good。

But why wouldn't you want to implement routing that way？Yeah。Well， okay， so it could get into a loop。

 but it's making a random decision every time， so would it be infinite？You know。

It's you know sort of probabilistically， you know， anybody else any other thoughts， yeah。😊，Yeah。

 yeah， so it's wasteful right like it's you sending over links it doesn't need to and just thinking about how long will it take this packet to get to its destination if you just make a random choice at every step right like who knows right。

 it could take any amount of time。😊，Similarly， you could have a router that just sent a packet to all of its neighbors and if its neighbors send it to all of their neighbors and so on and so on with a caveat that we'll get to in a future lecture that should work too right。

 so why wouldn't we want to do that？😊，Why not just send it to everybody？Yeah。

And just was the wire three quickly。Yeah， so I mean， it's。It's super wasteful， right， I mean。

 you'd end up sending the packet over every link。No matter where it's going。

 and you could probably just send it over a subset of path or of links， meaning on a path。

And so finally， like another part of this challenge is we want our routing to be able to adapt to arbitrary topologies because the graph that describes a network can vary a lot。

For example， this is sort of the topology of UUNe UUNe was a carrier network。

 meaning that it's a communications provider and specifically it was what's called a tier one provider and I think we'll probably talk about more exactly what that means later in the semester but sort of like the first order approximation it means that they're like an ISP for ISPs today they're part of Verorizon。

 but you can see you know there's a lot of links kind of messy kind of gathered around major cities。

😊，嗯。Century Link is another big ISP， and this is kind of what their North American network looks like。

😊，Berkeley is network。A little bit more structured， looks something like this。

With like residence hall over there on the left， you know various other things up at the top is how it connects to its ISPs。

Enterprise networks kind of have their own thing going on。

 they often have like a head office and several branch offices。

Data center networks often have these very regular structured topologies， something like this。

 you know these things are really engineered and they're sort of engineered without the constraints of like geography and populations and so on。

Of course， the internet as a whole is sort of a mishmash of everything， right。

 because it's like a network of all these networks。And。So you know， in all these different networks。

 we might actually use different routing algorithms。

 but it's still generally good to have a routing algorithm able to adapt to an topology。

 and this is especially true because every topology is dynamic， they all change。

And so why is that when I say that every topology changes， why is that？Yeah。Any router can go down。

 right， You always have to deal with failures， right。

 Some could put a backhoe through a link or the power could go out where a router is connected。

 anything like that， right， Another reason why， you know， I mean。

Lots of networks are dynamic you know because you might want to add equipment too right you might want to say。

 oh well we need more bandwidth here so we're going to install new links。

 we have new customers so you know we're going to have to adapt to those customers and so on。

 but you know everyone has to be dynamic because they all have to deal with failures。

So taking a step back from routing。Let's talk about one of the other challenges that routers face。

 and that's the challenge of forwarding。So。When a packet arrives， for example， at R2。So a packet。

Arrives at R2。R2 is going to forward it。To one of its neighbors， right it's going to resend it。

And so you need to decide which neighbor are you going to resend that packet to and you want to be able to make that decision fast。

 you know remember like packets can arrive on the order of nanoseconds。

 so you know this sort of implies that whatever decision making that you need to do when a packet arrives needs to be really simple。

And so almost universally， the solution to this is that these devices just use a simple table lookup。

😊，So。Here's a network， our two might have a table that looks something like this down at the bottom for every destination。

 there's a row， and in that row there's a column telling it which neighbor to use to get to that next destination that is like what the next hop is。

😊，For example， if R2 gets a packet for B or C。😊，It's going to send it to R3。Any questions on this？

All right。Now at like a low level right like eventually it's going to need to figure out like which physical port to send the packet out of right so maybe each port has a number which I've sort of drawn up here。

😊，And then you can create a table that looks like this one on the right。😊。

There's sort of practical differences between these two， right this one on the right。

 the second column is the port number to use， but logically they're pretty much equivalent。😊。

It's a lot easier to do examples using ones like the ones on the left。

 so we'll often stick to that but sort of be aware that both of these exist。So。

Note that the only thing which determines our forwarding decision in this case is the value in the destination address field of the packet header and the value in the corresponding row of the table。

 which is to say， if the tables are fixed， then only the destination field determines what happens to a packet。

So we call that destination based forwarding or destination based routing。

 and it's kind of the most basic way of doing this。

 and it's super common it's one of those sort of like archetypal internet things and we'll talk about some alternative approaches later。

 but you should think of this as the default。😊，So。Taking a step back。

 we'll look at the two things we know routers do forwarding and routing。So forwarding。

Looks at a packet's destination in the table and sends the packet。To the neighbor given in the table。

Routing on the other hand。As routers communicating with other routers in order to determine how to populate that table that you're going to use before forwarding。

 that's how that table gets set up。So forwarding is inherently local， right。

 it only involves the arriving packet and the local table。And so you， that is if a packet。😊。

For host beat shows up at some router。All you need to do is look up be the router's table。

And you know where to forward the packet。Routing， on the other hand， is inherently global。You know。

 in order to have figured out what R2's table entry for B should have been。

You need to know something that's not local to R2， right。

 you need to know where B is and B isn't local to R2。😡，So。

Sylvia mentioned this term data plane a couple lectures ago。

 and so forwarding is the primary role of the router data plane When we talk about the routers data plane。

 we're primarily talking about forwarding。The primary role of the router's control plane is routing。

 that's the primary control plane operation is figuring out these routes。And so finally。

 we can look at the time scales that these things operate on。

 and so forwarding takes place at the time scale of packet arrivals。😊。

So that might be as fast as on the order of nanoseconds。

Routing generally takes place much slower right， you only need to change these tables when something about your network changes。

So that's something like when a link fails or when a router fails， like we talked about。

 or when a router is added。So any questions on forwarding routing？Comparisons between the two。

Makes sense。Okay。So let's talk a little bit about theory。So。

We can graph the path that packets to a destination will take by if they follow the table entries。

 you know I've sort of been doing this all along， but like one possible set of table entries for paths to a from R1 and R2 would look like these right from R1 it's going to follow this red path from R2 it's going to follow this blue path and so the next top entry in the table becomes an arrow in this graph。

Notice that know because there's only one next top per destination in those tables。

 there can be only one outgoing arrow per node。If we're looking at it for a specific destination and so that means you know once paths meet。

 they're never going to split like here， you know you can see sort of two different places the paths could meet depending on what the table entries look like so in the top paths from paths 2A from R1 and R2 don't meet until R8 in the bottom they meet at R4。

But in either case， you know once those two pads to a meet。

 they're not going to diverge again because there's only one next top for packets going to A。

 so like in the bottom， it's not like one of the paths could go from R4 to R6 and the other could go to R8。

They both need to follow the same wherever it goes， does that make sense？All right。

 so the set of all paths to a destination form this directed delivery tree for that destination。

 and this tree has to cover every node， you know we want to make this assumption that a packet to somewhere can arrive at any router and willll have a way to get to the destination。

😊，And so technically speaking， this creates this oriented spanning tree rooted at the destination。

 meaning it's a spanning tree with directed edges， which all point towards the root。

A spanning tree is a new term to you， a spanning tree is a subgraph that touches every node in the original graph and forms a tree that doesn't have any cycles in it。

Any questions on this？All right， so moving on， earlier。

 I said that we wanted good paths between hosts， and the notion of goodness is flexible。

But like surely like the minimum requirement for good。

Must be that packets eventually reach their destinations， right？Anything else is definitely not good。

So it'd be useful to be able to a reason about this， and this was articulated by Scott Shanker。

 who is my advisor as routing state validity。😊，And this is a term that we use at Berkeley。

 it's not a standard term， but it's a useful one。And so in order to discuss routing state validity。

We need to distinguish between two different views of state。

And so the local routing state is just the contents of a table at any particular router by itself this can't be evaluated for its validity。

 it needs to be evaluated in terms of the global context and so all that's saying is like if I give you some routers table。

 here's R2's table。😊，Is that valid？Like will packets forwarded using this table。

 get to their destination， obviously like there's no way of knowing from just this information。

 right？So the global state is the collection of all the local state。

 it's the contents of all the tables across all the routers。

And so this is what actually determines which path this packets take across the entire network。

And we say that the global state is valid。😊，If it produces forwarding decisions that always deliver packets。

So we can think about the goal of routing protocols as computing valid state。

And eventually we're going to talk about how you actually do that。

 but just assuming that you've got some routing state。😊，You know， how can you tell if it's valid？

You know， we want a succinct correctness condition for routing， you know。

 so going to give you a second to think about you know what makes routing correct or incorrect and then I'll ask all of you what you think so take a minute。

 think about it， talk about it with the people next to you if you like。😊，And。

What is the clearest way to define correct routing？有何关注。他有交。that's hard to do。没。

Give you a few more seconds。All right， anybody？Anybody want to volunteer something they come up with？

Anyone have an idea？Too early in the morning to be dairy。All right。So。

I'll tell you how Scott articulated it。To foreshadow things。

 it turns out that for destination based forwarding。

 this is the same as saying that your RA should form this delivery tree that we talked about earlier。

 to see why Scott， at least I think it was Scott， who formalized this， came up with this theorem。

 which is a single necessary and sufficient condition for validity。😊，And so basically。

 it says that the global routing state is valid， if and only if。😊，For all destinations。

There are no dead ends。And there are no loops。So a dead end。Is when there's no next hop somewhere。

 like if a packet arrives and it's not forwarded like because there's no table entry for it。

Note that the destination doesn't forward the packet。

 but we don't count that as a dead end because it's the destination。Good thing。嗯。You know。

 other hosts are also generally going to act as dead ends because generally hosts don't forward packets。

Makes sense。A loop is when a packet cycles around the same set of nodes， you know。

 since forwarding is deterministic and it's only depending on the destination address， you know。

 if this ever happens or gets's caught in this loop。

 it's just going to stay in that basically indefinitely， right？😊。

So let's see if we can prove that this is the case， starting with the necessary part， yeah。Yes。

 if theres a power outage， then that could change things but a power outage you can consider as being a dead end right like it's going to try to send it to the one where the power has gone out and that's going to be a dead end so then this is looking at sort from the sort of theoretical perspective so you know I would say I would map your practical example of the power goes out and some router dies as being a dead end。

Does that make sense？Okay， so so the necessary part。

 it's pretty straightforward and it's basically saying you know that for state to be valid。

 it's necessary that there be no loops or dead ends， an equivalent statement。

 if you do some logic to it， I believe this is the contrapoitive says that if there are loops or dead ends。

 the packet won't reach the destination。😊，嗯。And。So you know， we can sort of show this， you know。

 if you hit a dead end before hitting the destination。

Then you're never going to reach the destination。Obviously， right？Similarly。

 if a packet gets caught in a loop， because you're just going to keep looping because it's deterministic and it's only based on the destination address which doesn't change if you get in a loop。

 you're going to stay in a loop。So that's also not going to get to the destination， right？

And we know that the destination isn't on that loop because if it was。

 it wouldn't have looped in the first place， right it would have delivered it to the destination and then stopped。

So you know， therefore it's necessary。That there be no dead ends and there be no loops。

That makes sense。Okay， so the other part is this sufficient part。

 which is a bit more tricky right and so the sufficient part says that if there are no loops or dead ends。

 that's sufficient to know that the state is valid。

 that's sufficient to know that the packet will be delivered。😊，And so proving this。

 it's a bit more subtle， but assume that they're routing state。Has no loops and has no dead ends。

So therefore we know。The packet can't hit the same node more than once。

 like it can't hit it twice because that would be a loop， and I just said， assume there are no loops。

Similarly， we know that a packet can't stop before hitting the destination because I said there were no dead ends。

 so that's violating this other assumption that we made。And so what's left？

What's left is that a packet has to just sort of keep wandering the network， hitting different nodes。

Can't hit the same one because that's a loop， so it has to just kind of keep hitting different nodes。

 but there's only a finite number of unique nodes in the network， right？

So eventually it's going to have to hit。The destination node。So therefore。

 know if there are no loops and no dead ends， then the routing state is valid。Does that make sense？

So that sort of you know， showed that you know， this simple statement of the routing state is valid。

 if there are no loops， no dead ends。You know， we've sort of proven that at this point。

 and that tells you when packets will be delivered。So。I thought now， let's see。Yeah， we've got time。

 so let's take a quick break。😊，And we'll resume in like maybe， maybe。Five minutes。

 something like that。I mean， okay。So let's get back to it。Assuming my clicker will continue working。

All right， so putting it to use verifying routing state validity。

 so now we've got this sort of simple condition to check validity， so how do we use it？😊。

A couple notes first， first of all， hosts generally do not participate in routing you know。

 in the common case， hosts have just like a single link to a single router。

And so they have this default route that sends everything to that router unless they're the destination。

 which case they don't send it at all。 So they're not very interesting。 So， you know。

 we often ignore them， except as destinations。Rers。Might be legal destinations。

 not just hosts or in addition to hosts， this sort of depends on the design of your network of your networking protocol in Internet protocol IP routers can be destinations。

 but you know how often have you ever wanted to communicate directly with a particular router right quite probably never。

So， you know， host to host communication is certainly by far more common。

 and so we're often going to ignore the routers as destinations。

 but you do want to think about routers any router。

 every router as potentially being a source for packets sent to every destination you know。

 because packets may arrive at a router in sort of unexpected ways。😊，Does that make sense？All right。

Putting our theorem to use here。We're going to focus on a single destination。

 we're going to ignore all the other hosts， we're going to assume all the other routing state。

 except the routing state to that destination。Of course， we can do this， right？It's all， they're all。

 you know， completely independent， right？ I mean， it's only dependent on your destination address and the destination address doesn't change。

 So if your destination address is。You know， E， then only table entries for E matter to you。

 you can throw away all the other ones when you're considering this。So for each router。

 you're going to mark the outgoing edge with an arrow pointing at the next top。Again。

 know there can be only one outgoing edge at each node because we're doing this destination based。

Then eliminate all of the links with no arrows。And look at what's left。

The state is valid if and only if the remaining graph is a directed delivery tree。

 which doesn't have any loops。and which all points to the destination。So remember。

 it's a spanning tree where the root is， know where all the links point towards the root。All right。

 so checking the validity of the state to A。 we've got this topology。

 we got a here in the bottom right corner。😊，So we're going to ignore all the other hosts。

And then we're going to point at the next top， so you might have table entries that describe this。

 these arrows。You're going to remove the unused links。And。Is this valid？Who thinks it's balanced？

Quite a few。 And so yeah， this is valid， right， It's a spanning tree converging on A， rooted at A。😊。

It touches every node。All the arrows。Point towards a。So here's a second example。

 you might have forwarding state table entries that describe these arrows。So you remove the edges。

And is this one valid？Anybody want to say why they think it is or is not valid？It's not。

It's not a tree， right and in the terminology of our theorem。It is a forest， you're right。

 in the terminology of our theorem， what's wrong here？Yeah。There is a dead end， right。

 this is a dead end。 It doesn't have an outgoing era。So here's another one。

We remove the links that don't have arrows。And you get this。So is this valid？Anybody。

What to volunteer。Yeah。It's not valid， right？Because there's a loop。

All these arrows just kind of a point to each other。So what about now？Yeah。There's a dead end， right。

 It looks a lot the same， except now。This nodes a dead end， it doesn't have an outgoing edge。

What about now？Valid， not valid。Anyone， yeah。So， you know it's。Does it have a dead end？

Even more fundamentally， it's got a problem。This note has two outgoing edges。

 right That's not even possible with destination based forwarding， right。You only got one next hop。

So this one can't even happen。About this， a final example is this one valid？😊，No， why not？

Because that one， yeah， it's got a dead end。 Can you fix this one？Or how could you fix this one？Yeah。

 and in fact， if it had forwarding state to any of its neighbors。

 any of them would actually work in this case， right。

 it would create a directed arrow from that dead end to any of its adjacent routers。

 any of those would make valid forwarding state。So。

Kind of summing this up it's really easy to check the validity of routing state to a particular destination right the dead ends are obvious。

 you end up with a node you know with no outgoing edge。

 so obviously that's not going to be able to reach the destination。😊。

And loops are obvious because they end up disconnected from the destination and disconnected from the whole rest of the network。

😊，So now you just need to repeat this same process for every destination。

And that tells you whether your entire global state is valid。Does that make sense。

 anybody any questions on validity？Okay， so a final note on validity is that you we've been looking at this from the perspective of destination based routing。

 this same basic rule of note loops， no dead ends， generalizes to at least any other system that does deterministic forwarding based on fixed packet headers。

 that is it's not necessarily limited to just destination based routing，😊。

It may generalize beyond that， I haven't thought about it hard enough to figure out exactly where that stops working。

 maybe Scott has。But you know， with just a little addition。

 which we'll I think talk about next week when we talk about sort of broadening beyond just destination base with just a little addition and carefully considering what actually constitutes a loop this generalizes。

And so now， unless anybody has any questions， I'm going to move on to something。Completely different。

We're going to try this activity。It may work， it may not， we'll find out。And。So here are the rules。

We're all going to work together。You are going to talk with your neighbors。

 that is the people to your left and right and in front and behind you， you know。

 I realize you're not exactly aligned so kind of figure out who you think is in front and who's behind who your neighbors are。

U。And some of you obviously won't have neighbors on all sides。

 Hopefully you have neighbors on at least one side， probably by definition。 And so everybody。

Is going to have a magic number， your own personal magic number。 Everybody's magic number。😊。

Initially is infinity。You would like to have。A magic number that is as low as possible， you know。

 you want to be number one。And so if your neighbor ever offers you a lower number than your current number。

😊，Then that's now going to be your magic number， right， a neighbor is going to give it to you。And so。

When that happens。You know， you should immediately offer。Your magic number plus one。

To your neighbors， remember， you want to be as low as possible。

 So you're going to give your neighbors one more than you have， right？So try， you know。

 remember your magic number， certainly， try to remember who gave you that number。

And so if somebody offers you the same number that you already have or offers you a greater number。

 you ignore it。😊，So I've written this up in sort of words。

 and I've written it up in sort of basically Python。And so take a second to look。

 is everybody clear on what the rules are， on what to do？😊，Yeah。get lower。Don't worry about it。

 I mean， your neighbor you're starting with infinity。

 right if anything your neighbor gives you is going to be。Going to be better than that， right？

So don't worry about that if your neighbor gives you a lower number， that's your number。

They're really clear on what the algorithm they're implementing here is。All right， so with that。

Let the game begin， everybody do this。We will。Reconverge in a few minutes。没。So remember。

 as soon as your neighbor gives you a better number。

 you want to immediately pass it on to your immediate neighbors， right， everybody doing that。

Keep going。Go to give it a couple more minutes here。Anybody have a number greater than 50？

Anybody have a number greater than 1，000？Interesting， anybody have a another greater than 2000？

Interesting， okay？Give you 30 more seconds。Okay。Remember the algorithm。

 you want the lowest number that any of your neighbors has offered you。

 you should offer that your number plus one to all your neighbors。Thats possible。All right。So。

Remember your number。So let's do the second part of this。Let's talk about your best friend。

You wanted a low number。Your best friend is the person who gave you your number。So， you know。

 note that。You are never your best friend'， best friend， I'm sorry， life is unfair。U。So。

If you forgot， who gave you your number？You forgot your best friend。A， you're terrible and B。

 it's easy enough to figure out， right。At least one of your neighbors must have your number minus-1。

 right， So pick any of those people and that person is now going to be your best friend。

Is that clear to everybody？Who your best friend is？So now。TAAs have envelopes。Some of them。

 those TAs are going to give some one of their neighbors an envelope。

And you give that envelope as a gift to your best friend。All right。Everybody clear what we're doing？

If you get an envelope， pass it to your best friend。Okay， go。Oh wait。 all right。こだけでやる。宝宝对呢。你看。

Where theよ。ランパーパック。そがつは。So someone gave you your number， right？That person must have less than yours。

 one less than yours。You're going to pass it to them。笑后了。あちって。All right。

 got a little bit less than one minute， remember if you know you've got。A number。Pasa two。

 whoever had the least。All right。All right， we're going to call it。So。With any luck。

Some envelopes got to their destination， I think there were five， I think there might have been four。

So who has an envelope？It'sone over there， one over there。How many did you have？2。Anybody else， okay。

 so I think there were four。Okay，唉。W't you open up your envelope。What does it say？Sas， hi Ian。

 are you Ian？That's too bad。Someone else opened one up。Are you Ian？I asked two pads， how I you。

 you got two， right？And what do they say？Are you in？A， okay。は。So we worked 50% of the time。So。

 you know。How did this work in the cases that it worked。

 We'll think about why it didn't work in a minute here。 What happened。

So everybody started with infinity， so this is y'all， these black boxes here with infinity in them。😊。

Ian started with zero。😀Yeah。😊，Ian told his neighbors one。His neighbor is told his their neighbors。2。

And so on。Right？And so it created this sort of slope。Leading to Ian。And so then， from wherever。

At least from two places。We started envelopes moving， right。

 and just sort of handed them down this slope and they ended up at Ian。So， you know。

 everyone who passed an envelope， raise your hand。So here's an obvious path to Ian。And you。

 there's another path。To Ian， and so those are part of this delivery tree。Leading to an。

So this generalizes this same basic approach so many destinations。

 right all we need to do is keep a separate number per each destination， right。

 you could have kept your Ian number and your Sylvia number and so on and this would have generalized to everybody。

Any questions on this basic algorithm？Yeah。我在。Oh I didn't， I gave them to Ian， Ian is one of the TAs。

😊，Good guess or a good good question。还质。嗯。Yeah， any other questions？好。嗯。Yeah。Yeah。

 so we would have written， you know， in that case you would have written Ian on it， right。

 and you would have said， okay， so my Ian number was given to me by this neighbor。

My Sylvia number was given to me by this neighbor。Other questions？Yeah。

I hope a lot for there are like。他老动。Destination。How do we keep。好 of。Yeah。

 so how would you keep track of it if you had a bunch of different ones， maybe in a table？😊，喂。

It's one per destination， right we can talk about。U。目的 he check到。Anybody。

 is it reasonable to keep track of an entry for each destination on the internet？Is that reasonable？

Mm。Maybe not， what about for each destination at Berkeley？Maybe right。

 so maybe it depends on the network right and so we'll talk about in a later lecture how you can sort of deal with that。

Good question。Okay， so what could possibly go wrong， what did go wrong。

 anybody have any thoughts about what could go wrong here？Yeah。

Some people maybe just didn't say their number to their neighbors。Yeahや。Yeah。

 there's some kind of gaps， right so do people， did they consider someone their neighbor if you know there was nobody next to them？

Anyone else？Yeah。Maybe some people made up numbers， right？Any other thoughts？All right。

 so I wrote them down， we covered some of them， so sitting too far apart， right， we got that one。

 and so that's a network partition， right， You didn't have any neighbors。

You may have forgotten your magic number， in which case that's like a router failure or maybe a router rebooting。

 right？You may have misremembered or misupdated your magic number。

And that's sort of the equivalent of an implementation bug， right。

 I think I heard one of these may have happened somewhere over here。😊。

Maybe a neighbor didn't hear the update， right， these networks， their best effort right。

 they're not reliable， so maybe your neighbor just didn't hear you。

 and so that's like a packet being dropped。嗯。Maybe you exchanged magic numbers。

RightAnd a neighbor gave you the number， they should have been your best friend， but then they left。

Right peace， so that could cause a problem， right？😊，That person leaves。

 and so that's like a link failure， right？And then we got this one too。

 someone might have lied about their number， you might have had a malicious actor， right。

 an attacker trying to subvert your network。😊，So you know。

 like there are a number of things that could go wrong。

 we probably got a number of these going on here， we lost two packets， 50% packet drop rate。

 that's not too good， but you know it's an early version of this network。

 so I think we probably had a partition and so anyway。😊。

What we implemented here is this distributed and asynchronous version of the Belman Ford Pafinding algorithm。

嗯。This should maybe be called the Schimbell Ford Moore Bellllman algorithm。

 if you took all the people who published the same algorithm in the order of publication。

 that's pretty long， it's usually just called Belman Ford。嗯。And。

So if there's a couple of things that we know about networks， right？Networks are distributed。

They've gotten many independent components。And we also know that networks are asynchronous， right。

 all the things don't operate in sync， it's not like if you do Belman Ford on paper and you know you can do every step in exactly the right order。

 you are all sort of doing all the steps all at once in sort of arbitrary orders。

But this algorithm works anyway。So this seems like a really promising algorithm。

To turn into a routing protocol。And in fact， that's exactly what we're going to do on Thursday。

 that is exactly what you will do for the project。😊，And so in the final few minutes here。😊。



![](img/690fb388ad4f8a7e367bee811fcba1a7_1.png)

I thought I'd just say a little bit about distance vectoror protocols in general， and so yes。

 a lot of text， so you know you know routing protocols that implement this Belman Ford style algorithm are called distance vectoror protocols。

 adjacent routers，😊，Conceptually are exchanging a vector that is an array， that version。

 the linear algebra version of vector， they're exchanging a vector of distances with their neighbors right because it's not just one number like you did it's a vector of numbers it's your ED number your Sylvia network your James number and so on and so on and so really it seems more like it's like a vector of tuples or it's like a map of distances like destination to distance but that's what you're exchanging this distance vector type routing protocols were used in ARPt which was the predecessor of the internet。

 as early as like 1969 so they've got pretty long history of routing in the internet later they were implemented by Xerox who you we all know from copy machines but Xerox was really quite influential in networking in a lot of technologies for a while。

😊，And then it was implemented by this thing Ro D， that is the routing Damon of BSD UniX。

 Berkeley UniX， in 1983， that version of the protocol。

 was then basically standardized in 1988 it's been updated a couple times one to support classless Ading。

 which is something that we're going to talk about next week。

 it was updated to work with IP version6， which is something that we'll talk a little bit about。😊。

That protocol that comes from Ro D， which is called RP or the routing information protocol。

 is sort of like the prototypical distance distance vector protocol sorry。😊。

That's kind of what our discussion of distance vectoror is going to center around something very much inspired by R。

 the project you're going to be implementing something very much inspired by R。

Final note is you know distance inspector has been deployed historically quite widely it's not nearly as common today。

 but it's also not dead Cisco has this protocol EIGRP， which is a distancespector protocol。

 it's used by a lot of Cisco networking routers， it goes back to the 90s。

 but it was only fairly recently like opened up and standardized in these RFCs。

 which are sort of where you know the body of knowledge that makes up the internet sort of codified。

😊，And then there are some other ones like this one Babel。

 which was published as an experimental RFC in 2011， but it's still actively worked on。

 they're actually working towards the standard of this new disspecor Pro Babel， but again。

 our discussion of it is going to go pretty much back to this sort of prototypical example of R。

 and so with that。😊，Finish up and I'll see you Thursday。

 and we'll talk about distance Spector in excruciating detail。还怎么一定。



![](img/690fb388ad4f8a7e367bee811fcba1a7_3.png)

![](img/690fb388ad4f8a7e367bee811fcba1a7_4.png)

![](img/690fb388ad4f8a7e367bee811fcba1a7_5.png)