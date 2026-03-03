# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p19 -19-(Lecture 18_ Multi-Parameter Revenue-Maximization).zh_en -BV1fNVNzhEBg_p19-

All right， so let's move on to the fifth and final part of the course。

 which is going have a fairly different flavor than the first four。But it's， I mean。

 one thing in common with the last several parts is that there's been very exciting progress just in the last couple years。

 So again， really emphasis on sort of。Recent breakthroughs。

And so the main change is I'm going to switch from welfare maximization to revenue maximization。Okay。

 so some over the payments。Rather than the sum over the values。Okay。

 so literally for 17 straight lectures， we've been talking just about welfare maximization。 Okay。

 so we have three lectures where we talk about revenue maximization instead。 So if you like。

 you can think about this， We're switching from the perspective of something like a government trying to allocate resources like spectrum licenses in efficient way to。

 you know， more of a monopolist who just wants to make a lot of money or you you want to think about it where can be switching from a competitive market where you can't really get away with monopoly pricing to a less competitive market where you can。

😊，And let me just， I want to open the lecture just by reminding you of some stuff from last quarter。

About the challenges of revenue maximization that don't come up when you're doing welfare maximization so one reason we talk a lot about welfare is just because it's a fundamental objective。

 it's well motivated many settings， many real world combatorial auction designs are really motivated by welfare concerns。

But the second reason is that it's just， I mean it's pedagogical so welfare is just sort of much easier to study so have like so if you don't care about computation。

 you have the VCG mechanism which says you get incentives for free for welfare maximization。

 there's a mechanism which maximizes welfare even X post。

As well as if you knew the valuations up front。 Okay。

 so there's literally like zero loss from not knowing valuations up front。

 if you want to do welfare maximization， if you don't care about computational issues。

 and the story is very different with revenue， It's actually much more sort of exasperating to study because there's no analog of the VC G mechanism at all。

 So which mechanism makes the most revenue just depends on the input and general mechanism。

 A will be better on some inputs than mechanism B， even if there's just sort of one buyer。

And you just trying to figure out what take it to leave it offer to make them or you know how to set a reserve price on ebay。

 Should I set it to $10 or $20。 What depends right So basically。

 you're hoping there's gonna to be valuations just a tiny bit above your reserve price。

 But if it's just a tiny bit below your reserve price， you're out of luck。

 it was a bad reserve price。So as a result。I'm going to remind you。That。Even just to start reasoning。

I'm talking about optimal revenue maximizing mechanisms。

The most common way to even start the discussion is to assume a prior。And then when you have a prior。

 you can compare the performance of two different mechanisms just by just through their expected revenue。

Okay。And this was the reason that we did talk about prior distributions last quarter in 364 a。

 Now we're sort of used to them because we've been talking about Bayes Nash equilibrium and simple auctions。

 we talked a little bit about Bayesian incentive compatible mechanisms。

 So we've talked about about Bayes Nash equilibriumria last quarter。

 we never talked about Bayes Nash equilibriumria basically not once。

 but we did have a prior for a couple lectures and the reason was just because even though we were still just doing doance strategy and compatibleat mechanism design。

 we just did it to compare the expected revenue of different auctions。

 Okay so when we did Myerson's theory when we did the Bu Clthereorem， this is why we had a prior。

Now for these few lectures， we are going to be studying not just D mechanisms。

 we'll be studying Bayesian and C battle mechanisms。

 so we'll use the prior for you know in two senses， one to measure performance。

 but also two to reason about how bidders behave okay so last quarter。

 it actually wasn't important that bidders even knew the prior。

 they had dominant strategies here for Bayes National it is of course going to be important that everybody knows the prior guess so people know people do know that they're doing a best response on average over the actions of the other players。

Okay。So。Really simple example。So we talked about one buyer。So again。

 I want to say a couple quick refresher on the single parameter setting。

 really very brief just like five minutes。So when you just have one buyer。So if you have one buyer。

 I should say also dominant strategy and compatibility and Beijingesian incentiveatibility coincide with one buyer there's no one else to average over so it's just it's the best to do direct revelation and for one buyer。

 there's not much you can do as a mechanism designer。

 you can offer you can make a take it or leave it offer if you want， you can randomize。

 you could have a distribution over over takeake it or leave it offers。Okay， so distributions over。

So also called posted prices。可以。And given a prior distribution capital F on the buyer's valuation。

 just assume there's sort of one good single parameter， then of course。

It's kind of obvious what you should do， you just say， well， if I set a price of capital R。

 I'll make r dollars whenever there's a sale， and then the probability of a sale is just the probability that the bidder's valuation is at least the offer that I make it。

 so one minus the prior capital F at the price that I offer and I just want to pick the best one。

And that's it。So there's nothing， there's nothing nothing hard for one buyer and one good。

And let me just remind you the punchline of Myerson's optimal auction theory。

So if you have multiple buyers， and let's say one good for now。So the optimal single item option。

When you have valuations VI drawn from known prior distributions FiI。And these should be independent。

Not necessarily identical。Then the optimal thing to do is you give the item to the bidder with the highest。

 what？Who remembers from last quarter？Anybody， excellent。Gives item。If I was feeling mean。

 I would say， what's the formula for that again， but。😀Ha。😊，Yes， there will be a Z。

Gs Adam to the bidder with the highest。Virtual value。

Which is z minus1 minus the CDf at Z over the density at Z。So， for example。

 if it's the uniform distribution。Then this is just 2 z minus1。Okay。

 so it would be minus-1 at 0 and one at one for the uniform distribution。 So remember。

 virtual values can be negative。 it can be negative or positive。 So anyway。

 there's some formula for it。 Actually a couple of caveats。

 This isn't let me just tell you the fine print。So what I just said。

Assumes that the thigh eyes are increasing。That's the only case we dealt with last quarter and encompasses many of the distributions you'd ever care about。

 so Myerson called this the regular case。The theory extends equally well beyond regular distributions。

 there's just extra technical details that we're not going to focus on。

 we didn't focus on last quarter and we're not going to do this quarter either。So it assumes that。

 And then there's also the possibility， given that one virtual value could be negative。

 like this 2 z -1 function， it might be that all of the bidders have negative virtual values。

 And in that case， you don't award it at all。 Okay And remember。

 this is a fundamental difference between welfare maximization， revenue maximization。

 revenue maximization。 It can definitely pay off to just leave stuff on the table， okay。So， if all。

VIVIs negative。No sale。Okay。And in the case of where all of the valuations are I IDD。

 So what I just said here is true as long as the distributions are independent。

 but they can be arbitrarily different distributions。 If they happen to be identical distributions。

 then this becomes very simple。Then if everybody has the same distribution。

 everybody has the same virtual evaluation function。So if that distribution is regular。

 meaning fee is strictly increasing。Then the bidder with the highest virtual value is exactly the same as the bidder with the highest value with the highest bid。

 So if all the fees are the same and we're in the regular case。

 then what this is telling you to do is to award it to the highest bidder。Well。

 except in the case where therere all negative virtual values in which case you award it to nobody。

 so that just corresponds to awarding it to the highest bidder and supplementing it with a reserve price。

 where the reserve price corresponds to the inverse virtual value of zero， okay。

So summarizing for the Id regular case， the optimal auction is nothing more than a second price auction with a reserve。

 or if you like an eBay auction with a suitable opening bid。对。

So that's some nice stuff you get in the single parameter case。And in general。

 so that was specializing this， but now sort of actually generalizing this。

And this was the version that we proved last quarter。So in general， even if it's not a single item a。

 even if you have some more complicated set of feasibility constraints。

What Marison's theorem tells you is that maximizing expected revenue boils down as I。

e is exactly the same problem as maximizing the expected virtual welfare。 Okay。

 so that's how you solve it very generally in single parameter settings。

So maximizing expected revenue。Reduces。So maximizing。Expected virtual welfare。

Meaning the sum of the P I V Is over the bidders that win。嗯。Allright， so any questions。

 I hope this sort of jog stuff that。Is vaguely you vaguely remember。 Okay。

 so we're actually not going to really need to know the details of any of this。

 This is more just to set the context。 The plan for this lecture。 So like I said。

 there's been some very recent progress， but the plan for this lecture is more just to kind of do the setup and understand the issues better。

 okay。So no worries if you don't understand the exact details of what we talked about last quarter。

So why is this interesting the fact that maximizing expected revenue reduces to maximizing virtual welfare？

Well， the first reason it's interesting is just conceptual。 I mean， we， you know。

 there's a zillion mechanisms you could run， and this gives us some kind of understanding about which one is optimal。

 So this is a reasonably crisp characterization of what optimal auctions look like。

And we get some immediate interesting corollaries that are kind of unexpected。From this statement。So。

In Myson's theorem， the feasible region is actually super rich。 Okay， so you。

 say it's even just a single item ox for concreteness。 Biders have these different distributions。

 Maybe there's lots of bitterders。 You can do whatever you want。

 So you've got to be incentive compatible， but actually not even decent。

 All I insist is that you're Bayesian and incentive compatible。And you can be randomized if you want。

Okay。Well， Myerson's theorem tells you well what you should do is maximize expected virtual welfare。

Okay。And that's dominant strategy incentive compatibleat。 This is again。

 assuming all of this is I'm going to assume regularity。

So it's dominant strategy and instead compatible because the allocation rules is monotone。

 You proved this on an exercise set last quarter。 We and maximization gives you monotone allocation rule。

 it gives you a decent mechanism， and it's also deterministic right the values show up。

 You just compute the Vs and you just pick the best one。 No randomization needed。

 So I allow you to be B IC instead of DSIC。 I allow you to be randomized set of deterministic。

 You're like。No need。 optimal mechanism is neither。So the optimal BIC mechanism。

Is DCI and assuming regularity。Deterministic。Now full disclosure。

 we didn't actually prove this statement last quarter because I never actually defined Bayesian incentive compatibleatible mechanisms。

 so we only prove this for the feasible region of DI mechanisms。

 but basically the same proof works over the bigger feasible region of BIC mechanisms okay。

So we proved it in spirit last quarter， even if we didn't prove it in letter。Okay。

So that's reason number one to care about this reduction from revenue maximization to virtual welfare maximization。

 conceptual。 we know what optimal auctions look like。

 the second reason we might care is computational。 So suppose you wanted to implement a revenue maximizing mechanism computationally efficiently。

What this statement says is， well， you know， if you can maximize welfare efficiency and efficiently and you may or may not be able to。

 depending on the setting， know we've seen plenty of examples。

 even single parameter settings where it's NP hard to maximize welfare。

 but if you have an algorithm which maximizes welfare。

 then you can just reuse that exact same algorithm as a black box and maximize revenue。

W which is kind of amazing， actually， because these are totally different objectives of welfare revenue。

 I just opened this lecture by saying how much more of a pain revenue is than welfare。 And yet。

 once you pass to just having a prior independent valuations， computationally。

 they become exactly the same。 Okay Give me a black box for welfare。 I'll just compute the fees。

 shove those in as you know， effective valuations and run the black box and I'm done。

 I get a revenue maximizing option。😊，So both of those are very cool。

So the goal then for the remaining lectures of the course。So that was all single parameter stuff。

 right， monotone allocation rules that's not defined， obviously defined beyond single parameter。

So what want to understand is， to what extent can this amazing theory have a multiparameter analog and remember。

 multi parameterameter is absolutely everything we've discussed so far this quarter。

 pretty much okay。So for example， in commtl a。Okayect。So to the extent possible。

 we'd like a multi parameter analog。Of Myerson's optimal A theory。

Now Myerserson's optimal Auction theory is from 1981， so that's 33 years now。

 but kind of shockingly there's been some important developments just over the past few years and again。

 perhaps surprisingly some of those developments have been coming from computer science。

 not from economics。So today I mostly just want to help you understand the issues。

 do a little bit of setup and then next week we'll sink our teeth into you some of these recent results and we'll see how far we get in the remaining lectures okay but certainlyll give you I'll certainly be able to give you a flavor for the kinds of developments that have been happening just in the past couple of years okay。

All right， good so any questions about that before。

 so this is a review of challenges for revenue even in the single parameter world。

 now I want to start contrasting this with the significantly more complex multiparameter world。

 so any questions before we do that？Okay。So。I'll be able to convince you that the multiparameter world is very different。

 even just in the case of a single buyer。So warm up。One buyer。So multi parameterameter here。

 the simplest way to make it multipar is I'll just say there's two goods。Okay。Different ones， say。

So there's going to be a prior over evaluations。 So I need to kind of say what the valuations should be。

 The simplest valuations I can think of are additive valuations。

 So let's talk about additive valuations。 That means there's going to be a V1 and a V2。

Let's even let them be IID。Okay。Let's try to start with something trivial。Okay。

 so the sum distribution capital F。V1 and V2 are I I D draws。

 and the buyer's valuation for the goods it gets are just additive。 So it gets both It's V1 plus V2。

 etc ceter。Yeah。So now let's ask the same question we asked in the single good。

 single parameter world。RightSo again， there's no need to distinguish between B， I C and D S I C。

 right that's not the issue here。 Really， you know， with one buyer， it's more like a pricing problem。

 Okay， so you can think of the mechanism design problem in the general case of a single player as just we write down。

 you know， some options。 know， we just kind of figure out prices to offer for the goods for sale。

And with an added evaluation， it kind of seems like this， this is silly， right， right。

 So we've already， we've talked about added evaluations。 Everything always decouples over the items。

 You can just handle the different items separately。So presumably what we should do is just kind of。

 you know， there's some optimal price， that's like the same monopoly price for this distribution F。

 we'll just slap that onto the good， the first good， we'll slap that onto the second good。

 and then the bidder can pick any combination at once。Okay。So。Alright。

 so what's like the simplest prior that's non trivial， let's say。F is one or two。With 50。

50 probability。 it's pretty simple prior。So let's just think about item number one。

So if this is the distribution， what's the monooppoly price。

 Monoppoly price just means the thing that maximizes expected revenue。So there's an item。

 the person either has value one and the person has value 2。How should we price that。

 supposeupp they're the only one of in the world， what should we do？

So a price of one would get us what expected revenue。One， right， the law was take it。

 we'll get a buck， a price of two would get us what expected revenue。1， because we'll get two。

 but only half the time。 So it doesn't matter。 Okay， so one or two， whatever。

 we get expect revenue 1。 Okay， so there's two goods。 So we get expected revenue 2。OK。All right， so。

 you know， so if we wanted to kind of。You know， explore the design space。 So like。

 so what else could we do。What guys have we wanted。We could only sell the goods as a package。

RightSo we could say， look， you this is an incentive compatible mechanism。

 Either you get neither or you get both。 And if you want both， you have to pay some amount。Maybe。

 like。Maybe like。3。I mean， that's a silly insane compatibleible mechanism。

 right I make it to take it to leave it off or just on a bundle。Okay， so how well does that do？Worse。

 what does it get。でも。あけも。If I bundled them together for price of three。I think there's another just。

そけれ。Sorry。Why would you ever get so sorry， say it again。Yeah。From the seller perspective， right。

 we're not talking about utility， So we want to say we want to do revenue。

Should it be a three force chance？A agree because reinforce forcedce because。

They have to value either of the items at you， right？

So the only way the person won't take it at a price of three is if it's one for both。

And so that's probably one quarter， so probably if a sale is three quarters and you make three bucks。

So it's two and a quarter。It was actually better。Right。So that's interesting。So better。

Bundle at price 3。Expected revenue is nine quarters。So， okay。

 so we need to work on our intuition a little bit better， maybe。RightWe're so used to welfare。

 where it's true。 when you're maximizing welfare， added evaluations， it does trivialize things。

 It really does decouple over the items for welfare。 that's the correct intuition。

The incorrect intuition is thinking that， you know。

Lessons for welfare carry over to revenue maximization。 Sometimes they do。 But， I mean， it's kind of。

' kind of an amazing theorem when techniques for welfare carry over。

 Okay that's sort of the exception that proves the rule。

So even in like the simplest multiparameter thing we could think of。

It sounds like the optimal auction is not simple or anything。 This is the optimal auction。

 I'm pretty sure， but it's maybe not the first thing we would have guessed。Okay。So。

Let give another example。Let's say f is zero or 1 or2。Equally likely。Oh， yeah。

 one thing I should say is。The error and the reasoning actually is really easy to see if you think about like a really large number of goods。

So imagine have one buyer， M goods， IID going to infinity。Right。

The law of large numbers says that the bidder's value for all of the goods gets highly concentrated as the number of goods grows large。

 So you know， almost deterministically what the person's willing to pay for the grand bundle。

 So why not just price the grand bundle at's slightly less than its expectation and you'll extract almost of the full welfare almost all of the time okay。

So it shows up already with two items， but the power， know， bundling for added evaluations。

 the intuition is very clear when you think about a large number of items。Okay， so。Good。

 so let's think about this example。0 or1 or2， equally likely。So what are the things we've tried。

 So if we sell separately。Separately， I cannot spell that word。Individually。

So what's the monopoly price on on a single item with this distribution。Price one， price two。

 does it matter？It doesn't matter， two third either way。

 either you can get a buck with two third probability or two bucks with one third probability from a single item。

So it price one or two。Expected revenue from the both is4/ thirds。So， bundling。Okay。

 so given that this is four/ thirds， the price of zero is one interesting， is uninteresting。

 a price of one is uninteresting because that would be less than this even if you all sold it。

 a price of four seems a little aggressive because you're only going to sell with probably one/ ninth。

If you price it at four。So that leaves two and three， so a price of if you said it at three。

Then the only way you'll sell it at three is if you have。At least one，2。

 and at least one thing that' at least one right So the winning combinations at a price 3 are 1，2，2。

1 and 2，2。 So it's a one in three chance of getting a price of three。

 So that's expected revenue  one。Price 2。 So when will the bid。

 when will the bidder take it at price 2， Well， as long as it's not 0，0，0，1 or 1，0。

 So now there's 6 outcomes， it will take it。 So that's a two thirds probability。 price 2。

 So that also gives you four thirds。Okay。So bundling again， at price 2。Expected rav equals4/ thirds。

Yeah。So there's something better than either of these。So it's better to offer。To the bidder。

 So with one bidder， you can basically think of it as you know I just write down a bunch of options right so I basically say you can pay this and get this。

 you can pay this and get this， you can pay this and get this。

 And the bidder just walks up and say that's my favorite option。

 Okay that's the way you can think about mechanisms when there's only one buyer。And so。

 the options are， basically。We say to the buyer you can take any one item。

 so either the first item or the second item。At a price of two。Or we'll give you both at a discount。

 price of three。Okay， and so again， the bo， so there's three options。 The buyer picks their favorite。

 which everyone maximizes their utility。 Okay， so again， it's instead of compatible a because。

 I mean， in effect， whenever the buyer can make when any decision they make。

 it translates to the revelation principle to an incentive compatible option。All right， so how why。

 okay， I claim this is better than4 thirds。Let's see why。So this is just the valuation profile。

 so V1 is 0，1 or 2。V2 is 01 or2。 each of these is a one ninth chance of happening。All right。

 And so really， okay。There's an issue of tie breaking。

 so assume that the buyer always breaks ties in favor of the seller。

And the way you can enforce that is just you add little epsilons。 Okay。

 so think of this as really price 2 minus epsilon。And think of this as price 3 minus two epsilon。

Alright， so everything costs at least 2。So clearly， we're getting a zero in all of these。Right。

How about here。 So if both valuations are one， how much money do we get。Ziro。

How about if it wants one for two and the other for 0。Yeah， so then it'll take the item at once。

 Okay， again， that's why I made the price two minus epsilon to make sure it really takes it。Okay。

 so how about all right， So another probably easy one。 How about 2 and 2。Yeah。

 then it's going to take the grand bundle， right？How about here， How about if one，2 and ones1。Yeah。

 so so this is why I did the -2 epsilon right， So for the So here if it's2 and one。

 it's it's value for the grand bundle is 3。 It's value for just the better item is 2。

 utility is epsilon。 If it takes the one item and the utility is two epsilon if it takes the grand bundle。

 So it takes the grand bundle。3，3。Okay。So， the expected revenue。Well， so three ninths。

 it gets a three。Two nights， it gets to two。AKA 139s。

 the relevant point being it's bigger than 12 nights。

Which is what we' were getting with the other options。Okay。Alright。

So not totally clear what to draw from these examples yet。 But let me， this example。

 I won't do all the details， but I'll tell you the example。 that's basically the similar complexity。

 which shows that。This corollary。Is already false。We have two items。One buyer。呃。Yeah， that's it。

 So it's no longer to be true that optimal mechanism is necessarily deterministic。Okay。

And so this will give us already a bona fide separationation。Between the two。Scenars。So example。

Again， IID。One， two， or four。With probability 1 sixth。One half and one third。So I write it down。

No tricks up my sleeve。And the claim is that the unique optimal auction is the following。

It's similar to this one， the twist being。You offer any one item。With probability，50%。

At a price of one。What do I mean by that？I mean， that one of the things。

 one of your options is to buy a lottery ticket。Okay and it says price is a dollar。

And it's a lottery ticket thats gets realized as item A。

 the first item with 50% probability and 50% probability gets realized ass nothing。

Bitders are risk neutral。 So you pay a dollar with certainty。

And then after you go home and open the box， 5050 chance that it has itemA。

that's what I mean by I'm selling 50% probability version of item A。

And so you have the option for either either of the two goods。Or。Both items。With probability，100%。

Ha a price of four。Okay。So I'll leave as an exercise。So first of all。嗯。Support A。

The expected revenue of the auction I just told you is a little less than3 and a half。And B。

That all deterministic auctions。Strictly worse。Okay。

Where deterministic auction just means that the only outcomes are either you get nothing。

 you get item 1， you get item 2， or you get items 1 and2。

Those was the only four possible outcomes in a deterministic auction， with two goods。

And this auction has an outcome that does not look like that。Okay。

You might wonder why not just offer it with probably 100% at price two。

But it's really not the same thing。 Okay So when you charge an extra dollar from item。

 you subtract one。From a bidder's utility， when they have it， they paid a dollar more。

 you sold these one less。When you allocate it with 50% probability。

 that's like dividing their evaluation into， whatever it may be。Okay。

 so the probability is a way to manipulate the utility in a multiplicative way。

 the price manipulates the utility in an additive way。

 and you just can't really simulate one with the other。But again。

 this is really something you should play around with to explore and not really to do here in class。

Okay， so。What was the point of all this？Well， one was just， you know。

 so we're back in the revenue maxization mindset。A little bit。But also。This kind of。You know。

 remember we have this motivating goal。Develop a multi parameter or analog Marson theory。

 so this sort of tells us to brace ourselves a little bit。So this tells us that。

 more complicated things are going on very quickly as soon as you move to multiparameter settings。

 So we should maybe you know， limit what kind of analog we could hope could be true。

And we should maybe be ready to use relatively sophisticated techniques to derive whatever multi parameterer analog exists。

So upshot。Okay， so first of all， you know， notice， notice how much was the same in all of these examples。

 There was always one buyer。 There was always two items。 There was always an added evaluation。

 and V1 and V2 were always drawn I I D。 The only thing that varied was capital F。

 and we weren't really varying it that much。But the format of the optimal auction was varying significantly with these small variations in capital F。

And this is even with one buyer， okay so look at how different that is from the single buyer single good case where always what we want to do is some take it or leave it offer and the only thing could change is exactly what that numerical value is。

 which changes in some easily understood way as you vary the prior F。

Okay's just whatever the maximizer of that， R times1 minus F of R is。So the format。

Of the optimal mechanism。Varies with F。So even ns n equals 1， m equals 2。IId。Additive。

And what this example shows is that the optimal a might be randomized。And so this， I mean。

 this immediately tells us that there's not an analog of Myerson's theory of the form。

 take as input the valuations， do some deterministic transformation。

 and then run welfare maximization and al palpsy optimalimmal auction We now know that is false again we now know there cannot be an extension on that form。

All right。Okay。So any questions。O。All right， so。So how can we get a handle on these optimal mechanisms。

 It seems like we might need， you know， you know， sort of explicit close form formulas seem kind of hopeless。

So we need some more general， powerful tool。So what we're going to mostly explore optimal auction design is through linear programming。

 Okay， and so I want to just say a simple， a few simple things about using linear programs to characterize optimalum auctions today。

 and then I'm going to say some less simple things next week。Good。All right。

 so here's the first observation。Which is rarely。Directly useful。In its own right。

 but this is a good starting point。I claim we can formulate。The optimal mechanism。

Ass the solution to a linear program？And we're going to start with just the single buyer case。

 But actually， this will be general enough。 It'll extend the bona fide mechanism design。

 So with multiple bidders。So， you know， this is not very explicit， you know。

 just writing down some linear programming optimal solution is the optimal mechanism。

 but it's a start， We've got to start somewhere okay。So for starters， let's just say one buyer。

I am going to allow any number of items， there's no reason not to here。So set U of M items。嗯。

I'm going to assume that the prior distribution has finite support， just like in the examples。

 so there's a finite number of different valuations the bidder might have。

So there's a finite set capital V。I'm also going to assume additive evaluations。

 We'll probably be able to talk some about generalizing that。

 But added evaluations will be interesting enough to get started。And then we， we know the prior。

 So we're just told a probability mass。the u F。Of V L or F of V。For all V And V。OK。

So these are all non negative numbers， suming to one。Yeah。O元。Also。

 in what I'm going to say for the rest of the lecture。

 So remember each of these is really an M vector。 It's an added evaluation。 There's M items。

 So it's how much you value each of the M items。We'll never need to assume that these are independent。

 Okay， so these can be arbitrarily correlated。 There's only one buyer。

 So we're not talking about correlation between different bidders。

 There's no other bidders right now。But between items。

 the relevant parts of the add evaluation can be correlated。All right。So they LP， excuse me。

The decision variables are as follows。WellI should say， so the revelation principle as usual applies。

 so at least in principle in the search for optimal mechanisms。

 we can focus on those where direct revelation is a dominant strategy for the bidders。

 again one buyer， so it may as well be dominant strategy。So the decision variables are just XjV。

So this is the probability that buyer。Gets item J。When it reports the valuation V。

And P of V is just the payment。Okay， or expected payment。Remember。

 we're thinking of buyers as being risk neutral， so we really don't care if the mechanism is randomized。

 all we really care about is the expected payment because so we'll just keep track of the expected payments。

你确。So in a deterministic mechanism， for example， these are going to be either zero or one。

Okay so the first two examples， these would be0 over one。 In this example here。

 this corresponds to having an X J V equal to 0。5。Okay。

So those are decision variables and the observation is that it's easy to write both the revenue and the incentive compatibility constraints and also individual rationality constraints as linear objective and linear constraints in these variables so I'll show that to you。

 but that's the point here。Allright， so the objective。Right，So this is what we're solving for。 Okay。

 so we think of this as defining a mechanism， okay。Allright。

 And so now over the space of all mechanisms， as represented by these X Js and P's。

 which one's the best。 But so we want to maximize revenue。

And so we want to maximize the revenue from this one buyer。And so。

Assuming that it actually does do direct revelation。So we just say， well。

 what are all of the valuations that the buyer might have？

What's the probability that it has a given valuation？

And then how much money do we get from the buyer when its valuation is B？Okay。

So that's the expected revenue。 remember the F's little F's are given， the Ps are variables。

 that's a linear objective。Okay， so the constraints， so let's start with the IC constraints。

So these are for all V and V prime。So I'm thinking here of V is the true valuation and v prime is。

Potential。Miss reports。So what's the utility of a bidder when its true valuation is V and it actually reports V。

 So that's just going to be， well， it's some over the items。

Its the bidder is true value for the item。The property gets that item when it reports truthfully。

The payment it gets when it reports truthfully。And that should be at least the same quantity。Again。

 true valuations。 But now it looks at the。New allocation probabilities with the MI report。

And the new payment with the mis report。Okay， so these are the I C constraints。

 Whatever your true type V is， you get better utility from reporting it than from any alternative type V prime。

So the individual rationality constraints， this is what says that a directly revealing bidder should always get non negative utility。

So this is just basically， this should be non negative。 Okay， So for all little V and big V。

If I look at the utility， when it。Reports truthfully。That's non negative。Okay。And。Also。

Of course you want these things are supposed to be probabilities。So， let's make them so。Okay。So。

This is a linear program in the decision variables is X and P。Okay。Because again。

 we know the potential valuations and we know the distribution little left。

Areed winning your program。And the claim is that the feasible solutions。

To this linear program correspond exactly to the IC and IR mechanisms and that the objective function faithfully models their revenue。

 right？So if you give me a mechanism， what is it， it's by definition a mechanism' is an allocation rule and a payment rule。

And so the allocation rule of your mechanism， I can pretty much just read off the values of the X JVs and the PVs。

 I imagine feeding at a given input V， And I just watch what it does。And if it flips coins。

 that just tells me the probabil is， these Xj of Vs。

 So given a mechanism that induces a feasible solution。Given a feasible solution。

 it induces a mechanism， right， So again， you know， basically on a given report V。

 a solution to the linear program just tells me exactly what to do。 Okay。

 tells me with what probability to give a given item J to the bidder。

Because valuations are additive and we assume it is a risk neutral， you know。

 I can treat items independently right so if x1 is 0。2 and x2 is 0。5。

 I can just flip independent coins for deciding whether to give player the player， the buyer。

 item1 or item 2 doesn't matter okay。So if you agree then just identifying the optimal mechanism。

 the revenue maximizing mechanism with respect to a given prior。

 boils down to just solving this linear program。Aged。All right， so some more comments。

 so as we noted， so deterministic mechanisms are the special case where each xj of v would either be equal to zero or equal to1。

But as we know， awfulomes might not have that property， so this need not be integral， this polytope。

What else？Right， so， for example， you know， what would how would the grand bundle。

 So how would bundling all items together be represented in as a feasible mechanism。

 that would just say for a given V， either Xjv is equal to 0 for all J or Xjv is equal to1 for all J。

 So that would be equivalent to the mechanism that all it does is offer the grand bundle at a common price。

 And then for Vs below that bundle， all the XjV would be0 for V's above that price。

 all the XJVs would be equal to one。So the size， and this will become important in a second。So。

 the size。Well， we have one decision variable。 So how is it scaling。

 So basically for each choice of J and each choice of V， we have a decision variable。

We're not so bummed about having a Susan variable for each item J， that seems reasonable， you know。

 having one for each possible evaluation is kind of a lot potentially。

 there's a lot of potentially different valuations。

 but it's also hard to see how you'd write down a linear program that didn't have that size that encoded incentive compatibility constraints okay。

So size。Polly in V。so that's how you should think of the size of this linear program。Okay。Now。

 one thing that's nice about the linear programming approach is。

It can be extended in lots of different ways。And for now。

 let me just mention that it's easy to extend this to multiple buyers。

So now we're going to have variables X， I， J V。 All。 So again， now we have n buyers。

 each with an added evaluation drawn from some known prior。Okay。So now。

 instead of just evaluation of a single bidder， we have a evaluation profile。 So this is an n vector。

And so now we specify the probability that bid I gets item J when the valuation profile is whatever it is。

 okay。And。We again keep track of the expected payment or the payment by Bider eye。

 and now it's not just for a single report by that bitter eye。

 but it's by the full valuation profile fee。So again。

 this is just encoding the allocation rule and the payment rule now that we have multiple buyers。

And so now， the new LP。Right， so now we're just going to sum。Right。

 so there's everything that might happen every valuation profile。

 the probability of that valuation profile。 And we just look at the amount of money we get from each。

Okay。So that's the revenue with multiple buyers。And now。

So one thing I want to point out is now that we have multiple buyers。

 there's suddenly a difference between a DI constraint and a B I C constraint。

So remember when there's other people， there's a distinction between saying。

 my action is best for me， no matter what other people are doing。Versus， it's best for me。

 on average， over what people are doing。 given some prior over what they're doing， okay。

So we're going to be talking about Bayesian incentive compatible mechanisms。 Okay。

 although this linear program could encode each。But so what would be the BIC constraints？

So now you want to， well for every bitter eye。Given the information it has when it chooses in action。

 when it's choosing whether or not to reveal directly or not。And so what does it know。

 pretty much all it knows is its valuation VI does not know that of the others。

It's pondering some misreport， VI prime。And direct revelations should be best for it in the sense that it should maximize its expected utility。

 so averaging over averaging over a v minus I。So this is going to be the average。

So this is just the possible values by the other bidders。

This is just my notation for the probability that the other bidders have this V minus I。

 I'm writing this， assuming prior that the different F subs are independent。

 otherwise I would just want to condition on v sub I here， it would be the same thing。

And then I just look at for this particular v minus I， what is， in fact， the utility of bitter I。

 Okay， so sum over J and U。V， I J， X， I， J， V bar minus。PIV bar。

And this should be at least the analogous expected utility for the M report VI Prime。So that。

 pretty much by definition。Are the bayesian insect compatibility constraints？Okay。

You get equally well encode code dec if you wanted to。

 then instead of having the sum over all of the V minus eyes。And a constraint for each V。

 you would have a constraint for each V， V prime I and v minus I。

 and then the constraint would just be that this is at least this。All right， so similarly。

So Bayesian individual rationality。Same thing。So for all I and truth reports VI。

Averaging over the possible types of the others。It should be that。

The expected utility of truth telling。It is non negative。Okay。

And then it's also important that each good is sold to only one person。So sumvari1 to n。Xi J。V bar。

The most one。For all J。For V。And then， non negativity。看。

So that's how you'd write down the analog of this linear program。 again。

 solving for the revenue optimal B， I C mechanism。Has the solution to linear program。

So just like before， there's a correspondence between the feasible solutions of this polytope。

And the mechanisms， the direct revelation mechanisms that satisfy Bayesian incentive compatibleatibility and individual rationality。

 Again， you can just read off from a solution to this linear program。 What is the allocation rule。

 what is the payment rule And again， because valuations are additive， and bidders are risk neutral。

 you can just handle each item J separately and you can just do， for example。

 randomized rounding so if you solve this LP and you look at a given J。

 look at the X Js correspond on a given input valuation profile V。

 and you can interpret those as the probability that each bit I gets that item J。

 you can just flip coins and allocate correspondingly So any feasible solution to this linear program can be realized as an incentive compatible mechanisms。

So what I want to leave you with is the following observation。With the following issue。

So when we had a single buyer。And we talked about the size of this linear program。

We said that it scales linearly or you， it scales polynomially with the number of possible valuations of this one buyer。

 Okay So certainly there are simple examples， right， that was like two or three。 Okay。

 we just have these small discrete distributions。 So as long as the support is reasonable size。

 this linear program is reasonable size。So how many decision variables are there in this linear program？

What is it proportional to？What if there are end players and each has a support size of cardinality too？

How many variables are there in that linear program？So there's end players， right？

And this V arrow is an n vector。RightWhere each entry can take on any one of that bitter eyes possible valuations。

 So even if you only have two different possible valuations， there's two to the n。

Of the strategy profiles and probably have many more than just two valuations。

 Okay so here for the single buyer case， the number of variables was you could imagine scenarios where this would be reasonable size。

 Basically， you cannot even imagine scenarios with any number of any reasonable number of players where this has reasonable size。

I really need to do this linear thing once， right to find the mechanism that's true。

So like if you could write this down， so you're absolutely right。 So you'd be happy。

 you'd potentially be happy if you could solve this with two weeks on a huge cluster。

I claim there are plenty of problems where you can't even fit this into the memory of all the world's computers。

SoBut yeah， you raise a good point， actually， excellent point。

Then it would just be sort of table look up to figure out what to do once you solve it， yeah， Ol。

The constraints， though， are there。How many constraints are there？Wow， okay， good。inanc。

 unfortunately， there's this one。Oh that。So this one says that goods can only be sold once。Still。

 I mean I。You're totally on the right track。So for the IC constraints。

It is a reasonable number of constraints， and the IR constraints is a reasonable number of constraints。

And we're going leverage that at the beginning of next lecture。Okay， so excellent point。

So there seemed to be some opportunities for compression， you know， for optimization。 Okay。

 but I just wantanna， I just want to point out that。We need to do something。

So exponential size and n。And it really， it's in two senses。 I mean， you know， in these lectures。

 I'm not going to emphasize the computational aspects。 I'm not going to。

 I'm not going to necessarily envision actually solving these linear programs。

 I more want to get a conceptual understanding of optimal mechanisms and what they look like。

 And even for just that conceptual understanding。 This is the wrong linear program。

 it's just sort of a two wasteful encoding of the optimization problem。 So this is too big。

 We want to do dimensionality reduction， and that's going to be the main topic of next week。

 So see then。