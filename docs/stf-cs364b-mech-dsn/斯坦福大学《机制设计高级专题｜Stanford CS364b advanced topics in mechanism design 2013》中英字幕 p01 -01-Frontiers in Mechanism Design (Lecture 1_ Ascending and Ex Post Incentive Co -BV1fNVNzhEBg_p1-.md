# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p01 -01-Frontiers in Mechanism Design (Lecture 1_ Ascending and Ex Post Incentive Co -BV1fNVNzhEBg_p1-

Alright， so welcome everyone， A C S 3，64 B。 It's a class called Topics and A in the game theory。

 It's a class which is not taught all that often。 It's probably been about five years since I've had the opportunity to do it。

 So this is about advanced topics on the interface of computer science and economics。 So quick poll。

 So who in the room has not taken 3，64， a。😊，Last quarter at some other time。1， any of those， two。

 Okay， so what， what's your guys's background， Like， do you have any experience with。Are you from C。

 S So for Econ or。They're from stats。You read through all the notes of the holidays， okay。

I hope you did other things too over the holidays。How are you， how are you。Okay。こ意が。Okay。Okay。

 so cool。 So I mean， the good news so that so， you know， I'm not gonna I realize it's I mean。

 I'm basically gonna give the lectures more or less assuming that you did take 364 a。

 know I realize a lot of that stuff has been a few months ago。

 which is a long time given all the classes that you've taken。

 I realize there's gonna to be rusty stuff。 I'll take that in account。

 The good news if you're really rusty or if you never took it all is there's a full archive actually from last quarter's class。

 So there's full lectures on YouTube and I finished all the lecture notes for all 20 of the lectures。

 And I'll try to remind you， hopefully most， if not all of you got the email I sent out Monday。

 So I'm gonna try to before every lecture just say you know what you might want to spend 20 minutes reviewing before before class just to make it a little easier to follow when I say in real time。

😊，So the plan for 364 B， pretty much the whole quarter we're going to discuss aspects of mechanism design。

And， you know， this is this is an advanced class。 So the focus is really gonna be to try to be on cutting edge stuff。

 Okay， so lots of stuff in particular， really just from the last five years。 I mean。

 the whole field of in the game theory is only about 15 years old。

 Most of what we covered in the fall was within the last 15 years。 But today or not today。

 but this quarter， it'll really just even give the last five years。 So what's mechanism design。

 So when I introduce this， I called this the science of rulemaking。

 you might remember the original sort of story I gave you about Olympic badmin。

 And then we proceeded to talk about lots of different applications， especially auctions。

 And just to remind you， the high level goal in mechanism design。you want to design systems。

Where you have strategic participants。 Okay， so there are users of your system。

And they're autonomous。 They can do whatever they want。 And in general。

 their objective is different than yours。 Okay， so， for example。

 we're gonna be talking a lot about auctions。 And as an auctioneer。

 maybe you want a efficient allocation of resources or maybe you want high revenue。

 That's not what the participants want。 They want to maximize the net utility。

 They themselves get out of the auction。 So there's a conflict there。And despite that。

 despite the fact you have these participants that are autonomous with different objectives than yours。

 you want your systems to have good performance guarantees。Perhaps high welfare。

 perhaps high revenue， we'll talk about a couple different examples。So that's that's the high level。

Of mechanism design， let me jog your memory with a specific case that we already understand well。

 And then we'll quickly move on to things that we don't understand so well yet。So scenario one。

Of the three that we'll discuss today。By the way， so the lecture format。

 So I'm gonna give one lecture， which is roughly ballpark 75 minutes。

 Then we'll have a 10 to 15 minute break。 And then there'll be a second lecture， which。

 again will be ballpark 75 minutes or so。 Okay， that's the plan for today and for the rest of the for the rest of the weeks。

 So we should wrap up by about 5 every time every Wednesday。Okay。

 so the first of the three scenarios we'll talk about today。

Let's assume that there's K identical goods。So maybe someone's unloading a bunch of old black iPhone 4 ss。

 something like that。So not worth that much these days， probably。

And you can go ahead and think about k equals1， what I'll say will be interesting even when k equals one。

 single item auction。And each bidder wants only one of these。

And it's important you know the terminology for this， this is called unit demand。Okay。

 so a bidder has unit demand preferences if they really only want one of the goods that's available for sale。

And each bidder has a private valuation v subbi。V sub buy is the maximum that bitter I would be willing to pay for one of these items by private。

 I mean that is known to this bidder， but it is unknown both to the seller and to the rest of the bidders。

 the other and minus1 bidders。And we want to think about the interesting case where the number of bidders N is bigger than the number of goods。

 K。Okay， so how do you solve this problem？ Okay， what do we want。

 So if we're interested in maximizing the social surplus。

 which is the objective function we're going to be discussing today in for a couple of weeks。

Then we use a variant of the second price auction of the victory auction。

Which I'll call the cavivic reaction。 this is something you saw last quarter。

So the vi is what's called a direct revelation mechanism。

 which means the very first thing you do is you're like， look bitter。 I don't know what you want。

 I don't know what your private valuation is。 So tell me。

You collect this information on the form of bids。So one per bidder。Again， bidders are economists。

 They don't have to tell you what they want。 They're just going to submit some bid BI to maximize their own objective。

Then in a direct revelation mechanism， there's an allocation rule and there's a payment rule。

 Remember， the fundamental decisions are who wins in your auction and what do they pay。

 So the allocation rule says given the bids expressed by the bidders， who wins。

 And so here we just pick the top K bidders。So give the goods to the K highest bidders。

What should the winners pay， Well remember in the single item auction， K was one。

 the victory auction for incentive reasons， we looked at the second highest bid when there's K copies of an item analogously。

 we use the K plus1 highest bid。 So if there's10 items， we use the 11th highest bid。

 the highest bid of a losing bidder。So charge all winners。The K of1 highest bid。

So that's what I'm going to call the K victory auction。

Let me remind you the basic properties of the caVic reaction and why we like it， in fact。

 in the fall we deemed this an awesome auction。So why did we call it that？Well。

 so it has good incentive properties， it has good performance properties。

 and it has good tractability properties。So by incentive properties， the formal term。

It's a bit of a mouthful。So a dominant strategy。Instead of compatible。Or D6 for short。And so， the。

Main condition here is that revealing your private information that is setting your bid B to your private valuation V sub by is a dominant strategy。

 a foolproof strategy。 Remember， that means it maximizes your utility。

 So the value you get for the good。 if you win it， minus the price that you pay。

 It maximizes your utility， no matter what the other bidders do。

 So it frees you from having to reason about what the other bidders want and how they behave。

 You don't care。 You know your best response， no matter what。So truth forbidding a dominant strategy。

Meaning， it's guaranteed。To maximize。Some other things， the quasiline utility。So remember。

 this is your value for the good if you get it。This is the notation I'm using for the allocation rule x sub I of the bid vector B。

 So this is one if bidder I is a winner。 that is if it's in the top K bidders，0 otherwise。

And then we subtract out what it has to pay， okay， which is zero if it loses or the cap plus one highest bit if it wins。

So this is something。 This is a property we approved last quarter。

 I'm not going to prove it again now。 And then the other parts。

 which we don't mention as much because we almost always have it is what's called individual rationality。

Which is that truthful bidding also guarantees。Non negative。Utility。Okay。

And the reason you're guaranteed non negative utility with a truthful bid is that the price that you charge a winner is always at most the bit of that winner。

 right， So you take the people with the K highest bids and you charge them all the K plus one highest bids。

 So you charge them less than their own bid。 So if the bid is truthful。

 then this quantity is non negative。So those are the incentive guarantees of the cavicic reaction。

 That's number one。So what are the performance guarantees？

So if what you want is an economically efficient allocation of resources。

 meaning you want to maximize the surplus， then even though you didn't know what people wanted in a advance。

 even though the seller had no knowledge of these valuations。

 this is something you get after the fact， assuming bidder is bid truthfully as they are incentivized to do。

So the CVic reaction maximizes the surplus。I'll also probably sometimes call the surplus the welfare。

Which in this context is just the sum of the bidders。Of their value for the good， if they get it。

And this is assuming truthful bids， of course。So because you only have k copies of the item。

 you can only set X K of the x sub I is equal to1。 And if you want to make this as big as possible。

 of course， what you should do is give it to the ones with the biggest Vs。 If the bids。

 the V I is equal to Vs， the V Is， well， then that's exactly what the。Cebic reaction is going to do。

So that's the second thing。 And then the third thing。Is that it's a simple slash tractable auction。

 and I'm going to be pretty vague for the first couple of weeks about what a simple option is。 this。

 for any definition of simple you can think of this pretty much qualifies。

 certainly it's polynomial time。Okay。So polynomial time and simple。Okay。So looking ahead。

 what we're going to talk about for at least the first half of the class。

 maybe even a little bit more is to what extent can we get all three of these properties more generally for more general settings that we might want to solve。

 And so we're going to start with a couple weeks about the happy special cases。

 although still much more general than scenario number one。

 where we can just get all of these things。 we can get all the incentive guarantees we want。

 all of the performance guarantees we want and all the tractability guarantees that we want。

 And there are a number of interesting cases in the theory is very nice。

Then we'll move on to cases where we'll be able to prove you cannot get all three of these。

 at least not this strong version of all three of these types of guarantees。

 and we'll spend some time exploring the various compromises and trade offs between them。

 So at a high level， that's what the first roughly half of the class is going to be about。

So any questions at this point？What I've said so far， I hope is review for you。

 Now I want to move on to things which are not difficult。

 but which you didn't talk about explicitly only alluded to in the fall。

So what I want to talk about next and what's going to be。Our obsession today and next week。

Are ascending implementations。Okay。And so。Rather than try to give you a formal definition。

 let me just show you what I mean by an ascending implementation for this particular problem。

 for scenario number one。Then we'll take a step back with that concrete example and say。

 why might we care about this， and then we'll ask what would a theory of ascending implementations look like because of the next few things we're going to do。

Alright， so for this special case of scenario 1， where you just have identical goods， Again。

 think of cake or one if you want。And unit demand bidders。

 the ascending implementation is just going to be the familiar what's called the English auction。

 this is what you would have seen in the movies。 or I got to see an art auction at Christies last year when I was on sabbatical in New York。

 and that's what they still use at those auction houses。

 And so here you don't have people writing down bids and envelopes and submitting sealed envelopes sealed bids rather they have an auctioneer。

 and there's some item being sold and the price starts very low and lots of people wanted it this low bargain price。

 but then they keep raising the price。 And at some point， there's only one person left。

 at that point， this ascending auction concludes。 and that's the winner。

 And the price is just the number which the second to last bidder dropped out。

Let me write down that a little bit more formally。So initialize the selling price to be0。

And we're going to have an initial set of active bidders。

 and initially s not the active bidders is just everybody。

And what we want to do is we want to increase the price until supply equals demand。

 So supply by definition， is just K copies of the good。

 And we want to get the price just right in the sweet spot so that there's exactly K people interested in buying the good at a particular price。

So we run in rounds。As many as we need。And in each round， we identify the new set of active bidders。

 And this will be a subset of the bidders that were active last round。 Okay。

 so for everybody who was active last round， we just say， well。

 would you still be interested in purchasing one of these goods at a price which was epsilon higher。

So we define the bit S of T， the active bidders at time T to be the active bidders at time T -1， who。

 when we now ask them explicitly， say yes， sir。 I would continue to like a good at the price P plus epsilon。

Okay， so here， Epsilon is just some increments that we fixed at the beginning of the a。

So it's some small percentage of the value that you're expecting to sell you're good at。 A penny。

 a dollar，100 dollars， depending on the good。Okay， and so again， when I say claim to want。

 I really mean we explicitly ask all the bidders of S of T -1。 Okay。

 and they we ask each of them a yes， no question。 We said， do you want it this price or not。

 And they give us the answers。 Okay， And S T is the bidders who said， yes， they still want。Now。

 an invariant of this auction is we're going to maintain the fact that the supply sorry。

 the demand exceeds the supply。 and the first time that the supply。

 the demand does not exceed the supply we stop。So if this is the first such iteration。

 that is if the number of bidders。Who now say they're interested at price P plus epsilon drops to the supplier below K at most。

 Then we halt the option。So we need to choose the winners and we needed to choose the selling price。

 So certainly everybody in S sub T wins。So we sell goods to everybody in ST。We sell it at price P。

 not at price P plus epsilon in the spirit of a second price auction。Now。

 it's possible a bunch of people dropped out in the last round。 even when K equal1。

 it's possible that you had two active bidders， you asked them both if they were interested in p plus epsilon and they both said no。

 and they both dropped out。 Okay So in that case， were just going to give the residual goods。

 So the K minus cardinality of S of T goods to people who dropped out last who were there still their last round and as t -1。

 arbitrarily， either at random or according to some operating fixed rule。 It's not going to matter。

So， and leftover goods。Of which there are k minus the number of active bidderters at the end。

To arbitrary。Subset。Of the bidders who just dropped out。Have the same。Thank you。 at the same price。

 Petee。Okay。And last iteration， when we asked them if they would be happy to have it at price P。

 they said， yes， That's why they made it into S T -1。

 They were not willing to accept it a price P plus epsilon。 That's why they're not in S of T。

 But they did say they were happy to have it at price P。 And that's what we give to them man。

 Thank you。😊，Okay， and then if that's not the case， if the demand is still too high， then， of course。

 we increase the price in。Start up。So there's many， many sort of variants of this ascending auction。

 And when you're doing this very simple scenario1， the auctions， the variance don't differ that much。

 So， for example， one thing that I defined is that if you ever drop out of this auction。

I never allow you back。So that's because I define ST to be a subset of S minus1。

 so if you ever say no， you can't say yes later。The auctions that， for example。

 Christie's are not like that。 and you can leave the room walk around the block， come back。

 And if the auctions still going， you can reenter no problem。 But again， for this simple scenario。

 these variations don't make a big deal。For other more complex settings that we'll study later。

 they can matter。Okay， so this is what I mean by an ascending implementation。Okay， here's an example。

Now， let me give you some motivation。I took a problem， simple， but， you know。

 real problem selling off K goods when you have more than10 people understood。

 I gave you what seemed like a perfect solution。 Okay the K Vic reaction。

 People write down these bids， talk K bidders， et cetera， et ceter， et cetera。

 We get all these great properties。Now， for some reason。

 I'm giving you another solution to the same problem。 Okay， why am I doing that。

 given that we have the caveVc reaction， Why should we bother thinking about the setting of implementation。

 What possible benefit might there be。There are considerations we don't have in the model。

 so for example， biders might have privacy concerns they don't want you to know the true valuation or how much surplus they're getting。

And they reveal less information in the ascending。Good， that's definitely one reason。

do we wanna look at a more general kind of problem。这。Also， good point。It's also no worse。

The same thing essentially， which I guess we'll show。

 but they're any worse than those considerations。May not be valid。Good point。

It might be easier to get the bids in as opposed to having to get in all these pieces of paper or're going to hear all the different bids here。

You know， if it's like you just wait until there's just one person left。

So if there was a ton of bidders， I'm just thinking of like the combinatorial simpler logistics。 Oh。

 you're saying the communication。Yeah， like I remember you said in the conatorial。

 just getting the bids itself since there were so many different packages。Problemmatic。对。dramaticman。

More dramatic。Good， I agree。 I agree。Even though we're assuming people are very irration。

 it might be worth considering things like someone coming back after walking around the block and just getting more money for you out of the auction。

Good。The V can't measure show the exact valuation which they have。So it might vary a little bit sort。

They may still be in the afternoon。It's causing the bad issue。Good。

It's older so people thought of it first。That's true。 They've been doing this a lot longer。

They've had ample time to switch， but you're right， inertia could be part of it， that's true。Yeah。

It more transparent process， like you don't have to trust anyone to collect all the bids。Great。

It allows people to update their evaluation if that sort of depends on。Good point。 Good point。

All right。Great， those all sound。Like excellent reasons。

 Let me maybe summarize a few of them or sort of group slash summarize a few of them。

 I could break the we， we also break the problem into two parts。 The first would be。

 if really all you cared about was scenario 1。Is there any reason to do this？And then。

 and some of the comments were more of the form。 Some comments were the form， yes。

 and some comments over the form looking forward， we can really imagine why ascending implementations might be especially useful。

 I think both sets of comments are good ones。 So let's just start with you know。

 what about just with scenario 1。Itself。So one reason was easier。For bidders。U。

And so notice that this auction is not a direct revelation mechanism。 direct revelation mechanism。

 By definition， What you do is you ask people for the private information。

 at no point does this a ask you， what is your valuation， It asks you only a sequence of yes。

 no questions。 Do you want to good at a certain price or not， Now， of course。

 this reveals people's valuations， If you look at when they drop out。

 But at no point does a bidder actually have to do that cognitive task。

So some of the comments were of that type。Other comments were of the form。

It sort of had to do with trust slash privacy issues。So let's just say better on trust privacy axes。

So when mean about privacy， I'm not going to define it formally， but at the very least。

 you realize that if you win in an English auction and the ascending implementation， nobody。

 including the auctioneer， learns what your valuation was。

 They learn a lower bound on it in the form of the second highest bid， but that's all。

In a sealed bit auction， possibly none of the other bidders learning the valuation of the highest bidder。

 but the very least the auction year does。And then the other thing mentioned was transparency right so somehow if you see these prices going up and you see the bidding process and you wind up winning the good at a high price。

 it's sort of much more transparent to you why that happened， perhaps。Good， And then another one。

Potentially more revenue。So the comment about being more dramatic， I kind of put in this category。

 if you think about bidding wars， you know， but for in many different contexts， arguably。

 you can imagine that that might get you more revenue in ining implementation and it wouldn't happen in a sealed bid format。

 So this empirical work on this。 and there's actually some supporting theory about why this would be true as well。

 although I doubt I'll have time to talk about it this quarter。And then。Let's say。Price discovery。

Et cea。With non identical goods。So this is something we had a long discussion about in the context of commercial auctions for spectrum licenses last quarter。

 which is you know if you have to say a lot of licenses up for sale， different geographic regions。

 different frequencies， you have your guess going to the auction about what your competitors want。

 but it's based on imperfect information and so it's very common you'll find out you thought there'd be a bargain to be had here and it turns out to be highly competitive and vice versa somewhere else。

 So with asc sendingending auctions， there's this opportunity for mid course corrections。

 it's an opportunity for the different bidders to sort of coordinate and realize some people to get out of each other's way if it turns out they're competing for something when something else would be just as good。

So as I said， price discovery and flexibility， et cetera， once you pass to non identical goods。

OhAnd then someone else mentioned it's no worse， which was an interesting comment。In fact。

 the next thing we're going to do is formalize the sense in which this may or may not be no worse than the direct revelation auction。

 That's an interesting thing to think a little bit about。Okay。So that。

 I summarizes the spirit of all of the excellent comments。Cool。

 I think I just got more participation in the first 30 minutes of this class than in the entire quarter。

 last last quarter。 which， which is， which is awesome。 Don't get me wrong。😊，Good。So certainly。

 all of these reasons and the fact that these are deployed widely in practice suggests that it would be really。

 it's very well motivated to try to develop a theory of good ascending auctions。

 ascending implementations。 and that's going to be the goal this week and of next week。

 that's pretty much the first major topic of the class。Okay。Questions。

Can everyone see this board okay？Alright， so what I want to do next。

 I want to stay just in the simple scenario number one for a little bit。

And I want to make precise the assertion that the English auction is no worse than the cavic reaction。

 for scenario 1。So what does that really mean？So。Let's start。

 The most interesting thing to think about is the incentive guarantee。

So what's the incentive guarantee for the caveVic reaction or for a direct revelation mechanism。

 dominant strategy incentive of compatible， truth lobidding is what people do。

 that's essentially what this says。So let's think about what the analog of truthful bidding is in the English auction。

 because again， this is not direct revelation。 We never actually ask people for a bid per se。

 We don't ask people for the private information。So it's intuitive。

 but let me just give it a formal definition。So I'm going to call it sincere bidding。

It's basically the same as truthful， but I'm going to try to reserve truthful for direct revelation mechanisms and use sincere for these iterative mechanisms。

So sincere bidding。Just means that all queries。By auctioneer。Are answered honestly。

And so this will make sense in kind of all of the auctions that we study。 But in particular。

 in the current a， this just means that when you're asked。

 do you want to good at a price of p plus epsilon， you answer yes。

 if and only if your valuation is at least P plus epsilon。

 that's what sincere bidding means over here。All right。So。

I going believe this is an exercise because the proof is pretty much the same as the proof of truthfullessness of the Viory a。

By the way， theres， there's I'll talk about exercise sets at the end of this first lecture。

 but there is an exercise set posted more on that later。So in this English auction。Sincecere bidding。

It's a dominant strategy。Well， almost up to Epsilon。Sure。

So the formal statements on the exercise set， but it's what you'd think it would be。

 no matter what the other n minus1 players do。You cannot improve over sincere bidding with any strategy at all。

 any action at all by more than an epsilon。 The epsilon comes in because there is a discretization error in this auction。

 so you might be able to get lucky and lie and stick in the auction one extra iteration you don't actually want a Ps epsilon。

 but you say you'll take it if the auction happens to halt。

 you'll actually get the good at a price of P。So if your valuation is between P and P's epsilon。

 you might want to stay in one extra round。 But that's the claim is that's all you can do。

 All you can do is gain that epsilon。And again， so the idea of the proof。

Is the same as in the Vi auction。 So you know how can you deviate in this English auction。

 else could you do other than sincere bidding， Well， you know， you're asked these yes。

 no questions and you could answer yes when it's no or vice versa。

 So if you answer no and the right answer is yes， that's dropping out early。

 That's like under bidding in a viory a doesn't help。 or you can answer yes when it's no。

 which means you stick in longer， which is basically like up to epsilon like overbidding in a victory a。

 which we also know can't help you。So that's the idea of the proof。As we'll see， you know。

 this sounds trivial， I'm sure right now。 we'll appreciate this dominant strategy property of the English auction quite a bit more very。

 very soon， actually。Okay。And so in particular， as epsilon goes to  zero。

 So if you imagine some kind of continuous ascending process in the English auction。

 then this really becomes a dominant strategy as the epsilon goes to 0 okay。All right。

 and the one reason， the one thing I do I want to point out。Which again。

 you'll appreciate more and more as we go through this lecture。

A difference between direct mechanisms and indirect mechanisms is that the action space for a bidder。

And an indirect mechanism is generally much， much richer。Than in a direct revelation mechanism。

So in a direct revelation mechanism， your action set， the stuff you can do。

 All you can do is report a bit。 Once you have one chance to interact with this auction。

 and it's right up front。Iterative a。You can in particular。

 examine the history of what's happened in the auction so far。

So I can look at what happened in the first 10 iterations。 And if I want to。

 as a function of what's happened， make my decision and iteration number 11。Now。

 it's still the case that even though you have a richer action set。

 it's still the case in the English auction that sincere bidding is a dominant strategy。

 but that's why it's not a totally nontrial state。So again， we'll develop this as we go along。

 but just note slash warning。Action set。And indirect auctions。Much richer than indirect。

Well let me just say then direct。To avoid parsing problems。

And the main reason is you can have history dependence。So I want to plant that seed right now。

And as we'll see， this does matter very soon。All right。

So what we're doing is we're trying to say that the English auction is just as good as the KVC reaction。

 and we've said that for the incentive guarantee， okay。

 honest behavior is dominant strategy either way， that's great， just as good。

It's also true that the performance guarantee is just as good up to the discretization error。

So again， this is straightforward， so I'll leave it as an exercise。So over here， for the victory a。

 we say assuming truthful bidding， you get maximum surplus。 So over here。

 we say assuming sincere bidding。We get maximum surplus as epsilon goes to zero。So formally。

 assuming since you're bidding。English auction。Maximizes surplus。Up to。K times epsilon error。

 So again， because of discretization， you might wind up giving goods to with with value that have epsilon less than than other bidders that should have gotten it instead。

 that can only help you by hurt you by epsilon times the number of goods， K。Okay。

As far as simplicity， it's also clear， it's a simple a。

 and it's clear it'll terminate because the price goes up by epsilon every time。

 Once that hits the maximum valuation， Obviously， nobody else is no under sincere bidding。

 no one's going to stick around in the auction。So someone made the astute comment that the English auction is just as good as the biya。

 and this is the formal sense in which that's true。All right。

 so that's what I wanted to say about scenario one。

 and now I want to slowly ramp up the complexity of the scenarios。

And see how our goals are going to change。So any questions before we move on to scenario 2。

So scenario 2 will be incomparable， scenario 1。It'll also be very simple。So。

We we definitely want to as people have alluded to。

 we definitely want to start thinking about nonidentical items so identical items are also interesting。

 So all of our sponsored search discussion last quarter， for example， involved identical items。

 but non-identical items have lots of motivations。 The original motivation for commtro auctions was auctioning off takeoff and landing slots at airports And so obviously those are goods that vary depending on the airport。

 depending on the time of day and depending on whether it's takeoff or landing we had an entire lecture last quarter about spectrum auctions where the different licenses while sometimes similar are not identical goods。

 they vary in geography， they vary in the frequency band and so on。

 Another thing about commt auctions sometimes people need to buy distribution route。

 So you have some product and you want to distribute it all over the country and so you need to contract with trucking companies and boat companies and so on。

 travel agents need to put together airfare and hotels and tours and so on。

 So all of these are reasons why there's been a lot of theory thinking about nonident items。Okay。

So this is going to be a set U。Of M items。Generally distinct。

So that's obviously more complicated in scenario number one。

 But here's going to be something very simple about scenario number two。 Okay。

 so in our first baby step with non identical items。We're going to look at what are called additive。

Valuations。Okay， and what that means。Is that each bitter eye？Has a private value， willingness to pay。

For each good J。Okay。So if I just give you J。Your value is V I J。 If I give you a bunch of items。

 your value for the bundle is just the sum of these V I Js for the goods J in the bundle。

So the value of a subset of goods is just defined as the sum of the goods and the subsets。

Of the constituent values for those goods。Okay。So in contrast to the unit demand case where bidders only wanted one good。

 here bidders are happy to have all of the goods even because you keep getting more and more value。

 the more goods that you get。So。You know， with non identical goods。

 this is often an overly simplistic model。 This assumes that there's no substitutes。 Okay。

 this assumes that basically your value for getting a good is independent of what else you get。

So this is false。 if there are substitutes， if there are goods that are redundant。

 that would mean having one reduces your value for having another。 It assumes there's no synergies。

 no compliments。 Okay， the case where one good， all of a sudden makes another good much more valuable。

 So again， substitutes would be like to interchangeable licenses， same location。

 different frequencies。 and you don't care which one。 and you only want one of them。

 that would be substitutes compliments would be if you're trying to piece together regional plans into something that covers a wide range。

 Then really， you want a whole set of nearby licenses。

 And so having some of them make the others more valuable。

 That's what we're excluding with added evaluations。 So it's occasionally relevant。

 But more right now， it's sort of， you know， my main motivation here is pedagogical。

 to increase the complexity gradually，Okay。So。Let's ask about the usual direct Reve DC implementations。

And then let's ask about ascending implementations， just like we did for a scenario number one。

So the DC direct Re solution is quite clear。Does anyone want to suggest what it is？

So suppose you wanted these three properties。For scenario number two。

 all of you actually know how to do that。It seemss like you just do M sim function， right？

So added evaluations means I do not care。 It means the outcome of other options have no influence about my preferences in a particular on a particular item。

Okay， so my value for getting this good J is independent of what happens in the other and the other goods。

 My values are additive。 The prices paid are additive。

 So the whole mechanism design problem just separates。 the items decoupled。

So really you can just solve each single item auction separately， and we know how to do that。

 we do that with a victory auction。Is there a question or a comment， Yeah that's right， that's right。

Yeah， so no budgets， no budgets at the moment。Okay， so the D6。

Direct revelation solution is very simple。Just run M simultaneous。Vickorys。And we have properties。

 one。D6。2。Seeming truth will bidd surplus maximization and three。It's of polynoial time auction。

 and it's simple by kind of any definition you might think about。questions about that？Yeah。

 I'm not giving， I'm not giving a formal proof， but it's just， you know， the value separate。

 the prices separate。 So the problems just completely separate。 Yeah。

 What a simultaneous matter here。What else you have in mind。You run these sequentially。Yes。

 you could run them sequentially。Good point。So let me maybe I should just say runs M separate。

And unrelated di reaction。Other questions？对。Doing them simultaneously would have advantages people could learn。

Right， so collusion， collusions a can of worms， which I I'm not going to address too much in the class。

 So that's a good point。 I mean， so there's again， outside the model reasons you might prefer either simultaneous or sequential。

 I mean you could tell stories about why sequential might be better， too。

 if you had uncertainty about people's valuations and so forth。 But again。

That's kind of not the model is it's just this。I mean， even with collusion。

 it's a little hard to see how you make a clear case that one dominates the other， I think。But yeah。

Okay。Other comments， questions。Okay。So， alright， so what about。

So what about ascending implementation。What's sort of the obvious thing to do here？

Run M separate ascending options。 I agree。We agree。So here here， let's actually here。

 I want to make them simultaneous， even though。Just for an example I'm about to do。

 I want to think of them as simultaneous。For concreteness。Yeah。And so what does that actually mean。

 So we're going to go ahead and and just start all the prices at zero。 Okay。

 and increase them like clockwork。 We're going to maintain a separate set S sub J T for the bidders that are active at time T on good J。

And the Jth English auction halts when the number of interested bidders drops to one。

And at that point， that last remaining bidder， gets the good at whatever the most recently。

 the most recent price that had demand to or bigger was at。

And so the the prices sort of go up and lock step， but the auctions are going to terminate at different iterations。

 depending on exactly how high the second highest bid is。Okay。

It everyone clear on what I mean by run M simultaneous English options。All right。

 so that seems pretty boring。So what we did for the scenario one is we just said everything about the ascending implementation is just as good as the direct revelation one。

 in particular， the incentive guarantee is just as good。 okay， it's dominant strategy。

 So we'd like to say the same thing for this。 We'd like to say that sincere bidding defined in the obvious way。

 you just answer queries honestly in all the options。

 We'd like to say that that's a dominant strategy with parallel English options。

That that seemed true。Go。Thank true。Okay。Actually。Here's a hint。 It's not true。So with that clue。

Does anyone see why？这里个。佢때嘅啲万 걸明得。In what sense， I mean evaluations are additive， right。

 So what do you mean take a hit。So this is where the， I mean， with this example。

 we'll start to see where the richness of the action set of indirect auction。

 kind of rears its ugly head。Okay。The point is there's a lot of things you could do other than sincere bidding。

 Okay， so how， how can you act in an auction。 Okay， well， you can be， you can be sincere。 Okay。

 you can bid sincerely with respect to your valuation。 Here's another thing you could do。 You can。

 in your mind say， well， let me pretend that my valuation was something other than it is。 Okay。

 I know it' 10。 but I'm gonna pretend like it's 20。

 And then I'll bid sincerely as if my valuation was 20。So that's a particular type of deviation。

There can also be deviations that are not of this form。Still more creative deviations。

 deviations that are inconsistent with sincere bidding for any。We。

So let's just suppose that there's two bidders。2 goods。Suppose Bider 2， let me tell you the values。

So bid1 is a higher value for both okay。So Bider1 has value3 for good one。

Which is higher than bidter2's value and similarly for the second good。

So what should be clear is that if both bidders bid sincerely。

 the first bidder will win both at prices of two and one。So， suppose。Bitter 2。Acts as follows。

So in the very first iteration。Okay，When bidders are asked。

 what do they want a good for good one and good2， They're asked。

 do they want the goods still at a price of epsilon。

Bitter 2 is going to monitor bitter one's response。

I'm going to assume the auction is run such that everybody sees who bids for the good at every iteration。

 That's the version of the English auction this example is for。And if a bitter one。Says yes。

 I'm happy to have good one at a price of Epsilon。Then it's going to retaliate。

Just going to keep bidding。On both goods。Forever。Or if you like up to the prices， at least say three。

对。Even though that's insincere， right its value is just two and one for the two goods。

 But if it observes bidder one bid on good one and iteration1。

 it's just going to bid way over its valuation。Else。It's gonna play nice。

So this is something bitter2 can do， this is an action of bitter2。

Theres no analog of this in a non iterative a。an iterative a where you're asked questions at every round。

And you learn information from previous rounds， this is the sort of stuff you can do。

The richer action space enables these kinds of strategies。Now。

 what does it mean to be a dominant strategy。 So let's think about bitter 1， right。

 So I claim that sincere bidding is not a dominant strategy for bitter 1。 in particular。

 it's not a best response to this strategy by bitter 2。

So dominant strategy means no matter what the other person is doing， it's the optimal thing to do。

Okay。So what happens if bidder one bids sincerely？Well， if bidder one bids sincerely， then。

 of course， it bids on good one at a price of epsilon， in iteration 1。 Of course， it does that。

 It's willing to pay three。 So it's going to say yes， I'm willing to pay epsilon。

That triggers Bider2's retaliation。And as a result。Bitter one will wind up with neither good。

It'll just get out bidd on both goods by bid or two。As a direct consequence of a bidding on good one。

 iteration 1， sincere bidding gives utility0。Is there a different thing that one could do。

Other than since bidding that would give a utility bigger than 0。Sure。

 just abandon good one immediately。So you don't want it。Okay。And cut your losses， right。

 Biter two is gonna to bid sincerely。 So at the very least， bitter one will get the second good。

At a price of one， it'll get utility one overall。Okay。So bitter ones。

 Bi2 is going wind up getting the first good at a price of 0。And2 is going to wind up sorry。

 one is going to wind up getting the second good at a price of one。

Rea this didn't work in the previous setting。We couldn't compensate hitter one or yeah， hitter one。

That's right。 So basically， I mean， so you can still try to force people out of an English auction。

 but then they're gonna have utility 0。 And since your bidding will never get you utility worse than 0。

So there's no kind of intermediate。Intermediated outcome。

This is still the case here that no one would want to deviate from a situation where everyone else is date truthfully。

Excellent， truth excellent， that's， that's true。 I don't think it's totally obvious， but that's true。

 it's an exercise。So that's exactly where we're going。So the proposal。

 which is an excellent proposal， is well at least sincere bidding is a best response to other people bidding sincerely。

 and it's exactly the next step of the lecture。But it's important to understand we have to change the notion of the incentive guarantee as we pass from direct revelation mechanisms to indirect mechanisms。

 we need to tweak what we mean by the best incentive guarantee we can hope for。

 given the richness of the action set， dominant strategies is no longer going to be possible is no longer appropriate。

 Of course， this does not mean that asing auctions are stupid and useless。 Of course。

 this does not mean that no one's ever going to do sincere bidding in a well-designed ascending a。

 That's not the point。 The point is to refine the definitions。

 so that they say what seems meaningful for indirect as。对。There one is。I this crazy group。

Ting better than better。嗯。Now they have。嗯。So， mean right so the grim trigger actually harms bitter two quite a bit。

I mean， so bid2 falls on its sword。When the bluff is called。All right。Exactly， exactly。

 that's what we want to formalize。 sincerity is an equilibrium。So that's what we need to understand。

There's a question here first。It's in bit two risks， negative utility right if one。

Oh is there a strategy validity which guarantees non negative utility or still makes non sincerity option？

Say that again。 What was the quo again。 So is there an example where Bi2 takes a strategy which is insincere。

 but we will definitely give it non negative utility。Where bid one is incentivized。I believe so。

 I'll leave it as an exercise， but I think so。If you。

 if you play around with the values in this example， notice here。

 I've made Bi too disadvantaged on both goods。But if you played with that property。

 I think you could get what you're talking about。Okay。So people have the fantastic intuition。

 There should be some notion of sincerity being an equilibrium。

 but it's actually a notion of equilibrium， which is different than anything I've talked about so far in these courses。

So we need to pin that down。 But the point is definitely to just sort of have to understand what is the appropriate analog of DI。

 We think of DIq as the strongest possible incentive guarantee for direct revelation mechanisms。

 We now see it's too strong for indirect， So I want to give you again the strongest possible you know。

 roughly speaking incentive guarantee for indirect auctions， the appropriate analog of DIC。So。

 here's the idea。And so， I mean， so basically， this， this is an extremely， this is extremely rare。

 You almost never see in iterative auctions that have dominant strategies of sincere bidding。 Okay。

 so don't get used to this。 This， This is probably the last time we'll ever see it。So the idea。

 as people have sort of been mentioning。 So we want the following condition。

That whatever people want。So that is whatever their valuations are， and again。

 we think of I only knows VI and doesn't know anyone else's valuations。And for all players eye。

Sincecere bidding。Is optimal for I。Provided。Others bid sincerely。And so I I mean。

 I'll do the math in just a second。 But so what's really important here is that we do not want to use Nash equilibrium as we've been defining it。

 Nash equilibrium is a full information equilibrium concept at a full information game。

 The assumption is that everybody knows everybody's payoffs。

 So if we play rock rock paper scissors and I play rock and you play scissors。

 I know what your payoff is。 your payoff is -1。 if we're in an auction and I see you win something for 10 bucks。

 I don't know what your utility is because I don't know your valuation。 Okay。

 so we don't want the full information Nash equilibrium concept。

 because I as a player do not know what you want。 I don't know your private valuation。

So what this is trying to say， it's saying， well， let's just assume I know your strategy， okay。

 whatever your evaluation is， which I don't know， let's assume I do know that you're playing sincerely with respect to it。

Okay， so I don't know。 I just know your plan。 I don't know your private information。

 I don't know your actual actions。 That should be enough。

For me to feel confident that bidding sincerely is the best response。Okay。

So that's what's subtle here。 There's stuff I don't know about you。Your valuations。

 there's stuff I do know about you， given your valuations， you're bidding sincerely。

 and that should be enough to conclude a best response。So in some sense。

 it's uniform over any valuation you might have， given that you're bidding sincerely。Okay。

So here's how we make that precise。So we have action sets。For bidders。 and again。

 in an auction context， this is going to be something like how you answer queries in a given iteration。

 given the history of everything that's happened so far。 So these are big sets， these action sets。

A strategy。Is given what you want， how you will act。😡，Okay， so it's a function。From。

Your private information， your private valuation。To your action。So， example。If you think about it。

Bidding sincerely as a concept。This is not an action。

 A bidding sincerely does not type check as an action It type checks only as a strategy。

So the action is actually， do you say yes or no when a bidder when the seller asks you if you want something at 10 bucks。

 your action is just yes or no。Okay， the strategy is to say， well， given what I want。

 given my valuation， I'll answer yes， if and only if my value is at least the price。

 at least 10 bucks。 So actions are what you do， strategy says given what you want， what's your。

 what's the plan of action， What do you actually do is the strategy dependent only on my valuation。

M be observed actions or others。So that's all encoded in a sub I。 Okay。

 so the way you should think of a sub I is you know。

 it's like a contingency plan for everything that might ever happen right so a particular action。

 a particular element of a sub I is going to be okay。

 in round one So in sincere bit So it's not just a yes or no answer to a question。Well。

 so in English action，In effect， it is。's just what， you know， what does you know。

 it's just what information do you base that decision on。

 So sincere biddings a particularly simple strategy where when you're given a query。

 you don't look at how you got there So when you're asked， do you want this item at this price。

 The only thing you look at is your value for that item and the price。

 You don't look at what else has happened or how else you've gotten there。The historyYeah。

 so I'm I'm trying to save you the great details about what AI actually is。

 but it's a full contingency plan。 Okay， so for example。

This crazy strategy for bidder 2 is a single element of a sub 2。 Okay。

 so this is a particular action。And what it says is basically。

 you know the way that you answer these yes， no queries from the auctioneer depends on what the other bidder did in the first iteration。

 so all of that is encoded in a sub I。 So can a sub super rich full contingency plan of how you answer queries as a function of everything you know up to that point in the auction。

is that clear。今今で自分だ。Well， so that's sort of。I mean， the domain here is V sub I。

 So this is an excellent point。 So you know， what's interesting here is that you have to commit to an action。

Knowing only what you want and not knowing what other players want。

And not knowing other players valuations。Now you may sort of learn about other players through their actions。

 but your strategy is a function purely of your own valuation。

 and that's exactly what I wanted to capture right so sincere bidding， for example。

 doesn't use information about V minus I。So the assumption in defining strategies this way。

 we're assuming， I mean， it's really tantamount to assuming that playerey knows absolutely nothing about other players' valuations。

Which， again， is very much in the spirit of our dominant strategy implementation。 where he said。

 I don't care what people want。 I know this is the right thing to do。

 So here we're going to say I don't care what other people want。

 I only care that they're bidding sincerely。 and then I know exactly what to do。

That's going to be the analog。Okay， right， so a particularly simple strategy is bidding sincerely。

 But again， for this to be well defined， it's a function of your valuation。 Okay。

 whether to answer yes or no， you need to know what your valuation is。Okay。

 so now consider a strategy profile。 Okay， so one of these strategies。

 one of these functions for each player。This is an X post。Nash equilibrium。E P and E。If。🤢。

And it's basically just encoding this idea here。Okay， so for all I， So whoever you are。

 whatever your valuation is， whatever other people's valuations are。Your strategy。

Is the best response。To what everyone else is doing， okay， to other people's actions。Okay。Now。

 you chose this action independent of v minus I。Okay， so as you vary over all possible V minus size。

 all possible things that the other players might want。

 you'reveering over all these various actions that they might be taking。

So what this is saying is that your strategy， so what this is saying is your strategy is the best thing for you to do。

 no matter what other people's valuations are， as long as they play according to these strategies。

 So again， as far as how is the player reasoning， this is like the player knowing nothing about v minus I and in almost doing worst case analysis in some sense。

 over V minus I。 But knowing or assuming that the other players are playing according to the strategies S minus I So it's a uniform best response over the valuations of the players might have。

So， even stronger。Would be a dominant strategy。 So dominant strategy says you're confident that you're doing the optimal thing。

 no matter what other actions people are taking。Okay。

Whether or not they arise via these announced strategies or not。So a dominant strategy， equilibrium。

Would be same thing。But。SIVI should be a best response。To。Any。Actions， a minus I。Weather。A minus I。

Has the form。SS minus I， v minus I or not。Okay。So， again。

Think about bidding sincerely in parallel English auctions as a concrete example。

So what we know is not true。 We know。 Oh sorry， this is a dominant strategy， equilibrium。Sure。

So we know that sincere bidding is not a dominant strategy， equilibrium。In parallel English auctions。

That's what that example shows。 It is not the case that sincere bidding is the best response。

 whatever the action of the other player。Okay， this is what's false。

But we also observed that this weird action by the other player is does not arise as sincere bidding with respect to any valuation。

It's some kind of outside the box action。We haven't improved this yet。

 but Xos national equilibrium would just say sincere bidding is a best response to any action。

Which arises through sincere bidding with respect to some valuations。So that's a weaker notion。 Okay。

 It's a uniform best response， but over a smaller set of actions by the others。

 not with respect to all actions， just all actions that could ever arise through sincere bidding。

So this is too strong， this is the candidates， and this will be what we adopt as the sort of correct。

 strong incentive guarantee for iterative options。So any questions about that？

So as a sort of initial sanity check， initial proof of concepts。

It is the case that while in parallel English auctions。

 we do not have a dominant strategy equilibrium。 It's sincere bidding。

 We do have sincere bidding as an next post national equilibrium。You mean， why do we use that word？

Why， why that word？ Yeah， the word sort of comes from。When you're talking about Bayesian models。

So is let' me try to give a short answer， so if there were a prior。

Then the usual notion of xos would be after all things are realized， which is sort of like， you know。

 if something is true X post， this is whatever the realization。 So here again， we're saying。

 you know， this is the best response， whatever the realization of V minus I。

 we just didn't have a prior。 But if you think about it， you know。

 if it's for every single V minus I， you don't care if you had a prior or not。

 It's independent on what the prior was。 So it's a good question。

 So sort given that there's no distribution here， it's sort of funny。Perhaps verbiage。

 but that's what we're going to use。If that didn't make sense， don't worry about it。Okay。

 so exercise。In scenario 2。Meaning added evaluations， non identical items。Sincecere bidding。

 while not a dominant strategy equilibrium。Is X post。Nash equilibrium。And simultaneous。

Sa for concreteness， English auctions。The proof is not hard。 So I'll leave it to you。

 But the the gist is， if everybody else is bidding sincerely。 if you think about it， sincere bidding。

If you're bidding sincerely， then the different auction have nothing to do with each other。Okay。

 your yes， no answers in one a will be totally independent on what happens and all the rest because your valuations are additive once you know all the other bidders are not paying attention between the different auctions。

 then there's nothing you can do basically it reduces just analyzing each item separately and we already did the single item analysis you can't do anything better than just bidding sincerely so that's the idea of the proof but it'll leave the details for you as an exercise。

So as usual， there's the discretization error， and here you might pick up an epsilon error for each of the M auctions that's being run。

So up to the number of goods times the discretization error， but again， as epsung goes to zero。

 it's simply an x post Nash equilibrium。All right。So a couple senses in which you I want to say that this is a strong incentive guarantee we should be happy with。

 so I've already motivated why you know we can't have even better。

 we can't have dominant strategy Elibria， but notice it's still pretty powerful to have this as a bitterder to have this strategy which is guaranteed to be optimal。

No matter what the unknown information of the other bidders just provided there following some standard natural strategy。

 So contrast that with a first price auction。 So if you're playing in a first price auction with somebody and suppose I even knew their strategy。

 Suppose I always knew they were shading their bid by 80%。Okay， and I knew that。

I totally want another value。RightBecause if I know their value， I know their bid is 0。

8 times their value。 and now I know exactly how to just beat them by plus epsilon。

so you don't have these kind of exp post sort of universal best response properties at all for lots of options。

Okay， so it's。Powerful that you don't care。 You're agnostic to other people's valuations。

 assuming only something like sincere bidding。Alright， so。In fact， I'm going。

Define non standard definition。Awesome ascending auctions。

As just like what we had for direct revelation， except。I should say。

One reason I was really excited to。teacheach them about ascending implementations is I have a legitimate excuse in lecture to say that an auction is totally epic。

X post incentive compatible。Is literally what these auctions are called in the literature。Okay。

So the first thing is the oxygen should be epic。And then。

So just like with the direct revelation version， we want a truthful revelation to lead to good performance。

 so ideally max surplus。So sincere bidding forms an exposedos na equilibrium and assuming that all bidders do bit sincerely。

Then we get max surplus， you can also obviously think about thinking about approximate max surplus。

And then again， we want some kind of。Poly time or simplicity。K of constraints。Okay。

And so I have given you such an auction for scenario number two。And so the question again。

 the high level goal for the next couple of lectures is how generally can we hope to get awesome ascending auctions in this sense？

So I have one sort of final minor point I want to make before the break， but any questions right now。

Yeah。再说商个法。没。Cidtigan， oh， you mean suppose I let the players choose the increment？

That's a good question。嗯。经营。I I'd have to think about it。I mean， its I'd have to think about it。

 Yeah， not sure。All the a that I was putting and presenting。

 I was just going to think about Epson as exogenous。 just chosen up front。So I don't know。

Or how about。You let me know， actually。Okay， other questions？Alright。

 so I want to do one final point relating sort of the direct revelation version of awesome auctions and the iterative version of awesome auctions and arguing that one is actually strictly harder to obtain than the other to introduce a relationship between the two。

All right， so。So the formal statement here， I'll leave is an exercise。 It's not hard。

 But what I want to do here is just sort of outline。You know what the main point is。

 sort of why it's an interesting observation。So early last quarter。

 I told you about something called the revelationvelation principle。

And the point of the revelation principle was to justify why we were kind of focused on these options that were direct revelation。

So basically where we just asked bidders for their private valuation as opposed to doing something more clever。

So the revelation principle is this simulation argument where basically says， well， you know。

 give me any mechanism that's guaranteed to have dominant strategies。

 but there's maybe not direct revelation。 Then I'll do a simulation with a direct revelation mechanism。

 and itll be just as good。 Itll be an equivalent mechanism。 It will be direct revelation。

So what the exercise is going to ask you to do is to apply that exact same simulation argument。

If you had an ascending auction that was awesome in this sense。

 so imagine I gave you an ascending implementation。Like this one。Okay。

 that was epic that had max surplus and so on。The simulation would just be， okay。

 well I don't want to bother with this ascending implementation。

 Let me do a direct revelation version。 Let me just ask players for their private valuation。

 I'll just simulate internally the ascending auction wait till it halts， that gives me an outcome。

 and then I'll spit that outcome out。So that's how you do simulation to go from iterative to direct。

And the claim is if you start with an ascending auction that's Xpost incentive compatible。

 you'll get an equivalent mechanism， which is actually dominant strategy and compatible。

So take an awesome ascending option， which again is only going to be X post instead compatible。

Apply the Reve principle。And the claim is。What you get is a DI。Direct revelation。And it's equivalent。

So in particular， if you had these three properties。It will be the case over here。

 you have DI max surplus， and again， reasonably simple in polynomial time。So what's the point。

 The point is designing these is at least as difficult， at least as hard to achieve as a designer。

 as designing these。Because whenever you give me an auction with these properties。

 I have an automatic way to compile it into an auction with these properties。Sat another way。

 a necessary condition。For having a good ascending implementation that's expos and of compatibleible is to have an equally good direct revelation implementation that's decent。

So the way this is going to show up is we're going to be striving for these asending implementations。

 And we'll always ask a sanity check at the beginning， well。

 can we at least solve the easier problem。Of having a direct revelation of D S implementation。

 If the answer is yes， then we can proceed and work harder to get an as sending implementation。

 If the answer is no， we know to quit。Okay， so that's the relationship between what we studied last quarter and this new sort of awesome ascending a concept。

