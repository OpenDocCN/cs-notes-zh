# 宾夕法尼亚大学《算法博弈论｜NETS 4120_ Algorithmic Game Theory 2023》中英字幕（deepseek-R1 p22 NETS 4120_ Algorithmic Game Theory, Lecture 23-B (Proper Scoring Rules).zh_en -BV15kLRzTExU_p22-

![](img/d0b47a4a8af32a1405742f33f101ab3d_0.png)

嗯。Okay谢谢。Okay。U。So。As we lease it。Go into the last three lectures of this class。I wantna。

Wrap up the sort of auction mechanism design part of the class and jump briefly。Into thinking about。

Information and in particular， like。Increasingly connections between the kind of stuff we've been studying。

 algorithmic game theory and machine learning and。The machine learning aspect of it will become increasingly apparent over this sequence of three lectures。

In this first lecture， I'll just sort of mention connections at the end。

 but we'll be sort of jumping。You know， straightforwardly into information。So okay。

 we've we've spent a lot of time thinking about auctions， which are which are very much about like。

The physical physical world we're like allocating things and we're collecting money and our focus has been on the things that we allocate。

 we want to maximize welfare or on the money we collect like we want to get rich。And。Yeah。

 and so those have been sort of the focus。What I want to ask in this lecture is how we can apply the same kinds of ideas。

 You know， we're still going to want to design mechanisms that are going to。

Elicit somehow truthful reporting of beliefs， but unlike in auction design。

 those you know you know the truthful elicitation of beliefs， you know it's not a means to an end。

 it's not that we want to truthfully illlicit beliefs so that we can allocate goods。

It's the beliefs themselves that we want to elicit and we'll be thinking about sort of correspondingly more complicated settings。

 like not single parameter domains where people might have complicated beliefs and getting them to tell us what those beliefs are。

 that's sort of the whole purpose of our investigation。Okay。

And so the problem I want to think about in this class is。

How should we contract with an expert like you someone who might have substantially more informed beliefs about what's going to happen in the future。

 like you know， who's going to win a presidential election or you know which of two competing video distribution formats is going to become dominant something that。

We will eventually observe the outcome of， but we want to like。Elicit informed beliefs。

Before the outcome is observed。嗯。From someone who you know has better beliefs than us。

 right if we were experts in everything， we wouldn't need to elicit beliefs from other people。

 but you like we were experts in algorithmic game theory。

 not necessarily in politics and so we might not be the people best positioned to estimate the likelihood say that Biden wins the next election。

Okay， so let's just sort of like to fix ideas。To fix ideas。Let's think about， you know。

 like the special case of like betting on an election outcome。

So suppose we want to know the likelihood that candidate A wins the next presidential election。

 which we know to be between candidate A and B。Okay， and just to sort of I'll。

This will be a bit informal， we'll fix the model in a little bit。But like to give you the vague。

 you know outlines of like the setting。Eventually， I'm going to learn who wins the election。

eventually I will learn like A wins the election or B wins the election。At that point， I can。Hey。

 the person whose beliefs I'm trying to elicit today。

So like the general idea is I want to write a contract。Such that。

Some person that I believe to have informed beliefs will tell me their beliefs today。

Then I will observe the outcome that actually occurs later。

 I'll see who won the election at which point the contract will specify some amount of money that I should pay them as a function。

 both of their reported beliefs and of the outcome that actually occurred。

And I'd like to write the contract so that。If the。Person whose beliefs I'm en listing today wants to maximize their expected。

Payment in expectation under their own beliefs then the best thing they can do is to tell me their beliefs correct that's going to be the the setting in broad strokes okay and in general there could be lots of different outcomes but what I want to walk through sort of a little。

Toy example where the outcome space is binary doesn't necessarily have to be。

 But the relevant thing is that I don't know the outcome now。 I want to。

 I want someone to tell me their prediction for what's going to happen now。

 like a probabilistic prediction。 like I think there's a 30% chance that a wins the election。

Eventually I will observe the outcome， not a probability， but like you know， like a won the election。

At which point the payments are made。打开。Okay， so we want to know the likelihood that some candidate A wins the next presidential election between A and B。

We could just introspect。 We could like， think to ourselves， you know， I think it's。

 I think there's like a。20% chance today wins the election， but you know。

 like that wouldn't be very valuable like we do not have especially informed beliefs we are algorithmic game theorists。

 we don't we don't follow politics。And so as it happens。

 we have a friend who's a professional gambler who is also a politics walkk。

 So like this guy has informed beliefs like he's， you know， watching the the nightly news。

 he's following everything。Of course， you know， nobody can tell the future， but like。

We think that this guy's beliefs are probably better than ours。

 and we would like him to tell us what they are。Okay。

 but he's this compulsive gambler and so like despite the fact that he's our friend。

If I just like ask him what his beliefs are gonna be， he's not gonna tell us or he's not gonna。

 you know， tell us sort of the。Sharpest version of them。 In fact。

 maybe it takes him a little bit of effort to to， you know。

 after we ask him the question to really come up with his best estimates and so。

He's basically only willing to do it in exchange for money in what will。Eventually。

 what will amount to a gamble right like what what he says is okay， you know。

 like what's in it for me， you offer me a contract that's going to pay me as a function of what I tell you and what actually happens。

m，You know， and then I'll then I'll do it， I'll play your game'll I'll。Report to you the。

I'll give you the report that I think under my a real beliefs will maximize my expected payment payout okay and the。

The name of the game here is。What that contract should look like。Okay。

 so how can we set up a gamble so that if this guy wants to maximize his payoff， in that case。

 he will tell us his true beliefs。Okay。By the way， like his true beliefs。

 there need not be some like connection between his true beliefs and like the truth。

 it's not even clear whether。You know， it is a coherent。Concept。

 the probability that a wins the election like what is the probability space that that has taken over。

 it's not clear that's a coherent concept。So we don't need there， you know。

 we don't need somehow for this guy to know the truth， we just want him to tell us。

His beliefs and the presumption here is that。When he's computing his expected payoff。

 he will compute that expectation under his beliefs。 That's going to be what's going to allow us to。

Contract to incentivize truthful reporting。Thank。Okay， so let's think about this。

 let's start with maybe some like strawman attempts like what could we possibly do？Right。

 we could start with like the easiest question like。We could say。

 who do you think is going to win the election？And of course he's not going to just give us an answer we have to we have to make it a bet and so you can make it a bet you'll say okay。

 who do you think is going to win the election I will give you a dollar after election night if the person you told me today was correct okay。

 so let's just betting on the on the winner。Okay， so what is our friend going to do in the face of this bet？

Yeah。是。Yeah， he's going to tell us who he thinks it' more likely to win the election right like what should he say to maximize his profits well。

 you know like if。Under his beliefs， he thinks that A is more likely than not to win the election than。

If he tells us A。Then he believes that he has at least a 50% chance of getting a dollar。

 and if he tells us B， he believes he has at most a 50% chance of winning a dollar。

 and so the thing that will maximize his payments under his own beliefs will be to tell us A。

 similarly if he thinks B is more likely than not to win the election， he'll tell us B。诶。Okay。

And so this sort of。You know， this kind of bet does get him to correctly tell us who he believes is more likely to win the election。

 but it didn't elicit all of the information that we wanted。

 we wanted to know like what he thought the probability was that a would win the election and。

This kind of bet。Does not distinguish between。The expert thinking that A has a 51% chance of winning the election and the expert thinking that。

A has a 99% chance of winning the election either way， his best response here would be to bet on a。

Okay， and so this is a fine bet as far as it goes， but it's eliciting something very coarse it's just eliciting from him whether he thinks a is more likely to win or B is more likely to win a single bit what we would like to do is elicit。

😊，More the probability that he thinks a wins the election we'd like to we'd like to be able to like write down a bet a contract。

That in the first case will cause him to tell us， I think there's a 51% chance that he wins the election and in the second case。

Will cause them to tell us I think there's a 99% chance that they win the election。Okay。

 so is the problem clear， like the thing that we're trying to do like this guy has beliefs。

In this simple case where it's just you know， a binary outcome。

 those beliefs can sort of be boiled down to a number。

 what is the probability you think outcome a is going to occur。I'd like to write a contract。

That is allowed to depend。On the outcome， like it's allowed to depend on the winner of the election。

Like I will eventually observe， does A win or does B win， of course， I will not eventually observe。

Anything of the form A had a 59% chance of winning。

That's not even necessarily a coherent probabilistic notion。U。So I only observe the binary outcome。

 but I want to write a contract that will allow me to。Elicit from this expert。

 like the real valued belief。Okay。The general problem makes sense。Yeah。我没师傅在在这点。好这。对。

Let's assume you can model this in different ways， but yeah， in this lecture。

 we're just going to model our friend， the gambling Pols wonk。It's a pure expectation maximizer。

 doesn't care about variance。Yeah。100，000 friends like asked。不费。If they all have the same belief。

 they'll all predict A in this case。Like suppose I in fact， have 100。

000 friends but they're all clones of each other， they all have the same belief。

Right they'll all take this but， if they think there's a 51% chance that A wins。

 it's not that 49% of them are going to say B， that would be a dumb thing to say if you think there's a 51% chance that A wins。

 they would all say A。And so merely。Clonning my friends is not enough to solve this problem as easy as that would be。

That makes sense。Yeah。Like big thousand press clients with high possibilitiesities going from like point。

 basically eilon。So Epsilon and chance that like A。

 so like Epson chance that Es offer them all to your friend just like see。这 the啊。

Like offer a menu of choices and let them take only one of them。

I think most want to each and to see where the boundary is between the one of statement and whats not。

You could imagine trying to do something like that。

 you'd have to think about you know the disctization and whether there are like arbitrage opportunities and how much money this would cause you it cost you to offer all of these bits but but you could imagine going down that road Yeah I mean like this is obviously not the solution and we're going to need a different solution。

Noello。I guess like make a market on。The probability and then like its off his elite and and his expectation sell it。

Like produceuce some kind of like prediction market Yeah。

 we're like rather than like paying him just if he's right。

 it's like he has like stake something so he thinks like E is。Like 70 cents， for example。

 if it's a charging more than 70 cents， then you'll want to sell it。Yeah， yeah。

 you could imagine all sorts of things of different complexity there are prediction markets you'd have to think about how to design them。

The place I'm going to go is we're going to look for sort of a simple solution。

 but a solution that happens to be， we're not going to talk about it。

 but happens to be sort of a core object in the design of prediction markets。Okay。

Its like one thing you might notice here， it's not just that our contract like wasn't good。

 it's like we didn't even ask the right question like I didn't ask him what was the。

Probability that a would win the election， I said， who do you think is going to win the election？

So like this does like a。You know， sanity check like。Like what if we just ask the right question。

 what if I say， okay， look？What do you think is the probability that P will win the election。

 That's the question I intend to ask that's the question I want the answer to。Of course。

 now I need to think about how to pay him right like I like basically I need a payment rule that says as a function of P and the event。

 whether a won the election or not， how much money do you get？ok。😊。

And so you could think about like how we should do this and， you know like。Like probably you want to。

If A wins， probably he should get more money the more confident he was in that right it like if he said there's a 51% chance the A wins and A wins。

 you know， probably we should pay him less than if he said there was like a 99% chance that A wins and A wins。

 you know， like like to the extent that he has more confident knowledge。

 we want to give him some explicit incentive to tell it to us。Okay， probably like if he's。

 if he thinks it's really likely that A wins， he should get more money if A wins compared to it with B wins。

 right， like simple things like this。And so maybe here's like the simplest di versionversion。

Right like。That could say， look， you told me there was a。P% chance that A would win。

I will pay you P dollars if A wins， that's the probability you told me you thought A would win。

And if B wins， I'll pay you 1 minus P。1 minus P is the probability that you thought B would win because here there's only two outcomes。

 right， So I'll just say， look， you know， whatever event actually occurs。

 I will pay you in proportion to。The likelihood that you ascribe to that event。Okay。

 so you get more money。For events that you specified were more likely to occur and the more confident you were in those events。

 you know， the more money you get seems like a you know not a crazy payment role right maybe the first thing you'd think of。

What's are。Politics won gambbleler friend going to do in response to this contract。

even if you think a winning8 has like 51% chance to the report one， Yeah。

 like we we asked the same we asked the right question here。

 but we elicited the same behavior as the last contract。

So what's he going to say to maximize his profits？Well。

 we can sort of go through his thought process， right？Like。

Suppose that our friend believes that A will win with some probability Q， that is his belief。Okay。

And now he's thinking what probability P he should report。

What we would like him to do is report p equals Q。But what's he going to do， you know？He's going to。

Like think about。Under his own beliefs， what is the expected amount of money he is going to make for every report he could？

Present right， so let's call that SPq this is going to be the。

Expected amount of money he makes in expectation over his own beliefs， which is that。

 A wins with probability Q if he reports P。Okay， well。How much money is he going to make， Well。

 if a wins， which he believes happens with probability Q， he makes P dollars。And if B wins。

 which he believes happens with probability 1 minus Q， he makes 1 minus P。ok。😊，So for him。

 Q is a constant， that's his belief， P is a variable that he's optimizing over。Okay， now。

This is like a linear function， right？You know，Q is a constant so。

He's going to get some convex combination of P and1 minus P or sorry's like。You know。

 he's going to get some convex combination of  Q and  one minus Q where the weights of that convex combination are specified by his report。

Right， so he will never have incentive to report something indecisive。

 like 75% chance today wins right like the， you know maximizing。Over some convex combination。

 like it's always going to be maximized at one of the extreme points if he believes that。

Q is bigger than one minus Q， right， the probability that a wins is bigger than the probability that B wins。

 then he can get in expectation。Q dollars by putting 100% of his weight。On the report today will win。

On the other hand， if he believes that B is more likely to win， that one minus Q is bigger than  Q。

 he can get。The most weight by putting 100% of his reporting weight on the event that B wins。Okay。

 so。Like if we offer him this contract， even though we've asked him the right question。

 like the only information he's giving us is going to be who he thinks is more likely to win。

 not the probability they think he thinks they're going to win what he's going to do is he's going to。

Ask himself。Is the probability that A wins more than 50%。 Is it more likely than not that A wins。

 If so， he will report 100% likelihood that A wins。Otherwise， he will report a0%。

Likelihood that A wins 100% that B wins， not that these are sensible probabilities。

 but those are what。Maximize his expected payoff under his own beliefs。Okay， does that make sense？

So like even when we ask the right question like。Figuring out how to。

Right the contract is a little bit tricky。This wasn't a crazy way to write the contract。

 I think it was pretty sensible， probably the first thing many of us would have thought of， but。

It doesn't elicit the information we wanted from it。Does this make sense？Yeah。所以了。明白。Of contracts。

Wちか？不是到我这个情况。对不起不起。You could， yeah， I think that was similar to a previous suggested sort of multiple bet set different odds so you could try to do that。

嗯。😊，We're going to aim to do something simpler and just have like a single contract。You know。

 like like you could try to do that and and there it would be a little messier or there'd be sort of discretization issues and you'd have to worry about what you allow about。

 you know， like are you going to allow them to。Take multiple of these contracts and how do they interact？

嗯。Good。Okay， but is the problem clear and why it's not like immediate the solution？Okay。

So let's now write down a model。Okay， so we've got some future event why， for example。

 who's going to win the election。Okay， so why is at the moment at which we're writing the contract like a random variable。

 like we don't know， but we will eventually observe the outcome of why。

 but we don't know it at the time that we're writing the contract。And。In our example， the， you know。

 why took values in just some binary space like a could win the election or B。 but more generally。

 that's not necessary。 Like why could take。Many different values Okay。

 so you could be betting on some richer outcome space so that's allowed in our model。Okay。

 and we're going to assume that the agent has some beliefs over how the outcome is distributed。

Okay so the agent's beliefs will be represented。As a probability distribution over these。

Fitely many outcomes。Okay， so so again these don't have to correspond in any way to reality these are just the beliefs of the agent what is relevant about these beliefs technically is that when the agent computes expectations about。

What their expected payoffs going to be， they're going to compute those expectations。

Under their own beliefs。Okay， now。We're going to offer some contract， some payment rule。

 which will pay the agent as a function of their reported beliefs and the outcome。Now， just as。

Has been the case throughout our sort of mechanism design portion。

The agent is under no obligation to tell the truth。The agent will report。

Some distribution corresponding to beliefs， let's call it P also a distribution of our outcomes。

 but not necessarily Q， we'd like them to report P equals Q。

 but they could report something else if doing so is advantageous to them。And。After。

They give us their report that sometime later we observe the actual realized outcome。

Like we see who wins the presidential election， for example。Okay。😊，The outcome could be arbitrary。

 doesn't have to be drawn according to the agent's beliefs， for example。Um。But at that point。

We have this contract that will specify what the agent has paid。

the agent will be paid some amount of money， which is a function of their report。

 their reported beliefs， and of the outcome。Okay so so S is this contract is really a mapping from the set of distributions over outcomes。

 these are the agent reports and the realized outcome to like a dollar amount okay。

 so they're paid according to their report and the outcome。😊，And this contract is known。

 so the agent will be deciding what to report based on what this contract is and we'll call this a scoring rule。

 that's what S stands for。Okay， and then here's sort of the meats of the model。

 which sort of ties the thing that we want。ing the truthful reporting of the agent beliefs to the incentive model of the agent。

What the agent is going to do。Is they are going to choose the report that maximizes their expected payoff？

Where the expectation is taken according to their own beliefs right like we're not we're not assuming that their beliefs are correct or or even that it is a。

 you know， philosophically coherent thing to make probabilistic statements about what might be a deterministic world for all we know。

 we're only purporting that the agent has beliefs， which can be expressed as probabilities。

And that when the agent figures out what they should report。They look at their expected。

Reward their expected payment according to these this contract， given。The belief they report。

 that's what they're optimizing over。In expectation when the outcome is sampled from what they believe to be the distribution over outcome。

Okay， so the model for what the agent is going to do is they are going to。

Consider each of the reports they could make。By thinking about what is the expected reward they are going to get from this contract in expectation over their own beliefs。

And then they're going to optimize over that and report whatever。Set of beliefs theirs or not。

 which maximizes their expected reward。Does that make sense？Yeah。

Instead of like trying to incentivize them to P create a function such that even if they report something else。

 there's only one valuation they could have really had to report I mean。

 I guess it's effectively you could I guess more generally。

 you could have asked this question much earlier in the mechanism design portion of this class and said like what why are we like implementing things so that truth telling is a dominant strategy。

 Could't you have implemented things so that。The dominant strategy was something else。

 but that we could figure out what your value was from what you're reporting by like inverting your best response function or something。

And like you could。 But in general， it doesn't help to。

 There's this sort of general notion called the revelation principle， which sort of says， look。

 suppose I had some crazy mechanism。Which implemented， say， in dominant strategies。Something else。嗯。

😊，I am going to。Now describe to you like a mechanism that provides the same outcomes but implements in truth telling that something else here's the mechanism I'll ask you what your value is and then I will play whatever I will play for you。

 whatever was your dominant strategy in the more complicated mechanism I designed given what your value was and now it's a dominant strategy for you to tell me the truth so a similar thing could happen here like if we had some scoring rule。

😊，That somehow made it a dominant strategy for you to report you know some invertible mapping of your beliefs so that we could recover your true beliefs from it。

 we could generically convert it into a similar scoring rule that incentivizes you to tell us your beliefs themselves so it's a good thought。

 but it turns out that kind of thing doesn't help。Get。Other questions？Okay。

So our agent is going to be thinking a lot about like what is there？

Expected payment for reporting P if the outcome is drawn according to Q。And so first I want to。

Give some shorthand notation for that because we're going to be talking about it a lot。Okay。

 so remember the contract。As described takes as input two things， a distribution。

 that's the reported beliefs and then an outcome like we see at the end who won the election。

 we don't see the probability with which they win the election。

So now let me define this shorthand function that takes as input to distribution， P and Q。

What does it mean？SPQ is。The expected payment we will make to the agent if they report the beliefs P。

 but the。States。The thing that we're betting on is actually drawn from distribution Q。

 so this is going to be their expected payment if they believe the outcome is drawn according to Q。

 but they report P。Great， so this is just the thing they're maximizing， it's the expectation。😊。

When the outcome is drawn according to beliefs Q of the payoff of the scoring rule of this contract when。

Beliefs were reported to be P。And just expanding this out。

This is just the sum over all of the possible。Outcomes， all of this possible realizations of the。

True probability of that outcome under belief Q。Times the payment that will be made。

 given that beliefs P were reported and that outcome was realized。Okay， so it's an expectation。

 one thing to note is that this is a linear function of Q。Because how does it rely on Q。

 it's just an expectation over Q and expectations are linear。Right， so this this contract s。

 it could be complicated who knows like how it depends on P and y， but the expected payment。

When the belief is P and the true distribution or sorry when the report is P。

 but the true distribution is Q。Is linear in cube。Yeah。Okay。And so now we can define like。

Our main object of study， which are called proper scoring rules， which are。Exactly those contracts。

That make it under any beliefs the agent might have。

A dominant strategy to truthfully report their beliefs。Okay。So how do we write that in our notation？

Well。Okay， a scoring rule， which again， remember is an object mapping reports。

 distributions over outcomes， cross actual outcomes to money to dollars。Is proper。If。

No matter what your belief is Q。Truthful reporting is a dominant strategy。Okay。

So what that means is that。S for every Q， for every belief you might have Q。

 and for every misreport P that you might consider。SQQ。

 this is your this is what you believe you will be paid in expectation if you truthfully report your beliefs。

 right， where here the forecast is equal to the belief。Is only higher than SPQ。

 what you believe you will be paid according to your true beliefs if you report something else。Okay。

 and if so this is saying it should be a no matter what your beliefs are。Under your beliefs。

 it should be a dominant strategy to tell the truth。ok。And if it is a strictly dominant strategy。

 if this inequality is strict whenever you report anything other than your true beliefs。

 then we'll call this a strictly proper scoring rule。Does this make sense？

And I think it's pretty intuitive。You know， like just as before in writing down a contract and entering into a contract with this agent。

 we are inducing a game in this case a pretty simple game， like a one player game。

And we would like the set of strategies in this game， here it's continuously large。

 it's the set of probability distributions over outcomes that they can report。

We would like that in this game it should be a dominant strategy for them to tell the truth。

 to tell us their true beliefs， and the whole point is we don't know what their true beliefs are。

 so this should be true no matter what their true beliefs are。Okay， they should make more money。

As evaluated under their true beliefs， if they tell the truth and if they do anything else as a result if they're。

Trying to maximize their payment， they should tell us their beliefs。

 this is the property that like our attempt at paying people in sort of proportion to the probability they told us on the actual outcome failed to satisfy there there was something they could do that would make them more money than telling us their true beliefs and even worse it wasn't invertible so we couldn't figure out what their true beliefs were from that。

Okay，'s the。The the。So we've now laid out the model and sort of。The thing we want。

 and it does all make sense， the model in which we are working。Sort of this object we want。

 which is basically just a contract that makes truth telling a dominant strategy。Right here。

Your type here is sort of your beliefs。嗯。The only possible like subtlety here is that。You know。

 like we're not assuming some true underlying distribution when we're taking expectations for the agent。

 it's always under their own beliefs。Everyone on board。Okay。U。

So let's now take a brief aside and just sort of remember convexity。嗯。😊，You know。Okay， yeah。

 like when I was in elementary school right like the question was like。

 you know what's convex and what's concave， like one of them is like this。

 one of them is like this and what I was told and has stuck with me is that the way you remember this is that concave。

😊，Is the one that looks like a cave。Okay， so that one's concrete。So what is a convex set？

So a convex set， we'll get to this one in a second， by the way。A convex set， there's a convex set。

 there's convex sets and there's convex function。So a convex set is any set of points。Such that if I。

Take two points within the set and draw a line between them。

Every point on the line is also contained within the set。Okay。

 so a circle is a convex set if I had some wonky shape。It looked like this。

 this would not be a convex set because， for example。

 if I took these two points and drew the line between them， I would have to step outside of the set。

So convex sets are sets that contain the line connecting any two points within the set。Okay。

 written in notation， you know， these are two dimensional pictures in D dimensions。Once again。

 a set as convex if it contains the line segment connecting any two points， so in other words。

 for any pair of points X and Y in the set。And for any。Wting between zero and1。

 if I take the convex combination of these two points， according to this weighting。

 just the linear interpolation of them that also lies within the set。Okay。

 so that's what convexity is for sets。Now I can also talk about concave functions。

 those are the ones that are not that do not look like caves。Okay， so things like this。

What's a convex function？Well， a convex function， if you like consider the set of points that lie above the function。

Okay， like。The stuff that's above the current。This is some set of points。The function is convex。

 if the set of points that lies above it is convex。Okay， so equivalently。Right， if I take。

Any two points？On the curve。The function defines。And then take the linear interpolation between them。

嗯。All of the points on this line have to lie above the function because the。

Set of points above the function must be convex。So in notation， again， for any pair of points。

 x and Y。And for any weighting that I could use to interpolate between them。

 if I evaluate the function on the corresponding interpolation between the two points。

That always has to be smaller than what I get from the linear interpolation of the function values。

That's the definition of convexity of a。Function， yes。This probably isn't important。

 but I'm just curious， are conducts and concave sets compliments。

 or are there some sets that are like that？Yeah， I guess I don't really know what a concave set is。

Yeah， like I think。Concave functions are just negative one times convex functions。

 the negative convex functions。Okay， so far so good。So there's another way to define convexity。Um。

 or you know， it's a characterization of convexity that you can prove。

 although I will just assert it。嗯。😊，Which is that。If you look at a function like this。

And then you take any point on the function。And you draw its tangent line or， you know。

 like it's gradient。Then。What you'll always find is that。That line lies below the function。

I can do that at any point。If draw the tangent line。

It lies below the function if the function is convex。Okay。So here's like a fact which is， you know。

 like a theorem， you could either define convex functions this way or you could prove that convex functions as we've defined them satisfy this property with a little bit of calculus。

You know， here's the property。Suppose I've got some function， de dimensionsional function。

 and then let's say it's differentiable just so it makes sense to talk about the gradients of this function。

 although that's not actually strictly necessary。Then it's convex， it turns out， if and only if。

 for every pair of points， x and Y。If。I look at some point why。

And then I look at sort of the line that is tangentks。To the curve at that point。

 So I look at F of y plus it sort of。嗯。You know， linear extension that I get by just taking the gradient of the function。

 which in one dimension is just the slope of the tangent line。嗯。😊。

And look at the line with that sort of with that slope with that gradient that。This line。

Always lies below the function value。Okay， so that's just this in pictures that if I take the tangent line。

At any point on this function， the tangent line always lies below the curve。Okay。

 or equivalently for any X and Y。It's always the case that F of x is only bigger than f of y plus the dot product of the gradient with y and x minus y this is just sort of a linear function that is tangent to F at y yeah like this is just the linear function that's tangent to f at y。

Okay。So it makes sense like， you know， if you're not comfortable with like gradients and stuff。

 like I think。It's really a pretty simple idea from pictures， right。

 like if you draw the tangent line， if the functionss convicx， it lies below the function。Yeah。好。

12个不是8。因此啊。Yeah， so like suppose you had。Like a convex function that was not differentiable then you could define something called a sub gradient。

 basically a sub gradient would， you know， like anything that。All of these are sub gradientients。

 basically。Whether。All of the sub gradientients are underneath it， but we won't talk about that。

But but like if there's if you're if you've got like the absolute value function。

 it's not like you can't talk about this stuff。Yeah。Does that makes sense？Okay。

So let's try to build some intuition， maybe by going back to the binary prediction case。ok。😊。

So the nice thing about the binary prediction case is that。Beliefs are one dimensional， right。

 like your。Your distribution over the outcomes can sort of be summarized by like a single number， P。

 what is the probability you think a is going to win the election because your belief for the other outcome。

Thats to be 1 minus P。嗯。Okay。So all right， so remember like we have this expression for。

If your beliefs are Q。If you think there's really a Q probability that A will win the election。

But you report belief P， what is your expected payoff？If A wins。

 which you think happens with probability Q， you get S。

 what the contract tells you you get when A wins the election， if B wins。

 which you think happens with probability 1 minus Q， you get SB。OkayAnd remember。

 this is linear in Q。And let's。Say that F of Q is。SQQ that is。

F of Q represents for someone whose belief is Q。How much money they get in expectation by telling the truth？

Okay， right， like S in general has two arguments， what you report and what you believe。

 but if you tell the truth， they're the same thing。

 and then F of Q is how much someone who tells the truth expects to get as a function of their beliefs。

Okay， so let's make a couple of observations。The first observation， as we already noted a few times。

 is that。the amount of money you expect to get is linear in。Q， it's linear in your beliefs。Okay。

 so like for example。嗯。Let's say that。The X axis here is Q and we are plotting。

The amount of money that you expect to get if you report a 20% chance that a wins the election。Well。

 you know， like I don't know what the slope of that is， it'll depend on。Various things。 but like。

 it's a linear function。 Okay， so it'll look like this。Yeah。Now。If F is proper。

If it's always a dominant strategy for you to tell the truth。Then no matter what your belief is。

Reporting your true belief。F ofq always makes you more money than reporting any other belief。Okay。嗯。

And。Yeah， and so。As a result。What that means is that。F of Q。The amount of money that you make。

By truthfully reporting if you have beliefs Q。Is。The maximum。Overall， P of S of PQ。

This is this is the maximization problem you're solving when deciding what's to report。

 you're going to pick the report that makes you the most money。

This is the expression that tells you how much money you think you're going to make if your beliefs are Q and you report P。

Truth telling the properness property means that F ofq can only be bigger than all of these right there's no misreport that causes you to be able to make more money than telling the truth and definitionly F ofq is equal to S of Q Q we get equality when p equals  Q so F ofq can't be bigger than the max right so F ofq is equal to the max of all of these functions of  Q。

Now， these are all linear functions。 So that means that F。There's you know， for different values of。

P。SFPQ will be a different linear function。So for different values of P。

 there will be different linear functions。 there'll be continuously many of these。But F。

 whatever it is， is just the maximum of all of these linear functions。Okay。嗯。So first of all。

 like the maximum of a bunch of linear functions is convex。you can sort of see that in pictures。

 I guess you could probably with some work draw a neater picture than that。

 but you could sort of convince yourself by drawing pictures。

 drawing a bunch of linear functions and taking the max。

 that the maximum of a bunch of linear functions is convex。嗯。

And but maybe sort of a more algebraic way of sort of verifying it is that。S of Pq。

 this linear function。Is the tangent line of F of Q at p equals Q。Why。

 well it's it's it's linear and it's equal to。S ofq Q by definition。

 it's equal to F ofq at p equals  Q and by properness， it lies entirely below。F ofq right。

 that's the properness condition that。F of Q is only above F of PQ。Yeah，意见。It's a tangent line。Yeah。

 if F is differentiable， it will be the tangent line， but it is a tangent line， but I guess。

 but the point is all of the tangent lines by properness are going to lie below F。

Which is why F is convex。Or you can just try drawing a bunch of linear functions and convincing yourself that the maximum of a bunch of linear functions is convex。

Yeah， I'm just like looking at that picture of the points where。Yeah。

 but that's because I only drew that finitely many lines， so it's piece wise linear but。嗯。Okay。Okay。

Okay， so here's the theorem。We're going to sort of。

Completely characterize the set of proper scoring rules。Okay。

 and it's going to be sort of very closely related to the set of convex functions。

So fix any setting of the sort that we've discussed， so any finite domain。

 let's say the cardinality of the domain is D。A scoring rule， again。

 a mapping from beliefs cross outcomes to dollar amounts。Is proper。If and only if。

We can express this if only if we can express。The expected payments。

That you're going to make as a function of your report and your beliefs。In the following way。

 as a function of some convex function F。Okay， so it's proper if and only if there exists。

 a convex function， a D dimensional convex function。So， that。The agents expected reward。

When they believe Q， but report P。Can be written as F of P。Plus the gradient of FFP。

Dot producted with Q minusP。Okay， like in particular， right。

 this means that if I want to know how much I need to pay you， given a particular reported belief P。

And I realized outcome why。That the payment rule is。You know。

 F of P plus the dot product of the gradient of FF P with what is this， this is the。

Standard basis vector that puts a one。In the coordinate corresponding to the realized outcome and a zero everywhere else。

Minus P or equivalently just the special case of this expression for the distribution that corresponds to outcome y happening with probability one。

ok。嗯。So what this theorem is giving us is basically。A generic way number one。

 to generate proper scoring rules。 There's many proper scoring rules。

 And if I want to come up with a proper scoring rule。

 I can just come up with my favorite convex function and。Write down this contract。

 this is my proper scoring rule。And on the other hand， a way to verify that scoring rules are proper。

 if I can write my scoring rule in this form with respect to some convex function F， it is proper。

 and that is the only way it can be proper。Okay， this is a if and only if characterization。Okay。

 and then finally， just sort of like。An observation。You know。

This convex function will always be just the amount of money that the agent gets in expectation if they have beliefs cue and truthfully report。

Okay， I mean that you can just read off of here if p equals Q， this last term empties out。Right so。

If they truthfully report Q。They get get F ofq dollars。Yeah。

 does the function need to be con from like。All of R D were。

domain you know it only needs to be convex on the reporting domain so on the domain of probability distributions。

 but let's just say it's convex everywhere for to avoid some notal hassle。

 but yeah like you know this function it domain isn't really know the domain is not really sort of all of R to the D it's just probability distributions over y and it's enough that it's convex over that domain。

Okay。Questions。So this sort like a characterization theor， I' it saying？Like。Yeah。

 but like proper scoring rules all have this common form。

 there's many of them of course because there's many convex functions and you can try to look for your favorite one that satisfy。

 you know there's other properties you might want that you can try to optimize for subject to properness again。

 think of properness as like an incentive compatibility constraint。

 but if you are going to do that essentially your opt problem is going to boil down into just optimizing over convex functions F all proper scoring rules are specified by like or characterized by some convex function F。

Does the theorem make sense？Okay。So there's two directions to prove because it's an if only of characterization。

Um。So in the first direction。I want to say， look。You know。

Like like we'll go in the direction first of generating the proper scoring rule you give me a convex function。

 I will produce a scoring rule for you and we will verify that it is proper。Okay。

 so we need to show that if F is convex， then the scoring rule that is defined as in the theorem。

 the payment that is made when you report beliefs P and the outcome y is realized is F of P plus the inner product。

Of the gradient of FFP with the Y standard basis vector minus P is proper。

And so we can start by just sort of like doing some computations like first of all。

 what is the expected payment for。What is the expected payment you get when you make report P and yet you believe the outcomes are drawn from Q？

Well， it's the expectation over outcomes drawn from Q of this expression。

But most of these terms are independent of the randomness and the expectation。

 most of these terms do not depend on why。The only term that depends on。Why is here？

And so we can pull the expectation through to the very end and and just sort of get that the expected payment is is。

Of the expected form， it's F of P plus the gradient of FF P dot product with  Q minus P。Question。

Okay， so this is the payment in general if you report truthfully。Sorry， if you report non truthfully。

 if you report P， not necessarily Q。On the other hand， like if you do report truthfully。

 then what is your expected payment， well， if you report truthfully。Your expected payment is SQq。

 well if  Q equals p， this term zeros out， and so your expected payment is just F ofq。And so。

What is the condition that the scoring rule is proper。

 what is the condition that you're better off reporting truthfully than lying？Well。

 it's just the condition that。The expected amount of money you make if you report truthfully。

 which we just observed was F of Q。Haveth to be bigger。

Then the expected amount of money you make if you lie， which is this expression。

But this is one of our definitions of convexity。Right， this is saying。At any point， Q。F of Q has to。

The above， it's tangentline。Right， this was was this was our sort of。Yeah。

 like our second characterization of convexity， it's exactly this if F is convex。😊。

It satisfies this property， which。Because of how we've written down the scoring rule is exactly the truthfulness condition。

Yeah， the scoring rule has Q within it its like how do you use the I think it was some something how do you use like。

Vers trying list information what Q is when you're So the scoring rule is defined as follows。

 It does not make reference to Q Okay， that's just the the， but this is sort of important， right。

 Like like in this whole model， like how are we like。What is the connection to ground truth。

 what is how are we like getting people to elicit their true beliefs。

 given that we are not assuming that their true beliefs are necessarily correct and so the only external thing we observe which is the realized outcome。

It's not necessarily sampled from their crew relief。 So how could we possibly get them to。

ToTo to tell us their true beliefs well， it's because we're assuming that。

The thing they are maximizing is their expected utility under their own beliefs。

 and so when you take this scoring rule， which doesn't make any reference to Q。

 but then you compute the。Agents expected。Revenue under their own beliefs。

 then you get an expression which which does contain a cube。 That's what's going on。

 Does that make sense。O。Good。😊，Okay， so that was the one direction if we have a convex function。

 we can always turn it into a proper scoring rule。We also want to argue that that's the only way that all proper scoring rules have this form。

So in the reverse direction， what we need to show is that if you give me a proper scoring rule。Then。

There is a convex function such that I can write the proper scoring rule which you initially didn't take this form perhaps in this form right I need to exhibit a convex function F so that I can express your proper scoring rule as F of P plus the gradient of F of P。

Inter product with the。W， standard basis vector minus P。Okay。

 so so what is what function f are we going to choose well。

 the function f we're going to choose is the same one from the other part of the proof。

 it's going to be you know F ofq will be defined to be the expected revenue。

Under belieff Q of truthful reporting。Okay。嗯。Okay， so so remember， we have this expression for。

The expected revenue that our agent will get if they report beliefs P， but they truly have beliefs Q。

Okay， this is a linear function of Q。And because we've been promised that the scoring rule is proper。

We know， oh， sorry， so just a couple of things to note about it。嗯。😊，We've got this function F of Q。

This is a linear function of Q。It is tangent to F of Q。Because by definition。

 when p equals Q it's equal to f ofq， F ofq is just as Qq。And properness tells us that。

This tangent line。Always lies below e。How come well？You know like。

F of Q is the expected profit you would get for truthfully reporting if you had beliefs Q。S of PQ。

 this is the expected profit you'd get for misreporting P if you had beliefs Q。

 and Proness says it's always better to truthfully report。

So properness tells us that this linear function， which is tangent to f at Q。Must lie below F of Q。嗯。

Okay， and so。You know like。Brenny P& Q。One way we can write SFPQ is as follows。

It's a linear function。 and we know the value of the function at one point。 right。

 So like think about this in two dimensions， maybe， you know。

 like we've got our intercept when Q equals P， we know it's equal to F of P。

And then we've got our slope。That's the gradient of F of P。Okay， and so and so this is。

This is the expression for。A linear function tangent to。Tangent to F at point P。

And properness tells us that all of these linear functions lie below F。

 which means that F must be convex。Okay， so that's the other direction。And so I want to now。

Just sort of。Go through。One example， and then maybe wave my hands at some relationship to。

Machine learning。Um。Okay， so like there's many proper loss functions， right。

 there's one for every convex function。But let's maybe just sort of think of。A few one for now。

So I claim that。The loss function。Okay， so so what what did we。

 what did we like try to do at the beginning of the lecture， We were like all right， let's try the。

Scoring rule。That in the event that outcome Y is realized pays you the probability that you reported for outcome Y。

That didn't work。Here's a different one。This scoring rule says in the event that outcome Y is realized what I'm going to pay you is in proportion to the log of the probability you reported for outcome Y。

Okay。I claim this one is proper， This one does incentivize you to tell the truth。So， let's。Right out。

The expected payment you would get if you report distribution P。

But Y is actually sampled from distribution Q？哎。Well。

 that expected payment is equal to this expression。

 the sum overall of the outcomes of the probability of the outcome under Q of to times log of the probability of the outcome under P。

Which。If you've spent time training neural networks， you might。No， under the name of cross entropy。

Okay， this would be or negative of cross entropy， this would be sort of a common thing to maximize as a machine learning objective。

Is it proper， Well， let's check our characterization。嗯。F of Q。Here。

 the expected revenue you get if your beliefs are Q。

 if the outcome is drawn from Q and you report truthfully。嗯。In this case。嗯。😊，Is this expression here。

 which you might recognize as the negative Shannon entropy。

One thing that's relevant about the Shanon entropy is that it's convex。

Okay so F ofq is indeed a convex function。And。We can。

Go through the exercise of trying to write down our scoring rule in terms of our characterization and see if we recover our original scoring rule。

Right， so like we're going to have to think about。The gradient of F FQ。 Well。

 what's the derivative of。F ofq with respect to outcome y well。

You know the derivative of log x is 1 over x。Okay， so like I guess the product rule tells us that the derivative of this term is going to be。

 you know。Log of Q of y plus one。Okay， so we write out our characterization here。Right， it's F of P。

Plus the gradient of FFP。Times the Y standard basis vector minus P。FFP， we know what it is。

It's the negative Shannon entropy。The gradient of FFP。the wife coordinate of the gradient of FFP。

 it's just one plus log of P of y。Okay。And。嗯。😊，You know， similarly here。

And all of the terms cancel and what we're left with is log of P of Y。Okay。

 which is to say we have verified the characterization that。Lolog of P of Y， which we hoped。

 which I asserted was a proper scoring rule。Actually can be expressed。In the form that。

Our characterization claimed that all proper scoring rules could be expressed。And therefore。

 this is indeed a proper scoring rule。Okay。So cross entropy， a common objective in machine learning。

That's a proper scoring rule。嗯。You know， like in linear regression。

 say if you take a sort of introductory statistics course and you learn about linear regression where you're minimizing squared error。

Squared loss where I pay you in proportion。To the square of the。Probability that is realized。

That's also proper。Right， so you might。Have wondered at some point like， you know。

 why is linear regression say？Defined as minimizing squared error。

 why not absolute error or something else why。When we're solving regression problems with neural networks。

 do we minimize cross entropy or sometimes squared error or not something else？

It's not a coincidence。If what you are trying to do is solve a regression problem that will。

Recover for some label you are trying to predict the probability。Distribution on that label。

 conditional on the features。Then。You'd really like that your loss function should be proper。Why。

 well。If it is。Then the unconstrained optimum to the optimization problem that says maximize the score or minimize the negative of the score。

 minimize the loss。Where。The labels。Come from training data that is drawn from some distribution。

 this is like the outcome that is realized according to some distribution。

Will be this minimization problem will be minimized at the true conditional label distribution if your loss is proper。

Because just as you're gambling。Policy wonk friend is trying to maximize his payment like when you unleash gradient desent to try to minimize some loss function。

 like the only thing it's going after is monomon Iically minimizing the loss function。

And so what you'd like is that the loss function should be minimized at the real probabilities。

 not at something else。That is not true of all loss functions， it's for example。

 not true of absolute loss as we saw at the beginning， but it is true for proper loss function。Okay。

 and so this is。An important reason why， for example。

 standard regression problems minimize squared error rather than some other measure of errors。

 an important reason why you see cross entropy showing up as an objectives in multi-class classification。

 it's because these loss functions are proper and so the minimization problem which you are solving is pushing you towards the true conditional label distribution。

 not something else。清楚对对。Dion， absolute awesome。是。So it is well it's not clear that it would have worked。

 but it is true that in our definition of properness and throughout the lecture。

 we have assumed that the agent is just an expectation maximizer so if your agent is not an expectation maximizer if they care about things like the variance of their payment。

 then proper losses are not necessarily going to elicit the truth。嗯。

But that just means things are more complicated， you're going to have to try to design contracts specifically tailored to their risk aversion。

 not that like absolute loss is going to somehow elicit the truth。Other questions？All right。

 and I'll see you guys on Thursday。嗯。

![](img/d0b47a4a8af32a1405742f33f101ab3d_2.png)

嗯。