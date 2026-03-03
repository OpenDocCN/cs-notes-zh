# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p08 -08-(Lecture 8_ MIR and MIDR Mechanisms).zh_en -BV1fNVNzhEBg_p8-

So we concluded last lecture with a piece of good news so we had this we've moved on to this mod evaluation case。

 welfare maxizations n be hard， but we can get decent approximation algorithms and polynomial time。

 if we ignore incentives completely So now of course what we want to do is want to say okay well we want just as good an incentive we want just to get a performance guarantee and computational tractability guarantee。

 but now we want strong incentive guarantees also ideally decent。

So how to extend the two approximation。For scenario。Number six。To a D mechanism。

So this is this turns out to be a lot harder than it might first appear， actually。

 And I'm not going to give you any positive results for for sort of this question today。 Well return。

 We'll circle back to it next week after we've expanded our toolbox。

 Okay So what I want to do next is I want to look at a couple of the scenarios。

 which where it's sort of a bit easier to get positive results。

 And those other scenarios will also motivate new tools for designing mechanisms that have good approximation guarantees。

 And finally， we'll go back to at least a subcase of the so modular case and apply those tools to get some positive results there。

😊，So first， let me just make sort of some high level comments。

Just about kind of the nature of the challenges in doing this question。 So first， let's just say。

 you know， for those of you who took 3，64 A last quarter， you know， we've been here before actually。

 and it seemed fine at the time。 So the case study that I used in 364 a was Napsackack。

And we had this notion， we had Myerson'slemma， and Myerson'slemma。

 what it did is it told us exactly which allocation rules could be used in D mechanisms。

 and it was very nice。 it was exactly the monotone allocation rules。And so， we had Napsack。

 MP hard problem。You can get a one minus epsilon approximation in polynomial time。 So that was good。

 But then when we inspected the corresponding allocation rule， we observed it wasn't monotone。

 So it wasn't suitable for a de mechanism。 But you know well。

 you tweaked it a little bit because it was a homework problem and showed that it could be you know redesigned to be monotone and still be a one minus epsilon approximation and then we got a decent mechanism。

 so it sort of a total happy ending So we required a little bit of algorithmic work。

 but we got exactly the conclusion that we wanted。😊，So the first thing you might think about is like。

 why don't we just go through exactly that same exercise here， We design the approximation algorithm。

 check if it's monotone， if it's non monotone， we sort of tweak it to it's monotone。

 and we're off to the races。So idea number one。So first of all。

 let me emphasize that Myerson's Lema stated last quarter was only for single parameter problems。

Actually， if you think about it， the statement only makes sense for single parameter problems。

 what did it say， what does it mean from allocation will it be monotone， it says the more you bid。

 the higher you bid， the more stuff you get。Okay。And if you' if it's multiparameter。

 if there's all these different bundles， you're bidding on simultaneously。

 it's not even clear what to say， the more you bid。

 what if you raise a bid on one bundle and decrease it on another one。What do you call that？So。

But we could hope to have an analog of Myerson's limo。That works。So idea number one。

 identify a monoity condition。The characterizes implementability。Characterizes。D6。Implementability。

So just to remind you， what does it mean to be implementable。

 that means I hand you an allocation rule， And the question is。

 is there or is there not a payment rule when coupled with this allocation rule gives you a decent mechanism。

 If there is， it's implementable， if there's no such payment rule， it's not implementable。

 And what we proved last quarter is that monoicity is exactly the same thing as implementable。

So maybe there's an analog here。So actually， there is。Yeah。

There's something called cyclic monotonicity。And so while there is a characterization of implementable allocation rules。

 it's just， you got to take this on faith for now， it's just not that useful。So what do I mean。

 It's not that So that said， we will actually use it once in this class。

 I'm pretty sure in a couple of weeks。 so what do I mean by not useful， First of。

 it's just hard to check， given an allocation rules。

 it's just hard to figure out whether or not it satisfies this property。

Whereas monoonicicity often is not very hard to figure out whether or not it's satisfied or not。

 But two， it almost never holds。 And we'll see more evidence of this as we go through the lecture today。

 Okay， so just rarely if you come up with something and you check this condition。

 it's just almost always false。Is it a sufficient It's necessary and sufficient， actually。

hard to check you mean testing wise So I just mean to like say take your favorite approximation algorithm and just ask the question。

 does it satisfy this condition or not？That's as a math problem， it's annoyingly time consuming。

 usually more so than in the single parameter case。 Plus。

 the other point is there tends to be just no payoff at the end。 Usually the answer is no。

 So usually you work hard to prove that actually， your algorithm is not suitable。

So I don't really advocate going this direction is what I'm trying to say。

 right so this kind of way of thinking about approximate mechanism design that was fruitful in the single parameterer world。

By and large， has not been fruitful for researchers in the multiparameter world。Okay。

So we're going to think about it a little bit differently。Okay， so idea number two。Okay。So more。

 the way we're going think about it is we're going to just start from what we already know works。

Right，And then just try to make it slightly more powerful one step at a time。 Add bells and whistles。

 Okay， so kind of start bottom up。 Okay， and so for example， the VC G mechanism we know is。

 we know works。 is de。 It may not be polynomial time。 In the cases we're now looking at。

 but at least it gets the incentives right。So idea number two would be， okay， well。

 we've got the V C G mechanism。 If it's NP P hard， we can't in polynomial time。

 But if we have an approximation algorithm that does run in polynomial time。

 let's just stick that in instead。So if you think about it， the VCG mechanism。

 you can define an analog with respect to any allocation rule。

 like our two approximation for welfare maximization。You get valuations from people。

 You invoke your approximation algorithm to compute an approximately optimal allocation。

 and then to compute the payments， you just invoke it n more times。 Okay， you delete a bidder。

 you use your approximation algorithm again。 And then that defines the payments。

Does that necessarily give you non negative payments？So no， it does not， among other problems。

Right so。That's going to be sort of the least of our problems at the moment。 Well， I mean， actually。

 frankly， in some applications， it's the most of your problems， but。Let me just say the following。

 so plug approximation algorithm。Into VCG。And let me just say the problem here。 And again。

 this So this is an attempt。 So just as far as like how we're approaching the problem。

 this is a different angle。 right， So rather than kind of you know。

 have a necessary and sufficient condition， which tells us what the whole design space looks like。

 We're just starting from something we know works and trying to extend it。

 The problem is this way of extending what we know works almost never succeeds。Okay。Yeah。And for now。

 the main thing I just want to say I never works is you will get a mechanism in general。

 which is not decent。Okay。And this I can sort of tell you morally why this shouldn't work。

 what the problem is。 Actually， there's some good intuition for why this is going to fail。

So let's remember what the point of the VCG payments were okay so you charged your externality。

 so basically the surplus loss that others incur because of your presence and the reason we're charging externalities is because if you then look at the utility of a bidder。

 its value minus its payment， its payment is then up to a constant。

 the negative of other people's welfare in the outcome so in other words。

 the payments are defined so that it aligns your own utility with the social welfare of everybody that's why the VCG mechanism works morally。

So intuition。By design， VC G。Alligns。The utility of a bidder。With social welfare。

Up to some constant term， which the bidder can't influence。 So for incentives， it's irrelevant， okay。

So this is just how mean， the VCG payments are defined so that this is true。

So in the happy case where you're maximizing welfare exactly。

 well the bidder wants to make its utility as high as possible。

 and so that means it just wants the social welfare to be as high as possible。

 so if the mechanism does this， then the bidder is going to be happy。Now。

 the mechanism fails to maximize the social welfare。 if it does something suboptimal。

That corresponds to an opportunity， potentially of a bidder to mistreport in a way that coaxes the approximation algorithm that actually spit out a strictly better solution。

 resulting in a strictly bigger utility for that bidder。Okay。

 so subopity in the allocation will kind of directly represent opportunities to missed reports to have higher welfare allocations therefore higher better utilities。

So that's why fundamentally， approximation algorithms just almost never work。

 if you just plug them into the VCG mechanism or the VCG payments。So again。

 if right hand side suboptimal。There exists opportunity。For some bitter。To increase utility。Now。

 you know this is sort of morally true， technically， the reason this is。You know， a little。

 not really the complete story is because。It's not clear that a bidder has a unilateral way of coaxing the allocation rule into a better allocation。

 Okay， but actually， this can be dealt with。 So there's a paper of Nissan and Ronan。

 And I'll put the citation in the notes who prove that this really is true。 I mean， really。

 basically， if you're doing something suboptimal V G payments just basically never work。 Okay。

 there is a theorem that says exactly that。Okay， and so the an important thing I want you to take away from this discussion。

And this will become clear throughout the rest of today and next week is that for multi parameter problems。

So there's a big difference between single parameter me design problems and multi parameterameter design problems。

 really very big as far as both how we understand it。

 but seemingly what is even possible versus impossible。So with the single parameter case being much。

 much easier， it seems。So for multi parametera problems。

Like the commator actionsuctions we've been talking about。

The bottom line is if you insist on dominant strategy and se compatibility。

 it just seems there is very little you can do， okay， the design space is just very meager。That said。

 we'll work hard today and next week to do the best we can in this very limited design space。

 but seems very limited indeed。And then in the entire second half of the class。

 motivated by this sort of moral， we're going to relax the DI requirements so that we can actually get a bigger design space and more positive results。

Good， I should say。So this as a mathematical statement。

 this is more conjecture than proof at this point。 there are theorems around this。

 So you can actually， you can imagine a theorem that actually said the spa， know。

 the only multi parameter de mechanisms are X where x is some small set。

And there is something called Robert's theorem， which basically says if you have a totally abstract problem。

 Okay so literally just some abstract outcome space， you don't have a notion of goods。

 nothing like that。 then in fact， you can actually prove that the only deterministic de mechanisms are minor variance on the VCG mechanism。

 that's known as Robert's theorem。 So basically an open question is does Robert's theorem hold for commtal auctions。

 Com auctions have some extra structure。 you have these goods。

 And I only care about what items I get， I don't care about what items you get。

 So this no externalities between bidders in that sense。 So that's extra structure in comm auctions。

 which seems to， on the one hand， make it really difficult to prove theorems like Robert's theorem。

 but on the other hand， doesn't seem to be enough structure to enable nontrivial de mechanisms So that's kind of the state of the art at the moment。

 It's kind of hard to prove positive or negative results for commtl auctions。

So I'm going to tell you in these couple of weeks what we have been able to prove。Okay right。

 so any questions？Alright， so here's the plan。 So again。

 the plan is to just start from what we know works。

 which at the moment is pretty much just the V C G mechanism and look at bells and whistles of it。

 look at variations and look at some problems where thatll give us nontrivial results， okay。

And so today I want to introduce a couple more scenarios。 One will be simple and solve completely。

 One is more complicated and will'll spill over into next week。

 and the tools we develop willll put to use from the submodular case next week。So beyond VCG。

 what else could you do？So here' is idea number one， it's a very kind of minor idea。

 but it's useful in some cases。So let me tell you about maximal and range mechanisms。

So maximum range MIR， this is a property of an allocation rule。

So MI IR allocation rule has the following structure。So what you do， okay。

 so say there's an outcome space， I'm going to describe this abstractly。

 but you can go ahead and think about comm options。So there's an outcome space omega。

 So this would be like all allocations in the problem we've been discussing。And。

This rule then precommits。Before it ever sees valuations， before it ever sees bids by the players。

 it says up front look。I'm only ever going to output an outcome in a subset omega prime。Allright。

 now， why would you ever do this。 So heres， here's what you want to have in mind。

 You want to think about omega as being either too big or too unstructured to optimize over efficiently。

 Okay， so searching over omega is a hard problem。Omega prime is going to be chosen to be either small or structured enough so that searching over is an easy problem。

Okay， so think of omega prime as a subset which is tractable。So you're losing information。

 but hopefully gaining tractability and passing to omega prime。

And then once the bids or evaluations come in。X just runs VCG on omega prime。Okay。

So it's a very minor extension of VG。 Okay， up front， I throw out some outcomes。

 and I run V C G on what's left。And the hope is that you can find a sweet spot。

 an omega prime that's rich enough。That you haven't， you can still get a good approximation。

 right You've thrown out some stuff。 But the hope is you still have kind of something near optimal for any evaluations。

 but it's also small or structured enough that you can optimize efficiently。Okay。

And this is clearly decent。Just because VC G is D6。

 Omega prime could well have been the original outcome space for all anybody cared。 All anybody knew。

Okay。So， that's an MIR。Mechanism are allocational。So as far as what else could you do other than the VCG well。

 know， this is something you could do。All right， so could it ever be useful for anything， Okay， well。

 it's not useful that often， but once in a while。 So let me show you an example。How you might。

 how youd actually do this to get a。Somewhat interesting result。So let me give you a generalization。

 So we're going to go back to the world of identical items。

So identical items is before we were talking about downward sloping valuations。

 We had Oszebel's clinching auction， blah， blah， blah， blah。

 So we're going to look at a harder version of that where we drop the downward sloping assumption。

Just remember， this is where all the items are the same。 And as a bidder。

 you might want more than one。 You're not unit demand。

Downward sloping said each additional unit gave you only less marginal value。

 Now we're going to drop that assumption。So extra units may give you more or less marginal value than the previous one。

Non negative marginal value， you have free disposal as usual， but that's the only assumption。

All right。And identical items。I has marginal values。Mu Ij， non negative。For all J， and again。

 the key point here is。Need not。The downward slogan。Downward sloping。

 you'll recall we had a nice ascending auction， and we basically got everything we wanted。嗯。

All right。So let me tell you what we can do just with a regular ECG mechanism。

 and then I'll explain how we can get sort of an incomparable result using an MIR mechanism。

 incomparable meaning it'll be faster， but it will be approximate instead of exact。

So I'll leave it as an exercise to convince yourself。

That you can solve this exactly using dynamic programming。

It's not that different than say Napssack or something like that。 In fact， if you think about it。

 Napssack is going to be a special case of this problem。 Okay so basically。

 if your marginal values are just 0，0，0，0，0，0。 And then at some some point。

 it kicks up to some number， you know，10。 And then the marginal values after that like 0，0，0，0。

 That's like， you know， if say it was the 12 good that gave you this margin of value of 10。

 that's like anapssack item with size 12 and value 10， right， you give a 12 items， you get value 10。

 your Napssack capacity is like M。So it's a little bit more general than Napsack。

 but the dynamic name programming again works fine。So exercise。

Can maximize welfare in time polynomial in N and M。Bydynamic programming。And of course。

 if the valuations are represented explicitly。If you' just given a list of these mu IJs。Then。

 you know， you'd be happy with this。On the other hand， you know。

 dynamic programming for the NApsack problem， we usually think of that as pseudopolynomial。Right。

 usually。Running time linear in the NA， so M here corresponds to the Napsack capacity and a Napsack problem。

 and if you're running time linear in the Napsack capacity。

 we usually think of that as only pseudopolynomial and not truly polynomial。

And so you might want to think here。 You might want to look for algorithms that actually are polynomial in N and log M。

The number of bits needed to explain what the supply is。Now， you have these marginal values， right。

 So again， you need some model for that。 but we've already talked about that。

 So let's think actually about a black box model for valuations that supports value queries。 Okay。

 so for a bitter eye， I'm just going to say， look， what if I gave you 17 items。

What would you pay for it？And they'll answer us。 And other than that。

 we're not going to treat them as part of the input。 Okay， they just answer value queries。

 Dan it's conceivable。 We could get a running time that had subline dependence on it。Okay。So。

 and we can， that's what I'm going to show you next。So this is by Dzinsky and Nissan。

So there exists a maximal in range algorithm or mechanism。With two properties。 So first of all。

 it's not going to be exact。But we'll get at least 50% of the opt welfare。And two。

The time plus the number of value queries。Is polynomial。And and。And logm。

And I guess I should also write。um。Log of the biggest。Number， probably。Okay， so again。

 the point here。So this is worse。 It's only approximation。 This is better。 Okay。

 the running time allow accounting value queries is constant time is poly them in the log of M。

 not an M。 So if M is huge。 this is a big win， actually。Allright， but again。

 the main reason I'm showing you this is just to convince you that， you know。

 M IR as modest and advanced as it sounds and is， you know， can be useful in some context。 Okay。

 that's the point of this example。All right， so any questions before the proof is not。

 but we all do the proof pretty quick。 It's not hard。 Any questions before that。All right， so。

So if it's MIR， I can tell you what is this outcome space So an allocation space， basically。

And M algorithmgon is going to say， look， I will only ever output allocations with certain special properties。

 So I need to tell you what the special properties are。 So here's what it is。

So what I'm going to do is just up front， I'm going to take these M items conceptually， at least。

And you're going to split them into blocks， chunks，So I started with M items。

 I only want there to be kind of n squared。Meta items， I'm okay being polynomial on N。

 I don't want to be polynomial on N。 I want to be sub。 I want to be logar in the M。So I start with M。

 I want to squeeze it down at just n squared， which means each block has M over n squared items in it。

And I'm only going to optimize over allocations where I do out items in these blocks of M over n squared at a time。

So your allocation will be some integer multiple of m over n squared， that's omega prime。O。

So this is now just a multi unit option in effect with n squared items。

 which of these n squared items represents M over n squared in the original one，So， you know。

 now that there's so few items， right， So now that the number items is just n squared。

 I can run the dynamic programming algorithm on these metaite and maximize welfare over all this entire restricted allocation space。

 omega prime。The only reason I have dependence on M at all is because I need to actually write down the quantity when I query a when I do a value query in one of these black box valuations。

 so I might have to ask it about a number as large as M， so I need log M time to do that。Right。So。ちち？

So it can be done。By D P。In Poly and。Wm。Time plus value queries。Okay。So， you know。

 I did choose Oomega prime small enough that it enabled fast search。Okay， that's good。

 But now the question is， did I throw out the baby with the bathwater。

 Are there still enough allocations in there so I can always get a good approximation。

 because that's what I have to。Right。So。Let me show that to you。So suppose the optimal allocation。

Is S1 star up to SN star。Now， all the goods are identical， So I mean。

 really of these are just non negative integers that sum to M， okay。

Soupp that's the optimal allocation。What I need to show。

Is that there exists an allocation in omega prime that is an allocation that only uses these blocks of M over n squared size that is almost as good as this one。

Why is that enough， Well， Because amongst all of those allocations， we're going to pick the best one。

 Okay so if I show you one good one， we're done。So I need to show there exists some allocation S1 up to SN。

Of blocks so that the welfare that you get from it。Is at least one half of the optimalim welfare。

Agreed。Okay。So if it is easy enough， two cases。So first。

 if there you know if in this optimal allocation， it turns out almost all of the welfare。

 say at least half the welfare in here。Comes from a single bidder。No problem。

Because one of our feasible allocations is just to give everything to one bidder。Okay。

So that's one of the things we optimized over。 So if there's one bidder in here which contributes half of the welfare。

 no problem。So then we just set S I equals to be all M。Nobody else gets anything。And then done。

Okay so I'm using monotononicicity here， I'm using that the muse are non negative。

So in this allocation， the key bitter eye is as happy as before， we lose everybody else。Sorry。😔。

One half there。 We lose perhaps everybody else， but they were only contributing almost half the welfare。

 So no big deal。 We're a factor to approximation。So。What if that's not the case。

 This is slightly more interesting。So suppose no bitter。

Contributes half of the welfare more in the optimal allocation。 Basically。

 what I'm going to do is I'm just going to sort of start from the optimal allocation。 All right。

 So what's the issue， right。So the issue is in the optimal allocation， right。

 So say M over n squared is like 100。Okay， so I'm only allocating in multiples of 100。

 The issue is that， you know， in this optimal allocation， right， this guy might have like 101 items。

 Okay， and more， maybe his marginal value was like 0 for the first00。

 And it was that magic 101 item that gave him all of its value。😊，Right。

So that means if I want to allocate it anything， if I want to get any value from that guy have to round up to the nearest multiple。

 Okay， I can't give it 1001 goods。 I have to give it 200 because those are the multiples that I'm allocating in。

So what I'm going to do， well just so I basically want to top people off。Okay。

 because then I'll get their value。But obviously， I can't， you know。

 round everybody up because I only have these M goods to work with。

 So there'll just be some sacrificial lamb， some bitter。I'll take all its items away from them。

 and I'll use that to round everybody else up。Okay。And O。

 so why is there somebody that has so many items that I can actually round up everybody else？ Well。

 this is the magic n squared number， right， So there's n squared blocks floating around。

 There's n bidders。😊，So somebody's got any of them。

Okay so that's my sacrificial lamb right I take his end blocks。 I basically that's enough。

 that's a proof of concept that can round everybody else up and just round this one guy down。

 Why don't I lose all of the welfare by rounding this one guy down Well in case too nobody has that much of the welfare。

 no single bidder contributes half the welfare or more。All right。

 so I feel like I should write something。So case2， otherwise， there exists I。With at least in blocks。

And so then how do I set my new allocation？So for k not equal to I， so S equals S star I rounded up。

So multiple m over n squared。So that is， I give this guy the fewest number of blocks so that it gets at least as much as it gets in the optimal allocation。

And then， I gets the rest。Or nothing， it doesn't really matter。And then what we have。

 we have some over。The welfare and our allocation。 Well， I， I was our sacrificial lamb。

 So we'll just lower bound that person by 0。 But for everybody else， they get at least as many。

 at least as much quantity in our allocation than the optimal one。So by monoonicity。

 we pick up all of their values by the assumption of case2。This is at least half of the full welfare。

And the optimal solution。说到出来。So that's an example use。Of a maximumimal range。Mechanism。

Any questions about that？Do one half。 Good question。 Good question。 So for this mechanism， certainly。

 that's not hard to show just with two people， just with two bidders。 So here's what's cool。

 there's actually a cool story about multi unit auctions。

 which is one of the reasons why about to dispens some time on it。😊，So for deterministic mechanisms。

It is unknown whether you can beat two with DIick or not。 This is quite nice open question。

What is known is that if you restrict attention to D mechanisms that always allocate all M items。

 then you cannot beat to factor2。What is unknown is whether there's a mechanism。

 deterministic de mechanism that may or may not allocate everything and always beats to open good open question。

 interesting。 So like definitely， you know， if you want to spend a lot your project time thinking about an open question。

 that would be a good one to do。 Very appropriate。Randomized。

 and this is a project topic looking about these papers， with randomized。

 you actually can get one minus epsilon。And it's going to be the same。

 so I'm about to pass to sort of a randomized generalization of maximum range。

 and I won't actually show you this proof， although it is a project。

 one of these randomized versions of maximumim range very cleverly designed by a PhD student of mine here a few years ago and one co-author shows you can get one minus epsilon。

that's very cool， and again， though in the same kind of polyen in and log n with value queries。

So there the statement is， you're still， you're randomizing so。

 but it's still it's d assuming risk neutral bitterders assuming risk and neutrality。

 and then you get an expected one minus epsilon fraction。U。That's a good question。Yeah， yeah。

 you get expected your expected welfare is 1 minus epsilon。

 There are some mechanisms out there with the approximations with probability one。

 And the expectation is only over the incentives， but this is not one of them。呃。Yeah。Yeah。Yeah。

 so this is this is scenario 7 is actually a nice challenge problem。So。

I mean the downward sloan case is already very interesting in the tractable side。

 And this general case is a quite interesting example on the intractable side。Okay， good。

 any other questions？All right。Then， as promised， you know， so again。

 we're trying to rack our brains and thinking about what could possibly what could these mechanisms look like for multiparameter problems。

 And we're just starting from what we know and taking baby steps。

And so let me show you one of the baby step。 And actually。

 this little baby step will get us basically to the state of the art。

 I'm sort of embarrassed to tell you， okay。And so this is nothing more than a randomized variation。

Of maximumimal and range。Okay。So， maximal in。Distributional。kindd of a painful name。Range。

So MIDR is now what we have。Okay。And I need to warn you。 So， first of all。

 this is gonna be kind of abstract。 And second of all。

 I won't have time today to give you an actual example of one of these mechanisms。

 So I'm going do the definition now。 anyways， I'll introduce you to the problem that we're going to solve using these mechanisms。

 but I won't have time today to give you that mechanism for that problem。 Okay， so just。

Forward pointer to what's going to be next week。 Where we we're going to pick back up next week。

Alright， but the idea is simple enough。 It just says， okay。

 instead of pre commitmiing to a subset of outcomes， we're going to allow lotteries over outcomes。

 randomizations over outcomes。 distribution。So again， before you ever see any valuations。

 what the allocation rule or the mechanism has to do。Is pre commitmit to a set。D。

It doesn't have to be countable， but I'll write this anyways， of distributions。Over omega。 So。

 you know， one of these distributions might be as simple as， you know， with 50% probability。

 I do this first allocation， with 50% probability。 I do this other allocation， or even just like。

 you know， with 1% probability， I， you know， cancel the allocation completely。

 Those would be examples of distributions over outcomes。Okay。Okay， so。And again。

 so maximum range would just correspond to the case where each of these was a point mass on a single outcome。

 That would be that special case。Over omega， good。And again。

 so let me to remind you so why do this Okay， So over here。

 hopefully it was sort of clear the role of MIR over here。

 which is the search space for the original problem was big and we just compressed it so that it was small so we could basically kind of search it more or less exhaustively。

Now， here in general， the set of distributions need not be small relative to mega。

 it might be infinite。But， you know， we know， lots of examples where sort of enlarging the search base also makes stuff more tractable。

 right Just think of integer and linear programs， right integer programs can be hard。

 You go to linear programs。 It's not that there's fewer solutions。

 but it's somehow very nicely structured and enables efficient optimization。 So something similar。

 that's a similar reason why distributions can sort of add tractability relative to the omega that you started with okay。

Okay， anyways。So those are some things you might want to think about。Now。

 what is what does the allocation will have to do， Well in the same way that amongst all of the omega primes。

 the allocation will has to pick the best one。 Remember， that's what V C G does。

 You tell it what it wants and it picks the best option Here。

 it just set up front omega prim set of all the options。 And again。

 best option means welfare maximizing。 with respect to the reported valuations。

 Same thing has to be true here。 amongst all the distributions。

Once you know what people actually want， once you know the alleged valuations。

 you have to pick the best， okay not outcome distribution。So now the question is， okay。

 so how do you measure the quality of a distribution， Well， just buy its expected welfare， Okay。

 so it's 50，50 over these two allocations， and you get these valuations and the welfare would be 10 in this case and 20 in this other case。

 So you say， okay， well， we'll treat it as 15。And if there's this other distribution of our outcomes that randomizes between 10。

 20 and 30 for expected welfare 20， we treat that as better。Okay， so when we compare distributions。

 we do it before we sample from them。 Okay， we just think， okay， just look at the expected welfare。

Under this distribution， given the alleged valuations and pick the one that's the highest。

So that's by definition， what the MIDR rule has to do。Okay， so in other words。

 once you tell me the distributions， the rest of the rule is completely uniquely defined。So， given。

So it is at the end of the day， going to be a randomized。Allocation rule。And so what does it do？

So it chooses。The star。To maximize。The expected welfare。

So let me just write this sort of totally abstractly。

 So here you should think of omega as just being like an allocation。 Okay。

 so there's just some outcome space。 little omega is some outcome， like an allocation。

 And this is just the expected welfare for the outcome omega and capital D is just some distribution over outcomes。

 So here。Omega is sampled from D。Khen。So you have no choice。 M I D R rule。 You have to pick the。

Distribution that gives you the maximum expected welfare。 These， of course。

 are the reported valuations。And then， of course， at the end of the day， it's a mechanism。

 you have to do something。So you sample from the distribution that you picked。Okay。Yeah。

So you output omega prime。Sampled from。EThe best distribution， D star。Okay。So that， by definition。

 is a MI IDR allocation rule。 Okay， And so again， given the choice of the distributions。

 everything else is uniquely defined。 so the only free parameter here， is the only design parameter。

 what are these distributions。 And again， I apologize， I won't give you an example today。

 I will next week。Okay， and so now， this is one of the very few nonop exercises。

Just because I think it's something that would be just。

 it just makes so much more sense for kind of you to do the quick computation than the me to do it in lecture。

 which is that， you know， this still works for D mechanisms。 Okay， there's an analog of V G payments。

Where again you sort of say， okay， we know what the expected welfare is if bitter eye is in the system and we know the expected welfare of the other bidders in that case。

 if we deleted bitter eye， we could recompute， we could rechoose the best distribution just for the other people。

 look at their expected welfare， we look at that difference。

 we can charge that as a payments and the claim is that payment rule coupled with this randomized allocation rule gives you the do strategy and compatibility。

Okay， so then you I'm paying based on these expected quantities。

 But what I actually get is randomized。 You can do it either way。 Actually， it's a good question。

 So the the simplest the first way to think about it is exactly what you're thinking about it。

 So the question is basically， is the payment rule randomized or not。

 That's kind of roughly what the question is So the allocation will certainly randomized。

 So sometimes I'll get nothing， Sometimes I'll get like this really juicy bundle of goods。

 And then but I'm only thinking about my expected welfare。 And you can implement it either way。

 Either I could just pay some fixed number， So like I tell you my valuation。 I always pay 100。

 Sometimes I $10 for nothing。 sometimes I pay 100 for a ton of stuff。

So that would violate what's called exos individual rationality。

 sometimes I'll pay 100 hours and get zero。 So I actually have negative utility in some cases。

 sort of the simplest implementation the mechanism has that property。 There's an extra trick。

 maybe I'll talk about it next week。 I'll see if it fits。

 There's an extra trick where you can actually compute the payments in a way that you have exp post individual rationality So you can couple the randomness in the allocation and the payment ruless if you want。

 so that you have that。 And then， of course， for the decent condition。

 we're just thinking about players as optimizing over expectations。

 So if you don't change the expectations， it doesn't matter for the incentive adapt。So。

I wasn't planning on talking about that today， but you cant get the exposed individual rationale if you want。

So exercise。So if Fx is MIDR。And P equals， let me just write the analog。

 CB the exercises for the formal statement， P equals analog of VCG payments。Okay。

Then X P is a dominant strategy and a compatible mechanism。Again。

 so we have not actually talked about randomized mechanisms at any previous point in this class or last quarter。

 I don't think。So what do I mean by this， I just mean that。You know， for all I， for all V minus I。

For all VI and for all mis reportss。Let me just say they' write it this way， expected utility of I。

Where the expectation is over the random coin flips of the mechanism， always。Maximized。

By truthful reporting。No matter what v minus I is。Okay。So if we extend bidder's utility functions。

Over distributions by linearity， assuming the is neutral。

Then we're just saying that for those extended utility functions。

 truth reporting should be a dominant strategy。 This is tantamount to assuming that bidders are risk neutral。

And that's what we're going to assume for randomized mechanisms whenever we talk about them in this class。

Isn't that trivial when we're measuring things here anyway？You know， it kind of depends on。You know。

 like， so when you talk about utility functions， I mean， there I mean， there's layers of assumptions。

 right？ I mean， so you know， it's one thing to assume some kind of consistency of coherency about how people compare deterministic outcomes。

 And then its sort of a strictly stronger assumption about how that extends to their comparisons over lotteries。

Right， so like， I mean， just think about money itself， right。

 So like we're assuming that you like 100 bucks more than0 bucks right what are， you know。

 and that that know that alone doesn't imply anything logically about， you know。

 how you feel about 50 bucks with certainty versus how you feel about 0，1，50，50。Right， I mean。

 that code talking about my value， my valuation。I mean， that assumes like you're risk control， right？

I mean， if we because the E should be measured on the utility scale or not on。Now。

 the quasiline assumption is sort of saying the vs are on a dollar scale。

That's kind of that's more of the implicit assumption that we've been talking about。

Because I'm doing things like adding up the values for different players and saying maximizing this has some meaning。

 So where， I mean， so you know， there's different interpretations。

 but certainly like the most straightforward interpretation of all of this welfare maximization problem is just cardinal utilities。

 So that there is some， There is some comparison between the two。Yeah。Anyway， so， I mean。

 this is an interesting topic。 This idea of risk neutral and what else could you do And， you know。

 how does it change mechanism design to vary that assumption， All that's interesting。

 It would have a good place in a class called Froniers of mechanism design。 that said。

 we're not going to do it。 Okay， so we're gonna have enough。😊。

Our job will be hard enough even though there risk neutral assumption。But but good comments。

 good comments。Okay。So pretty much all multiparameter， there's some minor exceptions。

 but to first order all positive approximation mechanisms that are DCI are MIDR mechanisms。

 that's the state of the art。Okay， so really， we kind of don't know how to design these s multiparameter mechanisms except via this regime。

 Okay and nice open， it would be great to see some progress that either adds some， you know。

 fundamentally， you know， you know， different tools to the mechanism design toolbox or failing that proves in a formal sense that there's nothing else you can do。

 both of those seem very difficult， but progress would be kind of celebrated in either direction。

 frankly。😊，So the focus on， on the rest of today and on next week is just going to be， you know。

 given that our design space seems so limited， let's start getting really creative within that design space and see what we can do。

 Okay， so that's going be the flavor。 So the theme for the next couple of lectures is it's kind of amazing what you can do with these mechanisms for suitably defined distribution。

😊，All right。Cool。So the last thing I want to do today， in the remaining time。

Is I want to introduce you to。A scenario where we can actually get some very strong positive results。

 and we can get strong positive results using an M I DR mechanism that builds on some of the linear programming machinery we've already built up。

Okay。And so today， we'll only have time to just talk about the algorithmic problem。 Well have to。

Pospone incentive issues till next week。So here's the deal。We've got non identical items， M of them。

So the new twist for scenario8s is we're going to have a healthy supply of each of the items。

 okay we're going to call it k， and so normally a k has been equal to 1。

 but nowK is going to be bigger。The problem is going to get easier at the bigger ca。

 the more copies we have。So in total， it's going to be k times M items。

And classes within each class K copy。Now， a bit valuation is going to be a hybrid of unit demand in general。

 so for a given type， for a given item， I don't want more than one copy。Okay。

So K different people are going to be given the K copies of a given item。

 but amongst the different items I have totally arbitrary valuations， monotone as usual。

 but other than that I don't care at all， it doesn't have to be sub modular， anything like that。

So bitter eye has an arbitrary。Monione。Evaluation。VI2。

So notice U is just the set of items and the types of items。And then we have cake copies each。

 so the valuations are defined only on the different types of items。So for example， if K was n。

This would clearly be a trivial problem。I could just give each bid or its favorite bumble。

 there'd be no contention， I could just charge price zero。

K equal1 would be the most general valuation model we've seen thus far in the call。

So the question is， maybe this problem。It becomescomes reasonably tractable from modest values of K and that is in fact a case。

 and it's sort of a nice kind of positive result from the literature here。All right。

 so here's the the I'm going approved。And again， so this algorithm。

 so we're just going to study the purely algorithmic question， maximizing welfare。

The algorithm that I'm going to show you won't directly lead to a mechanism。

 but with reasonably minimal massaging， it will be an algorithm that we can embed in this MIDR framework。

But for today， just an algorithm。So we showed that logarithmic supply is sufficient for a really good approximation。

So for some constant C。As long as K is at least c times log n ends the number of distinct items over epsilon squared。

本案。We can get a1 minus epsilon approximation。I forgot to say what the model is。

Here we're assuming black box valuations。That support demand and value query。

And the algorithm that we'll give。The running time plus the number of queries。Will be probably。

All the relevant parameters。그。So that's what I want to show you in the rest of。The problem where。は。

So we're going to build on the lineium programs we discussed。I was last week。Now in this case。

 so remember， when we're talking about linear programs。

 we're mostly using them to characterize low rise in equilibriumria and relate them to exactness of linear programming relaxations。

Today we're actually so in this case， the valuations are general。

 so we're not going to have what was in equilibrium。

 we're not going to have exactly linear probing relaxations。

 but we're still going to use them in an algorithm， we're going to solve one。

 it's not going to be integer， it's going to be fractional。

 but we'll round it to an integer solution which is almost as good as the fractional。

So they're going to use something called randomized rounding。Again what why rounding。

 well we're going to solve a linear program， and we're going to get fractions。

 things strictly between zero and1， and want to make them zeros and one， so that's the rounding。

I'm going to remind you the relevant linear program。

we had an integer program which exactly captured welfare maximization。

 and then we dropped the in constraints to linear negativity constraints to get the following linear program。

The objective function is just to maximize the welfare。

 so let me remind you we have a decision variable XIS for each bitter eye in bundle S。

 the semantics is this should be one if s is the bundle that I gets in the allocation。

 zero otherwise。The welfare overall， we just sum over the bitterders。

 we sum over the bundles that they might get。And then we pick up the value for whatever bundle they do get whenever that's one。

So what are the constraints， well， we have a constraint for good。Now， previously。

 we said that a good should only be allocate than once。Now we have K copies。

So now the linear program is going to be for good。The total number of times we allocate it should be a most K。

How many times do we allocate it will we sum over the bidders？

We sum over all of the bundles that include the item J。

And that's some over all eyes and relevant essay should be found。

Then we have the usual constraints that。Each bidder should only get to one bundle。

And then we have non negativity constraints。Replacing the previous integrated constraints。嗯。

Thank you。Now I did some hard work last week。When we were proving that we could maximize welfare。

For gross substitutes valuations。One thing we proved along the way is that we can actually solve this linear program in polynomial time given demand queries。

We actually had two parts of that proof， first we showed we could solve problem in the linear program in poly time。

 we actually never used the gross substitutes hypothesis in that part of the argument。

Okay all we did was pass at the due， look at the separation Oracle。

 notice that the separation Oracle was exactly a demand query。

 we assumed that we had efficient demand queries so we were done。

We used the G substitutes hypothesis when we then concluded that， oh， well， fortunately。

 we only had to solve a linear program。But its answer is the same as the integer program that we care about。

That's where we use gross substitutes， and that's what's not true。So a couple things of all。

In any case。The optimal value of this linear program is certainly an upper bound on the max welfare possible for allocation。

 we're searching only over more stuff to maximums only take。So they help the Os。

Is at least the max welfare。So it's a yardsrn stickick against which we can compare the welfare of our own allocations。

And recall。Ellipseoid plus demand queries。You can solve this linear program。In polynomial time。

So that's going to be the first step in our algorithm。it's polynomial in the same sense here， okay。

 queries， number of queries and polynomial and all the relevant。

So the first7 of the algorithm is to do that。And I'm going to denote it by x star。Be the optimal。

Solution。And again， there's no gross substitutes condition。

 so there's no reason to think that this will be anything other than fractional。SoIn other words。

 this is not directly useful for us， this is going to say something like a bitter one。

 give them like 10% of the pair of goods one and two， give them 20% of the goods two and three。

 et cetera， et cetera， what do we do with that？So。The question is， how do we round？

These X stars will bonafide andloc。And can we do it in a way that we can prove that the welfare of that allocation is almost optimal？

How many of you have seen randomized when you're programming routing before？ま。Okay。

 so it's a very natural idea， cool idea by Raabonna Thompson。So here's the key observation。

 so zoom in on some bit， say bid number one。So we have。

 in our hand some feasible solution to this linear program， so for bidder number one。

 we have these x1 Ss。That's sung to in most one。So the observation is we can think of this as a probability distribution over bundles S。

If sums just strictly less than one， just think of the rest of the propertiesbil being on the empty set。

So this is just in their online negative， okay， so that's a profit distribution。

Let's just sample from it， that's going to give us some bundle。

A given bundle with probability proportional or equal to whatever that X star I is。

And we can do that independently for each eye。So given this fractional solution。

 I'm giving you a randomized algorithm that outputs some hopefully some allocation。

And so the randomized algorithm does the following for each bitter eye independently。

 it assigns the items's S to Bi I。With probability X star。Actually for feasibility regions。

Feasibility reasons。Let me scale down the probability a little bit。

 I'll multiply it by 1 minus something。So there's going to be some property left over that all goes to the empty bundle。

Okay， does it clear what I mean？So when the LP， it was 60，40 this bundle or this bundle。

 I make them you know roughly 59 and 39， I flip a coin。

 so de properties of those bundles with 2% they get the emphasis。All right， show。

What properties does this have？So in the analysis we need to do two things。

 so the first thing we need to do is look at the objective function value。Yes。Basically by linearity。

 not a big deal。The second thing we need to understand is feasibility。

Because the thing to realize about this randomized algorithm is it's making random choices in a totally uncoupled way across the bidders。

We have end bidderters， we have K copies of an item， came might to be way less than。Sure。

 in some sense， the expected value， the expected amount of times you expect to sell a good isn' too much。

 but we all know things can deviate from the expectation。So analysis。Okay so first。

 what are the ramifications of the rounding on the objective function value。

 how does that change when we pass from the di fractional solution to this randomized integer solution？

Well， so let's look at the expected welfare of。The allocation produced by our algorithm。

This expectation is only over the coin flips in this randomized rounding algorithm。

So by linearatingating expectation， we can just look at the expected contribution of each bidders separately。

And for a given better eye， we can just expand its expectation and just say， well， I contributes。

VIS to the welfare of the allocation in the event， let's say， VISI in the event。诶。Sorry。なさね。

In the event that S happens to be exactly the items that get assigned to。Well。

 by definition of our randomized rounding algorithm。

 this is exactly the LP solution value XRIS scale multiied by 1 minus epsilon。

So this is just exactly equal to1 minus epsilon I。B I S。X star I。

This was the optimal solution value of our linear program。As a relaxation， that of course。

 is an upper bound on the biggest welfare of any imageger allocation。So this is a lease。

The upshot being that we run this very simple randomized rounding algorithm。

We feel pretty good about the welfare of what was。On average。

 it's going to be within one metapsilon as something which is probably bigger than the best integer solution。

Okay。That's good， objective function， that's the point， objective function and expectation is good。

So what about feasibility？This is the problem。And again。So let's understand this more more detail。

So think about some item J， say the first item。So what are the relevant random variables as we do this randomized rounding？

Well。Let XIj be the indicator random variable about whether bitter I gets a copy of J or not。

Notice that no bidder will ever get more than one copy of item J。

 and that's because just all of the Ss in this linear program represents bundles with the most one copy。

There nobody wants to go。So the sum， so for a given J。

 the sum of the XIJs is just the number of copies of J that get sold。

 okay and we only have K copies so we're really hoping that's going to be the most kit。Okay， so then。

So an expectation was certainly good。By a similar argument is for the depth of function。

 just by linearity。So this again， is for a fixed item J。So， if we look at the。

Total amount of comments that might get sold， again by linear of expectation。

We just look at the expected number that gets sold to J。

J can be sold to I in any number of different ways， any bundle S that includes J。

So this is just over bundles of S for which Jay is a member。Probability that I gets S。Again。

 by a randomized rounding。We know this is exactly x star I times 1 minus epsilon。

Giving us one minus epsilon， some over I， some over S， J and S。Star I。

And X star is a feasible in your programming solution， so at least for the fractional solution。

 we know that in fractional terms， J is not oversold， only K copiesies are sold。So most。

1 minus epsilon。But that's really not good enough。Okay， so we really want a feasible solution。

 we don't want an expectation。Every good is not a whistle really every good did not be a whistle。

 you want to go on a find allocation。So we just had to apply large deviation balance。

Who's seen Choff answer？Excellent。Other percent。That warms the heart， I tell you。All right。

 so let me not even write down， let me just so I'm going to use the turnout bound of the form。诶。

Let's see， so the probability that， okay， so here the YLs。These are independents。Bounded in01。

Namely we use exon Js here， which are indicators。So the probability that this exceeds， it's mean。

By more than one plus delta， here mu here is just the expectation of the sum。

 which was computed to be less minusps alone times k。So so the turnout bound here。OfThis forum。

As you all probably know， the really important property that Truoff found is that this probability is decreasing exponentially quickly in the mean。

So mu is the mean， this is what you're expecting to see， and we want to basically say okay。

 if the realization is not more than 1% or something， more than the expectation。

 so delta' is heres some small constant， we want this to be inverse polynomial。

 that's going to happen once mu is logarithmmic。So many of you probably when I first wrote down k equals omega of log M overrepson squared。

 maybe some of you even already sort of had this in want， but that's where it is， so the log M。

 the problem outset is exactly this mu in this turn up down。That's exactly。Where it comes from。Okay。

 so for us。So apply here。What do we get， we get the probability。

 so given that the expected number of copies of J that are sold is one minus stepspsilon times k。

 the property that's oversold。Is going to be。So just plugging in these things here， so mu。

We can think of as K， Dlta is going to be。Epsilon over1 minus epsilon squared。

And so this is going to be inverse poly， inverse poly and what， so this is just for one fixed item。

Okay we want this to be true for all items， so there's a union bound over the items on the horizon。

 so it's M， so it's inverse poly an M。So it's going to be one over end of the C where C is a constant。

诶。Provided。Let's see， so this is basically the epsilon squared that we want to basically kill the epsilon squared and have a log in the left。

So that's why we have is the logm over epsilon squared as we jack up the hidden constant in the omega notation that jacks up this power down here。

Okay， so that's just plugging in now with a union bound。그 또。So upsha。

So this is our union matter of the items。We are feasible。

With probability at least one minus one over of the sun。Do anyone want more details there to do fast？

So what do we learn？So in a given trial of randomized rounding。So basically。

 imagine we do a polynomial number of trials that ran that around it， because we saw theelP one。

But then we just keep doing it。Basically we're never going to see an in feasible solution。

 that's what this tells us，Each of these trials， which is independent。

 the expected objective functionality is really good within one minus stepspsilon。

 not just of the integer optimum， but even of the LP optum。So eventually within a poll on our trials。

 we're going to see a solution what's both feasible and has。

Objective function value almost as high as this expectation， just by a mark of it。So so。

An apo number of。Randomized rounding trials。Get a solution， let's say get an output。

And I'm not doing this super formally， but all the details are straightforward through just exactly。

Expect them to be。So it is feasible。And again， that means just every good is sold k times at most。

And2。The welfare。So I need a little bit of slack instead of one minus epsilon。

 let's say one minus two epsilon。Again， just for the mark on inequality， which I'm suppressing。

Time is the。So I'm going to write the stronger statement believe it or not we're actually going to use the stronger statement next week。

So we're within  one-2 epsilon of the LP solution。Which， of course， applies in particular that we。

Within 1-2 epson of the max welfare。Just by taking the best of all the randomized rounds。

So we're feasible， we're almost as good as the frac。

So this is a very minor sort of weakening of the guarantee we had for gross substitutes。

 for gross substitutes， we just said solve the LP， you'll get an major solution。

And no was a hundred percent of us。Here， generally won' I mean。

 it's not true that you'll generally get an imageteger solution even if you have this many copies。

 but you can round it to one losing almost。Okay， so the LP value simply will not be much bigger then。

So this solves the algorithmic question in a very satisfying way。

 okay this is still an empty heart problem， I guess I didn't prove that to you， but it is。😔。

But we can get within 1 minus xps1 freedom of the modest logarithmic。カ定す。Sorry。

 so I definitely don't want to don't feel I need to see the proof right now of this。

 but I'm just trying to understand what the formal statement is because。

So you still have some vanishing small， exponentially small probability of failure。

so what do you mean by any a polynomial number of grounds， you'll have a feasible allocation。

I're absolutely right， with high probability， it should all be with high probability。

And this should also be then。With 할 팔。So I mean， it's a Monte car algorithm。m Carlo。

It can be deranimized， I'm not going to do any of that in class。

 I'll try to put some citations and notes。But if you want。

 there are methods so called pessimistic estimators。At the very least。That you can use the。

It was with the same guarantee。So we' solve the approximation question next week。

 we massage this algorithm a little bit so that it becomes MIDR。

 which will give us the decent guarantee for。Similarの。ち強な。

