# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p09 -09-(Lecture 9_ MIDR Mechanisms via Scaling Algorithms).zh_en -BV1fNVNzhEBg_p9-

So at the end of last lecture， we were studying a particular scenario， a pretty new one。

 So we had non identical items。We had totally general valuations， case a not of modular。

 nothing like that。But the twist in scenario 8 was that we had a lower bound on the supply of every item。

 Usually we were just thinking of one copy of every item。 scenario 8， we have K copies。

 and the problem gets easier， the bigger K is。 the bigger the supply is。

 So we assume each bidder only wants one copy of a given item。

 But other than that it's totally arbitrary。 so thoses M sort of types of items。

 K copies of each K and items overall。 And valuations are defined only on subset of U。

 and we just assume we only give one copy to a given bidder。 but actually。

 we didn't even need that these were monotone last week。 If you go back and look at the proofs。

 So these are totally general Vs。 And for the purposes of talking about polynomial time。

 We're thinking of these as black boxes。 All we do is we interact with them。

 And they support value queries and demand queries。 It's not important right now。

 But the reason we needed demand queries was to solve an LP relaxation。

 That was the separation oracle in the dual that we needed to solve the LP。

And so what we did last week is we said， well， let's put incentives aside。

And just focus on the algorithmic problem of welfare maximization。

 We postpone incentives until today。 And for just the underlying welfare maximization problem。

 we showed that it can be solved in polynomial time almost optimally。 we had a really nice， strong。

 positive result。So like I said， the problem gets easier， the bigger K is。

 but so we need k to be logarithmic。So if you have a logM over epsilon squared copies of every item。

 we gave a polynomial time algorithm that gets within a one minus epsilon factor of welfare maximizing allocation and actually so let me say the theorem and here's what we actually proved because this is sort of a stronger statement than what I put on the board last time but the proof actually showed this。

The algorithm takes as input， it takes some feasible linear programming solution。

 so this was for that LP with the decision variables corresponding to bid design bundles S。

And so it takes as input an LP solution。 And then it did this randomized rounding。

 So it scaled down the solution slightly。 multiplied all the y by 1 minus epsilon。

 And then for each bidder， it gave it a bundle at random。 Okay。

 we did this independently for each bitter I。 We had these Y Is。

 And that we just interpreted those as the probabilities of getting a given bundle S。

 And what we proved is that the expected welfare of the solution was almost as good as the LP solution。

 almost as good as what we started with。 and there was a decent chance of being feasible。

 as a result， if you just keep doing independent trials of this randomized rounding algorithm。

 you simultaneously get the。An allocation which is feasible。

 meaning every good is allocated at most k times， and also the welfare of that allocation is almost as good as that of the LP solution that you started with。

So the particular wise that we were working with last week was the optimal solution。

 the linear program。 That's the obvious one to use。 But more generally。

 we didn't really use that fact。 We just said， okay， give me the feasible LP solution。

 Fe it into this randomized rounding。 And this is what you get as output。

 Feas plus almost as good as the fractional solution。 So that's what we proved。This can also be。

 so I gave you a randomized variant。 We're sort of thinking of just doing independent trials until it succeeds。

 It can be deranized。 I'm not going to talk about it in class， though， okay。

 but it's sort of nontrial but standard techniques from 25 years ago。 Okay。

 so this can be made deterministic as well。So that's specifically kind of where we left off last week。

Now， as far as the big picture， just so you don't lose the forest for the trees。 What are we doing。

 So this is the sort of second and final week of part2。

 where we're looking at sort of N hard versions of welfare maximization。 It。 I didn't say it。

 but this is also MP hard。 We can get close to optimal， but you can't get optimal。

And we're still looking for this very strong dominant strategy sound of compatibility guarantee。

 so that's what we're doing now。 And this is hard。 This is one of the most challenging goals we're going to see all quarter。

 And the reason being is as soon as you pass your approximation algorithms generally the VCG mechanism no longer works。

 And even more generally， we just kind of have a very sort of thin toolbox for designing multi parameterameter d mechanisms。

 And so the approach we're sort of doing is we're just sort we're doing this bottom up approach where we're just sort of you grasping for whatever d mechanisms we can find。

 we started with just the VCG mechanism， that's sort of all we had。 we said okay what could we do。

 Well the first baby step was maximum range。 So we said， well， I guess you know if we wanted。

 we could throw out a bunch of the outcomes up front and then run VCG on what's left。 It's clearly d。

 I give you one application of that for multi unit auctions with non- downwardloping valuations。

 We had to two approximation。 And so right now we're in the middle of this second baby step。

 just like okay， you know， just these maximum range mechanisms， they have some applications。

 but they're pretty limited。So the second baby step which we introduced last week and we' actually use in both of the lectures today is the extension of maximum and distributional range。

Okay。So a maximum distributional range or MIDR。Allocation rule。

 so this is going to be a randomized allocation rule。

And instead of pre committing to a set of outcomes。

 it precomms to a set of distributions over outcomes。 Okay， so script D is the set of distributions。

Okay，When I talk about outcomes， you know， I'm talking about them abstractly。 But for our purposes。

 we're always thinking about allocations。 So just a way of assigning the items to all of the bidders。

 okay。So as far as you know， right， So maximum range。

 that corresponds to the case where all the distributions are just point masses。

 So this is certainly at least as general。 You know， what might these be， know， So you。

 what is this distribution， It could just be an explicit list， know。

 this allocation with 1% probability， this other one with 3% probability， et etc cea。 You know。

 maybe it's defined implicitly， know like for each item assigned it randomly to a bid recording to some distribution。

 Those are the kind of distributions we want to have in mind in script D。Now， you know。

 this is is gonna to be this is in the spirit of VG。

 So there should be some flavor of exact optimization。 So by definition。

 once you've settled on this set of distributions， allocation was uniquely defined so basically。

 given that we're going to sample an outcome from one of these distributions。

 we insist on picking the distribution， which is best for the bidders。 just in the spirit of VG。

 So what's best for the bidders， it just means maximizes their expected welfare。

 given that we're going to sample from the distribution。So， it outputs。

So I'm going to use sometimes little omega as shorthand for an allocation。

 but just think of always little omega is some S1， S2 up to SN。

 the items assigned all of the bidders， okay。So it outputs some outcome or some allocation。

 drawn at random。From the best distribution。The star。Again， meaning that among all of the candidates。

So all of the distributions in script D， D star should give the bidders the maximum possible welfare。

Where here， V I denotes the reported valuations of the bidders，So again。

 sort of given that we've pre committedm to this distribution set script D。

 and given that we're going to sample an outcome from one of these distributions， we should pick。

 pick the best one。Sure。And then what I asked you to do as an exercise for exercise set four is to verify that there's a natural analog of VCG payments。

 which when you couple them with this allocation rule gives you a DI mechanism。

 So this is a randomized allocation rule So here we're defining D to be bidders maximize their expected utility where the expectation is over the coin flips and the allocation rule by revealing their true valuation。

 So we're thinking about risk neutral bidders okay。Allright， so that's kind of where we were。

 Now that everyone's here。 let me just sort pause for the quick course announcements。

 So there are only two required problems in exercise set4 those are due today。

 I'm gonna post an exercise set5 soon。 that's gonna be completely optional。

 just have two or three optional questions。 So be on the look out for that today or tomorrow。

 So the big news is that all the project deadlines are now sort of settled and all the project suggestions are on the website you should have an email with the link to that。

 So by Friday。 So this is for those of you taking the course for letter grade by the way。

 only So if're taking the course for letter grade send me at least two topics you're interested in by Friday and then over the weekend I'll sort write people back with confirmations of the project topics。

 There's two deliverables。 one just to sort keep people on track is I do want one to two page outline。

 There's more detailed instructions on the website So that's gonna be do March 5。

 That's a Wednesday and that's two weeks before the final report。

Do this is the Wednesday of finals week， March 19th and just you know ballpark 12 to 15 pages。

 there's both more detailed instructions。 There's also a sample report all posted on the website and again。

 feel free to just get in touch with questions either picking the projects or afterwards happy to help。

Alright， so any questions。O。Right， so we have on the one hand。 All right， so basically。

 we have these MIDR allocation rules。 We've defined them。 We haven't used them。

 There's this problem where we know how to solve it without incentives。 And so， you know。

 no prizes for what comes next。 We're going to use these allocation rules to get just as good an approximation for that problem with incentives。

 that's the plan for this lecture。 and then the second lecture today we'll go back to know kicked off this whole MP hardness discussion。

 submodular valuations。 and we'll give a second application of MIDR allocation rules to get a constant factor decent mechanism for a subclass of submodular valuations。

 Okay so that's the plan for today。 full disclosure。

 this is probably going be the most sort of technically intense lecture of the quarter would be my guess。

 So I'm not gonna say it's easy after this。 But if you can survive today。

 I think it'll all be downhill from here。 And also the lecture right now。

 this first lecture will be the longer one。 The second lecture will be the shorter one for today。

 probably。So that's just what， what you can expect。All right， so let me just remind you。

 why are we doing this， So why， you know， what's the。

You know whyhy did we define these MIDR allocation rules。

 well one thing is just we're just trying to brainstorm about what else might possibly be decentI。

 but I mean， can we even like think of why this might be useful？And so the hope。You know， which。

You shouldn't necessarily believe until I show you the actual examples。

 but the hope would be know in the same spirit that if you have a discrete problem， which is hard。

 like an integer program and you relax it to a linear program， you allow more solutions。

 fractional solutions that can somehow create tractability when it wasn't there before。

So this is sort of the daydream。Now， you know a couple warnings。 so first of all。

 this analogy is not perfect。 So when you relax an integer program to a linear program。

 you keep all the integer solutions and you get a bunch more stuff。

 you get stuff which is usually strictly better than the integer integer solutions。

 We've seen that already。And that's not really what's happening when you pass to an MID or allocation rule。

 if you think about it right So you have these integer solutions， these allocations。

 and we're passing to things which by definition are distributions over allocations。

 Okay so you're not gonna have anything strictly better than an allocation。

 you're only looking at distributions of allocations So in particular。

 if you think of an MID or allocation rule， and it happens to be the case that in this set script D that includes all the point masses。

 all the integer solutions。 Well， you're not going to do better than an integer solution with the distribution。

 So if you have all the integer solutions in D， all the point masses。

 you haven't made your life any easier。 things have not gotten more tractable。

 You're optimizing over just as hard a set as before。So that's a little different。

 so somehow these set script D have to be chosen and you know a fair amount of work has to go into figuring out what the right script D is。

 we'll see that today。And then the second comment is。

 you know we will see a couple of nice applications of MIDR allocation rules。

But they're really still you know， pretty limited in use。 And so it'll never be the case that。

 you know， you design some randomized algorithm and you get lucky and it happens to be MIDR。

 that just basically never happens。 You have to basically channel all your design creativity into ensuring the MIDR property。

 Now， again， we'll see a couple of positive examples。 but I mean。

 it's really a pretty limited kind of playground that we're working in to design these rules。

 Okay that was true for max range rules also， yout。

 you never accidentally get a maximal and range approximation algorithm。

 You have to sort of begin the exercise trying trying to get that property。Okay。So。Today。

 so in the first lecture， I want to focus on a special kind of MIDR rule。

And I'm going to call these scaling algorithms。Which is very restricted form of randomized rounding。

 randomized rounding。 We've already seen an example of last week in the just approximation algorithm。

 okay。So let me explain how I want you to think about。

Randomized rounding of linear programs for today。 And we're going to be， you know。

 this will be sort of our perspective in both lectures today。So we think about algorithms。

 approximation algorithms that are the composition of two steps。 So in the first step。

 you saw the linear program。 And in the second step， you ran it to an integer solution。Okay。

 so the LP you should have in mind is just the one we were working with over the last couple weeks。

 you know， with the Y Is as decision variables。So the LP。

 you can think of as that as taking these valuations as inputs， you know。

 as specified by a black box， supporting demand queries or whatever。

 So the first part of the algorithm takes as input， the LP。Sorry， the valuations。

 and then it solves some LP optimally。And it spits out an optimal LP solution。

Yhy star I so this was exactly the first step in our algorithm last week。

Then we have what I'm going to call an oblivious， randomized rounding algorithm。Or。

So the responsibility of the first box is just to produce an LP solution。

 and the responsibility of the second box is to compile this LP solution， which in general。

 is not a distribution of allocations into a distribution of allocations。

 so that is just going to randomly pick some allocation。

So over here we're going to get a distribution， and I'm going to use the notation。

R of y R of Y star as the distribution of allocations implicit in this rounding algorithm， okay。

All right， so a couple of comments。 So what do we mean by oblivious？

So what I mean by oblivious here is that once you give the random。

 once you give the rounding algorithm， this LP solution， the Ys。

 it doesn't look at the original input， the valuations that generated these Y's。 So basically。

 the rounding algorithm depends only on the Y's。 not on the V's。 That's what I mean by oblivious。

 In principle， you can imagine randomized rounding algorithms， which not only use the Y's。

 but go back and look at the's again to do clever rounding。

 Okay So today it's going to be oblivious and it doesn't do that。

 And if you think about the randomized rounding last week， it was oblivious in this sense。

 It just looked at the ys scaled them down and then flipped coins according to the Y'。

So that's what I mean by oblivious。And again， let me just remind you that this LP solution in general is strictly better right so when an LP relaxation。

 including the one we're looking at here， the Y star is strictly better than any integer allocation。

 Okay， so therefore it's not by itself a distribution of allocations。

 that's what happens in this final step。All right， good。So the question now is。

 what is the relationship between a randomized rounding algorithm and M I D R allocation rules。

 Are they the same or can they ever be the same。So at a high level。

 we might we might hope that randomized rounding is is a good candidate class of algorithms to generate MIDR rules。

 Remember what MIDR says， it basically says， you should always be picking the best distribution。

 I guess you're optimizing over distributions。Randomized rounding has this sort of nice， you know。

 there's some syntactic connections and that you are explicitly doing a random and optimization over fractional solutions and you're outputting distributions。

 which have some connection to what you're optimizing over。

 So M I DR says optimize over distributions。 This picture。

 Well you optimize over the Ys and then the y' is sort of generate these distributions。

 So that sounds like it's on the right track。😊，The concern。

 the reason why randomized routing algorithm like this might not yield MIDR rules is because what we really want to be optimizing over。

 if you look at the definition of MIDR， we want to be optimizing over this output here。

We always want to be outputting the best distribution of allocations for the given Vs。

But in this picture， the optimization is happening over here。

 The optimization is happening over the LP solutions。

 The optimization is not explicitly happening over the distributions。 Okay。

 So the worry is that there's some disconnect between those two introduced by the rounding algorithm R。

So scaling algorithms are going to be the specific kind of randomized rounduting algorithms where optimization over the fractional solutions is exactly the same as optimizing over the distributions。

 so it's exactly the class of capital Rs that give us the MIDR property in this schematic picture。

All right， so what is it simple enough to state？So an oblivious randomized rounding algorithm。

Is an alpha scaling algorithm。So here alpha is a number between 0 and1。If。Whatever you feed it。

 so whatever feasible LP solution you give it， why？

If you look at any bitterder and you look at any bundle。

 the probability that bitter eye gets this bundle in the output of this rounding algorithm is exactly what the LP suggests Y star I multiplied by alpha。

 Okay， so think of alpha as like 0。9。So the probability。 And again， so what's the coin flips here。

 The coin flips is over。What the randomized algorithm does。

 remember Y is an LP solution that gets fed to this rounding algorithm。

 it flips and coins and outputs an allocation。And so an alpha， sorry， so。

It's the probability that I gets S。I exactly。The suggested probability。

 or we're going to interpret this is the suggested probability of that event by the LP solution times alpha。

Okay。And again， let me remind you， we would not expect for some NP hard problem like this。

 we would not expect to ever have a one scaling algorithm。Okay。Remember。

 these LP solutions in general， they're going to be strictly better than any integer allocation。Okay。

 so if we had a one here that would say we're giving people exactly what the LP is giving them an expectation Okay。

 so we'd be getting an expectation the full value of the LP and we don't expect to get that。

 The LP is going to be strictly better than any integer allocation。

 So we want this to be scaled down， or we expect this has to be scaled down。

 but we're hoping alphas as close to one as possible。

 Al will correspond some approximation guarantee。Yeah。All right， so is that is that definition clear。

Okay， so the， I mean， the motivation， I think， will become more clear as you go along。

 But at high level， the point of this definition is so that by optimizing over an LP。

 you wind up inadvertently optimizing over the distributions in your range。 Okay。

 and we'll see that that happens。 but everyone can parse this okay。好 right。

So let me now show you why if you have such an algorithm。

 you're good to go and then we'll worry about， okay， do such algorithms exist， and if so。

 how do we get our hands on them？Okay， so claim。If we have an alpha scaling algorithm。

Then the induced allocation rule。X。Is MIDR， and so what I mean by induced allocation rule。

 I mean the allocation rule where you solve the LP optimally。

And then you apply the scaling algorithm to generate a randomly generated allocation。

 That's what I mean by the induced allocation rule。

So the claim is scaling algorithms are a sufficient condition to turn for a randomized rounding algorithm to give you an MIDR rule and therefore a DI mechanism。

So the proof is easy because we define scaling algorithms to make it easy。Alright。

 so M I DR just means of all the distributions of outcomes that we might ever see varying over all valuations for a given valuation。

 the algorithm picks the one that maximizes expected welfare。 So what is the range。

 the distributional range of this allocation rule。Well， it's just。As you range， so conceptually。

 imagine just over the LP solver， imagine feeding this every possible input in the world。

 every possible valuation profile。So you get back some set of every possible output。

 every conceivable Ys that you ever get from this LP solver。

 and from each of those Y's you might get， imagine applying the randomized rounding and you get some corresponding allocation distribution over the allocations so the range of act is simply。

The output distribution of the randomized rounding algorithm applied to any conceivable LP solution that might be fed。

Okay。Now， here's the key point。 So here's what's special about scaling algorithms。So no matter what。

Feaible LP solution Y。You feed the rounding algorithm R。

You get that the expected welfare of the allocation at the end of the day is exactly the same as the LP solution you started with。

 multiplied by alpha。Okay。So the expectation here， let's look at the allocation。 So， again， you know。

 omega drawn from R of Y。 just think of this as like the output of the randomized rounding algorithm and it's expected welfare。

 that's what we're saying。So。This is just the welfare of mega， and again。

 omega is just the random output of the randomized yaing algorithm。

And just so by linearity of expectations， we can just do this as a sum over bidders。

And now for a given bidder， let's just kind of brute force some this， let's just say， well。

 think of every bundle S the bitterder I might get， it has some value for that bundle。

 and then it contributes to this expectation， the probability that I actually gets that bundle where again this is over the coin flips and the randomized rounding algorithm。

And now， by definition。I've an now the scaling algorithm。 this is equal to。Just the。

Alpha times the welfare of the fractional solution given by the Y。Okay。So the point is。

 you saw this LP。 you get some fractional welfare， you know，1230 or whatever， know。

 which in general is strictly bigger than the welfare of any integer allocation。

 you feed it through this randomized rounding algorithm and you have just know exactly what's going to happen。

 the expected welfare is going to get scaled down。 It's going to get scaled down by alpha。

 It doesn't matter what y was。 It's always scaled down by exactly the same amount。 Like always 0。9。

So why is that good？Well， so again， remember。What do we need to have the incentive properties。

 We need to be optimizing over the distribution of our outcomes。 right， That's the definition。 Okay。

 we need to pick the best distribution。 What are we actually doing in our algorithm。

 Well we're not explicitly optimizing over distributions。 We're optimizing over our LP solutions。

But this basically says that the two optimization problems are exactly the same。

 If you're going to round using capital R this one algorithm。 Okay， so optimizing， you know。

 picking the best distribution for the expected welfare is exactly the same as picking the best fractional solution Y for the LP solution because there's just a linear relationship between the two quantities。

So upshot。R of y is optimal。For a given input or hereby optimal。

 I mean overall distributions in the range of the rule。If and only if， why is optimal。

For the same valuation profile， or hereby optimal， I mean over LP solutions。Okay。So again。

 the expected welfare always drops by exactly the same factor alpha。

 so by explicitly optimizing over the LP solutions Y。

 you wind up implicitly optimizing over the distributions of our allocations。

And that's the definition of MIDR。So that's the claim。So since why Star is chosen optimally。

That means we're choosing the optimal corresponding distribution。

 So the allocation rule is maximal in distributional range。So maybe just。

 just to sort of talk through this a little bit more to like what would go wrong。 So like。

 imagine instead of this definition， instead of alpha scaling， I only promised you that for every Y。

 for every I for every S。The probability is， at least。Alpha times what the LP suggests。

 Okay so maybe alpha is like 09。 So I said， well， you know。

 I don't know exactly what the probability is going to be。

 but I promise you'll be at least 90% of what the LP wants it to be。

Because often the kinds of guarantees we prove in the analysis of approximations， it's 0。

9 are better。So this claim is not going to be true。Right， assuming only that this is at least。

9 always。Why， well， maybe you had these two LP solutions， right， Y 1 and Y2。

 So you have a given input。 You have these valuation profile。

 and there's these two competing LP solutions at Y1 and Y 2。Okay。

And with respect to the LP objective， they're almost the same。Okay。

 like y 1 is 1% better than y2 for this valuation profile。 Okay。

 and maybe it happens that when you then apply the rounding algorithm， though。

 very different things happen。 Okay， so with y 1， when you round it， you actually only get 80% of it。

On average， in the allocation， whereas Y 2， for some reason， just is you know。

 better friends with a rounduting algorithm。 and you get 90% of Y 2 when you round it。Okay。

So you started with LP solutions where Y 1 was better than Y 2。

 But then after the rounding algorithm， they flipped。 Okay， it turns out further bidders。

 they actually would rather you started with Y 2 than started with Y 1。

They have preferred you started with a suboptimal LP solution because it does better in surviving the rounding algorithm。

So that's why it's really important that we have a quality here for this claim to work。

 for that might be art to work。Okay。So any questions about that？So， again， at a high level。You know。

 you can kind of reverse engineer everything we've said so far。

 You can come up with this idea of I MDR just by asking。

 is there a randomized analog of the V G mechanism。 The answer is yes， and it's MDR。

 that's just what you come up with by answering that question。

Then you sort of recognize that this is sort of a pretty hard property to in。

 and so now you want to ask， okay， well， what kind of crazy conditions can I envision on an algorithm where I'm guaranteed to get this property？

And randomized rounding starts looks like a good place to start because there's optimization and there's distributions。

And then you realize you need this very tight control over how the LP solution is rounded to have this correspondence between optimizing over the LP and optimizing over distributions and the control that you need is basically this definition of a scaling algorithm。

So that's where things stand right now。Any questions？

So what you should now appreciate is that if we can come up with these alpha scaling algorithms with alpha close to one。

 we're happy。Were get good approximations is going to be MIDR， so it's going to be die。So now。

 are there any。Well， actually， let's start with this first question， sort of an interesting question。

Let's actually think about the rounding algorithm R， which we used to prove this theorem last week。

So let remind you how that went。It follows this exact same blueprint。 We first saw the LP。

 We got our Y star。We scaled Y star by 1 minus epsilon。It sounds kind of like scaling algorithm。

 right？We scaled it down so we could be feasible with high probability。

So then we scale it by  one minus epsilon， and then we do this independent randomized rounding。Okay。

And then we do independent trials until we get sufficiently good welfare close to the expectation。

 And we're also feasible。 And then when we get when we stop， that was the randomized version。

So was that a scaling algorithm or not？It's kind of a subtle question， any guesses？No， why？

There's a school probability that you can have to do something strange at the end the size of probability。

Good。So I was a little， I underspecified the algorithm。

 and for one of the natural things I might have meant， that's exactly the right answer。

So how about the following version of the algorithm？Which is。

 I just keep doing independent randomized trials。And I wait until I get something， and I just wait。

 I never do anything weird。I just wait until I get one。That has good welfare， and that's feasible。

 And that's going to happen eventually with probably one。

So the version of the algorithm where I do it a polynomial many times and if none of them work。

 then I do something else， you're exactly right。Yeah， so yeah， good what happens。

Like maybe a certain allocation， allocating S toI makes it more likely that they'll succeed。

 which means that you get higher。You get higher than alpha times。

Why start for some of them in the lower further ones good good y exactly so the short answer is that the version I just said where you wait until you get something which is both feasible and high high welfare。

It's not the case that the distribution is exactly one minus alpha times the previous one because you've conditioned on stopping。

Okay so when you flip the coins and you don't condition on feasibility。

 then indeed the probability that you get a certain bundle is exactly one minus alpha times what the LP said that's by definition of your algorithm。

 but if then the final output is you know stopping then there's this conditioning on the stopping rule and so so concretely is exactly what you said it may be the case that if you know if I told you that the algorithm stopped here。

 I told you it was feasible and it had good welfare。

 maybe you could make inferences like oh well then for sure this coin flip came up tails because if this person got this bundle that would always screw everything up exactly。

You're coming all air。Well， if you just ti in a did one put them then ti， then it would be。

 I don't have to the outcome。Well， so the problem is it wouldn't be feasible。

 So that's exactly right。 So if you just wasn't feasible， then you just， no it。I see。

 excellent point。 Yeah， you could do that as well。 Thats That would give you a worse alpha。 Yeah。

 exactly， right。 So either， so you do it once。 is that true。 No。

 I think you' still have the conditioning problem， right， Sam conditioning problem， yeah。

So if you drop the feasibility constraints and you just said this is the allocation。

 then you sort of have it by fiat。 Yeah， Yeah， but so that's the problem。

 So I wish it was the scaling algorithm because then wouldn't we could skip 30 minutes a lecture。

 but it's not So the incentives are actually wrong。

 If you try to plug in the algorithm from last week into this schema， if you try to boost G payments。

 It's not going to work。 It's not going to be de。 It's not in general， be approximately d。

It is important that that thing exists。 There's a reason that there's a reason that we went through it。

So， instead。We're going to do something kind of remarkable。

 we're going to show that just by virtue of their existing one minus eon one minus epsilon approximate randomized randomized rounding algorithm。

 which is not scaling， by virtue of that existing， will show that implies that there must exist an equally good randomized rounding algorithm。

 which is a scaling algorithm。And we'll explicitly use the existence of this one we built last week in that。

Okay， you can think of what we're about to do is somehow taking that old approximation algorithm and smoothing its errors equally across all inputs。

 That's sort of morally what we're gonna do。Okay。So heres the here's。What we're going to do for this。

 here's the what we're going to prove this first lecture， so this is a result by Levy and Swwami。

From mid last decade。So in the current scenario that we're talking about。

Under the same lower bound on the supply。There does exist。A poly time。

One minus epsilon scaling algorithm。And because of everything else we've said。

That gives us a1 minus epsilon approximate。Poly time。MIDR enhanced DI mechanism。Okay。Which is really。

 which， I mean， just as a result， this is pretty cool right if you think that we haven't imposed anything on the valuations。

 right， this is actually a really strong positive result。 So first of all。

 we're doing just as well as without the incentive constraints。 Okay。

 so without incentive constraints，1 minus epsilon is the best you can。

 We're getting minus epsilon with D， the best incentive constraints。😊，And then also， of course。

 the approximation ratio is excellent。 It's basically going to one once the supply is going to is logarithmic。

 getting at least logarithmic。So we have to work pretty hard。

 but as a guarantee it's pretty compelling， I think。O。So what's the plan？

So let me tell you at a high level how this is going to work。Alright。

 so here's how we construct the scaling algorithm。Okay。So we're given as input。The optimal solution。

To the LP。I'm going to call it the original LP for reasons to become clear。

This is the input to the scaling algorithm to capital R。Now here's what we're going to do。

 we're actually going to solve。A second linear program。

Whose feasible solutions are encodings of scaling algorithms。Okay。

 so we're going to have to show this when your program exists sorry， it' feasible。

 That is there exists scaling algorithm， and I'm also going to have to show you that we can compute one in polynomial time。

 and I'm also going to have to show you that we can sample from that scaling algorithm in polynomial time。

So we'll get all of those things sort of in one fell swoop， but those are all important properties。

So we're going to solve a second linear program to compute。A probability distribution。Capital lambda。

And the profit distribution is going to be explicitly specified。 Okay。

 so it's just going to be a list。 It's going be。 Here's allocation 1。

 Spit it out with 1% probability。 Here's allocation 2， spit that out with 3% probability and so on。

Okay， so probability distribution， explicit。Again， remember。

 omegas represent outcomes mean as in allocations。Such that， okay， so L。

 the support of this distribution is going to be polynomial size。

And this is going to be a scaling algorithm， meaning that the probability if you sample from capital lambmbda。

That I gets S is going to be equal to。So right， so our alpha is going to be 1 minus epsilon。

Times Y star I for all I。And given that it's just an explicit probability distribution that has small size。

 then you can just sample from it efficiently just by brute force。So explicitly， so that's not hard。

 given if we can implement two， then sampling from it is easy。O。

So the content here obviously is just is step two， so how do I do that？Right the this is the point。

So you agree that if we can do this， then we're done， we have our1 minus epsilon scaling algorithm。O。

So。Details for step two。So first things first， let me actually explain this second linear program to you。

In some ways， it's the obvious  one。 I mean， it's just we're literally just gonna like in effectffect by brute force。

 you know， look。 So okay， why linear program。 So remember， we're given our target probabilities。

 right， So we're given as input。 You know， these fractions。

 which is sort of our target probability of giving S to I。 So these are just numbers。 Remember。

 these y stars。 So these are not decision variables。 Y stars are given。

So these are just linear constraints。 Okay， this idea that we should know。

 be scaling down probabilities by exactly alpha。 So that's why。

 linear program seems like something you might want to use。Okay。All right。

 so we're going to have to all right， so quick technical points。So Y star， this LP solution。

 remember what these decision variables are。 Okay， there's one for every bundle I and there's one。

 sorry for every bitter I and one for every bundle S。That's a lot of decision variables。 right。

 There's n choices for I， and there's two to the M choices for S。Okay。

 so there's zillions of potential decision variables。 On the other hand， remember， you know。

 this is what we did a couple of weeks ago。 We computed Y star in polynomial time。

 That was this thing where we sort of went to the duall， used the ellsoid method。

 and then the separation oracle was a demand oracle， etc cetera， etc cetera。 Okay。

 so Y star is the explicit output of some polynomial time， linear programming computation。😊。

So there was not time to write down to the n times2 to the m decision variables when we solve for y star。

 because there's only a polynomial number of nonzero y stars because it was done by a polynomial time computation。

So， that I。Be the non zeros， the indices for the non zeros and Y star。Okay。So poly size。

So I is poly in N M and the number of bits in the original linear program。Since。Explicit outputs。

Of a polytime computation。Okay。So why do I mention that， Well， you know， so looking ahead， I mean。

 like as I alluded to， these are going to be constraints in some linear program。

 and this means we can only worry about the non zeros。

 Okay it means there's going to be a polynomial number of constraints。

 That's why this is an important observation。Okay。So notations， a let omega be as usual。

 all possible allocations。So this is what we' remember。

 we're searching for a distribution over allocations。

 so somehow decision variables are just going to correspond to the probability mass on a given allocation。

And then because we're interested in the probability that a bidder gets a bundle。

 we should keep track for a given IN S。The allocations where I gets particular bundle S。Okay。

And so now what is the second LP？So the second LP will literally you just have a decision variable。

Lambda mega。So this just represents the probability mass we're going to put on the allocation omega。

 Okay， remember， we're solving for basically like a randomized rounding algorithm。

 we're solving for a distribution of allocations。 This decision variable just is going to be something like 1% output this allocation with 1% of probability。

Should be a distribution， so let's make sure that they sum the one。And then， of course。

 there's a whole raison detro for this thing， which is getting the scaling constraints。

So I really should write for all I， we really want to preserve the probability of every every single bitter bundle pair。

 but again， I don't want exponentially my constraints here。

 so I'm just going to focus on the nonzero y stars so the y stars is an I。对。So， okay。

 so what should be， So the right hand side here， we know what this is supposed to be。

 The probability mass of the allocations where I gets S is just supposed to be by the definition of a scaling algorithm。

 The target Y star I S scaled by 1 minus epsilon。 And then the left hand side here is just gonna be all allocations。

Where I guess S。So that's the OP。I will be to。く。Any complaints？

 There's potentially a complaint about this LP， actually， given what I said it was supposed to do。

So it's not， so I'm trying to encode scaling algorithms， algorithms that meet this condition。

And I didn't quite do that。I wrote down a smaller LP。Right。

So these are the constraints saying I'm supposed to respect the target probabil， the Y stars。

 and I only wrote them down when the right hand side was。No zero。

 I just didn't write down the ones that were zero。And if you think about it， I mean， I mean。

 it's not obvious that if you solve this smaller linear program。

 you're going to get something that respects those zeros。 Okay。

 so it might be the case that you know， theres some missing constraint where I S is not an I。

 meaning y star 0， the right hand side 0。 and maybe the probability mass on the left hand side adds up to 2% or something。

But there's actually， if you think about it， an easy sort of post processing hack to fix that。

So the claim is that if I think of any feasible solution to this linear program。Then it induces。

A scaling algorithm in this sense。So by Fiat， any solution to this linear program respects all the non zeros。

 so that's no problem。So what I can do is I can just take the feasible solution。

 sample from it if I ever see a forbidden pair in the output。

 so I pick an allocation from this randomized solution。

 and if it's ever the case that I get the bundle S where I is not an I， I say，'m just kidding。

And take it away from him。Okay so just sort of zero out。Forbidden。

 bitter bundle pairs after the fact， I just force them to be zero。Okay， so that's not the hard part。

 right so if you think about it， like enforcing that this distribution has a zero probability of giving some bidder。

 some bundle， that's really easy to enforce after the fact。

 So that's why I can get away omitting it from the LP。

 So the hard part is for the nonze is getting exactly right。 And that's done explicitly in the LP。

Okay。Summarizing note。Every feasible solution。Induces， I'll say。

Induces a1 minus epsilon scaling algorithm。Okay， just by canceling forbidden bitter bundle repairs after the fact。

Okay。So does everyone agree that if this thing is actually feasible， Remember， our priorityi， we。

 this could be empty。 We have no idea。 I can write this down。 Doesn't mean it's like useful， right。

But if this is not empty and I show you how to compute。A feasible solution in polynomial time。

 And moreover， the feasible solution has small support。

 then that's an implementation of step  two here。Are， so that's what I owe you at this point。

I owe you non emptiness， tractability of the solution。

 and small support of the solution that gets computed。Any questions， module that。好。

It an exponential number of land I。Excellent， yeah， so I should have mentioned that immediately。Yeah。

 there's a lot of lambdas。 Okay， so there's a lot of decision variables in this linear program。 Okay。

 so remember， omega is an allocation， a way of assigning items to bidders。

 And there's a zillion ways you can do that， right， Each of the M items can go to one of N bidders。

Okay。So that's MD MD theM allocations，So which is another reason why I really wanted to make sure that we had to have any kind of prayer so if both the number of variables and the number of constraints of polynomial as a linearar program。

 we're good to go， but use any polynomial time method， it's fine。If both are exponential， forget it。

 There's nothing you can do， basically。If one of them is polynomial。

 you least have a hope through the ellipsoid algorithm。 If you have a separation oracle。

 Okay so at this point， it's not at all obvious， we can solve it， but it's not obviously hopeless。

 And this is the comment about why it was so nice to have only a polynomial number of nonzes and Y star and dropping all but a polynomial number of constraints。

 So at least the number of constraints is small。But the number of variables is huge。Absolutely。

I guess I saw a question about knowing that there's a polymer。we were solving。

 so you have to reconstruct you' absolutely right。 I'm glossing over this on purpose and lecture。

 So if you look at the I so the notes for lecture 8， which are not posted yet。

 but they're about to be posted include full details on that。

 Let me just say a little bit about how it works。 So basically。Yeah， so what I wrote here。

 this is kind of more like morally， this should be true。

 It's not actually true that I've proven this to you in class at any point。But so， well actually。

 we'll have to deal with this later this lecture， and so I'll point out where we're dealing with it again。

 and it also explains why this is true。你看 yeah。I mean， one。While有。

Proving it is just to realize that the of the jewel comes back to the framework of the grant。So。

If you think if you assume your algorithm is polynomial。

 then you can have a polynomial number of constraints。

They're actually active at your optimal position。And each one of those constraints is going to correspond to a non zero dual variable。

the only possible a nonze variable back in the prim。 right that's exactly right。

 So that's sort of the missing trick。 I'll say this again when it's relevant in this lecture。

 But basically the idea is I'll point out in this， we'll see it explicitly in this lecture。

 So I'll point out where that is。Yep。But all is exactly right。O。So right。

 so we have this linear program， exponential number of variables， polynomial number of constraints。

Maybe we can solve it by eipsoid。That's going to be the plan。 We will。 that'll be the plan。 And now。

 again， just like with the welfare and maximization relaxation， again。

 sort of the dimensions are the ones that are backward from what we can handle， right。

 So the ellipsoid algorithm， you'll recall， it needs the dimension。

 The number of variables to be small。 It can handle a large number of constraints。

 So in this linear program， it's backward。 So if there's going to be something we can solve is going to be the dual。

 So let's understand the duall of this problem。All right， so thought experiment。So we， you know。

 we're hoping this is feasible， right， you know， sort of our whole approach of having scaling algorithms work depends。

 hinges on this thing being feasible。So let's play devilil's advocate for a moment。

Suppose I wanted to convince you that this was not feasible。Okay， a proof of infeasibility。

 How would I do that， What would be sort of a convincing， short proof of infeasibility。

And then as usual， these proofs of infeasibility will be just the dual linear system。Okay， well。

 suppose。I could come up with the following。All right。

So suppose I could somehow dream up what I'm going to call pseudo evaluations。ZIS。

And I'm calling them suit evaluations because these are not。

 I'm not going to assume that these are not negative。 They can be negative。

And I'm not going to assume they're monotone。 These can be literally any real numbers satisfying the constraints I'm about to write down。

So suppose I can find these suit evaluations， these ZISs so that。The following are true。

 so first of all。Other than these indices in capital I， these are 0。 So basically， there's a Z I S。

 I mean， these things are going to correspond to multipliers and these constraints。

 These are going to correspond to dual variables。 So in particular。

 they're going to correspond to these constraints。 So outside of the bitter bundle pairs in capital I。

Implicitly， we'll think of them as zero。Okay， but now here's the interesting part。

Suppose it's the case that the max。The largest possible pseudo welfare of an allocation。

Where if I suit a welfare， I just mean。You sum up the ZISIs。Okay so again。

 this is a thought experiment， so imagine for every imaginable allocation in the world。

 if I treat the disease as valuations， even though they just made up numbers。

 if I think of them as valuations and I look at the corresponding welfare。

And I call this largest possible suit of welfare you ever see Z star。Suppose this is strictly less。

Then one minus epsilon。Times the。Suo welfare of the solution Y star that we started with that are supplying our targets。

So。S over I equal into n。Some over subsets。ZIS times y。Star I。Okay。So the claim is。

 if I can find pseudo evaluations。Meeting these properties， then certainly， there's no hope。

 And there being a feasible solution of L P，2。Okay， so this is what I'm to prove to you next。If。

suit evaluation satisfying these exist， then LP2 is infeasible。

And this is just an analog of week throughout it。All right， so why is that true？

So then LP2 is infeasible。So then we be doomed。if this thing exists。

So we're hoping this doesn't exist。All right， so reason。Well。

 so just think of these Z I Ss as multipliers。 Okay， so imagine。

We multiply the constraint here by ZIS， and we multiply this constraint actually by minus z star。

And then we add up the results。OK。So with multipliers， minus z star。

For the normalization constraints。And then the ZIS is。

So what would then be true about the right hand side？Okay。

So can suppose I multiply this by minus z star， and I multiply each of these by Z I S。

 and then I add up the results。So on the right hand side， I'm going to get a scalar。

 I'm going to get one number。Right。There's got a contribution of minus z star here。

And then each of these constraints contributes1 minus epsilon y star I times ZIS。Yeah。Well。

 by assumption， this1 minus epsilon summed over all these constraints。

 the y star is times the ZIS is， this is strictly bigger than z star。Okay。

So these constraints contribute the right hand side here， this constraint contributes minus of that。

So you add them up， you get something strictly positive。嗯。Yeah。

So right hand side is strictly positive if I multiply。

The constraints with these particular coefficients。On the left hand side。So what's the coefficient。

Of each lambda omega。On the left hand side。So fix omega， omega is just an allocation。Okay。

 S1 has2 up to SN。Deite shows up exactly once in this constraints。

So that's contributing a minus z star。to the coefficient of lambmbda sub W and the sum。Here。

 so for a given allocation， mega， it participates in exactly the constraints corresponding to bitterbut pairs IS。

 where a bitter I gets that bundle S in this allocation omega。

So summing over all of these with the multiplier ZISs。

 the contributions to the coefficient of lambda omega is exactly the pseudo welfare of omega。 Okay。

 it's exactly the sum over the bundles S going to I， the corresponding ZIS value。Okay。嗯。

So is non positive。 So again， this is contributing minus z star。

 this is contributing the pseudo welfare of omega， and by assumption。

 the pseudo welfare of every single allocation， in particular， this one， omega is at most Z star。

Okay， so minus E star cancels out all this pseudo of welfare。So given these two properties。

 now we see why LP2 couldn't possibly be feasible。All the lambdas are non negative。

So if you have a bunch of things that are non negative， all with non positive coefficients。

That's going to give you a non positive number， and yet supposedly it's supposed to be a positive number。

So there are no lambdas that could possibly satisfy this summed up set of inequalities。Right。

So again， the point is， this is just kind of a linear proof of infeasibility of LP2。 Okay。

 I show you a particular。 So you need to satisfy all the coefficients。

 I've shown you this particular linear combination of the coefficients。

 which there's no way you can satisfy。 I've made it obvious。

 You can't satisfy them by making all the coefficients left hand side and I'm positive and making the right insides strictly positive So no way。

Okay。Good。So if there are suit evaluations with these properties， then certainly LP2 is infeasible。

And the duel。Then just by definition is the set of all proofs of this form。

Okay the dual linear your system。So the decision variables are just the z star， the multipliers。

And the ZIS。These are unrestricted。And then these are the constraints so it should be the case that all energy allocations have suited welfare at the most Z star。

So ZI of S。So that's what that says。So， this is。For all allocations。And I apologize。

 I'm going to switch back and forth between the notation for allocations omega or just S1 through SN as convenient。

 but it's always the same thing， little omegas are always S1 through SNs in this lecture。

And then this should also be true。So the pseudo welfare at the fractional solution of Y star。

Should be bigger than Z star。So what I've proven to you， again， the analog of weak duality。

 which is if D2 is feasible， if this dual in your system is feasible， then LP2 is infeasible。

 so they can't both be feasible。That's a weak duality， strong duality。

 So which in this just sort of simple feasibility context， is just farca's limma。

 the theorem of the alternatives。Says it's also impossible that both are infeasible。

So I prove to you they can't both be feasible。 I'm going to state without proof that they can't both be infeasible。

 Okay， it's not that hard to prove。 but it's outside the scope of this course。

 It's just strong duality， basically。So strong duality。They can't both be infeasible。

So exactly one is feasible。All right。So in other words。

 what's easy is that if there's a proof of this form。You dead meat。But。

If there's no proof of this form， you have to be feasible。So which is great because what do we want。

 We're really we're crossing our fingers that this as a feasible solution。

 These are the scaling algorithms。 Don't forget that。 Okay， this is what we're searching for。

 These are the scaling algorithms。 So it says all we need to do， quote unquote。

 is prove the infeasibility of D2。 And then we're good to go。 at least with respect to existence。

 And theres track computational tractability as well。😊，Okay。So again， just to recap， where are we？

What I need to prove to you is that this has a feasible solution。

 you compute compute one in polynomial time， it has polynomial size support。

The way we're going to prove all three of those things in one fell swoop。

Is to run the ellipsoid algorithm on this linear system， on D2。So， approach。Run ellipoid on D2。

And the reason that's not crazy is the reason the whole reason we're looking at the dual is this has a polynomial number of variables。

 right， So this has a variable。I should have written this。 so this is for all。

These correspond to constraints in the primal， which correspond to the nonze variables in the original LP solution Y star。

 of which is a polynomial number。There are， unfortunately。

 an exponential number of constraints in the dual， one for every possible allocation as one through S N。

 But now we can only least hope that we have a separation oracle。Okay。

So let's drill down on the separation Oracle。So remember how this works。

 the separation Oracle is given as input an allegedly feasible solution。

 so in this context it's going to be candidate values of the ZISs for all allowed Bi bundlele pairs I and a Z star。

And the responsibility of the separation oracle is either to say yes。

 it's feasible or if it's infeasible to give a proof in the form of a violated inequality in polynomial time。

 and it's not trivial because there's an exponential number of inequalities。

 so we have to somehow find a violated one if one exists without checking them all one by one。

So here's how we implement the separation oracle for this particular system。So again， the input。

To the separation Hkle is Z star。And ZIS。For all bitter bundle pairs。Well。

First thing we're going to do。We're just going to check that。It's only one constraint。

That's violated， we're done， so it's infeasible， and here's why。Okay。So for the rest of proof。

 let's assume it passes that test。 Let's assume the Z Is and Z star actually satisfy this。

And let's move on to the exponential many allocations。And let's actually use。The promise that I said。

 we're going say we're going to use the existence of some good randomized rounding algorithm。

 which is not a scaling algorithm to prove that there is one which is which a good one。

 which is a scaling algorithm。 So we haven't used the existence of last week's algorithm yet。

 So here's where that comes in。So step 2。So。We have this allegedly feasible dual solution。

 these ZISs， these suit evaluations。So what we're going to do now is we're going to interpret these EISs。

 even though they're just these sort of made up numbers we're given to as a possibly dual feasible solution。

 we're going to think of them as valuations。That we're going to feed into last week's algorithm。Now。

 the EIS just could be positive or negative， and the negative ones are annoying。

 so let's actually just treat the negatives as zero。Okay。So otherwise。

So let me write them as the z plus。IS is。Which is just the max。Of zero and ZIS。

Interpret these as evaluations。嗯。And I'm going to run last week's algorithm。On these valuations。Okay。

So this is inside our separation Oracle。 We're doing this。 This is getting pretty meta。

This is getting pretty。 So we're actually， because you might remember， you know。

 what was the first step of our old algorithm。Right。Solves an LP， right。Using ill illoid method。

 actually。But for now， just think of as a black box that we had this algorithm from last week。

 that gives us a1 minus epsilon approximation。So use old the algorithm。

One thing that's important is that the algorithm from last week。 Remember the valuations are general。

 Okay， we didn't assume they were subular。 We didn't even assume they were monotton。

 We assumed nothing， which is good because we're feeding it in these Z I Ss。

 which we know nothing about。OkaySo we're just saying， hey， algorithm， think of these as valuations。

 come up with a near optimal allocation for these EISs。

 and we invoked last week's algorithm as a black box。So use old algorithm。To compute。An allocation。

 S1 up to SN。That's almost optimal。Oh， actually， so I misspoke slightly， I slightly misspoke。嗯。

Let me correct how we used last week's algorithm。Okay。So remember。Last week's algorithm。

 when I described it， it took as input this optimal LP solution， and then it did randomized rounding。

 But at the very opening of today's lecture， I said， actually。

 if think if you think about what randomized rounding did。

 it didn't care what LP solution you gave it。 Whatever LP solution you gave it。

 it does randomized rounding， and we prove it gives you back an allocation。

 which is almost as good as that LP solution。So what we're going to do is we're going to invoke the randomized rounduting from last week。

 and we're going to give it this LP solution Y star that we started with。Okay。So we're going to get。

Is。くチ？To complete allocation with， so what was the guarantee from last week's algorithm？

We're guaranteed that。The pseudo of welfare， so treating these z+es as valuations。

Is almost as good as the fractional value of Y star。So actually。

 we're doing something simpler than I than I said it first。 Okay。

 so we're here in the separation Oracle。 Like I said， we first verify this final constraint。

Assuming it passes this test， we say， okay， interpret these ZISs zeroed out as valuations。

 And now just do randomized rounding using y star。 Okay。

 so y star was this LP solution we were given at the very beginning。

 So we just the same randomized rounding algorithm we did last week。

 What we proved is that randomized rounding gives you this guarantee。 Okay。

 You get a feasible solution。 You lose only one minus epsilon with respect to the LP solution you started with。

 Okay which is very proved at the end of the last week。Allright， so now。

What do we know about this quantity on the right hand side。Well， this is right。

 so remember Z+ was obtained from the z's just by making negative number zero。

So this is only smaller。With respect to disease。And we checked that the last constraint holds。

 that was the first step。So this is at least Z star。Okay。

So this basically gives us a violated constraint。 Okay， So remember。

 the first set of constraints says everything has to have pseudo welfare at most Z star。

What this shows is that basically by using the algorithm from last week。

 it computes an allocation for us corresponding to one of those constraints with pseudo welfare strictly bigger than Z star。

The one sort of hitch is that it's with respect to these Z pluses。

 but know basically just if any of the ZISes are negative。

 you just delete that bundle and it's still a violated constraint。 so again。

 the high level point here is that algorithm from last week is a separation oracle that in polyen all time will compute a violated constraint of this family。

So yields violated constraints。YeahYeah。Alright， so let me， let me just sort of。Explain where we are。

 We're basically done。 So let me explain why we're done。So we wrote down this linear system。

 which was feasible。 if and only if there existed a scaling algorithm。

 we showed that feasibility of that linear system was characterized by infeasibility of the dual linear system。

We just invoked the ellipsoid algorithm on the dual linear system。

 I showed you how to compute a violated constraint in polynomial time。And actually。

 if you got a notice。So separation oracs usually do one of two things。 Either they say， yeah。

 you're feasible or they said， no， you're not， and here's a biology constraint。

And I just showed that no matter what Z star and ZIS is you give the separation oracle。

 it computes a violated constraint。Either the last constraints violated or if it's not。

 use the algorithm last week to exhibit a violated constraint of the first family。

It never actually outputs feasible。So our separation oracle always successfully finds a violated constraint。

So that means it's an infeasible dual system。 There's always a violated constraint。

 no matter what you give it。Okay。So。Uppsshot。First of all， D2 infeasible。嗯。Always found violation。

Which means that LP2 is feasible。So there is a scaling algorithm。

 a one minus epsilon scaling algorithm。And。Now there's this issue。

 So the last comment is just to address。The discussion from earlier。Which is okay。

We can run the e on the dual program。So how do we actually whoops？

How do we actually compute the scaling algorithm？So we run a ipoid on this dual program to certify。

In the feasibility。So what do I mean， Okay， so the ellipsoid algorithm， it' a polyno time algorithm。

 if you run it for something like end of the fifth iterations， if an LP is feasible。

 it's guaranteed to find you a feasible solution。So what do you do， You run it on D2。

 you wait into the fifth iterations。 and all along， it's been generated violating inequalities。

 And this point， you've exceeded the running time bound that we know is true for the lipoid algorithm。

Okay， so we know it's infeasible after the end of the fifth iterations。 because if it was feasible。

 it would have found one。 We have proofs of that。So we know the dual systemss in feasible。

 and moreover， these end of the fifth inequalities that the ellipsoid algorithm has generated is sufficient to conclude in feasibility for all ellippssoid knows。

 these are the only end of the fifth constraints in the world， there aren't any others。Okay。

 so we we can imagine as if this dual linear system actually only had the end of the fifth constraints that the lipoid algorithm generated。

 Okay， if we delete all the rest， we only have these end of the fifth constraints generated。

 It's still infeasible。Okay。Now we do Olie's suggestion， which is well oh， that's great。

 so in the dual linear system， we always only had a polynomial number of decision variables。Now。

 we're saying Liit algorithm has helped us focus on a polynomial sized subset of constraints sufficient to certifying and feasibility。

So now if we take the duall back using farish or strong duality again。

 we get a feasible linear system。That has primal variables corresponding only to the end of the fifth constraints that we generated here。

 So we get a prim linear system with a polynomial number of variables as always it has only a polynomial number of constraints。

 So you can solve that primal linear system explicitly and because it only has end of the fifth decision variables。

 you're going to get a results which has only end of the fifth support at most。So。

Generates polynomial number of constraints。And remember。

 constraints in the due correspond to allocations。Where here L is just the maximum number of iterations that the ellipsoid algorithm might ever need to find a feasible solution。

And so then what you do is you solve。LP2 accepts。Only with the decision variables。Sorry。

This should be omega1 up to omega l。So those are the allocations over in the dual。

 and you solve the primal with only the decision variables corresponding to these L constraints。

And the whole point is this is still feasible， even though you've thrown out almost all of the decisioncision variables。

 because the duel is still infeasible。Okay。And this you can solve explicitly。

You don't even have to use aipoid if you don't want。Plynomnal number of variables。

 polynomnal number of constraints。Okay。And so that finally completes the proof of levevy swaing。

 So this is how you compute using a second linear program， a scaling algorithm。

 That's just a list of probabilities。 It says， oh， you know， tell me your LP solution。

 tell me your y star。 okay will then output this allocationation with 1% probability。

 this other one with 3% probability and so on by the linear priming constraints。

 It has the scaling guarantee。 If the LP suggests you output something with 4% probability。

 you're going to do it with 4% times1 minus epsilon。

 and that will be true for every single bit I and every single bundle S。 as a result。

 when you optimize over the linear program to compute y star。

 you're actually unbeknownst to you optimizing over the distributional range。

 So that gives you the MDR property。 and that's what gives you the DI mechanism with a one minus epsilon guarantee。

Okay。Hardest lecture of the quarter over， I'll see you in 10 minutes。

