# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p18 -18-(Lecture 17b_  Beyond Smoothness and XOS Valuations).zh_en -BV1fNVNzhEBg_p18-

So I want to do one other thing in this first lecture。Which is to go。To consider the you most。

 in some ways， the most general scenario where any welfare guarantees are known for any sort of。

You know， non brute force procedure。And it's going to。

Illustrate a nice trick for how you can prove price of energyarch bounds for Bayes National Libria without going through the smoothness regime。

 So it's gonna be a more direct argument， which seems necessary for a result of this generality。

So let me tell you the setting。I think we're at scenario9， but to be honest of sort of lost track。So。

 this is going to be。The， the most general one we've seen thus far。

Where bidders have what are called sub additive valuations。

Which just means that pairs if you look at two bundles。

 then my value for their union is at most as much as my value for each of them separately。

 get the sum of my value for each of them separately。So you should be wondering how this relates to。

All of the other classes evaluations that we've seen， and the answer is， you know。

 for the stuff we've been focusing on， this is strictly more general than anything we've studied thus far。

So in particular。It's not hard to prove。 I'll leave this as an optional exercise that this is strictly more general than X。

 O S valuations。 So X， O S valuations， that was this sort of perhaps weird class。

 This maximum of added evaluations。 But the key point was X。

 O S was strictly more general than sub modular。 And remember。

 sub modular was already giving us sort of you know， fits for multiple weeks， okay。

So the picture you want to have in mind is。Gs substitutes that' sort of the frontier of tractability。

 as we've discussed。Of exact tractability， at least。

Then we went to submodular and we studied that for a long time。

 and now in the context of these simple auction formats。

 it turned out there was the important property of submodular evaluations for simultaneous second B auctions。

 at least， was that there was a special case of an XOOS valuation maximum of add。

And then sub additive is out here。Okay。And all of these are strict。So for example。

 showing containment is quite easy， so suppose you have an XOOS evaluation， why is it sub additive？

Well， okay， suppose your evaluation was actually additive。Right， and think about S and T disjoint。

 That's the interesting case here。 This holds with the quality， right。

 for an added evaluation by definition。 So suppose your X， O S。Well。

 just pick the added evaluation that's exact on this particular bundle。

And that's going to give you some lower bound on the valuations over here。 But then re optimizing。

 picking the new additive valuation to maximize this and to maximize this will give you something only higher。

So that's kind of the two line proof of why XOOS has to be subbbatitive。

And it's not hard to find a strict separation either。

So what else should you know about savand evaluations。

 there's no known sort of constant factor de mechanisms or anything like that for saatd evaluations。

The good news is is if you just look at the algorithmic problem of welfare maximization。

 we do know how to do that well in polynomial time。 Well。

 meaning there's a two approximation algorithm。 It's a ingenious approximation algorithm it's not easy and it's from。

 you know， it's a little less than 10 years old。 it's relatively recent， but we do know how to do it。

 assuming demand oracles， okay。😊，And the way you should sort of think about savaative evaluations。

 I mean， it's basically。You know， roughly the frontier at which we know how to do constant factor approximations。

 even if we don't care about incentives at all。 So in some sense。

 it's the limit where we might hope to have constant factor guarantees for simple auctions。

And as I'll show you， you can get that。That'll be the point of the rest of the election。Okay。

All right， so good。 So you have to work hard to develop a polymer time algorithm to get constant factor approximation。

 What happens if you just use some simple option like simultaneous first or second price options。

' that's the question。So， fact。Is that smoothness doesn't seem to get you a constant factor。

At least to the extent that we understand the limits of smoothness。

So it seems to get stuck at giving you a price of anarch like one over log M。

 where M is the number of items。And the reason that you pick up a log M going。 So remember。

 we do know how to get a constant factor here。 That was the point of the last couple of weeks。

And the reason you pick up a login going from XOOS to sub additive。Is the X。

 O S valuations had this really nice property that， So remember。

 it was always how do you define the B stars。 How do you define the deviations。

 And the way we did it is we said， well， let's think about what items we rightfully are supposed to get in the optimal solution。

 And then we're gonna go all out for them。 And in our analysis， we really use two properties。

 we used that there was this added evaluation。 So this bid that was exactly representing our valuation on this particular set and was only smaller on every other set。

 So only underestimated。 So didn't overbid on other subsets。

 And if you go back and look at the analysis， I don't expect you to remember of hand。

 but we really needed both of those properties in verifying the smoothest inequalities。

 And those bids just don't exist for some added evaluations。 to target a set。

And with an added evaluations or with bids in a simultaneous single item a。

 if you want to bid exactly your value on a particular subset。

 you might be forced to overbid on certain subsets by a log factor。

And that logarithic factor shows up in the analysis， it can cause you problems。

So you can get a one over log price of anarchy， but it's not known how to do better using these extension theorems。

So instead what we're going to do is're going to use a direct argument。

And I'll tell you what I mean by that。And， you know， it still sort of has the flavor of smoothness。

 but it isn't。 And but the good news is the bottom line looks really good。😊，Okay。

 for simultaneous first price auctions。The Bays Nash price of anarchy。

 and this has to be product distributions。 remember we know even for unit demand valuations。

 the correlated price of anarch key is terrible。But for product distributions， we get that this is。

Boed below by a half。And so again， this is the best we know how to do with arbitrarily sophisticated polyel time approximation algorithms。

 So it's competitive with approximation algorithms， sort of apples versus oranges comparison。

 But still， that's something we're very happy with at this level of generality。😊。

And then for second price auctions， it degrades down to a fourth， but it's still a constant factor。

Okay。So I'm going to show you this proof。 I'm going to show you this result。

 This is similar arguments， a few extra details。 Okay， so this is going to be the plan。All right。

What does it mean to go beyond spoonoonness to do a direct argument？

So here's the flexibility we're going to allow ourselves in the proof that will allow us to get these better bounds。

嗯。So idea。We're still going to be defining these hypothetical deviations， B star。But in smoothness。

 in smoothness arguments， the key point is that they're independent of whatever bid profile B。

 we're eventually going to invoke it in。 Okay， so what the quantifiers were for every valuation profile。

 there exist B stars so that for every B。Okay， so the difference now is we're going to allow our B stars to depend on that B。

So， I mean， if we go all the way back to our very initial price of energyarch analyses。

 this is sort of like saying， well， look， this game might have multiple equilibrium。

 All I want to do is prove every single one is good。

 So why can't I just for each equilibriumria separately。

 you know pick my own favorite hypothetical deviations that prove that this particular equilibrium is good。

So that's enough to prove that all equilibrium are near optimal。

 It's just never how we've been doing it。 We've always been we've always been exhibiting these deviations without first looking at what equilibrium we're talking about。

 we have sort of a uniform choice in all of our previous analyses。

 a uniform choice of the deviations B star。 that we use those for every single equilibrium。

 And we're not going do that。 And now we're going look at the equilibrium and say， oh。

 for this equilibrium， I'm going deviate this way to show that this one is good。

 for this other equilibrium。 I'm going to deviate this other way to show that this one is good。

 And I show a generic way to do that that handles every single equilibrium。 And that's good enough。

 If all we care about is prove that all equilibrium are near optimal。 This is fine。

 It's not a smoothness proof， there aren't going to be any extension theorems。

 but the proofs won't look that different than the extension theorems either。

 so that's what's different。😊，so in equilibrium specific deviations rather than equilibrium agnostic deviations。

Okay。2。So let me show you the key nugget of this analysis， which is really really quite cute。So。

 Q Emmama。And this is also where we really use the sub addative assumption。

So remember we're talking about simultaneous first price auction。So fix a bit or I。

It's savanative evaluation VI。And here's the important part， fix a distribution。Di。

On the bids by the other players。 So there's N items。 Theres， sorry， there's M items。

 There's n players， B minus I。 remember this is。 This is n -1 different M vectors。 Okay。

 so these are distributions and what other players are doing。 Now。

 in the proof and the eventual proof， This distribution is just going to be what other players actions at an equilibrium。

 Okay， so we're look at some bayastic equilibrium。 Other players will be bidding in some random way。

 And that'll induce some distribution。 that's how we're gonna be a client of this。 But for now。

 just some distribution on other players behavior。Fixes set S。And so， now。There exists a B star I。

 and so notice， right I've seen this distribution again equate this distribution D with some base national equilibrium。

I've seen the distribution first， and only now am I showing you the deviations B star。Okay。

 so that's the sense in which this is a direct argument rather than a smoothness proof。

So then there exists to be star。This is going to be a function。

 both of this distribution D and the set S that you should think of S is what we're targeting。

 So that's going to be like a bundle and some optimal allocation。And then， okay。

 so what's going be true， what's going to be true is that we can lower bound our expected utility。

With respect to this distribution。Okay。So remember a B star I， this is not random。

 this is some fixed bid that we're doing as player I， this is something random。

 we're looking at our expected utility。And we claim that the expected utility is going to be at least half of our value for the set that we're targeting。

Minus an error term。Okay。So this is just the expected some of the highest bids on this S that we're targeting。

Does the Lema statement clear。Like I said， the proof is a acute symmetry argument。O。Good。

 and then basically， you know， looking ahead， when we prove the price of anarchy bound。

 we'll just use this instead of a smoothness condition。 Okay。

 this will sort of substitute for a smoothness condition。Alright， so enough to show， all right。

 So we're going to use the probabilistic method。 We're supposed to exhibit some fixed B star I that meets this inequality。

 I'm going to just pick B star I at random from a certain distribution。 And in expectation。

 this inequality will be satisfied。 So by averaging。

 there exists some choice of B star I that satisfies inequality。So， enough to show。

Aran and beast our eye。Works and expectation。So here's how I'm going to randomly choose this deviation B star I so that this holds an expectation。

So I'm going to basically mimic the other players。 Or rather I'm gonna mimic the maximum bit of the other players。

 Okay， so these n -1 players。 So on any item， there's some distribution over their bids。

 There's some distribution of the highest bid。Okay so I'm just going to set my bid。

 I'm going to have it be distributed on a given item in the same distribution as the highest bid by some other player。

So， specifically。Choose sample。 Okay， so there are echoes of the doppelganger trick here。

 although I'm not actually sampling evaluation。 I'm just sampling an action。 So remember。

 D is a distribution of a bid vectors。 So I sample， you know。

 a typical bid vector that the other players are going to。Go to play。And then I sit。

My deviating bit as follows。So， right， I'm targeting this set S。

 So we're going to be willing to bid non trivially on items of S。 And what do we bid。

 We just bid the。Maximum bid， according to a minus I。So the claim is this works。

So is the deviation clear？So again， what I'm told is I'm told the distribution over other players' actions。

 again， think of that as being in some base na equilibrium。

 I'm told a set of items that I'm targeting。 Think of that as being some bundle in an optimal allocation when I'm gonna to bid  zero outside of that。

 How do I bid on the items in S。 I just say， well， you know。

 let me sample what other players might be doing。 I'm going to look at the highest bid by some other player。

 and I'm actually going to set that to be my bid。 So I bid as if I'm a highest bidding player。

 highest other bidding player on an item。Okay。Okay， so。And this works。

 So in what sense does this work。So let's lower bound our utility。

 the way I'm going to lower bound our expected utility。

Where the expectation is now both over our random choice of B star I and over the random instantiation of B minus I。

 first， I'm going to say that our you know， our expected payment。Is it most to this term？

And that our expected welfare is at least this term。

And that's good enough to lower down my expected utility， expected payment at most that。

 expected welfare or at least that。Alright， so with the expected payment， if you can just。

Keep all this in your head as straightforward。So how much is bitter I going to pay when it picks B or I random this way。

 Well， who knows， because we don't really know what's going to win， what's going to lose。

 But it's not going to pay more than it than it bids。RightIf it wins everything it bids on。

 it'll pay exactly what it bids。 And otherwise， it'll pay less。

So the expected payment is at most the expected bids。And so what's my expected bid on a given item J。

 Well， it's distributed exactly the same as this， just by definition。O。So， by definition。Right。

 so this is just literally。How we set our B star。Ija。Okay， for each item that we're bidding on。 and。

 of course， you know， I'm calling it a minus I here。 I'm calling it B minus I here。 But who cares。

 right， They're drawn from the same distribution。 So this number and this number are the same。Okay。

 so our expected payment is certainly no more than this。So how about the expected welfare。

So now we're going to use the symmetry again。So by symmetry of B minus I and a minus I。

So this is nice。So for a given subset of S， remember S。 So there's some big set of items U。

 And then there's some set of items that we're targeting S。 We're going to win some of them。

Where we're the high bidder， and we're going to lose some of them where we're not the high bidder。

So consider the probability that we win。Exactly the set A。Versus we went exactly。The set of items。

 S minus a。So what can you say about those two probabilities？Any guesses？Whatll be the coolest thing。

All right， so these are equal。Okay。So why are they equal， Well， what happens， Okay， Okay， so what's。

 I guess I should say， what's the probability over。

 the probability here is over both a minus I and B minus I。I should have specified that。 Okay。

 so other players are bidding randomly。 And so are we。Okay。Alright。

 so we're gonna we win the items where we're the highest bidder and we lose the items where we're not the highest bidder。

 Okay， so if we win the set A， then it means the following property。 It means for the items。

 J that are in a。It means the maximum entry， so the maximum bid on J in a minus I our bid。

 so what are we bidding we're bidding the maximum entry in a minus I on the item J。

So if our entry is bigger than the biggest of the entries on J and B minus I， then we win。

 otherwise we lose。Right。So if we win the items in a。

 that means that a was that means in the realization of a minus I and B minus I。

 A were exactly the items J where the highest entry in a minus I was bigger than the highest entry in B minus I。

A minus I and b minus I have exactly the same distribution。

So it's just as equally likely that what we're calling b minus I could have been our A minus I and simultaneously what was our A minus I could have been the actual b minus I。

 that is it's equally likely that the other bidders。

 the highest other bidder would be what we just bid and what we just did was the highest other bidder。

And if we swap them， then we're just winning S minus n of a。Okay。So for each pairing of a minus A。

 B minus A， just swapping which way it goes， you exchange between winning A and S minus a for some A。

 so integrating over everything， you still get this。All right。So that's good。So that uses just。

 you know， our clever choice of this randomized bid where it doesn't use sabbatic。

So now let's use some addivity to say。 So remember what we're trying to do So we've already upper bounded our payment and expectation。

 Now we want to lower bound our welfare and expectation。So I is expected welfare。Okay。Is well。

Let's look at all the。Saets it might win， a。Times it value for a。Now。

 what I want to do is in this sum， which is ranging over all subsets of A。

 I just want to pair up A and S minus a。Okay， because I know they have the same probability。

 so we just argued， right？So， you know， just。In S， let's have some distinguished element one。Okay。

So choose an item。1 in S。 This is just to break symmetry。 This is just so that for any A。

 I count exactly one of a or S minus a exactly once。 And I count the other one0 times。 Okay。

 so I'm just pairing up A's in their complements。Okay， so， right， so let's just some。

Over subsets that contain a distinguished elements。And now so what I've done。

 just group the terms together corresponding to A and S minus a。

So this is now V of A plus V of its complement within S。So again。

 this is just pairing up A and S minus a for every A in this sum。Because remember。

 these are the same for ARS mea， so that's legit。So now I can use sub additivity。

So the sum of its values for each of these bundles separately is at least as large as its value for all of the set S。

Okay。I should then pull this out。This is now independent of a。

And so because we got this by just pairing up things with equal probability。

 this is going to be equal to a half， or if you prefer， you know。

 this is just the probability that you win a particular item1， again by the symmetry argument。

 the way we're bidding we're going to win a given item exactly half the time。

And so that proves the key limit。And so again， so a couple of things。So again， all right。

 So this is the key part of the proof， which really doesn't seem to have an analog。

 which is really sort of beyond smoothness in a formal sense。 So again smoothness inequal is。

 we flip the quantifiers in the sense that the deviation B star depends on D。

 which corresponds to some equilibrium。 And if you look at this proof。

 I mean it's really unclear how you'd have a version of this proof。

 which was oblivious to the distribution D。 I' it uses it in a very fundamental way。

 It seems these symmetry arguments。So that's very clever， right？And like I said。

 this keylema will substitute for smoothness condition in the price of anarchquy proof。

 which is what I'm going to do next。All right， there any questions about this。Alright， so good。Yeah。

 so the proof is coming up， it's you know。It's a little bit technical。

 like the doppelganger tricks that we saw before， but then then we'll be done with the lecture。

 and then we'll take a break and have an easy second lecture。All right， so。All right， so again。

 what we want to prove is that simultaneous first price auction。

Arbitrary product distribution over subative evaluations。

Bys na equilibrium within a factor four of optimal first price auction。

 so we don't expect to need any no forbidding condition。Actually， a factor two， excuse me， factor2。

Allright， so。The first maneuvers will be familiar。So consider a base na equilibrium。

In first price auctions， remember there's this nice optimization we can do where we can know we can basically cancel the error term we get at the end。

 which are just the winning bids， we can cancel that with the revenue on the left hand side。

 let me remind you what that is。So what do we actually care about。

 what we actually care about is the welfare of the equilibrium。

But always in these price of energyarchy of auction proofs。

 we pass to player utilities because that's what the equilibrium conditions is about。

So we have some of the utilities。Plus， the revenue is left over。Okay。So this is just by definition。

 eventually we'll be able to cancel this revenue term with that final error term we always get sum of the winning bids at equilibrium。

All right， so let's analyze this， right， because this is where。

This is where the equilibrium hypothesis can be used。And as usual。

 what we want to do is we want to lower bound this。

And we're going to do that by considering hypothetical deviations。

 and instead of a smoothness condition， the keylemma will propose to us hypothetical deviations。

 which this time will be a function of the particular sigma that we chose。Now。Okay， right。

 So let me define， let me define the deviation。So consider the situation where bitter eye finds itself having this sub added evaluation V sub I。

 And moreover， and we're dealing with this Bayes natural equilibrium sigma。All right。

 so here's what it does。To motivate the first step， let's look at this keylemma。

 So this keylemma tells us how to bid if we know how other bidders are bidding。

 that's not a problem because we know the Bays national equilibrium。 So we know what that is。

 But also， this was for a particular set S。So it told us， you know。

 given a set S that we want to target how to bid for that set。And canonically。

 we're now used to thinking of this set as， you know the stuff you get an optimal solution。

 But now we have the same problem we had before where we needed the doppelganger trick right where when a player I is sort of reasoning about deviations。

 It only knows its valuation。 It doesn't know whether。 So it doesn't know the optimal allocation。

 So we need to somehow in defining this deviation pluck from thin air。

 suitable set of items to bid on。 And we're gonna do that the same way we did before。

 bitter I is just going of hallucinate some doppelganger types， W。 And it's going say， okay。

 well for all I know other players have these valuations that gives me an optimal allocation that tells me a bundle of bit on。

So。Here's the randomized algorithm defining the deviation for bitter eye。So it samples。

 the doppelganger types from the public prior F。I'm going to use S star I to denote the bundle I gets in the optimal allocation。

 the optimal allocation when this is the type profile。Yeah。

Now that I know a set and that I know sorry distribution on those bidders。

 now I can invoke the key limitma to figure out what I should do。So， bid。B star I。

Where this is a function of what my value is。 It's a function of the。

Types I've hallucinated for the other bidders。 And it's a function of the particular。

Bs natural equilibrium we're looking at， this， of course。

 defines a distribution over bids by the other players。 Okay， so remember Sigma is known。

 Sigma is the mapping from valuations to bids。We have a prior on V。

 so we know a distribution over v minus I。 We know sigma。 So this is a distribution over b minus I。

 so sigma minus I v minus I is exactly a capital D。Okay。

 so this is just the distribution of the bids by the others。 That's the capital D。So as in key lemma。

And so in the keylemma， we take S to be S star I， V I W minus I， and we take D。

 so just be sigma minus I V minus I， where V minus I is drawn from the known prior。Okay。All right。

So if a bidder really， really wanted to。They could act in this way。Okay， and its utility， we know。

 would only go down。ちち？I should say this is also a recent result， so this is a stock。

 all this result is a stock 13 paper。Feldman grabvin and Lucre。Okay， so。

For every bidder for every type V I might have。Since sigma is a Bay as Nash equilibrium。

It utility only drops。So the randomness is。I want to write this out。诶。So it's equilibrium utility。

Is bounded below by its utility if it acted in this way。

 so let's just expand out the randomness and the actions of player I。

So we have randomness in what other players types are。We have randomness in bitter eyes action。

 it picks a W。And then it does this bid。B star I， which depends on all this stuff。Right。

 so that's what it's doing。Others bid， according to。The Bayes National equilibrium。

 And now we apply the key lemma。Alright， so for the key lemma。

 what I want you to do is I want you to think of。W as fixed。Okay， so remember。

 V are the actual player types。 Okay W exists only in the mind of player I when it's trying to figure out how to bid。

Okay， so and so， and how does it use W， It computes the optimal allocation。

 And it figures out this bundle of items that's getting S star I in the optimal allocation。

 So think of W as fixed。And at that point， then， the set S that bitter I bidding on is fixed。Okay。

At that point， we apply the keylemma。Okay， for a fixed W。And we apply it to this thing。

 so the key limitmma gives us a lower bound on how well we're doing with this deviating bid。

And what do we get， we get half the value of the set that we're targeting。Oh。

Minus the expected highest bid on the items that we're targeting。

 where now the expectation is over the uncertainty in other players types。Okay。Okay。

 so this is B minus I drawn from D， that for us is just the equilibrium bids by the other players。

So sum J and S star I。And then we just look at the highest bid by somebody else。

 and the bids are just given by the Bays Nash equilibrium。Okay。

So the notation here is this is K's type。 Sigma K of VK is its bid， given its type。

 And remember a bid is an M vector。 And here I'm looking at item J。

 So I'm looking at the J component of that M vector。Okay。All right。

And so now the rest of the proof looks similar to when we first did the doppelganger trip trick。

 okay。So this was our reasoning about a fixed player I who knew its valuation v sub I。

 So now we're going to integrate out over v sub I。 So average over player I's type and then sum over the bidders okay。

All right， so what do we get？Well， on the left hand side。

 we get the expected sum of player utilities。So what do we get on the right hand side， Well。

 something nice happens， okay。In particular， this term is nice。 Allright。

 so let's stare at this for a second。So remember， think of W as fixed。For starters。So。Okay。

 we're integrating out with us Okay， So what is this。

 So this is the welfare I contributes to the optimal allocation when its valuation is V I and everyone else's valuations are W minus I。

 It is by definition。 So it's， it's a contribution to the optimal welfare in that situation。Now。

 integrate out over W。 average over the types， the types W minus side that other players could have。

So what's that， That's just the expected contribution of player I to the optimal welfare。

 when its type is V I。And I don't know anything else about other people，As W minus I varies。

 I'm contributing something to the optimal allocation， and then if I average out。

 that's just how much I contribute to expected optimal welfare when I'm VI。

So now if I integrate that out over VI， that's just my expectedric contribution to the welfare。Okay。

So once I integrate out over V I， this just becomes eyess share of the optimal welfare。 Okay。

 so that's great。Allright， so the first term is exactly what we want。Well。

 I guess there's a one half there。So one half expectation over V。Of opt to。All right。

 so we declare victory on that term。Now， what about this term， What about this term， Okay。

 so we're integrating out with respect to V I。 So a V I joins its compatriots， V minus I。

 And we're also summing over I。Let me write this。By in the following way。

 I'll put the sum over bidders first， and then the expectation。

And then I'm just going to copy the sum again。this is this is simple but sneaky。 What happens next。

Allright， so this I haven't done anything。 Okay， I just wrote down what we had before and reorganized the sums。

So here's the sneaky part。I claim I can change this。Tos WI。Okay， and and it doesn't matter。

So why is that true， Well， let's look at， let's look at what we'。 Okay， What is this。

 What are we talking about here， So this is the highest bid。By some player other than I。O。

In the equilibrium。So this doesn't depend on I at all。 Okay I has nothing to do with this。

 It doesn't depend on I's type。 K I's actions are not involved。

 So doing something with player eye has no effect on this thing。

So the only thing that could matter is if it somehow affects how things were distributed。

 but it doesn't， right， So how is VI comma of W minus I distributed？Remember。

 it's a product distribution， so this is just a random valuation profile。

WI W minus I is also just a random valuation profile。doesn't matter。 Either way。

 this is just the set that I gets in a random evaluation profile。 Okay， doesn't matter。

 So this number is exactly the same， either way。Okay， so let me replace this。By just W。

Now why does it matter， Why is it nice having this be sort of a bonaide kind of coherent valuation profile that's independent of I。

Well， here's why。So， push this sum。God， I love linear expectations。 I love it so much。😊。

When I teach 161， it's the only time that's the algorithms class。

 It's the only time all quarter I put something in a box。I read it down and I put in the box。

And I say， this will be on the exam。 It's the only thing I do that for。All right。

 so push the sum back in here。Okay。So， now。So inside the expectation， what do we have？

Some of her eye。Some over。The items in the bundle that I gets in the optimal allocation。

And then we have， again， the maximum bids by others at equilibrium。The point is。

 now that this is just some fixed valuation profile， W。As that range over eye。

 these optimal bundles are just a partition of the items。RightSo over fixed W。

 these evaluation profiles， the optimal allocation is whatever it is。

 And so as I sum over the bidders and I sum over the items the bidders get in that optimal allocation。

 I just sum over all the items once each。这。So in other words。This。Right， so equals。

Just some over Jay and you。So this just ranges over every item once。Max equilibrium bid。Okay。Right。

 and I guess to get rid of I， let me just do this。Let make this equal。

So I'm just going to go ahead and throw I back in， but it'll only make this bigger。

And now this is exactly equal to the revenue term。都不有。So that was true W by W。

 so I can integrate out over W。And so you know the color。So the upshot is this。Is it most。

Some over all these of sum over I equal 1 to n。So these， you know， remember of a first price auction。

 So these are just the payments that people are making。 So P I of Sigma of V。Okay。

So this gets canceled out with this。So putting all together。

 we get that the expected welfare of the Bays Nationalash equilibrium is lower bounded by this half of the welfare。

So that's it。So again， as far as the high level， you know the details of these last shoe lines are slightly different than the doppelganger proof that we saw。

 But again， if you had to do it yourself， you could figure out all these tricks。

 So as far as you what sort of the new idea here， the new idea here is really the key limitma。

 The new idea here is really to recognize the additional flexibility。

 the additional power you have by choosing deviations as a function of the Bayes na equilibrium。

 Our priorityi， because you have no idea what the Bayes na equilibrium looks like。

 it's not clear how to use that knowledge in your proof。 And so here the really cool idea as well。

 I don't know what it is， but it's some distribution and I can sample from the distribution in my deviation。

 And at least for sub added evaluations， the symmetry between this sort of battle between you you pretending like you're the other bidders and the other bidders themselves is enough to give you this factor to combined with all of the other ideas in our toolbox。

😊，Okay。All right， so let's resume at four and we'll talk about revenue maximization for I promise at most an hour。

Okay， and it'll be mostly examples。 So it won't be It'll be good for a late afternoon lecture。

