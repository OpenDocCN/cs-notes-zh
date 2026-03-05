# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p21 P21 20moreapplications -BV1RdBTBrEdx_p21-

![](img/753bc7cf3b0263e2f42fda5c8dc77342_0.png)

Thank。We did not cover。This is laser。Yes， correct。

![](img/753bc7cf3b0263e2f42fda5c8dc77342_2.png)

You see how wonderful this class amazing isn't it and youre I guess we covered it。

 we had an extra two hour lecture on Saturday cover it going。😊。



![](img/753bc7cf3b0263e2f42fda5c8dc77342_4.png)

我的。Okay， let's go ahead and get started。A couple of the administrative things。Oomework 8。

We'll be out tonight and because that's coming late。

 that'll be due next Wednesday rather than next Tuesday。Um。Sorry about the delay。

For those of you who are graduate students。There's a November 11th drop deadline。

That's a week from this Friday， so a little bit less than two weeks。嗯。It is unlikely。It's possible。

 but unlikely that we'll be completely great done with grading the midterm by then。

 but we're prioritizing， grading the graduate student exams first。

So if you are concerned about your grade， you come to office hours。Next week before Friday。

We can take a look at your exam， hopefully at that point it'll already be graded and then we can have a discussion about whether you really need to be concerned or not。

Like I said， the the actual grades are likely to be released you know， early the week after。

 like November 14th or so based on how well we did with midterm one。

 if we're lucky we might get it done on November 11th。

But I realized that's not a lot of time for people to make decisions in advance of the deadline so grad students will be graded first if you have concerns in you're grad student。

Come to office hours next week and we'll take a look at your exam。Okay。

Any other logistical administrative？Questions， okay， great。So。嗯。A week ago。

We started talking about applications of max flows and and cuts。And。Mostly of max flows。

And so specifically we talked about edges justjo paths。And we talked about vertex disjoint paths。

And vertex capacities， and we talked about bypartight matching。Which。

Hopefully proved useful on the midterm。And in general。

 the way all of these things go more or less mirrors the way that in 374。

 we did most applications of graphraph algorithms， we treat Ford Fkerson， or in some cases。

 Or's algorithm as a black box。And we try to modify the input that we're given so that it fits into that black box and then we take the output from that black box and we manipulate it until we get the output that we want。

So in general， the strategy is。You're going to feed some input。Into the algorithm。

And there's an input transformation which does something to turn that algorithm the input into a graph。

Then。Here I need to compute max flow and maybe I need to decompose that flow。Into paths and cycles。

All of this we know how to do。Via Ford Fkerson。And so you' as output， you're， for example。

 either going to get the max flow itself or maybe you only care about the value of the maximum flow or maybe you want a path decomposition of the maximum flow。

Different variants call for different boxes there in the middle。

And then I'm going to try to transform the output。😡。

Into the output for the problem that I want to solve。

 so this is the sort of standard reduction pipeline。嗯。If you took 374， you've seen this before。

 except in the middle there， there was。Propological sort or in the middle there was all pair shortest pads or in the middle there was。

Maybe single sort of shortest pads or minimum spanning treats or something like that。

So all of the things that I'm going to show you today kind of fall into this category。And whenever。嗯。

We're going to do this。There are a couple of stages that we need to go through。Okay。

 so we need to describe how to transform。The input。So this is an algorithm， right。

 so we need to describe how to actually do this part。We need to transform the output。And again。

This is another algorithm， usually the output part of the algorithm is relatively simple。

 but we still need to specify what that。What that algorithm is。嗯。We need to analyze the running time。

And this needs to be done in terms of the original input。So。嗯。I know that。

Oran's algorithm computes maximum flows in order VE time。

But if I asked you to solve a problem that doesn't natively talk about vertices and edges。

 I don't know what V& E are。So ghosts and houses， right。

 I need the running time of my algorithm as a function of the number of ghosts and the number of houses。

 not as the number of vertices and edges that about some graph that I know nothing about because it's hidden inside this black box that you're building。

Yeah。U。And。呃。We need to。At least at some level prove that this reduction is correct now in general in this class。

 we have not been asking for explicit proofs of correctness General what I'm going to be asking for is for you to at least。

😡，State。Explicitly the relationship between the output of the problem that you're solving。

And the output of that max flow box in the middle。😡，Okay， so。For the midterm problem。

I reduce it to maximum matching with houses on the right and ghosts on the left。

 every edge in the maximum matching corresponds to an assignment of ghosts to houses。Um。

 and so the connection there is just what I said that the maximum number of ghosts。

 if I can assign every ghost to a house。😡，If and only if the maximum matching covers every ghost vertex。

Okay， so that that line right there establishes the。

The relationship between the ghosts and houses problem and the maximum matching problem that I'm reducing to。

And in an actual proof of correctness， this is also stating the theorem that you would need to prove what it means for the algorithm to be correct。

😡，Yeah。Now， all of these bits。Are a。Basically。嗯。Looking for。Some sort of correspondence。Between。

 typically。Features in the solution that you're computing for the outer problem。And for example。

And for example， in the graph that I build inside the problem。系。Now。

 one of the things that makes this。嗯。Sometimes confusing。

Is sometimes the input to this problem is a graph。And so I give you a graph and I ask you to find some structure in that graph。

 and the way you do that is you transform it into a different graph。

 run Max flow on that different graph and then pull the solution back。

And we'll see we will see a couple of examples of this。

 I mean the simplest example was the maximum matching problem itself I gave you a bipartite graph。

And I transformed it into a flow network by adding a source in a sink and adding connections and directing the edges。

And so I compute Max flow in this graph that I built， which is not the graph that I was given。

 but it's based on the graph that I was given and so features in the solution in this case。

 edges in the matching correspond to pads in the maximum flow of this graph that I built。😡，开。

So this is the outline that we're going to follow again in homeworks and exams we're typically not going to ask for explicit proofs of correctness。

 we are going to ask for at least a statement of the theorem but。😡，So。

We don't need this in homeworks and exams。😡，But nevertheless。You need to do it。Right， because。

The reason for at least walking through at an intuitive level how the proof would go is the way that you convince yourself that your algorithm is correct。

😡，If you don't do this proof of correctness， it's actually fairly easy to get distracted by things that look plausible。

 for example， problem 2 see on the midterm that are in fact not correct。😡，系。By the way。

 there are people taking the conflict exam right now。

 I will be posting the midterm and the midterm solutions。

 including both the intended incorrect solution for2C and a correct solution for 2C。

 and you'll understand why I took that off。Okay。嗯。Okay， so。

I'm going to jump right in to sort of typical example of a problem that can be based。😡。

To be solved using maximum flows。And this is a problem based on exam scheduling。

 so this is not like one of those canonical problems like maximum matching or topological sort。

 this is just a problem that I made up。Okay so。It's time to schedule final exams。😡。

And now there are a bunch of constraints that apply to scheduling final exams in particular。

 you know I've got a bunch of classes。So my input。I've got a bunch of classes。

 each of which needs a final exam， okay。Now every exam。Needs to be scheduled in a particular room。

And it needs to be scheduled in that room at a particular time slot。

And somebody needs to be available to proctor that exam。😡，But there are constraints。

You can't have two exams in the same room at same time。😡。

You can't have each class only gets one room and one time slot and one proter。😡。

But a proctor' can only proctor one exam。At one time。You can't schedule。

A final exam for a class that has 120 students in a room that seats 12。

So the rooms all have capacities。😡，And so let's。Say that every class。Has an enrollment。

So the number of students that are actually taking that class that's given to you in an array。Yeah。嗯。

Every room。Has a number of seats。And well， factors。Are only available at certain times， so for each。

😡，Time slot。And for each Proctor。I'm going to say this is the availability。So a of。K， L is true。

Means。Proctor L is available。At。Time slot K。Okay， so I have a bunch of resources。😡。

I have some constraints on those resources， how they need to be combined。

What is it exactly that I need to compute？😡，UmUm， so let me， let me write down， you know， he just。

Because I don't have enough already in the problem statement。Every class。Needs to be scheduled。嗯。

The number of students in the class has to be less than the number of seats。Breach exam。

I can have at most one。Exam。Her room。P time slot。And just to make things even more annoying。

Each proctor can only schedule can only proctor at most five exams because state labor laws require if they work for more than a certain number of hours you have to pay them benefits。

 we don't want to do that so。Each proctor。Can watch。At most five exams。And only when。Available。Okay。

 so there's my problem。What I want to output。Is。For each class。Where is their final exam。

 when is their final exam， and who is their proctor？Subject to all of these constraints。Okay。So。

A bitit overwhelming。So output。Ro。Time。😔，Proctor。Or every class。Okay。嗯。So。I can kind of。

Think of the objects that I'm computing as a set of tus。Um，That's， you know， I， J， KL。

 where I is a class。Jay is a room。Ks of time。And El is a proctor。All right。

So everybody understand what the。What the problem is asking for。lots of data being thrown at you。

 but we're going to organize it in a way that makes sense， yeah。啊，错的。喂喂开始。I mean。

 we can vary the problem and ask， you know， what's the maximum number of final exams that we could schedule subject to these constraints？

HowWhat's the smallest number of proctor that we need to hire？

That would add that we could satisfy there's lots of variances， but let's just solve the problem。

 can we schedule all the exams？Right。So about。5ive years ago。Cornell。

Was getting lots and lots of student complaints about exams， final exams being clustered together。

So like we have a rule that says you can't have more than two exams in any 24 hour period or you qualify to take a conflict exam for one of those classes。

So。Cornell had had a similar rule， but the number of conflicts that they were getting was getting out of control。

 so they hired。Some faculty from the computer science department say， hey。

 can you help us figure out how to schedule our final exams？Kind of like this。

 except then they had like an additional thing which made it much more difficult where for each student you want to minimize the number of exams they have back to back。

😡，And they managed to reduce the number of back to back exams by like 40% or something。

 so this is the one instance I know where someone from a computer science department did something intelligent and the university actually adopted it。

Okay。嗯。So each of these tus。😡，Corresponds to an exam， so I can associate with an exam。

 at least four different numbers。Now。嗯。This is an example of a type of problem that I call tuple selection。

😡，I've got a bunch of resources that need that are tied together somehow。

 I've got constraints on those resources and how they interact。

And I want to pull out a large set of tus。😡，With one of the elements of the tuL are one of each resource。

That meet all those constraints。😡，Okay， so the more general version of the problem。

So tuupple selection。We have a bunch of finite sets。Goll that x1， x2 up through。X of D。

These represent the different resources。U， and I have。A capacity。For。So for each resource。

 meaning for each element of each of these sets。😡，I have an associated value。Which。

I'll think of for now as a capacity。And similarly。Or certain pairs of。IOf resources。Okay。

But these pairs have to be in。Adjacent sets。Okay， so these capacities are going to encode the constraints on the various resources so so in the exam scheduling problem。

 we have a constraint that there can be at most one exam。😡，In any room at any time slot。Right。

We have a constraint that each proctor can proctor at most five exams so that that one's the simplest so this is going so one of these sets is going to correspond to the set of proctors。

And that proctor can only be involved in five exams。

 meaning they can only be named in five of those tuples that we're going to output。😡。

We also have pairwise constraints。So。Oh。Yeah， the most one exam per per per room per time slot will turn out to be a pairwise constraint。

 So if I look at the tus that contain。Pick a time， pick a room。

 there's at most one tuple that contains both that time and that room。😡，Okay。

 so the tuples that I'm pulling out correspond in this case to the exams in more general more generally what we want to output。

Is the largest。Set。Of。Tups。For the form little x1 up through little X D。Um。

In the product of these sets。So little x1 comes from big x1， little x2 comes from big x2， and so on。

Um。Subject to the constraints。That。Each X in。Any x sub I。Appears。At most c of x times。And each X。

Why pair。In adjacent constraints appears at most c of X Y times。

The absolute simplest version of this tuple selection problem is maximum matching。

I have two finite sets。😡，L and R。I have no constraints on the individual items。😡，No。

 I do have a constraint in the individual items。Every one of these vertices can appear in at most one pair。

😡，And every pair can occur at most once， so c of x is one for every x in the left set。

 C of x is one for every y in the right set， every x in the right set。

 and C of x Y is one for every x on the left y on the right。

The tus that I'm pulling out are edges in this bipartite graph。😡。

And I want to find the largest number of edges such that each vertex on the left appears at most once。

 each vertex on the right appears at most once and each edge appears at most once。Okay。

So how in general， do I solve this？Well， just like the maximum flow problem， sorry。

 the maximum matching problem。I'm going to set up a flow network。

And the flow network is going to have。Dlayers， one for each set that I'm given。

 one for each set of resources。And now I'm going to set up a source for text on one side。

Target vertex on the other。And I'm going to connect all these。And。

The easiest thing to imagine is that this graph in here is complete。This graph in here is complete。

This graph in here is complete， meaning for every index I。

 I have an edge from every node in Xi to every node in Xi plus one。Okay。😊，嗯。

Then for every vertex X in any of these sets。😡，I'm going to add a capacity。C of x。And for every edge。

 let me call this edge UVv。I'm going to add a capacity。C of UV。Sorry for the change of variables。

 but。So I'm going to assign capacities to the vertices and I'm going to assign capacities to the edges。

😊，Just transcribing the capacity that I'm given for the objects and for pairs of objects that I was given in the original input。

😡，Now， what is a tuple in this case？A tuple corresponds to a path from S to T in its graph。Yes。不是你是。

すよ。It is a number that I attach to the pair XY。😡，It signifies a number that I attach to the pair X Y that is problem dependent。

In the exam scheduling problem， it's。😡，Each。😡，Time room。😡，Can appear once。

But it's problem dependent in general。I mean， what it's actually saying here is。😡。

ImThe tuples that I'm pulling out correspond to these paths from S to T。

The the capacity C of UV means the number of these pads that I'm allowed to push through the edge UVV。

😡，That are allowed to contain the ajuvy。Likewise， the capacity of that vertex CX。

 that's the number of paths that are allowed to go through vertexX。

 which is the same as the number of tuples on computing that are allowed to contain item X。Yes。

 so are we only allowed to fair wise on yes， so this is very important。

This whole setup works as a maximum flow problem。😡。

If and only if constraints between pairs of items occur between pairs of items in adjacent sets of resources。

 There's a way of ordering the resources from one to D。

So that every constraint appears between one set。😡，And by itself。

 just a single node or a pair that appears in consecutive sets。The third and fourth set that's fine。

 the fifth and sixth set that's fine， the 28th and 29th set that's fine。The moment you vary。

From this。Set up where everything is nice and ordered。😡，The problem becomes NP hard。

So if the constraint， if the graph connecting， if you imagine a structure that you have a node for every set and you have an edge between two of those nodes。

 if there's a constraint involving those two sets。😡，If that graph is a path。😡，Then you' you're good。

If that graph has a cycle in it。The problem is NP hard。 If that graph has a node to degree 3 or more。

 the problem is NP hard。So it's very important that when you're given these things。

 I need to be able to order the resources so that the constraints only occur between adjacent pairs。

😡，系。I。So。But。If you've met that condition， you can set it up in a way that everything is nice and lined up。

😡，Then I have。U a correspondence between。Any tuple？And that corresponds to a path from。S  to T。

Which means that if I have any valid set of tus。Then I have a。Valid set of paths from S to T。

 meaning a set of paths that don't overflow any of my constraints。

 and that's going to correspond to having a feasible。UFlow。From S to T。

 technically the feasible feasible integer flow， but since everything we're doing。

 we're going to assume these capacities are integral because we're computing numbers of things。

 not weird fractional you know have fractional proctors or fractional students。

So everything's going to be an integer in these problems。

Any set of tuples that we construct that meets these conditions is going to correspond in this graph to a set of paths from S to T that meet the capacity constraints。

 sewing those paths together is going to give me a feasible flow from S to T that feasible meaning with respect to the capacities on the vertices on the edges。

In particular。😡，The largest。Valid set of tus corresponds to the largest valid set of pathsroistt T。

 which corresponds to a maximum。Feasible flow。From S to T。So we've taken this kind of。😡。

Very abstract。I've got some resources with some constraints on them。

 but all in this nice orderly way。And we build this layered graph where the layers correspond to different types of resources and then a maximum flow。

Can be decomposed into paths and those paths correspond to the tus that we're trying to compute。Okay。

So if I go back。😡，To the class scheduling problem。Now what I need to describe is。

 what's the order that I need to put these resources in， classes， rooms， time slots， proctors。😡。

And what are the capacities that I assign to the various vertices and edges？ok。😊，So。嗯。

Let's move this over here。😔，Sorry， this is going to be a little bit crowded but。

Complete it'll be okay。Well， I see one pairwise constraint here。😡。

That I've got a constraint between classes and rooms。

Um that I can only fit a class into a room if the number of students。

 the enrollment is less than equal to the number of seats。Now。

At some level this means if I have whatever graph I'm going to build。😡。

If I have a path that goes through a small room， it cannot then go through a large class。😡。

Okay so there are certain pairs of rooms and classes that I'm just not allowed to use。

So that's a pairwise constraint between rooms and classes。

 but it shows up as the capacity of that edge being either zero or one。😡。

One means I am allowed to schedule an exam for this class in this room。

 zero means I'm not allowed to schedule an exam with this class in this room。😡，Okay。

 so I need to put classes。Next to rooms。And then either zero or one， depending on。

Whether the class could fit in the room and I don't yet know whether classes in rooms would be。啊。

You know what order that's going to be in？The other place where I have constraints is the availability between proctors and times。

So again， this is going to show up as you know， proctors and times are going to be adjacent in order and I'm going to have。

😡，Well， some edges in this graph are allowed to have flow through them and some aren't。😡。

If a proctor is available at a given time， I am allowed to schedule that proctor at that time。

 but only once。Then I can't schedule the proctor at that time。

 so theres no path can go through that that edge so again。I'm going have。Proctors。And times。

And again， I'm going to have either zero or one。UAnd again。

 I don't know what whether I want to maybe I want to switch proctor in times in the order。So for now。

's these are kind of independent。The proctors themselves have a constraint。

So whenever we finally figure out the order， we'll say。

 put the know give each proctor vertex a capacity of five。嗯。

There's most one exam per room per time slot。So right here。

We seem to have something connecting rooms and time slots。So rooms and times have constraints。

 so every pair containing a room in a time has a constraint associated with it。😡。

That the number of exams that can happen with that room at that time is at most one。So。

This suggests that I need to figure out a way getting times and rooms to be adjacent。

So let me swap these。Now these are no longer independent。Right。This will be a capacity of one。

And I think at this point。I've I've set up the graph right and proctors have capacity of five all of the other。

Vertices have infant capacity。Hey。So here I've set up my classes， I've set up my rooms。

 I've set up my times， I've set up my proctors。Then of course， I need to put in a source ver Tex S。

And target vertex T。嗯。Between every pair of these blocks， I have all the edges。

 just that some of the edges between the class vertices and the room vertices have capacity zero。😡。

The rest have capacity one， all of the edges between rooms and times have capacity one and every possible edge shows up in here。

😡，Between times and proctors， again， all the edges are there。

 but some have capacity zero and some have capacity one。

And now what I'm looking for is a maximum flow。😡，In this， well。

 actually this isn't an optimization problem， is it it's it's a decision problem。

 I just actually it's just a construction problem I want。😡，To schedule an exam for every class。😡。

So how do I do that， yes？啊嗯。Just please。佢 my。Yeah I suppose that's true we need to every class gets exactly one exam。

 so you're right， I really should put a capacity one on the class vertices as well。Thank you。So okay。

 I build this graph， I compute the maximum flow， what do I do from there？😡，Yeah。Wait。

 so if the value of the maximum flow。😡，Is equal to n the number of classes。😡，Then we know。

That we can decompose this flow with value n into n flow paths with value1 each。😡。

And that means we're going to get a valid schedule。If the value of the maximum flow is less than n。

Then we immediately know that we cannot schedule。😡，An exam for every class。

Now it actually asks for the schedule itself。😡，So when we compute the maximum flow。

 if it has value n。😡，Then we decompose that flow into pads using the decomposition algorithm because this graph is a dag that decomposition will not have any cycles in it。

 so there's no random stuff to take out。And then every path that we get in that decomposition。

 we can transcribe as the classroom time and proctor。Or an exam。Okay， so。I'm going to。

Take this stuff。Because we're going to look at this。Later。And put that here。We got a thing okay。

Aapacity one。I'll fill in the details of the the notes later， so the the algorithm is。

Construct the graph G。Compute。The max flow。It's called that F star， max flowing G。

If the value of F star is less than n。Return false。Um，Otherwise。Decompose。F star into paths。

And write each path。As。ATupple for the exam。Yes。The bottleneck here in terms of running time is obviously the max slow algorithm。

at this point， if I want to analyze the algorithm， I need to go back to the original problem statement and figure out exactly how many edges and how many vertices there are。

So that I can write the running time of the algorithm in terms of those things。LetSee。

 what did I that I actually。Yeah， so if I， I， if I do this。In the end。

 I'm going to get something that runs in order n cube time where n equals the total input size。

So if you remember， the input size consists of an array for every class storing its enrollment。

 an array for the room storing their capacities in this two dimensional array showing when proctors are available。

So order EV for that max flow turns out to be orderette and cubed。Yeah。Could scratchch。Of。

So if were in how many additional proctors they would need to hire， so we need to。

I need to be a little bit careful about how I would set that up。So。Just to be concrete。

 let's suppose that the problem says there are additional proctors who are available at any time。

 so there are no constraints on the additional proctors。

 but they're more expensive because they don't have any constraints。Um。

So then probably the way I would want to solve this。

Isn it using maximum flows but using what are called minimum cost flows？

Where you associate a cost with edges and how much does it take to pump one gallon of water through this pipe？

In addition to capacities and then have the special proctors down below with additional cost edges。

And the given proctors as having everything else is zero cost。

And then asking for a maximum flow with minimum cost。Okay。

 so we haven't talked about Min cost flows yet， but we'll get to that next week。把I发老。

I want to make sure that each class has only one exam scheduled for it。我咗 edge中加先。

Has capacity one day。I didn't say anything about capacities on the edges from S to source。

 so if I don't say what the capacity is， I assume by default the capacity is infinite。So for example。

 the capacities of the room vertices are also infinite。

I'm allowed to have any number of exams in this room。😡。

Just they'll all be at different times in different classes。So this is this is， you know。

 if I want to be absolutely sure that I'm being clear。

 I could actually write you know infinities here， but if you don't say what the capacity of an edge is。

Then I'm just going to assume that it's infinite， likewise with any vertex。Okay。So。

There are other questions that show up， if you look in the textbook， you'll see other questions like。

There's a committee that needs to be set up and you have to have so many people from this department and each department of the same number of people of each rank in the department and then what each faculty member can only be in one。

You know， one of the committees that's that's one of these flow problems or I have a bunch of degree requirements that I need to satisfy。

 so each degree requirements is a set of classes I need to take classes that allowed me to satisfy these requirements but I'm only allowed to use each class to satisfy one requirement。

That's again， one of these twople selection things。Okay。

So the art in this is all in figuring out the order that the resources need to be put in so that the constraints only go between adjacent things。

Yeah。It's really。Its pretty。Yes。So sometimes it happens that the ordering is ambiguous。

Like there are constraints between these three things and there are constraints between these two things。

 but somehow nothing in between is constrained。You just set it up these three。

 those two and connect them with a bunch of infinite stuff。

But if you're given a problem where the constraint graph is more interesting。

 it has a cycle in it or if it has branches。You're looking at an NP hard problem。

 So you're probably going to end up either。Like。If you really had to do this in the real world。

 youd probably throw it at some interger linear programming solver。

Which works remarkably well in practice。Yeah。Very brief overview how this would be done。

 like implemented in the real world， like how。Well， I mean， the data would be given。Like this。嗯。

I mean， maybe I'm I'm not sure I understand your question how was it actually done？

So I don't know the details of the Cornell algorithm because in particular that business about each student I want to minimize the number of adjacent exams。

 that's a much more complicated constraint than the type we have here。😡，And I'm almost， no。

 I'll just say it， I'm absolutely sure that the problem that the Cornell people solved was NP hard。

And so they didn't actually solve to optimality， but they in particular at Cornell。

 people are very good at coming up with。Algorithms that are both provably good in theory and。

And observably good in practice。At getting almost the optimal answer。嗯。

So there they probably implemented something like an ILP solver。😡。

But specialized to the problem at hand so they can get very close to the answer that that the NP gods would give but。

嗯。So it might have been the difference between their algorithm would reduce the number of adjacent exams by 40%。

Whereas the NP gods might have reduced it by 45%。All right。Yeah。So。Look at the time here。😔。

We do one that's a little bit。呃。Sure了。De jointint path cover， Okay， so let's suppose I have a dag。

I'llJust fill in my favorite dag here。I don't actually know if this is my favorite dag。

But it's the one I have。So here's a dag。嗯。So I'm giving a da。4。

Obscure reasons I want to find a collection of pads。😡，That cover the deck。Now。

Previously we found sort of the disjoint path problem。

 that's what's often referred to as a packing problem I went to fit as many things in as I can without getting any collisions。

Here I'm interested in sort of the complementary problem it's a covering problem I want to use as few things as I can to cover all of the hertices。

 So specifically what I'm interested in is finding a collection of paths like these two。

That cover all the vertices。But have no vertices in common。Okay， so。

Let me give you a typical version of this problem that shows up on homeworks and exams。😡。

But not this semester。I have a stack of envelopes。Every envelope has a certain height and a certain width。

I want to put envelopes inside each other。But I can only do this if the envelope I put inside is smaller than the envelope that I have on the outside。

 so no tars envelopes。And the envelopes are pretty close together， so if I put one envelope in there。

 I can't squeeze another envelope beside it， I can just nest it。😡，So， you know， given an envelopes。

Each with height。HI and a width。WI。We can put。I inside J。

 if and only if the height of I is less than the height of J and the width of I is less than the width of J。

Um。Nest the envelopes。Into。As few。En thelos。As possible。So I've got 100 envelopes on the table。😡。

I to put some envelopes inside other envelopes。So that in the end。

 maybe I've only got five envelopes on the table each with more envelopes inside them。

 right so I've made five nested stacks of envelopes。So what's the correspondence here。

 well under the hood， there's a dag， there's a node for every envelope and an edge between one and one envelope and another。

 if I can put the second envelope inside the first。A path。

In that Dg corresponds to a nested sequence of envelopes， one inside the next。

A single envelope can only be involved in one of these stacks。😡。

But I want every envelope to be involved， so a stack of envelopes corresponds to one path。😡。

But these paths have to be disjoint。Because I can only use an envelope once。

And what I'm trying to minimize is the number of paths， that's the number of stacks of envelopes。

Okay， but。You know， phrasing it is an envelope problem。Um。啊。Let's say this do。Nested。Ss as possible。

Prasing an envelope problem maybe makes it more concrete， but this is a very general problem type。

So this is a flow problem。😡，But it's not a flow problem in that graph。喂。😊，In fact。😡。

It's a matching problem。What I'm trying to do is I'm trying to assign to each envelope。😡。

What envelope I put it into？😡，I'm trying to assign in the more abstract sense for every vertex。

 I'm trying to assign its successor in whatever path contains that vertex。😡。

The number of pads is equal to the number of nodes that don't have an assigned successor。😡。

Every path has a last vertex that last vertex doesn't have a successor。

So minimizing the number of paths is the same as minimizing the number of nodes that have no successor。

 which is the same as maximizing the number of nodes that do have a successor。😡，Okay。

 so I'm trying to match。Nodes。In G to their successors。系。Another way of saying this is for each node。

 I want to select its successor。😡，So this is a tuple selection problem where I've got pairs instead of Dtups。

I want to assign each node a successor。😡，So these words。Match， select， assign。😡，These are red flags。

😡，These are words that suggest that what you're doing is going to really under the hood be some kind of matching or tuple selection problem。

Okay， so。嗯。A pathath。So every path has a last vertex。With no successor。

So minimizing the number of paths。Is the same as maximizing the number of successors。So。嗯。

How do I actually want to set this up， what is the graph？有。喂。Right。

So I'm going to build a bipart graph。I' call this G prime equals v prime E prime。U。

The prime is L Union R。 L is a copy of。V and R is a different copy in V。Okay。

 so for the example graph here， I had six vertices， so one， two， three， four， five， six and one， two。

 three， four，5， six。The edges of this graph G prime。Correspond to the edges of my original graph Gs。

 so if I number these。I'm not going to draw all of them。

 but so vertex1 has edges to vertex 2 into vertex 3， so in the bipartite graph vertex one will have。

Edges to vertex 2 and vertex3。Vertex 2 has edges to 3。

 four and five so in here vertex2 will have edges to 3，4 and five and so on so。E prime equals E。

I think it really almost the right way to say this。For every edge from U to v in the original graph。

😡，I'm going to have an edge from the left copy of U to the right copy of V in this graph h prime。

He prime equals。You left the right。Yeah。Wherever U to V is aned in E。Yeah。

Now what I'm looking for in this graph is a maximum matching。Okay， so I need to find a max matching。

Nng prime。嗯。This maximum matching is going to give me successors。In G， which now gives me paths in G。

Um。So that gives me the minimum number of vert texture s pads that I want to find。

 so for the envelopes that gives me the minimum number of stacks envelopes that I can build by nesting。

啊嗯。The in particular， the number of paths。That I get in G is going to be equal to the number of vertices in G minus the number of edges that the matching。

So the running time to compute the matching。😡，Is B prime E prime。

 but I need to re associatesociate that with the parameters of the problem I was given。

So for the abstract problem where I'm given a graph G。

What is this running time in terms of the original graph that I was given？What's V prime？2 V。

 what's the E prime？E， so in this case， it is kind of trivial。But if I look at the matching problem。

 I'm given， say， N envelopes。😡，With various sizes。Now。What is the？

So if I reduce it to the path cover problem， V is just n one node for reversetex。😡。

If I open that black box and push through the reduction to the matching problem。

 now v prime is equal to 2 n， I've got two nodes for each envelope so in this case know V in this case is n。

What is E？Sorry。It's， yeah， I mean， I suppose。😡，You could say it's at most entries too。

Because for every pair of envelopes， maybe one could fit in the other， but it can't be both ways。

Or it could be that this envelope is wider but shorter， and so neither one fits together。

So at most and choose two， which is the big O glasses at most end squared。So。

This is big of and cubed。P nestesting envelopes。Right。😊，All right。

Let me give you one more example of this kind of reduction and then we'll be done。

 this will be relatively relatively simple， I hope。So let's say we're given a directed graph。G， not。

A da。timeme。And I want to cover the。The edges。Of G。With cycles。So this is the cycle cover problem。

So what I'd like to do is partition the edges of the graph。嗯。Into subsets where each subset。😡。

Corresponds to a directed cycle。Now， these cycles are allowed。To share vertices， that's okay。

 but they're not allowed to share edges。This is a flow problem actually this is a flow problem in more than one way。

 but this is a flow problem that。We can solve by doing a kind of reduction that we've seen today。So。

Can we describe this problem in a way that uses one of these verbs？😡，Yeah。Okay， but remember。

 we're not given the cycles。😡，So we want to match things that were given together to build the cycles。

😡，Yeah， match， something that starts at where like cycles and all that。嗯白。Well， okay。

 so you can match vertices to outgoing edges。😡，So， like。So I think you're on the right track。

 but say that again with no pronouns。a path that okay， so again。

 I want to phrase this in a way that I'm matching or assigning things that I'm given I'm not given those paths I'm just given the graph。

Yeah。Okay， well。I want to match edges to vertices， so。Every edge。We'd sit only one vertex。

So somehow I want this whatever matching assignment to tell me， you know， here's a red cycle。但是。

I'm going to match successors， but I'm successors of what？Breach edge in the graph。

I want to choose a successor。For that edge， it's on the same cycle。Okay， so。Or each edge。

I want to select。It's successor。On the same cycle。Every edge is only going to get used once。

So if an edge is red， that means it lies I mean I'm not given the coloring。

 but at the end of the day when I've computed everything， if an edge is red。

 that means it lies on the red cycle， which means it's followed by one another red edge on the same cycle。

😡，Okayy。So what， what。What do I do at this point yeah？The cycles are edge disjoin， so I'm required。

Yes， sorry。I should have written that into the problem statement。I did it in the example， but。

Sorry about that。So what graph do I build？😡，嗯。But。可以。我没。Okay。

 so I have a bipartite graph where each part has a complete copy of the set of all edges。

Of the original graph。And I have an edge in this graph that I'm building。😡，Between。第啊。

The vertex on the left that corresponds to the edge U to V。😡。

To any vertex on the right that corresponds to an edge leaving V。😡。

So there's an edge here in the bipartite graph H。😡，It looks like an H。

 if and only if the head of the edge corresponding to the vertex on the left is the same as the tail of the edge corresponding to the vertex on the right。

Okay， so V equals you know edge union edge。You know two copies。And E prime is。You to v。E2 W。

For all U to V and the E to W in my original edge set。睇。😊，I need to compute a maximum matching。

And in fact， I don't really just need to compute a maximum matching。

 I need to compute what's called the perfect matching。

 I need to match every edge to its successor on the same cycle in order to get a cycle cover。

But the way I do that is that computer maximum matching and I make sure every vertex was matched Okay。

 so the running time of this algorithm is V prime E prime。😊，Which is what？In terms of my original。

In terms of my original graph。是。So。Z prime is the most， well， it's exactly2 easy。

The two get swallowed up by the Big O。But what is E prime？嗯。How many edges are there in H？

I'm sorry well， okay。NumbNumber of edges， well first of all。

 it's at most e squared that's one way of saying it because there are e vertices on the left of H。

 e vertices on the right of H and any edge in H joins some pair so。😡。

Previousrily there's the most e squared edges， but I can do a little bit better than that。Yeah。

 so in fact， E prime is at most e times V。😡，So for every edge in G。😡。

The number of edges that can follow that edge in the same cycle is at most the out degree of the vertex with that first edge。

Ens。And that degree is less than V。So。This is e squared v time。Yes。我 be good because say action。

Partition， is it because that we want them actually join to set on further next station。

So the question is why did we why did we partition the edges instead of the vertices at least one way that I think about this is。

😡，I have no constraints at all about how many cycles go through vertex。😡。

So there's no natural next thing for the vertex to be associated with that's going to be sort of globally consistent if I had said pack as many vertex disjoint cycles in there as I could。

Then I would be looking for a successor for every vertex。

 and then I would build a vertex by vertex bipartite graph。

But because I don't have any constraints on the vertices。

I'm looking now for a successor for every edge。Okay。😊，We are done for the day Oh yeah。

 one last question。啊。到到。Yeah的。Oh， so what does it mean not to have a perfect matching。

 it means there is no cycle cover。😡，What you'll get is a collection of edges that define some cycles and possibly some paths becausetices some edges don't have a successor。

The Dg。Oh， I know， in fact that this this does have。😡，Well， okay。

 so I'm not looking for a perfect matching here， a perfect matching would mean every edge has every vertex has a successor。

 and I know that's not possible because sinks don't have any successors。😡。

But it's possible that I might end up with some pads that have zero edges in them。Okay， we're done。

 thank you， happy to answer more questions up front。房子。

Isn't there like an empty hard problem on some vertex subcom finding a。



![](img/753bc7cf3b0263e2f42fda5c8dc77342_6.png)