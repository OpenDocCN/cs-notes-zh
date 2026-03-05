# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p46 P46 04_4-2-4-MST普里姆算法 -BV1KnLCzXEcQ_p46-

![](img/25ce2acff467dfa7356a2cb50c85439c_0.png)

![](img/25ce2acff467dfa7356a2cb50c85439c_1.png)

When we speak about another minimum spanning tree algorithm， after talking about curse goalss。

 almost everyone's going to talk about Prim's algorithm。

Both algorithms are going to find a minimum spanning tree。

 but they do so in an entirely different way。Here in Pris algorithm。

 we're going to utilize a fact about a graph， which you can prove。

 which is that if you have two distinct components in a graph。

 if you have a component U and a component V， the minimum edge that connects U and V must be part of some minimum spanning tree。

😡，What this means is if we have a set set of nodes that is labeled and a set of nodes that are not part of our labeled set yet。

 as long as we keep finding the minimum edge that breaks this partition。

 we're going to be finding one of the minimum spanning trees that exists in this tree。

We can define mathematically using this diagram exactly what this means。So here we have two sets。

 a U set and a V set。 Imagine we've started labeling things in the U set。

 If we find the edge E that splits that partition， we know that this edge E has to be part of a an tree and we can label it as such。

Let's take this idea and apply it to a larger tree and actually run Prim's algorithm。Here。

 I'm going to start with just a single node。 It could be any single node。

 And I'm going to call this node part of my labeled set。

 Everything outside of that node is going to be part of my unlabeled set。

 So here I'm going to just choose this node A， and I'm going to call this side of my line the labeled set。

 So node A is。The labeled set。 And now to be parted to create a minimum spanning tree。

 I need to find the minimum edge。That crosses over my partition between the labeled set and the unlabeled set。

Here， this minimum edge is the edge 2。I go ahead and add this edge to my moon spanning tree。

 and I redraw my partition。Now again， I look at all of the edges that cross my partition。

And I find the minimum1 that is5。I add that label。And I redraw my partition。Again。

Do the exact same process， Find the minimum edge here。

 the minimum edge across the partition is this edge 8。Add this edge。And redraw my partition。

Here the minimum edge that crosses this partition is going to be either of these two edges 9。

 It's totally up to us which one we choose， I'm go ahead and choose this DF edge。Update my partition。

Minimum edge across to this partition is the FG edge with a weight of 4。Update my partition again。

 so here we have 13， 13， 11，10 and 16， 10 is the minimum edge here across the partition and finally C is the only thing that's outside of my partition。

 the minimum edge you add it is5。So here what we've done is we have created a number of different steps that we start with just a single node and we look at the partition that separates that node in the labeled set from every other node。

 we find the minimum edge that bridges that partition。

 add it to our labeled set and look at the next partition and find the minimum node that spans that partition。

😡，This whole process ends up creating a spanning tree that is a minimum spanning tree on the graph based on the partition property we discussed earlier。

Let's look at the code to actually implement this algorithm。

Same limitation this algorithm is going to require a few different data structures。

 and we'll go through this in the code。The first thing we'll see is the input's going to be a graph。

 and we're going to input the starting vertex that output's going to be a spanning tree。

What we'll do to actually do this implementation is we're going to label every single vertex with two different values。

😡，We're going to label the vertex with initial weight of positive infinity。

 and everything's going to be labeled positive infinity as its weight。

And then we're also labeled a predecessor node or the P value for every single vertex。

 so that tells us how this node was added to the minimum span tree and allows us to construct the minimum spanning tree at the end of the algorithm。

What we'll do first is then set the initial starting node， the node S to have the weight of 0。😡。

Now we know that the priority Q is going to maintain all of the different weights of all the vertices。

 so we have a priority Q that's going to maintain every single vertex。

 and it's going to organize those vertices based on the weight that it takes that that vertice currently has。

 that that vertex currently has。So what that means is we have a priority Q that contains B， D， E， F。

As well as a， a has a weight of zero and everything else has a weight of infinity。

We're going remove the minimum element from the priority Q。 here， The minimum element is a。

 our starting point。 When we remove a， we add it to our labeled set。

 and now we update all of the nodes instant to A。 So that means we look at B， and we say。

 is the total cost of this edge A to B going to be a smaller division between our partition than positive infinity。

 It is。 So we update B's weight to2， which updates our priority Q to contain B's weight to be 2。

 We also update D's weight to be 17。And we have the F's weight to be 16。

So now we've added a to our labeled set and we've looked at how that adding that label changes things across my partition。

 I now can ask my algorithm using the minimum he algorithm。

 what is the smallest element among all of the node weights？😡。

And the smallest element along all the nodes weight is node B。 So we go ahead and label node B。

 and we repeat this process by updating B to D across this partition。 Now。

 D has a weight of 5 instead of 517 because5 is small。Then 17。 and now B has a weight of 15。

 which is smaller than infinity。 We continue this process， again， adding the smallest node D。

 So D now becomes part of our minimum spanning tree。 B to D here。 We update our partition。

 We update the weights to get to all of our other nodes。 So here， Dc can be reached in 13 now。

DE can be reached in 8。And Df can be reached in9。 We add E being the smallest node that cross the partition。

And now we see that we can update EC to be 12。And。We find the smallest knowns now DF。

We have that here and finally EC。So what we've done is we have actually found an implementation of an algorithm using data structures you already know that we'll do this logic of finding the minimum node across the cut of the partition。

The last thing we want to know is we want to know what is the running time of this algorithm。

 how fast does it take to actually find the minimum spanning tree of Pris algorithm。

 and we're going to do the same analysis that we did with Kchco algorithm。

We can dive in and see what is the running time it takes to build it with an adjacency matrix and an adjacency list。

 and I complete those running times for you by just running through this exact code and seeing what's going on you can see that if we use a heap。

Plus， an adjacency list。We can have this n plus login runtime plus M plus login。

 So we have just a nearly similar runtime as we do， as we did with Chrisco's algorithm。 In fact。

 if we consider a sparse graph， a sparse graph is going to have。😊，M being proportional to N。

 Then the number of edges and the number of nodes are about the same。 And in that case。

 you can see when the number of edges and the number of nodes are the same。

 we know that this is going to be in log n。Plus， M logm。

Which means that the total running time is the exact same thing as。

Cco's algorithm that we have an M log M running time。 If we have a really dense graph。

 we know that M is going to be proportional to the square of the number of nodes that every single node is going to connect to nearly every other vertex in the graph。

In this case， we can see that the。M becomes in squared log in。

Which is going to be greater than in login。 So instead。

 our running time is going to just be bound by in login here。 So for a very dense graph。

 Prims algorithms able to run things proportional to the only to the number of vertices in the graph。

 not always necessarily to the number of edges in the graph。😊。

Though you always notice that this is going to have a plus component。

 so you're always going to be bound by the n squared。

 so you're going to see that just like M login and Kskotgon prints algorithmm is going to have the final running time。

The big idea to take away from this is we can find a minimum spanning tree using one of two different algorithms using those different algorithms。

 we're going to exploit data structures that we already know to build that minimum spanning tree and the time it takes to build that minimum spanning tree is going to always be proportional to the number of edges in the graph times the log of the number of edges in the graph。

 no matter what algorithm we use。😡，And in a dense graph。

 you're going to find that that runtime is going to be M log M in both cases。

We've learned a lot about minimum spanning trees， and we know a lot about how we can build in a really fascinating data structure that lets us dive into doing absolutely amazing things with graphs。

We're going to use our knowledge of mini spanning tree to now solve a real problem that a lot of us have。

 which is how do we find the shortest path from point A to point B on a graph from any two random vertices。

 We'll dive into one of the most famous algorithms in computer science。 Dykesch's algorithm。

 First thing next week。 I'll see you then。😊。

![](img/25ce2acff467dfa7356a2cb50c85439c_3.png)