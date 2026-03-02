# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P148：20_02_07_NP完全问题的算法方法.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

This video is a segue between bad news and good news。 The bad news。

 which we've now discussed is NP completeness。 The fact that there are computationally intractable problems out there in the world。

 In fact， they're fairly ubiquitous and you're likely to encounter them in your own projects。



![](img/7e0cd738287171db8ad9d70172ac6a04_1.png)

The good news is that NP completeness is hardly a death sentence。

 indeed our algorithmic toolbox is now rich enough to provide many different strategies toward coping with NP complete problems。

So suppose you'd identified a computational problem on which the success of your new startup company rests。

 Maybe you've spent the last several weeks throwing the kitchen sink at it。

 All the algorithm design paradigms， you know， all the data structures， All the primitives。

 Nothing works。 Finally， you decide to try to prove the problem is NP complete。 and you succeed。 Now。

 you have an explanation for why your weeks of effort have come to not。

 But that doesn't change the fact that this is the problem that governs the success of your project。

 What should you do。Well， the good news is NP completeness is certainly not a death sentence。

 There are people solving， or at least approximately solving NP complete problems all the time。

 However， knowing that your problem is N complete does tell you where to set your expectations。

 You should not expect some general purpose， superfa algorithm like we have for other computational problems。

 like， say， sorting or single source shortest paths。😊。

Unless you're dealing with unusually small or well structured inputs。

 you're going to have to work pretty hard to solve this problem and also possibly make some compromises。

The rest of this course is devoted to strategies for solving or approximately solving NP complete problems。

 and the rest of this video， I'll give you an orientation for what those strategies are and what you can expect to come。

So as usual， I'm going to focus here on general purpose strategies that cut across multiple application domains。

As usual， these general principles should just be a starting point。

 you should take them and run with them， augmenting them with whatever domain expertise you have in the specific problem that you need to solve。

The first strategy is to focus on computationally tractable special cases of an NP complete problem relatedly。

 you want to think about what's special about your domain or about the data sets that you're working with and try to understand if there's special structure which can be exploited in your algorithm。

Let me point out we've already done this in a couple of cases in this course。

The first example we saw concerns the weighted independence set。

 So we studied this problem on path graphs， but the computational problem makes perfect sense in general graphs。

 The general problem is I give you as input an undirected graph。 Every vertex has a weight。

 and I want the maximum weight subset of vertices， that's an independent set。

 And remember in an independent set， you are forbidden to take any two vertices that are neighbors。

 So in an independent set， none of the pairs of vertices that you've picked are joined by an edge。

In general graphs， the weighted independent set problem is NP complete。

 so we certainly don't expect it to have a polynomial time algorithm。

 but in the special case where the graph is a path， as we saw， there's a linear time。

 dynamic programming algorithm that exactly solves the weighted independent set problem。

 So path graphs form a special case of the weighted independent set problem that's computationally tractable。

 solvable and polynomial even linear time。 In fact。

 the frontier of tractability can be pushed well beyond path graphs on the homework I asked you to think through the case of graphs that are trees and notice that you can still do dynamic programming efficiently to compute weighted independent sets and trees。

 you can even get computationally efficient algorithms for a broader class of graphs known as bounded tree with graphs。

 So the definition of that's a little outside the scope of this course。

 but you can go even beyond trees。So the second example follows from our dynamic programming algorithm for the Napsack problem。

 so we discussed that running time and we explained why it's exponential time。

 the running time of our dynamic programming Napsack algorithm is in the number of items times capital W。

 the Napsack capacity， and because it only takes log W bits to specify the capacity capital W。

 we don't call that a polynomial time algorithm。But imagine you only have to solve a Napsack instance where the capacity is not too big。

 maybe even say the capacity capital W is big O of N and you definitely will see Napsack instances in practice which possess that property Well then our dynamic programming algorithm just runs in time O of n squared and that's a bona fide polynomial time algorithm for this special case of a small Napsack capacity。

So next let me mention a couple of examples we're going to see in the forthcoming videos。

 the first one is going to concern the twoat problem。

So twoatAT is a type of constraint satisfaction problem。

 remember in a constraint satisfaction problem you have a bunch of variables。

 each one gets assigned a value so the simplest cases the Boolean case reach variable can be zero or one。

 false or true， and then you have a bunch of clauses which specify the permitted joint values of a collection of variables。

The two in twoat refers to the fact that each constraint involves the joint values of only a pair of variables。

 So a canonical constraint in a twoat instance is going to。

 for two variables specify three joint assignments that are allowed and one that's forbidden。 So。

 for example， maybe it will say， oh， for variables X 3 and x 7。 It's okay to set them both to true。

 It's okay to set them both to false。 It's okay to set 3 to true and 7 to false。

 but it's forbidden to set3 to false and 7 to true。

 So that's a canonical constraint in a two S instance。3atAT， it's the same thing。

 except the constraints involve the joint values to a triple of variables。

 and it's going to forbid  one out of the eight possibilities。Now。

 the three sad problem is a canonical NP complete problem that was really singled out by Cook and Levin as being sufficiently expressive to encode all problems in N。

 But if each constraint has size only two， then， as we'll see。

 the problem becomes polynomial time solvable。 There's a couple ways of proving that。

 we're going to talk about a local search algorithm that checks whether or not there is indeed an assignment to the variables that simultaneously satisfies all of the given constraints。

So the final example we'll discuss in more detail later， but just very briefly。

 we're going to discuss the vertex cover problem， This is a graph problem and a vertex cover is just the complement of an independent set so while an independent set cannot take two vertices from the same edge in the vertex cover problem you have to take at least one vertex from every single edge and then what you want is you want the vertex cover that minimizes the sum of the vertex weights。

Yet again， this is an NP complete problem in general。

 but we're going to focus on the special case where the optimal solution is small。

 That is we're going to focus on graphs where there's a small number of vertices such that every single edge has at least one endpoint in that small set。

 and we'll see that for that special case using a smart kind of exhaustive search we'll actually be able to solve the problem in polynomial time。

So let me reiterate that these tractable special cases are meant primarily to be building blocks upon which you can draw in a possibly more sophisticated approach to your NP complete problem。

 So just to make this little more concrete， let me just kind of dream up one scenario to let you know what I'm thinking about。

 Imagine， for example， that you have a project where unfortunately it's not really twoat that you're confronting it's actually a threeat instance So you're feeling kind of bummed threeat MP complete and maybe you have1000 variables and certainly you can't do brute4 search over the two to the 1000 possible ways of assigning values to your  thousand variables。

But maybe the good news is because you have domain expertise because you understand this problem。

 instance， you know that yeah， there's 1000 variables， but there's really 20 that are crucial。

 You have a feeling that all of the action basically is boiling down to how these 20 core variables get assigned。

 Well， now， maybe you can mix together， some brute for search with some of these tractable special cases。

 For example， you can enumerate over all two to the 20 ways of assigning values to this core set of 20 variables to the 20 is roughly a million。

 that's not so bad And now， what you're going to do is for each of these million scenarios。

 you check whether there's in a way to extend that tenet of assignment of 20 values to the 20 variables to the other 980 variables so that all of the constraints get satisfied。

 The original problem is solvable if and only if there exists a way of assigning values to these 20 variables that successfully extends to the other 980。

 Now， because these are the crucial variables， and it's where all the action。😊。

s maybe as soon as you assign all of them zeros and ones， the residual sat instance is tractable。

 for example， maybe it just becomes a simple twoatAT instance and then you can solve it in polynomial time So this gives you a hybrid approach approach brute for search at the top level tractable special cases for each guess of assignments to the 20 variables and you're off to the races and I hope it's clear I mean this is just one possible way that you might combine the various building blocks we developing into a more elaborate approach to tacklingmp complete problem and that's generally what they take。

 they take a fairly elaborate approach because after all they aremp complete you've got to respect that。

So with that digression complete， let me mention what are the other two strategies we're going to be exploring in the lectures to come。

So the second strategy， which is certainly one very common in practice， is to resort to heuristics。

 that is to algorithms which are not guaranteed to be correct。

We haven't really seen examples of heuristics in the course thus far。

 Those of you that are alumni of part1， perhaps we could classify Carger's randomized minimum cut algorithm as a heuristic because it did have a small failure probability of failing to find the minimum cut。

 But rather I'm going to focus on some examples in the upcoming lectures。

 I'm going to use the Napsackack problem as a case study。 And what we'll see is that our toolbox。

 which contains various algorithm design paradigms。

 it's useful not just for designing correct algorithms。

 but it's also useful for designing heuristics。 So in particular。

 we'll get a pretty good algorithm for the Napsack problem。

 using the greedy algorithm design paradigm， and we'll get an excellent heuristic for Napsackack using the dynamic programming algorithm design paradigm。

The final strategy is for situations where you are unwilling to relax correctness or unwilling to consider heuristics。

 Now， of course， for an MP complete problem， if you're always going to be correct。

 you're not you don't expect to run in polynomial time。

 but there are still opportunities to have algorithms that， while exponential time in the worst case。

 are smarter than naive brute force search。So we have， in fact。

 already seen one example that can be interpreted as an implementation of this strategy。

 That's for the Napsack problem。 So in the Napsack problem。

 naive brute force search would just run over all possible subsets of the items。

 it would check if a subset of items fit in the Napsack。 if it does。

 it remembers the value and then it just returns the feasible solution with maximum value。

 that has time proportional to 2 to the n where n is the number of items。

 our dynamic programming algorithm has running time n times capital W。 Now， of course。

 this is no better than2 to the N if the Napsack capacity is huge if it is itself2 to the N。

But as we argued， if W is smaller， this algorithm is going to be faster。

 and also as you learned on the third programming assignment， sometimes even though W is big。

 dynamic programming is going to beat the crap out of brute force search。



![](img/7e0cd738287171db8ad9d70172ac6a04_3.png)

So I'll show you a couple of other examples， we'll talk about the traveling salesman problem where naive brute force search would take roughly n factorial time where n is the number of vertices。

 will give an alternative dynamic programming based solution， which runs in time only two to the end。

 which is much better than n factorial。The third example， which we'll cover in a forthcoming video。

 we already alluded to briefly on the last slide。's for the vertex cover problem。

 So this is where you're given a graph If every vertex has a weight。

 and you want the minimum weight subset of vertices that includes at least one end point from every edge。

We're going to consider the version of the problem where you want to check whether or not it's possible to have a vertex cover that uses only k vertices。

 whether or not there exists K vertices that includes one endpoint， at least from each edge。

 The naive root force search will run in time end to the K， which gets absurd。

 even when K is quite small， but we're going to show that there's a smarter algorithm。

 which is still exponential in K that runs in time only two to the K times the size of the graph。

