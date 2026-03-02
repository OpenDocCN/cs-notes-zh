# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P157：29_03_05_背包问题的动态规划启发式算法.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/a8f90c119e1236502910baf9411c3104_0.png)

A greedity heuristic for thenapsack problem is pretty good。

 but let's work a little harder and do quite a bit better。

We're going to accomplish a quite ambitious goal， The Napsack problem being NP complete is not we expect going to admit an exact polynomial time algorithm。

 let's shoot for the next best thing， arbitrarily close approximation that is。

 let's accept from a user， error parameter epsilon and return a solution whose value is guaranteed to be at least one minus epsilon times that of an optimal Napsack solution。

So a client who wants to be guaranteed that this heuristic outputs a solution with a 99% of optimal just has to set epsilon to be 0。

01。 If this sounds a little too good to be true， there is a catch。

 the running time is going to increase as we take epsilon to be smaller and smaller。

But what this algorithm exports to the client is an accuracy running time trade off。

 That is it exports via this parameter Epsilon， a knob that the user can turn wherever they want。

 if you want more accuracy and are willing to wait a little bit longer。

 you saidilon be Epsilon to be smaller。 If you want something really fast and you're okay with a bit of inaccur。

 you take epsilon to be bigger。And this is as good as it gets for NP complete problems。

 assuming P is not equal to NP， there's no way to solve it exactly in polynomial time。

 the next best thing you can hope for is arbitrarily close approximation in polynomial time。

 That is what we will get for the Napsack problem using a dynamic programming based heuristic。Sadly。

 the Napsack problem is the exception that proves the rule。 Most NPp complete problems。

 It is believed you cannot get arbitrarily close approximation。

 One concrete example is the vertex cover problem。 We discussed exact exponential time algorithms for vertex cover in a separate video。

 And you can talk about polynomial time heuristics for vertex cover。 and there are some good ones。

 you can get within a factor 2 of an optimum vertex cover in polynomial time。

 but it is believed you cannot get arbitrarily close approximation of the optimalmo vertex cover in polynomial time。

 In fact， if you came up with such an algorithm that would imply P equals N。

 While there are some other problems out there likenapsack that admit arbitrarily close approximation。

 there's many more out there which are like vertex cover where assuming P not equal to N。

 it is not possible to get arbitrarily close approximation in polynomial time。

But this is an algorithms class， we should stay positive and focus on what you can do。

 so let's move on to the arbitrarily close approximation for Napsack。

So the high level idea is both very cool but also very natural。

 What we're going to do is we're going to take thenapsack instance that were given。

 So items that had values and weights and somenapsack capacity。

 and we're going to massage it a little bit， not too much， just a little bit。

 but we want to put it squarely in one of our computationally tractable special cases and then we're going to solve this transformed version of the original input Now。

 because we're not solving the problem that we were given， we're not going to get the right answer。

 but as long as we didn't transform it too much we can hope that the optimal solution to the transform problem is a pretty good approximation of the original problem that we were given。

Well， what's a computationally tractable special case of the Napsack problem To date， we do know one。

 but we only know one so far， which is if we assume that the sizes of the items in the Napsack capacity are integers。

 we can go back to our dynamic programming solution of the Napsack problem。

 which runs in time and the number of items times capital W， the Napsack capacity。

 So if it were the case of the Napsack capacity W wasn't too big。 if for example。

 it was polynomial and the number of items N， then this dynamic programming algorithm would run in polynomial time。

For technical reasons， which I'll say a little bit more about later。

 this computationally tractable special case is not well suited for deployment in the dynamic programming heuristic。

 Instead， we're going to want to develop a second similar， but different。

 computationally tractable special case。The second special case is when the sizes in the Napssack capacity can be arbitrary。

 but where the item values are integers that are not too big。

This assumption can also be exploited by a dynamic programming algorithm。

 as we'll show in a separate video， there is a different dynamic programming algorithm for the Napsack problem whose running time is n squared times the largest item value。

 n squared times V max。So from this second dynamic programming algorithm。

 we can extract a second computationally tractable special case of an Napsack problem， Naly。

 if all of the item values are small integers， say a polynomial in the number of items N。

 then this dynamic programming algorithm already gives us a polynomial time algorithm for instances of that form。

Armed with this second computational tastely tractable special case。

 we can now return to the high level idea at the beginning of this slide and execute it。

Here's how we do it。 Ournapsack algorithm is given somenapsack instance。

 The item values need not be small integers。 Now we massage the instance a little bit。

 We transform it so that it becomes an instance that we know how to solve in polynomial time。

 How do we do that， We force the item values to be small integers。

 How do you take arbitrary numbers and make sure that they're small numbers。

 Well the first thing to try is drop the low order bits。

 and that's essentially what we're going to do。Our algorithm then solves this transformed instance by construction the instance has small item value so we can solve it in polynomial time using our second dynamic programming algorithm。

 Now we're probably not going to get an optimal solution to the original instance。

 After all we solved the wrong instance， we transforming the values before invoking our dynamic programming algorithm。

But the hope， and this is just a hope。 this is definitely going to require a proof。

 The hope is that we didn't lose too much information just by throwing out some lower order bits。

 So by virtue of computing a solution which is 100% optimal for the almost correct problem。

 maybe that solution is also almost optimal for the fully correct problem。

So here is the algorithm in full detail， it really only has two steps first we do the transformation。

 we round the item values to be small integers， then we invoke the second dynamic programming algorithm on the transformed instance。

Precisely， here's how we round each item value v sub I To begin。

 we decrease V to the nearest multiple of a parameter M。

I'm going to leave this parameter M unspecified at the moment。 And therefore。

 this algorithm will be undetermined。 Once we start analyzing the algorithm we'll see what the parameter M has to be as a function of epsilon。

 So don't forget that epsilon is the accuracy parameter supplied by our client。

 If the client sets a given value of epsilon。 What it means is that our responsibility is to output a feasible solution with value。

 at least one minus epsilon times that of an optimal solution。 So the smaller the epsilon。

 the more accurate our algorithm needs to be。When we round an item value V I down to the nearest multiple of M。

 we're decreasing it by an amount somewhere between 0 and M。 If V was already a multiple of M。

 we don't decrease it at all。 If V was just below a multiple of M。

 then we wind up decreasing it by essentially M。 Therefore， the bigger the M。

 the more information we're throwing out about our instance。

 and the less we should expect our accuracy。 That is， the smaller the value of epsilon。

 the more accuracy demanded by our client， the smaller we're going to have to take our value of M。

Now， once we've made everything a multiple of M， we may as well just scale down。

 may as well just divide everything by M， we're going to get integers。

The integers that we get after rounding down to the nearest multiple of M and then dividing by M are going to be called the V hats。

An alternative succinct way to describe the V hats is V hat I is by definition。

 VI divided by M rounded down， and so these funny brackets and blue on the right that's called the floor operator that takes in a real number and returns the biggest integer that's less than or equal to the input。

Thus， what is the transformation， in effect we take the item values that we were given。

 we divide them by this parameter M， and then we also round down just to make sure we're dealing with integers。



![](img/a8f90c119e1236502910baf9411c3104_2.png)

Step two of our heuristic is to just invoke the second dynamic programming algorithm to solve exactly the transformed instance。

 that is we feed into that second dynamic programming algorithm the instance with n items。

 the sizes are exactly the same as in the NApsack instance we were given originally。

 the NApsAAT capacity capital W is exactly the same as we were given originally。

 but we feed in the values V hat1 through V hat N， that is we solve it with respect to the transformed values。

 not with respect to the original values the VIs。Let's make two quick observations before we conclude。

 So first of all， remember the dynamic programming algorithm， The second one for Napsack。

 the running time is n squared times the largest item value。 And of course。

 here we're running the dynamic programming algorithm with these transformed item values， the V hats。

So therefore， if the v hats are big， then this running time is slow， that if the v hats are small。

 then this running time is going to be reasonable。 Now， let's remember the definition of the v hats。

 They're essentially the original item values divided by this magical parameter M。

 which we haven't yet specified。 But qualitatively， if M is big。

 the v hats are going to be small and the running time is going to be fast。 On the other hand。

 if M is small， the v hats are going to be big and this algorithm is going to be slow。

 So that's how M controls the running time of this dynamic programming based heuristic。 Also。

 remember， we argued how intuitively it seem to be controlling the accuracy。 the more you jack up M。

 the more information you lose when you round the v's and transform them into the v hats。

 And so the less accuracy you're going to have。 So bigger M means on the one hand。

 faster running time， but at the cost of worse accuracy。

 So this parameter M really is a knob that we can tune to figure out whether we want a faster algorithm or higher accuracy。

The nontri statement， which we need to prove in the next video is that there's a sweet spot for M that you can simultaneously get a pretty good running time。

 polynomial running time， and excellent accuracy。So one trivial observation but that's still really nice is that this dynamic programming based heuristic is guaranteed to produce a feasible solution。

 whatever output of items we get in step 2， it's guaranteed to fit inside the NapsSack The reason for that is we pass to the dynamic programming algorithm in step2。

 fully accurate sizes， the original WI's and similarly a fully accurate Napsack capacity capital W。

Therefore， the feasible solutions for the Transform Napsack instance are exactly the same as they were in the original Napsack instance。

This explains why we needed to develop a second dynamic programming algorithm for NapsSAC rather than trying to use the first one we developed。

Thankfully there is this second computational retractable special case where the items have small sizes and that turns out to be exactly what you want to make this two step recipe work The analysis is coming right up。

