# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p05 -05-5_ Revenue-Maximizing Auctions).zh_en -BV1VmC2YzEXJ_p5-

So today I want to begin our discussion of revenue maximizing auctions。

 So revenue is a topic we really haven't touched on yet in this class。

 ever since we began with the V auction， we've been focused on the objective of social surplus。

Maximization。So that's what we've talked about so far。

 We've designed for a number of different application domains， DS S I C auctions。

 which maximize surplus。So it's not that we haven't seen payments。

 there are payments even there in the victory a， but the point was not really to raise revenue per se。

 we had payments only to encourage people to do the right thing only so that we could get a DSSIC implementation Revenue in some sense was a side effect of the incentive constraints。

 So today we want to talk about when raising revenue as a first order goal。

So let me explain just for a second why。I started out by talking about surplus maximizing auctions。

And one is just it just something you should know。 So it's one of the most fundamental objectives in the theory and practice of auctions。

There are definitely real world scenarios where more or less what you want is to do surplus maximization。

 So one example would be when something like a government auctions off a public good。

 so you see that with these auctions run by the FCC to give to figure out which telecom should own wireless spectrum。

 for example， thinking revenue is a consideration for the government in those auctions。

 but still the first order goal more or less is surplus maximization， not revenue maximization。

 Another thing is in competitive environments， it's thought that you generally are forced to surplus maximization because if you don't maximize the surplus。

 one of your competitors will。So sometimes it really is what you want。But a second reason。

Then I started with surplus maximization as pedagogical。So it turns out surplus is special。

In a technical sense。And that made it easy to start with。

And the reason it's special is because you can maximize surplus in an unusually strong sense。

 In a sense， we will not be able to do with revenue。

 One way that this will be described is we can maximize surplus。Even X post。And essentially。

 what I mean is just， you know， like I said many times in the past。

 we were designing these auctions that had the cool property that they were maximizing the surplus as well as if they had known all of the private information。

 the bitter valuations upfront。 So even if after the fact I told you what everybody's valuations were。

 you'd be like， yeah， whatever， I mean， I did the optimal thing anyways。

 I already figured out the valuations。 Thank you very much。 So surplus can be maximized。

 even in the strong sense， as well as if you knew the private information in advance。😊。

A different way of thinking about this is you get the DSSIC， the incentive constraints for free。

 they impose no surplus loss。So let me now do a very simple example。 It may seem stupid。

 but it's actually very illuminating， and I'll drive home this point that profit maximization is just not as simple to think about as surplus maximization。

So I want to look at a single item option with the additional simplification that there is only one bidder。

 So one item， one Bider。So the bidder has a private valuationknow to the seller。And there's one item。

Now， when there's only one bidder。Turns out the design space， the space of all options you could run。

 is's not that rich。 There aren't there many different things you can do when there's only one bid you're interacting with。

Essentially， all you can do。Is offer that bidder， a take it or leave it offer。

 Those are the DSsIC mechanisms。 These are also called posted prices。

They didn't know that he is the only winner。It's not gonna to matter， right， D S I C options。

 you don't care generally。So you can think about it either way。嗯。

So you walk up to the bidder and you say， look。But basically you show them the item。

 you put a price tag on it， you say， take it at this price or not。So。

And a take to leave it offer with a posted price at a value of R as the seller。

 Your revenue is going to be one of two things。 Okay。

 So what happens if it turns out this unknown valuation V is at least。

The take it or leave it offer that you gave the bidder， What's your revenue going to be。

 How much money will you make？2。And otherwise。Nothing。 they walk away。So that's。

 that's kind of the space of possibilities。For one bidder and one item。

 you can also randomize over posted prices。 That's not going to change the point I'm making here。

Okay。So suppose this was your situation， and you wanted to maximize the surplus。

How would you choose R？You didn't care about how much money you make。

 All you want to do is sort of have the greatest global good possible。Zero， good。Easy problem。

 And if you think about it， that's basically what the victory a would do。 Okay。

 there's no second bidder。 you could think as if there's a second bidder of bid 0， okay。

So the max surplus。Just said R equals zero， okay？And notice。

 the answer did not depend on the private valuation V。 Okay。

 We don't actually care what this private information is。 What we should do is unequivocally defined。

 That's the sense in which we can even ex post， maximize surplus。

What if we wanted to maximize revenue？So let me give you sort of unreasonable easy version of this question first。

 What if we wanted to maximize revenue X post， that is。

 what if we actually knew V by our telepathic powers， We knew V in advance。

 How would we set R to raise revenue。We just set it to V， right。

 We'd set it to be as high as possible， subject to the bidder actually taking it。

 That would make us the most money。What if we don't know V， how should we set R？返。

You get to sit it once。So， in other words。 the revelation principle says that boils down to figuring out the last price you're willing to offer。

So what's that going to be？It's actually not even really clear how to think about that question。

 right， It's not even clear it's a well definedfined， meaningful mathematical question。

 So we have some kind of fundamental work to do to get a theory of revenue maximizing options up and running。

 it's not going to be as simple as surplus maximization。

 But I'm happy to tell you that in very reasonable senses。 it's a well solved problem。

 That that's what we're going to learn starting today。😊，嗯。So upshot。For revenue。Unlike for surplus。

Different auctions do better。On different inputs。So， for example， with one bidder。

 the auction which posts a price of 20。 Well that's going to do really great on inputs where the private value is close to 20。

完了。And at least 20。Yeah。And it's going to do extremely poorly on inputs that are close to 20 but below 20。

 Okay and on those inputs， auction that's opposed to price of 15 will do better。

 So which a is better。 It depends on the input。 and you don't know what the input is。

 That's exactly what's private。Now， you know， as computer scientists。

 this is not a quandary that is foreign to us right when we reason about algorithms。

 we face exactly the same problem。 You know， if I ask you which sorting algorithm is better， A or B。

 Well， sometimes the answer is obvious， Some sorting algorithms are just stupid。

 But if's like insertion sort and quick sort。 It's going to depend。 I mean。

 some inputs quick sort will be better。 some insertion sort will be better。

 same thing with heuristics for N hard problems， Travel salesman problem， what's better。

 Local search energy your programming， it's going to depend depends on your input class。

 So this is not a new problem。 But that doesn't mean it's an easy problem。

So what we need then to even sort of get started。Is a model which tells us how we should reason about trade offs between our performance on different inputs because whatever a we wind up advocating will do well in some inputs worse on the others。

 So how are we going to argue that our input is our auction is better than some other a。Wops。

There are multiple such models that have been well studied。

 but today we're going to discuss the most classical and most well studied one， which in economics。

 they would call a Bayesian model， Bayesian analysis， computer science。

 You generally call it average case analysis。 That is。

 we will posit a distribution over inputs that is a distribution over the private valuations and seek to do as well as possible on expectation with respect to those distributions。

So to be concrete， I'm going to keep working with single parameter。Environments。

The same sort of generality at which Myerserson's lemma applies， as we discussed last week。

 though I encourage you in this lecture to go ahead and think about the special case of single item auctions。

 That's already a very interesting， motivating example。😊，And。What's going to be new is that V I。

 the private valuation of participant I， is drawn from a distribution。F sub I。Can。So just a job。

 you may remember distribution function。 If you plug in some value Z with this spits back is the probability that the realization is at most Z。

 Okay， so the range here is 0，1。I'm going to assume just a couple technical points。

You assume that our distributions have densities。Little left subai。And downed support。

Let's say evaluations lie between 0 and some finite upper bound V max。Also。

The Fs need not be the same。 You can have some bidders that are aggressive， some bitterders。

 which are cheap skates， but they should be independent。For the theory we'll discuss today。

 they cannot be correlated。And they also should be known。To the mechanism designer。

So the whole point is， we're going to optimize with respect to these distributions。 And， of course。

 to do that， we need to know what the distributions are。So known to the mechanism design。

The mechanism designer knows the distribution from which a value is drawn。 It does not， of course。

 know the actual realization， the actual valuation。 that would trivialize the problem。

 Maybe I know your uniform from 0 to1， but I don't know what the draw actually is。It's a question。

Correct。So distribution F sub I is associated with bitter B sub I， and its valuation of V sub I。

Alright， so the mechanism designer needs to know these distributions just to reason about trade offs between different auctions。

 So what about the bidders themselves。 Well， it depends on the model。

 I want to keep things simple today。 So I'm going to continue to discuss only DSs IC auctions。

 only auctions where bidders have dominant strategies。

 Although the theory will talk about today actually generalize very easily beyond those。

 But when auctions dominant strategies， then you the bidders either don't need to know or they really don't care about the distribution from which other valuations are drawn。

 They have a dominant strategy， it doesn't matter what else is going on。 Okay So for today。

 only the seller really needs to know about the distribution。

 or have an estimate of the distribution。 For example。

 know if these are some sort of internet as there's a good chance you have piles of data that you've built up over time。

 that's where you get these distributions， these F subs from from looking at your logs of what people have done in the past。

Okay。So let's now notice that this problem that we were totally unable to think about5 minutes ago。

We can now reason about almost trivially， now that we've posited these distributions。

So back to the one bid case。One item。And this bidder's private valuation is drawn from some known distribution capital F。

So now for a given auction， when we want to know how well it does。

 we can just look at its expected revenue。And again。

 the expectation is with respect to this private valuation， V。So the expected revenue。

Some posted price are。Well， the easiest way to think about it is it' the。

 So we know that if there's a sale。Right。In the event that there's a sale。

 we know we're going to make R dollars。And what does that have to get multiplied by？Well。

 sometimes we're gonna have a sale。 Sometimes we're not， right。

 So this needs to be multiplied by the probability of a sale。Okay。

 and so the probability of a sale is just the probability that the value。

 the private value is at least。The posted price are that we chose。

So capital F tell you the probability of something we at most a given value。

 So what we want here is1 minus capital F。Of art。Again， the reason being is it just by definition。

The second term is the probability。That V is at least R。And this is。Revenue of the sale。

So that's a simple expression。If you told me some distribution capital F。

 I could now just search for the best R。 Okay， and whatever R makes that number as high as possible。

 that would be the optimal a， The revenue maximizing auction with respect to this distribution。

 capital F。So， for example。If V is drawn from a uniform distribution on 01。

A simple calculation shows。That best are。Is one half。Okay。

So what will be the revenue of this posted price， for example， if V is drawn uniformly from 01。My。

So how much money would you make What be your expected revenue with this posted price and this distribution。

One fourth， right， You， you have a sale half the time and you make half a buck every time it happens。

 okay。And some terminology that' will come up later is the notion of a monopoly price。

And that is just the value of R that makes this number as large as possible。

 Okay so that's a monopoly price。So for this distribution， the mopply price is one half。All right。

 so good。 So at least for this sort of very silly example。

Which I used to sort of illustrate that we needed a sort of richer model。 We know it to do。

 But we probably don't care that much about one Bider settings。

 right We'd like to do something a one more interesting。

 And it gets interesting already with two bidders。So I'll leave the computations as an exercise。

 but let me just sort of tell you some results。So now just let's just make it so there's two bidders。

 one item。And both evaluations， these are going be I I D bidders。

 So both evaluations are drawn from uniform 0，1。区月分。Does it matter whether or not the bids？

The bidders are。Speak up No what？Like the other today is drone。

As long as we're considering DS S I C auctions， no， because you have a dominant strategy。So。

 but let's think about it from the designer perspective， right， supposeupp you know。

 there's two bidders。 And your model is that their evaluations are drawn I D from uniforms 0，1。

With two bidders， there's more options you can start think about doing。So， for example。

 the victory auction now makes sense。 So you can just run the victory auction。 Again。

 the point of the victory auction is to maximize surplus， but it inadvertently generates revenue。

 We can see how much we get。So， victorycker。By a simple calculation， which will'll leave to you。

The expected victory revenue turns out to be one third。You sal to the high bidder。

 charge the second highest bid。 You'll make some money。 You'll make a third。

So what else could you do， Well， you could do a few different things。

 But the first thing you might think about doing。Is in the same way that we sort of had this auxiliary price for the one bidder case。

 We could augment the biy auction with a reserve price。 Okay， and in ebay auctions。

 for those of you that are familiar with them， these are just opening bids。 Okay。

 So when there's a reserve price， it just says， look， for me to even consider you。

 Your bid has to be at least as high as the reserve。Okay。Moreover。

 what's the benefit of the reserve price， This can potentially push up the amount of money paid by the winner。

 So it's going to be a trade off。 If we add a reserve and it's going to be a reserve of one half。

 two things happen。 So first of all， there'll be cases in the victory auction where we would have made some money。

 Okay， if the two bids were， you know， one third and one sixth， you'd make a sixth。

If you had a reserve of one2， you would filter both bids。 You wouldn't sell the item。

 You'd make nothing。 So that's an input where you do worse with a reserve of one half。

On the other hand， if you get one bid of two thirds and1 bid of one third in the victoryy auction。

 the winner is charged a third。 But if you had a reserve price of one half。

 you filter the one third bid， and that's now the price charged by the winner。 Okay。

 so just like in ebay， the opening bid， you're never gonna pay lower。

 you're never gonna have you're gonna get away with paying lower than the opening bid。

 when you have a reserve price， the winner will never pay less than the reserve price。

 And if the reserve price happens to split the highest bid from everybody else。 then that's a win。

So if we add a reserve to the victory a， we'll do better。 sometimes we'll do worse sometimes。

 And the distribution tells us how to average to figure out do we do better。 overall。

 turns out in this case， with a reserve of one half。

 we boost this revenue a little bit from one third to 5，12s。

So the pro of having higher prices with one winner outweighs the con of sometimes not allocating the good。

So far， the only point I've made is that there's multiple natural auction you could run already with two bidders in one item。

 and some do better than others on an expectation。But the obvious question is， you know。

 who says this is the end of the line。 right， Can we do better than just a simple virea with a reserve of one half。

 Maybe some other reserve is better。 Maybe some totally different auction format is better than this one。

 Who's to say。So if we want to be ambitious， then the goal。Should be for any situation。

 any single parameter environment， not just single item auctions， any distributions。

 not just I D distributions to characterize what the optimal auction is。

 Figure out the auction that maximizes the expected revenue with respect to the distributions F1 through F N。

And again， for this entire lecture， when I say optimal auction， I mean， maximizes expected revenue。

 expectation with respect to the given distribution over the V Is。So this is what we're going to do。

 Okay， so I' will give you such a characterization in the rest of this lecture。 Okay。

 that's the plan。So， step 0。And just to sort of remind you of an important。

 simple result from last time。So， I mean， our concern should be is like， man。

 It seems like there's a lot of different auctions you could run。

 Its like seems like a crazy big space。 Who are we to think we can actually figure out what's the best point in that space for any environment and any distributions。

So the first thing I want to point out is it's still going be the case that there's lots of auctions out there in the world。

 but at least we can funnel in on just these simple threestep auctions we've been discussing all along。

 these sealed bid or direct revelation auctions。 where you have an allocation rule X and a payment rule P and truth telling is a dominant strategy。

 That's all we need to worry about。 The reason is the revelation principle。

So remember what that says， that says， you give me any。Auction with guaranteed dominant strategies。

 I will give you an equivalent a。 In particular， the revenue will be equivalent so that truth telling is a dominant strategy。

 okay。So that's the first thing to realize。And again， remember， a generic such mechanism。

 you write by the allocation rule， which chooses who wins and its payment rule。

 which chooses what they pay。And because we're only going to be thinking about these mechanisms。

 and this is why I for the rest of this lecture， I will never again write bids on the board。 Okay。

 for the rest of today， I will always assume that the bids are just the valuations as justified by the fact that all auctions under consideration are DS S IC。

OK。So the valuations， of course， are unknown to the mechanism。 But if they're the same as the bids。

 then it still makes sense to write V。All right， and just to be clear。

You know what is the revenue of such a direct revelation mechanism？

Was's just the sum of the payments， Okay， So the payment rule。On a given bid profile， which again。

 I'm just going to write the valuation profile。 I look at the money paid by each of the in bidders。

 and I sum up。 Okay， so this is a number associated with every input， every valuation profile。

 This is what we want to maximize on average。 So again， with。

Expectation with respect to the vector V。Right right。Yeah。啊。Excellent question。 The question was。

 maybe we're losing tons of money by this restriction of DS S IC right So like maybe the first price auction kicks the second price auction to but。

 And you're right from what I tell you today， we will not roll out that possibility。

 I'm giving you in effect， a special case of the general theory for D SIC mechanisms。

 just to sort of slowly build up your intuition and understanding。

 I'm happy to report that the auctions advocated by the lecture today， remain optimal。

 even in the much bigger design space where you drop the DS SIC condition。

 So this is one of those scenarios where DS SIC is actually for free。😊。

But that won't be obvious from what I say today。Good question。Alright， so the main part， the main。

Thing we've got to do today。As I've got to give you a formula for the revenue。Okay， but so you。

 you should be kind of doing a double take。 It like， wait a minute。

 I just gave you a formula for the revenue。 Okay， you're right。

 But so it turns out this formula for revenue is， it's very hard to figure out what auctions make this as large as possible。

 Okay， so I'm going give you a second formula for revenue。 actually， really for expected revenue。

So really， what we care about is not so much this on a single input V。

 but rather we care about the expectation of this on average over V。

 I will give you a second formula。Which is also equal to this one， but which is much more useful。

Okay，It's basically going to be a much more operational formula that we can understand how to maximize。

 We can understand which mechanisms maximize it as opposed to this one okay。So， next。

So let's say important second formula。For expected revenue。Of an option。Okay。

So that's the main thing we have to do today。Right， so first， we'll derive this formula。

 Then we'll turn on to interpreting it and actually optimizing it in various cases of interest。2。

So what do I want to raise， I want to raise this。星期九。So this second formula for the expected revenue。

 is's going to be yet another killer application of Myerson's lemma。In particular， basically。

 we're just going to start from Myerserson's payment formula。

 Remember Myerserson's payment formula is what says that given an allocation rule X。

 there's a unique set of payments P that render it into a DS SIC mechanism。 We applied that。

 for example， to get our sponsored search per click payments。

So we're gonna start from the Meerserson's payment formula and then do some computations。

 and we'll end up with an extremely useful and operational expression for the expected revenue of an auction。

😊，So let me just remind you of the formula。So last week I only stated it for peace wise。

 constant allocation rules。So I stated it this way。So if it's piece wise， constant。

 the allocation rule， we just looked at the various points of a jump。 We looked at it break points。

And it was the sum over the break points of the jump in the allocation rule times the position at which that jump happened。

 So this is the position。 And we look at the jump。X， I。At Y J。And here， the Y Js。 Remember。

 we always look to the left of the bid that we actually got。 So here the Y Js。Are the break points？嗯。

Between 0 and the。Iith bitters a bit。对。So that's just straight off the board from last week。 Today。

 I'm going to write it a little bit differently。 and I'll tell you why， but。

I'm going to write it in a continuous form。So rather than a sum over a break points in this integral。

 I'm going integrate over the integral。Rather than looking at the jump of the allocation curve。

 I'm going to look at its quote， unquote， derivative。So we've got x prime。And I'm integrating。

 and I'm looking again， as usual， when there's an increase in the allocation rule。

 it gets multiplied and gets weighted by the position at which that increase happens， okay。

So a couple comments。Okay。So， you know， I hope it's clear that there are sort of， you know。

 you can syntactically match， you know， components of one of these formulas to the other one。

 In fact， you know， really， these are the same formula as long as you have sort of a suitable interpretation of what a derivative means and what an integral means when you have non differentialable but monotone allocation rules X。

 okay。So depending on how much of your advanced calculus you remember。Either observe or believe me。

That for the piece wise constant allocation rules we had been focusing on as a motivating special case last week。

 these formulas are really the same。Okay， but let me tell you why I did it。Okay。

 so one reason is that in this computation that will give us this very useful formula。

There's a couple of sort of calculus like maneuvers I want to do， like integration by parts。

 and they'll just look much more natural if I'm working with this sort of calculus like formula for for the payment。

 Secondly， is you know， there's really nothing special about piecewise constant payment rules。

 you know， and so last week， you know， when we were young and naive。

 It made sense to focus on that special case。 but with a newfound maturity。

 maybe I want to give you a version that also extends not know beyond peacewise constant rules to arbitrary monotone allocation rules X。

For those of you that sort of do remember your advanced calculus and are worried about， you know。

 some pathologies you can get from arbitrary functions X， let me remind you that in mechanism design。

 the only kinds of allocation rules we ever care about are monotone， and also bounded。

 and basically monotone bounded functions just are kind of almost as good as differentiable functions。

 Okay， the differentable except a set of measures 0。

 So it really gives very little trouble in doing kind of whatever we want with these integrals， okay。

2。So again， Myersson's payment formula were given as input， if you like， an allocation rule X。

 And this is what the payments have got to be， given that we've assumed D S I C mechanisms okay。

Allright， so。Ch。Good。So here's the plan。Can。So I talked about how the payments directly are difficult to work with。

 it It's not clear how to optimize them。 But you know。

 we've now built up all this comfort doing our surplus maximization。

 And there we really got some good practice。 We're like， what allocation will do we want， Well。

 let's look at our expression， right sum of the V sometimes the X's and let's choose Xs so that this number gets really big。

 So we have a lot of practice for designing allocation rules to maximize expressions of the allocation rules。

 Expresss of the X's。😊，So at least in principle， the following strategy looks like a good idea。

 We don't know how to optimize directly a formula that just involves the prices， the Ps。

 but we feel much more comfortable with the X's， with the allocations。This formula tells us that。

 well， if what you care about the P's。Actually， that's sort of a dependent variable on this independent variable of the X。

So this says if you care about revenue， if you care about money。

 you can always rewrite it in terms of the allocation rule X。

And that's what we sort of know how to optimize。 So in principle。

 we can take the very simple payment expression。Which is the。

And rewrite it in terms of the allocation rule。 Okay。

 what's not at all obvious right now is whether that's going to be a fruitful exercise or not。

 And there's really no way to know in advance without actually doing the computation。

 So that's where we're gonna to do next。 But that's where we're going。

 We're starting with this obvious but difficult to work with formula with the P's。

 applying this to get an expression in terms of the X' is。 the allocation rules。

 That will simplify beautifully。 and we'll get an expression that we can optimize directly。 Okay。

 so that's the plan question。So， the derivation。I've broken it into bite size steps for your viewing pleasure。

6 steps。But each is very simple。 And actually， the last three are trivial， okay。

So we're just going to start with the， with the payment format。So fix a bitder I for now。

 fix the bids or the valuations of the other bidders。 V minus I。 Remember， those are random。

 remember， every V I is drawn from a distribution。 So V minus I is from some joint distribution。

 Okay， but for now， just sort of condition on what it is。 fix V minus I。 Okay， I's valuation。

 we haven't fixed。 So I's valuation is random， drawn from F I okay。😊，So by the payment formula。

We have。So let's just think about how much money we're going get from bitter I for a given optionuction。

 Okay， so were take， we're starting from we're given okay， a D S I C mechanism X comma P。 Okay。

 that's the starting point。 Now， we're doing some computations with it。So in this auction。

 we're given。How much money do we get， on average， what bitter eyes valuation is。Well。

 so now we're just going to expand。The payment by bitter eye， in terms of Myersson's payment formula。

 okay。So that is just equal to。Alright， so we just integrate with respect to this distribution， okay。

First of all。So I'm just expanding the expectation。And now we're gonna get。

 we're going to get a double integral because I'm going further expand P I in terms of that formula。

Okay， and so that's sort of our initial expansion step。

 Then we're gonna have two steps that simplify it back down。Excuse me why clear some real estate。

Any questions？No questions。2。So to finish the expansion， step one just says。Holding V minus I fixed。

 integrating with respect to V I。What we get is a double integral。Over there。

So the outer one is the integral， just because V I's valuation is random。

Then we get this integration that we inherit from the payment formula。

So this goes from 0 up to I's instantiated valuation。Z times X prime。All right。So that's step  one。

And again， this is sort of what we knew we could do in principle。 We had a formula with the P's。

 We had a formula that would， and then we had something that would give us something in the Xs。

 right， But so what。 It's not clear if this is useful or not。

So now we're just gonna apply two of those sort of rules and thumb when you're kind of doing computations and seeing if they lead anything interesting。

So pretty much whenever you have a double integral or double sum and you don't know how to interpret it。

 check the reverse direction。Like some of the time it'll make it better。

 that should be a Pavvian response for all of you when you see double sons and deal girls。So。Step 2。

So we're integrating over the joint space of Z's and Vs， right This is choosing VI。

 this is choosing Z。 Z is always at most V， So let's reverse the order。

Let's have our outer variable B Z。And V I has to be at least Z。 This is going to go from Z to V。

Z to V max。And now， in the part we're integrating over V I。

 I'm gonna take the only thing which depends only on V I， which is independent of Z。Great。

So that's a new integral integral。And I have all the stuff that does depend。It's right。

 should busy easy。不宝。It does depend on the outside。Alright， and when you're doing these sort of。

 you know。Pavlavian response， you know， Maagings of formulas。

 You look for signs from above that you're on the right track， right。

And we have a sign here suggesting maybe we're doing something smart。

 which is one of these integrals that we can actually just kind of basically forget about。

 It just becomes something that we have a much simpler expression for。hich is this inner one。

So what is that also known as？Close。1 minus capital of that。

 Remember little that's just the density function for the ifF distribution。

 So we're just looking at the mass that's above Z。 Okay，1 minus F I of Z。Right right。

So that's a good sign。 We had two integrals。 Now we have one。All right。So that's step 2。

 Here's our last nontrivi step。Okay。Alright， so we， we only have one integral。

 so we can't reverse a pair。 But now， so we do have something which is clearly a derivative。

Under the interval。So that's another Plain response would now be integration by parts。

So that's what we're going to do。And with the decomposition， let's just make our life simple。

The part of， which is the derivative， which。Its the G prime， if you like。We'll make the X prime。

 And then whoops F will be the rest of the stuff。So when you integrate by parts。

 what do you get out pops sort of one integral， which is the F prime G part。

 And then you also have to evaluate F G at the two endpoints。So there's going be a second term。

 But let's just look at the part， which is F times G evaluated at the endpoints。

So when integrate by parts。有。So， the first term。Right， so we have the F parts。

 and then we have the G part。V max to 0。And then there's something else that we'll work with in a second。

 let's just look at this。 So what does this thing evaluate to when Z is 0。Obviously。It obviously。

 evaluates to。0ero， right because we have a Z here as part of the product。What about when Z is Vmax？

Also 0， right， So this is gonna be one。 V max is as high as0 will go。 So this is one。 So this is 0。

So， this whole term。Disappears， which again， is a sign from above or on the right track。Alright。

 so what do we get， Now， I get the other rest of the stuff。Zero v max。So now we have our X I， Z。

 V minus I。 Now we need to do a little product reaction on this thing。So what's that going to be。

 That's going to be your1 minus F of z。Plus， whoops minus。C times the density。对。

This this is where we are。So where we start， we started for how much money do we expect to get from bitter eye。

On average， over V sub I， and we got this。Now， the final sort of idea， if you want to call it that。

 So we're integrating something that looks like it should， you know。

 be with respect to I's valuation from 0 to V max。 It feels like this should be an integral over evaluation space。

 So I'm just going take out the density term。 put that in advance。 So I can interpret this。

As an expected value of a random variable。With respect to EI。Okay， so。

 but really all I'm doing is multiplying and dividing by the density。So I can rewrite this。To be 0。

The max。Yeah。distributeistributes minus signs。O。So that's step three。Which at least you。

It's not looking so bad。 We now have a formula that conceivably admits a nice interpretation。

 and it does。 I'm gonna explain you the nice interpretation now。So again。

 all we've done at this point。 this is just sort of the grunge work we had to do。 We had this idea。

 Martin's payment formula should give us a different representation of expected revenue。

 Maybe it's useful。 It's splified as much as possible， boom。So， step 4。

Let's just add some notation to make it look even nicer。Specifically。This thing。We're to note this。

By fe sub I depends on I because we're looking at eye's distribution here。Of。It's just notation。

It has a name， you should know the name。Which is a virtual evaluation。对。

I'll talk a little bit about how to interpret this when we get to the end of the derivation。

 It does have some nice interpretations。 But for now， virtual valuation fe by。

 it's just this thing that pops up in our computation。All right。So。

 but maybe an example would be helpful。Just so you're not too scared of these virtual evaluations。So。

 consider。So， suppose。F I of Z。IZ。On 0，1， I。e。 we're looking at a uniform 0，1 random variable。

So the density is just one。So let's look at what the virtual value is。Well， just by definition。

 it's z-1 minus the distribution function。 That's just the identity function。

 The density is just one。 So this is just。2 z -1。O。So we started with the distribution function， Z。

Uniform distribution。 So Z is between 0 and 1 here。 It's a uniform 0，1 random variable。

 And we get something which is uniformly spread between -1。And one， uniformly。Okay。So， again。

 I haven't told you how to interpret it， but it's not that bad in many cases of interest。

 One thing I just want to point out is gonna be useful later。So， note。

These virtual values can be negative。 It is possible that this second term swamps out the first。

 So again， here if Z is less than a half， this is a negative number。So it can be less than 0。

Let me summarize what we've proven。So how much money do you make。From a bitter eye。

Where you make precisely。The expected value。Of its virtual value。

So what I'm doing now is I'm interpreting Z as valuation。 Okay， Remember， So this is。

 this is an integral with respect to the distribution F sub I。 So it's like Z is a private valuation。

 It's the same same integral。So。Right。So how much money do you make on average from somebody。

 You make the average value of its virtual value times。Its allocation。

So that's where things stand at the end of step 4。Okay， agreed。Yeah。Where where it happened to that。

食晒。Where are we at？Oh here， yeah， I think I just totally omitted it。My bad。 Thank you。

 Thank you very much。Excellent comment。有感觉。Did you like how it kind of went away。

 And then it came back。嗯。This is Z。Dy。Thank you。Other questions or typos。Alright。

 so we've done all the grunge work。 So now let's just actually see why this is useful。

Why has a nice interpretation？So。Alright， so step 5。So now we just， so what do we just prove。

 So we just proved that two things were equal， whatever V I is。That's certainly under nice。

So remember， steps 1 through 4， were all fixing v minus I。 or we fix the values of the other people。

 They're random， but we conditioned on them。 And so we said， whatever V minus I is。

 these two averages are equal。 Okays scenario now we're just going to average more over the V minus I。

 They're still going be equal。So formally， we just apply。We just integrate out。

body over everybody else's。valuations。And so the expected amount of money that we get from bitter eye。

 on average。Over the inputs。It's exactly。The amount of virtual value。That I is contributing。

To the allocation。Okay。And now， finally。I just use linearity of expectations twice。

To say that the expected amount of money we make from everybody is the expected amount of these virtual values we get from everybody。

So the average， the expected revenue of the mechanism。

 So this left hand side is what we've cared about all along。Right。

 so we started with an arbitrary DSSI C mechanism， allocation rule X paymentable P。

The average over all valuation profiles， the average is with respect to these distributions。

 We the average amount of money we make。So we know this is just the sum of the Ps， by definition。

 That's the revenue。So， be linearative expectation。I can take the sum out。

Just look at how much money I make from a single person。For each single person， we。

 this is what we exactly characterize in terms of these virtual values。Okay。

And now I'm just going to push the sum back into the expectation。 So this is the second indication。

All right。 And this is where I wanted to get to。right。

So this is the objective we're trying to maximize the average amount of revenue that the mechanism gets。

 This can evidently be expressed as a sum of the Ps。

 And we just did a whole bunch of work culminating in the fact that we can express it in terms of the allocation variables。

 the X of I， which we knew we could do。 But the reason we should be happy。

 is it's sort of a fairly shocking the simple formula in terms of the Xs。

 which is characterizing the amount of money that we make And again。

 here's what's crazy right So this objective function revenue， What's it about。 It's about payments。

 That's all it's about。😊，Somehow， we just compiled the fact that we cared about payments into a new formula which doesn't reference payments at all。

O， it's only about the virtual values of the allocation to drive this point home。

 squint for a second and suppose that the Fi I wasn't even there。O。

 so just erase the FiI in your mind。What is that expression that's left。So。It's just the surplus。

 right it's a sum over eye of V， I X I。 So if we erase the fe of I。

 it would be the average surplus of a mechanism。 And that's something we already have a good understanding of how to optimize。

So somehow， payments， despite being about the entirely other part of a mechanism， the payment rule。

 not the allocations per se， it boils down to exactly the same thing as maximizing surplus。

 except instead of V I。You have some function of V I， this virtual value。

 which at least in some context， like for a uniform distribution， really isn't that bad。

 You just take Z and you replace it by 2 z -1。Okay。So it is not a obvious。 So I know。

 I know of no way to easily explain why you get such a magically simple formula for payments。

 purely in terms of the allocation rule。 But now that we have it， it's extremely useful。

 And so that's what I'm gonna to spend the rest of the lecture explaining question。

Like what like like step three is in。Sure， I mean， I think。

 I think I wrote on the board as we went along。 But so so step 1 was you expand in terms of myath payment formula。

 Step 2 is a reversal of order of integration。 Step 3 is integration of by parts。 Step 4。

 we introduced the notation for fe of I， Step 5。What step 5。It was something simple。Oh yeah。

 step 5 was just you forget about fixing v minus I and average over v minus I and linearity of expectations to finish。

Okay， good。So。So the rest of the lecture， how to interpret this， How do we optimize it， okay。第二。

What have you seen that？Excuse me。 do you that I didn't。 I talked about this。It's monotone。

It's different at all but I measure  zero。And you can make all this work。 Again。

 I'm not going to turn this into advanced calculus class。

 So I'm not going to give you a fully rigorous proof。But all of this can be made precise。

 All of this can be made rigorous。So every single step is correct with a suitable background of integration and differentiation。

 which I'm not going to do here for obvious reasons。Yeah。Survived。Good question。Good question。 right。

 So this simplifies。 That's right。 So that's what we're gonna to go next。

 So I want to So this computation that we just did doesn't really simplify if you make extra assumptions。

 It's still like exactly the same length。 So this computation， I did at a reasonably general level。

 As far as interpreting what we've done。 It does simplify。

 And so I'll now make extra assumptions so that we get particularly attractive consequences of this theorem。

 And that'll be a prime example。It depends。 So the question is about what if all of the Fis are the same。

And technically， you get simplifications in some applications。 it's well motivated。

 and it some in some innocent kind of depends。 But yes， for sure， in some applications。

 it is well motivated。 And you're absolutely right that it gets simpler。

 or what I'm about to say next will get simpler。Okay。Other questions。I just don't understand five。

Okay， so yeah， I did that too fast， I'm sure。So steps one through four。We fix v minus I。

And we said the expected amount of money you make from bitter eyes the same either way both the formulas are the same。

So if something's true， no matter what V minus I is， or if this equality holds。

 no matter what V minus I is， then it's also true for any averaging over the V minus I that you like。

And that's all we did。 So I just all I wanted。 So syntically。

 all I wanted to do is I wanted to replace a V I in the expectation with the full vector V。😊。

So I just integrated it out with respect to v minus I sub。Very sorry， the virtual value。

WWouldch you survive？呃。So okay， good question。 So this is still。

 so step 5 is still for a fixed bitter eye。OK。So， for every eye。Okay， so steps 1 through 4。

 we fixed both the bidder and the valuations of everyone else V minus I。 Step 5。

 we're only fixing bitter I and nothing else。 And we're averaging over all of V。Yeah。

 thanks for the question。O。So， again， so in English， what do we prove。Yeah。I。e。

 so this is the right way to remember it。Compactly。For any auction。

The expected revenue that the auction produces is just the expected what's called virtual surplus。

For what， for reasons that I hope are now obvious， We agree that if you hide the FiI。

 this is just expected surplus。FI just changes evaluation to a virtual valuation。

 So the expected valuation of this sum is the expected virtual surplus。Therefore。

 maximizing the left hand side boils down to maximizing the right hand side。So let's call this star。

对。Yep seems。は了这。Should there's a function in there。就在这是这个里面。These are both numbers。so。

 for a given mechanism。It has an expected revenue。 That's a number，127。

 And I'm saying the expected virtual surplus is some ai， conceivably different number。

 I'm saying it's not。 It's 127。I'm saying they're the same number for every mechanism， same number。

So the mechanism， which gets the biggest number of the right hand type is the one that gets the biggest number of the left hand type。

 which is what we want。All right。So now let's put this hard work to use。

 So remember the original motivating question， even just for two bidders， one item。IID uniform。

We proposed a couple auctions。 One did better than the other。 But， you know， for all we knew。

 there were other auctions out there that were still better。

 How would we ever know if we had an optimal auction。So， as promised。

Let's now make some extra assumptions just to interpret what we've done。So two assumptions。

Single item auction。And IID。Say all F are the same。And as was suggested。

 if you know nothing else about the bidders， General， you're going to assume their I I D。

 If you know extra information about the bidders， you have ebay bidding histories。

 you might assume they're coming from different distributions。 Okay， But for now。

 let's assume they're from the same distribution。Of course， if， if all the F's are the same。

If you remember the formula for P sub I， that depended only on F I and little F I。

 So if the distributions are the same， then these P I's are also all the same。And remember。

 what we want to do is we want to choose X。 So we're designing the auction。 right。

 It's just like whenre now it's just like when we're doing stripus maximization， right。

We can pick any auction we want。And we have some objective function that we want to make as big as possible。

 And now for the rest of this lecture， we're going to forget about payments per se。

 We're just going to focus on making virtual surplus as large as possible。So we get to choose X。

 How should we choose it to make that as large as possible。Well， so this is some average。Right。

 so the expectation is over the valuation profiles V for each profile V， we get some number。

We want to make the average as high as possible。But if you think about it。

 we actually get to define this allocation rule X separately for every evaluation profile。

 right So for every vector V， we can choose X I U who wins however we want。

So if you want to make the average of all these numbers as big as possible。

The obvious approach is to just optimize point wise to make every single constituent numbers as big as possible。

 That is for every possible input， every valuation profile V make what's inside the expectation as high as possible。

That's the obvious approach to how to choose X to make this number as big as possible。Yeah。

So obvious idea。Maximized star。Point wise。By which I mean。For each input。

And an input's evaluation profile。Right， it's our allocation rule。

 We get to define it however we want。 So let's just define。allocation rule。

To maximize the virtual surplus achieved on this particular input。 Now， in the current example。

 this was independent of I。 But let me just go ahead and write it for now。Okay。So the proposal is。

The expected surplus。As high as possible。For each input， make it as high as possible。

we have to make sure that thanks。Good， you're several steps ahead， but you're absolutely right。

 So we'll get there。O。So let me just make sure。 So what I want to point out。Is that this rule。

Is very easy to understand in the context of a single item a。

Where all the distributions are the same。Okay。So what does that mean。Okay。

 so we're a single item auction。 So the constraint is just that there's one winner at most。

So how do you define X to make this as big as possible。

So I give you V that you know everyone's valuations。There are， you know， then virtual values。

 And again， as the seller， you know the distributions。 So you know the fees。

How should you set X to make this as big not possible。Still serving the light。

The normal world from like。Yes。Exactly， exactly。So I mean， we're talking about basically x is a 0。

1 vector with the most1，1。So what should it be yeah。I't of the eyes。So we what we， so first let's。

 let's again a couple steps ahead。 I think。 So what we really want is the。

 is the bidder with the highest feeat or the highest virtual value。

 I guess let's just start with that。So you want to give this version with the highest virtual value。

 Okay， well， actually， that's even that we， that needs a slight modification。 actually。

 that needs a caveat。 Do we really always want to give it to the bidder with the highest virtual value。

Why wouldn't we， right， So don't forget， virtual values can be negative。So remember。

 we had this 2 z-1 for uniform distribution。 So went between -1 and 1。 Okay。

 So giving it to nobody is better than giving it to somebody if everybody's negative。 know。

 this may seem weird at first， but actually， remember in our one bidter one item case。

 We weren't always giving it to the person。 The only way to make any money was to set a price that was some nontrivial amount。

 which would result in them not always taking the item。

 So we actually shouldn't be shocked that sometimes no one will win。

 given that we want to make maximize revenue。 we already have some intuition for that。对。So， i。e。

So the winner。Is the bidder with the highest。Again， I'll just write FiI of VI。Even though right now。

 all of the Fis are the same function。Or。No one。If all。VI Vs。Are negative。看。Now。

 here's what's obvious。 right， So subject to feasibility。

 subject only having one item for every possible value V， we made this number as big as it can be。

 by definition， okay。Therefore， we certainly made this average over all of these numbers as big as it can be。

 Okay， we made this expectation as big as it can be for each constituent contribution individually。

 So certainly the average is as high as it can ever be。😊，The catch， however， is， you know。

 so is this actually illegal， Does this actually lead to a mechanism， Is this a bona fide mechanism。

And， you know， so what could be the problem。The problem is that there's no way to make a dominant strategy center compatible。

And by Maron's dilemma， we know the necessary and sufficient addition to be DS S I C is for this allocation rule to be monotone。

So the important question is， this allocation rule that we just defined。

 which is certainly optimal if we can implement it。Is it implementable or not？ I it monotone or not。

So， catch。Is this。Rule x。Monior。Yeah。So can you maybe think of a simple condition under which this X would be monotone。

Like a condition on fee。So a fee is non decreasinging， right。

 So what's the allocation will basically， it's basically give it to the person with the highest virtual value。

 Mononicity means that if you win and I bring your value up， then you should still win。

 So as long as bringing your value up only brings your virtual value up， then you'll remain a winner。

Okay， so phoing non decreasing is a sufficient condition for this rule to be monotone。

 And if you think about it for a minute， you'll realize it's also necessary。

So monoity of this rule boils down to fee being non decreasing。So， the answer。If and only if。

So now I'll just write fee because there's for the one distribution。Is monitor。

I've only shown you one example of a fee thus far， which is for the uniform distribution。

 that was 2 v-1。Okay， so that's increasing。 So that's good。 Allright。

 So at least for the uniform case， we know it is monotone。 So this actually， right。Thanks。

 I'll just say that。There are distributions that are， where fee is not monotone。

And then this argument doesn't work。So some distributions lead to non decreasing fees。

 and some don't。There's a standard terminology。For that dichotomy。

So we call it distribution F regular。If it obeys the condition we want， essentially， so if。

The corresponding fee。Which， again， is just this function that depends on capital F and its density little F。

Is nondeive。So exercise I said 3， I'll give you some examples to explore kind of which distributions give you non decreasing。

 which distributions are regular and which ones are irregular。

Most of the ones you'll find in the back of a statistics textbook are regular uniform， exponential。

 Gaussian and so on。There are distributions which are not。

 So like bimodal distributions usually are not。 And if you have super heavy tails。

 that will also usually be an irregular distribution。看。So， in this course。

Because it's an introductory course where I focus on the most important points。

We're only going to ever discuss regular distributions。

 The theory from this lecture can be extended to all distributions。

 including irregular distributions。 But it requires more work。

 But I do want you to know that there is a more general theory out there。O。Right right。

So back to the single item a。So let's consider the regular case。So suppose F is regular。

 even for the moment， assume that fee is strictly increasing， like for uniform distribution。

When bidders are all the same。 so they have the same function mappingping values to virtual values。

When we pick the bidder as the winner with the highest virtual value。

Can you say anything about which bidder we're picking in terms of the values。So by definition。

 we're picking the bidder with the highest virtual value。

Does that happen to also be the highest bidder？If it's regular and if all bidders are drawn from the same distribution。

Yes。So with fees strictly increasing， it means the ordering on virtual values is the same as the ordering on values。

So the highest value is the same as the highest。Virtual value。So the winner， if there is one。

 is going to be the high bidder in this auction， in this optimal auction。

So the only difference between this optimal auction where you pick the bidder with a high virtual value and the viy a。

 where you pick the bidder with a high value is that。In this rule here。

 there will be cases where you pick nobody。 if all of the virtual values are negative。

 So that is the only difference between the revenue maximizing auction for I D regular bidders and the revenue maximizing auction。

 It's just that sometimes not every， no one will win。Okay。In fact。

 I claim that this can be explained just through a single reserve price，So for ID regular bidders。

Same as a vickory。So what would be the reserve price， in terms of the right， So you want， So right。

0 is a good answer。The reserve price is zero in the virtual valuation space。Okay。

 so in terms of virtual values， that's exactly right。 You have to be 0。

So in terms of the actual bids， remember， the victory auction is just， you know。

 it's the high bidder， subject to the reserve。Right。

 so to map back from the virtual values back to the， to the actual bids like in ebay。

 you need to take the inverse virtual value of 0。 so with reserve price。Phi -1 of 0。Okay。

So the allocation we'll describe here。 Just give it to the highest virtual value or nobody。

 if they're all less than0。 If it's I I D in regularular。

 that's exactly the same thing as giving it to the highest value or nobody。

 if everybody's bid is below p -1 of 0。Okay。For the uniform distribution， recall that phi was 2 v -1。

So what value of v makes 2 v -1 equal to 0。One half。So for the uniform distribution。

 the inverse virtual value of 0 is one half。So for I I D bidders。

 no matter how many there are drawn from a uniform distribution I D， the optimal auction， O。

 among all the auctions that exist in the world， The optimal auction is simply ebay。A viory auction。

With the suitably chosen reserve price or opening bid， in that case， one half。So two bidders。

 one item in particular， the reserve of one half， which got us 5，12s。 You can't do better。 Okay。

 No other reserve is better。 No other auction format is better。 That's always the best you can do。

Okay。So， alright， so we have this very general formula characterizing revenue of auctions。

 It tells us how to derive optimal auctions， which in simple settings， actually are， you know。

Auctions that are actually in use in practice。 It's kind of amazing。

 We optimize over this huge set of optionsuctions。 The best one is really just ebay。😊。

If they're I I D， okay， so the exercises will ask you to do exactly this same thing when the bidders come from different distributions。

 And you'll find that the optimalimum options can be a little weird。Okay。

 so when people have different distributions， they have different fes of eyes。

So when you give to optimize revenue， you want to give it to the bidder with the highest virtual value。

 the highest PI of V I that need not be the bidder with the highest value。

To optimize revenue with non I D bidders， you fundamentally must move away from always awarding the good to the highest bidder。

好。The payments are also a little tricky to understand。

So that's going to motivate the main topic of next lecture。

 So now that we've completely solved for the optimal auction in this average case sense for any single parameterer environment。

 we're going to say， well， there are simple settings where this is an auction we might actually use。

 And they are more complex settings where in principle， the theory tells us how to maximize revenue。

 but they have extra properties or details which we never see in practice。

 like myth like allocating the bidders that are not the highest。

 And so the question we'll talk about on Wednesday is using the lens of approximation and saying。

 can we get almost optimal auctions using practical auction formats。 So I'll see you then。

