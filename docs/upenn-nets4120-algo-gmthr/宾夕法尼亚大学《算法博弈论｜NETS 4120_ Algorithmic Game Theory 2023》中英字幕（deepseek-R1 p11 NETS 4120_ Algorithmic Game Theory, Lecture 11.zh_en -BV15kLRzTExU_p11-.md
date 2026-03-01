# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p11 NETS 4120_ Algorithmic Game Theory, Lecture 11.zh_en -BV15kLRzTExU_p11-

![](img/dd3ddc5d9bc9b958890c15bf3ef3104b_0.png)

All right。Almost the end of February， hope everyone runs。

 I guess fully into the swing of the semester。U。I want to oh， yes。飞拜饭。mAibly， but like。

Don't arrange things so that you're really counting on it， so I'll try to， but。Not a firm promise。

Good question now。嗯。Good other sort of bookkeeping things before we dive in to the material。ok。嗯。

So we've been spending a lot of time thinking about。How and if。

People playing in a game might reach equilibrium and you know towards that end we defined a whole bunch of different kinds of equilibrium right sweet we're just coming off of a lecture where we。

Basically explicitly defined this larger class of equiria， correlated equiria。

 some of it we would have a story that people converge to equiria in general games。Okay， so。

 you know， that's all well and good， you know， maybe。

We've made some progress towards establishing that the following kind of prediction you know。

 has some you know， reasonable grounding， which is that you know。In many classes of games。

 at least in the long run， people will end up playing at or near some equilibrium of some sort。嗯。嗯。

But you know， like。That's not like a super crisp prediction in that。Even if it's true。

There might be many different equilibrium states right like even in really simple games and even when we like restrict attention to things like pure strategy and actually equilibrium right we saw really early on that。

Games can bring naturally have more than one pure strategy equilibrium。And of course。

 as we've expanded the scope of what we consider in equilibrium as we've move from pure strategy Nash equilibrium to mixed strategy N equilibrium to correlated equilibrium。

 of course correlated equilibrium， you know we're only making this multiplicity problem worse right because at every step of the way along this sort of hierarchy of generalization。

 we're keeping all of the old equilibrium and we're adding new ones。Right， so like。

In doing this and expanding， you know up to correlated equilibrium， we've maybe made。

The prediction that we will end up at some correlated equilibrium， you know。

 at least oftentimes in the long run， plausible， but we've also weakened the prediction in that like。

You know， like we might be predicting that the thing that is going to happen is just one thing in a collection of things that might be really big。

 might be a lot of equilibrium。Right， so sort of。The sharpness of our predictions has kind of degraded。

And so。What I want to think about in this class is sort of a way in which we might nevertheless be able to make。

Sharp predictions about something not necessarily at the level of what will what action or what distribution of actions will every player play like that's going to be tricky because you know we know there's lots of different even pure strategy N equilibrium generically。

But maybe。The thing that we care about is not。Specifically。

 you know what action is player one going to play and what action is player two going to play and what action is player three going to play maybe the thing we care about is something yes some sort of。

Higher level summary of behavior like。What will the social welfare be？Right like you know。

 if what I care about is like the sum of player costs or utilities。

 maybe I can never like maybe maybe even though I can't predict exactly what everyone's going to do because there's lots of equilibriumria。

 for example， maybe I can nevertheless say something about what the social welfare is going to be that it will be。

You know， at least this big and， you know， never more than that， something like that。Okay。

 so so that's sort of going to be like what we try to do in this game。

 we sort of take as we take as a given。The presumption that play in some game will converge to an equilibrium。

Okay have some sort in this class will think about Nash equilibriumria。

 but you could go through the same exercise for correlated equi。But。

Without assuming we know which equilibrium will converge to and then we'll try to figure something out on the basis of that prediction。

 assuming we're going to converge to equilibrium， what can we say about。You know。

 the social welfare of the game， the some player costs， for example， is it going to be good。

 is it going to be bad？Okay， and in particular， we're going to define two quantities that are called the price of anarchy and the price of stability。

Which are what you can think of as。The pessimistic and the optimistic answer to this question respectively。

Okay， so if I。Take as a premise that the kind of play I'm going to observe will be some equilibrium。

 but there might be many equilibrium。The price of anarchy sort of asks the question。

What's the worst case how bad things how bad could things get in equilibrium meaning you know。

 we're sort of going to study the social welfare at。The worst Nash equilibrium。

 like the worst possible Nash equilibrium for social welfare。

And we'll talk a little bit about where these themes come from， but like informally， you know。

If the premise is really， I have no control at all over what people do。

 I just think that for the kinds of reasons we've been talking about in this class it'll end up at equilibrium。

 you know， the only kind of robust prediction I can make unless I have some theory for how people choose amongst equilibrium is that things will be no worse than the worst possible Ntash equilibrium and that's sort of the price of anarchy。

On the other hand， if I have some ability to nudge people like maybe I'm rolling out some app and I don't I can't force what people are going to do。

 but I can set defaults maybe right maybe I can sort of set things going at some initial state and then people are going to be free to deviate。

Then maybe I can't hope to implement。Behavior that's not at equilibrium because people will eventually figure that out and deviate away from it。

 but maybe。I could， you know， set the initial。Preferences or whatever in the app so that。

Things are at equilibrium and maybe if I do that I sort of expect play to be stable。

 nobody has any reason to deviate and if I had that power。

 then I could arrange things so that the initial state of the game was not at just an arbitrary equilibrium but at the best equilibrium。

Okay， and so the price of stability asks， okay。ButI don't have the ability to force people's actions。

 but I can set the initial state of the game how you know how good can I make things what is the social welfare at like the best equilibrium and it's called the price of stability because you know the only reason I can't just。

Set things up at like the socially optimal state is because that's not a stable solution。

 people will deviate away from it if they inly do so and like the price of stability asks okay。

 like if people have the ability to deviate away and so I need to find a stable state in this sort of game theoretic setting but otherwise I can pick any stable state asking like what is the what is the cost of that compared to optimal。

Okay。And so in this class， know we're going to ask all of these questions。

 this is sort like a case study。We're going to go through how you can ask and answer these questions for Nash equilibrium。

But in general， this is， you know it is。You can imagine going through this exercise for any cost of equilibriumria。

 right for correlatedre deria， of course correlated equilibriumria。

 whatever you think is sort of a computationally plausible prediction in your setting。Okay。

That's the game plan for today。Any high level questions？Okay。So。Yeah。You know。

 like if we're going to talk about。How bad things could get and how bad things must get we need to right like implicit this is something that sort of never came up when we were just talking about game dynamics because the individuals are just optimizing their utility function but now we're sort of talking about you know a judgment call what is the thing that we as like the you know。

Designer careabouts and are optimizing when we're asking for you know how good things。

Or how bad things are we need to fix like what is the thing we care about and that's going to be encoded in objective function。

Okay， so in general and you could talk about this with utility functions or cost functions。

 i'm going to be talking about a class of congestion games today so students so players are going to have cost functions rather than utility functions。

😊，And。The objective that the objective could in principle be anything。

 it's just you know some function that maps game states to real numbers and specifies， you know。

 like you know， how good or bad each game state is。And in this， you know， again。

 like just as you could study the price of anarchy or the price of stability for any objective function just to make things concrete since we have only one lecture on this topic today。

 the objective function that。I'm always going to be talking about is what's called social welfare or in this case social cost okay。

 and it's it's just like a utilitarian objective， it is what is the sum or average cost across all of the players in the game。

Okay， so just to。so in principle you could talk about any objective function。

 we're going to talk about social cost， which is a natural one。😊，And。Because we're talking about。

Cost functions rather than utility functions， we would like social cost to be small。

We'd like to sort of minimize people's average cost， but of course。

 if we were talking about games that had utility functions。

 social welfare would be the sum of the utility functions and we would want that to be big。Okay。

 but this is just you know， a normalization thing。Yeah。Okay， so the point is， you know like。

From the point of view of this lecture， we're always going to be talking about Nash equilibrium。

 we're always going to evaluate the quality of an equilibrium by the social cost。

 the sum of player's cost functions， but you should keep in the back of your mind that this is really just an exemplar and you can talk about the price of anarchy or the price of stability with respect to any class of equi and with respect to any objective function。

Okay。So now we can define。The price of anarchy and the price of stability。And so。You know。

 we want to talk about。How good or bad？Differenterence equilibrium game states are in terms of our objective function in terms of social cost。

And the question one of the first questions you should ask is compared to what？Okay， so。

The benchmark we are always going to use here。Is what I will call opt， which is sort of like。

You know， the optimal social cost you could arrange if。

You didn't have to worry about incentives if people would just do what they were told or if there were no people if it was just。

 you know， an algorithmic problem you were solving for。Okay。

 so opt is just the minimal possible value of the objective function right like if you like in a traffic route and game。

 for example， this would be sort of the minimum average commute time if I could direct everyone's car。

To go where I wanted to for the sole purpose of minimizing average commute time。

 and I didn't have to worry about whether。For every particular person。

 the route they were taking was the minimum cost route for them。Okay， so in particular。

Like the game profile， the action profile that optimizes social cost might not be an Nsh equilibrium this is sort of the source of the tension here。

Okay， so like opt。Is something that would be like achievable if you had global dictatorial control and could just optimize for this objective function。

 but it might not be achievable in a game theoretic setting because we've seen plenty of examples where you know。

Yeah， with things as simple as prisoners dilemma where equilibrium is just sort of。You know。

 at odds with with the outcome that sort of globally maximizes people's utility。Okay。

But nevertheless， that's going to be our objective。That makes sense it can be our benchmark。Okay。Um。

Okay， so that's opt， you know， like if we didn't have to worry about people making individual decisions。

 we would just compute opts and we'd tell them to play that but you know。

 like since we're talking about a strategic interaction， that's not what's going to happen。

 people are going to make decisions to optimize their own utility functions unilaterally。

 I'll change my action， if it makes things better for me even if it makes things worse globally。

And so。Informally， the price of anarchy measures how much worse the objective but in this case。

 the social cost。Could be。If I assume that players play according to a Nash equilibrium。

 but I assume nothing else， so in particular， like they might play according to the worst Nash equilibrium。

 the Nash equilibrium that has the worst social cost。

And the units in which we will measure the price of anarchy are sort of in comparison to opt。

 how much worse is the social cost multiplicatively compared to opt？Okay， so in particular。

The price of anarchy of some game G。Is。2。The worst case， the maximum。Overall。

 Nash equilibriumria of the game。Of the ratio， of the social cost at that na equilibrium compared to opt。

So for example。You know， like if if。The only Nash equilibrium actually is。

The game states that that minimizes social cost， then the price of anarchy is one that's like the best case。

 but if there's an equilibrium such that the。Social cost is twice as bad as opt。

 the price of anarchy is two。Okay， it might not be terrible。

If there's an equilibriums say it's an n player game。

 if there's an equilibrium where the social cost is like n times as much as opt or n as the number of players the price of anarchy would be n and that would be pretty bad it would mean that the sort of。

The you know how bad things can get as a multiplicative factor of opt can sort of。

 you know there's no limits they can as the game gets bigger， they can get arbiter really bad。Okay。

 but that's what the price of anarchy is measuring。The questions about the definition。

We've in general to talk about price of anarchy or price of stability that we'll see in a moment。

 you need to pin down a class of equilibrium solution concepts that you're going to maximize over in this case we're talking about Nash equilibrium。

 you need to pin down an objective function in this case we're talking about social cost。

And it's just the ratio between how bad things can get。

In the worst equilibrium as measured by your objective function compared to opt， by the way。

This is something you'll encounter on the homework。U。

When we talk about the price of anarchy it's sort of natural that it'd be a number bigger than one right so sort of one is like the best case。

 but like if things can be twice as bad as up to the price of anarchies two。

 if things can be three times as bad as up the price of anarchy is three。

And so if we were talking about。A game with like utility functions where we wanted to maximize social welfare rather than minimize social cost。

 the natural way to define price of anarchy would be to take the。Reciprocal of this so that。😊。

The price of anarchy would still be a number that was one or larger。Okay。Okay， good。

 so any questions？Okay， so the price of anarchy is like this pessimistic measure。

 which is sort of natural from a computer science perspective right where we're sort of used to worst case analyses and on the one hand those are nice because they're robust if we're not making assumptions in this case about which equilibrium we might converge to then you know like we're not going to be wrong like as long as we converge to some equilibrium it's not going to be worse than the worst one。

But on the other hand， like。A pessimistic analysis might not be appropriate in every situation。

 especially if we are in a situation where， for example， by setting the defaults on some app。

 I'm in a position to sort of nudge people in the right direction sort of pick the initial state and。

Have the presumption that so long as I've picked an equilibrium。

 so long as the initial state is stable in a strategic sense， I'll stay there。And so the。

The price of stability is sort of the optimistic version of the price of anarchy。

 which again maybe makes the most sense in settings where you can actually pick the initial state。So。

You know the price of stability is also going to compare the ratio of our objective in this case social cost at some equilibrium a compared to the optimal social cost。

 so again it's going to this price of stability， it's going to be a number that's bigger greater integral to one。

But rather than measuring this at the worst Nash equilibrium。

 the Nash equilibrium that maximizes social cost， and therefore this ratio。

 we're going to measure this if we're talking about the price of stability at the best equilibrium。

 the equilibrium that minimizes social cost or this ratio。诶。So very similar to the price of anarchy。

 you know， we're measuring the same quantity， the ratio of our objective at some equilibrium compared to optt。

 but here we're measuring it at the best equilibrium rather than the worst equilibrium。Okay。

Makes sense。Okay， you know， so like。Generally， computer scientists are bad at naming things like if you've taken。

262 or like a complexity theory class， you know you。

There'sP and NP and you always have to like explain。

 you know NP does not stand for not polynomial time it's like。On deterterministic polynomial so okay。

 we're generally bad at coming up with names， but like。I think in this case， the names are sort of。

Evocative that the names should if you if you sort of file this away in your brain correctly。

 the names should remind you of what the quantity is Okay so so。The price of anarchy is sort of。

 you know what happens if you if you have no control at all。

 people are just optimizing entirely for themselves and you're unable to make any assumption at all other than they arrive at some equilibrium。

The price of stability is sort of how bad things can get if you can tell people what to do。

 but like you're constrained to you， to tell them to do something that is stable you know。

 in a game thetic sense。Okay， so one one other， you know。Question just to like。

Check your understanding。So as I mentioned。You know。

 I've just defined price of anarchy and price of stability over naashsh Belria。

 but it's very natural to define these things for。You know。

 any of the solution concepts we've talked about pure strategy， mixed strategy。

 correlated course correlated equilibrium， any of them。

 the definition would just change the set that we're optimizing over it would be min and max not over the set of Nash equilibrium。

 but for example， over the set of correlated equilibrium。Okay， so I claim that。You know。

 if I looked at。The price of anarchy in some game and ordered it over the solution concepts we've thought about。

 you know the price of anarchy if your pure strategy a equilibrium would be the smallest。

 the price of anarchy for mixed strategy ash equilibrium could only be bigger the price of anarchy for correlated equilibrium could only be bigger the price of anarchy for co correlated equilibrium could only be bigger can anyone tell me why this is the correct ordering is subset。

Each sub exactly like。我不。that's right it's because it's because these solution concepts are nested within one another you know a nash equilibrium is a correlated equilibrium is a course correlated equilibrium and we're maximizing over the set so if we're maximizing over a strictly larger set we can only get a strictly larger value what if I were to talk about the price of stability and to arrange these things what would be the ordering。

Whats that mean？Yeah， so if it was the price of stability。

 the price of stability over course correlated equilibrium would be the smallest。

 then correlated equilibrium。Mix strategy and pure strategy National Library how come？Yeah。

 so it's because we're minimizing for the price of stability， so if I'm minimizing over a larger set。

 I can only find a smaller value。Yeah。O。😊，Okay。But we're going to talk about。

Congestion games in this lecture we know congestion games have pure strategy Nash equilibrium。

 we have a computationally plausible story for convergence to pure strategy N equilibriumria。

 these best response dynamics， but we don't necessarily know which equilibrium we get convergence to。

 and so it makes sense to think about both price of anarchy and price of stability and congestion games。

 but it also makes sense to think about it over pure strategy Nash equilibrium for other games we might want to enlarge the class。

For now， we're going to talk about these concepts over pure strategy national equilibrium。ok。U。

And so we're going to talk about。The price of energyarchy and price of stability for a variant of。

Congeesttion games that sort of I mentioned when we talked about congestion games。

 but we didn't think about it in great detail called fair cost sharing games。嗯。

So maybe just to sort of remind you， okay， what is a congestion game and then what is a you know。

 what is a fair cost sharing game？So remember。You know。

 way back when like upwards of like a month ago at this point。

 we talked about this class of congestion games and what made congestion game special was that。

There is this set of objects called facilities。And。An action。

 like an action for a person was always a subset of those facilities。Okay。

 so yeah at the time we were talking about like traffic routing games the facilities were the roads and a road network。

 the action you could take is a path like from your source to your destination that's a subset of the facilities and that involved some number of players like playing on each of the facilities。

Like there's some number of people who play on this road。And。Each facility had some cost function。

Which for facility J， we called LJ。And the cost of that facility was a function only of the number of people playing on it。

 we didn't care who was playing on it with the number of people playing on it。

 so like the cost of facility J is the load on facility J when at action profile A and JV people are playing on it。

And your cost for playing some。Subset of the facilities with just the sum of the loads on the facilities that you played on。

Okay， that was like the defining characteristic of a congestion game。And in traffic routing games。

 you know， we had these， you know。Arbitrary loss functions。

 but like there was always the sort of you know maybe implicit presumption that they were increasing like if we're modeling traffic on a road。

 you know， like somehow the more cars are driving on the road。

 the more congested it should become the longer it should take to drive along the road。

In a cost sharing game， things are different in a cost sharing game， it's still a congestion game。

 we've got facilities， each facility has some loss function。

 you play on a subset of the facilities and experience cost equal to the sum of the load on the facilities you're playing on。

 but the loss function for a facility is now decreasing in the number of players playing on it。Okay。

 and the idea just to sort of tell a story about these things。The idea is that。

What you're doing by planning on a facility is like building infrastructure Okay。

 so think about like。Producing， you know like fiber optic network to connect different nodes in a network。

All， so maybe I've got。You know， a graph or something。And there's players who， you know。

Correspond to source destination pairs in this network and what they would like to do is you know buy or you build you know commissioned to be built fiber optic network to connect。

You know， their source and their destination pairs。Now， maybe。Different。

Stretches of the network you know would have different construction costs right like if I have to like tunnel through a mountain or something。

 it's going to be really expensive。And so each potential edge has some。Like just cost to build it。

 I'll call it WJ。But like， you know， maybe you and I can。Share edges so maybe you know。

 like we could all build our own disjoint。Haaths connecting source and destination and not share anything。

 but if we did that we'd have to you know like produce this infrastructure on our own and pay for its entire cost。

 but if we can collaborate and find ways to share even some of the edges then what happens is we split the cost to build Okay so like the fiber optic network costs the same total amount to build no matter what。

But the idea is。If K people are going to share like an edge in this network。

 the cost for each of them is just a one over k fraction of the total cost to build it okay the idea is if we can share you know capital expenditures you know to build like build out this infrastructure。

 what's going to happen is we're just going to split the costs equally。Okay。

 so this is a congestion game。But it's a congestion game where the costs have this。

Like the costs of facilities have this particular form where。The know。

 there's some overall cost for building the facility， WJ。

 and that cost is split evenly across all of the players who use that facility。Okay。

 so it's just a congestion game where in particular the cost of a facility J has the form， you know。

 some constant WJ divided by K if K people are playing on。Okay。

Otherre there questions about this class of games？Yeah。对。Okay。这。mSo let's see so so first of all。

 like let's just remember how congestion games work。There's like a cost for each facility。Okay。

 that's what LJ of K is， this is like the cost for facility J if K people are using it。

And then like your cost in the game as a player， you're going to play on some subset of the facilities like。

 you know， some path in the graph， say。Your cost is the sum of the costs of the facilities you're playing on。

Okay， so each facility J has this cost， you know， WJ over K， if there's K people playing on it。

 and then your cost as you know， player I at some particular action profile is the sum overall of the facilities you are playing on of the cost of that facility。

 given how many other people are playing on it at that action profile。Good。Good question。

 other questions。Okay， so this class games makes sense， it's a congestion game， but we're like。

Making a further assumption on what the cost functions look like， yeah。对。If before。

 it was that that cost could also decrease with any。Say it again。4 people using it。

Yeah that's right so like in congestion games we didn't like like we analyzed the convergence of best response dynamics in general congestion games in which we made no assumptions at all about what this loss function looks like but I think when we were talking about traffic rout games it was natural to like think about it as you know probably increasing but you're right like we didn't assume that and that's why we can talk now about cost sharing games in which these are decreasing and everything we know about congestion games is still true these are congestion games。

Does that answer your question？Good。Other questions？Okay。Okay， so I think we said this already。

 like the thing that this is modeling is just that。嗯。😊，You know， we're building， you know。

 infrastructure that has some fixed capital cost and that cost is going to be split uniformly across all of the players who are using each particular piece of infrastructure。

Okay， and so like one thing that is convenient to notice here is。At some particular game state。

 like what is the social cost well social cost in general is the sum of the costs of all of the players。

But we can like think about that as you know， okay， like you each player。

 their cost is their cost summed across all of the facilities so we can think about social cost by first summing over the facilities and then summing over the cost of each player for that facility。

Right concession cost is this double sum， some over the players， some the cost。

 some over the facilities of the cost of that player at that facility。

Now the cost of each player at some facility J， if there's K players playing on it is WJ over K right it's like the capital cost of facility J split Kways。

And if there's K people。Playing on it then there's k people who are playing there's k people who are paying this cost wJ split K ways so what are they paying in aggregate they're paying wJ right which makes sense if you think about you know splitting these capital costs equally like you know the the sum total that people are paying is the。

Some total construction costs fall all over the facilities。Okay， so in this case。

If I look at the social cost objective， which is just the sum of everyone's individual cost functions。

That is just the sum over all of the facilities that anyone plays on of WJ。

 it's like the sum of the construction costs of all of the facilities that we end up building okay it's like this very simple thing and it's because you know for every facility there's exactly K people paying the cost of that facility over K in aggregate they're paying exactly the construction cost for that facility。

Okay， so this is a useful thing to observe， so I just want to make sure people understand that。

LikeSo is that clear like like we're going to study the price of anarchy and price of stability in these games。

 we care about the social cost objective， but like。😊，The social cost objective。

 which generically is the sum of the cost functions of all of the end players。

 in this case simplifies out to just like the sum of the construction costs for all of the facilities that have anyone playing on them at all。

Makes sense。Okay。U。Okay， so let's start thinking about what is the price of anarchy and price of stability in these games and let me。

And there's like a definitional ambiguity here that I。

I want to clear up first So like when we talk about。Priceive。

And when we defined price of anarchy or price of stability， you know， it's like， okay。

 for a particular game。You know we're going to like maximize over maximize or minimize over all of the equilibrium of that game it's clear what that means like there's a particular game each there's finitely many like game states each game state is or is not an equilibrium will'll just take the maximum over all of the game states that are equilibrium。

Okay， but like。Now I'm going to like state theorem that is talking about like the price of stability for fair cost sharing games or what does that mean like a fair cost sharing game like fair cost sharing games are like。

A class of games right there's many different I could write down。

Many different fair cost sharing games that would differ in。

How many players there were how many facilities there were what these WJs are right like there's many different things that would be instances of fair cost sharing games so what do I mean when I talk about the price of anarchy or the price of stability for fair cost sharing games？

But what I mean is I am going to。Consider i'm going to quantify over all possible fair cost sharing games so when I say that for fair cost sharing games the price of you know the price of stability is at least log n。

What I mean is。What I mean is。In this case。There exist fair cost sharing games for which the price of stability is at least login。

It's not true for every fair cost sharing game， I could write down a fair cost sharing game。

With one player and one facility and clearly there would only it wouldn't even be a game like there's only like one action you know the price of anarchy and price of stability in that game would be one there's no decisions right so I don't mean in every fair cost sharing game the price of anarchy is log in I mean。

What I mean is for every N。There exists a fair cost sharing game whose price of stability is login。

Okay， so that's sort of a more formal statement of what this theorem is。ok。Right， and okay。

 so with that。In mind， the theorem I want to I am is that for the class of fair cost sharing games。

 the price of stability。Over pure strategy N equilibriumria is at least the nthharonic number。

 which is just one plus one half plus one third plus one fourth all the way up to one over n and a useful fact to know about the nharonic number is it's about login。

Okay。And what this really means is that for any number of players in there exists a fair cost sharing game for which the best Nash equilibrium。

Has social cost that is。H of N times that of the social cost of。Okay。

So before we like try to prove such a thing， are there questions about what the statement of the theorem means？

Yeah。All of these we'd love it if they were small， so like price of stability， price of anarchy like。

Ideally， you know， if it was a just world， it would always be one。玩。

Oh because we want to understand exactly what it is so I'm also going to prove it the I'm upper bounding it it's going to turn out to be exactly the enharrmonic number so we're going to lower bound it an upper bound it which is great from the perspective of us understanding it we're going to know exactly what it is from the perspective of you know like fairness and justice in the world it kind of sucks because it's you know like growing within N that's not you know not a great bound but that's what it is。

Yeah。别。好对。Oh， it just means that you I could go in to a partnership with you where we're going to build this length of fiber optic cable and you pay 90% of it and I pay 10% of it that the fair just means we split it evenly。

嗯。Okay， so questions about what the theorem is。Okay， so。Okay， so remember what this there means。

 it just means for every N。There exists a fair cost sharing game for which the price ofarch sorry the price of stability is the endharonic number。

嗯。😊，So。😊，You know in this direction right we're going to have to argue something more complicated when we upper bound the price of stability but in this direction really we only need to give an example right you tell me N I need to demonstrate to you the existence of a particular fair cost sharing game that has who is best equilibrium you know ideally it's only equilibrium is worse than opt by the factor that I claim Okay so proving this theorem will will really be an exercise in giving a particular example i'm going to like。

Write down on the board like a particular like cost sharing game that has this property and that will prove the lower bound okay because this is a the statement of this theorem is an existential statement there exists a game in which things can be this bad。

O。Okay， so what does it look like we need to， you know。Write down an end player cost sharing game。

Here's what it looks like。Okay， so we're going to have n players one through n who each have some starting location。

 okay， it's going to be one of these vertices。And they'd all like to。

Build you a connection to the same destination up here， see。Okay。

Now there's two ways they could do it。Each player could。😡。

On their own to sort of buy a direct connection from their source to their from their source to the destination okay。

 so there's the option for each of them to buy a direct connection。Or。There's sort of this。

Common meeting points down here， they could all send their traffic down here。

And then if they did that， they have the opportunity to buy like a shared connection that。

This link they could buy that on which they could all share and their traffic would all go along there。

Okay， so what are the costs？Well。Let's say that actually it's like really easy to get to this。

 you know， shared meeting point， the costs for all of these links are zero。It's free。Okay。

 and this shared link here， they could purchase that for。

One plus epsilon dollars where epsilon is just going to be some positive number that you should think of as really small。

 going to make it as small as we want in this argument。Okay， so， you know。

 there's this like piece of infrastructure that they could all share that cost one plus epsilon dollars and if they bought that。

 then that would be it like they'd all be connected to their destination。

Or they could buy these sort of individual links， how much do those cost？

Well player one could connect for $1 a little bit less than the shared link。

Player two could connect for half a dollar。Player three could connect for a third of the dollar。

 so on and so forth， and player N could connect for one over n fraction of a dollar。Okay。

 so this is the setup。Okay， so my first question is what is opt like suppose I could just tell people what to do。

😡，Um， to minimize social cost， like like what is the way to connect all end of these players to their destination so that the cumulative like infrastructure costs are minimized。

希望大家谢。Yeah， they should all share this edge， right if they all share this edge。

The total infrastructure cost started as one plus epsilon so something that I can make arbitrarily close to one like there's clearly no way to do any better than that like。

If I don't buy this edge even just connecting player one is going to cost one and you know connecting any one of the other players that will get me above this budget so like the optimal thing to do from a perspective of social cost is just to like all share this edge and the total infrastructure costs are one plus epsilon arbitrarily close to one。

But is this an equilibrium？No， how come？This in a。F especially campus。Yeah。

 like since this is a congestion game， you can think about equilibrium through the lens of best response dynamics no matter where we start。

 if we run best response dynamics， we're going to get to an equilibrium okay。

 so you can figure out what the only equilibrium is by just thinking about what happens if you start there and then start running best response dynamics。

So it's going to happen well。Players one through n minus one are going to be pretty happy with this solution right like player one certainly wouldn't want to deviate like he's he's playing only one plus epsilon over n his deviation would cost him one he doesn't want to deviate player two doesn't want to deviate player three doesn't want to deviate。

But player N kind of wants to deviate。Because player N is currently paying his fair share of this edge。

 which is one plus epsilon over n。But he could just buy this direct connection。

 which cost him only one over n， which is a little bit smaller。Right so。If we started here。

The end player would have a best response to deviate to。Bying the direct connection。

And once he did that， all of a sudden the n minus， you know now there would only be n minus one people sharing this connection and so everyone would be paying one plus epsilon over n minus1。

And so now player n minus1 would have a small incentive to deviate。

Then there'd only be n minus two people sharing this connection then player n minus two would have a small incentive to deviate and the whole thing would unravel until there are only two people sharing this connection okay paying one plus epsilon over two you know。

Player two would now be better off buying the direct connection that costs one half and now you know player one is choosing between paying one plus epsilon in his own and playing one on his own。

Be better off playing one。So like although the optimal solution here involves everyone sharing this edge and has cost one plus epsilon。

The only equilibrium in this game is for everyone to buy the direct connection。

The only na equilibrium in this game。Has social cost， well， one plus one half plus one third plus。

Plus1 over n， which is the mharmonic number around login。Okay， so the。

Price of stability in this game is just the ratio between the endharmonic number and opt。

 it's the ratio between H of n and1 plus epsilon。And。😊，I can make epsilon as small as I want。

If you claimed for me that the price of stability for this class of games was anything that was smaller than the anharmonic number by making Epsilon small enough。

 this would be a counter examplele to that claim。Okay， so that claims not true。

 so the price of stability is at least to the enharmonic number。Okay。Make sense。

You look like you have a question。Yeah。Yeah了。那个我。ButThat's really like also the kind of way you're saying to go about inclusive numbers。

7%。嗯，对。你我再 back。That's right， so for this construction。

You can't really modify it to get something better than the en phharmonic number。And in fact。

 the next claim is going to be that there is no other construction that does that either。

 so the next claim is going to be that actually the price of stability in this class of games is also at most the endharmonic number。

 it's like exactly equal to the endharmonic number and that this example is the absolute worst case。

Yeah。go if there's only one time。对。I是是。Yeah， so the price of stability always measures the best pure strategy Nsh equilibrium。

 the price of anarchy always measures the worst， and if the game only has one pure strategy Nsh equilibrium like this one does。

 then in this particular instance of the game the price of anarchy is equal to the price of stability。

But like that's not always the case， sometimes there's more than one equilibrium。对， he one。

It's not one because we're still comparing to like we're not comparing the best Nash equilibrium if we were comparing the best Nash equilibrium to the worst Nash equilibrium。

 then if there was only one Nash equilibrium， the quantity would always be one。

 but that's not what we're doing we're comparing an Nash equilibrium to opt。

 so like in this game for example， there is only one Nash equilibrium but the price of civil is not one it's about login。

Yeah。Yeah， so suppose。Like suppose you said， I don't believe this theorem like this is bullshit。

 the price of stability is smaller than H of N， it's like H of n minus one。Okay。And I would say。

 okay， well， here's a counter examplele to your client。Right。😊，By making epsilon as small as I want。

 I can cause the price of stabilityity in this game to get arbitrarily close to H ofN。

And so in particular， if you claimed it was anything strictly smaller than H ofn。

 well by making Epsilon small enough， this would be a game in which the price stability was。

Bigger than what you said it was。Yeah， which would be a contradiction to any claim that the price of stability was anything strictly smaller than H ofM。

Okay。Okay， right， so this is some this was just an example。

 this is some particular class of games in which things can be as bad as HM。You might wonder。

 like if you're more clever， could you come up with like an even worse worst case。

 like maybe things could be worse than this。But the next claim is that they can't this is the worst case not even up to constant up to like exactly the worst case。

 right like。The claim is that。In fair cost and games。

 the price of stability is never larger than H ofM。Okay。

 and let's just make sure we understand what this means。RightBecause again。

 we're talking about a class of games。😊，So just as this theorem was really about an existential quantifier。

 like for every end， there exists a game where the price of stability is at least H of n。😊。

This is about a this theorem is really about a universal quantifier for every。Oh， for every end。

But for every fair cost sharing game with end players。

 the price of stability in that game is at most stage of them。Okay。

 that's the claim right so we've seen an example of a game where the price of stability can be as large as H of N this theorem really says this game is the worst case in every single fair cost sharing game you can show me I can prove to you that the price of stability cannot be larger than H of M which again is you know something on the order of log n。

😊，Okay。Does the。Statement of the theorem makes sense。And by the way。

Once you understand the statement of this theorem， the lower bounds。

Like conceptually the way you prove it is sort of straightforward。

 it was asserting the existence of some game with a bad price of stability and so like the proof was always going to be an example like I would like construct a game for you and we would just like work out in that game。

 what is the price of stability。Here we're making a claim about all fair cost sharing games we're saying for every fair cost sharing game you can show me right so doesn't matter how many facilities there are doesn't matter what these WJ facility costs are for any。

Fair cost steer game doesn't matter what subset of the actions or subset of the facilities or legal actions。

 you know， like for any fair cost sharing game you can show me。

The price of stability is at most the anharonic number。

Like here I can't prove this by giving an example， there's like a universal quantifier so we need we're going to need to like understand something about the structure of such games so that we can prove this there。

Yeah。That here。work that there exists secret。我哋整体记得上少。As。Pice stability and support forward。

That's right so really what we showed is for any number。For any number less than H of M。

If any number， you like， I don't know， what's a good variable name。

P for any for V for value for any value v less than H of n。

 there's a game that has price of stability greater than V， that's actually what we should。

But like in particular， that means the price of stability cannot be。Less than any such。Yeah。Yeah。系你啊。

They sharing。Give me like bath in this scar and this is like and making that structure any more complicated。

 inly increases the prices。I guess it depends on what you mean by this structure like it has nothing to do with like this picture I drew on the board a cost sharing game is a game of this form to tell me to describe a cost sharing game to me。

 you need to tell me how many facilities there are what the action set is for each player。

 each action set can be an arbitrary subset of the facilities and what these numbers WJR that describes an instance of a fair cost sharing game so it doesn't have to be played on a graph necessarily right so in particular like that it doesn't has nothing to do with that picture I drew on the board but it does have to have this form like when I say fair cost sharing game I mean a game that can be written like that。

You still look puzzled。Okay。Okay。Good questions， other questions。Okay。

 so so is it clear sort of what we're？Claiming here that for any fair cost sharing game you can show me again。

 specified by a number of players， a number of facilities。An action set for each player。

 which is just you know an action set for each player just a collection of subsets of the facilities and a sort of infrastructure cost WJ for each facility right that's what defines a fair cost steer game for any one of those。

😊，The price of stability is at most the mharmonic number。Okay。

 so we need to like know something about these games。

So let's remember what we know about these games so you know like these are congestion games。

Right so everything we once knew about congestion games。

 like still true and if we like think back hard， we still know it。So。

We really only ever knew one thing about congestion games right like how did we argue that best response dynamics converges well we figured out that congestion games were potential games They were exact potential games I had a potential function and。

That potential function had the property that。Every time a player makes the best response move the change in potential is exactly equal to the change in player cost and so in particular。

 if a player is only moving to decrease their cost， the potential function decrease okay。

 so we know that and in particular like it wasn't some abstract potential function it was this potential function。

😊，So let's just like page that back into our memory。

This is just the potential function we used when we were studying best response dynamics and congestion games。

The potential function， which just assigns a number to every game state， looked like this。

We just summed over all of the facilities that had anyone playing on them。

For each of those facilities， we summed from K equals one to the number of people playing on that facility and what were we summing up while it was just the cost of that facility when K people were on it。

Okay， so this isn't exactly social welfare， but this was the potential function。Okay， so this is。

Okay， not new like this is just， you know， like we're remembering what we。

 what we once knew long ago any of this class。Okay。

 this function decreases when people apply best responsibility。Everyone。If not， remember it。

 at least remember once having known this。对。Okay。So like in our case， you know， like in general。

 we were used to thinking about this in some abstract way because we were talking about like arbitrary congestion games。

 we didn't know anything about the loss functions， but like in our case since it's a fair cost sharing game we know what the loss functions are like the loss function。

😊，For facility J， when there's K people playing on it， it always has this form。

 it's like the capital cost to building facility J divided by a K。

 the number of people playing on it。Okay， so the potential function in our case。Is this？And。You know。

 just like looking at this。You know this capital cost WJ， this is common。To every term， right。

 everyone's paying， you know， WJ over K when there's K people on it。嗯。So we can pull this out。

RightAnd we can write the potential function as just the sum over all of the facilities that has anyone playing on it。

Times the capital cost of that facility， WJ。Times the sum from k equals1 to the number of people playing on it like one over k right that's just noticing that the cost function is WJ over k WJ is common to all these terms。

 so I'll pull it out in front of the sum。Okay看。And， you know， like。In the worst case。

 you know what is this， it's one plus one half plus one third。

 plus one fourth up until the number of people playing on it。In the worst case。

 all end people are playing on each facility right so upper bounding what this is。

 it's at most one plus one half plus one third plus one4 all the way up to 10 brand。

Which is exactly the mharmonic number。Right， so I can upper bound this by。

The sum overall of the facilities that anyone's playing on of the capital costs of that facility times the anharmonic number。

And if you remember， like we sort of stared at the social cost objective， right。

 the social cost objective in。Fair cost sharing games is just the sum of the capital costs of all of the facilities that end up getting builts Okay。

 it's just like this term here without the age of n pretend you can't。

Pretend the HM is not being projected onto my hand。Okay。

 so like one observation that really just comes from like。Digging up from the。You know。

 depths of our long forgotten memory， what the potential function is and then just plugging in the specifics of this game is just that this potential function。

It's not social cost， but it's not entirely unrelated to social cost either。

 it's upper bounded by social cost times theharonic number。Okay， is that？Makes sense。Okay。U。Okay。

 so the claim here is that the potential。You know it's no bigger than social cost times the anharonic number。

But I also want to claim that it's only bigger than social cost， so I want to claim that。

 you know like this objective function， it's bigger than social cost。

Okay well how do we know that well let's just like look at the second line of this derivation and there haven't been any inequalities yet so this is exactly the potential function it's the sum over all of the facilities that end up being built of the capital cost of that facility。

Times this term。Now this term is at least one。Right because it's one plus one half plus you know we don't know how far it's going to go it's going to end after the number of people playing on that facility。

 but the number of people playing on that facility that's built is at least one and so like。

Whatever this term is that's multiplying the capital cost of facility J。

 it's a number that is one or larger。Okay， now social cost is just the sum of the capital costs of the facilities that end up getting built。

This thing is the sum of the capital costs of the facilities that end up being built each time is a multiplier that is one or larger。

就。The potential function， in addition to being upper bounded by social cost times H of N。

 is also lower bounded by social cost。Right。So like。This potential function， which， you know。

 like confusingly for the early part of this class， was not equal to social cost。

In this class of games， okay， it's not equal to social cost， but it's not entirely unrelated。

 it's sort of sandwiched between social cost and social cost times the enharronic number。

 whatever it is that lives between these two bounds。Okay。Okay， and so now you know like。

It's always annoying when to prove a theorem you need to like sit down and do calculations。

 calculations are always ugly it's much better if you can just like sit under a palm tray or something and conduct a thought experiment so let's do that let's you know like the rest of the argument will be proof by thought experiment。

Okay。So our goal is to compete， you know， we've got an arbitrary fair cost sharing game。

 we don't know what the game looks like， we just know it's a fair cost sharing game。

Our goal is to somehow。Compare。The social cost of the best Nash equilibrium to the social cost at opt。

How are we going to do that？Well， we don't know much about this game， but like。

There's some game state that by definition， achieve social cost opt。Let's give that a name。

's call that a star。ok。It would be great if a star was a national equilibrium already。

 then the price of stability would be one。But it might not be。So let's imagine what happens if we。

Start play。Like we're going to like imagine the thought experiment is going to imagine what happens if we run best response dynamics。

 best response dynamics starting where。Well， let's start best response dynamics at a star。

 this game state that achieves social cost equal to opt。

Which is fine right like we we the way we analyze best response dynamics that sort of really didn't care where we started let's start it off why not。

And to start running best response dynamics and we know that no matter where we started best response dynamics。

 it will eventually converge， it'll converge to some pure strategy na equilibrium。Okay。

 so we started it up， so we turned the crank， we ran best response dynamics it ran， ran it ran。

 and eventually it stopped at some pure strategy Nash equilibrium， holiday prime。

We don't know which pure strategy national equilibriumlib Bur this was maybe it was the best one。

 maybe it was the worst one， but at least it wasn't。

Wasn't any better than the best one can't be better than the best one Okay。

 so let's think about what is the social cost at a prime Okay。

 and we'll be pesimistic and we'll sort of assume that。This was the best na equilibrium。

If there's a better one， you know？Even better。Okay， so what do we know？Well。We know that。

The social costs。At this Nash equilibrium。Is upper bounded by the potential function value at this equilibrium that's just because we observed up here that the social cost at any game state is upper bounded by its potential function value Okay。

 so the social cost。At this equilibrium a prime is at most the potential function value at a prime。

Now the potential function value at a prime is that most the potential function value at a star。

 the starting point。喂hy。Yeah。Yeah， I mean， that it was because we got to A prime by starting at A star and running best response dynamics and the whole point of a potential function is that it only decreases when we run best response dynamics。

So we started a star， we turned the crank on best response dynamics and ended today a prime。

 and the potential function decreased at every turn of that crank。

So the potential function at the National equilibrium is only smaller than the potential function at Ot。

😊，But the potential function at opt is at most the social cost at optt times H of M because of the other relationship we observed between our potential function and social cost。

And。The objective function at A star is opt because that was how we picked a star a star was the game state that had objective function opt。

And that's it。Right， Mike。The social costs。At the equilibrium we ended up at。

Is at most H of n times opt and we don't even know if the equilibrium we ended up at was the best one if there's a better one it's even smaller than this。

Okay， so this means no matter what game you give me。Through this thought experiment。

 I know that the social cost at the best equilibrium in your game is at most H of N times off。Okay。

 in particular。You can't come up with a worse example than this， like if you think about this game。

Like we even went through this thought experiment sort of explicitly we started at Ot。

 we thought about what would happen if you ran best response dynamics and you ended up at the national equilibrium yeah。

对。The think are。他。这是给这份的。Yeah。在的。There can't be a Nsh equilibrium that has several cost better than a star。

There could be one that has better than a prime though。

A prime is not necessarily the best na equilibrium， it's just the one we ended up at。

But in the worst case， there's not。Because we have seen an example where this H event bound is actually tight。

It makes sense。Okay， proof by thought experiment。Okay。So that was the price of stability。

 let's just tie up some loose end and establish what the price of anarchy is。😊。

The price of anarchy in these games is much easier to establish and much less interesting and much worse so the first claim is that in fair cost in games the price of anarchy could be you know for the price of stability。

 it was always at most login the enharonic number。The price of anarchy could be terrible。

 it could be as large as N。Okay， so the claim here， right， remember what these claims mean。Right。

 when you know， the claim here is really for any n for any number of players。

 there exists a fair cost sharing game for which the price of anarchy is as large as n。

I just need to give you an example to prove this。And the example is very easy。😊。

Suppose we've got end players starting at F。And they would all like to go to tea and there's two choices for how to get there。

Okay， they could all share this past。Or there's two choices how to get there。

 they could split them up however they like。This path has capital cost N。

This path has capital cost one。Okay。对。If you could tell them what to do。

 what would you tell them to do？Should they build the expensive link or the cheap link？

Probably build a cheap like， share the one， right so they could I'll share this one。Okay。

 can't do better than that， opt just one。But if they all share the end length。

 that's also a Nash equilibrium because if they're all sharing the end length。

Each of them is paying only one and so none of them has any incentive to unilaterally deviate to the cheap length because if they did that they'd have to pay the capital costs for it all on their own which wouldn't be any cheaper than what they're currently paying and if you wanted to make it a strict preference you could make the 101 plus eon。

Okay， so optt is one， but there exists a ash。At the worstnash。

Is n right so all sharing one by the way， is also a Nash equilibrium right so in this particular game instance the price of stability is one the optimal solution is a Nash equilibrium but there's another Nash equilibrium and that one's bad that one's as bad as n times worse than enough。

Okay， so。If we're looking at。So in these fair cost sharing games， you know。

 even though in like our price of stability example， there was a unique Nash equilibrium。

 like there are games with multiple Nash equilibrium and the worst one can be way worse than the best one。

Okay， the price of anarchy in these games can be as large as n。嗯。And this is the worst case。

 like the price of anarchy is also at most and so in particular it's like exactly in。嗯。

And just to sort of say out loud the quantifiers again， what this means is that。

For every aircraft sharing game you give me。It doesn't matter how you instantiate the capital costs。

 the action sets， number of facilities， whatever for every fair costuring game you give me the price of anarchy in that game is at most n so in particular like this parallel edges example is like the worst one。

Okay。Actually we're going to prove something a little bit stronger than that right so what is the statement here it's saying。

If I look at。Social cost， sum of the cost functions for all of the players。

 that social cost in na equilibriumum can be at most n times the social cost in the optimal solution。

But what we're going to establish is something even a little bit stronger than that。

 we're going to establish that player by player， if a as an na equilibrium。

 theyre their individual costs at the na equilibrium is at most n times their individual costs at the optimal solution。

 and so of course if that's true， then it's also true that the sum of their costs at equilibrium is at most。

 the sum of their costs at the optimal solution， but like what we're actually going to prove is the slightly stronger statement that this is true player by player。

Okay， makes sense。Okay， and this is pretty straightforward。So。

What do we know about the worst Nash equilibrium？We don't know。Much about it。

 but like we do know it's an actually equilibrium， so let's use that。

Right like what does it mean that something's an Ash equilibrium it means that no player can benefit。

 no player can decrease their cost。By unilaterally deviating from their part of the equilibrium to anything else。

 we know that any deviation by any player starting from an ash equilibrium will only increase the cost。

So we can think about any deviation we want。Let's think about this particular deviation。

 the deviation in which player I switches to playing the action that they would have been told to play in the socially optimal solution。

So there's this like， you know， socially optimal solution a star。

 let's think about what happens if player I deviates from playing their part of the Nash equilibrium to their part of the optimal solution AI star。

Okay， because a is a Nsh equilibrium， we know that this deviation cannot be beneficial to them。Okay。

 now what is their cost？If they play， they're part of the optimal solution。But everyone else plays。

 nobody else deviiates， everyone else plays they're part of the National Belma。Well。

 it's the sum over all of the facilities that they're playing in the optimal solution。

But the load on that facility isn't what it is in the optimal solution the load on that facility is。

😊，At least the load on that facility in A。Or， you know。

 at least one if nobody's playing on it today because now。Play your eyes， play on。Okay。

 so it's the sum over all of the facilities that player eye plays on in the optimal solution。

 but the load on those facilities isn't what it is in the optimal solution。

 it's the load on those facilities， given the number of players playing on it in this Nash equilibrium A。

😊，Now， what is that well， you know like。TheLoad on the facility is just the capital cost over the facility divided by the number of players playing on it。

嗯。Now， in the worst case。Player I finds himself playing alone on each of these facilities。Okay。

 but that's the right because the cost decreases the more players are playing on it so the most expensive each facility could be is the full capital costs of that facility that's like the。

嗯。You know， that's the cost the player I would experience if he was if he had to purchase that facility all on his own。

So pized cost is upper bounded by the sum of the costs of the facilities。

 but some of the capital costs of the facilities。On all of the facilities he would have played on in the optimal solution。

Okay， or equivalently， I can write that as n times the sum of the capital costs of the facilities he plays on in the optimal solution divided by n I'm allowed to multiply by n as long as I divide by n。

And this。嗯。Is the best case cost for the facility right like the the cheap if I'm going to play on some facility J like the cheapest I could ever possibly experience it at is if I was sharing it with absolutely everybody else。

So in particular， this is at most n times my cost in the optimal solution。Like here we're saying。

 well you know， like in the worst case， you know， if I deviate to my action profile in the optimal solution。

 I have to pay for the capital cost of the facility all on my own and in opt maybe I got to split it ns。

 but it can't be worse than that。ok。And that's it right。

 that establishes that for every player I my cost。In the Nash equilibrium。

Is at most n times my cost in the optimal solution？And so in particular。

 if I sum up the costs of all of the players at the na equilibrium it's at most n times the sum of the costs of all of the players and the optimal solution and so this really is the worst case example。

 you know I could。There could be game states where the where the social cost was worse than n times opt。

 but those game states could not be nat equilibriumlibria。Right like。

No matter what fair cost sharing game you give me the worst case cost for any Nash equilibrium。

 remember our first inequality here was using the Nash equilibrium condition。

 the worst case cost in a Nash equilibrium cannot be worse than n times opt and so once again this is the worst case example。

 so the price of anarchy in this class of games， it's exactly n the price of stability in this class of games。

 it's exactly the nharmonic number which is about login。Okay。Soow。That's it。

Let me know if you've got any questions， so there was the next class。Yes。Okay。



![](img/dd3ddc5d9bc9b958890c15bf3ef3104b_2.png)