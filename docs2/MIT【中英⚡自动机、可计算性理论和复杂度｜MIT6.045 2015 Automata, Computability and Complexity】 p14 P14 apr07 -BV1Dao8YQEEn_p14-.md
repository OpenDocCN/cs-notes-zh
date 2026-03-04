# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p14 P14 apr07 -BV1Dao8YQEEn_p14-

嗯。Oh。Is there any chance that you could go and collllate the PSs？Yeah， and bring them back。

 They're all graded。 Yeah， exactly。 there are all lots out my office。 All right， great， wonderful。

 Thank you so much， Sa。 and just bring them back， yeah。😊，Okay。All right。Welcome back。

 I hope you had a nice holiday weekend so you I assume you got the email that the midterms are all graded。

 the average was about 67 by the standards of past year is actually pretty good，You know the。

You know we can't hand them back yet because there are a few students who still need to take them。

 but you know we can hand them back on Thursday and also if you want to come by for office hours today you know we can talk about your midterm if you want but so we'll have those back for you on Thursday PSet3 is all graded Saed is just going right now to collate them so hopefully by the end of lecture we will have those back for you and PSet 4 is out and because we were late getting it out we've given you almost an extra week to do it but you know you should get an early start because then PSet5 we'll also be out in a week or so all right so I want to continue with NP completeness which was the last thing that we were talking about before the midterm。

You know very， very important， very， very central topic in the course。

 so what we saw a week ago was sort of our first examples of NP complete problems so you know you know you can problems can be NP complete you know under touring reductions or better yet you know like a stricter notion is under mapping or many one reductions okay and you almost all the examples that you'll ever see or certainly that we'll see in this course of NP completeness reductions actually do give NP completeness under mapping reductions okay so you know and that was certainly the case for the reductions that we saw a week ago。

😊，So what we saw is you know we started out with like a problem that was NPp complete essentially just by the definition。

 which you called the Du problem， which is basically is there an input that causes such and such a touring machine to accept after a polynomial number of steps and then the main thing that this famous cooklen theorem does is that it reduces that dull problem to circuit set okay so it shows that circuits can simulate the actions of touring machines。

 okay that actually you know we can then you know if I give you a description of that touring machine。

 I tell you how many tape squares it can access how long it's supposed to run for。

 I can then in polynomial time I can output a circuit you know which will of course just be polynomly larger than。

the the input instance that you were given and there will be an input that causes the circuit to accept if and only if there was an input that caused that touring machine to accept right so that that's what we mean by a mapping reduction okay and we do that just by you know using and and ore and knot gates to just simulate each step of the touring machines you know time evolution so。

😊，You know so it's you know the details of the proof are kind of boring right it's really just you like you know。

 well it's almost like engineering a micro chip or something right you have to you use and and or in not gates you to simulate you the computational logic you want the possible actions that the touring machine can take okay then you know once once you have the circuit set is NP complete。

 you know then you're sort of cooking with gas okay because you circuit set is you know a problem that you know involving a whole bunch of gates you know you're given a circuit。

 you know of and and or a knot gates， okay each and and or gate just takes two inputs。

 each knot gate just takes one input and so gates are a very very local in some sense each gate is just sort of relating you know one or two input。

to one output okay and so now this has much more the feel of like a combinatorial optimization problem right and we can be you know more explicit about that and one way to do that is that we can show that actually once we know that circuit set is NP complete then it follows that even threeat is NP complete okay threeat you know you could think of as just like a very。

 very special case of circuit set where。😊，WhereWe're restricted to circuits。That have a very。

 very flat structure。Where the circuit has to be an end of a whole bunch of oars。

And each or can only be of three things， which can either be variables or input variables or the negations of input variables。

Okay， so。So basically， you know， to get from circuit set to three set。

 we give a general procedure for flattening out any circuit， okay。

 and then you know and that's kind of an amazing thing if you think about it because。😊，You know。

 we don't expect that like in the ordinary deterministic world that you could just take any circuit and flatten it out okay and yet in the nondeterministic world。

 the world of NP you can do that okay and the reason why you can do it is that like you can always just introduce more variables you can always introduce more variables that you know that the witness string you know you then demand has to provide for you so you can sort of force you know the witness string to do all the real work for you okay you know in order to make it easier for yourself to verify okay it's kind of like you know if you were。

You know， if you wanted to know make it really， really easy for yourself to check someone else's work right you would just tell them you know to say every step explicitly right and you would just you know if you were like if you were a boss really you had the power right you would you know just tell the you know tell the person proving the thing for you to just you know just really be explicit about everything just really make it as easy as possible for me to to check your work okay and then you know and then you you're the bus so they have to do it okay so that's sort of what we do here so what we'll do is we'll say we're going to just introduce a whole bunch of auxiliary variables so like one for each gate so the and gate。

 you know the output of the an gate I'll call y the output of this or gate I'll call Z the output of this not gate。

 I'll call W。And the output of this end gate if someone give me a name for it， I'm。Oh all right sure。

 so all right， and now you know I just have a bunch of constraints for each one relating at most three of these variables。

 so for example I've got an end of x1 so so sorry I know that y has to be the end of x1 and x2 okay but that you know is just a whole bunch of constraints relating x1 x2 and y okay。

 so like I can say if you know it cannot be the case that x1 is true。

 x2 is true and y is false and there are three other such constraints that I have to make so。😊。

So I can say it cannot be the case that those are all， let's see。

So something like that right and you know and then for each of the other possibilities it cannot be the case that x1 is false。

 x2 is false and y is true okay， so I could have another constraint that encodes that okay that will be you know a different combination of of negations and nonnegations over here okay so okay。

 and then you know I'll need some constraints。😊，That relate y to z okay because you know sorry sorry that relate I'm sorry that relate yz and x3 okay that basically say that z has to be the or of y with x3 okay so that I can encode using four constraints。

 you know each one related for disjunctions， each one relating z y and x3 okay and then。

How many constraints do I need we weighting W and x4？Two， yeah， and he says you know。

 it cannot be the case that x4 and w are both false and it also cannot be the case that x4 and W are both true okay。

 and then you know， and then I'll need four constraints for eating these three variables and finally I will need a constraint saying that O is true。

 and then this will be a three sad instance that， is satisifiable if and only if my original circuit sad instance was。

😊，Okay。Okay， so then。Yeah and then once we know that threeat is NP complete then it's sort of like the floodgates are open and you know we can just you know prove you know a zillion other things or NP complete by just reducing threeat to them okay because threeat is just a very。

 very convenient， very you know nicely structured problem to use as a starting point for reductions okay and historically that's exactly what happened after Cook in 1971 you know wrote his paper proving that3at is NP complete in 1972 CAp had a paper proving that 21 other problems were NP complete okay and yeah。

Yes， yes， yeah and CAp only needed mapping reductions you know and all example。

 I think that like Cook you know used like touring reductions which which are in NP completeness are also called cook reductions but you know just because he didn't really care about the distinction between the two but then CAp notice that hey you you can actually get by with mapping reductions in all these cases and since then it's turned out to be the case that almost always you only need a mapping reduction occasionally you you need a touring reduction okay。

😊，But。So。So okay， you know and so CAp's you know list of 21 NP complete problems actually includes you know a lot of the ones that you've heard of you know click traveling salesman Hamilton cycle three coloring right you know and and I believe that in recitation on Friday you probably saw you know some example of an NP completeness reduction I left you know which one to do to the discretion of your Ts but so I'm just going to do one all right because you know I get bored of this kind of thing pretty quickly but I'm going to do one NP completeness reduction just you know to give you an idea for how these things go you know this is something that might actually you know you know I promised you that everything in this course would be useless but NP complete problems you know you may actually deal with some point。

Career so it's good to know how to recognize one， if you come across one， what to do about it。

 okay we'll talk a little bit about that。All right。😊，So what's the three coloring problem？Well。

 it's that you know you're given a graph let's just be you know abstract about it。

 okay say you know we're given a graph， you know we won't require that it be a planer graph。

 it could be you know the countries can be connected together in you any which way you like。So。呃。

What it could have。呃。Okay， and you know our goal is to color each country red。

 green or blue in such a way that no two neighboring countries are colored the same。

 I'm not actually sure if this graph is three colorable。Well， we can see so so far， so good。

There's nothing between that green and that green all right now this has to be red all right I'm in trouble yeah。

 so if this graph is not three colorable all right。

 so that's fine that you know we have an answer for our instance the answer is no okay so。😊。

You know so this problem certainly has an NP complete kind of feel to it。

 you know a bunch of constraints got to satisfy them all or you know not there could be you know times when it's not obvious which decision you're going to make you know but then it could have consequences further down the line so you know has the feel of a kind of puzzle but how do we actually prove that it's NP complete well all right all right so first of all you know as usual quite easy to see that this problem is in NP right the witness is just the coloring okay so the problem is to prove that this problem is NP hard right so to prove it's NP hard we need to take some other problem that's already known to be NP hard and reduce it to this one all right so which problem should we choose anyway。

哇。Yeah， we can you know actually for this one we could just go directly from circuit set that would work fine or we can go from3at okay either way。

 you know it won't actually matter that much okay you know' let's what the hell let's go from circuit set okay so now what we need to do is something else show how to encode the logic of and or a not gates into the three coloring problem right so we need to construct maps you know so given a circuit you know we need to construct a map that's going to be threecolorable if and only if that circuit was satisifiable。

Okay。Okay， so this is always the trick with reductions。

 so you need to build some kind of gadget in your new problem that encodes the logic of the problem that you're reducing from okay so that the two things are isomorphic all right。

 so how are we going to do that？Well， the first step is just to establish what's called a palette okay and the issue was that the three coloring problem has a symmetry to it。

 okay theres you like if we had any valid solution so the number of solutions to a three coloring instance must always be divisible by what anyone。

Ha。by three， yeah， but even better than that。It has to be divisible by6 okay because anytime you have a solution you could permute the roles of red green and blue well okay okay I guess you could have like you could have like just one vertex and then you and then there's only three solutions all right so you're right you're right okay if you've got at least two vertices then the number of solutions to a three colororing instance is always divisible by6 because you can always just permute the roles of red green and blue you can always just change your color scheme and that will give you another valid solution three factorial is equal to6 so we want to you know and circuitat does not have that symmetry there's not really you know so so the first thing that we want to do is break the symmetry somehow and that's what we're going to do with this palette。

😊，Okay， so we're going to have just。Three countries whose ugly role in the world is to break symmetry and the colors。

 know we formerly called them red， green， and blue， but I actually want to now call the colors truee。

 false and neutral。😊，Okay， same difference。嗯。So clearly these have to be different colors。

 so I'm just going to call them true， false and neutral。

What's nice is that now I can have some other country and just connect it up to the neutral country。

 and then the color of this country will have to be what？True or false yeah。

 so now I have a boolean variable okay so now I've got a variable you know， could call it like x1。

 for example， that could you know has to be either true or false right I could have a whole bunch of these。

😊，Let's say one for every input to my circuit for example。

 okay and now you know what I need to show is that I can simulate and or a knot gates you know by just connecting countries to each other in an appropriate way so you know so this is you know it's actually kind of fun right it's like you know now now it's a puzzle that we have to solve okay so let's do the easy part first how can we implement a knot gate within three coloring。

😊，So let's say that I want a country whose color has to be the knot of x1。How could I do that？Yeah。啊。

Excellent。Exactly。There we go。So now this。Cory， it cannot have the same color as x1。

 and it cannot be colored neutral either， so it has to be colored not X1。

Okay so now I've got a knot gate all right， so the trickier part is to construct an and gate okay once I've got an and gate and a knot gate。

 then I'm done okay because by De Morgangan's law， I can then use those to construct an or gate and then I'm cooking we know that and and a knot is a universal set of Boolean gates。

😊，But we saw that all right， so how do we get our and gate？

I hope I'm going to have enough room on the board for this。呃。All right。

 so I won a con so now I've got these。These x and y countries and I need a country whose color is equal to x and y。

 so it's going to be true if and only if x and y are both colored true。

 and otherwise it's going to be colored false。So let me just show you the construction， okay。

 you know takes you know it takes some fidling around in order to find something that works。

 you know， and that's very typical of NP completeness reductions All right。

 but let me show you something and then let's just argue that it works。😊，All right。

So I'm going to have a region like this。This is going to be。

My my country that I claim is colored x and y all right I'm going to connect it here。

 connect it here let's just this is this is and then connect this to neutral to say that this one has to be either true or false now this is going to not quite work yet but let' just let's just look at let's just look at what we have so far and see what we've got okay so。

You know well they therere。There are four possibilities we have to try out right true， true， false。

 false， false， true and true false， you know， but false true and true false are basically the same by symmetry。

 so it's really just three possibilities All right。

 so let's first suppose that these are both true Okay， then what do these have to be anyone？

F and neutral。 Yeah， neither can be true， and they have to be different from each other。

 So one has to be false。 The other has to be neutral。 So then what does this have to be。True， okay。

 so so far our an gate seems to be working pretty well。😊，RightIf these are both true。

 it forces that to be true。 All right， well now suppose that one of these is false then。

Then what do we need to have over here？Well， you know what let's first suppose that these are both false。

 okay， suppose they're both false， then what do we need over here？True and neutral。

And so then what does this have to be？False， all right， good。 So so far it work you know。

 in two of the cases， it works really well。 All right， but now。😊，Let's suppose。

That this is true and this is false， okay， then we need this guy to be false。

 right and have we forced that？No， what， why not？False yeah。

 let's say I could have false neutral and then true Y。

 so I have not yet succeeded in building an angate right this you know。

 as far as you know like as far as this thing he is concerned。

 it might as well be an orgate also right。All right。

 so I need to do a little bit more work to deal with this case when one of them is true and the other one is false。

All right， so now I'm going to build some auxiliary crud that's just for dealing with that。All right。

 so here's what I'm going to do， I'm going to have some side flanking countries so this one down here is going to connect to true and to this one。

This one here is going to connect to this and it's also going to connect to false。

And it's going to connect here。Okay， then on the top。

We're going to have one here that's going to connect to true。And to this。

 and we're going to have one here that's going to connect to this。

 and it's also going to connect to false。呃。Okay， and it's going to connect here。Okay。All right。

 so now we've got these side flanks， okay， so now let's see what happens All right。

 so now this is true， this is false， well， okay， so what does this have to be down here？😊，Neutral。

Okay， and then how about this， what does this have to be？True。Ah， so look at that。

 we have forced this guy to be false。Okay， and you know， and just completely symmetrically。

 the flanks on the top are going to do the same thing。 right， If this is false。

 then they're going to。Force this to be false。 Okay， so they're going to break the symmetry。 right。

 if one of these is true and the other one is false。

 then they're going to force this thing to be false。 Okay， so that's how we build our end gate。

So we've gone through all the cases， and you can do it again at your leisure if you want and in each case。

This is going to be the end okay and then you know once we have an an gate and a knot gate then we can string them together you know as we like。

 so so now if I wanted the knot of x and y， then I would just put another one here and I would connect this up to neutral。

😊，Right and so forth， okay， and then at the very end。

 what will be the last thing that I need to do in this construction？😊，So you know。

 I've got my final output country。Then what does the output country have to be connected to Yes。

 yeah， the final output country has to be connected actually both to neutral and to false。Okay。

 in order to say that know the output of my circuit has to be true。 and then you know。

 then I just hand you the graph and I just ask is that graph three colorable。

 and what we'll have by construction is that it is three colorable if and only if original your original circuit set instance was satisifiable？

So we've encoded the logic of a circuit into the three coloring problem and therefore the three coloring problem is NP hard and in fact NP complete okay you know the one final thing that you'd want to check if when you're doing this is that the map。

 the new instance that you've produced is only polynomly larger than the original instance and furthermore whatever algorithm you had to reduce the one problem to the other ran in polynomial time。

😊，Okay those are formal requirements， it's pretty obvious that they're satisfied in this case right fact not only is it a polynomial time algorithm。

 it's a linear time algorithm which just basically just says just go through and translate you know translate the thing gate by gateit right and that's very typical with NP completeness reductions right that usually you know。

 often they're just very， very straightforward translations one thing so it's like you know they're not only like they're not only polynomial time reductions。

 they're like extremely polynomial time。😊，Okay， so。So all right， good， so that was our example。

 okay but now。😊，Ls you think that just you know everything is NP complete right。

 you know it's interesting to see how if we just made slight variations to the problems that we were talking about。

 then they're not NP complete or you know in less P equals NP anyway right you know then we get problems that are solvable in P so。

😊，Okay， so I think we already discussed why2 set is in P， right， I'm sorry， we already discussed。

 I'm sorry。 we already discussed why two coloring is in P， right， If I just asked you， you know。

 is this map too colorable or not， Well， then， you know， you just。

You just color your first country you know in a way like let's say red or blue and once you've done that。

 you've broken the symmetry， you know that all of you know that country's neighbors have to be colored blue no matter what and you know that all of the neighbors of those countries have to be colored red no matter what and then you can just keep going on coloring you using breadths first search。

 let's say and see if you ever hit a contradiction meaning you do you ever find you a country that has to be both red and blue okay and if you do then your map was not threecolorable and not if you don't then you have twocolored your map so in some sense what prevents two coloring from being NP complete is you never once you just make this initial decision of red versus blue then like you have no。

Further decisions to make right and that you know in particular。

 that prevents us from encoding an end gate into the two coloring problem Okay。

 so you know you can check that it prevents the NP completeness reduction from working。

 but then it also gives us a polynomial time algorithm to just solve the damnm problem Okay so。😊。

So so there's something， you know and actually this that' is pretty frequently the case that three is like a magic number for NP completeness。

 not always， but but very often you know as soon as you have three of something you you have like then you start having choices that you can make and choice is a burden because you choice is what gives rise to a combinatorial explosion of possibilities and then you know we can start trying to encode you know circuits into your problem and then before it long your problem is NP complete okay let's see another example of that。

😊，So。So let's look at twoat rather than three sat， Okay so I claim that twoat is actually in P。Okay。

 you know， that's a little bit less obvious than it is for two coloring。😊。

But we can first check that the reduction that proved that threeSAT is NP complete is not going to work for twoS。

 why won't it work anyone？what was special about three in our reduction that showed that threeSAT was NPB complete？

Oh。LikeWell where do we need to use three there？Yeah。

 exactly exactly it just comes from the fact that in order to construct a circuit we need gates and a gate has to have two inputs and one output you know in order to be able to sort of relate two different things to each other so you know with twoat like with twoat clauses you know we could encode a not gate but a not gate is just not enough to build a universal Boolean circuit out of right okay and indeed you know that sort of reasoning is going to you know lead to why twoat is actually solvable in polynomial time in fact even in linear time。

😊，Okay， so let do let's just do an example， let's say that we have a bunch of two set causes like X or Y。

 let's say。Not X or not y All right， let's just say that we've got these two clauses Okay。

 the point is that I can rewrite both of these as as logical implications between x and y okay。

 but this is really saying this one is that，If x is false then y has to be true right。

 and conversely， if y is false， then x has to be true。 Okay。

 what this one is saying is that if x is true then y has to be false， and conversely， if y is true。

 then x has to be false。Okay， but now you know you know like an input。

 you know this has like your same you know hand is forced kind of character as we saw with two coloring right where you know you commit to one thing and it just forces something about its neighbors okay and we like that if we're trying to solve a problem in polynomial time so now what we could do is just imagine a graph where the vertices are x not X y。

😊，And not y okay and this will be a directed graph and we will draw know an edge from one ver x to another if you know assigning you know the one forces the assignment to the other。

 so not x implies y， so we will draw an edge like that， not y implies x。

 so we'll draw an  error there， x implies not y，So we have like that， and y implies not x。Okay。

 so this graph just consists of two cycles okay now what you can notice is that both of those cycles actually correspond to satisfying assignments right you know so you know you just you know if you can follow through you know a cycle you know you know you can just visit all your vertices you know you know and it just hits an assignment to everything right then you know this is just saying that everyone is happy right you know you know all these variables have been set in these ways and no contradiction has been reached。

😊，Okay okay， now what is it that would tell us that our twoat was unsatisfiable or what would tell us it was unsatisfiable would be if no matter where you started。

 like if you started at X and you just followed errors along then you would be able to reach not X and if you just started at not x and followed hours along。

 then conversely， you would be able to reach X。Suppose that both of those were true then that would be saying that that the x true implies x false。

 that x false implies x true but if that's the case then certainly you're too sad is not satisfyisfiable and what can be proven。

 or what's not that hard to see is that in fact whenever you're too sad is not satisfiable。

 there are going to be cycles of that form or you or I mean it's easier to just see the contrapositive if there are no cycles of that form then by just following the cycles that are there。

 you you'll be able to trace out a satisfying assignment you're too sad。So。So let's see， for example。

 if we also had from X to y。And from y to x and from not x to not y and from not y to not x。

 right then in this case it's quite easy to see that we can get from x over to not x。

 and we can also get from n x over to x， so which means that if I had added the two clauses。

X or not y and not x or y， if I had all four of these clause。

 then I get an unsatisfiable toat instance， and I could see that by just doing like a depth for search or whatever on this graph and seeing that I can reach not x from x and I can reach x from not x。

Okay， so。So that's， yeah。Yes， so if I delete so okay good， that's a good example。

 let's suppose that I delete the last one all right so then I would only have one of these not the other and so then like in that case I would be able to reach x from sorry I can reach not x from x right sorry sorry I can reach x from not x right but I can't。

Wait a minute。 Oh， oh， I think the way it must work is sorry like that。

I think that these are the ones I delete， right？So yeah。

 good so so in this case I can reach not x from x， but I still can't reach x from not x which is telling me my instance is still satisifiable right you as long as because because as long as then I can just set not x know I can set x to be false know and then it's okay it's only if I can reach both of them from the other one that I have the contradiction。

😊， you know， for some variable， I can reach for some variable X。

 I can reach Xi from not Xi and notxii from Xi， then my twoat is unsatisfiable。

 otherwise it's satisfiable。😊，Okay。Good。Incidentally， if I just change the problem slightly。

 so let's say that like I told you that your twoat instance is unsatisfiable okay so it's not satisfiable。

 but I just ask you， can at least k of the causes be satisfied okay so I ask is there an assignment that satisfies you know at least k of the causes of your twoatAT instance。

 that version turns out to be NP complete？So you know。

 there's a wonderful illustration how you just make a slight change to a problem that's in P and it can become NP complete。

 and vice versa also。😊，Okay， so the max2at problem is actually N be complete。The arrows。Oh， okay。

 all right， sure if you say so。Thanks， thanks， Adam。Okay， yeah。That's right。Yeah。

 though that's just what I was saying before， if it's only one direction， then that's fine。

 then it's satisfiable。Then it's satisifiable because then you just have to。

 you have to start at the you know if x can go to not x and that's telling you that the variable that x cannot be set to true。

 if it's true， then it's also false， okay， but if you can't get from not x to x。

 then you could just set x to false so then you're fine。

Because you can't know because there's no implication that if it's false， it has to be true。

 so that's just telling you that x has to be false。All right。😊。

So also like if I gave you a twoat instance and now I asked you how many satisfying assignments does it have that turns out to be NP hard as well okay in fact that's not even in NP so that's even harder than NP complete okay but but it's certainly that that's an NP hard problem okay so just you making you know the fact that twoat is in P does not mean that every question that you you might want to know about a twoat instance is also in P okay it just means that determining whether all the causes can be satisfied or not that problem happens to be in P。

Okay。All right。Yeah。Oh yeah， no absolutely so that's an easy case right like you know even if a problem is NP complete in fact even if it's undecidable like the halting problem you know it can perfectly well have easy cases you know I give you a program that has no loops of any kind in and I ask you does it halt you say well。

 of course it halts right you know I give you you know a map where you know where none of the countries are connected to each other well you know of course it's three colorable right you know and same way you know if I gave you a twoat instance and K was equal to the number of clause and I ask you can K clauses can be satisfied then then you just got twoat and you already know the twoSas and P。

😊，So in order to get the NP complete cases， we need to set K less than the number of clauses。Now。

Okay， you know， and by the way， you know， if you ever haven't defined that like for any problem。

 this one that you know that you can both， you know。

 there's some instance where you can both solve you know that case of the problem in P and you also have an NP hardness reduction that works for that case。

 then definitely let me know about that， okay because then you've proven P equals NP。Okay。

 but so far that hasn't happened right so far in every situation， you know。

 if a problem both has easy cases and cases where an NP hardness reduction works。

 then the two cases are like you know don't match each other they're in different places， you know。

 so far you know for the last 50，000 times that people have tried it you know that just you know the two cases have always been disjoint from each other okay and that's part of the intuition。

 why we believe that why many of us believe that P is not equal to NP in the first place。😊，Okay。

 you know because it only would have taken one case where you know。

 like if we had been able to prove that twoSAT was NPp complete and also prove it was NPp， you know。

 and you know， yeah， then thenp would equal NPp and by the way， you know， if p equals NP。

 then one implication of that would be that every problem in P is also NP complete。😊。

on touring reductions anyway right you know just be trivially NPp complete okay and so this is you know this is a reason why like you know if I say that2at is not NPp complete you know strictly speaking I mean you I mean well it's not NPB complete assuming p is not equal to NPP because you know I can you know you can't definitively rule out that you know that anything in NPp is not NPp complete you know unless you knew that P is not equal to NPP。

😊，All right， so these are I'll leave these announcements there。But want them。U。Okay。

 so I wanted to say a little bit about， you know the question of what should you do if you encounter an NP complete problem in your life？

Okay so。😊，So what are， you know， maybe I can just you know ask the class like what are some ways that you might cope with an NP complete problem。

 okay， I mean you know， and all right， I'll throw out the first one for free， give up。

just say all right， but what else can you do besides giving up？Yeah， all right， excellent。

 so well let me write this down。😊，So approximation， meaning， you know。

 instead of looking for the optimal solution， you might just try to find one that's just pretty good。

 what else？Ahu。Yeah， change the problem。Okay。Okay， you know， very often right， you know。

 if you brought into an NB complete problem and just sort of telling you that you know you were asking the wrong question or you were asking something that was more general than what you actually needed to know and by using more specialized information about your problem you can make it something easier yeah。

Yes， okay， that's an excellent one。😊，Okay so like we just saw examples where you know even NP complete problems have special cases you know that are NP P right and very very often in practice you may find that even if your problem is NP complete that the instances you know that arise in your application or actually much。

 much easier than the worst case and we can already see you know examples of that right so we proved the three coloring was NP complete okay but in order to you know to give that proof we had to construct a world map that looked like this right you know you know well actually just a single piece of it a single end gate of it looked like that you know the real world map would have like many thousands of these hooked together okay and then you say well wait a minute that doesn't look much like any map I've ever seen you know I mean it proves the point that this general。

😊，problemble of three coloring a map is， you and be complete。

 you know it encodes you know whatever search problem you want okay but you know in real life。

 if someone hands you say a map of the United States you know or a map of Europe just the color that right is probably a lot nicer than this one okay and you know and so so so so sometimes that's just you know like a fact that you can use in practice and there's not really any theory behind it。

 but you know you just try it you just try out you know try to solve your instance and it just kind of works other times we can get more formal about it like we can find that there is some parameter of your problem like there's a parameter of graphs called the treewi for example that you we can say that actually in order for the problem to be N be complete know you know like the N be complete cases of this problem involve very large values of that parameter but actually the。

That I can construct the instances that I care about in my application only involve very small values of the parameter。

 and then when there's small values of the parameter then I may be able to prove that actually for those cases there's an efficient algorithm so you have on PSet4 you have a problem that's like that。

 the subset sum problem is known to be NP complete。

 if the numbers that you're summing can be like arbitrarily large capable what you'll prove is that if the numbers that in you're set are small enough。

 then there's a polynomial time algorithm。Okay， so。😊，So you know in fact。

 there's a whole theory of like parameterized complexity。

 it's called that deals with like you know finding like other parameters that control the difficulty of your problem besides just the obvious one which is the size of the input finding you so in addition to n you find some other parameters。

 K you or Kl whatever that somehow affect the complexity of your problem and you may find that you you can get like an n to the K algorithm so as long as k you like if K we n then yeah you're in the exponential case and and you could probably prove it's np complete also。

 but if k is only one or two then then you're pretty good。

 if K is 10 or 20 then then not so good but then there's also cases where what people really like in this theory is when you your complexity is like some function of K times n。

So I as long as K is constant and this is a linear time algorithm， unfortunately。

 what you find in this theory is that that function F of K。

 often it's something messed up like some enormous function of K。

 you could say as long as K is constant and that's a formally linear time algorithm。😊，U。Okay。

 so so how else can one cope with be completeness， yeah。啊。Yeah build well。

 build a quantum computer I'm going to put a big question mark there okay and it's not only for the obvious reason that you know that we don't know you know or you no one has built quantum computer yet you know I tend to be an optimist about this because I work on quantum computing you know I think you know if civilization lasts long enough eventually we'll have these okay but the real reason I've drawn this question mark is that you even if we have a quantum computer we don't yet know how much it's going to help us for Np complete problems know we know for sure that it could do factoring okay you know but we're going to see actually later in this lecture they're very。

 very important structural reasons why we think factoring is not NP be complete and those same structural properties a factoring that make it not NP complete you know also make it extremely useful for cryptography this is why we we base all our cryptography on factor。

😊，Rather than on NP complete problems， but unfortunately。

 those same structural properties also enable a quantum computer to solve the problem。

Okay so so factoring is really special and all the other things that we know for sure that a quantum computer could do are also somehow special。

 you know in some way and for Np complete problems， it's been a huge。

 huge open problem for the last 15 years you know whether a quantum computer can help you and if so by how much but most of us do not believe that a quantum computer is going to in general that you solve Np complete problems in polynomial time it might give you some advantage you know like it might improve the you know it might lower the rate of the exponential for example。

 okay but that it would you know or it might handle special cases that a classical computer will not be able to handle and there's some evidence for that but you know you know to solve the worst case in polynomial time that we think not even a quantum computer is going to be able to do。

😊，Even if you have a perfect one， so this is an extremely interesting topic。

 I'll say more about it at the end of the course， but for now I'm just going to put a huge question mark there。

😊，So okay， so what else yeah？To accelerate。Practice your cases are small。Yeah， okay。

 excellent so you can you know。I'm going to say just brute for it。

And just brute forcing it you know often works fine。

 you know it certainly as long as your instance is small enough it works fine right if you've got you know like like often in practice you'll have to deal with an NP complete problem you know but only on instances of size 10 right then you know just just brute forced a thing right you know。

😊，You know what's the problem okay but even if your instance is larger than that。

 you know you know we have algorithms that are much。

 much better than just you know trying every possibility okay so you can do brute force but be a little bit less brute about it okay so and actually if you take like the AI course you learn all about you know the methods that people have come up with to improve on brute force search。

Okay but。Most of them involve some sort of backtracking okay well let's just okay。

 so so there's sort of two there are two types of algorithms for you know dealing with with NB complete problems。

 okay， which are called。Complete and incomplete algorithms。Okay。

So a complete algorithm will be one that either finds a solution for you or else it tells you。

 I have proven that there is no solution， okay， or you know。

 if you ask it to find the optimal solution， then it will guarantee you that it finds the optimal solution。

 okay。YouAnd an incomplete algorithm is one that just tries to find the best solution it can okay and there's no but there's no guarantee that it's found the best one and you know and if it doesn't find any you solution at all that meets your criteria then there's no guarantee that no solution existed。

 all you know is that this algorithm didn't find one Okay so these are two very different kinds of algorithms okay but now you know even you know if you insist on a complete algorithm。

 you can still be a lot smarter than than doing brute force search。

 okay so you and and we know this from experience right if you've ever solved the Sudoku puzzle right I'm going to assume that you didn't do it by just enumerating every possible way of filling in all the squares and then just rejecting you know what if I filled them in with all ones that doesn't work okay what if I filled them in with all ones except with the last square。

two no that also doesn't work right and one of the last square is a three right you know you didn't just try every possible assignment in lexa graphic order okay I'm going to assume that you are a little bit smarter about it than that right and you said well all right。

 if I fill this one with a four then then this one you know you know obviously I can't have any other fours in this same you know three by three square right so I can just cross out that entire that entire branch of the tree can be can now be pruned right doesn't have to be searched anymore okay。

😊，The same way， you know， if you're threecoling a graph right， you know。

 as soon as I know that something is red， you know I don't have to bother searching you know the solutions that would assign one of these to be red Okay because I already know that those are bad okay these are not going to meet my criteria so so now you know I've just cut down the size of the search space okay and you know this is certainly something you can do in practice and you know often you know gives you very。

 very substantial improvements okay like it's still going to give you an exponential time algorithm。

 but it will be a milder exponential right and so it will let you handle much larger instances than you would have been able to otherwise and you know in the more clever you are about how to do the pruning you know the larger the instances you can handle and。

You know， and sometimes you can even analyze such things。

 you know theoretically and you can prove that they give you an improvement over brute for search Okay。

 so let me。Here's a few examples for threeS， you know。

 one can actually prove rigorously that there's a clever algorithm that lets you solve threeat in about 1。

3 to the end time。😊，Okay， at least that's the best current record when I last checked okay so you know。

ny so yes， you know， of course the best algorithm is exponential， you know。

 otherwise you would have heard about it right but you know。

 you can improve over two to the end you can you know， pretty substantially actually okay for。😊。

For something like Hamilton cyclecle， how long would Hamilton cyclecle take if you really use pure brute force？

Anyone。So you want to know like you know， can I is the re that visits each of v tech exactly once。

 if I really just did pure brute force， how long is that going to take me？N factorial。

 yeah exactly n factorial times so let's say this one was an improvement on two to the end。

 you know n factorial， maybe times n or so right because you know there are n factorial possible permutations of my vertices and in each one I'd want to check if it works or doesn't but you can be more clever about it and there's an algorithm that's merely two to the end。

😊，Okay， so。😊，You know， N factorial is sort of is roughly by Starling's approximation。

 it's sort of like n to the n because it actually like n over e to the n you can get something that''s you know。

 and that's sort of like2 to the N log n。😊，Right， I'll play very， very roughly， okay。

 but you can improve that you can make it merely two to the n Okay， and as a general rule。

 like every single situation where the brute force algorithm is n factorial。

 there seems to be a way to improve it to2 to the n。😊，I don't know any exception to that。

 you know unless you've just constructed one artificially so okay。

 so so often you know you can do better like that okay then there are also incomplete algorithms so。

😊，嗯。And。Most famous of these are various local search heuristics， okay。

 so there's something called simulated andnealling， there's genetic algorithms。

And you know there are various others okay and the incomplete algorithms。

 usually the way they work is just by starting out with a random solution and then just looking for ways to improve it okay so you could just like if you're trying to solve threeatAT。

 you could just start with a random assignment and then just repeatedly you know flip a variable。

 you know if it's going to increase the number of causes that are satisfied okay now what do you think is a problem with doing that anyone yeah。

😊，Exactly you can get stuck at local optimum right is this is sort of the central problem that these incomplete algorithms face okay because you can think of it as you know they're basically trying to climb a hill right you have this you know enormous dimensional landscape you know of all the possible solutions and you know let's say the height of each one is the number of satisfied causes and you are trying to reach。

😊，The highest point， okay， but you know， if you start over here and you just sort of go up for a while。

Well， you know then this is going to look like the highest point right。

 you know as far as the algorithm is concerned right it's you know you any way it goes from here it just makes things worse。

 okay but of course you know way further out know there were higher points but it just failed to find them okay and yeah。

😊，Yeah， but almost every NB complete problem sort of does have this character right that you can you know say so yes you have to make up an objective function and you know for an NB complete problem like there could be different objective functions that you could make up for the same problem right like for three set an obvious choice would just be the number of satisfied clause but you but then for subset sum you maybe it's a little less obvious like you could say you know the difference。

 you know the absolute value of the difference between the sum of your you know you know the subset you selected and the target sum that you' were trying to reach and you could say you were trying to minimize that you know ultimately get it down to zero。

Okay so yes you're right， you have to make up some objective function right I mean there will always be a trivial way to do it right but you know just say like the objective function is one if I have a solution and zero if I don't right but you know but you could you know you want to make up an objective function such that just trying to maximize that objective function is actually a good way of finding a solution to your problem。

😊，Yeah。So， in order to get out of local optima， you these incomplete algorithms， you know。

 which you're also called houristic algorithms。You know they'll typically you know also be willing to go down the hill sometimes so sometimes they'll be willing to make moves that make things worse just in order to explore the space a little bit more and hopefully find the higher peaks but but then there's a tradeoff and there's a lot of art to design of these sorts of algorithms。

 but in general know they can work know they can often work spectacularly well in practice like for you problem like they can handle know three sad instances like with millions of variables that that tend to arise in practice if you are trying to construct an instance that made those algorithms fail then you could certainly do that like for example by just taking something from cryptography by reducing encoding factoring into threeat。

Example， which you know you must be able to do because threeSa is NP complete okay。

 and that'll kill all these algorithms， you know， they'll just have no idea what to do okay but you know。

 but but if you take three sad instances that sort of tend to arise in real life applications。

 you know then these houristic algorithms often do remarkably well。😊，Well。

 see that's the issue right a houristic algorithm runs for as long as you want to run it for you know it runs for as long as you have time for okay so it's not you know so like the entire concept of the running time of an algorithm is sort of design for like when we have a proof that like within this amount of time。

 the algorithm will have done such and such right and for houristic algorithms。

 there's not really any proof that they're going to do anything good so you've sort you you've sort of left you the realm of this course you know the realm of rigor and you've entered you've entered the realm of the dark arts or you're sort of you say you who go this way you're on your own here we can't give you any formal guarantee that your algorithm will do anything you can run it for as much。

😊，Time as you have and see how good of a solution has it produced within that amount of time？Right。

 so presumably， in practice， you only have polynomial time in some sense， right。

 And so then the question that interests you is how good a solution can these things produce in polynomial time。

 But， you know， but often， you can prove that yes， if you let this thing run for exponential time。

 then it would find the best solution。 You know， often often often that often that's not hard to prove。

😊，Okay， all right。😊，I did want to say a little bit about approximation because that's a big one so you might hope that know let's say that you know I'm trying to solve the traveling salesman problem or something okay but know but now I give up on my demand for the optimal solution for the shortest tour this is all the cities I say now I only want a tour which is within 10% of optimal then you might hope that even formally that this would make your problem no longer NP complete you that there would just be a polynomial time algorithm that could provably always find you a tour that was within 10% of the optimal so is there or isn't there well that depends on the NP complete problem for some there's a good approximation algorithm for some there isn't and figuring out just how well the solutions to NP。

complete problems can be approximated has been a central topic in theoretical computer science for the last 25 years or so okay it's a huge。

 huge topic， you know， you know very complicated you。

 but sort of led to some of the deepest results in the field。😊，嗯。So。On the one hand。

 there were some pretty striking positive results。 So let's say that you had the traveling salesman problem in the Euclidean plain。

 okay， meaning that。You know， I just give you like a bunch of cities as XY coordinates。

 and now I ask you。For the shortest tour that visits the HC city once。

 which in this case maybe is that one。I'm not actually certain that it's that one。

 but it looks like it， right。😊，So okay， but you know， but now you know， you know。

 and you can see that this problem， you know， it looks kind of hard， you know， like like like indeed。

 you know this problem， the Euclidean traveling salesman problem is already np complete okay you can you know n hard okay you know you can one can prove that okay but it's sort of intuitively it looks like it shouldn't be that hard to get a decent approximation right you know just kind of go through right like you know that you know you're not going to be zigzagging all over the place right the best tour is going to be kind of moving locally and you know so in fact。

😊，There's an amazing result of Sanji Aurora from 1996 that says that for every positive epsilon。

There is a polynomial time algorithm。That gets a solution that's just within a multiplicative one plus epsilon factor of the optimal solution。

OkaySo you know if I say I want a solution that's within 1% of the optimal。

 you know then there is a polynomial time algorithm for that， if I want a solution within 0。

1% of optimal theres a polynomial time algorithm for that now it's true that like the complexity of the algorithm you will blow up as epsilon goes to zero right it has to because we know that when epsilon is zero then the problem is n be complete。

Okay， I forget at what rate it you know polynomialally or exponentially as a blowup as epsilon goes to zero。

 but know， but this says， you know， you can get really。

 even though the problem is NP complete to solve exactly， you can get really。

 really good approximations to the answer in polynomial time。😊，Okay。

 that's a planar traveling salesman problem you know， if you drop the planarity condition。

 then you already it becomes much harder to approximate it。Okay。Now。

 on the other end of the spectrum。Let's let's go back to our favorite example of the threeSAT problem Okay so let's say that I give you a threeat instance and I just ask you to satisfy as many causes as you can then。

So could anyone think of a way to at least satisfy some fraction of the clauses？

Sat everything to true， Well， okay， if every cause had only false literals in it， then you know。

 like in practice， that would probably work well， you know。

 but I can construct an example where that doesn't work yeah。Yep， yeah。

 you could just pick the literal that know occurs in a lot of clauses and set it to true， you know。

 yeah， you could think of a lot of things you know that would do reasonably well let me give you something even simpler than that。

 set every variable randomly。Okay， set each variable just completely at random。

 then I claim that that will satisfy about a seven eighth fraction of the clauses you know。

 in expectation， anyway you know， assuming that each clause has exactly three literals in it， okay。

 why is that anyone？😊，Yeah exactly because you know。

 because for each clause with three literals right of the eight possible assignments that could have。

 there's only one of them that's you know not that doesn't satisfy that cause right and so like in expectation you know we're going you know we haven't gotten to linearity of expectation but for those of you who' have seen that right you know each clause you know has a seven over eight probability of being satisfied and therefore the expected number of clauses that will be satisfied is seven over eight times the number of clauses okay so。

😊，It's very， very easy to get a7 over eight approximation。

 in fact I could leave this as an exercise for you。

 but it's even possible to get that deterministically as well okay you can design a deterministic algorithm that also gets this seven over eight approximation and it would be a little bit along the lines of what you were saying actually you know you go through and you know for each variable。

 figure out how to get this okay okay now。😊，One of the biggest achievements of theoretical computer science。

 you know， ever， certainly in the last 30 years there was something called the PCP theorem。

 it's not what you think it's probabilistically checkable proofs okay。

And you could think of this as like the you know。Well， okay。

 maybe appropriate to the name it's like the Cook Levinn theorem on some really powerful drug okay it's a super duper form of the Cook Levin theorem where it says is that not merely is threeat and you NP complete but you know in fact。

 even just to approximate threeat you know reasonably well is already an NP hard problem okay and。😊。

You know and in fact， you know， you know the original result was weaker than this。

 but today we know the following that。For all epsilon zero， for all positive epsilon。嗯。Okay。

 so it says。You know， if I pick any fraction I want greater than7 over 8 okay then you know I could give you a three set sense where I promise you let's say it is either know either all the clauses can be satisfied or else you know less than 88% of the causess can be satisfied。

 Okay and I ask you to decide which and that will be NP complete that will be an NP hard problem so what it says is that you know this stupid algorithm of just pick all set all the variables randomly that is that is essentially the best possible algorithm for three。

 That's the best approximation that you could ever get for it unless p equals Np if you can get even a slightly better approximation than7 over 8。

 and do it in the worst cased then p would equal NPp then you'd be solving an NP complete problem so that's an。

😊，Aazing phenomenon that somehow at 7 over 8， the problem undergoes the sharp phase transition from being easy to being NPP complete。

You know for other problems we don't know the answer quite as sharply okay for a lot of NP complete problems like there's some regime of approximation where we know that you can get it and then there's some other regime where we know that if you want to get an approximation that's this good then it's NP complete okay and then there's an intermediate regime in between them where we don't know if it's possible to achieve it or not achieve it okay so you know we neither have an algorithm nor do we have an NP complete in this result now if any of you have heard of the unique games conjecture that's one of the big open problems in theoretical computer science right now and the whole point of it is to close off a lot of these gaps if this unique games conjecture is true then basically a whole bunch of these problems you know actually are NP complete in the whole intermediate range where right now we don't know what happens。

Okay，So you know， this is a very active research topic。Okay。

 so the one last thing that I wanted to say is that。

You know there you'll often hear claims that you know that someone has built some physical system which is able to solve N complete problems in polyinnomial time。

 you know I'm not even talking about quantum computers here okay some people will say know that DNA or sorry that proteins are able to solve NP complete problems okay because you know if you just like formulate the problem you know I give you a sequence of amino acids and now you know what is the lowest energy state that this could fold into you can you know a reasonable formalization of that problem can be proven to be n complete and you that's kind of strange because every protein in your body you know is doing this all the time and they usually take only about a second to fold okay so does that mean that you know that the proteins in your body have a magical ability to solve NP complete problems right？

And you know to be even more concrete， does this mean that we could just synthesize a protein whose you know minimum energy folding configuration encoded a proof of the Rieman hypothesis and then we could just watch it go and then from this protein we would read out our proof of the Riman hypothesis you know that's what it would mean if this was literally solving an NP completete problem or that you could use it to break the RSA cryptoyst or something like that okay well know I'm probably not alone in being skeptical of that right and my preferred explanation of this is that well nature is simply chosen to avoid the hard cases of the really hard cases of the problem you know it is chosen to design proteins that that are relatively easy to fold and there would be a very strong evolutionary selection pressure you for proteins to be easy to fold。

😊，not misfold right you know even then you do sometimes get misfolded proteins so you know pons which are the agent of mad cow disease seem to be examples of proteins that have gotten stuck in a local optimum right they haven't folded into their global optimum okay and you know I would I would tend to analyze all the other cases similarly okay so。

😊，So on Thursday， we will talk about you problems that are not NP complete。

 you know like factoring and well at least the reasons why we believe that things like factoring are not NP complete。

 we'll talk about CO NPP， the NP versus CO NPP problem， we'll talk about peace based completeness。

You have them okay。What， what？Okay。Okay。Okay， so we'll have them for Thursday。Okay。

