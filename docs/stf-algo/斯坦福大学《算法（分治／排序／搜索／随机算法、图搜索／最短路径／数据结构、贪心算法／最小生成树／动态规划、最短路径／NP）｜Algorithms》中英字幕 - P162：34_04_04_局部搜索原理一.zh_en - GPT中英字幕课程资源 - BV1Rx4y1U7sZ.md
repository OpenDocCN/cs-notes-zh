# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P162：34_04_04_局部搜索原理一.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

Now that we've seen a concrete example of local search in the specific context of the maximum cut problem。

 let's move toward talking about this technique more generally。

So let's think abstractly about some computational problem。

 let's say there's a set capital X of the candidate solutions to this problem。

 maybe you want to search whether or not there exists a solution with a given property。

 maybe you want to find the solution which is optimal in some sense。

What are some examples Well in our last video X was the cuts of some given graph G。

 Other examples would include the tours of an instance of traveling salesman problem or perhaps the possible assignments to variables in some constraint satisfaction problem。

A fundamental ingredient to the local search approach is the definition of a neighborhood that is for each candidate solution。

 little X in the space of all possible solutions， capital X。

 you need to define which other solutions little Y are the neighbors of little X。

Let's look at some concrete examples in the maximum cut problem last video。

 we were implicitly defining the neighbors of a given cut to be those cuts you can obtain from the given one by moving a single vertex from one side to the other。



![](img/dd20358126db49f999a0a6d82319b74f_1.png)

If you're taking a local search approach to a constraint satisfaction problem。

 something like twoat or3atAT， a common approach is to define two variable assignments to be neighbors。

 if and only if they differ in the value of a single variable。

 so for the boolean case where variables are either true or false。

 you're going to define two assignments to be neighbors。

 if you can get from one to the other by flipping the value of a single variable。

For the traveling salesman problem there's a lot of sensible ways to define neighborhoods。

 one simple and popular approach is to define two traveling salesmen tours to be neighbors if and only if they differ in the minimum possible number of edges。

 if you think about it for a second you'll realize that the minimum possible number of edges。

 the two TSP tours differ in is two。So for example， in Pink。

 I've shown you two neighboring TSP tours， the first tour has edges from U to V and from W to X。

 but by contrast the second tour has the crisscrossing edges from U to X and from V to W。

 all of the other edges in the two tours are the same。

Once you've identified the space of candidate solutions to your computational problem and once you've settled on a neighborhood for every candidate solution。

 you're in a position to run local search local search just iteratively improves the current solution。

 always moving to a neighboring solution until you can't improve things any further。



![](img/dd20358126db49f999a0a6d82319b74f_3.png)

I'm going to specify here a highly underdetermined version of local search to highlight the number of design decisions that you've got to make。

 if you really want to apply local search to a problem in your own projects。

 We'll talk about the possible instantiations of the different design decisions in the next couple of slides。

 So for starters， you have to initialize the search with one of the candidate solutions。

 Some little X。 How do you pick it， Well， there's a number of approaches。

 We'll discuss that in more detail in a sec。Now just like in our maximum cut local search algorithm。

 we take the current solution， whatever it is X， we look for a neighboring  one y which is superior。

 if we find such a y， then we move to that superior solution， if there is no superior Y。

 we're locally optimal and we just return the current solution。

Our local source algorithm for the maximum cut problem that we discussed last video is in fact an instantiation of this generic procedure where the set capital X of all solutions is just the cuts of the given graph。

 and two cuts are defined to be neighbors， if and only if you can get from one to the other by moving a single vertex from one group to the other。

In that algorithm， as we are here， we just done from some arbitrary solution， some arbitrary cut。

 we repeatedly searched for a superior neighboring solution that as we tried to see if there was a way to move a vertex from one group to the other to get a better cut。

 if we found such a superior neighboring solution， we iterated from that better solution。

 and then when we couldn't iterate any more when there were no better neighboring cuts。

 we just halted and returned to the final result。You can apply this generic local search procedure to other problems in exactly the same way as an example。

 think about the traveling salesman problem。 let's say we define neighborhoods like we did on the last slide with two tours being neighbors if and only if they differ in exactly two edges and n minus two edges are in common。

 What do you do， you start from some arbitrary traveling salesman tour and now you iterate。

 you keep looking for a neighboring superior solution that is from the current tour you consider all tours you can reach by changing exactly two edges of the current tour you check if any of those and choose two solutions have strictly smaller cost if any of them do。

 you iterate from that new superior solution。 when you can't iterate anymore when all of the neighboring solutions are at least as costly as the one you're working with。

 that's a locally optimal tour and you return that as your final output。



![](img/dd20358126db49f999a0a6d82319b74f_5.png)

In the rest of this video， I want to continue discussing local search at a high level。

 talking about some of the design decisions that you've got to make。

 as well as some of the performance characteristics you can expect after we finish this high level discussion that we'll move on to some videos on another concrete example of local search。

 specifically to twoat， a specific example of a constraint satisfaction problem。



![](img/dd20358126db49f999a0a6d82319b74f_7.png)

Let's begin with three frequently asked questions about underdetermined characteristics of the generic local search procedure I just showed you。

Question number one concerns step number one of the algorithm you need to somehow come up with this arbitrary starting point X。

 How do you do it？To answer this question， let me crudely classify the situations in which you might be using local search into two categories。

In the first category you're really depending on local search to come up with a good approximate solution to an optimization problem。

 you really have no idea how to get close to an optimal solution other than through some local search approach。

The second category of scenarios is where you have some pretty good heuristics that seem to be delivering to you pretty good solutions to your optimization problem。

 and you just want to use local search as a post processing step to do even better。

So let's start with the first category where all of your eggs are in one basket you need local search to deliver to you a pretty good solution to an optimization problem。

 So this is a tricky spot to find yourself in。 Local search is guaranteed to deliver to you a locally optimal solution。

 but in many problems， locally optimal solutions can be much。

 much worse than what you're looking for a globally optimal solution in the special case of the maximum cut problem。

 we had a performance guarantee of 50% which already is only a so so guarantee。

 but for most optimal problems， even that kind of performance guarantees out of the question。

 there are locally optimal solutions far worse than the globally optimal ones。On the other hand。

 you know there are some good locally optimal solutions out there， in particular。

 the globally optimal solution is also a locally optimal one。Now， if you just run local search once。

 it's not clear how to evaluate the quality of the solution that's returned to you。

 you run the algorithm， it hands you a solution， it has cost 79217。 Is that good or bad， Who knows？

An obvious approach to doing better is to run local search many times， say thousands of times。

 even millions of times， and then amongst all of the local optima that the different runs of your local search algorithm returns。

 you pick the best one and you make that your final solution。

To encourage your local search algorithm to hand back to you different local optima when you run it over and over again。

 you want to be making some random decisions。And an extremely common point to make a random decision is in step1 of local search is in choosing your initial starting point little X。

 so for example， in the maximum cut problem you'd want to start with a random cut with each vertex equally likely to be an A or B with a traveling salesman problem you might want to start from a random tour that is a random permutation of the in vertices in a constraint satisfaction problem you could begin by giving each variable independently a random value。

If this seems kind of like throwing dart to the darkboard。That's what it is。

 Turns out there's a lot of stubbornly difficult problems out there for which the state of the art is really not substantially better than running independent trials of local search with different random initial positions and returning the best of the local optima that you find。

Now let's suppose you're in this second happier category of scenarios where you've got a better handle on your optimization problem。

 maybe you've figured out how to use greedy algorithms or maybe mathematical programming anyways you have techniques that generate close to optimal solutions to some optimization problem but why not make these nearly optimal solutions even better how do you do that will feed the output of your current suite of heuristics into a local search post processingces step After all。

 local search only moves to better solutions， it can only make your pretty good solution even better。



![](img/dd20358126db49f999a0a6d82319b74f_9.png)