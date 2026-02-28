# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p20 NETS 4120_ Algorithmic Game Theory, Lecture 20.zh_en -BV15kLRzTExU_p20-

All right。

![](img/b923a4c8746afc0ed37fac0303a13d0d_1.png)

It's nice outside today。So let's keep thinking about how to make money。

So to sort of recap what we've learned so far。we studied this sort of optimal auction design and at least in the setting of a single item auction。

 we were able to you know like analytically derive the form of exactly the revenue maximizing auction。

And then last class， we sort of said， okay， well， maybe auctions are。

Kind of hard to run like actually we don't buy a lot of the things that we use in our everyday lives at auctions like we buy them。

You know， basically at posted prices。And we realized， okay， well。

If we're willing to give up on exact optimality and settle for maybe a factor of two。

 then actually we can approximate the revenue of the optimal auction just with sort of simple posted pricing。

But both of these schemes， you know， both the optimal auction and sort of the optimal。

Revenue maximizing pricing scheme。Worked in this sort of。

The evasion framework where basically we assumed that you knew a distribution from which the buyer evaluations would draw。

Right like these distributions were sort of key objects。

 they defined these like virtual value functions in order to actually figure out what specifically is the revenue maximizing auction what specifically are the prices you should charge people you had to be able to sort of compute these virtual value functions and in particular invert them and these were defined in terms of these distributions over people's valuations and sort of you know like。

In some sense easier said than done right like you can like write these distribution you can define a model that has these distributions and its makes it convenient to derive things。

 but like when push comes to shove and you need to like deploy a revenue maximizing auction like where does this distribution come from。

Yeah。And again， like。This has put our discussion of revenue on a very different footing than our discussion of welfare。

 right run the VCG mechanism， which again optimized welfare in a very broad setting。

We didn't need to have any distributional knowledge we just like。You know， wrote down the setting。

 the VG mechanism corresponded to some allocation rule and some pricing rule。

 and it would always give you exactly the。Weallfare optimal allocation and be dominant strategy truthful。

 and we didn't need to assume that we knew anything about the instance。And so。

What I want to do this class is to think whether we can get any sort of analogs of that for revenue。

Is there some way for us to think about revenue？In like a distribution independent way。

 like I'd like to describe。An algorithm mechanism， just like everything we've been doing。

 it should always be dominant strategy truthful even in the worst case。

 but I should be able to state some kind of revenue guarantee in the same kind of generality that I can state a welfare guarantee for the VCG mechanism right like I should state a revenue guarantee that doesn't depend on。

The valuation is being drawn from some distribution， like the VCG mechanism。

 it should be something I can state in the worst case over valuation。Okay， and。

You know just just we've been doing for quite a while， you know。

 this is a very general topic right like for any mechanism design problem you can ask for you know what is called like a prior free revenue maximizing scheme we're not going to like。

We're not going to sort of cover the fully general case， unlike for the VCG mechanism。

 there's not like simple characterizations， people sort of study this on a case by case basis。

 what we're going to do today is we're going to go through a case study。

 something called digital goods options。But before。

We go and do that are there sort of questions about the general？Pmise， the thing we're trying to do。

Okay， we'd like to be able to say something about revenue。

 but in the worst case without needing to make。Des of average case assumptions we've been making。

 assuming that people's evaluations are drawn from some nice distribution。Is the idea clear？Okay。

So what's this case study we're going to be thinking about？

calllled the digital goods auction setting and you can sort of similar maybe another reasonable name for this would be unlimited supply auctions。

 so sort of the other end of the spectrum from single item auctions。The idea here is you're selling。

 something like software or movie rentals or something for which。You know。

 there might have been some big like fixed cost of production， right， like to produce。

Office you know， 2020 or whatever they're up to now like probably you know many。

 many thousands of software engineering hours went into that and it was expensive， but like。

Once it's produced for you to get a copy， there's basically no marginal cost We're just copying bits。

 Similarlyly， if you want to rent a movie on Netflix， you know， streaming to your device， know。

 of course， the movie was expensive to make。 you had to pay the actors。

 you you had to pay for the special effects。 But like once it's made。

 the marginal cost for you to watch it is is zero。 It's just copying bits。Okay。

 so that's the idea of digital goods auctions that。

The thing we're selling has no marginal cost of production。

 so unlike a single item auction for example， where there's this hard supply constraint in a digital goods auction there's no hard supply constraint like in principle everyone could win the item。

So in particular。Like just putting this into the kind of single parameter domain setting we've been thinking about。

A digital goods auction is just an auction， it a single parameter domain where the set of alternatives is all possible subsets of the bidders。

 any possible subset of the bidders could be deemed a winner and could rent。

Whatever movie we're selling or download whatever software we're selling because there's no supply constraints。

And。Well think of it as a single parameter domain where basically you have some unknown value for winning the item you've got some value。

You know， let's say VI and if you bitter I win the item， then your value， your utility will be。VI。

 and otherwise it'll be zero。Okay so it's a single parameter domain we know that you prefer to win then to not win the only thing we don't know is your value for winning and any subset of the bidders can win because。

You once we've made the movie， there's no cost to streaming it to one more person。Okay。

 does the setting make sense？So it's sort of the other it's a simple auction and among simple auctions。

 it's kind of the other end of the spectrum from a single item auction。

 a single item auction sort of has the tightest possible supply constraint。

 there's only one item an unlimited supply auction is the other end that there's you know。

 in principle more than an item any everyone could win if we wanted to make it so。And in some sense。

Digital goods auction are a good case study when studying revenue because。

When there's no supply constraint， that's sort of the setting where revenue and welfare are most at odds with one another。

Like what's the welfare maximizing outcome in a digital goods auction？Yeah。Give it to everybody。

 right， like。Assuming nobody's life is made worse by getting a copy of Microsoft Word or whatever。

 know free disposal， you can always delete it， then like if I want to maximize welfare I should like give it to everybody and that's what the VCG mechanism will do。

Okay， so the VCG mechanism run in the digital goods auction setting。

 well it'll give it to everybody and if it's committing to give it to everybody， you know。

 and it's also going to be a dominant strategy truthful mechanism，😊，That's individually rational。

The only possible pricing rule is that it charges everybody nothing。Right。

 because if I'm going to charge you more than nothing but。Also， will be individually rational。

 I promise not to charge you more than you report Then the amount you pay would have to be a function of your report and。

Then it couldn't possibly be dominant strategy truthful Okay， so for a digital goods auction。U。

The welfare maximizing allocation， if you want to implement that truthfully。

 gets exactly zero revenue。Okay， so so this is sort of a setting where revenue and welfare are maximally in conflict with one another。

You know， somehow， if we're going to get revenue， we're going to have to think about artificially limiting supply。

Okay， does that make sense？Okay， but。If you sort of remember。

The tricky thing when thinking about revenue is there's not an obvious benchmark。

 what should we compare ourselves to you know when we want to say you know we are optimal or at least we're doing well。

 you know， compared to what。Right。For welfare maximization。

 there's a clear benchmark we could choose the welfare maximizing outcome in some sense for revenue。

 there's no obvious upper bound I could just keep charging people more and more and more money。And。

For lots of ways of doing that， I wouldn't get a truthful auction and this was sort of the problem that we ran into before when talking about revenue that we sort of solved for the time being by thinking about this prior distribution on values。

In which case it made sense to talk about。Optimmal auctions measuring their revenue and expectation over those distributions。

 Now we want to。Figure out a way to think about this without talking about a prior distribution。Okay。

 so when we had a prior distribution， you know， we had this sensible way to talk about the expected revenue of an auction。

 we could think about the set of all dominant strategy truthful mechanisms and we could talk about the mechanism that had the largest revenue in expectation over the distribution。

We can't do that anymore， but maybe we can at least。

Use what we learned there as intuition to think about what might be a reasonable definition for a benchmark。

So maybe for a moment。Let's think about。What the revenue optimal auction in this case would be。

If we did know a prior distribution。Well， it's a single parameter domain。Our derivation from。

You know， a few weeks ago still holds。And。If you think about it。

You know an unlimited supply auction is kind of the same thing as a single bid auction like it's decoupled like whether I sell to Alice is independent of whether I sell to Bob so it's really just the problem of sort of thinking about what is the you know best dominant strategy truthful mechanism for selling to a single person。

Which we sort of derived last time or you a few weeks ago。Really。

 the only thing you can do when selling to a single person is to set a fixed price and。In fact。

 we know like what the fixed price should be， the optimal mechanism would take。

 you know Alice's or know if everyone was drawn from the same distribution the common virtual value function would take the inverse of that function evaluated at zero right the the value know the value that causes the virtual value to。

Sft sign from negative to positive， and it would set that as the price。Okay， so。

If if there was a prior， we just didn't know it， like if we sort of imagined that if we knew this thing。

 you， and were able to derive the revenue optimal auction， it would turn out to be a fixed price。

And so。Knowing that。We might now。Think， well， okay， you know。

One thing we could talk about trying to do， even without knowing this prior distribution is。

Trying to。Proruve of a theorem that says the amount of revenue that we make。

Is comparable to the amount of revenue we would have made using the best fixed price in hindsight if only we knew what all of the bids were。

 then in hindsight， there would have been some price that was like the revenue maximizing fixed price。

 Now， of course， we're we can't set the price as a function of the bids。

 But like if we could do something。That with competitive with the best fixed price， you know。

 the revenue with the best fixed price in hindsight， then first of all。

 we'd have a statement that made sense even without assuming a distribution。And additionally。

 if there was a distribution out there， we just didn't know it。

 we would like simultaneously be competitive with the revenue optimal auction， even you know。

 if we had known that distribution。Okay， does that make sense？

Like we sort of figured out that in this setting， the revenue optimal auction actually kind of just looks like a fixed pricing and。

And。So if we can compete with the benchmark of the revenue of the best fixed price in hindsight。

 which is something we can define without a distribution well then we're then we're competitive with sort of。

The best we could have done， even if we had this distributional knowledge that we don't。Okay。

 so does that make sense so yeah we still we still have a couple more thoughts to think about。

How to define a reasonable benchmark， but these are the。You know， main thoughts。ok。

So let's think about fixed price benchmarks， what those mean。So first of all。

 just to sort of note something we've noted before and that we'll note again。

If I set a fixed price of P。And who's going to buy the item？Well。

 everybody whose value is bigger than P， bigger than or equal to P。

And how much money am I going to make？Well， I'll make P dollars for everyone who buys the item。

So the total amount of money I'm going to make is exactly P the price I sex。

Times the number of people who were willing to buy that item at price P。

 which is just the number of people whose value for the item is bigger than P。Okay。

 so P times the number of people whose value for the item is bigger than P is an expression for the revenue I get at a fixed pricing。

So here's a claim that I want you to explain to me。So suppose in hindsight。

 I realized that the n bidders have values V1 through VN。Okay。I claim that like in hindsight。

 you know， if I pick the price to maximize this expression， the price that maximizes revenue。

 given the actual realization of the bidders。It's got to be that the revenue maximizing price is exactly equal to one of the bid valuations。

 like it's going to be either V1 or V2 or V3， you know， dot dot dot or VN。Okay， it can't be。

Anything other than that。Anyone。Convince us that that's the case， yeah。可以。Yeah。

So like let's let's think about this this revenue function at the price。

 it's sort of a step function， it's like a piece wise linear function， right because。Yeah。

What happens when I raise the price， well， everyone who's willing to buy the item all of a sudden pays more。

But occasionally as I raise the price， someone becomes unwilling to buy the item and so I sell to fewer people。

But where does that happen， well， that only happens when the price crosses a threshold of someone's value。

RightSo if I'm using a price that's strictly between， say V1 and V2。Then。

If I increase my price by epsilon， but I haven't yet gotten to V2。Then。

All of a sudden everybody will be paying me。Epsilon more dollars and because I haven't crossed the threshold of any lens valuation function。

Nobody has decided that it's no longer worth their while to buy the item。Okay。

 so I should so the thing I started with therefore couldn't have been the optimal price。

The only time I can't make this argument is if。The price that I am currently considering using is equal to someone's valuation function。

 then it might be that raising the price by epsilon is not a good idea because they and perhaps others might all of a sudden stop buying the item。

Okay， so the best fixed price in hindsight must be， you know， once I learn what the values are。

 there's only n choices for what it could be， it's got to be exactly one of the n values。

Does that make sense， is that clear？Okay。And so that means。You know。

 the revenue of the best fixed price in hindsight， which I'll write as opt to V and we have an expression for。

You know， if I sort the valuations。From let's say， highest to lowest。

 where V1 is the highest valuation， V2 is the second highest and so forth。

The revenue of the best fixed price in hindsight is always going to be。The maximum over。

The index I of the buyers。Of I times V。I can tell it。At the price of， yeah。

 I can sell it at the valuation of the highest valuation buyer。V1。

 in which case I will sell exactly one item。Or I can sell it at the valuation of the second highest valuation buyer。

 in which case I will sell exactly two items， or I can sell it at the valuation of the third highest valuation buyer in which case I will sell it only three items。

So I can write。With this observation in hand， I can write the benchmark that we're talking about。

As the revenue of the best fixed price in hindsight as just the maximum over I。

 where I is indexing like the I highest valuation。Of I times the I highest valuation。

 because if I if I price at the I highest valuation， I sell it to exactly the top i buyers。

 so I make eye sales。Does that make sense？Okay。So we have sort of a reasonably simple description of the benchmark。

But we sort of run into the same。Problem that we sort of discussed a little bit last time。

 which is that。Although it would be great to be able to compete with this benchmark。

And it's sort of a problem like like this is a little bit too much to ask for that we compete with this with a truthful mechanism。

Because it seems hard to compete with the case in which。

All of the revenue in the with the optimal pricing is actually sort of extracted from only one bidder。

 like the case of I equals one。Seems tricky。That corresponds to the optimal revenue arising from setting the price at the value of the highest bidder。

 selling only to him。B just to sort of。Think about why， you know。

 like maybe you can build some intuition by thinking of the case when actually there is only one bidder。

In which case。The best。Price in hindsight is to sell the good at the valuation of the one bidder。

Okay， but like。There's clearly no way to。Compete with that in a truthful way。

You know a truthful mechanism has to set the price independently of the bids I can't ask you what your value is and then turn around and say that's the price that's not going to be a truthful mechanism and so if there's only one bidder like I might not even know like the scale of the valuation I might not know like the order of magnitude of the right pricing and so I you know whatever price I said at you know I could be orders of magnitude off and just you know like not be able to compete with this benchmark。

Okay， so like and simply adding more bidders doesn't help。Because it might be that。

Really like only the high bidder matters like maybe i'm selling this dongle and I think there there's like someone in this class who is like a crazy person they value this at like $100 million。

 but like you know and the fact that there's more people in the class doesn't help me extract。

The revenue of the best fixed price， which is something like $100 million because everyone else sensibly values the set like 10 cents。

Okay， so like the problem is not just that there's only like one bidder。

 the problem is that the revenue of the best fixed price might be getting all of its revenue from just one person。

 potentially that's the problem。And so。Yeah， who knows like maybe。

it seems like this case of I equals one when the revenue is extracted from like the single person with the highest value。

 that is troublesome。Now， maybe if we think more about this， we'll realize， you know。

 it's hard to compute。 maybe the case of I equals 2 is also a problem。

 maybe I equals 3 is also a problem。 but like let's。

Let's cross that bridge when we come to it and try to like。

Weaken this benchmark with the sort of weakest possible bandaid that will overcome the problem we've just realized。

Okay， so let's just say， okay， you know？Forget about selling to only one person。

 Let's just try to compete with。The following slightly weaker benchmark。

 which is just the revenue of the best fixed price that sells to at least two people。Okay。

 so it's just the same as before， it's just the maximum over， you know。

 the index I of the I highest bidder。times。V of I， the value of the i pi bidder times I right that's still the revenue you get with the best fixed price that sells to at least i bidders。

But now like we'll just restrict this benchmark to take the maximum for I greater than or equal to two we'll just ignore the revenue that like we'll ignore the possibility that you might sell to only one better and we'll just consider the revenue of the best fixed price that sells to at least two people。

Right， so so like in a。In a realistic setting， like in a digital goods kind of setting where you have unlimited supply。

You should think of this as。Basically the same benchmark right like you're figuring out how you should price your like Netflix downloads。

 your Netflix streaming， you know， subscription price， you know， to make the most money。Probably。

The best fixed pricing will sell to a lot of people。Like it's possible that in fact。

 the best fixed pricing is to set the Netflix subscription to， you know。

$10 billion a month because maybe。You know， in principle。

 someone might have been willing to pay that and selling to one person at that rate might have been better than selling to。

 you know，100 million people at 7 a month， but like probably not。Okay， so， you know。

 if we're really thinking， remember we're thinking about the digital good setting。

 the whole point is there's zero marginal cost of production we're hoping to sell or at least we have the capacity to sell a lot of items。

嗯。😊，You know， realistically， in that case， this is the same benchmark。

 like you sort of expect that the maximum is going to be realized at some big number。

 you're going to try to sell a lot of copies， not at a small number。ok。Is that clear？

We've sort of weakened like。We're trying to compete with the best fixed price。In hindsight。

 there was this problem in principle with the best fixed price in hindsight that it might have sold only one person and seemed like we couldn't compete there。

 we've just sort of。You know， removed that bed case and we're trying to compete with what's left。

Okay。So how should we do it？So like maybe the first thing you would think of is you're like。

 okay like。I'll just like elicit the bids， everyone will tell me what their value is。

And then I'll just compute this number， right like it's not hard to compute this once I have the bids。

 I'll just compute the best fixed price in hindsight。It's going to be equal to the bid。

Of bitter eye for some eye。And I'll charge that。嗯。But the problem is。

It's not a truthful mechanism for sort of if you think about it， obvious reasons。

Because if I compute。The best fixed price in hindsight。It is exactly equal to the bid of some person。

The best fixed price in hindsight is equal to the I highest bid for some I。And therefore。

 that person has some flexibility to lower the price， right if they。Lower their bids。

 they'll have to pay less。And so it's not a truthful mechanism and in general。If you think about it。

 you sort of realized that。If a mechanism is going to be truthful。It must be that for every bidder。

 the amount of money they are asked to pay is independent of their bid。

If there's any bidder who has two different bids they can make that both cause them to win。

 but cause them to win at different prices， and they will report the bid that causes them to win at the lower price。

 whatever their true value is。So if we want to come up with a mechanism that actually is dominant strategy truthful。

 we need to figure out what to charge each person I in a way that does not depend on their own bid。

And this doesn't be that if we just like look at all of the bids and compute the best fixed price。

Well， it definitely depends on their bids。Is that clear？So somehow。

 like it should also maybe like build some intuition for how we should try to do this like。Yeah。

 somehow we need to compute。Like we need to compete with the revenue of the best fixed price。

 which is something that， of course， depends on this vector of bids that we get。

But we need to do it in such a way so that the amount of money we actually end up charging each person。

Does not depend on their bid。At all。😡，That's the puzzle we need to solve。

So maybe here's like a attempt number two after you hear that。You know， and we have the freedom to。

Offer different prices to different people potentially。Some of you think， okay， you know like。

The problem with attempt one was I just sort of naively tried to compute the best。Fixed price。

 the revenue maximizing fixed price and charge that to everybody， but of course。

 that depended on everyone's valuations。Now I need to charge bitter I at price that doesn't depend on bitter eye valuation。

 well why don't I do this， why don't I say look？For each bit I。

 what I'm going to do is I'm going to consider the n minus1 bidders other than them。

I will figure out what is the revenue maximizing price on everybody else。

 what's the best fixed price on those n minus1 other bidders other than bitter eye。

And I'll charge that to bitter eye。So this is a truthful mechanism because now every bidder is actually just facing like a take it or leave it price that is independent of their own bid right like the price you face is the function of everyone else。

So you you want to buy the good， if your value is above the price， you can't affect the price。

 it is a truthful auction。Okay。But you know， like how well does it do with respect to the benchmark we want to compete against？

And。It doesn't do great。So here's maybe like an example to sort of understand the kind of thing that can go wrong。

S like we've got 100 bidders out there。ok。😊，And what？You know。

 what the world looks like is that most of them have a low value。

 let's say 90 of the bidders have a low value， they value this item at $1。

And 10 of them are high value bidders， 10 of them have a high value， they value this item at $10。ok。

So here， the optimal revenue obtainable by a fixed price is $100。And I can obtain it in two ways。

I could set the price at $1。In which case I sell it to all hundred of the bidders。

 they're all willing to buy the item at $1 Okay so I could make $100 by selling a $1 item to 100 people。

But there's another way to obtain the optimal revenue， which is to price the item at $10。

I could also make $100 by selling a $10 item to 10 people。The $10 price， the 10 hyp。

Value bidders would be willing to buy it and they would each pay $10。

 that's another way I could get $100。Okay， so there's two optimal prices， $1 and $100。

But now if we sort of use this scheme。Of。For each bitter eye figuring out what is the optimal price to charge them by looking only at the n minus one other buyers。

We've got a problem。So let's look at what we charge the low value buyers。Okay， so so we。

Are deciding what to charge a low value buyer， someone whose value for the item is one。Well。

 if we exclude them when computing the price， what we see is that among everyone else。

 there's 89 remaining low value buyers。And there's still 10 remaining high value buyers。

So on this instance of 99 buyers excluding one of the low value buyers。

 there's now a unique optimal price and it's to charge $10 or if I charge $10， I still make $100。

 there's 10 high value bidders willing to pay $10。If I charge $1 on the $99 remaining bidders。

 I only make $99， so $10 is the optimal price to charge on this remaining instance。

 and so I decide to charge I decide to offer a price of $10 to each of the low value bidders and they don't buy it。

What do I do for the high value bidders？Well， for the high value bidders。First。

 I exclude them and I look at the remaining market。And in the remaining market。

 there's only nine other high value bidders， and there's 90 low value bidders。

So I could charge $1 and make $99 in total。Sell to all 99 of the bidders。This $1 item。

Or I could charge $10 in which case I would sell to the nine remaining high bidderters and only make $90。

And so for the high bidders， again， when I look at everyone else other than the excluded high bidder。

I find that there's a unique optimal price， it's $1。And so so when I do this。

 I charge everyone exactly the wrong price， I charge the low value bidders $10 and I don't make the sale。

And I charge the high value bidders $1， and I sell it to them， but。

I could have made 10 times as much money。And so this mechanism we just described。

 although it's truthful on this instance， it only makes $10。

 it sells to the 10 high value bidders at a price of $1。

 it fails to sell any of the low value bidders and so we're a factor of 10 away from optimum and there's nothing special about 10。

 you could have rewritten this instance， so we were a factor of 100 away from optimum or a factor of 1000 or a million。

Okay， so like。This maneuver where we compute the best fixed price in hindsight。On everyone。

 except the bidder we're using the price for。Like it just doesn't work to compete with this revenue benchmark。

Okay， but like let's remember， there was a good reason we considered this maneuver。

 which was that we need to find a way to come up with a price for each bitter eye that doesn't depend on their own bid。

ok。So we need to do something， yeah。It wasn't。呢在真睇四个代表。Nine times 10 is the same as 90。

But what is one times 99？二喂。It's the famous 99。Right， so， yeah， so so the point is like。

On the whole market， there's like a tie， like there's two revenue maximizing prices like one and 10。

 but on each of these like residual markets， when I remove one person， there's no longer a tie。

 there's a unique optimal price and it's exactly the wrong price。That makes sense。Okay。

 does this sort of example make sense and does the general challenge like like the general problem we need to solve make sense。

 we need to figure out a way to compete with the best fixed price in hindsight。

Which is a quantity that depends on the bids， like what the best fixed price is。

 depends on what the bids are， of course， but the price we charge to each agent is not allowed to depend in any way on their own bid。

And doing this sort of maybe the first thing that comes to mind just。

Removing agent I from the calculation of。Agent I is price that doesn't work。

 I mean it works for truthfulness， but it doesn't work for revenue。Does this make sense？O。

So let's sort of build up to this。Let's start with an intermediate goal and try to develop， you know。

 like maybe a useful mechanism design subroutine that'll be， a useful tool for us。Suppose I told you。

A profit target， so as I said， look。I'm your manager or something， I say， look。嗯。😊。

If we don't make R dollars。We're going to go out of business， in which case you're fired。And。

You're a salaried employee， so you don't know you don't want to be fired， but like。

You also are not going to， yeah。But like your job is， you've been told to make at least R dollars。

 if you make $100 r dollars， you know， you've seen none of that benefit。Okay， so suppose。

I've given you a profit target。And your goal is to meet that profit target if possible。

But you don't necessarily need to exceed it。Okay， so we want a mechanism that given a profit target R defined independently of what the bids are。

U。Will be truthful？And we'll obtain profit R。If it's possible to do so。

 if there is some fixed price that sells to at least two people that makes R dollars okay。

 so you want to want to come up with a mechanism that will make our dollars if our benchmark value is at least our。

Okay and that's like our only goal， so first of all we don't we're not worried about making more than our dollars and somehow right like we're satisfied with like crossing this threshold that is like defined independently of what the bids are。

Okay， and if it's not possible to make at least our dollars we have no revenue goals we're okay like you know we're。

Okay， like making zero dollars in that case， like if we make R minus1。

 the company is going out of business anyway。嗯。Okay， so it's the。

Is this sort of small limited problem， does it make sense like yeah？No。

So we're trying to compete with this benchmark eventually。And。What we're saying here is， look。

 if the benchmark， like in the event that it is possible to make R dollars with a fixed price。

 like if the benchmark value is bigger than R。Than I will expect。

The benchmark is the revenue of the best fixed price， so if it's possible to make r dollars。

 then I would like you to make r dollars and of course you know like if I。

 it doesn't make sense to say you have to make R dollars no matter what。

 if I say you have to sell this for like $100 trillion dollars then。You know。

 you have to allow for the fact that you might not be able to。

Right so if the you know if it's not possible to sell to make R dollars with a fixed price。

 then then I expect nothing of you， but I want to guarantee that if the benchmark value is bigger than R。

 then you make R dollars and I don't necessarily need you to compete with the benchmark value。

 it might be the benchmark value is like a trillion R。

 you still need only to come back with R dollars that makes sense。Okay。

So let's call an object that does this a profit extractor， given a target R。Okay。

 its goal is to like truthfully extract profit R from the set of bidders if。

Doing so is possible if if there is a fixed price that extracts that gets R dollars in revenue。

 and we'd like to do it with a mechanism that is dominant strategy truthful。Okay。

 and so here's a particular thing that I'll call a digital goods profit extractor。

That I claim has this property。And it's got a target or it's given a target profit level R。

 so the algorithm I'm defining is given this profit target that is again。

 defined independently of the instance。So it's not trying to compete。

 it's doing something weaker than trying to compete with。This benchmark。

 this benchmark is defined as a function of the instance here you're just trying to compete with this like bid independent profit target R。

Okay， and here's what it's going to do。It's going to elicit the bids。Okay。

 maybe think about them again as sorted from largest to smallest to V1 is the largest bid。

 V2 is the second largest bid， so on。And it's going to find the largest value k。

Such that the top K bidders have all bid more than R over K。If any such K exists。

And it'll sell to those top K bidders at a price of R over K。 Okay， so。

 so we'll find the largest K such that。There are K bidders who have bid more than R over K dollars and it'll sell to those top K bidders at the price of R over K。

 people who are not in the top K do not win the item and pay nothing。And。If there is no such K。

 it sells to nobody。Okay， the mechanism makes sense？Okay。Okay。

So the claim is that this mechanism is dominant strategy truthful。

 you have no incentive to misreport your value to a profit extractor。Yeah。And let's think about why。

Okay， so the。You know， the mechanism as defined is you know， it's not dynamic it it's like， you know。

 you submit your bids and you just find out like did you win or lose and what it's actually doing is it's。

 you know， finding the， you know， just the largest K such that there are K bidders whose values at least are over K。

But let's think about it as if it were a dynamic mechanism。

 let's think about the process of actually finding the largest k such that there are K bidders that each bit are over k。

And the process I want to think about is。Starting with k equals n。

 everybody checking if the top n bidders bid at least r over n， if the answer is yes。

 then like K equals n must have been the largest k， such that that was true。And if the answer is no。

 like shrinking K by one， say K is now n -1。 I'll check if the。

Top n minus1 bidders bid at least r over n minus1 if yes。

 that must have been the largest k otherwise Okay so I'm just going to check if each k satisfies this property that the top K bidders bid at least are over k。

 starting with the biggest K， starting with k equals n and。While the condition is not met。

 iteratively like shrinking k by1。Right， so this is just a procedure for finding the largest K such that the top K bidders are are。

Have bid at least our over k okay so so that's what the algorithm is doing so let's just think about running that procedure。

Okay， so our first like hypothesis is that maybe the top n bidders bid。

 maybe everyone bid at least r over n in which case k equals n is the largest such k。

And so I'll think about that as like offering to everybody to all end bidders。

 the opportunity to buy the item at a price of R over N。Okay。

 if all n bidders have value greater than R over N， they should all say yes。On the other hand。

 if any one of them has bids less than R over N。I'll think of them as rejecting that offer。

I to say no， I don't want to buy it that's are over end dollars。At which point I've learned like。

K was not equal to n， like there are not n bidders who have value bigger than R over n。

And so what I'll do is I'll say， okay。😊，You know， like the bidders that rejected this offer。

They're removed from the auction they can't win in the future。And I'm going to。Reduce K by one。s say。

 okay， now yeah， we're going to try this again。 we're going to。

Offer everyone who remains all of the n minus one bit or。Yeah， we'll offer everyone who remains。

A price， a fixed price of r over n minus1。Okay， now maybe everyone accepts the offer。

 in which case it must be that。K equal to n minus1 was the largest such k。

 such that there were k bidders that each bit at least are over n minus1。Or maybe not。

 maybe you know， maybe among the n minus one highest bidders。

 there's someone who doesn't value the item that much。

 they want to reject the offer in which case I say， okay， you know。See you later。

 you're expelled from the auction， yeah。不是。这。对这。That ist the only one that。标准。嗯。You know。

 if there's you're sort of imagining like there might be like 10 people who are tied for the lowest bid basically。

嗯。Yeah， in which case， sort of， you know， maybe。Nothing interesting will happen for 10 iterations but。

嗯。It's not a problem。I guess。Yeah， like maybe。The way I've written it。

 I am sort of implicitly assuming that there's no ties， so I guess really if， you know， yeah。

 maybe like if three people reject the offer， then you should write， you know K equals k minus3。

So maybe this is written under the presumption that there's no ties。Okay。But is this clear。

 so basically。😊，At any given moment。We're offering everyone a price of。A over k for some K。

If there's if there are people who are unwilling to。

Pay that price because their value is below that price， we show them the door。

 and among the remaining bidders we offer them now a higher price R over k minus1。Okay。Yeah。

 is there any we the highest value was that like the first。

The highest value of k I think is important for this to be truthful。Yeah， I guess。还两。But。可意。Okay10。

Send到00% want be。That's right， yeah， so if you use the largest value of k。Or sorry。

 if he's the smallest value of k， there would be incentive for people to under report。Yeah。Okay。

Anyways， we continue this process where if anyone rejects the offer。

 we remove them from the auction forever and then raise the offer right the offer between rounds always goes from R over k to R over k minus1 which is a bigger number。

 so the price is rising as this is going。Okay， and we stop as soon as we get to some K so that the K bidders all accept the offer。

 the K remaining bidders all accept the offer。Okay。

At which point they all get the good and pay the offer price that they all accepted。

This is just a different description of the same mechanism。

 this is a way to find the largest k such that there are K bidders who each have value at least are over k。

So let's just note like some properties of the mechanism as described in this way。So first of all。

 if you reject the offer。It's not like you can win in some future round like if you reject the offer。

 you're like。You know， eliminated from all future roundms。And so in particular。

It's a dominated strategy to reject any offer that is below your value。Because。

By not rejecting the offer。You're not committing yourself to anything。

 you can always reject future offers。And by rejecting the offer。

 you're sort of removing the possibility that you might be able to get the item in the future at some price that you would have been willing to pay。

So you don't want to reject offers that。That you would have been willing to pay because as soon as you reject an offer。

 that's it for you， you're gone。Similarly， like。There's no reason to accept an offer。

If the price is above what you would have been willing to pay， because the price is only rising。

Right，The price is going up。So if you're not willing to pay today's offer。

 you're even less willing to pay tomorrow's offer。 so there's no reason to stay in the auction longer than。

You know， your true value would suggest this is， by the way。

 the difference between picking the maximum value of k versus the minimum value of k picking the minimum value of k would sort of correspond to doing this process in the other direction first offering。

诶。The you know， the first bidder， the opportunity to buy the item at their value。

 then if they reject offering the first two bidders。

 the ability the opportunity to buy the item at like their value over two in that in that direction the price would have been going down and there would be reason to stay in the auction and try to。

You know， drive the price down。In this direction， the price is only going up。ok。

So it's a dominated strategy to reject bids lower than your value。

 it's a dominated strategy to accept bids higher than your value。

 so in fact it's a dominant strategy for every bidder to report their true value。Okay。

So we have this mechanism and。It's dominant strategy truthful。

Is it in fact a revenue extractor does it？Obtain this sort of revenue target we set out for it。

 Remember what we want is that if it is possible to obtain revenue R。With a fixed price。

 if our benchmark value is bigger than our， then our profit extractor should actually do that。

And otherwise that you know， it's allowed to obtain revenue zero。And I claim that it is。

So remember what our benchmark is or the benchmark of the best fixed price。Well。

 the best fixed price in hindsight。Always corresponds to charging a price equal to one of the reported bids of the bidders。

Right， and so it's like。For some index k， it's equal to for some index k。

 the best fixed price is the K highest bid。In which case the optimal revenue is k times the value of the K highest bid。

 right it's obtained by selling k copies of the item to the top K buyers。

And so like just like by definition， like dividing if our revenue benchmark。Is at least R？Well。

 that means there's some k such that k times the k highest bid is at least R。

And so like dividing the K highest bid must be at least R over K。For some k。And so。

Like that means there is some K。Such that the K high esttrs are willing to pay are over K。

Which means that the revenue extractor will succeed at finding some such K。

 it might find a larger K than this， but it'll find some such K。It'll find some K prime such that。

The top K prime bidders are willing to pay over K prime dollars。

 We know there is some such K prime because。The revenue benchmark itself must witness。

Some K with that property。And so it succeeds and you whenever it succeeds， it gets revenue exactly R。

 right， it always sells to K people at a price of R over K， and so it gets revenue R。Okay， so。

The revenue extractor succeeds in selling to some number of people k at a price of R over k。

Exactly when。The benchmark value we're trying to compete with is at least a R。Yeah。Why is that。单位。

So that's the benchmark class we're trying to compete with， the revenue of the best fixed price。

And the reason we're trying to compete with that is we sort of noticed that the Bay's optimal auction。

 like if we knew the distribution from which people were drawn would have the form of just setting like an optimal price。

Does that make sense？Yeah。这个。てられ。系个你。Oh this this would work for the k equals one case yeah the thing that's going to break for k equals one has yet to come yes so I'm I'm writing opt to greater than equal to two just because you know that's what we're threading through this lecture to eventually compete with。

 but you're right so that we haven't needed that yet like this this step who works even for the original opt to benchmark。

Good question。Other questions？Okay， and just to sort of like observe that。

This does what it says in the other direction as well。

It might be that the revenue of the best fixed price is actually smaller than our。Okay。

 in which case we don't， you know， we didn't。Ask of our mechanism that it make any money at all。

 and in fact， in that case it doesn't make any money at all。

Right if the revenue of our optimal benchmark is less than R， that means for every k， well。

 the possibility of selling to the top K people at a price of the K highest bid doesn't make at least r dollars。

 which means that for all k， the value of the K highest bid。Must be smaller than our overK。

And so the mechanism won't find any such k， such that the top K bidders are willing to pay are over K。

 and so it'll fail and it'll halt without selling to anybody。Okay， so this mechanism。

Gets revenue R exactly when it is possible to get revenue R with any fixed price and doesn't get revenue R otherwise。

 doesn't get any revenue otherwise。Okay。So we've got this useful tool doesn't solve our original problem because。

You know， like。Where does R come from？But maybe we can use it。

So the thing we can do now with this tool is。If somehow。Someone whispered into our ear。

A revenue target R that we knew was feasible。That we knew was obtainable with a fixed price。

Then we could use this mechanism to obtain that revenue R。And if moreover。

 someone whispered into our ear， a revenue target R that was not only feasible。

 but was competitive with the best fixed price。Then。

Our revenue extractor would get us revenue competitive with the best fixed price。Okay。

 like the only problem with this plan is that it like is predicated on。Someone whispering。

This secret into our ear。So we need to。Figure out how to implement that。Okay。

 so like the main problem is that we don't know R。We don't know a good value are。

 like if we pick something too small， we'll get our dollars。

 but that won't be competitive with the best fixed price if we pick something too big we won't get any money at all。

But。You can sort of think about what we've done so far as。

Reducing this sort of revenue maximization problem to like a statistical estimation problem。

Like our goal now is to find some way。Of。Estimating。嗯。

The revenue of the best fixed price right if we can do that。

 if we have some mechanism for estimating the revenue of the best fixed price somehow in a bid independent way。

 then we can feed that into our revenue extractor and truthfully get an amount of revenue competitive with the best fixed price。

Okay， so like the thing this little object is doing for us is it is。

Reducing our problem to like a learning problem， to like a statistical estimation problem。

And of course， like the tricky part is that for truthfulness。

 like it's sort of important that R not be computed from the bids of the bidders we're running the revenue extractor on。

 it's got to be defined independently。But the trick is going to be to。

Like do some random sampling and split the bidders into two parts。

Maybe use one of the parts for estimation and the other part for revenue extraction。

So here's the idea。It's called the randomandom sampling auction。So we're going to try to estimate。

The revenue。Of the best fixed price from a random subsample of the bidders。We will use that。As。

The secret whispered into the ear of our profit extractor。

And we will run the profit extractor on the other bidders， the ones we didn't use Test。

And the hope is that， well， on the one hand， we're going to get a truthful a because the people were running。

Our profit extract you on are different from the people we use to compute R。

 so our R really is independent of their bids。But because we did this estimation from a random subs sampleample。

 hopefully we also have guarantees that。The revenue。

 our estimate for the revenue of the best fixed price is like a good estimate。That's the basic idea。

Okay does the high level idea make sense we're going to like there's this statistical quantity like we don't know the answer to what is the revenue of the best fixed price we're going to try to estimate that by taking a random subsample of the bidders we're not assuming the bidders valuations are drawn from a random distribution the randomness is coming from us we're taking a random subsample like a you know standard surveying methodology say。

From this random subsample we estimate the revenue of the best fixed price and then on everyone else we run this auction。

 and if we're right， if we get a good estimate of the revenue of the best fixed price。

 our revenue extractor will do the rest。Does the basic？Promise makes sense。O。So here's the idea。

So we're going to randomly partition。All of our bidders into two sets that I'll call S prime and S double prime。

Okay， so what I mean by this is for every bitter eye， I'm going to flip a coin。If it comes up heads。

I put them in set S prime， if it comes up tails， I put them in set S double prime。

Now I'm going to look at both of these sets and I'm going to compute the revenue of the best fixed price on that set。

So I'll look at everybody in set S prime， and I'll just like compute what is the revenue of the best fixed price。

In S prime that's easy to compute remember the revenue of the like the best fixed price is just one of the bids so if nothing else I can just you know like there's roughly n over two people in each of these sets I just try those n over two values for each of them I compute the revenue I would guess if I priced at that level and I take the max so it's very easy to compute the revenue of the best fixed price。

On set S prime， the revenue of the best fixed prices R prime， on set S double prime。

 the revenue of the best fixed prices are double prime。And now here's the trick。

I'm going to run the profit extractor on both of these sets。

But I'm going to swap my revenue estimates。So I'll run the profit extractor on set S Prime using the revenue estimate that I computed on set S double prime。

And I'm going to run the profit extractor on set S double prime using the revenue estimate I computed on set S prime。

The reason I'm swapping these things is because the profit extractor is only dominant strategy truthful if the。

Revenue target I gave it was computed independently of the bids。But in this case。

 it was the revenue target I'm giving each of the profit extractors was computed from the bids of the other set。

And it independent of the bids of the set I'm running the profit extractor on。Okay。

 does the auction make sense？Randomly splitting people into two parts on each part i'm just like looking at the bids and i'm just doing this thing that we knew。

Naiveively at the beginning， like was not going to result in a dominant strategy truthful a。

 like we're just computing the best fixed price。 It's equal to one of their values。

But then we're not charging them that bes fixed price。

 we're using that as the parameter to run the profit extractor on the other sets。

And just for good measure， we're also running the profit extractor on our estimation set using the other set。

Does makes sense。O。不是。So this mechanism is dominant strategy truthful。

 how come well like we're just running the profit extractor on two sets of people on each set of people。

 we're running it with some revenue target， which is computed independently of their bids and in that setting we already proved that the profit extractor was dominant strategy truthful。

So's a down to strategy treatmentable mechanisms。Because we're swapping。These estimates。Okay。

 how about its revenue？So I claim that the revenue of the random sapling optionuction has got to be at least the smaller of the revenue of the best fixed price on set one。

And the revenue of the best fixed price on set two。But how come？Well。

Either the revenue of the best fixed price is greater than or equal。

 either the revenue of the best fixed price on set one is greater than or equal to the revenue of the best fixed price on set two or the revenue of the best fixed price on set two is greater than or equal to the revenue of the best fixed price on set one or maybe both。

Okay， but like one of them has to be greater than or equal to the other。And whichever one it is。

 that copy of the profit extractor will succeed because it's been given。

Right like either it's been given a revenue target of R double prime。

 but the best fixed price is actually larger， in which case it'll get profit R double prime。

Or it's been given a revenue target of our prime and the。Best fixed price gets profit R double prime。

 in which case it'll get profit R prime or maybe both。So like for sure。

 since we're running both copies of the profit extractor， you know， we get。

Revenue equal to the smaller of these two。Numbers are prime or our double prime。Right。

 because the revenue extractor succeeds exactly when its profit target is smaller than。

The benchmark on that set and the profit target for set one is the benchmark value for set two and vice versa。

 so one of them must succeed。So。If we want to relate。嗯。

The revenue of the random sampling auction to our benchmark。

 the revenue of the best fixed price that sell to at least two people。

 it's enough to relate the minimum of these two quantities。

 the revenue of the best fixed price either on set one or set two to our benchmark value。

So that's going to be the strategy for the rest of the proof。Okay。

So let's like forget about auctions for a second and just think about like a simple。

Comminatorial problem。ok。I'm going to flip k coins where K is at least two。

 so we're going to flip at least two coins。Each coin is going to come up uniformly at random as heads or tails。

And I'm going to tally up how many heads I've gotten and how many tails I've gotten。

And what I'm interested in is the smaller of those two quantities， the minimum。

 the expected value of the minimum of the number of heads and the number of tails after k of these plums。

Yeah。And the claim that I want to make is that this minimum value。It's at least k over four。Okay。

 so let's think about that。So let's just give some notation here。Let's say that MI。

Is the expected value of the smaller of the number of heads I've gotten and the number of tails I've gotten after I've flipped the coin i times。

Okay， so MK is the thing we're trying to bound。Okay， so we can like start。

By computing MI for each of the integers， see how far we get。So suppose I flip one coin。Well。

 it's either going to be heads or tails。And so you know either heads will be one and tails will be zero or tails will be one and heads will be zero。

 in either case， the minimum of the two is zero。So like M1 is zero。How about M2， I flip two coins。

 well there's sort of four cases I could get heads。

 tails or tails heads in which case the count of both is one and the minimum of the two is one。

Or I could get heads， heads and tails， tails， in which case。

 the count of one of these is two and the other one is zero， in which case the minimum value is zero。

So the minimum value， half the time is one and half the time is zero。So M2 is 1 half。Okay。

 only countably many cases to go。Now suppose I define。Xi。

To be sort of the increase in this quantity after one step。

 So Xi is like the difference between Mi and MI -1。

 It's the expected change to the minimum of the number of heads or tails after one more coin flu。ok。

😊，不。😡，By linearity of expectation。If I want to know what MK is， and I do want to know what MK is。

 that's the thing we're trying to prove the theorem about。Well。

 it's just the sum from i equals 1 to k of Xi。Right of the change and MI I from step I minus1 to step I。

 because if I sum all of these up， I get a telescoping sum that's just Mk at the end。

So let's think now about computing these Xs。O。So I'm going to break this into two cases。

 depending on whether eye is even or odd。Now for those of you who've taken a number theory class。

 you'll know that if I is even。An i minus1。Must be odd。In which case？

The number of heads must not be equal to the number of tails。

 you can't divide an odd number into two even integers。嗯。😊，Which means。right。

 so if I even an I minus1 was odd， which means that after the first I minus1 coin flips。

 the number of heads was not equal to the number of tails。Which means that there is a minimum。

 like either the number of heads was smaller or the number of tails was smaller。And so。

Xi must be exactly one half。We increase the minimum exactly when we flip the coin so that it lands on whichever of heads or tails was the minimum and it increases the minimum by one。

Okay。Now， if I was odd。This will become increasingly unlikely as I gets bigger， but in principle。

 there could be a tie I could have。The number of heads exactly equal to the number of tails in which case。

No matter how my coin comes up， I will not increase the minimum of the number of heads or the number of tails at all。

Because if there's five heads and five tails， then the minimum will still be five。

 no matter what the next coin flip comes out to。Okay。

 so this will become increasingly unlikely as I gets bigger。

 but like in principle there could be a tie。And Xi could be like zero。

But like at least it's not going to be negative， like we're not going to decrease this count。And so。

 you know， let's just be sloppy in this case and we'll say， you know， if I is odd， you。

 all I know is XI is you， non negative。Okay。So remember。

 we want to sum up from es1 to K of xk and like the even。Values of I are going give， you know。

 are going to give us an X I equals one2。And like。In any given string of integers。

 consecutive integers， something like half of them are even。So。You know。

 I can sort of bound this sum by the number of。Even integers in this sum。

 which is something like k over2 times1 half， which is what Xi is for the even integers。

And for the odd ones， we've sort of sloppily given up and we've said， well， maybe we get nothing。

But we get a value summing up over the even integers。

 getting one half or each of the even integers of k over four。是。You know， if you were paying。

A little bit more attention。You might have noticed that like。

It's really only roughly half of the integers in a。Sequence of。Kentucky integers that are even。

 you know， it's more like the floor of k over two rather than k over two if k isn't even。U。

And you might worry that this is actually like slightly less than K over four。

But you can make up for this fact just by checking that。You know。

 like actually x3 is not zero despite the fact that。Three is odd x3 is one quarter。

 you can just compute that， which makes up the difference， and so this is in fact a true statement。

Okay。So let's go back to the random sampling auction。And the claim is that。

The revenue of the random sampling auction。In expectation。

Is guaranteed to be at least to the revenue of our benchmark。

 the best fixed price that sells to at least two bidders。Over four。

 we get a four approximation to the optimal revenue。Okay。So remember。We've already shown。

That the revenue of the random sampling auction is at least the smaller of the following two quantities。

 the revenue of the best fixed price unlike random sample one and the revenue of the best fixed price on random sample2。

Now we know that。嗯。😊，This benchmark value， the revenue of the best fixed price overall。

 like say on all of the bidders。Well， it's going to be some price P。

 the best fixed price will be some price p， it'll sell to some number of bidders k that is at least two is the revenue of the you know we're comparing to the benchmark that sells to at least two people。

And so we can write the revenue of the best fixed price as k times p for some price p and some k。

 at least two。Now let's think of those K lucky winners。

 the K lucky winners in the overall set who would have won the item had we sold it at the best fixed price。

Some of them， when we ran the random sampling auction， were thrown into set one。

And some of them were thrown into set two， we flipped the coin for each one of them。

So of the K winners who would have won the。Auction at the optimal price。 Let's say that。

K prime is the number that ended up in set S prime。

And let's say that k double prime is the number that ended up instead said S double prime。诶。Now。

 what is the revenue of the best fixed price on set S prime？Well， at the very least。

 we could have tried selling the item for the same price that was optimal on the whole set。

In which case we would have been able to sell it to at least k prime people。

 the people who were willing to buy it in the whole set and K prime is the number of people。

 the number of such people who fell into set S prime and to each of them we would have sold it at a price of P maybe on this subset there's an even better fixed price。

 but if nothing else we could have tried selling it at price P so the revenue on this subset is at least K prime times P。

And similarly， the revenue onset。S double prime is at least k double prime times P because we could have tried selling。

The item at price P， maybe there's something better， but if we tried selling it at price P。

 we know there's at least K double prime people who would have been willing to buy it。And so。

If we look at the ratio of the revenue that we get over the benchmark。

 which is this thing we want to bound。Well， we know it's at least。

The minimum of the revenue obtainable。On set S prime and set S double prime。

Compared to our benchmark， remember our benchmark， we can write it as k times P。

And our prime is at least k prime times P。And our double prime is at least k double prime times p。

And P is in the numerator and the denominator， so it cancels out。And so it's at least the minimum。

 it's at least the。Yeah， the minimum of k prime and K double prime over k。Now， what is this？

How did we decide which of these bidders was in set S prime and which one was in set S double prime。

 we flipped the coin。Okay。So this is exactly equal to the outcome of the experiment in which we flip K coins。

And then count， you know， what is the minimum value of the number of heads and the number of tails？

Which is at least k over four when k is bigger than two。Okay。

 so this is at least one quarter this is the part where we're using that K has to be bigger than two。

If k was 1， the minimum would be equal to zero。ok。So。

We can approximate the revenue of the optimal auction without knowing the distribution。

Now we got this four approximation four is kind of a。Big number， like。

Your manager might not always be happy with you when you tell them you got 25% of the revenue you could have gotten。

But where did this four come from？Like remember like like。

We decided we couldn't compete with the price that sells to only one bidder。

 and so we lowered our sites， but we still asked to compete with the price that sold to at least two bidders that's where the four comes from but like the hard case is when。

There's only like there's a zillion bidders， but like only two of them matter。

 in which case the only time you're going to make any money with the random sampling auction is if you get lucky and split them between the two sets。

In general， competing with this benchmark。Starts becoming a lot easier as you。Say， well。

 I want to compete with the best fixed price that sells really least three people or four people。

So the same techniques， if you think about it， will get you a one plus epsilon approximation to the optimal revenue。

 where now we have to talk about the optimal revenue where you sell to at least K people。

But K doesn't have to become that large for Epsilon to become small。All right。

 so I'll see you guys next class， I guess。There's lots of holidays this week。

 including Passover and Easter， so maybe next class is next week， does that sound good？All right。

 see you guys next week。It's you。

![](img/b923a4c8746afc0ed37fac0303a13d0d_3.png)

系紧点。