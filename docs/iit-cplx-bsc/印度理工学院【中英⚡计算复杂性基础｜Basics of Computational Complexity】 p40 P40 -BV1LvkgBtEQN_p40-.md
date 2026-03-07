# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p40 P40 -BV1LvkgBtEQN_p40-

![](img/7f8dc208d80fe13b356314d039851201_0.png)

To last time。We defined， we started the。Reductions that are randomized。So。Which means that we ready。

 we see that problem E。So we see that problem A reduces to problem B。

 We say that problem A reduces to problem B in randomized polymer time if。

Inputex meant for problematic can be transformed to。A string M O fix。

Which will be a yes string of B with high probability。 High should be much above half。

So we have fixed it to be two third， but。As you， as we saw before， the probability can be amplified。

 so it can be anything。More than inverse polynomial away from half。 And that can be met。

Inverse exponentially away from one。And we have seen an example of this， this major example。

 major theorem we did that polymial hierarchy reduces to partP。W are randomized productions， right。

So we reduce sigma set to parityat in a randomized way。But now we can also define。Smaller。Classesses。

 like。Smaller than the polymer hierarchy， I mean， or par T P。Like Bp dot n。O。

 BPP dot n is the randomized version of NP。So these are the set of those problems that randomized poly time reduced to。

St。And in general， we can define BPp dot C for any complexity class C。

We don't know whether NP p is equal to B P or n p， but it is conjectured。

 There is some theoretical evidence for this。And if we take co， then we get。

Randomized version of Co N P。 So B P dot co N P。And same game we can play with the。

Not time restricted， but but space restricted classes like lock space class。V tape is lock。

N space while the input tape is full is n。So B PL， for example， is the set of those problems。

 which can be。呃。Solved by a probabilistic tuuring machine。 that is log space restricted。

And Rl is the one sided error version of this。Okay。

 so this is a probabilistic touring machine lock space。Restricted with。For yes string。

 it says yes with probability2 third。And no string string it always rejects， it cannot say yes。Okay。

 so RL is one sided while B PL is two sided error and what you can show immediately is。

That lock space is in a。because that has no random bits。Oral is in BPL。

So remember that RL can also be defined by a probability half， right， It doesn't matter。

 We can put it here。And then you can amplify it to two third， and。That then is， of course。

 contained in BPL and BPL is contained in。Bi。Okay， this is the non trivial part。

 So this I leave with an exercise。Why is B PL contained in P。 So here the idea is。That in lock space。

 it can only use log many random bits。So you can actually go over all of them。

And you can compute the probability for an input string x in polymial time。Okay。

 so if the probability is more than two third， then I mean， more than R。Are accepting。

More than two third of the Rs are accepting than you say it's a yes string。

If only one third were accepting， then you say it's no string。So this can。

 this simulation can be done in polyial time。Other examples are。Undirected connectivity。Okay。

 so Uon is given a graph and a dec ST2， whether there is a path。And。

For which you know polymer algorithm， right DFS。So believe it or not。

 this can also be done in lock space if you have random bits。So， this has。A simple。Oral algorithm。

The idea is that。You pick random neighbors and do a random walk。Okay。

 so in the graph starting from s， if you do a random walk。呃。

It's a great exercise to show that if t is in the same connected component。

 then with high probability， you will reach T Okay。

 so which means that and the random work can be done in lock space because you。

When you are at a vertex， v then you only need to pick a neighbor。And that only needs lockin bits。

 random bits。And second example is graph isomorphism。So graph isomorphism is this。

Problem of G where we are given two graphs。You can assume directed， weighted。Graphs， general graphs。

Whether they， the tour is amorphic。So， this。Isin。😔，B P， dot Con P。Okay。

 that was a major result several decades ago。It's a surprising thing that。

Graph isomorphism So if there is an isomorphism， then you can verify it。

If somebody gives gives it to you so。It's already in NP。 but if there is no isomorphism what they do。

 it seems that you have to go over all the。Permutation that's n factorial rate。

But here we are saying claiming that。Actually， it can be done almost in copy and it in randomized version of randomized version of。

NP Co N P。 So G I is kind of an N intersection， Co N P。Okay so you can think of this as。

Cranandomized version。Of N p intersection， Co， N p。So， G I is。Then not very difficult。

 It's not very high up in the polymer hierarchy。It's actually lower than N p， right。

 This is what this result is kind of。Sing。And in a major breakthrough。嗯。Bbai gave actually。

 an algorithm。In 2015， case so not many years ago， B bye showed that graph isomorphism。Is in quasi P。

So what is quasis I P。This is slightly above poleomial time。

The time complexity is something like two race2。Log into the sea。Okay， so instead of tourists to end。

 which will be exponential and tourist to log in， which will be polymial time。

 this is somewhere in between。But closer to polymer time， it's tourist race2。

Think of log square in right， So that's end to the login。So exponent is not a constant。

 but at the same time， it is also very slowly growing。Okay， so graph is amorphism has now。

subex algorithm。In fact， quasi polynomial algorithm。But we still don't know whether it is in P。

And now we will show that it's in。This randomized version of。NP intersection Co N P。

 So let's do that。So what is the language GI。That is easy to define。It's pair of graphs。

Finite graphs， G1 G2。And the is amorphic。Right， so isomorphic remember means that there is a way to relaable G2。

So that it becomes equal to g1。 So it is just a re labelling of the vertices。

And graph non isomorphism is the opposite。It's the set of。Pairs of graphs， such that。

They are not isomorphic。Right， so isomorphic pairs versus known iszomorphic pairs。

 And what you can show immediately。As I mentioned before。Is that graph ismorphism is in N。

Because there is a permutation。Ma given G to equal。 So somebody gives you that permutation。

 you can easily check。It's， it's easy to verify。And graph non isomorphism hes in。Ginbi。😔，Right。

 because it's just a complement problem。But what。Is open。

 It is still open is whether both these problems are in the intersection in both these classes。

So whether graph isizomorphism is in Qp。Graph non isomorphism is in。Enbi。And， of course。

If graph ismorphism is in P。so all these questions。

 the first two are equivalent and the third is is asking for a practical algorithm。

For graph is amorphism。And that we don't know。 We actually don't even know。Probilistic algorithms。

Okay， so we don't even know whether graphismmorphism is in BP。That's a major open question。Su。😔。

What we'll do now is focus on G I。 Okay， so well put。Graph known isomorphism。Yin。BP dot n。

So that's randomized version of。Np。Which kind of。Makes the definition that we started with BP P dot N P very useful。

That was the purpose。That will actually show a problem here。An interesting problem。

 which we don't know。Any lure。And that's graph known as amorphism。This is also called。

This is also an example of。What is called a one round。Merlin Arthur。Interactive protocol。

Berlin is the all powerful king or Berlin is the all powerful advisor prover。And Arthur is a weaker。

嗯。Ging。Okay， so Merlin sends proofs to。Arthur and Arthur。Is a poly time verifier， in fact。

 a randomized poly time verifier。And he has to verify。Without knowing the。嗯。

Without knowing everything。 Okay， so Arthur is much weaker than Merlin。

 So there are these definitions in complexity theory， which we do in advanced courses here。

 we'll not do it。 We'll just do G GN I proof and。That's a strong motivation for these interactive protocols。

With public coins。So each of these terms。Actually， define complexity classes。Okayive one round。

 How many rounds then Merlin Arthur。Based interactive protocols。 So let's do this formally。So。

 gold was Sir。Cip Sir。呃。Show this theorem。And started this big area of interactive protocols。

In complexity， theory。So， G and I。The show is in BP， P， dot N P。So what is the idea。

 So the idea is that when graphs are non isomorphic this G1 G2。

 there are many graphs which are isomorphic to one of them。

In comparison to when they are isizzomorphic， G1 G2 isizzomorphic， then only half。

That number of graphs are isomorphic to either one of these two。

So there is a gap okay you have more graphs that are isizomorphic if g1 G2 or not。

And you have less graphs that rise amorphic if G G2 R。So， let's use that。 So the number of。Gs each。

Such that。It is isomorphic to G or。Zidu。Okay， so one of these h is is amorph to one of them。

This is more。And， in fact， doubly more。When G G2 are different。Non azomorphic。Then， when they are。

Okay。So can we utilize this gap。To give a certificate。

 small certificate that they are not isomorphic。So， this largeness。Can be detected in MP P。

So that's what BPP n。Is good for。It will be able to detect that The number of H is more。And hence。

 G G2 are non isomorphic。So。Yeah， you can see that we are somehow reducing non isomorphic non isomorphism question。

2 isomorphism。Once， right， because we are talking about now age isomorphic to G。So in a way。

 we are reducing it。To the opposite。We reduce non isomorphism。2 isizomorphism。Okay。

 and since isizomorphism is an N， we get this NP result。So that's the plan。 Let's implement it。

So formally， consider the set as。Associated with。On in vertices。

So we can assume that G1 G2 have the same vertex set and the same will be for H。

So S is the set of each。So this is an important definition。In。We have each， but we also keep。

A permutation pi with that。 So graph each。Has vertic n。H is isomorphic to G1。Or。

It is isismmorphic to G2。And what is pi。 Pi is an automorphism of each。

So this we are keeping for a technical reason。 the reason being that we will lead。Bound， or in fact。

 we will need the size of S， exactly。So keeping the automorphism helps us in that。Lxihou。

So if G1 and G2 are isomorphic。Then the s， the number of each pie is Ps。

Each such that H is isomorphic to G1。I mean， if H is ismorph G1 iss also asmorph fit to G2 and there is no H of possible。

That' is the number of each and what is the number of pis。So， that is。The number of automorphisms。

Not that number of automorphisms of H and G1 will be the same。So for every every age。

 we are multiplying by number of automorphisms of G1。That actually simplifies our。Calculation for S。

 because。So how many graphs are ismorph effective to G1。That is。It's a number of permutations。

And out of these， you have to divide by。How many permutations are giving you the。sameme graph。Ych。😔。

So that's the number of automorphisms of each。And then you are multiplying by number of automorphisms of G1。

So， you get n factorial。you can think about this if it's not clear。

It's basically a count on how many each are isomorphic。To G1。 That's what you need to understand。

And so， size of S becomes。This number that we already know is n factorial。On the other hand。

If the graphs are non isomorphic。Then what happens is size of s is。

The case when H is isomorphic to G1 versus。Zhiu。So number of each pi。Says that H is isomorphic to G1。

Thejii。Okay， so the sets the part of his corresponding to G1 and the part of his corresponding to G2 you are summing them up。

Each of them you know is n factorial。 so you get two times n factorial。

Right note that the these two sets are disjoing。there is no h that is present in both because that would mean that H is ismorphic to both G1 and G2。

But given due to what non ismorph fixed， so that cannot happen。So。

 so hence we are just adding these two numbers， so。Again， in one， in the first case， isomorphicism。

isomorphic case， you have n factorial and non isomorphic case。 You have two in factorial。

So that is the gap， which I。Elude e two in the idea。SoS is doubly large。😔，Wen。G1 G to is， yes。

 instance of G， N I。And。We know the size。So that's an important thing knowing the size or at least size bounds。

 and we'll use this now。In the protocol。Sunao。😔，Did we give a。General method。

To test this size difference。In B， P， dot n。So， we use hash functions。Okay， so here you can recall。

The P2 par P reduction。Because the。Properties of hash functions that we prove there。

Well be using them。So， let each。Be the map。From this M。Bit vector2 K bit vector。

It basically sends you to。呃。Matrix multiplication， rate。So B， U plus small B。Where。😔，B is。Oh。

Its suitable dimension， appropriate dimensions， it's。K cross same。And small bees。Key bit vector。

So you notice that B U is K cross M times M cross one。 So you get K cross one， which is small B。

Dimenssion， so you can add。Okay so using matrices， you can make basically random matrices define random hash functions。

And the idea is that a big M you are。Oh。Compressing down to。Kay fine。Su。And we also， yeah。

 so basically。This is useful， when。 so hashing is used to。

Almost always it the effect is to actually compress the。Input， so M bits， it will reduce to K bits。

With certain properties。 So will let us now recall those properties。So， the probability。

That there is an element X。In the cities。Which is the pre image of0。As you randomly pick。

The matrices。So， this probability is。At least。Size of S by two is2 k。Right， there are。

S elements in the set， size of S many elements， and there are two as2 K points in the image。

An x that is mapping 2。From S2。0。So that probability is S by tourist to get slightly less than that。

And。This probability is， at most。S by two is2。Okay， so these are the properties that we are shown。

What is the chance that an element in S maps to0 this single point in the image。Upper wound。

 this is upper bound by S by tourist 2 k。I mean， roughly hitting one point in the image fixed point probability is1 by two is2。

And there are S elements。 So it's， it cannot be more than S by two is okay。

But then what may happen is。Collions， so many elements may be mapping to the same element。

In the image， for that。The probability may fall， but it may not fall by more than us choose2 by two is to2。

If that's the rough intuition for these two properties。Let us now use it on ours。

And see the difference。When it is small， what happens， when it is large， What happens。

So we have size of s。And factorial or two times。And factorial。So let's fix key such that。2 is 2 k -2。

And2 is 2 k -1。Sandwich， in fact2 in factorial。Okay， so basically case like log of size of S。

 upper bound on size of S。Let's fix key with that。So the image of the hash function， this2 is 2 k。

 it is slightly more。 It is actually doubly more than upper bound for s。Okay， so we are mapping S2。

Rer。A slightly bigger domain， but case。Is this。So， now。If the set is of size and factorial。Then。

 the probability above。Right， that probability is less than equal to。S by， which is S by。2 is2。

Becomes in factorial by。Tourist to kill。 Let's call this。Bi。

So that's the upper bound on the probability。And when S says2 in factorial。

Then the probability is greater than equal to。Spirus2 k minus S choose 2。By tourist to2。

Which is at least。 So let's take S by tourist to get out。We have one minus S by。

So this is just simple ca S calculation。 So S choose2 is S times S -1。

 be approximated by S square by 2。And you get this。Which is greater than equal to。Okay。

 so let's do this later。

![](img/7f8dc208d80fe13b356314d039851201_2.png)

![](img/7f8dc208d80fe13b356314d039851201_3.png)