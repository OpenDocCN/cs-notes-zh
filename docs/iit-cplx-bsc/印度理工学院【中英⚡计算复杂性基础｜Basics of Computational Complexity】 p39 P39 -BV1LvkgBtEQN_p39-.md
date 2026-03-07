# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p39 P39 -BV1LvkgBtEQN_p39-

![](img/afbf5c0c5bec1a90e6fbbc7f147f6318_0.png)

So。Next is。Claim2。Where we start with a large s。And we have to find K points。OrK vertices。Such that。

Starting from this says。Everything is a neighbor。Now， since we don't have any information about S。

We cannot do this。 We cannot f construct use systematically。

 So what we do is we give a probabilistic argument。Since we。Don't have extra information。About S。

Or inside us。We only know the size。 we don't know the exact elements， right。V。😔。

Will we try to construct。You。😔，By a probabilistic argument。Okay， so this will be。

Will be an interesting proof。Will probably。So how will， how do you use size of his， right？

 That's the。Point of this。So choose you went to UK randomly。Okay。

 so instead of trying to construct them or design them。

 you just pick them randomly and let us now calculate gamma US。Does it work。So， let。Or you will。

Basically， calculate the probability that Gamma US is everything。So let ER be the event。That。

An element R is not in gamma US。And let E R I。Be the event。That。😔，R is， sorry， not。Not in。

Not a neighbor of his， because via Ui。So， R is not in。S plus joy。

S plus U I is every element in is you are adding you are exoring with U I bitwise。Okay。

 so basically we are interested in the probability of this bad event that。

A point vertex R is not a neighbor of。S。So， let's estimate their probabilities。So what are there。

Probabilities。So probability of。The event， E R I over。This random view。

So if you pick you went to UK randomly。What is the chance that R is not a neighbor of。S， via U。So。

 this is。1 minus。Ad plus S。The size of that。By tourist to m， which is the size of。H space。Right。

 why is that， So R plus S are these。Good。Strings。And Ua is not one of them。

So these are actually the use that work。These are the U， such that。Uai is in art plus。

And since E is the event that。UI is not in art plus。Vi。😔，Subtract that out。

And then what you get is with So this is equal to1 minus。Size of s divided by two is to M。

And what is size of S。In claim two size of ss， size of s by2 to m is more than1 minus2 to minus n。

So this is less than equal to2 is 2 minus n。Okay。So which is a very small probability。

 This event happens with a very small probability， when， which means that。

If you now look at probability of the event， E R。So E R is the event that。

Our is not a neighbor of us by any of these voice， right。So you have to go over U 1 U 2 UK。

 So that's。Product of probabilities。And each of these probabilities is tourist to minus n。

 so you get。Two is2 minus K， N。And the way we have defined K。For this reason， we define k2 be m by n。

So what you will get here is。2 is 2 minus M。OkaySo the event E R happens with probability smaller than tourists to minus m。

Which means that the probability， when you randomly pick you。That there is an hour。

There is an hour for which year happens。This is。And where is this R， this R is in the space。0。

1 to the M， right。So， this is。01 the the size of this space。Times the probability。

 which is2 is to minus m。Which is just one。This is by the union bound。

So hence the probability that there is some string outside。Gma US for random use。It's actually。

Less than one。 That's the probability。Which means that。The probability。Over random view。

Says that all the ares。Your doesn't happen。Okay， this is positive。Which means that。There it exists。

So， sub you。Says that Gama US is everything。Okay， so by showing probability positive we have shown the existence of U。

Sos that every R is in the neighbor of。Neighbhood of comm， US。Okay， so this。

 this finishes the proof of claim 2。And once we have both these claims。We are almost done， because。

What do these claims tell you。So claims 1 and 2。Imply that。For all eggs。Input strings。X is in L。

If and only leave。They exist U1 to UK。Sas that for all are。

They exist basically just set you with k vertices key points such that for all R。嗯。One of these。

R ex Ui。Is Zhu。Right for a sum。So they exist to set U。This is that no matter which are you take。So。

 this domain is。0，1，2 the m。So， from this domain there will be these no matter what you want to U choice of you want to U says then no matter what are you pick。

A。One of these strings are exorary。For one of these you。

Will be a good string for the yes input string X， right， This is because。

This r plus Ui that we picked， its in S。Because R plus Ui。Istiness for some。Did it exist in Ie。

Sas that r plus Ui is in S。 It's equivalent to saying that。Gamma US。W are U I， There is a neighbor。

A is a neighbor via UA。Of some point， in the。Yes， okay， so that is for the。Yes。

String x for the no string X。The set will be so small。That no matter what you want to U， you pick。

This statement will not be true。Okay， but simply because gamma US is not everything。

 So that is what claims one and2 have shown。Which is nothing but。Showing that L is in sigma， too。

Great， soul。E is in Sigma 2， which means that BP is in。The intersection。Okay。

 so that finishes sipers。Q room。And although we don't know B PP in NP， this is still。呃。

A good amount of information， because it's telling you。That BPP is an NP to the NP， and its core。

And what it also tells you is the following。So this in particular， means that。If B， P P has。

An NP hard problem。Then what will happen。Yeah， let me not get into this。

 Let me just ask this as a question。So could the B P P have。An N P hard problem。Okay。

 what will happen if theP has an NP hard problem， Does it， Does this result give you anything。

 any indication。So practical implication will be huge because。

It would mean that you can in particular， solve a sat。By a randomized polynomial time algorithm。

RightAnd so that will already solve all these hard optimization problems in practice。

And to formalize those connections， let us move to。Randomized reductions formally。So。

 randomized reductions to。N P， which is to set and lock and also lock space。

recallcall that you have seen this while we were trying while finishing toda theorem。

So their sat was randomly reduced to parity set。呃。And we can now take that concept。

We can formalize it more generally since you have seen probabilistic tuuring machines now。Su。😔。

Language Ei。Reduces to B。In randomized polynomial time。Well denote it like a less than equal to。Od。

Subscript sub B。To mean that it is a randomized poly time reduction。

 not a deterministic polyial time1。If。😔，They exist of poly time。嗯。Probabilistic tuuring machine。Mm。

Sas that， for all input text。Probability of。So M will transform the inputex to something else。

 M of x。And this will be given to B。And we want this to be equal to a of x。

So the chance that this happens will be quite good。Okay， here probability is over random bits of M。

So， so this is a new notion of reduction。Okay， A reducing to B。V a probabilistic。Transformation M。

Which is a problem， which is a polynomial time probabilistic tuuring machine。

 And with it with good chance， X will be map 2。嗯。Correct， M of fix。Okay， so that E gets solved by B。

As I said， you can recall here what we did。With polymial hiarchies。

 So we show showed that every problem in polymial hierarchy actually reduces to par T P。

That is what we had shown and。Now， we can define。This helps us to define BP as an operator on complexity classes。

Su。So， we can define。Randomized version。Of Neno。Well call it BPp dot MP。SoBP dot NP is。

Defined to be the set of those problems。They are reduced to set。In randomized polymial time okay。

 so if if it was a deterministic poly time reduction， then this is exactly the class NP。

All problems R N P reduce to set， but we have now allowed the transformation to be。Randomized。

 So we are not very， very sure whether。We have gone above N， or we are still in N。Okay。

 but this is a way to define。New classes by randomization。So， in general。We can define。

For any complexity class。BP， dot c。To be the set of those languages that。Reduce to C。Okay。

 so BPp is is a new operator。And， of course， it's an open question。 whether B PR NPs N。

OkayN is clearly contained people or N because you can just ignore the random bits， random choices。

 but we don't know whether it's。Bigger。Or exactly equal we conjecture it to be sorry。위컨잭 to be 있 있고。

We conjectured them to be equal， but。Nobody knows for sure。 Some easy properties now。So N p。

 as I just said， is a subset of B P dot n p。And when you。Do go of this。 What happens。

So by via this randomized reduction， you can check that。This is the same as B， P wrote， Co N P。Okay。

 so this code and B P， you can。Interchange。Okay， so co of BPP do n p is the same as BPP dot co and P。

So this you can think of as the randomised version of Co and P。And just like。嗯。

BP acting on these channel complexity classes， we can also define it for log for space bounded classes。

Sou。Or for small classes， we have to change polynomial time to lock space。For smaller。

Complexity classes。We can use。Lock space。Vant of reductions。So， you get。B， P。So， L is in。P， P L。If。

There exists a logan。Space probabilistic tuing machine。M。Such that for all the input strings x。

Probability that。M correctly computes L for this input。This is quite high。More than two third， and。

Random bits of M。That's the probability， probabilitybilities over the random choices that am made。

Okay， so M this is just saying that probabilistic during machine in lock space work tape。So。😔。

V tape of size。Order login where any the input size。It is able to。

Come solve well with high confidence。It is two third， which can be amplified to close to one。

And so this is just lock space reduction based on this， we can now also refine classes。I mean。

 using this reduction， we can define classes。So， let us do that。New classes oral。Yeah， let me。

Take that back。 We can use lock space restriction。On work tape。So we are actually defining。

L space computation。 So instead of L， we have defined B PL。 I mean， we have kind of expanded L to B。

 PL by using this。Probabilistic tuing machine。And we can ex expand in a different way。

 which is one sided error。Instead of these two siders， so that's RL。So L is in R。If。Again。

 there exist in order login。Space probabilistic tuing machine。M such that for all input X。X is in L。

 if I only leaf， x is a yes string， if I will leaf。sorry。There will be two conditions。

For the yes strings， error is allowed。But not more than error cannot be more than one third。

 error to 1 third is allowed。For the no strings， no error is allowed。So for no string。

 you cannot get one。You'll get 0。Okay， and willll always reject。So if this happens， then we say。

That problem is in R。This is the one sided error case。So， R is。One sided。Error while B P L is。

2 sided。O， like we did for B， PP and R P similar。Definition。



![](img/afbf5c0c5bec1a90e6fbbc7f147f6318_2.png)