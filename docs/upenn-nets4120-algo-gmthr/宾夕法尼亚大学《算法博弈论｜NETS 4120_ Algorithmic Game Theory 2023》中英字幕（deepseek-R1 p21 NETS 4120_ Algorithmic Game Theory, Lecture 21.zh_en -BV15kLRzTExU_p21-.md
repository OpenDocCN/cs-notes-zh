# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p21 NETS 4120_ Algorithmic Game Theory, Lecture 21.zh_en -BV15kLRzTExU_p21-

Oh。

![](img/e2a20e289edb3ab985de71418692b32b_1.png)

All right。So let's see just a quick logistics check in。

You guys all hopefully just turned in the fifth homework and the sixth then final homework is now out。

 so like you're almost done with the course。m any logistics kind of questions so I guess like you just got of like do this last homework and take the late night final exam yeah。

How does the participation grading work you know， I guess I'll like。Look on。

Pazza not Piazza do we use Slack and see if you have ever typed anything and I'll look at the pictures and see if I like recognize your face and if one of those things is true。

 then I will give you 100% participation grade。嗯。Does that sound reasonable？Okay。

 good other logistics questions。Okay。U。Okay right， so we've been studying like auctions and pricings and other things for a while with the goal of maximizing revenue。

And just to maybe give a quick recap of things we know。You know。

 if we happen to be very well informed， if we happen to have a prior distribution over where bids are coming from。

 we know how to design。The exactly optimal。You know revenue maximizing auction， right。

 this was this thing we derived with virtual values， we can be like exactly optimal。

And we sort have said， okay， well， you know， that's great but it's sort of annoying to have to gather everyone together for an auction。

 that's not how we sell lots of things it's better to sell things with pricing。And we said， okay。

 well， you know， if we have the same piece of information， you， this belief。

 this distribution over where bitter evaluations are drawn from。

 then I don't need to gather everyone all at once， I can price things and get like half of the optimal revenue。

And then we asked ourselves you know like where did we come up with this prior distribution。

 how do we know a distribution on bitter values what if we don't have that and last class we saw this random sampling auction we said okay you know we can if we're happy with things like half the optimal revenue or maybe a quarter。

 we can achieve it even without knowing this prior。

 so long as we know an auction as long as we can run an auction as long as we can gather everyone in one place all at once and do this random sampling trick。

 then it turns out we don't actually need to know at least for the purposes of approximation。

 this distribution over bitter values。And so。In this class， I want to ask， you。

 can we to just like recapping？For these like exactly revenue maximizing auctions。

 there were like two things we complained about separately and had sort of separate fixes for。

One was not knowing the distribution from which values were drawn。

 wanting something more robust than that that didn't require that。Okay。

 our sort of answer to that was the random sampling auction。The other was not having to。

Gather all of the buyers in one place， not having to like actually run like a one shot auction。

 Our answer to that was sort of this this pricing model we came up with using these profit inequalities。

And what I want to do in this class is see if we can sort of resolve both of these difficulties at the same time。

 whether we can sort of。Get some approximation to the optimal profit。That doesn't require a prior。

 okay that doesn't require knowing where bidder valuations come from and that also doesn't it also sort of looks like a pricing mechanism that doesn't require gathering everyone in one place allows us to sell things sequentially。

Okay， so that's what we're going to try to do in this lecture。嗯。Okay。So in， you know。

 like all of these lectures， we've been sort of。Asking these general questions， but then。

Alyzing them within you know some like particular model as a case study， we've really had two models。

 the single item auction in which I have like that's like one extreme of the auction problem where my supply is one。

 the other was this digital goods auction which we studied last class in the context of the random sampling auction where。

There's no supply constraint at all， it's a digital good I can copy it for free。

 so like in principle I could give it to everybody if that was the right thing to do。

And in some sense， the digital goods auction is the version of these that sort of makes。

Revenue most interesting that puts revenue sort of in the sort of biggest tension with welfare。

 because in an digital goods auction if I wanted to maximize welfare。

 I just give the thing to everybody and welfare would be maximized。

 but revenue would be zero and you have to think about how to limit supply somehow to maximize revenue。

And so I want to continue thinking today about digital goods auctions。

But think about something that looks like a pricing in a sort of sequential setting rather than an option。

Um because， you know， like auctions are just logistically difficult。

 how am I going to get everyone in the same room at the same time？Right， and so you know similarly。

 I want a more robust model， so we're going to think about think about a sequential setting where。😊。

Potential buyers arrive one at a time， but their values are not drawn from a distribution， in fact。

 they could be chosen sort of in some adversarial setting like we want an algorithm that's robust enough that it has some kind of revenue guarantees no matter what the sequence of arriving bidders is。

And so。You know， the way we're going to address this problem in this lecture is we're going to remember back to the like first half of the class and remember our favorite algorithm。

 the polynomialates algorithm that was able to do remarkable things in sequential learning settings right like it had this sort of worst case guarantee that that we could sort of。

Cchoose experts that sort of were guaranteed to perform as well as the best expert in hindsight。

 no matter what ended up occurring， the reason this was useful for us before is we could use them as learning algorithms that agents could use to play games when the losses or games that were arriving were explicitly based on the choices of our opponents in these games so explicitly not distributional here we're going to try to use it to come up with a pricing algorithm。

Okay， so that's the general outline questions about like the。Basic premise before we。Go into details。

Okay。So let's just kind of like remember。Maybe like the moral of last lecture in which we studied this random sampling auction。

Like what was the basic technique？And we have this， you know。

 like useful subroutine called a profit extractor and the thing that it did。

Was somehow if we started out with。A a pretty good estimate for what the optimal revenue was。

Then the profit extractor would would allow us to。Truthfully obtain that much revenue right like in particular。

 this thing like we gave it you know， like a guess independently of the bids of the bidders who were running it on some guess are for like a revenue target and like the promise of the profit extractor was that if it's possible to extract r dollars from these good folks with with a fixed price it will do so it won't promise any more than that it'll never get more than that it'll either get exactly R dollars if it's possible to get at least r dollars or if not it'll get nothing。

Okay。And like the basic trick in the random sampling auction was to so this is great if you know what R is。

 but like yeah， sort of reduces this reduces your problem to like figuring out what R is。

And the basic trick was to like randomly partition people into two halves， estimate R from one half。

 like estimate the revenue obtainable from the best fixed price on one half and then use that for a profit extractor on the other half。

Okay， and the idea was okay， like on a random sample。

 I can estimate statistical property statistical quantities pretty well and the reason I want to use it on the other random sample。

 know the other half is for incentive guarantees like in order for the profit extractor to be truthful。

 I can't pick this number R as a function of the bids that I'm actually running the a on。

But at like a high level， what we were doing is。We sort of reduced this revenue maximization problem。

 this mechanism design problem to like a statistical。Estimation problem， like a learning problem。

Right， like we said the role that the profit extractor played in this algorithm was that of a reduction。

 it said if you can。Solve the statistical estimation problem， like from one subsample of data。

 predicts what the optimal revenue obtainable is on another subsample of data。

Then you've got a solution to your to your auction problem and that's what we did like we sort of solved the statistical estimation problem in like the most straightforward way。

 which is to just compute take a random sample and compute the quantity we want on the random sample and use the fact that。

 you know， if we sample a bunch of points that they sort of tend to reflect the underlying statistics of the distribution from which they were drawn。

Okay， so we was sort of like， you know， at the highest level last lecture was。

Some reduction from mechanism design to like statistics or you know， machine learning。

 some kind of estimation problem， but like we did it in a way that required everyone be upfront because we had to take this random sample of people。

Okay。And so。At a high level， like what we want to do。Today is exactly the same thing we want to。

 we're starting with a mechanism design problem， we want to reduce it to some learning problem。

But we want to do it in a setting where we don't have all the bidders up front。

 the bidders arrive one at a time。😡，Okay， so it's like an online learning problem。

which is a problem at least of a style that we've seen before where you have to sequentially make decisions as you know。

 like rounds of some interaction proceed and you want guarantees about the performance of your decision making process in hindsight。

Okay， so that should hopefully sound familiar and that's why maybe already at this point it sounds like a natural idea to try to take advantage of the polynomial weights algorithm。

 which was an algorithm we derived in basically exactly this setting。

 a sequential decision making problem。Okay。So our goal is to find a dominant strategy truthful online option to approximate the optimal revenue。

😊，嗯。So okay， so let's like parse what we mean by like these words like starting with like what's an online auction。

 what do we mean by optimal revenue。So by online auction， I mean the following kind of setting where。

Bitders like potential buyers， they arrive sequentially Okay， like add day T。

 like bitterter T arrives。And bitter T will enter their bid。But。

I can't wait until tomorrow or the next day to figure out the payment or allocation for bitter T like bitter T arrives they report their bid today。

 and I need to figure out。Whether they get the good or not and how much they need to pay today without the benefit of knowing who's going to come in the future。

 okay that's what I mean by like an online auction。And。In a lot of respects。

 the thing we do today will kind of look a lot like a pricing scheme in that you know。

 really what we're going to be doing is we're going to be deciding on a fixed price every day to sell the item at but。

For a reason that I'll point out， you know， basically just for convenience in like reducing this to the polynomial weights algorithm。

It'll be a little bit easier if we think about this as actually an auction and just to sort of remind you of the difference between like a pricing and an auction。

 even if I have a fixed price，In mind behind the scenes。if I just put a price tag on something。

 I say that this is $10。And then you buy it。I know that your valuation for the item is at least $10。

 but I don't know what it is exactly， it might be $11， it might be a million。

 similarly if you don't buy it， I know that your valuation is like less than $10 but I don't know what it is exactly so I learned sort of the single bit of information is it bigger than the price or less than the price。

And so it's going to be a little bit easier for us to instead set this up as an auction where I have in mind some price $10。

 but what I do is I say okay， you know give me your bid and the rule is just that if your bid is above the price。

 I'll give you the item and I'll charge you the price and if it's below the price I won't。

Everything that sort of happens in the end is the same as if I use just a fixed pricing。

 but then I know what your actual evaluation was， which is just going to be like convenient for us like you'd really want to do a pricing。

 not this basically all of the techniques we go through today could be used to come up with a purely pricing based algorithm。

 it would just be a little bit more complicated and next lecture we're going to see a pricing scheme anyway。

Okay， but that's like the different like like morally you can think of everything we're doing today and you'll see very specifically。

 you know what the algorithm is going to be doing is choosing a price every day， but。😊。

I'm going to describe it as an auction because。There's a couple things that are going to be easier if we actually get to learn what the bid and since it's going to be a truthful auction。

 the actual value for the buyer is that arrive today rather than just this one bit of information was it above the price or below but I just want to emphasize this is not like a crucial aspect of the problem if you like think a little harder you can。

Solve the problem with in basically the same way in this more limited but more natural setting。Okay。

 so that was like online auction。What do I mean approximate the optimal revenue remember we sort of wrestled with what like optimality should mean in the context of revenue and that was what led us to define you know like this setting where we have a known distribution over bid evaluations that allowed us to talk about the optimal revenue auction you know the dominant strategy truthful auction that maximize revenue and expectation and then like last lecture we noticed that。

Well， if we knew what the distribution was。And the bidders were indeed drawn IID then like what we derived is that in the digital good setting。

 at least the optimal auction would correspond to like a fixed pricing， basically like we'd say。

 you know， Microsoft Windows costs 99999。嗯m。Which？Gave us reason to think that maybe。Competing with。

The following benchmark， which we could define even without a distribution made sense and that and just a maybe like going through。

 you know， some of the。Hoops we went through last time， I you he to say， okay， well。

 if we knew a distribution and if it was that everyone was drawn from the same distribution。

 the optimal auction would charge everyone the same fixed price。And so， you know。

 maybe what we should do is we should compete with the revenue obtainable by the best fixed price in hindsight。

 I don't need to talk about a distribution to define the revenue obtainable by the best fixed price in hindsight。

Okay， so if we had something that for any collection of bids was was able to get revenue competitive with the best fixed price in hindsight。

 that would be pretty good that because in particular， like if bidders were drawn。

IID from some distribution， that would be competitive with the optimal obtainable revenue。But like。

 yeah， there was like a little problem with competing with the best fixed price and hindsight。

 which is that。You know， like。If I charge P dollars。

The revenue I'm going to get is P times the number of people who are willing to pay at least P。

And in principle， there are settings where the best fixed price in hindsight sells only one person。

And that's a problem because。You know， if I'm selling to only one person。

 like the best fixed price is going to be exactly their bid， exactly their value。

And I'm not going to be able to compete with that with a truthful auction right like like you know。

 like in order for the auction to be truthful， I have to basically come up with a price that does not depend on what you told me right like if the price I'm offering you depends on what you told me and therefore there are at least two different ways for you to win the item at different prices。

 you'll always misreport whatever causes you to win at the lowest price。

And so like I can't like compete with the best price in hindsight if I'm going to like。

 if it turns out that the best price in hindsight sells only one person because the only way to do that would be to charge their value。

 which I can't do in a truthful way。And so we defined like。Just like weaker benchmark， that was like。

 what's the revenue of the best fixed price in hindsight that sells to at least two people？Okay。

 and we saw okay， like we should think of this as like a reasonably modest weakening of the benchmark because if we're actually in like a digital good setting where we're producing lots of things。

 you know， probably we're going to， you know the best fixed price will probably sell lots of copies not just one。

Okay， so。Like last class we gave， you know， in this like random sampling setting。

 an algorithm that gave like a four approximation to the best fixed price that sells to at least two people。

And we sort of remarked at the end of class that like， you know。

 if you were willing to make two a little bit bigger， three， four or five。

 the best fixed price that sells to like K people， then you could also make this number four better。

 you know， like you can get sort of a very close approximation to the best fixed price that sells to at least。

 you know。Thousand0 people。And so like that's sort of what we're going to。

Do like we're going to give sort of an incomparable kind of result that rather than getting a four approximation to the best fixed price that sells to at least two people is going to somehow give like a one plus epsilon approximation for the best fixed price that sells to at least k people for some larger。

 but hopefully not crazy value of k。Okay， does all this make sense？Okay。So。嗯。

Let's just define the setting。So in this online digital good setting。

We've got and bidders who each have some valuation that we don't know。

And let's just scale things without lots of generality so that the valuations are numbers between zero and one。

And so it's a sequential auction， there's a time component here。So at time T。

Bitter T arrives and bids， they report some valuation VT prime。

I put a prime there because although our hope is to design a dominant strategy truthful mechanism。

In principle they could lie right so if we you know like if we designed something that was not dominant strategy truthful。

 they might report something that is different from their true value hoping to gain some advantage。

And then， you know， it's like a mechanism design setting。

 so we'll have an allocation rule and a payment rule。😊，Okay。

 so as a function of their bids and of other bids we've observed so far。We will decide at round T。

 whether to allocate the item to them or not and what to charge them。And。You know。

 like other than like writing on this slide that， you know， time proceeds in rounds t。

 like how do we actually encode in the model that。You have to make decisions as bidders arrive without using information that you know you don't know yet well。

The allocation rule and the payment rule we use at day T。Are defined as functions of。

The bids we've received from days one through T in particular， not for days t plus one or larger。

Okay， which is just sort of encoding in our model this aspect of time we cannot make decisions as a function of things we don't know yet right the bids that arrive at date t plus one and day t plus two those are in the future and so。

They're not inputs to our allocation。Okay， so this is just sort of like。

The part of the model that is。Encoding the temporal aspect of this auction that the decisions made at dayT can be a function of only of the bids that have been received up through dayT and not in the future。

Okay。嗯。And so。You know， there's a particularly simple auction format so that， you know， in this case。

 if you think about it a little bit， is that kind of like without loss of generality？

That is really just a pricing。But like a pricing in which I ask you first to what your valuation is。

And I'll call it a take it or leave it auction。And it's very simple。So。You know， basically。

 like at day T， before I see the bid of today's bidder。

 what I'm going to decide on is what is the price for the good that I'm selling。Okay。

 and I'm doing this before I see today's bidder， so the price that I'm going to come up with for the good that I'm selling。

 it's a function only of the bids I've received in the past。Okay， not including today's bidder。Okay。

 so maybe you know， I've done some like market research based on。The history of sales so far。

 I've decided on what I think is a good price for today。

 I commit to this price independently of the bidder who's going to arrive today。

And then like the bitter。At dayT shows up， they bid something VT prime and the allocation rule I use is and the payment rule I use is just sort of the rule that corresponds to selling the item at this fixed price。

 ST。In particular， like they get the item exactly if their bid is above the price I decided on。

 otherwise they don't。And。If they win the item， then what I charge them is the fixed price。Okay。

 so so in terms of the outcome， this is like exactly the same as if I had just before they walked into my store。

 you know， got out my。Price sticker gun， price tag gun and。

You know put this price S on the good that i'm selling right like when they walk into my store。

 if it's worth it to them to buy the item if their value is higher than the price。

 they buy it otherwise they don't if they buy it the payment tech collect is exactly equal to the price。

But this is just phrased in terms of an auction and in particular like。

Set up this way I actually observe like what their bid was。Okay。

 but like the point is that the item is for sale every day at some fixed price ST。

And the price is computed independently of bittertert's own bib。Okay。

 so pretty straightforward auction format， basically just a fixed pricing。With， you know。

 an auction artificially layered on top so that I can。Collect your bid。Questions about this。Yeah。

 this family of auction， these take it or leave it a。

And this is what we're going to be thinking about today， auctions in this form。Okay。

 one thing I'll note is that like。The only moving part here。

 the only thing that is left to design is。The rule that decides on what is the price to charge today as a function of the history。

Right once you once you figure out how to。Map a history to a price like you're done。

 then this is your scheme。Okay， and。You know， like sort of a quick observation。So immediately。

Like any auction in this format， any take it or leave it auction is dominant strategy truthful。Okay。

 like you have no incentive to misreport your value， you might as well report。

 you might as well bid your true value。And the reason is because the you know behind the scenes there's just this like fixed price ST that you're facing that was computed independently of your own bid so so your bid doesn't affect this price right like what happens is you win and you pay the price if you bid above the price。

 you lose and you pay nothing your bid if your bid was below the price。是。But like crucially。

 you have no way of affecting the price。So what could happen by misreporting？

RightLike if you're already winning the item by reporting truthfully then。Shading your bid upwards。

 you know， raising your bid doesn't help， doesn't change the outcome at all because you still win the item at exactly the same price right you weren't paying any function of your bid you were just paying the price。

And if you shade your bit downwards， if you sort of under report。

Well it'll you know for a while do nothing so long as you still are bidding above the price and at some point it'll cause you to lose the auction not get the good and that's a bad outcome for you because。

The good was worth more to you than the price。Okay， so if if。Your value is above the price。

 then it's a dominant strategy to report truthfully。And similarly， if your value is below the price。

 there's no reason to lie right， like if you under report。

You to lose nothing happens if you over report the only thing that can change changes is when your bid。

Goes above the price at which point you win the item， but you have to pay the price。

 and that's a bad outcome for you because the price was higher than your value。Okay， so either way。

 it's a dominant strategy to report truthfully。Okay， and the reason is very simple， it's because。

The price was computed independently of your bid。And in fact， like。Yeah and。

There's a sense in which this is really the only auction format。

 like it's not like you could be more clever and come up with like a fundamentally different auction in this setting that was also dominant strategy truthful。

Maybe you could be a little clever with randomness， but you know with the deterministic mechanisms。

 there's really nothing else you could do。And the reason is because。

This is a single parameter domain。Okay， like you just care if you win or lose and the， you know。

 your private piece of information is just。You knowYour one dimensional value。

 how happy you are if you win。And we know that in single parameter domains。

In order for an auction to be truthful， that one is strategy truthful。

 the allocation rule has to be monotone。Which just means that， you know。

 your probability of winning has to monotonically increase as you raise your bid。

And if it's a deterministic auction。Your probability of winning as a function of。Yeah。

for any particular vector of bids it's just zero or one。

 so that means that as you raise your bid you know at some point you go from losing to winning。Okay。

 and the payment rule in any such setting， the payment rule that makes this truthful is always going to be。

The lowest you know you are going to have to pay the lowest bid you could have made that would have still caused you to win that's what the payment rule sort of reduces to。

Which means that whatever this threshold is that must exist that causes you to go from losing to winning。

 that's the price。Okay， so in some sense in like a dominant in a in a single parameter domain。

 you know， like a take it or leave it auction is really like。The only possible auction format。

 like you know， behind the scenes as a function， perhaps of other people's bids。

 there's basically a fixed price that has been decided upon and if you you know。

 if you bid above that you win and you pay that price and otherwise you don't。Okay， so it's simple。

 but like in some sense， at least in single parameter domains。

 all deterministic options have that form。Okay。Questions about that。Okay。So remember， okay。

 we we sort of understand what， you know， like dominant strategy truthful auction have to look like in this setting like basically。

All of the action is just deciding on what price to charge at dayT right that's the only moving part in this family of take it or leave at auctions what price do we charge at dayT we have to decide on that as a function of what's happened in the past。

And you know， we'd like it to be a good price it right。

 we'd like to decide on good prices that cause us to make lots of money。

And so our goal is to learn somehow the best fixed price because our benchmark is。You know。

 like it's not like there's since there's no distribution， it's not like upfront。

 there exists a best fixed price。RightWhat ends up being the best depends on what happens。

 but we'd like to make as much money as whatever turns out to be the best fixed price in hindsight because that's our benchmark clause。

And so when I say that sentence， like we want to like make as much money as whatever turns out to be the best fixed price in hindsight。

Like you should be remembering the polynomial weights algorithm because that was sort of like the whole point of the polynomial weights algorithm。

 like we had these experts。And the polynomial weights algorithm gave us a way of choosing experts such that no matter what happened。

 we ended up doing as well as the best expert in hindsight。Okay， so。

Since our benchmark here is making as much money as the best fixed price in hindsight。

Like maybe we should be thinking about using the polynomial weights algorithm and somehow associating prices with experts。

Okay， like the experts are just suggesting to us that we play different prices。

And so let's just refresh our memory on the setting and guarantees of the polynomial weight algorithm and you know when we derived it。

 we were talking about losses， I think you want to every expert every experiences some loss and you want to have cumulative loss that is not much more than the best expert in hindsight。

 the one with lowest loss。看给了。Remember all of the bounds as if they were for gains other losses。

 but basically the same thing after you know， whatever the loss was before the gain is one minus that。

Okay， so here's like the setting in which the polynomial weights algorithm operated with sort of losses replaced with gains。

嗯。We've got some finite collection of N experts。And。Every day we have to choose one of them。

And at the end of the day， like we learn that that each of the experts， I experience some gain。

You know， GIT at dayT。Could be anything， right these could be chosen by an adversary。

And right the polymial Os algorithm gave us away every day before we learned the gains for the experts to choose an expert for that day。

And the algorithm experienced the gain of the expert it chose。

Like he followed the advice of that expert and whatever gain that expert got you get to。

And the promise was that。You know like。you play this algorithm consistently for T rounds。

Then no matter what the sequence of realized gains over these an experts turned out to be。

Like the worst case over sequences， no matter what。If I looked at the cumulative gain。

Of the algorithm。That was nearly as good as the cumulative gain of the best expert in hindsight。

 which was to say it was larger。Then。The game you would have gotten by playing any one of the experts consistently every single day。

Minus some term that sort of right you don't do quite as well as the best expert。

 minus some term that grew like only sublinely in T。

 so it grew like root T and grew only logarithmically with the number of experts。Okay。

 and so the idea was like if I look at the average gain over time， right if I divide both sides by T。

Then on average， I do as well as the best expert minus some term that like tends to zero。

 minus this regret term that gets smaller and smaller， the longer I play。Okay。We spent like。

 I don't know， it felt like a whole half a semester on this thing。

 does this sound like vaguely familiar？Okay。Okay。So the basic idea is pretty simple， you know。

 like we just want to like use this。Algorithm as a black box。And somehow encode， you know。

 I want to like take some collection of experts and I'd like to encode I'd like to associate each expert with some price。

And I want to like。Have the rewards that I assign to the experts and that I report to the polynomial weights algorithm。

Yeah I'd like to have those somehow correspond to the revenue that I would have made each day had I used that price。

So that the。Gain of the best expert in hindsight is exactly the amount of money I would have made had I used some fixed price consistently。

And then I'd like to choose prices using the polynomial weights algorithm so that hopefully I can read off of this。

Guarantee that like the revenue that I make is at least the revenue of the best fixed price。

 this benchmark I'd like to compete with minus something that hopefully becomes negligible compared to。

Overall revenue as time goes on。And like。The one complication we might run into is that。

There's a lot of prices I might charge between zero and one。There's like continuously many prices。

And。This algorithm only makes sense for like finite collections of experts and in particular like。

Although log n is small as a function of n， like。The bound doesn't say anything nontrivial if I have like infinitely many experts。

Okay， so you know。Like。We'll have to deal with that small complication。Okay。

 but that's the basic idea and you know， like probably。

Most of you could work out the rest of the lecture from here， but let's do it。So。The idea is。

 you know， look we there's continuously many prices between zero and one。

 but like let's fix some collection of them， we'll return later to like what's a good set to fix。

 let's fix some finite collection of them and treat them as experts and just you know proceed from here。

Now， okay， so like， you know， every day。Our algorithm is going to choose an expert and we've now associated the experts with prices and so you know。

 presumably when the polynomial weights algorithm says， you know， play expert five。

 what we're going to do is we're going to， you know like try to price the item at five。

And then we'll see what happens， you know， the buyer will buy the item or he won't。

But we're going to have to like go back to the polynomial weight algorithm and report to it a vector of gains。

 one for each of the experts， like that's what that's the feedback it's expecting。And so like。

 what should the gains be？And so what we'd like is to associate。😊，You know， the reward of the expert。

 the gains of the expert with like the revenue that we would have made had we。

Picked the price advocated for by that expert。And so like let's just think about what those are， you。

Suppose there's some expert who is， you know， every day suggesting that we price the item at S dollars。

Well， at AT， like how much money would we actually make if we priced the item at S dollars？Well。

It's given by this simple function， we would make S dollars exactly when the valuation of the buyer who arrived today is bigger than S when the bid that showed up today was bigger than S right because then the item sells at exactly the price we set。

 which was S。And。If the valuation was smaller than S， we make nothing right。

 So there's sort of like this discontinuity here， right like。At your value。You know。

 if I'm a little bit， if the price is sort of a little bit below your value， that's fine。

 you'll buy the item， but if it's a little bit above your value， all of a sudden you won't。Okay。

 so it's like the step function right I make S dollars if the value of the arriving bidder is above us and otherwise I make nothing。

And so let's the let's set the sort of gains to be this function right so we have a bunch of experts each of which are advocating for selling at some different price S。

Every day what we're going to do is we're going to you know run this take it or leave it auction at this price S。

And。This is the place where it's it's convenient that we're sort of running the auction rather than just using a fixed pricing because when we run the auction。

 we actually learn what VT is what the what the bid。

 what evaluation of buyert is and that's what lets us。Compute。This number。

 not just for the price that we chose， but for prices we didn't choose。Okay。

 and for the polynomial weights algorithm， we need to be able to report the gain。

 not just for the expert we chose， but for the experts we didn't choose。Okay。

 so that like right so so these are the gains we're going to report to the polynomial weight algorithm for each expert who's like advocating sell it a price S the gain we're going to report to it is S dollars if it turns out that。

Today's buyer had valuation bigger than S dollars and will report back to it0 otherwise。Yeah。第是。

There's nothing special about011， but you know somehow。

Guarants of the polynomial weights algorithm or any algorithm will have to scale with the range of the rewards right like if if your algorithm has some regret bound right you're doing only epsilon worse than the best expert if all of us sudden and I said okay。

 like you know actually the rewards are multiplied by 100。Okay， well now your algorithm is doing。

 you know， 100 epsilon worse than the best expert， not because anything fundamentally has changed but because I'm multiplied by 100。

So there's nothing special about the interval between zero and one。

 but like if the gains were going to be。You know， between zero and a million。

 we'd have to multiply this by a million。Does that make sense so you know if if instead of you like what does it really mean to like rescale without loss of generality so that the values and the prices are between zero and one。

 it means that to the extent that we have some reasonable upper bound on what the values might be we're going to like。

Divide everything by that upper bound so that the rescale values are between zero and1。

 but it means that you know， like when we convert back to the original values。

We're going to multiply everything back by that upper bound and so whatever your upper bound B was on people's values for the items。

 it'll show up here that your bound does that make sense？So yes。

s like it's it is sort of important to that。You know the scale of the values。

There's nothing special about zero and1 saying things are scaled between zero and one。

 it's sort of like saying。They're scaled between zero and something。

 and we're willing to pay in our bounds for what that something is。Good question， other questions。

Oh and yeah， just to like。 this difference between like auctions and pricing， right？

Even if it was if it was just a pricing if we sort of said， okay， I'm going to put a。

Price tag on this good for S dollar it' not just observe， you know， does it sell or not？

Then I would know the reward for expert S， like I would know how much money I made by selling this thing at S dollars because I would have seen whether it's sold or not。

 but I wouldn't necessarily know counterfactuals， I wouldn't know how much money I would have made today had I sold the item instead at you know S plus one。

It might have been that I would make S plus1， maybe the buyer would still have been willing to buy。

 or it might have been if I had raised the price by a dollar or I would have made zero today because I would have exceeded their value。

So if I。With just pricing things and not running a ticket or leave it auction。

 then I wouldn't be able to figure out what the counterfactual rewards were I wouldn't be able to figure out。

Without。At least having some clever trick， how much money I would have made had I set other prices。

 and therefore I wouldn't be able to compute。This vector of gains for each expert that I need to feed into the polynomial weights algorithm right because the polynomial weights algorithm needs to know the gain of each expert。

 not just the one you picked。Okay， and so just to sort of say a little bit about what you'd need to do to turn this into a pricing algorithm。

You'd need to be able to basically。Figure like figure out a way of coming up with like an unbiased estimate for those counterfactual rewards。

 how much money would you have made had you priced the item differently。

And you can do that basically through experimentation。

 like you can sort of build into this some like aB testing where with some probability I follow the。

Recommendation of the algorithm with some probability I pick a random price and so you can sort of do experiments to get estimates for what counterfactual rewards would have been and if you layered that on top of this you get a pricing mechanism。

 but just to you know so that we understand。This is the step in which we are making use of。

The fact that we're actually eliciting goods。Rather rather than just selling things literally with pricing。

Questions about that。Okay。Good so like。We can talk about the revenue that we would obtain had we used some fixed price P for the first T bidders。

Rise is just。P dollars times the number of sales we would have made had we sold everything at this price P so it's P dollars times the number of bidders who showed up before round T whose valuation was in fact bigger than P dollars that's the number of sales we would have made at price P。

And so like by construction because。The gain。The way we assigned gains to each of the experts which correspond to prices each gain was。

You know， for the expert advocating price P， it's P dollars if。

A sale is made to the bidder at day T and zero otherwise right bike construction。

When I sum up the cumulative gains for an expert from day one through T。

 when I look at the sum of the amount of money I would have made from the expert who corresponds to selling at P dollars。

From days one through T， that is equal to the revenue of price P。You know， up through day team。

Right like sort of sort of directly by construction。

 we just like defined the gains so that the cumulative gain of expert P up through dayT is equal to the revenue we would have made consistently selling at price P every day that was like the reason we defined the gains in that way。

And so。Because of this direct correspondence。If we use the polynomial weights algorithm。

As a price selection mechanism。Okay， selecting a price from some finite set n。

In every round and then actually use that to set the price and then。

Observe if the item sells or not at that price and then compute the gains， you know。

 the amount of money we would have made at each of the prices in the set end that we could have set and feed that back to the polynomial weights algorithm。

Well。You know， we can just take the bound of the polynomial weights algorithm， which we proved。

Some months ago in a very general setting。Just sort of notice that。

The gain of the best expert is the revenue of we get by consistently selling at some fixed price P and find that like the revenue we obtain。

Is at least the revenue of the best fixed price in this set n in this finite set n that we chose？

Minus。You know，Le some。Amount equal to the polynomial weight bound that sort of scales with the square root of the number of rounds we've run and the log of the number of prices we're considering。

So this is almost where we want to be， but not quite。Because。

Like we want to be able to say that we are competitive with the best fixed price period。

That's not yeah what we've said， we've said we're competitive with the best fixed price amongst the set of prices n。

That is necessarily not all of the prices。Right like there there's like infinitely many prices we could have chosen。

And our bound gets worse in some mild way with the number of prices we choose to compete with。Right。

 so there's like this trade off we have to manage， which is that。

We can't compete with the explicitly with the best fixed price overall。

 we can compete with some finite subset of the best fixed prices and。Presumably。

 the more prices we choose to compete with。You know。

 like the closer the best fixed price in that subset will be to the best fixed price overall。But。

 you know， like the worse our bound will be。So there's still this question if we want to connect this to the revenue obtainable with the best fixed price period。

Like how we should choose the set of experts， how we should choose the set of prices that we want to。

Be able to compete with。Yeah， like do we have like spirit？我人同佢签，但系嗰得分心系你俾我哋话。Yeah。

 so if you like divide both sides by T， then you get。You know。

 then the roots in the denominator so maybe the way we have sometimes。

Written these bounds down is rather than the cumulative payoff we said what's the average payoff over time。

 which is like dividing by t yeah so so like if I'm looking at the average reward。

 then this is going to zero。If you like actually use the entire animals very long as your crisis and might treat it the weight as like a PDF of a continuous function。

 like does this it it actually work in practice or was a lead of time to get do it？It would work。

 but you'd have to think about like how to do it and what the regret bound would be it wouldn't。Yeah。

 like eventually it would work， but you'd have to。Think a little bit yeah like both literally what is the algorithm like how do you choose prices every day you know you'd have you'd have to implicitly maintain some continuous distribution so you're not explicitly maintaining weights for each price anymore and。

Something would have to replace this law again and you'd have to figure out what that something was。

 but but yes like if you wanted to。Do this in。A way that doesn't involve the like discretization hack that I'm about to subject you to。

 you could。Good question。嗯。Other questions？It's like with that like。Basically。

 there's some trade off we need to manage， you know， like I can get。Yeah。

 I could compete with just like two prices， you know。

 like one and one half in which case the log in would be really small。

 but you know like the guarantee that I do as well as the best of these two prices would be quite weak compared to the guarantee that I do as well as the best price overall。

 I could compete with。10 trillion prices in which case maybe I'm really close to。

Maybe one of these 10 trillion is going to make me an amount of money that's close to the best price overall。

 but now log n is maybe big and the question is how to trade those things off。Okay， so let's。Yeah。

 there's also sort of different sets of prices we could choose， but let's maybe。

Make our lives simple by sort of thinking about like a one parameter family。

 suppose I just think about discretizing the prices。Sort of uniformly in some grid。Okay。

 so there's like a discretization parameter alpha and I'm gonna you know the prices I want to compete with are like。

 well I guess there's no point in competing with zero like zero the price zero would always make me zero revenue so you know I'll compete with the set of prices alpha two alpha three alpha four alpha all the way up to one as I make alpha smaller this contains more prices as I make alpha larger it contains fewer。

So maybe like the。There's like two things we care about right we care about how big is this set because that shows up in our regret bound。

And we care about。How close is the revenue to the best how close is the revenue of the best price in this set to the best price overall？

Because because that's what's going to allow us to。

Transfer between the bound that's explicitly promised by the polynomial weights algorithm。

 which just promises that we're competitive with the best price and the set to the best price overall。

So the first of these questions is simple how big is the set well， if you know。

 if I'm counting from zero to one by like multiples of alpha， well。

 you know I have to count one over alpha many。Steps， right， the size of the set is one over alpha。ok。

Now。The next question。What is， you know， how can I compare the revenue of the best price and this discrete set to the revenue of the best price overall。

 that's not too hard either， but you have to。It be know at least a little bit careful because。

I could have two prices that are very， very close together。But have vastly different revenues。

Like suppose the best fixed price turns out to be P dollars。And。I don't have P in my set。

 but I've got P plus epsilon in my set for some tiny， tiny value epsilon。

 something that's really close。Well it could be that if I sold everything at P dollars。

 I make a ton of money， like P times t dollars， maybe everyone buys it。

But if I sell it at P plus epsilon dollars， even though I'm really close to the best fixed price。

 like I'm only epsilon away。I make$ zero because maybe everyone's value was actually exactly P。

And as soon as I raise it by even like a little bit， all of a sudden everyone。

Goes from buying the item to not buying the item。So like that's the concern right。

s like what you immediately have。When you chop up the space of prices， you know。

 which is initially the continuous interval from zero to one into。You know， like this discrete grid。

You know alphapha two alpha， whatever what you immediately have is that。

For every price in the unit interval， there's something that is within alpha of it in this discrete set。

But that's not enough， right， because it's not the case that。😊。

Just because my price is within alpha of the optimal price that the revenue is comparable right like if I raise the price by a little bit。

 the revenue could like drop to zero。Okay， but it is the case that if I lower the price by a little bit。

 then the revenue will。Degrade sort of continuously with the price right sort of an asymmetry here if I raise the price by a little bit。

 the revenue could like discontinuously drop to zero。But if I lower the price by a little bit。

 that can't happen。If I lower the price by epsilon。

 what happens while everyone who is willing to buy before？It's still willing to buy。Okay。

 from each of them I previously made P dollars now I make P minus epsilon dollars。

 but like they don't stop buying。And actually like maybe my revenue rises discontinuously。

 like maybe there's now many more people willing to buy， but it can't like drop precipitously。

That's the asymmetry， right if I raise my price by some epsilon， the revenue can like。

Precipitously drop。But if I lower my price by Epsilon， the revenue could precipitously rise maybe。

 but it can't precipitously drop。Does that make sense？And so。What's important about this set。

 you know， the important feature of this set of prices， it's not just that。

There's guaranteed to be a price that is nearby the optimal price。

What's important here is that there's guaranteed to be a price here that is。

Nearby the optimal price and strictly smaller than it。Okay， so the claim is that。

If I look at the revenue obtainable by the best price overall。

 like if I'm allowed to pick any price and the continuous interval between zero and one。

That's at least。The revenue obtainable。By the best fixed price。Or sorry。

 if I look at the revenue obtainable buy the best price in this discrete set。

That might not be quite as good as the revenue obtainable by the best fixed price overall in the continuous interval。

 but it can't be too much worse in particular， if there's n bidders it can't be worse than the optimal revenue by more than alpha times n。

Okay， and the reason is because。No matter what the best fixed price in hindsight turns out to be。

I'm always guaranteed that there's some price in my discrete grid。

That number one is smaller than the best fixed price， that part's important。

But number two isn't too much smaller， is smaller by at most alpha。Okay， yep。即下会诶啊。Because of lesson。

Then the optimal revenue is less than alpha n。And so。We are happy if we sell， we're happy。

 we satisfy this guarantee if we make zero dollars， which we it's easy to do。Does that make sense？

Yeah。Like， I don say volunteer that like。是。This is summed across all rounds。And so small and。Oh yeah。

 maybe small n should be like big T this is like this is the number of bidders。

number of bidders timesYeah， this would be like alpha times t if t is you one bidder shows up in each round the total number of bidders is capital t like what this is saying is the amount of revenue you're losing by using a price that is alpha smaller than the optimal price is。

Potentially as large as alpha times the number of sales you made。Because。

At every for every sale you could have made at the optimal price。

You would still be able to make it at this lower price because people are only more willing to buy at lower prices and the。

Imount you know the and at the lower price， you make， you know。

 alpha less money because the lower price is potentially alpha less and。In the worst case。

 previously you were selling to everybody。You're still selling to everybody， but at you know。

 alpha less revenue per unit， and so your loss in revenue in total is alpha times the number of units sold。

of course， things could be better than this， right it might be that by lowering the price a little bit。

 you actually make a lot more money。Okay， but in the worst case， the you know。

 by restricting yourself to prices that are sort of on this grid。That has with alpha。

 you know your distance from optimality is not more than alpha times the number of potential sales you might ever make。

Does that make sense？Yeah。Okay， can you say that like a little louder maybe？Oh。Yeah。

 it's a good question so like in this particular case。

I don't think you could gain much at least because。嗯。

Ultimately the cardinality of the set N is going to show up inside like a log and so I don't think asymptically you're going to be able to improve much on this。

But there'st。Yeah there's no reason that picking this in sort of like arithmetic series is necessarily optimal and in the next lecture where we give an algorithm that has this for pricing that's going to have a different dependence on M we'll see yeah like maybe it's sort of。

😊，Better to pick like a geometric series， which， as you say， has。You know。

 more density lower down it is right yeah that like。

This I'm not this end is not necessarily like exactly optimal like it's just chosen to be simple in this particular case。

 I don't think you could make meaningful gains by choosing it differently。

But maybe a little bit in other settings， you might be able to。Good question。Okay。So。

We can sort of plug in this bound。So we can plug what we've just sort of calculated into the bound of the polynomial weight algorithm。

Now remember the polynomial weights algorithm， what it says is。We do as well as。

The best price in our finite set M。Minus some regret term that scales logarithmically with the cardinality of our finite set an instead of experts we're competing with。

And so if we pick this set that。Depends。If we pick this set that is sort of discretized at this granularity alpha。

 well then the size of the set is one over alpha。And if we want to ask how well we're doing in comparison to the best price overall。

 not just to the best price in our finite set， and we just saw on the last slide that like we have to subtract off another alpha n term so this additional alpha n term is the additional regret we might have。

Coming from the fact that the polynomial weightights algorithm was only competing with this finance set。

Now we get to pick alpha， right like alpha is like a parameter of the algorithm。Right。

 like we just decide on what that is。And so。We might as well pick alpha to make this bound as strong as possible。

Right， like there will be some optimal value of Al and it's not。

One and it's not infinity right like there's a trade off here because you know， like on the one hand。

 we've got this one term that's going to get better， you know， the smaller we make alpha。

And on the other hand， we've got this other term that's going to get worse。

 the smaller we make alpha。Okay， so it'll be some optimal value sort of。

 you know in between zero and one。And。You know like。Rather than。

Doing some calculus to find the exactly optimal value， let's just pick like a pretty good one。

Suppose we pick alpha to be like one over n。Then this just becomes minus1。

This becomes inside the square root to and log n。And two。

 root n log n is going to be bigger than one。So we can say that the revenue of the polynomial weight algorithm。

Is actually competitive with the revenue of the best fixed price overall out of the， you know。

 whole continuum of prices minus you know， this last term that we've been a little sloppy with so you could improve a little bit。

 but。We get the asymptotics right， minus maybe three root and log n。

 where here n is the number of bidders， the number of rounds that we've run this thing for。Okay。

 so let's think about this。Guarantee。How does it compare to like what we showed about the random sampling auction？

Like strictly speaking， this is incomparable to what we showed about the random sampling auction because。

We showed the random sampling auction gives like a four approximation to its benchmark。

 this multiplicative benchmark， like even know even when the best fixed price sells to only two bidders。

You we showed that you get at least a quarter of the optimal revenue and expectation when you run the random sampling auction。

Whereas here， it's like an additive guarantee。Okay。

 so it might be that right opt like if we sell to only one bidder opt could be you know as small as one right like if we sell to K bidders right remember we've scaled things so the values are at most one。

 if we sell to K bidders opt is going to be less than k so if we sell to fewer than like root n log n bidders then this is like definitely worse than the random sampling option it's not it's not promising us any revenue necessarily。

On the other hand， this could be a lot better than a for approximation if opt。Grows linearly。

 for example， if we expect the amount of money we make to scale linearly with the number of people we can get to walk into our store。

 then。This term will quickly become sort of low order right because if optt is growing linearly within and our regret term is growing only with the square root of n。

 then when we look at a multiplicative approximation， what fraction of optt are we obtaining。

 we will see that as n gets bigger and bigger， we're getting closer and closer to a one approximation。

And。It's sort of natural to expect that opt should grow within n。Right， like you sort of expect that。

You know， the number of sales you make should be somehow proportional to the number of people you get to walk into your store to consider making to consider a purchase decision。

And so like in particular。If。We're in a setting， like maybe a。You know， like。

We have this guarantee no matter what， even if the values are chosen adversarally。

But suppose we're suppose we are in a distributional setting in the end。

 suppose the values actually are drawn according to some process， so it makes sense to talk about。

 you know the expected value of opt as a function of n。And this is saying like if Opta grows。

Even like really slowly， like somehow sublinely within only as large as you know， like root n loggan。

 it's even hard to imagine how it would grow so slowly because people would have to become like less likely to buy the more there were of them。

 but right even if it grows， you know， pretty slowly， sublinely within。

So long as it's not slower than root and log n。This will be better than like the multiplicative bound we prove for the random sampling auction because it'll converge to like a perfect revenue approximation。

 not a four approximation。Right so like if the bidders have their values drawn IID from some distribution。

 this just means that know the probability that some bidder has value bigger than log n over root n should be like a constant。

And so like。That's true for any fixed distribution if you think of the number of bidders as something you can choose independently of the distribution right like if you show me a distribution and then I get to sample n bidders from it as n grows large like opt will definitely grow linearly within n。

Okay， so in this is sort of saying in a quite general setting in particular the setting where there is a prior distribution on values。

 we just don't know what it is， this will very quickly converge to getting like a one approximation a perfect approximation to the optimal revenue。

Questions。All right， I'll see you guys next time。

![](img/e2a20e289edb3ab985de71418692b32b_3.png)