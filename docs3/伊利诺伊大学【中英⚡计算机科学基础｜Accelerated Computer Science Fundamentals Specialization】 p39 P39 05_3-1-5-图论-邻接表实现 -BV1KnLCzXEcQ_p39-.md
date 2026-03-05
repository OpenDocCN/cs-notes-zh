# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p39 P39 05_3-1-5-图论-邻接表实现 -BV1KnLCzXEcQ_p39-

![](img/1f2cb00e6d64fd229392d1684900926c_0.png)

![](img/1f2cb00e6d64fd229392d1684900926c_1.png)

The third and final implementation of a graph that we're going to talk about is the adjacency list implementation。

 this combines some of the features of both of our implementation so far into this new structure that's going to have some unique properties。

Let's take a look。Here we have the exact same setup， we have a vertex list。Over here。

 and this going to be， again， implemented as a hash table。 So we have nice O of1 access time。

 and we have our same edge list。Over here。What we're going to do an adjacency list is we're going to maintain a linked list of all adjacent edges to a given vertex。

Off of the vertex list。So this means that off of you。

 I'm going to have a linked list that contains the fact that I have E A。

 as well as the fact I have edge C。That are instant to our vertex U。What this means is that here A。

 I'm not just goingm to store A， but I'm going to store a pointer。2 a itself。

 and a pointer to my edge C itself。😡，Here， instead of storing U and V。

 you can simply store a pointer back to where its location is。

 so this is use location inside of my adjacency list。

And this is a pointer to use location inside of my adjacency list。Here。

So what we have is we have pointers that come off of a linked list inside from our set of vertices。

That link back to the edge list and the edge links list then links back to the linked list element inside of my adjacency list。

 So we have pointers that are going both between my list of nodes as well as my list of edges。

 and this becomes a huge mess of different pointers。

Let's look at another one to kind of see how this starts to build out。

Look at an OW to give myself a little bit of space。We're going to see it W。

Has our first edge is going to be。Theen E W， this is E C。So this will have a pointer to edge C。

This W pointer inside E C is going to point back to the W node。

This node itself has a next pointer that's going to point to my next edge。

 which may be edge B that connects V and W。So again， pointer to the edgeless node for B。

And our W back to our location in our list W， the very last node is node D。

D again points to D and W points back to this node。So what we have is we have this。

Totally connected world， where we've got all these pointers interconnecting with between the edge list and the actual implementation of our node list。

And this is a crazy mess of pointers。Complicated to think about and implement。

 but let's see how great the running times are。If we want to insert a vertex。

 all we need to add is add the new vertex K here at the bottom。 and there's nothing else to do。

 We don't have to worry about creating an initial linked list because the initial linked list will just be a null pointer and we don't have to worry about adding anything to the edgeless structure。

 So insert vertex is just going to be our O of one amortized time。 the same as an edge list。

The remove vertex， on the other hand， though， is going to be slightly more complicated because imagine removing the vertex W。

😡，Removing the vertex W is going to require not just removing the vertex W。

 but also cleaning up this data structure of all of the edges。So in removing the vertex W。

 we're going to want to make sure that we move through all of the degrees of vertices and remove all of the associated nodes This is going to run in terms of the number of degrees。

Of。The vertex that we're going to try and remove。 This allows us to maintain the data structure。

 removing every single point of the way。Our adjacent is going to be an operation that we can now find is relatively quick。

 but not as quick as O of1。 So imagine if we need to find if U and W are adjacent here we need to either travel to use list and see if any of the pointers inside U points to a vertex that has V connected to it or go through all of the things in W and point to a vertex that has W connected into it。

Doing so is going to take us either to degree of V1 or the degree of V2。

 since we have to go through every single instant edge in their list。So that total。

 the totality of this running time is going to be the minimum of those two nodes of those two values。

So the minimum of those two values is going tell us the smallest list we have to go through。

 and we can go through the smallest link list。 So it's not quite over one time。

 It's not as good as an indjacency matrix， but it is pretty good。And finally。

 to find out the number of instant edges， we simply need to walk the link list。

 so this is going to simply be degree of V。So we've done a lot of analysis。

 and we've talked about a lot of different algorithms。

 The big picture of all of this is going to be a table that compares everything together。

 So let's look at that。Here is all of the different implementations built in a single table。

And let's look at this table。So the amount of space it's required。Is going to be。

N plus M for the edge list and the implementation list an adjacency matrix。We don't need n plus M。

 We actually need n squared time， where an adjacency list requires n plus M time。

So we can see that in an adjacency matrix， we're going to have the most space because that matrix can become huge。

 it's going to be squared by the number of nodes in the actual implementation。The insert vertex time。

 it's going to be constant time in an edgeless and adjacency list as we discussed， which is great。

Only an adjacency matrix is going to require linear time。 The remove vertex。

 we can discuss remove vertex as the actual mechanism。

 just remove the vertex or removing the vertex in all the edges。

 So give an apples and apples comparison。 I'm going to examine all of these algorithms by removing the vertex and removing all of the associated edges。

To remove the vertex and the associated edges requires us to go through the edgeless in our edgeless implementation。

It requires us to go through our entire matrix and our adjacency matrix。

 but only requires us to go through the linked list in our adjacency list implementation。

 just requiring a degree of V operations。 This is the best algorithm here。

To insert an edge requires o of one time in every single case， we can simply add it to the edge list。

 so they're all great implementations。 Likewise， removing an edge is also a constant time operation。

Finally， the set of instant edges， something we've talked about with all of these algorithms。

 to find the instant edges and an edge list， we have to go through the entire edge list。

 find the instant edges in adjacency matrix， we have to go through all of the nodes and to find out the adjacency list in all of the adjacency list implementations。

 we can just simply do degree of V。 so this is going to be the optimal algorithm here。And finally。

 if we want to find out if two nodes are adjacent to one another。

 we see that an adjacency matrix has this amazing constant time runtime。

 while a adjacency list has the minimum degree， so it's a worse runtime。

The big thing to take away is there is no clear right answer。

 so I circled and put a check mark by by the best category for every single row。😡，In doing so。

 we see the adjacency matrix is superior if we care about the R adjacentcent operation。

 it's the only one that has the best R adjacency running time。But on the other hand。

 if we care about inserting and removing vectors as well as checking out the list of all of the instant edges。

 we can see the ideal running time is going to be here for an adjacency list。Or in some cases。

 just as great for an edge list。So there is no single algorithm that works best for all applications。

 instead， as we dive into the different applications of graphs。

 we're going to look at what implementation of a graph is best to use and how and when we should use our different implementations。

😡，We'll dive into this next week as we start talking about doing awesome things with graphs。

 I'll see you then。

![](img/1f2cb00e6d64fd229392d1684900926c_3.png)