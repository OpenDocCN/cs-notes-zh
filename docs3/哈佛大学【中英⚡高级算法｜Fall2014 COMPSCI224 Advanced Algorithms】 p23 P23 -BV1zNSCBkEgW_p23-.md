# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p23 P23 -BV1zNSCBkEgW_p23-

![](img/3b5d9b023fcf1adf6a2c28c78f1a6387_0.png)

Okay， so let's get started， you're scraming today， right， is that right， great。嗯。So yeah。

 at the end of last lecture， there some there just maybe like a minute or two minutes more I wanted to say main cost max flow but ran out of time。

 so I just put that at the end of the notes at the end of the lecture notes you can go look at that。

🤢，Today I want to。Well， we only have three lectures left， I guess， including today。嗯。

So I want to show you some more topics today， I'm going to talk to you about another way of dealing with。

Kind of NP hard problem。 So earlier in the course。We saw that one way was approximation algorithms。

 right if you can't solve the problem in polytime， then maybe probablyvably get a two approximation or a log n approximation or something in polytime。

Okay， so another way of dealing with it is actually solving the problem in exponential time。 Okay。

 but then you want to make that exponential as small as possible。So。

I'll put fast in quotes today oh it's today。We'll do。Fast in quotes。Exponential timing algorithms。

Okay。And we'll look at。Three ways of doing this， so exponential divide and conquer。

So we're going to look at， for example， the traveling salesman problem。We're going to do。

Pruned bru forest。And also randomization。We'll see how to apply these things to。OhLike three sat。

And we'll also see。Inclusion exclusion。Also。Kind of a similar thing。 they're very。

 I think they're equivalent to each other is a Mobiious， fast Mobiious transform。An inversion。

And for this， we'll look at key coloring。Okay， so these are。

A few different ways to speed up exponential time algorithms。Or in some cases。

 we're not going actually speed things up。 We're going to。嗯。You know， lower the space complexity。

So there are some ways to get， say， exponential time， two to the end time。

 but then the natural implementation would also have two to the end space。

 but we'll see that sometimes we can get the two to the end time while having poly end space。

 things like that。So let's look at， let's just go through these。These techniques。

 is there any question about？Well， yes， I didn't see much its。So the first thing。

Exponential divide and conquer。Okay， so。The example I want to give you。Is TSP？Okay， so the input。Is。

A set P of points。And a distance function。Di。Which maps pairs of points to。诶。Not negative numbers。

And let's assume it's a proper distance function， so this is a metric。

 so it satisfies triangle inality and it's a metric。

 Diss are zero only if the two points are the same。And we're also given。呃。Two identified points。ST。

 which are in P。And the goal。Is to。Visit every vertex exactly once。Start at S and at T。

 visit every other vertex exactly once， and the total length of your tour should be as small as possible。

Have people here seen traveling salesmen？Find。ST path。Visiting。Each vertex。Once。And。Minimize。

Total length of path。So。For the rest of the lecture。If I say o star of F of N。That means。Oh。

 of Pol and。Times F of event。 And okay， so。I'm not really going to care too much about polyan factors。

嗯嗯。So what do we know about TSP？Okay， so what's the most straightforward algorithm？

Let's look at both the time and space。And what are you。Don't think， I mean， just。Yeah， tri path。

 so try basically all the orderings of the intermediate vertices。

And therere n minus two factorial of them。And each one。

 you can sum up the length of the path it takes about end time。So it's O starve and factorial。

And the space。Is all in。Okay， so this is brute force。Okay， two。嗯。

People might probably have seen something else， so something to trade off the space for the time。

So get time， which is much less than n factorial。But you're allowed to use exponential space。Yeah。

 yeah， so dynamic programming。 yeah， so your time will be O star of 2 to the end。And your space。

We'll also be O star of 2 to the n。And this is dynamic programming。

 and the point is you can define a function。嗯。Let's say。So you can say let F of。嗯。X， S。Be the length。

Of the。Shortest。X T path。Visiting。Every vertex。Every point， I guess， every point。In S。Once。

Wherere here S is a subset of the points。And what you want。Is F of S comma， all the points， well。

 you don't need S or T。Right。So the number of states of your Dic program。Are， well。

How many current so this is really like yeah， so you're currently at vertex S。

 you're trying to get to T。And you still need to visit everything in this set。That's what this means。

Okay， so there are so this is an arbitrary subset that like throughout the execution of this algorithm。

 and you can write down an easy recurrence for this thing， right。

 where basically you try all possibilities for the next vertex to go to。

so this over the course of running the algorithm could be any subset of this set。

 so there are two to the n minus two possibilities， roughly two to the n possibilities here。

 about n possibilities here。So the total number of states of this dynamic program is about n times 2 to the n。

 So your space is about。N times 2 to the n。And your time， well， for each state。

 you need to loop over the next vertex to go to， which has about n possibilities。

 so your time will be like n squared times 2 to the n。嗯。So great。

We can get poly space with n factorial time， which is super exponential。 It's like n to the n。

 which is like2 to the n log n。