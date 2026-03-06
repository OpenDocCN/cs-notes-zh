# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p10 P10 -BV1LvkgBtEQN_p10-

![](img/2d1c9399c3ce7c49db69ce0b1c7b11c4_0.png)

So let's now go deeper into this。Start stop and the main complication will be in compute。Right。

 because that is where the。Chunk of the T steps lies。So， start is simple。So this will。

 this is a boolean formula that resultss。The start configuration。Which is SC C1。Fariable。

This has to be Q of。And。The pointers or the。Two heads should be at the beginning。And。😔。

Input tape should have x。And you， because both X and U。Is the combined input。And， finally。

Work tape should be empty。Right， so these are the。嗯。Conditions， and we are doing an and over them。

That start resultss the start configuration， similarly stop。So this will result。

 It's a boolean formula that captures our results。That M stops。And outputs  one。

So which means that the state should be stop。So， finish state。And。Work tape header。

Should come back to the original。Position， and we don't care where the input tape。He is。😔，And。

Work tape should have。呃。The accept。The one bit at the end。Will at the end or be actually。Can we。

Can be more concrete。And just say that。Just demand that one is at the beginning。Okay， so。So again。

 this state is finished it。Work tape head has come to the beginning and has put up one。

In the beginning， Okay， so it has basically cleared the work tape and just put the output。

So so these are the easy Boolean formulas。 You can see that it's just an end of， of。

Equalities and equal you can implement。Quite easily， right， in terms of and or not。So， let me just。

Show how So a equal to B condition。Is implemented as。As。Either both A and B is true。

Or both are falses。Right， so this， for example， implements。That two variables are equal。

 either both are two or both are falses。And yeah， the state variable can take as many values as the number of states。

 but but that is finite and constant It doesn't depend on。Input size。 so you can actually。Do。

You can check these things bit by bit and。Using this。This idea。

This bit equality you can implement also for other strings。So for bits。

 you can implement it like this。And then you can extend it to strings， equality of strings。Right。

 so with this， let us now move to。Compute。 So what is compute。Supposed to do。So， this will assert。

That there is a sequence of steps following the transition function。A configuration sequence。G，0，2。

G T -1。Of the tuing machine M。Starting from C。An ending X C2。Right， so basically。

This talks about their exist。G0，2， G T -1。So g 0 is71， and。G， T，-1 is C 2。And。For every eye from。

0 to t -1。I want to say that G to G plus 1。Follows a valid transition step。Where I means。

It is following some step given by the transition function of M。Okay， so。

This part is basically saying that。Configuration， G， I to。G I plus one。Follows。Transition， I。

Given by。Delta。Now， transition function has only finitely many。嗯。It's a finite description rate。

 It's part of the。Finite control of the Turing machine。So。What this。For all， I part。

Of the formula seeing is。That G to G plus 1。Is coming from exactly one。嗯。

Command from the transition function given by I。 And remember that number of I is。Constant。

It doesn't depend on n。It the number of eyess。Constant。W again， this。

If you think about the definition of clearuring machine。

 you will see that finite control doesn't really depend on the input。

It not depend at all on the input。So this number of eyes is constant， and hence this or is actually。

We are just writing down。Every element of。The transition function。

One of them will be followed by G I to G I plus  one， and then we are going over all the eyes。

So you just open this up。Two times。Get doing an end。So this is an end of tea things。And of tea。

Forulas。Okay， so that is。Those are the comments。 And now， what remains is。Yeah。So let me go back。

 talk about compute again。So compute has been broken into three parts。嗯。Starting from C1。

 which is G0 and C2， which is Gt minus1。There are these。A。G0 to G1 transition。

And G1 to G2 dot dot Gt minus22。G T -1。Alright， so G T-2 to G T -1。All these。Steps have to follow。

They follow some transition， given by。Delta now this has to be implemented or checked by the Boolean formula step。

So we have to go there now。Define that。 What is that。So in general for two given configurations， C 3。

 c4 configurations remember are given by their。嗯。This area， you can think of this array or the data。

Right state pointers， which is head positions and the tape strings。Given this for C3 and for C4。

And also， given。A transition I from this delta。All you have to check in step is。

The bull only has to check whether。C 3 to C 4。Can you go from C3 to C4 in one step using I。

It is just a consistency check that you have to do so you can reduce it to basically equality tests。

And and over that。Okay， so this will be a bit painful。But let us anyways go through this。

So what you want is you want to answer it。That。😔，C 32， C 4。Transition。Or a step。Follows。

The transition。Ai。Which is from on status B1， B2。Under the。嗯。Input head。Repectively work。Tap head。

 you have B1 B2。So from there you go to state S prime。You can not change the input。

But we can change the work tape so make that be to prime。And then what direction to move， so。Epil 1。

4 input tape， Epsilon 2，4。Wed it。Right， so I remember is given to you when you are。

To define a step formula。I is given and it is like this， these seven values。

And C 3 c4 is also given the areas are given now you have to do the comparison。So let's do that。

 finish it。So far Epsilon 1， Epsilon 2。Equal to let's say， stay。Okay， that's one case。

Let's do this case， first。We use the formula。So， this will be。The state of C 3。Has to be S。喂。Well。

 because I。Needs to begin。From S and go to S prime。 So C 3 has to have status。And C4 a sp， right。

 So we are just implementing that。Or expressing that。And then。呃。

We have to now talk about the positions of the input and work tape heads。So there。

 let's say K prime and K， there exist these numbers。Such that。Let me use a different colour for this。

escape prime K。Such that B prime C， J。So c three。Is。P prime C 4。Is key prime。

That's because Epsilon 1 is。Is tea。Input tapia， so。Input tape head should not move。

 so k prime doesn't change from c 3 to c 4。That's where the head is。And similar thing for。

Work tape head。Okay， and。Now， this transition I also tells you about what was under the heads right so this that was B1 B2。

So， here we implemented that。In the configuration， C3， C4。The input tip。head。😔。

Started with B2 ends with B 2 prime。And what else does the transition want， It wants。

You be to not change。It a prime。K prime。C，3 is B1。And rest of the input and workt strings don't change。

Okay， so this is the。Main implementation of。Chicking。Whether a step was correctly followed or not。

 this is the most local check you are doing。 It's from one configuration to just the next。

Following I。Right， so this， I hope， is clear。And but I have implemented this only for stay stay。

There are three other choices， right？In fact， many more choices are there because it's you can either stay。

 stay or you can stay go right， stay， go left。Go left and go right and so on so forth。

All these9 possibilities are there。So， similarly for other。Or。😔，Anlogously or other。

Anlogous expression。A formula。For other Epsilon 1， Epsilon 2。

dependingep on what I was given to you to define a step I。

You can write down such formulas and do the check。For this given C3 to c4， whether it satisfies it。

So this boolean formula is true if I only leaf。This C 3 to C4 followed transition I。Right。

 that's that's what we have achieved。Now， some things are still。Missing。Or， I should。Point out。

S remarks。So first point you have to note is that。😔，X is fixed。X is a fixed string。

Cause that was given to you in the input。A。But will take you as a。Formal variable。Why is that？

 Because remember what was our original goal。Our goal was to。Show that。This problem。

 L in N p can be can be reduced to S can be exp So basically， we want to express the。

Vifier M computation as a。Formula with variables， right， So what will be the variables。

The variables will be the the certificate part， the U part will be the variables。

So I should mention here that the I D in the idea。嗯。A bit。Unknown certificate。Okay， so。

The U will keep as the variable。 So semantics being that if you exist。

 then the formula will be satisfiable。I mean， or if the formula are ultimately satisfiable。

 then there is some U。So that becomes a certificate。Or if the formula is unsatifiable。

 then the U doesn't exist。 There is no certificate。 So that will tell you whether x is in L or not。

Right， that's the original plan。This， I have already discussed that。Equality。On strings。

Can be expressed。As a formula。In CF。Like， that was basically this thing that。First， do it for bits。

 and then。And this over。Each and every bit。Of your two strings。

So whenever I am using equality in the formulas formula description， it can be implemented as cF。

 that is not a problem。When I'm using for all I。Operator。Right， I use this for all。

 for all I less than equal to t -2。So this can be expressed as ants。Conjunction。Right。

 you have basically for every eye， we have given some， some formula and then do it。

Around T many times。 Just cop that many times。That is not a problem。And。

The most important thing which is which I will not discuss here， will not work out here is that。

How to write this their exist key。How to implement this as a cF。They exist K plane K。

 This thing is tricky。Okay， because this remember k prime can take t values and same with k so they are taking t square values。

But their exist means that you have to take an or。Disjunction， right。

 How do you write it as conjunction。So， this needs。Property of curing machine。

 which you will see in the assignment， you will solve it。Well， also， other issue is that。

Not just the or but all another issues that K actually will depend on。The input， exact string x。X， u。

And step I。But U we have not even fixed U we are taking as a variable right。

 So actually this is a bigger problem。Then just this junction because key really depends on what step you are at step I。

What is x well that we can fix because x was fixed that is still okay。But。Yes， I can remove x part。

 but you， we have taken as a variables， we want it to be a variable so then。

K also becomes a variable， and then we cannot write this expression as CF。Right。

 so we need a uniform way。For4 k prime K2 B。Deine we somehow， we should know it already。So。

 the way it is done。Its a。Assume that。M is an oblivious。Juuting machine。That is。

Head positions only depends on。Size of x。And I。Okay。

 so it actually in a way only depends on what is the step you are at。And。

Do already know that function。Function of N， and I。You don't need you for it。Okay。

 oblivious machine Does't need to know。X comma U。So， it's not。Not ex you。That is not needed。

So what this means is that。Souki is known。As a function of step I。And we do not need the。

 and we can express。Did exist， K。S CF。Okay， so this oblivious tuuring machine conversion is true for any tuuring machine。

And。It is without loss of generality。So you do solve this as an exercise。

 This will finish this reduction next time。

![](img/2d1c9399c3ce7c49db69ce0b1c7b11c4_2.png)