# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p15 -15-(Lecture 15_ The Price of Anarchy of Bayes-Nash Equilibria).zh_en -BV1fNVNzhEBg_p15-

So quick announcement， it's a week from today that the project outline is due March 5th。

So instructions on the webp page， I think I said one to two pages with some further detailed instructions。

Any questions about that about the project？Okay， good， so look forward to receiving those。嗯。

All right， so let me help you page back in where we were。

So we're smack in the middle of part4 of the course and the attitude we have in part 4 is that we insist that our mechanisms be simple。

 maybe not to play， but certainly to describe and execute And then the question then is just if we stick only to simple options。

 when do they do well under what kinds of conditions but do well。

 I mean they're equiria for some type of equilibrium。

And conditions perhaps on the valuations or what generality of equilibriumria that we're looking at。

So last lecture。I introduced our first simple Auction format。

Which is basically you throw up a bunch of items at the same time on eBay and you try to sell them。

So simultaneous second price auctions。So S2A。Is the abbreviation I'm going to be using？And again。

 I want to remind you this is sort of very different than all the auctions that we saw in the past in the sense that these are auctions where the action space。

 So in other words， what a player is able to do or able to report is way smaller。

 then it's type space or it's valuation space。 So again。

 we're thinking of bidders is having combatorial evaluations。 think like submodular evaluations。

 they have like two to the M private parameters。 if there's M goods。

 but I'm only going to listen to M numbers。 all I let you do in this auction is submit one bid for each of the M items。

 Each of them is then sold with the V a to the highest bidder， the second highest price。

 So bidders have to somehow figure out how to communicate the most relevant information for the items that they want using this very small action space。

 So it's very simple mechanism to execute or describe。

 not necessarily that easy to figure out how to bid。

So we got off to a good start with our agenda of proving near optimality guarantees for welfare for simple auction formats。

 Here's what we proved last time。So we made the following two assumptions。

So we thought about bidders with some modular valuations。 Actually。

 it was a little bit more general than that。So in fact， it was okay for bidders。 if you want。

 you can just think sub modular。 that's fine。But technically we proved them for what are called X OOS or fractionally sub additive valuations。

 that just means the valuation is the maximum of a bunch of additive valuations。 Okay。

 we proved dilemma last week saying that every submodular evaluation indeed can be represented as the maximum of additive valuations so we proved this for even more general than the class of sub modular evaluations。

 That was one assumption。And you know， so this is certainly a restriction on valuations。

 but don't forget how hard we were struggling with this when we were doing things like incentive compatible mechanism design。

 Okay， so this is already a challenging problem。 We never had a decent mechanism， for example。

 that handled bids with arbitrary so modular evaluation so to prove guarantees with some simple oxygen equilibrium that feels like a victory。

Then what were we looking at。 So last week， we only discussed pure N equilibriumria。

 not really because they're well motivated just because I wanted to sort of you know。

 impose layers of you， complexity gradually throughout the lectures。

 So we thought about pure equilibriumria。We'll move on to other equilibrium concepts today。

 And also remember that with second price auctions。

 we have to make another assumption about the equilibrium。

 even in the victoryy auction with just one item in two bidders， you have these bluffing equilibrium。

 You have these problems with overbidding。 Okay so maybe my value is0， but I bid really high。

 And if you bid really low， then I don't actually have to pay the price for it。

 Okay so you have these low welfare equilibrium， even in the viy a caused by overbidding。

 So what we did is we only proved guarantees for equilibrium without overbidding。

And the precise sounds very important first day， but the precise definition we used is just that if you looked at the bundle that the items that a bid won。

 then the sum of its bids for those items was at most its value for those items。

 that's what we proved the factor to approximation for。And so if these are met， then。

We proved that the welfare。Of this pureyt equilibrium is at least one half times the opt to welfare。

 I also showed you an example that the one half is tight。 Okay there's an example which is two items。

 two bidders， unit demand valuations of puret equilibrium with no overbidding and it was off by 50% because the bidders kind of got miscoordinated on the two items。

 Each one got the one that they didn't really want。So I think that brings us up to date。

 Okay that was the last lecture。All。So now where are we going go from here。

 So of give you the big picture。 So the main focus of the first lecture today is going to be to go beyond pure Nationallibria with so pureash I equilibria。

 that's a full information concept。 Okay， so that's for games where players know what everybody wants。

 And in auctions generally， when you think about them， people don't know what each other wants。

 right So if I'm in a first price auction with one of you。 know。

 I'm trying to guess what you're going to bid。 And the reason that's hard for me is because I don't actually know what you're willing to pay。

So the more suitable equilibrium concept to study equilibrium ineffici in auctions is Bayes N equilibrium。

 that's the main topic for the first lecture。 I also want to give you some exposure to other simple auction formats。

 not just this one simultaneous second price auction。 So in the second lecture today。

 we'll talk about first price auctions， which are well motivated in this context。But again。

 as far as what's on tap。We want to do the price of anarchy。

 we're going to stick with this auction format for the current lecture， S2 A's。

 but you want look at the price of anarchy of Bayes Nash equilibriumlibria。Good。In fact。

 and I'll put this somewhere as an optional exercise。

 But if all we cared about were the pure equilibriumria of second price simultaneous auctions。

 something I proved to you earlier would have already been enough。

 So earlier we looked at and it won't be obvious why these are connected。

 although it's actually a pretty easy proof。 So we took the Kelso Crawford auction。

 So that was the ascending a that I showed you way back when we were talking about gross substitutes。

 I showed you the Kelso Crawford auction。 and the main point when I first showed you that auction is that if bidders have gross substitutes valuations and they all bid sincerely。

 then the auction terminate at a rise zone equilibrium， which in particular is welfare maximizing。

 Then we actually returned， I don't know if you remember。

 but we returned to the Kelso Crawford auction。 when I first told you about submodular valuations。

 And I said as a thought experiment， we were asking you know how easy ignoring incentives。

 how easy is just the welfare maximization problem with submodular evaluations。

 So it said as a thought experiment， imagine we just ran Kelso Crawford。😊，And let it terminate。

 Okay in general， there aren't mores in equilibrium for sub modular evaluation。

 So it's not going to be optimal。 But actually， we prove that it's within a factor 2。

 so Kelso Crawford terminates for submodular evaluations with well with the allocation within a factor two of welfare。

 It turns out sort of a simulation argument。 you can show that pure equilibriumria in the simultaneous second price as。

 correspond to the kinds of outcomes you get from Kelso Crawford with some modular evaluations。

 So we actually could prove this to just from inheritance from the work we did a few weeks ago。 Now。

 don't get me wrong。 I didn't waste your time last week because the way we proved this is important for the results。

 I'm going show you today on Bay national equilibrium。 but if all we cared about we purenalib。

 we wouldn't have needed to do that work last week。Alright。

 so lots of connections between the different， different things we've been talking about。

So how are we going to go about this， How are we going to prove bounds on the how good Bays N equilibrium are。

 Well， here's the plan。I'm going to ask you to remember not in detail， but just sort of in spirit。

 one of the major themes from the price of anarchy section of last quarter's course from 364 a。

 namely extension theorems。So one of the main points I tried to convey is that very often when you're bounding the price of anarchy of games and lots of different application domains。

 you can get away with the following analysis approach。 You can prove a POA bound。

Only for the pureac equilibrium of a game， just like we did last week for simultaneous second price auctions。

 And then as long as your proof for pureacria conforms to a certain template meet some additional conditions。

 then， in fact， basically with no extra work。You get the same bound。In 364A。

 we were talking about mixed naash equilibrium， correlated equilibrium。

 and coarse correlated equilibrium。So back in 364 a。

 we were talking about things like routing games and facility location games， this kind of stuff。

 And we were criticizing purena equilibrium。 We said， well， first of all。

 it might not exist all the time。 in some classes of games it does。

 but some classes of games it doesn't。 But then secondly， even if it does exist。

 it could be hard to compute like P S complete。 And even mixed national equilibrium。

 theyre always exist。 they can be hard to compute like PP hard to compute。

 And so instead we talked about these learning algorithms。

 these sort of weaker equilibrium concepts correlated and course quality equilibrium。

 for which theyre learning algorithms that quickly converge to them。

 So those retractable equilibrium concepts。 And so that's why we were really happy to have price of energyarch bounds。

 not just for purena equilibrium， but also for these much bigger sets， more tractable sets。

 correlated in course quality equilibrium。 So that's just sort of a brief review of what we did in weeks 6 and 7。

 I think， of last quarter。😊，Now， why do I bring that up here Well here we're in sort of exactly the same kind of situation as analysts as actually like someone who has to write down a proof。

 we're much happier if all we have to do is worry about purena equilibrium that's why we warmed up with purena equilibrium last week。

 but what do we really care about in an auction context。

 So we don't really care about pure National equilibrium they're not really modeling what we're trying to get at this incomplete information aspect of auctions。

 what we care about in the Bays National equilibrium with respect to some prior distribution。😊。

But these extension theorems from last quarter， maybe give us some hope that we can be lazy。

 maybe just like we had extension theorems that allow us to extend bounds from pure equilibriumria to things like co equilibrium。

 Maybe we can have extension theorems that extend bounds to pure equilibrium to baes Nash equilibrium。

 Okay， and we will。 Okay， that's going to be， you know。

Somewhat explicit in the discussion for this lecture。 So that's the plan。All right。

 so this is what's easy to argue about。 This is what's well motivated。All right。So。Let me remind you。

What's， you know， the high level outline of the proof of this result。That we did last week， Okay。

 let me remind you how we did this。So key step in proof。

Let me also just sort of remind you a little bit about。Price of antiarch proofs。

So the first step in almost any price of anarchy proof is you have to figure out how to use the equilibrium hypothesis。

 Okay， And so what is， what does that do， It says， well， you know， if this player switched。

 it would be even worse off。Why is that useful， It gives us a very flexible way of dering lower bounds on the equilibrium utility of a player。

 anything that it would switch to is utility would only go worse。

 that gives us a lower bound in how well it's doing in equilibrium。

So in constructing the proof then the question is， all right， well。

 so what hypothetical deviation should we plug into to the equilibrium condition？Last quarter。

 it was kind of very easy when we weren't talking about optionsuctions。

 we were talking about things like routing games。 we just said， well。

 let's look at the path this player is supposed to be taking in the optimal solution。

 and let's just think about switching to that。There's sort of there's this extra level of indirection。

 however， in auctions， which makes things a little forces us to be a little bit more creative。

 So what we'd like to say is， well， look， right So we're at some equilibrium。

 it doesn't have full welfare。 Let's look at the best allocation。

 And why doesn't this player just switch to grabbing items 3，5 and 7。😊，Okay， if you think about it。

 that's not quite well defined because， you know， the actions of a player are not grab3 goods。

 The actions of a player are submitted bid vector Okay。

 and sort of lots of different collections of bid vectors give rise to exactly the same allocation。

 Okay， so if what we care about as a well from maximizing allocation amongst the infinite number of bid vectors that induce it。

 we have to somehow figure out which one to use in our proof。Okay。

So I we sort of started this with a unit demand case where and the whole reason I started the unit demand case is because this particular challenge is relatively easy to see what to do。

 right， So for the unit demand case， where every bidder is only going to get one item in any sensible allocation。

 Now you can just say， well， we're at an equilibrium。You know， this bitter I。

 maybe it's supposed to get some item J in the optimal solution。 And so now intuitively。

 we use the deviation where I just goes all in for item J， meaning it bids 0 and anything。

 not equal to J。 and it bids its full value on the item J。

 And that was sort of the natural way of sort of trying to grab item J off the shelf。

So that was the unit demand warm up。 Then， you know。

 the whole reason X O S fits in so naturally here as the maximum of additive valuations is because。

 you know， basically， there was a sensible way to define this exact same thing。 What。

 What exactly should be the， the deviating bit。So what we did in the proof。Is， you know。

 given the bidder's valuations。And there's some bid profile that we're trying to lower around the welfare of。

We exhibited deviations。B star1 up to B star n。So again， in the unit demand case。

 B star1 was just look at what item1 is supposed to get in the optimal solution bid0 and everything else and its value for that item。

 In the general X O S case， we said， well， let's look at the items。

 the bid one gets in the optimal solution。 Let's look at the additive evaluation。 Remember。

 this X Os evaluation is the maximum of added evaluations， So let's look at the added evaluation。

 which is tight for， say items 3，5 and 7， whatever one gets in the optimal solution。

 and then thatll tell us exactly what numbers to bid on items 3，5 and 7。

 and we bid 0 for everywhere else。 So again， even in the X O S case。

 how do we construct this hypothetical deviation。 We look at the items we're supposed to get in the optimal solution。

 and we go all in for those items。 and the exact meaning of all in is given by these add evaluations and the support of V。

 so that's where these B star I came from。Okay， and。Here's how。That was the definition of B Star I。

 and now I'm going to write down kind of the major milestones in the proof okay the inequalities that we had。

So。Right so this is where we wanted the lower bound。 So we were starting for some equilibrium B。

So think of this as。So not all of the steps of the proof will require this。

 but sort of in the motivating case， we're thinking of。B is being a pure Nash equilibrium。

 satisfying no overbidding。But we'll keep track in these inequalities exactly where these hypotheses are used。

So the first thing we did is trivial， which is we just said， well。

Instead of lower bounding the welfare， we're going to lower bound in even smaller quantity。

 which is just the sum of the player utilities。Okay。So remember， this is values minus prices。 Okay。

 so this is this， this is just the values。 This is that minus prices。 So that's clearly only smaller。

 priceses are only non negative。嗯。Then。We use the fact that we're dealing with a purena equilibrium to say that any deviation only makes people worse。

 in particular， switching to the hypothetical deviation B star I only makes eye worse。

And then the relatively hard work。Which was just sort of a bunch of manipulation。Was。

 as usual with these price of anity type proofs， we have to relate this entangled term to stuff we actually care about。

 like welfares of the equilibrium and the optimal solution。

 and specifically you know the bulk of the work was proving that we could lower bound。

Some of these things。By the optimal welfare， which is great。 But， you know， there's a price to pay。

 There's an error term。 So minus something， right， So this is what we want。

 this is what we want to say is big。 This is our equilibrium welfare。 This is exactly the target。

 So that's great。 And then the error term， we proved。Was the sum of the equilibrium bids。Okay。

 so look at all the players。This is the set of items that I wins in the equilibrium B。

And then I just look at what I bid for it。 Now remember these are second price auction。

 so this is not necessarily what I is paying for J。 This is what it bid for J。

 what it pays maybe much less， the second highest bid okay。So that was the hard work。

So this is where we basically looked at each item separately and we said， well， look。

 either there's some other bid which is high or there isn't in the first case。

 then the relevant term is sort of nonpositive and we're done in the other case。

 it wins at the appropriate price and we've got what we want okay so we did last time。

And then the final step is where we applied the no over bidding。

So nobidding exactly says that the sum of your bids on what you win should be a most your value for it。

So by no overbid。Okay。So we can upper bound the error term by the sum of the V of Si's。

 which is just， of course， the welfare at equilibrium。Okay。And so then rearranging。

 we got the factor， too。So any questions about that。 So this again is review。

 but you may recall this from sort of the smooth discussion last quarter with these proofs it's really important to focus in your proof on exactly where you're using which hypotheses It's actually very crucial for these extension theorems that in some sense。

 you only use your hypothesis in a restricted way and restricted regions of the proof。

 That's when I'm spelling it out again okay。Any questions about this？This is what we did。All right。

 so let's actually talk a little bit about where our various hypotheses get used in steps one through poor。

All right， so first of all。And this， this has the same spirit as last quarter。

 The equilibrium hypothesis。 The fact that B is a pureash equilibrium is used in a minimal way in this proof。

 Of course， it has to be true somewhere。 We're not going prove a factor2 bound for every single bit vector in the world。

 Arrbitrarily stupid ones。 So it has to be used somewhere。 and it's used right here。 Okay。

 It's used in step 2。For each。 and we use it once for each player。

 We pretty much have to use it once for each player。

 And we just say the utility is lower bounded by if it's switched to this B star I deviation， okay。

It's obvious that the hypothesis is not being used in one。Okay，That's just trivial inequality。

 It's obvious。 It's not being used in four because that's just from no over bidding。 You know。

 just go back to your notes from last week to verify that it's not being used in3 either。 Okay。

 and this is the same as last quarter。 Last quarter。

 The part of price of antiarch proof where we actually had to do some hard work。

 It never involved the equilibrium hypothesis。 It always was just involved inequalities and manipulation。

 Sam thing here。 Okay， so it's not obvious from what I wrote on the board。

 but just trust me or check your notes。 We didn't use the equilibrium hypothesis in2 either。

 sorry in three either。 That holds for an arbitrary bid vector B， not only pure equilibrium。Okay。

 so P&E hypothesis。Used only in two。Not one or three or four。O。So that's the first point。

The other important point。So let's look at these deviations， B star I。Okay。

So suppose're suppose we're trying to figure out B star1 because remember what B star1 is。

 B star1 says， look at what items you're supposed to get in the optimal solution and go all in bidding for those items you're supposed to get in the optimal solution。

So let me ask you。 So let's try to understand， what information we need for this to be well defined。

 Okay， so do I need to know the valuation profile of V。For this deviation B star1 to be well defined。

So B star1 says， look at the items you're supposed to get in the optimal solution。And go all in。

So suppose I didn't tell you what the valuation profile was， would that make sense？No， right。

 because the optimal allocation is a function of the valuation profile。

 right Op allocation means welfare maximizing some of the Vs。

 How do you know it maximizes the sum of the Vs without knowing the Vs。

What if I told you just I's value， what have I told you just Bi one's valuation。

 and I didn't tell you valuations V2 through VN， would that be enough for B star1 to be well defined？

No， it still wouldn't be， right。 So the optimal allocation is a function of all of the Vs。

 not just V1。Okay。So okay， good， so what if I just tell you the valuation profile V？

And I don't tell you the current equilibrium bid vector B。 So you know V， but you don't know B。

Do you have enough information to define B star1？Yeah， you do。

The definition we're talking about for B star1 is independent of anything other than the valuation profiles。

 Remember， how do you define it， Look at the optimal allocation。 That's a function of V only。

 whatever it is。 and go all in。 And that's a function of your own valuation only。Okay。

 so this is important。 All right。 So B star 1 through B star N。

 they're constructed oblivious to what equilibrium B we're talking about。 Okay， They depend on V。

 all the components， not just V I。 They don't depend on B at all。Good。So choice of B star1， B star n。

Depends on V。But not be。你看。All right。So let let me just derive a sort of immediate conclusion from these two points。

 So again， I don't expect you to remember the details， but this know I'll tell you this is true。

 and it'll be easier for you to verify going back to you notes it's for last quarter。

 This is exactly the definition of a smoothness proof that I gave you last quarter so what we did last quarter I gave you a couple of concrete examples in routing games and facility location games I gave you this template。

 what are the steps in the proof and the key insight in what was common in those proofs is that you only use the pure equilibrium hypothesis in a very restricted way you use it once per player and you use it for hypothetical deviations which are defined independent of the equilibrium。

That's exactly what we're doing here。 so this literally is exactly meets the definition I gave you last quarter。

So I'll just state that。's not that's not the key point for today， but。You know。

 it's good to know that。So all this stuff implies that。This game is one one smooth。

In the sense of 364 a。There's one sort of technical difference。

 which is it's one1 smooth under the overbidding condition。 Okay， so the smoothest。

 the smoothest definition I gave you last quarter， it was for all it's basically， you know。

 there's an inequality that had to be true for an optimal solution， S star and for all S。

 So here it's going to be true for all S that satisfy no overbidding。 Okay。

 so this is a little twist。 but it's basically the same thing。When no overbidding holds。Okay。

 and so this means the theorems that we approved last quarter simply apply immediately to this game。

 Now， last quarter， we weren't talking about Bayes National equilibrium。

 So it's actually not quite what we want。 But， you know， it's still， it's a good start。

 So the extension theorems that we had last quarter are immediately relevant to what I've told you about this game here。

 right。😊，So as a consequence， the price of energy bound of one half。Extends to all。So again。

 thinking about it as a full information game like last week， mixed equilibriumria， correlated。

 coursear correlated， as long as they randomize only over no overbidding profiles。Okay。

 that's the little twist that we need。So only over。No over bidding。Big profiles。So， for example。

 if you consider theres various ways to interpret new over bidding。

 the most draconian way to interpret new over bidding is just to redefine player strategy sets to be those where they don't overbid on any bundle。

 Okay， so then youd have this automatically。 Then every bid profile satisfies no over bidding。 Yeah。

 So I wonder how the exception here works。 there is no。Yeah， good question。

 So I forget if we ever talked about that last quarter。

 we may not have because we probably only applied it to games that had purena equilibrium。

 It works out exactly the way you'd want it to work out， which is it just literally is still。

 still works in the following sense。 So for the extension theorem to apply。

All all you're responsible for proving is that whenever a pure equilibrium exists。

Then it is nearre optimal。 And if there is't one you're off the hook， it's not your problem。

 The extension theorem still works。So there's no pure in natural equilibrium， then it's just optimal。

Well， well， I would say for， right， So okay， good。So remember。

 you have to prove it using this template， so it's not clear that just because there aren't any。

 you could prove a bound of one using this template。嗯。But in principle。

 you could have games where that sort of thing is true。I mean。

 it's sort of funny because the extension theorem rescues you from vaccuity。

 I think that's the right word。 right So it could seem like you're proving something vacuous about this this empty set of pure equilibriumria。

 But then the guarantee holds these other sets that are guaranteed to be non empty。

 mixed equilibrium and so on。 so in some sense， I mean， it kind of says。😊，You know。

 you may have thought you were proving something about puria， but you weren't。

 whether you knew it or not， you were provingroving it about these bigger sets， yeah。

So that's also still true here。 It's a good question， excellentlen question。Okay。So again。

 so we're not getting to the punchline yet， I just want to remind you you already know a fair amount about extension theorems and also just point out that some of the technology I've taught you in the past is equally relevant to the new games we're seeing now。

Other questions。Allright， And so again， as far as， you， So what do we do。 So okay， So this is good。

 know， last week， I only told you about pure equilibriumria。 But fortunately。

 the proof I showed you enables last quarters extension theorem。

 So we get it for these more permissive concepts。 It's a good start。

 But these are all traditionally viewed as full information concepts。 And again。

 what we really want in an auction setting is Bayes National equilibrium。

 We want to model them as games of incomplete information， So that motivates the question， know。

 can we also have one of these for Bayes National equilibrium， And we can。

 although we're gonna to need a different proof， And that's what I'm gonna to show you next。😊。

All right。Heres， here's what we want to bound。 Okay， so the bays Nash。Price of anarchy。Now。

 for this to make sense， you need to specify a prior distribution， right。

 So the set of Bayes National Lib depends on the prior。

 Okay So if you want to argue that Bayes National Lib are good。

 you need to say with respect to what prior。And so this is defined as you think it would be。

 So basically， you just look at the welfare of a worst equilibrium over the optimal welfare。

One thing I I want to remind you， though， right。 So in a game in a Bayesian game where you have this prior evaluations。

 it's not like there's some fixed optimal allocation， right。

 So the valuations are going to be different for different coin flips， right。

 Sometimes they'll be high。 sometimes they'll be low。

 sometimes different players are high versus low。 So you know。

 the optimal welfare is a function of the input of the valuation profile of V。And V is drawn from F。

So even when we talk about the optimal welfare。What we mean is the optimal welfare。

 on average over what the valuation profile is， okay。So opt to welfare。

For the valuation profile of V。OkaySo for each possible V， we look at the maximum possible welfare。

 and we average that over all the V's you might see。So that's as good as we could do， obviously。

 with any auction。 That's what BCG would do， for example。Okay， on top， we watch the same thing。

Of the worst。Bs Nash equilibrium。So really， you know for this lecture we'll be talking about worst bayasticlib that satisfy no overbidding。

 et cetera， et cetera， and so here again， we measure it in the same way。So remember okay。

 let me remind you what a Bay national equilibrium is， so remember strategies。

 when it's a game of incomplete information， it's a function from your valuation to your action。

 okay so it's a function of what you want， how do you act？So。It's going to be welfare。

So I'm using sigmas for those functions。 So this takes as input valuations。And outputs actions， i。e。

 bid vectors， M vectors， okay。And so， so given valuations， this is the corresponding bids。

Of the bays na equilibrium， Sigma 1 up to Sigma n， those are the bids that induces an allocation。

 that allocation has some welfare。Again， as you vary over what people's valuations are。

 you're getting different bid vectors popping out of their strategies。

 you're getting different welfares for the allocation， and again we're just averaging。Okay。

So that's the definition， so this is how you measure performance of a bayesasticric equilibrium。

 this is how you measure the optimal performance。For simplicity， okay。

 so strategies are also allowed to be randomized， and we'll even use that in our proof later。

 meaning， you know just like in a game of full information， But if I know my value is 10。

 maybe I going to randomize over bids in some way。 In that case。

 you would also have an expectation here over the randomization over the actions in sigma。

 but that doesn't change anything I'll say today。 So I'll often just omit that for simplicity。

 so go ahead and think of the sigmas as deterministic。s。It's not without loss。

 but all the proofs extend trivially to the randomized case。Okay。

 so we want to prove that this is close to one， it's certainly the most one。And all right。

 so any questions about that， is Nash Pri of Anarch。Good， we'll be talking about this all day today。

So a question， though， is， there's this dependence on capital F。Right。

So the price of M is going to be different for different F's， different priors。

So what f is sort of worth studying more than others？How should we choose that？And， you know。

 pretty much any， you know， you know， there will be applications where maybe you really care about some particular prior。

 But， I mean， at the level of abstraction， we're talking about any choice of F would feel pretty arbitrary。

 frankly， and unsatisfing。So we basically want to say that this is good for as broad a class of Fs as possible。

 Maybe even for like every single F in the world。 That would be great。 O。

 maybe for arbitrary prior F。So that's a little too much to hope for。And so basically。

 the rest of this lecture， I'm gonna to show you two results。 Okay， so the first result is this one。

Which is is that F is a correlated distribution。The price of energyarch can be bad， very bad。Okay。

So again， remember prior distribution， it can be correlated or can not be correlated。

 It could be a product。 Okay so remember it's a distribution over a bidders valuations。

 So it correlated just means you know what it usually means。

 It means basically if you know one's valuation， it tells you something nontrivial about say bidder2s valuation and if it's a product distribution。

 then it's just the product of the unconditional marginals。So。

The first thing I'm going to show you in this lecture in the remainder of this lecture is I'm going to construct for you a correlated valuation distribution where they're going to be so modular。

 you're in a special case of so modular， but the price value is going to be way， way。

 way worse than two。Okay。The second thing I'm going to show you in this lecture。

 the other thing I'm going to show you is that if it's a product prior distribution。

 no matter what the distribution is， then it's a factor too。Okay。

 so we get a positive result for product distributions。

 we cannot get a positive result for arbitrary correlated distributions。

That's the high level takeaway。Alright， So any questions before I。

 the example is a little bit detailed。's， know， it's gonna to take 5 or 10 minutes to go through。

 Any questions for that。Okay。So this will give you a taste of the truly twisted things you can accomplish with correlated prior distributions。

All right， so proof of。So the bidder is， in fact， they're going to be unit demand。 Okay。

 so a special case of gross substitute special case of submodular，And not only that。

 a bidders value for each item will be either 0 or one。 Those are the only possibility。

 So there'll be items you want。 You don't care which one you get and items you don't want。

 So you should really think of the welfare maximization problem as just unweighted bypartite matching in this example。

 okay。So how many items are there， there's going to be n plus root in minus1 items。Okay。

 so essentially linear number of items。Also， just to keep the description of the example a little simpler。

 I'm going to allow myself reserve prices， okay。So， soon。Each item has a reserve price。Of。

One over end the 16。So a small reserve price。Now I don't actually need this for the example。

Reserve prices can be simulated with dummy bitterders。 So basically。

 if some item has a reserve price of R， then I can simulate that by just adding a dummy bidder who only wants that item and whose valuation is R for that one item。

 Then if you show me any basees national equilibrium with the reserve prices。

 I can extend that to a Bay national equilibrium with the dummy bidders just by having them bid their valuation。

 Okay， so a lower bound with reserve prices carries over to a lower bound with dummy bids。

 Ie without reserve prices。 but it's simpler if you just allow me the reserve prices。Okay。

 so all right， so what is this capital F， What's this valuation distribution。

 Basically all I'm going to give you a randomized algorithm to define the valuations。

 And so the prior is just the distribution generated by that randomized algorithm。All right。

 so here's what we do。And a picture will help here。All right， so again， biparttheite matching。

 so over here we have the bidders。There's n of them over here we have like n plus root end items basically。

So of the items， we're going to choose。A subset。Xi。Of root n-1 of the items。See for the common items。

And these are chosen uniformly at random。So for all subsets of you that have this cardinality。

 we pick this one uniformly random。These are goods that everybody wants。Okay。So this is C。And again。

 think unweighted by apartheid matching， where an edge just says， yes， you know。

 the bidder's value really is one for that item。So everybody wants C。And remember。

There's way more bitterders than of these items。 There's n of these。 There's root n of these。

This is a very unbalanced， complete apartpartheite graph。All right。

The other items are called special items。And each bidder is going to want to be interested in a distinct。

 special item。And so the next thing we do is we， in our randomized algorithm。

 generating the valuations， we randomly order。S。Okay， so we label these items in S1，2 of the n。

And bitter I is going to want only the I special item has no interest in the others， okay。

So precisely。For a given bidder I and a given item J。 remember their unit demand valuations。

 So I just have to tell you their values for singletons on bundles。

 you just take the max of all the singletons in there。So a bitter eye wants。The Jaith special item。

And it's also happened to have anything that's a common item。And it doesn't want anything else。Okay。

So in the picture here。We have this set S， exactly the same cardinality as the number of bidders。

 and we have a perfect matching。Okay。And the items that are put in C are chosen at random and the perfect match of the planted perfect matching。

 if you will， between the bidders and S is chosen uniformly at random。So that fully specifies。

 you know， for each possible set of coin flips that fully specifies unit demand valuations for the bidders。

 so we can interpret this as a correlated valuation distribution。And it certainly is correlated。

 right So for example， the common items， everybody has value  one for those，All right， so question。

What is the optimal welfare？In this setup。AndAnd does that depend on any of the random decisions？No。

 good。 right。 So， So the biggest value anybody can ever get is one。

 So the biggest welfare is clearly a most n。 But there's always a planted perfect matching between the bidders and the special item。

 So you give everybody their special item， and you can get value welfare N。

 So the VC G mechanism would get welfare N， probably one。So opt welfare equals n。

With probability one。Okay。Now here's the key point。

Here's why this is such a nasty example for equiria。So you know， suppose you're bitter one。O。

Now remember how it works in these Bayesian games， right， so you know the prior distribution。

 that's common knowledge， you know your valuation。And you can do a， you know， Bayesing update。

 You can look at the posterior you given your valuation。 And that's all you know。 Okay。

 you know what are the strategies people are using。 But the point is that， you know。

 what do you learn from your valuation， right， You learn a set of exactly root end items that you want。

Okay。And they have some labels。You actually know， because you know the prior。

 you know one of them is a special one reserved just for you。And you know。

 the rest every single person wants， right but by symmetry。

 you have no idea which is which one of these root end items has zero congestion。

 the rest have crazy congestion， but by symmetry， you have no idea which is which。So， you know。

So that's intuition of why this is a disaster for equilibrium。 So a key point。

Fitter eye can't identify its special good。Among the rude end at once。Ja。

So let's see how this really plays out。So this is the high level bit of intuition。

 why does this actually imply that you can't get reasonable welfare with the Bays National equilibrium？

Well， the first claim， and this is exactly why the reserve prices are useful。

Is I want to argue that a bidder can't just， you know， bid all over the place。 bid for everything。

 okay。So the claim is that no bitterder。Wants to choose an action。That would have it。 So remember。

 these are unit demand bidders。 Okay， so you only want to win one thing。 Okay。

 so people aren't gonna to bid on stuff which has value 0。 That can't possibly do them any good。

 So there's these root end items that they want。 And they may go for more than one， you know。

 to hedge to sort of hedge， right， But they don't But they really don't want to do is like win a lot of these because their values one。

 no matter how many they win。 But， of course， the price that they pay ads。

 the more these that they win， okay。So there's no way you want to pick an action。

Where with decent probability， you win lots of these things。

Let's say more than end of the one thirds items。With probability more than one over end to the1 sixthth。

Okay， so I claim you'd never do this。You'd never pick an action which gave you this。

 which gave you a sort of distribution of these properties because if you did。If so。

 you'd pay an expectation。Well， one over end of the one6 to the time， you'd pay。

 you'd win strictly more than end to the one third items。 And remember， because of the reserve price。

 you have to pay one over end of the one6 on everything that you win。 or if you like。

 because of the dummy bitters that are in the background。O。So this here is this is the reserve price。

And your value is with probability one at most one。 Okay。

 so this action would get you negative utilities。 Certainlyly， you're not doing that in equilibrium。

Okay。So， then。Let's see。 So the probability then。The bitter eye。Winds， it's special item。Well， okay。

 so maybe， you know， occasionally， it wins tons of stuff。

 So maybe occasionally it just wins all of the good it wants， including the special item。

 So just I'll give you。😊，End to the one6th to cover everything that's not excluded here。

 So this is when you win more than end to the one thirds items。

 But then if you win at most end the one thirds items by symmetry。

 all items are equally likely to be in there。And。And there's root end items that you want， okay？

So plus。So this is an upper bound on the number of items you're winning。 O， in the common case。

This is how many items you're trying to pick your special item from。 So this， again。

 is end to the 16。So in other words， you will almost never get your special item。At an equilibrium。

Okay， that's what this says。So。And so now if you think about it。

 if pretty much nobodys getting their special item。Right。

 then all of these are just going unsold right and there's no way you're getting linear welfare。

 Okay， the only way you can approach， there just aren't many goods here。

 There's only rude end goods here。 So the only way you could get linear welfare is if a linear number of these goods were actually going to somebody who wanted them。

 okay。So。The expected welfare of Bayes National equilibrium。So okay， so for each bidder。

Some tiny fraction of the time it getting a special item。Plus， you know。

 maybe all of these gets sold all the time。 So that's another。U。Rudan。So this is the common items。

These are the special items。But in any case。This is。Over end of the five sixths。Okay。

Which means the price of anarchy is polynomial in it。 a far cry from two。Okay。Now。

 the one sort of ten fine print with the dummy bidders is when you so reserve prices clearly have nothing to do with welfare。

 it's just part of the mechanism。 When you replace them with dummy bitterders， it actually。

 so dummy bitterders have some value and they might actually win something。

 and then all of a sudden welfare could go up。 but there's only a linear number of dummy bidders and the value that they have is just this reserve price one over end of the one6th So that the dummy bidders might contribute another end to the five6th term。

 that actually doesn't the lower bound still holds。 even with the dummy bidders。All right。

So that's the lower bound。Any questions about that？All right。So again。

 you what we're trying to do is we're trying to sort of funnel in on you know what is the you coolest thing that could be true right and we've known forever that we can't do better than a factor two。

 we proved that last week， you know even for pure equilibrium of full information games。

 we're trying to extend the distributions and now at least arbitrary correlated ones are out okay。

So the best case scenario is。Her a best case scenario， at least， is product distributions。

 I should say， an open research question。Is to identify classes of correlated distributions where you can have positive results。

 Obviously， this is a rather special， rather pathological， correlated distribution。

 And it's totally possible You can get good bounds for just swaths of correlated distributions。

 I have no idea。 Nobody knows。 Okay， So the positive results we know are just for the product case。

 And that's what I'm gonna show you now。So it's a little bit。

 I'm exaggerating a little bit when I say the best case scenario， but。Because conceivably。

 presumably， you could go beyond products， but。Arbitrary colate is not going to work。

So it would be great。 We be to get a factor to。For all product distributions。

So just one thing I want to point out。If you want， you can think about the full information case that we talked about last week as a special case of the Bayesian case。

Okay。Full information game。 That's where you know everybody's preferences。

 You know what everybody wants。 Beijing games。 you model the uncertainty about what peoples wants with a prior。

So no uncertainty just corresponds to a prior with no randomness。 Okay。

 and prior that's just a point mass。 Okay， so that's a legitimate prior distribution F。

 It's a degenerate kind。 You could have a distribution capital F。

 which just said this person's value is always this。 Second person's value is always this。

 Third person's value is always this， etc cetera。It's de generaterate， if you want。

 you can think of that as a product distribution。 It's just a product of point masses。 Okay。

 so even with this product restriction。You knowIf we prove a bound that holds for every single product distribution。

 we're certainly proving bounds on the full information model as a special case because full information corresponds to degenerate product point masses。

 Okay upshot being we already know one half is tight for full information。

 So certainly we want to do better than one half。For arbitrary product priors。

 the best hope will be we still get one half for arbitrary product priors。 Okay， and we will。

 but that's the best we can do。Okay。So， theorem。And this is also- this is still in that same CKS paper。

I'm sort of modernizing the terminology slightly， but really it's all there。Like I said。

 sort of before ahead of its time that paper。Chris Tudelu Kox and Shapira。All right。

 so I'm going to be vague about the no bidding condition we'll just you know the one that you need will just pop out obviously in the proof。

 so I'm just going to start doing the proof and then when we get to the end。

 it'll be clear what we need for no overbidding it'll be nice actually be pretty weak。

 It'll just be a sort of on average version of the nobidding condition we had for the pure case so。

It will be， no more worrisome than before。Okay， and as usual。

 the expectations on both sides of the kequality are with respect to F。Okay。All right。

And so I'm just going to right now prove this theorem specifically for simultaneous second price auctions。

 but it is， in effect， an extension theorem。 So it's still going to be the case that whenever you have a smoothness like inequality。

 which I'll write down now， it will be the case that bounds of that form。

 even though they seem like they're about pure equilibrium and full information games。

 those bounds extend via the proof I'm about to give you to Bayes national equilibrium， okay。

So they'll be easier to understand if I state it specifically for this model rather than abstractly。

 but as will probably be clear。嗯。The proof is quite generic。So let me just remind you。

What we already know。For the full information case。 So we know the smoothness like inequality。

 We know that for all valuations， for all bid vectors。There exists B star1 up to B star n。

 these hypothetical deviations。So that。So this is the inequality I was calling three at the beginning of this lecture。

 Okay， so this is the one where we did all of the manipulation。 We didn't use any of our hypotheses。

 but we did all the manipulation。So it's， you know。

 this is after you've invoked the equilibrium hypothesis in step 2。Okay， I'm going to call this star。

So this has the flavor of one comma 1 spoononness。 Okay， So there's no， So this， right。

 So this is exactly what we were calling 3。Okay。So this is immediately after we've applied the equilibrium hypothesis to get this entangled term。

 and it's also immediately before we've applied the no of rebidding hypothesis to relate this back to the equilibrium welfare。

 So derive this inequality。 We literally used no hypotheses at all。

 We did not use that B was in equilibrium。 we did not use that B satisfies any no of abidding condition this is just for the choice of B star Is。

 and again， remember this B star I says given V， look at the items I'm supposed to get an optimal solution and go all in。

 That's the definition of B star I。We with that choice of the beast our eyes。

 this is true for every single bit vector B， whether or not it's an equilibrium。

 whether or not it satisfies no overbidding。 Okay， and this we already proved。

 this was the hard work last week。 So taking this as input。

 I'm just going to show you how to turn this into a Bay Nash equilibrium bound。Okay。

 and that's going to be a generic argument。 Okay， that'll be an extension theorem for bass National equilibrium okay。

It'll be a little bit of work， but you know， next 10，15 minutes， the rest of the lecture。

Is that clear。 so this is just true， we're taking this as proven。Good。All right。Okay。

So let's start to prove of this thing。So consider a Bays N equilibrium。And， you know， when we， again。

 when we need it， we'll impose the appropriate No forbidding condition to complete the very last step of the proof。

All right， now。So we're responsible for proving a bound in the quality of the se。

 a lower bound on its welfare。And as usual， know the main thing we have going for us is this is an equilibrium so if we let players deviate。

Then we can lower down their equilibrium utility。And so， okay， so so that's the first step。

 We have to figure out， okay， so what， what， you know， again， here's the art。

 What deviation should we invoke。Okay。So there's an obvious idea。So the first step is going to be。

 So what I'm saying is the first step is going to be the same thing of the template。 Okay。

 lower bound utilities is by invoking that， in this case， Bay na equilibrium condition。

So the lower bound eyes。Expected utility。In Sigma。All right。

 so what hypothetical deviation should we use， Well， your initial response to。

 didn't we already solve this problem， isns't that the whole point of these beast our eyes， right。

 So Bea our eyes say， you know， look at the optimal solution。

 go all in for the items that you get the optimal solution。

 So it seems like that's what we should do。Right， so you just use the deviation。B star I of V。

So there's a problem with this idea。Though。So I want you to think for a minute about。

Why we can't do this。我で次。Yeah， so V V is the valuation profile of all the players。 So， to review。

 we agreed that， you know， one of these deviations B star 1。 remember what this is。

 Look at the items you get in the optimal solution and go well in。 We agreed that， you know。

 knowing V1 is not enough。You need to know all of these。 you need to know the valuation profile。

 but once you know the valuation profile， you can define B star1， for example。

 So that's why I wrote B star I of V。Where V is the whole profile。

But I claim this actually doesn't make sense right now。So， let's recall kind of。You know， this。

 the information available to players when they reason about how to act in a Bayesian game。 Okay。

 the whole point of a game of incomplete information is you don't know what other players want。Okay。

 so what's public is the prior distribution。 And the other thing that one thinks of as public is the strategy profile。

 Okay， so， if， if I only knew what you wanted， I'd know what you would be doing。 I know your action。

Right，But then the uncertainty is all modeled。 Well， I don't know your valuations exactly。

 I just know it was drawn from this prior， okay。And of course。

 I know my own valuation with certainty。 Okay So I know the prior my valuation and the strategies。

But knowing the prior my evaluation on the strategies is not enough information for bitter I to compute this deviation。

Okay， so the problem is that this is not well defined。

 given the information available to I when it's reasoning and how to act。Okay。

 that's why this doesn't make sense。So problem。Yeah。I only knows。VI。Not v minus I。O。

So this B star eye operator， know， we don't have an input for it。Okay， so。That's sort of too bad。

 But I mean， if we were really stubborn about wanting to kind of prove things this way， you know。

 stubborn about the fact that we want to， you piggyback on the solution we already have for the full information case。

 use these B star I operators。Well then okay， we need to somehow come up with an input。

 we need to feed it in evaluation profiles who can tell us how to bid。

 tell us what hypothetical deviation to consider。We've got VI， that's cool。We do't have v minus I。

 but we do have a prior。So I guess we could kind of come up with our own fictitious profile for the other players。

 and it would at least be well defined to stick that into this deviation suggestor。

It's not clear this will get us anything， but at least it starts being making sense again。Okay。

So bitter。 and again， all of this is just a thought experiment for the proof。

 Like we're not literally thinking of players reasoning this way， right。

 we just need some lower bound and equilibrium utility。 And so we need some deviation。

 We have what seems like a really good way of generating deviations。

 and we're just missing this V minus I。 So where do we get it just in our proof。

 We're going to sample from。The prior distribution。Okay。

So that's I think that's kind of the simplest way to salvage this idea。 And happily it works。 Okay。

 So I'm going to call this the doppelganger trick。You heard it here first。So。

Here's what we're going to do。 Here's the deviation we're going to use in our proof。Okay。

 so bitter eye knows its valuation VI， and it knows the prior。So it's samples。APro。

 it only needs W minus I， but humor me。 I'm gonna sample everybody from F。So in other words。

 I'm I'm basically giving you a randomized algorithm for bitter eye。

 And so this is just a mixed deviation， which is allowed。 You can do mixed actions in， you know。

 Bay games。 It's fine。So first， I sample types for everybody， evaluations for everybody。

Now I plug in to my B star I which sort of tells me a deviation， I plug in my real valuation。

 which I know VI， and I plug in W minus I， these doppelgans for the other players okay？

And then that tells me a deviation to consider， right？Choose action。呃。BI star。O。

So what we're doing is we're saying， well， you know。

Bitterize doing whatever it's doing at equilibrium。 If it really wanted。

 if it was crazy and it really wanted to， it could do the following instead。

 it could sample doppelgans。 It could compute the welfare maximizing allocation。

 It could look at the items as starai gets in that welfare maximizing allocation。

 and then it could bid all in for those items。It's a well defined strategy。

 And we're at a bay equilibrium， This well defined strategy gives you only lower utility。And that's。

 that's really we have a little bit of kind of manipulation to do。

 But that's really the key idea of the proof， actually， right there。

So the key idea is to still piggyback on what we did in the full information case。

 even though it's not full information and just make it work by sampling the Doppelgans to bridge those two worlds。

Alright， so any questions。Before we go the rest of proof。OK。All right， so here's the derivation then。

All right。Let's just focus on a single bidder。 So again， so now at high level。

 we're doing the same thing we're always doing。 We're getting a lower bound on I。

 equilibrium utility later。 we'll sum them up and sort of， you know。

 relate everything to terms we actually care about。All right， so。How well， O， so what is， in fact。

 Is expected utility in the equilibrium。Well， VI is known。V minus I is unknown。

 so we're averaging over what v minus I might be drawn from the rest of the distribution。

Given all the valuations， these are the actions that are played and I get some utility。

 so this is how well I was doing at the equilibrium Sigma。And of course。

 it would only do worse if it switched to this， the Sigma Darri。

So now let's expand this just using the definition of what Sigma star is， okay。So this， right。

 so this itself is randomized， right， This is basically an algorithm， which is doing that。

So this is equal to。Averaging over v minus I， that's just the other types。

But then this is averaging over the coin flips of bitter eyes deviating algorithm。And let's see。

 so now it's UI， and given that it chooses the qua fliplips W。

 it's going to play the strategy B star I， V I W minus I。Again。

 this just means you make up the doppelgans， You look at the optimal allocation and you go all in for your items in the optimal allocation in that problem。

Other people， of course， are just doing their thing。Counccillor's definition of Sigma starri。Now。

 here's where I'm going to use。 So the place where we actually use is a product distribution， which。

 again， we know is necessary and must be used in the proof。

 The previous example shows that shows up in this very subtle way。

So now what I'm going to do is I'm just going to。Change this VI。Into a WI。Actually。

 maybe I'm getting ahead of myself。Let me double check。Actually， let me do two things。

Let me stop there and then tell you what the next two steps they're going to do at once。Yeah。So。

 next。I'm going to do two things， so first of all。So so we have this inequality， equilibrium utility。

 some deviation utility。 This is true， whatever VI is， right。

 So remember bitter eye optimizes separately for each possible for each valuation VI that it has。

But I'm just going to average this inequality over the Vs。 So I'm going to apply the expectation。

 So I'm going to integrate out over I's valuation。The quality， of course， is still true by averaging。

And then， two。I'm also going to exchange。I'm going to change that V。 I to a W I。

 And the reason I'm doing that is because that'll put it in the wheelhouse of the moon is inequality。

 ultimately， okay。But just for model checking purposes， I'm going to exchange that VI。And WI。

And the reason I can do that is because these are IID。 and if you think about it。

 it's sort of subtle。It is important that F is a product distribution。

For me to get away with doing this。O。So this is V minus I floating around。

 There's a separate W minus I floating around。 But because F is a product distribution。

 I can basically mix and match。 Okay， V I W I， V minus I W minus I doesn't matter。

 There's no correlation between them too， so I can interchange them Will nilly。

But I encourage you to think about that a little bit offhand。

 I encourage you to think about where this exact proof would break if F was correlated。

 and it's in this step。Okay。So。Therefore。怎 now。I want you to think about。I dont know。

 I guess I've averaged out， so here's where we are。Averaging over the type profile of just。U。

Bterized utility。We can lower bound the x an equilibrium utility of bitter I。

By this expectation over two ID type。Profils， valuation profiles。Of UI， BI star， W。

Sigma minus I V minus I。So that's just immediately applying these to these。Okay。

 so now we're going to sum。Are the bidders。And okay。

 so the reason I wanted to massage it into this form is because once I sum over the bitterders。

 this matches exactly our sness inequality so what's inside the expectation on the right hand side here is going to be of the form the left hand side of our key sness inequality。

So。Some over eye。Apply star。 That's what I mean by the smoothness inequality。And we get that。

The sum of the X anti utilities。All right， It lower bounded by。 again。

 we have this expectation over both the real valuations and doppelganger valuations and now applying。

The moon is inequality。We have an opt of W。So here we have B star eye。Of W。

And remember B stars are a function of the valuation profile。

 so here you're always optimal solution with respect to the valuation profile for which you were defining the B stars。

Here we're defining the deviation profiles with respect to the doppelganger valuations W。

 so the bound is with respect to the optimal welfare for W。OkaySo that's the first term。

From the smoothest inequality。And then， the second term。

RightSo where does this this is in terms of the B's， which are the equilibrium bids。

 so the B minus I's。 So when we apply that after summing these。

 that corresponds to applying to the sigma minus I of v minus I， which is sigma of V。So minus。Some。

Or I equal 1 to n。Some J and Si， so here it's going to be sigma。Of V， okay I。e。

 what's happening at equilibrium。And then up here， for BI J， that now becomes Sigma I， a V。

So remember？This is the valuation。 This is the bid。 The bid is an M vector。 We're looking at good J。

 So for this to make sense。I take this M vector and I look at bid J。 But again， what's B over there。

 that role is just being played by Sigma I of V I here。So that's what we get。 Okay， so again。

 what did we do， We took this， We summed。I put the sums inside the expectations。

 and then I applied our smoothest inequality star to what we got in here。And this is what we get。

Any questions。O。All right， good。And。All right， so now now we're done。 All right。

 so we should say what the nobidding condition is。Okay， so。This term。Doesn't depend on V。 Okay。

 All we're doing here is looking at the optimal welfare averaging over the doppelganger types。

 But the doppelganger types W are just drawn from the true prior。So this term。

Is just the opt expected welfare。Okay。That's what this becomes。 Does't matter if it's W or V。 I mean。

 W is made up， but who cares's the right distribution。 So this gives us the right benchmark。

And the way I want you to think about this。Okay， so this is independent of W， right。

 So now you can just forget about W。 Just focus on the true types V。Allright， so fix I。What is this。

 This says look at in the equilibrium。 Remember， Sigma of V is the Bayes National equilibrium we started with。

 It says in the equilibrium。 Look at the items that I wins and look at how much it bid for the items that it wins。

 Okay， so in English， this is just the total bid by bitter I on the items it's winning in the equilibrium。

In the Bayes National equilibrium， so I'm just going to write that in English， actually。

So this is just。Sorry， it should be an expectation here。Expectation over the equilibrium。Eyes。

 total bids。On items， it wins。In the equilibrium。Okay， so it's， it's a lot of letters。

 but it means something very simple。So again， I just sified this right hand side is exactly the same as this right hand side。

Okay， great， so that's basically how you take the smoothest inequality and using the doppelganger trick extend it to something about Baysnash equilibrium。

Now at no point now we're not done， and in fact， we haven't proved anything because I haven't used a no overbidding hypothesis and we know that nothing is true without a nobidding hypothesis。

 but at this point of the proof it's clear what nobidding hypothesis we need to conclude okay。

So what do we have over here？We have the sum of player utilities at equilibrium。 Again。

 utilities are just values minus prices。 So that's even smaller than the welfare。

So the expected welfare at equilibrium is lower bounded by this。

Lower amounted by the optimal expected welfare， what we want minus this error term。どだ。

So our no rebitting condition。Is just this should be， but what do we need it to be？

For our factor two， in the full information case， we wanted our error term to be it most the equilibrium welfare。

 the National equilibrium welfare here we want it to be at most the Bay N equilibrium welfare。

And so we only need to upper bound this by the average welfare of bitter eye in the equilibrium。

So we insist that this is， at most。ただ。Averaging over the types。V I of S I。Of sigma of V。Okay。

IeIs expected。Contribution。To the welfare。To be overall welfare。Obviously。

 a sufficient condition would be that this would hold always so that with probability one。

 the sum of your bids on what you win is at most your value for it。

 But all we need for this proof to go through is that this holds on average okay。So if sigma。

 the Bayesastic equilibrium satisfies this no overbidding property for every single bitter eye。

 then we can upper bound each summman of the error term by its contribution to the welfare。

 So the whole error term is the expected welfare。 So we move that over and we divide and we're done。

So under this， no overbidding。Condition。Expected welfare of the Bay's National equilibrium Sigma。

Is at least one half times opt？Expected welfare。O看。Any questions about that。

So what I hope is clear is that this whole Dopppper graner trick。

Is generic in the sense that if I gave you as input some inequality of the form star。 And again。

 so what a star say again， it basically means for each valuation profile V。

 but independent of the bid nectar B， you compute these deviation these deviations B through B star n so that this holds for every big profile P。

 if you give me in effect an algorithm for generating these hypothetical deviations。

 it proves its inequality， the doppelang or trick just pushes that inequality through to an analogous inequality that averages over the prior distribution。

 assuming that prior distribution is a product， assuming that valuations are independent。

 so it wouldn't matter if you had sort of different factors in the opt and in the second term。

 those factors would just carry through and so on。 So that's sort of a11 smoothness。

 if you had a lambda mu smoothness， you would get a lambda over one plus mu more generally instead of one half So even though I prove it just in this one case for concreteness think of。

This is a one extension theorem for Bays Nash equilibriumria。Okay， let's let's resume in 10 minutes。

 We'll talk about first price auctions。