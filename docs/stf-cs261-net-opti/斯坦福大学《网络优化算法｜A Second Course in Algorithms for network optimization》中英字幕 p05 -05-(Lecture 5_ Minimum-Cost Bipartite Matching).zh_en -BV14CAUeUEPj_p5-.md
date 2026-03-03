# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p05 -05-(Lecture 5_ Minimum-Cost Bipartite Matching).zh_en -BV14CAUeUEPj_p5-

All right， let's go ahead and get started。So the topic today is again going to be bipartid matching but now a version with edge cost so the min cost perfect matching problem just a quick reminder problem said number one is due a week from today hopefully you've already looked at it and started thinking about the problems it's not that easy the kind of problems which you often take a few days to sort of stew and talk to other people about before you see it a crack them so definitely do not wait until the night before or you'll be in a world of pain unfortunately。

And exercise set two was out， that was posted the end of last week。

 exercise set three should be posted a bit next week。

 so letm me to remind you where we left off on Thursday， which will segue into our next topic。

 so we concluded our discussion of maximum flow applications with a discussion of the biparttheid matching problem。

So remember what's a matching， so if you have an undirected graph， a subset of edges as a matching。

 if there's no shared endpoints， so the edges in the matching need to be disjoint。

And we studied the problem of finding a max cardinality matching in bipartite graphs。

 and again again in matching， a majority of the applications are already captured by the bipartite special case。

 and the theories much nicer and the algorithms are much faster for the bipartid case。

 so that's what we're focusing on。So for example， the squares of apartid graph。

 these green edges would be a particular matching， it would be a perfect matching because it actually matches all of the vertices。

And what we saw on Thursday was that if you want a compute maximum Carally matching in a biparttheite graph that reduces to the maximum flow problem and of course we already know how to solve the maximum flow problem and the reduction was very simple。

 we just added a new source， a new sync， directed all the edges from left to right。

 computed a max flow， and there was a very immediate correspondence between matchings in the original undirected graph and integral flows in the directed flow network that we constructed。

So the motivation for this lecture is。So if you have a bipartite graph and maybe you have the happy case where it has a perfect matching。

 that maybe actually even has like lots of perfect matchings。

 so maybe you're trying to assign courses to time slots， jobs to workers， whatever。

 and maybe there's many ways you can do it。Is there some reason why you might prefer one of these perfect matchings over another？

And in applications， the answer is often yes， you actually do have a preference over exactly which perfect matching you pick。

 you'll see some applications on the second problem set。

 but know you can already imagine if you're assigning jobs to workers。

 you know maybe a given job can be done by lots of different workers but maybe some workers are better at it than others as you'd like to incorporate those preferences into your matching computation。

So here's the formal definition of minimum cost。Bibpartite matching。

Should say perfect bipartheite matching。So the input。So like last time。And a biparttheite graph。

So there's vertices V in vertices W。What does it mean to be biid it means each edge has one endpoint at each of V and W。

 neither v nor W has any internal edges equivalently a bipartid graph is one without any odd cycles。

 Every cycle has to be even in a bipartid graph。And unlike last time。

 it's going to be a more general problem。Where we're also told the cost。CCB for all edges。看。

Now next I'm going to tell you about some assumptions that we're going to have throughout the lecture。

 none of these assumptions are important， all of these assumptions are for convenience。

 there are easy reductions that show that each of these assumptions is basically without loss of generality there'll be some details on this week's exercise set and I'll talk through why right now。

So assumptions and again for convenience only。So first of all。

 I'm going to assume that the two sides have the same carinality。Colllored N。

 so there's two n vertices， n and V and n and W。Why is this without loss of generality where if this is violated。

 just add some dummy vertices to the smaller side to make it true， it doesn't change the problem。

That's assumption1， two sides have the same。Carinality。

I'm going to assume the G has a perfect matching。This may bother you because last lecture the whole point was to check if there's a perfect matching。

 but actually once you have costs， if you think about it。

 this is also a trivial condition to enforce， namely just add some dummy edges that have very high cost so that enforces a perfect matching。

 but it doesn't if there was a perfect matching in the first place it doesn't change the cost of an optimal solution。

All right， so assuming that has a perfect matching， not a big deal。And finally。

 I'm going to assume that all the edge costs are non nick。Okay。Again， for some problems。

 this matters， like for shortest paths， as you know。 But for matching， it doesn't matter。

 the nonnetivity constraint， right， Because if you have a graph with the perfect matching and you're trying to find the best perfect matching。

 Well， you can just add like， you know， if you have negative edge costs。

 you can just add 10000 to every edge。That changes the overall cost of every perfect matching by exactly n。

 the number of edges in a perfect matching times 10，000。

 so it has no effect on the ordering of matches which matchings you're regarding as better than others。

So that was fine if that was all a little too fast in real time。

 I'll ask you to think about this a little bit more in exercise set。

 and for the lecture let's just adopt these as assumptions about the input。And then the goal。

 as I've indicated， is among all the perfect matchings， and there's at least one。

 find the one with the minimum sum of edge costs。So the goal is to find。Perfect matching。Minimizing。

So I'm over the edges in the matching。Of the edge costs。

So I insist that you pair up all of the vertices， and I want you to do it as cheaply as possible。

So for this formulation of the problem， we're really thinking of the feasible solutions not as matchings。

 but of perfect matchings， and then amongst all the perfect matchings。

 there's an objective function you want to optimize， namely some of the edge costs。All right。

 so hopefully it's also clear， you know。Last time we were talking about max carinality now we're talking about minimizing。

 but again， for this problem， it doesn't matter， like the maximum weight perfect matching problem。

 that's the same as this problem。 You just multiply all of the edge costs by -1。

 call them weights and now find a max weight perfect matching。But for a convention。

 we're going to focus on min costs， that's how people usually talk about this problem。All right。

 so in the special case where all of the edges were the same。Okay， so say unit cost。

Then what we saw last time was that you can solve this problem just by reduction to maximum flow。

 so that was when we didn't have edge costs。Now we do have edge costs。

 and it doesn't really feel like the maximum flow problem is going to be able to encode the min cost perfect matching problem。

And the reason is it's not clear what parameters in a max flow instance would encode these edge costs。

 Now， maybe you think， well， I mean， edges in maximum flow， each of them also has a number， right。

 the capacity， But really， that's different。 Capacities and costs are not the same thing。

 A capacity on an edge。 that actually restricts what solutions are feasible。The edge costs。

 they don't restrict which ones are feasible okay the feasible solutions are just the perfect matchings。

 the edge costs dictate what are your preferences over the different perfect matchings so the capacities are about feasibility。

 the edge costs are about optimality so that's the intuition for why this seems like a new problem you shouldn't be expecting you to just give you a sort of easy reduction to maximum flow。

Okay。So it's a new problem， seems sort of incomparable to the maximum flow problem。So， but again。

 you know， Max F taught us that the types problems we're dealing with now， you know。

 you can't just sort of propose random algorithms and hope they're going to be correct。

You need to have a strategy， you need to have some discipline， you need to say， okay。

 well how am I going to improve the correctness of my algorithm and termination。

 what are sufficient conditions for optimality and how do we use that as a guideline for iteratively achieving those conditions and also feasibility。

So we're going to， so that approach served us very well for the maximum flow problem。 So remember。

 what was the maximum flow approach。 Well， first， we had our optimality condition。

 How do we know that a flow is maximum， Well， you， you construct the residual graph and you check if there's an S path or not。

 and we proved if there's no S path and the residual graph within the flow has to be maximum。

So given that we then looked at two different algorithmic paradigms from maximum flow algorithms in the first one we maintained the invariant of feasibility。

 we always kept afloat， these were the augmenting path algorithms， the first three that we studied。

 and then we worked toward satisfying the autoity conditions。

 we worked toward disconnecting S&T in the residual graph。

If you recall in lecture 3 in the push rela algorithm， we flip them around。

 so we maintained as invariant the optimality conditions， but we relaxed feasibility。

 and then we over time worked toward recovering a feasible solution。

So today for the Minco bipart matching problem， we're going to follow that second paradigm。

 something very similar to what we did for push rela。

 so we need to come up with some optimality conditions so given a perfect matching。

 how do you know whether or not it actually really is optimal or could there be some matching that has even smaller cost then once we have the optimality conditions。

 I'll specify some invariance which imply the optimality conditions just like we had invariance and push for label and then we'll design an algorithm which always maintains those invariance and eventually restores feasibility that is eventually actually comes up with a perfect matching。

So that's sort of what's going ahead and the reason I sort of say all this upfront is I wanted to be clear that even though these are pretty hard problems and there are lots of problem specific differences between them。

 there still really is some kind of high levelvel recipe for how you would prove all of these greatest hits of algorithms。

 I mean really there's a mindset which leads you to think about and understand properly these algorithms。

Okay， so step one is optimality conditions。That's the where we got to start。

 So we're not going to talk about algorithms at all。 at the moment， we're just going to say。

 suppose you handed me a perfect matching， how would I know if it was the best one possible？

LetsStart a new board for this。So what we're looking for is an analog of the。

No ST path in the residual graph characterization of maximum flows。

And so just like for the max F and cut theorem， we needed some preliminaries。

 we needed to find residual networks， we needed to define cuts。

 we're going to need some sort of equally natural definitions here。

That concern matchings rather than flows。So suppose we have some matching M， not necessarily perfect。

 it could even be the empty set， that's fine， just some matching M。Then。We're going to call a cycle。

C of the graph。 and remember it's a bipartite graph， so cycles have to be even。

so it could be something like a six cycle。So cycle C of G。Its called M alternating。If。

 as the name would suggest， every other edge of C。Is in the matching。So。

You maybe have some really big graph here。And you have some matching。

And maybe these three edges are also in the matching。

Then that would be an example of a M alternating cycle。Okay。

Now every other edge of the cycle is in the matching， notice。

You're never going to have more than every other edge of a cycle in the matching。

 This is as full as a cycle can get in a matching。Because otherwise someone would be matched twice。

But it is totally possible that you have some matching。

 even a perfect matching and that there are some even cycles which don't have any edges in the matching。

 Okay that can happen， too。 So this just says the cycle is as full as it could get。😊。

So one thing that's cool。About these M alternating cycles is they allow us to take one matching and easily transform it into a second matching with the same cardinality。

Namely， we just toggle amongst the cycles， the edges in the cycle。

 which ones are in the matching and which ones are not in the match。So by toggle。

 I just mean you could take this six cycle， which is alternating， remove the three pink edges。

And replace them by the three blue edges。That would yield a new matching。

And notice that the vertices in this new matching that are matched up。Well。

 they're exactly the same vertices that were matched up before we toggle the edges。

So obviously there's no effect outside the cycle， inside the cycle。

 everyone was matched both before and after， just in a different way to each other。Okay。

 does everyone clear on that？So an M alternating cycle allows you to do this toggle operation。

 okay and we'll see why that's used in a second。So that's the first part of the definition。

An alternating cycle。An alternating cycle is negative。

If the costs of the edges in the matching in the cycle， exceed the costs of the edges of the cycle。

 not in the matching。So if some over the edges。That are in the cycle and also in the matching。

Exceeds。The sum over the cycle edge is not in the matching of their costs。So， for example。

Here's an even cycle。There's a perfect matching。And this force cycle is indeed a negative cycle with respect to the pink matching。

So first of all， it's alternating， edge in edge out， edge in， edge out， and secondly。

 the edges in have cost 11， the edges out have cost nine。Okay， so that's the。Ngaativity。Condition。

So a negative cycle。All right， everyone clear on those definitions。With those definitions。

 I can state the optimality condition。Okay。Well actually let me ask you so any guesses like why so what are we trying to do。

 we're trying to understand how do we know whether a given perfect matching is minimum cost or not or that's what the optimality condition is supposed to help us with so why would I make this definition of negative cycles what does the negative cycles have to do with the question of whether or not a perfect matching is minimum cost。

Anything。Or just pull this out of a hat。Its sort of like the hall problem good。YouGet none of these。

 and it's probably going to be off。If we have no negative cycles right good So a suggestion was drawn with the halls theorem。

 which was giving us away， how do we know whether matching is maximum cardinality or how do we know if a bipartite graph has a perfect matching And so what we saw with hall's theorem was we saw well there's one simple kind of obstruction or what I was calling constricting sets So you have a subset of vertices on the left hand side So that the number of neighbors on the right hand side is strictly smaller So if you have 10 vertices on the left with only eight distinct neighbors on the right。

 no way are you gonna to have a perfect matching at least two out of those 10 vertices on the left are going to have to be left unmatched And then hall's theorem said the only obstructions where the obvious obstructions as long as for every subset on the left the number of neighbors on the right is at least the size of the set this is the nontrivial part of the theorem that。

That guarantees that you have a perfect matching。So let's build on this。 So what's the analogy Okay。

 so negative cycles， what do these correspond to just to sort of like a pattern matching with our discussion of。

 say Hall's theorem， you can also make an analogy with Max Fment cut if you want。

So a different way of saying it would be， what's the easy direction？

Right so Hall's theorem said there's a perfect matching， if and only if。

There's none of these constricting sets。So the analogy of that would say a matching really is minimum cost if and only if there's some absence。

Of obvious obstructions。So what I seem to be leading you toward is maybe these negative cycles are obvious obstruction。

An obvious proof that a certain matching is not minimum cost， maybe that's going to be the easy part。

 that if you have one of these negative cycles， there's no way you're optimal。

 and then there's going to be a non-trivial part which says， if you're ever not optimal。

 there would always be an explanation of this form。Okay， so theorem。Perfect matching M。

Is minimum cost， if and only if。There are no negative cycles。And as suggested。

 very much in the spirit of having a perfect matching if and only if there are no constricting sets。

All right， so this is an if and only。 So we need to prove both directions。

 So which is the easy direction， right to left or left to right。Good。

So left to right is the easy direction。As was suggested。What's the proof of that direction。

 how's it go？Intuitively。There is a negative。How come？Because you can。Good。

 so the proposal is you can use a negative cycle to toggle ledges and transform a matching into one with strictly smaller cost。

Frink。So a little more formally。So if there exists， M alternating cycle。Wt we say that， so negative。

So if there exists a negative cycle。Xi。Yeah。Then remember。

 negative cycles by definition have to be alternating。And remember， alternating cycles。

 you can toggle the edges and get a new matching that matches exactly the same nodes。

 So if you had a perfect matching and you toggle inside an alternating cycle。

 you get another perfect matching。So suppose we do this toggle。

What effect does it have on the total cost of the matching？Well， these edges go away。

 They used to be in， and now they're out。 so the cost drops by this much。

These edges used to be out and now they're in。And so the cost increases by this much。The net effect。

 right， It drops more than it gets increased。 Okay， so the net effect is a drop in the overall cost。

So let me use for this toggling operation， let me use the notation circle plus so you can think of this either if if you want to think about these as edge setss。

 M is a matching subset of edges， C subset of edges。

 you can think of this a symmetric difference if you prefer to think of these as like01 vectors then I'm just doing an x or so point is I'm looking at the edges。

 they're an exactly one of M or C。And this is how you'd algebraically write the toggle operation if you think about it。

So vent toggling gives us a cheaper。Perfect match。对。So any questions about that？

This supposed to be the easy direction， so if you're lost， let me know。

So I hope this direction is clear。All right， so let's do the hard direction。So again。

 what are we worried about？So at this point， we're convinced it's like， oh yeah， well。

 if you ever show me a negative cycle， I'm definitely convinced that the thing is not minimum cost。

The worry is that you have a matchingsh， which in fact， isn't that good。 it's not minimum cost。

 but there does not exist any negative cycle that proves it。

 So that's what we have to show can't happen。So for the reverse direction。

Let M be a perfect matching such that there's no negative cycle？Okay。Yeah。So at M prime。

 be a competitor。Any other perfect matching。 So you want to show that our matching M is cheaper than any other perfect matching M prime。

Okay， so pick your favorite。Yeah。So how are we going to prove that M is at least as cheap as M prime？

Well， we're going to now do sort of a generalized toggle operation。 Okay， so again。

 it's going to be the symmetric difference slash Xor。So again， what does it say。

 this says you look at the subset of edges that are contained exactly one of M and M prime。

So maybe some pictures would make this clearer。对。So。Here are two perfect matchings。

What is their symmetric difference？Oh。The pink edges， as usual， are the matching edges。

How would you describe the symmetric difference？exception。Good。The entire boundary。Yeahep。

Each of those edges is an exactly one of M or M prime。

whereas the middle edge is in neither M nor Mtro， so it's not included。So what if we take the same M？

And we think about the following different perfect matching。

What's the symmetric difference of those two perfect matchings？小gan。The left square good。

So this appears in both， so it gets canceled out。And each of these four edges is in exactly one of them。

O看。So that's the Ex door operation， any questions？Okay。So。We exed two perfect matchings。

 we got a six cycle here。We exd two perfect matchings， we've got a four cycle here。Obviously。

 I could paste copies of these gadgets together so I could get a collection of disjoint cycles。

 and actually， if you think about it， that's all you can get if you take the XO of two matchings。

Why is that true in general， well tell me the following， zoom in on your favorite vertex。

WhatWhat are the possible values for the degree of your favorite vertex in M plus M prime？

And other hand， there's two different possibilities。Zero or two。

Okay why because each of M and M prime have degree1。

So either they're the same edge and they cancel each other out。Or they're not。 And then you get。

 I guess this is reoring perfect matchings， I should say actually。And so you see both cases here。

So here's zero degree and here's degree2。So M&M prime both have degree one。

 either they cancel your degree drops to zero or they don't cancel they get degree2。

A graph where all the degrees are either zero or two， that's a union of disjoint cycles。

That's all it could be。All right。So， so what？Let me remind you who we're trying to prove。

We have our perfect matching M。 We're assuming no negative cycles。

 We're trying to prove it's optimal。 we're trying to prove it's better or cheaper。

 at least as cheap as this one competitive， perfect matching M prime。So what do we？What do we know？

So the difference in this sense between M&M prime is just a collection of disjot cycles。

 each even each alternating。So what this means is we can transform capital M into capital M prime just by toggling the edges in each of these cycles。

For example， in this first example， if I take this six cycle。So I'm sorry。

 if I toggle the edges with respect to this six cycle。I get this matching。Down here。

 if I take this force cycle and I toggle the edges in this force cycle， I get this matching here。

Okay。So when I take the XO and I get my cycles， it gives me a recipe for transforming M into M prime just by toggling in each cycle independently。

 the cycles are disjoint， they don't interfere with each other so I can just do this toggle separately for each。

So can a pain m prime from M。By toggling the edges。Of。The cycles， which remember are not negative。

Sure。By assumption。So if you toggle a perfect matching by a non negative cycle， what does that mean。

 what non negative mean， I mean， the edges that are dropping out。

Have cost at most as much as the edges are coming in。Okay， so because the cycles are non negative。

 just like it' the reverse of the argument of the negative cycles， talk about a non negative cycle。

 the cost that goes up。So because you can obtain M prime from M by such toggles。

 M prime has to be as at least as expensive。And that's the proof。

So this completes the optimality conditions for the men cause by part their matching problem。

So if you want to convince me something's minimum cost， convince me that there's no negative cycle。

Any questions about that， so again， this is the analog of there being no ST path in the residual graph。

Or the analog of having none of these constricting sets in Hall's theorem。Okay。

So we're going to continue。Repeating what worked for us in the push Re algorithm。

If you recall with push re label， it's a augmenting path。

The automatic conditions only held at the very end of the algorithm。

 if you're running Ford Ferson or Edmond's Kp， you always have a path in the residual graph， I。e。

 the opt conditions fail until the very end， that's your termination condition。

Where push for label was different， we said， let's actually maintain the automaticity conditions at all times。

The push label algorithm always had the property that there was no SD path in the residual graph。

So when you have an algorithm and you're trying to prove that something thing is always true。Usually。

 the strategy for doing that is identifying suitable invariance。 We saw that in push rela。

 We had these invariants saying the height of S was n。

 The height of t was 0 and edges can only go downhill gradually in the residual graph。

 And then we argued that as long as those invariants stay true， we don't have to worry。

 the optimality condition holds。 So that's the next step here as well。

Now we understand when we're done， we're done as long as there's no negative cycle。

 so next are some invaris which we're going to maintain in an algorithm and as long as these invaris are satisfied。

 the automatic condition will be triggered and once we've got that right。

 all we have to do is work toward feasibility。All right。

And in an even stronger analogy with push re label， really。

 what we need to do so we're going to be starting from the empty matching。

 and we're going to be building up to a perfect matching。

 So we're going to be increasing the cardinality of our current matching by one each time。

And just like in push re， when we were pushing flow around。

 we needed some kind of discipline about when we were allowed to push flow。

 and the solution in lecture  three was you could only push flow downhill。

 we were never allowed to push flow uphill， and that's what led to our termination and good running times。

So here again， we're going to need some kind of way to in a disciplined way only allow certain kinds of augmentations so that the invariants stay true and just like push Relabel。

 we're going to do this by having a sort of annotation a number for each vertex okay remember in push Rela we had these heights。

 we just made those up remember okay that just sort of helped us design a correct algorithm the problem statement of max flow and the output of the problem don't talk about heights that was all inside our algorithm and analysis here again there's nothing about nodes。

 we just have this graph with edge costs and our algorithm and analysis。

 we will attach numbers to nodes so that we can maintain these invariance and hence the optimality conditions。

It're going to maintain a matching M。Again， initially empty， eventually perfect。

And I was calling them heights for push rela here， they're usually called prices， they're similar。

 they're not exactly the same though。But whatever， it's going to be a real number that we keep track of with each vertex。

On both the left and the right hand of the bipartec graph。And。All right。

 so the algorithm is going to be maintaining both capital M and these Ps。

 and just like with push rela， we're going to have invaris that relate the current solution。

 the current matching to our current function on nodes， our current prices。So to the invariance。

 I need one really simple but crucial definition。Which is that of the reduced cost？

So fix a price for each vertex。To the reduce costs are with respect to prices？And for an edge VW。

 the reduced cost under P。Is just the original cost？

With the prices of the two end points subtracted out。

So the original edge cost minus the price of one endpoint minus the price of the other endpoint。

And so I can tell you what the invaris are。And again， they may initially look sort of mysterious。

 but I'm going to show you that these invaris are a sufficient condition for the optimality conditions and really that's how you come up with these endvariances。

 You kind of say what would imply the optimality conditions。

 and this is the kind of thing you come up with。All right， so invariance， first of all。做唔到。

All reduced costs should be non negative at all times。Okay。

 so put differently that sum of the prices on the two endpoints should be at most the original cost of the edge。

 that's saying the same thing。And then secondly。And this is the part which is sort of analogous to saying we could only push flow downhill。

For every edge in M。Just remember， we're maintaining both prices and a matching。

 So for every edge in our current matching。Is tight。By which I mean the reduced cost is zero。

 the smallest it can be。And those are the two invaris。So for example。

Suppose you have the following graph。So herere the edge costs， so again to talk about the invariance。

 I have to tell you what the current matching is， I have to tell you what the current prices are。

So let's say the matching is this one。And let's say。All right， well， let's start this way。

So if have that combination of a matching in prices。M。Are the invaris satisfied？Isvari too satisfied？

Yeah， variant two is fine。Vant 2 says that the sum of the prices on the two endpoints of a matched edge should equal the cost of the edge。

 and that's clearly true，7 plus0，7，2 plus02。 What rather variant 1。Which edge is broken。

 which edge is invari number one is broken， I guess I need to give you some。V1， W1， V2， W2。Yeah。

 V1W2 is busted。Because this edge cost is six， but the sum of the two prices is seven。

 that gives you a negative reduced cost， and that's what's not allowed。If I。For example。

 change this to whoops， that's what I want。I I change this in this。How about now？Now we're good。Yeah。

2 plus two is four， less than five， five plus zero is five less than6。

So the two edges in the matching have zero reduced costs。

 the two edges outside the matching both have reduced cost one， which is fine。And as we'll see。

 it's not a coincidence that this matching is indeed minimum cost perfect matching。All right。So Amy。

 so what I'm going to do next is prove that as long as the invariances are true。

 there's no non negative cycle， which is which Re is our optimality condition。

So any questions for you that， and that's also the motivation for the variant？

So is it clear what the statement is， what all the definitions are？Okay。All right。

 so let me justify these invaris。By saying if we keep them maintained and we come up with a feasible solution。

 that is a perfect matching， then we're optimal and we're done。So if M is perfect。

And the invariants one and two hold。TheM is， in fact， optimal。Okay。So wise is this cool。 Well。

 I mean， this now gives us sort of this gives us some serious guidelines into how we might design our eventual algorithm right so we're thinking our algorithm is going to start with empty matching and then build up edge by edge to a perfect matching。

 And it just says we have to figure out a way to do that so that we keep these invariants satisfied。

 And that's it that's now all our algorithmic problem actually is thevari keep the invariance maintained。

😊，Keep increasing the cardinality of the current matching。 if we can do that。

 home free by this Clint， because this claim would then imply that once you have a perfect matching at the end。

Because of the varianceance hole， you have no negative cycles。

 because of the automatic condition you got to be on the hold。All right。So proof。Well。

 to show that M is minimum cost， we know all we have to show is that there's no negative cycle。

 That's our optimality condition。 So long as we show there's no negative cycle， we're done。

So fix your favorite potential negative cycle。So an M alternating cycle。Okay。

 so we're assuming M's a perfect matching， we're assuming the invariance hold。

 we're trying to prove that there's no negative cycle。All right， so again， remember。

What does an alternating cycle look like？Well it's going to be an even cycle because it's a bipartite graph and alternating means it's as full as it could be。

 so every other edge is in the match。And as we've been discussing， previously。

 we were using the fact that you can togg leds inside such a cycle and transform one perfect matching into another one。

Okay。So the rest of the proof will fit on this board。Again。

 we're trying to prove that C is not negative， we' trying to prove that C is non negative。

So remember， remember negative cycles， we have to compare the edge costs of the edges in the matching and the cycle to those that are not in the matching in the cycle。

 so let's write those two out。So on the one hand。We have the edges。In the matching in the cycle。

And then we have the edges of the cycle， not the matching。

We're trying to prove that this is at least as much as this， that this isn' at most that。

So I'm assuming the invariance holds。 So I have to somehow use that in the proof。

 So what are the invaris buying me？Well， the invaris are about reduced costs。

 right there're about these CPs。They're not about seas。So somehow just strategically。

 it seems like maybe I want to。Force this to have some reduced costs in it so that I can apply the invariance。

So I really would rather have。This， so again， when we say the invariant satisfied。So this means。

 you know。For our price function fee。Okay。So we have a perfect match again。

 we have some price function the invariance hold。So what I just wrote here is not correct。

OkayIt's not correct。Reduce costs are not the same as the edge costs。

 reduced cost of the edge costs with the prices on the two endpoints subtract it out。

On the other hand， because C is an alternating cycle。Every other edge is in the cycle。

So every endpoint of the cycle， sorry， every vertex of the cycle is the end point for exactly one of these edges。

So in a 10 cycle， you have five edges in the set。And each of the 10 vertices of the cycle is the endpoint of exactly one of them。

So if I just add back in。The sum over the vertices。Of the prices。

Then this is so that should be over the cycle， not over the vertices。

Then the equation actually holds。All I've done is subtracted this number， sorry。

 added this number and subtracted it back out。 the subtracted part。

 I'm kind of burying on reduced costs。Is it clear？Again。

 just add and sub to some of the prices of the vertices in the cycle。

Obviously we can do the same thing for the。Other half of the edges in the cycle。Again。

 because this is every other edge of the cycle， so every vertex arises at the endpoint is of exactly one of these edges。

And so now we can take stock， right So we have this equation， we have this equation。

 let's compare term by term。Obviously， these are equal。It was literally just the same expression。

 so we can forget about that。What about here？Which is bigger， top or bottom。关系。Indeed。

 the bottom is bigger。So we need to remember the invaris， what do invaris say？

Reduce costs are always non negative， first of all， and second of all。

 for any edge which is actually in the matching， the reduced costs is as small as it could be。

 has to be zero。So by invari number one。Each of these terms is not negative。And byvari number two。

 each of these is zero。Every these a different， that's fine。Yeah， let's do this。So。

The bottom is bigger， can only be bigger。Okay。So here we have something small， plus something。

 we have something bigger， plus the same something。So over on the left hand side， overall。

The upper left hand corner is at most the lower left hand corner。

 that is the cost of the edges in the matching and in the cycle。

 is at most that of the cycle edges that are outside the matching。

 that's the definition of a non negative cycle。Questions。All right， so we've actually。

Haven't said anything about algorithms yet。And again。

 this is characteristic about how one successfully develops correct algorithms for these sort of harder problems in P。

Like maximum flow and min cost bipartite matching。So we started with optimal conditions。

Those really weren't algorithmic at all， at least not on the face of it， that was just structural。

But then we sort of compile the automatic conditions into these invaris。

 which now feels a lot more algorithmic so now rather than just trying to figure out how do we eventually at some point satisfy this automatic condition。

 we're like， oh no no， let's just make sure we initialize our algorithm so the invariance are hold and let's just make sure that every step of the algorithm doesn't break them。

And hopefully we eventually terminate with the。Perfect match。Yeah。

So I'm going to tell you about a way to do this， famous algorithm。Known as the Hungarian algorithm。

So this algorithm was popularized by Harold Khn in the mid50s。

So it's kind of weird that Har Coun is an American。It's called the Hungarian algorithm。

 so it's a story。Well， so there's a famous graph theorist called Conig。He wrote the first book ever。

 actually in graph theory back in the 30s。And so Conig was Hungarian。

 his books in German and it didn't make it to the States at all until 1950。

 and I think it was still then only in German。 So Cohn was reading Conig's book。

And he really wanted to solve this exact same problem we're talking about。

 so for practical and theoretical reasons， he wanted a good algorithm for this minimum and cost bipartite matching problem。

And so in Conning's book， there was a sort of stray citation。To this paper of Agavari。

And so he somehow tracked down this article， which was written in Hungarian because Zgavari is Hungarian。

 and he bought himself a massive Hungarian dictionary， remember in the mid-'50s。

 there's no Google Translate in 1953 okay？So he lies a huge Hungarian dictionary。

 translates to paper and realizes indeed Agavari had sort of all of the essential ideas for a good algorithm for this problem。

 for the Minco biheid matching problem， so he named it the Hungarian algorithm after Conig and Agavari。

 whose ideas he was borrowing quite heavily。Sometimes you also hear it called the Kne Monies algorithm。

 this is the same monkeyies so you might know from topology。

 so Monries has kind of observed a polynomial running time bound on K's algorithm。

 Kne just stated termination， Monies stated a polynomial bound the same one we'll see today。

And then actually less about 10 years ago。It was just discovered that actually an equivalent algorithm was already known in the first half of the 19th century by Jacobbe。

The famous mathematician who you know from like Jacobians and a million other things。

 So never he never published it， but it was in his notes。

 It was published posthumously in I forget which language。

 But it took a while for people to figure it out。But they did 10 years ago they realized it's actually from the 1840s or something like that。

 So Harold Khn， before he died a few years ago， he was in his 80s and he was giving talks which said the Hungarian algorithm and how Jacobbe beat me by 100 years。

 which I thought was。Kind of a good attitude about it。So what's the algorithm？

We want the invariance at the beginning， we want the invariance always。

 how do we get them at the beginning， while it's going to be easy， it's easier than in push re label。

So the matching is the obvious one。Empty set。How do we set the prices well？

Because we have this standing assumption that all of the edge costs。

 the original edge costs are non negative， which again， is just for convenience。

 It's not that important。 But with that convenient assumption。

If I just take all the initial prices to be zero。Then both invaris hold。

So with invaris say all reduced costs are not negative， that's true with zero prices。

 if the edge costs are not negative， all matched edges are tight， there's no match edges so whatever。

So the main loop will take me a little bit to describe。So remember， we're maintaining these invaris。

 so we're not worried about correctness at termination。

 but we're worried about is feasibility and push relaed。

 what we're worried about was getting back to a feasible flow here we're worried about somehow getting to a perfect matching。

So the termination condition， therefore。Willll be while M is not perfect。So that when we term A。

 we're done。And ideally， for each iteration， we'd like to increase the cardinality of the matching by one until we have the perfect matching。

It's going to be a little more complicated than that， just in the way in push relabel。

 sometimes we made progress by pushing other times we had to take a step back and do some relabeling instead。

So here， what I to prove is that there are two good things that can happen， two good cases。

 in one of the cases we're going to do an update to the matching analogous to a push of a flow。

In the other case， we're going to do an update of the prices。

 sort of analogous to a relabel and push rela， and so I'll show you a sense in which both of those good cases make progress。

 and then I need to prove to you that always one of those two good cases applies。

So that's the high level structure what we're going to talk about。All right， so good case， so dot。

 dot， dot， dot dot， okay。So it'll take a little while before I can actually tell you what the pseudocode is。

But it is， it's like these two subroutines， it's like check if case one is true or case two is true。

 in either case do the appropriate thing that makes progress。

 either on the matching M or on the prices P。So good case number one。Is that there exists。

But I'm going to call it a good path。What is this。So what's a good path， Well。

 it has to satisfy a bunch of things。I guess let me show you a picture just to。

To show you what we're trying to capture here。So have in mind a case where this is our graph。

 or these are the tight edges， maybe。This is in our matching。And then a good path。Is going to be。

This green path。Okay。So that's a picture I want to keep in mind。Formerly。

 what are the requirements of a good path？So it begins， it originates on the left。

And it ends on the right。Okay， so I hear。Starts on the left， ends on the right。

V and W should be unmatched in the current matching capital M。As it is over there。Three。

 we want it to be an alternating path in exactly the same way as we were talking about alternating cycles where every other edge is out of or in the matching。

Now observe， so if it starts on the left it ends on the right。

Does the path have an odd number of hops or an even number of hops？number of hops， right。

 it might be one hop or it could be three hops or five hops or whatever。So if it's alternating。

And the first vertex is unmatched， and the last vertex is unmatched。

Then the first edge of the path and the last edge of the path are not in the matching。Okay。

 so alternating here is going to be out of the matching in the matching out in and then again out at the end。

 so if it's a nine hop path， you'll have four edges in the matching and five edges out of the matching。

Okay， so alternates。Edges。Out of in。For。All edges of pe should be tight。Remember。

 tight means the reduced cost is zero。So what's the point of this definition。

 what I'm trying to do is give you conditions under which we can safely increase the cardinality of the matching。

Okay。So the point of this path is it allows you a systematic way to take a matching。

 get a bigger matching， and match it with more edges， and furthermore。

 this is the motivation for using only tight edges， we don't want to bust any of our invaris。Okay。

20 questions about the definition of a good path。So why do I call it a good path。

 what's so good about it？We'll consider taking the symmetric difference of the Xor of the current matching M and this good path P。

Okay。So for example， in this picture， if we take the XO of the pink edge and the green path。

Then what we get is this perfect matching of blue edges。O。More generally， this is again。

 a toggling operation。So what this does is it takes the edges of P。

 which used to be in the matching and kicks them out， takes the edges of P。

 which used to not be in the matching and puts them in。Okay。Remember。

 we said that the first edge and the last edge of this path are out。 Let's see you have a。

 if you have a nine hop path，5 or out，4 in。 So when you do the toggle。

Four dropout at five get included， so the cardinality of the matching has increased by one。

So Mx m plus P。A bigger matching。So that's definitely progress。

 Remember we're trying to get to a perfect matching。

So we have a bigger matching and we need to never screw the invariance and we haven't done it。Okay。

 so in varianceance。Still hold。Why， so why can't the invariants be broken？Well。

 we changed the matching， but we didn't change the prices， so we didn't change the reduced costs。

 so there's no way we screwed up in variant at number one。

 because we didn't change anybody's reduced costs。Invariant2， what could go wrong well。

 if we put an edge in the matching， which is not tight， then we'd be doomed。

 but we insisted that the good path has only tight edges， so invariant 2 is fine as well。

And so this can only happen。At most end times。Okay。

So we're super happy whenever we're in the main loop and we find a good path。Okay。

 we love it if it just like n times in a row， we just kept finding a good path after good path and that was it。

 and we terminate with the perfect match。Then we'd be done， the invariance would imply optimality。

Okay。So any questions about good case number one。Claiear so far。That's the easier case。

 the case isn't too much harder。Okay。So good case number two。So suppose there is a good set。Which。

 by definition， will be a subset of the left hand side vertices。And she says， about two properties。

Contains at least one unmatched vertex。And then secondly。

Remember when we talked about Hall's theorem， we talked about the neighbors of the neighbor said of a subset of the left hand side。

So we're going to talk about the neighbors， the neighbors not with respect to the original graph。

 but with respect to the tight edges。So we look at vertices in a set on the left。

 we look at any edges of them which are tight， and then we add the corresponding neighbors into the set capital Ns。

So maybe you have a couple edges that are actually in the matching， they're definitely tight。

But you can also have tight edges which are not in the matching。So this is NFS。And again。

 let me reiterate whenever I talk about the neighbor set I'm always talking about in the subgraph of tight edges only。

Why tight edges only。I mean， that's what's relevant for good paths。

 good paths are all about tight edges。Okay， and so what's condition two， condition two is that。Every。

Vertex of the neighboring set amongst the type edges。Is matched。To some vertex of S。In M。Okay。

Which you'll note is true in the picture that I drew。So there's four nodes on the left。Amongst them。

 between all the tight edges that they have， there's only two different neighbors on the right hand side。

 both of which are matched to two of the four vertices of Ss。So that's a good set。

It's a little less clear why this might be useful， so let me explain。

So I guess let's make a couple simple observations first。So in this picture， I drew。

There are four vertices on the left and there's two vertices on the right。

So it was in an accident that there's more nodes on the left than the right。

Or is that going to be true more generally of any good set？Suppose in general。

 I told you there were 10 nodes on the right hand side。What could you say about the left hand side？

There's at least 11。Why， well， condition2 says that these 10 nodes on the right。

Have to be matched to nodes on the left。 It's a matching。

 So they're matched to distinct nodes on the left。So that gives us at least 10 nodes on the left。

 but then I also insisted that there was one unmatched node on the left that gives us a lead。

So just from the definition， we're always going to have that。For a good set。

 the number of neighbors on the tight edges on the right hand side is less than the number on the left hand side。

 So is analogous to the constricted sets we talked about in Hall's theorem。Another key property。

Is that no edge of the matching？Basically， every edge of the matching is either in this picture completely with both endpoints or completely out of the picture。

 neither endpoint。So no matching edge has。Exactly one。Endpoint。And S union NFs。Okay。So why not。

 well work as such， how could that happen？You could either have a matching edge。

 which was incident on somebody on the right。But that's impossible because everybody here has already matched to people inside S。

Or you could have a matching edge from the left to somewhere outside NFS， except no。

 you can't because matched edges have to be tight and this is all of the tight edges by definition out of the left hand side。

So each matched edge is either all in this picture or all out， only two cases。All right。

 so what so okay， Supp I gave you a good set， What would you do with it When I gave you a good path。

 it was obvious， you come up with a better matching。

 So again here we're not actually going to make any progress on the matching。

 but we're going to update our prices。So here's how we use this good set to update the prices。

So why is this good？Here's going to be the price update。Fra all vertices is on the left hand side。

We increase their prices by Delta。I'll tell you what Delta is in a second。And on the right hand side。

 we're going to decrease the prices by Delta。So increase。P of V by Delta。We're all W and NFs。

Decrease P of V by delta。With's Delta， Delta is as large as possible。You should be wondering。

 how do I know how big a Delta is possible？So let's think about。

How a price update of this form changes the reduced costs。

 and so that'll help us understand what Delta is and in what sense we're making progress。So how does？

The reduced cost。Of some edge VW change。So again， we've taken all the vertices on the left hand side S。

We've jacked up their price by Delta， we've taken all of their neighbors along tight edges， NFs。

 and we've dropped their prices。By Delta。Well， suppose you have an edge which has an endpoint on both the left hand side and the right hand side。

What's the change in its reduced cost？Zero， exactly， nothing。Because remember the roos cost。

 you subtract both the prices， if one of them went up by the same amount， the other one went down。

 their sum is the same。Similarly， obviously。If。An edge that has no endpoints involved in this picture at all。

 its reduced cost doesn't change just because neither are the prices of its endpoint changes。

So there's really only two interesting cases。One case。Is an edge like this？

What can we say about such an edge？There's something that can't be。

By how we define the neighbors at NFs。It can't be tight， that's right。

Why can't it be tight because by definition， NFS contains all of the vertices adjacent to vertices of S on tight edges？

So good。So if it's not tight， that means it has a strictly positive reduced cost。

The other kind of edge that's sort of interesting。Is if the right endpoint？Belongs to NFS。

 but the left endpoint does not belong to S。That's also possible。Okay， so what happens， well。

 let's consider these two cases right， so first let's consider the first case。So a V is an S。

And W is not in the neighbor set， so that's like this edge here。What happens with the reduce costs。

 does it go up， go down or stay the same？goeses down。By Delta。It's right endpoint isn't changing。

 same price as before， its left endpoint goes up by Delta。

 which means the reduced cost drops by Delta。Now， remember was the case where this had to be the case it was not a tight edge。

 so it had a strictly positive reduced cost， so it's strictly positive and the bigger and bigger we take Delta。

 the smaller and smaller we're making it。So it goes down。And then symmetrically， in other case。

 if the left endpoint is not part of S and the right endpoint is part of N of S， then it goes up。

No change otherwise。是。All right， so everyone clear on the。

Ways reduce costs change as we change these prices。Okay。

So let's go back to the question of how big can Delta be。

 how much can we jack up prices on the left and drop prices on the right？Well。

For every edge of this form。The bigger we make Delta。The smaller it's reduced cost。At some point。

 some edges reduced cost will be dropped all the way to zero。

Remember one of our invaris says that reduced costs are not allowed to go negative。

So how do we choose Delta， we choose it as big as possible。

 such that no reduced cost becomes negative， and the only edges we're worried about are edges of this type。

 the first type over there。Yeah。Now， at that point， when its reduced cost becomes zero。

That edge is now tight when it was not。Before。And that's going to be a type of progress for us。

 We've increased the number of tight edges。That's not as exciting as actually making the matching bigger。

 but again， it's going to lead us to it's going to lead to the matching getting bigger。All right。

 so you do this update。Eventually。Some new edge becomes tight。

So you just jack up Delta until somebody's reduced cost becomes zero and that's where you stop。

There's actually a small bug in what I'm saying。How do you know that you didn't make anything un negative with your。

WithSo remember， our reduced cost is the cost minus the prices。 So when the price drops。

 it only jacks reduce costs up。The prices can be whatever。Yeah， so it's a good point。

 I didn't emphasize that， but prices can be positive or negative， it's no big deal。Yeah。

 so we don't care about that。 We just care about reduced cost being non negative， good question。

And again again just to reiterate one point， so edges of this form。

 they reduce costs are going down so they can strain how big we can take deelta。

 these reduced costs are only going up so we don't really care how much they go up by It's possible they used to be tight and now they're not tight。

 that's fine they're just going be positive instead of zero。All right。

 so there's a little bit actually of a bug with this statement。

Kind of a logical gap in what I'm saying。Do you see sort of an edge case that strictly speaking。

 I should？Address for you。Excellent， excellent， what if there's no such edge？

So what if every single edge？Incident to S actually is already incident to NFS。Right。

Why is that a problem， Well， then there's no constraint on how big I can take Delta。

 right I increase Delta and nobody's reduced costs are going down。

 so I can take it as because I want。So I claim that actually can't happen。

 by one of our standing assumptions， we had an assumption that the graph。

 the original graph has a perfect matching。Okay。By Hall's theorem or sort of obviously。

 whenever you have a perfect matching for any subset on the left。

 the number of neighbors on the right has to be at least as large。And so the only thing here。

Just remember when I drew this picture， it was only the tight edges。

 so that's why it wasn't a contradiction to see a picture like this because we're only looking at the tight edges。

 but if you're telling me that actually there aren't any other edges either。Out of us。

Then all of a sudden， have' exhibited a constricted set。

 All of the neighbors of the left hand side belong to this right hand side， as we observed。

The right hand side is strictly smaller than the left hand side。

 that's a violation of Hall's condition， which contradicts our assumption that the graph has a perfect matching。

Okay， so the upshot is this case can't happen。Okay。Good。So let me sort of do an example。

And I I'll have to stop after the example and pick up again on Thursday。

So the claim is both of these are progress， It's clear that when you have a good path that progress your're matching gets bigger that can only happen in times as we'll see new edges becoming tight that's also helpful you can't just have edges become tight forever without also doing some kind of path augmentation so just like in push relabel we showed that first of all we bounded the number of the labelbels then we said that you can't have a lot of saturating pushes unless you have a lot of relabels so they can't be that manyatururing pushes then we did the same trick with non-surating pushes。

 you can't have too many without having two relabels， it's going be the same thing here。

 you can't have too many of these price updates before you actually do before you find a good path。

So details on that Thursday and I'm also going to have to show you on Thursday why it is that one of the two cases always applies。

So that's where we'll start on Thursday。But just to tie it up to give you a。

Better intuition for what's going on。I just want to look at an example and think about。

 I want to stare at it and say which of good case number one or good number two。Applies。

 and then what happens when we update things？So suppose the original age costs are like so。

So how do we run this algorithm so we initialize with the empty matching？And we initialized well。

 our prices being equal to zero。So which edges， so the question is， are we in good case number one。

 where there's a good path are we in good case number two？Well， let me ask a preliminary question。

What are the tight edges right now， Remember， a good path has to comprise only tight edges。 Okay。

 So we're ignoring the other edges。 and we look for a path。 So what edges are tight。Nothing's tight。

 right， So everything has strictly positive reduced cost because the the reduced costs are equal to the。

Original cost at the moment， okay？So we're hoping then， so that means there's no good path。

So we're hoping that there's a good set， but again， sort of trivially， there is。So if I just think。

 for example。嗯。About taking this set S。So there's no tight edges。

 so the picture just looks like this one， except with only one vertex on the left and zero vertices on the right。

So here's where we do， the price update。So we jack up prices on the left as much as we can。

 what constrains it while we don't want any reduced cost to go negative。

So what are we going to replace this zero by？Yeah。So it is going to become three。

After our price update。Okay。Exactly。Okay。So now next iteration， which case are we in？

Do we have a good path？We do actually。 So now we have a tight edge， namely the edge from V1 to W1。

Or sorry， V1 to W2。So that's actually a good path。Okay， joins。It a path of tight edges。

 starts on the left ends on the right， it alternates trivially。

So we're going to augment empty matching with this。Okay。The visit our new matching it。All right。

Now what happens next？So do we have a good path in the next iteration？No， definitely not。

 we don't have any tight edges other than the match edged。So now you need to find a good set。

So what would be a candidate good sets？Well。So for example。You could take this。Combined with this。

Okay。So remember NFS is who you can reach from tight edges from the left hand side to the right from tight edges。

 this is the only tight edge， so this is who you reach on the right hand side。So now again。

 we can do a price update。So we increase prices on the left by Dlta。

 we decrease prices on the right by Dlta until some edge cost reduced cost gets zeroed out。

So what are we going to take Delta in this example？对吧。Yeah， it looks like two to me。 is that true？

Actually， this is fine， that's going to go back down again。CanCan you jack it up by5？

Not so sure about that。Yeah， I think you can jack it up by four。So as we increase Dlta。

This is the edge from V1 to W1， whose reduced cost is dropping。Because this price is going up。

And this price is staying the same。Okay。So once this gets to seven。This edge becomes tight。

At that point， this is a four。And what is this？inus4。O。And as we said。

 we don't care if prices go negative， that's no big deal。So let's see。

 so we have some more tight edges。So this is now a tight edge。U。

Are there any good paths at this point？No， so we need to do another dual update。

 There'll be a couple more amount of time。 So just skip to the chase。 Eventually。

 you'll get a tight edge so that this becomes。Let's see。 So what's going to happen。 So Min cost，7，2。

 I see， actually eventually this is going to be able to come。

So five and three is going to be the main cost perfect match。

So eventually you're going to have enough dual updates that this edge becomes tight。

 and then you can augment the matching by that and you get the min cost matching with total weight8。

So there any questions about that？Yeah。いぱいれてで、すね。ャフインド大事。An arbitrary that's going to be fine。

 so I'm going to give you so what I'm going to do next time is I'm actually going to give you a subroutine and I don want you to be scared of it it's like basically breath first search with a twist。

 so I'll show you how breath first search with a twist is guaranteed to either find a good path or exhibit a good set。

And then once you have either one， you do the corresponding update。

So that's what we're set on Thursday。