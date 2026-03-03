# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p16 -16-(Lecture 16_ The Price of Anarchy in First-Price Auctions).zh_en -BV1fNVNzhEBg_p16-

So at this point， all of you know as much about the price of anarchy with simultaneous second price auction as anyone in the world。

I'm not kidding。 So it not much more to say about that。

 but I do want to show you that there are some other auction formats。 And for this lecture。

 actually just want to focus totally on first price auctions。 Even for single item auctions。

 it's sort of interesting to talk about first price auctions， which we haven't done yet。

 but then we'll also be able to extend those results to simultaneous first price auctions。

By which of course I just mean you actually pay your bid， you don't pay the second highest bid。

 if you win， you really pay what you said you'd pay。And you know both this quarter and last quarter。

 we have talked， you know not we've talked very little about first price auctions。

 at least in comparison to second price auctions。 and the main reason that that's been true is because of our focus on these strong incentive compatibility guarantees。

 these decent guarantees， which of course， the V has in the first price auction hasn't。

 So the first price auctions hasn't come up very much。

But actually now that we're talking about these simultaneous auctions。RightI mean。

 it's not like using the second price rule， you certainly don't have a dominant strategy in these simultaneous second price auctions。

 We know that。 In fact， you know， if you just think intuitively， this is not a rigorous statement。

 but it's not even clear it helps being easier to play at all right in a single item actuallyuction。

 It's great。 You don't reason about the rest of the world at all。 You just bid your valuation。

 It's guaranteed to be good。 If it's the simultaneous thing。You knowIf I asked you。

 which would you prefer， would it be easier for you if I used a second price rule or a first price rule？

Probably a lot of people would say a first price rule， frankly。

 like it might actually be easier to reason about how to bid in one of these with a first price rule。

 certainly though at least first price rule would be at least as well motivated。

 if not more so than the second price rule once we passed to these sort of simple mechanisms for complex settings okay。

So， and actually， as we'll see， we'll be able to get better bounds for first price rules。

 So we'll do even even better than we did in the second price case， which is， which is pretty cool。😊。

All right， so。Let me just sort of remind you of the very， very basics。

 So I'm going to talk for the beginning part of the lecture， even just about a single item， Okay。

 which we have talked about some now and again。 But so just to remind you。

Suppose they're just one item。And so of the canonical example would be you have N bidders， IID。

 let's say uniform distribution。Between zero and one。Okay。Certainly， there's no dominant strategy。

 you want to shade your bid， the amount by which you want to shade your bids sort of depends on what other people are doing。

 but in this case， there's a unique base national equilibrium。And so given that your value is VI。

 you want to shade it and if everybody's uniform 01。

 the amount you want to shade it by is exactly an n minus1 over n factor so we certainly talked about this one n equals2 and we did a derivation on the board showing that bidding half your value is optimal assuming the other player is also bidding half their value。

 same calculation shows this in fact more generally if all bidderters are IID and a first price auction is's a very nice explanation of what you should do at the baseess equilibrium。

You should say， well， suppose I actually am going to win。Suppose actually am the highest bidder。

Then let me condition on that fact。 that's sort of the only relevant case for me is when I am the highest。

 and then conditional on the event that I have the highest valuation。

 what is the expected value of the second highest valuation。

So I think if there's just two bidders and we're both uniform 01， okay， I have some valuation。

 you know， 0。6 or whatever。Condition on me being the highest。 Okay， well， now conditional on that。

 the other person's uniform between 0 and 。6。 and the expected value of the other person is 03。Okay。

And so in that case， I bid exactly， you know， So this bidding half your value is exactly bidding your expected value。

 Sorry， the expected other person's value， given that you're the higher one。 Same thing here。

 this is the expected second highest， given that you're the highest in everybody's uniform。

 And actually that that exact same formula gives you the unique base national equilibrium for any IID setting。

 It's not that easy to prove uniqueness， But but it can be proved。 okay。Right。

 and so this is also sort of intuitive， I think。 So basically this says as the competition increases。

 you can get away with shading less and less and less。Yeah， when you say unique。

 you mean there's no other。 There's no other Bay natural equilibrium in the ID setting。Exactly。

 but that's not very easy to prove。That takes some work。Okay。

What's not too hard to prove is that there's no other symmetric equilibriumria where everybody uses exactly the same bidding function。

 So notice here it' symmetric。 right， So this formula does not depend on I。 What's hard to。

 what's sort of a pain to rule out is asymmetric based nationallib where different people use different bidding strategies。

 but it can be done。Okay， good， right。 So as the competition increases， get。

 you can get away with shading less and less， which sort of makes some sense。All right。All right。

 So as a consequence。Of what I just said。嗯。In I D settings。

 it's not very interesting to talk about the price of energyarch。 Okay， but， you know。

 the news is good。Price of energy be is simply equal to1。In IID settings。Okay。

 so in the unique base naturalch equilibrium， everybody follows exactly the same bidding strategy and the amount that you bid is strictly increasing in your value。

 So if everybody uses the same bidding strategy that's strictly increasing。

 it means the highest bidder is always going to be the person with the highest value。

 And that means you have full efficiency with probability1。 Okay So that's great。

 So I D case single at oxygen first price。 No problem。Okay， now。Let's just even。

 stick with the M equals one case for now。But relax the ID assumption。Okay。

 so we'll stick with it being independent。 The results last lecture we needed a product distribution。

 but we certainly never used identical distributions last lecture。 that never came up at all。

So let's think about distinct independent distributions。And now， this is no longer true。Okay。

So if you're runninging a second price auction wouldn't matter。

 right you don't need a prior it off as a second price auction as long as players play Don strategy。

 you have full welfare， first price auction， if you pass to priors that are not ID。

 you lose the full welfare property。So I leave this as an optional exercise。

That the Bays Nash price of anarchy can be strictly less than one。

Even if say the first bidder is uniform 01 and the second bidder is uniform 02。Okay。

So what does it mean that the price might be strictly that the one。

 it means that with positive probability， the person with a smaller value wins， I。

e winds up at the highest with the higher bid。Now， I saw some very hand wavy intuition about why this happens。

So remember in the IID setting。The calculation is such that the more competition there is。

 the less that you shade。Okay。So if these two people， so there's two bidders here。

 so if they're exactly the same， then the equilibrium would be bid half your value， okay？Now。

 as I make them different， if from this guy's perspective， oh。

 this guy actually has doubled the valuation as before。Then intuitively， the competition is stiffer。

Okay， so if this guy was uniform 0，1， this guy would want a bid half his value。

 I make this uniform 0，2。 So I make these larger valuations。

 That's like a more competitive environment from this guy's perspective。

 So it's gonna to bid more aggressively。 It's gonna to be more than be over 2 at an equilibrium。

Similarly， this guy， when know， because the competition is so weak。

 this guy might want to be less than its value over two， okay？

So with this guy bidding more than its value over two， this guy bidding less than its value over two。

 there's an opportunity for an inversion， it's not likely。

 but there's positive probability that in fact， the first bidder will win with a higher bid despite the fact that its value is actually lower than that a bid or two。

Okay。So that's what happens and again， you on an optional exercise set that I'll post at some point。

 I'll sort of tell you the formula for the bidding function then it's easy to verify if you're interested。

So that's what can happen， so there's already non trivialvi welfare loss， even one item。

 even just different uniform distributions。我看。Another thing I want to mention， you know。

 which is well known， is that。It's hard。To solve。For Bay's Nash Elibria。So even here， it's known。

 So this is a solved case， but the functional forms are not especially simple。

 they're not simple linear functions or anything like that。You know。

 going even much beyond this is quite difficult， so let me give you an example。

 so Viy of the Viy auction in his paper， which introduced the Viy auction this in 1961。😊。

He so he derived this formula。So we keep talking about his DI auction。

 but he talked about Bay National Lib and auctions too， and he derived this formula。

And he offered as an open question， well， I wonder what the Bays National Lib are when they're not ID。

 Actually， I even wonder what it is when there's two bidders that have different uniform distributions。

 so just uniform distributions with different supports。So he posed that question in 1961。

And he guesses when that problem was solved。Two bidders， uniform distributions， different supports。

Two years ago。 so it was 50 years before someone did the 30 pages of computation necessary to figure out what the base national equilibrium is。

When you have two bidders with uniform supports that are different。 Okay So you know。

 if you can get your hands on what equilibrium look like。

 that's great because then you can reason about all sorts of things about them。

 but you're just not going to get very far even just first price auctions two bidders different distributions Now。

 fortunately for us， if all we want to do is is bound welfare loss talk about the price of anarchy。

 we don't need to know what the equilibrium look like。

 at no point have we ever had actually a very solid understanding what equilibrium look like in routing games and facility location games or last lecture Okay We just prove we use the equilibrium conditions to derive lower bounds and equilibrium utility。

 And from that we deduce sort of macro properties， global properties about the welfare。

 Okay so for first price auctions， I would argue the price of anarchy sort of approach is particularly well motivated because it's not clear how else you would ever get a grip on the welfare at equilibrium beyond the most trivial or beyond symmetry。

😊，Convi。Okay。All right。So。First price options。 So I'm happy to report。

 we'll be able to use the same general analysis paradigm that we use last lecture for a simultaneous second price options。

 And the paradigm we use last lecture was to really the last two lectures was to figure out some inequality of this form and then to use this doppd gamemr trick to extend it to base Nash equilibrium。

 All right， And again， if at all possible， we want to avoid having to manipulate prior distributions in our analysis。

 So if we can get the extension theorem idea of the work， we want to use it。

 Okay and so that's what we're going to do。😊，So what I want to do next is I want to just prove an analogous inequality to this for the first price auction case。

 and I'm going to show you actually yet another trick， another tool for your toolbox。

 which is I'm going show you how we prove an inequality like this just for a single item and that's going to be good enough to extend it to an analogous inequality when you have multiple items So we're first just going to prove a smoothness like inequality for one item first price auction。

 We're going to do what's then called simultaneous composition to prove smoothness results again。

 it's still going to be sort the full information case roughly but we'll move from one item to many items using simultaneous composition and then we'll use the doppelganger trick to go out to Bayes Nash equilibrium for simultaneous first price auction。

And this is sort of the state of the art， I mean this is really the cutting edge toolbox for how we can prove welfare bounds for simple auction formats what I'm showing you right now。

Okay。And again， right， and so let me just remind you。So the B stars。Function of V bar。But not be。

So we definitely still want that property as well。Okay， so warm up。M equals1。

So what does this look like when there's only one item？Yeah。So those's going to be some tweaks。

 So there will be a couple small changes as we pass from second price to first price。

 but we'll see those as they come out。 So we need some。At least analog。

 something that looks basically like this。So， we need。Okay。

 so there's only one item we're just coming up with these deviation bids， so just single numbers。

So we need B star1 up to B star n。And again， function of the bar。But not B。

Such that the usual thing on the left hand side。I'm just going to write this part out。

 but now these simplify if it's just a single item case。Right，So if it's a single item。

You just give it to the highest valuation， right so this is just Vmax， right？What about this。

So if we're in the situation， we have a price single item， first price pricing rule。

 what is this boiled down to？And it doesn't even matter if it's first price。So remember what this is。

 This says basically， you have some， you had some bid profile B。 These are the items。 Yes。

 this is in the more general context。 This is the items that I wins with the bid vectors B。Right。

 so everybody wins nothing except for one person who wins the item。

 And that's the person with the highest bid， right。对啊。So this just becomes minus B mix。Okay。So again。

 all I've done is I've taken what was sort of evidently the workhorse of everything we did for second price auctions。

 and I instantiated it for the single item case， and this is what we got。

So this is the kind of thing we're looking for，The question then is， can we do this？

And what does do this mean， It means construct B star1 or B star N， Con the hypothetical deviations。

 given the valuation profile of V。Now。We could just try to， you know， use the exact。 know。

 we already solve this problem for second price auctions。 We figured out how to。

 how to choose these beast our eyes。 So in the second price case， we said， basically， you know。

 look at the items you win in the optimal solution for the valuation profile and go all in。

 So there's a single item auction。 So everybody， but one person loses in the optimal allocation。

 So they'll bid 0。The person who wins in the optimal allocation goes all in。

 That means they bid their value。 Okay， so it means the bidder with the highest valuation just bids it in its hypothetical deviationviation B star I。

 Everybody else bids 0。So is that going to work？So what I'm asking you is suppose we set the B stars exactly as in the second press case。

Is that going to prove an inequality of this form？So let's look at these terms， okay？So remember。

 we're looking at the utility of a bidder。Everyone else keeps doing what they're doing in the bid vector B。

 this one person switches to B star I。Okay， so there's all the people who lose in the optimal solution。

 right， so they bid zero。 that utility that sumant is just 0。 So no， not， that's not interesting。

So the only interesting bidder is the one who wins in the optimal solution with the highest valuation Vmax。

 and in itss B star， it bids Vmax。So what is its utility when it bids Vmax？0， right， I mean。

 this was like lecture one last quarter。 right， first price auction。

 you never bid your value your guaranteed zero utility。 It's never a good idea， basically。Okay。

 so that for the first time is showing so now for the first time we see why we need to do something different。

 at least a little bit different for first price auctions versus second price auctions。

 we can't use literally the same hypothetical deviations B star okay。So observe。And needless to say。

 you know this， we have no control over the right hand side。

 the right hand side might be a super positive number。Because B is basically arbitrary。

 so the B's could be small， the highest value could be big。

 so zero is not going to cut it on the left hand side。So observe。O be die， B star eyes don't work。O。

But what's cool is there's a super simple tweak， which works。 so here's what we do。Solution。U。

We're just going to choose B star I。To be half the value。O。So the full value。 And so you just hedge。

Now， based on what I just told you， the obvious definition of B star would be if you lose in the optimal allocation。

 you bid 0， if you win in the optimal allocation， you bid half your value。

 I'm going to do something a little different for a reason that will become clear in a second。

 So I'm just going to go ahead and also let people who don't have the highest value。

 Go ahead and use half their value instead of 0， okay。

We could have done that in the second price case to it would have been fine， actually。

 it doesn't matter。So that's the difference， half your value and so now going all in in a first price auction to hedge。

 you only bid half your value。So why does this work？So we get a version of this。

 we don't get exactly this。So the claim is that some of our I going to N， U I， B star， I。

 b minus I is at least half。Vmax。Minus Bm。O。And this is， for all。V。For all B。Okay。

So it's a version of this。And it'll be good。So the proof is easy。嗯。So first of all。

Because people bid at most their value。Their utility is going to be a， you know， non non negative。

 right， either you lose or you win at some price below your value。

 So the left hand side is definitely non negative。So if the right hand side is non positive。

 we're done。Okay。Not interesting。So there's only something to prove if half Vmax is strictly bigger than Bmax。

But in that case。On the left hand side， when we actually get to the bitterder。

 when we consider the bitter eye with the highest valuation。In itss B star eyes bidding V max， Ha Vm。

 excusecus me。 It's bidding half its value。 Okay， And so if half V max is bigger than Dm。

 then that bitter eye is actually going to win when it deviates。One thing to keep in mind， I mean。

 just to be clear。 So we're proving this for every possible bid vector arbitrarily crazy。

 And actually， one thing that's cool in the first price world is we don't even need to worry about overbidding。

 overbidding just takes care of itself。 So one case here is that all the bees are like a trillion。😊。

Okay。But that's not our problem because then， you know， the right hand side is going to be negative。

 No big deal， right。So we don't know。 So even when the highest bidder deviates to bid half its value。

 we're not sure it's going to win on the left hand side。 always。 But if it's the case that， you know。

Else bitter。 So in the interesting case， it does win。 El bitter with highest。Vhou wins。

So a bitter eye。In B star B minus I。So UI， BI star B minus I is at least its actual value for the good。

 minus what it has to pay for it， it's a first price auction， what it has to pay its bid。

 its bid is 15 V max。Also known as one half。The max， which of course， is at least the right hands on。

Okay。That's proof， it's just kind of a trivial proof。It should feel a little loose actually。

 and it is， and I'll talk about optimizing it later， but proving this factor two is just very easy。

Right。So any questions about that？So we took the inequality that we knew was super important。

 We specialized it to a single item， and we tweaked to the beast our eyes so that we got at least some version of that inequality with this extra one half here。

 That's what we've done。All right。So let's just start working through some corollaries in the M equals one case。

 Okay， just there's a couple differences。And first price auctions are better behaved than second price auctions in a few respects。

 Okay， so you might think that know in the second price auction。

Where you we had coefficients of one and one and we suffered a one half in the price of anarchy。

 now that we're getting a seemingly weaker lower bound of one/ half and one。

 you'd probably expect us to get a price of anarchy that's worse than one half。

Because we had one half before and now we're proving a worse inequality。

 turns out we still get a one half。Okay， so let me show you why。So that's quarterlyary one。

So for m equals1。I'm going to prove something a little weird。 So I'm just。

 just to help you understand the role of， So here's the new star。Okay。

This is what's the word deprecated star？Right， so I want to develop your intuition about， you know。

 what are the implications of what we just proved， the smoothness like andequality in the first price case。

 So I'm gonna show you that every pure na equilibrium has wealth for at least 50% of optimal。

 This is sort of a stupid thing to prove per se， because it's very easy to prove that the pure price of anarch is one。

 It's very easy to prove that pure equilibrium fully efficient And the first price auction。 Okay。

 But again， the point looking ahead to the extension theorems。

 the argument here will extend the stuff like Bayes National equilibrium where we know the price of anarchy isn't one。

 Okay， So that's why Im gonna do this。All right， so。And this will this will also show you why。

You know，Because the first price auction is nicer why the one half doesn't degrade。

 despite the fact that it looks like it should。So here's a trick that's specific to the first price auction format。

So remember what we always care about， know， we want to say the welfare at the equilibrium is good。

 okay。What we did in the second price。World is we said， wow。Let's just lower bound this。

By the utilities。Okay， so this is like， if you think about it。

 this is a super sloppy step if we wanted lower bounds on the welfare， right。

 because this is values minus prices。RightSo we're taking the quantity we care about。

 and we're adding a negative number to it just for free。 And we're getting nothing in return。

 right It just sort of you know， connected well with the rest of our argument。

 So we're not going to do this anymore。 Okay， in the first price auctions。

 we can actually eliminate this sloppiness。 And that's why we don't lose anything beyond the factor。

 too。So we're not going to do that。Instead。We're just going to say， well， look。

Let's keep track of player utilities。And player payments separately。Okay。

 so this is just by definition。Allright。Now， this part。It's easy to see what this is。 right。

 So we're summing over the players。 And we're looking at the price that players play。

 playersers pay at the equilibrium。 It's a single item auction。 Only one person wins。

 and it's the highest bidder。 So this summed overall eyes。 This is just going to be a Bm。😊，Okay。

That's easy enough。Now let's okay， so now we do this。

 so now we use the fact that B is a purenaache equilibrium。

Switching to the B star deviations can only lower utility。So this is just this Bmax term。Plus。

 I equal1 to N。UI， B star， I， B minus I。So that's just from the purenaric equilibrium。Condition。

And now we apply STAR。Okay， so that connects directly here。

 This is lower bounded by1 half v max minus Bm， so the two Bmax is cancel。Okay， and we're done。

So what happened is so why did this work， Why couldn't we do the same kind of trick to do even better in the second price auction？

 Now， remember， looking back， we had that matching lower bound of one half for the second price case。

 So we actually know that in the worst case， we didn't lose anything by throwing it out。

 And actually， if you think back to that bad example， nobody pays anything。

 So that's why this inequality is tight in the bad unit demand example for simultaneous second price auction。

Now， here， why is it that in the upper bound we can take advantage of thiss because。

With the first price rule， I mean， it sounds glib， but I mean。

 the price you pay is exactly the bid that you made。 Second price auctions。

 the price you pay can be much less than the bid that you make。

And the way that plays out here is on the left hand side。

 we basically think of this as involving player utilities plus the prices they pay。

So over here we have some extra term， the P's， and ultimately our error term on the right hand side is the bids。

Okay， so if the bids， the error term is exactly the same as our sort of surplus。

 we have to work with the prices that can cancel out in the second price case。

 and maybe these prices are way smaller than the bids。 Like maybe these are even0。

 despite the fact that these are big。 So there was no way to take advantage of canceling them now。

 It's really specific to the first price rule that the bids you have here in the error term and the payments the slack you have on the left hand side can be charged against each other。

 okay。So that's good news。 So actually， even though it seemed like we get something worse。

 we're still in the 50% range。 and as I'll discuss at the end， we can even do better than that。Okay。

 so questions about that。So again， we're just sort of warming up getting a feel for how to make use of this。

Smoon is conditioned for the first price case。So corollary2。This is。

 this is a little bit of an aside。But it's pretty interesting。

 It'll give me an excuse to show you that sometimes you can get even stronger extension theorems that apply even for correlated distributions。

So hopefully， I've already instilled some degree of fear into you for correlated distributions with that。

Wicked planted perfect matching， lower bound。 So that was when you had many items。

So now I'm going to show you that if you only have one item， it's not so bad。

 you actually can't handle the correlated case。So。Let me state it over here。So's a corollary2。Oh。

 and I should also say something。We've made no， no overbidding assumption here， right。No， no。

Overbidding assumption needed。Which you'd sort of hope would be true， right， I mean。

 it kind of seems， Im thinking about， it seems sort of trivial， right， So if you're paying your bid。

 know， why are you going pay more than your value， That gives you negative utility。

 And you could always bid 0 and go home。Okay， but it's just nice to see it sort of like reflected in the proof。

 right， so we don't have any last line where we invoke an overbidding。Okay， so。

When there's only one item。And it's a first price auction。Bays Nash equilibrium。

 the baseesnash price of anarchy is at least one half。Even for correlated priors。O。

So this is cool for a couple reasons， right so the first reason， like I said， is that we know。

Its basically， it's very rare。 You can get price of anarchy results for correlated distributions。

 We don't have a whole lot of examples。 Sponsored search is the main kind of killer application where you can get correlated price of anarchy bounds。

 I think that's， that's a project， but I'm going to be discussing it in lecture。

The second reason at school is remember right so I mean even forget getting correlated。

 even if this was at least product and not high ID。

 we'd already be in the regime where we know there's welfare loss。

 we know the price of anarchy is not one and we know it's basically impossible to figure out what the Bayes National Lib are so this is giving us good bounds well beyond where we can actually explicitly solve for equilibrium。

Okay。So。Oh， right， So morally， why is this going to happen。

 How How is it that we're going to get this。I mean， we'll see this reflected in the proof。

 but just you， so that you're looking out for the right thing。

 there's something very special about these B star eyes。

These B star eyes are simpler in a precise sense than the B stars we were talking about before。

So what do you need to know to formulate this hypothetical deviation B RI？Yes。

And Nafi minus I exactly。Okay。So that's exactly what makes it so that the extension theorem applies to correlated distributions。

 not just product distributions。So reason， B star I。Function of V， I， only。Not v minus I。Okay。

So you should keep an eye out for how that plays out in the proof。Okay。

 so let's start with what we care about。The welfare of our equilibrium。We're just averaging。

 so basically。All right， so I mean， I guess all of this is pretty easy to motivate。

So the whole so our last base actually was improve why was it complicated？

It was complicated because we have this doppelganger trick， why did't we do the doppelganger trick。

 it's because we needed an entire evaluation profile to figure out what hypothetical deviation to do。

So here we don'， we obviously don't need the doubleganger trick。 We can just directly do this bid。

 So this proof will be basically exactly like the very simple extension theorems we talked about last quarter where literally you just sort of。

 you know， keep averaging and you apply the smoothness condition， which in this case。

 is the inequality star。You just apply this inside and expectation and everything just works out。

 Okay， so it's just really going to be a very simple proof。All right， so this is what we care about。

Let's just sort of， you know copy we want to get the one half so we should copy the trick we did here of charging the prices and the bids against each other。

So this is expectation。Of the utilities。Yeah。Plus， the expected payments。Sorry。

 this should be some over eye。Some of I。PI。ち。Now， as usual， singlelaam oxygen。

 the second thing is very easy and understand in every evaluation profile。

 exactly one person wins and it's the highest bidder。And they just pay their bid。

So this is just equal to the expected value。Of max， I， Sigma I V。so one item。

 So the action is just a single bid。 This is the highest bidder。 That's the winner。

 and this is also what they pay。 Okay， so that's what this becomes。Okay。So what about the utilities？

Right， so now we use the， oh， good， right。 So now we want to use the equilibrium hypothesis。

 right We want to use the fact that sigmas obeys Nash equilibrium。

 So any legitimate deviation can only make you worse。

 And what we have going for us is that the B star deviation actually is legitimate。

 It's actually an option that bitter I could do at this moment because it knows V I。

So this is at most blah， blah， blah。Some of our I， UI。 So again。

 the point here is that it makes sense。To write。嗯。What do I want to do lets。

What notation should I use here B star？Ae。In all the other cases， past and future。

 I have to write the entire evaluation profile V here or some entire evaluation profile here。

 I can just write VI。Sigma minus I， V minus I。Yeah。ち。Good。Plus， this payment term。And now， of course。

 we're right in the wheelhouse of our smoothness inequality。 So inside the expectation is。

An inequality of this form， and so we can this allows us to disentangle the entangle term and lets us lower bound it by half of the relevant value profile。

 which here is just the full value profile V plus the max bid in the given bid vector B minus I。

 which here corresponds to sigma of V， the equilibrium bids at the valuation profile of V。Okay。

So invoking star。We get blah， blah， blah。And let's see， this is one half。V max。Minus。Max I。

Sigma I VI。So this is the B max when the valuation profile is V and when everyone plays according to Sigma。

And then we're still inheriting this circled term here。Okay。

And so now just like we had cancellation for the pure price of energy proof。

 cancellation here between the payment terms， again， this one。

 this is the one that really corresponds to the bids。

And then this is the one that really corresponds to the payments， but in the first price auction。

 they correspond to the same thing。So we literally just get one half。Expectation。

Over the evaluation profile。Of Vmax。This， of course， is the optimal expected welfare。T道。关多。In twice。

Oh， sorry。 That was a mistake。Thanks。The one aside， I forgot to mention。

Which is back to the pure proof。 this is， I mean， this is a smoothness argument in the sense of last quarter。

 So this already。For the full information case， which again， is not really the one we care about。

 but just to kind of close the loop， this corollary1 extends to mixed na equilibrium co。

 Lib and co co equilibrium by the arguments from last quarter and then corollary 2。

Is what handles the incomplete information case。 And again， I want to emphasize。

 this is a different argument。 So really， for Bayes Nash equilibrium。

 there's a few different extension theorems which take as input。

 smoothness inequalities like star and basically produce as output a Bayes Nash equilibrium bound。

Most of them are almost identical。 This one， this proof of corollary to this one is different。

 Okay so this is a class by itself and worth kind of separating。

 There are much fewer known applications of this one。 But when this is applies， it's great。

 it's a stronger It's a stronger result。 you get all priors， even if they're correlated。

 it's just a simpler， more transparent proof as well。

 so this is the happy case when this corollary to proof applies。

 So that's one of the reasons why I sort of digress and showed it to you but we won't see any other applications of this stronger extension theorem in this in lecture。

 so because the next step is to pass on to multiple items。 And as soon as you have many items。

 you have to know which items to target and to know which items to target。

 you need to know it seems you need to know what you get in the optimal solution and to know the optimal solution you need to know other people's valuations。

 least that's sort of the state of the art。😊，Plus， we have these lower bounds for correlated price of anarchy with multiple items as well。

Okay， good。So questions about that。That's everything I wanted to say about the case of M equals1。

And now I want to show you how we can actually， without too much effort。

 extend this to the general M case。Any questions about a single item？Wops， let's leave that。Okay。So。

 general M。So as usual what I have to explain to you is how do we construct these deviations the star so you give me the valuation profile。

 so we're now in the case of multiple items， we're again going to be treating exactly the same valuation class。

 go ahead and think about submodular， but the proof works more generally for these XOOS valuations。

 maximum of additive functions。So how do I construct？

These deviations B star from the valuation profile。 given what you know。

 it's exactly what you'd expect。 Okay， so what was the difference between first price and second price with one item instead of going all in。

 meaning your full value， going all in meant half your value。

 What do we do with multiple items in second price。 given evaluation profile。

 we look at the items a bit are supposed to get the optimal welfare we went all in。

 So now all in it's the same thing that all in means just cut the old one and half。Okay。So。

Let me actually spell it out in detail。So let me remind you the key property of XOOS valuations that makes this well defined。

So give an evaluation profile。With an opt allocation。S star up to S star N。

What we proved last week is that we can choose。Because each VI is the maximum of additive valuations。

 we can focus on the additive valuation， which is tight at the bundle S star I that I supposed to get in the optimal allocation。

 so it only underestimates the valuation everywhere。

 but we choose one that holds with a quality for this bundle S star I。So let S star I。Satisfy。

 first of all。So again， this is an additive evaluation， so it's just specified by these AI Js。

And if I evaluate this additive evaluation on the items that I' supposed to get in the optimal solution。

 I get exactly the right number。And two， it only underestimates everywhere else。Okay。

So those are the A stars。And。Then， we set。B star Ij。To be equal to 0。

So you're only targeting the items you're supposed to get in the optimal solution and for those going all in。

Now means。Your valuation for that item J， with respect to this additive evaluation A star， like Cu 2。

Sorry。should be up here。Okay。Alright， so now。We're going to move into what's called simultaneous composition。

And basically， what the next chunk of math， which is not too long， is going to show is that because。

Prices are additive。Okay it's just it's just these independent auctions。

 what you pay iss just the sum of what you pay in each。Because there X， O S valuations。

 we can basically think of your valuation as being additive， roughly。

 at least with respect to some bundle that you're targeting。Then。Any inequality。

 any smoothness inequality like this， which you proved for a single item。

 just by adding will give us the analogous smoothness inequality for the entire simultaneous composition。

Okay， so with the second price auction， I we actually sort of from scratch。

 proved an inequality like this。 the moonest like inequality。

 Now what we're doing is we're only proving the analog of that inequality for a single item。

 We've already done that and then show just kind of automatically extends to the M item case。😊，Okay。

 so this is like yet another degree of laziness that we're adding right。

 So we already have this one tool to be lazy。 these extension theorems which say if you satisfy these smoothest inequalities。

 whatever the mechanism is， then you can conclude Bay Nash price anarchy bounds。 Now I'm even saying。

 you know， if you don't even feel up for proving a smoothness bound for the whole mechanism。

 Just prove it for like this tiny piece of the mechanism。

 And that's good enough to get smoothness for the whole mechanism。 And then at that point， you know。

 the next part of the the next heavy hammer is the extension theorem。

 Okay so we've done a double reduction。 Okay， so from bayes Nash price of anarchy to smoothness from we're about to do the second reduction from smoothness of the simultaneous mechanism to smoothness of just one of the constituent mechanism。

 which is what we've already done the single item case。All right， so that's， that's， all right。

 So I'm not going to。State simultaneous composition is a formal theorem。

 but that's what we're about to do okay。All right， so is there some way we can take？Right。

 so how do we just show that this reduces to a bunch of single item computations？All right， so。Now。

 a bitter I， it doesn't have an added evaluation。 It really has this X， O S valuation V I， but。

Let's just， you know， for a while， think about as if its valuation really was a star eye， it's not。

 okay， that's an underestimate， but let's suppose it were。So you star I。

I'm just's going to be I utility。If。It had the valuation。A star I。O。So， notice that。

For every bid profile。The sum of the player utilities。Really， you know， in any。In any bid profile。

 but in particular in these bid profiles。Is lower bounded。By the sum utilities。

 if I switch to the U stars， if I pretend that the valuations are not really the VIs。

 but rather these AI stars。And that's immediate from property true。Okay。So the additive valuations。

 the A stars only underestimate the original values。So whenever I'm talking about player utilities。

I only underestimate player utilities by switching to the added evaluation。

So that sort of should be a trivial statement。Now and again。

 so why am I doing this So I'm going to basically I'm going to prove a smoothness inequality for the whole mechanism。

 but I wanted to just reduce immediately to each constituent item。

 Okay so that's why if the valuations themselves were additive， then that would be immediate。

But with X O S valuations， you can basically think of the valuations。

As being out of it for these kinds of computations。Okay。All right。

 so what I'm going to do next is so now with these preliminaries。

 I'm going to proveest a smoothest inequality， an analog of this。

 but four M simultaneous first price options。 Okay that's this derivation。So for every bid profile。

 okay， I want to analog of this， but for many items。So the left hand side， as usual。

 we have to look at the entangled term。And to make my life easier。

 I'm going to switch to the additive evaluations that are tight at the optimal bundles。

 the S star eyes。Now。On the right hand side here。The valuations are additive。Okay。

So if your evaluation literally is additive and you're participating in these simultaneous single item as。

 your utility just totally decouples。Across these items。

 your payment just adds over the mechanisms and with an addd evaluation。

 your value just add over the differentuction， single item optionsuction。Okay。

So let's actually express this then just simply as a sum over the items。Okay。

 so focus just on some item J。And then we can just talk about the contributions to players utilities from the auction happening for item J。

So I look at each of the players in turn。This just means， you know what you'd think it would mean。

 It just means the utility， the contribution of item J to the player's utility。

 This is well defined with added valuations。And I only need to know the action on item J to evaluate this。

 So I just want to know what is bitter I bidding in this profile。And what is everyone else bidding？

And this profile。Okay。So now forget about this。 Just focus on this， okay。So the claim is， I mean。

 we already。We already have a smoothness like inequality for what's inside the parentheses。 right。

 So there's some arbitrary item J。 I don't care which one it is。

Because I've switched to the additive valuations。Each bidder just has some valuation。

 an A star I J for this item J。There's some deviation that we're thinking about B star I J。

 which we chose。To be exactly the way that we choose it for the single item， smoothness inequality。

 right， So up here， So maybe I should make this more clear。Right。

For the single element of smoothness， I wrote it just existentially。 There exists these valuations。

 but really， the valuations are just， you know， B star I is by definition。VI over two。All right。

So on this item J， bidders have these added evaluations， A star IJ。

 they're using exactly the deviations required for this smoothness inequality as if this was the only item a happening in the world。

And so therefore， we can invoke our smoothest inequality for the single item case on this entangled term just on item J。

So again， at a high level， this is what we want to disentangle。

We switch to added evaluations that's fine for a lower bound。

Disentangling this boils down to disentangling each item J separately。

 And we know how to disentangle single items。 Okay， It is important that。

The deviating bids for the overall auction， the B star I project to what they need to be in the single item case。

 So remember， our smoothness inequality for a single item case is predicated on the deviating bids being half of the value。

 but that is exactly what we're using here。 The B star IJ is half of the local value A star IJ okay。

So the upshot is。Just applying the M equals one case。For each J separately。

What do we get so we get the right hand side？Okay。So the highest valuation。In this context， right。

 so locally， the valuation profile， it's as if Bi I has valuation A star I J。

So this is just going to be the max。Of a star I J。 so that's the analog of V max for item J。

The analog of Bm is just in the original bid profile Who bids the most on this item J。 Okay。

 So this is just going to be a max。Over all， the bidders。Of what they bid on this item J。Okay。

So this is a crucial point。I mean， algebraically， it's pretty trivial。 But as far as conceptually。

 you know， it's great that things are just working out so beautifully， allright。😊，So at high level。

 X， O S valuations， again， if you're just trying to lower bound these utilities， you can， you。

 you can switch to added valuations。 And then everything just projects under the item separately。

 They totally decouple Okay， as long as you choose the deviating bids so that locally on a single item option。

 You get the right deviating bids for the M equals one smoothest bound。

 you can just apply it immediately boom。😊，Okay， and now we're basically home free。

 We just have to rearrange and see that we have what we want。 So any questions about that？O。

All right， so what do we got， So let's try to understand why we're done。All right， so first。

 let's start with these。So let's bring out the one half。

So some over the items of the biggest A star IJ on the item， so let's write that。

 so let's group the items as follows。Let's go over the bidders one by one。

 and then let's group it by who wins what in the optimal allocation as star I。Okay， so again。

 I've just taken these M terms， grouped them according to who wins what and the optimal solution。

I'm going to take these M terms and group them according to who bids what。

 who wins what in the equilibrium。But either way。嗯。So what is this？What is that equal to？

How did we choose a star？ What's the point of a star。

So we had this bidder that didn't have an added evaluation。 Actually， it just had a。X， O S valuation。

 V I。But we said， well， it's a maximum added evaluation， so basically we can pick our favorite set。

Make sure we represent that exactly with one of the added evaluations while only underestimating everything else。

And so we picked the added evaluation A starI that exactly represents the valuation on the bundle SI。

O。So by our choice of AS starR， this actually， so we've already， yeah。

 so the point is this is exactly equal to V of S starI。We chose Astar to make it so。Okay， good。

And so， therefore。This whole sum。Is the opt to welfare。Okay。So what we just proved。

 So what have we proved， We proved that this entangled term， Okay。

 so we showed given evaluation profile V。We showed how to choose B stars。

So that for every bid profile B。This entangled term is lower bounded by half times the optimal welfare。

 half times the optimal welfare。Minus the sum of the equilibrium bids on the items that people want。

That is exactly the inequality we had for the single item case。Entangled term。

 half of the optimal welfare， minus the sum of the winning bids on the item sold。

 back then there was only one item。So this is exactly the same inequality for general M。Okay。

Because it's exactly the same inequality， we get exactly the same version of for starters corollary 1。

 exactly the same proof。 I'm not going to write down the same proof again。嗯。

So let me just say remark。So first of all。So this is simultaneous。Composition。

As proposed by Sirirconis and Tdo and the last stock conference。Okay。And as again。

 I hope you can see from the proof， it's pretty transparent。 I mean。

 there wasn't anything about first price as per se in this argument。I mean。

 what this says in general is it just says suppose with a single item。

 you can prove a smoothness like inequality like this。诶。And this was important。

 Suppose bidders have X O S valuations over all of the mechanisms。Okay， to look again。

 imagine that you're running a whole bunch of mechanisms in parallel at the same time。

 simultaneously。And imagine the bidders have XOOS valuations across them。

Then as long as each constituent mechanism satisfies an inequality like this。

 Then so does the simultaneous composition。 Okay， and this is the proof。

 X O X valuations just lets you project individually on each of the single items。So again。

 I've proven it to you for a specific case to keep it from getting too abstract。

 but I mean hopefully from the proof you can see it's some general theorem and it is。

 it's called simultaneous composition。So again， and so the point here is to go smoothness of the single item to smoothness of the composition。

Or if you like， it reduces understanding smoothness of the composed mechanism to that of a single mechanism。

 which is much easier， usually。So。Analoggue of corollary 1。 And to remind you。

 corollary 1 said that the。Full information concepts。Holds by the same proof。

So in our proof of corollary1， this is where we first used the trick of canceling out the prices paid on the left hand side with the bids made on the right hand side to get our factor2。

 That proof never used the fact that there was only one item。

 The only thing that proof cared about is that we had disinequality。

 Now we have exactly the same inequality but for any items。

 So exactly the same proof works and proves the factor2。 And again。

 that's a smoothness argument in the sense of last quarter。

 So it extends to all the full information concepts。Now。Crollary2 is a different story for one item。

 corollary 2 said that even for correlated prior distributions。

 we get a base Nash price of anarchy of1 half，We know that's false once we go from one items to multiple items。

Okay， not quite Last lecture I showed you that for simultaneous second price auctions， it's false。

 you have a bad P away for correlated priors， it takes very little work to modify the example I showed you last lecture to show that for first price simultaneous auctions。

 it's also a bad price of anarchy for correlated distributions。So the corollary2。

 the arbitrary co distributions were not expecting to just carry over to the general M case。

We also looking at the proofs， know Y for M equals1， we could choose the deviated B star。

 knowing only V I here we can't right So here when we define the devi bids B star I J， as usual。

 I need to know， what are the optimal goods that I get and the optimal solution。 And for that。

 I need to know all of V。So， instead。For the general M case and for Bays Nch equilibrium。

What we want is we want an analog of what we got for simultaneous second price auctions。

Which was for every product prior distribution， we wanted the price of anarch to be good。

 And so that's what we have。So this was proved not using simultaneous composition。

 but just directly by Haceim at all in E a couple years ago。So for all product priors。

The Bays Nash price of anarchy。And a simultaneous first price auction。Is at least one half。Okay。

So this is basically exactly the same result we had for second price auctions。 Actually。

 it's a little better because in second price auctions， we needed this overbidding condition。

 And here， as you'd hope in a first price auction， overbidding takes care of itself。

 You're never going to see overbidding in an equilibrium because that would be negative utility。

So the proof is basically the same。Okay， so basically， you just combine the proof of corollary 1。

By which I mean you take advantage of this trick of canceling out the payments on the left hand side with the bids on the right hand side with the Doppel Ger trick。

So just to remind you briefly what I mean by that。So for the bayes na equilibrium， again。

 the question is what what's the deviating hypothesis that you use。

 What you'd love to do is just use the deviations B star we've already carefully constructed。

 But you don't know the optimal solution because you only know your value， you don't know others。

 So you sample these doppelgans。 you sample these w minus Is。

 you know the prior So you can sample doppelganger types dopp valuations for the other bidders。

 then you can say， well， if this was people's valuations， what would be the optimal solution。

 And in that ex thought experiment， you're going get some bundle of goods S star I and then this is just how you bid so again。

 that's your and again， the only difference with the second price mechanism is instead of building bidding your full a star Ij。

 you divide by two to hedge with the first price rule。And then again。

 you have to use the product distribution assumption in exactly the same place。

 you do the switch between the V's and the Ws so that you can apply the smoothness inequality that we have So again this is the crucial inequality that gets fed as input to that proof you apply this inside the expectation and then you get what you want okay and again these just take care of itself So these bids just cancel with the prices on the left hand side there's no need to control these with some overbidding condition。

Okay。So based on all the stuff you've seen today， you're all fully capable of just putting those ingredients together to do that proof。

 there's literally no new conceptual ideas that you haven't already seen in the previous arguments okay。

All right， so any questions about that？Alright， so just a couple， just a recap in one comment on。

 on optimization。So I know I've already said this once。

 but just because this is one of the main points of today， let me just make sure it's crystal clear。

There's two important tools that we've learned。 Okay， and， they work really well in conjunction。

 extension theorems and composition theorems okay。So extension theorems we were introduced to last quarter。

For full information concepts like correlated course quality equilibrium， today。

 we've discussed for the first time extension theems for Bays N。

And the point of an extension theorem， so you only want to be responsible for proving a bound for some really simple equilibrium concept。

 like pure National equilibrium of full information games。

 but you want to claim credits for much more general results。

Today we want to credit for Bayes National equilibrium of an incomplete information game。

 where in particular there's a prior， there's some prior。

And so what I've shown you and this is principally the doppel gang trick。

 but we also had this other extension theorem that handles correlated distributions if you're lucky enough to be able to devise deviations that depend only on your valuation and not on those of others。

 so the point is you prove a smoothness like inequality， so this is an example。

 so that just means one of these disentanggling arguments。

 you prove a disentangling argument like this。Or like this。

 notice these inequalities do not reference any distribution， right There's no prior here， right。

 It just says for every valuation profile， there exists B stars so that for every bid profile B blah。

 Okay， there's no distribution in this statement。So you prove a distribution free statement。

And using one of these two extension theorems， you get the exact same bound in this case。

 it was one half all the way for Bayes Nsh equilibrium。 So that's the point of an extension theorem。

 You do the hard work， the manipulation without a distribution， just purely onval and bid profiles。

 You get the conclusion， though， with respect to your favorite prior。 Either product are correlated。

 depending on the type。 So you get your price of energyarch guarantee for Bayes Nash equilibrium。

 So that's tool1 extension theorems。The second tool composition says， well。know。

 provingrov these smoothness inequalities， proving these disenttanglement arguments。

 that's kind of hard work。Is there some way we can reduce these disenttanglement arguments and make them simpler？

And so what we saw for this particular case of simultaneous single item options is the answer is yes。

 because this' is a notion of composition， which says if you're happy handling X OOS valuations。

 and we'll talk a little bit next week about what's required to go beyond X O S valuations。

 But if you're happy with X O S valuations and its subclasses， then。😊，Then what。

 I lost my train of thoughts。 right。 So then rather than just directly proving smoothness for the entire collection of mechanisms。

 It suffices to just prove these disentangling arguments。

 these smoothness in inequalities for one constituent mechanism。

 that lifts by addivity to the entire mechanism。 Okay， so that's the second part of the reduction。

 So you wind up only having to ever actually prove， you know， given this toolbox。

 you only have to prove that for something like So you recall how trivial to proof of this was。😊。

Do you remember， this was like embarrassing to actually write that out in class， right。

 So we proved that for a first price auction， you know， whatever the valuation profile。

 if people just bid half their value， then this is true。 And it seems silly。 okay， But that's。

 in fact， the only specific property we needed for this auction format to deduce then Bay Nash price of anarchy bounds for simultaneous first price auctions。

 The composition theorem pushes this to basically a full information model with multiple items。

 the extension theorem pushes smoothness for the compose mechanism out to base Nash equilibrium。😊。

Okay， so that's the most important kind of high level takeaway from these last couple of lectures。

 The one thing， I just want to mention。Is a comparison between the two。 Okay。

 so I've given you results for the second price rules and the first price rules， you might ask。

 does the theory advocate sort of one over the other， For example， from a welfare bound perspective。

 So second price auctions， we know everything。 right。

 So we have the So what's weird is at the moment， I've showed you equal bounds for both one half either way。

 sort of for slightly different reasons。 but we got the same bounds。From last week。

 we know that for second price auctions， that one half is tight。 even for the full information case。

 even for pure， even for unit demand valuations， you can't do better than one half。

 I haven't shown you any lower bounds for product distribution。 say， for first price auctions。

 And in fact， you can do better than one half。 it's not that hard。

 I'll lay it out as an optional exercise。 You can improve the one half。 So this very simple argument。

You can have a slightly more clever definition of B star I， which is actually randomized。

 okay so you deviate to a distribution over scaled down versions of evaluation that improves the 0。

5 to 1 minus1 over e。Where E is 2。718 dot dot dot dot。 Okay， so that's roughly 63%。 Okay。

 so a more clever argument improves this 0。5 to a 0。63。As I hope is clear。

 you know that improvements is just going to cascade through every single result I told you today about first price auctions。

 whether it was quality equilibriumria， baesastic Libria， correlated prize for one item。

 whatever all the one half to become 0。63s。 that's the state of the art。

 but that is strictly better than what is attainable with the second price world。

 So you know using you know if you want to use worst case welfare loss as a criterion then it actually says first price is provably better than the second price rule。

 okay。So I think that's enough for today， I'll see you next week。

