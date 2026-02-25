# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P13：-13-Lecture 13 - Specification; Temporal Logic.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

First piece of my， wonderful legends。Go。It's all John F， okay。Allright。

 so coming back to the lecture so by simulation is again is this thing that I can do whatever it does and it can do whatever I do but that's the notion of by simulation now is that the same as language equivalent is not its more its much stronger and we see some example that is the case so now if you have a deterministic machine a good news is that language equivalentvalence。

😊，And by simulation is exactly the same。 If the machines are non deterministic。Not to。

 and we'll see how that can be possible。Okay， so this is the equivalence between the state driving and the state tilted and straight。

 And so for every move that I do up there I can do down here and this state is equivalent to these two states right so I can indeed reduce the。

Dimenssions of the finite machine without killing its behavior。Now。

 what is the difference between equivalence and refine？Equivalence， as we said before。

 is that there is this notion that we can do the same thing。Now when you have a refinement。

 what do you have in mind so I have this thing which is a specification and a specification in general tells me what I need to do。

 but it doesn't tell me things that I don't care about so when I do an implementation I may have to specify everything。

So when I do that， what am I doing？Am I copying what this thing is telling me to do？I'm doing less。

 I'm doing more。What is it。I do more， no， I do less。Indeed， and that's a notion of refinefining。

 Why do I do less。Because if I say the only thing I care is that I move straight right and I don't say which steps I'm going to take。

 it implies that if I do the long steps or the short steps doesn't matter right when I implement the fact that I need to go from here to where。

I need to decide what my stride is going to be。😡，And that is my implementation， right。

 And so it's less。Because the specification contains all the correct behaviors。😊。

And verify it is picking one， right？The implementation speaking one a refinement is a subset okay so it can still be many right so when you go in design in general。

 you have a specification when you do a first refinement， when a second， then a third。

 when a fourth and then you get to implementation and implementation。

 everything has to be decided so the actual implementation is always deterministic right no matter what you do it has to move in the physical space right so it has to be deterministic and if it is not deterministic。

 it means that you don't want to represent a piece of the actual implementation but the thing itself has got to be deterministic。

 the model may be nondeterministic okay。So two state machines M1 M2 that are not equivalent may be related and that's a relation that I was talking about。

 the containment so my behaviors are all contained into the specification so thats it so M2 may be type compatible with M1 in that it can replace with M1 without causing a tight conflict which means that if my finite state machine is input output spaces that are invariial。

😊，Space in real numbers， if I take the natural numbers。

 I have a refinement because the natural numbers are a subset of a real numbers。

 so I'm OK so Im type refine。😊，N2 may be a specializationation of M1 emtic can produce only the output sequences that M1 can produce but not vice versa。

 as we say before right so the specification was saying good from here to there。

 but I am taking a particular stride， so whatever I do is contain is in there。Specation。

 but that specification does more。 So that's what the。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_1.png)

Specialization relation means。M2 may be a specialization of1 in that at every reaction M2 can produce all the output values that M1 can produce。

 and that is meaning M1 simulates M2， so I can do everything that I mean。

 can do exactly the thing that M1 can do all right。Now， in all cases， if M1 is valid in a system。

 then so is M2， so I can replace it right？And I'm not going to change substantially the behavior of the entire system。

 but the only thing that is is matters in all this free relation with we is what we mean by valid。

 so it a type。Containment is a behavior containment is a reaction containment。

 So every time I have to specify what do I mean， what is my metric right So， for example。

 have you ever ask， is Apple phone better than Samsung， you ask me， I would say Samsung anytime。

But why， Because I don't care about Facebook or this kind of stuff。

But I do care about being robust and fast and blah， blah open。 And so for me， Samsung is better。

 you ask him and say no， Apple is better， so the matrix matters better per se doesn't mean anything。

 you have to define what is the space that you are going to use to measure things。All right。

 there is an example of that。Now then M2 for all these three things is a type containment。

 language containment， simulation containment， which means that the refinement notion is related to a particular measure that you are using to decide whether the two things are the same or not。

😊，Now， in general， we also say that M2 implements M1。

 so M1 is the more behavior rich is the specification。

 and M2 is a restricted version that doesn't go out of the space of what M1 is requesting。

To do so now the question is a refinement and then you want to see whether a particular machine is a refinement of another one in with respect to a type and that is very simple。

 So M2 is a type refinement of M1 if now this one is a actor model so P1 are the values x and w that are the input port and Q1 is a set of values that the output port can take So x and w in P1 and in Q1 is y now the other machine that we want to compare with is as a。

Less rich input state， if you like， input alphabet， and there a richer output alphabet。

Now can we say that this one is a type refinefinment of that one well if you have a subset of the types in there certainly true right because I have fewer things and the thing here is contained in there so I'm okay but how come that Q2 has to be larger than Q1 the reason being is that I want to make sure that whatever I put in here comes out that is accepted by one above and so on the output side I can be richer then the output side over where as long as the input type is contained in that input type as well okay。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_3.png)

Now let's go to the garage counter and we know that this thing is redundant so we can reduce it to a single state。

 that's okay。And we know that there are state0，12， et cetera。

 and the states correspond to the output， there is a  one to1 correspondence between the output and the state。

 which is the counter that goes up and the number it is in the counter goes up。

So the input port are P up and down with types V up V down present or absent and the output port Q is count where the type V count is a natural number for0 to M。

 Now the sequence of。Us can be present absent， present absent。

 present absent and S down can be this sequence and the count according to these sequences of the two signals at the input is absent absent 10。

1 and so on so this is a output that is produced by the sequence of inputs that I show in the line before so now type refiner。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_5.png)

An example of why should I care about type refinefin。

 so I have a garage counter that has a display that can take up to 99 numbers up to 99 so it counts 1。

2，3 up to 99 and I have another garage counter that has 90 spaces。Now， since they呃。

Space of the output in the natural numbers is contained in the space of natural numbers of the one before we can say the type or fine。

So every time I。I have this typerify it。 I know that I can substitute M2 for M1， except。

That is not always okay to replace M1 with M2。 When is that。Can you give me an example？胜ful系。

Right exactly， so if I have 92 cars then I'm dead， right， 92 spaces， not cars，92 spaces。

 and I have a machine that goes up to 90 then what to do I do when I have 91 cars right so my counter。

😊，Doesn't give me the right answer， and so I cannot use that counter to represent the behavior of the system。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_7.png)

The counter machine above like V1 up to M can be indeed be replaced by this we already saw that right so it's a compacted version of the finite state machines above and by the way this machine is completely totally absolutely equivalent to the one above。

 the only thing is that the input and the outputs are defined in different spaces so that the state doesn't correspond anymore。

😊，To the output。 So it's a more compact machine。 But if you look at the sequences of input and output。

 this is exactly we say。 it doesn't change。 So we respect to input and outputs where we say。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_9.png)

So if we look at again， the simpler model， which is your robot model and we say when is it okay to replace one machine with the other。

 we say that equivalence in general is language refinement for deterministic machine。

 and for nondeterministic machine is a concept of simulation。

 so that when it's safe to replace one with the other。But remember， simulation is one direction。

Language refinement also is one direction， but language equivalentvalence is exactly， you know。

 if if a is a language equivalent to B， when I can interchange both of them doesn't matter I can take A or I can take B is the same。

 right。If instead is a refinement， I cannot do that， right。

 I can substitute the richer machine with the turkey air machine， but not vice vera。

And in case you have a nondeterministic machine， when the issue is that one nondeterministic machine may have many more behaviors when another machine according to a choice that you make。

 so I can match whatever it does， but even though it looks like we can produce the same sequences。

 if I move first it may not be able to follow， if it moves first I can always follow but not vice first and that's the reason why you say simulation and but is not the same。

 absolutely not the same as the notion of language equivalent。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_11.png)

Now， how are we going to distinguish this thing。 We are going to talk about execution trait。 Now。

 behavior， we say before is something that represent the what。

Is the impact of this machine on the environment。And so the execution trace means I have a sequence of inputs and a corresponding sequence of outputs。

 this we call is a trace， right， So I give you a specific。

Sequence and you get specific pairs of input state and and output and this one is a trace right so the trace not only contains the information about the input and the output contains also the information about this state so it not only says okay I give out this thing but iss also saying well I'm going from V step to V step to V step and so on so it contains more information meant what we saw about the pair input output pair because now for example I can distinguish between the response of Vto guys right because now I have the states in it and so it was in the staing state you are in a different state so the sequence of state is different so that is。

The reason why traces you know are。Include another concept。On the language。

 but simply when input and the outputs。

![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_13.png)

So a behavior of the。Of a state machine is actually the set of all possible traces。

 right so everything that the machine can do， that's the behavior of the machine。😊，O。So。Now。

 language refinement， then you say that language I of state machine M is a set of old behaviors。

 So everything that the machine can do all the sequences of input and apps they can produce that is。

What the language of a machine is by way， if any of you has done a little of language theory。

 I don't know how many of you in computer science have done that。

 but you know that there are certain languages that are accepted by a finite state machine。

And so what does that mean， acceptance or hell which means that it can be produced any regular。😊。

Be here I have to say sequence of statements can be produced by a finite state machine right so it's a very well defined language is when this thing is true and it's called regular languages a nice language。

嗯。All right， so the language we say is a set of all possible behaviors for type equivalent in state machine M1 and M2 M2 is a language refinement of M1 if the language of N2 is containing the language of M1 which means that I have fewer behaviors than the other guy and my behaviors are in containing the behaviors of a bigger guy。

And so that is a refinement， so I have less behaviors but all my behaviors are contained the previous one。

 so M2 can replace M1 if it's observable IO behavior is a subset of F of M1。

 why do we talk about observable behaviors because if I care about what the finite state machine does to the environment。

 I have to look at what is observable， what comes out of that finite state machine。

 so whatever is not observable， whatever it doesn't come out。I don't know， so I don't care， you know。

 it doesn't matter， you know， with respect to what the system does。 now。

 if some of you has done some continuous stuff， right， continuous system theory。

They know about this observability and controltlability concept now that is related to what I'm talking about here。

 so a system， x dot equal to f of x and u and y equal to whatever G of x and U when we say that the thing is observable if for every transition of this continuous system。

 I can see I can I have a complete observation of the state and of the input that has produced that particular output。

So in that case， I know that nothing goes on inside the machine that I cannot see。😡。

Now why should I care if there is something inside the machine and I can see it if I can see it doesn't matter in principle。

 yes， it doesn't matter， but there may be certain things that you have not contained in your model that may completely kill the system so for example when an unobservable part of your system can be unstable so a thing blows up right and you don't see it but it's blowing up right that's not good yes。

Right。behi啫。Whi word in M1 but are not right but this is again。

 I mean you can replace it in the sense that whatever the new system does was contained the original system。

 so if youre carrying that is a specification then you are refining the specification according to the refinement relation then you can substitute it but if you are interested in all the behavior N1 then of course not。

So and remember that this also makes sense especially in the nondeterministic case when the nondeterminism in the specification。

 it means you don't give a damn and that is the reason why we define this way and remember again that everything that I don't say is very good so one of the thing that we did a lot in the old times in logic design was to back the designers。

 tell us what you don't。Care about because every every fit time you say this I don't give a damn is great because I can play with that thing。

 right I can decide what I want to do in this thing。

 right and so I can play in such a way that I reduce the size of a system。

 make it faster and whatever， because I have weird behaviors。

 but who cares this behavior don't matter。😊，And so the refinement contains only the baby。

 but I throw away all the dirty water， right so this is the key。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_15.png)

Okay。So we said before the language equivalent is not enough。In general， for nondemintic machines。

Only in that case because otherwise its perfectly fine。

 so how so how so so we have this nice machine on the left which is deterministic and it says that if x is present when it produce a0 moves to B。

 then if x counts again I get1 or I get 0 so if x is present I get to1 or I get to0 in these sequences now this other machine it says that under a particular input。

 I can go to two states right so F or H and F can only produce a1 and H can only produce a0。Okay。

So now this one， if you put any kind of sequences or inputs， you get the same outputs。

 doesn't matter。 I mean， it's just absolutely same。Yeah。

What can be a problem right so let's look at the behavior of this machine。

 so suppose that I take A and I going to B and that's fine。

 and I'm going to go in the second machine。 I move from E to F is a possible behavior。Now。

 the next behavior of my machine M1 is going to take the branch and is going to D， right。

 outputting a 0。Now， in the machine to vary， if I am in F， can I produce a0， no？So。

They are equivalent， but they are not。And so how so because of an undedeterminism right so I took direction in one case。

 one direction， the other case I took other direction。

Now if I revert the choices if one machine is allowed to choose first。

 then I can show that I can match the behavior， if I revert the order of choice。

 I cannot get it and so this means that one simulates the order but not vice certain and this is only true in the case of nondetermining machine because of this choices that I have and the large set of behaviors that I have as well。

 so however， even though these machines have exactly the same input output with behavior which a context which M1 is not available to replace it for n2 which is the one that I just told you about。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_17.png)

So suppose that M1 is a specification。 So everything thing it does is okay。

 So if I replace M1 with N2， I am O because any move。That M2 can make is O， but not vice versa。

As we just did an example for conversely， suppose that M2 is a specification。

 everything it does is okay， but its not okay to replace it with M1 because in state B and1 is always capable of making a move that M2 cannot match。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_19.png)

诶。And so on one way is okay， the other way I can， so it simulates in this way is not by simulation。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_21.png)

It simulates only one direction。O。Now， so is in some senses， we are talking about the matching game。

 right， So you make the move I match， you make the move I match。

 you can So any anything that you fud me， I have an answer，😊。

So that's a game that we are going to play。 And the simulation relation is that。

How to say vector relation that establishes what I should put in correspondence。

To make sure that these two machines can produce the same output no matter what I throw it then。

 so have S1 is ABCD S2 is the state space of the machine M2 is EFGH。

 not is that S2 as one state more but they still are output equivalent so it doesn't matter if the states are same number or not。

 I can get a language equivalentvalence even if I have different。Set of state。 Now。

 I call a simulation relation A pairs， the set of pairs of state S 2 cross  one。

 And let's see how this set is built。 Okay， so I start with DNA， right， So that's my。First。

Couple move。 So on the machine name1， Im in a machine name 2， I am in E。

 So the beginning of the game， lets the game begin so。Now， this pairing E A of initial condition。

 I'm going to collect， right， iss a pair  one stateiness，1，1 pairinginess to put it together。

Now then I can decide where I want to go as an next step so M2 suppose that M2 moves first is a game。

 so M2 moves first。

![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_23.png)

And it goes to F。Now， M1 cannot go back to B。 So the next quote unquote pair in the simulation relation is going to be FB is where I end up in the two machines。

 I end up in here and end up in。Now， first possibility。

 the second possibility instead is that I go in B M1， but M2 goes in H。 And so this is also possible。

Choices。 So it's another potential element of a simulation relation in the sense that that describes a different choice。

For very second machine。 Okay， so I keep on building Now， next step。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_25.png)

Now， the next step I'm going to。C and G， because x1， x1。 So from F I go to G。 So C G is O。

 And then from B， I go to D， then from H， I go to I。 So B pairs G， C and I D。

Are other elements of a simulation relation。 So this is all pairing that I can imagine， right。

 So it's always possible， joy。😊，Evolution of the two machines。Now。

 that set of pairing of states is called simulation relation。 Now。

 why should I care about simulation relation because。

The s existence of such a set is I can analyze and guarantees me that one machine can simulate the。

 Okay， so that is the algorithmic side of the other thing。 So since M1 simulate M2， M2 refine M1。

 M2 can replace M1， everything M1 is okay。 So is M2。

And so we say that this pairing of EAFDHPGC IDD is the simulation relation for the of machines where M2 the secondary machine is a machine that I am going to replace M1 with。

 so it goes in this direction so a simulation relation exists because I always like M1 to make this first choice and then M2 follows。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_27.png)

Now formal definition of simulation given M1， which is state the set of state as1。

 the set of input i1， the set of output to01 and U1 is the next state relation Why do I say next state relation not function。

Any idea？But why is not a function？Exactly， because this is a non deterministic machine。😊。

So the definition of function says that for a input value x， I have one and only one。Autto， right。

 That's a function。 right， The definition of function。 The relation is that I have one input。

 I can have multiple output。And the element of a then is that input with this output is one element。

 then this input with this output second element， this input with this output。

 third element okay so as I say all right， so that is the reason why we indicate with U1 and not with。

 for example， F1 which will be a function but given a set of inputs and a given an input a given a state gives me the next state and the output。

So it's a relation。 So it can be multiple。All right， so we say that M2 is a type refinement of M1。

 we know that it has to be otherwise doesn't even make sense to ask the question if M1 simulates M2。

If there is a relation which is of course a subset of S to cross S1 where S20 and S10 of initial states。

 of course， belong to this set because remember that the simulation relation is a collection of the joint movement of the machine so I have to start from somewhere so where I start is the initial condition of initial condition has to belong to s relation。

So for all the pairers that are belonging to the simulation relation S。

 the following conditionalals for all the input in I2。And for all states。

 S2 and output 2 that belong to the reaction set of S 2 and I1。

 there must exist a pair of state and output that belongs to an x state relation， such that。

The pair S1 and S2 S prime 1 and S prime2 belong to the， and the output set。

Of machine 2 is containing the output set of machine  one。

 And that is the reason why one simulates the other。 If it is equal， when they are。Equivalent。

 they are bi similarim， as we say， but in this particular case， they are not。

 so because O2 is must be contained in a one， so it may not be that way。

 So this essentially says that everything that the machine one does when S2 follows。

And actually it over that everything that M2 does is contained in everything that M1 can do because of this relation。

 So any any evolution of M1 M2 is contained in M1。

![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_29.png)

So as we say before， a stronger notion of simulation is by simulation。

And by simulation means if machine M2 simulates M1， M1 simulates M2。 So by simulation。

So which means that I can since we are playing a game right， so Im player number one。

 is player number two， then the by simulation means I move first e follows。

But I can allow him to always move first and I follow。Okay， so it's by simulation。Now。

 is by simulation the same as the greenness is not。 And we'll see later on， right。

 because this thing that we discuss is that I always move first。

 I' am the master or he always moves first， is the master。 What if。Here's a master for one step。

 and I'm the master for the next step。Okay， but that is tricky。 and in fact。

 you can have a bisimilar machine and yet not be the same as the。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_31.png)

That doesn't produce the kind of things that we want so it's possible to have2 machines that simulate each other that are not by similarim so this one is M1 simulates M2 and vice versa but they are not by similar in the sense that if I take this in in how to say interleaved kind of game then I can get different behavior so given M1 and M2 then we say that M1 is by similar to n2 if there exists a relation simulation relation where we start from an initial state S20 and S10 and for all pairs in S following conditionalal for all I and s prime202 in u2 or S2 I there exists a。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_33.png)

Per of states and outputs that belongs to the next state function of S1 and A so that the pair。

 the next state pair belongs to S and O2 is exactly identical to O1。 Okay， so that is the difference。

 right， we add before the O2 was contained in01。And vice versa for allli in I and S prime 1 belonging to this there exists an S prime 2 or2 in this such that S prime 2 and S prime 1 belong to s and the two output set are equivalent so I can revert right and if I can revert nothing happens。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_35.png)

O， now simulation in container。 So if M1 simulates them to。

 then Im sure that the output sequence is the same。Now。

 if I have a machine in such a way that they output put。Is the same for both machine。

 I cannot say that there。In simulation relation。 so and this is due to the fact that when I move in the finite state machine。

 the sequence of output， don't tell the entire story。

 Also what happens to a state is matters sometimes， and that is captured by simulation。

 but is not captured by the output equivalent。Is the pairing of the states that matters， right。

 So and in some sense， is， is the same thing as。If I put the famous curtain， right。

The output equivalence。I don't care what this guy does， right if a machine can compute， you know。

 in a horrible space can be too gazillion machine。 I don't see。 And the human answer like this。

 the machine takes time， status and whatever。 right So that is the language equivalentvalence。

 So they do exactly the same thing。 Now this simulation concept is that they are doing the same sequence。

 So it's that as if the machine is going through the same step that a human mind will follow。

So it's much stronger right because for example in chess I don't know how many of you followed a big blue game against the Kp right great champion of chess right so he always won except all of a sudden he never won anymore right it couldn't win anymore Now if you look at the process carps was following was a very reason kind based on experience based on patterns and all of that the machine was doing all of that plus right Plaa was doing exhaustive check of moves right。

And so， it was beating。So， it's different。Sequence of thoughts。

 different approach to solving a problem， so when if we say that they always come to you know if we change the white with the black。

 you always produce the same thing we can say that the two guys are producing the same output but not the same sequence the way in which they arrive to the conclusion is different and so the simulation aspect of things is that I care about how do I get to the solution and not only the fact that I have the same input output。



![](img/4b8d0c1e7ad65c66c56322cb3a1778ab_37.png)

So in summary， what have we done。 So we have defined type refinement。

 And so we say attempt2 can replace n1 without provoking a clash of the input and output spaces。

 Well， that's really the basic stuff。 I mean， iss really， I mean， it would be really。

Stupid what unquote to to to define two machines and implementation and that are not。Type refinement。

 one of each other。 Now， the interesting thing is that。Believe it or not。

 but a lot of mistakes are done on this way， so if you want to look around in the domain of big designs and what went wrong its on。

 sometimes people mess up because they mess up the type。

There is a particular casing point of the large design that will remain unnamed and costed about $200 million in which you know what they did is that they had the connection scheme right where the various components should be connected and they are connected to a st pin。

And guess what they did。They inverted two wires。Dft， like this。So if you had the type checking。

 you would immediately see it。 Oh my God， I inverted the wires， They didn't see it。

And so to find that that was the case took gazillion hours because it's a stupid mistake， right？

And so sometimes a stupid mistake is much more difficult to find than a very complex mistake。

 a simple check will find the stupid mistake。 So don't think I say this type of refine is totally stupid。

 Yes， it's totally stupid， except when a man is involved and he had too much to drink the night before and witch is very reps sos。

Or he was thinking about something else。 Okay， and two is a language refinement of them。 One。

 we say this when they。Whatever M1 can do， whatever M2 can do when M1 follows now M2 is a simulation refinement of M1 if at every reaction M2 can only produce outputs that M1 can produce。

 but M1 could do more。N2 is byimilar to M1 is that every transition either machine can produce all the outputs but the other can produce。

 so the two outputs are exactly the same。The sequence is exactly we same。

 but there is also remember this equival also all the steps。Where the two machine are taken。

 So is the output， I have to match the。Tate in which they are produced。诶。

So in all cases we say that M1 is valid in a system and so is M2 so this is the notion of refinement。

 we're all the meaning of valid what is valid， what we believe it's valid varies so we also say that T2 implement M1 in the sense that again the sequence of refinements is always followed when you do a design top down right so you have a specification go refinement refine refine refine refine。

You at the boat okay so we are way ahead of our time， so we have about 20 minutes of free time。

 which is not bad， I see someone likes that。And so I'll open to questions for another five minutes。

 and then I'll let you go and have a nice lunch， yes。

We have two machines produce periodic output wave both of them one machine produced a signine wave shifted by5。

If you don't associate any time stamp， then the sequence of values produced by both the machines are same language equivalent。

 right。Now， suppose we also associate timests to these Yeah when they're not they're not exactly so but if you associate with times stamps。

 it depends if you want to associate it in the sense that you want to produce a output。

The value associated with the time in which the value is produced。

 then we are not language equivalent。But if I keep hidden the time tag and I look at the transition relation。

 then I may be able to see that they are not the same machine。Because the state。

 it depends how I encode the state， yes。Excusing。Now we have to say again。

Yeah you have to start the talking about yeah they are not equivalents right exactly。

 but the point is that input， I mean output equivalentvalence yes because the same sequence is produced and the first step if at the beginning right is does nothing when it's a staering and so the sequence is the same。

Because it doesn't have the notion of T， right， So the only thing。

 and this is the doesn't have the notion of which states I went for to produce at that。

So as a matter of how you model， in fact， I say if you attach the tag of the reaction， then。

 of course， we are not equivalent。But if I look only at the output sequence， I maybe have the same。

 So suppose that the input is just tick tick tick tick is advancing by one and the first step is a stuttering step in machine2 then is they say。

Right。Because the tag doesn't matter。 right， It's a sequence that matters。And so we say there。

 that's a different story。No， because if you take as a specification。

 the input output behavior rate will produce the same。It。

 it depends on what you define to be the specification。 So if you say so is that。

You are making my points right you have to be careful about what you define。 So your thing is right。

 is fingers right， It depends what you define equivalent of what you expose， right。😊，right。

that you can compare how much。How much different are the two machines yes。

 but it's complicated right so for example， in in continuous time when you have this kind of things right so for example hybrid systems then there is a score equivalentvalence which says that score matrix it says that for example。

 two machines are quote unquote related or doing the same or whatever if the output you see is within a certain ball in time right。

😊，So if you have a reaction which is delayed or anticipated。

 it doesn't matter as long as it stays within a particular board and let's called thecarho matrix。

 So you can say， for example， the two hybrid systems Skype。Converge into a particular behavior。

In the Scho matrix it means that they are delayed， They can be delayed。

But where is a metric and what is a matrix is a way of saying what is equivalent。

And so its quite interesting to find out that， for example L2 matrix right L2 matrix is used to find out when for example。

 if something converges L2 means that the square root of the square of the components in the space that is a metric when size of the vector right and so if the difference between this two values go to0 when you say that you are converging in L2 norm is where another norm that you can define convergence yes is l infinity L infinity means that max difference goes to0 which is different when L2 also because L infinity is non continuous L2 is continuous and so on right so one gaziion different way of measuring things and so which is this point everything that you define to be your measure there is a definitions and where our algorithms that are associated to a metric。

いいです。And sometimes actually， people play the following game in the sense that they want to prove something and they will invent。

A particular matrix or whatever that they need to prove what we need to prove on right。

 So sometimes a matrix is invented after the fact。 right So I say I believe that we to do the same。

 but they are different。 So I have to invent a measure in such a way this two whatever same。

 And this all this stuff is the same right It's exactly the same。 you say， by God。 you know。

 this one is the same as that。 So but I have to find a matrix with telling me that。

And so you invent the matric later on and the matrixric， as we say before。

 can be many different things。 So for example， the equivalentvalence you know this met and up and up。

Any other question。By the way， this is rather advanced stuff， right， so you will not。

Find too much in your in your midterm or anything like that on this topic。 but for graduate students。

 this is important right So in fact， one of my my things。

 what I'mqu is that in the future we will be defining an additional course where more of the advanced stuff is going to go and some the graduate students will only take that and will not take this class because sometimes graduate students may be bored to death and sometimes the undergraduate students say。

 my God what is this crap that they are throwing at us not good either way so but if the undergraduate students have complaints about I don't understand a thing。

 try to ask I mean not you know I'll try to to make it as intuitive as possible walking around or jumping or doing something or picking up on the guys in the class so don't be afraid。

I'm not known to other eaten students who are making horrible questions。Okay。

 any other question come in？Okay， so class dismissed。

