# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p04 -04-4_ Algorithmic Mechanism Design).zh_en -BV1VmC2YzEXJ_p4-

Thiss a couple quick reminders， so the first exercise set is due now you should have either already emailed it to the TAs or you should have already given them a hard copy of your solutions。

The second exercise set has been posted。 You can find that from the website。 in general。

 I don't plan to print anything and bring it to。Bring it to class that seems like an antiquated sort of ceremony at this point。

 so check out the website， the second exercise set。

 which covers this lecture in the previous lecture you can find there。

So any questions before we get started？Okay， so last lecture， we stated and proved Myerson's lelemma。

 and this lecture next week are going to be devoted mostly to applications of it to using that as a foundation on which we build further mechanism design theory。

To remind you， Myerson's lemma is a characterization of the allocation rules that can be extended to dominant strategy incentive of compatible mechanisms。

So an allocation rule remember is your decision of who wins what and the question then is given such a decision。

 can you come up with payments， who pays what so that that coupling of the allocation of the payment rules is dominant strategy and of compatible sometimes you can sometimes you can't depends on the allocation rule。

 but in a very simple conceptually way， it depends on whether that rule is monotone so there exists such payments if and only if the allocation rule is monotone and we saw examples of monotone allocation rules last time we'll see more today。

Furthermore， in the case where you have a monotone allocation rule。

 there is no ambiguity in how to define the payment rule。

 there is only one way to do it if you normalize things so that zero bidders pay zero and moreover。

 we derived an explicit formula for what those payments are。

 we did that in the course of proving Marson's lemma for the case of a piecewise constant allocation function X。

 I have rewritten that payment formula on the board here。

So the first brief thing I want to do today is give you further intuition for this payment rule。

 We discussed how it's in some sense， the area to the left of the allocation curve on Monday。

 but now I want to apply it to sponsored search auction。

 show you fully explicitly what is the awesome sponsored search a that is how do you define payments when you use the surplus surplus maximizing allocation rule。

 which you'll recall。Is to assign the Jaith highest bidder。To the jas clocklock。And as usual。

 we're assuming that higher slots are better。So we have this notion of click through weights or CTRs。

Which is your probability of getting a click given you're displayed in the J8 slot。

 and those only go up as the slots get higher and higher。

So we argued on Monday that this is a monottonone allocation rule， the higher you bid。

 the higher the slot you'll get， and the better your CTR。

 So Myison's Lemma gives us an explicit payment formula for how you should assign payments if you want to be DS SIC。

So let's just go through what those are。 That is all we're going to do at the moment is instantiate this formula。

 interpret it for this particular single parameter environment。 Okay。

 this is just a special case to which Myson's lemma applies。So。So here， B is a bid profile。

 a bid vector。 I is a particular bidder。 And we're asking， what should it pay。Okay。

So the way to think about this formula here。 So we're thinking about a particular bitter I。

 and we fix the bids B minus I the bids of everybody else。

 We want to compute the payment that bitter I makes。 and it bids something。 It bid like 10， whatever。

The way to think about this formula is as a thought experiment just in our minds。

 we start bitter eyes bit at 0。 Okay， again， the other n -1 bitders we keep their bit fixed。

 be minus I is fixed。And we raise bitter eyes bid from 0 all the way up to what it actually bid B sub I。

So we have a piecewise， constant allocation curve。 So along the way。

 the allocation that gets awarded to bitter eye at this current imaginary bid will jump。 Initially。

 it'll be 0， Then it'll jump。 maybe it jumps multiple times before it finally gets its actual allocation at its actual bid。

 and recall the payment formula， you just track the jumps every time there's a jump。

 You add that to the running sum。 What you add， you add the magnitude of the jump in the allocation times the position。

 the bid at which you saw that jump。So what does that mean in the context of sponsored search？ Well。

 I think it's easiest。To think about the highest bidder， which is the one that gets the best slot。

So just to keep the notation down， let's rein。The bidders， so that in this bid profile。

 Bider number one has the highest bid and so on。Okay， so assume without loss of generality。

That we're looking at a bid profile， which is sorted。Okay， just for ease of notation。

So now think about bitter 1， the one with the highest bit。Okay。So what is its allocation？Okay。

 so what is its x value in this bid profile。Alpha 1， it gets the top slot。

 The C T R of the top slot is alpha 1， okay。Now， imagine that we reset in our minds。

 We reset its bid to be 0。 So it's going to be the lowest bid。

 And then we slowly increase it from 0 up to its actual bid B U sub1。

How is its allocation going to change What's the trajectory of the allocation as we move。

 it's bitden that way。From alpha。Good， so initially it's zero because it's the worst bidder of all。

 At some point， the imaginary bid is the k highest。 At that point， it gets the k slot。

 and the allocation is alpha sub K。 then it becomes alpha K minus-1 Al K -2 and so on all the way up to alpha sub 1。

 So the magnitude of the jumps in the allocation of bidder1 is going to be the jump in consecutive CTs。

 That is a generic jump will have the form alpha J minus alpha J plus1。Yeah。Okay。

So this difference corresponds to a term of this form。 Okay， a jump in its allocation。So now。

 the next thing to figure out is what are the positions， what are the bids at which。

The allocation jumps。 Okay， and I think it's easiest to think about the final jump。 The jumps。

 So remember， this is the top bidder piece of one。 We're fixing everyone else's bids they lower。

 and their in sorted order。And eventually， the allocation of this bidder is going to jump from alpha 2 to alpha 1。

What is the location， that is， what is the imaginary value of this bid。

 which you trigger this jump from alpha2 to alpha 1。B2， you have to beat at everyone else。

 And the nearest competitor is B sub 2， the second highest bit。 Okay， So when J is1。

 when we're looking at alpha 1 minus alpha 2， the the point at which that happens is B sub2。

 And in general， the position at which you have this jump in the allocation is going to be B sub J plus 1。

Okay。And now we sum over all of the break points。And so there's a jump。Starting from the worst slot。

 the ca slot all the way up to the slot that it actually receives。 whoops， should be J equals I。

 excuse me。Up to the slot that it actually receives， which is the I slot， okay。主要在。Okay。

 so that is exactly the payment。 So if you're the I highs bitter and you get the ice slot。

 this is what you should pick。 That's what myinlemma dictates。Now， this becomes。

 so this is already reasonably simple。 You know， obviously。

 you could easily write the algorithm to compute these that would run blazingly fast。

Let me just point out。 So I guess I'm interpreting here Alpha K plus 1 is being equal to 0。也不对？Now。

 remember， in the context of question。So then what's B sub J plus1？That would be be I plus 1。 Yeah。

 so it's all， So remember the the slots， the top slot is one， and then they go down。 Okay。

 so you're looking at all the slots below you on the page， which are higher indices。Now。

 remember in sponsorons search， the way we modeled it is we said we're thinking of advertisers as bidders as not having a value for an impression for being shown per se。

 except in as much as an impression leads to a click。

 So their value is really fundamentally for clicks。 And with that modeling。

 the way it actually works in practice is payments are assigned when you get a click。 Okay。

 not when you get shown。 you don't it's free to get shown， but if you get clicked on。

 that's when you have to pay。So this is just the payment that you're supposed to assign someone for being shown。

 If we're only going to charge per click， which is only going to happen an alpha I fraction of the time。

 then we should scale this up by one over Al I for the payments to be correct， okay。

So you multiply this。By one over alpha I。To get per click rather than per display。

 rather than per impression payments。Okay， so it's just going be a one over alpha I up front here。

And if you think about it， this is， I mean， you have to think about this for a minute or two to see this。

 But once you divide this by alpha sub I， actually， this has a really simple interpretation。

 So basically what you pay per click is just a suitable average。

 a suitable con combination of the bids of the advertisers in the slots worse than yours。

 So you can place some average of the lower bids。 That's what you pay per click。And this is， in fact。

 very close to the actions used， options used in practice for sponsored search。Full disclosure。

 The auctions used by all the major search engines are a little bit different。

 It's because of a historical accident。 actually， so by historical accident。

 the auctions used in practice are based on what's called the generalized second price a。

 And it's a little bit simpler to describe than this one。

 where if you're if you're an advertiser and you're assigned to slot J。

 you don't pay an average of the slots below you， you just pay the bid immediately below。 Okay。

 so you're going to pay bid BJ plus1， not an average of BJ plus1 through B K。 Okay。

 so the pricing is a little bit more aggressive in the optionss used in practice。 now。

 by Marison's Lemma， we know that if you want to be dominant strategy and center compatibleible。

 you have no choice。 This is the only thing you can do。

So as soon as I tell you that the auctions in practice use a slightly different payment rule。

 you already know they cannot be dominant strategy instead ofcomp。 Okay。

 they cannot be and they're not。 They are a little bit harder to figure out how to bid in strategically than this a would be。

 That said， there's some nice theory。 And you will go through the major points in problem 3 of your problem set。

 which shows that these two options are， in fact， you know， equivalent in a reasonably strong sense。

 Okay they're not the same option， And in particular， the one in practice is not DSIC。

 but it always has an equilibrium， which in some ways is simulating the dominant strategy outcome of this auction。

 Okay， So again， that's problem 3 on the problem set。So questions about sponsored search。

 that's going to be all I say about it for now。有。So， why。Whyhy is it。

Essentially because they didn't know this theory。Yeah， to the point that。I mean。

 there are people at these search engines that in some sense would prefer that discuss and perhaps would even prefer to switch to this payment rule because this is requiring bidders to work a little bit harder than they would have to otherwise。

So。Yeah， that's the reason。So it was not necessarily intentional to deviate from this theory when they first designed it。

 And， of course， you know， once you design it and it's making billions of dollars。

 it's high overhead to change so。Other questions？Okay。

 so that's our first application slash instantiation of myisonslemma for the day。

What I want to do next is talk about。Another type of option。Npsack auctions。

 This is going to be yet another single parameter environment。 So it is yet another special case。

 Okay It's yet another instantiation of the general tool， which I've given you， alright。

So here's the setup。So it's a single parameter environment。

 so we have n bidders each of the private valuation as usual。But in addition。Each bitter eye has。

A size。WWSI， everybody knows what this is， okay this is common public information。

And then the usual private valuation。For example， bitter eyed might have a television ad。

 and the size is the length of this television ad， which is verifiable and known。

 And then it's some willingness that has some value。

 which is its willingness to pay to have its TV ad shown during the Super Bowl。The seller。

Has a capacity。Capital W， perhaps that is the length of some commercial break。

 Perhaps that's three minutes and the bitter sizes are 20 seconds，30 seconds，45 seconds and so on。

 question。Un subsids are terms。No， those are different units。 Okay， so your size might be 20 seconds。

 and your valuation might be $10 million。But it's 10 million dollars for the whole 20 seconds rather than per second。

It's not so you cannot split Ni in。Okay， so it's just an indivisible item。

 You cannot show half of the TI。Okay， so that's one story。 You can， of course， I mean。

 Napsack problems， as you know， come up everywhere whenever you have a shared resource with some budget on its use。

 Maybe these are files you're storing on a server。 Maybe these are data streams。

 you would need to pack into a communication channel。

 Maybe there are processes you need to schedule on a supercomputer， whatever， okay。All right， so。

What are the possible outcomes？ So remember in a single parameterer environment。

 there's a set capital X， which says what you can legitimately do as the designer。Well。

 so the feasible set are just the correspond to the subsets of bidders whose sizes actually obey your capacity。

So these are 01 vectors。Such that。So again， one here means you've chosen a bidder as a winner and as zero indicates you have not chosen this bidder。

 it's a loser。And so if you look at the sizes of the bidders that you've chosen。

That should be at most the available capacity。So if you like a single item auction。

 it's just the special case where every size is one and where the capacity is one。

 If you had K copies of an item，1 per customer， then you'd have capital W equal to K。 And again。

 all the sizes equal to one here， different bidders can have different sizes。All right。

So what I want to do next is apply the same two step design approach I've been advocating all along toward designing allocation and payment rules。

First step， without justification， we assume that the bids are equal to the true valuations。

 And we ask， what would we do then， How would we maximize surplus and what algorithm would we use。

Then having made that decision in step 1， we try to get the payments right so that we have a dominant strategy instead setcomp compatible mechanism。

 thereby justifying our assumption that the bids were equal to the actual valuations。So step one。If。

 in fact。The bids equaled the valuations。 What would we do。If again。

 we were striving for one of these awesome auctions。So we want to maximize surplus。

So what our allocation rule would be， Well， assuming the bids equal the values， again， for now。

 without justification。We would just look at。The surplus。Of the various feasible solutions。

And we take the highest number we could get。好的。So remember。

 x is just all of the subsets of bidders who actually fit in the Napsack who obey the capacity。

 amongst all of them， we're going to select the one that maximizes the surplus。

 or at least if the B is equal the VIs， this would be the choice that maximizes the surplus。That is。

 we would solve。The Napsack， the instance of the Napsack problem induced by the bids that we were given and the sizes which we already know are priori right so I'm assuming so I list algorithms is one of the pre prerequisites of this class。

 So I assume you've seen the Napsack problem before if you haven't or you need a reminder I teach it in 161 and algorithms here and there's some videos of my lectures on Napsacks。

 I'll go ahead and post those on the webp page if you need to review。But in any case。

 this is the Napsack problem。 I give you values。 I give you sizes。

 and you want to maximize the value in the Napsack subject to capacity。

 And so what I'm saying is this allocation rule， the surplus maximization problem is exactly a Napsack problem。

 The values are given by the bids， the sizes you knew up front。So this is step 1。 Okay。

 assuming without justification that bids equals values。

 what would you do if you want to maximize surplus Well， just by definition。

 you'd solve this snapack problem with the bids equal to values。So step 2 says。

 given that design choice， let's get the payments right。 Now that we have Myison's lemma。

 we understand what that means。 Basically， we cross our fingers。

 hope in the allocation rules is monotone。 And if it is， we're done。

 if it's not back to the drawing board。 But if it is we're done。

 Myson'slema tells us how to implement step 2。In fact， this rule is indeed monotone。

It's not hard to prove。 I ask you to prove it on exercise set number two。 In fact， more generally。

 any single parameter environments surplus maximization leads to a monotone allocation rule。

 It is not just about the NApsack problem。 Very generally， surplus maximization gives you monoicity。

 and therefore， by Maron's lemma， you get DS S I C for free。We first saw this with the Viy a， right。

 We might have wanted to give the item to the highest bidder。

 but we didn't know who it was in advance， but we discovered the Viy a solved that surplus maxization problem as well。

 as if we knew the data in advance。 We are now seeing a much more general form of that。

 Any single parameter environment。 If you knew the values up front。

 you might want to do surplus maximization。 What we're learning from these two tools。 First of all。

 the claim that surplus maximization is monotone。 Secondly， Myson's lemma。

 which tells us how to take a monotone rule and make it instead of compatible。 Again。

 it says we can maximize surplus essentially for free。 we didn't know the data up front。

 it doesn't matter。 We still can do it giving bidders dominant strategies。So this rule is monotone。

And， therefore。Myasherson's Lena gives a payment ruleee。So an XP。Is DI DSIC。Okay， and again。

 part of what I want to do this lecture is just develop your intuition about what these payment rules look like and kind of make them a little less mysterious。

So let me actually digress slightly。So this is just sort of existential， right。

 So this just says we can make surplus maximization and center it compatible。

Let's drill down and look at what these payments actually are。 Okay， because they're not so bad。

So let's now take it on faith that this allocation rule of monotone。

What's the range of this allocation rule， What kind of numbers does it ever spit out。

To either 0 or one。 This is like simpler than sponsored search。 You either win or you lose。

 Your TV ad is shown or it's not，So what does a monotone 0，1 function look like？It's pretty simple。

 right， zero for a while。 Then it jumps to one。Okay。So。And remember， when we draw these curves。

 we're thinking about a fixed eye。And fixed bids by the other bidders。 Okay。

 and we're just varying this one bidder's bid。So there's some point Z。At which。X of Z。 And again。

 I'm looking just at I's allocation， given B minus I。

 There's some point at which it jumps from 0 to 1。And so this payment formula is not so hard to write down or understand when you have a 0。

1 monotone function。Okay。So， so it's clear that， you know， if a bidder loses。

 then this payment is going to be 0，If a bid wins。Okay， so this is where B is and the bidder wins。

What do we do， Well we look at the break points to the left， There's only one of them。

 We look at the magnitude of the jump。 Well， that's one。

 And then we look at the position in which that jump happened。 Okay， so that's the Z。对。

So in this picture， the payment of bitter I， when it bids on the winning side， it's just equal to Z。

Okay， that is the payment of a bidder in one of these 0。

1 monotone rules is just the minimum bid that it could have gotten away with and still won。

The smallest bit at which it would continue to win。And now， think about the victory auction。

 This is a totally legit way to interpret the victory auction。

 What is the winner pay that pay the smallest bid at which they would have still been the highest bid。

 I。e。 the second highest bid。 exact same principle that we're seeing here。So。If bitter eye wins。

Then the payment is what's often called critical bid。Which is what I just said。The minimum bid。

At which I still。Ws。O。Yeah。What do we do？Yeah， I mean， the theory works fine。

 no matter how you want to handle tos。So， I mean， you know， if it。

 if it tie broken away that you lost， obviously， you should pay 0。

 And if a tie broken away that you won， then you should use this formula。Okay。Good。So again。

 I've given you Myerson's dilemma in a pretty general form。

 And that's because I want to wintiateated it in lots of different ways for lots of different applications。

 But often in a concrete situation， you should not be scared of this format。

 It's often something very simple and easy to understand like this critical bid payment。有。Nextさ。

What do mean。タぶびっくりの。唔全。The pricing function changed。那さん。嗯。No， it does， right， I mean， I。

 what do you mean， I mean， the English sentence。You know that you know your payment is the smallest thing in which you continue to win that English sentence is the same in both cases。

 and that English sentence remains true when you have 01 allocation vectors in your feasible set。

 okay but it's not so it's not I mean， in the victory auction。

 the smallest bit at which you continue to win is the second highest bid overall。

In a knapsackack problem， the smallest bit of which you continue to win， its。

 it's not easy to explain what that is。 I mean， it is what it is。

 but that doesn't necessarily admit a simple description。Yeah。Okay。

 so I have a question for you then。So surplus maximization， monotone rule， payments， DS S I C。

 awesome。😊，Or is it， is this an awesome option。什么样的 opinion？那是。Yeah， so remember。

 there was in addition to surplus maxization in DS SI C。

 which is what I've been talking about today so far。 We also wanted to be computationally efficient。

行。So these were the ingredients。あ。And algorithm that I've described to you。Satisfies one， satisfies2。

 does not satisfy 3。 In fact， no a can satisfy。 forget about one。

 No a can satisfy 2 and 3 unless p equals N P。So answer。No。And the reason。

Is that we don't know of a polynomial time algorithm to solve thenapsack problem。 Evally。

 we don't know of a polynomial time implementation of this allocation rule。And， of course。

 we can say more。 It's not that we're just， you know， stupid。 we haven't found the right algorithm。

 It's an MP complete problem。 Okay， so if P is not equal to N P there does not exist。

 A polynomial time implementation of this allocation rule。是。So。That motivates the question。

So what kind of option should we use for thisnapsack option， I mean， just because itt't be complete。

 the problem doesn't go away。And so we'd still like some theory to guide us about how to approach this problem。

So if we can't have all three of these goals simultaneously。

Suggest we should relax at least one of them， one of these condition。So the question then is。

 which one should we relax。So like， what about condition1， What if we relax condition1。

 would that help。It's actually sort of a stupid suggestion， why？There two。

There's actually an even more fundamental problem than that。You're right。 I agree。

 And I'll come up later。 But there's an even more basic problem。Yeah。

 isn't the surplus maximizing what got us the N exactly。 forgetge about one。

 One was never the problem。2 and 3 are incompatible。Already， okay。

 so it will access as much as you want。 Thr it out completely。 You still can't get 2 and3。

So relaxing one doesn't help。You can't have two and three。Unless peak was NP。Okay。

 so there will be cases。 This will more be next quarter where it's interesting to relax one。

 But that's not going to get us out of our current bind， okay。

So what I want to talk about relaxing the other things。And so one totally reasonable approach。

It's not going to get much air time in lecture， but it's a totally reasonable approach。

 It's to relax 3。Especially in the context of knapsack。

 it seems actually maybe not that bad to relax 3。Why is that？

Do we know any at least nontri non force search algorithms for Napsack？Sure。

 right certainly if you took algorithms from me， you do， okay。

So there are dynamic programming algorithms for solving the Napsack problem。

 which's called pseudo polynomial time。 But for many instances that you come across。

 this is much better than say， two to the end。 It's much better than exponential time， okay。So， E G。

Solvednapsack。And pseudo polynomial time。Really， the more general point here is if you。

 if the Napssack instances are small and or structured enough and you have enough time and machine power to solve them in your budget。

 then by all means， go for it。 don't let MP complete to stop you。

 if you can solve them exactly okay for whatever application domain you're working in， go for it。

 that gives you implementation of the surplus maximizing rule。 And again。

 you can use Myersson's lemma， you still have monoonicity。

 even if you took super polynomial time to solve it。 so you can still have monoonicity。

 you can still apply Myersson's lemma。So if yournapsack instances are small enough and you have enough time。

 go ahead and do this totally legitimate way to to circumvent the problem。Alright， so。

 but what I want to talk a little bit more about is the case where your Napssack instances are sufficiently big that this doesn't cut it。

 Okay， that you really just don't maybe maybe you're solving these options in real time。

 Maybe you don't want to use enemy programming。 It's too slow。

 You want something which is more like a near linear or heuristic for a Napsack algorithm。

 That's what you have to use to get into your time budget。So， but differently。

 what I want to think about is。Insisting on one in three。And relaxing， too。Okay。

 relaxing to hopefully as little as possible。So， this brings us。To a sub branchch。

Of algorithmic game theory called algorithmic mechanism design。

I'm actually not going to say all that much about this branch。

 I'll talk about it in lecture for maybe 30 minutes。

 You'll have two or three homework problems on it。 That's about what you're gonna to see about this。

 Okay， I don't want you to get the wrong impression。 I mean。

 this is one of the earliest concerns on the boundary of game theory of economics and computer science。

 And it's really been a cottage industry。 there's been a lot of work on this over the past 15 years。

 I'll only have time to give you a taste of it。The chief concern of algorithmic mechanism design。

Is to say， well， problems like Napsack options and， of course， even harder problems。

 which you'll see on the homework， you can't get all three of these。

 What if we insist on computational efficiency， We insist on the strong incentive guarantee of dominant strategy of compatible。

 How close to maximum surplus can we get， Okay， How much can we get away with。

 Reing surplus optimality and get recover computational tractability。对。

So that's the name of the game in algorithmic mechanism design。Yeah。Now。

 an equivalent version of this。 What's cool is right。 So one is this DSSIC property， right。

 But what's cool is we now have Myison's Lemma， which tells us exactly which allocation rules are implementable。

 says it's exactly the monotone ones so we can replace one。

 which is this sort of hard to rock andcompatibility condition with just the much simpler and much more operational monotonicity condition。

😊，So really the way people in this field think about algorithmic mechanism design。

Is you want to get as close as possible to optimal surplus to the best possible outcome。

We know we have to relax it because it's empty hard。We want to be polynomial time。

And we want to be monotone。Okay， from one direction of of Marson's lemma。

 we know that as long as we're monotone， we'll be able to extend that to the DS S I C constraint。

 The other direction of Mason's lemma says we know we're not throwing out anything interesting by writing monotone here。

 There's no DS S I C auctions that we're missing out on。

So what's cool about algorithm mechanism design is it's really。Ha's a very familiar flavor。

To people who work in algorithms， So there's a field called approximation algorithms。

Which hopefully some of you have seen in your classes。What approximation algorithm studies is， well。

 for an N B hard problem， let's get as close to optimality as we can， subject to polynomial time。

Because of Myerson's lemma and rewriting this last const。

 algorithm mechanism design is almost exactly the same field。

Rather than getting as close optimal as possible subject to polynomial time。

 you get as close as possible subject to polynomial time and some extra constraint on your algorithm。

完了真的是。Okay。So really， the way I tell people to think about this is。

Algothmic mechanism design boils down using myin Limma。

 It boils down to essentially algorithm design， as many of us have lots of experience with in a sort of oddly constrained computational model。

 Okay， with this extra monoity constraint。 Okay， so the fact that you care at the end of the day about having a system with with good performance guarantees with strategic participants。

 that's get that through My's Limma gets compiled into this very relatively easy to understand extra constraints on the kinds of algorithms that you design。

😊，Okay。So that's algorithmic mechanism design。And I think the fact that it bears so much resemblance to something that。

The computer science field knows an awful lot about the design analysis of heuristics。

 And I really think that's one of the reasons why there's been so much work and progress in algorithm mechanism design over the past 15 years。

Question。Say it again。Like looking for it on the borders。呃，对。在我车。可可审。嗯m哼。It's a good question。

 So that's actually。On exercise， set number 2。So， and in fact， that's the whole reason。 I mean。

 just to give you a hint。 I guess it's sort of the hints on the exercise set， too。

But one of the reasons， one of the reasons I digressed into this critical bid discussion。

So if you think about， you know now that we know that the payments are so simple。

 it's just about understanding this critical bid。 If you think about that for a little while。

 you realize that it means to compute payments for people。

 you just have to solve a few extra surplus maximization problems。Okay。

 so you set surplus maximization once to figure out the real allocation。

 and then you do it a few more times to get everybody's payments。But it's not obvious。

 So it's a good point。 So computational tractability extends from that of the allocation rule to the payment rule that Myerson wants you to use。

Assuming it's， let's say， a 0，1 environment。Yeah。是。Yes。Right， so the question is。

 can you have an algorithm that computes that in polynomial time。But this is。Right。

 so the question is， so， I mean， just like， certainly， whenever you see a closed form formula。

 you should be optimistic that there's going to be a polynoial time algorithm for evaluating it。

 That's usually a good sign， but it's not automatic。Where would one？The chickening is happened that。

Well， like， I mean， for starters， I didn't promise you there were only polynoially many break pointss。

Okay， but as we said for 0，1， there's only going to be one break point。 So again。

 that's that's suggestive so。Good， okay。Right， best case scenario， okay。So， like I said。

 so approximation algorithms subject studies。How little do you have to relax optimality to recover polynomial time。

And we know a lot about the sort of best possible approximation algorithms for lots of different MP hard problems。

 Really， it's just been unbelievable progress over the past， let's say 20 years on that field。

 We know an awful lot。So here， we're saying exact same question。 Plus。

 there's one more hoop you have to jump through。 You have to be monotone。看。So the best case scenario。

 of course， is that you get the same answer for this problem。

As you do for the easier problem where I don't force you to be monotone。 Okay。

 you can only do better。 You can only get closer to optimal。 If all I insist on is polynomial time。

 then if I also insist on something else monoity。So the best case scenario。

Is to match the best known。Or even better， maybe the best possible， assuming P is not equal to N P。

 guarantee approximation guarantee。Without。Any monoity。Or equivalently。

 incentive compatibility constraint。不对。So this is obviously the best you could hope for。

 this would be the holy grail and algorithmic mechanism design。Okay。

 so we already faced some barriers。Just because of properties two and three。

There's a limit on how close we can get to optimal in polynomial time。

 ignoring incentive compatibility constraints。 And the holy grail would be to prove that actually。

 you don't lose anything more。 Okay you can get incentive compatibility for free。

 And we're a little spoiled right now。 right because for exact surplus maximization。

 that's what we got。We could optimize the thing with these incentive constraints。

 as well as if we didn't have them。 It didn't matter if we knew the values up front or not。

 We could do just as well on the surplus， so。We've been spoiled。

 We want to just demand exactly the same thing， except for polynomial time heuristics for N hard problems。

O。So。That's the high level discussion。Let me make this a little more concrete by returning to Napsackack options。

One thing you should have learned at some point about the NApsack problem。

 in addition to it being NB hard， in addition to there being dynamic programming pseudoponnoal time algorithms。

 is that it's not that hard to come up with heuristics that have provable guarantees。 in particular。

 a very simple greedy algorithm， which I'll remind you of。

 always gets within a factor two of the best possible solution。And again。

 if this is new to you or if you need a refresher， check out the 161 based videos that I'll put up on the course page later today。

So， again， to be clear。Were given as instance， anapsack problem。Specifically。

 we're given bids by bidders， B Is。 We know their size is the W I is， and we have some capacity。

 capital W。 We're punting on maximizing surplus completely。

I'm again going to follow the two step design approach。

 I'm going to assume currently that the bids equal the values。 We'll worry about justifying it later。

And I'm going try to get an algorithm which is really fast， not optimal。

 but not too far from optimal。 that's the point of what we're going to do now。All right。

 so want a quick and dirty knapsack heuristic， like greedy。

 So maybe we just want to go through the items in some order。pickinging the ones that look the best。

So what makes an item attractive or a bitter attractive in an abstractpsack problem。Well， you know。

 we want to maximize the total value。So big bids look good。转。On the other hand。

 we have this capacity constraint。So， small sizes look good。对。So we're going to sort the bidders。

 according to the bang per buck。 Okay， so how much money they get us per unit of capacity they chew up。

对。So these are the bang per buck ratios。嗯。Now， I just do one pass through the bidders。

 bitter one is the first one that we go ahead and allocate the TV ad。

 Then we allocate these guys TV ad。 Then the third one and then so on。 At some point。

 we're not gonna to have room for the next bidder。 Okay， maybe we have three units of capacity left。

 and the next bidder has size 4。 And at that point， we just stop。Okay， say this is good enough。

So pick winners。In this order。Until one doesn't fit。好。I mean， in practice。

 you would for the analysis， you don't even need to bother to do that， okay。And for， and actually。

 for the monoity proof， I think it matters how you implement it。 So let's focus on this。Okay。

 so the question was， you know， what if you reject a bitterder because it has size 4 and you have three capacity left。

 And then later on， there's a bidder that only has size 2。 They're not worth very much。 But why not。

 Why not take them。 Okay， So for this version of the algorithm， actually， as soon as we have a fail。

 we just ignore the entire suffix of the bitterders。 so that's the simpler version of the algorithm。

Now， you know， this is almost good enough。 But actually。

 there's some pathological examples for this two step heuristic。

 If you have one bidder that's both very big and and also very valuable。

 this can actually do the wrong thing。So we're going to have a quick post processing hack。

Just to address the special case of one big valuable bidder。

Which is we return the better of two solutions。And by better， I just mean has a higher surplus。

So return the better， better of the solution we just computed。Soll called it the step 2 solution， or。

The highest bidder。Whichever is better。Okay。So there are cases where the first two steps will give you something that has surplus 17。

 but is's actually just one bidder who bid 22。 Okay， left left out。

 And so then you you pick the bidder who alone has surplus 22 over the one you computed that has surplus 17。

So that's the heuristic。 I hope you've seen this before。 But even if you haven't seen it before。

 I want to remind you what it is。And then what I'm going to stay without proof and again。

 check the videos if you want to proof or check your favorite algorithms textbook is that this is guaranteed to be close to optimal。

In fact， it， it's guaranteed to be at least 50% of the maximum possible surplus。Questions。Question。

Yeah。疗西。C。あそそそ。No， we're definitely we're actually quite focused on surplus maximization。

We're trying to get as close to optimal as possible， subject upon normal amount time。は。

So the next thing I'm going to write down on the board is that this is guaranteed to be close to optimal surplus。

Other question？Sever's clear on what the algorithm is。right， so recall。Output。Has surplus。

This is as usual， assuming that bids equal values。 Okay， which again， we haven't justified。

 assuming that。The output has surplus， at least。50%。Times the maximum possible。

And if you're not impressed by 50%， you can make some extra assumptions， which make it better。 So。

 for example， if all of the bidders sizes is not too big a fraction of the knapsack。

 like if everyone is at most 10% the size of the Napsackack。

 then actually this heuristic is guaranteed to be at least 90% of the maximum surplus。

So this is a well known， very reasonable， super fast， right based almost linear time。

 All you have to do is sort heuristic for approximating the Napsack problem。

So any questions about that。 this， I'm stating without proof this I'm hoping you've seen in the past at some point。

Okay， so again， remember， we're in the middle of this two step design approach。 First。

 we assume that the bids are truthful without justification， and we do something。

And now we have to pay the pipeper。 We have to say， can we actually charge suitable payments？

 And as we know， that boils down to asking， is the allocation rule induced by this heuristic monotone。

So again， what is this， This defines an allocation rule。As input， you get bids。

You run this algorithm， It chooses some winners。 And then as output。

 you just say who the winners of your algorithm were。 That's an allocation rule。

 It might or might not be monotone。Happily。It is monotone。

It's a little less obvious for this allocation rule than the ones we've been talking about so far。

 but it is indeed monotone， and that'll be on the exercise set。And so， of course， by Myson's lemma。

This extends。To an incentive a compatible auction。Which， you know， we might， we might call。

An approximately awesome optionuction。So we knew we couldn't get 1，2 and 3。

 We didn't relax one at all。 Okay， because it's a monotone rule。

 We get dominant strategy and se accountability。 We didn't relax 3 at all。 In fact。

 it's running in O of N log N time。So we knew we had to relax， too。

 but at least we relaxed it by a bounded amount。 At least we still have a mechanism with provable surplus guarantees。

 Again，50% in the worst case， but much closer to 100% under reasonable extra assumptions on the input。

😊，Okay。Now I have a feeling。I sort of lulled you into a state of complacency。Right。

 so far in this class， I've only mentioned one non monotone rule， and it was a stupid rule。 Okay。

 it was the second highest bidder winning in a single item auction。

 which you'd never want to use anyways。So let me warn you， sometimes for some problems。

 there are natural heuristics。 You know， either the first thing you'd think of and or the state of the art。

And they're not monotone。 It's not automatic。 There are allocation rules you would want to use。

But that are not monotone。 And you'll see a couple on the problem set。In fact。

 problem four and the problem that's all about Napsack auctions and a couple of those parts will ask you to verify the non monoity of natural rules that you would like to use。

看。And so this is really why there's been so much interesting work in this field of algorithmic mechanism design。

 If you just ask， you know， how much optimality do we have to give up to get polynomial time。

 we know an enormous amount about that question。 It's a very sort of mature field at this point。

 approximation algorithms。 So if all of those algorithms just gave us were just monotone anyways。

 by Maron's Le we'd be done。 We could have technology transfer of the entire field of approximation algorithms on NAs。

😊，Over to these approximately awesome options。But because so many of them are not monotone。

 That meant we had to go back and either tweak these heuristics or in some cases。

 even redesign new heuristics from scratch to accommodate this extra monotonity property in order to get the incentive compatibility guarantees that we wanted。

 Okay， so that's a lot of the work that happens in this cottage industry around algorithmic mechanism design。

 You revisit wellknown MP hard problems。 You observe that the standard heuristics are not monotone。

 you redesign some new ones， which hopefully are just as good as the old ones。

 but are monotone in addition。Question。Iser ever I relax。Two to get three。

 is there ever the idea of like relaxing one like like the st of surf oxygen isn't explicitly decent。

 but it's close。If you find like you're good。They're closer。surplus。Right， so let me。

 let me give a two part question。 So about relaxing one。

 So you need to be clear on the reason why you're relaxing one。 So as we discussed。

 you should never relax one to try to resolve the friction between 2 and 3。

2 is stripless maxization 3 is polynomial time。 Those are in conflict independent of what in compatibility that you do。

So the question is， why why are you trying to relax， relax one And there the answer is yes。

 there can be good reasons why you might want to drop dominant strategies incentive compatibility Again sponsored search auction don't satisfy that property。

 it's not clear that there's any extra benefit。 it's not clear what they're trading in DSSIC。

 It's not clear what they get in return， except possibly a slightly simpler to describe payment rule。

 but there are other situations where there is a non-trivial tradeoff。

 actually I'll talk about it in this lecture。 So let me wait till that。

 But the answer is not for resolving two and three， but for other reasons， yes。

 theyre well motivatedt ways reasons to relax it。Other questions。Alright， so let me。

 let me just briefly hint at， at a sort of open research question。

 which I haven't had a chance to do yet in the class。

So I talked about how the best case scenario and algorithm mechanism design is to match what you can what we know how to accomplish without the monoity。

 without the incentive compatibility constraint。 And so， you know， obviously， a huge question is。

 you know， can you always do that or in what situations。

Can you achieve the holy grail where you get approximate surplus and optimization for free。So that's。

 that's a basic question。 We really do not understand well in these single parameter environments that we've been discussing。

So， largely open。So are there natural single parameter problems。Where the best you can do。

When you insist only on polynomial time is strictly better than the best you can do if I insist on both polynomial time and monoity。

So what's largely been happening in this realm。Of single parameter optimization problems is people observe that the known approximation documents are not monotone。

 work hard and come up with a new one that is monotone and as good as the old ones。For example。

 for the Napsack problem。You might have learned that not only can you get within a factor two very quickly。

 but you can get within a factor of one minus epsilon。

 where epsilon is a constant of your choosing in polynomial time。

Ponomial in the number of items and one over epsilon。 So you want 99%。

 you can get within 99% in polynomial time。So this problem4 of the problem set will revisit one of those approximation algorithms where you get1 minus epsilon。

There'll be an observation that directly， that that allocation rule directly is not monotone。

 But if you have an extra clever idea， you can reimple it in a monotone way。

 And this is what's been happening in sort of an ad hoc fashion for problem after problem after problem。

So what would be super cool would be just some generic black box reduction。

 So some proof that explained why we keep being able to match the best known approximation algorithms with the extra monoity constraint。

 Maybe there's a single generic method that takes some approximation algorithm。

 not necessarily monotone for a single parameter problem and transmutees it into an equally good approximation algorithm。

 which is monotone。 That would be amazing。😊，Or if such a thing doesn't exist。

 we need to understand why。The best case for a negative result would be a concrete problem where it really explains why you can do better without the monotheistic constraint than with it。

So if you're interested， there's。The state of the art。So these so called black box reductions。

 I'll have more to say about in the winter quarter course for those of you that want to take it。

What we know so far for these single parameter problems。

And these DSSI C implementations we've been discussing。Is a paper。

 I'll put a link to this up on the website。But this is just from last year。

 And stock is one of the two major theory conferences that happens every year。 Okay。

 so this is cutting edge stuff that our understanding is still really quite primitive。 All right。

 so there's a lot that we've figured out in the algorithmic mechanism design。

 There's a lot of really nice， approximately awesome auctions that people have designed。

 But on a more fundamental level， we really don't understand。 in some sense。

 why we've had so much success。Al， one more topic。 I want to discuss this lecture。

 Any questions before them。Oh。Questions。Allright， final topic of the day is called the Revelation principle。

Let me remind you that in addition to the lecture notes which I'm posting also on the website are links to some reading。

 so some textbooks either they are out there or in draft form。

 which give you alternative treatments of many of the topics I'm covering in class， so for example。

 there's a couple links to other treatments of the Re principle for those of you that are interested。

All right。So what I want to do now is sort of drill down on the question that was recently asked。

 which is， what are we losing by insisting on such strong incentive compatibility constraints。

 Weve focused thus far entirely on these DS S I C mechanisms。Now， it was a well motivated goal。

 right， So again， I want to undersell it。 Remember in a DSSIC mechanism。

 it's easy to play as a participant。 it's clear what you should do。 And the good news is。

 from the designer perspective， you have much more confidence in predicting what's actually going to happen。

 You only need a very weak behavioral model。 You just need to assume that bidders play a dominant strategy when they have one under that relatively weak assumption。

 You know exactly what's going to happen in your system。 Okay Furthermore。

 I've shown you a number of examples where we can actually get it。😊。

But it's worth taking a step back and saying， is there any motivation for weakening it in various ways。

Let me actually tease apart two different assumptions I've been making。

 which I've been deliberately conflating thus far。So the first requirement has just been that bidders have a dominant strategy。

 And remember， we haven't talked about this much yet。 But in the first election。

 we talked about rock paper scissors。 You certainly don't have a dominant strategy in rock paper scissors。

 right， We talked about first price auctions。 You certainly don't have a dominant strategy in first price auctions。

 This is unusual。 You need to carefully craft a game for there to be dominant strategy。

So that's the first assumption。So every bidder has a dominant strategy。

No matter what its private valuation is。But I didn't just assume this。

 I actually assumed exactly what the form of the dominant strategy is。

 I assume that actually reporting your true valuation。

 bidding your true valuation is a dominant strategy。 Conceivably。

 you could set up some auction format where you had a dominant strategy， which was different right。

 So just to give a very contrived example， you could imagine a single item a where everybody submits bids。

And then I double everybody's bids。 And then I run a victoryckery auction on those doubled bids。

 Okay， It's a stupid a。 But yeah， I could do it。You have a dominant strategy。

 but it's not to be your actual value， right， It's to bid half your actual value because you know I'm going to double it。

 Okay， so at least in principle， you could have mechanisms with dominant strategies that are different from what's called direct revelation。

Yeah。So this dominant strategy is truthfulbidding。So when you're talking about auction specifically。

 usually you'll say truthful bidding。 if you're talking kind of more abstractly。

 you'll hear this term direct revelation。Meaning you have private information and you just reveal it directly to the mechanism design。

The reason I've now and only now teased apart these two different assumptions is because one of them matters and one of them doesn't。

 Okay and the revelation principle just explains in what way one of them， in particular。

 the second one doesn't matter。ButFirst， let me just talk about the first one。So relaxing one。

So what if you set up a system where bidders didn't have dominant strategies。 And again。

 not a hypothetical question， first price auctions， no dominant strategies。

 They're not always used in practice， but they're sometimes used in practice。Okay。Well。

 we've talked about some of the cons， right， as a participant。

 it's kind of hard to figure out what to do。RightSo you already experienced this firsthand in your participation in first price auctions。

 And then as a designer， if you want to actually try to predict what's going to happen。

 you're on much shakiier ground。 You necessarily have to make some behavioral assumptions stronger than just the bidders play dominant strategies。

 They don't have them。 So you have to make some other assumptions about what they're going to do。

 General， you make some assumption like players are going to play some kind of equilibrium。Okay。

So I need to assume。Wlayers at。equilibrium。Definitely a stronger assumption。Okay。

Eria are not that It's not always easy to figure out what they are。 Okay， from a bitter perspective。

 there are going be many equilibria。 And it's not clear that players are going to be able to figure out how to coordinate on just one of the equilibriumria。

So there are different kinds of equilibrium that are used to analyze systems without dominant strategies。

 The first problem set will give you a taste of a couple of them。So rarely。

 but in sponsored search options， like in problem 3。

 you'll see a situation where you actually analyze Nash equilibrium in the exact sense sense we were talking about with rock paper。

 scissors in lecture 1。In problem 6， you'll get a taste of Bayes Nash equilibrium。

That's something I'll have much more to say about in the winter。

But you make much stronger assumptions as an analyst when you talk about these equilibrium concepts。

 For example， for Bayes National equilibrium， it's usually discussed with respect to a common prior distribution。

 And again， see problem 6 for more details about what that means right。

So these are unsatisfying things。 Okay， You can write down models。 They make predictions。

 You're going to have less confidence in your predictions if you go away for dominant strategies。

So why do it？Well。Sometimes you can actually have systems that perform better than any DS S I C system。

This is not always true。But there are systems of interest。Okay。

Where you get better equilibrium performance。G this again。

 assumes that the system is actually at equilibrium， which is a nontriable assumption。

 but it is possible if you can actually reach equilibrium play to some in some cases。

 perform better than in any DS SIC system。第二。AnyBetter maximize。Yeah。

 it could mean that or it could mean， you know， could mean other objectives as well。Yeah。

So it depends on the setting。 I mean， next week， we'll talk about revenue maximization。

 And then the problems we'll talk about next week。 It turns out there's actually no difference。

But if you look at more complicated revenue maxization problems， again， there's a difference。

 So there's no kind of a universal rule of thumb I can give you about when it matters and when it doesn't matter。

 Okay so sometimes it doesn't。 Most of the cases we'll talk about in this class are simple enough。

 there won't be a big difference。 but in interesting application domains， there can be a difference。

 so to you know， full disclosure， I need to tell you this so。O。Yeah， and again， So C 3，64 B。

 if you're curious about more details there。Alright。

 so now the revelation principle asks the question， answers the question of。

 is it interesting to relax， too。Okay， and the answer turns out to be no。So there's no need to relax。

 too。If you're focused on systems with dominant strategies，2 is for free。 without loss of generality。

Okay。So that's the revelation principle。Let me be more precise。

It's going to be by a simulation argument。By which I mean， you give me a mechanism。

With dominant strategies。That is not necessarily direct revelation。

 where players don't necessarily just review their true value。And I will give you in response。

Another mechanism。That is equivalent in the sense that the outcomes are always the same。

And what that is direct revelation， where all players need to do is report their private information。

And the new mechanism will also be DSSIC。So for all mechanisms， M。

With guaranteed dominant strategies。AndHere by guaranteed dominant strategies， I just mean。

 no matter which bitter you are， and no matter what private， your private information happens to be。

 you have a dominant strategy。So for every such mechanism， there exists。呃。An equivalent。

Direct revelation。TheSI mechanism。And prime。OK。So you give me M dominant strategies。

 not necessarily direct revelation。 I'll give you back M prime， which is direct revelation。So。

 the proof。Its by a simulation argument。So you give me M。

So my assumption there's always dominant strategies。So for a bitter eye。

 when it happens to have the private valuation V sub I， it's got to， by definition。

 have a dominant strategy。 Let's call it S I of V I。对。So then we're going to have M prime。

And M prime is just a front end。To M。Which is responsible for playing the appropriate dominant strategies in M on behalf of the players。

So players show up。They have whatever private valuations they've got， V1， V2 up to VN。

They tell M prime， hey， M prime。Here's my private valuation。Okay。And Prime says， oh， well。

 in that case。I， if your private value is V I。I know you've got this dominant strategy。 S I of V I。

 you should be using an M。 Yeah， let me just do that on your behalf。

So M prime takes these as sealed bids， if you like。And then in the guts of M prime。

It just reports the appropriate。Dominant strategies to M。M is none the wiser。 It just gets as input。

 these strategies。 That's one of V1 through S N and V N。 It computes some outcome。

Which M prime happily refers。So M prime leaves the outcome unchanged。And if you think about it。

Direct revelation。Ass a dominant strategy， always。And M。Right。So if you're a bitter eye。

 your private information is V sub I。 By definition， you want to do S I of V I in M。

 It's never a bad idea， okay。And the only thing you can do by misreporting V I is by confusing the mechanism M prime and getting it to submit the wrong thing to M。

 Okay and you don't want to do that because S I V is a dominant strategy in M。 Okay。

 so that's what's a dominant strategy。 Just report V to M prime。不。So that's the revelation principle。

 specifically， this is the revelation principle for DSSIC mechanisms。

 Other incentive constraints have their own revelation principles。 So in the winter。

 when we'll look at Bayes Nash implementations， again。

 you're making an assumption when you say I'm going to assume this system at a base Nash equilibrium。

 but you're not making an important assumption when you say， oh， and by the way。

 I'm going to focus on the equilibrium where bidders report their true value， at least in principle。

 that in practice， there might be reasons to use non-direct revelation mechanisms。

 I ask you to think about that on the second exercise set。 but at least in principle。

 it is without loss to ask for a direct revelation mechanism。

 you lose no power as far as what you can or cannot do。On Monday。

 we'll start revenue maximizing auctions。 Have a good weekend。 See you then。

