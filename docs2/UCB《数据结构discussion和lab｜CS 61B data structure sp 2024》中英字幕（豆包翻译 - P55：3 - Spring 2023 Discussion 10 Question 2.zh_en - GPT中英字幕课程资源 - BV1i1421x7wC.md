# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P55：3 - Spring 2023 Discussion 10 Question 2.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/49950c0d026714a7063ef4547216e1a0_0.png)

Okay， let's now go over question two， minimalistmos。In 2A。

 we are asked to find a valid MST first using crustcos and then PRs。

And we're also given a tie breaking scheme which states that we choose the edge that connects vertices of lower alphabetical order。

Let's run Cruscoll's algorithm first。Recall that in Kscoll's algorithm。

 we are repeatedly adding the lightest edge that doesn't create a cycle until we have added all nodes in the graph to our MST。

Let's take a look at our craft。Currently， our MST does not contain any nodes so we can go into the while loop。

And when we're inside our while loop， we add the lightest edge that doesn't create a cycle。

Looking at our graph， we see that the current lightest edge。Is edge A C with weight 1。

So we add this edge to our MST and then we add the endpoints of this edge to this set of nodes in our MST。

So now our MST contains the notes， A and C。There are still nodes not in our MST。

 so we continue with the while loop。Once again， we add the lightest edge that doesn't create a cycle。

So we look in our graph and the next lightest edge is edge C。With weight too。

So we add the endpoints of this edge to the set of nodes in our MST。

 so now our MST contains the node A， C， and E。B and D are not yet in our MST。

 so we continue with the while loop。We add the lightest edge that doesn't create a cycle。

Here we have two choices of edges， we can either pick E C D。Or edge D E。

 because both of these edges have weight three。Here we use our tie rating scheme to determine which edge to pick。

Because we want the edge that connects vertices of lower alphabetical order。We pick E C， D。

So now we add the endpoints of this edge to the set of nodes in our MST。

So now our MST contains the node， A， C， D， and E。There is still one more node that is not in our MST。

 so we continue with the while loop。And now we add the lightest edge that doesn't create a cycle。

So our current lightest edge is the edge connecting D and E because it has weight three。However。

 if we add this edge， it would create a cycle in our graph between C D and E。Because of this。

 we can't add DE so we basically ignore it and move on to the next lightest edge。

So now we look at our next latticeest edge and we see that we have two possible options here again。

We have edge A B and E B C。Both of these have weight for。

So using our tie breaking scheme to pick the edge connecting vertices of lower alphabetical order。

We pick edge A B。And we add its endpoints to the set of nodes in our MST。

 so now B is in the set of nodes of our MST。So now we check are all of the nodes in our graph and our MST。

Now all of the nodes in our MST are indeed in our graph， and we see that we have A， A B。C， D and E。

So we are done with the while loop。And this is the MST we get from Kscoll's algorithm。

Now let's perform Prim's algorithm on this graph。In Pris algorithm。

 we are starting with a node and we are continually adding edges that connect from。

Nodes with that are in our MST to nodes that are not in our MST。

So here we are starting with vertex A。So we add vertex A to the set of nodes in our MST。

And while there are still nodes not in our MST， we add the lightest edge that leads from a node in MST to a node that is unvisited。

Since a is currently the only node in our MST， we can only look at edges that connect from a to some other vertex。

So here there are three possible edges we can pick from。Aby。A C。And A D。Out of these three。

 we see that AC has the lowest weight with edge weight one。

 so we pick this edge and add it to our MST。And now we add the new node to the set of nodes in our MST so。

Our MST now consists of the nodes A and C。There are still notes that are not in our MST。

 so we continue with the while loop。Once again， we want to add the lightest edge from a node in our MST。

To a node that is not in our MST。So looking at all the edges that connect off a or C。

 we see that the lightest edge is between C and E。With weight， too。

So we add this new node to the set of nodes in our MST， so now our MST has the nodes A C， and E。

B and D are not yet in our MST， so we continue with the while loop。

We want to add the lightest edge from a node that's in our MST to a node that is not yet visited。

Here we have two choices we can either go from C to D or we can go from E to D。

Both of these edges have weight three。So we use our tie breaking scheme to pick the edge that has lower alphabetical order。

And we see at this edge， iss C D。And now that we have visited D。

 we add it to the set of nodes in our MST。So now our MST consists of A， C， D， and E。

We haven't yet added B to our MST， so we continue with the while loop。

So we look for the lightest edge that leads from a node in our MST to the final node we haven't yet visited。

 which is B。So we have two options here， we can either go with A B or we can go with C B。

Both of these edges have weight for。So we use our type breaking scheme to pick the edge of lower alphabetical order。

And that gives us A B。And now we add B to the set of nodes in our MST。

Now let's check have we added all the nodes in our graph to our MST？In this case， the answer is yes。

 here。 we can see that we can go from A B。See。D， and E。So we are done with the while loop。

And this is the MST we get from running Pris algorithm on this graph。Now let's move on to2B。

Now we're being asked， did crustcos and Pris find different MSTs or did they find the same MST？

And more generally， is the MST for this graph unique that is。

Does this graph only have one MST or does it have multiple valid MSTs？Well。

 here we can see that previously， given our tie breaking scheme of always choosing the edge of lower alphabetical order。

 both of these algorithms would find the same MST。But if we take a close look at our graph。

 we can see that it has two edges of weight three， that is Edge CD and E DE。

We also have two edges of weight4， AB。And Bc。So if we use a different tie breaking scheme。

 maybe sometimes we would pick AB and other times we would pick BC。So for example。

 instead of our current tie breaking scheme， what if we just picked an edge randomly if we had to decide between two of them？

And sometimes when we are crafting our MST。Sometimes edge C gets picked。

 but other times our type breaking scheme tells us pick edge ED。

So we can see that if we change our tie breaking scheme。

 we could potentially end up with all sorts of different MSTs for this graph。

Examples of which are given here。So here edge AB was picked instead of BC and here BC was picked instead of AB。

 both of these edges have weight four， so depending on our tie breaking scheme we can pick either one of them and similar。

Here for a C D and D E。That's it for question two。

![](img/49950c0d026714a7063ef4547216e1a0_2.png)