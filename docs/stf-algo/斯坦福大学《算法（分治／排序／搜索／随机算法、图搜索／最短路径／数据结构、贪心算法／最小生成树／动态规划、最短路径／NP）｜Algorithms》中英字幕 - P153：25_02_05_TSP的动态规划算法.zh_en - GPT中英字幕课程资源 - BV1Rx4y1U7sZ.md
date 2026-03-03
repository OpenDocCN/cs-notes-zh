# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P153：25_02_05_TSP的动态规划算法.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

Having laid the groundwork in the previous video， we're now ready to follow our usual dynamic programming recipe to develop a faster than brute force search dynamic programming algorithm for the traveling salesman problem。



![](img/832d2ebd29d7194c4c1a79b6853be4c4_1.png)

Iterating through all of those quizzes in the last video。

 we developed some healthy respect for the traveling salesman problem。

 We understood why the more natural approaches， which were sufficient for the shortest path problem。

 For example， in the Belmon Ford algorithm， are not good enough to solve TSP。 Now， No surprise。

 TSP is an empty complete problem。 We were sort of ready for this。

 But we now understand it in a pretty concrete way。

 In the single source shortest path problem and subpro。

 All you need to know is where is the path ending and how long could the path be That's not enough for the traveling salesman problem。

 because there's this extra tricky constraint that at the end of the day we want to visit every vertex exactly once。

 So in particular， to make sure we don't have repeat vertices show up in our subproblem solutions。

 we're going to need to remember not just where smaller subproblem end。

 but also the identities of all of the intermediate vertices in the path。

Here then is the final definition of the subprom that we're going to use。

We still want to keep track of where this path ends， so we still have our destination J。

But rather than just specifying a number of vertices that you visit on this path。

 we specify exactly which vertices get visited。 So that's going to be a subset， capital S。

 a subset of1 through n。 and of course， it better contain the initial vertex1 and the final vertex J。

And so for a given choice of J and a given set choice of capital S。

 we define L sub S comma J as the length of a shortest path that starts at vertex 1。

 ends in vertex J visits precisely the vertices in capital S exactly once each。Now。

 I can understand if your eyes widen a little bit when you see this definition。 After all。

 there's an awful lot of choices for the set capital S， an exponential number。

 So you'd be right to wonder whether this approach could possibly give any savings whatsoever over naive brute force search。

One thing worth pointing out， and in some sense， the source of the computational savings is that in a given sub problem。

 while it's true， we're keeping track of which vertices are visited on route from 1 to J。

 we are not keeping track of the order in which those vertices get visited。 And indeed。

 if we had one subprom for every ordering in which you might visit vertices from a given source to a given destination。

 then we'd be stuck with a factorial number of subproblem。

 as it is since we forget the ordering we only focus on subsets that gets us down in more than two to the end range。

 And that's ultimately where the savings over root force search comes from。So as usual。

 once we've gotten the right set of subproble， the rest of the dynamic programming recipe pretty much writes itself。

 but to fill in the details， let me just tell you exactly what the optimal substructure limit is。

 what's the corresponding recurrence， and then the final pseudocode that gives us our better than brute force search algorithm for the Tra salesman problem。

So for the optimal substructureure Leta， we just focus on one particular subpro。

 so that corresponds to a choice of the destination and J and a choice of the set S， it specifies1。

 the starting point， J the ending point plus the rest of the intermediate vertices that we've got to visit along the way。

 exactly onces each。So now we proceed exactly as we did in Belman Ford。

 namely by focusing on the last hop of this path P。

So if the last hop is say from vertex K to vertex J。

 then we can look at the previous part of the path， Call it P prime。 What can we say about it， Well。

 clearly it begins with the vertex 1， Clearly， it ends at the vertex K。

 because the path P visited every vertex in S exactly once。

 the path P prime visits every vertex in the set S minus J exactly once， and， of course。

 the optimal substructureion limitmma says not only is p prime sum path from 1 to k visiting exactly the vertices of S minus j once each。

 it is the shortest such path。The proof is an utterly standard cut and paste argument。

 like we've been doing for all our other optimal substructure les。

 I'll leave it as an exercise for you to fill in the details。As usual。

 the optimal substructure lemma naturally induces a recurrence。 The recurrence just says， well。

 let's look at all of the candidates for an optimal solution identified by the lemma and do brute force search among all those candidates。

That is for a given sub problem indexed by a destination J and a set of vertices S。

 What the recurrence does is it takes the best case scenario that is the best choice of the second to last vertex K。

 Of course， K should lie somewhere in the set capital S。 Also， it should not be the vertex J。

And for a given choice of k， we know the corresponding candidate solution has to be a shortest path from one to K visiting exactly the vertices of S minus J。

Combined with the cost of the corresponding final hop from K2 J。And effectively。

 we're using the same measure of sub problemble size that we were in the Belumman Ford solution。

 just the number of allowable intermediate vertices。 Of course， here。

 the sub problem also specifies exactly which those vertices are。 But as far as a measure of size。

 we just use the cardinality of that set。As always。

 the important property of the size measure is that to solve a subprom of a given size。

 you only need to know the answers of subproblems with strictly smaller size and staring at the recurrence you see that that is indeed the case here。

 you only care about subproblems that visit one fewer vertex because in particular J is excluded。

The dynamic programming algorithm writes itself， we have a two dimensional array。

 two dimensions because we have two indices for each subproblem， one specifying the final vertex J。

 the other specifying these set capital S。It turns out we can get away with a pretty small set of base cases。

 we're only going to need to precompute the entries of the 2D array in which the final destination J equals 1 is the same as the starting vertex。

Now， if S happens to contain just the vertex 1， then the empty path goes from one to one with no intermediate stops。

 that has linked 0。Otherwise， if S contains extratro vertices。

 there's no way to go from one back to one with intermediate stops visiting vertex1 only once。

 So we defined the other sub problems where J equals one to have plus infinity value。Now as usual。

 we solve all the subprom systematically using the recurrence。

 we want to make sure that all the smaller subproms are solved before the bigger ones。

 so in our outer for loop we iterate over the measure of subproblem size。

 which remember is the cardinality of the set S。Amongst sub problems of the same size。

 we don't care what order we solve them， so we just iterate through the sets S of Carinality M in arbitrary order。



![](img/832d2ebd29d7194c4c1a79b6853be4c4_3.png)

So these outer two four loops accomplish the following。

 they iterate through the relevant choices of capital S that is sets S that are cardinality at least2 and that contain the vertex1。

 So that's the first index of our 2D array。 What about the second index J。

 So this is where the shortest path and a given subpro is supposed to stop。 Well。

 sub problemsm only makes sense or only defined if that final vertex J is one of the vertices capital S that you're supposed to visit。

 So when we get to a given choice of capital S at that point。

 we're just going iterate through all of the relevant choices of J。

And if you recall our argument in the base case and the fact that the set SS size at least two。

 there's no point in trying J equals to one。So now that we have a subproblem。

 we have our choice of S， we have our choice of J， we just compute the recurrence for this particular subproblem。

So what is that， Well we take a best case choice of the penultimate vertex。

 So that's some vertex that we've got to visit， a vertex K and capital S。

 other than the one where we stop。 So it can't be equal to J。 And then given a choice of K。

 what is the corresponding solution of that candidate path from one to J。 Well。

 it's whatever the shortest path is from1 to K， which， of course。

 is visiting everything in S except for J。Plus whatever the cost of the final hop is from K to J。

 so the recurrence just figures out what is the optimal choice of K by brute4 search and then by our optimal substructured Lemo we know that's the correct answer to this subproblem。

Now， in almost all of our dynamic programming algorithms， after we solved all the sub problems。

 all we did was return the value of the biggest one。 Here。

 we actually have to do a tiny bit of extra work。 It is not the case that the solution we care about。

 the minimum cost traveling salesman is literally one of the sub problems。 However。

 it is true that we can easily compute the minimum cost of a traveling salesman。

 given solutions to all of the sub problems。So what is the biggest sub problem。 Well。

 there's actually N of them。 Remember， our measure of sub problem size is the cardinality of the set S。

 the number of vertices that you've got to visit in that subproble。

 So in the biggest sub problemsble， S is equal to everything。

 You have to compute a shortest path that visits each of the n vertices exactly once。

 So what are the semantics of one of those sub problems for a given choice of the second index J there's in different choices for that final vertex J。

 That subpro was responsible for computing the length of a shortest path that starts at the vertex1 that concludes the vertex J and that visits every single vertex exactly once。

 Now， how is this different than a traveling salesman。 While all that's missing is that final hop。

 That hop from J to one。So what this means is that after we've solved all of the sub problems in our triple 4 loop。

 we can complete the algorithm with one final brute force search。 This final time。

 the brute force search is over the choice of J。 the last vertex that you visit before you return home to vertex number one。

So you can skip the choice of J equal 1， that one doesn't make sense but for the other n-1 possibilities for that final vertex J。

 you take the previously computed value of a shortest path that starts at 1 and goes to J and visits everybody exactly once you tack on that the cost of the final hop going home to one from vertex J and of those n -1 different solutions。

 you return the best of them。 That is， in fact， the cost of the minimum cost traveling salesman tour。

The correctness argument is the same as it always is。

 The correctness of the optimal substructure lemma implies the correctness of the recurrence。

 and then the correctness of the dynamic programming algorithm follows from the correctness of the recurrence plus induction。

 The running time is equally straightforward。So because in the sub problemsble we're keeping track of a lot of information。

 specifically the identities of all of the intermediate vertices。

 there are a lot of subpro so in particular there's roughly2 to the n choices for the set capital S。

 there's roughly n choices for the final destination J。

 so combining those we get n times 2 to the n subproblem。

How much work do you do per sub problemm Well you have to execute this brute force search over the choices of the vertex K。

 the second to last vertex on the path， K could be almost anything in the set capital S。

 capital S could have linear size。 So you're going to do O of n work per sub problemm。Thus。

 the overall amount of work as promised is big O of n squared times 2 to the n。

This is still exponential time。 There's still severe limits on how big a value of N you're going to be able to execute this algorithm for That said the problem is NPp complete。

 and you have to respect its computational intractability。 And again。

 at least this shows there are often interesting algorithmic opportunities to beat Ruthfort's search even for NP complete problems like the traveling salesman problem。

