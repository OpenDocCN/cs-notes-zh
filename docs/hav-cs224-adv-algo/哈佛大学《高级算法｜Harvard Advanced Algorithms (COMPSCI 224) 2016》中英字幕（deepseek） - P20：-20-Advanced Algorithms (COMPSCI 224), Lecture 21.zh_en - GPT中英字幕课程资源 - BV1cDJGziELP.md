# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P20：-20-Advanced Algorithms (COMPSCI 224), Lecture 21.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/e9292249e93c99297c95a6913d5e97a0_0.png)

Okay， I guess let me get started。So to date。We're going to see faster flow algorithms。

 faster max flow algorithms。Okay， so we're going to see。Scaling。Blocking flows。Like this。

Blocking flows。Which you can speed up using link cut trees。是。

So let's just remember where we left off last time。 I assume that people。You know。

 either had seen some flow or we'll just look up details on what I said last time。

 but the basic idea of last time was。嗯。We have a capacitated。Directed graph。G， which is VE。

And each edge。E and Capital E has some capacity。C， E。Which I'm imagining is。In the range from。呃。嗯。

It's an integer in the range from one up to U。Okay。And we'd like。To find。S T flow。Of max value。Okay。

 so remember that a flow for us？Has to obey the capacity constraints。 First of all。

 a flow is just a vector defined on the edges。It should obey the capacity constraints。

 we shouldn't push more flow than an H has capacity for。嗯。

And the value of a flow is just the amount of。Flow coming out of S。Right。

So we said that the amount of flow going out of S has to equal the amount coming into T and for every other vertex flow in equals flow out。

 total flowing equals total flow out。Okay， so。So what I said last time was。嗯。Repeatedly。Find。嗯。

Augmenting paths。In residual graphs。Right， so remember if we have some current flow F。

You you can define what's called a residual graph。Where the new capacity in the residual graph is the old capacity minus the flow on that edge。

So the residual capacity is just。How much more capacity is left over given the amount of flow we've already sent？

Okay， no question。嗯。So， you can show that。呃。This algorithm is correct， the algorithm of。

Repeat like find an augmenting path， in other words， find some flow。Then define the residual graph。

 find an augmenting path there， define a new residual graph， et cetera。

 keep iterating until there is no augmenting path。That is a correct algorithm。Okay。So。嗯。Ford Fkerson。

You just repeatedly。Find。Armenting paths。each。New path。Pushes。At least。One more unit of flow。

And you know， time to find。One augmenting path。Is just linear in the number of edges， so why is that。

 how do you do that？To say。Three letters or one word or something。Yeah， yeah， DF Defer search， DFS。

 BFS， basically just find any path from S to T in the residual graph and push one unit to flow there。

 So this implies。The time。Oh at times F star。Where F star is the value of。

The optimal is the max flow that's achievable。A you。Okay， so。Today。

 we're going to talk about basically other algorithms that get faster than this。 Okay。

 this is pretty terrible。I mean， F star could be as big as。嗯。For example， n times u。Right。

The amount of capacity coming into T is as big as n times U or n minus1 times u。

 It's not even polynomial， right， because when we talk about polynomial time。

We want polynomial in the representation of the problem。

And to write down a capacity which is up to you takes log U bits。Whereas we're spending， we would。

 we could spend up to you time， right， So that's exponential time。Right。So。So。So， time。Terminology。

So。We say the algorithm is weak polynomial。That means。The time is。Polly。M and log of U。So I mean。

 it is polynomial time in the representation of the problem。But we say it's strongly polynomial。

If the time。This is simply poly M。The running time doesn't depend on the capacities at all。I mean。

 it implicitly does in the sense that you have to。pretendtend that you can manipulate。

Cacities in constant time。 You can， you can take mins of those numbers and add them and stuff in constant time。

 But the number of steps of your algorithm shouldn't depend on。

 shouldn't depend on how big the capacities are。Okay。And the last thing。

 which is I guess worse than these two is pseudopolynomial。And this is Polly。

M and USo Ford Fulckererson is pseudopolynomial。Today we're going to see some strongly polynomial algorithm。

 and we're also going to see a weekly polynomial algorithm。Questions about anything。Another place。

 for example， where you've seen pseudopnomial is Napsack， right。

If you remember the dynamic programming algorithm for Napsack？The running time， not the PTS or FTAS。

 but the exact algorithm。You do a dynamic program where the number of states involves the total weight of your knapsack。

Right， so you have a。So you're linear， your time is linear in the total weight of the knapsack。

 but that's again， not actually polynomial time， that's again a pseudo that's what you would call pseudonomial。

So before I start coming some algorithmms， I want to tell you what's currently known， so best known。

And。There have been some improvements recently despite despite their not having made improvements for like 30 years beforehand。

 so from the strongly polynomial。嗯。The best known is O of MN time， and this is due to Or。Okay。

 this is in stock 2013。So that's fairly recent。In fact， today I'm gonna， I'm going to show you。

A lot of the steps to get almost this。 I'm gonna show you M N times log n。

 There's gonna be an extra log n。 Okay， I I don't know if I'll get to show you all the details of log n。

 but you'll see at least log squared n。And you know that bound is from 1983。So， you know。

 over the course of 30 years， finally， the log n was removed。 Actually。

 there was something in between where the log n。Was improved to something that。

Is never bigger than log n， but it it can be better if if the graph is very dense。

 I might have been like the base of the log changed to something maybe like n squared over E。Right。

If the graph is very dense， then。嗯。Wait， okay， I， I forgot out what the base of the the log was。

 but basically30 years of log in gun shas。 Okay， so。From the weekly polynomial point of view。

We have two algorithms， neither of which is strictly better than the other。So one is。O of。

M times the min。Of M to the one third and to the two thirds。Log of。N squared over M times log U。Okay。

 so。This is a little better， right， So this is MN， this is like MN to the two thirds times some log factors。

This is due to Goldberg and Rao。And more recently， we have an algorithm that takes time。

Uil the m times square root of n。Times log squared you。And this is Lee in Sidford。

Just like a month ago or less than a month ago。Interior point， the faster interior point。 And it's。

 and it's， it's via the interior point method。Okay。

RightAnd this tda is hiding some log factors like some logMs， for example。Good。But in the worst case。

 if you think about it in the worst case in a very dense graph。N could be as big as n squared。

In which case this mean could be as big as end of the two thirds。

 So this would be like m times end of the two thirds times sum logs。

 whereas this would be m times root n times sum logs。

So there is a regime where this algorithm is better， but neither strictly。诶。

Neither strictly dominates the other。 right M is， if it's a very sparse graph。If M is much less than。

呃。The two third into this。That's I guess less than end of the three halves， maybe。

If M is much less than end to the three/ halves。This will be much less than MR N。

 in which case this would be better than this。 So there's some regime where ones by than the other。

 And there are also some other things you can do for unit capacity graphs， okay so。

There's a 1975 paper of Evan and Taarin。That shows that you can basically get this bound without these two logs or these these two logs。

In unit capacity graphs。Okay， that's evident origin。And you can also get M to the 107s。

In unit capacity graphs up to logs， and that's due to marie in Fox 2013。Okay。

 so this is kind this is a state of the art。嗯。Well， okay， so。It's up here。Yeah，Is M to the one third？

Oh， you're saying M is that most n squared。Yeah。Yeah， yeah， yeah， sorry， you're very right。Yeah。Yeah。

 sorry。Okay。Yeah。In the。嗯。Wait， actually， wait， go back for your Wait， sorry。

 I think if this is actually one third， but I'll come back to you if wass like， why did you say this？

Okay， so I fix I thought， I wrote down this and I thought it was this， but I could be wrong， so。Yeah。

 I'll fix that in the notes whatever it is Okay， I I what are we saying？So， I'm assuming。Right。

So I'm assuming I'm operating in the Word RAM model， and my words have at least log U in size。Okay。

 so I can do arimetic on capacities in constant time， that's my assumption。In which case。

 in the word RA model， like those are the running times。Oh，Did you find it？Empty the two/3s。

Did I really mistype it that badly， okay？ok。Sorry for lying to you。Okay， so。No。

 but that seems really， that doesn't seem to make sense， right because。

Then this would be better than this。So I'm just going to put this for now and I'll fix it in the notes。

 okay， so there's some powers here that I'm forgetting。嗯。Okay。

 so now let me just explain to you scaling and blocking flows。Okay。

So the idea behind scaling algorithms for maxflow。Is that we're basically going to reduce。

General capacities。General capacity case。To the unit capacity case。Oh， it is one half and two thirds。

I see so my one third here was off， okay， good。Okay， so。

 so the general idea of scaling is to reduce the general capacity case to the unit capacity case。

Okay。And how do we do that？So。Treat each。Treat capacities。As a log base two of you。Bit integers。

Written in binary。你。And then this is how the algorithm is going to go。Start。With。

F being the zero flow。And。All capacities。0。唔全。Now do we do？For。He。Being for K， let's say。

Equals log base two of U。Minus1 down to zero。Double each capacity。So， for each。Ege。Yi。Double。

Both the flow on E， as well as the capacity of the EE。本人。Also for eachIG。Double both。Honestly。

 in all capacities， let's call this C prime of E to be 0。Okay。

 so there are some actual capacities in the graph C of E。Okay。

 but we're going to maintain capacities C primly。Okay。Initially。

 the edges have no capacities their C prime value is0。And basically。

 what we're doing here is we're shifting it。 We're shifting in bit by bit。

 the next bit of the capacity of that edge。Okay。So we imagine that。

So like the edges have various capacities。 How should I put this。

 So let's say the edge capacities  one has capacity。 That's 0，1。 That's 2 plus 4，6。

 This is like capacity 6。 another one has some capacity。Two plus4，6 plus8 is 14， et cetera。So。

 initially。Kind of initially。All the edges have， and let's put leading bits of zero everywhere。

Initially， we imagine a graph for each capacity， edge capacity C prime is0。

And then what we do is we shift in the next bit of capacity。

So now these three edges will have capacity1， and this edge will have capacity zero。

And then we'll solve a full problem on that。 I'm going to continue writing。And then once we do that。

 we shift in the next bit of capacity。So now this has capacity  two，3，2，0。And then we do that。

Bit by bit。Until finally， we have。The entire capacity。Okay。

 C prime will be the entire capacity at the end。 but so okay， so that's roughly what's going on here。

 but let me let me finish the pseudocode。So for each bit of the capacities。

Starting with the most significant bit down to the least significant bit。

So we currently have some flow in the current graph defined by the C prime capacities。

We're going to double all those C primes， which means basically。

RightThis used to be when we were here， this used to be the least significant bit。

 But then we shifted over once to include one more， which means this position got shifted over。

 which means the capacity doubled。And then we're going to double all the flow values。

So they're going to remain feasible。Because we doubled the capacities as well。

And then we're going add these in。 So for each IG E， add in。The case bit。Of C to C prime E。And now。嗯。

Augment， you know。Keep augmenting。F， until。It's a maxflow。Okay。

So the invariant we're going to maintain is that。Every time we enter the start of this loop。

The flow we have is a max flow for the current capacity C prime that we have。Okay。

So how about correctness？So。We maintain the invariant。That。F is always。A max flow。

For the C prime capacities。At beginning。Of loop。Which is definitely true in the beginning when the capacities are zero。

Okay， and why is it true from iteration to iteration， Well， I think I guess I already said this。

 but the point is。When we double the capacities。Right， so to be a max flow。

 we know max flow equals min cut， and we know a max flow in particular， saturates a min cut， okay。

For a flow to be maximum。There must be some ST cut that has zero residual capacity across it。

So look at that cut。After this step。We've doubled the capacity of that cut。

 but we've also doubled the flow across that cut。 So even afterwards， it's still a max cut。I mean。

 it's still a max flow， Okay， and then we added in this extra bit of capacity。

 potentially to some of the edges。Right， so， but we still have a feasible flow。It's not a maximum。

 but it's still feasible， but we know that if we have a feasible flow that's not maximum。

 we can keep finding augmenting paths to make make a maximum。So this will find us linear your maxpl。

Okay。Okay。So how about running time？The running time is basically the number of iterations。

Times the time per iteration。So。The number iterations is pretty clear， it's written explicitly。

This is just log U。😡，How about the time for iteration？Yeah。

 so what is the time to do the unit capacity case， which I've written here？Yes。

 so but here what's our star？I'm sorry。MYM。So I mean， okay。

 so the thing is when we shifted in this new bit of capacity， right？

We' going shifted in this new bit of capacity。There might have been some unsaturated edges。

Those got doubled， and then we added this new bit， right？So it's true that there are most M edges。

 but。嗯。They're not all going to be unit capacity edges。😡，Do you see what I mean？

So it's not simply that。It's， it's not simply that we're in the unit capacity case。

 I shouldn't have said that。Okay。But we want to argue that this value F star is small。Right。So right。

 we're not in the inacity case， but we want to say F star is small so that forwardd fullquicent is pretty quick。

So。Yeah。Yeah。Yeah， exactly， so that's the point。Let's look at ourselves right here。😡。

We've doubled the capacities， but we haven't shifted in。Then you bit yet。This flow F。

Is a max flow for the current capacities， right， which means that there's a cut that's saturated。

So that cut has zero capacity across it。And then we added in the next bit of capacity to some subset of the edges。

The worst case is that you know。Any cut is always an upper bound on the max flow。

 So let's look at this cut。It has there are most M edges involved in this cut。 It had capacity 0。

 We've added at most M capacity， at most one capacity per edge to this cut。

So this cut now has capacity at most M， which means the max flow values is at most M。Right。

So this is O of。M times。F star。Which is O of M times the min cut。The men。S T cut。Right。

 and the point is。Before。Adding。In the next bit。A capacity。Some cut。Was saturated。Was saturated by F。

And has。Zero residual capacity。Let's call this cut C， some cut C。Do I have a scribe for today。

d right， so some cuts see as zero residual capacity。And C has certainly at most M edges。Implies。

After。Shifting in。The next bit。Of capacity。The residual。Capacity of C。

Is that most which implies that the min cut？Is that most。Right。So overall。

This thing we're saying is o of M squared。So this thing is O of M squared log U。Sure。Okay。

 so that's scaling。And we're going to see scaling again soon， but before that。

I want to now move to blocking flows， it turns out you can combine them。

 you can use scaling on top of blocking flows， we're going to see that。嗯。I mean， basically。

 you can use scaling in combination with lots of different algorithms。

Scaling just says youre reduced to having to do this over and over again。 right。

 So you can imagine instead of doing Ford Fulkerson here， you'll do some other algorithm。

 For example， blocking flows， which we're going to see now。不是。So。So blocking flows。

How's that going to work？So。In a residual graph。Gf。Okay。We say。The level。Elevie。Is the。Shortest。Plf。

Distance。From。From S to V。Okay， by the way， before I get more into blocking flows。

 I just wan to say that if you do。RightSo Ford Fulkerson doesn't really specify how to find the augmenting path。

 For example， you can do dump for search。You can also do breath for a search。

You could also do what's problem one on the current PSAT。

 which is augment along the path that has the largest minimum capacity。Okay。

And depending on how you find augmenting paths， you can get different running time bounds。

 So we you're gonna to see on the Pet is that you can do a lot better than vanilla Ford Fulkererson。

 if you augment along such a path with。Large minimum capacity。

If another thing you do is instead of first search， do breath first search。

And you can show that you'll get a bound of M squared times n if you do that。Okay。

 so that's Edmund Cart。What I'm going to show you now is that M squared n。

 you can actually get m times n squared using a different technique via blocking flows。嗯。

But I wanted to define- let me go through exactly how that technique works。Okay。

 but were there questions at all about scaling before I do blocking flows？Yeah。Yeah。

 so I'm always assuming that the capacities are integral because you can always clear denominators。

Yeah。Yeah， I mean， otherwise， right， otherwise。Kind of log U doesn't really make sense as a bound if they can be fractions because。

You know， you could say， well， I mean， what is you then。

 I guess you then would be the ratio of the largest of the smallest， maybe something like that。

 I mean， if， if you。Right， yeah。 so that's what theirre integers， right。

 But if you say they're fractions， then。Okay， why can't I just take all the capacities and normalize by the largest one。

 That doesn't change the flow problem at all， but that changes the largest capacity， right。

 So something about that is off。 So you need some kind of normalization for it to make sense。对。Yeah。

 so I'm assuming all the denominators are cleared out。Okay， so let me move on to blocking fluxs。Okay。

Let me make a definition。 So the level。Of a vertex in a residual graph is the shortest path distance from S toV。

And。An edge。Uv。Is。Admissible。If basically the level of V is the level of u plus1。

So we're only allowing edges that are along the shortest path， basically from。嗯。

Or let me only write the last thing， a path。A path is admissible。If。All its edges。Armissible。Okay。

And a blocking flow。嗯。Other， I believe I want to give the citation for blocking flows。

Didn't write it down， but I believe it's Dens。呃。Sometime in the 70s。嗯。So a blocking flow。Is a。啊。

Is it admissible flow？I。e。 it decomposes。Into。It miss。Augmenting admissible paths。Such that。Every。

Admissible。Is there missile flow， let's call it F。So that every admissible。path。ST path。Has at least。

1 edge。Saurated。Baf。Okay。So。This as a toy example。Let's pretend that。

This is our current residual graph。And let's say all these edges have unit capacity。Okay。

 so which of these edges？A admissible and which edges are not amissible。Yeah。Yeah， so this。

This edge here。Is not admissible。Okay and。You know， one。An example of a blocking flow。Is。Well。

 certainly this max flow is certainly a max flow is a blocking flow。

 So one example of a blocking flow。Is that green flow， this is a blocking flow。So okay。

 so a question for you。Do you believe that the claim that？Kind of blocking， I mean。

 a blocking flow is just a specific kind of。I mean， so a max flow is definitely a blocking flow。

Maybe a blocking flow is always a max flow。 So really finding。

Finding a blocking flow is the same as finding a max flow。 Do you believe that claim？No。

 you don't believe it，Anyone have an example in mind， I mean。

 I guess maybe it'll be a little tough to come up with this right on the spot but。Of， of why。

A blocking flow might not be a max flow， yeah。SU UV V2。But then UV is not admissible。

So a blocking flow for me should be composed into augmenting admissible paths， right。

 So it should only use admissible edges。If you use the IGV。Yeah。Now that。为。

Oh you want to use this graph， you want to use this flow。Okay。

 so what do you want the capacities to be？You want what？SU to me too。You need to be one。

VT toB2 and the others are still one。Okay。So this green flow， I guess。

 only has room to put one on it， right？Okay， so is this a blocking flow？嗯。Yes。

 it seems that it is a block and flow。And。Is it a max flow？Yes。Yes， that's true。Yeah。

 and you can even come up with examples。You even come up with examples where all the edges are unit capacity。

 so if I just change the graph slightly。嗯。Let's say that。So let's make all these unit capacities。

Then this flow is a blocking flow。Right。And it's certainly not a max flow。

 the max flow would send one along this way， one along that way。 but kind of this， this。

This flow kind of blocks both possibilities。对。I mean， the only augmenting paths。

 I guess are this one。This one and this one。 and they're all sat。

 all of them have at least one edge saturated。 But yeah， that's also， that's a good point。

 That's another one， as well。So questions about what a blocking flow is。Okay， so。So first。

Let's analyze。When。嗯。All edges。Have unit capacity。actually， before we do that。嗯。呃。Before I do that。

 let me write down a claim。啊。After。Augmenting。And this claim is really the point of finding blocking flows。

 So after augmenting along the blocking flow。The shortest path distance from S to T。

In the new residual graph。Or in the new。呃。It's in the new level graph。IE graph。Containing。Admissible。

Edges。Strictly increases。Yeah， these are edges that have residual capacity。

 if they have zero capacity， we ignore them。Is there any that have residual capacity？

And they have to increase the。it has to go from a vertex that's closer to。

Closer to S to a vertex that's one farther。So okay， before we prove this claim。You know why。

How would you use this claim as part of an algorithm？Well， me oh yeah。Zian。冷卒帯？这原声音。degrees1。

You increase the。By won， yeah， at least won。Yeah， you can't do it more than n times， right， so yeah。

 that's the point。So the point is， are when I say distance， this is an unweighted graph， right？So。

The distance between S and T certainly can't be more than n if there's an augmenting path at all。

 But if it's more than n， that means it's infinity。

 That means there's no path in which case we're done。 We've found we've done， we're done augmenting。

Um so。So consider the following algorithm。Find a blocking flow and augment along it。

Now form the residual graph。Find a blocking flow there， augment along it。

 and just repeatedly find blocking flows in the residual graph augment。The number， oh yeah。

How was that walking。Yeah。Go backward。Yeah， that's fine。 Yeah， Yeah， I in general。

 in the residual graph， some edges get reversed。Are they still admissible？Are they still admissible？

Oh， so the definition of admissible is that this happens in the current residual graph。

So you look at the distance from- so the residual graph changes in every step。

So what's admissible and what isn't is a function of the current residual graph。New religion。Yeah。

Yeah。Maybe I'm so。Okay， so。私さ？Okay， hold on。You want to take this graph and you want to form its residual。

 right？So。嗯。呃。So let let me pause for a second。 let me just draw that graph here。1，2，3。Oh yeah。

So now what are the residual capacities or residual edges you have？So we had before。

So this stay this goes this way。This goes this way。Ss that way。Let goes that way， this way。This way。

And here you go， this goes reversed。Right。This is the residual graph。 This is， this is G F。

Where this is my flow F。Right。Well， remember the definition of residual capacity， right。

 It's the old capacity。 It's the capacity minus the flow value。 So if you add capacity 0。

And remember， I'm in that definition from we were talking last time I said。

If if I have flow pushed the other way， I view that。For the purposes of forming the residual graph。

 I view that as kind of minus flow on this edge。Right so0 minus negative1 is1。

 So now I imagine that this has。There's a capacity one edge this way。

 there's a capacity one edge this way， there's capacity one edge that way。

And then now the shortest path distance from S to T。I think is one， two， three， four， five。

 length five。Actually， I think that this is the only ST path。Right。The， the level graph。

Let me define this as let me label some vertices this A， B， C， T。

 So the level graph would actually just be a path。 It would have S， A， B。Well，S A BC D T， So S， A。

 BC， D T。That would be the level graph。Corresponding to that blocking flow。

And then there's only one augmenting path here anyway， so you would just find it。Questions。Okay。

 so the point was， as you said。This。The number of iterations。

 So if we have this algorithm that does the following， find a blocking flow augment。

 Find another blocking flow augment， etc cetera。 The number of iterations can be at most n。

Until there's no more blocking flow， right， because the distance keeps increasing between S and T。

So the running time。So this claim would imply。That the running time。Is at most n O of n times？

The time。To find。A blocking flow。Okay。And we're going to show that you can do this in unit capacity graphs time in linear time。

 basically in time M by basically a modified depth for search。You can also do this in。

 we're going to show that you can do it also pretty simply in general capacitated graphs in time MN。

In which case you get a time of Mn squared。Using a fancy data structure， namely Li cut trees。

 Viator and Ta， I'll show you a little bit about that。

You can actually do this in M log n for a capacitated graph。

In which case you'd get a time of MN login。Which is not too far off from what I told you。

 the M N time， just last year's stock。Okay。So really， we just need to prove this claim。

 and then we need to understand the time to find a blocking flow。Oh。

 I think that paper is pretty complicated。 actually， I't I haven't read it。 So yeah， I'm not sure。

 I'm not sure。嗯。Since。Yeah， I'm not totally sure with that。What Orleans's algorithm is doing。Okay。So。

Let's prove the claim。It's actually a pretty simple。It's a pretty simple claim。So。

Let's look at the level graph。Before。Augmentation。Is L。And the level graph after augmentation。

I let's call that L prime。The level graph remember is the graph containing the admissible edges。So。

What does L look like？Well， here's S。And。Basically， you can organize it right into。

The distance from S T。 So there's some at distance one， there's some at distance2。

And there's T over here。There's some edges。And there's only edges in between adjacent layers。Right。

And what is a blocking flow？A blocking flow just is some flow that decomposes into a bunch of。

ST paths here。Okay。And so。Let's say， let me also draw some other edges。Question。

 so this this is a subset。😡，Of the edges。In the residual graph。

RightThe ones that go from one level to the next。Is it possible for me to have this edge。

 So not all the edges are drawn here， iss it possible for me to have an edge that looks like this？

Or an edge， basically edges that skip layers。No， right。

 because that's the definition of shortest path。This means that there's actually a shorter。

 well this is okay， this is an adjacent level bit。This is not okay。Otherwise。

 this would have had a shorter path to it and it wouldn't have been in this level。

So I can't have those kinds of edges。What I can have is I can have edges going backward and possibly jumping。

Like past possibly jumping levels too， I could have an edge that goes all the way back here。

 for example， that's possible。So。If you think about what kinds of edges are possible in L prime。

In L prime。The only edges。Audud。The only edges that。Appear。2。Either。From。L， okay。

 so certain edges from L might appear。 I'm not going to rule them out。

We might also have somebody of just show up from the reverseers of L。

 namely a reverse of one of these edges， right， Because after we augment along。Paths here。

 some of these edges might get reversed， just like what you saw in that example。From L or rev L。

Or yellow edges。Or yellow edges。Going backward。Right。

They're not an L because they don't go from one level to the next level。

 but they might be in G F in the re， in the residual graph。 You had a question。Oh yeah， yeah。

 that's you could have that。 You could have edges in the same level。 that's true。

So what does this imply this implies？That the shortest path distance in L prime between S and T。

Is at least。The shortest path this is an Al from S to T。Right。

If you imagine looking at this graph and you're trying to get from S& T as fast as possible。

 it doesn't ever help you to take a yellow edge or to take a reverse of one of these wide edges。

 right？Okay。So。Okay， good。 so the question is。Can。Can DL prime ST？一個。DST。Okay。And the answer is no。

Why is it no？Yeah。Right， yeah， if， if， if the， if the shortest path distance in L prime were the same as an L。

That means all the edges in that shortest path would be L edges。Right that means we have we have a。

A path of， that means that there's a path in L prime， which also exists in L。

But by definition of blocking flow， at least one of the edges on that path has to have been saturated。

So that entire path cannot not possibly be in the new residual graph， so it wouldn't be an L prime。

Right。If。If。There is。A length。DLS path。And now prime。Then all。Those edges。Our L。Implies。At least one。

Is saturated。Why our blocking floor？So this is a contradiction。嗯。Right。So the claim is that。嗯。Right。

 so if you， if you didn't use only L edges， if you use some yellow edges or some reverse edges。

 then that would only increase your distance。 That would only increase the length of the path。 right。

 So if you're telling me that your path length is exactly the shortest path length。

 then you have to be using L edges。都是。So that's that。So how do we find a blocking flow？

So finding a blocking flow。So。Let's first look at the case of。So a special case。

Let's look at unit capacity。Okay。So。We're basically going to do some kind of modified。

Deep for search。From S。A repeated depth for searches。So I'm going to have。Three types of operations。

Which I'm going to call advance。Retreat。An augment。其食。So this is defined， right？This is gonna be on。

 on the level graph。 Remember， I'm trying to find a blocking flow that uses amissible edges。 Okay。

 so this procedure， I'm gonna be， I'm gonna run it on the level graph。So let me have a loop here。

 so let's say while true。So。嗯。哎。Anything about I want to say this？诶。So I'm going to say V。

Is that V is going to get sent to s our current vertex？And I'll say。Well， true。呃。Advance。So。Well。

 V has。Some outgoing edge。Let's say V U。I'll advance。And by that， I just mean that V goes to you。

Sorry， we moved to。 We moved to。Proertects you。呃。How to actually， let me me sorry。

I shouldn't have written it this way， so let me say this。So we'll be always。Always have our finger。

On some vertex v。That we got to。By DFSing。Starting from S。Okay。If S is equal to T。

 I mean if v is equal to T， so if we've managed to reach T。Then， augment。Along。The ST path we found。

Then， delete。The zero capacity edges。Okay， so。I'm going to describe the algorithm in the general capacity case。

 but of course， if we're in the unit capacity case。

 then after augmentation all of those edges have zero capacity now。

 so we would just delete all of them。So if equals t， augment going along ST Pafi found。Then。

We put our finger back on F。Finger back on S。Otherwise， V is not equal to T。Advance。To some。A you。

Se system vertex U， such that VU。is an edge。Of course， there might not be such a you。

 We might be at a debt end。If no such h exists。Then retreat。Back。To。Previous vertex。W before V。And。

Delete the edge。From W to V。哎。Unless。V is S。In which case we terminate。Okay， so basically we DFs。

You know， imagine writing a recursive implementation of DFS。Okay， where you started us？

And imagine that in your DFS implementation， whenever you finish a recursive call and then go back up to the parent function call that called it。

That corresponds to going back on an edge in the DFS， right？And when I do that。

 I'll just delete the edge。And then when I make a call to an adjacent vertex in the DFS。

 that's my advanced step。And when I reach T。Well， I reached T via some。

Sequence of function calls on my stack that started at S and in in T。

 All of those corresponded to following edges。And I'm just going to augment along that path。Yeah。

I'm sorry。I don't， I don't mean delete it from like， from， I mean， delete like， so I mean。

All of this which judges are alive and which have been deleted。

 is all just maintained within the algorithm that computes a blocking flow。

I'm not deleting it from the graph or something。I'm just removing it from consideration from this algorithm。

Because so that。No， it's it's a dead end， right， So I mean， in fact。

 if I'm at some vertex V and it' it's a dead end。I can basically delete all the edges that go into V now because I know V is worthless。

 V take V cannot be part of an augmenting path from now on。Right。We stuck。Right so I'm not。Okay。

 so I shouldn't say augment， okay。呃。If v equals t， so what this thing is going to do is it's going to output a flow。

Okay， so。So we want。A blocking。Flow F， so this thing is going to output the flow F。

So what I really mean is a V equals T。Add。To F。嗯。All edges。

Add to F all the edges along the ST path we found。With the minimum capacity， that's right。

 With the minimum capacity。And then subtract that capacity from everyone on that path and then delete all the zero capacity edges。

No， so we're always going to operate in the same graph L。我。

So this is just finding a blocking flow in the current residual graph。

As we run through iterations of this， we are not changing the residual graph。

 We are not So we are not actually augmenting the flow yet。 We're just finding the flow。Yes。

 you keep trying a DFS from S。😡，Is it always true？Tund a dead end。

RightAnd that will still be a dead end。Right， because we're not actually changing the residual graph。

 right， we're not actually subtracting this flow from the capacities to define a new residual graph。

This is all still happening in the current residual graph。So if something is a dead end。

There is no extra capacity that's ever going to leave from it。

 right because we're not reversing anything after it。Like the number。

Over the various iterations of this， finding passed over and over again。

The capacities are only ever going down。😡，Edges aret only disappearing。

So if there wasn't a path from V to T now， there won't be one in a later iteration。So， I mean。

 just think of， just think of DFS as。As。How should I put this right？Okay， so the point is。If。If。

T is actually reachable。Right？If T is actually reachable， we will find a path that goes to T。Okay。

 and then we will saturate。 I mean， here we're in a ne case。 we will saturate those edges。嗯。

And then all these other edges are now。Blocked， so。I don't know， I don't know if I'm answering your。

In some cases。Could mean that there。No outgoing。It could also mean that there are。The vereses。

The ends of those。Wait， wait， wait so first of all， we're working in the level graph。

Which means edges only go to one level in the future。There are no cycles in L。

Maybe that answers your question？L has no cycles， what you're saying couldn't happen。Like， therere。

はい no。The distances。そです。That's right。But。But the thing you were saying before where you said。Like。

I'm at V， and then maybe there are edges leaving V。

 but they are going to vertices that I already used to get to V。Right。

Isn't that what you were saying？Like that can't happen because。

I'm only looking at edges in the level graph。So this level graph is a dag。Okay。I'm sorry。It know。

 Well， anyway， So do you both understand youre， Okay。

 so let's just continue because we're running out of time here。 Okay， okay， so。Okay。

 so rather than spend time understanding how the misunderstanding happened。

 Let's just now people understand。 So let's continue。 Okay， so。So good。 So any， okay， so question。

 So the run time。So in the unit capacity case。What's the running time？嗯。

Each edge is looked at a constant number of times。Right。You're going to maybe advance on some point。

 that's looking at it once。If you retreat on it。Then that's looking at a second time。 But now it's。

 you've deleted it。 So it's gone forever。 If you didn't retreat on it。

It means that eventually you reach T。Which means that you augmented it along it。

 or you added to flow to F along it， and then you deleted it。Right。

 so you only look at each edge of constant number of times， which means O M total time。

 So this implies。Oh the man。In。In a unit capacity。There's another。

There's another analysis you could do。Yes， that's right。Runtime un Class case Oman。Per blocking flow。

So O man capacity for MaxF。There's another analysis you could do is you could say， look。

After de iterations。The distance。From S to T。In the level graph。Is at least D， right？

Because the distance increases in every step。Okay。Which implies。If we decompose。Any。Max flow。呃。

Each in paths。Each path。Has length。At least D， which implies that there are at most M over D paths。

Which implies。The max flow。In the residual graph。Is at most M over D？Right。So。This implies。

That for all D， the number of iterations。 So forget about the， this is pretty good。

 Linear time to find a block flow。 It's pretty good。

 But let's attack this other business of the number of iterations。

 what I I think I might have deleted it。 The number of iterations it takes to find a blocking flow。

 the number of iterations of blocking flow we need。 How many blocking flows do we need to find。😊。

So this implies that the number of iterations of finding blocking flows is at most D and then plus M over D。

 So once we've had D iterations， we will only have M over D more iterations， right。

And this is minimized when D is about root M。😡，And this is at most rude end。For D being rudeam。Right。

Which implies。M time per blocking flow， rootm iterations。 So this implies。

Oh of m to the three halves， max flow。Or you could view it as M times the min of root M and N。😡，嗯。

In fact， I'm not going to show you here， but it's even possible。

 Maybe I'll put on a pieceet or something。It's even possible to， just say that。Okay， so how about？

Okay， what other thing。A unit graph。Is one where。Other than。S T。Every other。嗯。Well， wait let me not。

I just say another thing。If you look at， for example， graphs like the following。

So imagine a graph that has S& T as follows， and then it has two layers in the middle。

And all the ideas go from this layer to the next， and all these capacities are one。

Where do you see graphs that look like this？I claim if well if you've taken 124。

 I claim that there's a problem we reduced to flow。To ST， yeah， max matching and bipartid graphs。

So if I claim here， you can show that in graphs like this， the number of iterations。

Is at most this D plus n over D？Okay。Which implies。O of M Ruan。嗯。Maxwell。So in particular。

 you can find max matching and bipartid graphs in time EmRen。So if you just used Ford Fererson。

 you would get， I guess。F star is as big as n。So you get M N。

 but you can actually get M rootN using blocking flows。In the last remaining minutes。

 I guess I won't have time。So maybe allll did at the beginning next time。

 tell you a little bit about link cut trees。But how about general capacities？Okay。

 so here the point is。There are。At most。嗯。So remember， we had， we still have。Augment。Retreat。

In advance。There are at most M augments。My augment， remember。

 I don't mean actually changing the residual graph。 I just mean。Adding the minimum capacity of that。

Of that path to the current flow we're building to the current blocking flow。

Why are they most em augments？😡，Yeah。Yeah， every argument has saturated edge and that edge will be deleted。

 So every， every time we do one， we delete the number of edges， there are most M edges。

 How long does it take to perform the actual augment。What's the worst case？M。I claim。

 so when I say perform the augment， I mean， we've built up the path N， right。

 We've built up this path。 And now we're adding flow values along that path。

 That path has linked at most n。So。Relies。Total time。For augments。Is O of M。

How many retreats can there be？M， right， because when we do a retreat， we delete the edge。

So that implies that the total time for retreats。Is O of M。

 a retreat is just a constantine thing you delete the edge。So now how about the total time？

For advances。So the number。So I want to say less than something advances。

And this one is a little trickier， I'll just tell you because we're running out of time。The point is。

After every。嗯。After every N advances。After every N advances， there will either be a retreat。

Or there will be an argument。You can't advance n times without either reaching T or going backwards once。

Right。And if there's either a retreat or an augment， one edge is going to get deleted。😡。

So after every end advanced steps， definitely at least one edge is going to be deleted from either a retreat or augment。

Which means they are at most M times n advances。Right after。Every ut most and advances。Some edge。

Is deleted。Via retreat。Or augment。So this。It implies， so this is going to be O MN。So。

In general capacities。We have， again， the number of iterations。Times。Time per blocking flow。

This is at most， and we said this is at most O of N。So， this is。O of MN squared。Time。For Maxflow。

And the thing that I will tell you about a little bit next time is that。This。

This algorithm for finding a single blogging flow。Is kind of wasteful， right， because。

We started exploring quite a bit kind of how， how should I put it。嗯。Okay。

 so I'll say more next time I don't want to try and rush and say things that don't make sense。

 but the point is using a nice data structure。Due to slater intn called link cut trees is from 83。

You can find a blocking flow not in time M N， but in time M times log n。嗯。You can do。

O of M and log n。Via link cut trees。We'll see that next time。That's due to later int。So slater。

And Tan in 83。So I think that's enough for today questions before we depart。Okay， that's。

