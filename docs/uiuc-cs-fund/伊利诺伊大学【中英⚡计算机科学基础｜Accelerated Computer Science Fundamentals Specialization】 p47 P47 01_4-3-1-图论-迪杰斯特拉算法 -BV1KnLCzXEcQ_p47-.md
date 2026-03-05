# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p47 P47 01_4-3-1-图论-迪杰斯特拉算法 -BV1KnLCzXEcQ_p47-

![](img/511e7be4a9023a2c92dd44f815bfccee_0.png)

![](img/511e7be4a9023a2c92dd44f815bfccee_1.png)

One of the most famous algorithms in computer science is Dysch's algorithm。This algorithm is very。

 very similar to an algorithm we covered last week。 Prims algorithm， but it's completely different。

In this sense that instead of finding a minimum spanning tree。

 Dure algorithmm is going to find us the shortest path on a graph。

Let's see how the actual algorithm works。Looking here at this graph。

 we have a series of nodes as well as edges that connect it。

 Notice these edges are directed edges that they have a source node and a destination。

 So every edge has an arrow。And in Dexter's algorithm， we have the code right here to the right。

 You'll notice the first few lines of code sets up a for loop that goes through every single vertex on a graph。

And labels the distance to that vertex infinity and the previous pointer is null exactly how Pris algorithm did it。

 Then we sent our initial vertex to 0。We set up the same priority queue that is defined in terms of the distance to every single vertex。

 we build a heap so that we can have a priority queue of that。

 and finally we set up a graph that is going to be our labeled set of nodes that we have labeled。

Finally， we're going to repeat for every single node， and we're going remove the minimum node。

 add it to our labeled set。 And as we go through all of its neighbors。

 we're going to be updating the weight just as we've done with Prems algorithms。

 So nothing here is new。The only difference now is as we update the weight。

 if the weight is lower than what we have currently stored。

 so if the weight is lower than positive infinity， we're going to update it only if not just the edge weight is lower。

 but the entire distance from the root node or the starting point。To the new point。So does that mean。

 let's go ahead and run the algorithm a little bit。 starting at node A， we know a node As value is 0。

 and every other node's value is infinity。When we visit A， we're going to add a to our labeled set。

 so it is now labeled， and we're going to update all of the edges that come out of A。

 so now B's weight is 10。And F's weight is seven。WeWe've now labeled every single edge。

 so now we get to remove another element and add it to the labeled set。 Here we remove element F。

Element F is the minimum weight element along all of the nodes。We remove it。

 and now we have a labeled set that contains both A and B。

 updating all the nodes that are adjacent to F。 We see that the weight of E in Pris algorithm。

 we would update to just 5 because the weight of the edge that leads across the labeled set to the unlabeled set is just 5 In D's algorithm。

 the big difference is we're going to not just update it to be 5， but update the entire cost from a。

 So that means we're going to add it to the cost that F contains。 So F has the cost of 7。

7 plus5 is 12。So the value of E is 12。Likewise， the weight that we're adding to G is 5 plus 4 or 11。

So now we see we have three edges that span the set division， the set partition。

 we have a weight of 10， a weight of 11 and a weight of 12。

 the minimum wage edge that spans partition now has that weight of 10。

 and we go ahead and add B to our labeled set， we can update our partition。

And now we update the weights。 So B to C is 10 plus 7 or 17。And now going from B to D is 10 plus 5。

 which is 15。So here we have our labeled partition again。And now we find the minimum weight。

 the minimum weight is G， we add G， we update the edge weights， G to E is 11 plus 2， which is 13。

 it's not smaller than 12， so we don't update that partition right here。

And that's the only edge we need to update now the smallest number is 12。

 so we add E to the list 12 plus 6 is 18， we don't update the CE edge。

And there's no other outbound edges。 We update our partition again。And。Finally。

 the smallest edge here is now D， so we go ahead and update this partition。And finally， we get to 17。

 we add 17， and then we add 21。 So what we've done is we've ran the exact same thing as we ran with Pris algorithm。

 except for the only difference between Pris algorithm and D's algorithm is that every single point instead of just updating the weight of the edge。

 we actually sum the weight it took us to get to the edge that we're leading from and added it to the weight of that edge。

 So we're getting the total distance from our source node from a all the way down to whatever the node we just discovered is。

So if we complete this entire algorithm， you can see we fill this algorithm in with a little bit of code that calculates the sum of the two costs。

 So you can see here I filled in lines 1920 and 21 with this sum that adding the cost。

Of the path U to V plus the new path that we just。Arrived that if that sum is less than the current node stored。

 we go ahead and update it。As we run the algorithm， we'll see that we get this graph right here。

This graph is going to be a graph that。Labels the entire shortest path and labels every single shortest path from the distance from our starting node to whatever other node we are the graph。

 So if I want to know distance from A to E， I can simply look at the result of this table。

 and I know that get from A to E， I have to go via F。F goes via a。

So my path goes EFA or AFE in in the forward form and the distance is 12。

 you can see that using this table that we generate through Dictures algorithm。

 we know the precise path to every single node from A using Dicure's algorithm。Because of this。

 we call D algorithm a single source shortest path or an SSSP algorithm。

Dex Shagrim takes a single source， in this case， our single source was a node A。And from node A。

 it finds the shortest path to every single other node in our connected graph。

 This means we know the distance from A to B， A to C， A to D， A to E。

Dure algorithmcrorim only finds us a single source shortest path。

 so we have to give it a source node， and it was always going to start from that source node。

 does not know the path from B to D unless we make B the source node。

We're going to dive a little bit more into how we can apply di algorithm and the things we can do with it in next lecture。

 so I'll see you then。

![](img/511e7be4a9023a2c92dd44f815bfccee_3.png)