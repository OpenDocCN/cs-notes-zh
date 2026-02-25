# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P57：1 - Spring 2023 Exam-Level 10 Problem 2.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

可南家。If one Russia。

![](img/6544bcd1e79a3202e17b8d35d886237a_1.png)

2022 Ex prep 10 walkthrough and I'm Sherry in this part I'll be going over question two conceptual short paths。

In this problem， we're answering a few questions about shortest pass on a general weighted undirected。

So let's jump in。Part A asks us if all the weights are equal and positive。

 then breath for research we'll find the shortest path。And the answer to this is true。

And this is because BFS always finds a path with the least edges。

 and so if all the weights are equal， we can kind of just think of it as being an unweighted graph and so the path with the least edges is all so the shortest。

Part B asks us if distinct weights means distinct shortest paths and the answer to this is false and we can see a counter example here where I have this graph and we can see that we can either go AC or ABC and those they're both the shortest paths because they have length5。

Part of C asks us if we add a constant K to every edge if the shortest pass will change。

And the answer to this is。Also false and we can see that there's a counter example of this pretty clearly if we start off with this graph ABC。

 we can see that the shortest path is through B， but if we look at this new graph where we just added one to every edge。

 the shortest path is just directly to C now。The general idea is that by adding a constant to every edge。

 we penalize the paths with more edges。And part D is asking us something similar but not exactly the same and it's saying if we multiply all the edge weights by a constant positive integer k will the shortest path change and the answer is that this is true。

 the shortest path will not change and。Just as like a little proof sketch of this。

 if we consider some path p and let's say this is the optimal shortest path and then let's say there's some other path p which is not the optimal path and so obviously。

P star is going to be less than P originally， and so we have this left side hand side of the inequality and if we multiply all the edges by k。

 the new optimal path is going to have weight KP star。

 which is going to be less than KP for any other nonop path P。So it's still the shortest path。

That's it for this problem and here's my weekly exam tip for graph problems。

 you can either prove something is true with a really rough proof sketch like I did in A and D。

 or you can also if you want to prove something false。

 you want to use counter examplesamples like I did in B and C。

The most important thing is to draw out simple examples like these three node graphs that I did here and good luck in the rest of 61b。



![](img/6544bcd1e79a3202e17b8d35d886237a_3.png)