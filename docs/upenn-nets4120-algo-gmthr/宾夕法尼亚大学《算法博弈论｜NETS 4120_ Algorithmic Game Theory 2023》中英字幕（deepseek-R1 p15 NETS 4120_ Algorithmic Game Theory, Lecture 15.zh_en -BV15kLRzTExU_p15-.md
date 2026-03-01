# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p15 NETS 4120_ Algorithmic Game Theory, Lecture 15.zh_en -BV15kLRzTExU_p15-

All right， good， so let's begin。

![](img/fdcbea832c29e271c6b6aba545c7591a_1.png)

So we saw last class when we studied while we're in equilibriumria。Money for the first time。

So it turns out。Money is very useful when you're organizing a market to use it as a medium of exchange and。

Last class， although this is sort of the mechanism design section of the course。Yeah， really。

 we sort of went back and we sort of studied game dynamics again。

 like it wasn't a mechanism design problem。 we sort of wrote down。Basically。

 we sort of described a natural dynamic。That might play out in a Marcus basically where people take turns。

 you know， outbidding each other， competing on goods， the price of the good sort of goes up。

 the more demand it has， the more time it's been outbid。

And what we proved is that in this natural dynamic， we sort of。

It converges to while we're see equilibrium and remarkably an optimal welfare maximizing allocation。

Okay， so that was cool， I mean， it sort of means we have some。

Styylized at least micro foundations to the assertion that。

Markets through prices are able to coordinate。Useful allocations of goods。嗯。

But this was really a style of analysis from like the beginning of our course where we wrote down a game。

 we studied some dynamics， and we proved it converged equilibrium。Yeah。

The deadline 59 minutes from now that's not quite enough time。诶嗯。诶。59 minutes from now， big fix。

All right， maybe I'll plug fast。对。I'll make it in 30 minutes， we'll worry about it then。嗯。Okay。

So so this lecture we're going to take a mechanism design perspective we're going to say okay like we're not going to like rely on Adam Smith's invisible hands to figure out who gets what we're going to try to you know write down an algorithm that decides who gets what and。

Hope that we can design a mechanism that both。Ends up with making good choices。

 allocating goods well， and managing incentive properties properly so that people want to tell us what their utility functions are。

So let me define a very general setting and I'll talk about a couple of instantiations。

 but really like we're going to prove our results in this general setting that is really quite broad。

So。We're going to be。Coming up with mechanisms that are just choosing from some set of alternatives。

 that could really be anything could be in an auction who gets what。

 it could be in some city planning context， you know， do we build a library or a police station。

It's just alternatives in the abstract that we are choosing between。

And we've got end agents and they care about what we choose。 Okay， in an auction。

 they care about which goods they get in a city planning situation， you know。

 different people are going to use libraries to different amounts。 You know。

 they care about what we build。 And again， in the abstract， we're just going to model。

These n agents as people who've got valuation functions that just tell us how much they like each of the alternatives that we could choose so these valuation functions just map the choices that we could make。

 the alternatives chosen so a utility to a real number that tells us how happy they are we if we make that choice。

Okay， now。嗯。An outcome， oh， we're using money， right。

The kind of the design space we're working in right like you know if people report to us say a bunch of valuation functions and we sit down and think about what we should choose given these valuation functions。

 the kind of thing we're allowed to choose， I'll call it an outcome。

 and really it's a pair of two things。It's an alternative I can decide in an auction who gets what in a city planning setting。

 I can decide what resources to invest and what to build。But also a price vector。

I have the ability to charge people money， so for example， in an auction。

 know you might tell me that you really like。This dongle that I've got here。

And you might win the auction， you might get the dongle， but not for free， like I'll be like。

 all right， here you go $10。Okay， so an outcome in a mechanism design setting will be an alternative together with a vector of prices。

 with one coordinate for each fireer。With the sort of semantics that player I is going to have to pay PI dollars in exchange for you know。

 me having chosen alternative A。And just like last class。

 we're going to assume that players have our what are called quasi linear utility functions and let's just think about what that means because it's not completely without loss of generality。

It basically means two things。So first of all， what does it literally mean。

 it means that if I'm computing my utility for an outcome。

The way I'm going to compute that is I'm going to figure out what is my value for the alternative chosen。

And then I'm going to subtract off the amount of money I need to pay。Okay， now。Right， okay。

 so so like literally this is what it means right that that sort of my utility is just my value minus the price I need to pay。

Just like reflecting briefly on what are the assumptions we're making about agents when we assume they've got quasi linear utilities。

ItTwo things first one that we might take for granted。

 but it's still an assumption that you can express your utility for stuff in units of money。

like maybe if I give you this dongle。You just get some kind of ineffable joy from it that it would be craftas to express in dollars right then。

You'd have trouble writing down an expression like this， Okay。

 but like maybe we're pretty used to that。 we buy and sell stuff so we're sort of used to converting utility。

 which is some big thing that goes on， you know， in our heads into dollar amounts。Okay。

 so quasi linear utility functions， first of all， assume you can do that。And then second。

 then more seriously， they assume that your utility for money is linear。

They assume that you know you're going to be twice as well off with$20 compared to $10 you're going to be twice as well off with $2 billion compared to 1 billion Okay。

 so probably for most of you that's not literally true probably the。You know。

 maybe $20 is worth twice as much due as $10， but probably $200 billion isn't really worth twice as much view as $100 billion。

 it's not clear what you would do with $200 billion like you wouldn't also do with $100 billion。

 but this is sort of a reasonable assumption at low dollar amount。Anyways。

 it's the assumption we're going to make okay so we're going to assume that players have utility functions like this。

 everything can be expressed in units of dollars and you've got linear utility for dollars that makes sense this was the same assumption from last plot。

ok。So just maybe to point out， this is a very general setting。It captures all sorts of stuff。

Right so maybe like the most common kind of auction that you would have seen like on TV or you know。

 participated in on eBay is I've got one thing that I'm selling like this dongle or the Mona Lisa or a house or whatever。

And。At most one person is going to get it， it's indivisible， I'm not going to cut it in half。

 in which case if I've got a bunch of bidders， the alternative chosen is just the name of one of the bidders like one of them is going to get the item and the others are not。

Okay， so in a single item auction the。Set of alternatives chosen。

 the set of alternatives I can choose is just equivalent to the names of the bidders。

 I will give the item to exactly one bidder。But I could define a more complicated setting than that。

 for example， I could have a multi units auction the the goods I'm selling might be related to one another。

 So for example。嗯。😊，Airports in the US that take off and landing slots are auctioned off。

You know different buyers can get bundles of different takeoff and landing slots。

 but there's some constraints like if your plan is going to land。

 you probably eventually want it to take off again， planes can't land at the same time。

 there's a lot of takeoff and landing slots over the United States so it's this multi-unit auction with all sorts of combinatorial and temporal constraints but that can also be expressed in this setting right so we sort of decide the set of alternatives is a mapping from bidders to subsets of the goods that they can get possibly subject to arbitrary feasibility constraints。

Okay it doesn't have to be it doesn't have to be an allocation problem it can be what are called public goods problems。

 this is sort of what we were talking about when we talked about city planning I could decide you know the set of alternatives could be i'm going to build a fire station or i'm going to build a library or i'm going to。

Double the size of my police force。And these are things that will potentially affect all of the agents in the system right so you know when we're thinking of auctions for things。

 you know selling them on a Lisa。Presumably， you know。

 only one person is getting the utility from it， the person who gets it and maybe it's natural to model things says agents not caring about the outcome chosen if they don't get it。

 they really only care， I only care in the auction did I win or not， but in a public good setting。

 lots of people might simultaneously derive utility from the library。Okay。

 that fits into this setting as well and you can imagine all sorts of other applications。 Okay。

 so at the level。At which we've defined things， this mechanism design setting is extremely general。

So it makes sense， questions about the general setup。Yes。Its like each person have an evaluation。

That's right。 Yeah， so conceivably， the valuation functions could get complicated， right。

 like the way weve defined things。The valuation function is a mapping from alternatives to numbers。

 and if the set of alternatives is the set of all ways of dividing up a large collection of goods to and bidders。

There's a lot of them， in principle， you might care not just about the subset of goods you get。

 for which there's already exponentially many choices。

 but the subset of goods other people get in this setting。So yes。

 like like and this will be sort of related to。Later lectures where we worry not just about the kinds of classical results we're going to talk about today。

 but sort of computational constraints this is a good thing to notice that the objects we're talking about in some of these settings could be really complicated and computational problems over these objects could be tricky。

Good other questions。I like to deliver this whole lecture before the computer shuts off in 40 minutes。

嗯。O。So。We're going to the mechanism design portion of the course， we're going to design a mechanism。

What is a mechanism？It's just a fancy word basically for an algorithm that maps。Reports。

 agents reported preferences to outcomes。Okay， so so the sort of type of a mechanism， right。

 remember bidders agents have these these evaluation functions。They will。

Report them to the mechanism， they might lie， they don't have to tell the truth。

 but they're going to report their evaluation functions and based on those reports。

 the mechanism is going to choose an outcome。Okay， and now remember。An outcome is a pair。

 it's a tuple， it's a set of， on the one hand， it's an alternative chosen in the mechanism design problem。

And on the other hand， it's a vector of payments saying how much each of the bidders needs to pay。

And so it's going to be useful for us to like divide these two things up when thinking about it。

 we can think of a mechanism。As really a pair of two algorithms。

The first one is we'll call it the choice rule。And it takes as input vectors of reports。

 a supposed valuation function for each of the N buyers， and it chooses an alternative。

Whether we build the library or the hospital who gets which bundle of takeoff or landing slotbs？

And then separately， there'll be a payment rule， which takes the same input， the recorded valuations。

 one from each bidder， and decides who has to pay how much。

So it outputs a vector of payments that we're going to collect from the buyers， again。

 one for each of the and agents。Okay， make thanks。Okay， so， you know。

 like we could choose these in arbitrary ways， any choice of these two functions。

 a choice rule and a payment rule will yield some mechanism。And the question is like， you know。

 like what do we want， like what are the， you know， if we're designing a mechanism。

 if we're designing a choice rule and a payment rule， what are the what should we shoot for。

 what are the things we could want？And so。What I want to start off by doing is sort of like just。

Jotting down like a wish list， an optimistic wish list of all of the things we might want to ask for from a mechanism and you know。

 like maybe if we're lucky， we can get all of them at the same time。Okay。

So we'll start with some sort of simple things that are related to。Things we've already asked from。

 for example， the top trading cycles， algorithm and the。嗯。Deferd acceptance algorithm。

 but let me restate them in our setting now that we're using money because their statements are just going to be a little bit different。

So the first thing we want is called individual rationality。

 and if you remember this is sort of like a safety property， it should say like。

Theres you will not come to harm by participating in the mechanism。

 like whatever outcome is chosen by the mechanism， your utility will be non- negative。

 we won't do anything that will cause you to have negative utility sort of assuming that your outside option of not participating in the mechanism will just give you zero utility。

Okay， and so。In this setting。It just means that。For every。

Report for every vector evaluations that might be reported to the mechanism。

 So for every vector evaluations that your opponents report and。For the evaluate。Okay。

or whatever your true valuation might be if you report that to the mechanism。

If we look at the alternative chosen by the mechanism， the thing chosen by the allocation rule。

 your value for that thing will be at least the amount of money we ask you to pay。

So we're never going to ask you to pay more than the value of the thing we gave to you。

 at least according to your own report for what the value is。Okay， so it might be that if you lie。

 I'm auctioning off this dongle， you say it's worth $100 million。

To you and you're trying to get one over on me because it's only worth $2 to you。

 you know then I give it to you and I tell you to pay me yeah $50 million there's no promise against that the promise is that i'm never going to ask you to pay more than you told me the outcome was worth it to you。

O是是。This doesn't yet tell me that you're incentivized to report the truth。

 but it does tell me that like， if you are going to report the truth， then。

Nothing bad is going to happen to you， you'll be at least as well off as if you hadn't participated in the auction at all。

Okay， so this is sort of like a minimal requirement。

 if we design mechanisms that are not individually rational。

 then people are not going to participate。Okay， make sense。Yeah。Okay。Well。

 like suppose you enter this auction and you're like， oh。

 you know this dongle looks like it's worth $5， I'll bid $5 and I say okay。

 you know congratulations you're the winning bidder， here's the dongo。

 you pay me $10 that would be a violation of individual rationality and you would have regretted like participating in this auction this is saying I can't do that if you say it's worth $5。

 the amount of money that I can ask you for has to be like less than $5。Makes sense。Yeah。

Gbe a chance that。Thank。So I guess the question is on average over。

 so we're going to be talking about deterministic mechanisms。But if there's randomness involved。

 you could define。Sort of a version of this the over the randomness of the mechanism I could put an expectation on the left hand side on the right hand side。

 this is sometimes called x interim individual rationality when you get into randomized mechanisms there are differences between x n and x post and x interim rationality which basically depends they basically sort of ask at what point we're taking the expectation but。

We're going to in the world we're talking about today， everythings deterministic。

 and so it just says， you know。Given the report something is going to happen for sure。

 i'm going to ask you to pay some amount of money for sure it should be less than you said the outcome was worth to you does that makes sense。

But yes， there could be in more complicated situations like a risk neutral person might be willing to take some risks long as the upside outweighed the downside。

Okay， good。🤧So。Okay， so individual rationality sort of tells us， okay。

 like people are willing to participate in the mechanism， they won't come to harm。

 but we want more than that we would like。People to actually tell us what their valuation functions are。

 again， remember because。Down the line， we're going to be optimizing some objective function like we're going to be trying to maximize special welfare。

 for example， distribute takeoff and landing slots among airlines so that as many people as possible you know。

 can get home for Thanksgiving or whatever。嗯。And so。In principle。

 we can solve whatever algorithmic problem we want to allocate goods， for example。

 to maximize whatever objective we want， according to the reported evaluations。

But if the reported valuations are not equal to the real valuations because people are trying to game the system and our misreing。

 we won't have really obtained our objectives。And so。

Another goal we'd like is we'd like to design mechanisms so that people cannot game the system so everyone is always best off by truthfully reporting their values。

 because then whatever we optimize for on the recorded values will give us what we wanted on the true value。

So a mechanism is dominant strategy truthful。In the game induced by the mechanism。

 it is a dominant strategy to report your true valuation。Okay， and just。Reateated in our model。

What that means is。No matter what the other agents did。

 right so for every vector of reports of sort of valuation functions for all of the other agents。

No matter what your evaluation is， and no matter what alternative valuation you might be considering misreporting to the mechanism。

If we look at the utility that you get when you tell the truth， which remember is just。

The value for the alternative chosen when you tell the truth minus the payment you're asked to pay when you tell the truth。

This should be larger than the utility that you get when you missre。

Which is just the valuation you get for the possibly different alternative that would be chosen。

 had you misreported， minus the possibly different payment you would have had to make had you misreported。

Okay， so just in the game induced by this mechanism。

 it should be a dominant strategy to tell the truth。Makes sense。Okay。

So so far we've got individual rationality that makes it safe to participate we should be able to get people to participate in our auction we've got dominant strategy truthfulness they're going to tell us the truth so what you see is what you get like we know。

How much everyone likes each alternatives at the time that we do the optimization？

What should we optimize for。Well， there's different goals we might have and we'll talk about other ones later in the course but。

Maybe the simplest one is what I'll call allocative efficiency or just social welfare maximization。

Great a natural thing to optimize for in a lot of settings is you know making people in aggregate as happy as possible。

 choosing the alternative that maximizes social welfare， which is the sum of their values。Okay。

 so a mechanism is allocatively efficient。If no matter what bids come in。

 no matter what vector evaluation functions are reported to the mechanism。

 the alternative chosen is always the one that maximizes social welfare。

 it's got higher social welfare than any other alternative we could have chosen。Okay， so of course。

 in an auction we might care about other things like revenue we'll talk about that later in the class。

 but in all sorts of settings like if we're deciding how to invest the resources of our city into libraries and other services or if we're。

You know， figuring out how to allocate radio spectrum across the United States， for example。

 or take off in landing slots， we might care about social welfare。哎。Good so far。Yeah。

So last class you know， there was no mechanism we were studying this sort of dynamics in this in this market game。

 but what we showed is that。These sort of natural ascending auction dynamics。

Converge to a market equilibrium or all race equilibrium。 and that。Sort of amazingly。

 while racing and equilibrium are welfare maximizeimizing right。

 so the natural dynamics from last class sort have said， okay。

 like if what you want is allocative efficiency and everyone。Has unit demand valuations。

 at least or or you know， at least or substitutes valuations long as the settings is not too complicated。

 we're just sort of assigning items to people with simple valuations。

maybe you don't need a mechanism， maybe sort of natural price dynamics take you to allocateative efficiency anyway。

Here we're talking about a broader setting but the goal is sort of still the same， makes sense。Okay。

 one more thing， maybe。The way weve defined things like the payments could be positive or they could be negative。

 right， we could be collecting payments from people or we could be paying out others。

And you sort of might imagine that。If some of our goals are things like individual rationality。

 we want to make sure that。We never。Choose an alternative and then ask someone to pay more than。

Ask someone to pay more than they said the alternative was worth to them that an easy way to achieve that might be to just like shower everyone with money。

But that would be expensive， so another thing we want is that our mechanism should be no deficits like we。

 the auctioneer， should not have to pay money to run the mechanism。Which just means that。You know。

 I'll allow that there are transfers like I might pay some people and collects money from others。

 but。What I want is that no matter what set of valuations are reported。

 if I sum up over all of the payments， it's not negative。

 like in aggregates money should be coming to the mechanism designer not going from the mechanism designer to the population。

Okay， so this is like。The weakest possible revenue goal you could have。

 it just says you shouldn't lose money by running the auction。Yeah。在争议呢。P is the payment that。

The mechanism makes to PI as the payment the mechanism makes to agent I， this is saying。

 but they could be negative， which means the mechanism pays agent I。被上。Yeah。

 it comes up with these payments as a function of the reports。

 but it's saying no matter what the reports are， in aggregates money should be coming into the mechanism not going out for it。

ok。All seem like reasonable doeserta。Okay， so maybe let's start by going through。

Maybe the simplest possible example of a mechanism design problem， which is just a single item off。

Okay， so I've got this dongle， I would like to sell it to one of you。

So how do we embed a simple auction like that into this setting？Well。In this case。

 a set of alternatives is just the set of agents， there's one alternative for each of you in this room and it just corresponds to who is going to win the auction and get this dongle。

诶。And。In principle， you could have still complicated evaluations， maybe not only do you。

Like the dongle but maybe you've got like friends and enemies in the class that you really don't want your enemies to get it and you're going to be happy to differing amounts depending on which of your friends get it。

 but let's assume there's a simple setting where you you know really like。

You only care whether or not you get the item。If you don't get the item。

 you don't care who else gets it。This will be sort of a nice single dimensional setting。

Where really like your value for this。I can think of your value for the thing I'm selling as like a single number。

Like VI， that's going to tell you how happy you are if you get this item。And like， implicitly。

I'm going to like abuse notation and say that your value for this item is VI。

 But what I mean by that is your valuation function is。The following， if you get the item。

 you get utility V， and if you don't get the item， you get utility zero。Okay， so like。

VI is how much you like the dongle， if you get the dongle， you experience joy， you know。

 that has magnitude VI， and if you don't get the dongle。

 it's utility zero and you don't care who else gets。Okay， so sort of natural。

 simple valuation functions for a single item auction。

And so let's just like go through all of our desireerta and think， like， is there a way to achieve？

All of them at the same time， like starting in this simple case of single item options。Okay。

 so so in some sense， right， what do we need to do， we need to design。Two objects。

 an allocation rule and a payment rule。But if we're going to try to achieve all of these deerra at the same time。

We don't have any control over the allocation rule。

 our hands are tied right like if we're going to be allocatively efficient。And truthful。

Then we have to。Give the item to the person who says they want it the most。

Because if everyone's telling the truth。The way to maximize social welfare is to give the item to the person who wants it the most。

So we don't have any choice about what the allocation rule is going to be if we're going to satisfy all of these desideerrata。

 the allocation rule has to give the item to the person who reported the highest value。

So all of the action is going to be in designing the payment rule。So let's think。

Individual rationality is going to constrain us a bit more。In this setting。

 remember anyone who doesn't get the item。Gets value zero。嗯。

So that means we can't charge them any money， otherwise that would violate individual rationality。

Now， conceivably， we could pay them money。But like that seems like a bad idea。

 especially if we want to be budget balanced。So。Why don't we like？Guess at this moment， you know。

 not that。We're sure yet that it's not necessary to pay the money。

 But why don't we guess that like the right way to handle people who don't win the item is to just。

Charge them $0 and not pay them anything either。So if that's correct。

The only thing remaining in our design space is how much money to charge the winner。Okay。

 like the question， the only thing left to decide is what we should charge the winner。

Of this dongle when they win。Now， we know we have some constraints on this， right。

 Like individual rationality tells us that we can't charge them more than their value and budget balance tells us that we。

Can't charge them a negative amount。But we've got some freedom in between zero and VI。

So let's try some。Alternatives。So maybe the first。Gues is that。

We should charge them exactly their reported value。Okay， everyone bids on this item。

 someone in a high bidder bid $63， I say， congratulations you win。Here's the dongo pay me $63。

 It know。29 minutes。There's no cancel action。And this I can only snooze it for 15 more minutes now。

 and there's no X。What do you think is going to happen？You do not click take action to initiate。对。

Like should I just like take the should I do it now？I got to students。Okay， great， yeah。

 I'm not you know what， I'm not using office， this is Acrobat。😊，Good， okay。嗯。😊，Okay。

 so what do we think if I charge you your reported value。

 does that satisfy dominant strategy truthfulness？Yeah， like in a real same thing。You just。按照。Yeah。

 exactly like suppose my plan is I'm going to give this to the Hyyatt bidder and I'm going to charge them the number they told me。

And suppose you in your heart of heart you know， realize that like this is going to bring you a lot of joy。

 it's worth $64 to you everyone else thinks you know this is probably like a decade old what do I want with this I'm getting zero and I say you're the winner you get it。

 you pay $64 to me。When you realize that everyone else bid $ zero， you're。You have regret， right。

 like he realized you could have bid like 1 or even 1 cent and still gotten the item， but paid less。

So it's not a dominant strategy to bid your value if I'm going to ask you to pay your value。😡。

If in the event that you win， I'm going to ask you to pay your value， then no matter what happens。

 you get utility zero， either you lose and your value for the alternative chosen is zero or you win and you experience your value。

 but then you have to pay it right back to me。And。There are outcomes if you're the high bidder by some margin。

You could have gotten positive utility by lying and saying that you valued the item less。

 you still want to be the high bidder so you know so you can't report an arbitrarily lower value。

 but like ideally you're going to report just epsilon more than the second highest bidder。Right so。

If I ask you to pay your value， this does not lead to an incentive compatible auction。😡。

RightAnd it might you know like it it's not clear what you should be like it' it's clear that you don't want to bid your value because then you're going to get utility zero。

 but unless you know what all the other bids are it's not exactly clear what you should bid right so people might strategize in sort of incompetent ways and I might end up giving the item not to the person who wants it the most because maybe the person who wants it the most。

Didn't bid them up。Okay， so this is called a first price auction and it's not incentive compatible。

Yeah。Try again。So what if I？Give the item to the high bidder。

But I charge them the second highest bid。Okay， so I say， okay， you know， high bidder $64。

 you're the winner， the second highest bid was a dollar。So you win the item。

 but you only pay me a dollar。 Okay， the payment rule is I will give， I will。Pay the winner or sorry。

 the winner will pay me。The value of the highest bid excluding their own， the second highest bid。ok。

😊，How about this， is this a dominant strategy truthful mechanism？I say some nods。

Does anyone want to venture an explanation？Let's think about it。You're the high bidder。

 so you've won， I've asked you to pay the second highest bid。

Is there anything you can do to improve your utility？Well。You could try bidding higher。

That wouldn't change the outcome at all， you'd still be the high bidder and it wouldn't change the amount you'd have to pay because raising your bid hasn't changed what the second highest bid was。

You could also bid lower。Now if you bid lower and we're still the high bidder。

 you haven't changed the outcome again， you're still the high bidder and you haven't changed what the second highest bid is。

 and so the outcome is unchanged， you're no happier having bid lower。

Or you could bid lower to the extent that you were no longer the high bidder。

But now the outcome is worse for you because previously you won the item and were paying less than your bid。

 You were getting positive utility。 if you reduce your bid so that you're no longer the high bidder。

 now you lose the item and you get value 0。 So if you are the high bidder， you can't。

Ever improve your utility by bidding higher than your value or by bidding lower than your value。

 So for the high bidder， at least， truth telling was a dominant strategy。

Now how about four bidders who didn't win the offsha？Well， they can lower their bids。

 they still won't be the high bidder， they still won't win the auction that doesn't change anything for them。

They can raise their bid， but not you， to an extent that they're not yet the high bidder。

They still don't win the item that won't change anything for them。

And if they raise their bids so high that they are now the high bidder。They win the item。

But they have to pay the second highest price， and the second highest price is the bid of the bidder who previously was the high bidder in particular。

 had value higher than you。And so。You do change the outcome by raising your bid to be the high bidder。

 but only at the cost of having to pay something higher than your value for the item and so if you do that you'd have negative utility and so that's not a good idea either。

Okay， and so if I the second price auction。In which I give the item to the high bidder。

 but only ask them to pay the second highest price， that one is dominant strategy truthful。

It's a dominant strategy to tell the truth， to report your true bid for the item in a way that the first price auction was not。

Does that make sense？ok。😊，And so the second price auction。

also like it we didn't pay anybody right like if you didn't win you paid zero， if you did win。

 you paid us the mechanism， some amount of money， the second highest bid。

And so it's also no deficits， like the money is coming into the mechanism， not out。

And so this second price auction， which。Has a name， it's called the victoryy Auction。

 this actually satisfies all four of the desideerrato we set out， it's individually rational。

 someone it's strategy truthful， it's allocatively efficient and has no deficit。嗯。😊，Note， by the way。

 like if you've seen like oldtimey TV shows like you've probably seen like auctions where there's a guy with like a gavel or something and like people。

 he speaks incomprehensibly calling out ever higher numbers and people hold flags up or something and you hold your flag up。

 you know while you're still willing to pay the price。

 but then you know when when the ascending price， the number。

 you know being spouted out by the auctioneer gets higher than you're willing to pay。

 you put your flag down and the auction ends when there's only one person left that has their flag up。

That's like called an English auction， it's an ascending price auction。

And note that it implements exactly the same outcome as the Vi action。😡。

The person who wins is the one with the highest valuation because they're the last man standing。

 they're the one who still have their flag up at the end。But。The auction stops。

 the price stops going up。😡，When。The second to last person puts their flag down。

And so the price that the high bidder ends up paying。Is the value of the second highest bidder？ok。😊。

Right， so even if you haven't seen。Described in this form before the sort of second price。

 that auction， Everyone reports a number。 The winner gets the item and pays the second highest price。

 This is actually implementing。Like the classic TV auction， like the ascending price English auction。

That makes sense。Yeah。😊，Thank you。本院。So kind of case by case with a person that's not the that fit so that's below and how they could raise their。

Price above the map did so then they would get it。How did we know that it was going to。

That their utility would be that they would be paying more。

So we're thinking about whether they want to deviate from truth telling to reporting something higher。

So the premise was when they told the truth， they were not the high bidder。

whohoever was the high bidder。Ha their bid was higher than your actual value for the item。And so。

You could raise your bid above your value for the item， and at some point you'd be the high bidder。

And what would you have to pay， you'd have to pay the bid of the person who previously had been the high bidder。

But their bid was higher than your value， that's why you weren't the high bidder when you were telling the truth and so you have to pay more than the item is worth to you。

That thanks。It you that。FittterPrevious was like that wasIt doesn't matter whether they were telling the truth。

What matters is that when you were telling the truth， you didn't win。

Which means that their bid was higher than your value。Does that make sense？Great。ok。By the way， like。

We got so much like lift from going to like a first price auction to a second price auction。

 what if we keep going， right？What if we keep doing it。Consider the third price option。

 the highest bidder gets the item and they pay the third highest bid， iss that a truthful mechanism？

Yes，这孩的。Yeah， exactly it's not a truthful mechanism because suppose I'm the high suppose I'm the high bidder and you're the second highest bidder。

 but I'm only paying。The third highest price。Well you could raise your bid try to be the high bidder and you'd like to pay the third highest price that's less than your value and you know I'd want to outbid you and so like there's not even any equilibrium to this thing like the top two bidders would sort of like go to infinity and the third bidder might want to get it on the action too。

Okay， so the third price auction is not a truthful mechanism。Only the second price option is。Okay。So。

We laid out these four deitta。And in this like super simple case of a single item auction。

 we managed to achieve all of them at the same time。嗯。So let's see if we can do that for everything。

 like just for the entire general mechanism design problem I defined at the beginning。

 this extremely abstract general setting where there's an arbitrary set of alternatives。

 an arbitrary set of valuation functions， like can we always get all of our deiterrata just as the second price auction was able to you get them for us in the single item auction case。

是。Okay， so let me tell you about something called the Groroves mechanism and really this is not a single mechanism and this is a family of mechanisms parameterized by some function。

😡，H， that you'll see in a moment。Okay， so the Groroves mechanism， like all mechanisms。

It's two things really， it's a choice rule like an all yeah I have to map bids。

 reported valuations to alternatives。And a payment rule。And remember。

 our goal is to satisfy all four of our deiterta， so just like in the single item auction case when we were designing our mechanism。

 we sort of noticed like we didn't have any room for design in the choice rule if we want to be allocateocatively efficient。

Oh， the same thing here， like if we're going to be allocatively efficient。We have no choice。

 the alternative we have to choose， given the reported evaluations must be the alternative that maximizes social welfare。

Okay， so。We're stuck with that unless we're going to give up on maximizing social welfare。

 all of the action is in the payment rule。Now， the payment rule。Well look like this。

The amount of money that bitter eye will need to pay。Is some function H？

Of the bids of the other bidders Okay， so H we'll see in a moment can be anything like you know that's why this is a family of mechanisms H could be whatever you plug in no assumptions at all about what H is。

The only important thing about H is that it does not depend on your bid。

H is a function of everyone else's kids， but not of yours。Okay。

 so you'll pay this mysterious function H of everyone else's bids。

But actually you won't pay quite that much， I'm going to subtract something off from the payment。

 what am I going to subtract off？Well。It's the sum of the values of everybody else。

 everybody who's not you。Of the social welfare maximizing alternative that was actually chosen。Okay。

 so our mechanism。Chose this alternative a star。Everyone has some feeling about that。

 you've got a value for it， but so does everybody else。

What I'm going to do is I'm going to sum up everybody else's value as they recorded it for the alternative I chose and subtract that off from your payment。

ok。😊，And that's。And mechanisms that look like this are groves mechanisms。

 The reason it's not the Groroves mechanism， but Groroves mechanisms is because。

We could plug in whatever we want for each here。Okay， is this？Are the definitions clear。

 like at the moment， it should be entirely opaque and mysterious why we care about this funny looking payment rule。

We'll get to that in a moment， but is it clear at least， you know， like how the mechanism is defined？

Yeah， is not just higher the person the payment is going value every other person well this is negative remember。

 so the payment is going to be you know it's going to start out that this mysterious function H of the other reports。

 but then I'm going to subtract off for a minute。The values of everybody else。

For the alternative chosen。Not necessarily。I mean we'll have to analyze it。

 but like it definitely won't be positive for all Hs， right。

 like if I I could plug in a value of H that's negative， for example。

 and this would definitely be negative。Okay， to make sense。

So it's not that the mechanism should make sense to you yet。

 like we haven't talked about why things are defined this way。

 but I just want to make sure the definition is clear。Yeah。Okay。Okay， so what I want to。

So the Grorovs mechanism will not on its own。Satisfy all of our deiterta as I've defined it， because。

 for example。If I can really plug in anything for this H function。

 the payments could always be negative， so it like definitely definitely。

Is not always going to satisfy the no deficit property。But。What I want to do is I want to say， look。

This family of Groroves mechanisms， no matter what H you plug in。

Therere always going to be dominant strategy incentive compatible and allocatively efficient。And so。

If we want to get all four of the properties， once we establish this， we can。

Choose H to satisfy the other property。😡，Okay， and our choice of H will not interact with the incentive properties。

Because we're going to show that the mechanism is dominant strategy truthful for every choice of age。

Okay， so it's just going to decouple these things like in general， you might worry about choosing H。

 like in some ways would。Satisfy some of our deer deiterta in other ways we satisfy others。

 we're going to。Free ourselves of that worry by saying。

 no matter how you choose H it's going to be dominant strategy instead of compatible and so you can freely explore the space of H's to try to satisfy the other dera。

Okay。So the growths mechanism is dominant strategy incentive compatible and allocatively efficient。

 it's like definitely allocatively efficient because that was how we defined it like the allocation rule just chooses the alternative that maximizes social welfare。

So the only thing to check is that it's actually dominant strategy instead of compound。ok。So let's。

Think about that。So suppose is your agent， I。And we're fixing how all of the other agents are bidding the reported evaluation functions of all of the other agents exist。

 you're deciding how you should report。So let's say that。

A star is the alternative that maximizes social welfare given the reports。Okay。So if you。

And this is really a function of your reporting。Right because the mechanism doesn't know what the actual social welfare is。

 the mechanism is maximizing social welfare。Given the reported valuations。

It's going to choose A star as a function of your report。You can affect what your report is。

 not what the others are。But the mechanism will choose the alternative A star that appears to maximize social welfare given your report。

Now what's your utility going to be？Well， your utility is going to be your value for the alternative chosen。

 your real value for the alternative chosen， not your reported value， okay。

 your real value for the alternative chosen minus the payment rule。Now what's the payment rule？

It was this function H of everyone else's bids。Minus。The sum of the values。

Of everybody else for the alternative chosen， so since we're subtracting off the payment。

 your utility。Is your value for the alternative chosen plus the sum of everybody else's values for the alternative chosen minus this funny function H of everyone else's reports？

Now。Your job at this point is to choose the report that will maximize your utility。

So a couple things to note。So first of all， we don't know much about this H function。

 but we know that it is not a function of your report。

 it's only a function of everyone else's report。So it's true that your utility depends on this H function。

 but you can't control。That H function。 and so if you are thinking about maximizing your utility。

You might as well just maximize the first part of this。

Like you're just going to maximize your value for the alternative chosen。

 plus everyone else's value for the alternative chosen。

 because that's the part of your utility you can control。Noe also that。

You can affect your utility only through the alternative chosen。

Like if you lie about what your evaluation function is。

 that doesn't actually change how much you value the item that you get。

It only affects what the mechanism thinks you valued the item and therefore what the alternative chosen was。

So your ability to affect this is only through your ability to change what a star is。Now。

 what is this expression？It is just the sum of everybody's utility for the item。

 everybody's utility for the alternative chosen。Right it's the thumb of。

Everyone else's reported valuation for the alternative chosen plus your real valuation。

 for the alternative chosen。But a star is chosen。To maximize an expression that looks like this。Well。

 an expression that looks a little bit different than this because。

It's still summing up over everyone else's report。But it doesn't know what your real valuation is。

 it's maximizing social welfare according to your reported valuation。

But what you are led to care about because of the payment rule。

Is social welfare according to your true valuationuator？So if you report your true valuation。

 the mechanism will choose the alternative that maximizes social welfare according to your true valuation。

And that is what your utility function。So your incentives are aligned with that of the mechanism。

And so it's a dominant strategy for you and everyone else to report truthfully。Does that make sense？

Like basically， what's happened here？The payment rule has caused you to care about social welfare。

Because it subtracts off the portion of social welfare that comes from people other than you。

And so the allocation rule maximize if the allocation rule maximizes social welfare and your incentives are now through the payment rule aligned with social welfare。

 you want to help the mechanism maximize social welfare because that's what gets you the most fu。

Make folks。Okay， and that's really what's going on here。

 the particular payment scheme of the Groes mechanism。

was designed to align the incentives of the agent that were initially incompatible with one another。

 they only wanted to maximize their own utility with the incentives of the mechanism designer。

 the payment rule caused the utility of the agent to be equal to social welfare。

 which they could choose to maximize by truly reporting by reporting their true valueu。Okay。

 is that clear？So。For every Groroves mechanism， right。

 no matter how we've picked this unspecified H function。

It will be a dominant strategy for people to tell the truth。Okay， so。Remember， we had four toitderta。

 we wanted the mechanism to be truthful and allocatively efficient， so we have that。

But we also wanted our mechanism to be individually rational and budget balance that's not necessarily going to be true for every age function。

And so。Like the question is， how should we pick this H function to achieve all four of our dederrata？

And maybe we can。Try to build some insight by going back to like our case study of a single item。

So remember the single item auction， I've got the dongle for sale。

 the set of alternatives chosen is the set of people in this room who could win the item。

Let's start with a simple choice， what if this H function is just like identically zero？Okay。

 it's a simple H function。Let's just work through what's going to happen in the mechanism。

Suppose we've got two bidders， maybe one of them values the dongle at $5。

 the other one values it at $8。And perhaps that's how they bid。So if they bid truthfully。

 I look at the bids and I give the item to the person who had the highest bid。 Well。

8 is bigger than5。 So that means that。My allocation rule is going to decide to give the item to bidder two is the high bidder。

And what does my payment rule do， well remember？If H is identically zero。

The payment rule pays each person the negative。Of the sum of the values of everyone else for the alternative chosen。

Now if there's just two bidders， this is just。The negative of the other guy's value for the alternative chosen。

So。In this case。Well。Bitter 2， Biter2 is the high bidder。

The other guy lost the item and so has value zero， so the payment for bidder 2 is zero。

And for bitter one， he lost the item。The other guy Bi two won the item。

 his value for the alternative chosen is eight。And so his payment is negative8。And so the mechanism。

 what it's doing is it's saying， okay， I'm going to give the item to the high bidder。

The high bidder bid$8 for this thing。So that the losing bidder is not unhappy。

 I will pay the losing bidder $8。ok。😊，So indeed， this is a。Dominant strategy truthful mechanism。

 like both bidders are happy with this outcome they both get。Utility 8。

The high bidder gets utility8 because he valued the dongle at $8 and he got it and he didn't have to pay me。

The low bidder gets utility8 because I paid him $8。

And there's no better alternative they could have gotten right like the low bidder doesn't want to have won the item if he won the item。

He's only going to get utility5 because he doesn't value the item at $8 and values it at $5。Okay。

 so like。It is dominant strategy truthful the way we proved it should be in this case。

 it's actually also individually rational。 I mean， not only can you not get harmeded by participating in the mechanism。

 like everyone should want to participate in the mechanism， like if you lose the auction。

I'll just pay you money。I never charge you money， it's a great mechanism to participate in。

But it badly fails the no deficit property， like the way I'm getting。

Individual rationality and the way I'm getting dominant strategy truthfulness is by freely paying people to participate in my mechanism。

And so it's not quite perfect yet。And so。You know， sort of like。To fix the。

 if we get the no deficit property， we need to choose H。You know。

 so that like it takes positive values， we need to make sure that we're taking in money rather than just giving it out。

But。We need to figure out how to do that without breaking the individual rationality property。

As soon as we start increasing the prices we charge。We run the risk of charging people more them。

Their value for the alternative， so that's the。Problem we need to solve。 We need to。Like。

Choose H functions that take values above zero， but without breaking individual rationality。ok。U。

So here is the VCG mechanism， the Viy Clark Grovees mechanism named after three gentlemen who won the Nobel Prize。

 and really it's just a Groroves mechanism with a particular choice of payment roll。

 a particular choice of H。Okay， so gets its own fancy name。

 but really it's just a particular choice of age。嗯。😊，And in particular。

 the VCG mechanism is just a Groroves mechanism where H is chosen as follows。

Remember H is a function of everyone else's bids， not your own。So what is this H？It's the thumb。😡。

Over all of the other bidders who are not you。Of the value they would have gotten。

For the alternative that would have been chosen。Had you not participated in the mechanism？Okay。

 so let's unpack that。So I'm defining this。Alternative that I'm calling a star minus I。

This is the alternative。That maximizes social welfare。When I don't count bitter eye。

OkayThis is the alternative that maximizes social welfare if I only consider the n minus1 bidders other than bitter I。

So if we consider the world in which bitter I does not participate in the mechanism。

 so there's only n minus1 bidders in the mechanism。

This is the alternative the mechanism would have chosen in that world。ok。

So what is the payment rule of the VCG mechanism？Would it ask you to pay the mechanism？

RightYou are participating in the mechanism， so it's choosing alternative A star。

If you hadn't participated in the mechanism， it would have chosen this other alternative。

 a star minus I。And what it's asking you to pay the mechanism is the difference between。

What the social welfare would have been amongst all of your。

Competitors in the auction had you not participated？Minus what the social welfare actually was。

For your competitors in the auction， given that you did participate。Okay， so like。

If you hadn't participated， the mechanism would have chosen an alternative that maximized welfare among everyone else。

Since you did participate。The mechanism chose a different alternative， one that maximizes welfare。

 including you， but might not maximize welfare excluding you。Right， so you sort of。

Through your participation in the mechanism。You sort of made things worse in aggregate for everybody else。

 because if you weren't in the mechanism， it would have chosen the best possible thing for everyone else。

And the VCG mechanism asks you to pay。An amount that quantlifies exactly how much worse you made thanks for everybody else。

The difference between how happy everyone else would have been， had you not participated？

Minus how happy everyone else was， given that you did participate。Is the definition clear？2。Okay。

 so another way of saying this is。What the VCD mechanism is doing is it's charging every agent。

Their negative externality on the market。Right。Like you changed things by participating in the mechanism。

In particular， by participating in the mechanism you chose you caused the mechanism to choose a different alternative。

In doing so， you may have harmed everyone else in aggregate。

 you may have made their aggregate welfare smaller。

And the mechanism is asking you to make up exactly that amount。Pay that amount。Okay， and so。

What we're going to show is that。This is a good idea that the VCG mechanism actually satisfies all four of the deitorta we set out at the same time in this extremely general。

Abstract mechanism design setting we defined at the beginning of election。Okay。

 so like the first two doesiterrado we get for free because this is a Groroves mechanism。

RightLike we proved that。Every Groroves mechanism is allocatively efficient and dominant strategy incentive compatible。

 and the VCG mechanism is a Groroves mechanism， right a Groroves mechanism had a particular payment rule where we could choose arbitrarily this function H and the VCG mechanism just chose this function H in a particular way。

😊，So in particular。You know， still dominant strategy instead of compatible。

 our proof that the Grorovess mechanisms were dominant strategy instead of compatible did not depend on what H was。

对。Okay， so we need to verify the other two properties。

 the individual rationality property and the no deficit property。

So let's start with individual rationality。So what we need to show is that。

We never charge an individual more money than the alternative that we chose was worth to them。

Or said another way that their utility for an alternative their utility for the outcome we choose。

 which is remember。Their value for the outcome we chose。Minus the payments。

We charge them for the outcome， right The negative of the payment is just。

The sum of everyone else's value。For the alternative actually chosen minus the sum of whatever everyone else's value would have been。

Haved they not participated in the mechanism？We need to show that this utility function。

Can never be negative。Now， equivalently。Just combining terms here。We need to show that。

The sum over everyone's valuation， the social welfare for the alternative actually chosen。Is larger。

Than what the social welfare would have been。Had agent I not participate。

Had age and I not participated， we would have chosen a different alternative。

And when computing social welfare， we would have summed up over only the n minus1 bidders other than agent I。

So we need to show that。Agentized participation has only increased the social welfare。But。

Valuation functions are non negative。The way we wrote things down。

 your value for an alternative could be like zero， but it couldn't be negative。

And so this has to be the case。Because。If it's not the case。You know。

 like consider what would have happened。Our mechanism chose a star because it maximized social welfare。

Could have chosen this other alternative， could have chosen a star minus I that was in the outcome space。

And if。We had chosen alternative A star minus I and computed the social welfare for that alternative。

 we'd summed up the valuation over all of the bidders。

That would have been only larger than if we had excluded bitter eye from this sum because in the worst case。

 bitter eye has zero utility for this alternative， but it doesn't have negative utility。

And if this wasn't the case。Well， that would mean that this quantity。

 the social welfare of bitter eye didn't participate。

Was larger than the social welfare of bitter I did participate some over everyones。

Utility for a star。Yeah。But if that were the case。That would mean that a star didn't maximize social welfare because there this。

 there's this other alternative that has higher social welfare。

And that contradicts allocative efficiency， we know that a star does maximize social welfare。

 that was how we chose a star。Okay。And so the mechanism must be individually rational。

The payments we charge people never exceed people's values for the alternative。

And that's because of the paymentve rule we chose and the fact that our allocation rule is maximizing social welfare。

Is that clear？Questions about this argument。Okay， there's one more property to check。

We need to make sure that the VCD mechanism is no deficit。

 that it takes in more money than it pays out。And in fact， we're going to prove something stronger。

 we're just going to prove that it never pays anybody， it only takes in money right。

 like no deficit allows us to take in money from some people and pay other people and we satisfy the no deficit property so long as in aggregate。

 we take in more money than we pay out， but we' prove in fact the stronger claim that the payments are always non negative for the VCG mechanism。

 it never pays anybody that only collect payments。Okay， so let's think about that。

What is the payment made by bitter eye？Well。You know，'s just remember。

It's the counterfactual social welfare that would have been attained。

 had bitterder I not participated at the sum up， the sum over the n minus1 other bidders of the alternative that would have been chosen had bitter I not participated。

Minus。actual sum valuations of the other and minus one bidders。

 given the alternative that was actually chosen。So this is non negative， just like writing。

 this should be at least zero and bringing this term to the other side。This is non negative。

 whenever。When we look at the social welfare， excluding bitter eye。

It's higher if we choose the alternative we would have chosen， had bitter I not participated。

Compared to the alternative， we actually chose。But what alternative would we have chosen had Bi I not participated？

Well， the mechanism always chooses the。Alternative that maximizes social welfare。

So had bitter I not participated， it would have chosen the alternative A star minus I that maximizes this term the social welfare given the n minus1 players other than bitter eye。

And so。Because。a star minus I is the maximizer of this expression。

 the left hand side must be only larger than the right hand side。And so。The payments are always。

non negative。And so the mechanism is no deficit。Does that make sense？Yeah。嗯。Yes。

 so both the left hand side and the right hand side are looking at。

Sort of like the welfare of the n minus1 agents other than bitter I at some alternative。Over here。

 it's the alternative that was actually chosen， given the bitter I did participate。Over here。

 it's the alternative that would have been chosen， hadbit or I not participated。

Now had bidder I not participated， the mechanism would have chosen the alternative that maximizes social welfare among the n minus1 bidders who did participate。

So it would have chosen the alternative that maximizes this expression。

To the extent that a star minus i is not the same as a star。

 it is because the left hand side is bigger than the right hand side。That makes sense。

So it's like related both to the payment rule and to the fact that the mechanism is choosing the alternative that maximizes social welfare。

And if bitter eye didn't anticipatesipate it， this would be social welfare。Makes sense。Yeah。

Just like when we said that theyre a negative exponentiality for the same。

That's right by participating， you're only making things worse for other people that you're not making things better for other people。

 otherwise the mechanism would have chosen that better alternative。

 even in absent your participation。So this is just saying your negative externality is positive or your externality is negative。

Okay， so V G mechanism is great like we wrote down these ambitious deiterta in a very general setting and we came up with a mechanism that。

😊，Thatatisfied all of them in this very general setting right it's not just single item auctions。

 it's you know multi unitit auctions with arbitrary feasibility constraints。

 it's public projects problems， like really any any problem you can really embed as a mechanism design problem in the generality that we defined it。

So like， you know， I don't know， it's only like mid March and got like another month and a half of class and it's all set for mechanism design like what else is there to do should we just like end the class here？

嗯。And not quite like you know， there's some more lectures to come。And。There's some reasons for that。

So maybe the most obvious is that。The VCG mechanism is really good if what you want to do is maximize social wealth。

That's what it does， and it can do that while managing incentives in any setting。

But there's other things you might care about if you're selling things， you might care about revenue。

 for example。And the VCG mechanism is not the revenue maximizing auction。

You will need like a different solution if you care about revenue。

And it's also not computationally efficient。And like we focus today entirely on the payment rule because。

Allocative efficiency， forced our hand with the allocation rule。

But we sort of just like we were like， all right， you know， like allocative efficiency。

 just choose the alternative that maximizes social welfare。But。If this is like a multi unit auction。

 where you know。Auctioning off bundles of takeoff and land slots at all of the airports at the United States。

The outcome space is huge and it has combinatorial constraints。

Like it might be hard to solve that problem， right。

 oftentimes just maximizing social welfare is going to be an NP hard optimization problem。

And so what do you do in that case？And whoops and。You know， if you've taken an algorithms class。

 you heard of things like approximation algorithms， maybe we can't like。

Exactly maximize social welfare。 But maybe if we can get a 99% approximation that's good enough。

 can we just throw that in。And we can't， you know， if you sort of reflect on the proofs of， you know。

 the no deficit property and the individual rationality property and even。

Even the truthfulness property。They all had this step that relied on the alternative chosen being the thing that exactly maximizes social welfare to control things like。

 you know， the left hand side is bigger than the right hand side。And all of that breaks down if。

 rather than computing the。Welfare maximizing alternative。

 you only get something that has welfare that is 99% of the maximum。

So if your allocation problem is NP hard。But you've got a good approximation algorithm for it。

 it's not just that by running that you're losing 1% of welfare。

You're losing all of the incentive property。Even the no deficit property。

 like the VCG mechanism might be completely nonsense in that case and might like just try to pay everybody。

嗯。And so we'll need entirely new techniques for designing auction。

 even when all we care about is welfare， when we have to deal with computationally hard optimization problems。

Okay。So see you guys next week。Yeah。

![](img/fdcbea832c29e271c6b6aba545c7591a_3.png)

Oh。