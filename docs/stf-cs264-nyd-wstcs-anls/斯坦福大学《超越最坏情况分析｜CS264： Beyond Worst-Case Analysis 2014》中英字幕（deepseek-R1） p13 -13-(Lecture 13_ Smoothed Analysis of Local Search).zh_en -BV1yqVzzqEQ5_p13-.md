# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p13 -13-(Lecture 13_ Smoothed Analysis of Local Search).zh_en -BV1yqVzzqEQ5_p13-

This lecture we're going to start speaking about smooth analysis in earnest。

 So let me just sort of remind you the salient point of smooth analysis that I told you about last time。

 So this is an example of a hybrid model where you're trying to take aspects of average case analysis。

 aspects of worst case analysis and hopefully get the best of both worlds from average case you're hoping to be able to make really strong and meaningful performance guarantees and from the worst case you're looking for things which are robust guarantees。

 So not overly tailored to some specific distribution and smooth analysis is one particular hybrid model will' be looking at some others。

And the way we described it is that an adversary。 so this is the worst case aspect。

Pick some initial input。 Okay， so you have some algorithm you're going to use。

 and an adversary picks intuitively the worst input for the algorithm that you're using。

 But then nature sort of saves the day。So nature adds a perturbation。

So add some randomness to the input。 case what sort of worst case over the starting point and then average case over this ideally small perturbation that nature adds。

 Okay so as the perturbation gets smaller and small and smaller。

 we're becoming worst case analysis as it gets bigger and bigger and bigger。

 we're basically doing average case analysis。 Okay so the size of the perturbation interpolates。

Between those two models。So。When is smooth analysis is generally useful。

 so it's generally useful when the worst cases for an algorithm seem really brittle。

 like they're going to be destroyed by a perturbation Now these bad examples are all really complicated so you won't actually see one in lecture it would take too much time。

 but the smooth analysis examples will be doing they do have that feature so the claimment queue for simplex if you sort of see it。

 you see it's sort of a nice nice edge example also for local search which we'll talk about today。

 there are bad examples in theory， but they're very brittle it's just clear that they would be fragile and break down under a perturbation。

Now of the various cost measures for algorithms we're looking at。

 it seems like running time is usually the measure which has these very non-robust pathological inputs。

 so that's where we see the killer applications for the most part。 still to this day。

 the original application is the most famous one， the simplex method for linear programming。

 we talked about that a bit on Wednesday from 30000 feet。

 that's all I'm going to say about it in class， the references on the website have more if you want to delve in more deeply。

But today I'm actually today I want to give you a self contained account。

Of another genre of problems that are right in the wheelhouse of smooth analysis。

 namely local search。Okay。And one feature of discussing local search a little bit is while smooth analysis has had some really nice successes in this space。

 in my opinion there's still some really juicy open questions。

 which is just someone has got to solve， so we'll talk a little bit about those at the end of the lecture。

So just to remind you， so local search at a high level。

 so what you do is you have an optimization problem， you maintain a feasible solution。

 you have a notion of local moves that are permitted at each step and you keep iteratively locally improving the solution until you can't do so anymore and then it halts at some locally optimal solution so that's local search in general。

 I'll give you a specific example in a second。So why is local search crying out for a smooth analysis？

Well， so it turns out local search algorithms often do suffer。

 at least in theory from pathological inputs。 Okay， so they're often exponential。Worst case。

By which I mean， from a worst case starting point， you might have to do an exponential number of improving moves before you stop at a locally optimal solution。

On the other hand， you run these in practice and you never， ever。

 ever see these exponential examples， okay？So。You know，It depends on the problem， some。

 but think quadratic or even a little bit better running time typically observed in practice。O。

So this combination is the first thing that makes you wonder about smooth analysis and then if you actually inspected the bad examples and saw how brutalrittle they were。

 you'd really start thinking you want to do a smooth analysis so those are sort of clues that that's the right analysis model to be using to reason about local search algorithmcronys and their convergence time。

Okay。So that's local search just totally generically。

 We're going to do a case study for a fundamental problem that hopefully you all have heard of at some point in your life。

 the traveling salesman travel。Or TSP。And we'll be looking at a special case of the traveling salesman problem where the okay。

 where the city。 So the story is right， So you have a traveling salesperson and they have a bunch of stops they need to make。

 It doesn't matter what order they make them in。 They just have to go to each place exactly once。

 And so the places where're gonna assume the salesperson has to go are points in the plane。

And moreover， we're going to for simplicity be using the L1 metric okay to measure distance between two different points in the plane and a lot of that sort of for simplicity to keep the lecture simple。

 so that's what we'll be thinking about。More general results are certainly possible。So inputs。

 endpoints in the plane。Actually， let's even say in the unit square。Which is almost the same thing。

You we' given endpoints in the unit square。And the goal。Is to compute a tour。Okay。

 so a path that closes back on itself that visits each point exactly once。So P1。

 so really an ordering of the endpoints。That minimizes the total distance traveled。

So remember each P， this is just the next coordinate and the Y coordinate。

 and then distance between consecutive stops。We're going to use the L1 norm。

 same L1 norm that we talked about when we were doing compressive sensing。

 right so just the sum of the absolute values of the in this case， only two coordinates。

 also known as Manhattan distance in this context sometimes because sort of Manhattans like the number of blocks。

 you have to go total going both eastwe and north south。Okay。

And so similar results are possible for other norms。 This is mostly for pedagogical reasons。

 I'm just going to stick with L1 norm。Okay。So you probably know that the traveling salesman problem in general is N complete or MP hard。

 Even this special case is MP hard。So if you don't want to work really hard and solve it exactly。

 then instead one considers heuristics。 there is what's called a PA or a polynomial time approximation scheme for this special case。

 So for any epsilon greater than zero， there is a polynomial time algorithm that guarantees you a tour within one plus epsilon times the minimum possible。

 however， it's very slow because's really just kind of a theoretically interesting algorithm。

 So that's not how people solve it in practice， if people don't solve it exactly that instead they use heuristics。

 local search you know for 50 years has been one of the main heuristics used to generate approximate solutions to TSP instances。

 that's what we want to talk about today。All right。So this will be the problem for the whole lecture。

 clear。Okay。Now， when you talk about local search right so abstractly in each iteration。

 you make a local move which is improving。 So local search is only defined with respect to some notion of what are the local moves permitted so you have to define the neighborhood of each feasible solution。

 So there's many ways to do that， including for the TSP problem。

 but we're going to look at a very simple and wellknow and old way of doing this called the two up neighborhood。

And so this is nice。So you maintain a tour at every step， you start with some arbitrary tour。

 like initially you just go through the points in order of name， say。And。In the generic iteration。If。

You look at two edges in the current tour。Okay， so maybe。At some point。

 you go straight from U to V and straight from x to y。And the rest of the tour is whatever it is。

What you're allowed to do is you're allowed。To cut these two links and rewire。Now。

 if you think about it， there's a couple ways to rewire this， but if you rewire u to x and v to y。

Then you've taken your one cycle and turned it into two cycles。 right So you don't want that。

 That's not a tour。 So that leaves the interesting thing to do is to connect V to X and U to Y。

The rest of the tour， by definition， stays exactly the same。So that's a two up move。

 you have your current tour， it has n edges， you rip out two of them。

 there's a unique way to rewire them that gives you a distinct tour from what you started with。

 that's a local move。So you have flexibility because you can choose these two edges however you want from the current tour to break it up。

But that's the set of local moves available。Alright。

 And so then the algorithm that we're going to be interested in。

Is just generic local search under this neighborhood with the two up neighborhood。

So you just execute。 So you never do anything stupid that makes things worse。

 Okay so if you sort of in your mind think about doing this rewiring and you notice it takes you longer。

 you never do that。If there's many different swaps that make you better。

 we're just thinking that you pick one arbitrarily。 Okay， so if there's some improving move。

 then you do it。So， execute。Improving local moves。Until you can't anymore。So till none remain。Okay。

So by definition， the length of the tour will be strictly decreasing with the number of iterations。

If you think about it， that also means that this must eventually terminate。

There's only an in factorial number of different ways。

 actually less than that by symmetry that you could go through all of the points。

 that's a finite number， so eventually you'll run through all of the cases and because it's strictly decreasing。

 you can't cycle。All right。Now， in fact， where was a lot， of course。

 you'd hope that you'd find a locally optimal solution much faster than that。Oh。

 I should also note note that a given iteration， it's not hard to implement in polynomial time。

 Okay so for example， N cubed is super easy because there's only kind of n squared different edges to try ripping out。

 And then in linear time you can compute the result of the new tour。

 and you just take the best one so there's only polynomial many options So it's easy to execute one iteration in polymial time。

 Really， the question is how many iterations are required。

 And in factorial is not such a great upper bound。All right。

We I'm going to talk about today's drawn from。A paper of anglelert。Rglyn。Invoking。

And there's a bunch of results in this paper。 We're just going to focus on one of them。

 Let me actually state two of them for context。 So the first thing Iler to all prove is that， indeed。

Even in the special case of endpoints in the plane with the L1 metric。

And even for this particular twoap neighborhood， local search can， in the worst case。

Require an exponential number of iterations before halting at a locally minimum tour。Okay。

 so exponential。In worst case。This we're not gonna prove。 Okay， this is sort of a very， like I said。

 This is a very knifestead construction。 Okay， so it's a tour of force。

 It's very impressive when you read it。 And， you know， but I'm not sure if we went over it。

 I'm not sure what I teach you other than the fact that this is true。 Okay。

 knowing that this is true is nice。 Okay， but going through the proof。 again， if you're interested。

 just check out the paper。 Okay'， it's very， it's an impressive construction。

What I do want to talk about is the positive result。Which is that on the other hand。

Nature really does save the day， perturbation really does save the day。

Which is that local search under the trueop neighborhood has polynomial smooth complexity。

So even if you start from one of these exponential worst case examples， you perturb it slightly。

 local search runs fast。 So recall from Wednesday that what it means to have polynomial smooth complexity is your running time is polynomial。

 not just in the input size N， but also in one over sigma where sigma is the parameter controlling the size of the perturbation。

 Okay so like for a Gaussian， that was like the standard deviation。 Of course。

 there needs to be some dependence on the size of the perturbation because as the perturbation goes to0。

 we know the running time might go up to exponential。

 So polynomial in one over the perturbation size is what we're looking for。 So that's what I want to。

Prove to you in this lecture。In what sense the right answer， certainly not。Certainly not。

 It n't be hard。So that would be surprising。嗯。So yeah， I'll discuss a little bit more about the。

Let me just say it now， actually。There's a couple of disconnects between the theory and the practice of local search。

One is with respect to the running time。And that's the one that we're addressing in this lecture and that's the one that smooth analysis is appropriate for that disconnect is between just the number of iterations observed when you run it。

 the difference between exponential in the worst case and subcodratic in practice and so we're not going to get subcadratic。

 but we'll at least get polynomial and so we get a lot closer to explaining what the real performance of local search is。

The other disconnect is real， but I think it's a little less embarrassing for a couple reasons。

 but it's also harder to close。 It's also harder to know how to actually close that gap。

 which is the extent to which the local minima。Wwhichch is where a local search algorithm is going to stop。

 I mean if it gets lucky and reaches a globally minimum tour。

 of course it will stop because there's no way to improve it but certainly and maybe I'll put an example on the homework。

 you can have tours which are locally optimal say for the two out neighborhood。

 meaning any one of these swaps will only make you worse off。

 but if you could somehow do a much more complicated switch around of the points you would get a better tour so simplex is very unusual and the simplex for linear programming is sort of doing local optimization each time but because everything's linear and convex。

 it turns out the only local minima are the global minima for discrete optimization problems。

 especially Np hard ones， but even most ones， it's not the case the local minima is generally coincide with global minima。

 they're almost always different。 there's usually many more local minima than there are global then there are global mini So you might get stuck at something which is suboptimal of course for an Np hard problem and a simple algorithm we're not surprised we kind of always expect that if we don't work very hard for here。

ickFor any of problem。So you get asked the question， like we've asked at other points in this class。

 can you say anything about how close to an optimal solution is the locally optimal solution that you reach？

Depends on the problem。 For some problems， you can say， regionally interesting things。

For the traveling salesman problem， in theory。You don't do so well。 So the local minima。

 in the worst case， can be very far from global Minma， even in quite simple TSP instances。

Depends on the assumptions， so under the assumptions for today， you can prove some kinds of bounds。

So you can prove some constant bound， sufficiently big bound。

 where the constant also depends on the perturbation size， but the constant bound， again。

 is very far from what youd preserve in practice， right So maybe this would prove a factor of 5 and in practice。

 it would normally be 10% or something like this。So it's not that you can't prove anything。

 but there's a big gap between what's true in the worst case and what's observed for the empirical performance of of local search algorithms。

Now， here's a couple of reasons why。 Okay， so there's two reasons， I think why。

It's less a little less embarrassing， the this between theory and practice。One is， it's just。

 the gap isn't quite so ridiculous。 Okay， it's still a big gap， but it's not as big as this。

 you know，2 to the n versus less than n squared gap。 The second reason is that， you know。

If you talk about empirical performance of local search， when you talk about a number of iterations。

 like you know， there'll be people who do local search for a living and go to the grave without ever seeing this happen once in their lifetime。

 I mean， this is really， really rare。But if you run local search algorithms enough。

 you'll definitely see some cases where they terminate at a really stupid， locally optimal solution。

 I mean it's not。Super common。 But you， like， say one，' say 1% of the time for concreteness。

 You're going to see really crappy outputs。 So it can happen， right So the theory is。

 the theory is talking about something which does sort of exist， even in the real world。Now。

 the main reason it's so hard to close the gap between the theory and the Okay so anyone who runs local search。

 what you do is you don't just run at once and go to the bank right you run it like you know these things take know they often take like 10 seconds to run so run it 100 times with random starting points okay and take the best one and then you're usually going to be reasonably fun okay。

So the question then is sort of how to turn that into a theorem。

 Like you want to say the best of 100 runs of local search with random starting points is pretty good。

 Okay， and that's a little intimidating， actually， because there can be they can be a huge number of local minima。

 It can be an exponential number of them。 It's very hard to understand sort of what the structure is。

 if you take a uniform distribution over starting points。

 no one has any understanding of what the distribution looks like over the local minima you might reach So to prove a theorem which somehow says on average over the local minima。

 whatever that means， then you're doing close to optimal， don't get me wrong。

 if anyone formulated and prove such a theorem， it would be fantastic。

 but it's challenging it would be a great， great result。

 So it's sort of the ga that's sort of been thrown there。😊，So I'd say。

 so the two good news is the gap isn't as big as far as solution quality plus。You know。

 I think we should feel it's not。 It doesn't really feel like we're just lacking imagination in our analysis frameworks。

 It really kind of feels like， oh， this is it does well in practice for sort of complicated。

 messy reasons。 And it doesn't surprise me that it's allluded all of our theoretical framework so far。

That's kind of my opinion。Okay， so end of digression， rest of the lecture， running time only okay。

 we're going to punt on solution quality， at least let's get good running time bound。O。So actually。

 what I want to do first is I want to reformulate the perturbation model a little bit in a nice way。

 So this is going to be actually a very nice notion。Of smooth inputs。So previously。

 we were talking about it， like an adversary goes first and the nature perturbbs it。

 we're going to actually smooush those two steps into one。Okay。

So the adversary is not going to pick a single input。

 We're going to force the adversary to pick distributions。

 And then there's not going to be any nature， okay。Now， you should ask， well。

 but what prevents the adversary from picking a distribution。

 which is a point mass on a worst case input。 Well it's going to prevent it is we don't let it。

 We're going to insist that the distributions can't be too spiky。

 They have to be sufficiently diffuse。So。Adversary picks。Not too spiky。

Density functions on the UviI square。With the understanding that the point P is going to be drawn from Fi。

 different points being drawn independently。And。All， so on unit square。

And what do I mean by not too spiky？So what I mean is that if you look at the density of any of these densities at any point in the square。

 this is bounded above。Byu one over sigma。Okay。So was an upper bound in the density。我喜吗。

Sigma is a parameter。And so sigma is measuring the size of the perturbation。So as sigma goes to zero。

 this upper bound becomes trivial， which allows the adversary to just deterministically pick a point。

 okay？Now， so as Sigma goes the other direction， we approach average case analysis intuitively。

 And if you think about it， okay， so like， so Sigma is not going to go any lower then it's not going to get any bigger。

 excuse me， than one。the only way this could be one is if F is the uniform distribution on the square。

Okay。More generally。What this does。 and this is maybe。A way， I encourage you to think about this。

As this forces the support。Of a density， F I。To have area just in the usual， you know。

 the big measure sense。At least sigma。Okay。And this will hold with the quality， if and only if。

This density is only the distribution is uniform over its support。

 Okay So if you're uniform on a support of area sigma， then F is equal to one over sigma everywhere。

So the smaller the sigma， the smaller the area you can concentrate the distribution on。

We want to show that this conforms to our other definition of smooth analysis。 Well， so let's see。

 at the moment， I'm proposing this as a different model or as another definition。So。

What's nice about this， I mean， so what we talked about last time。

 so for the linear programming results， it was really about Gaussians， so a drawback of that。

 a drawback of the linear programming results that we have is we only know to prove them for Gaussians。

 and then it's clear what Sigma should be， it's the standard deviation of distribution。

So that actually motivates the question， you know， can we have， can we handle lots of distributions。

 okay， perturbations， right， so why this obsession with Gaussians， Yes。

 if you had to pick just one that'd be a good one， but we really like to have it， we'd like to say。

 you know any reasonable perturbation works。And so then you have to have some way of parameterizing arbitrary reasonable distributions and what does every distribution have？

Pretty much， pretty much every reasonable distribution has a density。

 So why not some parameter on the density and， you know， densities。You know。

So sort of saying they're always， at most something is a very natural way to say they're not too spiky。

 they're not too close to a worst case input。Certainly， if you want。

 you could take as a special case， F I to be a point plus a Gaussian or truncated。

 So it stays on the square。 Okay， That's certainly one instantiation of a distribution F。 Okay。

 this says， but it could also be just uniform on some region that has， know area， at least sigma。

So in that sense， it's not again， again， because of sort of the truncation， it's not identical。

 but I encourage you to think of the previous case as a special case of this。

 even though strictly speaking， it's not quite true。Other questions about the perturbation model？

So our goal is to show that no matter what distributions over points， the adversary picks。

Conforming to this bound that are not too spiky。 Local search is fast。

 organ fast is going to mean polynomial。 expect the number of iterations in N and in one over sigma。

Questions。All right。And。it's a area one square right。

 so if you have a big thing going to be like eight so that stuff couldn't be you had limitedating by18。

 wouldn't that mean that you have to spread out over an area of eight which is bigger than the square？

Let's。Let's see。 Yeah， So sigma， you should think of sigma here。Let's see。

 do I have something flipped？Should say。1 over sigma is， this goes to zero。U。

Sigma equal 18 that think is what you're thinking of。okay， I mean， so， I mean。

 I guess minimum of this and。And。Yeah， right。 So how would you， at least to integrate to one， right。

 It's a density， right。So if this is every， did you say sigma equal 8 a sigma equal 18 I said sigma equals 8 because then that probability be less than18 Yeah。

 so there's no density on the unit square， which is everywhere at most18。

I guess would be my response。Yeah， so the。Right， so sigma is never going to go above one。Okay。

 so Sigma is going to be。Between 0 and 1。And we want to be poly in one over sigma。Yeah。

Other questions。All right。So the proof plan is very clean， okay。

 so the rest of this lecture is devoted to a proof of the second part of this theorem。And。

For the proof plan， it's going to fulfill a promise that I made to you long ago when we were talking about。

Prammerize analysis。And its various motivations。So then we're going to bust down parameter analysis again。

So what we're to do is we're going to just you， for any input。

We're going to have a parameterized upper bound in the number of iterations of local search in terms of some condition number in terms of some parameter。

 and that's actually going to be easy。Pm。So in terms of a condition number。

And then the second step is， we're going to say that。

 So only then in the second step do we use the fact that we're doing smooth analysis。 And we say。

 well， because there's this perturbation， the value of the condition number has to be fairly reasonable。

 Okay It's not going to be some super nasty version of the condition number。It's a smooth instance。

We're going to show implies。The parameter we identified in part one。Is not too bad。我看。

So that's the point。And so part one， usually for smooth analyses is fairly easy。

 We talked about this at the end of Wednesday。 So in terms of the angle of the polygon。

 after we project the highdial polytope under the plane。

 what we said was that what spman andtang really prove is that every angle is bounded away from pi and so that bound away from pi can be thought of the condition number。

 given that it was very easy to have this iteration bound of two pi over that delta。

 we're gonna have something similar here， so unlike some of our work in the first couple weeks。

 this is going to be usually be easy， sometimes understanding in these pertrbbed instances。

 what's the distribution of this condition number， that can be a technically very challenging problem。

 It's not too bad today。 Fortunately， but for some applications it can be quite serious。Okay， so。

As a thought experiment， let's think about the ramifications when you do a swap like this。 Okay。

 So one of your standard swaps in two up。So suppose you swap like in the picture。

You used to have the edges UVv and X Y。And now you replace them with U Y。And Vx。

So this yields to decrease。In tour length。So an objective function value。Of。

And here's an expression we're gonna have to kind of be obsessed with for a lot of lecture。

So I phrase it as the decrease， okay。So the two edges that we delete。

Those contribute to a positive decrease。Remember， we're using the one norm here and the two edges。

That we stick in contribute to negative decrease。so it is going to be star。Okay。And basically， oh。

 yeah。 And so one thing that's very special about this particular local search application。

 which is why the main reason I can teach this whole thing in one lecture。

Is the implications of doing a particular swap？IE the change in the objective function value is totally independent of what's going on in the rest of the tour。

Okay， I could care less which points you're going through and what over here。

 same thing here doesn't matter， these contribute the same to the tour before and after。

And these distances are independent of what's up with the rest of the tour。So at the end。

 when I talk about challenges and other problems， that'll be a property that breaks down。

 okay that's a really nice property right here。Okay。

 so very simple expression depends only on the four points U V X， Y。

 How does the objective function change when you do this particular swap。All right。

Now which swaps are bad？So bad swaps for our purposes， if we're rooting for local search to be quick。

A bad swap， you might think it's one that increases the objective， but actually no。

 swaps that increase the objective are never going to fool us into taking them。

What we're really nervous about is swaps which decrease the objective。

So they're eligible to be taken in local search， but that just barely decrease it at all。

 make essentially no progress。So call a swap。Epsilon， bad。If star。So， this quantity。

Is in zero epsilon。Okay。So remember， this is the decrease in objective function value。

So this thing being positive is equivalent to it being an improving move， Allright。

So a bad swap is one that improves the objective， stars strictly bigger than zero。

 but by less than epsilon。So implicit in this analysis is a condition number。

Which is equal to the minimum epsilon such that a bad epsilon swap exists。So basically。

 we're thinking of an ill behaved instance is one where there exists。

 these improving local moves that make just very tiny progress。Now， if there are no local moves。That。

Make very little progress。 If all local moves make rapid progress。

 then presumably we can only take a few of them before terminating。Okay。

 because we just improve the objective function so aggressively。 right。

 So let's prove a more general version of that statement。So here's， let me。

This keylemma is going to be what we have to work a little bit to prove。 So let me state this。

 And so to give you some intuition， then I'll show you how this implies the theorem。

 and then we'll finally go and prove this thing。So here's the key lemma。For all epsilon。

Greater than zero。The probability here is with respect to the input。 so remember we're talking。

 we're really doing an average case analysis sort of， at least for a fixed choice by the adversary。

 we're doing average case analysis， so the points are drawn at random。

The probability over the points over the input。That there exists。An epsilon bad swap。Is at most。

Epsilon over Sigma and the fourth。Okay。So。Ignore the don't focus on the end of the fourth at the moment。

So again， this probability is over the randomness and the input。

The only thing we're really concerned about this right now is this is polynomial that's eventually going to be good for us that'll go into iteration bound。

One over sigma。 So remember one over sigma controls how spiky the distribution can be。

So that's one of our sigmas our upper bound on densities。

 And so this is just saying the more and more spiky the distributions can get。

 the probability of a bad swap gets higher and higher and higher。That's okay。

And the epsilon is the same thing as this parameter。 Okay， so the smaller the epsilon。

 the less likely you're going to have a swap that's quite that bad。

So the right hand size would all look pretty reasonable。Now。As far as you know。

 how to think about this and why maybe we'd hope it would be true。

 although proving it takes a little bit of work。So， you know。

 it might help to think instead of this perturbation model。

 think about the old perturbation model where an adversary picks a worst case input。

 And then nature kind of just like flicks each point a little bit。That's really what we're doing。

So suppose you're the adversary and you know that that's what's going to happen。 Okay。

 your points are going to get flipped slightly。And you're really。

 you're trying to create an epsilon bad swap， this swap that， decreases things， but only by。

 less than epsilon。What seems like a smart strategy for the adversary is you kind of pick your initial points。

So that you have one or many swaps where if there were no perturbation， this would be a bad swap。

I guess remember， you create the initial set of points？

You can basically make these swaps be whatever you want。RightSo in particular。

 there is that exponential lower bound instance。 right So as the adversary。

 you could pick the points so that with no perturbation。

 local search would take an exponential exponential number of iterations。 Certainly。

 in that instance， if you think about it， there's got to be a lot of really， really bad swaps。 right。

 If local search takes so long to terminate okay。😊，So as an anniversary。

 what you kind of want to do initially is you want to set it up so that you。

 you have all these swaps where for a really small epsilon， you know。

 the swap improvements like epsilon over  two or something like that。Now， the worry is， you know。

 things get perturbed right afterwards。 So if your swap used to be kind of right in the bad regime the bad interval。

 epsilon over 2， and then these points all get jiggggerered slightly。

There's some chance that either it'll be no longer improving at all， or it'll improve。

 it improve a lot。 It'll improve more than epsilon。Okay，And intuitively， you know。

 if you're perturbing things by some density bounded above by one over sigma， that kind of， you know。

 is sort of a amount of force behind the the fls。 And you might expect there to be some kind of epsilon over sigma showing up actually。

 because somehow that's sort of the diffusion， which is happening in the perturbations。All right。

So that's kind of one way to think about this， like imagine the adversary first set up the points so that this was actually true。

 and then that's kind of like the worst case for the nature's perturbation。

 but then you know because you have this max1 over sigma density。

 there's still only a chance of like epsilon over sigma that it's going to stay in that bad regime。

Okay， so。Let me now show you why if we can prove the key Lemo we're done。

It seems like epsilon have to be。End to the negative four or something， otherwise that probably。

Just always。has to be very。Yeah， okay。 So all right。 So maybe， maybe this would help if I make。

 let me jump ahead a little bit and point something out。 So the points are in the square， right，0，1。

 right。So。And the tor has n edges。So every edge is in the unit square。

 so every edge has constant length at most。So even the worst tour has linked O of N。

In the worst case。And there's going to be a least zero。

So if in every single iteration of local search， you make progress like additive progress。

 at least one over end of the 10th。Then in at most end of the 11th iterations， you're going to stop。

Now that's not a polynomial you're going to brag anybody about， but it's a polynomial bound。

 and it is I mean it really is exponential in the worst case。

 so you're really getting fundamentally different effects， even if you could prove that。

So you're absolutely right， in other words， we want to be thinking of epsilon is very small。

So if epsilon is already as big as inverse polynomial， we'll take it。Good point。

 So I think more epsilon is more like， you know。One over two to the root end or something like that。

 That's what we're really scared of。Yeah， and again， right， for this bad， you know。

 if you don't have the perturbation， if you just take this worst case exponential instance。

 exponential number iteration instance， the average swap has a epsilon inverse exponential。Right。

Because again， you're going from like n to zero。 It took you in exponential re iterations。

 So the average improvement is n over2 to the n。Zg。So in that sense。

 proving that if we could prove that this probability totally went away。

 once epsilon dropped below one over end of the  ten0。

 we'd show that the perturbations create destroy all of the bad examples。

It we'll prove sort of a smooth version of that statement。Okay。Any more questions？Yeah can。

More parties swap that isn't an。That doesn't include。Sa again。Well。

 we couldn't so if we don't find any nodes or any edges that we can swap。Then have we converge。

By definition， so any local search algorithm you specify the neighborhood。

 that's a design decision you make at the beginning of right right exactly right so this goes back to our discussion about this other gap being between how good is the locally optimal solution versus the global optimal solution。

And in some sense， So when you actually， so when I teach。

 you know how do you actually design local search heuristics in 161。

 So one of the main things I talk about is know this tradeoff between the richer your neighborhood。

 the more time you have to take to search it by their hands， hopefully know。

 local minima will be closer to global minima。 if you have a richer neighborhood。 I mean。

 the extreme neighborhood is every single feasible solution is in your neighborhood。

 And that by definition then turns every local minimum in a global minimum， of course。

 now it's not a heuristic。 you haven't done。So true opt is a very is a relatively small neighborhood as TSP goes。

 and certainly if you're trying to do TSP in practice。

 one does experiment with richer local neighborhoods in order to get closer to the global opt。But。

For the analysis， today， we're just going to focus on the simplest version of the two opt case。

 which， you know， this already itself is used。's not like this is not useful。

 This is this is also useful。Okay。So。Suppose we prove of the klema， why are we done？Here we are。

 here we are。So we already observed that the worst the initial tour could be is total length2 in。

And most， if you think about it in in the L1 norm， each edge has it most2。 so2 n can be the worst。

0 obviously is the best。So we have no epsilon dad swaps。

And this is sort of our very easy parameter analysis。Then， local search。Termininates。And at most。

To an over epsilon iteration。Good。If there' is no epsilon bad swaps。

 every swap that improves improves by epsilon， you start a 2 N， you go to 0。 So that's it， O。

So we're golden if epsilon is inverse poly？All right。

Let's figure out how long it's going to take now。Assuming we've proved the key limit。And again。

 because each iteration can be implemented in polynomial time。

 this just boils down to analyzing the expected and reiterations。

 So we want to prove this is polynomial in n in one of sigma。So first。

 just by the definition of expectation。We sum over all of the values。

That I'm going to use capital M as the random variable denoting the number of iterations。

 which is random again over the input。And actually， let me rewrite this。

 So M is a non negative integervalued variable。 So another way I can write this sum。

Is I just sum up all of the probabilities that the random variable is at least something。Okay。

So the only thing I'm using here now is that the random variables not negative and image are valued。

Some of you， I'm sure have seen this before， if you've never seen it or you forgot it。

 the best thing to do is just stare at it for 60 seconds。

 and then you'll realize its once you see it， you'll be like， oh， yes， that's obvious。嗯。Oh no， no。

 no， no， don't do that。Okay。All right， so now why did I rewrite it this way， I rewroite it this way。

Because the only way that the number of iterations can exceed M is if we have a pretty bad swap Okay。

 with epsilon equal to2 n over M。All，That's this， that's by this。 So if every swap。

 if there was no bad swap with parameter value to n over capital M。

 then we're certainly not going to require M or mores， right。

So a necessary condition for this and therefore an only bigger probability。

Is to sum up the probabilities of。Cad swaps。 So there exists。A2 n over M。Bad swap。Okay。Right。

So now we use the key limitma。Right， so we're invoking the klemma with epsilon equal to 2 n over M over capital M。

 Allright， So the little n on the top， willll just sort of add that to the exponent。

 That'll become an end of the fifth。The epsilon goes away。 There's a sigma on the bottom。

 There's an M on the bottom。But。It' keylema。So let's pull out everything that doesn't depend on capital M。

 name end to the fifth over sigma。Some and at least one。1 over m。好的。Now， at first。

 this kind of looks like a bummer because this thing diverges， right？On the other hand， like。

 how big could M be， if you thought about it， we actually discussed in passing of finite upper bound on capital M。

How many iterations could local search take to termminate， Could it really take infinite。

 to take forever and ever and ever。No， it strictly improves the objective function value。

 and there's only n factorial tours，So。We only need to sum this thing up the end factorial。Okay。

So this is well approximated by the natural logarithm， right， the harmonic sum。

So natural log event factorial， which if you like Sterling's approximation。Data n log n。

Giving us an upper bound of sigma to the minus1。End to the sixth login。

So that's why if we prove the klemma， then we're done。

It's just proving a sufficiently rapidly decreasing probability bound on the probability of a bad swa。

So any questions？Okay， so a couple of comments before we started in the killema。

 one can improve the upper bound and actually the same angr at all paper。

Do prove a bound where this end of the six becomes end of the fourth。The way they do that。

 they use the exact same kind of high level framework， they prove an upgraded version of the keylema。

 and what they do is rather than considering single swaps， they consider pairs of swaps。

So the keym is basically saying。You know， if you just take an arbitrary such swap。

 it lower bounds the progress you'll make with one swap。So instead。

 they prove a keying where they say， well， look at two ss on a row， One of them might be bad。

 but one of the two will be good。And if you think about it。

 that gives you exactly the same iteration bound up to a factor of two。

 so they prove a better lower bound on the rate of progress you make。

 if you break the iterations into payers。You do have to work a lot harder to prove that。

 I have to say， so but with a lot more work we can get this time to end of the fourth。

There's still a gap between that and the fourth and what seems to be the empirical performance。

 which is more like n squared or even a little bit better。

 But this just this seems to be the deal with smooth analysis。 Okay。

 so it does let you turn exponentials into polynomials， but it just seems to get tight bounds。

 The amount of analytical work required is just overhel it。 Okay。

 so it really just doesn't seem like a framework that allows us to nail the exponent of the polynomial。

Okay。But we're here to。Celebrate at its good points。Not complain。All right。

 so on to the proof of the key limitma。Unless there's any questions before that。All right。

 so consider a fixed swap。So how many different kinds of swaps。

 how many different swaps do we have to consider？So a swap is like this。

So how many free parameters do we have in star here？It is4。Yeah。So we have。Degrees of freedom for U。

 VX and Y。Okay， so that gives us end to the fourth possible swaps we have to consider。 Again。

 very happily， star is independent about what's going on with the rest of the points。

So consider a fixed swap。We're going to show that the probability。For this fixed swap。

 that star is in。Zero epsilon。Is big O of epsilon over sigma。好看。Having done this。

 we can apply the union bound over the end of the fourth different swaps。

 and that gives us the claimss bound。Okay， so that's really nice。 It Just boils down analyzing one s。

 That's what makes this。A nice analysis。So end the fourth swaps。done byい年だ啊。Okay。Now。

Let me expand this。Let's see1 minus v1。Plus x1 minus y1。So in terms of the coordinates。

So we have these four absolute values from the first coordinate。Plus。

 exactly the same thing with all of the subscript ones replaced by subscript twos。 Okay。

 So this is what we're trying to analyze right So the keym is all about trying to get a handle on the distribution of this number。

Now the reason I've expanded out the norms is because I'm just trying to like。

 so we'll be able to do this， it'll be pretty straightforward。

 but the one thing which is kind of annoying and forces us to work a little bit harder than we might otherwise is all these absolute values。

Okay， so if we pick some other norm， there'd be some other irritation。 like the Euclidean norm。

 We'd have some square root and some squares， right， So we'd deal with it。

 There'd be some other way of dealing with it， But it's something we got to deal with， okay。

So we have these absolute values。So I guess now I can erase this。

So here's the way we're going to deal with this， okay？So let's say trick。啊。

So you want to say this thing is only between 0 and epsilon with a low probability。We going say。

 well， it should be a lot easier to deal with if we knew。

Which of these coordinates was bigger than the other one。 right， So right now。

 this is either U1 minus v1 or v1 minus U1， And it depends on which of them is bigger。 Okay。

 so let's sort of just guess the sign of each of these absolute values， okay。Here's what I mean。

So for a fixed ordering。Of。The four values in the。First coordinate。Okay， so in ordering。

 I just mean which of these is biggest， second biggest， third biggest， fourth biggest。 Okay。

 so there's four factorial choices for orderings。 I guess I'm ignoring ties。

 That would be a few more four factorial choices here。 Okay。

 so four factorial squared choices I'm making。Now， once you tell me which of these is bigger than the other？

This expression simplifies， This expression is then just some linear combination in。

These eight values。Right。So once I fix the ordering。

 each of these absolute values either it just becomes a times 1 or a times minus1。

So just get this linear combination in terms of these eight variables。Also。

 because all coefficients in these terms are one， when I look at the linear combination that I get。

 every coefficient of a variable is an integer， possibly zero， but it's an integer。

 so I'm going to get either like two times U1。Or minus2 times u1， or maybe zero times u1。Yeah。

All right。So the expression star， the thing that we want to show。

 is very unlikely to be between0 and epsilon。Once we've made these four factorial square choices。

Boils down to a linear combination。Of eight variables。With integer coefficients。Okay。

And now here's a sort of trivial， but also sort of subtle points。

So the expression that we care about。 the sum of all of these absolute values of differences。

This lies in the interval， zero epsilon。Only if。1。Of these 24 squared。Linear combos。Okay。

L in zero epsilon。Okay。So let me make sure it's clear what I'm doing。This is star。

 This is the only number we actually care about。If you substitute values for the eight variables。

 you get a real number。so for some instantiations of those eight variables。

 youre to get something between zero and epsilon， for some， you won't。On this board。

 so this is just one expression。On this board。I've written more like ballpark，5000 expressions。

24 squared。500 expressions。Yeah。500 expressions，No matter what。The value on the left board。

Is equal to at least one of the 500 expressions on this board。 O。

 Which one depends on the relative ordering of all of these pairs。

But I've written out these 500 expressions that have covered every single case of what this thing might evaluate to。

 okay。So if I instantiate these eight variables so that this and this thing winds up being between 0 and epsilon。

And I look at these 500 instantis with those exact same variable values。

 One of those is between0 and epsilon。 in particular， the one of these， which is equal to this one。

Right。Why am I doing this rather than upper bounding the probability that this thing is between zero and epsilon。

 Why don't I instead just upper bound the probability that any one of these 500 things is between0 and epsilon。

O， that's a loser condition。 I get an upper bound on the probability。Its clear what I'm doing。Okay。

 it's kind of a hack， frankly，But we can get away with it because， you know，500s are constant，I mean。

 there are ser ways you could do this if you want。 But， you know， just as far as convincing yourself。

 all this stuff is true， this is probably the hideious way to do it。

So any questions about that about this note？A necessary condition for this thing to be bad。

 for this thing to be between 0 and epsilon is that one of these 500 combinations。

 one of these 500 linear combinations is between0 and epsilon， necessary condition。Good， so claim。

So pick your favorite linear combination in the middle board。

We'll just take a union down over all 500 of them。The probability that' linear your combo of your choosing。

Is between zero and epsilon。Is the most sigma over Delta。Okay。

And so then the union bound gives us a 500 time sigma over Delta， which is kosher by this claim。

So why is this true， Pro the claim。Well， we can certainly assume that one of the coefficients is nonze。

Okay， so again， remember， linear combination in 8 variables， U1， V1， X1， Y1， U2 V2， X2， Y2。 Okay。

 that's what' slinndered。 So's those eight variables， each with a coefficient。

If all those coefficients are0， then this linear combination is always zero。

 So it's not going to be strictly between0 and epsilon。

So we can assume one of the coefficients is not zero。All right。

So now use the principle of deferred decisions。Oh， yeah。 So let's say Z。Okay。

 so Z is one of these eight variables that has a nonze coefficient。

So now we use the principle of deferred decisions。So we're going to prove it even stronger statement that this probability is the most epsilent over sigma。

 actually no matter how you condition on the values of the other the seven variables。

So condition on the values。Of all。Other。7even variables。Okay， so don't forget what's random。

 I can't remember， the adversary has supplied these distributions from which the values of these8 variables are drawn。

 So I'm saying， draw them for the 7 other than Z。 Z remains random。Okay。

Maybe it'll also help to just remember like， what are we trying。

 What's the intuition for what we're trying to prove。

 Think of this adversary who initially picked this really bad instance。 And now nature's flicking it。

 Okay， Basically， what I'm saying here is， you know。

 even if I just get the flick of one of the points。

 that's good enough to prove that your devious swap you had in mind is actually either gonna to not be improving or improve more than epsilon。

 so only Z remains being random。 That's going to be enough。Alright。

 so condition on values of all other7 variables， good。Now。So。Yeah。So since the coefficient。Of Z。

All right， let's put it this way。 Okay so residual expression。After conditioning。Has the form？

Lambda for some number， some real number plus。Alpha times Z。We're alpha here。Is an integer？

And not equal is zero。Okay， remember， the only thing that remains that's random is Z。

 The other seven variables have been have been instantiated。 So we just have something like you know。

5 plus  two times Z。So and we're worried about what's the probability this thing lies in the interval of0 epsilon。

好的。Well， intuitively， the worst case is where the value of lambda is like epsilon over  two。

so even before we instantiate Z， it's sort of like centered right in the bad interval。

But the other hand， we know that Z， by assumption， comes from a pretty diffuse distribution。

 The densities at most one over sigma everywhere。Okay， so in other words。

 in an area of like merely epsilon， you can only fit in。A small amount of density。

It just can't be that likely it's going to be in this very tiny region because it's not too spiky。

Now， the only worry would be that， okay， well， maybe you， Z is really diffuse。

 but then maybe alpha is concentrating it。 but Al is an integer。So it has magnitude at least one。

 So it's actually only spreading Z even more diffusely。so Al Z is only less spiky than Z。

Because Alph is an integer。So you put all that together。So density。Of Z。

Is it most one over sigma everywhere？So probability that lambda plus alpha z is in zero epsilon。

Is it most the length of the interval over？D time is the density of bound in one over sigma。Okay。

 thiss all around to proof。Okay。And this is also， I mean， this is。

 this is a simple but still very characteristic type of smooth analysis， the sort of mixture。

 sort of principle of deferred decisions， and then still having residual randomness。

 which is just sufficient to prove that some condition number is large。

 many of them have this flavor， okay。And I like this proof in particular because I think those ingredients shine through in the most transparent way。

Any questions？Yeah， so it seems like。A more aggressive。

Of that probability would be one way to eliminate。什么。

The slack between theory of which probability sort of。The probability that one you just showed here。

 which part of it Well， I guess the claim or the factor 500 or yeah。

 like the deferred decisions sort of this blow up yeah。True。

 but let me point out that so all of the blow up we're suffering here is suppressed by the big notation anyways。

 right， So， I mean， so the real upper bound is， you know， something like 500 times end to the  sixth。

 you know， whereas the practical performance might be， you know， one times N to the 1。5。

So you might be able to bring down the leading coefficient。

 but none of this will help you bring down the exponent。 And even with a lot of hard work。

 people don't know how to get past end the fourth。 So getting into the fourth end of the third。

 you know， I mean， it may be as simple as something you know。

 as conceptually simple as something as looking at not just pairs of swaps。

 but even longer chains of swaps。 But pairs of swaps are already know。

 a real challenge to understand， know how to leverage those to get you a better of a bound。 So。

You know， my belief would be it is probably possible in principle to prove a smooth analysis bound。

 which you know， starts approaching you know what people see in practice， Maybe not exactly。

 but I do believe you could beat into the fourth， for example。

 but it's not clear that the amount of work it would require。

Is justified really for anybody to do So specifically about the end of the fourth ss。 Yeah。

 why are we getting that when we only have like we have end edges that we have to choose from right so good question。

 So if I give you a tour if you have a tour that you're working with。

And you know that the swap the swap you're going to take right now is neighboring one of this tour。

 Then you're right。 Then it's only n choose two edges。 So that's n squared。

 So from any given tour there n squared directions you could go。

 But if you think about every tour you might find yourself in at some part of local search。 Now。

 all of a sudden， the number of different swaps you might see are literally the number of edges in the entire graph N squared。

 choose2。So that's the difference and this is a bound over the entire algorithms。Yeah。

 because you don't know where it starts， you don't know where it's ever going to be， I mean。

 literally every swap might have an opportunity to be executed at some point in local search。

 it seems very hard to operate or rule out any particular swap coming up Yeah thanks。

Any other questions？Yep。I can see how the lambda。Epathy holds for。

Specific variable that is not equal to zero， right？Why doesnt。Doesn't need to hold fiery。

 So the sneaky thing that I did is I。I first， intuitively。

 I let you choose the linear combination first。Then I look at which variable has a nonze coefficient。

If none of them have a nonzero coefficient， I'm done。Okay。

 but then you picked the linear combination， I picked the thing with a non zero coefficient。

And now I use that to decide how to apply the principle of deferred decisions。

And I'm going to condition i。e substitute values for。

Seven of the variables other than the one that has a nonze coefficient。

So I'm basically adaptively picking which seven variables， right。

 So I'm adaptively picking which variable to save for the last based on the linear combination。So。

In fact， I had a bug in an earlier version of this lecture because missing that subtlety。

 so it's sort of a subtle point。So you visit you adaptively applied to principle deferred decisions differently for different linear combinations。

But for any linear in combination， there's one that works。 and that's all we need。Other questions。

Okay。Then， yeah， one of the comments。 So one thing I'll ask you to do on homework is notice that know all this stuff goes through。

 even if you're not in the plane。 Okay you have points in a higher dimensional space。

 but say with a constant dimensional space，3 space，4 space， whatever。

 you can push all this analysis through when you still get the exact same iteration count。

 the dependence on D shows up only in the suppressed constant in the big notation。

 And as I said earlier， and these I won't make you do。

 but you can do similar results for Euclidean norm and other norms， if you want。

 Okay so I presented the easiest one to present， but the results are really are more general。Okay。So。

 let me。Conclude with just some opening questions and speculations。Because， I mean。

 if you think about what are the ingredients that seem to make。You know。

 problems well suited to local search to smooth analysis。 Local search just ticks all the boxes。

 you know， you have these brittle， exponential， lower bounds。 you know。

 it's about essentially about running time and so on。 We have successes like this。

 but there's a lot of local search documents that we don't know whether or not they have smooth complexity or not。

Okay。All right， so the first thing would be just to identify， right。

 So people use local search for all kinds of different computational problems。

 And at least for sort of the most fundamental ones。

 it would be nice to show that local search has polynoml smooth complexity。Okay。

 so let's just say more。Poly smoothed bounds。For local search。So there are a few others。

 I don't want to give you the sense that TSP is the only one people have done successfully。

 there's other examples as well， Ka Mes is one where they actually done by graduate students here at Stanford last decade。

 or at least the initial results were David Arthur and Sergei Vasselvisky。

So that's a really nice example of an actually pretty hard local search algorithm that was proven to have smooth polynomial time。

As a challenge problem。Let me mention Max cut。So this is the problem where you're given an undirected graph with edge weights and you want to split it into two parts maximizing the weight of the edges crossing the cut so unlike minimum cut。

 which is polym time sallvable， maximum cut is NP hard and local search is one way you can approach it。

On the homework， I'll ask you to show that if the graph has bounded degree so all degrees are most constant。

 then in fact， local search， oh right， I should say with the local search algorithm is here it's really simple。

You just check if moving a vertex from A to B helps， similarly from B to A， if any of these flips。

 it's called the flip neighborhood， if any single vertex move improves the objective increases the way of the crossing edges。

 do it， stop when there's no more such moves。So I'll ask you to prove that that local search algorithm has polynomial smooth complexity in boundary degree graphs。

 okay。The analysis of that has much of the same flavor of this TSP analysis， I would say。嗯。Again。

 sort of the moral reason why we know how to analyze this is because like in TSP， in some sense。

 there are only an end of the four a polynomial number of different things that could happen and downed degree graphs。

 if you think about it in the right way， you recognize there's only a polynomial number of different relevant events as far as the different swaps that could happen。

What's open。Is general graphs。So we don't know whether or not local search has polymel smooth complexity in general graphs。

 just as of January of this year。So maybe 10 months ago or so。

 we learned that it does at least have sub exponential running time， smooth complexity。 Okay。

 so a socalled quasi polynomial time bound was proven。 that means n raised to the log n。

 Or if you prefer two to the log squared n。 Okay， that's a lot better than two to the n。

 but it's not polynomial。 It's super polynomial。Generally， you know。

 people rarely believe that a quasi polynomial bound is the right answer。

 People usually think it's either polynomial or exponential。 They're exceptions。

 but it's a rule of thumb。 So people sort of expect that the right answer there is polynomial。

 but no one knows how to prove it。So that's sort of a concrete question。

 which we don't specifically know。Frankly， I actually think much more sweeping。

 positive results should be true。So I actually think pretty much every single local search problem should have polynomial smooth complexity。

 and it's just a matter of proving it。 believe it or not there's actually a definition of pretty much all local search problems there's a complexity class called PLS。

 This is by Johnson P New Ynaocus it stands for polynomial local search and this is in some sense the analog of NP but for local search problems and I'll put a link on the website actually teach a lecture on this in my algorithmic game theory class。

 so I'll post some lecture notes if you want to read more sort of a gentle introduction to this complexity class。

And so I think everything in this， I think all these local search problems should be solvable and polynomial smooth complexity。

 I have various reasons for believing that could be wrong， of course。

 But I think it's more an issue of proving it than it being true。 I think that's more the obstacle。

There's two versions， actually of this， conjecture。 if you want to call it that。

 the stronger 1 I'm less sure about。 Okay， so the stronger statement would just say generic local search。

 as we've discussed， Okay， meaning you just， you know， follow your nose。

 if there's multiple improving moves， take any of them arbitrarily。

 that generic local searches always has smooth polynom complexity。 that would be a strong statement。

 still might be true。A weaker statement would be well。I don't know about generic local search。

 but I can at least craft some optimized smarter algorithm。

 which is guaranteed to compute a locally minimum solution and smooth polynomial time。

So I'm not going to restrict myself to the generic local search algorithm。

 I'm going to do something smarter。Now you might ask， what on earth else could you do？

Other than generic local search in a generic local search problem。

 But there are some tricks you can do。 So first of all， you can say， well。

 let's just focus on the moves that improve the most。 So not an arbitrary improving move。

 But when there are many， you could have some smart way of distinguishing between them。

 There's other tricks like you can do things like round the objective function。

 discretize the objective function sort of to smooth out some jagged edges of the search surface。

 So I don't know。 I think it might be really hard to prove。

 But I think actually that might be true It be really cool， be very sweeping positive statement。

 And two lectures。 So a week from today， I'll show you an analogous results。

 that also has the same flavor of generality， sweeping positive results。

 which says that for all problems， which emit a pseudo polynomial time algorithm。

 all of them have smooth polynomial complexity。 Again。

 like carefully crafting an algorithm to solve it。 So that's another analogy I have in mind and thinking that this might be true。

😊，Question is generic search I mean， why do we know that it converges in a general case， I mean。

 couldn't there be cycles No， because it's defined to only improve the objective function value。Okay。

 yeah， I guess。It's a great question。But so， I mean， this。

 this is sort of the subtleties of what does it mean for a problem to be in P， L。 S。

 And so some of the necessary conditions to be in P， L。

 S is you have to have an objective function value， which can be evaluated in polynomial time。

And then you also have to be operating on， you know。

 so basically the feasible solutions have to have a polynomial size description。

So there's only there's only exponential an exponential number of possible feasible solutions。

 they can't grow in length。 So this's not gonna to be an infinite number of feasible solutions。

 So by definition， if you look at the fine print of this complexity class。

 local searches guaranteed to terminate an exponential time on every single problem。Other questions。

On Wednesday， we'll talk about Pareto curves， see you then。

