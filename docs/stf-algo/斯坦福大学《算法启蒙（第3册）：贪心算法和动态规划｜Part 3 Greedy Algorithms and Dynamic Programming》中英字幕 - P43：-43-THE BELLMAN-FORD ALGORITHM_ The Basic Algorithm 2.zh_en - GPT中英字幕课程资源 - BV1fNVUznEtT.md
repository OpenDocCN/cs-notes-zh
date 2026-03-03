# 斯坦福大学《算法启蒙（第3册）：贪心算法和动态规划｜Part 3 Greedy Algorithms and Dynamic Programming》中英字幕 - P43：-43-THE BELLMAN-FORD ALGORITHM_ The Basic Algorithm 2.zh_en - GPT中英字幕课程资源 - BV1fNVUznEtT

Consider the following graph with five vertices。

![](img/3f406ef79d101a53f46bedca738388ae_1.png)

A' label their edges with their costs in blue。So let's step through the values of I and since there's five vertices。

 I' is going to take on the value 0，1，2，3，4， and let's look at what are the results of each round of subproblem computations is。

So in the base case， when I equals0， as always， the distance from S to itself is0 and for all other vertices。

 the subproblem value is defined as plus infinity。Let me write down the recurrence again。

 just in case you've forgotten it。So now we enter the main four loops， and we start with I equal 1。

So now we just go through the vertices in arbitrary order and evaluate the recurrence。

So node S is going to just inherit the solution from the previous step。

 it's still happy with the empty path of total length0。

Now node V is certainly hoping not to have to inherit its solution of plus infinity from the previous round when I equals 0。

 and indeed when I equals1， the subproblem solution for the vertex V is going to be 2 that's because we can choose the last hop to be the edge S comma V that has length2 and s's subproblem value last iteration when I equals 0 was0。

By the same reasoning， x's new sub problemblem value is going to be4 because we can choose the last hop to be S comma x and add the cost of that edge 4 to S's sub problemblem value last iteration when I equals0。

Now， the nodes W and T would love to throw out their plus infinity solutions and get something finite。

 And you might be thinking that because V and X now have finite distances。

 those would propagate to the nodes W and T。 that will indeed happen。

 but we're going to have to wait till the next iteration， we're gonna have to wait till I equals 2。

 The reason is， if you look at the code， if you look at the recurrence。

 when we compute the sub problemblem value at a given iteration I。

 We only make use of the subproble solutions from the previous iteration， I minus1。

 We do not use any of the updates that have already happened in the current iteration I。

 So because when I equals 0， A of 0 v and a of 0 x We both plus infinity。

 we're going to be stuck with a1 W and A1 T， both being plus infinity as well。

So now let's move on to the next iteration of the outer for loop when I equals 2。

 the subproblem solution at S is not going to change。 You're not going to do better than0。

 So it's going to stay that way。 Similarlyly at the vertex V， you're not going to do better than 2。

 so that's going to stay the same at this iteration。Something interesting happens at the vertex X。

 however， Now in the recurrence， you certainly have the option of inheriting the previous solution。

 So one option would be to set a of two comma x to be equal to4。

 but there's actually a better choice。 So the recurrence is going to come out to be even smaller。

 specifically if we choose that last hop to be the unit cost arc from V X。

 we add that unit cost to v subproblem value last iteration when I equals 1。

 That was22 plus1 equals 3。 So that's going to be the new subproblem value at x in this iteration where I equals 2。

So as advertised， the updates to the vertices V and X in the iteration where I equals 1。

 now that I equals 2 get propagated on to the vertices W and T。

 so W and T shed their plus infinity values， and instead they pick up the values4 and8 respectively。

Notice that I've labeled the vertex T with an 8， not with a 7。

 I've computed a of two comma T to be 8。 And the reason is， again。

 the same updates from this iteration。 In particular， the fact that x is dropped from 4 to 3。

 do not get reflected at other nodes in this same iteration。

 We have to wait until the next iteration of the outer for loop before they happen。

 So we're using the stale information at x that when I equals 1， its solution value is 4。

 that's the information we're using to update T's solution value。 So it's4 plus 4 or 8。

So in the penultimate iteration， when I equals 3， most things stay the same at S and V at X and W。

 we've actually computed the shortest paths， so they will all just inherit the solution from the previous iteration。

But at vertex T， it will now make use of the improved solution value at the vertex X from the iteration where I equals 2。

 so itss8 gets updated to be a 7 reflecting the improvement at x the previous iteration。

And at this point we're actually done， we've computed shortest path to all destinations。

 but the algorithm doesn't know that we're done yet。

 so it still executes the final iteration of the outer four loop where I equals 4。

 but everybody just inherits their solutions from the previous round at that point。

 the algorithm terminates。For most of the dynamic programming algorithms that we've discussed。

 the running time analysis has been trivial。 The Elmond Ford algorithm is a little more interesting from a running time analysis perspective。

 please think about it in this quiz。So the correct answer is B。

 that is of all these running time bounds， the smallest bound which is actually correct。

 so let me explain why why it's the number of edges times the number of vertices and also comment on some of the other options。

So answer a， quadratic and squared what this is， this is the number of sub problems right So sub problemsms are indexed by a choice of I。

 which is somewhere between 0 and n -1 and a choice of a destination V。

 there's n choices for each so there's exactly n squared subproblem。

 If we only ever spent constant time evaluating a subproble， then indeed。

 the running time that Belman Ford would be big o of n squared。

 And in most dynamic programming algorithms we've discussed in this class。 Indeed。

 you only spend constant time solving each subpro。 The one exception being the optimal binary search trees problem where in general。

 we spent linear time here again， like optimal binary search trees。

 we might spend more than constant time solving a subpro。

 The reason being we have to do brutefor search through a list of candidates that might be super constant。

 The reason is that each arc that comes in to the destination V provides one candidate for what the correct solution to this subprom might be。

 So remember， the number of candidates we had a quiz on this is proportional to the in degree of the ver。

VAnd that could be as large as n minus1 linear in the number of vertices。

So that's why the running time of the Bel and Ford algorithm can in general。

 be worse than and squared。Another interesting answer is C that it's cubic in N。 Indeed。

 big O of n cubed is a valid upper bound on the running time of the Belelt Ford algorithm。

 but it's not the sharpest possible upper bound。 So why is it a valid upper bound。

 as discussed just now is a quadratic and squared number of subproble。

 How much work you do per subproblem， Well it's proportional to the in degree of a vertex。

 the biggest in degree of a vertex is n -1 big O of n。

 So linear work for each of the quadratic number of subproblem resulting in cubic running time。

There is， however， a tighter， a better analysis of the Belmont Ford algorithm。 Now。

 why is O of M N bigger than n cubed。 Well， what is M in a sparse graph。

 M is going to be theta of n And in a dense graph， M is going to be n squared。

 So if it's a dense graph， it's true， Big O of M N is no smaller than N cubed。

 But if it's not a dense graph， then this really is an improved upper bound。

So why does the bound hold well think about the total amount of work done over all of the subpro in the following way？

😡，So all we're going to do is take the amount of work done in a given iteration of the outer for loop and multiply it by n the number of iterations of the outer for loop。

So how much work do we do in a given iteration for a given choice of I， Well。

 it's just the sum of the in degrees。When we consider the vertex v。

 we do we' proportional to itss in degree， and we consider each vertex v once in a given iteration of the outer form。

But we know a much simpler expression for the sum of the ind。This sum is simply equal to M。

 The number of edges in any directed graph， the number of edges is exactly equal to the sum of the in degrees。

 One easy way to see that is take your favorite directed graph。

 And imagine you plug the edges into the graph1 at a time。 starting from the empty set of edges。

 Well， each time you plug in a new edge， obviously， the number of edges in the graph goes up by one。

 And also， the in degree of exactly one vertex goes up by one。

 whichever vertex happens to be the head of the edge that you just stuck in。 So therefore。

 the sum of the in degrees and the sum of the， the number of edges is always the same。

 no matter what the directed graph is。 So that's why the total work is better than n cubed。

 It's actually big O of M times。So a number of optimizations of the basic Bellman Ford algorithm are possible。

 let me wrap up this video just with a quick one about stopping early。

 see also a separate video about a less trivial space optimization of the algorithm。

The basic version of the algorithm， the outer for loop runs for n -1 iterations。 General。

 you don't need all of them。 We already saw that in our simple example。

 where the final iteration did no useful work。 It just inherited the solutions from the previous iteration。

So in general， suppose it's some iteration earlier than the last one。

 So say with the current index value of J， it just so happens that nothing changes that at every destination V。

 you just reuse the optimal solution that you recomputed in the previous iteration of the outer for loop。

 Well， then if you think about it， what's going to happen in the next iteration。

 You're going to do exactly the same set of computations with exactly the same set of inputs。

 So you're going to get exactly the same set of results。

 That is it will be true again in the next iteration that you will just inherit the optimal solutions from the previous one。

 And that will keep happening over and over again until the rest of time。So in particular。

 by the time you get to the n -1 iteration of the outer for loop。

 you will have exactly the same set of solution values as you do right now。

 We've already proven that the results at the end of iteration n -1 are correct。

 Those are the real shortest path distances。 If you already have them in your grubvy little hands now。

 while you may as well abort the algorithm and return those as the final， correct。

 shortest path distances。

![](img/3f406ef79d101a53f46bedca738388ae_3.png)