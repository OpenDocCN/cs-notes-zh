# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p15 -15-(Lecture 15_ Smoothed Complexity and Pseudopolynomial-Time Algorithms).zh_en -BV1yqVzzqEQ5_p15-

Today， we're going to be having our final lecture on smooth analysis。

 So this idea of problem instances， which are sort of chosen worst case by an adversary。

 but then subjected to a small perturbation by nature。

And smooth analysis know historically and also the last couple lectures。

 the emphasis has been on you study some fixed algorithm of interest， for example。

 the simplex algorithm or local search or whatever。

 and you want to understand that algorithm through the lens of smooth analysis whereas in this lecture rather than trying to understand algorithms we're going to try to understand computational problems through the lens of smooth analysis。

 so we're going to see what we can learn about essentially computational complexity by seeking out algorithms with polynomial smooth complexity。

 the answer will actually be very crisp， at least within a certain natural class of problems。

 the answer will essentially be if and only if that is the smooth complex is polynomial if and only if the worstcase complexity is pseudopolynomial。

 and I'll remind you what that means in a second。Okay， but to really， to make this a crisp。

 if only of statement， we should zoom in on some class of problems so we know what we're talking about。

 So let me start with that。So we're going to talk about binary optimization problems of a particular form。

And there's many， many canonical examples for now think of Napsack as being a canonical example。

 one of the things that we've talked about before that we want to generalize。

So there's going to be n variables in their binary。 So x1 up to xn。These are either zero or one。

 for example， XI could denote whether or not you're including item I in some Napsack。

And then some of the 0，1 vectors are feasible。 And we're going to handle that in a very abstract way。

So we just have some feasible set。F。Which is some arbitrary subset of all possible0，1 n vectors。

 For example， in the Napsack problem， F would denote the characteristic vectors of all of the subsets of items who fit in the Napsack。

 That'll be one example。There are values。Again， just like in the knapsack problem。And the goal then。

 abstractly， is just to compute the feasible solution with the maximum possible value。

So compute x and F。 and again， remember here， x is an n bit vector。Maximizing。V transpose X。

Also known as。Some over the end coordinates of VI times Xi again。

 remember Xi is always going to be zero or1 in this lecture okay。

So I'd like to make that as big as possible， subject to the feasibility constraints。

 actually minimization would be fine too， for everything we're going to say in this lecture。

 I'll stick with maximization for consistency， but you can even think of the vs as being negative if you like。

 and then it's basically a minimization problem。Okay。So like I said。

 one example I want you to keep in mind for concreteness is knapsack。But， I mean。

 let's point out that you can encode many， many problems with this formalism。 And in fact。

 the worstcase complexity of the problem will vary， depending on how you choose capital F。

 the feasible region。 there'll be some choices of capital F that lead to a much easier problem than Naps。

 So， for example， I could define capital F to just be at most K of the coordinates of x。

 say most 10 of the coordinates of x or1。 that would be very easy to solve。

 You just sort by the Vs and pick the top 10 Vs。 and that would give you an optimal solution。

 or you can encode problems far harder than Napsack in this formalism。 For example。

 capital F could denote the characteristic vectors of independent sets in some graph。Okay。

 so as you vary F， you get different problems， right。But so these end things。

 you choose them are not。 But then there are also these global constraints encoded by capital F on which combinations are allowed and which are not。

Any questions on that？Is there a general approach to solving minor optimizationization problems Well。

 so it depends if you mean in polynomial time or not， I mean， if it's not。

 if you don't mean in polynomial time， then integer programming would be one obvious approach if you mean in polynomial time well then you know you get this plethora of differentmp complete problems and as we know different heuristics seem appropriate for different problems so you would not expect some useful meta algorithm covering all of them。

Okay。So， and in this lecture in particular， we're not going to be able to say we're not going to say some sweeping positive result for all of these。

 but what we'll be able to say is among problems of this form， one good thing is true。

 if and only if a different good thing is true。 smooth polynomial complexity。

 if and only if pseudo polylynomial time worst case complexity so that statement will make within sort of the realm of these binary optimization problems。

 and of course， there' will be plenty of problems for which both of those are false。

 like independent， for example。Okay。Let me give you another。

 I do want to point out that there will be implications for the management of this lecture。

 not just for NApsSAC， so we'll also get it。Results that we don't know。

 So let me just sort of sketch a quick second application now。

 and I'll ask you to think about it a little bit more on homework number8。

So let me let me talk about a scheduling problem。Suppose you're given end jobs。

Which each has three parameters。So depending on which homework problems you've done。

 you may have seen things like this。So let's say each job has a processing time PJ。

 that's how long it takes to execute we're thinking about just having a single machine。

 okay so you're just trying to figure out how to sequence end jobs on a single machine。

 each machine has some amount of time that it takes to run， assume you even know what that is。

Each job has a deadline。Okay， so you're welcome to think of these as you know。

 the homework assignments that you have at any given time。

 you have an estimate of how long it's going to take。Yeah。

 you know when it's due now unfortunately you're so overscheduled。

 you're actually not going to be able to complete all of the jobs by all of the deadlines so you're going to have to make some hard decisions and there's a cost。

CJ， which is the penalty you incur if you fail to complete job J by the time of deadline DJ。

And then the objective here is to minimize the total cost that you incur all of the jobs that you fail to fail to meet by their respective deadlines okay。

So you want to minimize the cost of the late jobs。So I hope you all agree that's a well defined computational problem。

 may not be obvious how to solve it， but I hope it's clear what it is was asking you to do。

So on the homework on homework 8， I'll ask you to give a pseudoponomial time algorithm for this problem Okay so a dynamic programming based algorithm。

 you know very much sort of in the spirit of what you know from Napsack problems okay and the reason I're going to ask you to do that is because we're going in this lecture have a positive result for all problems that have pseudopolynomial time algorithms okay we already know Napsack does this is just meant to show you a second application of sort of the meta theorem。

 the general theorem we're going to have today。So that's all I was planning on saying about this。

 But here's， you know， just again， proof of concepts。

 There's multiple things we're talking about at once。

 Probably the simplest thing for you to do is just keep knapsack is the canonical example in your mind as we go through the lecture。

OK。Right to homework。Sudo polynomial time。Okay， so it is NP hard。

 but it can be solved in suit upon time。All right。So back to the question about this lecture。

 Which problems emit smooth polynomial time algorithms。

 specifically which binary optimization problems admit them。So as usual。

 we have to be precise about what we mean by smooth complexity。

And it's going to mean the same thing as in the last two lectures。

So we're going to have this very pleasingly。Kind of agnostic or general notion of smooth instances。

So。Each VI， so these are pretty much the only numbers right in this abstract binary optimization problem。

 So if something's going to be perturbed， at least the way I've written it so far。

 it seems like it's got to be the Vs， right。So each VI is drawn independently。

From a density function， F sub I。From 0，1 to 0，1 over signal。Okay。

So this is exactly what we were doing last lecture when we talked about pretocurs of Napsack is basically what we were doing when we were talking about TSP in the plane as well。

 so notice that I'm scaling the values in effect to lie between zero and1。

 it's more or less without loss of generality and then again the assumption is that the distributions are not too spiky the density is everywhere bounded above by one over sigma so the area of support in particular has to be at least sigma。

So it's at least a little bit spread out。Everywhere。Okay。So， and then as usual。

 what are we going to mean by having polynomial smooth complexity。

 We mean there exists an algorithm with smooth polynomial time， running time。

 meaning it's running time as polynomial and the input size n。And in one over sigma。

So we mean the same thing as in the last。Couple of lectures。 So that's what we're asking。

 Which binary optimization problems admit an algorithm whose expected running time where the expectation is over the perturbation。

 whose expected running time is polynomial and n in one over Sigma。 That's the formal question。

All right。And so as I said， this is a very satisfying answer。To that question on the left。

 if and only if。Solvable and randomized。S州pome oil。Okay。That's what it means。right。

 so let me remind you a little bit about what it means to be pseudopnommal time。

 So normally when we talk about that， we're thinking as the numbers as being integers。

 although really， whenever you have anything in finite precision by scaling。

 you can think of them as integers as you want。 It's just some binary encoding。

So pseudopolynomial time means you can run in time proportional or polynomial in the magnitude of the values of the numbers in the input。

 so for example， in Napsack。You can run in time maybe polynomial in the NApsack capacity capital W。

This is not a polynomial time algorithm because polynomial time always means polynomial in the amount of bits it takes to represent the input。

 the number of keystrokes required to actually describe the problem So if your Napsack capacity is a billion。

 it does not take a billion keystrokes to describe that capacity it takes about 10 on your keyboard。

 So log of the magnitude of the number is the appropriate encoding size for numbers so anapsack dynamic programming algorithm。

 which runs in times something like n the number of items times capital W。

 the Napsack capacity is not polynomial because it's not n times log W。

 but it's pseudoponomial n times W and that's still good in many cases。

 right if these numbers aren't too big and your polynomial in them。

 then you're quite happy So that's one reason why why you're happy with pseudopolynomial time algorithms okay。

So this is what it means you run in time， you can think of it either as you run in time polynomial in the magnitude of the numbers。

 or you get to run in time exponential in the encoding length of the numbers。

 Both of those are perfectly reasonable ways to think about it。Okay。So and again。

 this distinction is only relevant when you're talking about problems where there are numbers， right。

 So if we're talking about independent set in unweighted graphs， there's no numbers。

 right So there's no there's no notion of pseudo polynol time。

 But when you're talking about something like a binary optimization problem where you have these Vs and the V's。

 depending how you want to think about it， you have the Vs could be super big or alternatively。

 if the V's are described to very fine precision。 It's more or less the same thing by scaling。

 then all of a sudden this is a relevant notion。But again。

 just think about Napsack as a concrete case of the type of problem that we're thinking about。Okay。

So。To go back to the theme that I mentioned at the very beginning。

 we're using smooth analysis in this lecture to understand algorithms not to understand problems。

 So when we talked about， say the simplex method， we said， oh， well， worst case is exponential。

 When we switch to a smooth model， the running time drops from exponential to polynomial。

 that's what we learned from smooth analysis about simplex Here， we're something very interesting。

 which is that problems which are hard in the worst case sense suddenly become easy。😊。

In a smooth sense， we go from a situation worst case where unless P was NP P。

 there does not exist a polynomial time algorithm to a situation after adding these really small perturbations。

There simply is poly on the time algorithm。 Well， again。

 expected running time over the perturbations。 Okay。

 so the problem goes from hard to easy before the algorithms went from fast to slow or sorry from slow to fast。

 Now， the problems go from， from hard to easy。And again， I mentioned this last time， but。I mean。

 it sort of， it seems feels surprising if you're sort of， you know。

 just used to the thinking of MP completeness as a death sentence。 But I mean。

 for the people who solve MP complete problems in practice。

 it's long been known that Napsack and other things that emit pseudopolingial time algorithms do seem empirically to be amongst the easiest of the MP complete problems。

 So this is sort of a satisfying way that we see that actually playing out in the theorems as well。

All right， there's also a connection and this I'll ask you to think about on the homework。

 There's sort of a third right So so on the left hand side here is polysmth complexity over here is pseudopolynomial time。

 There's a third notion which is also roughly equivalent to the other two which is which is admitting fully polynomial time approximation schemes。

 And that's sort of a best possible approximation result。

 So what that is is it means while you can't this is now all worst case notions。

 let me just write that let me just write down the acronym real quick。

So a fully polynomial time polynomial time approximation scheme。

 So what this algorithm does is it takes as input and instance and an approximation parameter epsilon。

 and it returns an approximate solution whose objective function value is within one plus minus epsilon of the best possible。

 And it does so in time。 polynomial and the input and polynomial in one over epsilon。

 Okay So the point is you can't get 100% of optimal， but you can get as close as you want。

 Your algorithm is going to run longer and longer and longer as you want to get closer and closer and closer。

 But actually， most empty complete problems are much more resilient than this for most empty complete problems。

 you cannot actually approximate them arbitrarily closely and bigger and bigger polynomial time amounts。

 Okay， so this is sort of the best case scenario。 So that's that's yet another sense in which these are sort of the easiest of the MP complete problems。

 So you get this collapsing of all of these different notions of relatively easy MP hard problems into this。

At PTTS category， the same as the problems that are solvable in。 roughly， yeah。

 so that's exactly what I'll ask you to explore in the homework。YeahAnd that's somehow more folklore。

 That's less of a what we'll do today， The connection between smooth complexity and pseudo polyoma is more has more of the feel of a theorem。

 whereas the connection between pseudo poly and F P tasks is a little bit more of an observation。

 Folore observation。 So， so it's a good thing to think about on the homework for that reason。😊，Yeah。

 so all three of these things are more or less the same Moulos and fine print。Good。Other questions。

Okay。So let's get going with the proof then。So I'm going to start by proving the slightly easier direction。

Which we're going to show the if。You have polynomial smooth complexity。

 then you're solvable and randomized pseudo polynomial time。

 any of these binary optimization problems， right。So。Consider a binary optimization problem。 so that。

There is a smooth polynomial time algorithm， called it A。Now， what we want is we want to use A。

 and we want to use A really as a black box。 We're not told anything about this thing。

 We're just told that it exists。 So pretty much the only way we can think about using this hypothesis is kind of running it。

 basically， That's the obvious thing to do。So given this。

 we want to somehow construct now a worst case algorithm。

 but that's allowed to run in pseudo polynomial time。

So our goal is harder in the sense that we want a worst case guarantee。

 but easier in the sense that we're allowed to run slower。S a upon uponnoial。Okay， so consider。

A worst case instance。Of whatever binary optimization problem we're talking about。

With weights with some V Is。 Okay， and think of them again， scaling， if necessary。

 Think of these values as being integers， okay。And that's really without loss of generality when you're talking about pseudoon andal time algorithms。

All right。But so now， actually， I just did this as an intermediate step。

 I'm gonna to scale the values again because for these smooth， you know， to have the。

 the perturbations measured correctly。 we're thinking about the values as。Being between zero and1。

So take this worst case instance with integer Vs scale by the largest of the values。 Vmax。

 these n values right now， they're all integers divide them all by the largest。So scale by Vmax。

So Vs are in 01。And now here's the point of all this。

So it turns out a major theme in this lecture is to understand how much better the best solution is than the second best solution。

 That's going to be really important today。 Okay， it hasn't really， you know， in some sense。

 it's like a numerical version of some of the stability clustering stability properties that we had。

 Those are much more complicated because there are combinatorial。 Now。

 we're just looking at the objective function value。

 So the gap between the best and the second best is going to be important。

So think about the value of the best solution。Minus the value of the second best solution。And。

Think about these different ways。 One way to think about it is suppose there was a unique solution。

 If there's multiple unique solution， sorry， a unique optimal solution。

 If there's multiple optimal solutions， put them all here。 Okay。

 so look at the one hand of the highest objective function value that anything can get。

 And then amongst everything， which is not optimal， look at how high you can get。 Okay。

 so once you go to that first subopti solution， how much lower is it than the than the highest。

So I claim。We have a lower bound on how small this could be。As a function of Vmax。

So consider the worst case instance that has integers。

What's a lower bound on how far apart the best and the second best objective function values are。

 one， right？So when we scale by V max， then it means that this difference has to be least1 over V max。

Okay。So the smaller the numbers that were being used in this instance。

 the better of the lower bound we have on this gap， between the best and the second best solutions。

And our intuition should say like bigger gaps are better for us， for better for an algorithm。

 right the more pronounced the optimal solution relative to everything else， somehow。

 the simpler it should be defined it， right。Okay。So how is this useful？Well。

 actually we're pretty much done now。 so here's the algorithm。

 so we're given an algorithm with polynomial smooth complexity。

 here's going to be an algorithm with worst case pseudopolynomial complexity。So two steps。

So we take this worst case instance after scaling。And now we pertuurbed the values。 Okay。

 And so let me be clear， right， So so far， when we're talking about smooth analysis。

 this perturbation was being done。 We're sort of thinking of it， at least as being done by nature。

 right， It sort it was measurement， error or whatever， right。That's not what we're doing right now。

 Okay， we're using perturbations actively as part of our algorithm to solve a problem。 Okay。

 these are just fictitious perturbations we made up to guarantee that our subroutine is going to run fast。

😊，To be clear we are we constructing an algorithm that going to run the pseudo polynomial time or expected toial time It's going to be expected to polynomial time。

 Yeah， so it's going to be a randomized algorithm。But it's it's going always it's going to be a so called Las Vegas algorithm。

 which is always correct， but it has variable running time yeah。But if it's FPTAs。

 can we just approximate it to one over VmX and then we know well okay。

 but then I'd have to prove a connection between this and an FPTA。

 which I haven't done right so on homework I'll let you investigate the rest of these ideas。U。

So we're going to perturb。Each VI。By random number。Delta I。Between zero and one over 2 n Vm。

So uniform distribution on that interval，Independently for each VI。Now。

We do pretty much the only thing we can do。 Like remember， you know。

 this theorem is totally abstract。 We know absolutely nothing about this problem。

 We have no idea what it is。 The only kind of foothold we're given is that we're told that we have a subroutine。

 We're handed a subroutine， which runs fast for perturb instances。 So what are we doing。

 We're making up pertu instance。 we're going to run A。

 Think about that's all you could do pretty much。So， run a。On perturbed distance。

And we just return whatever A returns。So what we need to show is that this algorithm。Returns， well。

 first of all， that it solves the problem。Correctly。

 and then second of all that it does so in expected pseudonoial time。So correctness。

Let me draw a picture that's going to be useful a couple times。呃。

When we think about perturbations and roundings and other things。

So consider the original problem that we had with these worst case values。

 So there is some optimal solution over here。So before the perturbation。

 this was the higher things we'd get。And then there is some second best solution。

And we have this observation that there's a lower bound about how far these are apart。Right。

 so this is at least。One over Vmax。Okay， and then we have all this other stuff。Actually。

 any two distinct solutions have to be one over you max apart， but we don't really need that。 Okay。

 we just need it at the top。Now。We pertuurrb things， right？And so that picture changes。 right。

 We sort of like flicking those little dots around， okay。So imagine that， you know。

 we're just thinking of holding who what the item sets are fixed。

 But now we're changing the objective function。 We're changing the values。

 In case so we're switching from measuring by the values V to measuring by some V hats or V hats or these perturbed versions of the Vs。

 So all those solutions， the objective function values is gonna move a little bit because the objective function moves a little bit。

😊，On the other hand， in each component。 So we got a couple of things going for us。

 right So each X is either 0 or one。 So let's remember what our objective function is， right。

 So our objective function is just sum of our I equal one to N。A V X， X is 01， if X is zero。

 who cares？If X is1， then it's going to move by whatever VI moves by。

VI is not going to move by more than1 over two n times v max by the definition of our perturbations。

This thing has n sum ends。O， so in the worst case， it moves by this in each of the n coordinates for a total perturbation of this objective function value of one half or one over2 V max。

So in the worst case。This guy maybe would go downward。Actually。

 if you look at the way I've defined the perturbations， this can't happen， but just humor me。

 So we're worried about sort of the opt。 remember， this is ground truth， right。

 These are for the real values。And we're worried in general。

 about the optimal solution getting worse when we perturb and other things getting better。

 when we perturb。 Okay， and we pinned everything down。

 the perturbations are so small that nothing moves by more than one over 2 V max。

 And then they started one over V max apart in the first place。 so they can't cross。

So the relative ordering of everything actually in this case。

 but in particular of the top two solutions remains the same， there's no inversion。

So this movement and this movement。And most one over2 B max。 And， of course， there's no magic there。

 That's just how we define the perturbations。 we defined it。 So it would be true。So， correctness。

Each solution。Pterred by less than one over2 v max。So with probability one over the perturbations。

The new optimal solution。Was an old optimal solution。O。

If we started with many solutions that had exactly the same objective function value。

 they won't in general， all still have the same objective function value。 But the point is， you know。

 whichever the best of those after the perturbations， that'll be our new optimal solution。 Okay。

 and that was one of the optimal solutions to the original problem。So that's correctness。 right。

 Basically， we solve a pro problem， but the perrivationations are so small。

 The optimal solution is exactly the same。 So we can just。

 it's legit to just return the optimal solution of the pro instance。Okay， running time。

Also straightforward。So by assumption， the subgroupoutine we were handed。

 A has a polynomial smooth complexity。So that means it's expected running time。Is Polly in N？

And one over sigma， where one over sigma is an upper bound on the density because we're picking things uniformly from an interval。

Of length， one over 2 N V max。 That means one over sigma is exactly2 N V max。

 This is the case where you just uniform on your support。 Okay。

 so the density is just the reciprocal of your area。So。Our expected runtime is just this plugging in。

NV max，2 N V max for one over Sigma。And that's pseudonomial。Okay。Any questions about that？Yeah。

 so are you doing that all the Vs are in。Yeah， I mean， if they're not。 I mean。

 the V Is are given is just binary numbers。 They're just represented， right。

 And so I'm just saying if you want， interpret them as integers。

 So if you want first scale them up or just， you know。

 first clear denominators to make the minitegers and then scale them back down to put them in 01。

Yeah， other questions。O。So you might wonder， you know， is this direction good for anything？

So after all， we could apply it to something like NapsSack。And what does it do。

 It gives us like a randomized pseudo polynommal time algorithm for Napsack based on what we proved last lecture。

 So last lecture， we approved of Napsack has smooth poly complexity so we can feed it into this reduction and get a randomized pseudo polyno time algorithm。

It's not really something we needed， right？We learned in undergrad algorithms。

 one or more deterministic pseudoalal time algorithms for NApsAC that probably had better running time than this。

 and also we didn't have to work so hard or we didn't have to do all that stuff last lecture。So。

 you know。You could imagine maybe other problems where this will get you a novel randomized pseudo polynoial time algorithm。

 I'm not saying those don't exist。 But I don't think that's the number one reason to care about this。

 I think the number one reason to care about this is actually the contrapositive。

 So negative results。 okay， and understanding problems which cannot have polynomial smooth complexity。

So notice by the contrapositive if a problem cannot have a randomized pseudo polynomial time algorithm。

Then by this reduction， it also cannot have polynomial smooth complexity。

So this is sort of like the perverse direction of using this reduction， the dishonorable direction。

Or you expand the frontier of negative results。嗯。So， so what。

 So are there problems that we know cannot have pseudopon time algorithms。 Well， yeah， actually。

 we know that almost all imply problems cannot have suitablehe algorithms under suitable complexity assumptions。

 There's a notion of a problem being strongly n hard。

 And the whole point of the definition of strongly empty hard is to say that you cannot have a pseudoponno time reduction。

 So I'll ask you to look up that term and talk about this a little bit on homework 8。 okay。

So what it says is while there are problems like Napsack and some other so-called weekly MP hard problems where the complexity drops from hard to easy when you switch to smooth analysis for most impbi completely problems。

 that will not be the case。 and we learn that from this reduction。 That's。

 I think the main reason to care about this direction。

Is there a way to use this to get any deterministic。啊 good。I don't， totally generically。

 it seems hard to me。You know，Unless you knew that A， because you know nothing about A， right， the。

 how would you deranize a totally generic A。 So if I told you that it had smooth。

Complexity in some sense， that for a worst case perturbation， it was still polynomal time。

 but then that would actually imply that the original that that problem was poly timeolable anyways。

You'd have to have some assumption， I think， on the D random。

 the prospects for de randomizing the subroutine A。In some limited sense。So it seems tricky。

I guess the way I think about it that way is if you can use this reduction for some problem you actually care about to get a randomized algorithm。

 then I would zoom in and just focus hard on that problem and say like。

 this's a good evidence that some deter thing must exist。 What does it look like。

 But then maybe start from scratch using the specifics of the problem。

I think that's kind of a takeaway more。Okay。So that's nice。 We sort of know that。

Killer applications for problems going from hard to easy。

 We should be looking at weekly and be hard problems。 Those are the pseudo polylymial time algorithm。

 So now it's sort of the best case scenario is that any problem with the pseudopolynoml algorithm actually does have polynomial smooth complexity。

 And very happily， that actually turns out to be the case。 So let's prove it。😊，So。Yeah。

 so just again， sort of a quick preamble。 So we're gonna to be given。So now the assumption is。

That the algorithm emits a pseudo poly on time algorithm at。

we need to show that it's smooth complexity as low as polynomial。

 And so this is where we're really doing something different。

 right We're really not fixing an algorithm and analyzing it。 We're really saying。

 given that our goal is polynomial smooth complexity。

 what kind of clever algorithmic ideas can we dev。 What with something new that actually meets that goal。

 Okay， so here we're really starting with the analysis goal up front。

 And then we're designing the algorithm crafted to that goal。

 as opposed to the last couple of lectures， which were the reverse。嗯。All。是不还有一。I。

I thought that so if we could solve a single NPR problem in polynomial time。

I thought theory then lies that we could solve every problem and your problem in polynomial time That is correct for worst case polynomial time computation。

 worst casenom， which is not what I've done for you。No， no， okay。

 but so there's not a polynomial reduction。other。So for example。

 if we had another NPR problem and we couldnoial like do polynomial reduction to Nepsec。

 then we could use this right And then the question would be how do you interpret what you get right So what's the distribution and then this problem also has to be So where's your distribution come from？

So let's start with S。Are you proposing a notion of a perturbed sat instance？Or not。

Or you' going to run the reduction and then perturb it。嗯。So the short。

I think you'll find it challenging to come up with a sensible notion of a pertturbbed Sa instance。

 And if you reduce sat tonapsack and then pertuurrb。

 you have the problem of trying to map back yournapssack solution。

 or in particular for decision problems， you have to prove that after you perturb it。

you still are respecting the yes， no of the original hard sad instance。

 and the hard sad instances are going to be ones that give you Napsack instances right on the edge of being satisfiable or not at a given target。

 and so it's where you expect perturbations to turn it into a 50，-50 who knows kind of situation。嗯。

Good question。 Other questions。All right， to the converse。 So now we know what we want。

 we want polynomial， smooth complexity。 And all we've got to work with is some black box。

 which runs in worst case through to polynomial time。 How do we use it。Well， let me。

Let me first tell you about the key analysis tool we're going to use。 Okay。

 so I'm not going to tell you the algorithm yet。 I'm going to tell you this really nice lima。

And so I'm going to call this the isolation Lima。Not to be confused with the original isolation limo。

 which I'll put on the homework just sort of for educational reasons。

 that was developed maybe in the 80s for parallel matching algorithms。

 But it turns out the same idea is hugely useful here。

 And for some of these smooth analysis problems， which is just sort of a very cool connection。😊，And。

What we're going to do here will be familiar to you now that we've done a couple of these smooth analyses。

 So this is going to be the part where we identify a bad event。

Which is simple enough and sort of just aligned enough with everything else that is really easy to upper bound the probability that this bad event happens。

 using the fact that it's a smooth instance。 So in the last lecture， like we worked really hard。

 And at the very end of the lecture， we finally had such a bad event here。

 I'm just starting with this bad event。 And we're just going to analyze it。

And then I'll show you how building on this we can get what we want and iton complexity。So。

So for this binary optimization problem under discussion， and actually。

 this lemma doesn't need there to be a pseudo polynommal time algorithm。 Okay。

 so this will actually be true for any binary optimization problem， easy， hard or whatever。

So fix an instance。And for a parameter epsilon。We're going to call an index or a variable。Epsilon。

 bad。If。We do two thought experiments。 First， we say， okay。So， you know。

 the real optimization problem is to optimize this value over all feasible sets。 Let's say， well。

 first of all， what if I made you include item I， if you will， in the NApsSt terminology。

 What if I force you to set X I equal to1。And then I force you to。

 and then you could maximize over the rest。 And then I do the same thought experiment with X equals 0。

Okay， so I'm going give two solutions， one with x equals 1，1 with X equals 0。

 each best with respect to that constraint。 Of course， one。

 the better of those two will just be the optimal solution of the whole instance。

 because the optimal solution either has x equal 1 or X equals 0。

 But one of them will generally be inferior。And the bad case is where those two solutions have almost the same objectiveive function value。

 Okay， so you're almost agnostic as to whether I force you to set X equal to 1 or I force you to set X equal to 0。

 It barely changes your optimization problem。That's going to be our bad event。So if the obsolution。

With X equal 1， let's say optimal solutions with Xi equal 1， X equals 0。嗯。Have value。

Within epsilon of each other。Okay。So that' can going to be a bad event。

It's actually quite easy to prove an upper bound on the probability of this bad event。

So specifically。Let's show。That。The probability。 So we're thinking about a smooth instance now， Okay。

 so I should say that。So the probability here is over the perturbations of the Vs。

So probability that there exists。An epsilon bad。Index I。Is it most epsilon n over sigma？Okay。

So the smaller the epsilon， So the worse the event and the smaller the e boundon the probability。

 the more spiky， you know， the bigger one over sigma can be， the more spiky the distributions。

 the worse our upper bound， as you'd expect。 Okay so this's the bad event。

 We have more and more control over it as the distributions are less and less spiky。All right。

 and so this proof should it resembles to a large degree our proof in the Pareto curve lecture when we finally were up bounding the probability you know of those indicator random variables in IT if you remember that this is definitely a little bit simpler。

 but it's very similar。So。We're trying to upper bound that any index eye is bad， fix your favorite。

So let's overrun the probability that a fixed index I is bad。And again。

 in the spirit of last couple of lectures， we're going to show that I alone。

 So V I alone has enough randomness to give us a good upper bound in this event。

So're just going to get rid of the rest of the randomness so we're proving even stronger inequality。

So condition on VJ for all G， not equal to I。Okay。So at S minus I。And respectively。

 S plus I denote the。Optimal solutions with Xi set equals0 into1。And to now。

 let's notice because there's so little randomness left。At this stage。

 we know a ton about S minus I and S plus I。So。S minus as I， actually。We know everything about it。

What is S minus I， It's the best solution where X I equals 0。 Okay。

 We know the value of everything other than I。And so we don't know V I。 But if X I equals 0。

 who cares about V I doesn't matter。 Okay， so what we're optimizing over， it's independent of V I。

 So they all just have these fixed values。 So there's just one of them， which is the best。Okay。

So S minus I is just fixed。And again， remember， throughout， we've conditioned。

In this part of the proof on VJ， all J not equal to I。

And we even know the exact value of S minus I because we fixed the values of all the x's for which it sets to one。

So also， it's value v minus s。Now。And again， this is very similar to last lecture。The identity。

A best plus I。没 right。Aso claim is now totally fixed。Right。

We know which feasible among all feasible solutions。For which x I equals one？

We know which of those has the maximum value。And there may be this sort of initial pushback。

 like what do you mean we don't want know what VI is yet， but of course， VI， whatever it is。

 contributes exactly the same amount to every feasible solution with XI equal to one。

So the relative ordering of the values of all the solutions with x equal to 1 is independent of VI。

Okay。So we actually know what S plus I is。So identity of S plus I is fixed。

And we don't know its value because VI is still random， but we know its value has the form X plus V。

Or x is fixed。Okay。And it's actually， you know， there's no mystery what capital X is。

 You just look at this best solution S plus I， you look at the coordinates where it's set to one other than I。

 and you add up all of， those values。 That's what capital X is。

 And then it's going to get this bonus from V。 and we don't know what it is。Do agree with that。

This is the subtle point。 I mean， the good news is you saw something even trickier than this。

 on Wednesday。 So it's of like a slightly simpler version of that。Good。So how could it be？

That this index I winds up Epsilon bad。 Remember， Epsilon bad means the best solution with U set to 0 and the best solution with U set to  one。

 they have almost exactly the same total value。So why is that unlikely？So what would have to happen？

Okay。What would have to happen， Well， basically。We have this solution。With have x cycle equals 0。

The best one with x equal to 0。 And it has some total value， know，1237。

And the only bad case is if this winds up with epsilon of 1237。

That's the only way that index I will be bad conditioned on all the other VJs。

So that means the only way it can happen is the V I lies in this little interval of length to epsilon。

 Okay， Basically， it has to be equal to v minus I minus X。Plus minus epsilon。So I is epsilon bad。

 if and only if。V I。Why is it being essentially equal？To the value of the optimal solution。

Without with x equal to  zero。Minus all of the stuff。

 the best solution with x equal to 1 gets other than from V。Plus， epsilon error。Okay。So， again。

 this is just one smooth random variable landing an interval of。Length to epsilon。

 the den is at most one over Delta everywhere， so this is probably most two epsilon over Delta。

So since F5 of x is the most one over deelta， sorry， one over sigma。For all x。

Probability I is epsilon bad。Is it most too epsilon over Sigma？Agreed。

 just by the density of our bound。So we're just done by the union bound。So given fixed index I。

There should be a two there。Is bad with that probability。

 and there's n of them to take the union band over。So done by Union mount。Any questions about that？

So that's the claim。 Let me now show you how this easily implies what for this lecture。

 I'm going to call the isolation lima。こしこ。It's a coroll area。

And here's what I mean by the isolation Lemma。Probability， and again， this is over the perturbation。

That the optimal solution value。Minus the second best value。So here it is， again。

 that gap between the best and the second best。 I told you it would be a theme。 Okay。

 so here it is again。So after you smooth the instance。The probability that this gap is small。

 meaningan at most epsilon， Repsilon is your favorite parameter。

This is bounded by exactly that same probability。Okay。So let me tell you why。 So the proof of this。

 given what we've already done is just， well， the proof of the claims like two lines。

 The proof of this is going to be like one line。But the statement actually is kind of amazing。

 Really， it's kind of cool。 Like it it sort of corrects a bad intuition that most of us wind up having。

 Let me explain， like， this seems to almost contradict the pigeonhole principle in some sense。

 when you first see it。😊，So let me explain。 So imagine epsilon。You know。

 think of eilon is pretty small， but like inverse poly。

 epsilon is maybe be like one over n squared or something。 Okay， Sigma， you know， some constant。

 Sigma is 10 or whatever， alright。So with those parameters。

 then this is going to be a nice small number。 Okay It's gonna be like theta of one over n。

 if that sounds like one over n squared。And so where epsilon is the gap between these。

 the first best and second best solutions。 So let me tell you why that's surprising。

How many different feasible solutions are there potentially？There's like 2 to the n， potentially。

 it depends on capital F。 but I mean， it could certainly be exponential in N。What is the spread？

Of total values。What is the interval of total values in which these exponential and end solutions lie？

How small could they be the total value？Zero， how big could it be？三个号。

And remember the VIs remember between zero and1。So it's the most n， okay？

So we have like  two to the N solutions。Thrown into。This thing of interval n。

So if the values of these were equally spaced。There would be an exponentially small gap in between consecutive items。

 consecutive solutions。 And indeed， on average， that has to be true。Right。I mean。

 it's just you pick a random pair of consecutive solutions。

 meaning like the k best and K plus first best for an average value of k。

 they really will be exponentially close to each other。It's out here。

Because we're talking about the best and the second best。Actually， they're， I mean。

 they're only inverse poly away。So in other words， I can take epsilon equal to1 over n squared here。

 and it's fine。 Okay， there's only an n in the numerator。 There's a two to the n in the numerator。

So that's what's amazing。 because we're looking at the very top。Of the values。

 they're far more spread out。Then they are in the middle of the distribution or even on average。

 Okay， Yeah， in some ways， this is the bell curve。 exactly。

 some wayss because we're at the very tail of the bell curve， and things are sparse。

 And this is making that precise influence。Where what's the case。Lears spread the top。

 Can you construct input whether even the exhibit is。Well， then this would be false， right？So no。

Yeah。So that's why。 that's where the name of the isolation lemma comes from。

 Somehow the best solution is isolated。 You know， it's lonely at the top。All right。

But we've really already proved it。So how do we just go from this claim to the isolation dilemma？

So let S1 be the best。Let us two be the second best。In particular。They're not the same。So。

There exists， some variable I。Set to zero in one of them。And one in the other。So suppose， oh， yeah。

 I should say there's a word。 There's a word for this in this context。In some of analysis。

 this is sometimes called the winner gap。Okay， so the gap by which the winner is indeed the winner。

So suppose the winter gap was actually small。Okay， less than epsilon。 How could that possibly happen。

 Well， then it must be the case。 Okay， So's okay。 So suppose S1 is has X I equals 0。

It's certainly the optimal solution for which Xi equals0。Similarly， S 2， if it has X equal 1。

 it's the optimal solution amongst everything with X I equal 1。Okay。So if this is less than epsilon。

 if the winter gap is less than epsilon， then by looking at S1 and S2 and choosing I an arbitrary element。

 which is 0 in one and one in the other， we exhibit an epsilon bad index。

So every time the winter gap is less than epsilon， we can witness it with an epsilon bad index。

 That means this is a necessary condition。For this。To this probability， it can only be small。

So a winter gap less than epsilon。Then this eye。Is Epsilon Ba？Any questions about that。And again。

 this stuff， everything on the board right now holds for any binary optimization problem。

 easy or hard。It turns out it's just useful when the problem isn't too art。All right。

So let's get to the algorithm design。So， now， we're going to assume。

In addition to being a binary optimization problem that it has a pseudoponnonymous have algorithm A。

I'm cheating a little bit for simplicity， I'm going to assume that A is deterministic。

 I'll let you check that exactly the same argument would work if a was randomized to polynomial time。

 It really doesn't matter。But think of it as determinististic。不是。All right。

 and so this is worst case pseudoonal time algorithm。We need to prove a smooth complexity bound。

 So the good news is， is we get as input a smooth instance。😊，So we're given a smooth instance。

And again， remember the Vs are in01。Drawn from a not too spiky distribution。

 density of most one over6。So here's our algorithm。In the algorithm， it's a quite nice algorithm。

It's not clear to me。 it's conceivable。 One could have come up with this algorithm without having a smooth analysis motivation。

 but I'm not sure at the same time， I'm not sure it would have ever happened。

Here's our new algorithm。So we have a loop。And so what we do is， we successively unveil。

The bits of the values。 Okay， so we're giving Vs as values。And we unveil their bits one by one。

 obviously from the highest order bits to the lowest order bits。So。With V hat I。Deote the first。

Bbits。Of VI。Let me just make sure it's clear what I mean when I also say that all the Vs are between 0 and 1。

 So let's just make sure what this means。 So when b equals1。

 you're just seeing the highest order bit of everything。

 So you're just seeing a one if V is at least a half and you're seeing a zero if it's less than a half okay。

Once you see the second bit，1，1， that means it's at least three4，1。

0 means it's between a half and three quarters and so forth。 Okay。

 that's what we're doing between0 and1。 and we're just sort of learning you know。

 the relevant power of two each time。So notice V hat depends on B。

 you're going to keep recomputing B hat， but I'm going to suppress the notation on B。

 but remember V hat， that's really with respect to a fixed it， a fixed number of bits。Okay。

So the good news is， is， you know， when B is small， these are small numbers。 Okay。

 They have small encodings。 So pseudoinal time algorithm is going to run fast。

 And we have in our hands a pseudoponal time algorithm A。😊，Right。So use A。To compute。

The feasible solution， X hat。Which by definition， is the one optimal。For Viha。Okay。Now。

 our task is not to be optimal for V hatt。 Our task is to be optimal for the true input。

 the actual V， the actual values。 And so especially early on， when we're looking at only a few bits。

 you might think we've taken such a course approximation of the input that when we solve exactly for this course approximation。

 we get something which actually isn't totally optimal for the real input。So intuitively。

 we want to keep unveiling bits B until we're sure we've got the right one。

 and we don't need to look at any more bits。Okay， so let me state this informally and then I'll explain exactly how I implement it。

But the point of step three is the stopping criterion。So what we want conceptually is that if x hat。

 okay， so we compute X hat by definition， optimal for the truncated things， the V hats。

If X hat happens to be optimal。For me。And now you should complain， you should say， well。

 we don't know V， we haven't looked at V， looked at the first Bbits only。Fine， O。

 but suppose X hat was optimal， no matter what the unseen bits are。

That would be good enough for us also， right they we don't need to look at anything more that we can just conclude we're optimal。

So that's going to be the idea。 So we're never going to look at all of V。

 but we're going to nevertheless have a certificate that whatever V is， we're optimal for it。Okay。

 so no matter。What remaining bits are？At that point， we stop and we return exha。Okay。So。Comment。

So as far as the running time。What， so step 2。So because a is pseudopolynomial。

 remember one way to think pseudo polynomial。Is that you you run in time exponential in the representation of the numbers you're working with。

 Okay， so it's B bits。 So it's going to be something like2 to the B。

So this runtime is going to be polyly。Polynomial and M。And two to the B， in iteration B。

This a suitable I want time out。Okay。So。The question then is， what does this mean？

So it's sort of clear。If we could actually faithfully opt implement step 3。

 I hope correctness is clear。So we have something Xha in our hand。 if a little birdie told us。

 I'm not going to tell you the rest of the bits， but whatever they are， this is optimal。

 of course you can stop， You don't need to look at them。

So let me actually show you we can implement this step in a nice way。 Just running A again， actually。

 okay。And the intuition is very simple。We just want to say， look。

We're hoping we're crossing our fingers， right， So we took this course approximation V hat of the true input。

 We got some feasible solution。 X hat。 We're crossing our fingers that actually。

 even though we solve this course approximation， we got the right answer for the real problem。

 We really want X hat to be optimal forevermore。 So what want to have happen is we want to like。

 well， if on our head， we ran this algorithm for B going off to infinity， X never changed。

 X just stabilizes。 Okay， we keep running A， we keep getting X hat back over and over again。

 even as we feed more and more data。😊，So how would that not happen， What are we worried about。

 what's the concern？The concern is that as we learn more about the true values， the V's。

 this X hat starts looking a little less desirable than it used to。Okay。

 and the second best valuable， second best one gets a little bit more valuable right。

 so let let's think about this， let's drill down。 So what would it mean。

 So what as when we see the next round of bits， we have X hat in our hand and it's our protagonists're rooting for it to stay optimal。

 right。But then we see some more bits， right， What could go wrong， Two things could go wrong。 Okay。

 so first of all， on a variable in X hat， which we've set to one。

The worst case for us is that the next bits is 0。 right。

 So imagine like the first two bits were one and one。

 So we know it's between three/ quarters and one， right。And we're sort of hoping it's high， right。

 because we're including it， right， But maybe we see a 0。 And now we it's at most 78s。

 maybe we see another 0。 And we know it's at most， you know， whatever 1316s， etc cetera。 Okay。

 so0 sort of makes things look less attractive than we thought， Similarlyly。

 whenever we have an x equal 1。Okay。If we see， sorry， if we have an X I equal to 0。

 something we're not taking， then we're concerned the next bit' is going to be a one。Allright。

 so if the first two things were 0，0， we know it couldn't be better than a quarter。 But then。

 you know， as soon as we see a one in the next iteration， we know it's at least an eighth。

 We see another one， then we know it's at least you know， whatever it is 5，16，7，16s or something。So。

 the intuition is。You know， we have X hat。 If all we ever saw were ones where we already have x equal to1 and zeros where we see x equal to 0。

 we'd totally be done。 Okay， But if it flips， if it's completely the opposite。

 we've got to be ready for X hat to switch to something else。 On the other hand。

 if we could somehow just recompute the optimal solution through these worst case settings of the rest of the bits。

 and we still got X hat back。Then we're golden。So that's the insight。 We actually know。

 right We obviously can't check everything the rest of the bits are。

 but we can characterize what is the worst case setting of the remaining bits。

 We can recompute just for that and see if we get the same solution X hat that。So that's the idea。

So let me just be precise about it。So for each eye。

What I'm going to write down is I'm going to write down。

 an approximation of sort of the worst case scenario4 x hat for the rest of time immemorial。

So as we discussed， if it's something that we're actually setting go to one。

Then the worst case for us for the persistence of x hat is to only c zeros。 So in this case。

 So V I'm defining v bar， a new V bar。And so V bar is just going to be equal to our truncated version。

 which corresponds to seeing zeros for the rest of time。 right， So V I hat。

 that's only taking the first B bits。 If I pat it with zeros for the rest of time， that's V bar。

 and it's the same number。 that's the worst case for the things we're already taking。

So for something where it's currently set to 0， we've seen the first B bits。 It's currently zero。

 The worst thing is， everything else is one from now on， okay。

And we don't want to actually keep track of all those ones。 We'll just add2 to the B。

2 to the minus B， excuse me， to V hat。So in this case， we set V hats， sorry， V bar I。

To be v hat I plus2 to the minus B。Okay。And the point is， in that second case。

 that's an upper bound on what the real input is。 no matter what the bits are。 Okay。

 even if all the remaining bits are one， that's still an upper bound on the real value V I。

And so now， to implement 3。What do we do？We're going to recompute。X bar。Optimmal for Vbar。

And the point is this is just one more computation of the type that we've already done。Okay。

 it's exactly the same number of bits。 we're still using just B bit numbers。

 and we're invoking the same algorithm。Okay， so poly and N in two to the be。O。So。Analysis。ち。

And again， the picture you want to have in mind is that same kind of。You know， we have the。Yeah。

Axis of the objective function values。And we're plotting things， you know。

 and things are here with respect to the real values， the V's。

 And now we have two different rounded versions of the true values， the V bars and the V hats， okay。

So if the green dots are with respect to the correct values， which we haven't looked at yet。

 then if we switch to optimizing instead with respect to the V hats or the V bars。

 each of these will have a little shadow nearby。If we switch the objective function a little bit。

 then each of these will change a little bit。And so now the plan is the same thing that we've already seen。

 We're going to show that the V hats and the V bars are close enough to the real ones that things can't move too much。

 and that keeps us out of trouble。that means， but I mean， ultimately。

 we really have to do the proof in a quantitative way because we really care about how big B needs to get before we trigger the stopping condition。

 Okay， so don't forget， we're invoking a pseudo poly time algorithm。

 So our running time is exponential in the representation of the numbers that we're using。

 The running time is two to the B。 Okay， So if we prove that we need to take B up to N to trigger the stopping condition。

 we're toast。Even like log squared， we would not be very happy actually。

 so we really want to say that by the time B gets to logarithmic in all the parameters we care about。

 the stopping condition will be triggered。Okay， that's what we need to prove。So it's good。如。

Let's do it quickly。Good。And did I finish this Yeah so if x bar。So notes。

 So let's proceed to understanding。How different things are with respect to these different objective functions。

Okay， so first of all。If。The X hat we compute in step 2 winds up again being optimal for V bar。

 Then we're done。 Okay， and that's just， by definition。

 We define V bar to be the worst possible ones。 The real inputs are not as bad for V hat as the V bars。

 So if even the V bars has give us back an optimal X hat， then we can just return it and we're done。

So if Xha opts。For both the hats and the bar。Also， for the true input V。

 which is really cool because we never looked at even most of V。 right So it's pretty neat。

So now let's get a handle on how closely our two rounded objectives approximate the true one。

So let's start with the truncated version。 Okay， so remember we' we're fixing an iteration B。

 So this is by definitionion the first B bits of V。So is it bigger or smaller than VI？Small it。

 right， you're just thrown off some of the trailing bits， okay。So。

This is in some interval where the right hand side is V。Okay， it's the most V I。

 How much smaller could it be than V I。Roughly。Right， okay。So。

Because you've seen its most significant B bits in the residual。

 there's only two to the minus B possible range there。 Okay。

 so the most you could be off is 2 to the minus B。All right， so how about for V Bar？

Is V bar bigger or smaller than V？F bars are defined over there。It's doing the same with here。

So you're saying it can't be less。So remember， sometimes v bar equals v hat。

And we just argued that V hack can sometimes be less。But it's a good point that it can be bigger。

 It could be less or bigger by how much in either way。To， right。Okay， so the V bar is。

 it depends on what's up with X hat。 Okay， we have two definitions。 In one case。

 we're underestimating and the other one， we're trying to correct for the underestimation。

 but maybe we weren't underestimating， so they will end up overestimating。

So that's what we know about about the extent to which V hat and v bar approximate V component by component。

So， let's think about。Going from just individual coordinates to entire feasible solutions。

So our objective function is just the sum of at most n of these Vs。Right。

So if you're just talking about， to what extent does the objective function value change。

 it's just going to be the same numbers with the error terms multiplied by n。

 You might get that accumulating from each of the coordinates。

 And let me just be a little sloppy and sort of consolidated everything and say for all X。

 what we have。Is that the objective function with respect to either V hatt or V bar？

This is going to be。Within。N times2 to the minus B。Of the true objective function， V transpose x。

So this is just immediate from。Frombi。All right， and so lay that back to this picture。

 that says if the green dots represent the true objective function value of v transpose x。

 then whichever one of v hat or v bar we switch to measuring instead。

 we get these perturbations in potentially either direction of magnitude up to n times 2 to the minus b。

So one thing that's maybe nice to see is that once minus B hit starts hitting log n。Then this starts。

 we get to start getting some control over this error。

 which we're pretty pleased to see because we know we can only tolerate B up to about log n in our running time。

All right， so upshot。Is that we're done。So here's the claim。

 and this sort of summarizes all the work we just did。 we're done once the winter gap。

Is at least2 n2 to the minus B。Okay。Now， I phrased this in a way that might be confusing。

 so let me clarify。Right， so we're just given this smooth instance。 Okay。

 and they're just these values。 And it has some fixed winter gap。 Okay。

 once you've sort of fixed the values。 Okay， the optimal solutions，1037， the second best one is 1023。

 The winter gap is 14。So it is whatever it is。So what I mean here is that。

 but think about as the iterations of our algorithm proceed， B keeps getting incremented。 Okay。

 so the winner gaps whatever， like 14。 But as B， as we keep incrementing B。

 this keeps getting smaller。 Okay， so there'll be some value of B。

 the first one at which that right hand side is less than this winner gap， okay。So the question is。

 how big does that need to be？Okay， and then why are we done once this is true， Well。

 once the winter gap is bigger than this。That means even if， you know。

 when we look at V hat and when we look at v bar， even though the objective function values of feasible solutions might be changing by most of this much。

 there's still such a big gap between the first best and the second best solutions。

 even if the first best gets decreased by the maximum amount and the second best gets increased by the maximum amount。

 it will still be the case whichever of these objectives we're using。

 will correctly rank those top two solutions。 so it doesn't matter。

 if we optimize with V with V hat or with V bar， we always get back the same solution。

 The optimal one for all three of them simultaneously。 Okay and at that point。

 the algorithm certainly terminates。Okay。So。Now the question is， when is this going to happen？Okay。

 in a smooth instance。So， recall。This。So the point of the isolation memo was to give us control over how likely the winter gap was to be of being small。

 So the winter gap is only almost epsilon， probability to epsilon and over sigma，So， probability。嗯。

That's it。So， let's say。I don't want to set the parameters here， so basically。All right， so to get。

Probability。Of winter gap。let me just set the parameters。So take Delta。Equal to。2 n over sigma。

N times 2 to the minus B。And then。By the isolation Lema。Probability that the winter gap。

I at least this amount2 and 2 to the minus B will be less than delta。Okay， so that's just solving。

That's literally just setting this to Delta and setting epsilon to what we want it to be。

 that winter gap and then solving for B。Okay。So。Equiently。

This becomes at most Delta to the probability this bad event becomes the most Delta as soon as B becomes。

Log。Of N。Over sigma times delta。So again， one over sigma， that's our upper bound on densities。 Delta。

 This is a free parameter。 Okay， so you pick Dlta however you want。

 If you want an upper bound of Delta on this bad probability， then。

Once B hits log n n over sigma delta， that's when the probability gets that small。All right。

 so let me summarize all this。So， thus。For all Delta。The probability that the algorithm halts。So now。

 remember， the running time is polynomial and n， but exponential in B。

 So we're gonna to pick up a So that the exponential will cancel that log。 It'll be polynomial and N。

1 over sigma， one over deelta。It's probably that the algorithm halts。In time， Polly。

In one over sigma。One over Delta。Is it most Delta？Okay。For whatever Dlta you want。

 I guess this is true simultaneously for all Dltas。So that's good。 So if you think about it， I mean。

 you could even sit， I mean， for starters， you could get deelta to be like one over n squared。Okay。

So this would say that this algorithm， this one which just unveils the bits one at a time。

 keeps using a to compute something and then checking with these worst case of E bars。

 So you get the same thing and stopping as soon as you get the same thing。 that algorithm。

Within smooth polynomillial time， poly and N in one over sigma， it completes with probability sorry。

 it does not complete， ah， I see the problem。Sorry， this should be the compliment。All about。

So it does not halt with probably the most one over a Delta。 sorry， probably the most Dlta。

 It does hold probably at least one minus Dlta okay。

So with only one over n squared failure probability terms polyialton。

So that's not quite the definition of smooth complexity we've been using。

 We've been using that the expected running time should be polynomial。

 and that's a slightly stronger statement。 However， with a minor tweak to the algorithm。

 once you have this guarantee， it's very easy to actually extend it to an algorithm that does have expected polynomial running time。

对。So that's the upshot。 So basically the failure probability is decreasing sufficiently quickly in the number of iterations。

 B， so that even though you have exponential running time in B。

 you start getting negligible probability of having to go forward once B hits logarithmic and all the relevant parameters。

Any questions？Yeah。我百啲。I。 I'm confused about why。probably the winter gap is greater than when the doing this D that is。

Should that be less than， I don't know。 Yeah， should be。You're right。That's the bad event， right？

Because we want the better gap to be a certain size， that's right。

 and then it also matches up with that inequality too。You're absolutely right。 So I had this flipped。

 So the bad event is that the winter gap is small because the winter gap is get big。

 then you terminate， right that was the whole point here。

 If the winner back with the winter gap for a given B is big， you're definitely done。

 So the bad case， the bad event when this is too small。

 So we're invoking the isolation limo with epsilon equal to our desired gap。2 n2 to the minus B。

And then that's the most Delta。When B hits this amount。So the way for， the way to think of it is。

 you know， So here is just some epsilon。 Our previous analysis tells us the epsilon we care about。

 Okay， the epsilon we care about is exactly this number。

Because being below that is the only way we're not going to stop。

Then we just threw in a free parameter delta， okay。And then we just said， okay。

 let's solve for the B。When， indeed， the right hand side here。

Our probability upper bound becomes less than Dlta， and this is the B that we get。

And then we're very happy to see all of the parameters popping up in the log bar because the running time is exponential in B。

Sorry after going over， I'll see you Wednesday。