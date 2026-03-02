# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P129：01_01_04_单源最短路径再探.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/eb5088c90415c0e1fc9ae8705227c03c_0.png)

In this next sequence of videos we're going to revisit the single source shortest path problem。

 this is a problem that we already solved using Dyextra's greedy algorithm now let's see what the dynamic programming paradigm can do for us for the same problem。

Let me just quickly remind you the definition of the problem， what's the input， what's the output？

We're given a graph and when we talk about shortest path。

 we're going to be discussing only directed graphs。

Each edge of the graph has a length which we're going to denote by CAB。And one vertex。

 which will denote by little S， is designated as the source vertex。

We're going to assume that the graphs are simple that is there's no parallel edges。

 the reasoning is the same as in the minimum spanning tree problem if you had a bunch of parallel edges。

 since we only care about the shortest path， you may as well throw away all of the copies of an edge except for the one that has the smallest length。

The responsibility of an algorithm for this problem is to compute the length of a shortest path from this source vertex S to every other possible destination V。

And always， when we talk about the length of a path。

 we mean the sum of the edge costs of all of the edges that are in that path。For example。

 if the cost of every edge was one， then we'd just be talking about the hop count and that's a problem that's solved using breath first search。

 but in general in the single source shortest path problem we're interested in edges that have possibly wildly different lengths from each other。

So let's now review our existing solution for the problem Dytras algorithm。

 review its pros and its cons。So Dexter's algorithm is a great algorithm。

 if you have a graph and it fits in your computer's main memory and all the edge costs are non negative。

 if you implement Dexter's algorithm using heaps， you will get a blazingly fast and always correct shortest path algorithm。

In part one of this course， we explained an implementation using heaps that runs in big O of M times log n time。

 where as usual M is the number of edges and n is the number of vertices。

 and this implementation is almost identical to the one we discussed earlier in this course for Prims algorithm for computing a minimum spanning tree。

 It turns out you can get an even better asymptotic running time， at least theoretically。

 a running time of M plus n log n， if you use a more exotic type of heap data structure。

 but let's for now just think of this as the line in the sand Big O of M log n using Dykes's algorithm on a graph with non negativeative edge lengths。

So given what a great algorithm Dykester's algorithm is on what basis could be rejected and study any other shortest path algorithm。

 well， there's two drawbacks we've mentioned before， let me reiterate them now。So first of all。

 if you're working with a graph where some of the edge costs can be negative。

 then the output of Dter's algorithm need not be correct。

 The correctness relies on the non-negative edge cost assumption。

 we saw concrete examples of this both back in part one of the course。

 but also in this course when we first started talking about greedy algorithms and we discussed their ubiquitous incorrectness。

Now， frankly， for many of the applications of shortest path algorithms。

 you're never going to run into negative edge links。 if you are implementing， for example。

 a program that computes driving directions， whether you're doing it in miles or in time。

 you're not going to have negative length edges， at least until we finally get around to inventing those time travel machines。

But not all applications of the shortest path problem are so literal and involve literally computing some path in space from some point A to some point B。

 More abstractly， the problem is just helping you find an optimal sequence of decisions。

 Imagine you were managing a bunch of financial assets， for example。

 and you are modeling a single transaction as an edge in a network that takes you from one particular inventory to another。

 when you sell stuff that might generate positive revenue and correspond to a positive edge length。

 But when you buy stuff， then， of course， you have to spend money and that could correspond to a negative edge length。

So the second drawback， which we mentioned in the intro video for this course is that Dus's algorithm seems highly centralized Now that's not a problem if you just are storing the entire graph in the main memory of one machine。

 but if you're talking about routing in the internet。

 while it's totally impracable for a router to have up to-d complete map of the entire internet to compute routes locally and so that motivates looking at a different shortest path algorithm which is better suited for distributed routing。

So we're going to be able to address both of these drawbacks in one fell swoop via the Belman Ford algorithm。

 which will be yet another instantiation of the dynamic programming algorithm design paradigm。

This Bellman Ford algorithm， despite predating the earliest version of the Apant by a good 10 years。

 nevertheless does form the basis for modernday internet routing protocols。

 Of course there's a lot of engineering steps that you need to go from the abstract Bowman Ford algorithm to practical solution internet routing we'll discuss that a little bit in a separate video。

 but this really is where it all gets started。So before we start developing the Belman Ford algorithm。

 we need to take care of some subtle preliminaries。

 we need to be clear about how we're defining shortest paths in the presence of negative edge costs and in particular in the presence of negative cost cycles that is a directed cycle of edges where the sum of the edge costs is less than zero。

You can think， for example， about this green cartoon I've drawn off on the right。

 where somewhere embedded in this graph is a directed cycle that has four edges。

 some of the edges in the cycle have negative costs some have positive。

 but on balance the cycle has negative overall cost cost minus2 if you traverse all four of the edges。

So let's think about how we should define the shortest path from the source for tick S to some destination V in a graph like this in particular。

 do we allow cycles in the path or not， So first， let's think through the ramifications of allowing paths to include cycles。

So this proposal actually doesn't make sense in that generally there will be no shortest path from S to V if you allow cycle traversals。

 The reason being that if you have a negative cycle like this one of overall cost 2 in this green graph and you can actually reach it from the source S。

 then for every path you can actually find another path will just even shorter。

 you traverse the directed cycle one more time， the path overall path length drops by another minus2 and there's nothing from stopping you from doing over and over and over again。

 So either the shortest path， you think of it as being undefined or you can think of it as being sort of minus infinity in the limit。

So if permitting our path to have cycles didn't work。

 why not we explore the option where we forbid cycles in our paths？

So this version of the problem is perfectly well defined。

 It's a totally sensible computational problem， which you might well want to solve。

 The issue here is much more subtle。 The issue is that this problem is what's called NP complete。

 That's something we'll discuss much more next week。

 but the bottom line is these are intractable problems。 There are no known computationally efficient。

 no known polynomial time algorithms for NP complete problems。 And this unfortunately。

 is one such problem， Computing shortest cycle free paths in the presence of negative cycles。

So a bit more precisely， if you came up with a guaranteed correct and guaranteed polynomial time algorithm that always computed shortest past in the presence of negative cycles。

 a consequence would be what's called P equals NP， and that's something we'll discuss a bit more formally in a later video。

 but certainly if you came up with such an algorithm you should report immediately to the Clay Institute。

 they would have a $1 million prize awaiting you for such an algorithm。

So for those of you that are already familiar with NP completeness。

 it would be an easy exercise to prove that this problem is NP hard。

 it would just be a reduction from the Hamiltonian Pa problem。

So it seems that we're stuck between a rock and a hard place。 if we allow cycles in our path。

 we don't get a meaningful problem， we get something that doesn't make sense。 if we exclude cycles。

 we get a perfectly meaningful but unfortunately computationally intractable problem。

So here's how we're going to proceed。 We're going to focus for now just on graphs that do not have negative cycles。

 We will of course， allow individual edges to be negative。

 but we're going to insist for the moment that every single directed cycle of the input graph has overall non negative length。

 so it can have some positive edge costs， some negative edge costs。

 but overall it has to be non negative。Now， I don't blame you if this assumption bothers you。

 but the good news is， as we'll see the Belelmon Ford algorithm effortlessly checks whether or not this condition holds。

 it effortlessly detects a negative cycle in the input graph if one exists So the version of the shortest path problem that Belman Ford algorithm is going to solve will be the following given an input graph which has negative edge costs it may or may not have a negative cycle the Belel For algorithm will either correctly compute shortest paths from the source to all the destinations just like you wanted or it will punt。

 but it will offer you a good excuse for why it punt it it will show you a negative cycle in the input graph and of course computing shortest paths is intractable in the presence of a negative cycle So Belman Ford you have to sort of let it off the hook in that case so it'll give an input graph either it'll show you a negative cycle or itll give you all of the desired shortest path distances。

 That's the guarantee we're gonna to strive for。So I're going to end this video with a quiz helping you understand why this hypothesis of no negative cycles might be useful in an algorithm。

 so for now I just want you to think about suppose I promised you that an input graph had no negative cycles and the question is how many hops。

 how many edges are sufficient to guarantee that you found the shortest path between S and some given destination feet？



![](img/eb5088c90415c0e1fc9ae8705227c03c_2.png)

So the correct answer is a。 And this is one of the main reasons the no negative cycle hypothesis is useful。

 It gives you control over how many edges are necessary to ensure that you've got a shortest path。

 So specifically， suppose you had a path between some S and some V that had at least n edges。

 Well if you have at least n edges， it means the path visits at least n plus one vertices。

 there's only n vertices。 So if you visit at least n plus one， that means you visit one vertex twice。

 say x。 So that means you have a cycle inside your path that goes from x back to X again。 Now。

 if you rip out this cycle， if you just delete those edges， you get another path from S to V。

 And because this directed cycle as they all are， must be non negativegative， the total link。

 The sum of the edge costs has only gone down by removing this cycle。

 So you show me path from S to V with at least n edges。

 I'll show you a path with fewer edges and that's at least a short could only be shorter。

 So that shows you that the short。This or a shortest path has a most n minus1 edges。

 which is the correct answer to the quiz。