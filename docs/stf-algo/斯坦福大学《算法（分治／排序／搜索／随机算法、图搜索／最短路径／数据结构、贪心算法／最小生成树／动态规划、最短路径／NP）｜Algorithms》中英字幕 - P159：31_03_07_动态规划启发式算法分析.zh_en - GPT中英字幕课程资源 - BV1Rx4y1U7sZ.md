# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P159：31_03_07_动态规划启发式算法分析.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/cf463caa3070d624c5f30fec498ef36a_0.png)

Let's turn to the analysis of our dynamic programming based heuristic for the Napsack problem。

 In particular， let's understand precisely how the running time of this heuristic depends on the desired accuracy Epsilon。

 We jog your memory。 What are the two steps of our dynamic programming based heuristic。

 The first thing we do is we massage the item values。

 We round them so that they are relatively small integers。



![](img/cf463caa3070d624c5f30fec498ef36a_2.png)

Precisely for each item I， we define the hat to be what you get by dividing the item size by M and then rounding down to the nearest integer。

 In step 2， we invoke our second dynamic programming solution for the Napsack problem。

 and we pass to it， these new values of the V hats。

 as well as the original item sizes and the original Napsack capacity。This algorithm， as stated。

 is underdetermined， that's because I haven't told you how to set the parameter M。

We do at least understand qualitatively the role of M and how it influences the choice in the accuracy running time trade off。

 specifically， the bigger we set M， the more information we lose when we round the original values。

 the V's to the V hat eyes。 More loss in information should translate to less accuracy， larger M。

 less accuracy。 On the other hand， the bigger we take M， the smaller the transformed item values。

 the V hats。 Remember， the running time of our second dynamic programming algorithm is proportional to the largest item value。

 So smaller item values translates to faster running times。 summarizing the bigger the M。

 the less the accuracy， but the faster the algorithm。



![](img/cf463caa3070d624c5f30fec498ef36a_4.png)

![](img/cf463caa3070d624c5f30fec498ef36a_5.png)

Here's our plan for the analysis。 We begin by studying the accuracy constraint。 Remember the setup。

 The client is giving us a positive parameter epsilon。

 and it is our responsibility to output a feasible solution whose total value is at least 1 minus epsilon times that of an optimal solution。



![](img/cf463caa3070d624c5f30fec498ef36a_7.png)

![](img/cf463caa3070d624c5f30fec498ef36a_8.png)

This constraint on our algorithms accuracy should translate to an upper bound on how large a value of M we can get away with。

 Remember， as we jack up M， we lose accuracy。 So the first question we're going to study is how large an M can we get away with while still being guaranteed to compute a solution within 1 minus epsilon times that of an optimal one。

Once we solve this problem and we understand how large a value of M that we can get away with。

 how aggressive we' permitted to be with the scaling will then evaluate the running time of the resulting algorithm for that particular choice of M。



![](img/cf463caa3070d624c5f30fec498ef36a_10.png)

To answer this first question， how big can we take M subject to an accuracy constraint of 1 minus epsilon。

 it's important to understand in detail how the rounded item values。

 the V hats compare to the original item values， the V's。

 That's what this quiz is meant to ask you to think about。



![](img/cf463caa3070d624c5f30fec498ef36a_12.png)

Remember how we obtain V hat I from V。 First we decrease it to the next multiple of M then we divide it by M。

 so we can think of M times v hat of I as what we have just after we've rounded down to the nearest multiple of M。

 And before we actually divided by M。 So how did we get to this M times V hat I。

 we decreased V down to the next nearest multiple。 So we decreased it by somewhere between0 and M。

 So that result is somewhere between V minus M and V。

So let's now assemble a few preliminaries crucial for the accuracy analysis。

 So what have we learned from the quiz， we learned that for each item I。

 the rounded value V hat I scaled up by M。 So intuitively。

 this is after we've rounded V down to the nearest multiple。

 but before we've divided that lies somewhere between V as an upper bound and V minus M as a lower bound。

 So let me extract from this two different inequalities。

 one which expresses an upper bound on V in terms of V hat I and then one which expresses a lower bound on V in terms of V hat I。

So there are two inequalities which are immediate from this fact。

 let me go ahead and give them names1 and2。 we'll put these to use in the next slide。

 So first of all， the value V， well， that's lower bounded by M times the rounded value v hat I。

 and then V hat I we can lower bound that by V after we subtract M from it。

 So we'll call those inequalities 1 and2。

![](img/cf463caa3070d624c5f30fec498ef36a_14.png)

So these first two inequalities， they're important for us， but they don't have a lot of content。

 They're just sort of immediate from our definition of step1 of our algorithm from the way we do our rounding。

 but step 2 of our algorithm gives us a third inequality， which is much more powerful。 And this says。

 well look， in the second step， we solve a Napsack instance optimally It's true。

 we solve it for the wrong values。 we solve it for the V hats。

 But for these rounded values of the V hats， the solution we come up with is better than any other。



![](img/cf463caa3070d624c5f30fec498ef36a_16.png)

In particular， if we measure value using the rounded values， the V hats。

 then the solution S output by art heuristic is even better than the solution S star optimal for the original problem。

 optimal for the VIs。

![](img/cf463caa3070d624c5f30fec498ef36a_18.png)

That is， if we sum up the V hat eyes of the items in our solution S。

 and we compare it to the sum of the V hat I in any other solution， in particular。

 the solution S star optimal for the original instance， we come out ahead。

 Our sum of values is bigger。 That's going to be our inequality number3。

These three inequalities are pretty much all we got going for us。

 but fortunately they are sufficient to solve the problem that we asked to determine how large an M we can get away with。

 subject to guaranteeing an accuracy of1 minus epsilon。To see this， let's just follow our nose。

 let's just see what happens if we chain these three inequalities together。 Now。

 the third one seems to have the most content。 that really says we're optimally solving this problem with the transform values of the V hat。

 So let's start by just writing down yet again in equality number three。

So inequality3 just says that the sum of the transform values。

 the sum of the v hats in R heuristic solution capital S is at least as good as any other solution in particular that of the solution S star optimal for the original problem with the original item values So inequality3 is a fine starting point fundamentally what we're trying to do here is lower bound the performance of the solution S spit out by r heuristic and that's what the inequality does。

 The one problem is is it's justifying the performance of S in terms of the wrong data in terms of the transform values of the v hats。

 whereas what we really care about of the original values of the vs。

 So we need to take this inequality 3 as a seed and grow from it a chain of inequalities rewriting on both the lefthand side and the right hand side these transform values of the v hats in terms of the original values of the V's and we'll use inequalities1 and2 to do that As we grow the chain to the left we want quantities that are only getting bigger and bigger as we grow the chain to the right。

 we want quantities that are only getting smaller and smaller。

 hopefully at the end of the day when the dust settles we'll have an approximate。



![](img/cf463caa3070d624c5f30fec498ef36a_20.png)

optimality results for our heuristic solution S。

![](img/cf463caa3070d624c5f30fec498ef36a_22.png)

Now， if you look back at inequalities1 and 2， you'll see that both are in terms of the quantity M times V hat。

 so it's going to be convenient to multiply both sides of this inequality by M。

 of course it's still valid if I do that。

![](img/cf463caa3070d624c5f30fec498ef36a_24.png)

![](img/cf463caa3070d624c5f30fec498ef36a_25.png)

![](img/cf463caa3070d624c5f30fec498ef36a_26.png)

To extend this chain of inequalities on the left hand side。

 we need to tack on a quantity which is only bigger。

 that is we need to upper bound m times v hat I in terms of the original value VI。

 but inequality1 simply says that indeed m times v hat I is never bigger than the original value VI。



![](img/cf463caa3070d624c5f30fec498ef36a_28.png)

![](img/cf463caa3070d624c5f30fec498ef36a_29.png)

So we simply apply in equality one to each item in the heuristic solution capital S。

 and we get an upper bound of sum over the items in our solution S of the value of that item。

 so that's great we get a lower bound on the performance of our solution。

 that's exactly what we want。

![](img/cf463caa3070d624c5f30fec498ef36a_31.png)

![](img/cf463caa3070d624c5f30fec498ef36a_32.png)

To grow the chain of inequalities to the right， we need a quantity which is only smaller。

 That is we want to lower bound M times v hat I in terms of some function of the original value v sub I。

 Now， v sub I can be bigger than m times v hat I。 Remember， we round it down。

 But inequality 2 says it can only be bigger by at most M。 So if we subtract M from V。

 we get a lower bound on M times v hat I。 So we just apply that term by term to the optimal solution S star。



![](img/cf463caa3070d624c5f30fec498ef36a_34.png)

![](img/cf463caa3070d624c5f30fec498ef36a_35.png)

So just by following our nose in this way， we get exactly what we want。

 we get on the left hand side what we really care about。

 namely the total value of the solution output by our heuristic。

 And this is the total value with the original values mind you， not with a transformed ones。

 but the ones we really care about， we get a lower bound on that total value。

 That's exactly what we wanted in terms of the best case scenario。

 the total value of the optimal solution。

![](img/cf463caa3070d624c5f30fec498ef36a_37.png)

And the only blemish is we pick up this error of at most minus M for each item I in the optimal solution S star。

 So let's just lower bound this crudely， the optimal solution at star。

 it can only have n items at most。 so we pick up a minus M at worst for each of those and most n items。

 So if we subtract an error term of M times n， that gives us a lower bound on the value of our solution S。



![](img/cf463caa3070d624c5f30fec498ef36a_39.png)

![](img/cf463caa3070d624c5f30fec498ef36a_40.png)

So now that the dust is cleared， we see that we have a performance guarantee for our solution S in terms of that of the optimal solution S star。

 Basically， we're off by this error term of M times n。 Remember。

 M is this parameter that governs how aggressively we scale the item values and it's controlling the running time accuracy trade off。

 We were expecting this all along， we argued that the bigger you take M。

 the more information you lose。 So the less accuracy you'd expect。 And indeed。

 the extent that we're off by the optimal solution is growing linearly in this parameter M。



![](img/cf463caa3070d624c5f30fec498ef36a_42.png)

The question we're striving to answer， remember， is how big an M can we get away with and still be sure that our solution is within a1 minus epsilon factor of the optimal one。

Well， to achieve this， we just need to make sure that the worst case error in our solution。

 M times n is never bigger than an epsilon fraction of the optimal solutions value。

 that is we just set M small enough that M times n is not more than epsilon times the optimal value。

So this inequality is meant to tell us how to set the parameter M in our algorithm。

 but you'd be right to complain that on the right hand side there's a quantity here that we don't actually know right we don't actually know the optimal value of the optimal solution as star that after all。

 is what we're trying to compute at least approximately in the first place。



![](img/cf463caa3070d624c5f30fec498ef36a_44.png)

So instead， what we're going to do is just use a crude lower bound on how small the optimal solution value could be。

 Let's make a trivial assumption。 Let's assume that each item has a size at most thenapssack capacity。

 That is each item fits by itself inside the knapsack。

 Any items which fail that test obviously can be deleted in a preprocessing step。

 Then the optimal solution， if nothing else， It's at least as large as the value of the max value item。

So to satisfy the desired accuracy constraint， all we need to do is set M small enough so that M times n is at most the right hand side listed here。

 Of course， it's sufficient to set M even smaller so that M times n is no more than an even smaller number。

So in our algorithm， we just set M to be the number that equalizes M times n。

 the left hand side with our lower bound on the right hand side， namely Epsilon times V max。

So notice these are all indeed parameters known to the algorithm， it， of course。

 knows how many items in there are， it knows epsilon that's the parameter supplied to the algorithm by the client。

 and it's easy to compute Vmax， the maximum value item。

 so the algorithm is in a position to set M so that this equality holds that is to set M equal to Epsilon Vmax over N that finally completes the description of the dynamic programmingbased heuristic。

So if' now completed the answer to the first question that we asked。

 how large an M can we get away with， subject to the accuracy constraint of 1 minus epsilon。

 we can get away with M as large as epsilon times the largest item value divided by n。



![](img/cf463caa3070d624c5f30fec498ef36a_46.png)

And now I hope that everybody is holding their breath and crossing their fingers just a little bit。

 because remember， M not only governs the accuracy， it also governs the running time。

 The more aggressively that we can scale the numbers， the larger we can take M。

 the faster the algorithm， And the question now is。

 are we permitted to take M large enough that the resulting heuristic running time is polynomial。



![](img/cf463caa3070d624c5f30fec498ef36a_48.png)

So the running time of the heuristic is certainly dominated by step two where we invoke our dynamic programming algorithm and the running time there is n squared times the maximum item value passed to that subroutine。

 that is the maximum value of a scaled value， the maximum V hat I。



![](img/cf463caa3070d624c5f30fec498ef36a_50.png)

![](img/cf463caa3070d624c5f30fec498ef36a_51.png)

So the big question then is， how big can these scaled item values， the V hatt I be？



![](img/cf463caa3070d624c5f30fec498ef36a_53.png)

So pick your favorite item I。 How big can its transform value V hat I be， Well。

 how do we get V hat I， We take the original value V I， We round it down and we divide by M。

 So the biggest， certainly that V hat I could be is the original value V I divided by M。

That obviously is at most the maximum original value divided by M。

Now we plug in our selection for M epsilon times Vmax over n。Very happily。

 the two Vmaxes cancel leaving us just with N over Epsilon。

Plugging in and over Epsilon as an upper bound on every transformed value passed to the step two dynamic programming solution。

 we get an overall running time of N cubed over Epsilon。The running time does degrade with Epsilon。

 the smaller the epsilon， the bigger the running time。 Of course。

 you would expect that for any NP complete problem。As you take epsilon smaller and smaller。

 you need to take M smaller and smaller to get the accuracy guarantee that results in less aggressive scaling of the item values。

 in turn， bigger transform values get passed to the dynamic programming subppertine resulting in the bigger running time。

Nevertheless， this does show that the full continuum of running time accuracy tradeoffs is possible for the NApsack problem。

 you want arbitrarily close approximation for this problem， you've got it。



![](img/cf463caa3070d624c5f30fec498ef36a_55.png)