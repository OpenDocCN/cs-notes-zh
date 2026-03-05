# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p43 P43 01_4-2-1-最小生成树（MST）简介 -BV1KnLCzXEcQ_p43-

![](img/6169e9a46b331cfea0d53641a158ef8c_0.png)

![](img/6169e9a46b331cfea0d53641a158ef8c_1.png)

In the past couple of weeks we've introduced the idea of graphs and we've deen into how we can do a simple traversal on a graph using a BFS or DFS traversal as part of a BFS traversal。

 you notice that we created a spanning tree that allows us to span the entire graph。This week。

 we want to focus on creating a minimum spanning tree。

 We want to find the tree that can be placed over a graph that connects every single vertex in the graph。

Using the the total number of edges or the minimal weight of all of the edges among the graph。

So let's look at what we mean。Here are inputs always going to be some undirected graph G with usually edge weights that are unconstrained。

 but they have to be able to be added together。 so we normally will just use integers。

 but we can think in certain applications these may be more complex formulas that can simply be added together。

😡，So given this graph G with edge weights， we know that we want to create a graph G prime that happens to be a spanning tree of the graph。

 it needs to be a tree so it needs to not have a cycle because it needs to visit every node exactly once and not have any of those back edges。

And it has a minimal total weight across all of the possible spanning trees。

 so you can imagine there's a lot of different ways to draw paths that connect every single node。

 but we want to know how can we draw a tree that connects every single node in the minimal possible way。

And there's going to be multiple different algorithms that we can build to figure out how that we can connect these two of the algorithms we're going to discuss is going to be Csco's algorithm and Pris algorithm。

 They're both going to take different approaches to building the absolute smallest possible tree。

 given a sequence of edge weights。That spans the entire graph。

This is going to be a really important application whenever we want to see what is the connectivity of any given system and how can we easily minimally travel between two different locations。

 So the next video we'll start diving into the first of these algorithms。

 Kshcro algorithm and learn about how it forms a minimum spanning tree on any given graph。

 I'll see you then。😊。

![](img/6169e9a46b331cfea0d53641a158ef8c_3.png)