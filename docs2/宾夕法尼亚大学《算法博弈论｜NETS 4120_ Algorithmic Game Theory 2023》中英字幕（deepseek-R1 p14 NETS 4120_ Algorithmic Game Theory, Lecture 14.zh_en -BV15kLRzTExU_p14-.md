# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p14 NETS 4120_ Algorithmic Game Theory, Lecture 14.zh_en -BV15kLRzTExU_p14-

Okay。

![](img/ac662b9e2b28e75e90710ec6c5e62828_1.png)

All right everybody welcome back from spring break。

 Hope everyone had fun and do whatever you guys do during spring break Now you know life is is real life is earnest the next problem set is asked you've got two weeks and we're gonna to have a guest lecture today by our T George who's way more hardcore than me and even though I offered him my slides see he's going do it on the board so it's a real mathematician no slides in fact I don't really remember what's on the slides so you guys have to help me recover all that knowledge maybe I'll ask some questions and you can like respond with guesses and we'll work it out together。

But yeah， will be more mechanism design today and I guess you know。

 just wondering what was in the previous two lectures。

 like what were the two topics that we looked at， does anyone remember？Okay。

People should volunteer yeah okay go ahead stable matchings was the lecture before the break right or before the exam cool okay and yeah what's what's the rough setup of that problem someone else。

Basically， don't give all the solution concepts or proofs just like what are stable mas about at a high level？

😡，Yep but。Yeah。嗯哼嗯哼。😊，Oh yeah， so preferences are given as rankings over the items right nothing nothing else that we would use to match them up Okay。

 and one lecture before that what was it the first spectrum that can be designed by。

No other than Natalie。Yep。Okay， and what was this setup？Yeah。Yeah。就是万。Yeah， perfect。

Yeah so people come in with their items and they basically start trading until everyone's happy and sort of why both of these problems belong to this like rough area of mechanism design is because we sort of care about。

Maximizing some， you know。Socially desirable things about the eventual allocations。

 so this is different from the game theoretic things that we covered earlier right because the game there was defined in a pretty。

Set in stone way here we have to sort of set the terms of or at least guide people towards like how to like optimally interact with each other to you know retrieve items that they like the most so today we'll talk about。

A market model， not the market model because there isn't a single one， but you know。

 what's like yeah， give me a couple words that are associated in your mind the word。你对我嘅。

What are some related concepts。Nobody in this rough range。Clasroom。Mart buying and selling okay。

 and to buy and sell would you use currency Yeah， money， perfect， perfect。 So basically。

 there's still like some items or goods， right， you want to buy and sell。

 There's still people who are interested in getting those。 So in that sense。

 it's similar to you know， the top trading cycle set that we looked at。

And at the same time it will be different because in the top trading cycle setup up oh that's much better in the top trading cycle setup you know everyone came with an item there's no money involved everyone just you know trades according to the protocol that we give them so the top trading cycle thing right in today's lecture willll look at a different model where money will be a factor so it's not just about what you prefer like what items you want to have it's also about whether you can afford them right in that sense we sort of like get closer to a model of you know a market economy。

Okay， so still mechanism design， but today we'll talk money， right？Okay。

 so what is the model so still we'll have a bunch of buyers and bunch of goods， so we have N buyers。

Yeah。And。We have M。Indivisible goods。嗯。So。And let's call it the setup goods。So。She。

Sos what's indivisible indivisible means that and G you know think of it as a finite set nothing fancy here so G is a set of items and each item can be had by one person or no people so indivisible means that you can't split a single item between two or more parties so that's not an option okay and will allow people to like in the most general setting to each receive one or more goods or perhaps none if they're not satisfied but the prices or the quality or whatnot。

Okay， so let me。嗯。Also give another part of the model to you guys and then later we can add the one more stuff。

Each buyer。Each buyer。Is assumed to have evaluation function。

And this function will be denoted by B and。Once again。We want。

People to be able to get you know no items， one item more than one item， right entire bundle so。😡。

This。Function VI， the valuation will map from SiI。In two。Vineerrals  zero1。

Can anybody tell me like in relation to set G？What's this bundle SI in set theoretic terms baseds on we just talked about？

So this evaluation function for each buyer takes an SI。

 a bundle of goods and outputs a number between01。Yeah， exactly so where。

It maps basically old subsets。Of G right G is finite so old subsets are just like a collection of zero one or more bundles Okay cool so there's that and I mentioned money so to introduce money。

We can very conveniently assume that。Items have prices。Okay， so each item have a price。Or good。Good。

 J has some price。Ass price Pi。Or PJ。Okay。So this is the entire model of the market pretty much。

Now we need to decide on the next step， which is how do we describe the state of the market at any given moment so what will it be like based on what we just defined goods of prices buyers want bundles yeah they can have like one or more items and so on and so forth so yeah what like out of of the things that we just defined like what's the state of the market fully given by。

At any't given points。So suppose all these objects already exist and people you know。

 have like bought what they need， yeah okay。Yeah， exactly so that that's the first part of what determines a state。

 so a zero state。State of market will consist of。sTo allocation S okay。

 and S here will stand for the collection of S I oral I from one through。And okay。

 so that's an allocation。Yeah， and what else do we need to know to know everything about the market out of all these things？

So we need to know the prices， right？The P will be。The entire price vector， okay？

And why do we need to nail the price vector well each buyer has a valuation function so like if the buyer just takes a look at the at all the items and tries you know every single subset the buyer will have some valuation for each of those subsets but this does not include the money yet right so there's also the notion of utility。

Which is。How I like a particular bundle minus what I have to pay for it okay。

That's the last ingredient， hopefully。And okay， so let's do。Let's do five here， actually。

 this is the state of the market。Okay。Each buyer has。A utility and。

We'll consider very natural class of utilities that are known as quasi linear yeah the word quasi has an explanation behind it。

 but you know ultimately you know it'll look linear to you once I write this down so buy's utility。

Is defined as。Ui。Of。一 bundle到。S I。And， you know， the price vector。

And the definition is that we'll take D I of Si the valuation。How happier。

 how much happier the buyer will become by obtaining the bundle minus the prices。

 and it will'll just sum up all the prices over。Alll goods， J and S I。E J。

Does this definition make sense？That cool， yeah。So this is the entire model of the market。😡。

We have states， we have utilities， we have prices。And now there is， there's one， there's one。

Points that we need to make clear right away so the state of the market is described by an allocation and the price vector so the allocation S here what do we know about it we know that each Si is a subset of G right but we also know something else so what else do we know again said theoretically about any given allocation right that assigns a bundle S to everyone what do we know about sort of the relationship between the different Sis as subset of G given this discussion about indivisible goods。

Okay， let's do you in the background。Okay， potentially。

 although there could be goods that no one wants， right， just too expensive or something。

 but yeah that would be a good point okay，s you。Yeah the sets are pair wise thisjoin right so nobody can have any overlap because goods are not shared okay so。

Let us call this。A feasible allocation。😡，Okay， okay， S equals。As I or I am。Easible。Okay。

 and it's feasible if。😡，S I intersect or let's do as J intersect as J prime。Is。

is in fact the empty set for Oj not equal to J prime makes sense right so again we don't require that sV a partition because partitions are required to you know encompass the entire set G of goods right whereas here we allow for the possibility of certain goods just not belonging to any of the bundles but the property that's preserved is that is that each good belongs to at most one bundle S okay so this is all the allocations that we care about。

And once again， at any given price point， any allocation will。

Induce a certain utility value for everyone based on their。

Value of the valuation of their allocated bundle and。

The sum of the prices that determines the overall price of the bundle， okay？Cool， okay。

 so we're doing mechanism design here。What kind of。

Bundles and prices so what kind of market states would we think are desirable from you know a regulator's point of view doesn't mean it will strictly enforce that but you know we'll sort of guide the markets in the right direction so yeah what do we want to happen anyoneep。

😡，Okay， so utility or potentially their valuations right。

 so that's that's a good definition and like yeah let me write down。Okay， welfare。Well， bear。

Maximizing bundle。Social welfare， right？还保。ok。So。Okay， I'll define， I'll define the actual。

Value of the like optimal welfare here instead of the bundle， but so opt will be。The max。

Value over all possible feasible bundles， so as feasible。😡，And the social welfare。

Of a bundle will be defined in a usual way， so for each eye we'll look at V of S and we'll sum all of those things up okay so。

This summation is a social welfare of any。Collection of bundles for everybody among the buyers and then we take the max of the bat over all possible allocations。

好第二人。So good question。If you wanted to optimize for the utility， you' would have defined it that way。

 but if you want to talk about welfare and you want to talk about it in a price independent manner。

 right， then you would define it like this yeah。😡，Okay another reason you might call this welfare values。

It hours。系诶。都。Some tell requires。Yeah so so prices right they they are just like you know part of the mechanism for exchanging your items and so ultimately ultimately like that's why this happens that you sum up you know both the utility of the buyer and you know the people so prices here are just instruments towards achieving the ultimate goal of like matching people up with what they want to have okay so again。

 very importantly this definition is independent of the price vector just depends on the valuations B not the utilities you okay so that's one does at them。

Okay， and what other desirable states of， you know， games have we talked about early in the course。

 what else could be good to haveh？Yeah okay equilibrium right ands and that's a different concept because you know for welfare you know we just want everyone to be happy in in total and for equilibriumria we are asking for a stability condition which means that everyone's happy and no one wants to switch and screw over the current state of the economy right okay so equilibrium and that's cold War raise equilibrium。

All raise in。Equiilium。We。They named after。Lon wrus。So it's a name out of you。

 so that's the difference between the animal and the person yeah。

And this is just one concept right so we're not talking about you know like today's lecture will not you know completely like。

 you know close off the topic right you can have like many such models， but like。

This is one of the most tractable end。😡，Theoretically appealing models and honestly like I've looked through tons and tons of books and everyone like gives like all these like sophisticated methods for computing wall rage and equilibriumria and like to the point where they sometimes ignore like you know what real markets do right so real markets have like much harder equilibriumria happening sometimes no equilibrium at all sometimes in the real world everything's in you know a constant state of flux。

Okay， so。What is this equilibrium all about， So let me give you。Several conditions here。

 the condition。Number one。And this condition is it has some meaning behind it。

 but and it's also like a very useful technical condition to have is that okay， first off。

 an equilibrium is a state right， so an equilibrium will depend on both both。Allocs and prices。Okay。

 so。We will require that any。Item， any unmatched item。Right any item not in everyone。

 not in anyone's bundle item。😡，Item Jenny。Okay， has。Price。EJ。

Equals what's a desirable price to have for unmatched items from sort of like an economic point of view。

啊，The greater than the value that anyone could get from it okay。

 so this is actually so this has its merits it' it's actually the opposite of what we're going to set it to。

 which is zero and the logic behind setting the price of all items that were not taken to zero it's actually that since the price of all the unmatched items is zero right？

The seller cannot lower the price of these items any further right it's already at zero and still no one wants them right so that's the opposite logic this logic however could also definitely make sense okay so this is condition number one condition number two is just technical condition that S feasible。

😡，ok。😊，But like this is not。This is not the main ingredient of course so for the main ingredients yeah i'm forgetting what's on the slide so can somebody help me and sort of propose like an intuitive metric for what's。

And equilibrium state。 So from the perspective of。Any。Individual。Fire。

What would happen in equilibrium？By the nature of equilibriumria。

So like why did we define like Nash the way we did and so on and so forth yeah？Okay。

 stable so from my perspective I'm one of the buyers， what does this stability mean？yeah， cool。

And in fact， we can go even more ambitious here， which you know might sound a bit surprising given that Nash just says。

 okay， you know， you can like profitably do in this that way so。

Will basically require that the bundle that every buyer currently has in this state SP that we want to be in equilibrium state is almost or exactly an optimal bundle that a person could have。

 and in fact， let me say that we are actually defining epsilin。

Will raise an equilibrium Okay so that we don't have to commit to exact optimality。

 So the definition of。Optimality here。It's such that for every。Byer， very good。

Everybody can still see this every buyer。Or can everybody actually see this？

Browund like the third row， fourth row， yeah， cool， yeah。啊。系。😊，So for all， buyers I。We want to have。

The following that the utility。You， I。Of S I。M is。Greater than or equal to what？UI of SI is at least。

 yeah。You buy一世。好。Ui of S I prime minus epsilon exactly so and in fact right。

 so we'll do it max right max over all。S prime feasible。Yes all。Perfect， right。

 so we take the maximum of like。What could be available right or in fact。

 we could literally just say max over O。😡，S， I crime。That's a subset of G， right， whichever you like。

Okay minus epsilon， so we're almost optimal， this is an additive notion of optimality。😡，In fact。

Are you guys lying to me， can you not see this from here？

Always speak up like like yeah if if there's anything that you can't see the best option is to ask me to move it yeah don't just stay silent anyhow okay this is literally the definition of the equilibrium we're going be finding it can you actually see it they're important okay you can see it you can see it everyone can see it cool okay good like otherwise like the rest of the lecture you can just like basically like nap and whatnot and like not here because like that's literally what we're going to be like looking for yeah perfect see。

Beautiful， yeah， yeah， okay。But like yeah， okay， so what do we want to do with this。

 we want to find this right and also want to find this。

 which is the welfare and maxim well okay about it。Yeah。高家。

So utility is sort of like my trade off like i'm a buyer it's like my trade off between like whats I want to have and what I have to pay for it。

 so for a notion of equilibrium it' it's definitely natural to use utilities for here you could。😡。

Again， plausibly consider maximizing the total sum of everyone's utilities。

 but you know this is also a great objective based on like you know what we just discussed like Aaron's point and also that you know it ignores the prices so there's like several desirable things about this right this is literally about you know getting the optimal thing this thing basically makes it almost makes us forget about the fact that prices ever existed is ultimately all we want is to is to get people to be happy right again prices are just an instrument here but for the equilibrium estate prices are a consideration because you know if you end up paying too much for all you like then you better switch out okay。

Good question good question ultimately many of these things come down to modeling right so ask these questions and I'll basically say that it's just a model and we'll move on。

啊。Cral。です的。I think the best way I do this is that both the sellers and the buyers are both buyers。

The buyers， they care about their。没法。The best the buyer is。And buying the bundle that night。はい。

On the other hand， the seller。Aboutit。And so the fact that the unsold item of price zero。

 thats like a best response。The seller if something is not selling and you would still have been happy if it' sold at a lower price keeps a lower price So the only way that seller can be done for negative price to zero。

 And then when we come about welfare and summing up will produce both the buyers and the sellers。

Byはい。These are really delivering to everyone' simultaneously about respond the seller's utility。

The revenue they get and personal health for everybody。嗯。嗯，一。😊。

So is it possible to have two separate？Subss of G where one of them has a higher valuation but yeah potentially like if this is any any concrete buyer can really value like a certain subset you know like like some types of candy over others but they might they might happen to be like very expensive at the current moment in the current market conditions so yeah can definitely happen and itss it's buyer dependent like the trade off between how much you value a certain subset and like the prices is buy dependent the prices are there for everyone but you know your valuations can change so it could be that somebody very rich could actually grab something that's super expensive simply because the valuation is through the roof。

Yeah。对。Yes so theres there's this like implicit seller right and the seller wants to sell these items in fact in fact there are also like other ways to model a market where people come with their own goods almost like two lectures ago but in this model we basically assume that the items are already there and there's a seller who basically wonders about how to set the prices on each of the items to you know make the market equitable for everyone and like the market state to be good right so there's this implicit seller behind the scenes。

And viewss Valley how that Salfactor and this one is a neighbors speaking portfolio。And firstly。被发关。

I understand I close the mechanism that I case the fire in。

The buyer gets their value through the valuation function and the prices is what the buyer pays to obtain the item and those go to the seller which which is like some entity sitting behind the scenes right so buyers get their value through this they subtract off whatever they had to pay for it and what remains is the net utility right by the way it not it's not inversely proportional rate it's like you know。

It's not a division it's like a subtraction so you subtract of what you have to pay and the seller receives all of those prices that collects all the money that the buyers pay right and then what Aaron said is that you sum up all these utilities right for each buyer and each item got sold at most once right and for all items that were unsold the prices zero right so those items are fine we can ignore them and so we sum up all the utilities for the buyers and then the utility of the seller is all the prices collected right so sum of P over all items and then when you sum up those two things together you get you get the welfare。

嗯。😊，不是。Yeah。😊，See， a great question， he' is determined such that we're。

Hopefully here or here or in both of these is good scenarios simultaneously right so our job today is to actually find those prices like find out how to set those prices right and like one way to approach this is a centralized approach right so an economy could just be you know heavily regulated so that as there's some centralized entity right like the party that sets the prices and says you know。

Every single good should be accessible to like every single person and so on and so forth， right？

One way we could do it is we could like solve a huge optimization problem that would like look at like all possible allocations right and like look at all possible ways to set prices to make everyone happy right but we don't want to do that right we are you know we live in a society where。

You know we want to argue that like that's not the way to go in many senses right。

 so instead we want the prices to sort of set themselves if that makes sense。

And right now we'll talk about like what that actually means， right？And by prices setting themselves。

 so。You know， you all can provide input， but like the starting point of that is that if I'm a buyer and I go。

😡，And try to like buy something from the market， then the price of that item that I'm trying to buy should intuitive go up if we were to imagine that like there are copies of items for example right so that's how markets work okay。

😡，That's a way to think about it。The market decides that things that are in high demand should have their prices go up。

Okay so and in some sense， what we'll do right now be sort of we'll describe a way to do this by using a very simple algorithm。

 okay and this algorithm will hopefully satisfy many people in this room and it'll hopefully not satisfy others because it's definitely not the most decentralized way to set prices but you know it's a good and simple one okay so。

So I also forget what the algorithm is， so let me just say。Ag here。

And let me just say that we start with everyone， so we'll have the algorithm will work to output。😡，嗯。

😊，Prices， so PG for all items J， okay， and。Allocs。And the allocations here we use the nottation where new is such a mapping。

That。😡，Or every item。Jy。New of j。Will be。bititter。哎护。As。J， okay。

 so that's what the algorithm will aim to find both an allocation and prices right so the entire state of the market。

Okay， so now I forget what the algorithm is， but。😡。

The intuitive thing that we can do is to set all prices to zero。

 so p equals zero means like every Pj is zero， right？And。New of。Jy is。No one for。诶。All items。Okay。

 okay。And。Let me simplify this problem for us。😡，Valuation so valuation functions as we wrote them down over there are actually quite complicated objects right basically you can have。

Your own valuation for like each possible bundle right so in particular the way we wrote down the model there could allow for things to happen where。

If I just get item one then I have a huge valuation for that， but if I have both items one and two。

 then suddenly the valuation drops for whatever reason right and so this。😡。

Function can hide a lot of complexity if each bundle can have。

Its own valuation in some unrestricted way， right？Instead。

Let's actually assume the following and this is this is not so we've defined like the most general model we could。

 but let's assume the following， let's assume that for each。😡，Byer and each。Item。

 there's some valuation VIj between zero and one that describes how much。

The buyer wants this concrete item。And let's say。To that extent that。For H I and J， B I of S I。

Will be equal to。Some of these numbers VIJ in。0 to one。Okay， overall j that belong belong to as I。

 Okay， so there will be。Number is VIj。Or all I bears Ij， okay？Does this make sense。

 that's a concrete。Model for like how we could view the utility function。

For any buyer and like any subset of the items each item has like a certain intrinsic value to that concrete buyer right could have a different value to a different buyer and then the buyer says if I get two items then I'll sum up their intrinsic value right so that's how you could think about。

Bundlow valuations additively， okay？Does this make sense to everyone？

This is like like the simplest one of the simplest choices we could make。For the valuation， again。

 overall。The model does not say how complex。😡，The valuation functions the I could be they could be like potentially given by like many。

 many， many parameters right and like they could like treat like big bundles and small bundles differently right use different like rules for like how different people value them here will literally assume that there exists so the Ij is literally like n times and numbers such that you know each of them describes for。

By your eye， how much is item J worth， okay？So。But。That's not the end of the story。

 We can simplify this even further， and we can say that buyers are。Unit demand。You at demand。Okay。

 so unit demand。Means that each buyer's bundle。Each writer's bundle。问到。Has。Most one item。

Okay does this make sense so basically no one wants more than one item in some sense maybe like you're you go to a market and you try to buy one chocolate bar right you don't want two because you know that's too much sugar or more right and you can also go home with zero chocolate bars if you want okay so that's unit demand buyers。

😡，嗯。😊，Cool， so。Can anyone give me an algorithm for how to solve this setting。

 see I've simplified it for you guys as much as I could， you know。

 really don't remember like the actual the actual thing。

Let me just once again remind you all that this is where we start from so the seller says oil prices are initially zero everyone is initially unmatched right absolutely no items used so far no competition has happened right so。

😡，like yeah， try to remember what we talked about like roughly like 10 to 10 minutes ago in terms of like the intuition for like how market set prices and like propose maybe like a very rough outline of the algorithm。

 meaning like just a single sentence， what should the algorithm do we started the old price being zero which is the small you know which is like the let's say the smallest they can be and everyone is currently unmatched。

What should we do any proposals？Speak up， otherwise， I'll be sad。Yeah。Yeah。Thank。

So like if there are still multiple buyers for kind the crisis assistance then。

Fers either don't drop off if they don't want to like if they head for it when they stay on。Yeah。

 great right so so like demand determines how how heavily priced a certain item is you over there was that was that what you were going to propose or something different？

Okay。嗯哼。😊，嗯哼。😊，嗯，哼。😊，这系。不。Excellent yeah yeah so so see like together you guys basically like covered some of the most important ideas of this algorithm。

 so basically the seller will you know step away and and just be like yeah。

You the buyers go ahead and bid on the items that you want and I'll give you the items at the current prices。

 but then I'll raise the price in response to the fact that you just got them so clearly you were interested in those items as you're like optimal things right and once again the unit demand model basically says that the bidding will happen you know such that each buyer will you know consider like buying like a single item that's better than their current item okay so it's a very simple setup so out of the two lectures that happen before this one yeah does this does this remind youall of anything。

Any other model that we looked at， unit demand buyers。Valuations， DIJ。For each buyer and each item。

 each buyer gets at most one item。Anything reminiscence of this huh？Yeah。

 stable ma right so so we could intuitively like， you know。

 consider this picture what we have like and buyers and then goods right so there's these like。

Byuyers and the goods。And， you know， there's an option for each buyer to either get matched to something or for another buyer。

 they can like not be matched to anything and you know。There's like something like this happening。

 okay， so it's very related。😡，Okay， does everyone see how this is very similar to the unit demand situation？

Excellent， okay， now my next question is， how is it different。From the stable Mashing setup。

h assume everybody wants to。Okay， yes， so here it's very possible that being unmatched will be the best option if everything that you want to get is too expensive for you to get it excellent okay。

 like but another element of the model that's different between today and you know you over there。

That could be a very useful assumption there here we literally don't care right if if anyone likes chess there's like a ches streamer that keeps saying that he literally doesn't care so yeah we literally don't care okay you。

Okay， good， good， good， okay， so okay， what are you what you're getting at here is that is that the model。

😡，There was， you know， really different in the sense that， you know。

 there we just needed a ranking from everyone now。We have you know a whole lot more going on right now we have prices in particular in stable matchings you could not buy your way into a certain preferable school the way you can you know by your way into a preferable item here so actually matching matching up students in schools was you know the model that we looked at before perhaps did not reflect you know。

Lots of aspects that are inherent to the US admissions system right now。Anyhow。

 so this also could be used to your model some of that stuff so money。Okay。

 so can we use deferred acceptance here， not really because you know。

 we've slightly changed the representation of what we're doing， but okay？So let's now。

 let me raise it。And yeah， since you all have given me so many helpful hints now I actually remember what the algorithm is and now I can write it down。

😡，The some level of detail。What happens is basically while。While there exists， you know and。

And more than epsilent， unhappy。By your eye。Right， excellent unhappy means that their actual optimal bundle at the current prices。

 right which are initially set to zero below change throughout the algorithm， right？

Epsilent unhappy is like a rough term that I use to mean that this buyer has。

Their favorite bundle and that bundle is better than the current bundle in terms of utility by more than。

An additive factor of epsilin， okay， so we'll take any such buyer。Let me just say like。

 while there's this like a buyer I prime， pick any such buyer I。Pick by your eye。ok。😊。

P pick the buyer， that's excellent unhappy。Unhapp。Okay， and。

Let this buyer look at item J prime or J star， sorry。😡，And item J star is the Ag Max。Of。

UI and here I'll have this notation， but most of you won't notice UI of J right by the way。

 how am I at using notation here in relation to the most general model notation when I'm writing UI of J。

What am I abusing here？People do this all the time in like econ papers。

 so right now I'm writing UI of J， what should I write instead to make it compatible with this utility function definition。

 yeah。啊。So's utility right so buyers care about their utility so it is UI right and it is UI in relation to item J。

😊，So it's just a small like notational aspect。So it is morally the utility of I related to J okay like take a look at how UI was defined。

 like what was it defined with respect to。Yeah。嗯。😊，Okay， so first off， I'm leaving out crisis。

 that's one notational fly， very bad。😡，Also S is a set， okay。

 so instead of J I should have written singleton right so just a said that contains J instead I'm just writing J。

😡，Anyhow。Very bad you should always like you know write this down in the prelims that will often abuse notations such that people read it and like they cant get mad at you because you know you warn them that bad things will you know are about to happen Okay。

 perfect and this is arc max over all J okay so we look at all items for that by air and。You know。

 we look at this。And by the way， what will this be。

 this will be basically VIj minus the current price Pj of that item， right？Cool。

And then what do we do， we look at first off， this utility， U I of J。😡，So if you're okay。

 is this utility？Guaranteed to be。Greater than or equal to zero。

 or is it not by how we define the model？Like a priorityi。UIJ。

 this is guaranteed the utility right not evaluation， is it guaranteed to be a positive number？

Well look at a very like desirable item J prime， sorry J prime new I ofJ star， sorry J star。😡。

Is it guaranteed to be at least zero？Or not。They're a simple question， okay。

 does somebody say yes or no and like justify and we can argue over that yeah。

They're potentially more than absolutely unhappy。😡，That not effective。Okay， good， good。

 that's a good reason， but you know， if not if not for that。There could also be you know。

 if this wasn't their favorite bundle or if they weren't like Epsilon happy or something。

 then it could be the case potentially that UI ofJ start could be less than zero right but yeah as you say if that happens you know。

That's probably not for an more than absolute unhappy buyer because they have a desirable bundle。

Okay， so。Basically， if the utility they would get from this J star is greater than zero。

 they will switch and we'll say that mu of j star is I okay everybody remembers what mu means mu basically says that item J star belongs to this fire index by this okay。

And。The price raising aspect。😡，Is that P of J star？Becomes。Or it comes。P of GA star。Plus， epsilent。

Interesting， right？First off this item J star could have belonged to no one。😡。

at which point like its price would be zero because it was never used before or it could already belong to someone some other buyer that' had it so in that case we'll take it away from that buyer and we'll additionally raise the price of that item okay。

Sounds good。So price raising， plus some buyers can become unmatched as a result of someone saying。

 oh， look。Please give me this item like I really wanted like really。

 like that's my like most favorite thing ever， right？Or that's my favorite thing ever， who knows？

Anyhow， you give people what they want and you have to take that away from other people because items are indivisible。

 okay？😡，And the price goes up by Epsilon， Epsilon is a parameter that we can set。😡。

To eventually hopefully converge to。Epsilon walluraria， so it's very suggestive notation here， okay？

So。We have this algorithm。Can someone tell me from the perspective of the items that we have what's true about items throughout this algorithm so initially all items are unmatched right what can we say after or like afterwards。

😡，Yeah what happens to data ofaths initially all items are't unmatched are there any invariance about items and like they're like you know like people put that yeah。

thing us。Exactly perfect yeah pricess never go down so the beautiful proposal that says that prices can be adjusted upwards and downwards depending on what happens in the market here will not make use of you know the ability to drive prices down when it gets sold simply because here will always you know essentially move an item from someone to someone else who wants it even more so here it will make sense to do essentially an ascending price auction okay where prices always go up and moreover every item that gets matched is never unmatched again because someone already likes it。

And in fact， that's someone when they got that item， like it very much at the current price point。

 the most perfect。Okay， see beautiful， so there are some subtle relationships here to the deferred acceptance algorithm。

 but there's also differences， of course。😊，Excellent， okay， so how do we analyze this first off。

 let me remind you guys very suggestively that each VIj。

 so the valuation that everyone could have for their favorite items is always。😡，We doing  zero and1。

 very suggestively。And now let me ask the following question。Does this thing？Converge in finite time。

 so I fix an epsilon， epsil equals 0。1。😡，Will this thing conversion finite time or like has its some potential for divergent？

So keep matchinging people to their favorite items and give items from the take items away from previous owners to give them to next owners and raise prices and so on and so forth yeah。

For increasing the price。或者你个手关关。Perfect yeah yeah prices always go up so Epsilon like it's small but it's not it's not too small right it's some fixed amount we have to commit to it we can't just like say that like epsilon is like infiniteimally small' that's an area that's a different area of math like here we want epsilon to be some concrete amount and you know in roughly one over epsilon rounds each price will reach it's like highest point one at which like no one wants to get it right because the valuations where between zero and1 so yeah。

😡，Perfect， okay。Yeah， let's actually get a slightly more precise bound on the conversion time of this。

So yeah， actually， so I kind of forget what that proof was all about， but one thing that I remember。

Is it says something about。Yeah how many items so how many items out of M items right so someone mentioned that here M is not constrained to be anything in relation to M to n right so we have end buyers and they're doing the smashing process so by the definition of our model how many items will like ever get matched and stay matched consequently。

And buyers and M items， yeah。Up to n items right and each of them has price at most one right okay so we should always like we should always look at when you're analyzing an algorithm we should look either at a potential function or like you know either an invariant or semi invariant right in this case。

 we have this quantity which is who。😡，Some of。EJ or O J in。

Like in the entire set jep right so old prices and all items in market and that thing。Cannot ever。

Go above and。嗯哼。😊，And each round， we raise the price of one of them by epsilon， okay？😡，Hey。

 so someone maybe like from that side of the room。😡，Uh， probably someone who hasn't spoken up before。

 yeah， and someone tell me what that implies about like how many times in total price， you know。

 any price will go up。Implying， you know， that this is， you know。

 the number the like max total number of pronouns that a algorithm will go through。Yeah。

 some of them are like roughly like over here。aga。😡，I remind you that。

In each round one item like while the algorithm still goes on。

 each item gets sold to someone new and its price goes up by Epsilon and also want to reminds you that the total number of items is at most n and the final price of each item is at most one so piece that together and tell me what's the number of rounds maybe you。

😡，是个呀。But perfect yeah yeah n over epsilon right see like I basically like I didn't remember if it's like N over epsilon or N over epsilon squared or something like that so you know yeah now we know。

Right and over Epsilon。Again， to get a sense of the scale， by the way。

 since we're like we used to do like regrets and whatever， yeah go ahead。Okay。It was， it was。

 and then we argued that。😡，The total number of items ever assigned to anyone。😡。

get involved in this process is that most n because each buyer has its most item or one item right and no item ever goes unmatched right and then each of these items has like price at most one so we sometimes them opt get total price most n to reach that price we need to do n over epsilon durations So okay we used to do regrets So is this bound better or worse than n over epsilon squared for example。

Just like a quiz question on your final。Is this bound that we actually got better or worse than this bound。

 which one of these would be betterhu？啊哈。Interesting yes， that is correct so if absolutelyps is 。

1 good you plug it in here that means you get 10 n right but here you would get 100 n right okay so this this is like very useful for like sanity checking your regret bounds and so on and so forth like runtime bounds so yeah。

 but let me raise this to not confuse anyone who's been maybe like you know catching up for something and so this is the actual answer right。

Okay， this is the runtime。On time。Perfect， okay， so we have this nice algorithm and it converges and it drives prices up and so on and so forth。

So why didn't we do this exactly， so what was this algorithm supposed to find for us？😡。

Why did we run this algorithm to determine like prices and like allocations and like when it stops we obviously output the current price vector right and the current you know set of bundles that each buy receives like what is this for like are we just analyzing you know some you know subroutine for something bigger or you know is that it is that we want so what did we want what were our visititerta from half an hour ago yeah。

Exactly， see like you know， because we talked about like 30 minutes ago this you know is already like out of our focus。

 but that's actually what we're working towards right right then I would just show that we can like you know allocate items to buyers and settle on a price vector。

And very clearly when this algorithm is not going anywhere anymore。

 that means everyone is absolutelyps happy right so that's kind of good。

 doesn't that mean that we are the Wal Asianian equilibrium。😡，So can somebody argue this for me。

 semi I informally now I need to write anything down also because you can't you can just say things。

 Yeah， okay， and yeah anyone from this corner that's not one of the people who have answered questions before。

Anyone。So okay， we're trying to find Evaluraian equilibrium right Euraian equilibrium is such a state where everyone is almost happy other than lake。

An epsilent additive factor， additive factor was I mean yeah， additive constant。Okay。

 and we assign people to assign and reassign people to their favorite items until this process converged and everyone's absolutely happy there。

 okay， so what else？We still have two other conditions in the world regime equilibrium definition。

 right， which are easy， but still someone needs to sort of like。Talk through these conditions。 Okayy。

 anyone who hasn't answered before， yeah。我得。Every time you give someone the ability to take away。

Mmhm。😊，Do there any price here set phone here on。And they never get matched right because because when an item gets matched it can't get back to unmatched cool excellent right very easy I just gave you the algorithm and suddenly there's proof that it leads to a oldura equilibrium isn't that cool in particular what what's really great about this is that is that everyone is basically at their most preferred point。

Granted given the current prices right because there its utilities are relative to what the current price levels are right but at those prices that are currently set in stone at the end of the algorithm everyone is almost happy and the degree of like almost happy we said it we said the absolutepsil。

I don't this。はい。对。可以。It' then possible that like item should。保回避。看多。

So here here we said first off here we said that each person is unit demand。

 so no one wants to have a second item， so really the only option at the end of this algorithm could be if someone wanted an unmatched item in exchange for their current item but because we define like an unhappy buyer as a buyer who doesn't like their item at the current price point。

 then it can't happen right so you know you could say like maybe the you know for some buyer like the price of that。

第二意。Oh。Is very， very。Large。But by definition of the algorithm， you know。

 if they still have that item that probably means they they have a very high valuation for item right again could be a very rich person wanting to get a very luxurious mansion right somewhere in Orange County。

😡，Uh， yeah， and like， you know， they could get like another house for free， but like who cares。

 right they have the money， they have the means。Which is reflected in their evaluation， right？Okay。

 perfect， okay， so what have I not talked about like I'm forgetting like I define so many things。

 anything else that we once that we haven't talked about。Physically obtaining。Yes。

 someone who hasn't answered any questions before， this is a very easy question。

 which of the items that we just wrote down on the board， like have we not addressed as of yet？周云。

I'm stubborn yeah， I was just going to keep waiting。We wanted a couple things。

 we got one of them which is the little ratio equilibrium right or an epsilon approximate ratio equilibrium。

 okay？Someone else， yeah。Yeah exactly right maximum welfare okay so do you have a guess of like how we would get it if we wanted to be lazy like let's say don't want to give any more algorithms to you like I already gave an algorithm for computing an epsilon wall equilibrium right。

So if I'm lazy and I want to do like an extra work in that algorithmic direction。

 what will I do right now？😡，Okay， so you're saying you take the Va equilibrium， right。

 and you try to show that is what？Or approximately max right because we just got an epsilon version equilibrium right so the maximum will of course also be like not exactly but approximate right perfect okay。

 that's what we will do。😡，Okay， so so does anyone have any preferences for what to raise here is everyone happy with the algorithm or do we want to keep going with that yeah we probably want to keep going badly because has I still have a point to make about it later maybe this thing I don't know what this is about this was like about like whatever runtime bounds I forget right。

Rising this， everyone happy， everyone knows how long this thing will run for。Importantly。

 does everyone like have a firm grasp on why this thing will at least conversion finite time cool excellent。

 okay， I'll trust you all。So the next lemma will show。Actually。

 let let's say that it's a theorem because it's pretty important and cool right。

 so we wanted a stability condition which called regionian and equilibrium。

 but actually we're also getting welfare maxation for free。Because。Let's say that。

S comma P is epsilin。W Asian。Equiilibrium。ok。😊，Then。S。

Let me actually write this write down the welfare， there are suggest overall virus of the I of SI。

Right where SI is the bundles that。As is formed of。系。😊，Is u most？Yeah， what is it at most？Yes。

 someone， someone give me。Some approximate expression here， take a guess。

So I gave you an apsinable origin equilibrium， which I'm trying to show into that it's also like。

Almost like a welfare maximizing state， so I just wrote down the welfare。

Of the allocation and this equilibrium， right didn't mention anything about the prices。Just yet。

What's on the right hand side， so the welfare in the old equilibrium yep。What minus epsilent？嗯。😊。

Okay， so that's a good guess， but it's a bit it's a bit too optimistic right because it's definitely not like valuations can be different maybe all valuations are like very small so you can't get all the way to one right maybe everyone's values for every item are like01 or something so then you can't get to n exactly but。

Okay， so let me。Let me do Max。Here， okay， can someone complete it now？

The the social welfare in the state S is at least the max。Look over there。

 definition of welfarefa maximizing， yeah。2。Yeah minus something that depends on absolute perfect yeah what's that thing oh max let me call it S prime right because s is already taken as the equilibrium okay max or S prime。

Of some of yeah， VIS prime I perfect right， minus actually the thing here will be。Minus Epsilon n。

Where n is the number of buyers， okay， so the bound will be good。

 but perhaps not as good as you might have wanted it to be okay。

 so if we have 1000 buyers that means that。That means that we want to。哦， that诶对。嗯哼。😊。

If we have 1000 buyers， that means we want to epsilon probably like something like1 like one over 10。

000 right， so we want to get like really close to double ratio equilibrium to make it close to optimal welfare okay？

对。Yeah， yeah， so。This is the whole max thing。This is minus。Epsilent N， okay， cool， Okay。

 so to save time a little bit， yeah， go ahead。Over here。

So what's important to understand is that welfare maximizing bundles right once again we're applying with respect to the valuation fee right so not like they did not involve anything regarding you right so the prices。

😡，Play no role here。 So now you you're I think you're confused because you're saying。😡。

The variation equilibrium that we defined。😡，has use in it right but somehow I'm claiming that we can do something about the total sum of the valuations right so there seems to be a mismatch right right once again like going back to the discussion the beginning of today's class right。

This thing is given through the Vs， which is the intrinsic valuations。

 don't depend on the prices and stability in the W equilibrium case is afforded， you know。

 with respect to the utilities， right？So that means that what I'll show you guys right now will sort of like factor these prices back out。

 right？😡，In some sense， so what I'll do is I'll write out the definition of raising equilibrium for every single buyer and then some overall buyers。

 this is a good technique which you know you might or might not need some homework， but again。

 so I'll write down to theian condition for each buyer I so for all J。Yeah， in fact。In fact。

 each buyer I gets gets their item， right， which I which I call S I， but that's a single item， right。

 So， so S V I of。SI， again， single item here。Mh minus。Okay， fine， okay， I'll do VI of J。

 okay of J sub I。The I of J sub I minus p sub J sub I okay。

 so each I gets J sub I which could could be an item or could be like no item right could be like you know an emptyT item okay so。

This thing is better than anything else they could have had in particular。

Let me take any other arbitrary feasible allocation SiI prime。😡。

Which would basically do the following。You would get V I of J prime of I minus P J prime of I。 Okay。

 so I fixed so fixed。S。Crime。Which is given by J1， J2。

JN right a single item or you know an empty item for each person right prime J prime1 j prime two J prime n right meanwhile S。

 which is the raising an allocation that we are trying to say is optimal with respect to that is just J1 J two。

JN okay， so two allocations， this is the Laian allocation， this is any other allocation， okay。

 and the price vector is set right it's this one。Okay， so I have this happening for every buyer。

 does everyone agree with this， I just like wrote down。😡，They're condition， or they're happy here。

As opposed to any other state， or did they make a mistake there？

Maybe I made like a slight inaccuracy here。I claim that I just wrote down therayian condition for each buyer。

In state in like allocation， like where they get JI as opposed to any other allocation where they get JI crime。

 yeah。Yeah， I did not include the Epsilon， guess what。😡，That's the e here Okay。

 so now what do I promise that I'll sum up over everyone Okay I'm summing up over everyone very useful trick to deal with equilibriumia all buyers I。

😡，And here I'm also summing up all by side to be clear I'm summing up the entire left side and the entire right side right I sum it up a bunch of inequalities inequalality is still true when you sum it up excellent okay。

😡，So。So in particular， the summation still extends to over here， right？M get summed up excellent。

 Okay， so let me rearrange it。And you rearrange it？I'll rearrange you as follows， though。

Some of the eye。JI。Over I。Is greater than some of V。J prime I。Or I。Minus。Excellent N。Plus。嗯。😊，诶不。

And here I'm going to do the price vectors， right？P， J， I prime。Okay， minus。二。J I for I。Okay。So。

Do you doall。Can you all pattern match this and what we're actually trying to show， which is this。So。

 right？This is what we just got by summing up a bunch of origin conditions over all buyers。

 this is what we want to show which basically says that the origin equilibrium allocation is almost the welfare optimal allocation right I just wrote out this goes here。

This goes here and this is an arbitrary allocation J prime right so it's the same as like saying that it's it holds for like the max of our all possible allocations J prime this epsilent N。

And there's this extra term， right？So this extra term， we hope。Is。How does it compare to zero？

下一 time。And why？喂。😊，We're summing up old prices。😡，In the state S。

 which is the World raiseian allocation to PJI， and we're also summing up all prices in PJI prime。

 right？The price vector is the same though， okay， so in both for like were we're comparing two allocations here。

 S and S prime。😡，But the price vector is the same， so the only thing that changes is which items belong to who。

😡，But the summation of the prices， right， if you take it over every bit。

 intuitively shouldn't really change that much， right？😡。

We have a common price vector which is the raisingian price vector right so that price vector determines the prices allocate to everyone and an alternative allocation has prime would just like reshuffle which item goes to whom right so intuitively。

What does that say？嗯。嗯。Very interesting。嗯。Okay， anyone。We have S comma P。Okay。

That's an epsilon world ratioian equilibrium， which means everyone is epsilent at most epsilent unhappy in that current state。

 given the allocation S， which gives them JI to each buyer I。ok。😊。

And I wrote this out to say that for any other arbitrary allocation。

 where everyone gets JI prime instead of JI。They are potentially。Just more unhappy， right。

 other than a factor of epsilent。 And then I summed the unhappiness up。

Over all buyers and I moved things around。😡，And now I'm comparing the sum of the prices。

 PJI prime overall I and PJI overall I。How do they compare？Okay。嗯。嗯h。😊，There any other。Yeah。

 exactly so again， to recap this。We set the prices。

All we know is that from the worlduraian condition。

Everything that's not assigned to anyone in the region equilibrium， right for allocation S。

All of those items have price zero， right， all the items that have non zero prices are matched。😡。

So old JIs you know， together make up like all of the prices， okay？Meanwhile， if you reassign items。

 then either the same items get reshuffled and all items that have zero prices are still left alone right。

 or we leave out some items that are priced above zero and bring in some items that are priced as zero。

 okay？😡，Does that make sense？That is actually where the conditions that all unmatched items in the origin equilibrium have pre zero come in。

So like those items are not desirable and in particular。

 if you fix the prices and do like any other allocation。

 then the total price paid to the seller of that allocation could only drop if we accidentally leave out items that had non zero prices yet。

So what happened here， which is a miraculous thing is that when we talked about welfare maximizing bundles。

 we just talked about bundles and valuations， right？

We didn't talk about prices prices could be anything right we just want to look at the final allocation and look at how happy people are without taking into account their like prices right that made them get to that point mean welluraian Eria do require us to reason about prices。

 but we summed up a bunch of eurasian conditions over all buyers。

And the entire thing with prices went away， right？So this thing， this thing completely went away。

Prices canceled out and disappeared essentially because of the condition that every unmatched item in a low equilibrium had price exactly zero。

Eventually， whether we conclude to your question， we conclude that the Eurasian equilibrium allocation。

Is almost the optimal allocation regardless of what the prices were that took you there。😡。

Eration equilibrium is。A twople that consists of the allocation and the prices so the prices think of them as like a technical tool to get us to the right allocation and so what we showed which is a pretty cool thing is that。

 you know we got to an optimal allocation by using some prices and how did we set those prices well if we use this algorithm to get to the Epsilon origin algorithm then that's how the prices were set right so these prices got us there to some allocation and then we took that allocation and said well you know here where the prices but you know at these prices comparing our allocation to any other allocation。

Cances out the prices and then what comes out is a statement just about the valuations and the allocation。

 okay？So that's a very cool fact， in fact。One of the main takeaways besides this algorithm of this lecture。

Is this link here？😡，ok。😊，Yeah。If we have an epsilon， we'll raiseian equilibrium。😡。

Or rather actually this link right so I didn't show that if you have a well for maximizing bundle that it's also an equilibrium bundle right but what I did show is that if we get stability we also get approximate optimality right so epsilon origin equilibrium。

Translates into an excellentpsil N， approximately best。😡，Allocation in terms of welfare。嗯。😊。

Great question right so we assume unit demand this algorithm which got us to raise in equilibrium assume unit demand now when we proved that equilibrium implies welfare maximization。

What we did here did involve the JIs， but if you' later show the slide。

 you'll see that that calculation。😡，Actually does not need to assume that we are unit demand okay that calculation holds even when buyers can have different like various items in their bundle right so we could replace your JI by S and J prime I by S prime I okay so the fact that we'll raise an equilibrium andly well from maximization is still good okay so the only thing that's not good is the algorithm and then the remaining couple minutes let me tell you what to do when we don't have this crazy restrictive unit demand condition in particular maybe like items in the market are heterogeneous right which means that it's not like we don't just need like one chocolate bar maybe we also like get like other stuff right at our local grocery store okay so their unit demand will not work because we need chocolate bars and we need sanitizer and like you know we need something else lotion。

 who knows？Okay。So what matters here？😡，Yeah， actually what mattered here what mattered here。

 how do we use the unit demand condition that everyone can own at most one item。

 like give me like a way for how this was used。😡，That everyone can own at most to one iT。

 like why was this useful？啊。这个啊这个。可。嗯m哼。😊，嗯哼火啊。Excellent， okay， there's end end let me give you。

 let me give you the definition of the most general types of demands for which we can also here that so it be called gross substitutes。

Substitute。Okay， so gross substitutes means the following， so consider two price vectors。He。😊。

And p prime okay two price vectors what do I mean by you know one vectors less than equal to another vector that each coordinate of this vector。

 each price Pj is at most price Pj star for the same item in the other price vector right so prices could have only gone up which is in fact true throughout this algorithm right each price like individually goes up for each item so price vectors can only grow in the sense okay so。

Let's consider any buyer。So and this property is a property of gross substitutes so like V I satisfies this property。

 so for every eye。Let's consider their best bundle。S prime or S star。Here in the in vector P star P。

Okay， so this， this bungo has a bunch of a bunch of things in it。 So the things in particular are。

Some items， right， maybe like， you know， like a bunch of Js， right， I kind of know J，1 I2 I。

Et cetera。ok。😊，So now some prices went up and some prices stayed the same so we got to P prime。

 so now you have S star。P prime。And I'm assuming here that there's like a single unique。

Optimmal bundle for everyone right but of course like usually like it could be that it's a couple of them of them like having like the same value right？

So。Here I'll just assume that the a max contains a single one Okay。

 so what do we want about this SP prime star？We want it。To only expand。So we still want to have。S。

Star P。Union。Some more items。Thank。What that means。Is that prices go up。

 I consider any concrete buyer that buyer has these items and that buyer now says actually prices have gone up so now my optimal bundle has changed。

 right？😡，It would be a pretty bad scenario for us if that buyers suddenly wanted to switch to another bundle where some items would be dropped。

 let's say right so really what we want and what gross substitutes and this is the property right of the valuation functions right here the unit demand valuation functions says that it only values at most one item to like some extent gross substitutes includes that and more potential valuation functions of this kind right？

So this property gross substitutes was important here， in fact， the same algorithm。😡。

Will be cool again。😡，All that's changed is that now everyone can have like an entire bundle of favorite items。

😡，But because of the gross substitutes condition。Those items that were in that bundle can stay there。

😡，And more items can be added on， right？Okay， so that that's the slightly finer point。

 which basically says okay you demand made it easy。

 but we can also go more general and maybe like on some homework we might ask if the gross substitute condition you know is satisfied for like some other class evaluation functions or not。

 exact definition will be in the slides to double check right。

 but one way gross substitutes useful mechanism design is it allows us to extend simple algorithms that we initially derive for simple things like I want that most one chocolate bar too。

More complicated bundles and more complicated valuation functions for the bundles， okay？Cool， okay。

 so to summarize， we went through went over a market model and we showed that we can do welfare maximization and equilibrium all at once by using a relatively simple algorithm for a relatively simple class of evaluation functions and what we briefly mentioned is that you know some more complicated valuation functions basically required the same algorithm。

 but slightly adapted okay。Thanks。嗯。