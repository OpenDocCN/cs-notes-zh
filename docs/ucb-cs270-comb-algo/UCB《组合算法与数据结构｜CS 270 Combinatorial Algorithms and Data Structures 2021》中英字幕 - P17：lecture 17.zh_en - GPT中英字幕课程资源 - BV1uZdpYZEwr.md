# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P17：lecture 17.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/732ae2c87e3e67d7696123b0fd134ae0_0.png)

Welcome， welcome everyone。Good to see you all today we' talk about La Phian sos。

Solving the plus and the systems。So just refresh your memory， a lapla of a matrix of a graph。Is a。

It is the。Mattrix L， which is D minus a， where D is the。

Diaagonal matrix of degrees of thequiertices D1 through DN。Is the degrees。And is the dec matrix？And。

We already saw several things about lapplian chigas inequality and spectral of a few results in spectralgraph theory。

 in particular， lapplian is this quadratic form。Which corresponds to， let's say。

 the energy of a spring system。Okay， we saw thisす。All right。

 so what we'll see now is the problem of solving lapplaceian linear systems， so here so the input。

Is a linear system of the form L is equal to B。And their goal is， of course， to find X。

So clearly it's just solving linear systems and we already saw a couple of algorithms for this。

 you know， we can do gaary N or you can try to do some sort of gradient descent。

Die algorithm with them。We we saw this earlier in the course。But。

These laplaianline systems are so ubiquitous in many areas of scientific computation and so on that people actually try to go well beyond Gaussian nation gradientant descent in particular in a lot of when you simulate some physical PDs or let's say flow of heat on a mesh or take an object you。

You discretize it by a grid， you have some object， you discretize it by a grid。

and then you get a graph and then use this graph to simulate run simulation solve partial differential equations on the object and this is very useful for scientific computing and so solving lapplian linear systems is sort of coal that they show up a lot over there and so people have had been trying to come up with very efficient algorithms for lapplian systems for a long time and there are lots of heuristics and real solvers that work on millions of vertices and so on and there's a lot of heuristic work on this problem。

And。So what？I mean， what sort of was another the key。

Result in theoretical computer science on this line was this paper by Spman and Tank。In。

Who got a near linear time solver？And this was nearly near time as in if you have a graph with images。

 this is a。Or tda of the number of edges。Here， Oilda just means that I'm hiding some logarithmic factors。

This peelment tank paper came out in sometime in the early 200s between 00 and 06 maybe sometime during this time and this was a really a remarkable achievement it was the paper was a few hundred maybe 12150 pages long it introduced so many new things into the area like spaifiers。

Spectral pifiers preconditioning lot of different ideas they introduced and they used all of it to sort of。

GoGet this algorithm。 It was a very complicated algorithm because are ran into hundreds of pages and。

Over time， it has been simplified and。Now， there are。

I guess in the last 10 years now there are at least three or four different algorithms which look very different from the original speedment tank。

 but use some ingredients which were first drawn from there。

 but now there are about three or four different algorithms which are simpler。Shorter to describe。

 but this line of work solving lapplian system s systems has been very influential in just algorithms design of fast algorithms so the key thing is。

There are very few things that you can actually do in linear time on a graph。If I give you a graph。

 what are kind of things you can do in linear time， you can run the basic connectivity， bread search。

 bread search。And what else can you do in dealinging your time？You can， I guess cook Gja extra。Yeah。

 there's very few things which were there if you could do kneeling at time。

 this is a new perimeterter that you can solve when kneeling at time as an exceptionally fast。

And for any given graph， you can solve the corresponding lap plusian systems in nearly time。

 and that became like a black box。Which led to fast algorithms for inspired fast algorithms for max flow。

で。There's about multi commodityority flows and sampling。Sampling random spelling trees。

A bunch of combinatoral problems。They were inspired by you or there were new algorithms that were discovered that use this lap plush in solve as a black box。

 it gives a very powerful primitive that you can actually solve in nearly linear time very fast。

 so you use this primitive to get algorithms from max and soil。

And so this led to fast algorithms for Maxlo， for example。Right， so the。On on an undirected graph。

 now we know how to compute maximum flow in near linear near time。

 near linear near time as in the number of edges times polylogue factors。

We'll see the max flow algorithm。Maybe not the nearly linear near time one。

 but an improved max algorithm maybe in the next few lectures。So that it was a major。

ReSort of revolution in that it you it LED to breaking barriers that were longstanding So for。

 you know， if you use Edmunds car， I guess I think the runtime of Edmunds S is。As anyone know。

 I think it's E times week。It's M times n。啊E m v。Edms Cup for maxflow is at times that。

I think that's where it is。So。😊，So， that's the。So that's the that's the context here and so and in fact some of these solving blood plus and drain systems shows that even when you're not trying to actually use them so for example。

 let's say you try to run interior point method algorithms these are。

Optimization algorithms and if your instances are graphs in many cases when you're trying to solve the interior point run the interior point method in each iteration of the interior point method。

 you'll have to invert some matrix which corresponds to some more solving the up plus and linear system。

SoAnd of course， in practice， the plus and image systems are useful for， as I said。

 for simulating some PDs and in fact， that's sort of the place where all this comes from。

People really had worked out a lot of heuristics to get far better than Gaussian nation and gradient descent。

 the knife Bo on gradient descent for this and even now I think the heuristic algorithms really do perform better than all the things that we can probably do。

On real instances， real large instances of this problem。So that's the plan for today。

 the plan for today is we will see sort of most a lot of the major details of a neo linear time solver for blood plus and linear systems。

Okay。Okay， so okay， so we're back to solving linear systems。

 which were doing a while ago in the class。 So let's look at and。

An algorithm for solving linear systems， which looks pretty much like gradient descent。

 but it's a useful variant， so let's look at it。So this is the Kashmas method。So。So for the moment。

 for now， let's forget about Lalaians and so on， we just have the problem of solving a linear system。

Okay。You have a。Some number of constraints。I是。And you saw thisly necessary。

So the algorithm is very simple to describe it's one of the simplest algorithms for solving systems it's a bit like gradient in descent but even simpler than gradient in descent so let me show you how it looks like if you like for example ran it on a plane okay so let's say you have three linear constraints here I've drawn three lines a1 x equal to B1。

A2 x equal to B2 a3 x equal to B3 and you want to solve this linear system in particular you want to reach you want to find the point of intersection right that's what。

You want to do。Okay， so you you want to reach this point of intersection， you start at some point x0。

Okay， and then you。You pick any of your equations that you have and if it's going to be violated。

If it's violated just fix it and the way you'll fix that is just by projecting so。

Let's say you pick x0 and you pick the first constraint here。And you just projected。So you ret one。

And then you pick some other linear constraint and then you project onto that so for example。

 maybe you pick the third linear constraint and then you project onto that。Okay。

 and then you look at some other linear constrain and you project onto that。He。

 and you repeat this process。Depending on you know which linear constraint you you pick。

 you might you know do many you might go in many ways， okay， and that's the idea。

So it's a very simple algorithm you just pick in violated con。

 fix it by hand by just projecting onto that constrain and。

Inote that every time you project you will violate the constraints that you' satisfied， for example。

 you look at x0， you move to x1 because you want to satisfy constraint 1。

 but then you project onto to here x2， which but x2 violates constraint 1， which is just fixed right。

诶一。Yeah， but intuitively it does seem like you are moving towards the point of intersection of all the constraints right and it's quite easy to see that we'll do that so。

So let's， let me write the。Algothm here， what you do is you start at some point x not。

And you pick a constraint。AIx is equal to gi you fix some constraint and you project it you fix by fix the fix the issue with that constraint by projecting so。

You know let me just write the formula for the projection and then we can verify that it's correct。

So xt plus1 is xt。pl。B i。Minus。EI。In the product X。Times AI by。n比。squ。

I claim that this is a formula for the projection。We can derive it also。

 but it's easy to just check it。Well firstly you are moving in the right directions right so if you look at xt plus one minus xt right it's a multiple of。

いや。Multiple of the constraint AI， the vector AI。 So that's basically saying that you are moving in the direction normal to the hyper plate。

 That's what projection should do。 This direction should be a1。 this direction is。え three。

And so on right so the direction is right Okay and then the only thing to check is you're moving the right amount of distance on the along the direction that you can just check by just compute a AI in a prototypet D plus one。

Okay， that will be AI inapper textt。Plus。You canIt will be B minus EI in the Protex t。

And then AI in a I is normmii squared， so you get normmii squared。By know me square。

And we check that this is actually equal to BI。So as you expect we the new point satisfies the constraint that you just projected on so the formula is right it's going the right direction。

 the right distance。Okay。Okay， so that's good。Okay， so now we have the formula and you know。

 what one can show about this algorithm is that if you have any sequence of。

Constraints or if you have any infinite sequence of constraints such that every constraint in your original system appears infinitely often。

You will converge the sequence of Xts will converge to the solution。Okay， so that's。sortrt of a。

Asymptotic statement and it really depends like if you fix any particular ordering。

 let's say you say I want to do A1 A2 A3 a and then repeat A1 a2 A3 am then actually proving its convergence or analyzing it becomes very subtle and trickyy。

Today we look at a randomized version of this where we'll pick a constraint a violated constraint with the basin a product distribution okay。

So。So here's the randomized version。So this is a randomized kshms。Okay。

 what is randomized customers well the I'm going to pick。The constraint AI in a cortex。

With probability。This probability specifically chosen for this， you know to work out nicely。

 we'll see how why it works out nicely， so you get norm I squared divided by the sum of the norms of Ya squared。

Okay， effectively， you pick a constraint with probability proportional to its square of the two norm。

Okay， so constrained as larger coefficients we begin with higher productivity。

And random and then you just project xt plus one is equal to like the projection onto that constraint。

The project extend into it。By this formula。Okay， so that's so this is a randomized algorithm now。

 And now we can analyze this algorithm， okay so。Let's see how to analyze this。So， you know。

 the analysis will be a little bit reminiscent of you know。

 things like things we've done in the past， it look a little bit like gradient and descent。

 which it should。Thank you。Yeah。Yeah。And。嗯。Right so this choice of probabilities is something that is geared for just our own application that we have in mind today。

 you could pick other things and you'll get different kind of bounds。Okay。

 so let's try to analyze this， so here' is an identity that I'll write down directly。

We have done this often， so you look at the distance to this actual solution。

 suppose x star is the actual solution， you can look at xt plus1 minus x star。Okay。This is。

Xt minus x start。Minus。AI in a product Xt minus X star。And。You know。

 we don't worry about the formula too much and I'm also I mean you can derive it very quickly and let's。

Just。See what it says。This is the key kiding。Okay。So。With。Yeah， I bar。Is equal to AI by nomihi。Okay。

And how do you derive this formula， you just substitute the update rule that we have。

 and you use the fact that AI in a para text star is equal to BI。诶い。ussing。

AI in a correct X star is equal to BI。Okay， so okay。

 so what's the nice thing about such a formula is you get often get this when you're minimizing your quadratic function or gradient descent your distance to or your vector your distance to the。

True and solution。Is your current distance to solution multiplied by the matrix？Okay。

 and this matrix is。You can see that it's identity minus。AUn vector， unit vector transpose。 Okay。

 it's actually。As you can expect， it's a projection matrix。

It's a projection matrix identity minus you transpose and in some sense。

 because you're multiplying the thing by a matrix less than the identity。

 you are shrinking the vector every step。But how much issing depends on how correlated your current。

Xt minus x star is with your current constrain AI。Okay， so that so this is what we have now。

 so let's。All right， so now I mean now let's just analyze the randomized algorithm。

 this is just deterministically true for every step， for every choice of step。Now。

 let's look at you know。The distance to optimum further randomized algorithm。

 So let's so if I look at xt plus 1 minus x star。Whole squared。Okay， what is that？喂。It's the。

Length of this vector， identity minus AI bar， AI bar transpose X T minus X star。ho squ。Okay。

 this is just what it is。So， you know， this matrix is really projecting out a particular direction AI bar。

Okay， so if you take a vector and project out a particular direction the length will decrease by exactly the projection onto that direction。

 so in fact the length square here will be。The original length square。

Minus the projection onto this direction， which is。嗯。EI bar in a product X T minus x star。

The whole is great。奇た。OkaySo far， this is just true for every step， every update。Okay。

 so now we have a randomized algorithm， so let's just stick in expectations。

So expectation over the choice of my constraint is expectation of the choice of my constraint。

And here。没 get。This is expect。是。Expectation over the choice of my constraint。Everywhere。Okayright。

 and then。So the first term is， again， is in independent of the。Constrained that you pick。

 So it's x0 minus x star。ho squ。The second term。You know exactly what probability you pick every constraint。

 so let's just write down that probability。So some or I， we decided to pick AI with probability。

Even by。This， this is the probability where you know。

The denominator is just short fbinnous norm of the matrix a。

 which is the sum of squares the two norms of the vectors。Yeah， that'요。The constraints that you have。

Okay， that's the innoator。All right， and then this times。Oops。Okay。

 that's the projection on that direction。So。Okay， so you know。We said AI bar is the unit vector。

Along AI， now you once you put back the length in， it would just become。Yeah。

So we have something nice here's some。Let me write down this as one over the Frrobinus normal phase squared。

Times sum over I of。AI in aberg X T minus X star。We call it squared。

Okay see this is where the choice of probability makes a huge difference。

 This is an expression it's very simple to analyze this expression here， this is just the length of。

A times xt minus x star。RightBecause some of squares are the coordinates。Ex too。

So you substitute that and let me just write down what I get。Xt minus x star。

Wuhole squared times 1 minus。one over。The Frvinian no。With he square。Times。This quantity。

Something that looks like the operator norm of8。I mean， it is， I think， the operator normal。嗯。Okay。

 so。就诶。The expected square distance in the next step is actually the original the current distance times something。

 which is one minus bh Okay， let's call this the minimum value of this b to be。加爸。

C of a this is as usual if you whenever you analyze an algorithm which is iterative like gradient descent or for these things。

 you end up with a parameter that depends on the like the condition number and the eigenvalues of this matrix that you are working with as opposed so here we have some number which depends on the matrix。

 which is K of a。Okay， let's call that cup coffee。But it's actually， okay， sorry。

 I should say it doesn't get depend on the just the matrix because I have Xt there。

 but let's ask what is the。Smallest value this thing can take， let's call that cup coffee。Okay。

 so copper of a or copper squared of a， but just to keep things。

 K squared of a is the smallest value。So I have a Frrobinusn。Smallest value are all vectors。

Of the two norm of A z squared divided by the two norm of c squared。纪历。Thiss some parameter。

And so we have our analysis now， you know， we have expected。呃猪农。

Squared is actually the original tuum squared。Times 1 minus ka squared of a。Okay， and then you know。

 you know how long this will take each time you are multiplying by this factor less than one so after so you converge。

Converge within epsilon。And in time， which is like。And。In time， which is order。

 you would want to go1 over kappa squared of a。Times log of1 hour epsilon。

Or log whatever the original distance was time stepspson。对。If you want to be very precise。

 you can say log of the original distance， which is x0 minus x star。What squared by epsilon。

In this time， you will converge to within distance epsilon of the。And so the convergence is nice。

 it's modular the fact that there's a cup of eggs sitting here， the convergence is exponential。

You take only longer the accuracy steps。Okay， so that's。

That's basically a very general randomized algorithm with and we won it now we'll see how to use it full up plusing systems。

Yeah， there's a question of whether you can replace the in by the minimum。I'm pretty sure you can。嗯。

系啊。Okay， so now， okay， now we have a schema。 Let's go back and try to solve the lapplian system。

 All right， so okay， so what is a lapluian system just to。Becon。Okay so。So。嗯。Yeah。

Just to recall some things that we did last time。We said。We said the few things， firstly， you know。

 we can treat a graph as a network of。Network of resistors of resistance one。Of resistance one。

And then we had this。These are facts that we these are basically different formulations of the problem that we saw last time。

 just to recall because it's important so we have this we have a network of resistors。

 it's an electrical network and we ask what you know。

Things like what are the currents and the voltages。 So， for example。

 one setting would be imagine a ocean。B1 unit BI units of current。Into vertex i。B units。Of current。

When do I。Into vertex I in this network of resistors。Okay， and then of course。

 if I have to do this by flow conservation， how muchever I push into the network I need to also take up so I'm going to have a summation BI is equal to zero。

Okay and this is what you know we call this the boundary currenter。

 I guess I don't know if the boundary current is a right minelogy here。

 I could also call it the excess at a vertex， how much excess current is flowing into the vertex thats。

Okay， and so we have this boundary recurrence， so this is a B1 through B and vector。

And then you can ask a few different questions， for example。

 you can ask if Im drawing pushing this much boundary current。

 what are the actual currents on the resistors of the network？So the currents inside。

So let's call them FUV， this is the current on edgeUv。Okay。

 so these are I guess we also use the word flows right these are also flows so this is。

This is a vector f is a vector in r to the E for every edge。

 it's a flow is a number and we'll have the convention that if I say FUV that's the flow from U to V and if you ask me for FVU I'll just negate FUV and give it to you。

So that's the convention。And okay， so these are the flows and then we have you know when you have an electrical network。

 you also have voltages， right， you have potentials。That you can measure at every vertex。

 so this is sum vector V， which is in V1 through Vn。

Because you have flows have the boundary current and then you have flows inside the network and then you have the voltages all right and in this world in this world。

What is Laplian system solving， I claim it's really computing voltages。Okay， so because。Okay。

 so you know the boundary current going into vertex I。Okay you know， BI going into verexi。Okay。

 now what are the voltages here， well， if B is going into vertexi and let's say the potential of vertex is V。

All right， on the edge I J。Right on the edge IJ， the current on the edge IJ is basically by Om's law V minus Vj。

By the resistance， which is we are assuming all the resistances are value1 right so V minus vj is the current leaving I on the edge I J so if I add up all the current that leaves I on all the edges。

That should be equal to B， so B should be equal to sum over all the edges i to j。Of V minus vta by1。

Okay。So you see that if I know the boundary currents。The voltages。

 you can get the voltages by solving this linear system。

And that's basically what we need to do and you know if you look at what this linear system is。

 if you write it out， it's really the same linear system as L times v is equal to B。

You're given the boundary current and you're trying to compute the voltages。

 that's basically what solving Lalu and linear systems is。Okay， so。And。And as we saw， I mean。

 just by ownl， you know， I can either。Find the voltages。We went to the end。

Or I can try to find the currents on every edge。Findd。Currents。啊。If I do。If sub 80。On exering。

It's the same thing because once you know the if I know all the internal currents computing the voltage is easy and if I know all the voltage is computing the current easy easy ast use something you can do in linear time right because the current on HI is VI minus VJ and if I know the current。

Current， then the voltage is just you get that by adding up the you know the omsl potential difference so you can do it in linear time so。

So although we are trying to solve Lv equal to B。Okay， we will actually instead。

Because it's linear time instead solve for the flow。Solve for the F the actual current on every。

On NH。Okay。Okay， so that's how we'll proceed， so we'll be working those in the domain of in the space of flows。

Okay，And here。Well， you know， flows are just flows satisfy in general。

 they satisfy what do they satisfy， well flows satisfy conservation。

At every word right conservation is incoming flow is equal good outgoing flow at every vertex and this is just also called the K of current law in case of current。

RightThe incoming current is equal to outgoing current。 so we saw that， but then。Yeah。

Everything that satisfies conservation is a flow， like it could be flowing water。

 right water also satisfies conservation。Electric current or electric flows have another property is that they have satisfied the catch of voltage law。

And there are many ways to formulate this， I guess in last time we saw that electric forces minimize the energy consumption for a particular fixing of boundary current。

 but K off voltage law， you the simplest way to state it is that if I pick any directed cycle。

And I add up the flow along them。 I should get 0。So if I have a cycle， IJ， J K KI。

If I add FIJ plus FJ K plus FKI that should be zero okay that's the that's basically kit of voltage law of course we're assuming resistances are one others I need to put sumish FIJ RIJ。

And this is really what differentiates electrical flows from other flows。

And we saw a geometric picture of this already， if you look at all possible flows。

 they form a subspace。Of R to the E。Because r to these is all assignments of numbers to the edges。

All flows are assignments that satisfy conservation。

These are all flows and electrical flows are a subspace of all flows。

 which is all everything that satisfies Ksha's voltage law。Okay， and we also saw that。

This is a subspace of all flows。And。Flows that are orthogonal to this or the orthoagonal subspace of the to this are circulations。

 what are circulations， circulations are precisely。啊。诶I guess so。

Cations are precisely flows which have no boundary current。Okay。

 so we saw this last and circulation sub precisely flows with no boundary current。

So this is just you know current moving around in the network without creating excess or deficit at any vertex so there's no current flowing into the network or out of the network but just going around from one vertex to another so clearly circulations don't occur in a real electrical network you know only way current flow is you have to drive in some flow at some vertex you introduce a potential difference otherwise there's no。

Okay， so these are circulations， that's the orthogonal subspace。Okay。

 and what else and what's our goal now， well our goal is to given a set of boundary currents。

 we need to find the internal flows， that's our goal。对。

So the voltage given Lv equals B could be like not a electric flow， it could be like a normal。

 it's a normal flow。So you have to project that into the electrical space somehow。

How are we doing that oh you're not given voltages like once you have voltages it's always an electrical flow right so so kit off voltage law or this is equivalent to saying that you can define voltages or potentials uniquely。

Like if you if you assign some numbers to the vertices such that the flow on the h Ij is equal to V minus Vj that is by that will be an electrical flow because it's voltage so so really things that are not electrical flows are flows where you cannot assign those numbers consistently so I guess。

If you have a。A， B， C， okay， and then let's say this is one。There's one unit of flow going both ways。

Okay， then there's no way to assign at voltages consistently because let's say I said voltage of c equals zero。

 Al right， then voltage at B has to be one because it's one unit above and voltage at a also。

You know， if you go AC， if you go along AC， you'll see that the voltage at A is1。

 if you go along ABC you'll see that the voltage at A has to be two。

So really the only difference between general flows and electrical flows is that you cannot in a general flow。

 you can't even define voltages consistently and electrical flows you can。

There exist voltage pages yeah。Okay， and then my next question with that。

 since L is a L has a non like trivial kernel V could have could be infinitely many things。

 so like how do you know which one to choose？Right you're right so there's no single answer of a V that we look for we look I mean we really were trying to compute any assignment of V that satisfies this you're trying to find some solution to this linear system。

Shifting all the voltages by the same amount doesn't change anything in the network。

 so there's never a unique answer you're right， but we just want to find some assignment。

So we can shift everything voltage by a the same amount。

 in fact that's precisely the kernel for the Pian。All right， it is just a bunch of ones Okay。

And really， the only thing we also have to make sure is that the boundary currents add up to zero because that's again。

 from the kernel issue that。If they don't add up to zero， you cannot even solve for。

 but so we will actually given the boundary currents。

 compute the currents inside the network that will be the way well proceed。Okay。

 and do how does the algorithm sketch of the algorithm go？Well， so basically what is the input。

 the input is this boundary current， right？Okay now I want to first thing I do is I'll find some flow。

Let me call this flow F0。F superscript zero， some flow。Such that the excess at every。But I didn't。

Well， basically that sacrificespace conservation。就。And you know， at every node。

 you must have if BI units are flowing in。U。BI units should be flowing out in the internal currents。

Okay just some flow and how do you like how do you find such a flow well you know you could for instance do the flow and you can just pick a spanning tree for the graph and just route everything on the spanning tree it's very easy right actually if you for the purpose of understanding this algorithmin。

 let's even start with a very simple boundary current。

Let's say I send in I'm sending in one unit of flu at vertex a know vertex。

P and taking out one unit at vertex cube。Okay and every other boundarycurrent is zero just for understanding。

 so then you know how do you route this flow like you just pick some some path from P2 Q like the breakfast search。

 whatever and send the flow along that。That's it right so this is some flow， Okay。

 it's not an electrical flow yet。Okay， and what's our。What's the idea now we would。Project this flow。

Onto the span of electric onto the electrical flow project。

Tef zero into electrical flows using Kashmars method。Okay。

 so but first let me write down a system of linear constraints， right。

What are the linearer constraints well we know that the linear cons we need to satisfy it along every cycle the sum has to be zero so but will pick a special set of cycles。

Okay， so first you pick a spanning 3t。Picker spanning click。Deep， some spanning cl。Okay。

 if I maybe I can， maybe I can draw a spanning tree， so if I have a spanning tree。Okay。

 then I get a you know， there are all there are lots of cycles in the graph。

 but I can get a set of nice canonical cycles， suppose this is a3 T。Okay， for every edge。

 if I take any edge E， which is not in the tree。Okay， let's pick some pair of vertices。UV okay。

 and let's say Uv is an edge that's not in the tree。

Then there is a cycle that you can associate with it， which is。You know。

 if you this is the thing you do when you do in spanning trees。

 right for every HUV you know there's a unique path。From you to be in the spanning tree。

And along with AGV， it forms a cycle， right there exists a cycle。C u v。Let me call that CUE。

 this is basically the unique site code。I guess unique cycle in the tree。Union U。你就。

When you add this HG you is unique cycle form that's called CV okay。

 and so for every non edge or for every edge not in the tree， I can I'll get a cycle okay。

And of course， for every cycle， electrical flows have to satisfy this catch of voltage law。

 the sum of the flows are to be zero for every cycle， but let's look at just this set of cycles。So。

So let me give it some name。Okay， I'm using scripty in my notes， but。Let's see if I can pull off Scy。

 okay，6 scripty。This is the set of cycles。That which are by these these found by adding an edge right for adding H to T。

I just to。Like the things that we just saw。Okay now。

Basically for each of these for each cycle in this set there's a constraint right so let me write those constraints。

嗯。行く。The constraint is for each C in this set， if I add up the flow values I want。

F subB on this thing it should be zero Okay and this is our linear system that we are going to solve by Kaashm's method Okay。

 this is the linear system and so this linear system you see that it has how many constraints there's one constraint for every edge not in the tree so it has exactly m minus。

We've total number of edges minus n minus1。That is m minus n plus1 edges。

M minus n plus1 constraints and。嗯。You can verify like you know one can verify that these constraints span all possible cycles like you wanted to get all possible cycles right。

 but you by just by dimension counting， you can verify that these cycles for any three these m minus n plus one cycle constraints span everything so satisfying these is good enough。

Okay， that give you an electrical flow。Okay， so now what you know let me just write down the linear system for this well it I guess there's a matrix right there's a matrix associated with this。

 it's a let me call this a this is a matrix。Yeah， yeah， you know， let's。呃。Yeah。So yeah。

 so let's get into this matrix more you know。Okay， so let me just write down this matrix that I have。

What is it indexed by， I have one constraint for every agent e minus t。

Right and what is the constraint Well， for every age E minus T I have a cycle Uv and for that cycle I have a。

Right so what is this a linear system on the flows。A times F is equal to0。

That's what we are trying to saw。呃， that。So， this dimension。Is as big as flows， so R to the E。即系你诶い。

The columns are indexed by E。The edges， the rows are index by e minus p。And for every cycle。

 you have just the indicator function of the cycle edges there。

 So if you indicator function the edges of the cycle。

 So if you have CV you have one on the edges in the。

one on the edges in the cycle and0 the y because recall that the constraint is mainly just sum over F E E in the cycle C is equal to zero。

Some of the flows in the cycle is zero， and you have that。and I'm ignoring the issue of signs here。

 these are not always one， there'll be one or minus one depending on the direction you're going on the cycle。

 but yeah we'll always use the convention that FU is minus FVU so but this is basically how the matrix looks like。

Can we applyinging Kashmas on this matrix？Right and so now we just need to see like you know what is the web parameter m that you can associate with this matrix。

 but not m copper， the parameter copper that we were talking about earlier， what is it。And to recall。

 cup of it。Had two parts to it， which had the Frrobinnus norm。啊。Yeah。So did I to find copper wrong？😔。

你点噶。嗯。I。So I guess ka definition is fine the runtime I said is one over K Okay， yeah okay。

 that's makes sense All right okay we are right we' are in good shape All right so what is Ka well it is I said it's one over the Frbeius norm。

Times in。offer。It f squared by F squared。Okay， that's okay， let's let's。

This is what determines the run time。 So let's figure out each of these terms。

 So I guess the thing that。Is maybe， let's do the。It's to the。

Thing that looks complicated was actually easy。So the first thing is。Tll you about this。

Something that looks like the condition number or the smallest angle in value okay。

 and the claim is this is actually always at least one。Okay， in fact。

 well prove that the spectral of a not the spectrum。

 just the length of AF is always at least the length of f。OkayAnd why is this true？Basically。

 because。If系。Okay， if I look at。呃E。It has a very big identity matrix sitting inside。几数。

So I said the columns are indexed by the edges， but let's just put the three edges first and then put the e minus t first next。

Okay， so if I put the three edges first and then I put in the e minus t。Okay。

 now every cycle like for every edge and e minus t。

 there is one constraint right and that's the only edge on in CUV。

The only knowledge that participates in CUV is the EdUV。

Because that's how it is right every knowledge participates in a cycle with very that is the only knowledge there I missed this picture yeah。

In CV， Uv is only knowledge so therefore。Essentially this block。Here looks like the identity matrix。

Right， so。Right。And， therefore。嗯。ok 诶。The proof I had in mind。

 I realized there was a there was a subtle team which I had missed。 But okay， let's see。

 So now this is a matrix A。 So what can you say about。TheOkay， so it has this bigak identity there。

 so the I claim that the smallest singular value of a is one。

Do people see that because if basically I claim that if you hit x on the left。

 if you look at x transpose a。Okay， if you look at x transposese， then it has a copy of x in there。

Extra transpoa looks like x and then something else， some whatever， some some extra stuff。

Because there's a big identity matrix x transpose looks like x and some extra stuff。

 so therefore the norm of x transposese is always bigger than the norm of x。Okay。

 and I want to think that that finishes the argument why norm of the right hand side。

 AF is also bigger than half。Doesn't have say that the smallest single value is at least one and therefore AF is elsewhere at least1。

Yeah， I think that's right。So。So basically did this。This is just because。Identity sits inside。Yeah。

Okay， I'm a little bit unsure， but if you'll point me to if there's a mistake， but it is a proof。

 I mean there is a two line proof in the book that I've given。

 but I thought this is I mean which also uses the fact that entity sits there。

 but I think the singular value proof is right。跟 check得 o。All right。

 so that's the easy part it's going to be just easily true for every graph and okay what's the other part which is interesting is a Frrobinus norm。

 okay let's calculate what the Frrobinnus norm A is。

This are sum of squares of the norms of all the rows。The length of all the rows。Okay。

All the rows are the matrix and that's basically is total length of all the cycles because the length the square length of a row is just then you know row is just a01 vector with the one one for every edge of the cycle。

 so it's basically the total length of。All these cycles。Okay。

 and what is the total length of these cycles， Well， okay。

 this is this is something to think about so。We'll write the total length of a cycle in a different way。

For right， so the length of the cycle is basically。WhereWhere did I say， okay， okay yeah。

 the length of the cycle is basically one plus the distance between U and V in the graph。

The length of CUV is one plus the distance in the tree between U and V。RightThat's clearly true。

So let's write that。1 plus the distance in the tree between U and V。Okay， and。Okay。

 so the quantity of interest is basically， you know， there's something like M。

Then the number of ages plus。呃。This quantity Dt of Uv well what is it it iss one plus a distance between U and V and the tree I'm going to call it a different thing I'll call it the stretch。

Stretch of Uv。Why do I say that， well， UV are connected by an edge in the graph？

In the original graph， Uv are connected by a net， so that distance is one。

And we are asking what is the distance in the tree。

 so in fact Dt of Uv is trivially equal to Dt of Uv divided by the distance in the graph of Uv。Okay。

 and some of basically the ratio of the distance in the tree and the distance in the graph on every edge。

 that's what seems to be important。 So we need to pick a tree such that this total stretch of all the edges should be small。

Okay， should be small as in we'd want it to be what know the first term is already M。

 so we'd want this to be order M。I mean or something close to M。 So since there are about M terms。

 like as many terms as there are edges in the graph roughly。 So you would want the stretch to be。

A small like order one order log n or something typical edge， you want it to be a small stretch。

To be stretched today。Order log n like you want the stretch of typical edge to be like， you know。

 order log squared and something small。Like let's say log， polyloggan。Okay。If you had such a three。

We could pick any tree to start the algorithm if you pick a tree where the total stretch is small。

 then your runtime is good so in fact there are such trees so just to state here's a theorem。

That exists。Span increase。In every graph。Such that the total stretch of all the。啊。Edges。Is about。嗯。

M login。Well definitely M log squared n so I think it's M log n log log n， but。

What's best M quoing you can get？Okay。And so if you， okay， so now we have a bound on the。

 so this implies that if you pick such a tree， the Frrobinnus norm of a。Is a order M log squared n。

And we already saw that this other term in the Ka is1。So basically， you get copper of a。To be。Like个。

You know。Oomega of1 over M log squared then。This implies that your run time。

That we started out with this copper squared is one over k squared。

 you get to order M log squared and run。Well， to be careful， okay。

 you can hope to end loss scored and I let me call it not run time iterations。对。That's what。Yeah。

其实 that gives you诶。Yeah， so that gives you what does it give you。 It gives you， Yeah， right。 So， so。

 so that's。Like sort of what we want okay so。Firstly。

 we want span trees with small stretch and we should be able to construct it efficiently。

 construct in linear time。In the linear time。But you can do this。

And just to give you an intuition of what these like what's the difference between just a knee spanning tree and a small stretch spanning tree。

 here's an example， I guess I I mean。This is I got this picture from somewhere on the web。

 but basically。You have a great。And we can draw many any kind of spanning tree for a grid。

 so look at the right spanning tree， the red spanning tree is good for all intents and purposes except its stretch is really high。

So if I look at a typical edge， let's say somewhere here， a typical vertical edge。

The distance in the tree is about。Order in。E theta and a typical edge。 So。

 so if I look calculate the total stretch of this， it'll be， I think。Order M times n。

Data times and that's the total stretch so it's bad as you can see。

 most stages are stretched because。To go from U to V， you have to go around here。Okay。

 but in the same graph， you can pick a different spanning tree， which has a very small stretch。

 so if you look at the green spanning tree， it has a really small stretch。W in factor。

It's total stretches like theta M a typical edge is like order only stretch by a constant factor。And。

To。So that's what a low stress pantry gives you right so a low stress pantry should look like the green tree and not like the red tree。

And you can construct them， so we came extremely close to constructing these earlier in the class when we talked about metric ands。

So we talked about how you can decompose a metric space into small pieces of small diameter。

And then we use that recursively to construct something we call hierarchical trees like her。

We embedded every metric into a three metric。That's very close to the kind of techniques you use to construct。

These low strip pantry， the only difference is or there we didn't have a graph we had just had a metric space and we were allowed to pick any tree。

That represents that。Over here， the restriction is you're given a graph and you're given a shortest path metric on the graph and you're only allowed to pick a spanning tree of the graph。

 So the restriction here is that you can't just。あYou know。

r some other tree which is with extra vertices and so on or there we had extra vertices and some other tree here you want a spanning tree of the graph。

 but you can do it by effectively as similar technique as that you first construct these low diameter decompositions just like we did there for metric spaces it's very similar and then you just use the low diameter decompositions。

To construct the slow streets pantry like the。When the idea is basically if to have a graph。Right。

 first， you decompose the。Graph into small pieces。Or you know， into pieces of， let's say。

 size some root and or some end to the epsilon。Which are low diameter。

you decompose a low diameter using the low diameter decomposition media that we had。Now。

 what you do is for each of the pieces， you construct a low strength spanning tree by induction。

By inductional constructors no stretch for each of the pieces。

And then you have spanning trees in all of these pieces。

And then you look at the graph formed by these clusters， each of these clusters， each of them。

 the connector that forms like a super graph right and you you know you do the same thing there and you get apanic tree for the whole thing right the only restriction from then was that you to you can't have。

You have to produce spanning trees of the graph， you are only allowed to pick edges in the graph and therefore that's the only you had to pick trees in the graph。

 so you dcur pick trees in each of these pieces and then you glue the trees together by a tree the higher in the bigger。

In the higher level component graph。So， so that's sort of the idea。 And we came very close。 I mean。

 the techniques that we used essentially give you this。

 but you have to work a little bit harder because and you can check that。 So okay。

 so there and I mean the。So we can do it so you can there are very simple constructions of spries with low stretch in fact if you care about stretch like m to the one plus epsilon it's really easy m log squared and you have to work a little harder okay so that's one thing。

All right， so so that part is good， but then you know after you pick the spanning tree。

 now we proved that the number of iterations is small。But you to implement these iterations。Right。

 each iteration is。啊。Implementing this update operation in Kashm's。In Kashmirs， right？This sorry。

 it just。I need to find a better way to scroll。一。Yeah， you need to implement this update operation。

 so a naive implementation of this would be very bad because you're actually dealing with vectors whose length is。

As long as the edges。Each of these we are working in the space of flows。

 so each of these vectors is r to the E， so if you even try to add them and each iteration will be too expensive。

So， but， you know， the luckily for us， everything is happening on a tree of right really have things happening on a tree。

 So there's some data structures you can use to implement the iterations fast right so you won't get into the data structures There's some data structures you can use basically what's happening is somehow。

All the everything's happening on the tree， so every time you add as you add a cycle or if you add you know you add something to the flow it's you know exactly which cycle you're adding it's some edge between U and B and you can actually maintain the data structure to do that so we won't get into the data structures aspect。

嗯。And then I guess there' one more thing which is which we left out under the rug is I said we need to pick。

You have a span plea。And you need to pick。ある。A row of this matrix a。

 a cycle with probability proportional to the length of the cycle。Okay。

 so you have if I give you a tree， I want you to pick and knowledge Uv。

With poverty proportional to the distance between UN and B in the tree。And yeah this is something。

You can I also do， but I think it。Again， it's some clever。Algothms thing。 I mean， yeah。

 also have clever you know data successes and。 I mean it's it's the this is this， this actually is。

This paper， I mean， gives you an algorithm to solve uppress systems is actually quite simple。

 you can actually implement this people have implemented this and。诶 it。

It brings back techniques from classic algorithms like data structures and basic updates on trees towards efficiently solving app flash like the the thing that we saw today is very clean and very simple because it brings back things from data structures and so on the original spment tank and many other papers they work in the。

They don't work in the space of flows。 They work in the space of voltages potentials。

 So if you work in that space you。You have n dimensional vectors， which are easier to update。

And you'd write， it's a very complicated recursive thing。

 the algorithm is a very complicated recursive thing。

 but it doesn't use any data structures and things like that。

 it's just precondition gradient in a sense。That you recursingly say。

I think we went through this earlier in the class。If you want to solve ax equal to L equal to B。

You find a matrix L prime that。3econ L X equal to be well so that you can run preconditioned gradient in designcent and then your problem becomes solving linear systems L prime X equal to B and you would recursively do this。

 So it gets more complicated， maybe much more complicated algorithm is way more complicated。

 but there's no data structures and things like that。Clever things， this is uses both。Yeah。

 I think Rahul， I think Rahul found a mistake in this。嗯。I think this argument。

 as I said with the single values is wrong， I'm pretty sure it's wrong。嗯。But。

It's pretty close to being right。 So basically the reason you you have。Yeah。

 AX doesn't shrink is because it has this identity matrix sitting there。But。What do you do？Yeah。嗯。

Right。嗯哼。RightI mean I guess what we are worried about is when you take the linear combination of the columns。

The identity matrix will copy what you have here。And then the only worry is the rest of the terms。

 the linear combination of the first。These columns could cancel out exactly what you have here。

And we need to prove that that doesn't happen。Yeah。嗯。不ta。Yeah。Yeah。

But we yeah I guess so how is a defined in the first place oh a is just this matrix right so you have it's indexed by the non edges of the tree on the rows and the columns are the edges。

And for every knowledge。You write down the cycle found by that。Knowledge， you write down that cycle。

 right the indicator of that cycle， because that's the constraint here。

Some over F is in the cycle that zero， that's basically saying。

For every edge U there's a row for every non edge， so not a knowledge for every non tree edge。

 these are non tree edges for every non tree edge theres a cycle where you can form and you write down the indicator function of that cycle in the edge space。

On the draw。Okay， that's third thing。 and so clearly you every non tri edge。

Like you know it belongs to one unique cycle and in that unique cycle it is the only nonreage。

 so theres a big identity matrix here。 but there's also other stuff here yeah。Okay， but you know。

 this is， yeah。嗯。Yeah。Yeah， I'll leave it as an exercise。

It's a very short like a tool line proof it's there in the thing if you want to check it out but but I think we are quite first the main reason is that the identity is here。

Any questions？Yeah。I mean now actually， you know， there are more versions of lap plus and solves。

 there's also a lappl and solver， which forgets gradient descent or you know which goes back to which implements Gaussian elimination efficiently。

On this。嗯你。On these locationss。Wait quick question so is there a reason we didn't just use the kmer algorithm on L itself like on L Yeah like you know we had we had originally we had like LX we wanted to solve and we converted it into this problem of like AF why don't we just use it on Ellen in the first place？

Right。呃。耶稣。Is it because like it says a nonzero kernel？No， yeah， no， that was。

 that was not super yeah。嗯。Okay， okay， so I think one thing is that to Kasmos。

 you need a starting point。Well， okay， you're saying let's just start with。Some set of potentials。

Start with some set of potentialedials and you run Kashms。Yeah。

 I guess the thing that we don't know how to control in that setting is we don't know how to control the eigenvalues of L。

Basically this in quantity that we have。Yes。Like the corresponding quantity there is。嗯。Yeah。

 what like yeah， I mean， really， we can see that quite nicely there the corresponding quantity there is how small is this。

Even on， let's say， even when x is not in the kernel。Let's say x is not in the kernel。

Xor at all onces， x the， how small can this be？You can see that this is related to the spectral gap。

 which is really the smallest eigenval applaian。If the spectral gap is bad。

 then this takes a long time。That's basically。It basically goes back。

 you end up with this like the Kas is not very different from gradient descent。

 so youll end up at basically the same scenario where the runtime depends on the condition number of hell。

And some of the condition number of L might be very bad， for example。

 if there's a long path and so on， condition numbers are pretty bad So what you do you have to。

You know， you get back to how do I improve the condition number。

 you try to precondition that that's the whole right that's thes the entire line of work there。

To make precondition great in decentsent work。And at a very high level， in some sense。

I think these algorithms are trying to say， okay， if you just did gradient descent。

 with ignoring that L came from a graph。Right great indcent is a continuous quadratic thing if ignoring the factor L came from a graph and you just gradient indcent your runtime will depend on the condition number okay and what these algorithms are saying is now I know that my matrix L is actually the of a graph so let's see what kind of graphs I can actually solve things on quickly you can solve things on trees and so on quickly。

On trees and partss and spars and trees and parts and things like that。

 so you're using that combinatorial thing as a as an additional ingredient in gradient descent like even in the preconditioned gradient descent and so on。

 they pick some spanning tree and you can solve it on span trees and so on。And for example， here。

 when we said， oh， you can always just pick。Like you can just pick a shortest we can pick a spanning tree and route all the flow in that。

That's basically implicitly saying about saying this fact that you're using the comm structure of the linear system。

To solve hard condition number cases easily， like on parts， it's easy to solve。Because you can。

You can do caution path easily， effectively， right。So， that's。做 yeah。

That's the mix I mean that's why this set of techniques are very powerful they bring two things which haven't been mixed earlier right we've been in the world of max flows you know combinatorarily talking about graphs and then there's the world of gradient descent and continuous optimization they use the two together very well right you know even on this algorithm there's data structures on trees and you know gradient descent put in together and that's why it's powerful。

And that's why they've made progress on Max flow and things like that。

Pat I just want to point out to everyone who's still here the project proposal is due tomorrow and it should be it's up on grade scopepe for everyone to submit right now and so you can everyone can add their teammates on gradeSpe so I'll make a post on Piazza tonight as well and send emails up but just a heads out for everyone because not a lot of people have submitted but。

Probably because not everyone knows it's on great scale， some should be great。这样。

Heads up for everyone。Thanks。Pvene， it's due April 1st， the proposals due April 1st。Really quick。

 could you go over again？Translated this from solving some Laossian system to finding an electrical flow。

Well， I mean， the what we said there was that basically that blood plus system is the。

Like is the problem of computing electrical flows because if you look at the problem of computing potentials V like if the potential on every vertex is VI。

 then the outgoing current each of these edges is VI minus Vj divided by one。

And that you're given bi and you're trying to compute Vs and that is essentially same as Lv equal to B because you can write look at L I mean the matrix L。

And you see what linear transformation it is， it is really this linear transformation。Because I mean。

 usually we state it as degree minus decency matrix， can also state it as。For every HI， one minus1。

1 minus1 that sort the all right。O。嗯。Yeah， okay。 I没 sense。Thank you， professor。



![](img/732ae2c87e3e67d7696123b0fd134ae0_2.png)