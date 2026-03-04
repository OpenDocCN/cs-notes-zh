# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P29：29_07_05_NP完全性.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/3672022481fa46e90a4bc6e5608aaa3e_0.png)

Next， we're going to talk about another very important aspect of this theory called NP completeness。

So this starts with a very simple definition， so any search problem。

 a problem in NP is said to be NP complete if all problems in NP polynomial time reduced to that problem。

This seems like a very， very strong condition， but actually it's pretty natural as we're going to see in just a second。

And the reason this class of problems is important is that there's a theorem that was proved independently by Cook and Levin in the early 70s。

 really about the same time as CAp was doing his reductions for practical problems that says that SAT is NP complete。

Now this is a result with amazing ramifications and in a course in theoretical computer science。

 you could learn this proof really in an hour and I don't have the time to go through it in detail。

 but I can explain the basic idea extremely briefly。

And the idea is to take the idea of a nondeterministic Tring machine。

 which is like a specification of an algorithm of a search problem so you take your problem and you formulate it as a nondeterministic Tring machine and that's true。

 any search problem you can do that that's kind of the formal definition of a search problem and what the proof does is take that notation。

 which is a particular notation you can think of it as a mathematical notation or states and arrows the way we do it with label transitions and just convert that notation into satAT notation and they're both kind of discrete formalism is not really that long or difficult but that's what the proof does is get to the point where given any search problem you can make a nondeterministic Tring machine。

And then you can convert that into an instance of sat。

Which means that if you have an efficient solution for SAAT。

 then you have an efficient simulation of that nondeterministic Tring machine。

 which gives an efficient solution to any problem in NP。

So nondemintri goes to that instance and that that's the reduction and again， in very。

 very much oversimplifying this proof， it's really an amazing fundamental result。

So the corollary to this means that SAAT is tractable， if and only if p is equal to NPp。

 of course if p equals NPp， it's tractable， but also if SAAT is tractable。

 then all the problems in NPp are tractable that means P equals NPp。

So another way to do it is to say， you know that assumption that that's intractable is very much the same as assuming that P is not equal to NPp。

And in terms of the practical problems， here's what this theorem says。

 it says that all those problems of carbs are going to reduce to satAT。

All problems of an NP reduce to SAAT， but then SAAT reduces to all of them。

 so what this means is that all the problems are NP complete， not just SAAT。

If we can solve any one of these problems， we can solve all the problems in NP that's a much。

 much stronger statement about the difficulty of solving these problems they're all NP complete and all of those thousands and thousands of problems that are proved that are formulated in scientific papers every year our NP complete in the sense that if you can find an algorithm for any one of them you have an efficient algorithm for all of them that gives us much more confidence about asserting the difficulty of finding guaranteed polynom times algorithm to solve them than just mere reduction。

So NP completeness is adds to our universes in the following way， if P is not equal to NP。

 then there's some intractable problems， if it's equal， there's no such thing。

 nondeterminism would help， if it's equal amateur is no help。

 and again these are the different formulations that we looked at if P equals NP。

 it's more no harder to find an answer than to just guess it， and if P equals NP。

 then there's guaranteed polynomial time algorithms for all the problems in NP， if it's not equal。

 then you can prove a problem to be intractable by doing a reduction from an NP complete problem。

So the situation is a little bit more like this。And that again。

 these are possibilities just based on the basic definitions that we have。

 but still there's no progress on knowing which these two things are true despite the fact that many people have been working on it for decades。

 so just a quick summary we have the class of all search problems that's NP。

 the ones we can solve in polynomial time， those are P。

 and then we have the NP complete problems which you can think of as the hardest problems in NP。

 and then the idea of intractability， which if P's not equal to NP。

 those are the ones that are not NP。And we have thousands and thousands of problems that are NP complete。

 and our idea about this theory is to use it as a guide when faced with a practical situation。

If you have an MP complete problem， you need to know that finding efficient algorithm。

 guaranteed poly time algorithm for that problem would be a stunning scientific breakthrough。

 it would be a proof that P is equal to NP。And you should know that because you definitely will confront some NP complete problems in your career。

 so it's pretty safe to assume that P is not equal to NP and that that NP complete problems intractable and so what you want to be able to do at a minimum is identify these situations and proceed accordingly。

 and we'll talk about ways of doing that in the next segment。In the meantime， if you're in Princeton。

 if you take a look at the west wall of the CS building。

 you can see some indentations in the pattern of bricks。

 and this is made for really students of this course if you take those indications and treat them as binary numbers。

 convert them to ASI， then you get the P equals NPP question。

Now when this building was built in the late 80s， a lot of people said it was buildings going to last a long time。

 why would you put a question such important question that so many people were working on into the brick well actually now a couple of decades later。

 it's more important symbol than ever of computer science and of course with just investing in a few bricks we could change the equals to a no equals in the end or the question mark to an exclamation point without much work。



![](img/3672022481fa46e90a4bc6e5608aaa3e_2.png)

![](img/3672022481fa46e90a4bc6e5608aaa3e_3.png)