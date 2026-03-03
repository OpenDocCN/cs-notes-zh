# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p07 -07-Lecture 7_ Linear Programming_ Introduction and Applications).zh_en -BV14CAUeUEPj_p7-

let's go ahead and get started so last lecture we wrapped up the first part of the course the course has four parts so the first part was about commatoral optimization so efficient algorithms for searching over discrete structures so things like flows。

 cuts paths and so on and so with today's lecture we move into our second part which is all about linear programming with an emphasis on applications and duality so how many of you have seen the least a little bit about linear programming at some point in your life just curious。

Okay， I'm not going to assume anything， don't worry， just for calibration。

So it's kind of confusing for computer scientists because this isn't programming in like computer programming。

 so this predates kind of basically modern computers。

 so it's more like in the spirit of television programming。

Which means you basically are scheduling things。 you're sort of like planning out what's going to happen。

 So that's the idea of linear programming， same reason in dynamic programming。

 same same notion of the word。嗯。So why we going had spend two four weeks on this topic？Well。

 so first of all。Pillenium programming is algorithmically really， really useful。

 both if you're trying to prove theorems and also if you're trying to solve problems in the real world。

So linear programming， if you remember only one thing about it after 261。

 remember that it's a remarkable sweet spot between on the one hand generality。

 so in particular every problem we've studied so far can be thought of as a special case of linear programming。

And on the other hand， computational efficiency， linear programs can be solved fast。

 both in theory and in practice。So sometimes and we'll see many examples。

 the problem you care about literally is a linear program。

 but there's also cases where even though your problem isn't a linear program。

 it's still a super useful subroutine to sort of have in your pocket so we'll have some lectures toward the end of the course approximation algorithms for NP hard problems so we're not going to solve an NP hard problem exactly using linear programming unless P equals NP but still a linear programming solution can serve to the basis from which we recover a near optimal feasible solution so we'll see that at the end of the course and then in practice wet really discuss this in 261 but in practice probably the most cycles are used for linear programming actually as a helper subroutine and what's called integer programming so that's a harder problem it's NP hard but people work hard to solve it exactly in practice because often know the viability of business is depending on having a sort of a efficient allocation of resources and so in those integer programming codes they invoke linear programming over and over and over again as a subroutine because that's really the workhor。

Of how those things get solved。So that's the first reason。

It's really sort of a very general but still computationally efficiently solvable problem。

There's a second reason which is also going to be very useful for us。

Which is just on a conceptual level。 It's really helpful。

 meaning it just gives you the right way to think about lots of problems。So like for Max flow。

 I tried to explain how the right way to think about the problem is in terms of these optimality conditions。

 you no SD path in the graph， how do you know when you're done。

 you know you're done when you've saturated a cut we had a similar thing with matching So linear programming duality can be thought of as a generalization of all of these things that we've learned In some sense。

 it's one of the more general answers you could ever have to the question how do you know when we're done。

 that's really what duality is all about。 So we'll start talking about that next lecture。

So needless to say， you know， this general answer to how do you know when you're done。

 it's super useful for proving algorithms are correct or at least approximately correct。

 because it sort of gives you a bound on how good any solution could possibly be。All right。

 so what is linear programming， well one way to think about it。So once upon a time。

 maybe a long time ago for some of you， but in at least one previous course。

 you may have forgotten it， but I'm sure you've seen systems of linear equations。

Which can be thought of as an easy special case of linear programming。All right。

 so what do I mean by a system of linear equations where you have variables， x1 up to xn？

And then you have a linear combination of them。Okay so that's one linear constraint。

 So here we're thinking of the A's and B's as given and the x's as free variables that we're solving for。

And it's not just one linear equation。 It's a system。 Okay， so in general。

 you're going to have M of these。Okay。And so if you prefer in matrix form。

You might want to write this like so。So you have a matrix A， so the columns correspond to variables。

 so there's n columns。The rows correspond to constraints， so there's M of those。

So this again is given， these are the coefficients， the little A's， this is what you're solving for。

 and you're also given a right hand side， B。Which has Li M。So one number per constraint。

So if you like matrices， that might be how you prefer to think about this。So when you study this。

 I'm sure you learned a pretty good algorithm for solving a linear system in the sense of an algorithm that either determines that there's no feasible solution at all。

 or if there is a solution， it returns run to you。So like Gaaxian elimination would be a canonical such algorithm and this is kind of thing。

 maybe some of you even learned it in high school， but certainly you know by the time of the first year math sequence here。

 one learned this stuff okay。So what does this have to do with the problems we've been talking about？

Well。And what's like a key problem with Gaussian elimination？It's linear systems。Well， what about？

Inequalities。And if you think about the problems we've been studying so far。

 if we wanted to try to encode them in this sort of language。

 it seems hard to escape wanting inequalities。Think about maximum flow。

What did our constraints look like in the maximum flow problem， Well。

 we had conservation constraints。 Those are equations。 So that's not a problem。

But then we had capacity constraints。 The flow on edge should be at most the capacity to the edge。

 It shouldn't necessarily be equal。 Does't have to be equal， can be less。And actually。

 we also have these nonnetivity constraints， so the flow should be at least zero everywhere。

 and it's hard to see how you would encode that into just a system of linear equations。 Okay。

 it really seems like you capture more problems by adding inequalities to these systems。 And again。

 just thinking about max flow， it's sort of obvious we might want to do that。All right。Right。

 so one way to think about linear programming is while Gaussian elimination and algorithms if its Ilk。

They check feasibility of a system of linear equations。

 Linear programming can be used to efficiently check the feasibility of a system of linear equations and inequalities。

 more generally， if you have a range of feasible solutions like you have many flows in a network。

 linear programming will allow you to optimize over all of the feasible solutions so that's the purpose of linear programming。

All right， so we're going to have several lectures on the near programming and。

Go to do lots of examples。 I basically want us all to spend some quality time with this idea because it's one of those things where like if you just see it in one lecture。

 it just doesn't sink it。 it's something you need to kind of spend some quality time with to really absorb and then actually use in your later studies and work。

So what's the ingredients of an LP？So you really you can sort of think of linear programming as this formalism。

 this sort of almost you know programming language for encoding certain types of problems so let me tell you what are the ingredients and it's very flexible so it's a recipe and as I'll try to convince you even today。

 it's a very flexible one。So basically we have to specify linear your program。

 you have to say what's allowed and you have to say what you want。So the first thing you need to。

Decide on are your decision variables。These play exactly the same role as in x1 through Xn that I just erased。

Okay， so each of these is a real value， positive or negative。So these are just free parameters。

 so it's the job of a linear programming algorithm to figure out the best way to set values for the x's。

All right。So then you have to discuss what's allowed， what's feasible。

So there's going to be constraints。And no surprise， given that it's called linear programming。

 the constraints should be linear。Okay。So like the ones we had in a system of linear equations。

 except we're also going to allow inequalities。So these are going to have the form。Some over AIJ。

So a linear combination of the x's。The A's of the coefficients。U。

That's going to be the left hand side。Then we're going to have a BI on the right hand side。

And in this space， this can be equals， or it can be less than or equal to。

 or it can be greater than or equal to。So all of those are allowed。

When you're defining a linear program。Now again， let me emphasize when you think about a linearium program。

 you think of the A's and B's as part of the input， so they were just known numbers， seven， minus1。

 et cetera， the x's are the free variables that we're solving for。Now。You may sort of。Observe that。

 you， allowing these three different types， really， this is a superfluous encoding。

 but it's convenient。 Remember， I'm not assuming that A's or B's are negative。Or sorry。

 or non negative， they can be positive or negative。 That's fine。 So given inequality of this form。

I can translate it into one of this form just by multiplying everything by -1 and similarly to the other direction。

Even equations， if you think about it are sort of a redundant encoding because if I want to say something is equal to 10。

 I can just have one inequality saying it's at least 10 in a second inequality saying it's at most 10 so really without loss。

 you can think of it as all inequalities and all going the same direction。Yep。我说是。We don't per se。

 but it's easy to have a workaround and one of today's examples will show you the workaround。

So when you input it to an LP solver， you're really sort of stuck with this language。

 but it's not a big deal。As we'll see。Good question， other questions？So again， AIJs。And Bs。

Our constants。Being。Numbers provided as part of the input。 Okay So， for example。

 like an edge capacity， that's what I mean， right， That's just going to be like 12 or whatever。

 And some given input。All right， and then you have to say what you want。

So just like in the specific problems we've been talking about。

 we need to poit an objective function。And oh， so I should say， oh yeah， day more in a second。

 so this should also be a linear objective function。It can be a minimization or a maximization。

Function it really doesn't matter。And then you get to choose some other linear combination with different coefficients。

 CJs。And you want to maximize the sum of the CJxjs sum to over J。Now again。

 there's no assumption that the C's are non- negative， they can be positive or negative。

 so then it's sort of immediately clear that it really doesn't matter whether you write it min or max because if you have a max。

 you multiply it by minus1， you may as well minimize that instead so you can transform one objective into the other objective just by taking the minus times the coefficients。

All right。And that's it。 So you specify those things， you've specified a linear program。

 you can start talking about solving it and what it means when you solve it and so on。So。Linear。

 what does linear mean here， really， how should you think about it？Well。

 so maybe it's simpler to say like what would be a violation of these rules， of the linearity rules？

Okay， so it's certainly not allowed is to have one of your decision variables in x embedded in some nonlinear function so like if log 1 plus x showed up。

 that would be nonlinear because log is not a linear function。Similarly， if you had x1 squared。

That would not be linear X， right， That's a quadratic function， not a linear function。Also。

 if you took like two different variables， X I and X J and multipied them together， again。

 that would not be linear。 Okay， It would be a quadratic term， just with two different variables。

So what's special about linear inequalities and linear objective functions is that whenever you see a decision variable。

 whenever you see an x， it's just a alone， except possibly multiplied dot times some constant。

 And again， remember， A's， Bs and C's are constants provided as part of the input。 And then。

 of course， you can sum them。 that's fine for a linear function。😊，O。

So that if you want to just check something linear and not linear。

 just look at the decision variables， make sure they all appear by themselves。

 multiplied by constants， and then add it up and nothing else， again in particular no products。Okay。

So you know the restriction to linearity， it's admittedly significant。

 there's problems we care about which are not fundamentally linear， but still as we'll see。

 there's a ton of applications that are exactly modeled or approximated by linear programs。

 sometimes the translation is super direct and we'll see an example of that when we go to max flow and Minco flow。

 but'll also give you a couple examples today motivated by machine learning where you need a couple tricks to really get the linear programming formulation so sometimes you need some ingenuity。

 but I'll teach you some of the tricks of the trade in these lectures。Al right。So。

I do want to do one toy example， all of our other examples will be actually quite real examples。

 so this is the only sort of simple toy example。Why am I doing it。

 reasonason one is just to make all this stuff a little less abstract so you're sort of sure what we're talking about。

 but secondly because I want to develop some of your geometric intuition about what it means to solve a linear program and of course it's much easier to have geometric intuition when you have two or three variables you're in two or three dimensions than if you have 100 dimensions。

Okay。So。Consider the following。Wein near your program。

So it's going to be just two decision variables， x1 and x2。We want to maximize their sum。

 that's the objective。So I have to tell you about their constraints。

So let's say that I'm going to require both to be non negative。Those are two of the constraints。

And then I'll pause at an upper bound on two specific linear combinations。

So that's evidently a linear program， two variables for constraints。

So among everything so what is it asking us to do， among everything that satisfies all four of these inequalities。

 find the one with the biggest sum。So what would that look like in a picture？

Since there's only two dimensions， we can think about candidate solutions as points in the plane。

Were there x1 and x2 coordinates？So。First， before we worry about what's optimal。

 let's just worry about what points actually satisfy for these inequalities。Well。

 let's just go through the inequalities one by one。So first of all。

 the first two inequality is say we basically are only looking in the non negative quadrant， right。

 the northeastern quadrant。So wanting x1 to be。Greater than zero says we should be on the right hand side of this line of the y axis。

And saying that x2 should be non negative says we should be north of the equator。

 so above the x axis。So how about these two constraints， so let's start with this one。

 so's I mean it's probably simplest to just say， okay， where does the line defining this inequality？

Hit the axes。 So for what values of x 1 and x2， do we have 2 x1 plus x2 equal to1。Okay。

So that's a line， right， the solutions to 2 x1 plus x2 equal 1。

 so we sort of think it might hit this zero1 or two times and hits it twice。

RightSo if you take x1 to be 0 and x2 to be 1。This constraint satisfied with the quality。

When going if you take x1 to be half and x2 to be 0。

 it's also satisfied with the quality on this axis。And so the entire line segment between these。

We'll also satisfy that with equality。So the set of solutions。

 the satisfying equation is just a line in the plane。So symmetrically， right。

 And so what is the what is the。Constraints say it says you have to be。Southwest of this line。

 right So2 x1 plus x2 should only be less than one。Okay。So this is 2x1 plus x2。Almost one。

And then symmetrically， you've got this。This has not really drawn very well to scale。And your minds。

 think of this as symmetric。So what's the feasible region。

 well it's points that satisfy every single one of these inequalities。

 so it has to be in every single one of the four half planes that we mentioned has to be above here to the right of here。

 below here and below there。So that's going to be this。Parallogram or this trapezoid。

So it's called this or feasible region。Okay so the feasible region is the set of all ways to set the decision variables so that all the inequality constraints are satisfied。

 possibly with equality， possibly not with equality， possibly with slack。So any questions about that。

 everyone see that that's the feasible region。So how about optimizing over the feasible region。

 So we're supposed to maximize the sum。So a good way to think about that geometrically is if you think about it。

 so that's saying we want to go in the direction of the vector 1 comma 1 as far as possible。 Ie。

 we just want to go northeast as far as we can。So what can we imagine doing Well。

 think about the level sets of this objectiveive function。 So it's a level set。 Remember。

 so if you fix a value for a function， the level set is just all of the inputs to the function that give you that value。

 Okay， so you might want to know， what are all the pairs of points。 if I feed it into this function。

 I get the value 10。And usually I have to erase what the previous class did in this room。

 which I think is some linear algebra section。But I fortunately noticed before I erased it。

That up there actually are the level sets。A linear function。So they're just these parallel lines。

So one line for each possible value that the function can take on，The lines go orthogonal。

 perpendicular to the direction of the objective。 so if the objective is going straight northeast。

 the level sets go straight from northwest to southeast at a perpendicular angle。

Because all of those have dot product zero with the objective function。

 so they all have the same objective function， whatever it may be。So in this picture。

 the level setss for this objective function are just 45 degree lines， parallel。Okay， and as。

We look at higher and higher function values， we're looking at level sets that are further and further northeast。

So in saying that we want the point of the feasible region。

With the biggest objective function value x1 plus x2。

 what we're saying is we want the feasible point， which is on the furthest out level set。

So just imagine in your mind that you do kind of a sweep line algorithm。

 Okay so you start a 45 degree line way down here。You just move it to the right。

At some point you're going to hit the feasible region。

 you're going to be passing through the feasible region。

 and then just at the point that you're about to have no intersection at all again with the feasible region。

 you pause， you stop。So this is like the last level set， in this case。

 the most northea eastern level set that intersects the feasible region。

That's going to be your optimal point。Right。So in this case， the most northeastern point。

 the one on the final level set is this corner here。Okay。So this is the point one third。

 one third for an objective function value of two third。So any questions about that？C。

Say goodbye to the level sets there。But keep them in your mind。Allright。

 so this was just a toy example。 And you may be wondering， you know。

 is any of this geometric intuition an artifact of the us being in two dimensions。

 The fact that we can draw it。Its an artifact of being in two dimensions。

 but actually all the intuition we just developed is not。

 all the intuition we just developed is true for general linear programs。

 so the algebra remains the same even when we can no longer visualize it once we have many variables。

So， in general。Right， so notice the number of dimensions corresponds to the number of decision variables。

So imagine you had a linear program with more like 1，000 decision variables。

 which is not at all unreasonable， super high dimensional space。But it's still true。

That the feasible region， okay， it's not a polygon， polygon is what you'd say in two dimensions。

 but it's the higher dimensional generalization of a polygon。

 so it's the intersection of half spaces。Okay。So one linear inequality is one half space。

 so the boundary of the half space is where this inequality holds with equality。

 So remember when you have an equation， the solution set for a single equation is going to be a hyperplane in space right so if you're an Rn you're going to have a hyperplan of dimension n minus1 that's going to be the solutions of a particular equation with an inequality you just get everything on one side of the half plane of the boundary you get a half space。

So one linear inequality gives you one half space to be in the feasible region。

 you have to satisfy every single inequality， so you have to be in the intersection of all of these half spaces。

So that's what feasible regions look like in general。 In your mind。

 you might just want to think about like in the 3D a dodeahedron， something like that。

 but in general， this is true。 intersection of half spaces just like that was the intersection of four different half planes。

And so again。The level sets of the objective are just going to be parallel hyperplanes。

The objective function will serve as the normal vector to these hyperplanes， okay。

 so just like the picture I era you just going have these parallel hyperplanes。And again。

 let's say it's a maximization linear program。 You just want to go as far as possible in the direction of C。

Okay， so you've got to be feasible， you got to stay in this intersection of half spaces。

 and you want to go as far as possible in the direction C。 So again， in your mind。

 at least this isn't how you code it up in your mind， you can think about this sweep algorithm。

Where you just start down a minus infinity and sweep this hyperplane perpendicular to the vector C and look at the last point that it touches the feasible region。

 that's going to be the optimal solution to the linearar program。

So I say farthest in the direction C that's assuming you want to maximize， you want to minimize。

 you want to go farthest dimension in the direction minus C。So in some sense， I mean。

 thinking abstractly about linear programming problem， it's actually very clean。

 it's a very simple problem。 You just have the higher dimensional analog of a poly of a polygon。

 so known as a polyhedron， and you want to go as far as possible in some direction while staying within that polyhedron。

That's little yeah， that's geometrically exactly what a linear program is。Okay。

any questions about that？So another piece of intuition we get from the figure。

 which holds more generally， so notice where the optimal solution was。Okay。

It wasn't somewhere in the middle of the feasible region。It wasn't even in the middle of an edge。

Hey was at one of the corners of the polygon？Okay， so confusingly， these corners。

 they're called vertices。Which conflicts， obviously with the graph terminology， but so be it。

So generally， a vertex。So generally。Opt equals。Or vertex or corner。Of the feasible region。O。

So the last point at which the level set is going to intersect the feasible region。

 it might be a point， maybe if it's just lined up exactly so， maybe it meets an edge。

 but then all points on that edge are going to be optimal。

 so in particular the endpoints are optimal and so on。So I'm not going to move this formally。

 it's actually a little bit annoying， but it's correct， and the geometric intuition， I hope。

 is a proof of plausibility that this is what's happening。So you have this indial object。

 has lots of corners， again， you can think about a dodeahedron。

 but it gets much worse in higher dimensions， but at least you know that one of those corners is the optimal solution。

 the corner which is furthest in the direction that you want to optimize in。

So there are some edge cases。Which I don't want to dwell on， but I want to point out that they exist。

Both these edge cases can happen and linear programming algorithms are coded up to deal with both of these edge cases。

So the first problem could be there's no feasible solutions at all。And if this is you know。

 if you feed into an LP algorithm， something that's infeasible。

 you want it to tell you it's infeasible correctly， right that's sort of the goal for the algorithm。

So like in this example。If I added an extra constraint saying that x1 plus x2 has to be at least one。

Then there'd be no feasible solutions， like because the maximum value of x1 plus x2。

 we computed is two thirds。 So that have an example of an infeasible linear program。

Can certainly happen。The other thing which can happen is that the optimal value can be unbounded。

So plus infinity， if you're maximizing or minus infinity， if you're minimizing。Now。

Hofully it's clear that a necessary condition for this to happen is that your feasible region is unbounded。

You has to have some direction where you can go forever， because if it was bounded。Well。

 then remember， you're just given these coefficients， this objective function， these Cs。

 if it's bounded， every feasible point will have some bounded objective function value。

So the only way this can happen is when you're dealing with the feasible region is's unbounded and the converse doesn't hold just because it's unbounded doesn't necessarily mean it's going to be infinite。

So again， in this case， you want your LP algorithm to tell you that it's unbounded and all of the existing algorithms will do that。

All right。So any questions about that？So I've spent the time so far just trying to get you to think in what I think of as a simultaneously helpful。

 simple and accurate way to think about linear programs， obviously I haven't discussed at all。

 like what does it mean to actually write a program for a computer to tell us to do like a sweep line algorithm or do something else okay and I'm not going to say much about it。

 I'll say a little bit more on probably Thursday so what I'm not going to talk about right now is what do the algorithms for solving linear programs look like。

Rather， what I want to do next is motivate why we care about those algorithms by showing you a bunch of applications。

 Okay， so if we can solve linear programming， then we can solve a bunch of other things that we care about。

 Okay And then for now， just take it on faith。 There are really good algorithms for linear programming。

😊，Okay。So applications， so things that reduce to linear programming。

 so honestly you could teach easily a full course just on kind of famous and important applications of linear programming。

 I'm not going to do that of course， but it's a very you know zillions of things can be modeled as linear programs。

So what I want to do is I want to do a couple examples which are quickly just showing that problems we've studied in the past easily translate to linear programs。

 and then I want to work a little bit harder to show you how some basic problems in machine learning with some tricks also become linear programs that's sort of the plan。

Good。Right， so I guess just a historical comment， so when you programming。

 it was developed by George Danzaig in 47， I'll tell you more about him later。

And so 47 was right after World War I， so they were really motivated by military applications。

 so they were thinking about things like you know how do you ship supplies from the factories to the troops as cheaply as possible and if you think about like 47 that way predates computer science so like the Stanford CS Department was founded in 65 almost 20 years later。

 and we didn't have an undergrad major I think until the 80s so this is way before computer science even though they were really doing algorithms。

 but now you know there really are a lot of sort of you know know quintessentially computer science examples which fall into the linear program camp So those are the ones that going to try to emphasize in class。

Okay。So when I first said about motivating inequalities， I mentioned max flow。

 So let's return to max flow。Now in fairness， Maxflowlow also predates computer science。

 but we're getting closer mid 50s。So the claim is that， you， Max flow。

 almost if you just look at the definition of the problem。 It's immediately a linear program。 Okay。

 but let me just， you know。Make sure this is clear to everybody。So。

So we need to decide them decision variables and the constraints of the objective。

So what are the decision variables if we want to have a linear program encoding MaxFlow？

One variable per whatt？Edge encoding what the flow on the edge。 Okay， that's what we're solving for。

 right So that's what we want to know the answers to。Okay。

 so we have M decision variables where m is the number of edges。All right， so constraints。Well。

 I'm sure you remember we had two types of constraints， we had conservation constraints。

 we had capacity constraints。Conservation constraints， what do they say。

 they say flow in equals flow out。Okay， great， how do you actually write that down in terms of these decision variables？

Well， for all vertices other than the source and the sink。So remember Delta minus。

 this is the notation for the edges sticking in。So this is going to be the flow going into V。

And so saying that it equals flow out just says that something over the edge is outgoing from the sum of those flows。

 and I get the same number on both sides。Okay。So strictly speaking to put it in the form that I told you about over here。

What I should do is I should subtract this right hand side from both sides and get a zero here。

 So this will have sum of some Fs and minus some sum of some other Fs equals 0。Observe that this is。

 in fact， a linear constraint。 right， When a decision variable appears， it appears just by itself。

 and then they just add it up。So that's exactly what linear means。So these are equations。

But then we also have our capacity constraints。And actually， there's one other set of constraints。

 do you remember？Yeah， non negative。So remember in a linear program。

 priori decision variables are allowed to be positive or negative。

 so if you want them to be non negative， you got to explicitly put that into the linear program。Okay。

So the number of constraints we have is n， or rather n minus2。Plus 2 m。Okay。And really。

 by definition， by the definition of a flow， the feasible solutions to the system of equations and inequalities are the feasible flows in the corresponding body network。

 really just define flows as the feasible solutions。And then for the objective function。Well。

 I can literally just write down the exact same expression I wrote down for you when I first defined it for you。

So it's the flow going out of the source。We want to maximize。Okay。Again。

 that just was by definition or objective function for max flow。And staring at it。

 it's definitely linear， right， It just sums up a bunch of Fs。

So this was meant to be a really kind of easy translation， agreed？

Effortless to take max flow and make a linear program。Okay。

Now we worked on these different graph problems and you sometimes we got lucky。

 we sort of changed the problem， but it reduced to one we already knew how to solve。

 but then sometimes something would just seem like harder like we'd add costs and that was a whole different dimension so we went from maxflow we talked a little bit about minco flow on Thursday and I mentioned now you need new optimality conditions you have to sort of redesign algorithms。

 which is true if you want sort of the absolute fastest problem specific algorithms but if you're taking a linear programming approach。

I want you to notice。It is totally trivial to just change this linear program so that it's suddenly the min cost flow problem。

Yeah。So the main thing is。Okay。Now edges also have costs。

And so now you have a new objective function。Which is minimize。Some over the edges。

The amount of flow on the edge times the cost per unit on the edge。Okay。

 this' is exactly what I wrote down Thursday is by definition。

 the objective function value of Minco flow。Now I had to do a tweak to the conservation constraints。

So because if you remember， I defined the problem in saying the feasible solution should push D units of flow from the source S to the syncnc T。

 so you'd also want to have。At S。Flow out equals D， and it would be redundant， but if you want。

 you can put at T。Flow any equal Steve。And again， this is a linear constraint， just in the same way。

 these are linear constraints。And that's it boom， all of a sudden we have a linear program for Mincost flow。

So we didn't redesign anything。 We're sort of， I'm envisioning a situation where we have a black box that solves linear programs。

 And again， in the real world， you do have black boxes that solve linear programs， okay。

So you figure out how to translate MaxF， you're like， I don't actually want costs。

 trivial modification to the linear programming formulation。反正。

So that's giving you an initial sense of kind of how flexible these are and how powerful that flexibility can be。

All right， so that was example too。Min cost flip。So any questions about that？Everything clear so far？

Then let's move on to some examples that。Some of you may have seen related material if you've taken CS229。

 if you've taken some machine learning。But。It'll both be problems we have not yet talked about in 261。

 it'll also be at least slightly non obvious uses of linear programming。

To applicationplication three。Fitting a line to data。Okay。Okay。

So you want to be thinking of some picture。Like this， where you have points。Precisely。

What's the input？So you have Mpoint， P1 up to Pm， these are hli in some dimension D。For this lecture。

 I'm totally fine with you always thinking about D equal to1 that's already a quite interesting case in general。

 though， a data point could have multiple features as they're called or dimensions， so for example。

 you know maybe each data point corresponds to a third grader。And we have a tuple。

 like maybe a triple saying， you know， what's the income of their household。

 how many years of education do their parents have， and how many books do they have in their home？

That would be associating a triple of numbers with each of these data points。

 so they would be d equal3。In the picture D equals one。Okay。

 and then you're also given what are called labels。L1 at the LM。And these are real numbers。

This could be， for example， the test scores of this particular third grader when they were in third grade。

Okay。The score I should say， it's one dimensional。So in this picture。

 the way I've done it is think of these as just real numbers， d equals 1。

 and think of plotting them on the x axis， and then think of plotting the corresponding label on the y axis。

Good。So what's the goal？Well， this is one of the most basic forms of what's called supervised learning。

 what a supervised learning mean， it means not give you labeled data， so the data are the P's。

 but they also tell you the answer in some sense， the ground truth， the Ls， the labels。

So what you want to do you want to， at least in this very simple example。

 try to understand the label as being a simple linear relationship of the points features。

So we want to compute a linear function。H。Mapping basically P's to guesses for L。Such that。

If I apply the linear function to X， I get something that approximates， not X P。

I get something that approximates L。看。You know， and pictorially。

 it's what you think we're trying to find。We're trying to understand as best we can a linear fit。

 so a linear explanation of the labels is a function of the features。

So this isn't precise yet because this is a squiggle， I haven't told you what the squiggle means。

But you see at least， at this level what I want。So what are we solving for， we're solving for H。

 We're solving for this linear function。 Okay， so again， let make it make clear the P's are inputs。

 the L's are inputs。 We're solving for H。Okay。So there's a couple of reasons you might want to do this。

 so one， and this is what you hear more in the machine learning class， you want to do prediction。

Okay，So maybe actually， given some new third grader who hasn't taken the test yet。

 you want to have a good guess about what they're going to score。 Okay。

 so you learn about their features， you learn about all the relevant aspects， you feed it into your。

L your function H， and you interpret its output as a guess or prediction for what the label of that point should be。

 Okay， so you train， meaning you solve for H onlabeled data。

 and then you apply the results to unlabeled data you get later。In statistics。

 you may hear a story that's a little bit different where you're more just doing data analysis or data correlation or data exploration。

 so you just want to know， is there a simple linear relationship between when I'm observing these test scores say and any of the features。

 are they positively correlated negatively correlated by how much。

 so the coefficients of this linear function give you that kind of information？All right。

It's a very basic problem， how does linear programming help？Let's be clear on the decision variables。

I want to make sure everybody understands this。So we're solving for a linear function H。

So linear functions are parameterized or characterized by their coefficients。

So we're really solving for the coefficients in this linear function。

 So those coefficients are going to be our decision variables。coefficients A1 up to AD。

And then also an intercept B。All real numbers。Of the linear function。H of Z。Some over J equal 1 to D。

 AJ。Zj plus B。Okay。So there's a bunch of equivalent ways to define linear functions。

 one of those ways is just functions of this form。Okay。So you take as input， D numbers。

 D real numbers， you're allowed to take some linear combination of them。

 some fixed linear combination， and add something。Okay， so that's a linear function。

Solving for the best linear function just means solving for these coefficients in the intercept。

So there's D plus one decision variables。Is everyone clear on that？So again， the P's are given。

 fixed， L's are given， fixed， we'resolving for H that is re'resolving for the A's and B。All right。

 so let's specify what we want right， So if all of these points were coline。

It's pretty clear what we do， right， We just return the line that goes through them all， Okay。

 but that never happens， okay。So you're looking for a line which does well。

 so how do we quantify that？Well， so first let me define the error of a particular line。

 a particular function H on a particular point。So air。On point I。And geometrically。

 the error is just going to be the vertical distance。Between。So in this picture。

 it can be the vertical distance between the data points， comma label plotted。

 and whatever line you picked。Okay， so the length of this is going to be an error on that point。

In general， it's sort of the difference between the actual label of one of these points and what your function predicts for it。

Okay。So we're going to call this EI， and it's a function of the depends on the linear functions on the coefficients A and B。

So what do we do， so we say， well。Let's plug in。The I point point Pi into this function defined by A and B and see what we get。

So J equal1 to D， AJ。PIJ plus B。So this by definition is the value of the linear function on this particular point P super i。

So this is our prediction， or this is this linear functions prediction of what's up with。Point I。

 but we actually know the ground truth for point I， right， We know it's label。So from this。

We want to subtract what we know to be the right answer。So that's going to be the error。Actually。

 we want absolute values here。We want error to only be positive。好的。So if you're too high。

 it's an error， if you're too low， it's an error， so we take the absolute value。Okay。Okay。

So now the question is to， again， we're sort of  striving for an objective here。

So how do you combine the errors on different points into a single objective function？

So we're going to do not the most common one， but still one which is interesting and used to some extent in practice。

So you minimize over coefficients， A in intercepts B， the sum of the errors。看。

So that's how I'm going to define the problem of fitting the line for today。

Some of you will have seen a different definition of an objective for this problem in the past。

 what would that be？Sure， so what。Yeah， I mean， you're saying this said， yeah。

There are ways of saying the same thing。So more common is to square these。look at squared mean error。

And so if you have squares， it's not linear， you can use linear programming。

 it's actually still tractable by something called convex programming。

 which if there's time I'll say a little bit about at the end of the course。

So in addition to being able to solve this using linear programming。

 it's not actually a crazy objective to use， so one advantage this objective has over the least squares is it's more robust to outliers so imagine that in this data set。

Actually， because of a noisy sensor or something， you had an X way up here。

Suppose I added this to the data set。That's going to drag the best line further up。

And if you think about it， if you're minimizing sum of squared squared errors。

Then this point is going to be a much squeaier wheel with squared errors than under just normal errors。

 so this is going to dominate the computation， and so that's going to drag the line further towards the blue point with the squares than it would with this near linear function。

So that's one reason you might care about this objective。For today。

 the main point is just it's will help us further understand how to use linear programming。

So no constraints。So I told you what the decision variables are。

The coefficients intercept of the linear function， I told you the objective minimizes some of the errors。

No constraints， A's and B's can be whatever they want。So are we done？Do we have a linear program？

Is there anything nonlinear that I've written on the board？Good。

So there is an aspect so I mentioned one example which said you can't take a variable and take the log of it because that's not a linear function。

 but actually if you take the absolute value of a function。

 that's not a linear function of it either so as stated。

 this is not currently something you can feed into a linear programming solver。However。

 it turns out absolute values are quite benign and usually there's a simple trick which turns them into linear。

 so let me show you what that trick is。To an issue。Not linear。あ。ち。So trick。

So when you use the fact that the absolute value of a number is just the maximum of either x or minus x。

It's one way you can think about the absolute value if you really want to。So。What's the trick？

We're going to add extra variables。 Okay， so we'll still have a1 through A D。 We'll still have B。

 but we're also going to have。E1 through EM。Where M is the number of data points。

What we're hoping is that this little EI will be equal to that absolute value to that。Capital EI。

Term。And the way that we enforce that that happens is by adding more constraints。So， basically。

We're going to have two constraints， one for each of the two possible cases that determine the absolute value。

So let me just take the definition of capital I subai， remove the absolute values。

So it should be at least that。But keep in mind， this might be a negative number。Right。

So I had a second constraint。Thishi just says it's also equal to minus。Of exactly the same number。

Okay。So if this is5， this is going to be minus5。Yeah。And the claim then。Oh yeah。

 so what's the new objective？Well， the objective is the same as it was before， except。

That objective wasn't linear because it had absolute values， but with the objective。Some of the Es。

This is a linear objective。Because it's just a sum of a bunch of decision variables。

 and if you look at these constraints， these are also linear constraints。Don't forget。

 so E is a variable。A is a variable， P is fixed， part of the input。B is a variable。 L is fixed。

 part of the input， but importantly， you never see two decision variables multiplied against each other。

 That's why it's still linear okay。All right， so I get to a linear program and the key points。

Is that at an optimal solution of this linear program？

It's going to be the case that the decision variable e sub I is equal to exactly what we want it to be equal to。

Namely the error。Okay。So why is that true， so suppose the error is like five？Okay。

Then we're gonna have two constraints， one， which says it's at least5， and one says it's at least -5。

So EI certainly can't be strictly less than five， because one of the constraints literally says it has to be at least five。

So by feasibility， EI can only be bigger than what we want it to be bigger than the absolute value of what's in the upper right。

There are feasible points where EI is strictly bigger。Then what's on the upper right corner。

 but those wouldn't be optimal points。So for some reason。These constraints read 5 and minus5。

And you looked at a feasible solution where EI was equal to6。

We'll I'll show you a better solution where I just round EI downs from6 to five。Okay。

 so that'll give me a smaller。I should say， minimize。

So that'll give me a smaller objective function value， a better solution。So by feasibility。

 it can only be bigger than what we want it to be， and by optimality。

 it's going to be equal to what we want it to be equal to the error。Okay。Good。

So any questions about that？So how would you fit a line under this metric。

 you'd literally just write down this linear program， it has M plus d plus1 decision variables。

 and it has two M constraints， you'd feed that in， you could ignore the EIs if you want。

 but the A's and the B's would give you the coefficients for the best linear fit under this particular notion of fit。

Questions。Everything clear。Okay。So last application。Again， drawn from machine learning。

 sort of very basic problem from that domain。Trying to figure out a good linear classifier。

 these are also called half spaces， these are also called perceptrons。So basically。

 the problem is very similar to fitting the line with the following difference in the previous example。

 we wanted to predict a real valued quantity like the test score of a student。

Here are the assumptions is we just want to predict the binary。Object， okay， like given an image。

 is it of a cat or is it not of a cat， that's it。So the picture you might want to have in mind here。

So this is now with D equal 2。So you're given a bunch of points。

Some of them are labeled positive examples， i。e。 they are cats。And some are negative examples。

 they're not cats。And you want to find a linear separator you want to draw。A hyperplane， so that。

All of the positive examples are on one side， all of the negative examples are on the other side。

And again， if you could do this， if you can find such a hyperplane。

 how do you use this later for prediction of unlabeled data， given some arbitrary image。

 you just check which side of the hyperplane does it lie on and then you answer cat or not cat as appropriate。

Yeah。All right， it's a little more formally。So the input。You have M positive points。P won the PM。

 those are the cats。M prime negative points。The non cats。

One way to think about this so before we had these labels。

 so we still have labels now the labels are either just like positive or negative。

 and I've just partitioned the points for your convenience into the positive subset and the negative subset。

So we still have the labels， they're just very simple labels now。Go。Compe a linear function。

Just like before。H of z equal to sum。Jco1 to D， AJ。Zj plus B。Such that， as we said。

All positive examples are on one side， all negative examples are on the other side。So such that one。

HPI greater than zero for all the positive examples。And two H of QI。

There's less than zero for all negative examples。Okay。So again， the P's and Q's are given。

And what we're solving for is H。And we're again thinking of H as being defined by its coefficients。

 A1 through AD and its intercept。系。So the way I've written this it seems。 And so for now。

 no objective function。 just a feasibility question。

 there or does there not exist such a linear function。And staring at it， I mean。

 it feels like it looks really， really close to a linear program already。Again。

 with decision variables， they went through AD and B。

The only thing which is different from a linear program， and this relates to an earlier question。

 is that we have strict inequalities in our constraints。

We're solving for a linear function so that it's strictly negative on the negative points and strictly positive on the positive points。

 strict inequalities aren't allowed in a linear program。But actually， it's very easy to。

Sort of simulates strict inequalities。With inequalities in a linear program。So how do you do that？嗯。

So the trick is to add just one additional variable。

 but so additional variables were helpful before to model absolute values。

 we needed M of them then now we just need one extra variable and that's going to be measuring how far away from zero we are in each of the two cases。

O。So it's going to look like maximize over Dlta。And the decision variables here are the A coefficients。

 the B intercept， and this delta。And so we're going to replace this by just saying it should be greater than or equal to Delta。

We're going to replace this by saying it should be less than or equal to minus delta。So subject to。

Ya。Yeah。And notice that there exists a solution。To the original problem。

 if and only if there exists a solution here with a positive value of Delta。So feasible。

In the original problem， if and only if。The optimal value here is positive。

If you can find a feasible solution with a positive delta。

 then it actually says something stronger than strictly Dlta。

 it's actually strictly bigger than zero， it's at least as big as delta with delta bigger than zero。

Okay。So that's quite nice。We'll revisit this example later， but is everyone clear right now。

 So if you want to find one of these separating hyperplanes， or rather。

 if you want to check whether or not there exists a separating hyperplane。

 it's really just a straightforward linear programming computation。Yeah。Okay。

 and I want to emphasize this is really a super basic primitive in machine learning。 Okay。

 so it's not not at all a native of example。 It's a quite， quite real example。

So the last point I want to discuss， well I guess second the last point I want to discuss。

 which again will sort of showcase the versatility。Of this language for writing down linear programs。

I want to show you a couple of other topics very related to this one。So， you know。

 if I tried to pass this off as a practical subrine。

 you would be right to make the following complaint。You could say， you know。

 real data is never going to look like that。Maybe you're going to have more pluses in one side than minuses and the reverse on the other side。

 but you're not just going to have all these pluses hanging out over here and then totally segregated all these minuses over here。

 There's going to be some intermggling。 if nothing else just from noise in the data， okay。

And if there's no way， right， so imagine I just changed， so imagine you had a corrupted data。Point。

 and this actually was recorded as a plus。This is a data entry error。Okay。

So now there is no hyperplane， which puts all the pluses on one side and the minuses on the other。

You can solve this LP and it's just going to go back and tell you， oh yeah， it's infeasible。

 there isn't a hyperplane。Okay。But you kind of want to say， okay， but you know。

I still think it's like mostly separable， give me a hyperplane to use for prediction tomorrow， right？

So how do you do that？So how do you overcome？How do you look at the more general case where there need not be a perfect separator？

It's a question。What if no perfect classifier？All right。

And so what I want to do is I want to show you how two other。Concepts and machine learning。

 which are sort of like have been big buzzwords over the years。 You know。

 I just want to convince you there really is just some more linear programming tweaks。

 you really kind of already know what's going on， you know。

 including with the basics of like support vector machines。 If you've ever heard of that。

 Don't worry if you haven't heard of that。Okay， so let's look at two possible answers for this。

So what do you do if there's no perfect classifier？

Well so I think the first and more obvious thing to do is the same thing we were doing when we were fitting our line so remember when we fit a line to real values。

 we were assuming they weren't all colinear so there was no perfect line。

 so we just looked at the error that a line made on each point and then we sort of summed up the errors so we tried to do the same thing here。

So minimize error。去去去。So here we have to be a little careful how we want to define error。

I think the most obvious way to define error would just say find the half space。

 which misclassifies as few of the data points as possible。

That's actually a hard problem both theoretically and in practice。

 so rather people use different notions of error， which you can actually optimize over。

 so I'm going to show you one very commonly used notion of error which admits a linear programming solution it's something called hinge loss。

So here's the idea？So in our minds， we have the following like dream。 Okay。

 we're hoping that the data has the property。Sorry， ideal that there exists in H。Such that let's say。

We said strictly positive， but let's say maybe even like at least one。For all the positive points。

And a most minus one。For all the negative points。So this would say actually something stronger。

So in a picture like this， So to satisfy these constraints in a picture like this。

 it would have to be the case that each of these points not only is on the correct side。

 but actually， their vertical distance from the boundary should be at least one。Okay。

 so there should be a big distance between every minus and the boundary and also a big distance vertically between every plus and the boundary。

 So this is called having a large margin in machine learning terminology。Okay。So geometrically。

 that's what these constraints correspond to。 Not only do you want to separate the points。

 but you want them to be at least one unit vertically away from the boundary。

Now this choice of 1 minus-1 is a bit arbitrary， but I have to fix some constant just to get a normalization。

 so I'm going to fix1 and 1。All right，I mean define find hinge loss。So on a positive point。Right。

 so I really want your classifier to put this vertical distance one or higher above the hyperplane。

 So we'm going to do is if you put this point less than one above the hyperplane。

 if you only put a8 above the hyperplane， I'm going to penalize you for the difference。

 so I'll penalize you 0。2 if this plus point is only 08 above the hyperplane。If it's only 0。

3 above the hybrid planee， I'll penalize you 。7。If it's below the hyperplane。

 I'll penalize you accordingly， so if it's one below the hyperplane。

 I'll penalize you two okay so that's the hinge loss。 basically it says for every point you say。

 okay， how far would I have to move this so that it's where I want it to be in namely vertical distance at least one away from the hyperplane on the correct side。

So how do you write that math so this is just。This。So as H drops below， so loss is bad。

 so higher loss is worse。So as this drops below one， remember you're hoping this is one or more。

 as this drops below one， your hinge loss on this point goes up and up and up。So actually。

 there's a detail。It's also not a good idea to just reward the classifier for putting points way on the correct side of the boundary so you're not going to get a free 100 points just because there's this one outlier that is way on the correct side that tends to not work so well。

So we're going to take the max of this with zero。好的。

That'll ensure in particular that the loss is always non negative。Okay。

So that's for a positive point。And then on a negative point， you're just going to do the same thing。

Socept you're going to flip this around。Okay。So is it clear。

 so what I've defined is I said fix a linear function that is fixed choices for the coefficients A1 through AD and the intercept B。

That defines an H。So we can now talk about which corresponds to choosing a line geometrically。

 so we can now talk about for a fixed line， we can talk about the hinge loss of that line with respect to each of the points。

对。Which？Measuring the difference between QR。6Q I minus多。Yeah。So as soon as this is。嗯。I see。 Yes。

 you're right。So the point is you want to be incurring loss as soon as this is any larger than minus1。

 so when this is minus1， this will be zero， that's good， but then as it becomes bigger。

 closer to zero， you're going to be picking up a loss。Thank you for the correction。Good。

 any other questions？All right。So。The claim is that minimizing hinge loss is just an LP。

Or it can be encoded as an LP。And this just is， you know， if you follow the example so far。

 you should sort of see how this goes。 Okay， so your first attempt would be to say， okay。

 what are the decision variables， same as before， A1 through A D plus B。What are the constraints。

 no constraints？What's the objective， minimize the sum of these things，What's the problem？

The problem is this is not a linear program。Why is it not a linear program。

 it's because in the objective function， we have these maxes。And that's a nonlinear operator。Okay。

But we had this same problem earlier when we were talking about fitting a line when our objective function had absolute values in them。

 and remember an absolute value was really just a max between x and minus x。 What was the trick。

 We added one extra variable for each term of the objective function and a pair of corresponding constraints saying it's at least something and at least minus something。

And that exact same thing works here， the only difference is your two constraints instead of saying at least something。

 at least minus something， one constraint says EI should be at least this。

 the other constraint says EI should be non negative for positive points， for negative points。

 one constraint saying EI is at least this， one constraint saying EI non negative。

 otherwise it's exactly the same as thefi the line example。あ。Questions about that。Okay。So if not。

 I have one last trick I wanted to show you。So this is we asked the question what do you do if there's no perfect classifier。

 we agree that if there's a perfect classifier， we're done， we just solve an LP and we find it。

What do we do if there isn't one， well， so one idea。

 I thing the easier idea was to minimize error instead。

 except that you're going to misclassify some stuff。Here's a more sophisticated answer。

And I'm just going to show you the tip of the iceberg。

 but basically what I'm showing you is sort of the initial idea of what's called SVMs or support vector machines。

 which if you take CS229， you'll hear a lot more about。So idea number two。

Is to not restrict ourselves to lines， allow nonlinear boundaries。So like imagine。

Your cats and non cats sort of look like this。Plususees and minuses。And you observe that。

 you know well。You can't quite get a linear separator。

But you can sort of get a pretty simple separator。Perfect separator between the pluses and minuses。

 one that looks sort of like a quadratic curve。So that moivates the idea of having。

Non nonlinear classifiers。But then， I mean， clearly we were getting an enormous advantage from the linear classifiers of computational tractability。

So how can we have sort of a richer set of classifiers without giving up on the ability to use linear programming。

 on the ability have to actually solve for it efficiently？So here's the way we do it。

Is we just take the original data points。And we add extra features。And so what do you do。

 you take what was originally a D vector。Okay so this is like the household income and so on。

And or you know pixel values， and you map this to a D prime vector。Where D prime is bigger than D。

 possibly much bigger than D。O。So you enrich the feature set。 And you may say， well。

 how do you do that， I mean， you know， doesn't that seem like a very domain dependent thing。

 to some extent， Yes， but there's some tricks of just automatically blowing up the feature set。

 which in particular allow you to fit quadratic curves and that kind of thing。

So what I want you to have in mind。Is think of。So if I feed in a D2 pull the feehi。

Think of what it gives me back。 So it gives me back the original D features。

So I fit in Z1 through ZD。I get back Z1 through ZD。But then I get extra features。

 which are just the z1 through Zd squares。And all the cross products of the different features。Okay。

And again， I encourage you to think about the D equal 1 case where this is already interesting。

When d equals 1， it just says。Phi of Z。Is Zz squared。好的。

So we kind of artificially inflated the dimension of each of the data points。

And now the idea is just to use exactly the same linear program we had before for finding a separating hyperplane。

 but instead of solving for a linear function defined in ddimensional space the original features。

 we're going to solve a linear program in de prime dimensions using this augmented set of features。

 but again we're just going to be solving for coefficient。

 so it is just going to be a linear program， albeit with higher dimension。So now the goal is。

Compute A1 up to AD D prime， so we're working in this higher dimensional space。Plus。

 an intercept such that。Same thing as before。So for all positive points。

So I sum over all the D prime coordinates。So now instead of talking about the original point P。

 I talk about the sort of inflated version of P on the bigger feature set。So I write this like this。

So it's a linear combination with coefficients AJ on the vector。Of enriched features。

And in the intercept， I want this to be bigger than zero for all of the positive examples。

And then I want the same thing to be less than zero for all negative examples。

So a couple comments to help you kind of。Start to understand what's happening here。So。by enriching。

 so if we have a new feature set which includes all of the old features。

 so like here we started with Z1 through ZD， we have Z1 through ZD plus a bunch of other stuff。

You certainly don't lose anything for any linear function of the original features。

 for any hyperplane you might have tried with the original point set。

 you're certainly welcome to try exactly that same hyperplane now just by using a coefficient of zero on all of the extra features。

So the point being is we've only enriched the set of things you can separate the points with。Now。

 how does this connect back to talking about quadratic curves So again。

 think about the special case where we just have one dimension， so we map a point z to Zz squared。

So there's two features， sort of one corresponding to the original value and a second coordinate that's for the quadratic coordinate。

Imagine so now you're just computing two coefficients and A1 and A2。

 Imagine you set A1 to 0 and A2 to 1。Now all of a sudden。

 your sort of new function H is z squared plus some intercept B。Okay。

 so by enriching the feature set and plugging in nonlinear terms， explicitly into the features。

You can actually still solve for a rich or separating hyperplane， not really a hyperplane。

 a richer curveb。 And again， the thing you remember， what makes this work。P was fixed all along。

 P is part of the input， so you can do any kind of preprocess on P。

 and there's no way you're going to screw up linearity。

 You're just changing some constants into other constants。O。Anyways， now that we have this formalism。

 we can basically just pretend like these were our original data points。So we did prepro。

 we blew up the number of dimensions， and now we just have an instance of our previous separating hyperplane problem。

 which we observed was just a linear program。And again。

 the one caveat is that the dimensions has gone up。 It used to be D plus one。

 Now it's a D prime plus one， where D prime is possibly bigger than before。 So like here。

The dimensions blows up by a quadratic amount。Now for proper support vector machines。

 there's sort of an extra trick， which allows you to do the computations as efficiently as if you were working in the original space。

 but that's something you should really take 229 to learn more about。

So next time I'll start talking about algorithms and also about duality， see you then。

