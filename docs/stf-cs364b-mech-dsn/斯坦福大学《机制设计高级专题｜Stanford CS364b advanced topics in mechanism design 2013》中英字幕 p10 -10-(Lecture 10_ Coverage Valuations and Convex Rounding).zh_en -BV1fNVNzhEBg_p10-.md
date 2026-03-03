# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p10 -10-(Lecture 10_ Coverage Valuations and Convex Rounding).zh_en -BV1fNVNzhEBg_p10-

Last lecture， I made something sound more complicated than it was。

 so I apologize for you if just like a couple more minutes about this。

So it was the part where I was talking about， you know how does the separation oracle work So we're applying the ellsoid algorithm to this dual linear system and at the end of the day。

 we know we're going to actually prove that this is infeasible。

 but it's the part of the proof where we're trying to argue we're trying to implement the separation oracle。

 So the first thing I said was was correct， which is just this last constraint。 Okay。

 so remember the okay， let's remember what everything is right。

 so at the very beginning right long ago， there are these real valuations that you care about the Vs。

You solved the linear probing relaxation for welfare maximization for the real evaluations of the Vs。

 Y star was the best fractional solution for the original ones of the Vs。

 and for the rest of the proof， you're just taking the Y stars as targets。 you know。

 just as fixed given constants。 And so in this dual system。

 the Z's are what are the decision variables。😊，So you check this last constraint。

And then if obviously this is violated， you can go ahead and return that。And then the claim is。

 if this last constraint is not violated， well， then actually。

 it's super easy to generate a violated constraint from this family。Okay。

 so that's that's the step that I made it sound way more complicated than it is。 So， you know。

 to first order， here's how it would work。 This is assumes you know。

 you're okay with like a randomized solution。 So suppose this passes。 This passes the test。

 This is actually true。So now what do you do， you just run randomized rounding from last week。

 meaning you know you scale down by a small factor， one nicepslu factor。

 and you apply that to y star。 now， semantically what we're doing is very strange because know Y star this is an optimal fractional solution for the Vs。

 The real valuations。 right now， we have these totally fictitious suit evaluations， these Zs。

 and it's not clear that know if you actually reved an LP for the Zs。

 you probably get something totally different。 you wouldn't get y star。 Again。

 Y star was optimized for for the Vs。 But nevertheless， if you want。

 you can still apply randomized rounding that any feasible LP solution。 Y star is one of them。

 So go ahead and do that And what we know is that if you apply randomized rounding to a feasible LP solution。

 you get an integer solution， which is almost as good。 that's the we proved。

So if this constraint is satisfied， it means you have a fractional solution， Y star， which for thes。

 these suit evaluations to ZI's is good， it's bigger than z star。If you do randomized round。

 you're only going to lose a 1 minus epsilon。 and you're gonna to get an integer solution。

And that's going to， in fact， be an allocation， an energy solution， which violates this constraint。

Okay。I mean， think about dividing the 1 minus epsilon here。 Okay。

 so this fractional solution is way better than Z star。

 It's better than Z star divided by one of Epsilon。 You randomize round， you get energy solution。

 which is still strictly better than Z star that violates this。

 So you just return that as your separation oracle。 Okay， and that's it。

That's the whole separation or implementation。Okay， so we don't actually' don't you know。

 what we need from last week is just the simple idea that randomized rounding scaled down slightly does almost as good as the expectation。

 That's kind of the only thing we're using。So any questions about that。

 I hope that's sort of cleared up that point。Okay。All right， so。

So now for for basically have a culmination of part 2。

Im want to circle all the way back to where we started。Which was submodular evaluations。

So just to remind you。You know， at the time， we had just sort of finished our victory lap with all the tractable special cases。

 We' sort of knocked off gross substitutes。 We'd seen we could you know implement the VCG mechanism and so on。

And we went what seemed like just a very small step beyond gross substitutes。So we have a set U。

Of items， not identical。And。Each VI is sub modular。

And this is just sort of a set theoretic version of diminishing returns， your value for something。

 your marginal value for something is going down， the more stuff you have。 So the more you have。

 the less you want more stuff。嗯。Okay， so if I look at how much？Extra value， J gives me。

That's less for the bigger sets。Then for the smaller set。And。Okay， so。

 but we saw already here welfare and maximization is NP hard。

 So that that was sort of the can worms we opened when we passed from gross substitute to submodular。

We also showed that。You know， it's just an approximation problem。

 Well from exposition is not that bad。 All you do is run the Kelso Crawford auction。

 and that already gives you a one half approximation again those other one half approximations as well。

And then we asked the question， okay well how can we get a good approximation and also get DI and I've given you no answers to that instead we took these detours to multiunit auctions and to these things with multiple copies and we've developed our toolbox and so now in particular we understand MIDR mechanisms and we're going apply that to solve at least a special case of scenario number six so no full blownown solution to scenario number six exists or not as known and I'll tell you probably a little bit tomorrow about the sense in which we think there isn't any for the full class of someular evaluations。

But。Here's the special case that we'll be able to solve。

So this is a subclass of submodular evaluations called coverage valuations。And so。

So a given valuation VI is coverage if it has the following form。So for a bitter eye。

 there's going to be some ground set。So you can think of this as being you know cities or something like that。

 and for each item， there corresponds a subset。Okay。So these are going to be AIJs。And by definition。

The valuation of a bidder。Is going to be the area covered by the sets correspond to the items that it's given。

Yeah。So let me give you a couple examples。So one thing is you could imagine that XI are a bunch of cities。

 maybe cities in the US。And items are， you， licenses to， you broadcast something or you know。

 permission to do something else。 And so AI J could be the set of cities that a particular license enables you to reach。

Okay， and your goal is to have coverage， if you like， of as many cities as possible。 Okay。

 so you can think of these AI Js as broadcast radio。Okay。

 and so it doesn't do you any good if you have two different， you know。

 you have permission in two different ways to broadcast to the same city， it only counts once。Okay。

 so given a bunch of licenses， you look at the union of everybody you can reach and that's what you get credit for。

 that's your value。Or if you prefer， you know， maybe you're a firm。

 an X I is a number of skills you're trying to hire。

 know or maybe you're a sports team and those are you know positions that you need to fill and you know And so then basically these AIJs are going to correspond it' to explain the skills of a particular worker so a worker maybe can do multiple skills they cover multiple needs and maybe you don't need more than one worker for the same thing。

 So you get credit for the union。So that's how you should think about coverage valuations。

It's pretty easy to see that every coverage valuation is， in fact。Submodular。So basically。

 you know what's the added value of a new person， Well。

 it's just the things in XI that you cover that were not covered before you got there and so the more other stuff there was。

 the less new things you cover， so the less your marginal value。

 the bigger the set of other people that are already there。So subset。Of submodular evaluations。

Now you whenever you pass to a special case， you should of course argue， well， I mean。

 but thiss even still a hard problem now， maybe this is now a subset of gross substitutes or something like that and we already know how to solve it。

But in fact， welfare maximization is actually still hard。Okay， even for coverage valuations。

So here's the best impossibility result known for approximating welfare with coverage valuations。

So there's no polynomial time approximation。For welfare maximization。Better than1 minus1 over e。

Which is roughly 63%。Okay。So I'm going assume， So what's true in this negative result。

 I'm gonna assume for the positive result is that the input is just given explicitly。 Okay。

 so I just literally like tell you what my AI Js are。 Okay， and then that's， that's the valuation。

 And I'm going tell you an AI J if by just like listing the elements in the AI J。

So assume the AI J is。Provided as explicit input。Okay。So I mean。

 this certainly says it's not part of gross substitutes。

 or at least assuming P is different than NP it's not part of gross substitutes because that we can solve in polynomial time。

Okay， so it's still you， it's a subcast of some modular which still motivates everything we've been talking about。

 which is when wealth harm maxization is empty hard， what do you do？

How do you get these approximation mechanisms？And so the point of this lecture。

So this is a result by a couple former PhD students of mine， Shaugmi in Chi Chi Yan。

Is that using an MIDR mechanism enhance a D mechanism。That gets matching approximation guarantee。

Okay。1 minus1 over3。For coverage valuations。Okay。And so again， this is sort of the you know。

 happy case where， first of all， you know， So this says， So notice this， this in proximity result。

 this is nothing about incentives。 right， This just says， forget incentives。

 Just polynomial time algorithms can't do better than 63%。

So we're doing as well as any polynomial time algorithm incentives are not。

 that's the first piece of good news。 the second piece of good news is that you know as approximation algorithms go。

 63% is a pretty good number okay there's a lot of problems or you can't get this close to 100% in the worst case。

So again， there's not tons of positive results in the DC approximation world， but this is。

Another interesting one。Do you was something about the complexity website。Well， I mean， not perchet。

 because I'm just assuming it's part of the input。So， you know， if Xi is big， I mean。

 you're forced to write it down and I'm allowed to be poly。 in effect。

 the algorithm is allowed to be polynomial in the size of the Xi， whatever that may be。

It's a good question， no。Yeah， I don't think so。 I see so。

You so maybe with an exponential ground set you're thinking that I haven't thought about。

What do you think。星期。Yeah， maybe with exponential。Maybe you need X。Yeah。

 maybe with an exponential size ground set。I， I haven't thought about that， actually， the of the。

Well， the claim is it's polynomial in the size of the input。

 where the input is defined to be the AIJs， which are explicit lists。Yeah， so in that sense。

 it's kind of， it has a pseudo polynomial flavor in that sense。 But I mean。

 that's another reason why sort of this is important。 I mean， I mean， this is already you know。

 so this， this hardness result is for this version of the problem。Yeah。So， you know。

 in the hard instances here， of course， the Xs aren't going to be ridiculously big。 You know。

 it's not going to be some。It's going to be a reasonable encoding of things。Yeah。Yeah， I。

 I have to think about that， whether given kind of unbounded。

Seets you can encode what you can encode。 It's a good question。O。Right，And I should say。

 so in particular， you'll notice this is a1 minus one over approximation algorithm。

RightSo I haven't even even forgetting incentives， actually I haven't told you a positive result this good。

 I've told you a one half approximation a 50% approximation for a general submodular functions。

 but there were， I mean， not， you know， so in 2006， there was a 1 minus1 over re approximation。

 nond for coverage。 And then in 2008， theres 1 minus1 over e for general submodular functions。

 So prior to this， it was known you could get this without incentives。 Not a lot prior to this。

 but prior to this， it was known you could get this。

 It was clear that this would be the holy grail for an approximation mechanism。Okay。

 any other questions。Alright， so we're going to， we're going to， it's going to be an M DR mechanism。

 but we're gonna have to， you know， it's not going to be one of these scaling algorithms。

 It's not going to be a special case of the， of the Levy Swmi framework。

So let me just comment on why do we need to do something different？So there's a few reasons。

 actually， but let me tell you the main reason。So suppose again so what was the idea in let me swamami the idea in last lecture was know okay you give me an approximation algorithm which I can't lift into a mechanism。

 but then I'll somehow smooth the approximation error over all of the inputs so that without any loss so that I can get the incentives So I'm telling you that for this problem there are these good approximation algorithms I get 50% or 63% or whatever So why maybe we can just again do the same thing where we saw an LP and we smooth that error over everything and then we're good to go so why can't we do that。

Okay， so let's suppose is a hypothesis that I gave you an algorithm which let's just let's say for every submodular evaluation function got a good approximation。

 let's say got 50% for every submodular evaluation like Kelsso Crawford， and that's the guarantee。

Here's the problem。Okay。So in Levi Swwami， where did we actually use the existence of a good approximation algorithm。

 Okay， so it didn't show up until buried inside the separation oracle that we used to improving the infeasibility of the duel。

Here， so we used it to say， oh， well， you know， if we have this solution with good fractional pseudo welfare。

 we'll invoke our approximation algorithm to get an image allocation with almost as good pseudo welfare。

Here's the problem。So what？So what instance do we invoke the algorithm on。

 we invoke it on the instance thinking of the ZISs as valuations。And the problem is。

 we have no control at all over what these ZISs are。 Okay。

 remember we're just running the ellipsoid algorithm。

 and it's just sort of generating these ZISs for us。 It's like， here， deal with this， here。

 deal with this。 And we're having to sort of par these ZISes by feeding back violated inequalities。

 These I， these ZISs。 they're not going to be sub modular。 they need not even be monotone。

 They can be anything。So just having an algorithm which does well for submodular evaluations。

 which are the evaluations we care about the VISs， totally useless once we're faced with these arbitrary VISs that the ellipsoid algorithm gives to us。

Okay， so it really doesn't seem to help having a good approximation algorithm for subclasses of valuations in this levy swami framework。

 you really seem to need general valuations because the ZISs could be anything。

Let me just write that。So ZIS is in D2。Could be anything。Okay。So approximation algorithm。

For special cases。Not directly useful。So full disclosure。

 there's some other kinds of incomparilbilities or you know。

 reasons why this particular problem doesn't fit into their framework。For the levy swaami result。

 they need valuations that support demand queries。 The reason they need demand queries is in the very first step。

 So what they start， they start by solving the LP relaxation to get this fractional allocation。

 maximizing the welfare over a fractional solutions。 there， the separation oracle is a demand oracle。

 turns out it's actually not hard to prove reduction from set cover。

 If I give you a coverage valuation。 It's actually n hard to answer a demand query。

So way back when I started talking about queries， I said。

 you know value queries pretty uncontroversial， right you got to tell me what your value was first a set seems like a minimal  query demandman queries。

 we said， well， you know I said that sort of the mathematical results are more mixed and you know and it's more that it's natural to ask for demand queries。

 So here's the first here's a concrete example where the mathematics are mixed for demand queries。

 It's a pretty natural valuation class for which answering what is MP hard。Okay。

 so that's another reason why levi smi doesn't apply here because these don't support those in polynomial time。

That said， a value query for a coverage valuation is easy。

 you just enumerate through the X's and just check which of the X's are contained in one of the given sets。

 okay？All right。Ch。Okay。So the upshot is， all right， so levitomy doesn't seem to work。

 least just not clear how to use it。You know， but we still so we want to do some MIDR mechanism。

 and still if you think about， you know， as far as all the algorithms in the world。

 which one seem like the MI yield MIDR mechanisms still seems like randomized rounding is kind of the closest to it。

 again because you're doing this optimization over these fractional solutions and the randomized rounding generates these distributions。

 It kind of feels like on the right track。So， you know， but we need to go beyond scaling algorithms。

 Okay， if you restrict yourself to scaling algorithms， it feels like you're basically you know。

You know it really is this Levy Swwae framework， it's hard to see。

 they seem like more or less the same thing。So the big question then is， you know。

 what else could we do other than a scaling algorithm get and get a MI I DR randomized rounduting algorithm。

 That's kind of the conceptual hurdle。 we have to climb over。So question。How to go。

Beyond scaling algorithms。So let me just remind you sort of the blueprint。That I had in mind。

So the way we're thinking about it is the VIs are fed as input to some LP solver。

The LP solver generates。The best fractional solution， Y star for the given input the Vs。

 this is the input into a rounding algorithm， an oblivious rounding algorithm。Or。

And then that generates some distribution。Over allocations。And scaling algorithms were by design。

So that optimizing over the output of the rounding algorithm。

Optimizing over the distributions was exactly the same problem as optimizing over the input to the running algorithm。

 optimizing over the LP solutions。And so the challenge， but differently。Is that， you know。

 for most rounding algorithms。So like I said， M I D R is not the kind of property you ever get accidentally。

 if you're not designing for it， you're not going to get it。 So for most R。

 it's just not going to be the case。As we talked about last lecture。That the optimal y。

Where this is over the LP solutions corresponds to the optimal。

R of Y scalinging algorithms has this property。Most drowning algorithms will not。

So I think it's not even clear， I really don't have any ideas how you would ensuresure this property other than through scaling algorithms。

So we need a different idea。Okay， so here's this sort of crazy idea。Oh。And it's kind of motivated。

the idea okay， so we want an algorithm with a bunch of properties。

 right so we know we're thinking MIDR because that's about the most powerful class of mechanisms we know。

We wanted to be have random polynomial time。 We want to have a good approximation factor。

 Okay And so what we've been doing is we're saying， well。

 we know how to get polynomial time and a good approximation factors。

 So let's try to sort of tack on MD R somehow。 Okay And that very successfully LED us to the scaling algorithm idea。

 which is great。 But so now we're kind of stuck。 right So now let's actually go back and ask， well。😊。

You know is there some alternative approach where you MIDR is the property that seems really hard to get。

 like the hardest to get？So can we have some high level approach that would guarantee the MIDR property？

And then we can sort of investigate， you know， what are the conditions。

 extra conditions do we need to recover polynomial time in good approximation Okay so let's shift our focus rather than thinking of MIDR as an add on to the algorithms we already have。

 Let's actually take that as the initial constraint and then go from there and that'll lead us to think about a very different or somewhat different kind of algorithm。

So how can you what would it look like， so what could we do that like by definition would give us MIDR？

So here's what we could do， okay？So the idea is instead of optimizing。

 as we've been doing all along over the LP solutions。

 instead of optimizing over the input to the rounding algorithm。

Let's optimize directly on the output of the rounding algorithm。And again， for a scaling algorithm。

 those are the same thing。For a noncal algorithm， these are different things。

 So instead of optimizing over these。These are still going to be our decision variables。

 but let's optimize over this objective function。So here's what I mean。

So let's see if we could directly solve。Okay， so here's what we have。

 So we're still maximizing some notion of welfare。 We still have some same decision variables as before。

 So it is still going to be subject to why feasible。For some LP。But instead of up here writing。

 as I've always been doing， you know， some over I， some over S， Y I S， V I S。

 I'm going write something different。 I'm going write。

 let's actually just sort of look ahead to the expected welfare we're gonna get from the rounding algorithm if we feed in Y as input。

So in other words。I don' want to write this。 I want to write this like this。 So expected value。

So for agiven choice of why。There's some corresponding distribution R of Y over allocations。

This is just a random allocation from the distribution。

 I this is just the output of the rounding algorithm if you feed it input Y。

And I just look at the expected welfare。Okay。So relative to before。

 basically what I change is the objective function。And again。

 rather than measuring the quality of an LP solution y。Bye。The usual linear objective function。

 I'm measuring the quality of a solution wide of these constraints by how good is the resulting random allocation after I apply the randomized algorithm R to it。

So again， the point is to optimize directly over the output of capital R， not over the input。

Another thing to notice so this optimization is only defined with respect to a rounding algorithm capital R。

 So you should think of capital R is fixed so we fix some algorithm that takes a linear programming solution and somehow generates randomly in allocation。

 R is fixed， then this optimization problem at at least it's well defined to write it down。Okay。

 so in effect。Optimize over the outputs。Rather than the inputs。Okay。And so， you know， I told you。

 the， the only reason you'd ever come up with this is， you know， if you were， you know。

 trying to guarantee some very， you know， challenging property like MIDR。 So the whole point。

 the whole reason， you know， we thought about this is this gives you MIDR。By definition。Okay， so if。

So in other words， consider the allocation rule， which solves this optimization problem。

 thereby computing a Y， a Y star， and then apply the rounding algorithm capital R to it。

 so therefore randomly output puttinging an allocation。So the claim is that allocation rule is MIDR。

 for sure。Why， well， so what's the range of this rule。So the range of this rule is just。

All output distributions of the rounding algorithm。For solutions that meet the LP constraints。Okay。

So the range is just， you imagine any input to the rounding algorithm。

 imagine the corresponding distribution and the objective function literally says pick the best of those distributions to maximize expected welfare okay so really the definition of this objective function。

Means it's an MIDR allocation。Okay。嗯。So。Not clear this is， sort of a crazy idea。

Let me just point out that you know， if all right， so like I said。

 this optimization problem is defined with respect to a rounding algorithm R。

So let me just point out if R happens to be a scaling algorithm， then actually。

 this is a very normal optimization problem。 and in fact。

 this is sort of one way you can sort of interpret the last the previous lecture。 Okay。

 so scaling algorithms are the ones where this problem becomes a linear program。

So if R is alpha scaling。Then， the objective。So if R is a scaling algorithm， then this would just be。

 this is always just the expected welfare， but if it's scaling algorithm。

 you know the expected welfare is just alpha times the LP solution value。

So the objective would just be equal to alpha。Okay。And this was just our computation before。

 so when we first introduced alpha scaling algorithms， we noticed that given an LP solution Y。

 the expected well for the energy allocation is the same scaled by an alpha factor so that's just we're plugging in that computation here。

 This you'll notice is linear， I should be just a y。This is linear in the decision variables。

 the wise， Okay， so this would just be a linear program if capital R is a scaling algorithm。

So at least it captures the special case that we successfully last on。So the hope then， again。

 So and remember， the whole point here is， how do we go beyond scaling algorithms subject to M IDR。

 Okay， so this， at least， is sort of now like a concrete proposal。So we can say， okay。

 here's an optimization problem， no matter what capital R is， it's MIDR。

So now what we want is we want say， for what rounding algorithms can we solve this in polynomial time？

 and get a good approximation。If it's a scaling algorithm， we can solve it in polynomial time。

Is there anything else where you can solve this in polynomial time？Well， the first question will be。

 is there anything else for which this is linear and that you it seems like that's basically only scaling algorithms。

 but we can actually， we can solve nonlinear some nonlinear programs in polynomial time as well。

Right。If this is a concave function。And why。Then it's still a tractable problem。

 right so concave maximization so it to linear constraints， that's something we can do。

So a pathway to go beyond scaling algorithms is to say for which rounding algorithms are is this objective function concave and the decision variable is Y。

Okay， so hope。Is that this optimization problem？Remains tractable。For some non scalar。Rs， of course。

 also hoping R gives us a good approximation。Yijii。If objective function is concacate。Okay。So that's。

 that's that's sort of the， that's the dream， okay。2。

So where I want you to be is I want you to agree that if star is tractable。

 then we have an MIDR mechanism， namely， you solve it。You get the Y。

 you apply the rounding algorithm， capital R to it。 Okay， that's an MID allocation rule。

So what you should be wondering is， are there any interesting non scale capital Rs？All right。

 so let me show you a rounding algorithm。A capital R， which doesn't work。

But it will be very instructive in the way it doesn't work。

And I guess just to say for what I've said up till now， this also has nothing to do with evaluations。

Okay， so it's just always true that this will be MID are， whatever the valuations。

 whatever the rounding algorithm capital are。 So really what we're going to eventually come up with is're going to come up with joint assumptions on first of all。

 the valuations， namely the assumption that their coverage valuations。

 And then also we're going to judiciously choice to choose this rounding algorithm capital are so that we do get concavity and a good approximation case that's what's eventually going to happen。

All right。So non example。All right， so if you so I'm going use a simpler linear program than we've been using so far。

 Okay， and that's sort of well motivated because， you know。

 if I want to prove that the objective function is concave and the decision variables， kind of the。

 you know。The fewer decision variables I have， the better。So， I'm going to switch。

So the linear programming constraints will be very simple。

 There'll just be a Y I J for a bitter I getting an item J。

 And we're just going to say that no item can be allocated more than once。 That'll be it。Okay。

So Y Ij9 negative？For all I J。And then also。Each get allocated at most once。So this is， this is。

 we haven't really seen something this simple since the unit demand days。 And actually。

 this is even simpler because I've dropped the constraint that every bidder gets at most one good because they're not unit demand。

 So that wouldn't make sense， okay。So， our。Set of decision variables and the constraints are are going to be simple。

 Okay， so that's nice。Now， consider the following rounding algorithm R。Okay。

 we're just going to do the simplest randomized rounding imaginable。

 because remember a rounding algorithm， it just takes as input some ys。

 and it outputs randomly in allocation。So if you give me YIJs that satisfy these properties。

It's going to randomized round it。 Okay，' at each item J independently。

 I'll think of the Y I Js as a probability distribution。 and Y I J gets J with probability Y， sorry。

 I gets J with probability Y I J。Any leftover probability， if this was less than one。

 it just goes to nobody。So， independently。For each good J。A son Jay。

According to the probability distribution。Induced by the bidders。Again， leftover probability。

 it just winds up unassigned。O。So this is a particular proposal for capital R。

 We're going to assume that there are coverage valuations。

And what I want to investigate is whether or not。Our objective function。

The expected welfare after the rounding algorithm， after that rounding algorithm。

 whether or not that expected welfare is concave and those decision variables the wise。All right。So。

Just a preliminary observation， sort of a sanity check。If you think about it for a second。

This could never work。By which I mean there's no way that this rounding algorithm could give us a concave objective function。

Let me explain why。So notice， this goes back to a comment I made last lecture。

When I was talking about the imperfect analogy， I said， why do MIDR， Why allow distributions， Well。

 maybe it gives distracttractability， like linear programs gives distracttractability。

 But then I pointed out this distinction that linear programs you get sort of extra stuff。

You optimize it and it's easier， but then you get things that are sort of even better than integer solutions。

 But if you're dealing with distributions， you never get something that's better than all the integer solutions。

 because， a distribution is dominated by the best solution and support。

So we're going to see that come up here。So think about this rounding algorithm。

 What if I fed this rounding algorithm capital R， What if I fed it an integer solution， a 0。

1 solution。So like the wise just say， you know， the first item goes to bid 3。

 the second item goes to bid 5。 The third item goes to bid 1。

 What's the rounding hour I'm going to do。It'Just going to be like， okay。

 you already know what you want。What do you need me for， right？So R of y is just going to be y。

I'm going to have an abusebuive notation， but basically a 01 vector is a characteristic vector for an allocation。

 and this thing will be a point mass at that allocation。All right。

 so what would it mean to be so now think about being MIDR right So that means so you need to look at all the distributions in your range。

 So this says in particular， every point mass is in the range of this rounding algorithm。

 right You give me an allocation image allocation。 There's a corresponding 01 vector Y。

 If I feed it into R， I get it right back。So every single allocation。

 every point mass is in the range。So if you're going to optimize over this range。

 you have to in particular， optimize over all of the energyteger allocations。

And the whole point was to attack problems for which that's a hard problem using M D R。 Okay。

 so this can't work。 There's no way that a rounding algorithm that leaves integer solutions untouched。

Could possibly be computationally tractable unless B equal is NP。Okay。

 so we know this is doomed to fail。Because the point masses survive in the range。

But it's instructive to still try to prove it Concave， even though we know it's not。

 to see where the concavity proof fails。 It's going to actually lead us quite directly to something else。

 which is concaid。Okay。All right。So again， the point here is。Optimizing over the R of y's。

As hard as the original problem。Okay， so let's try to prove it's concave anyways。All right。

 so is it clear what I'm about to try to do， so we have this space of n times M decision variables。

 Y Ij for every bidder and every item， Okay， so this is kind of the feasible region we're dealing with。

We're looking at this objective function。 so remember what this is。

 this is the expected welfare after the randomized rounding algorithm gets applied to Y。

 So this is some real valued function on the Y's。 and we can ask whether or not this is concave for this particular rounding algorithm or。

Okay。Okay。哎。So prove a ten。All right， so。First observation， So we want to prove this concave。

 some of concave functions is concave。So let's just try to prove this separately for each bitter eye。

 okay， that's sufficient。So enough to show that。Fawi。

So I'm going to abuse notation here a little bit。So you can remember Y it's just these YIJs。

 this is the distribution over allocations that has some set S going to I okay。

So it is just like what bitter oddd gets from the randomized rounding algorithm。

So enough to show that this。Is concave。And why。Okay。Good。

So now using the assumption that the valuations are coverage valuations。

 I can simplify this concavity problem even further。Okay。So let me just remind you。

 so what's the picture you should have。So we have this ground set。

Items correspond to these subsets and valuations are just the union， the area。 I guess actually。

 one comment I forgot to make。 So everything everything in the lecture today extends with no change If these guys have weights also。

 So if these are cities and you want to wait it by population， no problem。 Okay。

 would be extra notation and just no extra complications。

 But just think about the basic case we're looking at the cardinality of the union。Okay。

 so we're looking at the expected value， the expected size of the union。Of the sets that I gets。

So let's just think about it from the perspective of some element。

 So think of it from the perspective of just like San Francisco。

So what's the probability that San Francisco contributes one to this valuation。 Well。

 it's the probability that this guy gets any of the items that include San Francisco in it。Okay。So。

 let's just。Write that out。So since。This is just the union。According to the union。嗯。

We can write this。As a sum over。The ground set X I of the probability that each element in the ground set winds up in that union。

 okay。So some over everything that might contribute to the union。And the probability， where again。

 the probabilities with respect to the coin flips and the rounding algorithm applied to why。

That A winds up。In。く。呃 yeah。Okay。So we use linear of expectation once to say concavity of the welfare just blows down a concavity of each individual bidder and then for an individual bidder。

 we just say， oh well again， you know by this summation。

So we're trying to prove that this whole thing is concave and it's enough。

To just prove that each constituent term。So want this to be concave。In why。Okay。

And this is starting to look like terms that we can really get our， get our hands on。

 I can understand well。 Okay， so sufficient condition for the objective function to be concave and therefore。

 total tractability is that this expression， this probability is a concave function of the variables Y。

All right。So so far， the proof is working。 This is looking great， right。

 Like coverage valuations have been really useful， yeah。😊，Okay。So what is this？

So let's just write this out。So for a given， okay， so we've fixed a bitter eye。

And we've fixed an element A of its ground set X sub I。

 something that might contribute a unit to its value。So as a function of y。

What is the probability that a contributes to I？So remember what this rounding algorithm capital R is。

 It's very simple。 given the Y I Js。 it just says， okay， I gets item J with probability know Y I J。

 That's it。So what's the probability that。Little A contributes one to I's value。 Well。

 how could it not contribute one to I' value。It would have to be that for every single set that every single AI J that contains little A。

 I doesn't get it。O。So this is just one minus the probability that it doesn't get little A。

And so for that to happen for every single set。That contains little A。

 So if you like every single item that covers San Francisco。It has to be that you don't get it。

And that happens with probability。1 minus Yj。So this is exact。So our big high level goal。

 proving this thing concave reduces to proving that this is a concave function of the Y。

Or if you like that， this is a convex function of the Y。Which is not。Okay。So okay， why not？

 So what does concave mean， right， So concave is this way？So chds are underneath the graph。

So it basically means if you think about taking the average of two points or taking the function value。

 if you take the function values first and then you average， that's like the chords。

 so you get something lower， if you average first and then take the function value。

 that's like the graph， that's higher。So， you know， lets look this，' this look at this function。

 So like imagine。Say， you know， you had a Y vector。

Where exactly one of those was a one and the rest were zeroes。So Yj was equal to one for one of them。

 and the rest were zeros。Well， if you have Yj equal to 1， right then？

This whole things going evaluate to one。 The product will be 0。 You'll have one。

But think about averaging two different y vectors， each of which have exactly one。

1 in the rest zeros。 You're going to get a vector that has all zeros， except for  two，1/2s。

And then those halfves are going to multiply and give you a one quarter there。

 And this will give you a three quarters。Okay看。So you averaged two things that had value 1。

 You got something that had functional value  three4。 So it's a violation that can have。All right。So。

 but actually， you know， we got pretty far in this proof and we knew it wasn't going to work in the first place。

So。YouCan we fix it？All right， what does fixing it mean？

Fitzing it means changing the round rounding algorithm capital R。 Okay。

 doing something a little less obvious in the rounding。Okay， so that we get concavity。So， all right。

 so if it weren't， So what would be kind of like the next simplest rounding algorithm we could possibly do。

Well， let's remember that， let's remember the very initial cautionary tale that any rounding algorithm that maps integer solutions just back to themselves is doomed to fail。

Okay。So in particular， you， if you get an LP solution which says Y J equals1， you actually are。

 I mean， you really should not be giving J to I with probability one， you have to do something else。

So like probably the first thing you think about is like， okay。

 well let's just kind of scale down the probabilities a little bit。 Okay。

 let's allocate with probabilities like less than Y IJ。 I don't know what。

 but something smaller than Y IJ。So。Simplest possible fix。So， use。Probabilities。

So let me just parameterize it。And we'll sort of take stock and figure out what we want， okay？

So let's use properties F of Yjs。Instead of Y IJs。By which I mean。

A rounding algorithm will continue to be exactly this one。

Except we're going to replace the Y I Js with some function of Y I J。 Okay。

 think of it as like a scaling down operation， which we know something like that has to be necessary。

Okay。And so， right， good。So if we were going to somehow transform。These YJs scale them down。

 what properties do we want？So what what sort of would be the？Can we sort of think about what F。

Might look like。All right。We're thinking F of Y I J should probably be maybe at most Y IJ。2 reasons。

 One is the 1 I've been harping on， which is， again， we can't just sort of deterministically。

 you know， follow an integer solution。 So that says probably should go down。

 The other thing to remember is we do need sort of a well defined rounding procedure at the end of the day。

 Right， So what we we're using the fact that for a given item J。The sum of the YIJs was the most one。

 so it made sense to say give it to a random bidder according to the YIJs so we better preserve the property that you know the sum of our allocation probabilities is the most one for this to make sense。

 So that's another reason why it seems like F of YIJ might be should only be less than YIJ。That said。

 you know， given that we want an approximation ratio， probably we don't want F Y。

 I J to be too much less。Because maybe we're losing all our value。So let's just say。

 but not too much。In fact。If you think about this argument。

So what did I say at the very beginning of the lecture？Were talking about coverage valuations。

 And I said， wellow， you should be skeptical。 You know， have I made the problem trivial。

 Have I made it too easy。 And then I stated this hardness result， which is actually。

 you can't do better than 1-1 over E for these coverage valuations。

So if you think about combining that fact with this idea that you have to scale down。

 it actually suggests about what f of1 should look like， the fact that you can't do better than 63%。

 it actually means that if I give you an integer solution。

 you better not even always scale everything down just by like 65%。

Because even then you're going to be optimizing better than what the MP hardness says should be possible。

So this is now starting to get a little more of a guess。

But judicious guesshes is an important part of research。So the hardness results。

I guess I would say you just have to kind to keep your eye out for the clues。

 This is what I would say。So the fact that it was hard do within 1 minus1 over e。Says， well， maybe。

So that means in particular， giving integer solutions， we have to lose a 1 minus1 over E。

 And the simplest way to imagine where you kind of lose that welfare is just by scaling down。

So this suggests。That at least in this sort of simplest thing that could possibly work。

 where you use the same function F to manipulate all these probabilities。

It suggests that actually all the way out at one， where the LP is telling you to definitely give J to I。

 maybe you shouldn't give J to I with probability more than1 minus1 over E。

That's a guess you might have。All right。Yeah。Now， but then， of course， the other thing， I mean。

 the whole reason we're in this mess is because this thing isn't concave。 right So actually the。

 I mean， these are just sort of。Sort of side goals， I mean， really。

 what we want is we want that to be concve。I probably should have listed that as number one。

 actually。So，3。So let me just now。Write this。This way。Okay。All right， so。

Let me give that a better name。But actually， let's just try to think about what's the simplest F that would satisfy one and two？

Even。Yeah， so if at one， you want it to be like1 minus1 over E。

 it's kind of tempting to just set F to be f of y to be1 minus E to the minus y。Right。

Even ignoring three， it seems like that's the simplest thing that might give one and two。ああ。So guess。

F of Y， J will define。To be 1 minus e to the minus Y I J。So what does that look like。

So if this is f of y equal y。0，1，1。Then。This looks like this。Okay。

 where this curve is always the one minus v of the minus y curve is always at most of this one。

 sort of tailing off。So we have for。For Y Ij and 01。We have F of YIj， it does satisfy one。

So it's always going to be at most YIJ， and then the furthest it is ever away is at the rightmost point。

All right， so thats really satisfies one and two。What about three。So actually。

 even though sort of concavity was the whole point of this exercise。

 and we didn't even use concavity to guide us in guessing what F should look like。

 we just get it anyways， it just works， it just totally works。Okay， it's kind of magic。So。

So what is this now？What does star star evaluate？So these just become E to the minus Y， I J。

We're taking the product， so it just becomes as sum of the YIJ is up in the exponent。

Which is concave。So concavity just blows down to this part being convex in the exponential functions convex。

 Or if you prefer， you know， you could look at the Hessian and the Hessian is just going to be sort of a single block of non- zeros。

 all of which are equal to exactly the same constant， which is negative。

 So it's a negative semi definite hessian。 Okay basically it doesn't get much more convex than the exponential function。

 So it just， it totally works。Alright， so to reviews。 Okay， so what have we done， Allright。

 So we've done something where So we have a rounding algorithm now。

 which has definitely two of the three properties that we want。

 So there's still one more property I have to prove to。 First。

 let me just make sure it's totally clear what the。

 what the allocation rule and what the rounding algorithm is。Actually said， let me write this down。

Okay， so。So what have we done？Okay， so first of all。

 what's the rounding algorithm that we're proposing。

 It used to be this one where you just do randomized routing with respect to the Y IJs。

 Now it's just， you do randomized routing with respect to one minus e to the minus Y I Js。

These are at most Y IJ and the some of the Y IJs are at most one for an item J。

 So this is well defined。 There's going to be this residual probability more than before that an item is allocated to nobody。

 so be it。Okay。So that's the rounding algorithm。Now， what's the allocation rule。

 The allocation rule is just solve the following problem。So maximize over y。So again。

 this is sort of given。The VIs， coverage valuations explicitly through there sets the AIJs。

So remember what we had up here before is we had the expected welfare post rounding。Okay。

 that's how we got this expression in the first place。 right。

 So this was just the welfare of a particular bitterder post rounding。

 that became this using the coverage valuation assumption。 And then that became this， you know。

 with a short thought experiment。And now I've told you what the F is。So just to recap。

What's the contribution of each bitter eye？Iterate over the elements in its ground set。

 And you look at the probability that it gets some item J， whose AI J includes this little guy， A。

And that is just this term。Okay。And then subject two， some over YIj。For all J。Why are J non negative？

Okay， so the allocation rule is。Write this down。Solve it， get the best why， okay some Y star。

Run this randomized rounding algorithm。 So you do independent randomized rounding with respect to the F of Y I Js。

 and that's it。 It's the whole allocation rule， okay。As we've seen anything of this flavor。

 by definition is MIDR， M IDR， that's by definition of objective function。

We chose the rounding probabilities judiciously to force the objective function value to be concave。

So this is a concave maximization problem subject to linear inequalities。So modullo。

 some sort of technical annoyances that I'm not going to bore you with in lecture。

 this can be solved in polynomial time， for example， using the llsoid algorithm。Okay。

So we wanted three things， we wanted MIDR， so we get the incentive properties， we've got it。

We wanted computational tractability。 We've got the concavity。 So we've got the tractability。

 And then the third thing， which I still need to prove to you is the approximation guarantee。

 I have to prove to you that actually， at the end of the day。

 when we saw for Y star and we run the rounding algorithm， we get a good allocation。 Okay。

 We don't actually know that。😊，There's sort of hope， right。

 because we haven't actually tweaked to the YIJs too much， but I do owe you a short proof for that。

Questions。Yeah。So the tele rule might give a decent mechanism。

 but it is kind of unfair in what sense， because it penalizes people who want a lot of stuff a lot more than it penalizes。

So obfuscating， pretty nice everyone on the site。I see what you're saying。 So， I mean。

 with respect to the why， I mean， to the quest， I mean， so penalized in。 So you got to remember。

 I mean， you know， like the LP solution， the Ys， this might be unrealreizable。

So it's a little bit unfair to kind of say， oh， you're doing so much worse than the LP solution because the LP solution doesn't necessarily represent some realizable reality So it could just be that when you solve for a fractional solution in general you get stuff that's better than an integer solution。

So it could just be that like you're the bitterder who happened。

 who's the reason why the fractional solution is so fictitiously large。

So then you don't really have a right to complain when you say， oh。

 but the OP solution says I should get so much， you know。

 if there's no energy allocations that give you that much。So， I mean。

 there are probably cases where what you're saying is true， but it's not。

 I still don't really like using the wise as a benchmark。 I think that's sort of unreasonable。Yeah。

 it's a good comment。Other questions？Okay。So， the approximation。All right， so I forgot to say right。

So an output。All。Omega sampled from。The rounding algorithm。This surrounding algorithm。

Applied to the optimal solution， Y star。All right， so the claim is so the final claim。

Is that this is a 63% approximation in expectation。Okay。Alright。

 so one thing that's cool about these MI IR and MIDR allocation rules。

 And we did the same thing last week with multi unit auctions is all I have to do is exhibit some feasible solution with good expected welfare。

 Because remember， M I D R， what does it do by definition of all the feasible solutions。

 It picks the one that's best for the bidder。 Okay， so if I show you one good one。

 it does at least as well。😊，So need to exhibit。Some feasible Y hat。Such that expected welfare。

In R of Y hat。At least one minus1 over e times optt。And it's quite straightforward。

 which one we should try。So basically， there is some optimal allocation。It's natural to just say。

 well， you know， what if we just kind of fit into a rounding algorithm that we want the optimal allocation。

 Okay， what's it going to do？So。Just set Yj to be equal to one。If in the optimal allocation。

 j I gets J0 otherwise。So these are exactly the kinds of whys that were getting us in trouble before。

 right， because it did nothing。 It just handed us back the off allocation。 So now that we fix that。

 we just have to show we're not losing too much。So a claim。

Is that the expected welfare of your favorite bitter， bitter eye？Is at least1 minus1 over e。So again。

 expected with respects to the output of the rounding algorithm。

 if you feed it in this very strong hint about how items should be allocated。

 it will get a 1 minus1 of a refraction。Of that welfare it gets in the soft allocation。

And this is not hard to prove。 It does rely on the submodularity of the valuations。

It does not need to be coverage valuations。You do need some assumption on the valuations for this to be true。

So proof。So here's how I want you to think about this。So suppose in the optimal allocation。

 Biter I gets you know， some L items， okay。And what I want to do is I want to add these L items one at a time。

 Okay， in parallel in sort of two worlds。 right So in the first world。

 it's just where there's no randomized algorithm。 Okay， so there's this soft allocation。

 these L goods。 It gets good one， then good2， then good3， then good 4。

 and I track the increases in I's valuation。 Okay so each success of good gives it some marginal value。

 and I just track those numbers。On the other hand， I imagine trying in this sort of randomized rounding world to give bitter eye these same L items in sequence。

 But each time I try to give it an item， there's a one over each chance that basically the item goes poof。

 Okay， they don't get it。Okay。So a one more formally。I mean， so the high level idea is basically。

 you know， okay， so I give， you know over here， I give the items to the bidders one at a time。

 and this goes up by 10， then it goes up by 12， then it goes up by3， then it goes up by5， whatever。

You know over here， with a 1 minus1 over3 probability。

 you actually are getting the good because f of 1 equals1 minus1 of3。

So the difference between the two worlds is over here you have the entire prefix of items。

 so if you're doing item 11， you already have the first 10 items over here。Over here。

 you have some subset of the first 10 items， the ones that didn't go poof。 Okay， but it's a modular。

 So the marginal value of a new item is only going to be higher on the left hand side If you have a strict subset of what you have on the right hand side。

 Okay， so that's why it's true。So。Let TJ。Be the first J items of S star I ordered in some arbitrary way？

Then， so again， I mean， so just。To say it explicitly， with respect to a 0，1 vector， right。

 So basically， there's no chance I get any item outside of S star I。

 And there's a 1 -1 of every independent chance that I get each item inside S star I。 Okay。

 so but differently， you know， what is S I， It's just the result of the following random experiment for each good here。

I flip a coin with one every probability。 I delete it with one minus every probability。 I keep it。

 and then you get what's left on the table。 Okay， That's how you can generate a distribution of S's from S star I。

So。Again， just sort of thinking about。Acquiring the items one at a time。

So I look at the contribution to the welfare of the Jath item。So I should be J。

So what's the expected contribution of the JF item to Is welfare was the probability that you get it at all。

Times the expected。Added value of J。Given the subset of the first J minus-1 items that you got in this random experiment。

So for an item in S star I， this is exactly equal to 1 minus 108。

This is going to be the difference between you know。

 some subset of the first JMs plus J and just that subset。So this is by submodularity。

At least the marginal value with respect to the full set。Okay。So taking the 1 minus1 over E out。

We just get a sum over the items in the optimal bundle。Of the successive added values。

 success marginal values。Which is just。Your value for the full optimal bundle。And so again。

 submodularity is used crucially in this part。So if you didn't get some of the items in the past。

 it only increases your marginal value for the current item J under consideration。

So that's the third property。 You do， in fact， get a win minus u over approximation。Any questions？

Right so the mechanisms in this part two are obviously very complicated。

 they're the most complicated ones that we'll see in the quarter。

 It sort of befits the fact that we're actually you know despite being not much past gross substitutes where at what seems to be the frontier of tractability for DC approximation So to get this far you have to work very hard and I'll open next week with some comments about how going any farther seems in effect impossible And so in part 3 and part4。

 the class， the plan will be to look at weaker notions of implementation。

 well look at implementations and undominated strategies will start talking about Bays Nash implementations and the incentive guarantees won't be as strong but there'll be a big payoff both and the variety of problems we get strong guarantees for and for the relative simplicity of the mechanisms that give us those guarantees so don't forget there's a bonus lecture on Friday for those of you that are interested So 1250 to 205 on G 359 the goal is to plan。

goalal is to understand gross substitutes through the lens of greedy algorithms。 And then next week。

 I'll see you back on Wednesday for part 3。