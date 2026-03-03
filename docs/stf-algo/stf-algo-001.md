# 斯坦福大学《算法博弈论｜Stanford Algorithmic Game Theory CS364A, Fall 2013》中英字幕（deepseek） p01 -01-1_ Introduction and Examples).zh_en -BV1VmC2YzEXJ_p1-

So I want to welcome you to CS364A。This is a course on Al and the game theory。

hich very loosely is a survey of topics on the interface of on the one hand computer science。

 especially though not only theoretical computer science algorithms and economics。

 especially game theory。So the plan for today's lecture is I'm just going to give you sort of a taste of what the course is going to be about。

 The course is loosely organized around three themes。

 and I'll give you an example for each of the three themes。

 And if this is stuff you find interesting and exciting。

 then I hope you'll stick with me for the rest of the quarter。For those of you just coming in。

 there are sign up sheets going around。 So before you leave。

 please put your name on the sign up sheet with your email。All right。

So let me say what the course goal is for each of the three themes of the course， one at a time。

 So the first course goal is a bit of a mouthful， but I'll give you an example。

 So it's about designing systems where you have participants and the participants are both autonomous and strategic。

 they have their own interests， not necessarily the same as yours as a designer。

 And despite their strategic behavior you want the system to function well。

So let me give you an example。Really， frankly， it's more of a non example。

 a sort of cautionary tale of how when you don't take into account strategic behavior。

 things can go wrong。It's a pretty recent example。It's from the Olympics last year。In London。

Like every Olympics， this one had its fair share of scandals。

But one of the scandals was in a sport which is not really known for its scandals。

 not known for you know， failing drug tests and that sort of thing。

Can anyone guess what I might mean。Badmin， specifically， women's doubles badmin。

So let me tell you what happens。So let me tell you how the tournament is designed for how you decide who gets the gold。

 silver and bronze medal in women's doubles Baman in the Olympics in 2012。

The tournament structure is familiar to any of you who follow World Cup。

 although there are only half as many teams。 So there are two phases a round Robin phase。

 followed by a knockout stage。So phase one was the round roin。Specifically。

 there is 16 teams overall， so they were organized into four groups of four teams each groups， A，B。

 C and D。Round Robin just means that whatever group you're in。

 you play the other three teams in your group and you don't play any of the 12 teams in the other groups。

 okay。And the way it works is in each group， the top two teams advance to phase 2 to the knockout tournament。

 So we begin with 16 teams after the round Robbin matches， we have narrowed it down to 8。

This is a good time to come in。So those of you who have taken classes from me before。

Are probably the only ones not shocked with the handwriting quality。

You can always ask me for clarifications and give you a promise right now。

 I will never get upset if you can't read something I read on the board。 Ask me as much as you want。

So from each of the four teams， the top two teams of the group advance。 So those eight teams。

Make it to phase 2。Which is the knockout。Knockout just means you lose once and you're out。

 So you start with eight teams。 Those are the quarterfins。 The four losers are out。

 The other four teams make it to the semis。 Theyre the two losers get knocked out。

 They play the bronze medal game。 And then the two teams that make it to the final play for the gold and the silver。

Now。Let me explain why this is not necessarily a system designed to function well with strategic participants。

My claim is that in this tournament structure。There is a fundamental misalignment。

At least there can be a misalignment。Between。On the one hand， what the participants want。

And on the other hand， what the tournament designer。So a misalignment between the participant goals。

And the designer goals。And when this happens， you have trouble。So what do the participants want？Well。

 that answer is straightforward。Every team wants the best medal that it can get。对。

What does the tournament designers want， First of all， who is that？ So。

 it's basically the Olympic Committee。So what's their objective？Well， in hindsight。

 it looks like they didn't actually think about that question very carefully， frankly。But。

In hindsight。Certainly， what they claim to care about among other things。

 is that every team tries as hard to win every match in which it plays。So let's say want best effort。

From all teams。In all matches。Yes。嗯。They may want that as well。

 Okay so I'm not claiming this is even their primary objective。

But at least certainly something they explicitly stated after the scandal unfolded。 do they want。

 I don't think they thought about in advance， frankly。

 But let's just take on face value what they said afterwards。

 What they said afterwards was not that necessarily the primary objective。

 but certainly it was unacceptable if this criterion was not met。 they stated that explicitly。

Alright， now， if you didn't read about this scandal at the time。You'd be right to scratch your head。

 You'd be right to say， you know， where is the misalignment between these two things。

As a team you want to do as well as possible， the designer wants people to try to win。 You know。

 why would you not try to win。 In other words， how would losing ever help you in this tournament。

For example， consider a knockout tournament。They like phase 2。I mean。

 what what does losing do for you， losings gets you out of the tournament。

 It is obvious in a knockout tournament that you better try as hard to win every match because losing kicks you out immediately。

It's a question。How could losing。Help a team。嗯。And it's sort of subtle， you know。

 but the the teams in the tournament were， were very smart。And so here's what triggered the problem。

What triggered the problem is what， as far as you know， non expert like me can tell。

 is just a truly kind of random fluke event， which was。In group D。

On the last day of round Robbin play。There was a shocking upset。Okay。Namely， the Danish team。

And I'm not going to embarrass myself trying to spell or pronounce these last names。

 So just use initials。The Danish team， PJ。Upset the team that everybody believed was by far the best team in the world。

Team from China。HW。Okay。You mean白 that。By upset， I mean， everybody expected QW to win。And， moreover。

No， but， I mean， my interpretation is that even in light of this upset of this new information。

 again， people believed that they'd play again99 times out of 100。 Q W。 QW would win。

People did not seem to believe that QW was not， in fact， the much better team。

 even in light of this upset。Yeah， so let's right， even though。I'll just write QW much better。

 but of course， what I mean is QW believed to be much better。Just to lend some credence to that。

 let me just state now that at the end of the day， when the tournament finally completed。

 Q W did indeed win the gold medal。 So it seems like this was a justified belief。Now， it turned。

 this is around Robin play。 And remember， two groups。

 two teams from each group make it to the knockout。Now， QW lost this match。

 but they still made it to the knockout tournament As a result of this match， PJ1 group D。

 they were the top team。 QW came in second in group D。 And again。

 both of them therefore receded to the knockout tournament。Okay。

So this happened in the morning on the final day of around Robin play。Now， here was the next match。

And this was。The first of the two controversial matches。There was another Chinese team。X， Y。

That was not thought to be as good as QW。And it was playing the South Korean team。K H。

And they were both 2 and0 in group A play。 So they were both assured of proceeding to the knockout tournament。

 And this match between the two of them would just decide which of them was the group a winner and then which of them。

 the loser of this match would be the second best team in group D。 sorry in group A。

 So knockout was assured。 This was just to determine the seating。And here was the issue。

So here was the fact， just the way the knockout tournamentment was arranged。

 which led these two teams to think carefully about what they wanted to do in this match。

So the winner of group A， that is the winner of this match between X， Y and K H。

In the knockout tournament， would potentially meet this extremely fearsome team。

 QW in the semifinals。 It wouldn't be their first match， but it would be their second match。

 assuming they won and assuming QW won。On the other hand， the second best team in Group A。

 the loser of this match， would not have to face this fearsome team， QW until the final。

And the difference between meeting QW in the semifinals。

 whereupon losing then means a bronze medal is the best case scenario versus meeting them not till the final at which time a silver is assured that difference was apparently viewed by both teams to be such a big difference that both deliberately tried to lose this match。

If you're having trouble envisioning。What it looks like。你在。

When two badminton teams are at the same time trying to lose a match。は。I'm here to tell you。

 I found the match on YouTube。And there's a link to it from the coursese webpage。

So the same thing happened in a second match between the other South Korean team and an Indonesian team。

 for exactly the same reason。Question。So the。So there's a good question here， which is。

 is it relevant that two of the teams involved are Chinese are not， It's a good question。 So let me。

 so I can first tell a story under the assumption that it was irrelevant。

 And I'm not claim that's true。 And I'm claiming it's just a useful thought experiment to proceed through。

To first order from， again， the sort of amateur you know， perspective of myself。

 I thought all teams were reasoning as if QW would just win every match that it played。

 And that was just a given。Okay， the behavior that people exhibited was indistinguishable from that explanation。

 Okay， And if you know you're going to lose to QW， then the your first order optimization problem is to meet Q W as late in the tournament as possible。

 Okay， because that dictates how high you're going to place。Now。

 an interesting twist is that the QW team was Chinese and also one of the teams in the first controversial match。

 X Y was the other Chinese team。 And there is apparently lots of history when you had more than one team from China in the same tournament they work hard to meet each other ideally not at all。

 but if necessary as late as possible。 So obviously in the final， there's no other option。

 So you know， you could ask the question that was it relevant whether they're from China or not。

 It's hard for me to really answer that in an unequivocal way。 I just want to make the point。

The incentives are a problem， even if all of these teams were from different countries。

I think both teams。Couldn't， mean， couldn't。QW have said。X one。Thank you。

2W's next matches in the knockout。Yeah， QW's next matches is the quarterfinals。So。Okay。All right， so。

Again， the results。X， Y， KH。Both try to lose the match。So this is what resulted in derision， scandal。

 and ultimately the disqualification of。The four teams involved in the two controversial matches that I mentioned。

 question。あきも。We the QW lost。的なで。Well， so I think the question is。I mean。

 how does KH view the situation？Throughrow the map。QW never threw any match。I said upset。

 I did not say tank。So the first thing I said was， as far as I can tell。 And actually。

 know just for the record as a very， very diligent instructor， I watched some of that match as well。

 I'll tell you。It was close。And again， it may just be that they were better at throwing the match。

 but I really don't think so。 my belief。Some people actually criticized。

 these four disside teams not for throwing the match， but for doing it so artlessly。Yeah。Anyways， so。

 my belief， you know， I' bet a small amount of money， not a large amount of money。

 It a small amount of money that the Danish win is is actually an upset。

 Its just simply a rare event。 You know， and it does happen。 You know。

 any of us who follow sports know that sometimes they're upsets。 It seems like a legitimate upset。

 Also， again， trying to teach you to think strategically。 supposeose you're the best team。Right。

 sort of I mean， you should just win， right， You rightfully deserve the gold medal。

 You expect to beat anybody you， you meet along the way。 And again。

 the other thing is their match was first。 So there was no way for， you know， if。

 if QW wanted to help out X Y， they probably thought winning was doing them a favor。

 So they probably wanted to win that match， even from Senate's perspective。

We match with the Danish team because some other team in their group。过去。So it's one less I mean。

 again， there's no way I can make unequivocal statements about who meant to do what。

 All I can do is watch the matches。 My belief is that QW did not throw their match。

I don't know what it would mean to prove that。So the point。

Is that when you're designing a system like a tournament or like an auction or like a computer network and you have participants that are strategic。

 the rules of the game matter。 you cannot expect participants to behave in a way other than in their own interest。

 That is an unreasonable assumption of the designer， you must account for strategic behavior。

 if you don't do it carefully。 you will get unexpected and often undesirable consequences。

 And the first， almost 50% of the class will be on principles for system design that properly take into account strategic behavior。

So the rules matter。And the name of the field。Is mechanism design？And again。

 the goal of the mechanism design is exactly what I said。

 Our first course goal was how do you design systems when you have strategic participants so that the end result is something you want。

 Okay， It is a desirable outcome from the designer perspective。So this is， this is a theory course。

 And I'm not going to apologize for it。 Therell be plenty of theorems and proofs， and so on。

That said， we will occasionally look at some detailed case studies and in particular。

 for mechanism design。So where does this stuff get used？So killer apps include Internet search a。

If you want to know how Google made all their money， this is how they do it。 did it， frankly。

 to first order， using auction theory and Internet advertising。If you want to know how it came to be。

 the television stations own so much less of the spectrum and tele companies own so much more to service your wireless devices。

 that's also through carefully crafted spectrum as to reassign that public good。

It's been used for now 60 years to assign medical residents to hospitals， similarly。

 school children to elementary schools， and even to figure out kidney exchange。

 So this is when you have in two pairs of incompatible donors。

 but there are crosscompatbilities so how do you do that taking into account strategic behavior。

 mechanism design gives you tools to answer that question and design appropriate systems。

So this is a well developed field in microeconomics。 And along the way。

 we'll certainly be covering some of the traditional econ approach to mechanism design。

 This is a computer science class， however， And so there will be a consequent emphasis。 First of all。

 on the applications I choose， I'll choose some of the killer applications for the computer science side。

 But even in the theorems that we prove I'll be studying recent contributions about computer science with a focus on robust guarantees and also on computational efficiency to properties that have been largely ignored on the economic side。

Now， sometimes you don't have the luxury。Of designing the rules of a game from scratch。Rather。

 there's a game that's occurring in the wild。 Maybe it's in the Internet。

 Maybe it's in a road network， but it's a system。 It's out there。

 You want to understand it and maybe improve it。And the perspective we're going to focus on for these games in the wild that we want to understand。

Is we're going to want to understand the consequences of strategic behavior。

Maybe it leads to some degradation and system performance。

 but maybe selfish behavior is essentially benign。Again， this will be more clear with an example。

So let me tell you about Grace's paradox。This is a very nice counter counterintuitive example。

 It's been around 6，68。 Amze your friends at your next cocktail party。😊。

So we're gonna have a network。 It can model a lot of things。 But just think about cars on the road。

 That's probably the simplest thing to think about。

So think about this as a flow network for those of you who are familiar with them。

So a bunch of traffic， morning， morning rush hours， say all leaves S at the same time。

 This is thousands of cars。 And these are autonomous drivers。 They can take whatever path they want。

 I've give them a network with only two paths， the upper route and the lower route。So the。

 there are four roads in this network。Two of them are very simple and to understand。

Two of them you should think of as being sort of long highways， lots of lanes。

 They never get congested。At least up till like 2010， I would have counted Highway 2。

80 in this category。So officially， we have a function。

 X is the fraction of traffic that's using this road。 and this is the travel time and hours。

 So this is a constant function。 This says， no matter how congested this road gets that traffic experiences an hour of travel time。

😊，Okay， so the other roads are more interesting。They're more like what you're used to。

 where the more traffic uses a road， the longer it takes any of that traffic to get from the beginning to the end。

So from simplicity， let's just say it's the identity function。So what this means is that 10。

 if 100% of the traffic uses such a road， it takes a full hour。

 If only half of the traffic uses this road， it takes a half an hour and so on。

X is the fraction of the drivers that are using that road。问第三。Everyone starts at us。

Let me write down a little more stuff。Just to make it precise。So lots of cars。Lve S。

For T at same time。Each one can pick either rat that it wants。Now。

 I'm not going to give you any formal definitions today。 We'll have plenty in the weeks to come。

But you all probably have a vague sense of what an equilibrium should be。

 a steady state where nobody wants to move。So what seems like the sensible。

 steady state in this network。 So imagine， you know， these are the same people commuting， you know。

 at 8 AM day after day， you know， from Stanford to San Francisco。

 Where do you expect this to settle down， What do you expect the distribution of the traffic over the two routes to be。

Excellent， at steady state， your intuition should be that they're split 50，50。Why， well， you know。

 neither one is better or worse than the other， right。

 So each one has a combined travel time of one plus x。

 And so if there's more than 50% on one of them， that's gonna be slower than the one that has less than 50%。

 You listen to the traffic report。 You know， on the way to work。 You're like， oh， man， tomorrow。

 I'm gonna take that other route。 It was less， It was less loaded， it was faster。O。

So I'm going to just leave you with this。Hand wavy explanation for today。It's correct， though。

The sensible equilibrium。In this network。Is to have a 50，50 split。

So how long does it take everyone to get to work then。

What's the common commute time that everyone experiences？Hour and a half， right？So commute time。

Three hs。So what you should be saying is M doesn't seem that paradoxical， right， Oh， I forgot to。

 I wrote brace's example。 It's called brace's paradox。

And there's no reason you should be impressed up to this point。But。

I heard about the newest thing coming out of Google X。It's a teleporter。

So we're going to do is we're going put one at V that lets you go instantaneously to W。

 And not only that， it has enough capacity for everybody。Okay。So we change the network。In effects。

 we had this new road， this teleporter going from V to W。Instantaneously。对。Cool。Alright。

 so now we got to say， all right， So you know， what's going change。

 What's the new traffic routing that we expect。So here's the first question。 right， So。

 so consider the very first day that this thing gets installed。 Allright。

 And you're one of these drivers。 And you've been going on the upper route all along。

Are you going to still use the upper root？Yeah， right you want to use this newfangled device。

 not just because it's cool。But because it saves you a half an hour。

 at least if you think of nobody else changing， it saves you a half an hour。 right。

 So currently it's taking you half 30 minutes and then 60 minutes。 But if you switch to the zigzag。

 all of a sudden， it's 30 minutes plus 0 plus 30 minutes。Just an hour。 Okay。

 so you shave 30 minutes off your commute。By using the teleport。Okay。Allright， so the only issue。

 though。Is you know。You're not the only person in the world， right？

You're not the only one who wants to use a teleporter。 Now， maybe you're thinking， yeah。

 but the teleporter can accommodate everybody。 So so what， There's no congestion of the teleporter。

 It's not so simple。Okay。Everybody is going to switch to use the teleporter。

 there's no reason not to。So you'll agree that that gives us this traffic path。

Everybody on the zigzag。Are we better off？What's our commute time now？It takes two hours now。

Everybody takes this congesestable route。 That's an hour。 Teleport is free for everybody。

 but now everybody's stuck on this WT edge， and that also takes an hour， two hours。

But it's not like people were reasoning incorrectly in this network with a teleporter。

 It is a brain dead strategy to use this zigzag path。 You should always do it。

 It's always better than the other two alternatives， no matter what everyone's doing。

 that's called a dominant strategy。Okay， it's a foolproof for you individually to take the zigzag。

But everybody does it。 There's lots of congestion， and it's worse than when you didn't have the teleporter at all。

That's Grace's paradox。So a corollary of brace's paradox。Which is much more intuitive。

Is that selfish behavior by everybody doesn't always give the best thing for everybody。So。

 in this context。Selfish routing。Need not minimize the commute time。Right。

 so with the teleporter installed， if instead of everybody picking routes just by themselves。

 if instead there was some altruistic dictator that could just tell people which routes they absolutely had to take and they had no choice。

You could do better， right， if nothing else， you could just reinvent that 50。

50 split and go back to the 90 minute commute。 And in fact， if you think about it。

 there's actually nothing better you could do。 There's no way to make use of the teleporter in a helpful way。

So in that augmented network， selfish routing gives you a two。

 An altruistic dictator could give you a three hacks。

So you can improve the commute time by 25% with centralized control。

And there's a concept from computer science called the price of anarchy。

Which is exactly this measure。So you look at what's the performance of a system with strategic behavior。

You take as a hypothetical benchmark the best possible system performance。

 even if you could control everybody's actions and you look at the ratio。So in this braces network。

It's two over three/ halves， also known as4 thirds。可。When the price of energyarchy is one。

 that's the very happy situation where strategic behavior gives you exactly what you wanted anyways。

The closer the price of anarchy is to one， the more robust your system is to strategic behavior。

 the more essentially benign selfish behavior is in that system。So from an engineering perspective。

 then， the well motivatedtiv question is， well， okay， we certainly want to understand， you know。

 when is the price of anarchy equal to1， That's the best case scenario。

 But it turns out this theory has much wider reach。

 When you study which application domains and what conditions allow you to guarantee the price of anarchy is close to one。

 say something like four thirdds。So the goal of the weeks of the class， which we study this concept。

Will be for what applications。And with which conditions。Is the price of anarchy close to one。

And believe it or not， despite the fact that people have been thinking about equilibria for decades。

 if not centuries， and certainly we've known about the inefficiency of things like Nlibria forever since well before I was born。

 it wasn't until computer science got interested in this that they proposed the price of anarchy and started proving theorems about it。

 The people really started quantifying the inefficiency of equilibria。 That's a contribution。

 It turns out from the computer science world。 So I'm going to talk about that for a few weeks。

 sort of in the middle of the class。So killer applications， I will talk about network routing。

Scheduling problems。It has applications for simple auction formats。And why they do well。

 even in complex situations。And so on。For example， one thing we'll learn is that a modest amount of over provisionvisioning of network capacity。

 So for example， just keeping a telecommunication network at a max link utilization of 90%。

 that is a condition that's already strong enough to guarantee that the price of anarchy is close to one。

 and so we'll give the rigorous theorems establishing that later on in the course。我要。

situationsituations when strategic agents aren't so shortsed。They were game here。

reasonablea is I just。No， so I mean。I mean， I have to say， I mean， embrace this paradox。 I mean。

 it's not。 I mean， this is a real phenomenon so。Time in哪。Selfish agents。See the consequences of， oh。

 I do this network。Then we down the guy。It's not going to， I mean。So， I mean， there is some you know。

 you can talk。 I mean， you're basically saying， you know， how can you have some kind of collusion。

 either explicit or implicit。And you do see that coming up， for example。

 when you study repeated games， you get sort of a much richer set of equilibriumria。

 which can include。 So I mean， one of the most common places people study this is the prisoner's dilemma。

 which is really the distillation of the problem that's going on here。

 And especially when you look at an iterated version of the prisoners's dilemma the dominant strategy becomes more and more absurd。

 So then it's well motivated to ask， what's a better behavioral model that explains what you see in real life。

Honestly， know， there's been experiments with brace's paradox like issues in real life。

 This is what happens。 So I would argue here， we don't need a better behavioral model。 Simplistic。

 though， that it is。 it's very predictive。 That said， in other applications。

 it is a relevant question。 I don't think we're going wind up seeing it in the course， though。

 But it's a good question。Yeah。So。No， you can't do better than optimal。

So we've sort of concocted it so that it can't be better than one。

 So we've put on the bottom the best thing that could happen。

 even if we had full control over the system。So just by definition， it has to be at least one。Yeah。

Yeah， it wouldn't make sense。So I mean， you can't do better than optimal， so。一。Okay。

 so the question was about dominant strategies and do we assume， you know。

 what is our behavioral model And pretty much in this class， we're always。

 so we want to do analysis of systems with strategic participants。 And to do that。

 we need some kind of behavioral model。 We need to have some model about what people actually do when faced with some。

 you know， decision to make。And we will always， at the very least。

 assume that if players have an obvious dominant strategy， then they will take it。In fact。

 they'll be taught。 So a focus of this course， which， again， sort of differentiates。

For to a large extent， the computer science approach versus a more traditional approach is trying to push toward weaker and weaker behavioral models。

 making as few assumptions as possible。 So at times in the course。

 I will make assumptions like we're gonna to assume players play a national equilibrium under that assumption the following things are true。

 but。You know， also， there'll be a big push in the course to weaken up the assumptions significantly。

 And it's hard to get much weaker than assuming that when you have a dominant strategy。

 which again means it's always the best thing for you。 It doesn't matter what everyone else is doing。

 That's what dominant strategy is。 It's hard to get a weaker model than assuming that when that strategy exists。

 people will play it。 That'll be sort of our best case scenario。

 as far as how weak the behavioral model will ever get。So I think I have time for a quick aside。

So a little over 20 years ago。Conan Horowitz wrote just a two page observation in nature。

Very cute observation， which points out that braces paradox。 It's not really about traffic networks。

 It's really something much more fundamental。 you don't need traffic。

They propose the following physical experiments。Involving strings。And springs。

So you take some fixed base， something like this。Okay。And from it， from below。You attach a spring。

To the bottom of that spring， you attach a very short string。That's a string right there。Then。

 another spring。And at the bottom。You have a heavy weight。OK。

And so when you hang this weight from below， of course， it stretches out both of the springs。

 and it pulls that little tiny string top。I am also going to attach twoth strings that at the moment。

 seem superfluous。The first one。From the top of the top spring。To the top of the bottom spring。

The second one from the bottom of the top spring down to the weights。So they're gonna to be。

 you know， just long enough。 So they have a tiny bit of slack。But。Here's what's interesting。

Suppose now I take a pair of scissors。And I go up to that little ta string in the middle。And I go。

 snip， I cut it。This contraption will reposition itself， somehow。And the weight。

Three things could happen。Could stay in the same place。Could go up。Good out。

So who thinks it stays in the same place， the weight when I cut the string。Who thinks it goes up？

It think it goes down。Right right。Properly implemented。

The weight actually levitates off of the ground。Despite the fact。

 it seems like you made this system weaker。There's two arguments you can use。To see why that's true。

 one is a reduction， One is direct。 The reduction is to the traffic network we just saw。

The same equations that govern the physical position of these systems and strings and springs are those that govern the traffic equilibrium in these networks。

The analogy is force through the strings and springs corresponds to traffic flow through the traffic network。

Travel time on the right corresponds to distance on the left。

Cutting that ta string corresponds to removing。The teleporter from Ba Paradox recovering the superior equilibrium with 25% less commuteton。

 In principle， you can build this contraption so that this levitates to mere 75% of its previous base to weight distance。

This is not just a theoretical exercise。 Last time I taught this class。

 I offered extra credit for students who would build a demonstration and upload it to YouTube。

At least three students did it， maybe more。 but I found three。

 you can find links from the course web page。So it can be done。 No one has reached 25% decrease。

 but I think someone got 10% or so。So have a look if you think you can improve on last year's submissions on any dimension that you see fit be it either。

 you know， production， dramatic content。How far up it goes， Any of those things。 Again。

 there's a extra credit redeemable by the end of the class， if you like。So it embraces paradox。

 not just about traffic networks。So， let me tell you about the。Third， biggest theme of the class。

Which we will be talking about just for the final few weeks。

And it's gonna be the most computer scienceency part of this algorithmic game theory class。

We're going to see what we can say about a very fundamental question。Equilibria。

 we always talk about them。 We analyze them。How do we get there。Do we get there。

 Our systems at equilibrium。Right， some games are easy to play。

We talked about brace's paradox with the teleporter。

 We talked how using the teleporter is a dominant strategy。 There's no reason not to do it。

 That game is easy to play。 Some games are not so easy to play。 If you come on Wednesday。

 we'll talk a little bit about first price auctions and you'll see just how hard some games are to play。

Given that， how do in possibly complex games， players reach an equilibrium。Even more fundamentally。

 do they even reach。And equilibrium。And what can complexity theory。

 computational complexity theory tell us about this fundamental question。Okay。

So let me talk a little bit about equilibrium。 Again。

 I don't want to be too formal with the definitions now。

 I'm sure you all have a vague sense of what it means。

 It's just a system or a game as an equilibrium。 If， you know， for each participant。

 if everyone else keeps doing what they do， I'm gonna keep doing what I do。Now。Some games。

 it's actually a little tricky to define equilibriumria。 So hopefully。

 most of you know the game rock paper scissors， okay。But maybe just to remind you who's up for a few。

 a few rounds。Anybody who wants to break your as Rock， Okay， ready。1，2，3。1，2，3，1，2，3， okay。

Justent any of those tournaments fan。Or you're seeing that， you know about rock paper tournaments？

You know， I think it's like pool， you know， where it's like。

 you get these people and then they claim like they just are better the more they drink， you know。

 But really， they just are less aware of how badly they're losing the more they drink。

I love betting those people。Okay， so to remind you， so rock your possesssors， three strategies。

 two players， and one person wins。 one person loses。

So that's easy to encode in what's called B matrix game format。 right。

 So let me put it up on the board for you。So when there's two players， you just call one。

 the row player， you call the other one， a column player。In rockock paper scissors。

 So in our first two rounds， we tied。 and when you tie， you both get zero payoff。

 And then there's the cases where one beats the other。 right， So paper beats rock。

 So the first number is the row players payoff。 The second one is the column players payoff。

 scissors beats rock。 And， you know， the deal。Okay。So， in general。In a by matrix game， you have rows。

 you have columns。 Each matrix entry has a pair of numbers。

 The first number is the row players pay off。 If that's the outcome。

 the other number is the column players pay off okay。Now。

 what's pretty clear in Rock Haper's scissors is there's no deterministic equilibrium。Right。

 so if we each pick a single action。At least one of us would want to change。

 assuming they stayed the same thing， right， If we both pick rock， actually。

 both of us want to change， assuming the other one does not。 We want to change to paper。

 If we play different things than whoever's the loser wants to switch to the action that would beat the other player。

 okay so。Defining deterministic liberal， you could try to do it。

 but you're not going to get any in this game。So it's really important in Nash equilibrium。

By the way， I hope no one here thinks they know what an natural equilibrium is because they watched a movie a beautiful mind。

Are you all like too young to have seen that movie， It's getting old now。

 who's seen a beautiful mind。Okay。On the first exercise set。

 there'll be a question asking to explain why they do not correctly explain the Ash equilibrium in that movie。

All right。So a really key idea， then， in defining Nash equilibriumria is allowing randomization。

 Okay， which actually makes sense。 right， if you're playing rock paper scissors against somebody else。

 to me， my opponent looks randomized。 I'm just trying to guess kind of which is the most likely action they're going to play next。

So in Nalibria， you allow players to。 It's called mixing， mix strategies or randomized strategies。

And in rock paper， scissors。There is an equilibrium if you allow randomization，So each player。

Randomizes uniformly。Then， I claim。You get。A Nsh equilibrium。

And then sometimes people say mixed just to emphasize that you can randomize。

So what do I mean by this？If I'm picking a row uniformly a random and my opponent's picking a column uniformly a random。

 what you should check is that my expected payoff is 0。Okay， that's an easy computation。

 You don't see it in real time。 It trust me， it's an easy computation。 And actually。

 no matter what I switch to， if my opponent just keeps randomizing uniformly。

 doesn't matter what I do。 I'm gonna get expected payoff 0， no matter what I do。So in this sense。

 if they keep doing what they're doing， I may as well keep doing what I'm doing。 And that sense。

 it's an equilibrium。 In fact， as I'll ask you to verify on the exercise set。

 it's a unique equilibrium in the Rock Pa scissors game。全ち的に。Randomizes。不是。Other randomization。

That's a good question。在通了。I look， I look forward。 I look forward to seeing your research report on the topic。

Firsthand experiments， of course。Well， then you can be like the no hypothesis。All right。So， you know。

 all right。 So this， okay， So rock paperper scissors has an equilibrium in that sense， right。

 that's pretty limited， right， So this is not why Nash got the Nobel Prize。

 He got it because he showed， actually， forget about rock paper scissors every game。Every game。

Not just rock paper scissors has a ash equilibrium。Might have many。

 but it's definitely going to have one。看。I'm just going to state a special case here。

Every by matrix game。Meaning a game of this form with any numbers at all。Has a ash equilibrium。

In fact， Nash's theorem applies with any finite number of players。 doesn't have to be two players。走。

No。But， you know， basically， everyone plays a mixed strategy and holding everyone else fixed。

 If you do anything else， your expected payoff can only go down。

So if everyone else keeps doing what they're doing， you want to keep doing what you're doing。O。Right。

 but we're gonna to be our scientists， right Give us something we can use。

Don't just tell me that it's there。Tell me how to find it。嗯。So there's more good news。Which will。

 you know I'll give you the proofs for this in due course。Which is for zero， sum games。

So that's like here， But notice in every single matrix entry， the two numbers sum to 0。

In zero sum games， not only is there natural equilibrium， but we can find one efficiently。

 meaning in polynomial time。So one way to do this is linear programming。

That's relatively heavy machinery。 If you're really to compute something which is almost an equilibrium。

 then， in fact， very simple iterative learning strategies can be used to compute an approximate N equilibrium。

 And that's very suggestive that this is a sort of meaningful equilibrium concept。

 Not only is it out there， but if players learn in a natural way over time。

 they'll actually be able to compute it on their own。 And again， you know， details in due course。

So Na theem is 51。 This has been known for a long time， decades and decades。

But a relatively recent and just quintessentially computer science contribution to this line of work is a negative result。

Saying that in general， if it's not zero sum， then。Under suitable complexity。

 theoreticalore assumptions， in fact， there is no efficient algorithm for computing a national equilibrium。

 Such an algorithm does not exist。So this is just from 2006。Cannot compute one。In poly time。

In general。Now， as usual， whenever some computer scientist says something about some algorithm not existing。

 know， unless you're talking about the halting problem or undedeciability or something like that。

 usually what they mean is under some complexity assumption， algorithms don't exist。

 right So like an NP complete problem， often will in a cavalier manner。

 say there's no polytime algorithm。 Of course， we mean assuming P not equal to NP。

 there's no poly time algorithm。 So this situation here is similar， although interestingly。

 this theorem is not NP complete。 or let me phrase it as more of a mindbe to make it actually true。

 this problem is not NP complete unless NP equals co N。So it's unlikely to be NP complete。

 but it's also unlikely to be N。 Okay， And there are rigorous statements of all of those。

 We're not going go through all the proofs。 The proofs get pretty hairy。

 but I'll give you the vocabulary so that you're totally literate in what the formal statements are and what they meet。

Okay， so it's not N hard。There's a different， really until recently。

 very obscure complexity class called P A D。Which has been resurrected by this national equilibrium computation problem。

 because P P A D turns out to be the complexity class。 It was sort of defined to be， you know。

 the one for which this is complete。And again， I will demystify all of this in the last couple weeks of the class。

 but here's the point。Here's why this is interesting。 Here's why you should care。Two reasons。So what？

Well， so first of all， and this is just really for the hardcore computer scientists among you。

 on a technical level， this means that Nash equilibrium has furnished us with something very rare。

A natural computational problem。Intermediate to P and NP P complete。 And in your studies albeit。

 you've seen very， very few problems of that type。 right， You take your 100 level classes。

 even your 2 and 300 level classes， everything inside the class。

 N P seems to fall neatly into one of these two classes。 P and N P complete。

Who knows if some things conjectured to be in the middle。Anyone。

Sort of two quite famous examples other than this。Factoring， good， Any others。

Graphify somemorphism is another one you might have heard about。The point is。

 computing Nash equilibriumlibria， the most fundamental concept in game theory furnishes a third。

 And it is this result that establishes this fact， proving it P P80 hard says there's unlikely to be any polynomial time algorithm。

So that's pretty cool。So intermediate to P and NP， it seems。But， you know， on a conceptual level。

 it really suggests that we take a closer look at the notion of Nash equilibrium as a predictor for human behavior。

 at least in all game theoretic scenarios。Most of us don't believe that， you know。

 humans can do computation systematically faster than Turing machines。

 so if there's no polynomial time algorithm for solving a problem in general， in the worst case。

 many of us don't foresee human behavior solving that same problem， say within our lifetime。

So if computers cannot find naturalria in general， in the worst case。

Perhaps strategic participants can't， either。So this casts doubt on using the National equilibrium as a universal predictor of the outcome of strategic behavior because of an intractability critique。

Now there are， of course many， many complaints that people have had about NA Elibria ever since they were defined starting with the fact that they're not unique。

 so this is by no means the first， not even necessarily the most important critique of NA Eria。

 but it's an important one and it's one that computer science is uniquely situated to make。

 and that's why I want to highlight this negative result in that final section of the course。Okay。

So that concludes what I wanted to say by way of introduction。

 I wanted to wrap up by just telling you a little bit about expectations。

 how the course is going to work and taking any questions you might have。So what do I want from you？

So you can take this course in three different ways。 I welcome auditors， and then， of course。

 I expect nothing。 Show up when you feel like it or not。

I did that with many courses in my student time， even as a professor， I do that sometimes。

You can take it past fail， and you can take it for a letter。There'll be two types of assignments。

 There'll be what I call exercise sets。They will be weekly。 They'll go out every Wednesday。

 They'll go out the following Wednesday。My goal for the exercise sets is modest in any gra course like this one。

 I think the most important thing to do is spend some time afterwards。

 going back through the notes slowly to make sure you understand it。

 This is the kind of class where perhaps， depending on what kind of undergraate you were。

 you may have a experience with following classes in real time。

 even in depth that's very difficult to do with advanced classes like this。

 So it's really key you reinforce lecture material afterwards。

 The exercise sets are literally just a mechanism for me to force you to do that。😊。

They are going to be working out examples， filling in proofs that I skip in class and so on。

 They are not meant to be， especially time consuming。They will be weekly， however。

They'll be graded just on a plus check minus kind of system。

If you do all of the exercise sets that's already going be good enough for a B。

 And particularly if you take the class pass fail， that's all you need。 That's all you got to do。

So what's the rest of the work。 There's going to be biweekly problem sets。

 These will be more difficult。 They're meant not to reinforce the lecture material。

 but to actually extend it。 That is， I intend to teach you some new things relevant to the course of course for new things through these problem sets。

 Probably they'll have the format where you choose K out of n problems。

 So maybe I'll give you six problems。 I want you to do three。

They're also meant to be solved collaboratively。 So that's not mandated。

 but that's strongly encouraged。 So you can form groups of up to three to work on the problem sets。

 And we're only going to accept a single write up from each group。

 So there'll be five of those overall。 The fifth one will just go ahead and call it a take home final。

 Why not。So those are the expectations I have for you。 The floor is open for questions。

 either on the lecture content or on the course mechanics。Ohpe boy in the back。There is of course。

 website， the easiest way to find it right now is probably just go to my website。

And there's a link toward the top of my homepage。And definitely keep an eye on the course So I will be posting readings for each lecture on the website。

 This reminds me of a couple other things。 The lectures are being videotaped。

 that's really just you know there are' a lot of courses like this one。

 And so I just wanted to kind there's nothing fancy that religion just plop me a camcorder in the back pointed at the blackboard。

 and to make sure people aren't at Stanford can watch these lectures if they want。

 but obviously a side effect， know if you happen to miss a class。

 then you're obviously welcome to watch that later。

 hopefully they'll be posted just within a few days of the actual lecture itself。

 I'm also hoping to generate lecture notes though that's less of a promise。

 that's more of just a goal。 the videos will actually appear course notes I've written them for this lecture。

 know as time permits I'll post them as well to the website。

 So keep an eye on the website for those extra materials and the readings。Yeah。

 they'll go on Wednesday。 It'll go in two days。有。Oh， right， so。I mean， on some level。

I don't care what your background is， but to be useful。

 let me kind of tell you who my kind of archetypal student is that I'm talking to。So。

 you know what so when I prepare the lectures and I think about what level to explain things that I sort of have in mind。

 you know， a master's student。Maybe a first year PhD student。

 not necessarily with a theory concentration， but certainly someone who didn't hate theory， you know。

 and sort of， you know， enjoyed their theory classes as undergrad as much as any of the other ones。

I'm not so I， you know， I will assume basic undergrad CS， S theory。

 meaning algorithms and MP completeness， not much beyond that。

 not assuming anything in economics or game theory。 Conversely。

 this class certainly won't substitute for a proper course in game theory or microeconomics will'll learn it only on a need to know basis。

 So we'll only get sort of small pieces of those traditional fields。Correct。Oh， yeah。

 So my office hours will be after class。So you know。

 I'll start by just hanging out around here after lecture。

 and then I'll make my way over to my office in Gates 4，62。 Those will go till 4。

30 on Monday Wednesday。 This is also up on the web page， by the way。 Oh。

 and then I should introduce the Ts。 So you can stand up， guys。All right。

 so on the left is Oka and his office hours， when are they？Tuesday。Tuesday 1 to4。2。24 a。

 And then Castis is on the right and the black shirt。 and he' Thursday is9 to noon。

 Also in Gates B 24 a。 I will have office hours this week。 They will not。 Okay。

 so there is start next week。 Min start today。And that's all on the website。Other questions。Oh yeah。

 How are using piazza。We are， so there's a piazza website。

There's a link to it from the course homepage。And to be honest。

 I will be looking at it not every day， so certainly when it's important that I respond to something on it。

 I will do so， but the TAs will be monitoring it relatively closely。

 so in addition to the office hours， Piaz is a great way to clarify lecturer homework issues。Thanks。

对二。Well， you know， I want to see， potentially， So ask the question again。

 So who here this would be good A B testing I should have counted before the lecture and after the lecture。

 What a great way to kind of evaluate the quality of your first lecture， so。😊，Who， who is at least。

 you know，95% sure that they're going to attend most of the lectures in this class。O。

 who is less than 95% sure they're going to attend most of the lectures in the rest of this class。

Yeah， I'm gonna， I'm gonna wait a lecture or two before deciding on the room。 to be honest。

 I've already done some ground work and it's bleak with the room。So。Yeah。

So I'm hoping we kind of fit。But， I mean， if it's really， you know， if it stays at this size。

 I'll have to， I'll have to find something else to do。 But if we drop， say， 10 people from this。

I think maybe it's vaguely tolerable。it's easier for me。 I'm at the front， right， with all the space。

 but。So keep， keep， I mean， if you， let me put it this way。 If you're uncomfortable with the room。

 please ask me again。 Okay， the jury is out。 That's， that's the answer with the room。

 Other questions， yep。So the first exercise set will go out Wednesday。

And it'll be due a week from Wednesday。 And that will have some of these know questions about just from lecture。

 So like today， I'll ask you to， you know， there are a couple of things I mentioned in the course of class。

 So like prove that the unique equilibrium of rock paper scissors is randomizing uniformly。

 So just basic stuff filling in the holes。 And then the first problem set will also go out Wednesday。

 probably I'll give you about two and a half weeks to do the problem sets。 So that'll be for a while。

Okay， so I'll stick around after class for more people who have further questions。

 but that's it for today。 Hopefully see you Wednesday。

