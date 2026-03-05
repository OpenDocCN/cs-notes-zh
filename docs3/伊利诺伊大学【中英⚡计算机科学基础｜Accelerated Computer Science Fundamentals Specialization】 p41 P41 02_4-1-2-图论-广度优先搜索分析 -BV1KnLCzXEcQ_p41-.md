# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p41 P41 02_4-1-2-图论-广度优先搜索分析 -BV1KnLCzXEcQ_p41-

![](img/75d49f49889dedd242b1ea5275caefe3_0.png)

![](img/75d49f49889dedd242b1ea5275caefe3_1.png)

In the last video you learned how to implement a BFS algorithm and you learned what a BFS structure looks like here today。

 we want to do a little bit of analysis on what we did and what things we found out through running this algorithm。

So one of the first questions we can ask is whether or not the algorithm that we ran is able to detect different components in our RA。

Let's look at the code。Here in the code， we can see that at lines 10 through 12。

 we actually did something that I didn't really explain earlier， but you can see it's clever。

 We looked at every single node and we marked as unexplored initially and here this for loop we go through every node if it's still unexplored。

 we travel through the BFS algorithm。 So if we think about a graph that has two components。

We can see only when we visit one component， do we explore all three of these nodes and Markammal is explored。

Then here。When we have those two nodes， those nodes will be unexplored in the other component。

 because only once we actually visit the nodes in the BFS algorithm， do we mark them as explored。

 So because of that， we can simply cycle through。 And when we see another unexplored node。

 we have a new component。 Can we count components absolutely。 by adding line 13 here。

 we can count number of components by simply adding component plus plus for every time we call the BFS algorithm。

😊，This is fantastic。So does our implementation handle on little disjoint graphs， yes。

 what code handles this， this is the line 10 through 13， and how do we count component。

 we add on line 13 a component plus plus counter。Second question is。

 does our implementation detect a cycle？And if we think about what a tree looks like。

 a tree is going to be a series of nodes that everything's going to be a discovery edge。

Because we're always discovering something beneath us because we're always going down as soon as we travel to the same to a node on the same level。

 we know that we could take that cycle and completely re follow it again and again and again to have a cycle in our graph。

Because of this。We know that the existence of a cross edge means that there's a cycle。

 so does this algorithm detects cycles absolutely yes。How do we update our code， Well。

 let's see exactly where we look at cross edges。So here we see that in lines 26 to 27。

 This is when we see that a cross edge is labeled。 So if we simply say cycle。Is equal to true。

 we're marking the fact that cycle has been detected in graph。

So by adding a line 28 to denote that a cycle has been found。

 we're update our algorithm to not just do a traversal。

 but also count number of components and determine whether or not there's a cycle。 Therefore。

 does our implementation detect the cycle， Yes， how do we update the code to detect that cycle。

 We added the line 28。To mark that a cycle is found on our graph。

And what is the running time of this algorithm。 Well， to do that。

 let's go ahead and analyze this algorithm and dive into it To do this analysis。

 we're going to look at two different lines of code。

 We're going to look at line 19 and line 21 because those are the two looping structures and that's going to determine the number of times our code actually runs。

😡，So here the while loop at line 19， the while at line 19 says while the Q is not empty。

 so thinking about what's going be in the Q， the Q is going to contain every single node in the tree because when we discover it for the first time。

 we mark a discovery edge and we add that to our Q so the entirety of all of the runs of this algorithm is eventually going to run a total of in times for every single vertex in our graph so the while loop bit line 19 runs in times。

😡，Let's think about line 21， So line 21 says that for every vertex inside of the list of adjacent vertices。

 so that means that could be potentially every single other node in our graph if we have a fully connected graph。

So here we can potentially be up to n， but we also learn some property about our graph。😡。

We learn that in our graph， we know the sum of all of the degrees of all of the vertices for every vertex in our graph。

 that that sum， when we account for all in of them is going to be equal to 2M。

So one way of looking at an algorithm is it's going to be an in times n algorithm that for every single vertex。

 we're going to have a series of potentially every other vertex connected to it。

 or we can say in totality in the entire graph。There is exactly2 m of these vertices。

So what we can do is we can either do the analysis that says it's in times n or in squared running time。

 or we can say it's in time here and independently we have to add up all of the possible edges here so that's 2 m。

 so we can either do n times n to get an n squared running time or more precisely。

 we can say it's n plus 2 m。Which is going to be equal to a running time of O of n plus m。

So notice that M could be in squared。 So if we have a fully connected graph。

 the number of edges in our graph is going to be n times n -1 over 2。

 So that's going to be in squared edges in our graph。 So M may be n squared。

 But for a graph that's only partially connected or a graph that is sparsely connected。

 We can see M is gonna to be a number close through in。😊，So when M is closer in。

 this algorithm runs actually proportional to n。Because it's simply linear time based on the nodes or the edges。

 So the most accurate thing we can say is n plus M， knowing the M may be n squared。

 So the best running time we can say for a BFS traversal is an n plus M running time。

The last thing I want to talk about is kind of talk about a few different properties of the tree we actually create when we create this tree of all the discovery edges。

So one thing we can talk about is what is the shortest path from a to H。 So looking at this tree。

 we know this is a tree structure， indeed， that starting with the node we started our BFS traversal on。

 we can simply follow discovery edges， and those discovery edges are going to lead us down a path that gets to H。

Specifically， these discovery edges， we usually encode as a predecessor vertex。 So if we look at H。

 H's predecessor is going to be D。 D's predecessor is a。 A has itself as the predecessor。

 So we know the shortest path from D to H is the path among discovery edges。

 So that's going to be A D H。On the other hand， we may need to talk about what the shortest path is from E to H to different vertices。

Unfortunately， BFS only gives us the shortest path from our starting vertex。

So we don't know it is not possible。To know the shortest path from E to H with only。A BFS algorithm。

We always must look at only the starting vertex。 if we need to know the shortest path。

 we need to start our BFS algorithm at E or explore another algorithm to give us the shortest path。

 which we'll talk about in the future。Third question。

 how does any cross edge relate to the distance that I have between my starting vertex and my current location？

And if we think about this， the cross edge is always going to be an edge that's going to get us somewhere nearby where we've been。

So if the edge is going to explore a new structure。

 it would have been a discovery edge because the discovery edge is going to be the first time we see this structure。

 so when we have a cross edge， we know that somebody else has exploded already。

 so that means either one of our siblings or one of our parents have already seen this edge before。

 so that means a single cross edge is always going to be nearby our existing edges。 In fact。

 by following a cross edge we will never get one more than one further from our root。

We'll never get more than one further from our start。

So knowing that we're never going get one further than our start。

 we know that cross edges are always going to leave us in the same nearby neighborhood relative to our starting location。

 So this is a key idea that allows us to know that falling cross edges isn't going to do anything crazy。

 It's going get us to a different part of the tree。

 but it's still going to be about the same depth from my starting point。 The very last question is。

What's the structure made by this series of discovery edges。

 I've mentioned before that it's a tree that we're always seeing the shape going down away from the root。

 and I'm going to argue that this tree is not just an ordinary tree。

 that this is a substructure called a spanning tree and a spanning tree is a structure that spans every single vertex in our graph。



![](img/75d49f49889dedd242b1ea5275caefe3_3.png)

That means from every vertex here， we can travel along our discovery edges to visit any other vertex。

 This idea is it spans the entire graph in a single tree。

 We're going dive into what that means and do some more analysis on traversals and spanning trees in the next few lectures。

 I'll see you then。😊。

![](img/75d49f49889dedd242b1ea5275caefe3_5.png)