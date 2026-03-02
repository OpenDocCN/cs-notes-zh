# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P160：32_04_02_最大割问题一.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

In this sequence of videos we're going to discuss an important。

 if somewhat poorly understood approach to tackling MP complete problems namely local search Before I discuss the general principles of local search algorithms。

 I want to begin with a concrete example that's going to be to the maximum cut problem。

Some of you might remember that we studied the minimum cut problem in part one of the course in particular Car's randomized contraction algorithm。

 that problem was defined as seeking out the cut of the graph that minimizes the number of crossing edges。

 the maximum cut problem naturally enough we want the cut that maximizes the number of crossing edges。

More precisely， were given as input and undirected graph G。

 and the responsibility of the algorithm is to output a cut that is the partition of the vertices into two non- empty sets A and B that maximizes the number of edges that have exactly one endpoint in each of the two groups of the partition。

In the quiz on the next slide， I'll give you an example to make sure that this definition makes sense before that just a couple of quick comments。

So first， sadly， unlike the minimum cut problem， which we saw in part1 is computationally tractable。

 the maximum cut problem in general is computationally intractable， it's NP complete。

 more precisely the decision version of the question where you've given a graph you want to know whether or not there exists a cut that cuts at least a certain number of edges。

 that's an NP complete problem， there's no polynomial time algorithm for it unless P equals NP。

Like most MPcomplete problems， there are some computationally tractable special cases， for example。

 of the case of bipartite graphs。One definition of a bipartid graph is a graph in which there exists a cut so that every single edge is crossing it。

 and then obviously that would be the maximum cut of the graph。

A slick way to solve this problem is in linear time is to use breath first search。

 you just root the breath first search at an arbitrary vertex of the graph。

 you draw your breath first search tree， you put the even layers as one of your groups A。

 you take the odd layers and make it the other group B。

 this will have no crossing edges if and only if the graph is bipartid。

To make sure the definition of the maximum cut problem makes sense。

 what is the maximum cut in the following six vertex graph？So the correct answer is C8。

 that's because the graph is biidite， there's only eight edges and there is indeed a cut in which every single one of those edges crosses it。

Specifically， take one group to be the vertices W and X。And take the group B to B， the vertices， U V。

 Y， and Z。There are no edges internal to A。 There are no edges internal to B。

 Every edge has one endpoint in each。

![](img/806b5c858606245fd5edbaf7c4c5fae2_1.png)

So while the max cut problem is computational taste tractable in bipartid graphs like this one using breathth for search。

 it's MP complete in general， Moreoverover， breath first search turns out to be not a very good heuristic for approximating the maximum cut problem in general graphs。

 we're going to have to turn to other techniques。There's a number of interesting heuristics for the maximum cut problem。

 but I want to use the problem here to showcase the technique of local search。

Local search is a general heuristic design paradigm。

 but I don't want to describe it in general until the following video after we've gone through this concrete example。

 but at a high level you should think of it that we're always maintaining a candidate cut and we just want to iteratively make it better and better via small that is local modifications。



![](img/806b5c858606245fd5edbaf7c4c5fae2_3.png)

To succinctly state the algorithm， I'm going to need a little bit of notation。

 So imagine that we have some undirected graph and we're trying to approximate the maximum cut。

 and suppose we have some current candidate cut A comma B。 Some of the vertices are in A。

 the rest are in B。 Now， focus on some arbitrary vertex V。 V could be an A or B。 I don't care。

 There is some incident edges to this vertex V in the graph on the right I've shown you a vertex V。

 it has degree 5，5 incident edges。 Now， some of these edges are crossing the cut。

 Some of the edges are not。 So I'm going to use the notation C sub v of A B to denote the number of v's incident edges that are crossing the cut。

 and D sub v of A B to denote the edges， the number of edges which are not crossing the cut。

 So in the picture that I've drawn C sub v would be equal to 2 D sub v would be equal to 3。

Here then is the local search algorithm for maximum cut and step one。

 we just begin with an arbitrary cut of the graph， so we just somehow。

 I don't care how put some of the vertices in A， some of the vertices B。

Now we just iteratively try to make the cut that we're working with better until we don't see any easy way to improve it further。

So what's a principled way to take a given cut and make it better？ Well。

 let's just focus on very simple modifications。 Let's suppose the only thing we're allowed to do is take a vertex from one of the two groups say from group A and move it to group B。

 For example， in the green network I've shown you on the right hand part of this slide。

 if we envision taking the vertex V and moving it from a to B， we get a superior cut。

 Why is that true， Well here are the two ramifications of moving V from A to B。 So first of all。

 the two edges incident to V that used to be crossing the cut they no longer cross the cut when we put V over on the right hand side。

 the two edges whose other endpoints are in B， those edges get sucked in internal to B。

 they are no longer crossing the cut On the other hand。

 the good news is is that the three edges incident to V with the other endpoint in A。

 they used to be internal to the group A， but when we bring V over to the right hand side to the group B。

 Now those three edges cross the cut。 So we lost two edges from the cut。But we gained three。

 so that's a net improvement of one more edge crossing the cut。In general。

 this argument shows that for any vertex so that the number of edges incident to it that are not crossing the cut。

 if that's bigger than the number which are crossing the cut incident to it。

 then switching sidess with that vertex will improve the cut and the improvement is exactly the difference between the two quantities。

 D sub V and C sub B。If we find ourselvesse with a cut such that there's no vertex switch that improves the cut。

 that is if D sub V of AB is at most C sub V of AB for every single vertex V。

 then we stop and we just return to the cut that we ended up with。

We typically evaluate algorithms along two axes， so first of all， how good is this solution。

 so for example， is the algorithm always correct or at least approximately correct and secondly。

 what resources does it require so for example， is the running time reasonable。Now， to be honest。

 local search algorithms often perform poorly， at least in the worst case。

 along both of these criteria。 This local search algorithm for the maximum cut problem is interesting in that we can say nontrivial positive things。

 both about the solution quality and about its running time。

 The running time amount follows easily from an observation that we made earlier。

 namely that every time we do an iteration of the while loop。

 Every time we switch a vertex from one side to the other。 The number of crossing edges goes up。

 necessarily by at least one。 So I'm going to assume that the graph is simple that there's no parallel edges。

 in which case is at most n two edges in the graph。

 That means that this while loop can only execute in total and n2 or quadratic number of times。

It's easy to implement each iteration of the wild loop quickly。

 so that means this overall algorithm will terminate in polynomial time。



![](img/806b5c858606245fd5edbaf7c4c5fae2_5.png)

Now this local search algorithm does not solve the maximum cut problem optimally。

 it is not guaranteed to return the maximum cut， Indeed。

 that would be way too much to hope for now that we know that it runs in polynomial time。

 remember the maximum cut problem is NP complete。

![](img/806b5c858606245fd5edbaf7c4c5fae2_7.png)

However， interestingly， this is a heuristic with a good worst case performance guarantee。



![](img/806b5c858606245fd5edbaf7c4c5fae2_9.png)

Precisely， the outcome of this local search algorithm is guaranteed to be a cut in which the number of crossing edges is at least half at least 50% of the maximum possible。

In fact， something stronger is true， it's even guaranteed to be at least 50% of all of the edges of the graph。

 which of course is an upper bound on the maximum number of edges crossing some cut。



![](img/806b5c858606245fd5edbaf7c4c5fae2_11.png)