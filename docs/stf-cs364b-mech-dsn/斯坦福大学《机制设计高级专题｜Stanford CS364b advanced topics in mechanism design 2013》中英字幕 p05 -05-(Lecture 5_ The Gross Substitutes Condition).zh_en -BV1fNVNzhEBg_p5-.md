# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p05 -05-(Lecture 5_ The Gross Substitutes Condition).zh_en -BV1fNVNzhEBg_p5-

Right。Cool， so announcements。So exercise set two is due today。

 there will be an exercise set three posted hopefully completely tonight。

 to at least partially tonight if you want to start utterly on it。

 starting with exercise set three I'm going to start tailing off the exercises some so I'm thinking there'll probably be about only five or six on this third one and then as the projects kind of start coming out。

 those will you know become either nonexistent or very short the exercise sets。

So speaking of projects， so I've compiled a big list of ideas， they're not on the web yet。

 that's sort of I still have to put them on a webpage， but lots of ideas。

 one thing that's always a little weird about project courses like this is you wind up sort of settling on a project when you've only seen kind of a really small subset of the courses material So I thought maybe I'd give you just sort of an outline of what we're gonna to be covering this quarter。

 this is also for those of you who maybe thought I was making it up as I was going along。

 Well actually to be honest， I sort of making it up as I'm going along but this is kind of what I had this is what I have in mind。

 Okay so this will be the last lecture on the first topic。So for most of the course。

 we're going to be studying this paradigmatic problem of just you have goods and you want to allocate them to people to maximize welfare。

 We could talk about other problems。 But the reason I'm focusing on this is really。

 you can kind of cover。All of the trends that have been happening in this mechanism design world pretty much through the lens of this problem。

 So it's a really good one just to focus on to study all the different tradeoffs in recent work and mechanism design。

 So we're starting with tractable special cases where there's lots of positive results and so all these cases。

 the VCG mechanism is sort of the quote unquote obvious solution。

 direct revelation solution we're focusing on ascending auctions So sort of more ambitious goal So starting next week we're going to pass to cases where you cannot implement even the VCG mechanism in polynomialton or just the underlying welfare maximization problem is NP hard。

 And so this is for somewhat more general preferences。

 So we'll talk about positive and negative results for these NP hard classes of problems here there's going to be some pretty striking negative results so there's actually with D auctions there's not a lot you can do on this problem once you get past the tractable special cases that we'll talk about today so these negative results then motivate going beyond D implementation。

So relaxing the dominant strategy requirement and so we'll have a week or two so fridge of these last four topics will do roughly two weeks each I know that adds up to too many weeks but something like two weeks each so after we realize we can't get what we want with dominant strategy implementations we'll look at weaker equilibrium concepts one called undominated strategies where there's a lot of open questions and then we'll also start talking about Bay Nash implementations which are kind of very important in mechanism design and we haven't seen at all either last quarter or this quarter。

So we'll get some really nice positive results for Bay's National implementations。

This is where you have a common prior and you look at Bays National equilibrium。

 So bidders are doing best response sort of an expectation over the uncertainty about other players' valuations。

 We'll talk more about that obviously So the positive results here are going to be achieved with pretty kind of heavy duty mechanisms'll be polynomial time whether they won't be especially simple So then we'll move on and say okay well let's sort of go back to the idea that we want simple as thatll be somewhat resemble as used in practice the way we're doing in this topic and we'll ask to what extent can we get near optimal welfare And so here we're actually going to be doing nontrivial equilibrium analysis that'll be very much in the spirit of the price of anarchy section of the course in the middle of last quarter。

 there's been a lot of work on this the past few years and then with whatever remaining time。

 So all of this is about the welfare maximization problem that we've been studying this far and then finally I'll start talking about with whatever time remains about revenue maximization So remember what's hard about revenue maximization is we don't even have an analog of the VCG mechanism。

 So in welfare。If you want to optimize welfare and you don't care about computation or anything like that。

 At least there's this in principle solution of the VCG mechanism。 And for revenue maximization。

 there's no analog。 So this is we talked about Myerson's theory last quarter， for example。

 So we're going to study what happens when you have multiparameter settings like， you know。

 we're talking about now bidders who might have different values for different goods and so on。

 Okay so this is extremely hard。 but there's been some sort of exciting， know。

 new directions that have opened up in the last couple of years。So and again。

 just as far as you know you know all so this first topic is kind of the only one which is classical。

 So this first topic， you know we've seen some stuff in the past 10 years but it's mostly been from the 80s。

 you know all of these four topics will be nothing but 21st century stuff。 And in many cases。

 just the last three years or so。 Okay so that's sort of the outline of where we're going there'll be projects for all of these things up on the list。

 So if one of those sounds especially exciting。 all categorize the projects according to these topics。

😊，And the other thing I'd say is one real benefit。About the class being so relatively small as it's actually realistic for me to。

 be helpful with the projects more than say last quarter， know when there was 50 people。 So。

 you know， definitely feel free to know， get in touch with me and say。

 you know I was thinking about you know， this paper。

 do you think that's a good idea or not or whatever。 So both when you're picking the projects。

 And then throughout the quarter。 definitely feel free to get in touch and ask for my advice。

 It's sort of small enough that I can actually actually do that。

 Probably I'll schedule check in meetings with people and you know。

 week 7 or8 or something like that。 But even well before then just picking a topic if you want to talk about it。

 just let me know。😊，So those are the announcements， any questions？Sound good。O了。Alrighty so。So far。

 what we've done is we've looked at four tractable special cases。

 The first two were sort of really trivial。 The identical goods unit demand case。

 which you just saw with an English auction and then the additive case。

 which you saw with parallel English auctions。 we've done two not so trivial special cases。

 although with very satisfying positive results。 So we had the nonidentical goods and unit demand bidders that's where used the Crawford Noer auction to given epic auctions surpl maximizing。

 And then we also saw for identical goods and downward sloping valuations。

 we had Ozeba's clinching auction， which also gave us everything that we want。 And those last。

 if you think about it， those last two you know， know positive solutions that were nontri。

 they didn't really look that much like each other。

 I don't think the unit demand non-identical case and then the identical downward sloping case。

 I mean clearly at a high level， we approach it in the same way。 But the actual solutions。

 they don't feel like sort of minor variations on the same thing。

But it turns out there is a common generalization of those two scenarios。

 and it turns out there's actually sort of one。Instaniation， the problem we're studying。

 which represents the frontier of tractability in many senses of the word。

 So that's the plan for today， both lectures today。Okay， so frontier tractability。

So they're going to be something called gross substitutes valuations and it's sort of amazing how many different properties you know basically hold all the way out to gross substitutes and then fail beyond it and we'll see two or three of those topics today you know there's many more that I won't have time to discuss。

ち。So。So here's the plan for the next 30 minutes or so。So what I want to do is I want to start with。

Crawford noer auction。 So this was the unit demand non identical goods auction that we talked about last week。

 And I want to look at a natural generalization of that auction to where bidders might want more than one good at once。

And then we're going to ask， you， when might that a have a chance of working well？

And that question will naturally motivate the definition of these gross substitutes valuations。

 so we're going to talk about a concrete a that'll motivate this definition。

 and then we'll see that actually this definition rather than just being relevant for this one auction is actually a fundamental concept and we'll start talking about it to the properties。

All right， so the general setup。Which again will certainly encompasses all the cases we've seen thus far。

So their good should be in general， not identical。So as usual， M of them。And。

Bitter eye has a private。Evaluation。Or willingness to pay。In principle。

 for every possible subset of items that I might get， every bundle， it's called。K。

So that's a lot of private evaluations right if there's M items， it's two to the M of these。

 but we're not going to worry about complexity and representation issues until we need to Okay。

 so for now it's just a model。And。Unless otherwise noted。

 I will always assume that your value for the empty set is0 and more stuff can only be better， Okay。

 so that it's monotone。So this is also called free disposal。

 meaning you always have the option of just throwing things out if you don't like them。So， S union T。

F I ofs。The FT。Okay。So so far， this is super general。Okay。

 so it not has encode all four of the things we've seen so far。 as we'll see starting next week。

 this encodes some really， really hard versions of the problem。 So to get positive results。

 we need to impose more than just these conditions so far。So。Like I said。

 so what I want to do next is look at a generalization of the Crawford Noer auction。

 And you might remember that in the main iteration of that auction。

 what we would do is we'd take some bidder that was not assigned to any good。

 And we would ask it for its favoriteed good at the current prices。

 So there's the notion of a bidder having a demand， itss favorite good at the current prices。

So this next option， so now in this setup。Viitders might want more than one item。

Okay someone we asked them what they want， they might give us a whole set。So， formally。呃。Okay。

So it's just you know we've seen this concept many times， so eyes demand。At price Q。

Which I'll denote by D of Q Q here's a vector index next by the items。

So this is just the set of favorite bundles that the price is Q。Okay。Or my favorite I just mean。

You look at your value for that set， minus what you have to pay， okay。

 and you obviously you just sum up the prices on all of the items in the bundle。

So some bridge A&S of PJ。And you're allowed to demand nothing。So the empty set is allowed。

 in which case we interpret this as zero。Okay。Alright， so here's the generalization of the auction。

So the Kelso Crawford auction， Kel and Crawford were also the first to define gross substitutes the way we'll be using them。

Today。So。Prices are going to start。At zero and they'll only go up。

And then we're also going to keep track of the items currently assigned to a given bidder。Okay。

So it's initially nothing。So in the main loop。We're going to ask bidders what they want at the current prices。

 although there is one thing we're going to enforce。

 So you may recall that a key property in our analysis of the Crawford Noer a was that as soon as you bid on an item。

 you get that item and then you still have that item until someone outbids you。

So you can't just at some point， drop it and withdraw your bid and relinquish the item。

 that was a property in the Crawford Noer auction。 So， but differently from an items perspective。

 as soon as you're bid on and you have somebody that you're matched to forevermore。

 you're gonna be matched to somebody。 Just the sequence of bidders who outbid each other on this item。

 So that's gonna be an important property， We're gonna retain it。

 So when I say I ask bidders for what they want， I more say。

 given the items you already have at the prices you're already paying for them。

 what would you like to also bid on in addition。so that's what we ask every bidter in the main loop。

So ask each bitter eye。For a set in， so it's going to be like this definition。

 except it's given that you already have S sub I and you're not allowed to drop them。So in Argmax。

Of all the goods that you don't already own。Of this same thing。And now， in the。

So I want to explain this notation。Q Epsilon SI Union T。What I mean here？

So you might recall that in the Crawford Noer auction。When this happened。

 it was always the case that the bidder currently had nothing had the empty set。

 and they're only going to be bidding on one extra item because of their unit demand。

And we asked them to think about， even though the current prices were Q， we said， well。

 when you tell us what you want， think of the prices as being a Q plus epsilon。

 so we're going to do the same thing here。Now， for the items that you had already has。

 the prices are not going to change， but for the items it's newly bidding on。

 we're going to say think of those prices as beingqless epsilon because once you take them away from the other people。

 we're going to increment those prices and they really will beqless epsilon。

So this is just your so again， you already have S sub I。

 you can supplement it with more goods if you want， you're looking at the value。

 minus the price and what are the prices， so this is just for everything you've already got。

You just paid the current price。Q of J， then anything that you're going to newly acquire。

Think of the price as Q of J plus epsilon。Okay。And that makes sense once I tell you the rest of what we do。

 So first of all， if nobody wants any more stuff。Then we just halt。With the current allocation。

 that is everybody gets their set S subI of items and prices。

 meaning everybody plays Q of J for each of the items， J and their bundles。Otherwise， you know again。

 it's a nondeterministic auction， so basically the bidder can report any if there's multiple qualifying bundles。

 capital T， the bidder can report anyone， it doesn't matter which， and then the auction。

 if there's many bidders who want more goods， we just pick an arbitrary when it doesn't matter which。

So， else， pick I。They want some more stuff。Let them have it。So that means of course。

 we're taking it away from other people。So if you were a previous owner of these items in TI。

 then you're going to lose them。And then these are all being outbid。

 so we increment the price on everything that was taken away。

With the one exception here being that if you're actually the first bidder ever on a given good J。

 then the price can stay at 0。 Okay， but if you're outbitting somebody else。

 then the price should be incremented by Epsilon。And so that's the entire auction。

If the bidders are unit demands。This instantiates to exactly their Crawford Noward auction。Okay。

So this is its sort of natural generalization to arbitrary evaluation functions。Does it makes sense？

Alright， so a quick example。And the point of this example is that if bidders bid sincerely。

 So if the only thing we know about bitterders。Is that their valuation satisfies these properties and nothing else。

 And they' bid sincerely。This can be a total disaster。Okay that's the point of this example。

So suppose there's two goods。And the first bidder is going to be of a type we haven't really talked about。

 although that's very simple。So the first bidder is all or nothing。 also called single minded。

 So either it wants both goods or none。So its value， let's say， is three。If it gets both goods。

 and otherwise it's zero。Okay。Bitder2 is unit demand。So its value is two for any non empty set。

 okay just wants one item， and it doesn't care which one。

There unit demand and also with the same value for both？Okay。That's it， two bidders， two goods。

So think about these bidders and stare at that auction and think for a second about what's going to happen if they bid sincerely。

This is kind of interesting what happens。Okay， so let's go through it。

 Let's say we alternate players。对。So notice right， the auction has to pick a bidder if multiple people want more goods。

 let's say we start with bidder one。So Bider one says， well， at price zero， I'll take both。Thanks。

 thenton。It ten to be assigned to both items。Then we asked Bider too oh you know would you want to outbid this on anybody and Bi2 says yeah。

 yeah， price zero or price epsilon for sure， so let's say that it doesn't matter which。

 but maybe the second bidder picks the first good to outbid the first bidder on bumping up that price to Epsilon and grabbing good one。

So now we go back to bitter one， let me say， do you want to add bitter one still has the second good？

And we said， do you want to augment that by anything。 And they said， yeah。

 the second good by itself is not worth anything to me， but both goods has value 3。

 and the prices currently are epsilon and0。So the first bidder then grabs that first good back from the second bidder。

 which bumps up its price to two epsilon。Okay， so let we go back to the second bidder。

 so now it's going to grab the second good。Bumping up the price to epsilon。

The first bidder will grab that second good back from the second bidder。

 bumping up the price to two epsilon。And so this will continue for a while。Okay。

 so the second bidder will keep grabbing one good that's all at once。

 the first bidder really wants both is going to keep grabbing it back。

So the prices of the two goods will just increment two epsilon， two epsilon，  four epsilon。

 four epsilon， six epsilon，6 epsilon。Now， something interesting happens once both of those goods start having price three2s。

Okay。So once both goods hit a price of three/2s。Now。

 all of a sudden bitter one would prefer to have nothing。But importantly， in this auction。

 you cannot relinquish items， you only lose an item when you're outbid by someone else。Okay。

So let's say that a price  three/hals。 the first bid， the first bidder has both。 has utility 0。 Well。

 the second bidder。 remember， its value is2 for a good。

 So it is not deterred from a price of threehalves。

 So the second bidder is going to go ahead and grab say the first good bumping up its price to three2 plus epsilon。

Okay。And now the first bit is pretty bummed out。SoThe first bid says， well， look。

 I'm stuck holding item number two at a price of three/2al， so I have value zero for it。

I could get good one back， but then I'm paying three plus two epsilon for something I value at 3。

But if you just literally run this auction。That is the better option for bid one。

 it would rather have utility minus two epsilon than utility minus3/2s。

So it's going to go ahead and grab it back， even those negative utility。 So eventually。

 both the prices will go up to 2。 And at that point， bid  two， we'll see I give up。

so bitter one will end up with both goods， but itll pay four for utility of negative one。Okay。

All right， so， you know。It was easy enough to write down the auction。 The question is。

 is it worth anything， okay。So all right， so what can we， you know， what conclusions can we draw。

 So obviously then sincere bidding is not going to be any kind of equilibrium， right。

 if it winds up giving you negative utility， okay。What's worse is， I mean。

 even forgetting about kind of being an equilibrium， I mean， let's actually just， I mean。

 a sort of weaker condition is just thinking about Wal rosieian equilibrium。

Is it at least the case that you get sort of prices at the end where everybody gets their favorite good。

 and again， the answer is obviously no？So in this case， actually。

 bid number one is not getting its favoriteed good at the declared prices who would prefer to have nothing。

O。So but like I said， our general setup is super general， and for positive results。

 we're going to have to have extra conditions。And。This example suggests what maybe is a sensible condition。

At least for this particular auction to function well， in some sense， okay。So， we noticed。

That there was a points。How's the blue on the screen， Is it reasonable。Yeah good。

So one red flag was when this Kelsso Crawford auction got to a point that a bidder actually would prefer to relinquish a good。

 Okay， so the auction doesn't let you do that。 So if a bidder wants to do that and the auction doesn't let it。

 it kind of just feels like that's， you know， a deal breaker for any kind of incentive guarantees。

So we can first ask the question， you， okay， when is it going to be the case at least that in this Ke Crawford auction？

Bitders are perfectly happy to not relinquish the good that they've gotten。

And you know for motivation， remember in the unit demand case in the Crawford Noer auction that was in fact the case。

 that was part of our proof that determines a was and equilibrium right so if you only want one thing and you grab it。

And you still have it later。 Well， that prices has stayed the same。

 and the other prices have only gone up。 So you're still very happy to have it。😊。

So it's not like you're going to fast forward in time and all of a sudden the unit demand Bider wants to relinquish it's good。

 okay， that never happens。So that seems to be sort of an important distinction between the unit demand case and the general case。

 So let's try to think you know。Are there conditions more general than unit demand where it's still going to be true that at no point in this auction will someone want to relinquish a good that they won previously？

嗯。So the formal definition of a gross substitute valuation is just exactly that。

It literally just says in an ascending auction and really in the Kelso Crawford ascending auction。

 if you find yourself holding some goods at the price that you originally bid for them。

 it's the case that you still want them。That's the gross substitutes condition。Or GS， for short。So。

 formally。We talk about two price vectors。Where Q is component wise is at least P。 Okay。

 so so what you should be thinking of is youre thinking about the auction， this auction。

 the Kel Cr auction at some time with some price vector P。 And then you fast forward。

 prices only go up。 So you have some only bigger price vector Q。

So there'll be some components where these are the same and some components where they're different。

And it should be the case that。If some bundle of goods S。Was I's favorite at the price vector P。

 So In other words， this is perhaps， you know， a set of items that it bid on at that iteration of the auction。

And then we fast forward。So that it's Q。Then。ち。There should be a set T。So that。

The stuff you had at the price vector P。A is going to be the goods whose prices have gone up so maybe you don't want these anymore S minus a are the prices are the goods that you used to have。

 whose prices have not changed and it should be the case you still want these What do I mean by you still want them。

 that should be a set of goods that you could augment them by。

So that this is one of your favorite goods with respect to the bigger price vector cube。Okay。

So once again， think about， earlier time and a later time with the prices of the earlier time being P。

 and then at a later time the prices have ascended and they become Q。On some goods。

 the prices have gone up strictly。 That's what I'm calling capital A。 So anything not in A。

 the price is exactly the same as it was before。So what this says is that if you wanted all of the goods of S at the first period of time with prices P。

And only the prices on the goods of A have gone up。 Okay so the ones in S minus A have not gone up。

 you still want these goods in the sense that you have a favorite bundle。

 which includes all of those items that you held previously。

So that's what it means to say you still want the goods that you bought earlier。

 given that the prices are the same。Okay。All right， so any any， you know。

 I'll give you what we're going to do next is talk about non examples and examples of this definition。

 but any help required just sort of parsing this？And again， in my opinion。

 the right way to sort of think of this the first time you see it is it's really just sort of exactly the condition under which it seems like Kelso Crawford might work。

Okay。Because， again， what happens in California Crawford。 So in unit demand it was simpler， right。

 you've got a good， then you don't have a good， and you have a good again。

 then you don't have a good and so on。 So that's pretty simple。 It's binary。Kela Crawford。

 right in general， you might get 10 goods。 And then at some iteration， you know。

 three of them get taken away from you。 next iteration， two more get taken away for you and so on。

 Okay， so your set keeps eroding。 And so this is just saying， you know。Whatever you have left。

Whatever your partial bundle from before is， you're quite happy to just extend it and you don't want to relinquish any of those goods。

All right， so I think it's easiest to see a non example。So this bidder here。Ass a non example。

That was the bitterder that got into trouble in the Kelso Crawford auction， bidding sincerely。

So why is this a non example， Well， suppose let's take the smaller price vector P to just be one in one。

Okay。So then what does this bidder want， what's its preferred bundle。

 well it's happy to take both goods， right if the price is one each it pays two， its value is three。

 utilities is one， that's the best it can do。Now imagine I increased just one of those two prices。

 so it used to be there both one。 Imagine I increased the first good to three。

so now the price of the combined model is four。So this person doesn't want either， okay。

 so it's only preferred bundle at prices three and one is the empty set。Okay。

 and that's a violation of gross substitutes。Because we increased only one price。

 only the price of good A。And so we did not increase the price of good B。 And yet。

 this bidder does want to relinquish good B as well。 It wants to jettison both of them。

So that's a violation of gross substitutes。Are。Okay。So， examples。So everything we've seen so far。

Has been gross substitutes。So for example， non identical goods， additive， gross substitutes。

 in this case the items have nothing to do with each other。

 so you just make so the demand sets are just defined independently on each good。

 there's no interaction。So。Unit demand。As I said， we basically proved the gross substitutes property when we argued that Crawford Noer converges to warholan equilibrium。

 Okay， we basically said， consider the moment at which you bid for a good， fast forward。

Okay if the other prices have only gone up， you still want the same item。

 you don't want to get rid of it。嗯。So the multi unitit a with downward sloping valuations in this language corresponds to a symmetric set function。

 meaning the value of of the the meaning your valuation depends only on the number of goods that you get。

 not on their identities。 That means the goods look identical to you。 and the downward sloping。

Just means that your marginal value for each extra good is only going down as you get more and more goods。

 That， again， is gross substitutes。 Intuly， you know， if I take goods away from you。

 it sort of makes the goods that you still have only more valuable。 Okay。

 so you sort of only still want them。I'll leave it for you to think that through。But so in any case。

 gross substitutes does unify the last two scenarios we talked about。

 scenarios three and four to common generalization。

And there's other stuff that we want to talk about explicitly。But that it covers。So for example。

 K unit demand is a generalization of unit demand。So unit demand basically says。

 if you give me a bunch of items， I'm going to throw away all of them except my favorite。

 So K unit demand says give me a bunch。 I'll throw away all but my K favorite。So formally。

 you would say for a general bundle S。You would just take the best subset of size of most k。

And let's say you would sum them。Okay， so the the input is the same as in the unit demand case。

A VIJ for each day。And then you just assemble the smartest subset of k goods amongst what you're given。

 which obviously is just the top K。You can also say apply a concave function to this。

 and it remains gross substitutes。 so the exercises will ask you to think about。

 a couple of these concrete examples。So the picture you might want to have in mind。

For growth substitutes。 And this is a picture we'll expand on more next week。 But for now。

You should think it gross substitutes as really being you know， again， the frontier of tractability。

 So it contains。Unit demand。With non identical goods， it contains， say additive。Again。

 with non identical goods and multi unit as well， multi unit downward sloan。Okay。

 another stuff is in there as well。看。So next week， we'll look at things that contain yes as well。

Okay。To questions about that。All right， so what I want to prove next。

Is I want to make good on this promise that it seemed like the gross substitutes condition is what is sort of needed for the Kelso Crawford a to function properly。

 So we're going to take the functioning property as meaning converges to a Walwasian equilibrium。

 And this what we're going to prove。 gross substitutes is sufficient for this to converge wellwasian equilibrium。

So the proof is pretty straightforward。But I think it's good to see it just to help really internalize this definition。

So theorem。Assume。That all valuations are gross substitutes。And assume sincere bidding。

Then the Kelpo Crawford auction。Converges。To Walwaian equilibrium， as usual。

 it'll be an approximate version， an M epsilon， whilewaian equilibrium。

 where epsilon is the price increment。Okay。So let me remind you just what's an approximate was in equilibrium。

 it's a price factor in an allocation。 So first of all， all unsold goods should have price zero。

And secondly， everybody should get their favorite bundle at the given prices。In this case。

 their favorite bundle up to an additive loss of M epsilon。

 where favorite bundle is just the usual notion of the demand。All right， so proof。

So we really design the rules of the auction explicitly so that the only way that a good will be unsold is for the price to be zero。

And this is exactly what disallowing people to withdraw bids gets us。

 So the only way an item can have no winner is if it never had a bidder。 And then， of course。

 its price was never incremented。Okay。So that's fine。

 so that doesn't actually use the gross substitutes。Property。Alright。

 so here's the role of gross substitutes in this context。So let's argue the following andvariant。

I this will be true at every bidder at every moment in time in the auction。 And again， remember。

 what's a little bit tricky is， you know， from a bitter's perspective， you know。

 when it's your opportunity to go。O， to bid， you grab some set of goods that you want。 Okay。

 and you're happy after that iteration。 then everyone else takes their turn。 Okay。

 and they rip parts of your bundle away from you。So this invariant has to speak about whatever sort of piece of the bundle that you last bid on remains。

So for all I， for every bidder。The claim is that the items you have right now， S subI。Are contained。

In some bundle that you want at the current prices。So in a set。Of DI Q epsilon。And so here。

The definition of Q epsilon is as before。If you already own it。

Then it's just the current price and for anything you don't own。

We think of it as being bumped up by epsilon。So this is the clam。Okay。So the base case is trivial。

 right initially you have the empty set， so that's a subset of anything you want。So。

So consider iteration of this auction。Well， if it was just your turn。Okay。

So if you just went in this previous iteration。By the inductive hypothesis。There existed。

A favorite bundle of yours， a preferred bundle of yours that contains the items you already had。

 And that's a good thing because the Kelso Crawford a only allows you to bid on items you don't already have。

 Okay so the inductive hypothesis ensures that there exists a choice of T that augments your current items S I into a bundle in your demand set。

Put differently under the gross， under this invariant， it says。

 even if I dropped to the constraint that you had to retain the current items and I let you bid much more freely for any bundle that you wanted at the current prices。

 you would go ahead and recollect to the same items you already hold now。

 so the answer to your optimization problem is the same either way。

 whether I can strain you to retain the current items or whether I don't。Right，' inductive step。

If I just bid。Follows from。The inductive hypothesis。So in this case， your current SI。

 not just is contained in some set of your demand set， it actually is a set in your demand set。

So S I is in。Do you haveQFpson because you just chose it so。And then on the other hand。

 if some other bidder just took it。Yeah。Then's just followed this follows by gross substitutes。

So why does it fall from gross substitutes， Well， you just consider， you know。

 the last time you bid on something， the last time you bid on something， it was in。Your demand。

 it was a preferred bundle at that prices at those prices。

 What has happened since people have taken some items away from you every time an item is taken away from you。

 the price has gone up。 so for the current price vector。

 anything you've lost has a higher price than before。

Gros substitutes insists on nothing on items whose prices have increased。

 And gross substitute says the stuff that hasn't increased， you still want。

 And if you're still the holder of these things you bid on。

 that means you're the most recent bidder and the price hasn't changed。

 Price only goes up when your out。Okay。So that's that。

So for all bidders at all moments in time in the Kssel Crawford auction。

 whatever you've got is a subset of what you really want。Okay。And from this， we're done。Okay， so why。

So a termination。At termination， nobody wants to add anything。Okay。

 so that means not merely are you a subset of something you really want。

 you have exactly what you want at the current prices。

Well at these current prices modular of these epsilons， right。

 So the invariant says if you think of goods you don't have as being epsilon more expensive than they really are。

 then， in fact， you have your favorite bundle。Now， in fact。

 those other goods aren't epsilon more expensive， So the real prices are epsilon less。

 There's the most M goods。 So you're off by most M epsilon with respect to the final prices Q with any other competing bundle。

Okay。So， that termination。S I is the preferred bundle。 It prices Q epsilon for all I。

 So this implies。you're an M epsilon or rising equilibrium。So this is one of those proofs。

 which really is just sort of meant to verify that you got the definition correct。I mean。

 we came up with a definition exactly so that this proof could work the way that it did。

So any questions about that？All right。So here's a cool consequence。

So this was all done generically in epsilon。 We can take epsilon as small as we want。Okay。

 so letting epsilon go to 0， we no longer get an approximate or rise in equilibrium。

 We get an exact one。So this in particular， gives a constructive proof that。

When all valuations satisfy the gross substance use condition， there exists o wise and equilibrium。

A set of prices so that the market clears。 everything gets sold and everybody gets their favorite bundle。

Now， you might not be in a position to appreciate this yet because I haven't made a big deal about existence or what lies an equilibrium up to this point。

 and we've always had it。But in fact， without the gross substitutes condition in general。

 you don't have any or roian equilibrium。So I'll leave the details as an exercise， but。

If you think about the same case for which the Crawford， the Kelso Crawford a didn't function well。

So you have one single minded bidder and one unit demand bidder。There is no wall rise in equilibrium。

So it's not just that the Kelso Crawford auction gets screwed up。

It's that the thing that the Kel Crawford option is basically trying to compute。

 namely a was in equilibrium just doesn't exist。 it's trying to search for something that's not there。

So it's， it's simple to prove this。For example。You might hope that in in the was in equilibrium。

 the first bidder。Would get both goods。That's the welfare maximizing solution。

 That's sort of what you hope would happen。But， you know， then it should have non negative utility。

 Its values 3。 So that means that sum of the prices that's too good should be at most  three。

So one of the two goods should have a price at most three/ hals。Okay。

 but then bitter number two is not going to be happy getting nothing if there's an item that has price only three/2s。

 And that means it's not getting it's a preferred bundle。 the empty set。

 We wouldd rather get a good at three/2s。Okay。So in fact， something stronger is true。Yeah。

So if at some point we do a bonus lecture on this stuff， this is something I might prove then。

 but I'm not going to prove it now， this is not that easy。So unfortunately， right。

 so gross substitutes usually abbreviate by GS。 turns out two of the sort of most relevant papers on gross substitutes are by two guys named Gul and Stketi GS。

 So there's these papers by GS on GS。 it's very confusing。Anyways， in one of their papers。

 they proved the following very cool theorem。Which says that actually。

 so we define gross substitutes as being kind of the limit at which we expect there's one particular auction to work。

 Kel Croawford to work。 Okay， but that doesn' that doesn't feel like a very fundamental definition。

 Okay， it was just particularulated as one a。But in fact， gross substitutes are， in some sense。

 the natural limit at which Walra and equilibria are guaranteed to exist。

And that starts sounding much more fundamental。 Well rising equilibrium are a basic concept。

 It's basically the notion of a clearing market with indivisible goods。

And we now see that sometimes you have them， and sometimes you don't。When do you have them， well。

 basically you have them in the gross substitutes case and not generally speaking beyond。Formerally。

 this is the statement。So consider any valuation。Which is not gross substitutes。

Then I can find you a situation involving VI where there's no waraz in equilibrium。And， precisely。

Then there exists unit demand。And remember， unit demand is just a special case of gross substitutes。

So enhanced GS。Valuations v minus I。So that in the full valuation profile V。

There is no w riseian equilibrium。Okay。So in some sense， if you want guaranteed generic。

 guaranteed existence of Orizon equilibrium， and if you want to consider a class that permits any unit demand valuation。

 then you cannot go any further than gross substitutes。

 there's not a single other function that you can include。Okay。So again。

 I'm not going to prove this here。 it's not out of reach of us talking about。

 but just I don't have time for it in this lecture。Okay， so if you look at cases。

 So a couple of the projects are about understanding， you know。

 can you go beyond gross substitutes in any sense， And this theorem says the only way to get guaranteed while rising equilibrium existence beyond gross substitutes is to relax。

The assumption that you allow every single unit to bitter and so perhaps surprisingly。

 there's actually a couple ways you can go beyond gross substitutes。

 so those will be a couple of the projects。All right。So today。

 the the first of the two lectures is going to be a little on the short side。

 It's possible the second one will be slightly on the longer side。 although possibly not。 We'll see。

 Maybe we can just finish early。So let me conclude this first lecture， just with a couple。

Statements about incentives。Okay。So a question you'd be right to ask is why do we care about wez in equilibrium？

What good are they in this context？Now， on the one hand， when we talked about unit demand bidders。

 they were totally crucial。We were trying to have an incentive compatible auction to do that。

 we needed to simulate the VCG outcome and we needed to understand the VCG payments。

 and we understood the VCG payments equaled the smallest well rise equilibrium。

So it was crucial for the unit demand auction。Now last lecture when we were talking about multiunit auctions with downward sloping valuations。

 and remember that's a special case of gross substitutes。

 we already saw that in this special case we lose the property that we had in unit demand。

 we lose the property that the VCG payments are a w roian equilibrium。

 okay we can't necessarily get them both simultaneously。So even in a special case of GS。VCG。

Does not correspond。To a wall equilibrium。Okay， so certainly that's not going to be true here。 Okay。

 we gave just a very simple， explicit example last week that shows this。So in other words。

 the Kelso Crawford auction， well it gets the， in some sense， the allocation correct。

 the allocation is， you know， up to epsilon welfare maximizing the same same allocation is in the VCG mechanism。

 It gets the payments incorrect。Okay。And that's a problem。

Let me just sort of say this once and for all。So the only way you're going to get an ascending auction。

 which is both expos incentive compatible and well for maximizing。

Is if sincere bidding gives you the VCG outcome。Where by outcome， I mean not just the allocation。

But also the payments。And the reason is twofold， one we've already discussed。

 which is the revelation principle， which is an epic。Auction。If you apply the revelation。

 principle gives you a dominant strategy and set a compatible direct revelation mechanism。

 so that's the first thing with exactly the same allocation rule， exactly the same payment rule。

The second thing is once you just think about dominant strategy mechanisms。

 the allocation rule uniquely defines the payment rule up to a constant。

That's something we proved last quarter for single parameter problems。 It's also true here。

 I'm not going to spend time in class doing it。 I'll give you one reference to the AGT book。

 It's not that hard。 I'm going take me maybe 15 minutes。

 I just want to spend that time in other ways。So you can either see the AGT book。Section 9。5。5。

Or at some point， I'll add some notes to the revelation principle discussion back in lecture 1。 Okay。

 but it's true， and it's not hard to prove。 So if you have two different dominant strategy mechanisms。

 both of which were the same allocation rule in this case， the welfare maximizing allocation rule。

 they have。 and let's say losers always pay zero， So they're normalized to be the same。

 The payment rule has to be exactly the same。 You can't have different efficient mechanisms with different payment rules。

So that backing out， going to ascending auction， you cannot have an ascending a that gives you a payment rule other it than VCG1。

 it's essential that you simulate VCG payments to get what we want， to get the E options。Sure。

So in particular， that means that it's not good enough to just run Kelsso Crawford。

would not give us a epic mechanism。 We have to get the the payments right， as well。Okay， so in fact。

I'm not actually going to have time today to talk about， you know， incentives。

 I'll give you a brief comment about it next week。 So instead。

 what we're going to do after the break is we're going to discuss a second sense。

In which gross substitutes is the frontier of tractability。 And so remember， in all of these cases。

 we've wanted just the sanity check of asking， when can't we at least get VC G to run in polynomial time。

And so it turns out， in addition to Warez and equilibrium their existence。

In a totally different tack， computation， efficient computation of the VCG mechanism also grows substitutes as the frontier of when we can do it and when we can'。

Okay， so let's wrap up the first lecture there and resume in sort of 10 minutes short。

