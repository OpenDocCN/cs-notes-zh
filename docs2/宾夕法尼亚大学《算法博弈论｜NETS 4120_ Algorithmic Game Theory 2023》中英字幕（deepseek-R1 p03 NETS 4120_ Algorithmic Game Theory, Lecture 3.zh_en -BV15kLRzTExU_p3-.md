# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p03 NETS 4120_ Algorithmic Game Theory, Lecture 3.zh_en -BV15kLRzTExU_p3-

![](img/5ee4e96fd0a11695379ba8b4969d49ea_0.png)

All right， welcome to class number three。Maybe before we begin just some administrative stuff。

There's a grade scope instance for this class and if you were registered as of two days ago。

 you should all have been invited to it hopefully you're all like。

A member of the grade scopepe account for this class so that's how you're going to turn in your problem set when it's due weve started posting the office hours schedule on Sck I had my inaugural office hours today they were attended by the inaugural students。

So you know， like take advantage of those and hopefully everyone's taking a look at the problem set and has started doing it so that you can take advantage of the office hours as they if they come up so before we begin。

Today's material， are there any questions about just the administration of the class？Okay。So。

If you remember last class， we sort of went over the basic definitions of game theory。

 what is a best response， what is a dominated strategy， what is a N equilibrium。And along the way。

 we saw you know， some of these like standard。You know， sort of anecdotes of game theory 101。

 prisoners dilemma， Ba Strinsky， games like this， little games that you can draw as like a matrix and you can like look at them and you can understand them。

But。In general， like in this class， first of all， little two player games are quite limited in what they can model and there aren't。

You knowComp， which is one of the main things we're going to focus on in this class it doesn't doesn't really become a problem for two player games and you know。

 anyways there's sort of little interest in studying two player games。So in general， in this class。

 we're going to try to develop ways of thinking about large games and player games。

And so we'll sort of。Give our first example of that today。

 so today we're going to go through sort of a complete case study of some large structured class of games。

U and。There's all sorts of problems with large games。 you know， first。

 how do you even like express them。 We're going to have to think about how to。

Expressed them in a concise way even even to like think about them and that's going to require structure。

嗯。But weve talked about national equilibriumlibria。You know in a very large game。

 even if we believed that had pure strategy Nash equilibrium and remember， as we saw last time。

 not all games do。You know， now there's sort of。know the state space。

 the set of all possible permutations choices that you know all of the players can make the state space is exponential and so。

The existence of Nash equilibrium on its own doesn't really give us any guidance as to how to find it and so。

It's not clear that Nash equilibria even if even if we think that they are sort of a plausible conjecture for what a stable state should look like would give us any confidence that。

We would get to one， we would get to a stable store。

And so we're going to study in this class a simple natural dynamic。

 something that is hopefully computationally plausible， by which I mean。Doesn't require， you know。

 like vast resources， either computational or or informational on the part of any of the agents then is like a reasonable thing for them to do and show that it converges to na equilibriumlib and that'll be。

Something that you know， hopefully gives us confidence。

 at least in the class of games we're going to talk about that maybe pure strategy national equilibriumria are reasonable predictions for what might happen。

So this will be our first sort of computationally plausible set of predictions in a large interaction。

 but this will be sort of a running theme in the class。Okay。So just to sort of。

Start us off thinking about large games， you know， suppose I have like a general end player game。

 each of the players has K actions。Even if I just want to like tell you the utility function for one of the players。

 how many numbers might I have to write down？Like how big is how big is a large game。

 like end players， k actions， how many numbers do I need to write down for you to tell you the utility function even for just one player？

Yeah。The sign of value。Oh。Oh。The places players of yeah。Exactly， yeah。

 like what's a utility function， it just tells you， you know， a utility function for one player。

Basically tells you。In particular， like you know。Pfer ordering over all of the states in the game。

 How much this player would like the。Game to arrive at one of its particular states and how many states are there in the game well each player can choose one of K actions independently of one another and there's n players so there's k to the n of these right so K to the n numbers just to tell you one player's utility function and then I'd have to do this n times to tell you all of the player's utility functions that would define the game。

And。This would just be like an unreasonable object， like forget about。

Thinking about people being you know like optimally rational playing in this game well like you just you know for large end you just couldn't like look at this thing and have any idea what was going on this is just going to be like an object that is too too big to fit in your brain too big to fit in the brain of anyone playing in this game。

So like unless we impose some additional structure on large games。

 it just seems crazy at the outset to think about playing in large games in any kind of optimal way。

So you know， that doesn't mean we shouldn't think about large games， what that means is。

We shouldn't think about structureless large games if we're going to think about large games。

 we have to constrain ourselves thinking about games that you know despite the fact that they have many players。

 despite the fact that perhaps each player has many actions has some kind of concise structure that makes it easy to think about。

Okay， so maybe like。The first example of such a game and an instance of the kind the class of game if we' going to we're going to talk about today are traffic routing games that we talked about sort of informally in the first lecture。

And just I'm going to define all of this formally in a moment。

But just to give you sort of an intuitive sense of how a traffic routing game might be defined。

 you know what we're going to have is some underlying graph， okay。

 so there's like vertices and edges。Okay， think about this as like a road network。

Specifying how things are interconnected。And players will be identified that there will be end players。

 okay， and think of each player as being identified as some starting location and some ending location on the graph。

 possibly different for different players， but you know maybe player one。

Wakes up here at their starting location their home and would like to drive to here their ending location。

 maybe their office。And similarly， all the other end players might have might have a starting location and an ending location and。

The action space for the player might be the set of paths in the graph going from S to T which note might be really big right like the number of paths in the graph going from S to T could be exponential in the number of edges in the graph in the number of edges in the graph or the number of vertices in the graph right because you know if I have a graph that looks like this you know I have like an independent choice to make at every layer of the graph and I can make each of them differently so the strategy space can be really large but it's easy for me to tell you what the strategy space is right I don't have to enumerate an exponentially large set of actions I tell you the graph and then I say okay it's the set of ST paths in the graph a concise representation。

Okay， and。It's supposed to be a game right so it's supposed to matter to you what the other people do and so you know the way that is represented in like a traffic riding game is there's a congestion function on each edge okay。

Separately。For each edge that tells you how congested a road is as a function of the number of people who are playing on it。

Okay so everyone will choose a path this will in particular tell you how many players are driving on each road segment that'll you can plug it into this function to figure out what is the congestion on that road segment and and you know you sum up those congestions along your path to figure out what your total commute time is okay so we'll define a more general class of games that captures all of this formally in a moment。

 but this is just sort of。Maybe to put a picture in your mind to think about how we might。

Define a game， a class of games that has a lot of structure that lets us write down something relatively simple that you can think about。

don if I want to think about how to drive in Philadelphia， I don't have to like imagine。

 some like exponentially large object like enough to sort of have some idea of what the Philadelphia road network looks like and what traffic is on different routes。

Um， that lets us think about games that implicitly have large numbers of players and large numbers of back。

Okay。Questions。Yep。Cerify the function is for the inventory。That's right。

Which is important if we want this to be a concise representation because there's potentially exponentially many paths。

In the number of edges。Okay。So let's now give a formal definition for the class of games we're going to talk about today that will include in particular things that you will recognize as traffic ro games as well as some other stuff。

And。Okay。各喂。The way we define things。B class and sort of the tradition in game theory is that players want to maximize their utility。

But it's going to be more natural in congestion games to talk about players who want to minimize their costs you want to minimize like a commute time for S to T and mathematically these things are equivalent if I wanted to phrase it as maximizing utility。

 I could just say your utility function is the negative of your cost function。

 but to avoid having to do that all the time I'm just going to。For this lecture and for you know。

 some of the future ones talk about players who want to minimize costs rather than maximize utility。

 but don't let that throw you off， it's the same thing。Okay， so what's a congested game？Well。

 it's a game， so I have to tell you who are the end players within it。Okay。

 and now we start to get to。Some some aspects in which these games are more structured than general games。

 so I'm going to。Introduce this set of objects called facilities and in general this can be just some abstract set of M things。

 but maybe to keep something concrete in your mind if you're thinking about like a traffic routing game。

Think about the facilities as being。The individual。Roads in the road network。

 so the facilities might the set of facilities might be the set of edges in this graph。Okay。

And each player is going to have a set of actions， but the set of actions will not be arbitrary。

 each action will be identified with a subset of the facilities。Okay。

 so the action set will be a collection of subsets of the facilities。

It can be arbitrary subsets of facilities。Or rather， I can define a game。

 these are actions are arbitrary subsets of the facilities。

 but each particular congestion game will assign an action set to each player that is some particular subset of the facilities。

So for example， just to keep this all concrete and grounded。In a traffic routing game。

If I am a player who's starting。Location is S and whose ending location is T my action set would be the set of all ST paths which are a particular collection of subsets of the edges。

喂。Paths or subsets of the edges to in general in a congestion game。

 the action set for each player will be a subset of the facilities。

's a collection of subsets of the facilities， each action is a particular subset of the facilities。

And。For each of the facilities， we identify some cost function， okay for facility J。

 I'll write that as LJ。And this function maps an integer between zero and n and being the number of players in the game to a real number。

 and you should think of that as sort of meaning。You know。

 LJ of K is the cost of facility J when K players are using it。Okay。

 so this is sort of like the if we're modeling a traffic network， this is like， you know。

 what is the time to traverse the stretch of road as a function of the number of cars that are driving on？

like for a traffic riding game， you'd sort of expect that the cost would go up。

 the more people were using the road， but the definition of a congestion game doesn't require that this cost function be monotone。

 it might be interesting sometimes to think of games where the cost goes down when more people use it。

Okay。And in particular。嗯。😊，The cost of a facility does not depend on who is using it。

 just the number of people who are using it。😡，Okay。

 so this is another sort of important structural property of the game。

To describe one of these things， to describe a cost function that sort of cared about the identity of who was using it would require。

 again， an exponential in N。Number of numbers， there's a lot of subsets of the users。

 but if we only care about the cardinality of the set of users。On the facility。

 then this is sort of a concisely defined function。Okay， and so finally。

 what are the utility functions for the players or since we're going to be talking about costs。

 what are the cost functions for the players。So remember。

 what we need to specify is what is the cost for each player as a function of the choice of action for themselves as well as for all of the other players as a function of the choice of action of all of the players。

Okay， so you each player chooses an action， which is a subset of the facilities。

And given such a play profile， I can now。Ask the question， well， on each of the facilities。

 given what everyone is doing， how many people are using that facility。

 how many people have played an action that contains as an element。That facility， facility J。Okay。

 so well I'll just write a shorthand NJ of a to mean at action profile a。

How many people are playing on facilityac J？And then the cost of an agent in this game。

 the cost of a player in this game， given a play profile。

 given a choice of action for each of the players is just。The sum over all of the facilities that。

That player is using， remember an action is just a subset of the facilities。Okay。

 so summed over all of the facilities that that player is using， the cost of that facility。

 given the number of people that are on it。Okay， so again。

 just to keep things grounded in traffic routing games。嗯。

Everyone chooses an action in a play profile that means everyone decides a route they're going to drive from home to work everyone picks a path in the graph。

That tells us sort of the level of congestion on each of the roads。

 the number of people using each road segment and the time it takes to traverse each road segment given given the cost function for that road segment。

And then your total commute time， your total cost is the sum over all of the road segments that you personally have decided to drive on of the congestion on that road segment。

Okay， so it's a pretty natural class of games， pretty good model， I think for traffic routing games。

 but you know this is just like a slightly more general class of games that captures that。Okay。

 so why don't I pause we this is the class of games we're going to study today， why don't I。

Pause here to let you。Digest this and and take questions because I want to make sure， you know。

 there's some like， you know， abstraction here， but I want to make sure that。

All of this makes sense as a definition and in particular it's clear how these things map onto to maybe the more intuitive。

Idea of a traffic riding game。Yeah。There are questions about the notation or the definition or the objects we're talking about here。

Yeah。Yeah。不是。没有问题。That's right yeah so the cost function depends on the facility there's a different cost function for each facility and on the number of players using the facility。

 but it doesn't depend on anything else so in particular given that you and I are both traversing this road segment and there's a thousand people trying to do it at the same time it takes me the same amount of time to do it as it does you it's not it's not that like。

You've got an airplane or something and can go over the traffic。Peng。Yes。So， if。

I would need an I would to player， right？So then are they， Are we also adding up the cost。这定是一块。

Players are using。So the cost so your cost as an individual player depends on the。

Depends only on the the facilities you are using， the facilities other players are using contribute to their costs。

 but not to yours， so for example， if I'm driving from home to work along this central path and there's a huge amount of congestion on some road I'm not taking that doesn't slow me down。

Yeah。应该你判决。ISo there's no notion of time here。呃。Yes， so like right， it's it's true that like。

Um in real life time exists， but in this model there's no notion of time like you ever this is sort of a static you everyone chooses a path and you contribute to the congestion to every road in the path simultaneously。

Good question。Others。Okay。嗯。Maybe just to sort of briefly talk about very closely。

Related set of games to traffic routing games， but but that have a。Bit of a different flavor。

Even in traffic routing games。Maybe the motivating story is like this road network， you know。

 it already exists， it's been built。And what we're measuring is the amount of time it takes for you to drive down each of the roads and so the more people that are on the road you know takes more time so you know these these cost functions per facility they're increasing more people on the road。

 you know like more。More congestion。But note that we do not require in the definition of a congestion game that these cost functions be increasing function。

So we could also consider what are called network creation games where again， you'd have a graph。

But maybe now the model would be， you know these are。

placelaces where we could build road or we could build fiber optic cable or whatever。

 and there's different players who would like to connect different endpoints in this graph and to actually connect them you'd have to actually build these roads or stretches of fiber optic cable or whatever and that would come at some cost。

But that。If you and I both want， you know， have different points we want to connect。

 but there are paths that。Involve the same segments， then maybe we can share them。

And we can split the cost of building them， we can sort of team up and split the cost。

 so maybe there's some cost of constructing an edge。Say C dollars。Um。

 and if I'm the only one who's going to like use the edge， if I want to build it。

 I have to pay C dollars。But if you and I are both going to use it。

 then each of us only has to pay C over $2 and if there's three of us who are going to use it。

 each of us only has to pay C over$3， meaning， you know like there's a fixed cost of construction for each facility。

 but we can share the cost across people who are going to use it。

that kind of thing is also a congestion game。Okay。We'll think about games like this a little later in the class。

 but this is just to point out that。嗯。Yeah， but。Congestion games have a very particular structure。

 but there's a little more flexibility here than just modeling like traffic routing， for example。

Okay， so， you know we've got some class of games and you know at least I can like tell you what the game is。

 you know， and with sort of， you know， a relatively small amount of information。

 I can sort of describe the game to you without， you know， these sort of K to the end numbers。

And so there's some hope， at least that， you know， people could maybe figure out how to think about such games。

U。Okay， it' like so what， can we， what can we learn about games in this class。

 like can we can we make use of this structure to say anything interesting？So questions we could ask。

 right。Do。Games in this class have pure strategy national equilibrium。

Like if we're going to try to make predictions for what might happen and when people play in games in this class。

 like what should our predictions look like？And we know that every finite game has a mixed strategy Nash equiria。

 but like， you know， I don't know， are people really going to randomize like are you going to flip coins when you're deciding where to go to you know what route to drive on in the morning。

 it would be nicer if if we could if we could talk about pure strategy N equilibriumlibria， but。

Of course， you know， like we can't if they don't exist， so the first question might be。

Do games in this class have peer strategy N equilib？

Even if the answer were yes right these are still like very large games why should we think that computationally bounded agents who are not coordinating with one another might have only sort of a limited view of the state of the game like maybe they can get traffic reports but they don't know you know specifically who's doing what you know。

 is there any reason to think that。These are simple uncoordinated players could find one。

If even if the answer to the first question is yes， they have pure strategy equilibriumria。

 but the answer to the second question is no， then it's not clear they're going to be。

Good predictors。Okay， so you know like。The sub questions are just adding up to the overall question are pure strategy national equilibrium computationally plausible predictions in this class of games so that's the question I want to like try to answer today。

And so。 right the question is， can computationally bounded uncoordinated players find one？

What what are they going to do like why don't we start by thinking about a particular simple thing that like。

They might do and go from there。So I want to talk about something that I'll call better response dynamic。

And I'll describe it to you。In pseudocode in a moment， but like it's a super simple idea。

 let me just tell you what it is first。Oh and and。Although I'm going to write this out in pseudo code。

There's going to be a lot of things that are left unspecified like in this first line。

 what is the starting point， well it can be arbitrary。And that's going to be a strength in that。

Whenever there's something unspecified， like。What's the starting point of the dynamic？

The answer will be it can be anything and the things we're going to prove about it will still hold。

 Okay， so if we want to sort of think about this as。

Not an algorithm that you're going to run on a computer to compute to na Bo。

 which you could of course think about it that way。

 but but if we're not going to think about it that way， but but it instead a model，You know。

 still at a 10，000 foot view， but a model for what people might actually do。

 then the less stringent our model is， the less we assume specifically what they're going to do and allow them to do anything in some class of behaviors。

 the more plausible our model will be。Okay， so。Some dynamic it'll have some starting point。

 but I don't care what the starting point is， could be anything。Okay， so everyone starts off playing。

Arbitrarily in this game， they pick some route， it doesn't have to be a good one or a bad one。

And then you sort of imagine that， you know， okay。Every day the sun comes up。

 you have to drive to work again， you play this game again。U。And。Sometimes so and you know。

 maybe like you don't have。Findd grained information about what people are doing but but maybe the kind of information you have is the kind of thing you can get from Google Maps or like a traffic report like you have some idea for what the congestion is on each of the roads or at least what it was yesterday。

Okay， so you might notice that you were doing something that was suboptimal。

 it was not a best response to what everyone else was doing there's something else you could do you could change your action to that would improve your utility that would sort of decrease your commute time。

And so in arbitrary order， players will take turns changing their action if there's an action that they can switch to that will improve their utility。

Okay， and just sort of emphasizing the things that are underspecified here。Okay。

 I'm thinking about a sequential dynamic where people are changing their strategy in order。

 but it doesn't matter what that order is。And。I'm not assuming necessarily that they're playing they're changing their strategy to their exact best response。

 that they' that they're playing the thing that exactly minimizes their cost。

 I'm just assuming that they're changing their action to something that decreases their cost there could be many such things and I don't care which one they pick yeah。

对。Yeah， I mean， it could be like a greedy approach would sort of be， you know。

 pick the absolute best thing you can do given what everyone's doing now。

 I'm not even requiring they do the absolute best thing just something that improves a little bit。

And this will just keep going forever or until it can't go anymore because everyone's doing the best that they can be already。

Okay， so this is sort of the high level idea of what best response dynamics is。And so just to。

Write it down in a way that's harder to understand here it is in pseudocode。

But it's exactly what we said， right， like you start at some arbitrary action profile。

While there exists a player whose current action in this action profile is not a best response by which I mean。

Their action is not one that minimizes their cost given what everyone else is doing。

Then we let them change their action to something that does better we can let them change their action to AI Prime。

 or AI Prime can be any action that has lower cost given what everyone else is doing compared to what they were doing before。

 doesn't have to be the one that optimizes it， just lowers it。

And they change their action and we continue and if we you know only if everyone is playing a best response do we break out of this loop？

This is what I mean by better response dynamics。Is it clear？

So you can think about this as an algorithm if you like， with certain things that can be。

 you certain things that are underspecified and can be instantiated in arbitrary ways。

 or you can think about it as some model for what people might do。

 but is it clear what is this like dynamic that we are now going to try to make claims about？Okay。

Yeah。Okay。So what's。Start simple。So like。You know， is this whole dynamic it's a big while loop。

 it's not clear this thing is ever going to halt。It might go forever。

 maybe it doesn't converge anything， maybe people， you know， maybe like I。

It could be that repeatedly I change my action to something that decreases my cost。

 but it increases your cost and then you change your action to something that decreases your cost and it increases my cost and we go back and forth forever。

So a prior， it's not at all clear that this thing is going to halt。

But I claim one thing that is clear is that。If it halts。

 it halts at a pure strategy N equilibrium of the game。And can anyone？

Tell me like the one liner explaining why this is。Yep。Where each people。Ting their best。Yeah。

 it's like it is the halting condition of the algorithm right like what is the halting condition of the algorithm it is that everyone is playing a best response to what everyone else is doing if that werere not the case。

 if there was someone who was not playing the best response we would not have halted so like just by reading off the halting condition of the algorithm。

 it must be that if everybody if the while loop ever if we ever exit the while loop。

 if this dynamic ever halts， the thing we return is a pure strategy na equilibrium。

 which just means it is an action profile so that simultaneously every single player is best responding to what everyone else is doing that is the halting condition of the algorithm。

Is that clear？Okay， so。If we want to show that best response dynamics converges to a na equilibrium。

Which in particular will prove。There exists pure strategy Nsh equilibrium。

 it's sufficient to argue that this algorithm halts if it it halts at a Nsh equilibrium。Okay。

 so the next question is。嗯。The next question is， does best response dynamics always halt？

What do we think like， might it be that in every game best response dynamics halts。

 is that a theorem we could hope to prove？嗯。我后。Yeah， let's play rock paper， scissors， rock， scissors。

got me so okay， right like like best response dynamics does not always halt right we can do rock paper scissors and it's it's going to cycle right and and the problem is what's happening is exactly。

😊，What I said a moment ago that it might be that every time you best respond。

 you decrease your cost and increase my cost and the reverse happens when I best respond and that's what's happening in rock paper scissors。

 my costs going up then down then up and down， we're just cycling forever。Okay， so。

Best response dynamics。You know， like if our hope was to prove best response dynamics always halts like we're out of luck。

 it's just not true。I mean， in particular， like if it halts。

 it implies the existence of a pure strategy Nash equilibriumria。

 so it can't possibly halts in any game that doesn't have pure strategy Nash equilibriumria like rock paper scissors。

mOkay， but。What I want to approve is that。Although best response dynamics does not always halt in general。

 in congestion games， best response dynamics does always halt。And in particular。

 a corollary of this right like this is， you know， this is going to be be a statement about an algorithm right like we wrote down an algorithm and the theorem is。

The algorithm helpss。But like a corollary of this。Statement about know this this fact about you that's going to come out of the analysis of algorithms is just like a structural theorem about this class of games。

Right，It means in particular。It must be if best response dynamics always halts in congestion games。

 that every congestion game has at least one pure strategy national equilibrium。Right， like。

This is not an obvious structural theorem like not all games have pure strategy Nash equilibriumria。

 but if we can prove this fact about best response dynamics that it halts。

 that will in particular prove the existence of pure strategy Nash equilibriumria for every game in this class。

Okay， is that。Implication clear。And just to sort of like highlight this kind of implication because it's going to be a running theme in this class。

 right this will happen more than once that we sort of get some non obvious structural theorem about a class of games through the analysis of some particular algorithm。

Okay， so this is like the first instance of that。Okay。嗯。

So let's think about how you might prove something like this。Right。

 so what is the what is the concern， The concern is that。We get into a cycle。Yeah know， like。

These are finite games， they're big， but they're finite， so if this never halts。

 it means that if we keep playing this game。Via best response dynamics。

 eventually we're going to get back to exactly the same game state that we started to。Okay， we'。

 you know， maybe not the one we started up， we're going to visit the same game state twice。

So that like the kind of thing we need to prove is that we can never visit the same game state twice that we are making progress according to some metric。

 the metric might not be obvious a priori， but if we can identify any metric along which iterations of best response dynamics are making progress。

Then an implication will be that we can't loop back to a state we've previously visited。

So that's going to be the idea we want to identify some potential function。

 some function mapping game states to like real numbers。

And we want to argue that that potential function can only go in one direction， only go down。

As iterations of best response dynamics progress。And the implication of that is that we can't get back to the same game state twice because the potential function maps game states to potential to numbers and if the number is only going down。

 if we get back to the same game state it must have at some point gone back up and if we prove it can only go down。

 that can't happen。Okay， so that's the high level proof strategy。Now of course。

 the question is what is the potential function， This is the potential function we are going to use so let me I'm going to read it out to you。

 but let me state off the bat that like。This is not an obvious quantity of interest a priori。

 this is going to be useful for us because of the role it's going to play in the proof。Okay。

 so so like when you first look at something like this， you might think to yourself， okay。

 this maybe kind of looks like。Social welfare， the sum of the costs of all of the players right that would be a natural thing to think about like what is the average commute time of all of the players then it would be nice if every step of best response dynamics decreased the average commute time and then average commute time would be a potential and also like this would be an interesting statement in its own right。

Unfortunately that's not true and this is not social welfare。

 this is not the sum of the costs of all of the players what is this function？Well。

First we're summing over oh， so first of all， you know。ItIt is a function of the sort that I。

Promised it just labels every game state with a number to map from game states to real numbers。

And what number does it label a game state A with？First， we sum up over all of the facilities。

And then for each of the facilities we look and we say， okay， at this game state。

 how many people are playing on this facility， NJ of A？

And then we sum from one to the number of people playing on that facility right so K is1。

 then K is two all the way up to the number of people playing on the facility。

 and what we're summing up is the cost of that facility when there are K people on it。Okay。

Not obvious why you would care about this， but it's it you know the reason is going to pop out of the proof and you can imagine how to given the thing that we're going to prove how if you knew that was what you wanted to prove you could sort of reverse engineer。

What you needed to get this potential function。Okay， so， you know。

Remember the outline of the proposed proof outline。It'sNot not for T shirts。嗯。hel。We want to argue。

That。At every round of best response dynamics， this function decreases。

So we need the thing we need to think about is how this function changes when some particular player say I switches from action AI to BI during some step of better response dynamics。

 okay that's like the thing we need to think about if we can show that the change is strictly negative and will'll be done。

So let's start by thinking about something a little bit different。

But whose relevance will become clear shortly？Rather than thinking about the change in potential when player I changes their action。

Let's think about the change in player eye costs。😡。

Because that's something at least we can hope to get some handle on because like we don't know much about。

The individual changes that make up the rounds of better response dynamics mostly it's underspecified。

 but the one thing we know is that these changes like by definition must decrease the cost of the player who's making them that's why they are making them they better responses。

So we know that the change in playerized costs， the difference in playerized cost after they make their switch from AI to BI compared to before they make their switch。

 that difference is going to be negative because that's the one thing we know about better response dynamics。

 players decrease their costs。And so what is that change in cost going to be？Well。

 remember what a cost function looks like for a player in a congestion game。

It's the sum over all of the facilities that they play on， of the cost of that facility。

 given the number of players that are also playing on it。And so。Suppose I switch from playing。

A subset of the facilitiess AI， like a path and a graph AI。

To a different subset of the facility's BI， like a different path in the graph。Well。

 it might be that these paths。Are not completely disjoint they might like。

Interssect a little bit like if I live in the suburbs on some cudeac。

 like I might have choices for how to get into pen。

 but like there's no avoiding that first I'm going to have to like， you know。

 drive down my driveway and drive down like the road and you know。

 like the beginning and end of my path might look the same right so these like AI and B are not necessarily disjoint。

So like， first of all。If I look at。Any facility that I play on both in my new action BI。

And in my old action， AI， it contributes exactly the same amount to my cost。

 both before and after my switch。Right because that you know nothing's changed。

 I still play on that facility， I still drive down that road segment and this you know it's only me that's changed my action and I didn't change my action relative to this road so the number of people playing on the road hasn't changed。

So facilities that I play on both before and after the switch。

They contribute the same amount to my cost before and after the switch， and so they cancel't out。

 they don't appear in the difference in costs。Similarly。

Facilities that I don't play on either in BI or AI don't contribute to my cost in either case。

 and so don't contribute to the difference in cost。哎。

The only facilities that contribute to the change in my cost when I switch from a subset of the facilities' BI to a subset of the facilitys AI are those facilities that are in the symmetric difference or those facilities that either I previously was not playing on。

 but now am。Or the facilities that I。Previously was playing on and now I'm not。Okay， so。You know。

There's some facilities。That are in BI， my new set of facilities and my new action that I previously was not playing on。

But now am。I wasn't paying for the cost of those facilities before and now I am。

 so they're going to contribute positively to my change in cost。

So I'm going to have to pay the cost of those facilities and the cost of those facilities is not just the number of people them who were playing on them before。

It's that plus one because now I'm there right I've increased the load on those facilities by one。

So that my cost has gone up on the one hand by the cost of all of the facilities that I've moved on to。

Where the number of people playing on those facilities is now one more than it was before。

But on the other hand。It's gone down by the costs of all of the facilities that I was previously playing on and experiencing the congestion of that I no longer am。

Okay， so。I can write。My change in costs。If I in one round of better response dynamics have switched my action from AI to BI like this。

 the sum over all of the facilities I moved on， taking into account that there's now one more person on them。

 minus the sum of all of the facilities that I moved off of at their load yesterday， yes。INGMS。诶。

I this is was playing， this is what I was paying。Before I change my action。

So it's true that after I move off of this， everyone else on these facilities gets to experience the joy of not having to be around me and their cost has decreased on those facilities to LJ of NJfS minus1。

But yesterday， before I moved off， I was paying the cost of the facility。

 including my own presence there。Does that make sense？我 is。Typo should be A。Yeah。I why。Yeah。

 so NJ of A， this is the number of people who were playing on facility J at action profile A。

 which is the action profile that we were at before I changed my action。

Now these are facilities that I wasn't playing on in action profile a。

 but that I am now playing on in this new action profile that I get by changing my own action。

 but not everyone else's。And so now there's one more person playing on these facilities that one more person is me。

即 that。Um。Yes， exactly are these are not all of the facilities I'm playing on。

 these are exactly the facilities that I'm playing on now that I wasn't playing on before。

And of course， the ones that I was playing on both now and before， you know。

 they just canceled out in this difference。Does that make sense？Good question。Other questions？Okay。

 so this is an expression for my change in costs。And。

I don't know much about better response dynamics， but like the one thing I know is that whatever this is。

 it's negative。Because that's the definition of better response dynamics， but you know。

 a lot is left unspecified， but。When someone changes their action。

 they do so exactly because it decreases their cost。Okay。

So now let's think about what is the change in potential when a particular player changes their action from AI to BI。

Okay， and we can。We can go through sort of much the same exercise。

Let's think about the potential function again。It is a sum over facilities。A on each facility。

 we're summing from K equals1 to the number of players on that facility。

So if we look at the potential before。potential after my change。

 minus the potential before my change， I can think of this difference facility by facility。

And there will be some facilities such that the number of people playing on them has not changed。

In particular， those facilities that either I was playing on both before and after my change or the ones that I wasn't playing on before and after my change for those facilities。

 the number of people playing on them won't have been affected by my change in action and so their component of the sum is just going to be like the same before and after and so they're going to cancel out in this difference。

The only facility whose contribution to the potential is going to change。

Are those facilities such that？The number of players playing on them has changed。ok。😊，So again。

 there's two kinds of facilities like that。There's facilities that I was not playing on in A。

 but I am playing on in B。What's the change in potential going to look like as a contribution from that facility？

Well， previously for that facility， we were summing from K equals 1 to NJ ofA。

 the number of players on that facility。After the change。Well， NJ of A。Increased by one。

 so we're now summing from cableables 1 to NJ of a plus1。

And so we have the whole sum that we had before， plus one additional term。

 what's that one additional term， it's NJ of A plus one。Okay。

 and so the additional contribution to the potential。From the facilities that Claire I switched onto。

Well。It's going to be the load on the facility when NJ of a plus one people are on it。

Because that's the extra term that's added to this sum when we increment the number of people playing on the facility by one。

And then there's another kind of facility that you， has had the number of people playing on it train。

It's the facilities that player I moved off of when he changed his action。Okay，Now previously， you。

 when he was playing action AI。There were NJFA people on that facility。

Now that he's switched his action to something that does not。Contained facility J。

 the number of people playing on that facility has decreased to NJ of a minus1。Okay。

 so the contribution of that facility。To the potential。Is now a sum not from k equals 1 to Nj of a。

 but a sum from k equals 1 to Nj of a minus1。When we look at the difference in those two sums。

 what is the term that has been removed in that difference？Oh， it was the biggest term in the summit。

 it was NJ of A。And so what we。Subtract off。When we look at the change in potential on those facilities that player I has moved off of。

 those facilities that he had been playing in action A， but is no longer playing in action B。Well。

The sum， which corresponds to the contribution of that facility to the potential。

 is no longer contributing this term， which is the loss of the facility when NJ of a people are playing on it。

Okay。That makes sense。Yes。咁个头就四月份。那就好。不能没。So we have not specified particular congestion games。

 the claim we are making now is for。The set of all congestion games。是的。

This is the potential function that we are using for this proof。

 which is applying to all congestion games now。At various times， we will。

Try to adapt this analysis to other classes of games。Like on the next problem set。

 U are asked to do so and。You will need a different potential function。And part of the。Its sort of。

 we'll see several variants of the style of proof， like it's basically all mechanistic once you have the potential function。

 you have to think like what is the change in potential when when someone changes direction。

Most of the cleverness is in coming up with the potential function and。

Although there's not exactly a crank to turn to do that like。

One thing that you can often try to do is what we've done here is to try to rig things up。So that。

The change in potential is exactly the change in playerized cost。

That's sort of how this potential function is designed。该真。Yeah。Exactly。

 you want the potential you want to be able to argue that the potential function decreases at every rep。

What does the potential function represent。The potential function does not necessarily represent any natural quantity in the game。

 it is a tool in the proof to argue that you cannot get into a cycle。

Does it not represent the total time spent class like ball players？It doesn yeah。

 no that would be the social welfare or the social cost and if you write down what is the sum of the costs of all of the players。

 you'll get something that is not this。我。还いし。嗯。Thats said。As this figure each of cost just that when。

And plus。Or N plus point， here's a new kind of sum being added when you curve。Exactly。Exactly。

 like you can figure out what is the change in costs。

To a player and it's it's this you know this is what it is And then if you were now trying to design a potential function to make this proof work out what you'd want to do is design the potential function exactly so that this would be true so that the change in potential would be equal to the change in cost so you know what the change in potential has to look like。

So it's， you know， sort of like a discrete derivative。

 you want to take the discrete integral of it or something。ok。By the way。

 we're not quite done with the proof yet。嗯。😊，But these are all good questions。Right， so is this？

Cl is it clear where we are at the moment that we've sort of argued that' the change in potential when a single player changes their action from AI to BI？

It's exactly equal to the change in cost for that player。And we knew that if this is true in general。

 this statement has nothing to do with better response dynamics right like this was just like an algebraic identity。

 the change in potential is equal so the change in costs of the player。

But if this was a step of better response dynamics。

 the change in cost had to be negative right players were。By definition。

 the only thing we assumed about this dynamics was that the changes were such that they decreased players costs。

And so if this was a step of better response dynamics， this change actually has to be negative。

And so in particular， if we imagine tracking this potential function as better response dynamics goes on。

 it starts at some value。Every step a better response dynamics strictly decreases it。

And this can't go on forever because it's a finite game。In particular。

 we can never visit the same state twice。Because that would imply that at some step。

 the potential would have had to go up， which we showed can't happen。Okay。

 and so best response dynamics halts in congestion games and in particular halts set a pure strategy in Nash equilibriumria。

 and in particular this proves the existence of pure strategy in Nash equilibriumria in congestion games。

Is that clear？Like it's kind of neat， right like we。Just sort of thought about this algorithm。

And we proved that in this class of games。Pure strategy Nash equilibrium exists。

 we didn't know that before。And we even have a story for how you might find them。

 that sort of the inevitable result of people sequentially changing their actions in sort of self interested ways to decrease their own costs。

Like it's not just like pure strategy Ash equilibrium and this class of games are no longer just a stable point。

 but they are sort of。An attracting point of this class of dynamics where people are going to sequentially try to decrease their own cost。

Like this class of dynamics will inevitably get you to a pure strategygy Nash equilibriumria eventually。

And so maybe it's a reasonable class of predictions。Yeah， the imageify Israel numbers。Well。

 it depends what you mean by the image， the range of P is real numbers。

 but it doesn't map onto all of them because although there's a lot of game states。

 there's only finite many。我在。Potential， if it just ends up with。

Like why don't we just use the cost directly， whose cost？Chaing。Well there's n different players。

 so when I make a better response move， my cost decreases， but when you make a better response move。

 my cost likely increases。Right like if that could happen very easily you move on a road that i'm taking now it takes me longer to drive to work so when you make a better response move your cost decreases when I make a better response move my cost decreases but your cost goes up if we were just paying attention to individual player costs that wouldn't rule out the kind of cycling we're worried about。

We need a single consistent measure that goes down at every time to rule out cycles。

Do to see I first， hopefully。So。Here。I mean， we hadn't yet proven anything about the game。

 but we identified that when player I changes their action。

 their change in cost is equal to this algebraic expression and it's negative。

Which allowed us to realize， right， but this was。The change in cost for a particular player。

 there's end players and this thing might go up again when you。When you take your turn。

But now we're looking at this single potential function。And we're saying，huh， you know。

 when player eye changes their action， whoever player I happens to be any when any player changes their action。

 the change in potential is equal to the change in player I costs。

And this thing is negative if player I was the one who changed their action。

So now we have the single number that is decreasing at every round when different players change their actions。

 and this is what we need to argue that we don't get ourselves in cycles。Makes sense。Yeah。

 what's the significance of the point yourself。The significance of what？Oh。

 I just mean this is how I'm defining it， this is like a definition。Good question， other questions。

Yeah。Like so far its seems like creep in like super general。

 like but what is like a property project？你。A couple of things we're using crucially that congestion games have this notion of like facilities first of all。

 like most games don't like the potential function is defined over these facilities。

We're using crucially that。The cost of a player is the sum of the costs of the facilities。

 that was how we derive this expression for the change in cost。

 and we're using crucially that the cost function at each facility depends only on the number of players playing on it and not on anything else。

So we're sort of using all of the structure。But。Not more than that。 So。

 so this result holds for any game that can be described as a congestion game。

 of which there are quite a few。Okay。Yeah。find it's almost like you're starting with like you have to take state and then you're imagining。

Like the first person arrives at each。It doesn't have to be an empty game state。

 you can start it in an arbitrary game state。Yes， sorry， sorry。嗯。I guess that's like more like。

There my think think about this。But like the second term like the second summing term seems like it's。

Like if you remove the sum and replace it with the NJ of A， you would have a virtual welfare， right？

Um， you might have to， it might be like And of a， you might be like。

NJ of A times LJ of NJ of A like EW。Okay。Yeah and that the cost of a facility is a function of the number of agents on it。

 then we have proven that best response dynamics convers。Good questions， other questions。ok。

So we sort of said， okay， you know。Better response dynamics is great like you know。

 start at any state you want to let the players move in any order they want let them take any better response that they want no matter what。

They will inevitably。Lead themselves towards a pure strategy Nsh equilibrium。

 and therefore pure strategy N equilibrium might exist。

Something we have not addressed here is how long it takes。Like strictly speaking。

 all we have proven is that。The dynamics。Never visit the same state twice。But you know。

 like if there's n players and K actions， there's K to the N states and in a congestion game like K could be exponential itself in the size of the graph so。

You know， like doesn't mean it's going to be fast。mAnd like although I'm not going to give the example。

 like indeed you can draw。Graphs and give orderings of players that。

Conform to how we defined better response dynamics that really do take exponential time to converge to a N equilibrium。

So。You know， iss there any hope like can we say anything about anything non tri about convergence speed？

And。The answer is yes， if we're willing to。Think about approximation。So what do I mean by that？

So the way we've defined。A pure strategy N equilibrium so far， as we've said， look。

Everyone should be playing simultaneously an exact best response to everyone else。

 nobody should be able to improve their commute time by even。A microsecond。

But we could define a slightly relaxed version of that， we could say look。

A strategyrategy profile is going to be an epsilon approximate pure strategy na equilibrium if nobody could。

 if everyone's playing an approximate best response。

 if there's nobody who could reduce their commute time by more than a second by changing to a different route or half a second or a tenth0 of a second or whatever。

 some finite，Epsilon bounded away from 0。And the thought might be that if there's any friction to changing your action。

 if it's like a little annoying to do so， then maybe like below some threshold of gain。

 you're not going to bother doing it and it's kind of going to kind of be stable anyway。

Like I don't know if you know you've been driving with Google Maps never get these alerts that say you know。

 you get off like 95 here and take this crazy routes and it'll save like a minute and have decided not to do it I generally decide not to do it because of the cognitive load despite like leaving that minute on the table and if you believe that people sort of might think like that。

And you might think that。Approxximate pure strategy N equilibriumria。

 at least for small enough epsilon， are at least kind of stable。And so let's take that seriously。

And think about。A version of better response dynamics where。It's exactly the same as before。

Except now we're going to imagine that there's some threshold epsilon so that you're not going to bother changing your action。

If it won't decrease your cost by at least epsilon。Okay， so， you know。

If they we'll keep going forever while there is a player who's not playing an epsilon best response who can't decrease their cost by at least Epsilon。

And as long as there is one in arbitrary order， we'll let them change their actions to decrease their cost by at least stepson。

 but。If we end up at an epsilon approximate Nash equilibrium， we'll say the dynamic is done。

There's nobody who can improve there。Situation by decreasing their cost by more than epsilon。

 will declare the dynamics in havealed。And we can analyze this just as we analyzed。

The exact version of federal response dynamics。And an immediate parallel is that we can note that like by definition。

Of the halting condition。If this dynamics hs。Well， it halt add an epsilon approximate equilibrium that was the halting condition it halts exactly when there's nobody who can decrease their cost by more than epsilon。

 which is what an epsilon approximate。Pure strategy in Ash equilibrium is。But now。

 in addition to proving that this dynamics halt， we can attach to it a rate。

We can say it actually halts。Pretty quickly in sort of time that is。You know。

 individually linear in all of the parameters of the game。

 the number of players and the number of facilities and one over epsilon。

 the approximation parameter that we're thinking about。And CmX， which is just。

An upper bound on like the maximum cost of any facility， like how long it takes you to traverse。

You know。The Google River Parkway， you know in the worst traffic you can imagine。Whichs not nothing。

 but you know。It's a finite game， it's only going to be something finite。Okay。

 so the claim is that in any congestion game， best response dynamics will。

Halt at an epsilon approximate Nash equilibrium after only n times M times CmX over epsilon many steps。

And the proof。It's almost exactly the same as our analysis of the exact version。

We use exactly the same potential function。We recall just as before that。

At any step of better response dynamics。The change in costs of any of the player who made their moves is exactly equal to the change in potential。

All of that's still true。But now we observe。That our potential function， which we take a look at。

First of all， is always non negative。Because these facility functions。

 these individual facility cost functions， these are non negative。

And the potential is just a sum over a bunch of non negative things， so it's non negative。

So at any moment in time， the potential at any game state evaluates to something greater than zero。

And then the question is， you know， it's going down at every step。

 but how large was the potential when it started？Well， we assume nothing about where it started。

 but we can still give sort of a crude worst case upper bound on how big this potential function could possibly be。

We're summing up over all of the facilities M， there's M of them， so let's pay a factor of M。

We're summing up for each facility。Over the number of players playing on that facility in the game state。

Well， in the worst case， that's all of the players can't be more than all of the players。Okay。

 so maybe each of these sums will actually sum over n people， just pay a factor of n here。

And we're paying you each term in this sum is the cost of the facility when some number of people are playing on it。

 well each of those costs can be at most the maximum cost for that facility。

 which is just this number that we call CMX。Okay， so super crude upper bound。

 but it's just saying look。No matter where we started。

The value of the potential at that action profile， it can't possibly have been larger than M times M times CX。

And it can't ever get below zero。But at every round。The change in potential。

Is equal to the change in cost。And we've assumed that people aren't going to bother to change their。

Action unless they can decrease their cost by at least epsilon。So the change in cost， right。

 we start at this number at every round we decrease the number by at least epsilon and we can't get below zero。

So how long can this go on for？If it goes on for more than n times M times C。

 so we're epsilon many rounds， we'd have a contradiction。We'd have gotten to something below zero。

And so the theorem follows， it can't go on for more than m times M times CAC over we're epsil on many rounds。

Yeah。我要是。I不闪说。Because。We said it did， right。This dynamic。Is modeling？

Otherwise it would have halt it exactly like we're sort of imagining here that people are only changing their action if doing so decreases their cost by at least epsilon yeah so like were this is like this is the difference。

 this is exactly the difference between this dynamic and the exact better response dynamics and we're taking full advantage of that difference。

Okay， so if we only want to approximate N equilibriumlib， we actually get good rates as well。

Right so it's it's a， you know， at least for approximate equilibriumria， you know。

 maybe a fully computationally plausible story a。Permissive， fast。

 dynamic that doesn't require that anyone。Know anything heroic or have heroic amounts of computation that inevitably leads us to pure strategy Nash equilibrium。

好。So thank you guys very much， I'll see you next week yeah。I can this one。是。啊，不意思。Yeah。嗯。Yeah。

 I mean epsilon can be whatever you want， but of course the convergence rate depends by this theoremone one over epsilon。

 so if epsilon's one over 100， it's a factor of 100 here。All right， thank you guys。嗯。这。Yeah。



![](img/5ee4e96fd0a11695379ba8b4969d49ea_2.png)