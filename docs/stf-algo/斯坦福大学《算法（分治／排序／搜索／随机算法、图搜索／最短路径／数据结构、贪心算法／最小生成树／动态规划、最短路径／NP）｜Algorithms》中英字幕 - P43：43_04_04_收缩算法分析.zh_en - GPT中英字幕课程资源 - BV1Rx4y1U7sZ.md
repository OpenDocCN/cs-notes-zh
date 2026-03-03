# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P43：43_04_04_收缩算法分析.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

So in the last video I left you with a cliffhanger I introduced you to the minimum cut problem。

 I introduced you to a very simple and elegant randomized algorithm in the form of the contraction algorithm。

 we observed that sometimes it finds a in cut and sometimes it doesn't and so the 64。

000 question is just how frequently does it succeed and just how frequently does it fail so now that hopefully you've brushed up on your conditional probability and independence we're going to give a very precise answer to that question in this lecture。

So recall on this problem， we're given as input in undirected graph， possibly with parallel edges。

 and the goal is to compute among the exponential number of possible different cuts that's with the fewest number of crossing edges。

 So， for example， in this graph here。Which you've seen in a previous video。



![](img/15a7f994fac88930473df1e5704e4d6b_1.png)

The goal is to compute the cut AB。Here because there are only two crossing edges and that's as small as it gets。

 That's the minimum and cut problem。 And Carger proposed the following random contraction algorithm based on random sampling。

 So we have n minus two iterations and the number of vertices gets decremented by one in each iteration。

 So we start with n vertices we get down to two and how do we decrease the number of vertices。

 we do it by contracting or fusing two vertices together。 how do we pick which pair of edges。

 which pair of vertices di fuse， but we pick one of the remaining edges uniformly at random So theres however many of the edges there are remaining。

 we pick each one equally likely if the endpoints of that edge are U and V。

 then we collapse you and V together into a single super node。

 So that's what we mean by contracting two nodes into a single vertex and then if that causes any self loops and as we saw the examples。

 we will in general have self loops， then we delete them before proceeding。

 after the n minus two iterations， only two vertices remain。

 you recall that those two vertices naturally。a cut the first group of the cut A corresponds to the vertices that were fused into one of the super vertices remaining at the end。

 the other super vertex corresponds to the set B， the other original vertices of the graph。

So the goal of this video is to give an answer to the following question。

 what is the probability of success， whereas by success。

 we mean outputs particular min cut a comma B。So let's set up the basic notation。

 we're going to fix annual old input graph undirected graph。And as usual。

 we use n to denote the number of vertices and N to denote the number of edges。

We're also going to fix a minimum cuts。A comma B。 if a graph has only one minimum cut。

 then it's clear what I'm talking about here。 If a graph has multiple minimum cuts。

 I'm actually selecting just one of them because we're going to focus on a distinguished minimum cut。

 A comma B， and we're only going to define the algorithm as successful。

 If it outputs this particular minimum cut， A B。 If it outputs some other minimum cut。

 we don't count it， we don't count it as successful because we really want this distinguished minimum cut。

 A comma B。In addition to N and M， we're going to have a parameter K。

 which is the size of the minimum cut， that is it's the number of crossing edges of a minimum cut。

 for example， that cross a comma B。The K edges that across the minimum cut A B。

 we're going to call capital F。So the picture you want to have in mind is there is out there in the world。

 this minimum cut A B。There's lots of edges with both endpoints in A， lots of edges。

 possibly with both endpoints and B， but there's not a whole lot of edges with one endpoint in A and one endpoint in B。

So the edges F would be precisely these three crossing edges here。

So our next step is to get a very clear understanding of exactly when the execution of the contraction algorithm can go wrong and exactly when it's going to work exactly when we're going to succeed。

 So let me redraw the same picture from the previous slide。



![](img/15a7f994fac88930473df1e5704e4d6b_3.png)

So given that we're hoping that the contraction algorithm outputs this cut AB at the end of the day。

 what could possibly go wrong？Well， to see what could go wrong， suppose at some iteration。

 one of the edges in capital F remember F are the edges crossing the min cut A B。

 so it's these three magenta edges in the picture。 Suppose that some iteration。

 one of the edges of F gets chosen for contraction。

Well because this edge of F has one endpoint in A and one endpoint in B。

 when it gets chosen for contraction， it causes this node from A and this node from B to be fused together。

What does that mean， that means in the cut that the contraction algorithm finally outputs this node from a and this node from B will be in the same side of the output cut。

 Okay， so the cut output by the contraction algorithm will have on one side both the node from A and a node from B。

 Therefore， the output of the contraction algorithm。

 If this happens will be a different cut than A B。 will not output A B。

 If some edge of F is contracted。And if you think about it， the converse is also true。

 so let's assume now that in each of the n minus2 iterations。

 the contraction algorithm never contracts an edge from capital F。

 remember capital F are exactly the edges with one endpoint and A and one endpoint and B。

 so if it never contracts any edge of F， then it only contracts edges where both endpoints line capital A or both endpoints line capital B。

Well， if this is the case， then vertices from a always stick together in fused nodes。

 and vertices from B always stick together in the fused nodes。

 There is never an iteration where a node from A and a node from B are fused together。

 What does that mean that means that when the algorithm outputs are cuts。

 all of the nodes in A have been grouped together， all of the nodes and B have been grouped together in each of the two super nodes。

 which means that the output of the algorithm is indeed the desired min cut A comma B。

Summarizing the contraction algorithm will do what we want。

 it will succeed and output the cut a comma B， if and only if it never chooses an edge from capital F for contraction。

Therefore， the probability of success。

![](img/15a7f994fac88930473df1e5704e4d6b_5.png)

That is the probability that the output is the distinguishment cut a comma B is exactly the probability。



![](img/15a7f994fac88930473df1e5704e4d6b_7.png)

That it never contracts an edge of capital F。So this is what we're going to be interested in here。

 This will be the。Object of our mathematical analysis。

 the probability that in all of the n minus two iterations， we never contract an edge of capital F。

So to think about that， let's think about each iteration in isolation and actually define some events describing that。

So for an iteration I， let SI denote the events that we screw up in iteration I。With this notation。

 we can succinctly say what our goal is。So to compute the probability of success。

 what we want to do is we want to compute the probability that none of the events S1。

 S2 up to n SN minus2 ever occur。So I'm going to use this not symbol to say that S1 does not happen。

So we don't screw up in iteration  one， we don't screw up in iteration 2。

 we don't screw up in iteration 3， and so on all the way up to we don't screw up。

 we don't contract anything from capital F。In the final iteration， either。

So summarizing analyzingizing the success probability of the contraction algorithm boils down to analyzing the probability of this event。

 the intersection of all of the not Ss with I ranging from iteration one iteration and minus two so we're going to take this in baby steps and the next quiz will lead you through the first one which is let's have a more modest goal。

 let's just think about iteration number one let's try and understand what's the chance we screw up。

 what's the chance we don't screw up just in the first iteration。

So the answer to this quiz is the second option， the probability is k over M where K is the number of edges crossing the cut a comma B and M is the total number of edges。

 and that's just because the probability of S1。Probably that we screw up。

It's just the number of crossing edges。That's the number of outcomes which are bad， which trigger S1。

Divided by the number of edges， that's the total number of things that could happen。

 and since all edges are equally likely。It just boils down to this。

And by the definition of our notation， this is exactly k over n。

So this gives us an exact calculation of the failure probability in the first iteration as a function of the number of crossing edges and the number of overall edges。

 Now， it turns out it's going to be more useful for us to have a bound。

 not quite as exact in inequality。 That's in terms of the number of vertices N rather than the number of edges N。

 The reason for that is it's a little hard to understand how the number of edges is changing in each iteration。

 It's certainly going down by one each iteration because we contract in edge each iteration。

 but it might go down by more than one when we delete self loops。 By contrast。

 the number of vertices is this very steady obvious process。

 One less vertex with each successive iteration。 So let's rewrite this bound in terms of the number of vertices N。



![](img/15a7f994fac88930473df1e5704e4d6b_9.png)

To do that in a useful way， we make the following key observation。

I claim that in the original graph G that we were given as input。

 every vertex has at least K edges incident on it， that is in graph theoreticaloretic terminology。

 every edge has degree at least K。Where recall K is the number of edges crossing our favorite min cut A comma B。

 So why is that true， Why must every vertex have a decent number of neighbors。

 a decent number of edges incident to it？ Well， it's because if you think about it。

 each vertex defines a cut by itself。 Remember， a cut is just any grouping into of the vertices into two groups that are non empty that don't overlap。

 So one cut is to take a single vertex and make that the first group A and together n minus1 vertices and make that the second group capital B。

 So how many edges cross this cut， well， it's exactly the edges that are incidence on the first note on the node on the left side。

 So if every single cut， if all exponentially many cuts have at least K crossing edges then certainly the n cuts defined by single vertices have at least K crossing edges。

 So therefore， the degree of every vertex is at least K。

So our assumption that every single cut in the graph has at least k crossing edges gives us a lower bound on the number of edges incident on each possible vertex so why is that useful well let's recall the following general fact about any graph。

Which is that if you sum up over the degrees of the nodes， so if you go node by node。

 look at how many edges are instant on that node， that's the degree of V and then sum them up over all in vertices。

 what do you get， you get exactly twice the number of edges。

so this is true for any undirected graph that the sum of the degrees of the vertices is exactly double the number of edges To see this。

 you might think about taking a graph， starting with the empty set of edges。

 and then adding the edges of the graph one at a time。 each time you add a new edge to a graph。

 obviously the number of edges goes up by one and the degree of each of the endpoints of that edge also go up by one。

 and there are， of course， two endpoints。 So every time you added an edge。

 the number of edges goes up by one， the sum of the degrees goes up by two。 Therefore。

 when you've added all the edges， the sum of the degrees is double the number of edges that you've added。

 That's why this is true。Now， in this graph that we have a hand here， every degree is at least K。

 and there's n nodes。 So this left hand side。Of course， is at least。KN for us。So therefore。

 if we just divide through by two and flip the inequality around， we have。The number of edges。

Has to be at least。The size of the crossing cut or the degree of every vertex times the number of vertices divided by two。

 so this is just the previous inequality rearranging。

Putting this together with your answer on the quiz。Since the probability。S1 is exactly K over M。

And M is at least KN over 2。 If we substitute， we get the probability of S1。Is at worst，2 over n。

2 over the number of vertices， and the K cancels out。

So that's sort of our first milestone We figured out the chance that we screw up in the first iteration that we pick some edge from the crosses the cut AB and things look good。

 this is a small number right so in general the number of vertices might be quite big and this says that the probability we screw up is only two over the number of vertices So so far so good Of course this was only the first iteration Who knows what happens later So now that we understand the chances of screwing up in the first iteration。

 let's take our next baby step and understand the probability that we don't screw up in either of the first two iteration that is we're going be interested。



![](img/15a7f994fac88930473df1e5704e4d6b_11.png)

In the following probability。The probability that we don't screw up in the first iteration nor in the second iteration。

Now you should go back to the definition of a conditional probability to realize that we can rewrite an intersection like this in terms of conditional probabilities。

 namely as the probability that we don't screw up in the second iteration。

 given that we didn't do it already。Times the probability that we didn't screw up in the first iteration。

Okay， so the probability that we miss all of these K vulnerable edges in the second iteration。

 given that we didn't contract any of them in the first iteration Now notice this we already have a good understanding of on the previous slide we gave a nice lower bound of this。

 we said there's a good chance that we don't screw up。Probably at least one minus2 to the n。

And in some sense， we also have a very good understanding of this probability。

We know this is one minus the chance that we do screw up。

And what's the chance that we do screw up while these K edges are still hanging out in the graph。

 remember we didn't contract any in the first iteration that's what's given。

 so there are K ways to screw up。And we choose an edge to contract uniformly at random。

 so the total number of choices is the number of remaining edges。

Now the problem is what's nice is we have an exactec。Understanding of this probability。

 This is in equality。 The problem is， we don't have a good understanding of this denominator。

 How many remaining edges are there。We have an upper bound on this。 We know this is at most M-1。

 We certainly got rid of one edge in the previous iteration。 But actually， if you think about it。

 what we need on this quantity is a lower bound。 And that's a little unclear。

 because in addition to contracting the one edge and getting that out of the graph。

 we might have created a bunch of self loops and delete it all of them。

 So it's hard to understand exactly what this quantity is。 So instead。

 we're going rewrite this bounded in terms of the number of remaining vertices。 And， of course。

 we know this exactly n -1 vertices remaining。 We took two in the last iteration。

 we contracted it down to one。 So how do we relate the number of edges to the number of vertices。

 where we do it just in exactly the same way as in the first iteration。

 We make a sort of more general observation。For the first iteration。

 we observed that every node in the original graph induces a cut。With that node on one side。

 the other n minus-1 edges on the other side， but in fact， that's a more general statement。

 even after we've done a bunch of contractions， any single node in the contracted graph。

 even if it represents a union of a bunch of nodes in the original graph。

 we can still think of that as a cut in the original graph so if there's some super node in the contracted graph。

 which is the result of fusing 12 different things together。

 that corresponds to a cut where those 12 nodes in the original graph are the one side A and the other n minus-12 vertices are the other side of the cut B so even after contractions。

 as long as we have at least two nodes left in our contracted graph。

 we can take any node and think of it as half of a cut one side of a cut in the original graph。

Now remember k is the number of edges crossing our minimum cut a comma B。

 so any cuts in the original graph G has to have at least k crossing edges。

So since every node of the contracted graph naturally maps over to a cut in the original graph with at least k edges crossing it。

 that means that in the contracted graph， all of the degrees have to be at least K。



![](img/15a7f994fac88930473df1e5704e4d6b_13.png)

If you ever had a node in the contracted graph that had only say K minus one incident edges。

 well then you'd have a cut in the original graph with only K minus1 edges of contradiction。

So just like in the first iteration now that we have a lower bound on the degree of every single vertex。

 we can derive a lower bound on the number of edges that remain in the graph。

The number of remaining edges is at least one half。

 That's because when you sum over the degrees of the vertices。

 you double count the edges times the degree of each vertex。

 And we just argue that that's at least K in this contracted graph times the number of vertices。

 And we know there's exactly n minus vertices left in the graph at this point。

So now what we do is we plug this inequality， we plug this lower bound on the number of remaining edges on as we substitute that for this denominator。

So in lower bounding， the denominator， we upper bounds。This fraction。

 which gives us a lower bound on  one minus that fraction， and that's what we want。

So what we find is that the probability that we don't screw up。In the second iteration。

 given that we didn't screw up in the first iteration。Where again。

 by screwing up means picking one of these k just crossing Ab to contract is at least。1-2 over。

 and  -1。So that's pretty cool。 We took the first iteration。 We analyzed it。

 We showed the probability that we screw up is pretty low。

 We succeed with probability at least 1 minus2 over n。😊，In the second iteration。

 our success probability has dropped a little bit， but it's still looking pretty good for reasonable values event。

 one minus2 over n minus1。Now， as I hope you've picked up。

 we can generalize this pattern to any number of iterations。

 so the degree of every node in the contracted graph remains at least K。

 the only thing which is changing is the number of vertices is dropping by one。

So extending this pattern to its logical conclusion。

 we get the following lower bound on the probability that the contraction algorithm succeeds。

So the probability that the contraction algorithm outputs the cut AB， you recall we argued。

 is exactly the same thing as the probability that it doesn't contract anything。

 any of the K crossing edges， and either set f in the first iteration， nor in the second iteration。

 nor in the third iteration and so on， all the way up to the final n minus2th iteration。

Using the definition of conditional probabilities， this is just。

The probability that we don't screw up in the first iteration times the probability that we don't screw up in the second iteration。

 given that we didn't screw up in the first iteration and so on。

In the previous two slides we showed that we don't screw up in the first iteration with probably at least one minus2 over n in the second iteration with probably at least1 minus2 over n minus1。

 and of course you can guess what that pattern looks like and that results in the following product。

Now because we stop when we get down to two nodes remaining。

 the last iteration in which we actually make a contraction。

 there are three nodes and in the second to last iteration in which we make a contraction there are four nodes。

 so that's where these last two terms come from。Rewriting。

 this is just n -2 over n times n -3 over n -1 and so on。And now something very cool happens。

 which is massive cancellation。 and to this day， this is always just incredibly satisfying to be able to cross out so many terms。

 so you get n 2 crossing out here， it's going to be a pair of n minus threes that get crossed out and minus fours and so on on the other side there's going to be a pair of fours that get crossed out and a pair of threes that get crossed out and will'll be left with only the two largest terms on the denominator and the two smallest terms in the numerator。

 which is exactly。Two over。

![](img/15a7f994fac88930473df1e5704e4d6b_15.png)

N times n minus-1。And to keep things simple among friends。

 let's just be sloppy and lower around this by one over n squared。So that's it。

 that's our analysis of the success probability of Car's contraction algorithm， pretty cool。

 pretty slick， huh？Okay， I'll concede， probably you're thinking， hey， wait a minute。

We're analyzing the probability that the algorithm succeeds。

 and we're thinking of the number of vertices n as being big。

 So what we see here is a success probability of only one over n squared。And that kind of sucks。

So that's a good point。Let me address that。Problem。This is a low success probability。

So that's disappointing。So why are we talking about this algorithm or this analysis， Well。

 here's something I want to point out。Maybe this is not so good。

1 and n squared you're going to succeed， but this is still actually shockingly high for an oblivious algorithm。

 which honestly seems to be doing almost nothing。This is a nontrial， lower bound。

 a nontrial success probability， because don't forget。

 there's an exponential number of cuts in the graph。 So if you try to just pick a random cut I。e。

 you put every vertex 50，50 left or right。 you'd be doing way worse than this。

 you'd have a success probability of like one over2 to the n。 So this is way， way better than that。

 And the fact that it's an inverse polynomial means that using repeated trials。

 we can turn a success probability that's incredibly small into a failure probability that's incredibly small。

 So let me show you how to do that next。So we're going to boost the success probability of the contraction algorithm in if you think about it a totally obvious way。

 we're going to run it a bunch of times each one independently using a fresh batch of random coins。

 and we're just going to remember the smallest cuts that we ever see and that's what we're going to return the best of a bunch of repeated trials。

Now the question is， how many trials are we going to need before we're pretty confident that we actually find the in cut we're looking for？

To answer this question rigorously， let's define some suitable events。So by TI。I mean。

 the event that the IF trial succeeds， that is the I time that we run the contraction algorithm。

 it does output the desired min cut a comma B。For those of you that watched the part two of the probability review。

 I said a rule of thumb for dealing with independence is that you should maybe as a working hypothesis assume random variables are dependent unless they're explicitly constructed to be independent。

 so here's a case where we're just going to define the random variables to be independent。

 we're just going to say that we run the contraction algorithm over and over again with fresh randomness so they're going to be independent trials。

Now we know that the probability that a single trial fails could be pretty big。

 could be as big as1 minus1 over n squared， but here now with repeated trials。

 we're only in trouble if every single trial fails， if even one succeeds， then we find them in cut。

So a different way of saying that is we're interested in。The intersection of T1 and T2 and so on。



![](img/15a7f994fac88930473df1e5704e4d6b_17.png)

That's the event that every single trial fails。And now we use the fact that the trials are independent。

 so the probability that all of these things happen is just the product of the relevant probabilities。

So the product from I equal1 to capital N。Of the property of notti。

Recall that we argued that the success probability of a single trial was bounded below by1 over n squared。

 so the failure probability is bounded above by 1 minus1 over n squared。

So since that's true for each of the capital n terms。

 we get an overall failure probability for all capital N trials of one minus one over little n squared raised to the capital N。

All right so that's a little calculation， don't lose sight of why we're doing the calculation and we want to answer this question。

 how many trials do we need， how big does capital N need to be before we are confident that we get the answer that we want。

Well， to answer that question， I need a quick calculus fact。

Which is both very simple and very useful。 So for all real numbers， x。

We have the following inequality1 plus x is bounded above by e to the x。

So I'll just give you a quick proof by a picture。So first think about the line1 plus x。

 what does that cross through well that crosses through the points when x is minus1 y is 0 and when x is0 y is 1。

 and it's a line and so this looks like this blue line here。What does e to the x look like， Well。

 if you substitute x equals 0， it's going to be 1。 So in fact。

 two curves kiss each other at x equals 0， but exponentials grow really quickly。

 So as you jack up x to higher positive numbers， it becomes very， very steep。

And for x negative numbers， it stays non negative the whole way。

 so this sort of flattens out for the negative numbers。

So pictorially and I encourage you to type this into your own favorite graphing program。

 you see that E of the X bounds above everywhere， the line。

 the 1 plus x for those of you that want something more rigorous， there's a bunch of ways to do it。

 for example， you can look at the Taylor expansion of E to the X at the point0。What's point。

 the point is this allows us to do some very simple calculations on our previous upper bound and the failure probability by working with exponentials instead of working with these ugly one minus whatever is raised to the whatever term。

So let's combine our upper bound from the previous slide with the upper bound provided by the calculus fact。

 and to be concrete， let's substitute some particular number of capital n。

 so let's use little n squared trials or little n is the number of vertices of the graph。

In which case， the probability that every single trial fails to recover the cut a comma B is bounded above by E to the minus1 over n squared。

That's using the calculus fact applied with x equal to minus1 over n squared。

And then we inherit the capital n and the exponent， which we just instantiated to little n squared。

 so of course the n squares are going to cancel that is going to give us e to the minus1。

 also known as1 over E。So if you're willing to do little n squared trials。

 then our failure probability has gone from something very close to one to something which is more like say 30 some odd percent Now once you get to a constant success probability。

 it's very easy to boost it further by just doing a few more trials。

So if we just add a natural log factor， so instead of little n squared trials。

 we do little n squared times the natural log of little n。Now。

 the probability that everything fails is bounded above by the one over E that we had last time。

 but still with a residual natural log of n up top。 And this is now merely one over n。

 So I hope it's clear what happened。 We took a very simple。

 very elegant algorithm that almost always didn't do what we want。

 It almost always failed to output the cut Ap。 It did it with only probability one over little n squared。

 But one over little n squared is still big enough that we can boost it so that it almost always succeeds just by doing repeated trials。

 and the number of repeated trials that we need is the reciprocal of its original success probability boosted by a further logarithmic factor。

 So that transformed this almost always failing algorithm into an almost always succeeding algorithm。

 And that's a more general， less more general algorithmic technique。

 which is certainly worth remembering。Let me conclude with a couple comments about the running time。

This is probably the first algorithm of the course where we haven't obsessed over just what the running time is。

And I've said it's simple enough， it's not hard to figure out what it is。

 but it's actually not that impressive and that's why I haven't been obsessing over it。

 this is not almost linear， this is not a for free primitive as I've described it here。

So it's certainly a polynomial time algorithm， it running time is bounded above by some polynomial and N&M。

 so that's way better than the exponential time you' get from brute force search through all two of the impossible cuts。



![](img/15a7f994fac88930473df1e5704e4d6b_19.png)

But it is certainly the way I've described it， you've got to do n squared trials plus a log factor。

 which I'm not even going to bother writing down and also each trial。

 well at the very least you look at all the edges， so that's going to be another factor of M。

So this is a bigger polynomial than in any almost any of the algorithms that we're going to see Now I don't want to undersell this application of random sampling to computing cuts because I've just shown you the simplest。

 most elegant， most basic but therefore also the slowest implementation of using contractions to compute cuts there has been follow-up work with a lot of extra optimizations in particular doing stuff much more clever than just repeated trials。

 so basically using work that you did in previous trials to inform how you look for cuts in subsequent trials and you can shape large factors off of the running time so there are much better implementations of this randomized contraction algorithm than the one I'm showing you here。

 those are however outside of the course scope with this course。

