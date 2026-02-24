# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P9：-9- Flipped Lect 2 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Okay， cool， hi everyone， we're going to get started。

Can actually ask the people that are sitting in the back to come move up to the front。

I would greatly appreciate that。Okay， so I'll start with the audience， I am not Sylvia。

My name is Alex。 I'm one of your Ts。嗯。And for this second flip lecture。

The TAs got together and we thought it would be nice to give you a lecture from the perspective of someone who took the class recently and went through the material recently。

And talk through some of the things that we found confusing when we were learning this material not too long ago。

嗯。No。This lecture is prepared by me Naic and Sarah， so two other TAs。

I happened to take 168 here some years back。And they took the equivalent at their undergrad institutions。

 and so that's what we're basing our content on。So I'll start with some announcements。1。

Starting this week， in person lectures are back， so no more videos to watch before coming to lecture。

And so we'll be lecturing。Me being up here as a flulo just。And two。

 the other really exciting announcement is that Project1 is released today immediately after lecture。

And。I'll share some more information about this project。

You're going to be implementing a distance vector routing protocol。And in particular。

 what makes this really fun， why I like this project so much is you'll be working with a simulator that Murphy Mcauley and past grad studentss in Neus have Britain。

 where you'll actually be able to see exactly what is happening in the network。

So I have a little video from when I was working on this project over the weekend。It's very fun。

 the simulators all jigglely， you can move all the nodes around。

 you can see all the packets as they flow， you can send packets from some host to another host。

 and you're going to be responsible for building the routing tables to make an arbitrary network function。

 which is really cool。So the project is split and scored by 10 stages。

 and the goal is going to be effectively to derive each of the changes that we learn to distance vector optimizations to distance vector。

 starting from just basic packet forwarding， and then understanding why we need things like split horizon。

 poison reverse， rat poisoning， etc。It's going to be due at midnight on October 7th。

 and all of the information is going to be on Ed。At 12 immediately after that。Yeahep。

And as people come in， just if you can come and sit in the front。Thank you。

I'll just also give a shout out here at the Silverver Tenon and Ken who are the project TAs for this project。

 and they've been working really hard to get this ready for you and to get it released。

 and they will be the one supporting you。 so this is important if you have questions during while you're work on the project。

Come to project office hours， not the content office hours。

 So they specifically have lots of project office hours to get help。

Are there any questions about this？Project release。こ。I'm actually going to start with a few tips。

Briefly that you should think back to as you start working on the project。

 just because I was just working on this project and from what I took it in the past。

Given that the project is made up of these stages。Later stages are going to require you to go back and edit your earlier code。

 so I highly recommend that you comment your code in the earlier stages because you'll have to go back and edit it。

😡，And very quickly， we forget what our code does， even though we just wrote it。Very handy。嗯。

Remember that when a node receives an update， if you are told that your neighbor has a path to some destination with some cost X。

Your path to that destination， if you choose to use that route。

Is x plus your distance to that neighbor。So you have to keep track of。You take。

 however far your neighbor is from the destination and add your own distance that to that neighbor to get the total cost that you store。

And that was just something that bit me when I was working on this。嗯。



![](img/37f8b034ff227ec877845f564dd5571d_1.png)

And a higher level comment to say that this class doesn't have that many assignments。

 right we have two projects。One kind of homework is thing that' will happen later in the semester and two exams。

And so this is your chance to really get very comfortable with these concepts of split horizon。

 poison reverse and route poisoning。And how dis inspector works。

 because when it comes time for the exam， that's where we're going to apply these concepts and kind to stretch them more。

And so really make sure for each of the parts， you understand why what's happening is happening。

And if you just follow the PDF， the instructions， it has questions to help you understand as long as you make sure you're taking the time to answer those questions for yourself。

Something that helped me do this is when I was thinking through things， I logged what was happening。

 So whenever I was writing an update to my table， the routing table， I logged that I was doing that。

 and then I could really think。Look at the sequence of events and try to understand why the sequence was what it was。

So。嗯。And my last tip for you is that。呃。The simulator is a Python terminal。 It's interactive。

 And so actually， while the simulator is running， while you have that little visual section。

 you can also refer to each of the nodes。Buy their actual names like S1 and view the routing table live。

You can do print S1 do table， and it'll show you the exact like iners of your routing table。

 So it's really handy for debugging what's going wrong。Okay。

If there aren't any questions about the project， then I will get started on the section of lecture what I found confusing about routing and hopefully how we can clear it up。

可。

![](img/37f8b034ff227ec877845f564dd5571d_3.png)

So every semester。Students get confused about this。 They get confused about all these new terms。

 split horizon。Rap poisoning， poison reverse。And in particular。

 I see these questions very frequently。People ask what combinations can you use？

Which one of these three is the best？What is route poisoning versus poisonverse， the naming。

 the fact that it's so similar doesn't help。嗯。And of course， even within。

Split horizoniz versus poisonverse。 What are their differences。

 So let's take the time today to clear those up。I'm going to set the stage first to remind you。

 this has already been talked about in lecture， but why are we doing this in the first place？

So the core problem that we're trying to solve with routing is coming up with the rules for how we're going to forward packets。

So as a router， you get a packet。You look at the header。

 and your job is to decide to get this packet to where it needs to go。 What do I do with it。

 Which neighbor do I give it to。Routing as a problem is how you come up with those rules。So that。

The actual decision making process of who I should give this packet to。

Defining how you make that decision。And you have to make these decisions with some sort of requirements in mind。

In in particular， two very reasonable requirements。You probably want full connectivity。

 meaning that as long as a host is part of this core connected component of the graph。

 as long as it's concept like theoretically reachable。

 it should be practically reachable from any part of the network。And2。

You probably want to minimize latency， so get to your destination as quickly as possible。

 Don't take some very convoluted route， Take the shortest path to the destination。

I'll point out this routing is happening in the control plane of the network。And so really。

 the function of our network is broken up into two pieces。

We have the data plane and the control plane， and the data plane is the actual process of you get a packet。

And you're going to look up and give it to a neighbor， the actual process of handling that packet。

The control plan is making a decision of how you're going to handle that packet。

To which neighbor you should give for a particular destination。

 that sort of decision making is part of this control plane。So so far。

 we've been talking about link state and distance vector protocols as a two of our approaches。I。

Don't necessarily find Li stay easy， but I find distance vector harder because。

We start off with some general set of rules and we add these little optimizations。

To kind of make it function better and better。 And so especially because our project is focused on distance vector。

Let's talk about distance vector today and save Li state for another time。

 So if we have time at the end， I'll take questions on that， too。

So what do we do for a distance vector？It's two simple rules。One says。

Every node is going to tell each of its neighbors its distance。To some destination。诶。嗯。Y。

 as a speaker。And so R1 is going to tell all of its neighbors， which here happens on the screen。

 just happens to be R2。 Hey， my distance to D is 1。Our three is going to tell our to， hey。

 my distance to D is 15。And by the way， where does that 15 come from。

 well maybe there's kind of a path off screen here down below through some more convoluted parts the network that eventually makes it back up to R1 and D。

And so as speakers， every node is going to broadcast tell all of its neighbors its distance to some destination。

And then as a listener。Every node takes in all these updates and decides which of them it should use。

 which advertisement it should。Used for its route。And that should be an easy decision。

A cost of one to get to the destination is better than a cost of 15。

 and assuming that R2's cost to R1 and R2's cost to R3 are both the same， they're both one。

 we should take the shorter route。What are some problems that we're going to run into？Well。

 generally， our problems in network are caused by some sort of invalid network state。

So I'll actually turn to you and say。What are possible sources of invalid networks。

 what are issues that we can run into？It's going to cause us to not about optimal。Yeah。Yes。

 we do have problems with links going down。 I agree。

 And what's the result in the actual routing state。 So in these tables that we've built。

 what happens。イやス。Yeah， I agree with that。 You get state where someone thinks something exists when it doesn't exist anymore。

 and that'll be a problem。Someone else had their hand up。I thought。条。

Any other problems you can think of。有。Yes， looping。

 so we can get into this unfortunate situation where。

Both nodes think that the other has the shortest path to the destination。

And then when they get a packet， they hand the packet to each other and the packet goes back and forth。

 and that's a problem。I agree yeah。Yes， and in particular。

 that does happen when we get some sort of kind of looplooping behavior where I tell you I have a path。

 and you tell me no I have a path and we go back and forth and so。

These are all problems that we're running into yes， thiss great。

So I've kind of written these down for us to walk through。And I framed them in。These three groups。

The first， I'll say missing entries。 And what I mean by that is no one really mention this， but。

For completeness's sake， it is a slight problem if there does exist a theoretical path to some destination。

 but a router doesn't know about it right so there is some host that's attached on the other side of the network。

 but I as a router don't have a path to it， even though it's theoretically retrievable and that's a problem and we'll talk in a second about how that problem comes to exist。

Then someone else mentioned loops， and this is exactly a problem。

 we can get into a situation where two routers think that they are each other's next best hop。

But in that case， the packet is never going make it。 And that is a problem because。

We now have lost kind of from that starting from those nodes， you can't get to your destination。

And finally， I think you mentioned this stale network information where not everyone knows about a failure that's happened。

So。Drilling into these missing entries。What might lead to this happening？

every router is following these two rules for disinspecor we just talked about。

 and they're all honest。And so they're going to tell their neighbors what their。

Distances to destination。How would it be that not everyone knows？Anyた？Yeah。Right， right。

 so remember we have this issue of our underlying network。呃。deliveringing best effort。

 some packets can get dropped。So you have this problem where you could tell your neighbor。

 but your neighbor might not hear it， not because they're ignoring you。

 but because the packages doesn't make it。So that's definitely an issue at the time it gets wrong。嗯。

I have another one here for completeness， which I think is a little unfair just to say。

 maybe the destination is actually unreachable in your topology。

 like a link goes down to some destination。Or it's kind of not part of one overall connected component。

 and I just have it here for completeness。嗯。How do we solve this advertisement getting dropped issue？

我的。Yeah， as long as we resend every certain number of seconds， right， as long as our link。

Is not always dropping packets。 It has some percent chance of making it。 that if we just keep retry。

 eventually， the packet is gonna make it。And so that works really well。 actually。

 we just retransit every X seconds。呃。However， if the destination is unreachable。

There's not really any fix for that。Your only option is to get the network connected again。

 And so that's not really something we can fix with routing。这过。

This first problem we have a solution for， we're going to retrans advertisements。

But what do we do about looping？Its be important。In particular。

Can give me a kind of a succinct description。 What causes a loop， I mean。

 how do we get into the loop。Or once we're in a loop， why are we in a loop？

I someone said something very similar。This earlier。Yes， so I think you're answering the question of。

 hey， does this kind of how do we stay in this loop， then maybe mechanically back and forth。

 why do we accept updates？All very true。 I was looking for even more broadly。

 a direct loop means that I think that I should give my packet to you and you think that you should give your packet to me to have forwarding tables that kind of point at each other。

 that's very unfortunate。And so how do we actually get into this scenario， Well。

 imagine you have a network like this。And here， this is all valid。A valid forwarding state where。

To get to DR3 thinks I need to give my packet R2。To get the D。

 R2 thinks I need to give my packet to R1， and R1 is directly connected to D， so this will work。

But we run into an issue where if a link goes down。Well， eventually。

Art 2 is no longer getting updates from R1。And so its entry is going to time out。呃。

But R3 is going to advertise saying it has a path destination。That advertisement comes in。

 and R2 is pretty happy about that because it no longer has any way to get the D。

 And so it's very happy to hear that R 3 does have some sort of way to get the D。So great。

 R2 accepts that says my next stop is R3， cost of four。Which was the cost of our three plus the one。

One hop cost forget to。呃。And unfortunately， this is just going to go on back and forth。

 they're going to keep passing these updates to each other。

And up A costs count all the way up to infinity。It's a six。seven。And。It's continues forever。Okay。

 now finally we can get to talking about what the confusing parts were routing from me。Specifically。

 this is the class of problem， or at least how I think about it of what split Horiz poisonverses are attempting to solve。

We're trying to prevent loops from happening。And if they do come up。

 making sure that we get rid of them as quickly as possible。So splitizing comes in。

And the rule was what Horizon says。If I have a route through you， I will not tell you about my path。

😡，I will not tell you about that route。Because why would I ever tell you about a route that goes through you if I tell you about it。

 you shouldn't ever have to use it If you do have to use it， wear're in a loop。

 because if you give me a packet， I'm going to give it right back to you。嗯。

And this sounds pretty good。 I mean， in fact， if we walk through what happens here。

Same light goes down。Same forwarding table entry times out。But then。

Ds just not going to say anything。Sorry， R3 is not going to say anything to R 2 about its path to D。

And so eventually our threes path time is up， sorry。嗯。

And now we're in a state where neither R2 nor R3 has a route to be。

 and hopefully someone else in the network sends an update to R2 or R3 saying they have a custody。

And at that point， we can accept that new path and our network can reconverge， hopefully。

Does this work？Doess everything worse sometimes。Second。They don't have a more opinionated answer？

I mean， I think it works。It should work， yeah， ideally。

So it does work in the sense that you can't really have a direct loop form in this case。

But there are still edge cases。Where。You do gets direct loops forming。You saw one in。

A previous lecture that Murphy did。Where there were two routers talking to each other that had a path through some third router。

 They both went through the third router。When that third router went down。

If the timing comes out just right where。Our1 and R two tell each other about their paths through that other router。

And the routing entries expire at the same time。 You can get into a state where they are now sending packets to each other again。

 So there is this edge case。 And you'll see it very closely on the project。And so。呃。

Split horizon works to provide。Many kinds of direct loops。

 but there are still edge cases where they can come up。And what happens in those edge cases？

 So let's say that with one of these edge cases， we get into this。

Its an area where R2 is wants to give its packet to R3， RU wants to give it to our2。

Split horizonizon does get us out of this issue where R2 is not going to tell R3 about its route and R3 is not going to tell R2 about its route anymore。

 now that they're point at one another。 And so eventually the two entries time out。

But we have to wait an entire time to live。 So the entries actually have to time out。And remember。

 T T Ls are like。Usually considerably greater than advertisement time。

And so we're in a loop for a little bit of time。So this is where poison universe comes in as an optimization。

So that's an improvement on split horizon， and it says。Actually。

 instead of just being silent about my path through you。

 I'm going to actively tell you that I have an infinite cost path。哎。So if I'm going to route for you。

I'm going to tell you have an infinite cost path and often you'll hear this talked about is lying。

Why is this conceptually lying？Because you do actually have a path that is less than infinite cost。

 But you're going to say it's infinite cost to make sure that in no world is you never going give you a packet。

行。And all routers， like who's going to send a packet on a path of cost infinity？

And so what happens is。Assuming we somehow got into this state。

 You can trust me that there these edge cases you'll see on the project。

 once we're in this kind of looping state。If D is R3 is going to send an update to R2 saying that it's cost to D is infinity。

嗯。Our two has to accept that， by way。Right，Some pointed this out earlier。You might wonder， well。

ops well， why is R3 going to accept a path with cost infinity when it has an entry with a cost of two wass because that update is coming from R3。

 which is R2's next top。So as soon as your neighbor says you have a path to your neighbor and they tell you their cost has gone up。

 you have to accept that because that's new information。 That's better information。

 And what you have is outated。嗯。And so that gets set to infinity。D is also sorry。

 R2 is also going to tell R3 about its path to R3， saying it has a cost of infinity。

And so very quickly。Both entries are now no longer used。

That makes sense of how we get out of the scenario。I just want to really highlight。

 we're getting out of the scenario in the amount of time that it takes to send a new advertisement。

We don't have to wait for anything to expire。So that's already an improvement on split horizon。So。

 to really concretely answer this question of what is this difference between poison reverse and split horizon。

 Mechanically， I've showed the difference。But intuitively。

 they should be preventing the same kinds of direct loops。 they're both equally good at preventing。

But in the case that we do get into a direct loop that they don't prevent。

Poison Ever squashes those loops much quicker than split horizon。Because you actively tell。

Your you' neighbor through whom you're routing that you。You have a cost of infinity。

 so don't ever send me a packet。Yeah。No， I think when we actually implement this。

 if you have a cost company， you don't stand along that cost。But even if you did， I mean。

 the point is that if the destination is actually reachable。😡，Someone else's update will come in。

 And if anyone else has a path， it's going to be less than infinity。

 And so you're going to take the route through someone else。

The problem is while you still have your old update， I'll just point this out。

 this is a good question。While you are in the state， if someone else tells you， oh。

 I have a path to D with cost。😡，Six， you're not going to take it because you still think that our three has a path。

😡，With cost 2。 So the quicker we can change that to say infinity。

 the quicker this router is able to accept updates from other neighbors。呀。

One downside to split horizon is that's poison versus that's chatty。 right。

 It's going to send kind of。It's going to send us infinity instead of being quiet。

 but the difference is negligible in amount of traffic。So no， I't think I can think of her。

Any other questions？诶こ。

![](img/37f8b034ff227ec877845f564dd5571d_5.png)

Okay， fun， aside。 Can anyone guess why it's called Sp Horizon。

I was able to find this kind of cool picture of an actual split horizon engine。On Reddit。

Everybody has everything， yeah。Okay， yeah，'。By breaking a loop。

 you're having the two neighbors take other paths。 That's a good guess。No。But I like that。

Any other guesses？对呀。It's like a boundary between the two neighbors that don't talk to each other。

That guess。No。

![](img/37f8b034ff227ec877845f564dd5571d_7.png)

，I'll review it。I looked this up and in the original paper。They describe。Like the。

Forming of an update of。Like all the paths that you have is kind of your horizon。

 And I imagine it's like you're a node in the graph。And you look outwards。

 and I guess that's kind of like your horizon， like how you get to everywhere else。But specifically。

 it's split because you're omitting information to a particular neighbor。

 And so different neighbors are getting kind of different views of your horizon。Particularly。

 the neighbor through which you're going。Is getting a。You leave out the。

Pas the routes to destinations that you use that neighbor for。

 And so each neighbor is kind of getting a different overall view of your horizon。

The paper also describes this term as a whole horizon， which is like without split horizon。

 if you're sending everything it's called Who horizonoron， we don't use that in this class。

It's kind of cool。Okay， we've solved our looping problem。 That's great。Yeah。这个 questionion。

Let's think through that。 How would we go about implementing both split H and poison review？

So what does split Horizon say to do？You have a route through that neighbor。Don't say anything。

 What does poison reverse tell you to do if you have a route to that name？Say something。

You cannot do both， yes。RightYou can't both say nothing and say infinitefinity。Yes。

 you want to know that。要。Yeah。We will。But but this is as we're like we're drivingring kind of step by step as we get kind of cleaner and cleaner solutions。

Okay。就。Let's deal with this last problem that we identified。 Stay on network information。

 So how do we get into the state。嗯。Any change in the network state is going to be an issue for us。

 right？It takes time for this information to propagate through the network。And in particular。

 I'll point out that different classes of information take different amounts of time to propagate。

And so these are terms that。

![](img/37f8b034ff227ec877845f564dd5571d_9.png)

I mean， I don't think Syl uses in this class， I just have painted it this way of kind of like additive information。

 like someone comes up。So information that you didn't have before， new information。

Versus subtractive information， meaning information that people had that now needs to be revisedd or removed。

And specifically。呃。Additive information propagates as quickly as the advertisement frequency。

And so as and that's relatively short， I mean， we're going to be because we want to resend updates。

 we're sending quite quickly much quicker than the time to live。Subtractive information。

 So information gets removed。As quickly as it can expire。

 and that's always longer than our advertising frequency。And so in particular。

 we get this issue with information about。A router crashing or a link going down。

 or hosts being disconnected。Once someone has told you about this。

 that's not going to get removed from your table until it expires。😡。

So what can we do to improve this propagation time？

So this is the separate kind of slightly orthogonal problem that routeut poisoning is trying to solve。

And the key observation that we saw with Poverse was。You can override a neighbor's time to loop。

Right。By sending an advertisement that has infinite costs。

So rather than waiting for someone's information to expire， you could actively tell them。

This information， this host still exists， but the cost is infinity to get。Through me。

And so we're going to take advantage of that to try to get to a place where we converge more quickly。

 where information spreads the network more quickly。So。Now with route poisoning， the rule is this。

 when you lose a route for whatever reason。😡，Instead of just deleting it from your forwarding table。

😡，Tell all of your neighbors that your distance is now infinity。And the rule should make sense。

 you want to actively tell other people that now you can't reach that neighbor anymore。

And try to update their tables with a cost of infinity。And so， we can。Yep。

 we can walk through a case here where。We had our ballot set up here。R2 R3 sense R2， R2 to R1。

 R1 to D。And。Unfortunately， this link goes down， so R wanted D goes down。

And I wanted these post links it's going to detect it。And so it sets its cost to infinity。



![](img/37f8b034ff227ec877845f564dd5571d_11.png)

Well。Following route poisoning。R1 is going to advertise that infinity to R2 to let R2 know that it has a cost that R1 now can no longer reach D。

And then D is going to update its table and say infinity。And， sorry。

 R 2 is going to update its table to say infinity to D。

 And now R 2 is going to advertise to R 3 and say， hey， my cost to D is now infinity。

And that's going to continue onwards。And I just will point out。

 you actually kind of get this for free in the implementation。

Because as long as you just store infinity in your table。If you were to remove the entry。

But by storing infinity rather than a removing entry at the next advertisement period。

 your code by default is going to advertise infinity to the next neighbor。

So you'll notice in the implementation， depending on how you implement earlier stages。

 when it gets time to implement route poisons， you may not actually have to change one。

Any questions on rat poisoning？呀。Sorry， the next advertisement frequency that you。

So the question is why should we even wait until the next advertisement frequency。

 Why don't we send right away when we hear about infinity？And in fact。

 that'll be the final optimization we're going to say exactly that。

 Why should we when wait till the next advertisement period。

 let's just talk immediately when we find out about that information。Any other questions？

That is a great observation。 So in this particular case。Because it's kind of to the host。

 remember that hosts don't participate， they're not like speaking or sending updates。

 so someone went in and like hard programmed a static route that has a detailed of infinity from R1 to D for the direct next hop and so。

R1 needs some sort of method to tell that its's linked to the host went down to update that cost infinity If however it was a link between two routers。

 then yes， you would have to wait for that initial TTL like the time to expire and after that things can propagate as quickly as advertisement。

That's a great time。Other questions？呀。Yes， how is this different than poison rivers？嗯。

Let me come back to this in just a second。 I have a sliding exactly that。Just a second。So。

We now have a solution for our third problem， more or less。

I realized I just wanted to point one thing out that I had on my slide here that I forgot to say earlier。

Split horizon and poisoner verse。They really help us with preventing and squashing direct flus。

Meaning a direct loop is where I give my packet to you and you give that packet back to me。

They're not used for handling cycles where I give my packet to you。

 you give it to someone else and they give it back to me。

So we actually need a different fix for those kinds of loops。まから。呃。O。So we had whoops。

These are the three questions I listed earlier that were always confusing to me。

 And I find students get confused with easily。What combinations are these going to use。

 which one is best and rock poisoning versus poison reverse， which I'll have a nice chart for them。

So which compos can I use？Well， luckily， this came up as a question earlier。

 you can't use split Horizon poison risk at the same time because they conflict。

One says say nothing and the other says say it cost infinity。

And so your options are for these two classes of problems， pick one of these solutions or none。

And so to be kind of really。Precise or pedantic。These are all the options you have。

 where you pick either split her eyes in poisonous or nothing。And rat poisoning or nothing。

You don't need to write these down， you have to memorize them。

 This is just to point out these are the combinations that are possible。

Ands put it succinctly something from that7 on the left crossed was something from that side on the right。

The other question I see people asking is which one is best？

And I think there are different tiers to this question。 Some people are asking which combo is best。

 but others are asking actually of the three， which one is the best。And I think it's a slight。

Incorrect assumption when you ask that， because you can't compare all three。

Split horizon poison reverse to address one problem。

 right poisoning is kind of addressing a different orthogonal problem。

And so maybe the better question is what combination of them is best？And。put it shortly。

Better to use some strategy to solve a problem than none。And it's just rat poison here or nothing。

 and for loop prevention， poison arrest was just as good as split horizon， but when loops do arise。

 direct loops arise。Poisoner virus squashes them more quickly。嗯。

So I't say poison and out poison are the best combo。Finally。

 for comparing rat poisoning and poisonverse， what is the difference？So they are solving。

At the end of the day， we're all trying to decrease convergence time。

 how quickly a network gets back to a valid state。But in my mind。

 they're kind of solving slightly difference。Problems。

And so while their mechanism is the same of sending infinity。

They're triggered by slightly different things， so Po reverse。😡，Says。

If I get an advertisement from a my neighbor that has a lower cost than me。

Then what I currently have to get my destination？I will from now on tell that neighbor that my path to that destination is cost infinity。

I'm going to lie to that neighbor and only to that neighbor， no one else。Whereas。

Roout poisoning says， if I lose a route altogether， not that my route got replaced。

 but that I lose that route。😡，I'm going to tell everyone immediately。

That I no longer have a route to this destination。Does distinction make sense。

And so even though they're both studying infinity， they're also doing it slightly differently。

For round poisoning， you send infinity to everyone around you to that destination because you actually have no path to that destination。

For poisonerverse， you're only going to tell the specific neighbor that you have a route through that your cost is infinity。

 Everyone else you tell the truth to， whatever that cost you。Does that make sense。嗯。O。

Now for a split horizon versus Po diverseverse， I'm going to show one more kind of top down view on a network that maybe will help you visualize what's going on here。

 These are from Murphy's slides from an extra little slide deck that you made。We have this network。

 looks like this。All of our edges have cost one， and for now let's just focus on one destination because conveniently。

 as we think about all these things， additional destinations are just more layers of messages on top。

 The core principles， as we can tell is just one possible destination。

If we were to look at the best paths to A， that tree would look something like this。

And how do we know that these are the best paths， well， you can just kind of verify that。

The shortest possiblele path from 10 to the destination is one to three hops。

 there's no better path you can come up with on this graph。嗯。You could say， well， like。

 why does 9 go to 3 instead of to5， That might be an equivalent of Best path3。

 but we break ties consistently here by saying， we're going to take the neighbor that has the lower Id。

So。In a world without splitlin horizon or poison reverse。

Let's just focus on our router switch one here。When Switch one goes to advertise。

 it's going to tell everyone it knows， everyone in the world that it's connected to like each of his direct neighbors。

That it has a path to A with a cost of three。Everyone hears about that。

Everyone who is connected to one directly。In a world with split horizon。

It's still going to tell all its neighbors， but it's going to be silent to three specifically。

 won't say anything。啊。And in a world with split reverse。It's going to tell everyone。

 but it's going to lie specifically to three。 So instead of sending nothing， it's going to send。

 I have a path， but it's cost infinity。 So you better not give me any。嗯。And so。

If you just kind of step back and take a look， these are all the advertisements that are not sent to the split her ride。

And。For poison birth。It's the same exact kind of edges that aren't sent。But instead of not sending。

We send the cost infinity。And I'll point out this looks very similar to something。 In fact。

 this looks identical to the best path tree that we had at the beginning。

This should make sense because you don't send。Your updates all along the route that your packet is going to take。

And so。The updates that you leave out for split Hon or the updates that you send with a cost of infinity。

They will be on the same edges as your best path treat kind of look from above。Okay。

 I'm going to cover one more quick topic that I found confusing。 I like two slides on this。

 and then we'll take a break， and then we'll switch over to N's。Talk about。30。

So one other thing I keep seeing people ask， and I wondered this for a while too， was。

It seems like we need to do routing for both L2 and L3。So。Which should we be using？

We've learned about dis inspector。 We've learned about Lake State。

 We were also talking about learning switches。 So what should we be using。Well。

 L2 is responsible for local packet delivery and L3 is responsible for global packet delivery。

 And so the routing problem looks a little bit different in each of these domains。这的是这份。Well。

They both have the same kind of goal of a shortest path and to be resilient to failure。

But L3 is a potentially very large network。Whereas L2 is。

All destinations focus on all destinations in a smaller local network。

 and it's more plug and play where people in your local network are。Bring devices， move devices。

With minimal support。And so L3 has this property where it has to be scalable。

There's this whole question of addressing and how we handle addressing。Whereas。Now， too。

 is you have a small network and it needs to be operated with lower cost and like lower setup。

Difficulty。And so。We find that distance vector and Li state。2。

A better fit for L3 where they scale well。But they require some initial setup。呃。With addressing。

 which gives us some sort of static configuration。Whereas with a small network。

 we can use learning switches， which initially flood a packet。

 and N's going to talk about this in a second。呃。And then learn routing after packets get flooded as we see packets fly by。

And so learning speeches are a much simpler solution。 There's less setup involved。

 They're good fit trail too， This inspector length state are heavier。

 and they're better for they require a little bit more configuration。They are a better fit for L3。呀。

Well， for one， so far up until now， you've had to configure your。

 your like attachment to hosts directly。Like a network operator had to come in and say。

 you as a router， you have a direct link to this。Fill in that table and then let that property。再换。

Whereas with learning switches。People learn that they're connected。

 who they're connected to once someone speaks。呀。Yes。

 there isn't a separate protocol where learning Swers are talking to each other。

They are learning from actually seeing the data flow by。So if they're silent， they're not learning。

Before we go off to take a break， are there any other questions on routing overall？



![](img/37f8b034ff227ec877845f564dd5571d_13.png)

No。Okay。We'll take just。3 minute break， and then now it's gonna come up。



![](img/37f8b034ff227ec877845f564dd5571d_15.png)

Okay。Can people hear me too loud， too quiet？Hi so I'm Naic。

 I'm a graduate student here and also working on these kind of things。

 and today I'll talk about learning switches and the Spning tree protocol。



![](img/37f8b034ff227ec877845f564dd5571d_17.png)

So the goal is to walk through some examples with learning switches and the Spning tree project protocol and kind of stress what we have learned through the online lectures in Murphy's recordings and look into the corner cases of where the protocol。

 where are some interesting things that don't happen all the time。

 but we should think about and test our understanding that we understand the whole flow right。And。

Yeah， there will be a lot of these red boxes on the slides， which are questions。

 and then the goal is to get those answered in class。

There will be a green one afterwards with the answer。

 but please do answer them because all of this is review。 none of this is new material。

 This is from Murphy's lectures， but。We do cover some corner cases that。

Isn't directly in the lecture， so it could be good to go over them and test our understanding。

And Alex also had this， so if you have answered questions before and you want the reward。

 raise your hand。嗯。Yeah， I lecture should I give it to you to pass。And yeah。

 I'll try to propagate them with some algorithms。Read my questions as well。



![](img/37f8b034ff227ec877845f564dd5571d_19.png)

Feel free to use TV to pass these around。If not， if you remember how that worked。

So learning switches。This is a diagram that we' are going to use， the Ss S1， S2， S3 are the switches。

 and A， B， and C are the hosts， something like this would be familiar from lecture as well。

 where we were talking about learning switches。And the goal is to go through this and see how learning switches actually learn。

 like these S1 S2s are our learning switches， and they are going to learn about our endpoint。

And here in the process， we are going to go step by step and see how the switches。

Learn about the endpoints again just remember the distinction between these and the other routing algorithms we had used both Alex and Murphy had mentioned that these are kind of not c。

 so there is no preconfigured information， there is no control plane traffic all of these switches are going to learn about our endth but by just merely looking at actual data packets and data communication。

If this diagram right now isnt't clear， speak now because in next 30 minutes or so we're going to comfortably see this。

 So make sure this makes sense。So we now have this destination next top tables that the switches are going to maintain and in this learning process they are going to fill this in。

呃。DoDo we need a table here？行，关掉。嗯。Yeah， because these these are end hosts， right。

 They don't maintain any routing state。 They just have some traffic that they need to send and receive。

 and they are just doing that。Okay， so we now start with learning switches。

 There is some message going out。 A is sending out this message。 Who is this message meant for。

Can it be like S5？啊呃。Anyone because。喂。Yeah， messages are meant for anho。

 We don't send messages to the switches。

![](img/37f8b034ff227ec877845f564dd5571d_21.png)

![](img/37f8b034ff227ec877845f564dd5571d_22.png)

And then as as this is being propagated because just a data pair packet， there is。

 it is not control traffic。 It's meant for some。 like we said it's meant for B。

 And Epson receives this and is going to pass forward。 But before passing forward。

 is there anything that E1 can learn from this traffic。Yeah， so it can fill in the entry that。

It can get to A through its direct next hub。 It's directly connected。

And then since S1 doesn't know where to forward it next， It doesn't have an entry for destination B。

 It just is going to do this flooding that is by just sending this out on all the outgoing port。

 except the one of all the ports， except the one it came from。And as this packet propagates。

 the other switches on the road will also learn。Route back to 8。

 So this is just a regular data packet。 Nothing special in it。 But as it goes forward。

 it leaves this trail by which the switches learn how to reach8。And then typically。

 when you send something to an end host， usually the communication is society。

 B is going to send something back。 And if this happens， then on the way back。

 it is going to leave a trail of how to reach to B。

And then the switches on the way back will learn that as well。I fun。第一对准。Does anyone know？Yeah。

 it's just going to look up its table and it has a ro already。I'm sorry I one。

Am I doing bad with the canvas stuff。Okay。So now let's say we have a new host D that's being connected to S1。

嗯。And then A is sending a packet to D。 Would this be flooded。You seem determined anyone？

Do we have notes？I don't know if I should throw and。I another role here。Yeah。

 so it might be confusing and shouldnly because it doesn't know， even if it's directly connected。

 it hasn't been really quick configured to know about this route。In distance vector。

 we said that these are directly configured and we go and we say these two are connected to each other。

 but in learning switches， this is not the case。Nothing is directly nothing is preconfigured。

 And even if it seems that it's directly connected， and still doesn't know about it。So， yeah。

 the answer is it would be flooded。So if we say the N hosts D never sends。

 when will the switch actually learn about B？我子。Which one。Who responds back？Oh。

 the assumption is they never send anything。So yeah， when D never sends anything。

 it'll never the switch will never learn about it。合是。Okay。

 so we remember from lecture that this is all good until we actually have loops。And then here。

 if we introduce the additional link there， we now have a loop and this causes a problem。

And the problem is that if now end up flooding， if A send something and S1 ends up flooding or if D sends something and S1 ends up flooding。

 then this flooded packet is going to go around and around in our network。

Is the problem worse when we have more than one loop？Yeah。

 it is bad in that we have some packet that's going to go around。 And then at some point。

 it its TTL will reach and it will disappear。What happens if we have more than one。Yeah。

 it will duplicate。Because every time there is depends up near this loop point。

 both of them are going to propagate them。 So we' are going to spend more and more bandwidth on this things。

So it's really bad because it can just consume all of our bandwidth。But。

So far we also previously had underlying topologies that had loops， right。

 both when you were considering Li state and when we were considering distance vector。

 the underlying physical topology， we often had loops。

 and we said it's a good thing because it adds redundancy。So how did we deal with loops there？

This is can be worth the answer。Splin horizon。Yeah， in Li state。

 we had sequence numbers when we were sending this around。 And in， in this vector。

 we weren't really flooding。So the same kind of thing doesn't happen。 If we have one packet。

 there is no point where we are actually duplicating it sending out twice。

Even even if we had loops there， even without split horizon， when we had loops in distance vector。

 we never duplicated packets because。We were just sending this hand pack as wrong。And for Link state。

 we had sequence numbers。

![](img/37f8b034ff227ec877845f564dd5571d_24.png)

And we don't have sequence numbers here。 but be here because， well， we can't。

 These are just data packets， end hosts communicating with their other end hosts。

 So we don't really have a control protocol。All of these are just data packets。So， we just。

So that we can't build the underlying topology for doing flooding with these learning switches。

And Spanish Shi protocolto is what's going to help us to solve this。

And spanning tree protocol helps us create a spanning tree on top of this loopy topology。

 which ends up being loop free。 So we construct some tree。

 and then we will only use this tree and assume the other links for now don't exist。

 We'll use this tree to do our flooding。So let's consider some end results of trees that we can actually some trees and see whether they would be valid trees or not。

 like let's say and then yeah， the legend there shows what different types of links are in the beginning we just start of we don't know where any link is in our spanning tree or not and then as the protocol runs。

 we either add them to our spanic tree or disable them and never send anything over them never fled over them。

嗯。This is one example of a tree。 Would this be a valid tree for flooding？This would be。

This would be a better picture。Maybe be harder loops， There's nothing there。 This is valid， right。

Yeah， would the span tree produce this， the span tree protocol that was described in lectures？

Because。So it keeps closer further ones。So which link would be different。啊。😮，Okay。

 we're actually going to run the algorithm。 So I don't remember on top of my head which one would be different。

 but it seems we at least agree。panning tree protocol would not produce this。

And have some understanding of why。呃。Yeah， one， one example。

 I think is that's what you were saying is S 5 would connect to S 2。

 We use daling instead of connecting to S 3。Right， and this is because we had this thing of breaking。

Using smaller smaller ideas of switches。This is another one。 would this be。

Produced by the spanning treey vertical。Yeah。Do we all agree？

So this would also not be the one that we end up producing。

This is the underlying topology we're using before we introduced the loop in the underlying topology。

 but the topology actually changed。The spanning tree that we would end up using in a span tree protocol。

Which may seem unintuitive， but if you follow the protocol to the letter。

 then you'll figure out that this is what's happening。This is an another one。Now， did we。

 did we do this。Yeah。Did I give away the answer by asking？Yeah， would this ever be pre？

Do we all agree？Yeah， what are the things we are talking。So we check that S1 is a root。

We do shortest path to S， to S1， and we break ties with lower Is。And yeah。

 this is the one that would be produced to it shortest path。嗯。Spning tree protocol。Is this unique。

Could there be others？Could we think about her？啊。Yeah。啊。

AAre you saying it is not unique or it is unique。 It is unique。Yeah。

 because it would be really bad if it wasn't， right， because we are running a distributed algorithm。

If different parts of the network sell it different。Of different trees。

 And they couldn't really do correct flooding on it。



![](img/37f8b034ff227ec877845f564dd5571d_26.png)

Okay。So we went through some examples of what these spanning trees look like that let's actually now run the actual spanning tree protocol algorithm as describing lecture and see how we end up with the tree that we said is are we will have to end up in the end。

So。As we said， we'd start with all the links being unknown。

 we don't know at all whether any of these links are part of our span tree。

or are not part ofpanic tree， and in lecture we went over rules of how we decide whether something is part of Hispanic tree or not。

 do people remember these rules and want to shut out or do we want to just go through them？O。

So we will go through the rules when we get to the relevant switches。So again。

 we have these switches， and each of them is going to maintain its own。

Like each one in the algorithm starts thinking they are the root and they maintain a route and next up to get into the root and distance to the root in the very beginning。

 when everyone thinks they are the root。What are the distance numbers？It's something like this。

 right。Each one thinks they are rude。Each one thinks they are their own next hub。

 and they don't have any distance。反真。How do we proceed？Yeah， and then these switches start talking。

So what happens when these two talk。Whoho is going to change their table。Yeah。

 what will the numbers be？Yeah， and the other numbers。So the triple app would be 441。Yeah。

 let's just when I say 441， I mean the numbers in that order。Okay， how about this one。

Who will change and what will the numbers be。我托的点。And here。とりあえまか。你该点一点。喂 I hear。

S 3 is going to be 1，2，1。 Yeah， it learns from S。1，2。嗯。

How about the other two if we have new people who want to participate。So somehow yeah。

 they communicate with each other。 And what will the final result in as far as50。Export。啊。😮。

Is it one。And that's true S5。No force。Yeah， that's one criticism。Yeah。

 the question was it seems we will end up disabling some links and there will be no traffic over them。

 isn't that bad because we are overusing some and others using others。

I think we will actually see a poem。A muphy。Arenret the values clear？Okay。

 so we started with unknown spanning tree protocol。 And now we don't really have a spanning tree yet。

 right， We just have。WeIt seems we elected a route that we all agree on。

 and we know how to get there。And what's our next step？Oh， okay， before that。

 we we I just chose some order for messages to communicate。

 What would happen if I had chosen a different order。Yeah。

 because we said it's unique and it's a distributed system。

 So that's one of the properties we would want to do。



![](img/37f8b034ff227ec877845f564dd5571d_28.png)

So let's do the step two now， we now have this information and we are going to use this information to disable certain links and then kind of insert certain links to be part of span tree and in the end the goal is to end up with span tree that we had before。

And so what we do here is just we go over all the switches and see what they can disable。

 what they can enable。 And in the end， we will see that the spanning tree that we said in the beginning。

 we would end up with emerge。So we are constructing this tree for flooding。 Let's start with S one。

Which links do we know definitely will be part of the span tree and which ones are definitely not that S1 at this point can tell。

对庭。Both of them， S1 has four length。So which both。啊哈。How about the other two。

I was one of the rules of the protocol right if we have links to hosts。So how links to。A and D。

Are in the span tree。And the other two。We don't know yet。How about that too？

That is disabled or enabled。啊哈。And this process continues S3。Anything else？S4。S5。

Does it do anything else？And see。And then。Yeah。Now we can disable the other two because they are not using it for their shortage path。

 right？

![](img/37f8b034ff227ec877845f564dd5571d_30.png)

If if we are doing it in this order， they'll be disabled。

And there's also this thing that we might be worried that in the end。

 maybe some links will stay in the unknown state。 But if you look at the protocol back carefully。

 you'll see that。If you chose this order of switches and added spanning tree items in this order。

 then。The the switch that has higher I will always。Either enable or disable any link。 So in the end。

 we will have no links with unknown states。

![](img/37f8b034ff227ec877845f564dd5571d_32.png)

Okay， so now we have a spanning tree。Not what the spanning tree is。

 so it is actually different from the very beginning。

Because we had added the loops and the loops made the Spanish Shi protocol to converge on this apology。

And this is a valid tree。 There are no loops， and so we can now flood traffic over if S1。

Did not know about a as one could safely flood over the spanic tree。

 knowing that there will be no loop。And then it goes receiver。Okay。

 so what happens when something fail。嗯哼。😊，So we no longer have a spanning tree rat。

 then we need to go back and construct it。Yeah。嗯。We start again as one being， would the root change？

Any yeses。Yes， but once we converge， who would the route be。对。So we would run the same thing again。

 the highlighted ones are the ones that end up changing after you run the same protocol。

 you can just trace it by yourself off the electricity。而这 question。嗯。😊。

I don't know how it's done in practice， but you don't gain much by keeping the previous information because as you'll see。

 the new tree can be drastically different from the old one， depending on what links fail。

In practice， you can do either。Was there another question。So yeah， here is that example。

 what happens when that second link fail。嗯，哼。😊，Who would the world become？As true。

 the one with Lo baby， right？And one thing also regarding the previous question to note here is that in this case。

 between S2， S3， S4 S5， we have a valid tree。That technically。

 we could just stick to that and use it as our span tree。AndIn the end。

 we are just going to have just an equallyly valid span chip between those switches。But。

Thepanning chip protocol just always prefers the outer one。

So that's also a characteristic of the protocol itself。That in the end。

 we'll end up changing the spanning tree。Is this clear。Order for。嗯。When switches are manufactured。

 they have an like underlyinglined I。This ID is a long sequence。Yeah。

 they just talk and they are honest about their ideas and these ideas are unique by manufacturers。

 so they just use that for this kind of thing it's not just actually like one， two， three。

 not nice numbers， but computers don't care about that。It works out。Another question。嗯。Yeah。

 at this point， if everyone is alive， it still thinks it's a root。

It is a root within its own set of switches or something。So as long as it can't talk to the others。

 it can't become rude for the other set of switches， but yeah， within its own world， it's rude。

 and so that's also what makes the protocol say that。The it still works。

 even if there were others connected to S1， S1 would maintain a valid spending trade。



![](img/37f8b034ff227ec877845f564dd5571d_34.png)

For those notes。

![](img/37f8b034ff227ec877845f564dd5571d_36.png)

It periodically sends out to telling that it's still rude。And then if it doesn't。

 then election starts and they start finding a new route。But yeah。

 it just maintains the spanic trees。 That's the only thing that's。

If someone has to tell that the this is still alive， this path still work。

 and that's done by the root。

![](img/37f8b034ff227ec877845f564dd5571d_38.png)

![](img/37f8b034ff227ec877845f564dd5571d_39.png)

Yeah， we talked about this。And yeah， this is also another shortcoming of not maybe shortcoming。

 but maybe criticism of the algorithm。 The other one was what you brought up。



![](img/37f8b034ff227ec877845f564dd5571d_41.png)

And there has been some research on this。Yeah， actually Murphy， who was doing the online lectures。

 has a paper about。Taking ads to L2 and there's a poem more nicely criticizing what we also criticize。

Earlier in this。Networking is also fun。

![](img/37f8b034ff227ec877845f564dd5571d_43.png)

Okay。So today， we showed how Linux switches learned by flooding in a tree topology。

 and then realized that this is not enough when the underlying topology has looped。

 has loops with this we motivated why we need the spanning tree protocol。

 And then we introduced the spanning tree protocol that helps us。

Find a tree in the underlying loopy topology and then disable certain links。

 So flooding that will not happen on those links。 and then whatever is left。

 we can use that for flooding。For getting this plug and play experience or our end。嗯。

We also consider different failure scenarios and how Spanish Shi protocol reacts to them。

And in the end with this， what we get is now we can connect arbitrary devices via our phones and computer to the local network。

 and the local network will recognize。Who we are and。

They wanted this for that plug and play experience。 and this is how。Some of that is being done。嗯。

Yeah， think that all way ahead。Thank you to。Alex and Sarah and everyone else who contributed making this if there are any questions。

Anys can。Question。Okay。Does anyone else is anyone else very confused about sequence numbers？

For the next five minutes。Yeah， let's let's talk'll finally。有人看。



![](img/37f8b034ff227ec877845f564dd5571d_45.png)