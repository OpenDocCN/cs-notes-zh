# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p06 -06-Lecture 6_ Generalizations of Maximum Flow and Bipartite Matching).zh_en -BV14CAUeUEPj_p6-

All right， so two orders of business today。First order of business is to finish the Hungarian algorithm。

 this is for the minimum cost bipartite perfect matching problem。

 so I'll remind you where we left off Tuesday and then finish that up and then the second half of the lecture I'm going to give you a survey。

Of some problems which are more general than the ones we've studied so far。

 maximum flow and bipartid matching which also have efficient algorithms along the lines that we've been discussing okay so a few other problems I just want you to know they exist。

 they're solved using techniques similar to what you've learned so far in this class。All right。

 so let me page everything back in for you from Tuesday。

So what do we do so we're talking about the Min cost perfect matching problem and so again the first thing we did is structural not algorithmic。

 we wanted to know how do we know when we're done， how do we know if a perfect matching really is minimum own cost。

So that motivated an optimality condition。And so the automatic condition says that a given perfect matching is minimum cost if and only if。

There's no negative cycle。 Let me remind you what a negative cycle is。 Okay。

 so it's a bipartite graph。 So every cycle in the graph is going to be even。So first of all。

 a negative cycle has to be alternating okay so every other edge is in the matching。

 every other edge is out of the matching， that's of course as many edges as you could have from the matching in the cycle。

And then what does it mean to be negative， It means that the edges in the cycle that are in the matching have higher cost than the edges in the cycle。

 which are out of the matching。 So here's an example。 this four cycle。

 the pink edges are the matched edges， the edges in have cost 7。 the edges out have cost 5。

 So that would be a negative cycle。It's easy to see that the only way it could be minimum cost is if there's no negative cycle if you give me a negative cycle I can just toggle the edges in that side that cycle。

 I get a new perfect matching and its cost is strictly less than the one we started with so it's certainly necessary for optimality that there's no negative cycles but it's also sufficient that's the hard direction which is that if there's no negative cycles then in fact you really are minimum cost so we proved that last time。

So then we started thinking about， okay， how do we actually come up with an algorithm to compute a minco matching。

 okay， we know what we want the termination condition to be。

 we know the termination condition should be no negative cycles， but how do we get there efficiently？

And following the same strategy that works so well for maximum flow。

 especially in the push rela lecture， we're going to have some invariance which our algorithm maintains at all times so that those invariants imply the optimality conditions Okay so this isn't an algorithm but it's guiding us closer and closer to an algorithm okay。

 it reduces the algorithm design problem to just maintain the invariance and compute a perfect matching subject to them。

So what were the invaris？That we were going to maintain， so first of all each vertex has a price。

 so it's called P of V。This could be positive or negative。And then with respect to prices。

 every edge has a corresponding reduced cost。Cp of the edge。

 which is just the original cost minus the prices of its endpoints。 so that's the reduced cost。

 Both of our in variants about these reduced costs。The first one is that just every edge。

 whether it's in the matching or not should have non negativeative reduced costs okay so we don't allow negative reduced costs Secondly。

 for the edges that are in the matching， we insist on something stronger that the reduced cost is actually zero the minimum possible and so those edges are called tight if you have reduced cost zero。

What's the motivation for these invaris， Well， as we proved last time， if you satisfy these invaris。

 then there's no negative cycle。 Okay so what we need to do is compute a perfect matching so that the invariants hold。

 and then we're going to be done that's sort of the algorithmic problem we're going to focus on。

I also told you Tuesday what sort of the main loop of the algorithm looks like and what are the two different types of updates which are going to happen in each iteration of the main loop。

So obviously we're going to keep looping as long as our matching is not perfect。

 we're going to keep trying to increase the number of edges in our matching one at a time until we get to a perfect matching。

So one good case is if we find a good path， I'll tell you what that means in a second。

 but a good path allows you to increase the size of your matching by one without screwing up the invariance。

 What do you do， you just toggle the edges in the good path more on that in a second and then if we fail to find a good path what I'm going to prove to you today is that we'll find what I was calling on Tuesday a good set and if you have a good set then you have this particular update of the prices which makes progress in a certain sense。

So it should be clear that this can only happen n times remember n is the number of vertices on both sides of this biparttheite graph。

 perfect matching has n edges， each good path augmentation increases the number of edges that happens only n times it's not obvious。

 but what I'm going to show you is that this second step this price update can only happen n times at most until we find a good path。

So this happens at most n times in between each two times this happens， this happens at most n times。

 so that'll be an n squared iteration bound， as you'll see it's not hard to implement each iteration in linear time okay。

So at a high level， that's what we're going to be doing。Any questions about？That review。Okay。

So let me remind you what a good path is， so it's sort of by definition what allows us to increase our matching size without screwing up the invariance。

So， and this is sort of the picture you should have in mind。 if the pink edge is in the matching。

 then the blue edge could be a good path。So first of all。

 both of the two endpoints of the path should be currently unmatched。 Secondly。

 they should be on different sides of the graph， so the starting point is on the left side。

 the ending point is on the right side， both are unmatched。So if you think about it。

 that means the length of this path has to be odd because it keeps bouncing back and forth between the left and the right hand side。

 if it ends up on the right hand side， it has an odd number of hops。

The second requirement is that it's alternating。So again。

 the edges alternate being out of or in the matching capital M。 And because remember。

 both the endpoints are unmatched， Def that first top and the last hop are not going be in the matching。

 So if you have a nine hop path， you're going to have five edges out of the matching and and then four edges in the matching。

Finally， all of the edges of the path should be tight， should have zero reduced cost。

 what's the motivation there well we want all of the edges on this path to be eligible for membership in the matching and remember we have this constraint then anybody in the matching better be a tight edge okay？

So if you ever find a good path。Then。You do that first part of the while loop so you take the X or the symmetric difference of your current matching and this path so if you had like this nineh path you'd be kicking out four edges。

 the ones that were already in the matching and in the path and then you'd be putting back in five edges。

 the ones in the path which are not in the matching that would give you a matching with size strictly bigger。

 strictly more edges and you don't screw up the invariance why not well you haven't changed the prices so you haven't changed the reduced costs so invariant number one's fine。

You've put some new edges in the matching， so that could scrub variant number two， but by definition。

 all the edges in the path are tight， so that variances fine as well。So what I want to talk about。

 and this is the first kind of new stuff compared to Tuesday is how do we find a good path or you know。

 how do we do a search for one？Okay， so any questions before I talk about that？

So I'm going to show you a linear time algorithm that strives to find a good path and if it fails。

 it's going to find what we were calling a good set on Tuesday。可。Alright， and don't be scared。

 This is really just gonna be like B， F S breath for search with a tiny twist。😰，In fact， you know。

 before I actually describe the algorithm formally。

 let's just kind of follow our nose and if we just go through an example I think will be obvious what the algorithm has to be。

So imagine the following。So imagine we're at some point in our algorithm， so we have current prices。

 P and we have a current matching M。So what I'm showing here is the tight edges only。

Only of the edges with zero reduced cost。 The graph may have many more edges and might have lots of edges that have strictly positive reduced cost。

 This is the graph only of the tight edges。So remember the graph with all of its edges。

 we're assuming has a perfect matching， but that certainly doesn't imply that you have a perfect matching just consisting of tight edges。

 so like this one clearly does not have a perfect matching because node 4 is isolated。

 but this is totally something that might come up in the middle of the algorithm， okay。

 a subgraph of tight edges that looks like this。And maybe this is our current matching， say。

 of size of three edges， matching six of the eight vertices。So using this as a starting point。

 we now want to say， okay， how would we search for a good path？OkaySo first I mean。

 so just to know where we're going， is there a good path in this example？There isn't。

And so the one way you could see that is， you know， if there were a good path。

Then you could augment this to a matching with four edges， which would be a perfect matching。

 but obviously there's no perfect matching just of the tight edges because vertex 4 doesn't even have any edges incident to it Okay so just you know we're going to be doing a search for a good path clearly this search is going to fail So we're interested in you know what happens when this algorithm fails。

Okay。So。What would be， let's just follow our notes。

 like what would be kind of like probably the first thing you might try about finding a good path。

Well， you know the two endpoints should be unmatched。 Okay， so just pick。

 say the first unmatched node from capital V。 so let's say we start here， different color。Right。

 so three is unmatched。And we're going to do BFS with a twist from node 3。

The reason we need to twist is because of this condition too。

 we want to make sure that we find a path which is alternating， okay so that'll motate the twist。

But first we just start with BFS， so we just say okay， and again。

 we're only searching on the tight edges remember， because we want a path which is all tight edges。

 so we only search on the tight edges。We started three we say， who are three's neighbors。

 let's go explore them？Okay。So level one of the BFS tree， so that's going to be level0。

 levell 1 is just the neighbors of the starting point。Okay。Now。

 what if either two or seven was unmatched？What could we say？We'd be done， right。

 we have a good path， we have a one hop， good path。So its endpoints are free。

The edge is not in the matching， and it's a tight edge because we're only searching on tight edges。

So if two or seven is unmatched， we can just stop and return the good path。 remember。

 we're happy when we find a good path。Now， in this example that's not true。

 neither two nor seven is unmatched， They're both matched。So here's where the twist goes。

 and again this is to ensure the alternating property。So。In every even level。

 what we do is we only put the nodes there that were matched to the nodes in the previous level。

 the vertices in the previous level。So what we're going to do。So because two is matched to one。

We're going to put a one here， and because seven is matched to eight， we're going to put eight here。

是。So conspicuous in its absence is node6。Okay。So if I was doing normal BFS。

 six would also be a child of two。Okay。Why am I not doing that because then I would have a path in the tree which was not alternating where both of the edges in a row were out of the matching and we want alternation okay？

So we do a BFS level， then we just look at who they're matched to if anybody。

 we put those to the next level， and then we switch back to BFS again Okay so we just interleave those two different steps。

All right， so here， well we get stuck at eight。Right。

8's only neighbor is seven and we've already seen seven。One we're not stuck。

 so one has two neighbors， two and five， we've already seen two， but we haven't seen five yet。

So we put five on level three of the tree。Now let me ask you。Suppose that five was unmatched。

That would also be great， we'd also be done actually， think about it。

So it wasn't just like if a level1 node was unmatched we good， if this level3 node is unmatched。

 we're also good。Why， because the path in the search tree from that node back to the root is a good path。

So by construction， the two endpoints are both unmatched， by construction of the tree。

 every path in the tree alternates edges out of in the matching， and again。

 the tree only searches tight edges。So if five was unmated， we'd be done。

 we'd have a good path we'd stop。Now five is not unmatched， it's matched， namely to six。

And now at this point， we're stuck。Okay， six his neighbors are two and five。

 and we've already seen both of them。 I， this is where BFS would just sort of stop。So we failed。

 we didn't find a good path， okay。So what's the algorithm more formally？So you just grow a tree。

Level zero is， let's say the first unmatched vertex。OfThe left hand side。

And then we're going to do something different as you've seen on the even levels and the odd levels。

 so for the odd levels， so the way we create you know an odd level from the previous even level is just by BFS。

So level I。For iO。Just do BFS。Again， amongst the tight edges only。From level I minus1。And again。

 as usual， if you've already seen some vertex in a previous level， you don't include it again。

 like a normal breath for search。And then in an even level。

What you put there are the vertices that are matched。s a vertic season level。I' minus-1。Okay。

And then， you stop。If you ever find。Unmatched vertex。Okay。Does the algorithm make sense？

I feel like you could code that up in Python easily enough？So before I era this couple announcements。

 so exercise set number three I just posted right before class， problem set number one。

 as you know is due Tuesday at midnight and you might want to review the course homepage for the late day policy so there are late days but they're pretty limited so have a look at the official course policy。

All right， so' everyone with me so far， so we have this now subroutine that may or may not find a good path。

 We actually trace through an example where it doesn't。

 We agree if it ever ends if it finds it on match vertex we have a good path we're done Okay。

 no problem。So what I have to do now is I have to show if this algorithm gets， stuck。

 the subrine gets stuck， we can extract from it some other way of making progress。

Everyone everyone clear up to that？Okay。So let's think about， you know， in general。

 So here we have a particular search tree where this algorithm got stuck。

 Let's think about what a stuck search tree looks like in general。So here's an important point。

And this is where we actually use the assumption that it's a bipartite graph。

 remember I promise that has to be important somewhere， so it comes up in a subtle point right here。

Here's the claim。Okay。I claim that if you think about any matched edge。Okay so any pinkage， either。

 it's not in your search tree at all， meaning you didn't find either one of the endpoints。Or。

Both of the endpoints are found and in your search tree。And moreover。

 the two endpoints of that matched edge have to appear on consecutive levels with the first level being an odd level。

And you can see that up here， right the match edges go from level 1 to2 and from level3 to4。

And the claim is that's going to be true generally。

 any matched edge with one endpoint in the tree actually has both endpoints in the tree。

 The first vertex at an nod level， and then the other vertex at the next level。

 which is going to be even。Okay。So why is this true， Well。

 also assume you have a matched edge and you hit one of its endpoints。Okay。

So consider the first level where you find one of the endpoints of this match edge。

So the big question here is， why can't you encounter both endpoints of a mashed edge？

At exactly the same time， in the same level。 So， for example。

 what would be what if 2 and 7 were actually matched。Up in that upper right corner。

 then this would be false。Then it wouldn't be true that the endpoints were in consecutive levels。

 they'd be on the same level。So how can we be sure that there isn't some match edge between two and seven？

Good。So that would give us a triangle。If there was an edge between two and seven。

 we'd have a triangle。That's an odd cycle。And biparttheite graphs can't have out cycles。Okay。

And that's true in general。 so if you ever encountered both endpoints of a match edge in the same level。

 then you'd trace back the two paths back to the root and that would trace out nod cycle that doesn't exist so that can't happen。

So that's the where we use the bipartid assumption。

 When you find one end point of an edge for the first time。You don't。

 have not seen the other endpoint yet。Okay。So I guess other thing I need to argue is why couldn't it be consecutive levels where I is even？

But you think about it， that doesn't make any sense because every vertex at an even level bigger than zero is already matched to somebody on the previous level。

You can only be matched to one person， so if you're already matched to someone on the previous odd level。

 you can't be matched to someone on the next odd level。Okay。

 so that's why the first endpoint is always going to be seen at an odd level。

Even levels are always matched to vertices at the previous odd level。Okay。

So questions about that claim。So again， let me just to emphasize。Yous where to use the G as biids。

So you can't reach。VW in the same。Well。Okay。All right。So suppose we get stuck。Oh。

 so I guess just to review， so this also kind of hammers home the point that if we ever find an unmatched vertex。

 then we're home free。Okay。So notice that if we ever find an unmatched vertex。

Where' is it going to be， going to be a nod level， or is's going to be an even level？

Like where's the first place we could find an unmatched vertex， which level？

Level 1 right so we could find one on level1 and more generally in any odd level we could find one why can't we find an unmatched vertex at an even level other than level 0 because by definition。

 all vertices at an even level are matched to a vertex at the previous level。

So unmatched vertices are only at the odd levels。Which means the path from an unmatched vertex back to V is going to have odd length which is what we needed。

 of course it's going to be only tight edges and again by construction every path in the tree is alternating。

So what we need to understand is what's up when the algorithm gets stuck。So let S。

Be the vertices at odd levels。K。The claim。Is that N ofS， so let me remind you what NFS is。

I defined this last time。So NFS is just the neighbor set of S so you just take the union of all the neighborhoods of vertices and S。

 but remember we're doing it only for the subgraph of tight edges。

 so N ofs is the vertices on the right， reachable by a tight edge from a vertex in S。

So the claim is the neighbors of S from tight edges are exactly the vertices on odd levels。Okay。

Oh sorry， yeah， I said this twice。Actually， what I mean is this should be even。Thank you。

So as far as this picture is concerned。That's S。Okay。

And the claim is that the vertices that are reachable from s by a tight edge are exactly2，7 and 5？

So why is that true， Well， so why is this quality true。

 We'll consider about the two different inclusions。So certainly any vertex in an odd level。Is an NFS。

Because how did it get in the tree at a oddd level。

 it has to be adjacent to something at an even level via tight edge。

So what we're concerned about is that there's some neighbor。

 so some vertex of NFS that somehow we didn't find when we explored in our search tree。

So do you see why that can't happen？You see why it is that every single vertex adjacent to somebody and asked by a tight edge has to show up in the tree？

I hear some proposals。Good， that's all。It's just BFS breath research， okay？So breath， you know。

 any kind of graph search like this， it finds everything sort of findable and remember at the even levels of this search procedure。

 which is where it's starting from the vertices at S。

 it explores everything it adds all the neighbors。Okay， so so what is an odd level。

 it's all the neighbors of the previous even level that you haven't seen yet。

 so that's why there's no way there's going to be some vertex antis that you don't see in the tree。

Okay。All right。Now I have everything lined up so that I can explain why you can only get stuck with a good set。

So I have to remind you what a good set is。So this is just the same definition from last time。

So it's a good set， it's a subset of the left hand side。So that first of all。

 it has at least one unmatched vertex。We know that's true， the root of the tree is unmatched。

And secondly， it should be that all of the neighbors of S。Are already matched to a vertex and S。Okay。

So like in this picture， it's asserting that 6，1 and eight should be matched to vertices in the odd levels of the tree。

 which of course they are。And that's going to be true in general。

Because why did a vertex wind up at an even level by definition。

 because it's matched to a vertex at the previous level。So all of the or so to put it differently。

 every vertex at the odd level has to be matched to somebody at the next level。

 Otherwise that would have been an unmatched vertex and we would have stopped。Okay。

So any questions about that， everyone agree that these two properties hold when you get stuck in the search algorithm。

Okay。All right， so this was the definition I gave you。

 and I explained on Tuesday how you do an update when you find a good set， let me just remind you。

So for all V on the left hand side， you increase。The price by some amount Delta。

For everybody on the right hand side， you decrease。By the same amount。Okay。So we have S。

 we have N of S。Every vertex of N of S is already matched to somebody in S。

There might be other unmatched tight vertices。So how do we pick Delta。

 We take Delta as large as possible， subject to our invariance。

 What could go wrong with our invariance。 Well， we have invariant number two。

Varian number two says so we're changing the prices's a little bit dangerous right。

 we're not changing the matching， but we're changing the prices， so we're changing reduced costs。

 so if we had any edge in the matching which went from non from tight to nont。

 that would violate in variant number two， so that better not happen。

 but remember our property about these match edges and trees up in the upper left。

 either both endpoints of a match edgeger in the tree or neither one is。

So either both of the prices stay exactly the same or one of the endpoints goes up by Delta and the other endpoint goes down by Delta。

 which means that the sum of their prices stays the same。

 which means the reduced cost stays the same。So that's why variant number two doesn't get broken。

 Every matched edge either has neither price affected or they're affected in opposite directions about the same amount。

So the only embryovari you might break。Is invariant one。

That all of the reduced costs are non negative。So how could it be that a reduced cost becomes negative？

Well， for that， we want to think about an edge which is not tight。That looks like this。Okay。

 an image that has strictly positive reduced cost。 Again， remember。

 everything we've been talking about has been about tight edges。

 The non tight edges have been invisible until this very moment。

So now let's sort of think about putting the non tight edges back in the graph and notice that for an edge with one endpoint and S and the other end point outside of N of S。

Well now one of its prices is going to get raised by Delta。

 the other endpoint's price is going to be unchanged， so its reduced cost will drop by Delta。

 reduced cost is going down as we take Delta larger。So if take Delta larger enough。

 that might go negative。 and that would break our first imp period。

So we just raise Dlta until a new edge becomes tight， a new edge has reduced cost zero。Okay。

So we choose Delta so that this now becomes tights。Okay。So now we see a sense， so is that clear？

So that's how Delta gets chosen。 and Delta， we chose it so big so that it zeros out。

 Some's reduced cost。 And we argued last time why there has to be some edge that gets zeroed out because G contains a perfect matching。

So now， what I owe you is an explanation of how was this progress。

 We haven't changed the matching at all。So that's the most obvious measure of progress。

 which we're not satisfying。But here's the thing。Right，So remember， what is S and N of S。

 Those are all of the vertices we encountered in some search tree， starting from V。Next iteration。

 with our new subset of tight edges， we're going to restart this search again from V。

So what can you say about the search tree we're going to encounter next iteration versus the one that we got stuck on this iteration？

It's going to make more progress。Right。So all of the edges in the tree。They're still tight。 Okay。

 they're still there。 The matching is the same。 All the reduced costs are still zero for all the edges in the tree。

 Remember， the two endpoints get increased and decreased to cancel each other out。

But now the search is not going to get stuck where it did before， because here's another vertex。

 which we're going to find。On an even level。And so that from it。

 we're going to be able to do BFS and hit one more neighbor。Okay。

 so the upshot is because we have this new tight edge going to some vertex， not in NF S。

 our next search tree will have at least one more vertex than our previous one。Well。

 a search tree can't possibly have more than all of the vertices。

So we can't do this price update more than n times。Without， in the meantime。

 doing a matching augmentation without finding a good path。Okay。

So that's basically the entire analysis of the algorithm now。Whatever we argued。

 so surely you only find a good path at most end times because the matching can only have size n。

We just argued how you can only have n price updates between good paths。

 the reason being that the search tree grows by one with each price update。

And I'm not going to go it through it in detail， but hopefully it's sort of intuitively clear that each iteration is going to run in linear time if you implement it correctly。

 because again， it's just really BFS with a twist。Okay。So the final runtime。Is O of M。

 this is the running time per durationeration。Times n squared。Okay。

And this is actually exactly the running time and the analysis that was discussed by mons back in the '50s that I told you about on Tuesday。

So that's the Hungarian algorithm。Any questions about that？So again， maybe just to recap。

 what actually is the algorithm？So I sort of gave it to you piecemeal。

 so maybe it's hard to keep it all in your head at the same time。

 so you maintain a matching initially empty， you maintain prices， initially zero。

 you have these invaris， you have this while loop。Each while loop you have is a subroutine。

 this search tree procedure。Okay， where you interleave BFS searches with just adding the matched edges。

If you find a good path， you augment the matching， go to the next iteration of the while loop if you don't。

I showed you how to find a good set， taking the even nodes of the tree and the odd nodes of the tree。

 the dual update is add Dltas to the left， subtract Dlta from the right， go as much as you can。And。

And yeah， so that can only go n times until you have your next documentationation。Okay。

 so that's the whole that's the whole algorithm， just this one while loop within the search procedure each time。

 and then either the X or of the matching or this dual update。对。Practice do we actually。

It found it seemed like they were very loose。That's a good question so the question is is the analysis tight and in the worst case。

 I'm pretty sure this is tight so if you allowed me to come up with the arbitrarily devious graph and edge costs I think I could force it to be this way。

Now on the problem set number two， you are going to explore faster implementations。

 which are faster both theoretically， but it's also。

 you like we're using no data structures at all to prove this bound right so independent of you know what happens in practice。

 I mean even just it's obvious you'd like to do know some smarter data structure work to speed up this algorithm。

So there's a couple of ways to do it。There's a couple pretty simple ways to get this down to NM login。

Okay。And so one way to do this is just to use heaps in a smart way。

 a different way to do this is sort of a slightly different algorithm where you basically just run Dykster's algorithm n times in a clever way。

 so problems at two will step you through both of those two things。Okay。

So that's an ununggarian algorithm， any questions？All right。

 so the rest of the lecture is going to be somewhat less technical， a little more high level。

Which board do I want let's use this board？Okay， so we basically talked about three problems so far in 261。

Four problems if you count max flow and min cut as different problems。

 but let me count them as the same problem。So we started with MaxFlow。Man a is ST cut。

We observe that actually max cardinality biparttheid matching。Reduces to max flow。

So the arrows here are going to mean become harder。

 so any problem further up reduces to a problem that itp points to。

Then what we just discussed was minimum cost。Pparttheid matching。

So that obviously includes mass cardinality as a special case。So this is what we've covered so far。

So some things you might be wondering are。Is there a nice common generalization？Of these two leafs。

 so of max flow and of min cost byheid matching。And there is。

So I want to tell you a little bit about max Mincos flow， excuse me。So again。

 that's a common generalization of max flow。Min cost bypartid matching。

Another thing you might be wondering about is what's up with matching in non bipartite graphs。

Very reasonable problem。So non biparttheite matching。Obviously includes bipartite as a special case。

And then， of course， if you really want to be greedy， you could also add costs。

so you can talk about min cost。Non biparttheite matching。Which obviously includes。

The Carality case is a special case and includes the nonpartite， sorry， the bipartite special case。

Okay。So I want to give you just a brief sort of overview of these three pink problems for the rest of the lecture。

Any questions about the web？Alright。Yeah。So you know just as far as terminology。

 so there's this field called combinatorial optimization and you know that's what we've been studying these last few weeks。

 so that just means finding efficient algorithms which optimize over a collection of discrete structures。

And so these six problems augmented by two problems you already know a lot about from CS161。

 minimum spanning tree。And shortest paths， those eight problems， I think most people would agree。

 that's the list of fundamental problems in commercial optimization， that's a full list。

 there are other problems in the field， but I think as far as the most central ones after this lecture you will have seen them all。

Okay。So for these last slide I'm not going to be able to really tell you anything you know in detail about these other three problems so what are the takeaways So the first takeaway is just that these problems exist okay these more general problems。

 there are applications which are captured by these more general problems that aren't captured by the three I've told you about already Now these applications aren't quite as frequent as the three problems I've told you about that's sort of why focused on those problems。

 but still they're useful to know Mincosfo for example it's very useful to know that the problem exist and that there are fast algorithms for it。

嗯。Right， and so as far as so how fast， how fast can you solve these problems again， you know。

 it's not like breath for search。 It's not going be near linear time。

 but you can get running times for all of these problems。

 which are ballpared the kinds of running times we've been seeing so far。

 So there are algorithms with running time roughly n times M for all of these other three problems as well。

 So again， you know， millions of nodes might be a problem。

 But you can still counter pretty big graphs。So theyre efficient algorithms and then the third takeaway。

 which you're just gonna to have to take it on faith。

 is that these algorithms and the way that they're analyzed follow exactly the same recipes that you've been learning in 261 so far so you're very well positioned to study these problems in detail in a different course or on your own if you ever need them Okay so again。

 one talks about optimality conditions one sort of talks about augmentation subject to invariance and so on Okay it's the same ideas just kind of a little bit a little bit to the next level。

All right， so min cost flow。There's a few different equivalent ways to formulate this。

 but let me just give you one。Specific formulation。So just like in Maxflow。

 you have a directed graph， you have a source， you have a sink。

The way I'm going to specify it there's a target value， flow value D。

 so the feasible solutions to this problem are going to be the flows that push D units from S to T subject to the usual conservation and capacity constraints。

And so for all edges in E。Have a capacity。Which is not negative。And the cost CE。

Which can be either positive or negative， doesn't matter。And what's the goal？The goal is。

To minimize the cost of the flow， what's the cost of the flow where you look over all the edges？

You look at how much flow uses an edge。And you look at the per unit cost of sending flow on that edge。

Okay。So among all flows that push D units from S to T。

 you want the flow that makes this number as small as possible， or if there's no flow of value D。

 then you should correctly return that fact？So notice we already know how to compute to figure out whether or not there exists a feasible solution。

 we can just run max flow in this graph and see if the max flow value is at least D or not。

 so that tells us if it's feasible or not。The goal here is to actually optimize over the feasible solutions。

So just。I'm not going to have time to talk about detailed applications of Min cost flow。

 I might put one on a problem set。But just to help you appreciate this problem， let me notice。

 let's notice some special cases。 Its actually captures simultaneously three different pretty interesting problems。

 which is pretty cool。😊，So first of all。The shortest path problem。

Like you studied in Dytra's algorithm。So you have a source， you have a sink。

 I want to know what's the length of a shortest path from S to T。So how would you。

 if I gave you as a black box， a subroutine that computes Minco flows。

 do you see how you would use that， you just use it once to as a black box， give you a shortest path？

So the costs are going to stay the same right but in min costs so how would this work you have this graph you want to compute a shortest path from S to T so what's clear is you're going to feed the black box exactly the same graph exactly the same S。

 exactly the same T exactly the same edge costs so the only thing you have to do is sort of give every edge of capacity so that it type checks for the minco flow algorithm it's expecting an input with capacities。

Just give whatever capacities you want， give like every edge capacity one， for example。

What's the Minco flow going to be， Oh so D， by the way， so the flow value you can just set to one。

The Minco flow is going to find the cheapest way to to send one unit of flow from ST。

There' there's no binding capacity constraints， so it's just going to pick a shortest path to do it。

Okay。That's all just six capacities to one， invoke men cause flow， you get back a shortest path。

So Max flow is also can be thought of as a special case。

 it's a little awkward the way I formulated it， but still you can think of it this way。So Max flow。

 know your graph， you already have a graph， you already have a source， you already have a sync。

 you already have capacities， presumably you just pass those in the Minco flow， black box。

 but you need to set the costs。So how should we set the costs so that a type checks for them in cost flow subroutine？

The simple going to do is just set them to zero。Okay。

And so now what is the main cost flow7ine going to do。

 it's going to tell you whether or not there's a feasible flow with value D。

That doesn't mean Co flow does。How do you said D， Well。

 you kind of want to say D to be the max flow value， because that's what you're trying to compute。

 which sounds circular， but then you're like， oh， dude binary search， no worries， right？

So D to be 100， run Minco flow， if it says there is a feasible flow of value 100。

 you double it to 200， if not， you have it to 50 and you search until you find the largest D so that there is a feasible flow。

Okay， yep， we are。Yeah， that's fine。So just in the same way that with matching， we were allowed to。

 I kind of assume them away， but it's basically without loss， you know。

 negative costs don't really mess up matching either。So I mean， there is so right， yeah。

So negative costs are fine。Okay， so that's how you get max flow。

And then this I put on exercise set number three。But Minco perfect bipartid matching。

 the problem we just saw with the Hungarian algorithm is also a special case of min cost flow。

And this is really exactly the same reduction that you saw reducing max cardinality bypartite matching to maximum flow that same reduction lets you reduce the min cost bypartite matching to the min cost flow。

Problem。But you should think about that you should think through the details in exercise I said number three。

Any questions about that？I mean， in Minco flow， it's just part of the input。place。It doesn't。Yeah so。

I mean， an equivalent problem would be to say among all max flows find more of minimum cost。

 a roughly equivalent problem， so you could do it that way too right so like in the min cost perfect matching。

 I said what if there are many perfect matching， which one do you pick。

 pick the one with the cheapest cost。You can also phrase in cost flow that way， too。

 so find a max flow。 But if there's many max flows， find the one with the minimum cost。

Sometimes it's convenient， sometimes you're not really trying to maximize the flow。

 you really just need to get a certain amount of stuff from point A to point B。

Like you think about it， that's a pretty sort of basic problem。

 you're just like putting stuff on trucks to ship from your factory at all these different places。

 and you want to do it as cheaply as possible， and then you kind of have a D。

And then the thing which is maybe a little subtle， which is sort of glossed over。

 is this question about how would you use this as a black box to solve any of these problems？

The black box is expecting a D。 So in any of these， you better set D to something。Shortest pass。

 you can just set it to one max flow， you kind of want to do binary search on D Minco perfect matching if you think about it。

 you want to set D to be equal to n because you really want to sort of if you go back to that reduction then we talked about for bipartite matching。

 you really want something which saturates all of the edges out of the source and all of those were unit capacity edges So here D is going be equal to n。

So。嗯。😊，T how to deal the case when theres negative age。That's correct。

 you have to handle it directly。So the algorithms have to actually。I mean。

 so you don't do a reduction to the non negative case。他的他说要上。So a negative is so good。

 so one of the things I'm gonna ask you to think about in Pro set number two are the optimality conditions and again you've seen in a number of examples。

 different problems of different optimality conditions。

 but they're usually very natural and actually from in cost flow。

 the optimality condition is that the residual graph once you extend it to have costs should not contain any negative cycle。

So if you have a negative cycle in the residual graph。

 it gives you a way to replace the current flow with a cheaper flow。

 and then the hard direction in which you have to prove is that if there's no negative cycle in the residual graph。

 actually you're guaranteed to be optimal。So you just deal with。 So it's a good question。

 You just deal with negative cost directly as part of the problem。 And negative cycles。

 they're actually not a problem， right So for shortest paths， So if edges had infinite capacity。

Then a negative cycle would be a problem because you could get negative infinity costs just by pushing flow around the cycle over and over and over again。

 But if you have finite capacity on every edge，Negative cycles aren't a problem。

 they're just an opportunity for improvement， there's just an opportunity to have a better flow。

Which you're fine with。Good questions， Other questions，我 coming nice。No， FE Time CE， yeah。

I don't know what's clearest。Yeah。Right so problems in number two I'll ask you to think about optimality conditions。

 so no negative cycles characterizes optimality， I'll also step you through the analog of Ford Fkson。

 so just what's a simple augmentation based algorithm guaranteed to terminate with no negative cost cycle in the residual graph so that'll just give you nothing nothing too crazy。

 but just give you a feel for the basics of the problem。不。give it第我 give you个。L。It should be， yeah。

Nothing above D。 Yeah， so I mean， if you think about it， right， So like， suppose， right， I mean。

 so one way to see why this isn't a big deal， suppose we had a flow network， no cost。

 just a flow network。 And I just wanted to know if there's a flow with I D， find me one。

Or tell me that there isn't one。There's a very simple way to solve that problem just by a very simple reduction to the normal max flow problem。

Which is you just take your source， you add an extra source， an s prime。

 you connect S prime to S with an edge of capacity D。Okay。

 so now when you run MaxFlow in this new network。Where you have。RightSo suppose in this network。

 you either want to find a flow with value exactly D， or you should tell me that there isn't one。

Then again， what I'm going to do is I'm going to add s prime here。

I'm going to add something with capacity D there。If there was a flow of value。

 at least D in the original graph G， this computation will give me a flow of value exactly D。

 if there was no flow with value D before， there's not going to be one now either so I'll correctly deduce that effect so the exact versus maximum thing isn't really a big deal。

Yeah， it's a fair question though。Other questions？So that's actually all I was going to say about midtco flow。

But again， you'll see some more about it on problem set number two。Oh yeah。

 the other one thing I was going to just say about this web right so I mean just to help you understand how much of these are the natural sQel of what we've already talked about and how well you're equipped you are to do them。

 I mean if we had a semester instead of a quarter， I would just teach you those in the next four lectures but it's time to move on the linear programming next week so I'm not going to do it okay but it's really they would fit very。

 very nicely in what we've been talking about。All right。So any of other Minco flow questions？

Those want to talk a little bit about non bipartite matching。Questions。Okay。So nonbipartid matching。

So the input undirected graph。Arbitrary undirected graph， not necessarily biheid。Of course。

 a matching， the idea of a matching makes perfect sense in a general graph。

 just a subset of edges with no shared endpoints。So you can certainly talk about finding the maximum size。

 the maximum cardinality matching in a general graph。So for example， what's the max weight， sorry。

 the max cornality matching size and a five cycle？Not a trick question。Is there a perfect matching？

No， there's a odd number of node， of course there's not a perfect match。

So there's only there's five nodes so you can match most four of them with two edges。

 and of course that's possible。Okay。To opt equals2。And in general。

 odds cycles are the simplest possible non bipartite graphs。 Okay。

 so they already sort of illustrate。The issues with a nonbipartite case， and I should say， you。

 a priori， it's really not easy to see whether or not this problem should be polynomial time solvable or NP hard。

Really opera。 There's no reason to expect this necessarily to be efficiently solvable。 It is。

 but it's really not easy to see it。ち去去。So it certainly appears harder than the bipartid case。

 for example， there's definitely no natural reduction known from nonbipartite matching to the maximum flow problem。

 for example， so it really seems like a new problem， a possibly harder problem。

So I want to talk a little bit about the optimality condition。Which is quite beautiful for matchings。

So how do we know when we're done？So given a matching on a non bipartite graph。

How do we know whether it's maximum cardinality or not？So for example。

 how would you prove to me that some non bipartite graft does not have a perfect matching？

Remember Hall's theorem tells us how to do that in the bipartite case Hall's theorem says that a graph has a perfect matching。

 if and only if for every subset of lefthand side nodes。

 the number of neighbors it has on the right hand side is at least as large as it absolutely has to be right so if you have 10 nodes on the left they better have at least 10 different neighbors on the right if you ever fail that condition it's a convincing proof that you can't have a perfect matching。

But of course， this ho condition refers to a left hand side and the right hand side。

 so that doesn't even really make sense for a nonpartpartite graph。

So we need some other more general optimality condition。So think about the following graph。

So I'm going to take five triangles， right， so it's certainly。Not biheid。

And I'm going to connect them in a star。A pinwhe。So how big is optimal matching here？

How many how many edges can you get？So there's 16 nodes， so a perfect matching would have size8。

Six yep， I agreed， I heard it from a few people， excellent。Ot equals6 and this really， you know。

 this clam is both an upper and a lower bound to show you was at least six。

 I just have to show you the matching， So there's a lot of them， like here's one。呃。

So that's six pink edges。Why can't there be more than six。 Remember this is the hard part。

 How do I convince you that there can't be a matching of size7？Well。

 here's a way you could think about it。You can say， well， think about a triangle。Right。

So in most two of the vertices of the triangle are matched to each other。Okay。

 so the only way to match all three vertices of a triangle is to match one of those three triangles outside the triangle。

And here in this graph， that could only mean to the center。Okay。

 so any triangle with all three vertices matched has to be matched to the center。

Now the center can only be matched to one vertex。So four out of the five triangles have to have some vertex unmatched。

Okay， so you have 16 vertices， four have to go on match that leaves you with 12 that gives you a matching size of six。

So in general。This idea gives us a way to upper bound the size of a maximum matching。So， Lema。Okay。

And every graph opt the size of a maximum matching。Is it most the following？

Let me just write it down and then I'll walk you through it。All right， so I owe you a definition。

 what is OC？It's not Orange County。OECC stands for OD Comp。So what OC ofS says is the following。

 it says you give me a subset of vertices， I ripped them out of the graph。Okay， in general。

 this shatters the remaining graph in the multiple pieces， multiple connected components。

I look at the parodity of each of those connected components， they either a odd or even。

 and I just count out the number of those connected components that are odd。

 and that's OC ofS number of odd components after ripping out S。So for example， in this picture。

You want to think about just taking S to be the center alone？if I rip the center out of this graph。

 how many odd components do I have？5ive right， each of the triangles becomes a。

A component of size three。So if I choose S to be the center。

 what do I get on the right hand side here， I get 16？This is a five。And this is a one。Okay。

 so the5 minus1 here， the four， that's equivalent to where we said that four out of the five triangles have to have some unmatched note。

And so again， if this is the total number of nodes， this many has to go unmatched。

 then this is the number that this is sort of upper bound on how many can be matched。

 and then as far as number of edges you divide by  two。Okay。So the claim is this is true in general。

No matter what the graph is。So just a quick sort of already talked through it。

So what's the argument for all of the odd size components？A v minus S。Well， if you're odd size。

 you can't have a perfect matching internally， just like this triangle cannot be perfectly matched internally。

So at least。One vertex of this odd component。Is not matched。Internally。I看。

So that means there's at least OC of S such vertices。And if any of these are matched。

 they can only be matched to vertices of S。Okay。They can't be matched to each other。

So there's no way to match this vertex with that vertex because there's no edge。

 why is there no edge， because these were different connected components after I ripped out S？

So what does it mean that you're a connected component after you rip out S。

 it means all of the edges that stick out of this go to S， not to anywhere else。

So the only eligible vertices to match these two are in S。At least the number of components minus S。

Vertices go unmatched。And that gives us this bound。so again， if at least this many go unmatched。

 then most this many vertices get matched， which means there's at most that many edges。

So any questions about that？Yep。应个面你分好。That's right。also supposed of or can。

we can prove that it is incredible。Good， that's exactly where we're going。

 So we have proved that it's an upper bound。 That's what dilemma says。

So if there's anything unclear about the proof that it's an upper bound， you should ask。

So this upper bound is an analog of when， you know， back in lecture 1 or two。

 we had just proven that the max flow value isn't most the min cut value that any cut is an obvious upper bound on how big。

嗯。How big a flow could be。So for。Let me call this star。That's right hand side here。So what star is。

 star says well。Suppose we're just going to prove upper bounds on the maximum matching size using this simple argument okay。

 where we rip things out of the graph， we look at the number of black components and then that's how many that minus the size of what we ripped out is how many must be unmatched。

So star really says what's the smallest possible upper bound， I。e。 the best。

 the tightest upper bound， you can prove if all you do is think about these obvious obstructions。

 like in the pinwheel。And now what's totally not obvious is whether or not there going to be a gap。

Between star and the size of a maximum matching， whether or not， you know。

 there might be other reasons why the max matching is small other than just the obvious obstructions。

So really one of my favorite results in combinatorics says that actually there's never a gap。

So there always exists in every single graph， there always exists。

 a matching with size equal to star。So this is known as the To Burge formula。

And it says that equality holds。In thelemma。Okay。So Tuttan Bs are both sort of famous graph theorists from the mid 20th century。

So Tu in the 40s gave a characterization of which graphs not necessarily bipartite have a perfect matching。

 so he gave the nonbipartite generalization of Hall's theorem。

 and then in the 50s Burge observed that you can use the same idea to prove this formula to characterize the max matching size。

 whatever it may be。All right， so there are some pretty just like slick proofs。

 one page proofs by induction of the Td Burge formula， but I'm an algorithms person。

 so I really like to have algorithmic proofs。And so that first came along in the mid 60s。

A famous algorithm of Edmonds。Known as the Blossom algorithm。So this is from 65 and the main。

Sort of technical result in the paper is a polytime algorithm。For max cardinality。Nonbiheid matching。

 So this was in 65。Okay。So the proofs of the Tdbige formula were not constructive。

 They didn't give efficient algorithms。 Edmonds gave an efficient algorithm。

 And as a byproduct of his algorithm and analysis， he proves the Tdbige formula。

 So his algorithm actually concludes with the matching whose size equals the star there。

 So that shows that every graph there's always a matching。 so that。Aquality holds。So that's cool。

 That's an algorithmic proof of the T Burge formula。

 This paper is also sort of famous for this sort of almost throwaway section。

 which is called digression。The name of the paper is paths， trees and F。

So this is 65 and Edminds along with a couple other people independently was really the first one to propose that polynomial running time is a good definition of computational efficiency。

 Now mind you NPp completetan hadn't even been defined yet that was by cooking  Levin in 71 so this is before really complexity classes were being thought about no one had to defined P in order to find NP but Edmonds observed that his algorithm had running time end to the fourth and he said I think this is a good algorithm and let me propose as a definition of a good algorithm that the running time scales polynomial in the input size and he noted that brute4 search is not polynomial and he conjectured that problems like the TSP actually do not have any polynomial time algorithm。

 so back in 65 even though he didn't have the language he's conjecturing that P not equal to NP。

So it's a very fun paper to read。I'll post a link to it on the course site。And。Yeah。

What else did I want to say oh right， and actually。

 so again last year when I taught 261 I actually taught this algorithm。

 it was the 50th anniversary so it sort of seemed appropriate。

 but it took up two full lectures so I cut it this year to make room for some other topics。

 but again just to like prove the point this is something I could teach you in 261 okay so and you can study it on your own if it interests you。

😊，Okay。So that's the story for mass Carneality matching， TouchBr formula again， you know。

 so Edmund's algorithm was sort of the same kind of M times n squared。

 but sort of state of the art stuff gets more like n times M， even a little bit better。

 at least theoretically。All right， so now the hardest problem。So men cost。

Or equivalently max weights， non bipartite matching。And so here again。

 like the main thing I just want you to know is that this is still。A polytime solvable problem。

And glibibly， you might think， well。You know maybe I'm not surprised because Edmond's blossom algorithm tells us how to deal with the nonbipartite aspect and the Hungarian algorithm tells us how to deal with the costs。

 so let's just kind of like put them in a blender and we should get something that handles costs and nonbipartite。

And while sort of from 30，000 feet is sort of true。

 really like actually doing it is not easy okay so this I didn't teach in 261。

 I taught this in a 300 level class many years ago。

 so this again is due to Edmonds a little bit later than his unweighted case。

 but again it can be done okay。Actually， one thing I just wanted to say about the original blossom algorithm。

So what's the challenge right so why why is the nonbiparttheite case harder than bipartite Well actually we saw this toward the beginning of this lecture。

 if you remember when you were arguing about that search tree that we were growing in the bipartite case and we argued either we get a good path or we can do a price update and crucial to that argument was this point that it can't be the case that there's some matched edge currently matched edge so that we find both of its endpoints in the same level。

Okay， so we can't get both the endpoints in level1， for example。

 Why not that would exhibit a triangle。 It's bi partite。 there can't be a triangle。

In a nonbipartite case， this can totally happen so the way Edd's algorithm works is you actually do exactly the same search tree inter interleaving the levels。

 but then you have this additional big complication。

 which is sometimes you pick up a match edge that creates an odd cycle。

And really no one knew how to fix that for a while。

 but then Edmund's idea was he called it shrinking blossoms， so he called the odd cycle of blossom。

 and he contracted it into a super node and then recursed on the smaller graph。

 and he called that shrinking a blossom。And then basically， at the end of the algorithm。

 you have to undo the recursion and uncontract all of these things again。 So again。

 it's sort of an extra big idea on top of what we already saw for the flow algorithms。

And then in the min cost， max weight non bipartite algorithm。

So what's challenging now is that if you're using the blossom approach。

 you have these super nodes corresponding to contracted components。

 contracted odd cycles and somehow maintaining the prices on the vertices gets very complicated once you start contracting nodes so that those are the kind of issues that you have to figure out to actually make this work。

 but it can be done so there is a poly time algorithm， even for nonbipartite n costs and again。

 state of the art gets you around maybe n times M or so。So I do want to be honest， you know。

 we're talking about all these， you know often theorists equate polynomial time with efficiently solvable。

 but you know it's a little， you know the picture is a little more complicated And than that really depends on know how big your instant size is and so on So linear time is awesome right Like if it fits in main memory。

 you're probably fine， basically。YouAl with quadratic time。

 you start having some issues so something of size like 10 million probably fits in main memory。

 but that squared is not a running time you're really going to be able to handle okay？

These algorithms are almost more in sort of the cubic， cubic and the number of vertices。

 So for something like minco， nonbipartid matching。Up to maybe 1 thousand nodes。

 I guess you'd be fine， certainly like high hundreds。

 but once you were in many thousands of vertices， you'd actually have trouble solving those problems using this kind of algorithm machinery。

So this is the last point I'm going to make。Also on problem set number two。You're going to study。

 well， you know， so what if you have a really big graph。

 what if you have a million vertices and probably in your other computer science graphs classes。

 you've been given plenty of motivations for graphs with millions， if not billion of vertices。

So then you really say I need to run a linear time algorithm and maybe I'm willing to give up on finding the exactly optimal matching。

 I just want like a quite good matching and I want it near linear time okay so that' again that's very well motivated。

 it's very interesting and there's theory about exactly that question and again you're learning the tools that help you understand this theory。

So the baby step here would just be， again， consider this hardest problem。

 min cost non biparttheite matching。Suppose we give up on optimality， we just want to be fast， okay？

We're do heuristic。 All right， Well， of all the paradigms you learn in C S 1，61， you know。

 one of the ones that almost almost LED to really fast algorithms were greedy algorithms。 Okay。

 they're often not correct。 but they're getting a really good starting point for heuristics。

And there's a very natural greedy algorithm for non bipartite matching。

Just like it's really just like Cruscoll's algorithm。 So again。

 suppose it's the max weight version of it。 So you want big weights。Why not just sort the edges。

 again， non necessarily bipartid， general graph， sort the edges from highest weight to lowest weight。

Do one pass through the edges in this order？And include the edge。

 the current edge in your matching if you can， meaning if you haven't yet matched either one of its endpoints。

Okay， so definitely pick the first edge。 The second edge you'll pick if it's disjoint from the first edge。

 but you'll skip it if it shares an endpoint with the first edge and so on。 Okay。

 so this is not always going to be optimal。That's quite easy to see。Actually don't even need that。

So I just have a zigzag。With a  one plus epsilon like 1。01 in the middle。

 and then one on either side， this greedy algorithm is going to pick the zigzag edge because that's the highest weight one。

 and that we'll block the other two edges。Okay， so the max weight matching here is total weight2。

 the greedy on I just mentioned will be off by will only be half of that。Okay。

But it turns out that's actually a worst example for the greedy algorithm。For every graph。

 no matter what the edge weights are， the greedy algorithm will always guarantee you at least 50% of the weight in the best matching。

 and of course that's a worst case bound it can be achieved but in lots of graphs you'll do better than 50% but even in the worst case you're already 50% and the proof is not too hard so you'll see you'll see that on the homework and in the last module of 261 we'll talk about approximation algorithms for NP hard problems So things where an exact solution would require more than polynomial time。

 but it's worth remembering you know even the harder problems in P。

 and when you study nonbipartite matching， you can really feel you're in like you know the barren tundra。

 the outer reaches of P you can tell that NP hardness is like just around the corner So even for those harder problems in P it's worth thinking about fasturistics and again the theory that you're learning in this class helps you understand when they work well。

So Tuesday we'll start talking about linear programming， see you then。

