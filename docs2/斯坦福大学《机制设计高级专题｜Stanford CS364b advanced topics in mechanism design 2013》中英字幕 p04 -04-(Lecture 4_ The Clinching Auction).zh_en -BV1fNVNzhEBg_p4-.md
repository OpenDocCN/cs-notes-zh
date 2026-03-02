# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p04 -04-(Lecture 4_ The Clinching Auction).zh_en -BV1fNVNzhEBg_p4-

So one thing that's kind of bizarre is actually that that final theorem we did about the。

Ex post and sent a compatibility of that auction。 actually don't know who to credit that to。

 I haven't seen that precise statement actually stated anywhere。

 So I'm sort of drawing from four different papers from the 80s。 I mean， I'll post them on the。

 on the course site。 if you want to have a look， but。嗯。Anyways， yeah。

 so sort of drawing from what seems like a circle of ideas。More than any one particular source。O。

It's time to move on to scenario number four。Which happily， by and large。

 will be easier than the unit demand setting we just did。

 There's one nontrivial complexity which shows up， which is the main reason I want to spend some time on scenario 4。

 Plus， it'll be a cool option。 That's another good reason。And then again， looking ahead。

So what we're starting out with this class the first three weeks or so is I basically want to focus on the tractable special cases where we can get everything we want。

 everything I want， I mean we get a really strong incentive guarantee so for ascending auctions it's this epic guarantee we get total surplus maximization and we get it using auctions which are computationally tractable so there'll be lots of situations where it's simply impossible to get all of those things and what I'm doing in these first few weeks is trying to give you a really thorough grounding when we can get all of it and so next week will be the culmination of that and it'll be this very fundamental class of preferences called substitutes and the way I'm sort of structuring this is I want to make it so that that in some sense will be the convex whole of everything we've seen so far so we're looking at all these different scenarios that on the one hand know our fundamental in their own right the theory of unit demand bidders I think is very nice and very rich but on the other hand I think willll be much easier to understand these so calledled substitute preferences with all these special cases to kind of fall back on。

So that's kind of the bigger picture。All right， so scenario4。So we're looking at multi unit auctions。

 meaning we're going to go back to the identical goods case。So scenario one。

 you might recall was identical goods and unit demand。 So now we're going to relax。

 generalize the unit demand assumption。 and it's going to be what's called downward sloping valuations。

So we have M identical goods。But people in general want more than one， okay？

And so the way we're going to model this is VIJ is going to be your marginal value of getting a J copy of the good。

 given that you already have J minus1。And so these as usual， will be known only to the bidders。

So the private marginal value of Jth units。Okay， so if I give you some amount X of goods。

 then I sum up these VI Js for all J of most X to get your overall value for all X of good goods。

All right， so this is clearly not unit demand， right So unit demand would be the special case where these are zero whenever J is two or more。

 That would be unit demand。Right， but downward sloping。We will assume。That VI is non increasing。Okay。

 and as you'll see， we're going to use this assumption over and over again。 Okay。

 it's actually quite this problem gets a lot harder without this assumption。

 we may or may not talk about it later in the quarter。Okay。Good。So our goal is the usual one。

 We want an ascending auction with all the good properties。 Okay。

 so E and surplus maximizing and so on。 and as usual。

 it might be a good idea to start with a sanity check。And Je ask， well。

 at least can we have a decent direct revelation version？And you， again。

 because it's surplus maximization， we sort of know what we should be doing。

 We should be doing the VCG mechanism。And。I know you all know what this is。

 but there's a reason I'm doing this。So in the VC G mechanism， right。

 you just ask people for the private valuation。And then the allocation rule is just like， okay。

 let's take the bids at face value and maximize surplus。

And so the thing I want to focus on right now is I want to understand that for scenario number four。

 surplus maximization is actually a pretty understandable problem。 Okay， it's not that hard to do。

 in particular， it's polynomial time， but even beyond that， it has some nice structure。

So think about this for a second。The allocation rule of the VCG mechanism is max surplus。

With respect to the BIjs。So obviously you can enumerate over all feasible allocations and just pick the best one。

 but there's definitely a better way to a smarter way to do this。

 And so what kind of algorithm is sufficient for this。Dis degree y。So basically。

 you take all the BIJs for all I and allJ， you just sort them from high to low。

And you just take the top end of the highest end。Okay。

So with two bidders that maybe you're giving seven to one of them and three of the other。

 maybe they're interleaved， maybe B one of one was the biggest， B one of two was the second biggest。

 and B2 of1 was the next biggest and so on， but whatever。So greedy is good enough。

So that's what I want you to notice at the moment。And then you have your usual VG payments。

Charge externalities。And we're again going to be shooting for an ascending implementation that simulates the VCG outcome。

 So it's， again， going to be essential that。We have a sort of better。

 more structured understanding of what these payments are。

 okay to have any hope of having them you know fall out of some sending implementation。

 we need some understanding better than just that abstract one okay and we'll do that。

Do that when we get there。But at least the fact that the allocation was so simple。 indeed， I mean。

 this is even simpler than in scenario， number number 3， unit demand， it was polynomial time。

 but it was matching。 matching is not a trivial problem。 This is kind of a trivial problem。 Okay。

 so that bodes well。So。Why spend any time on the scenario at all？Well。

 there is sort of a new challenge here。Which is our approach from the unit demand setting。

True while rosian equilibriumlibria is not going to work for scenario 4。Okay。So VCG outcome。Need not。

The orizing in equilibrium。Now， while was in equilibrium， I only defined for unit demand bidders。

 but it's quite straightforward to extend the definition to say this situation。 So again。

 you would just say unold good goods have price 0。And now you'd say instead of everybody getting their favorite good。

 Everybody would get their favorite quantity at the current prices。 Okay， so。

 there's some four goods， and they each have some price， and then I have some value for four goods。

 and that's attract to some of the prices on the four goods。

 And it should be of any quantities that I could possibly have with respect to the current prices。

 I get my favorite quantity。 So that would be aazu equilibrium。 again， prices and then allocation。

And so the claim is that here， the VCG outcome need not be one of these well rise in equilibrium。

It's sort of interesting because there， if you think about it in the unit demand case， actually。

 we proved a whole bunch of things， all of which were priority nontrivial。 First。

 for these unit demand bidders in scenario 3， we show that there exists a rise in equilibrium。

Which in， our priori is not obvious at all。And for more general preferences。

 you'll even lose existence。 Okay， so first， there exists one。 Second。

 there exists the smallest one that's component wise is smaller than any other laws in equilibrium。

Third， the VCG payments were always at most， and what was an equilibrium。But then fourth。

 you actually have a quality at the smallest one between the VCG payment。 we're also equilibrium。

 For this setting， you still have those first three properties。There still exist Oriclib。

 They're still a smallest one， and all of them still upper bound B C G payments。

 We just lose the fourth。We lose equality。 It could be the VC G payments are strictly less than every war rise in equilibrium。

 I'll show you an example。All I need are two bidders and two goods。So suppose we have one bidder。

With an additive valuation。just gets two units of value for each good that it gets。

And then we have one unit demand bidder。we only wants one good and is' only to pay one for one good。

So the BCCG outcome。So how do you maximize surplus。

 well clearly you should just give both goods to bidder1？Was it pays the externality。

 so it takes the surplus that it rips away from other people by virtue of being there。

 if it wasn't there， then Bi 2 would get its good for a value of one。

 It doesn't get anything with bitter one there。 so the externality is one， so that's its payment。

Bitter1。Gets two units。And the total payment。Equs one。I remember， VC G doesn't。

 It doesn't really assign a price to each good per se， but assigns a payment to each bidder。

 with unit demand， it was natural to induce， you know， it gave you induced price on goods。

 which is just what did the winner of it pay。 But so in this context。

 it's just the total payment of the bidder1 is2。 for the sorry， is one for the two goods。Now。

 could this arise as well was an equilibrium。 And again， while was is equilibrium。

 you actually have by definition， you put the prices on the goods okay。Well。

 so if we so to simulate the vome ataz equilibrium， Bi one has to pay one total。

 so the sum of the prices on the two items is going to be one。So it could only correspond。

To a wall and equilibrium。Price Q。With total price one。Which means one of the prices。

Is less than one because they' some one。 They're both non negative。

But to be a aaz in equilibrium and for bidter two to get nothing， it has to be happy getting nothing。

O， but if there's some good out there with a price less than one， then this bids like， dude。

 I would have totally paid that for that good。 I would have paid one for it。

It a bit two who is going to be unhappy if the sum of the prices is exactly one。

So that's the sense in which you cannot realize the VG outcome in general with a raw in equilibrium。

 The prices are just too low。Alright。And so on the， on the exercises， you know。

 I'll ask you to think more about what was in in this scenario because， again。

 a lot of the nice properties still hold， just not this coincidence between the VC G payments and the smallest。

Of the war as in equilibrium。So。How can we go forward。

 How can we pursue the possibility of an ascending auction in scenario 4。

 So we can't get VCG outcome and smallest raw nuclear because they're not the same。

 So we have to pick。Okay， so either。We could try to shoot for an epic auction。With a non VCG。

But what was an equilibrium， maybe small an equilibrium outcome。Or。

We could give up on the WZ equilibrium property and just try to get VCG。Okay。

But we have to do one of these。One one would be challenging。Okay， so。At some future point。

 I'm still trying to figure out when。 So later。We'll show that one is impossible。Okay。

So thing one thing which I'll put on the exercise set is just kind of a very special case of this。

 which is if you just try。To implement， even just say like a direct revelation mechanism。

 So suppose you just ask people for their evaluations。 There is the smallest waters in equilibrium。

 Just charging them that。 Okay， so the first thing we're going to just notice that that's not DS S IC。

 Okay， so if you don't use the VC G payments。 But instead you use the wires and equilibrium payments。

 it doesn't work。Okay， those of you who maybe remember something we talked about in passing last quarter。

 we talked about something called demand reduction。

 And that's kind of the problem with trying to use these rising equilibrium prices。

 The problem is that a bidder might have an incentive to get fewer goods， but much cheaper。Okay。

And so the VCG prices are lower precisely to take away the incentive for that kind of demand reduction Now that just shows that theres that just shows one particular approach doesn't work。

 Really， what's going on here is that if you want to be surplus and maximizing I mean so we talked about this in single parameter mechanisms last quarter where if you fix the allocation rule it pays pins down the payment rule up to a constant and there is an analog of that for the problems we're talking about here and at some point I'll figure out a time to say more about it okay。

So， again， the high level bit here is that if we want a surplus maximizing auction。

 it's just not going to work for incentives to simulate any other payment rule。

 okay so we just have to punt on raw in equilibrium it's just not going to work。

So that's what I want to do next。So coming up next。We're going to do this okay。All right。And so the。

 I mean， frankly， the whole approach， the whole order of operations in accomplishing this is going to be exactly the same that was in scenario 3。

 happily， kind of every single step is considerably easier。 Okay， But so the first step is。

 we're going to say， well。😊，Yeah。We already mentioned this。

 but if we're shooting for these VCG prices， let's have a better simpler understanding of what they actually are okay we're not going to have an ascending auction that just goes to these very abstract externality charging payments。

What's important？Is so we understand what the allocation rule looks like。

Over here in this scenario four， let's understand what the payments look like。

So VCG payments revisited。Okay。All right， so。So what do I mean by charge externalities？So again。

 you know， again， what does this mean this means？嗯。Max possible surplus for others。Okay。

 so you imagine deleting I and now just optimizing purely for the other n minus-1 people。

 So obviously in a multi- united auction， that would mean you just look at all ways to allocate these M goods or bid I get zero of them。

 all M are given to the other n minus-1 people。And then you subtract。The surplus。

Of the others in the VCG outcome。Okay， so in other words。

 you look at the surplus of the other n -1 people， if you optimize purely for them。

 minus their share of the surplus when you optimize for all N people。So again。

 is this this is the completely general definition。

So now let's think about what that looks like for multi unionion auction。Okay。

And we're going to use the fact that surplus maxization is a greedy algorithm。 Okay， and again， this。

 this should feel even better than scenario 3。 scenario 3， we have these two matching problems。 Now。

 we just have these， you know， each of these is just the outcome of some greedy algorithm。 Okay。

 where I'm running here。 I'm running the greedy algorithm on us on a。Here。

 I'm running it on a subset of the bids as here。 Okay with eyes。

 all of the B IJ is deleted when I run this， this algorithm。Okay， so what is this。

 what is this expression in blue？So fixed eye。And let's say it gets。X I units。In the VCG outcome。

And so what I want to do here is I want to look at other bidders， BKJs。In sorted order。Okay。

 from high to low。And this is exactly the relevant input。For this computation。

 right So for the Mac surplus deleting I， What would I do。

 I would sort all the B KJ for K not equal to I。 And then I would just take the top M。Now。

The relevant regions， so from high to low here。So。First， we have amongst all of these other BKJs。

 again， remember by downward sloping， these appear。

 these are just sort of right so each persons again。

 think think about the truth think truthful bids or each valuation is already sorted high to low。

 So this is just some interleaved version of different people's sort of valuations。So， over here。

Of all of these， we have the highest M minus X I。 Were again。

 X I is how many bitter I gets maybe there's 100 units overall。 This guy got 10。

 So these are the top 90， okay。Then we have the next region。Which are the next XI highest。

 and then we have everybody else。Okay。These are the rest。So。These top guys。

Which of these two computations do they participate in。Which are those two allocations？Both， right。

 So when I was there， it's only to get 10。 So 90 go to other people。

 And of of the other of the other， who do they go to， They go to the highest B KJs。Okay。

 so these are。So these in both。These X I guys or 10 guys。 These are really important。

 These are precisely the BkJs that get allocated after I delete I from the optimization problem。Okay。

 so these are 10 units that were not allocated to these other n -1 bidders。

 I delete I and now suddenly they are。So the sum of the BKJs of these X units is exactly the increase in surplus to the other n minus1p。

So in other words， the difference between those blue quantities is exactly the sum of the BKJs in this region here。

Okay， so only after deleting eye。Right， and then these really are relevant。

 We could imagine even just deleting these from the input if we wanted。O。So good。

 So that sounds simple。 And it is。 All right。 so let's actually articulate。

This structure in a way thatll be useful for us。In a way that。You know。

 we could imagine maybe computing with an ascending option。 Okay， so what we're doing now is we're。

 we're， you know。We're having the analog of reformulating this as smallest las and equilibrium。

 We're going reform it as something， actually， even simpler。Okay， so equivalent。Alright， yeah， yeah。

 So okay。 So， so bitter eye gets some Xi units like 10 units。

 And the overall payment of bitter eye is exactly the same sum of these Xi things。 Okay。

 like 10 things。 So it's gonna be convenient to kind of ascribe。

 even though VC G just give sort of an overall price that bitter eye has to pay。

 It's useful to kind of， you know， think of that as there being a price for each of the X I goods that it gets。

 It's what gets X I goods。 We're going think of these X B Kjs as supplying those X prices for the different goods。

And notice those are different prices。 Okay， these in general will be different numbers。

So specifically， let's think about。Let me actually define。So this is for。

Some good that I actually gets。In VCG。So we can write this as the。

 this is a little bit of a mouthful， but。So what I'm going to do is for the first good that bitter eye gets。

 I'm going to charge it the lowest of these Xi。So the first good is its highest value。

 and that is the good that's going to be given the lowest price。

And so then for each success of good that it gets， its marginal value will be going down and down and down。

 and the pricing going to be attributed to it will be going up and up and up。So M minus J plus1。

Highest。BKL。Where here K is somebody other than I。Okay。So， for example， when J equals one。

 that just says for the first good that bitter eye was granted。

 I'm going to think of charging the lowest of these Xi bids to it for the second good。

 That's the price for the third good， that's the price for the fourth good。

 That's the price and so on。 These are sort of high and low。 so these prices are going up。

That's all this says here。And so the one way we can understand the VCG payments is just for a bitter eye that's granted J goods。

 It's paying this or it's paying this formula for each of the units that it gets。Okay。

So some things to note， we've already talked about this。So first of all， just by definition。

So what I'm trying to point out is there's some kind of， you know。

 in effect we're taking some kind of supply and demand curves and crossing them。

 that's basically what's going on in this mechanism okay。So just by assumption， by downward sloping。

 we have this property。So the value for each incremental unit is going down and down and down。

 By the way， I've defined these VCG prices。They're going up。So。At the end， and so therefore。

 for all of them。It's going to be the case that V of Xi。Is at least。PI Xi。Okay。

 so the price I'm charging for the highest， and therefore， for all of the units is at most。

 the smallest value and hence all of the values of all the units you got。So is that true。

 Well we just need to check the last one。 So the price for the last guy is just going to be this B KJ。

And when I is actually in the computation， all of the Xs that are allocated interspersed with this top region。

 that's because they were allocated。So these are people who lose when I is in the picture， okay。

 so all of these BKJs are lower than the top XI of the ones that belong to I。For the same reason。

If I go one more in this sequence， the inequality flips。So V I， X， I plus1。Is it most， again。

 I can define this equally well for any J。So let me， actually。Do that。Okay。

 the same for exactly the same reason。Okay， so for the X I plus one bid of bitder I。

 that was actually not allocated by the VCG mechanism， which means it didn't make it in the top M。

 By contrast， if I plug in X I plus1 here， all of a sudden I'm talking about this bid。

 which is part of the top M。 So this was in part of the top M， and this was not。 So this is smaller。

And so again， the way to think about this is just， you know， there's basically some values。

 marginal values by the bidder。 And then in effect。

 implicit in the VCG mechanism is some sort of price schedule。 right It's like， oh， you want， well。

 for the first good， it'll cost you this。 you want another。 that'll cost you this。 Another。

 that'll cost you this。 with some increasing price schedule。

 And with the V G mechanism is implicitly doing。 it's。For each bit of looking where they cross。

 and it's giving the bitter eye exactly the units so that of for the region where the values are at。

 at least the prices。And again， one thing to notice。As you sort of expect。So these VCG prices。

 this is totally independent。As you'd expect in a decent mechanism， independent。Of eyes reports。Okay。

 so one way to think about it is just the other n -1 bidders bid。 They bid whatever they bid。

As a function only of their n -1 bids。 So all of their B K Js that fixes the P I Js。 Okay。

 so you can think there's actually sort of a rise and equilibrium interpretation here。

 although the prices are bitter specific。 Okay， so rise in equilibrium。

 we have these just single set of prices， one for each good and every bidder walks up faces the same prices picks their favorite here。

 and this is sort of a general statement about decent mechanisms。 if just for a bitter eye Okay。

 as a function of what the other bidders bid。Now， all of a sudden。

 it's again like you're walking into a supermarket。Okay， or it's really here。

 it's like sort of a pez dispenser of goods， if you're old enough know what a pez dispenser is。

And so we're basically each good that comes out of the pez dispenser has a price tag。

 and each one is higher than before。And the obvious thing to do is just keep taking them until your marginal value for the next one decreases the price tag on the next item coming out of the PE dispenser so what this is saying is in effect。

 what the VCG mechanism does for you， it looks at the other bids。

 it sets up these price tags and then it optimizes on your behalf。

 it gives you exactly the optimal quantity at that price schedule， given your value。Okay。Good。

One more thing I want to say about the VCG prices。Right， so。Okay， so why， why am I not happy， Okay。

 so this is progress。 I mean， I think intuitively， this seems， you know， very well structured。

 very sensible。 It's still， So again， remember， we're trying to simulate these in an ascending a。

 Ultimately， we don't know what's going to look like yet。 but we wantan to， we want to compute these。

And this is still looking much more like something in a direct revelation mechanism。

 right I I'm really referencing all of the bids of all the other people。

RightSo I'd have that in direct revelation of limitation。

 But the point of an ascending of limitation is kind of to， you know。

 obviously you do learn people's bids or values in the iterative auction， like in the English a。

 the original one。 you learn when people drop out so you can back out what their valuations were if theyre if they're playing truthfully。

 but you sort of learn them on a need to know basis。 and this doesn't have that flavor。

 this expression。 This kind of references all of the bids。

 So I I want to do one more step and sort of reformulate this yet again。

 So it has more this flavor of something you can learn on a need to know basis。All right。

 and it's it's kind of immediate， no hard work here。So also equivalent。

So now I wanted to define it in terms of demand queries。 So again， ultimately。

 we're gonna to have some option where we're gonna have some price。

 We we're gonna ask people what they want。 So I want some version of P I J that references people's demands。

 So let me tell you， So what is a demand in the context of scenario 4。Well。

 it's just going to be at a given price per item on what's your optimal quantity？

So let's just say the maximum number of goods J。So that VI。Of J is greater than Q。

So if I tell you that you have to pay $2 dollars per unit， for this to make sense。

 it has to be downward sloping。 I've used that over and over again。

Your value per unit only going down so to know how many units you want before you should stop。

 you just go until the marginal value drops below the price per unit。 And you know。

 that's the right amount。So DIQ is just how many you want at a given price Q。Okay。So， now。

Here's another way to write。PI of J。Okay。So let's just take Jakeel one for starters。

So JL1 is the empty thing here。Okay。So it's just the value， the value of whatever is in。

Whatever's in this box。Okay， so there's some number here。So here' is how I'm going to define it。

 Okay， So imagine actually， I so so what does this， what does this demand say， This demand says。

 you know， for a given bidder， how many values do you have above this price？

 And so the thing I want to notice is what's special about this threshold is if I just go slightly above this threshold。

That's exactly where everybody else's demands is exactly the sum of them is exactly M -1。 Okay。

 so say the 100th， say the1 B， K J here is 173。Okay。Now consider the price of 173 plus epsilon。

There's exactly 99 B， K Js out there belonging to the bitterders other than I that are。

Bigger than 173 plus epsilon。Okay， so I I can characterize the M minus J plus1 highest number in here as the inphum of all the thresholds so that the sum of the demands are sum of the VKJs above this threshold is exactly M minus J。

Okay。So if you don't see this in real time， it's just stare at it later， okay， there's nothing yeah。

This reminds me of that's exactly what we're doing。 That's exactly what we're doing。

There was excellent。Very good。 That's right。 So this may be familiar to some of you。

 This was on a problem set in 3，64， a， absolutely。So。Yeah， I figured that was three months ago。

Thought you might be a little rusty。If we had to write it out and lock that。Awesome， awesome。Awesome。

嗯。Your excused for the rest of the lecture， if you want。It sounds like you earned it。Okay， so good。

 so PIJ。Is where to go， yeah。So the smallest price at which everybody elses demands。

Drops a lot of the stuff I talk about。 You might want to just think about the case where all of the all of the V I Js are distinct where there's no ties。

 A lot of this simplifies。 I'm going to do it in the general case。

 But that might be easier to just parse real time。 So I'm gonna write inequality here。

 It's the first time this drops to below M minus J。 But if there are no ties。

 then there's going be then， this is going be equal。 It's going to be the same thing。Again。

 the point is just imagine kind of sweeping a threshold from right to left and you're asking， okay。

 what is the point at which know there's exactly M minus L people to the left of me。

 and that's going to be at the M minus L plus1 highest speed。So why did I do this？Well。

 so here's a characterization of the VCG price， which is referencing only the demands of people。

 Okay， so all I need to know are what what are the quantities people want at some sequence of prices。

 And that actually tells me exactly what the price should be。

 So that's starting to feel like exactly something that would unveil itself over the course of an ascending auction。

Okay， that's what we're going to do。Okay。く。Good。So as advertised。

 let me tell you about clinching auction。 So last quarter we did。 So this is。

 so what I'm going to tell you now is the original clinching auction by Azebel。

So last quarter I told you about an extension of the so we're doing it historically out of order。

So last quarter we talked about a variant that was motivated about problems with budgets。

 which is not what we're talking about now。 So now we're just in the usual quasiline model。

 So one reason people have been building on this mechanism is because it extends to budgets more easily than other ones。

 but this quarter we're more focusing on the ascending auction aspects so this is the original one just for welfare maximization with no budgets。

 but what's nice about is it gives an ascending implementation and scenario4。Good。All right。

So this again， will just be one of these auction where we start the price at zero and you raise it and we wait and so basically we have the invariant the demand is bigger than supply。

 and as soon as the demand drops to be supplier or less we stop。

So we try to equalize supply and demand。 Now， on the other hand， remember。

 we definitely don't want to terminate with the lawss in equilibrium。

 We want to terminate with these VCG payments and these VCG payments charge different things for different goods。

 or at least the way we're thinking about them。 So we want our ascending auction to have that property also like the English auction did not have that property。

 English auction。 you had this current price and all the winners paid that same price of termination。

 So we don't want that。 We somehow want the prices to change over the course of the auction。

 so we're going to sell stuff along the way， not merely at the end。

 The stuff we sell earlier will be at lower prices。All right， so initialize。So a peak equal was zero。

So this is case I'm not I'm going to ignore， which is that even at zero price， this。

 the demand is at most M。 Okay， so in that case， just give you the good delay for free。

 and you're fine。So suppose at least a price equals 0。 There's sort of over demand。 Okay。

 so ask bidders。So at each iteration， at the current price。

 we ask bidders how many they would want at this price。 And again， remember， that's just very simple。

 really just asking， look， how big a prefix of your VI Js exceed P。 Okay， so as P goes up。

 there's going to be， of course， fewer and fewer VI Js that are bigger than P。

So these demands are going to be assuming bit honestly。

 these DIs are certainly going to be dropping over the course of the auction。

So that's bidders for their DIPs。Those are the queries we're going to ask them。去去去去去。So if， again。

 the demand has dropped。Halt， and I'll tell you in a second about the。Alllocs and payments。All right。

 but the main loop is as simple as could be。Okay you just keep increasing P by epsilon until the demand drops to be at most of the supply。

 Okay， and that's going to happen eventually， obviously。Okay， so allocation。Now， you know。

 in the simple case， and you might want to go ahead and think about this。

 the simple case where would be， you know， you have some iteration where some of uses exactly M plus one。

 say， and then you bump up P by epsilon， and then it drops to exactly M。And that's an easy case。

 So if the sp equal the demand， you would just give people the demanded quantities in that last iteration。

Now， in general， you know， especially when you've discretized like this， you know， for all we know。

 the total demand is going to drop from m plus1 to M -1。 It'll just skip M。 Okay， and basically。

 we're just going， we're gonna always allocate all M of the units。

 and we're just going basically do it arbitrarily amongst those sort of demands right at the threshold。

 So formally。So the final allocation， the Xs。Each bitter eye will get。At。

So they get at least as many units as they demanded in the final iteration。

And they'll get at most as many units as they demanded in the penultimate。Ittereration。Okay。

 so the sum of these is bigger than M by assumption。 some of these is the most M。So， give them that。

So， units。To each eye subject to。Allocating all items。Okay。

And it's not going to matter how you do this。 Okay， These are the constraints that matter。But again。

 I mean， in the simple case， you might want to think about that the sum of these just equals M。

 And then there's a unique choice of what to do there。So let's talk about the payments。And， you know。

 really。嗯。You know， for the payments， we're basically just going to copy this formula。Okay。

 up to the Epsilon。Okay。So with this understanding of VC G payments。 So。

 if you haven't done this work of sort of trying to understand the VC G payments in terms of demand queries。

 it's hard to see where this comes from。 given this， you know， groundwork that we've laid。Hopefully。

 these payments will seem。Well seem very sensible。So for the Jaith good。That a bitter eye gets。

I guess to suppose Vi I gets J or more goods。 And for the Jth good。

 we're going to insist that it pays。Okay， so there's going to be a minus epsilon。

But the main point is that you do the earliest。Meaning the lowest。Price Q。

So that the demand of the rest of the bidders。So these are over the prices Q that we're actually tested by the option。

 Right， So so what do we have here， Here we have it in feum。So in effect。

 the option is just discretize that in the multiples of epsilon。

 Those are the only things we actually sort of queried people's demands at。 and we're just saying。

 well， you know， what's our best approximation of this in FEMma。

 Let's just look at the lowest price at which this condition helped， which that was the most。

The first price， yeah， the first price at which that was at most。M minus J。Okay。

You may actually write this to be more symmetric with that。MingQ。Where again。

 this refers to the prices at which this auction actually queried bidders。

And this Q must exist because at the end of the auction， you know。

 if nothing else the highest price we ever tried， the sum of all of the demands was at most M。 Okay。

 so at that point， because bitter I got at least J items。

 the sum of everyone else's demands has to be a most M minus J。Okay， so if nothing else。

 the price at the last iteration will satisfy this。So that's the quencing option。

And this is all the properties we want。Okay， so we had to prove those things。 But again。

 the proof is， is definitely easier than scenario 3。 but that's the whole option。

Let me just make sure this makes sense。Let's just go ahead and run it in the example。

Which had no well rise in equilibrium。So remember we had a。Additive bidder， value2 for both。

We had a unit demand bidder。Okay， so。So let's try to understand what are bidders demands。So D1 of Q。

So what does that look like， So as a function of Q。What's bitter one's demand？

It's two win that drops a zero win。Right。So remember。

 the demand is just how many units would you want at that price i。e。

 how long a prefix of your valuation of your marginal valuations exceed Q so that one is just two comma 2 So as long as Q' is less than two。

 both of them do， if two' is at least two， none of them do。So D1 of Q。And then similarly。

 D2 of Q is1。For Q in0。And zero， thereafter。Aged。Okay， so then looking at the clinching auction。 and。

 you know， let's assume that。One over epsilon is an integer。Then basically， what's going to happen。

Is even in the very first iteration。Right。So even in the very first iteration， the demand。

 So think about it from Bi one's perspective， right， The demand by others is only one， right。

 So there's two units。The demand for others is only one， even at the beginning。

 even when the price is zero。Okay， so that basically means that bitter one will clinch its first unit at the beginning of the auction at a price of  zero。

So in other words， I'm going， I guess ignore this minus epsilon for right now。So basically。

 even at zero， this is going to be true。4 J equal1。Now， for this to be true for J equal 2。

 we have to wait until the price goes up to 1。 So the demand of the other person drops to 0。 Okay。

 so then the demand of everyone else is at most M-2。Imo 0。 And so that price 1 is what。

But the first bidder， we'll get that second unit at。 And if you remember。

 those are exactly the V G prices。 So Bi of one was supposed to be a combined value of one for both。

 That's happening，0 for the first unit， one for the second unit。All right。So let's， I mean， let's。

 so that's just sort of a。Toy example of the warmup。

 But let's actually prove that this holds in general。And I want to do， I want to do exactly the same。

 again， order of operations for unit demand。 I want to first just do an analysis under sincere bidding。

And I want to show you that， you know， up to epsilons。We， in some sense， simulate the VCG outcome。

 specifically the utilities of bidders and the VCG outcome。And then， you， as we know。

 that gives us something automatic for these consistent deviations。

 but we want to prove it works for all deviations。 And happily。

 that's much easier in this case than for the C， K option for unit demand bidders。Okay， analysis。

And again， for now， we'll just assume without justification， sincere bidding。Okay。So first。

 I want to talk about the surplus。Then I'll talk about the better utilities。 So let's first。

 at least prove that this auction， assuming since your're bidding gets the allocation rights。 Again。

 not worry about the payments。So， the claim。Is that surplus？Of clinching。

Is within the number of goods times epsilon。Of the max possible。Okay。This was pretty easy。

So the benchmark is VCG。And so the VCG allocates to the top。And。B Ijs。

And the surplus is just the sum of those。Okay， actually， the sincere bidding。

Let me just write theses。So that's what we， that's where we'd like to be。Now。

 assuming sincere bidding， what do we do， What does clinching do。Well。

 the last two iterations of the clinching auction identified two nested sets of bitters。Okay。

 so basically two nested sets of these VIJs。So in the last iteration。It identifies a set of。VIjs。

All bigger than P。And again， so this is I can understand if people don't see this。

 but if you don't see it's purely because you don't have the notation mapping solid yet because this is a trivial statement。

 So let's remember what is we're thinking about the final iteration of the auction。 Okay。

 when in halts。 So there's some current price P 00 bucks or whatever。 What is DIP。

 that's just how many units do you want at 100 bucks。 And again。

 that's just sort of how what's the length of your prefix。

 Okay so for how many Js is your VJ exceeded 100。So a DIP is just a collection。

 So if DIP equals to 10。 that's just a collection of 10 VIJs that are bigger than that threshold。

So by virtue of halting。With some of the DIPs at most M， that corresponds to a set。

Of these entries in people's valuations， whose size is the most。Okay。So needless to say， you know。

 whatever cardinality this is， these are the highest of all of the VI Js。

 So this is a subset of what gets allocated in V C G。And then， in the penultimate iteration。

We identify a similar set with a slightly lower threshold。With size bigger than him。Okay。

So the optimal solution corresponds to a super set of B1 and a strict subset of B2。

And so we allocate。Its all of B1。And rest to B2。And so the only error we could possibly be making is on VI Js that。

 you know， lie between P and P minus epsilon。Okay， so we're just making this discretization error of up to Epsilon。

 We waste at most epsilon surplus each of our units。 So overall。

 it put an epsilon at Epsilon times M surplus loss。Any questions about that？

So another way to think about it is this is doing an approximate。

 This is approximately solving the top M， you know。Sortted problem。All right。

So at least the allocation is basically right。So in unit demand。

 we then moved on to say that the prices were basically right。Here， because it's not unit demand。

 It's actually a little awkward to try to talk， you know， sort of directly about prices。 So instead。

 what I want to do is I want to talk about bitter utilities。 which if you think about it， you know。

 when you reason about deviations， that's what you actually care about。

 You just want to say bitter utility is basically the same， no matter how it deviates。

 So as long as we preserve those well， you know， all of the usual arguments will， will hold。So。Okay。

 so， so this was the assertion。 This is one， and this is the proof of one。 So here's the assertion2。

That the clinching auction basically has the same bitter utilities as the VCG outcome。

So for all bidders， I。Utility and the clinching auction。Assuming everybody did sincerely。

Is equal to the utility。In VCG。Up to plus minus M times epsilon。Sure。And， I mean。

 so this is the analog of saying we got the payments right。m。You got。

So let me argue this proof of two。Oh， yeah。So I just remind you。

So basically the way I'm going to prove this。As I'm going to remind you。

 the sense in which we can think about the VCG mechanism as kind of optimally solving this。

 you know supply demand curve， crossover point for a bitder。

 and then I'll argue that the clining auction is solving almost exactly the same problem just with sort of slightly different prices。

 So utility's going to be basically the same。So let me just remind you what's up with VG。

Because that's one thing we're comparing to right， So imagine we were actually doing VCG and everybody revealed truthfully what their private valuations were。

 what would things look like from I perspective。Well， from my perspective， before it。

 before it even submits anything。 So just as a function of the bids of the other bidders。

The bids of the other bidders define these prices， these P I Js。So again， this is。

 there's nothing I can do about this price schedule。 Okay， the price tags on the Pez dispenser。Then。

 you know。As a function of bitterized valuation， as a function of its value。

 marginal value for each of the next goods。 What the VG mechanism implicitly does is it just says。

 well， you know， I'll give you items at the prices until it's not worth it for you anymore。

 the prices only go up。 Your values only go down。 You know， at the point that they cross， I stop。

So in other words， I can think of。嗯。The utility in VCG。As being。The maximum。Over。The number of goods。

 So basically， I just you know， take the differences of your marginal values and the marginal costs。

 And as soon as these become negative， I stop。So let me write this this way。um。Max， so， basically。

If your' marginal value。Is bigger than the marginal price than you get it。 otherwise it's just zero。

Okay， so this is just saying， you know， trucate the sequence once they cross and then just sum up in the rest。

Okay， so this is the utility of bitter eye in the VCG mechanism using this notation。Okay。

 so in that sense， the VCG mechanism， it defines PIG independent of the valuation。

 and then it solves this problem optimally for a better eye。

So now I want to argue the clinching options is basically doing the same thing。Okay。

 under sincere bidding。So。So that's what's up in VCG。In the clinching auction， clinching。

So in the clitchching auction。I forgot the notation here。 So this， I'm going define as Q， I J。Okay。

So PIJ is the thought experiment。 suppose you're in the VG mechanism with everybody's truthful declarations。

 the Q IJs are suppose you're in the clinching auction with everybody bidding sincerely。

 and this is how they're defined。Okay。Okay。So the first thing to notice。

 this is really just by construction。 shootot， I erase the definition of P I J， okay。

So let actually let me rewrite here what was the reformulation that we had。

So this was the infeum over all Q， such that everybody else's demand。嗯。Is it most。M minus J。

So there's some smallest Q for which the point I'm trying to make is the P I Js and the Q I Js are almost exactly the same by definition。

 This is just the smallest of all real numbers  Q so that this is at most M minus J。

 And this just says， oh， well， if we restrict ourselves to multiples of epsilon。

 what's the smallest Q so that this is below M minus J。 Well， at worst， know， by discretization。

 it's an epsilon higher， then I subtracted epsilon from it。

 So Q I J is going to be only less than P J and by most epsilon。So。

So the prices are almost exactly the same。嗯。And the one thing， the one， I have to do some more。

 So why aren't we done。Okay。So remember that PIJ is the price you're going to pay for your J copy if I give it to you。

QIJ is the price you're going to pay for the J unit if I give it to you。Okay。

 so if I knew that a bitter I got exactly the same number of units in both， then I'd be done。

Because you get the same amount you're paying exactly the same amount for each show you'd be done。

 So I still have to do some more argument because I have to argue that， you know。

 you don't get radically fewer units for some reason in the clinching a。 And therefore， you know。

 your utility sucks。 I have to argue that。Okay。So why is that true？So， basically。

 I'm going to claim that in the clinching auction， we're essentially optimizing this。

For the bitterder， Okay， just with the Q's instead of the P's。 the Q's are almost same as the Ps。

 the load going to be almost the same。So， if。I is given。

At least at least J units in the clinching option。Then。Right， so， maybe just to back up。

 So what are we hoping is to be true， So we know that， again。

 the Q I Js are defined completely independent of what I does。And from I's perspective。

 what it really wants the clinching auction to do on its behalf。

 given that it's going to be paying Q Ijs， you know it just wants it wants the clinching auction to give it。

 again， the J units up to the point at which its value would drop below the price Q。

 that would be the clinching a optimizing for bitter I on its behalf。 So let's look at two cases。

 So we're hoping on the one hand that when its value is at least this price Q， it gets it。

 and the other hand， when the value is below the price Q it doesn't get it。

 Those are the two things bitter I wants。So suppose bitter I does get a JF unit。

Then the claim is it must be the case that it wants。Okay。And so why is this true， I mean。

 this is true sort of by the definition of the clinching auction。

 So what is the largest number of units you might conceivably get in the clinching auction。 Well。

 the most you might get is the amount that you demanded at the price of the penultimate iteration。

 Okay， P minus epsilon。And any units you get， you know。

 what's the biggest price you might be charged， right， So in other words。

 you would be totally happy to have this many units at a price of P minus epsilon。😊，O。

 you're not gonna get more than these units。 And what's the maximum price you could be charged， Well。

 the most it could be would be that last price P。 And then we also give you an epsilon bonus。

So you're happy with whatever you get， that's not the problem。So the other thing。The claim is that。嗯。

If suppose I does not get。At least J units。So ideally， we'd be able to say， well， you know。

 the only reason that can happen is because the price， the Q is more than its value to V。

 And that is true。 But up up to an epsilon， okay。So then if it doesn't get its JF unit。

 then it the only reason could be。That it's value。Is it most the price？At least up to an epsilon。

Okay。So this is slightly trickier， but not much。 I'll talk through it。

 but that's probably a good thing for you to think through also。So why would this be true？Okay。

 so suppose。um。That's why so suppose you didn't get J。Why would that be true。

 That would mean in the final iteration of the auction。 So notice。Again， by construction。

Whatever you demanded in the very last iteration of the auction。

 when this demand drops to Em or below， you're definitely getting that much。Okay。

 so if you don't get J units， it means at the last iteration。

 you said you didn't want J units right at this price of P， okay。And so why would that happen， Well。

 that would basically， I mean， then you just have to sort of substitute the value of the cues。 But。

 I mean， this is the condition you'll get。So I'll leave it for you to check that。All right。

 so and the claim is then we're done。All， so if think about the VCG outcome， what is your utility。

 your utility is exactly the outcome of this maximization problem。

Where you just look at the differences of the V's and the P's as long as they're positive and you sum them up。

What do these three points argue about the clinching a。

 It says it's essentially your utility is the result of exactly the same optimization problem。

 The only difference being instead of the P's， you have the Qs， those are most epsilon different。

 So they matter at most M times epsilon for utility。 Plus， if this difference is less than epsilon。

 you might get 0 instead。 so that's another at most epsilon per unit。So， therefore。Utility differs。

By most two epsilon， two epsilon。Okay。So this is the analog in the unit demand setting in scenario 3。

 where we said that the outcome of the C， K auction for every good J。

 the price was the same as under VG up to plus minus epsilon times。 so this is the analog。

 the utility of a bidder is essentially the same， whether you're talking about the truthful outcome of ECG or the sincere bidding outcome of the clinching option。

To questions about that， we're almost done。So that's enough to say。That。

So because we're simulating utilities。Under the VCG mechanism。

And because the VCG mechanism is dominant try and say compatible。No deviation could help you。

This says that consistent deviations won't help you either under the clinching auction。

 because again， there there's just this mapping between your utility and the VCG mechanism with a given declaration and your utility in the clinching a under a given consistent action。

 It's just exactly the same。So the， again， the issue is just， what about inconsistent actions。

 What about crazy actions， Can that ever help assuming other bidders bid sincerely。 Remember。

 Ra was assuming other bidders bit sincerely。 We don't know valuation。

 but we know they're not being crazy。So theorem。Last one for today。Clinching option is epic。

All right。YeahSo this is actually， I mean， basically the proof of this is already on the board。So。

So fix a bidder， fix valuation profiles。Assume other bidders bid sincerely， which is important。

 I leave I'll leave it to you to think about that。So what we need to show is that a best response up to some function of epsilon by I is optimal。

 sincere bidding is optimal。Okay。So here's the main reason it's important that other bidders bid sincerely。

Right。So in the cling auction。At the end of the day， So eventually， the cling ox is going to term it。

Okay。And， you know， whatever I does， it's going to get some stuff。It's going get J units of stuff。

And given that the other bidders bid sincerely， I always answer the demand queries correctly at every price they' ever asked。

Given that they bid sincerely。The price QIJ。The bitter eye is going to have to pay for its Jth unit。

 If it gets a Jth unit， it's going to be this number。Okay。

There's no action available the bitter eye that can change the price。 It's going to pay for a J unit。

 if it gets a J unit。Now， if the other bidders were not bidding sincerely。

 if they were like monitoring what I was doing， then all bets are off。

So if somehow I's behavior would change how the other bidders would answer the demand queries。

 forget about it。But sincere bidding in particular。

 means that the way you answer your demand query doesn't depend on anything that happened in the past。

OkaySo these are just going to be whatever they are。And so this price can be whatever it is。

So if you think about it。You know， like， let's actually give bitter eye way more power。 Okay。

 let's actually just say， we're gonna to let you pick however many units of this good you want directly。

 You just pick， pick J。P what you want。Just the catch， you have to pay， you know。

 Q I J for the J unit。But subject to that， do whatever you want。Well。

 what did we just argue happens in the clinching a。 We just argue that the clinching option。

Essentially， maximizes。Exactly that optimization problem。O。

Some over all J of the max between 0 and V。I J minus Q， I J。Okay。

 so the only thing the clinching a did wrong in optimizing this object this optimization problem for the bidder is。

 well， there might be some units J， where this difference is less than epsilon and you don't get it。

 so it might cost you M epsilon。That's the only error we make，So the point is， you know。

 forget about actions， even just let bitter eye pick units directly， but it can't affect the prices。

And then bidding sincerely is optimal up to Epsilon it。So but again。

 the crux the whole point is that you can't influence the prices。

 given that there's just nothing you can do。So。So， since。Eyes action。Can't influence。The QIJs。

And sincere bidding。Optimizes sum over J。Max  zero。Yeah， that's right。So any questions？All right。So。

Again， just sort of zooming back out to the big picture。 So for these， for these two weeks。

 our goals have remained totally invariant。 Okay， It's always asking。

 when can we get these awesome ascending auctions， We now have four scenarios where we can do it。

And the point of showing you all these different scenarios is that different scenarios have been hard in different ways。

So， for example， in the unit demand situation， the whole trick was to use these Or equilibrium equivalents。

 and we lost that in the multi unitit downward sloan case。

 that we had other structure which sort of saved us and still allowed us to get our eventual goal。

 So it's natural to ask， you， is there some common framework that you can think about both of these as special cases That's one question。

 Another question is， is kind of， you know， is there some， you know。

Inherent maximal frontier of of bidder's valuations， you know。

 that characterizes when we can have these awesome options and when we can't。

 And so the answer both of those questions are yes。 And again。

 the the key will be to understand these substitutes valuations。

 And that's what we'll start next week。 So see you then。

