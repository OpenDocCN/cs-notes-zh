# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P114：39_03_01_引言-路径图中的加权独立集.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/69e42e2f3330e7410ec0b61871515876_0.png)

So the time has arrived to begin our study of dynamic programming so this is a general algorithm design paradigm as I mentioned at the beginning of the course it has a number of justly famous applications。

 however， I'm not going to tell you just yet what it is that makes an algorithm dynamic programming rather our plan is over the next few videos to develop from scratch an algorithm for a non-trivial concrete computational problem The problem is finding the maximum weight independence set in a path graph。

This concrete problem is going to force us to develop a number of new ideas。

 And once we've finished solving the problem。 at that point， we'll zoom out。

 and I'll point out what are the characteristics of our solution。

 which make it a dynamic programming algorithm。 Then armed with both a sort of formula for developing dynamic programming algorithms。

 as well as a concrete instantiation， will move on to a number of further and in general harder applications of the paradigm。

 Indeed， even more than usual， the dynamic programming paradigm takes practice to perfect。

 And my experience， students find it counterintuitive at first。

 and they often struggle to apply the paradigm to problems that they haven't seen before。

 But here's the good news。 Dna programming is relatively formulaic。

 certainly more so than our recent study of greedy algorithms。

 And it's something you can get the hang of。 So with sufficient practice。

 And that's exactly what I'll be giving you over the next couple of weeks。

 you should find yourself with a powerful and quite widely applicable new tool in your programr toolbox。

😊，So let me introduce you to the concrete problem we're going to study over the next few videos。

 it's a graph problem， but a very simple graph problem。In fact。

 we're going to restrict our attention merely to path graphs。

 that graphs that consists solely of a path on some number n of vertices。

 The only other part of the input is a single non negative number per vertex。

 we're going to call these weights。For example， here's a path graph on four vertices and let's give the vertices the weights 1。

4，5 and4。 The responsibility of the algorithm is going to be to output an independent set。

 What that means is a subset of the graph's vertices so that no two vertices are adjacent so in the context of a simple path graph。

 it just means you've got to return some of the vertices and always avoiding consecutive pairs of vertices。

So when you have a path of four vertices， examples of independent sets include the empty set。

 any single vertex， vertices 1 and 3， vertices 2 and 4 and vertices1 and4 you could not， for example。

 return vertices two and  three because those are adjacent， that is forbidden。

Now to make this interesting， we're going to want just not any old independent set。

 but the one whose sum of vertex weights is as large as possible。

 that's the max weight independent set problem。So what I'm going to do next is use this concrete problem as an opportunity to review the various algorithm design paradigms that we've seen so far along the way。

 we'll see that none of them actually work very well for this problem and that's going to motivate us to devise a new approach and that approach is going to turn out to be dynamic programming。

So as always as our standard punching bag， brute force search。

 this would entail iterating through all of the independent sets and remembering the one with maximum total weights。

Of course， it's correct， no question about that， but as usual this would require exponential time。

 even in just a path graph， the number of independent sets is exponential in the number of vertices n。

So what other algorithm design paradigms do we know Well。

 we just finished a big segment on greedy algorithms。 We could certainly think about that。 you know。

 pretty much most problems， it's easy to propose greedy algorithms and this one's no exception。

I think the most natural greedy algorithm you might try to use to compute a maximum weight independent set would be well what's the myopic decision well you want to get as much weight overall so at each step you want to just pick the vertex with the highest weight that you haven't already chosen now of course you have to worry about feasibility remember we're not allowed to output adjacent or consecutive vertices so if any vertex is ruled out by adjacency we ignore it and amongst those that preserve feasibility we include the highest weight one in our set so far。

Well， let me redraw the four node path graph we had on the last slide and let me ask you。

 what would this greedy algorithm compute on this four node path and how does that compare to the optimal solution。

 the independent set with the maximum total weight？So the correct answer is the second one。

 Let's see why。 So let's start with the optimal solution。 the max weight independent set。

 Remember independent sets are forbidden from choosing adjacent or consecutive vertices。

 So in this case， the only sensible solutions to consider are the first and third vertex。

 the second and fourth or the first and fourth of these the best is the second and fourth for a total of8 So what about the greedy algorithm Well we just had this period of time when we got really spoiled with the success of greedy algorithms especially in the minimum spanning tree problem but let me remind you greedy algorithms。

 know they're often good heuristics， they're often not guaranteed to be correct And so I'm happy to have this opportunity to quickly remind you again of that drawback of greedy algorithms are quite frequently not correct So this is another such case。

 so what would the greedy algorithm do well it begins by picking the max weight vertex overall So that would be this vertex with weight5 that unfortunately it blocks the algorithm from picking either the two vertices that has weight4 the only remaining option that preserves feasibility is to pick the vertex of weight。

So that gives us an independent set of weight six。So if this greedy algorithm is not correct。

 you could of course try to devise other types of greedy algorithms。

 but I don't know of any greedy approach that will actually solve this problem optimally。

So that's a bummer but we still haven't exhausted our algorithm design paradigms。

 remember you know we learned this quite powerful divide and conquer approach early on in part one of this class and you know it seems like it could work here we had all these successful applications where the input was an array we broke it into two paths you recursed on both sides and combine the results and here you know path graphs don't look so different than an array of numbers so the obvious approach for divide and conqueror is to break the path into two paths each of half the length of the original recursively compute a maximum weight independence set in each and then somehow combine the results。

But the issues with the divide and conquer approach are already apparent just in our simple for vertex example。

So if we recur on the left half， that is the first two vertices and we compute a max weight independent set。

 that's just going to be the second vertex by itself。

And if we independently recursse on the right hand side on the vertices 3 and 4。

 the maximum weight independent set on the right half is going to be the vertex of weight 5。

 And now when we the recursion is complete and we get our subsolutions back。

 we have the second vertex and we have the third vertex。

 But the problem is the union of those two solutions conflicts。

 we cannot simultaneously output the second and third vertices， those are consecutive。

 Those are adjacent and that's not allowed。 Moreover， know in a four node graph。

 it's sort of easy to see how to repair this conflict。 but in a big graph， we say thousands of nodes。

 If you have a conflict right where the two subproblems meet。

 it is not at all obvious how you would quickly fix that and get a feasible and optimal solution to the original problem。

Now in some sense， the divide and conquer paradigm is more powerful or better suited for this problem than the greedy approach in that I do know of divide and conquer algorithms that could solve this problem optimally that run in quadratic time。

 but doing better than that in a divide and conquer matter seems quite challenging and in the dynamic programmingbased algorithm will develop will solve the problem in linear time that's coming up next。



![](img/69e42e2f3330e7410ec0b61871515876_2.png)