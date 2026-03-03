# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P141：13_01_05_约翰逊算法一.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/ddaffd8925c3c4d434f05fd5f39aec12_0.png)

In this video， we'll cover Johnson's very cool algorithm。

 It shows how to use the reweight technique we introduced in the last video to reduce the all pair shortest path problem in graphs that can have negative edge length to a single in of the Belman Ford shortest path algorithm。

 followed by N ins of Dyextra's shortest path algorithm。

We concluded last video daydreaming about this best case scenario where we have a graph with negative edge lengths。

 but somehow we come up with these magical vertex weights that transforms all of the edge length to be non negative。

And it turns out that the magical vertex weights which will realize this best case scenario are best computed by a shortest path algorithm。

 So before describing Johnson's algorithm in general。

 let me just walk you through some of the steps in an example。

So I've drawn a directed graph with six vertices and seven edges。

 I've annotated each edge with its cost in blue。 Notice that some of the edges do indeed have negative costs。

 so it is not currently an option to run Dyster's algorithm on this graph。There is no negative cycle。

 however， in this graph。 It only has one cycle， the directed triangle at the top。

 and its overall cost is one。 So we could run the Belman Ford algorithm on this graph if we wanted。

So our strategy is to compute a magical set of vertex weights so that when we transform the edge lengths using the reweighting technique described in the previous video。

 we wind up with a graph that now has only non negative edge lengths。

So where do these vertex weights come from， well the great idea in Johnson's algorithm is to compute them using a subroutine for the single source shortest path problem。

To implement this， we need a well defined instance of the single source shortest path problem。

 In particular， we need a source vertex。So that's a pretty good idea。

 There's only one small problem with it， which is that when you pick your arbitrary source vertex。

 it might not be able to reach all of the other vertices and to get our magical vertex weights。

 we're really going to want finite shortest past distances from our arbitrary source to everybody else。

 For example， in the graph that I've drawn here on the slide。

 It doesn't matter which of the six vertices you choose as your source vertex。

 you will not be able to reach all of the other five。So how do we get around this issue， Well。

 with a simple hack， we're just going to add a new vertex to a seventh vertex in this example。

 and we're going to connect this new vertex， which I'm going to just call S to all of the original vertices with a direct arc of length0。

We are then going to compute shortest paths from this new artificial source vertex S to all of the vertices from the original graph。

 noticeice that by construction， we're going to get a finite shortest path distance from S to all of the vertices we've installed a direct path from S to everybody else。

Notice that because this new vertex S has no edges going into it。

 it's effectively invisible from the perspective of all of the original vertices in the graph G。

 So in particular， the shortest path distance between any pair of vertices U and V and the original graph is unchanged by this addition of the vertex S。

 Similarlyly， whether or not G has a negative cycle is unaffected by the addition of the vertex S。

The next step of Johnson's algorithm is to invoke a single source shortest path algorithm using this newly added vertex S as our source vertex。

Now， in this example， and in general， we're thinking about the case of negative edge lengths。

 so we're not going to be able to use ditrus algorithm to solve this single source version of the problem。

 We're going to have to use the Belman Ford algorithm to do this computation。

So let's now go ahead and figure out what are the shortest path distances from S to the other six vertices in this graph on the slide。

So let's start with the vertex A。 What's the shortest path distance from S to a。 Well。

 it's certainly no worse than 0。 There's a path directly from S to a of length 0。 And indeed。

 in general， all six of the shortest path distances that we compute will be 0 or less。

So the question is there a path from S to a that is negative that's better than zero？Well。

 what are the other options We could go from S to C at length 0。

 But then we'd pay 4 to get back to a。 So that has length 4。 So that's no good。 A little bit better。

 but still not good enough would be to zip straight from S to B。 That has length 0， from B to C。

 Now're up to we're down a -1。 But then we have to go from C to A。 And so we add 4。 So we get 3。

 So we conclude that the shortest path from S to A is indeed the direct one hot path of length 0。

Most of the other vertices are more interesting。 However， think， for example， about vertex B。

 We could， of course， zip straight from S to B along a path of length 0。

 but we can get shorter than that if we go first from S to a at length 0。 and then from a to B。

 then that path has combined length -2。 And that is， in fact， the shortest path distance from S to B。

The shortest fat distance to C is just to take that same shortest path to B and then concatenate the edge of cost 1 from B to C。

 That is the shortest path from S to T goes S to A to B to C for a combined length of 0 plus -2 plus -1-3 in all。

So now let's move to the bottom of the graph。 the vertex Z is pretty easy to think about。

 there's only one path in the entire graph that's the direct one from S to Z。

 So z is just going to have the trivial shortest path distance of0。So now for the vertex Y。

 you got a bunch of different options。 You could， of course， go straight from S to y at length 0。

 but there's a lot of things better than that。 You could also go from S to z。

 And then along the-4 arc to y， that would give you a path of length-4。

 But you can do even better than that by going first to a， then to B， then to C， and then to y。

 So that gives you a path whose edge costs are 0，-2-1 and -3。 that gives you a combined total of-6。

 the shortsest path distance to Y。Similarly， the shortest path to get to x。

 the best thing to do is to accumulate all of the negative weight at the top of the graph。

 go via vertex C， and it's true you have to pay the cost of 2 to get from c to x。

 but you still end up with a net length of minus1， which outperforms the direct zero length path from S to x。

Now the brilliant insight in Johnson's algorithm is that this shortest path computation is extremely useful。

 in fact， these computed shortest path distances are exactly the magical vertex weights that we're seeking。

 they're going to transform all of the edge lengths from general to non- negative。

So let's define the weight piece of V of a vertex v from the original graph that is one of the six vertices in this example that we started with as the shortest path distance we just computed from the extra vertex S to that vertex V。

What I want to do next is see the effect of reweighting using these vertex weights， so to do that。

 let me redraw the example。So let's recall the formula for the reweighting technique。

 given vertex weights like these， you define the new length C prime E of an edge E， say from U to V。

 as its original length C E plus the weight of its tail， piece of U minus the weight of its head。

 piece of V。So let's just do this computation for each of the seven edges。

 Let's start at the top edge A comma B。 So we start with this original length -2。

 We add the weight of the tail。 So we're adding 0， and then we subtract the weight at the head。

 So we're subtracting -2 that is we're adding2。 So we get -2 plus 2 or 0 for the new length C prime E for the edge A comma B。

Similarly for the edge B comma C， we take the original length -1， we add to it -2。

 and then we subtract -3， but as we add 3， and again it all cancels out。

 we get zero for the new cost of Arc B comma C。For the arc C comma A， we take the original length 4。

 We add-3， and we subtract 0。 So the arc C comma A has a strictly positive， shifted length。

 that's now one。If we look at the arc C comma X， we take the original length2。

 we add minus3 and we subtract minus1， so that again all cancels out and C comma X has a new cost of 0。

Same thing happens with the Arc C comma Y， we start with minus3， we add another minus3。

 we subtract minus6 that gives us0。For the a Z comma Y， we start with one， we add0。

 we subtract minus-1， so we get a new cost of2 on the arc Z comma X。Finally for the Arc Z comma Y。

 we start with minus4， we add0， we subtract minus6， that is we add6。

 so that gives us a new length of two。So I don't expect you to have intuition or semantics for the computations that we just did。

 But at least in this example， the proof is in the pudding。

 We just used these shortest path distances as weights and reweighting magically made all 7 edges have non negative edge length。

 They all have length either 0，1 or 2。So what we've now done， at least in this example。

 is realize the best case scenario we were dreaming about。

 Remember what the key point of the reweighting technique video was。

 we pointed out that reweighting preserves shortest paths。 If you have some vertex weights。

 some piece of V's， you change all the edge length by reweighting for every origin S in every destination T。

 you shift the length of every st path by exactly the same amount by P of S minus piece of T。

 the difference between the vertex weights at the origin and the destination。

 So by changing all paths by exactly the same amount， you preserve which path is the shortest。

So that's a cute party trick。 It's not really clear it would be useful。

 but we are hoping that maybe reweighting in a shortest path preserving way could allow us to transform the general edge links version of a shortest path problem to the non negative edge links version of the problem so that we are not stuck with those slower Belman Ford algorithm。

 And instead， we get to use the faster diters algorithm。

And that's now exactly what we can get away with here， at least in this example。

 we did the transformation， the new graph has only non negative edge links。

 now we can just run Dykesster's algorithm once for each choice of the source fort to compute all of the shortest path distances。



![](img/ddaffd8925c3c4d434f05fd5f39aec12_2.png)