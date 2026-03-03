# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P131：03_01_06_基本算法一.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/c3da4ce6f8e6d928c52b27f322f0679e_0.png)

Now that we understand the optimal substructure present in shortest paths。

 we can follow our usual dynamic programming recipe to arrive at the basic version of the Belman Ford algorithm。

Let's compile our optimal substructure lemma into a recurrence of formula that says how the optimal solution value of a given subproblem depends on that of smaller subprom。

I'll use the notation capital L subV to denote the optimal solution value of the corresponding subproblem。

 subproblem is being indexed by two parameters，1 V。

 that's the destination we're interested in in the subproblem。

 and the second one is the budget I on the number of edges that are permitted in paths from S to V in the subproblem。

So a few details， first of all， remember that in the last video。

 we proved the optimal substructure limit in general for general graph G。

 which may indeed have negative cycles for that reason。

 we have to allow cycles in shortest paths from S to V。

 We're not concerned about the cycle being traverse and infinite number of times because we have this finite budget I on the number of edges that we permit。

I also need to explain what I mean in the case that there are no paths from S to V within most eye edges。

 and indeed， when I is very small， that will in fact be the case for many destinations V。

 so if there's no way to get from S to V using only I hops， we just define LIV to be plus infinity。

And as usual， in the recurrence， which is going to be defined for every positive integer I and every possible destination V。

 we're just going to state that the optimal solution value for the subproblem is the best of the possible candidates identified in the optimal substructure lemma。

That is capital L sub I V， the optimal solution value for the subpro with parametersmber I and V is the best of all the possibilities。

 So let me start with a minimum to take the best of the case1 candidate and the case2 candidate。

The case one candidate is simple enough。 One option as always。

 is just to inherit the best path we found from S to V that uses only I -1 edges or less。In case2。

 you'll recall from the quiz at the end of the last video really comprises a number of subcases。

 one for each choice of the final hop。 So here we're going to have another minimum ranging over all possible edges。

 W V。For a given choice of that last hop， the shortest path length is going to be the shortest path from S to that choice of W that uses the most -1 edges。

 and then of course we also incur the edge cost of the final hop W comma V。

Correctness as usual follows immediately from the optimal substructure dilemma。

 we know these are the only candidates and by the definition of the recurrence， we pick the best one。

Because our optimal subsspecial lemma has been proven whether or not G has a negative cycle。

 this recurrence is correct for all positive values of I， whether or not G has a negative cycle。

 so now let's see how it's useful to assume that the input graph G does not have a negative cycle。

So we had a quiz not too long ago that discussed the use of the No negative cycle's hypothesis。

 In particular， we argued that n-1 edges are always enough to capture as shortest path between S and any possible destination。

 Why Well， suppose there's no negative cycles。 fix the destination V。

 show me a path that has at least n edges。 If it has at least n edges。

 then it visits at least n plus1 vertices。 there's only n vertices so the path must visit some vertex twice。

 And in between two consecutive visits of a given vertex that's a directed cycle。 by hypoes。

 there are no negative directed cycles， they're all nonneg。

 So if I throw out this directed cycle from this path， I get a new path to the same destination V。

 and its overall length has only gone down。 discarding cycles only makes paths shorter。

 That's why there's a shortest path with no repeated vertices that is with a most n-1 edges。

So what does this observation have to do with our recurrence。

 Well it tells us only need to compute the recurrence。

 evaluate subproblem for values of I up to n minus1。

 There is no point in giving a subproblem a budget bigger than n -1 edges if there are no negative cycles。

 It's not going to be useful， you're guaranteed to have already found the shortest path by the time I has gone as large as n -1。

So to make sure this point is clear， let me just formally write down the subproblems that we're going to solve in the Belman Ford algorithm and which are going to be sufficient to correctly compute shortest paths for input graphs G that do not have negative cycles。

The so problems are simply to compute the shortest path links capital L sub IV， of course。

 for all destinations， we're responsible for ultimately computing shortest past to every destination V and for all relevant choices of the edge budget I。

 and so the base case is going to be when I equals 0。

 and we just said it has to go up as high as n minus1 and no further。

And this is actually a pleasingly parsimonious collection of sub problems。

 It may strike you actually kind of as a lot because there's a quadratic number there's n choices for the destination V。

 and then I is taking on n different values。 But remember。

 unlike only the other problems we've been talking about， the output of this problem is linear size。

 We're supposed to output a number for each destination V。

 So we really only have a linear number of subproblem for each statistic we're responsible for computing。

 and that's as good as we've had in any of our other dynamic programming algorithms。

So now it's a simple matter to write out the pseudocode of the justifiably famous Belman Ford algorithm。

Because our subprom are indexed by two parameters， the edge budget I and the destination V。

 we're going to have a two dimensional array A。Remember that we're measuring subproblem size via the edge budget I that's sort of the great idea in the Bel Ford algorithm to introduce this edge budget to control subproblem size。

 So the base case is when I equals0 and then we're talking about getting from S to some vertex V using zero edges Okay well if V happens to equal S。

 then you can do it with the empty path and the length of the empty path is0 but if V is any vertex other than S then of course you can't get from S to V using zero edges and remember in that case we define the optimal value solution to be plus infinity。

So now we move on to our customary double for loop1 for loop for each of the indices that indexes our array A。

 And actually， what's interesting is， unlike most of the dynamic programming algorithms we're discussing here。

 the order of the for loop matters。 You cannot pick arbitrarily。

 You really need to make sure that you have all the smaller sub problem solved by the time you need them。

 That means the outer for loop should be indexed by the subpro size I。So as we discussed。

 we're not going to bother letting I range above n minus1 that's going to be sufficient in the case where there are no negative cycles and for each choice of I。

 we solve all of the corresponding subproblems， all destinations V。For each choice of I and V。

 of course we just write down in code the formula that we stated in the recurrence。

So as I'm sure you recall， case1 furnishes one possible candidate。

 it's always an option just to inherit the shortest path from S to V that you computed using only I minus-1 edgesAlternativelyly from case2。

 there's also one candidate furnished for each choice of the final hop。

 so for each edge that ends at V for each choice W comma V。

 there's an option of taking a shortest path from S to W that uses only I minus-1 edges and tacking on that final edge W V。

And as we've discussed， if it just so happens that the input graph G has no negative cycles。

 then this algorithm will indeed terminate with the correct shortest paths from S to all of the destinations。

 Those answers will be lying in wait for you in the biggest sub problems。 The A and -1 Vs。

So that's correctness as usual， it follows primarily from the optimal substructure lemma。

 but in this case， also the hypothesis of no negative cycles guarantees that taking I equal n minus1 is large enough to actually capture the final answers。

So we'll talk about the running time of the Belman Ford algorithm in a sec。

 but first let's just go through a quick example to make sure all of this makes sense。



![](img/c3da4ce6f8e6d928c52b27f322f0679e_2.png)