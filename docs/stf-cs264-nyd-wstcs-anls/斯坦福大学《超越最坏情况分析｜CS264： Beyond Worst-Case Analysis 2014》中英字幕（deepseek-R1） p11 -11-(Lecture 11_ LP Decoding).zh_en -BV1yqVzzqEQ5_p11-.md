# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p11 -11-(Lecture 11_ LP Decoding).zh_en -BV1yqVzzqEQ5_p11-

Today is going to be the last subtopic within the exact recovery part of the class。

 I got kind of obsessed with this topic this year， so for better for worse we give you a lot of lectures on it so today I want to introduce the idea of LP decoding and this will spill up over a little bit into the beginning of Wednesday and then we'll start a new topic on Wednesday。

So this is。Yeah。Motivated by a topic， hopefully some of you have seen at least a little bit of。

 although I'm not going to assume any background， namely error correcting codes。

So error correcting code is when you want to encodecode information in a way that it's resilient to errors。

 things like bit flips， okay？And so we're only be talking about binary codes today。

 so it's just going to be things over the alphabet 01。And a couple things that you should remember。

 so first of all， the haming distance between two vectors。

 that's just the number of coordinates in which they differ。And then the distance of a code。

 which is an important parameter， is the minimum distance between the minimum haming distance between any two code words okay so formally a code is just a subset of binary n vectors because it's just a subset of01 to the n and one of the parameters you care about is amongst all vectors in your code in the subset。

 what's the minimum hamm distance between any two。So for example。So here's a code。

You could just think about all the binary n vectors that have even parity。

 meaning the number of ones is even。嗯。So what would be the what would be the distance。Of this code。

Yeah， it would be two， right？So if you flip one bit。

 then it's not a code word because all of a sudden you have an odd number of ones。

 but if you flip two bits， you can get back to a code word again。

So code wordss need to differ by two bits， two coordinates。

 but indeed some code wordss do differ only by two coordinates。And one way to think about this is。

 you could take just all01 vectors of length end to the minus1 and then append a parity bit so just whatever the parity is at the first n -1。

 you stick that at the end to make it even overall， that's one way of thinking about this code。

So this is a code that has a lot of words and pretty small distance and a lot of the codes that people think about and what we're gonna be thinking about today are codes where the distance is much bigger between two different code words。

 And particularly we not to not just detect an error。 so if you have distance2。

 that means if in transmission exactly one bit got flipped。

 you'll know something went wrong just see an odd number of ones and you're like， you basically say。

 hey， sender retransit， I don't know what you said。But if you think about it。

 what about the distance is like a lot bigger than two。 Okay， What if it's just D in general。Well。

 then certainly， even if there's as many as D-1 errors and again， adversarial， Okay。

 not probabilistic， Just adversarial errors。 If there's D -1 or less。

 you'll certainly notice because what you get won't be a code word at the definition of distance。

On the other hand， if less than D over2 bits were flipped， then actually。

 without asking for a retransmission， you can reconstruct what the sender meant because you just look at what is the nearest thing。

 which actually is a code word。 Okay， so you just say， you know， how many。

 how many coordinates do I have to flip to get back to a code word。 You know， let's just flip them。

 that must be what they meant。 Okay， so by the trianglelineequality， if everything is D apart。

 and you get something。 And there's the most D over two errors。

 It's closer to the original code word than any of the others。

So distance D allows you to detect d minus-1 errors and allows you to correct less than d over two errors And to the point of this lecture is to study the computational problem of given a corrupted code word。

 efficiently reconstruct what is the nearest code word to it okay。

And to continue the theme of some of the recent lectures。

 we're going to be asking when can you do this via linear programming， Okay， and again。

 there's going to be a actually quite nice sort of nontrivi linear relaxation of this problem and we'll again be seeking conditions under which this linear program is exact。

Okay， so this idea of decoding V linear programming works nicely。For a family of codes。

 which is what I want to introduce next。 And this already， know， I mean。

 one of the fun things about this topic is you'll see some ideas。

 which if you haven't seen them before， they're just cool ideas。 Okay。

 so idea number one is there's a very nice way to use graphs to naturally induce codes。

 so I want to tell you about that next。😊，So this is I mean sort of a very old idea， I mean。

 over 50 years due to Gallagher and then these graphs are often called tannergraphs for work in the '80s。

 really it sort of took off big time， at least in the computer science world with a paper of Ss or and spman about 20 years ago。

 and then there's been a lot of work on you these connections between graphs and codes in the last couple decades。

So here's the idea。So we're going of a bipartite graph。And these， bypart。

 that graph is going to play an important role。In our discussion of this topic。

The left hand side are the variables。 Okay， so there's n of them。 Okay。

 So these are just like the coordinates。 And then on the right hand side。

We're going to have a bunch of parodity checks。Okay。And there'll be edges。In this biparttheite graph。

And so for a given binary vector of length n。 So if you like a assignment of 0 or one to each of these vertices。

 we'll say that such an x satisfies the Jth check。If。When we zoom in on just。The coordinates of x。 O。

 So J， remember， J is going to be one of these vertices。So there's like a canonical J。And。

So a parody check， a note on this side， is going to have neighbors on the other side。

 It's a biparttheite graph。 Okay， so there's some subset of variables that neighbor this check J。

N J is denotes the neighbors of a vertex。 So this is saying for the Jith check， the J parity check。

 which variables are connected to it involved in it project this n vector to that subset of coordinates。

 And then this constraint insists that there's an even number of ones amongst these coordinates。

So if Jay has five neighbors， then we're saying necessary， well。

 sort of for this particular parodity check to be happy to be satisfied。0。

2 or 4 of those five neighbors should be set to one。 Okay， not one， not3， not 5。

So that's how you satisfy just one of the parody checks and then the code words。

Are exactly the vectors which satisfy every single one of the parodity checks。

So the variables are like Boolean variables。 Yes， everythings going to be。

 Everythings going to be binary。 Y， exactly。 So at the end of the day。

 you should think of each of these as， you know， an x is basically a 0，1 labeling。Of these vertices。

so that's sort of what x looks like。And then x projected onto N of J。

 that's just some five coordinates， some five components。 That's going to be like a 5 bit。

So this is basically establishing evenness of parity of various subsets of the left hand side。

That's what's going on。So like， what about this set， Could you imagine a bipartid graph。

Which corresponds to this code here。One vertex on the right that's going to be every time。

 That's exactly right。So this corresponds to having a single constraints。

Which variables are involved， all of them。 so it's one node on the right。

 and it's like a star to the left hand side。In general， throughout this lecture。

 I want you to think of these graphs as being sparse。 Okay， so think， for example。

 that maybe each parodity check involves like a random subset of 20 variables， ballpark。

 and maybe each of the variables is involved in like 10 different parodity checks。 Okay。

 So think of it as a sparse bypart that graph。That's what you should have in mind。So in particular。

 we're going to have lots of parity checks， and they will be overlapping in their variables。

So this one may have 10 variables and maybe two of those variables are also in some other parity check。

 that's fine。Okay。So， the goal， then。Okay， so just， I mean， literally any bipartite graph。

Without any further assumptions， induces a code。 O， so this defines a code。

'Exactly the subset which satisfies these parish checks。

But now to have a good code and your favorite definition of good， presumably。

 we need to- it's going to be a subset of all possible graphs。

So let's think about what kind of graphs would lead to curves that are good in some sense。

And so the focus in the lectures。Its to be sufficient conditions on the graph G。So that， well。

 first of all。It should be that we can correct。Many errors are the minimum distance between any two code words should be big。

And hereby big， I mean， you know， a constant fraction of n。

So let's say at least 1% of event or something like this。 Okay， so even if， you know。

 one out of 20 of your bits are getting flipped。 okay for this very long message， you can still。

 there's then its still you're still closer to the original code word than any other code word。

 so you'd really need a ton of corruptions to actually push something to get confused with some other code word。

So that's the first thing， but then。We also want to actually do the correction。

So the decoding efficiently。可。So that's what we mean by good。All right， so here are the conditions。

不给被告给来。And these conditions， you know， basically correspond to what people call low density parity check codes。

Okay， so LD PC。So you do a search on that， you'll find lots and lots and lots of papers。

 The parity check， you know， it's kind of obvious what that comes from， right。

 the constraints are all these parity checks， the low density refers to the fact that the graph is sparse。

 so bounded degrees right。All right， so LDBC codes。So the version we're going to look at is。

 I would assume that the left hand side is regular。So， deregular。So in other words。

 every variable participates in exactly the same number D of parity check constraints。 Again。

 think of D is 10。 Certainly O of one， okay。Similarly， the right hand side。

 we want to have constant degree。 It may or may not be regular。 It doesn't really matter。

But degree O of one。Again， think of it as maybe like 20。

think of maybe the right hand side as being half the size is the left hand side and having double the degree。

And then the important thing is we want an expansion condition。Okay。

 so if you haven't seen expanders before， this is another。

Very nice concept that this lecture will introduce you to。

So the third condition we want is the following。For some constant Delta， independent of n。So， that。

For all not two crazy large subsets of S。 So let's say， you know。

1% of the nodes or something like that。So for all subsets of the nodes。But as large as linear in n。

 so remember， delta is a constant， independent of n。

The condition talks about the number of distinct neighbors。To set has。 Okay。

 so I introduce you to the notation N of I or N of J， that's the neighbors of a single vertex。

 Okay so when I say n of a subset of vertices， I just mean the union of all of their neighbor sets。

 Okay， so N of S is everybody that has at least one neighbor in S。Now， if you take a set S。

And every node in S。Has degree D。What is the maximum number of distinct neighbors that you could possibly have。

 So what's an obvious upper bound on the size of NFS？D times S， Yeah， exactly。

 right So each vertex and S could have a most D neighbors。

So this is going to say that it has almost the maximum possible number of distinct neighbors， okay。

So， at least。I'm just going to instantiate all the parameters， so let's just say three quarters。

 anything about two thirds would work for all of the arguments today and Wednesday。

 but at least 75% of the maximum possible。Okay。So there's no way it's bigger than D times is Car out of S。

 It's actually to be 75% of that maximum amount。 And the point here is that this is true。

 not just for some S， but literally all exponentially many subsets of size up to Delta times n。Okay。

 so not even a single set of size this or less fails to have tons and tons of distinct neighbors。

What's the intuition behind why this is a useful property。Thats we'll get to that。 So， yeah。

 a lot of lectures about that， explicitly。Okay。All right。So one thing I should say is， I mean。

 this property is so strong。 I mean， you should sort of。Demand that there are examples。

 So it's really not at all。 obviously that this is a non vacuous definition。

 It's not obvious that any graph satisfies these properties。So。All right。

 but the people so everyone's clear on the concept I hope。 So here is your set S。And here is N of S。

 and N ofS should be big， no matter what S is。So the definition is clear， support definition。Okay。

All right， so。One thing I'll put on homework six。Is very classic application。

 The probabilistic method， which says that these graphs do exist。 In fact。

 if you choose when a random， it's overwhelmingly likely to satisfy this property。 Okay。

 so almost all graphs are expanders in some sense，So without high probability。A random graph。

That satisfies one and two， so the conditions on the right。Also satisfies。3。

As n grow sufficiently large。 Okay so with high probability means as n goes is large。

 the probability is approaching one。So intuitively， I mean， this is roughly the same。

 you can think about like you just take D random functions。

 So you take a random function from S to C and you just superimpose D of those。

 And this is roughly claiming that what you'll get if you superimpose D random functions。

 then you'll get this expansion property。So that takes a calculation， it takes a churn off bound。

 then a union bound， some of the stuff that's also in homework5。

 and so it's a good thing to leave to you。But so that turns out we're not going to worry about that。

 Okay， so people do worry a lot about， okay， can you have a deranized。

 explicit construction of expanders， that's a hard problem。

 But if you're happy with a randomized construction， Monte Carly construction。

 then just pick one at random and you're done。So that sort of mirrors what we're talking about with compressed sensing too。

 right where we wanted these matrices whose kernels had this almost Euclidean subspace property and it wasn't at all obvious。

 but it turned out a random matrix works okay so similar theme here。

 a random graph gives us the property that we want all right？Okay。So。So given a graph like this。

 again， we have， we get a corresponding LDPC code。 And so now I want to develop。

The idea that these codes are good in various senses， okay？So the first thing I want to prove。

Is that the minimum distance between any two code words is， in fact， linear and n。 In fact。

 it's lower bounded by the same Delta times n in the expansion parameter。Okay。

So the point is it's growing with n okay at the same rate。So distance。Of such a code。

So at least Delta times n。Okay。And I mean， in codes sort of one of the things you're looking for is you're sort of asking。

 you know， okay， to be resilient to errors， you need redundancy。

 So always the game is sort of minimize the amount of redundancy， know。

 subject to having a certain amount of robustness properties to error。

 So this this is an optimal in sense。 But this is like a good sanity check。

 Okay So it says basically as n grows， you're basically still know using a constant fraction of the coordinates for information as opposed to just for redundancy。

 Okay that's sort of the point here。So Delta here is sometimes called the rate。Good。

 so why am I doing this， Why am I doing this proposition， Because in some sense， I mean。

 this is not a computational result， right， So just arguing about the distance just says so this is going to imply in principle。

 if you have strictly less than delta n over two errors。

 then by just computing the nearest code word to what you received。

 that's going to be the intended transmission。So that's the what we know。

 So this gives us an information theore result， It says we have enough information to figure out what the person sent。

 but again， sort of the goal， I mean， for the whole class and particular for these lectures is to focus on computationally efficient solutions。

But still， you know， this is kind of obviously a prerequisite for having a computational efficient solution。

 where you have to at least be able to do it in principle that we will have a polynomial time algorithm。

 Also， I think this proof starts really showcasing why expansion is a useful property for codinging。

 and in particular for decoding。 That's another reason why I don't want to do the proof。

 which is which is not long。All right。So right， remember。

 the code words are exactly those that satisfy all of the parity checks corresponding to the right hand sides。

We're going to use that in proof。あ。Alright， its a proof。So suppose x is a code word。And suppose Z。

Is close in haming distance to X， whos。So I'm going to write D sub H for the hamming distance。

 number of differing coordinates。So what we need to show then is that Z is not a code word。

That's exactly what the proof boils down to。 Okay， Show me anything。 It's not a code word。

 it can't be too close to anything that is a code。Sorry， if's too close to a code word。

 it cant itself be a code word。Okay。So。Consider the Dh of Xz。

 consider the ham distance number of coordinates in which they differ。Here's the claim。

The claim is that there exists。A parody check。So a note on the right hand side， so again。

 don't ever lose sort of sight of the picture。So VC and edges whenever a particular variable participates in a particular parity check。

So there exists a parity check J。Such that。Exactly one。Coordinate。I would say variable， Is say。Yeah。

 coordinates fine。Coordative S。Participates。And the constraint。

So take 30 seconds and convince yourself。That if we prove the claim。

Then we've proved the proposition。Okay。So what's the reason Well， x is a code word。 So by definition。

 it satisfies every single parity check， including parity check J。Z on the coordinates involved in J。

 differs on exactly one coordinate。So if X satisfied this parodity check and this other thing is often exactly one coordinate。

 it's going to not satisfy the parodity check。And that means it's not a code group。So remember。

 if you just flip one bit involved in a parity check。

 it's going to go from satisfied to unsatisfied or vice versa。

 So this basically says like from Jay's local view， right So think of one of these constraints。

 these parity checks is just pretending like there's only these 10 variables in the world And if it sees exactly when those get flipped。

 it's going to go from happy and or vice versa。So this says if。

They differ sufficiently if you coordinate， there always will exist a parity check。

 which has that property。Okay， theres a proof of claim then。

And this is where we use the expansion property。Well， think about S， right。

 So S is a subset of the variables of small size。So S corresponds to some region of the left hand side。

Okay， and the size is small enough that the expansion。Condition。Holds is triggered。Okay。So。

 first of all。The total number of edges。Sticking out of S。Well， it's deregular on the left hand side。

So we have the number of vertices times the degree。Sticking out。On the other end。

 by the expansion property。We know that the number of distinct neighbors。Of S。

There's at least 75% of this number。O。So there's something like 100 edges sticking out。Okay。

They have to be going to at least 75 different nodes。

So that leaves only 25 edges left over that could be second edges to any of these nodes。

These 75 ones of distinct node have to be distinct。25 left over。

 those could takes 25 of those 75 and make them not have unique neighbor， but that still lose 50。

They have a unique neighbor。Okay。Oh。So， there's only。D over four con on best edges left over。

After accounting fall of the distinct neighbors。So in fact， there's not just one parody chick。

That has a unique neighbor， there's tons of them。Okay。So， at least。34 is minus1 quarter。Times Ds。

Nodes。Of van ofz。Have a unique neighbor。In S。OK。Any question about that。

So that's why the claim is true， and then the claim implies the proposition。So intuitively。

 this expander property is sort of saying， you know。

 you have kind of maximal disjointness between what the different parity checks are doing。

 subject to the fact that there's enough of them that they have to overlap to some degree。So agreed。

O。So they've got big distance， at least。There remains the question of how can we actually do this deco coding efficiently？

So any questions for get to the。When you're programming。

 relaxation and some discussion of when it might be exact。Everything clear。All right。

 so the same way we did with， say the cut problems。 a few lectures ago。

 let's start with an integer programming formulation。 This is already actually sort of interesting。

 and then the linear programming formulation will be sort of obvious given the integer programming formulation。

Okay， so I formulation。So intuitively， right so we're given。呃。We're given some received。Vectctor Z。

 O， so given Z。Which， like everything else， is a binary in vectoror。

This we're assuming this is sort of not a code word。

 It was obtained from a code word that got flipped in some small number of coordinates。

 less than Dlta。We want to know what is that code word？So very rough， I mean。

 so just very high level。This is the optimization problem we want to solve。 Okay， so we're given Z。

 we want to solve for x。With minimizing the haming distance and what are the feasible solutions。

 the feasible solutions are just the code words X。Okay。So this is kind of in English what we want。

So let me show you how we take this and how we turn it into a。Enter your program。Okay。

So there's going to be these variables X， where the semantics are very clear。

 So this is literally just the coordinates of the code word that we're computing。

There's going to be X size that we're solving for。Now， I had to tell you。

 how do we express the objective。And how do we express these constraints， Okay。

 the objective is easy， actually。So it's some notation。 So let's say。嗯。

So let's let I be the coordinates。It's a different color up。So let's say。

I is the coordinates on which Z I is0。Okay。So we're given Z this corrupted code word。 It's 0 on I。

 capital I is going to be one on capital J。 Okay so capital J is going to be the complement of capital I。

And so then the objective， hamming distance。We can just say。Wherever z was0。

 we would also like to be0。If we're not zero， then we pay a penalty。it's the one we pay a penalty。

And wherever the received code word was a one。We would also like to be a one。

 we're trying to minimize having distance，And we're going to pay a penalty。If we're not a one。

That's our objective。Now， let me say it's going to be convenient to simplify this。So namely。

 I'm just going to delete these ones。If you think about it， for every single code word。

 every single feasible solution， these ones contribute exactly cardinality of J to the objective function。

 It doesn't matter which code word it is。 Okay， so if I just drop that cardinal of J。

 the relative ordering of the solutions is still the same。 So the optimum is still the same。Okay。

So actually， the objective function that we're going to use。Is。Minimize over the zero coordinates。

 X minus over the one coordinates。Exile。Okay， that's the final objective。嗯。All right。

 so how do we encode？X being a code word。Okay。So， constraints。This is a nice idea， actually。

So let me tell you the intuition。So， first of all， by definition。

 x is a code word if and only if it satisfies every parity check。 Okay。

 And so we want to kind of imagine， again， we sort of want to put ourselves in the place of one of these parity checks。

 which is only staring at like 10 variables。 Okay， so a given parity check J basically doesn't care about any of the other variables。

 It just paying attention to these 10。 Okay， Some variables to these 10 some assignments of these 10 variables will make it happy。

 Some won't。So we're going to have one constraint per。Per parodity check saying that locally。

 this constraintsstrains local view makes it happy。

But then we're also going to have constraints which say the local views of different parity checks should be consistent with some overall assignment。

Okay。So。For a given parodity check J。When AJ。Be the sort of local assignments， if you will。

 that make it happy， okay。So this is going to be。Like a 10 vector。Okay。

 so N of J are the variables that participate in the parity check corresponding to J。

So this is just one assignment， Boolean assignment to each variable participating in this constraint。

 and it's happy whenever there's an even number of ones。So parity of Y is even。All right。So again。

 this is just like imagine parodity check J staringing only at the variables it cares about。

 These are all the things that make it happy。And the way we're going to encode this in the integer program。

Is we're going to have y j comma a。All right， so we have a decision variable for every parity check。

And for every possible kind of local assignment of its variables。That makes it happy。

With the interpretation that Y J A is one。If。In the code word we're computing。

Its value on the coordinates that this parity check j cares about is equal to a。And 0， otherwise。

Okay。Now， we've seen things like this before。 So just because you haven't lost the notation。 I mean。

 we've seen stuff like this before。Just with a little less notation。 So， for example。

 what were do in our linear programming， relaxation of multi way cut。Very， very similar。 Okay。

 so in multiway cut， we had K terminals。 and each vertex was being assigned to exactly one of those K terminals。

 Okay， so we had these variables， which were like y of V comma I。 V gets assigned to I。

 And then we sum them and said they should equal to one。 here， you know。

 it's basically the same thing。 We're basically saying， look， there's a given parity check。

It has its variables have to be assigned to something and they have to be assigned to something with even parity if this is going to be a code word。

 and we're just saying let's enumerate， so rather than enumerating each of the K groups that a vertex could get assigned to in a multiway cut。

 reumerating the different possible even parity assignments that one could make to the parity check J's set of variables。

 so it's exactly the same。And so the first set of constraints。

Which references these variables are for every parity check。And again。

 this is exactly what we had in multiweight cut。 So instead of summing over the vertex groups。

 we're just summing over the satisfying assignments。And overall。This is sum to one。Okay。

So any questions about that？So this says parodity check J， you better make it happy。

By picking some little A in capital A sub J。That's what we're saying。

Haven't we just created a huge number of variables。 Good， one for each possibility。

 It's a good comment。 So let's think about how big is AJ okay。So of depends on how big n of J is。

 right， So， you know， So J is a parity check。 There's some number of variables in it。

 If there's like  five variables in it。Then there's 32 assignments in all。

 half of them have even parity。 Okay， so A of J would have size 16 if there were five nodes adjacent to it。

 in general it's going to be exponential in the number of neighbors So this motivates the low density part of low density parity check codes。

 So remember， conditions 1 and 2 said this should be bounded degree， should be constant degree，10，20。

 something like that。 Okay it's not sensible to write down this linear program。

 if you have a really large number of variables in a parity check。

As long as the parity checks are sparse， this is legit。Okay， legit。

 at least in the sense of being colonmial size。Okay， and polynomial time software。O。So。

This is not good enough。So without further constraints， there can be feasible solutions。

 meaning assignments to X and Y， integer solutions to X and Y， so that it is not a code word。

Do you see why？So notice there is nowhere in this integer program。

 do X and Y appear in the same line？So theres currently no coupling between the x values and the y values？

I mean， there are in terms of the semantics。RightI mean。

 so what we're thinking why corresponds to is this。

 But y is really just some binary variable that the inger program can do whatever it wants with。

 and the only constraints that we have right now are these。So without further constraints。

 what the integer program can do is it can set the x's to whatever it wants。O right。

And if you look at it， if you look at the。Well， it's going to depend on Z right Yes。

 you're going to set to Z exactly right So you're just going to set it to Z that obviously minimizes ham distance with respect to the thing you got Z。

 And the complaint to be， oh， but Z' is not a code word。 I thought that was the point well， yeah。

 But the only way you're trying to enforce it being a code is through the Ys。 And for the Ys。

 I'll just have each parity check independently pick its favorite satisfying assignment to its own coordinates okay。

Now， these parodity checks overlap。 So you should complain that like a variable number 17 appears in these two different parodity checks that should have the same value。

In both of those parity checks， but that's not up on the board anymore。Okay。

So that's why we're not done。 We need sort of consistency constraints。

 which link X and Y and in particular， say that you know， whatever one parity check thinks X I is。

 other parity checks should think the same value。Ss how we do that。So for every edge of the graph。

 So again here I is a variable， J is a parity check in which that variable participates。

This is how we're going to write it。We some。Okay， so we have some fixed parity check J。

We think about all the local assignments we might conceivably use to satisfy parity check J。

 Thiss capital A sub J。 And then we focus only on the ones where X O is set to one。

 So let me use the notation a of I。Oops should be a。A of I equal to1。 Okay。

 so that means in this particular assignment， X I is set to one。And then here。

 I'm just going to write Y JA。Now， think about this constraint in terms of the intended semantics。

 okay。So in the intended semantics， you have these Y J As， and all of them are 0。

 except for one value of a， for which Y J A is equal to1。 Okay。

 and that corresponds to the assignment of these variables。 Either X I is set to 0。

In this local assignment， or it's set to one。Okay。And so what we're doing is we're summing overly over the subset of satisfying assignments where X I is set to one。

And so if one of those is， in fact， the one used， that will contribute one to the right hand side。

 if actually we're using one of the other ones， the sum is just going to be empty。

 it's going to be a bunch of zeros。 and so x I will be zero。So it actually does what you want。

So summarizing， I claim， at least that if you take any code word。

And you think about the induced values of the X I's and the Y's， according to these semantics。

 you certainly get a feasible solution。 But now also。

 the converse is true now that we've added the constraints 3。 Okay。

 the only way to satisfy these constraints is， in fact， well， first of all。

 the constraints 2 insist that every parity check is sort of locally satisfied。

 constraints 3 says actually， there's some you know。

 consistent assignment to X1 through Xn that induces the Y's through this relationship。 Okay。

 so the only way you can satisfy2 and 3 is。By setting X to be a code word and Y is to respect this relationship。

Any questions about that？Okay。So， let's summarize。So we have a one to one correspondence between code words。

Of our。LDPC and integer 01 integer solutions to the integer program。The optimal solution， know。

 because of our discussion with the objective function。

 the optimal solution of this integer program is exactly the nearest code word to Z。Okay。

 so solving this integer program really does solve the nearest code word problem。

Now that's an NB hard problem in general。So recurring theme right so just like how multiway cut without stability constraints tend be hard。

 know underdetermined linear systems， without some assumptions， it tend be hard。

 so we're going to look at the linear relaxation and then we're going to ask when does what are conditions in which it's exact。

We put X， I and 0，1，2。Yes， that's the very first thing I did。But yeah， you absolutely right。

I went from， sort of。East to understand， hopefully the hardest understand。

 So I thought that was a good place to start。Ha。😊，Okay。Alright， so the so the LP relaxation then。

Is the one you'd think。Given everything so far。 So minimize that objective function。

Subject to the local consistency， So the local sort of satisfaction constraints。

The feasibility constraints， or sorry， the consistency constraints。 But instead of the 0，1。

 you just have non negativity。Constraints。Okay so this we're going to call LP。

And if there's only a constant number of variables in each parity check constraints。

 then we can solve this linear program in polynomial time with a caveat that indeed the number of constraints or even the number of variables。

 the number of Ys is exponential in the number of variables appearing in a parity check。All right。

So here's the theorem， which will kind of prove half of。For the rest of this lecture。

 and then I think we'll only need about 30 minutes max on Wednesday to finish it up。

So there's sort of a sequence of papers about LP decoding in various codes。

 The result I'm going to discuss。Is from 07， Feldman， Malkin， Cveio。Forget the second S。

 Wayne Wright。Sin， Stein Wininwright。And so basically， so remember。

 we had this sort of preliminary litmus test。 What can we at least recover in principle， And we said。

 yeah， as long as it's a graph that satisfies those three properties， then we can do it。

 Now it's going to be basically the same statement， but we can do it in polynomial time。 Okay。

 so one of the constants will get a little bit less。 But otherwise， it's exactly the same statement。

 but now constructive。Not only can we do it in polynomial time， but in fact。

 we'll do it just by solving this LP。So if the graph G satisfies one through three。

So this just said D Regor on the left bound a degree on the right to that expansion condition and Z。

So the received the received of transmission suffered at most。elDelta not in errors。Okay。

 so our expansion condition。 so the information the result just had Delta times n。

 Now it's going to be Delta not n where Delta n is a constant， smaller than Delta somewhat。

 but it's still independent of n。 So it's still a constant fraction。 LP is exact。Okay。

That's the main resort。This LP of coding stuff that I'm going to cover。

There's a lot of other results of this flavor， but this this is a nice。

 relatively famous and representative result。So is it all clear？Okay。Good。

So here's how I'm going to split up。 I'm going to make the proof modular in a similar way I've done for many of these other recovery results。

Namely， we're first just going to study what are some sufficient conditions under which the algorithm would work。

And then we're going to connect our assumptions about the input here on the graph G to those sufficient conditions。

 I'm going to do that first part today， I'm going to do the second part tomorrow。

So today I want to introduce a technique， a new technique， which I alluded to last lecture。

 but you haven't really seen about how you'd go about proving a result like this。

 how would you ever establish that some linear program， which in general is not imager。

 how would you ever prove that under some extra condition it is guaranteed to be integral。

Something just， as a sandy check notice。If we solve this thing and we get back an imager solution。

 all the x's and y's are 01。Then we're definitely optimal。

We're not worried about that right because remember。

 the integer solutions correspond exactly to the nearest code words。

 So if we optimize over everything， we get an integer solution in particular。

 it's the best integer solution。 So it has to be the nearest code word。The the worry。

 and this will happen in general because it's empty hard。

 The worry is that we get something fractional， fractional X is fractional Y。

 and it doesn't correspond to a code word at all。 So it's not really about proving optimality。

 It's just about proving integrality。 that's really what the theorem is about。とかも。Okay。So。Good。

So let me just a preliminary observation， which I'll put on the homework。

 although the argument simple。Which is that if we want to prove this theorem， as I've stated it here。

Actually， it's good enough to prove it。In the special case， we're the nearest code word to Z。

Is the all zeros code group。notice for any code like this。

 the all zeros will be a code word because you definitely satisfy every parity check you could ever write down if you're all zeros and the claim is just that by symmetry。

If the LP is always integral when the nearest code word is all zeros， then it's always integral。

 no matter what the actual nearest code word is。 Okay。

 and that's a simple shifting slash translation argument。 Okay。

 so let you think that through offline。So this will save me some notation in the class。So enough。

So the general case reduces to the special case where the nearest code word to0 is0。Allright。

So that means what are we trying to prove， we're trying to prove that the best solution to this linear program is just to set Xi equal to zero for every single I。

Okay。Given that the nearest code word is actually all ex equal to 0。

 we' just trying to prove the linear program will solve to that。Notice that if all thexi is equals 0。

 then the objective function value of LP is also equal to zero。Okay。

So we're basically trying to prove that there do not exist feasible solutions to the linear program that have negative objective function value。

Which， of course， is not obvious because we have those minus terms on the coordinates in J。2。

So let's just focus on the case where the nearest code root is all zeroes。

 And we're really hoping that this solves to that solution and ask， when would that happen。

So sufficient conditions for success。嗯。And the idea is an important one。

The idea is what be called a dual certificate。Okay， so basically。

 what the argument is going to be using is LP duality。

But if you haven't really studied linear programming or duality， don't worry for two reasons。

 first of all， we're only going to use the easy direction of LP duality， not the hard direction。

 and secondly， even that， you don't need to know what it is because I'm just going to give you a self-contained proof but for those of you who know duality。

 try to spot how this is just a special case of weak linear programming duality。

I mentioned this in passing last lecture when we were talking about semi random implant planted models。

Rian on that。Yeah， that's okay。Because we talked about how for planted models。

Relatively simple algorithms can work。 But if you have a semi randomum adversary。

 the only one of the only node ways to get recovery results is through using semidefinite programming。

 And then we wrote down a semidefinite program， and we argued that it was a relaxation。

 And then we didn't prove that it was exact。 I just stated that it was exact。

 And I said that the way that that's proved is by guessing and checking a suitable due。

 and what we're gonna to do now is exactly that happily it's for linear program。

 So it's going to be an easier argument。 we can just finish it in the rest of the lecture。

 So this is really an example of the same kind of argument used to establish the semi randomum model recovery results。

OK。So here's a definition。 And this is going to be the nature of the certificate。 Okay。

 so the kind of result we're going to get is going to say it's going to be， know， a little abstract。

 I mean， we'll do some examples to get a feel for it。

 But the high level picture will be we'll say if you know， a certain。

If a certain set of weights on the edges of this graph exists。

 then it'll be a sufficient condition for this linear program to solve to the integer solution that we want。

 Okay， so we're going to reduce。Exact solutions or an integral solution to this to a more combatorial kind of existence statement。

All。So keep in mind this biparttheite graph that we've got。Rertices over here。

 parodity checks over here。Varis， constraints。So what we're going to be looking for is we're going be looking for an assignment of weights to the these edges。

 Okay， and the weights might be positive。 They might't be negative。 Okay， we're allowed to use both。

And we want weights with certain properties because these are going to guarantee the success of our algorithm。

So， edges。W。For this graph G。Are called feasible。If。They meet three conditions。Okay and they're all。

Simple enough。So let's remember what capital I is， right， So we received this corrupted code word Z。

 okay。I is the coordinates where z is zero。Given that the ground truth is 0。

 these are exactly the coordinates where there was no bitf。 These are the uncorrupted coordinates。

 The other ones are J。 Those are the ones。 Those are also the corrupted coordinates。 Okay。

 So we're thinking of I as being like 99% of the coordinates and J as being like 1% of the coordinates okay。

So for anything which is not corrupted。It should be the case。So remember so this is a variable。

 so I would correspond to like something here。The weight should satisfy the property that if I scan all the insert and edges。

 the sum of the weights should be less than one。O。So if I sum over all of the neighbors of I。WIJ。

 that's the most one。Okay。That's the first condition。

 So that's for uncorrupted coordinates or coordinates of Z。

 which have a 0 in them for coordinates of Z that have a one， exactly the same thing。

 except those one becomes a negative one。So it is actually going to force some of the weights to be negative if you think about it。

So some of the way it's incident to a corrupted to a one has to be at most。-1。

So let me just put this。No， I shouldn't do that。So two， I and J。Some of the WIJ at most minus1。Yeahば。

Now， if that's all there was no big deal， right。Just set all the weights to like negative infinity。

 We're fine。Okay。So the third one is sort of push back in the other direction。

And so for the third one， we about we think about things from the perspective of a parodity check J。

And we're going to look at a pair of variables， I andI prime that participate in this parity check。

Okay， so that's two edges。And we insist that their total weight is non negative。

So one of them' is allowed to be negative， but when I take this sum of a pair。

 it should be non negative。嗯。So if we have J and C。An I， I prime。In the corresponding constraints。

you neighbors of Jay？And it should be the case。That。WI J plus WI prime J is not negative。Okay。

So just get to start getting a little， So I'm going to prove to you in a second is that whenever you have feasible edge weights。

 the linear program solves to integers。So in other words， what this definition accomplishes。

 it reduces what we really care about。Proving exactly linear program to proving existence of one of these things。

 Okay， now， upfront， that's it's not clear why that's useful because it's not clear it's so easy to verify these things。

 Okay， but at least to sort of start giving you a little bit of a feeling for it。 Like。

 let's think about the case where there were sort of like very few errors。Okay， so intuitively。

 we sort of know what's going to happen。 right， We know that basically， you know。

 if I just give you as input， you know， Z equals 0。Then the LP is going to be fine。

 it's not going to do anything else。 It's going to give you back x equals 0。

And we're sort of thinking that， you know， okay， if only a few things are flipped。

 probably the linear program is going still be fine。 But then eventually once we corrupt enough。

 the linear program will give us back fractional answers or something like that。 But actually。

 if you think about the linear program and proving exactness。

 it's kind of like how was that going play out So how where is this phase transition where it goes from being exact and nonex and how would you have a proof the kind of。

Looks like that。Whereas you know， now that we've reformted as far as the existence of feasible edge weights。

 you can sort of get some feel for like why you know there'll be some low level of errors where you can prove these exist。

 and then there'll be some high level errors where you can't prove these exist。 Okay。

 so it seems a little， a little bit more something you can get your hands on。For example。

 suppose every vertex， every coordinate was in capital I。Okay。

 so that would be like no errors at all， which is stupid。 Let's just think about this definition。

 okay。If you have no errors at all， then you have a budget of one。On every single note on the left。

For your weights。And all you got to do is make sure all these pairs are not negative。

So if everything is an eye。An obvious feasible solution is set tau equals 0。Sorry。

 I said W equals zero everywhere。Right。So that that's just a quick saying to check。 But intuitively。

 it's of like， okay， but if there's very few errors， this should basically still work almost， okay。

So like， here's maybe a little bit more intuition。 So suppose everybody on the left has exactly degree 10。

 say， okay， And let's say just there's a few people who got corrupted。 Okay。

 so there's a few vertices， a few variables in capital J。 Okay。

 So now it's sort of annoying because there's a few vertices where you actually。

 some of their weights has to be  -1。 basically， right， That's what two says。

 right This is really annoying， okay。So you're like， okay。

 well maybe I'll just split that -1 equally among my 10 incident edges， like minus01 on each of them。

 okay。And then for the guys and I， I'll just have them be like 0。1 everywhere or something。

And that's actually going to work if you have few enough errors。So if you think about it。

 when is that going to go wrong？Right so here you have。So let's just focus on two of the villains。

 which have been corrupted。I and I prime，So these are both in J， capital J。

 So here some of the weights has to be below -1 okay。

So we're thinking about just having like minus1 over d。So minus01 on interested three。Okay。

 so imagine we just take every single coordinateord that's a1 and we put 1 over we do on all the infinite edges。

What could go wrong？You think collli on one one of。Exactly right。 Exactly right。

 So what could go wrong is if。We have two corrupted coordinates that show up in a common parity check。

Why is that a problem， Well， let's look at condition 3。

Condition 3 says that for every parity check constraint and every pair of vertices participating。

 the sum of their values， of their weights has to be non negative。So if you have two that collide。

 then each one's contributing minus1 over D and that's negative， so that's not okay。On other hand。

 conversely， if the errors are so sparse， you only get one error per parity check， this works。

 actually。Which is nice。 So it just feels a lot less brittle。 I mean， you can kind of feel， you know。

😊，How maybe， you know， we can imagine a little bit more having a proof that argues about when these things exist and when they don't。

Now， to prove that these exist as far as we want， we're going have to have basically a more clever version of this argument。

 a more adaptive version of this argument。 And thatll be， that'll be Wednesday， okay。

So that's all to develop your intuition a little bit for， what these things look like。

 what's the nature of the constraints， you know， why， know， how we're gonna to use them on Wednesday。

 But the last thing I owe you is I owe you a proof that whenever these exist， in fact。

 the LP is exact。So is everyone clear on all that？Okay。All right。 And so this。

I'm going to be honest with is a little tedious。 So I I'm going to do it anyways。

 just because it seemed unfair to put it on homework。And it also seems。So crucial for the argument。

 I didn't feel comfortable skipping it but just going to warn you。And again。

 for those of you that know LP duality， you'll recognize this as。As instantiation of it。

 unfortunately not the， not the clearest instantiation of it， but。Okay， so here's the here's。Limma1。

Lment 2 will be Wednesday。If there exists feasible weights。Then。X equals0。Is the unique。Obsolution。

T your program。ThatExact what you want。So we saw a linear program and out pops the nearest code word on a silver platter。

All right， so we talked about how。The objective function value。

 right of this target solution X equals 0。 The objective function value is 0。Out of all the x's are0。

 the objective function， remember iss just the sum of the x's on I minus some of thexi's on J。

So what we're going to prove。We need to prove that basically anything else has strictly positive objective function value。

So W be feasible weights。And X， Y be feasible。For the linear program。Okay。So W satisfies this stuff。

 1，2，3， and X， Y satisfies constraints Pren 2 and P 3。

And we have to use most of those properties in the proof。O。So， first of all。

So you want to prove that this's feasible in your programming solution。

 It always has non negative objective function value， and its objective function value equals 0。

 if and only if x is the all zero solution。 that's what I want to prove。

So let's look at the objective function value of this feasible solution。All， so some over the Xs。

For the zero coordinates minus the sum of the Xs in the。One coordinates。

This is going to be challenging。Ch。Okay， yeah， so I guess well， this is good。

 So I'm going to use properties1 and2 right now。 Okay。

 so some of the weights around a zero coordinates strictly less than one。

 some of the weights around one coordinates strictly less than -1。So I'm going to just， you know。

Imagine。So if I like， there's a coefficient of one right there。

And I can think of this as being a coefficient and a minus1。Cen。

So by substituting in the similar of the weights， I get something that's only less。 Okay。

 So this is the objective function or a feasible solution。 I claim it's lower bounded。Bye。This。Okay。

 so I just stick in some of the weights。Incident to the variable I。嗯。Okay。

So this is by conditions 1 and 2 of feasible weights。 I'm also using the fact that x is non negative。

I call that。Moreover。If the conditions I just erased were strict weights of strictly less than1。

 strictly less than -1。 So this holds as a strict inequality。

 except in the special case where every x is 0。O， if at least one of these exercise is strictly positive。

 like get a strict inequality。So what I've done is I've reduced Lemo1 to proving that this stuff in white is not negative。

That's the rest of the proof。 If this stuff is not negative。

 that says everything is strictly positive， except for the one case where x is always 0。

 which has objective function value of 0。 That means x equals 0 is the unique optimal solution。

All right。So。Serious real estate problems。P。All right， so we need to prove this is non negative。

 right， so goal。拿哪一。Alright， so what's next。So let's rewrite this a little bit。

So what are we doing here right So okay， so let's this is just over the zero coordinates is over the one coordinates。

 let's just combine these two， the expression and the sum is the same either way。

 So think of this as the sum over all of the left hand side nodes。So what are we doing。

 We're summing over the left hand side nodes1 by one。 When we get to a left hand side node I。

 we just sum over its neighbors。 Okay， So in other words。

 we're counting every edge of this graph exactly once okay。

So let's just be a little more explicit about that。So this is equal to。The sum over the edges。Of W。

 I J。Xi。So the circled quantity and orange is exactly this。 to use sum over all the edge weights。

 except when you get to a given edge， you multiply it by the x value that of the feasible solution of that particular variable。

Now， I'm going to use these。'm going use these constraints。 Okay。

 so I'm going to expand the X I's in terms of the Y's。そそ。去。So basically， in these derivations。

 there's these types of math were basically。You know， the first time you see it， you're like。

 how would anyone come up with a proof like this。 it's kind of like at some point。

 you realize it's like it's one of those proofs where there's only one like applicable step at every step。

 So you literally just follow your nose and it just like writes itself。 and you have this。

Page of math。 But it's like a correct proof。 And somehow， it goes from being。And， you know。

 kind of inscrutable to being almost trivial。 Right So that's what happens here。

 It's like we start with the objective function value。 We say。

 does either one of our constraints apply either for the weights or for the linear program。

 And then if not， then you reverse a double sum。I'm not kidding。

 That's the algorithm with that algorithm， reverse a double summer， apply constraint。

 You can do every week dual proof you'll ever see。So what I did here is I applied the only sort of applicable constraint。

 which is we had the X is want to go the Ys。 I don't know how to interpret that。

 but there's a lot of sums there， so I'm going to reverse them。It's true。

You can be algorithmic in your proofs as well。All right， so what is this doing。

 So we go through each edge。 So this think about this。What is this thing doing？Right。

 so this sums over each edge one at a time。 And then when it gets to an edge。

 it looks at the constraint， and it basically looks at all of the potential assignments。

 satisfying assignments to this constraint in which this variable is equal to one。

So reversing the sum says actually， let's instead。Go over the assignments one by one， right。

 So rather than going over the assignments of A J last， let's go over the assignments of A J first。

 and then sum over the variables in that assignment that are set to one。

 That's what the sum reversal means。So the dust settles and what do you get， this is what you get。

I can erase this。 I've used this。Bye拜。All right， so equals。So let's sum over the constraints first。

 then I want to sum over the satisfying assignments for the variables participating in the J constraints。

The y values only depend on the constraint in the assignment。 I can put those first。

 And now I'm going to sum over the variables set to one in a given assignment， okay。So I， for which。

A of I sets it to one。Cool。All right。So let's look at ss。 Okay， so now it， now it， now it。Well。

 the only thing we havet used basically is condition three of the feasibility constraint for weights。

 So that has to sort of be the key。 But let's think about some special cases。

 So don't forget what we're trying to prove。 We're trying to prove this thing non negative， always。

That was the very first step， we can prove this is not negative always， we're done。So。

Let's just think about a few A's， okay。So assignments。

 locally satisfying assignments to the J parity check has an even number of ones。 could be 0。

 could be 2， could be 4， could be 6， whatever， okay。So what if like nothing？And A is set to one。

What is this final sum？What does this thing？Zero， it's just an empty sum。So that's good。

 I want to prove this it' is not negative， right？What if？

The assignment A sets exactly two variables to one。Booone， condition three。It's not negative。Oh。

 but what if it sets four to one？Where what。It's fun。Break four into two pairs of two arbitrarily。

That applies to each pair of too。As a sum of non negative things， it's still a negative。

 and that's true， no matter what even number it is，So。

That's what finally happens is the double sum sort of isolates。

 know this part of the quantity so that， you know。Inter sum value by inner sum value， the sorry。

 outer sum index by outer sum index。 the inner sum is non negative。

 So we're using the non negativegativity of the y here as well。All right。So that's Lema 1。

Lmma 2 is going to say that as long as J is not too big。 Remember。

 J are the coordinates in which there are ones。 I。e。

 J are the coordinates in which there's been corruptions because we're assuming that the nearest co to0。

 I。e。 J is the coordinate where sum of the weights have to be less than -1。

 Okay so the pesky variables where some of the weights has to be small。

 as long as there's at most Delta not times n of those。

Then we're going to show a constructive proof for how to come up with these feasible weights。 Okay。

 and the argument actually isn't that different The naive thing we tried to do first where we just said it to be -1 over D everywhere。

 We're basically going to do like a mildly。 well somewhat more clever version of that。

 where we also make use of the expansion properties of G， which we know is important。

So any questions？Then to be continued on Wednesday， see you then。

