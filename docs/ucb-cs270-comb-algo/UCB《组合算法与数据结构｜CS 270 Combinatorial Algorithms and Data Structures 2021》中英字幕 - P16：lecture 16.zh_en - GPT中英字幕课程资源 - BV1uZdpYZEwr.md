# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P16：lecture 16.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

Okay。

![](img/a02555c11ebb04213a365990a9eb45bf_1.png)

Thank you it's been the messed up。嗯。😊，Thank okay， so now we'll clear on this with physical in a little bit more and talk about effective resistances。

So， you know， given a register network and you know what an effect resistance is。

 it's the if you if you replace this network， let's say you look at A and B。

 the effect resistance is，If you had to replace this network by a single register。

 what would that be， what would its value be？Okay and there are standard ways to calculate this by formula using series。

 you know， resistance in series and race in panel， but effective resistance is basically what is the effect resistance between A and B that you see and you can。

You can compute this in two different ways， one is you could say。

 okay I'm going to drive one unit of current in and out。Okay， and ask。

 what is the energy dissipated in the network？Okay， so RFf。Effective resistance between A and B is。

 you know， is the energy。Of one unit。Of current。You know from。Going into a and coming out of B。李永别。

Okay， ultimately， you know， it's also the potential difference if you send in one unit of flow into a and how to be right it's also the potential difference。

These effective resistances have very nice properties that relate nicely to random walks and so on。

 so that's what we'll see now Okay so firstly an obvious fact about effective resistances。

 which follows from the fact that it's the energy dissipation。From here。

 an obvious corollary is that。Adding edges。Can only reduce effective resistance。Why is that true。

 well we already saw that electrical networks， electrical flows tried to minimize the energy consumption given a particular incoming and outgoing flow okay and so if you add an edge。

There are more flows that you're allowing and more the space of all flows is larger。

Therefore you're minimizing over a bigger set， so therefore your energy energy of your minimum energy of the flow is going to decrease。

And therefore， adding edges can only reduce effective resistances。Okay， so。诶。

And these effect instance satisfy many properties， but I guess the one key thing we'll see first is how they connect to random walks。

 they are very beautiful connection to random walks。Okay， so。For that。

 let me define this thing about associated with random box。The hitting time。What is the heating time？

Theres a definition heating time。You to be。Is。The expected time。Taken by a random walk。

Starting at you to hit week。Do一 tree。Okay， and so it's a， it's a。

It's a directed quantity HUV is the heating time。From you started you and what's the expected number of steps before you reach me？

And the reason it's directed is you know there are clearly many examples where HUV and HV are very different。

 for example， if you have a clickique here。And you have， let's say this is your you。

And this is your V。HUv is large。Because if you started this vertex U and you do random walk。

 you'll get lost in the click for a long time before you decide to actually go to B it's a good chance that happens。

But HVU is really small because can be small because if you started V is a very good， you know。

 where will you go， you'll come to you at first right。So therefore HU and HVUR。

Really could be very different Okay and and you know will see that computing hitting times is very closely related to solving lap plus systems and it's also related to effective resistances and so on so。

Okay。So let's see what the theorem that I want to prove。

So here's a theorem that relates hitting times and effective resistances。Okay。In every graph。

The hitting time from U to B。Plus， the heating time from v to u is equal to 2 m times the effective resistance from。

Between you and B。And this thing is also called， I think hitting time from U to V and hitting time from V to U is also called commute time because it's the time that you started you。

 expire your time you start at U， go to V and then you actually come back to V。你琴日。とい。Okay。

 so but this is theorem， it relates hitting times and effect to resistances。It has a nice， very nice。

 elegant proof and you know， let's just see it。Thanks， so what is M here。

 M is the number of edges in the graph。Okay， so。What's the。主。Allright， so。

So we look at a few different electrical flows and we'll mix combine them to get this theorem so firstly。

Look at this。Electrical flow。See your graph this I'm going to draw my graphs at every node I I。不是。

A flow of。系。Can you push a flow of D at every node eye。Kty one。

Going to node one and so on Okay and then I of course I need to take out the flow somewhere so I'm going to take out all the flow at a given at a particular node let me call that node V。

At the node V， of course， even at node v， there is we already pushed。DV going in， right， so。Okay。

 now what is the total incoming flow， it's equal to some of these D Ds。

Where I should say these Ds are the degrees of the nodes。Deges of nodes in my graph。Okay。

 and if I add up all the degrees， I'll get the two times the number of edges。

So I need to take out that much flow， so that's what I'll do at node V， I will send out。2M。

M is a number of edges。Okay。So this is my boundary current。

 send DI and every node and take out  toM at Norwe。Okay， so。Here's a first claim。The claim is。

For every node。If pick any node U in the graph。Okay， then actually the hitting time from u to V。

Is actually equal to the potential difference from U2B。To。嗯。So， I'm going to use。P for potentials。

 So the potential difference from U to be P U minus P。So this is a claim I'm going to prove this now。

 So on one side， you have the random box。And on this side， you have。The potential difference。

For this particular configuration of flows。So internally it's clear， I mean it's not clear。

 but internally this sort of makes sense because you see that in the way you're driving the current。

 everything is going into V， all the current is going into V and somehow hitting time is measuring what is the chance you reach V or what how much time it takes to reach V so at least there things type check。

But let's see how this proof goes。So。Okay， but firstly， the。Incoming flow ignored you。W do you。Okay。

 this is actually equal to the outgoing flow。Well， what is the outgoing flow？Some overall。

It is u to W。P U， minus P W。系。嗯。Okay， so， you know， since we've been dealing with this P Pw。

PU minus Pw quantities。 Let me just give them a name。 it's actually， yeah。

 it's actually useful to give them a name， So let me call P minus PV as P UV。Okay。

 just a potential difference for you。This is a definition。

So this is another way so this is just the sum of U to w of P U W。Okay， just a short time。All right。

 so this is just K of current cloud。The incoming flow at node U is equal to the flow leaving that nodeU。

Okay， but。Okay， so。嗯。This is actually equal to some over。我的。Norddes v。

So some are all the NorthC to W。off。B。UV minus P，WV。Okay， so this。Like like this is just a。嗯Iデティ。

PU minus Pw is equal to P v minus Pw。Okay。Okay， so where V is our no special node here or v is a special node。

So what do you get here when you get。The first term here doesn't depend on W。

 the sum you sum you go the neighbors， but it first term doesn't depend on W。

 so you'll end up with D UV。Minus。Some overall U2 W。B w v。Sorry。D， U， V times P， U V minus P W。呃。嗯。是。

So if I so on the one hand， you have B。Do you。Is equal to。出来咩。D D U is equal to。Yeah。Okay。嗯。Yeah。

 I'm sorry。 I'm not doing a good job of。う。呃。Presenting this proof。same。Okay。Yeah， in my defense。

 this is， yeah。Yeah。Like this is really like this really starting from once you write down the of voltage law catch of current law here this is really four lines of algebra there's really nothing happening it's just simple manipulation and when I try to explain i'm messing it up but if it didn't get this simplification no worries at all don't the key point that I want to get to is just this equation this equation is nothing but this this。

This equation， simplify。You simplify this equation。

 which is just by in flow conservation at noU and the potential differences gives you when you simplify and get this equation。

Okay， so okay reset， so let's just say let's let's say this is what you get by like these three。

 four lines of algebra， all right？All right， so now the key point is this it looks like a recurrence relation in my potential differences to V。

 I have PUV， the potential difference to V， I've written it in terms of potential difference to from WV if v is my special vertex。

It turns out that the heating times also satisfy potential as a recurrennce relation。

So what is a hitting time recurrence relation， well， what is a hitting time from U to B？Well。

 this is the expected time we started week。ItStart at U and reach me。That's the expected time。

All right， now what happens in the first step of your work？Well， from you。

 you will take one step to one of its neighbors。Therefore， you take one step to one of its neighbors。

And then with equal priority and。Let's say the neighbor you go to is W。Then。Your expected time。

Of reaching V becomes the heating time from W to B。So HUV is equal to one plus。

1 over D times sum over the neighbors， UW neighbors。H w。So I can't suggest use。ok。Right， so呃。

This is just what hit like this is the linear relation to directdirect hitting times the expected time to hit go from U to B is equal to the first step plus one over D times the expected time from going through the neighbor to be。

Okay， that's just and you see that these two systems of equations are essentially the same they exactly the same。

Therefore。What we end up with is PUV is equal to。H you。In the hitting times problem。

 what does do you signify。水。What does DU signify in the hitting times problem？Heating times is。Well。

 it's the expected time it takes to go from， give you started to you the time it takes to reach we like in a random walk。

Yeah， I'm just confused， what does DU mean？Oh what is？

D U or D is just the degree at you sorry yeah D is just the degree at you Oh I see yeah and and so this is just saying that okay from whatex you we take a step and with one over D pro you go to W and if you go to W then you have your expected time is H W and then you add it up over all the neighbors so that's one plus one over。

Do you time， Sir。I see， I see， thanks。Any other questions？Okay， so。All right。Okay。

 so now we're in a good situation， we have related heating times and potential differences and heating times and potential differences when we set up the currents this way。

Okay。Okay， so now order to prove our theorem， which is this sum of the hitting times is equal to the effect resistance。

Okay， so we will just set up a few scenarios， right， so firstly。Okay。

 imagine I send like our our current scenario is， okay， if I send D U。

Where toU is the degree of U D units of flow going in。

There's a DI units of flow going in it eat node I。And then at node V， also there's DI units going in。

 DV units going in at node V。But then we take out two M units and we saw that in this situation column let me call this situation。

 I guess， situation a。Like for this set of in this situation， the potential differences。B。You对。Be有。

In this situation， I'm just going to is equal to the hitting times to be。什 you对。ok。ok， so。Okay。

 what we want right in this theorem for this theorem is we want want hitting time from U to B and plus hitting time from B to U right so you know we。

Create a different situation now where we do the same thing， but we take out the current at U。Okay。

 lets me do the same thing。Send DI units to vertexi。But then I take out all of the current at node V。

Its really not you。Okay， and then you know， just by the same theorem。The potential difference from。

V to you。Now everything is going out of you， so potential B to U in situation B is actually the hitting time from V to U。

Okay， so this is situation B。All right， we want to add these things but。You know it the。诶。Right。

 like when we going to。Add this thing， but before we do that， let's do。Oh。One modification。

Let's take this picture B， and。Reverse all the currents。Reverse all currents。

If I reverse all currents would to end up with。I' in a situation see I draw the picture again。

So now it's just the same picture， but you know， there is。2 m units coming in。And。

DI units leaving at vertexi。So all the flow is coming into vertex U。

And leaving at every other vertex。At every vertex flow is leaving out。

D equal to DJ and2 m units are coming in。 Okay， this is C。 of course， inside reverse everything。

 the potential differences reverse， right so。So， you know， hedge。We do you。

Is equal to the negation of。V U in situation C。好的。But。You know。

 the negation of V potential difference from BTU is equal to the potential difference from U toV。

 so this is P U V of C。对。This proof is quite。😊，Clever and elegant。

 it might be a little confusing at first， but I just wanted to show it because it's so elegant and right。

So we created these scenarios a is just send degree units of float every node。

 take out2 m mode at noded V。B is dig units every node， take take out the flow node U。

And then C is reverse of B。Okay， all right。 so then we have these So we have a relation for heating time from。

U to B and we have a relationship of hitting time from B to U。ok。Okay， and what are we going to do。

 we are just going to add AncC。不是。we can do this because all electrical flows are as we saw as a subspace right so if you add two electrical flows you'll get another electrical flow。

So what happens now if you add AMC？You get hitting time of U to V plus hitting time of V to U。

Ciing time with you to be。Plus， sitting time will be to you。

Is equal to the potential difference from。嗯。The potential difference from U to V in a plus potential difference U to V in C。

え。which is a potential difference in a plus C。U to B in a plus C。So this is clear。嗯。

So HUV plus HVU is equal to PUV。HU V plus H V U。Is P UV of a plus C。 Al right。

 so now what is a plus C， Let's look at what the electrical flow a plus C is。Okay。

 if you look at a plus C in a。You have degree units going in at every node and in C degree units coming out of every node。

Okay， so that means that they cancel the incoming DI and outgoing DI cancel at every node。

Except at UN andV。So a plus C。Looks like a flow。Where you're sending in。

2 no 2 m units of current at U and taking out2 m units of current at V。

That's precisely what a+ C is 2M going in at U and 2M leaving it the green currents don't cancel。

 all the blue currents cancel because they're going in in one situation and coming out in the other situation。

So a plus C is this situation where you're just sending2 m and U and 2 M at me。Okay。

 and now you see that this is precisely how you measure effective resistance。

 how do you measure effective resistance between you and we。

 you send in one unit of flow at you and take it out at we and ask what is the potential difference。

So in fact， P UV of a plus C。The potential difference in this scenario is exactly equal to since you're sending two M units。

Times the effect resistance from between。You doing。Okay， so what we ended up with is。Oh， sorry。

What we ended up with this。This thing H U to v plus H V to U。

Is actually equal to 2 m times the effect resistance。From you。Okay that's the。

The commute time is equal to the effective resistance。It's a very clever proof。

It's actually quite non trivial the equation that you have on over here because。H UV and H V U。

Quite asymmetric quantities。they are not equal and they're different。

And somehow they add up and you have this effect to resistance is a very symmetric quantity。

So right its。The proof had to be clever to get this equality。Once you get it， it's quite nice。

Any questions on this？All right， so you what sort of things are true here？You know。

 like when obvious corollary or an observation is that。The effective resistances。嗯。

Satisfied wrgling equality。Good， this is。Quite interesting， I。To see and the reason this is true is。

Like usings our characterization， the affected resistance from U to B， you know， I guess。

2 m times effect， and this proportional is equal to the。Expected commute time。

Expected time to do the following up thing we started you， go to V and come back to you。Okay。

 that that is。What effect resistances。 So if I look at。Effective residence of Uv。

Plus effect resonance of VW。This is the expected time to do the following thing。

 you could say you go from U to V。And then you go from v to W。And then back to we and back to you。

Right，But this is only one way of。Go reaching UW and coming back。

So this is the expected time of doing this is。Clearly higher than the expected time of just doing U to W and back。

This is great9 to the expected time of just going through U toW by any other way。By an arbitrary way。

Okay， so that's why it serves with the triangleality。Okay， so it's nice。

Whatat is it does this mean effective resistance is a metric on the graph， yeah。

 effective resistance is a metric on the graph okay。I's a metric on the ground， yes。Okay。

 another nice consequence is。You know。Firstly。The way we have defined it。

 the affect residents of every。Pair is utmost。Of every H UVV is at most one。For every edge you eat。

The affect residents。From U to B is at most one。Well， why is this， well。

 because if you have an edgeUV？There is a， I mean， you can think of the graph as there is a direct parts from U toV of resistance one and the rest of the graph。

Will only decrease the total energy consumption。It could exist by monotonity of resistance。

 effect resistances or monotonity of energy， total energy consumption， as you add more edges。

 the energy consumed by the electric flow reduces。For a fixed so if I fix one unit going in and one unit going out。

Then。Yeah。With just this edge， energy consumption is one and whenever you add an extra the rest of the graph one by one。

 it only goes down， so therefore effecteration on every edge is at most one。

What this implies is the HUv plus HvU。I actually we said is 2 m times the effect resistance。

U2 be and this is at most 2 m。So this is nice， so this is aimed between any graph。

The expected time it takes any any graph and any pair of vertices， U and V。

 the expected time it takes you to go from U to V and come back。Is at most two times then。

Last time we talked about analyzing random walks by using these power method， essentially the matrix。

Just understanding the distribution how it evolves over by each step that works out neatly if you have a regular graph through an irregular graph it gets a little bit more messy。

 but here you see that it's this is just true an every graph whether it's a regular or irregular。

That given any pair of vertices， the random walk goes from U to B and back to you in at most 2M steps in expectation。

Okay， and what that means is， for example， in any graph G。嗯。Like the if I started a vertex U。

 the cover time， the time it takes to cover every。Every vertex， the cover time。

The expected time by which you reach every node。In the graph is at most2 m times n minus1 because you could say。

 okay， I started you， what's the expected time that I you know reach V and come back。know。

 and then you say， what's the expected time we go from V to V1 and come back？

And so you just have you get use the same bound n n times and you get 2 m times n minus1 So in any graph。

If you start any node， you just walk in 2 m times n minus1 steps you reach。So。

 the expected time by which youll reach every node and come back is 2 m times n0 minus1。

Is that most expensive？Okay， so that's nice so we got these coronaries out。Okay。

 so I guess I have another 10 minutes， I can tell you。The relation between effective resistances and。

あ。Spanning please。And。So the reason this is n minus1 here is you started some node and you just think of starting at node12。

3， fix a particular order， one to n， what's the expected time that's if you start at one that you go to two and back and then from two to three and back three to4 and back and n minus one to n and back and you add them up that gives you the expected time that you cover every node in this particular order。

 one to2，2 to  three，3 to and then back。So。That's why it gives it throughout medicine。Okay。

 so so let me tell you about。The relation between effective resistances and random work。

So the All and spanning please。Okay， so if I give you a graph， given a graph。You know。

 we have a natural distribution of spanning trees， which is a uniform distribution of spanning trees given a graph G let mu sub G be the uniform。

Distribution over spanning trees of the graph。Okay， and。

This is a really nice way to nice characterization of electrical flows in terms of uniform distribution of spanning trees。

嗯。Okay， so here's the characterization， suppose you want to know。嗯。Okay。

 suppose is's a graph and you're sending one unit of flow at U and you're taking it out at V。Okay。

 you want to know how does the flow get routed inside the graph？Okay， here's a way to calculate that。

嗯。Pick。AUform spanning tree。Take uniformly random spanning3 T and in the spanning tree。

 there will be a path from U to B。So suppose this is the tree。Okay， you route one unit。From U to B。边。

re big。ok。So let's call this flow， I mean this this is just a park it's not really a flow but it says through naive it's a very simple flow's just one unit along going on this path that if I call that flow F sub T。

Okay， then if I average this overall all possible choices of my spanning tree。Expectation T F sub T。

This is actually the electrical float。That routes one unit of flow from。

Electrical flow that takes one unit。From you doing。

So it's really an average overall all possible spanning increase， uniform average。

And uniform because all our resistance values are one。

 if you have different values of resistances on the nodes on the edges。

 then you will have a more different distribution or spanning trees but。This has I mean。

 is not that difficult to prove， but let's keep the proof for now。 Okay， so so let's。嗯。You know。

 so so let's。嗯。So let's pretend this is true， right？Okay。

 so they so gives you a very nice characterization and so then this is how electrical flows are now if I want to know the effect resistance。

Between you and me。For an AGUV， what is effective resistance？ok。So。

And the natural way to calculate effective resistance is to calculate the potential difference between U and V in the electrical flow。

This is the potential difference。Between you and me。In the electrical flow。

 right if I send one unit of flow at U and one unit at V， then it's the potential difference。

So let's calculate that。嗯。So if I have the edge Uv。This to。诶。被读。So。Yeah。So by by O's law right。嗯。

Potential difference between you and me， right so。So。So let let's so。

Right so what is the potential difference between U and V or what is the current on UN andV in each of these flows right？

Uv。Is in the treaty。Okay， then of course the flow will just send one mi from U to B right。

 so then the flow F sub T of Uv will be one。However， if U2 be is not in the tree。

Then there won't be any flow going from U to E。Direct on the on the edgeGV， they don't very flow。

 because every time。You pick a tree， you route the flow only on the tree on the edges of the tree。

 therefore if U is in the tree， you have one unit of flow going there if U is not in the tree then they have zero units of flow going there。

Okay， so therefore， you will get a contribution to the potential difference only when Uv is in the。3。

 and you get no contribution of the price。 So therefore， you will get。That the total。

 the average over all these flows， the potential difference the quantity is。

The average of these flows is basically the probability that Uv。Is in the tree。

The probability at Uv is in the three is equal to the potential difference。From you doing。

Are these any trees or just or spanning trees oh these are spanning trees Wait is UVv and edge or is it a path U is a U is an edge？

UV is an edge， so if the edge Uv， I should say yeah。I say if Uv is in the tree。Then， you know。

 you will send one unit of flow from U toB directly okay， on that on that edge。

 you'll have one unit going。Okay， if Uv is not in the tree。

 then you have zero units going on the edge UVV， so the flow on the edge UVV is actually equal to the probability that UVv is in the edge in the tree。

RightAnd therefore the potential difference on the between points U and V in the actual electrical flow is actually equal to the flow going on the edge UV times the resistance of the edge。

 which is1， so you get probability T that Uv is in T is actually equal to the potential difference。

 which is actually equal to the effect resistance from U toV。

So that's so the probability that an edge in the graph belongs to the tree is actually equal to the effective resistance of the edge。

Okay， so the reason this makes sense is imagine you had like a very complicated network。

 but let's say you have an edge like this。O呃。probably the effective resistance between U and V is actually one。

It's also clear every spanning tree that you pick will pick theGV。

 therefore the effect essence is one。But if you had other path。

 then there are some spanning trees that don't pick the HUV。

 so the effect resistance drops and the probability that UV is in T also drops。做。

So effect is equal to the probability that an edge is in the random span tree。Okay and so this again。

 you know， we you know can derive many， many things like it has lots of properties but like for example。

 some over the effective resistances of all the edges。Because every three has exactly n minus1 edges。

 and every time you pick a three you have exactly n minus1 edges。

 so some of these probabilities actually could n minus1， so therefore it's n minus1。In a。嗯。Yeah。

 and you know， the whole world of things over there sort of scratching the surface。So today。

 I just wanted to give you a little bit of tour into electrical flows and effect resistances。

And so on next class what we'll do is we'll go back to electrical flows and we'll go back to the original problem of computing electrical flows。

This question of projecting onto this subspace。And that will lead us to this question of lapplian system solving lapplian systems。

 and we'll hopefully see a nearly near time algorithm for。Solving La plusian systems。

 which is very useful for many other problems like computing Max flows and so on。Any questions？

could you go back to the last slide， like the last page？So so诶 you said that the。

Effective resistance from U to V is equal to the probability the edges in the tree so what if like the edge is not in the graph like there's no edge in this particular graph but you can still have an effective resistance between two frequencies right like is there an analog to like this in then that case I guess。

😊，Yeah， actually。 I don't know for succinct expression in that case。 Yeah， I， I mean， the， I mean。

 there is an analog in that。Let's I mean。We are picking uniformly I mean this gives you a general way to calculate any electrical flow you want right doesn't matter if you want to compute any electrical flow。

 pick a random of spanning tree and route the flow in the tree。Okay， that gives you electrical flows。

嗯。But now， what， how do you infer the。Effect relations between。Arbitly pair vertices in the graph。

Yeah， I don't tell。 I don't know， actually， yeah。嗯。I don't know how to do that using trees。

I guess the。I mean， here we were able to do that because。We wanted to estimate the。Thank。

I guess we were able to estimate the actual flow on the HGV。

But as equal to probability that UVv is in the tree。嗯。Yeah， otherwise。

 I don't know if a succinct way to say what it is， but it is really just this the potential to you know。

 the electrical flow if you want to calculate any electrical flow。

 pick around the spanning tree and route it on that and then average overall your choice of spanning trees that gives you the electrical flow。

Of course， this is not efficient because sampling a random spanning tree is tricky hard。Yeah。

 thank you。Thank you， Professor。

![](img/a02555c11ebb04213a365990a9eb45bf_3.png)

嘿。

![](img/a02555c11ebb04213a365990a9eb45bf_5.png)

Hi， Pra， can you hear me hello and let me stop recording。

