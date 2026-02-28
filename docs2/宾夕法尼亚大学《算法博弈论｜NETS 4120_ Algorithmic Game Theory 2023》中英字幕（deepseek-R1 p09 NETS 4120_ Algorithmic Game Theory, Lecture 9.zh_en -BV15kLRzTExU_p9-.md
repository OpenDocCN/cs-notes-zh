# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p09 NETS 4120_ Algorithmic Game Theory, Lecture 9.zh_en -BV15kLRzTExU_p9-

Any epsilon whatever you're saying all right。

![](img/f7b2e7095c5df2198331cc44c940ef51_1.png)

Welcome back to the in person version of Nets 412， or I guess we've now added zeros to the end of all of our classes。

 so Nes 4120。Happy Valentine's Day and just to sort of。

Check off the sort of administrativeminista hopefully everyone turned in their second problem set just now the third problem set is out it's due in two weeks there's only six problem sets in the class so this means we're approaching the halfway point pretty good。

😊，嗯。And are there any questions before we launch in？Okay。So let's see， so I want to， oh， yes。

It's a good question， should I release the answers？Certainly you can like ask。

In office hours or on slackck， what the answers are， and I will tell you the answers。

 but I'm not sure I want to like post。A document with them。对。嗯。Yeah， so let's see。Other questions？U。

So I want to， you know， if you sort of remember。In the first lecture。

 we sort of spent a bunch of time thinking about all right， do you know like。

We've got this general principle in game theory that。Play should end up。At stable states of the game。

 whatever that means。And then we sort of。Thought for a little bit about various ways of formalizing that and we sort of had。

A whole host of solution concepts we sort of thought about dominant strategy， Nash equiria。

 things you could find by iterated elimination of dominated strategies， pure strategy。

 Nash equilibriumria， mixed strategy Nash equilib。And you know there were problems with some of these early ones。

 like there aren't always dominant strategy in a equilibrium， for example。

 there aren't always mixed strategy or sorry there aren't always pure strategy in a equiria。

And by the time we got to mixed strategy Nshlibbriria， you know。

 happily we had Nash's theorem that tells us that at least these things at least in finite games they always exist so at least we've got a way to。

In principle， like。Put some technical wood behind this。

Otherwise nice sounding premise that like play should end up in stable states like we had a formal way of defining what is a stable state that。

Like in principle led to a prediction in any game because Nash proved that every game has a mixed strategy Nash equilibrium。

And in some kinds of games， you know， these predictions are even computationally plausible in the sense that。

If we're in a congestion game， best response dynamics will get us quickly to an approximate pure strategy Nash equilibria。

 if we're in one of these generalized N player zero sum games， you know。

 multiplicative weights and more generally no regret dynamics get us to some kind of equilibriumria。

But。You know， in this lecture， I want to think about enlarging the circle even further， you know。

 just as we sort of generalized from。Dominant strategy equiria to pure strategy。

 equi to mixed strategy， equiria， I want to generalize。

 you know one layer up and and you know why like why would we want to generalize even further。Well。

Make strategy N equilibriumlibria exist。In every game， but。So far our sort of stories for why。

Nash equilibrium， our computationally plausible predictions have been sort of piecemeal like you know。

 we we picked a couple classes of games and gave like different stories for each class of games。

The hope is to by generalizing even a little bit further to get some class of equiria that we can think of as computationally plausible for every game。

Okay， those are going to be correlated equilibrium。Okay。

 so so okay I think this is probably telling that story we've seen simple dynamics that converge to N equilibriumria in ingestion games in separable zero sum games。

😊，And so you might at some point think to yourself， know okay。If we are sufficiently clever。

 then maybe we can find some class of dynamics that like doesn't care about the structure of the game。

 it just converges to N equilibriumlibria， mixed strategy National equilibriumlibria in any game。

But for you know， various complexity theoreticaloretic reasons。嗯。That appears to be unlikely。

 although。You know， just as you know， we as a community of computer scientists and mathematicians。

 you know， we're unable to even prove that。P does not equal NP P so you know。

Could be that there's efficient algorithms for all sorts of things。

There are reasons to think that it's in general hard to find Nash equilibriumria。

You can define a complexity class called PPD， which is sort of。

About finding general fixed points for general you know and dimensional functions and it turns out that the problem of finding Nash equilibrium is complete for this complexity class。

 so in some general sense， if you could if you had if you had a polynomial time algorithm of any sort for finding Nash equilibriumria in arbitrary even three player games。

Maybe even two player games， you could find fixed points for arbitrary。Functions and。

People have tried it doesn't seems as hard。 so there's reason to think that。

We're not going to find some even polynomial time algorithm， let alone。

 a sort of efficient decentralized dynamic that converges to NA equilibriumria without needing some additional structure in the game。

But maybe there's some more general。Kind of equilibrium maybe we can sort of enlarge the circle further just as we have。

You know， up until mixed strategy Ash equiria so far。That will take us， you know。

 when we went from pure strategy a equilibriumlibomic strategy， we got existence。

 maybe when we go another level up， we can get computational tractability。

And that's going to be one of the motivations for this lecture。Okay。嗯。😊，That's sort of the。

Motivation for the class we're going to go into some details now， but questions about the general。

Story and。How it fits into the。Story we're sort of weaving in this class。Okay。

So let's go back to these sort of two by two anecdotes from。Coassical game theory。

 how many of you guys know how to drive how many people have a driver's license Okay so like for anyone who knows how to drive you will be familiar with the traffic light game Okay。

 so so yeah I've got a two year old son who's learning about traffic lights and。😊，Dacare。

 and he's got this song。 I want an attempt to reproduce the。The tune。

 but the lyrics are something like。Red means stop。Green means go yellow means move very slow。

 And I'm not sure about yellow。 So let me remove yellow from this story。

 I don't think that's an accurate description of what yellow does。 So let's imagine。

stop like a world in which stoplight have just two lights like red and green。

 though it's clear what those mean at least。Okay。P。

Now we use stoplight at intersections where you know， like there's。

I say it's like a plus intersection so you know there's oncoming traffic potentially going in the other direction and when you get to this intersection。

You've sort of you've got a game with the other person perpendicularity at the intersection and let's say you've got two actions。

 you can stop or you can go。Okay。😊，And so we can sort of draw out a game matrix for what the payoff function might be。

We could both stop in which case。You know， nothing bad happens to us。

 but we're also not getting to where we're going so maybe we both get pay off zero。

Or you could stop and I could go in which case I get to where I'm going， I get payoff one。

 you get payoff zero， vice versa， I could stop and you could go I get pay off zero。

 you get payoff one， and of course we could both go but then we would die horrible fiery deaths and let's write that as payoff minus 100。

Okay， so， if you know how to drive you're sort of you've encountered this game before。U。So。Yeah。

 like， I want to think about the。Nash equilibriumria。

Of these games of this game and whether the Nash equilibriumria sort of。

Are expressive enough to describe the kind of behavior that we might want to see at an intersection like this。

So first of all， who can tell me what are the purest strategy N equilibrium of this game？好。

That's right so if there's if we're just looking at pure strategy equilibrium， no randomness。

 there's two of them right it's a symmetric aim I can go and you can stop or a vice versa。Okay。

 and it's an equilibrium because if I'm going and you're stopping yeah， there's no oncoming traffic。

 I don't want to switch to stop， that'll just slow me down and you don't want to switch to go that'll lead to a collision。

Okay， and you know， the situation can be reversed as well since everything's symmetric。

 so there's two pure strategy Nationallibria， I go， you stop， you stop I go。😊，Okay。Now， of course。

 these equilibrium aren't great because all of the utility here is accruing to like just one of the participants in this game。

 like symmetric game， but like。One person's getting to go to their destination。

 The other person's not。 The utility is you know，1，0。 So， So at least， you know。

 at these don't seem like。like maybe this equilibrium is like okay from a welfare perspective。

 but like it doesn't seem like a good way to coordinate society it's not like a fair equilibrium。

But things could get worse， those aren't the only two equilibrium。

There's also a mixed strategy actually equilibrium。Okay， and we can think about how。

We might work out what that is。So it's a symmetric game。

 so there's probably a symmetric equilibrium where both players。

Stop with probability P and go with probability 1 minus P。And so， you know。

 since it's just a two action game， you know， like that equilibrium will be defined by just a single parameter P。

 what is the probability that you stop？And we can sort of just， you know。

 like crank through what the equilibrium must be like you guys showed on the homework that。

first homework。That if we're really going to have a fully mixed equilibrium with support over both of these actions。

Then， well， it's got to be that。At this equilibrium both players are indifferent between their two actions。

 I can't randomize that equilibrium between two actions that have different payoffs for me and expect that to be a best response。

 otherwise I could just put more weight on the better action。Which means， you know， okay。

 I have to be indifferent between these two actions。

 stop and go and I know what my utility is for stopping， it's zero no matter what。

And so at equilibrium， my utility for going also has to be zero。So I know that my utility for going。

 well it's that if I go。And you stop which happens with probability P I get payoff one and if I go and you also go with which happens with probability1 minus p I get payoff minus 100 and so this just gives me like an equation for for P and I can figure out what is the。

In this equilibrium， what is the probability that I go and it's about， I stop basically where I go。

 basically a little less than 1% of the time。Okay， so like there's also a mixed strategy a equilibrium where。

Where both players independently stop with probability 100 over 1001。

And they will go with probability1 over 101。对。And。By basically any measure except maybe fairness because it's now symmetric。

Like this is even worse than the pure strategy in Ash equilibrium。

And the pure strategy actually equal to brim。One person was getting payoff one。

The other person was getting pay off zero。 so like at least someone was getting a positive payoff。

 the social welfare was one。But in this mixed strategy， national equilibrium， first of all。

Both players have expected payoff zero， right？Yeah， like now things are symmetric。

 at least both players get the same expected payoff， but it's not one， it's zero。And。

It's zero because there is a， you know， non trivial risk of like huge negative utility。

I like it's like what we're seeing here is basically just a failure to coordinate。ok。So like。

What's a good way to think about。What is happening at this mixed strategy， national equilibrium？

You know the two players are each independently randomizing。

With a probability about 1% they're going with probability about 99% they're stopping。

But there's two of them， and when they both independently randomized。

What that's doing is it is inducing。A distribution over the four states of the game， stop， stop。

 stop， go， go stop and go， go。And it's， you know， more or less this distribution。You know。

 roughly 1% of the time。I go and you stop， that's a good state roughly 1% of the time I stop and you go。

 that's a good state。About 98% of the time， most of the time neither of us go like because nobody makes any progress here。

And then some， you know， like small but like non trivial fraction of the time。

 we die in a head on collision。Okay， so like。When you look at the distribution over game states。

 this is a very inefficient。嗯。😊，You know， outcome right like sort of what we'd really like is almost all of the time just be be in sort of the good state where one person stops and one person goes。

Okay， like。Much better would be if we could sort of rig things up so that this was the distribution over gave states where。

Wherever wasting time， there's always somebody going。Maybe it's symmetric， it's fair。

 half the time I'm going， half the time you're going。And we never crash like ideally。

We'd like to be here。The pure strategy national equilibriumria sort of can get us。

100% of the time on either one of the diagonals， but don't randomize in this way。

And the mixed strategy N equilibrium is doing something terrible， it's， you know。

 spending like less than 2% of the time in the good states。Okay。So one question is。

Is there there maybe we just completed a bad mixed strategy N equilibrium like is there a different mixed strategy N equilibrium that can induce this distribution over the game states？

And if not， why not？Yeah。对。呃他0。Yeah， it's like even worse。 It's not like a failing of like。

The idea of stability in the national equilibrium it's like。Mix strategies， as we've defined them。

 aren't even expressive enough to represent this distribution of our gamet。Right。

The way we've talked about mixed strategies。I come up with some distribution over my actions。

 like 1% of the time I go， 99% of the time I stop。You come up with some distribution and then we sample independently like there's no mechanism for us to coordinate our sampling。

 I can't say when I stop you go and when you go I stop。Okay， so like。

The only distributions over game states we can induce are like product distributions。

 distributions that can be like decomposed into an independent distribution over the rows and an independent distribution over the columns。

Right， so if。I am going half the time and stopping half the time。

And you are going half the time and stopping half the time， which is what's happening here。Then。

We would get。You know we would actually be in sort of all four game states with probability 25% each that would be a。

Terrible outcome。嗯。And there's just like you know， there's no way like forget incentives there's just no way to。

Induce a distribution of game states that looks like this without some explicit mechanism for coordination like I would have to talk to you in order to。

In order to arrange for something like this to happen。

It can't just can't happen through independent randomization there's no way to decompose this distribution over game states into an independent distribution over actions for the column and row player。

There are questions about that？嗯。Okay， so like。It's clear。That。We'd like to。

Induce behavior like this。And the reason that we can't is not that this is somehow irrational that it's not that acting like this would be against someone's interest。

 it's not that this is violating an equilibrium condition。It is rational。

 right like if you are out there driving。嗯。And。You know when we're driving we don't have to sample our actions independently。

 we have coordination mechanisms， which are traffic lights。It's not that the reason， I mean。

 one of the reasons maybe I stop at red lights is because I'm a law abiding citizen and I， you know。

 just like following rules， but that's not the only reason like if if there's actually it's actually like a busy time of day。

 it is not a good idea for me to run the red light because I know that when I have a red light。

 the oncoming traffic has a green light and there's a good chance that if I run the red light。

 I'm going to get hit。Right， similarly。When I see a green light。

I go not just because that's the rule not just because I remember this song from preschool I go because it's a good idea like when I have a green light oncoming traffic has a red light if they're playing according to。

This equilibrium， then I'm pretty sure they're going to stop and so going actually is in my best interest。

Right， so there's a sense in which like。You can imagine talking about a distribution over game states like this as an equilibrium it's sort of rational for people to play like this。

 given that your opponent is sort of playing like this， you wouldn't want to deviate。

The problem is the notion like the only way we've talked about so far。

Modeling play of a game is through independent randomization and without coordination there's just。

No way to induce this distribution of gamespace。嗯。どこ？Okay， and so。At a high level。

One of the main ideas behind correlated equilibrium。Is to think about。The kinds of behaviors you can。

Induce rational players to play。By means of a correlating device。Okay。

 if I have the ability to put up。A traffic light that。

You know you can think of it as giving instructions for what one player should do in a way that is correlated with the instructions given to other players。

What can I， but I still can't like force people to do what I want so I can't just yeah can't just give them instructions to play whatever my goal is。

 I still need to rely on the fact that。They will think about whether it is a good idea to follow my instructions。

The question is what can I then， what kind of behavior can I then induce？Okay， and so like。

A trafficraffic light wouldn't work if it said。If it gave a green light。

To the oncoming traffic at the same time， it gave a green light to me。

 like then I would ignore the traffic light。嗯。The reason it works， the reason it works。

Not just on a legal level， but on an incentives level is because it's correlating the signals the correlating the instructions it's giving to me an oncoming traffic in a way that。

Implylies it's a good idea for me and for the oncoming traffic to follow the suggested action。

 go or stop。Okay， questions about。Traffic lights。Okay， so let's try to。

Generalize this intuition that we get from traffic lights。嗯。So let's see， maybe before we。

Go into the parsing the definition， let's try to。Get some intuition so。

Think about a correlating device like a traffic light except now instead of having two or three colors。

 you know， it could have 27 colors it could have。😊，86 colors and more generally。

Like you don't like without loss of generality， the correlating device can be thought of as。

Proposing an action for you to take。Okay， so the traffic light would work just as well if instead of green and red。

 it like said， go and stop。In fact， Blake。That's sort of without loss of generality because。

If I have some。Fancy correlating device that shows colors like a traffic light green and red， well。

 if people are going to think about what is their best response given the color that is shown to them。

they'll come to some conclusion。 They'll say， well， given what everyone else is like doing。

 given that I'm given that I see green， I should go。Okay， so select the first。You know。

 little twist I want to put on traffic lights is I want to imagine that。

The traffic light is not showing you a color， but it's just directly proposing an action that you should play。

 like go or stop。And。We could think about this in a general game， not just a game with two actions。

So the corlating device is just allowed to basically whisper in your ear。An action you should play。

 a suggested action。Now， the reason。The traffic light works。Is because。

The suggestion it's whispering in my ear。Is very directly related to the suggestion it's whispering into the ear of the driver。

Oncom in the on traffic。It's like I know that if the traffic light whispered go in my ear。

It whispered， stop。To the driver。Coming at me， the oncoming traffic and vice versa。

That's why it works。So more generally。We can think of。A correlating device as。Corresponding。

To a distribution over action profiles， one for each player。Okay， so。You know。

 the traffic light is a distribution over two action profiles， go stop and stop go。Right， Mike。

Whenever it suggests go to me， it suggests stop my opponent and vice versa。But more generally。

A correlating device could be thought of as。Just a distribution of our action profiles。

 so there's a big bag full of action profiles， one for each action。

AndWhat happens when we come up to the stoplight is someone pulls an action profile out of the bag and whispers into each of our ears。

 the suggested action that corresponds to our coordinates in this action profile。ok。Now。

We know what distribution over action like we the drivers， the players in this game。

We know what the distribution of action profiles is we know the definition of the correlated equilibrium right like that's important it's important that I know。

That when。I'm told to go， you're told to stop and vice versa。And somewhere more generally。

Given that I know this distribution of action profiles。

When I hear whispered into my ear by the tro lights。The action that I have been suggested to take。

Conditional on that being what was whispered into my ear。

I know the distribution on actions that all of my opponents have been。Suggested to take。

Like in the traffic light game it's pretty simple， I know that if I've been told to go。

 you've been told to stop deterministically。But in general， it might be more complicated。

 like I might not know deterministically what you've been told to do。

 given what I've been told to do。But I know I have distributional information about it。

 I would know what is the distribution on suggestions given to all of my opponents。

 given what I've been told to do。And so here's what a correlated equilibrium。Says in math but。

In words。It's this。The suggestion that was whispered into your ear。Should be a best response。

Even conditional on that suggestion， like conditional on the suggestion。

 you know a distribution on what everyone else is going to do。

And among all of the actions that you could play， given the distribution you know on what everyone else is going to do。

It should be a best response for you to play the action that was suggested to you。

 so the the action that was suggested to you should be a best response to the induced distribution on what everyone else is going to do simultaneously for every player。

Okay， so just writing that in math D。Is a distribution of action profiles and just to sort of。

Unpack this compared to like when we were talking about mixed strategy Nationalibria。

Now mixed strategy national equilibrium。We had not directly a distribution of reaction profiles。

 but an independent distributions over actions， one for each player。

 and the distribution of reaction profiles was just sort of induced by having every player independently sample from their own action distribution。

The fact that a correlated equilibrium is directly a distribution of action profiles allows as per the name for the action profiles to be correlated with one another。

 learning what I'm supposed to do in the correlated equilibrium actually gives me information about what you're going to do。

And so what it says is that it should be you know。I might consider。How I'm going to play this game。

 I could just say。It's a great idea to follow。Traffic lights。

 I'm going to play according to the correlated equilibrium， which just means。You know， whenever I'm。

 you know， an action is going to be drawn from this。肯。Correlated equilibrium distribution。

And I'm just going to play it， I'm going to play whatever is suggested to me。Okay。

 and if everyone else does the same， my expected utility is。Well。

 it's just my expected utility over a randomly drawn action profile from this correlated。

Action profile distribution。嗯。😊，On the other hand。I could consider deviating from it in some way。

 what are the kinds of deviations I could consider？Well。I see the output of the correlating device。

So in principle， I could consider deviations that are a function of that， right like I could。嗯。

if green means go and red means stop and yellow means go very slow。

I could go really fast when I see yellow， but stop when I see。Green and go when I see red。

 like I could see， I could do things that are a function of the correlating device。

And this condition is saying， you can't benefit by doing anything like that。And even。

Even conditional on。The suggestion that's been whispered into your ear。

 theres no other action AI stars will gain you higher utility。Right， so not just， you know。

In the stoplight game， is it better to follow the stoplight than to just go all the time it's also not a good idea to。

Go when there's a red light and stop when there's a green light， like in general。

You can't improve over playing your part of the correlated equilibrium。

Even after you see what your part of the correlated equilibrium is。

 assuming everyone else is also doing the same。Okay， does that make sense， so it's a。

 it's very much an equilibrium definition in the same spirit we've been thinking about them。

 it's sort of saying。Nobody can。Unilaterally improve by deviating from this sort of plan of action。

But now there's this means。By which。Players are coordinating with one another like the the distribution of action profiles might be go stop half the time and stop go half the time right intellectual to physically implement this you'd need a correlating device like a like a traffic light but。

We have those。Okay， so there are questions about the， yeah。监么。た。Not necessarily。

 but like it could be that。You know， like the traffic light is you know a little broken or something and you know what I know is that if I see green。

99% of the time you see red right so I like it doesn't have to be。

The way a real traffic light is deterministic， doesn't have to be that。

I know exactly what you're going to do given what I'm told to do。嗯。Yes， it's a like。

A valid distribution could be， you know。99% of the time it's either red green or green red。

 but you know half a percentage of the time it's you know green。

 green and half percentage of the time it's red red or something in which case if I saw green。

 I would now be pretty sure but not certain that you were going to see red。Does makes sense？

Other questions？Yeah， given AI。No， so you only。四。嗯。Your suggested action， not the others。Okay。

 so like， you know， at a traffic light。Oftentimes I can see that it's red for me。You know。

 depending on the setup of the light I might not be able to explicitly see that it's green for the others i'm pretty confident that it is because I know the distribution on。

😊，The correlating device， but I don't directly get to observe it， and so it's the same setup here。对。

How do you that。关别可以。嗯。去关。Which term？What要证。Oh。We'll see a weaker version of this in a few minutes where we do leave that off。

But。That's a weaker definition， like it might be， we'll talk about this in a few minutes。

 but but like。Yeah， you could imagine something like this that just says， look， you can。

 I I can't cover things up very well on a projector， but。It says， look。

You can either play according to the correlated equilibrium or you， if not。

 we will revoke access to the correlating device entirely。

 you will have no information and so basically your only option will be to play fixed actions or distributions over actions。

You'll no longer be correlated with what other people can do and we could say， okay。

 it should be like a better idea for you to like opt into the correlation than to do anything else。

This is saying asking for something even stronger than that。

 not only is it a better idea for you to opt into the correlation than sort of going off on your own。

But that even there's no sort of way you could。Beeneffiially deviate even using the correlation。

Like you could consider deviations that use the signal you've seen and even those are not beneficial。

But we will talk about the very anti。Yeah。6。So let's see。This is saying for every。

 I guess really it should。Yeah， I agree。AndMaybe a better way to write this would be for every possible AI and for every possible deviation AI star。

It's not a good idea to deviate from AI to AI star， so even if I restrict the tension justticssative。

The event where you're suggested to play AI。嗯。Even on that sort of restricted distribution。

 AI is a best response simultaneously for all actions AI。Distribution。

D is the distribution over recommendations so like to it。So like in the stoplight game。

 like the stoplight， the distribution D， the stoplight implements is the distribution of the two action profiles。

 half the time it's stop go， half the time it's go stop。

So the object that is or is not a correlated equilibrium is a distribution over action profiles。Yeah。

Go right outside were。对。Yes， so just like in anash equilibrium of room the。

Idea is it's a good idea for you to do your follow your part of it。

 assuming everyone else is following their part of it same here like it might be that。Yeah if。

Other people are not following their yeah， if everyone else is just zooming through the intersection ignoring the traffic light。

 it might not be a good idea for you to go when it's green。

 but this is saying if everyone else is following the recommendation you should to sorts sort of a stable state in the same way that a na equilibrium is yeah。

😊，不对。我知。 like there's no。That's what makes it like a stable stage， like just ast a N equilibrium。

 everyone's playing a best response given what everyone else is doing。Here。

 given that everyone else is following their recommendation。

 it is a best response for you to follow your recommendation as well。

For every recommendation that you would get under。This correlating device。Okay。

It might be that for some recommendations， you shouldn't follow it so maybe。You know。

Maybe there's a third light that's blue then。Blue means go also。But when it's blue for you。

 it's also blue for the other guy and。When you're told to you know， go in the blue intonation。

 it's like actually not a good idea for you to go。In which case there would be a， you know。

 in which case。You might still want to follow the recommendation sometimes when it says green or red。

 but when it says blue， you'd want to deviate to stop。Make sense。Good questions， other questions。

Okay， so in words it's just a distribution of action profiles so that。

The recommendation that you get as part of this action profile。

Is actually a best response for you to play。Even conditional on the action profile you've been recommended to play。

 the action you've been recommended to play， which tells you。

What distribution you expect everyone else to play according to？Okay。嗯。So one thing I want to note。

Is that？This is a general is it， you just as。Pure strategy N equilibrium。

 generalize dominant strategy Nash equilibrium， mixed strategy N equilibrium。Generalized。

Peer strategy Nationallibria。Correlated equilibrium generalized Nash equilibrium。Okay。

 like Nash equiria are correlated equiria， they're just the special case where there's no correlation。

Like if everyone is randomizing independently of one another。

That does induce some distribution over action profiles。Right like if I play rock paper scissors。

 you know， independently with probability one third and you do the same。

 there's now a distribution over action profiles， you know。We play rock rock with some probability。

 we play rock scissors with some probability， et cetera， et cetera。

But it is a distribution in which the two actions are independent。

 and so learning my part of the recommendation tells me nothing about your part of the recommendation。

Because there's no correlation right like we're applying rock paper scissors。

And I close my eyes and pick a random number and decide for myself that I'm playing scissors that does not give me any information about what you're going to play。

And so in particular。嗯。Something that right like in particular， if I was playing。

A best response to your distribution， which is what it means to be at a Nash equilibrium。

And our distributions， the distributions on our actions are uncorrelated。I am in particular。

 also playing a best response to your distribution。

 even conditional on the realization of my own action。

 just because if our distributions are independent。

 the realization of my own action doesn't change the distribution on your action。Like if I'm playing。

 if uniformly randomizing between rock paper and scissors is a best response to what you're doing。

 it is still a best response to what you're doing even after I like decide for myself。

 it' just in my head that I'm going to play scissors this round because that doesn't actually contain any information。

 but what you're going to do。Okay， so N equilibrium are also correlated equilibrium。

 they just are correlated equiria。Such that the distribution happens to be independent。But。Just as。

Mix strategy ash equilibria were a useful generalization of pure strategy ash equiria。

 they were a larger set， there were a mixed strategy a equilibria that were not pure strategy equiria。

Correlated equilibriumlibria are a strictly larger richer set than mixed strategy national equilibriumlibria we saw an example of that already in the in the traffic light game right we saw a。

Correrelated equilibrium。That was not a Nsh equilibrium， it was something different。Now in this case。

 it was just a distribution over a pure strategy in a equilibre， right？

Both of these corners were pure strategy in National Bellibria。On the homework that just went out。

 though， you're going to sort of work out an example where it can go beyond that right you can have。

Correlated equiria that are like truly different than。

Any of the Nash equilibrium in particular that can have higher social welfare than any of the Nash equilibrium。

Okay， so， you know， just to sort of maybe。Draw。A picture that's good to remember。U。You know。

 we've got。You know， dominant strategy， equiria here。We've got。

You're a strategy Nsh equiria that's a strictly larger sense。

We've got mixed strategy in National equilibriumria。It's a strictly larger set。

And we've defined this here correlated equilibrium。对。Okay。

here correlated equilibrium that again generalizes mixed strategy a equilibrium。

 but contains other stuff， you know contains mixed strategy a equilibrium but also other stuff。

 it's a larger set。Okay。嗯。Why don't we continue and we can define even larger sets。

And so there was a question about， you know， what if we don't condition on。

The suggestion that's been whispered into our ear， what if we just say something like this？You know。

Like giving someone two choices， either you can opt into the correlation。

 you can experience utility equal to the expected utility of the action profile sampled from this。

Coorrelating device。Or。You can opt out of the correlation and do something else。

 but I will no longer show the correlating device to you if you do that。

 so you no longer have the option to。Consider deviations that are a function of the signal that you get your deviations have to be just fixed actions or mixed strategies that don't depend on the correlating device anymore。

 so the alternative is to obtain utility sort of from the action profile that arises when you play some fixed action and everyone else continues to use the correlating device。

And the rationality condition here is that for everybody it should be better to opt into the correlating device than to opt out like your utility。

For opting in and getting payoff。According to this sort of correlated action profile should be only larger than the utility that you can get by setting out and doing your own thing。

Okay， that's called a course correlated equilibrium。屁懂。The only difference between this。

A course correlated equilibrium and a correlated equilibrium。

Is whether the set of deviations you are allowed to consider。

Or allowed to depend on the correlating devices。In a correlated equilibrium， you can consider。

Dviations after you've seen the suggestion。That you would have gotten in the correlating device。

And a course correlated equilibrium。You have to consider deviations before you've seen the suggestion。

Okay， so you can imagine by way of。You know。Only slightly stranded example。That。Now， when we have。

Cars that are， you know， driven manually or。Maybe beginning to have self driving cars。

 but the technology is still new enough that。The cars have to do what we say。

That if you imagine a service like Wa or Google Maps， that's going to。

Give us a suggestion like it's going to suggest a route for us to drive along。

 but it can't force us to do it。Like after we see the suggestion。

 we can decide if we want to do it or not。That such a service could try to implement。

It correlated equilibrium。It could sort of try to correlate the suggestions it gives to different drivers。

So that。To get some good outcome， like to minimize congestion time or something。

 but if it wanted people to follow the suggestions like the suggestions would have to be good ideas even after I saw the suggestion。

 like if you thought that you could get benefits in social welfare by occasionally telling me to drive some really out of the way。

 route in order to free up you know， road capacity for other people like on those days。

 I would just not do it。Okay， because I could deviate after seeing the suggestion。On the other hand。

 you can imagine some you know， world in the future where。

Maybe I have the option to buy a fancy self driving car that's plugged into the optimization network。

Or I have the option to you know use my old legacy car that's not。But the。The self driving car。

You know， it's not going to have a steering wheel like it' it's really going to drive itself。

 I'll tell it where to go， but it'll decide on the route。Okay。In which case。

 like my choice point here is at the moment when I'm deciding what card to buy？I can。

Optt out of the correlation， and I can opt out of the correlating device by buying like an antique car that has a steering wheel。

U。Or I can opt into the correlation by buying one of these modern networked cars， but if I do that。

 I'm not like I'm going to lose fine grain control on about which route I take on which particular day。

Then maybe if you wanted to incentivize people to。Ot into the network cars。

 it would be enough to implement a course correlated equilibrium course correlated equilibrium says on average。

You're going to be better off。Sort of opting into the correlation。

 you'll be better off on average than， you know， doing anything that's。

Doesn't get access to these correlating signals， anything you could do with your sort of antique car。

 but like there might be like particular days when if only you knew the route it was going to take you to tell you to take that day。

 you would have preferred to deviate you just didn't have the option。Okay。

 so maybe that's some high level。Intuition about the difference between these two solution concepts。

嗯。Yeah， so like whether a course correlated equilibrium is like a sensible solution concept depends on whether in the interaction you're thinking about。

The players have。The option of deviating after they see their suggestion or whether the only point at which they could deviate is before they see their suggestion。

A course correlated equilibrium says it's a good idea to opt in before you see your suggestion in expectation over what the suggestion is going to be。

 a correlated equilibrium says it remains a good idea even after you see the suggestion。P。Okay so。

Like another difference between correlated equilibrium and coursear correlated equilibrium。Of course。

 correlated equilibriumria can occasionally suggest things that are just like on their face a bad idea so long as it doesn't do it too frequently and the benefits that you get from correlation elsewhere are enough to sort of counter weigh these occasional。

 like obviously bad suggestions。Whereas course whereasas correlated equilibriumria can't do that。

 correlated equiria can only make suggestions that are good suggestions given what you know。Okay。

 so just to sort of give like an example。Suppose I've got a game that looks like this。Maybe。You know。

 it's sort of a simple coordination game in the upper quadrant here like， you know。

We'd either like to both play A or both play B， but like if we mis coordinateordinate。

 that's no good。And then maybe like there's this like obviously bad move C that。You know。

 if we both coordinate on C， we get like even even worse payoff than anywhere else in the game。Okay。

So we can think about the following。Distribution on action profiles。

That a third of the time suggests that we both play A。

A third of the time suggests we both play B and a third of the time suggests we both play C。

So this is not a correlated equilibrium because。If I'm you know if I if I get the A suggestion great I'm going to play a。

 it's a great idea if I get the B suggestion great I'm gonna to play B， it's a great idea。

 but if I get the C suggestion， well I know that if you play according to the correlated de。

 you're going to play C as well， I would be better off playing A or B so it's not a correlated equilibrium because one of the signals C would is not a best response conditional on that signal。

😊，On the other hand， it is a coarse correlated equilibrium because。

Suppose I opted into the randomness。I'm getting gains from the coordination here like two thirds of the time the coordination is actually helping me。

 it's only a third of the time that the coordinations hurting me。

So if I opt in like two thirds of the time I benefit from the coordination。

 a third of the time I get payoff one another third of the time I get pay off one。

 the last third of the time， you know。I kind of got screwed over， I get pay off minus 1。1。

 but like still。On average， my payoff's pretty good， it's 0。3。

If I compare that to how well I could do。By opting out of the coordination。Well， how well could I do？

Well。You know， if I no longer have access to the coordination signal， it's not like I can say， okay。

 I'm going to like follow the suggestion if it's A or B。

 but I won't tip it C because I no longer see the suggestion。So really。

 the only thing I can do is play like a fixed action or a fixed distribution over actions。

So like what happens if I play a fixed action， I could play A while you randomize like this。

But in that case， like， you know， a third of the time I'd get payoff one。

A third of the time I'd get pay off minus one and a third of the time I'd get pay off zero and so my payoff for playing a would just be zero。

Similarly， my path for playing B would just be zero and for playing C would be negative。So。

Opting like despite the fact that this coordination mechanism a third of the time tells me to play something dumb。

 like I'm still on average gaining more from the coordination than I'm losing。

 I'm better off on average following this coordinated strategy than doing anything that's independent of the coordination。

So it is a coursear correlated equilibrium。Does that make sense this is maybe like the salient difference between。

A correlated equilibrium， a course correlated equilibrium。Like a course correlated equiria can。

Be a good idea to play just by virtue of like averages like it， you know。

 if usually you're gaining from the correlation， it can occasionally suggest something that you wouldn't want to do if only you had the option to deviate given the suggestion。

 but like it's not worth opting out of the correlation entirely because on balance you're gaining more than you're losing through the coordination。

A correlated equiria can only suggest things that are best response is given。

The information available to you。Okay， questions about the difference between a correlated equilibriumlib and a course correlated equi。

Okay， so just sort of maybe。Adding a circle to our。Degeneerate Venn diagram here。

Of coursese correlated equiria， generalized correlated equilibriumria。

Correlated equiria are coarse correlated equi， but there are some coarse correlated equi that are not correlated equi。

 so again， it's a larger class。嗯。And just sort of， you know， like。Looking at this chart。

 what did we get？At this point， when we got to mixed strategy National equilibriumlib。

 we got existence。The goal is to show that at this next jump， we get computational tractability。

So sort of by the end of next class， I want to be able to。

Describe like an efficient learning dynamic that will converge to correlated equilibrium in any game。

Okay。Okay。And the way we're going to eventually get there。

 like the the learning dynamics it's going to be a little bit more complicated than polynomial weights。

 but it's going to be related So we're going。Be talking again about sort of regret the way we talked about regret class class。

U。It's going to be useful for us to give like an alternative definition of correlated equilibrium。

 of course， correlated equilibrium that。Or defining the same object。

 but in terms of regret because our path to。Like。Efficient。

Learning dynamics and games are going to be through designing。

Learning algorithms that can guarantee the various kinds of。

You that players don't experience various kinds of regret。So。Let me define。Maybe a。

Larger class of kinds of regret than we've talked about before。

So let's say that a strategy modification rule， FiI。It's just a mapping from actions to actions。

Saying like。You know， look。Every time you play action5。

You should feel bad about it like you should have played action four every time you played action five。

And every time you played action  three， you actually should have played action seven。Okay。

 so it's like think of a strategy modification rule as like a backseat driver who's telling you what you should have done instead of what you actually did。

Like for every action you could have played， the strategy modification rule is telling you what you should have done that maybe would have been better than that。

Okay， but more generally， it's just a mapping from actions to actions。But your regrets。

Given an action profile in a strategy modification rule。Is the difference between。

How well you would have done if you had let the backseat driver go back and change history。

 change the action you actually played into the action the backseat driver said you should have played the action that you get by applying the strategy modification rule to the action you actually played。

The difference between the utility you would have gotten under this counterfactual world in which the backseat driver applied the strategy modification rule compared to the utility that you actually got。

 given what you actually did。O。😊，So a strategy modification rule tells you。

For everything you could have done what you should have done instead。And。

Your regret to a strategy modification rule， given a particular action profile is just。

How much better you could have done had you applied the strategy modification rule？Okay， and。

You know， some backseat drivers give only like simple suggestions。

Like their suggestions aren't conditional， they're just like。Yeah。

You just should have played action seven， action seven is the best action， just play action seven。

So if the strategy modification rule has that form， it says just play action7。In particular， if it。

Maps to action 7， no matter what input you give it。Or for any value of seven。

 it's a constant function。And we'll call it a constant strategy hum rule。Okay， and so。

Let's give an alternative。An equivalent definition of a course correlated equilibrium。

And then an equivalent， but alternative， but equivalent definition of a correlated equivalent。

So a distribution。Overaction profiles。Is a coarse correlated equilibrium？

If simultaneously for every player， I。And for every constant strategy modification rule。

Their expected regret to that constant strategy modification rule is。Non positive。

 they don't have any expected regret。Now a constant strategy modification rule is just sort of like a。

Ofuscated way of saying。You don't have any regret to the best fix action。Right。

 it's just saying like， look。U。In expectation， like you're better off following the correlating device than always playing action one。

And also you're better off following the correlating device than always clang action too。

RightSo it's the same definition from before like you're better off following the correlating device than doing any fixed thing。

That is independent of the correlating device， the fact that it's a fixed thing is encoded in the fact that here we're just thinking about constant strategy modification rules。

Okay， so if you have no regrets to the best fix action。This is exactly the same kind of regret that。

The polynomial weights algorithm guarantees is diminishing guarantees goes to zero right if you play a game with the polynomial weights algorithm。

You're promised that your average expected your sort of average payoff over time is at least as high as。

Had you counterfactually been able to go back and modify your play every day to play every day consistently the same fixed action？

I was just saying you have no regret to。咁。Constant strategy modification ruless。

So an immediate consequence of this。Is that？In any game。

If we've played the game for T rounds and have generated a sequence of T action profiles。

 A1 through AT。And it turns out that。This sequence has。Low regret。

 let's say deelta of T regret in the sense that we talked about last class。是。Then if I look at the。

Distribution that results just from sort of the empirical distribution over these action profiles。

 The distribution that results just from。Picking uniformly at random one of these T action profiles。

This distribution is a delta of T approximate course correlated equilibrium， meaning。

The expected regret is okay， it's not less than zero， but it's less than delta of t。ok。

And so in particular。That means that。We already know a learning dynamic that converges to coarse correlated equiria in every game。

The polynomoid algorithm does it。Because we know that if every player。

Play is according to the Ponomy awaits algorithm。Then no matter what their opponents do。

Their regret to the best fixed action and hindsight。Equivalently。

 their regret to the best constant strategy modification rule。

Goes to zero at a rate of roots log K over T。And if everyone does it。

 everyone's regret to goes to zero at that rate and we get a sequence of action profiles that has regret going to zero at this rate。

 regret to the best constant strategy modification rule， which。We now realize defines。Of coursese。

 correlated equilibrium。Okay， so we have a very fast dynamic converging to course correlated equilibrium and arbitrary games in particular。

It has no dependence at all on the number of players。

And it only has a logarithmic dependence on the number of actions。

Right so like this is saying in an N action game。Sorry， a K action game with end players。

After a number of rounds that is。Independent of the number of players n can be as large as you want and only logarithmic in the number of actions and going to zero at a rate of one over the screw of the number of rounds you've played。

You're converging to these approximate course correlated equilibriums。

 This is incredibly fast convergence depending only logarithmically on the actions and unbelievably like entirely independently of the number of playerslis。

😊，And so the question I want to ask， and I want to。

Set up the question this class and then answer it next class。

Is can we similarly think try to think of？A learning dynamic。

That we can argue converges to correlated equilibrium， not just coar correlated equilibrium。And so。

 you know， like。Of course， correlated equilibriumria。You know， like it sort of。

We gave an equivalent definition of it in terms of regret to these like constant strategy modification rules。

And then we just kind of like remembered like， oh yeah。

 like we've been studying this polynomial weight algorithm in class。

 it already guarantees that that form of regret goes to zero。The strategy here will be to。

Give a characterization of correlated equilibrium in terms of a richer regret notion。

One that's stronger than is guaranteed by the polynomial waste algorithm。U。

But maybe next class we'll be able to give an algorithm that promises diminishing regret of that stronger form。

Okay。🤧So here's the sort of regret definition。B。The regret definition of correlated equilibrium。

And it just removed the caveat constant from constant strategy modification rule。Okay， so a。

Distribution over action profiles。Is a correlated equilibrium？If for all players， I and。

Now for all strategy modification rules， all possible backseat drivers who are telling you what you should have done now as a function of what you did。

 they might have different suggestions for different things you've done。

If were all strategy modification rules。Your expected regret to that strategy modification rule is non positive。

Okay， the claim is this is the same definition， and this is a correlated equilibrium。Okay， so。U。

So a strategy modification rule， right， like what is it doing but saying， oh， well， you know like。

Every time you played action  seven， you should have played action4， every time you played action9。

 you should have played action 12。Um。It's what it's saying that if there are no beneficial deviations of this sort。

Right like if actually the best if you've totally stumped the backseat driver and that's okay， like。

 yeah， every time you played action 12， I guess I would have played action 12 two every time you played action  three。

 yeah， okay， fine I would have played action 32。Well。

 like the only way that can be true for like every backseat driver。Is if。In fact。

The action you played， which in a correlated equilibrium was equal to the suggested action you were given。

If in fact， that really was a best response given the suggestion。Right like if。

We're playing a correlated if D is a correlated equilibrium， right what that means is that。

Even conditional on seeing your suggestion， even conditional on the action you're supposed to play。

 that action is a best response。And so in particular， like there's no strategy， you know。

 if the strategy modification rule says every time you。Played action five。

 you should have played action three like that's not helping that's making things worse because the condition the correlated equilibrium condition was that conditional on being told to play action five action5 really was a best response。

 playing action three can't gain you anything。And if that's simultaneously true for every action。

 as it must be， if you have no regret to any strategy modification rule。

Then you're out a correlated equilibriumver。Okay， so this is the same definition of correlated equilibriumria that we saw before。

Just now in terms of strategy modification rules， there should be no mapping from the suggestion that you are given to the action that you should play。

That does better than the identity matter like you should just play the suggestion。

 that's what it means that the suggestion is a best response。

To the distribution induced by the suggestion。Okay。That that makes sense。So okay。

 so a course correlated equilibriumria corresponds to no expected regret to constant functions to sort of。

Functions that can sort of go off on their own， but， but can't interact with the。

Randomness of the correlating device。Correrelated equilibria corresponds to no expected regret to arbitrary mappings between suggestions of the correlating device and。

Actions that you take you should just follow the actions。嗯。And then in asking the question。

Are there learning algorithms that efficiently converge to correlated equilibria just as the polynomial weights algorithm efficiently converges to coursearse correlated equilibria？

We can again sort of abstract away the game theory part of it and try to approach this as a pure machine learning problem。

And sort of say， okay， well。The polynomial weights algorithm is a way to play in a sequential interaction that guarantees us no regret to the best。

Action in hindsight。Can we derive a learning algorithm that goes beyond that and guarantees no regret。

 not just to the best fixed action， but to sort of。

Arbitrary counterfactual worlds that would have arisen by applying arbitrary strategy modification rules。

Okay， so that's that's that sort of。The approach we're going to take next class just to like set it up here。

We're going to go back to the expert learning setting。

And we're going to try to derive algorithms that have stronger guarantees than the polynomial weights algorithm。

 but in the same setting。So we want to learn an algorithm in the same expert learning setting。

But can guarantee the following。Okay， so just to recall the setting。We've got these K experts。

 the K like actions in the game。Every day we need to pick one of them， every day we pick an expert。

And then after we pick the expert， all of the experts experience some loss。

Say a number between zero and1。We， the algorithm， experienced the loss of the expert we picked。

And our goal is the goal for the polynomial weights algorithm。

Was to come up with a way of picking experts so that our accumulated loss as an algorithm was no worse up to some diminishing regret term than the accumulated loss of the best fixed expert。

Here we have the stronger goal。We'd like to come up with an algorithm that for arbitrary sequences of losses can pick experts。

Such that。The accumulated loss of the algorithm， the sum over all of the rounds of the loss of the expert we chose at that round of the algorithm。

Is no more than sort of。The loss we would have accumulated in the counterfactual world where at everyday T。

 rather than playing action  A， we played action F8 for some strategy modification rule F。

 where F can map arbitrary actions to arbitrary action。Okay， so just note that。

Asking that this hold for arbitrary strategy modification rules is strictly stronger than the guarantee that the polynomial waste algorithm promises because doing no better than the best fixed expert just corresponds to having no regret to constant strategy modification rules。

 strategy modification rules that sort of always suggest you play expert too。Okay。

 so the polynomial weight algorithm promises this for strategy modification rules that are constants。

 says you do as well as always playing expert one or always playing expert two or always playing expert three。

That's why we converge to a coursearse correlated equilibrium if we play according to polynomial weights。

Our goal for our next class is to。Give algorithms that promise simultaneously for all possible strategy modification rules that we don't have any counterfactual regret to。

Playing those strategy modification role like that we are immune to like backseat drivers who can now suggest。

Swapping actions playing things as a function of what we've done。

Causing us to regret our choices we do at least as well as any plan that the backseat driver can come up with by。

Using a strategy modification rule。Okay， if we can do that。

 then we will have a learning algorithm that if players use it to play a game converges to a correlated equilibrium。

That's going to be the plan for next class。O。😊，So I'll see you guys on Thursday。



![](img/f7b2e7095c5df2198331cc44c940ef51_3.png)