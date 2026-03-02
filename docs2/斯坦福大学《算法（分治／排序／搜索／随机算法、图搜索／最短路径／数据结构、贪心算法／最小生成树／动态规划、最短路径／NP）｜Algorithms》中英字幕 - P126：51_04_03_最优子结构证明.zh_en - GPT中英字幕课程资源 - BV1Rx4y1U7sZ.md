# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P126：51_04_03_最优子结构证明.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/dbe9c4e99d8b8f67876059b29490d7e7_0.png)

So let's take any old optimal binary search tree for keys 1 through n with frequencies P1 through PN。

 The thing we're trying to prove is search that the left subt t1 should be optimal for its key is1 through R minus-1 and the right subt t2 should be optimal for its keys。

 R plus1 through N。 So we're going to proceed by contradiction， We're gonna assume that's not true。

 What would that mean That means for one of these two subproblem either1 through R minus-1 or r plus1 through n。

 there's a binary search tree with even smaller weighted search cost search time。

 then t1 or t2 respectively The two cases are totally the same whether in our contradiction we assume t1 is not optimal or with the t2 is not optimal。

 I'm just going to prove it in the case that t1 is not optimal。So if T1 is not optimal。

 there's got to be a search tree on its keys one through R minus1， which is better。

 called that purportedly better solution T star1。Now as usual。

 the thing which we're going to try to contradict to get the finalan proof is we're going to exhibit a search tree on all of the keys one through end。

 which is even better than t， but T was supposed to be optimalmost that would be a contradiction So how do we get our superior search tree for all of the keys where we're just going to take T and we're going to do cut and paste we're going to do surgery on the tree T ripping out its left subte T1 and pasting in this subtree T star1 called the resulting tree T star。

So to complete the contradiction and therefore the proof of the optimal substructureial dilemma。

 all we have to show is that the weighted search cost of T star is strictly less than that of T that would contradict the purported optimality of T。

So that's precisely what I'll show you on this next slide。

 and it's going to be evident if we do a suitable calculation， here it is。

So let's begin just by expanding the weighted search time of our original tree capital T。

 the purportedly Op  one， let's expand its definition。

So you have one sum for each of the items I and the weight we give to a given item is just its frequency piece sub I and we multiply that by the search time of 4 I and T。

So'm me now pause and tell you the point of this calculation we're about to do so we start with the weighted search time in T and that's of course expressed in terms of search times in this tree T。

 What I want to show next is that that can equally be well expressed in terms of search times in the subtrees T1 and T2 that is there's a simple formula to compute the search time in T if I told you the search times in T1 and T2 that's what's going to allow us to easily analyze the ramifications of the cut and paste and to notice that in cutting and pasting in a better tree for the subproble。

 we actually get a better tree for the original problem。

So the right weighted search time in T in terms of the weighted search time in T1 and T2。

 it's going to be convenient to bucket the items into three categories。

 those that are in the left subre T1 e1 through R minus1。

 those in the right subre T2 R plus1 through n and then of course left over is the root R itself。

 so let's just break down this sum into its three constituent parts。

So the sum man corresponding to the root R contributes the frequency of R times the search time for R。

 namely one， because it's the root。 And then we have our sum。Over just the items up to R -1。

Of their frequencies times， their search times， and similarly those As went up to end。

 their frequencies times， their search times in T。So for the next step let's observe it's very easy to connect search times in T with search times in the subtree T1 and T2。

 Suppose example you were searching for some key in T that was in T1。

 so some key that was less than R What happens when you search for this item in the tree T Well first you visit R It's not R it's less than R so you go left and then you just search as appropriately through the search tree T1 that is the search time in the big tree T is simply the search time in the subtree T1 plus11 because you had to visit the root R before you made it into the subtree T1。

So that is， for any object I other than the root， we can write its search time in the big tree T as simply one plus the search time in the appropriate sub。



![](img/dbe9c4e99d8b8f67876059b29490d7e7_2.png)

So now let me expand and group some terms just to clean up this mess。

So now that the dust has settled let's inspect each of these three sums。

 we actually have a quite simple understanding of each of them。

 so the first sum is just the sum of the PI， so for example。

 in the canonical case where we're dealing with actual probability is this is just one The point is whatever the PIs are this first sum is just a constant meaning it's independent of the treat T with which we started。

What's the second sum， that's the sum of the objects from1 to R minus1。

 the frequency of i times the search time4 I in the search tree T1。 Well。

 we have a much better shorter nickname for that sum。

 It's the weighted search time of the search tree T1 for the objects it contains one through R -1。

 Similarlyly， this last sum sum from  equal R plus1 to n of the frequency of i times the search time in T2。

 That's just the weighted search time in the search tree T2。

So we did this computation with the purportedly optimal search tree capital T in mind。

 but if you think about it， you look at this algebra。

 this applies to any search tree you like for any search tree。

 the weighted search cost can be expressed as the sum of the PIs plus the weighted search cost of the left subtree of the root plus the weighted search cost of the right subte of the root in particular that's true for this tree T star we got by cutting and pasting the better left subte T star1 in for T1。

So applying this reasoning to T star， we can write its weighted search cost as the sum from Michael 1 to n of all the PIs plus the weighted search cost of its left subre of its root。

 which remember by construction is t star of1 and then it has the same right subre as the tree T does。

 namely T2。And the point of all this algebra is that we now see in a very simple way。

 what are the ramifications of cutting and pasting in this better left subtre。

 we get a better tree for the original keyset contradicting the purported optimality of the tree T that we started with that cans to the proof of the optimal substructure lemma for optimal binary search trees。

