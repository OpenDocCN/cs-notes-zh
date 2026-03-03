# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p17 -17-Lecture 17_ Linear Programming and Approximation Algorithms).zh_en -BV14CAUeUEPj_p17-

All right， so I want to keep on talking about approximation algorithms and again。

 one of the takeaways from approximation algorithms is that all of the design paradigms that you've studied over your education so far are super useful for approximation algorithms and so this lecture is going to be about how one of the design tools that you just got this quarter。

 namely linear programming how that gets used an approximation algorithm design and in some ways it's sort of a match made in heaven because remember know a key challenge in the design and analysis of approximation algorithms is getting a handle on what the optimal value is sort of minimum cost of a tour。

 the minimum makes span of a schedule， whatever and now often it's hard to get a handle exactly on what the optimum is after all it's usuallymp completelete to compute but so what you wind up doing is you prove bounds on how good the optimal solution could possibly be so you you identify quantities that are only better than opt you use that as a yardst to compare the solution of your own algorithm and if you're within a factor alpha of something which is better than opt then you're certainly within a factor of alpha。

The optimalim solution as well。So the question then is you know where do these bounds。

 where do these things only better than opt come from so last week we saw a couple ad hoc examples so like for scheduling we looked at the maximum job size。

 we looked at the average load for metric TSP we looked at the minimum spanning tree but if you think about it know when we talked about duality the whole point of dual linear programs was to give you bounds on how good the optimal solution could be and indeed dual feasible solutions turned out to be the key to a lot of kind of the state of the art approximation algorithm so I'm going to give you a glimpse of that today。

Actually， I want to start with a problem where we're initially not going to use linear programs。

 It's going to really be kind of a continuation of our lecture a week ago。

 which we concluded with set coverage， So I want to talk a little bit about a variant。

Called the set cover problem。So the input is exactly the same as in set coverage。

 there's some ground set you， I give you a bunch of subsets of it each just a list of elements。

 there's no budget though， okay， there's no K。So while in set coverage。

 the hard constraint is that you're only allowed to pick k sets subject to that。

 you want to cover as many elements as possible， those are reversed in set cover。

 The hard constraint is you have to cover everything subject to that you want to do it using as few of the subsets as possible。

So pick as few subsets as possible。Subject to the union of the subsets you pick should be all of you。

So for example， if this is your ground set and S1s the top half， S2 is the top half， bottom half。

And maybe there's a different way that it's partitioned S3， S4 and S5 here。

 the optimal set cover is going to use two sets， I you' just going to pick S1 and you're going to pick S2。

S3， S4 and S5 would also be a set cover， but it uses three sets， so it's not as good。

So that's the set cover problem。Clear。So we allow you to pick as many sets as you want。

 but you have to cover everything and you again want to do it sort of as economically as possible。

All right， so。This is another NR problem。You it's NP hard basically for the same reasons that set coverage is NP hard and again the tension of which sets to pick is the same as before。

 on the one hand you want like big sets， but other hand some sets largely just are redundant with other sets where some are sort of uniquely useful so you have to balance that tension between the size of a set and sort of the other possibilities of covering those same elements。

Okay。So。The greedy algorithm that we discussed for the set coverage problem again makes perfect sense for the set cover problem。

So what was the greedy algorithm for set coverage。 Well。

 we just kept picking the set that covered as many new elements as possible。 We were only allowed to。

 you know， pick K set。 So we stopped after K iterations。 So we're again going pick the set。

 which covers as many new elements as possible。 We're just gonna run into completion。

 We're gonna run until we've covered everything。So greedy algorithm。Yeah。

So C is the collection of subsets that we've chosen。So wow seeing not a set cover。

At to see the subset Si。Okay。Covering。The max number of new elements。Okay。So as usual。

 when you're thinking about picking a set， the elements which have already been covered by previous sets don't count。

 okay， you're only looking at the new progress you're making relative to the union of the previous sets that you've already chosen。

And then you just return this collection。Okay。Its everyone clear？On the greedy algorithm。So again。

 just use the one from last week but let it run until it's a cover obviously if there is a set cover。

 it's going to find one， if nothing else it'll just pick every set。

 so the only question is you know how good is the set cover in terms of how many sets it uses compared to the minimum possible。

 the minimum size of a set cover that's sort of the key question。All right， so。

We're not going to get a factor as impressive as for set coverage， but we'll get something。

So what we're going to prove next is that greedy。Is a natural log of n。Approxiation。Okay。

So I should say we don't expect this to be optimal certainly because it's an n hard problem and it's obvious you could implement this in polynomial time and actually if you want concrete examples where this won't output an optimal solution you can just go back and look at exactly the same examples we discussed for set coverage so the first example will show that there might be a set cover of size2 but this greedy algorithm will output one of size3。

 the second example from last week will show that even when there's a set cover of size3。

 the greedy algorithm might output something of size 5 and there are worse examples than these as well。

So we expect it to be so optimal by how much， well。

 this is the upper bound we're going to we're want to proof。Oh so what's N？I should say。

Where N is the number of universe elements。 If you stare at the proof closely。

 you'll realize we actually prove its natural log of the maximum size of a subset。

 which could be much smaller than the size of the universe。

Let's just prove this version for simplicity。So this is the first result I'm going to talking about today。

 we're not going to use linear programs。Actually， for this。

 we're going to be able to really nicely piggyback on our understanding of the set coverage problem。

And so that allow us to really quite quickly prove this guarantee。

So let's remember what we prove for set coverage， we prove that no matter what the collection of subsets is。

 no matter what the budget K is， the greedy algorithm will output something that covers at least a one minus1 of refraction of what the best possible collection of k sets could cover so that's the what we proved last time a 1 minus1 of re approximation。

And now， notice。So think about our current greedy algorithm and just sort of zoom in on the first say。

 like 10 iterations of this greedy algorithm for set cover。

Now think about if we ran the greedy algorithm per set coverage on the same set system with a budget of 10。

Any difference between those two algorithms？Exactly the same right Every iteration。

 you just pick the set that covers the largest number of new elements。 Okay。

 so iteration by iteration， these algorithms are the same for set cover and set coverage。

 The only difference is the stopping condition， set coverage， you stop after K iterations， set cover。

 you stop when you've got a set cover okay when everything's covered。So。

What's the point Okay so imagine。That there exists a set cover that uses only 10 sets。Okay。

And now imagine in our minds， imagine we ran that set coverage approximation algorithm with a budget of 10。

Well， we know it's a1 minus1 of re approximationroxi。

 if there's something with size 10 that covers everything， with our 10 sets。

 we're going to cover at least a 1 minus one of a refraction of everything。Okay。

So that's what happens with the first 10 sets， we get at least one minus one already covered。

All right， so rather than 10， let me just say opt for the number of sets in the best set cover。

So the first op subsets。Cover at least one minus 1 over E times u elements。Okay。Again。

 there exists a solution with offsets covering all of you and the greedy algorithms of 1 minus1 over your approximation。

Now， this set cover algorithm is not going to stop after just picking offsets unless it's lucky enough to already cover everything。

 it's going to keep going。But the point is that within opt iterations。

 it has shrunk the number of elements it has to cover by a factor of E。

1 minus1 over E at least got covered， and most of one over e fraction still needs to be covered。

So opt iterations shrink the universe size by a factor of E。Okay。That's true。

 not just for the first batch of opt iterations， right sort of， you know。

 the second batch of opt iterations can just be thought of as a sort of residual set cover。

 set coverage problem and the same guarantee continues to hold。So every opt iterations。

This algorithm reduces。The number of uncovered elements。By a factor of in most， sorry， at least eat。

Okay， so you divide by E every time you do optt iteration of the greedy algorithm。

How many times can you do this Well， you know you're done once you have less than one uncovered element。

 you start from n， you're dividing by E every time， remember that the natural logarithm is log B E。

So。We're done。Meaning all elements covered。Within at most。Ot times the natural log。

 Ie log base E of n iterations。Okay。So Opt is theest smallest size of a set cover and the greedy algorithm will get you that number of times the natural log event。

Okay。So there any questions about that？Yeah。So we actually actually sort of the point of this is we are already。

 you know， again， so we could reuse the tools from last week to just solve this problem quite easily。

 which is good okay。It's a basic problem， set cover。

 the motivations are very similar for set coverage。

 right we mentioned a lot of applications of set coverage。

 You know it's just the difference sort of which is the heart constraint and which is the objective You could imagine。

 for example， if you know you're trying to locate fire engines you know in a city。

 maybe it's a hard constraint that you really have coverage to all of the neighborhoods and then the natural objectives just to minimize know the cost or the number of fire stations so it's going to depend on the context。

 which one's the heart constraint and which one you just want to do as well as you can。Okay。

But actually， when set cover arises in applications。Often not all the sets are the same， right。

 So like some neighborhoods might be more expensive to build them than others。

 Okay So in the usual set cover problem。This is what we're going to discuss next。

We still have this input， we still have this collection of subsets。

 but also each set can have its own cost， possibly different for different sets。Okay， so cost C。

For each SI。All right。The goal now， of course， is to compute the set cover with minimum possible total cost so the previous problem corresponds to all of the Cs being equal to one。

Now， in set coverage， there were no costs， right？So once we talk about set cover with cost。

 it's not clear how to piggyback on our set coverage analysis to very quickly prove something。

That's the bad news。So we're going to need some other idea。

The good news is the idea that we need is really only the analysis， as far as the algorithm。😊。

It's pretty easy to think about extending the greedy algorithm to when sets have costs so like if one set costs twice another。

 maybe you're only tempted to pick it if it covers at least twice as many new elements。

 that's sort of the obvious extension of the greedy algorithm and so then that turn out is going to work well。

Okay， so what is the greedy algorithm with costs？I always pick。The subset S I。With the minimum。

I'm going to call it a ratio。Which is the cost of the set。Divided by the number of new elements。

That the set covers。Okay。So in other words， it's the average cost。

Per new element that you're covering， okay？So if the set costs 10 and it's covering four new elements。

 it's going to be 2。5。Okay， notice that if all of the costs are one。

Minimizing this is the same as maximizing the number of new elements covered。

 which is exactly our old algorithm， so this does indeed specialize to our previous greed algorithm and all of the costs are the same。

Okay。Is everyone clear on the new algorithm？You just use this different criterion。In the main wild。

Yeah。And so the good news is even with costs， the greedy algorithm is still just as good as it was before。

It's still a basically login approximation。And again， the n is really the maximum set size。

So that's what I want to prove next。Okay。The greedy algorithm still works even when there are costs。

Now here it's not clear how to prove it because again we can't piggyback on our set coverage analysis so what I'm going to do is I'm going to give you a direct argument。

So we'll just see a proof and then we'll zoom out and we'll recognize that the proof that we just did was really using a dual feasible solution and weak duality。

 That's really what's going to be going on in this argument。All right。

 so what's our strategy for the analysis， How we're going to prove a band on on the greedy algorithm。

 Well， you know， as always， you know， when you know。

 you're proving a guarantee on a greedy algorithm， you better use the fact that it's greedy somewhere in your proof。

You need to use what its greedy criteria is， so let's go ahead and get that out of the way first。

It have a very simple lemmo。Which is where we use the definition of the greedy algorithm。

So this will be familiar from a similar but harder lemma。

 slightly harder lelemma that we had a week ago for set coverage。

So suppose the current greedy solution。All right， so imagine we've been running the greed and we' run for 10 iterations。

 Okay， We're going to look at some subset S。 Okay， any of these input subset S。

So after 10 iterations， some of the elements of SI will be covered and some will be uncovered。So。ど。

Call L， the number of elements covered by Si at this time。Look， can we conclude， right。

 so a week ago， we wanted to say that you know， the greedy algorithm made healthy progress at every step。

 That's sort of what we were doing Here。 we're going to say， well， you know。

Would it prove an upper bound on how big this ratio could be of the next set chosen by the greedy algorithm？

So next set chosen by greedy。Has ratio。At least， sorry most， the cost of Si。

Divided by the number of elements of SI， not yet covered。Okay。

So if you've understood everything I've said so far， this is like totally immediate。Okay。Why， well。

The greedy algorithm of the next iteration has the option。Of picking the set S。If it picks the sit S。

This is the cost that will be incurred。 This is the number of new elements that will be covered just by the definition of L。

Now the greedy algorithm picks the set with the smallest ratio。

 so it'll be at most the ratio would attain if it achieved SI。Okay。So that's it， so that's the proof。

So any questions about the lima？So in set coverage we said， oh。

 well as long as the greedy solution is far from optimal we're going to make healthy。

 we're going to cover a lot of elements now what we're saying is you know if there's some set where we haven't done a good job of covering much of it。

 it's because we're picking cheap sets or sets with small ratios。

 a small average cost per element coverage。Good。So notation。For the analysis。We're going to define。

For elements。Kidy。Will be the ratio。Of the first set。The first subset。嗯。It's a cover E。

In the greedy algorithm， Okay， so think about it this way。

 we zoom in on the 17th element of the ground set。We watch greedy run。

 the greedy algorithm terminates with a set cover， so at some point it's got to pick a subset that covers this element number 17。

We look at the first iteration where it gets covered， where it gets newly covered。

 we look at the ratio of the set that's chosen in that iteration， that is QCB。

Okay so every element just says， oh yeah， the ratio of this first set to cover me was this。

I'm using this notation Q subB to sort of perhaps remind you of the Q values we talked about when we analyzed online bipartite matching。

 as we'll see something very similar is going on with Se cover。So maybe just a quick example。

Right so if you imagine that。Sort of a very simple set system， say this was the set system。

Let's say all the costs were one。So greedy is just going to pick the biggest set first if all the costs are the same。

 so each of these gets a Q value of what？Was it。1 by three。So when we pick this， the cost is one。

 the number of elements covered for the first time is three， so the set has a ratio of a third。

 everything that it covers newly gets exactly that as its Q value。Okay。

SimilarSo then what happens next well so in the next iteration of greedy this covers two elements newly。

 this one only covers one element newly， so the greedy algorithm will pick this one next again its ratio is one over two。

 so both of these get a Q value of12。Now， in the final iteration。

 greedy has no choice but to pick this set。It only covers one new element so the ratios1 over one。

 and so this one gets a Q value of one。Okay。Good。So I need- so let's do。Let's do the next step。

So so what， how do we use this lima？Well。This lemma gives us an upper bound on how big the Q values of the elements of a set can possibly be。

So fix your favorite subset S。Think about the Jith element of Si to be covered。By greedy。Okay。

The Q value。Of this element E。Is it most the cost of this set？

Over the size of the set minus j minus1。How should you think about this， okay？

So here's the way to think about it。😊，So imagine J -1 elements have already been covered。

That's just like plugging in j minus1 for L in the lima。So if only J minus1 are covered right now。

 at some point there'll be a set which covers this Jth element to be covered。

 and the lemma is in effect， so Ill say that whatever set is used to cover this Jth element has ratio at most the cost of this set S divided by the number of still uncovered elements in S。

 which is the size of S minus J plus1。Okay。It may also help to look at this figure。Okay。

So let's say for this biggest set， the set of size three。Now。

 one thing that's a little confusing maybe is as you can see in this figure。

 the greedy algorithm doesn't exactly cover the elements sort of one by one in general it covers a batch of elements in the same iteration so like for this set it covers all three of them in the same iteration。

 so they all get a one third。But if you think about it。

 that's fine for this What is this asserting for a set of size3。

 it's saying that that the first element to be covered has a Q value of a most a third。

 if the cost is one， the second element to be covered as a cost of most a half。

 and the third element has sorry not a cost， a Q value of most a half。

 the third element to be covered has a Q value of at most one。Here， it's only more true， right。

 It's one third， one third， one third。Similarly for a set of size2。

 this corollary says the first one to be covered should be a most one half。

 we're doing even better than that， we have a third。

 the second one to be covered as cost of most of one。

 and indeed that is in fact the Q value of the second one to be covered okay。

So the way to think about the proof of this is just first thing about the special case where you have this set S and literally each element gets picked off in a different iteration I guess really in the first iteration。

 the first one gets chosen and the second iteration is set containing the second one gets chosen and so on then it's easy to see why this holds it's really just you substitute J minus-1。

 the number of predecessors of the j elements for L in this lemma and then you realize oh if they could covered in batches actually the Q values are gonna to be even smaller because that means at the time I was covered there were even more uncovered elements。

 even fewer covered elements than there was in the case where to get picked off one by one and so it's going to be only more true just like in the figure。

All right， so any questions about that？All right， so that's how I use the greedy algorithm。

 we use the greedy algorithm to say to basically get these upper bounds on how big the Q values of elements of a set could be。

So let's just sort of compile this information。So for all subsets， SI。

How big could the sum of the Q values of elements in the set SB？Well。

There's the first one to be covered， so that's taking J equal 1 in the corollary。Sorry。

Taking J equal to1 in the corollary， there's the second one to be covered。

So that's taking j equal2 in the corollary。The second to last one。

We'll have a Q value upper band of C over two。And then the last one to be covered C over one。Okay。

 so it's just applying that corollary for each of the elements in the set S。So if you look at this。

This is just is approximately， so bring the C out。We're left with this harmonic sum。

 one plus a half plus a third all the way up to one over the set size。

 that's basically the natural log of the set size， being slightly sloppy。

 there's an extra additive term known as Ogular's constant here， but that's less than one。

 so I'm just going to ignore it。So this sum is bounded above by basically the set cost times log of the set size。

Which of course， is the most in the worst case。CI times the natural log of the ground set size。Okay。

So that's the first thing to notice greedy gives us sorry ourlemma gives us control over how big Q values can be。

 so therefore of course there's some kind of bound on the sum of the Q values of the set。

Here's the second property we'll need and then we'll basically be done。Again。

 this should perhaps remind you of what we were doing with online bipartite matching。Yeah。

Which is if you look at the sum of all of the Q values。

It's exactly the same as the cost of the greedy solution， the final greedy solution。Actually。

 I claim this is an invariant of the greedy algorithm。 Okay， this is true at all times。

 and therefore， in particular， at the conclusion of the algorithm。 It's clearly that true initially。

 all the Q， I guess I forgot to say this。 But you， all the Q values we think of as initially being 0。

Before that any of them have been set and the initial set cover， we don't have any sets。

 so there's no cost。So let's imagine when a new set gets added。

 Okay so it's just going to prove that this stays true with every iteration。

 So think about iteration， the greedy algorithm picks some set S， that set has some cost C。

So the right hand side goes up by exactly C in the iteration。What's up with the left hand side？Well。

 who gets a Q value？So remember， when does an element get its Q value。

 it's when it gets covered for the first time so the set S that got we just chose。

 that's going to trigger all of the newly covered elements to get a positive Q value。

 What is that Q value， Well by definition， is's just the ratio of the set we're picking in this iteration。

Okay。So let's see， so left hand side。So let's say when greedy picks。S I。

 clearly the right hand side goes up by C， Left hand side goes up。Bye。

Number of newly covered elements。Times whatever the Q value is， the Q value is the ratio of this set。

 and just by definition。 What's the ratio of a set。

 It's the cost of the set divided by the number of new elements covered。

 So the number of new elements covered in the denominator cancels with this。

So this is just equal to C。So those are sort of the two technical facts that we need and now we're basically done。

 So any questions about one or two。Okay。So， again， just at a high level，2 saying that， you know。

 these Q these Q values are are a proxy for the cost of greedy。

 And this is what we want to upper bound。And then you look at part one and you're like， oh cool。

 this gives me like a set by set upper bound on how big these cues should be。

 so that should translate to some upper bound on the greedy performance。

So Im going to put all the pieces together。So conclusion。

So the greedy cost is the sum of everybody's Q values， right that was just 0。2。

Now we need to relate this to the optimum。So let me write the following。Take the optimal set cover。

Some over each of the sets in the optimal set cover。Now the optimal set cover， it's really good。

 but it supposed to be a set cover， so each element appears in at least one of the sets that it chooses。

So if we sum over each of the sets that it chooses and then sum over the elements in that set。

 we count every element at least once， possibly more if optimal sets overlap。

so by summing over the optimal sets and then summing over the elements in the set。

 I only overcount the sum of all the Q values。So now we use。The first part that's set by set。

 we have a good upper bound on how big the sum of the Q values could be。So again。

 sum over the subsets chosen by optt。Here we have C。Times natural log of n。

So bring that login out and of course， sum of the costs of the sets and opt is just opt。

 just the cost of opt。And that completes the proof of the login approximation for greedy set cover。

 even when sets have costs。So questions about that？It might seem a little mysterious。I mean。

 you know this lemma was natural enough， we wanted to use the fact it was a greedy algorithm。

 this just kind of fell out of the fact it was a greedy algorithm。

 then we kind of crunched some numbers and we got what we wanted。

 but then yeah that's a little unsatisfying。 It's hard to you know you might be asking you how would you replicate this for some different problem。

 seems like kind of an ad hoc analysis。So what I want to do next is I want to give an interpretation of this proof in terms of linear programming duality。

 okay weak duality。然。So in some sense， they're going to prove the same theorem。

For the same algorithm。But。really， we're just going to reinterpret the proof we just did is really a better way to phrase it。

Okay。So questions before we do that？Dual interpretation。All right， well， for they be a duel。

 they better be a primal first。 So let's start there okay。

So let's start with something which is a linear program that's obviously related to the set cover problem。

 well to talk about the exact relationship， but it's clearly related。

So the decision variables are going to be X。this intended semantics are if Xi equals 1。

 you pick the set SiI， if Xi equals 0， you don't pick the set SiI， C is the cost of Si。

So you're picking sets， the xs say which ones you pick， what's the constraint。

 the constraint is it has to be a set cover， What does that mean。

 it just means every element should appear in at least one of the chosen sets。Okay。

So we're going to have for all elements in the constraint。

We're going to have at least one that should be chosen at least once。What do we sum over。

 we sum over all of the sets I so that E belongs to S， and at least one of those better be one。And。

It doesn't really make sense to have negative numbers， so let's say exercise is non negative。

You might think we also want the constraints that exc of most one， but actually those are redundant。

 you don't really need them。All right， so。What's the relationship between this linear program and the set cover problem？

Well， the set covers。Are in one to one correspondence。With01 solutions of the linear program。

And the cost is preserved。好师。So in other words， if you give me a set cover。

 I will just set the Xs to be0 or1 accordingly， and I'll get a feasible solution。

 the linearar program and its cost will be equal to the cost of the set cover， and I can map it back。

 give me a zero1 feasible solution， I just pick the sets whose X equals  one。

 and that'll give me a set cover the constraints enforce that。All right。So any questions about this？

This is sort of hopefully very simple， but important。Okay。So set covers correspond to0，1 solutions。

 Now， of course， you know， linear programs are not， you know。

 they don't need to return to you something that's only zeros and ones。

 Linear programs are allowed to use fractions。Now we saw a couple examples in the first half of the class where fractions didn't help the linear program。

 You're always guaranteed to have an optimal01 solution。 First we saw that with minimum cuts。

 and then we saw that with bipartid matchings。 So those were two really happy cases where actually the linear program although those not obvious it always gives you zeros of ones is the optimal solution。

Now， for Se cover and for this linear program。We do not expect to always get 0。

1 solutions back as optimal solutions。What would that imply if we always got back zero in solutions？

The opposite of p equals NP is what it would do。Right so， so the set cover problems np hard。

We can solve linear programs in polynomial time， we've talked about that。

 So if solving linearar program just gave you a 01 solution that happened to be optimal。

 even overall all of the fractional solutions， well then boom。

 there's your optimal set cover just on a silver platter handed to you by the linear program。

So we don't expect that to happen。 Okay， so we don't expect to be able to solve offset coverage with linear programming。

 which means we expect that fractions can help。So to see why fractions can help。

Consider the following very simple example。Three elements in the ground set。

And the collections are all possible pairs。Okay。So that's a set system。

It should be quite clear that all the costs are one。

It should be quite clear that the best set cover has two sets， right， no one set covers everything。

 so you need two。But with fractions， you can do better。If you pick each of them to be one half。

Fractionally。Then since each element belongs to two sets。

The sum of the fractions of the sets the container will be equal to one。

So that gives us a feasible solution。And this feasible solution has objective function value。Only 1。

5。So that's really seeing it in action。 How the linear program， it's NR problem。

 whenever you have a linear programming。A linear your program related to it。

 you're going to expect sometimes you get sort of nonsensical answers。 Okay。

 You're going to get things that are better than not， strictly better， potentially。All right。

What we build terminology。So a linear program like this is called an LP linear programming relaxation。

Of the set cover problem。Relaxation in the sense that it has only more stuff。Okay。

 so every set cover corresponds to a feasible solution。

 but there can be other feasible solutions as well。 Okay， so it's not an LP formulation。

 it's an LP relaxation because you have other things in addition to the set covers。

And whenever you have an LP relaxation in this sense for a minimization problem。

There's a clear relationship。Between the objective function value of the best fractional solution and the best set cover。

 the best 0，1 solution。So which way does the inequality go， which one is smaller？

Remember it was a minimization problem。Yeah。Fal optimal is smaller。

 Why because it has only more stuff to minimize over。 So the minimum is only going to be smaller。

So connecting this back to what I said at the beginning of the lecture。

 what's the whole sort of name of the game and approximation algorithms bounds on the optimal solution。

 so here's where we're seeing this。 When you have an LP relaxation。

 it gives you bounds on the optimal solution。 Okay it's only better than opt if it's a relaxation。

Okay。So any questions about this， the LP relaxation of Se cover， so this is our primal。

 this linear program。Okay， so let's look at the dual then。So the do。

 I'm just going to apply the standard recipe， which we spent some quality time with a few weeks ago。

This should be men， by the way。All right， so we have a minimization primos。

 we're going to have a maximization。The objective function is going to be the old right hand side。

 so those are all just ones， the decision variables are going to correspond the constraints。

 we're going to have one decision variable per element。

I'm going to use PCB as our notation for dual variables。

 this again is sort of meant to evoke previous things that we've done。In particular， with matching。

Okay， so we know we're going to have one constraint for each variable。

 so we're going to have a constraint。For every SI。We know that the right hand side is going to be the coefficients in the objective function。

 so we have a C here， this is a max， so we have a less than or equal to here。

If you work out what the transpose does。Here we're just going to be summing。

Over the elements in the set Si。Of their dual variables。这样。So those are the dual constraints。

If you like， you can think of this as sort of a price of an element。

And so this is just saying that for each set， the sum of the prices of the elements it contains should be bounded above by the set cost。

And then all'll do a variable should be not negative because we have inequality constraints。Okay。

So that's the duall just using our standard recipe。And remember， what's the meaning of a duel？

The meaning of dual feasible solutions are bounds on the optimal primal objective function value。

 So here are primals minimization。 So these are going to be lower bounds on the。

Objective optimal value of this， so that's just weak duality。So if P a vector indexed by edges。

It's feasible。For the duall。Then。It's dual objective function value。Is a lower bound？

On the optimal solution of the linear program， Ie the fractional opt。Which， as we said。

 because this of relaxation is a lower bound on the op that we actually care about。

The minimum cost of a set cover。Okay。So again， this is weak duality。

This is because it's an LP relaxation。What's the point， the point is， remember。

 we want good lower bounds on how small the best set cover should be okay so any dual feasible solution provides us with such a lower bound。

Now。Let's reinterpret our sort of previously somewhat mysterious computations one and two in terms of this dual linear program。

So this fact one， the fact that the sum of the Q values。As we define them in the previous analysis。

I it most， the set cost times log n says。That if we scale down the Q values。By a logarithmic factor。

Then actually we're going to satisfy the dual feasibility constraints。

 what does dual feasibility say says the sum of the prices is at most the cost of a set。

What does this statement say that says that some of the Q values is most the cost of the set times log in。

So if we scale that down by log N， we'll recover dual feasibility。 and again。

 this should remind you of when we were scaling things in online biheid matching。

 we scaled cues to get Ps， which were dual feasible。

So if we' defined the vector P to be the vector Q as we defined it previously。Divided by log in。

This is feasible for the dual linear program。Sorry， one implies this。Or this is what？All right。

 so let's look at2，2 says that the sum of the Q values is exactly the same as the cost of the greedity solution。

 so once we divide， we can say the cost of the greedy solution is a most log n times the sum of the P values。

So cost of greedy。Equals。Vlogin。Because of the scaling。Some of the P values。Okay。By part one。

 we know this is a dual feasible solution。So by weak dual and the fact it's a linear programming relaxation。

 we know that this is a lower bound on the optimal solution。So this is a most log n。Time's out。Okay。

So what was the point of these steps1 and two， the point of steps1 and two was just to。

 given what the greedy algorithm did to expos facto come up with a dual feasible solution justifying its decisions and proving that its solution is near optimalum。

That's really what was going on with the definition of these cus。

 controlling how big the sum of the Q values could be， it's really a dual feasibility argument。Okay。

All right， so that completes the reinterpretation of our set cover proof。Any questions about that？行。

What's the， like， what's the relation between the second implication and the。这点扣款。

So in this inequality。I'm using weak duality。So for here here。

 it has nothing to do with linear programming。 The equation has nothing with programming。

 This is really just like by construction of the Q values， this is true。

 And then you pick up the log factor just because P is Q scaled by log。

Then the question is the question is more like what do the sum of the P values have to do with anything？

So ultimately， we need to relate the left hand side to the cost of an optimal solution。

And so some of the prices are sort of intermediary for that。

 And so where linear programming comes in is we really need this to be feasible for the dual solution so it's feasible dual solutions it gives us bounds on the optimum。

 So that was the point of part one， par one says that actually this really is a dual feasible solution。

 this is the dual objective function value。 And so by this argument that gives us the lower bound on the optimal solution。

Does it make sense？Okay， thanks for the question。Other questions？All right。

So the set cover is sort of interesting because the algorithm。

 you certainly don't need to know linear programming to come up with that algorithm。

 anybody could come up with that algorithm if you have some good intuition about greedy algorithms。

As we saw from the first proof， you don't even really need linear programming to do the analysis。

 though it is much less mysterious and it feels much more systematic if you know linear programming。

 the analysis。But so now I want to think about an algorithm which uses linear programming。

 not just in the analysis， but actually in the algorithm itself。

So there's going to be an approximation algorithm where one of its steps is to explicitly solve a linear program so again。

 that sort of that's a high level takeaway is that you know in the same way that when we're talking in the first half of the class。

 we said sometimes you really solve a linear program and that's really what your algorithm is sometimes you just use it to prove some other faster algorithms correct like the Hungarian algorithm so same thing going on here sometimes we use linear program just to understand what a sort of fast algorithm does。

 but sometimes we really actually use it as a subroutine。

So I want to illustrate this point with the vertex cover problem。

 so you studied a polynomial time solvable special case of the vertex cover problem on problem zip2。

 let me remind you the definition。So I give you an undirected graph。With costs on vertices。

Non negative costs on vertices。Okay。And the responsibility of an algorithm here is to。

Choose a subset of vertices。So that every edge has at least one of its endpoints chosen。

So you're picking vertices and they should hit every edge， at least one of their endpoints。Of course。

 you know， you could pick all the vertices。 that would be a vertex cover。

 but so subject to being a vertex cover， you want it to have the smallest possible cost。

So the men cost subset of vertices。Such that has at least one endpoint。Of every edge。Okay。

So that's the very this cover problem。As you saw， it reduces to max flow and bipartite graphs。

 but in general， this is an MP hard problem。Okay。So the first algorithm I want to show you for vertex cover。

Is going to explicitly solve the linear programming relaxation。

 So this is the linear programming relaxation for set cover。But actually， if you think about it。

 vertex cover is really just a special case。Ops set cover。she that。

So what's the ground set in the vertex cover problem？In other words， what's getting covered？Edges。

 right， so for each edge you need to cover one of its10 points。

 So the ground set correspond to the edges。Which means that the subsets need to correspond to collections of edges。

And they should also send out correspondent vertices presumably。 So if for given vertex。

 you look at the incident edges， and that corresponds to the subset of elements that it covers。Okay。

So verth cover is a special case of set cover。With elements corresponding to edges and vertices corresponding to sets of the incident edges。

So let me just rewrite this a little bit， so of just really change notation， but it's really。

 I want to emphasize is literally the same LP relaxation we were already talking about。

So instead of eyes。Let's write Vs。Again， the semantics here is that X v should be 1 if vertex is in the vertex cover and zero otherwise。

So it used to be that it's still true that you have to pick one thing。

But now there's a simpler way to write this， which is that for all edges， V comma W。

At least one of the endpoints should be chosen。Okay， that's what the primal constraints simplify to。

And then。Just a change of subscript here。And so now what's going to be true is that instead of set covers being a one to one correspondence。

By the same reasoning vertex covers will be in one to one correspondence to zero1 solutions to this linear program。

Okay。So as I said， Vertex covers NP hard。 So we don't expect this thing of program to always solve it optimally。

 We expect there to be fractions， actually， exactly the same example。I showed you for set covers。

 still shows that fractions help here。Let me just redraw it in a different way。

 supposeupp your graph is a triangle。A vertex cover obviously must have two vertices。

 you can't have one vertex covering all three edges。But if you pick each vertex to one half。

Then every edge is covered fractionally。 So again， the optimal solution is2 and the fractional solution is three/s。

 just like in set covered。Okay。All right， so's going to be， what's our plan， what's the algorithm？

Well。As I said。This time we're actually going to just go ahead and sha this linenium program。

So step one。Soaw the LP relaxation。To get an optimal solution。X star。Also I should say。

 you know for this algorithm， we actually won't even need the dual linear program。

 so we'll modify the dual later when we need it。 So for this algorithm。

 all we need to think about is the primal。Now we're not going to use it for the analysis。

 really just going to solve it。 Okay， we're just going to plug this into a linear programming algorithm and get back the optimal fractional solution。

 okay。Now we're certainly not done if it handed to us on a silver platter or a 01 solution we'd be done that' would be great so then we'd be lucky in general we're going to get something like this。

 we're going to get something with fractions and so somehow know just in the same way we had to take minimum spanning trees and massage them in the traveling salesman person towards here we're gonna to have to take this fractional solution which is not really what we want and massage it into what we actually do want a vertex cover just like in TSP where the whole name of the game was to transform the MST into an aarium graph and a TSP tour without losing too much in the process here the plan is to transform this into integers。

 hopefully without losing too much in the process。So this is known as linear programming rounding。

 so you take something with fractions and you output something with integers。All right。

 and for vertex cover， this is about the simplest linear programming rounding algorithm in existence。

So the final answer of our algorithm。As we're just going to look at。The vertices， V。

Which in this optimal LP solution are chosen to at least a one half。Okay。

 so we scan over the vertices， if it's less than a half， we don't pick it， if it's at least a half。

 we do pick it， that's our final answer， capital S。That's it， that's the whole algorithm。

So given that linear programs can be solved in polynomial time， clearly。

 this also runs in polynomial time。All right， so let's see why this works。

So claim one is that at least it outputs a feasible solution。Okay。Do you see why this is true？

That's right。So it helps if you look at the linear program relaxation， so remember x star。

 it's optimal， but in particular it's feasible for this linear program。So for every edge V comma w。

 the sum of the x values of the two endpoints has to be at least one。Well。

 the only way that can happen is at least one of them is at least a half。Okay。

 so if both of them are strictly less than a half， you'd have a violation of primal feasibility。

So that means for every edge you will indeed be picking one of its endpoints。

 IESS indeed will be a vertex cover。Claim  two。Is that this algorithm is a two approximation。Okay。

So it's a lot better than what we're getting for general set cover。 I forgot to say this actually。

 so when we realized that vertex cover was just a special case of set cover。

 clearly we can always default to the greedy algorithm and the analysis we have more generally So what we're hoping for we want to beat log in right is's an only easier problem with special case so we want to do better。

😊，The first question you should ask is， well we already have an algorithm， the greedy algorithm。

 maybe that algorithm already performs better in the special case of vertex cover instances。

Turns out it doesn't。 I'll put that on exercise set number nine。

 but the greedy algorithm actually can be off by a log n factor。

 even when it's a vertex cover instance， so greedy algorithm there would mean you always add the vertex。

 which minimizes the cost of the vertex divided by the number of edges it's covering for the first time。

So if we want to do better than a logarm that guarantee for vertex cover。

 it has to be via a different algorithm， so that's what motivates using linear programs more seriously。

And indeed， the good news is this very sort of conceptually simple algorithm does give us a much better guarantee than we had for general Se cover。

Okay。And it's very easy to prove， so let me just show you the argument。All right。

 so what's the cost of our algorithm？We just sum over all of the vertices in our set S。

 look at their costs。Think about it。This is the most summing over all the vertices。Times the cost。

So I guess the intuition behind this claim is that the algorithm only pays double what the linear program is paying。

 okay， so whenever the linear program maybe gets away with paying just for half of a vertex。

 well in that case we pick the full vertex， that's only a factor two blow up。So concretely。

 this is where you see it。So for any vertex in the set S。

 we know X star V had to have been at least one half。So if I double x star V。

 I get something which can only be bigger than one。so that's what gives me this inequality here。

So this is really using the definition of the set seat。

 you had to have XRV at least one half to be chosen that gives you this inequality。So what is this。

 we'll pull the two out。Now even the sum with the vertices the cost of vertex times the extent to which the LP chose it。

some over V CVxV， that's just exactly our linear programming objective function value。

So this is really just two exactly equal to2。Times the fractional opts。

And because it's an LP relaxation。Yeah。That's almost twice the cost of minimum cost for text cover。

So any questions about that？If we try to。Asposed to。Not yet as time。So。

So I'm sure I understand the question， so in this algorithm we're both using a relaxation and we're doing a rounding right so when I say relaxation。

 what I mean is this linear program here。Where vertex covers correspond to 01 solutions。

 but there's also other stuff too， like fractional solutions。

So that's what I mean by linear programming relaxation。 So in step one。

 we're really using linear programming relaxation。 But then the question is when it gives you fractions。

 how do you interpret it， it's really not what you want， you don't want fractions。

 you want a vertex cover， So you need to do some kind of transformation and actually this really kind of mirrors what you often do in practice when you're using linear programs as a heuristic for integer programs is if you get fractions。

 you just kind of like round them up to the nearest integer。😊，Okay。

 and so that works reasonably well in a lot of cases。

 vertex cover is this sort of cool example where it actually even works well theoretically in the worst case。

 So I think of this as you first relax and then you round Does that answer the question or？Yeah。

 so that's actually where we're going to go next， we're going to use both the prim and the dual。

You know。Fundamentally， like in principle， it doesn't help you to always to also use the dual because of strong duality kind of says they're sort of the same。

 And so it kind of says， you know whatever dual feasible solution you might be using as a bound。

 you may as well use the optimal dual bound。 but then that's actually the same as just the fractional optimum of the primal On the other hand。

 and we'll see this next， It's often just much more convenient to well so a couple things。

 So first of all， you might not actually want to solve a linear program in your algorithm。

 you might want something that's much faster。But then secondly， even for the analysis。

 sometimes you even though you wind up not using the best you know lower bound you just use one which is much more convenient for the analysis so sometimes if you're actually trying to prove theorems it is beneficial to use kind of suboptimal bounds and we'll see that next。

Other questions？Okay。All right。So that's good。Two approximation for vertex cover， pretty nice。

Can we do better？Well， in terms of approximation ratio， the answer may be no。 Okay。

 there's something known as the unique games conjecture。

 This is a strengthening of the P equal NP conjecture， significant strengthening。 Anyways。

 under this conjecture， there's actually no polynomial time algorithm for vertex cover better than a two approximation。

So that's not what we're going to look for，'re not going to look for a better approximation algorithm。

Instead， we're going to ask， well， you know， could we have just like a much faster algorithm that still gets a two approximation。

 Okay let's try to do better on running time。 in particular。

 let's try to avoid solving a linear program。 Now you can solve linear programs。 You know。

 it's efficient polynomial time， but it's not blazingly fast， like a linear time algorithm。

So what we're going to show you next is a linear time algorithm which is informed by the duel for the vert test cover problem that will again be a two approximation。

Okay。So I'm going to need the dual this linear program again。

 vertex cover is a special case of set cover， so I'm just going to sort of instantiate this for the case of vertex cover。

So， the elements。Correspond to edges， we agreed。So instead of some of the prices on the elements of the universe。

 we have it over edges。Seets correspond to incident edges。All so we have C sub V。For all V and V。

And here we have incident edges。 So remember， Delta v is the edges incident to V。I see。

 I jumped ahead， that should have been you before oh well。Okay， and this is still true。

 it's still true that if you have a dual feasible solution， then it lower bounds the fractional lot。

 which will lower bounds to the real lot。So that's the primal dual pair for vertex cover。好。

So I'm going to show you what in hindsight is an algorithm which if you're staring at the primal and due。

 the algorithm I'm about to show you is like basically trivial if you have the primal and dual staring staring at you on the boards。

If you didn't know linear programming， it's not really clear to me how you' come up with this algorithm。

 even though it's sort of very simple in linear time。

So this is an example where knowledge of linear programs。It really， it's not just， you know。

 so when we started with the greedy set cover algorithm we really just。

 we didn't need linear programming to help come up with the algorithm。

 we just needed to understand why a natural algorithm worked well。

In our second algorithm where were actually solve a linear program。

 it's clear we're kind of just you know in this black box way using linear programming here is maybe like the happiest case。

 which is we come up with a super simple， super fast algorithm which works well。

 where linear programming just sort of led us to developing the algorithm。

 that's maybe the best case scenario。All right， so what is the algorithm？

So the algorithm is going to construct in tandem。A vertex cover and a dual feasible solution。Okay。

So initially we just start with all the prices equal to zero。And。

Our vertex set equal to the empty set。 Okay， so notice this choice of prices。

 This is a dual feasible solution already。So remember， if we said p to be zero everywhere。

 we get a feasible solution， all the costs are not negative。So but of course。

 the empty set is not a feasible vertex cover。So we're just going to have one loop。So， while。

S is not a vertex cover。Why is it not a vertex cover。

 it must mean there's some edge where we haven't chosen either endpoint yet。

 choose an arbitrary such edge。So an edge VW such that neither V nor W is an S yet。

And actually now we're going to modify the dual solution。Okay。

So we're going look at this edge which isn't covered yet， we're going to look at its price。

 its current P value， we're going to increase it。Okay。

So we're increasing the dual variable corresponding to this primal constraint。

 which is currently violated Okay Again， if you didn't have the primal dual pair up there。

 like why would you even have PCB in your algorithm description。

 which just be like a weird thing to make up out of thin air okay。But we have a。Prial contraint。

 which is violated。 We know there's a corresponding dual variable。

 maybe sort of increasing it can guide us about how to proceed。All right。

 so why don't we just increase the price ofedgy forever？Well， it's because of dual feasibility。Okay。

So dual feasibility says for any vertex， the sum of the prices on the incident edges should be at most the vertex cost。

So at some point， when you keep raising this edge price。

 one of the two endpoints will become tight i。e。 the sum of the。Prices on the incident edges。

 including the current edge， will equal the cost of that vertex。Okay。So basically。

 you increase the price as much as possible subject to dual feasibility。

So until the dual constraints。For V or W。Becomes tight and again。

 tight just means holds with quality。So now you've got to stop。You can' really。

 you can't keep increasing this price。 But other hand。

 it's given you a hint about a vertex to put in your vertex cover。

 namely whichever end point went tight。Okay。Add the tight vertex to S。Okay。And that's it。

It's a whole algorithm。Any questions about the algorithm？Makes sense。

So it's easy to implement this in linear time， you can actually just do a single pass over the edges and implement this out for them。

 okay， so it's super fast。Okay， so why does it work？So for the analysis。

Let's try to understand what is it maintaining at all times？And what is it working toward？

So the first invariant， the first thing which is true at all times。

 is that P is a feasible solution for the dual。We saw this was true initially when all the P's readled to zero。

And obviously， you know just by construction， we make sure we never violate dual feasibility Okay so at the conclusion we have a dual feasible solution too。

Conditions variance2 and three。Are going to correspond very closely to the complementary slackness conditions that we were discussing in linear programming。

 so in linear programming， we had these general optimality conditions。We said that if you have a。

A potential an alleged primal solution X， an alleged dual solution Y。Basically。

 what you want is you want x to be feasible， you want y to be feasible for the duall and you want complementary slackness to hold。

 and X and Y are both jointly optimal if and only if complementary slackness conditions hold。

So it was opt conditions linear programming。 What did the conditions say they said that whenever in this feasible solution。

 you have a strictly positive decision variable。It should be the case that the corresponding constraint in the other linear program is tight holds with equality。

 Okay So every strictly positive primal decision variable。

 there should be an equality in the duall for every strictly positive dual variable。

 There should be an equality in the primal。 Those were the complementary slack conditions。

 which characterized optimality for linear program。All right。

 so that's to remind you about complementary slackness。

So the next condition says suppose that a vertex v is chosen in the vertex cover。

This is like having a primal decision variable strictly positive， actually equal to1。

So commentary slackness would say that the corresponding dual constraint should be tight。

And if you think about the way in which we pick vertices， that's actually just true。

So Fv is included in the set S。That only happens。When sum of the prices of the incident edges equals the cost。

 and that's not true， we're going to keep increasing the price of this edge more。Okay。

So that's the one compliment slackness condition， which says when something in the primal is strictly positive。

 the corresponding dual constraint should hold with the quality。Now， you know， at some point。

 our luck's got to run out， right， We're not thinking we're going to be proving an optimal algorithm。

 an exact algorithm for vertex cover。 Notice that you know。

 the algorithm certainly is then the day at outputs of vertex cover just by the termination condition。

 So it would be pretty surprising if we exhibited a feasible dual solution where both sets a common ss hold because that would actually say that we solved the problem optimally。

 which we're not expecting to do。So where we have to give up a little bit is in the other complementary flatness condition。

 we'd like this to say that whenever a dual variable is strictly positive。

 the corresponding primal constraint holds with quality。So whenever p sub B is bigger than0。

 we'd like it to be that the sum of x v and xw equals1。

 that would be the normal complementary slackness conditions， that's not going to be true。Okay。

But something weaker is going to be true。So whenever an edge has a strictly positive price or even otherwise。

 as you'll see。Well， it's not going to be true that。Xv plus xw。All right。

 so so' remember the x's we're thinking of as being0 or1。 everything in the set cover S is a1。

 everything outside of s is0。 So this being equal to1 would say that you know for each edge we magically chose exactly one of the two endpoints and definitely you are optimal if you can pull that off so if you can actually find the subset of vertices that covers every single edge each one exactly once it's definitely optimal。

 it's the best you can do。So that's not going to happen。But a trivial statement， which is true。

 is that x v plus xw' is in most two。Trivially， because each have xv and xWs and most one。

In what sense is this approximate complementary slackness。

 exact complementary slackness would say that the sum equals one？And we're saying， well。

 it can't be too much worse than one， it's not arbitrarily higher， it's only off by a factor two。

Again， in this particular case， this is trivial。 right。

 It's just sort of because X v and XWR is the most one， you know， this is true。All right。

 so those are the invaris。What is it working toward？It's working toward primal feasibility。

 Initially， we do not have a vertex cover。 And once we have when we stop。So at termination。This is4。

S is a vertex cover。Okay。That is we work toward primal feasibility。In this algorithm。

So in summarizing， we maintain at all times dual feasibility。

 an approximate version of complementaryary slackness， and we work toward primal feasibility。

This is not the first example of an algorithm like this that you've seen。Okay。

So this is known as a primal dual algorithm in exactly the same sense as the Hungarian algorithm for men cost perfect biid matching in the Hungarian algorithm。

 we maintain prices， we maintain dual feasibility at all times。

 we maintained exact complementary slackness at all times and we worked toward having a perfect matching toward primal feasibility here it's exactly the same thing。

So that was for problem in P， so could solve it optimally。 here's is the problem that's NP hard。

 we have to give something up and it's very transparent exactly where we're giving something up。

 One of the complementary slackness conditions is holds only within a factor two and that's going to translate immediately to us being near optimal within a factor two and this is true very generally you have prima feasibility。

 dual feasibility and approximate complementary slackness that will guarantee that your solution is approximately optimal。

All right。So。This linear time algorithm is also a two approximation algorithm for vertex cover。

And the proof you've basically already seen it multiple times。 Okay's you know， remember。

 we introduced complementary slackness in the context of the weak duality derivation。

 We derived weak duality that was easy。 We said when is everything going to hold with the quality that gave us the complementaryary slackness conditions。

 So now we're just going to do the exact same thing which says complementary slackness It supplies optimality and we're just going lose that factor two in the middle。

But so just to make it precise。Here's the cost of our algorithm， the vertex cover that we output。

Because we have this first complimentary slackness condition。

We know that the cost of each vertex is exactly， it's tight because we included in the vertex cover。

 so the sum of the prices of the incident edges。Is exactly equal to the cost of that vertex。Okay。

So as usual in this derivation， the second thing you do is reverse the order of summation so you can apply the other complementary slackness。

 so now we're going to sum over edges first。So we sum over edges。How many times does this sum？

Include the term P of B。Well， it includes PCB once for each vertex and S。 that is an endpoint of E。

 for which E is incident 2。 So P E appears in this some overall once or twice。

 depending on whether both or one of its endpoints， were chosen as part of the vertex cover。So。

 let's say。E equal VW。Okay。Or if you like， you can think of this as Xv plus xw。Okay。

So here's where we use the kind of trivial approximate complementaryary slackness。

That the intersection of the vertex covered with the two endpoints is the most two。

 or equivalent xp plus xw is the most two。So here we get2 times sum over E。Of PE。

So now we use dual feasibility。Of these prices pe。So the sum of the prices as the objective function value of a legitimate feasible dual solution。

 this is a lower bound。On the fractional optimum。And since we were using an LP relaxation。

That's in most the cost of the best vertex cover。So the algorithm basically simultaneously gives us the best worst case approximation that we think is possible with the best possible running time。

 namely linear time。Any questions about that？Next time we'll talk about randomization and approximation algorithms。

