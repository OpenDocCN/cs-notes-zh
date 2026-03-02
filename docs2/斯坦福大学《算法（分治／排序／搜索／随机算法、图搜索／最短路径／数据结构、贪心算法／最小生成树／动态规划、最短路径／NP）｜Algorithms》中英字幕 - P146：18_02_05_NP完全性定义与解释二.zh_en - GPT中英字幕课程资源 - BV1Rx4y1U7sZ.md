# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P146：18_02_05_NP完全性定义与解释二.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

So for those of you out there that fancy yourself computer scientists。

 I hope you feel some pride seeing this definition， I mean。

 how cool is it that our discipline came up with such a great concept of an NP complete problem。

 the fact that there's a universal problem that simultaneously encodes all computational problems in which you can efficiently recognize a solution。



![](img/b60fe6765547965a63cd414423868b9b_1.png)

There remains， however， a niggling issue。 in general。

 when you're confronted with a mathematical definition。

 like the definition of N completeness that I just gave you， you should demand two things。

 The first thing you should demand is explanation of why you should care。

 That is if the definition is met is satisfied。 What are the interesting consequences。

 I'd like to think I've given you a very satisfying answer to that question for the definition of MP completeness。

 I've argued that if a problem is NP complete， then that's strong evidence of computational intractability。

 In the sense that a polynomial time algorithm for this N complete problem。

 If one hypothetically existed， that would automatically solved efficiently。

 thousands of fundamental computational problems。 Anything for which you can efficiently recognize a solution。

But the second thing you should demand from somebody who offers you a mathematical definition is examples。

 Do things that I care about actually meet this definition and， and be completeness。

 I haven't shown you anything。 And indeed， when you look at this interpretation。

 a single problem that simultaneously is encoding all problems with efficiently recognizable solutions。

 You might well wonder， could such objects ever exist。

And the reason the theory of N completeness is so powerful and over the past 40 years has been exported from computer science to all kinds of other disciplines is that that question also has an incredibly satisfying answer。

 turns out tons of problems are not merely in N。 They don't merely have efficiently recognizable solutions。

 Thouand and thousands of problems are， in fact， N complete as hard as any other problems in NP。

So both the definition of MP completeness and the fact that amazingly there exist NP complete problems。

 that's due to independently Steve Cook and Leon Levin。

So Cook and Levin came up with their largely similar theories independently。

 Cook was at that time as he is today at the University of Toronto。

 Leonna Levin was behind the ironron Curtains， he was working in the Soviet Union。

 so it took a while before his results were known in the West these days Levin is a professor at Boston University。

Both Cook and Levin proved not just the basic existence result。

 but also gave some hints that problems that people really care about are also going to be and be completele。

 for example， some constraint satisfaction problems like3SAP。But the vast scope of NP completeness。

 the sheer breadth of problems that would eventually be proven NP complete was first made clear in a 1972 paper by Richard Kp。

 In that paper， he showed 21 different problems are NP complete。

 including the traveling salesman problem and various problems that many different communities had been stuck on for decades。

 It now became clear that NP completeness was the fundamental obstacle。

 preventing progress in efficient algorithms across many， many different domains。

So another thing that's amazing about NP completeness and a big reason for why it's been so successfully exported from。

 first of all， theoretical computer science to computer science more broadly and then beyond into engineering and the other sciences。

 is that it's quite easy to stand on the shoulders of these giants and prove that new problems。

 problems that you care about are also NP complete。

So imagine that there's some computational problem pie that you really care about this is just crucial to the project that you're working on and you're stuck。

 you've been trying for weeks to solve it throwing everything in your toolbox at it。

 you tried greedy algorithms， divide and conquer， dynamic programming， randomization。

 you've thrown every data structure in the book at it， hash tables， he search trees， nothing works。

 you can't come up with an efficient algorithm。😡，At that point you should contemplate the possibility that the issue is not your own lack of cleverness or ingenuity。

 the issue is not having few too few tools in your program and toolbox。

 perhaps the issue is intractability of the computational problem that you're trying to solve。

So when you reach this point of exasperation， it's time to consider applying the following two step recipe for establishing that the problem pi is NPP complete。

Of course， the problem doesn't go away just because you prove it's NP complete。

 but you should approach it using a different algorithmic strategy and we'll discuss some of the most popular set strategies of approaching NP complete problems in the rest of this course。

So let me state the two step recipe just at a very high level。



![](img/b60fe6765547965a63cd414423868b9b_3.png)

So the first thing you need to do is settle on a suitable choice of an NP complete problem pi prime。

 The second thing you need to do is you need to show that pi prime reduces to the problem you care about pi that shows that your problem is at least as hard as this NP complete problem in the sense of the NP complete problem reduces to yours and therefore your problem assuming it's an NP is NP complete as well。

So clearly， the devil is in the details of successfully executing this two step recipe。

 and you might well be wondering， well， how on earth do I know whichmp complete problem pi prime I should use？

 And then secondly， how am I going to come up with this reduction from thismp complete problem pi prime to my own problem pi。

 But don't be intimidated by either of these two steps， with just a little bit of practice。

 you can actually get quite good at both of the steps and execute this recipe successfully in a lot of different cases。

So one thing that should make the first step less intimidating is there are some excellent lists of Np complete problems。

 In particular， simple ones that tend to be useful in devising your own reductions。

 And the canonical such list is a book by Gary and Johnson called Computers and Intractability。

 It's from 1979。 but it's so incredibly useful。 I don't think I know of another computer science book that's more than 30 years old。

 which is as useful as this one。So there still remains the question of how do you actually come up with one of these reductions from a known NP complete problem pi prime to the problem you actually care about pi。

 But don't be intimidated by this step either。 So， first of all， as an algorithm person。

 you should be thinking about reductions all the time anyway。

 This should be a very natural mode of thought for you。 For example。

 when we first started talking about all pairs shortest path。

 we click quickly observed that it reduces to the single source shortest path problem。

 So that mentality of solving one problem using another is equally useful in the design of MP completeness reductions。

And also， there's a lot of resources available to gain facility with MP completeness reductions。

 You can look in the various algorithms textbooks。 generally， they have lots of examples。

 The Gary and Johnson book is a good one。 There's some online courses that study MP completeness in more depth。

 Those resources will give you a lot of examples of MP completeness reductions It'll offer some tips and how to come up with them yourself and most importantly。

 practice will make perfect。So as strongly encourage you to take advantage of those resources。

 I think you'll be pleased to have NP completeness as part of your toolbox。

 certainly nobody wins if you spend weeks or months of your life inadvertently trying to prove that P equals NP。

