# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p20 -20-(Lecture 19_ Interim Rules and Border’s Theorem).zh_en -BV1fNVNzhEBg_p20-

All right， well， I'm going go ahead and get started。So last lecture。

 the topic is revenue maximization in multiparameter settings， so let me just remind you。

 we had these four parts of the course where we were just obsessed with welfare maximization maximizing some of the VIs at the very end I'm talking about maximizing some of the PIs。

 maximizing some of the payments to the seller， so if you like you know we're thinking about the things from the perspective of some monopolists that wants to maxim their own revenue。

Another thing I want to remind you is in the single parameter case。

 So this is where there's only one type of stuff and players values are just linear in the amount of stuff they get。

 That was last quarter， very well developed theory。 That was Myerson's theory。

Which gave us basically a very crisp understanding of optimal auctions。

 It's just maximized virtual welfare。 And so the hope and what I want to talk about today is the extent to which we can get a multiparameter analog of Myerson's theory。

 this idea that revenue maximization reduces to virtual welfare maximization and amazingly。

 there's been progress significant progress on this issue just in the last few years。

 even though Myerson's paper is from 1981。 so that's pretty cool。Right。

 so and then just why is why is it interesting， is this theorem that you know the single parameter world that revenue maximization reduces to virtual welfare maximization。

 There's both the sort of conceptual slash structural。

 we have a good handle on what an optimal auction looks like， we know， for example。

 that even if you optimize a verbaesian instead set of compatible mechanisms。

 you get a dominant strategy and compatible optimal solution， you know。

 you get deterministic mechanisms as long as the distributions are regular。

 And then there's also the computational interpretation。

 which is well as long as it's a problem domain where you can maximize welfare。

 this automatically means you can maximize revenue too because you just feed in the virtual values into your black box to maximize welfare and boom you're done。

 You've got a revenue。 a computationally tractable revenue maximizing auction。

 So those those are the analogs， we're gonna be striving for today。 for multiparameter problems。Now。

 the main point of last lecture was to show you know that that's a pretty ambitious goal。 Okay。

 so we started with just these examples。 We just had one buyer。 We had two items。

 The buyer had an additive valuation over the two items and its values for each region I from these super simple distributions。

 and already in that very simple case。 the optimal a could be really weird。

 and we showed that it varies a lot with exactly what the prior is。 and we showed that， in fact。

 you may need randomization to be an optimal revenue maximizing auction case it was no longer true that deterministic suffices to be optimal you need randomization。

 So that's an important lesson that we learned。 So we know things are going to look more complicated in the multiparameter world。

 but still， you know。Even knowing that， we want to get as close as possible to sort of the holy Grail of Myerson's single parameter theory。

So that's the that's the context。 Let me just remind you， the formal setup。

So we're now not talking about just one buyer， we're talking about multiple buyers。

 we're talking about auction or mechanism design setting。So we have items， M of them。

And we're going to stick with additive evaluations for now next lecture we'll talk about unit demand as an example of how to push the theory further。

 but as we saw last lecture additive evaluations already pose a number of complexity。

And we're working in the finite support case。Okay， so capital Vi subbi denotes the potential additive valuations that bitter eye might have。

And it has some density little F， and again， these are additive。

So a bitter value for a bundle S is just。The sum of its values for the individual items。

 J in that bundle S， okay。So there are these V Js drawn from this prior。 So just to be clear。

 I will be assuming throughout today that we have independence across bidders。 Okay。

 so the F is need not be identical， certainly， but bitter one and bit 2。

 I'm gonna assume that their evaluations are independent。 Some of the stuff I'll say。

 extend the correlated distributions。 But I won I won't make a big deal of it。

 nowhere will we need that for a given bitter I， its value for different items is independent。 Okay。

 so for a fixed bitter eye， it can have an arbitrary correlated distribution over its values for the different items。

 J。 but independence between the bidders。Okay。So what we were talking about in the last lecture was。

Right so it was clear with all these examples we were looking at that we probably it didn't seem like some nice closed form formula was going to be sufficient to talk about revenue maximization like it was in a single parameter setting。

 there's just too much complexity going on so we needed some more sort of general tool for getting a handle on it。

 so we were looking at linear programming formulations。And so we made the observation。

 although it wasn't really clear if it's useful or not yet。

That the revenue maximizing auction for this kind of setup can be expressed as a linear program。

 a really big linear program， but a linear program。So the decision variables。

 so we have the revelation principle so we can think about just direct revelation mechanisms and so the decision variables of this linear program are going to correspond to the allocation rule and the payment rule of that mechanism。

 so x's and P's。So how would you write this， So revenue， well， you just， so we want expected revenue。

 So we just average over the possible valuation profiles。

And then we just look at how much money we make on a given valuation profile。Okay， so to be clear。

F is given。 This is just the given prior distribution。 Okay。

 so these are just numbers that are part of the input。 This is a decision variable。 Okay。

 so this is the payment rule of our auction。 And this is why we want to maximize the expected revenue。

Now， subject to what， well and this is， this is going to be important to kind of remember this。

 There's three types of constraints in mechanism design。 there's incentive compatibility constraints。

 There's individual rationalotic constraints， and then there's feasibility constraints on the allocation。

So the IC constraints。And so remember， once you have more than one buyer。

 there's a difference between dominant strategy or Bayesian incentive compatibility。

 depending on whether it's a pointwise requirement or an average requirement。

 we're looking at the Bayesian incentive compatibility version， so the average version。

So here we just quantify over all bidder's I， all possible two true types。

 VI and all possible reported types VI prime。And again， this is just on average。

We sum we average over all the types that the other bidders might have。

According to the relevant density。And then on the left hand that we say， when we report truthfully。

 what's our utility？So we just do it good by good， so again。

 remember it's added evaluations so I can just。Okay， and so X I J， so this is the probability。 sorry。

 that should be X I J V bar。So the x's are our other decision variables corresponding to our allocation rule。

 this is the probability that bid I gets item J when the reported evaluation profile is v bar。

And then there's the payments。Okay， so this is just the utility of bitter I total when the full reported value reported profile is V bar。

 And then this is averaging over what V minus I might be。 Okay。

 and that's how bitter I's thinking about。 Well， I know I'm V I， Who knows that other people are。

 I just average over V minus I okay。And so this would be at least the same thing， yada yada。

 yada yada， and then in here， of course we still have the VIJs， those are the true values。

 but then these things change to the reports。Okay。So those are the BIC constraints。

And then we have the individual rationality constraints。

 which in this context are usually called interim individual rationality。

 And so this just says direct revelation always gives you non negative utility， again。

 only on average。 So this would just be the left hand side above。

So this is the expected utility if you report truthfully when you're V。

So the left hand side above should be non negative。For all bidders。

 whatever their actual value might be。And。But we're not done。So why do we need more？

What other constraints do we need。It's one other set。Right。So like， which， which means。哦明。

One bigger gets。But， so， we have these items。 you know， there's only however many there are。

 And each one only go to one person。 right， So they're simple， but we can't forget about them。Okay。

 so feasibility。So in every evaluation profile。For every item， it should be the case。

That if we sum over everybody。That's the most one。Okay。

Sore to remember the semantics here are Xi J of V bar。

 that's the probability that I gets J on the input V so the sum of everybody's probability should be at most one。

Rightright。So a couple of things to remember， a special case would be a deterministic mechanism。

 that's when the x's are always either zero or1， but as we know we need to allow randomizations。

 we're going to allow x's between0 and1。You know， if if you had a mechanism which was selling item separately。

 that would just say， you know X only looks at the j components of this right So remember what V is So V。

 first of all， it's a vector of n valuation profiles， one for each bidder。

 And then for each bitter eye， It's V is an M vector。 itss value for each of the M goods。

 Okay so this is really n times M numbers。 It's being fed in here。 And so one thing we saw is simple。

 but not always optimal is' just selling good separately， that would just say， you know。

 I'm not even going to look at the items other than j when I figure out how to allocate j。

 But as we've seen in general， if you want to be optimal， maximize revenue。

 you can't just sell the separate item separately。 you might want to bundle。

 you might want to do other things。 So it's important that when you decide how to allocate an item J。

 you actually look at everybody's values for all of the items so this is the general。

 This is the general formalism。Oh I guess there should be non negativity constraints。So。

That's the L I left you with the very end of the last lecture。 Let's notice it is， in fact。

 a linear program。 Okay so again， remember the Fs are given， that's the prior。 the V's are given。

 Okay， those are just people's potential valuations and the X is in the P's are the decision variables and everything is linear objective in all of the constraints okay。

Also， there's certainly a correspondence between feasible solutions to this and mechanisms that we're talking about you know a mechanism induces a feasible solution just with the intended semantics of the X's and P's Similarlyly if you look at a feasible solution to this linear program。

 it basically tells you what to do on every input so if you solve this。

 you get some X's you get some P's and evaluation profile V comes in you just do like basically table lookup into the decision variables you say。

 hey is what do the LP solve to for X Ij on this valuation profile Oh it's0。1。

 I guess I'll just give item J to bitter I with 10% probability okay？

If you want now you can ask okay， how do you you know how do you assign all of the items。

 it actually doesn't matter if you think about it， so from a player's perspective because their valuations are additive and because their risk neutral all I care about are the individual marginal probabilities。

 the XJs so for example you could just allocate each item J independently that' would be one way to do it go to item1。

 look at the X ones。Alloccate randomly， according to the X I1s， repeatat the process with item 2。

 repeat the process with item 3 and so on。 And that would be a mechanism that would implement the intended semantics of a linear programming solution。

And there's a correspondence， you know， between the revenue of a mechanism and the objective function value here。

 Okay， so if you， if in principle， if you solve this linear program， you know。

 it would really print out for you instructions that would be a revenue opt a revenue maximizing B。

 I C， I I R mechanism。So that's kind of a straightforward approach。Okay。

So there are some issues with this linear program。So you'd be right to ask the question， you。

 what have we accomplished？And let me remind you， you know why when I said when I said what we're striving for is Myerserson's theory。

 I tried to explain why why we're so satisfied with Myerserson's theory。 And there's two reasons。

 The first is sort of conceptual slash structural。 It gives us a handle on what optimal mechanisms look like。

 virtualr welfare maximizers That's really nice。 The second is computational。

 It reduces revenue maximization to welfare maximization。

 And this does neither of those really is not obviously， right， I mean， this linear program， I mean。

 so first of all， if all you tell me is that you know。

 something is a solution to some massive linear program。

 It's not clear I've learned that much about it。 It's not's not not a big takeaway there。

Nothing like， you know， understanding as a virtual welfare maximizer。 Secondly。

 this is too big to be computationally useful。 Okay， so notice that the number of evaluation。

 both the number of variables。are indexed by the number of valuation profiles and so are the number of constraints indexed by the number of valuation profiles and that's a lot so that's exponential in the number of players in okay。

So it's not clear what we've done。 although nevertheless。

 this is kind of the right starting point for more interesting results that I'm going tell you about today。

 okay。So what I want to do next is。And this mean we're gonna the exercise we're gonna to do next is kind of probably the most important takeaway for today is we're going to try to basically have an equivalent linear program with much fewer variables。

 Okay， so the number of variables we're going to want to be only growing linearly with the number of players not exponentially with the number of players。

 Okay now it turns out， hopefully seems like a regional good go on its own right。

 But it also turns out that studying this problem of how to do this dimension reduction for this linear program will lead us to the structural insight that we wanted in the first place。

 Okay， so we will get to the conceptual path as well。 but for now。

 let's just focus on is there some way we could write down an equivalent version of this linear program with much fewer variables。

So that's the next thing we're going to do。All right。

Let me remind you of something that we just talked about very briefly Okay so I don't really expect you to remember it。

 but it's the notion of interim allocation and payment rules。

 The time we talked about this briefly is when we I was first talking about Bayesian andcompatible mechanisms。

 We were about to talk about those black box reductions from approximation algorithms to mechanisms。

 And I did a special case in the single parameter setting。

 I talked about the extended Myerson's lemma and when we talked about the extended Myerson's Lemo。

 we were talking about the monotonicity of these things called interim allocation rules。

 So here's what they are。 Let me remind you。So。Consider a direct mechanism。X， P。Okay。

 so the allocation rule and the payment rule both take as inputs a full valuation profile。 Okay。

 so in this case， a full n times M numbers， M numbers from each of the N bidders。Now。

Any mechanism like this induces an interim。Alllocation rule。Okay。And an interim allocation rule。

Takes as input only one bidders data， so only M numbers， not n times M numbers。And。

With the missing numbers， with the missing valuations， it just averages over the other n -1 bidders。

So YI of VI is just the expected allocation that I gets when it reports VI with the expectation over the unknown V minus I。

So let me just also write this out and sort of the notation over here。So， some。Over V minus I。

Times the probability of v minus I。Or X， I， V I V minus I。So in general， right， so the output here。

 this is actually， let me just go ahead and sub this by J。Okay。

So let's just talk about them separately for each item J。Okay， so for example。

 even if you started with a deterministic mechanism。With no randomness， so x being always zero or1。

Now there is going to be randomness supplied by the unknown valuations of the other bidders okay so even it's a mechanism where you always either win or lose。

 you might still reason about this mechanism by saying， okay， well if I bid $10。

 what's my chance of winning or the chance of sort of the randomization of what other people are bidding or what other people want？

So this would be the probability of winning in the case of a 01。Al right。And again。

 I want to point out it takes much fewer arguments， just that of one bidder， not of all n bidders。

So similarly， although these will be much less important for us today are the inim payment rules。

Definineed in the analogous way。Where you just average over the。Payments of the actual payment rule。

Or you're averaging over the unknown v minus I。Okay。So any questions about that， Okay。

 so especially this one， Okay so。This is going to be just this entire lecture on a technical level is about understanding this mapping between the x's and the Y's。

So the x's are what we're totally used to， I'll sometimes call these X post。Allocation rules。

Expost in the sense that it's a function of the full valuation profile。 Okay。

 so it's privy to all of the information of all of the bidders。And these are x inim。

 where in some sense you only know V and you're averaging over v minus I。So keep this in mind。

I'll try to be consistent with the notation where x is always the x post rule and y is always the x interim rule。

Okay。And so just a little， a little more verbiage。So we're going to call。Y Q， the reduced form。

Reduced form of X P。Okay。So， evidently。A mechanism， X P induces a unique Y in Q。

 They're uniquely defined。 Okay So oops， yeah， so Y Q is the reduced form。Why reduced， Well。

 if you think about them as variables， notice there are many fewer sort of variables of the form Y I J VI。

 okay or Q I VI， but especially here。So remember x， it takes as an argument evaluation profile。

 so in some sense， the amount of data in x is proportion of the number of valuation profiles exponential in n。

This is indexed only by the choice of the bidder， I， so n choices， M choices for J。

 and then the number of possible valuations for that bidder。Okay， so this， the number of。

 the amount of data of this form is scaling polynomially in the number of bidders in the number of items and the number of possible valuations。

 But the point is， this is not blowing up as the product of the number of different valuations of people。

 Okay it's not indexed by the valuation profiles。 So that's the sense in which it's reduced。

 There's much fewer of these than of these。Okay。The other thing you might expect， I mean。

 because in some sense we're compressing the information， going from XP to YQ。

 you might have multiple different mechanisms， X1， P1 and X2， P2 map to the same reduced form， okay。

 that's possible。All right。Now， why did we do this， So why did I introduce this？ So remember。

 our goal was， can we have a smaller linear program？ And so the question is。

 if we have a smaller linear program， what are the decision variables going to be。

And so the point is， instead of the X post allocation and payment rules。

 we're going to use the X interim allocation and payment rules。

 and as we just argued that's going to be a much fewer number of variables。 The reason this works。

 and this is sort of the big insight is that almost not everything。

 but almost everything we care about in this linear program can be expressed purely in the vocabulary of the X interim rules。

 we don't actually need these sort of full blown dependence on the valuation profile to talk about what we care about in particular。

 to talk about revenue that can be expressed in terms of the X interim rules。

 the incentive compatibility and the individual rationality constraints can also be expressed purely in terms of the interim rules we don't need all the other information Feasibility is another question and that I'll get to in a second。

Okay， so key points。Intraim allocation rules and interim payment rules。Sufficient to express。

Expected revenue。And BIC and the IR constraints。Okay， namely。So what do we do for the revenue？

So bi linear of expectation， we can just look at each bidder separately。

 we look at every type that bitter eye might have， we look at the probability that it's going to have that particular evaluation。

 and then we just look at the interim payment rule so we look at how much we expect to collect from bitter eye when it has the type VI。

So that's an expression of the revenue。 Now。 Not none of this is indexed by evaluation profile。 Okay。

 that's the key point。 It's only indexed by the report of a particular player of V。 I。

 That's the big win。 So here we have the arrows。Which means this is a sum over zillions and zillions of things。

Here we have a sum just over the sum of the supports of everybody's type distributions。

 So think of it as if like each player has 100 or 1000 different types they might have Okay。

 so think of the card now as the VIs as 100 or 1000。Over here。The number of some ends here is。

 you know， something like 100 to the end。Alright。Here， it's n times 100， okay。

So when we calculate the expectation for QI， y， isn't that still over。

Such an ugly space how does one do that efficient。 So， so okay， good。 So what's cool。

 So the payments handle work out really nicely， actually， because bidders are neutral。 Okay。

 so basically， whatever randomness there is in the mechanism。

 I don't care whatever randomness there is other peoples types。

 I don't care when I reason about like whether to bid 10 or whether to bid 20 under the assumptions that we have in this model。

 the only thing I look at is the expected amount of payment I make and the expected welfare I expected to get out of it。

 So the point is， you know， so we're gonna have this LP over here。 And when we solve it。😊。

The semantics of the LP solution will say when this bidder bids 10， they should pay an expectation。

 know，8。Okay， and now it's up to us as mechanism designers to figure out。

 so basically we're free to arrange the payment rule in any way we want。

 as long as at the end of the day， the expected payment of this bidder is  eight。But so for example。

 they could pay $8 always， whether they win or lose now that's not individually rational after the fact。

 but with a risk neutral bidder， it's strictly speaking aloud。

 or you can think about sort of ways to arrange spread the payments over the space in some better way in some more fair way。

 subject to keeping the expectation exactly the same。

So the short answer to your question is we never need to compute this expectation。

 We'll just solve directly for the cues。And we just will know there's some peas， but whatever。Yeah。

 good question， other questions。O。So that's how we express the revenue。

 purely in terms of the interim payment rule。 So for B， IC。So what do we do？Let's see。Right， so now。

We just look at our expected utility。So when bittertter eye reports truthfully。

It's expecting to get item J with to get item J with probably X I J V。 and again。

 buried in here is randomness both over V minus I and over any randomization in the mechanism itself。

But again， the point is this risk neutral bidder doesn't care just because at the end of the day。

 when I'm reasoning about what to report， what's the probability I get out M J and because the valuation is additive。

 there's not even any complications about how the different items interact。

 it can just reason separately about the different items J because valuations are additive。

 that's really useful。Okay。And then， oh， this should be a why， excuse me。Minus。Q， I， V。对。

So the point is， so this is Bider's expected utility when it reports truthfully， and again。

 the key point here is we were able to express its expected utility purely in terms of the interim rules。

And then this should just be at most the same thing with the misreport。Okay。So this is BIC。

And then for individual rationality。Same thing。Left hand side above。

 so the utility of direct revelation。Should be non negative on average。And okay。

 so that's all I claimed。 I claimed that the interm rules were enough to express expected revenue， B。

 I C and IR constraints。And so I just proved to you， I just wrote them down。Now， okay。

 so let's try to think a little harder about feasibility and these were already annoying constraints in the first place because this was the only set of constraints of which there were a lot okay so you might even notice that the number even in the old linear program。

 there's a ton of variables， but therere a small number relatively of incentive compatibility and IR constraints again。

 proportional to the sum of the types， whereas this was the one where really we had a constraint for every possible valuation profile。

So the question is， how do we write， How do we express this。

If our vocabulary is only the interim allocation rule。

 So notice the payments are totally irrelevant for encoding this。 iss not about the payments。

 so it's really about asking， you know， how do we encode this constraint here on the X post allocation rule。

 using the vocabulary only of the X interim rules， using only the Ys。O。So， al right。So obviously。

 we need to kind of throw in some constraints。To enforce feasibility。 So the question is。

 what should we throw in。 So， for example， you know， it it's going to be clear。

 Let me write down one thing， which is obviously a necessary condition。 So again。

 this is going to be constraints that I'm supplementing this linear program with trying to capture。

These constraints in our new reduced vocabulary。So it certainly should be the case that for every item。

 J。So what I'm going to do is I'm gonna look at a bitter I。 I'm gonna say。

 just what's the probability that bitter I gets item J。 Okay。

 averageverd over everything we don't know， Aver over over everything。So。So what do we average over。

 So we average over basically the types。That bitter eye might have。

The probability that it has that particular type。And then。I can just write down XI J， VI。

 so this is the probability that I wins J when its type is VI。Okay。

So what's inside the parentheses is the probability that I gets the good。

And if I sum over all the bidders， that has certainly be at most one because it could only be allocated once always。

Oh this would be why again， sorry。To that that's going to be true。

RightSo if you take any actual mechanism and you pass to its reduced form。

 you look at this interim allocation it's certainly going to satisfy this inequality because always it only gives the good away once。

 This is some average version of that， which might make us nervous。So the question is。

 is this enough or do we need more。So this is an issue， I think， I mean， one。

 there's sort of a lot of formalism here， but two， I think you really appreciate the technical issues if you try to do one or two of these examples yourself。

I'm going to ask you to work on the following。You know it's about these examples are like the complexity level of a can can。

 basically， okay， they're basically like little constraint satisfaction problems。So。

Supposes to the following example。Okay， so the question is， is this answer sufficient？

So suppose there's two bidders。And let's just go back to a single item case。And let's suppose。

 the bidest valuations are just IID。From some distribution F。50，5，1 or two。Okay。

 so there's four possible outcomes。And suppose I gave you the following alleged interim allocation rules。

Okay。So suppose。Y1 equals 12。And so again， don't forget what this means。

 So this means when bidder reports one。It wins the item 50% of the time。Okay。Now， the other bidder。

 you know， it might be one， it might be two is a 50，50 chance of each。 Okay。

 so this is really an average over two outcomes。 Okay， so bitter 1， all I know is I'm bidding1。

 and I know the other person is 50，51 or2。 and the mechanism is going to do something in either case。

But if I average over both what the other player's value is and I average over what the mechanism does。

 this is my winning probability when I report one。Okay。

 so and let's say that when Bider1 reports two， it wins with 78s probability。

And let's say for bidder  two， it only wins one eighth of the time when it reports one。

And it reports one and it wins half the time when it reports a half？So this is a mechanism that。

 you know， this seems to be favoring the first bidder for whatever reason。 for whatever。

 That's allowed。So that's my question for you。 My question is。Does there exist？An ex post rule X。

 that's feasible that only allocates the good at most once， always。That induces why。

So I want you to think about that for a minute。Let me make。

 let me just make it clear what we're looking for。Allright， so remember an x poster rule。

 So so what are the candidates for X， right？ So when x takes this input a full valuation profile。

 Okay， so it's going to take in。As input， a possible value of one and two。

 of which of course there are exactly four possibilities。And then。

The allocation rule has some probability of winning， assigns each player some probability of winning。

Okay。So candidates x for the exp post rule X are just ways of filling in these eight squares。

So that every row sums to at most one。So for each of the four reports。

What probability do you give it to each of the two bidders？So the question is。

 is there a way to fill in those eight squares so that， you know， for example。

The average winning probability of the first bidder when it reports one。

OkaySo these are the two cases where Bider1 reports one。

So this is the probability that the mechanism assigns to bitter one in those two cases。

 and these are equally likely。So the average of these two numbers should be half。Okay。

And there's three other constraints of the same form。Does it clear what we're looking for？O。

So if you think you have， if you think you figured out a solution， shout it out。

 if you think there's no solution。Explain why。I should say this does meet the sufficient condition or the necessary condition。

Okay。So the necessary condition， so how would this work， so in this setup， this is always a half。

 so everybody's equally likely to get e type， so this is just the sum over all of the y values multiplied by a half and the y values is indeed sum to2。

So this， this is legit for this constraint。I don't。 Thank you。Okay， how come。As to be。

and then the upper rightmost one has to be one to satisfy the1 app and 18 the column。

the1 half and one8 so like if they both report one， doesn't the first bidder have to get it？

one half to one of the time yeah， it's tricky， right because？Yeah， so this's so theres the profile 1。

2 is relevant for this quantity and the profile 2，1。Is relevant for this quantity。Yeah。

But this is the right kind of， I mean， it really is， I mean， it's very suuco， like Ive got to say。

Just exercise so。It'sll give me like 30 more seconds。And then I'll tell you the answer。嗯。

I know it 30 seconds。快。你得。A quick way。Yeah， so what do these constraints mean？我唔。検象なて。

What do you think？So。そ the。This once we just look at the left column。

 so we have that the first two numbers must add up to one， right？

Let's see because we have a half here yep and the second two must also add up to one。

Because we the two have a half here， the bottom have to add up to one therefore the two in the bottom left also have to add up to one Oh I see you're saying the column sum。

 no hold on。The bottom， the bottom line thing is。たと。There like two alternate ones。

So I agree these need to sum to one。What inference do you want to make here there's also sum to one because the bottom right the two is the bottom right have to sum to one and why is that the white because of this I think it's these have to sum to one Yeah。

 so those sum to one。Another house。Y 1，2 equals 78s， which means that。在。嗯。Yeah， I guess yeah。

 one hint is that the numbers， the extreme numbers tend to be helpful。

 Things close to 01 tend to be helpful for solving these problems。 So you're saying the 7，8s。Yeah。

 so that means that the two things that end with two the second and fourth。

That's about these two right Y one2 refers to these two things right so those should average to seven8s。

Right， so the sums to right， okay， good。I think we can take the18 and we can move that into an average of seven eighths on the other side。

Because。So we can figure out that two things on the right add to add up to one4， right？

Which means that the corresponding things on the left would have to have an average of seven/ eighths。

Okay， my guess is， I mean， this is exactly the right kind of reasoning。

 So my guess is if we actually wrote down all these constraints。

 it would force us to the following numbers。 I' going to write into the table。

 I think I'm just going to write them in now。 So but I mean。

 that's exactly how you reason about it right So basically you you have constraints on pairs So certain pairs have to obey certain averages and unfortunately。

 you can't pair up the pairs easily。 It's more like this path， this directed path。

 you have to chase it around， but eventually you get implications backward。It a hander。Maybe sure。

They think they have one， okay。What do you think So I think one there。

Where you or well zero to the right， I'll say。Then zero to the gave going back。Here。Okay。嗯。And then。

Three， fourths。And then to the right one。完。I could别忙。Some of the one bottom should be。

So if the bottom one is， you're saying this should be different， should be10。

There some the ones on the website should be。I mean how to be having。

so now it's78 because we more than what now average。Well now that the money doesn't work。This。

 why does it work？不。です。Te this box。こにな。Which one， this might work actually。

 It's not the planted solution I have。No， there's no reason to think they're unique，Okay。ここいう。Oh。

 I think it's true。This looks good to me。 I think it's good。没有。Yeah。Good。Okay。So。

Here's an easier one。So example two。What if I。I'll keep the78s18。I'll make that one fourth。

And I'm like that one three fourths。Would you ever have Ys and not X？What do you mean。Yeah。CaYeah。

 I'm wondering like when only make the wise， or I guess we don't have。

I'm wondering when we try to make exits from Y。So the point is the x's are just too big。

 right so the high level thing we're is we're doing this dimension reduction。

 So what we want to do is we want to sort of， in our mind， have the x's there。

 And x's actually correspond to actual mechanisms。 But we're doing this sort of compression。

 We're past in the interim rules。😊，Which is a small enough set。

 We can kind of do things like compute on it。 And I'll show you later that we get other conceptual insights from working with the Ys。

 I haven't yet。 But that's a promise。 And so， but then so what you'd like to do is。You know。

 compressed to the Y， do computational on the Y， and only at the end。

 once you've optimized over the Ys， do you kind of back out what's a good x corresponding to the one y。

Well， that's exactly what we're trying to study。 We're trying to study which wises correspond to a mechanism in the background and which don't。

 Now， even if you have why to do correspondence a mechanism。

 there's a question of how do you find it， And I'll mention that a little bit at the end。

 but it can be done。Do anything about this one？How come。So， there's what。

You get paired like the Y12 case gets pair with the Y22 case and y1 trans vice versa。

So the112 case needs to win at least three fourth of the time， think against the other two。

 and the bottom needs to win at least one half of the time， but that。1。Yeah。

So basically the problem is kind of what happens on the profile 22。Right so both of these are high。

 I mean， this isn't a total fruit， but this is the idea of the proof。I mean。

 this says that you when the first bidder bids high， it should usually win。

 this is when the second bidder bids high， it should usually win。

 but sometimes they're both bidding high and one of them' is going to win with probably at most one half。

So that's a problem。So this is infeasible。All right，Why did I do this， I did this for a few reasons。

 One is you know this problem of understanding which ys are feasible。

 which y is correspondent bona fide x's is like the main kind of technical core of this lecture。

 So it's important that you really understand the issues around that problem。

 That's the first reason I did it。The second reason is， you know， when you play around with it。

 I think， I mean， you appreciate that it's not a trivial problem， right， So so this， I mean， somehow。

You know I think what is clear from playing around with it is it's some linear system， right。

 So basically， we're just saying that certain averages in this table should be certain targets。

 So if you wanted， we could write down a huge linear system。

 and that would characterize whether or not it's feasible would say whether or not there's an X corresponding to the Y。

So that's the second reason It's just it's a complicated mapping。

 Third is that it's important to now understand that， you know， this is not enough。 Okay。

 so our second example shows and again， notice the second example still satisfies this necessary condition。

 Okay， because these numbers also sum to two。Okay， so the LP。

 the linear program we have written down right now。This stuff over here。Plus， this， you know。

 these single extra constraints for the individual items。 This is not good enough。

 There are feasible solutions to the linear program that's currently on the board that do not correspond to mechanisms。

 Okay， there are y's that satisfies these inequalities for which there's no X that projects to them。

 And that's not okay because we want to do things like optimizeim over the Y's to find a revenue maximizing Y。

 But then if we did that and there was no corresponding mechanism wouldn't do us any good。

So the final point is just， this is not good enough。 We need to add further constraints。 Okay。

 so we're not going to give up， but we just have to add more constraints，Okay， so point。

It turns out we need to add a lot more constraints， so need to add。More constraints。

To ensure feasibility。Okay。Okay，And so by feasibility。

 I just mean that every y that's a solution can be mapped back to a mechanism for the original setting。

Okay。So here's what's going to happen next。 So in the remainder of this first lecture。

 I'm going to explain how this gets done for the current setting that we're talking about。

 So I'm going to give you basically a complete solution to what are the extra constraints that force every Y to correspond to some X Okay。

 for added evaluations。 And that's where where then we're going to take a break。

 in the second lecture we're going go， we're going to do a few things。 So first of all。

 we're going to go beyond added evaluations。 We'll talk about unit demand valuations also thatll be clear that that really the discussions more general。

 and then but you know。It's not so much that we want to capture unit demand valuations per se。

 It's going to be that looking at this feasibility issue more generally will lead us to the structure of optimal mechanisms。

 which is really kind of the you know， the main point of of today。 But so first。

 let me just tell you exactly what constraints are necessary and sufficient for added evaluations for every y to correspond to an X。

All right， so let's look at so here is one necessary condition。

 Let me show you actually a bunch more really easy necessary conditions。

So we can treat each item separately。RightSo we have X I Js and we have Y I Js。

 And just with respect to feasibility， different items don't interact at all。

 So we're just going to sort of handle each item J independently。And。

So suppose we had a bona fide exposed allocation rule。And consider the induced interim rule。Okay。

 so I'm going to write down some inequalities that these y's will certainly satisfy。 Okay。

 if you started from a real allocational X。So for simplicity。I want you to think of， right。

 So remember， we have these capital Vs。 So capital V is the possible valuations that a bidder could have。

 You know，1 buck，2 bucks，3 bucks and so on。 So these are these different sets。

 I want you to think of every element these sets as disjoint。 Okay， that's just convenient。

 So think of it as if it's also tagged with a bitterder's name。 Okay。

 so I have a type that'd be like， my name is Tim。 and I'm willing to pay 10 bucks。

 That's actually my type And then everyone else here has a something thing a different one tagged with their name。

 okay。So without loss of generality， so that obviously affects nothing。

It just lets me write unions in ways that's not confusing。All right， so now。

It's going to be a lot of different conditions。 they're parameterized in the following way。

So for bidter one of all the possible types it might have， pick your favorite subset。

 I don't care which one， S1。Do the same for each of the other bidders。Okay。

So I'm going to write down two quantities。 And it's going be obvious that。

 that the second one is at least as big as the first。So expression one。Right。

So remember so there's this fixed allocation rule in the background。

So imagine I run the allocation rule x。So I pick a random valuation profile。According to the prior。

 there's some prior also， I should say that。So fix F。So I pick a random valuation， and I look。

 and then I look at who wins if anybody。And I'm looking at the probability that the winning bidder。

Under this allocation， rule x has type。In one of these sets。Okay。So if the winner is nobody。

 then it doesn't happen。 If the winner is bitter eye。

 then it counts if and only if bitter I's type is in S I。 valuationu is in S I。 Otherwise。

 it doesn't count。So probability。That the winner。Right so the probability is。

V drawn from F and also under any randomness in the allocation rule， if there is any。 So winner。呃。

Yeah。So winner of item J。An x bar an x on V。Has type。And the union of these Ss。Okay。

And let me just point out this is easy to write as an expression of the as a linear expression of the inter allocationloc rules。

So what's the probability that the winner of item J has type in some S。

 Well by linear of expectations， we just look at the bidders separately。

If we're talking about bitter eye， I just look at the various types it might have that are indeed an SI。

I look at the probability that。I has that type。And I look at the。Probability。

 according to the interim allocation rule， that it wins item J when it has that type。

So that's quantity1。Again， the F's are given， that's just the prior。

 so this is a linear function of the Y'。So here's the expression， which is obviously bigger。So。

 let 2。Be the probability。That one of the bidders simply has a type。In an SI。And again。

 this probability， this has nothing to do with the allocation rule， of course。

So this is just for a random evaluation profile drawn from the prior， there exists a bitder。

With value in the set capital S sub I。Okay。And so if we wanted to write down an expression for this。

 so this is one minus probability this doesn't happen。

And this doesn't happen if everybody misses their set S I。So this has nothing to do with anything。

 This is just a number。 Once you fix the prior， this is just， 0。1， whatever it is。Now。

 what I hope is clear。Is that one is at most two。No matter how I choose these restricted sets of types。

O。So if you parse the definitions， that's clear。The right hand side is somebody has a type in S。

The left hand side is not only does somebody have a type in S， but also such a person one。

If it's a more restrictive condition， the probability is only smaller。So two is the least one。

For all， choices of restricted types。So something was is maybe kind of surprising。Is that okay。

 going， remember what this is。 So it's going to be true that any right， So again。

 this is just a number。So think about this as a constraint。 Okay， so the right， so again。

 the prior is fixed。 So the right hand side is just a number 01。

The left hand side here is a linear constraint on the interim allocation rule on the Y， okay。

And the assertion is just that if y is derived from an X。

 So if y is a legitimate inter allocationloc rule， then this is true for all sis。

So what I want to tell you about next is Bors theorem， which states that the converse is also true。

Okay。So you give me some wise， and alleged interim allocation rule。

The the claim is that if these constraints are satisfied。 So again， remember。

 right hand side is a constant， Left hand side is a linear constraint on the Y。

 So if your y that you give me satisfies these for all choices of the S of Is。

 then what I'm going to prove is that there is indeed an x that induces that Y。

 So Y is indeed an inter allocationlocable。Okay。So it cannot be an example like this。

 So if you put differently， if you give me a y like this one。

 which is inconsistent with every X post allocation rule。

 then it must violate some constraint of this type for a suitable choice of the SO。

So not only are these necessarily holding for every intra allocationloc rule。

 Y they characterize the intra allocationloc rules Y。So is it clear what I'm standing？

So that's Border's theorem。That this is also sufficient。So， i。e。Y J V Is。Induced by some。X。

 I J V arrows。If and only if one。At most two。For all S1 and V1。SN and VN。Okay。All right。

 so I'm doing， I'm making good progress。 so let me I'm going to prove this to you。嗯。Because。

I like the proof。proofof is basically something you'd put on a 2，61 final。

 The proof is max flowman cut，ItTook a long time for economists to realize the proof was max Fman cut。

 but。Now we all realize that。Tme。So。去去去。All right。Maybe I'll show you the network。So we're thinking。

 the way you should think about it is that we're given the Ys and we're trying to compute。

 We're not worried about efficiently efficiency， but we're going to use max flow。

 We're trying to compute on a big graph using max flow a suitable X。 Okay。

 that's what we're trying to do。So it's just going to be a simple two layer network with a source and a sink。

So in the first layer， we just have all of the possible evaluation profiles。 Again， remember。

 we're not trying to do anything efficiently here。 We're just trying to prove something okay。

So I'm going to write down this big graph。So there's evaluation profile。

 there's another valuation profile。And so on。Yeah。All of these have arcs。

And flow in this graph is going to correspond to probability。Okay。

 so we're going to try to push one unit of flow from S to T corresponding to probability。

So given that we think of one unit are probably starting at S。

And then it goes to the valuation profiles。And so， you know。

 the capacities on these arcs out of S are what you'd think they would be。

 right so we have a prior it tells us exactly how likely each valuation profile is。

 We just use those numbers in the prior to assign capacities on these arcs。So this is just F。Of V1。

 F of V2， and so on。Good。So now， remember， so we're， we're thinking of we're given as input the Y's。

 and we're trying to now compute the x's。 So x is a full blown x post allocation rule。

 It has to It has to decide what to do for every valuation profile。 Okay， meaning who wins。 Okay。

 And again， I'm just doing this separately for each good。

 So think in your mind that there's a single good。And now， basically。

 flow coming out of evaluation profile is just going to say， who's the winner， Okay。

 or if it's sending flow to multiple people， that's like a randomized decision about who the winner is。

 okay。So the next layer。Is going to be these tagged evaluations。So think of it， as you know， we have。

So this means that player one wins when its type is V1， this is player one wins。呃。

It has some other type V2。And so on。And then down here we have player N winning when its type is whatever it is。

 Via Bell。And then we also have a dummy node for nobody wins。Okay。

And these are all going to be connected to the sink。And remember， we're given。

The interim allocation rule。 Okay， so we're given these Y's and y says exactly this kind of information。

 It says when a bitter eye reports a given type， the probability that it wins。

And so basically on one of these outgoing arcs is going to be just why。This is going to be Y of one。

When its report is V1， it's going to be a y of1 and when it report is V2。

Y of n when this report is VL。And then this just basically has all the residual。

 this last no C arc has the residual probability。So these things are going to sum up to something that's a most one。

That was basically the necessary condition I just erased。

 so whatever the extent to which this is less than one is just what we put up here。

So some of these of course， are one， so the capacity incident to the S。

 the capacity incident to the source is just equal to1。And then over here as well。

 the capacity incident to the sink is equal to one。And then inside here。

Each of from each valuation profile。Right， so this says who the n bidders are and what their types are。

 There's n plus one outgoing arcs。The plus one is because the mechanism always has the option of having no winner at all。

The N types， well， you know， you can award it to bidder 1 or bitter2 or bitter 3。

 you have those n options， but of course， you can't choose what their type is。

 right So give an evaluation profile， either you can award it to bidder 1 when their type is V1 or bidter2 when their type is V2 and so on。

Oops， yeah， so that wouldn't be。 that wouldn't work。

So you have an outgoing mark to only one node that represents bid 1。

 and it's exactly the node where bitter one's type is what its type is in that valuation profile。

And we're going to go ahead and make these infinite capacity because we can。嗯，Yeah， infinite。 I mean。

 it just helps us reason about the proof， right， So ultimately。

 we've got to say that every cut is big。 And if some of the things are infinite。

 then if you cut one of those edges， we know what's big。 So we we're making our lives easier here。

So that's the graph。Allright， and so。嗯。Claim one。Is that the Y， okay， so remember， we're given the Y。

 and our job is to check whether they're feasible or not。

 whether they're a real inter allocationloc rule or just some poseer thereof。So the claim is that。

 you know， there is a allocation rule inducing the Y。

 if and only if this network supports a flow of value1。Okay，If it supports a flow of value1。

 then you know again， think of basically a flow in this graph is an explicit description of a mechanism。

 right， so given evaluation profile， you just look at the outgoing flow。

 you scale it back up by the amount of flow that was incoming。

 and that tells you the probability to award the item to each of the people。

 so I'll leave that for you to check offline， if you like。

 But I've set up the graph so that flows of value1 correspond exactly to X post allocation rules that induce the interim rule Y。

So that's what it boils down to does this。Network support a flow of value1 or not。 So that。

 of course， by max flowing cut reduces to just checking that every ST cut has value at least one。

 So that's what we're going to do。All right。ち。So let's say you check。Why induced。By some x。

If and only if max flow value。Eals one。 Okay， so in fact。

 flows of value 1 correspond to xos rules x that induce y。Okay。So。By Maxman cut。Just need to check。

All ST cuts。Have value at least one。So fix an ST cut。Fix an ST cut。And I'll draw a picture。

So the schematic that I want to think about。Is this first layer divided into some A and some a bar？

And the second layer is divided into some B and some B bar。

So A and B are on the source side of this cut。Allright， so what edges are cut？ Okay， So again。

 remember the source side。So the source side here is this。

So all of these edges sticking into a bar are cut。At the very least。

And all these edges sticking into tea from， oh， sorry， that's not what I wanted。

All the arcs sticking out of B into T or cut。Okay。So。

I need to relate this to this condition relating one and 2。 Okay， so the claim is。

 is that as long as these conditions， one at most two hold， then indeed。

 the min cut value is at least one。 But I mean， I need this， right， We know that。We know that wise。

 if we don't have these extra constraints， then there will be wise that we can't。呃，In部。Okay。

 so here's what we do。So we define s sub I。To be the types of eye。

Or the valuations of I that are not represented in a。O。So evaluations in S sub I。

 if every single occurrence of it is in a bar。 Remember， these are valuation profiles。

 So in each profile， I has some type。S sub I are the types that only appear in the valuation profiles in A bar。

Some types of eye。Not。Represented。In a。看。Allright， so that tells us something about how much capacity we're cutting here。

 Right remember， we cut every arc that goes from S to a type in a bar。 Okay， And again， remember。

 by definition， every single occurrence of S sub I is down here。So。Here's the first key claim。

Which is straightforward。 if you can just keep track of all the notation。

 So the total capacity of the cut edges。Between S and valuation profiles， these evaluation profiles。

Is at least？The probability that there exists I。With a type in S sub I。

Which was exactly our expression， one。Okay。So again， this is just by how we defined S sub I。

 All occurrences of everything in S sub I are down here。Okay。

So in any evaluation profile where anybody has a type from SI， that's got to be an A bar。

 and A bar are the things that are getting cut。And then sum of this is just the total probability mass on those events。

All right， so we cut at least one。Right here。Okay。So now here here's where having infinite capacity edge just simplifies our life。

So I've drawns edges going both into and out of the red blob， right。

 But one of those we're not going to have。Which one。So see these two crossing edges。

I claim one of those we'd immediately be done。 We're trying to prove that the cut has value at least one。

Yeah， so forget this one， right， that would be a cut edge of infinite capacity。

This thing going in is fine。OkayMimum cuts won't have those， but that's fine。One question。

 The cut from S to A bar， shouldnn't it be2。 Why is it one instead of two。

One was the probability that you have an SI and。The was just a probability。Oh， that's two。

 maybe is what you're saying。 Oh， sorry。You're totally right。Thank you。 Thank you。

 You're absolutely right。Absolutely right。Good。O。对呀。嗯。That's a two Tim， cheeseez。Sorry。

 an usually thin too for me。All right， so what does that mean。

 So what does it mean that we don't have any outgoing arcs？Well， so that means。Right， so all right。

 okay， let me just throw this down。Can assume it be。Includes every arc of the form。

So every node of the form IVI。With VI， not in SO I。Okay， so consider valuation。

 which is not an S sub I。That means it is represented in A。Right。That is， if you're not an S sub I。

 there's some valuation profile here where indeed bitter I has this valuation V sub I。

 That means there is an arc to the node which represents I winning at valuation V sub I。

 So that node better B in the set B。 So that's all this says。

 You can assume B includes every node corresponding to a bitter I winning with evaluation V when V is not an S sub I。

So elses cut a plus infinity edge。And now， remember， we cut all of the arcs out of B going to T。Okay。

So total capacity。Of cut edges。Of the form。I V I to T。Is at least。 So remember。

 the sum of the capacities here is one。So it's at least1 minus the stuff I don't cut。

 The stuff I don't cut is here。And all of the nodes here。Have the property that VI is in SI。

So any node where VI is not an S is up here， so these are only nodes where VI is an S。So one minus。

Yeah， let me just write down the capacities， so I sum over all of the bidders。

I sum over all of their possible types in S I。 and then I look at the。ちち。I get this right， F I。I see。

I apologize， I made one error on this capacity。So。Y1 of V1？That's the probability， right。

 So the way I define this， this doesn't sum to 1。 I got the scaling wrong。 So y won v1。

 So that says when Bi1 has valuation 1， the probability that it wins。 Okay。

 so it's the probability it wins conditional on having the evaluation V1。

 So the unconditional winning probability and having V1 is F of。F of， F of one。Times V1。

Can some this would be F of。1 V2， and this would be F of N Vl。O。

So I wrote down conditional probabilities of winning， given your type。

 what I really want is just unconditional event that you both have a type。

 a certain type and you won at that type。 and now these sum to one。Sorry about that。

So now I'm just summing up the capacities of the cut edges over all of the nodes where a bitter eye has some type in S sub I。

 And so that's F sub I， V sub I， Y， I， V I。And this。Is equal to one。So that's just the probability。

 right or put differently。 This is the probability of a winner。 you know， both， you know。

 it's probably the winner has， has。Is it bit I with a type of VI？So adding them together。

So cut value， whatever you decide， is's at least2 plus1 minus-1。And remember。

 the assumption is that two's at least one。And that was for an arbitrary S T cut。

 So every cut has value at least one that can support a flow of value 1。

 So that gives us the allocation rule implementing that y。Okay。So again， let me just before we break。

 let me just remind you why we were doing this， right So this completes you know， something nice。

 So we had the super big LP with expensively many variables。 We asked the question。

 could we have a smaller LP expressing the same thing。

 And so we decided on the variable set very early， We said， well。

 let's just have a variable for each for the interim allocationloc rules and the interim payment rules。

 And then there was a question， could we actually write down a set of constraints phrased only in terms of the interim rules that captured the full mechanism design space and no extra stuff。

And it was easy to capture the BIC constraints。 It was easy to capture the individual rationally constraints。

 it was easy to phrase the objective。 so border theorem now says if you just stick in these one at most two constraints for each of the items J。

 and again remember these are written purely in terms of the inters Y so they're in the right vocabulary。

 you throw all of these constraints in that now we have the LP we want， there's a lot of constraints。

 but at least there's a polys size set of variables and everything in there is the mechanism design feasible region。

So let's break for 10 minutes。 when we come back， we're going to generalize this and the payoff will be finally。

 we'll get an analog of Myerson's theory for these multi parametera problems。

 We'll discover a sense in which optimal mechanisms while not virtual welfare maximization are just distributions over virtual welfare maximizes。

 So that's what we'll study in the last lecture。 So see you in 10 minutes。

