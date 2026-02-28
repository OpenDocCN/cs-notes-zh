# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p12 NETS 4120_ Algorithmic Game Theory, Lecture 12.zh_en -BV15kLRzTExU_p12-

![](img/d6a77a0e9165ddd15a3eb485a48942f8_0.png)

Alright。So let's begin。And first， I just want to remind everybody that the midterm is next week。

 I was announced on Piazza some time ago and and hopefully everyone is。

Ready and studying it's going to be。Asynchronous can you can take it whenever you want。

 it'll be timed so as soon as you start taking it， you'll have 90 minutes to complete it and you can you can finish it at anytime between next Monday。

 I think it goes live midnight， Eastern time and next Friday。😊，U。

And we're going to cancel class on Tuesday， so for example。

 you can use class time to take it if you want。So before we begin， any questions about logistics。

 midterm， things like that？Okay。Is that a question？

So this is sort of the halfway point in the class and we're going to。

Switch gears from game theory to mechanism design basically starting today。

So up until today we've been studying game theory， by which I mean， you know。

 we've been like taking games as given， you know， someone hands us a particular zero sum game defined by a matrix or a particular congestion game and we've been trying to think about。

😊，How people， how rational actors might behave in such an interaction。

 we've been trying to make predictions that they will play， you know various kinds of equiria。

 national equilibriumria， correlated equiria， and we've been trying to justify those predictions by sort of thinking about whether there are computationally plausible dynamics that might get us to those states。

😊，So。Mechanism design you can sort of think of as reverse game theory in that。

The problem setting might specify。You know what people's ultimate utility functions are。

The rules of the game will not yet have been defined like their action set won't have been defined and the mapping between the action set and the outcome that they that they're going to ultimately care about won't be defined and。

The， the sort of。Thing to do to solve a mechanism design problem is to。

Design the game to design the action set， to design the mapping between actions and outcomes so that when players behave as we predict that they will and that we've now developed。

 you know， a large collection of tools to。😊，Predict what people might do in a game。😊。

The premise of mechanism design is to design the rules of the game so that when people behave rationally。

 they will achieve the goal that we set out。And we're going to start by studying。😊。

Sort of a simple problem。 And it's it's。You know， got sort of a fanciful premise。

 the house allocation problem， that's got a nice algorithm for it。😊。

But I want to point out that even though this is sort of a simple problem with sort of a fanciful premise initially。

😊，This is actually。An important problem related to how kidney exchange is currently carried out。

 and I'll talk about that briefly。And in particular。

 like we're going to solve this problem by deriving and analyzing the top trading cycles algorithm。😊。

Okay， so what is the house allocation problem？And this is。

Called the house allocation problem because that was how you know， Chapleplain and Garcarf。

 who were mathematicians originally defined it and they were sort of being。

know a little bit facetious， this is not how housing markets work， but we'll talk in a moment。

 this is actually roughly speaking how modern kidney exchange works。😊，So the premise is that。

You've got these different individuals。Who each already have some good cha and scarf called it a house so so let's you know we can call it a house as well Okay。

 so everyone shows up to the market and they have a house， their own house。😊。

But they have preferences over all of the goods in the market over all of the houses so your favorite house might not be your own house right you know and my favorite house might not be my own house and in particular there might be gains that could be made from trade right like if you prefer my house to yours and I prefer your house to mine。

 then we would both be strictly better off if we if we traded。Okay。

 so the you know the premise is everyone shows up with some good and they've got preference orderings over all of the goods in the market。

😊，And。So this isn't yet a game right， like there's no like actions yet。

 but our goal is to turn this into a game to design some game that the players can play that will involve exchanging goods。

😊，So that。Both， we can facilitate the coordinate the exchange of goods to arrive at some good allocation。

 some higher quality allocation than the one we started with。

 and we're going to have to talk about what that means like what a good allocation is。

And do it in such a way so that it is a dominant strategy for everyone to report their true preferences。

Okay， and just let's sort of think about this for a moment。You know。

 suppose I propose an algorithm for solving this problem。

 so you will report something to the algorithm like you will report to the algorithm your preferences over outcomes。

Okay over goods that you might receive and as a function of everyone else。

 everyone's reported preferences， I will mediate some allocation。

 I will say okay you know here's the exchange that's going to take place and in particular here's the good that you are going to get。

😊，AndAs soon as I do that， I've defined a game， your action set is the set of preferences that you could report to the mechanism。

 you could report your own preferences， but also at your option you could lie。

 you could misreport your preferences if that's beneficial。

And there's now a mapping between these actions and outcomes right when everyone reports some set of preferences。

 the algorithm is going to choose some outcome。😊，Okay， and you have preferences over outcomes。

 which you know， which good， which house you receive。

And so you know as soon as we specify some algorithm。

 we've defined a game and our goal here is to design a game so that in the sense we've been talking about this whole time。

😊，It is a dominant strategy for you to report your true preferences。

And let me just sort of point out why it is important to achieve both of these goals right and this is really what's going to separate。

Mechanism design from algorithm design right right so algorithm design。😊。

So of corresponds to just achieving the first goal。

 we want to design an algorithm that will somehow given inputs produce a good output。Okay， but。

In a mechanism design problem， which is really an algorithm design problem in a strategic setting where the inputs to the algorithm are going to be chosen by strategic agents who could misreport their own。

😊，Preferences their own input， you know， their own part of the input to the algorithm of doing so is beneficial to them。

U。😊，A mechanism design is different because if all we do is we design an algorithm that given its inputs。

 somehow compute some good allocation， some high quality allocation。😊。

As measured with respect to the inputs， then we actually have no idea whether the allocation that was computed was good。

 was high quality with respect to the actual underlying problem instance right because the underlying problem instance is not necessarily what is given to the algorithm right the agents have the agency to misreport their preferences to the algorithm if that's beneficial and so if all we're doing is solving the problem instance we're given but we haven't designed an algorithm then incentivizes people to report their preferences truthfully。

😊，Then we might be solving the wrong problem instance， and therefore we might be fooling ourselves。

 right， you know， even though we've come up with some。

You know with some solution that is good with respect to the specified inputs。

 it might in fact be bad with respect to the true unknown input。😊，Okay。

 and that's why we want to be able to design mechanisms that actually incentivize people to report their preferences truthfully so that we can be certain that the good allocation we came up with。

 you know， since we you know， did solve the algorithm design problem in particular in part one。

 actually is a good allocation， not just for the reported instance of the problem。

 but for the real instance of the problem because in particular people report truthfully。😊。

Does that make sense？嗯。So good time for questions about that。 if it doesn't， because this is sort of。

Basic principle of mechanism design we're going to be working with for the rest of the semester。

it's algorithm design where。We don't have the luxury of assuming that the instance that the algorithm is given is the correct one。

 we have to actually work to incentivize people to report to the correct you know instance of the problem to the algorithm。

A little confused why if the algorithm is trying to give you your preference， why you would ever lie。

 like regardless of what the algorithm actually is。Yeah， so the algorithm is， yes。

 so that's a good intuition and。Sometimes it's something we can use to。

Actually achieve dominant strategy truthfulness， but the basic problem is。😊，You know。

 even if the algorithm， so first of all， you know， there's this。

Premise that the algorithm is sort of trying to give you the thing you want。

 which is not necessarily justified in all settings right the designer of the algorithm might have goals that are different from you。

 for example in an auction setting， the designer of the algorithm might want an algorithm that generates high revenue。

 which is not necessarily aligned with you know your interests。And second。

 even if the goal of the algorithm designer is broadly aligned with the interests of the participants。

 like maybe the goal of the algorithm designer is to maximize social welfare。😊。

That does not necessarily mean that。The goal of the algorithm designer is perfectly aligned with your particular interest right because you know you in particular are interested in maximizing your own welfare and that's not necessarily going to be obtained by maximizing social welfare right like you know it might be in this case that the good that is your favorite is also my favorite good and it can only be given to one of us and the algorithm is going to choose somehow to give the good to you know me or you or maybe somebody else and you know right no matter what happens there's somebody who's not going to get it and the question is could they have misreported something so that they would have gotten it and if so then the mechanisms not dominant strategy truthful and that's sort of the。

😊，U。😊，Problem like if somehow the algorithm was able to simultaneously give everyone their absolute favorite choice。

 then you're right， it would be like pretty easy to show that such an algorithm was down in strategy incentive compatible like why why should you lie to the algorithm if it's going to be trying to give you your favorite choice。

😊，The problem is， you know， like as always， in game theory。

We've got these like an agents you know whose goals are not all compatible with one another right we might all agree on what's the best object。

 but like only one person can get it。😊，And so the algorithm is not going to be able to pick an outcome that is simultaneously everybody's favorite choice。

 and that's where the issue comes in， does that make sense？Yeah。Oh is 3。

2 under the assumption that like all the players have like know how the algorithm works。

 I guess there's no like obfuscation between what the algorithm is and what the players know about the algorithm so as if like they know what how the algorithm is going to work and even if they know they will not change their preferences。

To something else so that they can get something better than what they would have gotten and if they didn't know。

If that means right so so we're going to be operating under the assumption that everyone knows what the algorithm is you know。

 if there's like uncertainty about what i'm going to do then you know it's hard to you know you right like what is our rational agent going to do well you sort of have to in that case specify what exactly they know you know so they could have some。

 you know like beliefs about what i'm going to do like with uncertainty but that。You know。

 both would complicate things and would。Make our predictions a lot less， a lot more brittle to。

 you know， like the difference between what we think they know about the algorithm and what they really know。

 So we're going to be。Sort of。Operating in the setting where you know like the actual algorithm we're going to be running the mechanism is public and that's the common setting like typically if someone's running an auction it doesn't have like secret rules and they only tell you what the rules are after the outcome you'd be suspicious if only after bids are in I sort of decided who the winner was and what they'd have to pay using secret rules that I hadn't revealed to anybody like at any reasonable auction everybody knows upfront what the rules are。

Does that make sense？Yeah， that does。Okay。Okay。So。When Chapl and Scarf wrote about this。

the was house exchange， but of course this is not how housing markets are run。😊。

In particular like the setting is sort of describing like a barter exchange market like I haven't mentioned money at all。

 you know people are like just trading goods and like in general money is a good way to mediate markets and in fact。

 you know like in housing markets。😊，As in many other things， we mediate them using money。

 you put your house on the market， you there's some， you know。

 market price's that's established informally。😊，The buyer gives you money and then if you want another house。

 you can trade that money for a house and fortunately you don't have to like find somebody else who would like to you know move to your city who has a house in the city that you want to move in and you know work out a barter exchange。

😊，But there are things that actually do work that way and sort of I think the most important example is paired kidney exchange。

So。😊，In the United States， at least。😊，First of all， kidneys are important。嗯。You know。

A long waiting list of people in line for kidney transplants。 you know， like there's more。

People who need kidney transplants， then there are kidneys available and people die every week waiting for a kidney but。

It's also an unusual organ in that。Most people have two of them and they only need one and so you can have live donors so you know if you need a kidney transplant。

 then you might be able to find someone who's willing to donate their kidney to you。

Now not everybody can donate a kidney to you， you know there's blood type compatibilities and even if you find someone who has a compatible blood type sort there's there's sort of more complicated protein match compatatibilities so it's actually like kind of hard to find a suitable donor。

You know if even if you have someone who's willing to sort of undergo the。

 you know ordeal of donating a kidney to。And。Because of this， there's sort of a natural。

There's an inefficiency here， which exchange would naturally resolve。Right， so。

You might have somebody willing to donate you a kidney， but they cannot because of， for example。

 blood type incompatibility， I might have someone willing to donate me a kidney。

 but they cannot because of blood type incompatibility and maybe。You know。

 your donor is compatible with me and my donor is compatible with you and so you know perhaps perhaps we could arrange an exchange。

Now。In principle， this is the kind of thing you could also mediate with money。

 like in a in the housing example， you could imagine a society in which。😊，You know， like。

We could raise money you know either your donor could sell their kidney on the open markets and and my donor could sell their kidney on the open market or maybe I just have some cash lying around and then we would buy each other's kidneys。

 but in the United States and in many other countries that's illegal so it's illegal to to。

Pay money basically or anything else of value for organs。And so。😊，Because of this。

 sort of standard market solutions fail， but there's an opportunity to save many lives with effectively markets that are able to coordinate these kinds of exchanges and that's exactly what happens so in fact the sort of algorithm we're going to talk about today is used in paired kidney exchange and the premise here is that sort of the individuals coming to market are pairs of people。

 one of whom needs a kidney and one of whom is willing to donate a kidney。😊，Okay。

 so the good that is coming to market is a kidney and sort of the individual here is actually a donor patient pair who are incompatible with one another。

😊，And the preferences over the goods are determined by things like blood type compatibility and sort of finer protein profile compatatibilities。

And it's important to be able to coordinate exchanges of this sort without using money because it's illegal in the US and this is done so there are thousands of paired kidney exchanges in the US every year you know saving thousands of lives using basically the algorithm that we're going to talk about today。

😊，Okay。But for the rest of the lecture， we're going to talk about houses instead of kidneys。

So here's the market。Here's the model。So we've got n agents and we're going to denote the agents by P and each one comes to market with some good H and so you can read this as you know house I。

And。We're going to be talking about a setting where agents have ordinal preferences rather than cardinal preferences。

 So rather than talking about like utility functions and like the utility that you would have for each house。

 we're going to represent your preferences just as。In ordering， okay。

 so you have some strict preference ordering you know player eyes， strict preference ordering。

 we will write like this。Over all of the goods， okay so you know， if we line up all of the houses。

 you can rank order them from your favorite to your least favorite and in general。

 if player I prefers house J to house K will denote it like this， which you can read as you know。

 I guess just player I prefers house J to house K。Um。

And the fact that it's a strict preference ordering just means that for a repair。

 either you prefer J to K or you prefer K to J， there's no indifferences。Okay。

And this ranking you know includes your own good Okay， so you know， it might be， for example。

 that you actually kind of like your own house and maybe it's not your absolute favorite but。😊。

You prefer your own house to many of the other houses on the market。Okay。😊，And。Our goal is， you know。

 stepping into this setting to design an algorithm which will induce a game。😊，Okay。

 so our goal is to design an algorithm， What are the inputs to the algorithm。

 Well the inputs to the algorithm are the preference orderings and agents will each have。😊。

Some preference ordering and they will submit those as the inputs to the algorithm。Okay。

 what's the output of the algorithm， the output of the algorithm is the allocation。😊，Okay。

 everyone came in with a good， everyone's going to leave with a good。

 but it might be a different good Okay， so the output of the algorithm。😊。

Is some matching between agents and goods？Okay。Now， the agents have preferences over the goods。

RightAnd so， of course， they have preferences over the outcome of the algorithm。

 which is going to give them a good。And so because because we have this algorithm mediating in exchange。

 taking as input preferences and outputting and allocation of the goods。

 when we specify an algorithm， we induce a game。😊，The action space in the game is the set of all preferences。

😊，That an agent could report to the mechanism。And their true preferences specify their utility function in the game right in particular。

 that， you know， they true preferences for every。😊，For every set of actions of their opponents。

specifyify a preference ordering over their own action set because every action they choose will result in some allocation and they have preferences over these allocations。

😊，Okay， so once we specify an algorithm， then we can start talking about。😊。

The resulting interaction as a game。And our goal is to design an algorithm that not only comes up with some good allocation。

 but。😊，Induces a game such that it is a dominant strategy for every player to report to their true preferences。

Does that make sense？Okay。So。We've said a couple times now that we would like to induce a good allocation and so what does that mean like what is a good allocation and。

😊，You know， we're basically going to ask for something pretty weak here。

 which is that the allocation shouldn't be bad。 so let's define a bad allocation。

And informally speaking， we will say that you that an allocation is bad or Pareto suboptimal。

 if it is possible to make everybody happier， okay like if it's possible to make everybody happier compared to。

 you know， the allocation I suggested， then my allocation is bad in the sense that， you know。

 there is nobody， not even one person who prefers that allocation over some other one。Okay。

 so in particular， we will say that some allocation mu is Pareto suboptimal。😊。

If there's a different allocation， new。😊，Such that。😊，For every single person。

 their output in new is at least as good as their output in new。

 so there's nobody who strictly prefers mu to new like at best， you know everyone's indifferent。

And there's at least one person who's not indifferent， okay， there's at least one person J。

 such that they strictly prefer their allocation and new compared to their allocation in Mu。Okay。

 so we say that。An allocation is Pareto suboptimal。If there's some other allocation。

Which we say Pareto dominates it。If there's some other allocation that Praer dominates it。

 which means that in this other allocation， there's at least one person who's strictly better off and there's nobody who's strictly worse off。

😊，Okay， so if we sort of， you know， had a vote like which， among all of the N agentsent。

 which of these two allocations would we prefer， there's， we could get consensus。

 we could get consensus on new instead of mu because there's nobody who like actually strictly prefers mu to new。

😊，Okay， right。Everyone can agree that we。Should not output a Pareto suboptimal allocation。

 everyone would be happy to vote for a different allocation with which Pareto dominates it。And。

If an allocation is not Pato suboptimal， then we'll say it's Pato optimalmal。Okay， and our goal here。

 you know， our sort of weak definition of what a good allocation is。

Is to just output something that is preto optimal， something that's。Not。Really bad。

 something that you know， at least is not possible to simultaneously improve on for everyone。

RightLike if we're at some Pato optimal allocation。

 it might be that I personally would prefer some other allocation。

 but I'm not going to get consensus on that because if we move to some other allocation。

 there's got to be someone else who's strictly worse off。😊，Does that make sense？Okay。

 so we've defined sort of our。Weak notion of the quality of an allocation。

 let's now talk about incentives。And。Quite frequently in mechanism design problems sort of as a minimal requirement you will ask for what is called individual rationality and here's what individual rationality means in this case。

 but in every mechanism design setting there's sort of a similar definition。😊。

An individual not rationality basically means that。You know， you can't be harmed by participating。

Right， like in this case， it's sort of saying。Well， you know， no matter what your preferences are。

 okay， and no matter what other people's preferences are。At least if you tell the truth。

 if you report your true preferences to the mechanism， then I can promise you that。

You're going to be allocated something that you like at least as well as the thing you started with。

Right like the thing that you wouldn't want is that， you know。

 you come to the market with your house， you like， you know。

 agree to participate in exchange mediated by this mechanism and then like you are given a house that you like less than the one you started with and you a kidney that you like less than the one you started with would be even worse。

Okay， and like if you designed an algorithm that had that property。

 you wouldn't be able to get anyone to participate in it。😊，Okay， so you know like。😊。

Mechanism design problems are。M， if you didn't require individual rationality。😊。

You could sort of often get truthfulness just by like threatening people right with violence or something right but the problem is you wouldn't be able to get people to agree to participate in your mechanism。

😊，Okay， and so we're going to want to get dominant strategy incentive compatibility in a way that。😊。

Also guarantees that people can only benefit from the participating in the mechanism compared to not participating and that's what individual rationality is guaranteeing that sort of in the worst case you will like walk away with your own house。

 I'm not going to like give you like a worse good than the one you started with。Okay。

 has this condition clear， is a very weak condition。

 but you'd hate to design a mechanism that like didn't satisfy this because then you'd find that you know。

 when you launched your app or whatever you had no users。😊，Okay。And once we have this sort of。

Weak individual rationality condition， which really just means you know it's like safe to participate。

😊，We're going to ask for this stronger condition， dominantance strategy incentive compatibility。

 which。😊，Guarantees not only that people should be willing to participate in the mechanism because they you know can only gain。

 they can't lose， but actually that we can actually trust the reports that they make to the mechanism because when viewed as a game。

😊，It's a dominant strategy for people to report their true preferences。

You knowIf you remember dominant strategy， truthfulness is sort of the。You know。

 game theoretic prediction that required sort of the fewest assumptions on rationality like if something' is a dominant strategy。

 you should really play it， you don't have to think about you know who else is participating in the mechanism。

 what they might be reporting， like you know you know that no matter what， you know。

 no matter how those things shake out。😊，Like your best response as always to report truthfully and so if we can design a mechanism that's dominant strategy instead of compatible。

😊，We have really good reason to be able to trust that the inputs that are represented to the mechanism really do reflect the true preferences in the market。

Okay。So dominant strategy incentive compatibility just asks that in the game induced by the mechanism。

 truthful reporting is a dominant strategy and just to sort of。😊。

Reate in this setting what specifically that means， what it says is that for every player I。

No matter what your preferences are。No matter what everyone else's preferences are。

 and no matter what deviation， you know， what misrepresentation of your true preferences you might consider reporting。

If I consider the allocation that will result， if you tell the truth。Okay。

 the allocation that will result from the mechanism。

 if you tell the truth and everyone else reports whatever they're reporting。

And I consider the other allocation that you might be able to obtain by unilaterally deviating to misrepresent your own preferences。

 okay？Then。Again， in all of these cases， you prefer you will prefer the good that you get。

In the allocation that results from truth telling compared to the allocation that you would get if you misrepresented your preferences。

Okay， so because of like all of these universal quantifiers， like whatever your preferences are。

 whatever other people's reported preferences are。😊。

Whatever clever misrepresentation you're sort of like considering， you know。

 thinking about in the back of your head to report to the mechanism。

It's never a good idea like you're always better off telling the truth than lying。Okay。

 and this is nothing more than the requirement that the the game that is induced by the algorithm。

 the mechanism that we deploy should make truthtelling a dominant strategy in the sense that we've been talking about this whole class。

😊，Okay。😊，So how are we going to solve this problem， Here's you know a page full pseudo code。

 but it is a very simple algorithm。 Let me just you know before we try to like parse this。

Massive code let me just tell you how it works。So， imagine。That the end agents are are you know。

 standing in a room together。 Okay， they've all like come to some physical marketplace with their good。

Okay， so you here you are standing in this marketplace， you can look around and。😊，You know。

 there's the end goods in the market， a array in front of you。

 remember you've got preferences over all of them。One of them is your favorite good。Okay。

Point to your favorite good everyone's going to point to their favorite good Imagine peoples you know the algorithm is going to construct a graph。

 but like imagine people like physically pointing to their favorite good Okay。

 so we have these end people in the markets and each of them is pointing to exactly one good。😊。

Okay now。😊，Some of the goods might be very popular right there might be some good that has you know 10 people pointing to it and if the good that you have by the way is already your favorite good。

 then you can point to yourself。😊，Okay， so everyone's pointing to their favorite good。😊。

What this is inducing， really， is some graph。In which the vertices correspond to people and every vertex has one edge outgoing from it right the edge is where you're pointing。

😊，And what the algorithm is going to do is it's going to look for a cycle in this graph right if we can find a cycle in this graph then that's sort of a potential trade right if I'm pointing at you and you are pointing at me。

 that means that there's a mutually beneficial trade we can work out amongst the two of us right like you know you can have my house and I'll have your house and we'll both be happy because these are both our first choices。

😊，And in principle， like we don't have to look for cycles of just length two。

 right I could have a cycle of 10 people， you know we could all give our goods to the person pointing to us in this cycle and everybody in this cycle would be happy with this allocation because everyone would be getting their first choice。

😊，Okay so that's what that's what's going to happen we're going to like look around for a cycle and if we can find a cycle any cycle。

 we will clear goods along that cycle， meaning in that cycle everybody will get the good that they' are pointing to and because it's a cycle everyone's happy right like there's nobody like if if I have to give my good to someone else that's only because I'm getting a better good。

😊，Okay， so we're going to clear goods along the cycle。

And those people are going to be removed from the market because they've already cleared。

 they've gotten their favorite good。😊，Okay， so suppose we find a cycle of length 10 initially now now there's sort of 10 people who are cleared。

 we're going to remove them now there's n minus 10 people left and we're going to do the same thing。

😊，Okay， so everyone's going to look around and they're going to point to their favorite good amongst those that are remaining。

😊，Now there might be some people whose favorite good was amongst the 10 goods that were cleared in the first round and so their like absolute favorite goods are no longer in the market right but that's okay。

 they're going to point to their favorite good amongst whatever's left。

So some people might now be pointing to their second favorite good。

 but it is the favorite good amongst everything that's left。😊。

And we're just going to repeat this process。 Okay， we're always going to look at。😊。

This graph induced by everyone pointing to their favorite good amongst everything that's left。

 we're going to clear trades along cycles and then we'll update the graph because when we when we remove goods from the market。

 some people， you know anyone who was previously pointing to that good but didn't get it is going to have to update where they're pointing。

😊，And we're going to keep doing this until until。Until nobody's left。Okay。Yeah， the pseudo code。

Is just。Explaining a little bit more formally this process。Okay， so we're going to maintain。U。😊。

The set of people who are still in the market， we're going to call it S right S1 is the set of people initially in the market and SI will be the set of people in the market at Ro eye。

And initially it's everybody。Okay and while there are people still in the market。

 we're going to construct this graph， which is just the graph that is induced when everyone points to their favorite good okay。

 so the vertex set in this graph it's just the people who are still in the market and there's a directed edge in this graph from person I to person J only if good J is personized favorite good amongst all over the remaining goods。

😊，Okay。Then we're going to just look for cycles in this graph and we will clear trades along it。

 which just means if person I is pointing to good J， right IJ is in the headet。

 then person I will be allocated good J。😊，And then we're just going to update the bookkeeping。Okay。

 so we're going to remove from the set of active agents from the set of agents in the market。

 anybody who was involved in a cycle that was cleared this round。😊，And that's it。Okay。

 so I think I'm pretty intuitive。😊，Algorithm， are there questions about it？Yeah。

 how does this guarantee that you'll end up with a house that's better than the one that you started with？

Good question Yeah， we're going to have to resolve all of those things， by the way。

 it doesn't guarantee that you're going to get something that is like strictly better than what you started with since after all you might have started with your favorite house。

 but you know we will want to argue that this is individually rational。😊，Yes。

 we're going to have to think about that， good question。😊，Yeah， so at the moment。

 this is just an algorithm like， you know， there's no particular reason you should believe that this is individually rational or dominant strategy truthful or that it finds preto optimal allocations。

 but we're going to claim it does all of those things。😊。

But are there questions just about like what the algorithm is for now？Okay。So in fact。

 the first thing we want to establish is even more basic than that like you know。

 how do we know it's an algorithm at all like how do we know it's going to actually halt and output some allocation because we we have this like step that's like okay。

 you know， find a cycle in the graph and clear people along that cycle but。😊，You know。

 what if there are no cycles？Right。😊，To show that the algorithm halts and outputs something。

 it is enough to show that every round it can find a cycle。Right。

 because remember how does the algorithm work， it finds a cycle in the graph and it clears that cycle and it removes any agent involved in that cycle and you know a cycle will involve。

😊，At least one person right it could be a cycle of length one。

 it could be like a self loop if if you know my own good is my favorite one amongst the ones remaining I'll point to myself and I might be the cycle that's cleared but a cycle sort of you know is going to have at least one person and so if at every round I can clear at least one cycle then the number of active agents will reduce by at least one every round and will converge after atmost end rounds So to show this thing halts it sort of sufficient to show that。

😊，The step at every round that involves finding a cycle never fails。But I claim that's the case。

The first claim is that。In the graph that is constructed by the algorithm at every round t。

 this is the graph that results from everyone pointing to their most preferred good amongst the ones remaining。

 but there's always at least one cycle。😊，Okay， and in fact， you know。

 every agent is part of the one cycle。So who can tell me why。

I don't have to worry about like being stuck at some round， you know。

 like round five and not having any cycles in the graph。

 why do these graphs that we're constructing always contain at least one cycle？

I feel like it might have to do with the fact that there's as many edges as there are vertices。嗯。

Yeah， so what do we know about this graph， We know that there's。

 there's exactly one edge outgoing from every vertex because everyone's pointing right exactly one vertex。

So why does that tell me that there has to be a cycle？

Because it's connected and it can't be a tree because it would have n minus1 edges。

 so it has to have a cycle in there。Yeah。SoSo this is like a simple way to see this， right， like。

 you know， imagine that you are standing on one of these vertices。😊，And you're going to take a walk。

 okay， you're going to walk along the outgoing edges。So there's two things about this graph。First。

 you never have any choices about where to go or you always have exactly one choice of where to go because there's exactly one。

Edge， leaving every vertex。And second， you never get stuck right。

 because you never what would it mean to get stuck would mean that you ended up at a vertex that had no outgoing edges。

 but like there's always one outgoing edge。😊，Stteep can always take a walk along this graph and you never have any choices and you never get stuck。

Okay， so the fact that you never get stuck means there must be a cycle because you can keep walking forever right。

 but there's only finitely many vertices and so eventually you must reach a vertex that you've been to before and that's a cycle。

😊，And the fact that you don't have any choices means that every agent can be part of at most one cycle。

Okay， does that make sense？So just because of how we're constructing these graphs that everyone's pointing to exactly one vertex。

We know that there has to be a cycle。😊，And so like this concern we might have had that the algorithm just like is ill defined get stuck like we don't have to worry about that it's like like the algorithm is。

😊，Well defined and will' halt after at most end round。Okay。

 so let's go through like a little example just to make sure we understand the algorithm and challenge my ability to draw on the screen。

😊，So here's an instance of a problem in which there are five agents and five goods and what you see here are the preference orderings of each of the agents so like the way you should read this is you know for agent one。

 his favorite good is good two then good five then good three then his own Good one and his least favorite good is good four and similarly all of the other agents you know also have complete preference orderings。

😊，So how's the algorithm going to work？😊，Well， we've got a graph in which the players overtices one。

 two。3。4，5。And they're all going to point to their favorite good。😊，Player1 points to good 2。

 That's his favorite。Player two points to good three， that's her favorite。

Player three points to good one， that's his favorite。Player 4 points to good one。

 That's her favorite。And player five points to good4。

So this is the graph that we get at round one and we find that there is indeed one cycle， okay。

 so one， two， three。😊，And so we clear this。 So this means that。Player one is assigned good two。

 his favorite good。Player 2。Is assigned good3。That's his favorite。And player 3。Is a sign good one。

 that's her favorite。Okay， so we clear these guys。They're removed from the market。

And so now people have to again point to their favorite goods。 Okay。

 there's only two people left in the market theres。😊，Player four and player five。

Player 5's favorite good is still there。 It was always good for。But player 4， you know。

 her favorite good was good one， which is gone now。

 she's now got a point to her favorite good amongst the ones that remain。That's good five， the only。

Ha。Remaining good in the market。Because he prefers good five to her own good。

And so we have one more cycle to clear and we clear it so the。Good that goes to player 4。

Is good 5 and the good that goes to。Player 5。Is good for and so okay， two three。

154 that I do it right，2 three154， yep， so that's how the algorithm works。Okay。

So is the algorithm clear， like does this make sense to everybody？

And note that after like a cycle is cleared。We have to update the graph。

 like in particular in this example。😊，Player 4 did not get her favorite good， She had to。

Settle for her actually， third favorite good。Okay， and this is why。😊。

It might not be like totally obvious why an algorithm like this would be dominant strategy instead of compatible because not everyone is getting their favorite good。

 and so what you playerer4 is now wondering to herself is whether she could have caused the algorithm to have done something differently and to actually have gotten a most preferred good or a more preferred good at least for example。

 you know good three or good one had she reported different preferences to the algorithm。

 right than who knows。😊，ThisDoes the example make sense to everybody？Yeah。Cool。嗯。Question。😊，No。

 I was just saying， yeah， I good as well， great。Okay。

 so first let's think about the quality of the allocation found by the algorithm and then we'll think about as incentive properties。

😊，And so the claim is that。😊，The top Tra cycles algorithm indeed produces a Pareto optimal allocation on every instance。

Okay， so this says nothing about incentives， it's just about the sort of input input output behavior of the algorithm。

😊，Right， it says。No matter what set of preferences are reported to it。

The allocation that it produces will be Pareto optimal with respect to the reported preferences。

And so。Let's approach this with proof by contradiction。Like suppose this weren't the case。

 what would that mean？Well， that means if the allocation that we output was not Pareto optimal。

 then it must be Pareto dominated by some other allocation。So let's say that it is。

 let's say that there's some other allocation new that Pareto dominates mu。

And let's think about what new must look like。Okay。And so the first clam I want to make。Is that。

If I look at。All of the agents who happened to be cleared in the first cycle。

 like you were cleared in like round one of top training cycles。It's gotta be that they receive。

Exactly the same allocation and new than mu， right， like new and mu are different somehow。

 but I'm claiming like they cannot be different。In the allocation of any of the agents that were cleared at round one of top trading cycle。

 can anyone tell me why？Because they're already receiving the best possible preference。

 so they have to receive the best possible preference。

Exactly like like what was special about the people who were cleared at round one like the people who were cleared at round one were like super happy with their allocation。

 they were by construction receiving their favorite good amongst all of the goods in the whole market because at round one。

 everyone was pointing to their favorite good and the people who were cleared at round one got it。😊。

And the claim， right if I have some other allocation that Pareto dominates mu。

 that means that everybody has to be at least as well off everybody has to be getting either the same good or a good that is even more preferred。

😊，And people who got their favorite good in Mu cannot get something that is even more preferred。

 there is nothing that's even more preferred， so they must be getting the same good。Okay。So next。

 I claim that everyone who is cleared at round two of the top training cycle， the algorithm。

 everyone who was part of the second cycle。They too must be receiving the same allocation that they do in new in this other allocation that like purportedly Parado dominates mu。

Right， and this is for the same reason， right because， you know， let's think like。😊。

Who are the people that are cleared at round two of the algorithm， well they sort of like two cases。

It might be that these people were receiving their favorite good right because like you know what happened that round one。

 everyone was pointing to their favorite good， then we cleared some。😊，Some of the goods and then。

YouSome people are still pointing to their favorite good。

 their favorite good was not cleared at round one。Other people are now pointing to their second favorite good because their favorite good was clear that round one and they didn't get it。

😊，Okay。But I claim that like， okay， given that everyone in New got the same allocation as the people who got cleared at round one in the top trading cycles。

 it's actually also got to be the case for people who were cleared at round two。Because。

There's sort of。Only two cases here right like by the same logic people who were getting their favorite good in mu right well there's nothing that'll improve upon that they're still going to be they're still going to have to get their favorite good in anything that Preto dominates mu。

😊，And the people who were getting their second favorite good， well， how could they improve。

 they could improve by getting their first favorite good， but。😊，We've already established that。

Their first favorite good was a good that was cleared in round one。

And the goods that were cleared in round one are identically allocated in new compared to mu so these people can't get their first favorite good in new either and so since。

😊，You know， nominally， we think new Pareto dominates mu。

 it's got to be that they're getting exactly the same good right so the allocation has to be identical when we look at people who are cleared at round two as well。

😊，Does that make sense。And then the claim follows by induction， right this is true at every level。

Okay， so the， you know， we've sort of proven the base case and then the inductive case is that well。

 you know， if we have that。😊，The allocation you know。

 of new and new are identical when we look at the subset of people who are cleared in the first K rounds of the top training cycles algorithm。

Then it's got to be that it's also identical or when we look at the people who are cleared in the first T rounds of the top trading cycles algorithm。

It's got to be that it's also identical for the people who are cleared at round T+1。

And this is for the same reason， right like the people who are cleared at round t plus one of talk trading cycles by construction are getting their favorite good amongst everything that remains after the first T rounds have completed。

😊，But the sort of inductive hypothesis here is that the allocation has been identical so far for the first T rounds and so。

😊，If your favorite good， you know， if you can't get anything。

That was cleared in the first T rounds of top trading cycles because it's already been spoken for。

 not just in Mu but also in new， then you cannot do better than your allocation in Mu。

 which is by definition， your favorite good amongst everything that was remaining after the first T rounds completed。

Okay。And so， you know， we have。A base case for our induction。

 we have an inductive case just continuing this logic。😊，Through end steps of induction。

 we established that actually。😊，Mux and new have to be like actually exactly the same like they're exactly the same allocation。

 And so that's a contradiction because the claim was that new Pareto dominated mu。😊，来丈ぞ。Okay， try to。

Right。T instead of QED at the end of these things， but I forgot on this slide。um。

that's the proof Does that make sense to everyone understand？

What we proved and how we proved it and in particular like this algorithm always guarantees for every set of inputs to produce a preto optimal allocation。

Okay。So let's think about incentives now。嗯。😊，And this one's easy so I claim that the top trading cycles algorithm is individually rational and just remember what that means it just means that everybody leaves with a good that they like at least as well as the one they started with Can anyone tell me why？

😊，You could be pointing to yourself so that would form a cycle， I guess yeah like。Remember。

Your own good is in your preference ordering and it is allowed that you point to your own good。

the only goods we ever allocate to this algorithm are goods that at some point during the algorithm you are pointing to。

😊，And by definition， you're always pointing to your favorite good amongst the ones remaining and if you're still if you haven't been allocated yet。

 like by definition， again， your good remains。😊，The thing that you're pointing to is definitionly never less preferred than your own good。

 right it's either something other than your own good。

 in which case you like it strictly more or in the worst case it's your own good because you're still in the market if you're like one of these vertices pointing。

😊，And if you don't like anything else as much as your own good。

 like the algorithm as you point to yourself。Okay， and so that's why you can never get anything that's worse than your own good from your own point of view and so the algorithm is individually rational。

Okay。And then finally， I claim that the algorithm is。Dominant strategy incentive compatible。Okay。

 so so not just individually rational， but。😊，You know。

 like you don't have to like do any kind of counter speculation like you can never do better than just telling the algorithm the truth right even though the algorithm is not always going to be able to give you your first choice。

😊，You can never sort of game the system and get something even better by lying to this algorithm。

And so let's prove this。You know， here actually， like if you view it the right way， the results。

Quite intuitive。 So some me sort of。Sketch the proof in a maybe more intuitive。

 slightly more informal way。So the algorithm， the way it really works， right。

 is you report some set of preferences but。Like， without loss of generality， we can。

Think about the algorithm as if it， you know， really works the way I described it where you are sort of。

 you know， an active participant standing。😊，In a town square and every round are asked to point to your favorite good amongst the ones remaining in fact。

 all of that simulated like all of that is simulated by the preferences that you reported but。

You know， if I let you actually like， you know， point every round。

 that's only giving you like a richer strategy space like you can in particular implement what the algorithm would do for you if you truthfully reported your preferences by always reporting your you always pointing to your favorite good amongst the ones remaining and I've only given you like extra freedom like now you can do silly things like you know。

Point to things that are like inconsistent with any preference ordering。So in particular， like。

 you know。If I can prove that it's always in your best interest to do as you're supposed to do and always point to the good that really is your favorite amongst the ones remaining。

 then you know that suffice it to prove that the original algorithm is dominant strategy instead of compatible because it's possible to implement that strategy by reporting your true preferences。

Okay， so let's select the goal。 we're going to sort of imagine the players as like active participants at every round。

 and we want to sort of argue that it's actually a dominant strategy at every round for them to point to their favorite good amongst the ones remaining。

😊，And so。Let's think about this， like why。What would you be afraid of like like what would cause you to doubt that you might not want to point to your most preferred good like what is the。

Bad outcome that you might be worried about like like。

 what are you risking maybe by by doing something other than pointing to your favorite good。

Any anyone want to venture a guess？you think there' will be a lot of competition for that and you think you try to get like first dibs on your second favorite Yeah exactly right like like you know it might be that your favorite thing is like also everybody else's favorite thing you know right like maybe there's these different vaccines you know Pfizer Moderna Johnson Johnson Astrazeneca and like you know you would like the most effective one but so would everybody else and。

Your concern is that if you point to your favorite thing， then。You might not get it。

And more than that。Your concern might be that。You lose out on an opportunity right like maybe like today since everyone's pointing to their favorite thing and we all agree on what our favorite thing is if I point to my favorite thing。

 I'm not going to get it， but maybe like I have an opportunity to get my second favorite thing today right like maybe I'm going to be the only one pointing to my second favorite thing today because everyone else is pointing to。

 you know。😊，This like you know golden house that we all agree is the best house and like now is my chance I'm going to point to my second favorite house and if I do it today i'm going to get it but if I do it tomorrow it's going to be too late because after the best good is gone there will tomorrow be lots of competition for the second best good right so like the reason you might not want to point to your favorite thing is because。

😊，You're concerned about sort of missing out on some transient opportunity。

 like maybe there's no way for me to get my favorite thing。

 but like if I act now I can like get my second favorite thing and if I behave honestly。

 you know I'm going to have to settle for like my fifth favorite thing's sort of like the thing we need to rule out。

And that's the thing I want to convince you cannot happen。Okay， and if that can't happen。

 then there's no reason not to point to your most preferred good right right if there's if there's no way to miss out on an opportunity。

 right if any opportunity that is available to you today will also be available to you tomorrow then there's no reason to sort of strategize like this like you might as well try to get your favorite thing and if that doesn't work you know。

 nothing lost anything you could have gotten today you can also get tomorrow。Okay。And so。

Let's think about that like what are the opportunities that are available to you today？Okay。

 so let's imagine that。You know everyone else has gone first everyone else is already pointing to their favorite good and now here you are looking around at this you know partially constructed graph all that remains is the choice of where you're going to point and you're thinking to yourself you know where should I point？

😊，What are the set of goods that if you point to them today， you will get them。

 you you can get them immediately。Can anyone tell me like what are the goods that， you。

 I know what the rest of the graph looks like？😊，What are the goods that I could sort of get today if I wanted？

Remember that the algorithm works by clearing cycles。So if you think about how the algorithm works。😊。

U。😊，The set of goods that I can get。Are the set of goods that form paths leading into me that that if I follow the outgoing edge of the。

 you know， good all the way through。U。You know I end up in a path that leads to me。

RightThose are the goods I could get because if I point to those goods。

 I will form a cycle that didn't exist before going through in particular like me right including the edge of the good that I pointed to。

😊，So let's call these goods the choice set of agent I at some particular time step。

 these are exactly the goods that I could get today if I wanted。😊，Right， so remember。

This concern I might have right right， like why wouldn't I want to。

Behave truthfully like my concern is that like my favorite good is one that there's a lot of competition for I'm probably not going to get it if I point to it。

😊，There's something else I could get， right， like something in my choice set。

But that this thing won't be around in my choice set tomorrow if I don't act now。

And that's what we want to argue cannot happen。And so the claim is exactly that that can't happen and the way to think about that is to think about how this choice set can change over time。

😊，And so the claim is that。😊，If I have some set of goods in my choice set today。

All of those goods are still going to be in my choice set tomorrow and maybe some other goods。Okay。

 okay， and so actually like， you know。😊，Greedily grabbing something today in my choice set is not a good idea。

 right， because I could you know greedily take the favorite thing in my choice set today。

The claim is both that those things will still be available tomorrow and that there might be other stuff that I might prefer even more。

😊，Right， because like， you know， maybe。My favorite good is also the favorite good of the owner of my second favorite good right so the second favorite good is not in my choice set because he's also pointing to my favorite good right he's not part of a path leading to me。

😊，But， you know， like like maybe only my third favorite good is in my choice set。

 But if I'm his second favorite good， then after。😊，The first round。

 when maybe my first favorite good is going to be removed， he will， you know。

 point to me or to point to someone else in my choice set， which will add him to my choice set。😊。

Okay， so the claim is that my choice set can only grow monotonically nothing ever leaves it and things might join it and so the optimal thing to do is therefore to be patient all yeah there's there's no gain and there's potentially some loss in。

😊，Grabing something in my choice set， if it is not my absolute favorite good amongst the ones remaining。

Okay。So， the reason。It's sort of simple to see if you remember how the algorithm works。

Right right like。😊，How would something。And my choice set be removed。Well。

The only way it could happen。Is if。One of the agents that is in my trice set was cleared。

 for example。Or if their favorite good， the thing that they are pointing to now is cleared。

But my choice set is exactly the set of。Vertices that are parts of paths leading into me。

And so there's no way for either of those things to happen for either agents in my choice set to be cleared or for the。

 you know their favorite goods， the things they're pointing at to be cleared without me being cleared。

 because if they're part of a path leading into me。

 then any cycle they're a part of is going to involve me。Okay。

 so like my choice set is going to remain， you know， the things currently in my choice set。

 the parts of the graph involved in things currently in my choice set is going to remain static until I am cleared because。

 you know， they can't form a cycle without me。Okay， and that's， that's it。 That's like the the。

Key insight right， and that's why it's dominant strategy truthful because。

The set of options that are available to you， right， your choice set can only grow with time。

And so this algorithm is set up so that there cannot be any missed opportunities。Okay。So， that's it。

I'll take around for questions and otherwise I'll see you guys on Thursday。😊，Thank you。Thank you。

 yeah。

![](img/d6a77a0e9165ddd15a3eb485a48942f8_2.png)