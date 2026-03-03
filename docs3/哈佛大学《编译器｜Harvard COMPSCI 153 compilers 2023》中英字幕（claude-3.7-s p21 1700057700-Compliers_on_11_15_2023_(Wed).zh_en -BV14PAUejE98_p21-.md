# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p21 1700057700-Compliers_on_11_15_2023_(Wed).zh_en -BV14PAUejE98_p21-

Maryland。你。It over right。Okay， so how many get into that？Let's go upwards。

 how many think minimum color？No good everyone understands the problem。

 Who thinks three is the minimum number of colors needed。

Who thinks four is the minimum number of colors？All right， let's。Look， it is for。

 as I said before class， the four color theorem says for a plain a graph at most four colors are needed。

 Let's see why it has to be at least four。 So let's look at the West Coast California and Oregon。

 let's just pick arbitrary colors for them。 doesn't matter which two we pick。

 That means that Nevada has to be blue。😊，Since Nevada。As blue in Oregon is green。

 Idaho has to be red。Arizona。Over here has to be green。And now we have。Which state？Uah， uah。

Utah can't be colored any of the three colors we've been using red， blue， green， we need four。So。

Why is this the preclass puzzle we'll get to register allocation later today in the lecture and also in next lecture and we'll see how graph coloring ends up being part of the way we're going to approach register allocation。



![](img/8f39a81cca67cc60d83b4d5710ef822e_1.png)

But before we get there， announcements， homework 5 is out great。

 you've got a little less than two weeks to work on it。

 Home 6 is this is another overlapping homework homework 6 is do on Tuesday。

 December 5th It's going to be looking at data flow analyses and optimizations which we will'll finish covering today。

 so I'll actually I may release it。😊，As soon as it's ready to go。

 which might be today definitely by Monday at the latest。

 optional and Home6 is going to be register allocation。

 you can optionally choose to implement a register allocation algorithm if you do。

 then you can enter a leaderboard where we just have some test cases a test suite and you try and do as well as possible on the test suite。

Compared to clang。I will say everyone is going to be able to use up to three late days worth of late minutes for homeworkwork six。

 so you should not worry about running out of late minutes that I appreciate it's a little tight at the end of the semester with us。

With this homework， if you're feeling。Any sort of time pressure or time crunch。

 feel free to reach out to me about it。Alright， Any Eddmund questions。Okay。

 so today we're going to wrap up data flow analysis and then start talking about register allocation。

So if you recall， we were looking at data flow analysis， laveness analysis in particular。

 and we had a pretty straightforward algorithm where we essentially set up these equations。

We such that we would start it with a really bad approximation of the solution。each iteration。

 we would go through all of the equations for each node。

 we would go through the equations and essentially try and make those constraints。

 those equations satisfied。And keep on going until we encountered no more changes。

 and we hand wave the fact that we would always terminate and that by starting with the empty set as the initial guess。

 we end up with the smallest possible sets we could。So the question is。

 can we do better than that simple algorithm？So one of the key things to note is。

There was only one way that information propagated。Between nodes， right。

 so one of the equations just kind of for a given node， propagated information from the out。

The set of variables that were live immediately after the node propagated that to the set of variables that was live just before that node executed。

 but the only way that things actually propagated between nodes was with this equation。

Where we look at all of the successes event。So in prime， successes are in in the control flow graph。

And look at the set of live variables just before N prime， union those together。

 and that was the set of live variables immediately after N so we're propagating the live variables backwards in the control flow graph。

So what that means is if the。Inets of a node successor didn't change。

Then out of in is not going to change。Meaning that。

There's no need to revisit the equation that propagates out of in to in of in。

So an idea for the improved algorithm is that we actually keep track of which node successes have changed。

And then only。Revisit their equations if the successes have changed。

 meaning that we might have additional information to propagate。So he is an algorithm for it。

We use a first and first out queueue of nodes that might need to be updated。So that's W。

 so we see everything initially to 0。We initially put all of the nodes into the work queue。

And we repeat until W is empty。 We take the next node off of n。We essentially perform the equations。

Updating from the successes of N， updating from out of N to in of N。And only if。

The live variables just before N executes changes。Do we add the predecessors of N to the work list？

Okay， so what this means is it's only win a node。呃。Something gets added back to the work list。

 only F。嗯。At least one of his successes change。We can of course be a little smarter。

 we can check to see whether something's already in the work list。Before we add it back in。

 we can be a little careful with this initial work list。

 instead of putting all nodes in in an arbitrary order， we might want to do it in a particular order。

And so on。 But this is the basic idea that we're going to have a work list of things that。

Might have changed， and we only put things on the work list when the equations might have changed。

Okay， any questions about this mild improvement to the algorithm？O。

So we've been looking at this idea of data flow analysis motivated by liveness analysis。

 the set of variables which live。 we'll see some uses of that analysis， both。

Later on in lecture today， but also in the homework assignment6。

You'll be implementing a liveness analysis and implementing optimizations。

 including dead code elimination， which uses live variable analysis。

But this idea of data flow analysis applies to more than just labness analysis。

 There's actually a whole lot of other analyses as well， including available expressions。

Reaching definitions， alias analysis， constant propagation。

Let me talk through a few of these analyses to kind of understand what they are and then see how they would also fit into the state of flow framework。

So available expressions。The idea is an expression E is available at a given program point P if。

On all paths from the entry。🤢，Of the function to program point P。

 expression E is computed at least once。And moreover， between that computation。Of a。

And program point P， there's no assignment。To the free variables of E。

The idea is that if he is available at P。Then we don't need to recompute the expression A。

So this is useful for common sub expressionpression elimination。

If we find out that an expression E is available。At a program point where E occurs again。

 that means we already computerd it。

![](img/8f39a81cca67cc60d83b4d5710ef822e_3.png)

And so we might be able to。Weuse their computation。So again， this is the definition。Of what we want。

 the idea of when an expression is available。If we had that information。

You can hopefully see how it would enable us to implement common of expression elimination。

But the question is， how do we actually compute this？

How do we compute the available expressions at every program point？

So let's give this clear in our heads with an example。Okay， so here is a control flow graph。嗯。

We're going to compute this information starting from the entry of the function。And moving forward。

 So whereas with laveness， we went。Backwards， we propagated live variables backwards from the out the in with available expressions we're going to go forward。

 So we start off at the beginning of the function。 There are no expressions that are available。Again。

 the program points will be considering are just before and just after nodes。

 so just before this basic block， this instruction， no expressions are available。

Right here after x is assigned A+ B， the expression A+ B is available。Now， in the analysis。

 we might also be recording which variable it's available in it's in the variable X。

 but for our purposes， we'll just think about what expression is available。



![](img/8f39a81cca67cc60d83b4d5710ef822e_5.png)

Okay， after the next instruction， we're going to have both a plus B and a times B。



![](img/8f39a81cca67cc60d83b4d5710ef822e_7.png)

Available。Again， propagating that information forward。

From the out of that basic block to the in of the next basic block。嗯。

We're performing the comparison way greater than A。So at that point we。

We'll ignore the computation of way greater than a。

 we're only going to be considering expressions available assigned to variables。

 but you could imagine another analysis or an intermediate representation where way greater than a is also an expression that's available。

Okay， probably you're getting the information forward。Right， now at this point。A is assigned a plus1。

 So what's that going to do to the available expressions。

 What are the expressions are going to be available immediately after this。None of them。

That is correct， why is that？So once you're change the value of A。

 these are no longer valid right once we've changed the value of AAA。

The previously computed value for a+ B is no longer correct with the current version of a。

Why isn't a+1 available？Hey。Again because we like assign a over and depends on itself Yeah two steps that is valid for like a hot cycle and exactly right a plus one。

 yeah， we computed it， but then we immediately modified the value of a so you know we have no variable that is storing the expression a plus1 that we computed。

😊，So nothing is available after that。Proropagating forwardd x equals a plus B。😊。

A+ B is available there。Now we have。We modified the available expressions right here。

 so we actually need to propagate that information along this edge。And actually combine it with。

The information that was previously there。 So previously。Coming into this node。

 a plus B and A times speed was available on this edge。Coming in on this edge。

We have A plus B available。So now what's going to be the available expressions immediately before this mode？

So it's going to include a plus B。Is it also going to include a time speed， William？No， right。

 because we've edit it it。Right， so what's interesting is on both of these edges。

The expression A plus P is available。 So that means no matter how you get to this node。

 A plus P is going to be available。But eight times B。😡，Isn't going to be available on the edge。

 so we end up taking the intersection of those two sets。

Right and now we have only a plus B available before that， so we changed this。Information。

 we kind of need to propagate that change， so we're going to modify what's available after that expression to also be just a plus B。

Same thing here， we need to modify that to VA+ B。And now at this point， we're actually stable。

In the sense that。If we propagate this on， A+ B is available。Proroppaate it through this instruction。

 we get nothing available。So the information at this program point didn't change so we know that we don't need to recompute from that point onwards if we're kind of simulating the work list algorithm in our heads。

So this is the result of the available expression analysis on this example。Okay。

Any questions about that？Yeah， in this case， these wouldn't open any doors for optimizations。

 not that I can sleep。Correct， we've done the available expression analysis to figure out which expressions are available。

 which program points， that information would then feed into。Subexpression elimination。

 common sub expressionpression elimination， and you right in this example。

 which was nice and important to demonstrate the data flow analysis。

 there's no opportunity to replace a computation of A+ B。😊，Great。Okay。

 let me give you another algorithm， another data flow analysis， reaching definitions。

So as we've talked about， a definition of a variable V is when the program assigns to the variable V。

And we say that a definition of the reaches program point P F。

There is a path from the definition of V to P。With no intervening assignment to V。Right。

 so that is where。When we think about when we use。A variable V。

 we might be interested in which definitions can reach it。Okay。

 that is which assignment their variable v might be the assignment that gives us the current value through our use of V。

So this information would be helpful for that。Saying at each program point P。

 what definitions reach that program point？And so that this additional this information would then let us very easily figure out if I'm at a program point where we use V。

 which definitions could reach it。And。You might imagine。From that information。

 we might get to things like。Dead code elimination if I have definitions that don't reach any uses。

Okay。So。All of these these three data flow analyses that have presented with you。

 they're computing different things。Some of them are computing information backwards。

Some of them are computing at Fords。But they offered and within a general data flow analysis framework known as the Gen Kll。

Analysis framework。The way you can think about it， all of these analyses。

Is that they're computing facts that hold true at each program point。

N of n is the set of effects that hold immediately before n。

 out of n is the set of effects that hold immediately after n。



![](img/8f39a81cca67cc60d83b4d5710ef822e_9.png)

![](img/8f39a81cca67cc60d83b4d5710ef822e_10.png)

Each instruction you can think of as generating some facts。And killing some facts。

 So for the liveness analysis。It generated。

![](img/8f39a81cca67cc60d83b4d5710ef822e_12.png)

Anything that was used？Any variable that was used it in。



![](img/8f39a81cca67cc60d83b4d5710ef822e_14.png)

That generated additional waveness information。And any variable that was defined in got removed。

 right， it killed that information。The analyses we've talked about died on which facts they were computing。

Because they differ on which facts they were computing。

 which facts were generated or cud at a particular node was as specific for that analysis。

As I mentioned， they differed on whether there were forwards or backwards， a Fors analysis。

 you kind of have the information at the end of N immediately before n and you propagate that information forwards。

To then compute out of in， the facts that hold true immediately after in。

 by contrast to backwards analysis computes in of n using out of in。

These analysis is also different in how they combined information。

 We sometimes call this a May analysis versus a must analysis。In a must analysis。

 we're computing facts that have to be true。Meaning that when we have incoming sets of facts from multiple edges。

 we'll take the intersection of them， they have to hold true on all of the edges。

By contrast in a May analysis， we're interested in information that may be true。

And we'll be taking the union effects on incoming edges。

So if we think about the three analyses we've looked at very quickly， liveness。

 reaching definitions and available expressions。We can kind of characterize each of them。

Within the data flow， within the GenQ data flow framework， what are the facts they're computing。

What are the gin and kill information and are they fors or backwards？And are they may or must。

So looking at laveness， we're computing the set of variables that are alive。



![](img/8f39a81cca67cc60d83b4d5710ef822e_16.png)

We generate the variables that are used it in， we cool the variables that are defined it in。

We're propagating from。Out to in。So we're going backwards。The gen set is the use of variables。

 the kill set is the definition of variables， and it's a May analysis we're taking the union of facts when we combine them。



![](img/8f39a81cca67cc60d83b4d5710ef822e_18.png)

By contrast reaching definitions， the set of effects are。😊。

The variables that are defined and can reach that program point。



![](img/8f39a81cca67cc60d83b4d5710ef822e_20.png)

The gen set。Is the node in， ifN defines the variable we're interested in。呃 it。

Kills a fact if it defines a variable。

![](img/8f39a81cca67cc60d83b4d5710ef822e_22.png)

嗯。AN defines a variable that it removes the reaching definitions that were flowing through it。

It's a For analysis and it's a May analysis right so can。



![](img/8f39a81cca67cc60d83b4d5710ef822e_24.png)

From the in information we're computing the out information， you'll note that it as a For analysis。

 it has a very similar form to laveness， except we swap the roles of out and in。



![](img/8f39a81cca67cc60d83b4d5710ef822e_26.png)

But the idea of taking the gen set union。诶。The input minus the kill set。That structure still holds。

Available expressions， facts are expressions that are available。

 the gen set is the expressions that are evaluated。

 the kill set is expressions that contain a variable that gets defined by the node right those are the facts that get removed。

 it's a forward analysis。 So given the inset we compute the outset。And it's a must analysis。

 so we're taking the intersection of the facts。Any questions about this idea of this gen kill framework and how these three analyses fit into it？

Okay。So this is a pretty general framework。 There's actually a lot of analyses we can phrase as Gen Kll and you can imagine that you could implement a Gen K data flow analysis。

 simply instantiate。A few parameters， is it forward or backwards， what are the gen sets。

 what are the kill sets， and bang you'd be able to very quickly instantiate， for example。

 these three different analyses。Unfortunately， not every data flow analysis were interested in fits into the GenQ framework。

嗯。One of them is constant propagation。Another one is alias analysis。

We can come up with a more general data flow analysis。That fits not only Jen Kill。

 but also some of these other analyses。Let me lay out for you as a Ford analysis。

 but the same idea works with a backward analysis。The idea is that we're computing some data flow facts。

 right， We're going to phrase that as a set。L。Of possible things that we're computing。

So L here might be。For reaching definitions， L would be instantd with。The set of definitions。

We have a flow function for a node in。That is it takes the information that's true just before the node。

 returns the information that's true just afterwards for a gen kill analysis。

 this flow function would be expressed using the gen sets and the kill sets。

So it fail as the incoming information。The result is the Gen set union L minus the kill set。

We have some kind of combining operation， so when we have multiple edges coming into the same node。

 how are we combining the information on those different edges and the GenN kill framework based on a may or a must analysis that operation would either be set union or set into section。

嗯。So if we generalize the Genki framework to this。Essentially abstracting out what the combining operation is。

 allowing sort of arbitrary flow functions。We can express an algorithm for this state of flow analysis in a pretty similar way。

We're going to initially set the in and the out。

![](img/8f39a81cca67cc60d83b4d5710ef822e_28.png)

Values for all nodes to some special value Here， we're calling it top， which is going to be。



![](img/8f39a81cca67cc60d83b4d5710ef822e_30.png)

If you will the maximum amount of information。Right。嗯。

We the maximum amount of information and let's say enables the most optimizations。诶。

We then have a very similar algorithm where we can simply iterate over all of the nodes repeatedly until there's no change。



![](img/8f39a81cca67cc60d83b4d5710ef822e_32.png)

Computing， using the flow function to compute to propagate information from the beginning of a node to the end of a node。

 combining information from。

![](img/8f39a81cca67cc60d83b4d5710ef822e_34.png)

The predecessors， there's a typo here， sorry。This should be n as in the success and nodes of N prime。

嗯。So the basic idea of the algorithm is the same and all we've really generalized is how we combine information。

From predecessors and then how we compute information for a particular instruction。

So to see an instantiation of this， let's take a look at the constant propagation analysis。Okay。

 so the domain that we're going to be using。The set hour from which we're drawing values is given by this Hasy diagram。

嗯。Li more specifically actually。The domain of things we're going to be computing is actually a map from UI to。



![](img/8f39a81cca67cc60d83b4d5710ef822e_36.png)

Symbolic constant。 So UA， we're going to be computing this for every single variable， local variable。

 the each local variable， it's either going to be not a constant。

It's going to be a constant equal to a particular value I， like constant zero。Constant one。

 constant negative one and so on。

![](img/8f39a81cca67cc60d83b4d5710ef822e_38.png)

Or it's going to be undefined。 There's no information for that variable yet。

So we're able to represent this。The symbolella constant as a lattice。

 a Hesi diagram over here on the right。

![](img/8f39a81cca67cc60d83b4d5710ef822e_40.png)

Where。We're going to initially be essentially for each UID starting it undefined。



![](img/8f39a81cca67cc60d83b4d5710ef822e_42.png)

And moving down in this lattice。If we have constant information， we know it's equal to a value。

 a constant 5， fantastic。 We can store that information If we have incoming edges that says the UA D4 is equal to5 on this branch and 7 on this branch。

 that means。😊，At the mergerch point， it's not constant。So we combine that information to be noncons。

We can make this vegan tuition more explicit with a flow function。Where， for example。



![](img/8f39a81cca67cc60d83b4d5710ef822e_44.png)

呃。If we have a。A node that's assigning， let's say，01+02 into a UID。

And M as our map from UIDs to symbolic constants， the flow function is going to update the map。

To replace UI with。

![](img/8f39a81cca67cc60d83b4d5710ef822e_46.png)

The result of reasoning about that instruction，01 plus O2 in this example。So for O1 plus O2。

If either the opera end01 or R2 is not constant。Their01+02 is also not constant。Right。If。

Either of them is undefined， like0102 hasn't been assigned to yet。

Then the result of 01+ O2 is also going to be undefined。The nice case for us is。If both O1 and O2。

 according to the incoming map， both map to constant values， let's say I andJ。

Well then we know that the result of 01+ O2 is going to be a constant。The constant i plus J。

For constants K rather， where k is equal to a plus J。嗯。

And so here we're very succinctly saying in our flow function。

How we're going to update the map for the UID we're updating based on。

Essentially how the instruction will take constant values and compute results from it。嗯。什么的。🎼あ。

All right， so the flow function here was defined in terms of this。



![](img/8f39a81cca67cc60d83b4d5710ef822e_48.png)

Semantic operation for instructions， they kind of said。Hey theian， for this instruction。

 if this was the。Information， the map about constant values。Of inputs， what's the。呃。What's the？

Is the result of this constant or not？Allright。In order to implement this。

 we needed to be able to interpret an opera end with respect to a。A map。

 so that's what these later bullets define。

![](img/8f39a81cca67cc60d83b4d5710ef822e_50.png)

嗯。If the opera end is null throughout our purposes， we're going to treat that as non constant。

If we're only interested in tracking integer constants。If it is a literal integer。K。

 then it's going to be a constant K。If it's a UID， it's going to be whatever the map says for that UI。

 where it iss constant， non constant， undefined and so on。Okay。

 so this is defining the flow function using a couple of helper functions。

An interpretation operation for instructions and interpretation operation for opera。

To instantiate the framework， we also need to specify a combining operation。 So in particular。

 if we have two maps from UIDs to symbolic constants。When we combine that information。

 we have to decide how to combine them。What we're going to do is to point ways to join on these maps using。

嗯。Letuce meat。Essentially， so that is， as I mentioned， if we had two incoming edges， one edge is。



![](img/8f39a81cca67cc60d83b4d5710ef822e_52.png)

The constant is equal to the UID P is equal to0， another one that says the UID is equal to two willll combine those to end up saying that UID Fu is not a constant。



![](img/8f39a81cca67cc60d83b4d5710ef822e_54.png)

If had zero on one branch， two on the other。It's definitely not always equal to zero。

 it's not always equal to two。Any questions about？The constant propagation analysis。

The idea of what is computing and how we're instantiating it for。Using this framework。Okay。

 one more data flow analysis。This is when you'll be implementing。Alias analysis。So诶。

The idea here is to figure out whether。A UAD， a local variable that is a pointer。

Whether that pointer might be alias。😡，That is whether there might be another value out there in the program that's also pointing to the same location。

嗯。

![](img/8f39a81cca67cc60d83b4d5710ef822e_56.png)

So the domain we're going to use is again going to be a map。😊，From UIDs。

 this time to symbolic pointers。The symbolic point is there's going to be three possible values。

 again， undefined。Meaning we don't know any information about it。Ha hasnn't been defined yet。



![](img/8f39a81cca67cc60d83b4d5710ef822e_58.png)

Unique， meaning that this U I， the pointer in this U I is。The only pointer to that memory location。我。

There may be an alias out there。The flow function。嗯。



![](img/8f39a81cca67cc60d83b4d5710ef822e_60.png)

So defining a flow function for the UID equals instruction operation。We'll again。

 break it down by cases。That is if we。Have a UID that is equal to a newly allocated slot。



![](img/8f39a81cca67cc60d83b4d5710ef822e_62.png)

Well， allocating that slot， this is a new piece of memory。Conceptualally， right。

 we'll end up implementing it by having a piece of memory on the stack。

But at the semantics at the LLVM level， you can think about this as allocating a new piece of memory。

Because it's new， nobody else points to it。So what that means is immediately after the allocation。

 percent S， sorry， UADS is a unique pointer to that location。So the flow function reflects that。

The flow function for load instruction。 So we're actually going to a memory location and loading from it。

 We're concerned with point of values here。 So we now have a value that we took from memory somewhere。

We have no idea if it's unique or not。Right who knows who else might have that same value。

 the person， maybe there was a piece of code that stored the value in there and is still retaining that value。

Maybe somebody else has read from the same location previously。

What it means is when we load that load of value， load a pointer from memory， it may be alias。

All right， so we reflect that in the flow function。With a store。It's kind of similar if we stored。

If we stored the UAD T。😡，Into a memory location。Someone else might read that location。Right。

 and use it。So we're going to update T to now maybe be alias。

Even if T was beforehand a unique point of that memory location， that point of value has now escaped。

 if you will。We don't know who else is going to be using it。So we update T to B。

To indicate that it may alias。And you can go through other instructions and figure out the appropriate flow function for them。

 the appropriate transfer function。嗯。When we combine the information， again。

 we're going to be doing pointway。Pointwise is on the two maps。

We're going to use meat in the let as well， so that is。



![](img/8f39a81cca67cc60d83b4d5710ef822e_64.png)

诶。If something。If our information on one branch says the UID may be alias and the other one says it's unique。



![](img/8f39a81cca67cc60d83b4d5710ef822e_66.png)

All we can really conclude is that the pointer may be alias。

So we're always moving downwards in this lattice。Okay。Any questions at the moment about what？

The alias analysis is computing。Or why it's useful。Yeah， I guess I'll ask the why she school。

Why do you think it might be useful？What would Alias if you knew？That you had a UID。

To a location that was。So you had a pointer that was the only pointer to a memory location。

What kind of things would that let you reason about？I guess maybe you can like。Pre straight。

You can read the value whether or not they value their changes or not， great。

So let's say you did a load from F。AUAD food。Then let's suppose we did a store。Through the UID bar。

And then we did another load from food。Are those two loads the same value？There was a load from food。

 two loads from food， but there was an intervening store。Through the pointer stored in the UI bar。

Now F is a unique pointer。I know that Bar is not alienliasing it。😡。

So that store that happened to Bar could not have changed the value in the location point2 by food。

That would allow me to realize that， aha， those two。

Loads are going to give me the same value and I can remove one of them。

So that's an example of the idea where knowing。That expressions do not alias each other。

 allows me to perform optimizations。Yeah， is it possible to get like more specific than just saying like something might be alias like in your example if we know thatlia's not Yes。

 it is possible to have more precise information here we are just talking about whether a local is unique or may alias。

 you can actually imagine a more sophisticated analysis that could actually figure out。Well。

 which expressions？May alias each other， so even though the pointer in fo may not be unique。

Maybe we're able to reason about the fact that it's a least。Only by the UID Bz。

 so when we do a store through bar， okay， we know that bar and food do not alias each other。Right。

 so you can imagine a more sophisticated。Domain。That we're working on instead of saying undedeef unique maleallias。

 maybe it's something like what is the set of expressions， the mayallia set？

With the bottom of the lattice being some unknown set of expressions may alias。

And that might allow us to retain precision。In some cases and still be able to realize that。Hey。

 these two particular expressions don't alienlia each other。And enable optimizations。There's also。

The data flow analyses that you'll be implementing that we're looking at today and that are commonly used and compilers are all what are known as intraprocedural analyses。

 they examine a function in isolation。There are also analyses that consider。An entire program。

And so there are analyses where you could look at the whole program and try and understand what expressions might alienlias each other in the whole program。

Perhapsps to enable optimizations across a whole program or perhaps to reason about properties that the program might have。

 such as no use after free。Right， even if。The free happens in a different function。Yeah。Oh sorry。

 is that a follow up otherwise William had a？VeryQu I was going to say， so for the vote language。

We can。Like we you can do this get element pointer thing where you can like find an element past like and in there you can use that to like get a pointer to something past the end of the array because you don't。

check the link to the right when you get point right so an operation on that e you could make it alias anything。

呃。So there is get element pointer in LOVM。And that is the thing that ends up being translated to pointer arithmetic。

At the assembly level。 And right， if you have arbitrary point or arithmetic， you can end up。

Constructing arbitrary pointers。One of the things， though， is。嗯。Modulular。Lentths of a race。

Get El pointer will actually make sure that you're getting a valid pointer。

RightBut you might get him on point it doesn't actually check for the length of an array。嗯。

If you remember the computation model。That we used。

 the interpreter we used for LOVM back in homework three。

You can think of about that as being undefined at the LOVM level。Right。

 and ideally and you do want to avoid that undefined behavior。

if you end up allowing that undefined behavior in the programs you execute， yes。

 you run into problems。But essentially what's going to happen is your semantics at the language level don't hold anymore。

And so we know that this happens right with buffer overflows and sea。😊，Arbitrary things can happen。

You can't actually rely on the source program as written to be what's going to be executed。

If you end up encountering and exploitding that undefined behavior。So yeah。

 depending on how defensive you want to be in your compiler。

 you want to do things like check or array Bo。Before constructing point to them。

Thanks for bringing that up。Well maybe two questions， like one， if you know the pointer is unique。

 can you get rid of the pointer entirely？In the sense that。

Or maybe I'm still thinking about this at the source level what if you have like a corner tonight。

Right you？So if you have a unique pointer， can you get rid of the pointer， it depends so definitely。

嗯。We're just about to talk about register allocation and one of the ideas might be。诶。

You can imagine an optimization where if I allocated a stack slot。

But I'm able to reason precisely about that allocated stack slot， I only have unique pointed to it。

 you can imagine that that might be something you end up pulling into a register。

 I don't need to use the memory location for it at all。

So you can imagine a local analysis that uses unique could actually reason about when you could。

Get rid of that tax law。嗯。A lot of the time， let me think about this a bit more。

And clearly if you take an address of something and。If moved somewhere else， then you couldn't。

Get rid of that memory location。Because somebody。Took the address of it and passed that in as an argument to another function。

 for example。嗯。So。It depends as the answer， but yes。

 that is one of the optimizations that might be enabled being able to。嗯。

Lift that value from the memory location to somewhere else。Okay。

Any other questions about data flow analysis？Okay， because we're now going to transition。

Into register allocation， so a different topic。flowlows very smoothly because we're going to be using that liveness information。

But it is a big transition here。All right。So。Register allocation problem。

That we want to be addressing， that we want to be solving is that given an。

Program and an intermediate representation。They use an unbounded number of temporaries。Okay。

 so this might be the UIDs and an LLVM program。What we want to do。

Is find a way to map those temporaries to machine registers。So， that。

The program semantex is preserved。The behavior of the program is still the same。

We want to as much as possible use registers， registers are really fast。

Much faster than accessing memory。So we want to use registers wherever we can。

We don't want to do pointless moves between registers right why move from register one and into register two？

And then use register two， I don't I just use the value for register one。

 right so avoid those needless moves。We need to make sure that we have calling conventions met。

 so certain registers are used for specific things。 so when I call a function I might be putting。

The first few arguments into specific registers， so in our use of registers and our mapping of temporaryor registers。

 we need to respect that。Okay， so that's our goal。It may not be possible to put all of the UADs into。

😡，Into registers， we might have only key registers available and many more temporaries that alive at the same time。

 So we are going to need to spill。Some of these temporaries to the stack put them in memory locations。

Okay， so this is the problem。We're going to look at ways in the rest of today's lecture and Mondays of solving this problem。

Any questions at the moment about what we're trying to accomplish？O。Well， let me give you。

A simple solution to it。That。Works okay。This is called the linearar scan Reg allocation algorithm。

 It's essentially a greedy strategy。First of all， let's assume we've had the liveness information computed。

 Okay， so for node in live out。Of N is the set of UidDs that alive immediately after。嗯。

After that node。Let's suppose we have some set of usable registers。

 we're going to call that set PAL short for palette。

 we'll see why we're going to be treating those thinking about those registers as colorss sometimestime soon so we have a palette of colors。

It's the usable registers， so when we're doing this register allocation we might actually be reserving a couple of registers。

😊，To let us handle the spill code， that is。Putting values into a stack slot。

 reading from a stack slot， we need a couple of registers to store the address。

 get the value from that address and so on， so a lot of the time the available registers we have for register allocation don't include all of the general purpose registers。

What we're going to do is maintain a layout， a map from UIDs to locations。The tell us。

For every program point。 So at every program point， we're going to have one of these maps。

The map for that program point will tell us， for this UI D， Where is the value for that U AD stored。

 It might be in a register。It might be in a specific stack slot。Okay。嗯。

What we're going to do is scan through the program。For each instruction that defines a UID X。

We're going to。Look at the registers。That are currently in use。So by that， I mean。

Let's take a look at all the UADs that are alive after this instruction。

That is the UIDs that might be used later on in the execution。Let's go to the map。

And see which of those UIDs are currently stored in a register。Those are the registers。😡。

The container value that might be used in the future， we don't want to use one of those registers。

What that means is the set of available registers for us is the set of。Possible registers。

 our palate。Minus the set of registers that are currently in use。If no registers are available。😡。

That's bad。Right，It means we don't have a register available for us to store the value we just computed。

 What we're going to do is simply store that。UID in a stack lot。Okay， so in a new stack slot。

We just defined x， we're going to store it in a stack slot。Hopefully we're in this other case。

But we do have at least one register available， in which case we're going to use that register to store。

Then newly defined UID。So this algorithm is greedy， we're just kind of going through。The program。

 if there is a register available， let's use that register to store the new UID。

We're not really thinking hard about what's the best possible use of these limited resources。

 these registers， which UAs should we store in registers， instead we're just greedily。

 if there's an available register let's use it。Okay， so we can solve the problem。😊。

As in we are using all the registers we can。We're going to make sure that our semantics are preserved for every UID。

 we know where it's going to be stored， either in a register or in a stack slot。

 so you can imagine that from there we end up generating assembly code that。

Reads from the register or loads and stores from a stack slide。Any questions about this algorithm。

 Linea scan？Yeah so just to clarify like the live out。から教て。Live out could have like a bunch of UIDs。

 let's say， more than the number of registers， right？Yes， yes， so that in that case。

 some of them would also point to slap of tax loss。Yes。Yes， but。Yes。

 there might be many variables that are live out， live after this node。

Some of them might be stored in stack lots。 Some of them might be stored in registers。

 for all purposes， we want to see which ones alive。And stored in registers。

Because those are the registers we cannot use， either any that are still available。Okay。

So we have an algorithm that can solve the register allocation problem。So for homework six。

The code we're going to give you actually has two register allocation strategies。

 one which just spills all the registers， that's essentially what's going on now in kind of our version of the O compiler that we've been building up over the last few homeworks。

And we've also implemented linear scan。Right， so greedily assigning registers。

This is an optional task， but for those of you who are able to start on this early enough and have the motivation。

 you get to try and implement a better register allocation strategy。😊，嗯。Right。Let me jump into。

Thinking about， well， how could we do better than linear scan？In general。

 register allocation is an MP complete problem。How do we allocate inemp to registers？Efficiently。

And effectively。So that's bad news。 But the good news is that。There is actually a heuristic。

That works really well in practice。Tends to be linear。In the size of the code。

 so in the size of the function。This heuristic is based on graph coloring。

And hopefully the intuition for this is clear the problem of graph coloring， as we saw in the prep。

 given a graph。😊，How do we assign one of K colors to each node in the graph so that connected nodes have different colors？

For our purposes， the nodes here are going to be the temporary variables， the UADs。

And there's going to be an edge between two nodes， between two variables。

 if there is some program point where they are alive at the same time。Okay，Cos are registers。

 So the idea is that we're trying to assign registers to。UIDs to Tempes。

Such that if two UIDs are going to be live at the same time， they're in different registers。Right。

Okay， so this。Idea seems pretty intuitive， right， pretty natural fit。

Think about these temporaries as nodes and a graph with edges between them based on laveness information and whether they have to be la at the same time。

 fantastic。 We can just use graph coloring to solve this problem。😊，The thing is， though。

 graph coloring is also an N complete problem。So we've reduced an MP complete problem to another MP complete problem。

How does that actually work？So it turns out that。The。

Register allocation by using graph coloring does not actually directly solve。🤢。

The graph coloring problem， It may not find the minimum number of colors to color a graph foot。

 That is it may actually be doing some spilling， even if there was。

An assignment of registers to UIDs that would not require spilling。What's going to happen though。

 is that graph coloring framework is a really useful and intuitive one for us to think about。

 and we're going to go through some heuristics。😊，That very often allow us to come up with an efficient graph covering that is using our available registers we're able to color the graph。

And ideally， not do too badly in the cases where we can't。Okay。

 so I'm actually going to go through a couple of iterations。

Of register allocation via graph coloring， getting progressively more more complicated in the algorithm。

But let's start off。With an idea。Of graph coloring through simplification。Okay， so in this approach。

Ca Reg allocation， there are four phases。In the first phase， the build phase。

 we're going to create this graph， it's known as the interference graph。Nots of temporaries。

 we have edges between them if two variables interfere with each other。

 that is if they're live at the same time， there's any program point where they both life。Okay。

 so at the end of the build phase， we have。A graph。In the next phase， we simplify。

The idea here is that if there's a node in the graph。That has k minus1 edges where。

K is the number of going to be the number of registers。Then if we。Took out that node。

Would be left with a simpler graph。So G minus n is a simpler graph， it's a graph with one list node。

And if that graph is K colorable。😊，Then so is the graph within in it， right？So that is。

 if g minus n is k colorable， then great。Ass saying cake colours to the notess。

Add back in the node N， and it only has at most k minus1 edges。

So there's the most K minus1 colors that can't be colored。

 so there has to be at least one available color for us to color that with。Great。

So the idea of the simplify phase is that we're going to be removing nodes with degree less than k。

And that's not going to affect our ability to successfully color the graph。However。

 it might be the case that。We get to a point。We've been removing nodes with a degree less than K。

 We might get to a point where the graph has only nodes left that have degree greater than a equita K。

What we're going to do in that case is choose one to potentially spill。

That is if we can't end up doing a k coloring。That's going to be the node that we will spill。

The temporary idea that we're going to store in a stack slot。一。Well that's。

So after we've chosen a node to potentially spill。We get to then continue with simplifyimplify。

That is， we're going to end up removing that node that might need to be spilled from the graph。

Keep on going with Simplify， remove any nodes that now have degree less than k。

So kind of by iterrating between simplifying and spill， we're removing nodes from the graph。

Eventually the graph is going to be empty。At that point， what we do is we start。

Adding the nodes back in in reverse order。And coloring them。Okay， this is selecting。

The colors to put in。If as we're going and trying to color the nodes。If we。

If we encounter a node that we remove through Simplify， we can definitely assign a color to it。

It's got very few neighbors。However， if we get to a node that we identify it through the spill phase。

Maybe we'll get lucky and be able to color it。But it may be that there's no available color。

 in which case we are in fact going to need to spill it。

What we actually do then is we rewrite the program。We rewrite the program to explicitly spill that。

Value to the stack。Read it back in when needed。So what we're actually going to have is a different graph now。

So we actually go back。To the build phase。And build a new graph from our modified program that now has the explicit spell。

Okay。This is a lot to hold in your head。😡，These four phases。 I'm going to walk through an example。

That will make it a bit more intuitive。This example is actually from the textbook by Appel that is part of the recommended reading。

Let's suppose we have a program。We don't really care too much about what the program is。

 but the basic idea is。Let's assume that。Some locals， some temporaries are live out。

And sort of propagated the information back and now these are the variables that are lan， J and K。

 we have laveness information at every program point just by performing the laveness analysis。嗯。

From the laness results， which I'm not showing directly。We want to compute the interference graph。

So here we have。One node for every local， for every temporary。And an edge between the nodes。When。

There is some program point。Where they're live， we both those variables alive。 So， for example。

 here at the end of the program， by assumption D，J and K are live out。

 So D and J are alive at a program point。 and indeed， there's an edge between。D and J。

In a similar way， JN K alive at a program point is an inch between J& K。And so on。 right， So just。

 you're welcome to go and verify this particular take for me that this interference graph。

Is produced by the liveness analysis of this simple program。

Any questions about how we construct the interference graph？Okay。We've built it。😮。

The next phase is simplify。 And for that， we get to ignore the program and just focus on the graph。

The idea is。Let's suppose that we have four registers available to us。

What we're going to do is look for a node that has degree less than four。

And we're going to remove it。And we're going to record in a stack。

The nodes that we've removed because that order is going to be important later on。So。

It's kind of arbitrary， which node we dos， but I pointed out that G is a node with only three edges。

 it has degree 3。Three is less than four， let's remove G， put it on the stack。Great。

 the graph is now simpler。😊，We actually reduce the degree of some of the nodes by removing G H has degree1。

 let's remove it。呃。Okay。Also has degree less than four。So we'll remove that。

Now D has degree less than 4 J。诶。We can keep going E。If is' degree one， awesome。

The s phase phase worked really well。 We were， in fact， able to remove all of。

The nodes in the graph with the s Fa a phase。As we kept on removing nodes。

 there was always some node with a degree less than four， allowing us to remove it。

So the graph is now empty。We color the nodes。In order of this stack。So starting at M， then C， then B。

 so here's the original graph。We're going to be assuming four registers。

 so here are four colors for us to use。嗯。So let's suppose purple corresponds to the Reg T1。

 green to T2， and so on。So we can pick an arbitrary color for M。Say purple， fantastic。

Pop it off the stack。The next one to color is C。Now， because。

We remove these nodes in the simpl phase， we know that they always have a pretty small degree。

 less than four， so there's always going to be some available colour。B is next。

 B is adjacent to yellow and purple， so we need a different colour， green， awesome。



![](img/8f39a81cca67cc60d83b4d5710ef822e_68.png)

Now we have if， if can be。Any color except purple？

![](img/8f39a81cca67cc60d83b4d5710ef822e_70.png)

Well choosehoose green。E。What colors can't EB？Right。Green or purple， great， choose yellow。

 we can keep going。 and the cool thing is that because all of these nodes were removed in the simplifyim phase。

We know that we'll be able to find a colour for them so we can keep on going through。H。Cheee there。

Green， onefold。Fantastic。So we were actually able to color the graph that is we can use for registers。

For this program。And so you can imagine translating from the representation down one level to actually talk about registers。

Using this graph covering， using this register allocation。 So， for example。

 we're going to store G in。

![](img/8f39a81cca67cc60d83b4d5710ef822e_72.png)

![](img/8f39a81cca67cc60d83b4d5710ef822e_73.png)

G green Reg T2。So we can imagine rewriting that and this would be the program rewritten to now use registers instead of the temporaries。

Alsowesome。Hey， we kind of got lucky in this look at this line here， T3 is assigned T3。😊，That's aOup。

 right， It turns out that the variables here got assigned to the same register so we could actually get rid of this instruction。

 this move from T3 to T3。 that's awesome。Okay， so this example worked out really nicely。

 The simplified phase was able to always remove a node with a degree less than k。

So let's try it again。😡，But this time we're only going to use three registers， so the same program。

 the same interference graph。But now we only have three colors。In the simplified phase。

 what that means is we're going to look for nodes with degree less than three and remove them。So， H。

Has degree2， so we're going to remove H。😊，C， his degree too。G has degree two。Awesome。Anything else？

No。At this point， all of the nodes remaining have degree at least three。Okay。So。This is a shame。

 right， It might mean that we're going to have to spell。What we're going to do is。

We want to pick a node。To potentially spill。Now， we don't want to pick a note arbitrarily。

So what would be a good node？For us to spill。Now what does spelling mean。

 remember it means that there's going to be a temporary variable。

Though we might have to store on the stack if we don't happen to have an available register when we get round to coloring。

So what do you think would be properties of a good？Temporary variable to put on the stack， Maddie。

Having a lot of edges， what does it mean if it has a lot of edges？there's a lot of liveness。

 there's a lot of overlap and liveness。 So the hope is that if we spill that variable。

 took that out of the graph。That's going to reduce the degree of many， many of many。

 many other nodes， right， And so hopefully that'll。

Mean that now there's a lot of nodes that are less than degree3。

 meaning we can do our simplify phase and get rid of them So that's a reason why we want to choose a node with a lot of edges。

What's a reason why that might be a bad idea or way it may not work out if we end up choosing a node with a lot of edges？

Nicholas， will it work better if we choose to spell a note of free of the most number all budget。

 like other nodes that we can simplify？So would it work if we tried to？

Spill a node that wouldd free up as many other。Nos is possible。Yes。

 that would be a node with high degree， because if we remove that node with high degree。

 then that's going to decrease the degree of many other nodes。

I guess it may not necessarily be a high degree， like freeing like having one with a high degree may not be like having one that is connected to another node that just needs to remove one incoming algebra。

Oh， so maybe if we look to see， oh here's a node that is almost less than K。

 it has exactly K neighbors， maybe if K could identify a node to spill that would definitely like reduce give me in more nodes that I can simplify away。

 there might be a way to do it。嗯。So in some ways， the idea of like finding nodes。

 which are going to reduce the degree of other nodes。Yeah。

 to maybe high degree notes like live for longer and have more。Your asked to start。Right。

It's possible that。Exactly， he said， nodes with higher degree。

 they're interfering with a lot of other variables。

 and that might be because they have really long lifetimes。

And maybe they have really long lifetimes because they're used a lot。

Which means that if we put them on the stack， we might actually be doing a lot of reads and writes to them。

 which would be bad。But just because it has a long lifetime doesn't necessarily mean that it's written。

 written a lot， Maybe it's written at the very beginning of the program。And red at the very end。

So it's live for pretty much the entire program， but not actually used。Rightい。

So we're actually going to use a heuristic。To do this。So yeah。

 we want maybe a node with high degree or something that will produce other nodes that cause other nodes to go below the threshold。

 but also one that isn't used or defined very often so that we don't need to access the stack much。

So a common thing to do is to compute what's known as the spill priority of the node。

 And the basic idea is。The number of times that it's used divided by the degree of the node。

As a way of balancing it。 And by the number of times it's used。

 if there's a use or a definition inside a loop。Well the loop is going to be possibly executed multiple times。

 so a common way of doing this is let's just assume the loop is executed 10 times。

 so we're going to weight uses and definitions inside loops higher than uses and definitions outside the loop。

If you you can be a little more precise and think about nested loops as executing。You know。

10 to the level of the nesting depth。They're try to approximate how often they used。

So upon computing the split priority。😊，We might then want to。Choose one with。Lu priority。That is。

High degree， small number of uses。Okay， so let's go back to our。Stack。

We want to pick a node that has a small sp priority。 I'm not going to show you the computation。

 let's just say that D。Is the node that we're going to select as a candidate to spell？Okay。

 so we put it on the stack and we market， hey， we might need to spill this。And then we keep going。

 We go back to the simpl phase， and now there are indeed some nodes that have degree less than three。

 so we can simplify away K。JB， awesome， we're going to get to an empty graph。

Whereupon we move into the select phase， that is we're going to again， color the graph。

In reverse order， we're in the popping order of the stack。We have three registers， T1， T2 T3。

 and we start with M。So we color M。 We color F。E。被。Jy。And K。

 we know that those are all going to succeed because they were removed from the simplified phase。

 Now we get up to D。

![](img/8f39a81cca67cc60d83b4d5710ef822e_75.png)

Are we going to be able to cuy？No， there is D and it is neighbors with purple， green and yellow。

 there is no available colour for us to color D， we got unlucky。



![](img/8f39a81cca67cc60d83b4d5710ef822e_77.png)

In the graph coloring we ended up with。We didn't have an available colour。 So we're， in fact。

 going to。Need to spill it。 Now sometimes you do get lucky。😡。

Sometimes as you're going through and doing the coloring。The node might still be colourable。

 in which case we can color it and keep going with the spill phase。

 I'll leave it to you if you end up implementing a Reg allocation to figure out if there's a particular order you should use the registers in that might be likely to increase。

😊，The likelihood of succeeding in coloring。Succeeding in colouring a potential spill node。Okay。

But we got unlucky here， and we are going to need to rewrite the program。

So let me just go very quickly。Sketch this through。I'll go a minute late。

 What we're actually going to do is rewrite the program to now spill。D。

 put it into a stack slot when we use D we're going to read it in。

 so note that we actually introduced a new temporary variable here。

 D2 in order for us to read from the stack slot and use it。Okay。

So we've gone all the way back to the build phase with this new program。 We build a new graph。

 We have D and D2 now。 Okay， so in some ways， what happened was by spilling。

 we split that high degree node into two local variables， which now have different degrees。



![](img/8f39a81cca67cc60d83b4d5710ef822e_79.png)

![](img/8f39a81cca67cc60d83b4d5710ef822e_80.png)

Okay。Then we go back to our simplification stage。It turns out that。

Here we are going to be successful。And our simplify， we do have nodes of low degree throughout。

 we're able to pop them off。In order。Meaning that we'll get up to the select phase。



![](img/8f39a81cca67cc60d83b4d5710ef822e_82.png)

And be able to successfully color everything in。Sorry， I didn't mean for that to disappear okay。

I a couple of minutes over， so'll leave it at that。 We've seen this algorithm， fantastic。 Next class。

 we're going to look at a variant on this algorithm that's more sophisticated and has some desirable outcomes in the coloring。

😊，Thanks very much， good luck with Homes， and I'll see you on Monday。



![](img/8f39a81cca67cc60d83b4d5710ef822e_84.png)