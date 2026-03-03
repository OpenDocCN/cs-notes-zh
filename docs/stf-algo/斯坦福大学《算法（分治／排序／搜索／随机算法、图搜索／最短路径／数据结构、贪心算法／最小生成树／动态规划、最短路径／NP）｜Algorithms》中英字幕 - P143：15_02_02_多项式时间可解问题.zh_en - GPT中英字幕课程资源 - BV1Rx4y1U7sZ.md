# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P143：15_02_02_多项式时间可解问题.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/e44eb6c8f1eadd971407a23f339d934c_0.png)

In this video we'll begin our study of our final topic， first of all。

 what are NP complete or computationally intractable problems， and second of all。

 what are some good strategies for approaching them algorithmically Let's begin by formally defining computational tractability via polynomial time solvelvability that is we're going define the complexity class P。

As you know from the past several weeks of hard work。

 the focus of these design and analysis of algorithms courses is to learn practical algorithms and relevant supporting theory for fundamental computational problems。

By now we have a very long list of such problems， sorting， searching， shortest paths。

 minimum spanning trees， sequence alignment， and so on。

But the sad fact is I've given you a quite biased sample thus far of computational problems and for many important computational problems。

 including ones you are likely to run into in your own projects， there is no known efficient。

 let alone blazingly fast algorithm for solving the problem。

And in as much as the focus of these courses is what you can do with algorithms rather than what you can't do。

 it would nevertheless be fraudulent， I think， to teach you about algorithms without discussing the specter of intractability that haunts the professional algorithm designer and the serious programmer。

In the same way your programmer toolbox should include lots of different design paradigms like dynamic programming greedy algorithms divide and conquer。

 lots of different data structures， hash tables， balance search trees and so on。

 that toolbox also should include the knowledge of computationally intractable that is NP completele problems。

 maybe even how to establish problems or NP complete and again this is because these problems are likely to show up in your own projects it is not uncommon that a graduate student at Stanford will come into my office。

 asking for some advice how to approach a problem that's come up in their own project from an algorithmic perspective。

 very often after they've sketched the problem for two minutes，5 minutes on my whiteboard。

 it's very easy to see that it is in fact an MP complete problem they should not seek out an efficient。

 exactly correct algorithm and instead they should resort to one of the strategies for dealing with MP complete problems that we'll be discussing later。

So in the next sequence of videos， my goal is to formalize the notion of computational intractability through the definition of NP completeness and also give you a couple of examples。

The relatively brief discussion that I'm going to give you of NP completeness is no substitute for a proper study of the topic。

 I encourage you to seek out a textbook or other free courses on the web to learn more。And indeed。

 NB Compness， I think， is a topic worth learning at least twice from multiple different perspectives。

 and indeed， those of you who have studied it before。

 I hope you find my treatment somewhat complementary to previous treatments that you might have seen。

 Indeed， Nmb Compness is really one of the most famous。

 important and influential exports from all of computer science to the broader scientific world。

And as so many different disciplines are getting increasingly computational and here I'm thinking about everything from the mathematical sciences。

 to the natural sciences， even to the social sciences。

 these fields have really no choice but to confront and learn about NP completeness since it genuinely governs what can be accomplished computationally and what cannot。

My perspective here will be unapologetically that of an algorithm designer and in particular after our discussion of MP completeness。

 the rest of this course is going to focus on algorithmic approaches to these problems。

 if you're confronted with an MP complete problem， what should you do about it？

So rather than starting out by formalizing computational intractability。

 it's a little simpler to begin by defining computational tractability。

That brings us to the Uber important definition of polynomial time solvability。

So the definition is a bit of a mouthful， but it's sort of exactly what you would think it would be。

 So a problem is polynomial time solvable naturally。

 if there's a polynomial time algorithm that solves it。

 that is there's an algorithm and there's a constant K so that if you feed in an input of length N to this algorithm。

 then it will correctly solve the problem， either it'll correctly answer yes or no。

 or it'll correctly output an optimal solution， whatever。

 correctly solves it in time Biggo of end to the K。Pretty much all the problems we've discussed。

 it's been kind of obvious what the input length was， it was for example。

 the number of vertices plus the number of edges， or it was the number of numbers that had to be sorted。

 etc cetera， for an abstract problem， you know just informally I would encourage you to think about the input length N as the number of keystrokes on a computer that would be required to describe that given instance。

And yes， it is true that strictly speaking to be polynomial time solvable。

 all you need is a running time of big web end of the K for some constant K。

 even if you get K equals 10000， that is enough to meet the demands of this definition。 Of course。

 for concrete problems， you're going to see small values of K。 In this course， K has usually been 1。

2 or 3。So a quick comment for those of you that are wondering about randomized algorithms and of course we saw some cool examples of randomized algorithms back in part1。

 so to keep the discussion simple when we discuss computational intractability。

 let's just think only about deterministic algorithms， but at the same time。

 don't worry really all of the qualitative conclusions we're going to reach are believed to hold equally well for randomized algorithms in particular。

 we don't think that there are problems that deterministic algorithms require exponential time and yet randomization allows you to magically get polynomial time and there's even some mathematical evidence suggesting that that is the case。

So that brings us to the definition of the complexity class capital P capital P is just defined as the set of all polynomial time solvable problems。

 the set of all problems that admit a polynomial time algorithm solving it。

For those of you who have heard of the P versus NP question， this is the same P。

Throughout these courses， we've exhibited many examples of problems in P， right。

 that's really been sort of the whole point of the course， sequence alignment， minimum cut， sorting。

 minimum spanning tree， shortest paths， and so on。There are two exceptions。

 one we talked about explicitly at the time， which is when we discussed shortest paths in graphs with negative edge costs。

 and we stated that if you have negative cost cycles and you wanted shortest paths that are simple that do not have any cycles in them。

 then that turns out to be an MP complete problem for those of you that know about reductions it's an easier reduction from the Hamiltonian path problem。

So we did not give a polynomial time algorithm for that version of the shortest path problem。

 we just punted on it。And the second example is a really subtle one， so believe it or not。

 we did not actually give a polynomial time algorithm for thenapsack problem。

So this requires an explanation because at the time in our dynamic programming algorithm。

 I'll bet it felt like it was a polynomial time algorithm。

 so let's review what its running time was so when the Napsack problem the input is n items that have values and sizes and also you're given this Napsack capacity。

 which is a positive integer capital W， and our table our twodisal array had theta of n times capital W subproblems we spent constant time filling any gentry。

 so the running time of our dynamic programming algorithm was theta of n， the number of items。

 times capital W the NApsack capacity。What， on the other hand。

 is the length of an instance of Napsack。 Well， as we just said。

 the input to Napssack is 2 n plus1 numbers， the n sizes， the n values and the Napssack capacity。

 and naturally to write down any one of these numbers。

 you only need log of the magnitude of the number right So if you have an nger K and you want to write it in binary。

 that's log based 2 of K bits。 if you want to write it down in base 10 digits is going to be log based 10 of k。

 which is the same up to a constant factor。 So the point is the input length is going to be proportional to n and proportional to log of the magnitudes of the numbers。

 in particular， log of capital W。So here's another way to see why the dynamic programming algorithm is exponential in terms of the input length。

 Let me use an analogy。 Suppose you were solving some problem of a graph cuts。

 So remember the number of cuts in a graph is exponential in the number of vertices。

 It's roughly two to the end for n vertices。 So that means if you're doing brute for search and I add just one more vertex to the graph。

 it doubles the running time of your algorithm。 That's exponential growth。

 But actually the same thing is going on in the Napsack problem with a dynamic programming algorithm。

 supposeupp we write everything in base 10。 and I just add one extra0 to thenapsack capacity。

 I multiply it by 10。 Well， then the number of subproblems you have to solve goes up by 10。 So again。

 I just added one digit， one keystroke to the input。

 And yet your running time got multiplied by a constant factor。 So it is， again。

 exponential growth with respect to the encoding length of the input。

Now it's no accident that we failed to get a poll on time algorithm for the Napsack problem because that is。

 in fact， an NP complete problem， and again， we'll explain what NP complete means shortly。

So that's the mathematical definition of the complexity class P。

 but more important than the math is the interpretation that is how should you think about the class P。

 how should you think about polynomial time solvelvability to the practicing algorithm designer。

 the practicing programmer， membership in P， polynomial time solvelvability can be thought of as a rough litmus test for computational tractability。

Now， the identification of algorithms that run in big O of end to the K time for some constant K and practical。

 computationally efficient algorithms is imperfect。 There are of course， algorithms。

 which in principle run in polynomial time， but are too slow to be useful in practice。 Conversely。

 there are algorithms which are not polynomial time， but are useful in practice。

 You already coded one up when you did the dynamic programming solution to Napsack and willll see several more examples in future lectures。

And more generally， anyone who has the guts to write down a precise mathematical definition like this complexity class P needs to be ready for the inevitability that the definition will accommodate a few edge cases that you wish it didn't and that it will exclude a few as edge cases that you wish it didn't。

This is an inevitable friction between the binary nature of mathematical properties and the fuzziness of reality。

These edge cases are absolutely no excuse to ignore or dismiss a mathematical definition like this one Quite the contrary。

 the friction makes it that much more astonishing that you could write down a clean mathematical definition something that either is satisfied or not satisfied by every single computational problem and have it served as such a useful guide to classify problems into thetractable in practice problems and the intractable in practice problems。

 and we now have 40 years of experience that indicates this definition has been unreasonably effective in just that kind of classification。

Generally speaking， computational problems in P can be well solved using off the shelf solutions。

 as we've seen in the many examples in this class。Problems that are believed not to be in P generally require significant computational resources。

 significant human resources， and a lot of domain expertise to solve in practice。

So we've mentioned in passing a couple of problems that are believed to not be polynomial time solvable。

 But let me pause here and tell you about a more famous one， the traveling salesman problem。

The traveling salesman problem remarkably just doesn't sound that different than the minimum banning tree problem。

 a problem for which we now know a litany of greedy algorithms are run in near linear time。

 So the input is an undirected graph。 And let's go ahead and assume that it's a complete graph。

 So there's an edge between every pair of vertices， Every edge has a cost。

 and the problem is nontrial。 Even if every edge cost is just either one or two。

Let me draw an example in green with four vertices。

The responsibility of an algorithm for the TSP problem is to output a tour that is a cycle that visits every single vertex exactly once。

 and amongst all tours， which you can think of as a permutation of the vertices。

 the order in which you visit them， you want the one that minimizes the sum of the edge costs。

So for example， in the green graph that I've drawn， the minimum cost tour has total cost 13。

So the TSP problem is simple enough to state it's clear you could solve it by brutefor search in roughly n factorial time just by trying all permutations of the vertices。

 but you know we've seen many， many examples in this class where you can do better than brutefor search and the TSP problem。

 people have been studying seriously from a computational perspective since at least the 1950s。

 including many huge names and optimization people like George Danzig。

 So despite the interest over 60 years there is to date no known polynomial time algorithm that solves the traveling salesman problem。

In fact， way back in 1965， Jack Edmonds in a remarkable paper called Pas， Trees and Flowers。

 conjectured that no polynomial time algorithm exists for the traveling salesman problem。



![](img/e44eb6c8f1eadd971407a23f339d934c_2.png)

This conjecture remains unresolved to this day almost 50 years later， as we'll see。

 this is equivalent to the conjecture that P is not equal to NPp。

 So how would you formalize a proof of this conjecture。

 How would you amass evidence that this conjecture holds in the absence of a proof。

 Those are the topics of the upcoming videos。