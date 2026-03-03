# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P11：-11-Advanced Algorithms (COMPSCI 224), Lecture 11.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/df10b25e18f0ca0b17f1de56bfdb79b6_0.png)

So today I want to finish the。Finish the analysis of the dual fitting analysis of the greedy algorithm for set cover or weighted set cover。

嗯。And。I'll do one， I'll do one other very simple example for dual fitting。

 namely unweighted vertex cover and you're so the next homework is going to be out tonight and you'll see a problem related to that。

嗯。To vertex cover。Then I want to talk a little bit about a limitation of。

Of this whole LP framework for approximation algorithms。

 okay so I'm going to introduce something called the Inity gap of an LP relaxation。

And then I'm going to talk about。呃。More approximation algorithms namely polynomial time approximation schemes。

And that's where we don't just want say a two or log n approximation。

 but we want a one plus epsilon approximation。Where Epsilon is given in the beginning， okay？

So how do we get for any fixed epsilon a polynomial time approximation。

 sometimes that's not possible。But， we'll see。An example where that is possible。うんうん。Okay。

 so last time I defined the set cover problem or the weighted set cover problem。There are M sets。

 each one is a subset of the universe， the universe for us is one up to n。And a set S has a cost Cs。

 and the goal， given this this an input， the goal is to find a sub collectionction of the input sets。

Which covers the entire universe。 Okay， you must cover the universe and you want to do it as cheaply as possible。

 minimize the sum of costs，The sum of costs of sets you take。So the greedy algorithm， well。

 in the unweighted case， I think people have if you've taken CS124， you've seen the greedy algorithm。

For the unweighted cases is you just keep taking the scent that covers the most new elements。

But when you have costs on the sets。Then you just slightly alter that。

You pick pick the set as long as there's an uncovered element， you pick the set。

 which minimizes the ratio between its cost and the number of new elements you get to cover by picking it。

Okay。And。Theorem。嗯。Greedy。Is a login approximation。We'll even see it gets something slightly better。

Just some history， I guess。呃。And the unweighted case。When all the costs are one。

 that's what I mean by unweighted。This greedy algorithm is due to Johnson。Back in '74， I think。

Whoscribing today， okay agree。And also， I believe independently。

 at least they didn't ciite each other。In discrete math。75。And in the weighted case。

I don't know how to pronounce this name。And that was in '79。Okay。

We're going to take a primal dual look at analyzing this algorithm。Okay so if you took CS124。

 we did analyze it there， we didn't talk about primal dual。嗯。

You canYou can take a prim do a look and for one of the。

Homework problems that I'm going to release soon for vertex cover。

 it's going to be for weighted vertex cover。Even it's not just an issue of the analysis。

 even to come up with the algorithm， I think it helps you to have a primal dual look at the problem。

Okay。Okay， so。So the LP。Relaxation。For set cover， I said last time。In the primal。

We want to minimize the sum over s of CSs times xs， where xs is 1 if you take the set0 otherwise。

 subject for all I from1 to n。You need that the sum over sets containing I of xs is at least one。

 and that for all S xs is at least zero。Yeah。No， so that's a very good point。 Yeah。

 I shouldn't have said the LP relaxation， so。and LP relaxation。 Okay， so if you。

So the set cover problem is actually this problem， but where you have the constraint that excess is in zero is either  zero1。

 and we relax that to just put a linear inequality。But you could imagine formulating it。

Another way and getting another LP relaxation of another formulation of the same problem。

And maybe using that LP relaxation would give you better results。So there's actually。

 I'm not gonna to get into it in this class， but there's actually a formal way of doing this。

 So given。Given some integer programming optimization problem where you have integer constraints。

There's a systematic way of。Converting the LP of getting more and more refined LP relaxations。

 which get， which become better and better approximations to the integer constraints。

 So if you want to read more about this， you Google for like the Shili Adams hierarchy。 Okay。

 so I'm not going talk about that in class。But。Theres and you can show that。

Eventually this thing becomes the integer program after。

 but then by that time you've blown up the LP to exponential size。Okay。So that's the primal。

And the duall。I we want to maximize。The sum of e going from1 to n。Of Y3。Subject to。

The constraint that for all sets S， the sum of elements in that set of Y E is at most Cs。

 and also y is a non negative。呃。Rector。Okay。So we'll do dual fitting。

I think I mentioned this at the end of the last time， but now I'm actually going to prove something。

So's a dual fitting。没有。S。How to maintain。Dual solution。As we build the primal。Okay。

When we take a set S。Okay， we're going to set。X of S to1。In the primal。And two。For each。

Newly covered。Element E。We'll set。Y sub be to equal C sub S over。呃。The number of elements。

Nearly covered。By S。Okay。So this is what we're going to do。Remember the usual thing？

We know by weak duality that but that any primal， if we have two feasible solutions。

 one for the primal one for the dual， we know the primal cost is at least the dual cost。

Where Op is sandwiched in between。嗯。So， but they have to be feasible。 So as it turns out。

 this y might not be feasible， but will show that if you entry wise just scale down by log n。

 it will become feasible。Okay。So。Let me write down some observations， first of all。

The cost in the primal of x is the cost in the duall。Of why， and we've rigged it that way。And。

Will'll show。That。In fact， it' willll show y over the n harmonic number。Is feasible for the duall。

And that's going to imply law and n approximation。And definitely， I should also say， I mean。

 I didn't say the primal will be feasible， right？The primal is feasible。

Because we keep doing that while loop as long as there's a constraint that's violated。Okay， so。

So now we just need to show this。So claim。Y over HK。Is feasible for the dual。So proof。So I mean。

 this constraints's never violated。 The only trouble is this one。

So we need to show that for all sets S， this summation is at most。Cs Times login need to show。

That for all S。The sum of E and S of Ye is at most CS times log and n。

 or actually times Hn and what's K， there's no K here。Okay。So let's order。The elements。Of S。By。

Byiwen。They are first covered。So E1， E2。EK。Right， so let's say SS size K。嗯。So。Let's look at。

Right before。Right before。EI was covered。So what I want to say now， and I'm going to write you know。

 when I finish the sentence。I want to， I want to basically say that。You know， each one of these EIs。

 at some point when it's first covered， it's going to get its Y sub be set， right。

Now what E might not get EI might not get covered by S might get covered by someone else。Okay。

But I want to argue。That when EI was covered， I want to argue that the price that we set to Ye。

Could not have been that high。 I want an upper bound on that price。 I'm calling my Y is for me。

 the price vector。Okay。So what's some bound？ Can anyone tell me a bound on the price。Of。Of。

That we will assign to YE。So right before we covered EI。😡，Right。So EI is not covered。

 meaning we haven't chosen S yet， because us would have covered it。

What would be the prices derived from choosing S at this point？C us over what？And。And what's。

 what's a lower bound on， Yeah， K minus I， K minus I plus1， actually， right， right before we。

 I was covered。We could。Have chosen。S， at price。Cs over k minus I plus1。Okay。So we know that implies。

At the price of EI。Is that most CS over k minuss 1， right？That's what greedy does。

 It chooses the thing that gives us the lowest price。Whoops， I just lost one。So this implies。That。

This summation。The sumation right here。That star。Is that most。

C sub s times the sum i from 1 to k of 1 over I。Which is exactly C sub S times HK。

And K is the size of S。 remember K here is the size of S， which is certainly at most n。In fact。

 we proved something stronger， we proved that if all the sets in your set system have sized at most K。

 then actually greeting gives you a log K of approximation。Okay。So that's it。Ill there just one more。

 even shorter one。So one more。Vertex cover。So right， the input。Is an undirected graph？G equals V E。

Okay。I'll say this has size n。And that has size M。And the goal。Mr。 Pick。As few pick。

Pick a subset of the vertices。As as small as possible。Such that each edge。In Yi。Is incident。Upon。

At least one。Vertex。Of S。Okay。🤧。So there's a greedy algorithm for this problem， which we said at 124。

 but。I'll write it again， so greedy algorithm。While， and by the way， notice that。

Notice that vertex cover is actually a special case of。Set cover。People agree with me。

 so someone tell me why？The edges are so okay， so in set cover。

 there's a universe and there's a collection of sets。

So what's the universe and what's the collection of sets。Right， yeah， so every vertex is a set。

And every edge is an element of the universe。 That's right。 Yeah， okay， good。So greedy。

 while there exists。An uncovered。Well， there exists an uncovered edge。E an edge E from U to V。

Add both。U andvy。To意。And the claim。Is that greedy is a two approximation？Okay。And。嗯。Probably won't。

Maybe we'll see one proof。 there are many。Proofs。Well， we'll see a primal dual proof。

 but one proof is you can say， look。The set of vertices that I pick in this way form a match well。诶。

Look at the edges that appear in this loop。Throughout every iteration。

Those edges from we're matching。Okay。And therefore。

 the number of vertices we return in our set is twice the size of a particular matching。

And then you can say any vertex cover。Size is lower bounded by the size of any matching。Okay， so oh。

 you look。Yeah。私あ。Yeah。Okay， good， so the sets are the vertices。Right。

 so vertices can have high degree。 Yeah， yeah， good。 Yeah， I was。

 I was also thinking that right when I wrote and then I like Yeah， edges。

 edges are contained in two sets， but。Right。But actually， that's a good point。

 So inject for set cover， for set cover。We said that if every set has size at most K。

 you get an HK approximation， like a long K approximation。

 but you can look at it the other way around too， you could say， well。

 what if every element is contained in net most K sets？So for that， you can get a K approximation。

And how's that， Well， actually， it's going to be related to what I'm going to write now。 So proof。

 you know， if you really want to see one proof， we'll see another one。One proof。You know， you know。

 see the CS124 notes， Google it or something。But I'll show you a different proof today we'll do primal duel。

But。Other proof。This primal due， that's going to be helpful for。

Something on the P set that will come out soon。 So let me write。TheNLP relaxation。

 not the LP relaxation。So primal。The prime rule is。Minimize。The sum equals1 to n。

 or the sum v goes from one to n of x of v。 So that's whether or not you take the vertex v into your vertex cover。

 subject to。For all edges。For all edges E being UV。In the set of edges， x U plus x v is at least1。

 and x is at least zero， entry wise。I mean， this should look familiar， it is the set cover LP。

 basically。Dl。We wantant to maximize。The sum of edges。Of YC E。Such that。For all vertices V。嗯。

The sum of。And edges containing V。Of y sub E should be at most one。

And also Y is and true Y is at least zero。Okay， so。Another way besides greedy。

 so the nice thing about the greedy algorithm is that it's pretty fast。

You don't have to actually solve any linear programs。If you're willing to solve linear your programs。

 which is slower。You could just solve this primal。Right。And you could say， well。

I'm going to get now some fractional solutions for the XUs。Right and I'll and then what I'll say is。

 look for every， for every one of these， now I need to get an integral solution。

 I need to choose which vertices to actually pick。For every one of these inequalities。

Either X U is at least a half or X v is at least a half。Okay。So。I'll pick whichever one is。

Whichever one is at least a half， I'll put it into my set。Okay。And you've now at most doubled。XV。

 so you've most doubled the cost of the solution。So that's another two approximation。

For vertex cover， and that's also a K approximation for set cover of every set is contained in K elements。

 right， because if every set is contained in K elements。 remember， these are the sets。

You'll have a constraint here that involves k variables。 Their sum is at least one。

 one of them has to be at least one over K。 So take the one， which is at least one over K。

And then now you'll get a K approximation， okay， so that's it。So I want to show though。

 a primal dual analysis of the combinatorial algorithm。

 We like combinatorial algorithms because they're faster than actually solving linear programs。

So going back here。So now the proof using primal duel。It's， again， going to be dual fitting。

When greedy。Takes u， takes， takes some vertex v and capital v。Set X， V。So one。And also。Se X。Sorry。

 when greedy decides to cover an EG。When greedy covers。An edge E。Which is U V。An edgeet。Set。

X U and X V， both to one。Well， this isn't even going to be dual fitting。

 this is just pure primal due because we're going to get feasibility automatically set and set Y sub。

Yi。To one。Okay。So I think that's it。🤧。So。嗯。Both of these are feasible solutions。Okay。And。

Whenever we increase the dual solution by one， we increase the problem by at most two。

Possibly one if one of them was already taken。So it's a two approximation。Okay。Zo。Both feasible。

But primal cost。Is that most twice dual cost？Implies to approximation。So on the PE。

 you'll see the case where the vertices are actually weighted。

 so you're trying to minimize xv times the cost of V。

Then you need to think about what the greedy algorithm needs to change。 you know。

 are you still going to take both， that's probably not a smart idea if one of them is way cheaper than the other one。

But by reasoning about。Both the prime and the duel you can get。You know， a decent algorithm。Okay。

 so that's all I want to say about approximation algorithms via dual fitting。Or via primal duel。

I want to move on to item two， which is integrality gaps。Okay。So we， we can ask ourselves。

What is the limit？Of using。Some。LP relaxation。Well， if you think about it。

We always so far we achieve in our proofs， we say we achieve。cost。At most。

 some approximation factor alpha times the opt。Of。The LP relaxation。Right。And we can ask ourselves。

 well can we improve alpha from log n to root log n or to a constant or something？But。

What if there is an inherent gap between the opt of the LP relaxation and the opt of the original integer program。

 right？If。There is some gap。So let's say we're looking at a minimization problem。Is there some gap？

That says opt。Of the LP。Is that most beta times opt？呃。Beta times opt of the。Integer program。

For some particular instance。Some particular input。You know， then。

Such an argument we can't hope to get better than a beta approximation。Then we cannot hope。

To achieve a ratio alpha， which is strictly less than beta。Right。So。I mean。

 I don't want to say that we can't hope to achieve it。V any algorithm。

 but we can't achieve it via this particular LP relaxation， which goes back to your question。嗯。

Which is， you know， when you said is the LP relaxation unique。

 you know it's not sometimes if you're smarter and write down a better inger program to begin with。

 right， there might be many different ways to capture the problem as an inger program。

If you write it in a smarter way and then do an LP relaxation of that。

 maybe that could maybe a different LP relaxation could give a better approximation ratio。

But this just， this just gives you a limitation on using a particular LP relaxation。 Okay， so。

 for example。I mean， let me make this concrete example，'s go let me do them back in reverse order。

 first I'll do vertex cover because it's simpler than I'll do set cover。Sovertex cover。

So where's the LP for vertex cover， it's right here。

So what this constraint actually should have been is that。And then we write it like this for all。

For all you。X U is at least 0。 What this constraint should have been is that X U is either  zero or one。

 and we relaxed it to this， right。And I claim that actually， once you do that relaxation。

You already are losing a factor of two。Their are inputs。Where beta is 2。Okay， or roughly two。Opt。

For the fractional solution is only half the cost of opt for an integral solution。Okay。So。

What's an example？呃。Take the complete graph on in vertices。I'm not going to drag complete graphs。

That was terrible。This doesn't even look right。Okay， and I think I drew one twice， I drew2 twice。

 Oh right， it's， I forgot it's。Yeah， okay， that makes sense。Okay。So。Opt。Of the fractional。

Of the LP relaxation。Well。What can we do？We can put a half。On every vertex。Right。

That will be a feasible solution。In fact， that is the optimal solution， that's n over 2。

A half on each vertex。Whereas in the integer program。I mean， for the actual vertex cover problem。

The best you can do is。N minus1， you take some vertex， you just take take one vertex， right？

Take all vertices except one。 So n -1。Right。If you take any solution with fewer with n over two or fewer vertices。

 that means there are at least two vertices left out。

 but then you're not covering the edge between them。Okay， so you need a cost at least n minus1。

So there's a gap of roughly two。Okay， so if you're arguing using this LP relaxation。

 if you're somehow rounding solutions to that， then you know， you'， you're sort of。Out of luck。Yeah。

いア。A different outcome。嗯。Yeah， so I'm saying。If our way of coming up with this algorithm and analyzing it is to compare with the optimal solution of some LP relaxation。

Well， if if the LP relaxation has a gap with the original integer program and that gap is at least a factor of beta。

Then there's no way to achieve better than a beta approximation by this kind of comparison， right。

 Like if， if the way that we're analyzing our algorithm is to say， look。

 our algorithm never achieves cost more than alpha times。Optt of the linear program。Well。

You're not going to be able to achieve an alpha here that's better than beta。

Because the solution you're providing is an integral one。So in particular。

 the example which creates this gap。You're going to be off by at least beta。So that's what I mean。嗯。

So yeah， this， the best beta you can achieve is usually called the integrality gap。It's like the。

The max over all instances of the gap。And usually parameterize instances by something like by the problem size。

 So like as a function of n。What's the worst gap that you could possibly have or as a function of some other parameter of the problem？

 So we're going to see that， for example， for set cover right there。

 we're going to parameterize by N。And we're going to say， as a function of n。

 what's the worst gap that you can have。 So I mean。

 we're going to give an example where you're off by a log n。Okay。

So yeah here I'm really looking at the ratio。So， yeah， it's， it's as n gets big。

 the gap is approaching， too。Any other questions？Okay。Okay， so。For。Another example。

 it will be a little。More a little trickier。St cover， I want to give a log。A log end gap。Deefine。

And to be2 to the Q。in-1。For some integer Q bigger than zero。Okay。And。Elements。Of。呃。Of the universe。

Are in correspondence。With。Elements of。F2 Q about 0。So what is this， these are vectors。Of length Q。嗯。

Over F2。Yeah， over01。So this is some vector space。Hey， so。Really， I'm just saying， you know。

 think of these as like bit strings of length Q and adding them means bitwise。Bitwise Xor。And sets。

Our。Also。In correspondence。With elements。Of F2 Q。We the set corresponding to alpha， so let's say。

If alpha is an F2q， so it's also some bit string of length Q。That implies that S sub alphapha。

Is the set of all E in the universe？Such that。Alpha dot E。This is the dot product is equal to one。

Moud2。Okay。Are there questions about， you know， feel free to if I'm saying if I'm using some jargon thats。

That doesn't sound。Good to you， just ask me to clarify， okay。Yeah。出てるす。Oh， is that right？Oh yeah。

 yeah， yeah。 I see what you mean。You can't hope to achieve alpha。Yeah， okay。Yeah， so。Opt of the I。

Right， yeah， okay， yeah。So let me just think so here， so if the LP is one， the IP is。2。😔，Oh yeah。

 okay。 so this beta is actually a half。Yeah， okay。Yaan。So。

So this one over beta is what I was calling the integrality y。Very good。

So here I have a vector of bits， here I have a vector of bits， I'm taking their dot product。Okay。

 Montu。Okay good。So what am I going to try and claim？I want to claim that a fractional solution。

Can actually cover all the elements with a cost of a constant。Okay。

 whereas an integral solution has to have cost at least Q。And Q is about log n。

So what's a fractional solution？What's a cheap fractional solution？Or let me ask you。

 let me ask first as a hint。For every element in the universe， how many sets contains it？

How many sets contain it？Okay， so there are two of the Q sets， and wait， many， how many contain it？

There are exactly two to the Q sets。Half of them， right， because in particular， I mean。

 one easy way to see that is if you pick alpha at random。

Then the probability that this dot product is one is a half。喂。I mean。

 and that's because we removed zero from the universe。So。Each element。Is contained。In exactly。

Half the sets。So that implies a feasible solution is can take。That for all you， XU is。呃。2 over M。

Okay。Good。And what's the cost of this solution， it's two。Implies the opt of LP。Is that most too？Yes。

Make sure we're all on the same page， right， the cost in the LP was just the sum of the XUs。

And the constraints were that for every element， the sum of the xus for you for all S。

 I should say for all sets， S x S is2 over M。 So the constraints are that for any element E。

 the sum of all the Xes for S containing E should be at least one。So this is just equal to。

One over the number of sets。Containing。呃。Yi。For some意。Okay， so good， meanwhile。For the integer。

Integer solution。There。Well， it's going to follow from linear algebra。Right。Suppose。

We have a solution。With Q -1。Sets。S alpha1。Up to S alpha Q -1。And what you're telling me。

 you're telling me that。The union。Of S alpha I。Or。The intersection of the complement of S alpha I。

 where I goes from 1 to Q -1。 You're telling me this intersection is empty。

There's nothing that's not there's nothing that's not covered by any of them。Okay。But what is？

What does this mean？What is this intersection？This equal。To the set of all。Ease。Or not that it's。

Empty with that， I guess it's the set zero。It's not in the universe，So what is the set。

 it's the set of all ease such that。For all I from 1 up to Q minus1。Alpha i dot Q dot E。

Is equal to zero。Right。So we started off with a Q dimensional space， a Q dimensional vector space。

And here， this is the set of all elements satisfying Q -1 constraints。Q -1 linear constraints。

 So its dimension is at least one。Okay。So in particular， it's not empty。This is an。At most， Q -1。

Dimenssional space。呃 sorryor。So sorry， that just not what it meant。Q minus1 linear constraints。

Implies it's at least one dimensional。Which implies， it's not empty。Okay。So that's a contradiction。

So you need at least Q sets。Okay。Questions。Okay。So now I want to touch on the last thing。

 polynomial time approximation schemes。So here the idea is， well。

 let me just start defining some of these terms。So let me look at minimization problems。

 you could define similar things for maximization problems。Okay。We say。A problem。Admits。A Pta。

This is a。Polynomial time。Approxiation scheme。Actually， you know just before I。Just before I。

Let me say one more thing before I finish with。Inteegality gaps。

 there are actually stronger things you can do。 So with integrality gaps。

You're just saying that this particular LP relaxation can't give me something better。You know。

 a stronger statement that you could hope to make is。Unless P equals NPp。There's no。

Polynomial time algorithm to do better than a login approximation。Okay， right？So， I mean。

 forget about even using LP relaxations at all， no matter what you do， unless people's MP。

 there's no。tter bettertter approximation ratio achievable。 so actually for the set cover problem。

It's known。 This is due the theorem due to Fga in 98， that。You can't。

You can't really do better than natural log of N。Unless you can solve sat in time and the log log N or something like that。

The best known algorithms we have for set， run an exponential time and end。

 end of the log log n is way cheaper than that。So that gives strong evidence that。

We don't expect to beat natural log event。So that the proof of that doesn't use any。

 it uses some machinery that we're not going to cover at all in this class and it builds upon something called the PCP theorem。

PCP stands for probabilistically checkable proofs， I guess if you want to hear about that。

 take a complexity course or go read about it。Anyway， I just thought I would mention it。

It should be exposed to its existence。Okay， so back to Ptasses， FPtaes and F PRes。

So we have some minimization problems， set cover or whatever else， vertex cover， et cetera。

 And we say it admits a PT if。For all epsilon in 01。And also for all problem sizes N。Can achieve。

We can achieve。Fla fixed。You can achieve one plus epsilon in approximation。In time。Poauly N。

We write it as N。To the F of one of Epson。Right。So。

Think of Epsilon as a fixed constant01 or something。Okay。

So what I'm saying is for any fixed constant epsilon you give me。

Then it's possible there is an algorithm that gets a one plus epsilon approximation。 in this time。

 F of1 over epsilon could be terrible。It doesn't have to be polynomially when arup line。

It could be two to the two to the two to the1 Epsilon or something， but if it's a fixed constant。

 then this is a polynomial。Okay。So meanwhile， an FP task。F stands for here。Fully。

So a fully polynomial time approximation scheme。Is one where。For all epsilon。We can get time。

Polynomial。And over Epsilon。So you're not allowed to have crazy dependencies on Epsilon。

In particular Epsilon， you shouldn't have epsilons in the exponent of N。And an F press。Is a fully。

Poly time。Randomized。Well， there's no， I guess it should be F。Patrass。

 but you can't really pronounce that。Appximation scheme。And。嗯。

Here we allow ourselves to use randomized algorithms。

And these randomized algorithms are allowed to have some probability of failure。So the time。

Is Paully。And over Epsilon。That allowed。To give。A wrong answer。Meaning not。Not wrong answer it say。

 not achieve。One plus epsilon optt。With probability。At least。

The probably atmost a third or something。Good question， why third？So suppose I could achieve this。

Third guarantee。And I really wanted to achieve a guarantee of say Delta as opposed to a third。

So what would I do？Make a bunch of different runs， right， and take like the。

The median rot or something。Okay， so。嗯。So basically this， the way you define it。

When you define this F press， the way。Specify that constant doesn't really matter。Yeah。Yes。

Why is that the case？Well。Maybe not in this situation。A third is a good thing for kind of bounded。

Error polynomial time algorithms， maybe。What's one nice thing about a third。

 So suppose forget about F press is the the reason I pick a third， I'm now digressing slightly。

 But the point is， if you have an algorithm that outputs a number and you have no way of verifying that that number was correct or not。

Okay。Well。If you know that the number is failing you with probability at most a third。

Then if you take many trials and take the median number that showed up。

 it'll be good with with high probability， okay。嗯。That's not true。 with a half。Right。嗯。

So a third is sort of the。The number of the form one over integer。

 where integer is as small as possible， which works。呃。Yeah。Okay， so。Good。

 so I want to show examples of Ptasses and FPta and F passeses， so I'll show a PTA。

And I'll also show an FP task。For Napsack。And I'll show an F press。For counting。Number of solutions。

To DNF。I forgot the year。So。This is due to carp。Ly。Mara， I believe。And I Ill。

I don't remember the year right now。Napack， well， there's been a sequence of papers I'm not going to cover。

The most efficient FPta are Ptasses。From searching around， it seemed that the most efficient one。

The most efficient F task for a knapsack was due to。Eugene Lawler in '79。

Maybe I missed some reference。These areI should have said these are examples。Yeah。

So let me define Napsack。So we're given。So we have an Napsack。With capacity。W。

And we're also given items。With。Weaiights。W1 up to WN and values。V1 up to Vn。Yeah。

I'm defining the problem。This is the definition of the problem， sorry， so problem statement。

Is this okay， so we have a knapsack。With capacity W Na， I mean。

 I literally mean a knapsack like we have a backpack， okay， and it can hold w pounds worth of stuff。

And we have items with the following weights。 So item I has weight， WI and value VI and。

We want to pack。Ournapsack。To maximize。The total value。So this is our goal。Okay。So。

So we could write this as maximize。S I from one to N。Of the value of item I times。Xi。

 which tells us whether we took it or not。Subject to the constraint。

That the sum I from one to n of W I X I is at most W。 and that for all I。

 W I is either X I is either 01。Okay， so this is Napsack。

So suppose we relaxed the integral constraints。This integral constraint to。嗯。Suppose we relax this。

I like this one and this color is more visible， I think， so suppose we relax this too。

Xi is between1 and0。Okay。I don't want to relax it to just say Xi is bigger than equal to zero because if there's a really valuable item。

 you might be incentivized to take it multiple times。Okay。

 which there is a variant of knapsack where that's allowed。

 I think it's called multinapsack or something。 but for me， you can't。

 you can't purchase multiple copies of the same item。 Okay。

 you can just take a subset of the N items you're given。

So suppose you had this fractional version of Napsack， what would the optimal solution be？

Whatd you do。Yeah， so for fractional app。P fractionctional Napsack。Sort items。In decreasing order。By。

V I。Over weight of I， so which has the best， which gives you the most bang for your buck。

 most value per pound。And。Take Philip。Napack。In disorder order， right？

Put as much of item 1 in this sorted order as you can。 And if you still have space。

 put item 2 until you run out of space。 And on the last item。

You might onlyt be able to take a fraction of it， but you'll take whatever fraction you can fit。

 so what's a natural greedy algorithm？That you might hope。 So by the way， Napsack is NP hard。Okay。

But I claim that there are dynamic programming solutions to Napsack。Right， so。So exact。

Integral knapsackack。One thing you do is you can good time。O of NW。Okay。

So here what you do is you say F of。IW is equal to the most。Value。

Achiieevable let me make myself some let me not cram myself。So how you get this， you say F of IW。

Is the max？Value。Achchievvable。Or let me write it as B。F of IB is the max value achievable。

If we have。The space left。And only。Take。Items。From the set。From to set one。Up to I。有人。

So at the end of the day， what we want is F of n comma W。How you get F of I comma B， Well。

 you can either take the iOD item or not take it。So you can either F of I B is equal to the max of F of I minus1 B where you don't take the item。

Or F of I -1。 Or so let me right like this F of I B。Equal to zero if I is equal to zero。

Otherwise equal to the max。Of F of I minus1 B and V I plus F of I minus1 B minus W I。If。

B minus WI is not negative。So you can write a recursion like this and fill up this table using dynamic programming。

So。So great。 we have a fast algorithm for Napsack， but Napsack is NP hard。 How is that possible？Yeah。

 W is right， when we say polynomial time， we mean polynomial time in the bit representation of the input。

RightAnd W， to write down W as part of the input takes log W bits。So it actually be polynomial time。

 We would have to spend。 polynomial time means polynomial in N in log W。

 So n times W is not acceptable。And you could also get， so you can also define。

V to be the sum over I of V。And you can also get time。O of N V。

Thiss another thing you could do for Napsack。How is that？You define F of I。Coma P。As being。

It's another dynamic program， and he has to have people seen this。Right。

How would you get so NW for NapsSAC is according to this， you could also get NV。

Any how would you define F of I comma P？Yeah。Ninimum weight。To get。Value。Exactly V。Using。Only items。

From the set。One up to I Okay， and I'm not going to do it。

 You can set up a recurrence to fill this table out as well。I think they're just。

They're just different algorithms。Yeah。Yeah， I think we're just。Okay， so great。

So now what we want is we want。Good approximation algorithm。So what's the- okay。

 so we know how to do exact integral Napsack。And we know how to， but it's slow， right。

 We don't like W。 We want log W。And we know how to do。Exact fractional k Napsack。

So what's the natural greedy algorithm that the exact fractionalnapsack adjust to us？Yeah so。呃。

Approxiation。Algorithm。Attempt。For integral k Napssack。Sort by。VI over WI。Keep。Taking。Items。

Till there's no space。Okay。So I claim， though， that we're going to have to tweak this algorithm。

 but I claim that just as written。We can do very badly。

Anyone have an example of an input where we would do badly？Yeah。Because's one one。所。Right。

 so you're saying there might be an item that has a better ratio。Which has a very small。

 a very small weight and very small value， but just a better ratio。

 But then there's a big item that has a lot of weight。That once you put the first item。

 you can't fit it。RightSo that's right for example。Bad case。You could imagine。For example。

 v1 equals 2 and W1 equals 1。Whereas V2。Equals W and W2 equals W。All right so。

Greedy would take this item first because that has a better ratio， but then you can't fit this one。嗯。

So。ThisWhere Op would have just taken V2 and gotten W value。

 So this implies that you get an unbounded。Or。Really， you know。Not better。Then。

 and I could have made this， you know， one plus epsilon。Not better than a W approximation。

that's not great。Here's a modified greedy algorithm that a claim does pretty well。Take either。One。

 the output of greedy。Or two。The most valuable item。I'm pretending。

 I imagining that I've already filtered out items that have weight bigger than W。 I mean。

 if an item has weight bigger than W， there's no reason to。Acknowledge its existence。 Okay， so claim。

Is that this algorithm？Is it to approximation？Okay。And we're going to prove alemma。

 and then we're going to see how to。Explainit that lema to get a Ptas。Okay， so。Let me write ama here。

 ma1。🤧嗯。Suppose。Greedy。Takes。Items。呃。V1 over W1 going equal to V2 over W2。

greater than equal to v k minus1 over w k minus1。Then。No room。For。Case item。Then。

The sum I from 1 to K。Of V I。Is it at least opt？Okay that's dilemma。So proof。

The proof that modified greed is a two approximation。Well。

I claim it follows immediately from thellmma， Why is that？

Are people okay with the statement of dilemma？Yeah。Ms。 Iidian。うか？メくだもた。The wise。So by the way。

 this sum includes VK。Yeah、そい。Yeah。Yeah。だごとが。Yeah， right。wasn go。Right， right， I mean， right。

 or another way of saying the same thing that you just said is this sum of V from Is1 to K is just。

V1 plus thatt up plus vk minus1 plus vk。One of these。Is at leastocto two。By dilemma。Right。Okay。

 so that's the proof， so now we just need to prove this thing。So how would you prove this slemma？

And I claim。You should think about this thing。Yeah。的かじ。Yeah， exactly， right。

So we know what optt is for this thing。upp for this thing。Would take the first K -1 of these items。

 and then it would take some fraction That's less than one of the last item。Okay。

So we know that that's what Op would get， the optimal profit for the fractional solution。

And we know that the integral opt can be at most the fractional opt。And this number is at most。

 this number is bigger than the fraction optt right because we're not just taking a fraction of the K element。

 we're taking the whole thing。So proof is that。The sum equal equals 1 to k of V。Is even bigger？Then。

Fraactctionional knpsacks opt。Okay， so that's it。So now I want to give a PT。Okay。

And I think the main。Observation that I want to use for this Ps is that。If。If no item。Has value。

Bigger than Epsilon timess optt。Then。Greedy。Achievees。At least one minus epsilon opts。Okay。Yeah。

 so I should say I defined PAS， FAS， et cetera for minimization problems。

 but you could also define them for maximization problems。

So with the minimization problems you want to get at most one plus epsilon opt for maximization。

 you want to get at least one minus epsilon opt。O。So why is this true？

This is true because of dilemma。Right。So greedy gets the first k minus1 things in the sum and misses out on the kth。

But if no item has value。If no item has value more than epsilon times optt then missing out on the k is that most losing as epsilon times optt。

 So the sum of the first K -1 is at least one  epsilon。Okay。So。Also。This is observation1。

Observation2。Is at most。One over Epsilon。Items。Can have value。At least Epsilon optt。

Or better than have salilon time left。Now， well what do I mean by that at most one of us on items？

In the optimal solution。Have value bigger than Epsil up。Otherwise， optt would be better than optt。

Okay， so now。What's a PTTS， Remember， Epsilon is a constant。Okay。

So let's give me some algorithm that given a fixed epsilon runs in polynomial time。

Your exponent is allowed to behave。As you want in terms of Epsilon。Yeah。くである。Yeah， exactly。

 so the algorithm， so just to repeat what Yarick said。This is just an algorithm algorithm。Gues。A set。

S。Of size at most one of epsilon。Gues it set S of Pism minus1 or epsilon。Which。Would be。

A set of elements。An optimal solution。A value。Bigger than epsilon。Time's opt。That's step one。Two。

 and you're going to put S in your output。Well， you first we' going to check to make sure it actually fits in your。

In your knapsack， if not， just keep going on in the loop， continuing in the loop。

If it does fit in your Apppsack， you guessed S， then2。Remove。All items。Remaining。Which have。Value。

Bigger。Thenhan anyone at us。So S is supposed to be the set of items。With value， at least Epsilon opt。

 Okay， so now that we've guessed S， we can remove all the items which have value bigger than them because we're assuming that that is the set of big items。

 And then three。Run greedy。On what's left。What's the running time of this algorithm？Yeah， so and。

To the one of Epsilon plus one。Or。Yeah， I guess there are some Ms here。

 depending on how many sets you have， so let me just say。Oh then to the one over on times， you know。

 Paully Evan Adamerson。I'll be less specific。Okay。Re claim。Is that our profit？

Is at least one minus epsilon times opt？What's the proof of that？So。Suppose。In some itration。

 we're actually going to guess S correctly， suppose we guess S correctly。We know that optivs。

We know that optt is equal to the value of S。So the sum of the values of items in S plus opt prime。

 which is the best。Packing。Of the small items， the items。With value at most。

 with value at most any item in S。Meanwhile， what do we achieve， achieve？V of S。Plus。Greedy。Plus。

 you know what greedy achieves。So we need to show that this thing here is at least optt prime minus epsilon minus epsilon of optt。

 let's say。Okay so greedy。What do we achieve with greedy？We know that。This item VK。😡，V K is。

 K is the last I is the is the item that we don't take。 The first item we don't take， right。

 What do we know about V K。I mean。We know something from here know that。

We know that we filtered out all the items of high value。So we know。We know that。

VK is at most epsilon times opt。Because is the set of containing S is the set of items with Epsilon optt。

Value for each item。And we also know。Ne greedy。The greedy output plus Vk is at least opt prime。

 That's Lamma 1。Which implies that greedy。Achievees。Ot prime。

Achiees at least up prime minus epsilon times up。So that's it。 Okay， so that's。That's it。

Questions about that？Okay， so if there are no questions。

 I guess next time I'll show you an FP task for NapsSAC and an FP for another problem。Next week。

 I will not be here。But。We'll have two guest lectures， one on Tuesday， one on Thursday。

 because I I won't actually be in Cambridge。 I won't be here for office hours， but I'm very happy to。

 you know， if someone wants。If people want to attend my office hours。

 I'm very happy to do Google Hangout or something。 Okay。

 so you should send me an email if you want to chat。嗯。Very good and yeah， as I said。

 PS at4 will be out tonight。