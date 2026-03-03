# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p07 -07-7_ Multi-Parameter Mechanism Design and the VCG Mechanism).zh_en -BV1VmC2YzEXJ_p7-

Okay， so today the plan is to sort of ping pong a bit between the more applied and more theoretical aspects of mechanism design than what we've been talking about。

I want to begin the lecture with one final point on last week's topic。

 last week's topic was revenue maximization in single parameter environments。 So last week on Monday。

 we covered something very fundamental， Myerserson's theory of optimal auctions based on virtual surplus maximization than on Wednesday。

 we talked about much more recent results。 We talked about approximation guarantees for much simpler options。

 we also talked about prior independent options， options that do almost as well as if you know the distribution。

 even though there are description cannot reference the distribution。

So what I want to just say one final thing about it is， okay， so we've learned all of this theories。

 so how does this actually get a plot？So I want to say a little bit。As a case study。

About some work that was done by Michaella Strrovsky， who's a professor here in the business school。

And Michael Schwartz。So's a working paper from '09， I'll put a link up to it on the course website。

And this is a field study。So they were working for Yahoo。

And they were trying to be smart about setting reserve prices in keyword auctions at Yahoo。

 really smarter than they'd been in the past。And by keyword auction。

 I just mean a sponsored search a， same thing。你看。Now， I know what you're thinking。 You're thinking。

2008，2009， researchers give Yahoo some advice。 What's happened since then。

But don't blame Ostroskin Swtz。 I mean， this is， this is good work。 So you。

 the worst days that Yahoo actually coincided with basically not having a research group。

 So I'll tell you more about the impact of their work in a second。O。

So one thing Im asking you to verify on the exercise set is that at least in the theory。

If you want to do revenue maximization， a keyword a。

 it's as straightforward as some of the other simplest examples that we've seen。

 At least if the bidders have evaluations drawn I ID from a regular distribution。

So very much in the spirit of a single item auction。So， if you have。Bitders， And remember。

 in keyword options， the valuation is per click。 So if those valuations per click are I D from a regular distribution。

 meaning the virtual value function is increasing。So with a single item auction。

 we observed that this is a great exhibit A for auction theory。

 We get that the victoryy auction with a suitable reserve price is optimal。

 Here we get that the natural extension， the rank by bid。😊，Allocation rule， again。

 with a suitable reserve price， the same reserve price。

 a monopoly price is the optimal optionuction once coupled with suitable suitable payments。Okay。

So in theory， if I told you this regular distribution a bit is your I D。

 you would know exactly what to do to maximize revenue。So Ashtrasky and Schwartz said， well。

 let's look at what Yahoo is actually doing and compare it to the theory and if it deviates from the theory。

 bring it closer to the theory and see if Yahoo actually does better if it actually does make more money。

So what were they doing？Well， they were using unusually low reserve prices compared to what the theory says。

So in the earliest days， the reserve price was just a penny。 Then later they raised it to a nickel。

 And then at the time， the study was in 2008， they had raised it to a dime。Perhaps more curiously。

 this reserve price was used across different keywords。 Okay。

 so remember how it works in these keyword options。

 the user types in some query into a search engine And then the advertisers who actually care about people searching for that term。

 they're the ones that participateate in the auction。 So of course， the participants。

 one of these auctions is different if someone searching for station wagon than if they're searching for camera。

 And you might think that， you know， maybe some search terms involve as where the valuation distribution is rather different than for other keywords。

 So maybe people searching for divorce lawyer， maybe typical valuations per click there might be different than when the keyword is pizza。

 for example。😊，嗯。So that was what was in place。When this study was done。And。

So here was the field experiment that they did。Its， I mean， in some ways， it's very straightforward。

But I want to tell you about it。So they said， well， you know， what would the theoretical optimal be？

First of all。Question。So， you know， of course， Yahoo gave them past bidding data。

 They studied roughly a half a million keywords。 So they saw a history of bids on each of these 50000 keywords over some period of time。

 From that， they proposed， they sort of fit distributions to them。 And that was a bit ad hoc。

 but there's no real evidence that it mattered which distribution they use。

 they fit log normal distributions to the past data。And of course。

 they did this separately for each keyword， so they got a different valuation distribution for each different keyword。

 depending on the bids on that keyword in the past。

And so then they did something which all of you are now in a position to do。

 which is once you have the distributions， what's the optimal reserve。

 you all know that's the monopoly price。 It's a calculation。 any of you could carry out。

It did indeed vary with the keyword for some， the theoretically optimal reserve price was little for as it was high。

 but for many， many keywords， it was considerably higher than the baseline 10% that Yahoo was using across the board。

 Okay， they range as high as like a buck， but seeing 20，30，40 cents was not very uncommon。 Okay。

 so 2 to 4 x， The suggested increase was reasonably common。

So then for these keywords where the theoretically optimal reserve price was higher。

 the obvious thing to do was to raise it。 see if it gets better。 to check the theory。

So that's what they did。 Now， the the Yahoo top brass。 they wanted to be a little conservative。

 They didn't just want to sort of run wild， you know。

 and immediately switch to the theoretical prediction。 So they took the midpoint。 They said， well。

 you know， if the theoretical optimalum reserve is 40 cents， let's just average that with the old 1。

10 cents， let's just bump it up to 25 cents。 Okay， So that's what they did。😊，So oh， sorry。

 new reserve。Is the average？Of the old one， which was 10 cents。Plus， the optimal one。

One sort of lesson learned from this study， which is kind of cool。

 which is that in both practice and in theory， you get the most gains in revenue from this sort of initial increase。

 So once the reserve gets pretty close to the optimal one。

 raising it that final bit doesn't really change the revenue very much。 Okay。

 so the biggest gains are from the initial increase。 if the reserve price is way too low。

 So even though you know， the the reason was maybe conservatism。

 this is actually a well justified maneuver。😊，Okay， so what happened？Well， it worked。So the revenue。

 you know， it varied a little bit keyword by keyword。 but overall， the revenue went up。

By several percent。So you know， it might sound sort of modest， several percent。

 or remember several percent of like a really large number。 So this was a big deal。

And it was especially effective in some sense where you'd expect it to be competitive effective。

 which is keywords， which were not sorry， you'd expect it was effective in in keyword markets。

 which on the one hand， there was actually value there。

 So there were people willing to pay for those clicks。 And secondly， there weren't a lot of bidders。

 It wasn't very competitive。And if you think about it。

 this is where you'd expect reserve prices to matter the most， because remember。

 the reserve price raises your payment exactly when there's precisely one bid above your reserve。

 otherwise， it just defaults to the usual surplus maximizing a。 Think about a single item a。

 right if you get two bids above the reserve， it's as if the reserve was 0， it doesn't matter。

 Okay So if I increase the competition， you have lots of bidders。

 It's more and more likely you'll see two or more people above the reserve price。

 So reserves are really important in thinner markets where you don't have a lot of bidders。Okay。

 so especially。So I'm going to put it on the exercise set， the next one。If you to think about。

 you know， give me some examples of keywords that might simultaneously be valuable。

 There'd be people be willing to pay for those clicks。 But also， you might have， say， at most 6。

 you might think advertiser is bidding in the option。Okay， and here here here by small。 I mean。

 let's say at most， at most6。So this was cool。 So in the。

 in the Yahoo president's third quarter report in 2008。

 she was talking about know how the company was doing。

 and they had had this growth in search revenue。 And she cited better reserve pricing strategies as the probably the dominant factor in that revenue increase。

 So it was a big deal for Yahoo at the time。😊，Question。second。Like Mars came in。Good question。

 Good question。 right， So those of you who are doing the problem sets know that there's this thing called the generalized second price option。

 That was problem。 I forget3， maybe。On the first problem set。 And indeed。

 Yahoo was not using the DSSIC payments。 They were using the sort of next slot。

 general GSP type payments。Now， so it doesn't require much of that doesn't require changing the story much。

Because， what we said。And what I'm asking you to prove on the exercise step。

Is that if you want the optimal DSIC auction， then you should use the myson payment rule。

 but in fact， you can do exactly the same exercise you did for GSP in the presence of a monopoly in the presence of a reserve price and you get that there's always this full information equilibrium。

 which mimics what would be the dominant strategy outcome in the Myerson optimal auction So the bids have to work a little bit harder to shade their bids just right。

 But if you believe in that equilibrium of GSP even with the reserve price。

 you actually will have optimal revenue at that equilibrium。 And in fact。

 I mean if you read the ba but that's what they do Okay and so then。Yeah， and so in particular。

 when they have to back out the valuation distributions。

 they do not assume that bids are truthful bids。 So they assume bidders are actually at that equilibrium of the GP auction from that。

 they reverse engineer their values。 And then because you can use that same recurrence to back out their values from their bids。

 And then you can actually fit the distributions to it。 That's a good question。Question。

So you don't know people's values， so it's not clear how to check that。Yeah。So I mean。

 you can do sanity checks， so you can do things like， well。

 here's a set of bids that are clearly not at any equilibrium， whatever the values。

 And people have certainly done those studies at length in GSP。

 And I'm not sure what rule of thumb to tell you。 I mean， the equilibrium analysis is useful。

 I mean it does help you think about the problem properly。

 but its there's also non-trivial deviations from the equilibrium quite commonly。Okay。

 any other questions。Allright， then if not the middle part of the class is going to be fairly abstract。

 and then we'll jump back to another case study， okay。Allright， so for the first time。

I want to move beyond these single parameter environments that we've been talking about。 Okay。

 so in a single parameter environment， you might recall。

 the reason they're simple is that from each bidder's perspective。

 all you have is one private piece of information。 Your value for stuff。

 that you have this value V I， If I give you twice as much stuff。

 You get have twice as much value for that stuff。Right。

 but it's easy to imagine situations where this is not a sufficient model for what you're trying to understand。

 Imagine there's two goods， different goods。 Okay， A and B， And all I want to know is like， do you。

 do you want A better or do you want B better。Already。

 we're outside of the single parametermer environment。 It's not the case that， you know， all more。

 more stuff is all equal。 Okay， you care which kind of stuff you get。So。Let me talk about general。

Or so called multi parametermeter。Mechanism design。So we have n bidders as before。

In the single parameter environment， it was sufficient。 so we're young to have a set of outcomes。

But in the single parameter environment， all we cared about was how much stuff a bitter got。

 So outcomes without loss of generality were these n vectors just saying how much stuff everybody got。

 no longer true。嗯。We're gonna have a totally abstract set of outcomes。

 I am'm gonna assume it's finite。And this could be anything。Okay。

 certainly need you don't want to think of about it anymore as n vectors。 Allright。

 at least not n vectors of numbers。So we'll see more concrete examples as we go。 For now。

 go ahead and just think of this as a single item option。

 which gets set omega would have n plus one different outcomes corresponding to who won， if anybody。

 Okay， that's fine for now。So a bitter eye now， rather than having just one private valuation has a separate private valuation for each possible outcome。

And this again， is a real number。 And at least for today。

 I'm going to be thinking of this as non negative as well。Oh。Okay。

So this is a general mechanismism design event。Now， in the context of a single at auction。

So even if I， even if I take omega to be the n plus one outcomes about who won， if anybody。

 this is already a more general model。 This is no This is already no longer a single parameter environment。

 We'll see more interesting examples later。The reason is that when we're thinking about single item options in the usual way。

Really， a bidder was only allowed one opinion， Okay， which was how happy it was if it got the good。

 I its value for the good。 If it lost， if it didn't get the good， its value， we just assumed was 0。

Okay， so there are n outcomes， the ones in which I loses where its value was assumed 0。Okay。

No longer true with this formalism。 Now， in principle。

 bidder can have an opinion about each other person winning the good as well。 Okay。

 so maybe the best case for me is I get it。 That's 100。 But if this person gets it。

 they're my friend。 So I'm still pretty happy，75， I don't like that person at all。

 So that's the worst case outcome。 then' then it's a 0。So already is not that unreasonable， right。

 If you think about people bidding to acquire a startup or something like that。

 maybe you really want to acquire it。But you'd also much rather， if it's acquired by somebody else。

 you'd rather be in a totally different market rather than to your direct competitor。But again。

 we'll see more examples as we go。So I， what I want to cover now is another sort of absolute cornerstone。

 absolute linchpin of mechanism design theory。And this is an old result， it's from the early 70s。

And it's usually credited jointly。To victoryckery。Clark。And groves。And what the VCG mechanism。

 this VC G theorem tells us is that， well， there's at least one result from the single parameter world。

 which extends to the multi parameter world， even though it's totally general。

And the result is that we can still do dominant strategy incentive compatible surplus maximization in every such environment。

So we already know the special case of this result for single parameter environments。

 You'll recall thats we had this exercise showing that the surplus maximizing allocation rule is monotone。

 and then we had Myerserson's lemma saying we can turn that into a DSIC mechanism。

So this result we don't know because we have never before thought about multiparameter environments。

Okay。All right。Also， for those of you that remember the definition of an awesome auction。😊。

This has two of those three ingredients。 In one was DSSIC ingredient2 with surplus maximization。

 assuming truthful bids。 conspicuously absent is that third property polynomial time。 Okay。

 And we knew we already had to lose that in single parametermer environments。 Think about Napsack。

 Think about a couple of the problems on the first problem set。

 So we certainly don't expect to have it here。 In fact。

 we'll see that in some of the key applications。 the VCG mechanism is， in fact， highly non-asome。

 And I'll make that precise。 in a little bit。Alright， so the。

Plan is the same plan were I was advocating for the single parameter problem。Which is， I mean。

 as usual。 So we're thinking about direct mechanisms in the same way。

So we just get bids from players。 We choose allocation。 We choose payments。

 although that's defined in exactly the same way。And we are getting going to factor this design problem。

 We need allocations。 We need payments， they need to be coupled。 We're to do it in two steps。 First。

 we assume without justification that we have truthful bids and ask what would we do。

 and then we try to come up with suitable payments to get the DSIC property。

 thereby justifying our assumption that bids are indeed equal to valuations。

So let's assume truthful bids。So just again， no motivation yet。

So I'm going to write these in as vectors now， not as numbers。Why am I doing that。

 Why is B1 now a vector and not just a single number。 What do I need to ask Bi1 about。

Yeah each outcome， right by assumption， that's the private information。 Okay。

 Bi one could have any value for the various outcomes。 I have no idea what they are。

 And I can't do any kind of sensible maximization unless I know。 So I'm gonna ask them。

So I get these bids， a vector of vectors。So BI indexed。My capital omega。

And it's kind of obvious what the allocation will has to be， because the。Property that I want is。

 is already in the theorem， right， So just like before we just set on a given bid vector。

 we assume that the values。 And under that assumption， we just output the outcome。

 which is surplus maximizing， okay。So step one， our hand is forced by what we want。Okay， so x。

 this is no longer a vector necessarily。 This is just some element of capital omega。

And surplus is defined in the usual way。 We just sum over the bidders of their value。

 We don't know the value。 We use bids as proxies。So among all of the possible outcomes。

 we just choose the one that maximizes some of the bids for that outcome。Only thing we can do。Now。

 step 2。We need to define payments。To get the DSSI constraint。给。

And this is exactly where I stopped at the end of lecture 2。 And then in lecture 3。

 I gave you Myson's Lemma， which implemented step 2 for all of the rest of the single single parameter applications we ever saw。

 because that's mysons Limma did。 So what you need is you need the allocation rule to be monotone。

 necessary and sufficient。 And if it's monotone， then by the way。

 here's the formula for the payments to get the DS SIC proper。Now， we're not in Kansas anymore。

Multiparameter problems，And so the issue。It's not obvious how to define monotonicity of an allocation rule anymore with these abstract outcomes。

Okay， remember what did it mean in the single parameter setting。 It meant if you bid more。

 you get more stuff。Okay， we just have to set omega。 What does it mean to get more stuff。嗯。Similarly。

 it's not clear what it means to say a critical bit。

 That was our characterization of truthful payments for 0，1 problems。Right。

It was just the smallest bid you could make and still get away with winning。

We don't even really have a notion of winning anymore， with this abstract set omega。Moreover。

 you know， you can consider false bids， which are higher in one component and lower in another component。

 Okay， so the space of mis reportss is no longer one dimensional。 It's multi dimensional。So。Issue。

Definition of monotone。Et cetera。Not clear。Okay。That's where the single parameter paradigm starts to break down。

Just for completeness， there is actually a notion of monoity， cyclic monotonity。

 which is a necessary and sufficient characterization of the allocation rules。

 which are implementable。 And actually， mathematically， it's very pretty。

 It's basically isomorphic to the fact that a network has well defined shortest paths。

 if and only if it has no negative cycle。 So it's kind of a very cool the mathematicalmaticly。

 But cyclic monoity is way less operational than monoity。 It's just brutal to verify。

 You can't figure out if an allocation will satisfies it or not。 So it's never actually。

 it's almost never used to design mechanisms and prove that their DS SIC。 Unfortunately。😊。

So we're going to have to use a different approach， a direct approach。

And here's what turns out to be the key idea。One of your exercise sets， I asked you to prove。

interpretationterpretation of what these critical bids are for surplus maximizing problems。

 there was sort of an English description of how you could interpret those critical bids。

 Does anyone remember what it was。Good externalities。Okay so one way you can think of。

The critical bid in a 0，1 problem when you're doing surus maximization is basically bidders pay for whatever surplus they take away from other bidders by virtue of their presence。

 by virtue of participating in the auction。And if you think about that English sentence。

Charge somebody for the surplus loss they inflict on the others。

That actually totally makes sense in multi parameter environments。

So that actually way of thinking about payments， at least for surplus maximization。

 which is all we're trying to do right now， that seems like something that I generalize。So， idea。

Charge a bitter eye。It's externality， and I'll give you the formula in a second。And again。

 what I mean by this is a bidder has to pay for the surplus loss it in clicks on others。

 And if you think about it， that is sort of a natural thing to try， right。

 we're trying to make this thing D S I C。 So we're trying to get the bidders to do what we want。

 and we're trying to do what we want， which is surplus maximization。 So hopefully by you know。

 what do they care about， They care about themselves。

 And that's all They care about how much value they have for an outcome。

 What do we care about the designer。 We care about their value for an outcome and everyone else's。So。

 somehow。Forcing the payment， forcing them via the payment to care about everybody else's value for the outcome seems like it could work。

And indeed， this so called internalizing the externality is is a standard trick in in economics。

 and it works here and in many other places。Okay， so what do I really mean by this。So again。

 we have our allocation rule， and I'm proposing now a payment rule。OK。So the proposed rule， allright。

 So the surplus loss inflicted on everyone else。 So first， we say， well。

 how well would these other n -1 players， How well off would they be if I didn't exist if we just ignored it when we maximize for surplus。

Okay。So that means instead of solving this problem。Suppose we solve this problem with I omitted。对。

So this would be the surplus enjoyed by the other and minus1 bidders。If we did not consider I at all。

On the other hand， with I。If Oomega star is the outcome chosen here， and we did consider I。

Then restricting just to the surplus enjoyed by the other bs。It would just be the sum of there。

Bids further chosen outcome omega star。So， this is with I。

And this is where I'm using the notation omega star。To be the outcome chosen。

By the mechanism on a particular bit。So this is precisely what I mean by the externality。

So I've given you the allocation rule。And I've proposed a payment rule， Okay。

 but we don't have any Myerson'slemma guaranteeing that we have a DS SI C property。

 So we're just going to have to check it from scratch。Okay。But once you've guessed the payment rule。

 checking it is usually not that difficult。 So that's what were going do next。Okay。

So claim this mechanism and this mechanism is what's known as the VCG mechanism。

I claim that it's DSSIC。And of course， by definition， it's surplus maximizeizing。

Assuming truthful bits。But I owe you this， and then we're done with the theorem。All right。

So proof of claim。So we're gonna do something we haven't really done。

 I don't think since we talked about the victory auction。Which is prove D S， I C from scratch。

So we have to prove that no matter who you are， no matter what the other people are doing。

 your pay off， your utility is maximized by setting your bid equal to your value。

So let's fix who you are。I fix what everyone else is doing。B minus I。看。

So I is trying to figure out what it should be。 It's trying to compute the best B I。So。

If it chooses some bid。B，I leading。To an outcome， Omega star。Then。As usual， as utility。

We're in the same old quasilinear model。 So it's just its value for the outcome chosen。

 minus the payment it has to make。Okay， so just by definition。

So let's expand this using the proposed payment。So we have， we have one term。

 So Im gonna expand this。 So there's the value of I term。And then the payment term has two terms。

 Okay， and I'm going to collect。This part， this second term with the value term。

 And then this will be a second term。 Okay， So I just rewrite expanding。Oh yeah。

 one of these is minus。 This is minus。Thank you。Yeah。Thank you。All right， so call this one。Call this。

 too。So， a wise person once said。Do not worry。About that， which you cannot control。

So have a look at the second term there。 have a look at two。So player I， right。

 it gets to choose B I， and that's it。So what， what influences player I have over that second term。

What is that second term a function of。好没。Yeah， so it only depends on BJ's for genetic at equal I。

So that's just some number， okay。Thousand23。 And it's that it's the same number， no matter what bid。

Player I selects， okay。So player I wants to maximize this difference，1-2。

 but that reduces that is equivalent to just maximizing one， because it has no control over two。

And's not going to worry about it。So let's just focus on term 1。Think about that。Alright， so。

 let's think about what's the best case。 Now， let's remember。In term 1。

 so this is where bitter eye has some influence， okay。But let's remember the nature of its influence。

 okay。Bitter I cannot decide Oomega star the outcome directly。

 The mechanism gets to choose Oomega star。 All bitter I can do is try to coax it into picking an attractive outcome。

 bidding appropriately。How does the mechanism。Yeah， bummer。

So let me just write it up here for scratch。So VCG chooses。Omega star。

To maximize what it believes to be。The sum of the valuations。Okay， so don't forget。

The mechanism is the one that gets to choose the outcome omega star。 And this is how it does it。

This bitter I can choose B sub I， Of course， B sub I participates in this optimization problem。

 So bitter I can influence the outcome chosen， but only via its submitted bid B I。不。

Let's just imagine。 imagine I actually could pick the outcome directly。O。What would it do？Well。

 the best case for I。Well， the outcome it's rooting for。

Is the outcome that makes one as big as possible。 Again， can't control 2。

 So you want to make one as big as possible。So the best case for。I， is it the mechanism。Picks。

An outcome making one as big as possible。Okay。So what's going happen if I bids truthfully。

What it wants to have happen， habits， right？So if it said right， So what is it。

 what does it want to be optimized， What I want to be maximized is it's its value plus the sum of the other bids。

And if it sets B equal to VI， the mechanism， by definition， will maximize sum of the bids。

 but that Ih term then is equal to the VI。So this， but another way， this objective function。

And the one that I cares about become the same when it bits truthfully。

And that's really where you see this internalizing the externality。 Okay。

 so the designer objective and the bitter objective actually become one。So setting B。Equal to V。

Causes this。To happen。So that's the VCG mechanism。And again， with the right intuition。

 the right approach that externalities are a good bet， good first try for the payments。

 The proof actually isn't that hard。 But this is really one of the you know。

 most important reference points in mechanism design theory。Could you see。What was the question？

Picking evaluation， maxim something。It doesn't get to picket's valuation。 It gets the picket bid。

Picking the bid to be might as that。Because then what's in one。The objective function in one。

Because the same as the objective function that VCG maximizes。

So the optimization problem that it would like to see solved from its perspective is exactly the one that the mechanism solves。

Questions。Alright。So I want to give you。Another way to think about these payments。

 which is sort of nice。Just as a Sandyche this internalizing the externality notice all the way back to the victory auction。

 we saw this idea。 so we have this highest value bidder。If it didn't show up， who would win。

The second highest bidder， okay， the second highest valuation bidder with the valuation of V 2。

 So by virtue of one showing up， it took the good away from that bidder。

 And so that caused a surplus loss of V2 to the rest of the collective。 Okay。

 and that's exactly its payment。So let me give you a different way to think about this payment。

 which is also。You说。So let me just rewrite。The payment。

All I'm doing to the formula I had on the board before is adding and subtracting I bit。 Okay。

 I bid evaluated on the chosen outcome。So if you do that。

 another way to write exactly the same number。Is I can think of the payment as basically。

 you pay what you bid， except they give you a rebate。 I'll give you some back。So if you want。

 you can think about the victory as you pay what you bid。

 except I give you a rebate equal to the extent that your bid is higher than the second highest bid。

 give you a rebate of V1 minus V2。So you can generalize that。

So you pay your bid like in a first price style auction， but I'll give you some back。

And what do you get back？Your rebate is the extent to which your presence increased the surplus in the environment。

Okay。So， again， like in a single item auction， if you're the highest value person。

 if you weren't there， the surplus would be V2 with you there， the surplus is V1。

 your highest valuation。 So the surplus went up by V1 minus V 2。

 And that's exactly the the rebate I give you back after you pay your bid。 Okay。

 and that's a general principle。So you pay less than your bid exactly the extent to which you increase the surplus。

One of the reasons I want to mention these couple interpretations of payments is it makes it particularly transparent why the payments have two properties that we want。

 Pro ask you to verify in the next exercise set。 First of all， the payments are always non negative。

it's never the case that the designer is paying the bidders。

 The bidders are always paying the designer。 like in all the examples we saw。

 And it's going to be the case that truth telling bidders have non negative utility。

 which is equivalent to you never pay somebody。 You never ask someone to pay more than what they bid for the outcome。

 Okay， so that's going to be easy given what I've told you in the past 10 minutes。Allright。

 so what's the takeaway。From all this VC G mechanism is in discussion。Well， the upshot is， is that。

 you know， if we jettison。All practical concerns， including computational trackability。

 Then in principle， in insanely general abstract environments。

 we can still do surplus maximization with this extremely strong incentive guarantee。

 dominant strategy set of compatibility， okay。So upshot。In principle。Can always do ESIC。

Surplus maximization。Allright。月1月是。No， that's one of the things that's that's easy given given the second。

 That's， in fact， that's one of the main reasons I talked about the alternative interpretation。

 that's what。Yes， good， excellent point。 So let me， let me， let me summarize the， the comment。嗯。

I may have a era what I needed。Yeah， okay， so you'll recall that in the middle of our proof。

Establishing。I know here it is， good。So the comment was， well， you know。

Our D S I C proof carries through， no matter what the second expression2 is。

 As long as it's independent of bitter eyes bid， as long as bitter eye can't influence it。

 it doesn't matter what that number is。Therefore， in particular。

 we could just add some arbitrary constant to bitterize payment。 Okay。

 and that wouldn't change the incentive compatibility properties。

 That if you think about it was actually true back in the single parameter case as well。

 I was just always normalizing things。 So losing， this is back when we had a well defined notion of losing。

 losing would give you a payment of 0。A rather bidding0 would give you a payment of zero。

So the comment was， well， you could have anything else here。 So why did we choose what we chose。

And I mean， so there's a couple of reasons。 One is just conceptually。

 the payments I just gave you have a number of nice interpretations。

 So they make good economic sense。 and they're well motivated。 But on a technical level。

 it's true that this constant is chosen just right。

 So the payments are guaranteed to be non negative that it's from the bidders to the seller。

 But then also you have guaranteed non- negative utility for truthful bidding。

 So it's sort of the sweet spot right between those two。

 But the fact that all these happen in the same place is not an accident。被告了。Alright。

 so in principle， D S I C surplus maximization always an option。 In practice。

 doing this can be really， really hard。Okay， and to drive that point home。And also。

 sort of segue into some more applications。 I want to introduce you to combinatorial options。So。

 contract auction。The main difference between what we've been talking about so far。

Is that there's multiple goods。 Actuallyly， we've talked about situations with multiple goods。

 But here， the multiple goods are not all the same。They can be different。

And different bidders have different preferences for different goods。 they need not be consistent。

 right， So in some sense， even in sponsored search， we had multiple goods。 We had slot 1。

 We had slot 2。 We had slot 3， but the bidders all agreed on which was the best and which was the worst。

The higher the slot， the better。 So we could still shoe hornn it into a single parameter environment。

 Now， we don' get applications where you can't where the goods are fundamentally different。

 Some bidders will like some more， other bidders will like others more。Yeah。All right。m。So。

 it's a little hard to know what to say about common auction。 On the one hand。

 they're super important。They've generated you know， hundreds of billions of dollars， if not more。

 through dozens， if not hundreds of auctions for selling off wireless spectrum over the past couple of decades。

But they're extremely hard， they're very hard to do well。 So in fact。

 they're pretty easy to do badly。 one of the early spectrum auction， this is in New Zealand， 1993。

 the consultants projected revenue of $250 million。 they got 36 million。

 so they got like 13% of what they were expecting because of a poorly designed auction format。

So Wednesday is when I'm really going to of drill down on， how do people solve these things。

 what are thought to be good and bad auction formats for actually doing this。

 But for the rest of this lecture I just sort of want to introduce you to common auctions and the reasons why they're so difficult。

Okay。Ch。So n bidders as usual。Maybe think of these bidders as， you know， Verizon。

 AT and T and a few different regional carriers。Is it said M， capital M of M goods？And， you know。

 a few of these goods might be， you know， the same。 But in general， these goods are different。

 Think of a good as being， you know， a right to broadcast at a given frequency in a given geographical area。

 So， if you vary the frequency or you vary the area， you get a different good。So， outcomes。So。

 you know， the general mechanism design problems we just talked about is that's certainly general enough to discuss the problem of surfpl maximization here。

So the outcomes， they're gonna， we're gonna go back to being n vectors。

 but there's not just one type of stuff。 So each component of our n vector will just say which goods it's called the bundle。

 Which bundle of goods does bitter I get。Okay。Now， in principle， our formalism。

Allows bitter eye to have valuation for every conceivable allocation of goods to the bidders。

 And there's a lot。 if you think about it， the size of omega is quantity M plus 1 raised to the M。

 It is a lot of these things。😊，But we're going to simplify it a little bit。

 We're going to assume that a bitter eye only cares about the goods that it gets。

 We're not going to allow it to have an opinion about who who gets what，Of the other goods。

So how many private parameters does a given bidder have in this model。Yeah。

 which we're calling little M， so 2 to the M。Get through the little M。

We're allowing it to have a separate maximum willingness to pay for each subset。

 each bundle of goods that it might get， not as big as the number of allocations。

 which is M plus one race to the M， but still an awful lot。Okay。So generally。

 one does impose some assumptions on these functions。

It depends on the context we'll talk more about this Wednesday。For now， let's just say。

Let's just normalize it。So your value for the empty set is 0。

 And we're going assume something called free disposal， which means if I give you more goods。

 your value can only go up。O。The surplus objective can be simply expressed。

As maximizing over the bidders。Of their values for the bundles that they get。Okay， and， of course。

 as you'd expect， each good can only go to one person。All right。

So this is a special case of a general mechanism design environment。So the VCG mechanism。Applies。

And in principle， we could use it。To maximize surplus subject to dominant strategy and se compatibility。

So。I don't really know of an example in the real world where anyone's ever done that。

When you have multiple kinds of goods。So maybe while I clear some real estate。

 you think about some reasons why。You either couldn't or wouldn't。

Run the V C G mechanism to maximize surplus in a non trivialvi combinatorial option。ち。

There's not just the one right answer to this question， I should say。So what do you think， critiques？

Why either couldn't or wouldn't you do that？嗯。Ready to come here。Good， right。

 so one thing we've discussed already in the context of single parameter problems。

 So certainly we inherit it here is that even if you could get people to tell you all their private information。

 and it was correct。Surplus maximization could be empty hard。Okay，And so that can be intractable。

What else。There's both， there's something else which is in some sense。

 perhaps even more of a deal breaker and even more obvious。

 and then there's some things that are more subtle， but also quite serious。Good。

 so something that we never saw in a single parameter environment was just the difficulty of elicitation。

Right， so someone has2 to the M private parameters。So if M is 20， this is a million， right。

 And even if you want to tell me truthful bids for all of your million valuations。

 I don't want to listen。Okay， I don't want to hear it。 but I mean， realistically， of course。

 bidders aren't willing to do this。 It's， it's really the bitterders that。You know。

 won't and can't do that。OkayAnd again， that did not come up with a single parameter problem。

 if you only have one number， of course， there's no complexity difficulty in just reporting it here with so many parameters。

 there is， So this even before we get to the point of computing anything。

 just gathering the data is already infeasible。Okay。So those are the two that I wanted。

The class to come up with just off the top of their collective heads。So all right， major challenges。

And I'm going to do this， sort of， from most。To sort of most obvious， to least obvious， possibly。

 maybe also most serious to least serious。Worthy of caps。

So this is a complete non starter in practice。 I think this is the number one reason I don't really know of people that have seriously considered running VCG options for a significant number of goods。

 Okay， I think this is where just， you can't even get， can't even get off the ground。So。

And it's not just about the VC G mechanism。 Notice。

 it's really about any direct revelation mechanism， VC G mechanism or not。 Okay。

 so it's just hopeless to ask people for everything that they know。So an obvious approach then。

 and what is done， as we'll elaborate on on Wednesday。

 is you ask bidders for relevant information on a need to know basis。Okay。Now。

 we haven't talked about any auctions like that yet， but you're familiar with one。So， you know。

 there's another implementation in effect of the sealed bid second price option。

Called the English auction or an ascending auction。

 this is what you've seen in the movies where there's an auctioneer and people bid。

 and this price keeps going up and up and up and people raise their hands And what happens in one of these English auctions。

 The auctioneer keeps raising the price。 and people you know， dropped their hands。

 And when there's only one hand remaining， the auction terminates， that's the winner。

 and the price is whatever it was when the second to last hand dropped out。

So just like in a second price auction， there's an obvious way to play in an English auction。

 which is as long as the current price is less than your value， stay in。 Why not？ You might win。

But as soon as the price goes over your value， drop out because if you win。

 it's gonna be a price higher than your value， your utility will be negative。

If all players play in that obvious way， then the outcome in selling price of this English auction is exactly the same as the second price auction。

 highest valuation wins charge the second highest valuation。 Really。

 the victory auction is just the revelation principle applied to the English auction。

 If you want to think about it that way。So you can do that even for a single item auction。

 even though in some sense， you might want to， but you don't need to。

 complexityplexity considerations don't demand it here with so many private pieces of information。

Demands it。 Okay， there's really no choice but to use some kind of so called indirect mechanism。

There are some bonuses。 I mean， this is really the key reason。

 The key reason is that direct revelation is a nonstarter。

 but there are some other bonuses of not using direct revelation。

 Maybe some of you wrote about this in your first exercise set， critiquing the revelation principle。

 But so， for example， sometimes people are worried about privacy。

They don't want to tell the auction or all of their private information。Al。

 this shows up in an English option。 right， Think about it。In a sealed bid， second price auction。

 you have to， if you report truthfully and you win， then the seller， the auctioneer。

 knows what your maximilllineiness to pay really was because you wrote it down an envelope。

 you gave it to them。What about an English auction。Suppose you win in an ascending English auction。

 Does the auction you learn， the maximum you would have been willing to pay。What have they learned？

Yeah， they learn a lower bound than what you'd be willing to pay。

 which is the second highest valuation。 Okay， so if you they sell to you for 100 bucks。

 maybe you were right at your limit， Maybe you would have paid 1000。 They're none the wiser。

So this is a second order reason why， you know， people also like non direct mechanisms in this context。

 although， again。You know it's really just sort of gravy。Okay。

So there's some really nice work in the theory community。

 which I've covered in sort of other versions of this course。

 which says that at least in the worst case， you cannot do any kind of。

 you cannot even get close to maximum surplus without eliciting an exponential amount of information。

 Okay， so in the worst case， this。😊，You know， exponential complexity doesn't go go away。

 But as you'd expect， these iterative options do save you a lot， especially in practice okay。

So that's  point one。And then the other one that was raised， which is even when one。Is not a problem。

So why would it not be a problem， Well， for example， if it's a single parameter。

 then one is not a problem。 It's easy to just reveal your private info。

Then maximizing surplus can be in Phart。So this is something you already know well from previous discussion。

 And like with point number one， if this isn't really a critique of the VCG mechanism。

 neither of these are， it's really just pointing out how difficult know trying to solve these comm as really is。

 So any mechanism， if it's going run if it's gonna be computationally tractable。

 cannot maximize surplus exactly。 And indeed， in practice， really， there's no choice。

 you have to give up on exact surplus maximization。 So people in effect。

 they' hoping that they're close to surplus maximization。

 it's a little hard to check if you think about it because even after the fact you don't actually know what people's values are。

 So how would you convince me that something is or is not surplus maximizing。

 But there is theory that's helpful here it identifies conditions on valuations under which options will get you at least close to 100% surplus。

 But again， both of these two things， you know， full elicitation and full surplus have to be relaxed to get any kind of working implementation。

All right， so here's the subtle point。Which is even when neither one nor two is a deal breaker。Yeah。

You know， maybe you're thinking， well， when would that ever be the case， But there are situations。

 right， So maybe you have single parameter bidders and you have a small problem。

 maybe you only have like 10 goods and 10 bidders， okay。

And this are already nontri for people to implement。 Then the computational problems。

 you can just solve them by brute force search or integer programming or what have you。 Okay。

 so they're still n be complete。 The complexity doesn't kick in。

 Let's say you're at small problem sizes。Even then。

And now I'm going discuss a critique of the VC G mechanism itself。

 rather than the problem fundamentally。The VCG mechanism。Can have some bad properties。

You can to have bad revenue properties。Can even have， despite the fact that it's DS SI C。

 It can have weird incentive properties， which I'll elaborate on next。Okay。

So we've sort of been talking about DSIC as a holy grail so far， and in many senses it is。

But in this context， some more extra properties that you really want show up。

 And the V C G mechanism does not， in all contexts， have them。me you example。

Let's just say two goods。Okay。Bitter one。Only wants both。Okay。

 so this year had a problem on problem at one， which was like this。 Okay。

 we're a bid wants a set of items， and it has no value if it gets a strict subset。So bid1 wants both。

 So that means。Its value for A B is one。 And again， in the motivating application。

 think of one here as like a billion dollars。And 0， otherwise。And Bider 2 only wants good A。

 It's much easier to please。So V2 of A B is V2 of A。Just one。And again， zero otherwise。

Oliba is an exercise for you to convince yourself。In this case。The VCG revenue is one。

Which is also the same as the max impossible surplus， which is great。Okay。

So no issues with the VCG mechanism for this simple， too good。

 too bitter case that's exactly what you want。Which is give， you know。

 it satisfies one of the bidders。 It doesn't matter how you break the tie。

And the winning bidder pays its full valuation， pays billion dollars。Now， here's what's unsatisfing。

 What's going to be more than unsatifing。 Here's what's going to be a deal breaker。

Suppose I had a bitter three。I make the situation more competitive， it would seem。

Bider3 only wants good be。Okay， sort of the。Complement of bitter2， It only wants to be。And again。

 it's value for B is one。So what's the new Mac surplus？2。Right， so now。Obviously。

 the high maintenance bidder， Bider 1。Lepped out in the cold。

 We're gonna give good A to bit 2 and good B to bit 3， surplus 2。Any guess。

 this isn't completely obvious。 And I'll probably put it as an exercise。 Does anyone see on hand。

 what's going to be the revenue， the new revenue。 So the surplus doubles to 2。 That's great。

 What happens to the VC G revenue。Do I be able to compute it in real time。It's not totally trivial。

 does it stay at one？Why to see that？Why。I was just the second analogy for the House。呃。That nice。

Like surplus the eye of the world。Excellent point。 So if you use the second interpretation of ECG prices where you pay your bid。

 but your rebate is how much you increase the surplus。Well， think about，2 or bit3。

 doesn't matter which they're symmetric。RightSo before Bita 3 showed up， the surplus was one。

Then Bi 3 shows up and the surplus jumps to two， one up by one。So then what does it have to pay。

 What has to pay It's bid 1 minus surplus increase it affected， which is one leaving you with 0。

So that's the easy is your revenue。对。Revenue drops。To zero。

And this is a new phenomenon we haven't seen yet。 Okay。

 this did not happen in the single parameter problems were talking about。

You might want to just think about the victory auction as a quick exercise。

RightSo imagine you have bidders with some valuations， vi a doing doing whatever it's doing。

 I had one new bidder with some valuation。 The revenue can only go up。

Either nothing changes or this is the new highest bidder。

 and now the new revenue is the new second highest valuation as opposed to the old second highest valuation。

So this is a new twist。Which is， which is you know， quite serious critique。 actually。

 the V C G mechanism for contra auctions。 And it's a critique。 actually， in many senses。

 I'm sort of showing you the tip of the iceberg。I guess there's two things that are， you know。

 obvious here and really problematic。 First of all。

 there's this seemingly competitive market where you make literally zero money。 Again， again。

 it's not that in these government auctions， the government's really trying to maximize revenue per se。

 Really， the first order goal is still surplus， typically， but。Usually。

 you have some kind of revenue considerations。 and this is a problem。Secondly， it's just。

 you don't want， you don't want a mechanism that has this non nonmonetonicity in the revenue。

 If new people show up， you want revenues to only go up。 If that fails， like it does here。

 then there's all sorts of problems with collusion， with sh bids and so on。

 I'll ask you to explore this in the exercises。 So this example leads to many incentive problems in the VCG mechanism。

O。So final challenge。Which again， is something we that just hasn't come up before。So we argued。

In our first point。That direct revelation is absurd。

So we have to interact with the bidders over rounds。 like you do in an English auction。

 like you do in ascending auction。 we really have no choice。

And when you go beyond seal bit auctions and allow rounds interaction。

 especially with multiple goods， there are new opportunities for gaming the system。😊。

Let me give you an example。There is a study by Crampton and Schwartz。Oh。

About cousive bidding in the earliest FCC a。So as far as the history about how things like spectrum got allocated。

 obviously， this was being done before wireless。 you had to do it for television a long time ago and so on。

 So for a long time， it was just purely political process， So itd be some company。

 So it was giving away for free， but buy just purely political process。

 So all the different big companies would hire all these lobbyists and， try to know， sweetweet talk。

 D C and sort of giving them some license for free。And， you know。

 that both one didn't seem that fair。 And also， just once， you know， new technologies came out。

 it was just too onerous。 There were just too many people who needed licenses to。

 to do it in this way。 So they switched to。Awarding them for free by lottery。And these license。

 these are valuable licenses。 and you could resell them。Okay， so this was like a chance for。

 you know， a good for free that you could resell for millions of dollars。 That didn't work so well。

 turned out。Actually LED to some of the fragmentation in the spectrum。

 which maybe is one of the reasons why the US phone market this day sort of lags behind certain other countries。

 So that didn't work very well。 So in the in the early 90s， they're like， okay。

 we need to have a smarter way to to allocate these licenses。

 And that's when they started to get interested in auctions。

And so this paper reports on some of the auction that happened in 94，95。And so they talk about。

 you know， various ways that bidders can collude。When you have an auction that's indirect。Where。

So the FCC a they were discussing。 I think there are 94。What you did is you had a bunch of goods。

And you can even think of them as being identical goods。 They weren't。 But for for the story。

 you can think of them as being identical。And what you would， what you did basically is you had。

 you ran in parallel in the same room， if you like， ascending slash English options on all of them。

Okay， so each one had its own auctioneer and its own price。

And they could go up at different rate so they could be at different prices at different times。And。

And then at the end of the day， you know， the highest bidder on each good just won that good。 Okay。

 so they were just sold separately using simultaneous ascending options。And one very cute。Haack。

That was used。So these bids are in the hundreds of thousands of dollars， okay。So， you know。

 if you bid 383000 versus 383172， you know， it's all the same to you。Right。

So that gives you these lower order digits， this bandwidth to communicate with the other bidders as the auction proceeds。

 Communicating before the auction。 that would be illegal。But you can bid over you want a bit，So。

 you know， one example。Was there were these two。 And this was sort of a not very competitive a。

 which is why maybe the callusive bidding was sort of particularly effective。

So there is two regional characters。Carriers。US West and McLeod。And US West really wanted Rochester。

 Minnesota。Okay。And。Rochester， Minnesota， you know， it happened to be licensed number 378。

And this annoying McLead company kept battling with US West for Rochester， Minnesota。

 So they go back and forth， higher and higher bids each round， right。So， US West got annoyed。

With this competition over license 3，78。 And so it shows a bunch of licenses it had no interest in at all。

But that McLead was currently the high bidder， and no one else was even fighting McLead for these other ones。

 It just had a won， basically。 but the auction was still open。

And so US West put a bunch of bids on these other licenses it didn't care about。

 which McLead was holding。You know， bids are the form， H72000。When I say it was 378。

And the other one， you know， whatever its current bid was， it would up it by 10 grand and tack on a。

 you know。Was it 378？Okay。So， you， it was very clear signaling stay out of 378 b。And it works。

It worked。 Very few bidders actually used at least detectable。 So I mean。

 the detectable collusion in this paper was very small。 It was not many of the bidders。

 but the bidders who used it successfully got their licenses at what's thought to be a big discount。

 almost 2 X。It's very effective。Now， there's a very easy fix for this particular problem。

Which is what？Just make the big increments big enough。So you have to bid it in increments of， say。

 10，000 or whatever the appropriate unit is for the goods that you're selling。Allright， But， I mean。

 you know the game， right， you know， who knows what else you could do。 Okay。

 so the high level point here is that we're forced to depart from the direct revelation world。

 We have to have as that are indirect。 that interact with the bidders over time。 And as a result。

 there's way more design decisions， way more opportunities for strategic behavior。 So on Wednesday。

 I'll talk a little bit more about， you know， what are the current a formats。

 the cutting edge and these spectrum options。 See you then。😊。

