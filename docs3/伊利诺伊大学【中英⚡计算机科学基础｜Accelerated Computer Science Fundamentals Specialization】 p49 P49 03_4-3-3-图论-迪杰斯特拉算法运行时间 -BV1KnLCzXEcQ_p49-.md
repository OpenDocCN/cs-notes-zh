# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p49 P49 03_4-3-3-图论-迪杰斯特拉算法运行时间 -BV1KnLCzXEcQ_p49-

![](img/699fc50d8e4eb986083d8df3e527d38e_0.png)

![](img/699fc50d8e4eb986083d8df3e527d38e_1.png)

Right now you understand how to use Dykes's algorithm and all of the intricacies of how to run Dyk shywim。

 the last thing we want to discuss real fast is just do a quick discussion of the running time of Dyke's algorithm。

So if we think about the total running time of Dyter's algorithm。

 we know that the running time is going to be very similar to the algorithm that it's based on。

 In fact， let's do a little analysis and see how this differs from Prim's algorithm。

Here we see that just like Prim's algorithm， we're going to construct a graph that's going to have every single vertex that's part of this graph。

 We're going to build a priority queue of vertices and go through every vertex on the graph just as we did with PRm's algorithm。

At every single vertex， we're going to remove the minimum vertex and then go through all of the edges。

 and as we find an edge that's smaller， we're going to update the weight of that edge。

So here we see that the updated cost of the edge only happens when we need to decrease。

And using a special type of heap called the Fibonacci heap， we're able to optimize。

The Dicure's algorithm running time to an amazing runtime that's going to run the exact same way as the best optimization of PRs algorithm。

 So the total running time here is gonna be order of M， the number of edges plus in log in。😊。

The total number of nodes in the graph times the log and the number of nodes in this graph。

 This running time is the absolute best running time that you can get in any shortest path algorithm。

 So even though it's a little bit more than a traversal。

 It's a little bit more than an imp plus an algorithm that extra log in to the in allows us to find the shortest path while just traversing over all of the edges and nodes。

 this is absolutely fantastic runtime and is a great way to find a shortest path and is the optimal algorithm to do so out of every algorithm that exists。

😊。

![](img/699fc50d8e4eb986083d8df3e527d38e_3.png)

![](img/699fc50d8e4eb986083d8df3e527d38e_4.png)

Now that you understand the running time of Dke's algorithm and you have a complete understanding of it。

 let's look at one of my favorite problems in all of computer science。

 and you'll see this as a fun way of seeing which algorithms should apply for a real life problem。

I look forward to showing that to you， and I'll see you there in the next video。😊。



![](img/699fc50d8e4eb986083d8df3e527d38e_6.png)