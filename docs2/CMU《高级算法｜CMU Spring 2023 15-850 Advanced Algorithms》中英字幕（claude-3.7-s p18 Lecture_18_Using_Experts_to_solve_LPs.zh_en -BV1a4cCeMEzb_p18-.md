# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p18 Lecture_18_Using_Experts_to_solve_LPs.zh_en -BV1a4cCeMEzb_p18-

So todays lecture we are going to talk a little more about solving linear programs using experts。😊。

And later on in the course maybe in a couple of weeks well actually be talking about algorithms for solving linear programs and really this is the first algorithm so right now you are getting the first algorithm to solve a linear program。

And we will just use the multiplicative weight algorithm or the hedge algorithm。

And really all you will use is this version let us say， of hedge。

 which just says you know fix an epsilon from error parameter then for any gain vectors。😊，啊。

Which line the range negative row to positive row。The hedge algorithm ensures that for any possible export。

 the average gain of hedge is comparable to the average gain of expert I。

Times 1 minus epsilon minus adjective epsilon， so there are both a multiplicative and an adddjective loss out here。

😊，As。Long as t is at least some some omega， there is some constant， maybe 4，8， something like this。

Rose square。Times log of the number of experts divided by epsilon squared。Yeah。

So as long as you run hedge for long enough， the average gain that you get in hedge is comparable to the average gain of the best expert。

 of any expert and hence of the best expert。😊，Up to the add and multid laws。Okay。Th to notice。

 this depends on the scale of the gain vectors， so it depends quadratically as the width so to speak。

 it depends logarithmically on the number of experts and it depends inverse quadratically on the error parameter epsilon。

😊，Absolutely。我我没完了。发院。然后。So at least as far as I understand this， this goes to like mid 90s。

 actually。😊，There is a good reason for people not being excited。

 especially people who solved LPs you know who were trying to develop algorithms for solving LPs。

 the runtime of the algorithm is going to dependverse inverse polynomially in the error parameter。😊。

Typically we like to have algorithms which depend like log1 over epsilon and not one over epsilon so this is this is kind of poor if you actually want to solve the LP exactly。

But if youre happy with approximate， as often we are， were very happy。So， this。The work I know of。

 So this is a work of Gregoriais。And kchon。I think and then there was also work of plotkin small tar plotkin Mo than tarish。

I might be getting the references slightly wrong， but is these are both in the mid90s。

And they realize this that this is very simple algorithm。Do。Okay， so this is the。

 this is the theorem that we're going to take。Take as a black box。

 And what we're going to prove today is that we're going to say given。And。AB。LP is of the form。

 let's say， Mac。What should I do。Maximize Cronpo x。Such that K X is at most B， X is non negative。

Let's say， a。Is。M cross N， M rows in n columns。And you know， appropriate sizes come。

 you know B is an RM， C is an RM。And we are maximizing this overall X belonging to R， of course。

The of this thing。Okay， I want to be able to solve， get。Solution。

 and I'm putting quotes out here because you'll see what。What what I mean， get a solution X。

And let me say that this is a feasible LP， so there is a solution to this thing。😊。

And so we'll get a solution in X such that。C transpose X is at least C transpose。

 Maybe I'll make it X hat so that it's clear。 C transpose X star。4。Any mean。Ex star that satisfies。

They help me。So it's actually super optimum， but， and。我这个。A X hack。

Is less than equal to B plus epsilon times the all one factor。

So I'm going to relax the constraints ever so slightly by an epsilon。Okay。嗯。

And the time that this will take。嗯。The run time。Will be。嗯。Well， let's see what they run。

So the runtime is going to be dependent on something called the width of the LP。

It will depend epsilon squared where epsilon is this parameter out here。

 and then it there will be other parameters out here you know。Poly in the LP size。

And you'll see how this will come out。我去。啊。Good。Good。So， for instance， you， you might be able to say。

 for for example， you might know that。Shrinking X hacked down by 1 minus epsilon， let's say。

Maintains feasibility。 It's what is known as a packing L。So you could shrink it down by a little bit。

This would satisfy these constraints， but now your your objective function would have gone on。

But this claim that I'm making will just hold regardless。

So what is really happening is that ax equals D is giving us this polytop Im giving you a slightly relaxed。

😊，Maybe I'll use the different colors。 I'm giving you a。Lightly relaxed body。

And I'm giving you a solution out here。Now， as we will see later on in the course。

 the ellipide algorithm also does the same thing。😊。

But the advantage with the ellipoid algorithm is that it its behavior on epsilon is 1 over you know。

 is going to be ellipoid will replace this in epsoid。

Eexide is actually a polyteme algorithm for for linear programming， the dependence。😊，On Epsilon is。

Long。Instead of one over polyabpsilon， it's log1 over that。So it's that that really gives you the。

Strongly， that gives you the polytime algorithm for linear programming。So right now， we are。

 we are being much weaker。Yeah。I'm sorry。So anllipoid came out in 79， I think。😊。

So these these are interpretations of yeah linear so this interpretation of linear programming solving came out in the 90s。

😊，So it it afterwards， it's worse， but it is a simple idea and it is very you know commonly used。

 in fact I will show some applications of this。😊，Yeah。好，你。はい。

In distance in the sort of Euclidean sense or something like this。啊。Ofhand。Nothing that can't be。

 you know， obtained from this thing。 I don't know of once off the top of my head。

 but we can think about it。There might be something we can get out。You'll see how this comes on。Okay。

Other questions。

![](img/5b1ddfca4559c2f20c34993483e44ec6_1.png)

Okay so let me show you the the algorithm so the algorithm is going to be fairly straightforward it is one that we talked about briefly last time。

 but let me just tell you the algorithm。😊，So the algorithm is going to be the following。

I'm going to have an expert。For each constraint。So there are M experts。

So I'm going to maintain probability vectors over M constraints at each point in time。

Well at each time。Im going to create， I'm going to take so here heres the picture that is happening here。

 this is a， this is P1， P2 up to PMm。😊，Im maintaining a probability distribution over vectors over the constraints。

I want to make sure that Ax。I is at most。啊，驴。So， what I am going to do is I am going to take an average constraint and the average constraint says alpha。

What is alpha alpha is is a rh vector， so let me write it as alpha transpose is equal to p transpose a。

😊，So I'm just summing up the rows according to these probabilities。Beta is just a scalar。

 this is P transop， this is Pt。😊，So at each point in time， I have a。

Probability which is being maintained by hedge。I'm going to use。Those probabilities。

To average out the rolls。O。Both A and B。I'm going to find。我 sorry。哦。The average constraint。

Maximize C transpose X。Such that alpha transpose x is less than equal to both。Okay听。

So this gave me a solution。Yeah。X T， let's say。Right now。

 is this is a solution to the average constraint。😊，And now I define the gain vector。Is equal to。嗯。

Times X B。Minus。A times xt should be less than equal to B。So this。

Is positive where I'm violating constraints。If I have a gain which is positive when I am violating constraints。

 the probability mass will tend to cluster towards the constraints that are being violated。😊。

puttingtting more importance on the violated constraintsstraint。

So the next time I will try it harder to satisfy them in this average sense。😊，This is game。F。G地。

To hedge。Do yes。Let it。And， of course， P1 was just the just the。Uniform distribution over countries。

啊。Is the algorithm clear。我以个。I feed G T to hedge。To get P plus。I had P1。Heage is that the month。对。我。

Oh。Thank you。哦。五个。Questions about that。The way I always think of this is look。

 this you know all the gain is doing is is just trying to push the mass into the violated constraints so that on average constraints are being satisfied。

😊，And that's， that's going to come out in the analysis。 The analysis is just going to be。We个。Let's。

 let's go ahead， okay。So I want to prove this theorem， the proof of the。猪啊。Ro of guarantee。

Up guarantee up there。嗯。So let me just imagine that X star。Is the optimal solution。It's， in fact。

 any solution to the LP。Okay， justs fix this guy。Oh， okay。

 I haven't told you an important thing I am getting a solution every time。😊，I want a solution X hat。

 So act。Finally， x hat is going to be for one is going to be the average。

Of all these little solutions。没有。And I'm going to run this for t equals some number of steps。In fact。

 I' am going to run this for t equals theta of row squared。

Log of little M over epsilon squared steps。Where row will be fix so。

And row will come out very naturally from here。The row is going to be the max。Possible value of this。

哦G地。Over。I'm just making sure that。Grow is just the upper bound on the games。In absolute value。

That's where the row comes from。we will see examples。 this is almost。By definition。So， fact1。X star。

Is feasible。For。This step， this constraint。I ask for a single constraint。

 right my claim is X is feasible for this constraint。😊，Y X star is feasible for this LP。😊。

It satisfies each of these constraints individually， so it satisfies their average。嗯。

Faavable for the one constraint。Okay。😊，So， this means that。

Xter the max value out here is at least C transpose X。对。If each xt has objective function。

 at least x stars value。Then， it's average。So this this just says therefore C transpose xt is at least C transpose x star。

Right， because we are。Getting the max。Therefore。The average of these guys。

 which is C transpose x hat， is at least also C transpo。回章。

We are always getting a super optimal value and hence their average will also be super。😊，Yeah。

Im having having difficulty getting an intuitive understanding of a regular portion of experience？

There way to。Like would have any meaning with picture you can think of you， for example。Maybe呢。Not起。

I I'll give an example in a minute。This hold on road like two minutes。Yeah。Okay， hit。Here's。

 here is what I can。 Let me drop it。I think it'll be useful。Thank picture。

I'm trying to maximize in this direction。The notice。

That these constraints are kind of useless if I'm just trying to maximize that right。

The only important constraints are。This constraint and。In fact。

What's really happening is we won't be able to move past this point， right that's the optimal。😡，やて。

Because we will be held back。By let's say the perpendicular hyperplan。This， this hyperclaim。

Is the average of this constraint in that constraint。That's the average were looking for。

That's exactly。To what we are doing。You know thank you for asking the question What we are doing is we are saying initially I don't know which constraints are important which are going to hold me back。

😊，Let me just start off with an average constraint， which is some， some weird old thing。

 I don't even know。But as time passes， I want to put more and more of my mass on these important constraints and finally the weights are going to be only on that and that's what this going。

😊，The proof is not going to quite work like this， but the proof is kind of like mysterious it will just drop out like that。

😊，But this is the picture that I keep in my mind。还问。不有问。

The average constraintsstraint should not become degenerate 0 less than 0。嗯。They。啊哈。😊，哦。对啊。

Let's see how it goes。Let let's hold on to that third let's see。O。So。

 I needed to show two things I needed to show you that x hat had good value and approximately satisfied the constraints。

😊，I showed you it at good value。 Now， I just need to show that it approximately satisfied with。Okay。

嗯。And all I'm going to use is I'm going to use that character。So let's， let's just do the analysis。

So let's just say the LHS， the left hand side up there。Is。The average。Time average in this case。好。B逼。

这点。What is this？In fact， let's let's just look at one of these guys。

 you know instead of taking the average right away， lets me just。Write this down。What is this。

This is the probability vector。Times。A X， B minus B。The definition of the can。The violations。

Which is。The same as。B啲。Transpos a。 I'm just moving this guy over。Inner product with X T。Minus。B啲。

I just opened this guy。😊，And I moved a over from this， this to this side。

But this is equal to alpha times xt minus。This is just the average that I'm taking。And this is。

Less than equal to0 because my xt was feasible。Okay。😊，都。Notice。

You know I am always working with this thing this thing is less than equal to 0。

 if a bunch of averages time averages over objects which are less than equal to 0， we just proved it。

😊，So I just need to analyze the right hand side。And what's the right hand side。

 The right hand side says this is EI。GD。What's EI GT？E I GT is。点爱。嗯。Yeah。

I'm taking the inner product。With this object。This is just。The eye is constraint。Minus。B i。Okay。

So if I were to sum this over all times。This is equal to the Ih constraint times x hat。Minus B。

What do I want this to be？I want this to be less than equal to0， right？This is what we want。

 We want the I constraint to be less than equal to0。What do we have？We have。

Hedge says0 is less than equal to1 minus epsilon times。AI transpose X hat minus B。M- capital。

I've just copied the hedge guarantee down here。And so this hedge guarantee says。

AI transpose x hat minus D is less than equal to epsilon divided by  one minus epsilon。

 whatever this is， some constant。That's the guarantee。We are saying are constraint instead of this。

 It's really。Some other constant， not important but constant。不看。Point I want to make。

 maybe I'll go back to this picture again。Want to say there was a weighting of these constraints。

That we should have chosen in order to show that the optimal solution was out here。

We don't know this waiting up front。This weighting is like the optimal weighting in some sense。

 what we are finding is we are finding a weighting which is as good as any other weighting。😊。

And that's， that's exactly what these constraints are doing。 John， you had a question。哦。你说。

You want to ask it anywhere。诶 sorry。嗯，这个。Oh in the tip， okay， so maybe I confused you。

The kem just says this。What we showed in our proof for the LP was that this quantity for us。

Was less than equal to the。So， this quantity is less than equal to 0。

 but this is exactly the violation of the constraintsstraint。😊。

So this translates to the violation of the constraints11 minus epsilon less than。Other question。はい。

反人对。好，这样。到。Okay， yeah， so you can't do this in poly time。😊，But suppose we don't worry about that。

Suppose what we do So you know， how would I convert this into an algorithm for solving LPs maybe I push this up in case people want to stare at it。

😊，Okay。So what do I do and this way we will see in ellipsy。😊。

What we are going to do is we are going to drive this epsilon into the ground。

We're going to make this epsilon one over。Polynomial， one over exponential。In the input lens。

And the picture I have is， well， this is。Kind of enlarged。By a huge amount， I want to be there。

 there that's my X。Im going to be within。三。Epsilon ball。

This is a different epsilon which is kind of the question you were asking as well you know what can I say about the L2 distance what I can get is you know。

😊，Just because of this， I can use like coi shorts or something like that to get some bound on the L2 test。

😊，So I can just make sure that x is very close to X。😊。

And x is so close to X that there can be only you know， one solution。I I'm going a little fast。

 but let me just say it and we we will do this in more detail later on basically because x is a solution to this LP。

 it has bounded denominators The denominators cant be too large Kraers rule。😊。

So what I want to figure out is I am sitting at this x。

What are the points with bounded denominator size which are close to extra。And basically。

 you'll be so close that there' will be only one point， which is that close to。

And that will be extra。 So use snap。And for those of you who have seen continued fraction approximations。

 this is that idea， but taken in higher dimensions。😊，It's you know。

 if you' are interested in this thing， look up simultaneous。Dofhanine。Equations。We。

 we'll talk about this later。 I'm just know riffing right now。But that's the rail point。

How does ellipsoid find this corner？Ellipide gets so close to this corner that the only reasonable solution is this one。

😊，What does reasonable mean， et cetera， we will get into that later， maybe an exercise。

 maybe a homework problem。😊，对。So。啊，对。So row depends on the LP。And basically， you have to okay。

 actually row depends on two things。Row was basically the maximum violation。

That that vector can have。So it depends on two things。Firstly， it depends on the LP， of course。

But B depends on your procedure for finding solutions out there。

If you always found me Xts which were which had low violation， I'd be very happy。

And you might say you know there is a chicken and eggie problem。

 but thats what we will do in the rest of the lecture。

In the rest of the lecture let me tell you what I'm going to show you。

what I am going to do is I' am going to give you an algorithm for finding max flows。

 you know how to find max load， but I will give you an algorithm for finding max flows which takes order m squared time。

😊。

![](img/5b1ddfca4559c2f20c34993483e44ec6_3.png)

![](img/5b1ddfca4559c2f20c34993483e44ec6_4.png)

And you will say this is boring， this is not really interesting because I can find max flows faster than there。

But then I'll show you an algorithm to find max load than m to the three half star。

Using a fancier way of finding。Of solving that problem。

 of solving that that that first step average problem。And if I had more time。

 I would give you an algorithm for solving this in time m to the4 third。

 which 10 years back was the state of the art。😊，And all this is going to proceed。

 we are just using this machinery and it is going to be just almost blindly using this machinery plus one smart ID。

😊，So in this case。😊，You need not know row ahead of time。 So what you could do is you could say。

 oh row is going to be one。And any time you got a row， which is too large。😊。

You can throw away everything youve done so far。And doubleub your row and go。

You don't have to throw it away， but it's the easiest way of doing that。嗯。Exactly。

 so what might happen is because row you you realized or row is bigger than I thought it was you might have to run for more rounds。

😊，But because you are doubling row every time， it is like the time is dominated by the largest row that you will get。

😊。

![](img/5b1ddfca4559c2f20c34993483e44ec6_6.png)

So it's only a factor of2 or4 or because it's a geometric zone。Excellent question， Other question。

Okay。可能。So let me tell you about Max loss。So what do I want to do， I want it all max。

So right of the band， I'm going to write a cravvy LP。

We want to write an LP with an exponential number of variables。Not a problem。

So I want to solve max law。And in fact， I'm going to solve max flows with unit capacity edges。

Some of this can be extended to general capacities， in fact。

 all of this can be extended to general capacities， but it requires more effort right now。😊。

Unit capacity graph。So I'm given a graph。For the time being the graph can be directed later on we come to undirected graph。



![](img/5b1ddfca4559c2f20c34993483e44ec6_8.png)

嗯。Edit of capacity one， I haven't sourced。Yes。I have a sink。I want to find a max flow。

And let's say that the max flow value is equal to f。The maxax flow value is equal to f。

 and just so that you remember。

![](img/5b1ddfca4559c2f20c34993483e44ec6_10.png)

This is really the classic example of max flow。 This is S， this is T， A and B。😊。



![](img/5b1ddfca4559c2f20c34993483e44ec6_12.png)

Edges 1，1，1。 Okay， everything has unit capacity。 I'm not going to write it down。

 The max low value in this case is 2。嗯。And the the the flow， the max logo is like this。Yeah。有。

Of course， the greedy algorithm， you know， this is all sort of stuff that you've probably seen the greedy algorithm might actually push a unit of flow。

😊，This way。And then you undo it by pushing， you know。

 you construct a residual graph and you push one unit of flow back。And so in the residual graph。

 this edge flips。 but if you don't remember it you don't even have to worry about it。

 you should look it up later。你看。Okay。I want to solve Max flow this thing。 I'm want to write an LP。

I want to solve that。And the LP I'm on the right is maximize。😊。



![](img/5b1ddfca4559c2f20c34993483e44ec6_14.png)

This LP has a variable for every part from ST。😊，And this is saying。

 how much flow am I sending on part P， F P is the amount of flow I'm sending on part P or all parts P。

 which goes from S P。 So P， you know， this sum is some。Overall。Parts。

 maybe exponentially many parts from ST。诶。Such that。If I look at all the parts。

So that a particular edge belongs to that path， it is at most one or in general the capacity of the edge。

😊，For every edge of。An F P can only be non negative。Okay。Think个。We O Lp。Great LP， actually。

Most of the time I don't write LPs with clo conservation and stuff like that it is a little annoying I just write this one。

😊，We got。This LP has an exponential number of variables。😊，But a linear number of constraints。FPO。

 apart from these constraints。嗯。Okay。Good。To let me。Work。Our algorithm through this。

I have apart from the non negativity， which I kind of already you know put aside。😊。

Apart from the non negativity。嗯。Let's look at this， I have one constraint per edge。

So I'm going to have one expert per。

![](img/5b1ddfca4559c2f20c34993483e44ec6_16.png)

So I'll be given。 So lets say know what is this thing going to give me given。

probabilityb vector p I am not going to write p because you know it it is clear P belongs to the probability simplex on M items。

 one per edge。let's look at the average constraint。What's the average constraint saying？

Some overall ages。B sub E。Times some overall all。It's capital P。 Okay， I'll， I'll try to write。

Capital P， carefully。And this is， this is a tiny little P， maybe。Will I confuse myself。

Given a probability vector Q， all my probability vectors are now going to be called Q。比一。B。

If less than equal to some overall ages。Of Q E times1。Right hand side is one。

Left hand side with this。Okay。So what is the right hand side， it is a probability distribution。

 so I just get back one。😊，Whats the left hand side。

 let me just have two summations I should you know immediately flip them around summation FP。😊。

And then summation over all ages E。Such that。B。Belongs to。嗯。枸铁。Okay。What is this。

If I look at some parts。I am summing over all edges， E， E1， E， E1， E 2， E 3。Or E5。

 each of these has a probability value。😊，I'm summing over these guys。So。

 this is really equal to really length。😊，Of the part B， if you view the queues as being edge length。



![](img/5b1ddfca4559c2f20c34993483e44ec6_18.png)

I gave you probabilities。On each of the edges of the graph。These are just numbers。

 not negative numbers。You should think of them as lengths。I am asking for the length of the path P。有。

打电话。被疗费。我了。Blow conservation。Yeah， so this one is much easier to cast into this framework。

I think the other one also works out， but it is a little more annoying to deal with。

But this is just saying。I'm just rewriting this。Its F of B。Times length。

Of P according to the probability value given by Q。What do I want to solve？

I want to just say this is the same as the inequality。Some overall parts。

Some flow that you want to hang on the part。Times the length of the part。

You want to check whether this is less than equal to one。这。Oh， I forgot to write。嗯。Good， thank you。

That's fine。What am I doing。I gave you a probability vector Q。For every part， this gives me a length。

I am trying to push flow。So， that。This constraint is satisfied。 How should I solve this？

I have just one constraint。On the side， I have constraints FP is non non negative。

And I want to maximize。上业线。So let me just abstract out parts are something， right？So basically。

 I have variables of the form F sub I。Times the size of pi。Is less than equal to1。

 and I want to maximize formation F sub I F sub I the non negative。How do I solve this？

I picked the smallest item here。And I said F to be equal to 1 over S I。

That will maximize this quantity。What are the sizes here， the sizes are the lengths of the parts。

What is the smallest length of the park？The shortest back。So all this is saying is。

 find me the shortest path。W slow on that。Findin me the shortest path。If it has some lamp。

W flow equals one over that land。That will solve the。For the the。

The algorithm says this algorithm says， therefore。아 algorithm them。Solving。Okay。Average constraint。

Says。Find。Shortestpan。With respect to the edge length。Yeah。Ft。

FP is equal to one over the length of the shortest path。And repeat。Does this kind of make sense？

So what we are going to do。If we are going to in on on this instance， here's what we will do。

Let me choose a slightly better instance。Actually。めて。Here is the graph， S。

What's the shortest path in this graph？Pro S。Just weights are one lit。睡。It's thispat。

If you want to sign a max flow， should you be sending flow along that path？你咧。

What's the max flow in this graph？2。And what's a unique maximum。

The unique max flow sense flow this way。先争を始しめ。So if you send flow along this path。😊。

It's like a dead end。 It's using up this edge from one of the max flow parts and this edge from the other max flow part。

 is giving meaning， you know， it's kind of。Clogging up the network。Yeah。This algorithm says step1。

Sandflow in disk。Okay。Not a good idea， but not what the heck。有的。

You send one unit of flow and maybe Ill use a different or have color is green。

I send one flow on this map。Now我 happened。I send。This information back to hedge。

What hedge does is it increases the length of these edges。By one plus epsilon。These three ages。

 the the three ages。Now what's going happen next step？Well。

 maybe I'll still still push flow on the same path because this path is off length3 times  one plus epsilon and this path is off length 5。

😊，So I still some push some flow on the same。Now this guy has become one plus epsilon squared。

The the congestion is increasing rapidly。John。These parts。

 these pink parts will become the shortest path。So you will send flow along those。

And then occasionally you will send flow along the green path。

 but if you actually do the calculation after a little while after a constant number of time sending flow along the green path。

 the constant depending on one over epsilon。😊，You'll stop sending flow in the green path and you will only send flow along the pink path。

And finally， you leverage things out。When you average things out。

 there will be a tiny bit of flow that will be due to the green guys and most of the park flow will be due to the pink。

😊，And that will be pretty much， you know， everything is converging towards。The maximum。

That's what this algorithm。At each point in time， it's got to find。

One shortest back push flow along that。And then it's going to increase the length of the edges on the shortest path by one plus epsilon factor。

That's the， that's what the algorithm。You know， I can do the rest of the thing， but it's not。

 you know， not important how I。How为 do的。nolysisOK的， thank。We only absolutely like exactly。

 So at each point in time， itll pick the pink path。

 you know one path and the other path and then it will just oscillate between。😊。

the green parts be more good so so in this example that is what I initially thought。

 but what is going to happen is that every time you pick the the pink parts。😊。

You are increasing the weights of at least one of the edges on the green path as well。

 so after you picked this pink path and this pink path， the green path is getting hit twice。

And somehow， you know， after a few times it becomes so much that sort of it's never a good idea to choose these。

 It's always better to choose。Again， I have a Python notebook， and I'll share with you guys。

 You know， feel free to play with this。's that's how I get my intuition。 right。

 play with the damn thing。😊，On on paper， I used to do it。

 But now I why should I do it if I can do get Python to do it for me。Yeah。Yes， and in fact。

 that's all。All the algorithms， it really boils down to a clever way of finding the R max。

Because it's a single constraint。😊，How hard can a single constrain？I mean， it can be but。

Between friends。So it it really it is exactly the same algorithm。

 its just that I am observing that because I wrote it this way。

 this single constraint is just the shortest part computation。😊。

So it takes me linear time to find one augmentation of this thing。

And then I have to do this some number of times。How many times do you have to do this。

 it depends on the width。😊，And so it really comes down to what is the width of this。Hay。

And that's what we have to look at more closely， but let's take a two minute break let me change this slightly it will make my arguments a little easier。

😊。

![](img/5b1ddfca4559c2f20c34993483e44ec6_20.png)

Suppose， I know。Using let binary search or something。

 suppose I know that the max low value is equal to F。Not important， but it just makes my life easier。

 Im going to write down one more constraint。 In fact， instead of saying， maximize this quantity。

 I'm just going to say this quantity equal equal to。The max low value was equal to where。

So Im just saying the total amount of flow I am sending is equal to air。Subject to these constraints。

Now， it's a feasibility LP。No big。So I can do the same thing as before。

 I can say instead of maximizing FP。I'm just saying FP sums up to it。系。This is my my constraint。对。

Yes。不可。There is an optimal solution。It satisfies。This constraint subject to these inequality。Optimal。

Satifies the optimal flow satisfies these constraints， this constraint subject to these inequalities。

够。In fact。In this case now I don't need to worry about what the length of this path is going to be。

 I am going to set on this path on this shortest path， I'm going to send f units of law。Just。

 you know， I know that this， this has to be satisfied。 so what did I do， I chose the pink path。

 I sent two units of four now because F is2 capital F is 2。Then the green part。

 I send two units of law。 So each time I'm sending F units of flow of the edge。Okay。

That's how I'm averaging。Every time I'm signing maxlow units software。

So it makes my life easy because now I can ask the question。

The only constraints that are of interest， you know that we averaged out were these constraints。

If I find one max one shortest path and push F units of flow， how much can this be violated by？个。

Okay。😊，So how many rounds would I have to run this algorithm in f minus1 is really f。

So the number of rounds。See that most F squared times log of the number of constraints。

 which is the number of edges divided by。I need to run so many max flows。

In order to find the you know1 class episode on the Proation。Yeah。

Every max load takes linear amount of time because it is really by extra algorithm。M plus and logia。

This is my run time。Or第三个。And I'm not going to you know， worry about optimizing these things locally。

 I want to give you。One new idea。How big can Fb， by the way。

 what the max flow what is the maximum max flow value？M。你。So this could be like M。这。Whatever M。

 So this is like ms m squared times M that's m cubed。

Not the greatest in M cube runtime we don't like。对。So we can do two things to improve。The， the setup。

Here's the first thing。And the first thing I'm going to just change a couple of letters on this guarantee。

And I'll just say， you know， it must hold true， if guys shouldn't believe me， you should check。

The guarantee that I'm going to give you。Is if this thing was between negative lambda and positive row。

 lets say then this row squared is really a lambda times zero。You can prove。

It's the asymmetric version of hedge。Whatever。Okay。Yeah。

So now what you should really care about is how much is this inequality going in both directions。

 how much can it violate and how much can it sort of become satisfied。😊。

This quantity lies between 0 and capital F。So the violation is ut most error。

The the the lowest this quantity can be0， so then really the gain vector the gains。In this case。

 lie between negative 1 and capital f 1。Now， the good thing is that instead of this f squared now I only have an m because it is 1 times f。

That's already a faster algorithm quadraing。But that wasn't the idea I wanted to tell you that's just。

 you know， it's an optimization that we know。Here's what I want to tell you。How do I。

How can I reduce things？Suppose I had a different way you know what was the real problem The problem was whenever I solved this this single constraint。

 this average constrained problem， my flow all went on a single path。😊。

If I could average my flow out。If I could kind of load balance my flowaw。😊。

So that no single edge used a lot of the flow， I'd be very happy。😊。

What's the best way of averaging out the flow？So that no single edge uses a lot of flow。

It's this healthy。But wait， this is the problem we are trying to solve， right。

 It is a chicken and egg problem。I want to send F units of flow so that no edge uses too much flow。

 It is a max flow problem。 I want capacity constraints to be satisfied。😊，I didn't want to do that。

 That's why I average all the clothes together。 or average all the constraints together。

 Then I got shortest parts。 All my clothes started going on a single path。😊，Don't like it。

I want some kind of load balancing。But in a way that I can compute it fast。

And this was an idea that came out of a very nice piece of work。嗯。And they used， okay。So， let me。O。哎。

So this。Yeah。Was an idea due to actually this idea was floating around for some time。

 but it really came together in this paperwork。😊，Christiano and company won the Fox or Stock Bestpaper award a few years about 10 years back now。

They do的 following。So remember， what do I want to solve？I want。

I want to solve the single constraint problem， So I want to say sum over parts P。

 I want to send F units of flow。FP are non negative。And。I want to solve with constraint。sation f B。

Times the length。呃。Of P， according to the lens Q a。I want to solve that， but I don't want。But。Don't。

 but want to spread out， but wont。Do stay。是。I want to solve this problem really fast。

I want to send F unit of flow。It doesn't matter You know， by scaling。

 this is really like one unit of law。嗯。But I dont want I want to send along short paths。

 but I dont want to put all my eggs in one basket to mix my metaphor I want to spread my flow out。

And for this， they used the idea， so this idea。Idea number you know there are a lot of ideas in this lecture。

 maybe idea number three in this lecture。😊，Is use。And来看看。So here's what I'm going to do。

I'm going to view my ST network。Oh， by the way， so this will work only for undirected graphs。

 so now I have to restrict myself。😊，Why I take that。

Versionions of this can be extended to directed draft but that requires a lot more work。😊。

Here's what's going to happen。 I'm going to take an undirected draft。Okay。

 they keep drawing directed graph。This is S， and this is T。I want to send one unit of flow from S2 T。

So here is what Im going to do， Im going to take S Im going to view each edge as a unit resistor。

Im going to take S and I'm going to attach it to a battery。

I am going to take t and attach it to the other end of the battery and I am going to compute the electrical flow this is going to push let us say you know there is one unit of voltage potential difference between this this is going to push some amount of flow。

😊，Electrical flow。Now， electrical flow has this very nice property。That if you set up you know。

 some potential difference between two points。The flow goes in a way that minimizes the total energy dissipated。

And for this， you have to you know remember your whatever electrical physics classes that we had。

 how much energy is burnt on an edge。😊，They then I squared out。

So it the if you have flow e on an edge， it's f squared。

 so this is the amount of current flowing on the edge times the resistance。😊，And they told us。

Energy is this。 So I'll call this the energy bond of the flow。

And electrical flow flows in a way that minimizes the energy part。No question。

Suppose you were sending flow from S to P。And they were two parts like this would they would would the electrical flow go only on one edge or would it split between the two。

It would split right because if you have half the half the current that a square you know that is a square sitting out there。

😊，That's a quarter of the energy bond per part。 So that's half the energy。

So it's going to try to spread it out。He doesn't want to send too much flow on a single edge。

Because that will burn too much energy。Let's spread it on。对。So the question is。Why did we do this。

 we did this because we wanted to spread out the flow。We we wanted to find some flow from S to T。

Whi did not use any single edge too much。Furthermore， we wanted to find this fast。

That was that thing。 We want to do this fast。 So， and we want I forward to。I want this time。Hfully。

 for us， computing electrical flows is going to satisfy both the constraintstrain， both the property。

😊，Firstly。Will be able to show。So， you know I'm not going into the details well be able to show that the width is at most square root m over Xlon or something like。

So instead of the width being M as before， the width becomes square root。骂七八了。And， secondly。Can。咁标。

In nearly。I'm cheating。Yeah。Why am I cheating， I am going to not satisfy this。

 but I am going to satisfy slightly weaker。😊，But if you work through the calculations。

 you will realize you know instead of finding this instead of finding one if you get one class epsilon。

 it doesnt hurt you too much it okay。😊，You are already finding approximate clothes。

 You can just fold in the approximations everywhere。And it seems almost magical。

It is magical but you know there is a science behind this so let me in the last five minutes at least tell you the main ideas you know the width being square root time over epsilon the square root is really coming from this contracted。

😊，It's just saying do not push flow on a single edge。 you know， spread it when you can。

And that's going to be the important idea。 You， this square will give you the square root。

Some details， not important。 Let me tell you the main idea behind computing it in Ne linear。

And for that， lets let me introduce。1。Character which hopefully you guys have seen before。

 but if you haven't， then it you know it's going to become a familiar friend。😊，我 were带。

So how do you compute this in a linear time？You use the idea that computing， that。对。Actually。

 it should be a carra， I guess。This min energy flow。Okay。嗯。Electrical flow。嗯嗯。

Can be computed in the following way。 Is the solution is。A solution to。To。

 to a system of linear equations。So what's this linear equation， Let me just introduce。An object。

So is a solution to something well get to that。Will define。The Laplaceian。Matrix L of a graph G。

 So I'm going to write Lg even though you know soon I will start dropping with G。

It's a square matrix。There are n roles。There are n columns。喂。😊，What is the IJth entry out here？Okay。

 so firstly， the the diagonals。Are all going to be。Thereero is。The simple graph。And the off diagonal。

You know， the I J entry。The LI J is going to be。One， you know。

 is going to be one over the resistance of IJ if the edge I J。Ex。

And it's going to be vital other ways。You could just imagine that the resistance is infinity。

 which naturally leads it to just being here。It is a symmetric matrix because we were talking about undirected graphs。

And so the min energy electrical flow is the solution to the following thing I want to find I want to multiply L the lapplaceian。

By the potentials， the voltage is at every voltage。Such that L of phi is equal to。嗯。Let's say。1。Yes。

So， this should be。One， if the vertex you know L of I。

 the ih coordinate is going to be1 if i is equal to S， negative1 if i is equal to t and 0 otherwise。

This is just saying I want to push one unit of current from S to T。

What should my potentials be at the various vertical here。Which will achieve。This kind of electric。

It's a little。I' mysterious。So so phi of v for a vertex v is equal to the kind of voltage level。😊。

Or potential。I。It is just saying what should I you know what should the voltages at the various voltageticCs be？

😊，So that I'm going to achieve this kind of law。第一个。对。

Exactly fee the assignment to ver okay that is a good point the fee giving me voltages。😊。

And then I'm going to then use。 Then I'm going to say that the flow。Yes。有味。Is given by well。

 if you have voltages at the various vertices， what should the current be。

Everything back to oms law I you know again Im pulling this out of a hat is the potential at U is the voltage at u minus the voltage at v divided by the resistance between you。

😊，So， this will give me a solution to how you are going to send one unit of flow from S2T。

What voltage difference should you maintain。And this immediately gives me clue。Bottom line。

 in order to find this find this current， you needed to solve a linear system like this。

This linear system in general， you would require Gaussian elimination， but。

Because this is the Laplaceian。It's coming from a graph。

And you can use this connection to solve these linear systems。 So the theorem really is。嗯。

Linear systems。Lx equals B for L being the Laplian。Of a graph of an undirected graph can be。

Approximately solved。嗯。linear尼感。Where M is the number of edges of this front。啊， sorry。

So it is like various pieces coming together。Firstly， you need to solve linear systems very far。

Corresponding to Laplaceians。And this is this is some is actually CMU technology this actually came out first due to work due to spman and tank in 2004 Shaanghua Tenang used to be a PhD student at CMU。

😊，Back in the day before my time actually。But then this was simplified by Kts Miller and Pang Richard Pang is currently a faculty member out here Gary Miller used to be on the faculty until he retired two years back and the Quts and Peng were grad students here when they simplified this I think this was five and they gave much simpler implementation much faster and simpler implementation of this stuff。

😊，Of solving linear systems。Solving Laplaceian systems in near linear time。And once you can do that。

 you can find the approximate flows and these flows have small width， so you are in great。

But the model， okay， so the real moral of the story is。😊，The width does not just depend on the LP。

 It depends on how you find the solution。Sometimes the obvious way of finding the solution has large fit。

😊，But if you are smart about it， you can get a small width approximate solution and then you are in。

Let me stop here， and。Will， will continue on Wednesday。

I might not say much more about solving flows fast using these LP you know I would love to tell you more about lapplaceians and stuff like that。

 maybe I will but maybe not on Wednesday。😊，We will take a little break。

 We' will talk a little bit about。Connections to。You know。

 this hedge algorithm I just gave it in a vacuum right I said oh multiplicative weights you should increase the weights of experts who are good。

 decrease the weights of experts who are bad。😊，But you can view this in many different perspective。

 You can view this using convex optimization and you can view this using the perspective of。

Online learning。So maybe next time I'll tell you a little more about these different perspectives。

 the all equivalent。😊，And so this tells you， you know。

 gradient descent is the same as something called Paulo， the regularized leader。

 which is the same as the hedge， which is they are all the same same anyway will continue on Wednesdayd。

😊。