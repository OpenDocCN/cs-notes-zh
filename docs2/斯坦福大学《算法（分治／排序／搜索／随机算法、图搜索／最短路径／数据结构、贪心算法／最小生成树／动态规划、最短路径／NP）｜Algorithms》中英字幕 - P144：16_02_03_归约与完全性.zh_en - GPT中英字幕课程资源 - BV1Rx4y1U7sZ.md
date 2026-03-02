# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P144：16_02_03_归约与完全性.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/b4b104c725f763d0b45d54c92878b242_0.png)

How do we amass evidence of computational intractability of something like the traveling salesman problem。

 The key idea is through the formalism of completeness。

 which in turn depends on the idea of a reduction between two problems。

We left off last video with Edmund's Prescient conjecture from 1965 in his paper Pa。

 treesrees and flowers。 when， while pondering the traveling salesman problem。

 he conjectures that there is no polynomial time algorithm for it。That conjecture is equivalent。

 as we'll see to a conjecture called P not equal to NPp， and this is not resolved。

 This remains to this day one of the most fundamental open problems in all of mathematics。

It's important that research and algorithms does not grind to a halt just because we have this open and presumably extremely difficult P versus NP problem that we don't yet understand。

 we still want guidance about which problems are easy and which problems are hard。

 so a pretty great idea for giving us such guidance while at the same time evading actually answering the P versus NP problem is to show that problems are difficult in a relative sense。

 a mass evidence of intractability by showing that a problem is at least as hard as many other computational problems。

To make this idea of relative difficulty precise， we need to say what we mean that one problem is as hard as another。

 The language for that is a reduction from one problem to another。

We say that a computational problem， say pi 1 reduces to another one， pi2。

 if all you need to solve pi 1 efficiently is an efficient algorithm for pi 2。

 that is if I gave to you on a silver platter， a polynomial time algorithm for the problem pi 2。

 then using that as a subroutine， you could build a polynomial time algorithm for pi 1。

So we'll see some concrete examples in just a sec。 But let me just mention I being slightly informal with this definition。

 you'll see something a little bit more formal。 If you look at a textbook or take a class specifically on this topic。

 But this is how you should think about reductions。

 All you need to solve pi 1 is someone handing you an efficient subroutine for pi2。

 That is the algorithmic way of thinking about reductions。Indeed。

 by virtue of being immersed in algorithms over the past many weeks。

 we have examples of reductions the next quiz is going to ask you to recall some of them。

So the correct answer is all of the above。 A， B and C are all legitimate reductions from one computational problem to another。

 So， for example， answer A， this is something we discussed back in part one of the course when we first motivated linear time。

 median algorithms。 At that point， we were arguing that for a median algorithm to be interesting。

 It better be faster than n log N time。 That's why we're shooting for linear time。

 The reason being that one perfectly correct algorithm for computing a median is you take the input array。

 you sort it。 for example， using merge sort and n log n time。 and you return the middle element。

 That's going to be the median。The second answer B。

 so this is something we mentioned in passing in the naive implementation of Ksco's algorithm where we wanted to check cycles when we were thinking about adding a new edge。

 and we observed that one way to check if a graph has a cycle is you just run depth first search on that graph if there's a cycle you'll detect it by exploring an edge which points backward to a vertex that you're still in the middle of exploring。

The third example is maybe more interesting in the sense that we invoke the provided subroutine more than once when we first introduced the all pairs shortest path problem。

 we observed that one solution， and in certain cases is actually a very good solution is to just invoke a single source shortest path subroutine like Dkes' algorithm or the Bum and Ford algorithm。

 N times once for each choice of the source。 But again。

 it's still a reduction given an efficient algorithm。

 a polynomial time algorithm for the single source shortest path problem。

 you just run at n times that gives you a polynomial time algorithm for the all pairs shortest path problem。

In fact， seasoned algorithm designers and seasoned programmers are always looking for opportunities to employ reductions。

 So when someone describes you a computational problem。

 the very first thing you should try to think through is。

Is this a problem I already know how to solve just merely in disguise。

 So maybe if you have to make a sequence of decisions。

 maybe you can phrase it as as shortest path problem。

 a problem that you already know excellent solutions to。 And if that fails。

 If the computational problem you're confronted with isn't literally the same as when you already know how to solve。

 maybe by invoking known primitives， known algorithms a small number of times。

 that's sufficient to solve this new computational problem that you're confronted with。

 So all of these are what I think of as honorable uses of reduction。

 So it's somehow the light side of the force， it spreads the frontier of tractability to cover the things we can do with algorithms wider and wider。

 Now， for NP completeness for establishing computational intractability。

 we have to turn this world on its head。 This relies on a perverse use of reductions。

 which I'll explain next。So I suppose that the problem pi 1 reduces to pi2 in the sense that all you need to solve pi 1 in polynomial time is a polynomial time algorithm for pi2。

 That's the only missing piece。 Now， as algorithm designers。

 you're probably thinking about the happy case where we have a polynomial time algorithm for pi 2 sitting on the shelf。

 We have something like dixtrous algorithm or bellman's forward algorithm and we take it off the shelf and we use it combined with this reduction to solve pi 1。

 But let's think about the contrapoitive of what it means when one problem reduces to another。

 And now let's think about the case where we don't actually believe that it's possible to solve pi 1 and polynomial time。

 Well， if we don't think it's possible to solve pi1 efficiently and pi 1 reduces to merely computing pi 2 efficiently。

 Well， then we certainly can't believe that it's possible to compute pi2 efficiently either。

 That is if pi 1 reduces to pi 2。 and it just so happens that pi 1 cannot be solved。

In polynomial time， then pi 2 cannot be solved in polynomial time either。

So this is the perverse use of a reduction that I mentioned earlier。

 This is the dark side of the force， rather than using a reduction to enlarge the frontier of tractability from pi2 to include pi 1 also。

 we're spreading the frontier of intractability from pi 1 to pi 2。

So this then is what we mean formally when we say that one problem is at least as hard as another。

 if pi 1 reduces to pi 2， what does that say that says pi 2 allows you to solve pi 1。

 maybe it lets you do other stuff as well， so therefore pi2 is at least as hard as pi 1。

So we now have the vocabulary to say that one problem is at least as hard as another one。

 And let's remember what our plan was。 Our plan was to amass evidence of the intractability of the traveling salesman problem by saying it's at least as hard as lots of other stuff。

 So to pass from as hard as a single problem to a big set of problems。

 we're going to talk about the notion of completeness。Formerally， consider some set C of problems。

 And it's gonna be tricky to get the right set of problems。

 We'll discuss that in detail in the next video。 But for now， just let C be any old set of problems。

We call it computational problem pi complete for C。

 we call it C complete if it's at least as hard as everything in C。

 if everything in C reduces to pi Oh， and also this problem pi， it should be in this class itself。

So the second constraint here is the more important one。

 It's the one that fits more directly into our narrative。

 Remember we wanted to have vocabulary for saying one problem is as hard as a whole bunch of other stuff。

 C is a bunch of other stuff。 So pi is at least as hard as everything in C。

 that is everything in C reduces to pi。 One nice reason to have this first constraint also to assume that the problem pi is a member of C is that gives the following nice interpretation。

We can think of this problem pi as being a hardest problem in the set C， it's in C。

 and it's at least as hard as everything else in the class。

So we're starting to see a confluence between our strategic plan amassing evidence for the intractability of TSP by arguing it's as hard as a bunch of other stuff and the mathematical formalism。

 right this notion of completeness gives us a language to say that a problem is at least as hard as a bunch of other stuff So how should we define all of this other stuff。

 that is what is a suitable choice for the class C。Well， we'd like to present the strongest evidence。

 the most compelling case possible of the traveling salesman problem being intractable。

 So that says we should strive for the biggest set C that we can find。

 The more stuff this problem is as hard as the greater the evidence of its intractability。

 So we want to prove it complete for a really big set C。Well。

 why not be ambitious and reach for the stars， Why don't we just show that the traveling salesman problem is the hardest problem in existence。

 It's C complete， even if we take the set C to be all computational problems。Well。

 this is a good starting point， but it turns out this is too ambitious。

 We're not going to be able to prove this fact。 There are indeed computational problems out there that are certainly strictly harder。

 Str more difficult to solve than the traveling salesman problem。1。

 I hope you've heard of is the halting problem。So in the halting problem， it's very simple。

 you're given as input， some code， say a program written in C， and you're given an input。

 and the responsibility of the algorithm is to decide whether or not the provided program will halt eventually when you run it with the provided input。

Perhaps the obvious approach to the halting problem is to just simulate the provided program in an interpreter in effect on the supplied input。

 But here's the problem。 Suppose you've been simulating the provided program on the provided input。

 And you've been running for， say，10 hours， Maybe you suspect the thing is in an infinite loop and it's never going to halt。

 But how do you know， Maybe if you ran it for one more hour， it would halt。

 What if you've been running it for 10 years， Maybe now you're pretty sure it's in an infinite loop and never going to halt。

 But how do you know， Maybe it's going to halt tomorrow morrow。

Problem of not knowing when you're done is an issue not just with the naive simulation approach to the problem。

 but with any possible approach to this computational problem。 Indeed。

 Tr proved in his landmark 1936 paper that there is no algorithm。 however slow。

 guaranteed to always correctly solve the halting problem。So this is one of those theorems。

 which is simultaneously， at least in my opinion， very deep。

 But also the proof is just like four lines。 You prove it by contradiction。

 You assume that an algorithm for the halting problem does exist。

 And then using the code for that program。 you construct a program that， on the one hand。

 can't halt And on the other hand， can't not halt。 obviously a contradiction。

 So the purported algorithm for solving the halting problem can exist。

 So this is the kind of argument I find just totally baffling。

 I like to recall von Neumman's quote that there's some things in mathematics that you don't ever understand you just get used to。

 And this kind of diagonalization argument inspired by cant towardss original argument that there's an uncountable number of real numbers。

 I think falls squarely in that category。

![](img/b4b104c725f763d0b45d54c92878b242_2.png)

Anyways， the point is that the traveling salesman problem no longer looks quite that bad。

 And we now realize that our original thought to prove that the TSP problem is at least as hard as every other problem is a little misguided as a little too ambitious。

 So it's certainly not at least as hard as the halting problem。

 The halting problem is what's called undecidable， There's no algorithm for it whatsoever。

 whatever time bound I might give you。 whereas the TSP problem by contrast。

 if I give you a big enough time bound， roughly n factorial for in vertices。

 You can solve the problem， namely using our favorite punching bag brute force search。

 You can just try every one of the finite possibilities。 and pick the best one。

But the high level idea at the top of this slide that is proving the traveling salesman problem complete for a big class of problems is still a good one。

 We just have to refine our understanding of the suitable choice of the class C。 in particular。

 by virtue of being solvable by brute force search。

 there are certain problems that we cannot prove the T SP is at least as hard as。

 but maybe we can prove that amongst all problems which can be solved using brute force search。

 amongst such problems， T SP is the hardest one。Now， to execute this idea， we'll， of course。

 have to define what it means for a problem to be brute force solvable that will motivate the complexity class NP P the subject of the next video。

