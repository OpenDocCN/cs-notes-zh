# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p21 -21-(Lecture 20_  Characterization of Revenue-Maximizing Auctions) -BV1fNVNzhEBg_p21-

All right， so just the story so far。 So let's just sort of recap where we are。

 So what we've accomplished is we have this linear program with a reasonably small number of decision variables。

嗯。Where the whole point is right that we phrase everything only in terms of the interim allocation and payment rules。

And so what are the constraints， we have the Bayesiancent probability constraints， those are easy。

 the individual rationality constraints are easy， and then we have these border constraints。

Saying that one is at most too。嗯。There aren't too many of these incentive about a constraints。

 They're just for all I， for all true typess， for all reported types。

 there are even fewer individual rationality constraints， for all bidders for all true types。

 There's a ton of border constraints， tons of them。 Okay so these are for all J， all items。

 And then for each fixed J。 You have to have a choice of the restricted set of valuations。Okay。

 so certainly exponentially many constraints。Okay。And then right， non negativity。

And feasible solutions。Are exactly the reduced forms。 And remember。

 reduced form is just the fancy word for the Ys and the cu's， okay。

Well the point is there are actual Y's and Qes induced by bona fide mechanisms XP。

So we have a linear program with much smaller dimensions that doesn indeed capture all of the reduced forms。

And。I think it's useful to have a sort of， you know， very coarse geometric。View。Of what's going on。

Okay。So the geometric view。Is a projection。你确。And again， as you've seen。

 because all of the complications are with feasibility and feasibility in the problems we're setting only references the allocation rule。

 I'm often just going to ignore the P's and Q's。 I'm just going to focus on the x's and Y's。

 That's where all the hard stuff is。So in general， what we're doing is we have this。

High dimensional set of x's。This is my attempt at a high dimensional polytope。Okay。And then。

We're projecting it onto a lower dimensional space。Okay。So so I'm going to call this set x。

 and these are the Y's。Which。I'm to call capital Y，And so this mapping， so just to be clear。

 so what is this projection？So the X IJ V arrows， so this is the X post allocation rule。

 are inducing the YIj VIs。via。This average， okay， so just this weighted sum。So this again。

 is just the definition of the interim rule。But again， what I want to emphasize here is just。

 this is just some linear function。 Okay， so we get the Ys by just applying some， you know。

 linear projection type operator to the exit。 So this is basically what's going on。

So this high dimensional polytope， we had an explicit description of it。

 that's what we started today with。 Okay that's when we had the variables。

 the x's and the P's indexed over all of the valuation profiles V。 So it was huge dimensions。

 but it was very easy to just write down all of the constraints。

 Okay so we had this exact character we had an explicit description of what this was。

So then what did we do， So then we said， let's pass to the interim rules。

 So we basically figured out what dimension we wanted。

 what the variables were and what we just did is we just figured out an explicit description of the projection of this polytope Okay so we said。

 take all the real allocation rules， project them into the Ys。

 and now you know what happens to the constraints。 And can we get a handle on what those constraints look like And this is them。

Okay， so these are exactly the defining half spaces for the projection of the polyte。 Okay。

 so that's what this is。 Expit description of the projected polytope。Okay。So。

That's just worth kind of keeping in mind as a rough guide。

Because we're going to have some geometric arguments。In this lecture。Now。

 remember so in this lecture， what I want to focus on is know really structurally。

 can we have an analog of you， can we have some version that says revenue reduces to some variant on virtual welfare maximization？

And。I claim， if you think about it， here' would be the best case scenario。

So a special case of what we're trying to do is the single parameter theory。

 which requires virtual welfare maximization， we've seen even in a single buyer。

 we need randomization。So what be the simplest imaginable description of optimal auctions？Well。

 I guess it would be a randomization over virtual welfare maximizers。

That's kind of the conceptually simplest thing we could possibly hope to be true。 And shockingly。

 it it actually is true in problems we care about。 So that's going to be the point of this lecture。

So best case scenario。嗯。Opt auction。Is a distribution。Over virtual。Welfare maximizeims。

 which I'll define exactly what that means a little later。Okay， so VWMs。

So the two things that are going to be more complicated than in the single parameter theory。

 first of all， there's the randomization， but we know that's necessary。 The second thing is。

 and this is not surprising。 we're not going have some formula。

 We're not going to have this v-1 capital left divided by little F。 I mean。

 that's just way too good to hope for。 So， the analog of those virtual values。

 It's just going to be computed from some linear program。 But once you compute it。

 it gives you the functions。 And then you do a suitable randomization。 and you're good to go。

All right。At the same time， I'm gonna go beyond additive， okay。And。I'm not going to define generally。

 you know what， what， what one can handle。 but I just want to think about this representative special case of unit demand bidders。

Okay。ち去。Yeah， so not additive， the point。And if you think about it， this already。

 so what we did last lecture does not apply to unit demand bidders okay and the reason is is because for unit demand bidders。

 we basically want to add some constraints to the original X post linear program。

 the highdial linear program。So， change。In the non reduced。LP。So remember unit demand bidder。

 So again， like addeditive bidders， you have these Vjs。 But when you get a bundle。

 you don't take the sum， you take the max。 And the way we normally think about that is like， well。

 okay， if people only want their best item， let's just only give them one。

 And so usually just restrict allocations to give each bidder at most of one item。

 And then it's basically like bipartite matching。 So if you think about that， you're like， okay。

 so now back in the original non-reed Lp Last lecture。

 we had the constraint that every item was allocated to only one person that made sense。

 Now we just want the other set of constraints that every person gets one item。

So for the non reduced LP， we want to add。And so remember， this is in terms of the x's。

 this original LP。So we add that。去去。The total for the goods given to a given bidder。Is it most one？

For all I and V bar。Okay。So geometrically， what we just did to pass from added evaluations to unit demand valuations is we took our high dimensional polytope and we added some more constraints。

actually kind of a lot more constraints because it's one of these for evaluation profile。Okay。

So that means that this projection is going to look different。And it means that you know。

 the border constraints are no longer in general， going to characterize all of the reduced forms that we care about。

 Okay， so last lecture， we had some Y's， that's in the projected space。 And we said， you know。

 when is there an X that induces them。 So we're asking exactly the same question now。

 except in our except the xs we have in mind are more constrained than they were before。

 not only do they only give an item to one person， they only give one。One item to a person。

 Okay so not correct。So the question then is， how does this change in the high dimensional polytope get reflected in the low dimensional polytope Okay so this works for additive bidders。

 What's the analog for， let's say unit demand bidders or much more generally。Okay。

 so those are some of the motivations about what we're going to do and the issues that we're going to solve。

So let me tell you what's really kind of the main point of this lecture。Okay。

 so the main structural theorem。And this is barely a year old。

 So this is Kai Dascalacs in Weinberg from Fox 12。So， and again。

 I'm going to state this for unit demand bidders， but its， you know， it is more general。 Basically。

 the assumption you need is that the bidders are additive。

 but that there's also allocation constraints。 So a's sort of weird way to think about unit demand bidders。

 you can think about it that， you know， my valuation is actually additive。

 but just the mechanisms only allowed to give me one item。Okay。

And then that's actually equivalent to being unit demand。

 Okay once you have the allocation constraints。 So any time the valuations can be so expressed as additive。

 but with additional constraints on the allocation。

 then what I'm going to talk about today works okay。

So it's not all the applications you'd want to care about， but it is somewhat general。All right。

 so here's the claim。So every vertex。Why？Of why。 Okay， so remember Y here is the projected polytope。

 Okay， so I'm saying， consider the polytope of reduced forms。And consider a vertex a corner。Okay。

The claim is。Every corner of this projected polytope。Is induced。By a virtual welfare maximizer。

So I'll tell you exactly what a VWM is in a second， but again， just to be clear。

 I'm saying pick a corner of the projected polytope。And this unit demand set it。

Look at everything that projects to it。 there may be many， when you do a projection。

 it's not injective。 Okay， so many things from the high dimensional polyte may map to the same point in the low dimensions。

 but I just claim I can find something in high dimensions。

 that is I can find an actual allocation rule， which is a virtual welfare maximizer that projects to this particular reduced form at the vertex。

So then。You know， I don't expect you to necessarily know what to make of this。

 but this actually implies what we want， and I'll explain why it implies what we want。

 This gives us an analog of Myson's theory， basically。All right。

 so what's what's a virtual welfare maximizer。So a virtual welfare maximizer。Is an allocation rule x。

That maximizes。I mean， it's what you'd think， so basically what it does is it looks at the input valuations。

 it applies some transformation， which I kind of call fee in the spirit of last quarter。

 and then it just maximizes welfare with respect to these transform valuations and so the free parameter is this fee。

 this transformation。So， that maximizes。Over feasible allocations。And where the FiIJ is。

Our arbitrary functions。O。So for example， suppose it was unit demand bidders。And again。

 unit demand in this context， we're thinking of just like the allocation should be a matching。Okay。

So then what does a virtual welfare maximizer look like， Well， up front。

 it precommits to some functions VI J。Okay。And so basically when a bitter eye shows up and it says。

 oh， my value for you know the three goods are3，5 and 7。

 then we invoke the virtual valuation function it says all in that case， I'll give you weights。

 you know，10，2 and 6 for the items 1，2 and 3 so the fee takes as input。

 your value for each of the M items and it spits out your weights for each of the M items Okay so that defines your fiI Js is a function of your report。

So now for each bidder item pair， we have a weight。Okay。

 so the output of the FiI J on that particular item。

 And now we just compute match matching with respect to those weights。

So that's a virtual welfare maximizer。 Okay so there's some table lookup as a function of what people report。

 what weight you describescribe to particular edges， and then you just do max weight matching。Now。

 there's a lot of these because there's a lot of lookup tables。

 you can basically have arbitrary freedom of mapping the Vs to the weights to the fee of theses。

But for a fixed choice of fee， it's just a very simple deterministic mechanism。 Okay。

 And in the unit demand case， easy to implement polynomial all time。 Okay， because again， really。

 this is just doing welfare maximization。 And the fees just tell you what weights to feed into the black box。

 It does a welfare maximization。Okay， definitionqueer。All right。And so in the， you。

 in the single parameter case， there's only， you know， we usually think about only one item。

 So there's no J。 Okay， so in the Myerson theory， there's no J。

 And then fee was a particular function that we wrote down explicitly。

 Okay but with those additional simplifications， it was indeed a welfare。

 a virtual welfare maximizer。All right， so let me now explain why this main structural theorem gives us an analog of Myerson's theory。

 Okay and that'ss。Pretty。It's not not too hard and then I'll this， prove the theorem。嗯。It' corollary。

The two corollaries。And we'll have kind of everything we want。So for every allocation rule， X。

So remember， Capital X is just the non reduced LP， capital X is just the polytope of all allocation rules that are feasible。

So for every feasible allocation will X。The claim is， there exists a distribution。Over VWMs。

 so remember， virtual welfare maximizers live up here。Okay。They're real mechanisms。

 They're not interim， right， They really are operational。 They tell you what to do on every input。

So VWMs live up here， consider an X， which lives upstairs。The claim is。There exists a distribution。

Over VWM is little X prime。Which is a complexve combination of virtual welfare maximizes is also an allocation rule and in this polyte capital X。

So that。X and x prime。Have the same reduced form。So， don't forget。

When you're doing a projection like this， it's not injective。 Okay。

 so many different mechanisms can go to exactly the same point downstairs。

 that is many different mechanisms can have exactly the same reduced form。So what I'm saying here is。

 give me any mechanism you want。 Okay， I'm not claiming that that mechanism has to be a distribution over virtual welfare maximizers that need not be true。

 but I am claiming， well， if all we care about are reduced forms。

 then this thing may as well be a distribution of a virtual welfare maximizers。

 I can find one that has exactly the same reduced form。Okay。So that's what I'm claiming。So okay。

 so why is that true？So that's basically true by linearity。So， start from X。Okay。

And so the original allocation rule， so it has some reduced form。Okay。In any polytope。

Any point can be written as a condessc combination of the vertices。

So I don't know how much basic polytop here you guys have seen，So in two dimensions。Anything inside。

 not only can it be written as a convex combination of the vertices， but， in fact。

 you can always find at most dimension plus one vertices of the polytope， So in this case。

 a triangle。So that if you take the suitable convex combination of these vertices。

 you can get that point in the interior。 Okay， so polytopes， there's a duality in polytopes。

 you can either describe them as the intersection of half spaces。

 or you can describe them as the convex whole of finite set of points。

 and you can go back and forth as you like okay。So this is a polytope downstairs。

 so when you project the allocation rule x to get a reduced form。

That reduced form is a convex combination of the vertices of this polytope。

The main structural theorem says that every vertex of this polytope is the reduced form of a virtual welfare maximizer。

 okay。So basically what we get is we get' some point in the middle。

 and it's 20% of this reduced form of this one virtual welfareer maximizer。

 30% of this other one and 50% of this other one okay。And now because everything's linear。

 you just go back upstairs and you say， okay， well for each of those three corners。

 let's look at the virtual welfare maximizer that induces them and let's just take 20% of the one plus 30% the other plus 30% of the third as proper allocation rules and lo and behold that distribution over virtual welfare maximizes。

 that mechanism induces the same reduced form that we started with the same reduced form of the occasionalal X that we began with。

So you project， decompose into the corner， decomposes a comic combination of the vertices。

 apply to the main structural theorem， and theyll go back upstairs in your done。

So proof bi linearity。All right。Okay， so that's the first point。 And then the second point is。

 is that if all we care about is our revenue。Then the only thing we care about in our mechanism is its reduced form。

 we actually could care less about additional details。

We only care about our mechanism and as much as we care about the reduced form。 We already saw this。

 So when we first motivated the reduced linear program。

 we said what we clearly have going for us is that， you know， to express the revenue in particular。

 but also some of the constraints， the interim rules were enough。

 So we're going to use that again now。So corollity。There exists。A revenue maximizing auction。

That is distribution。Over virtual welfare maximize。Why take an arbitrary revenue maximizing auction？

Apply this corollary to get a possibly different auction。

 which is a distribution of a virtual welfare maximizes and has the same reduced form By virtue of having the same reduced form。

 it has the same revenue。 So that is also an optimal a。Okay， so giving an arbitrary optimal option。

 I'll show you another one。 that's a distribution of a virtual welfare maximized。O。

And this basically this is great okay， this is really you know。

 probably a huge closer to Myerson's theory than we probably had any reason to hope for seeing those crazy examples last week。

 in my opinion so I find this sort of very satisfying。Okay， so that's this。

 so this fact is sort of the main takeaway， really of this lecture。 All right。

 So you do have a multi parameterer analog of Morrison's theory。

 at least for these additive problems， subject to feasibility constraints。

 although there's been some further generalizations over the past year。

So you do have to have a distribution， we know that， and you don't get an explicit formula。

 which is not surprising， but beyond those two drawbacks。

 you get the same structural understanding of optimal mechanism。So any questions about that。

 I do want to sketch the proof of the structural theorem。

 Like we're distributing over different mechanisms。

 we just take our allocation rules and like 20% of the time use this exactly。Exact。

 and you can flip all the coins at the beginning。And so I hope this was clear。

 but so where do these coins come from， they come exactly from the coefficients on the corners of this polyte down here。

Yeah， yeah。 So So this is not obvious。 I mean， this， this is what's interesting。

 This is the interesting part。 Well， I mean。呃。Maybe conceptually this is what's really。

 The reason this is interesting is this gives you this， And， but this is not that hard either。

 I mean， it requires a proof。Not that bad。Good， other questions。ち。All right。

 so proof of structural theorem。Right。O。So consider any vertex of y。O。So some corner downstairs。

Alright。So one thing which is intuitively clear and not all that hard to prove is that you can characterize the vertices of a polytope in the following way。

 Okay， so think about linear objectives。 So in other words， you know， directions of optimization。

 Okay， think about like you're maximizing， okay。So if you're maximizing linear function over a polytope。

 you basically want to go as far in the direction of the normal until until there's no level no longer an intersection with a polyte so you can imagine like a sweep line and when you get to the end of the polytope。

 that's where you stop and that last point in that direction is the maximizer over the polytope。

So that's going to be a corner， it's going to be a face certainly。

 and sort of you know generically it's going to be a corner， and in fact。

 corners of polytopes are characterized by this。So if you say， consider a polytope。

 consider the set of points that arise as the unique maximizer of some linear objective function。

 that subset is exactly the vertices of the polytope。Which you know， which makes sense， right？

If something's sticking out， then you just pick the direction to go as far in that direction as possible。

 And then conversely， if you don't have that property。

 it must be because you're the interior of some face。So we're going to use that property。

 we're going to use that property in the vertices of a polythic characterized by being unique maximizers in some direction。

So， at W。Be a linear objective。Such that Y star maximizes it。And so， you know， just to be clear。

 what's objective function。 So the variables， right are the。Y， I， J V I。

So remember the payment rules are not relevant here。 so we're just looking at the Y's。

 These are the variables。 So W is indexed to the same way as the variables， right。

So we're going to have a why。Sorry， WIJ。V I， and then me sum over all of the relevant stuff。

 So sum over J and U， sum over V I and V I and sum over I。In。Okay。

So this is just W transpose y expanded over the relevant index sets。Now， here's。

 heres here's sort of the sneaky part。So from these weights。

 let me extract a virtual valuation function。嗯。So define， remember I'm trying to prove。

 trying to prove that why star arises in effect as a virtual welfare maximizer。

 So to prove that I need to come up with these fees right and the fees are unrestricted can be whatever they want。

 but I got come they got to come from somewhere and it's going to be this direction of maximization that I get them。

So， define。FI J。To be to the weights。And again， I have to do this thing where I translate between the conditional and unconditional chance of winning。

 So I'm going to scale back up by the probability of this type。Okay。So this is just the usual prior。

 kind of probability that ice type is VI。Okay。So hopefully it's clear sort of where I'm going。Right。

 we have our Y star。 I suggested a fee。 So evidently。

 what it would seem I'm going to argue is that the virtual welfare maximizer corresponding to fee。

Has the reduced form Y star？Right， we started with Y star。 I needed a VWM for VWM。 I need a fee。

 I just told you a fee， so。So that's how it is going to go down。So。All right。

 so what's the easiest way to argue this？What we're going to do is we're going to say， basically。

Give me any allocation rule。The claim is its virtual welfare with respect to fee boils down to this quantity。

Okay， and again， so you may wonder like what what is it nontrivial that I'm doing。

 like what has to be argued。 And again， it's just， you know。

 keeping track of what's upstairs and what's downstairs。 Okay。

 keeping track of the allocation rules and keeping track of the interim allocation rules right。

 So why is just with respect to the interim and virtual welfare maximizes or upstairs。 Okay。

 they real allocation rules。So。But the claim is， for every allocation will X。You know。

 whether it's explicitly maximizing with respect to fee or not。Can write its virtual。Welfare。Again。

 with respect to this choice of fee。As。Well， so first， just by definition， you know， what is it。

 So we average over all possible valuation profiles。 So this is kind of， well， let me start it down。

So we just expand， we condition on what the input is， and then on a given input。

 what's our virtual welfare， Well we just sum over the bidders。Some over the goods。

And then we look at。Who gets it and what's there？呃。What's their contribution to the virtual welfare？

Cases are just by definition。So I'm treating p as an objective function。 O。

 X is an arbitrary allocation rule。 I'm just saying。

 how well does it do with respect to the objective function fee。This is how well it does。

 could be good， could be bad， depends on x。嗯。Now， we've seen this over and over again。

 linear objectives。Can be articulated purely in terms of the reduced form。Okay。

 so this is written in terms of the x's。 This is in terms of the allocation rule。

 I can equally well write it just in terms of the induced y。So it's by linear of expectation。

So the expected virtual welfare， let me just separately look at each bitter eye's contribution to the expected virtual welfare。

So that's going to depend on what its type is。So I should look at the probability that it has a given type。

And then when it has that type， I should look at its contribution。Okay， which should be this？So。

 FiI J。Notice one thing that's really important is that VI J depends only on V I Okay and I emphasize this back in the single parameter world as well。

 that the whole the whole point of a virtual value definition is that I look at a bitter I。

 I look at this report。 and without knowing anything else， I can map that to some new value。

 Okay so again， it's crucial that VI J depends only on V I and not V minus I。

 That's also what allows us to pass to the interim rules without any problems。

And then this should be a Y IJ。VI。Okay。呃，呀。Right。So this is the expected。 So what do we have。

 So this is the expected contribution of bitter I when its type is V I， this is its unconditional。

Contribution， this is the total contribution。And so now it's clear why I define the virtual values the way I did。

Okay。So I've passed from the allocation rules to the interim rules。And now， this is just。

Objective function value of the interim rule。 Y with respect to this direction of optimization。

 W downstairs。So again， this is just by definition， F times phi is equal to W。

So call this where we ended up star star。嗯。Now。Let's look at the first one。 right。

 Suppose we wanted to make star as big as possible。O。

And we get to choose whatever allocation rule we want。Well。

 this is the same thing we did way back when we were studying Myerson's theory。

So basically we were studying expected revenue， it was really hard to think about because you can say if you raise a reserve price。

 you'll do better sometimes you'll do worse other times it was hard to think about the prices directly。

 but then when we passed a virtual evaluations， it was trivial to maximize the expected virtual surplus。

 you just maximize it pointwise。Okay， so whenever evaluation profile shows up。

 you just pick the feasible allocation with the biggest some of the virtual values。

 We' exactly the same situation here。 Okay， so this is an average over evaluation profiles。

But I can choose the allocation rules， I can choose its output。

 its behavior on each valuation profile totally separately。Okay， so for each fixed V。Okay。

 this is just a constant。 So for each fixed V。I just look at what's in the parentheses。

And I just pick。The feasible allocation， whatever that may be， whatever the feasible set may be。

 I picked the feasible allocation that makes what's in the parentheses as big as possible。Okay。

 so like if it was unit demand bidders， I would just delete all of the negative virtual values。

 delete all the negative fees and find a max weight matching on what's left。

 or Id just find a max weight matching。So if I want to maximize star。

The obviousSo if I want to maximize star over allocation rules， the obvious thing to do。

 obviously the optimal thing to do is to just pick the virtual welfare maximizing outcome。

Outcome by outcome， Okay， also known。As the virtual welfare maximization allocation rule with respect to feet。

So notes。Can maximize。Star。Point wise。Using the virtual welfare maximization。O。So call this X star。

So the allocation rule X star maximizes virtual welfare over all possible allocation rules。

 just because it doesnt point wise， can't do better。Alright， but。By virtue。

Of maximizing this expression of raw allocation rules。

 because of the equality between star and double star were also inadvertently。

In this virtual welfare maximizer， we're inadvertently maximizing this final expression over all reduced forms。

Okay。So remember this。Equivalence holds for every allocation rule， optimalti or not。 Okay。

 so whatever you're doing， optimizing the virtual welfare， you're equally well doing。

 maximizing the W weight of your induced virtual your induced， reduced form。Okay。So。Induced。

Reduced form。Also， it's called this why。Also maximizes double star。Over why。Okay。

But what do we start with， We started with。The vertex Y star， and we chose W。

 so that Y star is the unique maximizer of that objective。

So it must be that little y equals little y star。They're both optimal them。So since Y star unique。

Y equals y star。And again， X is a virtual welfare maximizer。 So we took an arbitrary corner of Y。

 and I exhibited a virtual welfare maximizer that has that induced reduced form。And again。

 don't forget why we care about this， we care about it because it basically says all reduced forms or comic combinations of reduced forms。

 therefore all allocation rules or comic combinations of virtual welfare maximizers， or sorry。

 all allocation rules。Are equivalent with respect to the reduced form for some distribution of a virtual welfare maximizers。

 Therefore， so are revenue optimal mechanisms。So that's the whole story。Any questions about that？对。

Let me just tell you briefly what I'm not going to talk about。

But which I'm sure you're wondering about， which is computational issues。

But this is just too much to sort of just fit into the。Remaining time of the last class， so。

Let me just sort of mention it。So， there's。So I've been saying that the reason we care about。

 this myerserson theory was twofold。 One was the conceptual structural， One was the computational。

 So now we have an analog of the conceptual structural part。

 We understand what optimal mechanism looked like we understand the sort of added complexity。

 which is necessary and sufficient， moving from single parameter to multipara。

 I've said nothing about the computational perspective。 Okay and and it was perhaps worrisome。

 Even when we were just talking about the additive case and we had these border constraints because the resilience of these constraints。

 So it wasn't clear how you were going to solve that linear program。On the other hand， you know。

 we've been solving a lot of linear programs this quarter where， you know。

 at least one of the two between the variables of the constraints is small and the other is big。

 And that reduced formal LP did have a small set of variables。

 So that's suggestive that perhaps know， we could use our eipsoid magic to actually make some of these things。

 in principle at least polynomial time。😊，All right， so what are the things we'd like to know？

So these are sort of the relevant computational questions， which you should be wondering about。

So given a why， So given an alleged inter allocationloc rule。

 can you in polynomial time figure out whether or not it really is one。 Okay。

 so I've given you kind of a， you know， structural characterization。 I've basically said， you know。

 it it， you know， it is feasible， if and only if it's a convex whole of reduced forms of virtual welfare maximizers。

 right， but that doesn't sound like a computationally efficient statement。

 Okay so that's question one。 So given why。How to check membership。In why。Ie。

Is y in the convex whole？Of reduced forms。Virtual welfare maximizers。嗯。Now， we at the end of the day。

 what we'd really like is we'd really like to sort of compute the revenue maximizing mechanism。

And so the high level idea of how we might approach computing the revenue maximizing mechanism is we'd say。

 okay， well， X， that's way too many variables。 So forget about solving an LP upstairs。

But we have this， at least small number of variables。 So maybe we can at least optimize over y。

 and find the revenue maximizing reduced form， which is feasible。 hopefully。

 right So we have these feasibility constraints， and then we optimize。

And then if we find the optimal reduced form， hopefully we can somehow in a computational efficient way。

 go back and find an X corresponding to that y。Okay。

 so the first thing we need to do is just how to optimize。Over capital Y。

So if I don't worry about how to implement reduced forms and I just want the best one again。

 remember， revenue can be expressed purely in terms of reduced forms。

 so in principle just working with reduced forms should be enough information to figure out what an optimal a is right we just help find the reduced form of the biggest revenue。

Okay， so then if we could solve this problem， too。How do we actually figure out， again， Remember。

 reduced forms are not operational。 Okay， They don't actually tell us how to allocate when evaluation profile shows up on our doorstep。

 So how do we take a y and turn and make it operational and compute some X。So how to reconstruct。

A suitable distribution。Over virtual welfare maximizes。So the good news is we know that。

 whatever the best reduced form is， we know it does have a conceptually simple representation。

 it's a distribution of for virtual welfare maximizers but then there's this question of how do we actually get our grubby little hands on it。

Okay。So。so how do we do this？So it would take me， you know， so the short answer is。

Sort of the silver bullet here to all of these problems， more or less。Is aipoid magic？Okay。

 so our main tool for。Dealing with optimization problems that have exponentially many constraints。

And I do want to emphasize you again I'm not going to tell you the details。

 but you've seen stuff of comparable complexity in this class Okay so when we were talking in particular about the levy swami framework。

 so this was using scaling randomized rounding algorithms to produce MIDR algorithms。

 MIDR mechanisms that had some pretty heavy ellipoid based machinery， and I guess that's probably。

That's close to the complexity of this stuff。 So， you know， if， you know。

 it's the kind of thing where like， I could give another lecture and give you all the details。

 I'm not going to， but just don't be， if you want to learn more， don't be too。

 too scared of too scared of probing further。 it's in the spirit of the kind of stuff we've been talking about。

Alright， so as you'll recall， you know， the key point in the ellipsoid algorithm is， you know。

 you got to implement a separation oracle。And so the really key problem。What things boil down to。

I mean even say for this first problem， just checking membership of an alleged。

Interim allocation rule。So if you give me why？You know。

 which may or may not be a member of capital Y。 I want to figure out whether or not it is。

Does there exist？A weight vector。W。And you think of。

 think of all the entries in w's between minus1 and1， say。So， that。Basically， W transpose y。So。

 these are。I don't think I have that。 basically So the。

 the value of this reduced form in this direction。Is strictly bigger。Then the max。Virtual welfare。

With respect to FiIJ VI defined as before。好山。So let me tell you why this is a relevant subproblem。

So the connection is the following。So。I just erased what this is about。So suppose there was a why。

 So you came up and you showed me a little Y。 Okay so in alleged， reduced form。

 an alleged inter allocationloc rule。And I wanted to prove that you're lying。

 so I wanted to show no way。 so it was like one of the Sudoku puzzles。

 I want to do the same kind of thing。So one way I could prove that there's no way that your rule is legit that it belongs to capital Y is I could find a weight vector W。

 Okay so again， this is all downstairs。 This is all in the reduced form space。Well。

 I find a weight vector little W where。The objective function value。Of your reduced form。

Is bigger than the objective function value obtained by any reduced form of any virtual welfare maximizer。

Okay， so let's recall the proof we just did。 So what we just said is that every corner of the polytope。

Of the， of the Pto downstairs。So all the corners of the downstairs polytope are reduced forms of virtual welfare maximizers。

 So that means， you know， whatever direction， whatever W you optimize linearly downstairs。

 you're not going to do better than you're not going to do strictly better than every single reduced form of virtual welfare maximizer。

 right because the corners for every for every direction， a corner is going to be optimal。

 And the corners are exactly corresponding to these virtual welfare maximizers。

So if you show me a why and I exhibit a direction where your why actually outperforms every single virtual welfare maximizer。

 you're outperforming every corner of the polytope so you cannot be in the polytope。

 your Y cannot be in the polytope， okay？So what this subprom is trying to do is trying to find a certificate of nonmebership of little Y and capital Y。

 Okay So those are the kinds of problems that show up as subroutines of separation oracles when you apply ellipsoid magic。

 Now， I'm not expecting you to see immediately， you know， how this gets plugged into here。

 I'm just saying， you know， given your vague memory of the other ellsoid arguments that we did。

 And given the kinds of problems that we're solving here。

 this feels like the kind of thing that would be likely to pop up and it does。

 Okay that's of all I want you to appreciate。And the reason I mentioned this。

Is because if you want to solve okay， so there's definitely some work， going from。

 solving this to solving these， but it can be done。But what I want to sort of point out is that。

Even to verify that this was true。For a fixed W。If you want to do that in a computationally efficient way。

 you need to be able to maximize the virtual welfare with respect to some fee。Okay。

 so forget about the even harder problem with sort of searching for a W that has this property。 Okay。

 supposeupp I handed you a W on a silver platter。 And I said， this W certifies this in feasibility。

 And you just have to check it。So even to check that a given weight vector W works satisfies the strict inequality。

 you have to compute the right hand side。Okay。So what I'm saying is。

There's no hope solving these three questions in polynomial time。 unless at the very least。

 we can solve the welfare maximization problem in polynomial time。 Okay。

 that's the point I'm trying to make。So necessary condition。Can max welfare？In polyth。对。

So that's given this approach of using this structural thing to find。

this is not saying you're possible。 You're right。 You're right。 You're right。

 We're saying like maybe we could do it if we totally different way。 We're saying given this method。

 you're absolutely right。 So in fact， you can， So it's excellent。

 So the point is that I'm only showing you an obstruction to this proof approach。

 I'm not showing that fundamentally， revenue maximization is harder。 although that is known。

 So you can prove in some sense that irrespec your algorithmic approach you can reduce just in the usual computational problem sense of the word。

 welfare maximization or revenue maximization。Yeah。

 but it's an excellent objection and the complexity of wellner vaccination is relative to the valuation。

Yeah， or the or the allocation constraints， which are related， right So I mean。

 so that so in that's what's a little bit different about this formalism than the rest of the stuff we've been talking about。

 Normally， we've thought of the complexity is sort of built into the valuations here。

 there's this weird thing where， I mean， I mean， we used addivity of the valuations when reasoning about this reduced formalpy about just being sort of a faithful model pretty heavily。

 And so at least I mean， again， there's been sort of advances since。 But at least for this setup。

 this way that we're going about it， you need the additive structure。

 And so then valuation complexity kind of gets translated to allocation complexity when you sort of shoehorn your evaluation class into some weird additive subject to constraints kind of model。

嗯。So。I mean， you can certainly imagine， right。 But so the point is the wellfront access problem need not always be tractable。

 I mean， it's easy to come up with cases where either because of the valuations you started with or just because of p S constraints and the allocation。

You know， like， like。Yeah， so I mean， if you wanted to try to。Yeah， so so， you know。

 it may or may not be tractable welfare maximization， but the claim， which again to haven't proved。

 I've only been trying to give you some intuition for why welfare maximization is necessary。

But it's true that it is necessary。 And it's also more or less true。

 And that's the content of the paper that it's sufficient。Okay， so again。

 this there's fine print here， which I'm not going to get into， but。So theorem。Also more or less。

Sufficient。Okay。So given as a black box， an algorithm that maximizes welfare with respect to arbitrary coefficients。

 and then applying ellipoid magic， you actually can in principle polynomial time way solve all of these problems。

服。Any there any questions about that。All right。So in the fall， I did a top 10 list。

Which I thought worked pretty well， actually， because， I mean。

 one of the things about these classes is you kind of at the end。

 you kind of forget all the stuff you learned。 And， you know， like。😊，know like you still know it。

 but it helps to be jogged the memory and just being like， oh yeah。

 either that was cool or I can't believe I thought that was hard at the time or whatever。

 So but unlike last quote， I didn't prepare one in advance。 So we can just sort of wing it。

 But do any of you have anything you want to make sure is' on the top 10 list。😊，I soy magic。

 soy magic， all right。给我。Anying else？我我。um。Yeah。Soipoid magic。WE exists， if and only if。

LP relax is exact， yep。Yep， exactly。The way you can get E pretty easily Yeah。

 the black loss reduction， yeah。Yeah，By a fractional matchings。All encountering。Oh okay。Take limits。

Okay， cool， cool。実回。Yeah。 let me just wrap up by sort of reminding you of the overarching course narrative。

 I mean， there was one， believe it or not。 let me just sort I know like you know on a lecture lecture basis can be hard to keep track of so。

Allright， so where did we start， So we started with really easy cases。 so in particular， week one。

 we focused a lot on unit demand valuations， which showed up again today。

In the connection of bipartid matching， we covered the Crawford Noer auction。

 So this was this ascending auction where in each round。

 each bidder picks its utility maximizing good at the current prices and bumps up the prices by epsilon。

 we had a really quite nontrivial proof that that auction had some killer properties。

 So in the unit demand case， we introduced more in equilibrium。

 And we had this great convergence between the smallest well and equilibrium and VCG prices。

 that was sort of the magic of unit demand valuations。

 And that was the limit more or less of where we had that property。

 And so what that meant was is we had this really simple ascending a。

 And by virtue of a converging of the smallest well and equilibrium。

 it actually was an ascending implementation of the VCG mechanism。

 So that gave us like an exp post and Senate compatibility guarantee。😊，So then we did the。

Kelso Crawford auction， which I thought was cool for a number of reasons that showed up a few different times。

 So that was the extension of the unit demand one to more general general valuations。

 So that was how we motivated the idea of gross substitutes。

 although we later understood gross substitutes from many different angles， initially。

 it was just proposed that the definition under which Kelso Crawford would work by work， I mean。

 converge and equilibriumlib Again， assuming without justification sincere bidding。

 And then a couple lectures later， we said， well， what if there's no sincere bidding。

 what if we didn't have gross substitutes and we had a nice two approximation algorithm from it for even for submodular valuations。

We studied those of you who went into the bonus lecture we studied how gross substitutes can be characterized algorithmically。

 theyre exactly evaluations where demand oracle reduces to eval oracle。

 which was sort of some very nice comm optimization arguments then so so that was sort of part one ascending a。

 epic implementations， easy cases So part two is Dc and know with the problem unlike in 364 a where I gave you this curated selection of solvable problems for Dig mechanismchan design。

 here we really kind of confronted know we stared into the abyss basically for Dig mechanism design。

 So we were super hard to get you know basically state of the art tractability results So know one really powerful one which was cool was when we had a logar and copy copies of every item whatever the valuations we were able to at a one plus epsilon that was using the levy swami scaling algorithms technique and that was some of the harder linear programming machinery that we ever used but we got a one plus epsilon。

In a pretty general setting。The other thing we did was this special case of sub modular functions。

 coverage valuation functions where we used a convex program within this strange randomized rounding where you actually will sometimes throw away goods just to recover convexity of the objective function。

 but that gives us a 63% welfare approximation， which is the best possible swimming pen equal to NP for coverage valuations。

So then we said， whoa， the mechanism design is really hard。 So when we can do it。

 the mechanisms are super complex and a lot of the times we can't do it at all。

 So let's weaken the incentive guarantee and see what happens。

 And so when we went to Bayes Nash equilibriumus good stuff immediately started happening。

 There is the mentioned highlights where you have these very general black box reductions。

 you show me an approximation algorithm， I'll show you a BicC mechanism， which is just as good。

 the only catch is that the running time blows up to depend on the size of the type spaces。

 but not in the same sense as we have in this lecture。

 So the sum of the cardinalities of the type spaces is your new running time dependence。

 But you preserve the alpha approximation algorithm， whatever it was。So then we moved on to part4。

 So that was what's currently， I think one of the hottest topics inic mechanism design。

 which is you know take a complex environment like comml auctions。

 What if you just throw something super simple to sell stuff on ebay and we saw I guess two things。

 So first of all， lots of really simple a formats have surprisingly good equilibrium guarantees really equilibrium guarantees that are in most cases match or almost match the best known polynomial time algorithms for the underlying welfare maximization problem and moreover。

 there's this very systematic way of doing these proofs in the same sense the price of anarchy proofs last quarter could be made systematic。

 So the notion of smoothness we saw last quarter reappeared today。

 we had extension theorems this time for Bayes Nash equilibrium a couple flavors and we also had composition theorems。

 So at one point we even reduced analyzing bayes Nash equilibrium of a bunch of first price auctions to just analyzing the pure equilibrium of a single item first price auction。

 which was a pretty great reduction。And improve complexity。

So then when we kind of mastered all that pricey energy of simple auction stuff that LED us to the current topic。

 revenue maximization。 again， the main thing this has in common with the previous ones is that this is totally cutting edge stuff。

 Again， just what we talked about today is less than a couple years old。

 very much still what what a lot of people are thinking about trying to understand this stuff better。

 We certainly saw the challenge we have these crazy examples with just one buyer and two items。

 optimal mechanisms can be weird。 But at least as we saw today。

 we can get some grip on them using linear programming。

 there's even a multiparameter analog of myson's theorem。

 Op auctions or distributions of virtual welfare maximizes。 So that's the recap。And believe it。

 believe it or not， you guys are now。 if you， if you sort of absorbed this course。 I mean。

 you're amongst like the top 50 experts in the world in this stuff。

 I don't know if that's what you wanted when you started， but whether you want it or not。

 that's where， that's where you've derived。 So I'll stop there， thanks。

