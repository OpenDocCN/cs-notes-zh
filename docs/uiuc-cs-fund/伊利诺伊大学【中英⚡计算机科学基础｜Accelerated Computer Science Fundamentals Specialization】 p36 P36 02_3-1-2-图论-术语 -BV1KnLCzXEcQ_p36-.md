# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p36 P36 02_3-1-2-图论-术语 -BV1KnLCzXEcQ_p36-

![](img/dfd65277a58d71900a576aa4b8a11023_0.png)

![](img/dfd65277a58d71900a576aa4b8a11023_1.png)

Before we dive into actually implementing graph， let's talk about a little bit of vocabulary about graphs so that we can have a common understanding of exactly what we're talking about。

Looking at a sample graph， we have a series of graphs here。

And I'm going to always refer to the big graph as the capital letter G。

 and G is a collection of vertices and edges。Here inside the graph G， we have three subgraphs， G1。

 G2 and G3。These graphs are disconnected because there is no edge thats shared between G1 and G2。

 but G1 itself is a connected graph because every node inside of G1 can be connected through to various edges。

I'll use the term node and vertex interchangeably。When I say node or when I say vertex。

 you can think of all of the sets of nodes or all the set of vertices。

 these two terms are completely indistinguishable。 If you come from a background of mathematics。

 you're probably used to the term vertex。 If you come from a background of networking。

 you're probably used to the term node。On the other side， the term edge is universally used。

So whenever you hear the term edge， that's always going to mean the connection between two nodes or the connection between two vertices。

 depending on the choice of words you use。We're going to define the variable in to be equal to the number of vertices in the graph。

😡，So if we count the number of vertices， that's going to be defined as n。

 if we count the number of edges， that's going to be defined as the variable M。

So NMM are going to be the two terms that we're going to talk about a lot。

A few different things to talk about when it comes to this graph。

 One term is we have the idea of an instant edge and edge is instant to the node if it is an edge that is directly connected to that node。

 So all of the nodes that all of the edges on a node are its instant edges。

Second thing we're going to talk about is the degree of a node。

 So the degree of the node is the count of how many instant edges it has。

 So if you look at how many edges are on this node， if that node， for example， here。

Has three instant edges。 So we say the degree of this node。Is three。

The third thing we can talk about is adjacent vertices。

 Adcent vertices is every single vertex is's adjacent to a node。 So if we。

Travel over all the instant edges and see which nodes are connected to it。

 Those are adjacent nodes or adjacent vertices， so we have the idea of a single node has a number of instant edges。

 those the number of instant edges it has is the degree of that node and the nodes on the other side of those edges are the list of adjacent nodes。

We can also have terms that you may remember from trees。 For example， we can have a path。

 A path is a sequence of vertices through a tree。The second thing is we can have a cycle。

 a cycle is a path that starts and ends at the same node， so if we travel through a bunch of nodes。

And now we have a path， this path is a circle， so we call this a cycle in the graph。

And we're going to this semester， we're going to mostly talk about simple graphs。

A simple graph is going to be a graph that has no self loops。

 so that means there is no edge that links back to itself because that's going to cause some problems as you're moving throughout the graph。

 you can simply go to your own location and there is no multi- edges that is there's no set of edges that connect two of the same vertices that if there's a connection between vertex A and vertex B there is exactly one edge that that goes between those two edges。

We've talked about already the term subgraph where we can have a subset of a graph and any subgraph is going to contain all of the vertices and all of the edges in that particular subgraph。

 You see， we have three subgraphs here， as I mentioned earlier。 And finally。

 we have a number of other terms that we'll introduce you to as we come across them。

 These are things like a complete subgraph， a connected subgraph， a connected component。

 acyclic graph， and then a spanning tree， which will dive into all of these terms as we get to them as we explain graphs。

 So this is just a little bit of vocabulary to ensure that we're on the same page as we talk about the graph algorithms that we're going to be talking about。

😊，So to begin kind of this discussion， let's do a little bit of math to find out things that we can know about a graph just from the terms that we've already been introduced to。

Part of that is going to be some simple questions on what it means to be a graph。

 so let's dive into these， so how many edges can exist on a graph？

That is the minimum number of edges on a not connected graph。So if the graph is not connected。

 we know that there does not need to exist any edges whatsoever。 A connected graph can be the graph。

 ABC。Which are all individual subgraphs with no connections。

 So the minimum number of edges on a not connected graph is 0。

Now consider if this was graph was connected， if we connect this graph。

 then we can see every node must be connected to every other node。

 so the minimally connected graph is going to be a graph where we have a path from one node to every single other node in the graph and only one path to get there。

Here is a minimally connected graph， you'll notice that we need exactly one fewer edges than we need nodes。

 so the minimum number of edges in a connected graph is going to be the total number of nodes。-1。

The next thing we can talk about is what is the maximum number of edges for this exact same thing？

So we're going to assume with most of our graphs that we're always going to have a simple graph。😡。

So always having a simple graph means there's no self edges and that there is no multi edges。

 So if we start drawing out graphs， we can see for n equals  one。

 we have just a single node for n equals 2。 We have two nodes for n equals 3。

We have three nodes and it's connected。N equals four， we have four nodes。

And we can see that these nodes are all connected。And we can look at how many edges this has when n equals one。

 number of edges is0， n equals  two edges 1 and equals 3 edges are 3 and equals 4。 We have 1，2，3，4，5。

6 edges。So this looks like a nice repeating sequence。And we can define this to be。

Our nice arithmatictic sum of in。Times n minus1 over2。

Which is equal to the order of in squared total edges。So for every single node。

 we're going to have edges out to every other node。 So it's basically itself。Times。

So in being the nodes itself。It's going to connect to every other node in -1 other nodes。

 But we know that only half those nodes， half those edges can exist because you're not going to have a node。

 an edge from A to B and B to A。 So we divide that total by 2。 This is exactly what we found。

 We found n times n-1 over 2 is a number of edges in a connected graph。Now。

 if the graph is not a simple graph where we can have multi edges。

 we can have an infinite number of edges before we run out of vertices to connect。

 because think about a graph with just two nodes， if it's not simple。

 we can have as many multi edges as we want。So you can imagine there is an infinite number of edges that it can exist in a nonsimple graph that's going to contain multi edges。

 So because of that， we're going to always constrain ourselves to simple graphs this semester。

 And in future courses， you can dive into exactly what it means when we start having multi edges。

Finally， the very last thing we can ask about is what is the sum of all the degrees of all the nodes。

 So if we think about the degree of a vertex， we know that's how many edges there are。

 If we sum all of them up， we know that there's going to be。

Every single out edge is going to eventually have an inbound edge。

So the degree of all of the vertices is going to be equal to2 m2 times the number of edges under the graph。

 because here we're double counting the edges。 One's going to be an outbound edge on A。

 the other one that we're gonna count as an inbound edge on B。

 because the degree of a accounts for the outbound edge and the degree of B counts for the inbound edge。

 Despite the fact that the inbound and outbound edge is exactly the same edge。

 It is the edge between A and B。 In the next lecture。

 we're gonna to start implementing the graphs and doing exciting things with C plus plus with graphs。

 I'll see there。😊。

![](img/dfd65277a58d71900a576aa4b8a11023_3.png)