# CMU《计算机网络基础｜CMU 14-740 Fundamentals of Computer Networks 2020》中英字幕（deepseek p12 -P12-2020_10_15_Lecture12.zh_en -BV13J6uYpEZm_p12-

![](img/7bf57d0ac982683bdaa862a7ffdc892f_0.png)

This is 147，40。 Welcome， everybody。Tos a beautiful fall day where it's just absolutely lovely out and we get to sit inside and talk about networks just the way it should be。

 I guess。Today， we're going to continue our conversation。About what just happened。There it went。

We're going to continue our conversation about TCP。And we're gonna get to。Yes， sorry。



![](img/7bf57d0ac982683bdaa862a7ffdc892f_2.png)

We're going to dig in a little bit on one of the other components。

 Now I mentioned this briefly last time， but TCP is this。

This' an amalgamation that we can do different things with and has different components。

 different pieces of it that have been modified throughout time。

 and so we're going to talk about a couple of those components today we're going to get into congestion control。

Which is definitely the area that has been modified the most in TCP since the original versions came out。

First up， though， let's talk about flowke control。Flow control is one of those things that is controlled by window。

 Now we learned about windows in the reliable data transport lecture where we talked about them as a mechanism to allow us to have multiple segments in flight。

And to properly control those segments。And then last lesson， when we talk about TCP， conspicuously。

 there was no mention of Windows。Even though we did talk about the idea of there being multiple segments in play。

Today， the windows come back。There are two windows in TCP。 They are independent windows。

 that is they function independently of each other。

Yet both of them act as controls on the sender or limits on the sender。The sender， basically。

 whenever it has a segment to send， has to check。 Am I allowed to send this。

 Is this in the flow control window。Yes， no。 And then also， is it in the congestion control window。

 Yes， no。 And if the answer to both those questions is a yes。

Then the sender can send the segment otherwise。He's limited by one or the other of these two。

And it's important to recognize that these are two separate things。

 So please do not get them mixed up， even though they both have the word control in them。

 they're very different。

![](img/7bf57d0ac982683bdaa862a7ffdc892f_4.png)

Different structures。 And both of these windows are here。 This is a picture I showed you last time。

 Both of the windows are here because of these producer consumer problems。AndBecause we have。

The sender able to produce segments at a different rate than the network is able to accept them or consume them。

 And also because that might be a different rate than the receiver is able to receive them。

The first that I'm going to talk about， the flow control is helping to manage the receiver as the consumer of our segments。

So you can think of this as the producer the sender is the production side。

 they're generating segments。For flow control， the receiver is the。Consumer。

Who will be getting these and needs to be protected a little bit。

 So what we're trying to do is make sure that the receiver has memory set aside for all of the segments that show up。



![](img/7bf57d0ac982683bdaa862a7ffdc892f_6.png)

Okay now you might look at this and say memory， that's a quaint notion and clearly in the 80s when we were just developing this memory was a very expensive component of my computer。

And so。It was often the case that the computer would have a limited amount of buffer space to store these segments。

Through the years， of course， the segments haven't changed in size。or anything like that。

 but the memory has gotten a lot cheaper and our computers have a lot more of that memory and so you might say wait a minute。

 this is kind of clint that we're worrying about this。However， recognize that this is on a。

 this buffer is usually set aside on a per connection basis。

And we today have computers that have and are handling a lot more TCP connections than previously。

 so just because you have a lot of memory。In your computer or on your server doesn't necessarily mean that this problem has gone away。

 You may be dividing a larger chunk of memory into many more pieces。And so， we have some amount of。

Of space to hold the segments when they show up， and that is traditionally called the RCV buffer because we're computer people and we like to get rid of bowels。

And then once we've named a thing， as has been done here， then everybody else uses that name。

And so the receive buffer size， that's the number of bytes that can be held in the receiver。 Now。

 of course， the reason we have that buffer on the receiver。

Is because we need to store those segments， the data that has come from the network。

 So I'm showing here on the left side of my diagram that we have data coming in from the network layer for my P。

And so those segments are showing up。At some rate。And there's no way for the receiver to interrupt the application to say。

 hey， I just got you another thousand bytes of data。

 please take it instead the application comes by asynchronously and scoops up the data and so that means we have this buffer。

Whose purpose is to store the segment data until the application can come and get it from us。

And so of my entire receive buffer， some of that may already be used。

Some of that may already have data in it， and that's what I'm showing there on the right side of that rectangle。

The space left is this spare room。And we've got to make sure that the sender。

 when he's sending segments， doesn't fill up the spare room。And so that's this receive window amount。

Okay， that lets us ensure that。We want to communicate that amount of space back to the sender。

 so the sender never actually sends us too much data。

So that we always have a place to put it on the receiver。So that received window。

 that spare room space， the RCV window， right we。When the receiver side can fairly easily calculate how big that is。

 And if everything is in order， then it's fairly easy to， to be able to say， you know。

 I know how much my receipt buffer is。 I know what that variable is。

 because I'm managing that that memory。 You know， I'm mall lookeded it a long time ago or whatever。

I know how big that is。 And I have the bite numbers of the bites I've received。Right。

 so I know as I'm acknowledging things， I know you know I've just sent an act back to the other side with the bite number of the next bite I expect and that will be the that will go into the spare room kind of at the。

The right side of the spare room。 So I know how where that is。

 I know what the application has has picked up from me。

So I can calculate how much data I have and how much is left。

 And so I can figure out what that actual receive window value should be。And obviously。

 if you're receiving segments out of order， that gets a little bit more complicated。

 but it's a tiny bit of management math that the receiver has to deal with。

Now what do I do with that number， I calculated that I have received window number of bytes。

In my spare room， that's the amount of space I could accept。But this is on the receiver side。Right。

 the receiver can calculate that easily。I need to control the sender。

And so TCP allows us to communicate this value back to the sender。

Because in the header of a TCP segment， we have that receive window value。 right。

 That's that 16 bit value。 It's on the fourth row down next to all the flags。Right。

 that's this RCV window value。 I'm going to send that as a receiver。

 I'm going to send that back to the sender。And tell them， here's how much space I have。

You can send me this many more bytes。Now， one thing that you might be thinking about immediately and saying。

 wait a minute。😡，By the time that gets back to the centerer， that value may be out of date。

 right we've got more segments may already been in flight coming here。Right。

 how do we manage that well。The sender knows。Where you were at the point in time when you made this calculation。

Because you're sending back an acknowledgement number， right， The acknowledgement number is the。

The basically tells here's the bite number of everything I've received previously。

And you can view that receive window as an offset of that。 so I've received up to X。

 and I have Y amount of extra space。And the receiver sends that back to the sender。

 when the sender gets that， the sender can calculate oh。Okay。

 I know this is where the window starts and this is how much how big the window is。At this point。

And so if the sender has already sent segments out that we're in that window。The center knows that。

Okay， and so the sender， again， the sender is keeping track of the。The send value。

 the bytes that he's sending and so when he puts together a new segment。

 he uses that receive window offset from the acknowledgement number to tell him kind of， okay。

 I can go up to this bitete number in this stream。D案 question。好 course the。From。

Like anything other than the7。So the question is， is there a way for this value to shrink？In fact。

 be modified at all。Before receiving the first Q when also already said more。Yeah。

 so there is a startup problem right， how do you how do you begin a connection if you've never gotten a receive a window back from the other side。

Okay， and so that is special case。So you're allowed to send your first one。

 And then when you get an acknowledgement for that first segment， then you find out， oh。

 this is how much space there is over there。 And then you can start sending them。

 But other than that， this value is only going to be modified based upon。

Segments that the receiver gets from in this connection from the send。

So it is a communication just between these two。Okay， so does that makes sense。

 it's a fairly simple mechanism， not too complicated。I。Maybe if I were designing TCP again。

 I'd get rid of that urgent data pointer and use that space to make the receiver window to a 32 bit value and just go ahead and calculate。

😔，Not as a relative offset， but here's the actual value， but other than that。

 it seems like a very simple。Mechanism。And it does its job very well of managing that control。

I point that out because the congestion control is not a simple mechanism。Okay。

 congestion control is a lot。Messier because it's a distributed problem。All right。

 so what is going on with congestion control， What we're trying to do with congestion control。

Is manage the memory that is distributed among all of the routers along the path from send to receiver。

We've talked about this way that clan when we talked about the so and forward networks。

Each of the routers has some memory in it。😡，That is used as a queuing space， as a buffer。

For when it has too many segments that need to actually packets at that level， too many packets。

That are trying to gl out on a single link。And has to be able to store them and so it has this memory to handle that。

Okay， and that means between any sender and receiver。There may be many。

 many routers that have these buffers and spaces in them。

And it gets really complicated because those particular pieces of memory。

 those buffers are also on the routes from other senders to other receivers。Okay。

 so you can imagine maybe I've got， you know between me and some destination。 We have some number。

 You've done trace routes right， You have some feel for， you're gonna have， you know。

 a dozen routers between me and my destination。Right。

Other people may be sending TCP streams that intersect with my does and routers and maybe intersect with only a couple of them。

 Maybe you'll only one of them。 Okay， and you know their packets will fill up these buffers as well。

 And so this is a distributed problem we have to deal with。And it's ugly there are costs。Now。

 in a non COVID world， at this point， I would set you up in groups of four and ask you to spend two minutes。

Writing down a list of the bad things that you see happen with congestion。Okay。

 so what I'd like you to do right now is just kind of sit back。Give you 30 seconds to think about。

What happens， what what is the cost， Why is it we don't like congestion I we're actually using a word from that most of us associate with traffic right。

 I don't like congestion right I don't like the Fort Pit tunnel being filled when I want to go through it。

Okay so it's a bad thing and yes， we're using that word deliberately right。

 it's a bad thing here also well tell me why tell me what happens when there is congestion sos take a second。

 take 30 of them。Sip back and think about， maybe make a list。

 jot down what you think are at some of the bad costs of congestion。😔，All right。

 so now that you had a chance to thank what I'd like you to do is just go ahead and dump some into those in the chat。

 go ahead and tell me what you came up with as some of your answers。Audience participation。

 let's all go， type something。All right， so clearly we thought that a lot of people saying drop packets。

RightLot packets， those are bad right wait times on the client side。

 which may there may be some blocking because of that that your application can't continue。Delay。

 right， maybe there's not just。You know， some sort of loss。

 maybe there's there's some delay of those packets as it takes a while to happen， new connections。

 I love that it takes more time for a new connection to get established。Yeah， this is great。

 These are all very good answer， I like。😊，We even got some of the security people in here saying denial of service。

I'm going to say maybe to that one right， certainly if if my congestion is happening。

 then whatever I want is denied to me， but it's not a traditional security problem where。

Some resources are getting overwhelmed， it's just kind of natural things that are going on。And， yes。

 Stehanus， I love your description of this。 right， This is what we feel。 And actually。

 this maybe what we feel would have been in traffic in places。 You know。

 never been to Boston before or Beijing。 Yeah， the whole network can grind to a halt after burst of traffic。

😊，Maybe a little melodramatic， but sure。Here's what I put for some of those right so an individual packet if there's congestion is going to experience some queuing delay right it's going to hit some router somewhere and wait around a while。

Sometimes they'll be dropped。😡，If a router already has its buffer full and another packet comes in。

 there's no place for this packet， and so it gets tossed over the router shoulder onto the floor where it shatters。

嗯。By the way， one of the problems will'll not talk about in this class。

 but you might look up the idea of buffer bloat。 It turns out that having too much memory can also be a problem。

 So even if we're not losing stuff， we end up with long delays。Now， when you get long delays or loss。

 what does a sender do， right a sender retransmits。

 right has to resend that segment because it's been lost。Okay， or maybe it wasn't actually lost。

 but it was slowed down enough that the actual acknowledgement took too long to get back to us。

 And so we re transmittedmitted。Even though we didn't need to。

 so that timeout value we were using turns out to be a premature value。

All this collapse down means we are wasting network resources。There is bandwidth available there is。

You know， the resources of all the routers going on， but they're being mismanaged。In some sense。

 they're being wasted because of this congestion。Edric。你觉得。お较新。大家。因为这把这。

Does that mean that like congestion causing report congestion at that。Yes， yes， I'm sorry。

 I didn't I didn't show how bleak this was。 And Edric who pointed this out entirely right。

 guess what， if you have some delay and loss， what does TCP do， it retransits。

And what happens when you retransmit， oh， you get more congestion。Okay， not good at all。

So so that actually is the elevator pitch。For congestion control， right。

 TCP needs to do something to make sure it doesn't make the situation worse when there is congestion。

Yeah， so basically， guys who've got too much data， too many sources。

 or maybe a couple few really fast sources that are sending too much data。

 and it's too much data for the network to handle。 I want to be very clear about this。

 This is not a flow control thing。This is not whether the receiver can handle it or not。

 it's the fact that the network， the routers in the network can't handle that。Okay。

 and as the network load， we， we kind of think about this distributed problem。

 and we try to put it down into some single concept that we're going to call load。Right， yes。

 you could look into it and find out of the dozen routers between me and the endpoint。

 Maybe there's only one of them that's having trouble。

But I'm going to think about it as the load of the network。

 especially at the transport layer because I'm abstracting the network anyway。

And so as the network load increases， as there's more traffic in the network。

Or at least along the path I'm using on the network that means I'm going to have longer delays right because the queuees are going to be longer in some router and so to get through one particular router is going to take a longer time。

And it may end up overwhelming some routers buffer space and us actually losing the packets as they travel。

 which isn't good。Okay。So what we need to do is what we want。

 we would like to control things so that we aren't adding to the problem。

And so that we can help manage this load and get our packets traveling well。 So our。

 our goal is a large throughput and a small delay。😊，By the way， I'm using the word throughput here。

 which is technically different from bandwidth。Okay， bandwidthand is an available resource。

 It's an available amount of transmitting power， whereas throughput is the actual。

Amountunds of bandwidth I get to use right So if I， this is a measure of the actual bits I'm sending。

 not the ones that I could be sending。Right， so。What that means is if I want。So as a sender。

 I don't particularly care if I'm connected band。I want to use it and that becomes throughput。

So if I want a big throughput， well， I need to be sending packets。

And it's not usually that that's my goal to have a big throughput。

 my goal is usually to send a lot of packets。And that implies that I will increase my throughput as I use the network。

The problem for the sender is that as I add more packets to the network or as there are more packets in the network。

 then these Q lengths increase， the delay increases。

And so I can start off with a very small delay right if there are no segments in the network。

 then they go quickly， but as that throughput increases。

 we're actually adding to the load of the network。And so I've shown in a few little sketchy graphs here kind of what would happen in terms of throughput and delay related to the network load and the idea is on that first graph。

 if I'm not sending anything， I'm not in any load on the network， but my throughput is very low。

And so I can send more packets， I can send more segments and increase that throughput。Okay。

But as I do， I eventually load up the network and I can no longer keep increasing the throughput。

In fact， we come to some point。Where our traffic intensity is equal to one and all of a sudden things just kind of go over the cliff。

And we start getting large packet loss and then things get retransmitted and you end up with a real mess。

The graph on the bottom again against network load。

 shows that as you're sending as the load of the network is low， then the delay ends up being low。

If you are the only packet in the network， then the routers don't have to cue you at all and you go at the speed of the network。

😡，Okay， but as the load increases。Then your packets take longer and longer and longer， and。

They aren't identical rats， right。Which means that we have a couple of regions here right so I've got a region on the left。

😡，Where things are lightly loaded， right， I'm not getting a huge amount of throughput。

But I'm also not getting much delay。And then I've got a center section there where the load is starting to increase。

 and even though I get a large throughput， the delay is increasing and increasing fast。

And then I have the congestion collapse region on the right。Where everything is really bad， right。

 The delay is huge。Packets are being dropped and retransmitted and dropped and retransmitted。

 and I get very little actual throughput when that happens。Where would we like to be on this graph？

What load would you like to operate at。Well， clearly， the collapse region is not it。😡，Alright。

 I'd like to stay away from that。 But can you point to a particular X value that you think is the appropriate。

Level to be working at。There's a knee point there， right， Yeah。

 that knee point right here is a nice place to operate。At that point。

 you get a large amount of throughput with a small delay。And if you increase the load。

 you only get a little bit more throughput。But you get a lot more delay。Okay。

 so there is a nice spot to be working at。Okay， so we'd like to。To get to that。

 we'd like to somehow be able to manage that。 Now， the problem is。As a sender。

 I know that I'd like to be at that knee。How do I know I'm there？Well。

 if you think about control theory， not even just network control theory， but control in general。

 control relies upon some feedback mechanism。Right， you do something。

And you can't control that process unless you are able to understand how well that process has occurred。

And so for us， for the sender， the process is sending segments。I need a feedback mechanism。

 I need to know， how did this do。Okay， and to let me know which side of that knee am I on And what we want to do is to react to that feedback。

 if it looks like。There's too much load in the network。 Then I can slow down my sending rate。

I cannot transmit the packets or the segments as fast as I had been sending them。Okay， so。

 and sometimes this is called the conservation of packets law。

 which kind of sounds like it's a physics， you know。Conservation of momentum。

 the way the universe must work。It's not that kind of law at all。

 This is the more of an engineering law。 We would like to be operating at some equilibrium。

And once you're there， you'd like to use the feedback of the network。😡，To know。

That you're at that nice knee point and then only add a new segment to the actual transmission or to the network when you know one has been taken out and you only know one who's been taken out when you get some feedback。

Now， where should this feedback come from？Well， there are two basic choices here。

 one of them seems obvious， one a little less so。I'm using the network。

So it's possible that the network should be telling me whether there's congestion or not。

The network knows if there's congestion， right， there's some router out there who's crying。

Because there's no memory and he's dropping packets， and he's definitely under congested load。Okay。

 so we could get a signal from the router from the network layer that says， hey， hey。

 we're congested。 Please slow down。Or we can use a different mechanism。

 one that's kind of tappeded into the feedback mechanism we're already using。

TCP uses receiver feedback as a reliable data transfer tool， right？We send segments。

 We get acknowledgements。Those acknowledgegments are feedback。

So the other opportunity is to use that end to end feedback。

 that message that comes from the receiver。😡，That may give us some hints about whether there is congestion or not。

So there are these two different approaches。RightAnd the network assisted one seems obvious right And in fact。

 it has been used in every networking technology that's been put together ever。 right。

 So the idea is the routers are going to tell the send or something， right they may。Send some。

 some data directly back to the sender。 right， Let's send a message back saying， I'm overwhelmed。

 Please slow down。Or maybe I' go ahead and have the router instead of sending an extra message。

 let's just go ahead and put some notification into the header of the messages as they flow by。Right。

 so it'll say， I'm in trouble。Let me go ahead and set this bit。

 That will get to a receiver with the idea that the receiver， when he sends an acknowledgecment。

 would include that bit。To tell the sender， hey， there's some congestion somewhere slowed down。

Or it could be that the network actually explicitly sets the end rate。The network could know， hey。

 here are my capabilities， I know what this bandwidth is。

Along this link you're trying to put together， you should be sending at X number of bits per second。

All those mechanisms would be network assisted that would come from the network。

And all of them have the same problem。😡，Even though it seems obvious that the router knows that they're in trouble。

When the router is in trouble， the last thing you want it to do is extra work。

You would like it to do its fundamental job， which is forward packets。

That's what a router should be doing all the time， forwarding packets as fast as possible。Okay。

 if we tackle on these other jobs， oh， I'm congested。 I'm too busy。 things are bad。 Therefore。

 I need to send a bunch of more messages back to everybody who is transmitting to me。

That slows down that fundamental job of forwarding packets。

And that means it's going to be longer until that router gets out of its congestion。Problem。

And so that's why we end up using an end to end approach right we don't want the network to have additional work to do。

 just go ahead forward package as fast as you can。😔。

We're going to go ahead and use the end to end feedback we already have。

 We're going to use the acknowledgement mechanism， and we're going to infer from that what the situation is in the network。

For reliability reasons， I already need to know if there's loss。

And we're going to just make an assumption， which is a fairly decent one。

 that if there is loss in the network， it's because there's congestion。 not 100%。

Segments get lost because of it got flipped somewhere and the data link layer threw away a frame。

Okay， that happens。But more often segments are going to get lost because there's some congestion。

And so we're going to use that loss or even the delay。

That we observe as mechanisms to control our own sending。That's what happens in TCP。All right。

 so now let's take a look in TCP。How does TCP actually manage this？So TCP has this window thing。

Right again， this is our other window， this is different from the receive window。

 this is congestion window and again we have you know we were running out of space as we type things。

 so we call it Kong win for the congestion window that's a variable that's a value that tells us how big this window is。

And that lets us compare when I want to send a segment。 Is it in the congestion window or not。Okay。

 and that congestion window。We're going to calculate and manipulate that congestion window。Basically。

 what we're doing is making sure that we don't send anything outside of that window value and since we're keeping track of stuff by bytes sent。

 congestion window is going to be in bytes。And we'll always make sure that the last bite we sent。

I subtracted out the last plate that's been acknowledged that that space is less than my congestion window。

Now， I assert down here at the bottom that my sending rate then is roughly congestion window divided by the round trip time。

Where did that come from。And what's going on there？Well， take a look at that bullet up there。

 uses common wind variable。 How much data is allowed in flight at any time。

Do we have a formula that lets us know something about the amount of data that we can have in flight at any point in time？

Do we have？Maybe a fundamental equation。That tells us how much data we can have allowed in flight at any point in time。

Anybody。Oh， no。 Have we forgotten the fundamental law。Of networking so quickly。Yeah。

 how do I calculate the amount of data I can have in flight at any point in time。

 that is my bandwidth delay product。Remember in that terms， bandwidth delay。 If I take the bandwidth。

 I have multiply my round trip delay。That's equal to the most data I can have in transit at any point in time and so if you look at that formula there。

 what I've done is I've just solve for the rate。The congestion window amount of data I can have in flight is equal to the bandwidth times the delay。

 so if I just take the bandwidth times delay and divide by delay or divide by round trip time。

 I end up noting that my rate is equal to my congestion window divided by my round trip time。

So that means bigger congestion window， more data in flight， higher sending rate。Okay。

 so what we're going to do on the sender side， this is by the way congestion control entirely on the sender side。

 the receiver doesn't know how the congestion control is working。

 the receiver works exactly like we talked about last time。Cended， though。

 is going to be looking for evidence of loss。That comes in， well， anytime there's a timeout。

 that's how we know there's some loss。my timer goes off。We lost something。

 or at least we think we lost something， and we retransmit it。IfFrom willing to retransmit something。

 I'm pretty sure there's some loss。Okay， so we're going to associate that with congestion again。

 not entirely true， but close enough。We also have this triple duplicate act mechanism。

Remember that get the same if I get three duplicate acknowledgements。

 which means a total of four acgments。With the same act number。I use that as an indicator。

 a softer indicator of loss。Okay， even though my timer hasn't gone off yet， fast retransmit says。

 go ahead and retransmit that thing。And so what I'm going to do is anytime these happen。

 I'm going to reduce my congestion window， which will keep me from sending anything。

Because or at least it will reduce the rate at which I send things if the congestion window goes down。

Which will help us get out of congestion faster。Now there are several algorithms that get put into the congestion control on the sender。

 and all of them manipulate this congestion window variable。

so we can think of this as these different components that are pieces of the makeup my entire TCP scenario。

And so there's some， there's one called slow start。That helps us get。Start it right。

 gets up to some equilibrium point。And then we have a congestion avoidance phase。

 which we call AIMD or additive increase， multiplicative decrease。That is basically， okay。

 I'm sending as fast as I can， but I'm going to be careful to try to avoid any congestion if there is any。

Right。And for this to work， we're going to have to estimate what round trip time is。

 so we'll figure out today I've been promising that I'll show you how we actually calculate the timeout value。

 we'll talk about how that happens。One thing that I think is very interesting is that we are managing this rate right What we want to do is keep track of。

Our sending rate and be able to change the rate， raise it and lower it。

 but at no time am we actually taking measurements of time。

We're not seeing how many segments do we send per second？

We don't ever actually calculate or count over a second。Okay， instead。

 TCP is known as a self clocking system。 It doesn't have an external time sense at all。

 which is a little bit weird， but it shows up in various places。

 The best example I have of this comes from my hobby。 You guys may know that I brew my own beer。Okay。

 and that means that every once in a while I spend the afternoon making about 100 bottles of beer。

 which I stash in my basement。Right。But of course I don't like them all just down there。

 I like to drink the beer， okay， so I would like some in my refrigerator so that when I come home after a difficult computer networking lecture。

 I can pop open a beer and have one， right？So how do I manage to make sure that I always have a beer available in that refrigerator。

 I could。Do some calculation， right？ I could say， how many beers do I drink per day or per week。

 right？ And let's calculate out that number。 And then let me make sure that I bring up beer from the basement at that rate。

If I drink X beers per let's be nice and say per week， I drink X beers per week right。

 this is a pre COVID number also I drink X beers per week。

 then I would want to put some mechanism in place that would make sure that X beers per week come out of the basement into my refrigerator。

That would not be a self clocking system because I'd be working with time。😡，Al。

 I'd say like every Sunday， let's say I'd have to bring up。X number of beers。Right。

And that will be a clocked system。Instead I actually soft clock。

 how do I soft clock well one of the things about brewing is that when I drink up beer。

 I have to wash out the bottle and keep it because I'm going to eventually want to put more beer in it。

And so after I washed the beers out。Or wash the bottle out。

I take the bottle and I put it in one of those little six pack holders that I keep up in the kitchen。

And then every once in a while， that six pack holder gets full， right， And when it does。

 what do I do， I carry that down to the basement and put it in storage for the next time I brew。

And I bring up six beers to replace it， to put in the refrigerator。This is a self Clark system。

If something happens like there's a global pandemic and I suddenly start drinking beer at a higher rate。

Okay， then。That means I don't have to change anything about my system， right。

 It just means that as I consume more or less。Then， I create empty bottles。Faster or slower。

 those empty bottles get taken down to the basement at the same rate that the bottle the full bottles get brought back up that's a self clocking system。

Okay， and those are less。Less brittle to changes。If things change about my consumption。

 the system doesn't have to change at all and they don't have to worry about like oh。

 that week where I had a party and needed more beer up to handle that or something like that right if there's an extraordinary event。

😔，A clock system would have trouble handling that。Whereas the self clocking。

Just kind of all works itself out。So TCP is self plot incleement。

 so there's no external clock telling this what's going on。

It's also important to recognize that they're couple， they're man need algorithmic variant。

We're going to talk about the first two today， Tahoe and Reno。Okay。

 and I say here that Reno is the most widely used。It is historically the most widely used。

 it's hard to say today whether more people are using it or not。

You're going to have to look at installs of Linux versus Windows and things like that and what is being used on all those。

Let's just say it is the most widely used in networking classes and textbooks。

We will be talking about many other variations to come as well as importance。

 important and kind of cool stuff。All right， so here's a picture to get us into this slow start mentality。

 this picture from the paper you read， the Jacobson paper about congestion control。

 and this is a graph that's showing what happens when you don't have any slow start mechanism。Right。

 so what do we mean by that？ Well， let's imagine that some application comes around and says， hey。

 I'd like to send this file。I'd like to send this HTTP request to that web server。

 or I'd like to respond to this HTTP request with something all of a sudden。

 the application says here's a bunch of data tos send。And TC pieces。 sure， I can do this。

 Let me start up， when me make segments out of it， chop it up into pieces。

 put headers on each of them， and let's just start sending them。

This was the way the original TCP worked。And that's the result。 right， They get this graph。

 What am I seeing here， Well， time is along the X axis。

So we're seeing a file get sent and it takes about 10 seconds to send this file on this network。

The Y axis is the segment number of each of the packets that are sent。

Each of the segments that are set。Right， and you'll see。First off， if you do a bit of math。

 you're going to realize that these are fairly small segments。Okay。

 because that is counted in kilobytes on the side。 and you can see， you know， the whole thing is。

 let's say， 68 kilobytes。And each of the black dots you see is a separate segment that gets sent。

With its own sequence number， and so you can see at the beginning of time with this TCP do。

 TCP sends a whole bunch of segments。Right， it sends segment 0，1。

 whatever dot that that that all way up to like 20 K， which is a lot of dots， right。

 We've got like two or three dozen dots there。To get up to that 20 k on that original peak。Okay， now。

This turns out to be too much for the network。How do we know？ Well， look。

 about a second and a half later， there's a dot there。Right，What's that thought。

 That's a retransmission of a segment。 Which segment is it a retransmission of one near the end of this bunch。

 No， it's like a third of the way through。We managed to get like the first 10 kiloabbytes through the network。

And now we're being said， okay，11 kilobte， please send that again。Okay。

 and then a quarter of a second later， we get a a look at that。

 That must have been some timeout window went off or something， right， because all of a sudden。

 dump him again。 Here's another three dozen segments。3333333。And this up down， up down， up down。

Behavior that you see of TCP and the network is， let's dump very quickly。 So very fast slope。

With in a short amount of time in a lot of segments。

And then we wait around and we get to retransmit a bunch of segments。

And then we wait around and retransmit and retransmit and retransmit。

And I've shone there in that little purple bar there。

I was able to find some segments that got sent five times。Okay， the same sequence number。

 that is the same segment。Got sent at like time 4， N time 5 and a half， end time 6 and a quarter。

 you know。Those guys got sent five times， and I love this quote from the paper。

Ven Jacobson says nothing in this trace resembles desirable behavior。I agree entirely。

 right Do I want my network to have to retransrenchitt stuff five times？No， what's going on here。

 What's going on here is we're not giving the。The network， a chance。

 We're not getting to equilibrium。 We're just dumping way more than the network is able to handle on it。

Okay， here is far more than your bandwidth delay product。And the routers in that network。

Can't handle it。 They get into congestion right away。 And where is the congestion coming from。

 Can I blame those， Oh， the network is bad。 Everybody must be checking Reddit right now。 No。

 this is one sender。 This is me。Okay， I am my own worst enemy in this case。So what do we need to do。

 we need to slow things down。We need to get to some sense of equilibrium。

 and part of it is that I as a sender， have no idea at the beginning what that equilibrium is。

I can't tell， oh， this is how many packets per second I should be sending in my network。

Because I've just started up， I have no understanding of what's going on on the network。

 and so I create segments as fast as I can。😔，Therefore， a slow start component was added to TCP。

The slow start component is entirely intended to slow you down。

Until you have a chance to understand what the equilibrium of the network gives。

Now we don't want to be too slow we'll start off very slow， in fact。

 we'll start off with our congestion window variable set to one MSS， one maximum segment size。

Basically， I get to send one segment。Okay by the way。

 all of the discussion today is going to assume that we have as much application data as I want。

so of this bunch of data I'm supposed to send， I'm only allowed to send one segment at first。Also。

 you should notice here what are we doing， we're manipulating the congestion window variable。

 that's how congestion control works。All right， so my congestion control window is one MSS。

That may be way too small。😡，That hopefully I can send more than one MS per round trip time。

So what I want to do is I want to ramp it up quickly。And to ramp up quickly。

 what I'm going to do is I'm going to do it exponentially。

 I'm going to keep doubling my congestion window。You know， double it， double it。

 double it so I send one， then I want to be able to send two， then I want to be able to send four。

 et cetera。the question as the initial window start。Yes， the initial congestion window。

 I guess we should be careful， right， This is classic TCP。

Any particular implementation may be slightly different from this。But under your classic TCP。

 you always start at one MSS。In theory， I might have some knowledge。

 yesterday we used this same network。And we had this kind of level。 Maybe I could use that。

But classic TCP does and classic TCP considers any connection to be unique。

And so we're always going to start at one。 We're going to send one。And then two， and then4。

 and then 8。Now its an exponential process， right， exponential processes。

Are designed to use up resources quickly， and eventually we're going to get to some limit。

And S start has its limits。Basically， that limit is when I get to some loss event。Okay。

 I'm going to keep doubling and doubling and doubling until I actually cause a loss or until I have some indicator that there's some congestion。

Right， and。We'll handle that with our next。はい。The other thing that can happen is there is a threshold。

 the slow start threshold， again， SS thrash。Because we wanted it to fit on the slides。

 I guess that's some， some threshold that's been put in place。

For when you're starting up a connection， this is how big this should be okay and we will by the way modify that one a little bit。

 but at the beginning it would be you know some number that some administrator or some implementer has decided upon。

So we'll keep doubling， keep doubling until we hit that threshold or until we get。

Some actual bandwidth law， some actual loss of segment。How do we do this。

 We want to double the congestion window， every round trip time。Okay， well。

 that almost sounds like I have to be keeping track of round trip time。

But that wouldn't be a self clocking mechanism。And instead， there's a very nice。

 elegant mechanism that we use。 And idea is every time you get an acknowledgement。

You go ahead and let's see， an acknowledgement means that's around trip time。Right。

And every round trip time， I'd like to double a congestion window。

So every time I get an acknowledgecment， well， I can't double the congestion window for every acknowledgement。

😡，Ca that would， in cases where I sent out a bunch of segments and I get back a bunch of acknowledments。

 That would be too fast。Instead， what you do is every time you get an acknowledgement。

 you increase the congestion window by one segment size。Okay，Now why does that work， Well。

 take a look at the picture， right， I send a segment。At that point in time。

 my congestion window is one MSS， one segment size。Right。

And then that goes out and it comes back one round trip time later。At that point in time。

 what am I allowed to do？At that point in time， my congestion window is one MSS。

And I have no outstanding unacknowledged segments。All of the segments we've sent have been acknowledged。

So that means I have a window that is completely empty。

So we are allowed to send another segment because the window is empty。And because of this rule。

 we're going to increase the window by one segment size。That lets me send two segments。

One because the window was empty originally and one because I increased the window by one segment。

And so now we send out two segments。When the first acknowledgement comes back。

That means my window size is2， but I have only one unacknowledged segment in it。

 so I'm allowed to resend one。Plus， I increase the window by one segment size。

So we actually send two。When that second acknowledgement comes back， the same thing happens。

 There's now space to send another segment， and we increase the size by one。

So I know now go ahead and send two， that's a total of four。For this round trip time。Okay， Eric。

Perhaps。这个所调我吃啊。So if you're getting a bunch of for previous segments right yeah。

 so this picture shows is assuming good behavior。We'll talk about the loss scenario in a second。

Which is， which will be a little bit different。唱那歌啊。啊没。

Where' does the preset value come from from some network administrator。

 maybe the administrator or the implementer decided maybe it's an environment variable you're allowed to set。

It would depend on how this was actually implemented。So yeah。

 various ways that that number is set somehow it comes in existence。All right。

 so if I understand the very simple idea， self clocking idea every time I get an acknowledgement back。

 I'm going to increase the window size by one and what that does is it doubles the congestion window every round trip time。

Question。怎么我れ。这在之下。我在听我跟觉。Yes， so you're asking if I have multiple senders in my network。

 which we do right we're all sending right now and we're all exponentially increasing yeah。

 we're to class in congestion In fact I don't even need multiple systems right if I only have me sending and I double every time eventually doubling is a big number。

In fact， not even eventually， really quickly， keeping doubling gets to be a very big number。 Okay。

 so， yes， this is a slow start mechanism。It starts us at one， it quickly gets us moving， right。

 we're quickly moving a lot of data， but eventually or but。In the very near future。

 we're going to run into trouble。Okay， and when we do， we'll see it， right， We'll see a loss event。

And when that happens， we'll stop Dublin， we will be done with slow start。At that point。



![](img/7bf57d0ac982683bdaa862a7ffdc892f_8.png)

Here's another picture from the same paper。 This is Van Jacobson saying， hey， look， slow start。

 much better。This is the same kind of picture right over 10 seconds And you'll see now you can actually see one dot and then two dots and the four dots and then eight dots and then it moves off into this nice move。

Set of dots。And so our file gets sent。At a good rate。嗯。

You might ask yourself the difference between this picture and the previous one in terms of dimensions right still took us 10 seconds to send the file right didn't this the previous picture take 10 seconds to send the file？

But this one was ugly， and this one is good。What's the difference between the two files？

So I'm nitpic on Van Jacobson's paper。好呀。Yeah， the wax has scaled differently because he's actually sending a different file。

 right， The previous file， he sent 68 kB of data。Right， this one in 10 seconds。

 he sends almost 160 kB of data。 Okay， so yes， it's good。That that happens？But if you're not careful。

 you'll say hey， it's a pen7。All right， so slow start works， fantastic， that's great。

 what happens next？😊，What happens after slow start， Well。

 when you get in a loss event or you hit the threshold， you move out of slow start into， well。

 I want to keep control going， right， I'd like， I've now discovered kind of a limit of the amount of available bandwidth。

 I'd like to be sending near to this limit。I've discovered something about the network。

 let's keep going。Okay well， we then move into what we call congestion avoidance phase。

Where I would like to send a lot， but Id really not like to cause congestion。

 so I'm going to do what I can to avoid it and we call this additive increase multiplicative decrease algorithm。

What's going to happen is I'm going to continually add to my congestion window。 Okay。

 I'm going to slowly increase that window getting bigger and bigger and bigger because I'd like to use bandwidth if it's there。

If I can send at a higher rate， I'd like to。But if I ever have a loss event。

 if I ever discover that there's some congestion， I want to get out of that situation quickly。

 I want to let the router to recover from that congestion， and so I want to lower my rate。Quickly。

 and so that's why we have a multiplicative decrease。

 I will not just subtract one from my congestion window when I see some congestion。 Instead。

 I will cut it in half。I will multiply by a fraction so that I rapidly decrease my congestion window。

And then I'll go back to additively increasing probing for more bandwidth。

And so we end up with a congestion window sized。That has this kind of behavior。

 this saw tooth like behavior。 We're going to increase the congestion window by one every round trip time。

 This is different from slow start， right， Slow start increase the congestion window by one for every acknowledgement that came back。

We are adding one for every round trip time。Okay， and then if I ever have a loss event。

We cut that congestion window in half。And so this lets us probe for bandwidth if it's there and get out of the router's way if there's any problem know？

新な。Like if you， send often heres。It sort of looks like you can't like like many under doing this。

 And one under， theres aggressively like are very high。 and just started。Yes。

 so Deion is pointing out that there's some competition going on and we'll talk more about this as well。

 he's right， if you have multiple senders that are doing this kind of behavior。

 it might get in a situation where the other guys back off first and I get to keep increasing my bandwidth and so I win in this know kind of competition for bandwidth。

Okay and that gets really interesting we'll talk much more about the fairness and how this all boils out。

 but yeah you're right that that could be one of the。There are a couple bad behaviors that happen。

 emergent behaviors that happen because of this。But let's keep it back to what does one sender do。

 What's the algorithm asking them to do， This is this additive increase。

 multiplicative decrease behavior that we follow in the。

In the congestion avoidance phase now that additive increased multiplicative decrease actually came about as in as a refinement。

 the original TCP with congestion control， which is called TCP Tahoe。

Tho didn't really have a multiplicative decrease。 Okay， basically， you see the blue line here as。

 and again， we have the wax in time， but I've labeled it as transmission rounds。

 The number of round trip times。 You see every round trip time。 You can see， we have some slow start。

 but then additive increase。 We just increase。 you know， my window is 8， then it's 9， then it's10。

 then it's1， then it's 12。And under the first version， Tahoe。Whenever there was a loss event。

 we went back to the beginning and slowlo started again。

And that was quickly discovered to be too wimpy。And would give up too much bandwidth and we didn't need to back off that much。

And so Reno， the second version of congestion control came out and it included this multiplicative decreased idea。

 so it would still add one， add one， add one， but if there's ever a loss event you divide by half instead of going back to the slow start。

So that's another story we're going to explore more is that you can refine these algorithms and it has been refined quite a bit through the years as weve come up with new ideas。

This was called Fast recoveryy right to Tahoe， whenever there's a loss of events。

 goes back to slow start。The story with Reno' is a little bit more complicated than I showed on that picture previously with Reno。

 there's this idea that we're able to look at the feedback and see two kinds of different feedback。

Okay， one of them is there's a strong loss event if a timer goes off， pretty sure there's a loss。

I'm going to retransmit anyway， and so that's bad。And so in those cases。

 we're going to go ahead and follow what Tahoe did。If there is a loss that causes us to retransmit。

 we're going to start over with slow start。Okay。However， if there is not。

 if there is a light indication of loss， which I get from these duplicate acts。

If I have three duplicate Xs show up。I am going to retransmit because that's what fast retransmission required of us。

Okay， but as far as congestion control， that's where we do the divide by 2。Okay。

 so now Reno actually kind of has this different philosophy that says， hey， you know。Some loss。

Detection is worse than others。And so we don't want to back way off if one segment has just gotten delayed a little bit。

Or something like that。 Okay so we'll go ahead and and only back off if there's kind of an alarming。

Scenario that we see。The other thing I should point out is this threshold value。

We had an SS threshold that was just set at some number through slow start。

 and when I got to that I moved into congestion control into congestion avoidance rather。

We're going to go ahead and manipulate that variable as well。

 because that's kind of an indicator now that I have had some understanding of the network。

 I can use that to guide future slow start scenarios。And so when we do the division by half。

 we're going to set the threshold to that that divide by two number。 And so that number will vary。

 It won't just be some number that some implementer decided way back when it actually will have something to do with the network behavior we're observing right now。



![](img/7bf57d0ac982683bdaa862a7ffdc892f_10.png)

And so we get pictures like this Here's a。Sa sort of plot time and transmission rounds and congestion window size on the Y axis。

And you can look at this graph and you should hopefully immediately be able to look at this and say。

 oh， slow start happening， when does slow start happening？Can you point to it？Yeah， I hope you can。

 right， it's right there， right It's this exponential behavior。

We are going from one to 2 to four to 8 to 16 to 32 as my 32 segments as my congestion window size。

 oh and it's over there as well。Those are times when the slow start algorithm is working。

Right how about congestion avoidance well congestion avoidance is going to happen at the other times right where I get these nice linear increases right 32。

 33， 34， 35， 36 right we're adding one every round trip ton and so that's an additive increase。Right。

And then something happens， right， I got up to like 42 there。Okay， and then something happens。

 can we tell what happens？Yeah，3 duplicate apps， right。 How do you know。Yes。

 the congestion size in the next round is divided by two。And we continue with the additive increase。

 So we did not go back in the slow start。 We stayed in the congestion avoidance phase。

We just backed off to allow some router to recover。At that point， once I backed off。

 what's the value of my threshold？That threshold variable we keep track of， what happens to。

I'm sorry。Yeah， so this threshold remember this is another variable that Reno is going to be managing for us right and so when we back off on you divide by two。

 we're going to set it to that variable to that value that we set the congestion window to。

So at that point in time， we're going to take the 42， which was our congestion window。

 we cut the congestion window in half， and we set the threshold to the same value。

Now why is this important， well， notice originally with the slow start， we got up to 32。Right。

And so I'm going to guess that was what the threshold was was set at 32。Okay， now。

What we're doing is we're saying， hey， you know， we now understand something of the network。

 Maybe that threshold should be more like 21 instead。

 And so if you go back into slow Srk for some reason。And curl out of that。

 you should stop when you get to 21。对。Thank续。不退啊。Oh， yeah。 So we're looking over hereops。

So Edric's looking here at this point saying wait a minute。

 you know the threshold looks like it's half of that right。

 but remember what happened we grew here it was 21 right we grew up to here and then had another loss event。

Okay， and so we're going to divide it from。From again in half to get us done to hear。Okay。

 and so at this point， if we have a triple dip act， what if I point this up， this is。

What 16 or so right at that point in time， the threshold again and congestion window going to get cut in half down to eight。

All right， so that's great， feels like we understand the congestion avoidance mechanism as well。



![](img/7bf57d0ac982683bdaa862a7ffdc892f_12.png)

We have been relying upon this round trip time。Okay， to help us manage。

Some of our variables to be able to set our timer things like that。

 and so I wanted to add as another component， another piece you can kind of imagine there's another piece of the code in the sender code base。

Another algorithm description。 How do we go ahead and figure out what that round trip time is or what that timeout value should be。

The round trip time is actually what we observe out of the network。And you guys。

 you've seen some network traces by now， you should get a feeling that is the round trip time always exactly the same。

 is the network nice and static and everything's just moving along exactly perfectly， no。

 it's variable quite a bit。Okay， and so we're going set the timeout value。

But its relationship to the round trip time is important。

 and if we set the timeout value less than the round trip time。

 then we're going to be sending out too many retransmissions。

Because the round trip time is the first time at which we would be able to get an acknowledgement。

So we shouldn't set the timer to be less than that。Okay，However， we don't want it to be too long。

 right， if it's a 10 second long timer and the round trip time is only a second。

That means if there is a loss。I won't know about it for an excessive amount of time。Okay。

 that means I will deliberately not be using the bandwidth efficiently， I'll not be reacting quick。

Okay， so。We actually want to get this timeout value to somehow link up to be managed buyer to be a reaction to the round trip time that we're actually seeing in the network。

So what's that imply that we do Well first thing we're going to do is we're going to go ahead and measure what we think round trip time is。

And we can do that by actually sampling when I send this segment。

And how long does it take until I get an acknowledgement？I can actually measure that at the sender。

And so we're going to do that。 We're going to call that some sample。

 We're going to say this is the sample round trip time。We're going to ignore any RET transmissions。😡。

That we get， and we're just going to collect these samples。

I'm going to not just collect one because as we mentioned， the network varies quite a bit。

And so somehow I'm going to have these samples and I'm going to want to smooth them out somehow。

And we'll use that smoothing to come up with a better estimation of what the round trip time actually is。

Now， first off。Why is it that we ignore these right retransmissions this kind of gets back to a question Deion had asked earlier right about。

Our mechanisms and why we're doing them or the fact that we are thinking about them in kind of the clean。

 no loss environment。What happens if I do have a retransmission？

And why should TCP ignore those samples？ Well， this is why， right here。

 I've got a scenario where I send a segment。Right， and。

The timeout goes off early and thus gets retransmitted。Okay， but nothing actually got lost。

And the issue is that I'm going to get an acknowledgement back from the other side。

I technically won't know whether that's an acknowledgecment of the first segment I sent or the re transmittedit segment。

 right， And so I could measure。This very short round trip time。

That occurred between the sending of the second， the retransmitted segment and the receipt of the acknowledgeknowment for the first。

And I don't want there to be any danger that that might happen。

 so anytime I retransmit that particular segment is not eligible for any round trip time measurements。

Okay， we're gonna to。Ignore that entirely。All right。

 the next question then is I've got all these samples and they are going to vary quite a bit。

 how do we smooth them and how do we create an estimate for around trip time based upon these samples？

Well we're going to use a moving average what's a moving average。

 a moving average is where you take a lot of samples and you detect or you declare that you're going to use some number of those samples to create an average so you're going to average over them。

 but you're going to average over only some number of them so a classic example is the stock market。

Every day， actually， every millisecond， bullets imagine every day stocks have a certain closing price。

And I may want to calculate a 30 day moving average。So what do I do， Well。

 I have to keep track of 30 days worth of that stock data。

And then I can take the last 30 days and his average amount and come up with an average。Okay。

 it's a moving average because tomorrow， I'm going to do the same thing。tomorrow I'm going to take。

 well， I'm going to take these 30 pieces of stock data I have。 I'm going to kick out the last one。

Okay， and I'm gonna move them all down a little bit and add in whatever tomorrow's stock price is。

And now， I'll have 30。Pieces of data to average over and 29 of them are the same that I used for today。

I just have gotten rid of the latest and added the earliest。

Now we could do this with our samples that we've gathered around trip time right I'm going to collect a bunch of these samples I could make a moving average of those。

The trouble with that is that means I have to keep track of 30 values。

 I have to have this array that I'm managing of 30 or however many values。

And so one thing that's commonly used is instead of having a moving average of the actual samples。

 use what is known as an exponentially weighted moving average。What this does。

 it's different from my stock example， in my stock example。

 all 30 of my samples were weighted equally when I calculated the average。 I add up all 30 of them。

 I divide by 30， right， exponentially weighted。Means I don't have to keep track of all of them。

 but it also means that the most recent have the most weight。So when I'm averaging things。

 it's not actually averaging them all equally weighted。On the other hand。

 the formula is really easy and I don't have to keep track of an array and manage all that stuff。

So what do I do， Well， I have some number that is my estimate。And when I get a new sample。

 I want to reccapulate the estimate right it's kind of like I want to calculate tomorrow's moving average for this stock。

Ticker， right。 So I take that estimated value。And I take my sample， my new value。

 and I throw them into this formula， right， whereasas I take  one minus sum parameter alpha。

 I multiply by my estimate， and then I add in that estimate with that weight of alpha。Right。

 so I'm discounting everything that's gone before by some parameter value。

 And that's the weight of this new sample that I'm adding to the mix。

 And then that result gets put into。Becomes my new estimate of the round trip time。

OkayTyp we're going to use 1/8 as our value for alpha， which。Implies something about the weight of。

Of how much I'm weighting current values versus past values。Okay， so every sample is going to。

 at some point， be multiplied by one/8 and added in。

 but then it's going to be multiplied by  one minus by78s over and over and over and over again。

Until eventually， its weight， it's still technically there， but only in a very small sense。You know。

Six0 or 100 samples later， it won't have that much of effect on the actual estimate。Okay。

 so this is now how I estimate， this is now a number。

 I think the round trip time is about this value。I' have smooth out that I've got around a value for the round trip time。

How do I use that to set the timeout？Well， certainly I can't use that。

 the timeout cannot be my round trip time estimate。If it was。

 there going to be a lot of times where my trip time is more than that estimate and I'm going to re transmit。

So I need a number bigger than my round trip time to be my timer that。

Bigger part is some safety margin we're adding in。How much bigger， That's the real trouble。 Okay。

 Well， it turns out if you spend some time looking at this。

What you want is you want a larger safety margin if the actual network is more variable。

Look at the converse of that to help understand it。

 Let's imagine our network was rock solid all the time。 exactly the same round trip time。

In that case， you could set your time out to be just barely more than that right if your round trip time was always。

 let's say 500 milliseconds。Okay， my timeout could be 501， and I'd be pretty safe。Right。Okay。

 but let's imagine now that I have a huge variance in that right。

 my average is still 500 milliseconds。But a lot of times it's 50 milliseconds， a lot of times it's。

You know，1 thousand0 milliseconds。RightSetting it for 501 is crazy then。

 because I'm going to have like half of my。Of my seven segments are going to need to be retransmitted。

So if there's a large variation， then I would like to set my。

By timer further away from my estimate of the round trip time， I need more safety margin。

So what do we do there？We can calculate how variable is my network。

 how much deviation is there for any particular sample from my estimated average。Alright。

 and so what I'm gonna do is I'm gonna take。 Let's go ahead and take the sample that I get each time and see how far away it is it from my estimate。

 So let's subtract the estimated round trip time。 Take the absolute value。

That tells me how far they are apart。That's a measure of deviation。Or variation。Right。

 so let's go ahead and。Well， turns out that variation also is all over the place or could be right so I need to smooth that that's just one measure of estimation of variation。

 so I'm going to go ahead and smooth those values as well using the exponential way of moving out average algorithm。

Partially because I've already got the code in the code base to do that， right。

 So it seems reasonable。 Typically， we set the parameter， though。

 to be a quarter instead of an eighth。But otherwise， I do the same thing。 I go ahead。 and now I。

 I have a。And a moving average of what my deviation values are。Okay， so that tells me， oh。

 your network is this。This deviant， this far away from the average estimated round trip time。Okay。

 and if that number is big， then I want my timeout to be further away from my。Estimated。

 and if it's small， then I want it to be close。And so I actually set the timeout value to be the estimate。

Plus， four times this deviation。Okay， so fly 4。It's another votdoo constant seems to work。Okay。

 I would like some safety margin。 And so since。estimated is something that varies a bit。

 and the deviation is also something that varies a bit。

 Let's go ahead and tack in that safety margin related to。过。Yeah。That's a good question。

 I think it's a coincidence that I'm multiplying by one fourth， I'm sorry for Z。

 the question was hey four and hey， beta is one over four， are those related。

And I think it's a coincidence。I think the four is there again because I want some safety margin。

From this thing that is moving around a bit。🤧B。Now， I want to point out。

This is the place we've gotten to， but earlier versions didn't do this earlier versions。

Just took that estimate and multiplied by two。And said， oh， here's my estimate。

 my estimate around trip time is 500， I'll set my time out to be twice that。

OkayAnd that meant that our safety margin was always static。

And it turned out that wasn't adaptive enough if the network is。Nice and steady and solid。

 Then that was too much margin。 But if my network varied a bunch， it wasn't enough margin。

 And so that's the reason we， you know， we go with this four times。

 And this is something that we do care quite a bit about。 if this value is set incorrect。

 then that means you're gonna be retransmiing more than you have to。

 All those slides where it said premature time out。

 right That would be because you didn't estimate the round trip time properly and set the time out based upon that properly。

 You had set it too short。 which we care quite a bit about。Okay。All right。

 so done with congestion control for today， we got at least two more lectures talking about some form of congestion control。

 though， congestion control has these different chunks， these different pieces。

 so make sure you understand slow start we begin， we exponentially increase the congestion avoidance Once I am at some level where I've hit my threshold and I think I've got the right amount of bandwidth I still want to probe for more there might be more bandwidth available。

 and if there is I'd like to take it。But if there ever is not。

 then I need to get out of the way of the network of the router quickly and let the router have a chance to get back on its feet。

 and so we multiplicativeably disc。Decrease our congestion window in those cases。

And then we talk about how to actually set the timeout value and the difference of what's going on based upon that。

The loss is from a timer versus triple to Kak as well。Alright。😊，Do have any questions？

send using is in the so。And the send is。真的是必须的 start。I'm sorry。 Is this Reno or Tahoe。

 Let's see if Reno。And reno if there are triple du good acts。Then you divide by half。

I think he's asking what is the S experience。Oh， so if they're in slow start phase and you see either loss event。

Then that's an indicator that you've hit。The limit of things。Okay， and you will。Let's see。Yeah。

 I think I can't remember what Reno does or Taho does。

 I think Reno at that point goes ahead and divides that in half。

 that's the divides the threshold in half and goes into congestion。Oh control。

 So that is we thought that the cancer slows out in does not mean that we slows out。应该是比得这个可以的。然后。

Reno does， again， I'm not sure I understand the question or I've got the entire question。

RightReno is different from Tahoe in that it it。Looks for the triple duplicate acts。

Right is that and that's a question so when there is a triple duplicate act。嗯。We're going to go。

 we're going to divide by half and we're going to stay in congestion avoidance phase。Oh。

 so if you're in slow start at that point， yeah。Yeah， so if in Reno， if you're in slow start。

When you see triple duplicate acts， that's an indicator that。嗯。That that， you know， that you're good。

 I mean， you have a loss event， but it's not terrible so。Move into congestion avoidance。

And do that immediately by dropping， you're still going to drop your congestion into it half。

In if you were in slow start in Tahoe and you saw a loss event。

 then you go back to one and start over。If your inss start in Reno。

You don't always go back to one and start over。Does that answer the question？Let's see。

 Does slow start take action when the congestion window drops to zero during the transmission。

 I'm not sure why the congestion window is dropping to zero during the transmission。

 Congestion window is a output of slow start。And so if you're in slow start。

 you are controlling the congestion window。And so you never put it to zero。

 you might put it to one if you have a loss event。And if Ben。

 maybe they're saying if the trend throughput it goes to zero。

You're going to get a bunch of loss events， and so you're going to kind of get pounded down to。

To keep trying sending one as your congestion window。Okay。All right。Any other questions。Alrighty。

 then， thank you very much， everybody。Have a great weekend， we'll see you next week。

For a little bit more congestion control。

![](img/7bf57d0ac982683bdaa862a7ffdc892f_14.png)

Yeah。

![](img/7bf57d0ac982683bdaa862a7ffdc892f_16.png)

哦。

![](img/7bf57d0ac982683bdaa862a7ffdc892f_18.png)

Yes。