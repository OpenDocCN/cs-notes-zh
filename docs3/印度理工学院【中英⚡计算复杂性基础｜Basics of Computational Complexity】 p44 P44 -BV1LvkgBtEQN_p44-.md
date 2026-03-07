# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p44 P44 -BV1LvkgBtEQN_p44-

![](img/6d001640418e3b14692374377b24b5c2_0.png)

So， in the last class。We defined the Boolean circuits。And we showed we first defined these problems。

 which can be solved by。Sistin。Buling circuits。For growing n input size。

And these problems we collect and form a complexity class called size of T。Size bracket team， right？

And we also showed that this non uniform hierarchy theorem。

Or hierarchy theorem for circuit sizes does exist。It's almost as good as the deterministic time。

Harch theorem but has a different proof the proof here is by counting。Okay。

 we did not we did not use dagonization method， but。Counting method。

It's not very clear whether dagonization trick exists here。And then by collecting policy size。

Circuit families， we get this peace slash poly。Complexity class。

 which is the analog of polymial time， but now it is for。Circus， bullying circuits。

 instead of duringing machines。And we were proving that peas contained in pe slash poly。So， this is。

Just a proof sketch。 I will not go into the detail proofs。

It's actually not difficult to finish these proofs。So peas contained P slash poly is done by。

The following， So let X be。I X P the input of fixed length n。And whatever the Turing machine does。So。

 each step。Of the tuuring machine， M on x。It's very simple， right， It's just。

One bit changed in head moving。So that can be easily implemented by and or not kit。

 so each step of the Turing machine Emex。Can be written as a can be implemented by gates。

And are not kids。And then you go over all the steps。

 Remember n is fixed for this right so this will give you a circuit C。V。😔，Find a circuit C。

 we convert。M X into 2。Circuit。Cnix。And。It' is easy to see that since the number of steps is polynomial in n。

The circuit family。Xin。As N grows。Is poorlyan sizeized。

So that means peace containedent peace slash polying。And。So， all efficient algorithms。

 they actually live in P slash poly。Is that all。So， surprisingly。

Because the way peace s poly is defined in a non uniform way。

You can actually have very a completely different circuit for。Length n and length n plus one。

 So in particular。Every so first of all， observe that there exists a unary language。L。

 that is uncomputable。For example。In。Which has those unary strings one to the end， such that。

And describes。A tuuring machine。That holds。So if you take this language。

Then clearly this halting problem reduces to this so L is uncomputable and now what you do is you have a trivial circuit Cn which solve which will accept only on。

呃。When one to the n is in the language， otherwise， it will reject。So， the circuit family。C N。

 such that。CNx is one。CN is one。If on leave。1 to the n is in L， right， this is。This solves well。

Right， so and， and it is of constant size， in fact， not even P slash poly。So。

 this is constant size circuits。Solving an uncomputable solve problem。Right， so。

That shows you the power of。Non uniformity。This is the power of non uniformity。

Because we don't know how to produce C， but C exists。Rightai， so this is the。

It's a non uniform circuit family， it cannot really be produced， but it exists。And hence。

 P slash poly can solve uncompable problems， it can solve the halting problem。So， it allows us。

To hardwi。The answers。So without knowing the answers they can be hardwired right without computing the answers you are just hardwiing it and so they exist circuit exists okay。

So peacer poly is an important class。So， we will。Define it。In one more way。So， p slash poly is。

An important class。Let's define it。Vre tuuring machines。So instead of using bulloleying circuit。

 we can also use steering machine。And then it will be called。Duringuring machine with advice。

So let's define that what is advice to a tuuring machine。It is something like。

Oracl duringuring machine， but weaker。 Okay， so this will actually be。

Somewhere between knowledge atic tuuring machine taking advice and oracle tuuring machine taking advice。

 So we is it is also called we can also call it。Non uniform during machine。So， weve。

A decision problem L。Is in D time。Bin。😔，Baaiyin。If they existed tuuring machine。Duringing machine M。

Such that， for all inputex。There exists so T and air functions right T is the time function is the advice function。

 so there should exist in advice which is a screen。Alpha n。Of that much length。

Such that M given X and the advice。Is one if only leaf。It's a yes stream。Okay， so。Basically。

 what is happening is alpha n is some kind of a certificate and when it is when it is provided then。

And will be able to。Identify x as yes or no string。 The key thing here is the difference from N。

Is that the same this alpha doesn't depend on x？O， it only depends on its length， it doesnt。

 it is not a function of x， it is only a function of n。And。The time， obviously， the time of M。1 x。

Is is T of X。Okay， so M is a tuuring machine that takes Tn time on n sized inputex。

And it works correctly if it is given given advice。For that length。Okay， not for x。

 but for that length。So that's the important point。So alpha n doesn't depend on x。

It only depends on n。So only on the length。N equal to x。To same advice for all the inputs。

So that is a difference from NPp。So this you check as an exercise。

How is this different from NDTM definition or oracle definition？

Okay you can see the differences so that defines d time Tn and then using this we can define p slash poly by limiting T to be polynomials so we can actually put this as a。

Proposition。That pe slash poly。Defined by a boolean circuits。

 policyized bullolean circuit this is actually equal to union of。D time into the sea。

Slash into the D。For all constant， C， D。Okay， so this is another way。

To define P slash poly using tuuring machines。So here there are no circuits， right。

 This is just by tuing machines， so。Lets to the forward direction。Sa L in P slash poly。So why is it。

 why is Ellen？This is D time， this tuuring machine with advice。Well， so since L is in P slash poly。

 it means that L has。Poly size circuit。Xiyin。And you just give this CN as advice。Do duty machine。

Suvian。Give C N as advice。To a universal tuuring machine， to a turing machine。That on x。Of Liinin。

Simply computes Cnx。And hence solves。For whether x is in x is a y string or no string。Okay。

 so this means that。I mean， since yen was of policy， this means that。嗯。To a tuuring machine M。

 So this means that time of M。Is。So there exists C。Such that。Time of M is。Less than equal to。

And to the sea。And the circuit sizes。En to the D。And Su。It immediately tells you that L is in。

D time into the C slash and the D。Okay， so hence it is。

L L is in a P slash poly it is also in the right hand side and lets do the converse。So say。

 Eli is in。D time N the C。Slash and the D how do we show that L P slash policy from tuuring machine we need to go to circuits now。

So， during machine M。X comma， alpha n。呃。Soolves。X and L problem。

 there is this polytime tuing machine。Into the sea time or order into the C time tu machine。

 which will solve。Yeah， we go off into the C time ting machine， which will solve。

Whether x is a year string or no string。For advice。Alpha n。Which is of length。Ento the D。

That is what is given to you so。Let's define circuit C n。As the。Circuit， that computes。Basically。

 it computes the or it simulates。It simulates M。On any input given alpha。On。And every input。On。

Arbitrary x。0，1 to the n。Okay， so given any input of that length。

There is a fixed advice string alpha and that during machine takes and does its computation。

 this can be written as a circuit。And let's call that circuit C。So， this is again。Gold。😔。

This advice is hardwired。In the simulation。And then it can decide for all these。

Inputs of the fixed lengthntin。So you can see that the size of C。Is some polymial blow up。I mean。

 this steering machine has into the C steps， right？The size of in sea， some polymial blew up。

I mean simulation， I think you can do even in quadratics， So it is something like。Ento the2 C。

And it is polynom in。Right， so this means that we have shown。嗯。That L is also in P slash poly。

It has poliized circuits， which means that。We have shown both of them peace left left and side。

 right inside equal。So we have non uniform circuits。And we have non uniformed tuing machines。

These are the same。These are equivalent concepts。So， non uniform。Efficient。Circuits。

And this side is non uniform。Efficient。Tuting machines。Duringing machines that take advice。

 run for polyial time。Or circuits。That two。A of size， polymial。They solve the same problems。

 and they can also solve uncomputable problems。Right， that is what we have。Sun。Now， can this。

Advice duringing machines。Can this solve。Something hard as。Set。There's the next question you can ask。

So。😔，It's a good tuuring machine。With advice。Solveet。

RightIf these steering machines with advice if they are so powerful as to solve uncomp problems。

 can they solve satAT efficiently？So this is an interesting question it is still open。

But what we will show。Is an interesting polymer hierarchy collapse so。Well show the following termem。

This was done by car ppton。1982。It's a classic theorem that sees if you can solve that。

Bipponommal size circuits， which means also。Duringing machines with advice in polynomial time。

And polynoial advice。Then。PH collapses， too。The second level。Okay。

 so everything in the polymer herearchy is equal。이꼴드 segment마2。So it still doesn't say that。

And P will be P。It says that N to the NP。Is equal to everything above。

SoSigma 1 sigma 2 may still be different， but this is a strong theoretical evidence again that。

SAT cannot be solved。With poly size circuits。 So one immediate consequence of this is。Thus。

Bulion circuits。Is a useful way。To study。NP heard problems。Because suppose you show that。

NP is not NP P slash poly。So， this car leptton theorem is saying that most likely satAT is not NP s poly so NP is not a subset of。

P slash poly。And this in particular would mean that p is not equal to N。Right， so we can follow。

The root。This is a feasible root because of caral lipton theorem show that sat is not in p slash poly and then。

Separate P from N right so N sat not in p slash poly is a stronger conjecture than sat not in P。Okay。

 so let's prove carlypton。So assuming that satAT is in P slash poly。I mean， the idea is that。嗯。

Use use circuits， sat circuits。So， if Cn solves。😔，St。Then， use them。To find a satisfying assignment。

So if CN is solving the search per version， then you can also solve the。

If if CNN is solving the decision version， then you can also solve the search for version which is to actually find a satisfying assignment and once you have the satisfying assignment you can actually convert。

Pi 2 set，2 sigma，2 set。So， use this。To convert pi2 set。2 sigma 2 set。

And showing pi 2 in sigma 2 equal。Okay， so this first thing is called self reucibility。

So we can use self producibility of that to basically you can set x1 to0 or 1。And。Ask S itself。

Which one is true？So once you know that， then you know that x1， what how to fix x1。

And then you can proceed to fix xs and so on。Okay， so as soon as the circuit solves set or an algorithm solves that。

 you can also find an assignment。And once you find an assignment， that will help you in。

Converting for all they exist to。They exist for all。So， so which will imply that。Be is。Sigma 2 pi 2。

As before， right。That is the idea so lets see the implementation。So， consider。P to certain instance。

For all you。Did exist， we。5 Uv。Okay， now。If sat。Has， let's say。Size。Am to the E Circuit family。Xiin。

Such that。Cm。Phi， given， given Phi and U。Basically。But there is a satisfying assignment V exists。

Okay， so you is given。And then phi is given and whether V exists or not。Okay， that is a sad instance。

 so suppose it can be solved。Cm is solving that。Okay， so suppose this sat instance is being solved。

So you if we fix you， then v is the only unknown thing， whether it exists or not this a sad instance。

And so the circuit CMm can。Solve it， that is what we are assuming。

And see the set instance has size m。Okay， so we use the。Sircuit corresponding to that size。

 which is CM。Circuit itself as size m to the is some constant。And it is solving this。Okay， so。

Using this C we now try to find V。That will do next。Yeah。🎼，🎼不。



![](img/6d001640418e3b14692374377b24b5c2_2.png)