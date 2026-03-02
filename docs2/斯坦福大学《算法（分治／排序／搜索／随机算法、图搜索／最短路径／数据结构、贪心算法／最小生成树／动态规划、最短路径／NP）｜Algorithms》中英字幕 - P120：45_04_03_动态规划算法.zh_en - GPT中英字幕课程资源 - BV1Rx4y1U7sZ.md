# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P120：45_04_03_动态规划算法.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/ef476b2636b1259cf650ee9dcc028fca_0.png)

So now that we understand the way in which optimal solutions must be composed of optimal solutions to smaller subproblems。

 we're well positioned to turn that into a recurrence and then a dynamic programming solution for the NApsack problem。

To compile our discussion from last time into a recurrence， let me just introduce a little notation。

So by capital v subi X， what I mean is the maximum value you can get of a solution that satisfies two constraints。

 First of all it should make use only of the first I items， second of all。

 the total size of the items that you pick should be at most x。

The analog of this notation and the In set problem was G sub I， the graph of the first i vertices。

 We're now using two indices instead of one because subproblems have two different ways in which they can get smaller recall case2 of our thought experiments When we look at a smaller subpro。

 there was both one less item and there was also less capacity。So when thinking about a subprom。

 we need to keep track of both， we need to keep track of how many items are we allowed to use and we need to keep track of what's the total size that we're allowed to use。

So let's express our conclusion to the last video in this notation。

 what did we figure out last video we figured out that the optimal solution has to have one of two forms。

 either you just inherit the optimal solution for the Napsack instance with one less item that was the first case。

 or you take the optimal solution to the subproblem which has one less item and less capacity by the weight of the current item and you extend it to an optimal solution for the current subproblem using the I item。

So v subi comma x， the optimal value for the current subproblem。

 it's the better of the two possibilities， so we take a max。

The first possibility is just the optimal solution to with the sand capacity in one fewer item。

 re'using that solution。The second one is you commit to using item I， you gain value V。

And you combine that with the optimal solution using the first i minus-1 items in the reduced capacity of x minus the weight of the current item。

So one quick edge case， if the weight of the Ithe item is bigger than our permitted capacity X。

 then of course we can't use it， and then we're forced to use the first case。

 we're forced to be in case1。This then is our recurrence for the Napsack problem。

So that completes step one where we think about the optimal solution structure and use it to devise a recurrence。

 now in this step two， we're going to precisely nail down what exactly are the subproble we have to care about。

Well， in our maximum weighted independence set example on path graphs。

 remember the reasoning every time we recursd， every time we needed to look up a subproblem solution。

 it was obtained by plucking vertices off of the right of the graph。 and for that reason。

 all we ever cared about were the various prefixes of the graph。In one dimension。

 we've got something similar going on here， whenever we look at smaller subpros。

 it's always with one fewer item or're always sort of deleting the last item before we do our lookup。

So again， we need to worry about all possible prefixes of the items。

 so some problemsm of the first eye items for all values of I。For the Napsack problem， however。

 there's a second sense in which subproblem can be smaller and remember case2 of our thought experiment。

 when we want to know the optimal solution that's guaranteed to use the current item I。

 we have to reduce the capacity before looking up the corresponding optimal solution of a subproblem。

That is we're not just peeling off items， but we're also sort of peeling off parts of the NApsack capacity。

Now here is where we're going to use our assumption that I told you at the beginning in our input that sizes are all integers and that the Napsack capacity is an integer。

 so the Napsack capacity starts at capital W every time we peel off some integer amount of capacity from it。

 so at all subpro we're going to be working with integral Napsack capacities So therefore in the worst case。

 what are the various subprobles that might arise， well perhaps each choice of a residual capacity012 all the way up to the original Napsack capacity capital W。

So now we're in great shape and step two， we figured out exactly what subproms we care about in step1。

 we figured out a formula by which we can solve bigger subproblem given the solutions of smaller ones。

 so all that remains now is to write down a table and fill it in systematically using the recurrence。

 beginning with the smaller subproblem ending up with the largest subproblem。

So here's the pseudocode it's again going to be very simple in this algorithm the array A that we're going to be filling in has two dimensions in contrast to the one dimension in the weighted independent set problem。

 that's because our subproblems have two different indices we have to keep track both of which set of items we're allowed to use and also what capacity we need to respect。

So the two independent variables indexing subproblem forces us to have a 2D array that we're going to go through now in a double for loop。

So in the initialization step， we fill in all the entries where I equals zero where there's no items there。

 of course the optimal solution value is zero。And then we just go through the subproblem systematically。

When we get to a subproblem， we use the recurrence that we developed to compute the entry in that table using。

 of course， the entries that we've previously computed in earlier iterations。

So for a given subproblem where you're allowed to use the first I items and the residual capacity is X。

 what do we know from my thought experiment this can only be one of two things we're just going to do brute force search through the two possibilities。

 the two possibilities where we have case1 where we just inherit the optimal solution with one fewer item and the same capacity。

 or if we're going to actually use item I， then we compose that with the optimal solution from the first I items that leaves enough space for item I。

And in that case， we get the value v sub for including this I item。

So the code doesn't quite make sense in the case where the weight of the current item WI is strictly bigger than the capacity X that would give us a negative array index。

 which of course is a no no， but in that case amongst friends we just interpret it as ignoring the second case of the max so I'm not going to write down the extra code。

 but what you would write down is if WI is strictly bigger than x then you just define a of I comma X to be equal to a a I minus1 comma X。

And one crucial point is that you know by the time we need to solve subproblem with a given eye and a given X。

 we have at our disposal the solutions to all of the subproblems that we need in particular。

 in the previous iteration of the outer for loop， we computed these solutions to the two relevant subproblem for evaluating this recurrence。

 there they are waiting for us available for constant time lookup。

So after this double four loop completes sitting there waiting for us in a in the entry。

 n comma capital W is the solution that we wanted， that's the max value solution that can use any items that it wants and that can use the entire original Napsack capacity capital W。

 that's what we want to return。So that's it， that's the whole dynamic programming solution for the NApsAT problem just to make sure this makes sense in the next quiz。

 I want to ask you to analyze the running time of this dynamic programming algorithm。Alright。

 so the correct answer is the second one。 and the running time analysis is as straightforward as it was for the max independent set problem。

 We just count out the number of subproble and look at how much work we do in each。

 So how many subproms are there where they're indexed by both I and X。

 There are n plus one choices for I。 There are capital W plus one choices for X。

 So that gives us theta of n times W different subproblem and all we do for each is a single comparison amongst previously computed solution。

 So we just do constant work per subproblem giving us the overall running time of n times capital W。

So a couple other quick notes which play out in exactly the same way as for the Max In set problem。

 so I'm not going to discuss the details here， so first of all correctness， again。

 it's exactly the same template as in the previous dynamic programming algorithm and in our divide and conquer algorithms。

 you just go by induction on the problem size and you use the case analysis or our thought experiment to justify formally the inductive step。

So this algorithm suffers from a similar drawback to the max weight In set algorithm for Pas that we looked at。

 namely it computes the value of an optimal solution， not the optimal solution itself。

 it returns a number， not an actual subset of items。But just like with the independent set problem。

 you can reconstruct an optimal solution from the filled in array just by tracing backward。

 so the intuition is you begin with the biggest subproblem and you look at which of the two cases it was used to fill in that entry if case one was used。

 you know you should exclude the last item if case two was used。

 you know you should include the last item and also which of those two cases tells you which subproblem you should trace back to to continue the process。

So I encourage you to spell out the details of this reconstruction algorithm and the privacy of your own home that'll give you some nice practice with this reconstruction aspect of the dynamic programming paradigm。



![](img/ef476b2636b1259cf650ee9dcc028fca_2.png)