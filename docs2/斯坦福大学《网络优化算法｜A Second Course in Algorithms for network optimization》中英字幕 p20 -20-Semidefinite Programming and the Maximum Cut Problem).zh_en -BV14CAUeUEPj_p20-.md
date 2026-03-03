# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p20 -20-Semidefinite Programming and the Maximum Cut Problem).zh_en -BV14CAUeUEPj_p20-

All right。So you know having now essentially completed CS261 with the skills you've learned this quarter。

 you're now in a position to sort of learn and appreciate a lot of stuff in advanced algorithms and so this lecture is just going to be sort of one illustrative point I'm going to show you a really cool and quite famous approximation algorithm know which we will build on a number of the ideas that we've seen over the quarter and I could pick many other examples of cool results which are now well positioned to understand。

All right， so the lecture is going to be about the maximum cut problem。

 so we talked a lot about minimum cut at the beginning of the class。

 this is going to be about maximum cut。So the input is an undirected graph。

And a non negative weight for all edges。And the goal is to compute the cut AB。

So this is just the partition of the vertices into two different sets。Maximizing。

The total weight of the cut edges。Where an edge is cut if it has one endpoint in each of the two sides。

 one end point， A， one endpoint and B。Now， if this were the minimum cut problem。

 we'd know what to do right， so then we could reduce it to the maximum flow problem。 Okay。

 so we don't have an S& T here， but even so， it reduces to the maximum flow problem。

 if we wanted to minimize， but instead we want to maximize。

So you know one obvious sort of hack would be well let's just like negate all of the edge weights and then solve a Min cut problem and that's actually worked for us in the past on occasion。

 But if you actually go back to all of our maximum flow and minimum cut algorithms。

 they're assuming nonneative edge capacities and that hypothesis isn indeed used in the correctness of all of those algorithms。

 So if we take a max weight instance， negate the max cut instance， negate the edge weights。

 we get a minimum cut instance with negative edge weights。

 and it's not totally clear what's up with that。And indeed， this is an NP hard problem， it turns out。

It's just not hard to prove。嗯。So as a result， we're going to talk about an approximation algorithm。

So restricting attention to polynomials and algorithms， how close to fully correct can we get。

 what approximation ratio can we get？Well， pretty much at the very dawn of approximation algorithms。

 so like kind of early 70s or so， it was observed that it's really not difficult to get a one half approximation。

Okay， that is to have a polyno melt time algorithm that outputs a cut with the weight of the crossing edges is at least half of the maximum possible。

 pretty much anything you might think to try gives you a one half approximation， greedy。

 local search， picking a cut uniformly a random， linear programming rounding。

 all that stuff gives half approximations。So that's the good news。

 There's all these different ways to get 0。5， but it was pretty frustrating。

 It sort of seemed like the whole algorithmic toolbox was getting stuck at 0。5。

 And the concern was that maybe actually it was NP hard to do better。

 We've seen some other examples where it's sort of NP hard to beat the sort of obvious algorithm like set cover and set coverage。

 for example。😊，So that's why it was sort of a really cool algorithmic breakthrough when in '94 Gums and Williamson developed an approximation algorithm that does significantly better than one half。

So what was the breakthrough， the breakthrough was to make use of something called semi definite programming。

 which is kind of like linear programming but taken to the next level okay so it's again going to be of the template where we have a relaxation。

 although it'll be a different kind of relaxation as I'll explain and then again we're going to round it to bonaide cut without losing too much in the rounding process okay。

So that's what're going to do。Now。So actually most of what I need to do is explain to you what this relaxation is and provide you some evidence about why you can actually efficiently solve the relaxation because again。

 it's going to be kind of an LP relaxation on steroids a little bit。

So I want to introduce you to it in two steps。So first， I'm going to give you actually an exact。

Formulation。Of the maximum cut problem。 So this is going to be an NP hard formulation to solve。

But this will be the form in which we can figure out how to relax it。

So there's going to be decision variables。One per vertex。Y I。

And the constraint will be that it's plus minus1。Okay。

So the plus or -1 is just indicating which side of the cut the vertex lies on。 So you might say y 01。

 you could do 01， is's just sort of more convenient to do -11。Good。

 so in this formulation is giving be no constraints other than this， that H Yi is plus minus-1。

Now what's the objective？So I claim we can express the maximum weight objective function exactly in terms of these variables so notice there's already a one to one correspondence between cuts and feasible solutions right for any plus minus1 assignment to the labels to the vertices you get a cut and vice versa。

So how do we write down the objective function in terms of the YIs？Well。

 so we want to maximize the sum of the cut edges。 So presumably we have like a sum。Overall edges。

If we happen to cut IJ， the EIJ， then we get a prize of its weight， WIJ。

And then we want this multiplied by something。Which is one。 if the edge is cut and which is 0。

 if the edge is not cut。Okay。And so the point here。

 and the reason this is a quadratic formulation is if you think about the product。Of Yi and Yj。

This product is one if the two vertices are on the same side of the cut， doesn't matter which side。

 just the same side， and it's minus1 if they're on different sides of the cut。

And so in that second case， on a different sides of the cut， and that's a minus1。

 we want to get this bonus of the weight of the edge。And so the slick way to do that is you say。

 okay， well， you it's good for us when this is a minus1， so we want a minus sign。

 so now this is going to be plus minus1 with the opposite semantics And so the way to get that back to a0 one is just to take one minus the product and then times1 half。

Okay。So notice。If the vertices are on different sides of the cut that is Yi and Yj have opposite signs。

 this evaluates to 1， if they're on the same side of the cut and YYj evaluates to 1。

 this evaluates to0， which is what we want。So this is just really a rephrasing of the maximum cut problem as a quadratic program。

 Okay so if you like， this is a proof that quadratic programming is n hard。

 Max cut is a special case。So any questions about that that first step？

So again I went through this because the relaxation is more natural when you're staring at this formulation。

All right， so the relaxation。But so with linear programming， we would say stuff like， you know。

 maybe Y I is gonna be either 0 or1。 And then in the， you know， when we relax it。

 we say why I is some real number between 0 and1。 Okay so that's what we're used to。

 What we're going to do here is actually a little bit。 it's of it's a bit of a leap。

 so it's cool you can get away with this。😊，And I'll have to do some explaining about why we can get away with it。

So here's what we do。Right so again， it's going to be a relaxation in the sense that we're going to have something where each of the ys might be -1 or plus1。

 but there might be other things as well， which don't necessarily correspond to a cut。 Okay。

 we're going to get other stuff。 So Y I could be not just -1 or plus1， but actually。

 We're going allow it to be any unit vector。In Rn。So any vector on the unit sphere in n dimensional space。

 and here is the number of vertices。To be any。Unit vector。In RN。

So of course plus1 and -1 can be thought of as a special case of this right if you just take plus1 and then pad it with n -1 zeros or same thing with -1 pad out with n -1 zeros。

 then indeed you get points on the sphere in n dimensions。

 but of course there are a lot of vectors on the sphere and n dimensions other than those two okay。

So。That's going to give us， okay， right？So that's the first thing。

 So I'm going to call these now Xs when I switch to the vectors。So the y's are the plus minus ones。

 the X's are just sort of the general unit vectors， so intuitively。

 we just want to sort of take this and plug in X's for YI's。Now， if you think about it。

 we have to understand what we might mean here right so when each of Y I and Yj was plus minus1。

 this was just multiplying two numbers if these are now vectors。

What should the product correspond to， But also the obvious thing to try is the inner product。

 and that's what we're going to do。So now， what do we get。We get。Maximum。

 and this will be the relaxation。Some over the edges， WIj，1 minus the dot product of X and Xj。Okay。

Subject to XI unit vector。Okay。And actually， let me write this in a particular way。

So obviously what it means to say something's a unit vector is that sorry that it's two norm。

 it's Euclidean norm。Is one。So obviously it's the same to say that the Euclidean norm squared is1。

 it'll be clear why I'm doing that later， it sort of doesn't really matter okay。

So unit vectors maximize this。 Now， how should you think about this geometrically？

Okay so what's sort of going So what's not at all clear is how you would solve this relaxation or how it would relate to the optimal solution of the original problem。

 which are kind of like the two crucial points， but before we do that。

 let's just try to get like some understanding of how to think about this so you have this graph。

 there's vertices， N vertices， there's edges。What does solving this thing do。

 it takes the n vertices of the graph and it embeds them， it gives them geometry。

 it puts each of those vertices on the unit sphere in n dimensions。Now。

 what is it trying to optimize， It's trying to maximize this weight times 1 minus the dot product of these。

 Okay So in other words， it's trying to get this dot product to be as close to -1 as possible。

 It's trying to take the endpoints of an edge and make them inal。Okay， on the sphere。

It doesn't have be plus1 minus-1， but just if they're in typicalpital。

 you're going to get the full WIJ for that edge。 So you're taking the n vertices。

 you're distributing them on the n dimensional sphere， trying to make each edge。

 its endpoints as close to inpal as possible。So that's what this is saying geometrically。

Now one thing that I hope is clear。Is that this is indeed a relaxation。Okay。

 so let me call it the vector opt， the biggest this number could be for any unit vectors。

Is at least as big as the opt that we care about。That the best max cut。Why。

 because every cut corresponds to one particular feasible solution of this what's called the semidefinite program or vector program namely。

 if you have a cut for everything on the a side， just give it plus1 and then n -1 zeros for everything on the B side。

 you give it -1 and n minus-1 zeros， that's a feasible solution。

 this optimizes over only more stuff and it's maximizing。

 so it's only going to get a bigger number than the original problem。Okay。

 so in the same sense that we had linear programming relaxations。

 this is a vector or semi definite programming relaxation of max cut。Okay。

Now here's what's kind of crazy。So this， I hope is clear。

 the following fact may strike you as quite counterintuitive。It's really not obvious。

Which is that we can solve this relaxation。In polynomial time。

And what I'm going to do next is I'm going to explain why this is true。

 it's not going to be like a full blown proof， but I'll kind of explain I'll try to give you a very plausible argument for why it should be polynomial timeslvable。

Any questions before we do that？Yep。N is the number of vertices。

So the number of points you're putting on the sphere is the same as the dimension of the sphere。

It'll be kind of more clear why that happens in a little bit。Other questions？All right， I mean。

 one reason you know I found this surprising the first time I saw it is you know， you look up。

 you know， so why was this clearly not a linear program， Okay。

 so one issue is like the plus one minus one thing right that's not a linear constraint。

 but whatever the other thing is like that Y I times Yj right you're multiplying two decision variables together and remember that was like the number one forbidden thing when we're talking about linear programs we're having like two different variables in the same term and there they are。

😊，But in the relaxation， we've got that， too。 We've got this dot product of X I and X J。

 So it again feels like totally quadratic。 So how do we escape， know the quadratic quandary。

 if you will。😊，Okay， so。The moral reason for why this is tractable。Is convexity。Okay。

So we talked about convexity a little bit back when we were talking about strong linear programming duality。

 so remember a convex set。Just means that you contain all the chs。And if you're not convex。

 then there are cordds which do not lie entirely in the region。Okay。So that's convex。

 that's not convex。Okay， and in fact， actually a really good just sort of。

Rule of thumb for you to remember， kind of like forever is that convexity is usually very closely associated with computational tractability。

 Okay， and many of you who go on to work and say machine learning will hear this over and over over again。

 They are in conx optimization on a lot of other fields。

 convexity is usually fundamentally what's driving computational tractability。Now convexity。

 I actually mean it in two senses so the first is in terms of the feasible region so then we're talking about convex sets so things like this and so you linear programs as we saw had convex feasible regions and we're going to have that here too。

 as we'll see in a second。The other part of convexity。

 which is important is useful is in the objective function。So you can be computationally tractable。

 not just with a convex feasible region， but even if you have not a linear objective function。

 but a convex objective function。 So minimizing a convex objective function over a convex set is a tractable problem。

 Now， in linear programming， you have a linear objective function。

 which is a very special case of a convex objective function here， when we reformulate。

 we'll also have a linear objective function。 Okay so for us。

 we're actually using the the power of optimizing convex objective functions。

 though you'll certainly do that in machine learning and regression and so on。

 But we will use the fact that， we can rephrase this relaxation so that the feasible region is convex。

😊，All right， so that's just something to remember， convexity and computationaltractability almost always go together。

But still， you stare at this。You know I'm talking here about like these convex feasible regions and。

 you know， containing the cordords and all this kind of stuff。 All right。

 so what's the feasible region here， the feasible region here points on the sphere。

You take an average of two points on the sphere。You don't get a point on the sphere。

So like what am I talking about， where is the convexity？So to expose the convexity。

 we're going to have to reformulate。This vector program， Okay。

 we're going to get something which is equivalent， but where the convexity will be very transparent。

And so the first idea， and again， so why does it not feel linear？Well， several reasons， okay。

 but again， there's this dot product that we're worried about。

So we're going to do something we've done before when we talk about linear programs。

 which was add extra variables that represent or intended to represent the sort of nonlinear quantities。

 In case it's linearization。So for each dot product。We're going to introduce a decision variable PIJ。

Okay。So this is for every pair of vertices， whether they're connected by an edge or not。

 So we're going to have PIJs。And the intended semantics。

Is for PIj to be equal to the corresponding dot products。In their product of X and Xj。Okay。

So when we introduce these decision variables， this is what we have in mind for them。Now， of course。

 if we just stop here and we don't okay， so you can imagine just taking that linear program and replacing each of those dot product of XI with XJ with PIJ。

You might say what do we do with that norm squared constraint。

 Well actually you know the norm squared is just Xi dot product with itself。

 so that would correspond to a PII in the second set of constraints。So we could do that。

 we could just substitute。But then the problem is we've really sort of done a relaxation of our relaxation。

 so while it's certainly true that know， if you have a set of vectors， these Xs。

 you can define these corresponding PiIjs if you just solve。For a bunch of PIJs。

Who's to say that they actually arise as the inner products of some vectors， X1 through xn。

 if we don't add any more constraints， the PIJs could define any n by N matrix that they want。So。

The question then is。How can we enforce the intended semantics。

 so we've added our variables Now we've got to add some constraints and the meaning of the constraints will to say that P Js must arise as the inner products of N vectors。

 X1 through XN。 Okay， so we need to impose a constraint， which says that。 And surprisingly。

 perhaps if you haven't seen it before， that's a convex constraint。All right。

So let me remind you some linear algebra， you've probably seen this before。

You've probably forgotten it。That's okay， you know it's easy to page it back in in sort of 20 minutes with your linear algebra textbook or Wikipedia。

 so let me just sort of jog your memory。So suppose you have an end by end matrix。Of PiIjs。

And wondering， is that of the form？Of a bunch of inner products。 Okay。

 with the I Jth entry being the inner product of the I and Jth vector。 Okay。

 that's what we're wondering。 Clearly， some matrices will be of this form and others will not。 Okay。

 so in particular， you know， any matrix of this form is going to be symmetric。

Because the inner product of Xi and Xj is the same as J Xj and Xi。

 and obviously some matrices are not symmetric。So this will be true for some matrices。

 but not all of them。So first， let's just sort of observe something this we should be able to understand in real time。

So this is really just rephrasing this thing。So P has this form， if and only if it can be written。

As basically a square。Okay。Meaning as x transpose X。For some n by N matrix x。Okay。And this。

 once you sort of remember all the definitions is just taological。 So think about x transpose x。

What's the IJth entry of x transpose x， What's the dot product of the I row of x transpose with the Jth column of x？

That's the same as the。Dot product of the I column of x with the J column of x。So indeed。

The entries of x transpose x are exactly the dot products between Xi and Xj。好的。

So this is really just kind of， if you like， by the definition of matrix multiplication。

And then what are the Xs， so the X's， as we discussed？Are just the columns of your n by N matrix x。

Okay。All right。So this is a famous type of matrix。K you sort of things which are like squares right？

So they're going to be symmetric as we discussed， but then the key word here is positive semi deffinite。

 or PSD。Okay。So if you like， we'll say by definition。P is symmetric and positive semidefinite。

And this is where the semieite programming terminology comes from。

So a positive assimity of the matrices are these squares can be written as x transpose x。

 or equivalently， they're matrices of inner products of vectors。Now， PSD matrices are super nice。

 super nice。 Okay So one proof that they're super nice is that there's like a zillion different ways to characterize them。

 It would feel very different。 but actually， all of the characterizations are quite easy to go back and forth between。

😊，So in particular， so for example， one characterization of PSD matrices。

 they're the matrices that have all non-negative eigenvalues， it's a symmetric matrix。

 so it has a full set of real valued eigenvalues and it's PSD if and only if all of the eigenvalues are non- negativeative so that's a really nice characterization of them。

We're going to use。So I'm going to write down one of those characterizations。

 which exposes the conxity in the clearest way。So it turns out a matrix is positive semi definite。

 if and only if。What's called this quadratic form？Meaning you look at the z transpose pz here Z here is an n vector。

If you think about what this is， right so you multiply p times z， you get a vector。

Then you must buy that times another vector you're going to get back a number。

 So this is a real valued number to scale it。Called the quadratic form。

So if and only if z transpose pz is non negative。For all possible， so called test vectors， Z。

Now so again， just to make this maybe a little less mysterious if you really don't remember it。

 so let me just point out that if so one direction here we can just immediately see on the board okay？

If P is a square is x transpose x？Suppose P has the form x transpose x。

Now think about this quadratic form， suppose we hit it by Z transpose on the left and Z on the right。

Well， now we just have xz transpose times Xz。That is we have a vector dot product with itself。

That's always not negative， right that's just the norm of the vector。so if p is like this。

 stick on a z transpose there， a Z there， it's obvious that you get a non negative number。

The converse is not obvious， but especially if you have this eigenvalue characterization。

 it's kind of very easy to prove。All right。So any questions about that。

 that was the sort of linear algebra recap that I had to do。Questions。All right。

 so why does this make us happy？So again， remember a matrix P， these PIjs， right， they're PSD。

That is， they really represent the inner products of a bunch of vectors。

 if only if this quadratic form is always non negative。no matter what Z is。So， fixes Z。

Your favorite Z， I don't care which one。And think about what this constraint means。

 Think about what it looks like。Well， if you just do the matrix vector multiplication。

For this quadratic form。You just get the Youma were all choices of INJ。Of P I J。Times Zj。Okay。

 that's just expanding this out。Remember， capital P is a PSD matrix。

 if and only if this is always not negative， no matter what Z is now for fixed Z。For fixed Z。

This quantity is linear。In the PIjs。So it's true。 There's this quadratic aspect to it， Z， I， Z J。

 But if we actually fix the vector Z， these become numbers， you know，2 and -3， whatever。

 So there's just some number。 And as an expression， this is just linear in P。

Which means that for each fixed choice of Z， we have a single linear constraint in the decision variables in the PIJs。

So really， this vector program is just a linear program in disguise。

 so ultimately the restriction that the matrix represents the inner products of vectors boils down to this infinite set of linear constraints。

Okay。All right， so let me。So to summarize。So let's take stock of where we are here。So。

Summarizing the discussion thus far。We have a linear programming relaxation。Which is equivalent。

To our vector relaxation。So for decision variables we no longer have the vectors Xi。

 we just have PIJs， those are real numbers representing the doT products。

 and then we impose these positive semi definite constraints。

 which are linear in the PIJs to enforce that the PIJs really do arise as inner products。

So max one half。IJ and E。嗯は。WIj1 minus Pj。Subject two。Z transpose pz non negative。For all Z and RN。

So don't lose track of what's fixed and what's a variable， right， So this matrix。

 this n by N matrix containing all the PIJs， those are our decision variables In a given constraint。

 Z is fixed okay。So it's just a constraint that looks like that。

 So that's sum on the right hand side。 should be non negative for some set of fixed z's。All right。

 so in addition， let's just go ahead and force symmetry。Explicitly。

And then we also had this constraints that。We don't actually just want the PI Js to arise as the inner products of vectors。

 We want them to arise as inner products of unit vectors。

So that just means we want the PII values to be equal to1。Okay。

Because remember what is PII representing， it's representing the inner product of XI with itself。

 that's just the norm of Xi， so if PI equals 1 that corresponds to the vector。

 corresponding to hi being a unit vector。Okay。All right， so any questions about that？

So the claim is that。For any feasible solution。To this linear programming relaxation。

There's an equivalent solution to this vector programming relaxation。and conversely。And moreover。

 this mapping preserves the objective function value。What's the bijection， if you start here。

 Okay so if I start you with a bunch of vectors， then you just define PI J to be the dot product of X Xj。

A。This will all be satisfied， so these are the PSD constraints。

So if you define the PIJs as dot products of vectors， those are just going to hold。

 that's just what PSD means， and then if because you have unit vectors。

 you're going to get this as well。Conversely。Given a matrix of PIJs satisfying all these constraints。

 it has to be a PSD matrix。Okay so remember， this is a characterization of PSD matrices。

 these constraints。And so that means by this equivalent characterization。

 P has to arise the doc products of X's。And moreover， because of this constraint。

 those Xs are going to be unit vectors。Any questions about that， the equivalent of the two。

Relaxations。So in effect， this is the one we're kind of going to think about in our approximation algorithm。

But this version is important because it demonstrates why you can actually solve this thing in polynomial time。

Now， of course。You should probably have a complaint about this particular linear program。

And then the bothers hear about it？So it again， exactly， there's infinitely many constraints。

 it's true， each one is linear。But there's an infinite a number of constraints， one for every。

N vector Z。So that's a little frightening。On the other hand， know。

 didn't we talk at some point about some linear programming algorithm that actually could be poly time。

 even if you couldn't write down the linear program？Did we talk about at some point？すかわ。Good。

 so we got the ellipsoid method。Right， so issue。A couple of things。So you're right。

 we need a separation oracle， but just to catch everybody up so issue。Infinite number of variables。

And what I was alluding to was solution number one。Which is the ellipsoid method。Okay。

So this is back in lecture 10 I think we're talking about this。

 so the lipoid method is mill linearia program which is like kind of amazing in theory and kind of useless in practice so let's just talk about this for the moment so what does it say it says well suppose you have a polynomial number of variables okay which we do。

We only have n squared PIJs， not that big a deal。Suppose you have a poly number of variables。

 And then I don't care about your constraints at all。 back then。

 we were thinking about like an exponential number of constraints。

 like paths or trees or something like that。But it actually got a bit an infinite number of constraints。

 really。What did we need， we needed a polynomial time separation oracle。What's a separation oracle。

 somebody hands you an allegedly feasible solution。

 the responsibility of the separation oracle is either to verify feasibility or if it's not feasible to hand back a proof of it in the form of a violated constraint。

So the question then is， is there a separation oracle for this linear program with infinitely many constraints？

And there is， and again， it's just the same kind of simple algebra we were talking about with PSD matrices。

So what do you do， so suppose someone hands you an allegedly feasible。Collection of Pijs。

So you form the matrix capital P。And what you're going to do is you're going to compute its eigenvalues。

That can be done in polynomial time。 That's a standard matrix algorithm。 a lot of ways to do it。

 So you can view the eigenvalues of the matrix P。 if they're all non negativeative， you say good job。

 It's PSD。 remember that's one of the characterizations of PSD matrices， non negative eigenvalues。

Now， if there's a negative eigenvalue， then you know it's not PSD， but that's not good enough。

 The separation oracle also has to return a violated constraints。 but if you think about it。

 the eigenvector associated with a negative eigenvalue will form a violated inequality。 So if z。

Is an eigenvector of P with a negative eigenvalue， Then Z transpose P Z is going to be negative。

 Okay， So it's just going to be the eigenvalue， which is negative times the norm of z。

 which is positive。So that's your separation oracle really can be done poly no time I give you a P。

 you can tell me whether or not it's PSD， and if not you can show me why。All right。So yeah。

 let' down。So separation Oracle。Eigenvalue and eigenvector computation。Okay。And again。

 if you're just sort of like trying to understand conceptually。

 why on earth should you be able to solve this thing efficiently。

 this is why it's because PSD constraints are really conve constraints and moreover。

 they have a polynomial time separation oracle so morally that's why you can solve semi differentite programs in polynomial time。

Now that's not how you're actually going to do it in practice。

So the way people really solve semi defite programs are using what are called interior point methods。

So I mentioned these only very， very briefly at the end of one lecture as a third paradigm for solving linear programs where you have both polynomial time guarantees and can be competitive with simplex in some cases and so it turns out ever since the 90s at least there's been a lot of work extending the reach of interior point methods and they can now accommodate they've been able to accommodate semi E programs for quite some time for about 20 years when I say accommodate I mean in both theory and in practice so they're interior point methods which are polynomial time。

And there are also ones which can solve， let's say medium size problems in practice so what I mean。

 medium size， you know thousands of variables， you should probably be able to handle tens of thousands not so clear。

 that might be pushing it the state of the art SDP solvers。

 so it's a couple of order of magnitude less than the size of the linear programs you can solve in practice。

 you know but still it's much better than you could do with the typicalmp hard problem。All right。

 so that's what I wanted to say about， you know， why can you actually solve。

This relaxation polynomial time，So henceforth， we're just going to assume。That we can solve this。

 and we're going to get our hands on an optimal solution to this relaxation。

And for the rest of the lecture we're kind of going to forget about this version。

 this was kind of to explain to you why it's sufficient solvable and we're going to think about solving this version and again。

 you can go back and forth Okay so if you solve that you can recover the vectors。

 you have a solution to this。Okay， good。 So now we know we're not crazy。 Okay。

 at least this is a computational efficient step to solve this relaxation。But， you know。

 now we have the same old problem we always had when we were trying to use relaxations for MP hard problems。

 right， If we can solve this in polynomial time， Max cuts NP hard。

 So it's not always going to give us back， know integer values。

 It's going to give us like random vectors on the sphere。We don't want random vectors on the sphere。

 We want to cut of the graph。So how do we get a cut of the graph from these random vectors on the sphere？

That is， how do we round the solution to this relaxation to a feasible integer solution？Okay。

 so let x1 through xn denote the actual vectors， making this as big as possible。Okay。

And so just like there is no way to interpret fractions as a vertex cover。Or as a set cover。

There's no way to just interpret。Random vectors on the sphere as a cuts。AndSo I should say。

 so as far as the history。 So these kinds of semi definite relaxations。

 they'd been kicking around for a little while。 People were certainly thinking about them some in the 80s。

 but nobody really knew how to do this rounding。Okay。

 so it was the rounding that was developed by Guumms and Williamson in '94。

Which connected kind of this branch of mathematical programming to the development of approximation algorithms。

 So it was a very important result for that reason。So。We're going to use randomized rounding。Okay。

So you saw randomized rounding once it was exactly a week ago。

 we were talking about churn off bounds and as giving you some applications。

 mean we talked a little bit about hashing， but then we also talked about the sort of edge disjoint paths problem and we talked about solving a multi-commodity flow relaxation。

 interpreting as a probability distribution and then making random choices and getting some kind of approximation guarantee。

So here we're also going to use randomized rounding。

 and actually it's going to be simpler than what we did a week ago。So what are you we going to do？

Let me show you a picture of what we're going to do。Now I can't really draw。

 I can only draw points on the sphere kind of in 2D。So I know it's kind of weak。Bear with me。

So here's the origin。So how do we get a cut？So again， remember what the SDP is trying to do。

 We talked about as geometric intuition， right for any two points that actually are connected by an edge。

 it's trying to make them as inpal as possible。 It's trying to put them on opposite sides of the circle of the sphere。

 So if the SDV solution is really good， then most pairs of endpoints of edges are going to be nearly antipatal。

So if you see a picture like this， you should say， oh， well， you know。

 these adjacent things probably aren't connected by an edge in most cases。

 because the SDP wouldn't want to do that。 You want to put them far apart。

 So the things close to each other， you sort of expect to usually not have an edge between them stuff that's far apart。

 You figure probably there is an edge between them because the SDP wanted to get a lot of。

G a blog bang for its buck。So。We knew something that in hindsight is supernatural。Okay。

We're going to make a random hyperplane。Through the origin。看。This induces a cut。

The vertices on one side， that'll be our set A。The vertices on the other side， that'll be our set B。

Okay。So that's the whole algorithm。Random hyperplane rounding。嗯。So there's intuition behind。

 you know why you might want to do this again， typically the SDP will have things be far apart。

 you know in typicalpal and in that case they're almost surely be other opposite sides of the hyperplane and then you'll cut them as well。

 So you know there's intuition for why it's a good idea but it's hard to really know whether it would say beat a 0。

5 approximation without actually doing a little bit of analysis Well it's not very difficult analysis。

All right。What's the Ro algorithm？Choose a random unit vector。Or。

This is the normal vector to the hyperplane that we're picking。

And now you just define A and B according to the sign of the dot product with R。Okay， again。

 remember， we're taking as input these vectors， we're taking as input the optimal solution to that relaxation So we have one n vector in our hands for each vertex of the graph。

So for those vectors Xi。Which have non negative dot product with R put those in A。

And then ones with negative dot product with R。Put those in B。O看。Now you may be wondering。

 what does it actually mean？To pick a random vector on the sphere， a random unit vector。

If you've never thought about it before， but actually this is not hard。

So one way you can do this is you can just pick N IID standard Gaussians。

 so a normal random variable means zero variance1， make those into an n vector。

 now that might not be a unit vector， but you just scale down by the norm。

So that gives you a random unit vector， everything on the sphere is equally likely。

The main property that we're going to use of this distribution。

 the uniform distribution on this sphere is that it's spherically symmetric。

 so the density of a point only depends on its radius from the origin。

 doesn't otherwise depend on it。 rotationally invariant， if you prefer。Okay。All right。

So any questions about the algorithm？Good。So here's the theorem。The expected。Weight of the cut。

Produced by this algorithm。I at least。878。Time's out。87。8%。Okay。A lot better than 50%。 And actually。

 frankly， for N P hard problems， there aren't a whole lot of them where you can get this close to one in the worst case。

 Okay， so it's pretty cool。😊，This is an approximation guarantee you can almost sort of take at face value。

 those are somewhat rare。And again， remember， before this。

 every imaginable tactic seemed to be getting stuck at 0。5。 and it's also trivial to get 0。5。Okay。

So why is this true？Well， here's the keylemma。Hema says that for。Every edge。The probability。

That the edge Ij is cut。By our random hyperplane。Is at least 0。

878 times what the vector relaxation earns for that particular edge。So one half。

 one minus dot product of X。And X J。Okay。So in other words， we're saying remember。

 So the closer this gets to -1 the bigger this gets and the closer they are to antipal。

 So this is just saying the more and more antipoal that the points get， you know。

 our probability of cutting them in our randomized hoverplan algorithm is going up accordingly。

 Okay this's scale together。 And in particular， there's no kind of weak link。

 There's no sort of magical dot product where the SDP somehow gets a lot out of it and we fail to cut it。

 Okay that would be a problem。So to prove that the Le implies the theorem。

That's really just linearity of expectations if you think about it。Right。

 so the expected weight of a cut produced by our algorithm。Well， let's just for a given edge。

 think about the expected contribution of this one edge。Okay。So by linearity of expectation。

 that expectation of the sum becomes a sum of the expectations。

So we now we have a sum over the edges。Of the weight of that edge。

Times the probability that Ij get cut。So again， we're just computing the expectation term by term。

 edge by edge。 This is what we get。 He we get WIJ， if it's cut， we get  zero， if it's not cut。

 So this is the expected contribution。Now I just plug in the keylemma， right。

 so the keylemma says that our cutting probability is closely related to the SDP term。

So this is by dilemma。878， some over。IJ and E， W IJ。One minus X Xj。So this。

 remember is the semi E programming opt。And by virtue of being a relaxation。

 that's only bigger than the real opt。So。878。Time's up。Any questions about that？All right。

Proof of lima。Yeah。So we want to lower bound the probability that our algorithm cuts a given edge as parameterized by their dot product。

So。This winds up being a surprisingly。Nice and elementary thing to think about。So fix an edgech。

So the vertices IN J， there's corresponding vectors on the spherepherx I and Xj。

So those two points together with the origin span a plane going through the origin。

 a two dimensional subspace。 So let's just think about the subspace span by Xi， Xj， and the origin。

So in my earlier picture。I was restricting a 2D because that's all I could draw。

Now we're actually doing the analysis in 2D， no matter what the original ambient dimension was。

So we have the origin。Xi is somewhere。And xj is somewhere else。Okay。So。We picked a random vector。

 unit vector and n dimensional space， but because it's rotationally invariant。

 it doesn't matter which slice we look at。 when we project down to a two dimensional subspace。

The random vector is going to project down to a random point on the circle。Okay。

So the hyperplane in this subspace is just a uniform， or random hyperplane like this。

So in which cases are INJ going to wind up on the same side of the cut and in which cases are they going to wind up in different sides of the cut？

Well。If the hyperplane goes anywhere through here。Then we're totally good。

Xs and xj are on different sides。Okay。And actually， if I draw this the other direction。

Same thing if the hyperplane goes anywhere here。But Xi in exchange different sides。

 If the hyperplane is in these smaller wedges， well。

 then ex ion and X are going to be on the same side。Okay， we're not going to cut them。

So if we call the angle theta。On the circle。Of the wedges between Xi and Xj。

The probability that are randomly chosen， uniform or random。

 hyperplane cuts them as exactly two theta。Over two pi。

So there's sort of two pi total measure of these hyperplanes and a two2 theta fraction。

We'll cut Xi and Xj。Ro clear man。It was very nice。To have like a really simple understanding of the cutting probability as a function of the angle。

Between the two vectors，All right。But now， what about the other thing we somehow need。

 So this this is our cutting probability， but we need to relate it。Two。

 what's earned by the semi Ena program， which depends on the dot product between these two vectors。

But wait， actually don't dot products or something to do with angles。

That's kind of like almost their definition。One way to think about them。

So think about the dot product of Xi and Xj， the sort of an annoying term in dilemma on the SDP side。

Well， so this is just equal to the norm of X times the norm of Xj times cosine theta。Okay。

 something you learned a long time ago。Xi and Xj are unit vectors。

So the dot product of xine xj is just cosine theta。Okay。

So what we've now done is we've parameterized how well we're doing as a function of theta。

 how well we're doing is exactly theta over pi， we've parameterized how well the semideite program is doing as a function of theta。

 namely cosine theta。We don't expect to always do as well as the SDP。

 but we're hoping to do as close as possible。So the question then is for a worst case choice of theta。

How much smaller can this be than this？That's what's going to govern the approximation ratio that we can prove。

In other words， what we want to prove is that for some constant， it's going to be 0878。

 no matter what theta is， this is always at least 0。878 times this。

So the lemma then becomes equivalent。It's proving that theta over pi。

 at least certainly a sufficient condition for a proof of dilemma。

 is that theta over pi is always at least。878。 and sorry， so what the。

What the SDP actually gets is12 times 1 minus cosine theta。Okay， so I apologize。

I was talking about cosine theta， really， we should be talking about one half times1 minus cosine theta because this is what the SDP gets。

This is what we get。This is what the SDP gets， So we want to get for every possible theta。

For every possible theta， we get a healthy fraction our cutting probability is a healthy fraction of this。

And now I don't have much more to say， this is just true。And now that I've told you that it's true。

 it would be very easy for you or anyone else to verify。 For example。

 you could plot these two things。 and， you know I've looked at plots of it。 It's obvious， okay。

 that this holds。If you're a stickler for rigor， it's total freshman calculus to actually prove this。

 it gets a little tedious， but you know it fits in a page so obviously I'm not going to do it here。

 I'm not going to waste your time with that。So this you can just。Verify via plots。Or calculus。Okay。

And so that completes the proof of the lemma， and therefore the theorem。And therefore。

 the fact that randomized hyper planee rounding is 0。878 approximation from X。

Any questions about that。Now we've seen some pretty weird numbers。

For approximation ratios and competitive ratios， right。

 like we were haunted by 1 minus 1 over1 like for a long time， right？But then you know。

It was also inevitable。 We discovered it was actually the correct answer in a lot of different contexts。

 Now，1-1 over E may be a weird number。But this  point878， this is like a really weird number。Right。

So yeah you figure， okay， I guess the right answer is like nine tenths or something like this。

 right that's how most of our brains tend to work。Believe it or not。

 there's some reasonable evidence that there's no better approximation algorithm for the maximum cut problem。

And this is now getting reasonably recent。This is from '05。

So it not I'm not going to be able to write down if P not equal to NP。

 then there's no better algorithm。 Okay， that's what was true for like set cover and set coverage。

 So there are multiple problems where we can say。Assuming p not equal to NP。

 we know the optimal algorithm。So here we're going to make a stronger assumption。

APossibly much stronger assumption。Okay。So it's an assumption called the unique games conjecture。

Or UGC。UGC is a little technicalical to state， so I'm not going to do it right now。

 basically it's asserting that a particular constraint satisfaction problem is hard so if unique games's conjecture is true。

 then P equal to NP is true in some sense， but it's definitely possible that the unique games's conjecture is false at the same time P equal to NP。

 In fact， probably probably probably at least half of theoretical computer scientists。Believe that。

 okay。So if you don't believe the unique game conjecture。

 one way to read this would just be to say doing any better on max cut would require sort of a major breakthrough on this problem that we have no idea how to solve。

 That's a sort of backwards way of looking at the reduction。Anyway， so it's true。

 So assuming the Uni games conjecture， assuming this particular constraint satisfaction problem actually is MP hard。

 then if P not equal to NP。This is an optimal。U。Max cut algorithm。Okay。And as usual。

 I mean it here in the sense of the in terms of the worst case， approximation ratio。

So even the unique game conjectures is only from O2 or so。

 that's a pretty recent relatively speaking complexity assumption。

 but a lot of things have been derived from it， this is maybe the coolest thing that's been derived from UGC and this fact itself is not easy to prove。

 so this involves some nice kind of fouria analysis on the Boolean hypercube actually proved this statement so it's cool stuff。

Right right。Questions。Okay。So back in lecture one， I kind of said how I think of there as being like two audiences for 261。

 the first audience are sort of those of you that will probably never take another algorithms class。

 you know you're going you're graduating this year or what have you。

And so you know so that motivates sort of spending a lot of time in this class and kind of the essentials so just classic stuff which you didn't see in your other classes which are most likely to be useful to you later and so for that group。

 I want to say that you know pretty much now at the end of 261。

 you know more about algorithms than almost anybody who doesn't have a PhD in the subject like you have a really quite deep understanding at this point so you should feel good about that。

The second audience is sort of those that are preparing for deeper study in theory or in algorithms。

 And for that group， I mean， after 261， you're really kind of well positioned to take whatever you want。

 Okay， so any 200 level or 300 level theory class， you know。

 you're very well prepared for at this point。 And this lecture was sort of。

Meant to be an illustration of that fact， Okay so Max Cu。

 this is something you'd probably often see in a more advanced class。

 but it's quite easy to teach this to you at the end of 261。So in any case。

 you know if you've stayed on top of the lecture material。

 you've learned a ton of stuff right and at the classes。

 I sort of like this tradition of doing a top 10 list just to kind of remind you like how much more we know now than we did when we began because it's a lot seriously like I mean I'm well aware of how much I'm teaching it's a lot of stuff so right。

 so where do we start So number one。We started with the max Fman cut theorem。

 This is the theorem that actually seduced me into a career in algorithms。 I just saw this。 I'm like。

 you know， how could these seemingly so complex structures that are also so practically useful be so beautifully characterized。

 So that really sort of opened my eyes。 We saw some cool algorithms right We saw augmenting pathbased algorithms。

 We saw push re label algorithms， We saw applications like to image segmentation。😊，Also。

 MaxFlow sort of gave us this first exposure to this general issue of how do you know when you're done with an algorithm。

 so back in MaxFlow， how did we know we were done， there was no ST path in the residual graph but now we sort of see that's that was the first step in a journey to understanding that question much more deeply。

Number two， biparttheid matching， especially the Hungarian algorithm。

 probably the canonical primald algorithm。So how did we know that we were done in the Hungarian algorithm。

 Well， at the time it was a little mysterious， we had these sort of strange invaris that it kind of pulled out of a hat。

 and then we we observed that we were optimal at the end。But then once we studied LP duality。

 we had a very clean understanding of what the Hungarian algorithm was doing。

 namely maintaining dual feasibility and complement slackness， working toward primal feasibility。

 and we then understood that this is a totally systematic way to solve linear programs and the problems that they can model。

So linear programming obviously sort of played a really big role in 261 so the first thing to remember is just that they're efficiently solvable just in theory and in practice we said very little we didn't have really have time to talk about the details of linear programming algorithms but even just knowing black box that they're out there is tremendously powerful so if you want to prove theorems you should definitely know you can solve linear programs in polynomial time even ones you can't describe as long as you have a separation oracle using the ellipsoid method and then for those of you who are sort of going be more do hands-on work it's very possible you'll want to solve linear programs in the future and so it's very good to know first of all the tons of different problems can be modeled as linear programs。

 second of all that you can really routinely go into the hundreds of thousands of variables and constraints with commercial solvers really some of you I'm sure that will be directly useful for you in your future。

So then so fourth。 So okay， that that's fine。 That's of the practical side linear programming。

 but then we also had duality， which is just as a conceptual tool for kind of understanding how algorithms work is incredibly powerful。

 So it says that， you know， whatever the optimal solution may be to your linear program。

 you're always guaranteed to have a dual solution certifying its optimality。

 So it's kind of the ultimate answer of how do you know when you're done。 You know。

 you're done when you have a dual solution with the same objective function value。😊，ちちちゅ。Right。

 and then also， as far as we as far as proving strong linear programming duality。

 the fact that the prim dual always have the same objective， you know。

 it it's very powerful and it may seem counterintuitive。 But remember， ultimately。

 it just boiled down to this highly plausible fact that if you have a con set and a point outside the set。

 there's a separating hyper planee between the two。

 That's really what strong linear programming duality boiled down to。

So the multiplicative weights algorithm， So this is when we' were talking about online decision making and so multiude of weights was this very simple algorithm sort of in the spirit of reinforcement learning and has this kind of amazing guarantee that the per time step regret goes to zero as the time horizon grows large and so remember that means what does no regret mean it means you're doing as well on average as the best fixed action in hindsight。

😊，And so we saw that was both interesting in its own right。

 as sort of an algorithm for making decisions over time in an online setting。

 but it also has some really surprising application。

 So we proved the Min Maxax theorem for zero sum games。

 which says that it doesn't matter which order the players move in as long as they both optimize randomly。

 And then we also saw applications to sort of fast approximate solutions to flows。

 multicommodity flows and so on。So then online algorithms， I put that6 on the top 10 list。

 So lots of problems in the real world are online。 It doesn't really get any airtime in a class like C 161。

 But so now we talk about a little bit。 And we see that at least for some problems。

 including some practically very relevant ones like online bipartite matching。

 there are actually quite useful algorithms with good provable performance guarantees。

 So the water level algorithm from bypartite matching being maybe the most compelling example that we saw。

😊，So then we talked a lot about MP hard problems， what to do with them at the end of the course。

 So early on in that we talked about the traveling salesman problem。

 which is a famous problem and it's just sort of really easy to understand that it's sort of puzzled and challenged people over the decades and actually when it comes to approximation algorithms。

 you actually now know the state of the art for the traveling salesman problem So for the metric TSP problem there is no algorithm known that's better than Chris Defiti's three Has approximation which you all know and then even for ATSP asymmetric TSP。

 there isn't anything a whole lot better known from the login approximation than I showed you in that lecture。

So a few of the course themes came together then when we started going deeper into approximation algorithms when we saw how linear programming。

 which in the first half was really focused on proving exact optimality of polymial time solvable problems。

 it's actually maybe the most commonly used tool for proving worst-case approximation guarantees for NP hard problems and this can have many different forms。

 sometimes you use linear programming or duals only in the analysis。

 so like when we proved an approximation ratio for the set cover problem。

 we only use it in the analysis， sometimes the algorithm solves the linear program explicitly。

 so like in randomized rounding or in our vertex cover rounding algorithm and then sometimes the linear program and it's the dual pair guides the algorithmic decisions that you make but you never actually solve it explicitly and therefore you can have very fast algorithms like our linear time two approximation algorithm for vertex cover。

All right， so number nine。Five essential tools for randomized algorithms in particular。

 the one you are least likely to have seen before the turn off bounds turnout bounds are used all the time。

 and you saw a couple of canonical cases in this class。

 what does it say it says you have very sharp concentration around the expectation for sums of bounded independent random variables it comes up all the time。

So and we saw applications both to hashing and also to randomized routing， to low congestion routing。

And we also quickly reviewed some simpler ones， some sort of oneline proof ones that remain super useful。

 linearity of expectation， which is sort of trivial but used all the time， Markov's inequality。

 which is good for when you're happy to have just constant probability guarantees。

 Chey Chev's inequality， so that's the case where you have a handle on the variance。

 and then the union down， which is good for avoiding lots of low probability events， simultaneously。

And finally， let me just mention sort of last lecture， beating brute force。

 So we talked a lot about MP hard problems。 And one takeaway of 261 is that。You know。

 just because your problem is NP hard and believe me。

 problems you encounter later will sometimes unfortunately be NP hard。 It's not a death sentence。

 It doesn't say that your algorithmic toolbox is useful。 actually sort of the contrary。

 we kind of see that for every coping mechanism for MP hard problems almost the algorithmic toolbox you've developed remains completely useful。

 So we saw that in approximation algorithms。 But then we even saw that on Tuesday。 for example。

 we gave a dynamic programming algorithm for TSB dropped the running time from n factorial down to two to the N。

 I introduced you to fixed parameter tractability， this idea that sometimes when a parameter is small。

 like the optimal solution。 you can be brute force search I showed you vertex cover。

 but there's many， many other examples， and then we saw this kind of amazing random search algorithm for threes by shown in。

 which gave a fourtds to the n running time for threeat blowing away the two to the N that would be required from brute force search And there's things I omitted。

 but that's just that's the top 10 list。 probably you didn't know most of that stuff before we started。

 Now you're all experts on it。Okay， so I want to thank the TAs before we wrap up so Oka and Choany。

 and thanks to all of you for coming， best of luck on all your finals。

 hope to see you again in the future course。