# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p46 P46 -BV1LvkgBtEQN_p46-

![](img/8ae25e8de049a7041529d8364eca4a37_0.png)

So， last class。We。😔，Have been talking about circuits。We had Boolean circuit。

 So we showed the interesting results like if MP is contained in P slash poly or。

Express contained in pe slash poly。 Then what happens。Basically， polar heric collapses and。

Some very surprising or。Weird things happen， which we don't believe。And then， we started。

Another reason。We started expelling this remain reason of defining Boolean circuits。

Which is to model parallel computation。In contrast to the sequential。V of solving problems。

 which is duringuring machine。 Turing machine is step by step。 It's just one processor。

 which is doing the computation instead。In parallel algorithms， we want many processor。Right。

 so many tuuring machines。 how do we model that。So for that， we say。呃。

That if you have polyan processors， think of them as as these and or not gates。

And the connections between them are the wires。And the depth of the circuit we want to be。Log n。

 poly login， which is the which is the time complexity。Okay， so this。

 we will call efficient parallel algorithm。Which has poly and many gates or processors。

And the depth is polyloggan。Which corresponds to polyloggan time。

In parallel right so this should be true for all Xs of all length。 So again。

 for different and the circuit may look very different， the algorithm。

 parallel algorithm may look different because after all。

 you have to take these these many processors， poly and many processors that is growing with n。Right。

 so this is a mode。 this is a。Concept where circuit is a natural construction or concept then。

Application of this you can see in parallel algorithms like adding to in bit numbers。In parallel。

 so if you do it sequentially， it will take order in time。But if you use many processors。

Order end processor， then you can actually do it in order login time。Okay。

 that I leave as an exercise。 so now。This is nicely captured。By Boolean circuits。Of depth。Poly logan。

Okay， so we polyan size and polylogin depth。This is like time and sizes like。The processors。

 number of processors。And with that， we can now formally define。What is called next class。Okay， next。

 next is。The nickname of Niolalas Prepener。Who is credited with studying this。For the first time。So。

Any language， L。Is set to be in N CD。NCD is the new complexity class D。Some constant。If。

There exists a circuit。Qi。😔，嗯。In fact， I should say。If there exist， a constant see。Greatitter than 0。

And there exists an L uniform， lock space uniform。Circuit family。Xiyin。Which size。As I said。

 we want size to be only polynomial in n。So size is less than equal to n to the C and C is the absolute constant。

And C is a circuit。As N grows， it becomes a circuit family。

Which can be computed in the connections can be computed in lock space。Okay。

 that is what the uniformity means。 So it's a lock space uniform circuit family。

 You can actually produce the circuits very efficiently。

 surely poly time you can produce them and depth， most importantly。Is at most。Log into the D。Okay。

 so this D is the。Prameter of the complexity class。 So for constant d say the equal to 0。

 what does the equal to 0 mean， it means that。Yeah， okay， so let me。Put a biggo here。

So d to 0 means that depth is constant。Right， that's N0 N1 means。Depth is login。

And size always is only poly。 only polymial size is allowed。Because these are classes， N C Ds。

 such that。The circuit family C N computes L。 So for all X。0，1， to the n。X is contained in。In。😔。

X is a yes string， if it only leave。CN X is one。Okay， so Cn solves well。Using polyen gates log in D。

 so polylog。Dippped。And based on this， you immediately get the complexity class。And see。

 that's next class。Whi is union over all， N Cds。Okay， so in this， remember。

 I should have mentioned this。That the fanin is constant。Su。😔，Here， the fanamine of C。

Is assumed to be。Constant。Okay， so this is the constant funding in。Version of circuit。

 which we are talking about。 So in constant fanin， the depth is log into the D。

 We can also make the fanin。So fanine is how many inputs are entering a gate right that is that we are fixing to with2。

We can also allow。Fanning。It could also allow arbitrary fanning。And in that case。

 it has a different name。Then it is called AC。D。So L is in AD。Kind of another class。

 short form for another class。If。Xin。If the circuits。Xin above。Have fanamine。Unbounded。

Unbounded means。That it's allowed up to。The size。Okay。

 so fanom cannot exceed the size of the overall overall size of the circuit。

But it can be as big as that。 So anything is allowed when anything is allowed。

 we call it unboundunded famine， and we call the。Problems that you are solving ACD。

 that' is the complexity class。Okay， and we can also take that union。And call it easy。No。😔。

An easy observation is that。NCD。Is contained in ACD。Because ND has found in too while。

Constant while ACD has an any fan unbounded fan， so it' is clearly contained。And moreover， EC D。

 you can do an N D D plus one。Why is that。So， the idea is。If a gate has。S inputs。Den。

We can simulate it。In logs depth。Fanindu。Circuit。Right， you can check this as follows， so。

Suppose you had four inputs。Okay， so you had 1，2，3，4 inputs。And you were computing a gate。

On these four。 So instead you can do it two at a time。So first， you compute this these two。And then。

 these two。Next， you compute these two。Right， so。You can break it up this output that is being computed。

Instead of computing it at once， you can compute it in two steps， so that is depth2。And also。

 found in too。So， via this reduction。嗯。Inputs。If they are， if the fanamine is。Bolin。Then， you can。

Glow up the depth。And reduce the fanin。 So this means that。Fand in polyan。Of famine into the sea。

 size or depth。Log Dn。😔，Translates to。You can manage in funding2。And increase the depth。Okay。

 so that is what that is the claim that ACD can be computed in。NC D plus one。That finishes the proof。

And。By this containment so we have sandwiched ACD and Ns。And hence， easy and since are equal。

They are equal and in terms of time， what does it mean？Well， since this is。

Parael algorithm is also sequential。 So it's in P。Okay， that should be clear。And the open question。

 of course， here is。Whether N is。A subset of proper subset of P or not。Right， which is like asking。

Can every algorithm。Be made parallel。Okay， an efficient algorithm。 can it always be made parallel。

And we don't expect so， so we conjecture is that N C is not equal to P， but this is an open question。

Su。😔，As in exercise。I leave it to you。That this。NC 0 is smaller than strictly smaller than AC。0。

And AC0 is strictly smaller than m1。Okay， I leave this。To you it has a simple proof。

 So N0 is since the depth is constant。And the famine is also constrained。

These are actually local functions， constant locality。It cannot solve anything more than that。

Any function that you compute in N0 every bit， I mean the or the output bit will depend on only constant many。

Input。Inputs right because the fanin is constant， depth is constant。While this is more complicated。

 So here you use parity。Okay， so parity function， you can。Computing N C1。Again， by this。嗯。

Doubling procedure， recursive procedure， you do it too at a time。

So you can compute parity in login depth， constant finding 2。But you cannot compute in a C0， okay。

 so。This is a。Very interesting result。And not easy。Okay， you can try your hands at this。😔。

We do such things in advanced courses， and。Yeah， so of the。Meta theorem here is。Any language hell。

Has efficient。Parallel algorithms。If and only if it is an N。Okay， this is this take this more as a。

Definition of efficient parallel algorithms。Okay， if you can find an N circuit， then it is。

Solvable in parallel polynomial time。 Okay， we can also compare this class N C1 E1 with lock space。

 so。Dippped。Of the circuit。Get depth corresponds to。A parallel of time。But it also corresponds to。

Sial space。Okay， so if you actually simulate this circuit by duringing machine， then。

The space required really depends on the depth of the circuit。Right， this is natural because。

The depth， I mean， unless you compute the previous the。Value below。 you cannot go up。Right。

 so that much of memory you need to。Have。That is the rough idea。Forly。

 what we will show is this theorem。That N1 is contained in law is s。In lock space。Which you know。

 is in N L。Which actually actually similarly in easy one。So y is N1 in L。How do you show this。嗯。

Basically， in a circuit。嗯。What you can do is。And here you have a variable。Okay。

 and here you have the circuit value。And rest， you have。Some circuit connections。

So this path that we have path that we have drawn from X to C。This has depth login。

And so the way you can simulate the computation of this circuit just in log space， login space。

Is by recognition。Okay， so。Basically， compute。Start from。The root。And compute。嗯。Its inputs。嗯。By re。

Reusing the space。So。The recurnce for this procedure。Right， if you start at the route。

 it has two inputs compute those recursively。Reusing the space。So the recurrence for space becomes。

Is Sof。Y。Less than equal to S of。L，-1 plus。So。When you go down， then the。You are going deeper。

Into the circuit， right。So， L is。In the top， it is。Logan。And then when you go below it is l 1。

 so here it is level L while when you go below it is L minus1。

 and it can only reduce log n order log n many times， right so。Once you have the。Two inputs。

 then the space needed is only constant， so that' is order  one。Okay。

 so this this this is the space requirement is it is。SL is equal to Sl 1 plus order 1。

Which gives you。S L is order L。So you just need the lock space。For this simulation。

You C X computation。C， x is computable。Yin。Lxby。So N C1 is in L。That's what we have shown。

L is clearly in NL that is trivial and y is NL in EC1？Let's focus on that。So， for this。

You basically express。Select L be a problem in Nl。With tuuring machine， M and input x。Of Li and。

Right， this is the setting。You have a problem in Nl。L with T machine M， which only takes lock space。

 but its a N DTM。And it is solving。 it is running on inputex。So what is the number of configurations？

So， number of configurations。Is。두 레2。The space。Right， which is。At most， the tourists to log in。

Let's call that bound begin。So， they are。Begin many configurations。It's basically polyinian。And。

How the NM moves from one configuration to the next there are many options right it is an NTM so we can express this as a as a configuration graph。

Let's call the decency matrix a。Liyi。😔，Be the adjacency matrix。Of the configuration graph。O Emex。

M1 inputex。Right， let A be the edency matrix。And now all you have to do is to。Check weather。

The start configuration。Is connected to the accept configuration。That's all you want to check right。

 so this reduces to computing。E to the n。Matrix powering。Or in fact， Boolean matrix powering。

E to the end。RightThat is what you basically want to。Check that in end steps。Whether you can reach。

From C start to C except within n steps， So you have to compute this a to the n power。

So by repeated squaring。Compute this。In E1。Okay， this you can do easily。So， again。And then in a1。

 what you do is you express。This as a， I mean。Ass a matrix powering question。

What is the matrix the matrix is basically the adjaency matrix of the configuration graph of the NDTM。

On a certain input， this entity team only requires log space。

 so the configuration graph is not too big。Itucency matrixes begin， times begin。So。

 you have to compute this。E to the n。And check in entry。And checking an entry。Or testing an entry。

The this entry， which will check is。This is C start row， C except column， whether that entry is 1。

Right， so you just have to compute one entry of this powering。

So the way you do it is by repeated squaring， so you compute a square a to the 4 a to the8 dot dot a to the n。

This is only login。Sts。And so you can express this as a circuit of login depth。

With unbounded fanamine。 So that's exactly AC1。Okay， so you can simulate。

NL in A1 and N C1 in lock space。 Okay， that's the gap between N C1 and A1。

 And remember that all these things。They are。Living in。N C，2。Right， so we have a。

Classification or complexity classes， famous complexity classes between N C1 and N C 2。

 So that is a nice result。To know。And。Using this lock space now， we will do something。Newu。

Which is P completeness。So is there a P complete problem？So， we call problem B。Bihard。If。

For all problems in P。Or for any problem， A and P， A can be reduced to B。Now。

 if you say polymial time reducible， that will not give you anything interesting。Will will say。

 willll make it stronger。 Well say that。Within lock space， you should be able to reduce。So， if E。

We had this implicit reduction concept， right？So the same thing implicitly， L reduces。Dubbi。😔，Okay。

 so a should L reduce to be implicitly meaning that bit by bit there is a lock space reduction。

Of course， in lock space， you cannot produce all the bits。That will lead。More than login space。

But a single bit。I mean， x string。Of a can be mapped 2。Some string way。And bit by bit。

 it's a lock space。Reduction。Okay， then we call B P hard and。Of course。P completeness will be。

Additionally。If B is in P。Then we call B， P complete。Okay， so that is the notion of P completeness。

It's kind of the hardest problem in。The deterministic polymer time class。 So are there such problems。

So does there exist。Unnatural。Focus is on natural。P complete problem。

So this is what we will define next。

![](img/8ae25e8de049a7041529d8364eca4a37_2.png)