# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p47 P47 -BV1LvkgBtEQN_p47-

![](img/17a8d85a12a8052c115eeed06b01ac90_0.png)

1 easy to。Observers。For P complete problem that。Say LSP complete。Den。If that problem is in N。

 that is there is an efficient parallel algorithm for a P complete problem。What it would mean is。

That every problem in P has a efficient parallel algorithm。So N C will we be。

So if you believe that N is not equal to P， then。P complete problems cannot have an efficient。

Pal simulation。And similarly， P complete problem if it is in lock space。Den。

Every problem is in lock space。Okay， so we believe that lock space is different from P and hence。

P complete problem cannot be solved in lock space。NP complete problem cannot be solved in N。

Cannot have a parallel。Sivulation。Okay， so in this sense， a P complete problem is hard。 Okay。

 it's in the sense of hard to parallellyize。Okay， this is the。Meaning of P hardness。So。

 let's introduce it。And again， circuits will come to rescue。 So circuit。Evaluation is the。Problem。

 we will define。So circuit evaluation is the problem of。Given a circuit and an input。

Does it accept it， So is c x equal to 1。So， C is a circuit。Vd。😔，And inputs。1 output。And C， X is one。

Okay， so basically circuits with accepting inputs。That is what circuit evaluation consists of。

 it basically just is asking。Whether a circuit or an input is one Okay。

 so intuitively you have to compute the whole circuit for this。And。

We will show that this is P complete。This is a P complete problem。Circuit evaluation is。Be complete。

So。First is。That it is in P。Why is it in P well， because given a circuit。

 you can obviously compute it。Given a circuit and an input。So given C co my X。It is easy to simulate。

To compute。C， X bio tuuring machine。Right in polynomial time。Efficiently。

 you can check whether you can compute c of x and then check whether it' is one or0。

That's the easy part。 So more interesting thing is。P hardness。Why is it P hard。

 So can you why can you reduce every problem in P to this。In lock space。

 using a implicitly lock space。Reduction。So， let。Lbn P。With tuuring machine， M。Of time complexity。

Into the sea。Where X length is N。So let in other words。

 let L be a problem which is solvable in polymial thing。Seeize an absolute constant。

So polynomial time solvable problem L。And during machine solving it， let's。Start with this。

So essentially you recall cook levin reduction。Great that reductions。Basically， converted。

Every step of the Tring machine computation into logical。Gs。And if you。Go over all the steps。

 then ultimately it is giving you the circuit you want。So as in just let's recall。

 So as in cook levin。We can assume。And。To be oblivious。And translate。嗯。The step。That the I step。

Basically， switch maps configuration C I to C I plus one。Translate the IAT step。To a formula。

And this we can see as a constant size circuit， So this implies that each step。Is a constant size。

Circuit。Let's call it C。So this is the major thing we are。Recalling from Cook Levin。

 once you understand this， then now what happens is。During machine M has many steps。

 it has N to the C many steps。And every step is just a computation of a constant size circuit so you can。

Join them together。And you get a big circuit still of size polynomial。Okay， that is。

Faithfully simulating what M was doing。so啊。😔，Since number of steps。Is less than equal to n to the C。

In fact， enter the sea log n。This means that。We get circuit。Xi。Of size。Into the sea logan。Exactly。

 simulating him。Right， moreover。Okay， this is all fine。

 this we understand that tuing machines can be converted into a circuit。But。

Why is it a lock space reductions。The only thing missing。Su。The Iot circuit。Xi。

This can be determined。Using。Or given。Can be determined。Easily， basically， this is from。

Control of him。And the Iath head position。Independent of。Right。

That is the point of oblivious it doesnt depend on x， it only depends on length of x which is n。

So using M's control。Finight control and the a head position。You can compute the circuit C。Given。

Given I and the previous configuration。Configuration， C， I，-1。Right， so。Taking this as an input。

You can compute the。Circuit。And。All this only requires。So how much space is needed for this。

You only need to basically store I。In space。At most。The length of eye。Right。

 which is what is length ofified。 So I goes up to into the seasuits login。So， what we have shown。

Is that。The problem。In polynomial time， which we took。

As L this has been reduced to circuit evaluation 1 x。L reduces to circuit。Evaluation。

 So you just have to compute the circuit and。If the circuitone x is 1， then x is a a string。

It's l reduceuces to circuit evaluation。B lock space。By lock space reduction。Which means that。

Circuit evaluation。I P complete。So circuit evaluation we have shown is a P complete problem。

And which means that this problem you cannot solve in parallel。So this， you can now。

 we can now make this conjecture。That circuit evaluation。Can't be done。😔。

Efficiently or can't be paralyzed， let's say。Okay， so intuition is that the circuit is already。

 I mean， although circuit is kind of a parallel algorithm， but to for a curing machine to compute it。

 it has to go。In every part。No part can be。I mean， it y it cannot be distributed。

Acro different processors。Okay， one processor has to go through this。Su。😔。

So it's an interesting problem， which is in polymial time。

 It's the hardest in polymial time in the sense of。Paalization， if you want to。

Convert every problem into a fast parallel algorithm。 Then you have to convert。

Circuit evaluation problem。That will suffice。Okay。So。As a corollary， what you get。Of this。

 from this proof。Is this problem of circuit set。Red circuit set is the problem。Of giving a circuit。

Whether it has a satisfying assignment。Circuit C。And there exist in x。Says that it。Evaluates to one。

The circuit set is N complete。Well， this is kind of im， right， so。Circuit set is。Clearly。😔，Yinbi。

So in。In N， because you have to guess just you just guess x。

And then compute C of x in polynomial time， so it' is clearly an NP。And。And three set reduces to it。

3 set trivially reduces。Tally3 set will reduce two circuit set。Okay， so circuit。

What we have shown is that circuit evaluation is P complete where the notion of production was。

Implicit lock space reducibility。And circuit SAT。When this x is not known， you have to guess it。

 this is NP complete。Right， so both these， both these problems are new problems。

 but they fit very well with the known complexity。Already defined complexity classes and circuits also help to understand next。

To study higher classes。Lake Beach。嗯。Pace space。I mean， this even before P space。

 you have this shop P。PH is a question about formulas。 So that is again， a circuit question。

Sharpie is a both sharp set， again。Circuit question。Pace space is about QBF。

And we'll now move to next。It also helps understand。Next， so hows that。So， let's。

Define our next complete problem。Circuits give a natural problem。This for this win， I need to define。

A harder version of circuit set right circuit set is in is in NP for next5 to make it harder。

 how do we make it harder。We make it succinct。Okay， so C。Is a succinct。Circuit。If given eye in。Bary。

So I is given in binary via N bits。They exists a polynomial in end time。Algorithm。To output。

The ice gate。Let's see the I gate， and it's。J。Edge。So let me make this icon come G。So， essentially。

What is the iron gate。And how is it connected to its neighbors。

So what is the eighth gate and what is the Gth edge。How is it connected。Right。

 so this local connectivity information。Is easy to compute。 That's what it means。That is local。

Connectivity。Is easy。To find。嗯。While the graph itself。Is huge。Okay， it can be。

Of the order of Iger N bit。 So I guess tourist order in。Or or square。Okay。

 so if you look at the number of gates， they are actually two ways to win。

And the number of edges can be。Oh。Then two race to2 in。The circuit graph or the circuit tree is huge。

But each interconnection can be computed efficiently。 Okay， so local information is easy to compute。

 This is what a succinct circuit is。And what we can show。The theorum sees。That's succinct。

Circuit set。Okay， this is next complete。So succinct circuit set is a circuit set。

 but where the circuit is given to you in a succinct way。Right。

 so local connections can be easily computed。 There is an algorithm。

 but obviously the whole circuit cannot be given because it is too large。So， if you can。

Test whether it has a satisfying assignment。Then。You can solve next。So， let me point out that。

Circuit size is exponential。To is to order in。But number of variables。Is in。

Okay so number of variables is not very is not explanation， number of variables is just n。

 but the circuit itself has large size， tourist to end tourist to2 n size and so whether given such a circuit in this local way can you test its satisfiability。

This problem is next complete。 So first of all， why is it in next。So， it's in next。

It is a next because you can guess X。嗯。And then， you can。Compute C of x。In exponential time。As。

The size of sea。Is only exponential in them。So， let me。Change some things here。

So this is into the sea。Okay， circuit size is into the C。 C is an absolute constant。And。And then。

Yeah， so you can actually come guess guess x in 01 to the n。And for this x。

 the circuit size is promised to be。Atmost two raised to and to C。For some constant。Xi。😔，Okay。

 so inex can be any consancy， so。Circuits of size2 is to to see are allowed。

 but the information local information will be computable in polynomial time， poly and time。Right。

 that's all what succinctness means。 So the satisfiability can be checked once X is given。C。

 X equald1 can be computed。So that part is the easy part。The difficult part is being hard。

 Why is it hard。So next hardness， we will do。We have to reduce any problem in next to that， right？

So say， selector。L'll be in next。Vi the。Ambin。😔，It's exponential time veryifier。

And input x being 01 to the n。Right， so we have the verifier。 We have the input。

And we have the language in。M is the tuuring machine verifier， and L is the language。

 the problem in next now。The Iot step。Of the tuuring machine。

C I to C I plus one configuration change。This has what will this。Configuration， size B。

This will be exponential rate。 The configuration size is exponential， but。嗯。So this。The small。

 the smallest change from one configuration to the next， this is given by M's control。

So that is a constant size circuit。Which is producible in。In。In how much time。

 So you just have to compare。The locations。So it will be computable in log of。嗯。The number of。I mean。

 the basically configuration size。In this time。Which implies。So configuration size is how much。

That will be。Log of the number of steps。Red， witch is two raised to and raised to sea。

That is polym n。Its polymial and time。Right， so which means that the configuration graph。So。

 this configuration graph is。I mean， or the circuit that you get。The corresponding circuit。

Is succinct。Right， which means that we have reduced L 2。嗯。Sucinct circuit set。

So every problem in next via the configuration graph or where this cooked levin reduction can be reduced to succinct circuit set。

Right， so this is a problem， which is next complete。So this with this， we finished the course。

 we covered a lot of topics。And to learn more， you can do the advanced courses。I hope you enjoy it。

Thank you。🎼。

![](img/17a8d85a12a8052c115eeed06b01ac90_2.png)