# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P64：4 - Fall 2022 Discussion 11 Question 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/0183802e833ff03898cb2413d184f460_0.png)

Question 3， A asks us to design and algorithm to determine whether or not a graph is bipartid。



![](img/0183802e833ff03898cb2413d184f460_2.png)

A graph is biheid if we're able to split all of this vertices into two distortjoint sets， U and V。

 where all the vertices in U are only connected to vertices in V and all the vertices in V are only connected to vertices in U。

😊，So as an example， the graph here on the left is bipartheid because every vertex marked with U only has vertices marked with V as their neighbor and vice versa。



![](img/0183802e833ff03898cb2413d184f460_4.png)

The graph here on the right is not bipartid because no matter which set you assign this question mark vertex to。

 U or V， you're going to end up breaking the rule。 if we assign the vertex with the question mark to the set U。

 then you end up with two vertices in the set U that are next to each other and if we assign the question mark vertex to the set V。

 then you end up with two vertexes of the set V that are next to each other。

 So this graph cannot possibly be bipartid。Take a moment and try to think of which algorithm we can use to try and determine whether or not a graph is bipartid。



![](img/0183802e833ff03898cb2413d184f460_6.png)

So one way to solve this problem is to use a modification of B， F， S or D， F， S。

We just need to traverse through every single node in the graph。As we traverse。

 we're going to be marking each node as either being in the set U or in the set of V。

We can start a traversal by marking the first note as being in the set you。

Then we'll try to mark all the neighboring nodes as being in the set V。

 and when we traverse to the next node， we'll flip to instead marking all the neighbors as being in the set U。

If we end up getting to a node which has the neighbors marked as the same set that that node is in。

 then we know that the graph is not my part time。For example。

 if we run the algorithm on this graph on the very right。

 we would start by marking the leftmost node as being in the set U。And then we'll go to its neighbor。

 the middle node and mark as in the Z V。Then we'll go to the neighbor of the middle node and mark that as being in the set U。

 So now the node remark U V U。And then finally， we will'll traverse the neighbor of that rightmost node。

 which is going back all the way to the leftmost node， See that that node has already been marked U。

 and then conclude that we now have two nodes marked U that are adjacent to each other。

 so it cannot be bypartite。

![](img/0183802e833ff03898cb2413d184f460_8.png)

This problem gives us a pseudo code implementation of depth first search。

Except that this implementation has a small bug。Let's try to see where this bug is。

 and then we leave graph where the pseudocode implementation traverses the node in a different order than the correct implementation of DFS。

So if we compare this implementation to the implementation that's given in the class lecture slides。

You'll notice that the order in which we mark the neighbors is different from the order that we normally do in D F S。

In this pseudoode implementation， the neighbors are marked as soon as they are pushed onto the fringe。

So let's see what the effect of that is when you run it on a sample graph。



![](img/0183802e833ff03898cb2413d184f460_10.png)

The way we're supposed to mark the vertexes is to mark them as visited after we pop them off the stack。

But because this pseudocode implementation marks them as soon as they're pushed into the fringe。



![](img/0183802e833ff03898cb2413d184f460_12.png)

We end up traversing the vertices in a different order。



![](img/0183802e833ff03898cb2413d184f460_14.png)

So， let's take a look。We'll first push a into the fringe because a is the node that we started the search on。



![](img/0183802e833ff03898cb2413d184f460_16.png)

![](img/0183802e833ff03898cb2413d184f460_17.png)

Will visit a by popping it off the fringe。And then take all of its neighbors。

 put all of A's neighbors into the fri， Mark all of them。



![](img/0183802e833ff03898cb2413d184f460_19.png)

And then。Visit the next neighbor。Normally， C And D would not yet be marked in the proper implementation of DFS。

 but because this implementation of DFS marks all the neighbors as soon as they pushed under the fringe。



![](img/0183802e833ff03898cb2413d184f460_21.png)

All of these neighbors are already marked。So we actually don't visit any of B's neighbors at all。



![](img/0183802e833ff03898cb2413d184f460_23.png)

Then we just take the next item off the fringe， which is C。



![](img/0183802e833ff03898cb2413d184f460_25.png)

See as no neighbors。And then。We'll take D off the French。

 and all of these neighbors have already been visited。

 So the order in which we visited these nodes in this bug implementation is。



![](img/0183802e833ff03898cb2413d184f460_27.png)

![](img/0183802e833ff03898cb2413d184f460_28.png)

A， B。

![](img/0183802e833ff03898cb2413d184f460_30.png)

C and N D。However， the correct implementation of DFS should have continued to the node D after visiting the node B。

 because D should not have already been visited by the time we visited B。

 So the correct order in which we should have traversed these nodes should have been A， B， D and N C。



![](img/0183802e833ff03898cb2413d184f460_32.png)

![](img/0183802e833ff03898cb2413d184f460_33.png)

![](img/0183802e833ff03898cb2413d184f460_34.png)