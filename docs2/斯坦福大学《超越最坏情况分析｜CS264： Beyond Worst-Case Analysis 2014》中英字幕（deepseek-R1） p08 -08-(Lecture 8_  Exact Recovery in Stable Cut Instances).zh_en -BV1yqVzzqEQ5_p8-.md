# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p08 -08-(Lecture 8_  Exact Recovery in Stable Cut Instances).zh_en -BV1yqVzzqEQ5_p8-

The topic for today is what I'm going to call exact recovery in cut problems。

So let me tell you what I mean by exact recovery。This is a topic I actually surreptitiously already introduced you to on Monday。

So in exact recovery， the question you're try to understand is for a given algorithm。

That you have in mind。Figure out which inputs this algorithm works properly on。

 So solves the problem correctly。 Okay， So for what inputs is a given algorithm a。Solve the problem。

 exactly。Our main theorem on Monday was exactly this type of exact recovery guarantee。

 We proved that single link plus plus exactly recovers optimal solutions in three stable K median instances。

 Okay that was the main theorem on Monday。 So I really want to sort of tease out that kind of property and give you some more examples of these kinds of exact recovery results。

 now okay， so what's the motivation for these kinds of guarantees。 So I mean。

 here we're thinking of this algorithm a as something which either we already have access to So maybe like today its gonna to be linear programming。

 Okay， so Stanford has a site license for Cx。 So this is an algorithm we can just run for free。

 We just feed an input， see how it does。 or it's an algorithm which should be very easy to code up Okay。

 so with simple algorithm like single link plus plus So and the idea is， you know。

 and this is really often the case in practice where you designing an algorithm from scratch。

 especially a complicated algorithm with sort of a last resort really， it's much preferable。😊。

something in your existing toolbox suffices for the problem at hand。

 at least for the inputs that you care about。 That's actually how most clients of algorithms actually use them。

 By contrast， not all， but a majority of theoretical research on algorithms kind of says， you know。

 let's try to come up with new algorithms。 you know， which is a lot of fun and really interesting。

 come up with new algorithmic ideas。 often general purpose。

 But here we're really going to sort of take this different approach you know。

 we have our algorithms that we're allowed to use in hand。

 let's understand what kinds of inputs they work on。

 So the theory I'm going to be that we talked about Monday today and then at least one lecture next week。

 all is trying to capture sort of that use case， if you will， formally with formal theory。Good。

So we're going to do another case study today。Of exact recovery。

And it's going to be graph cut problems。 which are quite similar in spirit to clustering problems。

 Okay， you're taking a graph and breaking it into pieces。

The difference is going to be on the kind of algorithm that we talk about。 Namely。

 I really want to talk about just linear programming。 Okay。

 so when does linear programming exactly recover solutions to NP hard graph cut problems。

 So that's the topic today。So， when。Our NP hard problems。So exactly。By a linear program。Okay。

So the answer， of course， is not going to be always because if you don't know this already。

 I'll tell you right now， linear programming can be solved in polynomial time。

 So if we're talking about N be hard problem， we're not going to solve worst case instances of linear programming。

 but maybe we can solve a lot of instances that we care about。 All right。

 we want theory to explain when it works well。So。The segue that I'm sort of doing today is I'm keeping the kind of conclusions that we're gonna be proving similar to last lecture。

 Okay， so we're still gonna to be doing exact recovery for clustering style problems。

 but I'm sort of shifting the algorithm on you。 I really want to start talking about linear programming。

 because it turns out a lot of the sort of greatest hits and exact recovery are for know。

 proving relaxations， linear programming or convicx programs， proving them exact。

 I guess I want to push us toward the direction of understanding linear programs。

 So thatll allow me to next week， Hopefully say a little bit about you know。

 some hot topics like compressed sensing and stuff like that。😊，All right， so similar guarantees。

 but with linear programming algorithms。So the first part of the lecture。

 I just want to give you a relatively gentle。Introduction to how this is going to work。Okay。

So I'm going to talk for maybe the first half of the lecture or so about a problem some of you I'm sure have seen the ST Min cut problem。

 so the dual problem to max flows，So this problem is actually solvable in polynomial time。

 so it's not really the type of problem where you are going to ask a question like this。

 but later on in this lecture， we'll look at an NP hard generalization of min cut and then we'll extend the same techniques to get the exact recovery results that we want。

All right， so。For those of you that haven't seen S Mincut or need a reminder。

 So the input here is an undirected graph。With costs on the edges。

 okay sometimes they're called capacities in this context， and to go with costs。

So positive costs on the edges。And there's a source vertex。And there's a sink vertex。

And the problem you're trying to solve is you're trying to identify。The minimum S T cut。

 So the S T cut， which cuts the minimum total cost of edges， okay。

So this is something you definitely spend some quality time with in CS261， for example。

 for those of you that have taken that class。Okay， so first of all， remember what a cut is。

 a cut is just， you take the vertex set and you partition it into two groups， A And B。

 What makes a cut an S T cut S， this distinguished source vertex should be on one side。 T。

 the single vertex on the other side。 Okay， so little S is in capital A， little T is in capital B。

 That's an S T cut。 And among all S T cuts。We want to minimize。The total cost of the cut edges。Where。

 of course， a cut edge is just one with one endpoint in each of the two sides， one in A and one in B。

So for example， a picture you might want to have in your mind。Would you a graph like this？

So here's S， here's T。So those are the edge costs。 So stare at that graph for a second and try to figure out what the value of the best S cut is and the minimum S cut。

What do you think。Herard a seven， heard a six。I think it's6。So if that's a。And that's B。

 that separates S from T， and it cuts six edges。 And I don't think there's any cheaper one。Okay。

So if you want， you can solve the minimum cut problem using lots of pretty maximum flow algorithms。

 which you study in CS 261。 That's not what I'm going to do here。Rather。

 I'm going to show you how we can just solve a linear program。And the energyteger solution。

 the optimal solution is just going to pop out。 Okay。

 as as the correct as the exact answer to this linear program。

And then we're going to generalize it shortly to MP hard generalizations of this cut problem， okay。

So， I'm going to assume。So we're given an input like this。

 I'm not going to assume any stability condition， anything like that。 I don't need to。

 I will assume that the optimal solution is unique。Okay。So that's like a super。

 super weak version of stability， only one optimal solution。It's not really that important。

 but it'll just make things simpler， right。Now， actually let me ask。

 so how many of you who really knows nothing about linear programming or feels like they know nothing about linear programming。

Okay， a couple of you。 that's fine， good。We won't need too much。

 So just so what I'm going do next is show you a linear program。

 which is meant to capture this minimum cut optimization problem。 Okay， so just is the cartoon。

 I talked， I talked a tiny， tiny bit about linear programming in lecture number one。

 And so remember this this cartoon。 the upshot is you want to maximize linear function over linear constraints。

 So you have a feasible region。Which is the intersection of half spaces。

 So it just looks like a polygon in two dimensions。 And then you have some linear objective function。

 that just means you want to push in some direction as far as possible。

 And so linear programming is just meant to find the point in the feasible space。

 which is as far as possible in the desired direction。 Okay。

 so that's the sort of geometric picture you should have in mind。Now。

So the way you specify a linear program is first， you' got to say what your variables are。

 your decision variables。 Okay then you got to say what your objective function is。

 which should be linear in the variables， You got to say what your constraints are。

 which should also be linear in the variables。 So let me show you such a linear program meant to capture minimum cut。

 or at least a relaxation of minimum cut。So the variables。So。There's going to be。

A variable Xy per edge。And the semantics of X E is that we want X E to be one。

 if this edge winds up getting cut and 0， if this edge is not cut。 That's the intended semantics。

We're also going to have a vertex for sorry， a variable for each vertex。So here， the semantics are。

 if D V is 0， that means we're thinking of V as being on the source side， the S side of the cut。

 If D V is one， then it's on the sink side of the cut。So those are the two variables。

 two sets of variables。Allright， so what are the constraints。Well， certainly。

 S better be on the S side of the cut。 Okay， so we fixed D S at 0。 That's tethered there。Similarly。

 T better be on the sink side of the cut。 So that's tethered at one。

 The other D values are allowed to range freely。And then we want to say something that。

We want to constraint。Which says that if U and V are on different sides of the cut。Okay。

 if the vertices U and V are on different sides of the cut。

 and there happens to be an edge between them， well then that edge gets cut。 Okay。

 so I'll show you the constraints that indicate that。So for all edges。With end points U and V。

We have a pair of constraints。Which says Xy is at least。D minus DV。That's the next E。

N Xc is also at least Dv minus D。Okay。So this is just saying。

 Xy is at least the absolute value of the difference between D U and DV。 Okay， I wrote it this way。

 so it's obviously linear in the decision variables。

The point here is that if one of the D's is 0 and the other is one， this forces the x to be1。

 So if the nodes are on different sides of the cut， it forces the edge to be cut。

 which is what we want。All right。And then with the decision variables。

 I hope it's kind of quite clear。What the objective function is going to be。

So Xy just is supposed to denote whether the edge gets cut or not， the objective function， of course。

 is to minimize the total cost of the cut edges。So the objective。Just sums over all of the edges。

It looks at whether or not that edge got cut， and if it does get cut， if this is a one。

 then you pick up its cost C。And you want to minimize this。All right。

So that's a linear program whose intent is to capture the minimum cut problem。And you know。

 it's at least a partial success in the sense that if you show me an ST cut。

 that certainly naturally induces a feasible solution to the linear program。

 you show me the cut that sets A and B， I'll set all of the d's equal to zero for vertices A。

 I'll set the ds equal to1 for the vertices B， and I'll set x is to be 01。

 depending on whether the edges cut is not cut or cut respectively。

 okay really by definition of you know we've basically engineered this linear program so that cuts would give you feasible solutions。

But now， remember。The feasible solutions to a linear program， they're not just a bunch of discrete 0。

1 points out in space。 Feasible regions of linear program look like this。 Theyre like convex sets。

 Okay， so they include other stuff than just the things that we had in mind and just the sort of the 0。

1 vectors for cuts。 They have， in particular， fractional solutions， okay。And so at linear program。

 you optimize over the entire set of feasible solutions， the fractional ones and integer ones。

 the ones we。Care about the ones we don't care about。 and you get whatever you get。

 You get whatever is optimal。Okay。So the concern always with when you try to formulate discrete problems like a cut problem as a linear program is that when you solve the linear program and you get the optimal solution。

 it's not meaningful。 Okay， it doesn't actually correspond to a discrete solution。

 It corresponds to some fractional thing that you can't interpret。I mean。

 we know for many of programs that there's one optimal solution that is。嗯。I don't know the correct。

 I that basically an extreme solution。 So okay， would be right and therefore， and therefore。

And therefore there's no guarantee that that's not fractional either in general。

Okay general in general， no， well， here， I wouldn't expect you to necessarily know anything。

 but I'm going to prove something about it。 Okay， so in general。

 when you formulate linear programming， you know， you intend for them to be formulations。

 but frankly， they' relaxations。 Okay， they include stuff beyond the just integer solutions you're trying to capture。

 And so when you optimize over the linear program， you might conceivably get a fractional solution。

 which is not what you want， which really just doesn't correspond to a feasible solution of your original optimization problem。

 okay。However， okay， well， first of all， so facts。And again， this is something you just。

 even if you don't know why this is true， all of you should know this is true and remember forever that this is true。

So in fact。Linear programs can be solved efficiently。 Okay， that's true， both in the practical sense。

 with the appropriate commercial software。 And it's also true in the theoretical sense in the sense of polynomial time solvevability。

 Okay， so you should know both of those things。So， con solve LP。In polyton。Okay。

It's not essential that， you know why。 okay And in fact， frankly。

 most people who use linear programming， both in practice and in theory， treat it as a black box。

 and don't know a lot about the why。 Okay So know， if you're feeling very keen by all means。

 learn more about it。 Okay you know， there are people who are experts in this， and， you know。

 it's useful skills。 But a lot of people just use linear programming without actually understanding it。

 And that's that's a totally acceptable and normal thing to do。

 And that's what we're going to do in this class。 needless to say。

There's some other great classes at Stanford， where you can peek under the hood and see how these things actually work。

 and those are fun as well。Okay， but so here's the claim。

 So the claim is that the optimal solution to this linear program。

Is not something that we can't interpret。 It's not fractional， in fact。Is integral。Okay。

So we just write down this LP， we just stick it into our favorite LP solver and out pops on a silver platter。

 this unique optimal cut。So we just run this algorithm。

 which presumably someone up has coded up and engineered very well。

 and it just gives us exactly what we want， I that's a pretty sweet guarantee， actually。O。

So any questions before。I start explaining why this is true。 This isn't obvious。

 And the proof is not that long， but it's not， it's not an obvious statement。Right， I meant to say。

Just to illustrate sort of like what fractional solutions might look like on that graph over there。

 you know， imagine in this graph。You set all of the X subBs equal to a fifth。In this graph here。

So you could， for example， set D here to be a fifth。D here to be two fifths。

 the D value here to be three fifths and the D value here to be four fifths。

And you can set all of the Xs equal to 1/ fifth。Okay。

That would be an example that satisfies all of these inequalities。And it does not， know。

 doesn't correspond in some obvious way to a cut。If it feels like kind of a superposition of a few cuts。

 that's good intuition。 It is。 okay， but it's not obviously a cut， okay to have all these fractions。

Okay。So the proof of this claim is pretty neat， actually， I mean。

 there's a bunch of ways to prove it。But this has always been one of my favorite ways to prove it the way we're gonna show you now。

 But， and then it's also going to generalize nicely to N N B hard generalizations。 Okay， as a bonus。

😊，All right， so let's have some notation。So C star is going to denote the optimal min cut。 Okay。

 so this is the optimal integer integral solution。Okay， so this is really a partition into A And B。

And F star is going to be the edges。That are cut by sea Star。So there's a partition into A and B。

 these are the edges of wood and one endpoint on either side。All right。So， some notation。

So now for an arbitrary S T cut C， So some other partition into A And D。

I'm going to define Delta of C。Okay。Now， C star is the mint cut。 It's the cheapest。 Okay。

 so every other cut is at least as expensive。Delta of C is just a formula for how much more expensive C is than C star。

Okay， it's some kind of symmetric difference formula， okay。So why is C more expensive than C star。

Well， presumably。There are some edges。That are not an F star。

 meaning the optimal cut doesn't cut these edges， but C does。Okay。So this is the extra cost。

 in some sense， that C is getting hit by， which C star is not。Now， on the other hand。

 we got to give this cut C a rebate for any edges which the optimal cut C star is cutting and C is not。

Okay， so we subtract off an analogous term。If the optimal cut does cut E and C does not。

Then we have the corresponding rebit。So this is just the amount by which C's cost exceeds。

C stars cost。So a very simple observation just because C star is the unique optimal cut。So obviously。

 Dlta of C star is zero。Both of these sums are vacuous。And any other cut。

This is going to be strictly positive。Right， because we assume C star is the unique optimal cut。Okay。

 that's really just some notation。 okay， Delta。How much worse other cuts are than C star？Okay。

So now I want to do the same thing。With respect to the optimal LP solution。

 So this was all about cuts。 Okay， there's no linear program over here。

 There's just about cuts and graphs，Now， let's think about feasible solutions to learning a program。

 which， as we saw， you know， can have fractions。 Okay。

 the x's are in general fractions between their own one，right。

And I want to write down sort of this same Dlta， okay。But， but let me just point something out。 Okay。

 so if， if we're talking about the optimal fractional solution。

 the optimal linear programming solution， now， all of a sudden。

 the optimal fractional solution is only going to be better， only going to be cheaper than C star。

We agreed that every cut。Induces a feasible solution to this linear program。 Okay。

 so every cut in particular， C star is one of the feasible points。

And this linear program is optimizing over all points， including in particular。

 the one representing C star。 So it can only be better。 It can only be cheaper。 Okay。

 so now I'm gonna to write down another deelta term， but it's actually going be nonpoitive。

 right because the optimal fractional solution can only be better than the optimal integer solution。

So similarly。So suppose we solve this to optimality。So we got our X hats and D hats。

 that's what makes this as small as possible over the whole feasible region。 that's a D hat。

So optt LP solution。And so now we define。Delta of x hat in exactly the same way。 Okay。

 so it's the extent to which x hat is more expensive， even though we know it's actually cheaper。

 So this is going to be non positiveitive， more expensive than the integral solution C star。

So we have these two analogous sums。So we say， well， first of all。If there's anything that's。

The optimal solution doesn't cut， so it incurs zero cost on this edge E。Meanwhile。

 our fractional solution X hat incurs some fractional costs where it contributes。

The corresponding term to its objective function。Okay。

 so these are edges on which the optimal min cuts C star incur 0， and we incur whatever we incur。

 according to X hat。Now， the other term。You say we also get this rebate， though。

So for any edge which the optimal， which C star cuts。

 that corresponds to sort of an x value of 1 to the extent that R x value is less than1。

 we get that difference back as a rebate。So again， it's C toB。

One is basically what the C star is paying。So the extent to which x hat is less than one。

 That's a bonus that we get。 That's a rebate。Okay。So that's just exactly the same computation with a fractional solution instead of with cuts。

 these individualteger solutions。And we already discussed。Why。It must be the delta of x hat。

Is it most zero？C star is one feasible solution。 X hat is the optimal feasible solution。

 It can only be better。 So Dlta can only be non positive。So that's going to be， that's two。All right。

So that's kind of the boring stuff， relatively。Here is what's pretty cool， alright。

So how am I gonna remember what we're trying to prove， Okay， we're trying to prove that actually。

 the optimal solution is going be integral， and it's gonna to be an algorithmic proof。Okay。

So I claim。That there exists a randomized algorithm。That takes as input， x hat。

So it takes in this possibly fractional solution X hat。And then it's going to output an S cut。

 a random S cut。 So a randomized algorithm，And。Here's the property that that distribution of SDD cuts is going to have。

Okay so C here is a random variable， it's a randomized algorithm。Such that。For all edges。Alright。

 so again， for a given edge， because the cut is random， sometimes the edge will get cut。

 and sometimes it won't depends on what exact cut capital C this algorithm spits out。

But the fraction of the time， the probability。That C cuts。Yi。Is going to be exactly。

The LP solution value， X hat E。Okay。So these x hats are between 0 and 1。

 but the sort of like the di fractional extent to which they I just cut in this LP solution。

 And I claim that I can exhibit a randomized algorithm。 I have to show you what it is， obviously。

 but I claim I can exhibit a randomized algorithm。So the distribution of the cut satites the property。

 the probability in given edges cut is exactly the fractional cut value， if you like in the LP。

 Ex X hat。And of course， that means in addition。Obviously， the probability of the compliment event。

That he is not cut。That's going to be just one minus the probability that it is cut。

 so the probability it's not cut is just one minus x hat E。

So that follows immediately from the first statement。So let me show you why， assuming the lemma。

We're done。 Okay， I want to show you that the lemma implies the claim。

 Then I'll show you the algorithm， which proves the lemma。And the reason I'm emphasizing。

This argument， the part of the argument， which is going from the lemma to the claim。

 this argument we're going to copy almost identically in the more general setting。 Okay。

 so the algorithm itself will have to change nontrivially。

 So the proof of thelemma will look quite a bit different depending on the problem。

 But this argument I'm about to show you， will just sort of extend very easily。

 so this is this is the argument， which you should be ready to see a second time later in the lecture。

So proof that dilemma implies the theorem。So suppose we actually constructed。

An algorithm with this property。So， here's the intuition。 Okay， so we're trying to prove that。

 you know， the fractional solution has to be this unique。You know， this unique min cut。 All right。

 So we have two things working in different directions。 Okay， we have one。

 which says every integer cut has positive delta except for C star War at 0。

But then we also have this fractional solution where the deelta is non positive。 Okay。

 so in some sense， here， the fraction solution is better than C star。

So if we have a distribution which matches the linear program。 Okay， that means basically this。

 this randomized algorithm is averaging over a bunch of S T cuts。 You know。

 a bunch of integer solution C gets a randomized algorithm that spits out a cut。

 That means it's a distribution over cuts。 integer cuts。We know that every single integer cut。Is。

 you know， only worse than the optimal one， Strly worse unless it's actually C star。 Okay。

 On the other hand， this Lima kind of says that our distribution。

 our randomized algorithm is doing an exact simulation of our linear programming solution。

 And the linear programming solution is at least as good as the integer solution。Okay。

So that basically saying that this distribution has to be a point mass of probably one on the unique optimal cut。

 Okay， Anything else would give us a contradiction。So that's sort of the， you know。

Very high level idea。And the proof really just formalizes those couple sentences， right？All right。

 so let's look at the， right， So we have this distribution of cuts。

 this randomized algorithm that sps out a cut。Let's calculate， on average。

 how much worse this cut is going to be than the optimal one C star。 Okay， We know it's， you know。

 it's either going to be C star， or it's going to be something strictly worse。 We know that。Well。

So here's Delta C。Okay， so by linear of areaity of expectations。The expected value， okay。

 remember what's random， Okay， C is what's random， The cuts C。So by linear have expectations。

 this is very simple to calculate this expectation。 Okay， we can just do it term by term。

So we have a sum。Over the edges that sea star does not cut。Of the contribution， if we cut it。

Times the probability that we， meaning our randomized algorithm， cuts it， so C cuts E。嗯。

So that's just looking at the probability that that predicate is actually met。Same thing here。

For the second term， we say， okay， well。What about the edges that were cut by C star？

Whenever we don't cut it， we get the rebate， so we want to know what's the probability that our randomized algorithm spits out a cut which does not cut each。

So that's just linearity of expectations applied to this。Equion。Now。

 the Lemma tells us that a randomized algorithm cuts an edge with probability exactly equal to the linear programming value。

嗯。So， this。Is X hat E。发个万了。Okay。Similarly， it says the probability that we don't。Cut an edge。

Is exactly one minus the linear programming value for that edge E。 O， so again， by dilemma。

This is1 minus x hat E。Okay。But having done that substitution。

 we now see that expression is exactly what。Still on the board。M就嘅呢种基。不道理。Delta of x hat。

 what we have on that middle part of the board is exactly deelta x hat。

Which we observed is non positive。Because the fractional solution is at least as good as the optimal。

 best optimal solution。Okay。So all of this is in most zero。And this is by two。Allright。

 so let's remember。 So what what have we done。The dust is settled。

 this says the randomized algorithm。Spits out a cut。Which， on average。

 is at least as good as the best cut。The randomized algorithm spits out a cut that on average is at least as good as the best cut。

How could that possibly be true， Okay， There's one best cut。 Everything else is strictly worse。 Okay。

 so if you give me a distribution of cuts， which is as good as the best cut。

 it has to be outputting the best cut with probability 1。Okay。

 any probability on any other strictly worse cut would make the average strictly worse。So。

It outputs C star。With probability one。All right。Now， this isn't quite what I claimed。

 I claimed that the LP solution you started with has to be integral。

 Once I show you this randomized algorithm， it'll be obvious that the only way that randomized the algorithm would ever deterministically always do the same thing is if you feed an integer solution。

 Okay， so I'll leave that for you to think about outside。

 Okay So the fact that it always this randomized algorithm is actually deterministic means that X hat has to be integral。

Okay。So any questions about that？And so this deterministic part is probably coming from the fact that we're assuming that。

The afternoon。Yeah， I mean， so the theorem I'm proving is still true anyways。

 so I'm actually proving a stronger statement here。

 which is that the only optimal LP solution is integral。

 So if you have multiple optimal integral solutions then by conity。

 convex combinations of them are also optimal for the linear program and those are fractional solutions。

 So in general， what's true about min cuts is that basically you've got a bunch of vertices corresponding to the minimum cuts and then any of their convex combinations are also know optimal for the LP and that's it So there some face of the cut polytop which is optimal。

是。Alright， so I owe you the algorithm。So， proof of lemma。A proof sketch of lemma。

So what is this magical randomized algorithm that outputs it always outputs an ST cut and the prop it cuts a given edge is exactly what the LP says it should be。

 Here's what it is。😊，Okay， so remember what the remember the linear programming solution looks like。

 Every vertex has a D value。 Okay， it's between 0 and1 and 0 means we're on the source side。

1 means we're on the sink side for a general solution might be somewhere in between。

And then you have these X hats， which is the extent to which the edge was cut。Okay。

So here's what the algorithm does。You start S and you blow up a balloon。Okay。To a random radius。

Between zero and1。And the S side of the cut is just whatever is captured in your balloon。

And the sink side is whatever else there is。That's the whole argument。So， pick。A radius。

Strictly between0 and1。Uniform or random。Set the source side of the cut to be。

The vertices such that D hat V is at most are。Remember。The D value of S is 0。

 So that certainly goes into a。 And also T T is at one， and R is less than one。

 So T certainly goes on the opposite side。So this is certainly an ST cut with probability1。

And I'll leave it for the homework that you check this works。All right。It's quite simple。

So if you take a given edge， that's say a 02。Is its x value。

 It's cut exactly 20% of the time when you pick this random radius。Also。

 to fulfill a previous promise， I said， you know， the only way that the randomized algorithm is going to be deterministic is if you feed into an integral solution。

Okay， that should also， certainly if you do this easy exercise， it's also going to be clear。

 if you have， if it's not an integer solution， that means there's some edge， which is， you know。

 has a value of like 01。And that means there's going to be some values of R where it gets cut sorry。

 there's going to be some value of R where one endpoint goes to the S side。

 and there's gonna be some values of R where that doesn't happen。 Okay。

 so as you vary the choices of R， you really will see distinct cuts。

 So if any fraction means you can have multiple different outputs from the algorithm。

 That means if you have a constant output of the algorithm， it has to be integral。

Any questions about that。Alect。So this is not， I mean， this is not a new result。

This kind of stuff has been known for really 50 years， probably。But let me show you how we can。

To a very， very similar argument。And prove that for an NP hard cut problem。Okay， so a harder problem。

 but under a more stringent assumption。 So not just a unique optimal solution， but more generally。

 a stable instance， we can again， get exact recovery by just solving a linear program。

So the more general problem is called multiway cut。And it's all exactly the same。

 except instead of just having one source and one sink， you now have some number of terminals。

 and there's going to be three or more。Okay， so before we had two terminals， one we call the source。

 one we call the sink。 Now we're going to have K terminals where k' is at least three。

 Everything else is exactly the same。So， input。Undirected graph。Costs。And you have terminals。

T1 up to T K。Okay。And the goal。Is a cut。 So what's called a multiway cut。

So you're going to have a partition of the vertex set now not into two non empty groups。

 but into K non empty groups。And now， instead of just having a so side and a sink side。

 you have one group corresponding to each of the K terminals。Okay， so TI and Si。For all I。Minimizing。

To로。Cost of cut edges。So now in general， you're going to have a T1， you're going to have a T2。

You're going to have a T3。And you're responsible for slicing up the graph。Into three parts。

There should be exactly one terminal in each of the parts， and again。

 an edge is cut if itss endpoints are in distinct parts。

 you' going to minimize the total cost of the cut edges。This is MP hard even for K equals 3。

 This is MP hard even for K equals 3。What's the intuition by and why it suddenly becomes hard。

It'sNot clear how you're making the flow price。始に。Yeah， well， I mean， yeah。

 So you sort lose a bunch of things at once。 It's hard to there's。I mean， it's of similar to saying。

 you know what's the intuition for Y is2 S and P and 3 S NPP hard。

 it's kind of a hard question to answer。I mean， so certainly one thing。

 like one way you could convince yourself something's going on is you could play with some small examples and observe that the analog of the maxfilm and cut theorem doesn't hold once you have three terminals。

 That's probably how I would start developing intuition about why something more complicated is going on。

Yeah。Okay。Good， so this is MP hard even for K equals 3。

 So we're not going to just write down some linear program with no assumptions and expect it to solve to an integer solution。

 that's just not going happen。 Instead， we're going write down a linear program at a stability condition。

 And then we actually are just going solve it。 And the integer solution will just pop out。 Okay。

 that's what's gonna happen。 So harder problem， stronger condition。 we get the same result。Allright。

 so the stability condition we're going to use。Is the same one we studied on Monday。

So it's going to be this one where we think about we basically imagine as a thought experiment perturbing the input。

 you here the input being the edge costs。 We're going to be allowed to blow them up by up to a factor of gamma。

 And we want the optimal solution to remain invariant no matter how we twiddle with the edge costs。

 Okay， so it's different than a week ago。 but it's really exactly the same as Monday。So it's again。

 game of stability。So， opt。It is invariance。So here opt， I really mean， you know。

 the integer solution。 Okay， so the minimum cost multi way cut under。

Perturbations of the form CE goes to Sigma E， C，E。Where Sigma E is in between one and gamma。不的。

So on Monday we talked about camedian instances， we had this metric。

 we were allowed to blow up distances back to a gamma factor。

 here it's the same thing just on the cost of the graph， of the edges of the graph。And remember that。

 you know， the bigger we take gamma， the more restrictive this condition is。

 and the fewer instances we're talking about。 So the tractability can only increase as we make gamma bigger and bigger and bigger。

All right。So here's the theorem。And this is recent， this is just from earlier this year。Mkaarav。

 Makkaaraachev and the Ja of Raavvan。From an algorithms the main algorithms conference January this year。

So。For all gamma stable。Multi weight cut instances。With Gmma greater than4。The LP solution。

 of course I haven't told you the LP， but I will tell you the LP so it'll be an LP。

 and the theorem is going to be that the optimal solution to this LP is， in fact。

 the stable multiway cut instance， so it does solve to an integer solution。

So that's what I want to prove for the rest of the lecture。So， that's very nice。

So I an help get what you want。A couple other comments， I guess， so multiweight cut， you know。

It's natural to study it just you know as the generalization of the very famous S and cut problem。

 it also， it does show up in applications in various guises。 So like image segmentation。

 so if you want to model an image as a graph and you want to break it into different regions that's often solved by modeling it as a multiway cut problem。

 Okay， So if you have a belief that there's like four regions。

 then you have the four terminals corresponding to the regions。

 and basically the four parts of your multiway cut。

 correspond to the pixels of your image that you're ascribing to each of those four regions okay。

Can you give us a sense of what the barriers are。So as far as like， how far can you go。

 as far as I know。Not much is known about that， actually。I was wondering that myself。

So unlike the Kameian example where the upper and lower bounds are pretty close。

 I don't know that anyone's thought about it much。 So that would be interesting。

 I mean would so if someone wanted to do maybe a theory project。

 this paper has a lot of other results too， so you could talk about the other results in this paper and also maybe think about what would lower bounds be for this multiway cut example。

Yeah， I'm not sure。Yeah， it's really。I could imagine for being the right answer。

 or I could imagine it being a small number， Im really not sure。

I'll put a link to it on the course page。 Yeah， Yeah， In fact。

 I think there's already a link on the course page to it。um。Okay。

 so that's that's the result I my cover。 Any questions。Right。

 the proof is going to follow very similar lines。 Clearly。

 something is going to have to be different because we need to make use of our stronger hypothesis。

 We need to use the stability assumption。 We're also going to need a different rounding algorithm。

 because the rounding algorithm has to be a little bit more clever， okay。um。The randomized algorithm。

So that's going to be the main difference。All right。All right。

 so I need to tell you what the linear program is。And this is this is a quite nice and natural generalization the one I already showed you。

So again， we have variables saying the extent to which an edge is cut。

So we're going going to have these D values。 The semantics are going to be slightly different。

This is going to be for all vertices and for all I equal 1 up to K。So for vertex V。

 DIV is meant to say the extent to which。This vertex has been assigned to the Ih group。

 So in an integer solution， we're gonna have this K way cuts。 We're gonna have these K groups。

 So for a given vertex， we're envisioning all of its D values being 0。

 except exactly one will equal to1。 If it's in the Ih group， then its D IV values equal to 1。

 It's DJ V values equal to 0 for J not equal to I。That's what we have in mind for these D values。

 So if you like， its sort of like。You know，Uary coding of which group youve got assigned to？Allright。

 good。 So constraints。Well I guess first of all， the objectives is the same as before。

 that's easy enough。Xy is whether the edge got cut or not， and we pick up the cost CE。

Each time and it just cuts。So how about the constraints？The constraints are sort of interesting。

So first， what's clear？Good。Is that remember， the I terminal better be in the I group。Okay。

 so in the same way， we had S tethered and T tethered。 Now。

 were going to have all the terminals tethered。So。For all， I。

 T I better be assigned to group fully okay。Also， it better be the case that every vertex belongs to a group。

 at least fractionally。So if you sum over all of the groups you could be assigned to。

That should equal one。嗯。So again， in our dreams， for a given vertex V。

 exactly one D values one and the rest are 0。 Okay's just indicating which group is's a part of for a linear program。

 we need these linear constraints。 We need real valued variables。

 So this is sort of the best we can do。 We' just going say the sum of the extent to which youre assigned the group should should be 100%。

Good， and so now we need an analog。 So before we have these constraints。

 would say that the extent to which an edge is cut is at least the difference in its Dvalue on opposite size。

 But so X E was at least D U minus D V， and X E was at least D D minus D U。

So we need analogs of that。 and so these are slightly more complicated。So。

We look coordinate by coordinate。And we have a notion of sort of how far two vertices are apart in a given coordinate。

 and then we sum up over the coordinates。Okay， so why you should be at least。

So this is for an E E within points of UVv。Yeah， so we have two of these。And of these flipped。Okay。

 so again， this is just， we have two constraints just basically saying this y value should be at least the absolute value。

 Okay， right it this way。 So it's obvious it's linear。And then at the end of the day， finally。

 we say the extent to which we call an edge cut is just the sum of these y values。

 the extent to which they're cut across each of the coordinates。Actually， I need to change this。

 I need to do something slightly different。Okay。But this is basically it。So how do you。

 how did you think about this， Okay， well， again， remember。

 whenever you're trying to interpret the linear relaxation， think about， okay。

 what are the intended semantics for an integer solution， Okay。

 always anchor that and trying to parse these things。So the intendedix semantics would be， okay。

 well， you know， suppose you have a vertex that's in group 7 and another vertex。

 which is in group 10。 That means the edge between them got cut for sure， right。

 So we want the fact that they have they're in different groups to force us to set X E to be equal to 1。

 Okay that's what we're trying to accomplish， Allright。

So what does it mean that a vertex is in group 7， it means that all of the D values are0。

 except it has a one in the seventh coordinate， and then its mate has a one in the10th coordinate and zeros everywhere else okay。

So that means。There will be exactly two coordinates when I equals 7， when I equals 10。

 so that this difference is one or the max of these differences is one。Oh。

So that means when I sum this up， I get two， actually。So something's a little off。

But here's a quick fix to that。Just do a half。Why don't we just say that Xy is greater than all YE optimizeized？

Well， if that would be weaker， we could， that would be legitimate。 But if you think about it。

 this is going to be， this is sort of a stronger constraint once you're dealing with fractions。

 right， So you know， the sum is bigger than the max。So basically。

 we want to force the linear program to keep the x's high。Okay so the bigger。

 legitimate lower bound we can write down on the x's。

 the stronger we expect the linear programming relaxation to be， in the sense。

 the smaller the gap we expect between whatever the LP solution is and the integer solution。

But you're right that if you only focus on 01 variables， then you may as well do max instead。

Allright， so again， y， y 1 half， all this stuff。 it's because， you know。

 in the canonical case where these are zeros and ones， this sum is going be equal to  two。

 Ex the two。 you know， you get contribution of one from each of the two groups that the endpoints are present in。

 You cut it in half， you get one。All right。So that's good。

 So this says whenever you're assigned to different groups， you're forced to be cut。 And similarly。

 if you're at least sort of fractionally assigned to sort of different groups。

 it's again going to force the edge between you to sort of be cut。 Okay。

 so you're going to pay for the edges some sort of prorated basis based on how different the labelings of your endpoints look like。

Okay。All right， so that is the linear program。Any questions about that。I mean。

 another way you can sort of think of this， which is maybe useful。Gemetrically。As you can imagine。

That in this linear program， instead of assigning， so in the integer problem in the discrete problem。

 you want to assign each vertex to one of the three groups。

Think of the three groups as corners of a simplex， of a triangle。Okay。And so basically。

 what's going on is in the linear program。We can't get away with forcing each vertex to be assigned to one of the corners of the simplex。

 We allow the linear program to assign a vertex anywhere inside the simplex。Okay。

So that's sort of a way to interpret its labeling。 So when K equals 3。

 a given vertex gets three values，3， DV of 1，2， and 3。

 you can think of those as being a coordinization of a simplex。

So it's a geometric way to think about what it's doing。The real problem is I give you a graph。

 you want to assign the number 1，2，3 to each of the vertices。 What can you do in polynomial time。

 You can assign a point in the simplex to each vertex。And then what this is all saying。

 this is saying that you're going to pay。 so when you assign vertices to points in the simplex。

 the further apart they are in the simplex， the bigger fraction of this edge you're going to pay for。

 pay for cut okay， and this is some kind of basically L1 norm of where you put the two endpoints in the simplex。

 That's another way to think about it。Questions。So in that sense。

 we probably still have a guarantee that there is in。In这个。We just can't necessarily。He solve。No， so。

 right。 So， so the the facts still hold。 So we can still solve this linear program in polynoial time。

So without without assumptions， it's not going solve it to an integer solution。 And actually。

 on the homework， I'm gonna to ask you just know to get a better feel for this， know。

 look at a concrete instance where the LP actually does strictly better than the best integer solution。

 But in some sense， we know this morally automatically because this is an n hard problem。

 And we can solve the LP and polynoial time。 So we don't， I mean。

 we just know it's going to be wrong sometimes And here for a linear program， what wrong means。

 this is does too well。Right so it's going to do at least as well as the best multiway cut。

 but it has the potential to do even better， but by making use of these fractional solutions that we have no media use for。

Okay， so the magic here is we're going to say， okay， in the worst case。

 certainly the LP will be strictly better。 Okay， it'll have a。

 truly fractional optimal solution under you know。😊，Somewhat reasonable stability condition。

 The gap goes away guaranteed。 Okay， that's that's the magic here。 So really， I mean。

 so the way you should think of it is。You know， this theorem is really the exception that proves the rule。

Okay， so when you're talking about， you know， most problems that we care about， you know。

 outside of a few， you know， just very happy positive results like， bipartite matching， Max flow。

 etc cetera。 know， linearar programs generally are not guaranteed to do what you want。

And so this is great， so we can actually guarantee that you just solve them and don't have do anything else。

It's a very happy day。O。All right。So I'm going to approve， any questions？All right。

 so there'll be a part of the proof which。Mirrors fairly closely what we already did for minimum cut。

So I'll go through that， but I won't belabor it unless there are questions。

Because it should be the second time you're seeing it。 And then again。

 what we have to do differently。Is the rounding algorithm。

 we' have to do something smarter than that idea where we just blew up a balloon with a random radius。

 All right， That's also the algorithmic piece。 So my guess is， you'll find it the most sort of。

Clever and intriguing。All right， but so。All right， it's proof。All right， so notation。

 So it's going to be the same。Same gist。 but we somehow have to make use of this stronger assumption that it's for stable or better than four。

So here's what I'm actually going to do。Is motivated by the fact that we're assuming for stability。

 Remember that what that means。 Okay， that means even if we perturb things by a factor 4。

 theres opt stays opt。 It's still better than everything else。 Okay， now actually。

 here here's sort of a simplifying intuition。 You can keep in mind。

 the stability conditions kind of a little hard to get a feel for initially because it talk about all perturbations。

 right， But actually， if you think about it， if you think about like cuts。See like a three way cut。あ。

There's very strong intuition for like， so suppose you wanted to prove that this wasn't for stable。

 Okay， so suppose this is the original optimal solution。

 And I wanted to exhibit a perturbation to convince you that this wasn't for stable。Theres actually。

 it seems actually kind of intuitive of which perturbation you'd probably use。

Or the first one you'd try。So remember， what you' not to do with perturbation is you allowed to blow up costs。

 the objective function is to minimize the costs of cut edges。

So the really kind of adversarial thing to do would be， all right， Well。

 if this is your optimal solution now， I'm just going to look at the edges that you're currently cutting。

 I'm going blow all of those up by a factory gamma by the most possible。 Okay。

 so I'm gonna to hurt you as much as I can。And meanwhile。

 you're going to leave everything else exactly the same。Because， right。

 this wouldn't hurt you and would hurt your competitors。 Okay， So in some sense， actually。

 there's a strong intuition that， you know， and there'll be a homework says about this。

 which is the perturbation you should think of is just blowing up the cut edges and opt by gamma。

 And that's sort of the relevant perturbation， okay。So that's going to motivate how I define this。

So basically what I going to do。 it used to be that we had that so our old assumption was just that there was a unique opt。

 So not not only is there a unique opt， but it's still opt even if we blow up all of the costs of its cut edges by a factor 4。

Okay， so I'm just going to write that down。 It's going to be the same expression as we had before。

 except with the extra four in it， reflecting this kind of worst case perturbation， okay。All right。

 so first， I don't spent you in remember the exact details， but this is what it was。

So again this is supposed to say how much so this used to be how much worse is C than C star。

 now it's how much worse is C than C star after we blow up C star's cottage edges by a factor  four。

So for the stuff that C star does not cut， we don't blow it up。 So there's no four here。

 And this picks up an extra C， E。Whenever C cuts an edge that the opt did not。

 so that's extra cost for C。And then over here， we have this four。Okay。

So this is summing over edges that opt did cut F star。

 These are the ones that we blew up by a factor of gamma， gamma bigger than4。

 So I'll just use four here。And this E is not cut。F see。好像。So this is exactly what we had before。

 except there's this coefficient of four in the second term， otherwise it's exactly the same。

All right， so homework。Just making precise intuition we just said。Which is the Vgama stability。

AndI mean， this is pretty much immediate。But。I think it's good for you to just make sure you solid on it offline。

So for every cut， let's see。 So for C star， this is0 because again。

Both sums are vacuous when c equals C star。And for anything else。

 it's strictly positive by gamma stability。Okay。Because C star beats C even after you've blown up the cost of all the edges in F star。

So that's one thing。 And this is sort of where we're encoding the stability constraint。

 The next thing we did is we said we wanted to do something similar for the LP solution。 Okay。

 and for the LP solution， we're not going to have the。 Okay。

 so the LP solution is just do the same statement as before。

And the definition is actually exactly the same。不来。Okay。And again。

 because the LP solution is at least as good as the best multiway cut。

 the multiweight cut is one feasible solution for that linear program。

 the optimal solution can only be better。This again， for exactly the same reasoning， is non positive。

Okay。So Delta x hat is just saying how much better for the LP objective function value is the fractional optimal than the cut C star。

 and that's non positive。Allright， So now here's the， here's going to be。The new lemma。 And remember。

 the lemma is what talks about algorithm or randomized algorithm，So what did our old lemma say。

 Our old lemma for just the min cut problem said， look， I'm going output a random S T cut。 Okay。

 so a distribution number cuts so that the probability of an edge getting cut is exactly what the LP says it should be。

That was our old le， every edge was cut with exactly the probability that the LP wanted it to be cut with。

We're not going to be able to prove that now because if we could prove that lemma。

 then we'd get a polytime recoverability result without the stability constraint。Okay。

 so that's too strong。 It's empty hard problem。 Okay。

 so we don't expect that exact same loan to be true。

 We're hoping that that lemma relaxed in modest ways is true。And it is， that's the case， all right。

So what's true is there exists a randomized algorithm。呃。That outputs with probably one。

 the feasible cuts。Multi weight cuts C。And。Right， so such that for all edges， two things are true。

So what did we say， what was our old lemma， Okay， the probability that you cut the edge is exactly x hadi and therefore。

 the probability that you don't cut an edge is exactly 1 minus x haddi。

 So we're just going to have versions of both of those statements that are off by a factor 2 okay。

So the probability that C cuts E。Before this equaled x hat E。

The new statement is it will be bounded above by two times x hadty。 So it might be more。

 but only twice as big。And， secondly。Okay， so notice what this would imply is just that the probability that is not cut is lower bounded by 1-2 times x haddi。

 It turns out that that's not going to be good enough for the analysis we're about to do。

 So we want a better lower bound than the probability that is not cut。

So the probability that E is not cut。So before this equaled one minus x hat E。

 And now we're going to argue that it's at least。That same factor divided by two。

That's a two on the bottom。Okay。So notice that does not follow from one。 Okay。

 what follows from one is a lower bound of 1-2 x hat E。 this is a different lower bound。🤧Okay。

So let me again show you why。Given the lemma。We're done。So why does the lemma imply the theorem？

So it has exactly the same。It's exactly the same as before， basically。

But let me show you the calculations。So basically， the four is going to cancel out these two factors of two that we lose。

So let's compute the expected extent to which the multiway cut output by the randomized algorithm is better than the optimal one after we've blown up the costs of F star by factor 4。

So again， just by lineard of expectation， we can just analyze that term by term。

So some over the edges not cut C E times probability that C cuts E。

Minus sum over the edges that C star does cut。C，E times the probability that E is not cut。

By our random multiway cut。Okay，s see there's a four there。 Sorry， forgot the four。

This is an important for。All right， so again， that's just。Linniary of expectations。

Applying the lemma。Part one。This is the most two x hat E。Right。Flying thelemma part two。

So we're shooting for an upper bound here， just to be clear，So for the positive term。

 for the positive term， we want an upper bound。For the negative term， we want a lower bound。

 so we're subtracting something smaller So overall， it's bigger。

So this we have a lower bound of1 minus x hat E quantity over two。Okay， by lema part two。All right。

That just plugging in the line。And so what do we have。

 so we pick up a two in front on this first term。We pick up a one half here。

 which cancels one of those。So down here， we got a minus2 sum over E。AndF star C， E1 minus x hat E。

Also known as。Two times deelta of x hat。Last I checked double a non positive number was still a non positive number。

So the expected extent to which the random output C is better than C star is nonpo。Okay，But again。

 every single output。Okay， is。You know， thats， you know。

 it's strictly worse than C star unless it's actually C star。 So the only way this can happen。

Is if with probability 1， this randomized algorithm outputs the stable optimal multiway cut C star。

 And again， once I show you the randomized algorithm。

 it will be clear that the only way it's going to have a constant output is if you fit it in an integer solution in the first place。

So it means that the optimal LP solution X hatt had to have been integral。So questions about that。

Yeah， so in some sense， you know， where does the stability condition rescue us that allows us to absorb the fact that we can't perfectly mimic the LP in some distribution of our healthy weight cuts。

 we lose a factor two in upper bounding the cut probability， a factor two and lower bounding。

 the uncut probability and the stability factor of four kind of absorbs both of those。All right。

 so what is this randomized algorithm？So this is， again， very simple。

 but this probably isn't the first one you'd think of the first one you'd try。

 whereasas the balloon growing  one， I think for some people， it's maybe the first one that they try。

 okay。So Im going to， I'm going to tell you what it is and leave the analysis to the homework。

So algorithm for the limma。And so， again， we're given。The X hats。Which willll ignore actually。

 in the Dhas。I guess remember every vertex。Is assigned to a point in the simplex。Okay。

 so it has three coordinates， if you like。The extent to which it belongs in the I group for each value of I1 up to K。

 Okay， so that's sort of the input to the rounding algorithm， to the randomized algorithm。Okay。Now。

Here is the randomized algorithm。So initially， all vertices are unassigned。If you want。

 you could seat it by assigning the terminals to the appropriate groups。

 but it actually doesn't matter。 Okay， so just think about all the vertices assigned。

So here's what you do。 Okay， you're going to do a loop until everybody's assigned。

And in each iteration， you're going to do a random experiment which may or may not assign some of the vertices to some of the groups。

 okay。In each iteration。Of this loop， you're going to make two independent random choices。 Okay。

 one choice will be a threshold， very much like our random radius for the minimum cut case。

 the S cut case。 The other one will be a random group。

 which is who you're going to assign labels to in this particular iteration。Okay。

So you choose a group。Between1 and K。Uniformally at random。And you choose a threshold R。Again。

 uniformly random。Okay。And then。You look at all the vertices which have not yet been assigned to a group。

Okay， now let'ss just remember this。 right， So suppose of a vertex V。

 I'm looking at like group number 7。 So I'm looking at like D sub v superscript 7。 All。

 So remember the semantics， the bigger that number is the greater extent to which we fractionally assigned it to the seventh group。

 so the higher that Dvalue， the more the LP suggesting it should belong to the seventh group。

 Okay And we want， you know， you look at our deta for this rounding algorithm。 It means also that。

 you know， the probability that we wind up assigning this vertex to the seventh group。

 also better be going up。 Okay， with its Dvalue， Allright。😊。

So that suggests saying you know the higher it devalue in this coordinate。

 the more likely it should be that it gets assigned to this group。

 so let's just use this R as a threshold and just say as long as you beat the threshold。

 meaning you're above it。You get to go to this group。So V unasigns。

And the extent to which V is assigned by the linear program the group I。Is at least R？Then， assign。

VE to the I group。Okay。So， that's the algorithm。So it's definitely going to output a multi way cut。

Remember that the terminals are fixed to have these kind of basis vector coordinates。

 So the terminals are one and the I coordinates zero everywhere else。

 That means the only group they can be assigned to is know， the one they're supposed to the I group。

 okay。It's not obvious that it satisfies these two properties， but it does。 Okay。

 it's not that hard to prove。 Okay， so that's why I want you to think through it。

 just to make sure it sort of makes sense。 So imagine you have an edge。Uv。

And say in this linear programming， this alleged fractional solution。

 the coordinates look like one half， one half0， let's say k was three。And one third， one third。

 one third。Okay。And just sort of， you， this is a randomized algorithm。

 So a lot of different stuff can happen。 Okay， so just before we adjourn。

 I just want to mention a little bit of intuition about about what can happen， right。

So we're interested whether or not this edge gets cut or not。 Okay， and this。

 this is saying we want to have like pretty good control in the property that gets cut from either side。

 okay。And basically， it gets cut。Right， so so if one of these gets one so a certain label and the other one doesn't。

All right。So for example， if the random choice of I equals 3。When you're like that， okay。Well。

 if we choose the third coordinate， Okay， then there's no way U is going to be assigned to group 3 because its value is 0。

 There's a one in three chance that B gets assigned to group 3， okay。And so if that actually happens。

 if we wind up picking R， the threshold to be below a third， then indeed V gets assigned to group 3。

 and we're sure that this edge is going to get cut。 definitely So whenever coordinate3 is chosen。

 either neither vertex gets assigned or the second one is assigned to a group that the first one will'll ever be assigned to。

On the other hand， maybe we choose R equal to a half。Okay，And then V doesn't pass the test。

 And then this edge lives to survive another day，And now maybe on the next day。

 randomly we re chooseose I， and maybe we choose I equal 1。Okay。

So now a couple of different things can happen。 Right now we have one half and a third。

One thing that could happen is we choose R strictly below a third。Okay， and then in one fell swoop。

 both U and V are going to be put in group 1。Okay so there's no way this edge is going to get cut。

 it's safe forever evermore。Because you only get labeled once。On the other hand。

 we might choose R strictly between a third and a half。Okay， and then that's pretty dangerous， right。

 So that says V， that's sorry。 that says U gets labeled1。 V doesn't get labeled。

 So maybe it'll get lucky。 It'll get labeled one later， but that's sort of a， you know。

 unlikely chance。 It could happen， but you wouldn't want to count on it。On the other hand。

 maybe you choose R to be strictly bigger than a half。 Neither one gets labeled。

 Let me just start the process all over again。 Okay， So there's these different ways that， you know。

 that things can get resolved for this edge。 It turns out， you know， if you think about it， you know。

 a few lines of probability prove that actually the cutting probability and uncutting probability are both tightly controlled around what the linear program wants them to be。

 And so the fact that you losing only a factor two and either one is what gives you the force stability of result。

One final comment about why this is cool。So there there's this big cottage industry of linear programming rounding algorithms so you have an NB hard problem and the traditional approach which is also useful in practice often is you solve a linear relaxation it has some fractions and then you do something maybe stupid or maybe clever around the fractions into integers and hopefully it you don't lose too much so maybe you had a fractional solution。

 you round some things， you get something which is 10% more expensive but now it's an inger solution so there's lots of algorithms which kind of use roundings to transform fractional solutions into integer ones。

A key ingredient of these theorems were these rounding algorithms。Okay。

But notice they're not our algorithm。Right，Our algorithm is solve the LP and declare victory。

 Okay So these rounding algorithms， know， which again， people have been developing machinery。

 you know， for understanding these rounding algorithms for decades。

 We're actually now just using them in the proofs to explain why LP solve exactly in stable instances。

 which is a， you know， pretty neat thing。😊，Alright， so I won't be here Monday。

 but I'll see you for a double header a week from today。 Have a good weekend。

