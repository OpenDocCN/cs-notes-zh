# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p02 -02-2_ Mechanism Design Basics).zh_en -BV1VmC2YzEXJ_p2-

So let's go ahead and get started for those of you just came in。

 if you didn't have a chance to sign up Monday， sign up sheets are going around。

 if you did sign up Monday， of course you don't need to sign up again。

 so I'm going to go ahead and start with the lecture material I'll pause at a couple places for some course announcements。

 but I want to get started by giving you an introduction to mechanism design。

 remember as discussed on Monday mechanism design is in some sense the science of rulemaking and the overarching goal is to design systems which have strategic participants but nevertheless perform well。

The sensible place to start a discussion of mechanism design is single item option。

So here's the setup。There's a seller， and the seller owns one good。

I bought an iPhone 4 S almost two years ago。 Maybe it's time for me to upgrade。

 Maybe I want to auction off my 4 S phone。If you like， think about an ebay auction。

 Those are single item options。There is some number of players or bidders potentially interested in buying the good for sale。

And we're going to want to make statements about how bidders behave in different options。

 depending on the option rules。 So we need to have a model of bitterder behavior。 And for that。

 we need to have a model of what bidders want。So the first key concept is that of evaluation。

So each bitter eye。Has evaluation。It'sDe noteded V sub I。

And the valuation is the maximum amount that I would be willing to pay for the good for sale。

 So maybe for my iPhone 4 S， there's some bitterder out there and it's willing to to pay up to $90 for my iPhone 4 S。

 Of course， subject to buying it， it wants to get us as cheaply as possible。

 but it doesn't want it at all。 if the price is bigger than its valuation in this example，$90。

So that's evaluation。 How much you're willing to pay for the item。

And what's really important and what makes the auction design problem difficult is that this information。

 the valuation， it is what we call private to bitter eye by private。 I mean。

 the seller has no idea what it is。 In some sense， that's the reason you're running the auction because you don't know what people are willing to pay。

 And we're also going to assume that the other bidders do not know the valuation of bitter eye。

 In that sense， it's a private valuation。So now let me tell you about what a bidder wants formally。

 So I'm going introduce a utility model。And we're mostly going to stick with the simplest sort of first cut。

 most natural utility model you might use in such in an auction setting。

 It's called quasilinear utility。 It's not really important。 You know that term。

But you might see that in the textbook， for example。And all it means。

Is that if you're a bidder in this auction and you lose。Your utility is zero。Your utility of winning。

Well， it depends。 First of all， it depends on your valuation。

 What is the most you would have been willing to pay for it。 Second of all。

 it depends on the sale price。 What you actually had to pay for it and your utility is just the difference between those two quantities。

Yeah。对。So that's a definition，For most of our discussion of mechanism design， when we have money。

 all of the auction discussion， we will model participants as acting to maximize their quasi linear utility。

 We will model them as wanting to maximize this quantity。I want to focus today， on。

A very simple type of auction format， sealed bid auctions。These work as follows。

The first thing that happens is each bidder submits a bid to the seller， to the auctioneer。Oh。

Privately in a sealed envelope， if you like。Now， the auctioneer or the auction designer has to make two decisions。

 Okay， First of all， so given the bids， and they have N bids from the people who are are vying for this good。

 First of all， which of them gets it。Second of all， what do they pay。Yeah。Now， for step 2。

There's a pretty natural choice to make。So what do you think， You get these N bids from everybody。

 You have to pick somebody， or if you want nobody， that's allowed。

 But a most one person to win the good。What seems like the obvious thing to do？So。

 the highest bidder。Right everybodybody said what they'd be willing to pay。

Pick the one who said they'd be willing to pay the most。And we'll see later。

 sometimes there are reasons you actually don't want to do that。 But for today。

 we're only going to focus on options that。Indeed， award the good to the highest bidder。Oh。

So all optionsuction we talk about today will have that property that indeed。

 whoever's the highest bidder gets the good。Now， step 3。Deciding what to charge the winner。 Well。

 again， perhaps one natural thing comes to mind。 it's actually。

 there's a bunch of reasonable things you could do in step 3。And in fact。

 the behavior of the bidders will be very different depending on the decision。

 on your implementation of step 3。Here's a trivial example。 What do you want to try to be altruistic？

Okay， you said， you know what， I'm not going charge the winner anything。 You know。

 I just want to sort of figure out who wants it the most。 And I'm just going give it to。Okay。

So who wants to volunteer， So imagine you were actually participating in this auction。

 So who wants to volunteer how they might， what bid they might submit into this auction。Okay。

 suppose it had to be a finite number。Yeah， so you'd be tempted to write something like one more than the highest other bit。

 or in general， you write down just the highest number you have time to write down in your envelope。

Okay。I'm sorry。Something like this， yeah right， so you ought to do your best so basically you name the highest number you can think of。

 the winner is simply who could name the highest number。

 has nothing to do with how much they actually wanted the good。

 has nothing to do with their valuation。So that choice of step  three does nothing to discourage people from overbidding。

 Okay， so there's an incentive problem。All right， so that's obviously a bad idea if you want to have the allocation of the good correlate with bidder's valuations。

So another very natural idea， and indeed， an idea that。Is reasonably prevalent in practiced。

Is the first price auction。And the way I sort of told the story so far。

 this is probably the first thing that we come to mind for most of you。

 What do you charge the highest bidder？ Well， they wrote down what they'd be willing to pay。

 So just ask them for it。 So just have them pay what they bid。

And the main thing I want to tell you about， the main thing I want to convince you of today about first price auctions is that they are nontri to reason about。

 even if you're a single participant in a first price auction， that's nontri to reason about。

 And certainly as a designer thinking about a collection of participants in a first price auction。

 it's nontri to reason about。 So to drive this point home， we're going to do an experiment。😊。

And this experiment is only for those of you that are officially registered in the class in access。

 and you'll see why in a second。 So if you are officially registered。

 get a slip of paper If you don't have one， borrow one from a neighbor。Yeah。Yeah。Yeah。Yeah。

I'm going to give you an opportunity。To earn a little pocket change。As you attend 3，64 a。

So here's what I want you to write down。On your slip of paper。给。So first of all， who you are。

Second of all， your birthday。Okay。There's gonna be five things to write down。

So you don't want to lie about your name because then we won't be able to give you your money on Monday。

 okay。Condition on your name， we can verify your birthday。

 That's why I want only for the people who are registered for the class。

 So don't try long about number 2。The reason I don't want you to lie about your birthday is because your valuation is going to be a function of your birthday。

So I'm going to define your valuation。As the two digit number of your month， your birth month。Plus。

 the two digit number of your day。Times， 10 cents。So， for example。

 the biggest valuation you can have。You were born on the last day of the year。

Your valuation would be。12 plus 31 times 0。1 or $4。30。If any of you are New Year's Day babies。

 then your valuation is only 20 cents。Now， the fourth and fifth things I want you to write down are bids。

The way this is going to work is we're going to collect all of your slips。

And we're gonna do two experiments。 in the first experiment。

 we're going take each registered student and pair them randomly with another registered student。

And we're going to run for each of these pairs。 And you'll participate in exactly one pair。

F each of these pairs will run a first price auction Okay。

 so there'll be two bidders and one thing for sale。

 the higher of the two bids will win and the utility I。e。

 what you'll get paid next week is your valuation minus what your bid was。 so that's experiment one。

Experiment two will put you in a group of three。Randomly。And we'll do exactly the same thing。

 We'll run a first price auction。 Only one of the three bidders will win。

 and that bidder will again get paid on top of whatever they earned in the first experiments。

 their value minus their bid。If you want， you're welcome to write down the same bid twice。

 you can bid the same way with two players， with one a competitor， as with two competitors。

 that's fine， or you could perhaps see a reason to bid differently in the two different experiments。

In any case， spend some time thinking about what those two bids should be and write them down on the on the slips。

 We'll collect them at the end of the class。你将你。There's only one round to this。Excuse me。This is 430。

 so it gets multiplied by 10 cents。The biggest evaluation could be is$4。30。

I had to put a budget on this experiment。I realized this is only pocket change for a bunch of Stanford engineering students。

 but。You know， I hope that some of the competitive fire nonetheless。

 compels you to think carefully about what to bid。はまさ。

Any other questions about what the experiment is？Or what I want from you？Yep。Question。勉こで。

Could you speak up？Can we be nasty and develop some horrible amounts that you have to give out lots some smoking？

How would you do that。So that does it might not think about。U。Do what you will。Other questions， y？

The this。I'm sorry。U。Yeah， if you promised register after class， you can do it。Other questions。

経タというのがあり。还有点。Good question。 Good question。 Notice。

 Notice that if you win an auction at a sale price higher than your valuation。

 then utility is actually negative。 So in the context of this experiment， you owe me money。😊。

And I do expect you to pay up， and if you don't， you can expect a penalty on your point total。Really。

 what I'd encourage you to do strongly is don't bid higher than your valuation。But you are free too。

 if you want。Yep，やな。是的。Good。You get some utility from。Arguably not。

 arguably there's some price at which you are indifferent between not winning and winning it at that price。

So ties I mean， ties will flip a coin。So general， in general what we all this stuff we discuss about auctions。

 it won't matter how you break ties for concreteiness for these experiments。

 we're going to choose randomly amongst those with the highest bid。Okay。

So a couple other announcements。So first of all do keep an eye on the web page。

 there's been some updates。 So for example， the video for the first lecture is now up on YouTube there's a link from the website so go ahead and check that out。

 know they'll go up whenever they go up， but I'm hoping generally it'll be at most a few days after the lecture There's also a very rough draft of lecture notes for the first lecture。

 those will frankly be a little bit more erratic in the timing that they appear on the webp page so don't count on the lecture notes being too prompt the videos I hope will be reasonably prompt。

Also posted as the first exercise set。To remind you from Monday， there are two types of homeworks。

 exercises and problems。 Excis are supposed to be easy。

 They're just supposed to fill in things that I've glossed over in lecture。

 You might even want to do them quite quickly after the lecture。

 I think you'll find them straightforward。 If the lectures themselves made sense at the time。

 So this has already been posted problem set number one problem sets are the ones with openended harder problems。

 which you should do in groups of up to three， one right up per group。 The problem set is written。

 but I'm still proofreading it。 So that'll be posted later tonight。 That's doing 16 days。

 So the exercise set。 This is the easy one， doing seven days， the harder of one do in 16 days Que。

For the web。待会。So four you are randomly matched with one another student。

 the one who bids lower has utility zero， the one who bids higher wins in the utility。

 which is what you are paid next week， is your value minus the bid that you submitted。Yeah。

So ties will break randomly。We collaborate on the exercise sets as well。So see the instructions。

 I listed specific instructions on the exercise I said about collaboration。有。

S turn the slips of paper at the end of class to one of the Ts who to remind you are Oka and Coss in the back。

你不要这边。Yes。定。Iically all。That。Yes。Yeah， so。Yeah。Okay。

 would you like to turn them in now Would that answer the question， We can do that， too。Yeah。えかさ。

Okay， so the rule is they do it the end the class。That's all I'm going to say， okay。

Other announcements。 Yes， there is another announcement。 So because the class is being videotaped。

 I have to sort of interrupt for an announcement from the Stanford legalgal Department。

Everyone actually has to sign a release。What the release says is that either you can that you。

 your face might show up on a video on YouTube name in this class。 or if you're not cool with that。

 then you agree to sit in some part of the room， which is off camera。

And so there's lots of the room which is off camera。

 actually almost none of you show up on the video and you also agree that you'll save questions till after class okay so those are the two options but I do just you know they've asked me to have everybody sign one of those release forms because the class is being videotaped。

Okay， so I'm not gonna say anything more about first price auctions。

 There is interesting theory about first price auctions。

 You will see a glimpse of it on the first problem set。

 And for those of you that take the SQL course to this in the winner。

 we'll talk about the theory More about analyzing first price auctions。

 But the right place to start is with a different auction format。

 also very common in practice called the second price or victoryy auction。Yeah。

How many of you have ever bid in an auction on ebay。Good。So let me ask you a question。

So what happens when you win in an auction on ebay？ So， for example。

 maybe I'm bidding on someone else's iPhone 4 S。 and maybe I bid， you know， say 100。

And suppose I win。Do I necessarily pay $100 for that iPhone。我是。No。I don't， right。

So ebay is not a first price auction。 and a first price auction。

 I would have to pay my bid of 100 every time I won。So why， what do I pay instead。

 If I don't pay what I did， what do I pay。Pay the minimum of your bid and。啊。

One does the minimum price implement over the。Right， so to first order。

 what you have to pay is you basically pay the minimum amount necessary to beat out all of the competition。

Okay， so your closest competition is the second highest bidder。

 So if the next highest bidder bid $90 and I bid 100， I'd only have to pay 90。 Okay，91。

 there's this increment。 But the first order， what I pay is not my bid， the highest bid。

 but just the highest other bid， the second highest bid overall。

So what I want to talk about next is exactly this。 The second price auction。

 I don't want to talk about exactly the same thing that's run on ebay。

 I want to talk about a sealed bid auction。 There is a problem on the exercise set asking you to compare and contrast to the exact ebay auction format with the sealed bid a format we're going to talk about right now。

 So to be clear， right now， we're talking about sealed bid auction。 Each bidder submits their bid。

 The winner is the highest bid and the price the winner pays is the second highest bid。

 That's a second price auction also called the Viy auction。Now， the second price auction。

 in contrast to the first price auction， is easy to analyze， both in the sense that as a participant。

 it's easy to figure out what you should do。 And secondly， as the designer。

 it is easy to predict what will happen。So let's make that precise。So here's the key insight。

My victory。So this claim makes precise how each bidder has an obvious optimal strategy in a second price auction。

By obvious， formally， we meet a dominant strategy。namely。To set its bid。

 to be its actual true valuation v sub。What I mean by this being a dominant strategy， I mean。

 amongst all the bids bitter I could submit。No matter what the other bidders are doing。

 this bid is guaranteed to maximize Is utility。The reason this is such a breath of fresh air for the bidder is because this guarantees you do not have to reason about what the other bidders are doing。

 You don't care how many other bidders there are。 You don't care if they're bidding their values or if they're bidding in some complicated way doesn't matter。

 whatever they're doing， you should just bid your true value。 It's guaranteed to be optimal。

 Obviously， that's different than the thought experiment I just made you go through for first price auctions where。

 of course， you don't bid your value。 If you bid your value in a first price auction you are guaranteed zero utility。

And a first price auction， you always bid less than your value。

 The question is by how much And the answer to by how much depends on what you think other people are bidding。

 That's the contrast to the second price option and this guarantee that's independent of how other bidders behave。

So this is one of those great mathematical statements that is both really interesting and really easy to prove。

So let's talk about why it's true。有。Cs 364A。Yeah。Why do you ask？啊，是。不。So， proof。

So pick your favorite player eye。I don't care which。The valuation is whatever it is， Vi sub by。

And I also need to fix what the other bidders are doing。

 because I'm not supposed to care what the other bidders are doing。 That can be arbitrary。

This may be your first exposure to a bit of very common， but also rather wonky notation。

 B minus I refers to the bids of everybody other than I。

 So this is just a vector with the I component deleted。 Okay， so that means what everybody else did。

So what do we have to show？You have to show that， no matter what I is。No matter what VI is。

And no matter what B minus I is。You need to show that I utility。Is maximized。By bidding。Vs sub by。

Okay。So just to be clear， the valuation of a bidder is not something that it chooses。 right you。

 in some sense， are born with your valuation。 That's what you， that's how badly you want this object。

 The bid is what you get to choose。 So what this is saying is you may as well set your bid to your valuation。

 That maximizes your utility， yeah。す。It's the bids of all players， except for that a buy。So。

 we're just going to compare。To the highest other bid。 So I'm going to call that capital B。

So B is the largest bid by one of I's competitors。Okay。Now here's what's special。

About a second price option。What's special is that even though there's a zillion different bids that I could submit。

Only two different things could happen。So I utility can only be one of two things。In one case。

It bids less than capital B。What is its utility in that case？Z， it loses。Or。

What if the bids at least the highest other bit， Let's say strictly greater than the highest other bid。

What's its utility。Yeah， so it's， it's value for winning。 So then it wins， right。

 then it's the highest bid。So it's its value， minus the price that it pays。

Because it's a second price auction， the second highest bid， assuming B I is the highest。

 The second highest bid is capital B。And this is just already totally not true for a first price auction。

Okay， what would I have to write here。In a first price auction， I have to write something different。

 What would it be。V I minus B， I， Okay， because the price would not is not the second highest bid。

 capital B， but rather I bid itself， B sub I。 So its utility in that case would be V I minus B I。

Okay。So that's really nice。 There's only two different things that could happen。Alright。

 so that's just sort of an observation。 Remember what we need to show。

 We need to show eyes utility is always maximized by bidding truthfully。So there's just two cases。

There's the case where the amount I would be willing to pay Vi by。Is at least capital Bs。

 at least the highest of the bid， and the case where it's not。So first， suppose that。

The maximum that I is willing to pay。Is less than capital B。

What is the best case utility for I in these two cases then。It can't do better than0。 right。

 If V I is less than B， this is a negative， that's a 0。Okay。So， in this case。

Max possible utility over all bids it could submit is equal to 0。 And in particular。

 if it does bid its true value， it will lose and it will have utility 0。Okay。

 so it is an optimal thing to do in this case。To's check the other case。

When VI is at least capital B。So now what's the max possible utility that I could ever get。

So if V I is at least B， then this quantity is the better of the two。Okay。

 so this is the best utility that could achieve。And again。

 it does achieve that utility when it is truthfully， when it sets B I to B V I。OK。

And so since the bid I， it's valuation V sub I and the bids B minus I will are arbitrary。

 This concludes the proof。Doesn't matter which player you are。

 It doesn't matter what your valuation is。 Does't matter what the other players are doing。

 Big your value。 You're guaranteed to maximize your utility。And again， clearly not true for， say。

 a first price auction。So that's the sense in which second price auctions are unusually easy to participate in。

Let me just point out another。Very easy property to see。

Which is you will also never regret participating in a second price a。

 At least if you do the obvious thing and bid truthfully。So I claim that in a second price auction。

Every。I'm going to call it a truth telling bidder。 That just means you set your bid equal to your value。

 as in this dominant strategy。Every truth telling bitter。Gets non negative utility。Obviously。

 it might be 0， in particular， if you lose， it's going be 0。

 but it's never going to be negative if you bid your true value。Do you see why that's true？

And I want to suggest a sort of simple proof of that property。So who is at risk。

 Who's the only possible bidder that could have negative utility。The winner， right。

 Everybody else is 0。What does the winner pay。Second highest bid， by definition， right。

 and by because it was the winner。 it was the highest bid。And because it's telling the truth。

 its bit equals its value。So it pays something less than its value or at most its value。

 So that means its utility is non negative。So proof。It's simply because of the selling price。

Is no more。Then the winners bid。对。All right。So that is the second price or victoryy auction。

 and probably its most important properties。So in both the exercise set and the problem set that are going out today。

 I'm going to ask you to sort of explore around the Vic reaction in this theorem a bit so you can prove something a little bit stronger so while it's not the case that the bidding the true value is always in every situation。

 the unique best bid you can prove it's unique in the following sense。

 if you submit any bid other than the true value， your true value。

 there will be scenarios where it comes back to haunt you there will be scenarios where your utility is not as high as it would have been if you would bid your true value。

 So in that sense， bidding your true value is the natural dominant strategy in a VCory I'll also ask you to consider an extension where you have not one item but multiple items and so on。

Good。So what， if we take a step back。We've proved the following theorem or sort of a meta theorem。あ。

Which is that the victory is awesome。By which I mean。

 it achieve simultaneously a number of quite different， but all quite desirable properties。

 The one I've focused on so far are the incentive properties。

 the fact that bidding truthfully is a dominant strategy。It also， as we'll see。

 has a performance guarantee， in some sense， solves the optimization problem that we would have wanted to solve our priori in giving the good to the bidder who wants it the most。

 And thirdly， it is。Obviously， to this audience， a computationally efficient auction。

 There's no obstacle to running this in practice。Let me just write that down。So by a。

 I mean three properties。Good incentive properties。 And there's a more。Foral term for this。

Dominance strategy。Incentive compatible。Or D S。What does this mean formally this just means？

What we just proved in claim one and claim two。Okay。

 that's what that's what dominant strategy and compatible means。

 It means bidding your true value is a dominant strategy。 And if you bid your true value。

 then you're guaranteed not negative utility。What are the performance guarantees。 So， okay。

 two things。 First of all， this is really strong。 This is great。 All right。

 So we want a reason about what happens in systems with strategic participants。

 Any such theory has to make behavioral assumptions about how bitterders behave。

 The weaker the bitter， the weaker the behavioral assumptions we impose。

 the more plausible is the prediction are theoretical prediction for what happens in that system。

 When you have an a like this， which is dominant strategy instead of compatible。

 the only thing we have to assume， and it's still an assumption。

 but it's a relatively weak assumption is that when a bidder has sort of a natural。

 obvious dominant strategy， then they will play that strategy。 So when you have a decent a。

 that is the background behavioral model that you assume。 and that's about as weak as it gets。😊。

So we're very happy when we have this kind of incentive properties。 Now， of course。

 this isn't enough by its own right。😊，You could have an auction that simply always held the item and never gave gave it to anybody。

Okay， strictly speaking， now would satisfy this property wouldn't be very interesting。

So the second part of the story about why this is an awesome auction is that it maximizes the social surplus。

Meaning it awards the good to the bidder who has the highest value。So formally。

 if bidders bid truthfully。And by property  one， we have a reasonable conviction that they should bid truthfully。

あ。Then the auction。Maximizes。Well I'm going to call the social surplus。Which， by definition。

 is just the sum of the values of the winners。Okay。Now in a single item auction。

 there can only be one winner。 So it's just the value of the winner。No， I mean， VI evaluation。Okay。

So what I mean is the sum over the bidders of V I Xi。

 where Xi is just an indicator of whether I won or lost the auction。唔。So this is the claim。

 the vi auction maximizes this sum。Where the meaning of X I is just one was a winner in 0。

 it's a loser。 Now， I've written it in sort of a more general notation that I need to just to move forward。

 But remember， by there's only one copy of an item。 So X I is one for one person and 0 for the rest。

 So this is just the value of the winner。 So what I'm claiming here is that the highest valuation bidder wins in the di reaction。

Assuming that all of the bidders report their true valuations。Why is that true？Well， by definition。

 the victoryckery auction selects the winner the highest bidder。

If everyone's bids equals their valuations， then the winner is the bidder with the highest valuation。

So that's all I'm saying right here。But this is also really cool。Right because remember。

 these Vs were private， What people were willing to pay。

 We had no idea what they were in the first place。 That's why we were running the auction because we didn't know what this was worth to people。

If we had known。Maybe our objective， one reasonable objective would be to make sure the item goes to the person who wants it the most。

 We just didn't know who that was up front。And this simple vi reactionaction protocol。

 despite all this information being private ai。 at the end of the day。

 it solves that optimization problem as well as if the data was public， as if we did know it upfront。

Okay， so that's a very nice guarantee。This optimization problem。

 we might have wanted to solve our priori。 We didn't even know the data。 We didn't know the V Is。

 And at the end of the day， we get the solution， the optimal solution， surplus maximizing solution。

Yeah。That这个需要。It depends。 We will talk about revenue maxims， as well。The question was。

And some surely in some contexts， you care about revenue。 the answer is yes， sometimes you do。

 Sometimes you actually do care about surplus。 if you're in a highly competitive environment or for any government auctions。

 this is more the first order objective。 but we will cover revenue maximization in a couple weeks as well。

So those are the two really key properties。 We simultaneously get these super strong incentive properties。

 dominance strategy， incentive compatibility， and this great performance guarantee that we get optimal social surplus。

 and we also don't have to work that hard to do it。😊。

Right all we have to do is identify the highest bit。 So it's a linear time auction， if you like。

And as far as where we're going next。Sort of the overarching question will be， you know。

 can we have analogously awesome as for other and more complex situations than just social surplus and single item options？

Sometimes the answer will be yes。 Sometimes the answer will be no。

So what is the motivation for trying to generalize this， What we already mentioned。

 we'd certainly also like to understand revenue maximization。

That is certainly sometimes the chief objective for people who are running auction。

And we will discuss it。The other thing is， sometimes just the goods we're trying to auction off。

 We don't just have one。 It's a lot more complicated。 Okay。

 so we'll actually get into such an application next。

When I start talking about sponsored search auction。

Another case study we'll do in a couple weeks is when we talk about wireless spectrum。

 Okay it's lots of different goods， and they're not necessarily all identical。

 So it's much more complicated to figure out how to allocate them to a bunch of bidders。

 And the question is， as we go to these more complicated， but extremely important applications。

 can we have these three properties simultaneously or not。Okay， let me pause for questions。

 Coming up next is sort of a brief case study of sponsored search options。

 So it is a natural time to take questions。对。我直过这个。It's just a。 It's just a name。

So that's just what it's called。Yeah， so quasi utility just means you want to maximize the value for what you get。

 minus the price for what you have to pay for it。 It's just a definition。Other questions？

If we're this is for the experiment， oh， let's experiment questions for afterwards。Other questions。

よしから。Excellent point。 So the question was， what's up with collusion in the Viy a。

 So what if bidders don't behave unilaterally， but rather form groups。 So that， in fact。

 is one of the questions on problems at number one。

 asking you to explore in what ways the vi A is vulnerable to collusion。

Designing collusion resistant auctions turns out to be a quite tough problem。 And the theory。

 I would say， is not very advanced。 and there's a lot of actually impossibility results。

 So in practice， if you look at how people hand a collusion， it's usually more through legal means。

 So rather than try to design an auction， which is intrinsically robust to collusion。

 because very few such auction formats exist， you actually just kind of go outside the model to make sure that it's very difficult for anything more than very small collusion coalitions to form。

Yeah， good question。Any other questions？Cool。All right， so， so， you know。So why， you know。

 why ist this victory enough， right， So is the rest of this just going be theory for theory's sake。

 How general can we make it。Well， absolutely not。 Okay。

 so the next application I give you about a more complex a format。ItI mean。

 has just been a jaw droppingly jaw droppingly large fraction of the Internet economy。 Okay。

 so let's talk about sponsored search options。不不。So， for example， around 2006。

These auctions were responsible for roughly 98% of Google's revenue。Okay。

 so now they have lots of different advertising streams。

 but we're still talking tens of billions of dollars a year generated through the auctions I'm about to tell you about。

So what are these。こ。Well。To tell you something， I'm sure you already know。

When you go search on some query in a search engine。What comes back。Two sets of results。Okay。

The format can look a little bit more complicated than this sometimes。

 But let's just say there's two lists of links that come back when you search for， say， camera。

So first， there are so called organic search results。

So these are URLs that the search algorithm has deemed by some algorithm like page rank or variant to be deemed relevant to your query。

And initially， in the early days of the search engines， this is all there was。

 All there was was the organic search results。And then sort of early 21st century。

 people realized it could be a very good idea。To also allow people to pay， to have links to say。

 their own landing page shown along with the organic search results on the search results page。

So these are the sponsored links。So this is advertisers submitting bids to the search engine for in。

 in effect， purchasing this real estate on this search results page。

OkayEvery time you search for a query on a search engine in real time。

 one of these sponsored search a is run。 Okay， so we're talking probably millions。

 if not billion of these being run every single day。In the background， you know。

 there's some interface by which as an advertiser， really anybody can bid on these keywords。

 Okay so the system just stores which advertisers have bid on which keywords when a keyword gets searched on that pool of advertisers get entered into an auction automatically。

 and it is somehow， as I'll describe， decided upon which advertisers gets shown on the page and in which order and what they're going to pay。

Okay。This is no longer a single item option。What are。There's not only one slot for sale， right。

If I was only going to have one slot， one advertiser shown on this page。

 it would be a single item option。 Okay， But as you recall， in general。

 you have many sponsored links， okay。So it's not immediately a single item option。

 We can't immediately use a second price option。Moreover。Not only are they multiple goods。

 but they're not interchangeable。 They're not all the same。Why not？Feel free to just shout it out。

Different pieces of real estate are more valuable than others。 And in fact。

 as most people track from top to bottom， the higher the slot that you're awarded。

 the happier you are， the more likely you are to get what's called a click through the person actually clicking on your link。

 So there's multiple goods。 And they are not all the same。

 So those are two senses in which this is more complex than the single item options discussed so far。

😊，So these are often called slots in this context。 So the goods are decay slots。On the results page。

You know， different keywords very dramatically as far as how many people care about them。 But。

 you know， for some concrete numbers， you might think about there being8 slots。 So K equals to8。

 and there could be， you know， say， 100 bidders and equals to 100 vying for those eight slots。有。

Just assuming right now that our universe has like one keyword。So this is the format。 I mean。

 so every time that， you know， so an auction of the format I'm going to describe is run every time something is searched on。

 So there is a universal a format， no matter what it's searched on。

Their parameters get that get tuned that depend on the search word。 like what's the reserve price。

 eta， et cea， cetera。 But there is this。Search independent auction format。

 And that's what I'm describing now。Okay。So those are the goods。Who were the bidders。

These are the advertisers。Who have bid。On the query。On the current query。Okay。

 so this set of bidders， who these bidders are， of course， depends on what the query is。 right。

 If I search for you know， station wagon， it's gonna be one set of bidders。

 the bidders that care about that search query。 If I search for camera。

 it'll be a totally different set of bidders who have bit on that particular keyword， okay。All right。

And as we said。These are not identical goods。And generally speaking， higher on the page。Is better。

Okay。So we're gonna have a pretty simplistic model of how this goes on。

 But it's actually been a very influential， simplistic model。

 It really has guided a lot of how these search options have evolved over the past now。

 almost 10 years。So。A key note。 So O， so we need to explain or quantify the extent the way in which one of these slots is better than another。

 So that's done using parameters called click through rates。So alpha J is going to be the notation。

For the probability。That whoever typed in this search the search query， is the probability。

That they're going to click on the link in the Jith swap。Okay。

 so this is called a clickthrough rates。If you like， it's the fraction of impressions。

 the fraction of the number of times that your ad has shown that it actually results in a clickthrough to your landing page。

Or CTR。Obviously， a higher alpha means a better slot， a more desirable slot。

Here are the assumptions I will make about the clickthrough ratess。As we've already said。

 higher is better。 Okay， so slot 1 is the top most。 That's also going to be the highest CPR。

So the alphas only get smaller as you go from top to bottom。

 And that's a pretty uncontroversial assumptions。 It's not perfect， but it's really quite reasonable。

Let me now give you an assumption， which is unreasonable。

But it's actually very easy to extend everything you're gonna to say to a much more reasonable version。

 And that'll be on the second exercise set。So， the unreasonable assumption。

Will be that the clickthrough rate of slot J doesn't depend on which advertiser you put there。Yeah。

So if you had a bunch of companies that were basically interchangeable。

 this would be a reasonable assumption。 If you had。

 know two companies with very different reputations。

 then you'd expect the clickthrough rate to also depend on the reputation of the company that you put there。

 but it's easy to introduce a second set of parameters that are specific to the advertisers so that the clickthrough rate is just the product of those two parameters and everything that well say will continue to extend。

 so this unreasonable assumption is for convenience only。The third assumption。

Is that what an advertiser cares on cares about is not one of these slots per se。 That really。

 what an advertiser cares about is a click through。

 We're going use that as our unit of measurement for what advertisers care about。 cares about clicks。

 So to have a valuation， a private one like before Vi sub。

 which is what it we be willing to pay for every click to its landing page。So as a consequence。

 so if you have an advertiser I with this per click valuation V sub I and you put it in slot J。

What value does it derive from slotlotje。The product， Okay。

 it's value per click V sub I times the fraction。 The probability expects to get a click alpha sub。

2 right。So that's the model。 Those are the assumptions。Any questions about that？

So now we're gonna to ask the same question we did with a single item auction。 S item auction。

 We had maybe like 10 bidders who wanted this one iPhone。

 We had to figure out who wins and what do they pay。 Now。

 we've got maybe 100 advertisers vying for these8 slots of varying qualities。

 We have to figure out which8 of the 100 do we choose。 What order do we put them in the slots。

 and what price should each of them have to pay。And the question is。

 can we have an auction as awesome as the victory auction for this more complex setting？Okay。

So what does that mean？So first， if possible。It would be great if it was a dominant strategy incentive of compatible a。

 Again， what does that mean， that means reporting your true value per click is a dominant strategy。

 And secondly， if you report your true value， you're guaranteed non negative utility。

Why do we want that property， if possible， First of all， as a participant， it's easy to play。

 You have an obvious strategy。 Secondly， as the manager of this system。

 you have a much you have a pretty strong prediction about what's going to happen。

 You expect people to bid their do their dominant strategies。 You expect truthfulbis。

 You can reason about the behavior of your system。But the other thing the Viy Auction did is it solved an allocation problem optimally。

 It gave the item to the person who wanted it the most。 So we'd， again， like that property。

 a performance guarantee saying that after the fact， even though we didn't know valuations up fronts。

We have an allocation which is just as good as if we did know the valuations up front。So so for now。

 we're going to again want to maximize social surplus。I'm again。

 going to write it as a sum over the bidders。 I equal1 to n of the V I times Xi。

 Xi semantics are now different。And avic option， X I was just one or 0， whether you won or lost。 Now。

 X I is the fraction of a click that you get in your slot。 Okay。

 so if this bitter I winds up in the first slot， it gets alpha 1 of a click。

 So X I would be equal to alpha 1。 if it winds up in the second slot。

 It's X I would be equal to alpha 2， because that's how much stuff it gets。

 It's what fraction of a click it gets in this particular allocation。So， where X I。Is the CTR。

Of the slot。I get assigned。Now， of course， in this example with 100 bidders and8 slots。

92 people get no slot at all， and their X I， of course， is 0。Okay。And of course。

 when I say maximize social surplus， maximizes quantity， I mean subject to feasibility， okay。

 so you can't put more than one bidder in the same slot。

 so subject to at most one person in the top slot， one person， the second slot， and so forth。

And then the third one you'll recall is， you know， we want these options to run in real time。 So。

 you know， certainly they should be polytime。You know， idealally， even something like linear time。对。

在。It doesn't matter。So's， it's going to be scale andvari。 The actuallyuction I discuss。

 So if you like， scale them so sum to one。But it turns out to not be important。看。So that's the model。

 And the question is， is there or is there not an auction with all three of these properties。

So are we saying that？No bid gets more than one slot。Good question。

 We will also disallow a bidder from getting more than one slot。Yeah， in principle， you know。

 you could imagine writing the code to put them in more than one slot。

 but that's thought to be a waste of resources。So better。

 better to give the second slot to somebody else to maximize the chance that somebody gets click on。

Other questions？田まさ。All right。So， you know， a little truth in advertising。

 it will not be the case that we can always get all three of these properties。

There's not gonna be some universal mechanism， which is always awesome。

 But for sponsored search options， there is。😊，An auction of all three properties， okay。

So I want to tell you a little bit about that auction today。

 and then we'll finish the discussion on Monday。嗯。So the reason。Mechans design problems are hard。

 or at least seem hard if you don't have the right toolbox。

Is because you really have two couple decisions you have to make， right。

 even just for these simple sealed bid optionsuction。 You have to decide who wins。

You have to decide what the winners are going to pay。

And whether or not players have an incentive to game the system depends not on really just either one individually。

 but rather on， are they coupled in the correct way。Okay， so， for example。

 in a first price auction or even with sort of no payments at all。 in some sense。

 we were picking the right winner。 Okay， awarding to the highest bidder。

 there is a way using the second price to incentivize players correctly。

 Okay so so that you get a dominant strategy implementation。 But if you get the payment wrong。

 So even if you get the winner selection correct。 If you get the prices wrong。

 the incentives can go hay water。So we really have these two joint design problems。

 Who wins and what do they pay。So an approach that we're going to be able to get away with for this problem and some others。

 which will make precise next week is we're gonna to be able to do mechanism design by factoring these two design problems apart and solving it one at a time。

 We're going to first figure out who the winners are。And then given that decision。

 we're going to be able to always successfully define selling prices so that we get the desired incentive properties so that we get a dominant strategy implementation。

So the approach we're going to use。So let me just for reference。

 let me remind you what are the three properties we want， dominant Strate and center compatibleat。

Max social surplus。And polyly time。Prices。So we first。Satisfy these two properties。

 conditioned on somehow later take on fate， satisfying one。

 and then they actually pay the hike who applying payments。

So all I have time to tell you about today is find search options。The step one。

So I'm going to tell you how if we were so lucky。To have truthful bids。

 I'm going to tell you how advertisers should get assigned to。not。

Monday I'm going to discuss tattoo two budget。How do you render algorithms dominant strategies that are compatible by charging super payments。

 that is Monday we will look at vast generals of victory' second price rule。

Including to the slide location algorithm。So I said， yes。Suppose we had clearpoint。

I actually knew the true private valuation。And I've got these eight slots of varying quality。

To sign them。I want to maximize this。Who should give？我三个。

So the person who wants clicks the most should get the most of it。You should go to the first time。

They'reThe next best person the personer wants。But it's almost badly it the second slot and so on。So。

 in other words。The obvious reality。Good Ja Sw。Obviously following on on time。

 all you have to do is sort。It's easy to prove， it's maximizes the surplus。

 that's the last exercise and exercise segment number one。いし。So that's the first step。

If we had coevers， buoyance and new people's。True evaluation。We know what to do。

Just like an the victory auction， if we knew people's private evaluations。

 we just knew we should do it to the highest value。The magic and the victory a。Is aing payments。

Is there a way to assign payments in a sponsor search option？

So that people actually are incentivized。The true valuation。我翻张了。

