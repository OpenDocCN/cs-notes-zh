# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p12 -12-(Lecture 12_ LP Decoding_Introduction to Smoothed Analysis).zh_en -BV1yqVzzqEQ5_p12-

We're going to finish up the discussion， the proof of LP deco codingding from last lecture。

 and then we're not going to do any hard technical stuff。

 but I'll give you sort of the high level goals of smooth analysis。

 That's what we'll do in the second half of the lecture。

So let me help you page back in where we left off last time。

 The good news is almost everything we did Monday， we can just sort of accept as true and then sort of just proceed from there。

 which is what were we doing So we were considering decoding So we talked about these families of codes which you can define using a graph a bipartite graph So on the lefthand side you have variables on the right hand side you have these parity checks So each parity check just consists as a subset of the variables and is asking that an even number of those that subset of variables is equal to one and and the code words are exactly those vectors that satisfy every single one of those parity checks and so we proved last time on Monday information theoretically that these codes have good distance if you use a bipartite graph that has expansion So that was this short proof we did that use the fact that many parity checks have a unique neighbor if you have a bunch of corruptions and then we shift the attention of focusing okay how can we do it computationally efficiently we don't just want to know that it's possible in principle to decode we want to polyno all time algorithm to do it。

And like several previous lectures， we're studying in particular， when does linear programming work。

 what does it mean by work， what we write down the linear relaxation for this NP hard problem so we started with an integer program。

 which was exactly the problem of finding the nearest code word to a given message Z。

 we looked at a linear relaxation sometimes it's going to be fractional because the problem is NP hard。

 but we're asking for sufficient conditions under which we solve the linear program in polynomial time and it gives us back on a silver platter。

 the nearest code word okay so extra conditions under which we get the exact solution and we made a lot of progress on Monday。

So specifically， we identified a sufficient condition under which the unique optimal solution to this linear program is indeed what we want。

 is indeed the nearest code word to the corrupted code word that we were given。

 So let me just remind you sort of what those what that condition was。So the condition okay。

 here's theem we're trying to prove。 So all of this is exactly the same terminology and notation as Monday。

 So this is all in your notes or on the video from last time。

 So we're thinking about a bipartite graph that satisfies three conditions。

 The first two conditions basically just says it's bounded degree so that's the low density part of the low density parity check in particular。

 every node on the left hand side has degree D Okay and think of D is maybe like 12。

 So that's the number of parity checks in which each variable participates。

 The right hand side Ie the number of variables in a parity check that's also constant maybe twice as big 25 something like that。

The third condition is the expansion condition， so I've written that here so that you can remember。

 so this is what says that on the left hand side。If on the left hand side of the bipartite graph。

 you take a constant fraction of the vertices。S okay。

 so when most delta times n were delta some constant， then the number of distinct。Neighbors of S。

 and of course， it bi。 So the neighbors are on the right hand side。

 The number of distinct neighbors of nodes of S is almost as big as it could possibly be。

 Every node on the left hand side is degree D。 So the most number of labels neighbors you could possibly have as d times capital S。

 you have 75% of that at least。 And that's true for every sufficiently small set S。

 all the way up to a constant fraction of the nodes all the way up to Delta n nodes。

 So that's conditioned3。 So we're trying to prove that any whenever you have a code defined by such a bipartite graph。

 then this linear program and you suffered sufficiently few errors。

 So last time I wrote Dlta not times n， I'm just taking delta not to be delt over2。

 So if you suffered it most deta n over two errors， then the LP is exact。

 and we proved that if there exists feasible edge weights for the bipartite graph。

 And I'll tell you what that means。 But we proved if there exists feasible edge weights。

 then we get the conclusion we want。 then we get exactness of the LP。

 So we were reduced the proof of the theorem to the proof under the same hypothe。

Of the existence of a certain family of edge weights。 Okay so that's what we accomplished on Monday。

 So the remaining action item， the remaining thing to do is to show that under these hypotheses。

 we really can exhibit weights that satisfy these conditions。 Okay。

 and so that's that's we're going to do for the next 20 or 30 minutes or so。Right。

 so the proof of that， that's what we did at the end of last lecture。

 that was just this weak duality argument， which is sort of kind of very algebraic。

 but you just follow your nose and it works out。 In some sense， really， you should think of it。

 you know， the reason these things are defined the way they're defined iss exactly so that proof at the end of last lecture works。

 I mean， really， the way you think about it is you start with the proof that you want。

 and then you reverse engineer the condition。 And this is just the condition that pops out。

 It's a special case of weak duality。All right， so what what is a feasible edge weight。

 This is what we actually got to have to exhibit this lecture， So we have this graph。

 so we're going to assign a weight to every single edge of the graph that's WIJ could be positive or negative。

And the first two conditions basically say， you know。

 gives us a budget on the total edge weight that can be incident to a note on the left hand side。So。

 if we think about。Some note on the left hand side and its various neighbors。All right。

 so one other thing you remember also on the homework and we mentioned this Monday by a shifting argument to prove the theorem we can focus on the case where the code word we want to recover is all zeros okay which is definitely a member of the code so in our mind we think of that the sender sent the code word zero most to this many errors so we get a vector with it most to this many ones everything else is zero and we want to solve this LP and have it solved to the all zeros solution okay。

So capital I denotes the coordinates with no corruption， so these denote the zeros。

Jy denotes the ones。 So there aren't that many of these。 This is where we got a bit flip， okay。

Fasible edge weights， that means that for all of the uncorrupted coordinates。

 you get a budget of one on the sum of these edge weights。 But for the corrupted coordinates。

 these have to， on average， be negative。 Okay， so sum of these edge weights be has to be less than -1。

 So those are the first two conditions， then we also have this condition on pairs， which is。

 on the other hand， if you think about it from the right hand side of the graph。

So you look at any two variables that participate in a parity check J。

 then the sum of their edge H should be non negativeg so we actually needed this for all even cardinality sets。

 but then we observed at the end of the last lecture， if you have this for pairs。

 you have it for all even cardinality sets just automatically okay。So that's where we work。

 so I want to prove that under these conditions， these always exist。

 and the proof is I'm just going to show you the weights。

So any questions about what we're doing or why？That's the missing limit。2。Then let's do it。So， proof。

All right， so J is the errors， remember， and there aren't too many of them。

And that's obviously going to have to be used somewhere。So here's the first step。

So we're gonna exhibit these weights。 And we're obviously we're gonna。

 we're gonna have to make sure that both A and B hold。 And somehow， you know。

 right on the borderline， we're gonna have to still a third argument。

 So the first step is we're almost going to take a closure operation over the corrupted coordinates。

 So we're going supplement the corrupted coordinates Jay。 by extra coordinates。

 which weren't themselves corrupted but you know， somehow， you know。

 they're almost like corrupted by osmosis by other corruptions that they share a lot of parodity checks with。

 Okay， so。Precisely。I'm had to define a set K of coordinates。 So again， it coordinates I。

e a bunch of vertices on the left hand side。So these are。Coordinates。

 which are not themselves corrupted。So， we belong to I， but。At least 50% of their parity checks。

Do have a corrupted variable。So in other words， have neighbors。And J。All right。

So the picture you want to have in mind。Is。So here are the flipped coordinates， J。Okay。

And they have some neighbors。And you also want to think of sort of the parodity checks that these variables appear in are polluted in some sense。

 so they've got some things going wrong。And K， vertex and K is somebody。

For whom a lot of their parity checks contain some other corrupted variable。All right。

 so that's a definition。And。You'll sort of see why we use this definition in a second。

 But the first thing I want to prove is that actually， you know， even if we throw in K。

 it doesn't blow up the sort of size of coordinates we have to argue about by very much。 Okay。

 so K is sort of not much bigger than J。So a claim。Is that if we look at J and K together。

 so the corrupted coordinates plus these kind of corrupted by relationship coordinates。

It's still at most Delta n。 Delta is the same Delta as in the expansion condition。

So that's the first thing I want to approve。So this will be the first。

 but not the last time that we use the expansion condition。It's a proof of claim。Soupp not。

We're going to proceed by contradiction and the contradiction will be eventually to the expansion condition that G allegedly satisfies。

So suppose， in fact， this is bigger than Delta n。I want to choose a subset that's exactly size Delta N。

 Okay， the reason I want that size is because I want the expansion condition actually applied to this subset。

 And this only goes up to sets of size Delta N， okay。So， choose。A bunch of coordinates。 Okay， again。

 we're dealing with left hand side vertices here。So that on the one hand。Basically。

 what we do is we take the corrupted coordinates J。

 and we just supplement them by these corrupted by one hop coordinates up until the size of deelta n。

So J Union K。And the size of S is exactly delta times that。So in this picture over here。

 I'm taking all of GA and part O K。All right。S。I want to show that this condition is violated。

 And that's my contradiction。 So what does this condition say， It talks about the neighbors of S。

 Okay， so basically I going to want to say that actually， if J union K is too big。

 then here's a set that doesn't expand。 So to talk about it not expanding。

 I need to count its neighbors。 I need to say the number of distinct neighbors is not too big。

 So let's try to figure out how many neighbors does S have and intuitively。

 if you look about the definition of K， K is defined as basically saying it already has a lot of redundant neighbors with the people already in J。

 So that's of where the contradict is going come from。 there's just too many neighbors in common。

 given that this thing is an expander。But you， to really prove that when you're a short calculation。

So to count the numbers of S。Let's first count the neighbors of just the corrupted coordinates。

And then let's count the extra neighbors， distinct neighbors that the vertices that we picked from K。

 so the vertices and K intersect S contribute to the set。Okay。So this is going to be。

The neighbors of。Let's see S intersect K。So this is just the vertices of S that we haven't already counted in J。

 but again， we just want to count distinct neighbors。

 so we're going to subtract back out the ones we already counted that the neighbors of J。So again。

 we're just breaking up the neighbors beveque by those who are a neighbor of somebody in J and those who aren't a neighbor of somebody in Jay。

So now， again， we want to say this is not too big， so we want number bound。So Tupper bound。

 this first thing。We're just going to use it as deregular on the left hand side， okay。

So this contributes to most D times the number of corrupted coordinates。 And of course， to this。

 we have control over。 There's the number of errors。 And we're assuming there's not too many。 Okay。

 so that's fine。 We have an bound on that。And then the second step。

 we're just going to have an upper bound by the definition of K。 Okay。

 the fact that K already has a lot of their neighbors already covered by J。So in particular， you。

 for each vertex， each coordinate of K， at least half of its neighbors are redundant with those we've already counted。

 so they're each contributing at most D over2 to the number of neighbors。

 given that we've already counted J。So plus D over2。Times the countercardinality of S intersect K。

So any questions about that step？AllSo again， this per vertex is trivial。

 this the per vertex contributions by the definition of K。All right。So we know Jay can't be too big。

RightWe're assuming that there's at most。Delta n over two errors， right？The set overall has size。

 delta n， so whatevers remaining is in here。So this is at least deelta n over two。

And for the purposes of an upper bound。Since these are contributing less than this。

 the worst case for our upper bound is that basically this and this have exactly the same size。

 Delta n over 2。That's as big as this could get as if this is as large as possible and this is as small as possible。

So what if it were actually the case that。This was Delta n over 2， and this was Delta n over 2。

 Then it would just give us D， Delta N。Well so basically you do this computation， the dust settles。

And you get。This is at most。3 quarters。D。Delta M。Okay。Delta number two， Dlta number two。

 you add these， you get 3D over  two， so two times2 of thenominator gives you the four。And。

Now we're done。Because Delta n is just equal to the size of this。

So we've just counted up the neighbors and proved that it's strictly less than 75% of D times the size of S。

 And that's the reason I left this expansion condition up here so you can see that's immediate contradiction。

 that's exactly what this asserts can't happen。How that the It is not。

 I'm sort of toying with the idea of putting on the homework， asking you。

 what is the minimum value for which everything in these proofs work。

So it's a value which is not too far from the minimum possible for which the proof works。

 and subject to that keeps the numbers nice throughout lecture。I'm looking out for you guys。

All right， so so that's sort of a preliminary step that we need we're when we want to verify the feasibility condition。

 it's convenient to not just have a dichotomy between corrupted and uncorrupted coordinates。

 but in fact have a trichotomy which includes this third case。

 coordinates which are sort of not themselves corrupted but share lots of stuff with these share lots of parity checks with corrupted variables。

 but it's not a big deal because this isn't too big。O。So good。

 So now I can just tell you the weights。U。set actually has an intuitive meaning too because if youre doing a local search that did try to reconstruct the code word right these are the variables where they would say。

 hey， I should be flipped right because half of my half my parity checks say I should be flipped potentially I it sort of depends on exactly how many。

 it depends on the parity of the number of flipped variables that you shared the parodity check with right So that would be true if you were sort of the only one was flipped。

 you know， or if an even number of other people were flipped but absolutely somehow。

You'd think that if you lots of your parity checks are shared with corrupted variables。

 you'd sort of expect most of your parity checks to be messed up intuitively。

 Really proving that is not obvious， but that's definitely good intuition。

 you' at risk in some sense， yeah。You'd sort of expect it to。Right。

 so certainly if most of your parity checks， certainly the converse。

 if most of your parity checks do not have corrupted variables。

 then you're going to look locally quite good for sure。

And it's good intuition to think about the converse as just holding。

 even though that direction requires a proof and uses the expansion condition。Okay。

 so let me just define for you the weights。OK。And this is pretty slick。

 So this is actually not the first proof。 This was sort of a slightly simpler version of the original proof by Fdman ball that came along a few years later。

 And yeah， it's slick。 Let's just go through it。Alright， so we're going define the。

 So so here's the plan。 Right， So these are the three conditions we need。 And the one which looks。

 to me， intuitively， I kind of have the less， the least feel for is the third one。

So what we' going to do is we're going to define the weights。

 So the third condition just obviously holds。 Okay， that won't be the problem。

 and then we'll have to check that A And B hold okay。So it will define。

 so this third constraint is you know talking about the right hand side because so you correspondingly。

 we'll define the weights J by J independently， so in some sense。

 each parity check J will specify what the weights are for all of its edges。

 so with the variables that it includes。So here's how it works。So each parodity check。

Picks a favorite。Favorite variable。So I'm going to use the notation v of J for the variable chosen by J。

It's got to be one of the variables in it。And。There's going to be a nontrivial constraint。

Which is that if you're a corrupted coordinate or if you're one of these friends of corrupted coordinates in K。

 you have to be chosen by lots and lots of parity checks。 that's going to be a requirement。So chosen。

At least three quarters D times。Now of course， you can only be chosen by parity checks in which you participate and you only participate in D parity checks。

 okay so there's no way you're chosen by more than D people and the insistence is that at least at least for these coordinates and J&K you better be chosen close to the maximum number of times。

 75% of your parity checks better choose you。Now， if you think about it。

 it's not obvious you can do that。Okay。Because a given parity check has lots of variables。

 And actually， maybe even a given parity check has lots of corrupted variables。

 I can only pick one of them。Okay。And that could totally happen。 So remember。

 we might have 1% of the things being errors， right。

 and a parity check has a constant number of variables， know。

 like 20 right So maybe there's  a million coordinates。

10000 are corrupt and a given parity check has 20 variables for probably know all 20 are corrupted。

 so it has to pick only one and those other 19 will not be chosen by this parity check。 So the hope。

 of course， is then that well， you， then hopefully there's know most of those variables。

 other parity checks can choose them。 Okay Now that wouldn't work if somehow those 19 variables showed up and all of these other parity checks together。

But now intuitively， if it's got this expander condition and everything's kind of totally scrambled all over the place。

 maybe that doesn't happen。Okay， that'd be the hope。 O， And it's true。 And actually。

 it's not that hard to prove。 It turns out， especially if you know Hall's theorem。

 So who knows Hall's theorem， raiseise your hand。You should know Hall's theorem。 Okay。

 so Hall's theorem， who knows Max Floman cut。Okay， so hall theorem is a corollary of max Fment cut。

 Okay， actually a quite easy corollary。 It would be a great like 2。

61 problem set question to just deduce hall's theorem from max Fment cut。

 But here's what it's But know hall theorem came first， actually。😊，Just from the 30s， I think。

 So it's about matchings。So let's just say， let's just talk about perfect matchings for a second。

So suppose you had to bipart that graph， and you're wondering whether or not it has a perfect matching。

 okay。So to convince you that it does have a perfect matching。Okay， really easy。

I'll show you the matching。 So if you like， matching is N N，So。

 but it's actually quite easy to put in Co MP using Hall's theorem。 I mean。

 we know it's in Panmo time， but forget about that for a second。 So certainly one you know。

 way I could convince you that there isn't a perfect matching is if I showed you a constricting set。

So suppose I showed you 10 variables on the left hand side so that the number of distinct neighbors of these 10 nodes was a set of only8 nodes。

You should then be convinced that there will not be a perfect matching of this graph。

In a perfect matching， any set of K variables has， K mates。 They're distinct。

So if you don't have 10 distinct neighbors of this set of 10 variables。

 No way can you have a perfect matching。 Okay， So it's clear that a necessary condition for a perfect matching is that every single subset of K vertices on the left hand side has at least K distinct neighbors on the right hand side。

 If you don't have that property， you certainly don't have a perfect matching。

Hall's theorem asserts the converse。 If it is the case that every single subset of K vertices on the left hand side has at least ca to neighbors。

 then there does， in fact， exist a perfect matching。And so this， again。

 you can deuce so just from max flow min cut。 All right。

 So the flows give you the matchings and the min cuts。 if you don't have a perfect matching。

 then the max then the mint cut of the graph will basically exhibit for you。

 one of these constricted sets。So this I'll put on the homework。

 I'll just let you take Hall's theorem as a black box。 although again。

 it' be busy already know to prove it。 But using Hall's theorem。

 it is in quite straightforward to show that because the graph is an expander。Wwhichch of course。

 talks exactly about the number of distinct neighbors that any subset the left hand side has because the graph is expander and the number of distinct neighbors is at least 0。

75 d times the size of the set， you can find sort of a union of 0。

75 times d matchings which is the same thing as basically saying each node on the left hand side is chosen  three quarters times d times。

So it's not obvious， but。If you think about houm a little bit and you use the facts its expander。

 it's just true。Alright。Any questions about that？For the rest of the proof。

 I'm just going to assume that we have such a magic。 Okay But again， here again。

 we are using the expansion property of the graph。Questions。Okay。All right。

So every parity check picks a favorite variable。And the constraint is that any corrupted。

Variable or friend of corrupted variables。 Any in J And K is picked lots of times。 Okay。

 so maybe you think of D as like 12。 Everybody gets picked nine times。Everybody in JK。All right。

 so what are the weights， So homework。This is possible。Allright， here's our way to find the weights。

We define them differently， depending on if the chosen variable is corrupted or not。So， if。

The chosen variables corrupted。Which sort of makes sense if you think about it， right。

 because I mean， C is going be， we're just going define these so that C holds。

 But we also eventually have to worry about A And B。

 And it's really the corrupted variables impose a pretty nasty restriction on these weights。

 We basically have to like lots of negative weights next to a corrupted coordinate。

 But at the same time， we have to have these non negative pairs。Okay。

 so that's why we're going to treat them differently。 So for a chosen variable that is corrupted。

We're going to。Have the corresponding edge have a negative value。So we said。

The weight of the edge between the favorite variable。And this pared check。To be equal to minus。

Two over D minus epsilon， where epsilon is don't worry about epsilon。

 that's just like a tide breaking epsilon。 Okay so epsilon is an arbitrarily small constant。

-2 over the degree D of the left hand side nodes。 Okay。

 so the two is probably a little mysterious right now。 The two is some slack that we need。

 The reciprocal in D， we actually mentioned this very briefly last time when I tried to develop your intuition about the weights。

 So let me go through that discussion again。So intuitively。

 because existence of the weights implies exactness of this linear program。

We're sort of thinking that， you know， we're thinking that the exhibiting feasible weights should get harder and harder as there are more and more errors。

 as J is bigger and bigger。 And remember， if J was empty。So if you literally had no errors at all。

 then this is a trivial problem because you just said all the W's to be equal to zero。Okay。

But then and then we also argue that， well， at at least it's a， know。

 vaguely robust argument is that if J is still super small， if J is so small。

 that no parity check has more than one。Corrupted variable。

 Then it's also really easy to exhibit feasible weights。

 basically just for each basically what you do。Its just next to each corrupted variable。

 You just give all the edges the weight like -1 over D。 Okay so it has to have a total of -1。

 You just spread it equally among the D adjacent edges。

 So that's -1 over D next to corrupted variables。 And then to make sure you have this pairs condition next to uncorrupted variables。

 you just have a one over D on all of the D edges。 And as long as no single parity check has two corrupted variables。

 then this condition is going to be satisfied。Of course。

 that's not good enough for what we're trying to prove， because again， we might have a parity check。

 which is entirely corrupted variables。RightSo we're doing some more clever version of the argument。

 But we actually have seen this one over D before。 Okay， that's basically saying we're trying to get。

 you know， a negative we're not trying to get the -1 from just one edge。 That would be crazy。

 We're trying to get this -1 contribution to the edges incident to corruptive variable like roughly equally from the incident edges。

 so we can't have it exactly equally， but we can have it up to effect to2 roughly equally from the incident vertices。

 right。So that's why you shouldn't be too shocked to see this reciprocal N D show up。Okay， now。

 but if we want C to be satisfied， it's actually pretty obvious what the rest of the edges incident to J better have their weights to find as。

So remember， condition C says that any pair of edges with the same right hand side vertex have to have sum of weights non negative。

 I just slapped down a negative weight。 So that lower bounds the weight of everything else incident into J to the negative of that。

 to two over D D minus epsilon。Okay。So set the other。WIjs。Equal to 2 over d minus epsilon。O。Co。O。

So there remains what to do for。Podity checks， whose favorite vertex is not corrupted。

So if the chosen vertex。Does not belong to J， then we just set WI J to be equal to zero。For all。

Incident edges。Okay。I want you to observe， so a subtle point is these friends of corrupted vertices。

 vertices and K。Also are in that second case。So if I'm a parity check J and I choose a variable which is not corrupted。

 even if it's a friend of corrupted variables， I still have everything B0。

 so that's sort of important。So again， these organizations in K are kind of walking a fine line between being treated as corrupted sometimes and uncorrupted as others。

So those are the weights。Is that clear， is the definition clear？

Is it also obvious the conditions C holds？The third condition of the feasible weights。Yeah。

 why can't you have all corrupted bits going to like one parry check or like 20 corrupted bits going one perry check。

 you absolutely can。You absolutely can。 Oh， Yeah C Con C is satisfied because we force each parodity check to pick a single favorite variable。

 And the negative weight only gets to go between the parity check and its favorite variable。

So if you have a parity check with 20 variables， all of which are corrupted。

 one of those corrupted variables for this parodity check will pick up a negative。

The rest will actually pick up a positive， which is kind of crazy because those corrupted variables have to they only have a budget of minus1。

 so we're actually sort of you know we're making backward progress as far as getting it down to 1。

But as far as that's sort of you know， that's kind of punting the problem down a little bit。 right。

 So eventually， you have to verify B。 And you should definitely be wondering why why does B hold。

Even A， the factor of two can even make you nervous about property A actually， but C。

 which was the one that maybe seemed the hardest to control， that's the one we just kind of said。

 well， let's make sure we do C and then suffer the consequences later。Okay。

Everyone ready to verify A and B。All right， let's do it。Three cases。

So let's start with the corrupted case。Which is sort of the one you know。

 we're kind of worried about a little bit。Because the budget is so stringent， minus one。All right。

 so in this case。So this is what we need to compute。 So now we're， okay。

 so we define the weights from the right hand side of the graph。 But now to verify A And B。

 we have to think about things from the left hand side of the graph because we've fixed I and we're thinking about all events。

Outgoing edges， so we have a budget of minus one here。So a question for you。

So notice that the weights take on only three distinct values。 Okay，0， positive or negative。

 there's only one positive value。 There's only one negative value。

How many of those three values are candidates for a WIJ when J is a corrupted coordinate？

So I don't tell you anything else other than I Jay a note in the graph， and I was corrupted。这没有放的房子吗？

Anything else？Could it be zero？No， it's only for is not El J。Why could it not be zero？

Oh that's region。So remember， just because you're corrupted doesn't mean that every parityote chose you。

It means that like nine out of 12 chose you。But there's also three that maybe didn't choose you。

 And if you weren't chosen， maybe somebody who wasn't corrupted， was chosen instead。In which case。

 you're going to be zero， actually。So this could be any of the three values， okay？Now。

 what we do have going for us is that by virtue of being a corrupted coordinate， in a parity check J。

 for which I is the favorite chosen variable， V of J。Then， by definition。

 that edge weight is negative。Okay， so the first thing about going for us。

 if we're chosen that edge weights negative， the second thing we have going for us is that we're chosen by most of our parity checks。

That's this condition。All right。So the worst case as for upper bound is that we're chosen the minimum number of times。

 exactly3， fourthth D。Okay， and we pick up negatives。

 And then for the other one fourth D part of the time， we actually get a positive contribution。

 We actually are like2 over D from the remaining 25%。 So that's the worst case。

 That's as big as this sum could be。Yeah。So， this is。Less than。Three quarters D times minus or sorry。

Two over d minus epsilon。So this is the contribution from parity check J for whom were the favorite variable。

Plus， D over4。2 D minus epsilon。 Okay， And this is the worst case where we have a full 25% of the people who didn't choose this。

 and they actually chose a different corruptive variable。

 So we actually got stuck with a positive value for those parity checks。All right， so also known。

As minus。D over 2。To the minus epsilon。Which is less than minus1。So that's case one。Any questions。

 Benette？All right， with。We've dealt with B， that's true， exactly right。

So we've a big check mark here。Big check mark there。Unfortunately。

 we still have two cases because we're going to have to treat these friends of corrupted variables。

 vertices of K separately from vertices of I。intuitively， we have a control。

 we have control on the sum of the weights for those two different vertices for two different types of vertices for two different reasons。

Let just put the K in the same case as J because we said that J and K are both chose at least 3。

 times so let's go through the case of K。Let's see what's different。So case two。Consider a variable。

So okay， so we're trying to prove A， for all the remaining vertices， vertices of I。

 including those in K， we're trying to prove that the sum of the weights of the incident edges is less than one。

Alright， so consider someone in K。So let me ask you the same question I asked you before。

 if all I tell you is that we have an edge IJ， and I tell you that the coordinate I belongs to K。

 what are the possible values that this weight might have？ before could have been any of the three。

 Is it still any of the three。Can't be negative， exactly right。can't be negative。

Because if you're the chosen variable。I just yeah， if you're the chosen variable and you're not corrupted and remember if you're in K。

 you're not corrupted， you're just a friend of the corrupted variables。

 if you're the chosen variable and you're not corrupted， you're zero。

 Okay so is everybody else incident to that same period of check okay？

So that's why we can't inherit the argument for the corrupted nodes because we don't have any of these negative contributions。

None， no negative contributions at all。 Min some zeros。Micine positive contributions。

 Good news is our budget is now one。O， but still， right， got。

 if we got a positive contribution to over D for all D of our parity checks， we'd be toast。

 That would give us two。On other hands。Why do we have control？ So what do we want。

 We want a lot of zero contributions and not many positive contributions。

How do we have control over that， Why do we know there's many more zeros。

 and there are positive ones。 In this case， it's just by the definition of K。

Which I guess have erased， okay？So K are those vertices for whom？

They share lots of parity checks with corrupted variables。So。Oh， no， that's not why， excuse me。

That's wrong。The reason we have control in this case is because our covering condition。

Also applies to vertices of K。That's the key point of case2。 All right。

 So remember when we when we had， this is the key point。

 when we had parity checks choose their favorite variables。

 we insisted that not merely the corrupted variables get chosen over and over and over again。

 but also these friends of corrupted variables get chosen over and over and over again。And remember。

 if you're chosen， the worst case is that you're zero， no matter who you are。 Okay。

 so the only way you're ever going get a positive contribution is if somebody else was chosen and it was corrupted。

 Okay， so if you're chosen， you're never going to get a positive number。

 You'll get either negative if you're corrupted or 0， if you're not corrupted。

So the fact that this vertex of K shows over and over and over again tells us that a lot of those WIGs must be zero。

Okay， not positive， that's the point。Okay， so in particular。

 so this is bounded above by what's the worst case？

The worst case is that it's chosen only 75% of the time by 75% of the parity checks。

And that's a zero plus。In the remaining 25%， it picks up the maximum possible contribution。Okay。

And so this is just equal to。D over d minus epsilon1 half。Which is less than one。 But choose epsilon。

 But choose epsilon， sufficiently small。So that's why we finding in case two。All right。

 so case three。So case three is for vertices that are not only not corrupted。

 but have kept a safe distance。From the corrupted variables。And now this is what I got confused。

 This is what I was saying for case too。 So the reason we have control here。 So， again。

 for exactly the same reason。The contributions to this I。

 they're either going to be zero or they're going to be positive。

 and we want to say there aren't too many positives， there have to be enough zeros。

And here we're going to use the fact of that， well， but you know， if you're not in K。

 that means most of your parity checks are totally clean。So most of your parity checks。

 half your parity strictly more than half your parity checks。

 there doesn't even exist a corrupted variable to be chosen by that parodity check。

 So it had to choose something uncorrupted。 So you're definitely going to get a 0。

That's why you get lots of zeros in this case。All right。So formally。Some。

Of the weight contributions about the parage texture you're part of。Is going to be a most。

 So if you looked at how I defined it， if 50% of your parity checks were not clean。

 then I put you in K。 right， So if you're not in K。

 you actually have strictly more than 50% of your parity checks。 have no corruptive variable。

 So that lets me get something downed away from one half here。 again。

 the worst case is that you're in the fewest possible zeros and you have the maximum possible number of ones。

Everyone contributes2 over d minus epsilon。And this。If you choose Epsilon sufficiently small。

 you can check that at most one。So this is like d 1 over 2， and that's like2 over D。

This can be strictlyuous。Yeah。So that closes the whole loop， So that says， you know。

 using this expansion condition， we can always exhibit these feasible weights。

 and by the duality argument we have at the end of the last lecture。

 that implies integrality of that linear program， which we know has to be the optimal code so that completes the proof。

Any questions about that， that's Elpedta coding。So。All right。In that case。

 we're finally done with this exact recovery stuff。And so we're going to move on to。

A different part of the course， which you already got an appetizer of when we talked about planted and semi random graph models。

So the remainder of the course is going to be devoted to analysis frameworks which draw on aspects of average case or distributional analysis and also aspects of worst case analysis。

So I often call this robust distributional analysis。

And there'll be many different interesting flavors of models that fall into this category。Okay。

 so today I just want to sort of tell you， you know， what are some of the。

High level features and motivations of these kinds of models。

 and then also tell you a little bit more details about probably the most well studied such model。

 smooth analysis。All right， so at a high level， the goal here is to try to define a way of analyzing algorithms where you get the best of both worlds of the average case analysis world and the worst case analysis world。

 So what's really good about average case analysis is you often get sort of very meaningful performance guarantees and you get very sharp predictions and what's good about the worst case world is you get very robust performance guarantees so if you can prove anything positive。

 it holds in a vast array of settings so you'd like to be able to both prove something very strong。

 but also have it apply to many settings simultaneously so we're trying to get a sweet spot where we can have both of those at the same time。

So I haven't used this notation in a while， but let me just remind you we were talking about this early on in the course。

So in general， if you have a cost measure。On an algorithm， which again， this could be running time。

 this could be the solution quality， this could be page faults， whatever。

I use this notation for the cost of an algorithm， A on an input Z。So as we discussed。

 worst case means you look at the worst case overall input Z， maybe parameterized by the input size。

 something like that。So just to be clear， what I mean by average case。

So one thing I want to say is average case is only defined with respect to a distribution over inputs。

 So worst case， there's no distribution。 If you like。

 there's no real kind of model of any inputs being more or less likely than others。

Average case does not make sense。Unless you specify a distribution。D over the input Z。

And then the most standard thing you do。Is you look at the expected value。

On a random input drawn from the distribution D。Of the cost of an algorithm。On a random input Z。

 Okay， you could certainly look at some statistic other than the expectation also if you wanted to。

 Yeah， but for the discussion， I'm just going to focus on the expectation。But the point is。

 if you have a distribution， then you can talk about average case analysis。

 you could imagine trying to design an algorithm that makes this as small as possible，Again。

 I want to emphasize that。The algorithm that minimizes this quantity will in general。

 be different for different distributions。 D。 Okay， So again， you vary D， you vary， for example。

 the relative order of different algorithms， for the expectation。O。Right。

So I'm not going to talk much about pure average case analysis in this class。

 It will show up sometimes just sort of a benchmark against which we compare our own solutions。

 You know， I do want to just take a couple minutes to point out that you know， there are situations。

 I mean， average case analysis gets sort of a bad rap。

 I'd say in the kind of theory of algorithms literature。

 But there's certainly situations where it's exactly what you want。

 And I even sort of think as time goes on， there's more and more situations where it's exactly what you want。

So this is exactly the right analysis framework when， first of all。

 you have a very good understanding of distribution over inputs for the problem you're trying to solve。

 And secondly， you have the luxury of really being able to design a customized algorithm for this situation。

 okay。So understanding the distribution， that generally boils down to， first of all。

 having reams of past data。And second of all， an assumption about low volatility。 Okay。

 so like the stock market， we have reams of data， but I'm not sure there's anybody who feels that confident about their understanding of the distribution over what the stock market is going to do。

But there ares， lots of contexts where you sort of sort of know the distribution tomorrow is going to be like yesterday。

 or at least the distribution tomorrow will be like it was on a Thursday last week。

 something like that。Okay， and if you think about it， I mean， in the age of big data。

 mean I think there's more and more cases where this actually happens。 know。

 a lot of the big companies where some of you might go on work after graduation。

 you might well be task with coming up with some optimization problem for which you have millions or billions of data points with low volatility And in that case。

 by all means， you know， design the algorithm which minimizes the expected cost or some other statistic with respect to this well understood distribution right。

In this class， we're going to be motivated more by situations where there's still some uncertainty。

 so maybe you believe there really is a distribution and you're just not so sure about what it is because maybe your data isn't very rich or maybe just it's changing so fast。

 you're just not confident about optimizing overly with respect to a distribution D。

Or it may be that we're more interested in understanding the performance of a general purpose algorithm。

 like say， the simplex method for linear programming。

 rather than coming up with some new algorithm specifically tailored to some distribution。 Okay。

 those are both。Sort of kind of domains we're thinking about。

So there's good things about average case analysis。 The main issues are。I'd say， uncertainty。About D。

So maybe D exists and you don't know it。And there's also an issue with overfitting。

Which is even if you know D today and then you optimize。

 you get every last sense out of your algorithm with respect to today's distribution。

 it could be you lose some robustness， it could be that if things are different next week because you've tailed your algorithm so carefully to how things are today。

 it doesn't respond very well to how things are next week。

So those are two reasons why you might want to add some robustness to just the high level idea of minimizing this expectation。

Okay。So how would one do that？So most of the remaining models are' going to talk about。

Can be cast as a hybrid model。 I， I mean， hybrid between worst and average case analysis here of the following form。

So。With C。Be a set of distributions over inputs。So I realize this is a little abstract at the moment。

 I'll talk about how to interpret the sit to you in a second。

So theres some the way to think about it is you believe there really is a distribution of inputs。

 You're not sure what it is。You suspect it lies somewhere in this set C。

 but maybe C includes a bunch of Gaussians， a bunch of uniform distributions。

 various parameters for those distributions， et cetera，And you'd rather not have to。

 you don't understand enough about the application to commit to something as specific as like a parametric form for the distribution of inputs。

But you like an algorithm that would work well kind of no matter what reality is。

 So you believe reality is well described by distribution。

 You're not sure which can you have something which simultaneously works well across all of these possible realities。

So rather than taking a worse case over inputs。We're going to take a worse case over distributions。

In room。So I'm going to hedge my bet over which of these distributions actually governs the data。

And then for。A given distribution of our inputs。I want the expected cost or again。

 some of the statistic if you prefer to be as small as possible。Okay。

So number of the things we're going to do next can be interpreted as instantiations of this idea。

For the moment， I want you to think about this set C of distributions as exporting a knob that you can turn to interpolate between the average case world and the worst case world。

If the sets C is a singleton。So if the set C has just one distribution in it。Then the max is vacuous。

 And so it just reduces to average case analysis。 Okay， so one thing in C is average case analysis。

If C is super big。 So if in particular， it includes every possible point mass on a given input。Then。

For the point masses， this disappears。 and this just becomes some fixed input。

 And you're taking the max over all possible inputs。 And then you recover the worst case model。多是。

So the sort of， you know， the smaller C is and you know the more randomness there is in the various points of C。

 the closer you are to average case analysis， the richer C is。

 and the more deterministic these distributions can be， the closer you are to worst case analysis。

And we're looking for a sweet spot in between the two。通ちです。Okay。

So why would you do this or why do people do this？So like with a lot of the other high level ideas we've talked about。

 there's a number of motivations and they don't all apply in all situations。

 if each of these motivations， it sometimes applies。

So the first thing which sort works really well for in all of the applications is you avoid pathological inputs。

And in particular， in smooth analysis， this is really kind of the number one reason people study it。

 So know we talked at length about the perils of worst case analysis， especially， for example。

 in online paging and we talked about how you know。

 basically you get overly pessimistic performance predictions and you get meaningless or even incorrect。

 in some sense， comparisons between different algorithms because the performance is governed by these potentially very unrealistic pathological inputs。

 So having a distribution allows you to avoid those。 as long as no I mean。

 if the pathological inputs are sort of very sparse and you have any kind of diffused distribution。

 they're not going to play an important role in your algorithm design or analysis。

So a reason or which may or may not be the goal。Is to model， quote unquote， real data。

 but that's still uncertain。Okay， so maybe you have in mind that you know。

 data is somehow sufficiently random and we'll have an application in hashing in a few lectures where this is very explicit。

 and you don't want to actually commit to you know some very precise definition of what's being inserted into your hash table。

 but you at least know that there's sufficient randomness in the data you believe that about real world data。

 So it's sort of a nice way to。You know articulateticulate qualitative properties that real data has without getting too specific。

O。So sort of a consequence of this first point。Is there's plenty of situations where there are algorithms。

For which neither worst case analysis nor average case analysis advocates for them strongly。

Yet empirically， they seem to be really good general purpose solutions。

 And so this analysis framework seems to capture some of the reasons why that's true。

 It's not good in the worst case。 You know， it's not， you。

 the literal best algorithm for anyone's distribution， but it almost always works really well。

 And again， simplex method linear programming being a canonical example。And the fourth one。

 which see see much， we won't see much of it for a couple lectures or for a couple weeks。

But just like with parameterizations， when we first started talking about parameterizations。

 the goal was merely to analyze existing algorithms like the L algorithm for paging。

 But then at some point， once we had some novel parameterizations。

 we just couldn't resist trying to design some new algorithms that did even better with respect to these parameters like maximum weight independence sets。

 we had this very cool algorithm where the the greedy algorithm where you pick sort more nodes than before and then compute maximum independence in the bipartite graph。

 And that we were driven to that with a novel parameterization。 So in the same way。

 whenever you have a a new way to analyze algorithms， know， it's natural to ask。

 does it naturally guide you to new algorithmic ideas that seem useful。😊。

But the next several lectures， this really won't be the point， really， for the next several lectures。

 just like parameterized analysis， and want to start with applications where it's used only in the analysis。

 then we'll talk a little bit about how it might guide design。Good。All right。So that's kind of。

Very high level。Let me try to help make this a little more concrete for you。So first of all。

 let me point out that we've already seen something which is you know。

 can sort of be thought of as a special case of this。 It's sort of a slightly degenerate version。

Because of the symmetry involved， but。You could sort of think of plan graph models。In this way。Okay。

 think， for example， about planted cleeique。Okay。Where somebody picks K nodes to plan a cl。

 and then you fill in the rest of the edges of probably 50% each。

 That's like having one distribution D。For each choice of where you put that initial cake leak。

Once you decide on the K cl now you just have this distribution over graphs。And there， in effect。

 our cost measure was just zero or1， depending on if the algorithm was correct or incorrect。

 and we just wanted to be correct with probably close to one， no matter where the clique was planted。

 that is for every single distribution D in that class。So that's one example。

But really a full blown example。A smooth analysis。And really。

 of all the alternatives to worst case analysis that have been proposed。 this1， I think。

 is the most well known and most extensively studied。

 That says there's still a lot of stuff we don't know about it。

 But more work on this probably than any of the other models we， we're talking about in this class。

And I'll talk about this probably for the next three lectures or so。Different applications of it。

So how's it work？Well that's a nice idea， it's one of these hybrid models。So， an adversary。

Pickix an input。 O， So if you like a linear program， O。

 possibly a linear program on which the simplex method runs in exponential time。

 so pick some worst case input。But then。Nature。Slightly perturbs the input。Okay。

So perturbation is going to mean different things in different cases。

 You could think of it as like adding a very small Gaussian or some other kind of random variable that's not too big relative to the magnitude of the values and the input。

Okay。Allright。 And， you know， so there's a couple nice things。 So really。

 the main motivation for smooth analysis is this first point。 Okay。

 so for algorithms that just like simplex， which have this very sparse set of very bad inputs。

 it's going to allow us to get rid of them in effect。

But it also has a nice interpretation as far as modeling real data。

 whenever you have a computational problem where the data is being supplied by some kind of measurement。

 then it's natural to think of as what you really see is some measured value of ground truth。

 so with's some noisy version。 maybe the noise event very small， but if nothing else。

 there were like rounding errors and the floating point arithmetic and it's not clear that you see the exact ground truth。

 you see some slightly noisy version of it。 And so this says that if ever you have input。

 that has this small noise in it that actually is already enough to justify the fast performance of certain algorithms。

Okay， so let me also just compare it briefly to semi random models。

So similar random models don't quite fit in here because the order is some sense reversed。

So in a semi random model， nature goes first。 It picks like a planet clique instance。

 And then an adversary gets to go second。 And if it wants， to can， for example。

 remove edges that aren't part of the clique。Okay， so it's like a reversal of these order。

So they're both totally reasonable and nice models， but they， they're not。

 I don't know how to unify those two because of the difference in orders。Okay。So。

What is the goal in smooth analysis？Okay let me first say， should you。

 for what kinds of problem should you consider using smooth analysis？So when does it work。

 when useful？So the main thing is that the bad inputs。So whatever cost model you're using。

 whatever computational problem you're thinking about。

 the bat and whatever algorithm you're thinking about。

 the bat inputs for that algorithm should be very fragile。Okay。In the sense that， you know。

 they really seem very delicate， they're usually extremely hard to construct the claymenti cube example。

 the bad example for simplex of decades after the invention of the simplex method。

 And you just look at it， I'm not going to go actually prove it in class。

 But if you go read about the claymentty cube， you look at it， you're like。

 that's a real knife edge example。 It's just kind of obvious right And all of the killer apps with food analysis really are for problems or it's just clear that the pathological examples or these knife edge examples。

 Okay So for that exact same reason。Usually， it's about running time analysis。 So， again， remember。

 this is an abstract cost measure。 Okay， in our different applications， this is meant many。

 many different things。 Sometimes it means running time for smooth analysis。

 it's pretty much always going to mean running time， okay。So， usually。For runtime analysis。

And the reason is that for other cost measures， the bad examples actually aren't that fragile。 Okay。

 and you can't really get rid of them with perturbations。 You know。

 like if you think about the greedy algorithm for maximum weight independence set or something like that。

You know， if you perturb the vertex weights by epsilon is really not going to fundamentally change the performance of that algorithm。

 That's heuristic。 Okay， so there's a bad input for the original one。

 A slightly perturbed version is going to be an almost bad input for the same algorithm。 Okay。

 so it just turns out that you you seem to only have this fragility of inputs for， you know。

 specific cost measures。 so in some sense。You know， this smooth analysis isn't always know。

 isn't always an interesting framework to apply， but for the types of problems that are in its crosshairs。

 it does really well。All right， so the goal。Then so now just think about runtime。

The question is when can you have algorithms， when can you prove that an algorithm has polynomial smooth complexity？

So this is going to be the supreme。so the adversary picks the input first。

 so we take a max or a soup over input Z。And then we take an expectation over perturbations。

 which I'm going to note by R of Sigma for now。 Sigma here is the size of the perturbation。

 So you can think of this if it's a Gaussian， you think of this as a standard deviation of the Gaussian。

 Okay， so if Sigma is small， you're adding a small perturbation。 If Sigma is big。

 you're adding a big perturbation。 A lot of noise。And then in here you're looking at the cost。

Which we good to think about running time of A on z plus the perturbation。

So you want to prove that this quantity。It's polynomial。In the input size。And。And。In one over sigma。

Okay。So again， with smooth analysis， usually we'll have one exception。

 but usually it's more like you're more having the perspective of we know this algorithm works well。

 let's explain why Okay， so the algorithm is fixed and you're just trying to understand its performance。

 Okay， so we have an algorithm A like simpleimpx。And， you。

 we know simplex is exponential time in the worst case。

Which means we know that as the perturbation approaches just being deterministally 0。

This running time has to blow up。Okay， so we know we need some dependence on the size of the perturbation sigma。

 because if sigma is 0， it is exponential time。 Okay So it has to be polynomial and in some function of sigma。

 And it turns out the right thing to try to be polynomial in is one over sigma。All right。

And so I hope' I wrote these next to each other for a reason。

 know clearly this is an instance of a hybrid model。 so here for each you know worst case input。

 so for each choice of Z， you have a separate distribution D。

 the corresponding distribution is just the slightly fuzzy version of inputs around the center point Z。

So again， that's your class。 Class is like slightly fuzzed out point masses。

 And you want to do as well as possible on every single one。All right， good。All right。

So I want to conclude the lecture with a discussion of sort of the origin story and still kind of the main。

 the biggest killer app。Of smooth analysis， which is to the simplex method。And so really。

 smooth analysis was invented for this purpose。So this is by spielman and Tang。In 0，1。可。

And I'm just going to talk about what they did at a high level。Okay， so what is the result。

 So basically， what do they prove， Okay， so they prove simplex。

 despite having worst case exponential running time。 in this sense。

 it does have polynomial smooth complexity okay。So they were thinking about linear programs。

So think like you， minimize。C transpose X， subject to。AX equal B， something like this。So again。

 the formal E theorem statement says， consider an arbitrary linear program。

 so you need to pick C A and B arbitrarily。For some of the most of the applications we'll talk about are not that sensitive to the perturbation distribution。

 this actually does seem or least no one knows how to prove it without a very specific perturbation distribution。

 The good news is the perturbation distribution is Gaussians。

 which is sort of the best justified distribution。 If you're only gonna use one。

 So their perturbation model。 So their notion of R sigma， They。

 they just add they just add I I D Gaussians to every single entry of the constraint matrix A to every single entry of the right hand side B。

😊，With standard deviation Sigma。And they prove that a particular variant of the simplex method。

 which I'll explain in a second， Indeed， in this sense。

 has running time polynoial and n and one over sma。It's a really big polynomial。 So in that sense。

 it's not a super accurate description of the empirical performance。

 which is usually thought to be roughly linear in N。 It's a much， much bigger polynomial than linear。

 but it is polynomial。Which is nice。Okay， so any questions about kind of this statement？

Is that a question？Yeah， so I don't know whether does this hold for like uniform distribution like Max bound does there I mean。

 that seems like the other construction that might like sort of black box Most of the theorems that we'll talk about yes。

 I do not as far as I know there is not a proof this Yeah。

 I think everyone believes that's true it's just sort of the analytical I mean。

 hurdles are very high yeah。I mean， so already the original proof of this was dozens and dozens of pages。

For Gaussians。Okay， and so that's so needless to say。

 we're not going to be covering it in lecture in any detail。

 but I wanted to say a little bit about it， you know because you know。

 it is kind of the calling card for smooth analysis。Allright， so。

So let me tell you a little bit about it。So first recall， what the simplex method is geometrically。

 right， So geometrically， I've drawn this cartoon a number of times already。But so linear programs。

 you're maximizing a linear function over intersection of half spaces。 So in two space。

 it's just a polygon。And again， remember， a linear function is just like a direction。

So you're trying to find that vertex if you're trying to maximize that direction。Now。

 the simpleimx method， geometrically is very intuitive。 Okay。

 you just walk along edges of the feasible region。 Okay， so even in higher dimensions。

 it's called a polytope。 Okay， but you still have these edges。

 so you just walk corner to corner along an edge，And you always walk along some direction where the objective function gets better。

 Okay， so it's almost like a local search algorithm， except by linearity。

 It turns out all the local maximum are also global maximuma。

 Okay so you just keep getting better and better and better。

 And then eventually you stop when no edge makes you even better than where you are now。

 and you're optimal。So correctness isn't really an issue with simplex。

 It's more how fast does it happen。And just to be clear， you look in two dimensions。

And you get a little bit fooled because you're like， how hard could this be just like， know。

 in the worst case， I walk around this polygon， No big deal， right And in two dimensions， you know。

 if you have like M half spaces， you're gonna have like M sides right to this polygon。 So a big deal。

 right。But now think about like going to higher dimensions， okay？So。

 and just think about something really simple。 Think about just like a hyper cubebe。In N dimensions。

 right？Now of a sudden， there's two to the n vertices。Okay。So if you literally， you know。

 visited every single vertex of your polytope， you'd be in trouble。 O。

 then the running time really would be exponential in N。And actually。

 the claymentti example is sort of a tweaked version of a hypercue。

 so they actually show that there's basically between the invertices and simplex actually can visit every single vertex。

 so not only the number of vertices can grow exponentially in the dimensions， but in fact。

 in pathological example， simplex visits them all。Okay， so but anyways， geometrically。

 that's what simpleimpx is doing。But like with any kind of local search style algorithm。

This algorithmcro is kind of under definedfined， right。

 because when you're at one of these vertices and you have these like 100 different edges， maybe。

 you know，73 of them are going to make you worse。 So clearly， you're not going to take any of those。

 But then there are these 27， all of which would lead to an improvement in your objective function。

Now， again， in 2D， you don't get an appreciation for this。 right。

 It's kind of like there aren't many ways you can go。 But in high dimensions。

 there can be lots of different interactionss you can go。

And you have to decide if there's 27 improving edges， which one do you follow？

So the choice of which edge to follow out of many improving ones is known in this context as a pivot rule。

 so you have different flavors of the simpleimpx method depending on how you instantiate the pivot rule。

So the result of spielman and Tang is for one particular choice of the pivot rule。 Again。

 as far as I know， there is no smooth complexity result known for any other choice of a pivot rule。

 Not because people think it's false。 Just again， it is resisted attempts of analysis。

 This is sort of hard enough， okay。So let me tell you a little bit about the pivot rule。

The pivot rule is called。The shadow pivot rule。Which I have to say， if you had practical。

 from a practical perspective， if you only had an analysis of one pivot rule。

 you probably wouldn't choose this one， but it's cool。 It's cool enough。So here's what you do。

So we observe that simplex is pretty easy in two dimensions， right？

So the idea is just to project your high dimensional polytope down into two dimensions。 All right。

 so you have this high dimensional， like an end space。

 and imagine you sort of like hang a light source from above it and then you look at the shadow that it casts on the ground。

Okay， so that's a picture that looks something like that。Okay。But we'll pass around。

So when you hang this light bulb behind the polytope and you look at its shadow。

Some of the vertices will still show up in the shadow， but some will disappear。

 Some will get swallowed up into the interior。 so there's no new corners in the shadow。

 Every corner in the shadow is a corner in the original polytope。

 but you will lose some of the corners of the original polytopap。Okay。So the idea then is like， okay。

 well why not just project it down into the plane and then run simplex in the plane because simplex in the plane。

 we talked about it if you only have M half spaces， you're going to have M edges。

 so you're just going to zip through there in linear time？Well。

 the problem is this doesn't quite work。 O the reason this doesn't quite work is， you know。

 it's true that if， if the constraints are originally specified in the plane。

 you're only going to have one side。Okay。Per constraint。

But if you have just a small number of constraints in high dimensions， like the hypercu。

 and then you hang the light ball behind it from the wrong angle。

 you'll actually see an exponential number of corners down in the plane。 Okay so basically。

 you'll still have most of the exponential many corners in high dimensional space。

 you'll still have that in the projection。 So just because you reduce it to two dimensions doesn't mean you suddenly get a free lunch and can just zip around。

 I mean， it will be linear time and the number of facets down in the plane。

 but that could be exponentially large。😊，Okay。So， technically， then。Here's here's sort of。

 the hard theorem that Spman prove。They prove that the expected。

Number of vertices were equivalent in two dimensions， number of sides。Of the shadow。Its polynomial。

In n and one over sigma。Okay。And so actually， the way they prove this and the way a lot of these smooth analyses work actually is sort of a nice instantiation of something I told you a long time ago when you're talking about parameterizing algorithms。

 One of the many reasons I gave you of why you might want to parameterize the running time of an algorithm is it sort of suggests an approach to explaining good empirical performance。

 right So first， you say， oh， well， you know， for certain die of this parameter。

 this algorithm runs fast。 And now real world data in some sense has has nice values for this parameter。

 Okay， and this works exactly in this way。😊，So if you're in two dimensions。And you have a polygon。

 and you're just trying to figure out how many facets there are。

Suppose I told you something about the angles。Between two consecutive sides。Okay。

So that angle is going to be less than pi。Okay。And as you traverse this polygon， in total。

 it's going to be like a two pi rotation。Okay。So if I told you that each one of these angles was bounded away from pi。

 So not it was less than pi， but it was even like at most pi minus Dlta。

Then after two pi over Delta turns， you'd have made the full circle。Okay。So this minimum angle。

Between， you， between one of these consecutive sides and pi can serve as a sort of condition number。

 and it's straightforward to analyze the number of iterations in terms of that gap。Okay。

So what they actually prove。Is they say， consider the biggest。Delta。

Such that all angles of the shadow。All at most pi minus delta。Okay。

Then what they actually show is that the expected value of pi。

It is now bounded below by something that's。At least inverse polynomial。And one over sigma。Okay。

So the number of turns you'll take walking around the polytope is the most two pi over this。

 so that's the most polynomial in in and one over sigma。Okay。So that's sort of the gist。

And we'll see this same template reoccur in you know for other applications which are both pretty cool。

 but also that I can actually teach you fully in lecture where it'll have this same spirit。

 we'll say， okay， the running time of say， local search is bounded by a polynomial and these various parameters and as long as there's a small perturbation。

 these parameters themselves are polynomally bounded and that'll give us the final result so we'll start that in earnest on Monday。

 see you then。