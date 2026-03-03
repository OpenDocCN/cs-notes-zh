# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P155：27_03_03_贪心背包启发式算法分析一.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/5fe4027a40e2ce3374d45b7844b2f47a_0.png)

Let's now turn to the analysis of our three step greedy heuristic for the Napsack problem and show why it has a good worst case performance guarantee。

So the goal is to prove that the value of the solution output by this three step goody algorithm is always at least half the value of an optimal solution。

 a maximum value solution that respects the NApsAT capacity。

The key idea behind the analysis is a thought experiment in which we use as a yardstick。

 an algorithm which gets to cheat。Recall that in step one of our greedy heuristic。

 we sort the items in non increasing order of bang per buck that is via the ratio of the value over the size。

In step 2 of the greedy heuristic， we pack the items in this order。

 so maybe the first K items for some value of K in this order fit into the knapsack。

 but then we don't have room for item K plus1。 and at that point we stop this step of the heuristic。

The thought experiment is to imagine that our algorithm gets to cheat and pack a fraction of this item K plus1 into thenapsack to fill it up fully。

 So for example， if we pack in the first K items and after that there's only seven residual units of capacity in the Napsack and suppose item K plus1 has size 10。

 then we envision taking 70% of item K plus1 and filling it filling up thenapsack with that fraction the value。

 let's say it's prorated so let's say by filling in 70% of the item into the Napsack we get 70% of its value。



![](img/5fe4027a40e2ce3374d45b7844b2f47a_2.png)

So we're going to call the output of this cheating algorithm the greedy fractional solution。

So just to give a super simple example， imagine you had a knapsack of capacity  three and you had two items both of size two。

 let's say one has value three， one has value two。Well then in the greedy fractional solution you begin by considering item1 that has the higher ratio of three/hals that fits fully into the K NApsSack。

 then you move on to item2， it only fits 50% into the NApsSack and the total value of the solution would be the full value of item 1 that's  three plus 50% of the value of item 2 so that adds one more so the value of the greedy solution here would be four。

 the greedy fractional solution would be4。In the next quiz。

 I'm going to ask you to ponder what properties this greedy fractional solution has relative to feasible solutions of the Napsack instance。

correct answer is D， the greedy fractional solution is always at least as good as the best nonfral solution。

 and in fact， it can be strictly better。 indeed， if you look at the last slide in that simple two item example。

 in that instance， the greedy fractional solution is better strictly better than every single feasible solution。

 Now it's not going to be strictly better in every single instance because there's going to be instances where the greedy fractional solution happens to use no fractions。

 it happens to just fill the Napsack fully using 100% of various items。

 and then that is no way that can be better than an optimal non-fal solution。

So I'm not going to prove this fact for you in gory detail。

 but let me give you just an outline of the argument。

So the claim is that the greedy fractional solution of an Apppsack instance is guaranteed to be at least as good。

 have at least as large a total value as every feasible solution。

 that is every non fractional solution。The proof of this would fit in fantastically in the greedy algorithms section of this course that is really what it is。

 one way you can prove this formally is using an exchange argument。

 that's what I'll sketch at a high level here。I'll leave it as an exercise to you to fill in the details。

 but it's really very similar to our proof of optimality for the greedy algorithm for why sorting by ratios minimizes the weighted sum of completion times of a bunch of jobs on a single machine。



![](img/5fe4027a40e2ce3374d45b7844b2f47a_4.png)

So how should we proceed， we have to prove that the greedy fractional solution is as good as every feasible solution。

 every non fractional solution， so fix such a solution， call it S。

 this is a subset of items that fit into the K NApsack。So you could imagine， for example。

 a scenario in which the greedy fractional solution packs item number one and then item number two doesn't fit into the NApsack。

 but if we take 80% of item number two， then that fully fills up the Napsack。

 so that might be the greedy fractional solution and maybe we're thinking about nonfional solution where item 1 is equally well packed there。

 but instead of item 2 which wouldn't fit， it uses item 4 which is smaller and then maybe there's some little bit left over of unfilled Napsack capacity for this nonfional solution capital S。

So the interesting case is where S packs some stuff that the greedy fractional solution does not。

 and let's suppose it uses up L units of the Napsack capacity via items which are not packed by the greedy fractional solution。

Well， on the other hand， the greedy fractional solution completely fills up the knapsack。

 it uses all of the space all capital W units， so if there's L units of stuff in S。

 which are not in the greedy fractional solution， there have to equally well be at least L units of stuff in the greedy fractional solution which are not packed by S。



![](img/5fe4027a40e2ce3374d45b7844b2f47a_6.png)

So this might make it seem like the two solutions are apples and oranges。

 each of them packs some stuff that the other one doesn't， but they're not apples and oranges。

 the greedy fractionracal solution really is better。 Why， while by the greedy criterion。

 everything not packed by the greedy fractional solution has ratio has bang per book worse than everything that it did packed。

 So these L units that are missing from the greedy fractional solution are less valuable than the L units that it includes。

So since the L units of stuff in the greedy fractional solution missing from capital S are a better use of space than the L units of stuff that are in S。

 but not the greedy fractional solution， some easy algebra shows that indeed the overall value of the greedy fractional solution is at least the overall value of S since S was arbitrary that shows that the greedy fractional solution is in some sense better than optimal。

 it's better than all of the non-fal feasible solutions。

Now it's not clear the moment while we bothered to do this thought experiment。

 which transpired in some fantasy world where we were allowed to pack items fractionally now what we really care about is our three step greedy algorithm and that is not in the fantasy world that's in the real world where we cannot pack items fractionally so what good could this thought experiment be well as we'll see in the analysis in the next slide it provides a useful yardstick。

 a hypothetical benchmark against which we can compare the performance of our threestep greedy algorithm。

