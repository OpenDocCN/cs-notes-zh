# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p19 -19-(Lecture 19_  Online Algorithms and Random Permutations).zh_en -BV1yqVzzqEQ5_p19-

So we've covered tons and tons of different ideas and tons of analysis frameworks over the last nine weeks。

 so for these last two lectures I want to give you a couple applications which brings multiple of these ideas together and along the way。

 I'll also be able to introduce you to a couple of the problem domains that we haven't really discussed yet。

 so'll kill a couple birds with one stone。So the plan for both of these lectures is to return to online algorithms。

 So that's something we did discuss way back at the beginning of the course。

 We discussed a single problem， which is a paradigmatic online problem。 The paging problem。

 we talked about that quite a bit。 But online algorithms are useful for reasoning about lots of other kinds of problems as well。

 So today we'll be discussing online algorithms for network design problems。

 So these will be graph optimization problems on Wednesday we'll talk about online decision making problems。

 Another both of these areas have tons and tons of work in them。

 and I'm going to showcase some recent results which make use of the ideas we've talked about in the course。

Okay， let me tell you about the Stener tree problem， specifically the online version。

 I hope at least a few of you have seen the offline version at some point in the past。

 although I won't be assuming that。 So here's what you know up front。So you're given a graph。

You know， a road network or something like that。 You're given edge costs。

 So these could be lengths of roads or something like that。So these are non negative。

And you also know a root vertex R。Okay， so this is some starting point。

What you don't know is what are called terminals or demands。So arriving online。

And so remember what this means， okay， so on online algorithms that means there's some input。

 but you don't get it all at the beginning， you're going to be given it piecemeal one at a time。

 and you have to make some irrevocable decision each time you get a new piece of the input。

So the input here is going to be a sequence of vertices and your responsibility is to keep all of these vertices connected to each other and to this root vertex R。

So arriving online are terminals。T1。T 2。Actually I I'm going to call these S。To avoid some notation。

 confusion， S1。S2 and let's say t is the number of termins。ST。So that's what you don't know， right。

 so anything could show up。And like I said， what you have to do。

You have to maintain a connected subgraph。 And so without loss of generality here。

 it's going to be a tree。 So a tree that spans the root vertex are and all the terminals you've seen thus far。

Okay。So just to make sure this was really crystal clear。

 let me relate it to a problem that definitely all of you should have seen before。

 which is the minimum spanning tree problem。So the two differences between the minimum span tree problem。

 Okay， so the first is the difference between the minimum spanning tree problem and the minimum Steer tree problem in the spanning tree problem。

 you need to build a tree that spans every single vertex of the graph。

And you want to do it as cheaply as possible。The st tree problem says， well， look。

 maybe you don't actually have to span every single vertex in the graph。

 There's just some sub subset。 what I'm here calling the terminals and your tree only has to span that subset of terminals。

 You can make use of extra vertices if it makes your tree cheaper as intermediate stops。

The second difference to minimum spanning tree problem is the online nature。 Okay， so now。

 in addition to not having to connect everything， you only have to connect these terminals。

 and I'm only going to give you the terminals piecemeal one at a time。 Okay。

 and you don't know what the future is going to bring。So you're given S1。

 you have to connect it to R by some path。 natural one's the shortest path。

 but you can do something else if you wanted。 Then S 2 shows up。

 you need to connect that to what you've already done and so forth。So that's the online st problem。

 And you'd like your tree to be as cheap as possible。 I mean。

 ideally as close to as possible as the cheapest tree that just spans R in all of the terminals S1 through S T。

Okay。So is the problem definition clear？O。Alright， so the minimum span tree problem is polynomial time sovable。

 as you all know， there's lots of greedy algorithms for it。 Even offline。

 the standard tree problem is NP hard。 So for polynomial time algorithms。

 you're not going to solve it exactly， but you can get constant factor approximations。

 Here we're dealing with the online situation。 Our algorithms will also happen to be polynomial time。

 So we're certainly not going to solve it exactly。 in fact， in general， as we'll see。

 we won't even be able to do as well as offline algorithms we won't even in the worst case。

 be able to get within a constant factor。 So we're going to talk about next。So as usual。

 before we look at alternatives to worst case analysis。

 let's sort of calibrate things by just saying， what does worst case analysis give us， and in fact。

 it works pretty well for online Steinnert works much better than for the paging problem。All right。

 so the worst case model。Was studied quite thoroughly by Amo S and Wman。This is quite a while ago。

 25 years ago or so。And so this just means literally this sequence could be anything。 Okay。

 the sequence of terminals。 So you have no idea what it is。

 And we're going to look at the performance of an online algorithm by the worst case ratio between the cost of the tree that it builds and the minimum possible cost tree in hindsight。

 given the whole sequence。And so as usual。Before we talk about positive results。

 let's just try to understand what could we expect。 be， what could we be hoping for。 Like I said， if。

 if you're familiar with the approximation algorithms。

 polymthal approximation algorithms for the problem。

 maybe you'd be hoping for like a really good constant factor approximation because that can be done offline。

But with the online version。In the worst case， there are some nasty examples。

Let me show you a very nice construction based on the so-called diamond graphs。 Okay。

 so what'm gonna to do is I'm going to exhibit an infinite family of graphs so that if I choose one a big one of these graphs。

 I can figure out a way。 So you show me an online algorithm。

 allll figure out a way to define a sequence of terminals so that your online algorithm does poorly。

 So let me start by describing the graphs。 Then I'll describe what the terminals are going to be。😊。

So here are the diamond graphs， so G1 is just a diamond。And then in each step。

 so it's an inductive construction， you put in a diamond for copies of the previous member of the family。

 so for G2， you make a diamond of diamonds。Okay， so that's a G2。And in general， GK。

Has four copies of Gk minus-1。And the root is always the vertex way on the right。Okay。

So those are the diamond graphs。So the number of vertices and the number of edges are both scaling exponentially in K。

 There's ballpark。 In fact， there's exactly four to the K edges in the k graph。

 And there's roughly four to the K vertices in that as well， okay。So I said。

 you know what's the definition of problem， there's a graph I told you what that is。

 I need to tell you what the edge costs are， so all the edge costs are one。All edge costs are one。

 I told you what the root is。So why are these bad graphs？For online statutory algorithms。Well。

 fix an algorithm and for simplicity， suppose it's a deterministic online algorithm for the diary problem okay。

On the homework， I'll ask you to also handle the randomized online algorithm case。

 which is basically the same。So the upshot is， is that the。

Terminals that are chosen at the end of the day are all going to wind up on a line。 Okay。

 where what do I mean by a line。 So here， that's a line， That's a line。 I mean。

 a single path going from left to right through the diamond。 Okay， that's what I mean by a line。

 So again， at the end of the day， the adversary is going to ensure that all of the terminals lie on a single line。

So the claim。Can define the terminals， and again， the definition will be a function of the online algorithm that you choose。

 so for each algorithm， it's Murphy's law， I'll pick the worst case sequence for that algorithm。

So that so first of all。All on a line。And that means we know that optt is cheap。Okay。

 so every line here has length， total length 2。 Every line here has total length4。Here it's 6。 No。

 sorry I hear it's what is it。 So that's， I meant G3， right， So in G3。It it would be eight and so on。

Okay。So up， not too big。On the other hand。What I'm going to do is adaptively reveal these terminals as a function of the decisions that your online algorithm makes。

 so I'm just going to sketch this by picture to give you the intuition。

 given the intuition it shouldn't be hard to work out and that's I'm going to ask you to do in the homework。

So I just imagine we're dealing with G2 for the moment。

 I think you'll see how the recursion will work。 So the first thing。I'm going to do。Is。

I'm going to say， look。Here's the first。Zral。Okay。And so now the online algorithm has to pick a line。

 Okay， if it wants， it can build still more stuff。 But let's say it does the obvious thing and picks one of these。

 one of these shortest paths to connect them。So you know， maybe it picks。This one。Okay。Well。

 so now is the adversary， the super annoying thing to do next。Is to make this the next request。Okay。

 so it's on the line different than the one that you chose。

And so then the obvious thing to do is connect it to the root， say that way。

 you could also connect it up there， but let's say you connect it down there and I'm also going to make that a request so again。

 the part of the first half of the line that you didn't take and so now you you could connect it either here。

 really let's say you connect it there。And in general。

 you can recurse okay so you keep making the algorithm pick lines or parts of lines。

 you make it make this binary decision， does it go up or does it go down。

 and then whichever direction it doesn't take， you put the next batch of requests on the other sides of the lines I would have thought that that your second choice of vertex for this G2 should be the middle of the bottom half of the graph。

Oh yeah。 So I guess I skipped ahead and iteration is what you're saying。Yeah， you're right。嗯。I mean。

 eventually you're going to do all of these things。But yes， you're right， I skipped the head。

So as was said， the next thing to do would be to pick one of these midpoints and again。

 the algorithm has to make decisionciion either direction。

 and now you sort of recurse to the next batch of midpoints。Which will look like that and so on。

You can't think any mid points on the top though， because then your choices would not be in the line。

URight， right。Okay， then I'm confused about your first comment。So what I propose。

LikeE we always just， if you use the top， then we go to the middle of the bottom。

 if you went to the bottom， we go to the middle of the top。

 recur and then we recurse on the little subpieces。

So let's say we choose in middle middle the bottom。And then he picked some that。

Choose the other of the two paths you could have just。Okay， so right。

And we only get to choose two to a kid。All right，Right， so we want it to be on a line。

 so now we're going to do this。And so now， it chooses。

And so now we need to pick the worst of these two， so we get to pick this one， all right？

And here we don't care， we can pick either one， right？Okay。Good， yeah， so in some sense。

 the first request is this one。 The next request is this one。

Then you get a batch of two requests and now going down the recursion。

 the number of requests sort of per batch is going to double every time。So that's right。

 so the point is you want to keep all the requests on a line so that the ops stays cheap。

 but then you also sort of in each batch， there's going to be a logarithmic number of batches。

 one batch basically for each value of k， you want basically the algorithm to pay commensurate to what the optimum pays just in one shot。

Okay， that's sort of the intuition。So。Repeatedly unveiled successive midpoints is we I'll say。Okay。

いや。喂思。So for the first one， it goes distance。系。To to the K。 let's say like the the1。

1 line has distance n。 Okay， so for the first request， it goes distance n。

 but doesn't it then always like half the distance。 now， so that's why you want the number。

 you want the number of requests in each batch to also be doubling each time。 right， So you。

 so you're right for the first two， right， So this one has costs， you know， say， let's call it one。

 This one has cost one half。 like you say， Okay， so that looks like trouble。

 But then we have these two requests， two requests at length one quarter。 So that's another half。

Okay， so you're right Yeah， it's almost tempting for the lecture to actually skip this outer most steps so you don't get confused by this point。

 But like there is this initial battery you go from one to one half。 then it'll always be one half。

1 half， one half， one half for a logarithmic number of stages。 Now。

 the number of requests in each of those stages is going to be doubling。

 So the length per requests is having。 But again， because you can sort of recurse。 So basically。

 you know。You've made a binary decision many， many times once you've blown up this construction to each K and to get the lower bound to work。

 you really have to punish the online algorithm for every single binary decision it ever makes。

And so that results in the number of requests doubling。Okay。

 so that was just that was just basically meant as sort of a cartoonish hint to carry out the details yourself at the end of the day once you get。

You you get a lower bound of omega log n。Or n is the number of vertices。

 And so the number of vertices N here is going to be exponential in K。 Okay。

 so you take K to be whatever。 And then N is basically like 4 to the K。

 and you're going get a lower bound of K。 I you log in。So that's the line in the sand。There are。

's the next， that's the next points。And。Here again。

 because I want to focus on alternatives to the worst case model， not the worst case model itself。

 I'll leave the proof， which is very nice to the homework。In fact， the greedy algorithm。

So what's the greedy algorithm。 Well， it's what youd think right So the first vert shows up S1 shows up。

 you connect it to R via a shortest path。 S2 shows up。 you look at everything you've built so far。

 you connect S2 to everything you've built so far along the shortest path and so on。

 So that's the greedy algorithm。 It's probably the obvious one to try。 And in fact。

 that gives you a matching upper bound。So a greedy algorithm。Yields a log in approximation。

And as far as the proof， for those of you who have seen the proof that the MST heuristic is a two approximation。

 for say the TSP problem or the Steer tree problem， it has a very similar flavor。

 the fact that you can't control the ordering in which the points show up is the reason why you get a login instead of a two but the ideas are basically the same Okay so the sort of standard ideas in this context。

 so I'm going to put them on the homework。Okay。Okay， good。 So that's that's pretty much the story。

 the basic story with the worst case world。 you can't get constant， which sort of a bummer。

 but you can get logarithmic in the vertex size。This means we're exponentially worse right than what？

Then the opt， then opt。Well， we're sort of arbitrarily worse than opt。

 if you take N going to infinity up to。Well， I mean， log is。

 there's no function that give there's no function of a constant， which will give you log。

 So we're arbitrarily worse than not。 So it's growing within n。 In fact， if you like the upper bound。

 the upper bound will ask you to prove is even log T。Okay， so the number of requests。

 it actually doesn't really matter how big the graph is， it just matters how many requests you have。

 You'll notice in the lower bound or if you work through the lower bound。

 you'll notice the number of requests equals the number of vertices basically。

 So that's why doesn't that's why you have this combination。So it's sort of a bummer。

 We don't get that close to optimal。 On the other hand。

 is's nowhere near as dire as it was with paging。 Remember paging， we really had no choice。

 but to turned alternatives to worst case analysis， right because， you know。

 we were getting like a page fault every single time step， no matter how big the cash was。 I mean。

 we're getting just like totally absurd stuff。This， you know， I wouldn't call this totally absurd。

 I would agree it's pessimistic。But， you know， actually， in。

 it seems pretty reasonable that you couldn't do much other than the greedy algorithm。

 if you had absolutely no information about the input。 you might think about， okay。

 what else could you try to do， The other thing you could try to do and actually。

 we'll see this in a different algorithm in a second。

 you might try to pay a little bit more now So build some extra stuff somehow to make to make connecting subsequent vertices cheaper。

But with sort of no feel， basically for a worst case sequence coming up。

 it's just sort of unclear what direction quote unquote。

 to possibly build in that's going to help you more than it hurts you overall。

So it seems sort of intuitive， I think it seems reasonable that first of all。

 you wouldn't get a constant knowing nothing， but second of all you get something nontrivial and optimal amongst online algorithms from the greedy algorithm。

 So you know this is not you know it's a mixed report card， it's not really that bad report card。

But it's certainly still very well motivated。To think about sort of a natural situation where you had some more information about what the sequence was likely to be。

And that's what I want to do next。And so understood both in， know， so as usual。

 there's sort of two angles to this。 one angle is just we'd like to have more meaningful performance guarantees。

 We don't really want to be arbitrarily far off of the optimal solution。

 but also we're sort of wondering， you know， would we design our algorithms differently if we had more information would we actually approach the problem in a new way and both of those answers will turn out to be yes。

 okay。All right， so what's the new model， the non worst case model， Well。

 this will be reminiscent of the last couple lectures。

So the first assumption is that now instead of these terminals。

 these Sis being a worst case sequence。They're going to be drawn from a distribution。Okay。

 I going to call pi。 Okay， So pi is a distribution on the vertices of the graph。 So again。

 we know the graph for sure。 We know the edge costs for sure。 We know the root are。

 and there exists this distribution over the vertices pi。These are I I D。Okay。And now， you know。

 that's a much stronger assumption， of course， than a worst case sequence。

 So we'd certainly like to do better。 And what we'd like is we'd like to have an algorithm。

With expected cost。At most， the expected cost of opt。Okay。So even with the graph edge cost fixed。

 since the terminals， since these are random， the cost of the optimal solution is also random。

 So the natural benchmark is the expected cost of the minimum cost of di。

 Given the realization of the terminals。 And we'd like our algorithm to do at least almost as well。

 It should be an O of one in here。Okay， so a constant factor。

 Okay we're going have to lose something， obviously， but we don't want to lose more than a constant。

And so if we can do that， we're doing much better than the worst case regime， obviously， okay。

So stronger hypothesis， stronger conclusion， that's a we'reafter。Okay。So more lines in the sand。

 So we need more assumptions than this to be able to prove anything， to be able to do anything。

What's a couple things， so first of all。You might ask， right。

 So remember there's at least two reasons why you might want to change the analysis framework。

 One is maybe you believe that， you know， this greedy algorithm is much better than this pessimistic logger in the guess of it。

 Okay， and you just want a different data model to explain why it has better performance。

 That's what we do with like smooth analysis and simplex and local search。 And actually。

 so that's not what's going on here。 Okay， so the first lower bound indicates that that's not what we're trying to do。

So greedy。The claim。Is still not good enough。Okay。Now， notice the greedy algorithm， know。

 its description is totally agnostic to pi。 it's just an algorithm。 And you know。

 any change when you when you look at the greedy algorithm is only going to be in the analysis。

 It's not the algorithm。 But still， you know， you look at those diamond graphs， you know。

 and it's not you know。You can think about it， but at first blush。

 it's not sort of clear that those have anything to do with these IID samples from some distribution pi。

And but this is not true。 and this is a simple lower bound， which you'll put on the homework。

 It's just a bunch of points on the line。 Gredy can still be off by a log factor。

 even when points are drawn ID from a distribution。

 and I can even tell you the distribution because again。

 the algorithm doesn't depend on the distribution，So what I'm trying to say is if if we're going to be able to accomplish this goal in this new model。

 it's going to be via a new algorithm， Okay you know， which probably is a feature。

 It's sort of telling us if we had more data about the problem。

 how would we exploit it in an algorithm。 That's kind of what we're driving toward。Okay， secondly。

This goal of getting within a constant factor of optimal。Is impossible。

If this distribution is completely unknown。Okay， so in other words。

 if I force you to write down an online algorithm first， Okay with no dependence on pi。

 and then I get to exhibit a pi， then I can break your algorithm。

 Okay this is a harder job for me as an adversary than it was before because it used to be。

 I could just exhibit my favorite sequence。 You actually have to exhibit a distribution and the sequence is gonna be drawn I from this distribution。

 but still as the adversary， I can solve this harder problem。

 I can still break your online algorithm if it has no dependence at all on pi。 Morly。

 the reasons that's true。 is a little bit annoying to actually make precise。

 So I'm not gonna put on the homework。 But basically， if you don't know anything about pi。

 you can kind of simulate the instances on those diamond graphs。

 basically I'll just make the probabilities of different points really different。 So that basically。

 you know what used to be the first point in the bad sequence。

 will just be kind of the first point and appear over and over and over and over and over again。

 So you know， if you see duplicates of a point， it doesn't change the optimum。

 It doesn't change your stino tree。 if you have duplicates of a point。LikeOkay， cool。

 I'll just keep my tree the same way it is， so it's like it never happened。Then， you know。

 there'll be this much smaller probability of the next two midpoints。 At some point。

 one of those will show up。 Each one is equally likely。 Okay。

 so there's a 50% chance it's going to be the opposite of where you built your initial path and so on。

So if you know nothing about pie， can more or less simulate the worst case instance。Yeah。

ButWhat if you were just forced to randomize the order。

 like would that be enough that's the second part of the lecture。So it turns out the answer is no。

 but that's the second part of the lecture for similar reasons。Okay。

So it turns out it's easier to think about unknown I distribution。

 So I'm starting with an easier model。Okay， so again， so we said， okay， let's make our lives easier。

 Let's assume terminals are drawn I D from distribution pi。 We know that if we want to do better。

 we need a different algorithm， and we know that if we want to do better that new algorithm better actually have some knowledge of pi。

Okay，That's the point of mentioning these two lower bounds，Okay， so。Now。

 we have to say what it means。 And we face the same problem in the last two lectures。

 The lecture on self improvingrov sorting algorithms and the lecture on pricing with an unknown distribution。

 we need to sort of say the algorithm has at least partial knowledge of the distribution pie。

 And the exact model we're gonna use is exactly the same models in the last two lectures。 Okay。

 where you have some samples from Pi。So to make my life easier。I'm going to assume that。

 you know that the algorithm knows the number T of terminals that are going to show up。Okay。

Assume T is no。So you don't know what these terminals S 1 through S T are going to be。

There's 100 of them maybe， but you know there's going to be 100 terminals。

This is probably not an assumption you want and a solution to this problem。

 And there are extensions of these results that remove this assumption。

 But the algorithm gets more complicated and the constants get worse。 Okay。

 so I'm not planning on covering them， but it can be done。 I want you to know that it can be done。

So the main points come through much more clearly if we just assume that you know roughly at least how many terminals T you're going to show up。

Where do I use this assumption， It's more like， okay， so。The assumption is actually that。

The number of samples that you're given is equal， or you know， within a constant factor， say。

 of the number of terminals that are going to show up。 Okay So' that's the important assumption。

So you're given tea。I these samples。Q won。Of to Q T。From Pai。Okay。

So in the same way we talked about sorting algorithms that only knew the distribution through some number of training samples。

 we talked about pricing functions， that only knew the distribution through some number of bids from previous auctions。

 here we're talking about network design algorithms that only know the distribution on terminals through T samples from the past。

So again， the algorithm doesn't know pi per se， but it does know Q1 through QT。

 which are drawn from pi。Okay。対性。他。You， one， one junk terminal， which is just drawn a million times。

So this is where we're using the coupling between these two assumptions， right。

 So if all of the mass was just on a single vertex， so that that's all you saw in the samples。

 that would also overwhelmingly be the only thing youd actually see is the real input。Okay。

 and so then your algorithm would just build the shortest path to it， and that'd be fine。

So for the lower bound so it's a good comment so when was the discussion here that I was talking about where I said。

 if you just have an unknown ID distribution， the problem is you can embed the worst case instance by mixing out the probabilities。

 there I need the sequence， so T if you will， to be super， super long， in fact。

 you know much bigger than n， for example。And so here I'm really sort of so what's actually important。

 in fact， I maybe you know said this the wrong way。

 It's not so important that the algorithm knows T per se。

 It's just important that the number of samples is commensurate to the number of actual points that are going to show up。

 So that'll really be the technical assumption for the lecture。

And that was violated in the discussion around this point around the second lower bound。

 like T over That would be fine。 I'm probably going to put that on the homework， too。

 So if they're ballpar each other， it's fine。But if you have like three samples and then you have 100 points that show up。

 not so fun。But it's not superbi。 Its sort of degrades in the way one would hope。

And the proof that I'll give you will just basically show that if you。

 if you stare at it the right way。O。Now， all right， so any， any technical questions。

 So have a brief discussion about interpretation。 But， is it clear what the model is going to be。

Okay， so online stuttry， not only does this distribution exist， pi exist， it's assumption number one。

 but also the algorithm that's partial information in the form of samples or the number of samples is commensurate with the number of terminals that are going to show up。

 and this is our goal， constant factor robots。Okay， so why why this model。

 I actually think there's a couple reasons why you might care about this model。

 One was the same one I was emphasizing in our last couple lectures， which is you in many situations。

 you might have partial but only very coarse information about a distribution and often is literally in the form of past instances。

 like in auctions， you have bid data from last week and maybe it was a thin market。

 a rare keyword that people were searching on you don't have a lot of data。

 but you at least have six times that a comparable auction was run over the past week。

So that's the first reason。 That's sort of the little interpretation。

 Let me give you a second interpretation， which wasn't relevant last time。

 which was even suppose you knew Pi completely。Okay， and so notice here。

 it pis just a distribution on the vertices。 Okay， so that would just be like， you know。

 there's 1000 vertices would be 1000 numbers， not totally ridiculous， right。

 So you have this like percentages for each of the vertices in this network of how frequently it's going to show up as a demand point。

O， so if you know pi fully， again， you really believe in it。 in principle。

 you can just run an optimal algorithm。What do I mean， Well。

 every single online algorithm has some expected cost with respect to this distribution。

 right So there's a like finite number of you know， of qualitatively different online algorithms。

 Each one has some expected cost。 one of them has the smallest expected cost。

 And you can just run that Okay， And in principle， there's no reason not to do that。 You don't need。

 I mean， why compare with some ratio。 Like， Who cares。 like this one algorithm is just the best。

 if you believe in this distribution。The issue is in general。

 that algorithm is going to be complicated。Okay， so if you think about what this algorithm is going to look like。

 it's basically going to be a massive lookup table。 Okay， It says， oh， well。

 given the realization of the first 10 terminals， here's the edges you should build next。 Okay。

 and then you flip coins and you get the 11 terminal， It says， okay， given that。

 you look up in this big table， Here's what you should do next and so on。 Well， so， you know。

 it's it's conjectured in this case that there is no simpler algorithm。Okay， so in particular。

 I would conjecture that you can't have。An exact optimal algorithm that uses space that's not scaling exponentially in the number of terminals T。

 The formal way you'd prove that is you'd prove the complexity of computing and optimal strategy is P space complete。

 That's the complexity class， which which naturally pops up for these optimal kind of policy type computations。

 I don't think that's actually been studied for these problems。

 but often for these kinds of problems。 It's P space complete。

To compute what the best thing to do is。 So again， it exists。 But just complexity gets in the way。

 in this case， even complexity of describing the thing gets in the way of actually implementing it。

 So then you say， look， okay， I have my00 probability numbers。

 but I can't compute this optimal thing。 I there a simple heuristic。

 which allows me to compute a pretty good policy。 Okay And so this says yes， So this says， yeah。

 just sample， you have the distribution。 You can certainly sample from it 100 times or whatever。

 I I D， No problem。 Now just run the following algorithm。 Okay。

 and then the theorem' is going to say that's going to do almost as well as if you did， you know。

 use the exponential size lookup table and do the optimal thing。So that's interpretation number two。

 So one is just you don't have the information， Two is you have it。

 but it's too cumbersome to exploit completely。 So this is a way to use it approximately。O。Great。

Then let me show you how to use it。And there's actually。It's quite a nice simple algorithm。

And remember， we have said that， you know， when we're talking about greedy， and maybe it makes sense。

That greedy is worst case optimal。 We said， you know。

 the other thing you might try to do is build some extra stuff。

So that it gets cheaper to compute other people， but like where do you build it。

 given that you know nothing about the sequence， So for this algorithm。

 it's going to very elegantly use the samples to sort of figure out in which directions to build extra infrastructure is kind of early investment for later payoff。

So here's the augmented greedy algorithm。I forgot to say this ID D model is due to gar at all。From 0。

8。I think it's a little amazing that this wasn't studied earlier。

 given how fundamental the standard true problem is。有。The distributions ID。

 why do we say that we have this exponential， I don't quite understand that yet。

 why you say there's an exponential number of possibilities because。I feel like the don't we。

 don't we know the problem， if we knew the the distribution， couldn't we just simply compute。

The probability that a certain vertex is become is going to be the next terminal or going to be terminal。

 Well， in fact， we， we know that， especially， as you say，ca this ID。

 The issue is that the optimal action is going to be history dependent。

 So after you've seen 10 different vertices， you might wantna do something different next for each of the possible end of the 10th realizations of the first 10 vertices。

Yeah， so you， if you're only going to see you know one， you know， if T is tiny。

 if T is like three or something， you can get away with this， but if T is big。

 then you can't get away with this。And you know， as as was pointed out， it's not。

 you know in my lecture， I haven't made precise that you。

 that you can't do something better than this naive lookup table。

 But certainly for a lot of problems of this flavor， you can't。 if pe is not equal to pe space。

 And thats I suspect that's true for these as well。Although as far as I mean。

 there may also be a nice open problem to actually prove that。So certainly the general issue here of。

 of， you know， So I guess what I'm trying to point out is there's two different types of bottlenecks and。

know what we're talking about this lecture is potentially relevant for either of the types of bottlenecks。

 One is an informational bottleneck， where you really just have a course understanding of the distribution。

 The other is a computational bottleneck where you have all the information you want。

 but you don't have the computational resources to make optimal use of it。

 And this is a potential tool in your toolbox， whichever of those two bottlenecks may be the constraining one in your application。

 That's really the。You know the way to interpret this。Okay。Sure， what's the algorithm？

So there's gonna be two stages。 The first stage we're just going to pre process。 Okay。

 this is work we're going to do before any of the real terminals show up。

 So remember that the Q Is are the samples。 Okay， so we know that in advance。

 And then the Ss are the real deal。 Get are the actual terminals that we have to span。

So here's what we do just with the QIs。So basically， what we do is we， even though we don't have to。

 these are just samples like that we dug up out of our data logs。 we're going to build。

A tree spanning the root R and all of the samples。 Okay， We don't have to。

 This is just our investment in infrastructure up front， okay。So use。

 and we're going to do it in a particular way。And I'll say what I mean by this。

 We're going to use Prim's MST algorithm。To construct。A tree on R plus capital Q。

 so we' meeting the samples。And remember， we're assuming that there are T samples。

So primm is the one。 so Crsco is the one where you sort of sort and do one pass。

 Prim is the one that's sort of like dikestra where you grow a tree like a mold from a starting point。

So what do I mean by this exactly， Here's what I mean。So we grow the tree from the root R。

Capital T is the tree so far。So we're going to slowly connect up the sample points。

 we're going to build the tree iteration by iteration。

 So which sample point do we want to sort of bring into the fold next Well you remember Prims algorithm。

 you always look for the one that's closest to your tree so far。

 so's going to be the same thing here。 So while there's samples that we haven't yet brought into our tree。

We pick the one。Cllosest。So S is going to denote what we're spanning so far to the terminals that we're spanning so far。

Cllosest。To a point of S。Add to our tree so far。Shortest path。Between QI。S。

And then we move QI from Q。To S。Okay， so we start with R。Remember， again。

 this is basically an offline problem here， right we have all of these Q1 through QT upfronts okay。

Of all of those tea， we look at which of them is closest to the roots。 Maybe it's Q3。

And we add a shortest path between them。And there might be intermediate vertices on there there。

 which are not terminals。Then we say okay， which one of the guys who want Q3 is closest to either R or Q3。

 So maybe Q7 isn't very close to R。But now that we've connected Q3。

 Q7 and Q3 are pretty close to each other。 So Q7 is the next one that goes added in。

So now we repeat maybe Q10 over here， maybe that's the one that's closest to any of these three。

 so we connect that say to R and so on， okay we keep repeating。

Do we just keep constructing people by shorttz paths？

So that's what I mean by applied Pris algorithm to construct a Steer tree on R and the sample points Q1 through QK。

Right right。So。Now， what I need to prove to you is that this investment is going to pay off somehow。

And again， keep in mind that if you just ran greedy。

 if you ignored the samples and you just ran greedy on S1 through S T， you do poorly in general。

 okay， you might be off by a log factor。Do we know what kind of what kind of？Yes， we do。

 It's a factor， too。 Yeah， and some of you will have seen that。 Okay。

 so I'm basically going to pump that to homework because one， it's simple。 and2。

 a lot of people have probably seen it。And that's right。 And that's a very important point。

 So and actually， I mean， you might be thinking， you know。

Why did I specify the spanning tree algorithm， Like the cost is just the cost of the spanning tree。

 Who cares which algorithm you use to get the spanning tree。

 But it turns out to understand the analysis is's useful if you think of it being done with Prims algorithm。

 Okay， you'd be right to make that comment。 Why not use crustesco。 you could。 Okay。

 because you get exactly the same output。 Any theorem that I prove with a prim implementation would hold with the cres implementation。

 But this is the way I want you to think about it that will make the analysis as transparent as possible。

 believeve it or not。Okay， so now， basically， once the real points start showing up， S1 through S。

 you just continue running this algorithm。You already got out a tree， spanning R and Q1 through Q T。

 and you just keep running it。O。So on arrival。Of S I。Add to tea。As shortest path。Between S and。And S。

And then， add。S I to S。O。So maybe this was how the tree from the preprocessing phase finished。

 and now S1 comes up here， maybe it's closest to Q3， you know maybe then it's sort of S2 is there。

S3 is here and so forth。It seems like you could do slightly better by like running the same algorithm。

 but only building the pieces of this preprocessing tree like as you need them。

 So in the graph you drew， for example， you don't meet that last Q value。Well， you don't need it yet。

But maybe you stop there。 like you never would have needed to build that。 Sure， but maybe you don't。

 right， So it's a little。 build like parts of the tree in the pre processing step only as you read it there。

 Let's see。 Let me think about this。 So yes， yes， that's right。 So you're saying basically。

 the red tree is only in your mind。 right。And then basically you do all the blue editions。Okay。

 still find the closest point to the red tree， exactly。

 And you're saying you only actually build these once it's used by some blue point。 Yes， I agree。

So you can lazily defer the red constructions until they're actually used by one of the actual points。

 You definitely want to have that full red tree in your head， though。

Should we accomplish the same by going through。At the end and just cutting any of the red links that we can use。

Yeah， so So I should have been more clear about this in the online model， what makes it online。

 So there what are the irrevocable decisions， any edges that you literally build。

 you can't undo later， right， So Elliot sort of pointing out that since this first phase is basically。

Kind of fictitious。 We can kind of tentatively build it in our mind， know。

 like put down a reservation， basically， right， but then cancel the reservation at the end if it was would have never used。

So yeahep， I agree。 So in other words， the approximation guarantee I'm going to approve。 So actually。

 so to be more precise。Or even just more generally。

 I'm gonna to prove an approximation algorithm for this algorithm。

 which is subop evidently suboptimal in multiple ways。 That's an excellent point。 That's one of them。

 Another one is， you know， there's bettersteinertry approximation algorithms than the Mt heuristic。

 So you could swap in a better one it would be better Again。

 I want you to think about this actually particularly implementation。

 the Mt heuristic to just understand the first version of the proof。 Also， if you think about it。

 there's no reason to keep connecting people by shortest paths only to the Qs and the previous sis and R。

 right if you know in one of the earlier shortest paths。

 you span a bunch of intermediate vertices as well。 and those are closer to this new terminal S1。

 go ahead and go straight to these intermediate terminals。

 Why bother going to either either the endpoints that are terminals。

 So that's yet another sense and this is a suboptimal algorithm。

 I obviously the approximation ratio we prove for this will carry over to all of those optimizations of this algorithm。

 I don't think you can prove a better factor for a lot of those optimizations。

 You can prove a better。If you swap up in a better standard approximation algorithm。

 but I'm just keeping it the easiest one to analyze。Yep。Good。Okay， any other questions？

 Is the algorithm clear。So that's it， and this works actually。Its pretty nice。 So theorem。

This is a four approximation。Meaning that the expected cost incurred by this algorithms is most four times the expected cost of the minimum cost Steer tree on T terminals drawn I I D from pi。

 no matter what pi is。 Okay， so it's an arbitrary distribution pi。

If you substituted the state of the art Steiner treee algorithm in step one。

 this would come down to something like 3。2。A little bit more。Alright， and intuitively， you know， I。

 I'm not claiming you would literally implement this algorithm。 but I mean， on a conceptual level。

 I do feel like it's giving some guidance about， you know， how to approach this problem of， know。

 if you wanted to build some extra infrastructure that would make your life easier later。

 how do you do it。 This shows if you just use some random samples from the distribution that already kind of naturally forces you into the parts of the。

 of the graph where the demand is likely to be high。So that sort of happens quite naturally。

All right， it a proof。 want to say a little bit about it。So there's two steps。

And step 1 is sort of standard。 So I'm going defer that to the homework。 Step 2 is not so standard。

 And I' cover， I'll cover that completely。So see homework number 10， but some of you。

 if you've taken CS261， you've probably literally already seen or done this exact same proof。

So the first claim is that the cost incurred by the algorithm。Is it most two times？

We expect the cost of opt。Okay， the expectations here you know。

 over the random realizations of both the samples， I guess actually here it's just the samples。

 right， So in step1， we only work with Q1 through Q T。Okay， so opt on what。 So I should say opt。呃。

Yeah， that's fine。So the left hand side here， the expectation is over Q1 through Q T。

 the samples that are given to the algorithm because its cost in step one depends only on its samples。

s just whatever it is。And on the right hand side， I'm looking at the expected cost given。

T IID samples from pi， the cost of a minimum Steiner tree spanning these T IID samples。Now。

 of course， since everything's being drawn from exactly the same distribution。

 the probability space here is the same as the probability space here。

 both of these are over two TIID samples from the distribution pi。

 the semantics is a little bit different here on the left hand side。

 it's these kind of fictitious points given to the augmented greedy algorithm here we're thinking more as actual demand points to be spanned by the standardary algorithm。

 but it is the same probability space on both sides。And so this is basically true with probability 1。

 Okay， So what I ask you to prove in the homework is just to say。

I'm basically going ask you to prove that the M T heuristics is two approximation for the standard shoe problem。

 So that's something you may know。 You don't know' it's worth going through once in your life。

So it's sort of one of these things where you sort of take the optimal solution and you double all the edges。

 and then you show that the doubled version of all the edges， you know。

 is basically a union of paths， which can be construed as some kind of spanning tree or some And then your algorithm is doing a minimum spanning tree computation。

 So it's at least as good as this doubled version of opts。 That's sort of the way that it goes。Okay。

 so step two。Is that the second step is no worse than the first。Okay。And， you know。

So the two steps you'll agree andly the theorem。All right， so why is this true。Well， let's think。

So the claim is going to be that， O， So this algorithmcro is a total of  two T iterations， right。

 So it has T iterations in the pre processing step。Where it builds up this initial tree。

 and then it has two more iterations when it gets the actual wool。Terminals， S1 through S。

And the claim is going to be that the expected cost of every single iteration in phase 2。

Is in most the expected cost of every single iteration in phase 1。So why is that true？

Let's start with phase one。So let's about， you know。

 so let's just think about like the seventh sample， you know， Q7。 it is what it is。 It's random。

 although the samples are random， but we just imagine the expected cost that we incur in the seventh。

 not sorry， not in the seventh iteration。 the expected cost we incur in phase1。

 when Q7 is connected to into the tree。Well， the only thing we're going to use。Is that， you， Q7。

When it's added to the tree so far。Whatever else happens， it gets added via a shortest path。

Eer the R。Or one of the other QIs？So the best possible scenario。Is that Q7 is connected to this tree。

By the shortest of all of the paths between it and R and the other sample points。

It's going to be connected by some path。To either the root or the other sample points。

 And the best case is going to be the shortest of all those paths。

 That's the minimum amount we we could possibly pay connecting Q7 in phase 1。

So the clam here is expected cost。To connect Q I。It's certainly lower bounded。

So maybe I should say without the expectation first。So first just with probability one。

Cost to connect QI。To tea。Is it least。Shortest distance。I see。然后。Yeah。所有。아つ。Between Q， I。

And the roots， plus all the sample points， of course， excluding QI itself。Okay。So with probability1。

 we can always lower bound the connection cost we incurred in phase one handling QI by this just because we used one of these paths。

 Best case is the best one。All right， so if you agree to that， let's just take expectations then。

Okay。So that happens always， so it certainly happens on average。All right。

So let's think about the right hand side there a little bit。So what is that really。

And so this is true， you know， this is true for each of。The sample points， each of Q1， Q2 up to Q T。

 So it should be T。All right。So I claim then that。Expected cost in phase one。

Ass at least k times the expected value of a random variable x， where I'm defining x。

To be the distance。Between on the one hand。A sample from pi。Namely QI。And。R plus。K minus-1， IID。

Samples。From highi。I。e。 the root。 And on that board， this correspond to the。

T minus1 sample is not counting QI itself。Okay。So I claim that's just what this is， right。

 So QI is just a random sample from pi。 R is fixed， Q minus Q minus I。

 that's just T minus1 ID samples from pi。That's true for every each one of the。

Each one of the T samples。 So we incur that cost， that lower bound in the cost。

 T times once for each iteration in phase 1。 that gives me this lower bound on the phase one cost。

Any questions about that？So do you think this is just a very simple random experiment？

You draw a point from pi once， you set it aside。Then you draw a K minus one other points from pi。

You add the root to them， and then you just look at the nearest neighbor distance between your first sample and these tea pointss。

So that's random， of course， it has some expected value。

 and the claim is that expected value was a lower bound on the cost incurred in each iteration of phase one。

Each of the tierations。Yeah。Okay。So what about phase 2， Remember we're trying to prove。

 we're trying to charge our cost in the second phase to our cost in the first phase。

 I say life only gets better。Once we're dealing with the actual terminals。Well。Here's step two。

Or we're connecting things via a shortest path to what we have so far。

And you what we have so far includes certainly the root R， it also includes all of Q1 through QK。

Okay。So preceding S1 or any of the Si's are the root in K ID samples。From Pai。And of course。

 your nearest neighbor distance to what's come before you is only going down as more and more things come before you。

 there's only more and more things to be your nearest neighbor。So in each iteration。

Of the second phase。The expected distance between S and what's come before you is actually an even better experiment than this。

 the same experiment， except with more ID samples here。

And so your nearest neighbor distance is only going to be smaller。So notes。And step 2。Expected cost。

Of every iteration。Is it most？Expected value of x。 expectation of this thing。Because literally。

 it's exactly this same thing， but with B replaced with more samples。So that's it。

 So that means in phase 2， we have an upper bound of T times the expectation of x。

 in the first phase， we have a lower bound of T times expectation of x。 So that's step 2。

 That's step 2 of the proof。Right。So the cost you incur。

Building the infrastructure and the samples dominates the expected cost that you incur on the actual terminal。

Any questions about that。Cool。So I want to talk a little bit about a random permutation model。

 This is a question that was asked early in the lecture。And。

This is all going to be able to talk about it in class is the next 15 minutes。

 but it's a model that's been。Starting to be very popular， especially for online algorithms。

 It's a really good match for the analysis of online algorithms。And you can think of it as。

A semi random model。For online algorithm analysis。 Okay so remember what a semi random model was。

 We talked about that first in the context of graph problems。

 That was where you had sort of a mixture of an adversary in nature。嗯。So an adversary was， and so。

 you know there's a little about that of the I model where the adversary picks this distribution pi。

 but still， it's closer to average case analysis， what we just did。

 It's closer to sort of a robust average case analysis here， the adversary has more power。

So adversary chooses。Sorry， a worst case in but， its favorite sequence。And then nature。Presents it。

In a random order。Okay。And so again， you can think of analogies here to things like smooth analysis to things like pseudoran data when we're talking about hashing。

 where basically， we just want to assume that the input has， in some sense， sufficient randomness。

 Otherwise， we don't want to assume anything about it。 And indeed。

 most of the positive results in this model， we're going to work with just a uniform at random ordering。

 but a lot of them work more generally， as long as it's know sufficiently random ordering over the input sequences。

 sorry over the over the possible orderings。Now。This model has been studied for network design problems。

 I might say a little bit about it if there's time， but if I'm only going to say one thing about it。

 it needs to be about so called secretary problems。Because this is really。The paradigmatic。

 random ordering problem。I。e。 guessing the max of a sequence。对。So the deal is。An adversary is given。

 you know， like 10 index cards。 Okay， writes arbitrary numbers on the 1 thousand index cards。

 It can be negative， can be arbitrarily big， just from some totally ordered set。

And you're responsible for out of these thousand figuring out which one has the highest number。

 And the adversary is just going to flip them all over， F down。

You're just going to see the cards of one at a time face down。Then you say。

 do you guess this one or not？Okay，And if you don't guess it， then I show you the number on the card。

 I throw it away。 We move on to the next one。 And you say， this one or is it not this one。Sorry。

 I I show you the number， and then you make the decision。 Excuse me。 Sorry， Yeah， sorry。

ExcuseSo I show you the number and you say stop or continue the next one。 Okay and you know。

 the secretary story is， you know， you're hiring someone for a position， you interview。

 you interview them， you discover their quality and you're wondering whether you should hire them or not hire them and move on to the next candidate okay。

All right， so I show you these numbers on the index cards， at some point you have to say， yes。

 I'm picking that one。And you win if and only if you get the highest number of them all。

Out of be thousand。 So if you guess randomly， you'd have a  one in a thousand0 chance of being right。

So the question is， is there anything can do that's smarter than know， random。

 It's better than one in1000。And probably many of you have seen this。And indeed。

 it's pretty easy to do better， actually。So it's quite easy to get it right with 25% probability and to see why you're getting it right with 25% probability。

Oh， I forgot to say， right。 So right random permutation。 Okay。

 so the adversary writes them down the N X cards。 O， but then nature is going to shuffle them。Okay。

Otherwise， there'd be no hope， turns out。So they're presented in random order。

 And so that's exactly this model。 Advdversary chooses the set， if you like。

 the unordered set of numbers you're going to see。 Nature chooses the random ordering in which you're going to see them。

So how would you get the max with at least 25% probability。And have a one liner for them。

You sample like some constant number， and then。You tracked the max for that。

 and next time you see someone who's better than a max for Mac。Exactly， yeah。

 so to get quarter half works， exactly。So you just interview the first half。

 You don't tell them this， but there's no chance you're going to hire them。

 That's just to get calibrated。And then you pick the first candidate after the first half， if any。

 who's better than the best you've ever seen so far，Now， of course。

 if the best person in the pool was in the first half， your toast。Right， you have no chance， right。

So， but as a sufficient condition for the succeeding。

 suppose you're lucky enough that not only is the best person in the second half。

But also the second best persons in the first half。Okay。Then you're golden。

RightSo what what's the thing you're worried about。 The thing you're worried about is that。

 the diamond is indeed there in the second half， but you didn't get sufficiently calibrated by the first half。

 And you mistakenly hire somebody who while better than anybody you've seen so far is not the best。

But if the second best person in the pool is in the first half， you're very well calibrated。

 no one's going to fool you into mistakenly hiring anybody other than the best person。

 And conversely， when you get to the best person， you will hire them。

So if you're wondering whether this is the best possible strategy， the answer is no。

 although it's not far from the best possible strategy。

 if you interview the first one over E fraction， so roughly 37%。And you use the same rule。

 hire the best person after that。And also if you do the accounting more carefully。

 that gets you a one over e success probability， so about 37% success probability。

So that's the secretary problem。And I wanted to take at least a little time to tell you about a sort of generalization of the secretary problem on which many of my friends have bagged their head against the wall for many years now。

 but it it sort of become a famous， slightly slightly notorious problem。嗯。

And this is the right place to mention it。So this is called the Maroid secretary problem。Yeah。So。

Tell you briefly what a majorroid is。 The basic idea is you want to answer the same question。

 but where you have the potential of actually hiring multiple people。 Okay。

 so the simplest version of this problem is I tell you you can hire 10 people。

And you just want to make a smart decision in the same model， online random ordering。

More complicated it would be when there's also feasibility constraints。 Okay， so maybe actually。

 I don't just want you to hire any 10 people。 I really want a certain skill set covered。O。

So maybe everybody has some number of skills， right，2 to three skills。

 and there's like 10 skills that want hired。 Okay， so maybe you wind up hiring five people and covering them all。

 maybe you wind up hiring four people and covering them all， whatever， Okay。

 but that's kind of what I want， okay。So Ma choices are an abstraction to discuss a rich family of these constrained multiple secretary problems。

 let me tell you a little bit about that。So you is the universe。 So of all secretaries。

 So these are the people you're eventually going to。Interview。Okay， and each one has a value。VI。

 this is the value to you。So think of it as you get VI dollars if you hire this particular person I。

But you can't just hire anybody。So there's a set of feasible sets。Okay。

 so some collection of subsets of you are deemed feasible。So I want to give you some examples。

So first would just be you can hire K people and I don't care who they are in case of the K secretary problem。

 so that would mean a subset。Is feasible， belongs to seed if and only if。

The cardinality of this is at most k。This is also something called a uniform matrix。

 So the standard secretary problem is just this when K equals 1。Okay so you can hire one person。

 can I don't care who it is， you can't hire two people， so a set with one element is feasible。

 a set with more than one element is infeasible。All right。

 so remember C just denotes the feasible sense。So let me give you some examples which are not don't look that well motivated。

 but are more meant to kind of。Get you to think about the math in the right way。

So first there's a so called graphical matteroid。So imagine these secretaries are edges of a graph。

Whatever that means。And then define the feasible subsets。To be the ascyclic subgraphs。Okay。

 so basically， you're allowed to hire a subset of people， if and only if there's no cycle。

Graph theoretic cycle amongst them。W is that a useful construction for the。

It's very useful for understanding what a major it is。Yeah， so， so I decided to。

Pitch the lecture more to help you kind of understand the mathematical concepts as opposed opposed。

 I mean， frankly， I mean， this major secondary stuff， it's more fun than it is applied。

 It's not like it's inconceivable to be applied， but this has primarily been kind of you know。😊，Well。

 yeah， it's sort of the original secretary problem。 may be all you need for that for most people。

 I'd say。 So， you know， modulo， people with unusual tastes or cultures。U。Yeah。

 that so let me finish let me give you one more example。嗯。Maybe I'll give you actually。

 maybe I'll modify the third example to give you one that actually is pretty well motivated。

 So a different one would be。Suppose you have a bipartid graph。Okay。And。Right， and basically， I look。

 so you can define the subset of a matteoroid to be the subset of， say， the left hand side for which。

There's a matching of all of them to the right hand side。Okay，So， so for example， it could be that。

 you know， if I talk about all the vertices on the left hand side， there is no matching。 Okay。

 that matches everything on the left hand side。 You know。

 if I just focus on like one vertex on the left hand side， presumablys it's easy to match。

 I just pick any edge adjacent to it。 And in general， kind of the bigger the set。

 the the harder and harder it's going to be to have a perfect matching of the vertices in that set to the right hand side。

So you can talk about the subsets of vertices that emit a perfect matching in the sense that are matchable。

 Okay， So that's also a matroid。And that starts getting closer to the problems one might care about。

 right， So like you could imagine， you know。You know， basicallyically。

 you can imagine that these are sort of people， and they have locations where they'd be willing to live。

 okay。So that's what it means on the left hand side。

 that these are people and their edges or places they might be willing to live。

 The right hand side are positions at different locations。

 So now you're both hiring people and kind of figuring out where geographically to send them to。

And so maybe let's say you have a capacity of only one at each of the locations。

 so you can't hire so many people that there's no way to send them all the distinct locations。

So that's another metric。 that's called a transversal metric。Okay。

 and then another sort of canonical example is if you， again。

 this is now just a mathematical example。If you look at vectors。And over some field。

 and you look at the subsets of them that are linearly independent over that field。

Those also form a matroid。 I haven't told you what a mattriot is yet。

 I'm just telling you the examples first， okay。All right。

 so what properties is it that all these set systems share？

That all these scripts share that make the metroids。So it's two properties， one is simple。

 one is less simple。So it should be not empty。 I'm not going to write that down。

 The first is it should be what's called downward closed。

 meaning subsets of feasible sets are also feasible。

Which is very natural in most of the stuff that we're talking about。 Okay。

 if you have the resources to hire people's1，7 and 10， you can also hire just 7 and 10， if you want。

So if S belongs to C。And teasus sub theve。Then T also belongs to C。So that's the first thing。

 The second thing。 and this is what really has byte。 This is the exchange axiom。

Which says that suppose you have two。Feaible sets。One of which is bigger than the other。

Then there's some way I can augment T。 I can make T bigger。Staying feasible。

 adding an element from S。So S is bigger than t。Certainly I can pick something which is in S but not T。

But not only that， I can pick something in S not T。Such that if I supplement tea with I。

It remains feasible。Think just about these uniform matrixs， okay。So this just since say K equals 10。

 So it says it's feasible if， if you have 10 people or less。

 Okay So suppose I give you one set that has8 people， another one that has six people， okay。

I can certainly find someone from the group of 8 who's not in the group of six。

And I can add them to the group of 6， and that'll still feasible because there's only seven people。

 So that's sort of trivial for the uniform matot case。If you think about， you know。

 vectors that are linearly independent， if I have four vectors that are linearly independent and there' are set of three vectors that are linearly independent。

I can find something among the four， which is not in the span of these three。

 And if I add that over here， it blows up the dimension。 as it stays linearly independent。

And that's one of the original motivations of the definition of nature is thinking about linear algebraicness of vectors。

For graphs， it's actually pretty easy to prove。 I'll put this as an exercise。 Okay， it's not trivial。

 but it's straightforward and elementary。 it's a CS S 1。

61 level exercise to prove it for graphs that it satisfies the exchange property， okay。And。

To the goal， then。The goal is you're going to be given these values in random order。

OkayAnd you have to， again， irrevocably pick at each point whether to hire this person or not。

You are required to be feasible， no matter what。 O， It's like if you can only hire 10 people。

No random coin flips should cause you to higher 11，Or for a graphical matteroid。

 nothing should cause you to higher acycle。 Okay， so you can never do that。

But it should be the case that on average， over the random ordering， the value that you get。

 meaning the sum of the V Is for everybody you hire should be almost as high。

 meaning at least a constant fraction of the maximum possible。Okay。

 so we got that in the original secretary problem with a one over E approximation factor。

So the question is， can you get some constant factor approximation no matter what the mettroroid is？

And the conjecture is yes， but we don't know that。Okay， so conjecture。

Constant approximation possible。For every matrixot。We know it for a lot of special cases。

 For example， I'll put on the homework， the case for graphical mats。

 which is pretty simple to get a constant factor。 We know it for transversal mats。

 although that's more difficult。 I won't put that on the homework。 We don't， for example。

 know it for so-called representable mats。 These mats that are correspond to linear algebraic vectors over a field。

 We don't know if it' that's true or not。We also know how to get a log log approximation。Okay。

 so two logs。It's not known how to get a constant。So most people。

 when they think random permutation model， this is what they think。So it's just。

 you know I want to do to kind of have heard of this problem。

 the other thing I just want you to think of this as is know this is sort of you know the semi random type model of choice usually when you're trying to reason about online algorithms。

 okay so it's more stringent it's harder to get positive results than for an unknown ID distribution so if unknown ID distributions too easy。

 consider the random permutation model for more robust results。So I'll see you Wednesday。

 where will conclude with online decision making。