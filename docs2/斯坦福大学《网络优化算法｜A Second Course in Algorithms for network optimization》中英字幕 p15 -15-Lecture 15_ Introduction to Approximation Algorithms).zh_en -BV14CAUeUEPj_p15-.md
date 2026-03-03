# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p15 -15-Lecture 15_ Introduction to Approximation Algorithms).zh_en -BV14CAUeUEPj_p15-

Any questions before we get started？Okay， so if not。

 then with this lecture we're going to start on the fourth and sort of final module of CS261。

 which is about NP hard problems。Yeah。And pretty much all of CS161 and all of the first half of CS261 focus on problems that are solvable in polynomial time。

 that's kind of what we've been， what you've been doing for like a quarter and a half is learning polynomial time algorithms for lots of different problems。

Now， unfortunately， it's kind of a sad fact that in practice。

 there's actually a lot of problems which are both important。

 practically relevant and pretty frequently occurring。

 which we do not believe are polynomial time solvable so there NPR。

 so unless P equals NP there's no polynomial time algorithm for them。And so the question is。

 you know but just because the problem is NP hard， that doesn't mean you don't have to do your best to solve it。

 I mean， it may be some crucial optimization problem for your startup or whatever。

 So it's still important to kind of know are what are the options you have available to yourself as an algorithm designer when a problem is NP hard and so that's what we're gonna to focus on for the remaining lectures and primarily we're going to focus on approximation algorithms so I'm not really going to talk at all about MP completeness or MP hardness in this class in 261 I sort of assume that you've seen that in previous classes 154 or even before that if you want sort of a refresher on NP completeness how to define it。

 how to interpret it， I'll put some 161 level videos up on the course website if you're interested。

All right， so so what does it mean as an algorithm designer， if your problem is NP hard Well。

 I mean one thing to remember is it's not a death sentence。

 it doesn't mean there's literally it's literally hopeless to do anything nontri for the problem but it does kind of like throw the gauntlet to the algorithm designer kind of says like you're gonna to have to step up your game in various respects and particularly you have to make some kind of compromises so maybe the compromise is know you work a lot harder。

 you spend a lot more time in the problem you buy like thousands of cores maybe the compromise is you only restrict attention to kind of relatively modestized inputs or maybe the compromise is you sort of relax correctness and look at approximation。

So those are the things we're going to be talking about。So possible compromises。

 so it's not a death sentence， but it does generally mean you need significantly a more human and computational effort to get an acceptable solution to MP hard problems。

Okay。And there is， of course， sort of a tradeoff you know so the more work。

 computational and sort of human thought you put into a problem， the better you expect to do。

 and so we're going to be exploring a continuum like some things which are kind of quick and dirty and maybe the results you get aren't that strong and then if you work really hard。

 how do you get excellent results。 So we'll talk about that whole continuum。All right。

 so the first thing you can do is you can try to make the problem go away。You can say okay， well。

 maybe this problem in general is NP hard， but maybe my application has some special structure and with this special structure。

 the special case of the NP hard problem is actually polynomial time solvable and this happens a fair amount。

 In fact， you've already seen an example in this class。

 the vertex cover problem in general graphs as anmp complete problem But as you saw on a problem set in bipartite graphs。

 the special bipartite case vertex cover reduces just a maxment cut。

 and it's polynomial time sovable So sometimes when you do a restriction to a special case。

 you wind up in P wind up being polytimeollvable。 That's great。 Sometimes you're still MP hard。

 but you're in a sense still much easier than where you started。

 we'll see an example for that when we talk about the traveling salesman problem next lecture。😊。

In any case I do want to point out that I mentioned that sort of doing well on NP hard problems takes not just computational but human effort and so you implementing this step definitely takes sort of domain expertise in human effort。

 you have to understand your application， you have to understand what special structure your application has。

 and then you have to figure out an algorithm which exploits that special structure but when it works that's a great resolution。

So you don't want to solve NP hard problems if all you really care about is a polytime special case。

All right， so you can also spend exponential time。On the problem。

But hopefully it's still better than brute force。Okay。

 so sort of we sometimes almost identify MP hard problems。

 which are those that seem to require brute force， but the real situation is actually a little more nuanced than that。

 There's a lot ofmp complete a lot ofmp hard problems where you know while we don't know any sub exponential time algorithm。

 you can do better than brute force So instead of like brute force might be n factorial and we know an algorithm which is two to the n or brute force might be2 to the n but we know an algorithm which is 1。

5 to the n。Okay， so we don't know anything subexial for any natural andcomplete problem。

 but sometimes there are shavings， significant shavings you can do with respect to just the most naive brute force search algorithm time permitting。

 we'll see a couple examples in 261 in traveling salesman problem and in threeatAT as well。Okay。

And I should say， you know， pretty much in practice， right， there's almost no MP hard problem。

 you would actually resort to just brute force search。 You would always try to do something smart。

 So in a class like 261， we sort of focus on you know stuff that works fairly generally。

 and then you can prove guarantees about， you know in practice。

 keep in mind that you know there's always heuristics。

 which usually to at least some successful pruning at least some successful speed up over brute force。

 you know， although in practice， those are often super application specific。 And so for that reason。

 they don't really fit inside of course， like 261， which is focused on general techniques。

You can also say， well， you know， maybe we want to be fast， we want to handle large input sizes。

 and so then a possible compromise is to relax correctness。

So hopefully you relax it in some bounded way， hopefully you're still in some sense approximately correct。

 at least on most of the instances， if not all of them。

And that this is what we'll be mostly focusing on for these last three weeks。

So what this is called when you relax correctness， at least for optimization problems。

Is approximation algorithms。Now as you know， you can study approximation algorithms even for problems that are polynomial timeslvable so this particularly came up when we were discussing matching。

 so matching is polynomial timeslvable in the nonbipartite case even but it's fairly slow the exact algorithm so in the problem set you explored some ideas where we prove approximation say near optimal matching because that run a near linear time so we've already seen approximation algorithms for problems in P but for NP hard problems really they take on a sort of new importance because polynomial time exact optimization just isn't an option。

All right， so what's the game and approximation algorithms？

So we're going to take as a hard constraint polytime。Okay， in the worst case。

 so in every single input we want an algorithm that runs in polynomial time。

 obviously the smaller the polynomial， the better。But anything polynomial is a good start。

 much better than exponential brute force search。And then the goal。Again。

 we're going to be talking always about optimization problems。

 so there'll be a notion of an optimal solution， and we just want to get as close to it as possible。

这。Close in the sense of having objective function value close to the best possible objective function value of any feasible solution。

So that's sort of at a high level of what the approximation algorithms are about。

 you have an N hard problem， you can't solve it exactly in polynomial time， presumably。

 but if I give you a constraint of polynomial time， how close can you get。

 how close can you get to full optimality And so this there is now a massive massive literature on approximation algorithms people in a good chunk of the algorithms research world has been obsessed with approximation algorithms for。

Basically you know 25 plus years now， so as a result there's tons of results。

 there's a lot of sort of really cool general techniques and so the goal on CS 261 is just to expose you to sort of a couple of the ones that seem most broadly applicable。

 the ones that you might be most likely to remember later on but just know there's a huge huge literature on approximation algorithms。

And I guess you know sort of one takeaway， you know， we'll do lots of specific examples。

 including in this lecture， know， but one just thing to keep in mind what should be sort of cool。

For you is that one thing approximation algorithm shows。

 it shows that literally every algorithm design paradigm that you've learned so far in your studies。

 which you've probably only used for exact algorithms。

 is actually again useful for the design of approximation algorithms。 So greedy algorithms。

 divide and conquer algorithms， dynamic programming。

 linear programming and then even some other techniques like local search。

 which are also useful for heuristics。 all of those are used to successfully design good approximation algorithms。

 So we're almost going to be doing kind of a nostalgic tour of all the techniques you would have learned in 161 and seeing them useful now in this other context for NP hard problems。

 so that's one thing to keep in mind。😊，Allright。So that's kind of。You know。

 the philosophical preamble I had for you。So let's do some examples。

 so what are some examples of NP hard problems you might want to approximate and how would you approximate them？

So let me begin by just pointing out you actually already know several examples， really。

 let me just remind you of some of the ones that you know。So first。

 a problem we studied exactly a week ago。Min makes span scheduling。

So we were studying this at the time in the context of online algorithms。

 so the setting is you have M identical machines， there are end jobs each with a processing time and the objective function is to minimize the makepan。

 what does that mean， that means you want the most heavily loaded machine to be as lightly loaded as possible。

 so you want to minimize the maximum load。Equivalently。

 we're basically trying to distribute the jobs as evenly as possible between the different machines。

So that was the problem。嗯。We were setting it online where the jobs come one by one。

 but if you think about it， it's a totally reasonable problem to study offline。

 you could imagine cases where you actually know a whole batch of jobs that need to be scheduled。

 you know them at once， and then you want to do a more kind of centralized optimization to schedule them all in a smart way。

So the offline problem also makes sense。Again， offline means you have all the jobs at the beginning。

So that problem turns out to be NP hard computing the schedule with the best possible make span。

 We're not going to prove that。 and really we're not really going to prove any of these NP hardness results。

 I'm just going to state them。 You really already know how these things are proved if you've taken。

 say CS154 so you take some knownmp complete problem like SAT and then you reduce it to the problem that you're talking about and that proves that it'smp complete as well。

 So you should have seen a bunch of reductions of that form in your previous courses。

 All of these are proved by exactly those same kinds of reductions and I'm not going to do it not going to do it here。

All right， so for our purposes， let's take it as a fact that it's empty hard so we don't expect to get an exact solution in polynomial time。

 what would be a polynomial time algorithm that gets close to opt？Well。

 let's just revisit what we were thinking of at the time as our online algorithm。Grahamm's algorithm。

And Graham's algorithm and the parlance of approximation algorithms is a two approximation。

What does it mean that an algorithm is a two approximation。

 it means it runs in polynomial time so remember what Gham's algorithm is。

 you go through the jobs in an arbitrary order。Okay， one by one。

 and you always schedule the next job on the machine that has the lightest load。Clearly。

 a polynomial time algorithm， okay？Moreover， we proved back then。

 we proved that the schedule produced by Graham's algorithm has makes Ben at most twice the best possible in hindsight。

 Okay so the best possible hindsight is the same thing as our optimum right for the offline problem。

 so now it's just that both the algorithm and the optimalim solution have all the jobs up front。

So because Graham's algorithm had a competitive ratio of two。

 because it always produced a schedule no more than two worse than the best in hindsight。

Reinterpreting it as an approximation algorithm。You can call it a two approximation。

 always outputs to schedule within factor two of the best possible。And this too。

 this is usually called the approximation ratio of an algorithm。

 okay it plays exactly the same role as the competitive ratio for online algorithms。

 they just use a different word for it in the offline case okay。So okay， so you could say why。

 So for Graham's algorithm， you know if you really what you care about is the offline problem。

 the fact that Graham's algorithm actually processes jobs online， that's just kind of a bonus。

 It wasn't really a constraint for the offline problem。 So it's natural to ask， well， you know。

 maybe I can somehow do better。 if I have all of the jobs upfront。 Okay。

 And you can actually for this problem。 And actually a very simple idea。

 which youll explore and problems at four， already proves this。

 which is before you do your single passover the jobs。 You just sort them。Pros the biggest job first。

 then the next biggest job ending with the smallest job。

Now if you think about it sorting the jobs by processing time。

 that's definitely not an online computation， if I feed you the jobs one at a time and you have to schedule in that order。

 you can't sort， but if you have them all up front。

 you can sort them and then go in that order that lets you beat the factor of two actually by a significant amount。

So that's an example of how offline algorithms can do things that online algorithms cannot。Yeah。

 so Pet four。Can do better offline。Okay， so that's example one。

I want to go through sort two more examples to just reinterpret previous stuff you've seen as approximation algorithms。

 then we'll do a new example。So any questions so far？Okay。So okay， example number two。

 so this is something you may or may not have seen before it sort of depends on who you took 161 from。

 I teach this when I teach 161， some other people do too， but I know some people don't。

So hopefully though you at least heard of the NApsack problem。

 which is sort of a traditional killer app for dynamic programming。

 so what's the problem so the input is n items， each item has both a value and it has a size or a weight。

And then you also give you a knapsack with some fixed capacity。

And the goal is you want to pack thenapsack， you want to stuff it subject to the capacity。

 so some of the sizes of items you pick should be a most of the capacity subject to that。

 you want the most valuable subset possible so you pick the subset of items with maximum value that fits in this Napsack。

 And if you think about it like whenever you have like a single shared resource with bounded capacity。

 it's basically anapsack problem So it comes up all the time。Okay。

 so what do we know about Napsack and again， so if you want to refresher if you never saw that。

 I'm not going to teach it again in 261 because I teach it in 161。

 but I'll put some again some 161 level videos up on the course site if you want。ど宝。

Let me you let me sort of remind you of the executive summary。So first of all， like I said。

 the students usually learn this for dynamic programming。

 so you learn an exact dynamic programming algorithm that solves the Mapsack problem。

Now one thing which is pretty confusing until you get used to it。

 so the Napsack problem is actually NP hard。Okay， so there's no polynomial time algorithm for thenapsack problem。

 Let's remember what polynomial time means for a second。

 So polynomial always means polynomial in the input size。Now。

 you just have a graph with like n nodes and images， it's clear what the input size is。

 it's like n plus M。But remember， there's a subtle point when the input has numbers。 Okay。

 like the weight of an edge， the capacity of an edge or the value or the weight of an item in k Napsack。

So if the weight of something is a million， what's the input size？Well。

 the input size is just how many keystrokes it takes to type in the input to feed it to a program and you only need seven keystrokes to type down the value a million。

 so the input size is logarithmic in the magnitudes of the numbers。

 the input size is the number of digits needed to write down all of the numbers in your problem okay。

So polynomial input size means polynomial in the number of objects。

 plus the number of bits necessary to represent all the numbers。

 and the Napsack algorithm is not polynomial in that sense so the typical running time for the Napsack dynamic programming algorithm would be n the number of items times or let's say n squared times the maximum item weight。

So if I multiply all of the item weights by 10， this running time actually gets slower by a factor of 10。

 even though the input length only went up by a single digit per item。

 so that's called a pseudopolynomial time algorithm where it's polynomial in the number of objects and the magnitudes of the numbers rather than in the logarithm of the magnitudes of the numbers。

 rather than in the number of digits。So that's how you reconcile the fact that Napsack is on the one hand NP hard。

You cannot solve it exactly in time polynomial in the number of digits and the number of items and lets peak equals NP the other hand there are again。

 this is an example of beating brute force search right brute force search for Naps Act would be two to the n try all subsets of items and this dynamic programming algorithm in kind of almost all cases of interest will be much faster than that brute force search algorithm so this is like this is an NP hard problem where you can really do something non-trivial。

Okay， so that's what's up with solving Napsack exactly so what if you really want to be in truly polynomial time and you're willing to give up a little bit on correctness。

So。You can also there's a very natural greedy algorithm。

Where you know the gist of it is as you try to pack orders。

 try to pack the items in order of what's called density。

 so the value per weight bank per buck in a sense， so that will give you a one half approximation。

 meaning it's guaranteed to output a feasible solution。

 total value at least 50% of the maximum possible。So that's an application of the greedy idea。

So let's say dynamic programming equals exact。And then if you use dynamic programming。

In conjunction with truncation。What do we mean by truncation， well。

 what's wrong with the old dynamic programming algorithm？If the numbers are too big。

 then it runs a long time。 So what if I just like lop off all the low order bits of all of the numbers and the input So that actually that old algorithm。

 all of a sudden runs fast because the numbers have many fewer digits or much smaller numbers。

 So that's what I mean by truncation。 You take the input numbers， you chop them。

 You sort of divide them all by a million， something like that。

 And then you run the dynamic programming algorithm， and then you scale back。

So if you do that in just the right way。You can actually get a1 minus epsilon approximation。

For any epsilon you like in time。It's polynomial in n and1 over epsilon。Okay。

So now we know we can't get a one minus epsilon approximation for epsilon equals0 in polynomial time。

 But the point is is you can get as close as you want。

 you can get 99% in polynomial time it's just that as you get closer and closer to optimal。

 your running time is blowing up with a one over epsilon as part of it so you can't go all the way to exact。

 but for any constant epsilon， you really can't get a one minus epsilon approximation for a Napsack。

So that's sort of the happiest case imaginable so if your problem is NP hard。

 this is about the best you could hope for， that you get arbitrarily close approximation。

 many MP hard problems， this is not possible。All right， so any questions， Benny of that， again。

 this is all stuff I cover in 161 and I'll put videos up on the website if you want to check them out later。

So any questions？Okay。All right， so now let me revisit something definitely all of you have seen because this is again something we talked about exactly when we could go in the context of online algorithms。

The Steer tree problem。So again， let me just quickly remind you the setup。So the input is a graph。

Undirected。With edge costs。Free judge。And。One thing I asked you to think through last week。

On exercise set number7 was why there's no loss of generality in restricting ourselves to the metric special case。

 What's the metric special case， It means the graph， first of all， is complete。 Every edge is there。

 Second of all， the edges satisfy the triang inequality。

 Okay so the shortest path between two points is just the one hop path between the two end points。

Okay， so we'll use that again here。So without loss of generality。She is complete。

And the triangle inequality holds。Okay。All right， and then the other part of the input were terminals。

Okay， so let me call， as I said， I'll call them capital R。Well。So maybe we have T1。T2， T3。

 for example。All right。So。We studied this in an online context previously where the graph is specified up front and these terminals t1 through TK come in online one by one。

 and at each time it had to make a decision oh what's the goal so the goal is to output a subgraph of G that spans all of the terminals and subject to spanning all the terminals is as cheap as possible。

 minimum sum edge costs。So in the online context we studied a greedy algorithm which just processes the terminals in whatever order they come。

 so in some arbitrary adversarally chosen order， but again， just like with scheduling。

This problem makes perfect sense also as an offline problem， where I give you not just the graph。

 but also all of the terminals up front。 Okay， so just tell you， these are the 10 terminals。

 Connect them as cheaply as possible， please。So that's the offline standard problem。This again。

 is MP hard。Again， I'm not going to prove it pretty much。

Pretty much all of the MP hardness results from today。

 I think date back to the original paper on MP completeness or rather on sort of。

The pervasiveness of MP completeness by Dick Carpen 72。

 So these are all sort of among the very first generation of MP hard problems。

And we gave a greedy algorithm。Which was a two log k competitive。Or in the current context。

 we would call it a2 of log K approximation algorithm。Okay。

So remember what that on greedy algorithm was， just it effectively processes the terminals in an arbitrary order。

 each iteration it adds one new edge， connecting the new terminal to some previous terminal。

 and amongst all of the possibilities it does the obvious thing it fixs the cheapest of those edges。

So that was the online algorithm and it what we proved is that the solution of outputs is within。

Two log K times the best possible solution in hindsight i。e。

 the optimal solution of the offline version。Of the problem。Okay。So。In scheduling。

 I mentioned briefly that you could do better in the offline case。

 if I give you all the jobs in advance， you can sort。And so the question arises is， you know。

 if we study Steerttry in the offline case， can we do better than log K。

 you can't do better than log K with an online algorithm， it turns out。

But you can with an offline algorithm， and that's what I want to show you next。Yeah。

And the high level idea of why you can do better is the same as before。

 which is if I give you all the terminals at once in advance。

 you can process them in whatever order you choose。

 not just in some arbitrary one that comes in one by one online。So and again。

 we kind of want to sort of be greedy in some sense， so okay。

 we're going to process the terminals one at a time。

 what's the best order for us Well probably the first thing you might think of would be okay among all the terminals that we might connect next。

 let's connect the one that we can connect as cheaper than any of the rest of them。

Okay so if there's three terminals left， we could pick any of the next。

 the first one has a shortest edge of length three to a previous terminal。

 the second oneest has a shortest edge of length5 to a previous terminal and the third one has a shortest edge of length7 to a previous terminal we pick the first one so let's go for the three。

 maybe after we include the three we'll be able to connect those other two cheaper than we could before。

Okay。So that's an idea to do the same thing as in the online algorithm setting。

 except process the terminals in a greedy ordering in order of so basically at all times picking the terminal that you can connect as cheaply as possible。

If you think about it a little bit。You realize that what this algorithm actually is？

This algorithm is actually what it's literally doing is just running Pris minimum spanning tree algorithm。

On the subgraph induced by the terminals。It turns out。So if you go back and reread Prims algorithm。

 what happens， you start from a node， you add one edge every time， which edge do you add。

 you add the edge which is cheapest and will'll extend the tree by one。

 and that's exactly what this idea is doing here so it's literally just computing Pris algorithm on the subgraph induced by the terminals。

So this is why it's called the MST heuristic。So in general， we can describe。

This offline algorithm as just output。A minimum spanning tree of R where r is the set of terminals。

 so you have n vertices， some k of them are terminals， you forget about the n minus k。

 you just delete the n minus k vertices which are not terminals， you have a graph on K vertices left。

 you compute an MST on that graph of k vertices。Certainly， a polynomial time algorithm。

 certainly outputs a feasible solution。 outputs a subgraph spanning all the terminals。

 not totally obvious how good it is。Okay。And actually， you。

 it's easy to see from an example that it's not always going to be optimal。 I in some sense。

 we know that because it' is to be a hard problem， it's a polynommal time algorithm。

 but it's always good to see the concrete examples where they're not optimal。

So here I've redrawn an example from a week ago。This network here。

 which is complete and does satisfy the triangle quality。So the greedy algorithm。Delettes。

 so remember the middle node is not a terminal， so the greedy algorithm will delete this。

 be left with a triangle and computer MST of the triangle。So that'll be something like this。

 the blue solution。So that'll have cost for。On the other hand， the optimal solution。

We'll make use of the center spoke。And achieve three。Okay。

So what's really tricky about the Steinerchi problem is sort of adding extratro vertices to your solution can actually allow you to have a cheaper tree。

Because these vertices can kind of serve as rendezvous points that are kind of efficient for many terminals simultaneously。

 so that's what makes the ditry problem hard， and that's why this MST heuristic isn't always going to be optimal。

If you just generalize this argument， you use sort of bigger and bigger wheel graphs。

 you can show that the ratio between the MST and the optimal solution can become arbitrarily close to two。

Okay， so you can amplify this example and make this gap bigger， make this gap around two。And so then。

And that's going to be。Tight。In the following sense。The cost of the MST of R。

Is it most twice the cost of the optimalsteiner tree？Okay， so in other words。

 the MST heuristic is a two approximation algorithm for the offline standard tree problem。

 obviously blowing away the log K approximation we get from greedy except for super small kit。Okay。

All right。Any questions？Other than how to prove a theorem， it's actually quite easy。

So as far as announcements， Pro at three is due tonight， as I'm sure you know。

 problems at4 I'll post as soon as I can tomorrow morning at the latest and homework two solutions are available at the fronts and you should have your grade your grades for Pro at two already。

All right， so any questions before we prove that？That the MST is are almost twice as expensive。

As the oimmost sintry。Okay。Well， this is going to look a lot like our proof of the0 of log K competitive ratio for the online algorithm。

 but happily it's actually going to be easier so we'll use the same ideas but we don't have to work as hard。

And the reason is it's sort of easier to relate the cost incurred by the algorithm with the optimal solution in this offline case。

 we can do it the whole thing in one shot， rather than argue separately for each edge of the greedy algorithm。

 which is what we had to do in the online case。All right， so a T star。The optimum diner tree。

So the following maneuvers should be familiar to you。

So you going want to use the metric special case， the assumption that the edge have satisfied the China of quality。

Why is the China line quality useful it allows you to shortcut okay？So what do we want to shortcut。

 we want to shortcut something which includes in particular all of the terminals and we want it to be cheap。

 How do we make sure it's cheap， We start with O。What's the problem with opt。

 the problem with opt is it's not oarian， it's just some tree。

 so it's going to have degrees with odd nodes。But if we double every edge of the optimal solution。

 we definitely get an oarian graph because it vertex doubles the degree of every vertex。

 and it only doubles the cost， Why is it nice to have an oarian graph。

 well because then we can take an oular tour which uses every edge every once and visits every terminal at least once。

 then we can shortcut and then we can compare it to our MST and we'll be done。是。So in detail。

With HB you double all the edges。Of T star， so we just take T star and for each edge。

 we just make two copies， both copies have the same cost as the original edge。Again， clearly Olerian。

 all the degrees are even， which means it has an oiluler to。

We should also keep track of the cost here。All right， so T star has cost opt。

So if we double every edge， all of each combined has cost。Exactly two opt。

Now an o tour uses each edge of H exactly once。So the total cost of all the edges on sea is also going to be exactly two opts。

Nowm a shortcut。So shortcut to a simple cycle。On the full set of K terminals， t1 through TK。Okay。

 so because T star， because it's feasible spans all the terminals。

 which means that this Ouler tourr visits every terminal at least once。

 which means it's well defined to say shortcut it down to a simple cycle on the terminals。 Basically。

 you just look at the tour。 you look at the first occurrence of each of the K terminals and then you just shortcut accordingly。

Okay。Because the triangle inality holds short cutting can only make things cheaper。

So this is the most two opt。So now what do we do， we're actually now， unlike the online case。

 now we're actually just sort of almost immediately done。So we have a cheap， simple cycle。An。

The terminals， what do we have going for in our algorithm？Well， the algorithm computed the MST。

The best spanning tree， spanning the terminals， we have a cheap cycle spanning the terminals。

Pretty easy to turn that cycle into a tree。Just delete any the edge of the cycle and you get a spanning tree of the terminals。

And we picked the minimum spanning trees， for algorithms just doing better than that。

So R minus an edge。Is a spanning tree？Since the cycle had cost the most two opt， deleting an edge。

 also has cost the most two opt at costs are not negative。And MST。

 which is the output of our algorithm， is only better。And that's the full proof。So again。

 this spanning tree is again。And most too out。So any questions about that？Okay。Example number four。

So this one will be new to many of you， although it's totally fundamental。Okay。Again。

 I suspect this was one of the Kp's original list of MP heart problems。Set coverage。

So what's the input？So the input is a bunch of subsets。So maybe there's a subset。

 there's another subset， there's another subset。And there's a subset。All of some ground at you。Yeah。

So subsets S1 up to SM。Belonging to a ground sets you。

Think of each set as just subset is specified by a list of its elements， so if it has 12 elements。

 it's just like a linked list of 12 elements in the input。And。You're given a budget。Okay。

And what you want to do is you want to pick k subsets， k of the given subsets。

To cover as much ground as you can， to maximize the area of your chosen sets in this picture。So， go。

Pick K subsets。To maximize the size of their union。So it's。Clear what the problem definition is。Ch。

So the thing to notice about it is you know， So you want to maximize the size of their union。

 So obviously all else being bigger， sorry， all else being equal， bigger sets are better sets。

 You want to cover more stuff。 But it's not so simple。 right So if all the sets were disjoint。

 that would be fine。 You literally just take the the K biggest sets， but there's overlaps。

So just because it said is big doesn't necessarily mean it's all that useful to you。

 it could be mostly redundant， like in this picture， right if you look have the two biggest sets。

 they have an enormous common intersection。So if you pick one of these two super big sets。

Then as a second set， you might do much better for yourself picking one of these two sets as opposed to the largely redundant big set。

So it's these overlaps， this redundancy， which is mode it makes the set coverage problem kind of tricky。

 So you want big sets， but you also want small overlaps。

Okay so you know it's like any sort of super basic problem this shows up all the time and in fact。

 usually problems come up sort of like thinly disguised and you need some sort of practice to recognize them Se coverage honestly this just comes up like literally basically right so for example。

 you know maybe your startup has the funds to hire like K new people okay how do you associate a set with a potential employee。

 it just corresponds to the skills of that employee or the tasks that they can accomplish if you like you can hire K people you want to cover as much territory as you can have as many skills as you can get。

Or you know maybe you're building things， you're building factories。

 fire stations or seasonalsal chocolate shops， whatever and you want to cover as many neighborhoods as possible again it's literally a set coverage problem in machine learning。

 maybe you want to just identify a small number of features that explains as much as your data as possible it's a set coverage problem maybe an HCI know you're trying to figure out how to display stuff on a screen and you know the user only has a budget of like three or four menus or windows or whatever and you want to figure out which three or four things should you display to maximize either you know maybe the number of topics covered on an aggregator know or maybe the amount of functionality that the user can do with that set of menus。

So really kind of all the time。All right。Yet again， NP hard。

So we need to figure out what we want to do with it。And both in theory and in practice。

 a pretty good way to deal with set coverage is a greedy approach。

 This is going to be sort of one of the killer apps of the greedy design paradigm in approximation algorithms。

All right， so what would be the greedy algorithm？We're going to pick sets one at a time。

What's the first set？First， that's going to be the biggest set， why not。

 cover as much stuff as we can。How about the second one？Well， we could pick the second biggest set。

But we kind of don't really want to count the elements already covered by the first set。

So it's almost like we want to redefine the size of sets in our head after deleting out everything that we've already covered。

 and then with respect to that new measure， we want to pick the biggest set。Okay。

So a little more formally。You just pick the sets of one at a time。And in the eye iteration。

You take the subset that maximizes the number of elements that are newly covered。嗯。Okay。

 with respect to a1 through A1 through AI minus1。And then you just return the case sets that you picked。

Is there everything clear？All right。Do I want these， yeah， I do。So how well does it work？

That's the obvious question。Clearlyly polynomial time， we're not worried about that。

How well does it work？And it seems like a pretty good idea， actually。

 kind of feels like it should work well。Okay， we know it's not going to be optimal， though。

 because it's an N hard problem。And so as usual， it's kind of helpful to kind of see what can go wrong。

Some concrete examples where greedy is not optimal。So let's do some examples。So example one。

This will just be with k equal2。 remember K is the number of subsets you get to pick。So。Here。

We'm going to do the following， so here's our ground set。You。And。

What I have in mind for a the optimal solution。Is that there are these two disjoint sets， S1 and S2。

Each of which is exactly half the ground set， so it's a partition of the ground set into S1 and S2 equal size。

Now， if this was the whole input， the greedy algorithm would have no trouble。

 it would just solve it optimally， so we need to trick the greedy algorithm into doing something wrong。

Doing something wrong means choosing a set other than these two。But it's a greedy algorithm。

 so to get it to choose a set other than these two。

 we need to feed it a set that has 51% of the universe in it。

 otherwise it'll take one of these because they cover 50%。So that's what we do。We define an S3。

Which is 50 plus epsilon percent of the universe。Okay。And that's it， so that's the whole instance。

So what happens， well， the greedy is tricked into picking S3 first。

Because that's the biggest of the sets。And now in the second step， it has to pick either S1 or S2。

 It doesn't matter which one it picks。 Maybe it picks， for example， S2。Okay。

And so what we find is that the opt is the full set of the universe。

And greedy is roughly three4 of the universe size。Okay。Have crew on that？All right。

 so that's a concrete example of what can go wrong for greedy， proof that it's non general optimal。

 which of course we already knew， but it's good to see this。Let's at another example。

Let's try to build on this idea。Now with k equal three。Okay。

So what's opt going to look like now so it's three sets。

 so I guess instead of partitioning the ground set into two equal size sets I'm going to partition into three equal size sets。

Equal size sets， yeah。こ。Okay。S1， S2， S3。Eachs exactly a third of the universe size。So again。

 we want to trick。The greedy solution into picking and the making mistake into picking something other than S1 S2 or S3。

 And actually， we don't have to work quite as hard to trick it in the first iteration。

 These are 33% of the Uniized。 So if we just have something。S4。Which is。U。One third plus epsilon。

Then greededy will pick that。In the first iteration。Now， we again。

 we' we don't want the greedy algorithm if we're sort of trying to have a bad input。

 we're trying to trick the greedy algorithm into still even in the next iteration。

 even for the second set， it's still not going to pick S1 S2 or S3。Okay。

So how do we make sure so we got to feed it basically a set which is bigger than S1 S2 or S3 well。

 not quite。Because greedy is only looking at the newly covered elements。

 so we have to feed it something that's a little bit bigger than the sort of Vi territory in any of S1S2 or S3。

So。Suppose the good algorithm picks set set S1。 Okay， What would be the benefit to it， right。

 So notice that right， each of these columns is a third of the rectangle。

 And this is also about a third of the rectangle。 So in the intersection， one of these small squares。

 That's one9th of the universe。 Okay， We have one9th in here。 We have two9s。Currently。

In each of S1 and S2 and S3， relative to the elements already covered in the first iteration by greedy。

So to full greedy a second time， we just need to give it a set which covers slightly more than a two ninth fraction of the universe。

So that's easy to do。We just give it an S5 here。Which is29s plus epsilon fraction action of the Uni size。

Greedy will then pick S5。And now in the last iteration， we allow Gy to pick S1S2 or S3。

 and it doesn't matter which one。So again， maybe it picks。S3。So again。Opt is 100%。So what is greedy？

So greedy is everything but these two squares。All right。

 so what's one of these squares well this was two9s of the full rectangle and then this is two9ths of the sub recectangle。

 so what is uncovered up here is29 squared， sorry not two9 squared，29 times one third excuse me。Yeah。

 anyway， so one minus two times。Two ninths times one third。So this is the one third part。

And this is the two ninth part。So that's what's left uncovered by greedy， and that happens twice。

Both here and here。So this gives us。227th， 427th。Shoot， this is wrong。这这这这这这这。去。I see。

 this is a four， sorry about that。One minus827。She goes 1927s okay？So again。

 so where is the third comes from， the third just comes from I'm focusing on a column。

 where does the fourns come from， well this is covering one third of the column。

 this is covering another twons of the column so that's fivens leaving fourns of the column okay so the width is one third and the height is fourns and we have two such rectangles those are uncovered so this is what is covered。

What is this， this is roughly 70%。Okay， so why did I walk you through this a couple of reasons。

 but the first thing to notice is that by bumping K up from 2 to three。

 we were actually able to get a bigger gap。 Okay the first example only showed greedy cannot be better than a three quarters approximation Now we know it actually can't be better than a 19 over 27。

Approxiation。Okay。Any questions about the example？Examples。Okay。So you can extend this idea。

So using exactly the same pattern and you can prove a lower bound on how good greedy could be for all k。

And you get the greedy is no better。Then1 minus1 minus1 over k to the K。's a plug in two。

 if you plug in two， this is a half， so this is a quarter， so this is three quarters。

So that's what we had here。Blugging K equal3， What do you get。

 you get two thirds raised to the cubed， so that's  a27，1 minus a27， it's 1927。

 So those are the k equal2 and K equal3 cases extending this idea you get this expression。For。Okay。

 for any cap。Now maybe you're wondering well okay， well。What is this number？

So it keeps getting smaller with each value of k。 So it's decreasing。 What is it converging to。Well。

As k gets large，1 minus1 over k is very well approximated by e to the minus1 over k。

Recall that we had this figure。This was in the middle of the analysis of the multi of weights algorithm is when we were using this。

That the exponential function is well approximated by 1 plus x， especially。Right around here。

 right around zero。So that means as k gets large， this becomes very close to e to the minus k。

 e to the minus k to the k that's just 1 over E。Are actually getting the same thing we had last lecture。

1 minus1 over three。63。2%， roughly。在这。So before this class。

 one minus1 where you probably struck you was a weird number， comes up surprisingly often， actually。

So again， what was the point of all this， The point was， as k grows large， if。

 if we don't restrict K to be small， then we're not going prove a bound better than 1-1 over3 for the greedy algorithm。

 Okay， but of course， whatever， these are their first examples。 for all we know。

 there are much worse examples。But there aren't。So theorem。They're all k。Greedy is， in fact。

minus1 minus1 over k to the k approximation。And so in particular。

 it's always a 1 minus1 of re approximationroxi， and then it's better if k is small。Okay。

 so this is literally the worst example you will ever see when k equals 2。

 this is literally the worst example youll ever see when k equals 3 and so on。Okay。

So next goal is to prove this。Any questions for that？We've been clear on the problem， the algorithm。

 the statement， the tightness。Good。All right。Quick little lemma。

So thelemma really is where we isolate what's special about the greedy algorithm。

 and then the proof is just going to be kind of little algebra on top of that。So what's dilemma？

You know， pause the greedy algorithm in some iteration。I don't care which one。

Suppose that at the moment。The current greedy solution， the eye sets it's chosen so far。Covers。

L elements。And I don't care what L is。Then。The next set chosen by greedy。Covers at least。1 over K。

Ot minus L。New elements。Okay。So what's the point of this lemma。 So you know in general。

 how do you prove good things about greedy algorithms。

 One of the most natural ways to do it is to kind of say every iteration of the greedy algorithm。

 something good happens， And you saw this all the way back in like Dketra's algorithm where you proceed by induction on the number of iterations and you say every iteration of diyktra。

 it's correctly computing some shortest path。 And so when it processes all the vertices it's done and it's optimal here we're not going to be optimal。

 We're gonna be approximately optimal， But this is giving us a lower bound on the progress of the greedy solution relative to kind of how many elements it's currently missing。

😊，Okay so if L is close to optt we're already done， if L is far from opt。

 then this guarantees us a lower bound on how many new elements we get at the next iteration。

 so as long as we're covering much fewer than not we're going to make rapid progress in increase it。

Which sounds like a good thing。 Sounds like probably we should be home free。

 and we are modular little algebra。I guess I should prove the dilemma for you。

Do you see the proof of dilemma？It's kind of a one liner， actually。Here's one way to think about it。

Granted at the moment， we're only picking one set。But suppose we actually picked k sets right now。

 which should be kind of ridiculous， but suppose we did it。

 and actually suppose we just magically knew what the optimal sets were and we picked those K optimal sets。

How many newly covered elements would there be？At least。

How many elements would be covered at least if we picked all k of offsets right now？Ot right。

 we just， we'd at least get the elements in those sets。 right So we'd boost our value up to opt。

From the current value of L。All right。So if weve picked all K sets in the optimal solution at once。

 we would certainly boost our objective function by optt minus L。Now these are k sets。

 I'm only picking one set， but if picking k sets would boost it by optt minus L。

 then an average one of those k sets would boost it by opt to minus L over k。

 and so in particular the most useful of those k sets would cover at least optt minus L over k new elements。

Now we still don't know which set that is， but we pick the set in the greedy algorithm that maximizes the number of newly covered elements。

 so we only do at least as well as this best of the K optimal sets。So' the approved。

So it holds for one。Of the case sets in aunt。Again。

 it even holds sort of on average for the sets and optt。

 and of course the max is always at least the average。And our set。Greedy only does better。Okay。

So there any questions about that？That's dilemma， so we're just a little bit algebra away from the theorem now。

It can be instructive to。And stain shape that lima on our bad examples。So say k equals  two。

With the lemma asserts， it says， well， okay， in the first iteration， L is0。Okay。K is 2。

 So the lemma is just telling us that whatever the greedy picks in the first iteration。

 it's got to be at least half the universe。 Why because one of opts， right。

 So if opts covers the whole universe， one of its sets covers half the universe。 And indeed。

 that three covers half the universe。Now， in the next iteration。What does the dilemma assert。

 it says， well now the number of uncovered elements is opt over two。

And so it says we get at least one half times optt over two， so opt over4 or 25%。

 and indeed that's exactly what happened when we pick S2。The number of newly uncovered elements。

 covered elements is a quarter of the universe size， so not surprisingly。

 given that Ive told you that the upper and lower bounds are going to match。

 that lemma actually is holding with a quality in every single iteration in our bad examples。

All right， it's a proof theorem。All we're going to do is iterate this lemma and see what we get。

So a GK， a GI。Deote the value of greedy。After eye iteration。By value of greedy。

 I just mean the size of the union of the high sets that it's picked so far？

So we're going to try to understand how rapidly this grows， and again。

 themma sort of tells us that either you're already close to opttI or you're going to get a big jump from GI to GI plus1。

Okay， so then。So GK is what we really care about。 This is the final value of the final greedy solution。

 GK。So let's apply dilemma。So how many elements have we covered？At the end。Well。

 it's however many we covered after K minus-1 iterations。

 plus the number of newly covered stuff in the last iteration， the K iteration。How much did we cover？

In the K iteration， well， we don't really know， but we know it was at least。1 over K。

Times O to minus L L conveniently is just Gk minus1。Okay。Oh。So this is using the limma。Okay。

Also known as opt over a K。Plus1 minus1 over k。GK minus1。Okay， just reorganizing terms。And。Now。

 of course。We can just play exactly the same trick。So this gave us a lower bound on GK， GK minus1。

 we're going to get exactly the same lower bound with indices dropped by one。Okay。

So at least Gk minus two。Plus1 minus1 over k。呃。去去去。Let's see， I see， I'm getting ahead of myself。

 okay，Plus one over k。Os minus GK minus2。so this is just applying the lemma to GK minus-1。

 how many elements are covered， well it's whatever you were covering the previous iteration plus the newly covered elements in this iteration。

 and that by the lemma is guaranteed to be at least1 over K optt minus the amount of stuff you were covering before the iteration。

Now， if you want to substitute the blue thing back into this expression。

 just notice that this is all multiplied。By a 1 minus k。So basically， every time we apply the lemma。

 we pick up another 1 minus1 over k power on the remaining terms。So。

Let me just rewrite this a little bit， so it's clear。So opt to K。Plus。Ch。1 minus1 over k opt over k。

That is。Yeah。Plus。Maybe I'll just skip the skip to the end， skip to the punch on。Okay。

 so when you iterate。Yeah。When you iterate， what do you get？You get the least。Optto K。plus。

Offt over k1 minus1 over k。Plus opt over k1 minus1 over k squared， and so on。

And you have one of these terms for each iteration of the greedy algorithm。

 there were k iterations of the greedy algorithm， the exponent starts at zero。

 so the last exponent is going to be k minus1。Okay。This may be clearer if I also just write this as。

Equal opt over K。Plus 1 minus1 over K G K minus2。Okay。

So this term corresponds to this term this optt over k。

 this optt over k times 1 minus1 over k that corresponds to this  opt over k multiplied by that leading term and then so on。

 and then we just keep it aating。So every time you apply the lelemma。

 you get another term opt over k， but the 1 minus k is raised to another power。All right。

So obviously， so this is something we know what to do with， right。So again。

 we just analyzed greedy iteration by iteration， we had this simple lemma which would of give us a lower bound on progress and happily when all the dust settles we just have a geometric series。

 we know to do a geometric series， we know close forms for them， right。

So we bring the  opt K out front。So now we're summing 1 minus1 over k。

To the I from I equals 0 to k minus1。So what do you get？So geometric series。

 so remember it's bunch to things of the form P to the I。

 you get a 1 minus P and the denominator and the numerator， if you do the infinite series。

 then you just get one， but so we have a truncated series， the last term is K minus1。

 so we're going to have an error term in the numerator。

So this is like the1 minus P factor you should be useful， used to from geometric series of P to theI。

And then up here， what's the correction term1 minus。1 over k to the K。And so again。

 this is in your one of three notes， I'm sure okay。That's what you get with a geometric series。

This notice is 1 over k。It's that cancels at the K。Leaving us with art。

1 minus1 over k raised to the K。As claims。Okay。So that's set coverage in the greedy algorithm。

Now of course， this is a tight analysis， we know you can't do anything。

 you can't prove anything better for the greedy algorithm， we have bad examples。

You might of course wonder could you have a smarter algorithm， I mean。

 this is one of the most natural things you could try。

 and so this becomes sort of more amazing when you find out that actually， unless P equals NP。

 there's no better approximation algorithm。So one can prove that any improvement over 1 minus1 over3。

A really sort of above this for any K or for large enough K would imply P equal in P。 Okay。

 if you could beat that factor。 So unlike the Napsack problem where you can get1 minus epsilon for epsilon as small as you want here。

 there is really kind of a hard barrier with how closely you can approximate sec coverage。

 at least in the worst case in polynomial time。And that threshold is exactly 1 minus1 over E。

And it's exactly the greedy algorithm that gives the optimal approximation algorithm in terms of the worst case approximation ratio。

So any questions about that？Okay， so that's the last real proof that we have for you for the lecture。

I do want to tell you just sort of about where。Kind of this idea has gone viral recently。

So I'll say a little bit just informally。About the problem of influence maximization。

So it's funny because， you know， this greedy algorithm was around in the 70s and the analysis and actually。

 lots of generalizations。 All that stuff was known in the 70s。 The hardness result is more recent。

 more like the 90s。 But so people knew about these greedy algorithms forever。

 And they've really just in the last5 to 10 years， totally gone viral in both machine learning and data mining。

 you really， there's really lots of papers that think about these influence maximization problems and use these kinds of greedy algorithms and you'll see 1-1 over3 in the papers and all this kind of stuff。

 So I want to just give you a little bit of a glimpse of this。😊，So there's a lot。

 I people have been looking at a lot of applications。

 but let me just single out one which is representative and has been particularly influential。

So suppose you have a social network by which I just mean a graph。

And let's work with directed graphs so you can think about like the Twitter graph who follows whom that would be a directed social network。

As far as the semantics for our purposes， we want to think of an edge from V to W as meaning that V has some influence over W so when V updates its opinion or its action。

 there's some chance that will cascade to W updating its opinion or action。All right。

So now I'm going to propose just a very simple model of how ideas， you know。

Videos that are being shared， memes， whatever， how they might spread through a network。 Okay。

 there's many other such models as well。 But this one I'll do fine for our purposes today。So。

Imagine that some vertex is active。So nothing was sort of amusing， I mean， all this stuff。

This idea of looking at spread in networks。This has been around since before computer science。

 people cared about this before。Computer science was really disciplined。 Edemiology。

 They cared a lot about the spread of stuff through networks。 Okay。

 And that's actually where these models come from。 They were looking at the spread of diseases and thinking about you know who to vaccinate。

 Who is it really important that doesn't get infected。

 because if they get infected is likely to spread the lots of other people。 Okay。

 so that's where all this comes from。All right， so I'm going to say active instead of infected。

 it sounds a little better。A little more positive。So when V becomes active。

 it has an opportunity to activate all of the vertices that it influences。

 we look at all of the edges going out of V and for each of those vertices on the other side of that edge。

 there's some chance it now becomes active as well。So。For all outgoing edges。With probability P。

 P is just some parameter of the model。 think of it as like I dont know， 0。2， for example。

So it's probably P。W gets activated。If it's not active already。Okay。So for example。

Maybe V is activated。So now all of a sudden there's a chance for each of these three nodes to be active。

 and we flip an independent coin for each of the edges。So maybe this one actually。

 this person is influenced， okay， they change their opinion or they sort of do some product switch or whatever。

Maybe this person is not activated， but this person is。So now in the cascade model。

 now these two newly infected nodes also have an opportunity to infect people outside of their outgoing edges。

 So， for example， maybe this vertex。Faiils to activate this vertex X， but。

This vertex at the bottom has a second chance， another chance to activate x。

 and maybe in that case it succeeds。And so then here。

 x does wind up being active at the end of the cascade。 Okay So if you think about it。

 one way thing about this is， you know， suppose V gets activated， when is x can also get activated。

 it's going to be if and only if there's a directed path from V to X of edges that all got activated。

 Okay， so a path of the pink edges。 That's exactly when X， it's activated given that V was。

All right so a couple of things to notice so in this model again there's lots of variations。

 but once a vertex is active， it's active forevermore， first of all。And then second of all。

'll notice that， you know， it's sort of memoryless from a vertexus perspective。

 right So if you find out you know that somebody really likes， you know some new song， you know。

 the first time maybe you ignore it， the second time maybe you ignore it。

 the third time maybe you sort of you know listen to the song yourself。

 but it of it's assumed to be independent， So each of those sort of times you see a friend of yours。

 listen to a song， you have an equal independent probability of listening to it yourself。

So questions about the model？So this is just a model you could posit。

 so you can imagine doing lots of things， you can imagine doing simulations to see who gets infected as a function of who starts the cascade。

So what people have really been focusing on on the optimization side。Is you know。

 how do you get this process to spread as fast， as far and wide as possible Okay so people are sort of thinking it's like。

 oh， well， you know， we have some marketing budget， you know。

 or we have a sort of limited number of free products we can give people you know or you have a you know there 10 people I can take the time to call them on the phone and try to convince them of some new idea。

And then the hope is that the cascade will take care of the rest so you have a small investment up front and you're relying on this cascade to spread your ideas or spread your product or whatever far and want。

And so the question is， what's the best way to do that？And so the objective。Could be the compute。

 the K most influential nodes。That is。You want to maximize。Overall all subsets of size k。

F of S defined as the expected。Remember， it's a random process。 Okay。

 remember you flip a coin for each edge， So that's why there's an expectation。So the expected number。

The active nodes at the end of the cascade。If all of the nodes of S are active。At the beginning。Okay。

So certainly， this is always going to be at least k。

 So if you activate K people at the beginning and it never spreads anywhere。

 you're going to have exactly K people be active。 the hope is that maybe it goes from this seed set of size K via the cascade to a much。

 much much bigger set of people okay。And so if there's some magical set of influential people where that's likely to happen。

 you want to figure out who they are。So that's the influence maximization problem。

So let me just tell you the punchline。Because we out of time。

So it's natural to think of a greedy algorithm。For this， actually。So you currently you have nobody。

 but you haven't given your， you haven't called anyone on the phone to tell them your idea。

 And so who do you call first， who do you call the person that's going to lead to the biggest jump。

And the objective function value。How do you set in the second person？Well you say， well。

 let's look at the person who gives us the biggest jump relative to where we already are Okay。

 so maybe be on average， it's going to reach 12 people with this first person and then the second person I'll reach you know 20 so eight new people compared to just having the first person and so you can just do that K times and that's the greedy algorithm。

And it turns out exactly the same analysis that I showed you for max coverage applies to this and a bunch of other problems as well。

And the basic reason。Is that if you think of the process in this sense where basically you're just flipping coins for all of the edges And the question is just how many vertices are there paths to。

 If you think about it， you realize that after you flipped the coins for all of the edges。

This is actually literally a coverage problem。Where the sets correspond to who can be reached from some vertex。

 so if some vertex has passed to 20 different vertices。

 that's going to correspond to the cardinality of the set。

Maximizing the number of people that you actually reach is exactly the same as the coverage problem on with those definitions of subsets and then the influence maximization problem。

 the only sort of extra bells and whistles is that there's an expectation So it's not one coverage problem it's really kind of a superposition an average of a bunch of different coverage problems。

 but if you stare at the analysis I gave you for a little bit， you realize it still works just fine。

Okay， so again，1 minus1 over three。So Thursday I'll be a traveling salesman problem， see you then。

