# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p03 -03-(Lecture 3_ The Push-Relabel Algorithm for Maximum Flow).zh_en -BV14CAUeUEPj_p3-

Okay。So what are we're going to do this lecture we're going to keep talking about maximum flow。

 So last week we talked about a few maximum flow algorithms and all of them are what's known as augmenting path algorithms for the obvious reason each iteration of those algorithms you find some path in the residual graph and then you augment it by routing additional flow along that path。

 So in the first lecture we saw the Ford focusingson algorithm。

 So that's where you just pick an arbitrary path from S to T in the residual graph to augment。

That's not even polynomial time algorithm。 That's only a pseudoponomial time algorithm。

 Then on Thursday， we talked about the Edmunds CAp specialization of Ford Fson。

 that's where amongst all the S pass and the residual graph。

 you pick the shortest one known with the fewest number of hops that gave us a polynomial running time bound。

 It wasn't very good， just M squared times N but you as the start。

 And then we also talked about Dix algorithm briefly。

 although that'll be developed more on problem set number one。

 which was this idea of augmenting through blocking flows。

 and with the implementation on the problem set we'll get a little bit better of a runtime bound of n squared M。

 So that's the story so far， the goal for this lecture is to teach you a different paradigm for maximum flow algorithm design known as the push rela paradigm。

And so to this day， in fact， push for algorithms are often the method of choice and practice。

 They're really very， very fast in practice， even if they've never sort of quite won the grand championship of worst case running time bounds in practice。

 they do really， really well。 That's why I want to devote a whole lecture to it because it's really something you might use in your own work in the future。

So。To introduce push for label， let me just sort of give you a motivating example of why you might want an algorithm which does something other than augmenting paths。

 So for some parameter， K， think of K is like 10000 or something， something big。

Imagine you have a network that looks like this。Okay。So you have a bunch of edges with capacity K。

 and let's just say you have K of these edges， so K will mean several different things in this example。

So you have a path of k edges， 10，000 edges each with the capacity 10，000。Here's your sink。

And then x is connected to the sink by lots of disjoint paths that are only unit capacity each。

And let's say the number of these paths is k。对。So this obviously has some flow network。

 You might be given this as input for all you know， okay。So what can you say。

 so how long would it take， say the Ford focus and algorithm to compute max flow in this instance？

As a function of k。Wass the guess？K squared， that's absolutely right。

So so each iteration of Ford Ferguson takes linear time and indeed it's going to have to。

 you know when you do breadth for search or depth for search。

 you're gonna have to search down this whole long path of length， roughly K。

 So each iteration takes k time。 And unfortunately。

 you'll only be able to route one unit of flow each time。 because you'll be able to， you know。

 these don't bind， but you know， you have these unit capacities on the right。

 So you have a full K iterations with K time each。 So that's K squared。 the max flow value here is K。

So you know， intuitively' like， okay how could we do better at least on this network well you look at this and you kind of say。

 well， what we really kind of want to do is just like flood this path， you know， just route K units。

So spend linear time， linear and K getting flow to X and then spend linear time just distributing it amongst the theta of k different edges。

 If we could do that， that would be a linear time algorithm for maxflow in this particular instance。

 Okay， we wouldn't waste all this work， just sort of recomputing these long paths over and over and over again。

So that's sort of the high level intuition behind what push reliable algorithms are trying to do。嗯。

Allright， on the other hand， you know， it's not so simple， right， I mean， this is just one example。

 if there only， if there are less than K paths over here。And we tried to flood this path。

 We'd push K units of flow to X， and then we actually wouldn't have enough capacity to push it the rest of the way to T。

 So then we'd have some excess flow here， and we'd have to sort of send it back to the source if there were less than K paths。

So， you know， the question is， you know， is there any way to implement this idea systematically so that it always works no matter what the graph is。

 whether it looks like this graph whether it looks like something totally different。So。Simple。

 important definition for us。Is that of a pre flow？

So this is the same thing as a flow except the conservation constraints are a bit relaxed。

 remember the conservation constraints was our way of saying that the flow in should equal the flow out at every vertex other than S and T。

 And if you think about this idea of sort of flooding the network。

 you know before this flow is reached all the way to T。

 you're not going to have conservation you might have sort of excess， say it be node X。

 if you had fewer than K paths。 So a pre flow is just relaxes the conservation condition in a natural way。

Okay， so it's a vector indexed by edges。And it satisfies two things。First of all。

 it satisfies the usual non negativity and cap constraints。

So these are exactly the capacity constraints that we had for flows。

And then instead of flow in equals flow out。We're going to allow the flow into a vertex to be possibly larger than the flowout。

Okay。But not smaller。So only more flow can go into a vertex than go out of a vertex。

 and this is except。At S。So of course， at S， there's going to be zero flow in and some them amount to flow out。

And again， you why this relaxation， think about this case where we're sort of trying to push flow through this network and we're at some intermediate point。

 right， So whatever， you know whatever the frontier of our pushing the flow is going to be is going to be more coming in than there is going out。

 so that's why we want this relaxation。그。Okay。So remember。

 there was this totally key concept of a residual graph。 We talked about this at length last week。

 so you have a flow in a network， then you get a corresponding residual graph where you have forward edges with residual capacity。

 UE minus Eie and reverse arcs with residual capacity， E subB。Notice that， with a pre flow。

 we can just as well form exactly the same residual network as we could with a flow。Again。

 we just edge by edge， do the forward arc， do the reverse arc with the appropriate residual capacities。

This relaxation doesn't。It doesn't screw up our residual network construction。So four preflow app。

We define the residual network， a residual graph Gf as before。Okay。All right。

So the next concept is we want some way， you know， at the end of the day， right。

 So we're gonna have algorithms which in their intermediate stages， maybe have a pre flow。

 which is not a flow。 The conservation constraints will be violated。 Of course。

 by the time one of these algorithms terminates。 It better give us a flow。 The maximum flow problem。

 You can't output a pre flow。 You have to output a flow。So we need to work toward。Arriving at a flow。

 work toward conservation constraints。 So we want a measure of how badly we're violating the conservation constraints。

So for Fl flow F。The excess of a vertex。I's just the difference between these two quantities。Yeah。

Flow in。Minus flow out。Okay。And for a pre flow， this translates to saying that。

All of these excesses will be non negative。Okay， again。

 except we're not thinking about the source in the sink。

 we're thinking about the rest of the vertices，So flow just means all the excesses are equal to zero with a pre flow you might have strict inequality here。

 you might have some positive excesses。 pre flow is a flow。

 if and only if it has no vertices with positive excess。Have you been clear so far？

So to turn a pre flow into a flow， we basically have to kind of you squash these excesses。

 we have to get rid of the excesses。Okay。So next we need to understand what does it mean how are we going to modify pre flows in an algorithm when we were working with flows。

 our hands were kind of tied， right we had to maintain the conservation constraints at all times so that naturally motivated pushing flow on an ST path because that maintains the invariant the conservation constraints are satisfied。

Now that we're actually allowing ourselves to violate the conservation constraints。

 We have more flexibility in how we augment one of these pre flows。 We don't have to use a path。

So in fact， what we're going to do is we're only going to push flow along a single edge of the network in one step。

Okay。So they're called push Rela algorithm， So let me tell you about push。So， again。

 you want to think there's some fixed graph。 There's some current flow in that graph。

 And then there's a corresponding residual graph， like usual。 sorry， some pre flow F in the graph。

So the subroutine， I'll give you， you know， I'm going to inveil the whole algorithm step by step。

 This will be a subroutine in the whole algorithm push。

 So suppose you look at a vertex V and now you want to and you're thinking of V as being a vertex with excess and you're trying to get rid of the excess。

 You're trying to move it somewhere else in the network， okay。So what do you do？Well。

 you hope there's some outgoing edge in the residual graph that has positive residual capacity so。

So you started V， you look at the outgoing edges。In the residual graph。And again。

 so for this whole lecture， unless I specify otherwise， when I say an edge in the residual graph。

 I always mean an edge with positive residual capacity。

 okay so all those zeros just think of them as deleted from the residual graph。

So you want to find an outgoing edge from V in the residual graph with positive residual capacity。

 And then you just want to route as much flow as you can on the edge from V to W。Now。

 if you think about it。There's actually two different constraints on how much flow you can push from V to W。

The one which you're very used to is the capacity constraint。 So if the residual capacity is6。

 you'd only push six units to flow along that edge， just like before。But now， remember。

 we need to have this flow in as at least flow out。 or equivalently。

 excesses need to be non negative。So if you have a vertex and its excess is only three。

 even if the residual capacity of this outgoing a is 6， you can only send three units of flow。

 That drives the excess down to 0， and we're not allowed to make it negative。

So Delta is just the smaller of these two possible bottlenecks。

 the most we could possibly push without violating any constraints。So the minimum。Of these excess。

And the residual capacity。Of异。Okay。Where this is defined in the usual way in residual networks。

 Okay so there's the forward as there the backward arts， et cetera。Okay。And now what you do。

 you push Delta units on this hit。And so this augmentation works exactly the same way as in path augmentation。

 if this edge E corresponds to a forward edge of some network。

 then you increase the flow on that edge in the original network， if this is a backward edge。

 then increasing by Dlta really means you reduce the flow in the original network on this edge okay so just like an augmenting path。

Okay。So that's the push Sub team。So， notice that。If there wasn't already an excess of W。

This is going to create an excess at W。Right，Because when you push on V W。

 you increase the flow going into W， but you're not increasing the flow going out of W。 Okay。

 so the excess will definitely be positive after the push。

 It might have been positive already beforehand。All right。So that's a basic subroutine。

 the push subroutine。 So you change a pre flow just by increasing or decreasing the flow on a single edge at once。

Now， this isn't going to be good enough。 we need some more ideas to get a bona fide max flow algorithm。

And one thing we could be concerned about。Is。Just pushing flow around in cycles。Forever。

So think about the following network。Say with all unit edge capacities。So you know。

 if you push some flow here。And you get next test of one here。You can then push on this edge。

 That just moves the excess over here。 You can push on this edge。 that moves the excess down here。

 Of course， you want to push it to T。But， you know， conceivably， if you don't know what you're doing。

 you could just push this around the cycle over and over again。 Okay。

 so just because you zero out the excess at one vertex。

 it doesn't automatically mean you're making progress。

 It might just be like that excess reappears at some other vertex。 Okay。

 so it could be an infinite game of wackam mole。 if you know what that if you know what that is。

Alright， so。We need some principled way of figuring out how how to apply pushes so that this doesn't happen。

 So the， first of all， we terminate。 But then also second of all， of course， we want to be correct。

 We want a max flow at the end of the day。So。Here's the nice idea we're going to use to argue all the correctness properties of this algorithm。

For each vertex， we're going to give it a height。And I really encourage you to like think about a graph now is just living in 3D。

 Okay， So all the vertices have an X Y coordinate， and then the height just corresponds to a Z coordinate。

 So there's a notion of some vertices being higher than other vertices， okay。😊。

So you maintain a hyp for each vertex。Subject to three invaris。

And the first two invaris are sort of very simple， the third one is the interesting one。So。

 first of all， the。Height of the source。Is just n。 So remember， n is the number of vertices。

And it never changes， okay。As an invariant， source is always at height end。

The sink is always at height zero。你看。And again， it never changes。 So all the action， all the heights。

 they only change on the other vertices， other than S& T。And so here's the。Interesting and variant。

N chickenvari says that， at all times。In the residual network， the current residual network。

The arcs of the network， again， arcs with positive residual capacity， they， let's see。

 so the base they can't go downhill too quickly。Okay， so let me write that in math。

So for all edges in the residual graph from V to W。H of V， so this is the tail。

Is it most one more than？The height of the head。So for a picture。Ma you have a vertex V。And it has。

Three outgoing neighbors。And suppose it just so happens that the three neighbors are at the heights 3。

4， and six。Then for this invariant to be true。V better be at most。What。What's the biggest。

 What's the biggest height I can give to V and have the invariants still hold。4our， good。

So basically， it can only be one more than any of the outgoing edges。

 so it has to be at most one more in particular than the minimum。Of the vertices on outgoing edges。

 So there's three。Constrains V's height to be at most four。Okay。

So what we see from this example is that edges in the so if this is satisfied。

 then there's three cases for edges in the residual network， they can go uphill like from V to W3。

They can stay flat， like from V to W2。And if they go downhill， they only go downhill one step。

That's the case of V from w to W1。Okay。Now， I don't ask you to have an intuition for these invaris yet。

 I'll explain where they come from in a second。 But can everyone sort of parse them clearly。

 So understand what they're saying。All right， so these How would you ever think of these invaris。

 Where do these come from。Well， here's the point。So。So I claim。That if the invaris hold。

Then a familiar condition is true。 Namely， the residual graph at this moment in time does not have a path from S to T。

 S and T are disconnected in the current residual graph。So stare these invaris。

1 through three for a little bit and see if you can see why this is true。

 why they imply that S& T have to be disconnected。And the residual graph。Anyone have a proposal？

Why that's true？Is it a hand or？Yeah， we need to go down we down。呃。As promised is that most minus1。

Very good， yep， so let me repeat that proof it was absolutely correct。

So think aboutverse suppose by contradiction， there was a path from S to T in the residual graph。

How many edges could it possibly have？N-1， that's the longest a path can be in the graph。

So by the first invariant， you started height N。You traverse this alleged path that exists to T。

 you traverse at most n 1 edges。 you go downhill only one step each time。

Yet somehow you're supposed to wind up at high zero。So that's a contradiction。

 So we take n steps to get from S to T in the residual graph， but the shortest path length not。

 is not N's n -1 at most。Okay。Now， remember， from last week， we're very familiar with this condition。

 a residual graph not having an ST path。If F is a flow and there's no SD path in the residual graph。

 that's equivalent to being a maximum flow。 Remember。

 that was our big structural result from the beginning of the second lecture。Now。

 if F is a pre flow and not a flow， it's not feasible， so we can't call it a max flow。

 but if you have a pre flow F， which happens to be feasible， it happens to be a flow F。

 and there's no ST path， then you know you're done， then you know you have a maximum flow。Okay。

So if you both satisfy the invariance。Plus， you satisfy the conservation constraints。

 not the relaxed version， the original flow in equals flow out version for flows。

Then this implies that you're optimal。Okay。So that's where these come from。

Okay so basically you're thinking， how do we know when we're done？

What do we want to be true at the end of the algorithm。

 we have our optimality condition that there's no SD path in the visual graph and then it turns out maintaining heights works great。

 and then you say what are sufficient conditions on these heights so that we know that S until T are disconnected and these invariants are those conditions。

It's interesting to compare and contrast this approach。

 this paradigm to what we were doing with augmenting paths。

How did every one of our augmenting pass algorithms work， Well。

 it maintained as an invariant at all times， feasibility It always maintained a flow。 initially。

 the zero flow。 and then these augmentations， conservation constraints were always satisfied。

The goal what the algorithms worked toward was to reach a residual graph with no ST path。

So the invariant was feasibility， the goal was to disconnect S&T。Here it's exactly the opposite。

So the invaris are insisting that S and T are disconnected in the residual graph。

 And what we have to work toward is restoring feasibility， transforming a pre flow into a flow。 Okay。

 so there's sort of the symmetry between them。 But I think most people find the first paradigm much more natural。

 that you sort of you， insist on feasibility all the time。 and then get better and better and better。

 But it turns out to be a really good idea to relax feasibility and restore only at the end of the algorithm。

 And that's the key idea behind pushre algorithms。 I also think that's why So this paradigms from the mid 80s。

 Where the augmenting path algorithms are from the 50s and 60s and early 70s。

 So I think this is a little。😊，Sort of less of an obvious paradigm to come up with than augmenting paths。

Okay。ち。I guess just just to reiterate one point from last week when I was contrasting C 1，61 and 2。

61。 So the maximum flow problem， we know it's polytime sovable。

 We already have a couple polytime algorithms for it， but still。

It's sufficiently complex that it kind of demands our respect。 Okay， we can't just sort of。

 we know that we can't just make up some random algorithm on the top of our heads and hope that it's going to be correct。

 That's sort of where we started lecture number one。

 So for these harder problems in P like maximum flow and even harder ones that will stare at。

 you really need to have a plan， a strategy when you're coming up with your algorithm。

 So you need to sort of be clear in your head about how do I know when I'm done。

 what are the optimality conditions。 And what is my systematic way of algorithmically getting closer and closer to those conditions。

 So we're seeing another instance of that what I was calling a twostep paradigm from， from last week。

Okay。All right。So I want to now tell you an actual push for algorithm。

And the algorithmm is going to maintain these three invaris。

But we actually need to just think for starters about how do we even satisfy these invaris at the very beginning of the algorithm。

Okay。So there'll be a main loop。But I want to talk about the initialization a little bit。Now。

 in our augmenting path algorithms， initialization was trivial。

 We just started with the all zero flow。 Now notice here。

 these invariants actually reference two things。 They reference a residual graph。

 and therefore a current pre flow F。 It also references a height function So for initialization。

 I need to tell you what the initial F is。 I need to tell you what the initial H is。All right， well。

It's kind of obvious we should just set the height of the source to end。

We don't really have any choices by the first invariant。

And we're going to set all of their heights to zero。Okay， so in particular。

 we're going to set the height of the sink to zero as required， but also everything else。

So H of v equals zero。不。Other vertices。So that's going to be the height function。

 but I still have to tell you the initial pre flow。So here's a question for you。

Suppose we did the obvious thing。And we initialize the algorithm with the all zero preflow。

And this height function。 would that satisfy all the invaris。关了。Yeah， this an from the source？

Exactly right。So the answer is think about any edge which goes out of the source S。

So it starts at height N， and then one hop goes to height 0。But what's a third invari。

 it says you can only go downhill one step at a time。

So all of the edges outside out of going out of S violate the invariant。

 So we can't start with the all zero flow。 And actually， we really just can't。 if we。

 if we insist on this height function， we cannot have these edges outgoing from S in the residual graph。

 It's just not allowed。So how do we kick out all of those outgoing edges for S from the residual graph？

We just saturate them。And then the reverse arcs appear。

 but the forward version of the arcs disappear， because we've saturated them。

 So that's the initialization。So for all edges out of S。We saturate them。

 meaning we set the pre flow equal to the capacity， flow everywhere else is zero。For all other edges。

Notice that F is F is not a flow， obviously， right， because these vertices， you know。

 right out right one hot beyond S， they have way more stuff coming in and they have 0 going out。

 So conservation is violated， but we do have a pre flow。

 The flow in is only bigger than the flow out。So F a preflow。Plus the invariance。

W do the invariance holds well the only possible problem because all the heights are0 except for the source S。

 the only possible problem where edge is going out of S。

 and by construction we remove those from the residual graph through saturation。

Everyone clear on the initialization？We can'， of course， I mean， we have a lot of work to do， right？

 I mean， so we have this pre flow， but it's not a flow， and it's anywhere close to being a flow。

 Okay but at least we have the invariance。 And I'm going to show you a main loop that will keep the invariant satisfied and will work toward restoring feasibility。

 We'll terminate with a feasible flow。Questions。All right， so the main loop。Well。

 what are we trying to do， We have a prefo that's not a flow。 So that is。 Remember。

 that means positive excesses。 So we want to somehow now squash these excesses。

 So the mean while loop is just going to look for a vertex that has excess。So while there exists。

A vertex again other than the source in sync。It has excess。Now in general。

 there's going to be a lot of such vertices？And among them all。

 there's different ways you're going to push relatable algorithms。

 but I'm going to tell you about sort of a very practical one。

 which is you always pick the one with the highest height。

So if there's multiple vertices with excesses， you look at the current height function。

 the H function， and you look at the one with the biggest H value。So choose such a V。With。

Biggest height。And if there's a tie， you can break the tie arbitrarily。

So now you're always going to prioritize pushing。Okay， so if it's possible。

 right so you have a vertex V， it has access， you want to get rid of the excess， so you want to push。

This is 17。You want to push on an outgoing edge。If possible， if not。

 that's what we're going to do the second step called the relabel。But first。

 let's just say if it's possible to push， then you go ahead and do it。

So why would you not be allowed， So how could you not push。嗯。Oh yeah。

 so this will jump in the gun a little bit。Okay。So here's going to be the condition under which we allow a push to happen。

 So if there's an outgoing edge from V in the residual graph。That goes downhill。 O， Now。

 if it goes downhill。 It can only go downhill by one。 We know that。

 but there might be some edge going out of V， which go downhill。So if there is such an edge。Then。

We push。嗯。OnV。Okay。And I should also say， you know， when we go into the push subroutine。

We're going to push flow on this same kind of edge。好看。So in the final algorithm。Only push on an edge。

BW。That goes downhill。With H of V equal H of W plus1。So， for example。

If this vertex v had excess and we called push on this vertex v， we'd be fine。

Because there is an edge indeed， which goes downhill。So we'd satisfy the if condition。

 And then when we get inside push， we would just route the appropriate amount of flow from V to W1 because it flows downhill。

Now， a totally other possibility。Is that the height function？Assigns via2。Okay。

And so all of the edges out going from Vigo uphill。So that would be a case。

 But this can happen even though V has excess。 So in that case。

 this if statement is not satisfied and something else has to happen。Okay。Okay。

So what's the other thing that happens。 Well， you do a rela。

 which just means you increment the height of V by one。Okay。So else。Increment v's heighte。

And this is known as a relabel。Okay。And that's the entire push for algorithm that we're going to talk about。

Yep。Yep。Does这个 mean push是。I mean， push through the edge VW or just any edges okay。

Any edge that meets this property is okay。I mean in an implementation。

 it would be natural to do the same one， but as far as everything I'll say today。

 all that's important is that it's pushed on a downhill edge and so this is just saying it's like。

 well， you know if there is no downhill edge I'm not going to try to force you to push this is check for a downhill edge if there is at least one push on an arbitrary downhill edge and that'll be fine good question other questions。

Yeah。エスピー？I'm satisfied when all the heights are zero in the beginning。对。

But not satisfied by one name being one area or the other。So remember。

 it's only for edges in the residual graph。That the height condition matters。

So it's definitely important。 So， as we discussed， it's important you don't use the all zero flow。

Then you'd have a violation。Right，But so the point is， with this height function。

 the only possible edges， which might go downhill too quickly are the ones going from S to some of the vertex。

 And it's exactly why we saturate all those edges in the initialization to make sure they disappear from the residual graph。

 So again， unless I say otherwise， the residual graph。

 I delete all edges with zero residual capacity。对。Other questions？So again。

 so there's a lot of things which are not clear。 It's not clear this terminates。 Okay。

 so that shouldn't be obvious， let alone that it should be polynomial running time。

 It's also shouldn't be clear。 It's correct。 Okay， but I just want you to be able to parse the code。

 I feel like you could code this up in Python very quickly。Any questions at that level。Alright。

 so this algorithm works great。 So for the rest of the lecture。

 I'm gonna explain the census in which it works great。 Okay， now。

 also I'm not gonna do it as a programming project or anything。

 but I encourage you to code this up if you ever well I mean。

 you can also just download Maxflow code， which uses this algorithm from the Web。 But you can also。

 of course， implement it yourself pretty quickly if you're a good coder。😊。

It's a pretty simple algorithm。Okay。So it's， as usual。

 I'm going to talk about correctness for a little little bit before proceeding to the running time。

So， the first。thing I want to notice is that the invaris， at least are maintained。

If this wasn't true， we'd be in big trouble， because what are we hoping。

 we're hoping at the end of this algorithm， I guess one thing I should say is。You know。

 notice by our termination condition。If the algorithm terminates。

 it definitely terminates with a flow， right， because all the excesses have to be 0。

 Okay for the wild loop to exit。 So we definitely have feasibility restored at the end of this algorithm。

 if it ever terminates。Alright， and so then what we have in mind， our strategy。

 our plan for solving the max flow problem is we're gonna have feasibility at the end。

 and they're gonna have these invaris which imply that S and T disconnected， the residual graph。

 which implies that we're optimal。 So it better be true that every single operation we ever do doesn't break any of the invaris。

Okay， so the first two ims are fine。We never relabel the source， we never rela the sink。

 so the heights of S&T stay in in zero forevermore。So it's this third invariant。

That we have to think about。And that algorithm does two different things， it can either push。

We're do a rela。we have to argue for both of them that neither one can mess up the invariance。

So how about a rela？Well， so let's remember what the invari says。

 it says edges in the residual grael can only go downhill gradually， okay by one step。

So's under what condition are we going to relabel a vertex？Well。

 the only time we ever re a vertex is if all of the edges out of it， stay flat or go up。Okay。

So if that's the case and we only raise its height by one after we do that。

 any of the outgoing edges， if they go down， they can only go down by one step。

so just by the entering condition of the else clauses。

 there's no way we can screw up the invariant with a relabel。

 you really make sure that we're not going to screw it up before we bother to do the relabel。

So how about a push？What could conceivably go wrong with a push？

So a push doesn't change anybody's heights。 So the H values stay exactly the same。On the other hand。

 the push can change the residual graph。You sent flow on an edge。

 So if the reverse arc wasn't there in the residual graph， it suddenly appears。

So that's what could possibly go wrong。 Okay， you augment along an edge。 you get the reverse arc。

 It's conceivable。 This new edge violates the third invariant。But actually。

 and this is the whole reason why we insist on pushing flow downhill。So notice what this sit。

You only push if there's an outgoing edge that goes downhill， and in the push algorithm。

 we only have a push on an edge that goes downhill。So if we push on an edge that goes downhill。

 the reverse sharc goes uphill。And that's fine。The invariant just systems can't go downhill too quickly。

 Fin can go uphill， it's fine。Okay。So that's the claim。 Any questions about that。Again。

 the upshot here is。The algorithm terminates， it can only terminate。With a max flow。

It's feasible by the termination condition and it's optimal by the invariance。

So before we do the running time analysis， I want to do sort of a detailed example because I know it's probably a little bit abstract until we trace through what this algorithm actually does。

So let's go back。To our network where some of the capacities are really big。

 but the max flow value is actually only three。Okay， so this is what this network looked like。

So what's the algorithm， how's the algorithm going to work？Well， we need to initialize。

 and again that means both the heights and the pre flow。So these are all zero heights。

 so green is going to denote the heights。 What's the height of S？4， right？Is this for vertices？Blue。

 I'll put the flow Mountain in blue。So we initially satured all the edges going out of us。

So we're going to route one unit of flow on this arc。And 100 units of flow on this orrc。AndRemember。

 we already know the max flow value here is 3。 Okay， so there's 100 units going sort of southeast。

 that's going to come back to home to home to roost at some point。All right， so maybe in purple。

 I'll put the excesses right So as soon as you do this push， you have excesses。

You have an excess of1 and V。And you have an excess。Of 100 at W。Okay。So that's universalization。

 everyone on board。So now we enter the main loop， how does the main loop work where we say， well。

 if there's no vertices with excesses we're done， if there are vertices with excesses。

Pick the one that has the biggest height。So we have two vertices with excess， both V and W。

 they both have high zero。 So here we can choose arbitrarily。 let's choose V。So， I get to V。

And the algorithm says， okay， I want to push flow。 I want to get rid of these access if I can。

 So what do I do， I scan the outgoing arcs， and I see if any of them go downhill。

And if so I'm going to send flow on it。 So does V have any arcs that goes downhill right now。No。

 that's heights zero， right， so outgoing ours can only stay flat or go up。

So this triggers the relabel step。And so V is going to be relabeled one。Okay。

It occurs to me I should also， the residual graph is going to keep changing。So maybe in pink。

 I'll say what the reverse arcs are。K。So remember blue is the flow。O。So now next iteration。

 we again say， look at the vertices with excess。 They're the same as before They're V and W。

 Look at the one that it's the highest。 And now we don't have a choice。 Okay。

 so now we're definitely going to invoke push on V again Okay。

 because it's now it has the higher label than W。So at this point。

 does V have any outgoing arcs which go downhill。Yeah， which one？There's actually two of them， right。

 So the arc from V to W goes downhill and the arc from V to T goes downhill。 And again。

 the algorithm， as we're going to analyze it can decide arbitrarily。

And so we're probably rooting for the algorithm to send that unit straight home to T。

 but just to make it interesting， let's assume it doesn't do that。

Let's assume that the algorithm routes the one unit here。So then the excess here goes from 1 to0。

The excess of W goes up one from 100 to 101。And now we get sort of a residual arc here。

 a reverse arc。With a residual capacity one corresponding to undoing that flow。Everyone with me。O。

All right， so now we go back to the main loop。 And so now notice there's only a single vertex that has excess W excess 101。

 So we're definitely going to go to that next。So right now， it has high  zero。

 So certainly there's not going to be any outgoing arcs which go downhill。 So clearly。

 we're going to rela this thing to one。Next iteration， we pick W again。

 we again scan for downhill outgoing arcs， Are there any at this point？Yeah， which one？To tea。

From w to T goes downhill， t is anchored at zero。So what's going to happen？

Is we'll push as much flow as possible from W to T。 now， because this edge has capacity only one。

 it's not much。 Okay， you' just going to push the one unit of flow down along here okay。

So this becomes one unit。You get a reverse arc。And the excess drops back down to 100。All right。

 so next iteration， we again pick W because it still has excess。At this point。

 in the current residual graph， does W have any outgoing arcs that go downhill？Well。

 the only outgoing arcs are it has these outgoing arcs going to V。But that's those are flat edges。

 right，1，1。 And then there's in the residual graph， there's this edge going from W to S。

That's outgoing from W。 But S has height 4。 So this goes from height 1 to 4。 It goes uphill。 Okay。

 so two of them are flat。 The parallel edges are flat。 The other one is uphill。 So no。

 we cannot push on W right now。So we go what do we do， so we relabel。

So now next time we again pick W and we scan for outgoing arcs， which go downhill。And now notice。

 we have some marks。So the two arcs， which go back to V。

 so the one that was originally in the network plus the reverse arc of the flow that we pushed south previously。

 those both go from height2 to height 1。So when we push， so now at this point。

 we can push from W to V。Let me just kind of do all this at once。

So we're going to undo the flow that we previously sent from v to W。

 so let me erase this reverse arc。Make that zero。 and then we're also going to saturate。

The edge from the original graph that goes from W to V。O。What does the excess now become a W？

How much did they go down by？Two， that's right。So it got rid of one unit on this one。

 and it got you of one on that reverse arc， which I erased？And so that access just shows up at V。U。

From V to W， oh yeah， yes， that's true， yeah。That's not going to matter for us。

 but you're totally right。Yeah， thanks。So the excess drops here by two， it goes up here by two。Okay。

Now， what happens next。 So now actually， notice we used to only have one edge with excess。

 Now we have two edges with two vertices with excess again。 So again。

 it's not immediately clear this is making sort of monotone progress in any sense。

So what happens next， Well， so now we go back we say， oh， there's two vertices with excess of those。

 I picked the one with the tire up。So that's going to be W。

So W is going to be chosen next again by the algorithm。So at this stage。

 are there any edges outgoing from W that go downhill？There are not okay。In fact， really。

 the only edge， which is still in the residual graph going out of W is the one going back to S。 Okay。

 so the unique outgoing arch residual graph goes to a node with height 4。

So a double is going to be relabeled。It's going to be still the only outgoing edge goes from three to 4。

 it's relaed again。Now the only outgoing edge is flat， it's going to be relaed again。And now finally。

 at this point。It's going to send its excess of 98 back to the source when where it disappears。 Okay。

 and again， if you think about， we knew this had to happen。 We know the max flow values 3。

 So we should have been eyeing this 100 with a lot of skepticism，So that reduces this to two。

Let me just erase this residual arc。 There are residual arcs， but。Picture is getting too complicated。

 so the point is the excess here goes down to zero。So now in the final iteration we say okay。

 which vertices still have excesses， well V has an excess， it's the only one that does。

 so we go here and we say， are there any edges outgoing from V which go downhill？

There is right so basically from v to t。Goes downhill。 So even though V's only at height 1。

 he's at height 0。 So in the final iteration。B discharges its excess and that gets sent on the edge from V to T。

And this is the。Maximum flow that we computed other previously by seemingly simpler means。Okay。

So obviously， there networks where push re does much more straightforward execution。

 I could even make choices in this network so that it executes much more straightforwardly。

 but I wanted you to sort of appreciate why the analysis we're going to do you know has to have some arguments。

 really some you know， there's no really obvious， you know。

 monotonity argument that says every single push or re。

 something good happens we have to sort of go in through the outdoor a little bit and have a more indirect argument。

Okay。Good。So questions。About the example， about the algorithm。Yep。In the end。

 are the high values guaranteed to be the same？Choices。That's a good question， I believe not。Yeah。

 so， I mean， pretty much all the algorithms we've done so far are underspecified。 I mean。

 it's really obvious and Ferguson where the path can change iteration。 Now， of course。

 you wind up with the same flow at the end， which is maybe your point。

 if you have a correct max flow algorithm， you obviously are going to get the same flow if there's unique max flow here。

 we don't really care about the height function per se。

That's just really a way to organize the pushes to make sure we make healthy progress。

 so we kind of don't really care that different executions can result in different height functions because we throw that away at the end of the computation anyways。

 It's a good question。Other questions，How。Yeah I mean I I don't have a lot to say other than what I said previously。

 so I mean it was known since the 50s that what you want to be striving for is a residual graph with no ST path or you want to disconnect S&T and so I think there's sort of this really key insight which in hindsight like it feels very natural。

 but you can imagine why it would take people a long time to think like switching it around and saying actually you know' if that's what we really want。

 we really want to disconnect S&T， can we have an algorithm which just forget how a determination at every single point。

 it has S&T disconnected。Okay， but well then you have to relax something else。

 You're not just going to initialize with a max flow。

 And sort of the only other thing you have to work with is this feasibility。 So， you know。

 you can try to relax like capacity constraints， but then that seems very difficult to try to restore。

 So instead， it's natural to relax conservation constraints。 Also， you know。

 I think one thing that does come up to people's minds pretty naturally is this flooding idea where you just try to push as much out of S as you can and then just know get it to T and you can't get it to T then route it back。

 And that also naturally motivates why you kind of have this flow in bigger than flow out。

And then really the height function， I mean， these invaris for the height function， you know。

 I can see how they seem a little out of nowhere。 but I think， you know， later in this course。

 I think it'll feel more natural because you' have seen more examples。 You're right。

 the first the first person at some point had to have an argument like this。

 And that takes that takes some insight。 But but that's a sort of this kind of a recipe for these optimality conditions。

 And that's one of the things I'm hoping to sort of convey by example after example throughout the course。

But certainly， I mean， you know， you know， as best as I can， I try to make it feel like， you know。

 you could have come up with this algorithm， know， very naturally step by step。 know。

 and for many algorithms， and many of you， I do believe that's true。 I'm not lying， but you。

 sometimes you kind of step back and just admire like a leap of insight。're like， yeah。

 I may not come up with it myself。 So I'm glad you proved it。 And I can just check the proof。

 I can just learn the proof。 know， So that's what's cool about know， math and proofs。

 like one person proves it， it's true for everybody And then usually verifying it。

 It's much easier than proving it in the first place， which is more or less the P versus MP question。

😊，Propositionition in a layered manner。そ。To cut it into A and P two partition。

 Then everything greater than equal to4 would be one partition and everything less than or。Yeah。

 it's a good， it's a good question。 So， I mean， there's some intuition that maybe there's a cut going on at the same time where。

 you know， you look at the high labels and the low labels and there's some correspondingent cut。

 and you can tweak push for algorithm so that that becomes a formal correspondence。 Actually。

 last year， I put that on a problem set this year， I'm not going to。 So if you want。

 you can sort of think about the height function is encoding a cut in some sense。 Yeah。

We're not going to need that for the analysis though。Okay， so what's actually true about this？

So here's here's we're going to prove。 This is。Due to Goldberg and Tarjn again back in the mid 80s。呃。

So this push rela algorithm terminates。After。Oh n squared relabels。And O N cubed pushes。Okay。

So's the most a quadratic number of relabels， I improve that first。

 and then piggybacking on this and going prove theyre going to be a most a cubic number of pushes。

So this theorem， for simplicity， I'm just gonna focus on the number of times Each operation is invoked each time you do a push each time you do a label。

 That's not the same as a running time analysis of an algorithm。 The algorithm。

 you really have to keep track of all the work the algorithm does。

 not just necessarily pushes and res。So on the second exercise set， I'll ask you to think about。

How would you actually implement this？In cubic time。So cubic running time。

What makes this at least slightly non trivialvi， what makes this slightly non trivial？Is。

The requirement that when there are many nodes with excess。

You're responsible for choosing the one with the biggest height。

So you need to be a little bit smart to think about how to keep track of vertices with excess so that you can always find the highest such vertex in constant time。

I think could always use like a balance search tree to do it in log time。

 but actually the structure of this problem means you can even do it in constant time。

 but I'll ask you to think about that outside of class。

I'm going to focus just on bounding the number of times these operations are in vote。All right。So。

Let's see。Do I have room on this board， not really？Oh yeah， I'm sure you can remember what a push is。

So。Let me state to key lema。If there's time， I'll prove this today。

 otherwise I'll prove it at the beginning of Thursday。

 what I want to focus on is more why this keylema implies the running time bound or the operation count bound。

So what's the limits say？It says consider any graph。Any preflow F。

Consider any vertex that has excess。Okay， so if the excess is positive。

Then the claim is there exists a path。From the。2 s。In the corresponding residual graph。Okay。

So you may not really know what to make of as lemma。The first time you see it。

Let me first just point out that there's very strong intuition for why this lemma should be true。

Okay。You've got a vertex。 It has excess。 What does that mean that means the flow in is bigger than the flow out Well。

 this flow that's coming in， it had to come from somewhere and it basically came from the source originally。

 So there should be some way of just kind of undoing it and looking at a path of reverse arcs and the residual graph that leads back to S from V。

 the flow got there somehow you should be able to undo it get back to S。 Again。

 I'll give you a formal proof for completeness， but that's morally why this is true。

Now it's not obvious why this limb is useful， but that'll become clear shortly。All right。

 so let me show you how you can very quickly derive the bound of the number of relabels from the keylemma。

 Can remember the claim is that the number of relabels is O n squared。Okay， so why is that true？

So corollary。The point is this keylemma。Bounds above how high a vertex can ever go。O。

So the claim is it's the most H of S。Plus n minus1， and as always is the number of vertices。

The source remembers at height N。SoThis is going to be 2 n minus1。

This is a variant argument we had earlier again。A vertex V has excess。

 assuming the key limitma is true。 There's a path from V to S in the residual graph。

This path can only have n -1 edges in it。And edges go downhill gradually by one each time。

 and the source is anchored at n。So if you started V， you traverse a path of most n -1 edges。

 and you went down by a most1 each time step， and you end up at n。

 you could only have started a 2 n -1。 Okay you couldn't have started any higher than that。

 You couldn't have got down to n sufficiently quickly。Okay。

So the kellema immediately tells us that the heights of vertices cannot become unbounded。

 and this is the thin end of the wedge。 From this， we'll be able to derive the rest of the analysis。

So in particular， this immediately gives us。A quadratic bound in the number of relabels。

Okay why well， don't forget， we only ever relabel a vertex if it has excess。

 we don't just like randomly increment you know， vertices that are already fine。Okay。

So whenever you relabel， it has excess， when it has excess， that height isn't very big。Okay。

 so at the end of the algorithm， nobody's going to have height bigger than 2 n minus1。Now。

 there's only in vertices。 So that means a quadratic number of relabels overall。 Of course。

 we're also using that heights never go， never go down。 They can only go up。

So it's the most over of n per vertex， the most n squared relabels overall。

So any questions about the relabel analysis？Yep。So do you see why it's at most O of n per vertex？

So the height of a vertex can't get too big。 That makes sense。 Okay。

 so every relabel of a vertex increases its height。So if the height can only be O of n。

 it can only be re to O of n times there's n vertices that's O of n squared， relabels overall。

Other questions？Okay。So we're going to piggyback on this relabeling bound and derive a bound on the number of pushes。

And。There's really two different kinds of pushes， and we really need to think about them separately。

Where are there two kinds of pushes， well remember？When we choose Delta。

The residue of which is still up here。 Okay， so in a push。

 we could be constrained by one of two things。We can't push more than the residual capacity of this edge。

 On the other hand， we can't push more than the excess of the vertex。

 there's an edge constraint and a vertex constraint，So if it's the case， that。

It's the edge that's constraining so you push a flow equal to the residual capacity of the outgoing edge。

 No surprise that's what's called a non excuse me， a saturating push because you saturate the edge that you're pushing on。

 The other kind is called the nonsaturating edge。So let's the first thing about saturating pushes。

Again， this is the case where Delta equals or again， Dlta is how much flow you augment。

Equals residual capacity。Of youred。So let's argue that not too many of these can happen over the entire trajectory of the push forla algorithm。

So what are we worried about？You know， we're worried that we have some edge VW。And you know。

 we keep running this algorithm， you know， and basically we just keep doing saturated pushes on this edge over and over and over and over and over again。

Maybe it even happens forever， who knows？So how do we say that can't happen， Well， you know。

 run the algorithm to completion and look back over all of the operations that it did。

It did a push on this edge， it did a relabel on this vertex， a push on this， a push on this。

 push on this， relabel it this， etc cea。Look， so fix your favorite edge from v to W。

Iollate two consecutive times where the algorithm did a saturating push from V to W。 Okay。

 so maybe I did it seven times total。 Okay， so look， for example， at the third time。

 it did a saturating push on VW in the fourth time。

 And we want to think about everything which happens in between。Okay。

And so the claim is that in that time window。There have to be some relabels。

So between two saturating pushes。I going add VW。And so and I mean this in the same direction。

 so forward along VW both times。Two saturating pushes of Vw。Each of VW， in the meantime。

Has been relabeled at least twice。Okay。So that's the claim。

 So we're not going to say that you can't do many saturating pushes of a given arc， you can。

But between each pair， consecutive。Consecutive saturating push。

 there have to be at least two relabels of V and W each in between。Now， notice if the claim is true。

A vertex can only be labeled O of n times。That's part of our relabeling analysis。

 of vertex can only be relaed O of n times。So if each pair of saturating pushes triggers two relabels of the endpoints。

How many times can this one edge be have a saturating push？Also， O bit right。

 So the endpoints can only go up O n times。 Each of these triggers going up。

 So you have O n per edge。So summing over edges， that's MN overall。Okay。

So this is even stronger than what we're trying to prove。We're trying to prove N cubed pushes。

 And N M you know， is at worst N cubed。 And generally， it's smaller。 Okay。

 so it's actually stronger than what we need to prove。All right， so why is this true？Well。

Think about the first time you do a saturating push from V to W。Okay。We only push。Downhill。Right。

So the first time we do a saturating push， it has to be the case that， for example。

 this is height 5 and this is height 4 or something else， okay， they differ by one， it goes downhill。

This is a saturating push。 What does that mean。That means this edge gets saturated。

 so it vanishes from the residual graph。So the saturating push deletes the edge from the residual graph。

So how could it be that we ever have another saturating push in the same direction from V toW？Well。

 that can't happen until this arc reappears in the residual graph。

 what causes it to reappear in the residual graph， a push in the opposite direction from W to V。Okay。

So a prerequisite for seeing a second saturating push from B to W is to see a push back from W to V。

Now。Pushes only go downhill。 So if there's ever a push from W to V， it has to be the case。

The w is six or more。Okay。Because heights never go down。

 So for it to go downhill right So initially we have V flowing downhill to W for it to go backward。

 W needs to be raised two steps at least to be above。Okay。

 and now to have a second saturating push in the original direction from v to W， now， of course。

 you know again， it can only flow downhill， so this can't happen until V has retaken its superior position over W。

 which requires it being relabeled at least twice。So for the second saturating push。

 we have some situation like this。So' that's the proof of the saturating pushes at most O of M times n。

 Any questions about that。Yep。Yeah。Yeah， again， you know。Think of it this way。

 So think of it in the original network。 Think of it。 You collapse parallel edges。

 So if you have edges with capacity，7，12 and 19， you know。

 you just add them up and have an edge of cost 38， or capacity 38。For the residual graph， you know。

 you might have two copies in each direction。 You know。

 I'm happy to sort of live with the two copies each direction。

 but I don't want to unbound a number of copies。 And again， for Maxflow it's silly。

 there's no reason to have parallel edges。 You may as well just amalgamate their capacities。😊。

So that's why M is the most O n squared。Right。Other questions。All right。

 so how about the non saturating pushes？So in the detailed example we did。

 we certainly saw examples of both。 Some of those pushes were saturating。 Some were nonaturating。

 Remember， non saturating， what does this mean。This means that the bottleneck is the excess of the vertex。

So we're deelta the amount of stuff that you push。Is equal to the excess at V。嗯。

So with a saturating push， we sort of had a notion of progress that the edge disappears in the residual graph。

 Maybe that was a good thing。For a non saturating push， what kind of progress occurs？Well。

 the excess gets zeroed out at V。So that's what's good about a non saturating push is V used to have excess。

 now its excess has gone down to zero。So we need to somehow leverage that。Okay。So， proof。All right。

 so claim。One other thing。And the algorithm。When there are multiple vertices with excesses。

We're doing some kind of， we have a rule for which one we pick。 We pick the one that's the highest。

Nothing I have told you so far actually uses the fact that we're picking the highest。Access vertex。

So if that's somehow useful for us， this is the part of the analysis where it's going to happen in the final non saturating push analysis。

Okay。So again， run the algorithm to completion and look back in hindsight at all the operations it ever did。

 pushes or labels，lah， blah， bh， blah。Now look at a time window bracketed by two consecutive relabels。

 not necessarily of the same vertex so we have a relabel of some， you know the fifth vertex。

 a whole bunch of different pushes， and then a relabel of like the 12th vertex。

 so we're zooming in on that kind of time window。So what can happen in between these two relabels。

 Well， the claim is only so many non saturating pushes can happen。Between two relabels。

We have a most N。Non saturating pushes。Okay看。That's the claim。If the claim is true。We're done。

We already know there's only a quadratic number of relabels。

 if there's only not O of n non saturating pushes between each pair。

 we have a most acute cubic number of such pushes。Okay。Which is the theorem。All right。

So we're done with the theorem， the analysis overtn。

 except I need to prove the claim which I'll do now， and there's also the key lemma。

 but I'll save that till Thursday。Okay。So proof of claim。So suppose there's a non saturating push。

At the vertex V。So this vertex used to have access。 We do a push now， doesn't have access。

So buy our choice of V。Meaning， because amongst all vertices of excess， we chose the highest one。

Certainly the time of this。Non saturating push， we can say that V has height at least as big as anything else with excess。

That's just sort of immediate， that's just by definition。But what's a little more interesting。

Is that this remains true？Until the next relabel。So at the time it chose V。

 certainly among everything with excess， it was the highest， that's just our algorithm。Now。

Assume there's no more reliable for a while。 We're just pushing stuff around。

We only push on edges that go downhill。Okay， so these pushes can create new vertices with excess。

 but each newly created vertex with an excess is height even smaller than the vertex where it got the flow from。

So if at the beginning。V has the highest height of anything with excess。

 and the vertices with excess just keep getting lower and lower。 Indeed， at the end。

 V is also going to have height， at least that of any other the node with excess。Okay。

So this is true when we choose V by a definition of the algorithm。

 this is true because flow only goes downhill。Good。By the same reasoning。

So the nonsaturating push by definition， it squashes the excess completely。

 Okay so V is x has 0 after the nonsaturating push。 The worry is that at some other point later。

 someone pushes flow back to V and it has excess again。This cannot happen until the next relabel。

Why not， well where would V get this flow from？Flolow only goes downhill。

So it would have to get it from a node with excess that's even higher。

 But there are never any such nodes until there's over label。Okay。

 so V maintains its sort of high dominance for everybody with excesses until this summer label。Good。

So this implies the most n。Non saturating pushes。Till the extra label。

RightSo if you go with full n iterations， if you have n non saturating pushes without seeing a relabel。

You've squashed all the excesses down to zero， one by one。 so again。

 in non saturing pushes without a relabel， you just have everything x says zero and the algorithm stops。

So if the algorithm keep going， you have to keep seeing relas。

 at least one every n non saturating pushes， giving us the cubic bound。

On the number of nonaturating pushes。Questions。Though you should believe the theorem modullo。

 the proof of the keymma。 The keylemma is the one that says anything with excess has a path back to the source in the residual graph。

 So I still need to prove that to you。 I claim I've proven everything else about the theorem。

So that's not clear you should ask a question about it。Y， do explain。AStment。This one。Sure。

 so a non satururing push at V。Reduces its excess to zero。And until there's a relabel。

 it will never become positive again。So for every non saturating push before rela。

 that's one more vertex whose excess you've zeroed out。

So every non saturating push makes the excess says  zero。 It can't become positive。

So if I've done 10 different non saturating pushes。

 I've got 10 different vertices that all have excess to0。 then if I've done any of them。

Everybody has excess zero， but that means I have a flow and the algorithm's done。Other questions？

All right， so we'll kick off Thursday with a proof of the key lemma。

 and then we'll move on to applications of max flow and Min cut。

