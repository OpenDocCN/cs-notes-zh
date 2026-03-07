# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p20 P20 -BV1zNSCBkEgW_p20-

![](img/dcf8bfb4e07815aab5a0d7667e649b3c_0.png)

Okay， I guess let' me get started。So to date。We're going to see faster flow algorithms。

 faster max flow algorithms。Okay， so we're going to see。Scaling。Baling flows。Like this。

Blocking flows。Which you can speed up using link cut trees。Okay。

So let's just remember what we left off last time， I assume that people。You know。

 either had seen some flow or we'll just look up details on what I said last time。

 but the basic idea of last time was。嗯。We have a capacitated。Directed graph。G， which is VE。

And each edge。Ean Capital E has some capacity。C，E。Which I'm imagining is。In the range from。呃。嗯。

It's an integer in the range from one up to U。Okay。And we'd like。To find。ST flow。Of max value。Okay。

 so remember that a flow for us？Has to obey the capacity constraints。 First of all。

 a flow is just a vector defined on the edges。It should obey the capacity constraints we shouldn't push more flow than an edge has capacity for。

嗯。And the value of a flow is just the amount of flow coming out of S。Right。

So we said that the amount of flow going out of S has to equal the amount coming into T and for every other vertex flow in equals flow out。

 total flowing equals total flow out。Okay， so。So what I said last time was。嗯。Repeatedly。Find。嗯。

Augmenting paths。In residual graphs。so remember if we have some current flow F。

You you can define what's called a residual graph。Where the new capacity in the residual graph is the old capacity minus the flow on that edge。

So the residual capacity is just。How much more capacity is left over given the amount of flow we've already sent？

Okay， no question。嗯。So you can show that。呃。This algorithm is correct the algorithm of。

Repeat like find an augmenting path， in other words， find some flow。Then define the residual graph。

 find an augmenting path there， define a new residual graph， et cetera。

 keep iterating until there is no augmenting path。That is a correct algorithm。Okay。So。嗯。Ford Fkerson。

You just repeatedly。Find。Armenting paths。嗯 each。New path。Pushes。At least。One more unit of flow。

And you know time to find。One augmenting path。Is just linear in the number of edges， so why is that。

 how do you do that？Just say three letters or one word or something。Yeah， yeah， D Def search， DFS。

 BFS， basically just find any path from S to T in the residual graph and push one unit to flow there。

 So this implies。The time。Oh at times F star。Where F star is the value of。

The optimal is the max flow that's achievable。A呀。Okay， so。Today。

 we're going to talk about basically other algorithms that get faster than this。 Okay。

 this is pretty terrible。I mean， F star could be as big as。嗯。For example， n times u。Right。

The amount of capacity coming into T is as big as n times u or n minus1 times u。

 It's not even polynomial， right， because when we talk about polynomial time。

We want polynomial in the representation of the problem。

And to write down a capacity which is up to you takes log U bits。Whereas we're spending。

 we could spend up to U time， so that's exponential time。Okay。So。So。So time。Terminology。So。

We say the algorithm is weak polynomial。That means。The time is。Polly。M and log of U。So I mean。

 it is polynomial time in the representation of the problem。But we say it's strongly polynomial。

If at the time。This is simply poly M。The running time doesn't depend on the capacities at all。I mean。

 it implicitly does in the sense that you have to。pretendtend that you can manipulate。

Capacities in constant time。 can you can take mins of those numbers and add them and stuff in constant time。

 but the number of steps of your algorithm shouldn't depend on。

 shouldn't depend on how big the capacities are。Okay。And the last thing。

 which is I guess worse than these two is pseudopolynomial。And this is Polly。M and U。

 so Ford Fulckererson is pseudopolynomial。Today we're going to see some strongly polynomial algorithm。

 and we're also going to see a weekly polynomial algorithm。Questions about anything。Another place。

 for example， where you've seen pseudoponomial is Napsack， right？

If you remember the dynamic programming algorithm for NapsAC？The running time， not the PTA or FTA。

 but the exact algorithm。You do a dynamic program where the number of states involves the total weight of your knapsack。

Right， so you have a。So you're linear， your time is linear in the total weight of the knapsack。

 but that's again not actually polynomial time， that's again a pseudo that's what you would call pseudonomial。

So before I start coming some algorithms， I want to tell you what's currently known， so best known。

There have been some improvements recently despite there not having been improvements for like 30 years beforehand。

 so from the strongly polynomial。嗯。The best known is O of M N time， and this is due to Or。Okay。

 this is in stock 2013。So that's fairly recent。In fact， today I'm going to show you。

A lot of the steps to get almost this， I'm going to show you MN times log n。

 there's going to be an extra log n。Okay， I don't know if I'll get to show you all the details of login。

 but you'll see at least log squared n。And that balance is from 1983。So， you know。

 over the course of 30 years， finally， the log n was removed。 Actually。

 there was something in between where the log n。Was improved to something that。

Is never bigger than log n。