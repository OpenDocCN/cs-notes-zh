# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P18：lecture 18.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/06071532b4ee602442e47d6dcaac3f66_0.png)

Welcome， everyone。Today we will talk about maximum flow in undirected graphs。

So we'll see an algorithm for maximum flow in undirected graphs and let's even assume that the graph is unweighted。

 so all the edge weights are。稳。graduateduates just one and。

We'll find an algorithm for maximum toander graphs。

 but the key thing is we'll use the primitive that we constructed last class in the last lecture we saw。

And algorithm' give for La plush in solvers。So what are these？Well， these are。You know。

 you have a lap plusian linear system， Lx equal to B。And you can find X。

Approximate later with an epsson error in time， which is essentially linear in the size of the graph。

 so you can find it in time， let me say o tilde of M。Lone， one over epsilon。

So it's essentially a linear time operation on the size of the graph and given any B。

 you can find x easily and this has an interpretation in terms of flows the interpretation was if you。

Think of the graph as a network of resistors where the resistance on every edge is one。

And if I tell you that。If I inject a flow of B at every node， so I have B1 going into node 1。

 B2 going into node 2， and BN going into node n。And we compute the electrical flow inside the network。

As in if these were the actual currents going into these nodes and coming out。

 then what would the flows， the electrical flow and all the edges of this network be。

 we can compute that in linear time。And the key thing is the electrical flow is one that minimizes the total energy consumed。

 so the total energy consumed was basically if you have a flow F on H E。

So this is the total energy consumed。Where RE is the resistance on H。Okay。

And we did this for all the resistance being unit capacity。

 but essentially the same algorithm also works if you are allowed to put in resistance values on the edges of the graph and you solve this。

Okay， so that's our goals， our goal would be to use this electrical flow computation to actually do max flow computation。

And we saw a couple of examples where the two things are different。

Because their objectives are different。Okay， so what is a maximum flow？So you know let me mag flow。

 you can obviously formulate it as a linear program so let me formulate it as a linear program so。

Here's a linear program。 I'm going to formulate it in this way。 So I have a。

I'll call this Xcon set K， which is a set of all flows。Flow is just a vector and r to the E。

Such that。What should be true？Well。You know， flow should satisfy conservation loss right the incoming flow should be equal to outgoing flow。

 So basically if I。Sum up all the outgoing a vertex。The flow on those。That should equal to zero。

For most vertices， for basically most vertices， I。And here we'll always use the conventional that FIj is equal to minus FjiI。

Okay， that that's always going to be implicit。 So when we say F I J， you know。

 if the edges J I instead of I J， we'll call it a minus fJI。 So so this is a reasonable equation。

 So the total outgoing float of vertex I is0 unless the vertex I is the。

In you know S and T there are two nodes S andT we are computing max S flow， so mean if it's S。

 then the incoming flow should be some very large value， hopefully so。If I equal to S。And if it's t。

 then the total flow should be like minus f because that's leaving there。If I equal to T。And other。

 it's so。知道。Okay。So basically， this is all flows that have like a capital F going in to S and capital F leaving out of T。

And you know， whatever happens in the middle， but as long as you satisfy flow conservation。

 this is it's in the setF okay。Okay， so so far we just talked about flow conservation Okay when and then when we talk about electrical flows。

 then we go ahead and minimize the total energy consumed by the flow。

 but today we'll be talking about max flows for max flows what you have is capacities So let's say all the capacities are one so the capacity constraints are clearly the things that make you know max flow problem。

The max problem is that on every edge you have a capacity。

 so the capacity constraint is that you know F to B， the flow and H E， that say it's one for all HE。

ok， so。So in some sense， maxflow is the problem of finding。

Or flow with capacity constraints and the max flow。

Is the problem of finding a point F which is in the in the K。

 it satisfies the conservation and satisfies capacity constraints。Okay。

 so that's the problem we are dealing with。Okay so it's a linear program。

 but there's a reason I have separated the conservation constraints K from the capacity constraints。

 as you'll see basically the conservation constraints are very easy to satisfy。So for example。

 if I wanted to find the flow of value F。From ST。Just find any path from S。

And just route F units of flow on that path。Okay， so the capacity constraints are what makes the problem interesting and hard if you just wanted a point in k it's easy。

Like if you just give me the flow value， I'll find a path and route that much flow in there。Okay， so。

 so basically， you know。The polytop K or the linear program associated constraints in K are easy。

 like you know they're sort of the easy constraints。in fact。

 there are many different flows that you can find。With size by flow conservation。

 you can find one path or you can find the electrical flow electrical flow also gives you a point in K because it gives you sizespace conservation。

But of course it doesn't satisfy for capacity constraints， but it's also a point in K。

 so there are many ways to find points in K。And the real trick is to find a point in K that SA face capacity constraints。

Okay，And so we'll do this。Were essentially saw we a leave program here。

 so we'll do this by using the multiplicative weight algorithm。Okay， so the。You know。

 if I had to say。Sort of the bigger picture of the algorithm that we will see today is that there' will be a multiplicative age algorithm that will you know。

 use。An electrical flow solver。To compute the， to solve the。

So the max low problem that'll be the idea。 So since it's been a while since we talked about Mac multiplative weights。

 I just do it a little more with。And this recall what multiply weights and what guarantee we need Okay。

 so here's the version of multiy weights guarantee that we'll use。

So this is multiplicative weights or the expert algorithm or the hedge。He gelut， I guess so。

So here's the setup I would we are thinking about so you have。The game has。

 there's a multiplicative weight algorithm。Okay， and then there is a adversary of nature or we will call it oracco。

You can address it。Again， essentially what are our experts？Okay， som sorry and there should be， yeah。

 look what are experts here， let's say experts are1 through M。

It just like there M experts all right so how does my how is my deative weight set up well in round t？

The algorithm maintains some probabilities right so the algorithm sends or algorithm。

Fixes are probability distribution。Be superscriptive。Okay。

 this is a probably distribution on the experts。And the adversary or the oracle can actually look at this product distribution or what it can do whatever it wants。

 and it's going to give you a set of well use gains here as a term now you could also talk about losses but let's just talk about gains。

 so this is a gain vector gains。So what are the gains well gains is some vector so if you pick export one。

 you get a gain of G1， I'm sorry should be。G。This in round T of G sub T， G superscript t1 to GMm。

Okay， those are the gates。And then the algorithm incur。

Again given by the expected value so the total gain incurred by the algorithm is basically you know the in the product of P and G。

This is what we。Okay。See you pick a algorithm picks a product distribution of experts and there's some nature or oracle that gives you some gains and then the total gain incurred is just P in a priority G。

 which is the expected game。It is someピデア GD I。Okay。😊，Okay。

 this is basically I'm recalling the setup of multiplicative weights and you know the guarantee is basically that after a number of iterations of this algorithm。

The expected loss or the average expected loss or the multiative average expected gain or the multiplicative weight algorithm is no worse than the best single expert throughout。

Okay。If I picked one expert as my pro distribution and stayed throughout。

 I would be no better off than。Using the multiative weight algorithm。

Hes a multi white algorithm beats every single expert over a long period of time beats are you know just does well as well as any any expert。

Over roughly long aits， log mits。Okay， so I'll state the theorem that we'll use。Reect。

So the theorem is， let's say all the gains are in some range。

You need to put in some range for the gains so。嗯。Okay。😊，Then no matter what the oracle does。

 like whatever for every choice of the gain vectors。Okay。😊，You would have that。The。Average gain。

Of multiplicative age algorithm， which is given by this。P， T in a product G T。

It's the average gain of the multi algorithm this is at least the best gain by any given expert。

 so you pick any fixed expert。Max overri for a fixed expert。You ask， what is his game。 Well。

 if you just picked him every time you would get。Where youd get。嗯。Like you get GTI， right。

 so you get just。With theith expert every time you'd get GTI。And that would be a total gay。

And you match him back with an epsilon。Okay， and I need to say how long after how long this is true。

 Well， basically this is true after。B。I。嗯。Garma R La M by Epsilon Squared。对。After this many steps。

Is that like an O bound or is not there's an O bound yeah thanks？There's no body of gama。So the。

So this is basically the multiweights thing that we saw in the class。

 we didn't see this tighter bound we saw I think order rosequad by rosequad lo M or epsilon squared。

 but you can derive this。Takeer bone。Yeah， it's a bit more subtle to derive this tract bond。

 but it's just the algorithm is essentially the same algorithm we saw， right？

And I guess the key point here is that this theorem is true， irrespective。

Of what sequence of gain vectors you're given。So even if the Oracle sees the probability distributions that are being played。

 so Oracle picks the G。After it sees what's being played， even then the same guarantee holds。Okay。

 and we lose that。All right， so that's multitplicative weight。

Okay so now the first black box we' build is we'll see how you can use multiplicative weights to solve a linear program so earlier in class I think we saw how you can use multi online convex optimization to solve a linear program this is very much similar to that。

 but it wouldn't hurt to just go over it again because we'll be using it today。Okay， so。Okay。

 so now we'll see how to use this multipl weight algorithm to solve a linear program。

 so let's just look at a linear program， so solving LP。Why are multiplicative weights。

So let me just write down an LP， so it just be a feasibility LP， so feasibility LP。Would be。You know。

 find the next。Such that。You know， some set of constraints are true， let's say。

You have a bunch of constraints like AI in a protex。Is less than equal to B。You。Okay。

 so you have a set of pin screens， AI and the products lessing group BI。

So these are the constraints of interest。But we'll also throw in a bunch of easy constraints。

Not just in view of what we are going to use it for。

 so there'll be another set of easy constraints let's just call it x in k。

 these are supposed to be easy constraints。Okay， so how do we solve this so let's call these the other constraints。

I guess let's call them hard constraints。So in our application。

 the hard constraints are the capacity constraints， the easy ones are the conservation。

 flu conservation。Okay， so again， whats the game being set up basically well run multiplicative weights。

 so here's a game。So we will have know one player will be。A multiplicative weight player。

Okay and the other player would be。你。Where we called it the oracle。Okay， so。

So what is the idea the idea is what what our experts our experts are going to be。Constraints。

So maybe I can， yeah， I can write here。😔，A experts。Will be the constraints。Okay， so。

We are going the algorithm will simulate by the multiplative weight and the we run the the the algorithm that we are going to。

Devicice will actually simulate the interaction between multily weights in oracle and what's the multiplity weight algorithm doing it's trying to find a violated constraint okay multi weight algorithm is always trying to just find a violated constraint and the oracle is just trying to exhibit a solution。

Reco gives a solution， multi weights try to find our pilot constraint and that's the game they are playing okay。

But again， the weight we' set up， the multiply weight algorithm goes first。

So it has to give a constrain that and then the oracle gives the solution， okay？

So the records job is easier， so multi weight says I'm going to look at this probability distribution of constraints。

So the experts are the cons， so the oracle fixes。Some PDFf over constraintsstrain some。

Some probability distribution。Let me call， let's call that again， it's P sub T。Bス不。P T 1， P T2 P TM。

Or were the constraints？Okay， so。嗯。And the oracle now finds a point in the polytop。Findins。Orracle。

 you know what what is it output， it outputs an x x superscriptee。

Wwhich is in the which satisfies the easy constraint so easy constraints are always going to be satisfied it's as if the oractalles moves are always inside the easy constraints okay it's always satisfy the easy constraint。

But。So if the oracle plays x of t， what is the gain like what's the gain vector。

 the gain vector is how much the constraint is violated by so the gain vector is。So GT is。

How much the eighth constraint is violated by？Notor that AI X should be less than B。Therefore。

You know， the way we have defined the game。If Xt violates a constraint I， then the gain is positive。

 so the multi weight algorithms gains are the total violations in the constraints。Okay。

 and so that's the gain vector the oracle sends back， basically， it finds a pointex。And it， you know。

 the corresponding gain vector is this one， and that's what it sends by。Wai， so the gain vector。

 if it's negative， then it's found a feasible solution， yes。

 if all the if the gains are all negative， then it's found a feasible solution。

 then the Orac has found a feasible solution。Yeah。Yeah， so。Okay， but you know。

 I still didn't say how it， you know how it finds this。Like， you know， what point does it pick in Xt？

Well， it makes sense that the oracle should。Minimize the gains of the algorithm， meaning it tries to。

はい the。I just stepping back if the multiity weight algorithms gains are low that means that it's not finding any violated constraints and we are happy so the records job is to actually find an X whose gains are low so in fact but we want the average gain to be low so what we want is。

One of it will find an x such that what is the average gain， well it is just。This thing， right。

 it's P。第一。基地。As I've defined here， it's basically the average violation in the constraint。

If I had to write down， it's the average violation in the constraint where the average is taken by the distribution picked by the multiplicative weights。

So this is where the oracle is actually looking into the probabilities of the multiplity weight multiy weight says I'm going to check these constraints of probability p1 through pm and the oracle picks an x such that the average violation is small and you know。

If there's a feasible point， the average violation should be negative， right。

 there should be a point which is。Like the gain should be negative。So。

If there exists a feasible point。Extt。Okay， if there exists a feasible point X， then you know。

If you pick X， all the gains will be negative。We' all negative， so the average gain is also negative。

Okay， so what we'll make sure is that the oracle。Pix。A point Xt。Whose average gain is， you know。

 let's say let's say zero or let's say average gain is less than epsilon。

Or that in terms of the violation， Oracle wants to pick a point that whose average violation is less than epsilon。

Okay。So if we could make up an oracle such that its average violation is less than epsilon。

We you know' that will be our algorithm， so you the multi rate algorithm playing against naacle。

 which given any distribution finds a point whose average violation is less than epsilon， okay？So。

Right so this seems circular right we wanted to solve a linear program， but now our oracle is is。

Sort of task to find a point whose violation is less an eent。

 so implement directly you to solve a linear program， it seems like。So what did we gain？

Anyone see what towards the game is？question， when you say average gain are you talking about average over time no average over sorry the average over the Ps so this is the average gain yeah I mean I mean average over P over under the distribution P。

This is what I am referring to as average gain。I guess I should just say， yeah。

The advantage might be that the average gain， you don't have to。Satisfy all the constraints at once。

 you just have to prioritize。Yeah。That's right so like originally we had to satisfy all the constraints now we just have to satisfy this average constraint and note that average constraint is just one linear constraint this whole thing is just one linear constraint。

If I say that the out gain is less than epsilon。It's a single linear constraint on on my point。

 So we this thing reduces the problem of satisfying all the capacity constraints to satisfying。

To constructing an oracle that satises one linear constraint。Itr of M one Okay， so that's easier。

 right， so so that's what the it's what will make the oracle do。

 So let me just write down what the oracle does。So the oracle。Or does it do。

 it sees the probability distribution。P equal to P1 through PM。

Just the pro distribution of the constraints。Okay。And。It outputs a0 x。K such that x is in k。

 x satisfies easy constraints。And secondly， the average gain。The average violation。力的力骚。

Is average violation is at most steps not？So it finds an exc that these two are true。So。

 this is a effectively solving。An LP with one constraint， which usually is easier。Okay so okay。

 so let's say we somehow implement such an oracle and we use that here。

 so that's what this oracle is going to do。Okay。睇。Okay， so now what do we know， well in each round。

第一。The gain of the algorithm， multi weight algorithm。Is smaller than epsilon。Right， because。

Like the oracle seems to always make sure that the gain is at most epsilon。

That the gal the multigra algorithms at most epsilon。Okay。

 now let me just write down what the so again mod cycle comes are most epsilon。

But we know that the gain of multi algorithm is。So。Is。嗯。

Average over time is better than any single expert， so if I take one over t。Some more would I。B。第一。

GT， this is the average gain over T steps。This is utmost epsilon。

 right because each step is's umost epsilon。But by the guarantee of the multiplicative weight algorithm。

 this is by the theorem that we stated。This is at least the gain of the best。Expert in hindsight。

 So if I just look at any given eye。I equal to 13。And I look at what just picking that one would be。

 so if I just pick that one。I would have1 over D。S over t equal to one through T each time I'm just picking that constraint。

 So my gain will be。AI in a product。X0。Minus B。So this is a multiplude of weight guarantee I'm just substituting that here。

Okay， Epsilon Mr this。All right， so what that means is now I'm just going to take this inside。

 so I'm going to take this。Inside， so what is it， it's max over I。嗯。AI in a product。1 over啲。

T equal to1 through capital t。X D。Minus B。It is same。Mineus epsilon， sorry， minus epsilon。

Are the epsilons the same or are they different epsilons or I use the same epsilon yeah yeah we could they come from different places yes they come from different places this epsilon comes from how accurately we said the oracal does this epsilon comes from how many the guarantee from the multily weight algorithm them use the same thing because we sort of balance are quite well。

嗯。Yeah。So now you know， you see that this。Looks like a good solution now。

 if I call this x star or this call this X star， then you see that X star。Has this inequality。

 so I should say two epsilon is bigger than the violation。嗯。In any constraint for Xstar。

So x star is a two epsilon feasible solution。Okay， this is sort of way similar to what we did earlier where we solved LP using online Comx optimization。

 this exactly the same just that we're using multiplgative weights as a particular version of online Com optimization here。

So in this case， multiplicative weights is trying to choose。Constraints that。

Are like most likely to be violated。Bas yeah， yeah。

RightM weights is trying to choose constraints that are violated and the oracle looks at what distribute multi weights peaks and it sort of satises the average constraint every time。

Okay， so。So right， so what are the okay， so this is good so now just to go go to the quantitative parameters well the quantitative really the two parameters of interest are。

Firstly， the maximum， like we want all the gains to be in some range， right？The minus gamma to rh。

 that's what we were using in the theorem， So so let me just say what these parameters are rh。

 What is that it's the maximum gain。Possible like its sort of the maximum violation of a constraint。

So that's the maximum。喂你士。Like on every like on whatever constraint and whatever solution the oracle produces。

 so it's like you can say it's max or I。Of， you know。X。第。In a product， AI。Mus B。

This like it's the worst possible violation that you could produce。And what is gamma。Well。

 gamma is like the。嗯。In some sense， it， it's the。Minimum gain or maybe a side space constraint too well right that's what gamma is。

其实。😔，And a runtime is basically the critical point is that a runtime。

Is like how many rounds do we need to run this interaction between the two objects。

 it's going to be row gamma long M by Ms epsilon squared。Okay， that's what。

So it depends on the maximum violation and the minimum。So。This mag violation。

 I is also usually called the width of the oracle。It's like the in some the row is' like the largest eigenvalue if you have a strong convex function。

 strongly convex function， the largest evalue of the hesN。Okay， so that。Okay。

 so we have everything set up now all we need to do is to construct this oracle。

Once we have a construct oracle for our problem at hand， we have a flow。

And algorithm get them to solve Max flow。Okay， so that's。So just to recall what the oracle has to do。

嗯。It has to do the following。That it gets a probability distribution over constraints well the constraints。

Are indexed by edges。So it's a broad division P over the edges， so you have p sub E。

So why is there a pro distribution of the it is because？Because okay， these are， just to recall。

 these are the constraints that you have。So the constraints are really the capacity constraints。Okay。

 the only concerns that the flow is going to be violating are down on edge on some edge。

 it will be sending too much flow。And the multiplity weight algorithm is essentially deciding which edge to check。

For capacity violation。Okay， so。You have a product distribution over。

 we edge to check for capacity violation， so that's what the pro distribution PB is。Okay， and。

And what should the oracle do？Okay， the oracle should do is。It find a float。Okay， well， firstly。

You know， it should satisfy conservation constraints always， so F should be in K。

So in every vertex conservation constraint on S incoming flow of capital F。

 on T and outgoing flow of capital F。Okay， and the。Only thing the other thing is the average gain。

 the average gain is the average violation right so it's sum over e。B sub一。F sub B。This should be。

Atmost one。So， this is the。Average gain。Is less than epsilon X I should put one plus epsilon because。

Your constraints are F sub B less than equal to one。Okay， so the average gain is。most one per。

C our task is just this instead of all the capacities。

 you're just given a broader distribution of the edges and your goal is to find a flow with the summation piece of Bf subB at most one plus epsilon。

Okay， so is that clear？ok， so。Okay， so now this is a task to construct the oracle。

 let's try this like the simplest oracle you can try Okay， the simplest oracle you can try is well。

 what are we trying to do。Okay， we're trying to essentially in another way to say it is。

 we're trying to minimize this average gain。On a float。

You want to find a flow that minimizes this average game。系。That's what the re is trying to do。Okay。

You know a flow is just a complex combination of paths right here to send some amount of flow on every path on。

Now诶。So it makes sense that if you are trying to minimize this。Average gain。

 like this quantity submission， P sub B， F sub B。You send all the flow in the shortest path。

Shortest path with edges P B。Like if。MyIf I look at edge weights。If I click my edge H to be PB。

I have a graph now evaluates at P of B。Okay， so now I need to send the F units of flow from S2 T。

There are no capacities right now right there are no capacities I just need to send F units of flow from on this graph。

诶。And I want to minimize this total average gain。So the best thing is to sort of pick the shortest path。

嗯。So here's an oracle， treat P or B。As it eats。Okay。Compute the shortest path， compute。

Shortest part from S。And you just route F units on route。F units。On this part。

Okay is the most natural children thing could try。Well， okay so。嗯。Firstly。对。Okay。

 there are two cases right。The length of the shortest path。It length to the shortest part。

 let's say it's less than one。If the length of the shortest path is less than one。

 then all the flow is going along that path。Right， so the total。Sorry。

 so Lent to short price is 1 over， so let's say Lentil the shortest part is1 overf。

If lengthent source plus1 orF， you're sending F units of flow on that。So therefore， the total cost。

The summation P sub B， F sub B will be like1 over f times F。This will be at most one， okay。

 that's what exactly what we wanted。Remember， we want to find her。

Thing without it gained one perception one。So that's fantastic。And。Okay， that's good。

On the other hand， if the length of the shortest path。I。At least is more than1 or。Okay。😊，嗯。

That means what is if the lengthil short part is at least one over f， that means that every flow。

For every flow。Subummissionation P sub B， F sub B is at least one。Okay。

That means that there is no flow。嗯。With。Average game。Or， you know， average violation。

Less than epsilon。Okay should put an epsilon everywhere， but yeah。佢唔。So， this means that you know。

 there's no flow with like you can just return saying there there's no way to route F units of flow。

Okay， we're trying to solve maximum flow in this algorithm。

 but as usual we'll do a binary search to figure out how much is the maximum flow。

 so we are fixing the F units and we're saying can we send F units of flow perity and。

So we run this algorithm basically for like a bunch of different Fs， is what I'm hearing。

And then we converge to F at the end。we do a binary research。

 so let's say binary research exists outside of the algorithm like it's like outside of the algorithm binary research is outside of that but what the algorithm is doing right now is just trying to find out if there is a flow with F units of flow from S2 T。

And。Yeah， the way we've defined a quao k is like that are easy constraints k。Defined so that。

It's really exactly F units of flow going into S and leaving T。

Okay and so right so this algorithm is trying to find out if there is some flow with F units of flow and then we'll keep doubling F and you know find out when it's infeasible and then we'll do binary research to figure out what what's a maximum value of the flow maximum possible so right now we're just trying to find out if there exists a flow with F units。

And。If it so happens that。Bake。We are in this case， so multiple weights find some edge weights。

 find some probabilities， P of V。And。There is no。嗯。No way to have a game。

The average gain less than epsilon。That means that。Yeah， there's no flaw。

With average violation epsilon， right less' epsilon。

 which means that there's no flow which surface all the constraints。

So does that implies the problem is infeasible or like what does what does the multiplicative white algorithm do with that Oh so that just means that the problem is infeasible as in you cannot route f units of flow from ST so essentially what happened is there are two players a multiy way algorithm is trying to find good pro distribution over edges to check and it has hit upon this distribution PB。

Such that no matter which way you try to flow， the average violation it'll see is at least steps long。

So yeah， but like what does that mean for the overall like solution like is it possible that like the distribution you just chose was like faulty or something and it could have chosen a better distribution that would have worked or something like that no the no the the distribution or edges to check right it's。

It's it's not like。嗯。So let me say this clearly， so let me say it this way so。Right。

 if there is a flow。With。Which doesn't violate any capacity constraints。

Then no matter which distribution or constraints you check。Your gain will be less than zero。

So what just happened is multi weight hit on the best possible distribution to check。

there are two players right so the multiweight algorithm is trying to find violations。

 the oracle is trying to find flows and what just happened now is there the multiy weight algorithm1。

 which means that there is no flow。A say there is no flow and so so we can just， you know。

 we can it can say return that there is no flow on the other hand if。Like， if there is a。

Shortest path was values less than one overf， then the record just returns that flow along that path and you just。

You know， you just continue and the algorithm continues for T steps and if the algorithm continues for T steps。

 you will just return the average of the flows from T steps and that will be your。Flow with value F。

 which has violations of one perpsilon。It's a two epsilon feasible solution。

 so every edge is violated by at almost two epsilon。B。就。You，In some sense， it might also be good too。

See what these。Piece of ease are right so。Basically， we're going to update。

Update the edge is multiplicativeily write the weights multiplicativeily。So if I look at。You know。

 if my weight on the edge E at time step t， t plus1， well， if you recall。

 it's equal to the weight on the edge。At time T times e to the epsilon times the gain。At。嗯。

The gayness。In this case， F sub E minus1。It is multiplicativey update based on the game。其 soべ。

Essentially， if you look at the total weight of an edge。

 it's basically e to the epsilon times the total flow that you have sent on it over time over the T steps。

Because you are updating multiplicatively its。This。The there is also a minus t。

 but that doesn't matter because it's just the same factor basically。For one you。

 it's essentially e to the epsilon times the total flow。So far on that edge。Okay。

 so these are the weights which the multiplicative weights algorithm is maintaining internally。Okay。

 so。So in some sense， so here's。Here's a nice example too。So by the way。

 I'm following a lot of things from。Unm guupta's election notess。Which are quite good for this。😔，So。

Okay， so here's a graph and let's say this is S and this is T。Okay。

 so really all the age capacities are one。Okay， so of course you can route two units of flow。

 you know one unit this way and and one unit， like I guess one unit this way and one unit this way。

 okay that's what you should do。But。What will this algorithm do， this algorithm will okay。

 initially all the weights are one， it' will find the shortest path。

So it will find the shortest path， so it will find this path。And send one unit of flow that way。Okay。

 this is a standard example multipl in Maxflow， right？

What let's say Edmunds carp and other basic max algorithms do is they have this idea of residual network。

 which lets you reverse the flow。On theSo what Edmdsk would do is they would pick the green path and then they would pick this blue path。

And you'd get two units of flowing， basically two steps。

But multi our algorithm right now is not going to be computing residual networks。

 so it's just going to keep flowing every time it will keep flowing one unit of flow。嗯，我。

And what will happen is it will。Whatly do， it will average the flow over time。So what happens now is。

 okay， it sends one year of flow this way。The other flow。So basically。

 whenever it sends a flow like this。You see that it increases the weight on that edge。Internally。

The multi degree weight algorithm increase the weight on that edge because the weight is a total flow。

So first time it sends a flow this way， the weight goes from one to。E to the epsilon。Okay。

 and the next time it routes that way， it goes from e to the epsilon t to the two epsilon。And so on。

It's multily increasing the weights of these edges。And up to a point where。

This path is no longer the shortest after log m mis， this path will no longer be the shortest so。

It will find a different shortest path。And then the other edges start becoming more important。

And after logM or epsilon square its， what you do is you'd output a flow。

 which is the average of all the steps flows， so you would have most of the flow going this way across the you'd get most of the flowing going two units this way。

 but the initial steps you would have used this other path。就。

So it's quite nice algorithm to play around with。All right。

 so how long does this take to converge okay， and to do that， we just need to figure out， you know。

 what is the parameters that we care about。Okay， firstly。Gmma， what was gamma。

 gamma is the minimum violation。At the minimum measure， the minimum value of。This quantity， AI X。

Minus B。The minimum gain。Okay， and note that in our case。

 the constraint that were looking at is f minus1。At minimum。

Value of this and you know our flows are always non negative numbers。

 so therefore this is always at least negative one。Okayith the way it's set up。

 it's almost negative one。Okay， so our gamma is negative one。Okay。The other thing is。Re。

 this is the more interesting quantity。 R was the maximum， the width of the oracle。

 So it's the maximum violation， right， So maximum violation。Or the bit is。What， what is the。

Maxum value of this quantity。Well， the worst case scenario you can send f units of flow along a single edge along on that edge。

 it might be sending f units of flow， so this can be all the way up to f minus1。So basically F。

Right and so。So this is kind of bad。Okay， we start with the unit capacity graph。

 the so which means that F was at most M。Because all its capacities are one。If all its capacity one。

 the worst best possible flow is am。So F is at most time。So but still， so basically a width is M。

Okay， so if you substitute these things， you get a run time。It is order M squared。Or epsilon square。

 I guess order m squared or epsilon square， which is not good， I mean， which is okay， which is okay。

 but。But this is for this is for the shortest path or， if you use the shortest path。

 the runtime can be order m squared or epsilon squared。

And the reason this is happening is the shortest path can， in the worst case。

 create violations which are M， which is f minus1。On an edge。嗯。In fact。

I would try to think it always creates violations of f minus1。

Because if it're using only a single path， some edge along the path will have F units flowing and then you have f minus1。

So。Okay， so you'd want to find flows that。Spread out the mass a little bit more。

 right shouldn't put all of the mass along a single path。ok。And then our goal is to improve the。

Wedth of this oracle improve this row quantity so that the runtime is smaller。Okay。

 so that's our goal now we want to construct this oracle， a better construction for this oracle。

The shortest part one was gave us the M and the better construction is just we use an electrical flow。

Right so if I have to use electrical flow， I mean the computational electrical flows are ease fast。

 it takes o tilda m stem time to compute electrical flow， so efficient implementation。嗯。

So what do I need to specify， I need to specify the resistances。Okay， so the resistance will use。

Is going to be the。Probably is P B， which makes sense because if the。嗯。

Multlyweight algorithm is going to check E E， we want to satisfy the constraint on the edge so we want to increase the resistance there。

Plus Epsilon over。😔，M。Okay。This is going to be a resistances。Use these residences to compute。

Electrical flow。That we call use。If hat。Is the electrical flow？Okay。So okay， that's fine。

 You can compute this。 The key thing to check now is what is the。

Does it satisfy the average gain constraint？And what is the width？Okay。

 what's the width and what's the average game？All right。

 so let's calculate the width first width is the easier one。So before we， okay。

 so for the electrical flow or record。Okay， what is the。With then what is the average gain？Okay。

 in order to do this first， lets just。Make the obvious observation that electrical flows minimize energy and that's what we want to start with。

So。Okay， so suppose。You know， F star is the best max flow。Is the optimal max flow？opptimum。You know。

 optimalpt max flow as in a flow that doesn't violate any capacities。

what is the energy consumed by Estar？The energy of Fstar is basically。S over F star E whole squared。

Times are be。All right， now I mean the optimal max flow that we're looking for if there exists one。

And we're assumingsuming that exists one， we're looking for it。If there exists one。

 the optimal one satisfies all the capacity constraints。So of course， all the flows are at most one。

So this is at most one squared because all the flow is on every edge。The flow will be most one。

It's one squared times what are the values of the resistances well we know what we used。

 we used P sub B plus epsilon over M。Okay， so what does this give us， this gives us。

Some over Eピ or B。pl。Epsilon times sum over some or M。Times the number of ages。是。这是 the shape嘛。

So this is one plus epsilon。Okay， basically by our choices of resistances。

 the total energy of the opt this came back from a search。I don't know， did I say Google？

My phone started just talking to me。So。So yeah， the energy of the optimal max flow is at most one perula。

Okay， which means that energy of our electrical flow will be only smaller because that's what it does right energy of Fta is going to be smaller than energy of this optimal max flow。

And it's going to be one plus epsilon。And recall energy of F hat is just。Submission， piece sub。所以。

Some over。If hat E squared， R。Is at most one pluseppsilon， right that's what we get。Yeah。

So that's good， Okay， so we are。We have some handle on this， the electrical flow。

So now we can use this handle to first bound the width and then bound the average gain。

The two quantities that we have care about。Okay， so let's see what the grid is。Okay。

 what's our basic factor regard sum mentioned F hat E squared R？Is at most one plus epsilon。

Given R is actually。Summation if had T squared。PE plus Epsilon orM。Okay， that's what we have。Okay。

 so now okay， now it's just。Okay， now what's the width？With or the maximum violation。几会。Well。

 width or the maximum violation is basically how large can a flow on an edge be？All right。

 we know that。We know that for all edges E。Like， F had E。E squared times epsilon over m。

Is at most one plus epsilon。Right， that's just， that's just because they， you know。Here。

If the total energy is at most one perceptpsilon， then you know， of course。

 this is one of the terms and every term is non negative。

So this implies that F hat E is at most square root of M or Epsilon。So that's good so we got。A width。

The row parameter would be square root M or epsilon。If you recall our shortest path。

 oracle had a width of m， this has M or epsilon square root time。

 so it got from m to square root time so it's improvement in the width。This is improved， right？嗯。对。

Allright， now。What was the other quantity we care about， it's the average gain， so just to recall。

 it is this quantity。Because note that our oracle is required to output。诶。

A articleal is required to find an F。With whose average violation。

 the average game is at most one per。Okay， so that's。So we want to bound sum mentioned P sub B。

 F sub B。Okay， and what we have a bound on is。Sation T sub B， F sub B squared。Okay， so like you want。

You want to do this， so I guess it's natural to try to do kushi Schwartz in these sort of situations。

 so you'd do kushi s Schwartz so they say this is at most。Submmission thea B。To the half。I sum B C B。

S sub B squared to the half。So， this is a。Is that right？Yeah， I think that's right。

This is Phi shorts。对。All right， so the first term is， of course。

 one because it's a probably distribution。The second term is。No， it's just the。

It's just bounded by one plus epsilon。From the from the total energy bound。系的。

Because some mentioned p subb， F subB squared is sitting in here。就。This is from total energy bound。

So we end up with the whole thing is at most one pluspsilon。Okay。

 so the firstly the oracle satisfies the average gain constraint。

 its average gain is organized at1 plus epsilon， and it's width is better。

 it's width the square root time instead of the shortest part thing， which is M。Okay。

 so if you put this together， so you put multiplulating weight of these electrical flows。

You get a run time。Which is。Order roll lawn。M over epsilon squared iterations， right？

This is what it is， but this is going to be in row gamma row gamma London， so this is going to be。

Gamma is one。R is square root M。L name。Or epsilon square its。

 so it's basically o tilde square root m its。And in each iteration。

 what you need to do is to solve a appplian system to compute the electrical flow。

So in each iteration， you need to compute electrical flow， so the total run time。The actual runtime。

Is。What t does square root time。Times the computer electrical flow is or tilde m so you get o tilde m to the three halves。

Okay， this is the runtime of the algorithm。So the。So。系。

So there's a question about when does this gamma row long n by epsilon squared bound hold the multi weights bound。

 its quite it's a little bit confusing but it's really you have to assume that gamma is at least one。

啊。Or I mean， gamma and row at least one Suan this holds。Now。Okay， so so that's。Right so we okay。

 this is good。 I mean we' got m to the three hps it's quite a clever algorithm and this should be nice except that you know。

 there is already an algorithm， I mean or when this was this algorithm was discovered in 2010。

 there was already an algorithm from。Mid 90s， which gave you M to the three halves。

Even on directed graphs。 So all the everything that we're talking about right now only works in undirected graphs because。

TheseAll the electrical flow machinery only works on un graphs。But leaving the reside。

 we got an approximate max flow under graphs with them to the three hs。诶嗯。闹。

You can actually use this technique to go beyond m to the three hals。所 you so。One can get。

M to the fourth third， I'll give them。Using by modifying this thing and this is actually beats all the old。

All the old algorithms like you based on preflow push and you know Edmunds car and all the other combinator techniques。

 you look at all the old combinator techniques that give you algorithms for maxflow。

 the m to the fourth third actuallybles all of them。But don't， but a it I mean。

 there are two caveats there when I say beats， it computes。And it works only on undirected graphs。

Which is。I guess its not such a bad thing because。Yeah， it works in underative graphs。

 the second thing is it's also approximate。So。Approximate as in the runtime has an over epsilon squared in the denominator。

If you want an epsilon approximate flow， it takes。But it beats all the earlier combinatatorural techniques。

Okay， and。And but this you know， this m to the fourth third really was the first improvement on just MaxL even on undergras for a long time。

 I guess and。this led to subsequent work。Right now。

 the best algorithm for Maxflow on undirected graphs is m to the 1 plus epsilon。I guess。

Maybe it's better than them to them， but basically its time to the one perception it's nearly linear near time。

 maybe just say nearly linear near time。So now we know nearly linear time。

Approximate max flow on undirected graphs。That's what we know already。嗯。

And whether you you can do a max flow in directed graphs in linear time is one of the big open questions。

 I mean not just big open questions， it's something which people。

Have been chipping away it it's something which seems not 50 years from now but maybe five years from now within the next few years sort of a thing。

Yeah， but yeah， there's a lot of work on that going on。Okay。

 so I should say let me say a little bit about how this m to the fourth third algorithm works。Okay。

 so the it's。No。So what is the issue here， the issue is the width。

 really the main issue in all this is the width。Wdth of the record。

 which is basically what is the worst possible violation of the congestion that you see on an edge？

And in in the electrical flow it can be square root time Okay， and so the。

So the modified algorithm is just that it's just the following。

This is a modified oracle or modified algorithm， I guess。ok， let's say you。嗯。

I guess let me just say following the modified algorithm is basically as follows you compute electrical flow。

And you see if all the flow values。If the row or the max or E F F had E。

If this is smaller than m to the1 third。You use it。Otherwise， if。

There exists in H E such that the row is more than f， it's highly congested。

 meaning you're sending more than m to the one third flow on it。What you do then is you just。

Delete the red。And you continue the algorithm after deleting that。Okay。Basically， you delete the rat。

 compute electrical flow， and repeat。Okay， and。You know。

 it's a bit hacky in that sense because you're basically deciding to delete edges from this。

Max flow network。And continuing to execute the rest of the algorithm just as this。and of course。

 by brute force， you're enforcing that your width is always at most same to the one third。Okay。

 and so。If your deleted addresss did not have much effect on the flow， you'd be happy。

The tricky thing is to show the really important thing is to show that you don't do too many deletions。

 as in the deletions don't affect the max flow value。And you don't do too many of them。

And it has a very nice proof， I guess。I won't have time to do it today。

But it's a very nice proof where。You basically use the。

Effective resistance between S& T as the potential。So if you look at your graph。

 originally the effect to resistance between S& T is。At least one over m squared or something。

 the affect resistance。Between S and T is at least1 over m squared initially。

And you use this as a potential to say that you don't do too many deletions by arguing that every time you delete an edge。

 the effect to resistance goes up by at least some multiplative factor。

And there's an upper bound on how large the effect resistance can get。

 so you bound the top number of deletions。So this argument is sketched out well in unum with the selection nodes。

 but the algorithm is basically just this you use the algorithm that we just described。

Except whenever you see an electrical flow with too much flow on an edge。

 you delete a red and you repeat algorithm as。And。That's what。This is。Yeah。It。

I wish we could do this algorithm in detail but。I think we're running out of time in the class。

 we just have seven more lectures or I guess we on eight more lectures but。Yeah。

 we have other topics to cover。喂。嗯。But I hope you got a sense of how elect flows are used to compute this。

And the near linear time approximate max flow， eventually it doesn't use electrical flows。It uses。

Different different kind of algorithms， but many of the ideas are stem out of electrical flows。

The idea of preconditioning， especially the critical idea in all of this underlying a lot of this is the idea of preconditioning。

So at the end of the day。Max flow computation and everything if you stated in the world of gradient descent is。

Something like minimize some norm， let's say there's a matrix B and you want to minimize some infinitefinity norm of Bx。

Where access on。Fctor。Its it's some sort of non minimization problem in the world of gradient descent。

That is。LikeIt's just very simply stated， all of these electrical flow computation。

 max flow computation， all of these are very easily stated as some sort of non minimization or some matrix like infinity to infinity non minimization。

And it's natural that you know these gradient decent can be sped up using preconditioners。

 that's not surprising。What is interesting is that in the world of when the be comes from a graph。

 you can construct these preconditioners by combinatorial techniques， so for example。

 when we are using internally linear time lappl and solvers， linear time lappl and solvers。

 if you recall last time we use data structures on trees。And。

know the other way to construct linear a timeularrian solvers all uses this low threat spanning trees。

Other combinatorial objects， basically you approximate this matrix B that comes out of your graph。

 you precondition the problem by using a combinatorial object like a low stretch spanning tree or in the near linear time algorithms。

 they use a different preconditioner， which is basically you can construct these。

Spae graphs that approximate the original graph。In the form max flow computation。You could say that。

It's a yeah， it's basically the idea is some combinator preconditioners plus some form of gradient descent give you this。

These improvements。In these attitude terms。Okay， and so next class we'll start a new topic and talk about semi programming。

Thank you， Professor。Right。

![](img/06071532b4ee602442e47d6dcaac3f66_2.png)

是。

![](img/06071532b4ee602442e47d6dcaac3f66_4.png)

那就 said。