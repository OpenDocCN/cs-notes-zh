# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p13 -13-Lecture 13_ Online Scheduling and Online Steiner Tree).zh_en -BV14CAUeUEPj_p13-

Okay， so last week we started our discussion about online problems and online algorithms。

 we talked about the multiplicative weights algorithm。

 that's online algorithm for online decision making。 and we talked about its guarantee。

 and then we kind of sort of a detour last Thursday where we didn't talk about online problems per se。

 but we talked about applications of multiplicative weights。

 So both to zero sum games and to the fast approximation of certain linear programs。

 So this week these two lectures are going to be sort of on the more traditional quote unquote part of online algorithms。

 So we're going to study a couple of the traditional killer application domains。

 things like scheduling things like matching。So there's two problems and two algorithms I want to discuss in full。

 if there's time， I'll introduce you to a third problem as well。

So the first problem is about scheduling， so what's called Minm span scheduling。

And so recall what an online problem means in general。

 this is where you do not have all of the data in your hands up front data arrives piecemeal one piece at a time。

 and as the algorithm， unfortunately you can't just wait till you have all the data and then solve it like you've been solving problems in this class and in 161 rather you have to make an irrevocable decision each time a new piece of the input shows up so like an online decision making every day you had to take an action without knowing the cost of that action so to specify an online problem I need to tell you sort of the way in which the input arrives。

 what do I mean by piece by piece and then what decision do you have to make when a new piece arrives。

So this problem is going to be。We're going to be thinking about jobs being scheduled on machines。

So there's going to be M。Machines， all of them are exactly the same。

 and you know about these up front， Okay， so you know you've got your M machines。

And then what arrives online are the jobs。Okay， so jobs arrive online one by one。

And job J has a processing time。Pj。Okay。So this is the input coming in one at a time jobs。

 one at a time， what decisions you have to make when you get a new job。

 you have to figure out which machine to schedule it on to assign it to。Okay。

So you wish you could just wait till you got all the jobs and then you could just assign them in a globally optimal way。

 but that's not going to be allowed， okay， so this is like real time scheduling， if you like， okay。

All right， and so again， by schedule。So feasible solutions correspond on the schedules。

 and that just means an assignment of each job。To a single machine。Okay。All right。

So what's the objective， what do we want， Okay， so people have thought about a lot of different objective functions in a scheduling context。

 but probably the most practically relevant one is the one we'll talk about now called the makepan。

So to define the mix band， I need to tell you what the load on a machine is。In a schedule。

So the load on machine eye is just the sum of the processing times。Of jobs。Assigned to I。Okay。

So you showve as a processing time of given machine out of a bunch of jobs assigned to it。

 you sew up those processing times that's its load。And then the makepan is just the minimum， sorry。

 the maximum。Over machines。Of the machine load。Okay。So for example。If you have four jobs。

 two machines。And you schedule them like so 2213， here you're going to have a mixed span of four。

Both machines have load  four， so the max is4， on the other hand， that's a three。On the other hand。

 if you sort of screw it up a little bit and you put say a two and a three on the same one。

And then over here you have a one and a two。So here they make bands five。Which is worse。

 we want a small mixedpan。Okay。So yeah， so we want to minimize this。

So basically the goal is to load balance as evenly as possible。

 so that's the way we're going to minimize the maximum load is we're basically going to try to get it as even as possible。

And again， in many scheduling contexts， make Spanish really what you care about Okay。

 so like if you want to think about， say you're spawning off a bunch of mapprod jobs or Hadoop jobs to do a bunch of parallel processing。

 well， in many cases， you don't know the final answer until the last of those parallel processes has completed so it's really governed by the latest job to finish that corresponds to the last job on the machine with the biggest load it's really very practical objective function。

Sa questions about the setup。Either about sort of what I mean by the data rise online or by what the objective function is or anything else。

Cl so far。Okay。All right，This is one of those cases where sort of possibly the first algorithm you think of actually does great。

 case what sort of a happy case。So here's a natural approach。

And this was actually analyzed exactly 50 years ago。By Ron Graham。When he was at be Labs。All right。

 so jobs coming in online。 You got to schedule it right now。 This job shows up。

 So you got to pick a machine。So I mean， there's a few things you could think to do。

 You could like pick a machine uniformly at random and hope it like gets pretty load balanced。

 But I mean， actually， which machine would seem to make sense。

 given that you want everything to be even。At a given time。

 which machine should you put the new job on？Right， exactly right。

 So I heard many people say the one with a minimum load。

 so the one which is sort of know under full compared to everybody else。

So that's what we're going to study。So when new job Jay arrives。Assigned to the machine。

With smallest current load。Okay。Yeah。Now how are we going to measure the quality of this online algorithm。

 so we need a benchmark。A yards stick against which we compare our own performance。

And we're going to use this strongest possible benchmark we're going to say well。

 you know imagine we actually could wait until we had all the jobs and then we just computed the optimal schedule。

 the schedule with the minimum mixpan， or if you prefer。

 imagine that we had full knowledge of the future。And then we could schedule the jobs in a way that would get us the minimum possible makepan。

Okay， so we define opt。To be the minimum makepan of any schedule in hindsight。Okay。

So when we're talking about online decision making。

 we talked about the best fixed action in hindsight that doesn't really have a natural analog in this context。

 but we really can just what we're going to do successfully is say that we're not too much worse off than this very strong benchmark。

 so what an allpower all-know opponent could accomplish。Okay。All right。So we have our problem。

 we have our algorithm， we have our benchmark， we want to know how close is our algorithm to this benchmark。

So what are the challenges involved in trying to prove some kind of guarantee for an online algorithm like this？

Well， the challenge is kind of the same thing as it was when we were trying to design optimal algorithms for Maxflow and know。

 biparttheite matching and so on。 We need to know how do we know that we're done。 And back then。

 it meant how do we know when we're optimal。Now， here。

 where we're making decisions online and the optimum has full hindsight or full forknowledge。

 we're not going to expect to be optimal。 Okay we expect we have to make some compromise in our guarantee。

 reflecting the fact that our algorithm is much less powerful than the benchmark。

So we're not going to say that the algorithm is optimal。

 but we still want to say that the schedule it produces is close to optimal。

 So then the question for the analyst is how do we know if the solution is close to optimal？

So how do we know？Okay。If we're close to the optimal solution。Okay。So how might we prove this？

So the idea in the analysis， so the algorithm is just Gham's algorithm so the algorithm is just as is。

 So we're talking now about strategies for the analysis。

 So the plan is rather than try to understand opt itself in any detail。

 we're going to define some simple， lower bounds on how small opt could possibly be。

 Okay so these lower bounds will be things that could only be better than opt。

Sort of like when we were talking about dual feasible solutions， it's kind of a similar idea。

So next what I want to show you is I want to show you two different simple lower bounds on this number。

Okay。Then we're going to compare the output of Graham's algorithm to those lower bounds on the optimal solution that will give us the guarantee。

All right。So then the question is where do these lower bounds come from actually one of the most powerful tools for generating these lower bounds you already know。

 which is just linear programming duality because remember this is a minimization problem。

 so we're looking for lower bounds and that's exactly what dual feasible solutions give you for a minimization problem。

😊，Now the two online problems we're going to talk about today actually we don't need to be so sophisticated。

 we're going to be able to just kind of make up good enough lower bounds for our purposes anyways。

 but a little bit later we will use linear programs for this purpose， again， just in the analysis。

 not in the algorithm。Okay。So。The first lower bound， I hope is kind of obvious。

The Minm ban is at least the size of the biggest job。

Any schedule has to put the biggest job somewhere， and that machine is going to have load at least equal to the size of that job。

Okay。So that's our extremely easy lower bound， then we have a still quite easy lower bound。

 that's limit two。So limit2 says， not only does the Min make span in hindsight have to be at least the size of the biggest job。

 but it also has to be at least the average。TheSor of the sum of the processing times divided by the number of machines。

 So in some sense， the best possible scenario would be like all the jobs get divided across the machine so that everybody's load is exactly the same。

Okay。So formally。This is。One over Ms。 so remember M's the number of machines。

And then the sum of the processing problems。Okay。And again。

 the way to think about this is sort of like the gold standard for load balancing is you make everything exactly the same。

 the load of everybody exactly the same。 And this is what that would mean if you made everybody exactly the same。

The total load on everybody divided by the number of machines。So just to make it formal。

So consider any feasible schedule。Again， in hindsight。Well， the max load of a machine。

 I either make span that's only more than the average load of a machine。

You can't have everything be smaller than the average。And。This is just equal to this quantity。Okay。

So those are our two lower eventss， but are those clear？

So neither of these in general is going to be exactly the same number as opt。

 but they can only be better than opt。 They can only be smaller than opt。

 So if we can actually compare our algorithm solution to one of these lower bounds。

 then we know we're also can similar compare ourselves to the only worse actual optimum solution So we're going to see this a lot for the remainder of 261。

 this idea where you don't exactly characterize what the optimum is， but you get some handle on it。

 you get some bound on it and you compare the output of an algorithm to your bounds。

 So this is canonal in that sense。And then the theorem。Is that actually this？

Online algorithm does pretty well。Given how strong the benchmark is。So no matter what happens。

Your schedule at the end of the day。 It's not going to be optimal。

 We sort of expected that because we're forced to be online。

 but it's not going to be more than double optimal。

 So you lose a factor2 from not knowing the future。So in online algorithms terminology。

 this is called being too competitive。And then sometimes this number is called the competitive ratio。

Okay， so if the online algorithm is always within an alpha factor of the optimum。

 then we call it alpha competitive， or it has a competitive ratio of alpha。Okay。

So any questions about that before we prove it， proof is not difficult。So what's the proof， well。

 consider the worst load in the online solution， okay？So let I。So again。

 run the online algorithm to completion， and now in hindsight looking at what it did。

 focus on the machine that wound up being the biggest that determines the makepan。

So call that machine eye。And we're going to be interested in the last job that ever got placed on machinech I so in different iterations of the online algorithm。

 different jobs got assigned， we're sort of fast forwarding to the last iteration where some job was assigned to this worst machine。

Aye。No。Now， somewhere， we better use， you know that the algorithm as being at least slightly clever。

 right It's not an arbitrary algorithm。 It's an algorithm。

 which is greedy in the sense that when a job comes up， why did it schedule it。

 where it scheduled it， What's because that job had the minimum load at that time。

 That's the definition of the algorithm。 You schedule something on the machine that currently has。

The minimum load。So prior to Jay's assignment。Eyes load。Was the smallest load at that time。

 right So we're thinking about some iteration with this job。 J gets scheduled on I iteration 117。

 So in a iteration 117， I had the smallest load。 That's why Jay got scheduled on it。

And then kind of the same argument here， but going in the other direction。Well。

 the minimum load can only be less。And the average load。In iteration number 117。Okay。

So you can't have everything bigger than the average。And so this is just equal to。Continue this here。

Well。Let's think about all the jobs that were scheduled prior to this iteration。

So currently we're scheduling job J， so the jobs which have been scheduled so far are jobs one through J minus1。

That is the average load of a machine in iteration 117 just before I get scheduled。Okay。

So what does that mean so that means？So fast forwarding all the way to the end of the algorithm。

The final load on this machine。Is it most what its load was before it got its last job？Plus。

The processing time of that last job that it received。Cha。

So this was an upper bound on before jobb Jay was assigned to it。

 this is the upper bound on after job Jay is assigned to it。So what doleslemmas tell us？

That whatever the job Jay is。The size has to be bounded by the minimum possible make span so our benchmark。

We also observed that the Minm span can't be any less than the sum of all of the processing times divided by M。

So it certainly can't be less than this prefix of the processing times divided by M。

So that's less than not。This is using Limma 1， this is using Limma 2。So that gives us our。

Competitive ratio of two。Okay。So that's a full proof of the theorem。Any questions by of that？

Makes sense。All right。You might be wondering about this too and is it tight。

 so it basically is tight in the worst case， I'll ask you to think about that on exercise set number seven。

 if you make an assumption that the jobs aren't too big。

elative to so sort a lot of jobs and they're relatively small。

 which is actually a pretty common case in practice， then you do do much better than two。So。Yeah。

 again， even in the worst case， despite the fact that you're online。

 you still get within a reasonable constant factor。

 so that's definitely the happy case in online algorithms， Okay doesn't always happen， happens here。

All right， so any more questions for？Hide the proof。Okay。All right。

 so I want to do two more sort of case studies。In the design and analysis of online algorithms。

The first one is going to be about a problem called the Steer tree problem。

We'll talk about that today。And then mostly on Thursday， we'll talk about。

 we'll revisit our old friend bipartid matching， but this time we'll think about it from an online algorithmist perspective。

And there we'll see a very nice。Sort of randomized greedy algorithm。Which does quite well。

And I should say just so you don't get the wrong idea， I mean。

 so in all three of these case studies this week， we're going to be using the super strong benchmark of the best thing you could have done in hindsight or the best thing you could have done with full foreknowledge。

 so that's kind of a brutal comparison， to compare yourself when you only know what you've seen so far to compare yourself to someone who knows everything。

Obviously if you get positive results， it's great， so like for this scheduling algorithm。

 there are a lot of problems where all online algorithms have terrible competitive ratios just because it's too unfair a comparison。

 So sometimes you have to change the model that's one of the themes in my 264 beyond worst case analysis course。

But for 261， what I'm going do is I'm just going to cherry pick a few problems that are quite fundamental problems for which you actually can get good online algorithms with small with good worst case competitive ratios so there are some success stories and that's what I'm focusing on in these lectures。

All right， so now I'm going to talk about a graph problem， the Steiner tree problem。

So the punchline here is going to be that a natural greedy algorithm turns out to be the optimal online algorithm。

 and the analysis is pretty nice and we'll introduce some tricks that we'll use again later when we study the traveling salesman problem。

Okay， so again， it's an online problem， so I have to tell you in what sense the data arrives piece by piece and what decision does the algorithm make each time it gets a new piece。

So there's a bunch of stuff you know， up front。So there's an undirected graph。

And also every edge has a cost。No negative。OK。So this is known quote unquote， offline i。

e at the beginning。What arrives online are terminals。So arriving online one by one。Terminals。T 1， T2。

Up to TK， and these are all vertices， vertices of the graph。

And the way you think about a terminal is the terminals need to be connected to each other。

That's sort of the responsibility of the algorithm at all times， whatever terminals have showed up。

 they should be connected to each other。Now there these edge costs。

 presumably we want to keep them connected as cheaply as possible。Okay。

So that's the standard problem。So， go。Maintain。In a perfect world。

 you'd maintain the minimum cost is's going to be approximate because it's online。Mencro subgraph。

Spanning all terminals。Spanning all terminals so far。Okay。So I say they main cost subgraph。

 but if you think about it， know edges are not negative， so there's never a point having a cycle。

 but you may as well just delete an edge from a cycle you're getting an only cheaper solution。

 So really these are going to be trees。 So it's called the Steiner tree problem。

And so the terminals arrive online， know so in general， maybe in the 11th iteration。

 you have these 10 terminals have showed up， they're already connected to each other。

 the level1 shows up， you have to somehow extend it to the existing infrastructure。So， you know。

 you might want to think about something like a cable company， you know。

 extending infrastructure to a new neighborhood to keep them to connect them when a new market comes。

Emerges。All right， so any questions about the problem definition？Yeah。

The pool itself is defined in one light。Yeah， you're right。

 I'm being sort of sloppy about that I mean so maybe a better way to say it would be I first just define the Steer tree problem in the way that I normally define problems。

 offline problems right just see I give you all the terminals up front and then the goal is just to have the tree spanning them with the minimum possible cost。

Here we have an online version so again we're going to be comparing ourselves to the best solution in hindsight。

 so the best Steyner tree in hindsight， so in a perfect world wed love it if at every single time step we currently have the minimum cost Steynert tree and the current points now that's not going to happen but we hope to be close to that sort of gold standard。

Yeah。So I'm sort of conflating together here the definition of just the normal binaryner tree problem and then the online version that we're studying now。

So any other clarifications， it's a good question。So I'm going to prove a result for what looks like a very special case。

Though it turns out to not be a special case at all。And so it's a special case。

 which is the case of you have metric costs， so what does that mean？So first of all。

 G is the complete graph。Now if this was the only thing I was going to write down。

 you shouldn't be bothered because if you take an arbitrary graph。

 I can just throw in the rest of the edges with a cost of like a billion， it'll be the same graph。

 it'll be complete okay。But actually it seems like a much more significant assumption。

We're going to assume that the edges satisfy the triangle inequality。So what does that mean？

So if you think about a triple of points， really just means that the straightest path between two points is a straight line。

 I a single hop。So we're all triples of points。UVW。

If you go from the classroom from going from U to V。And then subsequently going from B to W。

 that should be at least what it would have cost to go straight from U to W。

So that's the tri equality。So it says whenever you have a two hot path。

 you can replace it with a one hot path， it'll only get cheaper， or by induction。

 if you take any path between two endpoints， you may as well replace it with the shortcut。

 a single edge between those two endpoints， it'll only be cheaper。

So that's what the tri on equality means for us。So for example。

 if you have points in real dimensional space with any norm， Euclidean norm， whatever。

 it's going to satisfy the tring lineality。Something like airplane ticket fares is not going to satisfy the triangle inequality。

 So sometimes you get a cheaper flight by going to an intermediate point。

 as far as the distance traveled。That will satisfy the triline quality as far as the actual how much you pay。

 that will not satisfy this。All right， so it seems like a special case， but it's actually not。

So I'll ask you to think about this in next I said seven。So the general case。

 meaning an arbitrary graph with arbitrary non negativegg costs。Reduces to the metric case。

In other words， if I hand you。A subrtine that is alpha competitive for the metric special case and that's exactly what I'll design for you next so given a black box that solves the metric case you can just use it and to solve the general case with one extra preprocessing trick but I want you to think about that offline so for today just focus that we have these assumptions and we're free to use them。

All right。So again we're just going to look at a greedy algorithm again this might be the first one you would think about so in our third case study I'll show you a case where the algorithm which turns out to be really good is not the first one you'd think about it still has a greedy flavor。

 most things in online algorithms have a greedy flavor because it's not totally clear in many cases what else you could do but again in the bipartide matching it'll be a quite clever greedy algorithm here might well be the first thing you would have thought to write down。

All right， here's the algorithm we're going to analyze。

So initially before any terminals have showed up， remember we have the graph up front。

 the edge costs up front， the terminals come in online。 So before we see any terminals。

 we don't need any edges。 so we initialize T。 this will be our final tree of the empty set。Now。

 when a terminal arrives。For I greater than1， notice that when T1 arrives。

 when the first terminal shows up， we don't need to do anything that sort of spans itself in effect so we don't have to actually do anything until the second terminal shows up。

All right， so now we're in like iteration number 11。 Okay。

 we have these 10 terminals that have already showed up。 We've built some tree spanning them。

We have this 11th vertex that just showed up。 So what we're going to do， we're going to say， well。

 let's look at the 10 previous points。And look at the cost of the edge between the new 11th point and each of the 1 previous points。

 and among all of those 10 options， let's just connect it along the cheapest edge of that form。

 so if 10 terminals showed up before， that's 10 options to connect the  11th12 with a1 hot。

 and we just picked the best of those options。And again， remember。

 we're thinking of the graph as complete。 So there's always a one hot path from any vertex to any other vertex。

So add to T。The min cost edge。Between TI and TJ。And Jay should have arrived earlier。

 okay so with J less than I。Okay。So that's the whole algorithm。

Let me go through a couple of examples just to make sure it's crystal clear。

It might remind you a little bit of a minimum spanning tree algorithm。One of them in particular。

It's a little bit like prims， minimum span tree algorithm。

 That's the one that just sort of starts from a vertex and then grows like a mold。

 adding one edge at a time until it covers the whole graph。 That's prim。

And so here we're doing the same thing， we're just adding vertices one by one， adding oneedgy time。

 the difference is in Pri minimum fe algorithm we get to pick the order ourselves。

So we get to choose the order in which we process the vertices， whereas in this online situation。

 it's a sort of worst case ordering of the terminals。

 we have no control over which ones we see first or second。All right， so some examples。

 so let me show you that this online algorithm is not in general optimal。Okay， so example one。

 so again it's supposed to be a complete graph， so let me show you an example on K4。

So here's one way to draw K4。And imagine the edge weights are two。Around the boundary。And one。

On the spokes。So this we werere given up front。Okay。So now terminals arrive in some order。

So suppose T1 shows up first there。 Again， we don't have to do anything we're sort of spanning T1 kind of degeneerately。

But when T2 shows up， say over here。Now we have to do something。 And actually。

 if you look at the algorithm， it's forced to what we do。 When T2 shows up。

 we just include the direct edge between T1 and T2。The algorithm will always do that。Now。

 maybe and so here， this is fine， we're optimal。But now T3 shows up。So now it's a little ambiguous。

 so according to the algorithm we should either connect T3 to T1 or to T2。

 both of those options have the same cost that we pick arbitrarily， doesn't matter in this example。

 let's say we picked that one。So that would be how the greedy algorithm would execute on this example。

So greedies costs would be two plus two or four， right？Whereas opt would be what？

optpt would be three。Okay。You would just pick the spokes。Okay。

And that would give you a tree spanning actually all four vertices， but whatever。

It turns out to be cheaper to have this intermediate point that connects to all three of them。

Any questions about that？All right， so here's another example。

So let's look at an example that's on K5。So here's one way you can draw K5。Okay。

And suppose these are the edge lengths。ち去去。All right， so let's say T1 shows up here。Okay。

 nothing to do。T2 shows up here。That forces us to take this edge。Let's say T3 shows up here。

Now here there is actually again a tie， so remember the algorithm says。

 well try connecting T3 either to T1 or T2， whichever is cheaper， both of these have cost2。Okay。

So let's say that we break ties by including this one。Obviously。

 you can perturb the example so that this is the unique thing that the algorithm will do。

Now let's suppose T4 shows up here。Again， there's a couple options now it doesn't matter。

 so maybe we pick that edge so we could connect T4 either to T3 or to T2。

 let's say we connect it to T2。And then T5 is up here。And again， there's a tie we could connect T5。

 either to T3 or to T1， both of those would cost one doesn't matter。So let's do that。

So everyone follow that， how the greedy algorithm might execute on this graph。Well。

 by the way I forgot to say this， but so both of these。

 the triangle inequality is indeed satisfied in both of these examples。

 you can sort of trust me on that。Okay， so how much does greedy cost us？We。

 four plus two plus one plus one。Also known as eight。What has opt in this example？Good， it's four。

So you can see that by considering。This path。Optt equals four。So in example 1。

 we were off by a four thirds factor。 in example 2， we're off by a factor of2。 So what do we know。

 We know that the greedy algorithm is certainly not better than too competitive。 Okay。

 Maybe it's too competitive。 We don't know， but it's certainly not better than too competitive。

But actually， it's quite easy to continue the pattern。In the second example。

All right so there's another thing I'll ask you to think about online。But actually。

There's no way the greed algorithm is too competitive。

 it's actually not competitive for any constant factor。Competitive ratio of greedy。Can。

 in the worst case， grow logarithmically。With the number of terminals k。Okay。

And it's really a family of examples for which this is kind of like a base case。

But I'll leave that for you to think about so if you take what's going on in this example and you sort of amplify the idea。

 you can get the gap between greedy and the optimal and hindsight to grow logarithmically with the number of terminals。

Something which is quite a bit harder to prove， but also true， right， So this。

 so this is just stating a lower bound on one particular algorithm。

 The first algorithm we thought of。Really， as algorithm designers， we want to know， okay， well。

 how good is the best algorithm？ we don't want to break just one algorithm。

 maybe the algorithms stupid。So a harder result， but a true result says that every online algorithm for Steiner treee。

 including randomized algorithms， has competitive ratio in the worst case that grows logarithmically with the number of terminals。

So this lower bound actually applies to all online algorithms。

And I mentioned that because that makes the following theorem seem。Rather more interesting。

Which is that this greedy algorithm is， in fact。Log K competitive。看。

So at least up to some small constant factor， greedy is the best online algorithm。

 at least in the worst case， so you can't do better than greedy。Alright。

So any questions before we move on to the。The proof。This proof is a little harder than the last one。

 but still not too bad。Okay。All right。So let's see why G has a good competitive ratio。All right。

 so it's going to follow。From the following key lemma。So for any value of i， the claim。

Is it the e most expensive edge of the greedy tree。Has cost。And most。2。

Times the minimum cost dtry and hindsight divided by i。Okay。

So let me help you parse this a little bit so suppose I equals one。What does that say that says。

 okay， greededy built this tree。Get notice so greedy built a tree that has exactly K minus1 edges。

 right there were K terminals， first terminal doesn't do anything。

 each of the next terminals adds a single edge， so you have a tree with K minus1 edges at the end。

Okay， so this says， well， take eyeicle 1， the most expensive of those K minus1 edges。

 the claim is is it most two times opt。So it's a pretty expensive edge， actually， right？

But then it says， but the second most expensive， that's going to be only opt。

The third most expensive， that's going to be only a most two thirds times opt and so on。Okay。

 so it's asserting this simultaneously for all choices of I。Yeah。So the key lemma。

Easily implies the theorem。Why is that？It says， well， consider the overall greedy cost。

So we just argued the most expensive edge is at most too opt。

The next most expensive is the most stop。And so on。Also known as。Two opt。Time sum。

I equals 1 to k minus1。Of one over eye。Okay。So if you like， think about it this way。

 we're running the greedy algorithm， it builds this tree。 after it's done。

 we kind of look in hindsight at the edges it picked and we sort of sort them in our minds from highest cost to lowest cost。

And these are the upper bounds that we have on each of those edges in that order。

 from highest cost to smallest cost。Okay。All right。So this is a harmonic sum。Probably you've seen。

You may have forgotten， but I'll bet at some point you've seen the fact that this is at most the natural log of K。

 You can prove this just by estimating the sum with an integral。So。That gives us。The theorem。

 assuming the keylemma。Okay。So the competitor assuming the keylemma。

 the competitive ratio of the greedy algorithm is no worse than two times the natural log of K。

Have record that？I owe you the Kilema， obviously。Any other questions， modlo that。Oops。Soir。

Proof of Chilema。So let have a few steps， none are hard， but there's a couple steps。

The first couple of steps are actually this sort of really neat tree doubling trick。

 which we'll use here and we'll use again when we study the traveling salesman problem。So first。

 let me remind you of something that hopefully you saw like back in 103 about olearian graphs and oarian tours。

So suppose you have a graph。Actually not necessarily a graph but a multigraph。

 so this is just an undirected graph where you could have multiple parallel copies of the same edge with the same pair of endpoints。

So suppose H is a connected multigraph。With all even degrees。Okay。So。Maybe it's something like。

And so here everything has degree two， except for the middle vertex， which has degree  four。

 so that satisfies the condition。Then， H。Has an Oular tour。Once it's an oiler tour。

 it's a walk through the graph， it ends where it started。

 and uses it traverses every edge exactly once。Okay。So for example， in this multigraph。

That would be an example of an Oular torque。Okay。So it's clear that the even degree condition is necessary because every time you enter a vertex。

 you also exit the vertex。 So if you visit some vertex K times on an Oular tour。

 it means it had to have had degree 2 k。So certainly the only way you can have an ainator to have all even degree is this is asserting the converse that's actually also a sufficient condition and the proof。

 again， I'll bet you saw this in 103， I'll put it on the exercise set just for completeness but the proof is you really just sort of peel out peel off cycles one by one until you're left with an empty graph。

questions about this？Connected multigraph all even degrees has an oil tour。Okay。

 so how are we going to use this？So step two。And let me remind you while we're doing this proof。

 we're only talking about the analysis right So the algorithm is as simple as。

it's not on the board anymore， yes it is。 see the algorithm is just this。

 The algorithm is dirt simple。 Okay so when I talk about constructing Oular tours。

 we're not doing it in the algorithm， we're just doing in the proof okay。

So consider an optimal standardner tree。Spanning the terminals that showed up。Okay。

 so this is what we would have done in hindsight if we knew all the data and we also had the ability to solve NP hard problems。

 this is what we do。Okay。So here's the doubling trick。So define the graph H again just for the proof。

Two copies。Of each edge。Of T star。Okay。So if T star was， say this optimal tree。

 this was the optimal solution in our first example。

 we're just going to form the multigraph where we double every edge。Okay。

So it used to you have three edges now， it has six edges。Why did we do this？

This is to make it olearian。If you make two copies of every edge。

 every verticeses degree goes up by a factor two， so everyone has even degree。

So H is an olearian graph。Okay。And。And again， both copies of the edge get the same cost。 Okay。

 so you make a copy of an edge you copy its cost as well。Oops， this should be H。

So what's the sum of the cost of the edges in this double graph capital H？Good two out。Okay。

So we started with optt and we doubled it， so we just get two opt。Now， if we take an Oular tour。

Of H so like in this picture， there's lots of ways to do it， but maybe we go like this。

We use each edge exactly once。And so we again have that if we sum over all of the edges in the tour。

 this is still too up because it's exactly the same set of edges as we had up here。Okay。

So that's step two， and again， we're doing all of this only in our minds， okay。

 only as a way to kind of somehow relate some piece of the greedies cost to the optimal solution。

So how are we relating to the optimal solution， where we start with the optimal solution。

 that's a good start。And now we've done this thing where we've made an olearian tour doubling the cost。

So why is that useful？And also， you'll notice at no point yet have I made use of our assumption that we're in the metric special case that the Tri inequality holds。

So this is where we're going to use that assumption。So step three。

Let's run what we're trying to prove， by the way， right so we fixed eye。

And we're trying to say that the I most expensive edge is the most two opt over eye。

 We're trying to say that simultaneously for all eye。

 So here's where we actually sort of zoom in and focus on an eye。So a fixed eye。What S1 SI。All right。

 so when greedy runs what happens at each iteration， some new terminal shows up。

 you build one new edge from that new terminal and some old terminal。 So in that sense。

 every terminal is associated with some cost， the cost of the edge that you use to connect it to previous guys when it showed up So S thrown through S just says well。

 amongst the K terminals， these let's define these as the eye of them with the most expensive connection costs。

So these are the ones where it sort of really hurt to connect them to the tree so far。So terminals。

With the highest connection costs， okay？So again I've reindexed it T1 through TK。

 that's the order in which they arrive， in general the most expensive terminals could be early in the ordering late in the ordering in the middle windows knows。

But just rename the terminals so the this one through SI。

 the ones that were the most expensive to connect to the tree。All right， so here's how we use。

The triangle inequality。 Remember the triangle inality says it says the shortest path between two points is the direct one hot path。

 Again， it's a complete graph， So there always is a one hot path。But differently。

 intermediate destinations can never get you there faster。

So why is it useful to have the tri on quality？Well， what's useful is you can shortcut。

So for example， suppose you have some tour。Okay， so there's eight vertices here。

 the vertices may or may not be distinct， maybe you're visiting some of them more than once。So。

These edges have some total cost。And you can imagine shortcu the tour， we'll do this in a second。

But you could say， well， what if I just pick out these three vertices？

And I just connect them immediately through each other。

 so I splice out some of the intermediate destinations。Well。

 the tringgonality says that sum of the cost of those three blue edges is going to be in most the cost of the eight green edges。

Tangle quality says this will be at most the total cost of this3 hop path。

 this will be at most the total cost of this3 hub path。

 and this will be at most the cost of this2 hop path。Okay。So given a tour you can shortcut it。

 meaning take path segments of it， replace them by single edges。

 and you get a new tour spanning fewer vertices， but your cost has only gone down and notice that would not be true if we didn't have the triangleequ that would be like saying。

 oh well why can't I just change my airline ticket to cut out all of the stopovers well your fare might go up if you do that so it's really about the triequality。

Okay， so what are we going to shortcut？ Well， we're going to shortcut。This tor C from step two。Okay。

So we're going to take C， which is a tour， so remember we started with T star。Okay。

 so T star spans all of the terminals。Plus， maybe some other stuff。

 but it certainly spans all of the terminals。 So S1 through S I are spanned by T star。

 So when we double T star and take the Ouler tour， certainly every one of S1 through S I will show up possibly multiple times。

So， and all we really care about for this part of the proof is S1 through S。

 So let's just take the Oer toward capital C， which includes all of S1 through S possibly multiple times。

 and let's just shortcut it down to a cycle that only spans S1 through S。 and moreover。

We don't really need more than one visit to each， okay？

So we take C and we just replace it by straight edges so that we get a simple cycle with I edges total on S1 through S each appearing once。

So shortcut C tos a simple cycle。Call it C。On the set of terminals S1 through S。

So there's two things you should be clear on at this point and ask questions if it's not clear。

 first of all， this is well defined， that it makes sense， okay。

 that you really can take C and shortcut it to a simple cycle on S1 through SI。 Secondly。

 that in doing so， we get something that has only smaller cost。

 Those are the two things that should be clear to you。Any questions about that？

So it' in short cutting only replaces pass by single edges and triality。

 says that only decreases cost then。What we have is that the sum over all edges in this shortcuted tour。

Is in most too hot。 mayor may not have gone down， but definitely didn't go up。All right。So remember。

 this is a simple cycle。With eye vertices， so it has eye edges。

One of these eye edges has to have cost at most the average。Okay。

So there exists an edge between two terminals column SH and SJ。With cost。At most two opt over i。Okay。

So again， we have eye edges， this is never bound on the total cost。

 So for the cheapest of those edges， we get another bound of this on the cost of the cheapest edge。

Okay。what are we trying to prove， We're trying to prove that the I most expensive edge of T has cost at most to opt over I。

 Now， remember， by definition， the terminals that are connected by the I most expensive edges of T are exactly S1 through S I。

Okay， so what thelemma is asking us to prove is that， well， at least one of the I terminals。

 at least one out of S1 through S I got connected by an edge in greedy。By an edge of cost。

 it' most too up to over， that's what we have to prove。Some of them can be more expensive。

 that's fine， but if we look at the eye most expensive edges。

 at least the cheapest of those should be at most two opt over eye。Okay。All right。Pret much done。

So what have we done？ We've done this big thought experiment。 Okay， what we I mean。

 we've just really taken the optimal solution。 We've massaged it。

 We sort of zoomed in on this one sheep edge。 We haven't connected it to greedy yet。

 All we've been doing is doing thought experiments about the optimal solution。So。Here's the point。

 though。We identified two terminals amongst these first I， S H and SJ。

 so that there's a really cheap edge between them， connecting them directly。

Imagine then that maybe SH arrives first and SJ arrives afterward。What does the greedy algorithm do。

 well when SJ shows up， it sort of looks at every single terminal which already showed up。

 looks at the one hop path and picks the cheapest。So if SH arrived earlier。

 that's one of the options that we can connect SJ2。And we just said that the cost of doing so。

 connecting J toH on the direct edge is the most too upped over eye。

Maybe greedy will connect it to some other terminal。

 but that would only be because that edge was even cheaper。Okay。So summarizing。Whichever of SH or SJ。

 so whichever end point of this edge arrives later。Is connected。In greedy。By edge。Of cost at most。

To opt over eye。Okay。And that's what we were trying to prove。

 so we took the eye terminals that were the most expensive to connect。

 and we argued that at least one of those was connected with a cost only to optto I。

So that completes the proof of the key lemma。 I was arbitrary， so we proof of this in general。

 And remember， we had this short argument about why the key lemma implies the theorem that the greedy algorithm really is O of log K competitive。

So any questions about that？Yeahep。最有点。This was the I had most expected。

Because as H and S J are arbitrary。It was I。expenses。business。Yes。

 what was the question and how do we that between SH and SJ is the I boost。😊，系。は thanて。We don't。

 so what we know is that all of S1 through S。Including in particular， SH and SJ。

 all of us1 through SI were the most expensive ones to connect。So the keylemma is really just saying。

 okay， well amongst the most expensive。Just show me one which wasn't too expensive。

 Show me one which only cost two opt over eye。So I just so obviously you know the cheapest。

 if any of them satisfy this inequality， the cheapest one that got connected satisfies this inequality。

 but from the proof perspective， all I have to do is exhibit to you。

 I just have to show you a proof like here is this one terminal from that those most expensive eye where it didn't cost that much。

 it only cost two opt over I。Okay， so I just need to show you one of the eyes is it works。

 And so how did we do that， So we did this by like sort of dreaming about the optimal solution and what it looks like。

 And we argued that there has to be this cheap edge。

 There must exist some pair of terminals amongst this most expensive eye SH and SJ。

 so that at least those two。Have a cheap edge between them。Okay，Now SH and SJ。

 we don't know that they're the I most expensive。 We know they're amongst the most eye expensive。

 they may or may not be the I most expensive。But that's good enough。

 so both S and SJ are candidate terminals where if they were connected cheaply， we'd be done。

 we'd prove the key lemma。And so how do we argue that one of them is connected cheaply。

 when we just look at the second of the tu arrive？I mean， so for the first one that shows up。

 it doesn't really help them， like if SH shows up first。

 it's not that useful that SJ is closed because SJ isn't there yet。

 but when SJ shows up now it can connect to SH again it may not do so。

 it's the greedy algorithm so it could connect to whoever's closest but SH gives us an upper bound on how close it is to its nearest neighbor among previous terminals。

Other questions？Okay。So this is the last。Proof I plan to do today。

 but I do want to at least introduce you to the problem that we're going to talk about at length on Thursday。

And the problem is going to be online， bipartite matching。

And here there's an obvious greedy algorithm which does pretty well。

But then there's a smarter greedy algorithm， which is actually does better than the。

Simple greedy algorithm and it is actually optimal。

So I'm not going to tell you about that algorithm today， we'll start Thursday with the algorithm。

 but let me tell you about the problem definition and why it's important。So online bipartid matching。

And in this case， again， we're not going to see any analysis till Thursday。

 but here we're actually going to use a dual linear program to get a bound on how good opt could be Okay so this the analysis on Thursday will sort of showcase how the same kind of tools you've been learning to establish the optimality of problems like maximum flow and matching and linear programming are also useful for establishing bounds on the competitive ratio for giving you guarantees on the performance of heuristics。

Okay。So bypartite matching。 And so there's not even going to be any weights。

 there was just going to be max cardinality bypartite matching。 Okay so as we know， offline。

 if we knew the graph up front， this would just be an easy reduction to a maximum flow computation。

This is going to be an online variant， so as usual I have to tell you what do you know upfront。

 what arrives online， and what do you have to do when something arrives online。All right。

 so to bipartize graphs， that there's going to be two sides。

 I'm going to call them LNR left and right。The left side is all known up front。Okay。

So you have a bunch of vertices over here L。And in vertices of R。Arrive online one at a time。

And when a vertex on the right hand side arrives， it arrives together with all of its incident edges。

So it's a bipartid graph， so for a node on the right。

 all of its incident and edges go to the vertices on the left。

So maybe the first vertex in R shows up， maybe it's connected to those two vertices。

 then this one shows up， it's connected to those two vertices， this one shows up。

 it's connected to these three vertices and so on。Okay。So that's the setup。

 I give you half the graph， the left part of the graph up front， the other half comes online。

Now the goal is to do with matching， computer Max Carnelally matching。

 you wish you could delay till the end and just do an optimal matching at the end of the day。

But it's online so you can't。And if you're ever going to match a vertex on the right hand side。

 you have to do it at the time that the vertex arrives。Okay。Now， obviously。

 if it has like three neighbors and all three of those neighbors are already matched to previous vertices。

 then you can't match this vertex。 Okay， so once you match someone， they're matched forever。

 It's in a revvocable decision。 Okay， so if a vertex shows up and it has sort of three neighbors。

 two of them are matched。 but one of them is unmatched。

 then you can match it to that unmatched neighbor if you want。 or if you want。

 you can just not do it and wait for the next vertex instead。Okay。I can go。Max matchup。

So I can just just develop a little intuition for this。

 so here what would be the first thing that you'd think to do。Well。

 here it seems like the obvious sort of the simplest greedy algorithm would just be okay when someone shows up if you can match it。

 match it， otherwise obviously you don't， who do you match it to， I don't know， you know。

 pick arbitrarily， pick randomly， do something okay。

And so to see why that's not necessarily going to be optimal。So imagine you this is L。

 so you're given L up front。Ours arriving online。And maybe r is connected to both of the vertices and L。

So it seems like you should match this vertex， probably， why not？And it says。

 but then you got to pick， am I going to match them to the top or match them to the bottom？

And no matter which one you choose， you might regret it later。系。So like maybe。

You choose this edge to match this vertex on the right。And then。Another one comes up。

And unfortunately， this vertex can only match to the upper left vertex。

And can't match to the lower left vertex。Okay。So now the greedy algorithm stuck the online greedy algorithm。

 right， so there's only one option to match this， but that's already matched。

 so you just lose the vertex。On the other hand， if you knew this was going to be the graph。

 of course you could match everybody， you could have a perfect matching just by picking the two crossing edges。

So this greedy algorithm actually isn't that bad and we'll talk about that Thursday。

 but you can do better， okay so there's a smarter， randomized greedy algorithm， which is really nice。

Okay， so let me just wrap up by。Talking about motivation a little bit。

So the killer app for online bybar type matching。Is web web advertising， or at least these days。

 The problem was first studied back in 1990。 That's kind of when online algorithms was really hot the first time around。

 but you know， because of basically the Internet economy。

 there's been a big resurgence of interest in this problem for the past seven or eight years。

 and actually， the proof I'm going to show you on Thursdays only from 2013。

 So we're still sort of understanding these algorithms better year by year。All right。

 so why do people care about this so much？Well， think of the vertices on the left hand side。

As corresponding to advertisers okay so these are people who have entered into a contract know with a search engine or a content provider or whatever to have their ad shown to people some number of times。

 you know maybe 5，000 times Moreoverover the way it works in almost all online advertising is you can do targeting sometimes very finegrain targeting so an advertiser might say something like I'm going to pay you X amount to show this ad 5。

000 times to mails between the ages of 15 and 25。That's the example。

 I mean they actually get much more fine grain than that too。

 okay and if you think they don't know this stuff about you。

 they do know this stuff about you when you're actually viewing these pages。

So that's what advertisers do。 Okay， so they say show my ad this many times to this particular demographic group。

And so， you， an ads is going to be shown 5000 times， think of there being 5。

000 vertices on the left hand side corresponding to that advertiser， one per ad shown。

And so these are no upfront Okay， so this happens offline people enter into contracts。

 Yeah sometimes people sign new contracts， but that's on a very slow time scale。 Okay。

 so basically you know who the advertisers are upfront on a given day。So what arrives online？Well。

 consumers of these ads。Okay， eyeballs。So who is this。

 This is someone who just typed in a query to a search engine。

 This is someone who just viewed a content page and so all of a sudden。

 you know the a server didn't know that this person existed。

 but suddenly they show up they request a page or they type in a search query and the a server will generally know some stuff from the IP address。

 say or cookies about this person and this corresponds to an edge on the right- hand side。Sorry。

 our have vertex on the right hand side， what are the edges？Well。

 a new eyeball is going to be matched to exactly the advertisers whose's targeting criteria this person matches Okay so if this is a mail between the ages of 15 and 25。

 then itll match some advertiser for which that was their targeted group so in general。

 someone on the right hand side will not be matched。 everybody on the left。

 It'll only be matched to the advertisers that care about that type of person。

any questions about the interpretation？I really have like multiple personal friends at both Google and Microsoft。

 where more or less their full-time job is implementing the algorithm I'm going to show you on Thursday and sort of fine tuning it for their systems。

 Okay so I'm going to talk about this week， even though it's theoretically beautiful。

 It's really practically deployed and making a lot of money for some of these companies。😊，Questions。

All right， well， we went over both times last week， let me let you go early this time。

 see you Thursday。