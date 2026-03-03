# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P149：21_02_01_顶点覆盖问题.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

In this video and and the next， we'll develop an exact algorithm for solving what's called the vertex cover problem。

 This is a well known MP complete problem。 As such。

 we certainly don't expect our exact algorithm to run in polynomial time on general instances。

 But the algorithm does showcase two of the algorithmic strategies that we discussed for dealing with N P complete problems。



![](img/96063ed389151753d0b41c32490aed66_1.png)

First of all， we can interpret this algorithm as on general instances。

 while it's true running an exponential time， nevertheless improving markedly over the more obvious naive brute force search。

 This illustrates the point that from any MP complete problems。

 there is a lot of room for algorithmic ingenuity， even though you're not going to come up with a polynomial time solution。

A second interpretation of the algorithm we're going to develop is that it's polynomial time for special classes of instances。

 in particular， instances that have an unusually good optimal solution。

So let me introduce you to the vertex cover problem。The input is simply an undirected graph。

The goal is to identify the smallest size that is the minimum cardinality of a vertex cover of the graph。

What is a vertex cover， we call a subset of the vertices， a vertex cover。 If for every edge。

 at least one， possibly both of the edges end points lie in the set S。There is。

 of course always a feasible solution， you could always choose every single vertex that's certainly going to be a vertex cover。

 but the hard question is how do you make sure you get one endpoint from each edge in the most parsimonious way？

So what might this problem represent， well perhaps you're assembling a team of some sort。

 so maybe a team of programmers， maybe of lawyers， maybe a football players who knows。

 but think of the vertices as being potential people that you could recruit onto your team and think of an edge as representing a potential task that your team might have to complete and the two vertices in the edge represent the two people who are capable of accomplishing that task。

 so then what a vertex cover is it says hire enough people so that every single task you can accomplish。

 you have one of the two people in your team that's capable of accomplishing that task。

So you could of course imagine various generalizations of this problem。

 you could have a weight for each vertex， for example。

 indicating the salary that you'd have to pay that person。

 you could also imagine that instead of edges you have what are called hyper edges if more than two people are capable of accomplishing a given task。

 but the unweighted graph vertex cover problem will be interesting enough for our purposes here。

Many people are of the opinion that this is a poorly monitoriked problem。

 many people think it should be called the edge cover problem， not the vertex cover problem。

 because you're choosing vertices to in some sense cover the edges by picking at least one of their endpoints。

 but this is the conventional name for this problem in the vertex cover problem you're choosing a set of vertices and edges provide the constraints。

Let's now jump to a quiz to make sure the problem definition is clear。

So the correct answer is a let's consider each of the two graphs in turn。

 Let's start with a star graph on n vertices。 so this has one vertex in the center and n-1 spokes。

 The claim is it has a vertex cover of size1。 Obviously the minimum possible that vertex cover comprises just that center vertex Why is it a vertex cover while every single edge is a spoke and one of its endpoints is the center vertex So you just pick the one vertex and you hit all of the n minus-1 edges of the graph。

So how about a cl on n vertices。 So a graph in which every single one of the n choose two edges is present。

 Why is n-1 vertices necessary and sufficient for a vertex cover， Well， to see why it's necessary。

 consider any set that excludes at least two vertices of the graph。 because it's a clique。

 there's an edge between those two excluded vertices。

 And that's an edge such that neither of its endpoints is in this set。

 So that's why the set is not a vertex cover。 If it has the most n -2 vertices in it。

 On the other hand， if it only excludes one vertex。

 then there cannot be an edge with both of its endpoints missing from the set。

 because there's only one vertex in total missing for the set。

 So that's why any subset of n-1 vertices will be a vertex cover of a clique and-1 is sufficient。

Figuring out the minimum size of a vertex cover in these two special graphs probably didn't seem that hard and it's not。

 but when you're talking about general graphs that you don't know anything about。

 computing the minimum cardinalityality vertex cover is in fact an NP complete problem there is no a polynomial time algorithm that solves it unless P equals NP。

So that's definitely a bummer。 So let's review our strategies for dealing with NP complete problems that we discussed in an earlier video。

So the first strategy is to identify computationally tractable special cases of your NP complete problem。

Now， in the best case scenario， the version of the problem that you have to solve in your own application lies squarely inside one of these computationally tractable special cases。

 then you're good to go。More commonly， the instances that arise in your application won't necessarily be in one of the computationally tractable special cases。

 but it can still be useful to have subroutines ready for various special cases。

 One thing we discussed in the past is the potential of a hybrid approach。

 perhaps you do a little bit of brute force search。

 and for most of the branches of your brute force search。

 the residual problem falls into a computationally tractable special case。

And it turns out there's some quite interesting， computationally tractable special cases of the vertex cover problem。

 And the story here is very much in parallel with discussions we've had in the past about the independent set problem。

So in particular， you can solve vertex cover in polynomial time on path graphs。

 just like we did with independent sets， actually more generally in trees or even more generally in what's called graphs of bounded tree with。

 But at least for trees， that's a application of dynamic programming。

 which you're now in a good position to solve yourself。

 So I encourage you to think that through as an exercise。

 why can you solve the vertex cover problem in polynomial time in trees。

So another quite interesting class of graphs where you can solve the vertex cover problem in polynomial time is the class of bipartite graphs。

 One way to think about a bipartite graph it's a graph that has no odd cycle so then obviously trees are a special case an equivalent definition is that you can partition the vertex set into two groups A and B so that every single edge has exactly one endpoint in each of A and B。

 that is bipartite graphs can also be thought of the graphs for which there's a cut that slices every single edge of the graph。

It's far from obvious how to solve the vertex cover problem efficiently in bipartite graphs。

 but it can be done its an application of what's called the maximum flow problem。

 that's a graph problem which lies just beyond the techniques that we're covering in this class。

So what I'm going to cover in the next video is using a different algorithm。

 yet another computationally tractable special case of vertex cover。

 specifically when you're interested in the case that the vertex cover is small。

And what I mean here by small is logarithmic in the number of vertices or less。



![](img/96063ed389151753d0b41c32490aed66_3.png)

A second strategy for dealing with NP complete problems is to relax the requirement of correctness and to focus on heuristics。

 algorithms that are fast but need not produce an optimal solution。

So there are some pretty good heuristics available for the vertex cover problem。

 I'm not going to discuss them here because I think that time will be better spent discussing heuristics for the Napsack problem。

 but you can， for example， use the greedy algorithm design paradigm to generate some heuristics for vertex cover Now some greedy algorithms do better than others。

 but if you make the greedy choices judiciously， you can get pretty good guarantees for the vertex cover problem。

So the third strategy is to insist on correctness， in which case you're not expecting to get polynomial time for general instances unless your intent on proving P equals NPp。

And so while you're expecting an exponential running time。

 you still want a running time which is qualitatively better than naive brute force search。

And this is exactly the point of the next video， we're going to give an algorithm which is indeed based on enumeration。

 but it's a smarter enumeration than naive brute for search。

 so we'll get a faster exponential running time and that'll allow us to solve a wider class of problems。

