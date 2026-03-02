# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p03 -03-3_ Myersons Lemma).zh_en -BV1VmC2YzEXJ_p3-

All right， let's go ahead and get started。 I'm going to begin by reminding you the story so far。

 Last lecture on Wednesday， we did some mechanism design basics and possibly the crown jewel of that lecture is the introduction of the victory or second price sealed bid auction for selling off a single item We explored at the properties of the victory auction。

 and we concluded that the auction is awesome。What I mean by that is it satisfies three different properties that are kind of totally orthogonal to each other and that you all really want。

So first of all， it has strong incentive guarantees。

 so I introduce the term dominant strategy incentive compatibleatible or DSIC。

That means that for each bidder it has a foolproof strategy and the strategy is just to bid your true private valuation for the good being sold。

 so truthful bidding is a dominant strategy by definition in a DSIC mechanism why would we want such a property first of all the bitter perspective it's an auction which is very easy to play it's clear what you should do if you believe that you should play an obvious dominant strategy it's in contrast to the first price auction which we had an experiment with on Wednesday which I'll give you the results of today。

Secondly， from the designer perspective， assuming nearly the behavior on the part of the bidders is that they play obvious dominant strategies when they exist。

 assuming just that relatively weak behavioral assumption， you can predict the outcome of the option。

 You just expect everybody to bid their true values。 If everybody does that。

 then the highest bidder will win。 the highest valuation bidder will win。

What that means is that the victoryy auction， assuming truthfulbids a reasonable assumption in light of one maximizes the social surplus in the sense that it gives the good to the bidder who values it the highest。

 That's an optimization problem， you might well have wanted to solve a priori a priori you couldn't do that because you didn't know the data valuations。

 which are the data to this optimization problem were known only to the bidders in advance not to you as the seller。

 nonetheless， through this second price payment rule the victory auction solves this problem as well as if the data was known in advance。

 Finally， and this is obvious for the victory auction， it runs in polynomial time。 In fact。

 linear time， there's no obstruction to really running this auction in real life。

So this motivated the question， could we have equally awesome auctions for more complex allocation problems。

 problems that are very important， for example， sponsored search auctions。

 really perhaps the main engine that has generated revenue in the internet economy。

So we concluded Wednesday by wondering whether or not such an awesome auction for sponsored Church could exist。

 We'll answer that question in the affirmative today。

 I also ended with the following proposed methodology for designing auctions。 Remember。

 an auction involves two components。 Even just simple seal bit auctions， You have to pick who wins。

 you have to pick what they pay and those two decisions are coupled。

 But I proposed factoring that two prong design decision， solving them one at a time。 Step 1。

 you assume without justification， that you get truthful bids。 You take the bids that face value。

 you just assume they really are the value。Under that unjustified assumption， you say， well。

 if I was so lucky， could do I at least understand how to achieve problems2 and3。 That is。

 can we give a polynomial time algorithm for maximizing the surplus assuming truthful bids for sponsored search we noticed that there was a natural greedy algorithm。

 you give the the J best slot to the J bidder， Step two。

 the subject of X lecture is given how you decide to solve， given your allocation decisions， So。

 for example， allocating slots and bid order， can you come up with an analog of the second price rule。

 can you come up with payments that give you the DSsicC property。

 thereby justifying your assumption in step1 that the bids really were equal to the valuations。

 so that's where we were what I'm going to give you today is a solution to step two。

 not merely for sponsored search， but actually a very powerful and general tool in mechanism design。

 It's essentially going to explain to us precisely what the space。

Of all dominant strategy incentive compatible mechanisms look like。

 We're going to get a very strong understanding of what these options are。 And as a consequence。

 we will see that there is indeed one。 There is indeed an awesome option for sponsored search。

 and in coming lectures， we'll have further applications as well。All right， so again。Coming up next。

I'm going to give you a general understanding。Of what dominant strategy incentive of compatible options。

Look like。And so we're going to understand our design space。 And as just one special case we'll get。

 we'll figure out how to charge payments in a sponsored search auction。So again。

 I'm going to appstract out now more generally than sponsored search。

So what I'm going to define first is a space of environments。

 So special cases will be things like single item auctions， sponsored search auctions。

 but it will encompass both as well as many other examples。😊。

So these are called single parameter environments。The ingredients of which you've really all seen before。

So an environment has some number of bidders there's still going to be n of them。

And each bidder is going to have a private valuation as usual v subbi。

And the way you think about this valuation v sub I。

 this is how much I values a good in the units of the amount of stuff that it gets。 Think。

 for example， about sponsored search。 remember the valuation was per click。

 So if you gave something in expectation0。25 of a click。

 then its value would be its basic value per click V times 0。25。

 So that's the sense to think of this value per units of a good okay。

The reason it's called single parameter is because while we as a designer， do not know the valuation。

 it's private。 This is the only thing we don't know about the bidder。

 We just don't know this one number。 That's the single parameter。

The other ingredient of environment is what are the feasible allocations that as a seller。

 as a designer， you can choose。不。あと。So I'm going to use capital X。

To denote the set of all feasible allocations。So the elements of this set capital X are n vectors。

 So each element of capital X is the form X1 through X N。

 X I is the amount of stuff that you give to bitter I。 So， for example， in sponsored search。

 if you give it a slot that has an expected 0。25 of a click。

 then that bitters value of x sub I is going to be 0。25。Okay。

 so this is the amount of stuff everybody gets。So to make sure we're on the same page， some examples。

So for a single item auction。What are the vectors in this set capital X， What do they look like。Yeah。

 so the key。 So first of all， it's 0，1， a bidder either gets the good or it doesn't。

 And there's only one copy of the good。 So they better be at most1，0。 Okay， so it's just the 0。

1 n vectors with the most 1，1。If you were selling K identical copies of exactly the same good and you gave it most one per customer。

 the only difference would be it would be sum over the Xises at most K。So response in search。

I'm not going to be too pedantic about this。Hopefully。

 it's already intuitively clear that you can encode the possibilities in a sponsored search auction within this formalism。

So x is just the vectors that arise。If you have K slots of assigning at most K bidders to these K slots。

 In fact， at most one of the bidders to each slot。 And again， as discussed yesterday。

 we also assume that each bidder gets at most to one slot。So let me just for short。

 say ways to allocate。U。Slots。Okay slots。To the bitters。With the understanding of it。

 most one bidder per slot and the most one slot per bitterder。Yeah。And as we discussed。

A component x sub I is going to be equal to a number alphas sub J。Where remember。

 we're using the alpha Js to denote the click through rates of the slots。

 If and only if bitter I is assigned。To the slotchat。你看。

So these are going to be n vectors where the components are either going to be 0。

 or they're going to be one of the alphas。 Okay， Al 1 through alpha K。

So those are single parameter environments。And that's what we're gonna to be working with for the next several lectures。

 I'll give you further interesting examples， later on。We already talked about sealed bit auctions。

 Let me talk about them again， really， just to introduce some terminology for concepts you already know。

We're going to continue for the moment to talk only about seal bid auctions。

 We'll talk about whether that's a restriction of interest or not a little later。So as we discussed。

 there's three bids。 First， you accept bids from the bidders。 They may be truthful。 They may not be。

Based on the bids that you get， you have to pick who wins and you have to pick who pays what's。

 Okay So that decision in step 2， Who wins， That's called an allocation rule。

 That's all it means is you're picking who pay， who wins as a function of the bids that you see。

The third step， who pays what that naturally enough is just called a payment rule。

 But those are two phrases you should know。So the allocation rule takes as input。

 the entire vector of bids， it spits out who gets what， and that should be of course， feasible。

remember x is all of the possibilities，And these are n vectors。 They're real numbers。

Let me just write it this way。 They're part of real end space。 and all of our applications。

 they'll be non negative， additionally。And again， so that's something you should know。Who wins？

And then who pays what？Well， here you just choose， again， the input is the entire vector of bids。

 the output is an n vector of who pays what。And this is just these are real numbers。Okay。Yep。

Maybe should just be in eye。在 the price of。So remember。

 this is not just a single item auction we're talking about right now， right。

 So like in a sponsored search auction， you actually have k different winners， one for each slot。

 and you expect to charge everybody something who wins a slot。 maybe different things。

 but they're all going to pay something。Okay。So to remind you。About our current utility model。

 the quasi linear model。So I utility。On the bid profile B。When I say profile。

 I really just mean a vector。 That's often what these kinds of vectors are called。 Okay。

 so the vector of bids or the profile of bids。Is by definition well。We look at how much stuff I gets。

VI is its value per unit of stuff。 So it's V times the amount of stuff it gets。

And then we subtract out how much it's got to pay。O。

So that's bitterized utility in a given bid profile with respect to a given allocation rule and a given payment rule。

Now， over here。I allowed payments to be arbitrary， they could be negative。

 that could be huge for our you know and sometimes you want to allow negative payments and things like that。

 But for our purposes in this class， there's no harm to just focus on payment rules。

That are non negative and that are not too big in the following sense。So we in lecture。

We'll focus on payment rules。Such that。The payment that I pays。Is at least zero？

That is we're not going to be thinking about situations in class where the seller actually pays off the buyers。

Okay。It a seller。Won't pay the bidders。And the most were're ever going to charge somebody。

Is what they said was their value per unit of good。 Remember， we don't really know for sure。

 anybody's value per good V。 That's private。 All we know is the proxy that they told us。

 They told us they big V。 If we take that at face value， this is their value per unit of good。

And then we can also look at how much stuff we gave them。对。

Does anyone see why it makes sense to cap the payment。

 given that we're trying to design D SI C auctions while we might never want to charge more than this。

Suppose we did charge more than this。And this was a truthful bidder。 B， I really equaled V I。

What would be its consequent utility？It be negative。 Okay。

 so this is sort of the upper bound that we can charge。

So that truth forbidders will never experience negative utility， like in the vi a。

So this upper bound is to ensure。Non negative utility。Of truthfulbiders。Okay。

So that's the basic setup。 Okay， so I've introduced single parameter environments。

 This encompasses the examples we've seen so far。 I'll give you further applications that fall into this domain。

 And the reason I've defined at this level of abstraction is the following mechanism design tools I'm going to give you will apply in every single single parameter environment。

 So this is the right level of abstraction for the tools you're about to learn。

We revisited seal bid auctions。 You already knew what they were。

 but especially this allocation rule word， is I'm going to use this 40 times in the rest of this lecture。

 So it's important you know what it is。So any questions about the general setup。好 right。So。

 now we come to。The first really important part of this lecture。Which are two crucial definitions。

Both definitions single out allocation rules that have particular properties。

So we call an allocation rule that is a way of choosing who wins。On every bid profile。

We call it implementable。If。There exists。A way of charging payments。

There exists a payment rule P so that when we couple this allocation rule X that we were given with this payment rule P that we constructed。

 we get a DS SIC auction。That is， the implementable allocation rules are， by definition。

 exactly the allocation rules that can be extended to dominant strategy。

 incentive compatible auctions。 Or if you prefer， if you think about the set of all DS SIC auctions in the world and you project them all down just onto the decision of who wins what。

 you get this set of implementable allocation rules。 In any case。

 these are the only possible candidates， this is really our design space。

 If we want to design awesome auctions。 Remember， property one of an awesome auction。

 is it should be DS S IC。 So these are the only things we can use。

Even if we only look at condition one。Right。So let's， for example。

 suppose we're just selling off one item， okay。So it's look good an allocation rule。 Okay， remember。

 that just picks who wins。 It doesn't say what they pay。 So what about the allocation rule。

 where I always give the good to the highest bidder。Is that implementable or not？Why？

The reason it's implementable is because there is a payment rule。 We've already talked about it。

 It's the second price rule。 And if you couple that allocation rule with a second price payment rule。

 you get the Vicky auction， which is DSSIC。To prove it's implementable just by exhibiting the suitable payments。

What about steal in a single at auction。What about the allocation rule where I give the good to the second highest bidder。

Is that implementable or it not？Not clear， right？We certainly haven't seen a payment rule that renders it D S I C。

 but to prove that it's not implementable， we'd have to argue that there is no conceivable payment rule that could work。

Which seems like a tall odor as well， so not clear。All right。Second。Crucial definition。Oh。

 and I should also say just to tie this in with where we were last time。

 So the sort of cliffhanger question at the end of last lecture was in the context of sponsored search。

 we had proposed an allocation rule， the one that awards the J slot to the J Hythe bidder and really now in this vocabulary。

 the question was， is that an implementable allocation rule or not。

 that's what we want to understand from the end of Wednesday。So here's the second。

 really important definition。An allocation rule is monotone。If。For every bitter eye。

And for every fixed set of bids by the rest of the bidders。 Remember， B minus I is an n-1 vector。

It's the bids of everybody except for that of I itself。If every bidder in bids by everyone else。

The amount of stuff that I gets。Holding everyone else fixed。Can only go up as it bids higher。Okay。

 so it's non decreasing。And it's bid Z。That is， with a monotone allocation rule。The higher the bid。

 the more stuff you get。You can also fit in right。Yes， non decreasing in a bit。Yep。

 can stay the same。Just can't go down。So a single item auction。

Let's think about the first same two rules。 So how about the allocation rule with the highest bidder wins。

It's monotone or not。It's monotone， right， in a single item option。

 you either get nothing or you get the item。If you keep everyone else fixed and you increase your bid。

Well， as long as you're less than the highest of the bidder， you get nothing。

 And as soon as you're bigger than all the other bids， you get one。 Okay， and in particular。

 if you're the highest bid and I raise your bid even more， you're still the highest bid。

 so you'll still win。So that's a monotone rule。How about the allocation rule where I give it to the second highest bidder？

Is that monotone， is that not monotone？Why is it not monetary？Right。

 so if you're currently the winner， that means you're the second highest bid。

 But then if I jack up your bid so you're the highest， all of a sudden you're the loser。

 so it's a violation of monoity。Okay。So， you know， as far as working with auction design。

 this monoity property is much more operational than talking about implementability。 Okay。

 often not always， but often for given allocation rule。

 it's either obvious or easy to check whether or not it's monotone。

 So this is a relatively verifiable condition。Here's another example。So remember。

 in sponsored search， we already went through the exercise of， well。

 if we assume without justification， truthful bids， how should we， what allocation should we choose。

 and we argued that you should give the J highest bidder to the J best slot for each J。

So what about that allocation rule， is that monotone or is that not monotone？That's monotone。 right。

 So remember， the clickthrough rates of the slots are soon to be going up as you get higher and higher slots。

So if I keep everyone else fixed and increase your bid。

 the only thing you will do is ascend through the hierarchy。

 you will only have a higher and higher ranked bid， you'll only get a higher and higher slot。

 which by assumption only gives you a higher and higher CTR， click through rate okay。So， example。

Sponsored search。Allocation rule from last time。Now of course。

 the reason we focused on this rule was not because we didn't know yet that we cared about monotononicity。

 we just wanted to maximize surplus， and we're now seeing our happy fortune that indeed that turns out to be monotone。

不。Any questions about these two important definitions。An allocation rule being。Implementable。

The allocation rule being monoon。Yeah。Should you speak up Do you examples of things that are。この。

So that'll be clarified in the next theorem。Yeah， it's a good question。TheQuest was。

Is it possible to be implementable without being monotone？Other questions。All right。

 so let me introduce you to the first。Major tool in your mechanism design toolbox。

So I'm going to call this Myerson's lemo。Because I'll be using a form。

That appears in a paper by Roger Morrison in 1981。I'm going to state it in three parts。

The first part says that the two definitions I just gave you。Coinciide。

They describe exactly the same set of allocation rules。Yeah。Okay。

So usually what we really care about。As we care about whether an allocation rule is implementable。

 we're in a situation like at the end of last lecture where we know how we want to make the assignment。

 but we don't know how to make the payments， we don't even know if it's possible to make suitable payments to get the desired incentive properties。

So part1 says checking， whether or not something is implementable。

 reduces to checking whether or not it's monotone， which is an intuitively much more operational condition。

Further。In the case where you do have an allocation rule， which is monotone and Irgo。

 it is implementable。 The question then is， all right。

 we know these payments exist to extend this rule to a incentive compatible mechanism。

 What do they look like， What's our design space now for the payments。

So part 2 says that in this situation， actually， the design space is trivial。

There is a unique choice of how to assign payments so that you get the DSSIC property。

I'm lying a little bit。I'm going to assume a very natural normalization for part  two。

 I'm going to assume that if you bid zero， then your payment is0。Certainly under our。

Current assumption that payments lie between 0 and your bid times your allocation。

 A bit of 0 forces it to be 0。 Okay， so I'm going to state that assumption in this lemon as well。

So modo， that normalization， unique payments for monotone rules， there's only one way to do it。

And this is not merely existential。In fact。These payments are given by an explicit formula。

Which I will show you in the course of proving myson's lima。So I'm not going to state it here。

 it'll arise naturally。Okay。So each of these parts is interesting in its own right。Okay。

 so part1 is completely fundamental。 It tells us exactly what our design space is for D S I C mechanisms。

 It is precisely the set of monotone allocation rules。

 You're going assign goods in the way that you want And it's monotone。 you're done。 If you can't。

 you got to pick a different allocation rule。 can't be extended to be in compatible。

Part 2 is really interesting。 In particular， I'll leave this as an exercise。

 but you might have been wondering， does anything other than the victory a work。What' mean by work。

 I mean， well， suppose you always want to give the good to the highest bidder and you want it to you want truthful bidding to be strategy proof to be a dominant strategy。

 Is there any way to do it other than the second price rule， Like what about the third price rule。

 study that in your exercise set。 Well， the consequence of this is that actually the victory a is unique。

 That is the only way to award the good to the highest bidder and have no strategic behavior on the part of the participants。

' The only way to do it。 So that's also very interesting。As we'll see。

 it'll be great to have an explicit formula that'll tell us exactly how to charge payments in sponsored search auctions。

 We'll also use that formula when we talk about revenue maximizing optionsuction next week。😊，Finally。

 let me just note that。Again， I haven't proved thislemma for you。

 so you shouldn't necessarily believe that it's true， but。If you take for now。

 you believe me that this lemma is true， it actually implies the answer to the Cliffhaner from last week。

Okay。So corollary。There is an awesome。Auction。Reponed search。So why is that true？Have a。啊。Right。

' prepared。Excellent， so。Being awesome， I defined as having three properties。 So， first of all。

 you should be dominant strategies instead of compatible。

 but you should also maximize surplus and be polynomial time。 So at the end of last lecture。

 we handled two and3。 Okay， if you just do the greedy algorithm and bids happen to be truthful。

 you get 2 and 3。😊，Now， we observed three minutes ago that happily。

 this surplus maximization rule is actually monotone。😊，Therefore。

 Myerserson's dilemma applies to it and guarantees us that there are payments， in fact。

 a unique choice of payments， so that we can extend it to a dominant strategy and compatibleat mechanism。

Okay。So it's just using a greedy allocation rule， combined with this lemon to generate suitable payments。

 And that gives us our sponsored search a that satisfies one through 3。Okay。Yep。

If you have problems gallery。application properties。げずてもら。Good， so then。

 so then so the question was about randomized auctions， which I'm not。

 I'm not gonna talk a lot about now because I want to develop intuition for deterministic auctions。

 But looking ahead a little bit， you could equally well define these little X of I as the expected amount of good that you get at a given bit profile。

 And then this theorem extends with exactly the same proof。😊，So adding random。

 so this theory will accommodate randomization with essentially no extra work。 That said for today。

 for clarity， you can just think about deterministic as like the ones we've discussed so far。

Other questions。Okay。So next step is the proof。Let me sort of take a little break before that。

 A couple things。So。Here are the results of the first price auction experiments。That we ran。

On Wednesday。So it's around the other direction。So on one side。

 we've plotted how you bidted as a function of your value。On the other side。

 there's a list of all of the participants and how much money they won。And again， remember， you know。

 before you start feeling too smug， how much you want is probably a property more of your birthday than the cleverness in how you bid。

So overall， the class， I thought bid very reasonably。

 it was a bit more aggressive than how the equilibrium theory predicts， but that's completely normal。

 It's usual in experiments that the bidding is a little more aggressive than what theory predicts。

 You might ask， okay， what is it that theory predicts。

 What is the equilibrium in this first price auction supposed to be。😊，Well。

 it does depend on the number of bidders， as many of you correctly determined。

 the more competition you have， the closer your bid should get to your value。

 the less you can get away shading your bid， the more competition you have。

 if you're paired up with only one other bidder。 That is。

 if you're in a two bidder first price auction at equilibrium。

 everybody should bid half of their value。Okay， and in class， it was more than that。 was the。

 what was the least fit。Okay，75%， probably more like something like that。 Yeah。

 so it should have been 50% of your value at equilibrium， but。

 but the experiments had more something like 75% of your value。

 And then if you're in a threebitter auction with uniform valuations like we had。

 the equilibrium suggests you should bid two thirdds of your value in the threebitter case。

So everyone cooperated brilliantly by there being 42 participants。

 which divides equally by two and by three， despite the fact it 51 enrolled students So thank you for that。

 Thank you also， thank you also for overbidding， because then it means I have to pay you less。

 right so that was great。 I'd like to particularly thank the student who won both auctions in which they participated。

 but did show by bidding their value。 That was fantastic，😊。

I it's really really a model student from the instructor's perspectives。

So for those of you who have nonze winnings， you can pick up an envelope with your pocket change from one of the Ts afterwards。

 don't spend it all in one place， okay。The other announcement is。

 I don't think I brought quite enough of the release forms last time。 So this is just saying。

 you know you understand that this class is being videotaped with the videos posted on the web。

 So if you can just pass these around， if you sign one last time I have it so you don't need to do it again if you didn't sign one last time please sign it today and give it to one of the Ts after class。

走了吗。If you need am Florida L。W up in the I。Okay。Single parameterer environment。

That's exactly why I define single parameter environments exactly because those are the settings in which you can prove this theorem。

必し。A single good optionuction where we did。Exactly。So， remember， so in a single predator environment。

 there's a notion of the feasible allocations。 And so that is where the details of your environment。

 like how many goods there are shows up。If you only have one good。

 then you only have n plus one feasible allocations。 If you have K copies of a good。

 then you have many more feasible allocations。So it's part of the description of the environment。

 what's feasible， and of course your allocation rule is responsible for picking something feasible for every bid vector。

Yeah， could you explain why it is not going be？That's on problems at one， actually。 Yeah。

 so problems at one ask you to verify that。 It's good。 It's not obvious。 So it takes some cal。For。

 everybody else does that and you're born on January。So I asked you to prove it on the problem set。

 So I promise it's true。 So we can talk。 we can talk afterwards about it， too。But it does， again。

 It takes a computation。 It's not。 It's not obvious。说对了。It it's called a Bayes Nash equilibrium。

 Yeah， so again， the details are all spelled out in the homework。So let's get started in the proof。

We begin with an allocation rule。X。At the moment， X might be monotone。 It might not be monotone。

 I'm currently agnostic。Here's the plan。Let's do a thought experiment。

Suppose there did exist some payment rule P so that coupling it with X gave you an incentive compatible mechanism。

Let's try to think about what P would necessarily have to look like for this fact to be true。あ。So。

 the plan is。什么。Thanks。The plan is to invoke this D S I C constraint。

 which I've said on multiple occasions， is very strong。Okay。

 so to invoke this constraint and use it to whittle down the space of candidates for this payment role P until one sole candidate remains okay。

So how are we going to do that。Well。Let's fix a bitter eye。And bids by the others B minus I。

 Remember， dominant strategy means， no matter what the other bidders。

 no matter what better you look at， no matter what the other bidders are doing。

 it has to be a dominant strategy for this point for this person to report truthfully。

 So fix who we're talking about， fix what the other people are doing arbitrarily。

 I don't want to carry all this notation around。So let me just a shorthand。Right， X of Z and P of Z。

For what I gets given what everyone else is doing。 Okay。

 so the amount of stuff that I gets when it bids Z。

With everyone else doing B minus I and what it has to pay when it bids Z。With everyone else bidding。

 according to B minus I。看。Now， it might help you to have a graphical representation of what one of these x's look like。

 what this allocation rule looks like。Yeah。So。The X axis is here。 So remember， B minus I is fixed。

 So we're looking at as a function of I' bid Z， how much stuff does it get。嗯。

So in a V auction in a single item auction。 So again。

 I'm just sort of looking at special cases to develop your intuition here。

If we were working in a single atuction environment and we were looking at the highest bitter winds rule。

Well， for low bids， you lose。 And then as soon as you're the highest bid of them all， you win。

So this allocation rule is going to look like this。Your x value is0 for a while。

And then at some point， it jumps to one。Okay。So this is what your X function。

 your X curve looks like in the highest bitter wins single item rule option。

Now with sponsored search， it's a little more complicated， but it's the same flavor。

The only difference is， and so again， I'm thinking of the allocation rule where the J highest bidder gets the J best slot。

So now the difference is it doesn't just jump in one shot from 0 to 1。 Okay。

 So if you're even worse than the k highest bidder in the sponsor search auction。

 you don't get any slot at all。 So you get no stuff。 your X value 0。

As soon as you become the k highest bidder， you get alpha sub K stuff。

 Once you're the K -1 highest bidder， you get alpha sub K -1 bigger amount of stuff and so forth。

So there's not going to be just one jump for sponsored search。

 There's a jump each time you ascend the ranking in the slots，So this is going to look like。That。

 and then like that。 So this is when you're in the cave slot。This is where' in slot K -1。

 And maybe there's only three slots， and it looks like this。So this would be sponsored search。Okay。

 so when I say consider an allocation rule X。 here are two of the curves that we might be talking about。

 These happen to be monotone curves。Now， I said the plan is to invoke this very stringent。

Dominance strategy condition。To whittle down what the payment rule P could possibly look like。

So let me show you how we do that。 It's actually， one it being very slick。

 It's based on a simple but clever swapping trick。Again， remember where we are。 We were given X。

 and we as a thought experiment thinking， hypothesizing about a rule P so that X P is dominant strategy incentive of compatible。

So assume for the moment that that's true。看。To suppose such a P exists。

And here's what we're going to do。And this is sneaking。We take two values， Z and y。

These are just two numbers， five and six。And we say， well， you know， for all the auction knows。

 Z is the person's actual private valuation， and it's scheming and thinking about bidding why it's instead。

Or symmetrically， maybe why is its true valuation and in scheming about bidding excellence debt。

 It has to handle both of those cases。So let's just write down the DS SI C constraints for those two cases。

 See what we get。 Turn out to be quite powerful。So case1。Is when the true value is z。

And the false bid is why？看。So dominant strategy and C mobility says pize utility when it bids Z。

 better B， at least as high as when it bids Y。Okay， that's by definition of the incentive constraint。

So what is its utility when it bids Z。Well， we just look as usual。

We look at how much stuff it gets when it bids Z。 That's x of Z。

We look at its value per unit of stuff。Right， by assumption， it's true value is Z。

 so we can Z per unit of stuff。And then it pays whatever it pays when it bids Z。是。

So this is I's utility when it bids by definition。And。By DS， S I， C。

 this better be at least as large as its utility when it bids y。

So what changes if it bids Y instead of Z， how does this expression change。Let me give you a hint。

 There are three Z's on the left hand side。Two of them changed to wise， not all of them。没有。

Could you speak up？WellSometimes that's boy by skill。Yes， exactly。

 So the two Z's that change to Y are the one inside the argument。 Okay。

 so bid I cannot control what its actual value is per unit of good。 That's immutable。 That was。

 in effect given at birth。 It can change what it bids。

 and its bid gets fed into the allocation rule in the payment rule。So the utility， if it bids。

Why is the amount of stuff it bids when it bids y， that it gets times its's value per unit of good。

 which is still Z。 Can't change that。Minus。How much it has to pay when it bids why。

Everyone clear on that。关就。Why is what？That's by definition。 I set it up that way。 I'm saying。

 consider。そそでね。It says that the utility of truth telling。

 bidding Z is at least the utility of bidding Y。Which again。Just is， by definition。

 true under the hypothesis that X P is dominant Str and compatible。

This says for every bidder for no matter what its value is， no matter what it is， blah， blah blah。

 blah， in one particular case， when it happens to have value Z and ponders the false bid Y。

 certainly in that case， it's better be true。 has to be true in all cases。

 So I'm just instantiating DS SIC in a judiciously chosen case。So here's the swap。On the other hand。

Think about the situation， totally possible， or I's actual value is y。

And it contemplates under bidding， submitting the false bid Z。So， again。

Because it's dominant strategy incentive compatible， utility of bidding truthfully。

Meaning of bidding its actual value， Y。Better be， at least as large as its utility。

 If it instead bids falsely the bid。Z。Same reasoning。So what？Well， here's what I're going to do。

 Okay， here's what's neat about this。I can read off from these two inequalities。

Upper and lower bounds on the different， the difference between the payment at Y and the payment at Z。

Okay so I'm going to do a sandwiching argument。In the middle of the sandwich。So remember。

 Y is some bid。 Z is some smaller bid。So I'm looking at how much bigger the payment is going to be at the bid Y than at the smaller bid Z。

And I'm going to derive a lower bound from one of these and an upper bound on this from the other。

 So that's going be the sandwich。So from conditionition1。If I bring P Y over here。

And then Z X of Z over here。I get a lower bound on P of y minus P of z， which is z。

Times the amount of stuff you get at Y minus the amount of stuff you get Z。Okay。

 that's just rearranging one。Rearranging2。So here， bringing P of Y to this side。

 I get an upper bound on the payment difference。Which is why。Times the allocation difference。

So I get a sandwich on this payment difference in terms of two other quantities。

I claim this sandwich is useful。So much so。I'm going to designate it star。哎。Say it again。I mean。

 maybe the semantics are different， but the number as numbers， they're the same。

RightSo think of z is5 and y is 6 equation。I'll through based on the assumption that one of them is。

Now， so the auction is DSIC。So that means。For a given bidder。Whatever its actual value is。

 whether it' 5 or whether it's 6。Whatever it's thinking about bidding。

 whether it's5 or whether it's 6。Its truthful utility has to be at least its false bidding utility。

So I've instantiated that condition twice。For one hypothetical bidder。

 whose true value is 5 and is contemplating bidding 6。 a second time for a hypothetical bidder。

 whose true value is 6 and is not contemplating bidding 5。

From those two instantis of this DS SI C condition， I get those two inequalities。

 They have to be true。 If X P is DS SI C。 and by manipulation， I get the sandwich。对。

As was having a similar problem making， but， I worked as the equation that you've written up there actually。

As。Times back。And so since pull for the equation is incorporated。没吃饭。No， they they're not。 I mean。

 I mean， I guess the reason these are both true at the same time is because the auction has to guard simultaneously against a bidder that has a value 5 because that what might well be the truth。

 That might well be reality。 and it has to guard against a bitter whose true value is 6。

 That might well be reality。 The auction doesn't know。

 So the auction has to handle protect against every single possible reality simultaneously。

 The value is unknown。So it really has to guard against both of these two things at the same time。

 Of course， if the designer knew up front that this case was impossible。

 it would be a much easier a design problem。 The whole point is， this might well be true。

This scenario， this might well be true。Alright， so why is star useful。

It actually immediately implies one part of one promise from myerson's limit。

 And I'm going to leave it as you as an exercise on exercise set 2。

To make sure that this proof is making sense。So， the exercise is that。From star。

You can read off the fact that if I give you a nonmonittone rule。

 like the second highest bidder wins rule， there is no way It is DS S I C。

 There is no way that there is a payment rule that extends that nonmontone allocation rule to a DS SIC mechanism。

 It cannot exist。 That actually follows immediately from star。Okay。So if。X is not monotone。对。X。

Is not implementable。对。So that is one direction of part 1。 Part1 says implementable。

 if and only if monotone。So we've shown that not monotone is not implementable。

 So what I need to show you is that if you are monotone， then you are implementable。

So we're going to assume that for the rest of the proof。So rest of proof。Assume X is monotone。嗯。

For simplicity， this is just to sort of reduce the amount of technical stuff you have to keep track of。

In real time during this lecture， let's think just about piece wise， constant piecewise。

 constant allocation rules like these two on the board， like the ones we've seen so far。Okay。

 so for simplicity。We're going to assume X' is monotone。 We know that's now necessary。

Just for convenience。Assm X is piece wise， constant。That is， it starts out at some number。

 Then there's a jump。 Then it stays at that number。 There's another jump。

 stays at that number and so on。 Okay， so we're looking at allocation rules like these two。Okay。So。

 that's one。Immediate use of the payment， of the payment different sandwich。

Let me actually use it again to prove the rest of the parts of Marathon dilemma。

So maybe I should write it again。So we had in the middle。P of y minus P of Z in the bottom。

 We have Z X， sorry， Z。Okay。Here's the payment sandwich。So。Now what I want to do。

Is I want to think about Y and Z， which so far have been arbitrary。 Y has been bigger than Z。

 That's all I assume。 I want to now think about Y And Z is getting very， very。

 very close to each other。 Never the same。But I want to think about fixing Z and letting Y approach Z from the right and getting super close。

So in star。Fix Z。And take the limit。Y down to Z。To derive。Well， let's see what's going on， okay。

There's really two cases。 So remember， for simplicity， we're working with piecewise constant。

Alloccation curves， that's just to help you understand the argument。

So case 1 is where Z is not at a break point。Okay， Z is like there， or it's like there。

So what's happening。To the difference between x and y and x of z， as I take y super close to z。

Thats 0， right， X is going to be constant。 It's going to have the same value for y and Z once y gets sufficiently close to Z。

 right。So the only action。 O， so when that happens， the left hand side will read 0。

The right hand side will also read  zero。So the payment sandwich says that there can't be a jump of the payment at Z either。

 Okay， It's got to be exactly 0。 that difference。What about when Z is exactly one of these break points。

And I let Y tend to Z。In the limit， what is going to be this， this value。Just gonna be the height。

It's going to be the extent of that jump at Z。Now， as you take Y to Z。

These two numbers are also becoming arbitrary， close to each other。So we have that the difference。

 the jump， if you will， of the payment at Z has to be exactly because it's sandwiched on both sides by the same number。

 exactly Z times the jump in X at Z okay。So jump in key。At Z has to be。Z times the jump in x。At Z。

So this is now what I meant by saying that the dominant strategy condition is super strong。

 and it's going to whittle down what the payment rule has to look like to just one candidate。

 So we've now learned is that if I give you X。O， and you're trying to solve for P。Okay。

 to make it DS S I C at every single point， Z。 remember Z's arbitrary here， at every single point， Z。

X， the given allocation will dictate with no uncertainty what has to happen。

 Either P stays exactly the same。 It's also constant where X is constant or where there's a jump in X。

 There's also a jump in P。 And it's whatever that jump in X is multiplied by the point at which that that jump happens。

 Z。So this dictates how P the payment is changing at every single point。All right。And from that。

 if you know the initial condition that the payment of a 0 bit is 0。

 it uniquely determines what the payment has to be。 no matter what Is bid is。

 It's just the sum of these jumps that you experience。So。If p of 0 equals 0。

 which I was which I am assuming。In the version I'm proving。

Then we have the following payment formula。The payment of bitter eye has to equal。Well。

 so what is it， So we look at the jumps in X。And they get multiplied by the position of the junks。

Where what I mean by these Yjs。Are just， right， So if。

 if you think about the bid as being somewhere like in this last part here。

 I'm just summing over the 1，2，3 jumps that occur to the left of I bit。 That's all I'm doing here。

So we're y1 through YL。Yeah。Are the break points。Of x。In the range。Zero。To be。Sorry。

 shouldn't be an either。Okay。So what have we done， We've said we were given an allocation rule X。

 We were trying to solve for a payment rule P subject to the constraint of dominant strategy and center compatibility。

By invoking this constraint， instantating it cleverly。

 we have deduced that the only possible payment rule that has any chance of working。Is this one here？

This is the only candidate for a set of payments that would render the allocation of X into a incentive compatible mechanism。

So are we done， have we finished the proof？So see one more thing we have to do。She was missing。Good。

 the proof that it works， it's exactly right。So to do。Verify， okay。

 I said this is the only thing that could work。But I haven't shown you， it does work。 And actually。

 if， if X is not monotone， we know that even this doesn't work。

So we have to verify that if X is monotone， then indeed。

 this payment rule gives us an incentive compatible mechanism。 If we can show that， then indeed。

 we're done。O， I've already argued， or I've already given you an exercise， one direction of one。

And then the rest of this proof is a constructive proof of the reverse direction。

 given a monoone allocation rule。 I've constructed for you a payment rule P。

 We've argued this is the only one that could work。 And then this is indeed the explicit formula。

 Okay， and we'll interpret this explicit formula to give you some more intuition for it once we finish this verification。

So to do， verify。But， he works。When x is monotone。Actually。

 let me give you a little bit more intuition for this payment formula right now， okay。

So let's just think about a single item auction。 Okay。

 let's think about the allocation rule where x just gives it to the highest bidder。Okay。

So then x always has the value 0 or 1。Right， so if you're a bidder， low bids。

 you don't win high bids you do win。 What is the transition point。

AtWhich your allocation switches from zero to one。's。

 it's basically the lowest bid that makes you the highest overall。 O。

 also known as the second highest bid overall。So what I'm saying is in the highest bidder winds rule。

 the location。Of the jump on the X axis， where you switch from 0 to 1， the location of the jump。

Ie what we're calling Z or Yj， we're calling Z here。That's the second highest bid overall。Okay。

What is the magnitude of the jump you jump from losing0 to winning one。So as a special case。

 we recover the second price payment rule from this formula。Okay。

So if you're the winner with this allocation rule， you are the highest bidder。

The jump occurred at the highest other bid， the second highest bid overall。

 And the formula tells you that's exactly what you should pay and that it's the unique way to render that rule incentive compatible。

Okay。2。So， let me。Complete the verification。Let me give you a proof by picture。

 It's not hard to do algebraically， but for the sake of variety。Let me， show off my。

Notoriously poor drawing skills。remember， here's the payment rule here。So given a bid。

 you look to the left。You look at all of the jumps in the allocation rule in the x curve。

Between a bit of 0 and the bid you actually submitted。

You find the locations at which the allocation curve jumped。 That's what I'm calling Y 1 through Y L。

And the payment， you sum over those jumps， and it's the extent of the jump times the location of the jump。

Okay。All right， so。Proed by picture。So let's draw the same picture three times。

Three times because I want to compare what happens when you be truthfully。With this payment rule。

What happens when you overbid and what happens when you underbid。嗯。

So we're always talking about the same allocation rule。

 So maybe it's a sponsored search type of allocation rule。And we're talking about a fixed bidder。

 So its value is the same in all of the cases。So there's its value。

So now let's see what happens in the three cases， bidding truthfully， under bidding and over bidding。

So what's its utility when it bids truthfully， when it submits a bid equal to its value。Don't forget。

What the utility formula is。It be。Times x of B minus P of B。 So here V is its true private value。

 B is the bit it submits to the option， which may or may not be the same as V。But for starters。

 let's assume it is the same。Okay。So how much stuff does it get， first of all， okay。

The amount of stuff it gets， which corresponds to the height。So x of B， remember， that by definition。

 this curve is just how much stuff you get as a function of your bid。

So that's how much stuff it gets when it bids truthfully。看。What's its value for that stuff， Well。

 that's given by the width。So we multiply it by its value per unit of stuff。

So it's that height times this width。So that gives us this rectangle。看。How much does it pay。

And this is where I think your intuition will become a little sharper。

So how do you compute the payment， Well， you go， you look to the left and you say。

 what were all of the break points。And the total payments， while you sum over those break points。

 you look at the height of the break point and you look at the location where it happened。

So there are two break points， two jumps to the left of V。Here's the first jump。

That's the magnitude of the jump。 That's how much it went up。 And this is the location of the jump。

Okay， so I'm looking at。The location of the jump。Which is so this is y1。And this is why too。Okay。

So the locations of the jump times the magnitude of the jump。

So the first term of the payment is this rectangle。你看。Amount of the jump times the location。

The second term of the payment is the amount of the jump。Times the location。看。

So it's the area above that curve。 So to be clear。嗯。This is the seller revenue。And what remains。

 this stuff。This is I's utility。O。So I computed the pink rectangle and then subtracted the area above the curve。

 leaving the area below the curve。So what happens if。I overbis。

Remember we're trying to argue with utility can only go down with the payment rule that we've chosen。

So it overbids。Well， how much stuff does it get。Well， now it gets more stuff。 right， to remember。

 the allocation rule tells you how much stuff you get。So the amount is all the way up to here。Okay。

But its value for stuff is still V。Okay。So， the width remains。V， right。

 so value per stuff times the stuff you get。So。The rectangle changes to this one。

The width is the same as before the height is bigger because it got more stuff。Okay。The payment。

 So now there's three break points， but the concept is the same。 We have y1， Y 2 and y 3。

 But what you pay is the area above the curve up to the point that you were allocated。Okay。

So the payments。Is all of this stuff。Yeah。嗯。So the utility in this picture。

 So remember the utility here。Was this thing？The utility in the middle picture is the same。

Minus this extra payment it's making up here。Okay， so that's， so here， this stuff cancels。

 This is all signed with a positive for utility。 In this picture， this stuff cancels。

 This is a positive， and this is a negative。😊，Okay， so that's less overall。 Okay。

 so this was the same as before， And that's an extra penalty for over bidding。Last case， underbiden。

Okay。All right， so what's the new rectangle？Well， so again， the bidder can't control the width。

 The width is always its value， and that stays the same in all cases。

 So what it accomplished by under bidding was decreasing the amount of stuff it got。 Okay。

 the new amount of stuff is only down here。So the pink rectangle is now this thing。

And the payment is the area under the curve。Okay。Justs this。

Leaving the bidder with this rectangle utility。Which you'll notice。Using here。

 the fact that the allocation curve is monotone that。That had a bigger。Amount of area here。看。

So this square。Is exactly。This part of this region。Okay。And so the general principle here is that。

For a truth telling bidder。Yeah。So the utility。Is the area under the curve。

And I hope this makes the payment formula a little less mysterious。And the revenue。

Is the area above the curve。And in tandem， these two constitute the surplus。 Okay。

 so there's some surplus to the surplus objective function of this bidder getting this amount of stuff。

 The bidder itself keeps some of that surplus。 Its utility or consumer surplus。 The remainder。

 the revenue goes to the seller。 That's how it gets split。

So it turns out this now hopefully more natural sounding way of charging payments。

 actually by this argument， or if you prefer a simple algebraic argument does show that when the rule is monotone。

 indeed， Myerson's payment formula here gives you a dominant strategy and of compatibility。

So that opposite of the proof。 I'll finish the lecture here at the beginning of Wednesday。

 I'll show you exactly the payment formula that you get for sponsored search。

 It'll be just an immediate application of Myerson's payment formula。 See you then。

