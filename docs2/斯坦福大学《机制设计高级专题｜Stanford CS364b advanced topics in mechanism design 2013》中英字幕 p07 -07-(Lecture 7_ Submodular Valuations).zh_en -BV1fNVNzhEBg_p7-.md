# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p07 -07-(Lecture 7_ Submodular Valuations).zh_en -BV1fNVNzhEBg_p7-

Okay， so's let's just start with announcements。 So exercise set3 do today。

 there is is gonna keep exercise sets， and they'll still keep having a decent chunk of questions on them。

 but I'm gonna to start making almost all of the questions optional。

 So because I want people to be focusing on projects instead。 So for example， on number four。

 I think the number of nonopional problems this will totally be like two or three problems。

 Okay so that's really gonna to be tailing off now。 speaking of the projects。

 So I did finally post an initial batch。 you should have an email with that link。

 it's not linked to from the course page。 So if you didn't get an email from me tell me And you can go to to the projects I posted 10 from this first part of the class the first three weeks I posted close to 10 more for this week and next week and I'll post a few more for the last three parts soon as well。

 There's no hurry。 it's not first come first serve or something like that。

 So what I want is from everybody a week from Friday， which is February 7。

I would like your top two choices， and then I'll make some kind ofized computation centralized matching of who gets which project。

 And again， one of the things this is the smallest class I've taught in a while。

 And so I'm really looking forward to the opportunity to be actually talk to students individually so feel free to involve me in the process if you want questions about you're wondering whether paper A is too difficult or paper A paper B is too boring definitelyly feel free to ping me by email for some advice final announcement by sort of semipopular demand I'm going say there's going to be a bonus lecture。

 maybe there'll be two probably over the quarter。 So the first one。

 which will be more about the theory of gross substitutes valuations that's going to be a week from Friday So February 7。

 1215 to 205。 it will not be videotapes。 so really come if you want to see it。

 and it's going be in Gs 315 on。So any questions before we get started。The February is personal。

All right。7eventh， yeah， Friday， sorry。Yeah。So that was the time slot that most people could make。

Okay， so where did we leave off last lecture。 So we're almost so the first part of this class was about tractable special cases where you could maximize welfare in polynomial time。

 implement the VG mechanism in polynomial time。 and ideally even get ascending implementations in all of those cases in some sense。

 a strictly more difficult goal。 So let me just close the loop on that。

 I didn't actually talk about ascending implementations for gross substitutes evaluation。

 So I just want to have a few comments about that before we move on to less tractable cases。

So recall gross substitutes。 That was what last week was all about。

 That's this condition where if you're a bidder and you lose some of the items。

 but the items that you're still retaining still have the old prices。

 you don't want to relinquish them。 so in an an ascending a。

 you still want what you've got in any point in time。

 even as prices have gone up on the other objects。 and we proved a bunch of stuff about that last week。

 the second lecture last week was about welfare maximization。

 and we worked pretty hard to prove that you could actually do it in polynomial time。

 And that took some work， took some assumptions， we need to assume you get use demand queries。

 So that we interact with these black box valuations。

 You give them a price vector they tell you back the preferred bundle。

 and we use the ellipsoid algorithm， which is the sort of heavy machinery linear programming algorithm。

 which says， oh， as long as there's a polynomial time separation oracle。

 you can solve the linear program in polynomial time。

 So there are some bells and whistles on those results。

 you can get away with just value queries there are some complicated commonatorial algorithm that don't use the ellipsoid method。

 But anyway was the main point is poly time。With gross substitutes valuations。

 so at least we can get a D6 solution， VG。So what about the more ambitious goal of getting an ascending implementation？

So this is this is actually a tricky question。 So first of all， let's remember what that means。

Or necessary condition， as we've discussed by a combination of the revelation principle and uniqueness of prices。

 at minimum for an ascending auction to be exp post instead compatible。

 it better be the case that the bidders bid sincerely， the end result of the VCG outcome。

 both the allocation and the payments。So we've mentioned this a few times。

If all we wanted was the VCG allocation， meaning a welfare maximizing allocation。

 we know how to do it。 The Kelso Crawford auction converged to a rise equilibrium， in particular。

 it's an efficient allocation。 So the hard part is the prices。 and in fact， you actually can't do it。

Okay， so one of the results in this G tochety paper say that actually there does not exist。

Ascending auction。For GS， that always terminates at the VCG outcome。Okay。

And it's really quite a nice example。 on the optional exercises。

 I'll just sort of sketch how the example goes。 It's just it's three bidders and four items。

 And the thing I want emphasize is this is not this is not a computational and possibility result。

 It doesn't say there's no polynomial time algorithm or something like that。

 It says it's information the。 So it says if you restrict attention to just having an increasing price trajectory and interacting with bidders only through demand queries。

 you simply cannot learn enough about what they want to be guaranteed to compute the VG payments when you terminate。

 it's purely information theoretical。 you don't get enough info。 if you restrict prices to be aend。

 So this is a sense in which while gross substitutes are sort of the limit of tractability。

 This is a sense in which it's actually strictly harder than the first four scenarios that we study。

So that's good to know。 interestingest to know。 Now。

 there have been a couple proposals and sort of the ascending auction， sort of flavor to， you know。

 expand what we allow as an ascending auction and therefore elude this impossibility result。

So the first thing。Is a paper by Azabel， the same Izebel from the clinching auction for scenario four for multi unit auctions。

And Oze aboutt proposed allowing more than one ascending price trajectory。 So in some sense。

 you know the prices go up and you ask a bunch of demandqueries， learn some stuff。

 and you kind of restart somewhere and do it again， and you do that a bunch of times。

 And he showed that if you're allowed to sort of have n plus one ascending price trajectories。

 then you can get enough information to compute all the VCG payments at the end of the day and you do get an exposyn compatible welfare maximizing mechanism for gross substitutes。

So can compute。The VCG outcome。Using n plus1 here， n is the number of bidders。

Ascending price trajectories。And in some sense， this is in the same spirit of how to implement the VCG mechanism。

 you solve n plus one welfare allocation problems。 So in the same thing here。

 you're gonna have one price trajectory where， in effect。

 you're asking demand queries from all N of the bidders。

 And then you're going to have n different other trajectories where one of the end bidders is excluded。

 And at the end of the day， you stitch all that information together to compute the VCG payments。Yes。

Okay， so this algorithm， this algorithm is quite interesting。 sort of as a proof of concept。

 It really says， you know， you can take these just simple ascending auctions like Kelsa Crawford。

 which only get you a w roian equilibrium and don't get you VCG payments and somehow build on them in a clever way and actually get enough information to get the VCG outcome and you only use item prices。

 the entire time。 So that's interesting。 but it is pretty complicated。

 So I'm not going to talk about it more in class。 it is one of the projects。

 if you're interested to read about this auction。 And because you know of all these ascending price trajectories。

 I don't really know of real worldd a that resemble this particularly So it' it's a cool theoretical construct。

 but I'm not sure it's more than that。 It can also be thought of as an extension of the  clinching a for identical items that we talked about for scenario for the tricky thing here when you have multiple goods is as the prices go up。

 the demand for a good need not only go down。 So if it's identical goods。

 if everythings the same the higher the price the lower the demand。

 if you have a bunch of different goods and you fix it on just。itemem。

 it may be that the demand shifts from going up and down because prices on all the different goods are sort of simultaneously going up。

 So you have to extend the clinching auction to deal with not just clinching， but also uncinching。

 In some sense， know refunding bidders as you take items back away from them。

 So that's sort of the high level gist of how this works。 Okay， And that's all I'm to say。

 say in class。 So the second way that people have expanded what's allowed as far as asc sendingending auctions and dodge the ghost to get impossibility result。

 and it's more sort of closely connected to what people do in practice is to allow bundle or package bidding。

So some early suggestions of how this might be done were parks on Unger and Asible and Milgram。

And again， the latter paper here is one of the project topics if you're interested。

And so this is sort of related enough to things we've already said that I'll give you a few more details right now。

So the idea is， you know， our auction are going to be more powerful than before。

 rather than just maintaining a price for each item。

 the way we've been doing all along for every possible subset S of goods。

 and even for every possible bitterder I， we're going allow。

 we're going keep track of a different candidate price。So bundle prices。P I。

For all bidders I and for all bundles of goods， S。So let me show you how this one way this could work。

 there's there's many ways you can do these options。 But let me just give you a very simple one。

And this is going to be。Very similar。To the Crawford Noer auction。

 So that was that one with unit demand bidders， where we just had people continually bidding on their favorite good over and over again。

So we're going to do basically that same thing， except instead of bidders bidding on。

Items are going to be able to bid on bundles and instead of just one item having one price。

 we're going to allow different prices for different people。So each iteration。As long as nobody。

 as long as we're getting new bids。Here's what we do。So at any given time， there'll be these PISs。

 okay a price for each bundle in each bitter eye。Now， in general， these PISs might overlap。

 it might be that in different parts in time， different bidders had bid for overlapping bundles。

 so we can't just regard all of these as being sold。

 so the seller has to somehow figure out which of these bundles it's going to actually tentatively accept at the moment。

 and so the seller just picks the allocation of items to bidders that maximizes the seller's revenue with respect to the current prices。

 the current PISs。So the seller computes。The allocation S1 through SN。Maximizing。It's revenue。

And all the PI of Ss started zero。Now， so if you're one of these bidders。And you're not chosen。 Okay。

 so you end up getting nothing。 You're given an opportunity to bid again， bid on some bundle。

So for each eye。With nothing。The bitter eye picks one of its favorite bundles at the current prices。

 And now， remember， the current prices， actually， they're personalized， right， They're P I of Ss。

 So bitter eye says， well， you know， given the current price for me for any bundle and given my values。

 which one gives me the highest utility。So pick S。In Argmax。Of its value for a bundle。

 minus its current price of that bundle。And。It's allowed to increment the。

Price for that bundle by epsilon。OkayAnd so notice， bundles are chosen to maximize revenue。

 So by increasing the price on a bundle that has your name on it。

 you're more likely to get allocated in the next round by the seller。 Okay So initially。

 know so if you think about this auction， initially sort this is weird。 All the prices are 0。

 So basically， if I'm a bid。 if all the prices are0， may as well just ask for everything。

 So in the first round， everybody ask for everything。

 And then the seller is just gonna pick sort of one person arbitrarily。 Everyone else will lose。

 And then they'll have to pick bundles that they want。 And then slowly prices will be going up。

 And then eventually these will be sort of meaningful maximization problems。

 so basically have bidders focusing in on the bundles that give them the most utility at the current prices and the sellers always just picking the highest revenue bundles。

 and you just let this go。Allright， so。Yeah， again。

 so I would really just think of this as like that unit demand option， except what we used to have。

 you know， it used to be that the fundamental things were items that people were bidding on。 Now。

 it's like the goods are bitter bundle pairs。 I comma S。

 So that's what get incremented in a given round， something corresponding to a bitter eye and a bundle。

And just like the Crawford， Noer auction has certain properties at termination。

 So does this one proofs are pretty much the same。So properties。So if bidder is bid sincerely。

 and that just means that they you know， report a bona fide element of this maximizeimr。

So if you have sincere bidding。Then you terminate at the sort of suitable analog of a Walraian equilibrium where you have bundle pricing。

So that's called a competitive equilibrium in this context。

And this first property is true with absolutely no assumptions at all about the valuations。 Okay。

 so gross substitutes are not doesn't matter。 Okay And the proof is exactly the same as the proof that the gross or Crawford noer auction converges to a rise equilibrium。

 It's like basically word for word the same。 As far as what's the definition。

 the definition here just says the seller should be maximizing their revenue with the current prices。

 Obviously， that's going be true a termination。 And then furthermore from each bidder。

 they should be getting their favorite bundle at the current prices。 And again。

 remember the prices are personalized and are bundle specific。 And that's also sort of clear。 I mean。

 that's how， know， so a bidder is going to wind up at the end of the day。

 getting some bundle that they bid on。And then what's happened since then。

 the prices of other bundles have gone up。 Okay， so you only bid on a favorite bundle。

 And then if you get it， it only looks better as time proceeds。 So it's the same proof as before。

 The first welfare theorem still holds。 It's still the case that a competitive equilibrium。

 It has to be a welfare maximizing allocation， okay。Now， just to be clear， full disclosure， I mean。

 this could take forever to terminate。 I mean， it's fine hyp。 It could take a long， long， long。

 long time。 Okay， Two reasons。 First reason is there's just a lot of prices you have to maintain right。

 So for each bidder， there's n bids。 There's two to the M possible bundles S and you're only incrementing one at a time。

 Okay， so could take forever to get these high enough for to be meaningful。 Okay， in practice。

 of course， youd increment lots of bundles at the same time。😊。

The second reason why there's no guarantee of quick convergence is that in general。

 this could be an NB hard problem asking the seller to find the revenue maximizing allocation。

 but whatever， I mean， we're doing this as sort of a proof of concept at the moment。

So it's going to converge to a well maximizing allocation that doesn't contradict any NP be hardous results we know for that problem because this need not be efficient。

So it converges to a welfare maximizing allocation。

 though we've now seen many cases where getting the allocation right with an ascending auction isn't necessarily the hard part。

 It's really getting the payments right。 And again， we need that。

 if we want to expose set of compatible implementation。 So what about the payments。

 And here we will say something only under the gross substitutes condition， okay。So。

If the Vs so remember this thing， property one is true， whatever the V is。

If the VI is satisfied the gross substitute condition。

Then in exactly the same way that in our unit demand option， so what's going on in general。

So Crawford Noer， just to remind you， not only did it converge to a well rise equilibrium。

 but it converged the lowest well rise equilibrium。 Again。

 under the unit demand assumption that coincided with the VC G payments。

And so in the same way that unit demand was the magic condition that allowed the coincidence of the lowest O rise and equilibrium and the VC G payments for these bundle pricing options。

 not unit demand， but gross substitutes is the magic condition。😊，That has。

 there is a notion of a lowest competitive equilibrium with gross substitute valuations。 And that。

 again， coincides to the VC G payments。 Okay， and this as like this will converge to the lowest competitive equilibrium。

 So under this assumption， you do actually get the VC G payments。

So a picture you might want to think about。Is。So you can imagine the world that we had the entire last three lectures on。

 which is the item pricing world， which is for each item， you maintain a price。

 If somebody gets a bundle of items， you just add up the prices in the bundle。 Okay。

 that was the last three weeks。 item pricing also called linear pricing。And so what do we see。

 We saw， well， if you just want equilibrium to exist at all。

Then you have to restrictumulizin equilibrium。Then you have to restrict attention to gross substitutes valuations。

And if you want a coincidence。Between rise Elibria and VCG payments。

 you have to restrict further to the unit demand case。

So here we have existence of Woaz in equilibriumria。We proved this last week。And then here。

 we actually have。The lowest equilibrium equals VCG。 Okay。

 this was a pretty hard proof that we did in week2。Okay。

And so what I'm saying is that if you enlarge the space of auctions from just item pricing to these bundle prices。

 you get the same picture， but sort of zoomed out。So， it's bundle pricing。Now。

 existence is no longer a problem。 existence of this competitive equilibrium。

But if you want to converge to a VG outcome。Then you want gross substitutes。

So lowest competitive equilibrium equals VCG。So for item pricing。

 gross substitutes is sort of the threshold of equilibrium existence。 Okay。

 but it's actually too far to make it easy to compute the VC G outcome in an ascending way with bundle pricing。

 gross substitutes is the frontier of attainability of conversionverg of VC G outcome with simple ascending bundle price options。

 So again， as I've said， it's amazing how many different properties simultaneously gross substitutes is really kind of the limit of where you can get nice properties。

 So here we're seeing yet another one。 So I should say。😊，So you get asked about the converse。

 So we talked about last week how in some sense， gross substitutes is the maximal class so that you get existence of as equilibrium。

 So you could ask the same question。 I it the maximal class where you can get V G payments within ascending auction almost。

It moralally basically yes， although strictly speaking。

 a slightly weaker condition is the one that's necessary。Some of me just say and almost。Onlyly yes。O。

And， you know， so as far as， you know， how to people， you know， right So。

 so the theory starts breaking down at a certain point。 But， of course， the problems don't go away。

 Okay， we do have comm auction。 We want to solve them with ascending implementations。 You know。

 maybe hopefully gross substitute sort of holds， But it's not totally clear。 So you might ask。

 you what parts of this theory to people help people build on。And so we talked about this， you know。

 last quarter。 You can go read the notes if you want to review it。 But just， you know。

 a couple points。 So first of all， one thing you can do is you can just stick with basically the Crawford Noer option in effect。

 Okay， or just assume there are substitutes， I guess the Kelso Crawford option。

And even if there are gross substitutes valuations， we know it's not incentive compatible。

 We know there's incentives for demand reduction。 but you could hope that it works good enough。

 And really for the 90s， that's what people were doing。 so they knew it wasn't perfect。 empirically。

 you'd see evidence of demand reduction。 But it wasn't a disaster。

 And with billions of dollars not a disaster was kind of a pretty good， pretty good baseline。

 So people were okay with that。 And conservative in the 90s。 And honestly， the last 10 to 15 years。

 there's been an enormous number of competing proposals and designs about how to incorporate this package or bundle bidding in common auctions。

 And it's been done in a limited way and in different ways in different countries。

 And so there's two reasons there's two main drivers for why people trying to incorporate bundle or package bidding。

 the first is actually if you' just don't have substitutes at all。

 if you have compliments or synergies between different items。 then there's this exposure problem。

 we've talked about on occasion。 So you really want to help people vulnerable to exposure problem。

 The second thing， although I think this is a less important。

Point is you might hope to reduce incentives for demand reduction also by allowing package bidding。

 say even if people had substitutes valuations。 But， you know， I think the， you know。

 the kind of arguments， the debates continue about the right way to do this。

 And there's no consensus。 I'm not seeing that they'll be a consensus soon。

 So this is very much the kind of stuff People who design options for a living struggle with。

So that concludes everything you want to say about ascending implementations。 And for now。

 at least substitutes any questions， any of that。So I want to warn you。

 I'm pretty sure we're not going to see another ascending implementation for the rest of the course because now we're going to look at slightly harder problems。

 We're essentially no ascending auctions with any kind of guarantees are known。

 as's basically an open question for the rest of the scenarios we'll talk about。

 It's sort of open other reasonable ascending auctions from them。

 case that's something to keep in mind。Okay， so that concludes part one。A the class， part two。

We're going to go a little bit beyond these tractable special cases。

 and tractable means at the very least polynomial all time welfare maximization。

 So now we're going to look at scenarios where we lose that property where it's NP hard to do welfare maximization。

 As we'll see， as soon as that happens， there's a host of problems that arise for the mechanism designer okay。

So。Let me take you one step。 What would seem to be one small step beyond gross substitutes valuations。

 Okay， sort of the next level of generality。So it's going to be submodular valuations。

So this will be our scenario six。So evaluation。So against the set function。So it's a modular。And。

I think everyone's seen this definition last quarter at some point， at least on the homeworks。

 if nowhere else。If it only is。So here's the picture you won' to have in mind。

 okay so here's the entire item set。Here's a bundle， small bundle， here's a bigger bundle， tea。

 and then there's an item which is outside of both。Okay， I want to ask the question。

 what's the marginal value of requiring J， given you already have some stuff。Okay。

 and so modular just says the marginal value of more stuff is less the more stuff you've already got。

 okay， diminishing returns。So。If you already have T。And I give you J also。

 it's not as important to you， it's not worth as much。As if you merely have S。And I give you。Jy。OK。

So this is for all S and T and for all J。 The only interesting case is when J is outside of S and T。

 although it's true， no matter what J is。Allright， so the more you've got。

 the less you need more stuff， a module。So just real quick。

 So just to make it's easiest to start with a non example。

we were sort of plagued last week by valuation which the time we observed was non gross substitutes now we'll see it's also a non submodular。

 so the single minded bidder。So， let's say。You're in allwe or nothing。

You have value one for all the goods， even say there's only two goods。

 and you have value zero if you don't get everything。Definitely not the modular。Is the clear。

I it as' two goods？If I give you good A and you've got nothing， you're like。

 I still don't have everything。 So it's still value 0。 Okay， no marginal value。

 But if you already have one good， then the second good completes the set。 Okay。

 and that gives you the bump up of one in value。Okay。2。So that's exactly that's a non example of s。

 That's a violation。Now， intuitively， what you should be asking， you should be asking， you know。

 how does this compare to the last one to gross substitutes。 And in particular， actually。

 are they different， They seem to be trying to say basically the same。

 The intuition is very similar behind the two definitions。 But they're basically trying to say that。

 you know， as goods are taken away from you， Your value for what you've still got is only going up。

Right， so that was sort of true in the substitutes case， right。

 You lose goods and you still retain the old ones。 And this is also sort of saying， you know。

 it's kind of like， well， if I had， you know， think about J， if I had less stuff。

 then my marginal value for J would only be higher。So they only seem like the same。

So let's spend a little time understanding how they relate to each other。

 because they're defined very differently。O。So first。

The first claim is that submodular is at least as general as gross substitutes。

 so if you satisfy the G S condition， then you must be a sub modular evaluation。For some reason。

 this seems to have only been proven by Go spahetti in 99。But。That's where it's from。Okay。

 so this takes proof just because the definition of the two concepts are so different， right。

 so gross substitutes， it's not even directly a definition on the valuation。

 It's more the discussion of the demanded sets as prices vary。 Okay。

 so it's just defined in a totally different way than than a condition directly on the valuation the values of various sets。

So。How are we going to do this， So suppose you have a grow substitute dev valuation。Okay。

 and fix an S and a T and a J。 We want to prove it's a modular。

 So we want to prove that this holds review。All right。Somehow in our proof。

 we have to have some of these sets up here。Right， in our proof somehow， right。

 And pretty much the only thing gross subidies refers to is sort of your favorite bundles of given prices。

 demanded sets。So let's start， So to invoke the gross substitutes hypothesis。

 we need to start feeding at price vectors。 right， And we want sets that look like this。

 So let's start with T plus J。 So let me say， how could I get T plus J out of the gross substitutes condition。

How could I get that to be a favorite set。Well， actually。

 I guess this is sort of an easy way to do that。Right， so let's just。

Make the prices outside of T and J plus infinity。And let's make the prices inside。0。For starters。

 at least。对。So， step one。With the P。Equals zero，4 T， Union J， infinity。Otherwise。And remember。

 valuations are always monotone。Okay， so let's freeze disposal。Well。

 so now it's kind of an no brainer。 right， So definitely， you know， T plus J is a favorite bundle。

 you don't have to pay anything for it。 And any other good would just， you know。

 give you negative utility。 and need not be the unique favorite bundle。

 Maybe there's some good in T that you could care less about， but it's a favorite bundle。So t plus J。

So remember， this is the notation capital D。 So there's only one valuation。

 So there's no subscript I。 So this just means it's a utility maximizing bundle for you at the prices P。

Okay， so we want some comparison of T plus J and T。

So somehow we want to manipulate these price vectors so we get something about the set T， right。

So how are we're going to do that， We're going to do that。 We're going to say， okay， well。

 let's slowly make the item J。Less and less attractive。Okay。

So imagine gradually raising the price from0。On item J。All the other prices stay the same。

So think about， you're a bit with this valuation。 Think about how your utility for the different bundles are changing as the price goes up on J。

 Okay， So if it's a bundle that doesn't include O， So bundles that you know。

 so the whole universe is T union J at this point。 Everything else is obviously irrelevant。

So for a bundle that does not include J。 So for any subsets of T， you don't care。

RightBecause J is not a part of it。 That's the only price that's changing。 So it doesn't matter。

 So the utility stays exactly the same。For any bundle that does include J。

 the net utility is going down at unit rate。 Okay， because the price on J is going up。

 utilities going down。So there's going to be some point at which you like some bundle entirely inside T。

 some bundle that doesn't include J， at least as much as the bundle T plus J。

As T as J is getting worse， so is' everything else that includes J and everything inside to you staying the same so at some point there's this first point at which there's a tie。

Between a bundle inside T and a bundle includes J。So epsilon will call the price at which that tie first happens。

So step two。Epsilon is the smallest price。So that bundle that excludes J， that is a subset of T。

Is also in the demand set。Okay， so I'm gonna to call P epsilon。This price vector。

 which is epsilon on J， zero on T plus infinity elsewhere。So let me update the picture。

That's absolutely。Okay。So T plus J is still a favorite bundle。 right。

 We stopped epsilon just before it would go away。Okay。

 and now there's some other thing tied for that just inside tea。Alright， so the claim is。In fact。

 so there's some subset of tea inside this favorite bundle。 I claim actually T at this point。

 T itself has to be has to be a favorite bundle。 And now I'm actually going to use the gross substitutes condition。

 I haven't yet。Okay。So the claim is by Gs。Tee is a member。Of this demanded set。Okay。So why？ Well。

 maybe think about it by contradiction。 Okay， so we chose epsilon so that some subset of tea is a favorite bundle at this point。

 So if T isn't one of them， it means only strict subsets of T。

Are utility maximizing bundles at this point。 The only strict subsets of tea。

 so now jack up the price on J a little bit further。Okay， now， so what's happening again。

 So as you jack up the price on J， everything inside T is the same as ever。

 Anything that includes J is getting worse。 Okay， so epsilon is the point at which any bundle that includes good J is about to disappear from the demanded set。

 Okay， they're just about to go away， okay。So they all go away。 And if you don't have T。

 you only have strict subsets of T。But this violates a GS。Okay。

 we had a price vector where a demanded set was T plus J。

 The only price we increased was J G substitute says has to be a new demanded set that is a super set of T。

Otherwise， we increased only on J， and all of a sudden we want to relinquish one of the items in T。

 that's a violation of GS。Okay。So。That's good。We have T plus J showing up in the proof。

 we have T showing up in the proof。That's what we want。A relationship between。So， in fact， right now。

 we know exactly what is the difference between this bidder's valuation。

 This bids value for T and It's value for T plus J。Which is what。Absilon。Good。So because of this。

 lets remember。Also。T plus J。Is in this demanded set？Right，We chose epsilon。 So that was true。

 So that means the utility the bid gets from these two bundles is a tie。Okay。

So what's the difference between the prices？ Well， one has the good J。1 doesn't。

 The good J has price epsilon。 Okay， so the values have to differ by exactly the same amount。Okay。

Okay。Agreed。All right。So that's good， you've got two of the four。In the proof。

So how to get the rest well。Let's make everything in tea， but not as irrelevant。Okay。

So let's actually make。Let's now raise the price again。 So everything in T minus S is infinity。

And everything in S stays 0。Okay， and Jay stays at Epsilon。

Because gross substitutes because that only control things if prices only go up。 Okay。

 so we don't want the price to go down。O。Shu。So step 3。Raise prices on t minus S。

It's a plus infinity， called the new price vector Q epsilon。

Again to remember Jay's price remains epsilon。Okay， so what's obvious is that。

 the only things with finite prices are in S and J。

 so any favorite bundle at Q Eilon has to be a subset of S plus J。So only subsets。The S plus J。

R in D。A few epsilon。And actually， gross substitutes tells us something stronger than that。

Which is what you see。S something。We asked close， sort of kind of a dual statement。You。

 you may also get some strict subsets， but you can't only have strict subsets， exactly。

 So you got to have S plus J in there。Right。Why， well， what does gross substitute say， Okay。

 so you have this price factor。 P epsilon T plus J is a demanded good。

 I've only increased prices on t minus S。 And the condition says you don't want to relinquish anything that hasn't been increased。

 know， you don't want to relinquish any of S plus J。So。By Gs。As suppose Jay is a member。

Of the favorite bundles at this price vector。I don't know。 Oh， yeah。Yes， applying it to T。

 you're right。 We're not going to use that property， but you're absolutely right。Oh， I see。

 That's interesting， actually。Okay。Right， so I'm to write down the inequality we need。

 But I guess the equality actually holds。 So in particular， just from this property。

 the bidder likes S plus J at least as much as it likes S。 which is actually all we need。So you till。

For S plus J， and again， this is at the prices。Q epsilon is at least。The utility for S。

Just because that's suppose Jay is a favorite。 And again。The only difference between these two。

 as far as the prices is that the price overall here is exactly epsilon more。 Okay。

 so its value for S plus J must be at least epsilon more than its value for S it's inequality to hold。

Okay。So that completes the proof。Okay。So at least we're trying to get some understanding of the relationship between。

 In fact， even if you didn't care about submodular evaluations per se。

 this is something you'd want to know about gross substitutes evaluations。

 This is just a little bit I think， easier to get your head around as opposed to the definition of gross substitutes。

 Okay， so they're always submodular。 Good to know。Allright， and you may， you know。

 it would be totally reasonable to wonder at this point， if actually， they have the same definition。

So I'll leave it as an exercise to prove that if there's only two items， so in that special case。

Then， in fact， the two definitions do coincide。And as we said is。

 this is actually holding with equality。Do。こかで。Something's fishy， though， so I mean， it's not。

I think for sec。そして。I mean， it's not， I mean， gross substitutes doesn't imply that it's an additive function。

So。I have to think about it。I to think about it。It does seem like this crucial something thing stronger。

 but， but I mean， it's not， but I mean， yeah， I mean。

 gross substitutes include things that are not a， as we know。

So I to figure out exactly what this statement is。Okay， so when you remove the elements in t minus S。

 right， So if you use in the set， it is tied with the current。A7ty。Yeah。

 so you have to like increase that further actually get a die。Yeah。

 it's not but so we're in the proof。So I think it in this case。But so we argue， I mean。

 the thing that So here， here's the reason why it kind of seems。 Let's see。 So， I mean。

 T is one demanded set at this point， right。And then if I increase everything in t minus S。Oh， oh。

 I see。 I see。 I see。 I see。 Yes， The point is S plus J would still count。Yeah。

 so you need not have S。 Okay， good， good， good。 Yeah， All right， So gross which just says basically。

 so you might want to acquire new things。 You just don't want to drop old stuff。

So maybe once I sort of obliterate t minus S， used to be like， oh， I really want T。

And now I obliterate t minus S，' like， okay， well I don't want those。

 I still want S sometimes when the gross substitutes condition， but now I want J also。

So it could be that S plus J is the unique。 So once you pass to Q epsilon， it could be S+ Js unique。

Good。Good， yeah， thank you。Okay， excellent。So with m equal 2， in fact。

Vro substitutes is equivalent to submodular。Which is equivalent to just being some additive。

 meaning your value for both goods。Is the most the sum of your values for the singletons。 Okay。

 so that's easy， easy to prove。 So they coincide for two items。

 They do not coincide for three or more items。Okay。

So you can be so modular without satisfying the gross substitutes condition。

 Let me give you an example。Actually， a student basically gave this counter example for the exercise set。

 so I'm just going to reuse it in lecture。😊，So let me show you an example of what's called a budgeted additive。

Evalaluation。So say there's three items。And you have values for the items，1，2 and 3。

 and your valuation is additive， except there's some limit on how much utility you can have。

 on how much value you can have。 Okay， I'm going to cap it at 3。

So let's say that your value for a set S is going to be the minimum。

Of three and the sum of your singleleton values。Okay。Makes sense。So you can't get6。

 So if you get all three items， it's still just three。So this is submodular。

I'll leave you to check this in the privacy of your own home。It's not hard， I mean。

 basically just the contribution of an item， the marginal value is always the same except when it exceeds the cap。

 in which case you know you only get up to the cap and the more other items you have。

 the closer you are to the cap， so the less the marginal value so that's the proof。

And to see that it's not gross substitutes。need to show you the price vectors。So consider。

So how about the price factor？On ABC。One half， one half， two。

So if you have this valuation and those are the prices on goods， ABC， which do you want。

 what maximize your utility。あ对。Don't forget about the cap， right。

So if the prices are strictly positive， you never want all three。Right because。Right， so the。

 the highest this can be is 3。So remember， the prices you pay are not capped。

 Like you just pay the money no matter what。 And then when you computing the value part of your utility function。

 there's no reason。 Once you have the third good， there's no reason to have more。

Once you have the first two， there's no reason add the third， A And B， exactly。

 so A And B will get you a utility of two。 And that's the best you can do。

And then what if we go instead？What if we raise the price on good B？Then what do we want。Yeah。

 then we just want C。T。For utility one。Again， because the value is capped again， you。

 you might think we want to add a because the value is one and the cost is one half。 Again， remember。

 once we have good C， the marginal value of a is 0。 So the positive price， you don't want to add it。

So that shows explicitly that sub gross substitutes is a strictly stronger condition than submodular。

Okay。So in other words， if you sort of remember our picture。 So now things are looking like this。

And then we have this sort of interesting subclasses of gross substitutes so we have unit demand。

 we have sort of identical， we have additive and so on。

 this is how the hierarchy is getting built up。Okay。Alright， so any questions about that。

 So definition is a modular strictly more general than gross substitutes。 Okay。

 so it's more ambitious to do anything with the modular evaluations。

And life was already getting a little complicated with gross substitute。Got be ready。Allright。

 so now。I want to talk about welfare maximization。Okay。

 so the same problem that we were obsessed with last week in the second lecture。We worked hard。

Usual lipoid algorithm。We did it。 We grow substitutes。 What happens with sub modular， okay。Well。

 we can't do as well。 Okay， we can't get polynomial timemo from maximization and polynom in exactly。

Okay， so an easy facts。Another optional exercise。If you have submodular evaluations。

Can't max welfare。Let's just say empty hard。To maximize warre。And so， one easy reduction。

Is from partition。 Certainly， there are stronger， negative results known。

 But if you just want to establish MP hardness， that's an easy way to do it。Now。

 we talked last week about， you know， when you with these sort of you know， combatorial evaluations。

 when you talk about polynomial or and be hard， you have to specify what's the input size。

 So it should be a little bit more precise here。 But， I mean， this this hardness result is so easy。

 Like it never comes up basically。 So this is already true。 if you just have two bidders。

And if they just have these budgeted addeditive evaluations。

 and so these you can just write down explicitly as input。 Remember what we're worried about。

 we're worried that the input size has is 2 to the M and trivializing the problem。

But with these special valuations， obviously， the input size is going be n plus error n times n。

 I guess， K polynomial and N and M。So even for that special case。

 where you can really talk about polynomial and impize in the normal way， it's already NP hard。

So this if you like， you know， if you believe in P equal to N P。

 that says we didn't need this example， right， We'd note just from this fact that actually there's a difference that sub modular is strictly more general。

 Okay because there's things we can do for gross substitutes that we can't do for sub modular。Okay。

So。Time to take a step back。 Zoom out。And like， recall the forest。 So of recall what。

 what we've been after。In the course so far。So。There are these three things we wanted， okay。

 which is。Sometimes I call awesome auctions， right。And so he said， well， okay。

 we want the best case scenario along every possible axis。 Okay。

 the first axis being the incentive guarantees， we want them to be as strong as possible。

 So for direct revelation mechanisms， which is now what we're talking about。

 it would be dominant strategy and set accountability。

We want the best imaginable performance guarantee， assuming we care about welfare maximization。

So that was the second one。 and then we wanted tract ability。 So at the very least。Polynomial time。

 ideally， somehow simple and natural on top of that。 Okay， and for the tractable special cases。

 we are getting all this stuff。So。Okay， so now what are we hoping we might be able to get， Okay。

 so from this N B hardness result， we conclude that， well， you know， forget about one。Right。

2 and 3 already。 we cannot attain at the same time， assuming assuming P is not equal to。Right。

So that's what we just learned， even for sub modular evaluations， two and three are in conflict。So。

Right， so relaxing one won't help us with that problem。 right， So that's not a way out。

 So what we're going to look at， is're going to look at relaxing，2。Okay。

So we want to approximately maximize welfare。So in some sense。

 these will be approximately awesome auctions。And this is going to be the subject of this week and next week。

 Okay， so that's part  two of the course。 Okay， so we're going to still be hardliners about how strong an incentive incentive compatibility guarantee you want。

 We're going stick with Dc。And then subject to that， we're going to ask。

 to what extent can we get two and three simultaneously？So now I want to warn you。

So this part of the class， this week and next week。

 will probably have the most complicated mechanisms in the class。 Okay。

 the good news is there'll be D。 So like if you actually had to play in one， it wouldn't be hard。

 You have a dominant strategy， which is just direct revelations。 That's not a big deal。 But， I mean。

 these will be kind of almost all just purely theoretical constructs。

 proofs of principle of tractability。 Okay， so somehow insisting on D， really， first of all。

 these impossibility results。 There's lots of stuff you just fundamentally cannot do。

 probably we' improve those impossitibility results， but I'll survey them。😊。

And the stuff that you can do， which is what I'll focus on。

 You have to work really quite hard to do it。 Itll probably be some of the more intense algorithms some of you have ever seen。

 actually， okay。So just， brace yourself for that， especially next week。So then， you know。

 after a couple weeks of realizing， you know， how much we have to suffer。

 if we insist on dominant strategy and compatibility， we'll take a step back and we'll relax this。

 okay。And so in part three of the course， we'll look at relaxing this to undominated strategies。

 We'll talk about that a little bit， and we'll talk about Bay Nash implementations， okay。

So then the good news is we'll be getting kind of， you know。

We doing much better with respect to the positive results。 Okay。

 we'll be getting better approximations for a wider class of problems。 The mechanisms will still。

 though， mostly feel like theoretical constructs。 they'll still be pretty complicated。So in part 4。

 what we're going do is we're actually going to take the simplicity constraint as the hard constraint。

Okay， and so we're going to say， let's insist on simple options。Which， though。

 may not be very easy to play as a bidder。 Okay， so the equilibrium set may be complicated。

 at least the mechanisms are simple。 And we're going to ask， you know， how well can we do。

So what kind of approximations do we get at equilibrium？

And then time permitting at the end of the course will switch to revenue maximization。

 which sort of has a different flavor。Okay， so that that's sort of the high level comments about where we stand。

Any comments or questions？What的。All right。Any other warnings that I owe you？Okay， good。All right。

 so that's where we are。when can we get one through 3， For example， for some magical evaluations。

Well。Let's begin with an easier question， which is， when can we at least get 2 and3。Okay。

 because at the very least， you know。You got to figure people have been thinking about that for like 30 or 40 years And the half。

 That's just approximation algorithms。 the literature and approximation algorithms is very。

 very rich。So that'll draw some lines in the sand of what we might possibly hope to accomplish。

All right。So prere。How about just two and three？Now， of course。You know， ultimately。

 we want to extend these approximation algorithms into instead set of compatible mechanisms。

 But let's， just do it one step at a time。Allright， And so the good news is， is actually。

 so the news is quite good for some modular evaluations。 If we just want polynomel time。

 good approximation。 It's simply be hard， but it turns out we can get quite good constant factor approximations。

 Okay， actually， something I've already shown you。😊。

Already is a good approximation algorithm for some modular welfare maximization。 Okay。

 so that's what I want to conclude this first lecture the day with。So theorem。Yeah。So again。

 a positive answer to this question for scenario6 mod evaluations and。

This is a recent result just from about a year ago。Here's what we're going to do。 Okay。

 We're just going to run the Kelso Crawford auction。And。

 I'll review the key points of it in a second。 But that was the one that worked for gross substitutes。

 So Crawford Noer was for unit demand， where bidders just bid on one good。

 And then we had gross substitutes where they could bid on a bundle。 But otherwise it was the same。

And so we were talking about all of that auction seems totally engineered for gross substitutes because basically。

 that's the condition you need for people to not want to relinquish items and terminate a laro and equilibrium。

lah，h，lah blah， blah。So we're going to go ahead and run that auction。Okay。

Even though the bidders will have sub modular non gross substitutes valuations。

 we're going to run until completion。 And we're actually going argue that that completion is almost optimal。

 It's not optimal because they may not be what ro equilibrium， but it's within a factor of two。

So of all bidders。Have some module evaluations。And bid sincerely。 remember。

 we're not the point here is， the point here is just to have an algorithm。

 I'm not talking about incentives。 Okay， The point is just an algorithm。 Okay。

 so I'm just going to simulate sincere bidding for these bidders to compute an allocation。

So if everybody is similars evaluations and。Bid sincerely。In the Kelso Crawford auction。

Then I claim it terminates。With an allocation。With welfare， at least half of optimal。

So with gross substitutes， you get 100% of optimal because you'll converge toos in equilibrium here。

 there are no wwas in equilibrium。 And we know it's empty hard to compute an optimal in anyways。

 but it's going to terminate with something within 50%。Now。

50% maybe isn't like the best approximation factor you've ever heard。 But， you know， frankly。

 most N hard problems， you can't get a constant factor at all in polyial time。

 including for lots of welfare acquisition problems。 So this isn't that bad if you。

 if you really care about sub evaluations， there are other algorithms， which do better than 50%。

 you can get， I think things 63% or something like that。

 And that's one of the projects if you're interested。 Okay， so there are somewhat better algorithms。

 But honestly， you know， again， this， as these things go， we should be happy with this。

 for worst case guarantees they don't usually get too much better than this。Okay。Allright。

 I should also say， historically， people usually will know and teach a different older to approximation algorithm by Lehman Lehman and Nissan。

 That's a simple greedy algorithm。 and that's outlined also in the exercises okay。But I wanted。

 I wanted to do this one because we basically already know the algorithm。

 and it's kind of cool that it just works。All right。

So let me just let me mention a couple salient points of the Kelsso Crawford auction and then think about what you don't remember and ask me and I'll elaborate。

OkayBut so here here's sort of the key， here's the key points。Right so initially， you know。

 all the prices are 0。 And then every time somebody bids on an item。

 the price gets bumped up by Epsilon。 One really important property。

 I made a big deal deal of this at the time is that there's no bid withdrawals。O。So if you。

 if you're the tentative winner of an item at a given price， whatever happens with the other items。

 it doesn't matter。 Okay， I'm not going to let you relinquish this item。 Okay。

 that's by definition of the auction。 Okay， that's what motivated the gross substitutes condition in the first place。

 Okay， we wanted to argue that that's not a bad thing that people can't relinquish items because they don't want to anyways。

So that's an important property。With sub with submodular evaluations。

 people might actually want to withdraw their bit O， because they're not gross substitutes。

 but we're not going to let them， okay。So in particular， if you think about it。

 remember an important property here was that condition in the waz andiclibria that unsold goods have price zero。

Okay， how could it be that you didn't get get sold， It has to have meant that nobody ever bid on you。

 because again， if someone ever bids on you， then the only thing that ever happens is you exchange hands between bidders that you never become unassed。

 So the only way you are unsold is to have price 0。

And we're going to use that in the proof of this theorem。Okay， so what else？And then， if I。

So then what the bidders actually do？Most of a given iteration。

 some bidder has some current set of items SI， we ask if the one's any new ones。And if it does。

 we say， tell me your favorite set。 Okay， the items T I you want to add to the ones you've already got。

 And then when it says， I want these goods T I， you take them away from the current owners。

 You reassign them to I， and all those prices get bumped up by Epsilon。

And that's the Kelsso Crawford auction。So i bidds for best set。TI of new items。Given。Of course。

 the current set of prices plus。The items S I。It already has。Okay。

 so it's doing some agon max over the items set U minus the items S I that it already has。

 And among all those subsets， it picks the best one。 utility maximizing one。Okay。

Does anyone want any more review of Kelso Crawford， Is this enough。This makes sense。Okay。Alright。

So we're going to prove that this terminates with a true approximation for sub modular evaluations。

 a proof。So okay， right， What am I proving， Let me tell you what I'm proving first。

So here's an important lemma。And it's going to sound weak， but actually， this is I mean。

 this is really where the s modularity condition is important。So at termination。And again。

 we're always assuming sincere bidding。All bid utilities are non negative。Okay。

So this should feel kind of weak。 So for gross substitutes。

 we were saying it was a warazan equilibrium。 So we were actually saying that every bidder has its best bundle。

 utility maximizing bundle。So all I'm saying is now is now they might be bundles that ones a lot more than the one it's got。

 but at least it's not paying more than its value for what it has a termination。

And let me remind you， actually， when I kind of showed you the distrous things can happen in the Kelso Crawford auction。

This this was violated。 So what we did is we ran the Kels Croawford auction with a single minded bidder。

 One of these all or nothing bitters。 And if it bit sincerely， it actually wound up with utility -1。

Okay， we saw that last week。 So there are definitely to be evaluations where this doesn't happen。

Okay。So。So proof。And this is really where sub modularity of evaluations gets used。Gets used， yeah。

All right， so the invariance。Will be the following。At all times。In this algorithm， for all bidders。

Consider a bitter eye currently with items S。For all subsets of its items。

Bitter eyes value for that subset of items。Is at least the price it's paying for those items？不证。

So we're gonna prove a stronger statement。 Okay， for the induction。 right， So what I want to be true。

 I just want to be true that any the algorithm， the bundle that a bidder actually winds up with。

 It's not paying too much for。 Now， remember that what's tricky about this auction is， you know。

 you bid for some bundle when it looks really good at the time。

 But then people take these items away from you。Okay。

 so the problem is sort of at the end of the auction。

 You might wind up with this bundle that you didn't bid on。 You bid on something much bigger。

 And all these pieces were sort of taken away from you by other people。

 So that's why I want this invariant that applies to every single subset of the items I currently have。

 because any of those might be my allocation at the at the end of the auction。行。I this clear？Right。

So S I is what I has right now。 There are some prices。 I want to say。

 whatever subset it winds up with， it's going to be fine。 It's gonna have non negative utility。

 right， That's what I want to prove。So base case， everyone's got nothing at the beginning。

 So this is fine。Also， for the inductive step， I mean， almost all the work takes care of itself。

So consider an iteration。So suppose I。Has S I。And bids for new items。TI。Okay。Now。

 most of the invariant is just going to be fine， because I've made it so strong， right。So which。

 which bid， who is the only bidder whose invariium might get screwed up。Right。

 so bitter eye is taking items away from everybody else in this iteration。Okay so it says TI。

 I want those， and it takes them from people。So suppose you're some other bit of K different than I。

 Okay， so what happens， right？ You had this bundle of goods。

 You were perfectly happy with whatever subset you were going to get。 And now some were taken away。

 but the prices on what you still have are unchanged。

 So you're still going to be happy with whatever subset you might get。😊，Okay， no problem。So。

Vance still holds。For K not equal to I。Okay， so we just said to show that I didn't script the invariant by acquiring these new goods。

 T sub I。 Okay， that's， that's the。That's the key point of the proof。All right。

 so let's actually do what do that。All right， so for I。Let's proceedd by contradiction。Contra。

Add diction。Suppose there is some set，'s called it A。In its new bundle of goods， SI Union TI。

So that the prices。A strictlyly bigger than its value for it。Okay。So here are the old items。

 here are the new items。 in general， this set A， as far as we know， might span both。Okay。

I'm going to call the subset of the old items in A X， and I'll call the new items in A Y。

So x is just a projected on the SI。 Y is a projected on the TI。Alright， so。

Does the inductive hypothesis tell us anything here？いそ。So why is the new stuff？Right。Agreed。

 definitely agree， A can't be an SI。And， in fact， more generally。

 the part of a that projects into S I， namely X satisfies this condition。

Because everything in SI satisfies this condition。So by IH， we have。VI of X。At least this。And yet。

 by assumption。If we add in all the elements to y。Ie， you know， X union。 remember。

 x union y equals a and A is our bad set。 The inequality flips。嗯。This is where we stand。

So now what I want you to imagine， imagine we start with a set X。Okay。And we sort of track， you know。

 both the left hand side， the value and the right hand side， what you're paying。

 track both of those quantities as we add the elements of y， the items of y in one at a time。Okay。

 so both are getting bigger， but possibly at different rates， okay。So， in particular。

We start with the left hand side being bigger。 So say there's like， you know， L items in here。

 We're going to add them one at a time。 Theyll be， you know， at some point。Right， all of a sudden。

 this flips from there to there。 Okay， there's some item at which all of a sudden。You know。

 this holds。So let's just rename so that y has the items1 through L。Consider the first time。

Where it flips。So why would it flip？Right， so when it flips， okay。

 so if this holds and suddenly it flips， well， I guess this didn't go up by as much as this。

So I guess the marginal value of adding that item over here was less than the price that's being paid for it。

That is。Okay， so again， we look at this is just the marginal value of adding J。

This must have been less than P J。Great， that's the only way this thing flips。Okay。Well。

 now this is starting to look kind of in the wheelhouse of some modularity。Right。

 we're talking about sort of marginal values of adding one extra item。 What does the modularity say。

 It says adding an item to a bigger set。Is even less useful than adding it to a smaller set。Okay。

 so what we're having here is that adding J。So this set。Is not very useful。

 And that's going to be even more true。If we think about adding it to every， you know。

 everything other than it in a。Let me say that again。So by submodularity。Let's think about。Oh。

 I don't want to do that， even wait home on it。Yeah， okay。

 So let's actually expand all the way out to S I Union T I。

 And let me remind you the definition of T I。 We asked this bidder。 We said， look。

 you've already got S I。Given that， what else do you want and give me your best answer。

 what would maximize utility among anything else you might pay。 And they said， T I。Okay。

But let's think about it。 like like， why not say T I minus J instead， right。

 So like even if you only have this very small subset of goods， J doesn't really do you much good。

 right， That's sort of less than the price you're paying for it。

 So why on earth did you want to add that to this much bigger set S I Union T I minus J。

So by submodularity， the marginal value。Of adding J。 remember J's in T。Don't forget。Ze。Okay。

 so the marginal value of adding J to everything you've got。This is even smaller than this。

 So this is also less than P J。But then that means T I wasn't your utility maximizing subsetstantive items to add。

 Okay， T I minus J would have been an even better set to add。Because if you deleted J from TI。

 your marginal of value wouldn't increase by very much。

 but the price you pay increases decreases by even more。So then， T I minus J。Better to add。Then TI。

 so there's our contradiction。Okay。Jo is a key limit。 That's somehow like the。

The hardest work in this fact of two proof。 right there。So that's great。

 Okay so people don't necessarily have their favorite bundle。

 but at least they have non negative utility at the end of the day。 And as I said。

 we know that's not true。Without some modularity。All right。So， here's a corollary。

And this is sort of the consequence of this lemma that will be directly useful when we prove the approximation bound。

And the coral area says， look at the prices。At the end of his auction。

So suppose when we run the Kelsor Crawford auction， the final prices are P。

And the final allocation is S1 through n。Then the claim is the some of the prices of termination are bounded above by the welfare of the allocation。

So then some over PJ， JNU。Is it most the welfare？Aieeved。Okay。So again， it's not。

 it won't be clear why this is an interesting statement until we prove the theorem。

 but this is what we'll use directly。 So proof。So let's also recall。

 and this is sort of a key property at the Ksler Crawford a。The only way。

That good goes unsold as if it has price 0。So how am I going to use that now？Well， sum of the prices。

Overall。Equals the sum of the prices of the goods that were sold。Because the remainder is 0。

 One way I can count up the some of the prices of the goods that were sold。

Is by just iterating over all the bidders and looking at what goods they got。

That's just iterating over the sold goods。 And by the key lemma。Bitter by bitter。

 This is bounded above by the welfare。Of that bitter at termination。Okay。That's cool there。

We can lower bound the welfare achieved by the final prices of all the items。

So why does Kelso Croawffer terminate with a two approximation？

So this may give you flash flashbacks to the price of anarchy segment of last quarter's course。嗯。So。

 let P。And S1 through SN B as above。So final prices is， final allocation。

And we want to compare ourselves to the optimalim allocation。

We want to say we're almost as good at termination。

So let S1 star through S N star be the optimal allocation。 Okay， well for maximizing。Now。

 at termination。Because of Crawford auction， nobody wants to add any new stuff。Okay。

 so in particular， if I'm a bidder， I've got some items and maybe sort of there are these items I'm supposed to have in the optimal allocation that I don't have them。

But I decided not to bid on them。Okay， why not， I guess it would have made my utility worse。

So that termination。Yeah。For all I。If I did a cost benefit analysis of grabbing the items that I have in the optimal allocation but that I don't have now。

 it would come up negative or non positive。Okay， so if I do the thought experiment， I say， well。Now。

 what would be， what would be my。Extra value getting those goods that I don't have in the optimal allocation。

Well， I guess that would be at most what I'd pay。是你给。So strictly speaking。

 because of the epsilon stuff， there's a， you know。Up to。An epsilon error for good。But whatever。

Among friends， forgive the asil。And let's just go ahead and be sloppy and never bound that by。

The some of the prices of everything I'm supposed to get in the optimal solution。Okay。Okay。

So that's just the termination condition。Maybe even sloppier， actually。

Let me make this even more true by making left hand side even smaller。So by monotonicicity。

I can lower bound this by just the welfare that player eye gets。And the optimal allocation。

So that too bad so sorry， let me put that on top。So basically， I started， I had this one inequality。

 which is just immediate from the termination condition of Kelso Crawford。

 I declined to try to get these bids， these items from S star minus S。 That's where this comes from。

 Now， I'm doing two sloppy inequalities。 Here's the first one。 I'm just throwing in more prices。

 which can only be positive。😊，And then over here， so that just makes this bigger。And then over here。

 I'm lower bounding this。Because VI is monotone， remember， free disposal。

I'm making this only more true if I replace this by V of Etorra。So summing over all bidders。

 So again， remember， this is true for each bidder。 No bidder wanted to grab any more items at the end of the auction。

So we have。Some of the optimal allocation welfare terms。Minus the sum of the algorithms。

Welfare terms。At most， some of her eye。Some of her。The goods that I gets in the optimal allocation。

Which by the corollary。Let's remember， our corollary says that the final prices are bounded above by the welfare of the final allocation。

So that's what I'm using here。 So this is just a subset of the final prices。

 So all of the prices are only bigger。 Mc coroll says I can bound this by the welfare。

And now I just move this over， divide by two。And we get that the welfare at termination is at least one half of the optimal welfare。

Okay。So again， so to sort of jog your memory of how a lot of the price of energyarch analyses worked。

 which is basically the template we're copying here。 you halt with some kind of equilibrium。 I mean。

 there's no formal equilibrium concept here， but there's this termination condition。

 which has the same flavor。 Nobody wants a new items。

 So you can think of that as like an equilibrium condition that generates an inequality for each bidder relating its utility。

 well it's welfare at the algorithm to that in an optimal allocation。

 we get one of those inequalities for each of the bidders。

 and then we combine them and rearrange and then the key lemmo was just saying that you know when we look at all of those quote unquote equilibrium conditions。

 we have this error term， which is the sum of the prices。So if that error term was too big。

 we'd be hosed， but we use s modularity to argue that it's not。 And actually。

 you can relate that back to the welfare of the final allocation， which gives us the factor， too。

Alright， so I think it's time for a break。 So I'll see you in about 10 minutes。

