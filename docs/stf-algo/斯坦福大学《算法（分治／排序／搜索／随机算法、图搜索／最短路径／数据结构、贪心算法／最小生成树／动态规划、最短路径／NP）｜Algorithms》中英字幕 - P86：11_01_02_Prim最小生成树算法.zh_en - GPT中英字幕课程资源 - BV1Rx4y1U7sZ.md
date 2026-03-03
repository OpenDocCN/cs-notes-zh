# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P86：11_01_02_Prim最小生成树算法.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

Okay， so it's time to discuss our first minimum span tree algorithm， namely Prims algorithm。

 definitely a candidate for the greatest hits compilation。 And again。

 remember even though it's called Prims algorithm， it was actually discovered earlier by Yarnnic So how's it work。

 Well before showing you any pseudocode， let's first illustrate it on an example。



![](img/fb282f5d932ac9554ac9c64edd6e7269_1.png)

As we go through the example， I hope that the similarities to Dyketra's shortest path algorithm will be evident。

I'm going to work with the same example graph from the previous video with four vertices and five edges。



![](img/fb282f5d932ac9554ac9c64edd6e7269_3.png)

The plan is to grow a tree one edge at a time and we're going to keep growing this tree like a mold。

 we're going to start from just a seed vertex and then we're going to suck up one new vertex with each iteration of the algorithm so this is similar to Dyster's algorithm in Dxster's algorithm that was clear where we should grow the initial mold from because we were given a source vertex that they're trying to compute shortest pass out of we have no source vertex in the minimum spanning tree problem but it turns out we can just pick an arbitrary vertex to start。

 doesn't matter which one which is cool。

![](img/fb282f5d932ac9554ac9c64edd6e7269_5.png)

![](img/fb282f5d932ac9554ac9c64edd6e7269_6.png)

So the plan is in each iteration， we're going to add one edge and span one new vertex adjacent to the ones that were already spanning。

 Now， as a greedy algorithm， Pri is simply going to select the cheapest edge that allows it to span one additional new vertex。

 Now， at the start of the algorithm here， we're not really spanning anything。

 We're sort of thinking of ourselves is growing from and currently spanning just the vertex in the upper right。

 So what are the edges by which we can span an adjacent vertex。 Well，'s two edges。

 There's the top edge with cost 1， then we'll span an addition， the upper left of vertex。

 or there's the edge with cost2 on the right。 If we include that we'll be able to span the vertex in the bottom right。

 So we're going to be greedy。 We're just going to choose the cheaper edge， the edge of cost one。



![](img/fb282f5d932ac9554ac9c64edd6e7269_8.png)

Now the vertices that our tree thus far spans are the top two vertices。



![](img/fb282f5d932ac9554ac9c64edd6e7269_10.png)

So in the next iteration， we want to add one more edge to span one additional new vertex and now we see that there are three edges sticking out of what we're spanning thus far that will allow us to span a new edge。

 There's the edges that have cost 2，3 and 4 The two and the three will allow us to span the vertex in the bottom right if we pick the four that'll allow us to span the vertex in the bottom left Yeah we're going to be greedy we'll have these three candid edges we're going to pick the cheapest one which is the edge of cost2。



![](img/fb282f5d932ac9554ac9c64edd6e7269_12.png)

So now the mold that we've been growing， in effect。

 covers all of the vertices except for the one in the bottom left。



![](img/fb282f5d932ac9554ac9c64edd6e7269_14.png)

So now in the final iteration， we want to include one more edge so that we span that final remaining vertex。

 the one on the bottom left note that there there was this edge of cost3 that we never added。

 but it got sucked up into the tree that we grew anyway。 So we're going to go ahead and ignore that。

 adding the three wouldn't allow us to span any more vertices。 In fact。

 it would create a loop which we don't want。 So we're going to say okay。

 we'll have the two edges that would allow us to span an extra vertex。

 There's the four and there's the five。 We're going be greedy。 we're gonna pick the four。

 And once we have the edges that cost one and 2 and4。 we have a spanning tree。 there's no loops。

 there's a path from any vertex in any other vertex along pink edges， the cost to7。

 you might recall from the previous video。 This is indeed the minimum cost spanning tree of this graph。



![](img/fb282f5d932ac9554ac9c64edd6e7269_16.png)

![](img/fb282f5d932ac9554ac9c64edd6e7269_17.png)

Of course， the fact that we have this simple procedure that works correctly in this toy example。

 which is four vertices and five edges really means nothing。 I mean。

 you shouldn't draw any immediate conclusions that this is a good algorithm in general。

 even though that is going to be the case。 So let's next go and actually define the algorithm generally。

 So if you have a general graph， what does it mean to start somewhere and grow a mold。

 span one more vertex each iteration， always proceeding greedily until you're done。

 So let's spell out the pseudocode on the next slide。



![](img/fb282f5d932ac9554ac9c64edd6e7269_19.png)

So here is Pri's minimum spanning tree algorithm。 We're going to start with just two lines of initialization。

 We're going to maintain a set of vertices capital X。

 This is meant to be the vertices that we span so far。 Again。

 we need some seed vertex from which to start the process It doesn't matter where which one we pick we're going to get the same tree at the end no matter what。

 So just call it a little less。 That's an arbitrary vertex from which we start growth。

The other thing we're maintaining is of course， the tree， so that's initially going to be empty。

 we're going to add one edge to it in each iteration。

An invariant that we're going to maintain throughout the algorithm is that the edges that currently reside in the set capital T span the vertices that currently reside in the set capital X。

Then we're going to have our main while loop， this is the workhorse of the algorithm and it's very similar to the one in Dketra's algorithm。

 namely each iteration is responsible for picking one edge， crossing the current frontier。

 advancing to include one new vertex and again it's going to be greedy。

 the criterion is going to be different in fact simpler then with Dyster's algorithm instead of looking at length。

 we're just going to say what's the cheapest edge that allows us to span a new vertex。

So the loop's going to keep going as long as there are vertices that we don't yet span。

And then what we do is we search through the edges that allow us to span a new vertex so which edges are those Well we want there to be one endpoint in the set capital X of vertices we already have our tree spanning and we want the other endpoint to be nonreundant so we want it to be outside of capital X so if we have an edge that crosses the frontier in this sense。

 one endpoint in capital X one endpoint outside， that's how we increase the number of spanned vertices by one in an iteration。

So if E is the cheapest edge amongst all of those that cross the frontier with one endpoint on either side。

 that's the one we're going to add to our tree so far capital T in this iteration it's endpoint that's not already in capital X that's going to be the vertex that we add to X in this iteration。

And again， the semantics of an iteration is that we're trying to increase the number of spanned vertices while paying as little as possible。

 that's the sense in which Prims algorithm is a greedy algorithm。

So as usual with a greedy algorithm this seems natural enough but it's not at all clear that it's correct that it always computes a minimum spanning tree。

 in fact if you think about it， it's not even obvious it actually computes a spanning tree at all。

 minimum or otherwise， but it is correct， let's make that statement precise on the next slide。



![](img/fb282f5d932ac9554ac9c64edd6e7269_21.png)

So the key claim is that Prim's algorithm is correct。

 given any connected input graph is guaranteed to output a spanning tree with minimum possible cost so before we delve into any details let me just finish this video by telling you about the proof plan we're going to prove this theorem in two parts first we're going to establish that it outputs some spanning tree maybe maybe not minimum even that's non trivial then we'll worry about arguing that the spanning tree output actually is one of minimum cost。

Both parts of the proof are interesting， for part one to argue that we output some spanning tree。

 we're going to review some preliminaries about graphs and about cuts and about spanning trees and graphs。

For part two to argue optimality， we're going to rely on a very neat property of spanning trees。

 minimum spanning trees called the cut property。

![](img/fb282f5d932ac9554ac9c64edd6e7269_23.png)

I'm happy to report that the work that we do here in both parts will bear further fruit later。

 we're going to reuse these ingredients when we prove the correctness of another MST algorithm name Crusll's algorithm。

For those of you who would much rather talk about running time than correctness。

 don't worry your time will come after we wrap up this correctness proof。

 I'll address how do you implement Prims algorithm quickly。

 in particular using heaps we'll get the running time down to the near linear bound of O of M log N。

