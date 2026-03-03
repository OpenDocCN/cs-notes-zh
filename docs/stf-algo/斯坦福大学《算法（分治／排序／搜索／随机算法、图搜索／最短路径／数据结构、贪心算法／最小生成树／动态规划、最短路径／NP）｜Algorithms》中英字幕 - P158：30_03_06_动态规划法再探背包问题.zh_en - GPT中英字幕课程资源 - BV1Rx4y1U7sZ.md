# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P158：30_03_06_动态规划法再探背包问题.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/c0c714e28957c393386d74ba5db66edb_0.png)

In this video we'll develop our second dynamic programming solution for the Napsack problem。

 why do we need a second algorithm， well it's a crucial building block in our heuristic that achieves arbitrarily close approximation to the Napsack problem in polynomial time。

Recall that in the Napsack problem， the input is two n plus1 numbers。 There's n items。

 Each one has a positive value V and a positive size W I。 Additionally。

 we're given a Napssack capacity capital W back in the dynamic programming section of this course。

 we already devised an algorithm for this problem。 That algorithm assumed that the item sizes were integral and also that the Napsack capacity is an integer。



![](img/c0c714e28957c393386d74ba5db66edb_2.png)

The running time of that dynamic programming algorithm was big O of n。

 the number of items times capital W， the NApsSAC capacity。In particular。

 we get a polynomial time algorithm for the special case of Napsack when the Napsack capacity is not too big when it's polynomial in N。

It turns out that this is not the right special case on which to build an algorithm which has arbitrarily good approximation in polynomial time。

 rather for that kind of heuristic， what we really want is a polynomial time solution for the special case where item values are small。



![](img/c0c714e28957c393386d74ba5db66edb_4.png)

That is precisely the solution we're going to provide in this video we will be assuming that the integer values are all integers。

 the sizes and the Napsack capacity can be whatever。

 and the dynamic programming solution that we develop will have running time Big O of n squared times V max V max here denotes the maximum value of any item。

The running times of the two algorithms are more in parallel than the notation might suggest。

 Probably it looks like there's an extra factor of n in the second dynamic programming algorithm。

 but that's the wrong way to think about it。 Think for the first algorithm。

 Think of W as an upper bound on the largest total size that a feasible solution might possess in the second algorithm。

 Think of n times E max as an upper bound， on the maximum total value that any feasible solution might possess。

 In the first algorithm， we're focused on size， in the second algorithm we're focused on value。

 and in either case， the running time is the maximum quantity that we have to worry about times the number of items N。

Now， since all of you are survivors of my dynamic programming boot camp。

 I don't feel the need to develop this solution in great to Da。

 let me just jump to the relevant subproble。So the subproms here will be a twist on the ones that we use in our first dynamic programming algorithm for Napsack。

 the part that's going to be exactly the same is we're going to have an index I。

I specifies which prefix of items were permitted to use in a given subproblem。

Now in general in the Napsack problem you're simultaneously trying to get the value high while keeping the weight small。

 so the way we organize things in our first dynamic programming algorithm is the second index into a subproblem specified the residual capacity X that we were allowed to use and then while respecting that capacity X we asked for the largest value that we could obtain just using the first items here we're going to turn that on its head。

 we're going to have a second parameter X， which is the value that we're striving for so we want to get value X or more and we're going to try to minimize the total size that we need to use subjects to getting value at least X。



![](img/c0c714e28957c393386d74ba5db66edb_6.png)

![](img/c0c714e28957c393386d74ba5db66edb_7.png)

So the first index I ranges as usual from0 to n， this corresponds to all the prefixes of items you might be interested in。



![](img/c0c714e28957c393386d74ba5db66edb_9.png)

![](img/c0c714e28957c393386d74ba5db66edb_10.png)

The second parameter X ranges over all of the targets for total value that you might be interested in。

Now， remember， we're assuming in this video that every item value is an integer。

 so that means any subset of items will have an integral total value。

 so we only need to worry about integer values of x。 In addition。

 we never need to worry about trying to achieve a total value bigger than n the number of items times V max。

 the largest value of any item。 In fact， you could replace the upper bound n times V max by the sum of the Vs if you prefer。

 So for a given choice of I and x。 I'm going to use capital S sub i x to denote the optimal value of that corresponding subproblem。

 So that is the minimum weight， the minimum total size that is sufficient to achieve a total value of x or more while being restricted to using just the first I items。



![](img/c0c714e28957c393386d74ba5db66edb_12.png)

![](img/c0c714e28957c393386d74ba5db66edb_13.png)

If there is in fact no way to get the target value of x using just the first I items。

 that is if the sum of the values of these items is already less than x。

 we just define this to be plus infinity。

![](img/c0c714e28957c393386d74ba5db66edb_15.png)

So let's write down the natural recurrence。 Let's assume here that I is at least one。

So the structure here is going to be exactly the same as it was in our first dynamic programming algorithm for the NApsack problem。

 specifically let's focus on a subproblem， a choice of I and a choice of X。

 that final item I is either in this optimal solution for the subproblem or it's not that gives us two cases and the recurrence is just going to do brute force search over the two cases。

Because we're trying to minimize the total size required to achieve a given value target here the brute force Church is going to take the form of a minimum。

What are the two candidates for an optimal solution while the boring one is when you don't even bother to use item I。

 then of course you just inherit an optimal solution。

 a minimum size solution using just the first I minus1 items achieving the same value target X。



![](img/c0c714e28957c393386d74ba5db66edb_17.png)

On the other hand， suppose that in an optimal solution to the subproblem， you do actually use item I。

Well， this contributes to the size of item I to the weight of this optimal solution。

 so that's going to be w sub I。What can we say about the rest of the items in this optimal solution。

 Well， because the solution here achieves a value target of X。

 the items in this solution other than I must be achieving by themselves a value target of x minus v sub I and of course。

 by the usual cut and paste argument amongst all subsets of the first I minus-1 items with that property。

 they better well have the minimum total weight。So one quick edge case in this second case。

 if VI is actually bigger than x and we have a negative index here。

 we just interpret this quantity as zero， that's because item I alone meets the value target of x。

Let's now wrap things up with the pseudocode of the new dynamicmic programming algorithm。

So a will be our usual table， it has two dimensions because subprobles are indexed by two parameters。

 I， the prefix that ranges from 0 to n and x， the value target that ranges from0 to the maximum imaginable value。

 let's say n times V max。So the base case is when I equals  zero。

 that is you're not allowed to use any items in this case we have to fill it in with plus infinity。

 well except if x itself is zero， then the answer is zero。

Now we just populate the table using the recurrence in a double for loop。

 the structure here is exactly the same as in our first NAPS academic programming algorithm。

In the first dynamic programming solution that we developed for NapsAC we could return the correct answer in constant time given the field in table。

 that's because one of the subproble in that dynamic programming algorithm literally was the original problem when I is equal to n and x is equal to the full NApsack capacity capital W the responsibility of that subproblem was to compute the max value solution subject to the capacity capital W using all of the items that's literally the original problem。

By contrast， in this dynamic programming algorithm。

 none of the subprobles are literally the original problem that we wanted to solve。

In this new dynamic programming algorithm， however。

 none of the sub problems correspond directly to the original problem that we wanted to solve。

 None of them tell you the maximum value of a feasible solution。 to see why。

 let's inspect the largest batch of subproble。 When I is equal to N and you can use whatever subset of items that you want。

 The second index of one of these problems is a target value X。 That might be a number like。

 say 17231。 So after you've run this algorithm and you've filled in the whole table。

 What do you know in this subproblem。 You will have computed the smallest total size of a bunch of items that has total value at least 17231。

 So that's going to be some number， maybe it's 11298。

 But what of your Napsack capacity is only 10000。 Then this is not a feasible solution。

 So it doesn't do you any good。Okay， well that's not quite true。

 it does do you some good if you know that every single solution that gets。

Value 17231 or more has size bigger than your Napsack capacity。

 well then you know that the optimal solution has to be less than 17231。

 There is no feasible way to get a total value that high。

Now you realize that if you knew this information for every single target value X， and you do。

 once you've filled in the entire table， that's sufficient to figure out the optimal solution。

 to figure out the biggest value of a feasible solution。

All you need to do is scan through this final batch of subproblem。

 you begin with the largest conceivable target value X。

 and then you get less and less ambitious as you keep finding infeasible solutions。

 so you scan from high target values to low target values and you're looking for the first that is the largest target value X。

 such that there exists a subset of items meeting that target value whose total size is at most your NApsack capacity that is going to be the optimal solution。

 that first target value X that can be physically met given your NApsSack capacity。



![](img/c0c714e28957c393386d74ba5db66edb_19.png)

Analyzing the running time is straightforward， so how many subprom are there or equivalently how many iterations of our double for loop do we have。

 well it's n outer iterations and then n times Vm inter iterations， so that's n squared Vmax overall。

Our brute force searches over only two candidates， so we only do constant work per iteration of the double4 loop。

And the final line we do is scan through the largest batch of subpro， so that's O of n times VmX。

So the running time is dominated just by the constant work per subproblem。

 and so our overall running time is O of n squared times the Vmax as promised。

