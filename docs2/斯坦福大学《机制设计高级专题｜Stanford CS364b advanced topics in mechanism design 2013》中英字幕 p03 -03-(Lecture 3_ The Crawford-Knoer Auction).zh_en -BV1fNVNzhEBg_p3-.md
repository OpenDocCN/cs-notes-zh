# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p03 -03-(Lecture 3_ The Crawford-Knoer Auction).zh_en -BV1fNVNzhEBg_p3-

So I guess just maybe。You know， as far as so I mentioned this last time。

 but we're I'm going keep exercise sets for at least a few weeks and then at some point。

 so the main deliverable for the course is a project。

 at least for those of you taking it for a letter grade， so I'll probably post， start posting topics。

Probably in week four of the class will be my guess。

 but I just want to mention it now because I'm definitely happy that people propose their own projects。

 so if there's either something from other research you're doing。

 you think would work well with this class and you could kind of have it be a win win， get a project。

 get credit for this class but also have it be good for your own research group that's cool or if there's already something that's triggered your intrigued you that's happened so far this quarter or happened sometime last quarter maybe just start thinking about that in the back of your mind but I mean I'll give out enough concrete project topics for everybody in a couple weeks anyways。

Oh， yeah， right。I also I should have done this last week but I forgot。

 because we're putting the videos up on YouTube， I'm required to get a release from all of you。

So passes around。So this says， you know you agree to either one have your likeness appear。

On a publicly available video， or if you don't agree to do that。

 then you agree to sit somewhere in the classroom off camera。And that's fine。

Most of the classes off camera， you may have noticed。三年。I think you do， actually。

 I'd feel better if you did。😊，Yeah。Good， good。 Okay， so it's been a week。

 So let me just sort of remind you where we left off last week。

So this first segment of the course I'm thinking probably the first three weeks is all about the theory of ascending auctions and so what I'm doing so what we're doing is we're designing ascending auctions for increasingly complex scenarios so each of the scenarios I'm choosing to unveil a new layer of complexity in the design of ascending auctions so in the middle of what I've been calling scenario three so scenario one was unit demand bidders and identical items that was easy you just use a single ascending a scenario number two was non-ident goods but added evaluations that was also simple you just use parallel ascending auctions although we saw already we needed to introduce X post instead of dominant strategy implementations now we're in scenario three。

And the good news about scenario3 is we can get very striking positive results。

 We can get pretty much everything we want。 They're greatending a。 The bad news。

 or maybe it's a feature。 if you want to call it that is it's actually quite intricate even though the solutions are simple understanding why these simple solutions work so well is's pretty intricate。

 So we already saw some non-trial theory of this scenario last lecture and we'll finish that up this lecture So again what is it So we have nonidentical items and we talked about motivations last week and we're assume bidders are unit demand。

 So if you give them a bunch of items they throw out all of the ones except their favorite。

 So there's a private value Vj for each bitter I and good J and if you get a bunch of them。

 you just take the max。 So that means without loss。

 we can think only about allocations where each bidder gets at most one good i。e。

 we can think of allocations as matchings in scenario number three。

 And again what are we shooting for in all of these scenarios。

We want an auction that's the analogous of dominant strategy incentive of compatible。

 But as we saw in this context， it should be exp post incentive compatible。

 That means sincere biddings and exppost na equilibrium。

 which means you don't have to know what other people's private information are you just have to know that the bidding sincerely with respect to some valuations。

 As long as you know that sincere bidding for yourself is the best response。

 whatever your evaluation。 So that's what this means expos incentive of compatible。

 We want maximum surplus。 Actually we want something even stronger。

 We want basically to simulate the direct revelation outcome of the VCG mechanism。

 which in particular is maximum surplus。 And then we also have this criteria of being simple at the very least polynomial time。

And so last lecture， again at a high level， the reason this seemed like a challenge。

For scenario number three is that in particular to simulate the VCG payments。

 the VCG payments didn't seem like that simple a thing it was this difference of two different matchings。

 and we were restricting ourselves to these very simple ascending a and we needed some reason to believe why ascending auctions might suffice to compute these VCG payments so the culmination of last lecture was characterizing the VCG payments in a much simpler way than they first appeared in terms of while rising and equilibriumlibria So let me just remind you about them。

So recall。So here Q is a vector of prices on the items。

 here M is a matching between the bidders and the goods。Is it Walrasian equal to Bum or WE。

 if and only if？So first of all， each bidder should get a favorite good。

By which I mean the item to which bitter eye is matched in M。Should maximize its。Utility。

So it's value for the good minus the price it has to pay。 If all of these are negative。

 then we just think of this as being the empty set， okay。And I'll also use on occasion。

The notation for this set。The demand D I of bitter I at a given vector of prices Q。

So this is the demand of a bidder at a set of prices in a unit demand context。 And then， you know。

 again， this would be trivial without any other conditions because we could just set the queuees to be infinite and the matching to be empty。

 So it's also important that unsold goods have to have price 0。So J unsold。Only if Q of j equals0。

Okay。And then the key result from last time。Which took some work。But having done that work。

 we'll now just use it。Which is that if， that， in fact。

The VC G payments can be characterized in terms of all rise and equilibrium。 So first of all。

 the VC G outcome is aar equilibrium。 It's point number one。 Second of all。

 among all of the prices that arise in equilibrium。 And we know there can be many。 So first of all。

 there is a smallest one， which is an obvious。 And second， actually。

 the V G payments are that smallest equilibrium。So if P of G is the VCG payment。Of the winner。

Of item J， or if item J goes unsold， just define p of J to be 0。Then。So P of M， let's see。

 so where M here is the VCG allocation。Is it will rise in equilibrium。And two。

P is component wise at least as small as any other wall is equilibrium price vector。Okay。And again。

 what was the point， the point is now rather than conceptually shooting for the VCG payments。

 we're going to conceptually shoot for the smallest awa in equilibrium。

 why does that seem like progress Because if you look at the definition of awas in equilibrium it feels like the kind of things that are true by the stopping condition of an ascending auction。

 I guess this seems like progress， something we could plausibly compute with an ascending a So the point at today's lecture is to actually show you the auction which does indeed compute the smallest as in equilibrium or equivalently compute to the VCG prices。

And let me give you a warning， my guess is there's going to be two lectures with a break as usual。

 I suspect the first lecture will go a little bit longer。

 but then the second lecture will make shorter。 Okay， so we'll finish at the same time overall。

 but it might be a little bit front loaded today。So any questions before we start before actually。

 the next step is I'm actually going to show you the option。

 And then the rest of the lecture will be analyzing it， proving that it does what we want。

any questions？All right。So the good news is that the auction itself， very simple， very attractive。

 It's really kind of the simplest thing you might possibly hope can work， which is great。😊，All right。

Here's the auction， we'll call it the CK auction。After Crawford and Noer。And again。

 a lot of this class will be very recent stuff。 But last week and this week are not not lectures of that form。

 This is old stuff。All right。All right， so the intuition。

 we're just going to start with the prices being 0。 There's going to be over demanded goods。

 and we're just going to raise prices on over demanded goods。

 And we're going to hope that supply and demand equalize at some point。 And that's when we'll stop。

So initially。All prices are zero。And there's going it's gonna to be a notion of bitterder is being assigned or unassigned。

 So a means there's some item that you're tentatively the winner of。 And I should say。

 for those of you that remember the Gail Shapley stable matching algorithm。

 you might enjoy looking for parallels between this auction and stable matching。

 There's actually a number of them。So all bidders initially are unassigned。Naturally enough。

And so here's the main loop。So remember， this is an iterative option。 It's not direct revelations。

 So we're never going to directly ask people for their valuations。 We're just going to ask people。

 well， given our current prices， what do you want， meaningan。

 which is your favorite good at the current prices。 Okay， so those are going to be the queries。

So for any bidder which is currently unassigned， does not have some item， we say， well。

 which item would you want given the current prices。 Again。

 we collect that information from all the unassigned bidders。So ask each unassigned。I。

 I'm going to use this notation， D。Of Q。Okay。So here DIFQ is actually so if there's ties in this definition。

 this is actually asking for all of the things that maximize utility。

 sort of remarkably in this auction， we actually only need one from each bidder。

 so each bidder can just choose an arbitrary favor good andt tell us and again if it doesn't want any of them。

 it should tell us because if the prices are too high。Okay， so if none。Allright。

 so either if there's no unassigned bidders or if every unassigned bidder says no。

 I don't want anything， the prices are too high， then we stop。

 Okay and the tenative winners become the actual winners and the current prices become the selling prices。

So， if none。Halt。And again， the current allocation and prices become the final ones。Otherwise。

Pick some such bitter eye。And the good that it wants。At the current prices。

And we're just going to give J to I。So if you like。

 you can also think of this as bitter eye is sort of outbitting the current holder of the good J。

So assign J2 I。Now， if I is the first person to ever bid on this good J in the history of the auction。

 then it's not kicking out at anybody else。 Okay， and we also just leave the price at zero。

 But in the general case， it's going to be that there was some I prime who was the previous bidder on J who had been the tentative winner。

So if I。Outbid。I prime for J。Then。We make i prime unign。And also。We bump up the price of this good。

So increment。Q of J。By Epsilon， where Epsilon， as usual。

 is just some small increment that we choose in advance of the auction。Okay。

So the first bidder on a good gets it at zero， every subsequent good changes who the winner is and bumps up the price by and epsilon。

Okay。Actually， I just realized I had a typo。ち。So when you ask people for their favorite good。

Actually， this doesn't make a big difference。But for lecture， I'm actually gonna。

Ask them for their favorite good at the prices Q with an epsilon added everywhere。 Okay， now。

 that's almost exactly the same thing。Right， so if I add epsilon to every single part。

 so the good it doesn't change your favorite， except it might cause you to drop out when you weren't going to drop out before。

y， that's the only difference。 But let's just do it this。And that's it。 That's the whole option。

Upon termination， you pay the price is Q。U。Let's see， no， no， we're actually going to have you pay。

 yeah， so the Q， right， so it didn't get increment exactly， exactly。So let me just write this here。

So。So， at current。Alloccation。And prices Q。That's right。So conceptually。

 when we ask a bidder for its favorite， we're envisioning incrementing every single good。But really。

 it's only the one that it actually picks。 It's gonna get incr。 Okay， but， you know。

 this is gonna introduce a distization here of epsilon and a bunch of stuff。 But that's all it does。

 Okay， so it's not a big deal。 Yeah， but this is the formal description。Exactly。

And because this was the comment， because the bidder was agreed to pick a good J at this price with the increment。

 then we know that it's happy to have that good， or at least it has non negative utility for that good even after the increment。

Okay。All right， so that's the whole auction。So this is it。

So the rest of the lecture is just going to be proving that this does everything we want。

any questions about that？See it again。No。So you mean here？Yeah， so， in fact， I mean。

 this can be implemented in many ways。 I mean， so one thing you can do is you can just pull the unassigned ones。

 And as soon as anybody says they want to outbid somebody else， you stop and you go with that person。

So you know， I just， I single this out because I always want to focus on you know what are the queries。

 What is the communication between the seller and the bidders and you know。

 at least in the maximal implementation， every single round the subset of unasigned bidders are given a so-called demand query at the price Q plus epsilon。

 But again， if you wanted to optimize it that easy。 So for everything to work。

 you just need to pick an arbitrary bidder I and an arbitrary who's unassigned and an arbitrary good J in their demand set and proceed。

 That's all that's necessary。So I prior with this description。

 it seems like you could implement it one way and I could implement it a different way。

Might come up with different。Allocations。knowUp to the error。 Yeah。

 so up to the discretization error， I agree。 So so there's a question whenever there's， you know。

 in some sense， it's underdefined， you know。I mean， in a bunch of ways。 So sort of amazing。

 it works actually。 So you know you could pick any number of unassigned bidders and then they could offer any number of their favorite goods。

 And in principle each of those decisions can have a lot of influence over the trajectory。

 but in the same spirit of the Gae Shaplely stable matching result that actually the outcome is independent of those choices。

 the same sort of things going on here。 And actually， if if you go back what I promise you。

 So what am I promising you that this is going to do and promise you this is going to simulate the VG outcome。

😊，Which basically means I'm promising you that the final prices will be the VCG payments right so the VCG payments are obviously defined independent of any ordering here。

 so if I say that this always equals this one fixed thing。

 that's a proof that the output of this is independent。

 so the sequence of iterations will certainly depend on how you make these decisions。

 but the final output will not， which is a totally non-trivial feature of this algorithm。So again。

 all the complexity here is in the analysis， none in the option。

 which arguably is exactly how you want it。 Okay， if you have to have complexity somewhere。Alright。

 so let's start developing a fuel for this option。So first， just a couple trivial observations。

 So notice that if you're a bitter I and you bid on some good J， Okay， you're the ten of winner。

And you will continue to be the tentative winner on that good。Until someone outbids you。

Once you're assigned， I will not ask you for further input。Okay。

 so the only way that you relinquish a good is by someone else taking it away from you。

So then in particular， if you think about it， once a good has been bid on。By a bidder。

 it will forevermore be tentatively to assign to somebody。Okay。

 so once you're tenly assigned to someone， you always will be for the rest of the option。Okay。

So I bid on Jay。Retains it till out bidd。And then once so。If J is ever bid on。Will be。

Assigned at the end。It may change hands many times。

 but it's never going to be put back in the pool of unassigned goods。All right。

 and assuming sincere bidding termination should be obvious。

this is always a feature of ascending auction， It's clear you're making progress。

 the prices only go up， you know if I'm a bidder， I have some maximum willingness to pay for any item if the prices get higher than that。

 well， obviously I'm going to drop out。So terminates。

And let's say the maximum valuation of any bidder。Over epsilon， the amount of progress we're making。

 this is as high as the price would ever get on the single good。

 and then times the number of goods M。Okay， so it's pseudo polynomial。

 So if you' were taking the algorithms class， this wouldn't be ideal。 But you know。

 for such a simple ascending auction， this is just fine。

 And you can imagine ways of accelerating it like as the prices rise， you know。

 you increase epsilon accordingly， we're not going to discuss optimizations。

 so for the basic version， termination is clear。Okay。So the first a is an easy one。

And it's just going to confirm the intuition we've had so far that it seems like nearly the Walraian equilibrium property could probably fall out pretty easily of the first asing auction you'd think about that equalize supply and demand。

So let's make that precise。So sincere bidding。Results in an epsilon or as in equilibrium。

And on the exercise set that's due today， I ask you to prove that if you have almost wellizing equilibrium。

 you necessarily have an almost surplus maximizing allocation。So hence。Close to Mac surplus。

In case you're going to be off by at most M times epsilon from the surplus。 Okay。

 so as epsilon goes to zero， you have no surplus loss。So let's prove this is true。

 Okay let's prove the epsilon R is in equilibrium condition。 remember that what that condition is。

 it's the same as the normal WE condition， except you're allowed to be assigned to a good where you're off by epsilon here。

Okay， to the way， so it's still going to be true that you never have negative utility。

 but it may be that your utility is epsilon less than if you've gotten some other good of the current prices。

 that's the definition。So approve。All right， so how about this， How about。How about this condition。

Unsold goods have price 0。 Why is that true？That's from here。Right。

So the only way you go unsold is if you were never bid on， if you were never bid on your price of0。

So that's good。So now let's try to understand。Why a bidder is matched to its almost favorite good。

 I mean， in English， very quickly， it's just because at the time you bid for a good。

 it was essentially your favorite up to an epsilon。

 and then things only started looking better as the rest of the auction proceeded。So， formally。

Suppose I at the end of the algorithm is matched to J。And here I'm allowing J to be nothing。Well。

 consider the last time that I was asked the last time that I was unassigned。 and it said。

 I want Jay。Okay。So I'll say when I bid for J， with the understanding that Jay is the empty set。

 this was bidding for nothing。At that point。Jy。So， so these， so this is。

 this is some intermediate iteration of the auction。 not at the end in general。 Okay。

 so it's not the final price vector Q， It's some other price vector。 But of course。

 since it's an ascending auction， it's at some point with only lower prices。So when I bid for Jay。

Jay was I's favorite。At the current prices。Okay， I'm lying a little bit， why am I lying a little bit？

朝セさ。Yeah， up to Epsilon。 So I asked for its favorite at Q plus Epsilon everywhere。 But then， in fact。

 after the assignment， I only bumped up J's price by epsilon， everything else stayed the same。 Okay。

 so if it was basically tied between two goods， all of a sudden at the current price is after I sort of broke that symmetry and made the one that it got a little bit more expensive。

 But up to an Epsilon， that was its favorite。AndNow here's sort of a really important property of the unit demand setting。

 which is that as the auction proceeds， this is only more true。Okay。So since then。

All right so this was， know， some iteration number 124 out of a total of 180 iterations。

 So what could have happened in the final 56 iterations。 Okay， Well， first of all。

 what's going on with the price of good J。In those last 56 iterations。Nothing。Right。

 the price doesn't change unless you're out bidd。 And I was the final winner of J。

 And I'm I'm sort of rewinding to the point that it was the last bit on that good。

 the last bid on that good。And of course， it' it's an ascending auction。

 So the other goods are only getting more expensive。 Okay， so this is only more true at the outset。

Since then， let me just write only more true。So Jay's price unchanged。Others going up。Good。

 that's it。Okay， number one。嗯。So looking ahead a little bit， so。For the second lecture for today。

 we're going to look at a scenario4， which is not that complicated。

 It'll have some different complexities in scenario 3。

 But then next week we're going to culminate this whole ascending auction stuff by talking about。

 in some sense， the most general situation provably for which you can have these awesome ascending auctions。

 And so that's a setting called so-called substitutes evaluations。 And so just looking ahead。

 this is kind of the key property that that define substitutes valuation。

 So this is an important property。 basically at a snapshot of an ascending auction。

 you do your best thing。 And then that remains the best thing as the auction proceeds。

 that'll be the motivation for the generalization next week。Okay。So what do we know。

 So we have this simple option。 And the hard thing that we're trying to prove is that the outcome。

 assuming sincere bidding is actually the VC G outcome。 We've made some progress。

 We at least get the VCG allocation。 We at least get a surplus maximizing allocation。

We get some while're rising equilibrium。But we really want one in particular。

 the smallest of them all。 Okay， and that's going to be harder to prove。

 But that's what we're going to do next。Three question。All right。So limit two。And this， okay。

 solemma2。Here's what it says。So consider the outcome。Of the C auction。Okay， so final price is Q。

 final allocation M。And let PM star， I assuming sincere bidding and PM star be the VCG outcome。

Assuming truthful revelation。Okay， so this is what we want to be very close to。So the claim。

And number 2。Is that we're almost as low as the VCG prices。So P。

 we know is the smallest exact wall in equilibrium， we're going to terminate with something Q。

 which you know is an epsilon wall in equilibrium， which is barely bigger than the smallest possible exact orazan equilibrium。

That's limited。And this is a little tricky。 It's probably as hard as we're going have to work today。

 It's all elementary， but it's just， it's a little tricky。Okay。Good。So。Proof。

So most of the trickiness is just in the setup。 actually。 Okay， so we're going to have an inductive。

 It's going to be an inductive argument。 So give me a second just to sort of set up the appropriate induction。

So consider the first time。So intuitively， what we're going to say is in this CK auction。

You know's a red flag kind of goes off， so imagine we're just running this and imagine we knew what P was。

 the VCG prices were。And imagine we're sort of tracking the prices of all the goods。

And the current price of some good J。Start drifting upward further and further。

 and it starts being a little bit above the VCG price P。

 and then it starts being more and more above this VCG price P。Okay。

So I'm going to parameterize that。 So let's consider the first time。That we have a good。

 whose price is whose price is significantly above P， and it's about to get bumped up even further。

 Okay so some bidders about to on bid on this seemingly quite expensive good。

So consider the first time a bidder。Call it I1。Is about to bid。On a good J1。With the current price。

And again， this is not at the end of the auction。 This is somewhere in the middle。

 I'm going to use a different letter R Q is the prices of termination。 R is in the middle。

So it price Rj。And so that the current price is already sort of significantly bigger than P of J。

 the VCG price。 Okay， so let's just say epsilon times L L here is a parameter。 Okay。

 so think of it as like 10 or something。it's already drifted above the VCG price。

 it's about to go even further。O。So here's the key claim。So basically， what I'm going to do。

Is I'm going to give an inductive construction。 parameterized by L。 The induction will have L steps。

 And it'll be evident that that it'll be patently obvious that the maximum number of steps I could run this induction without a contradiction is for L being up to the number of goods that could possibly be traded。

 Okay and of course， you should think of min of N M is the number of bidders is the number of goods。

 That's just the edges in a maximum match。Alright， so claim。So suppose this is true。

 Suppose this is about to happen for some L。Then I claim for all positive integers K between1 and l inclusive。

I can show you。A nested set of bidders getting bigger and bigger。

 a nested set of goods getting bigger and bigger， satisfying a few properties。So we said UK。Okay。

 goods。I said Bk。Of because one bitters。This， is always going to be one more bitter than goods。

That satisfies the following properties。Why these properties？

Theseise properties were the sickest proof I could figure out。对。They't really have a better。

Better explanation for you。So。Okay， so for all bidders in this set UK， sorry。

 for all goods in the set UK， all of the prices of these goods are high。 Okay。

 so we're starting from the assumption that there's one good with a high price。 Sorry。

 this should be J 1。So there's one good J1 with a high price。 That's going to be the base case。

 And I'm going to show you bigger and bigger sets of goods， all of whom are overpriced， okay。

So I'm going to lose an epsilon each time I add a good。 but still。

 I'm going to give you these big sets of goods。 All of whose prices are too high。So。R of J。Is。

Greater than。So always remember P are the VCG prices， the smallest boarz in equilibrium。

PJ plus epsilon， and then again， I'm going to lose a little bit in every step of the induction。

So when K equal1 is going to be the base case and that's just sort of the same thing I was assuming every time I bump up Ka。

 I'm going to lose a little bit in how overpriced all of these goods are。So two。

For all bidders in the cave set。The most recent bid。By I。Its for a good。In UK。

So I'm going to show you K plus1 bidders， all of whom most recently bid for some good in these K goods of UK and I should be a little bit clear here。

So， I'm including。Yeah， so there's a little bit of time and coherence。 So the price are。

 So remember we're basically freezing the algorithm and auction when this bid I1 is about to bid on this good J1。

 Okay， So R， again， these these all only matter for the epsilon。 So it's not a big deal。

 just to be precise。 are the prices before we increment J1 by epsilon。

And when I say most recent bids， I'm including I1's bid on J1。Okay。

 so this bid set is sort of after I1 has been on J1， and the price R is before that's happened。

Allright， so3。All of the bidders。In Bk。Are matched。In the vcG outcome。

And the VCG allocation and star。Okay， so these are three properties。And I think。

 once I show you the base case， it'll be more clear。 There's one thing I want to observe right now。

So suppose I can do this。 Okay， so suppose I prove to you this claim。Then， in particular。Remember。

 Bk has K plus1 vis。And property 3 says all of these K plus1 bidders are matched in the VCG outcome M star。

Okay， well， K plus1 can't be bigger than the minimum of M and N。

 only the minimum of M and N goods can be traded。 Okay。

 so this says I'm only going be able to do this construction for L at most min of N N-1。So。

 if proved。Implies that L。Is strictly less than the minimum of M and N。And we'll be done。

So the one thing I want to have observed is I've reduced the proof of lema 2 to this inductive construction。

Okay， assuming this， then I can exhibit these nested families upsets for you。G。And from here。

 from here， it's pretty straightforward。 This， theres some nice cute ideas， but it's pretty。

 pretty straightforward once you have the inductive setup。All right。Then here's the construction。

So the base case， you can guess what it is。 But there's actually one， one thing we do have to prove。

So we're going to take。All right， yeah。So for the base case， we need one good。 So cake was one。

We need one good and we need two bidders。All right， so。What I， too。Be the current bidder。On J1。Okay。

 so remember where we are。This bitter I 1 is about to bid on J1， even though J1 is already expensive。

 So I claim that actually it must be displacing a bitter I2。 Okay。

 there must be someone who would previously bid on that some tentative winner。 I 2。 I 2 exists。

 Why does I 2 exist。Exactly， I heard from a bunch of people so in particular。

This assumption implies that the current price of the good J1 is positive。

 So someone bid on it at some point。 So someone's its tentative winner right now。Okay， so I2 exists。

All right， good。And so now what we're going to do， we're going to set the good set just to be equal to J1。

And by hypothesis， one holds。So no problem there。We set the current bid set to just be I1 i2。

I2's most recent bid was on J1。 I1 is about to bid on J1。 We're going to count that。

 So property two holds。But we do have to prove property 3。Okay， so I have to argue。 So remember。

 this isn't the VC G outcome M star。 this may seem a little weird， actually。

 right because we're arguing about the C， K auction， which is doing its thing。

 And now I'm sort of watching the trajectory of the C K auction and then arguing about what's up with those bidders in the VC G outcome。

 Okay， but I really need that as a reference point。So I need to prove that。 So proof of three。

All right， so why is this true， okay？All right， so。So first， I claim that。It's only one。

 that should be J1。Both of these bidders in question。 I wanted I， to， their value for the good J1。

 the ones that they bid on most recently。Well， it's got to be more than the VCG price of J1。

Why is that？ Well， okay， they just bid for it in the C K auction， right？

 So at the current price in the C K auction， which is R。

 that's how expensive is good is they wanted it。 They prefer to have that good to just dropping out of the auction。

 So their value have to be at least to the current C K price R。

 which by assumption is significantly bigger than the V C G price P。And what does that mean， Well。

 so now I want you to remember。That the VCG outcome is a wazian equilibrium。

 which means if you asked any bidder， is it happy with what it's matched to at the current prices。

 which in this case we're doing a thought experiment for P， it would say， yeah， I'm happy。

So in particular。If someone is unassigned， they're better be happy being unassigned。Okay。

 but given that I1 and I2's value is bigger than the price of J1。

 there's no way they'd be happy being unasigned in M star。 Okay。

 so they get strictly positive utility if they're matched to J1。

 So they have to get strictly positive utility in this outcomes。 So they have to be matched。

All right， that's the proof of base case。Any questions about that。

So now I got to show you how I can keep building up these sets of goods， the Us and bidders。

 the Bs by one。 And each time I build them up by one new sort of residence。

 I'm allowed to lose an epsilon in how expensive those goods are。 Okay。

 so that's the game now of which through the inductive hypothesis。Okay。So inductive step。

So we're given U K -1 and B K -1。Satisfying one through three。

So we're going to start by finding a good to add another item。

 so we want to supplement UK minus1 by one new good。Here here's what we're going do。

 We're going to say， well。We have these， the number of bidders。In the last set。

 outnumber the number of goods。Moreover， all of these bidders have to be matched to something in the VCG outcome。

Okay so from the last step for iteration K -1 when we have these K bidders， they're matched to K。

 obviously distinct goods in M star。And our special set of goods， U K -1 only has K -1 goods。

So there has to be something outside that set。So。Seeing it again。By the inductive hypothesis。

There is a bitter eye。In our bitters set。Amongst our cabitderters。And B minus-1。That's matched。

To a good outside， we're going to call it JK。Outside of UK -1。And。The VCG outcome and star。Okay。

That's just pigonal principle。Now。Let's try to reason about。Now， the other thing is。

 remember from property too。Last time we asked this bitter eye what it wanted。

It didn't want good J K， right There's as good it's sort of rightfully supposed to have in the VC G outcome。

And it avoided it。 said， no， no， no， I'd rather have this other good， which is in UK -1。

 So let's try to understand why， why did it do that。 Intuly， the reason is， is because， you know。

 whatever the good was in UK -1， it look cheap compared to good J K， right。

 But we also know that sort of everything in UK is really expensive using VC G prices as a reference point。

 So it must be that like the good it's supposed to have J K is even more expensive up up to an epsilon。

That's sort of the argument。But let me just make that precise。それ个1要开。Yeah， right。

 So so hopefully the labeling J K suggested that would be what we add to UK -1。

 And what I'm about to do is I'm， I'm going to argue that it's okay。

So I've already argued that at least it's a different good。 So at least they get a bigger set。

 So remember， we have this property here on UK right So for the induct step。

 I need to make sure that this is okay。 So in other words。

 I have to argue that Jk is expensive with respect to the VCG prices。 Intuly。

 the reason that's true is because if it wasn't expensive This bid。

 I would have bid on it and not bid on this other thing in UK -1。

And so that's all to get property one to go through for the inductive step。Allright。

 but just let me let me just quickly do this。 I mean， this。

 this is really where we use the kind of whatez equilibrium property of the of the C， K option。

 So let me just spell it out。Wherere to go oh yeah， so question。Why did I？Last bid on。嗯。

A good J and u k -1。Instead of on。JK。Okay。Well， so it must have been。That Jay looked better。

So I'm going to write this in terms of the prices R。U。Which I'll explain in a second。So'。

 there's actually two different things going on here。 So let me explain one at a time。

 So first of all， if I suppose I replace the R's with a different letter S。

 which were the prices at the time that this bitter I， All right， So remember。

 bitter I's most recent bid。With furthest good J。Okay， so we have this bitter eye at some point。

 most recently in the auction， it bid for some good by the inductive hypothesis。

 We know that good is in UK -1。 I'm calling that good J。 Okay。

 so J is the most recent thing that I professed interest in。Right。So at the prices at that time。

 whatever they were， the prices were S， then by definition。

 J was the favorite good of I at those prices S up to an epsilon。Okay。

 because we just asked what's your favorite good。 And it said J。 Now， since then。

 more stuff has happened， we don't have those prices asked what these other prices are。

 But just like in Lemma 1， this decision is only better than ever。 Okay。

 so the price for this good J has not gone up and the price for this other good J K may have gone up。

 So again， this is only more true with respect to the prices are。Okay。

 so this is the combination of the fact that I bid for J plus the fact that we have sending prices and that prices don't ascend when you've got a good。

Okay， so that's true。On the other hand。At prices P。Okay， so in the matching M star。

 the VCG outcome M star。I is matched to J K。 And because this is what was in nuclear with the price is P。

 I prefers J K to anything else in particular to this good J。Okay， so， but。Since PM star。

 Laazian equilibrium。We get the reverse inequality if I switch the R's to P's。again。

 this is just because people bid on their most preferred goods up to an epsilon。

 And this is by the Wazian equilibrium condition applied to the VCG outcome。So how is this possible。

 How is it possible that when we switch the prices from P to R。

 I relative preference between J and J K flips。Well。

 it has to be that if I think of going from let's say which one's higher。

 so the r's are the higher ones， so it has to be that if I switch from P to R。

 the why would I switch from Jk to J， it has to be that the price on Jk goes up by more then the amount that the price went up on J so price is P。

 I like Jk， I increase all the prices to R， why does it flip because relatively speaking the increase in price on Jk is more than that on J up to the epsilon。

If you like， you can just add these two inequalities， cancel all the Vs and rearrange。

 you'll get exactly the same thing， you prefer an algebraic manipulation。So all this stuff implies。

That。ButAgain， the extent to which。JK is marked up。Over the reference point of the VCG prices。

So again， switching from P to R， your favorite switches from J K to J。

 So the increase on JK has to be bigger。Then the increase on J again， up to an epsilon。Okay。Now。

 J was in this set of goods we inherited from the last iteration。 UK -1。

 The inductive hypothesis says those are all expensive。 Okay， everything in UK -1 in particular。

 J is expensive。 So this is just saying J K is as expensive up to an epsilon。So inductive hypothesis。

L minus K minus-1 plus1。Also known as epsilon L minus K。That's again。

 the whole point of this was just saying we can add this good J K to our old good set。 Okay。

 and again， what was the problem， Why might that screw us up， Well。

 we have to preserve this property that all goods in our special goods set are expensive。

 And that's what we just proved。So。Setting UK equal to the last set of goods。Plus。

 this new giver just identified JK。Satisfies one。So that's one of the main two things I had to show you。

I added a new good to the good set。 now I have to add a new bidder to the bid set。

 and it's the main other step of the the inductive part。Okay。

 so I showed you where I get my K good from。 Where do I get my K plus first bidder from to which do the inductive step。

All right， well。So， JK。Its price is bigger， right， What do we just prove。

 We just prove that JK's price is bigger than that at the VCG prices。 So in particular。

 it's positive。This is good that we just added。 so I should say， all right。 So， so what， okay。

 So adding a new good， we had to make sure it was expensive。 adding a new bidder。

 What do we worried about， Okay， what is it， what do we have to preserve。

 We have to make sure that when we add a new bidder。

 it was most recently interested in some good in our set UK。

 And then we also have to make sure that it's matched in the VC G outcome。

 So this is what we have to keep keep our eye。Okay， so。But if the price。Of this good。

 we just added J K is positive。 again， as we discussed。

 there must be some current tenet of winner on it。 Okay， that means people were bidding on it。

 So if someone most recently bid on it。And there exists a bitter。IK plus1。

 the most recent bidder on J。Sorry， the most recent bid on JK。And now importantly。

 this is not one of my old bidders。Okay， so this is what I want to add。

 I want to augment the bidderset by this。And bitter I capable plus1 is not a member of B， K -1。

You see why。And I was allowed to keep track of。我。経験い。Good， and。And which property are we using here？

Property2。Okay， so we're using the fact that the K bidders we had before。

All of their most recent bids went just to the K -1 goods in U K -1。 Jk is this new good。

 So none of our old bidders most recently bid for Jk has to be somebody else。

 I'm calling that I K plus1。Excellent。And so this is who we're going to add。And。

Currently assigned to it。And so。That means we're allowed to define。

 at least for the perspective of property too。We can define BK to be Bk minus1 plus this new person。

K plus one。Now there is this final property three。Wch is that this new person we just added has to be matched in the V C G allocation M star。

 The proof of three is exactly the same as the proof was in the base case。 Okay， so basically。

 it's bidding on this good at a price which is even higher than at the VCG price。

 So that means with respect to the VCG prices， there's certainly something that it's strictly wants。

 So it can't be unmatched。 It has to be matched to something。 So same as the base case。Okay。

So that proves this inductive claim that if something is too high by L multiples of epsilon。

 I can construct these sets。 I can keep constructing bigger， bigger betters。

 all of whom are matched in the V G outcomes。 Theyre only be the minimum and M of them。

 So that's the most over。Pricing， we're ever going to do a result by the C K algorithm。

 So as epsilon goes to 0， we really are getting the minimum VCG prices。

 or at least we're below the minimum VCG prices。All right。Q we。Questions。Like。

 probably that should be the hardest thing for the day。So learn my lesson from last week。

 I'm trying to put the hardest things kind of more in the early part than at the end。

 So always slow some energy。Okay。So that's really cool。So it really doesn't， frankly， to me。

 intuitively， it doesn't feel like the auction。 It does feel like it's explicitly engineered to term a Owa equilibrium。

But it doesn't feel like there was intentional work to go into being so parsimonious about it。

 to actually， you know， convert into the minimal ones。 Yes， you got that grant that it starts at 0。

 So it starts underneath all of the Wawau equilibrium。

 And somehow that's enough to make sure you don't ever kind of shoot into the interior of the set of Waazu equilibrium。

 which is really cool， I think。Al right， so for the incentives part， which I'm about to move on to。

We need actually a sort of two sided bound。Because strictly speaking， so what do we prove。

 We proved that any exact while rising in equilibrium。Can only be higher than the VCG prices。Okay。

 but the C， K auction isn't actually computing。 It's not trim with an exact or riseiz equilibrium。

 It's term with an epsilon， approximate one。so we haven't strictly speaking proved that it couldn't be way lower than VCG prices。

 and as we'll see， that would actually be a problem for incentives。 but you know intuitively。

 you wouldn't think so and it's not。 So I'm going to state this lemma。

 is the proof of this lemma is very similar to the proof we just did。

 and I've sort of chopped it into morsel size pieces on the exercise set。

 you can go through it there。 It's very similar flavor。So here's the statement。

The statement is that any epsilon robot an equilibrium。

 whether the one computed by this auction or not， can't be significantly lower than the V G payments。

 so just throwing in in epsilon doesn't really change the fact that you can't be smaller than the V G payments。

So， a QM。Vene arriveiz in equilibrium。And with PM star。E the VCG outcome。Then。there should be mices。

You can be a little bit less than the VCG prices， but not by much。Just by the same amount。

Epsilon times is potentially the number of bidder item matches。 Okay。

 the minimum of the number of players， the number of bidders。So we will use this lemma， Okay。

 so we'll see。 we'll use this when we talk about incentives。 but the proof I'm not going to do here。

There's a similar inductive buildup that sets proof of this limitma as well。Alright。

 so let's take a step back。 Let's take stock of what we've got and what we want。

And what's the gap in between them。So upshot。Notice all this analysis has been done。

 assuming that bidders bid sincerely。 When we ask them what their favorite good is at the current prices。

 they tell us honestly。I this has all just been， in effect。

 a thought experiment kind of crossing our fingers。 If people behave this way， then what happens。

And so now sort of the most important thing is to understand， is there any。

Justification in that assumption。 Do we， Is there any reason for bidders to bid sincerely。And。Right。

 so but。Is sincere bidding。And X post Nash equilibrium。Again， up to some small error。ほ not。

So one thing maybe， so one thing we're just thinking about a little bit。

 there's an exercise on this also， you know， which is merely by virtue of the fact of sincere bidding leading。

To the VCG outcome， maybe that's enough。So maybe just simulating the VCG outcome in an indirect auction is a sufficient condition。

For having a expos and setting compatible implementation。It's a little bit of a subtle question。

 It kind of depends on the context a little bit。 But that's just something to keep in mind。

 I've been trying to argue。 I haven't given you all of the rigorous backing yet。

 but I've been trying to sort of direct you into thinking that it's a necessary condition。

 right So if we want an expos to compatible implementationation thats surplus maximizing I've basically told you without a fullproof yet that we have to at least do this now。

 now that we've actually succeeded for a problem we care about the question is， is it enough。Okay。

So what I want to do next is kind of help you kind of understand。

That question a little bit more and what is involved。

Safe for the scenario 3 in passing from what we've proved so far and what we want。

So let's start with just kind of what you get for free from proving that sincere bidding gives you a VCG outcome。

So， let me define。So recall， we discussed these indirective limitations last week。

 So just to remind you， so when you have an iterative a， there's just no notion shade of an action。

Which is what you do。Like how you bid at each round as a function of everything you know and everything you've seen so far。

 Then there's the notion of a strategy。 And remember。

 strategy is a function from your private information， your valuation to an action。

 So it's a function of what you want， how do you behave。 So， for example。

 sincere bidding if you think about it， It's really a function。 It's really a strategy。

 It's not an action。Because your answer to a query depends on your value。 so knowing your value。

 you know how to act。So what I'm not going to do is I'm going to define a subset of strategies。

So a particular strategy of function from values to actions， I will call consistent。No， excuse me。

This is actually， is an action。So consistent action。Is defined as。The result of sincere bidding。

With respect to。Some。Private valuation。Okay， so in other words， think about this。

 Suppose you have some player and you have no idea what they want。

 You have no idea what their valuation is。 But you just observe how they act。

 how they answer these queries。 then you can answer the question， Is this a consistent action or not。

 I can say yes， because I can envision a evaluation with respect to which this would be the outcome of sincere bidding。

 I can't just watching the action。 There's no way I can I don't have enough information to say。

 is this person bidding sincerely or not， because I don't know their evaluation。

 I only see in effect the range of their function。 I don't see the domain。

 Okay So an action is defined as a consistent one if it could arise from sincere bidding。

 if there's evaluation for which this is how the player would act。All right。So now。

 here's kind of the。Here's what you get for free from simulating the VCG outcome。

So it would A be an iterative auction。With this property。

Such that sincere bidding gives you the VCG outcome。So if other players， here's the claim。

 if other players bid sincerely。I suppose your player aye？And you know。

 other players are bidding sincerely。You could bid sincerely。

Or if you get a higher payoff from some other action， you'd do that as well。Okay。

So what do you think the rest of this proposition is。

 I want to say it's never in your interest to deviate from sincere bidding。

And so I'm gonna make a weaker statement。 It's never in your best interest to deviate to a particular in a particular way from sincere bidding。

So the claim is it's never in your interest to deviate to a consistent action。So again。

 when you're formulating how you might act at an auction。You have a bunch of options。 Right。

 So one thing you could do is you could just be honest。That's the easiest thing。

 Here's one form of deviation。Well， let me actually upfront pretend。

 like I have a different valuation than I do。And then I'm just going to act consistently with this。

Incorrect valuation with this false valuation。Okay that's another way I could act。

 which is not truthful， it's a deviation。A third thing I could do is just something crazy。

 And we saw an example last week。 Remember we had parallel English auction。

 I wanted to convince you that you didn't have a dominant strategy equilibrium。

 And the way I convinced you is I had the second bitter act in this crazy way。

 The second bidder monitored what the first bidder did in the first iteration and then conditioned on that and then behaved in totally different ways after that。

So that's a still third kind of action， which is not a consistent action。

 There is no valuation with respect to which sincere bidding would lead to that crazy second bidder from last week。

Okay， so what you get for free here is。If sincere bidding leads to a VG outcome。

 then this sort of first， this intermediate deviation is never helpful。

 It's never helpful to just say， well， let me pretend like I have this other valuation and then bid sincerely with respect to it。

 That's not going to do you any good。So if other bidders bid sincerely。Can't gain。From any。

Consistent action。So did you see why you get that for free？When an auction has this property？

And want to suggest。It's kind of a。One sentence， English reason。I mean， in effect。Right。

 so what do we know about V C G， We know V CG is dominant strategy and compatibleible， right。

 So we know that， you know， in the direct revelation version。

 at least if you declared an incorrect deviation， it wouldn't help you。Okay， and so the point is， if。

If with sincere bidding， this auction A is simulating the V C G outcome。Okay。

 so then if you bid truthfully， it just simulates the truthful VC G outcome。

 If you just bid with some other consistent action。

 it's exactly as if you bid the corresponding valuation V prime to the VCG mechanism。

 which doesn't help。Okay， so in other words， when you have an auction with this property that it simulates the V C G outcome with sincere bidding。

 it introduces a very strong bijection。Between， on the one hand。

 when everybody plays a consistent action in the indirect in the iterative a and then the possible strategy profiles。

 direct revelation profiles in the VCG mechanism。 Okay。

 there's a one to one correspondence that preserves bidders utilities。

So that means deviations amongst consistent actions， correspondent deviations in V CG。

 And those never help。嗯。So let me just write a little bit。About that。Very。Okay， so reason。

So consistent actions in A。And so this is utility preserving。Strategy profiles。

 or maybe I'll even just say bid profiles。In VCG。92一。We're just inheriting。

This property from the fact that VCG is dominant strategy center compatible。Okay。

So that's what we get for free。 Now， this is not the same thing as saying this is weaker than saying the auction A is X post instead instead compatible。

 It's weaker than saying sincere bidding is an X post Nash equilibrium because it' going to be an X post Nash equilibrium that says。

 look， I'm bitter eye。And it should be the case that if I know。First of all。

 that other playerss are bidding sincerely。And second of all， again。

 for the purpose of this thought experiment， I even think of that， I know their valuation。

It should be that my best response among any action I could do， consistent or inconsistent。

Should be to just answer all the queries truthfully。Okay。

 so what you have to prove is that even if a bidder。

 So you assume all the other bidders bids sincerely is to prove that even if this bidder bids in a crazy way andconsistent with evaluation。

 even then their payoff doesn't go up。Okay。So theres going be an exercise saying that actually there are if you want a pathological action where you can separate these two things。

 you can。Okay， so there are options A that have this property， and therefore。

 consistent actions don't help， but inconsistent actions could help。 That's in principle possible。

And that means that when it's not possible， you have to prove something。

 There has to be something special about the auction that lets you argue not just about consistent actions。

 but more generally about all actions。And that's what I still owe you for the C， K auction。

 So that's the last part of the first lecture today。 Okay， so it's all that clear。

So that's the issue。Good。So。K。Right so last theorem。For the first lecture。

Is that the C auction happily？Is。More generally epic。And again， up to。You know， up to small error。

Again just to be clear。This property you get for free is weaker than EC。

So E is not automatic just because you simulate the V G outcome with sincere bidding。

 So it requires a proof。All right。So fix the bidder。

 who's contemplating its arbitrarily crazy actions。Fix the evaluation profile。

And assume others bid sincerely。RightThat's the one thing we get to assume。

 So the other players are not doing crazy actions。 And we want to prove that I has no incentive to do a crazy action。

 either。And so again， what we know is that consistent。Actions don't help。

So the plan is to basically prove that for any deviation which is not necessarily a consistent action。

 I can exhibit to you another deviation， which is a consistent action， which is just as effective。

I guess I'm going to sort of reduce the inconsistent case to the consistent case。So plan。

Inconsistent ones no better。All right。So consider an arbitrary deviation by I。And let's just sort of。

Notice a couple trivial things。So first of all。The auction is going to terminate。

 I can't really do anything about that。All the other bidders will drop out。

Because they're bidding sincerely once the price gets sufficiently high。And， you know。

 from my perspective， there's no way this was helpful unless it gets some good。other。

 has zero utility。 So let's suppose it deviates in some way。 And at the end of the day， it gets。

A good J。We're following this specify。When responding to specify crazy strategy。Exactly， so。

 and now what I want to prove is that， you know， it did whatever it did。

For it to be a conceivably interesting deviation at termination， it got some good J。

But the intuition is， well， surely there's much more just direct ways of getting this good J。Like。

 why not just bid a billion if， that's what you wanted at the end of the day from this auction。

 Whyna just bid a billion for good J and nothing for anything else。

 Like you're gonna get J at the end of the day。Now， it still requires a proof。

I don't see why this is totally trivial， it does work， it is true。So I's actual valuation is V sub I。

 V prime is going to be， is going to represent some consistent deviation it could have done。 Okay。

 so I'm going define V prime。In the obvious way， So if for good J， it's just sufficiently large。

 plus infinity， let's call it。And for any other good， it's going to be zero。

So one deviation would be， I pretend my valuation is v prime， and then I bid sincerely。

 And that would be a consistent deviation。 And these are the ones that we know don't help。

So if I can show that the inconsistent one is no better than doing this， we're done。Okay。So， claim。

可呀。And so， then。Yeah。So let QM be the final outcome with this arbitrarily crazy deviation。Okay。

 so this is the outcome in which I gets J。 in general， there's some matching M。

 and there's some final price vector Q。So here's the claim。

Which is that if the true valuations really were v prime for I and everybody else with a standard deviation V minus I。

Then the outcome of the C， K a would be a well we'reaz an equilibrium or an epsilon one with respect to this artificial evaluation profile I just defined。

So， QM。Theres an epsilon will was an equilibrium。For v prime I V minus I。So just to be clear， I mean。

 the reason， So if you see some trivial reason how to finish the rest of the proof。

 I'd love to know it。 Okay， as far as I can see， the issue is that you somehow have to say that crazy actions can't let you get a good J at a lower price。

Then you would have gotten it had you just bid consistently with V prime。

I don't think it's obvious that you can't manipulate the price downward in this auction with inconsistent actions。

 you can't。 I'm about to prove that to you。 but I don't see obvious reason。

Why you can't force the price downward。 It seems like you have to use some of the theory we've developed。

O。So why is this true anyway， So in while we're in equilibriumlib。

 we have a lot of control over their prices and how they relate to other prices。

 So that's the route we're going to use。So was the claim clear？So again， V prime is fictitious。 Okay。

 I looked at eyes deviation。 Then I invented V prime。 This is These are other people's valuations。

 And then this is a world defined state。All right， so。So it's certainly still true that unsold goods。

Have price zero。There's nothing I can do about that。 right， So by the rules of the auction， you know。

 if I does something crazy and it bids for some good。

 it has that good forever because there's nothing you can do about it。So this property。

 the C auction persists。It's clear that I。Gets its fave good。

In the hypothetical world where it had the valuation V prime I。は。And then for the other bidders。

 it's the same reason as ever。 It's just the termination condition of the C， K auction。 right。

 So if there was some bidder， I prime。That was getting a good that was not its epsilon favorite。

So again， it's the same reason， right， So think about the last time they bid， right。

 It was their favorite。 And then again， prices still only ascend for everybody else。 Again。

 there's nothing that this deviator eye can do about that。So let me just write other bidders。Epsilon。

 happy。For usual reasons。O。So that's just a quick claim。So whatever eye does。It can't。

Prevent the fact of this auction terminating with this well rise equilibrium with respect to some valuation profile。

 Okay， where V prime is just meant to sort of。Indicate what it seems like I wanted by its deviation。

Okay。So again， what we want to argue is that these prices can't be too low。

 What we're worried about I doing is somehow acquiring this Gujat at a super low price。

So why can't that happen？ Well， it can't prevent the fact that you go to a walls in equilibrium。

 And remember there's a limitma 3。 This was the one I skipped。

 limitma 2 that we worked hard to prove says that while water is in equilibrium outputted by the C auction can't drift much of a VCG prices。

 And we knew we needed that。 But remember we also had this complementary limit 3。

 which is that by the way， with an epsilon water in equilibrium。

 you're not going to be really lower at all than the VCG prices。 So we're going to use that here。

So we know it terminates the laws in equilibrium。 Le 3 is what tells us that those can't be very low just by virtue of being a was zone in equilibrium。

Okay， so Bima3。The outcome of the C K auction。Is at least， let me write it as P prime。

 So here I'm defining。P primed to be VCG payments。For v prime I， v minus I。Minus epsilon times。

The number of trades that might happen。So again， these equilibriumia Q cannot be too low with respect to this VC G price vector。

So。Let's now do the full comparison。 So this will wrap up proof。

 the full comparison of this deviator's utility。With this crazy action resulting in this polar rise equilibrium Q comma M versus if it adjusts bids sincerely。

So utility of I in QM。Well， so the payments are almost the same as with respect to the VCG outcome with its valuation profile。

So utility of I。In VCG。With the with the bid profile， V prime I V minus I。So again。

 what this is saying is that basically， you know this is really what we want。

 says this crazy action and this indirect doctrine isn't really doing much more than misreport in the VCG mechanism。

 which we know can't really help。So this is just by VCG being DC6。Utility of eye。And VCG。

With the honest valuation profile。And then again， here， now。

 it's not the case that the C K Auction actually exactly simulates this outcome。

 but it simulates this outcome up to an epsilon times the usual factor。So u till of I。

Bidding sincerely。In C。Im sorry， there should be a。Plus， blah， blah， blah。

And then this gets carried down here。And down here becomes a。Gets doubled， yeah。Sure。

And so that's that in the end， we just argued directly whatever action you do， it results in some QM。

 which is some rise in equilibrium。 And it can only save you some vanishly small additive factor over what bidding sincerely did。

So that shows that you get robustness not just against these consistent deviations。

 but against arbitrary ones。 So that gives us what we wanted an awesome ascending option for unit demand bidders。

😊。