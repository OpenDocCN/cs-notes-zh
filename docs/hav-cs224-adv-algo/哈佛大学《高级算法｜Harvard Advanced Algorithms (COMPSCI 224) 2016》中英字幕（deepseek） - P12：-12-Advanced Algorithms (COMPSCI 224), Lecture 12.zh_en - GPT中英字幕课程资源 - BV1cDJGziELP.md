# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P12：-12-Advanced Algorithms (COMPSCI 224), Lecture 12.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/8639b0c41a701c41a0ba9ee7f1e8425e_0.png)

Okay， so I'll get started。I sent an email， but just in case someone didn't see it。

Next week we're having two guest lectures， one on Tuesday one on Thursday。

 the Thursday one will not be recorded。So if you want to see that lecture。

 you should be here in person。Okay， so today I want to wrap up with approximation algorithms。

We're going to finish FP tasks。This is we're going to do it for Napsack。2。

We're going to look at F Praes。I'm going to do this for DNF counting。And then three。

We're going to look at semi definite programming。And we'll look at max cut。And if we have time。

 we might look at one other。Application as well。Okay。So let's get started。

 So last time we saw with Napsack that there was a PT。a PA just means for any fixed epsilon。

 you can get a one plus epsilon in approximation， for an Napsack。

 I guess a one minus epsilon in approximation。And your running time is a polynomial in N if epsilon's a constant。

But with an FP task。We want to say that your dependence on epsilon is also。Polynomial， okay so。

So we want to。Polly。And one over up san。Depenence。Fornapsack。And I think actually what we'll get is。

Today。We'll just see it's a very simple algorithm， It'll get you n cubed over Epsilon。

1 minus epsilon approximation。Okay。Do you have a scribe today？Yeah， okay。

I did some searching around to see what。The best known bound was for Napsack。呃。So。

It's possible to get。With a different algorithm。A running time of n times log one over Epsilon。

Plus winter uppson to the fourth。This is due to luller。And。79。

I searched around a bit to see if there was anything after '79 where someone improved this。

 but I couldn't find things， maybe I just didn't search hard enough。A。So yeah。

 there you go for if you're want a final project I'm。Yeah。Yeah， okay。So。Good。

 so let me show you this algorithm。So this is an idea that。嗯。It gets used a lot in FP ta。

 which is so the idea is rounding。So remember the setup。Okay， we have N items， we have anapssack。

 first of all， a Napsackack。Of size W。Capital W。And then we have N items。With weights。

W1 up to WN and also values。V1 up to VN， remember， and the goal is to pack this knapsackack。Don't。

 don't overload it。 you can't put。More than W total weight in the K Napsack and the items that you put in there you want。

 you're going to collect the sum of values of those items and you want to get as much value as possible。

So the basic idea is。Well， what do we know？We know that there is an algorithm with running time。AndV。

So we mentioned this last time this is via dynamic programming where here V is just the sum of the VI。

Unfortunately， this is not polynomial time。Because the running time depends on the sizes of the numbers。

 as opposed to logarithms of the numbers。 Okay， writing down a number V only takes log V bits。

 So the input。Is exponentially smaller than the potentially。So the trick is just to make these small。

Okay。To get a PTTA， what are we going to do？We're going to define new values。

We're going to set v prime。It's equal or VI prime。To be。N over epsilon。Times。VI over Vmax。

And let' it let's floor it， so that it's an integer。Okay。And then。Run。An O of N V prime algorithm。

That's going to give us a set。This is going to be an exact algorithm for the new values。好 right。

And that's going to give us a set of items， which is the optimal thing for this new set of values。

 and the claim is just if you use that set for the original problem with the original values。

 you'll get at least1 minus epsilon times opt。Okay， so I'll justify that for you。

 but what's V prime here？Or any bound on V prime。Capital D prime。And it's got to rhpsilon。

 right thing。This thing here， we have v prime is at most。N times the max over I of V prime。And well。

 V I is at most V Mac certainly。 So this is at most1。 So this is that N over epsilon。

 So this is at most n squared over epsilon。So this running time is at most what I said N Cubaub Eon。

 so that's all theres to。AndThe basic idea is something fairly simple， so what's the basic idea？Okay。

First of all， we know。That opt prime by opt prime， I mean， opt the value of opt in the new problem。

 Okay， after you change these values， opt prime is at least。Vmax prime。Right the maximum value。嗯。

The maximum value of the VI primes。And one of the items actually has。Value Vm。Right。

 so that item will have。At least n over epsilon value。Okay。

But how much value did we lose in any given solution？In this new rounded problem。Well。

For each item in a set， we rounded down its value after this multiplication， right。

 So by rounding down， we at most decreased its value by one。So I mean。

 the basic idea is I'll make this more formal。After rounding。I mean。

 if there was no rounding if we just multiplied by some scalealar on every single value。

 then opt doesn't change， Every set just has the same multiplicative factor times its old value。

But by this rounding， we potentially lose one from every value。So after rounding。Any set。

 let's call it S， a subset of the items。Loses。At most。S， which is at most n value。Right。

Which is at most。Epsilon Times Ops proton。All right。So。

Let's just now make it's a little very slightly more formal， so claim。If Dp。Un roundunded。Instance。

Returns。Some set。A。Okay， which is subset of n。Then。The value of a。Is at least one minus epsilon opt？

The， if you take the original valuation and compare to Op of the original problem。So proof。Okay。

 what's the proof of that？Well。For all sets。S， what we said over there， S subset of1 to n。

We know that。The value。If you look at so。Let me write like this。Alpha， so the value prime of S。

Is at least alpha the old value of s minus the size of s？And it's at most alpha times the value of S。

Where。Alpha is the scaling that we're doing。And over epsilon times Vm。Right。

That's what I just said over here， we lose at most the size value。So。Like。A star。Be some。Optimmal。

Set。For the original NApsap problem before rounding。

So what do I want show I want to show a lower bound on the value of a。What do I know。

 Well I know that the value of a。Is at least。1 over alpha times the value prime of a。Right。

That's just that inequality here。And then I know that a is the optimal solution to the new valuations。

 right？ So this is certainly at least one over alpha times that V prime of a star。Okay。And now。

 now I want to go back toward optt for the original problem。 So v prime of a star。

 this is true for all set。 So in particular， it's true for a star。

 V prime of a star is at least alpha v of a star， which is opt minus the size of a star。

 So this is at least。Alpha times， so this is v of a star， which is opt。This is opt。Minus。Alpha。Times。

呃。Or one over alpha， sorry。Times the size of a star。Okay。嗯。And。That's certainly at most end。

So this is at least。Opt。Minus n over alpha。Which is equal to， which is at least opt。Minus。Epsilon。

Times v max。That's just the definition of alpha。And now Vmax Op is certainly at least V max。Okay。

 so that's it。So are there questions about？About this F task。Okay。There are no questions then。

Let's be done with Napsack。And。Before I move， actually， before I move on to F presses。You know。

You could ask。When can I know for sure that there is no FP tasks？Right。

 not every problem has an F P task。 Okay， so， for example， for set cover。

 we know you can't beat log n approximation， not just because of integrality gaps。

 but there's actually a proof that unless you can solve S really fast， which we don't expect。

 there's no。There's nothing better than a lawn and approximation。Sometimes for some problems。

 you know， you can't beat it to approximation for vertex cover。

It's known that there's a fixed constant。I forgot exactly what that constant is。

 but it's bigger than one that unless p equals NP， you can't beat that approximation ratio。

And there's also some more recent evidence that says you can't beat it to approximation if you assume some conjecture。

But okay， but sometimes they're just kind of。Easy reasons why there's no FP tests。Okay， so。

You don't always have enough PT tests。And let's give it a very simple example。So bin packing。Okay。

And bin packing， what's the input， there N items。With sizes。S1， S2 up to SN。

 and all those sizes are in the range from。Z to one。Vins。Have capacity。Exactly one。

And then crossed the goal。Is to pack。All items。Into。As few bins。As possible。Okay。

And you can't cut items up， either。You have to put an item fully into a single bin。

People have questions about the problem statement。So it's known that bin hacking。

 as I've stated it here， is NP hard。 Okay， and the decision problem， the decision problem of。

Can you pack these items into even two bins？Even that problem is NP complete。Okay。So question。

Given what I've just told you， do you expect to have an FP task for binpacking？

You should use that most one plus epsilon times the optimal number of bins。

So what would an FP test for impactpacking mean？Okay。So an FP task。

And your run time to find this packing。Is polynomial？In end。As well as one over epsilon。

Do you expect to have an FP tasker bin packing， why not？Okay。That uses fewer than but why can't you？

是。Yeah。Yeah， right， so the point is， so the reason。So we don't have an FP task。Unless。P equals NPp。

 What's the proof of that？If we had FPTAS。Run it。With Epsilon much less than1 over n or something。

And the point is the error in the number of bins you use will be less than1。

 and we know the number of bins you use as an integer。Okay， so if I tell you。

 there is a packing z using at most 2。2 bins。 Well。

 then you know that there's a packing using two bins， right， So you can。

 you could have solved that decision problem with an FP task。

 and it would have been a polynomial time algorithm。Okay。You don't always expect to have an FP task。

And I guess the term that's used when you don't have an FP task is that the problem is strongly NP hard。

嗯。Good， so that's all I want to say now about FP ta。And I want to move to F presses。Okay， so F press。

 so2 F press。It's like an FP task。But you know the algorithm。Is randomized。And has， you know， some。

One third chance。Of failing。To find。A good solution。At most of one per chance。

So I want to give you an example for this as well。Which is DNF counting。

So maybe people remember what CNFs are。From threeat or sat。So CNFs are。Formula is written。

 So it's called conjunctive normal form。 DNF' DD stands for a disjunctive normal form。

 What does it mean， It means that you have some clauses。 So an input， what does an input look like。

It looks like a clause， I'll say what a clause is in a second。

 a clause C1 or C2 or dot dot dot or CM。And a clause some C looks like some。X。

 J1 and X J2 and whatever and X JR， and some of these might be negated。Yeah。And right。

 the satisfiability problem for DNFs is。And CFs， you sort of flip where the ans and the O's are so in a CNF you would and a bunch of clauses and each clause would be an oe of some number of literals。

in DNF you reverse that。And we know from。You know。We know from the Cook Levin theorem。That S。

Is an NP complete problem？So sat at least is NP hard。How about the decision problem I mean。

 the decision problem for set is if you're given a CNF formula。

Does there exist in assignment to the variables？Which causes the formula to evaluate to true。

How about for DNFs， if I give you a DNF and I ask you， is there。

 I there an assignment to the variables which makes this thing true。Is that hard？Now。

 why is that not hard？Well。一。Solve any clause。 So this thing is satisfiable。

 if and only if at least one of the clauses is satisfiable。

 and then you can just go loop through clause by clause and just check that， you know。

 basically it's satisfiable as long as you don't have X and not x somewhere。Right。Okay。So。今呢。

Satisfiability， that problem。Is in P。 There's a polynomial time algorithm for that。

 That's a pretty simple algorithm。 How about。DNF。Counting。Given a DNF。Do want a DNF formula。Count。

The number。Of satisfying。Of satisfying assignments to the variables。Okay。

 do you expect that to be easy？Any thoughts？入だとお。Nation。Yeah， yeah， exactly。

 So if you could count a number of DNF solutions， you could solve set， right， because if you have so。

This is a hard problem。To do it exactly。So the proof that it's hard。

Is that if you have a SAT formula？Let's say you have x1。And NX2。And explore something。Whoops。

 this is。This is a DNF。Let's see if a set formula looks like that。And you have some other thing， X5。

Or not x1 or whatever。Right， so you want to know。You want to know whether or not this thing is satisfiable。

 this is your input for SAT。Well， if you could count the number of solutions。

And then then you would know whether or not it's satisifiable because you would know whether the number of solutions is zero or not。

RightSo how could you count the number of solutions to this CNNF formula， Well， you could negate it。

 just negate the whole thing。Right。And then this just become the negation of a CF is a DNF。Right。

 so notice that C1 or。C1 and C2 negation is just equal to negation of C1 or。Nigation of C2。Right。So。

If you have a CNF， so here you have a CNF。This is now a DNF。And you could have lots of clauses here。

And if there are n variables。😡，Well， if the number of solutions to this DNF。Is。T。

Then that means the number of solutions to the negated CF is T。

 which means the number of solutions to the non negated CF is 2 to the n minus T。Right， so。

If you could count the solutions to the negative， then you're counting the solutions to the original thing。

Does that make sense？So。Solving the counting， the exact counting problem for DNFs is NP hard。

 in fact， it's even harder than NP hard。 it's what's called Sha P hard。In fact。

 there I'm not going to dwell much on this， in fact， there's a complexity class。Sharp P。

And the complete problem for Shape is counting the number of solutions to SAAT。Okay。And。

And DNF counting happens to be complete for that class， DF counting。Is Shark P complete？

Sharp is like number， so it's like counting， yeah。I mean， that's where that name came from。

But it's a class that contains NP。Baasly， so for people who have taken some complexity course and have seen the formal definition of NP。

Right in NP。嗯。NP is the class of problems where there's a witness that's verifiable in polymial time and P in Sha P。

 you want to count the number of witnesses， basically。

It's an even harder problem than finding a witness。Okay so this is a pretty hard problem。

But you could ask ourselves， well。Can we count？Number of。Solutions。It's a DNF。Up to one plus epsilon。

So I'm not going to get the exact number of solutions to DNF。To the DNF counting problem。

 but I'll get it up to。I'll get some number that's at least one minus epsilon times the true number。

 and it's at most one plus epsilon times the true number。Okay。Notice that。

It's not immediately clear that we can't do this， right？

The proof that counting DNF was hard really relied on the exact count。Right。We said that。Basically。

 if we could tell whether the number of solutions to this CF is0 or not， then we would have solved S。

 but if there was some multiplicative error here， then we can't distinguish 0 from non zero。唔。So。

And the answer to this question is yes， we can。There's an F press。Due to。Cart。Luy。And Madras。

What year is that op press let me Cha 89？And that's what I'm going show you。You mean a deterministic。

Counting。Yeah， I should know this。 I， I don't。Think so。 But let me。

Let me look into that Oh like like is it hard for some complex would it imply collapses of complexity classes if that happened？

嗯。I don't know off the top of my head， I'。I'll look into that， I'm not sure， yeah。Yeah。

Can we also have them？这在早人。Yeah。Okay， so that's a good question。 I mean。

 you can ask the same question for Napsack。So in Napsack， let's say that the values are integers。

And the weights are also integers。But we have an F task。 so why is that？

RightWe know that the answer for Napsackack has to be an integer if the values are integers。

Right so why？Does anyone have an answer，W why can we have an F test for NapsAC？

So let's say that the max weight， let's say the max value of any item is Vm。

 We know that opt is certainly not bigger than n times Vm。

So what I'll do is I'll set Epsilon to be much smaller than1 over n times Vmax。I'll run my FP task。

 It'll give me some number with fractional error， and I'll just round it to an integer because I know the answer has to be an integer。

Right， so what'？Sorry。It's not polynomia， why？Right， yeah。Right， exactly。 So it's that same issue。

 right， So with Napsack， the problem is that you don't want to run in time proportional to the numbers。

 You want to run in time proportional to the description of the input。And to write down。

 Vmax takes log Vmax bits。 So you would have to set Epsilon to be too small。

And Paully went over up sloan wouldn't cut it。Okay。

 and it's the same with DNF counting it's a similar thing。 You can have DNFs where the DNF has size。

 n or something。But the number of solutions to that DNF is exponential in N。So imagine a DNF。

Which is x1 or x2 or x3， et cea。It has exponentially many solutions， right。

 The only thing that's not a solution is if all the x's are false。

So it has two to the n minus n solutions。 So if you wanted to get that answer accurately。

 you'd have to set Epsilon to be1 over that。And then poly went a revon would be exponentially big。

Okay。So。So the idea behind。You know， the way that we're going to get started developing this carp B Madrass algorithm would be to。

 you know， to try out the first thing that might come to mind if I tell you completely randomized algorithm。

 right， but there's going be a problem。 And then we're going have to be we have to。

Use that clever trick to get around that problem。So。What's one way to。嗯。Randomly estimate。

The fraction of so there are two to the n assignments， let's say there are n variables。And M clauses。

Sam。Of。The two to the n。Variable assignments。Satisfy。Our formula。Our DNANF formula。Let's say。

Let's say a P fraction。So really what we want to do is we want to estimate P。Right。So。

AAre people with me？Okay， so how would you estimate P？Yes， sample a random assignment。

 a uniformly random assignment。Check whether or not it satisfies your DNF。

And do this a bunch of times and take the empirical mean。

 or take see what empirical fraction satisfies your DNF。Okay， so what's wrong with this algorithm？

Theresの那。Yeah。Right。If p is very small， and the fact if p is 1 over 2 to the n。

 so there's only one assignment， you're not going to see a satisfying assignment。

Unless you sample exponentially many assignments， right， So， So a bad example for this。

Is know what if the clause？What if your DNF formula is just。X1 and x2 and dot dot dot and xn。ok。

There's only one assignment， and you're not going to see it。 You're going think the answer is 0。

 unless you。Do exponentially many samples。So really， the problem is that P can be small。😡。

So the trick in this F press that I'm about to show you。Is to rig things。So that。P is not too small。

Okay。So here is let me just call this。其我。So okay， so what does KM do？Okay。来。S I。Be the set。

Of assignments。Satisfying。Satisfying clause I。And now set U to be let you， let's say B。

Seent B to B the union over all I from1 to M of Si。We want to estimate。The size of B。

Up to one plus epsilon， okay？Now。Dfined B prime。To be。嗯。Or should I put this？The set of all pairs。

I comma X。Such that。Assignment X。Satisfies。呃。Cause i。Or if you want to think about it， I don't know。

I wanted to write it explicitly。 so you know what I'm saying， I think some people use this notation。

 the disjoint union of SI's。Okay。Each satisfying assignment is not written just once in the set。

 It's written multiple times， once for every clause that it actually satisfies。Okay。Okay。So。Notice。

That。So a question。We want to estimate the size of B。

 Is it easy or hard to estimate the size of B prime？嗯。WaitIn in this right， I mean， in general。

 I give you a DNF。Even an arbitrary DNF， which is an ore of a bunch of clauses。

 a clause is just an and of some literals。And I want you to compute or estimate the size of B prime。

You don't have to be shy， you know， just yell it out。I see a nod。Okay， so。Explain your nod。Right。

 yeah， so the point is。The size of B prime。Is the sum。Of the size of S， where I goes from1 to M。

And what's the size of S？This is just2 to the n minus。嗯。Number of literals。In the CIA。

So for the literals that actually appeared in the I claws。

You know what you have to set them to to make this and evaluate to true。

And then all the other n variables you could just set to whatever you want。

Or all the other n minus number of variables you can set to whatever you want。Okay。

 so the point is we can actually compute the size of B prime exactly very quickly。😊，So now。

 instead of estimating this P。Let's estimate。P prime。

 which is the size of B over the size of b prime。And then once we get that， once we get this。

 we'll just multiply it by the size of B prime， which we know。

 and then we'll get the size of B up to some error。Okay。So。What's the lower bound on P prime。

 The problem before was that P prime could be too small right。

 So now what's the lower bound on P prime。Can P prime be too small？1 over M， right， so P prime。

Note P prime。Is at least1 over M， right？Each assignment in B。Appears at least once in B prime。

 and it appears with multipleity at most M right， So B prime is at most an M factor larger than B is。

Okay， so P prime is not too small。And now， how can I give me an algorithm to estimate P prime？😡。

So what we want to do is we want to pick somehow do something similar to what we did before。

 which didn't work， pick a random assignment。And then reject and then reject it if it's not in B。

The problem is that a totally random assignment。It's probably not in B。

Or the chance that it's in B is really small。So。Instead， what do we do？

We need to pick a random element of B prime。And check if a random element of B prime is in B。Right。

a pick。A random。Element。Of the prime。And check。If it's。In B。Well。

Checking if it's in B is sort of a weird thing to say because。

Kind of the types of the elements of B prime and the types of elements in B。 When I say type。

 I mean in programming languages， right。嗯。An element of B。Is。A bit string of length N。

 right It's a true false assignment。An element of B prime。Is not a bit string of length in。

 It's a bit string of length n together with an index from one to M。 So what is， you know。

 what do I mean when I say check if。If the element of B prime， if this pair， check if it's in B。

So what's one way？How can I implement this check if it's in B。

 and then we'll also talk about picking a random element， but how can I check if it's in B？Yeah。Oh。

So the way a DNF is to satisfy the entire thing， you just have to satisfy one of the clauses， right？

So any X in D prime definitely is in this set。Right， so I want to， basically what I want， right。

 What do I want， I want a biject between B。And a subset of B prime。

So that it makes sense to check that this element of B primes in B。 and I'll just spill， oh yeah。

Yeah， so check， so look at it， so what's the bijection going to be？Basically。

 for every assignment X that appears anywhere in B prime。Its representative。

 which corresponds to it being in B， will be the I such that it's the first time。

I is the index of the first clause that X satisfies。😡，Okay。So。By objectivejectively map。

B into the set。IX。So PB prime， this is bandnot where。CI is the first。Cluse。X satfies。

So each satisfying assignment is counted exactly once now。And we can check that。

 right Once we get an element of B prime and we can just now take that x。

 compare it like run it through every clause and make sure that that I is the first time it's satisfied。

 so we can check that quickly。Okay。How about picking a random element of B prime， how do we do that？

😡，How to pick a random L in a V prime？How do I choose a clause？Choose any clause。Okay。

You mean not randomly， just arbitrarily？Randomly， okay， uniform like under what distribution？

Uauniform。Okay， so we could do that， I don't know how to make a uniform clause work。But okay。

 you have a suggestion。for me dangerous just like how much。And so then you just。Yeah。现在没得问。嗯。Wait。

 so， okay， so I think， so yeah， So you said we'll pick clauses like that with probability dependent。

The size of the。is by。The size of the clauses， okay， so yeah， not quite the size。The size of S。

 right， right， Okay， good。 So the point is。What are we going to do first。Pick。A clause I。

I can claw randomly。Where the distribution is as follows， close I。Is picked。With probability。

The number of assignments it has。Over。The sum。J from1 to M of size of Sj。so not uniformly。

 but according to this distribution。Right。And then now。Then， pick。A random。Satisfying。Assignment。

For C。A uniformly random assignment， uniformly。So。If you pick from B prime this way。

 then you will guarantee that。The element you get is a uniformly random element from B prime。Now。

 we already said we know how to compute these things， right？We can actually do this。

 The size of S I is just， well， we wrote it somewhere before，2 to something minus something。

 Maybe I erased it already。T oh yeah， there， the size of a size that2 to n minus the number of littles in C so we compute this。

 we can compute these numbers。Yeah， so if you ever have a。

 if you have a clause that's ever like X and N x， then you can just throw that out of your DNF because there's no way you're ever going to satisfy it。

Okay。And now picking a random satisfying assignment， well， how do you do that for the clause well。

The variable the literals that are actually in the clause， you set them to what they have to be。

 and everybody else you just pick uniformly at random。Yeah。So that's that。Okay。

 so that's the entire algorithm。And。This is a sample an estimate P prime。

So now we just want to argue that this works。So the final algorithm。Is。呃。Sample。Qi。Elements。From。

B prime。Let。P prime。I'll let P Prime Tilda。B。Fraction。Of。T sampled elements。That are actually in B。

And then three will output。P prime tilde times the size of B prime。

Are there questions about what the algorithm is？So does anyone have any ideas for how we might？

Prove that this algorithm works well。Okay， well， I saw it on people's lips。

 but no one wants to speak it loudly， so it the turnoff bound， right？Analysis。Turn off band。

So more formally。Let x1 up to Xt。Be such that。Xj is。1。That's the J。Sampled。Element is in B。

And zero otherwise。嗯。And。Let x be the sum from j equals 1 to T of xj。

So what's the expectation of x well by linear expectation？It's going to be p prime times t。So now。

When does this algorithm fail， this algorithm fails。If x minus its expectation。

Is bigger than epsilon。Time is the expectation。Right， so this is。This this means we failed。

 We failed to get a good approximation。So what's the probability of that？Well， the turnoff bound。

Says that it's at most。Well， the turn bound says two times e to the minus。

Epsilon squared mu mu is the expectation。Over some constant， I don't know three or four or something。

And what's this thing？We said this thing is P prime T。Right。So。This。Is less than deelta。If。Qi。

Is at least some constant times。嗯。Log one over Delta。Over。P prime times epsilon squared。Right。

And remember， we know that p prime is at least1 over M。That was the problem before。

 We could have done the same exact argument in the beginning where we just sampled random assignments and saw what fraction of them worked。

The problem then is that P could have been2 to the n or something。

 which means we need at least two to the n samples。

 But the point here is that P prime is not too small。 P prime is like one of M。So this is。Just。

M times log1 over delta。Over ups squared。So we take a polynomial number of samples。An。

For each of the samples in polynomial time， we can check whether or not it's in B。

 we can do the sampling in polynomial time。 So this is all a polynomial time algorithm。So that's。

 that's it。That's enough press for DF counting。Okay。Questions about。

I'm going to move away now from F Pra and FPta and move to another topic。

Another approximation algorithms topic，Before we do a switch， are there any questions？So。

I haven't told you yet how algorithms work to actually solve linear programs。

 I just claimed that there are algorithms to do it。嗯。

So next week you're going to see some guest lectures when I come back。

 we'll start talking about how to actually solve linear programs。

So now that we're in the phase where I'm just claiming certain things can be solved without actually proving it。

I'm going to claim that we can also solve some definite programs。

 so I should first define what that is。So semi definite programming。

 I'll just like linear programming is often called LP， this is usually called SDP。嗯。

So what is a semi definite program？🤧。Okay good。So SDP。So x， capital x。Is an N by n matrix？

So linear programming， we're trying to solve for some vector X。

 Now we're trying to solve for some matrix X。And what the problems look like are minimize。The trace。

Of C transpose X。I'll say a second how to interpret this。Such that。For I from 1 to M。The trace。

Of AI transpose X is equal to B。Okay。So just like L。

 LP is you minimize C dot X subject to AI dotx is B for a bunch of different rows of this matrix A。

But now both AI and X are both matrices now。And there's also these non negativity constraints。Okay。

 and we're gonna replace the non negativity constraints with。Well。

 it's called semi definite programming， a positive semi definite constraint。So。

And I'll say what that means。I'll do a little linear algebra review x is positive。Some I definite。

And I'll usually write this as X。Is。At least zero， which was a little squiggly greater than sign。

So known。So you can see a book， there's a book on semi deffinite programming。

What's it called again so it's called。It's called semi definite programming。And it's by。

Vandenberg and Boyd。Okay。That。Consve。SD P。Up to。Say L bits。Of precision。In time。Polly。N M L。

so we're just going to take that as a black box， just like for LP， I said there are。

Algoms out there that can solve linear programs in polynomial time。

I'm just going to take as a black box that we can do this for SDP。冇仔。

And so what is this trace of C transpose X business so you can prove to yourself。

So I'm not going to prove it， so just fact， you can go and， I mean it's just the computation。

 the trace。Of A transpose B in general is just the sum over IJ of AIJ， BJ。Okay。Really。

 what this is saying is。Don't view X as a matrix， except for the last part。

 which is really something matrix specific。Don't view x as a matrix。

 Just view it as an n squared dimensional vector。And this is really just linear programming， right。

 So this is C transpose X， where C is also an n square dimensional vector。

This is AI dot X where AI is an n square dimensional vector。

 and then you have this funny constraint at the end where instead of saying that it's a non- negative vector。

 you say that if you view this n squared dimensional vector as an n by n matrix。

 that matrix should be PSD。Okay， so that's the difference between SDP and LP。嗯。Now。

So what does it mean to be positive semi definite， so the definition？X。Is PSD positive semi definite？

If。For all vectors， Z， or let's say Y and RN。We have the inequality that y transpose x。Why。

Is at least zero。Actually。Let me just write one more thing。Which we're always going to use。

 it's going to be is a symmetric。我来也没觉。AndJ so claim。

I just want to do a little bit of linear algebra review。The following。Are equivalent。For symmetric。

N by n matrices x。So1 or let's say A。X is PSD。B。So remember。So another factor of linear algebra is。

If you have a symmetric， real matrix， then it can be diagonalized and it has a full set of real eigenvalues。

 this is the spectral theorem。 so B， all eigenvalues。Of x。Our。No negative。And see。🤧咳。Can write。

We can write X。As。M transposem。For some real matrix N。Okay so。嗯。

If these things don't look familiar to you， then for lecture， just take them as truth。

And you can find them in any， pretty much any linear algebra book。 Okay， I mean。

 it basically follows。 So look up spectral theorem， Okay， and you'll see all of this。Okay， so。

First of all。First of all， I claim that linear programming is really just a special case of semi deffinite programming。

Okay。So I don't want to go through the details because I want to actually talk about， you know。

For our purposes in this lecture and what the remains of this lecture。

 I just want to say that there's this thing called SDP。Which can be solved efficiently。

And now we can use it for approximation algorithms。Okay。

 so I don't want to get too much into the theory of how to solve them， etc cetera。 But I want to do。

 I want to say just a couple things about them。 So LP。Minniar programming is a special case。Of STP。

 does anyone see why？So suppose I have an LP。That looks like this， any LP， by the way。

 can be written in this form， minimize c transpose x subject to Ax equals B。

And x is at least zero in every coordinate。I claim that。This can be represented as an SDP。Right。Yeah。

 so exactly， so SDP。Okay。We're going to define C to just be a diagonal matrix C1， CN on the diagonal。

Okay， we're also going to define。AI as being。A。AI1。诶。AI N。Diaagonal matrix。

And then we're also going to enforce。We'll also add constraints。To force。X Ij equals zero。

For i and n equals to J。You can add more constraints to force that。Okay。And to say that it's PSD now。

 to say X is PSD， Well， it's a diagonal matrix。 So all the eigenvalues has to be non negative。

 which means all the entries on the diagonal has to be non negative。Okay。

 so LP is just a special case of SDP。And。I won't say much more about this。

 but SDP also SDP is actually a special case of LP， well， where you have infinitely many constraints。

So basically， for every Y， you can write a constraint where。

You can write a constraint where the trace。Of your matrix now is like y y transpose times x。

Should be at least zero。Okay。So if you have infinitely many constraints in your LP。

 you can represent an SDP， but of course， that's a really big LP。🤧So。Now。

 I just want to say that SDP。Is now really the same because of this claim。

 SDP is really the same as VP， which is vector programming。What do I mean by that？

We said that if x is PSD， it's the same thing as saying it's M transpose M。Which is saying it's。

So right， it's a gram matrix， what's called a gram matrix， it's V1 up to VN。Times。V1， VN。

Which means that。If we look at the IJth entry。Of x， that's just equal to V。vj。Okay，This implies。

 for example， the trace of C transpose X。That's just the sum overall IJ of Cjvi。vj。And similarly。

 for the other constraints that you have。You can write it as just。A sum of AIj times V。vj。

Right so vector programming is。Well。It's like linear programming except。

Variables are dot products like this。So SDB can be solved efficiently。

 so VP can be solved efficiently。And there's no more once you're solving vector programming。

 there's no more PSD constraint because I mean， you're already encoding that in the fact that you're using vectors in the first place。

They're using these vector dot products。So， VP。Says minimize some over IJ， Cj， V。vj。Such that。嗯。

For I， let's say for I going from y up to M。Let's say for K going from1 up to M。The sun。

Over IJ of AK IJ V。vj。Should equal Bk。That's what vector programming looks like。Okay。So。

Now I want to look at an example of using。Vor programming。

 which is the same thing as semi deffininite programming。To get an approximation algorithm。

So an example。Is Max cut？Okay， so the input。Is a graph？G equals V。It's an undirected graph。

And you've probably heard of min cut， max cut is maximized。

 find a cut that has the maximum number of edges crossing it。So goal。Find a cut。

 A cut is just a partition of the vertices into two pieces。 Find a cut。

Which is a partition S and V minus S。Maximizing。Maxim my Zing。Number of edges。Guang。From S。

To the opposite side of the partition。So。If you took 124 last term， I think I mentioned。

A good approximation algorithm for max cut。Has anyone seen any approximation algorithm for X cut。

You didn't remember anything。Well， I'll tell you。Just pick a random partition。So for each， so。

 you know， have a left set and a right set for each vertex。

 put it randomly in the left and randomly in the right flipcoin。 probably a half it's in the left。

 probably half it's in the right。 Look at any edge。

What's the probability that the edge crosses the partition？Well， it's a half。So in expectation。

 half the edges cross the partition and you get at least M over to M is the number of edges。

 So let's say this thing is。It's equal to n， and this thing is equal to n。

 You get at least M over two edges。An opt is certainly at most M。

 So you're getting at least opt over two edges。O。嗯。Another non random algorithm is。

Just start with an arbitrary partition。And as long as there exists a vertex。

That has more neighbors in its own partition than in the other one。Swp it。

So this has to terminate because you're always increasing the number of edges that cross the partition。

And if it's now terminated， then that means that。Every vertex has at least half its neighbors in the opposite side。

 which means that you have at least M over2 just crossing the partition。Okay。

 so both of those are two approximations， you get at least half of optt。And for a really long time。

Those were the best algorithms until I think it was 95。Wasn't 95。It was Gomans and Williamson， yes。

 Gomans Williamson， well， actually 95 is the journal version。

 so it was even earlier when they first came up with it， but Gomans and Williamson。

The journal version is in 95。What do they get， instead of getting at least half of optt。

 they showed how to get。0。878 approximation。Okay。And what is this number？😡，This number is the。

The lowest possible value。Over all angles in the range from。Zero to pi。

Of2 over pi times theta over 1 minus cosine theta。Okay。

 so that's so we're going to see that algorithm。😊，Even though the number looks weird， it's actually。

It's actually a very simple algorithm， it's just that before them。

 people weren't using SDPs to come up with approximation algorithms。And kind of after they did that。

it was a really influential paper， so then people started saying hey。

 maybe we could use SDPs for other problems as well， and in fact they did。

And there's something called。So first of all， just like LP have integrality gaps。

 SDPs also have integrality gaps。Okay。So I'm you know， I'm gonna write down max cut。 not。

 I'm gonna write down max cut not as an integer LP。

 but I'm gonna write it down as a quadratic program with integral constraints。Okay。

 and you'll see what I mean in a second。We're going to relax it to an SDP by whenever we have quadratic terms like Xi times Xj。

 we're going to relax that to V dot Vj。So instead of thinking of X I as being a plus -1。

 we'll think of it as being a unit vector and multiplication will be dot product。Okay， so max cut。

We can write it as a quadratic program， we want to maximize the sum over edges in E。

 where E and edges from I to J。🤧Of。I think1 minusxii times Xj over 2。

So the point is and here for all I， X is in the set from minus1 and 1。Yeah。So the point is。

Xi tells you whether' on the left side of the right side of the cut， vertex I。Now。

 if they're both on the same side， the product will be1，1 minus1 is 0。

If they're on opposite sides of the cut。Then you'll have1 times -1， which is-1，1 -1 is2。

2 over two is1。 So this counts basically how many edges are crossing the cut。

This is a quadratic program。😡，So by the way， Max cut is NP hard。

 So we've also shown that now quadratic programming is NP hard。Okay。So。

We don't expect to be able to solve this quadratic program unless P equals NPp。

 so the SDP relaxation。Is to maximize。The sum。Over edges and E。E is IJ。Of1 minus V dot VJ。Over 2。

 and for all I， V dot V is equal to1。Or SDP or VP， it's the same thing。Okay。

So we can solve this thing。Quickly。Okay， but now we don't get a bunch of minus ones and ones telling us left or right。

In the partition， what we get is a bunch of unit vectors。So now how do we actually？

Turn those vectors into a partition。So the algorithm， the Goldman Williamson algorithm。Is pick。

A random hyperplane。Thinkick a random R in RN。😡，By the way， remember from。

The way we got to vector programming。From SDP。Remember， these Vs were the columns of a matrix M。

 They're n dimensional vectors。So what we're going to do is we're going to pick random vectors R in RN。

 pick a single random vector R in RN。😡，And。Put vertex。I in S if the sign。Of R dot。V I。

Is at least zero？And we'll put vertex I in the other side of the partition if the sign。Is negative。

OkaySo pick a random hyperplane and you're either above the hyperplane or below it。

 and that decides what side of the partition you're on。Okay。So now。In the last minute。

 what's the expected。🤧嗯。What's the expected。Size of the cut by doing this。

This is just the sum over edges and E。Of the probability that。Let's say E is I J。

 the probability that I and J are。Well， V I and。VJ are on opposite sides。Of R。Right。

But VI and Vj are just two vectors， so we can draw them。

And they span a two dimensional space so we can draw them。They're on the unit sphere。

 they have norm1， so VI is somewhere。VJ is somewhere。

What's the probability that they're separated by this hyperplane？Well， R has to be somewhere in here。

😡，So for them to be separated， R had to be somewhere in here。So there's an angle theta。So。

The probability that E is separated。Is equal to。Yes。Well， I'm running out of time。Well。

 the probability that you separated is state over pi。嗯。Which means that。呃。The probability separated。

Over。1 minus V。vj over 2。Is equal to this two over pi。嗯。Two over pi times。

Data over1 minus cosine theta。V。vj is exactly cosine theta。Okay。And。So this is exactly where。

This ratio comes from okay， and then you ask， like， what's the worst that this ratio could ever be。

 Well， it's the in overall theta。So I'm out of time， but I mean。

 that's basically how the algorithm goes。 maybe I'll fill in details a little more vigorously in the notes。

嗯。But。That's it。Okay， questions in the last few seconds。Yeah。てあ。Yeah， I mean， I just mean。I mean。

 what's the probability that the sine of V。R is not equal to the sine of Vj。R？😡，So。By this， I mean。

 what's probably that the sign。V。r is not equal to the sign。MVJ。That。So。All right。Right yes， sorry。

 yes， so I guess。So R is the normal to the hyperplane。

 so I guess what I meant is so if this is the hyperplane。Then。In this picture。R would be here， yes。

 yeah。Sorry， that picture was a little misleading。But the point is the hybridplane has to be somewhere in this window in order for you to be cut。

Okay， so anyway。Enjoy the guest lectures next week。

