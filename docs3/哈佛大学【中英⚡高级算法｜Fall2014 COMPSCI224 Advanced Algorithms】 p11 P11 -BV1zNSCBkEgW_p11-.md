# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p11 P11 -BV1zNSCBkEgW_p11-

![](img/65174c14b8a71413e90b53acf02f9600_0.png)

So today I want to finish the。Finish the analysis of the dual fitting analysis of the greedy algorithm for set cover or weighted set cover。

嗯。And。I'll do one other very simple example for dual fitting， namely unweighted vertex cover。

 and so the next homework is going to be out tonight and you'll see a problem related to that。嗯。

To vertex cover。Then I want to talk a little bit about a limitation of。

Of this whole LP framework for approximation algorithms， Okay。

 so I'm going to introduce something called the Inity gap of an LP relaxation。

And then I'm going to talk about。嗯。More approximation algorithms。

 namely polynomial time approximation schemes。And that's where we don't just want。

 say a two or log n approximation， but we want a one plus epsilon approximation。

Where Epsilon is given in the beginning， okay？So how do we get for any fixed epsilon a polynomial time approximation。

 sometimes that's not possible。But， we'll see。An example where that is possible。Okay。

 so last time I defined the set cover problem or the weighted set cover problem。There are M sets。

 each one is a subset of the universe， the universe for us is one up to n。And a set S has a cost CS。

 and the goal， given an input， the goal is to find a sub collectionlection of the input sets。

Which covers the entire universe。 Okay， you must cover the universe and you want to do it as cheaply as possible。

 minimize the sum of costs。The sum of costs of sets you take。So the greedy algorithm， well。

 in the unweighted case， I think people have， if you've taken CS124。

 you've seen the greedy algorithm。For the unweighted cases you just keep taking the scent that covers the most new elements。

But when you have costs on the sets。Then you just slightly alter that。

YouYou pick the set as long as there's an uncovered element， you pick the set。

 which minimizes the ratio between its cost and the number of new elements you get to cover by picking it。

Okay。And。Theorem。嗯。Greedy。Is a login approximation。We'll even see it get something slightly better。

Just some history， I guess。呃。In the unweighted case。When all the costs are one。

 that's what I mean by unweighted。This greedy algorithm is due to Johnson。Back in '74， I think。

Whoscribing today？Okay， agree。And also， I believe independently。

 at least they didn't ciite each other。In discreteet math。75。And in the weighted case。

I don't know how to pronounce this name。And that was in '79。Okay。

We're going to take a primal dual look at analyzing this algorithm。Okay， so if you took CS124。

 we did analyze it there， we didn't talk about primal dual but。

YouYou can take a panel do a look and for one of the。

Homework problems that I'm going to release soon for vertex cover。

 it's going to be for weighted vertex cover。Even it's not just an issue of the analysis。

 even to come up with the algorithm， I think it helps you to have a primal dual look at the problem。

Okay。Okay， so。So the LP。Relaxation。For set cover， I said last time。In the primal。

We want to minimize the sum over s of CSs times xs， where xs is 1 if you take the set0 otherwise。

 subject for all I from1 to n。You need that the sum overs containing I of xs is at least one。

 and that for all S xs is at least zero。Yeah。No， so that's a very good point。 Yeah。

 I shouldn't have said V LP relaxation so。呃。And LP relaxation。 Okay， so if you。

So the set cover problem is actually this problem， but where you have the constraint that excess is in is either 01。

 and we relax that to just put a linear inequality。But you could imagine formulating it。

Another way and getting another LP relaxation of another formulation of the same problem。

And maybe using that LP relaxation would give you better results。So there's actually。

 I'm not going to get into it in this class， but there's actually a formal way of doing this。

 So given。Given some integer programming optimization problem where you have like integer constraints。

嗯。There's a systematic way of。Converting the LP of getting more and more refined LP relaxations。

 which get， which become better and better approximations to the integer constraints。

 So if you want to read more about this， you Google for like the Shirali Adams hierarchy。 Okay。

 so I'm not going to talk about that in class。But。There is yeah， and you can show that。

Eventually this thing becomes the integer program after。

 but then by that time you've blown up the LP to exponential size。So。So that's the primal。

And the duel。Is we want to maximize。The sum of egling from1 to n。Of y3。Subject to。

The constraint that for all sets S， the sum of elements in that set of YE is at most CS。

 and also y is a non negative。呃。Viectctor。Okay。So we'll do dual fitting。

I think I mentioned this at the end of the last time， but now I'm actually going to prove something。

So dual fitting。没有。Shou。How to maintain。Dual solution。As we build a prim all。Okay。So。

When we take a set S。Okay， we're going to set。X of S to1。In the primal。And two。For each。

Newly covered。Element E。We'll set。Y sub be to equal c sub S over。呃。The number of elements。

Nearly covered。By us。Okay。So this is what we're going to do。Remember the usual thing？

We know by weak duality but that any primal， if we have two feasible solutions。

 one for the primal one for the dual， we know the primal cost is at least the dual cost。

Where opt is sandwiched in between。嗯。So， but they have to be feasible。 So as it turns out。

 this y might not be feasible， but willll show that if you entry wise just scale down by log n。

 it will become feasible。Okay。So。Let me write down some observations， first of all。

The cost in the primal of x is the cost in the duall。Of why， and we've rigged it that way。

And we'll show。That。In fact， we'll show y over the n harmonic number。Is feasible for the duall。

And that's going to imply law and N approximation。And definitely， I should also say， I mean。

 I didn't say。