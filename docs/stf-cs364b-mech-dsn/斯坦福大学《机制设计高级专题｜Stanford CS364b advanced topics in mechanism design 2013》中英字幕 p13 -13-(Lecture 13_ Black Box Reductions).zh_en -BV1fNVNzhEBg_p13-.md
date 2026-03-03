# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p13 -13-(Lecture 13_ Black Box Reductions).zh_en -BV1fNVNzhEBg_p13-

All right， so let's get started。 So let me sort of just remind you where we are。

 So last week for the first time we relaxed our incentive compatibility guarantee for weeks and weeks。

 we'd been focused just on strong guarantees like dominant strategy and compatibility Expos and compatibility last week for the first time we started talking about Bay Nash implementations。

 So the current set of goals are the following as usual。

 we want simple and polytime mechanisms as usual， we want to have welfare as close to optimal as possible。

 at least subject to polynomial time for the case of n hard welfare maximization problems。

 and we want mechanisms that are Bayesian incentive compatibleible for today or for this lecture。

 And remember what that means is that means direct revelation mechanisms should form a bayes Nash equilibrium。

 Now to talk about Bayes Nash equilibrium， there has to be a notion of a prior So basically when a agent is reasoning about whether or not direct revelation is a good idea or not。

 So what do they know they know some common prior distribution capital。

They're assuming that other bidder's valuations are drawn from that distribution。

 they know their own valuation， and there are these strategies。

 so they know the strategies that everybody are playing， so I don't know other people's valuations。

 but if I knew their valuations， then I would know their actions。Okay， so in algebra。

So what does it mean the direct revelation is a Bay as na equilibrium just means that for every bitter eye。

 whatever its valuation， VI might be。So whatever its valuation might be， then direct revelation。

 meaning just report the true value。Should maximize？It's expected utility。 And here。

 the expectation is over the random draws of the other bidders。

 When I talked about the general Bayesnash setup last week。

 I allowed the prior capital F to be correlated。 until further notice the distribution is a product distribution。

 Okay， so until further notice， bidders valuations are independent。 So I don't need a condition on V。

 When I write V minus I drawn from F minus I， so again， B IC means that direct revelation。

 Sigma V equal V I should maximize utility okay。So the UI。Okay。

 so here I'm assuming that other bidders valuations are drawn from FSI and I'm also assuming that they're doing direct revelation。

 because it' is an equilibrium concept。Maxims this over everything that Bi I could do so over all reports。

BI。Okay。So in other words， you can declare whatever you want， declare whatever B you want。

 But under the following assumptions。 first of all， the bidders valuations are drawn from F minus I。

 Second of all， the other bidders are doing direct revelation under those two assumptions。

 your utility expected utility is maximized by just direct revelation。

 Okay so that's what that's what a Bayesian se battle mechanism is。

And I don't think we didn't really talk about so we didn't really talk about concrete examples last week。

 The point of this lecture is going to be a very sweeping。

 really very satisfyingly sweeping positive result。

 basically saying whenever you can get a computationally efficient approximation algorithm。

 get you can massage it in a way that it becomes a Bayesian incentive comp mechanism so we'll get positive results that are simply impossible for the stronger notions of incentive compatibility。

So whats sort of the coolest thing that could be true？

So the Holy Gil would be that we can achieve all three goals。

Whenever we know it's possible to achieve only the last two goals。

 So whenever you have a polynomial time algorithm， which has some guarantee on the welfare。

 we'd like to basically get Bayesian instead of compatibility for free。

 And I'm going to show you how to do that in this lecture。 very cool。All right。

 so what's the sort of methodology that we'll use， What's going to be this black box reduction。

 which I。Sketched last time， so let me remind you the blueprint。Of how this works。So。

There is going to be，- we're going to be given。An algorithm A。Which achieves only2 and3。 Okay。

 so you want to think， think about a canonical case like bidders with submodular valuations。

 something like that。 That's a problem for which we know there are good approximation algorithms。

 and we totally failed to get a decent mechanism outside of the special case of coverage valuations。

 So that's a。 A is something which is not suitable for a mechanism。

 but has a good approximation ratio。And we want to design this algorithm B。

And the way we're going to do this is we're going to pre process valuations。Okay。

So the valuations will first go into initial subroutine。 These are going to be resampers。

 and so this will somehow basically resample valuations。

And feed this new valuation profile into the old algorithm。

And the algorithm will not be any of the wiser。 The algorithm will just treat these resampled valuations。

As a valuation profile， it will do its thing。And what we want is even though a is unsuitable for a big mechanism。

 B can be implemented as part of a big mechanism， okay。So the goal here is given an algorithm A。

And a prior capital F。Construct an algorithm B， which has the form first， you apply resampling。

 this is a subroutine R， then you apply A。Where are I。Its a poly time。Reampler。Okay。

 mapping valuations to valuation。嗯。So that's the high level plan。Now。

 for this to give us the sweeping positive result that we want。Basically， two things should be true。

 So first of all， the incentive failures possessed by a should go away。Secondly。

 we should inherit the approximation guarantee of a。 So what's good about A we retain。

 what's bad about A we get rid of。So primary goals。For R。So again。

 there's going to be one algorithm R I for each of the n bidders。

So R takes I's valuation and spits out a different valuation。So， first of all。The compose algorithm。

R followed by a。Is Bic implementable？All I mean here is that by big implementable。

 I just mean right So B is basically an allocation rule it takes this input evaluation profile。

 Spits out some allocation。 I just mean I can couple it with some payment rule so that that。

 you know， allocation payment rule combo is indeed a big mechanism。

 Okay so that's all I mean by big implementable。 There exists a suitable payment rule。

And then it should be welfare improving。Okay。So if I look at the expected welfare。Of algorithm B。

 so equivalently。Remember， B is just A applied to the resampled valuations。

That should be at least as good as if I didn't resample。And remember。

 sort we're motivated by the situation where a is a good algorithm okay so we're thinking of this as being very close to the maximum possible welfare。

 So maybe for every possible valuation profile， a is close to the maximum welfare。

 or at least maybe on average over the relevant distribution F。

 the expected welfare is close to optimal， and the point here is just that whatever guarantee this has then our massaged algorithm has it as well okay。

So if we can do these two things， I mean， that's great。

 that basically says this is the technical sense in which Bi will be without loss for approximation algorithm。

Okay。Good。All right。Another really important property for making this work。

Is we're going to have each resamper be distribution preserving。Okay。

 so remember a resampler R sub I， it takes we're envisioning it。

 taking the actual valuation of better I V and remapping it to some other valuation。 Okay。

 so it gets an input at random。 It remaps it。 So its output is also random。

 We would like the distribution of inputs to be exactly the same as the distribution over outputs。

 That is， we would like the output。Of the I3 sampler。To be distributed according to F subbi。

 the same distribution from which VI is drawn。Okay。

So this is another property we're going to use as sort of a guiding principle for how we're going to come up with these resampers。

 these R subs。Now， we'll kind of see in the proofs why this distribution preservation property is useful。

Let me just say about why it's why we might want it。

 in fact it's sort of hard to think about how you'd prove this result without this property。

 but so basically improving the key properties one and two。

Distribution preservation will allow properties one and2 to decouple across the bidders。So decouples。

Proof of one，2。Across bidders。And so， you know， we'll see this in more detail later。

 But just you know， roughly speaking what's going on。

 So if everybody else's distribution stays exactly the same， remember， you know。

 the big implementability condition， when a player I is reasoning about whether or not direct revelation is a good idea。

 It's only reasoning about other people and as much as we're sort of averaging over V minus I。

 Okay so if behind the scenes， there's some resampling going on。

 which leaves the distribution of what I see in variance。

 then the decision about whether or not something is the best response is also invariance stays exactly the same。

Alright，So some sense somehow， if other distribution stay exactly the same。

 it allows me to handle incentive separately for each of the bidders。

 That's the intuition for the first part for the welfare parts。 Well。

 so we want the expected welfare to only go up。 And so if all the distributions are remaining unchanged。

 then by linear of expectation， I can just handle this bidder by bidder。 that's all that matters。

's that's know we'll return to that precisely later。

 but that's the gist about why you might want this distribution preservation property。

As a tool for proving one and two， these are the two things we really care about。O。

So that's at the high level。 So now the rest of this lecture。

 I want to show you the construction of these Rs， which is pretty nice， actually okay。

So I gave you a hint at the end of last lecture last lecture I talked about the special case of single parameter settings and uniform distributions just to kind of as a warm up So today I really want to talk though about multiparameter settings we're really motivated by these commator auctions problems where we just failed to come up with good decent mechanisms so I'm really thinking about like some modular valuations as a motivating problem So that's multiparameter。

 that's not single parametera so it was really just a warm up last lecture。

So here's the general setup。So。Bittter eye。I am， however。

 going to retain the assumption from last lecture that there's an explicit set of possible valuations that's finite。

 and that's explicitly given。 Okay， and that's not that satisfying an assumption。

 but we're going to need it for today。 Okay， so a bitter eye has a finite。😊，Set T。Of possible types。

 So remember， so pretty much in this class， whenever I say type， you should just think valuation。

 Okay， so type is just the private information known to that agent that you don't know as the designer。

 Okay but think valuation。Has a finite set。Of possible types。Or evaluations。And。

You should also think about it that we're basically given as input just a list of the possible types and the probabilities of those various types Okay this is the prior so remember all of this only makes sense with respect to a prior。

 I'm assuming it's a product prior so I only need to know the marginal distributions right so the probability for each bidder with the probability of VI and that's just given as a list。

And so what you might want to think about is you might want to think about like say in some modular valuations。

 Think about some concrete crass class that we've talked about how to represent coverage valuations。

 K unit demand valuations， something like that。 So just imagine we're this we're given like a polynoial polynomial length list of succinctly represented valuations of that type。

 Okay， with some probability masses。 Okay so that's what you should think about。Okay， and then also。

 there's some just algorithm， which， again， we're thinking of as being a good approximation algorithm。

 which just maps a evaluation profile or a type profile to an allocation。Okay。Yeah。

 so these are numbers that obviously for a fixed eye， these are non negative numbers that's sum to1。

All right， and so again， think of a as either a good approximation algorithm possibly in the worst case for evaluation profile。

 or at least on average with respect to the specified prior。Now。

 I want to proceed for each bidder independently， okay。Any questions about the setup？Okay。

So here's the way I want you to think about this。What we're given is we're given an algorithm A。

 where if only people。Did direct revelation， we get great welfare。RightBy definition。

 it's a good approximation algorithm。 So if we ran it on the true input， we do well。 Okay， that's a。

 The problem is， you know， it's not it's not a big mechanism。 people aren't motivated to。

 to do direct revelation。 So let's just make a small change。 Let's stick with algorithm A。

 Let's fix a bitter I。 And let's just try to correct the incentives for bitter I。 Okay， by itself。

 so for every bit other than I， let's imagine that they do direct revelation。

 even though it might not be in their best interest。 Okay。

 so let's analyze the world from I's perspective， assuming everyone else is direct revelation。😊，可以。

Looks like something died on the board here。Okay。So first step。So fixed bid eye。And in effect。

 we're basically just assuming that all the other resampers。Orre the identity。

And everybody else is just directly revealing their information。

 even though they might not be incentivized。For J not equal to I。

And so the question is just how to incentivize direct revelation for I under these assumptions。

All right。Now， what do we have under our control。So there's two things We actually need to。Design。

 the first thing， obviously， is the resamper， the R I， but also remember。You know， ultimately。

 this algorithm B， this is just the allocation rule。 Ultimately。

 this is going to be embedded in some mechanism。 So somewhere， either implicitly or explicitly。

 we're thinking about designing a payment rule， P I as well。Okay。So the question is。

 how do we design just for I？The resampler RI and the corresponding payment will P so that its expected utility is maximized by direct revelation。

So this is something we talked about in the special case at the end of last lecture。 So again。

 the special case， I said let's just talk about single parameter settings。

 this is the end of last lecture and let's just assume the uniform distribution。

 And the reason I started us with single parameter settings is because we have a very good sense for what what's an implementable allocation rule It's just monotonity。

 We talked about that a lot last quarter for Dig mechanisms。 But as we explained last week。

 it's basically the same story for big mechanisms， single parameter。

 So an allocation rule is implementable can be turned into a big mechanism if and only if it's monotone so if and only if as you average over all the v minus I。

 the amount of stuff you get is only going up as you bid higher。 so we didn't prove it。

 but the proof is the same， but we talked about I called it the extended Myson'slemma last week monotonicity is sufficient。

 also necessary， but the point was it was sufficient for big implementability。Now。

 the whole point of today's lecture is to do things like comptourial auctions。

 which are multiparameter， which means it doesn't make sense to talk about a monotone allocation rule。

 there's multiple things you're bidding on， So what does it mean to just bid more。

 What if you bid more on one thing and less on another。So this is what's a little intimidating。

 but actually it plays out really nicely in this context。When you think about it， I mean。

 what are we trying to prove， We're trying to massage algorithm into a different algorithm。

 And then we need to argue， okay， and now， all of a sudden， it's incentive compatible。

So we need to think to ourselves like what's that part of the proof going to look like where we write down this proof and says。

 oh， now we've got it， now we've got our incentive compatible mechanism。Because again。

 we don't have Myerserson'slemma。 It's not single parameter。 Okay。

 so we need some part of the proof where we argue we've achieved the desired incentive compatibility。

Okay， so that's something to watch out for。That said， it's going to fall out quite nicely。

 We're again going to use basically a matching approach。

 So in the single parameter setting last week， we drew up a bipartite graph on the left hand side was the true type of a bidder。

 On the right hand side was a possible resampled type。

 And we talked about how distribution preserving resamplings corresponded to perfect matchings in that graph。

We also argued that if the allocation rule was already monotone。

 then the maximum weight matching for the appropriate weights was just the straight up the sort of easy perfect matching from left to right so you just match the J smallest valuation with the Js smallest allocation probability and if you don't have a monotone allocation rule then if you compute a maximum weight matching。

 it just automatically uninverts all the inversions in the allocation rule。

 and that gave us the monotone allocation rule at the end of the day。

 which gave us the implementable mechanism。So we're still going to use this matching setup。

 we're still going to look at， know now it's going to be basically fractional matchings from true types to resampled types and so we can't use Myson's limit to argue monoonicity。

 but what turns out to be cool is the exact same linear programming duality we use to characterize well raw un equilibriumlibria will be able to use directly to argue that we're incentive compatible。

OkaySo we're basically going to wind up proving it directly and we're basically going to wind up proving it directly with tools we've already developed。

 Okay， so that's the good news。 So pretty much all the pieces we're about to assemble you've seen in some form before okay。

All right。I there any questions about any of that？If not， I'll sort of set up， you。

 the right analog of the matching for this more general setting。Okay。All right，So here's the idea。

So remember， we have two things we need to design。 All right。

 If we want to sort of establish incentive of compatibility， we need to pick this resamper。

Okay so how do we remap playerize type？And then secondly， if we want。

 we can also talk explicitly about what the payments are going to be。 Allright。

 so the resampling algorithm R that's going to correspond to a prim linear programming solution like fractional matchings。

 and the prices will just fall out of the due。So in what way are resampling algorithms equivalent to some kind of fractional matching？

Okay， it's， it's going to be fractional what are called sometimes B matchings。

Which just means that the amount of flow into or out of a node might be something other than one。

 this is also called the transship problem sometimes。So let me just show you the LP formulation。

And it's basically。The same。As the LP formulations were talking about for unit demand bidders。

 a couple of slight differences that we'll discuss。But no big deal。And so， again。

 the graph you should have in mind here。As you want to have in mind on the left hand side。True types。

And on the right hand side。Reampled types。And you should think of a resampling algorithm。

 remapping an input valuation VI to some other output valuation V hat I as like pushing flow from that true type VI to the resampled type V hat I so the probability between the inputs in the outputs is going to correspond to flow in this graph from the left side to the right side。

So let's fill in some details。So first， what are the decision variables？

So T sub I is the possible types of bitter eye。And so basically。

 they're going to correspond to flow variables。So for a choice of a left hand side and right hand side node。

We're going to have a decision variable S of T， which is meant to represent。The probability that。

 first of all， the true type of bitter eye is S。And then， secondly。That gets rematpped to T。Okay。

So that is the semantics you should have for the decision variable XST in this linear program it's the probability that the bidder shows up with type S。

 and then it's fed to the resampling algorithm that says yeah， well， today。

 let's report you as T to the algorithm A。Okay， so constraints。All right， so first。

For every true type S。Let's look at the sum of the excessTs over T。

So this is the sum of the outflow on a left hand side note。So what should that be equal to？

For this to make sense， for the semantics to make sense。So looking at this。

 so X T is the probability that V equals S and R V equals T。So if we sum this over all possible Ts。

So we're sum this probability overall possible T。Then what are we left with。

That's just the probability that V equals S。Right。And the probability。

 the V equals S that's given by the prior。So that should just be the probability that I has type X。

So this is going to be Fi of S。O。So basically， so another way to think about it is you want to think about the initial flow in this graph。

 you want to think of this one unit of flow， which is probability mass。

And that one unit of flow or sort of initial commodity is distributed according to the true types according to the prior。

 so at a given node S here， it starts， it's endowed with F I S units of stuff。Okay。

 and we want everything to go from the left hand side to the right hand side。

 so the outgoing flow should also equal FIS。Okay， good。Now。

 the second set of constraints is motivated by our distribution preservation property。So remember。

 one of our guiding principles is that when we define these random and last algorithms RI that map types to types。

 we want the distribution on the output types to be the same as the distribution on the input types。

So given that that's what we want。If we fix resample types or a right hand side node。

And we look at some of the flow going in。Or the total probability mass leading to T。

What should this be equal to？F good， F5F T， Thank you。Okay。And that's just because that。

 by definition， is the input is the probability that the true type is T。

 and we want the probability of the re type of T to be equal to the probability of the true type of T。

And good， so that's the entire primal， Okay， the entire primal linear program。

And the claim is that feasible solutions to this linear program are in byjective correspondence to distribution preserving resampling algorithms。

Okay。Namely， so how would you define an algorithm from one of these LP solutions， Well。

 if someone with true type S shows up。You would just output a type with probability proportional to the XSTs where Ts。

 I'm ranging overall possible output types T so the probability given that you have somebody with S。

 the probability of the output T is just going to be XST normalized by F of S。

So you want to think of probability。That RIS equals T given。Yes。This is just going to be X，ST over。

F5 of S。So that's how given these X's， you would define the R Okay， just output。 So it's basically。

 it's almost like a randomized rounding of this linear program， if you like。On the fly。Okay， good。

Don and clear on that。 Fe solutions to this are exactly the same thing as distribution preserving random resampling algorithms。

Not clear this was helpful， but I just want to make sure the projection is clear。Okay。

 but it turns out it is helpful。 it's really helpful， actually， Okay， so let's see why。

So one question is。You knowIs there something that makes sense to optimize？Over this polyte。

And there is。So in the same way， one thing I want to point out， I mean。

 so even though we'll be using exactly the same math。

The exact same compliment Sness conditions we used for unit demand bidders。

 but the semantics are pretty different。 I mean， it's maybe like worth squinting and just like not not worrying about the differences in semantics for this lecture。

 because it might get confusing。That said， I mean， back a couple of weeks ago。

 when we were talking about unit demand bidders and the LP duality， we had different bidders。

On the left hand side and various items on the right hand side。 O。

 and the edges were kind of the value of a given bidder for a given item。right。

 And so now we fixed a single bidder。And we're just looking at all of the possible roles it might play。

 Okay， so these are kind of like possible lives that bitter I might be leading。

 And then the items are somehow corresponding to particular misrepresentations of that bitterder designed to kind of coax some algorithm into a better solution。

 Okay So so the semantics of what things mean is not well preserved。 Okay。

 but it's the same linear you program， the same duality， the same company slackness。

 It's exactly what we need。Okay， good。So here's the objective we're going to want to study。

So let me just write it down and then as time proceeds， we'll see why it's natural。So， I mean。

 in the same sense， in the same way， unit demand with unit demand bidders。

 we wanted to do a welfare maximizing allocation。 here。

 we somehow want to like maximize welfare on behalf of bitter I in some sense。

 So let me write down the objective for that。So I'm going to maximize。Overall， edges， if you like。

 so choices of a left hand side node S， a right hand side node T。And we're gonna look at， you know。

 the amount of flow going from S to T。And so what's the coefficient， Okay。

 So there's going be some edge weight。I need to tell you what WST is。So WST is defined as。It says。

 well。I's true type is S。We're thinking about the case where。So this says true type S。

 resampled or misreported type T。So imagine that， you know， it' true type as S。

 but it says that its type is T to the algorithm。And everybody else reports truthfully。Okay。

So this is evaluation profile。 The other bidders do whatever they're doing。 I says its value is T。

 It's true。 value is S。 and I average this over the other bidders。Okay。So WST。

 which sort of matches up with these semantics right So if you think about this reampling algorithm。

 you know an XST pair， that's how frequently somebody with true type S gets remapped to somebody with type T and then that gets fit into the algorithm what we're saying here is just like。

 oh， well you know when the true type is S and it is actually misreported as T how good is that for this bidder。

 I that like a lot of expected utility or not so much expected welfare， excuse me or not so much。

 So as always， we use its true type to evaluate its value。 But of course。

 the mechanism is in privilege of the truetri， it only goes on what it's told and with this S T pair。

Algothma is being told that the type is T。Okay， so this is how good this particular mis report is for this particular bidder averaging over the valuations for all the other bidders。

So if you think about it， that's a sensibleens coefficient。

 given our semantics that X S T is how frequently you lie about someone whose S is actually being T。

 This is just how good that is for that bitterder。Now， why would we want to maximize this。Well。

 there's sort of two reasons。 remember what our goals are right So we have this algorithm A。

 It's not incentive compatible， but it's a good approximation。 So first of all。

 so we're trying to go towards something which is incentive compatible。

 and this is going to be vague。 but I hope by now you have this sense that you know incentive compatible mechanisms always are basically optimizing on behalf of the participants。

Why would you tell somebody what you really wants Well you'd only do it if they actually act in your best interests。

 given they don't act in your best interests， you're going misreport your interests so instead of compatibility somehow has the flavor of optimizing exactly on the behalf of participants and so that's what this objective is doing informally okay this is just saying given that we're going to remap I types in some way。

 let's make sure it gets the most expected utility possible over all possible remappings given that we're feeding it into algorithmary。

 that's the first thing。Secondly， the second property we want is want welfare to only go up。

 And so at least from bitter eyes perspective， again， we're sort of maximizing overall remaps。 Okay。

 all distribution， preserving remaps。 But still， there's this spirit of we're trying to make eyes welfare as high as possible。

 And so that should somehow also lead to kind of us doing only better than we were doing before。

 Okay so those are all the reasons this feels like should feel like kind of the sensible objective to right now。

Okay。Good。So。Let me just make an informal claim。Which basically is just that， you know。

 for this linear program。 So notice， I mean， this is。

 this is the same objective as we had for our welfare maximization back with unit demand bidders。

 Okay， we've seen this objective before。 I'm just going claim basically。

 we know everything we could care to know about this linear program。 Okay， We know it's dual。

 We know the complementary slackness， etc cetera。 Okay， We already did all that。 back in lecture 6。

 I think it was。Same LP。As for unit demand。Fits。And lecture number six。Okay， so there's。I mean。

 aside from the semantics， which as we've already discussed， are quite different。

 There's two minor technical differences。 Let me just point out。

So minor technical difference number one is that with unitity demand bidders， we had ones here。

Saying in that case， that's， okay， I guess two things。 So first of all， we didn't have a quality。

 We had it most。 Okay， because we were thinking about a case where we have N bidders。

 M goods N can be bigger than M or vice versa。 So maybe some goods are unsold。

 Maybe some bidders don't get an item。So that makes almost no difference。

 It just means that in the dual， instead of having non negative dual variables。

 corresponding to the constraints， we have unrestricted dual variables。 that's all。Allright。

 so the equations also， the right hand side was a little different before we had a one here saying that every bidder should get at most one item because it was unit demand。

 That was sensible。And here we had a one saying every good should be allocated only once， okay。

Which is， which was also sensible here Instead， we have these kind of， fractional things。

 But if you think about it， I mean， you know， it's basically the same thing， right， So like， imagine。

 for example， all of these are multiples of one over 100。 Okay。

 and so maybe one of these is like 17 over 100。 Okay， so just make 17 copies of this guy。 Okay。

 each with like  one over 100。 So first of all， I guess if all of these were the same。

 Imagine it was a uniform distribution。 Imagine these were all one over 100。

 Then it's clearly just the matching L P kind of scaled。 Okay， it's just a change in units。😊。

And if these are different numbers， you could just imagine you know。

 looking at the lowest common denominator or sort of the least common multiple and just making suitable replicas of everybody and then just doing matching with the replicas。

 matchingching with the replicas is just going to correspond to fractional solutions over here。 Okay。

 So I mean， that's sort of a vague。 I mean， but just intuitively。

 this is really going to be the same。2。So， that's the hand waving。That I'm not going to， you know。

 again， go through the same old duality for this。 I'm just going to use it。

But there's not really going to be any surprises。So in particular。

 what we're going to really find useful is the complementary slackness conditions。O。

So consider to remember what commoner slackness is。So if I give you a solution。

 which is feasible for the primal， I give you a solution， which is feasible for the dual。

 complementaryary slackness is a necessary insufficient condition that they're both optimal。 Okay。

 Their complementary slackness is satisfied。 They're both optimal。 If it's not satisfied。

 at least one of them is not optimal。So let's consider an optimal pair and invoke complementary slackness。

So what x star and Y star P star。Be an opt。Prial dualo pair。Okay， so X star， of course。

 is exactly what you see here。Let me just- I'm not going to write it down。

 but let me just sort of remind you the structure of the dual from before。

 so there's going to be a set of dual variables for this first set of constraints。

 so we're going to be calling these the USs actually these won't play any role and then there's another set for these。

 the PTs。These are the， the constraints have exactly the same flavor as for unit demand bidders。

 So the dual variables are exactly the same。 only difference because these are equations。

 These could be positive or negative。 Okay， so in the last application， these were non negative。

 Now they could be either。 It doesn't matter。So that's why I write U star P star for optimal dual solution。

 Okay， use for these constraints， P's for these constraints。Alright， so so by virtue of being。

Both optimal。For the primal and duel。Compment， complimentary slackness conditions hold。

 What do they say。Well， so。In the case of unit demand bidders。You might recall what it said。

 And so this is when we were making the connection to a anduc Lib。

 Coary slackness said the only way that a given bidder I gets some item J is if that item J is one of its favorites at the current prices by favorites。

 that just mean utility maximizing， maximizing VIJ minus PJ。

 Okay so that's what commonary slackness said back then with unit demand bidders。So now， again。

 the analog is， right， instead of bitterders， we have true types。 And instead of items。

 we have these resampled types。So rather than a bitter getting only their favorite items。

 now it's going to be a true type， only gets remapped to its favorite， possible resampled types。Okay。

At the current prices。So common slackness will now say。

The only reason you would ever have a strictly positive primal variable。X star S greater than0。

 I it if the corresponding dual constraints is tight。So again， with unit demand bidders。

 the corresponding dual constraining tight just meant it was a utility maximizing item for that bidder at the current prices。

 So here it just means it's a utility maximizing resampled type for this true type at these prices okay。

So let' going to write that down， So the only way this could be positive。

Is if what you're getting sent to， this resample type T。Has to be utility maximizing。 Okay。

 so in the Arg max。Over all possible things you could be rempped to。Of your value minus the price。

 Okay， so the value， remember in this LP， that's these weights， these WSTs。

 so these are playing the role of the values VIJ in the unit demand setup。So we have Wsz minus。

P star Z。Okay。So again， we could do the derivation。

 but the derivation is exactly the same as a few weeks ago。 Okay。

 So I'm just going to explain by analogy，right。So a few weeks ago， we had a VIJ and a PJ。Okay。

 and that was the only difference， right？Now， we actually had。

 you might be a little confused how a few weeks ago with unit demand bidders。

 We actually had three complementary slackness conditions， all of which were important。

 but two of those complementary slackness conditions have gone away because now we have dual variables which are unrestricted。

 so we also had two conditions， one saying， you know。

 the only reason that a price of a good is positive is if it's sold。

 And the only reason that the utility of bitder was positive is if it gets some good。

 Those have gone away。 basically because we have the equations instead of the inequalities in the primal。

 So this is the only complementary slackness condition。

So if ever you have the primal and dual feasible solution satisfying this。

 they're optimal and conversely， and it's the converse direction we're using here。

So any questions about this？Alright， so let's remember what we're trying to do。 Okay。

 so we're just we're focused on some bitter eye。 we're trying to get the incentives correct。 Okay。

 And so what I'm doing is a high level。 I'm basically saying the way I'm gonna get the incentives correct for this bidder。

 I'm designing two things simultaneously。 How I resample its value and what prices I charge it。

 I'm computing both at once。 I'm solving a primal dual pair。

 and I'm going to use the primmal solution to define the algorithm Mar sub by。

 I'm going use the dual solution to define the payments P。

 And the reason it's gonna to be incentive compatible is exactly because its this complementary sness condition。

 So that's how the threads are coming together。Okay。So。Let me just。

Come back to filling in the details。Right。So。To get Bayesian incentive compatible。

So what is R or R subbi and what are the prices？So define R。Just by the probability。All right。

 so basically， again， if the true type is S， you just resample the type proportional to the X star Ss。

Meaning this， remember the sum of the X star S T sum over T， the sums to F of S。

 So I have to divide by F of S to get a probability distribution。So that's our eye。And then。

Define a payment rule。PI。Such that the expected payment。That bitter eye has to pay。

When it declares T and the expectation as usual is over other people's reports。

 this should be equal to P star T。For all tea。Okay。So this this， I hope is clear。

 we sort of already talked about how the primmal solutions correspond to potential resampling algorithms that preserve the distribution。

 So just to remind you a couple of things about payment rules in a Bayesian setup。

 So a payment rule by definition takes as input a full valuation profile。

 Okay so this is both whatever I reports， whatever reports T。

 this is you know what the other people report assuming they're reporting truthfully。 So V minus I。

 This gives me a payment for bitter eye on this valuation profile。 But again， remember。

 you know we're in this regime of assuming risk neutral bidders。So the only thing I。

 as a bidder care about is my expected payment where the expectation is over possibly random choices of the mechanism and then also over the randomness in other people's types。

 So I actually don't care what this payment rule is as long as the expected payment by I when it declares T as exactly what the dual linear your program is telling me it should be P star T so this is just some number like 10。

 I don't care what these numbers are as long as they average to 10 and neither does the bidder okay。

So choose Pi PI however you want as long as this equation holds and。Obviously， you know if you want。

 it could even be sort of I mean， it's easy to think of rules that could do that。

 many rules that could do that。 and I'm agnostic as to which one you do okay。So。

This is the construction。O。So the claim is， if I resample I's truthful declaration。

 according to this R sub I， and if I charge at a price according to its declaration。

 according to this， then at least for I， it is Bayesian set of compatible。

 That is I maximizes its expected utility， if it does direct revelation。Okay。

So the reason is already on the board， but let me just。

 I want to go through it carefully because I know there's a lot to keep track of。All right。Okay。

Questions。이 다。Sa it again。Yeah， so right。 So excellent point。

 So the question was about the size of TI， the size of the type space。 I mean， at the end of the day。

 I mean， I mean， just even trying to run R sub I。RightSo even just， I mean。

 I I'm thinking of oursibs literally just sort of， you know。Right， so I mean， the right。

 So this linear program is indexed by the types。 So the the running time of the big mechanism we get at the end of the day is going depend on the type space。

Which is not。Which is a drawback。 It's probably the biggest drawback of this reduction。

 And so it's an excellent comment。 It's not really clear how you'd bypass that with some general black box reduction。

Maybe for specific cases， you could handle implicitly defined type spaces。But just， I mean。

 just to make sure the point is clear about why you， it， it can be a bummer to。

 to depend on the type space。 So like imagine。Right， so it's commercial auction， right。

 Multi multip mechanisms。 So imagine there's like M goods。 Imagine there's like 100 goods， okay。

And your value for each of the 100 goods， let's even say you have an additive valuation。 Okay。

 so it's like a trivial type of valuation。 And for each item。Right， you have value。

 either 0 or one for that item，50，50。Independent for the different 100 items。Okay。

So the number of different types you could have is 2 to the 100。O。

 but it was somehow a very simple sounding， succinct to describe， you know。Type distribution。Alright。

 so the running time of this thing would be polynomial in that2 to 100。 Okay， now， maybe for。

 you know， like， so I think an interesting research question is for sort of nice。

 implicitly defined distributions， Can you have a reduction。

 which then is polynomial in the description size。 And I haven't seen too much work on that。

 I think that's largely open。And if you wanted something as sweeping as what we're doing right now。

 I'm not really sure how you'd bypass the dependence on the types。But yeah， thanks in the comment。

So and so another way of saying it is the algorithm A that were given。

 the good approximation algorithm， we're thinking of that as being polynomial。

 probably only in parameters like n。But then we're going to give a mechanism which is polynomial both in n and in the type of space size。

 so that's the real cost of the reduction。Other questions。Okay。All right， so why is this true？

 So the claim is， this is the panacea right here。 Okay， Use this R sub I， use this piece of I。

 and we're good to go。So let's prove that。Right， so key points。So by complementary slackness。

Whatever eyes's true type may be， S。Basically， the resampling algorithm is doing right by bitter eye。

Okay。So if I look at the various。Mireported types T that S might get mapped to。

 all of them maximize I's expected utility。So R sub remember this， So this， remember， this。

 this is something random。Okay， in general， right so this is our is a randomized algorithm in general。

 but everything its support and its support is good for bitter eye。Okay， so it mixes。Only over。

Declarations T。That maximize。Eyes expected utility。Where as usual。

 the expectation is over Father bidder's valuations， what is I's utility。

 where again we look at its true type， the algorithm though is run with a declared type and everybody else's true types。

 and then there's some payment。Okay， so just to make sure this is clear what's inside the square brackets。

Is I's utility， given that its true type is S， given that the report T is fed into the algorithm A。

 and given that the other bidders fit their valuations v minus I into the mechanism。Okay， so this is。

Utility。All right。Again， true type is S， but T gets fed into the mechanism A to the algorithm。

This here。OrAt least once you apply the expectation to it。

That is just how we defined the coefficients of our linear program。

We defined it to be the welfare that a bidder with true type S enjoys。On average。

 when tea is instead fit into the mechanism。So this is equal to WST。And then this。

 just by the definition of our payment rule， is equal to P star。Of tea。Okay。

And so what does commentaryary Sness say， Comary Slaness says the only way X star S T can be strictly positive。

 In other words， the only way that the resampling algorithm might conceivably output the declaration T。

Right， so the support of this resampling algorithm is exactly the T's for which this is positive。

 The only way that can happen is if that happens to be a declaration， which maximizes。You know。

W S Z minus P star Z overall Z。 I。e maximizes。Bittterize utility when it has true valuation S overall all possible supports。

So why does that imply Bayesian insect compatibility， Well you know。

 imagine your bitter eye right and you're sort of trying to craft some very clever deviation。

 some very clever thing。Or at the end of the day。Right。What do you do， You just。

 you report some possibly false valuation that gets remapped to some other report that gets fed into the algorithm A。

 And by assumption the other bidders are just feeding in truthfully v minus。 That's all you can do。

 All you can do is influence what at the end of the day gets fed into the algorithm A The resampling algorithm R I is already feeding it in an optimal response for you every single time with probably one Nothing you can do can do better than what the resampling algorithm is doing for you。

 it only uses best possible declarations feeding into the algorithm A。So。

If we if we define RI and PI this way。Direct revelation。Optimmal， again。

 in the sense of utility maximizing。Optimmal 4， I。Okay。Is that clear， that's really kind of the。

Biggest point of the lecture right there。Right。So you design the resampling algorithm and the payment rule simultaneously is a prim modual pair。

 Coary slackness gives you the desired incentive compatibility guarantee。

 So this is how we manage to kind of dodge basically needing to prove some analog of myson's lemma。

 We kind of just get the incentive compatibility。 We just prove it directly as a consequence of this complementaryary slackness。

O。So let me remind you at the outset。I kind of said this was the first step where we made an unreasonable assumption。

Where we said， let's， you know， let's just focus on a single bitter eye。For all the J not equal to I。

 let's assume that there's no resampling。 And let's assume that even though the incentives are wrong。

 they just declare their true type。 Okay， all the analysis thus far has made those two assumptions。

 Either our Js our identity and everybody else is doing direct revelation。But here's the point。

What we just said about I maximizing its expected utility by just doing direct revelation。

 This is still true。If we use any distribution preserving RJs。Resampling algorithms。Okay。

So these should be independent resampling algorithms。But so suppose now， I mean。

 the point is basically， if I'm bitter I and I'm doing all my know， again。

 when I reason about whether direct revelation is a good idea or not。

 the only thing I care about the other people is the distribution by which the V minus I show up。

 Okay All I care about is my expected utility。 and this depends on other people's actions only in as much as it depends on the distribution of V minus I's。

So if every bitter J other than me right， so know if they truthfully reveal something and then they get a randomly remed declaration。

 but the distribution is exactly the same as before。 So in other words， if each marginal。

Of the distribution number of valuations the same as before。 What do I care。Okay。

 so before this was the best thing for me， assuming averaging V minus I's according to F minus I's。

 Now there's some， I mean， from my perspective， it's basically like you swapped out one algorithm that had a particular output distribution。

 You swapped in a different algorithm with different code with an identical output distribution。

 And you asked me if I care。Okay。And by assumption。

 with these risk neutral bidders and this Bays Nash setup。

 I only care about my expected utility with respect to the distribution over F minus I。

 So any changes you make that don't change that F minus I。

 don't change what I think is the best response or not。Okay。So initially。

 we thought about RG as being the identity， but doesn't matter。

 As long as they preserve the distribution， direct revelation is still the best response for me as bitterder。

 Theres all I care about is maximizing this。 And again。

 this quantity only depends on other bitterders and as much as it depends on。

The distribution over V minus I。Okay， so the reason is that f minus I。Is unchanged。Okay。So again。

 before， we were making two assumptions first， that the RJ is with the identity。 and secondly。

 that people were doing direct revelation， even though they didn't have an incentive to。Now。

 we're not assuming that the other RJs are the identity。

 We're just assuming that they preserve the distribution。

 but we are still assuming that the other bidders do direct revelation。

But now that's okay because they also， by construction of their RJs。

 maximize expected utility by doing direct revelation。 So to basesn equilibrium。

 it's only a best response for me If you're also doing it， that's the normal equilibrium concept。

 Okay， so I should do direct revelation as long as you're doing direct revelation。 So that's fine。

 We get that simultaneously for all of the bidders。😊，All right， so in other words。

So as long as we define all our eyes。And PI is this way。And by this way。

 I just mean you solve this separate primal dual pair for each of the bidders to get the corresponding primal RI。

 dual， PI。Then we indeed have our desired big mechanism。你看。So next up is the welfare analysis。

 which is not hard， but any questions before that， Any questions just about how we got the incentives right。

Con need distribution design。okay， yeah， so what could go wrong， So it's conceivable。

 There's some other construction that doesn't require it。But， you know， the。

 the obvious problem would be。Right so I mean， I need to right。

 so I care about what v minus I is being fed into here。 right， So my utility for both of these。

 right。And so sometimes this number is going to be high， sometimes this number' is going to be low。

And depending on what I declare， it's going to change。Right。

And so so imagine there's two things you could declare。Right。And you in each case。

 there's a case where you get high utility， and there's a case where you get low utility。

 And you're wondering， what should I do， option A or option B。Well。

 whichever one is more likely to give me high utility， that's my best response。

But the point is if I change the distribution over the V minus Is。

 now it might be the case that now all of a sudden option B is more likely to give me high utility than low utility because of course。

 my utility depends on other people's reports。So it seems like you'd need some more global construction if you wound up not preserving the distribution of every single bidder。

So I guess a different way I'd put it is if you have in your mind that you want a black box reduction and you say to yourself。

 how could I possibly prove it， I think this is the first thing you'd want to try and the cool thing is that it works。

Yeah。I mean， the other thing you could try to do is you could try to somehow do it iteratively。

 you could try to sort of like first fix bidder1， you assume bidders2 through n。

 you know assume deal with them later and correct bidder1 and maybe you screw up the distribution and then you proceed to bidter two and you could try to do it for it。

 But then the problem is by the time you get to the end。

 maybe you screw up bit one's incentives again。So。Hard。

 hard for me to see how you do it without the distribution preservation property。

 So I was just thinking， as long as everyone's posterior is the same。

You could just commission on whatever the post。 You lose your welfare。Say it again I as。So you。

 you're saying imagine， imagine I now have a correlated F。 No， not correlated。

 It is independent for each person。 just making sure the same independent thing for each person。

 the same independent mappinging for each person。You just care what the distribution on the right hand side of your margin is。

In this。Yeah， I'm not so sure， right， because the weights。 I mean， if you look at this change。 Yes。

 the weight should be with respect， too。Whatever you've engineered at the posteror。It has no use but。

you better be optimal with respect to the real weights。um。Maybe。

 maybe we can talk about them more later。Other questions for the welfare analysis？All right。

 so we've got the incentive property。So that's good。So welfare analysis。And so again。

 we can just do this bidder by bitterder， right So by linear of expectations。

 we can just look at we're actually going to argue that each bidder's contribution only goes up。

So let's start with the contribution of a bitter eye to the expected welfare in the mechanism。 Okay。

 so after we've done the reampling。Okay， so we're averaging over all inputs。

 so the entire valuation profile。And we want to look at the overall welfare。

Where what's being fed into the algorithm is the research so this is this expected welfare of B。

Since what we want to argue is high， has only gone up。Okay， so well， what is it by definition。

 so for bitter I？Well， there's the various types it could have。Okay， so let's just condition out。

On what its true type s is。Now let's examine what the resampling algorithm does to its type。

So this is just sum over tea。And this is just the probability that。Rs is equal to T。

And so what is this？So by construction， this is just whatever the linear program told us it should be normalized to be a probability distribution。

 so this is just。X star S T over F of S。So of course， we get some happy cancellation there。

And then there's still some randomness left。Right， so this。

 so what we've done is we've conditioned on what I's true type is。

 what type it's reported to the mechanism A。 And then we have the expected。

Welfare where the expectation is over the remaining randomness。

 which is over the remaining valuations of other bidders。And this is， let's see。

 so I's true type is S。And then again， the algorithm is invoked。With the resampled。

ActuallyI guess I've conditioned on T， so sorry T。V minus I。So I've cheated a little bit here。

Really what I should write here is。The resampled version of v minus I。But the point is。

 it doesn't matter for this expectation。 right， If I take the expectation over v minus I or take the expectation over R minus I of v minus I。

 same distribution。 Okay it's the same number。So this is again， where we use the。

Distribution preservation property， they resling algorithm。Okay， so we have a name for this。

So this is just our linear program coefficients。Ex utility to a bidder when its true type is S and T gets declared to the mechanism。

Okay。So all this becomes sum over ST。X star， ST， WST。Yeah。Which makes us happy。

Because this is exactly what we explicitly optimized in our linear program。So that sounds promising。

So that's I's contribution。To the welfare and B。What about I's contribution to the welfare of the original mechanism？

So， this was to B。Okay， so this is now。Oh yeah， I see。Right。So contribution to right， blah， blah。

 so without the resamps。So this， again。We can condition on what bitter eye true type is。

That happens with Sac occurs probability FFS。And then。S is what actually gets fed into the。Algorithm。

So this is just going to be S。诶。S v minus I。So this again。

 is just this is one special case of the coefficient in of the new program。

 so this is just the expected utility to bitter eye when it actually has a true type S and declares it。

 also known as WSS。And the point is， okay， so the welfare after reampling corresponds to the optimal solution of a linear program。

 and the claim is just that our old welfare was some feasible solution to this linear program。

 okay and therefore is it most as good。Specifically。We can think of this。 So these are the W S Ses。

 So this is as if。We take our usual objective function。And all the terms are zero， unless t equals S。

 in which case x hat is just equal to the full mass F of S。Okay。

And the point is this is a feasible solution。To the LP。

And X star was chosen to maximize the objective。So。New is at least old。嗯。Which is what we wanted。好看。

That the welfare analysis。So， you know。Basically， what one would really hope would be true is true。

 right So we know that there is， you know we know from things like the VCG mechanism that there's really good coincidence between getting an incentives right and getting optimization right。

 And we see that here。 So basically we define the random sampling algorithms and the prices from optimization。

 it only improves the welfare。 again， the intuition is the same as a single parameter case somehow in optimizing the weights。

 you just sort of uninvert all of the inversions and the allocation rule you were given with and you you get the incentives for free。

So let let me just say where this algorithm is from。So there were two concurrent soda 11 papers。

 so one by Wei and G Wang， who's actually at Stanford as a postdoc these days。

And then the other paper was by Jason Hartline， Bobby Kinberg and Mallectian。

So that's where these come from。And so what we can conclude there is definitely some tenical fine print and the biggest point is what we mentioned in the discussion。

 which is to you basically even sort of writing down these sampling distributions is polynomial in the type space and it's undesirable in some contexts。

 but it says you can take any polynomial time alpha approximation algorithm， polynomial in whatever。

 and there exists a big mechanism， which is polynomial in the same stuff plus polynomial in the number of types which has just as good an approximation factor and is big so again like a killer application thinks submodular evaluations。

We mentioned in passing that if you throw out incentives。

 you can get 63% maximizing welfare with the mod evaluations。 DI have no idea。

We gave one for coverage valuations， but in general。

 seems like one might not even exist but this says if you relax to bit， you can get that 63%。

So the mechanisms aren't that simple， that's the point of the next lecture。

 starting with the next lecture， but in principle you you know this really kind of shows how much。

 you， how much easier in some sense the sweep and positive results you get with baesing andat that you don't with D6。

So I'll see you in about 10 minutes and then we'll。

