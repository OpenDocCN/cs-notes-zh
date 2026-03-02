# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p17 -17-Frontiers in Mechanism Design (Lecture 17a_ Demand Reduction in Multi-Unit A -BV1fNVNzhEBg_p17-

Alright， so let's let's go ahead and get started。 So the first of the two lectures is going to be the culmination of part 4 of the course。

 So remember this is where we insist on simple auction formats。

 and we're asking for which formats and under which conditions， for example。

 in the valuations are equilibrium guaranteed to be good。

 the price of anarchy guaranteed to be close to one。

 So in the last so we've had three lectures on this topic so far。 and for concreteness。

 all three of those have been on exactly the same type of auction formats。

 simultaneous single item as。 We've looked at both the second price version and the first price version。

 and it's been convenient to be concrete to develop our toolbox。

 And now we have both extension theorems and composition theorems to prove bounds in the price Banarchy。

 But what I want to emphasize in this lecture is that our toolbox is rich enough to cover our other kinds of interesting auction formats as well。

 And so the first topic for today's lecture we're going revisit sort of an old friend and apply the same toolbox to prove some interesting new bounds。

 And then I'm going show you。Basically， how you can go beyond the smoothness framework and cover even more general settings than we've done so far。

 So both of these results are just from the past， you know，3 to six months or so。 So we're really。

 all of you are really， you know， completely up on the cutting edge。Okay。

 so let's go to the first topic。 So the price of anarchy of demand reduction。 So let me remind you。

About both a setting and an auction format and incentive issues that we were discussing in the very first part of the course。

 so this was in lectures， I think three and four。So this was at the time we were calling it scenario number four。

So this was where we had identical items。Okay。And bidders are not necessarily unit demand。

 They want many items， but the assumption in scenario 4 is that the valuations are downward sloping。

 Okay so the marginal value of each additional item is at most is is not increasing。

 is decreasing as you get more and more items， okay。So downward sloping。Valuations。

 and such a valuation is specified by the marginal values。Of getting a jaith copy of the good。

 Jaith good。And so downward sloping just means that the marginal values are only going down。Okay。

So this is the special case of the gross substitutes scenario in when you have identical items。

 so gross substitutes was the extension of this to heterogeneous items。

And let me just remind you a little bit about this scenario。

So let's recall what the welfare maximizing allocation rule is because it's very simple in this setting。

And we used it back in the day and we're going to use it again today。So。

So suppose you knew the actual marginal valuations。How would you allocate the M items。

 how would you split them up amongst the n bidders to make the welfare as big as possible Well remember this is just a simple greedy algorithm so you would just sort the marginal values。

 you basically just sort of right you have n times M numbers， n bidders。

 and marginal values for each of them of those NM numbers you would look at the highest M of them and those would correspond to the allocations of the M items that you've got。

So really， all you do。You'd sort all the MIJs。Okay， and depending， it may be that。

 you one bidder gets all of them， that's fine。 And maybe these are split amongst the bitterders in different ways。

So sort all the marginal values。Alloccate to the highest。En them。

And this makes sense because valuations are downward sloping okay so because the mus are only going down as j increases。

 this means that by giving allocating to the highest mu I Js。

 each bit I will get an allocation corresponding to a prefix so the highest 10 mu I Js for a corresponding bitter I will be those with J equal1 through 10 so that's why this makes sense downward sloping is important for that successfully maximized welfare。

Okay so this is the allocation rule so suppose you wanted to turn this into a mechanism how would you do it Well so you know we're back into settings that we understand well so if know if you could just do a direct revelation mechanism you could just run the VCG mechanism that would be fine our main concern when we talked about scenario number four was at the time we were concerned about ascending implementations so yes there's the VCG mechanism but we worked hard to develop this other ascending a the clinching a which at termination assuming sincere bidding terminated with the appropriate allocation and the VCG payments okay。

So the clinching auction what was the main thing we studied in scenario four a couple months ago。

And one thing I want you to remember about either the VCG mechanism or the clinching auction。

 whichever in this setting is that different items are sold at different prices。

 even though all the items are identical， the clinching a， for example， you know we had this price。

 the price went up over time and as the auction proceeded you would as a bidder you would clinch items successively at higher and higher prices so you'd end up with like 10 items。

 you'd pay something for item1， something larger for item2。

 something larger for item3 and so on so to get dominant strategy and seat or expos and。

 we had to sell the items for different prices so that's what we did in scenario4。Now。

 to motivate the clinching auction， what I did is I actually said， well。

 let's do something even simpler。 and see where it goes wrong。

 And where it went wrong is what motivated the VCG mechanism。

 So even simpler than the clinching auction， the VCG mechanism would be， well， you know。

 all the items are the same。 Let's just sort of draw a supply curve and draw a demand curve till they cross and set the price where they cross okay。

😊，So in other words。In addition to the clinching auction， our punching bag in that lecture。

Was uniform pricing？Which was if you're given bids， so I'm going to call the bids BIJs。

You just sell to the highest or the top。BIJ is。Add a price。Equal to the m plus1 highest bit。Okay。

So in other words， so this mechanism has exactly the same allocation rule as VCG。

 as we said over here， given the BIJs， you allocate according to the highest M of them。

 but the payment rule is different and simpler so VCG， the clinching auction。

 you charge different things for different items here we're going to charge exactly the same thing。

If you're going to charge exactly the same thing for all of them， well inspired by the dickckerory a。

 one thing you might try to do would just be to take the highest losing bid and that sets the price for everybody else。

So this， I hope， is all review。Another thing we were sort of using to illustrateustra at this time This is also when we were talking about wall rise and equilibrium。

 And so you can think of uniform pricing is basically trying to implement the smallest well rise and equilibrium in a mechanism。

 So in this identical good setting， there were was in equilibrium。

 So that's just the price where the market clears。 Those are just going to be all the prices between the m highest and the m plus1 highest Bj。

 So this price corresponds to the smallest w rise and equilibrium。

 And we were just coming from settings while the lowest war in equilibrium In fact。

 gave us incentive compatible mechanisms， unit demand bidders。

 and we used this mechanism to illustrate that that doesn't continue to work when you have identical items。

Let me remind you why this doesn't continue to work， why this isn't incentive compatible。

 It's because there's something called demand reduction。So even suppose m equals 2。So again。

 the point of this example is just to show that in the mechanism where you use the welfare maximizing allocation rule and you use uniform pricing。

 it's not dominant strategy and Senate compatibleible you allow players to report downward sloping valuations。

 they have the option of telling the truth， but they're not going to in general。So why。

 well just suppose you have one additive bidder。And one unit demand bidder。Okay。

So bidter 1 is additive。 It gets three for each item that it gets。And bidder2 is unit demand。

So it wants one item for a value of two， and it has no marginal value for a second item。

So the claim is that the first bidder does not have an incentive to bid truthfully。

 so assume the second bidder does bid truthfully。So why not。Well。If。Bitter1 did bid truthfully。

How many items would it get？We get both， right。What would be the price for each one？Also， too， right。

 So there's sort of four， you know， if all the bids are truthful。 Well， in any case。

 there's four bids，4 B I Js， there's M goods， the top two win with the truthful bids。

 these will be the winners。 What's the clearing price。 It's just the highest losing bid。

 This is the highest losing bid， okay。And that's what happened。 The Bi one tells the truth。

 it would get six value， but it would pay to each for utility of two， okay。

Suppose instead that bidder one engages in demand reduction。 that is it replaces this with a0。 sorry。

 it replaces mu and2 with a0。 It says actually， I'll just pretend to be unit demand。

 and my value is 3。Okay。So now in the allocation， so now that the second things is zero。

 the highest two bids are the first unit bid from each bidder，3 and two。 So those are the winners。

 each bidder gets exactly one unit and nobody allegedly nobody wanted a second unit okay so the highest losing bid is zero in case we just give both goods away for free one to each bidder。

So then bidder1， it gets fewer items， only gets one， but it pays nothing。

 So its utility is three better than two。 Okay so that's demand reduction。 And it's real。

 And you see this in practice when people implement this auction。

 and sometimes they do Biders have an incentive to get fewer quantities than they would otherwise want because they wind up getting it at a much cheaper price。

 And so overall， it's a win okay。So number one。Would prefer one unit。At price zero。

 which it gets with a false report。Over two units。At price to each。

Which would give it only utility to。是。So that's a concrete demonstration that the uniform pricing mechanism is not decent because of demand reduction。

But now that we're in this part 4 of the course， you know， maybe we we're tempted to say， well。

 you know， so what， you know， maybe we want to use this anyways。 Okay。

 so now we have a toolbox for reasoning about mechanisms which are not truthful， Okay。

 which are not decent， where we don't even know what bidders are going to do。 Okay。

 but we don't we can't even solve for equilibrium。So maybe actually this simple mechanism， you know。

 maybe it's equilibrium or pretty good anyways。 And then maybe there are context in which we want to use it。

 Okay， so that's the first half of this first lecture is the price of anarchy of demand reduction。

 Okay， so what's the price of anarchy of this mechanism。any questions about up to that point。Okay。

And then a quick full disclosure you so of the two lectures we're going to do today right so the first one is the last lecture of a part。

 so this first half is going to be kind of a little on the technical side。

 know but comparable to last week and it might be a little bit longer might be more like 90 minutes。

 but then the second lecture being the introduction to a new topic is going to be shorter and easier so just so you're duly warned。

All right， so here's what we're going to prove。We are going to prove a bound on the price of anarchy of demand reduction。

And so I'm going to show you sort of a blend of two papers just from the past few months。

I'll put links up on the website。So you might recall fromult simultaneous single item auction discussion for the second price rules。

 we had these no overbidding conditions which were necessary for good bounds。

 And here this has the flavor of a second price auction right so we're not charging people what they bid。

 We're charging them something that could be quite a bit less than what they're bidding。 So again。

 the guarantee will be under a no overbidding assumption。So with no overbidding。

We're going to prove that the Bay Nash price of anarchy is a constant bounded below by a quarter。

And this is going to be actually even for correlated prior distributions。Okay， which is pretty cool。

 We have not seen， We've seen almost no results for correlated priors。

 The only one we ever saw was when we talked about a single item auction with the first price rule。

 And so we're going to see a second example of that today。😊，Okay， so that's the。

 that's the main result。 So demand reduction， while definitely， as we know。

 can affect efficiency at equilibrium。 It can only affect you so much。Alright， so。What we now know。

 we have this toolbox of extension theorems， and I'm not going to go back over them again。

 We know that proving bounds like this just boils down to proving a suitable smoothness condition。

 So I'm just going to state the smoothness condition。

 It will be familiar from the last several lectures。So it boils down。

For the following smoothness condition。So what we want to prove is that for every valuation profile。

 mu。There exists hypothetical deviations。Which are allowed to depend on mu。Such that。And again。

 this is exactly the same order of quantifiers we've been talking about the last couple lectures。

 so it's okay if you don't remember the details， but this is exactly what it was before。

 just trust me。So we're given evaluation profile。 We sort of figure out how to deviate what we were doing in simultaneous second price auctions as we were saying。

 well， compute the optimal allocation for this valuation。

 look at the items I'm supposed to get in the optimal allocation and now bid all in for that allocation。

 Those are the B stars we were talking about last time。 Okay So for every evaluation profile。

 figure out。Dviations B star。And then remember smoothest conditions。

 you're always proving some inequality with respect to every possible bid vector B。

 whether or not it's an equilibrium。Such that for all bid vectors B。

And then it's this disentangling inequality。 Okay， So we say， well。

 let's look at the utility of people。After they deviate。Unilaterally。

And we want so this is an entangled version of the deviations and of this arbitraryrd vector B。

 and we want to disentangle it。 we want to say it's at least in this case。

 we're going to say it's at least half。Of the opt welfare。

For the valuation profile under consideration， and then as usual。

 it's going to be the sum of all of the winning equilibrium bids。 So again。

 this is going to be exactly the same as what it was before。So here's going to be the notation。

 I sum over the bidders。I'm going to look at how many。Okay， so X， I B。

 this denotes how many copies of the item Bider I gets in this bid profile。 is gonna be like 7 items。

 something like that。 And then I just look at。The bid that the players submitted for each of those copies。

 Okay， so this is the sum of the bid submitted by bitter eye on the items that it wins in the outcome。

 okay。And again， all of this is exactly what it was last time，Sos what I call this star。And。

I'm just going ask you to verify offline or recall if it's fresh in your mind that if we prove this inequality。

 then we're going to get this bound。 Okay， and and okay。

 we're going to get this bound assuming that we have no overbidding。

 So no overbidding just asserts that。This is at most。Some over J equal one。

To X I of B of the marginal values。Okay。And recall that the way we use nobidding conditions is that allows us to take this error term upper bounded by the welfare in B。

 That's the turn of the winds up getting subtracted and then divided back through。 Okay。

 so it's all the usual maneuvers。 So if we can prove star， then we get our bound of one fourth。

 Do we have any idea how bad it gets if we do a lot overbidding。 Yes， And in fact， I mean。

 if I was still doing exercise sets， this would be an exercise。 it's at that level of easiness。

 And actually， if you go back and you stare at the proofs， it's actually， it's quite clear。

 So if you overbid by most a factor of gamma， then this bound is going to degrade in some linear way in gamma。

 Yeah， so the proof just wind up working very nicely。So certainly people are not。 I mean， certainly。

 if people are overbidding by 10，20%， then all of the qualitative conclusions are totally exactly the same。

 If They're overbitting by a factor at 10。 You still have a constant。

 but it's not looking like such a good constant anymore。 Yeah， good question。Okay。Good。

 so assuming this no forbidding condition， assuming we prove star will'll get the bound of one fourth。

 Okay， and it's exactly like the simultaneous second price auction analysis there， we had a one half。

 The reason we got a one half there。 and we're getting a one quarter there for simultaneous second price auctions。

 we did not have a one half here。 We just had a coefficient of one。

 So this extra coefficient of one half is why we're getting a one fourth。

 And so the one half we got two lectures ago。😊，Allright。So any questions about that。

 So the rest of this part of the lecture is just going to be， I'm just going to show you the B stars。

 which gets you in quality star。 and then I forgot to say， right， So that's how。

 so that's how you get， know， the one fourth for what equilibrium concepts do you get them。 Okay。

 so we we saw a bunch of different extension theems for Bay natural equilibrium in the last couple lectures。

So we had， but there were sort of two main different ones and they boiled down to how these be stars are chosen。

 the one that you've seen mostly。Remember， we have these canonical B stars in mind。

 like you compute the optimal allocation and then you go all in for what you're supposed to get in the optimal allocation。

So then the B stars depend not only B star I depends not only on V I。

 It depends on the full valuation profile。 right So to compute the optimal allocation。

 it's not enough to just know what my valuation is。

 I need to know everybody's valuation to compute the optimal allocation， okay。

And so then when for deviations defined in that way where B star depends on the full valuation profile。

 we are able to extend the price of anarchy bounds to Bayes national equilibrium for an arbitrary product prior distribution。

 So we had to assume that the valuations were independent。

 And the proof where that showed up is we had to use this doppelganger trick。

 So for a bidder to be able to actually execute B star。

 It had to have some imaginary evaluation profile。 Remember when you reason in a of incomplete information。

 you only know your valuation， you don't know the other people's valuations。

 So B star is not defined if you only know your valuation。

 So you just make some you just sample some from the publicly known prior distribution。

 That's the doppelganger trick。 And we had a nontrivial proof that extended the Bayes nationalash price of anarchy bound to product prior distributions。

 There's this one case， this was I called the corollary to last lecture。

 It was just a single item first price auction。 And we could get away with super simple B stars。

 Everybody just bid half their evaluation。 and you can bid your half evaluation without。😊。

Anything about other valuations？And what we saw is that in that simple type of B star。

 simple type of deviation， where it depends only on your valuation， B and not on others。

 not on v minus I， you actually get the extension theorem for correlated distributions。

 for totally arbitrary prior distributions， F。That's what we proved。

 That was actually a much easier proof。 That was basically just linearity of expectation。 Okay。

 so that's， that's the thing to remember。 We have two genres of extension theorems。

 If B star depends on the full profile， you get it for product priors。

 If B star I depends only on I' valuation， you get it for correlated priors。

 So by stating this for correlated priors， what you should be sort of anticipating is that I'm going show you hypothetical deviations B star or B star I depends only on。

 in this case， mu I。 that's that's what's going to enable the extension theorem。

 which should get me this conclusion。 And that's what I'm going to do。😊，Alright。

 so that's the recap of how you compile smoothness conditions like star into v Nash price of energy bounds。

 Okay， and again， it's just exactly the same as before。 So I'm just going to show you this。

 And to show you this， I just need to show you to be stars。Okay， everyone clear。

So once you get used to this whole template， it becomes very algorithmic， basically， I mean。

 there's just this way that you prove bounces like this。 show me the B stars okay。Okay。Good。So。

The B stars are maybe not the first thing you'd try， but they're the second thing you'd try。 Okay。

 So let me explain。Alright， so so far， what this what everything I've said sounds the most like is second price simultaneous second price auctions。

 right， We have this nobidding condition。 We're charging people less than their bids， etc cetera。

 And So what did we do for what were our B stars in that case。 like we said。

 you compute the optimal allocation and you go all in for the optimal allocation。

 where in that context， we had these X O S valuations。 So going all in。

 you just looked at the relevant add valuation that met your optimal bundle。

 And that sort of told you how to bid on the different items。 So here it's simpler。

 that high level idea is simpler。 Comp the optimal allocation。

 go all in on the bundle you're supposed to get。Here's the first thing you try。

To implement that conceptual idea。So you just bid your value。

Up to the number of items you're supposed to get。In the optimal allocation。

 and then you just bid zero everywhere after that。Okay， so this is。

 this is a deviation that depends on the full profile。 Okay， I look at the full profile。

 I compute the number of items I get。' that's this notation。 So this notation is for the profile mu。

 How many items do I get。 So this is just a number like 7。And then I don't。

 So I bid truthfully up to the number of items I'm supposed to get that's going all in for them。

 And then I bid 0 after that。This， I think， would be the first thing you would try。

 given what we've done so far。Okay。So I'm not going to do the details of this。

 I'll leave it an optional exercise。 It's not hard to not hard to prove that this is too aggressive a deviation。

And it doesn't work。It doesn't work in the sense that So remember。

 we need this sum inequality star to hold for every single bid vector B。 So by this is not working。

 what I mean is that I can exhibit some， you know， frankly。

 kind of weird bid vector B So that because these bids are so high you wind up winning items。

 but you pay your full value。 so just like so we had a similar thing happen with the first price option。

 Okay where the first thing we tried to like， well， what if you bid your value。

 And the first price auction。 well， But then if you win， you pay your value， your utility 0。

 So the left hand side was 0。 didn't work for the first price auction for similar reasons is not going to work now。

 this might be 0， even though the right hand side might be big。

So there exist bid vectors B for which that's true。So that's the first thing I think you'd try。

 given the analogies with the simultaneous second price auctions。 The then one this doesn't work。

 And once you realize it doesn't work because it's sort of too high， too aggressive。

 because on the left hand side， you eat up all of your utility， all of your value with what you pay。

 like， well， you know， for first price auctions， we have that problem。 We just cut it in half。

 So that would be the next thing we'd try。 Let's just try to use the first price a trick。

So idea number two。Cut B star I in half。Okay。And this works。 So this， this， this works just fine。

 You can prove this inequality star。😊，For these B stars。Okay。

And it's going to be by basically the same proof I'm going to show you。

But I'm going to show you that proof not for these B stars。Because there's an even better idea。

So remember， if you look at this。We said there are these two types of deviations。

 those that depend on the full profile and those that just depend locally on your own value。This。

Is of the former type？Because I'm computing how many items I get in the optimal location。

 So that depends on the full valuation profile mute。If we want a conclusion for correlated priors。

 I want it to just depend locally。And there's actually a very simple way to do that。Any ideas。

So what's like a version of idea number two that doesn't depend on。Everybody else's valuation。

Any guesses？So we're just going to use mu I， the values， the marginal values cut in half。Okay。

So just like in the first price single at auction， you just bid half your value。Okay。Now， frankly。

 we would have loved to have done this in the simultaneous single item option。

That would have been cool。We would love to have gone away with that。

 but if you think back to that auction format， that wasn't an option。Simultaneous second price a。

 the interest， the whole point of it was you have this valuation space bigger than the bid space。

 We're thinking about bidders that have like submodular valuations。

 but't let I don't listen to your sub modular valuation。 I force you to submit just one bid per item。

 You have two to the M things to say， I only let you say M of them。

 so you didn't have the vocabulary to express a bit of half of your evaluation for simultaneous single item options。

 unless， of course， you have an added evaluation。Here， we don't have that issue。 I mean。

 this is a simple auction format， but the simplicity does not come from having a bid space strictly smaller than your value space In this uniform pricing auction。

 you're permitted to report any downward sloping valuation you want。 So certainly。

 reporting truthfully。 reporting truthfully over two is an option。 Okay， and we're gonna to use that。

 So that's why we're gonna to be able to get an extension to correlated priors here。

 whereas we didn't for simultaneous second price auctions。

 We can get correlated in effect because the bid space is rich enough to express valuations。So。

That's what we're going to do。 So what remains to show is that for this choice of B Dar I。Star holds。

 And then we're done。 And that's all I'm going say about the price of man demand reduction。

 this proof， okay。It's very cool up to here。All right。So。Proof of star。

So fix an arbitrary bid profile B。 Again， star has to hold no matter what B is。

Consider one of these thumb mans on the left hand side。 and let's try to get a lower bound on it。

Okay， so fix your favorite player eye。So we're going to use the fact that the allocation and the prices。

Are computed in such a simple way。 Okay， so let's just remember the picture。So a couple things。

So first， just remember this B star I。 This is just。M I over2。And then the other thing to remember。

 okay， so the allocation rule。 So the mechanism is going to have these sorted。Hio。

So these are going to be all the inputs to the mechanism of the。BIjs。And。

It's going to allocate to the top M。And then the M plus1 guy。Seets the price。嗯。O。

In the uniform pricing mechanism。Now。From I's perspective。What is I submitting in this profile。

 It's submitting its valuation， It marginal valuation is divided by 2。

 and its marginal valuations are decreasing。So the highest bid that player I submits。In this outcome。

Is it's bid for the first item， which in this deviating bid bidder。

 I says it's willing to pay new I1 divided by two for the first item。

 Okay that's what's happening the outcome that we're looking at。And then， you know。

 maybe there's some other bids， some BKJs that are higher， then there's some more BKJs in between。

The next highest bid belonging to player I， which is going to be its alleged value for the second item。

 U I2 in half。And then there's going to be some various muIjs that don't make the cut。Okay。

 so maybe mui3 divided by two is over here。Okay。And then， in between。So these are BKJs。

For the other players， whoops， K not equal to I。So that's the picture you have in mind。 Okay。

 sorted from high to low。 top M are allocated。 first losing one sets the price for all of the items that are allocated。

Now， I'm going to do something just for technical convenience。 That's a little weird。

 but it just smooths the proof out。So。All right， so in this profile。

 the other n -1 bidders are doing what they were doing in B。

Bitter eye switch from what it was doing in B to this deviation B star。For the analysis。

 I'm going to pretend as if there is still a copy of bitter I submitting its old bids in B。Okay。

 so the claim。Is if I look at playerize utility。After it deviates to be star and the other n minus1 players are still doing whatever they're doing。

That can be lower bounded。B its utility with its same action。As it after。

 I add some n plus one bidder to the auction Who's bidding exactly how I used to be bidding in the original profile B。

Okay， but more generally， just imagine this picture。 Okay。

 so imagine that there's the other n -1 players doing what they were doing。

 And then there's bitter I submitting these mus over2。

 And now imagine I just insert some more bids into this array。Okay。

 the claim is this can only be bad for bitter eye for its。

 It can only decrease its utility if I submit some more bids into this array。 Again， it's sorted。

 remember。Becauseuse， what are the implications from Is perspective， if I throw in some more bids。

 Well， first of all， there might be some items that used to be。

 they used to make the cut in the top end that get pushed out of the top end。 Okay。

 so whatever items I used to be winning， which were giving it non negative utility。 Now。

 it doesn't get them at all。 so that's bad。 The second thing is， is as I throw in some more bids。

 Remember， this is sorted， the price is only to be going up。

this number is only going to get higher as I throw more things into this sorted array。 Okay。

 so you win fewer things and whatever you're still winning， you win at a lower at a higher price。

 So your utility clearly drops。When I insert more bids。And again， for convenience。

 what bids am I going to insert， I'm just going to insert the original B I Js。 Don't worry about why。

 So this is just the claim。 So I'm actually going to lower bound D。All right。Okay。

 so the bid vector B is there。 And now I've inserted this sort of new player that's bidding according to B star。

 I want to lower bound that new player's utility。Good， alright， so。We need to compare。 So we。

 we need to relate things to the optimal welfare。 right， That's always the point here。

So what's going on in the optimal location， let's say I gets X star I items。

And the optimal allocation for our fixed valuation profile mu。And let's say it gets X I items。

In the outcome， under consideration。So B star， and again， remember this is just mui over two。

 okay always。All right， so that's the notation。 X star is what bitter eye gets in the optimal solution。

 X I is what it gets and what we're dealing with right now。Alright， so let's。

 let's start with an easy case。Or let's just observe something really nice。

About our particular deviating bid mu star。Okay。So excuse me。 not mu star。 Mu I over 2。

 So B star I is mui over 2。So suppose you win an item with this bid。Okay， so you bid Mui over two。

I claim every item you get， you're really happy you got it。

So you get significant utility from every single item that you win with this bid because you bid only half your value。

You pay it most your bid。So the payment eats up at most half of your value for the item。

 So you're left with utility， at least half of your original value for the item。

So that's this nice sweet spot that these values over twos represent。

 because you're not going to pay more than that， you're insured of getting high utility for every item that you win。

So， every item J。I gets。And mui over2 B。Contributes。At least Mui J。Over two。To I utility。OK。

Why at least Mu I J over 2。 its value is mu I J over sorry， It value is exactly mu I of J。

 Its bid is exactly Mu I J over2。 Its payment is at most that。 So the utility is at least this。

 What's left。Okay。So a really easy case for us then。

Is any bitter that when it deviates via U I over 2， if it gets a lot of items， it's really happy。

Okay， so remember we're trying to do。 we're trying to say that these are big。

 We're trying to lower bound。 Ultimately， what we want to do is we want to lower bound utilities of the equilibrium。

 So we're doing that by lower bounding utilities One you deviate in this way。

 And so if you get a lot of items when you deviate in this way， then you're going to be happy。O。So。

 precisely。For any bitter eye。Where it gets at least as many items after deviating as it's supposed to get in the optimal solution。

呃。Yeah。Then this。Right just using this fact。뭐。I'm even going to throw out anything beyond the first XRI that you get。

 I'll just sum up your utility contributed by the first XI items that you get。

And by this observation。Oh。So at least this。对。And this is。

Just I was welfare in the optimal allocation by the definition of X star R。Okay。

 so this just meant to be an easy case。 So any bidder when they deviate。

 they get at least as many items as they're supposed to get in the optimal allocation。

Because item by item， they get high utility， at least half their value。

 That means their utility is at least half of the world on the optimal solution。

 And that is actually way better than what we're even trying to prove。

So we're trying to prove that some of the utilities' post deviation is lower bounded by half of the welfare minus some error term。

so for bitter I in particular， we just prove star without an error term。Okay。Is that clear。

So this is an easy case where we're getting even more than what we want。Okay。Allright。

 so the real case。So the interesting case is where you have this carefully crafted deviation。

 bidding half your value， but then when you actually deviate that way， you just don't get many items。

Okay， so now it may not be that it may not be that your values are high。 you might， In fact。

 even think about the case where X I is 0。You might want to keep that in mind in the following derivation。

 Okay， so imagine you switch， you say mui over two and you get nothing。Okay。

So it's obviously not the case that your welfare is high， your welfare is zero。

OkayBut so we want to somehow have the error term involved。

 We want to basically say that the welfare that we that we're supposed to get is being sort of。

 instead， you know， we can charge that in effect against bids by other other bidders， okay。All right。

 so suppose the post deviation， you get fewer items than the optimal solution， again。

 think of X equal to zero as a canonical special case。So what have we got going for us。

 So we want to lower bound the utility。So let me write it this way。So there are some items you get。

 You get X I items。And we argue that for any item you get under any circumstances。

 because your bids aren't that high， your utility is high。Okay。

So you're happy for the X items you get with the deviation， for sure。So now let me write it this way。

Okay， so imagine， you know， maybe in the optimal allocation。

 you're supposed to get six items and you really only got three once you deviate it。So for items。

4 through6。Here's the way I'm going to think about it。

So for the items that you're supposed to get in the opt allocation and you didn't get here。

 why is that， Okay， It's because you're after the cutoff。Okay so items 4，5， and six。

 if you only got three items and you're wondering about why you didn't got items 4，5， and6。

 is because you know， mui 4 over two， Mui 5 over2 and MuI6 over two， we're all here。Okay。

So they didn't make the cut。So what we'm going to do is I'm going say， OK， well。

 if they didn't make the cut， then I'm going to point to bids in the top M， which did make the cut。

Those are at least as high as my bids， which did not get allocated。O。So for you， items 4，5， and 6。

 I say， well， let me look at what I bid for that particular item。And remember。

 this is what you're bidding on the Jith copy of your item。And because you lost。

 that means there's some other bid that did make the cut。Which is higher than your bid。

And so what I'm going to do is I'm going to charge you know so say for the fourth item。

 I'm going to charge it to the lowest bid that made the cut， for the fifth item。

 I'm going to charge it to the second lowest bid that made the cut， for the sixth item。

 I'll charge it to the third lowest bid that made the cut and so on。So。So this was what you bid。

 you lost out to somebody else。And。This is going to be what I'm going to charge it to。Okay， so again。

 the way to think about this term is it's just some BKJ that made the cut therefore is bigger than your bid。

So that's the claim。Okay， or this is true in general。

So when you deviate in this way for the items that you get。

 this is a lower bound on utility for the X items that you actually get here for every J。

 this is non positive。Okay， because you lost and this guy won。So J by J in this range。

 this is non positive， so of course， I can add this in and it's still a valid inequality。K。All right。

So why did I write it this way， it's because I need to lower bound this deviating utility with respect to the optimal welfare so I can group these two terms together。

So， this is equal to。The welfare of bitter eye and the optimal solution for the profile mu。Minus。

So here's what I'm going to do。So I've gotten rid of that term。

 I just combine that with the first sum。I'm going to subtract something even bigger。 Sorry。

 So this is going to be less than or equal greater than or equal to。

I'm going to subtract something even bigger than this。

 I'm just going to let the sum range from1 to X star I。 so I'm just adding more terms。

 So I'm subtracting something even bigger。And now， the claim is is we're done。

So the claim is Star holes。So summing over all of the bitters。 So this is true for every bitter eye。

So summing over eye。So obviously， this part is just the optimal welfare or half of the optimal welfare。

 I get that bidder by bitterder。So let's look at this expression。 Okay。

 so if we stare this expression in exactly the right way， Allright， what do we want it to be。

 We want it to be the claim is that it's going to be。That that sum is upper bounded by the sum。

Of the highest。M B I Js。Okay， so I'll argue that in a second that that sum。

 the error term is bounded above by the sum of the M highest B I Js。 Let's just。

 Let's just observe that if we prove this， this is exactly the same as the smoothest condition。Okay。

 so that term is exactly the same。 This term is exactly the same。 All right。

 So what is this last term， This just says， you know， look at the some of the winning bids。

 and the allocation rule gives it to the highest M BIJs。 Okay。

 so this term is also exactly the same as this term。Okay。

So why is the sum of this over I bounded above by the sum of the highest。VIjs。Well。

Consider the highest。BKJs。Okay。Sored from high to low。

RightSo this is the highest of all of the N M bids。 This is the m highest of all the N M bids。

So what are we doing here， Okay， so say x star I is like 10。What this sum is。

 this sum is the tail of this sorted sequence。 Okay。

 That's the sum of the last 10 entries in this array。 If X star I is like 10。

So that's just what this is， by definition。Now， when we sum over the bidders。Okay。

 the sum of the X I。 remember X I is how many items somebody gets in the optimal allocation。

 The sum of those allocations is M。 All M items are allocated。 So really。

 what we're doing is we sum over I。 We're just saying， okay。

 it's upper bounded by the lowest 10 of these。 plus， it's upper bounded by the lowest 13 of these。

 If player 2 gets 13 items of the optimal allocation。 Plus the lowest five of these and so on。 Okay。

 so that's what these terms are， as we sum over I。 So we charge a total of M times to this array。

 And we're always charging to the lowest entries in this array。Okay。

So we charge M times to only the lowest entries。 Certainly it's only more if we charged exactly once to each of the entries。

Okay。So that's the truth。啊。Using the fact that the sum of the X stars equals M and the fact that we only charge to the smallest entries in the array。

So any questions about that？Okay， then I just mention。

 I'm not going to write any more down on this point， but just a couple variations。

 So first let me just emphasize the B stars we used indeed depended only on mu I， not on mu minus I。

 you just bid half your value， so we do get the factor of four all the way out to the Bayes na equilibrium of correlated distributions。

If you want， you can equally well do a pay as bid version of this so you can have the same allocation rule。

 but you can just analyze it as if you pay exactly what you said you're willing to pay for each of the items for the exact same reason that you could cancel out the revenue terms with the bid terms in the simultaneous first price auction analysis and the same way you can cancel those terms here and you should get a factor of one half the paper doesn't claim that for some reason so maybe I'm missing something but I'm pretty sure this should improve to a one half for the pay as bid version and one thing that's cool is you can even extend this to scenario5 so this was identical goods downward sloping pretty much the same analysis works if you go all the way out to gross substitutes so this is now nonidentical goods。

Bidder's valuations are gross substitutes。 And again， the bid space is gross substitutes。

So if you think about it， this is basically like instead of analyzing the uniform price auction。

 this is something like analyzing Kelso Crawford。 So Kelso Crawford was this ascending auction。

 We only analyzed it， assuming sincere bidding。 we never， we argued that， in fact。

 sincere bidding is non incentive compatible。 So you could ask the question。

 what happens in Kelso Crawford， if bidders do whatever they want。

And this equilibrium analysis basically says you still get this factor4 for Kelso Crawford so it's non incentive compatible。

 but again assuming no overbidding the equiria are good for Kelso Crawford。

 So that's actually very satisfying that these are auction formats we talked about the being of the course。

 but really like 30 years old know these are results that are just a few months which finally kind of push beyond the sincere bidding and actually do a proper analysis of the you know cost of incentives so how much welfare do you lose when you take incentives into account for those 30 year old auction formats。

 So that's pretty satisfy you have to do a little bit more work I mean so where we're really using the identical items know is when we were saying oh the allocation rule is super simple。

 you just sort it in this array and then you can do these charging arguments that part is much more complicated for gross substitutes。

 but still the proofs aren't that much more aren't that much more technical。All right。

 so any questions about all that？O。