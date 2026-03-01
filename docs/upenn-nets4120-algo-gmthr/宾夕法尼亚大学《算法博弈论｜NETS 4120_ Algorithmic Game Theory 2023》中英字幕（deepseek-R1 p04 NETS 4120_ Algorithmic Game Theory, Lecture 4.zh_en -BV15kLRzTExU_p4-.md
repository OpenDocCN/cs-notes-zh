# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p04 NETS 4120_ Algorithmic Game Theory, Lecture 4.zh_en -BV15kLRzTExU_p4-

あ好。

![](img/0cbb14a1f377ae4cc3b09109c5a10c7a_1.png)

All right。So before we begin， let me start by asking just if there's any pickups or administrative questions。

 the first homeworks do a week from today， I guess on grade scope。

 so let everyone know how to turn it in if need be。Everything's going well。嗯。Okay。Oh， yes。对。嗯。

Why don't I come up with that this weekend and then I will post it on Slack。嗯。

It will be roughly midterm that's what i'm going to aim for and just need to figure out the exact date。

 but let me let me commit to doing that over the weekend and remind me if I don't。

Good other questions。Okay， so just sort of maybe briefly。

Recapapping where we are in the story of this course and motivating what I want to do today。嗯。Okay。

 so we sort of， you know， we gave all of the classical definitions of game theory， you know。

 best response equilibriumria。😊，Caused everyone who took Econ 101 or game3 101 in the econ department to you know。

 remember， remember it。And we sort of said， well， you know， in this class。

We're not so interested necessarily in sort of two by two games， you know。

 we're interested in making predictions in large games。And we said sort of in order to do that。

 we need to think of number one structured classes of games right classes of games that at least conceivably someone could like fit in their minds。

 you know， even like unstructured games are sort of exponentially large and the number of players and that。

Although， you know， this classical idea from game theory and economics that。

We shouldn't expect to see， you know， if if gameplay is going to。Sbilize anywhere。

 it will have to be at a stable state of the game thats sort of like tautological but but concretely that says if we're going to predict you know if anything's going to be predictable at all。

 if it's not going to be some sort of you know chaotic system， you know。

 forever changing if it's going to stabilize anywhere。

 it will be at some notion of equilibrium where everyone is best responding to everyone else roughly speaking because otherwise it wouldn't be stable。

But we sort of said， okay，That's fine like if there is going to be a stable state， it'll probably be。

An equilibrium of some sort， but even when equilibrium exists。

 why should they be plausible predictions， we sort of want a computationally plausible story。

 not just for why you stay there， if you ever reach an equilibrium， but for how you get there。Okay。

 and。What we did last class is we sort of gave。You know。

 if you like sort of a first case study in when this might be right we defined a reasonably expressive class of games。

 class of large games， congestion games that had concise descriptions。

We studied a reasonably natural dynamic best response dynamics that was pretty general like there was a lot of unspecified moving parts unspecified in a good way。

 meaning， you know， it didn't matter what the starting state was。

 it didn't matter the order in which people。Took turns improving their action It didn't matter exactly how they improved their action。

 They didn't have to play an exact best response just a better response right and we sort of showed okay like。

You know， if you sort of believe that what people might do is。

Roughly described by some instantiation of this better response dynamics that we studied。

 then you should sort of believe that you know Nash equilibrium in particular pure strategy。

 Nash equilibrium are reasonable predictions in the context of congestion games because this dynamic sort of inevitably leads to them and in fact quickly leads to at least approximatepoimate Nash equilibrium。

Okay， so that's what we did last time。Okay。And what I want to do this time is sort of ask。

How far if we think of best response dynamics as one。

Computationally plausible story for how people might。End up at equilibrium。I want to ask like。

How far can we push that story， how broadly how much explanatory power does best response dynamics have for sort of play converging to Nash equilibriumlibria beyond congestion games like。

I what we proved last class it like you know is best response dynamic sort of a dynamic that really only makes sense to think about in congestion games or are there things that are not congestion games for which best response dynamics converges。

 does it we already know it doesn't converge in every game like in particular。

 there are games for which there are no pure strategy national equallibbri like rock paper scissors。

As we saw last time， you know if we can prove the best response dynamics converges。

 well that's a proof that the game in question has a pure strategy national equilibriumria so you know like we know for sure。

The class of games that it converges in can't be all games。But the question is。

 can we characterize exactly the class of games for which best response dynamics converges？

And sort of， you know say we sort of fully understand this part of the story right if you are a game in this class。

As response dynamicsy converges。If you're not， it doesn't。Okay， so that's the plan for today。

And you know， like concretely。The way I want to get there is I want to。

Consider a couple of more sort of case studies I want to。Study two games。

 neither of which are congestion games。Okay， put there。

Related to things we've studied and in each of those games I want to prove that best response dynamics cons despite the fact that they're not coning games。

 Okay， so like you know， like the。Answering the first part of that question， you know。

 these first two examples will show us that congestion games are not it like there's stuff that is not they could you know。

 there's there are games that are not congestion games for which best response dynamics converges。

And in doing that， we're going to go through a couple more examples of this style of proof we saw last time that sort of tracks a potential function。

In service of arguing that best response dynamics converges in these games。And having seen， you know。

 three proofs in this style， the one from last class for congestion games and the two today。

 what I then want to do is sort of。Try to abstract away。

What structure specifically we needed those games to have in order for the proof to go through and to use that structure to characterize。

Exactly when best response dynamics converge。 So I want to give an if and only if characterization that says。

 you know， if your game has this property， best response dynamics converges if not， it doesn't。Okay。

 so that's the plan for today。Are there any questions？Either about。The general。

Narative we're building up here details of what we did last time or questions about。

What I assert we're going to do today yeah before all the done sequentially yes。

 best response dynamics is a sequential dynamic。啊，没事没事，咱们听个会。What do you think？No how come。呃。

like some kind of cycleYeah， like you can the question was， you know。

 best response dynamics is like a sequential dynamic。

If we said everyone updated simultaneously would the theorem we proved off class still be true。

 the answer is no， you can sort of like imagine why it is even just in like a simple traffic routing game。

Right， so suppose you've got a traffic riding game。Super simple。

 it's like you know two roads up and down and the delay is just the number of people that take the road so the equilibrium is like half the people take the top road。

 half the people take the bottom road。嗯。And so okay， you know。

 suppose we start out with everyone taking the top road。

 you can sort of see how sequential best response dynamics is inevitably going to。

Very directly converged equilibrium just one by one， you know。

 while there are more people on the top road than the bottom road people will switch from the top road to the bottom road until it's an even split and then we'll be done but。

You know， like if you， if you think about simultaneous best response dynamics。

 suppose everyone's like moving along the top road and everyone simultaneously looks and they says。

 it's like 100 people on this top road。 there's zero people on this bottom road tomorrow。

 I'm gonna switch to the bottom road and you know， okay， so they do that。

 And then there's 100 people on this bottom road and nobody on the top road and it'll it'll just cycle back and forth。

 So there's some kind of like。😊，Symmetry that hasn't been broken there if we literally look at sequential best response dynamics。

Or simultaneous best response dynamics right so so you can think of great so you can think of sequential best response dynamics as just some kind of。

If you like perturbation of simultaneous best response dynamics， like， you know。

 maybe not everyone changes their action at literally the same time。

 even if there's just sort of like random offsets that induces some ordering in which people make their decisions and we don't care what the ordering is。

 the analysis we went through doesn't care what the ordering is。

 but like it does have to not be simultaneous to avoid this kind of kind of cycle good question。Yes。

 those end those players change their。Any increase in utility was good enough for our analysis。Yeah。

 so that was sort of a。A strength you know， a generality that was sort of nice you know like right。

 we're also trying to tell a story here in which we are assuming only sort of。

Assuming making minimal assumptions about the players。

 they don't need to be able to exactly optimize their path。

 they just need to be able to do something that improves on what they're currently doing。

Good question。Other questions？Yeah。Okay。So let me start by telling you about a game that。

Is not quite。A congestion game， although it did look a lot like a congestion game after I tell you what the game is I'm going to ask you to tell me why it's not a congestion game you like to try to remember the specifics of what to find a congestion game Okay。

 but here's the game we're talking about it's going to look a lot like a congestion game。

And it's called a load balancing game on identical machines。

Think about this as modeling something like the following， it's a bunch of like servers。

Those are sort of like the facilities。And。There's a bunch of players who correspond to people who would like to schedule one job。

 like one run of。Their piece of code on one of these machines。

Okay and the machines are identical so it's not like one has a you know better GPU than the other。

 but you know the other one has more RA or something what we'll think about on the homework the case when you know when that is the case when the machines are not identical but here the machines are identical so you don't you know the players don't have any a prior preference over what machine their job runs on。

But the jobs have different sizes right like I might be you might be running like linear regression。

 I might be training you know ResNe 50 to like class by imageNe mine's going to take longer to run than yours。

And the way that is。Represented is。Each of the players who correspond to people who want to run single jobs。

Has a size or a weight that I'll call WI。Okay， so like intuitively。

 the bigger my job is the longer it's going to take to run the bigger my WI。Okay。

 so that's just like a characteristic that's like inherent to the players they each have some fixed job of some fixed size they'd like to run。

Any action space？Is just the set of machines， the set of facilities， so I can choose a job， sorry。

 I can choose a machine to schedule my job on。Okay， so there's like 10 machines。

 my action space is just， you know one through 10， I point to one of the machines that's where I'm going to send my job。

Now the way jobs are processed on these machines its not like first come first serve or anything like that。

 it's like some kind of round robin scheduling and so all of the jobs like on a particular machine are going to finish at the same time。

Okay， so it's not that some of them are going to finish it earlier than others。

 they're all going to finish at the same time。And well what is that time well we need to wait until we can。

 you know， we've had enough computation time to run all of the jobs on that machine。

So the load on that machine， right， the cumulative running time for all of the job scheduled on that machine is just the sum over all of the players。

Who decided to schedule their job on that machine machine J of the weight。Of that player。Okay。

 so there's like some number of jobs assigned to。Machine 2。Um，You know， those jobs have some weight。

 like maybe the first one。Has weight six and the next one has weight three and there's another one that has weight one。

U。The load on that machine is 10。Okay， and the cost of a player is like the amount of time he needs to wait before his job completes。

 it's just the load on the machine he chose。Okay。So it looks kind of like a congestion game right like there's players。

 there's facilities， those are。The machines， the action space of each player corresponds to a subset of the facilities。

 in this case a very simple subset， just a singleleton， you just pick one of the facilities。😊。

And the load on a facility， which is equal to the cost of the player who chooses that facility is just the sum of the weights of the players who chose that facility。

Yeah。Sa thing of。That's sort of motivating why the cost of a player is equal to the load of the machine he chose because like if I if I ran the small jobs before the big ones。

 you might if you were a small job you might not care that there were big jobs running after you。

 but just to have a simple model like this where the cost of a player is equal to the load of the machine no matter right there's no aspect of time here where some of the jobs finish earlier。

Yeah， like I asked you to imagine a world where the jobs all finish at the same time。嗯。Okay。

 is the game clear？People have weights。They point to machines。

The load on a machine is the sum of the weights of the people who pointed to it。

And the cost of a player is equal to the weight of the machine she pointed to。Yeah。没。One machine。

 yeah， you can't you can't like split your job across multiple machines。

 you just run it on one machine。Okay。Nevertheless， I claim this is not a congestion game。

As we defined it last time and so our proof from last time does not like imply the best response dynamics must converge in this game。

 could anyone tell me why this is not a congestion game yeah？That's right。 so in a congestion game。

 the way we defined it。The cost of a facility。Was a function only of the number of players using that facility。

 but in particular not the identity of those players。

 we didn't care who was driving on the same road as us。

 just the number of people who were driving on the same road。

And so if all of the jobs were identical， if all of the jobs had weight one， for example。

 and all I cared about was therefore the number of people who were running jobs on my machine。

 this would be a congestion game。But because they're not and the load of a machine cannot be expressed just as a function of the number of people playing that on that machine。

 but actually cares about who they are because it's the sum of their weights。

 this is not a congestion game。Okay， is that clear？Yeah。

 like a condition here is like a special piece of this， but all the way through the。嗯。

I think you can rearrange those words into a correct sentence， so if all the weights are one。

 this is a special case of a congestion game。Like this would be an instant。

 this would be a congestion game if all of the weights were identical。But a congestion game， right。

 like the class of congestion games， of course。In some aspects。

 is much more general than this in this。You know like the the action set can be in general like a subset of the facilities right so like this this doesn't capture road networks so congestion games this is not a generalization of congestion games but neither is it a congestion game because of the weights。

嘅合病运。You could， by the way， you could define a generalization of congestion game like weighted congestion games where the action space is arbitrary subsets of the facilities once more。

 but now the cost of each facility is the sum of like the weights of the players on it。

And I think on one of the upcoming homeworks， you will show that in fact。

 best response dynamics need not converge in weighted congestion games。

 although you could define that generalization of congestion games， like it just it wouldn't be true。

 the best response。Andvers。In that class of games。But like nevertheless。

 we're going to show in this particular game it does。Does that make sense？Okay。

 good other questions about。Either the specifics of what this game are or why it is not a congestion game why our proof from last time doesn't apply right like if you remember our potential function last time sort of made crucial use of like the fact that the。

The the cost of each facility depends only on the number of people using it right like it's summed from the number of people the number of people ranging from one to you know like the number of people actually on the facility of the cost of the facility when that many people were on it so like。

It's not just like a technicality that this isn't a congestion game。

 but like exactly the same proof applies like our proof from last time actually used。

The fact that is not true in this game that the load on a facility depended only on the number of people playing on it。

Okay。Okay， nevertheless。I claim that best response dynamics converges in load balancing games。

On identical machines。Okay， so if you can run best for stone dynamics on this class of games or you know。

 imagine it being run。And you'll come to the same conclusion。

 even though this is not a congestion game。It converted to N equilibrium and like in particular。

 like。Load balancing aims and identical machines must therefore have pure strategy actually deliver。

Okay， and I'm going to sort of go through this proof and in in many respects。

 it's going to be quite similar to the proof that。Best response dynamics converges in congestion games we'll have to use a different potential function。

But like。There will be a minor difference in how we derive the conclusion that I sort of want to focus on because。

Remember， our goal from seeing this example on the next one is to try to like。

Focus on the aspects of the proof that are sort of important and those that aren't and try to abstract away from the important ones。

 exactly the class of games for which best response dynamics converges。Okay。So at a high level。

The form of the proof is going to be quite similar。Right like and just to sort of remember like。

The main thing we need to deal with。As players take turns making better responses in a game。

Like basically， the only thing we know directly from the definition of a better response is that at the moment at which they。

Change their action， they take their better response。

 their cost decreases like that's what it means that it's a better response。

And so it's like tempting to just try to like say， okay， well， like， you know。

 either they're decreasing their costs and that can't happen forever， so like converges。

But like that's not right because， you know， my cost decreases at the moment that I change my action。

But then it's your turn and your cost decreases at the moment that you change your action。

 but your change in action might have increased my cost， and so this doesn't rule out cycles。

And that's why we need to identify something else， some other single function。

 this thing called a potential function that is sort of like accumulating the progress and right it's important to have this one single function that is decreasing at every round of best response dynamics so that we can。

😊，Have some way of measuring quantifiable progress， right。

 like that's how that's the engine of the proof。And so。Yeah。

 so what we want to do once again at a high level is identify some potential function。

And argue because we know that each individual player's cost decreases at the moments at which they change their action。

That the potential function must decrease， we need to connect somehow the change in potential to the change in an individual player's cost that's and so it's the same high level strategy as last time。

Okay。So we've got to use a different potential function this time。

And the potential function is going to be。The sum of the squares of the load on each of the machines。

Okay， maybe half of that just for convenience， but the half is not really important。Okay。

 and probably right to。When I like。Whip a potential function out of my hacks， you know。

 the question is where did it come from？Okay， so in some sense。

 the potential function of course is reverse engineered to make what will follow workout right you sort of know the pattern of what has to work out and you want to find a potential function that has that property。

But maybe sort of intuitively。U。You know， what are you？Encouraging。

When you're asking for like the sum of the squares of a bunch of numbers to。Be small。

 you're sort of encouraging that the weight be as evenly as possible partitioned across the machines because the marginal contribution of like a unit of weight。

On a large machine is more than it is on a small machine if we're squaring the waves。Okay。

 and sort of intuitively like as equilibrium， you know。

 like the weights should be sort of evenly distributed because there should be no way for someone to move from a more loaded machine to a less loaded machine that like decreases their cost。

So that's sort of， you know， that's why you might， when you're hunting for a potential function in a game like this。

 consider something like squares of losses。Okay， now remember。

The thing we know in better response dynamics is that。

Individual players decrease their cost when we change when they change their action Okay。

 so we want to understand what an individual player's you know change in cost looks like and relate that to the potential function somehow。

So just like we did for congestion games。Let's think about。What happens when a particular player I？

Switchches from some machine J to some other machine J prime。Right， what's their change in cost Well。

 like definitionly it's the。Load is their costs after they switch。

 so the load on machine J prime after they switch to it will have to take into account the fact that their weight is now on it。

Minus their cost before they switched， which was the load on machine J。

They load before they switched。Okay， so after they switch。

 they have to pay for the load of the machine they're on。

 but the load of the machine they're on has increased because now they're on it as well。Okay。

 so after they switch， their cost is the load of machine J prime。Addduction profile a。

 I was like what it was before they switched plus their own weight plus WI because。

They add to the weight of the machine。嗯。And before they switched， it was just the load of Ma J。

 which at A Pro A already included their own weights。And we know， you know， like if nothing else。

 right， the one thing we know about better response dynamics is that like this expression has got to be negative because the fact that they made the switch right means that this switch was a good idea for them to make。

 they decreased their cost。Okay， so like this is like the one fact we have to work with that this expression here。

 the load of machine J prime plus WI， their cost after they switched minus the load of machine J that is negative。

 and we need to argue based on that fact that the potential function is decreasing。Okay。So now。

I want to think about what the change in potential looks like when the same switch happens when player I switches from machine J to machine J prime。

And I want to relate it to this expression somehow。

 so I want to look at the difference between the potential after the switch。

When player I is playing J prime。To fit the potential before the switch when player eyes is playing J。

And we can just write out what this is right like you know， so nothing's going on here other than。

Unraveling the definition of the potential function， which is the sum of the squares of the machines。

So like first of all。Like。For any machine that's not either J or J prime。

 right the one that player I switch to and from below it has not changed right nothing has changed for those other machines。

So when we're looking at the difference in potential， the difference。

 like the only terms that won't cancel out are the terms corresponding to machine J and machine J prior。

 those are the only machines whose load has changed， everything else cancels out in this difference。

Okay， so this difference is really just the squared load of the machines after the switch。

Minus the squared load of the machines before the switch。

And the only machines that have changed are J and J prime。So。After the switch。

 what's the load of machine J prime squared， oh it's just the load of machine J prime before the switch plus the weight of player IwiI squared。

And similarly， the load of machine J after the switch is the load of machine J before the switch minus WI squared right because this weight WI shifted from machine J to machine J prime。

Okay， and before the switch， well like。The shift hadn't happened yet。

 so it's just the load of machine J prime squared minus the load of machine J squared。

So this is just， you know like。Literally looked up at the definition of the potential function and written down like you know。

 syntactically what the change was。Is that clear？Okay。

But now like we're going to see some cancellation of terms right because we've got you know like a square here so what's you know a plus b squared is like a squared plus 2 AB plus b squared right so we're going to get like a you know load of machine J prime squared term and a load of machine J squared term and those are going to immediately cancel out。

With。They're're negative counterparts and so what we're going to be left with is just the cross terms。

 right？So what are the cross terms， we have you know， well。

 two times the weight of player I times the load of machine J prime plus the weight of player I squared。

And that's the first cross term。First pair of cross terms， second pair of cross terms are。Well。

 two times。The load of machine J times the negative of the weight of player I。Plus， again。

 pize weight squared and all of the other terms， the load of machine J and J prime squared have canceled out。

Okay， so this is just expanding out the quadratic and canceling terms。And remember。

 like what is our goal， our goal is to somehow relate this to this。

 so we'd like to do some algebra to find this expression within here。So let's。Do that。

 let's simplify so like first of all， you know， there's this convenient factor of one half out here that'll just get rid of these twos。

And so what are we left with？Well， like we can notice that every term inside here。

Includes a factor of WI， the weight of player eye， so we can pull that out。

And we can observe that this is just like the weight of player eye。Times the load of machine J prime。

Plus， WI。Minus the load of machine J。Okay。And so we've done it， we've found this term up here。

 the change in player eyes costs。Somehow inside this expression for the change in the potential。

So this is just WI times the change in polarized cost。

And since we know the change in polarized cost was negative。

We also know the change in potential is negative。Okay。

 and so because the potential function must strictly decrease with every better response move。

And can't go below zero。And yeah， it's only a finite number of game states。 this means we can。

We have to converge to best response dynamics， otherwise we would repeat a game state。

 which would contradict this strictly decreasing property。Okay， so we're done。

And what I want to highlight here。Is that？When we went through this sort of similar proof for congestion games。

What we did is we said， okay， well。The change in potential was exactly equal to the change in playerized costs。

 like that was how the potential function was rigged up。

But like the small thing I want to notice here is we didn't need that， that's not true here。

Right like the change in potential is not equal to the change in playerized cost， in fact。

 because this is a weighted congestion game you wouldn't be able to find。

AA potential function that has that property。嗯。But that's okay。 We didn't need it。

 We only needed the fact that。But like we didn't need these numbers to be the same。

 we needed them to have the same sign。Right， we needed that。

We could figure out from the fact that playerized cost decreased after his better response move。

 that the potential also decreased， we didn't need the magnitude of the decrease to be the same。ok。😊。

And so we've proved the theorem， best response dynamics converges。In news。Waied load balancing games。

Questions about that。Yep。This one。This is just so what is the potential function。

 it's the sum of the squares of the loads of the machines。

We've got the sum of the squares of all of the loads of the machines here。

 and we're subtracting off from that， the sum of the squares of all of the loads of the machines before player I made his move。

Now player， I moved from J to J prime， so the load on machine J changed。

 the load on machine J prime changed， but the load on all of the other machines did not change。

So we when we're looking at this difference， like the loads for any machine whose name is not J or J prime。

 those just cancel out in the difference because they're the same。

And so this is just the load out of machine。J after the switch squared plus the load of machine J prime after the switch squared。

Minus their loads before does that make sense？Good， other questions。Okay。All right。

 so the proof works even if the change in potential is not the change in cost as like a fun fact。

 it's possible to rig up a potential function in which the change in cost is equal to the change in potential like only if it's a congestion game。

 but you don't need that for the proof to work。O。嗯。So that like。

Wasn't a congestion game but it kind of looked like a congestion game right there were like facilities and people were playing on them and they had their you know like their actions were subset of the facilities and their costs were equal to the cost of the facility so。

😊，Although the proof was like a tiny bit different， you might think to yourself。You know。

 like maybe fine， it's not just congestion games on which best response dynamics converges。

 but it's like。You know。Things that are basically congestion games。

And so I want to just go through like one more example of a game in which best response dynamics converges like a super simple game that just doesn't look like a congestion game like doesn's have facilities。

 for example。Okay， and I'll call this the red state blue state game， but it's， you know。

 really simple game。But maybe is supposed to。Model some kind of polarization phenomena。

And so the idea is。Undering this game is a graph。Which maybe you can think of。

If it's helpful as sort of like a social network graph。

 the vertices are the players and the edges correspond to some kind of affinity like friendship。Okay。

 and in fact it could be a weighted graph so like。The weights could correspond to like， you know。

 the degree of friendship， they could even be negative weights so you could have enemies recorded in this graph。

嗯。And the players are the vertices。Okay， and the players need to pick between one of two options okay。

 so you can think of them as you know political positions that's probably like what the name of the game is trying to get you to think of。

 but like really it could be sort of any two options in which there are any kind of network effect so you can think of it as getting a Mac or a PC or an Android phone or an iPhone joining Twitter or mastodon or whatever。

ok。And the point is in this game。嗯。You don't have any。

A prior eye preference for which of these two options that you pick， red or blue。

But you'd really like to pick like there's some there's some kind of like network effects here。

 like you'd really like to have picks。The same option that your friends picked and maybe a different option than your enemies's picked。

Okay， so。嗯。😊，What's your utility？Oh and just like notationally to make it easy to write out the utility functions。

 let's identify the two options as one or negative one。Okay。

 so you're picking one or negative one and the reason why that'll just be like convenient notly is because。

If I multiply my choice by your choice， it'll be one if we pick the same thing and it'll be minus one if we pick something different。

Okay， so what's my utility？Well。It's the sum over all of the。All of my neighbors in the graph。

 all of the people that I'm connected to in this social network。Of。The weights of our connection。

At the weight of the edge connecting me to you。Times。My choice， times your choice。And remember。

 my choice times your choice is one if we pick the same thing and it's minus one if we pick something different。

So this is the same thing as。The sum of the weights。

I have to everybody in this network who picked the same choice as me。

Mine is the sum of the weights of everybody I'm connected to in this network。

For people who picked it a different choice than me。

So I get like positive utility when my friends have the same affiliation as I do。

 and I get negative utility when my friends have an opposite affiliation to me。Okay， yeah。

 the weights can be negative yeah， so if you want to have enemies in here with negative weights for the enemies you would get you know negative utility if they pick the it's emrassing to you know have the same political beliefs as you're you know dumbest enemies and you're proud to have picked the opposite from them so yes the we won't require in the analysis that the weights are positive。

Yeah， so we for at least food that。H。嗯。Yeah， I mean。

 like I guess like since we have weights like without loss of generality。

 it could be a complete graph and if you wanted to model an edge not existing。

 you just give it weight zero。But it doesn't have to be a complete graph。

 but basically the lack of an edge is equivalent to having an edge of weight zero。In this model。

Good question。Other questions about the game？Okay， so。

Not really a congestion game like it's hard to think about how you'd map this onto something that looks like a congestion game。

You know， like if you tried to say well， one and negative one are facilities or something。

 the problem is not just now。But there are weights， of course。

 like so you care who picks your affiliation and like what their weights are。

 but you also care who picks the other affiliation。Okay， so just it's some game。

 not a congestion game。Okay。Nevertheless， the claim is that。嗯。😊。

I'll state it you know the reverse set of implications like the people don't have to randomize here to come to a stable state this game always has pure strategy Nash equilibrium always has a pure strategy Nash equilibrium and in fact the way we are going to establish this is we're going to argue that best response dynamics converges right so like really the theorem is best response dynamics converges in the red state blue state can but like in particular this proves it's got a pure strategy Nash equilibrium which again isn't like a prior obvious。

嗯。And so let's go through this proof one more time itll be like the third time we've seen。

A proof in this style and once again like。You know， we basically need to。

Find the right potential function here it is now when you need to find one of these like on a homework problem you should really approach this in the reverse direction like when I present this on a slide the potential function is the first thing and then calculate like the change in playerized cost and the change in potential and like lo and behold it chose the right potential function but like you in trying come up with the potential function should probably be working your way backwards up this slide like calculate the change in playerized cost。

 calculate the change in potential and try to figure out what would be the potential function you could choose that would allow you to relate them。

But okay， here's our potential function。Um。What do I mean notationally by the sum of， you know。

 J less than I I mean， I don't want to double count edges。

 so I'm going to sum up over all pairs you know all of the edges， all pairs I and J。

 but so that I don't count。The edge twice， once from I to J and once from J to I。

 I'm only going to count it。 I'm only going to count the pairs in the order in which J is less than I。

But this just means I'm summing up over all of the edges in the graph。

 and I'm counting each one once。Okay， so what's the potential function？

It's the sum over all of the edges in the graph， not double counting。Of the weight of that edge。

 the weight of the edge between I and J times the。Choice of action I times the choice of action J right。

 the choice of player I times the choice of player J。

 which remembers just one if they're the same and minus one if they're not。

 so it's the sum of all of the edges in the graph of plus the weight of that edge if player I and J pick the same action and minus the weight of the edge if they pick a different I。

Okay， that's the that function。And once again。Turning the crank on our proof templates。You know。

 we want to think about what is the change in a particular player eyes cost when they change their action The reason we want to think about that is because that is really the only object that we have any handle on we know that。

The change in cost of a player will be some monotone quantity because players change their action only when it'。

Decreases their cost or increases their utility。Okay， so what is it in this case？U。

Like like first of all， what does changing your action even mean in this game there's only two actions you know one and negative one and so changing your action is like the same thing as as multiplying your action by negative one right like either you're going to switch from affiliation one to affiliation minus1 or you'll switch from affiliation minus one to affiliation one This is another place where we're sort of getting some。

Getting something out of our convenient convention of associating the two actions with one and minus one。

 changing your action corresponds to multiplying by minus one。Okay， so before your change。

Your utility was the sum over all of your neighbors in the graph。

Of the weight of the edge between you and your neighbor。Times your choice。

 times your neighbor's choice。And after your change， it was the same thing， except your choice。

Now changed from whatever it was before， AI said minus that， minus AI。Okay。

And so this is especially simple expression， your change in utility well， right like you know。

It's your utility before， minus negative your utility before。

 so it's just twice your utility before the chain。Your change in utility is always exactly equal to twice your utility before the change。

Does that make sense？Okay。Now the next step in this proof template is to make sure that it's to look at the change in potential and make sure that we're making progress along this one single axis we've defined。

And the only tool we have to do that is to try to find somehow within the expression for change in potential。

 you know， like the expression for change in playerized utility because we know the sign of that thing at least。

And so you know we do what we need to do， we write out the change in potential。

Whi in this case right like what's the potential function before the change。

 well it's just the sum overall of the edges counting each one exactly once of the weight of the edge times the choice of the left end point times the choice of the right endpoint。

And。嗯。In particular， like。Player eye is the one who's changed his action。

And so any edge that did not involve player I。Cancels out in this difference in potential。

 right like， you know。Any term that did not involve player I is the same before and afterwards。

So the only terms here that change here this is a confusing notation because I here is a constant。

 I is the name of the particular player who changed action。

 the index of summation here is only J or the only terms that change。

Are those terms corresponding to edges that had one endpoint at player eye？All right。

 so the changed terms are the edges that had one endpoint at player I。

 the other endpoint was somewhere else J。And so the change of potential， it's you know。

 the sum over all of those edges， all of those JI pairs。Of the weight of the edge times AI times AJ。

 that was what it was before the change。And then after the change， we sum over the same set of edges。

AI now negated his action。And so the change in potential is exactly equal to the change in polarized utility。

And so we know that player eye is always moving。Such that his utility increases after his move。

The potential also moves monotonically。And therefore。

 we can rule out cycles and establish the best response dynamics converges and that。These red state。

 blue tape games have pure strategy to actually deliver it。Okay。Yeah。は。Let's see。

So if we summed over the utility of all of the players， I guess we would count each edge twice。

 but I guess this is half of social welfare so yeah this is an example of a game where it happens that social welfare is a potential function and every better response move not only improves the utility of that player。

 but。But improved social welfare， which is something that wasn't true in the last two games we studied。

So yes， good point。Yes， AI。AI is the old action， so this is like the potential at state A and then we're considering what happens when player I changes his action。

 which just corresponds to like negating so like negative AI is the new action。

So when we calculate the change， I thought we do。5 minus。I we start with work like the end of this。

Yeah， so long as you do it consistently in the change in utility and the change in potential。

 it doesn't really matter。Right， like so I guess， you know。

 here the utility after the change will be higher。Because people are maximizing utility instead of minimizing cost and so we've written things in this way so that。

The change is like negative as it was in the previous games。

 so in the previous games it was cost instead of utility but。

If we had written things the other way around。It would have been fine so long as we hadn't like used different orderings and our different calculations we just want that directionally。

The change in utility or cost is the same as the change in potential doesn't really matter if that so maybe that's a useful thing to point out right like so like。

We noticed in the last proof that we sort of don't care。

That the change in utility is exactly equal to the change in costs。

 like we only care that the signs are the same。We've also sort of been talking about decreasing potential functions。

 but like。An increasing potential function would be just as good。

We just need to the meat of the proof is sort of ruling out the possibility that there are cycles that we ever visit the same state twice。

 as long as the potential function is making monotonic progress either upwards or downwards we're okay。

That makes sense。Yes。Okay。Okay， so now we've seen。You know， three examples of this proof basically。

I want to think like， okay， what do we need？What property does a game need to like make this proof work？

And so。You it seems very closely related to potential functions。

 so why don't we give a name to the kinds of things we're talking about。So a function。

That maps game states to numbers。We'll call it an exact potential function for a game。If。

For every game state。And for every player who might change his action。And for every。Action。

BI that he might change his action too。We have that。The change in the potential function。

After the switch compared to the before the switch。

Is exactly equal to the change in polarized costs after the switch compared to before the switch。

Okay， so for congestion games and for the red state blue state game we gave exact potential functions。

 those were functions that had this property that we could relate。For every game state。

 for every player and for every deviation in that player。Exactly。

Her change in costs with the change in potential。Yeah。But we saw this example of you know the。

Load balancing game， the weighted load balancing game。That。

We proved best response dynamics converged without an exact potential function。嗯。

And so I guess we don't really need an exact potential function for this proof to work out。

We really only need an ordinal potential function。What is an ordinal potential function？Well， again。

 it's like some object。That just sort of。Label is the game states with numbers right it's like got a label gun and so it's a way of writing a number on every game state。

And it should have the property that for every game states。And every player， I。And every。Deviation。

 every change in action the player I might consider changing his action from AI to some other action B。

That。If the change in action decreases playerized cost。

Then the change in action also decreases the potential function。

RightThat's really this was sort of what we needed to make the proof go through because。

The fact that we were playing best response dynamics。Gave us the left side of this implication。

The playerized costs decreased through this move。And we used the right side of the implication that the potential function decreased right so so an ordinal potential function is more general than an exact potential function。

 exact potential functions， of course our ordinal potential functions。

 but the reverse is not necessarily true in particular like the the potential function we used in the load balancing game was not an exact potential function。

😊，Okay。So is it clear what an ordinal potential function is and why？

At least if we want to use the same proof template we've been using to prove the best response dynamics converges。

 it is sufficient if someone shows us an ordinal potential function。Because again。

 like the way the proof works is。You know， we need to argue that at every step。

 the potential decreases because that tells us we can never return to the same state twice。

And the thing best response tells us is that every time a player takes a move in the dynamic。

 it's because their cost has decreased。And this is exactly the implication we need to。

Get the conclusion that， you know， when someone takes a move， the potential decreases。Okay。

So like hopefully， you know， you've seen the proof three times now。

 you could write out a general proof that sort of says if I give you an potential if a game has an ornal potential function。

 then Beth's response dynamics conver。Okay。But like you might at this point wonder。Like okay。

 like we you know， we've been hammering at this like one like proof technology like find a potential function and like you know like squeeze it until you get convergence of best response dynamics and like。

 you know， if you like squeeze hard you realize okay like you know。

 an ordinal potential function is sufficient but you might think okay， but like maybe。😊。

There's only so much you can get from excqueezing this oneproof technology like maybe this is just not a powerful enough argument to argue that best response dynamics converges in all games like maybe there are games that don't have ordinal potential functions。

 but nevertheless such that best response dynamics converges right like that's a completely reasonable thing to believe like in general like you know like。

The same proof technique doesn't work for you know。

 all categories of statements you might want to prove。Great， so you might think， okay， fine， like。

 you know， this somehow maybe characterizes。Like。The class of games you can prove。

You can prove in which best response dynamics converges using this particular proof technique。

 but like that's not an interesting class because maybe。

There are games that for which your best response dynamics converges。

 but like to prove it you need some entirely different technique。

That's a reasonable thing to believe。But。It's not true。

 this is a sort of complete proof technique for best response dynamics。Right， so。

This is going to give us a characterization of exactly when best response dynamics converges。

So the claim is that best response dynamics。Is guaranteed to converge in a game G if and only if the game has an ordinal potential function。

Okay， so so like our we've like hopefully now you can sort of。

Recite off by rot the proof that if a game has an ordinal potential function。

 then best response dynamics converges in that game。 But I claim the reverse is also true。

 If best response dynamics converges in the game， it has an ordinal potential function and so。

You know， like the complaint that I have。You，You might。

 you might have considered like complaining that I've like。

Criippleled your career proving that best response dynamics converges in different classes of games by only teaching you one method of proof。

 but you know I can respond and say it's the only one you need like you know if best response dynamics converges。

 you might as well try to you do it by just keep continuing to look for that ordial potential。Yeah。

 I guess that was my question， even if we do group this。Oh no， not necessarily， I mean。

 it's exactly as difficult to tell if as it is to tell that best response dynamics converges。

 but you know if best response dynamics converges， there is an or potential function。But yeah。

 so might require like cleverness it's not like it's not like this mechans like it's not like there's a decision。

 it's not like there's an algorithm but can take as input a description of a game and mechanistically tell you does best response dynamics converge or not。

 although as we'll see when we prove this。Yeah。There is sort of a mechanistic way to think about it if you。

 but it might not be computationally efficient。嗯。😊，Yeah， so this doesn't mean that like。

Your next problem says that's easy， it just means。You know， there's always a proof of this form。

Good question other questions before we like jump in and prove this other questions about like。

What the theorem is saying？My best response at MI is that just that。在就是。Iteration of fire。

Yeah good question so like what do I mean by best response dynamics I mean basically。Something。

Like I mean， every instantiation of the algorithm we've been proving things with so far， so it means。

It means yeah， like at every iteration， someone chooses an action that is a better response。

 but like I also want it to hold for every starting point and for every sequence。

for every ordering in which people might pick best response type pick best responses。

 so you might mean something more limited that there exists say starting points and there exists a particular special sequence of rounds in which people can play。

You know， better responses that converge to equilibrium。But I claim that section that that wouldn't。

 you know， if I replaced all these universal quantifiers， you know。

 for all with existential ones there exists， that wouldn't be very interesting because of course if I start at a na equilibrium。

Then， okay， best response dynamics won't leave it。 So when I， when I say best response dynamics。

 I really mean。When I say best response dynamics converges， I mean。

 it's got to be that no matter where I start from and no matter what order in which I let people。

Change their actions to decrease their cost we must。Yeah， there's no way to get in a cycle。

 you must converge to the na River， good point。Other questions about what the theorem says before we prove it？

Okay。So。Okay， we've done again like the forward direction， if there's an ordinal potential function。

 then best response dynamics converges， we've basically seen that proof three times。

 so I'm not going to。Do it again。 But， you know， like， you should。Introspect。

 then make sure you remember how to do that。嗯。Let's prove the opposite direction so I want to。

Think you i'm starting from the statement that best response dynamics converges in some classical games and what I need to do in the proof is I need to like。

Think about that statement and somehow extract from it an ordinal potential function that I can demonstrate to you。

Okay， so the nature of。You know， the input output behavior of the proof is you give me a game in which best response dynamics converges。

 I somehow process that game into an orddinal potential function。Okay。

So I want to think about a graph， of an abstract graph that is described here。

 but maybe let me like tell you about it in words before you try to read the definition。

It's going to be a really big graph。So basically there's going to be a vertex for every state of the game。

 so remember what is a state of the game？It is a choice of actions for each of the end players。

 so if there's K actions per player and n players there's you know K to the end game state so there's a lot of them。

Okay， but that's okay， like， you know， that would be annoying if we were coding up an algorithm。

 but when we're just like conjuring the object in a proof， it's no big deal。Okay。

 so let's imagine a game。It's got a whole lot of game states， exponentially many game states。

But like nevertheless。I can imagine a giant graph that has one vertex for every game state。Okay。

So those are the vertices of the graph。Now。Let's think about the edges of the graph。Basically。

 I want。There to be an edge。Between vertices， right an edge between two game states。

 a directed edge from game state。A1 to game state a2。If there is a way。To get。

From the first game state to the second game state。Va one step of best response dynamics。Okay。

 so let's think about what that means。Well， first of all， like in one step of best response dynamics。

 like definitionally only one player is changing their action， it's like for sure。

 if there's an edge between， you know， like game state A and game state B。

 it had better be that A and B are actually identical except in one coordinate。

 they must be exactly the same except in one player's action。Okay。

 so like most vertices can't have edges between them just because of that because they differ in two or more players actions right if two game states that differ in two or more players actions cannot have edges between each other this in this graph we're constructing。

 but if they differ in the unilateral change in one player's action， they might。Okay。

 and not just that。Right。I need that。The action that these two game states differ in actually constitutes a better response for the player changing their action。

So it's got to be that。Yeah， if there's an edge between A and B， it's got to be that。

The cost for the player that is changing their action between A and B。

 the player whose index I is the one index that differs between these game states actually decreases。

 it's actually smaller in game state B than game state A。Okay。So is that？

Does that make sense so I'm like defining some very big graph？

But like hopefully it's got some kind of。Intuitive structure like。There are。Edges。嗯。

Every edge in this graph corresponds to。What could potentially be one round of best response dynamics？

If you started at the。Beginning of the edge， there would be some player who could unilaterally change their action to get you to the end of the edge and in doing so would decrease their cost and for every such pair there is an edge so the edges in this graph exactly correspond to sort of traversals that you could make in the state space of the game corresponding to a single round of best response dynamics。

Does that make sense， is it clear what the graph is？Okay。So once we've defined this graph。

We can think of best response dynamics as a traversal of this graph。All right， like we start。

Somewhere best response dynamics starts that doesn't care what game state we start at so we could start at any vertex。

 any game state。And。We move along by following edges in the graph there might be choices right there might be vertices for which more than one player has a better response so there's multiple outgoing choices better response dynamics could take any of them。

Okay， so so right like the out degree could be as large as and any of the players could potentially have a better response move。

But like。Better response dynamics， like although it's not fully specified。

 we don't know what vertex at start set， we don't know what choices it'll make like if I think about visualizing the trajectory of the game as we play better response dynamics。

 it would be some traversal of this graph it would you know there'd be like a little you know a dot specifying where we are and the dot would move along the graph always following one of the outgoing edges。

Is that clear？Okay， so。Okay， so best response dynamics corresponds to some traversal of this graph。

Um。What are the Nashlibria？In this graph， what like。What do the Nash equilibriumlib look like？Yeah。

There's sink， right。A Nsh equilibrium a pure strategy N equilibrium is a game state such that nobody has a best such everyone's already playing a best response so nobody can unilaterally deviate to improve their cost and so if we're at a Nsh equilibrium。

There must be no outgoing edges， right because outgoing edges indicate that someone can change their action and decrease their cost。

 similarly if there are no outgoing edges， by definition we're at an ash equilibrium。Okay。

 so best response dynamics corresponds to a traversal of this graph。

 nashic Bellibria are the sinks in this graph。What does it mean that best response dynamics converges？

If you tell me best response dynamics converges， what do I know about this graph？你搞死。There are sink。

 what else？No cycle。Well， sinks you could have a graph that has sinks and also cycles but but like like the meaning。

 like what we mean when we say best response dynamics converges is that this graph has no cycles right because we ask for all these universal quantifiers no matter where you start no matter what order in which you let players deviate。

 you always converge， well that wouldn't be true if there was a cycle in this graph because in particular if we start somewhere that leads into the cycle and we consider the sequence of best responses corresponding to the cycle。

 we might continue traversing the cycle forever and never never breach a national equilibrium。😊，Okay。

 so the Nationalsh Libria。Are sinks in this graph？And。

The hypothesis of the theorem that best response dynamics converges or the hypothesis of this direction of the theorem。

Can be translated into the language of this graph as meaning exactly the graph is ascyclical。

 There are no cycles in the graph。Okay， make sense。Yeah。Okay， so what we need to do， right。

 you gave me a game。Which I can sort of unroll into this graph， you told me the game。

I such the best response converges， so I know that the graph is acyclic I need to somehow use this graph。

And the fact that it's acyclic to construct an ordinal potential function to you for you， okay。

That's like what we need to do。Okay， so starting with some basic facts。嗯。

I need to use somehow that the game is acyclic， right that the graph is acyclic because it's like an important hypothesis here so like。

I claim that one simple implication of the fact that the graph is acyclic is that。

From every starting point， from every vertex in this graph。

 there is some sink that is reachable through a path through the graph。Can anyone tell me why？

You're shaking your head。Proably good cycle that then had like an outgoing brush as well。

 Like if you had a。Like， do you take three points for pen in a cycle。

 but then also point to a sink like outside of them that with them？

I guess you're saying that so something like that would sort of correspond to a scenario where there exists a sequence of better response moves that reaches the equilibrium but not every sequence does in particular there's a sequence that goes around the cycle so like a game that had that property we would not say that best response dynamics converges when we say best response dynamics converges we mean for every possible sequence of better response moves so in particular there aren't like it rules out this case there are no cycles。

Okay， but。Sure mind I read book。Yeah， but say there are not like。Yeah。

 the starting premise is there's no cycles in the graph。

 how come I know that from every starting point I can reach a sink， yeah。不是。Yeah。T edge。

WeTake a move that next state if it's a best response， otherwise we did， but not know。是的。Yeah。

 although I guess this is just like like a fact about graphs。

 so like the you don't necessarily need to think about how we constructed the edges。

Like I claim in every acyclic graph， there's a sink that is reachable from every state， yeah。

When are we staying basic children。Not only that there's a sink。

 but that there's a sink that is reachable from every vertex。

That will the end the Edinburgh has this。Yeah， and I guess you can modify that to。

Argugue that that's true from every starting point as well。Yeah， or maybe like even simpler。

 like just imagine that you're standing on one of these vertices。

And then you decide to take a walk and you're just you're going to like step along edges as you see them。

Unless you get stuck。And。There's no cycles in the graph。 So like。

 where are you going to go on this walk like。It might be the。

You end up in the same place you were before， except that can't happen because that would be a cycle。

对。了解。Yeah， so like if you can't if you're taking this walk and you can't visit the same state twice and you can't because there's no cycles。

 then you know like my walk can't have infinite length because you know the number of steps I take can't be more than the number of vertices in the graph and so whatever path I end up taking I have to end up at a sink because I will eventually reach a point at which I can no longer go on and that'll in particular be a path from me to the sink and so every vertex。

Every。From every vertex， there is a reachable thing。So in particular。嗯。It makes sense to think about。

The length of the longest finite path。From a vertex to a sink because I know from every vertex。

 there are reachable sinks， and I know that every path in the graph is finite because there's no cycles。

Okay， so that's going to be my potential function。Let's make sure everyone's clear on what this is right so what is it。

 first of all， what is a potential function it is just。

Like the kind of object it is is just a mapping from game states to numbers it's a way of labeling the game states with numbers and this is the way i'm choosing to do it I am。

Labelling every game state with the length of the longest path from that game state to any sink。

In the graph。Okay， I know there is at least one such path and I know that the length of any such path is finite and so this is like a well defined function。

Yeah。The number of steps。It's an unweighted graph， so just the number of edges I need to traverse along the path。

Okay。😊，Is the definition clear， like this is some function mapping game states to numbers。

And so like we need to argue it's a potential function。Now remember。An ordinal potential function。

So remember。The edges in this graph correspond to better response moves and an ordinal potential function must have the property that for every better response move。

 or for every better response move， for every unilateral deviation that decreases the deviating player's cost。

 the potential must decrease。Now all of the better response moves correspond to edges in this graph。

 so what we need to show is that for every edge in this graph going from A to B。

The potential at B had better be lower than the potential at A。If we can show that。

 that will mean that our function is indeed an ordinal potential function。对。Okay。

 so I claim that this is true， I claim that in fact。

Not only is the potential at B lower than the potential at A， it is lower by at least one。

 the potential at A is at least one larger than the potential at B。Can anyone tell me why？Yes。

这还lo王这还lo王是。body。Yeah。Like phi of a is the length of the longest path from A to a sink。So。You know。

 I'm trying to think of what is the longest path oh question？Not necessarily。Okay可。

There could be multiple paths， right， there's potentially multiple outgoing edges。Right， so I could。

Have something that looks like this。Right， so this is， I claim the potential here is。

At least one more than the potential here， but not exactly one more because there's an even longer path。

对。3ion。Well remember this is a directed graph， so you know there can be but like the out degree is not just one and if I took away the directions there could be cycles there's just no directed cycles。

Okay， but right， so so this isn't anequality， it's an inequality。

 but right why is it the case that the potential。At a。

Has to be at least one more than the potential it be。Well。

 like what's the longest path from A to a sink？You know， who knows， but like。

If B has already done their homework， B knows the longest path from B to a sink and I have an edge to B。

One thing I could do is take one step to B and then take the longest path from B to a sync that would be a path that is one longer than the longest path from B to a sing maybe I've got another one that's even longer but。

My longest path is at least one more than be's longest path。

So this is indeed an ordinal potential function and therefore not only。

Does the existence of an orddinal potential function imply the convergence of best response dynamics。

 but the convergence of best response dynamics impliesim the existence of an orddinal potential？

I'll see you guys on Thursday。嗯。

![](img/0cbb14a1f377ae4cc3b09109c5a10c7a_3.png)

It exciting。