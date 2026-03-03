# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p18 -18-(Lecture 18_ Pricing with an Unknown Distribution).zh_en -BV1yqVzzqEQ5_p18-

Al right， so the plan for this lecture is to continue the theme that we introduced last lecture with self-improving algorithms。

 that theme being we're going to sort of make a stronger distributional assumption than we had been in smooth analysis and when talking about hashing。

 So we'll really think of inputs is being drawn ID from some distribution and we'll allow algorithms to react even evolve。

 that's sort of even what we want。 we want them to evolve so that they're as good as possible with respect to that distribution seeing some number of IID samples。

 so last time we talked about sorting And so today I want to talk about mostly just a very simple pricing problem。

 but then also a little bit at the end about auctions。

 But the bull is going to be very similar given I samples from an unknown distribution you want an algorithm or an auction that converges quickly to how well you could have done had you known that distribution over inputs upfront。

So here's a pricing problem， It's about the simplest one you could imagine。

 but it still turns out to be pretty interesting。So。You want to sell something。

 I you' got you've got a good or you've got a service。

 And there's a potential buyer that you've identified。

 You don't know what the buyer is willing to pay for that good or service。 So if there's a buyer。

With an unknown willingness to pay。Or value。V。Okay。You don't know what V is， if you knew what V was。

 the problem would be easy？So what you want to do is you want to set a price key。Okay。

 and this is going to be a taker to leave it offer。 Okay。

 the buyer can either take it and pay you P or not take it and walk away。So。

If the price is bigger than what they're willing to pay。The buyer is going to walk away。

 there'll be no sale， okay， and you make zero revenue。On the other hand， if the price is right。

Then there's a sale at price peak。Okay， so the seller makes p bucks in that case。

And we want a reason about how the seller might want to set this price P。

There's this intuitive trade off。The higher you at the price， if it turns out there's a sale。

 then the happier you are， the more revenue you get。 But in some vague sense。

 it seems less likely there'll be a sale。 The higher use at the price。 Okay。

 there's no distribution on the board yet。 So it's not clear what I mean by less likely。

 but that's sort of the intuition。So that's that's what's pushing in either direction and setting the price higher or lower。

 And without any further assumptions， frankly， given that V is just some totally unknown number。

 it's not even clear out as sort of reason about this。

 how to prove theorems about which P's are good or which P's are bad。So。We're going to。

Like last lecture， think of V。 the willingness to pay is coming from a distribution， okay。

So distribution capital F。 So F here denotes the cumulative distribution function。 So remember。

 that means。Capital F of x denotes the probability。That the random variable is at most x。

That's capital F of x。And so for the moment， as a thought experiment， this won't be our main model。

 but for the moment as a thought experiments， imagine the seller actually knew the distribution capital F so to be clear。

 the value V， the realization remains unknown， but the distribution capital F from which that value was drawn for the moment。

 we think of as known。Well， then it's a pretty easy problem to think about， actually。

So just think of that if you just sort of set some price P， How much money would you make。Well。

 whenever there's a sale。You make P bucks。And then that's just gets multiplied times the probability that there's a sale。

 Okay， which is exactly when the value V is at least P。

 So it's exactly the complementary event of this one。 Okay what's one minus capital F evaluated at P。

So this is an expression we're going to see many times with different notation throughout the lecture okay so it's always important to remember for this single buyer problem。

 there's two terms， the money you make on a sale， the probability of a sale。

 you want this to be high， you want this to be high but they trade off against each other okay。U。

Oops。加了卖。Revenue per sale， fraction of the time you get a sale。So， you know， if you were the cell。

 you just said， P to maximize this， kind of a no brainer。So just to wake you up。

 why don't you work through an example over the next。30 or 60 seconds or whatever。

So suppose the distribution was a uniform。On 01。O。So I。e。

 capital F of x is just the identity function。On01。

M you think about what you would set P2 in that case？Yeah， that's a good thing to set it to。

So how would you solve this problem， Well， you know， you just instantiate this。

 I told you what capital F is。 It's the identity function。

 So the expected revenue function becomes P minus P squared。So that's a concave function。

 The second derivative is negative。 second derivatives-2。

 So all you have to do is check the socalled first order condition。

 you have to do is set the derivative to 0 and solve and you're done。 Okay。

 so you just set P minus p squared equal to 0 and solve you get p equal1 half。

So what's the expected revenue， the maximum possible expected revenue？quarter， right。

 So you're going to sell half the time。 And when you sell， it'll be a 。5。

So I want to wake up your calculus brain cells， which have probably been long dormant。

So let me give you another example。 What if it's the exponential distribution。

So1 minus e the minus x on the real line。So this you might not be able to do in your head。Is it one。

 Yes， it's one。So a little terminology。 So the best P is often called the monopoly price。

 like this this is sort of like you're the only， you're sort of have a monopoly on this bidder。 Okay。

 so given that you have no competition， this is how you should extract maximum revenue。

 So we'll call sometimes call it the monopoly price， I'll sometimes use the notation P star。

 So for uniform P star was one half。For the exponential distribution， P star is one。

 what is the expected revenue at the Monpoly price？1 over E。That's right。

Because the selling probability at the price one is exactly whenever and you make a dollar whenever you sell。

Okay。Good， so， you know， but the high low point here is， if you know the distribution。

 this is sort of a solve problem， right。Calculate some derivatives or fire up mathematic or whatever you want to do when you just sit P appropriately。

And you get， you know， reasonable answers。 So that's not the model。 This is。

 this is more kind of the holy grail to which we want to aspire。 Okay， because actually。

 as the algorithm designer our lives is going to make our lives a little harder。😊，Namely。

 F is going to be unknown。Okay， so it's still a little different than it was at the beginning because we are going to assume that such an F exists。

 Okay， and we're going to have the opportunity to observe multiple samples and therefore。

 learn something about capital F。So we still have some non trivialvial assumption there。

So just like last lecture， we saw a number of sorting inputs before we had to try to converge to what would be the information theore sorting algorithm。

Here we're going to have M。Again， training inputs or samples。And these are just IID draws。

 let's call the V1 through VM。From this underlying distribution， capital F。 So I repeat。

 you do not know capital F。You have partial information about capital F in the form of these MIIID samples。

So we have sort of a。Pameterterized， we have sort of a measure of how much information we have about the distribution in the form of the number of ID samples that you've been given。

So what's the goal。 Well， the goal is the same thing I was last lecture。 So quickly。

 meaning after hopefully not too many samples， we want to be able to solve the problem。 I。e。

 define a price so that our performance I。e。 our expected revenue is just as good as it would have been had we known capital F upfront。

 that is we want to do as well as the monopoly price in this formula。So goal。

 having seen V1 through VM as a function of those samples， we pick P， and we want it to be。

That our expected revenue on the real distribution， which is this formula。

Is basically as high as you can get。 That is。 It's basically the same as。

The expected revenue with the monopoly price。So something like within a1 minus epsilon factor is what we'd love to have。

Okay。So in a lot of pricing problems and auction problems。

 there's actually kind of a very nice interpretation of what these training inputs are。

 these sort of samples from the distribution， which is just your data。And in fact。

 definitely some of the big data companies do roughly exactly this right so imagine you're ebay or imagine you have a search engine and you're running sort of auctions on keywords。

 you can just look at what people bid on these keywords or on these products in the past if you assume some kind of stationity which depending on the application may or may not be true。

 but if you assume some kind of stationity， those are effectively giving you these IID samples So again you'd like to extract from your past bid data how should you sort of tune things like the reserve prices of your auctions tomorrow。

So it takes a very natural interpretation a lot of modern applications。Anyway， this is what we want。

Okay。Any questions about that？Yeah， about。Good question， That's exactly what's up next。All right。

So that's what we'd like to do。But there's kind of a problem。

Which is what Andy's question was alluding to， which is the way I've phrased it。 we can't do this。

 Okay this is too much to hope for in the following sense。

So there's really two questions we want to ask so first is the design question。

 which is what's the smartest way to use your data。

 Okay so what's the smartest Ie the best function from samples to prices。

 But then also we might want to study what's sometimes called the quotequote sample complexity。

 which is how much data do we need to harvest in order to achieve a certain kind of performance so we want to get within 90% of optimal。

 how much past data do we need to use。And so the issue is that， you know， in some sense。

 the sample complexity is infinite。 Okay， What do I mean， I mean， for all fixed number of samples， M。

Do remember the little M is the number of samples we get？There exists a distribution。Capital F。

Such that this， and by this， I mean the goal over there。Is impossible。And it's not a deep thing。

 It's easy to explain the issue。Is if you have a very， very small chance of winning the lottery。Okay。

So consider a distribution。Where the probability that v is big。Let's say capital M。Is small。

 So let's say one over little M squared。 we can M little M is the number of samples。

 Capital M is just some big number。And then otherwise it's zero。Okay。Where M is big。

Let's say like at least little M cubed。Alright， so first， what if we knew the distribution， Okay。

 if we knew the distribution， then we knew we know what capital M is。 Okay， and I mean， in general。

 it's kind of a no brainer to figure out what to set the price to， right， So the value 0， Who cares。

 we don't want to deal with them。 And then if they only have one possible positive value。

 we should just set the price of that value。 and make them pay everything they're willing to pay。

 So clearly， in the optimal price is just to set it equal to capital M， okay。So opt。

 so P star equals capital M。AndO is capital M over little M squared。

 And so like for capital M is little M cubed， then this is little M， Okay， which is big， potentially。

 it's as the point is this is as big as we want。 We just pick capital M big。On the other hand。

We get these little M samples。What are we going to see。Zeros。

 nothing else without high probability I have to be very lucky to see even if we see a capital M great。

 we're home free， but that's almost never going to happen。So with high probability。All VIs are zero。

So we're then responsible for hallucinating up some price。

 basically just positing some wild guess for what this unknown capital M might be。 Okay。

 and almost all the time， we're either gonna get too high。

 And then we'll never make any money at all。 or we're gonna guess way too low。 Okay。

 so maybe we guess M over 2 or M over 100 or who knows what。 Okay， so we're gonna be way off。

 So well make a little bit of money， but nowhere as close to what we could。

 Certainly not  one minus epsilon times what we could have we known it upfront。

So why do I present this， Not because it's interesting。But just because it says。

 we need to at least make some modest assumption about what this distribution capital F is。

And the good news is， many different modest assumptions suffice for interesting results。

 I'm going to show you two of the many ones that suffice in this lecture。😊。

So one of them that suffice this is we're just going to look at bounded valuations。

So to fix this issue。Mild restriction。On F。And the first restriction I'm going to impose。

We'll look at ancompar one later。Is we're going to assume that the support of F。Lies。

Between one and capital H， where capital H is some parameter that we know。

So we know upper bounds on the support，1 and H， we know nothing else at all about capital F。

 capital F can be arbitrarily weird otherwise。Good。So。Now we can actually answer this question。

 We can understand this goal。 And again， to reiterate， the goal really has two parts。

 So first of all， given samples， what's a smart way to use them。

 what's just a good function from samples to prices？ And then second of all。

 if you had a particular revenue target， like a1 minus epsilon approximation。

 what value of M is necessary and sufficient。 So how big does M have to be before you can get it。

All right， so we can answer both of those questions just in this model。Any questions？Yeah嗯。

Trowing on in， in options like ebay， but in。Super high value option。こで。They' collect the data also。

はい？So the agents know about we figure out that we are going to use the data than they might。

Play like， when。Play to play with the data so submit false values such that That's right。 And。

 you know， in the applications I mentioned， it seems like hard to pull that off。 if you're just。

 I mean， it's I'm not so sure that actually Google keyword advertisers are deliberately under bidding so that the subsequent reserve prices are higher。

 They could try， but it seems a little， it seems a little hard to pull off touction in which one work。

 Oh yeah。Make sense。 Yeah， no， so there's no question there is an incentive。 who play role at。

Smarer than people were crying at them。'Les money。So agreed。

 So there's potentially incentive issues if you're harvesting from the same people you're later selling from。

 agreed。 So we're going to ignore those in this lecture。Okay。Alright。

 so I need to do a little bit of technical development to explain how this is going work。Ultimately。

 our pricing algorithm is going to be very natural。 But it's especially now， I mean。

 to see how it's natural， we need to think about it in just just the right way。 Okay。

 so let me sort of tell you how you should think about。You know， learning so the high level plan is。

 remember， So we talked about this with a sorting application on Monday。Which was a really naive and。

 impractical way to approach that sorting problem would be to try to learn all in factorial probabilities of all the different possible permutations you might see。

But that would take in factorial samples， at least it would take in factorial space to kind of remember stuff。

 all those statistics。 And it's not what we did。 We just learned relevant statistics。

 a small number that were sufficient to get a sorting algorithm， which worked well。

 So that was great。 That was a huge win。 So it's the same thing here。

 We don't really want to learn capital F in sort of excessive gory detail。

 We just want to learn enough relevant statistics about capital F that werere off to the races with figuring out basically the right price。

 Okay， so that's what I'm going to develop Now。 I'm going sort。😊。

Develop your intuition for what are these relevant statistics about capital F to get a good solution to the pricing problem。

Okay。So。I need to tell you about prices in the corresponding quantiles。

So we're going to go back and forth。Between two different views of the same thing。

 basically the same thing。It's basically two different parameterizations of all the possible prices that you might use。

So。For the moment， let's just draw some pictures about of some distributions。

 Ass we knew a distribution capital F。 right， So in general， CF functions sort of look like this。

So remember， it's at a given point， at a given P， the fraction of the mass， which is less than P。

 So this is going up with P。And it starts at 0。 And then in this case， at H。

 it would terminate at one because it's a probability distribution。

So you can think of F as mapping numbers in this case between 1 and H， the numbers between 0 and1。

Now。If you think about it， what we really care about for the revenue computation is not so much F of P。

But what we care about is one minus FF P。 That's a little more natural。 The probability of a sale。

 That's like the good case。 right， So being below P is the bad case， being above P is the good case。

 So let me actually just kind of do a quick flip of this。

 So I'm going to replace this by one minus FF P。 I'm also going to call it Q。行。And so now。

 instead of this going from southwest to northeast， this goes from northwest。To southeast。Okay。

So if you set a price to be zero， then the selling probability is one。

 if you set the price to be more than capital H， then the selling probability drops to zero so in general。

 as the price gets higher， you're making more money， but you're selling less frequently。All right。

 so this is what I mean by quantntile。And if I ever use the notation。

 the quantile of a price P just mean1 minus f of。 so Q of P just says start from P。

 go up to this curve and go over to the left and see what the number is between 0 and1。

We want to be able to go backward too。So we also define given a quantile。

So given a number between0 and1， what's the corresponding price， Okay， so if we start on the left。

 then we move to the curve and then we drop down and we see what we get。

And so the formula for this is just the inverse of the CDF evaluated。At1 minus Q。Okay。

And notice that we can write the revenue。So we were writing it as P times 1 minus F of P。

 so the dollars per sale times the probability of a sale。Alternatively， notice this is just Q here。

你看。So it's also p times Q with P。Okay， good。Let me now So the next claim will explain what are the relevant statistics。

 So I need this stuff to have a vocabulary for the relevant statistics。

And so let me tell you what we wish we knew。 Okay， we don't know them because at the beginning。

 we know nothing。 Okay， so really， we wish you know capital F。

 But let me show you sort of a sweet spot， which are just a few statistics about capital F。

 which if we at least knew those， we'd be fine。 Okay And it involves these quantiles。

 That's what I told you about the quantiles。😊，Okay， so claim one。U。So to I Q n to be one over H。

 So capital H remember is our known upper bound on the valuations。 And now we just。

 we look at powers of one plus epsilon times one over H。So， Q1。I's just Q n times1 plus epsilon。

Q2 is just Q1 times 1 plus epsilon。And so on。Up to QS。Which is at one。Okay。

So power is one plus epsilon between one over h and1。

And so how many is this S is log to the base1 plus epsilon of H。

Which is basically your favorite base of log H over Epsilon。Okay。

So it' log H over epsilon different statistics。The quantiles。So here's the claim。

Which is if you basically the claim says if you knew the prices at all of these quantiles。

 you'd be done。Okay。So， the best。Of the P of QI's。So remember， P of Q just says， okay。

 if you tell me you're selling like with probability 10%。

 what price does that correspond to that sells with 10%？

So the best of the Ps and what do I mean by the best， I mean， maximizes expected revenue。

and remember in this terminology， it's p times  Q is the expected revenue， so the sale probability。

Times whatever price that's at。And the claim is this。Yields a one over one plus epsilon。

Approximation。Of us。看。So what I'm saying is。Even if you knew the distribution。

Here's like a very lossy， compressed version of it。

 which is still good enough for revenue maximization。 Okay， throughout capital F。

 except retain only the prices which make the selling probability equal to these log H over epsilon numbers。

 okay。So if age's like 10， it's just like 1%， and maybe it's 2%，3。5%，5%，7%。

 So just keep track of that set of prices。Then just do brute force search over how good each of those prices are。

 and the claim is one of them is almost as good as the best one as almost as good the mono monoly price。

O。All right， so this is pretty simple to prove， so let me prove this for you。

So just to be clear where we are， right， in our model， we don't know these， right。

 We don't know the P of Q I's because we know nothing。 right。

 But this is just sort of an intermediate step。 So the natural next thing to do is learn the P of Q Is。

Let me show you that if we had an exactly， we'd be done。All， it's a proof of claim one。All right。

So there's some monopoly price。Okay we wish we were using this。 Good， we don't know what it is。

So at P star be the monooppoly price。And Q star is whatever the sale price is， the monopoly price。

Okay。So， here's a little observation。I claim the Q star。

So the selling probability at the monopoly price。Can't be too small。It's got to be a least。

One over Cap reach。Take a little time to see why that's true。So we're using here that。

F has support in oneH。So here's the observation， what if we just set a price of one？

How much money would we make。1， because we'll always sell The valuations at least one。

 That's where the support is。 So we can definitely make a buck， right。

So suppose we tried to sell at a price that was so high that the selling probability was less than one over H。

What's the maximum amount of money we get from a sale？H， right。

 so our expected revenue is going to be less than one of age times H I less than one。

 And we know that can't be optimal。嗯。So bound evaluations means we can have this。

 it's a weak lower bound， but whatever。 Some you know。

 bounded away from0 lower bound on the selling probability。 right， That's why over in the claim。

 I didn't bother to state any quantile less than amount of rich because we know we don't need them kind of a priority right。

Okay， good。So。Let me show you now that one of these Q Is has to be good。 Okay。

 almost as good as a monopoly price。 And it's sort of like the obvious one， right。

 So you just kind of want to use， okay， maybe we don't have the Quan corresponding to maybe we don't have  Q star in our set。

 So we have a nearest neighbor to Q star in our set。 So let's just look at that。 specifically。

 let's look at one that's slightly below Q star。So the QL be the biggest。Q I。That is at most Q star。

And there's got to be one because Q star is at least one over each。So what do we know？

What can we say about QL versus Q star？All right so I guess by definition， QLs at most is big。

How much smaller could it be than Q star， what factor？Can't be that much smaller than Qstar。

One plus epsilon， right because we have all powers of one plus epsilon in there。And also。

What can we say about the relationship between the selling price at QL？

Versus the selling price a Q star， namely the Monoppoly price。住民か。No， I mean， the prices。

One of those is bigger than the other。Yeah， why is it the same relationship？

Because it's a different variable， one's a quantile， one's a price。If can a cure， We sent the price。

 too。So QL is a number between0 and1。So QL is something like 10%。

 and Q star is going to be something like 11%。So which of those corresponds to a higher price？QL。

 the lower selling probability means the higher price。 Okay， they're going in opposite directions。

 So to sell more often， you got to drop the price to raise the price。

 you got to drop the probability of sale。Okay。So this goes this way。Because QL is a most Q star。

So what does that mean， well， that just means that if we look at them the revenue that QL obtains。

And so what's the revenue？Corresponding to the price of QL， well it's just the sale probability。

 which is QL。Times the price that leads to as selling probability of QL。What do we know here。

 We know this is。One over one plus epsilon。Times Q star。Times the monopoly price。

This is also known as。It's three letters。Good。Yeah。

So I've just exhibited for you one of the prices in our set。

 which gets a1 minus epsilon approximation， obviously picking the best one can only be better。

So the best QI， only better。So that's the perfect claim one。Any questions about that？

So this says that this particular set of logage over epsilon numbers is sufficient to be off to the races。

 sufficient to get1 minus epsilon approximate revenue。Now。

 that's only going to be useful if we can quickly figure out what these are。

 or at least close estimates， but at least it sort of gives us a target to shoot for。Question。

All right。So the idea then， is just to learn the learn the。Idea。Learn。The P of QIs。Okay， ultimately。

 that's what we needed to do。Right， so we knew the。I mean。

 the QI's are not dependent on the distribution。 or the QI's are just the powers of onepsilom between one of H and 1。

 It's the P of Q is。 we didn't know。 We didn't know which particular price winds up giving you a target selling probability because we don't know capital F。

 But if we can learn these， we just pick the best and we know we're done。So let's learn them。 Now。

 of course， we're not going to learn them exactly。 we're getting these samples。

 So we're gonna have sort of like noisy estimates of these things at best。

 So let's first observe just to sort of， you know， to encourage ourselves。

 let's observe that this proof of this claim one is actually very robust to sort of various approximations。

 Okay， and that's going to start making us very optimistic。 We should be able to pull this off。😊。

Okay。So just some observations。So what did we really need for this proof to work？

 So there's two relaxations which we can accommodate pretty much effortlessly。So first of all。

 you know， it wasn't so important that we had exactly this set of QIs。 Okay。

 if we just have a rich enough set of QI's and then we pick the best one， everything's fine。

What did we really need for this proof， We just needed to make sure that， you know。

 whatever Q star was and Q star could be anything between 0 and1。 Well， not between0 and1。

 between1 over H and 1。 And no matter what it was， we had defined a Q value in our set that was less than a Q star。

 but a most of one plus epsilon factor less。 So any rich enough set with that property is good enough for the proof。

So， note。Sufficient to have any set of QIs。Such that for all T。

 So for all possible values that Q star might take on。There exists I。

 such that QI is between T over1 plus epsilon and T。Okay。again， whatever Q star is。

 we can find something just a tiny bit less than it。So that's all we need。

 So that's without change to the proof， agreed。Okay了。

So now here's something that's slightly more complicated， but barely。

So that gives us more flexibility for what these Qs are， which is nice。The other thing is。

 like we said， you know， we can't really expect to know these exactly with no error。 right。

 So suppose we only learned all of the P of Q is approximately。Okay。So。If。And actually。

 it's really the revenues。 Well， it's sort of the same thing。 So， but let me just state it this way。

 So if each revenue calculation。Onlyly。Accurate。Let me， let me phrase this differently。So ultimately。

 we're of estimates。So， if our estimates。嗯。Sorry。P hat of Q I。

All we know is that they're within one plus minus epsilon of what they should be。

So a picture will understand what's happening here？So。We're looking at two candidates。

Quantils in the corresponding prices。 Okay， so here we have。 So in the old days。

 when we knew exactly what the price corresponding to every sale probability was， What did we do。

 We just said out， Well， let's compare。The revenue we get from this price， okay？

So this is the selling probability。 This is the revenue per sale。 So this is the expected revenue。

 And then we have some other one。P of QJ， QJ。And whichever these was bigger。

 that's the one wed picked。 or whatever was the biggest of these was the one that we eventually picked。

 Okay that was in the version of claim1 where we knew these things exactly exactly correctly。

So if we have some error。If we only know the P's up to1 plus or minus epsilon。

Then these quantities can shift by one plus minus epsilon。

 So you can go up up to a one plus epsilon factor or down， it can get multipied down by one epsilon。

So what can happen is you can have some inversions。 Okay。

 so it could be in reality for the true price corresponding to this quantile and this quantile in this order。

But with our estimates， our P hat。 So our estimate P hat of the price corresponding to selling property at Q J。

 that might be too low by up to a minus。One minus epsilon factor where correspondingly。

 we might unfortunately overestimate。The price that would give us the selling probability of QI。

So that might get multiplied times one plus epsilon。Okay。

So some of our revenue estimates might shrink， but by hypothesis only by 1 epsilon。

 some of them might grow， only by one plus epsilon。 So we might make a mistake。

We might choose something whose real revenue for the real distribution capital F is actually lower than something else。

 But the worst possible areas by  one minus epsilon over1 plus epsilon。 Okay。

 if you get the simultaneous crossing of these two things。

So if our estimates of the P of the prices corresponding to the sale probabilities are within one plus epsilon。

Then the only thing that happens。 and this is in this final step here， actually。

 so we might make a bad choice when we pick the best one。The approximation factor。The grades。

By another。1 minus epsilon over one plus epsilon factor。Okay。And that's the picture。 Okay。

 that's the proof。So that leaves us with a sort of new version of claim1。

 where the approximation factor instead of1 minus epsilon is now one minus epsilon squared over one plus epsilon。

 But if we just reset epsilon to be epsilon over4， it's fine。 Okay。

 that whole thing is bounded above by one plus epsilon。 So it's no big deal。

So again all of this was to say that we had claim one。

 that was sort of a daydream where we had exact computations of the price corresponding selling probabilities。

 Now we realize all we need to do is get estimates of them。Surely that seems possible， and it is。

Okay， so any questions about that？So now I want to tell you what is the algorithm which actually satisfies the hypotheses of this relaxed version acclaim one。

Yeah。Okay。All right， so algorithm， it's very simple。So you get your samples。Do you want up to VM。Now。

 we don't know what any of these cues are。Okay， we know the value of these things， right。

 We know that the person was willing to pay 20 bucks。

 We just have no idea if we set a price of 20 bucks。

 what would be percentage of the time we got a sale。 Okay， we have no idea。

 So we do the obvious thing。 we estimate using our samples right So if we think about a price of 20 bucks and exactly。

 you know，7 out of 20 of the things are at least 20 bucks。

 we imagine as if 35% of the time in reality， we'll get a sale。

So it's the obvious empirical estimate。So we said。Qe hat of VI。To be equal。

So the number of the samples。With VJ， at least V。Over M。The number of samples。我这。

So these are all multiples of one over M， all of these empirical quantile estimates。

 all these Q hats。 They are multiples of one over M。For the minimum sample， this is going to be one。

 for the maximum sample。 This is going to be one over M， for example。Yeah。Okay。And。

Then what our algorithm does is it simply returns。So it's given the samples。

 it's responsible for reporting a price。 So it just is going to say use a price， the sample。

 which maximizes the expected revenue I think you would get and the expected revenue I think you would get is just with respect to these selling probabilities。

 the Q hats。So return。V I。It maximizes。VI times。Q hats of VI。OK。So the value of that sample。

 the value of VI times the fraction of the samples that are at least V or above。

So one possibility is you set it to equal to the maximum of all the VIs。

 but then it gets scaled by1 over M。 You can set it to the minimum of the VIs。

But then you'd only make that much per sale， or probably you want to set it somewhere in the middle。

So that's the whole algorithm。Okay。Any questions about the algorithm？

So the output is kind of the first one you think of， Yes。

 basically said just assume that your input you know exactly represent distribution， yep。

 exactly right。Which is nice， I think。Yeah， so it's really。 so it's true。

 The challenge is more in the analysis， showing that the obvious thing works。 It's not so much。

You know， some kind of unusual creativity with how to do it， so I agree with that。Okay。

So to justify this。We need a claim two， but claim two basically just says turn off bound and do what you want in this case。

But let me spell it out for you。I'm going to spell the statement。 I'm not going to spell the proof。

You will spell out the proof。So Cla two。And here is where we'll see the sample complexity。

So suppose M ends the number of samples。Is at least c times H over epsilon squared。

Lgue H over perhaps s and square。And so as usual in these kind of statements here。

 C is a sufficiently large constant。Though it really doesn't have to be very big。

 something like four。Okay。H， capital H， remember that the upper bound on the valuations， Epsilon。

 this is shooting for a one minus epsilon approximation。Souppose we have this many samples， at least。

Then with high probability over the samples。The following are true。

 so I'm going to write down two statements， which basically are the hypotheses of the relaxed version of claim1。

 which means we're done so the point of claim two says that that algorithm works。

 but I have to sort of glue it with our sufficient condition for working， which was our claim one。

Okay。So what were the hypotheses in claim one or what are the relaxations？

The first thing we better have is we need to have a rich enough set of quantiles， okay。

So that's one thing we needed for the proof of claim one to go through。

So the first statement is just that。So for all tea。Between one over h and1， indeed。

There exists a sample I。It quantile。 And notice， these are the cues。 These are not the Q hats。 Okay。

 because claim1 was all about the cues。 right， So you needed basically good coverage of the real quantiles of the distribution。

 So again， we don't know what these are。 But the analysis just says that we have them。

So theres this I， such the Q of V lies in the target range。T over1 plus epsilon。Okay。

So with this many samples， we have a rich set of quantiles available。Again。

 we don't know which VI we can't compute Q of VI， but having sampled all these things。

 we know we have a very rich set of them anyways， which is all we needed for the performance guarantee。

Okay， second thing。For all of the relevant samples。So for every VI who's corresponding。Yeah， no。

 this is right。Okay， so for all of the samples that aren't absurdly big。

So whose selling probabilities aren't too small。 indeed， we get a good approximation of the Q hats。

So Q had a VI。Is in one plus epsilon times。Q of V I。And of course， given that at a given price。

 you have a very good estimate of the sale probability。

 that also means you have a very good estimate of the expected revenue at that price of EI。So， in。

We think。The price VI would generate。Revenue VI times our estimate of the probability of sale。

 which is our Q hats and because our Q hats are almost correct。This is in the real revenue。

One plus minus epsil。And this was。Its actually for me。Let me actually do this。So really。

 in claim one。What we needed was that our revenue estimates， were basically accurate。 So sorry。

 there's sort of a typo here。So the figure is correct。But I forgot the cues in this statement。ち。

So there's a hat here。So this figure was what said。

 as long as we get one plus epsilon estimate of other revenue estimates。

 we only lose this small factor on the approximation with respect to claim1。

 and the second statement of claim two is saying yes， indeed。

 we do get that the desired accuracy on the revenue estimates of each of the potential selling prices we might use。

Okay。So is the statement of the claim clear？I'm not entirely clear why in the first part。

 we're interested in the true Hes， as opposed to the House。 This is what Cla one needs。

So when we thought about claim one。So claim one basically said。

 here's some sufficient statistics to guarantee that one of the available prices will actually work。

I mean， there's various ways to do this。 This just turns out to be， as far as I can tell。

 the cleanest way to do the derivation。I mean， so yeah I could have a version so I could reprove claim1 with Q hats instead。

So instead， so when we took claim1 and we relaxed it to estimates。The way I set it up。

 the only thing that's estimated in claim one is the revenues。

And so you can see that very clearly here。AndBut the point is just this is true also。

It would sort of makes sense right so you take all of these samples。

 you expect them to be sort of uniformly distributed throughout the quantile space。

 you know and we have you know way more than just kind of we have much more than HO Epsilon so HO Epsilon is kind of what you'd need to expect one in every kind of epsilon and the quantile space so we have a lot more than that so you'd sort of sort of expect that。

You should have plenty to sort of get the coverage。 the claim one demanded。So so again。

 there'd be a version with the Q hats， but， you know， claim one was easiest to prove with the cues。

 And it's actually very easy to establish this statement as well。

 So just from the assumptions we made about。That is bounded。 Yeah， right。

 And you can see the support bound is showing up in the sample complexity， yeah。So I mean。

 there's sort of two things one is kind of like morally why should this all work and the explanation for that's pretty simple。

 which is just claim one tells you you only need sort of log H over epsilon statistics。

 it doesn't seem like it should be that hard to learn a good estimate of any one of those statistics。

 you'd sort of expect claim one that would still be true if you had really good estimates。

And so then you should be done。 And all that intuition is correct。 But the same time。

 I wanted to give you some version， which was actually mathematically， you know， fully correct。

 As I said， I'm not going， you know， I'm not going to bore you with like turn up down de variationvations。

 that kind of thing， but。At least the statements or everything I put in the board really doesn't apply what we want。

So any other questions about that？So the proof fear， there's no surprises in the proof。

So I'll put this on homework five。So this is just a turn off balance。Okay。

And they're both pretty easy， one is especially straightforward， and two is pretty straightforward。

And so that's why the learning algorithm works。It's a corollary。

Our algorithm gets a1 minus epsilon approximation。With this sample complexity。

So the sample complexity depends roughly linear on the bound H on the support and quadraically on the。

Reciprocal of their tolerance，Now you should ask， maybe like Raphael said。

 it's kind of the obvious thing and so you'd be natural to wonder maybe a less obvious thing could somehow do better。

 not so much better than one minus epsilon， but better in terms of how much data is necessary to get to one minus epsilon。

 it turns out the answer is no。So it's known that actually this is tight。

 not just for this algorithm， but for any algorithm up to this log factor。

 so no matter how smart you are with the data， you can really need H over epsilon squared samples to get to a1 minus epsilon approximation。

So its。That's an information sort of the slickest way I know how to do it is an information theoreticalore argument。

 So basically， you take two distributions。And you show that if you。Cannot distinguish between them。

 So basically， your promise is distribution D1 is distribution D2。

 I promise you that the M samples will be either all from D1 or they'll all be from D2。

And I'll make them far enough apart so that you really have no choice but to distinguish between which of those two cases it is in order to get one minus epsilon approximation of revenue。

And then you keep track of the distance between the two distributions。

 or rather the samples generated by the two distributions using the notion of statistical distance。

 which we talked about。When when did we talk about that？Four weeks ago or so。h Oh good， good， good。

 Yeah。 So with the hashing。 we had a notion of proximal uniform。

 So there we wanted upper bounds of the statistical distance saying things were almost the same here in the proof。

 you're gonna to have lower bounds in the statistical distance， basically saying that you know。

 until the number of samples becomes really large， the statistical distance is large。 And therefore。

 sorry， it takes a lot of samples before you can get the statistical distance to be sufficiently large so that you have a chance of differentiating which ones the sample comes from。

So that's how you do it。各。All right， so any other questions？About this stuff。All right。

Then let me switch gears a little bit。And instead of asking this question。

 remember I said there are two intertwined goals， one is how do you use samples in a smart way。

 So we now know this is a smart way to use it if you have sufficiently many samples。

 the other was the sample complexity to get one minus epsilon。

 so now I want to look I just want to switch the regime where you have very little data。Okay。

 where you know almost nothing about the distribution。

So getting a one minus epsilon approximation is not really realistic。

But you still want to use your limited data in the best way possible。

 and you want to know what kind of approximation factor can you get。

And so the other thing I want to tell you about today is a kind of surprising fact。

Which is that even if m equals1。You can get a nontri approximation factor。

So this really drives home the point that you can start getting good approximation guarantees for these kinds of problems without learning almost anything about the distribution。

Okay。So positive results。1 now equals one， So I'll give you one sample and you have to pick a price。

I think that。It's pretty much all you could do， right， Yeah。

 So that that's actually what we're going to prove it for。

 You just regurgitate the sample as the price。All right， so the proof is actually， you know。

 I can give you a proof by picture， but I have to explain what the picture means for a little bit。

 Ca let me tell you what the picture is going to be。So he need to tell you about revenue curves。

And so again， we're going to be using these quantile notions。So。

Before the quantile was on the Y axis， now I'm going to put it on the X axis。So remember。

 this is the probability of a sale。 Okay， so low Q means a high selling price。

High Q means you're selling at a low price。And then。So what's the Y axis。

 The Y axis is just going to be。The revenue you get when you set a price that sells is probably acute。

Okay， so I'm going to call that R of cube。So that's just defined as the probability of a sale。

Times the money you make on a sale。 Okay， And again， remember。This thing is just equal to。

F minus-1 of1 over cube。 So it's just the price， which would net you a probabilityative sale of exactly cube。

So for example。For the uniform distribution。Well， so then capital F is the identity function。

So F inverse is also the identity function。Okay， so Q times P of Q。

 it just becomes Q times 1 minus Q。So in other words， it's like exactly the curve I just drew there。

Okay。So that's what the revenue curve looks like for the uniform distribution。

So if it's the exponential distribution。Well， so now F has an exponential。

 You might expect X F inverse to have a log。 So let me spare you the calculation and just tell you the answer。

 So here。R of Q is going to be equal to Q。Times the natural log of one over。Okay。

But we see something we saw before， right， so you might recall that when we saw it for the monopoly price。

 the exponential distribution， the monopoly price was one。

 the selling probability at that monopoly price was one over E。

So the best price corresponded to Q being1 over e。And when Q is1 over E， this is also1 over E。Okay。

 so it's one of three times one。So the highest， the revenue at that cell price of 1ner3 is also 1 of3。

 which we knew。So， graphically。What the revenue curve looks like for the exponential distribution。

 it's not symmetric。Around one half anymore。It's a little bit kind of。

Lopsided with more mass to the left。Okay。It's not quite that flat but。And so the height， right。

 so the biggest revenue。We know occurs when Q is 1 over e。

 and we also know that the revenue at that point。Is one over8。Whereas for the uniform distribution。

 we know the best Q is one half， and we know that the revenue at that point is a quarter。Okay。

So those are two revenue curves with two distributions。One thing you'll notice about both。

These are both concave functions。Okay。So that's going to be the second distributional assumption we're going to make today。

So we're going to replace the bound evaluation assumption with an orthogonal assumption。

So now the distribution can have an unbounded。Support。

 like the exponential distribution is totally fine。

But we're going to assume that the revenue curve is concave。

That is not true for every distribution in the world。

 but it's true for the majority of the distributions you'd find in the back of an intro to Sta textbook so it covers a lot of cases。

Zxiong。And again， remember， we need some kind of distributional assumption to prove anything。 Okay。

 so this is going to be the assumption for this result。So F is such that R。It is concave。

Sometimes these are called regular distributions， although you want need to know that。

 although maybe the takeaway lesson for that is whenever you prove a theorem you really like。

 but it doesn't cover all cases and you need to make some assumptions。

 call the objects that satisfy your assumptions regular。It's a very nice idea， right？

I guess you could also just call the ones that don't satisfy the assumptions pathological or something like that。

You get the idea。Okay。Good。Right。So here's the key claim。

So let me state this and then I'll explain why it implies what we want。

So this is kind of an amazing claim。It says。It it's going to sound very weird。

 but it's also going to sound interesting， I hope。So suppose like you you know。

 youd love to use the monopoly price。 You know， that's the optimal thing。

 Suppose instead of using an optimal price， you do something very strange。

 You pick a random sample from the distribution F。And you use that。As a price instead。 Now。

 we've already talked about the case， you know， with the motivation of having M equal1。

 this kind of seems like the first thing to try。 right， Just regurgitate the sample as the price。

 So we're just trying to say， how well does that do。

So using a random sample as a price rather than using a monopoly price。

And the key claim is that that gets a factor one half approximation。So， formally。

Draw a price randomly from the distribution capital F。 So remember what F is。

 So F is where the bidders valuation is being drawn from。 right。

 But now we're sort of using it to sort of make up a price。And so， if we look at the。

Expected revenue that we're going to make where the expectation here is with respect to the random price。

 and then also with respect to this sort of bidder who shows up with some random valuation V。

This is at least one half。Times P star1 minus F。Of P star。So an immediate corollary。And this is for。

 so this is for regular distribution， I should say。So this is under this assumption。So corollary。

We can get a one half approximation。Even when m equals 1。Okay。So just reuse the sample as the price。

It's an immediate corollary。Ages nope， I've dropped that assumption。

So I've dropped to the bound valuation assumption。 I've replaced it with a concave revenue curve assumption。

 and those are orthogonal。 Those are incomparable assumptions。So in particular。

 this holds for the exponential distribution。Or like a log Gaussian distribution， say。All right。

 so is this statement clear for approval， and it's clear why we care about this。

 why this is what we want？O。All right， well then let me tell you the proof。

And the proof is by picture。不。All right， so let's look at these revenue curves。So。

Look at the monooppoly price。ButSo we're looking at a point which in the x axis。The value is Q star。

 So the cell probabilityba。 so I'm looking at the very tippy top of the revenue curve。 Okay。

 so the highest amount of revenue you make， okay。So the X axis， that's the quantile。 So's Q star。

 the selling probability at the monopoly price。 And then the y axis is the revenue at Q star。Okay。

So what can you tell me about the area？Of this rectangle。Okay。

 that goes through the very top of the revenue curve。So what's the width？Yeah， what's the height？

The人。The height is R of Q star， right， So the expected revenue you make。

When you use the monopoly price， also known as a three letter word。Opt， right？

So the area of the rectangle is opt。Okay。All right。So now here's the one part， which is。

Which is kind of neat or tricky， depending on how you want to think about it。

So let's look at this expression on the left hand side。Okay。Let's do a change of variable。Okay。So。So。

 P。Let's think of P not just as a price， but let's think of it as the inverse image of some target selling price。

So here's another way to think about it。 Right So what are we doing here， We're drawing P。

 according to capital F。Here's another way to draw P from F。 I first draw Q uniformly， from 0，1。

That's a sale probability。Then I take1 minus Q。Okay， that's now a failure probability。

 or probably that evaluate it most some P， but it's also drawn uniformly from 01。Okay。

Now I take F inverse。Right， so I mapped this number between 0 and 1 to some number on the real line。

 according to F inverse。That's a random sample for F。Okay。

So another way to think about it is suppose， you， I want to randomly sample the height of a human being。

Obviously， I don't want to pick a random number between four feet and  eight feet， right。It's a very。

 it's a very non uniform distribution。 right， So if I was directly， you know。

 picking on the number numeric scale， it would be a complicated distribution。 On the other hand。

 I could just pick a random person in the world。And look at their height。

That's going to be a randomly sampled height value from the height distribution。

 So that's all I'm doing here。 Okay， so rather than sampling V from F， I sample Q from uniform 01。

 I look at 1 minus Q。 That's again， the uniform 0，1。 And then I apply F inverse。

That gives me a sample of P， according to capital F。哎。So that change the variable。

Where I instead sample Q。Right mean， least if this is confusing。

 I hope you at least recognize the look。 There's a bijection between the P's and the Q's。

 There's some distribution on the P's。 So surely， there's some corresponding distribution on the Q's。

 So maybe what's a little mysterious is why is it uniform。 Okay， but they're quantiles。

 So it's really by definition that they're uniform。 So the， you know， Q equal 。5。

 That's exactly where half the distribution is below it and so on。 Okay。

 So quantiles are just by definition， uniform and 01。Okay， so instead we pick Q uniformly from01。

But then we just look at the exact same expression。 Okay， so before we were picking P uniform from F。

 we were looking at the revenue。 Now we pick Q uniform from 0，1。

 and we look at the corresponding revenue。So Q times p of Q。Okay。

 so these are just different ways to write revenue。So that's exactly the same number。

 the left hand side is exactly that number。Okay。Let me actually rewrite this still further。

 This is just the revenue expected at the price with selling probabilitybil Q。

So let me actually write this as RFQ。So what does that correspond to pictorially？

So expectations are just integrals， right， And the uniform distribution is just sort of la big measure。

 you know， or your standard remon integral。So by taking the expectation over Q from 0 to1 of R of Q。

 all I'm doing is calculating the area under the revenue curve。Okay。你思。So the quantity we care about。

 the expected revenue of a random reserve price drawn from F is the same thing as the pink area。

 the area under the curve。So the third geometric shape I want you to think about。

 the third and final one。Is。A triangle。And it's a triangle。Then as endpoint00。1，0。

And the top of the curve， so Q star R of Q star。In these two cases， the blue triangle is a subset。

Over the pink curve。That's true whenever this curve is concavefe for a concave curve。

 all the chds lie below the graph。So， back incvity。Area under the curve。

Is lower bounded by the area of the triangle。Now， the triangle has exactly the same width and the same height as the rectangle。

 but it's a triangle。 So it has exactly half the area。And so we're done。That's why。

This is at least half of the optimal revenue。 The optimal revenue was exactly the rectangle。

This should be half here。Sorry， thank you。A， the triangle is exactly half the area， the rectangle。

And the rectangle was the operating revenue。Any questions about that？

I'm wondering how this general lies too when。三号。Yeah， it is a good question。's you know。

 when you have two samples， it's not even clear how to set the price。No， it's not。Just up my。

What does that mean pick the price so I one way to interpret this result with one sample is just you know assume that the one sample is your entire distribution right and I think of this algorithm is the same as the other algorithm that's right so two or whatever you can just assume that that's your entire。

That's an algorithm。 It's not clear how well it works。

It's not known how to prove of bound better than 0。5 for any of those acronyms。

So I say it can't be done。But it's not， it's not clear。 And it's just。

 it's not also just clear that it's the optimal thing to do。

If you really want to sort of get the best possible constant， maybe it is， but that seems。

That seems hard to develop intuition about that。Even with two samples。

 we don't really know the best way to use them。It's a good， good question， so。Any other questions。

WellThis seems like a good place to leave you before the holiday， so have a great break。

 and I'll see you a week from Monday。