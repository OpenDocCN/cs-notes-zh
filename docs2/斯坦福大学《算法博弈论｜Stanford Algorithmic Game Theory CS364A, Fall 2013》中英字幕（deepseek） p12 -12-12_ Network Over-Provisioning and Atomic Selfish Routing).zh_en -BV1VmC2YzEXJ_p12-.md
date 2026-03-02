# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p12 -12-12_ Network Over-Provisioning and Atomic Selfish Routing).zh_en -BV1VmC2YzEXJ_p12-

What I want to do today is continue talking about routing games。

 talking about their equilibriumlibria， when and in what senses are they close to an optimal solution。

The first two results I want to discuss today， I kind of want to interpret in the context of a case study。

 The case study is in the strategy when you're managing a communication network of what's called over provisioning。

So the routing model we've been talking about is sort of general enough to cut across a few different domains that originates from transportation networks back in the 50s or even sort of implicitly before that。

 but one big advantage in communication networks， which is not so true in transportation networks is it's relatively easy and cheap to add capacity to communication networks if you tell your urban planner is to go add four more lanes to highwayway 101。

 it's not so simple。So a popular strategy。For people who actually do manage。Communication networks。

Is to install extra capacity。So more capacity。Then is needed。

And all I mean by this is that if you look at the network， you know， in any typical moment in time。

 it's going to be not fully utilized。 In fact， possibly quite far from fully utilized。

 So a lot of the capacity will just be sitting there unused。

 And if you look at communication networks out there today， that is， in fact， a property of them。

 they're not even close to fully utilized， generally speaking。So there's no。

 I don't know of a definitive reference on， you know， the over provisioning strategy to give you。

 But， if you Google it， you get lots of research papers， you get， know。

 discussion forums where know network managers are discussing whether or not to do this and if so。

 by how much and so on。 So it's really， you know， like I said， something that's used quite commonly。

You know，So why， why， why would you want more capacity than you really need， You know。

 So one reason is you want to make sure， you know， if demand suddenly grows for your network。

 you have sort of enough capacity there to absorb it。

But I want to focus on performance reasons that you might want to install extra capacity。

 And these have been。Observed empirically。And so I'm going mention two things。

 and we'll have theorems that correspond directly to to these two empirical observations。

So empirically， the network just functions better。For whatever performance measure you want。

 you know， packet drops， delay of traffic， whatever。The more capacity you have， the more， the。

 the better the performance of the network。And two。When people think about sort of a related point。

 when people are sort of asking the question， you know。

 what should we do with our network to make sure the performance is reasonable， for example。

 to guarantee certain latency for our end users， when you download a web page or what have you。

It's often thought that it's cheaper to just add extra capacity， make the network you know。

 bigger and therefore function better， as opposed to having some kind of smart control， you know。

 possibly in software。 So doing something like guiding the performance of the network with the current capacity toward optimality。

 So it's not to be cheaper than。Somehow being smart and enforcing you know what networking they call QOS or quality of service。

 So this would be just you know guaranteeing some kind of end to end delay， for example。

 and you know one way you might do that would be some kind of a mission control procedure。

Whereby you actually are able to refuse entrance of some traffic to the network in order to keep the congestion down so is there's not consensus on this topic。

 but there's a sizable camp that believes you rather than be smart about managing the traffic in your network。

 just make sure there's more than enough capacity to hold it okay。And again， so these are just， know。

 empirical phenomena。 And I want to show you two mathematical results which corroborate this real world experience。

But so the first result is actually just going to be an instantiation of what I already told you on Monday。

 We went over a very general theorem on Monday。 So I'm just going to instantiate in a particular way。

 That'll correspond to point number one。That the more your over provision。

 the better the network functions。 So we'll have a sense in which the more of over provision。

 the price of energy will get closer to one， and then we'll prove a new theorem making this precise。

All right， so。On Monday， we worked with arbitrary sets of cost functions。

 And so to illustrate this point。I want to now instantiate cost functions to look like this。

 So every edge is going to have a capacity。It's called UB。And the cost or delay function。

 be there'll be some basic propagation delay with zero traffic。

 and then as it gets more and more congested， of course， the delay goes up and it goes very sharply。

As you get to the asytote， Okay， so qualitatively， that's what the cost functions are going to look like。

So we're going to consider a self droughing network， just like we were talking about on Monday。

Where every edge cost function。How's the form？Well， if you're overcap。Then it's infinity。

 so basically you can't go over capacity。And if you're under capacity。

 then it grows as the reciprocal of the capacity remaining。 Okay。

 so one over the capacity minus the amount of traffic on it。At least a few of you。

 I hope have encountered functions like this previously。

 This is the standard delay function for what's called an M M1 Q。

 A Q with Po on arrivals and exponentially distributed service rates。 If you take you know。

 if you take a textbook on networking and you just start reading from page 1。

 this will be the first delay function that you find in a networking textbook。Alright， so we want to。

Have a mathematical statement that says the more the network is over provisioned。

 the better it will function， okay。Yeah。So here's what our provision is going to mean for us。

And'm going to parameterize it。So alpha over provisioned。And by this， I mean。

That the maximum link utilization in the network at equilibrium is one minus alpha。So meaning。

 if look at the amount of traffic using any given edge。Of course。

 it's got to be less than the capacity because otherwise， wed have infinite cost， but actually。

 it's even at most one minus alpha times the capacity， okay。So for all edges。At equilibrium。Okay。

 so one of the most basic network measurement tools is you just look at link utilization。

 So what I'm saying here is just inspect， zoom in on each of the links in your network。

 Look at the link utilization。 If all of the links utilization is the most1 minus alpha。

 Okay so maybe alpha is 。1。 So thatll be 90% link utilization。

 then we call it alpha over provisioned。 the more the alpha， the more it's over provisioned。

 the less it's utilized。All right。So I'm just， I'm going to skip a calculation。But it turns out。

 you know， what we did on Monday was we basically gave an algorithm for computing the price of anarchy。

 the worst case price of anarchy for any set of cost functions。 right So what do we prove， We said。

 well， it doesn't matter what your network is， how big and complicated it is。

 whatever the price of anarchy is。 It's no worse than one of these two node two link networks you always realize worst case price of anarchy on 2 node2ing networks。

 So we could take that abstract set C of cost functions to be these M1 delay functions with the additional restriction that flow never uses them more than one minus alpha times the capacity。

 Then there's going to be some trivial network with cost functions like that。

 that realizes the worst case price of anarchy。 And we can just compute it in that small trivial example。

 So I'm gonna skip the details of that and just give you the bottom line of what you get when you do the calculation。

So it follows from what we said yesterday。That in any alpha over provisionion network， again。

 no matter what the topology is， just as long as the equilibrium basis condition。

So you get an exact formula。Which is also tight， so this can be realized。

 as we know even in very simple networks。The price of anarchy is bounded above by the average of one and the square root of one over alpha。

So let's just sort of get a feel for this。 Okay so， you know， what's intuitively， hopefully。

 what you'd expect intuitively is， you know， as you make a network massively over provisions。

 you know， then in some sense， these cost functions are like essentially constant。 right So I mean。

 if you have so much capacity that basically， you're never gonna fill up a link at all。

 it's almost like you have constant cost functions， and you'd expect traffic to be on shortest paths。

 everybody would be happy be basically be optimal。 So you would expect that as alpha approaches one。

 as the link utilization approaches 0%， you'd expect the price of energy of one。 And you see that。

 plug and alpha equals one， then you get one。😊，If you let alpha go to 0 and you make no guarantee on how far away you are for capacity。

 Well， then you're going be near this asymptote。 And it's a crazy， steep cost function。

 And we know from Monday that even in simple networks with crazy steep cost functions。

 the price of energyarch can be arbitrarily large。So we're not also surprised to see that as we take alpha going down to 0。

 as the max link utilization approaches 100%， this blows up to infinity。

So what's cool is we have this exact expression that we can evaluate with interesting values of alpha。

 You know， that might correspond to something in practice。😊，So for example， alpha equal 01。

So if you plug in alpha equal 。1， you know， this is like 10 under the square roots。

 It is a little bit more than 3。 So the average here is going to be a little bit more than 2。

So a special case says maximum link utilization at most 90%。 And again， in reality。

 many link utilizations are far less than 90%。 But as long as everythings at most 90%。

 this says the price of anarchy is， bounded by something just a little bit bigger than two。Okay。

 so that's a sense in which from what we already learned on Monday， we see how， you know。

 the selfish Shoing theory corroborateates this real world experience。 Okay。

 that networks perform better， the more they're over provisionvised。So that's the first。

Sort of vignette about。Network over provisioning。Let's move on to this。

 Let's see if we can have something which allows us to compare。

The benefits of adding capacity versus the benefits of being smart about the traffic management。

All right， so I just mentioned this， but let me mention again。

Which is we know that if you make no assumptions about cost functions at all。

 you can't say anything about the price of anarch could be arbitrarily large。

 And we know that just from the nonlinear version of Pigu's example。Okay。So on Monday。

 we argued that as D goes to infinity， the optimal solution can split 1 minus epsilon epsilon with epsilon going to 0。

 So the opt goes to 0， whereas the equilibrium is 1， no matter what D is。

 So that ratio blows up to infinity， as D goes to infinity。嗯。So the point being that。

Even in very simple selfish shroing networks， the price of energy is unbounded。In general。

So the main thing we did on Monday is we made assumptions about and that we just did in the last application is we made assumptions about the cost functions。

 And we said as long as they're not too steep。Then， in fact， the price of energyarch is bounded。

 it's near one。But what if we actually want to say something about networks with arbitrary cost functions。

 So cost functions of the form X to the D， What could we do。Well， you know。

 one thing you could do is you can make extra assumptions， not on the cost functions。

 but about maybe， say the traffic matrix and about the network topology。

 And there's been some work in the systems community。

 There's a sitigcom paper from about 10 years ago that does exactly that。

 that says if you look at quote， unquote， Internet like topologies。

 even for arbitrary cost functions。 The price of anarch is pretty small。

 So that's a totally legitimate way to proceed。 We're going to do something different。Here。

With an eye toward this comparison of adding capacity versus you know， smart traffic management。So。

What we're going to do is we're going to take an arbitrary network， including， say。

 the nonlinear pig's example。And we're going to compare the equilibrium。To a weaker。Benchmark。

A weaker version of Ops。And the trick is， in our comparison。

 we're going to force the optimal flow to send additional traffic。

So and we can already see how this might work in the nonlinear Ps example。

So if the equilibrium flow has to route one unit of traffic， as usual， it will all go on top。

 So the equilibrium costs one。But what if now I get， I let you route optimally。

 but I force you to route two units of traffic。In that top network。What are you going to do with it？

If you only have one unit of traffic， you can split at 1 minus epsilon and epsilon。

But now if you have to route a second unit of traffic through， you're sort of stuck。 Okay。

 Either you can route it on the bottom link， which is always expensive。

 or you can route it on the top link。 But then it's going to get congested and you lose all your benefits。

So if you have to route two units of traffic， there's nothing better you can do than putting one minus epsilon on top and one plus epsilon on the bottom。

And your cost， then in routing two units of traffic is going to be more than one。

 which is what the equilibrium pays routing only one unit of traffic。

So we're going to seek some kind of generalization of that observation。And to further connect this。

To the previous point。I'm going ask you on this exercise set to prove that comparing to an optimal solution that routes additional traffic is mathematically exactly the same thing as comparing to an optimal solution with the same amount of traffic。

 but in a slower network， with in some sense， worse cost functions。And so the interpretation here。

 so now same amount of traffic with both the equilibrium and the optimal。

 but these different networks a slower one and a faster one。 What this says。

 what we're going to prove， will imply that an equilibrium in a faster network is even better than an optimal solution in the original network。

And in fact， if you have these M M1 delay functions， that has a particularly nice interpretation。

 it says if you double the capacity and use equilibrium routing。

 that's at least as good as if you used optimal routing in the original network。 Okay。

 so this is a precise way of saying the performance will be better。

 if you don't try to manage traffic and you just add capacity。 You double capacity。

Versus not adding capacity and routing optimally doing the best you can in the original network。

So that's what this theorem is going to imply。So here's the formal statement。

This is an old result with my PhD advisor， Aviarddo。

And so the real benefit here is that now we're going to make no assumptions on the cost functions at all。

 other than the baseline assumptions， non negative， non decreasing， continuous， in particular。

 the theorem will apply to networks like this。So the cost of an equilibrium flow。

With our units of traffic。It's going to be bounded above by the cost of an optimal flow。With two R。

Units of traffic。So the generalization of what we observed in the No nonlinear Picks example。

 where forcing opt to route two units forces its cost to be above one， the equilibrium cost。

So this is the formal mathematical statement。 And I've tried to sort of give you a narrative in the sense in which it makes。

It formalizes。This philosophy， this philosophy that adding capacity。

Meaning using a faster network does better has smaller cost than not adding capacity and being smart about routing traffic。

So up next is the proof of this。 Any questions。seemss like。right。Our breakfast。So， no。

 that's more what's going on in this equivalent version。 So it can be rephrased as such。

And that's exactly what the exercise asks you to go through。

 But in the theorem that I'm about to prove， there really is fundamentally twice as much traffic on the optimal network。

But again， I mean， your interpretation is correct， but it takes an additional change of variable。

 basically， which is what this exercise asks you to do。Other questions。I see。Yeah， but it's optimal。

 right。So if it's just。Eilium flow so there's two different moving parts here， right？

So I basically give you full control over the network， but I make you route twice as much。 Obviously。

 the first thing makes your life easier， The second makes your life harder。

 and it's totally unclear who's going to win the Tuuckcker war。Yeah。Yeah no， no。

 we want to make off weaker， right？So apps should get the slower network。Or if you prefer， you know。

 we get the faster network， but we're just going to be very dumb about our routing。O。So。

Proofs not too hard。So we've got our equilibrium flow。It routes only our units。Like last time。

 it's going to be F。And like last time， F star will be the outs。Flow。

 and that routes twice as much traffic to our units。 Okay I'm again。

 going to assume that everybody starts from the same source and is going to the same destination。

 And it's again true。 See exercise set 6， that this extends to multiple sources and multiple destinations with essentially the same proof。

But it's simple to see what's going on with one source and one destination。

So recall the definition of an equilibrium flow。 any flow in use is shorter than any other。 sorry。

 any path in use by equilibrium flow has to be as short as any other path with respect to the current traffic。

 So in particular， all paths in use have exactly the same travel time。 Okay， and like on Monday。

 I'm going to call that capital L。And what I'm going to do here is really kind of conceptually exactly the same as part one of the proof that I gave you last time。

 So what were we doing there。 So the hard part about trying to get a grip on the optimals cost。

 is that not only is the traffic pattern different than the equilibrium。

 but once you mix up the traffic pattern， the costs themselves are different。

 So how do I compare these two different flows which are measured with respect to totally different cost functions。

 So we had this nice idea on Monday， which was that。

 if only we froze the costs at the equilibrium amounts。

 then because the equilibrium sort of routes everything on short as paths with those fictitious frozen costs and the other flows only going be worse。

 And here we're routing twice as much traffic， it's actually going be twice as bad。

 so we're going to just do that exact same trick here。

 So we're going to freeze the costs at the equilibrium values to give us a grip to give us some kind of handle on a version of the optimals cost。

So the equilibrium flow。Total travel time or cost。 So let me just write it in the path version。

So the amount of flow on a path time is the cost of that path。And。

The path cost is L for any path that it actually uses。And then， of course。

 it's to flow that routes R units of traffic。 So these values sum to R。

So just like last time we get to r times L amount of traffic times the common cost of all traffic。

 that's the equilibrium cost。And if we use the fictitious equilibrium cost to lower bound the optimal flow value。

 we can do that as well。 just like last time。So。If I look at the optimal flow routing two R units and I don't measure its cost with respect to the proper costs。

 Me a cost with respect to F star， but rather。I freeze them at the equilibrium values。Well。

 we know that these are all at least L。Because the equilibrium routes stuff on shortest paths。

And for this flow F star， we' forced it to route two our units of traffic。

So we know this sums to 2R for F star。So that's what we get。 We get that if we use the wrong costs。

So we're gonna have to pay the pipe later。 But for now， we use the wrong cost。

 We actually get a fantastic lower bound on the optimal flow。 Remember， that's what we want to do。

 I to say the optimal flow is at least as expensive as the equilibrium flow right now。

 we're saying it's twice as expensive。 but， of course， we're cheating。

 We're not using the cost with respect to F star。 We're using the other ones。😊。

But it does reduce the proof。To showing that the overest potentially introduced by using the wrong costs is at most R times L。

 So remember， this is the equilibrium cost。 We want to say that the optimal flow is at least this。

This erroneous version of the optimal cost is at least2 R L。 So if we're off by only R L。

 then we're done。 then， in fact， the real optimal cost is at least R L。

 And that's what we're trying to prove。So in other words， to finish。It's enough to show。Now。

 remember， last time we had two ways of writing costs。

 We could either sum up over the past or sum up over the edges。

 So I'm going now write these exact same quantities， but as the sum over edges instead。

 So don't get confused by that。So we want to prove that。ち。去去去。So this is the cost of F。

 This is what we want to lower bounds。So I've written it in the edge form。嗯嗯嗯。Let me do it this way。

This is exactly the same as this。 just written the edge form instead of in the path form。 So this。

 we just argued。Is at least two times RL。 So this is our fictitious lower bound on the optimal cost。

And then。This is just the cost of the equilibrium flow。Written in the edge form。And as we observed。

 this is exactly our times L。Okay， so we have not proved this inequality。 This is inequality。

 We're about to prove。So what you're supposed to observe right now is that if we successfully prove this inequality。

 then we're done。 Okay， What are we trying to prove， We're trying to prove that the optimal flow。哎。

Is at least as expensive as the equilibrium， Sorry。

 optimalum flow F star is at least as expensive as the equilibrium flow F。

So here we have cost of F star， if we successfully prove this then it's at least two times RL minus r times L。

 I。e R times L， which is indeed the equilibrium cost。So if we prove this inequality。

 then we've proved the theorem。Agreed。Okay。Okay。Okay， so we're going prove this inequality。

 We're going do it edge by edge， separately for each edge。Let's say， we'll show。For each edge E。

So we're just， let's just look at the sum ends for a particular edge E。

 I'm going to rearrange them here， and it'll be the same thing。So I'm just going to take。

The sum man from this one and move it over here and move that one over there， okay。

And flip the right and left hand sides。So what you get when you do that。This is the following。对。

So if we prove this inequality。Then we apply it just term by term。

 and we get the desired inequality from which we have the film。

So we've just done some content pre rearranging。 The theorem boils down to understanding this。Okay。

And in some sense， here's what we're trying to do here。

 So we observe that if we cheated and froze the cost at the equilibrium levels。

 we really easily got this super strong lower bound on the optimal cost。

 We proved that lose double the equilibrium cost。 So fundamentally。

 what we're trying to show is that our overestimate in our cheating is at most once times the equilibrium cost。

 because then our residual lower bound is still once times the equilibrium cost。

 Now we're good to go。 So that's what this is saying。 It says， look at a given edge。

TheThis is the difference between the costs frozen at the equilibrium amounts， which was our cheat。

 This is what we actually should have been using。So this is our error and cost per unit of flow。

This is the amount of flow that we're incurring that error for。

 The amount of flow that the optimal flow actually routes on it。

And we're saying that that's at most the equilibrium cost。Okay， so summing over all the edges。

 this is just the overall error we make by using the wrong costs。

And this is saying that total errors at most once the equilibrium cost are times L。Okay， but now。

 in any case， we just need to draw a quick picture and we' see this is true。Okay。

So here's an easy case。 What if。So F and F star could be any non negative real numbers。

 What if F star is bigger than F on this edge。What can you say？So cost functions are not decreasing。

 as always。 So if F star is bigger， then this cost is bigger。

Which means the left hand side of this is actually non positive。 So that's clearly true， okay。

So easy case。Fstar， at least Fffy。Okay。Left hand side is non positive。So。

The merely slightly less easy case。Suppose the amount of optimal flow on E is less than the equilibrium flow。

 F star E less than F E。And consider the following picture。

So this is going to be the flow on E and the cost of E。

 so this is going to be some kind of cost function。And now， let's look at。F story。So again。

 the x axis is the amount of flow， the y axis is the cost。So here's two candidate flow amounts。

Fstarri and Effie， and Fstar is further to the left。So let's look at what all these quantities are。

So the right hand side。The equilibrium flow out。 So that's F。 So with F sub B。Height cost of Eps。

Okay， so the right hand side。Is this rectangle？Me。That's our upper bound on the air on this edge。

 the left hand side。Well， it's F star E。 So it's going to have with F star E。

And then it's the difference between the cost and the cost function evaluated at F star E versus F。

 So the height is going to be this。No。So this is the left hand side。

And then the entire shaded rectangle。Is the right hand side。And so in general。

 the width of the left hand side rectangle will be smaller because F3 is less than F E。

 and in general， the heights of the left hand side rectangle will be less than that of the right hand side one just because the difference in costs is bounded by the difference in costs between 0 and F subB。

So that's it， so that verifies its inequality for each edge。And as we've argued。

 that goes all the way back to proving the theorem。Qu许。In your diagram。

 it looks like the legend is bigger。How do you figure？Looks at random。

So the left hand side is the pink rectangle and the right hand side is the green rectangle。Yep。

 whole thing。So like including the area。Oh yeah。原告的。有。Use our equation for what。好试的。

Where do we use our equation？就我公司。Click the one over function。Oh， we don't。 Yeah。

 So if you look at the theorem statement。Ma I should to make this more clear。Yeah。

 let me make this more clear。So you're absolutely right。

All that this theorem needs is connuing non negativity and non decreasingreive， and that's it。

Now the reason now， okay， so just to remind you of the interpretations I gave you before this proof。

You might be thinking， okay， it's kind of isn't this apples and oranges。

 like isn't it sort of weird to compare like， you one net。

 know wide as optimal have twice as much traffic， What does that mean so this is the formulation in which the proof is the nicest So I prove this version of it。

 But on the exercise I ask you to do a change of variable to observe that a totally equivalent statement to this theorem is to look at two different flows with exactly the same rate。

But when you route optimally， you have a slower network。In a precise sense， Okay。

 that'll be spelled on the exercise。 So again， you have optimal， you have equilibriumria。

 But rather than twice as much traffic， you have slower network， and same traffic。

And then if you take that statement and you take the cost functions to be these M on1 cost functions1 over u minus x。

 then it's a particularly nice interpretation。 The change of variables has a particularly nice form。

 It really says that if you do equilibrium routing after doubling the capacity。

That's only better than optimal routing in the original network， with the original capacities。

But it's only that， you know， one， I mean if you have an arbitrary cost function。

 doubling the capacity is not is not defined。 So， with the M M1 cost functions is's a notion of capacity on the edges so I can make a statement about doubling the capacity。

 But the， the basic comparison is， is holds for any cost functions y。Where what？

Continuity comes into existence of equilibriumo， which is a fact I stated on Monday。Y。Okay。

 any other questions。Good。So Im promise that one。One of the questions I asked was to you know。

In the spirit of the。Poor incentives in the badminton tournament in the 2012 Olympics。

 I asked you to go find other examples out there in the real world。

Of systems where the incentives were not quite right。

 So a couple of you came up with pretty nice examples。 So I'll just tell you one now。

 Probably I'll tell you one or two others in later lectures。

But one team of students pointed out that。Theres， I hadn't heard of this， actually。

 I'd heard of spelling bees， of course， but I didn' there was I'm not surprised。

 but Id never heard of the National Geography be， but there is one。Maybe some of you are alumni。

 I'm not sure。So my understanding is it's for sixth， seventh and eighth graders。

And the way the rules of the competition are is， you know， so they rank the top， you。

 15 or what have you。And， you know， there are very cash prizes，25 k for first place。

 I don't know what you do with 25 K is a 6 grader。I guess probably your parents just put it in your college tuition account。

 That's about the end of it。Anyway， so they rank you and there these cash prizes。 And， you know。

 of course， it's， you know， it's it's， you know， tons of glory。 You know。

 if you place first in the geography B。 And， but so the rules are， again， it' 6，7th and 8th grade。

 And the rules are if you place first， second or third。😊，You cannot enter again。So。

If if you're an eighth grader， you want to do your best。But if you're a sixth or a seventh grader。

And you're not going to get first。Maybe you don't want to get second or third。

 Maybe you want to get fourth， So you can enter again next the next year， because hey。

 you you get fourth as a sixth or seventh grader。 your chances look good as an eighth grader， right。

And so it's， you， it's unclear if there's actually been people intentionally using the strategy my guess is it would actually be pretty hard to pull off to just sort of you know。

 not a lot of be hard。 know， if you're shooting for fourth， he might get third instead。

 but it has been acknowledged that like so one winner as an eighth grader was， in fact。

 fourth place as a seventh grader and actually commented an interview with Alex Tribe that you know。

 the previous year。 he was really hoping he get either first or fourth。

 And so did he did make that comment。 So it's not lost on the you know， very smart。

Very smart contestants。Okay， so a little bit more about routing。

So I want to relax one of the assumptions we've been making thus far。We've been thinking about。

 you know， very small agents， cars on a highway， know， individual packets and the data network。

 And so it made sense to model the population as basically being a continuum。

 basically being an infinite number of players。Some context， you don't want to do that。

 Like if you're modeling an entire Internet service provider routing its traffic。

 that is not a non negligible agent in a network。So I want to look at a finite number of agents that are of nonnegligible size。

 So in addition to being you know， a natural model。

 we're going to get some new kind of phenomena that's going to show up in the next couple lectures as well。

 Okay， so this will give you a gentle introduction to some of the complicated things that can happen in other important models。

All right。So the deal now is there's a finite number of players， K。

And each with its own source and sink。They might all be the same。 They might not okay。Sinnc ti。

And I'm going to keep things simple。 I'm just going assume each has exactly one unit of traffic to send。

And the responsibility of a player is to pick exactly one path from S I to T I。 Okay。

 so it's going to have this one unit of traffic and all of it gets routed on an S I T I path of the player's choice。

The objective function of a player is the same as before it just wants the path that has cost as。

 as small as possible。 And as usual， there were these edge cost functions。

 So short cost is with respect to the current traffic pattern。おぱ。All right。

 so let's look at an example。It's a slight variant on Pgu's original example。

So rather than tons of agents， there's only going to be two。And I'm going to change the one to a two。

The top cost function is still the identity function。So on the bottom。

 any player using the bottom link has cost 2。 doesn't matter if both of them are there are just one of them。

 If there's one player on the top link， the cost is one， if both players that are on the top link。

 the cost for each of them is 2。So the objective function is going to be the same as before。

 Just this total cost of all the players。So what seems like the optimal thing to do。that。

Is that easy to see？Well， for an optimal solution， there's no reason to randomize。

 It's just going to be one solution that's best。For equilibrium， it's going to be relevant。

 But for today， we're not going to allow randomization。 But it's a good question for equi。

 But for today， no。So you want to split them on the two。So you want to do one player on each。

For the cost of three。whoever gets stuck on the bottom has cost 2。

 The person on top is lucky and has cost one。And this is an equilibrium。

 So what do I mean by an equilibrium。 I just mean it's a traffic pattern where if any player unilaterally switches its its path。

 meaning the other K -1 player stay fixed， then any path switch only makes you worse。 Okay。

 your cost either stays the same or goes up。 It can't go down。

 If there's a player who can switch a path and get less cost then it's not an equilibrium。So this。

 I claim is an equilibrium。Certainly， it's obvious for the top player who has cost one。

 They're very happy to have cost  one。 Don't want to switch to the bottom。

But what's a little interesting。 And now already a little bit different than the previous model is this player on top。

 even though they're sort of bumpumed out， They have cost 2。 and they're jealous。

 that the player who has cost one。 There's nothing they can do about it。

So if the player on the bottom switches to join the player on top， what's its cost going to be？

It's again， therere going to be two。So just because it looks upstairs and sees a player with cost  one doesn't mean it can join it and also enjoy that cost of one。

 And that's different。 Okay， when you were negligible。

 you could switch paths and enjoy whatever cost they were already incur。So this is an equilibrium。

You see another equilibrium？嗯。Both on top， that's right。Because again， you have costs 2， you switch。

 you can't help it。 It doesn't matter。 Okay your cost doesn't go down if you switch。

 So what's the cost of this equilibrium。It's worse， actually， so this one has cost for。

So this is an important point。 This did not happen in the previous model。 I didn't prove it。

 but I asked on Monday for you to take it on faith that all equilibrium have the same cost in the nonatomic selfish routing model。

Here， and in fact， in most games， you can have multiple equilibria。

 which have different objective function values。All right。ど場に。Right。

 so the definition I gave you of the price of energy on Monday is now obsolete。 Okay。

 what I wrote was cost of an equilibrium in the numerator and cost of an optimal on the bottom。

 The bottom still makes sense。 There's still an optimal solution。

 It's not well defined to just write cost of an equilibrium because there's many。

 and they don't have the same cost。So we have to make a choice。

About which equilibrium we want to talk about。The best case scenario， as far as proving upper bounds。

 of course， would be to give a bound on every single one of the equilibrium。 Okay。

 that's what we'd love to have for positive results。 And for today， that's what we're going to do。

 We'll talk about other choices later on。So a redefinition of the price of energyarch。

On the numerator， if there's many equilibrium， we take the worst of them。Okay， so in this one。

 we would take the second equilibrium。Over the cost of us。So， E G。Equals4/ thirds in the example。

Right。Questions。So that's the first big。Technical difference that happens when you relax the assumption that players are small and you allow them to have non negligible size。

So I'm next going to state a fact at this time at the end of the lecture。

 I'll actually give you the details。 but let me just state it for now， which is another difference。

So this is example。18。6 in the AGT book。So they're less well behaved， not only in that。

 you can have multiple equilibriumria， but they're also less well behaved in that the worst of these equilibriumria can be worse。

 I。e。 less close to optimal than the bounds that we just proved in the nonatomic case。

So if you restrict to say， aine cost functions， A X plus B。

 we proved on Monday that the price of anarch is always four thirds or better in the nonatomic selfish routing world here。

 it can be bigger than four thirds。 It can be as high as 2。55/ hs。Okay， so not a total disaster。

 but noticeably larger than we had for the case of negligible sized players。Yeah。え。Yeah， so。

So this is a lower bound。 So this is just some concrete example。

 And so the example in the book uses four players on the exercise set。

 I ask you to come up with an example with three players。

 The upper bound I'm about to give you will be for any number of players。Which is what you'd want。So。

Right。So the main other results I want to tell you about today。

Is it matching upper bound so this was proven？Independently by two groups。

 Arb Cazar and Epstein and Chris Duulou and Ktsupus。Miid the last decade。

Which was that there is no example worse than this for atomic selfish routing networks。2。5 is。

 in fact， tight。对。And so this is for any number of players， any number of sources and destinations。

Arbitrarily large network size。 so that's the you know， the bad news is。

 is the constant is not quite as close to one as before。 But the good news is qualitatively。

 this still set tells us something extremely nontrial。

 It says you can scale up your networks as much as you want。

And the price of anarchy does not grow with the network size or the population size。

 It remains bounded above by universal constants。Any questions about that there。O。

So theres a couple of reasons， I want to show you a full proof of this theorem。 I mean。

 it's not it's not that long。 One is just the basic result in the area of routing games。

 but also this proof will have a particularly canonical flavor of how you prove upper bounds in the price of anarchy。

 And it's even canonical in a sense that can be usefully formalized， which will develop next week。

 so this in the future will be sort of a canonical example of some more general method for proving this price of anarchy bounds。

 But for now， let's just understand why this theorem is true。So the usual notation。

F is an equilibrium flow。 There might be many， but this proof will work for any of them。

 and therefore will give us a price of energy bound。So F is an arbitrary equilibrium flow。

F star is the optimal flow， the one that minimizes the total travel time。嗯。And。

Each cost functions app fine。 So of the form AE X or AE， yeah。AEX plus B。

So I'm going to be using the， the same notation we were using before。

 So like F subB will denote the total amount of traffic that uses an E E。 If you think about it。

 know， we just have these K players and each picks one path for one unit of traffic。

 So F subB will just mean the number of players that choose a path that includes this E E。

 That's gonna to be the total load to the edge。So we'll write FE for a number of players。Using E。

And their path。You know， sameme thing for F star E。

 So that's the number of players that in the optimal solution that use a given edge E。All right。

 so three steps。And all of these steps are sort of canonical， in a sense。So how are going to do this？

 So what do we need to prove， We need to prove the price of anarchies of most five hves。

 What does that mean。That means that the cost of this equilibrium flow is the most five half since the cost of the optimal flow。

 So we need an upper bound on how cost of the equilibrium is。Okay。So what do we have going for us。

Well，So halfline cost functions。 We've got to use that。 But also。

 we better use the fact that F is an equilibrium。Right。That should be clear， too。

 if F is just any old flow， an arbitrarily stupid flow。

 we're not going to be able to prove anything about it。 So it's important it's an equilibrium。

So we need a plan for somehow using that hypothesis in our argument。 right。

 How do we use that F as an equilibrium。Alright， let's remember what it means to be an equilibrium。

 It means that if any player switches paths， they only get worse。

 That's the definition of an equilibrium。 So that's cool。

 That means if we pick a player and we pick a hypothetical deviation。😊。

We say the costs would then only go up， so that actually gives us an upper bound on the player eyes cost in an equilibrium。

It will only be worse if it's switched。 Pa as an upper bound on the equilibrium cost。

 And that's good because we want to upper bound the cost of the equilibrium of everybody。

 not just of a given player， but of everybody。So what seems like a good idea。

 what seems like kind of the only way we might use the equilibrium hypothesis is to say， well。

 pick a player eye， click a hypothetical strategy。 It only gets worse。 Thatll give us an inequality。

So we just have to think about， okay， so what path might we sort of hypothesize I switching to。

And so now。Probably the most natural choice is just to say， you know。

 why isn't this player eye doing what I wish it was doing in the optimal solution。

If all the players did that， you know， we'd be fully optimal and somehow it's not。

So I kind of want an explanation for why player I is picking its equilibrium path and not its optimal path。

 And the reason it's an equilibrium。 Okay， but that'll give us the first inequality。Allright。

 so precisely。Using the equilibrium hypothesis。Since that is an equilibrium。Neuropplayer I。

Wants to switch。I'm gonna use the notation。PI。So， this is the。

Path that player I uses in the equilibrium flow F and P star I is what we wish it was using。

 It's path in the optimal solution。Okay， so eyes arms half。So that's the notation PI and P star I。

And but I doesn't want to switch， means this cost would only go up。I。e。Sorry。

So if I look at the cost of。Player I in the equilibrium， right。

 So the cost of its path is P in the equilibrium。So this remember。

 is just the sum over the edges in the path。Of the edge costs。

So this is how well player I is doing right now in the equilibrium。If it switched。

 it would only get worse okay。So what would be the cost if it's switched？Well， so what's the picture？

So we have this network。We have SI， we have TI， it's doing something in the equilibrium。

 all the other players are picking their pass in the equilibrium。And， you know。

 P star I looks like something else。Right it's some other the path。They may share some edge。

 but it's some other path。Okay。So if player I deviated from P I to P star I。

 there's kind of like two kinds of edges。 Okay， are the edges that are in both of the paths。

 Maybe they have the same prefix， for example。 So it's going to pay exactly the same cost as before。

But then there are going to be these edges， which it sort of newly uses。

 which are in the new path and not in the old bath。So the cost， if it switches。Well， there's all the。

It's the business as usual。And the edges it was already using。And then in the edges。

 which are in the new path， but not the old one。What do I need to write here？Right。

In the equilibrium F， they were like， say， five players using it。

 And now this player deviates it becomes the sixth。 Again。

 that was the same reason we used up here for why when the players are split。

 there's actually no incentive for the bottom player to move to the top because then it actually adds its own plus one once it moves。

So this is exactly its cost in the equilibrium。 This is exactly its cost if it switches。

 And this inequality is because we assume methods in equilibrium。Any questions about that？

I'm fixing an optimal solution。 and I don't care which optimal solution you fix。So in the same way。

 I don't care what equilibrium you pick。 I don't care what optimal solution you pick。

 They all the same cost， y。So for the past that are in common between PI and PRI。

 it's the business as usual， same cost， and then for the edges which are in PDI， but not in PI。

 it's the cost of F subB plus1。His eyes joined them。啊。Why is or is not？Okay。So， but， you know。

 we're doing an upper bound。 And for all we know， P I and P star I are disjoint。 Okay。

 for all we know， there's no shared edges。 So let's just keep things simple。And write this。

It's equilibrium path costs。Is bounded above。By the sum over the edges in the optimal path piece our I。

 where we always add one to take into account I possible new presence。Good。😡。

So that's step one already done。So step2。Allright， so this is good。

 We've used the equilibrium hypothesis for each player I。

 we now have an upper bound on how costly it is in the equilibrium。

 And let's go in the right direction。 The price of energy demands a bound on the overall cost of the equilibrium。

 Okay， with respect to the optimal。So， step 2。Let's sum these up。

 so we have one inequality for each of the K players。Yeah。对。So what do we get。Well。

 for the left hand side。All right， so left hand side。We sum over the players equal equal1 decay。

Some over the costs and their edges， okay。So I want to do the same。 Okay。

 I I just want to know simplify this。 So how many times So pick your favorite edge edge number 17。

 Okay， so how many times does the cost of edge number 17 appear in this double sum。 Well。

 it appears once for each player I for which edge E is is a part of its path。 Okay。

 so if three different players have a path that includes edge number 17。

 then the cost of edge number 17 is going to show up three times。

So this is just the sum over all of the edges。OfThe corresponding cost of the edge。

 multiplied by the number of players that actually pick a path that use that edge。

So this is the left hand side after we do the summing。So right hand side。After summing。Is， let's see。

 What's this thing。So some of our I equal one decay。Some over ENP star I。C of F E plus one。

 same reasoning。 How many times does does for a given edge edge number 18。

 How many times does this term show up once for each player who uses that edge in its optimal path P star I。

 also known as F star I。So this is just equal to some overall the edges。F star E， CE。FE plus one。O。

So again， what I did is I took。This， which held for each player I， I added them up and simplified。

Let me simplify the right hand side a little bit more。

 Everything I've done so far has been for any non decreasing cost functions。

 I haven't used the fact that they're a fine。So let's now expand this。

 knowing that the cost function C， E is of the forms A， E， X plus B， E。So this is just substituting。

Okay。That's just multiplying out。So that's the end of step 2。 Let's take stock。All right。

 so what do we do？We summed up these inequalities。 Why did I do that。

 The reason I summed up all these inequalities is because of the left hand side。

Is something I care about dearly。This is just the cost of equilibrium flow。All right。

I had I had the set of inequalities， inequality I just up the cost of player I。 So I add them all up。

 I got another on the cost of everybody。 And that's the whole point of this theorem。

So the left hand side， I get something I care about。 The right hand side， I then just kind of。

Saw what I got。And I actually got something I don't care about at all。Really。

So like the semantics of this term are totally unclear。 right， Like， what is F E times F star E。

The number of players in the equilibrium times， the number of players in the optimal solution。

 It's like some weird entangled version of these two different things。 Okay。

 so I don't know what to make of this。 This just is what it is。So step 3， then。Says， well， okay。

 I don't care about this。 The only， you know， the only two things I actually care about are the cost of the equilibrium and the cost of the optimal flow。

 right， That's what the theorem is about。 Okay eyes on the prize。

 Those are the two things we care about。So step3 has to basically just relate this back to the two things we care about。

 the equilibrium and optimal costs， all right。Okay。So step 3。We'll begin with an exercise。

Which is an inequality whose responsibility is to basically disentangle this confusing product of F and F star F by itself。

 We kind of know what to do with F star by itself。 We know what to do with the products we don't know what to do with。

So we have this inequality， which says， consider any non negative numbers。Integers， Y and Z。

It's the case that the product of y and Z plus1。All so this is an entangled version of something。

And here's the disentangled version of it。5ive thirds y squared plus1 third z squared。Allright。

 so we'll put this to you in a second。 But first， let's just stare at this。

So what if I choose y equals z equals1？What are both sides？Both sides are  two， right， Okay。

 so it's tight if y equals equals 1。 What if y equals。Let's see。

 What about y equals 1 and z equals 2。What are both sides of five equals1 and equals 2。

But's sides to three， okay。Okay， so it's tight for those two cases。 The claim is， it holds， in fact。

 strictly for any other combination， okay。 you know。

 once someone's pulled this out of a hat and ask you to verify it， it's really not hard。 Okay。

 you just brutefor check these small cases， a few small cases。

 and it's clear it holds for larger values of Y and Z。 Okay， but I'll leave that for you。

The question of like， how on earth would you come up with this in the first place。

That'll actually be a little less mysterious， you know， in about a week or so in the course， O。

I mean， already once we put it to you， it'll be a little less mysterious，So this is true。 And again。

 the， the role of this is to disentangle a product into individual sums。

And so the way we're going to apply this， right， So this was this entangled version of equilibrium omost flows that was puzzling us。

So this is going to be our y。And this is going to be our Z。Or Y sub B and Z sub B， if you like。

 we're going to apply this inequality once for each of the edges of the network。Okay。Okay。So。

All right， so remember the left hand side。We had the cost of F。That was this。

 that was this left board， and then the right hand side after summing was everything here culminating in that thing on top to which we will now apply this inequality once for each edge。

on a given edge， F star E playing the role of Y and F E playing the role of Z。So what do we get？

All right。So we get is。The F star E times F E plus1 becomes a five thirds。F star E squared。Plus。

 one third。F e is squared。Plus。BE times F star E。然。

So now let's be sloppy in the interest of simplification。So let's collect all the F star stuff。

So just for kicks， I'm gonna just multiply that by five thirds。 can only get bigger。

And that lets me bring the five thirds out。S over E。And now the F star E terms look like this。

And then。The remaining Fff terms。All right this。So this has another name。What is that。

That's just the cost of F star。 Okay， so remember。This by the you know， by our Aline cost functions。

 this is just the cost of the edge。For F star， so that's just sum E of F star E， C of F star E。So。

 most。53s times cost of F star。What about that？Yeah， that is most the cost of F， right。

 If just for kicks， I threw in a bunch of B sub Bs here。 Sorry， B sub B F sub Es。

Which would only make it bigger。 Then this would be exactly the cost of F。

 So that's upper bounded by the cost of F。Cool。So this little in quality allowed us to disentangle the right hand side that we didn't understand。

In terms of。And a linear combination of two things we care about。

 the cost of the optimal flow and the cost of equilibrium flow。

So remember what the left hand side is the left hand side is the cost of equilibrium flow。

 So that appears on both sides on the left with coefficient one over here with coefficient。

 one third， happily less than one。So we subtract this from both sides that gives us a two third cost of equilibrium on the left。

 We multiply by3 by three/2als， so we get what we want。So you get at the cost。Of the equilibrium。

 is it most。Cost of ox。Times， we have the five thirds to start with。And again。

 we subtract the one third because the two third multiply back through times three/2s。Which is。2。5。

That's that。Questions。Was the。代的。Yeah， I'm actually gonna，'m actually going show you that now。

 It only takes a couple minutes。 I've got a couple minutes。

 so I'm gonna to show you that there's no better。Bound possible， in fact，2。5 is the right answer。

 despite the fact that maybe this inequality felt ad hoc。

 it's actually given us the best possible bound。Other questions about the upper bound first？

Like one third some。Here。Yeah， so this is exactly the cost of F star。 So this isn't quality for this。

So if I could make this bigger。😡，By throwing in a sum of E of B， E F E。

And then that would be exactly one third the cost of equilibrium。

So this is something bounded above by a third of the cost of the Elipium。

 It's just missing the B terms。Increase the traffic to a very large numbers， so that each。か这。

Each individual is very small。good question， right。

 so what you'd hope would be true is that under some natural limit。

 selfish this atomic model would basically become the nonatomic model。 And the answer is yes。

 Basically what you'd want to be true is indeed true。I mean。

 so this is tight for worst case Atomic selfish routing networks。 I'll give you an example right now。

 where it's tight。But if you then make additional assumptions， then， of course， it need not be tight。

So if， if you assume that there's a bazillion players all of cost epsilon。

 while keeping the cost functions normalized， then no。

 it's not going to be tight because it'll approach the other model。Other questions。Okay。

So here's why it's a tight example。Yeah。Okay。So， it's2。Sos a bidirected triangle is what it is。Yeah。

So theres， so the six edges， two of them are zeros， Four of them are x。 Okay。

 There's going be four players， each with one unit of flow。

 and the four players will be in one to one correspondence with the four edges that are labeled X。

So for example， here's an edge that's x。And here's a player， player number one， S1 T1。

 the obvious thing for player1 to do is just take its one hot path of cost X。

 there's going to be four analogous such players。O。So that's the example。

Like in that first example I showed you with the X and the two。

 the optimal solution will also be an equilibrium。 but then there'll be a second。 in this case。

 considerably worse equilibrium。So the obvious routing where O。

 so I guess the first thing you notice is the bidirect triangle。 So as a player， you have two paths。

The obvious path is to take one hop and go straight to your destination。

 The alternative way is two hops around the other triangle。 Okay。

 around the other side of the triangle。 So， for example， that's one。

 Either the knew the obvious one hop path or for some reason， it could go via。A two hop half Okay。

 and all four players have that I thing， yeah。Directionions。Yeah， it's been directed graph all along。

We've never needed。 We've never used under retrographs。A model will talk about Monday。 it'll matter。

 but for these routing networks， it just doesn't matter， it turns out。Yeah。Okay， so arts。

So all players on one hop hats。And then the cost equals four。Because there's 4 xs。

 each one has population  one。 So it's a cost of4。 That's awesome in equilibrium。

 There are two0 edges， but nobody， you know， the zero edges are not in correspondence with anybody's source directly。

 source destination pairs。 and no one has a zero path available。

 So cost of the one is the best you can do。 So if all players simultaneously get cost one。

 it's gonna be an equilibrium。 can't do better。But。If all of them pick their two hop paths。

And I know this sounds crazy。But check out what happens。I've tried doing this。

 We actually draw the two hop paths， but it gets kind of messy。 So let's do， let's。

 let's do the instead the following on each edge， I'm gonna keep a tally。

Of how many players are using that edge as we go through the players one at a time。So S1。

 instead of going there， is going to go there and go there。Okay， and please watch me carefully。

 This is very easy to make mistakes in this demonstration。

 So if S1 takes its too hot path that puts a first player on this one。

And then it puts a first player on this link， as well。So let's do the same thing。 So S 2。

 there's T 2。 So that's its two hop path。So that'll put one there and one there。S3， there's T3。

 so that'll go this way。So that'll put one on the zero and then a second one on that x。And S4。

 there's T4。 So there's the two hop one there。 So that's a one on that0。

 and the second one on that x。So the orange tick marks are are denoting the edge loads。Okay。

 look good。So I claim that everybody is simultaneously foolishly picking two a hop path is actually an equilibrium。

 Nobody can do better by switching back to their one hop path because the other three people were too busy flooding the network。

😊，Okay。So， for example， consider player 1。 Okay， so player 1 is is one of the ones that's worse off。

 Okay， so notice here the two players。Have cost。Was it。I'm not so sure about that yet。 Okay。

 let's let's consider player 1。 Okay， so currently player 1。Is incurring cost 2 plus 3。

 a player 1 seems to be like， it's got to have a way to do better， right。

But if player one switches from its two hop path to its one hop path， it becomes the third player。

On that edge。 So its cost will remain3。Okay。And you can do the same observation for the other three players as well。

So because all the other players are busy fighting the network。

 you actually can't go back to your one half path and be better off。So。Two of the players are like。

 so player one and a second player have cost 3。 and then two of the players have cost 2。

 So that gives us a total of 10。So that gives us。Pre of of 2。5。Any questions about that？

So coming up next， we'll look at a variant of these routing games where you have positive externalities。

 And that's somewhere where we'll have a multiplicity of equilibriumria。

 some of which we really don't want to argue about。

 So we'll be looking at alternatives to the price of energyarch concept in the presence of multiple equilibria on Monday。

 Have a great weekend。😊。