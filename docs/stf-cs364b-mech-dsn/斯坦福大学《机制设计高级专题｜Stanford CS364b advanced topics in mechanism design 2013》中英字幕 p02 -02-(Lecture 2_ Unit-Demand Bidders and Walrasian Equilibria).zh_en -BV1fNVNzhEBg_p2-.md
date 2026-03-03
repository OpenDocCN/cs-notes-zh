# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p02 -02-(Lecture 2_ Unit-Demand Bidders and Walrasian Equilibria).zh_en -BV1fNVNzhEBg_p2-

人究。Okay， welcome back。So I promised to say a little bit about you know course expectations and that kind of thing。

 there'll be some similarities， but also some differences from the fall。

 so there'll be no so in the fall we had exercise sets and problem sets， and that was it。

So no problem sets， probably many of you will not miss them， but so no problem sets。

 those were the hard ones。Instead there's going to be know so the focus of this class。

 you know sort of today notwithstanding， the focus of this class is on recent research。

 like I said last five years， mostly And so it's a good opportunity to do a research project。

 So maybe around the fourth week of the class or something like that I'll post a list of various research papers that I think might be fun to read in more depth and so the deliverable will be some kind of research report。

 say ballpark 15 pages， something like that know if you want you can just sort of a paper summary paper synthesis but for those of you that are looking for kind of research problems to work on this is another natural opportunity to spend to spend some time on that exercise sets there will be some including starting this week exercise set number one's a very very variablebones webp page at the moment。

 but exercise number one is linked to from the web page and those have the same format as last quarter meaning only once a week I actually think that'。

Probably even more crucial for the first part of the class just to keep you engaged with the material and just to keep you sort of to get you solid on all these concepts。

 I'm probably going to have them tail off once we get to the midpoint of the quarter and where I'm expecting you to spend more time on the research projects。

 so expect kind of maybe four or five exercise sets of a similar length to the fall and then maybe you know ones that have say two to four exercises for the second half of the class。

 something like that。Do we turn in the exercise sets or are they just for practice then you turn them in。

 Yeah， Yeah， And there's， if you look at the PF on the on the I'm not gonna bring hard copies。

 but the PF has full instructions about， you know， exactly， you know， what the honor， you know the。

What resources you can use and， and working with other people and so on。

 Those of you who took it in the fall， it's the same policies as in the fall。And right。

 so then also like last quarter， we are videotaping the lectures。That said。

I am thinking of attendance as roughly required。 We're a small enough group。

 It would be sort of a shame if half of you didn't come just to watch it on YouTube later。 You know。

 I know I know some of you are gonna have interviews and stuff。 and I realize there'll be conflicts。

 but barring kind of hard conflicts。 I do actually expect you to to attend the lectures and use the use the videos for review or for the few lectures that you absolutely have to miss And there will be lecture notes。

 just like last quarter， also just like last quarter。

 I'm not really gonna promise a bound on the latency of the lecture notes。 sometimes they'll be fast。

 if I have a lot of other deadlines。 they may not be so fast。 So I'll do my best。

 but I'll get them out when I can。 And the website， as usual。

 will have sort of related readings to the lectures。 I'll get that up probably tomorrow。Questions。

Yeah。we're taking this class for credit， yeah。Past failure mean。Yeah。

 you do not have to do the research project if you're taking a pass bill how would you compare this in terms of workload。

You know， it's hard for me to say。You know， I'm nervous of saying anything on the record about that because there's a little apples and oranges。

 you know， with the research project， which to， you know， a large extent， you know。

 I hope some of you will feel motivated to work extremely hard on the research project。But， you know。

 and on the one hand， there are these brutal problem sets in 3，64 a。 but there are also， you know。

 groups of size 3 that you can work on them together。

 So that makes it a little hard for me to do the arithmetic。 as far as what I'm shooting for。

 I'm shooting for it to be a little less time consuming overall。

 Feel free to let me know on the evals if I succeed or not at the end of the quarter。 But you know。

 last quarter， I imagine was pretty time consuming。 And this quarter， I mean to be rigorous。

 but not quite as time consuming。But we'll see， your mileage may vary。Other questions？All right。

So hopefully now it's sort of clear what the plan is so we want to look at more interesting。

 more complex scenarios of allocating scarce goods to people in a way that gets good performance in this case。

 good surplus， and ultimately our focus is on having ascending auctions。

 which are expos and compatible， since your're bidding leads to good performance and or simpler polynomial time and I left you last lecture with the observation that a prerequisite is you need to at least have good direct revelation dominant strategy mechanisms before you could hope to have this。

So that's the paradigm I want to start exploring for scenario number three。

 the more complex scenario in this lecture now。So scenario 3 is going to be a strict generalization of scenario 1。

And it's still going to be incomparable to the added evaluation， scenario number two。

So we're gonna have， like scenario number  two， we're gonna have non identical items。

And like scenario one， we're going to have unit demand。Bitders。Or valuations。By which I mean。

Bter eye has a private value。VIJ for Good J。And we define bitter eyes value for a bundle of goods S。

So in the additive case， it was the sum over the goods in the bundle。 here。

 It's going to be the max over the goods in the bundle。So again。

 unit demand means you're not interested in more than one item。

 but you do have preferences amongst them。 Houses， for example， might， you know。

 as often used as an application here， So you're not going to buy more than one house potentially。

 but there are some that you would be willing to pay for more than others。So the goal。

 which is actually to take all of this lecture and a little bit at the beginning of next lecture as well next week。

 So， but the following goal is to construct an auction with all of these properties。4 scenario 3。

 that turns out to be a really interesting problem。 Okay， the solution is really nice。

 but we have to develop a reasonably deep understanding of the scenario to justify the eventual solution。

 okay。So， as we said， the sanity check， just to even wonder if this exists for unit demand bidders and different items。

 Well， do at least have a direct revelation DI implementation for scenario number 3。And we do。嗯。So。

First， I think I put this on a exercise in the fall。

 but I want to point out that there's a very strong connection between seeking to maximize surplus with unit demand bidders。

 unit demand valuations and bipartid matching。Okay。So， suppose。

We just wanted an algorithm to maximize surplus。 So If you want。

 think of this as the allocation rule in a V CG mechanism。

 So suppose you actually knew all the V I Js。 And you just wanted to compute a surplus maximizing valuation。

But because bidders are unit demand， it's pointless to give a goodder more than one good。Okay。

If you gave it two goods， it's just going to throw out the one that it doesn't that it likes less anyways。

 Okay so without loss， each bidder gets at most one good。

So to max surplus without loss of generality。And most one good per person。And of course， each good。

Only goes to one person。 You can't give a good to two different people。 Okay。

 so we can think of this as a bipartite graph with bids on one side。And goods on the other side。

And the edge weight。Is just equal to the valuation that a given bitter I has for the given good J。

Okay。Maximizing surplus is just maximizing the VIJs over all pairs IJ where bitter eye gets good J。

 so that just corresponds to computing a max weight bypartite matching in this graph。So corollary。

Maximizing surplus， ignoring incentive issues。Maximizing surplus with these unit demand valuations is equivalent to max weight。

Bparttheid matchingshing。So something I hope many of you have seen at some point in your education is a polynomial time algorithm for max weight bypartite matching。

 You can solve it using linear programming。 There are lots of combinatorial algorithms for， as well。

In fact， next week， we're going to see， you know， possibly one of the simplest algorithms known that computes em max weight bypartite matching。

 Okay， up to an epsilon， but it'll still be a very simple algorithm that shows that this is a computationally tractable problem。

 It's not trivial。 I don't teach it in my undergrad algorithms class， for example。

 but this can be solved quickly。All right， so， so what？ what about incentives。Well。

 something that I hope you might maybe remember from last quarter。Is that the surplus objective。

 if you want to maximize it with a decent mechanism， is a very special objective。

 We basically have a universal solution。For doing surplus maximization in a dominant strategy way。

 And that's called the VCG mechanism。And so again， what I'm doing here is I'm doing a direct revelation D6 solution to this problem as a sanity check before we move to the ascending implementation。

 which is the hard part。Okay， so what is the VCG mechanism， Let me jog your memory。

I guess I should say， so the VCG mechanism is defined super generally。

 this is a just very powerful tool。 If you only care about dominant strategy implementations and surplus maximization。

 kind of always gets you those two properties。 Very often， it's computationally intractable。

 But one thing that's special about scenario 3 is that it's not going to be computationally intractable。

 It's going to be polynomial time implementable because surplus maximization is just a matching problem。

😊，So it's direct revelation。 So you just ask people for their private information。

So you collect the BI Js。Now you're thinking of these as being truthful and you want a surplus maximizing outcome。

 so it's clear what your allocation rule should be。 you just take the bids at face value。

 assume the valuations and compute the thing with a maximum surplus。

 That is the second step is you compute a max weight bipartite matching with the bids being the weights。

So here's the allocation rule。So you compute the max weight matching。With respect to the bids。

And then you charge the right prices。 Okay， and I'm going to be a little informal about the VC G prices right now。

 Okay， we did go through them in detail last quarter。 I'll remind you about the actual formula。

 a little later。But the gist is you charge people their externality。Okay。So charge each bidder。

 it's externality。Well， I mean it's externality。 I mean， like， well， first。

 imagine that this bitter I didn't exist。 and we only optimized for the other n -1 Biders。

 We get some number。Now， suppose instead we optimize jointly for all n bidders。

 and we just look at how much of that surplus the other n -1 bidders get。That's only lower number。

 Okay they're going to get more surplus if I optimize specially for them。

 So the difference of these is a non negative number。

 and that's the payment under the VCG mechanism of this bidder。

 Why do you charge people their externalities， The externality can also be thought of as the difference between the social objective function of surplus and the individual objective function of just what you get minus your payment and we proved last quarter was a simple proof that these payments align those objectives。

 and therefore， indeed， truth or revelation is a dominant strategy with these payments。

So I just wanted to remind you conceptually what these payments are。

 I'll give you the formula when we actually need the formula in a little bit。Okay。So this is good。

 So this means the sanity check passes。 We want the sending implementation。 We asked。

 is there at least a polynomial time， decent implementation， Yes。

 the reason we can implement B C G and polynomial time in this particular case。

 So we pass the sanity check。Now。The hard part。With interesting part， perhaps。

So I guess it's still here。And so the goal。Is just to get these three properties for scenario number three。

So high level design plan。I I should also mention， so to see so this is so scenario one that was identical goods and unit demand。

 that's the special case where these VI Js are independent of I well sorry， independent of J。

 where all bidders have the same VIJ for every good J。 sorry。

 each bidder I has the same VIJ for every J。It's incomparable to add evaluations because here it's unit demand and that's just a different thing than additive。

Okay， so we're generalizing scenario 1， We're incomparable to scenario 2。

 but somehow we'd still like to apply the same type of thinking when we design the sending implementation and the two optionsuctions we've seen so far are based on you start prices at  zero。

 things are overdemanded。 People want lots of goods。

 but then you increase prices until supply equals demand。

 So that was true in the original English auction where you had a supply of K。

 It was true in the parallel English auction， where had a supply of one for each of the M different goods。

So it's going to be I'm not even going to tell you the final auction until next week。

 but at a high level where we're going。Is he want to initialize？Pak equals 0。

And we want to raise prices for the various goods。As needed。Till supply equals demand。Okay。Al right。

 so what does this mean， Okay， I want to drill down on this this。

 So this is like our 30000 foot high level idea of what this thing might look like。Alright。

 so supply is clear。So we have one copy of each of the M items。What's demand？

You give me a vector of prices and say that these prices with single item would I most。Good。

So in the original English auction， where there was only one kind of good for sale and we were looking at a given price。

 We just asked people， do you want it or not。 Okay， so every bidder contributed to 0 or 1。

 We added up how many people wanted it。 We just compared it to K。 Ca was a yes， no question。

Sort of the same thing with the parallel English auctions for each English auction， it was a yes。

 no question， you want this or not。Okay。Now， with unit demand bidders here in different goods。

At the end of the day， we know a bidder is only going get one item at most。

So we're actually not going to ask it a yes， no question。 We're going ask it a richer question。

 We're going to say， well， given the prices that we've currently set for each of the M items。

 which one's your favorite。Right。What his favorite mean， well。

 it means your net utility for is the highest， your value for it and minus the price you'd have to pay。

And so now a bitter instead of just contributing， you know， one number。 It contributes。

 in some sense， one number to one of the goods， exactly one of the goods or most one of the goods。

So rather than overall demand， let me just say demand of I， a bitter I。Is going be itss fave good。

At the current prices。Q。And again， by fave， I mean。Highest VI J minus Q J。And of course。

 if all of these are negative， then the bidder says， I don't want any of them at the current prices。

 so your demand can be the empty set as well。So with that notion of demand。

 we can start thinking about， you know you know the supply equal demand or not。

 So we look at a good if it's more than one bidder's favorite， then it's overdemanded。

 If it's a good that nobody wants， then it's under demanded。 And so certainly if you're overdeded。

 that suggests the price is too low， suggests maybe you should raise the price。So again。

 the full description have to wait till next week。 But I wanted you to kind of have in mind。

 what's the know general form of the ascending a going to look like， What are we shooting for， Okay。

 so this is， this is sort of how we're thinking it's going to work at a high level。Good。Now。

So another goal， in addition to having this kind of description。We want sincere bidding。

By which I mean， every time we ask a bidder for its favorite good。

 it tells us which one is its favorite with respect to its actual valuations。We want sincere bidding。

To terminate。In the VCG outcome。Okay。Now。I've actually， if you've been。

 if you're paying close attention， you notice， actually。

 I just made this a slightly stronger goal than it was before。 Okay。

 so what I said our goal was was to have an ascending a。 That's fine。 Epic， that's fine。 And I said。

 I wanted sincere bidding to lead to maximum possible surplus。Now。

 an outcome of a mechanism like VCG is two things。 It's an allocation， it's a payment。

And it's certainly the case in the VCG outcome， the allocation is efficient， it's maximum surplus。

 and the payments are whatever there are。So I just strengthened our goal from wanting some outcome that has maximum surplus at some prices。

 They actually wanting a maximum surplus outcome at the VCG prices。You might wonder why I did that。

 Turns out it's necessary， but I'm not going to tell you till a future lecture why it's necessary。

 You might say， well， why don't we have a， you know。

 surplus maximizing allocation at some possibly different prices。

 Turns out that approach is doomed to failure。 Okay， if we want maximum surplus in an epic mechanism。

 it's going have to be through the VC G outcome， including the VC G prices。

So take it on faith for now that we're going to want this to be the goal。

 we want not just a surplus maximizing allocation， but we want the prices。

 a termination of our auction to be those of the VCG mechanism。 if we'd run it， which we not。

 but if we'd run it。 So we want to simulate the VCG outcome。Now， here's given that。

Here's the key challenge。 Okay， So again， the challenge given that what we're doing is confining ourselves to these very simple price ascending。

 make s demand mechanisms， on the one hand。And secondly。

 that we want to mimic the VCG prices at the end of the day。Is that， you know。

 this is not these VC G prices。 This is not such a trivial computation。

The VC G payment of a bidder is you charge it its externality。

 which is the difference of two different matching computations。 So basically。

 you compute the matching for everybody and then you compute the matching with I deleted and you take the difference of these two numbers。

 And that's the definition of the VCG payments。 so we know how to do it in polynomial time。

But that's not some just like closed form formula， or some easy thing to write down these VC G payments。

Whereas these ascending auctions， know， just these sort of simple ascending price raising things。

 it doesn't feel like they're doing， very complicated computations。

So it feels a little ambitious maybe to use this kind of very simple computational model。

 if you will， of these ascending auctions to compute something as intricate as these VCG payments。

 these differences of matching。O， that's why this seems， you know， at worst， hopeless or false。

 And at best， a little tricky to prove。 turnss out it's merely a little tricky to prove。So。

 key challenge。How to ensure。Prices of termination。Again。

 computed with these simple ascending procedures actually equal the seemingly rather complex VCG payments。

Okay。So here's the proof plan。Okay， but just to be clear， we will succeed in this。

 We will accomplish this。So today。What we're going to do is we're just going to focus。

On the VC G payments。 And we're going to understand that theyre rather simpler than they at first appear。

Okay， so we're going to characterize the VC G payments in a way that are much more understandable and much more plausible as the output of an ascending auction。

Next week， I'll finish the construction and actually prove you that an ascending auction can compute those prices。

So， today。Characterize VCG prices as。So this is not going to make sense。 This is， again。

 just a kind of。Give you a forward pointer。But we will do this today。I'm going。

 I'm going to introduce the notion of what was in equilibriumlib。

Which is the appropriate notion of market clearing prices for these matching settings。

 And we're going to show that there in some sense， a smallest there's not one while was is in equilibrium。

 There can be many， but in some sense， there's a smallest one。

And we're going to prove that the V3G payments are exactly the smallest while we're rising equilibrium。

And this will be interesting because while rise in equilibriumria are much more plausible outputs of ascending procedures than this difference of matchings。

And then tomorrow。sorryrry， next week。So next week。Aions such thats sincere bidding。

We're not going to prove directly that it converges to the VC G payments。 Rather。

 we're going to prove that it converges to the smallest。W rise in equilibria。

 which by our laborers today we know actually are the VCG prices。So it's sort of the forest clears。

 the big picture clear。So the end goal is an ascending implementation for these unit demand heterogeneous goods。

That's going to require simulating the VG outcome。And the topic for today is to understand the VCG prices in simples in the simpler ways of rising equilibrium。

So the rest of today。We do this。So what is a well rising equilibrium？So this definition can。

 you can make this definition very general。 I'm just gonna to give you the suitable notion for scenario 3 for unit demand bidders。

 Okay， here is how you define it for scenario 3。So you also hear these called competitive Eo sometimes。

So I'm going to breathe very the WE so it's a pair。So it's a price vector。Q。

 so a price for each of the M goods。And an allocation， again。

 we can think of allocations as matchings without loss of generality。M。So that。

The following conditions hold。The main condition is that everybody should be getting their favorite good。

At the current prices。So each bidder。A。Match to its favorite good。

So I'm going to use for a bitter I and a matching capital M。

 I'm going to use M of I to denote the good J that I gets。It's possible that I gets no good。

 Then I define this as the empty set and the value of an empty set is 0。

 and the price of an empty set is 0。 Okay， so in general， we could have more bidders than goods。

 We could have more goods than bidders。 Everything I say will be relevant either way。

So we have a bitter eye。 It's matched some M I， and M I should be its favorites。

Meaning it's an a max favoriteed in the same sense that we mentioned when we were defining demand。

Right。So Argm over J。VIj。Let me switch the notation a little bit。VI J minus Q J。Okay。我会这里面。We are。

 Let me actually， But so let me just。Let me be redundant and write a little extra or none。Or no good。

So in other words， M I should be empty if all these values are negative。Okay。So in particular。

 yourre。Every bidder should have non negative utility。Okay。That's what this ins。By itself。

 condition one is not interesting。Do you see why。There's some very stupid examples of Qs and M's that satisfy condition1。

Let give everyone nothing right。If you think of the Q's as plus infinity， then nobody wants anything。

 and you just hit M to be the empty matching。Okay， so that's not that certainly we wouldn't want to call market clearing。

So。The other condition is that a good J。Should go unsold。Only if its price is as low as possible。

 so its 0。Okay。And by unsold， you know， I mean， in M。Okay， so I mean。

 J does not arise as M of I for any bitter eye， That's what I mean by unsold。Okay。So。

It's new new definition。 We should get a feeling for it。 So let me tell you interpretation。

 why we might care some examples。So as far as interpretation， actually。

 these well raws equilibriumlib。 if you think about it， these are kind of magical。😊。

So forget about M for a second。 So's thing about Q。Right。So suppose you slap。

 So just the Q part of O is and equilibrium。 I'll call it you know， a price vector。

 O is an equilibrium price vector。 So suppose you just have one of those cues and you slap them down on the goods。

 okay。And now all the bidders just sort of walk up and they see these price tags on the goods。

 these Q of Js， right。And without coordinating at all， every， you know， theyre， you know。

 like on a shelf。 Okay， with a price tags。 And every bidder just walks up and chooses the one that they like the most。

 Okay， with no bearing to the other people。Okay， so everybody individually optimizes their own utility。

 according to the announced prices， the price tag X Q。Well， then you get， then you get。

 So assuming there's no， assuming there's no ties。You're going get back this matching M。 Okay。

 so in particular， nobody's going to choose the same good。 It's going to be no conflicts。

 despite the fact that everybody made independent decisions。So these cues。

 this is the sense of market clearing of these and nu you announce the prices。

 you let people do whatever they want。There's no conflicts， no good is overdemanded。

The only goods left on the shelf are those that were price zero anyways。

 so they really nobody wants them。So that's sort of how we often think about laws in equilibriumlibria。

 They are prices that just decouple individuals optimization problems。

 They can just solve them separately， and there's no conflicts in the market clears。

 So that's pretty cool。Why am I talking about these， Why might they have anything to do with， say。

 ascending auctions。Well， recall sort of our high level design plan。We're adjusting these prices。

Until supply equals demand。Okay。And so what are demands， demands our favorite goods。

So p's demands means essentially all goods should be demanded one。Okay。

So we're envisioning this auction terminating with prices that seems like they should look like aazian equilibrium。

So everybody picks their favorite good。 no good is over demandded。

You're only under demandded if the price was zero anyways。So looking ahead， the connection。

 the reason we're talking about these use is because if we run this high level idea of an ascending auction that we have with supply demand to completion。

 competing with these market clearing prices， that's going to be what why an equilibrium。Okay。

 so these objects are the natural termination point of the family of ascending auctions that we vaguely have in mind right now。

Okay， so that's why we're going to talk about。I mean， obviously this is， you know。

 this also says why。Why it's a good reason to talk about them because they let us understand VC G payments。

 But there's an even more intuitive connection。Okay， so some examples。

So let's look at a single item a。So this means we have one good。Maybe we have like four bidders， say。

And let's say the values of the bidders for this good are 10。8ight，7 and4。So what are the prices？

That rise and rising in equilibriumria， in this example。没是。Yeah。Have agree？So， it's not unique。

If you slap any price down on this item between 8 and 10。

The three people with the lowest valuation are not going to want it。

 and the one with the highest valuation is going to want it。Okay。So if everybody walks up。

 this guy's gonna take it off the shelf。The market clears， all the goods are sold。

 and these three bidders also have they， they can't get non negative utility from any of the goods。

 So they're also happy， having nothing。Okay。So， again， just sort of foreshadowing things to come。

What would be the price computed by the Viy auction or an ascending auction？In this single item。

 in this single item setup。It would be8， right， Yeah，8 plus epsilon for the English auction。

So essentially， just empirically in this example， the Vickery or English auction is computing as its final price。

 the smallest of the wallwa zone equilibriumria of this example。Un'clear what that means right now。

 but as we'll see that's a general phenomenon。If you try to charge people the highest Walwaian equilibrium price。

10， that would be like a first price auction。And that we know is not dominant strategy incentive compatible。

 that does not have good incentive compatibility properties。So at least for the single item oxygen。

 we're observing a correspondence between the smallest， the lowest， was and equilibrium。

 and the prices computed by incentive compatible auction。To just。Just remember that。

So let's look at another example。Because things can get a little more complicated。

So let's say there's two bidders。And three goods。Let's say the goods out number of the bidders。Yes。

And let's say the values are as follows。So for edges that are not in the picture。

 think of the value as being zero。So I claim that 0，1，0 is the。

Equiilibrium is a rise equilibrium price factor。Okay。So for that to be true。

 we would have to pair these red numbers， this price vector with a matching。So that the pair。

 the matching and the price vector satisfied these conditions。So。

How many matchings in this graph could I choose with this price vector。

That would result in a horizonizin equilibrium。At least two can I have a lower bound？

I have a conjectured。Strongger lower bound。How do people say three？How many people say it too？Okay。

 well， so hopefully the two that are here are sort of uncontroversial。So that and that。

Is going to be a matching， which。Makes things in equilibrium。So basically， this bitterder shows up。

 So the issue， of course， is I'm sure if you'll notice is there are ties， right。

 So it's not well defined to say a bitter picks。 It's， its unique favorite good。 Okay。

 They have to choose amongst them somehow。So one situation is where both bidders choose the lower of their two favorite goods。

Another situation is where they both choose the。Upper of their favorite goods。Those are both。

Or is an equilibrium？What's the surplus of those two matchings？No surplus is four surplus is four。

Yeah， surplus is four， 3 plus1 or two plus two。Which is also the the biggest surplus of any matching。

 in the example。So perhaps the controversial matching。Is this one？Where。

The first bidder picks its top good。And the second bidder picks it the bottom good。

So is that equilibrium？Why not？It fails condition2。Right so in all three of those matchings。

 of good is left unsold， it was kosher。 If the top good was unsold because that had price 0。

 kosher at the bottom good was left unsold， It has price 0。

 but it's not O if the middle good is left unsold。Because that is price one。

What what's the surplus of that matching that doesn't work？Three。

 so that was not a max surplus matching。So I lied a little bit， you know。

 when I said the magical I wasgenic Lib is people just show up and with no coordination。

 pick their favorite good off the shelf。 when you have ties。

 you do need coordination to break the ties。 if there's no ties。

 what I say is correct because everybody has a unique favorite good， but with ties。

 you do need this kind of coordination。😊，All right， questions。More executive smallest。Yeah。

 it's not to find it。Yeah。Hey， initially， well wise is in equilibrium weren't to。We'll get there。

All right， y， if you always prefer to pick non zero items among your ties because I of not coordination。

Well， it's okay。 So yeah， yes。 So it's actually the bigger issue。 I should。

 I should have actually been clear， which is the， the bigger problem is just over demandded， right。

 So the bigger problem is where the top bidder picks bottom and the bottom player picks up。

Right so theres like with this story where people just don't coordinate and do whatever they want。

 you also get this non matching where this bidder picks this good and this bidder also picks this good。

 So you， at the very least， need coordination to just prevent people from choosing the same good more than once。

The zero problem， maybe you can fix in some other way。

But coordination with ties is fundamental to a rising equilibrium。Yeah。你司机。Yeah。

 so that's related to this point。 Yeah， so I'm going to address that at some point。So the VCG。

 you mean the payments， they are unique。 We didn't prove that in the fall。

 We only proved it for single parameter problems， but I don't want to do it today。

 but we'll do it later。Alright， so。What I want to prove next is that it wasn't an accident。

That the matchings that worked had max surplus and the matching that didn't work didn't have max surplus。

 not an accident。 That's general。So this is going to be a version of the。

So called first welfare theorem， again， adapted for the current。Simple setting。

So first welfare E theorem， generally the interpretation here is that the outcome of markets are efficient。

 so it's something people。Obviously， argue a argue a lot about philosophically。 But mathematically。

 the statement here is very simple。Consider an arbitrary will rise in equilibrium with these unit demand bidders。

Then it must be the case that the matching M。Maximizes the surplus。

Only max surplus matchings participate in moreroian equilibrium。If think about it。

 this sounds sort of like good news， right because at some point we're trying to drive toward a connection between VCG outcomes and Wowa and equilibriumlibria。

 so it should sort of warm our heart that at least Wawas and equilibrium are fundamentally about Mac surplus outcomes as our VCG outcomes。

It's a proof。All right， so just some notation。So， you know， fix any oil in equilibrium Libia， Q M。

 like capital Q know the sum of the prices of all of the goods。So for all we know。

 M may or may not be max surplus， but something out there is max surplus， call it M star。

So by the Wariz in equilibrium condition。Every bidder is just as happy。

Getting whatever good it gets is M at the prices Q。

 as it would be getting the good it gets in M star at the same price Q。So by the way。

 why is an equilibrium condition？For all bitter's eye。So again， remember who。

M of I denotes the good that bitter eye gets in a given matching， if any， if that's the empty set。

 the value is defined as0 and the price is defined as0。So this is true。So that's just condition1。

 the was equilibrium。So some these over all I。Okay。Well， when I sum these overall I。

 I just get all of the edges of the matching M once。 Okay。

 so this summed over I is just the overall surplus of M。

There's going to be some stuff with some cues。Here， this by the same reason。

 this is just going to be the surplus of the allocation M star。Minus some stuff with some cues。Okay。

So what's up with the cues？And also， why is this hypothesis， too of what was equilibrium important。

 right， So to be clear， we know this is false if I drop condition2。

 right by the example we had said all the cus to be infinity M to be the empty set。Okay。

This is clearly false， So we better use hypothesis 2。 We used one here。So to see that。

 let's try to understand what this is。 So suppose sum over all the bitterder's eye。

 maybe think about the case， to see the subtlety， think about the case where there's like 10 bidders and 20 goods。

 Okay， where there's a lot more goods than bidders。So suppose I sum over the 10 bidders。Okay。

There allocated these 10 goods at most。And I look at the prices。

Of the goods that they get in this matching。How does that compare to the sum of all of the prices？

It's equal thanks to condition2。So what cues are missing here？😡，So we sum this over eye。

 the cues that are missing。Are the queuees for the goods that weren't sold？They have price zero。

 so even though there's fewer terms， when we sum this over eye， the sum's exactly the same。对。

So surplus of the matching M minus Q。And over here， we just have some cues。

 We don't really care about them。 Okay， so some over I。Q M star I。So， rearranging。Right。

 so the point is， this is。Certainly a most cute。Okay。So rearranging surplus of M is at least。

Surplus of M star。When we add capital Q to both sides， this becomes a non negative term。

 So if we drop it， it becomes only less。 so that gives us this。 what we're done。Okay。

 so M star may have been optimal， so was M。That's the first welfare theorem。So later。

 when we do asending implementations that have this discretization error。

 we're going to want an approximate first welfare E theorem saying that if you're almost an approximate almost of all is in equilibrium。

 you're almost optimal matching。 So that's one of the exercises on the exercise set。

 but the proof is exactly the same。All right。So good。 So we're starting to get some clues。

ThatMaybe there is some connections between VCG outcomes and what rise in equilibrium。So let me just。

 there's a very simple fact I'm going to need in the next theorem。

 which I call the mix and matchch lemma。The proof is not hard at all。

 so I'm going to put it on the exercise set。It's， it basically says， well， look。

 So we're all in equilibriumli our pairs。 It's a price vector， and there's a matching。

And we know that these things aren't unique， right， So in all for example， in this， this。

 we know that there can be various cues。 They can also be various matchings。Mixing Matma just says。

 give me any two ws in equilibrium， I can pair them up in the opposite directions I get wwas in equilibrium。

 so I can take any price vector contributing， participating in any water in equilibrium。

 any matching， participating in any water in equilibrium， and put them together。 I get new ones。

So mix and match Lemo。M1 Q1。呃。NM Q2 or Walgenic Libya for。Particular evaluations。So our M1 Q2。

And MQ21。See exercises。Okay， but it's not not hard just a few lines。All right。

So now I want to actually get down to business with relating V G payments and all large in equilibrium。

 Okay， let's really try to start getting at the heart of the matter。

So this theorem is going to say we're not yet going to argue that there's a。Any equations involved。

 But at the very least， we're gonna say that VCG prices are no bigger。

Than any while we're using equilibrium。They're bounded above by every what was in equilibrium。

So fixed any unit demand valuations。So at P P of G。Be the。VC G payments。By the winner。I of J。Okay。

So just to be clear， right， So while' in equilibrium， the prices are on goods。Okay。

 they're not in the bidders。If think about V C G， VC G assigns payments to the bidders。 Okay。

 but with matching， you know， you can transfer between them right So in the， in the VC G mechanism。

 you know， bitter eye pays 10 bucks。 Well， what do they pay it for， Oh， they paid it for good 17。

 Let's just call the price of good 1710 bucks。OkaySo that's all I'm saying here。

 So if we're given good J in the VCG mechanism， look at how much was paid by the winner of J in the VCG outcome。

 call that the price of good J。If good J was unsold by the VCG mechanism。

 we're going to define this to be zero。So the VCG outcome induces a price vector on the goods。ち。

So if Q is a large equilibrium price vector。Then p of G is at most Q of J。For all items， J。Okay。

That's why Im going to improve next。Well rise any equilibrium price vector is bound above。

What the VCG payments could possibly be。Okay。Now， if。I could prove also， not just this。

 but also that the VC G payments themselves， in fact。R。Overall' is an equilibrium price vector。

Then there's a sense in which that's the lowest， smallest while we're as equilibrium。And we will。

 in fact， prove that。that's where we're going。But for now， I just want to say。B C G payments。

 they're not going be bigger than always any equilibriumping。So was a clear theorem statement？Rights。

So， proof。The proof is actually going to have a similar flavor to the proof of the first welfare theorem。

Similar kind of maneuvers。start it down here。O。So。So if a good is unsold。

 So if for a good J that's unsold by the V C G outcome， there's nothing to prove。 Okay。

 we define P P of that J to be 0。 So it's clearly true。

 So we're only interested in goods J that are awardeded to somebody in the V C G outcome。

 consider such a good J。 sayy it was one by bitter I。Okay。So， now。

This is the first time in the lecture where we really need to write down the formula for the VCG payments。

 which is not surprising。 I mean， look at what we're asserting。

 we're asserting inequality with the VCG payments on the left hand side。

 so let's figure out what was this again， What was this externality thing。So recall。So P of J。

Is just the VCG payment made by Bi eye。So it's the externality of I conceptually。

So what does that really mean mathematically？Well， it means。Do the thought experiment。 Okay。

 so we already know what VC G computes to compute some matching M。

 It gives some surplus to the bidders other than I。 Now。

 suppose actually we just recomputed a matching from scratch tailored to get these n -1 bidders the biggest surplus possible。

That's could to be some bigger number。And the V C G payment is the difference。

So it's going to be the difference。Between the surplus enjoyed by the other n-1 players。

When I specially compute a matching just for them， that's M minus I。Minus。

Their share of the surplus when I computed a matching， optimizing everybody's surplus。So， where。

M is the VCG allocation， that is the one maximizing surplus for everybody。And M。Minus I。嗯。

Equals opt matching。After deleting。Bitter eye。Okay。Can everyone read this？So again。

 this is just this is all I'm doing right now is recalling the definition of the VCG payment。

 That's all I've done。Okay。So again， you say， what would surplus would they get if I optimize just for them。

 what share of the surplus do I get when I optimize for everybody？O。So again。

Now I'm going to use the same kind of maneuvers as in the first welfare theorem。So let Q。All right。

So consider a y is an equilibrium Q。And consider the sum of the prices as before。

So I want to prove these QJs are at least as big as these PJs。

So here's where I need the mix and match lemma。Right。

 so my definition of a rise equilibrium price vector is just that it participates in somewhat rising in equilibrium。

For the proof， I actually really want to pair this with the efficient matching computed by the VCG allocation M。

 Okay so by the mix and match Limma。QM is a well riseiz in equilibrium。

Meaning it satisfies these conditions one and two。So again， P is the VCG computation。

 Q is your favorite Well Y is unique equilibrium， which I want to prove is at least as big。So。

I'm going to do the same maneuver， I'm going to say as I did here。Socept they're going do it。

With respect to just the bidders， other than I。So by virtue of this being。Of laws in equilibrium。

 everybody's getting their favor good at the price Q。

So everybody's at least as happy getting their good in capital M as they would be in the good that they get an M minus I M minus I was when I optimize surplus just for these bidders other than I。

So we have v sub K。M of K minus Q。at least， so again。

 this is because MQ with the mono in equilibrium。And it's happier in this case。

Then if it got the good it got an M minus I。At the current prices。Okay。

So I did exactly the same thing as I did here。The only difference is I threw player I。

 and the other difference is instead of using the matching M star there。

 which was optimal for everybody I'm using as a competitor， the matching M minus-1 I here。

 which is optimized for bidders other than I。So， again， summing。What do I get。

So I'm going to sum this over。All bidders， the n -1 bidder is different than I。

So I haven't done anything interesting here， just copy this down。

What is this when I sum over all of the bidders， we just did this。

 What is this if I sum over all the bitters， this is。Qu。Oh yeah， good。 So， so， right。

 So if I do it over all the bidders， including I， this is capital Q。Therefore， as you say。

 if I do this instead over all bidders other than I。

 it's capital Q minus what's missing and what's missing is Q sub I。 Take the VC G payment。 Sorry。

 the， the， the。Q sub J， right， Q sub J。Okay， so so I， the bitter that's missing。

 And then the good that it's get is J。 right， So these are the prices on the items。Okay。

 so if I sum this over everybody I included， I would pick up all of the goods with nonze price。

 That's what we did over there。 So that'd be Q。 If I， if I delete I， it's deleting the good J。

 So it'sleting the price Q sub J。Okay， that's what happens when I sum that。And then。Again。

 this I'm not gonna care。 I'm gonna care that this is the most capital Q。So rearranging。And again。

 remember what it is we want， what are we trying to prove。

 We're trying to prove that the VCG payment， VCG price induced for good J， lower bounds。

 anyone has unique equilibrium price on J。So I want a lower bound on Q sub J。So I have this  Q sub J。

 This is a minus Q。 So if I add it to this side， it annihilateates this thing， which is the most K。

 Again， this is non negative。 and I can then drop it。 It becomes only more true。

And I get that the rise equilibrium price on J is bounded below。By this term。Mineus this term。

Which should look familiar？So this is the VCG price。It's also right there。Okay。

So the surplus or the other end -1 bidders get when I optimize just for them。

 minus their surplus share when I optimize for everybody。Okay。So， that's the proof。

Any questions about that？So again， we're slowly developing more and more connections between the VCG payments and these will rise in equilibrium。

 which initially seemed like pretty different objects。

So now we see that every wall is in equilibrium is at least as big。As the VCG payments。Okay。So now。

 as promised。The VCG outcome is， in fact。Our laws are equilibrium。

We know it's no bigger than anyro equilibrium， in fact， it is a wellro equilibrium。And， hence。

The smallest such。Okay。So this is the sort of climax of today's lecture。

 We have a characterization of V G payments， which just seemed complicated a difference of matchings。

 Now we understand that actually theyre merely these rise equilibriumlibria。

 which seem like plausible termination points of ascending auctions。 And moreover。

 there's non uniqueness。 You have lots of horizon equilibriumlib。

 But we know exactly which one we're shooting for。 It's the one at the bottom。 It's the smallest one。

Next week I'll show you what setting auction can indeed de compute that smallest oriz equilibrium。

Okay。So here's the keylemma。I need to prove this theorem。

And thislemma is pretty nice in its own right。 It starts showing how VCG payments are nicer than usual in matching problems。

So， at MP。Be the VCG outcome。We've been talking some about matchings when we delete a bitter I。

What I want to talk about now is I want to talk about matchings when I add an extra good。

So let M plus J。Be opt matching。With have a second copy of Good J。Added。

So as good as identical in all respects。 Okay， so for every bidder K， V， K。

 J and V K J prime are exactly the same。Okay， so everybody likes it just as much as J。 And again。

 remember， we' unit demand。 Okay， so everyone only wants one good in particular。

 they only want one copy of J。So there's more stuff for sale。 We even range the space of allocation。

 so the surplus can only go up by adding a new good J。Okay。And so the claim is， in fact。

The VCG payment made for Good J。Is exactly the extent to which the surplus would go up。

If I added a second copy of J。Okay， so is the key limo。So remember。

 M was our original computation with just one copy of each good。

 M plus J is recomputing an optimal solution with a second copy of J。 This is only bigger。

 and the claim。Is that the extent to which this is bigger is exactly the price paid for J。Okay。

So this is real this， this keylemma。 This is special for unit for unit demand valuations。

 for these matching problems。 So remember， when we define the VG mechanism。😊。

If you remember in the fall， we define it super abstractly。 We didn't even a notion of goods。

All we had were sort of abstract outcomes。Okay， so there wasn't even a way to define duplicating a good for the original VCG mechanism。

But with the special structure of a matching problem。

 we can characterize VCG payments in this very simple way。All right so questions about that？

Otherwise， I'll show how the key lemma implies the theorem。

 and then I'll sketch a proof of the keylemma。 and we'll be done。Allright， this gets pretty slick。

So why， assume we prove the klemma， why would that imply the theorem？

Why does that imply that the VCG prices， which we now know are equal to this？Are， in fact。

 a rise in equilibrium。O。Alright， so we don't have to worry about goods that go unsold by definition。

 those have price 0。 So we're not worried about the second condition of laws in equilibrium。

So remember we're trying to prove V CGs walls is in equilibrium。 This condition is immediate。

So let's think about condition one。Think about goods that are actually sold。

So consider a good that's sold and suppose some bitter eye gets it。Okay。And we want to prove that。

This is I's favorite good。With respect to the VCG prices。So consider a competitor。

 Consider some other good L。The limit is， we can understand。嗯。The VCG price of L P L。

As the extra surplus of having a second copy of L。So we have a bitter eye。In the VCG outcome N。

 it's matched to some good J。We have some good L， presumably match to somebody else。

 and we're doing a thought experiment where we have a second copy L prime。Of hell。

So what I want to do now for you is give you a lower bound。On how big this surplus gain is。

 a lower bound on piecebel。I want to show you one way that we could make use of this second copy of L to get more surplus。

So here's one， I'm not saying it's an optimal way。 I'm saying it's one way we could use L prime。

So we start from just the VC G outcome matching capital M， because there's only one copy of L。

 Now we say， oh。We're given the second copy of L prime。So let me reassign I。The El primeme。

So originally， bitter I got good J。 Now， I have this extra copy of L L prime。s say， wow。

 let's free up good J。We'll give bitter eye good L prime instead。Now。

 I'm not going to stop there because now I've freed up a copy of J。O。

 and now I'm just gonna re optimizeimize from scratch for the other n -1 bidders。 Okay。

 so bitter I definitely gets L prime。And now I optimize for everybody else。

 what goods were available to everybody else。Well， I've only committed to using L prime。

 and J is freed up。 So there's actually one copy of every single all of the M goods available。

 which I'm now going to use optimally for the n -1 bidders other than I。So， start from M。

Reassign I to L prime。Compute the optim matching。M minus I。Of other bidders。

To the original copies of all goods， which are all currently available。Okay。So remember， P of L。

 This is the surplus gain that we get by re optimizing with an extra copy of L。

 I'm giving you a feasible allocation。 So that's a lower bound on the surplus gain you can get。

 How much more surplus do we get from this reassignment。Well， we gain。Okay。

 so we gain the contribution， we gain whatever values i is for L， L prime L being the same thing。

We took J away。From we took J away from I。So we have to account for that。

 So this is the surplus gain just from this step。And then。We get the surplus gain。

 which is the extent to which re optimizing from scratch from bidders other than I is higher。

Then their surplus share in the original outcome M。Also known as the VC G payment by bitter eye。

 by definition。Which using the klemma a second time。Is exactly P of J。So let's write this as。

Gain by reoptimizing。Forbiders other than I。Okay， this is just by definition。

 This is just what we did。This equals VCG payment。Of I。By the original definition of the VCG payment。

Which in turn equals。Pr J。By the keylemma。Okay。So the VC G payment by a bitter eye right。

 is the same as。The price of the corresponding go that it gets J by the klemma is exactly， well。

 it is what it is。 Okay， It's P of J。So rearranging， what do we get？We get that。V I of J minus。Sorry。

 P of J。Is at least V of L minus P of L。W which verifies the walla equilibrium equilibrium condition one for the allocation and the prices induced by the VCG outcome。

Okay。So that's again， assuming that we can prove this cool characterization of EC G prices。

 that they're exactly the surplus increase of an extra copy of the good， assuming that that's true。

Then we can conclude that the VCG outcome is a quasi equilibrium， therefore the lowest such。

Any questions about that？Alright。So final piece of the puzzle then。Is this key lemma。Okay， so。Again。

Suppose I gets good J。And VCG outcome。MP。Okay。Now we're doing the whole point of this klema is to do a thought experiment where we duplicate this good J。

So I mean， I guess to put it better， consider any good J。

Consider the winner of it in the VCG outcome I。Now imagine we duplicate good J， we get a J prime。

Well's a claim？So suppose when you have only one copy of J。And you run the V G outcome， you do this。

 you know， allocation procedure。 Supp bitter I winds up getting the good of J。 Nobody else gets it。

 Biter I is the lucky winner of Good J。Now I suppose I introduce a second copy of GoodJ J Prime。

 there's two copies available。And again， I re optimize。

The claim is that bitter I is still going to be one of the most two bidders that gets a copy of Good J。

WhenWhen Sply was scarce， when there was only one copy， it was the one that got one。Now。

 there's two copies。 Everyone valuess in the same。 I definitely to get one of those copies。

That's the question。So I think that's pretty intuitive。RightSo if I gets a copy when it's scarce。

 it should still get a copy when it's less scarce。 It's a little tricky to proof。

Okay so I'm not going to do it now。I put this on the exercise set with ample hints。So， claim。

After adding the duplicate J prime。There is an optimal matching。M plus J。Such that I is still。

Mached to J or J prime It doesn't matter。 One of the two copies of J。Okay。

So I'm going to assume this claim and finish the proof of the klima。So。Assume this is true。Then。

Consider this matching that has available these two copies of good J and consider deleting bitter I。

 So that takes away one of the two copies of J。To the other n -1 bidders， they form a matching。

And they don't use both copies of J。 They use it most one copy of each of the available goods。 Okay。

 so the matching induced by the other n -1 bidders。

 we can think of as a matching with respect to the original good set。

So call that induced matching M minus I。With each good used at most once。Okay。Now。

 what I hope is clear is by virtue of this matching M plus J being optimal max surplus。

Then certainly， M minus I should be the max surplus matching of these other n-1 bidders that uses every good at most once。

 If there was some matching better than M minus I with that same property， well。

 I would just couple that with matching I to the copy of J。

 And I would get a better matching than M plus J。 Okay so the most trivial cut and paste start。😊。

Okay。So M minus I must be。The optimal such matching。Okay。

Me a matching of the players other than I to using goods at most once。

So what does that mean so that means？If we think about the difference in surplus So if we think about this quantity。

 the difference in surplus between having an extra copy of J and not。So remember。

 this is what we want to prove is exactly the VCG payment of J。 We want to prove this is exactly POJ。

All right， well， an M plus J using the claim。I is matched to one of the two copies of J。

So this is VIJ。Plus， the rest of the stuff。And over here。This is also equal to VIJ。Because again。

 an M I matched to J。 So that's the whole point。 As I gets a copy of the good J in both of these two matchings。

 Okay， so that part just cancels out。So plus the rest。So the VIJ cancels out the difference。

 So what are we left with。Well， so this matching is nothing more than I matched to a copy of J plus the other bidders in this optimal matching M minus I for them。

So this is just equal to K， not equal to I。V sub k of M minus I。What do we have here。

 this is just right， we've deleted bitter I from this sum。 That's the part that's canceled out。

 So we're just left with a surplus share of bidders of than I for the VCG outcome M。K。And this。

 of course， is just the definition of the VCG payment paid by bitter I， and therefore。

 the induced payment for good J。So that concludes the proof of the keylema modular the claim that basically by duplicating goods。

 it's only other people that get the new copies。 don't actually kick people out。

 So modular the claim， we have this really nice characterization of the VCG payments is' just surplus increase by duplicating goods。

 There's this really slick argument showing that that's enough to conclude that VCG outcomes areiz in equilibrium。

 that simple first welfare theorem like argument showed that all otheriz equilibrium are at least as big。

 So VCG is the smallest。 So that's now the line in the sand that we're going to shoot for at the beginning of next lecture。

 ascending options that terminate guaranteed at the minimum wiz and equilibrium。 See you then。

