# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p16 NETS 4120_ Algorithmic Game Theory, Lecture 16.zh_en -BV15kLRzTExU_p16-

All right。

![](img/7bbda20821d39562631af8376e275c29_1.png)

So let's begin where。We started talking about auctions last class and we're going to keep talking about auctions for a little bit。

 sort of a mini section of the course。And maybe just to remind ourselves of where we are。

Last lecture， we introduced this extremely general mechanism design setting just to like drawg your memory a little bit。

There's like a completely arbitrary set of choices that we need to make like we just call this the set of alternatives and。

Participants in the auction could have entirely arbitrary set of preferences， valuation functions。

 mapping， arbitrary alternatives to evaluations and assuming that they have。

Qui linear utilities for money， which just means they can represent， you know。

 their happiness level for all of the different alternatives we might choose in units of dollars and that their value for money is linear and the amount of money。

We showed that there was this one mechanism， the VCG mechanism that solved this problem like in full generality and had a lot of nice properties that maximize social welfare。

 it was individually rational which means that sort of it was safe for people to participate they would never be asked to pay more then they valued the alternative that was chosen。

 it was dominant strategy truthful， nobody could manipulate by sort of misrepresenting their preferences。

And it had the no deficit property， like we were going to make money， we weren't going to lose money。

Okay， so。this general setting captured all sorts of stuff。

 not just single item auctions that were' sort of our running example。

 I have a thing to sell you know who' is it going to go to。

 but really lots of things in full generality， could be arbitrary combinatorial auctions where we're giving out lots of stuff and we've got constraints about who can get which subsets for example if we were auctioning off takeoff and landing slots at airports or if we were auctioning off radio spectrum across the United States just to mention a couple of real- worldorld examples。

 you could capture public projects problems， you know should we as a town build a fire station or you know a library so all sorts of things。

And。We sort of ended the class， you know， wondering if， you know。

 like that was it like maybe you don't need auction theory beyond the 1970s when the VCG mechanism was developed。

 like maybe that the solves mechanism design。And there were a couple of reasons we had at the end of class for why we might not quite be done。

One that I'll just remind you of， but is not the topic of today's lecture is computational complexity。

 So we just sort of took it as given that we could。Say， you know。

 our actually just choose the alternative that maximizes social welfare given the reported evaluations。

 but of course， in a complicated setting with a big outcome space that might be a computationally hard problem and we'll have to spend time later in the class thinking about what to do when when it is。

But。😡，Sort of more immediately and what we'll talk about today is。The VCG mechanism was great。

If the thing you wanted to do was maximize social welfare。Right， like。If。

What you wanted to do was choose the alternative that made people in the aggregate as happy as possible。

 you had this sort of utilitarian objective where you just want to maximize average or some value for the alternative chosen。

 well that's exactly what the VCG mechanism does。But。

We might find ourselves in a position where that you know social welfare is great and all。

 but maybe that's not our goal， maybe we have some other objective we'd like to maximize。

 for example， an objective you often want to maximize when you're selling things because you want to maximize your revenue or your profit。

Okay， and the VCG mechanism just， it doesn't do that。

 it's very specific to maximizing social welfare。So what I want to do today is to。You know， the。

The very the general problem of。Understanding all of the objectives that are compatible with。

You know， dominant strategy truthful mechanisms in the。

Full mechanism design setting as we defined it last class。

 that's a complicated problem that's still not completely understood。

But what you can do is when you sort of restrict your attention to restricted classes of problems that still capture some interesting stuff。

You can fully characterize fully answer this question。

What objective functions can you optimize for in a dominant strategy truthful way？

So that's what we're going to do today in a particular class of problems that I'll define called single parameter domains will give sort of a full classification for when you can solve this problem and when you cannot。

And。This will be sort of the basic building block that we use next class or the next few classes really to do a few things。

 one of which is maximizing revenue in the class of auctions another of which will be solving various kinds of combinatorialarily hard auction problems that require the design of approximation algorithms with special properties what those properties are will be sort of the content of today's lecture。

Okay， so that's sort of the。Agenda for today。Questions about the。

The plan of action before we dive in。Okay， so like。One thing I want to observe。

 like the VCG mechanism， it maximizes social welfare。

 which is just the sum of the valuation function， like the unweighted sum of the valuation functions for the alternative chosen。

One easy extension that is something you're going to prove on the next homework is that very similar ideas。

 very similar derivations actually will allow you to maximize like a slight generalization of the social welfare function which basically amounts to like weighted social welfare like you don't have to maximize the unweighted average of everyone's happiness for the alternative chosen you could maybe like some people better than others。

 some people are more important than others， you could give different people weights and you could maximize the weighted average。

And in fact， you might have your own preferences as the mechanism designer so you could give weight to your own preference if you want to put your thumb on the scale。

So you could take the social welfare objective and sort of maximize。Instead。

 like an affine transformation of that where I differently weight people's values and maybe I have preferences myself as the Me designer。

 so this is a pretty easy extension of what we did in class last time and you'll do it on the homework。

But this isn't a huge extension， these things all really look like social welfare。

The real content of this class is you know what else we can do。

 what are things what our objectives functions we can maximize。

 which like really don't look like social welfare， how far can we get beyond this？

And as I suggested earlier， like in full generality， that's kind of a hard problem， I mean。拨啊五。Yeah。

 even at the research frontier， this is not a fully understood problem in full generality。

 so we're not going to' you know we're not going to answer。

This question in full generality of what objective functions can we maximize in a dominant strategy truthful way in arbitrary mechanism design problems。

 but rather we'll try to like give a complete answer for that question in a restricted domain that is still rich enough to have some interesting stuff in it。

And this restricted domain in this restricted setting is something I'm going to call a single parameter domain。

Walk through the definition。 But let me try to give some。Intuition first。

So remember in full generality in this mechanism design setting。We talked about last time。

You could really have an arbitrary evaluation function that just assigns like an arbitrary real number to each of the possible alternatives。

 So like the number of。Parameterters I would need to write down your evaluation function is。

Linear in the number of alternatives like you need to be able to tell me how happy you are for every possible alternative。

 so for example， in a combinatorial auction with K items you would need to tell me not just your utility for all of the different subsets of items that you might get but in principle you could also have preferences over the subsets of items that other people get right like maybe you'd be jealous if your next door neighbor got like a cool。

Car or something。Similarly， even just like in like a single item auction。

 which seems like this sort of super simple thing。When we analyzed it last class and we sort of noticed that like second price auction are truthful。

We assumed that。You didn't care like we assumed that the only thing you cared about was whether you got the item or not。

Right like there was some value you had for this item such that if you got it， you。

 you would experience you know， V units of happiness and if you didn't get it。

 you'd experience zero units of happiness， but if you didn't get it。

 you didn't care about who else got it。But that was an assumption like in the generality in which we defined the mechanism design problem in which we proved the VCG mechanism has nice properties you could have。

Like you could have had， in principle， a different utility。

Or every single person who might be allocated the item。Okay。So。

Informally single parameter domains are those for which。We assume that's not the case。

 like basically。We assume that。For everybody， there is a publicly known ordering over outcomes。

 for example， in a single item auction， we assume everyone would prefer to get the item over not getting the item and we assume everyone is indifferent。

To who gets the item， assuming it's not that。Okay， so the thing that we sort of just assumed structurally about people's preferences is that。

They'd prefer to win the item than to not win the item， at least if prices are now objects and。

That assuming they do not win the item。They don't care who else wins。

And what we that's what we assumed last class and what we got out of that was that I could describe your utility function in this case。

 which otherwise could be like a complicated object just with like a single number。

 what is your value for the item right like how happy are you going to be in the event that you get the item。

Okay， so a single parameter domain just sort of generalizes this。We sort of assume like we say， okay。

 look。We've got some set of alternatives， A。But what we assume is publicly known is what I'll call for every。

For reag， a public value summarization function that maps alternatives to real numbers。

That's sort of like the relative。You know， the sort of assumed relative preference over all of the outcomes like you prefer winning the item to not so maybe this public value summarization function maps to one。

In the outcome in which you win the auction and maps to zero for any other out。Okay。

 so that's sort of。Some structural assumption about your preferences that we assume we don't need to elicit from you。

 we know that already， you prefer winning the item to not。

The only thing we don't know is like quantitatively how happy you're going to be if you win the item。

Okay， so this public value summarization function， this is publicly known。

 we don't need to like elicit this through a truthful mechanism， but there's some like number。

 there's some real number VI like your value for the item that we don't know。

That is like a scaling factor。Your happiness at some alternative A is going to be VI Is。

 this public value summarization bunch。So just to like make that concrete。

 to walk through a couple of examples。Single item optionsuction are a single parameter domain。

And the public value summarization function， is's just what we've been talking about， it says。

Your relative utility for winning the item is one and your relative utility for losing the item is zero。

 and of course there's this unknown scaling factor， v， your value for the item。

 and your actual value for winning the item will be v times this。

 so it'll be v if you win the item and zero otherwise。So by assuming the structure。

 by assuming that you don't care who gets the item， assuming it's not you。

What this lets us do is it lets us summarize your otherwise complicated valuation function in like a single number。

 your value for the item。Does doesnn't have to be a single item auction either it would sort of work in a combinatorial procurement auction as well。

know in some settings， so let's consider the following mechanism design setting。We're here， maybe。

The mechanism designer is not selling things， the mechanism designer is buying things instead。

 we could call this a procurement auction。And suppose that what the what the sort of。

Mechanism designer wants to buy our paths in a network。

Maybe the mechanism designer would like to buy a path in the network that connects some source to some sink and maybe the agents correspond to edges in the network。

 so the agents correspond to service providers who can route traffic from point A to point B。And。

Great， so what the mechanism designer is going to have to do is it's going to have to sort of buy from a subset of agents responding to a path connecting point A to point B。

To optimize some objective。But the the agents are going to experience cost if they provide the service。

 so I'm an agent that controls some edge， if I am going to let you use the edge。

 then I will experience some cost。Now you don't know what that cost is。

 that's the thing that you need to elicit truthfully if we're going to have a you know a truthful mechanism。

But。Like maybe what is known is that the structure of that cost function is that the agent controlling some edge will experience some cost if the bundle we buy is a path that includes that edge and they will experience no cost otherwise if we don't have to use the。

Okay， right， so you know， the alternative chosen is going to be a subset of the edges and agent。

E corresponding to one of the edges will have some cost if the edge is in the bundle and won't otherwise this is the public value summarization function。

 Now quantitatively， we don't know what that cost is。

 That's the thing that we need to like truthfully elicit in the mechanism design problem。

 but that can be summarized。As a sort of just a single parameter， like a scalar。

Equal to their cost that'll just be multiplied by this to figure out what their cost function is。

 Some unknown cost C， if their edge is used and zero otherwise。Okay。

 so this is also a single parameter domain。Because the thing we need to elicit is just a single number。

 the relative ordering of the outcomes in all of the agents's preferences is known。

Just maybe for one more example， suppose what I'm doing is I'm selling。Advertising spots。Okay。

 so maybe I've got like banner ads banner ads slots that I can fill with your banner ad。

 and I've got real estates on different website so you could buy a banner ad on the New York Times website or the Washington Post website or the Fox News website。

And suppose。哦。I know that what the agents have is like。Some。

Utility that is like additive in the number of unique viewers who see their ad。Okay。

 so maybe like you know they're selling something so every time I show the ad to like a new person。

 they have some chance of clicking through and buying the thing for me， so for each person， you know。

 like given how effective my ad is and how expensive my product is I make， you know， I don't know。

 maybe six cents。But that I don't have any value for showing the ad to the same person the second time。

 like the ad's going to work or it's not。Okay， so。For。

A bidder in this auction who's going to get who's going to get like an allocation of a slots as the alternative chosen by the mechanism。

What they care about is， you know， if every ad slot corresponds to some set of viewers。

 what they care about is the cardinality of the union of those sets。Okay。

 so maybe if the Washington Post and the New York Times or they might like individually have lots of viewers。

 but maybe they have a lot of viewers in common， and so the bidder would have high value for either one of those ad slots on its own。

 but their value for the union of the two of them wouldn't be that much higher。

 whereas maybe their value for like the New York Times and Fox News would be higher because even if the sets themselves are comparable size。

 they're much more disjoint so the union would be large。Okay， now。

If I made that assumption that the thing that the advertiser cares about， you know。

 that the advertiser's utility is basically some scale or multiple。

 you know like some kind of click through rate of。The number of unique users。

Then the complicated part of the utility function， which is that what you care about is the union of the advertisers who are going to or the users who are going to view your advertisement across the bundle of slots you get。

That part is that part I can sort of shove into this public value summarization function。

And the only thing I need to elicit from you is like this real number V， which is。

You know exactly how many cents each unique user is worth to。

 in which case your evaluation function is really VI。

 your sort of private value for showing an ad to a new user times the public value summarization function。

 which includes the complicated logic of taking the union， the cardinality of the union。Okay。

 so like。Single parameter domains can encompass relatively complicated mechanism design settings。

The key assumption， though， is that。The thing that makes the valuation functions complicated。

Is publicly known。And the thing that I don't know is just a single scalar。Okay，Does that make sense？

So from this point on we're just going to like talk about single parameter domains。

 so I want to pause here like if you if these make no sense。

 this is like a really good time to ask for clarification yeah like the same sort of structure for each player。

Not necessarily， yeah， these public value summarization functions could in principle。

 be totally different for each agent now。Probably in most realistic settings that you might not know like you might know about the setting in general。

 I know in general when I'm selling paintings， you prefer to get the painting then to not get the painting and that in general you you don't care who gets it if it's not you I might know a lot less about specific bidders so it might generally make sense to model things so that these public value summarization functions are the same across all of the bidders just because I'll know about the domain in general。

 but maybe not about the specific bidders， but this setting is flexible enough that if I did know something specifically about you。

 I could model you differently than everyone else。Yeah。这是开的。嗯。

So here I guess maybe it's what I called AIJ up here， like the outcome。

like what I need to decide is whichs say I've got a set of advertisers and a set of advertising slots。

 then maybe like XI J is one means like advertiser I is the one that's assigned to slot J。

And so to figure out advertisers advertiser I， utility。

 we would take the union over all of the slots J that are assigned to them of the set of viewers of that advertising slot。

Yeah。😊，真不是不。There is a good。Could you they have the idea that the even evaluation is。大概是个 number分是材。

Did they try about number different numbers being probably advertising you don't want to get the sellers better。

就走年。So your utility function， there has to be this like publicly known public value summarization function。

 and then your utility function has to be decribable as like a number VI times this thing。

So for example， when when I write down this public value summarization function for a single item auction。

 this is the thing that is encoding the structure that you don't care who gets it if it's not you。

 because your relative utility is one if you get it， and it's zero if you don't get it。

 no matter who else。Yes， sir。 So this this writing this down， this is encoding the logic that。

Your relative preference is first to get the item。Next。

 to not get the item and you're indifferent between all alternatives in which you do not get the item。

publicIt's public in the sense that like。I can design the mechanism with this knowledge。

 like this is not this right。 Like in the end， we're going to ask for mechanisms that are dominant。

 strategy truthful， which means there's something that。

Is it going to be in the strategy space of the bidders that they can report to us and possibly choose to mis report？

嗯。😊，I'm not going to ask them to report a whole valuation function。

 which is an arbitrary mapping from alternatives to numbers。

 I'm going to ask them to report a single number， which is like the scalar multiple of this thing。

 which is assumed to be their utility function。The right sense。Yeah。

 but I need theoretically define the single an function thing as a one if a with I。

 negative one if a is less than I and zero otherwise。

 and then it would matter for each player like which other piece。Oh。

 so you're saying like you're imagining a setting where I like。Basically people come like lined up。

 there's people like left of me left of me， there's people right of me like my favorite outcome is that I win at next that the people left of me win at next the people right of me win it Yeah。

 that would also like that would also be a single parameter domain it would be a different one。

 but you could encode that as a single parameter domain。

What you would have difficulty in coding at the single parameter domain is if。Each bidder could have。

Uniquely arbitrary preferences over who gets the item。

 but if everyone agrees that there's this ordering and everyone is happier if someone to the left of them wins then to the right。

 you can also encode that as a single parameter demo。

just to clarify like each person has negative that they the negative。你就你呢个。单位。

So long as I know who your enemy is， it would be。 I can't like because when I'm when I'm asking you。

To report something it's just this number of V it's not this number of VI paired with who your enemy is。

 but yeah you could have a like we could have a single parameter domain where your first favorite is you know you get the item your second favorite is anyone but your enemy your third favorite is your enemy gets it and I could encode that as a public value summarization function so long as I already know who your enemy is and I don't need to elicit that from you that makes sense Yes so it's these are just three examples you can encode all sorts of stuff a single parameter domains but not arbitrary things it is a limitation。

But you can encode everything we've done managed。Good question。Yeah。这快。Okay。Yeah。

 the players know they're on utility functions。这是降低来。被有没有。They could sure， yeah。

 what we're going to derive is mechanisms for which it's a dominant strategy to report the BIs so long as we're in a single parameter domain。

Okay。Sos everyone with this setting？Okay。嗯。So let's remember what a mechanism is。

 remember it is an allocation rule or a choice rule。Together with a payment rule。

The choice rule or the allocation rule， right it's a mapping from reported valuations。

 which in these single parameter domains are just each reported valuation is just like a real number。

The mapping from reported valuations to alternatives chosen。So in principle。

 a choice rule could be like totally arbitrary， it could map arbitrary reported value vectors of reported valuations to alternatives。

 but we'll say that a choice rule in a single parameter domain is monotone non decreasing in。

The bid of player I。If no matter what the vector of other bids is。

 no matter what the bids of the other players other than I are。

And for every possible misreport that bitter eye could consider making that。

Is pushing their bid upwards， so for every VI prime that is bigger than the VI。It should be that。we。

Public value sumization function of the alternative chosen when。Bitter eye bids the lower value。

Should be only smaller than the public value summarization function of the alternative chosen when bitter eye bids the higher value。

So this is saying。If you raise your bid。It might be possible that the alternative changes。

 but the alternative should change to something that you prefer， not to something that you。Like less。

Okay， so if I like in a single item auction， if at some bid， I am。Losing the item。

 so my public value summarization。Value is 0， and I raise my bid。 I can go to winning the item。

 so my public value summarization function might shift to one by raising my bid。

 but the reverse shouldn't happen。 I shouldn't go from winning the item to losing the item by raising my bid。

And more generally。my value， which up to scaling is just my public value summarization function applied to the alternative chosen。

Is monotone increasing in my bid or at least non decreasing where I can't， I can't。

Get an alternative that I like less by raising my bid。Okay， that makes sense pretty。

Natural property to think about that sort of if someone raises their bid。

That should only cause them to get。An outcome that they like more。Okay。

 questions about this property clear。Oh， sorry， Tna。In a single item option， this means if an8。

 you know， if our allocation rule is such that。Some agent wins at bid V。

 He also has to win at all higher bids。ok。So here is sort of the punchchline。嗯。

What we're going to prove is that within single parameter domains。If you have。An allocation rule。

And you're interested in the question of whether you can。Implement it truthfully。

 whether you can implement this allocation rule by pairing it with a payment rule that makes truth telling a dominant strategy。

You can answer that question by just asking yourself。

 is the allocation rule a monotone in all of the bidders bids？If the answer is yes。

There is a payment rule that implements this choice rule in dominant strategies。

And if the answer is no， there's not。ok。So in particular， you know， like here's the theorem。

The payment rule is not even a mystery， it's like given here in the theorem。

So a mechanism in a single parameter domain。嗯。😊，By which I really mean， I guess a choice rule， okay。

 so you think about it this way maybe like you've got some objective function you'd like to optimize for in a way that makes truth telling a dominant strategy。

Well。Once you have that， you。You know if you're going to be able to do that。

 you know what the allocation rule has to be， it's got to be the allocation rule that chooses the alternative that maximizes whatever your objective function is given the valuation function。

O。Look at your。Altative， look at your choice rule。And check。

Is it monotone non decreasing in this sense， Is it the case that。

For every bitter eye and for every set of bids， bitter eye can only obtain a more preferred outcome if they raise their bid。

 never a less preferred outcome。Then if that's the case。

If you pair your allocation rule with this particular payment rule。

Then you'll have a dominant strategy truthful mechanism that implements your objective function of choice。

And if it's not。There is no mechanism that implements your objective function of choice and dominant strategies。

 it's just not possible。O。And the payment rule is something and you know。

 maybe we'll look at this and sort of observe that it recovers things like second price auctions。

 but is the form of the statement。Clear。Okay， so it's like a complete characterization in single parameter domains of which objective functions you can implement truthfully and which you cannot and the characterization gives a very simple answer。

 like the allocation has to be monotone non decreasingreing in every bidder。All right。

 maybe it's worth just spending like a moment like glancing at the form of the payment rule。

That makes this thing truthful and observing that even though you know it looks kind of complicated。

 it's got like an integral， it does recover like the simple things we've studied so far。

 like second price auctions in the sort of single item auction setting。Okay。

 so what's the payment rule， how much money do you have to pay？Well。

You have to pay your value for the alternative chosen。That's what this is right VI。

 your value times your public value summarization function evaluated at the alternative chosen。

Minus this like integral。😡，Overall bids lower than yours。

 all bids between zero and what you actually bid zero and VI。

Of what your public value summarization function would have been， had you bid this lower value Z？ok。

So let's just maybe like observe that this recovers a second price auction in a single item off。Okay。

 so let's suppose that。You know， I'm the winning bidder， I bid。100 for the item， and I won it。

And the。Second highest bidder bid $75。Okay， so the payment rule to be consistent with what we studied last class had better be that I should pay $75。

Okay， well， if I won the item， my public value summarization function at the alternative chosen is one。

 I won the item and we multiply by $100 my value for the item， that's 100。And then I subtract off。

This integral。From zero to 100。Well， what's my public value summarization function here。

 it's just one for bids for which I win the item and it's zero otherwise。Okay。So。

It's just the indicator function。For like。The event that。Bitter eye wins。嗯。When。They bid。Z。

Integrated overall z from0 to 100。Now。If I'm giving the item to the highest bidder。

What is the lowest bid such that they win？Well， it's it's the second highest bid that at the moment that you raised your。

Bid above the second highest bid， you became the high bidder。So whatever the second highest bid was。

 the integral from zero to the second highest bid was zero because you didn't win the item of the public value summarization function was one。

The integral from the second highest bid to the indicator was one everywhere from the second highest bid to your true bid。

For this integral， right， we have 100。Minus just the difference between。Your actual bid and。

The second highest bid， your bid was 10， we said。Of， you know， like a function one。

 so it's just 100 minus v2。And。The price you pay is just V2， the second highest bid。Okay， so this is。

Some payment rule that's like， you know， on its face。

 it looks a little more complicated than a second price auction， it's got this like integral in it。

 but as a sanity check。You know， like when we instantiate this for single item as where the thing we want to maximize is social welfare。

 which just means give the item to the person who likes it the most。You know。

 like gratifyingly this complicated expression recovers second price options and like more generally we can take other domains and apply this payment rule and it'll recover other things。

Okay， so it's the statement of the theorem。Sure。Okay， so let's prove it and。

I want to simplify notation because otherwise we have to like think about expressions that look like this a lot。

 like WI of x of Z v minus I， I just don't want to write that down over and over again。

 so let's simplify notation in the following way。It's like， first of all。What are we doing。

 we're proving dominant strategy truthfulness or which means we're going to need to reason in the following way。

 we're going to have to pick a particular agent eye to zoom in on and we need to say look。

 no matter what everyone else bids， it's always in bitter eyes best interest to bid the truth to tell the truth。

And so throughout all of these arguments， we're just going to be fixing what everyone else bids and thinking about the incentives of agent by。

So I want that to be reflected in the simpler notation as well。Choose your favorite agent I， okay。

 just choose it right now。Also choose the bids of all of the other agents。

 the argument we need to make had better be true no matter what those things are。

 so let's just fix them。And now。When previously I would have written， you know。

 w of x of V where V is this vector of all of the other bids and bitter eyes bid and W is the public value summarization function and x is the allocation rule。

 I'll just write Y of V for that Okay， and this will just be like。

 I'll think of this just as a function of。Bitter eyes bid fixing everything else。 It's just。

 you know， what is bitter eyes relative。Utility， relative value。

 according to their public value summarization function when they bid B。Okay， so just for example。

 in a single item auction fixing what everyone else bids， y of V is just one。

If bitter eye wins the auction and at zero otherwise。Okay， so this just like。

Simimpr notation for like the thing we're going to need to be talking about。EnDuring this argument。

Does that make sense？ok。Now there we're proving and if and only if characterizations。

 we need to prove two directions of the claim。Let me prove one of them first。

So what do I want to prove first？Well。The two directions are， on the one hand。

 if x is monotone non decreasing。And we use this payment rule。

 then the mechanism is dominant strategy truthful。 That's the  one I want to prove first in the other direction。

 we're also going to need to eventually prove if x is not monotone。

 then no payment rule can make the mechanism dominant strategy truthful。嗯。As I've written it。

 it does not say that， but that is also true。We're not going to prove the uniqueness。

 but but it is true that this is the unique payment rule that does it well。

This is the unique pavement rule that makes it truthful and individually rational and budget balance。

 of course， if all I wanted was truthfulness， I could also take any。

Translation of this and it would work。Okay， so first we're going to prove the one direction that says。

If you give me an allocation rule that happens to be monotone。In the bids of all of the agents。

 then the payment rule on the previous slide makes it dominant strategy truthful。ok。Okay。

 so so like just again， to like write down what we need to prove in our new notation to make sure we get it。

We need to prove the following。Remember you are bitter eye。Your true value。

 unknown to the mechanism is V。 What we need to show is that。You can't benefit。

You can't get a higher utility outcome by misreporting some other bid V prime。Okay， so。

This is the inequality we need to show， we need to show that your utility， if you tell the truth。

Is higher only higher than your utility if you lie and misreport your evaluation as V prime。

What's your utility if you tell the truth Well， it's a single parameter domain。

 so by assumption it's v times y of V。Minus the payment you need to make。Okay。

 both the allocation and the payment are a function of your report。What's your？Utility， if you lie。

 well， if you lie。You'll get a different allocation and a different payment。

 but you won't have changed what your actual utility is。

 so your utility will be v times y of v prime。Like youll still your utility will still be evaluated according to your actual utility function。

 but the alternative chosen might be different。And the payment。

That you have to pay could also be different。Okay， so dominant strategy truthfulness just means for all V for all v prime。

 it had better be than v times y of v minus the payment you make when you report V。

 that's just your utility when you tell the truth。Is at least v times y of v prime minus the payment you need to make when you report v prime that's your utility when you lie。

Okay， so this is just a restatement of what we need to prove in our notation。B。Okay， and。

Like the theorem statement was nice enough to like， actually give us。

An expression for the payment you need to make when you report V。You know。

 we don't need to like wonder what that is， we can just plug it in， right like the payment rule。

Is this very specific thing， it's your value according to your reported valuation of the alternative chosen minus integral from all the bids。

 the integral over all of the bids you could have made that were lower than the bid you did make。

Of your。Of the public component of your value， if you had made those lower bids。Okay。

 so your utility。In that case， if you tell the truth。Well。

 it's your value for the alternative chosen。Minus the payment you need to make。

 which subtracts off your value for your reported value for the alternative chosen。

 which is the same as the value for the alternative chosen if you took the， if you told the truth。

Minus the integral overall lower bids of this thing that we're now calling y of z。

And that had better be higher than your value if you lied or your utility， if you lied。

 which you know， you really experience。Utility v times y of v prime。Right， because， you know。

You lied， but you didn't deceive yourself。But what the payment rule subtracts off is your reported utility for the alternative。

 So what the payment rule subtracts off is now V prime times y of V prime plus。Again。

 Y of Z integrated overall。Bid Z that were lower than the bid you actually made。Okay。

 so this is just the thing we need to prove， but plugging in our actual expression for the payment rule。

ok。And just trying to simplify this a little bit。we might notice that like we have this cancellation on the left like v times y of V cancels out with the same term and the payment rule。

 and so what we need to show is just that this integral on the left。

 this integral from zero to v of y of z， this integral overall lower bids。

 bids lower than your true value。Had better be bigger than this integral from all bids lower than your reported value。

Minus。V prime minus v times y of v prime。Okay， so this is just simplifying the expression。Okay。

 this is the thing we need to show。Okay。Now we can basically prove this by drawing a picture that's what we're going to do The only thing is there's like two pictures we might need to draw depending on whether V is bigger than v prime or whether V prime is less than sorry whether V is bigger than v prime or whether V is less than v prime Okay because like we're going to draw a picture that's like。

The difference between these two integrals and it's going to matter whether v is on the left and v prime is on the right or vice versa。

O。😊，So let's consider two cases。 The first one is going to be the case when v prime is greater than V。

Okay， so like， your misreport is bigger than your real value。In which case？If I subtract off。

This integral on the left hand side from both sides。

 what I get left on the right hand side is just the integral from V to v prime。Okay。

 and so the expression that we need to show simplifies to the integral from。V。

 your true bid to v prime， this higher misreport you made。

Of your public value summarization function， well that had better be less than the difference between your missed report and your true bid times your。

Public value summarization function at your M report。So I claim that this is like a picture。

 so ignore everything else on the slide， I'm going to draw a picture for you。So。

We're taking the integral over this thing y of Z， which is some curve。

 I don't know much about what it looks like， but I do know by assumption that it is monotonically increasing in Z that was the premise right our allocation rule was monoed。

So thing， whatever this curve y of z looks like。😡，开了。Pving upwards。Okay。

 that was like the one assumption we made monotone non decreasing。

Now I'm looking at the integral of this thing from v to v prime。😡。

And I know in this case that V is less than v prime。Let's say these's over here。Be primes over here。

And so can anyone remind me like？And probablyly you all took calculus back in like third grade or something。

 so it's been a long time you don't really remember， but like let's try to like what is。

 how do I draw an integral， what is the geometric meaning of like a 1D integral of a curve。Yeah。

Everyy end of the curve， so the integral from v to v prime like this thing that we need to bound。

It's like the area under this curve。Okay， so the left hand side is this area I've shaded in yellow。

Now this right hand side is like the product of two numbers。

 and I guess in like first grade you put in geometry， you talked about like areas of shapes。

 what kind of shape has an area that can be described as like the product of two numbers。Yeah。

 they rectangle， right？So what are those two numbers？One is。Y of v prime。

 that's just this point here at the top of the curve。And the other the other of which is。

V prime minus v， that's just the length of this interval that we're taking the integral over。Okay。

 so the right hand side is the area of this rectangle。Okay。

 and the area of the rectangle is bigger than the area under the curve because。

The curve is monotone increasing。Okay， the area shaded in white includes the area shaded in yellow。

And that's what we needed， right that the right hand side should be bigger than the left hand side。

Okay， make sense。And if you prefer。Algebra to pictures。 It's also like a one liner。ok。嗯。😊。

Now there's this other case too， because。If V is actually bigger than v prime。

 then this integral is going to be like negative and in order to think of it as an area。

 we're going to have to multiply by negative  one， which is going to flip some signs around。

So let's just do that case as well。If v prime is less than V。

The thing we need to do simplifies a little bit differently now the integral from your lower missre to your higher true value。

Of your public value summarization function at these。Bid Z， you could have made in between。

Now this should actually be bigger than v minus v prime times your public value for itsreinged V prime。

Okay， so let's just。Draw this picture a little bit differently now。Okay， so same axes。

But now v prime is the smaller number。And V is the bigger number and you still don't really know what this curve looks like。

 but I still know it's monotone increasing。Okay。Now the left hand side it's still， you know。

 like we've arranged things so that we're still integrating from the smaller number to the bigger number。

 okay this time B prime is the smaller number， so the integral can still be interpreted as the area under the curve。

Okay， so the left hand side。Remains the area under this curve。

And the right hand side is still a product of two numbers， so it's the area of a rectangle。

But it's a different rectangle this time。So the width of the rectangle is still what it was before。

 it's the interval that we're integrating over， it's the interval from V to v prime。

But the height of the rectangle is no longer。The highest point on this curve over the area of integration。

 but rather the lowest point on the curve in the area of integration。

So the right hand side is the following rectangle。Whose base is？

The interval we're integrating over from V prime to V。But whose height is now。

The lowest point on this curve that we're integrating over。And again， because。

The one thing we know about the curve is that it's increasing。We know that。

The area of the rectangle has to be smaller than the area under the curve in particular。

 it misses like all of the area under the curve that corresponds to parts that actually increase。

Okay， and so the area of the rectangle， the right hand side is only smaller than the area under the curve。

 the left hand side， which is the thing we were trying to show。Okay。😊，Make sense。

So that's actually the。Complete proof in the Wo Direct。

We've shown like even though all we did was like draw pictures of curves on the board。

Like what we've shown is that。If you pair any monotone allocation rule。

With the payment rule in the statement of the theorem， which remember recovers among other things。

 the second price auction rule。Then the resulting mechanism makes it a dominant strategy to tell the truth。

Okay， so like simple geometric arguments。You know，Motone allocation rules can always be made dominant。

 strategy truthful， and with a particular payment rule。Questions about that direction？Okay。

We still need to prove the other direction and like in some sense。

You might think the other directions kind of harder to prove because there's this sort of universal quantifier like in this direction I told you what the payment rule is and so in some sense。

 like the thing you needed to prove。Inevit， if it was true， inevitably had to come out of， you know。

 just like。Manipulating the algebra because you knew what the allocation rule was。

 you knew what the payment rule was so you know there was a particular mechanism you were analyzing。

 you could just write down what your utility was for telling the truth。

 what your utility was for misreporting and you know you just had to like establish an inequality on this particular mechanism that I told you was true。

In the other direction。What we need to show is that if I give you。A mechanism that is non monotone。

 an allocation rule that is non monotone， then there does not exist a payment rule that you can use to make it truthful。

So it's not enough to show a violation of truthfulness for a particular payment rule。

 you need to show that for all payment rules， you don't get a dominant strategy truthful mechanism。

Right so this conceptually seems harder， we need to prove the non existenceence of something rather than just establish the properties of a particular concrete mechanism。

That's not that hard either。So let's do it and actually it's going to be a little bit。

Easier to prove the contra positiveitive。So remember。The original statement of the theorem。

 this direction of the theorem is that。If your allocation rule is non monotone， then。

There does not exist a payment rule that makes it truthful。

But what I'm going to prove is the the equivalent statement， which is the contrapositive。

 which is that。If there is a payment rule that makes your mechanism truthful。

 then your allocation rule is monitored。Okay。So that that's an equivalent logical statement。

 but it'll make it easier for us to think about things because algorithmically， we can think that。

Someone has handed us a truthful mechanism that includes an allocation rule and a payment rule。

 so now we can start reasoning about its properties with this payment rule。

 and what we need to establish is that whatever this mechanism is。

 the allocation rule has to be monitored。Okay， so that's like a logically equivalent statement and it's the one we're going to establish。

Okay， so to show。You know you hand me something that is a you know you claim as a truthful mechanism okay so it has an allocation rule in particular it defines this object Y that we're talking about and it's got a payment rule and what I need to be able to do is。

Look at this object you've handed me and hand you back a proof that your allocation rule is monotone。

Okay， so。What do I know， I know that I've got。A particular pair of objects。

 an allocation rule and a payment rule， and I know that。By assumption。

The mechanism defined by these objects is dominant strategy truthful， What does that mean？Well。

 it means that。If you tell the truth。Your utility， which is just。V times y of V。Minus P of V。

 the payment you have to make when you tell the truth。Is only larger than。Your utility when you lie。

 which is just v times y of v prime， right， your true utility for the allocation that results from your lie。

Minus the payment you have to make when you report V prime， this is just， you know， this must be。

 if the mechanism is dominant strategy truthful， this must be true for all pairs V and V prime。Okay。

 and in particular， it has to be true for pairs such that v prime is bigger than V。Okay。

 so without loss of generality， let's assume that the mis report we're talking about v prime is bigger than V。

Okay， so that this is just the statement of dominant strategy truthfulness。When。Your true value is V。

And your mis report is B prime。Now， if a mechanism is dominant strategy incentive of compatible。

 right， like it has to be。A best response for you to tell the truth， no matter what your value is。

Right， like it doesn't make sense to say the mechanism is dominant strategy incentive compatible if your value for the good is exactly $2 right。

 like what it means for the mechanism to be dominant strategy incentive compatible is that no matter what your true value for the item。

 it should be a dominant strategy for you to tell the truth。So in particular， like this is the world。

 this is the statement of dominant， this is the implication of dominant strategy truthfulness when your true value is V and you're considering misreporting V prime。

But you can also consider the world where your true value is v prime and you're considering misreing。

Your bid as V。And that also should be a bad idea if the mechanism is dominant， strategy truthful。

Okay， so let's suppose that。In this know bizarrezaarro world， your true value is now v prime。

 the thing that was previously your misreport， and you're considering whether you should misreport V。

 the thing that in the bizarrezaarro world was your true value。Well， in this case。

 dominant strategy truthfulness requires that。Misreporting is also a bad idea。So。Your value。

 if you tell the truth， your utility， if you tell the truth。

 which in this bizarre world where your true value is v prime is now。V prime times y of v prime。

 your true value for the alternative chosen。Minus the payment you have to make when you report B prime。

Dominant strategy incentive of compatibility requires that this is larger than in this bizarrearro world。

 what your utility would have been for misreporting， which is your true value in this world， V prime。

Times the allocation you get when you tell the truth。Minus the payment you get when you mis report。

Okay， so。This is possibly。But like we're riskly done。

 but let me pause here because even though these are sort of。

These inequalities are both just reading off an implication of dominant strategy and of compatibility。

 This is possibly like。A slightly subtle step where we're sort of saying， look， dominant strategy。

 truthfulness means you're better off telling the truth whether your value is V。

And you're considering misreing v prime or whether your value is v prime and whether you're considering misreing V。

Is that clear？Yep。😊，先はい。That the truth that Im agree that， whether or not。对那。It's not the same。

Because， but like。Note that when you miss report。You evaluate your utility according to your true value。

 you haven't deceived yourself， just the mechanism， but according to a。

According to the allocation chosen by the mechanismchan。So here， like the cross terms here。

 we have v times y of v prime。What happens when you really value the thing at V。

 but you misreport v prime， the corresponding thing here is v prime times y of V。Okay， so these are。

Different statements， but both statements that are implied by dominant strategy truthfulness because dominant strategy truthfulness means it's a good idea to tell the truth no matter what your value is。

Does that make sense？Okay， so。This is the main idea is this step clear？

Both of these things have to be true， the mechanism is dominant， strategy truthful。

So whenever you have like two inequalities that are both true。

 it is very tempting to like add them together like the if a1 is greater than B1 and a2 is greater than B2。

 then like another true inequality is that a1 plus A2 is greater than B1 plus B2。

We've got two such inequalities here， let's just add them up。

And what's going to happen when we add them up？嗯。So the first thing we might notice is that there's going to be some cancellation。

And in particular。All of the payments are going to cancel。

Right it's like because on the right hand side here。

 we have the payment you have to make if you bid V。As if V was a misre。

But on the left hand side up here， we've got the payment you have to make if you bid V here V was the truth。

 but the payment rule doesn't care the payment is the same。The payments just a function of the bid。

So the payment。Terms when you bid V cancel out when you add these two up。

 similarly the payment terms， when you bid v prime cancel out when you add these two equations up。

 which is good because the thing we're ultimately trying to prove is a statement about the allocation rule and has nothing to do with the payment rule right we're trying to prove the allocation rule is monotone。

So it's a good， you know， like it's sort of annoying that。

These dominant strategy truthfulness statements conflate the allocation rule with the payment rule。

 but by adding these two inequalities up， we can't slotout all of the terms corresponding to the payment rule。

And so what's left？Well。We just get that。V times y of v plus v prime times y of v prime is at least v times y of v prime plus v prime times y of v。

Okay， this is what is left after the payments cancel out。And we can combine like terms， right。

 we've got like y of V terms on the left and the right。

 and we've got y of V prime terms on the left and the right。So combining like terms， we've got。

V prime minus v times y of v prime， just aggregating together the y of v prime terms from the left and the right is larger than v prime minus v times y of v。

嗯。And remember， V prime is bigger than V， that was the assumption。

Our initial presumption was your value was V， and you were considering a missed report at a strictly higher value v prime。

So v prime minus v is some positive number。And so we can divide。

Both the left hand on the right hand side of this inequality by v prime minus v。

And what we've established is that y of v prime is bigger than y of V。

And the only thing we started with was the assumption that v prime was bigger than V。

So we've just established that if v prime is bigger than V。

 then y of v prime had better be bigger than y of V， which is exactly the monothicity property。Okay。

 so if you handed me a truthful mechanism。Irrespective of what the payment rule was。

 the allocation rule had better be monotone。So that completes the other direction of the characterization。

Right on the one hand。If you have some arbitrary objective that leads to a monotone allocation rule。

 you now know how to make that truthful。You don't have to worry about thinking about payment rules。

 improving dominant strategy truthfulness anymore， you just need to check monoonicity。

You can look up what the payment rule is。From this slide。On the other hand。

If the thing you want to implement doesn't have a monotone allocation rule。

 if the corresponding allocation rule is not monotone。

 you don't have to waste your time thinking of payment rules trying to make it truthful。

 you now know it's impossible Okay so we've。In some sense。

 reduced what was originally a mechanism design problem。

Simultaneously come up with an allocation rule and a payment rule to choreograph incentives so that people want to report truthfully。

Into what is now like a purely algorithm designed problem。Just design a monotone allocation rule。

Okay， and the mechanism design part is handled by this theorem in sort of a black box way。O。

Questions about that。All right。So in that case， I'll see you guys next time when we'll start putting this characterization to work。

嗯。嗯。Can you quickly reflect on what Monalo need in different context of this？



![](img/7bbda20821d39562631af8376e275c29_3.png)