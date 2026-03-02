# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p14 -14-(Lecture 14_ The Price of Anarchy in Simple Auctions).zh_en -BV1fNVNzhEBg_p14-

All right，'。Let's get started on part four out a five of the course。

So this is going to be about the price of anarchy of simple auctions。And。

This has actually been probably one of the hottest areas。

Kind of mechanism design in the computer science side， at least for the past few years。

 so some of the results we cover even will just be from the past few months。

 there's sort a lot of action in this part of the world these days。嗯。And。

This is motivated okay so we've had this list of three criteria， incentive guarantee。

 performance guarantee， tractability guarantee， and it's been a while since you know we were meeting that third bullet you know with anything that could reasonably called simple it's been maybe like three or four weeks we've got a number of you pretty like proof of concepts。

 theoretical constructions in a row and so in this part of the course we really you will insist on simplicity you know whatever the costs may be okay。

So。Pretty much everything in this part， there'll be no question。That the auctions are simple。

 Now to be clear， when I say an auction is simple。 in this part， I mean， it's simple to describe。

 it would be simple to implement。 I don't necessarily mean it's simple to play in。

 like a DI mechanism。 Actually， even the big mechanisms。 You know。

 while there is this informational assumption that you know this common prior。 At least you know。

 it's clear what you're supposed to do。 You're supposed to just do direct revelation。 Okay。

 So that's easy for the bitterder if you believe in the prior。 These will be as where。

 it will not be at all clear how you're supposed to play as a bidder will not be clear what the equilibriumria are。

Despite being unable to solve for the equilibrium and figure out what they are and the same spirit as the price of anarchy results from last quarter we'll be able to prove that whatever the equilibrium are。

 they're good， they're near optimal。So these are the two things we're looking for。

We want simple auctions。That have near optimal equilibrium。

 what kind of equilibrium it'll depend today。 I'm going to keep things simple。

 just talking about pure Nash equiria。 but next week， we'll move on to Bays Nash equiria。

 as you might expect。All right，Today I want to go back to a familiar scenario。

 it's also the same one we sort of had in my last lecture。

So I want to think about an allocation problem， which we now know is reasonably complicated。

 some modular evaluations。Okay， so M non identical items。And each bitter eye。Has a submodular。

Valuation V I。 And don't forget what a sub modular mean。 That means diminishing returns。So if you。

Add an item to a bigger set。The marginal value is less than if you add it to a smaller set。Okay。

So this is a scenario we've seen many times。 you know。

 before we were thinking of somehow these evaluations as being provided as input。 and as you'll see。

 that's not really going to be how we think about it today。 But you know。

 roughly think of the valuations as being a black box supporting demand queries。 But really。

 we're more thinking that there are bidders out there that。

 we're expecting to be able to ask demand queries if they have to。So again。

 just to remind you about this setup， you know why is this such a good sort of challenge scenario without incentives。

 we know how to get a constant approximation， therefore with a big mechanism now we know how to get a constant approximation。

 but we don't know good de mechanisms for this setting， okay only for special cases like coverage。

So what if we sort of abandon this exercise of trying to sort of come up with these complex synthetic battle mechanisms and we just sell these items on eBay instead。

Is there any math we could do that would sort of indicate whether it would be a disaster。

 or whether it would actually be okay？So that's kind of the point of this lecture。

 What would happen if that's how you tackle this problem， You sell them all event。All right。

So how are we going to model selling M items on eBay。

 we're going model it as a simultaneous second price option。Okay。So I'll call these S2 A's for short。

As for simultaneous two for second price。So each bidder。A。

So this is the action space or the bid space， it's very simple。Each bitter eye submits a bid。BIj。

For each J and U。好的。So I want to emphasize how different this is than all of the auctions that we've seen or almost all of the auctions that we've seen thus far。

 I guess with the exception of maybe Kelsso Crawford。

So a bidder has an arbitrary submodular evaluation。 Okay， there's M items。

 There's two to the M possible bundles。 a bidder could get。

 It could have a different private value for each one of those two to the impossible bundles。

 We have no idea what any of those two of the M numbers are。

 And we're not even we're not going to ask a bidder for anything but vanishing only for small fraction of it。

 okay。So a bidder is only ever going to be able to express M numbers， one per item。

 even though it has two to the M things to say。so in other words， you know。

 I talked about how action and type spaces can be different。 Direct revelation they're the same。

 back in indirect revelation mechanisms。 We're thinking about cases where the action space could be way bigger than the type space because you have history dependent strategies and consistent with any type。

 Here's a case where you have an action space way smaller than the type space。Alright。

 so it doesn't even make sense to talk about direct revelation right in this mechanism。 Okay。

 there's no way to actually directly reveal evaluation。It's really very different。

So what do we do with these beds， Well， for each item separately， we just run a Va。Okay，S。

So each item sold separately。We a victory auction。啊。And so a well motivated goal， you know。

 this may be good。 This may be bad， but I would just want to understand which is which。 Okay， so。

 you know， it's， it's just try to understand the performance of this。So how good are the equilibrium？

And again， for today， I'll keep things simple。 Just talk about pure naashlibria。

 but we'll extend those in later lectures。All right。Any questions？Makes sense。All right。

 so there's sort of there's an issue with second price auctions and trying to analyze their equilibrium deria。

 even actually in the basic case of a single item option。

 even if you go all the way back to lecture 1 of 364， a okay。

So there's an issue with second price auctions of overbidding， again。

 equiria that exists only because of bluffing。So this is easily appreciated by example。

So imagine we just have two bidders in one item that is we're just running a regular old victory auction。

And bitter one wants the thing。And Biter2 could care less。

 Biter 2 has some small epsilon valuation for it。And let's suppose it's a full information game。

 which again， is weird for auctions， but I'm just going to use it for an example to make a point okay。

So now assume that for some reason， they get stuck in the following equilibrium。

The second bidder bid is really high。Just because， just as a bluff。And you， basically。

 the first bidder gets scared and walks away， been zero，So this is a N equilibrium， actually。

 if you think about it。 So neither player can increase their utility via unilateral deviation。

 Okay Bider 2 is obviously happy。 There has no incentive to do anything。 Bider one。 you know。

 it could raise its bid and outbid the second bidder。

 but then it would have to pay one for it because it's the second price auction and that would cancel out its value。

 It would get utility0 just like it has now。Okay。So this is a Nash equilibrium。

 a pure Nash equilibrium。That obviously has terrible， terrible welfare。Okay。

 the optimal welfare is one， this has welfare epsilon。Okay， but this， you know。

 this is one of those examples that just kind of says， okay， it's not that it's a bad question。

 It's just that we don't have all the kind of definitions and conditions right yet to do the interesting theory。

In particular， you look at this and you're like， well， you know。

 this is a pretty risky strategy for bidder 1。 You know。

 what if a bidder 3 shows up that has value 10 or something， right。

 then it's going go ahead and bid 10 and this bidder 2， you know， sorry， that's not what I meant。

 So you can imagine that some other bitterder。You know bid something like one minus epsilon。Okay。

 and then bid 2 is going to continue to win。 It values on the epsilon。

 And it's stuck with a bill for 1 minus epsilon。 Okay， and has a super negative utility。 And really。

 for all it knows， that can happen。So it's highly exposed。

 It's not really clear why bitter 2 would do this。 So what we're to do is we're going to focus on equilibriumria。

 you know， where there isn't over bidding in this sense，So we're going to approve welfare bounds。

For no overbidding。Equilibria。 And for today， we're going to talk about pure Nsh equilibrium。对。Now。

 there's different ways you can。Sort of talk about no overbidding that vary a little bit。

 but they're not really relevant for today， so I'm not going to make a big deal of it。

 but let me just sort of briefly mention it。So when I say I focus on no forbidding scenarios。

 here's two different things that could mean。The first thing I can mean is I'm just going to define the strategy space of a bidder to only use bids where it doesn't overbid Okay。

 so I could actually in the victory a， I could just literally say， hey， bidder number two。

 I'm going define your strategy space to be between 0 and epsilon。

 Then it's obvious that in any na equilibrium， there's not going to be overbidding in this sense。

 That would be kind of the draconian way。 A second way would be like， I let bids bid。

 whatever they want。There's some equilibrium will have overbidding and some will not have overbidding。

 some will be good and some will be bad。 and I'll just give you guarantees for the equilibriumria that don't have any overbidding。

 So are sort of the two different approaches I could choose。

 So're almost the same one differences is is in the second setting。

 in the first setting sorry in the second setting where the bid space is everything it's sort of harder to be in equilibrium because if you think about it。

 there's more deviations So for something to be in equilibrium it has to be that no deviation can make you better。

 And so if I simply disallow you from doing a bunch of actions， you have fewer deviation。

 So it's easier to be in equilibrium。 on the other hand， if you're allowed to do crazy deviations。

 including overbidding， then it's harder to be in equilibrium you might have less of them。

Everything we say in today's lecture， just won't matter which way you do it。 Okay， both of them work。

A coupleup other things。 So， you know。What is know no overbidding， what does that mean exactly。

 So the no overbidding condition that we'll need today is that if we look at the items that a bidder actually wins。

Then what it bid for those items and some is no more than its value for those items。

 so it's not for every single set in the world。 It's just for the set it happens to win in the auction。

 And then the second thing is， is， and I'll leave this as an exercise。

 an optional exercise is it's easier to parameterize the bounds will give。

 So as a function of how much people overbid， you get graceful degradation in the price of energy bounds。

All right。So。All right， so now we're ready to go。 So now we've got everything we need to prove some good balances。

So let me just tell you the notation I'll be using。So。The bids now， first of all。

 they're indexed by the players。 So you have a M vector for each of the N players。

 Each player gives you a bid for each of the M items。Okay， so we have。N bid vectors。

 each of which is itself an M vector。So SI of B is just the items that I wins。

Meaning the items on which I is the highest bidder。

 remember we're just selling each item with a separate single item auction。

 highest bidder wins on each item。Items， I wins。And then PG。

Is the price that the winner of Good J pays， which of course is just the second highest bid on Good J。

Okay。All right， so now no forbidding。So again， this just means if you look at the bundle of goods that a bidder actually wins。

 the sum of its bids on that bundle is not in sum more than its value for that bundle， okay？

And so again， this is going to be like a stark violation of no overbidding right， because， you know。

 in this case， the second bidder actually wins the item。

 It's value for what it God is epsilon as bid is one。 Okay， And again。

 it's because in a second price auction， you can have such a big difference between what you pay and what you bid。

 That's why this can happen。So B satisfies no overbidding。If。For all I。If I look at what you bid。

On what you win， that should be bounded above by your value for what you won。Okay。

So that's what I formerly mean by no over bidding。So restricted strategy spaces or whatever reason。

 as long as this' is satisfied， we're going to be good to go。Okay。All right。

 so what might we hope to prove， Okay， what's the best， know。

 can we prove maybe that every equilibrium with no overbidding is fully optimal。

 and maybe that's true。Well， so let me show you that there are limits even under this condition on what kind of welfare guarantee we might be able to approve。

So here's an example showing that。We're not going to do better than 50%。对。

That's going to be the best case scenario。It's going to be a simple example that shows that。

Two bidders， two items。Let's say the items are called X and Y。Both bids are going to be unit demand。

 remember unit demand is a special case of submodular， special case of gross substitutes even。

And let's say that the first bidder really wants x。But if it can't get X。

It it's okay if it gets why half is happy。Ands better choose the opposite， it really wants why。

But better X than nothing。对。So what be the optimal welfare in the setup？Yeah。

So if you just give x to 1 and y to2， then you get an optimal welfare of two plus two or four。

And it's easy to come up with。Pure equilibriumria that actually do implement that optimalum allocation。

 But remember from last quarter， games in general have multiple equilibriumria。

And there's different ways you can approach this， but what you'd love to do is you'd love to prove a bound on every single equilibrium。

 or in this case， every single equilibrium with no overbidding， okay， that's the price of anarchy。

 the worst case equilibrium。So there's another equilibriumria， which is not good。

And it sort of has this flavor， although you'll notice there will be no overbidding in this example。

So for some reason， even though one really wants x， it bids zero for it。

 and meanwhile it bids1 for y and then vice versa for2。Okay。So。Bitter 1 gets y for free。

Bitter 2 gets x for free。Okay， so they both have utility one。

And even though they want the other good more， they don't have an incentive to go get it， right。

 because if， for example， Bider 1 does make a move and outbid bidter2 for x。

 it has to pay one for that good。 So it gets one more value， but it has to pay one more。

 so it cancels out。So again， no unilateral deviations are helpful。And so， this is。

Pure strategyastic Libria。And the welfare is only two。So， half of the optimal。

So this puts a limit on what we might be able to hope to be true。Allright， so the goal for today。

Is a theorem of Christtualou， Covax and Shapira。A little bit ahead of its time， actually。

W whichhich says。As long as bidders have some modular evaluation functions。

 actually it's more general， as we'll see， but for now some modular valuations。

If B is a pure geneticnastic Libo。With no overbidding。Then the welfare of B。Is indeed 50%。

Times the optimal welfare。So this is， in fact， this simple little example， two bidders， two items。

 unit demand bidders is a worst case example for no overbidding equilibrium in second price simultaneous options。

So that's pretty nice。 again， let me remind you， we have no D mechanisms that get close to this guarantee。

 It's sort of apples and oranges comparing them， but just you know ballpark。

 we know how to do this with just centralized poly approximation algorithms。

 We don't know how to do it with D mechanisms here。

 It's happening for us at pureache equilibrium okay。Now， as you know。

 sometimes in games you don't have pure natural equilibrium。

Turs out in these games there does always exist a pure N equilibrium。

 I'm not going to prove that because we're going to show that this bound applies more generally to other equilibrium concepts which do exist always。

 but you know it's not a vac state， okay， there are pure equilibrium in these games。Okay。

So any questions？To the rest of the lecture is about proving this theorem。All right。

 so I want to do a warm up。 I want to prove a special case of the theorem。

 The general case is actually not much harder， but I think it'll be easier to understand if we just do it in pieces。

So for starters， I want to assume that all bidders are unit demand。Okay。

 which is a special case of sub modular。 Let me just remind you that the one half example already applies to unit demand bidders。

 Okay so one half is already the best we could prove， even just for unit demand bidders。So， warm up。

Each VI unit demand。So we again remember what that means。Of the foreign V of S is equal to the max。

J and S。So basically， each bidder has these VI Js， these singleton valuations。

 If you give me a bundle， I throw out all but my favorite。

Okay that's what I mean by unit demand valuations。The other thing I want to mention is that。

 if you think about how would you actually bid in this auction？This is， it's not clear， actually。

 know， if you actually had a time deadline and you had to buy a bunch of stuff on ebay by， you know。

 tomorrow。It's a little tricky to figure out how to do this。 And in fact。

 if you were unit demand it sort of really exposes the problem。 In fact。

 we I don't know if you remember， but we actually made fun of this auction format when we were talking about spectrum optionss in 364 a。

 one of the rookie mistakes was to do something simultaneous instead of ascending but it's you know we're just going we're gonna it's interesting to analyze the simultaneous case in any case。

Suppose you only want one item， right， even suppose like your value for all the items is the same and you only want one of them and a simultaneous second price auction。

 Should you， you know， like target a whole bunch of them at a pretty low bid。

 hoping you get lucky and get one of the items at a bargain。

 Should you kind of go all in on a single item and bid really high on a single item。

Sort of not clear。 You have to trade off the risk of winning too many items because， again。

 just because your unit demand， if you bid on multiple items。

 you might win multiple items and you have to pay for them all。 Okay， so you get value from one。

 but you have to pay the piper for all of them。 So you have to hedge the risk of winning too many versus the risk of winning too few。

 I E not， okay。So unit demand is already kind of an interesting case。All right。All right。

 so this is so this is gonna be a price of anarchy bound。 And you might recall from last quarter。

 there is a pretty， you know， common template for how you prove these bounds。

 And there'll be some small differences。 but still this argument will roughly follow the same template。

 So the first step。 So obviously， you have to use the hypothesis that you have an equilibrium。

 Okay And so what does that mean， It means nobody can do better by deviating。

 So the first step of one of these price of anarchy proofs is always to figure out， okay。

 let me kind of creatively concoct a hypothetical deviation， which some bidder could take。

 but they don't。 that gives me a lower bound on this bidder's utility at equilibrium。

I do that once for each bidder。 Okay and usually the optimal solution somehow suggests these hypothetical deviations。

 So that gives me a lower bound on the utility of every bidder。

 And then somehow I'm going to sum up all of these utilities。

 And I'm going get some weird entangled thing of the optimal in the equilibrium outcomes。

 which I have to disentangle happily， that turns out to be easier in these models usually then in the stuff we talked about last quarter。

 And then eventually you saw for the price of anarchy bound。

 So we'll see all those steps coming up coming up now。😊，But again。

 you often so the first step again is just figure out the right way to invoke the equilibrium hypothesis。

So， let B。The appear a equilibrium with no overbidding。And so the deviation， so。

 when we' were talking about things like routing games in last quarter， you know。

 what we basically said is like， look in the optimal solution。

 this bidder is taking this path from here to here。 And it's not in the equilibrium。 Why not？

 And we sort of thought about this path in the optimal solution as a hypothetical deviation。

 that's how we got started。Now， it's a little the one thing that's sort of interesting and different about these auction problems。

 We can again do the same reasoning。 Okay， so we have some equilibrium。

 There's some allocation of the items。 Maybe the welfare isn't that good。

 There's some other optimal welfare maximizing allocation we wish we had。 And so again。

 we sort of want to go to bitter ride like。You wound up with， like in this example。

 we want to go up to Bi X and we want to say， you wound up with good Y。

 you're supposed to get good X。 Why don't you have good X。Okay。

And so but the issue is that a bidder is not in a position to just grab a good off the shelf， okay。

 the action space of the bidder is just bids。So the deviation should have the form， you know。

 if this bidder is supposed to get a given item， why didn't it bid for that item。

 And that's going to be the deviation we're going to look at to derive a lower bound on utility。Okay。

 its let be more precise。So consider a bitter eye。And consider the optimal allocation， again。

 just for the analysis。 Okay， we want to bound the equilibrium。

 We we're trying to relate it to the optimum。 So think about the optimum， whatever it is。

 this bitter eye gets some item unit demand。 So everybody gets it most of one item in the optimal solution。

I get some item。Let's call it Jstar I。Okay。The item I gets in opt。If I gets no item。

 then just think of this as the empty set or no okay？Now again。

 the reasoning is we're at this equilibrium， the bad cases where the bitter eye has some other item in the equilibrium。

 we want to say， dude， why didn't you go after this good J star of I that you're supposed to get？

So here's how we implement that。We say， well， one thing you could have bid bitter eye is you could have gone all out for good J。

Sorry， good J Star bye。And given up on everybody else。Remember， these are unit demand bidders， okay？

So this is basically what it means for bitter eye to target a particular item。

 This is kind of the best it can do。 Give up on everything else。 Remember。

 we're thinking about sort of no overbidding。 So this in some sense。

 is the biggest bid that's either allowed or if you like。

 makes sense for bitter eye to go for the good it's supposed to get the optimal solution。

So this is the hypothetical deviating bid vector B star I we're going to use for I。All right。

 so because we have an equilibrium， I's utility， bidding whatever it's bidding here is at least as large as its utility from bidding this。

Okay。Oops， since B is a PNE。All right， so what is I's utility in the equilibrium？Well。

 it's just its value for whatever goods it gets。Minus what it has to pay。For whatever goods it gets。

And then this is at least as large as if it deviated to this。Allright， so。And this。

 when I talked about how in these price of anarchy proofs。

 whenever you start seeing sort of entangled versions of the equilibrium and optimal outcomes。

 this is the kind of thing I was referring to Okay。

 some bid profile that's a Frankenstein pieces of the optimal。

You of the optimal allocation and pieces of the equilibrium。 Okay。

 so these are the things we often sort of have to work hard to relate back to what we actually care about welfare at equilibrium and welfare at the optimal allocation。

Now， in this case， it's going to be pretty easy， actually，So， on the right hand side。

RightSo you know we're just looking at I's value after it deviates and we're looking at what it has to pay after it deviates and remember you know because the deviation is so simple。

 this right hand side is also very simple so bitter I has basically withdrawn from all goods other than J star of I on the right hand side so the only thing that's irrelevant on the right hand side is this one good J star of I。

Right at the other items， it's not winning and it's not paying anything。

So let's think about what could happen on this right hand side。 Okay， just on this one good。Okay。

And this is what's a little weird。 I mean， even though bitter I is targeting this item。

 there's no guarantee that it's going to win it with this bit of V I J or V I J star F I。

 There might be some other bitterder at this equilibrium that's bitting even higher。

 totally possible。 Okay So there's going to be two cases。

 One in which bitter eye through this deviation actually acquires this item and one in which it doesn't。

 Okay we have to deal with both of them。 Both are possibilities。So case one。

 let's suppose it actually wins。So when it does this bid。

It's at least the highest bid by anybody else。At the equilibrium。Okay。So， then。

The right hand side is just going to be the difference of these two。Okay。So it wins。

 it derives this value from winning。And this so it's going to be the highest bid。

 this is the highest bid by anybody else， so that's going to be its price。

 it's the second price auction。So this is just going to be max k not equal to I。VKJ star I。Okay。

So that's the case where it wins。Where this deviation actually gets it。

Manaages to have it acquire the good。So case two is where it loses。And then， well， basically。

 there's nothing happening on the right hand side， it loses， it gets nothing。 It pays nothing。 This。

 again， is going to be lower bounded by the same quantity。 Okay。

 this is going to be negative in this case。So， in any case。I'm going to simplify this。

 so this is what we got immediately from the equilibrium condition。You know this。Whatever it is。

 this is non negative these prices。 So if I delete this subtracting term。

 the left hand side only gets bigger。O。So just to simplify my life。

 I'm going to throw out that red circle term。So I'm going to have this on the left hand side and we just agreed that this right hand side。

 whether it wins this item J star of I or loses it。

 in any case I can lower bound the right hand side by the difference between its value for this item。

 J star that it's supposed to get and the highest bid by somebody else at the equilibrium。So V， I。

 J star I minus。Max can equal to I。You have J stare。看。So that's what we can conclude。And actually。

 let me， this is a term that's being subtracted。 So let me just make this even smaller。

Just to simplify the later calculations， let me just sort of throw I back in there。Okay。So again。

 I'm taking the maximum over more things。 So that's a bigger number。 I'm subtracting it。

 So this right hand side has only gotten smaller。Yeah， good。All right。

 so that's just invoking the equilibrium condition。Targeting the good。

 You're supposed to get the optimal allocation and some simplification。 All。

 So this was just for one bitter eye。 Obviously， I can do this for all of the bidders and get these analogous lower bounds on their utilities。

 or in this case， in their contribution to the welfare。 So again。

 don't lose sight kind of like the high level picture。 What are we trying to do。

 We have an equilibrium。 It has some welfare。 We know it's not necessarily optimal。

 We want a lower bound on its welfare in terms of the optimal solution。

Here I'm at least getting a lower bound on the contribution to the welfare of a particular bidder。

 So that's good news。 Okay， and on the right hand side is some component of the optimal welfare。

 So these two terms are exactly the kind of things we want。

 Eyes contribution to the equilibrium welfare， lower bounded by I' contribution to the optimal welfare minus some error term that we'll have to deal with eventually。

 Okay so that's the whole point of this。Okay， this is for a particular bidder relating the contributions to the two welfares。

 So now we just sum over the bidders。 See what we get。So summing over eye。So we sum this over eye。

 what do we get？What's another name for this summed over eye？Yes， welfare B， exactly。

So the welfare of our equilibrium。RightSo this is just right。

 so it's a second every item sold in a second price auction。 every item goes to exactly one person。

 right， These are the items that go to bitter eye。 it has some welfare。 you sum over all the bitters。

 you pick up all of the welfare of the equilibrium allocation。

So the left hand side of Sder Vaai is just the equilibrium welfare。 How about this， sum de I？Good。

Exactly， so the optimal solution， just every bidder gives at most one item。

 we're just summing over the bidders looking at their contributions。So this is exactly what we want。

 This is perfect，So let's look at the error term now， minus。Some。Overall， the bitters of。

This weird thing。And this is sort of the residue of our entangled equilibrium optimal。Turms。

So in what sense is this an entangled version of the optimal and equilibrium， well J star I。

 so the choice of the item， this is a function of the optimal solution。

 this is what I supposed to get in the optimal allocation， these bids are the equilibrium bids。Okay。

So we have like some bidder。 It's getting some item， know， item number  three in the equilibrium。

 We're looking at some other item 17， I guess in the optimal solution。

 But we're looking at whether are the bids that everybody put on that item in the equilibrium。

And then we hit the highest。Okay。So this is the error term。So we're hoping this is small。

 this is small， we're good to go。All right， so let's。Try to understand this。 Notice to this point。

 we have not used the over bidding assumption。 So that presumably。

 and we know this is not true without that assumption。 So that has to come into play somewhere。

 presumablysumably， it's controlling the error term。All right， so。Good， so let's think about this。

As follows。Good， so， yes， all right。 So let's think about this in the following way。 So this。

 we want an upper bound on this。 right， This is our error term。 You want to say it's not too big。

So let's think about it。Rather than iterating over the bidders and looking at the item they get in the optimal allocation。

 let's iterate over the bidders。And look at the item or items that they get in the equilibrium。Okay。

Notice this is just summing over every single item that there is。So remember S sub B。

 this is just in the equilibrium， which items does I win， every item goes to exactly one person。

 so you sum over I， you sum over their Js， the sums over every single good exactly once。

Here we're summing over every good at most once。Okay。

 so this is just we're looking at the items allocated in the optimal allocation。

And so this only gets bigger if。Right， so let me first write it this way。But there's a reason。

 whoops， since no one I wanted， sorry， Jay。There's a reason I wrote it this way。What is？

The highest bid on a good J， which item I wins in the equilibrium。Good， right， so what is this。

 these are the items that I wins。Under what conditions do you win a good。

 well if you're the highest bidder。So for any good J， which I wins。

 we know this highests bit is simply I's bit。So this is simply equal to BIJ。

 that was the purpose of this reorganization actually。And now we're home free。

Right so we have error term。At most sum over I equal 1 to n。

 sum over J that I wins in the equilibrium。Of eyes bid。What is this？Boed above by。あれしないてのまぱ。Yeah。

So this is where we use the nova bidding。By virtue of I bidding B I Js and all this stuff that it won。

 we know its value。 We're assuming that its value has to be at least as large。 Okay。

 the price it pays might be less because it's not paying its bid。 It's the second highest bid。

 But the assumption of the equilibrium is that sum of the bids is most of the value。

We only need it for the actual set of bundles that I win。So by no overbidding。

And so now we're just back to the same old， some over the bidders of their contributions to the welfare。

So that means this is the most the。Welfare。Of B。对。So plugging this back in， what have we shown。

 We of B is at least opt welfare minus welfare of B。 Okay。

 so add welfare of B to both sides divide by  two and we're done。

So just rearrange to complete the proof。Welfare of B is at least half that about。Okay。Good。

So all of the sort of key steps that we should， you know， I know it's been a while。

 but all of the price of energy analyses that we did last quarter had more or less the same flavor。

 So again， start by applying the equilibrium condition App at once for each bidder with a judiciously chosen deviation。

 We had to be a little more clever here because there's sort of I means a wider range of deviations we might pick because there's this mapping between bids and allocations。

 but the deviation we did is probably the first one you think about we wants you to have an item J。

 So just go all out for item J。That gave us a lower bound on the utility of every single bidder。

 we summed over those to relate welfare and of the optimal and equilibrium up to an error term and the error term is more or less corresponding to the disentangled stuff that we had to deal with last quarter and so then dealing with the disentangled stuff we had this reversal of sums in this overbidding hypothesis to control that error term and then you just saw for the price of anarchy so those are all basically the same four steps that I taught you in the fall。

Any questions？So that's a special case of unit demand bidders。

 Okay And this generalmodular case is not a lot harder， but I just sort of wanted to。You know。

Have a delimiter on the pace that the notation came at you。Okay。

 so I want to extend this to sub modular next if there's no questions。So there is one kind of。

There's one new thing that I really need to teach you for it to be clear about how to proceed。

 the main thing that's unclear。So if you just think about， I mean。

 basically we'll get the same proof to work as a modular， the main step。

 which is really not clear is this very first one。Okay。So。If bidders are not unit demand。

 if they have general submodular evaluations， now， again， I can look to a bidder and say， okay。

 what does this bidder have Well from in the optimal allocation has goods like 3，5 and 7， Okay。

 not just one good， but many。And now I have to somehow concoct a bid vector， which kind of says。

 you know， all right， go after all of the goods 3，5 and 7， and don't go after the rest， perhaps。And。

 but how exactly should I set， you know， there are no V I Js for general smod evaluation。

 There's only values of bundles， right， So maybe a value like 25 for goods 3，5 and 7。

 So how should I set your bids for good 3 and 5 and 7。 Should I， Should be 25 over 3。

 Should I do something smarter or what。Okay， so that's the part which is not totally clear about extending this to some modular evaluations。

 What's the B star， Okay， and it's actually a very。

 a very nice answer for what the analog of B star should be。 So I need I'll teach you that lemma。

 and then we'll be able to get the same proof template to work for some modular。All right。All right。

 so general case。How to choose。B star， I。All right。So here's an important lima， okay？

Just about some modular evaluations， which gets used all over the place in this part of the world。

So it's yet another property of some modular evaluations one you haven't seen before。

So every submodular valuation， submodular monotone valuation。

 can be represented as a maximum over additive valuations。So here's what I mean。IE。There exists。

Additive valuations。 So remember what that means。 that just means you have these singleton valuations for the different singletons。

 And then if I give you a bundle， it just adds up。 Okay， so unit demand is a max。

 additive just as a sum。So there exist M vectors。No promises on how many。Possibly a lot。

 but it's not going to matter because it's only for the analysis。

So let's say there's going to be R of these vectors。 each one is indexed by the items。So that。

For all bundles。VI of X。So basically， what I'm going to do is I'm going to take each of these added evaluations。

 I'm going to。Evaluate a bundle S。On。Some given additive evaluation。

And then I look at the biggest valuation you have。Under any of these。Okay。So conceptually。

 just think you go A1， A2， A3， all the way up to AR， you say for this out in evaluation。

 what would be the value for this bundle and you look at the highest number that you ever see。Okay。

So， just， for example。So let me show you a sense in which this is kind of a very nice extension of unit demand。

So V is unit demand， which of course is a special case of submodular， so if this lemon is true。

 it'd better be a max of additive functions。Just use one m vector per item。Where。

What should be the form of the E additive valuation， Do you remember， unit demand valuation。

 This is characterized by。U。Vjs。Do you see how to represent a unit demand valuation as a maximum of additive functions？

Very simple additive functions are enough。It just BJ。Right。Exactly。So this should just be VJ。

FL equals J，0 otherwise。Another way you can think about this if you want。

You can think about one of these sums as a dot product between the characteristic vector of S so a one when the element's there and a0 when it's not there。

 so a dot product of the characteristic vector of S with this vector AI。O。And so in that case。

 with these， you， basically you're just saying。Yeah， anyway， that's one way to think about this。

 and then you take the max of all of them。So unit demands are just the special case where each vector is all zeros。

 except for one special to an item。Good。All right， so right so before I prove the lemma。

 what else should I say， so the converse of this lemma is false actually so there are valuations which are the maximum added evaluations。

 but which are not submodular。So the maximum of additive valuations is a more general class。

I'm not going I'll try not to use this terminology too much， but just sort of FY I。

 Sometimes these are called X O S for X or of or of singletons， don't ask。嗯。

And then they're also called fractionally sub additive。Again， maybe don't ask。嗯。

So this is a class evaluations which is studied in its own right， and in fact。

 the one half guarantee I show you will apply not merely to submodular evaluations。

 but more generally to any evaluation which is a maximum of added functions。

 but in particular submodular evaluations。Okay， so any questions before I approve the lima？

It's not clear why this is useful， but just looking ahead a little bit， know。

 the motivating question was， okay， in unit demand， when you consider a deviating vector。

 it was clear what it should be， it should just be like you go after the one item。

It turns out that you know these additive evaluations are going to be perfect for supplying the hypothetical deviations in the price of anarchy proof。

 okay， so that's why we're doing this Okay， this representation tells us exactly what hypothetical bids we should use that fits actually very snugggly。

Back to everyone clear， before we approve limitma， what it says。过。All right， so proof of limo。

It's pretty easy， actually。So I'm just going to explicitly tell you。

 so hand me a sub modular evaluation v sub I， I'll just tell you exactly what these vectors are。

There's going to be one， there's going to be a lot of vectors， a lot of added evaluations。 In fact。

 it's going to be M factorial。So one added evaluation for each possible way， I could order the items。

So how exactly do I define each entry， so remember this is indexed by the items？Well， basically。

 so for an ordering of the items， I just imagine giving the items to the bidder one at a time in this order。

Okay。And so for the entry of this valuation corresponding to an item J。

 I just look at the jump in the bidder's valuation when I get around to giving it Bi J。

It goes from some previous valuation when it had all the previous stuff to some new valuation。

 once I give a J also， I look at that increase， I define the J entry of this AI pi to be that increase。

 that marginal value。Okay， so I is just fixed for the whole proof for a given ordering of the items and a given item J。

Ill just define this。To be。So S pi J is just going to be the stuff earlier than J in the ordering pi。

And I look at the extra value you get from also having J。没有原。So again， this items。Before Jay。Yinpai。

O。Everyone okay with that definition。So there's M factorial added evaluations， one for each ordering。

And the claim is this works。so this is it。 So I'll prove it to you。 But this is the。

 this is the construction。 So you give me a submodular evaluation V I。

 I define these M factorial additive evaluations。 And the claim is that this is satisfied， okay。So。

We have to prove this for every possible bundle s。So fix some such bundle。All right。

 so I'm going to prove two things， first of all， that there exists a pi。

 so there exists in added an evaluation for which this holds with equality。And secondly。

 for every pie， this can only underestimate it， the right hand side can only be less because are the two things they have to show。

So。Let me exhibit an ordering， exhibitbit a pie for which quality holds。

It's just going to be any ordering for which the items in S appear first in the ordering。

Okay so there may be many such orderings， maybe there's 100 items and S has 10 items。

 any ordering where those 10 items come first， I don't care about the relative order as long as their first pro claimers of quality holds。

So， if S。Is a prefix of pi？Then sum over JS。A pi J is exactly your EIS。iss that clear？

So how AI is defined， you just add the items in order from front to back and so literally you just in this if you use this particular pi。

 you're literally just accumulating the value contributed by these items in S and no other items have showed up to screw up the calculation if you want you could write this out or just be a telescoping sum。

Now， the other thing I have to show is that。Other orderings。

 other addeditive evaluations can only underestimate the value。

 because I want this to be the max over all orderings。And this is going to follow by some modularity。

Which is important for the proof。So otherwise by sub modularity。Well， what's different， okay？

So say the bundle has 10 items， right， So in any case， this is a sum of exactly 10 things。

The marginal increase caused when this item showed up。

So the only difference between when S shows up as a prefix and when the S doesn't show up as a prefix and when it doesn't show up as a prefix。

 I mean， some of those other 90 items are interspersed in the middle。

So you maybe get the first item of S， then you get some item outside of S。

 then you get another item of S something outside of S and so on。So really。

 you're doing exactly the same computation in both， except here， when an item from S gets added。

 there might be extraneous stuff outside of S already there。What does some modularity tell you。

 it tells you the marginal value of goods is decreasing， the more stuff you already have。Okay。

So by virtue of there being things outside of S。When you do the margin evaluation calculation。

 you get something that's only smaller。So。I'm just going to write that。喂。

So there's a few ways to think about it。 another way to think about it is basically。

 for an arbitrary ordering pi， I could construct an ordering in which S is a prefix。

 which is only higher。RightSo in other words， for an arbitrary ordering。

 I could just look at the positions in which the items of S show up。

I could define a new ordering where those are first in that exact same ordering。

 The only difference is that when I compute marginal values here， there's only fewer items involved。

 So the marginal values are only higher。 Okay so that's why if you get V of S here。

 you got to get something smaller in any other case。 So is sort of immediate bymodularity。

 if you can keep all the notation in your head。Any questions about that？O。All right。

 so that's worth remembering， so mod evaluations are a special case of the maximum of additive evaluation。

So。Time to prove the CKS theorem。All right， so the structure is going to be pretty much exactly the same。

So we start with an arbitrary purenaic equilibrium， which does not suffer from overbidding。

Before we said， let's just look at the item。 J star of I that I gets in the optimal solution。 Now。

 they're not unit demands， and they may get many items。 So let S star。I。The items I gets in optt。

And now here's the clever part。 Okay， so we're going to use this representation in terms of added evaluations to choose this deviation by which I targets this bundle S star I。

So bylemma。We can choose。An add evaluation。I'll call it a star I， again。

 this is an M vector indexed by all of the items。Such that。um。The following two properties hold。Okay。

O。So。What does the limitma saying， the limitma says consider a submodular evaluation。

And then pick if you want your favorite set S，So my definition， this says for your favorite set S。

 which in our case is S star I。If you operatei pick a set S。

 there will be one of these constituent added evaluations for which it gives you exactly the right answer on that particular bundle S so by virtue of this being the maximum over these added evaluations。

 one of these achieve this maximum。So what we're saying over here is we're saying given S star I。

 the bundle I supposed to get the optimal。Focus on the added evaluation。

 which attains this maximum for that bundle， the optimal items， the items and the optimal solution。

Now for any other bundle， any other bundle is the maximum over all of the additive evaluations。

 so for any other bundle S， its value is whatever it is。

 it's at least as large as every single additive valuation representing the functions so in particular is at least as large as this added evaluation a star。

So， again， one way to think about it is， you know， some mod evaluation。 obviously。

 it's not an additive function。 It's a maximum of additive functions。

 But if I sort of only care about one bundle， I can sort of think of if as if the valuation is additive just for that one bundle。

 Now， on other bundles， it might underestimate， might get it wrong。

 It's only going to get wrong by being too low。 It's not gonna be too high because everything's a maximum of these additive evaluations。

 but on one bundle， it'll be correct on everything else， itll only be too small。😊。

That's what this is saying。All right。So this is exactly how we're going to define our bid deviations。

So remember in the general case， the question was how to choose B or B star I。

So we're going to could choose B star I to be equal。To this added evaluation， except， you know。

 just to keep things simple， we're going to zero it out outside of the items in S star I。

So in the unit demand case， we said go all out for the item you're supposed to get in the optimal solution。

 zero everywhere else here again， you're going to be zero everywhere outside the optimal solution going all out for S I just means bidding according to this added evaluation。

All right。So we're going to set B star。IJ to be equal to a star Ij for J in the optimal set。

And zero otherwise。Any questions about that。 That was the key new conceptual problem we had to solve to move theem modular evaluations。

 The rest of the proof will be similar， as you'll see。When exercise to go all out for this bundle。

Can't work out and put everyone time what AI should be。 Yeah， so this is good。

 So one thing to keep in mind is everything we're doing right now is sort of just。You know。

 a thought experiment as analysts。 right， So we， we are assuming that bidders can figure out that they're doing a best response。

Which is basically a demand query。That's kind of implicit in the equilibriumm being meaningful here。

it is possible that I think it's an national agreement， but it's not。

Depends how you want to define that。 So it's an excellent question。 So an open issue。

 basically with everything I'm going to talk about in the next couple of weeks is how meaningful are the equilibria that we're discussing。

And it's not， I mean， they're going to exist， but as far as complexity issues largely not understood。

 it's something that multiple different parties are working on as we speak， actually。

So its an excellent question。 it's really， So， you know。

 I warned you I warned you at the very beginning that as soon as we got beyond gross substitutes。

 nothing that we discussed will be fully satisfying。 Okay， And for a while。

 what's been sort of unsatisfying is just the sort of elaborate complexity required and the mechanism construction。

 And what's pretty unsatisfying in this part of the class is sort of the lack of a convincing story about why these equilibrium are likely to be realized。

 doesn't we don't know the negative evidence isn't overwhelming either。

 It's just sort of the jury is still out。 And again， and if nothing else， I mean。

 you look at this of simultaneous second price auction。 I mean， we we should。

 as theorists try to understand how they work。 And so it's not。

 I mean I think it's clearly a good endeavor to just try to understand them better。

 And it's just that our understanding is pretty primitive at the moment。

So that's about all I can say。the downside about， you know。Teaching cutting edge research type stuff。

 the story isn't really complete， but that's definitely the key drawback with this part of the stuff。

Good。Good。Right， but for the proof， literally， we're just saying。

 supposeupp you had a national equilibrium。 I don't know how you got there。 Not my problem。

 Let me just show that it's good。Okay。Good color。Other questions？All right。

 so these are the deviations that are going to work out great。So。

So let's just see how it actually goes。So since B is a pure Nash equilibrium。

Eys utility only goes down if it tries to deviate in this way。So here's this utility pre deviation。

Kind of a mouthful。Now， in the unit， here's， here's what's going to work out so great。

 Here's why this additive representation is so nice。 Basically。

 this analysis almost reduces to the unit demand analysis。

 So this is exactly the same inequality I wrote in the unit demand special case。

 The next step that we did is we examine the right hand side。 And we said， oh， well。

 all that mattered。 We said the bid， the bidder is bidding0 everywhere， except on this one item。

 So all that matters is this one item。😊，T。So now what do we have？We have the same thing。

 It's bidding zero everywhere outside of this special bundle S star I， first of all。

 so everything outside of S star I is going to drop out of the right hand side。Furthermore。Prices。

 by definition， are additive over the items。 So if you win two different items。

 you just pay the sum of their prices。Furthermore， the value。On this bundle S star I。

 we can think of as additive。As if the bidder had separate values AI J star for each of the goods。

 J in S star I。Okay。So that's really why this works so well。 Okay。

 if you tell me just one special bundle up front， then I can sort of think of a s evaluation as being additive on that one bundle。

 okay。😊，Good， so the upshot is this is basically going to decouple across the items in S star I and it'll be just like the unit demand case on each of those items。

Good。So。So we'll just analyze。Each J and S star I separately。Okay。On the right hand side。So。

For J and S star I。Again， two cases。So case one， we win that item。

Meaning the deviation to that item A star Ij is bigger than the biggest equilibrium bid by somebody else。

So this is just max BKJ。And in this case。The contribution to the right hand side is lower bounded by AIJ star。

Minus this max。 let me again just simplify my life by taking a max over all。

That only makes it smaller。Okay， so again， this is the contribution to the right hand side on the items J that I'm bidding on that I also wind up winning。

 this is the winning condition。On the other hand， if this is true。

Then the contribution is zero right because I lose that item J and I pay nothing。So again。

 bounded below。By aster Ij minus max k equal 1 n。B， Kj。Right right。Good。Now， okay， so the claim。

 in any case。The right hand side。Let me just combine these Okay， so again。

 like last time these are not negative， so by throwing them out。

 I only make the left hand side even bigger。 So in any case VI。So in anyways。

 the contribution of I welfare to the equilibrium。Is bounded below。

By the sum over the items and what we wish it was getting and the optimal allocation。

Of sort of additive part of its valuation on that item J minus the highest equilibrium bid。On that。看。

Okay。right。 So what is this， Okay， so。So the right hand side is let's remember by condition one。

This part is exactly equal to bitterized value of S star I。And then I'll just separate that out。

J and S star I。Max k equal1 to n highest equilibrium bid on J。And again， this， so， you know。

 just this is kind of straight from the equilibrium。 This is straight from the optimal solution。

 This is， again， the weird sort of entangled term that we have to deal with So it's referencing an optimal allocation。

 But then it's looking at equilibrium bids on those items。 So again。

 this has aspects of both the optimal allocation and the equilibrium bid vector。 okay。

So summing over eye。So again， the right hand side， sorry， the left hand side。

 we just get the welfare of B， the equilibrium welfare。

This certainly just the optimal welfare once we sum over the bidders。And then some of our on to N。

 some over J equal S star I。Max of these things。And now we have the same maneuvers that we had before。

So by virtue of S star being some allocation， each items allocated at most once。

 rather than breaking things down according to how the optimal solution allocated them。

 let's break them down according to how the equilibrium allocates them。

 this is to sort of put stuff in the wheelhouse of our no overbidding hypothesis。

So this is at most some of our high equal1 to n， some of our。

The items that I wind in the equilibrium。RightSo both so that's just a sum over all of the items allocated in the optimal solution。

 That's just a sum over all of the items， because each item is sold to the highest bidder。

 exactly one person in the equilibrium。And this is the same term in here。And。Rights， so again。

 by virtue of this item being in eyess winning set at equilibrium。

 It must be that the highest equilibrium bleed belongs to I。And now， this。

Is it most the by the nobidding hypothesis？This is at most。Bitter eyes。

Value for the bundle that I got S I would be at equilibrium， swimmingming over the bidders。

 this again， is just the Nash welfare。 So again， rearranging here gives us the factor too。Yeah。Okay。

 so one thing I'll leave is an optional exercise， but it's sort of very clear in the analysis。

 which is that this one half bound degrades gracefully as a function of how much overbidding there is okay so if people overbid。

 you know but maybe by only some gamma factor so then basically this you can't maybe upper bound it by V times this。

 but you can bound it by some constant factor times the value so that's good enough for something close to a half as long as there's close to no overbidding。

So this is a canonical result of the form where you take a simple a and you show that it has good equilibriumria。

 even though you don't actually know what the equilibriumria are。

 just by working with the equilibrium condition and doing some algebra。

 you can prove that you have to have welfare close to the best possible guarantees we can't get with D mechanisms as far as we're going to go next。

 we'll spend probably roughly three more lectures on the price of energyarch and simple auctions。

 so one thing as I want to look at more auction formats。Beyond just simultaneous second price。

 we'll have some more bounds for some other auction formats。More general valuations。

 not just some modular evaluations。 and then finally， more equilibrium。 So pure naash equilibrium。

 frankly， aren't especially well motivated in an auction setting。 N equilibrium。

 That's a full information model。 It assumes you actually know what everybody wants。

 and really incomplete information models is what makes sense in most auction contexts。

 So we really want to be talking about Bayes Nash equilibrium。

 But it turns out this kind of proof is amenable to an extension to Bayes Nash equilibrium in exactly the same way。

 although you， you have to work a little harder， But in the same spirit of the results we had last quarter where bounds for N equilibrium extend to weaker concepts like correlated and course correlated equilibrium。

 So that'll probably one of the main things we talk about next week， How do you get bounds。

 not just for pure equilibrium， but also Bayes Nash equilibrium。 so I'll see then。😊。

