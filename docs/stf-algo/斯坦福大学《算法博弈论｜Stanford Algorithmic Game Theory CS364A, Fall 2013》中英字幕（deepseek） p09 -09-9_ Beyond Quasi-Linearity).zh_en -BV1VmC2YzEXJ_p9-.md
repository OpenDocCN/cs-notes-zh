# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p09 -09-9_ Beyond Quasi-Linearity).zh_en -BV1VmC2YzEXJ_p9-

All right， so welcome to what's going to be the last lecture on mechanism design of the course。

 Next week， we're going to start studying games that are more appear in the wild and talking about their equilibrium and when they are close to optimal。

For this last week of mechanism design， I want to study problems where there are constraints on payments。

 So we're going to be moving beyond the quasilinear utility model that we've been studying thus far。

 What do I mean by constraints on payments。 Well one type of constraint is when players have budget constraints。

 a maximum amount that they can pay Another type of constraintsstraint is there's simply no money at all for applications where it's illegal or otherwise inappropriate。

 And so this type of mechanism design is quite a bit harder。 And some sense。

 there's not as much you can do。 But the other hand。

 some of the greatest hits of mechanism design theory do come from these kinds of problems as you'll see。

So let me just remind you about the quasiline assumption we've been making thus far。

We've been assuming that。Every。Players strives to maximize the difference between its value for whatever outcome is chosen。

 I'm using the multi parameter notation here。 So little omega is just some possible outcome from capital omega。

 So it strives to maximize its value， valuation for the outcome chosen， minus whatever it has to pay。

So its utility is linear in money。Okay。So in particular。

 at no point have we really imposed constraints on the payments beyond just the baseline constraints that we were thinking of them always being non negative and always being at most the bid of the player。

So the first reason that we might want to。Consider situations where the payments are not。

Quite so unrestricted are budget constraints。So this just means that for a given player I。

 there's a maximum amount its kid can possibly pay。Now。

 your first reaction to me saying this might be that this is kind of a weird， extra cons。

So if you think about something like a single item auction。

 then budget constraints usually you don't really need to include them in the model。

 That's just sort of part of somebody's valuation。 Remember， when I very。

 for the first time introduced valuation， I said， think of it as a maximum willingness to pay。

 So if you're only selling one good， know， if you can only pay so much feasibly。You know， presumably。

 that's a cap on your valuation on how much you'd be willing to pay。 Okay。

 so the budget would constrain the valuation anyways。

But there are other applications where this makes tons of sense。

 in particular situations where you might wind up buying lots and lots of things， hundreds of goods。

 and maybe you want some overall cap on the total amount of payment that you make for everything that you buy。

And the application， so， you know， economists auction theorists have thought about budgets a little bit over the decades。

 but the application that really forced people to start taking budget constraints much more seriously。

 start trying to develop better models， better analyses of them was their old friend keyword auctions。

So some a few of you may have done this， but if you actually go and enter some bids on a search engine for various keywords。

 you will be asked for， among other things， certainly the following two parameters。So first of all。

 you'll be asked for your value。 That is。How much you're willing to pay for each click that you get on your sponsored link。

 So this might be ballpark 25 cents， something like that。On the other hand。

 depending on the popularity of the keyboard in question。

 there might be tons of research search options in a given day。 thousands or even millions。

 And So your ad might get shown。 your sponsor link might get shown a lot of times。

 And if it gets clicked on a lot， that's 25 cents times a very large number。

So you do want as many clicks as possible， but you also want some control over your maximum expenditures。

 This is the way in which most people reason about these kinds of decisions about their preferences over buying a large number of。

 in this case， especially identical goods。So， by popular demand。

You know the search engines are happy to have this parameter and the advertisers are generally happy to have this parameter。

You're asked for a daily budget。So maybe you're willing to pay 25 cents per click up to maybe a maximum of $100 in a day。

 up to 400 clicks， okay。Or whatever it is that you're paying per click， divided by 100。

So some applications， you don't really need them， but some you really do。

So the simplest way to incorporate budgets into our vanilla quasiline model。Is the following。

 and this is somewhat extreme， but it's still a useful guide。So if your payment。

Is it most your budget then like before， you'll have quasiline utility， Your value for the outcome。

 minus what you pay。So I'm going to use the notation capital B。Her eyes budget。

And it's just not okay to go over budget， let's say。So your utility is minus infinity。

If you're asked to pay more than your budget。It's easy to think of smooth versions of these where you just pay some penalty。

 depending on the extent to what you go over your budget。 people have thought about those models。

 but we're going to stick with a simple one for lecture today，Alright， and again。

 the way I'd like you to think about this。The new feature or the new sort of aspect of this mechanism design is a new set of constraints。

In mechanism design， we've had constraints all along。

We've had our incentive compatibility constraints。 That's what gives mechanismism design its flavor that often compiles down to some kind of monoonicity condition on the allocation rule。

We've had allocation constraints， you know， simple things like you can't allocate a good to more than one different person。

 Those are the two types of constraints we've had so far。 Now， there's a third。 Okay。

 the payments can only be a certain amount。So limiting the power of the designer also limits what you can do。

 And mechanism design with constraints on payments is generally harder than in the models we've seen so far。

 There's impossibility results things you can't do that previously we could with money。Okay。

Or without budgets。So let me develop your intuition for this。

So I guess we've seen one example of this already。So we talked about how surplus was special。

 So we had this VCG mechanism， which maximizes surplus even X post。 So that as you do as well。

 with respect to your performance measure， with respect to surplus。

 as if all of the information was known to you in advance。

 And so what was really special about surplus was two things。 Basically。

 we didn't have to worry about payments except in as much to get the DS SIC property。

 They weren't in the objective function。 All we wanted to do was maximize surplus。

 we didn't care about revenue， and they weren't in the constraints。

So when we lifted the payments to be into the objective function。

 we had the week on revenue maximization。 And as we saw。

 that required some modeling and technical innovations beyond surplus maximization。

 We're going to continue to think about surplus roughly this week。 But now payments。

 instead of being the objective in the constraints。 And again， that makes our lives more complicated。

For example。We no longer have the VC G mechanism or the even the victory option in our toolbox。

So we can't maximize surplus。In the X post sense。That we could with the VCG mechanism。 Okay。

 so we're not going to get surplus as high as if we knew everybody's valuations of front through telepathy。

This is going to be treatment in a single item auction。 If you think about it for a little bit。

So imagine we're just selling off one thing to say， you know，10 potential bidders。

 And imagine bidders do have budgets。And let's even imagine that we do have telepathy for the budgets。

 We know what they are。Let's say everybody has a unit budget。

I argue that single item auction are in the best motivation for budgets。

 but I'm going to use it anyway just to prove a point in this part of the lecture。 Okay。

 The point I'm trying to make holds very generally。So， but the valuations。Are private， as usual。嗯。

So maximizing surplus in the X post sense that we got spoiled with through the vi a and then the VCG mechanism extension for a single amount。

 that just means you always。Successfully award the good。To the highest。

 the bidder with the highest valuation。Okay， so everybody has a unit budget。

 Their evaluations can be all over the map。 We have no idea。

 and we have to identify who the highest valuation person is， okay。And at this point， you know。

 we basically hopefully already see the impossibility。 So first of all， what if we ran the victory a。

Okay。We know what the winner pays in the victory auction， as stated， pays the second highest bid。

 second highest valuation。 No reason that to expect that to be at most one could be anything okay。

So maybe there's some other option that will get us full surplus， but that does respect budgets。

 What do you think。We've got exercises to sort of talk about this point。完了。That's right。

 So one of the main conceptual points of Myson's byma was that once you fix the allocation rule。

 for example， surplus maximization， you have， you have no remaining free parameters。 Okay。

 the payments are determined，So we lose the Vicky a， and therefore。

 we lose the ability to maximize surplus， even in a single item option。

So the point of this example is that we got to do something different。Okay， so then the question。

 of course， is， what should we do？So that's the subject of this election。What should we do。

And so to handle budgets， I'm gonna， I'm only going to tell you， you know。

 basically one auction format， But it's a very nice one。 It's called the clinching auction。😊。

The reason for the name clinching auction will be clear once we describe it。

So the original version of the clinching auction。St Aabelle。And the original version。

 I'll ask you to go through in the third problem set。

 The original clinching auction actually was not intended to deal with budgets。

 It was intended to be an ascending implementation of the VCG mechanism for a special problem for so calledled multi unit a。

So the， it was then adapted to the case of budgets。 And that's what I'll talk about today。

By dainsky it all。About five years ago。Okay。So's the， that's the history lesson。

 Let me tell you the model。So in lecture， I'm only going to talk about the case of identical goods。

That was the subject of both of these papers。 It since been extended。

 but I'm just going to stay with the basic setting， identical goods。

A lot of the times when we've talked about identical goods。

 have've also made the assumption that each bidder only wants one。 That is not the assumption today。

 Biders in general want as many of these goods as they can get their grubby little hands on。 Okay。

 again， think about clicks where you just really want it。 You're happy to have as many as possible。

All right， so as far as each bitter eye。Well， there's going to be a private valuation。

And we're just gonna to have a very simple model， like our single parameter problems。

 like our keyword a， where your evaluation is just linear in the amount of stuff that you get。 Okay。

 so if I give you K goods， then your value for those K goods is V I times K。

 so you're happy to have another good as many as you want to give me。

 I get V I X each time you give me another good。😊，In addition， each eye。

 each bitter eye has a budget。B，I。And I will be assuming that these budgets are public。

 by which I mean， they are known to the mechanism of fronts。 Okay， the budgets， by assumption。

 cannot be manipulated by the bidders。 only the valuations can。Now， it would， of course， be better。

To have an auction which did not make this assumption。

Which elicited the budgets from the bidders and was incentive compatible incentivized the bidders to give you truthful valuations and truthful reports of the budgets and did the right thing。

That problem turns out to be harder。There's some impossibility results saying that things don't work。

 The clinching a is not incentive compatible。 I'll ask you to work that through an exercise。

So we're going to make the assumption of public budgets。 It makes the problem remains nontrivial。

 Atable， and by solving it， we'll get some well be guided toward interesting auction formats。

 which is the point of this theory in the first place。嗯。Yep， so public budgets。

So what I'm to do is I'm gonna first describe an auction， which is not the clinching auction。

 which is more naive， but very natural。 And we'll look at how it fails。

 And then a revision of that initial attempt will be the clinching auction。

 So we're going to do it in two steps。Question。你们要求他你。I'm sorry。They also have a。So as usual。

 the bid will be the alleged valuation。But they do not have a second report for the budget。

 That's the key thing。 So there's two parameters associated with the agent，1， we don't know。

 So we don't1， we do know。 So we don't have to ask them，1， we don't know。

 So we have no choice but to ask them， yes。Don the。It's going to be dominant strategy。

 so it will not be relevant。Okay。So like I said， so first。

 I'm going to give you something which is not the clinching auction， but is more naive。

And so the initial idea is， basically。To use a market clearing price。To allocate the goods。One thing。

 you， just to reiterate with the public budget assumption。

 remember that our non example with the victory auction， the budgets were public there as well。 Okay。

 so the difficulty of budgets is present even when when budgets are known。Okay。

 so what do I mean by using market clearing price。So I'm going describe I'm basically going describe you the allocation rule and the payment rule at the same time。

 I'm going describe this as a direct revelation mechanism。

 but as should be clear from the description， it's very naturally implemented as an ascending auction。

 Last week， we talked about some of the benefits of ascending auctions over direct revelation mechanisms。

 And indeed， Azebal's original motivation was really to have an ascending implementation。

 He wanted an analog of the English auction when you were selling many goods rather than just one。

 But for simplicity in lecture， I'm going to describe the direct revelation version。😊，All right。

 so market clearing price， that means we should somehow equalize supply and demand。

The supply is evident。 It's here on the board。 There's M goods。

So let me tell you about the demand how much people want。 Now， that's， of course。

 going to be a function of the price。 The lower the price， the higher the demand。So to find I demand。

At price P。Denoted D of P。Well， there's going be two cases。 Okay， so remember。

What bitter eye is like。It has this simple valuation where every good you give it。

 it has value V for。I'm going to write this down， assuming truthful bids。

 So I'll go back to the convention of interchangeably talking about bids evaluations。

 assuming that they're truthful。So first of all。Suppose the price。Is bigger than eyes value V。

How many does it want？None， that's right。The reason is because it's going to increment the value part by V I。

 and it's going to increment the payment part by more than V I。 So that leads to negative utility。

All right， good。So how about。That's not what I' meant to do。

How about if the price is less than the per unit value。Well， let me give you a simple case。

 So what if the budget was plus infinity， What if there was no constraint on how much bitter I could peg。

What would be its demand at a price P less than its valuation。 How many does it want。All of them。

There's no diminishing returns here。 Every good you give it， it gets a V I。

 So if the price is cheaper than that， give them all to me。So the only thing constraining。

So there's two things constraining， I guess， how many goods。I could possibly get。

 The first is just how many goods are available。 So I'll cap this at M。 The number of goods。

 The other is how much it can pay。So the amount it can pay。Is this budget B？

It has to pay that per good。So B， I divided by P is the number of items at price P。 It can afford。

 Okay， this might not be an integer。 So let's also round down。Per good。 P is per good。

So that's the demand of a better eye at a given price P。So the higher the price。

 the less the demand as you'd expect。Okay。What's the demand of price zero？

You'd happily take them all。And the demand at， and let's say。

 an infinite price or is sufficiently high price。It's going to be zero。Actually。

 just so you have good intuition for these demand functions。

 Let's think about this a little bit more carefully， exactly how it decreases， O。

So I'm raising the price P slowly on this bidder。 O， and its demand is only going to drop。

There's actually two ways it could drop。Right。So the first way it could drop is if the price hits the bidder's value。

 let's say the demand is currently 10 at the current price。 and all of a sudden。

 the price hits the value。 What how the demand decreases by what， from 10 to what。To 0。 O。

 it suddenly evaporates。 O， so it with some number， some positive engine now， it's0。

What about the other kind of decrease， other kind of decreases where the price is still well below the value。

Okay， but obviously， with a fixed budget， the amount you can afford is dropping as the price goes up。

 So to suppose the demand drops for that reason at a given price。

 But when it drops from 10 to something what's going to drop to。Not。Okay。

 there'll be some price at which you can afford strictly exactly one less good than you could before。

 Okay， so as we increase P， the demand drops either by a single unit or it suddenly goes to 0。

I guess I didn't quite specify the demand function when the price equals V。 I。

 I didn't say what it was。And that's because， you know。

 both in the auction itself and in our analysis， we get to be flexible。Okay， when V I equals P。

 you know， the bidder could care less how many items you give it at that price。

 It's totally indifferent。 So we'll define when P equals V I D I of P to be whatever is convenient for。

 for the what's under discussion， okay。Again， as usual， we can't violate bidder's budgets。Allright。

 so now。What does it mean to choose the market clearing price。

 It just means we're going to sell items at the price， which makes supply and demand the same。

We know what supply is。 It's just M。 We know what the demands are。 They're just this D I of Ps。So。

But P star。Be the smallest price。P。So that supply。Equals。Total demand。So if you want to be nitpicy。

There need not be any prices where this holds with equality。 And that's because as we just observed。

 demands can suddenly drop by like 10。So then we have to look at the point where everywhere to the left of that point。

 all smaller prices， the demands strictly bigger than M and all prices a little bit bigger。

 The demands strictly less than M。 And there will be some such point。And。Then what do we do？

Just for all I。We give D of P star。Goods to I。At the market clearing price， P star。

So that's the first cut。Of the mechanism。And I've defined for you both the allocation rule and the payment。

Questions。嗯。没。Here later。Well， I mean， we need to prove set of compatibility， right。

So guided by all the way back to the victory auction。

Where sort of amongst prices where someone would accept the good。 You always take the smallest one。

 It seems like the right thing to do。Questions。Allright， so the good news。お。Is in contrast。

To the victory auction or the more general VCG mechanism， budgets are going to be respected。

By this mechanism。Where to go。User error。Okay。So recall the definition of demand。

 I guess this is where you see， right。So if we allocate to a bitter eye D I of P goods at a price of P。

 then by the definition of D I of P， the amount that it pays is at most B sub I。

 We defined d sub I of P to be the largest number of goods that the bidder could afford at that price P。

 Actually， the minimum of that or 0， if the price is bigger than the value。

So just by definition of demand， budgets are going to be respected。The bad news is。

Anyone to guess the bad news？Yeah， not DS SIC。Since's the bad news。 I'll give you an example。

Essentially。The problem here is something that plagued us on Wednesday with simultaneouslyimult incentiveing options as well。

 which was a form of demand reduction。So in effect， a bitter preferring to get more goods， sorry。

A shoeing， getting more goods at a high price， opting instead to get fewer goods at a lower price。

 and。Bdding in a non truthful way to make that happen。So here's an example。

 And hopefully this will also kind of make sure that we all understand how the clinching auction works。

So just two goods and two bidders。Let's say， and again， remember， budgets are known。

So let's say we're well aware that the first bidder can afford an arbitrarily large amount of payment。

 but we don't know what's value。Let's say its private value turns out to be6。Okay。The second bidder。

It's value in its budget。Are both5。这是什个。So what's the market clearing price。

Assume for the moments that bidders bid truthfully。So bids equal values。

What market clearing price would we then compute。So remember the mark clearing price is the smallest price。

At which supply equal demand。And prices don't have to be integers。So what are I like，5。5。

 What's the demand at 5。5 total。That's also only two。

RightSo you only need a price of 5 plus epsilon for the second bidder to have demand 0。Okay。

 at which point the the first bidder has demand， too， which clears the market。

So the smallest of all prices that equalizes supply and demand would be  five plus epsilon for arbitraryarily small epsilon。

 So we'll call it 5 among friends。So suppose。Number  two。It's five。Number one， bid 6。

So we agree that the price will be 5。 So who gets the goods。So bitter 1 gets both。

 So what's the utility of bid1 with this allocation payment combo。That's right。

 So you get a utility of one for each good for a total of two。

So at the risk of plunging my foot into a bucket of water。

 let me work out the rest on this part of part of the board。There's a bucket of water right there。

Does it makes sense， given all the rain we've been having。O嗯。So demand reduction。 remember。

 the idea is it can be better in a poorly designed auction or in a manipultable auction to get fewer goods at a low price as opposed to more goods at a high price。

So imagine that it's a bitter one。 It can't misreport its demand per se。

 All it can do is say it has a different value， a lower value。 So suppose number one bids 3。

Instead of  instead 6， excuse me。All right， so let's think this through。

Let's think about Bi number 2， for a second。So when the price is 0， or're very close to 0。

 what is bidder2's demand。It's true。 It's habit of both。Okay。

What's the price at which bidder2's demand drops below to。在。2。5， as soon as the price exceeds 2。5。

 it still wants goods as many as you give it， but can only afford one of them。Okay。So the price 2。5。

 we have a demand of  two from bidder number one and a demand of one from bid number  two。

 So we're not in a market claim price yet， but something interesting has happened。Now。

 once we get to the price of three。Remember， bid number one， falsely bid 3。Okay。

 so that's the point at which we're on the verge of kicking Bi number one out。

And so that's the point in which the auction is going stop。 Okay， So again， remember。

 when P equals V I， I'm gonna define the demand according to my convenience。 So let's just。

 I'm gonna set the demand equal to one for bid number one when the price equals its false bid 3。

 Okay， the demand for bitter number 2 is still one。 So that's where the market clears。 Okay。

 at the price of  three。Now， the bad news for video number one is instead of getting two goods like before。

 now it only gets one。 The good news is the price for that good is no longer 5。 Now it's 3。

So what's the utility of Bider number one with this false boot of 3。3，6-3。

 It's value minus the price。So that's a concrete demonstration。

That with the market clearing price based auction， it's not D S I C。So it's been a while since we。

Talked to it since we put on the mechanism on the board。

Any auctions that were not incentive compatibleatible。 Okay。

 we sort of had a rich enough toolbox this had stopped happening to us。So what happened here？ Well。

 we went back to the。Approach of designing the allocation and payment rules together。 And evidently。

 we did it incorrectly。 Okay， notice， this is totally a single parameter problem。Okay。

 budgets are known。 There's just a private VI for each bidder。So this allocation rule。

 I'll let you check this。 The allocation rule is monotone。So by Myson's lemma。

 there are payments that would make it a DS S I C mechanism。 Evidently， we got them wrong。

So we could go back and derive。The D S IC payments that Maronss Lemmo would give you。

 but I'm not going to do that。 turns out a different allocation rule。

 Well smarter allocation rule is going to work better。 Okay。

 so this is going be the clinching option。So again。

 I'll describe this in it's a direct revelation form。

 But I encourage you how to think about how this might be implemented in ascending form。 Again。

 that was the original motivation for this clinching a technology。So we're again。

 gonna have a price which inside our algorithm， we think of ascending at some steady rates。

Rather than allocating all the goods in one shot at the end。

 we're going to allocate them piecemeal at different prices。

So I'm going to keep track of this current supply S。Which is， of course， initialized。To M。

While goods remain。While theres still demand。I'm going to raise the price。

You' going to raise the price until demand falls。And by demand falling， what I mean is。

I wait until there's some bitter eye。So that。If I let the other n -1 bidders。

Take what they want at the current price。 There'd still be some left over for bitter I。Okay。

 so maybe there's 10 goods left。There's 20 bidders out there in the world。

 And if I just let these 19 bidders take what I want。

 the price is actually high enough that some of these 10 goods still remain on the show。So， S minus。

Some over the other bitterders。Of their demand at the current price。 Remember， as we increase P。

 these are dropping。 this is staying fixed。 This is how many goods are left。

 This is what people want at this price。 This goes down as the price goes up。

So once this is positive。Let's call this。Number K。I guess I should also remind you。

What these demands are。 is's it up there。 Oh， good。 It's still up there。Okay。

 so demands are defined in the same way。Once this happens。Once there are these K good left over。

 even if the other one and -1 bidders take what they want， I let bitter。

 I have these K goods at this current price of at this current price of P。

So these are goods that these are called clinched。This is the。Name of the clinching auction。Okay。

So these goods that you get that I gets at this point。 These are its goods forever more。

 and the prices that it pays for them are fixed right now。

This price will go up later on in the algorithm doesn't matter for these particular K goods that I gets right now。

 P is what it has to pay for them。And maybe the main thing that the clinching auction does differently than the market clearing price auction。

Is that it go ahead and keeps track of the reduction in budget with a couple things。 So。

 first of all， it promises goods at relatively low prices early on in the auction。

And then second of all， to make sure that all the prices come out correct At the end。

 it keeps track of bidders keeps track of bidder's budgets and reduces them as they clinch goods。

So it decreases the supply by the。Amount that it should， namely k。To decrease S。By K。

And bitter eyes budget by the amount that it's now committed。Namely， the K goods that it's clinched。

Times the price that it's going to have to pay for。Sure。So unlike the first option。

 based on the market clearing price， a bidder will not necessarily pay the same price for all of the goods that it acquires。

 The price it pays for the goods will get higher and higher as the auction proceeds。

So I'll go through an example。 I'll go through the same example， in fact。

 but any questions about the auction before I hide the pseudocode for a minute。

What if I can't quote the？You afford it。 can afford the goods by the definition of DJ。

Other questions。That's a good question。 So it turns outrbitrarily， arbitrarily works fine。对啊。

So you can even do them simultaneously。So arbitrarily。Yeah， so just to be clear with respect demands。

 remember the demand of a bidder at a given price， part of that definition is how many you can afford at a given price。

The price is increasing as always。 So that makes the demands drop。 But remember。

 the clinching auction is keeping track of the past expenditures of a bitter eye。 Okay。

 so you decrease the you really tracking residual budgets， not original budgets。 And so， of course。

 when you compute demands， it's with respect to residual budgets。

 not with respect to original budgets。Okay。发生。播的吗？Yep， as I said， you break ties arbitrarily。

Let's revisit the example。So let me remind you of the example， oh what's up there perfect。2 goods。

First， bid rise infinite budget value 6。 That was the one who had an incentive to reduce its value previously to get one good at price 3 instead of two goods at price 5 each。

Bitter 2 has budget equal value， equal 5。So what happens with truthful bids now？So initially。

 what are the demands initially when the price is 0。They're both two， right。

So from each bidder's perspective， the other one doesn't leave any on the shelf。

So we need to look at the first price point which somebody's demand goes down。

Very already talked about what that was。 That was a price 2。5。 Once it hit 2。5， Bi number two。

 can now only afford one。Okay，So again， bitter2's demand drops to one at the price of 2。5。

 leaving one on the shelf。Okay， so this condition is triggered with bid number one at the price of 2。

5。K is equal to 2-1。 There's one good left on the shelf。We go ahead and give it to bid number one。

At the current price， which is 2。5。たと。Now， there's only one good remaining。Okay， so for。

 for there to be something left on the shelf when everybody else goes， it has to be， we。

 we have to wait until the price is so high that one of the bidders demand drops to 0。

So that happens once it's equal to 5， the valuation of the second bidder。 At that point。

 the second bidder is kicked out。 and that's the price at which a bidder 1 gets its second good。

So the prices are less than with truthful bids and the non D S I C market clearing mechanism。 Okay。

 with truthful bids bidder 1 paid5 for both。 That's why it had an incentive to do demand reduction。

 You might hope and will prove a more general statement。

 You might hope that getting the prices right in this sense would take away that incentive for demand reduction。

So， Ferm。Indeed。The clinching option。Is DSSIC。K。Now， you know， one way we could prove this， again。

 this is a single parameter problem。So in some way， the， the way that I've trained you to prove this。

Is to write down the allocation rule formally， compute the Marison payments and then check that we got the payments right。

 Check that the payments here are actually the Morrisson Lemma payments。 You could do that。

 It would work。Turns out in this case， I think it's easier to just verify directly。

 So that's what I'm going to do。So a proof。So fix some bidder， fix bids by the others。

So it's sort of a trivial observation， the one that kind of helps you。Orient you for this proof。

 right， So don't forget that your value per unit of good is always the same。

 whether it's the 7th good that you get or the 20th good you get。 It's always V I。Okay。

So at any point in the auction， if you pay less than V I， you're happy， if you pay more than V I。

 you regret it。Okay。So the price is going up at this steady rate。

 So there's this prefix of the auction from time 0 up to V I where any goods are just you're happy to have。

 And then in the suffix of the trajectory after the price is V I。

 you don't want anything because the price is going to be bigger than your value。😊，嗯。So note。

Goods clinched。When the price is less than your value。Respectively bigger than your value。Contribute。

Positive。Respectively negative。Utility Utah。Okay。So basically。

 you want to be present when the price is less than your value and you want to be absent when it's higher。

The other important observation is that what's the role of your bid in the clinching auction。Okay。

So let's remember how we define the demand of a bidder。Okay。

 so if the current price is less than a bidder's bid。

Then we just defined your demand as how many goods you could afford。At the current price。

 since according to your bid， you want as many as possible。And as soon as the price exceeds your bid。

 we effectively kick you out of the auction。 Okay， your demand is 0 forever more。

 As soon as the price exceeds your bid。So you're kicked out。Exactly when the price reaches your bid。

Kicked out in the sense that your demand is0 forevermore。So。I'll just go through one of the cases。

Since they are symmetric。So let's just compare two situations。 Sation1， you bid truthfully。

 you bid your true value V I。Situation 2， you bid something less than V I。Okay。Well。

 if you bid less than V I。How do the initial iterations of the auction change？You bid less than that。

VR。Well， as long as the price， remember， we're thinking about the case where your bid is less than your value。

So if the current price in the auction is less than your bid。Then these two worlds are identical。

 Okay， So remember， your demand， is's just your budget over the price。 And again we know your budget。

 that's public。Or we zero it out at this threshold。 Okay， so before we hit your bid。

Your demand is independent of what you bid。 Okay， it's just your budget。

 which is known divided by the current price。So if you'd like， formally by induction or whatever。

Run the auction in parallel with the true bit V I and the smaller bit B I。 They're exactly the same。

Until the price hits the smaller value， the bid。Okay。

 the auction is identical in execution up to that point。And then what happens， Why is it different？

 Well， suddenly you're kicked out with the smaller bit。Okay。

 so there is no change in how the optionuction proceeds until the price reaches your。L bid。不不。

And so when I say the algorithm execution identical， again， I mean。

 on the one hand with your true bid and the other hand with a smaller bid B， I。

So the prefix up to the price B I is exactly the same。

 The difference with the false bit is you're missing out on whatever happened in the clinching auction when the price was between B I and V I。

Okay。You don't know what happened， but whatever happened could only have been good for you， right。

 The only thing that could have happened while you're participating in the auction in a price less than the value。

 The only thing that could happened， you could have gotten goods at a price less than your value。

 And you just threw them away。So summarizing the only thing that happens when you bid lower is you lose some goods on which you would have otherwise earned positive utility。

 obviously， not a good idea。The case where you bit higher is similar。Again。

 run the auction in parallel with your true bid V I and this overbid B I。

 nothing changes as long as the price is below V。 I。 The algorithm executes identically。

 The difference is you stay in the auction longer with this high bit of B， I。

What can happen in the when the price is bigger than V I and less than your bid。

 The only thing that could happen is you get some goods at a price higher than your value。

 giving you negative utility。 You don't want that。So that is why the clinching auction。Is DSSIC。

Cool option。Well， I think it's a cool option。 If you think about it。

 I haven't really proved to you in a very meaningful sense that it's a cool option。

 What I prove it was DS S I C。 And anyone want to give me another DS S I D S I C auction that respects budgets。

😊，Give the goods for free。 price 0。Budgets are respected。 D S， I C， O。

 I have not actually given you any formal sense in which the clinching auction is better than giving goods away randomly。

I'll tell you a secret。People are still to this day， kind of struggling with。

The right way to do that。There's some valt attempts。 There's some nice theory here。

 There are senses in which。The clinching auction has been proved。To in various worst case senses。

Have good surplus。Now， what do I mean， good surplus， good compared to what。

I certainly don't mean good compared to the maximum possible surplus compared to like the V C G surplus。

 because we know even in a single item auction， when all the budgets are known and equal。

Any DS S IC mechanism can have far worse surplus than a VCG mechanism that didn't have to respect the budgets。

So I don't mean compared to the benchmark of the V C G mechanism。

 That benchmark is just too strong to make any comparisons。

So that means you have to go back to the drawing board and think about benchmarks that are weaker。

 but also just smarter， that take into account that any solution has to respect budgets。

So there's a few ways of doing that。 I'm not going to cover any in the lecture。

 They're all just sort of would take a little bit too long。

 So the original paper that proposed this clching auction for budgets， stop Zinsky Levy and Nissan。

 They focused on a property Pareto optimality。So they observed that the clinching auction outputs a prereto。

 optimal allocation。What that means is， is if you consider any other allocation in which some player is better off。

 I。e。 has higher utility。 There's a different player that's worse off。Okay。

So this is a relatively kind of weak notion of sort of efficiency。 economic efficiency。 Okay。

 There are other allocations which are maybe incomparable where some players are better。

 but other players are worse。 And what was nice about their contributions is they derive a sort of uniqueness results。

 saying that if you care about preto optimality， essentially。

 the clinching option is what you have to do。 if you want to respect budgets。

The drawback there is that prototypeto optimality isn't。

 It need not be a necessary or sufficient condition for a mechanism to be optimal in various other senses。

So a second approach is the same one we took for revenue。 Remember。

 even when we put payments in the objective function。

 we lost this ability to have a single mechanism， which is always the best one。

 And the first thing we did is we introduced distributions that did average case analysis。

 And then what you might like to say is a simple versus optimal result。 There's a nice mechanism。

 like， say， the  clinching option， which is almost as good as a possibly very complicated average case optimal mechanism。

So that's been，'s been worked on that very recently。 just appeared maybe four months ago。

 Even that only handles the case where everyone has identical budgets。

 but that's good progress from just a few months ago。

And then a third approach people have looked at is they've tried to sort of redefine the welfare objective function in ways that it's a smaller number。

 Okay， that takes into account budgets。 All， there's some progress here， too。

 but it it's fairly ad hoc at the moment， But you'll get some more experience with that in the exercises。

So the takeaway is the clinching auction seems like a great idea。

 It See like an awesome a in some sense。 And we're struggling with what that means。

 And this is actually not uncommon in research and research。

 It's often that you find the solution before， you know exactly what's the problem that it's solving。

 And this is one of those cases。😊，I got one more really nice mechanism for you today。

That's all I gonna to have to say about budgets for the rest of today and for Wednesday's lecture。

I want to make the constraints on payments still more stringent。If you like。

 I'm going to set the budgets to all be0。So I want to talk a little bit about mechanism design without money。

This， of course， is a tie your hands even tighter as the designer。So you can do even less。But again。

 there is some。Really quite beautiful and also practically useful mechanisms in this space。😊，Alright。

 so I've probably conditioned you to be thinking so much about auctions。

 You're probably wondering whether it's an oxymoron to talk about mechanism design without money。

Really， mechanism design is just about what do you do when preferences are not fully known on priori。

 Okay， it's not really about， mean， then you know， different flavors of mechanism design give the designer different abilities to interact to implement things。

Some situations， money is illegal or otherwise morally repugnant。So organ donation。Okay。

 kidney exchange。 We'll talk about some on Wednesday。 There are markets for kidney exchange。

 They do not use money， at least not in the US。 Last。

 I checked Iran was the unique country that actually had a legal monetized market for kidney exchange。

Not saying money never has anything to do with voting， but。It's supposed to be illegal。

The way kids get assigned to elementary schools in lots of different cities around the world。

 it's done with neism design with no money。The way。

Recent graduates from med schools were assigned to their residencies。 same thing。

So there's lots of applications。 We'll talk more about them on Wednesday。

The thing I want to do today is just tell you a really nice algorithm， really nice mechanism。

Historically called the house allocation problem。So there are N agents。

Each begins with an initial endowment of one house。You may covet others houses。

You may want other with people's houses more than your own。In fact。

 you have a total ordering over the houses。 That's your preferences。

Suppose you wanted to take as input these in houses that the agents currently have。

 And if youd like rearrange them。 But again， with each agent having exactly one house。

 you want to do that in the best possible way to make people as happy as possible。

What's a sensible approach？So me tell about the top。Trading cycle algorithm。T TCA。

Which is going to propose a particular reallocation。 Okay。

 reassignment of the end houses back to the N agents。

 which in some sense is the best allocation you might want。

So we're going to construct the allocation iteratively。

We're going to be deleting agents in bunches after we've fixed their reallocations。

 The agents that remain will always be in possession of their original initial house。Conceptually。

For the agents that remain， you imagine asking them。 you say， hey， of the houses that still remain。

 That is the houses that belong to the remaining agents point to your favorite。Okay， so remember。

 you started with this total ordering over houses。 Some of them have disappeared。

 They've gone other people， bummer。Of those that are left， tell me your favorite。Sure。

So you can think of this as defining a directed graph where the out degree everywhere is equal to one。

100 agents， each one chooses one outgoing arc。Maybe agent two is coveting agent one's house。

But agentnt1 says， well， I like my house。 thank you very much。

And then maybe you have something interesting worth three。 really likes for's house。

Who really likes Five's house。Who really likes three's house？In any case。

 when you have a directed graph whose out degree everywhere is one。

 you're gonna have at least one cycle。Started a node。 Just follow these outgoing arcs。

 You're gonna repeat。There may be more than one， but there's going to be one for sure。

This directed graph has two cycles。 Okay， the self loop that counts as a cycle。

 And then there's the 3，4，5 cycle。So there's at least one cycle。The algorithm then picks one。

 If there are many cycles， it can pick anyone that it wants。And when it picks a cycle。

 it does the reallocation suggested by the cycle。For example， in the 3，4，5 cycle。

 you just go ahead and give fours house to3。 You give five's house to4。

 You give threes house to five。If you pick the self lu as a cycle， then one keeps its own house。

After you've done the reallocation， you delete those nodes from the graph。 They're gone。

So they've gotten their final houses。 whatever they got from the cycle。

 that's what they get at the end of the day。This terminates with a new allocation or with an allocation。

 Each agent gets exactly one house。Cool。So it seems like a nice algorithm。Hopefully。

So is it any good， Does it， Does it have any reasonable properties。

 Let's just to build up your intuition， Let's start with a sanity check。I claim， at the very least。

You're not going to be worse off than where you started。Okay， so every agent。

Maybe it keeps its same house。 Maybe it gets some new house。 But in any case。

 the house it winds up with， it likes at least as much as the one that it started with。

Anyone suggest a proof of why that's true。Yeah。Okay。最後。神分你。So。Good。So succincly， I' put it。

 you always have the option of pointing to your own house as long as you're in this graph。O。

So remember， if you don' get if you don't participate in a cycle。

 you keep your house for the next iteration。Okay， so every iteration you're in the graph。

 you have your house。 You can point to it， if you want。If you point to something else。

 it's because you like it even better。Every agent is processed at some point in this algorithm。

 When it's processed， it's given the house that it's pointing to。

 which at that moment is going to be either its own house or something that like bep。O。

So that's good。 At least you can't do harm with this algorithm。手外面。Again， before。

 I'm going have time to talk about welfare properties。

 but let me just talk about incentive properties。If you now imagine。

That these total loadings are unknown private to the agents。

 There's an obvious direct revelation mechanism you could run。

 Tell me your're ordering or run this algorithm， and then I'll output that allocation。 And。

 of course， there's no money。Okay。And the claim is that direct revelation mechanism。

Is dominant strategy and compatible。Okay。So if I'm gonna reallocate goods using the top trading cycle algorithm。

 tell me what you really want。That was a good idea。什么定。It ask for。要玩嘅。

You just mean as far as how things get reported。Okay， good， good question。 So good question。

 So the question is sort of comparing kind of what I ask for in the two different mechanisms we've seen so far。

 And one thing that's really cool about this housing allocation setup is the space of preferences is very rich。

😊，Right， so， you know， what I don't know about you could take on in factorial different values。

 So this is not a single parameter setting。 There's not a single number or two single numbers that's summarize to me how you feel about everything。

O。By contrast， when we were talking about the clinching auction。

We assume that upfront that I know your budget。 and from that and your value。

 I could conclude your demand。At any given price， okay。Okay。So why is this true， So now， of course。

 that we don't have money。 I mean， we can't even speak about Myerson's lemma。 I mean。

 for multiple reasons， one， this isn't single parameter。 There is structure from the problem。

 but it's a different type of structure。 But two， the whole point of Myerson's lemma was to give us the payments and make a DS S I C。

 We really need the payments to be 0， okay。So we're going have to check the DS SIC condition directly。

So， a fixed eye。And as usual， the other reports。And。Suppose with a truthful report。By I。All right。

 so we won the top trading cycle algorithm。It picks a cycle。 Does the reallocation deletes。

 picks another cycle。 Does the relocation deletes， et cea， eta， et cetera。

So it has some number of iterations， let's say L iterations。 and it picks a single cycle in each。

So it's called the cycle C1。Up to C。That's semicolon。嗯。And let's say that I lies in the Jaith cycle。

So when we fixed eye， we think about a truthful report。 We run the algorithm。 This is what we get。可。

So now， let's think about what is eyes power。We have various misreport it might give。Sure。

And the way we can think about a mis report is that in each iteration of of the top trading cycle algorithm。

 it points to some other house。 It points to somehow a worst case house for the designer。

 or best case house for itself。So if we give I the power to point。To different houses。

 in what way can it influence the execution。Of the top trading cycle algorithm。So let's say I。

 with a truthful bid。Is chosen in the 10th iteration。 Okay， so let's say J equals 10。

Does this bidder have the ability to change what cycle gets picked in the first iteration。

How would to do that？To close another cycle。嗯。By making a worse bid。Rights， okay， good。Good。

And so then what would be the case。So it didn't point to itself。

 it pointed to if it points to something else in the same cycle。It's going to be a worse house。

 right， It can be a house of like less。Okay， so， basically。So eyes only ability。To influence。

Cycle chosen。Is to points。To a house that likes less to close the cycle。嗯。Said again， sorry。

 I didn't hear。Po group。Do how that like existing？Then its own， mean， oh， okay。We than it town。

That's the point。真。Likes less than its favorite。Okay。So this leads。

 I'm going to be a little informal here。This leads。It's being allocated。

So if it closes the cycle and it's chosen right now， the point is。

 it's literally going to get that allocation right now， okay。Leads to being allocated or worse。

houseuse。T before。Okay。So， details。I'll leave for you to check。ちんと。Like we' going at the similar。

I believe it will， yes， yes。Yes。So in fact， the way it's usually described is just you delete all the cycles in the first iteration。

But， but I'm almost positive。 It's uniquely defined。Okay。

So this brings us back to where we were with a clinching auction。 Okay， I told you it was D as I C。

 And you'd be right to respond。 You know， seems like a cool algorithm， but so what。😊。

Another D I C mechanism would be to just output a constant allocation。 Okay。

 or just always force bids to have the same house that they started with。

So in what sense is this bitterder， better？Well， here， the theory is much more satisfying。 Okay。

 so here there's a sense in which the top trading cycle algorithm does the uniquely best thing。

 I don't have time to discuss this in detail， but I'll put some details either in the notes and or in the problem sets。

 So this is the unique allocation in what's called the core。And so basically。

 what the core means is it's， there's a stronger version of incentive compatibility where if you imagine some subset of these bidders。

 So say there's 100 agents overall。With this allocation。

 it's impossible for some subset of 10 agents to sort of break away from the mechanism。

 Reallocate their 10 houses nearly amongst themselves and all be at least as well off as they are in the top trading cycle algorithm。

 at least all as well off plus one strictly better off。

 so you cannot pointwise do better than you're doing in the top trading cycle algorithm。

 no matter which subset of agents you're talking about。

 So claim one is that the top trading cycle algorithm has that property。

 the allocation that it outputs， no subset to better by breaking away。

 The second claim is that every single other allocation fails to have that property。

 every single other allocation is vulnerable to some subset breaking away。

 doing exchanges only amongst themselves。 at least one will be strictly better off and no one will be worse off compared to this allocation。

So more on mechanism designed without money on Wednesday。 See you then。

