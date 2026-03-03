# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P89：14_01_05_割性质证明-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/2524bf4944729479adb045f45ad0462b_0.png)

Okay， so to this point， we've proven the correctness of Pri's minimum spanning tree algorithm under an assumption。

 under an assumption that the cut property is true。

 so the purpose of this video is to supply the missing proof to convince you of this cut property。

Let me remind you where we stand。 So through all the minimum spanning tree videos。

 we're assuming distinct edge costs， all of this can be extended to edge costs with ties。

 in particular there's a version of the cut property when edges have ties。

 but we're just going to focus on the main ideas， which were exposed already with distinct edge costs。

 So what does the cut properties say。 Well， it's meant to be a guarantee that an edge is safe to include on in your tree so far。

 So it justifies an iteration of a greedy algorithm like Pris algorithm。

 specifically consider an edge of a graph。 And suppose you can find some cut。A comma B。

 so that amongst all the edges that are crossing this cut E is the cheapest。

 So E the E E has to not just cross this cut， but it has to be cheaper than any edge that crosses this cut。

 If you can find just one cut of this form so that E is the cheapest crossing edge。

 then it's definitely not a mistake to include E in your treat， you definitely want it。

 it is in the MST。 So this is a nontrivial claim。 and let's turn to the proof。



![](img/2524bf4944729479adb045f45ad0462b_2.png)

At a high level the plan will be not that different than the correctness of our greedy scheduling algorithm for minimizing the weighted sum of completion times that is we're going to use an exchange argument embedded in proof by contradiction。

 and the type of contradiction will be of the same form， we'll start with an optimal solution。

 suppose it doesn't have the property that we want it to have。

 and then we do an exchange to make it even better contradicting the assumption that this solution is optimal。



![](img/2524bf4944729479adb045f45ad0462b_4.png)

![](img/2524bf4944729479adb045f45ad0462b_5.png)

![](img/2524bf4944729479adb045f45ad0462b_6.png)

So specifically if we argue about a contradiction， we assume that the cut property is false。

 so let's just make sure we understand what that means， the cut property is false。

 then there's a graph and there's an edge which actually is the cheapest crossing some cut and yet that edge does not belong to the minimum cost span tree T star。

The plan then is to exchange this missing edge E with some edge that is in the treat T star。

 which is more expensive， thereby getting a better span tree providing the contradiction。



![](img/2524bf4944729479adb045f45ad0462b_8.png)

So this idea currently is a little bit handwavy to really execute it。

 we have to specify which edge we're going to exchange the edge E with that's a subtle point and we'll develop it over the next couple of slots。

So let's begin with a sort of first cut attempt at an exchange argument。

So what's the world look like， well we have some cut of a graph。

 so we have one blob of vertices A and then the rest of the vertices are in this blob B。

 this is the cut for which edge E is the cheapest。And by our assumption。

 in this proof by contradiction， this cheapest edge E does not belong to the minimum spanning tree T star。

 That said， I claim， while T star may not have this edge E that crosses this cut。

 it better possess some other edge crossing this cut A B。So why is that true， Well。

 suppose the opposite， suppose in fact， T star did not have any edge crossing this cut AB。

 Well then t star wouldn't be connected。 It wouldn't span all the vertices。

 right remember our proof of the empty cut lemma， So if you had this empty cut。

 then there's no way to have a path from one side to the other side but that's spanning trees have to have paths between each pair of vertices。

 So T star as a spanning tree has to contain something from this cut by assumption it doesn't contain edge E。

 So it contains some other edge， let's call it F that crosses this cut。Now， of course。

 since E is the cheapest edge crossing this cut in F is some other edge crossing this cut。

 F is strictly more expensive than E。And at this point we seem beautifully set up to execute the desired exchange argument。

 we have the edge that the optimalmal solution is missing。

 we have a candidate replacement E F which is more expensive。

 so if we swap EF hopefully we get a new spanning tree that has strictly smaller cost providing the desired contradiction。



![](img/2524bf4944729479adb045f45ad0462b_10.png)

But things are more subtle than they were with the scheduling application。

 The reason being is that schedules are simply sequences of jobs。

 So whenever you do an exchange of two jobs， it's clear you get another schedule。

 but spanning trees and graphs are subtle objects And there's a question if we take a spanning tree and we add one new edge and delete an edge。

 do we get another spanning tree of the graph or not。

 So the following quiz is going to ask you to think about that question carefully。Okay。

 so what we wish that the answer to this quiz was was either answer A or answer is C。

 So A would be the cleanest solution who were always true that when you take a spanning tree。

 youd take an edge outside of the spanning tree and then you swap those two edges。

 you get a new spanning tree， then in fact， our proof of the cut property would be done right we would just go on that previous slide we would rip out the edge F from the spanning tree we'd plug in the edge E because E costs less than F we'd get a spanning tree which was cheaper we'd be done that would be our contradiction Now if a wasn't true we'd still be okay if C was true if maybe not every swap yield a new spanning tree。

 but at least if you're swapping in the edge that's the cheapest crossing some cut。

 you get a spanning tree， then we'd also be golden because in fact we only are trying to execute the swap the exchange using an edge which is the cheapest crossing some cut if you go back to the previous slide you'll see that was the only case we needed this fact to be true。

 Unfortunately， the correct answer to this quiz is D you need not get a new spanning tree when you execute and exchange。

If you're plugging an edge， which is the cheapest edge crossing some cut。

So to understand this better， let me redraw the picture that we had on the previous slide。

We had our cut A B， we had our cheapest edge E， which by assumption does not belong to the spanning T T star。

 but we observed that T star has to contain at least one other edge crossing this cut because it's connected and we called that F。

And we're wondering if swapping ENF yields a new spanning tree or not， so to reason about this。

 let me just draw you what the rest of the spanning tree might look like。



![](img/2524bf4944729479adb045f45ad0462b_12.png)

So in this picture， the spanning tree T star is given by the pink edges and it's just to this path of five edges on the six vertices。

 so what happens if we exchange ENF well， unfortunately something bad happens？

So we certainly get a new subgraph of five edges after all we just subtracted one and added one。

 but this spanning this new subgraph fails to be a spanning tree it fails on both counts。

 first of all it obviously has a cycle， it has a four cycle and secondly it's not connected the upper right vertex is just totally disconnected from the rest of the vertices so that's no good that's a exchange which just does not produce a feasible solution and it is not therefore useful in our proof by contradiction。

Now， if we wanted to salvage some hope from this seemingly promising proof plan。

 we could take solace from the fact that there's not just one pink edge crossing the cut AB。

 F isn't the only one， there's actually this other one on the bottom， so let me call that E prime。

Now E being the cheapest edge crossing this cut overall。

 not only is E cheaper than F it cheaper than E prime also， so in some sense with our motivation。

 we could care less which edge we exchange E from crossing this cut because it's cheaper than all of them and we see that at least in this example swapping with E prime yields a good solution。

 it yields a feasible spanning tree。So what have we learned。

 what we've learned is that if we want to execute this exchange argument。

 we cannot blithely exchange with any edge of T star that crosses this cut。

 so the best case scenario so what we're hoping is true that we can always find some suitable edge like E prime on the previous slide so that when we execute this swap。

 we do in fact get a spanning tree。And I'm happy to report that we can indeed always do this。

So what I need to explain is the procedure by which we exhibit this edge E prime。

 which doesn't get us into trouble when we swap， which still gives us a spanning tree after the swap。

So let me explain the procedure by which we identify this magical edge E prime that we can swap with and still be a spanning tree。

 So here's the way to think about it。 So we've got this spanning tree t star。

 we've got this edge which is not yet in t star Now if we just plug E into t star we're going to get a cycle why well a spanning tree remember it has a path between each pair of vertices。

 So if this new edge maybe it's endpoints are U and V T star already has a path between U and V So when you plug in this new direct edge between U and V it closes the loop。

 it gives you a cycle So let's go ahead and call that cycle capital C。

Let me also redraw the picture from the example on the previous slide so you can see what that cycle was in that special case。

Now here's the pattern to notice about this cycle capital C， at least in this example。

 which is that the lousy edge， the edge F for which when we swapped。

 we didn't get a spanning tree that's off of this cycle capital C， whereas the good edge。

 the edge where we could do a swap and get a spanning tree E prime that's on this same cycle capital C and that turns out to be true in general。

 so when you add the edge to the spanning tree and you get a new cycle。

 that cycle is what furnishes the candidates for swaps that will give you a new spanning tree。

So the one lingering concern。 then we have this cycle。

 all edges of the cycle are going to be good candidates for swapping。

 We just need to make sure that there is some edge that actually crosses this cut AB like the edge E prime does in the picture。

 But here we're going to rely on a effect from previous video。

 the double crossing lema remember the double crossing lima says that if you have a cycle that crosses the cut at least once then it has to cross it twice So if you cross once that it has to loop back around that and looping back around it's going to cross it a second time。

 So this cycle capital C， we know it crosses the cut AB once that's because it includes the original cheapest edge across the cut E So it's got to cross it a second time。

 if it's got to be an E prime in the cycle crossing the cut and that's going to allow us to do the swap and get a new cheaper spanning tree completing the contradiction。



![](img/2524bf4944729479adb045f45ad0462b_14.png)

So just to spell things out in a little more detail。

 So what we do is we first say we use the double crossing Lemo so we have this purported minimum spanning tree t star。

 we have this cheap edge E not in it we plug E into the spanning tree。

 we get the cycle we call the cycle capital C the cycle crosses the cut A B once through the edge E crosses it a second time by the double crossing lemo。

 we're going call that edge E prime since E prime crosses the same cut as E we know E prime is strictly more expensive than E remember E' is the cheapest one crossing this cut AB So now what we do is we execute the swap with this new edge E prime so E primes in t star the cheapest edge E is not in t star so we can swap them we can take we can rip E prime out。

 we can stick E in Now something I want you to think through carefully at home。

 commit yourself this is true is that because we pluckged E prime from this cycle this new tree which I'm going call capital T this is a spanning tree necessarily intuitively the reason being you plug in E you get this one cycle involving。

EAnd then when you rip out E prime， you destroy the cycle and because it's on a cycle。

 you don't destroy connectivity between any pair of vertices。

 there's still one path between each pair but make sure you believe that convince yourself at home。

And once you're so convinced you will also realize that we've finished the proof。

 we've executed our proof by contradiction since E was the cheapest edge crossing the cut and E prime is another edge crossing the cut。

 E's got to be cheaper since T differs from T star only in the swap of these two edges。

 its aggregate cost has gone down， and that contradicts the purported optimality of T star completing the proof of the cut property。

