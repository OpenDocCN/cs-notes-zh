# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p07 NETS 4120_ Algorithmic Game Theory, Lecture 7.zh_en -BV15kLRzTExU_p7-

![](img/23d7e2dd09412192767b4b2254e27750_0.png)

So。Okay。All right， everybody。Thanks for。Tunning in online。

 hopefully next class will be in person again。嗯。Anyone who is willing to please turn on your camera just to sort of simulate to the in person experience as much as possible。

 hopefully。Just as in class， you know， if anything I say is unclear。

 you can you can just you know speak up and ask a question。

Online is a poor imitation of the in person experience。

 but let's try to make it as interactive as possible。So。Just to。Summarize a bit。

For the last two lectures， we took a bit of a break from game theory。And we just studied。Learning。

 we studied sort of over a series of two lectures。The derivation of this polynomial wakes algorithm。

 which is somehow。A way to。Choose actions in some dynamic sequential environments。

And it had some nice properties， the promise was no matter what losses or payoffs were associated with these actions。

If you use the polynomial weights algorithm to choose the actions， then。

You'd have the promise that no matter what happened in hindsight。You the algorithm。

Did as well as whatever turned out to be the best action in hindsight。So。

What I want to do this class is start and we sort of。

Foreshadowed a little bit that you could use this to play a game。嗯。😊，嗯。

But we didn't really sort of bring it all the way back to sort of game theory and so what I want to。

Do this class to start to close that loop。So I want to talk about an important class of games。

 zero sum games。And。Zero sum games are sort of。Both interesting and important class of games。

 but also a very structured class of games。And they've got。

Very interesting property called the Minmax Theorem。

That helps us both think about how one should play in a zero sum game and characterize what the equiria are in zero sum games。

And。What we're going to do this class is we're going to approve that theorem。

 we're going to approve the minim theorem。And。😊，The proof。

Well turn out to sort of fall very easily out of a thought experiment that comes from sort of thinking for yourself。

What would happen if you started to actually play in a zero sum game using the polynomial weights algorithm so it turns out。

Play using the polynomial weights algorithm in a zero sum game。

 this is something we'll prove next lecture。Play actually will converge to Nash equilibria So we you know so。

Bringing this back to sort of a previous theme in the course。

 the polynomial weights algorithm will be。A sort of plausible learning dynamic for convergence equiria in zero sum games。

 but more than that it will help us prove。Interesting structural properties about the equilibrium of zero sum games that are not true in general sum games。

Yeah。U。And so。Yes， so so like the way we're going to use it today is sort of。嗯。

As part of a thought experiment to prove Ethereorem that von Neuman proved in a very different way。

 70 years ago， but now that we know about the polynomialoid algorithm。

 the proof for us is going to be much easier than it was for him。Okay。Okay。So let's， you know。

 remember what games are and sort of。Think specifically about zero sum games。Let's see。

SoR hand just go ahead， you don't have to raise your hand， you can just unmute。好。Sorry。

 I was just wondering if the slides are posted because I don't see them on the website。No。

 they are not yet posted because my VPN was acting up and I can't connect to Penn servers from home。

I just want to check I can if you I can post her in the slackck if you want to。

Refer to them right now。No， that's okay， you can't continue， didn't mean it interrupt。Thank you。

 yeah， they'll be up shortly。😊，Kd a message saying Zoom quit on the s。

 but it doesn't look like it's quit。 Can you guys still hear and see me。Yes， okay。Ohpe。

 keeps telling me that it quit unexpectedly now。嗯。😊，Yep。



![](img/23d7e2dd09412192767b4b2254e27750_2.png)

![](img/23d7e2dd09412192767b4b2254e27750_3.png)

Right right now it's restarted on me， can you guys still hear and see me？Yes， we can。

it still seems to be recording all right， let's share screen again。



![](img/23d7e2dd09412192767b4b2254e27750_5.png)

Okay。Okay。

![](img/23d7e2dd09412192767b4b2254e27750_7.png)

So what's。Two player zero sum game mode it's just what it sounds like it's a two player game such that。

For every action profile and in the two player game， an action profile is just a pair of actions。

 one for player one and one for player two for every action profile。

The utility that player two gets at that action profile is just the negative of the utility that player one gets and so the reason these are called zero sum games is if I sum up the utility of the two players then the action profile。

 it sums to zero。And one thing you might like notice is that there's nothing special about zero。

If I added you know some constant like five to every utility function that wouldn't change the strategic nature of the game at all。

 so you know we could equally well talk about five sum games instead of zero sum games the point is just that these games are strictly adversarial so the only way that player one can change his action to improve his payoff is to harm player two by exactly the same amount and vice versa so the fact that they sum to zero is not important the important thing is that the sum of the utility functions is some constant it doesn't change across action profiles。

And what that sort of means strategically is that。There's no pie to enlarge。

 like any any sort of gain for me is met in equal proportion by a loss for you。不。

And one thing I'll you know， we won't talk about too much but。

I'll just maybe mention for those that are interested。

zero sum games and in particular the mini Maxs theorem that we're going to prove today。

Are really sort of。Fundamental objects， not just in game theory。

 but in computer science and optimization and mathematics and。You know。

 the world and broadly machine learning。And so。You know， if you're interested， like there are very。

 very close connections between zero sum games and linear programming。

 the minimax theorem we're going to prove today is really in a fundamental way。

 the exact same thing as linear programming duality。

If you know anything about adversarial machine learning。

 so GNs and sort of the way people train models for to be sort of robust against adversarial examples。

 these are solving for the equilibriumria of very large zero sum games anyways sort of beyond the。😊。

You know， ability for zero sum games to model strictly adversarial interactions。

 these are sort of really fundamental objects that。😊，You might encounter again and again。But okay。

 like， let's， let's sort of start by。就。Thinking about zero sum games just in sort of the。Simple。

Two by two matrix game， you know， anecdotes of economic game theory way that that we've。

Used before to think about sort of very simple games。And so here's。A simple two by two。

Matrix game that is sometimes called the presidential election game， the story is unimportant。

 we're just going to use this as an example of a simple zero sum game。But you know。

 maybe here's the story there's a presidential election between a Democrat and a Republican and these are sort of。

You know， simpler times before。嗯是是的。Campaign issues might have been things like you know。

 infectious disease and democracy and things， this was back when candidates might choose to focus on relatively mundane things like the economy or the social contract or morality or tax cuts。

And。The idea for this know very simple game is that the two candidates at the beginning of the election have to pick。

What is the issue， the main issue that they're going to focus their campaign on and。

How this issue will how focus on this issue will play out in the election will depend on what their opponent decides to focus their campaign on。

Maybe depending on what the row candidate picks you have to focus on。

The economy or the social contract。Yeah， that will。

Induce some odds that they win the election depending on what the column player chooses to focus on morality or text cuts say where。

Bigger numbers。Correspond to a。You know， larger chance of winning the election and smaller numbers correspond to a smaller chance of winning the election and because it's a。

It's an election， there's one winner， it's a zero of sum game。

 the only way I can become more likely to be elected president is if you become less likely to be elected president。

Okay， so。You can write down。You know。Toy， little game like this as a two by two matrix in the way that we're used to。

😊，没有。Because it's a zero sum game。You know， just like notally， it's a little wasteful。To write down。

Payoff the way we're used to writing them down。 right we're used to sort of writing。

Hairs of numbers in every entry of a matrix like this。

One corresponding to the payoff of the row player and the other corresponding to the payoff of the column player。

But because this is a zero sum game and the column player always gets。

The negative of what the role player does， you know， we can sort of。

More economically write down just the single number in every entry though。系啊。For the row player。

 which we can now think of as the cost for the column player。

 so the row player would like to end up in the sort of square of this game matrix that maximizes the payoff similarly the column player would like to end up in the square of this game matrix that minimizes the cost and the payoff and the cost are the same。

So one player is trying to maximize and the other player is trying to minimize。Okay， and so。

We might as well give our candidates names。Let's call the row player Max because Max would like to maximize the number in this matrix you'd like to maximize the utility。

And we'll call the columnplay min because min would like to minimize the number in this matrix。Okay。

So。I want to think about。How one should。Reason about playing in a zero sum game。

 given that their opponent is， is clever。So， let's。

Sort of go through maybe an exercise in reasoning about this。

 and I'm going to ask you various questions about what people should do and。I don't want you to。

 you know like。ToDo algebraic calculations in your head and give me a number。

 what I'm looking for is more sort of instructions for how to go about。

Thinking about instructions for how you might think about computing those numbers。

 not the numbers themselves。So。U。I want to think about how to play in a zero sum game and I'm going to focus first on order of play。

So suppose that max has to go first。And announce his strategy and Max' strategy could be randomized so Max strategy doesn't have to be。

 you know， I'm going to center my campaign on the economy。It could be that you know。

 max the strategy as well， you know， with probability 60% i'm going to center my campaign on the economy and with probability 40% i'll center my campaign on the special contract so the question is。

If Max。Is sort of handicapped and forced to go first and like reveal his strategy to men and men has the advantage of。

Getting to best respond， you know， maybe she has your spies on the inside of Max's campaign。

 She figures out what his strategy is and gets to choose the best response。Yeah。

 I want to sort of figure out。How Max should think about how to choose its strategy？And。

Maybe it to sort of。Start thinking about this。Suppose。Right you know。

There's sort of two optimizations here if Max goes for Max has to optimize for what's going to happen when min best responds and。

Min best responding is itself an optimization problem。This this nested optimization。

And so let's think about it from the inside out just suppose。Max announceds some particular strategy。

 it's like， you know he's going to randomize uniformly。Um， so like， you know。

 half the time Max is going to focus on the economy。

 half the time he's going to focus on the social contract。

What should men do and here I'm not looking for。Necessarily like which actions you should play but。

What thought process should she go through to figure out what she should do？

Anyone can unmute an answer。So men could， you know， say， like， let her probability of playing。

Morality be alphapha。And then once you define that， you know what her expected utility will be。

 and so she can just choose alpha to minimize。That like expected payoff。Yeah， and I guess。

She might no， even。Right off the bat that like whatever so alpha is it's like the probability she's going to play like morality or something and one minus alpha is the probability's going to play text cuts is that what you're saying right？

Yeah， and I guess she would like know right off the bat that。Alpha was going to be 0 or one。

 Like if you're just best responding to something I'm doing。

 there's no need for you to randomize because your pay off is going to be。

If you randomize between two things， your payoff is just going to be the average of the payoffs of the two things you're randomizing between and know the weighted average can't be larger than the maximum of the two things。

But like you're exactly right that what men should do is she should。

Figure out given what Max is doing， what is the utility of。Playing each of her two actions。

 what's her utility for playing morality， what's her utility for playing tax cuts and she should pick the better of the two and remember Min is trying to minimize the utility so she should write down an expression for her expected cost for playing morality an expression for her expected cost for playing tax cuts and she should play whichever of those two is smaller。

😊，🤧So right she can do that。They can say， look。はい。If Max is uniformly randomizing between these two actions。

 then if I play morality。Half the time。I'm going to get payoff three。

And half the time I'm going to get pay off minus two and so my expected utility will be half times three plus half times minus two。

 which is one half。And similarly。Yeah， so she can make to herself well if I pay by tax cuts。

 if Max is uniformly randomizing。Half the time I'm going to get pay off minus one and half the time I'm going to get pay off one and so my expected utility is know half times minus1 plus half times one。

 which is zero。And。Men is trying to minimize the payoff。Yes。

And so having gone through this calculation， she should put taxco。Right， like。

You her best response problem is pretty straightforward given that she knows Max's strategy。

 she just for each of her actions， computes the expected cost of that action and she chooses the action that minimizes the expected cost。

Okay。And。We can generalize this， of course， right it like the particular numbers here were specific to。

Max announcing this like uniform distribution one half， one half on his two actions， but。

The basic logic is straightforward， no matter what Max announces。Yes。So more generally。

If Max announces that he's going to play。According to some mixed strategy。That puts weight P。

On focus on the economy and weight  one minus P on focus on society。Then。😊，What men should do？

Is she should go ahead and。Under Max's distribution。

 figure out what her expected cost is for playing each of her actions and then play whichever action minimizes that expected cost。

Okay， so we can write that down。Right。Yeah。Her cost for playing morality if Max puts weight P on economy is going to be P times3。

Plus1 minus p times minus2。And。Her payoff for blank tax cuts is going to be P times -1 plus 1 minus P times1。

 Okay， and she will play the action that minimizes。These two expressions， either know。

 the expression for her payoff for morality or the expression for her payoff for tax cuts。Okay。

So if we can work this out， then Max can work this out， right？Min and Max are are。Not， yeah。

 they're not going to cooperate here because it's a zero sum game， right。

 anything that's good for men is bad for Max and so。

Max knows that this is the logic that Min is going to go through if Max announces some particular strategy。

🤧。嗯。😊，And so the question is。Knowing this， what strategy P1 minus P should Max announce？

To maximize his payoff after Min best response。Right， what your backs do。Again。

 I'm not looking for like a number looking for sort of a thought process。Yes。好。

Should he choose a value of P that like maximizes this argument function exactlyact right。

 like he knows what's going to happen if he plays P1 minus P。If he plays P1 minus P。Then。

The utility that he's going to get。Is the utility for the action that Min chooses。

But he knows that Min is going to choose the action that minimizes the utility between her two choices。

Right， so。😊，You know， maybe。Covering up， I cover it up on my screen with my finger。

 It doesn't cover it up for you。 but covering up the。Arg Max for a moment。

Max knows that if P plays thumb strategy P， then the utility he's going to get is whichever is smaller。

 3 p minus2 times 1 minus p or p times minus1 plus1 minus and so。Since he wants to maximize that。

 he should play the action， the he should play the distribution P that maximizes this minimum。Right。

 so in the given that he knows what man is going to do and given that he knows that。Men is going to。

Act in a way that is sort of contrary to his own interests。

Max should play the strategy that maximizes the minimum。Okay， is that clear？So there's this。

If we're thinking about what Max should do。There's this nested optimization， this maximum term。

He should play the strategy that maximizes the minimum over men's two actions。Okay， now。

Things are symmetric for men， of course。We've been thinking so far about the situation。

In which Max has been handicapped and has forced to reveal his strategy to men and let her best respond but。

What if the tables were turned right like if if Min was the one who was under this handicap was forced to reveal her strategy to Max and let Max best respond。

Then。She could go through an equivalent chain of logic， she could say well， look， you know。

 whatever strategy I announced that puts probability Q on morality。

I can figure out what is the expected utility that Max is going to get if he plays economy and if he plays society and I know that if he gets to best respond。

 he's going to pick the action among those two that maximizes his utility。

 I'd like his utility to be as small as possible so I should pick the queue that minimizes that maximum。

Okay， so if Max goes first， he should solve this max min optimization problem。And if Min goes first。

 she should solve this min Max optimization problem。Okay。So let's。You know。

 just to get a better sense of this， again， this particular toy game。

 hopefully' maybe go through this exercise of figuring out what mins should do， what Max should do。

And how much of a disadvantage it is to have to go first。Right， so。Yes。

It's sort of clear to think about it。That in a zero sum game。

Like going first is definitely only a disadvantage。 you can't be an advantage。

 like because what you're doing is your。Revealing information to your opponents that they wouldn't have otherwise that they can use to try to harm you right like their only goal is to minimize your utility。

And so whatever they would do if they got to go first。

 they could still do it if they get to go second， but maybe they could do something even more clever that would harm your utility even more if they have knowledge of what you're doing right so giving up your strategy。

 revealing your strategy can only be a disadvantage。Okay。But。You know。

 it's not clear how much of a disadvantage it is， let's see， let's work it out in this case。Okay。嗯。😊。

Oh， maybe one。Sort of thing worth noting。If you look at。The payoff。That。The cost， let's say。

 that men has for playing morality。It is increasing in P the weight that Max puts on economy。

 if Min plays morality， then the payoff that she gets is increasing in the weight that Max puts on economy because the payoff for economy is positive and the payoff for society is negative。

Yeah。Similarly。If men plays tax cuts。Then。The payoff she gets is decreasing in P。

 the weights that Max puts on economy because the payoff when Max plays economy is negative and when he plays society is's positive。

And so。If we sort of imagine plotting out。U。Plotting out。As a line， the payoff that。

Min gets the costs that men experiences。If Max as a function of the weight that Max puts on economy。

 this line has positive slow。And if we imagine plotting out as a line。

The payoff that Min gets cost of min experiences as a function of the weight that Max puts on economy。

 this line has negative slow。Okay， now Max is going to。Pick a point on the X axis。

 like let's say that the X axis here。It's P。对。Okay， Max is going to pick a point on the X axis and。

Min is going to play whichever of these two lines is below the other one。

 she's going to pick the action that minimizes the cost。

And Max would like to maximize the height of the point she ultimately picks。So。

Knowing this like geometrically on this like plot。Which point P should Max pick。

The intersection section。She should picked the intersection， right。

 he should pick the intersection because。😊，You know， if I， if I plot out the maximum of these two。

Of these two lines， right？The maximum is sort of like this upper envelope up here。くちく。And so。

The maximum is minimized here at exactly the intersection。Okay。So if。😊。

Max would like to maximize the minimum payoff of these。So there's two curves here。

 he should pick the P that causes them to intersect should。

He should sort of randomize between economy and society。Exactly in the proportion。

That would cause men to be indifferent between her two actions。Okay， so。This makes。

Max says computation very easy。Right like。😊，He knows that Vi's payoff for playing morality if he plays economy with probability P is exactly 3 p minus2 times 1 minus p。

And he knows that。Her cost for playing tax cuts is exactly p times minus1 plus1 minus p。Okay。

And so if he wants to。Minimize or maximize the minimum of those two。He should pick the P that causes。

These two expressions to be exactly equal。Okay， so it's just a little bit of algebra。

And when you work out the algebra。Yeah， Max would figure out， okay。

 he's supposed to the thing he should do if he has to sort of play defensively like this。

 if he has to go first。Reveal his strategy and played defensively so that。

Things are as good as possible for him when men best responds。In this case。

He should focus on the economy with probability 37s。Yeah。Okay， and of course。

You should to put the remaining probability four sevenths on society and so we have a mixed strategy for MA here。

😊，嗯。Now。This mixed strategy is designed so that。Min is exactly indifferent between her two actions。

 she's exactly indifferent between playing morality or tax cuts。

And so we can work out that the payoff that Max will get when Min best responds is well。

 it doesn't matter what she plays when she best responds we work things out so that。

No matter how she plays， the outcome is the same and it's one seventh。Okay。

 so so just to sort of like remember now not that the number is like deeply important， but like。

In this particular example， when we put Max at a disadvantage and forced him to reveal his strategy。

 but then Max played optimally。He could still guarantee himself pay off at least one seven。Okay。

 he gets to pay off one seventh here when he is in the position of disadvantage。So let's think now。

About how much better he can do if we put him in the position of advantage。

 if we make Mingo first and give Max the opportunity to best respond。Right。

 like things should only be better for him。 So that his payoff should be， you know。

 like at least one seventh and maybe better。So again， like the computation， know。

 the logic that Min goes through。嗯。Should be exactly the same as Max went through a moment ago。

You know， we've got these two curves representing the payoff。

That Max gets as a function of the probability that Min puts on one of her actions， same morality。

And the payoff curves for these two options Max have opposite slopes。And。

Max is going to pick the alternative that maximizes his payoff。

And min would like to make that as small as possible。 and once again， the maximum is minimized。

Exactly at the point at which the two curves intersect。And so。Like men can。

 that's as Max did think to herself， okay， well。You know I should put weight on morality Q exactly such that my mixed strategy Q and one minus Q makes max exactly indifferent between his two actions。

so we can write down， as a function of  Q， what is max is payoff for focusing on the economy。

 it's 3q minus1 minus Q。And we can write down what is his payoff or focusing on the special contract。

 it's minus two times  Q plus1 minus  Q。And。Men is looking for the value of Q that equalizes these two。

A line of algebra， she can work it out， it's two seventh she should focus on morality。

 two seventh of the time。有。Okay， so Min has some other mixed strategy if she is in the position of disadvantage。

 she should focus on morality two seventh of the time and tax cuts， five seventh of the time。

Once again， when Max best responds， well， it doesn't really matter what he does。

 Min has rigged things up explicitly so that Max is indifferent between his two actions。

 his chance of winning the election is exactly the same。

 no matter which of economy or society Max focuses on。

 that was that sort of a characteristic of Min's defensive strategy here。And when Max best responds。

His payoff is， again， we can work out 17。Okay， so。Okay。Something a little interesting happened here。

嗯。When we put Max at the position of disadvantage of having to go first。

 but allowed him to play optimally， we found that。Despite being in this position of disadvantage。

 he could get himself pay off1 seventhth。But that even when he was in the position of advantage of knowing Min's strategy ahead of time and getting to best respond。

 he still couldn't do any better than17。In this case， although of course。

 it wasn't a disadvantage to go first。It wasn't really an advantage either。看。Sure。嗯。Okay。Okay。She。So。

Yeah， so I want to like think about this and think about whether this is。

A quirk of this game or whether this happens more generally。And what the implications of this are。

Good。So。These strategies that we computed for men and maths， right you know， we're sort of。

Not we weren't thinking like equilibrium like thoughts。 We weren't thinking， okay， like。

 you know what's a stable。Dates that we might both find ourselves in。 we were thinking， sort of。

Defensive play thoughts， because normally when were when we think about like。

Playing in a matrix game like this， we think about。

What happens when both players play simultaneously and remember equilibrium， of course。

 is a state in which both players are simultaneously best responding to the other。But。

When we derived that Max should play。You know， three seventh， four sevenths。

We were thinking about how Max should sort of play defensively in this sequential interaction where first he had to reveal his strategy and Min got to best respond and when we derived that men should play two sevenths。

 five seventh，This was again in this sort of defensive sequentialial situation where。You know。

 like Min was thinking how she should do what would she should do if she first had to reveal her strategy and allowed Max to best respond right so there was no thinking there that Min would like we knew that Max would best respond to what Min did in that situation。

 but there was no thinking that min should also be best responding to what Max did because。

Max got to move after men。Okay。But。Because the payoff for both players was one seventh。

 regardless of whether。They moved first in this interaction or whether they moved second。

Like actually in this game。😊，It must be that this pair of strategies that we derived in this defensive manner。

 three，7， four sevenths for max and two/ seventh， five sevenths for men。

It's actually a N equilibrium of the game in which both players get payoff one7。

And the reason is because， you know。We know that when。Max。

Plays according to this that Min can force the cost to be17， even when she is best responding。

 and she can't do better than that because she's best responding。Similarly。

 when min commits to this strategy two seventh， five/ seventh。

Max can force the payoff to be at least 17。Even when he's best responding and of course he can't do better than that because he's best responding so when both players are playing these strategies and simultaneously getting payoff one seventh。

They must be both simultaneously best responding to each other's strategies。Okay， so。

 so like one thing to observe is the fact that。W。In this game， the payoffs turned out to be equal。

 independent of the order of play meant that。He。By computing these strategies in this sort of defensive sequential way。

whichch was sort of easier than computing strategies， equilibrium strategies in general。

 there was no circularity here the way there normally is in equilibrium computation。

 we were just sort of computing you know like two steps of rational thought。😊。

I meant that like we were actually computing Nash equilibrium of the game。

 that's one thing to notice。And so like let's， let's maybe。

Investgate further and see if this is a more general phenomena that happens in zero sum game。Okay。

 so。Okay， so so far we sort of talked very concretely about a particular zero of sum game。

The next part of the lecture， I'm going to， you know jump into abstraction and prove a theorem about like general zero sum games。

 so let me pause here。To ask if there's any questions about。

Anything we've talked about so far because because it is a good time to ask questions because so far。

 yeah， we've talked about very concrete things， very concrete calculations， but it's gonna to get。😊。

More abstract soon， so let's make sure we all are on the same page。So any questions？Good。Okay。U。Pool。

So like that was a very simple。Example of a zero sum game each。U。

Each player only had two actions and so we could think of their mixed strategies just as being defined by single numbers。

 P and Q。But。More generally， a two players or some game could have a bunch of strategies， let's say。

let's use n to denote something that might be the number of actions available to a player in a zero sum game。

 when I write n in brackets like this。I mean this as shorthand for。The set of all actions。

 one through N。Okay。And similarly， when I write。Delta of n like this。 What I mean is。

The set of all probability distributions over those actions。Okay。Yeah。Yeah。And so。

Let's now think of an arbitrary two player zero of sum game。

In which the row player has an actions and the column player has M actions。Okay， and remember。

We can always represent such a zero sum game as an n by M matrix that I'll call you。Okay。

 you can think about the entry， the IJF entry， the entry in this matrix。Corsponding to row。

 I and column J。You can think about that as the utility that。Max。

 the row player will get if he plays I and Min plays a J。Okay， and we only need one， you know。

 the reason we can think about a matrix instead of。

These sort of more general games that like in which in each entry there's like a tuple of payoffs one for each player is because。

In a zero sum game， we only need one number。 We know that Max wants to maximize that one number。

 and min would like to minimize it。Okay， so we can think of a。Zero sum game， a general。

 zero sum game。As being represented by some N by M matrix。

Where n is the number of actions available to the row player， one for each row。

 and M is the number of actions available to the Helen player。And。Given such a game， we can define。

What I'll call the max min value of the game and the min max value of the game。

Exactly sort of analogously to how we thought of these things in the presidential election game。

In word， I'll sort of say it in English and we'll sort of go through the math。In words。

 the max min value of the game is the payoff that Max can guarantee himself if he is handicapped so that he has to go first and announce his strategy and min is able to best respond and the min max value of the game is conversely。

😊，Value of the game that Max can guarantee himself if。

Min is the one who's handicapped and has to announce search strategy first。

 and then Max has the ability to best respond。Okay， so let's just walk through this。

The max min value of the game， remember this is the payoff that Max can guarantee himself if he's forced to go first that's why the max is sort of on the outside here max is the player who's going first。

So， Max is going。Announce some mixed strategy to men， okay， so。

He'd like to choose the mixed strategy that will maximize his payoff after Min Best response。

 so he's going to choose some distribution over his an actions and he'd like to choose the distribution that maximizes whatever comes next。

Now what comes next。Next， Min gets to best respond， and he's going to choose。

The action of hers why that minimizes Max's expected utility， given her choice。Okay。

 so for each action Y she could choose Max's expected utility is just the average over all of the actions that Max could play of the probability that he plays that action of the utility that he gets when he plays that action and when Min plays y and right so so the inner expression here is just。

😊，The expected utility when Max plays this mixed strategy P and min plays this pure strategy Y。

 and what Min is going to do is she's going to pick the action and the pure strategy that minimizes the expected payoff。

Okay， and so Max would like to pick the mixed strategy that maximizes the payoff after Min minimizes if Max is going first。

Similarly， the min Max value of the game。😊，Is the value that Min can sort of force if she's handicapped and has to go first so she would like to pick。

The distribution over her actions， the distribution Q over her M actions such that。

After Max gets to go second and best respond and choose the action that maximizes his expected payoff with knowledge of Min's。

Mix strategy that the resulting payoff is minimized。Okay， so， so。

Let me pause here and ask if this is there because there's like some， you know。

 like notational burden here， but I think。The idea is， sort of。Pretty simple and intuitive。

 especially after we've gone through this presidential election game。

It's just sort of each of these is sort of like a two level optimization sort of。You know。

 thinking one step ahead of what your opponent is going to do。

 I'd like to choose the action that gives me the sort of best payoff if I max that maximizes my payoff after men gets to best respond and vice versa。

Okay， is it clear what the maximum value of the game is and what the min Max value is and how this sort of generalizes our discussion of the presidential election game？

要。Okay。嗯。So remember。I think this is hopefully intuitively clear end。嗯。😊。

It's a couple of lines of math if you want to。Work it out。 It's a good exercise。That。

In a zero sum game。Going first cannot possibly be an advantage。And the reason is pretty intuitive。

 it's that。Okay。Your opponent just wants to。Minimize your utility。And。By telling them your strategy。

 you're not removing anything from their strategy space。

 you're not making it so that so that they can't do anything they would have done without that knowledge。

 but you're giving them additional information that they can choose to optimize and using if it's useful but they don't have to right so like giving them additional information。

Isn't going to harm their optimization， can't make their optimization。Problem like， you know。

 less favorable to them and it could because they can always ignore it and it could make it more favorable。

Okay， so just sort of。Writing that observation down。In the notation， we just。The established。

What this says is。For any zero sum game U。The min Max value of the game。

Can only be larger than the max value of the game right because going first being on the outside of this optimization procedure right Max goes first if he's solving the max problem。

Going first can only be a disadvantage， and max would like payoff to be higher。

 so the max min value can only be smaller than the min Max value。Okay。Is that clear。嗯。Now like this。

Basic facts。About zero sum games， which is called Von Neuhman's Minmax Theorem。

The interesting part of it is the other direction of this inequality。Right。

 sort of like straightforward that going first。Cannot be an advantage。But。Okay。

What the Minm Max theorem says is that a zero sum game going first is actually not a disadvantage either。

Yes。And the presidential election game wasn't like。Unusual in this respect。

 this is true of all zero sum games。No matter what the order of play is。

 whether min has to go first or whether Max has to go first。

Payoff they can obtain if they play optimally is the same。

The min max value is equal to the max min value。And so there's。You know。

 a couple of interesting corollaries of this theorem， which we're going。

 we're going to prove the theorem in a moment。U。It's like first of all。It must be that。

In any Nash equilibrium of a zero of sum game。Max must be playing a maximum strategy， in fact。

 any maximum strategy will suffice。And men must be playing a Minm strategy。

 any Minm strategy will suffice。W so this is sort of。Immediateates， but like。

If this weren't the case， right， it would sort of mean that。You know。

 there was an advantage right if the if the。嗯。😊，If this weren't the case then。Yeah。

It would mean that they could sort of break out of equilibrium by committing to something。

And going first。And my opponent like wouldn't currently be best responding to it。But。

I can't do that because the min max value is equal to the maximum value。

And one interesting thing about this is that。In general， thinking about。

Equiilibrium strategies and computing them in general it seems tricky right because it involves this sort of circular counterfactual reasoning like I want to play something that's a best response given what my opponent is going to do but I need to like think about what my opponent is going to do in order to make that you know like a sensible optimization goal but like they need to think about what i'm going to do right so like。

😊，In general。Nashation equilibrium I have this sort of。P。

Fixed point feel to them is's a sort of circular counterfactual。

Counter speculation that I need to engage in。 I need to think about， you know。

 what would my opponent do， given what I'm going to do， But you know。

 like to figure out what I'm going to do， I need to think about what they're going to do。

Back and forth。But。We didn't need to do that to compute min Max and Max Min strategies in the presidential election game or。

 you know， more generally in any zero sum game， we just needed to like solve like two steps of optimization right we needed to compute basically。

Min's best response problem right like we need to solve just a best response optimization and then maxes outer optimization。

As a function of what Min was going to do Okay， so so somehow this makes zero sum games a little bit easier to think about。

😊，And it also means that。Because there's this thing called like the value of a zero sum game。

 the Min Max value， which is the same as the max value。It must be that。

At every Nash equilibrium of a zero sum game。I will have the same pair。Right。

 like my value for the game， which is not in general， true of other games， right。

 like in other games， we've sort of。Thoughought about already。

 I might prefer one equilibrium over another， the equilibrium might have a very different payoff for me。

But that can't happen in a zero sum game。Okay， so let's just like note that these things are not。

In general， true of general sum games like。In the Bauffins Strinsky。

 in a little toy example we went through early in the class。嗯。You know。

 I prefer the Bky equilibrium to the Strinsky equilibrium and my wife prefers the opposite right so that's like the kind of phenomena that cannot happen in a zero sum game because of the mini Max theorem。

嗯。It means zero sum games are easier to play than general sum games。

 there's no need to engage in counter speculation， you just have to think about playing defensively。

And one thing I want to note just because we're going to give such a。Slick proof of this is that。

The theorem is not at all obvious， so Von Neummann first proved this theorem in 1928 and he wrote。

As far as I can see， there could be no theory of games without this theorem。

 I thought was I thought there was nothing worth publishing until the minimax theorem was proved。

And Brell， who was， you know， another smart fellow。

Thought that he'd proved the special case for five by five matrices and thought it was false for larger matrices。

😊，Okay。And in general， this is， you know， what we're going to prove is sort of equivalent to something called linear programming duality。

 which has lots of important implications， but anyways。

 the reason that Brel and von Neumman had to work so hard at this is because they didn't know about the polynomial weights algorithm so the fact that we have studied and derived the polynomial weights algorithm is going to make our lives easy。

😊，Infinitive。I think seeing how the proof works will also help us。

Appreciate what the polynomial weights algorithm is doing。

 there's some sense in which the polynomial weights algorithm is a constructive version of the minimax theorem。

Okay。So let's prove it。对。Wait， I have a quick question。 Yes。

 is it this is only for two players or some games or like this is only for two players or some games。

 Yeah， like， this is a good question。 Next class， we will。😊。

Think about what happens if there's more than two players。Yeah， that's worth thinking about。

How much of what we're talking about for two players or some games is true for end players or some games if any of it。

Will。Talk about that next class， but yeah， it might be might be illuminating to just sort of yeah think about it when you're falling asleep。

 so let's prove this okay so like。U。😊，So we want to prove that the min max value is actually equal to the max min value。

And the interesting part of that proof is。Showing that the maximum value。

Is at least the Min max value， right， that this direction is sort of immediate that sort of revealing information to your enemy is never a good idea。

😊，Okay， so。Suppose it were false， suppose the Minm theorem were not true。

That would mean that there actually was some game U for which it really was a disadvantage to reveal your strategy to your opponent。

Okay in particular， it would mean that the min Max value of the game。

 how much max could guarantee if he got to go second like actually was strictly larger than the max min value of the game。

 like how well he could do if he was forced to go first。And so in particular。😊。

We could give names to these numbers。 we could say， look， the min Max value of the game。

 like how much。Max can guarantee if he has the privilege of going second， let's call that V1。

And the maximum value of the game， like。How much Max can get if he's disadvantaged and has to go first。

 we'll call that V2。And。😊，The assumption that。And the min max value is strictly bigger than the maximum value。

That's sort of like saying， well。V1 is equal to V2 plus epsilon。

For some value of epsilon that is like strictly bigger than zero。

Like V1 actually is bigger than V2 by some amount。Okay， so so like。

 setting up like a proof by contradiction。If the。The are more false， there would be some game U。

 there would be some value V1 strictly bigger than V2 such that。If Min has to go first。

 then Max can guarantee himself pay off at least be one， but if Max is forced to go first。

 then he can guarantee himself pay off only the two， which is strictly smaller。And so。😊，You know。

 this theorem。It's like in some sense， just like a statement about matrices right like there's no time there's no dynamic so there's no time aspect to the theorem。

But nevertheless， like the way I want to prove the theorem。Is by conducting a thought experiment。

In which men and Max are repeatedly playing against each other in this game。

 you about think about in this thought experiment。As play proceeding according to some dynamic。

 just like we thought about when we thought about best response dynamics in congestion games。Okay。

 so in the thought experiment， there is time。😊，🤧，And here's how。Min and Max are going to play。Okay。

So Min is going to play this game using the polynomial weight algorithm that we derive class class。

Okay， so what does that mean remember？How the polynomial weight algorithm works。

It maintains weights across these different actions。We're going to associate。

The actions in men's copy of the polynomial L algorithm with like men's actual actions in the game。

Min has M actions。 He will run the polynomial weights algorithm by initializing M weights。Every day。

The polynomial weights algorithm maintains a probability distribution over these actions that will be mins。

Mix strategy。At that round， which she will play。And then Max will do something。

And that will lead to some costs。For each of men's actions。Okay。

 just like the cost specified by the game matrix given what Max played。

 and that'll be the cost that we feed to the polynomial weights algorithm for each action to update the weights for the next day。

Okay， so let me just make sure that sort of this is a sensible thing to everybody that I can talk about men。

Playing a game。Using the polynomial waste algorithm to determine what her mixed strategy is。

 Is that clear。Okay， so min is going to play the game using the polynomial weights algorithm and what's Maxm going to do。

Well， every day。Max is going to。Look at what the polynomial L algorithm。

I doing it's not a secret right like he he can just look up the lecture notes from last class and you know he knows what the history of play has been so far。

 so he knows exactly what probability distribution the polynomial weights algorithm is suggesting that men play every day and Max will do the very natural thing of best responding to it every day。

😊，Okay， so what Max is going to do every day is just。

Best respond to M's strategy I mean said another way。

If WT is the mixed strategy maintained by the polynomial weights algorithm at weight t at AT。

 then max is just going to play the action that maximizes his expected utility given Min's mixed strategy。

Okay， so this is。Some I'm sort of laying out some dynamic。I've told you。

What both players are going to do at every round。 Every round men will look at the history of playup until now。

 she will。Use the polynomial weights algorithm to define a mixed strategy， and you will play that。

Max will best respond to that mixed strategy and they will do this over a sequence of T round。Okay。

 so this is some well defined dynamic that we can think about。

Are there questions about this thought experiment， like what it is we are thinking about？Okay。

So what I want to focus on is。😊，What we know about each player's average payoff as they interact in this play dynamic over time。

And let's start with men because we just。You know， finished last class。

Driving the guarantees of the polynomial weights algorithm。

 so we know something about what men is going to be promised。Alright， so。First of all。Okay。

Like we can just write out syntactically what is？The expected cost to men over time。

 whilst is the average over the T steps of this interaction。Of。😊，The expected utility。嗯。

When Min plays according to her mixed strategy and Max best responds。嗯。😊，And。

Remember what the polynomial weights algorithm promises？

Remember these utilities just correspond now to the losses experienced by each of men's actions。

And remember， the polymial weight algorithm promises that。M's actual realized average utility。

Will be no more than the average utility of whatever turns out to be the best action in hindsight。

 the minimum cost action in hindsight plus some like regret term that goes to zero。Okay， so。

What is the best action in hindsight， Well， after tea days。You know。

 when we actually see what action Max has played at each day T X T。We can ask， well。

 what is the action that men has in hindsight that would have？Minimized her。

Expected cumulative costs or expected average costs， given what Max actually did。And。

That's the best action in hindsight。 And so what the polynomial weights algorithm promises is that。

Min's realized average utility is no more than the average utility of her best action in hindsight。

Plus， some regret term。Okay， and we can sort of manipulate this a little bit， right， like， you know。

 okay， like we're taking the minimum。Overall of。Men's actions in hindsight， you know， like。嗯。

Inside of this average， but like。Yeah， we might as well have taken it outside of the average。

 so I can just write this just sort of moving the min outside。As。The action that minimizes。嗯。

The utility。Averd over the T rounds like this。And。😊，Synactically， right？

I can notice that this is an expectation。Right， it's like。An average over key things。

 my utility at round little T for each round little T ranging from one to big T。

The state uniform average。And so。I can think about this as。The utility that。

Men would get playing the action Y star against。The mixed strategy for max that happens to put weight1 over T on each of the actions Xt。

Okay， which I'll just call X bar。So just because syntax can be confusing。

Like say this again because really。Mathematically， nothing has happened here。

 but there's sort of an important change in perspective。Okay。

 so what the polynomial late algorithm promises。Is something about sequences of play。

It says if you play the polynomial weight algorithm or T rounds in sequence。

Then your average utility over those T rounds。Is no more than。

The average utility of the best action in hindsight over those T rounds。

And all we're doing in this last step is we're sort of noticing that。For any particular action。

 why star？My average utility for playing Y star over T rounds。It's the same thing as saying。

My expected utility for playing Y star when my opponent is playing a mixed strategy。

That just randomizes uniformly over the actions that she played over the last tea round。ok。

And all throughout here， Delta T， it's just the regret bound of the polynomial weights algorithm。

 this thing that。We proved。We can drive arbitrarily close to zero by just planning for long enough。

Okay， look something like this。Okay， so any questions about this so far？

Basically all we've done so far is we've。Remember the promise of the polynomial weights algorithm。

 it says that if I play a game with the polynomial weights algorithm。

My expected cost is no worse than the expected cost of the best action in hindsight。

And we've sort of said， okay， that turns out to just be another way of saying。

My expected cost is no worse than。The cost of my best response。

Against the mixed strategy that corresponds to my opponent。Playing。

Uniformly at random according to their play history。あ。But。

If we look at what we've transformed this into at the end。Right。

 like the payoff that I get by best responding to a mixed strategy of my opponents。You know。

 the path that Min gets。That's only smaller than。The payoff she would get by best responding to the worst possible mixed strategy her opponent could play right that's the maximum value of the game。

Okay， and we give a name to the maximum value of the game that was B2。And so。What we get is that。

If men plays according to the polynomial weight algorithm， then the expected payoff in this game。

Is upper bounded by V2， the maximum value of the game plus this regret term Delta T。Okay。

 and the reason is because。Well， the maximum value is sort of。

U how much Min can guarantee if she gets to go second and getting to go second is like having the opportunity to play the best action in hindsight after you know what your opponent is doing。

And that's exactly。That's exactly what the maximum value of the game is。

And then what the polynomial weights algorithm promises right so that you're competitive with。

How well you could have done had you gotten to go second？So。On the other hand。

 right we've just thought about。The average payoff of the game over time by taking the perspective of men and and thinking about。

What the polynomial weights algorithm requires。On the other hand。

 we can analyze exactly the same quantity， but taking Max's perspective。Okay， so。

It's even simpler from Max's perspective， Max is literally just best responding to men's mixed strategy every day。

So Max is literally in the position of getting to know what men's strategy is every day and best responding to it。

😊，And so in particular。嗯。You know， like he's， he's getting every day。

At least the min Max value of the game because the min max value of the game is。

A bound on how well he can do if he gets to go second and we've set things up so that he does get to go second。

So because Max is literally you know， getting to best respond to Min's mixed strategy every day。

We also know。That every single day， he is getting utility at least to be one。And so in particular。

 the average utility has to be at least to be one。😊，Okay。So， on the one hand。

The average utility is at least v1。That's because Max is best responding。On the other hand。

 the average utility。Over this experiment。Is at most V2 plus deelta T？😡。

Because men is playing according to the polynomial weights algorithm。

And remembering that V1 we've assumed， is equal to V2 plus epsilon。This means。

In order for this to be true。It's got to be that epsilon is less than delta of t。

The regret bound for this algorithm for polynomial weights。对不起。But。Delta T。

Is this expression that goes to zero as t grows large？

Rant it goes to zero at a rank of one over rootee。And this is our thought experiment。

So whatever epsilon is， and you've assumed we've assumed that there's like some concrete epsilon bounded away from zero。

Whatever Epsilon is。We can just take T large enough so that the regret term is smaller than it。

And that leads to a contradiction and proves the minim there。Okay， let me just。

Take a moment to reflect。U。So。In a very strong sense， the polynomial weights algorithm。

Really is sort of。A constructive version of the minimax theorem。

 that's why the minimax theorem follows so。Directly from once we know the polynomial weights algorithm。

Because。It allows you to be in a position of playing first。Like in this thought experiment。

 Min was playing first， was announcing that she was using the polynomial weights algorithm。

 and Max was best responding to that。😊，And yet。Yeah， it it。

You had guarantees that you could do as well as you could have， if you had gone second。

Because the promise of the polynomial await algorithm。

Is about doing as well as the best fixed strategy in hindsight in hindsight means after you've observed what actually happened。

😊，So like doing as well as the best fixed strategy and hindsight means really doing as well as if you had gotten to observe everything and then go second。

😊，Okay， so you can play first， but do as well as if you had played second。

Really what the Mind Theor is about。不是。U。If you think about the proof。Also， it means that。

It's a pretty good idea to play the polynomial weights algorithm in a zero sum game。Right， because。

I'm always going to do as well as if I got to go second， no matter what my opponents are doing。Okay。

 so。Even if I don't know very much about the game， maybe I don't even know the whole game matrix。

I'm just getting enough feedback to play the polynomial awaits algorithm algorithm。

 which is just sort of what are my payoffs given what my opponent actually did？It promises me that。

I always get my value for the game， sort of my safety value。

That I could have obtained had I known the whole game and sort of optimized defensively against my opponent。

No matter what they do， I might be able to even I might be able to do better。

 in fact I'll do as well as。If I was in the position of getting to best respond with full knowledge for what my opponent was going to do。

So it sort of means that。😊，嗯。Even if you know very little about the game。You can always。S livev。

Get the payoff you would have had you played optimally。Using the polynomial weight algorithm。

 at least if you're in a zero sum game。Okay， it is able to do this again。

Like without knowing much about the game， right， like if you think about。Um。You know。

 let's say a zero sum game in which each player has n actions。Yeah。

The game is defined by n squared numbers right， like for every choice of the row player。

 for every choice of the column player， there's a number in there。

But the convergence bound of the polynomial L algorithm。Depends only logarithmically on end。

So it means that you can。Get within epsilon of the value of the game of sort of playing of how well you could have done。

 had you studied the game and played completely optimally。After only。About log in many rounds。

 after which you've only really seen。A tiny fraction of this payoff matrix right like because to run the polyial release algorithm。

 you only need to see the sort of rows of the payoff matrix corresponding to the actions your opponent actually played。

😊，Okay， so somehow like the the polynomial weights algorithm allows you to learn to play optimally in a zero sum game。

Without having even really seen most of what defines the game。ok。

So withs that and the last of my remaining voice。Let's end it there， hopefully by Thursday。

I'm healthy enough to do this in person。See you guys next time。Okay。Thank you， Professor。

Thank you Yeah， thanks for coming。Thank you。

![](img/23d7e2dd09412192767b4b2254e27750_9.png)