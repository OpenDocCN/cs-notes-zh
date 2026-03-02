# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p11 -11-(Lecture 11_ Undominated Implementations and the Shrinking Auction) -BV1fNVNzhEBg_p11-

All right， so let me go ahead and get started。I just want to make a few final comments about sort of the part 2 of the class。

 And then we're gonna move on to part 3。So where are we。

 So we've been striving for these three things。 We've been looking for strong incentive guarantees so far。

 D or epic back in part 1， welfare， Op or almost optimal and poly time mechanisms。

 And up to this point in the class， we constrained ourselves to these super strong incentive guarantees。

 we can get away with it in part1， because I sort of shepherded you through tractable special cases where we get everything we want。

 And we just finished a couple weeks though， where of MP hard， special cases of welfare maximization。

 And what we discovered is is that just already two and three jointly is nontrivial。 It's MP hard。

 you're looking for approximation algorithms。 But at least there's a lot of tools。

 there are a lot of positive results known。 But then if you add in DI on top of it。

 things get actually quite difficult indeed。 In two senses。 So first of all。

 the positive results that are known。 you have to work quite hard to get those positive results and complex mechanisms seem required to get them。

And then secondly， and this is what I'll comment on at the moment is you know there's lots of cases where it's just simply impossible okay so no matter how hard you work。

 no matter how complex your mechanism， you can't get all three of these properties simultaneously。So。

Yeah， so let me just comment on some negative results。So scenario number eight。

 this was what motivated us throughout part two， this was bidders with submodular evaluations。

 so this was just a little bit beyond gross substitutes。

 but already welfare maximization was NP hard， and part two culminated with a positive result last week。

 we showed that for a special case of submodular evaluations， namely these coverage valuations。

 we gave a DI mechanism that was very good it was 63% of the optimal welfare and that's actually best possible。

 even ignoring incentives unless P is different than NP。

But what about sort of the general version of scenario 8， Okay。

 so what about full blown submodular evaluations without this coverage restriction。

 And let's say I give you black box access just through value oracles。 and that's all we needed。

 All we were using was value oracles with the coverage valuations。

So with just  two and three jointly， the news is good。 Okay。

 so there's a beautiful algorithm by Vnd Drac。😊，Which those of you who just sort of like contra optimization。

 I recommend reading this sometimes， it's really a very nice algorithm。

And so this says ignoring incentives。You can get 1 minus1 over E。For some modular evaluations。

Only using a polynomial number。Of value queries。Okay。

So this says there's at least no obstruction to a complete solution for scenario 8 just from parts 2 and 3。

 So the question is， what happens when you add in DI also。

And it turns out we now understand that the problem is just fundamentally much， much， much harder。

 if I insist that you solve the problem using a DI mechanism。So the first。

So basically a pair of papers by Doug Zinsme and Doug Me and V Dak。Basically show that non trivial。

 I'm not going to state the formal version， but nontri approximation。We here non trivialal means。

 you know， anything better than a polynomial approximation factor。

 So we're talking just beating something really terrible， like rude M or M is the number of items。

 So forget about 63%。 I mean， just anything， certainly any constant， no matter how small requires。

An exponential number。Of value queries。Okay， so this is DI。

And this is even if it's just what's called a truthful and expectation mechanism。

 So it's not just for deterministic。 The first results for deterministic and some bells and whistles on them。

 And then the second paper shows that even with the full blown MIDR mechanisms。

 you can't do better you can't get nontri approximation with less than exponential many value queries。

 And this， you know， despite being sort of bad news， just intellectually。

 this is a real kind of triumph of this algorithm that game theory field， actually。

 So a lot of these results have only been the last five years or so。

 we now understand in a rigorous sense how incentives make N hard problems much， much。

 much harder than if you just care about approximation algorithms。

So I'm not going to talk about this now， know， I think especially this first paper would be a good topic for a bonus lecture。

 So maybe in a couple weeks if there's interest， we can talk about it。 it's a doable argument。

So instead， what I want to do now is is plunge on to step 3， where we say， you know。

 let's relax this。So let me just write something weaker here。

And with the hopes of getting sort of two benefits， first of all， just that these negative results。

 we want them to go away and they will go away， so we'll get much more sweeping positive results。

 also the mechanisms will get simpler， generally speaking okay。

So the incentive guarantees won't be as strong， but there'll be lots of other benefits。

 Oh other thing I want to mention here。So sort of a really kind of nice open question。Is。

If you have demand queries。So let me just jog your memory， what are all these queries？So in general。

 if you have a valuation， a value query just says you ask it for a set and it tells you back what the value of that set is。

 kind of any reasonable model evaluations， you can implement value queries in polynomial time。

 demand queries know while they're useful in natural in an auction context it sort of depends。

 we've actually seen some examples or demand queries are NP hard。

 including coverage valuations that we talked about last week。You know。

But sometimes you can implement these in poly time。 And when you can。

 you can do useful things with them。 And the main application you saw demand queries was when we solve the LP relaxation of the welfare maximization problem。

 How did we solve it， we passed to the dual， the separation Oracle for ellipsoid in the dual was a demand query。

 So that's what we needed to solve that linear programming relaxation。

 And we've used that in a couple different context。

So it's known that you actually with demand queries and in a decent mechanism can get a nontrivial approximation。

 although it's basically logarithmic in the number of goods and we don't know whether a constant factor is possible or not。

 so that's sort of a major open question sort of in this part of the world。

 Can you get a constant factor decent mechanism with demand queries you cannot with just value queries。

F。So。On the part 3。So we're going to compromise on the incentive guarantee。And the question now is。

 you know， what compromises could we make， What would be a sensible weakening of dominant strategy and sense of compatibility。

So the main answer to that is something called a Bayesian incentive compatibility and so that's I'm not going to talk about that in this first lecture。

 but we'll talk about it a bit toward the end of the day and quite a bit for the rest of the class and that's where we're going to have a common prior and basically we're going to ask that all the bidders are optimizing an expectation over this prior and that's sort of a very traditional approach to mechanism design。

Before we get to these Bay incentive compatible mechanisms， I want to take a detour。

I want to show you one result， which at this point is sort of a curiosity in the literature。

So the incentive guarantee will be weaker than DI bidders will not have dominant strategies and the options I will show you。

 but know it will still very much have the spirit of DI。

 We have to make very minimal behavioral assumptions to argue that we get what we want from this mechanism。

 And I'll be precise about that。But you know， this sort of notion of a little bit weaker than Dc。

 basically players not playing stupid strategies。 There's not a lot known either on the positive side or the negative side。

 I'm going to show you kind of the main positive result known。

 We don't really know anything negative。 So again， this seems like a very interesting direction for more research。

So next， so this will be all the first lecture today。

 and I might spill spill over after the break a little bit also。So Dik。

 the only behavioral assumption was that if a player has a dominant strategy。

 they play it So a foolproof strategy， playersers will play。 Now we're just going to assume that ifs。

 if there are stupid strategies， bidders don't play the stupid strategies。

 The stupid meaning is dominated， sort of obviously dominated by something else， okay。

So assume bidders。Don't play stupid strategies。Okay， and I'm not， you know。

 in the context of the concrete mechanism， It'll be very clear what I mean by this。

 It'll be very clear what I'm assuming。All right， so any questions before I start sort of talking to you about the setting and the mechanism where we look at this relaxation at TI。

Alright， so。嗯。This is going to be another scenario。But you know。

 not very different than some of the other ones we've seen。

So this is going to be called single value multi minded bidders。 So let me， let me say what I mean。

So we again have our set of non identical goods。Okay。In each bitter eye， we don't know what it wants。

But we know there's some bundles of goods that it wants。 Okay。

 so the simplest case would be sort of unit demand。 We know it wants， you know， a singleton good。

 and it doesn't care which singleton it gets， or maybe it wants a pair。 And we don't know which pair。

 okay。So there are these things are these bundles that it wants。Okay， so could be one， could be many。

 We don't know。And then a strong assumption， okay。But one that's important for the results I'll say is valuation。

VI and VI is the same for all of the bundles。Okay。So it's in the spirit of unit demand in that the bidder doesn't want many of these。

 It only wants one。 And as soon as it gets one of these bundles， it gets a value of V I。 Okay。

 So in a very simple case would be the bundles are just the single tins of U。

 That just says I want one good to me， they're all the same。 I don't care which I get。

 It's worth 5 bucks， okay。Okay。So formally， given this information。

 the valuation forbi I is just defined as。VI， if S includes one of these desired bundles。

Some AIL and zero otherwise。So it's single value because there's the same value for every bundle。

 and it's multi minded because it wants， you know， these are the multi。 Okay。

 the bundles it might want。All right， so what are some other examples。 So one example。

 imagine you could imagine that you have a network。And as a bidder。

 you have some source and some sink in this network and those are private。

 the seller doesn't know what they are， and then what you want is just a path from your source to your destination。

And so then here goods correspond to edges and the bundles correspond to the path from your source to your destination。

 if the seller doesn't know your source and destination。

 it doesn't know your bundles and then this assumes you don't care which path you get。

 just want some path。Another example you could imagine you're a firm and you just want some task to get done。

 VI is sort of the value for getting this task done and you need some workers that have enough skills that are needed for the task and so maybe sometimes three workers are good enough to accomplish this task。

 maybe if you get some really good workers two of the workers are good enough for this task and you don't care which ones you get just as long as the task can be achieved。

So those would be some examples where you might see this。Questions about that。

So let me develop your intuition by mentioning two special cases that can be solved by de mechanisms。

 And you may have even done these on homework last quarter。 I don't actually remember。

So special case number one。Is when if I。I also tell you what these bundles are。

 so specification number one。A AI Ls all publicly known。So other words。

 the only you know what bitter I wants， you just don't know how much they're willing to pay for it。

 You don't know VI。 That's the only thing which is still private。

So these are the kind of problems that we talked about some last quarter。

 this is a single parameter problem now from a bidder's perspective。

 either they get a bundle they want or they don't get a bundle they want。

 and they have this private value。 and that's sort of like winning and they have this private value of V for winning so this is where we have Myerson's lemma that says you know allocation rules can be turned into decent mechanisms if and only if the allocation rules monotone meaning the more you bid holding everyone else fixed。

 the more likely you are to win or you only switch from losing to winning never the reverse。

 if you raise your bid so this is a single parameter problem。

And one of the things we talked about last quarter is how greedy algorithms often give monotone allocation rules and therefore lead to die mechanisms。

 And that's equally true here。So， greedy。Gives a there's one parameter I forgot to tell you about。

So we're going to assume。That all desired bundles have cardinality at most D。Okay。

And D is known to the fill。So you might want to think of like D is maybe6。 and then you know。

 the bundles have sizes，1，2，3 or4， something like this。O。So greedy gives a decentick。

One over D approximation。So let me tell you what I mean by greeding。

So what I mean by greedy is you just sort the bidders from， so you get people's reported valuations。

 you sort them from high to low。 you start with the highest bidder。

 you give them one of their bundles。You go to the next highest bidder。

 you look at the bundles they want if any of them don't conflict with goods you've already allocated。

 you give them one of them。And so on。 And you just go through the bundles in this way。

 allocating people a bundle， if you can。Right。So that's going to be monotone because as you raise your bid。

 you go only earlier in this ordering。 Okay， So if you get allocated later。

 you're going allocated earlier as well by greedy。Now， this is not an optimal algorithm。

 doesn't maximize welfare， but it loses a factor D。Okay。

 and I'll leave the proof as an optional exercise。 But the intuition， I hope， is very clear。

 So you give someone a bundle and it hasn't most D items。 Okay。

 so how could you have screwed up by giving these D items to this bidder。Well。

 maybe by giving this bidder those D items， you blocked these D other bidders in the optimum that you really wish you would allocate it instead。

 Okay， but you're running a greedy algorithm。 So those D bidders values is most as much as the one you're just getting credit for now。

 So you get once times a value instead of D times a value。 So that's the one over D。Okay。

And it turns it So this is an MP hard problem。 so even in this public this public bundle case。

 and it's not trivial to approximately maximize welfare。 In fact， you can't do much better than D。

 Okay so there's a reduction from independent set and bounded degree graphs that shows basically you know one over D is what you're stuck with。

 and greedy already gives it to you okay。So this special case。

 we kind of you know subject to P versus NP， worst case approximation， we know what to do with it。

 because you just run greed， and this will be relevant for the mechanism that I show you okay。

Allright， so special case number 2。And。Can't do much better。So， special case number two。

Is when each bidder has only one bundle。So when each bidter has only one AI。

 so that's called single mind inters。But in this case。

 so it's incomparable to special case number one， in the sense that over here。

 you don't know what the bundle is。So， only one。Unknown。Bandu。Her bidder。Okay。

So this now is not a single parameter problem right because there's two things you don't know about a bidder。

 you don't know its value， VI and you don't know the bundle it wants AI so Myerserson's Lemma。

 for example， doesn't apply automatically okay。But， it turns out。Greedy still。

Gives a D61 over the approximation。Okay， so what do we mean by greedy？ Well。

 so now you have to ask people for two things， not just one thing。

 right before we ask them just for their value。 Now we say， what's your value and what's your set。

And now you're on the same algorithm you did before。 Okay。

 you just sort them from high to low by reported values。

 and you just greedily give them a set if you can。Okay。

So definitelyie one over the approximation if it's deI because it's sort of a special case of the previous algorithm。

 and you can sort of prove just from scratch that it's dI。 Basically。

 it's sort of close enough to a single parameter problem， you can just prove that it works。

 intuitivetuly， you know， from a bitter's perspective， given that it only wants this one set。

 it's never going report a set that excludes any of the items that it wants because then it's guaranteed zero utility。

 And by enlarging the set， you only make it more likely that you're not going to be feasible when the greedy algorithm gets to。

 So there's not really any reason to lie about the set。 And then once you're not lying about the set。

 it basically defaults back to the single parameter analysis。So。

 I'll leave the details as an optional exercise， but that's kind of the idea of why this is also DI here。

Okay。All right。So in this sense， scenario number nine is kind of just a little bit you know beyond what we know how to do with DI mechanisms and we'll show how basically you know taking this greedy out。

 basically an indirect implementation this greedy algorithm with a couple twists is good enough to get。

 okay， you it won't be one over D， but it'll be one over D plus some other factors and it won't quite be DSI。

 but'll be close to DSI。And again， I， I'm going present this to you not as something like， you know。

 that's， you know， from the book of magical proofs， although it's not that complicated。

 It's pretty nice， but more just sort of as an intriguing， you know， point that， you。

 it feels like there should be some broader theory around， okay。O。If any questions。

 everyone clear on the scenario？So now we're going to go back to the full blown scenario。Again。

 there's only one private value。 All your bundles are worth this。

 but you have an unlimited in effect number of bundles。

 all cardin outality most D that you might want。 And you're happy to get any of them。All right。

Alright， so let me。Tell you。About what I'm going to call the shrinking mechanism。

And so this is due to Babyoff Leviee and Pavlooff from 06。

So it's been around decent number of people know about it。

 no one's really known how to build around this， okay。Alright。

 so it's going to be an indirect mechanism。OkayI thought we were done with indirect mechanisms。

 but we were going to see at least one more this one。

 So we're never even going to really ask bidders what bundles they want explicitly。

 We're going to sort of force them to choose as the auction proceeds。

So we're not going actually ask them for their value， either。

It's going to have sort of an ascending auction flavor on the values。So I should say， let's assume。

So we're also going to assume that all values or at least， let's say one。Really。

 the assumption is you know some lower bound on people's values， okay call it one。

So you initialize the bids to be the lowest the values could be。

These will only go up over the course of the auction。So just like an ascending auction。

 we're going to systematically ask bidders， are they happy with us increasing their bid on their behalf？

Or do they want to drop out？Then there's going to be the goods that a bidder is after。 Okay。

 so we're going to force a bidder to kind of narrow its focus as the auction proceeds。So initially。

 there's no restrictions。So SI is the items which are still permitted to be allocated to bidter I。

 anything outside of SI I cannot get， no matter what。

so this will only be decreasing as the a proceeds。And then I'll need a couple sets of bidders just to keep track of stuff。

So let me just put these。Here。So losers is going to be the bidders that have dropped out irrevocably from the auction forevermore。

So I'm going show you the main loop， and then we'll do an example。So a while。

There are bidders which sort of have neither dropped out nor won in the previous iteration of the auction。

We're going to compute a new candidate allocation。 Okay。

 so new is going to be what we're computing in this iteration of the while loop。

And the way I want you to think about what we're about to do next is I want you to remember what we said about the greedy algorithm。

 Okay In some sense， what we're doing is reducing the known case to the unknown case。

 meaning the known bundles case to the unknown bundles case。

 relaxing the incentive guarantee a little bit。So if we knew all of the bundles and we were happy getting a D approximation。

We would sort bidders by value， high to low， and we'd just allocate them a bundle as long as we can。

Okay。So the problem， of course， being is that we don't know the bundles， right so we can't do this。

 So we're going to ask the bidders to kind of help us simulate this greedy algorithm。 Okay。

 because they know what bundles they want。Notice that in the greedy algorithm。

 the order in which we go through the bidders is independent of the bundles。

 So in the greedy algorithm， we go through the bidders from highest value to lowest value。

 We don't even need to know the bundles to know the ordering。 Okay。

 but we do need to know the bundles to know who to allocate until what。So。So now。

We go through all the bidders that haven't dropped out yet。So go through all bidder's I and remember。

 losers are the ones that have dropped out forever。We don't know the values。

 but we have these lower bounds， these presumably lower bounds， these proxies， these Bs。

From high to low bid。Break ties canonically， for example， leographically。Okay。

So we want to run the greedy algorithm。Okay。And。Right， so basically， new is what we're computing。

 So you should think of this as being the greedy， the output of the greedy algorithm that we're computing one at a time right now。

 So intuitive trulyly， what we want to say is that。When we get to a bitter eye。

 if it doesn't conflict with people we've already allocated。

 then we should go ahead and add this bidder to new into the allocation we're computing。ね。

Was there a question？There's one annoying twist， though， actually， which is in this greedy algorithm。

 So there's this one thing that's kind of weird。 All right。

 which which just adds a little wrinkles to the analysis， which is at the end of the day， you know。

 think of this think of U as being like 100 goods。 Okay， so there's lots of items。 And you know。

 think of D as being maybe 6 or 10。 Remember， that's that's sort of an upper bound in the cardin out of goods that anyone wants。

 And D is pretty important， right， because like in the greedy algorithm。

 D is what shows up in the approximation ratio。 So we really， I mean。

 we're thinking of D being small。 right。😊，Now， when we initialize this mechanism， on the other hand。

 we basically say a bidder can is essentially going for everything， going for all 100 items。

 so this is way way bigger than D in the case we're thinking about。

So and this is going to be this annoyance， although from a bidder's perspective。

 there'll be this kind of initial phase where it hasn't given you any information about what items it's targeting。

 as far as you know it wants any of the 100 goods， and then there'll be this first phase where we force it to target at most D items。

 okay。So the relevant twist right now is that， we don't want to run the greedy algorithm with any bidders that have。

 sets of 100 items。 we want them to be at most D。So here here's the twist。 We say if。So again。

 remember， SI are the items that I might conceivably get。

 anything outside SI I is definitely never going to get。

 and this is what's shrinking over the course of the auction。

So if I has narrowed its focus to at most D goods。This sort of makes it eligible for the greedy algorithm。

And。S I feasible。For new。Meaning whatever other bidders that have been added to new。

 their SiIs are disjoint from this one。Then we add I to new。是。

So that's an iteration of the greedy algorithm that's successful， or we can add this person。

 there's no conflict。Now， here's what's sort of cute。

So if it's the case that the greedy algorithm normally in this iteration would take a pass。

Because we're at this bitter eye and it has these set items S it might get and it conflicts with the people we've already taken in new。

We give the bidder the opportunity。To shrink the items that it wants at this point。Okay。So。

If bitter eyes bundle as subai。It's items S I conflicts with new。 You say， well， if you want。

You have the option。To shrink Si。To T， I。So in other words。

 we asked the bidder to volunteer some of the items in S subI and agree that it will be excluded from getting allocated those at any point for the rest of the option。

So T is what's left。Where。Okay， so TI should be at most D。And TI feasible。For new。Okay。

So think of this as saying， you know， we go up to bitter eye and we're like， look。

 based on the commitments we've already made in this iteration， we're going to take a pass on you。

 Okay， but here are the items that are sold。 Here are the items that have been sold here。

 the ones that are left。 Okay， some of the ones that have been sold are in your S I。If you want。

 you can suggest a strict subset of USITI， which consists only of items we haven't sold yet。

And if you do that， and these are most D items， then all of a sudden you're eligible for greedy algorithm。

 and we'll go ahead and pick you and add you to new。But it's up to you。 You don't have to do that。

 but you can， if you want。So in particular， this is the first time。

 just from a bitterder's perspective， so even the highest bidder at the beginning of the algorithm is going to be asked this question。

RightBecause again， think of this as like 100 items and D as like 10。 if you're the highest。

 know I mean， initially all the bids are one。 So it's the highest bidder。

 So let's just say the bidder with the alphabetically first name。First iteration of the wild loop。

 first iteration of this loop， basically that first bidder is going to say， look。

 know your s sub I is bigger than D， so we're going to skip you or， but if you want。

 suggest a subset of size of most D and then we'll pick you。

So that's the first shrinking by giving Bider。Okay。So then， so if the bidder agrees。

Then we reset the items it might conceivably get to this shrink set TI。And then again。

 simulating the greedy algorithm， we add I。To the allocation new。Okay。Option two is you just pass。

Yeah。You can say now I think I'll just stick with S a， thank you very much。O。So we're not done。

But that's one of the two questions that we ask bids in a good iteration。All right。

So let me actually， let me tell you， let me skip a step。Which is less important。

 I'm me to tell you about the other thing that let me try to motivate， you know。

The incentives that face a bit when they're try and decide which these two options to take。 Okay。

 so the point is， like， if you don't shrink your， I mean， the way I've written it， kind of like。

 why would you ever shrink your set， know， what's the benefit， Okay， so let me， let me explain that。

So basically， the next thing happens for a bidder。呃。So basically， for anybody not chosen。Okay。

 so are anyone not chosen by the greedy algorithm？They're going to be asked again。One of two things。

They say if you weren't chosen by the greedy algorithm。

Then you' would have to drop out or double your bid。You wanted these items， you didn't get them。

We need to make progress either your values， right， So remember， we don't know people's values。

 We just have these sort of doubling estimates， these lower bounds on people's values。

 So if we didn't allocate to this person， we need some information， right。

 Either our our estimate of their value is too low， right They have this really high value。

And they should be allocated。 And so we say， okay， then double your bid， you know。

 put your money where your mouth is， double your bid。

 and you'll have a better chance next time being chosen the greedy algorithm or drop out。So。

 there's just too much competition， you're not going to win。So option one。Is。Losers double their bid。

Option two is I can drop out。In which case。We add I to the losers。So again。

 there's an interplay between these two options， right？Okay， so to first order， as you'll see。

 this isn't gonna be quite true。 But the way you should think about it is， you know， in this first。

 basically what a bidder is deciding between。 Okay。

 so the the happy case is when greedy just picks you， you don't have to do anything。 Okay。

 that's awesome because you're not competing whether the bitterders or your bid is just so high。

 Then you're happy。😊，So the problem is what if you're not going to get chosen by the greedy algorithm？

You kind kind this auction gives the bidder two ways of succeeding in the next iteration。

 And they're really pretty different ways， actually， The first way is you bid higher。

 and then you out earlier in the greedy ordering。 So you have a better chance of getting your items S sub I。

 or you're allowed to just go after fewer items， shrink your set and you'll have fewer conflicts with other bidders。

Okay， so either your bid stays the same and your set shrinks or your set stays the same and your bid doubles。

 Okay， so those are the kind of that's the trade off you're facing as a bidder。

 And there's not going to be a dominant strategy。 Okay。

 that's kind of what's really interesting about this auction。 Like as a bidder。

 It's not really obvious what you should do。 It's gonna to be obvious things that you shouldn't do。

 And the guarantee for the auction will'll hold as long as bidders don't do obviously stupid things。

 But it's not like we're gonna have some prediction about what happens in the auction。

 like with truthful mechanism。 So we just expect people to just do direct revelation。

 So that's sort of what's quite different about this auction。Okay， let me fill in the details though。

 So there's this other piece。Which is a little annoying。

 which is because we're using an approximation algorithm because greedy is just an approximation algorithm。

 it's possible that， you know in one iteration， even though sort of the bids have only gotten higher。

 it's possible we why not compute an allocation， which was worse than the previous one。

 And we don't want that。 Okay， so the approximation guarantee sort of depends on a monoity。

 So the reason I have this old and new is every iteration， we're going be like， okay。

 let's look at what we just compute with our greedy algorithm。

 Let's look at what we computed last iteration。 And if last iteration is better。 Okay。

 let's just use that instead。I that's a simple optimization。

 which is you remember last iteration's allocation and you just keep it if it's better than the one you just did。

So。I'll write that here。If。The sum of the bids last time around。

It was higher than some of the bids this time around。Then。I shouldn't do this the other way。

So what you're sort of hoping is that you've made some progress。And so if that's true， then。

Basically， your new tentative allocation is。So old is what you're saving the ten of allocation in。

 Okay， so you compute this new one new。 And if that's better than the one you were saving， well。

 then now this better one is the one that you start saving。

So what does it mean to lose in this sort of greedy algorithm step？

It means that you're neither in old。Nor have you dropped out。So at this point in the auction。

 if you're in the set old， you're happy。Okay， you're like a tentative winner in this auction。

 You're tentatively going to get all of the goods S sub I。

 and the current price for that is going to be B I。If you're not an old at this point。

 you are not a tentative winner， and those are the ones that are asked to either double their bid or get lost。

Okay。And that's it。 So that's the option。And then the final allocation is just。

The S sub I's where I an old。And then the final payments were just the last bid that you ever made。

Okay。So， let me do a quick example。So let's look at four bidders and four items。And d equals 2。

And let's， let's even just do it for a single minded example， okay。So let's say。

 so these dots are the four items and the four bidders I'm going to represent with these circles。

 so each bidder is single minded。 It wants a pair of goods。So let's say a bitter one。

Is going to pay six for this bundle。Go'ing to pay five there。L by 15。I'm going to pay 12。

So it clear what the example is？So there's four bidders， each has exactly one bundle。

 and the bundle consists of two goods。And again， remember， the seller。

 we don't know what these pairs are。 We had no idea。So， it's unknown。Alright。

 so what's this a going to do。Well， so initially right， so initially all the bids are one。

 so let's just say wed go through the bidders in order of name，1，2，3，4， okay。So it gets a bitter one。

Its current bid is1， itss current set S1 is all four items， okay。So what the auction does is it says。

 hey， bidder number one， because your set S is so big， bigger than D。

 we're going to take a pass unless you want to shrink。Okay。And。I mean， this let me just point out。

 okay， so from a bit perspective， I mean， maybe the single minor case is a little weird to talk about。

 right because。As a bidder， maybe you want to think about the following case， right。

 So maybe you want to think about the case where D is like 10。

And you're a bidder and unsmanknownst to the seller， your unit demand。Okay。

 so all you want is one item。 You don't care which one they're identical to you。

 and you're willing to pay like 5 for just one item。 Okay， but these like 10。Okay。Now。

 as this auction proceeds， right， sort of， it seems like， okay， at some point。

 I need to stop going for 100 items。 I need to like focus on 10 because I have no hope of being chosen by the greedy algorithm until my S I is down to 10 items。

 right， But then there's this really kind of nontrivial decision you have to make， which is like。

 there's 100 items。 I just want1 I don't care which。 And now I got to tell the seller 10 of them。

 And the other 90 I' becoming eligible for。So intuitively if you're bidding this auction。

 what you want to do is try to look at the bidding that people are doing and try to see you what's the least competitive parts of the items and then kind of say okay。

 but you're also like hedging you're like， okay， here are 1 items and I think I got a good chance at getting one of these 10 for a low price so from a bidder this is the kind of reasoning you have to do。

And， there's no obvious optimum way to do that okay。

Now in this single minor case it's maybe kind of a too simple an example because there's really no reason to hedge like what are you hedging exactly right so you may as well just kind of say。

 oh yeah， sure I'll shrink to the only bundle I want。

 but still let's go through it in this example just to keep it simple。So I'm bid number one。

 at the very first iteration I'm saying either I'm going to get passed over or I can shrink to these two items。

And even here， it's not， I mean， you can make a case either way。 I could kind of say like， well。

 my value 6。 I'm gonna be asked to double my bid to 2。 That's fine。

 I could just sort of stick with all four goods for now。 But let's say bitter one just says， sure。

 I'll shrink， you know， I'll shrink my S sub one set to just the two that I want。

 And then this auction is gonna say， oh， great。 Well， in that case。

 I'll pick you and the greedy algorithm。 okay。😊，Good， so this， so this is a winner。

In the first iteration。Let's do this。So now we go to Bider2。O。So we go to Biter2， Currently Biter 2。

 know， itss S sub2 is all four items， just like everybody else。

And these two goods have already have been allocated this iteration。

 and so the auction askeds bidder to hey。I'm going to take a pass on you unless you shrink to a set of size at most two。

 which is disjoint than these ones we've already allocated。Right now， Bi2 is going to say，y yeah。

 I'm not going to do that because Biter 2 is only happy if it gets that good and that item's already been allocated。

 Okay so bitter2， it actually is clear what they should do。

 There's no shrinking that makes sense for bitter number two。 So it's going to say， I'll take a pass。

Okay， skip me。Bitter number 3， they ask the same questions。 Do you want to shrink or not。

 And bitter 3 says， well， I mean， it doesn't have to do this。 But one sensible thing would be to say。

 oh， sure， I'll just shrink to the two items I want。

 That's feasible with respect to the ones you've already allocated。 And And the option says， great。

 We'll pick you with greedy。 And then4 will take a pass。Okay。

Why wouldn't Vi2 just drop out altogether？Well， because its bid is only one， and its value is 5。

So the one thing to think about， I mean， you're right that sort of like at the end of the day。

 Biter 2 is gonna be host， probably， but Bi 2 doesn't know everyone else's value Yeah。

 so we want to be as close to D6 as possible。 So so hopefully already we're seeing this is definitely not d。

 right。There's really not a dominant strategy in this game。

 There's actually kind of a nontrial game to play as a bidder。 Okay， so it's something else。

We'll see what it is。But you know， certainly， but what's cool is。As a bidder， you still。

 you only have to reason about your own problems， basically， which are not easy。

 but you really don't care what other people are doing。 And that's very strongly in the spirit of DI。

 having no need to reason about others' behavior。 I guess that's great。So for all this guy knows。

 its value is blowing away everyone else's。 and it just has to be patient。

 It's going to get what it wants，All right， so first iteration， Biter 1 and Biter 3 get allocated。

 Biter 2 and Biter 4 take a pass。So that gets us sort of through here。Now， here， okay。

 so there was no old one。 So clearly the new ones better。

 So the bidders that are relevant here are bidders 2 and4。

 We asked them you either double or drop out。And in this case， bidders two and4 are happy to double。

Or we would expect them to double。Becauseuse their values are much bigger than two。

Now let's go to the next iteration。Okay， so now we start from scratch， but the bids have changed。

 Okay， so the ordering on the bidders have changed。

So now the highest bidder breaking by name is going to be bitter number two。Okay， so we asked Bi2。

And Bi 2 hasn't shrunk yet。 Okay， so it's S sub 2 is all four items。 So the auction says。

 we're gonna skip you because your S sub 2 is too big unless you want to shrink。

And the second bid will say， sure， I'll shrink to these top two goods， and the option says oh great。

 we'll pick you in greed event。Now I can remember we're going by bid so we get to the fourth bidder。

And we say the fourth heads， you want to shrink or not， Otherwise we'll pass on you。

 And the fourth says， sure， I'll shrink to the bottom of two goods。 Greeds is great。

 I'll pick you both。Right。Now， when we get to bid 1， all items are gone。

 So there's no be pointless to shrink。 You'd have to shrink to the empty set。

 So one gets skipped and three gets skipped。So now， one in three。

 being the ones that were skipped are asked to double their bids， and they will presumably say yes。

And same now now everybody's already shrunk。 Everybody's shrunk down to the bundle that they want。

 And so now no one even gets or let's see， So now when we go through the bidders again。

 we don't even bother to ask bitter one to shrink or not。 which is like， look， you fit。

 We'll just pick you， okay。Bitter 2 conflicts with one。 So two does get asked to shrink。

 but there's no way it's going to give up on that upper left good。

 So it passes3 just gets taken without being asked and then4 is going to skip。对。

And so then two and four both double。And same thing happens。 And then。One in three in double。

And then once this cycles back again， so this will be an iteration where one and three got allocated and two and four got skipped。

Two and four you' both going to be asked whether to double or not。And now we expect two to drop out。

RightBecause if double they would go to 8 and notice the prices you pay if you win are exactly what your final bid was。

So at that point， two drops out。Four says， sure， I'll go to8， no problem。And right。And so then。

 in the next iteration。This is the high bid。So we go to this guy first。We take Bi 4。

And then one in three are both going to pass。Because one of three are blocked by us taking four in the first iteration of greedy。

And so then one is asked to double。And we refuse， presumably， because that would take it to 8。

3 will be asked to double。And it will accept。Which will take three to8。

And then in the last iteration， again， breaking by name， we ask Bi 3 first。

 or we just notice that bit 3 is feasible， so we take it。

We ask for whether it wants to shrink or not and it won't。

And then we ask for whether it wants to double or not， and it won't。So at the end of the day。The。

 the only guy we allocated was V3。In this auction， O， which is certainly not optimal， right。

 Opmal would be the top and the bottom for 20。Okay， but we're not expecting to be optimal。 Okay。

 but that's what it does。 Yeah， Rory， Why are we doub every time。

It like that's what screw That's excellent point。 Yeah， so there's sort of two。 It's a good point。

 So we're losing twice。 So one loss is just because greedy， even on the real values。

 is off by a factor of D。 And you're absolutely right。

 we're sort of picking up another factor of two loss because we sort of this discretization error。

 basically。 And if we wanted， we could certainly change that factor 2 to a factor of one plus epsilon。

 We'll see a part in the proof where it would get traded off。But you're absolutely right。

 too is sort of。Arbitrary。That's all right。O。So that's the a。If get it。Okay， cool。So。

 the claim is that。The auction has a non trivial welfare guarantee as long as the bidders don't do anything stupid。

Okay， and that's what I want to prove to you over the next few numberss。 But thats， that's the goal。

 That's that's the one thing I want to say about this mechanism。

 basically about this sort of slight relaxation of D6。 So any questions before we start the analysis。

All right。Good。So。All right， let me tell you what I'm going to assume。Right， this is important。

 So let me tell you。What do I mean by the bitterders don't do anything， sort of obviously stupid。

So the analysis of the algorithm。Will be of the auction will be assuming that the bidders behave in the following way。

So the first two are simple。So you'll drop out before your bid exceeds your value。Okay。

 so in this step， if your bid is already strictly more than half your value。

 then you're gonna to say no， I'll drop out。And again， this is obviously not。

 dropping out with this is obviously stupid because if you win， you love negative utility。

 It's dominated by dropping out， which guarantees you zero utility。And then， conversely。

Won't drop out。Until BI is greater than VI over 2。Because if is VI over two or less。

 why not just don't？Right。Because you might win。 if you win， you'll get， non negative utility。

 And if， you know， if you lose， you'll get 0。And then three， three is about three just says。

When it's obvious， you should shrink。Shrink。So let me spell that a little bit。Whenever。嗯。

BI is already big。Okay， so whenever your bid is such that， you will refuse the next doubling。

Whenever BI is bigger than V over2。SI is not feasible。In greedy so far。And there exists。

A feasible TI and S。With TI at most D。That I wants。Then， I will shrink。To such a TI。So right。

So what we're thinking about is， you know， there's a situation where。You know， you get to this part。

 shrink or don't shrink。And。Right， right。I guess I should say， thiss one other twist。 No， Okay。

 this is basically what I mean。 So when you're asked to shrink or don't shrink and not shrinking is going to result in you being asked to double your bid and you being asked to double your bid will result in the bid being more than your value。

 causing you to drop out。 Why not shrink。 Okay， That's all I'm saying。So， and that's it。

 That's the three assumptions。 Okay， so， you know， the paper sort of writes down a formal definition about how reasonable this is。

 But I mean， in this concrete settings is just obvious， right， These are sensible。

 it's not a dominant strategy， but you don't have to know anything about what other people are doing。

 All you need to know is sort of your value and you have to be able to basically solve this problem。

 Okay， so it's bitter， you have to be able to figure out given the goods that are left。

 whether you want any or not。Whether one of your bundles is in there。So I view these as， you know。

 while not decent， kind of very pleasingly weak behavioral assumptions。

And under just these assumptions， we can say。呃。That the auction's output will be good。

Are pretty good。All right。Here's an initial。There's a limitma that we don't necessarily care about in its own right。

 but it winds up being kind of really useful for the rest of the analysis。

 basically just says this thing isn't going to run too many iterations。

So under our behavioral assumptions。The number of iterations， which I'm going to call R。

Is bounded above by three times。The log of the maximum valuation。

And so the important thing to notice here is that it's independent of the number of bidders。

 independent of n， which is you might have been concerned like know， maybe every iteration。

 only one person doubles and then n iterations， everybody doubles。 And so， you know。

 n times log V maxax would have been kind of， yeah， of course。Independent of N takes proof。

It wass not that hard。All right， so consider the last bidder to drop out， okay。All right。

 so one case is that this was a bitter that never shrank。Okay。That's an easy case， right。

 If you've never shrank， then your set SI is too big to be eligible for the greedy algorithm so you can't ever win。

 if you don't win， you're asked to doublele。And in Vmax doublings。

 you're going to drop out because it'll be bigger than what you value。So then at most log base 2。

 Vmax iterations。So the interesting case。Is when S I， when I has shrunk。OK。So let me tell you。

 let me give you something that's almost， but not quite a proof。

 And then we'll see it's pretty easy to kind of fix it up to be a real proof。So， let's say that。

S I is， let's say that， you know， okay， so a couple things。 So first of all。

 if you've ever shrunk even once in your life， you have to shrink to something that meets the cardinality bound。

 Okay， so there's really this sort of phase transition。 Okay， for a while。

 S I is everything and you're just totally ineligible for greedy。No matter what。

 And then there's a space of your life after you shrunk at least once where as long as you don't conflict with anybody。

 you're eligible for greedy， okay。Alright， so S I， because they've shrunk once。

 sort of eligible for greedy， modo feasibility。So， you know， if this guy dropped out。

 it had to have lost， so it should be conflicting with someone who was a winner called the conflicting person Jay。

Okay。All right。Seets your recall。 So this is the end of the algorithm。Right。

To S I is conflicting with some other bitter J。 Okay， their bundles intersect in an item。Now。

 everyone's bundles are only getting smaller and smaller and smaller as the algorithm proceeds。

 So two bidders whose bundles intersect at the end of the algorithm have been intersecting for the entire course of the algorithm。

Because they're only bigger in the past。And so what that means， and then if you think about it。

 right， if they've always intersected every single iteration， every single iteration。

 only one of them could have won。 One of them had to have lost。And if you lose。

 you're asked to double your bid。So one of these two bidders。

 I or J has to be doubling the bid every iteration。So within two VMax iterations。

 someone's had to be asked Vmax times and they'll drop out。So in particular， I mean。

 the one that dropped out I， it happens within。Vac iterations，2 V max iterations。Okay， so。Yeah。

So there is this sort of corner case， I guess I should mention。

So it is actually possible the way I' phrased this algorithm。That。You know， you'll drop out。

 you will have lost， and you don't actually conflict with anybody who's winning。

It's not very important， but I just want to point out there is a corner case， right？Right。

 so how could that have happened。Well。Here's here's when it can't happen。 right。

 Suppose in the last iteration， the allocation that was computed， the new one。

Was strictly better than the old one。Okay。So this bitter eye was eligible。

 so we just computed new using this greedy algorithm and so if that's the final allocation and I as a loser。

 then I was not accepted by this greedy algorithm， which and the only reason you don't get accepted by the greedy algorithm assuming your size is of most D is because you were blocked by somebody。

So that's fine。That's the case we're probably all thinking of。You know only thing is， is， you know。

 it is possible that in that last iteration of this auction， you computed something that had。

 you know， worse some of the bids than the previous iteration。

 So you just threw out that greedy computation at the end。

And you took the one from the previous iteration。And then you're tempteded to say， oh， but I mean。

 then this bitter eye should have conflicted with someone in that iteration。

Which was true for the set of goods S sub I it was going after in the previous iteration at that greedy computation。

 which it may have since shrunk。Okay。So there's this corner case where a bidder might have shrunk its good since it was excluded by some greedy computation into a previous iteration。

So it is sort of possible that this fails。But then you kind of do the obvious thing。

 You just kind of sort of reverse back into the auction。 And you kind say， well， look。

 there look at the last greedy computation where I was not chosen。 It's because it set at that time。

 was blocked with somebody else at that time。 Okay， And so in all iterations prior to that one。

 This is true。 They were I and J were blocking and all iterations prior to this one。

 So they were doubling。 they basically taking turns， doubling。And then ever since then。

 it must have been must be the case that the greedy computation from that iteration has just persisted as the best allocation for the remainder of the auction。

And I is not in that allocation， so every time that allocation is chosen， it's a loser。

 and so every iteration after that intersection point， it keeps doubling。Okay。

 so if you like2 V max at most， up to the point where I andJ conflicted in that greedy computation。

 and then I most Vmax after that for the doublings when I is excluded because you keep retaining the old greedy allocation。

So let's just say corner case。In fact， if you， if you do this argument more carefully。

 you still get2 V max， but it's probably a little bit easier to think about。um。

As just you separated into two parts， the last time that I conflicted with anybody and then the sort of final phase where it just keeps not getting chosen because we just keep picking an older greedy allocation。

So let's just say corner case might add extra。Log of Vmax。看。But so again， the upshot。

 and this is important。 Okay， it's really important that this iteration bound is independent。

 The number of bidders in。 It' would be nice if it didn't even depend on V max。 But if at。

 if you look at how this auction works， obviously， it's going to depend on Vm with the doublings。

 Okay， so that's the point。 Okay， so's， That's a good iteration bound。O。So any questions about that？

So。So I think what I'm going to do is I think I'm going to tell you the proof plan。

For the approximation bound， then we'll take a break。

 and then we'll do that proof and then start talking about Bay Nash equilibrium。Okay。

 so let me tell you， okay， So again， what we're going to prove is that under these behavioral assumptions。

The wealth， no matter what players do， the welfare of the final allocation is near optimal。

So we're going to do that in two steps。So at the termination of the auction， just remember。

 there are these sets that a bidder is going after and they keep shrink， keep shrinking。

 keep shrinking。S hat I， that's just going to be I set at the very end of the auction at the conclusion。

 Okay， whether you're a winner or a loser， I don't care。 That's what you're going after at the end。

So Is final set。Now， here's an important thing to point out。Okay， so here's， heres。

 so it's clear we're going to get some welfare loss just because we're using greedy。

 So we're expecting a D loss in the approximation。 But there's going to be a loss on top of that。

 And I want to just tell you a little bit about why we should expect that， okay。So， what opt hat。

Be the max welfare that anybody could get。When I only gets。Goods。From S hat I。Okay。

So opt is just the maximum welfare is just the welfare maximum allocation。 Okay， so for the real opt。

 anybody can get any items。 Okay， and then you just maximize welfare subject to that。

 So this is a more constrained optimization problem。 So the opt value is going be worse。

 going be smaller。 I'm saying， no， you don't get to optimize over all allocations only over those where bitter I only gets items that are in S hat I。

 And again， we're thinking of like therere being 100 goods and S high S hat I is only like 10。Okay。

 so there really is gonna to be extra welfare loss because of this。

 Basically because of miscoordination problems amongst the bidders。 Again。

 think about this case with 100 items， people only want one。

 but they're sort of forced early on in the a to kind of guess a good set of 10 items that they think they can get one of at a cheap price。

 So you've got all these different， maybe you've got 100 bidders。 Okay and 100 items。

 So you could just have this perfect matching between the bidders and the items。

 And it would be awesome。😊，But the bidders don't know this。

 the bidders are having to just kind of like guess， they have very few clues to go on。

 so the bidders just kind of guess these sets of 10 items。And then the question is。

 you have a perfect matching that， in addition， only gives each of these bidders one of the 10 items that they've funneled in on。

 Okay And in general， there won't be。 there might be a perfect matching originally。

 But then once there's all these exclusions from certain bidders getting certain goods。

 all of a sudden， there isn't。 And there's going to be a worse optimal allocation。

So a key conceptual thing we have to do in this analysis is quantify the welfare laws arising from the bidders just in a totally uncoordinated way。

 trying to guess know where theyre be where they're going to be able to get a bundle from。Okay。

 and so that's， that's exactly what this analysis is going to do。

 So there's going to be one loss because you use greedy algorithm and then a loss because of this restriction。

Alright， so opt hat is trying to quantify one of these losses。 It kind of says。

 suppose they gave you exponential time and I gave you all the information。 But you know， I you know。

 you had to respect people's final sets。 How well could you do。

 We want this to be not too much less than the real opt， okay。Al right， so some more notation。

 Do I need this yet， Not yet， No， let me state the limmas。So Lama 2。

Under the behavioral assumptions I just erased。The welfare of the shrinking mechanism。

Is at least 2 D R times opt hat。 So I'm running where all these are。 So D。

 this is our 10 is our cardinality bound on bundles。 R， that's the number of iterations。

 So that's log Vmax。Okay， so intuitively， this is going to come from the greedy algorithm。

 We're sort of losing the greedy algorithms worth every single iteration。 And then also， you know。

 this is a smaller number than opts。 Okay， that's not a theorem。 It's just dilemma。

 so this is opt under the restriction， people can only get the goods in the items and the sets they were shooting for at the end of the auction。

And then limit3 quantifies to what extent optt hat is worse is less than opts。So under B。

Opt hat is at least。I' going need a plus one here。R plus1 times opt。And again。

 R is the number of iterations， which is log of Vax。Okay。So again， as expected。

Because bidders had to sort of funnel in on a subset of goods。

 It has We have less flexibility for the allocation。 So we're losing something。 Fortunately。

 the loss is just the iteration count， which we know is regionally small。

 And then we do pretty well with respect to this respected notion of the opt。Okay。

 so putting these together， we get the shrinking mechanism。It is a1 over D。

Log Vm squared approximation。Okay。So if we didn't care about incentives at all。

 we would not have that。Okay。In the special cases， we could get DCI and we could get that。

In this multimined case， DC， as far as I know， no one knows how to get anything。

And so here what we're doing is we're losing a bit in the approximation。

 and we're getting a pretty strong incentive of guarantee。

 And that's as far as I know the state of the art for this problem。So。Let's take a break now。

 actually， let's come back at 330， and I'll prove to you limits 2 and limits 3。

And then the last part of the， then the rest of that lecture will be， I think， relatively light。

 I basically just have to do some basees Nsh basics because we haven't done it yet。

 So getting ready for base N implementations。 So we'll talk a little bit about sort of base N equilibrium first price auction and that kind of thing。

 Okay， so I'll see it 3，30 for the proofs of these。

