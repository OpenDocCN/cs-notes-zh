# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p11 -11-Lecture 11_ Online Learning and the Multiplicative Weights Algorithm).zh_en -BV14CAUeUEPj_p11-

Okay， so the plan for this week is it's going to be sort of a segue between the second module of the course on linear programming and the third module out a four of the course on online algorithms。

 so we are going to start talking about our first online problem， our first online algorithm today。

 we're going to cover a famous algorithm called the Multipl of weights update method but then also show I'll show that there are consequences for our last couple of topics。

 linear programming and the Max theorem that are derived from the multiative weights algorithm so we're going to both introduce some new concepts but also reinforce the things we talked about last week。

All right， so what do I mean by an online problem？Well， this term was invented in the '80s。

 so it sounds a little anachronistic at this point。

 has nothing to do with the internet or with social networks， anything like that。

What an algorithms person means by online is that the input to the problem arrives piecemeal one at a time in some sense。

So the input arrives one by one。Now what this means sort of depends on the problem right。

 but so for example， if you're scheduling jobs on machines。

 you could imagine that the jobs arrive online， meaning one by one。

 or maybe you're solving some graph problem and you get a new vertex of the graph at each time step。

And what makes it hard is that your algorithm has to make some kind of arevocable decision at each time step。

So algorithm。Makes a revvocable decision。Each time step。Okay。

 so maybe you have to decide which machine the new job goes on。

 maybe you need to decide whether or not to match the new vertex that just showed up this kind of thing。

And， you know， if you think about it for a second， you realize actually like a lot of problems in real life。

 both computational and otherwise， really are online problems。

 So it doesn't really get any airtime in CS161。 But if you think about it。

 the kinds of problems you might design algorithms for in the future。

 likely some of them will be online problems。So that's what we're going to talk about in for a couple weeks。

And the subject of today。It is a very simple model of making decisions online。

So this is a model that was actually first studied in the 50s in game theory。

 but it's been rediscovered many times in particular in machine learning theory。

 they also have sort of independently studied this model。And you know so this problem。

 I think it's interesting in its own right， but as we'll see there's also implications for both linear programs and for the miniax theorem。

So what's the setup？So there's a set of actions。 that's just fixed and we know what they are。

In today's lecture， N will denote the number of actions。

 and this problem is already interesting if n equals 2， that's still a non trivial case。

So what might this mean this can me a lot of things， but for example。

 maybe every action is a stock you're trying to choose how to invest？

Or maybe you you're trying to figure out how to get to class from home。

 and there's different routes you could take， so the different actions could be the different routes。

Okay。So that's the first thing。So what's the online aspect？There's going to be a reward vectors。

R1 up to R capital T。不起。So each reward vector。Specifies for each action at a given time step T。

 the payoff that you will gain from picking that action at that particular day。

And so these rewards can be positive or negative， we can scale with all of generality for our purposes。

 so they're between minus1 and1。So these arrive online。Meaning what at a time in a sequence？

Every time you have to make some decision and what makes it really tricky。Is that a time T。

The algorithm has to choose in action。Yeah。To play on day T A。Knowing。

Only the reward vectors that have shown up in the past。So knowing only。R1。Up to Rt minus1。Okay。

So when you have to pick an action at day T， you don't actually know what the reward of every action is。

 Of course， if you knew all the rewards upfront， you just pick the action with the highest reward。

 but if you don't know， what the rewards are going to be， it's really not clear what to do。Okay。

And should， I should say， when I say chooses。Randomizations allowed。And actually， as we'll see。

 randomization is necessary for good guarantees in this problem。

 it's sort of important that you hedge your bets given that you don't know what the rewards of different things are going to be。

So that's a setup。So each day you choose an action from A。

 you know the reward vector is from the previous time steps。

 but what really governs your reward is what is the reward unknown reward vector for right now for day T。

And if you think about this a little bit。It seem kind of unfair。Right。I mean。

 you know this algorithm， in effect， you have to make this action and you know absolutely nothing about the rewards of the different actions。

 so you have no clue what the consequences of the different actions are， and somehow you got to pick。

So it's， you know， if you could get any kind of nontrivial guarantee in this area。

 very unfair fair setting， one should be pleased。 On the other hand， you should also be thinking。

 okay， well， you know， is anything nontrivial even possible。

 Maybe you're just sort of always they'll be reward whatever however smart your algorithm is。

 there'll be instances where you do terribly。 So that's the next thing I want to talk about。

 What kind of guarantee should we be shooting for。With this unfair setup to the problem。

So I'm going to show you some limitations on what we could possibly expect。

 but then I'm going to give you an algorithm which actually given these limitations is as good as could possibly be。

So what are the limitations。 So first of all， well， you know。

 how would you try to convince somebody that your algorithm was really good Okay that you did a great job of sort of choosing actions over time。

Well， probably the most compelling statement you could make would be to say， well， you know。

 suppose it was the case that even if I were omniscient and I knew all these reward vectors up front。

 I couldn't have done much better than how my algorithm actually did。 So my algorithm。

 even though it didn't know the reward vector at the current time step。

 was almost as good as if I had clearair voyance。 and I knew what it was going to be。

So that would be the strongest imaginable guarantee。 and it's too strong。 Okay。

 so that's too strong a benchmark in this。In this setup。

So the first thing you might want to try to do， you can't do， can't compete。With okay。

 so if you were omniscient and you knew everything up front， what would be your reward？Well。

 on each day， from1 to capital T， you would just pick。

The action that at dayT gives you the largest reward。Okay。So degree， so in hindsight or with forknow。

 this would be the total reward that the obvious algorithm would get。Okay。

And it would be nice if we could come up with an algorithm。That's online and does almost as well。

 so why can't we do that？Well。Pick your favorite algorithm or even just suppose there's two actions。

 okay？So pick your favorite algorithm， It can be randomized。 And now， you know。

 I'm going to play the role of an adversary， and I'm going to look at the code of your algorithm。

 and I'm going to feed you kind of really nefarious reward vectors。How would I do that， Well。

 I know the code of your algorithm， So I just look， okay， it's day 17。

 I know what happened in the last 16 days。 What is your probability distribution over the two actions on day 17。

And if it say 60 on the first action and 40 on the second action， I'll just give you a reward vector。

 which is minus1 on action 1 and one on action 2。So every day， whatever you're more likely to play。

 I'll feed your reward vector where you get minus one then。

But if you sort of get lucky and choose the action that you're less likely to pick。

 then you get a plus one。So with an adversary like that， which always feeds in a vector。

 which is either plus 1 minus1 or minus1 plus1。What is this number？Tee。Right。Each day， little T。

 there are two actions。1 has reward plus1，1 has reward -1。 So the max is certainly plus1。

 summed over capital T days。 Okay， so in hindsight， however， the adversary did this。

 as long as it only did plus -1 vectors， you can get T in hindsight。So the adversary can ensure。

That this notion of opt。Equals capital T。Well， what does our algorithm get Well。

 the best case for us is that we were picking an action 50。

50 uniform at random and we have a half a chance to get plus one a half a chance to get minus1 if we're picking anything other than 5050。

 we're only more likely to pick up the minus1， but in any case。

 the expected reward earned by our algorithm is going to be zero or less。

So that's a quite big gap between how well any algorithm could do。 Not the algorithm was arbitrary。

 So the claim is for every single algorithm， no matter how smart， just by virtue of being online。

 you're stuck with this huge gap between how well you might do in the best action sequence in hindsight。

Any questions about that？So this is the first limitation， okay。

 so the first super strong benchmark you'd dream up。It's too strong。So here's a key idea。

And this is sometimes known as regret minimization。

So we're going to compare it to a weaker benchmark。In which we swap the max and the sum。Okay。

So in English， what we're going to ask the way we're going to try to convince somebody that our algorithm did really well is we'll say。

 you know what， suppose we at least had four knowledge， not of the reward vectors。

 but of the best action。 supposeupp little birdie told me that if you were just going to pick one action。

 you should pick action 7 if all the time。 So let's see how well the best fixed action does。

 And let's compare our algorithm to the best fixed action in hindsight。Yeah。Yeah。And so again。

 what is that that's really just exchanging？The maximum and the sum。Okay。

So this is what we'd like to get。 We'd like to do as well as the best fix action in a hindsight。

 So we're going to examine the difference between our benchmark and how well we actually do。Okay。

 so we have some algorithm that's choosing perhaps randomly some action AT。

 and this is our total reward over all of the days。So this is what we're going to be focusing on。

For the rest of the lecture， this is also called the regrets。

Of an action sequence or of an algorithm for a given sequence of reward vectors？

the max outside of some of the A is really effective。No， no， which is important。

 it's one action let me。Let me actually write a in capital A for emphasis。So fixed action。

 so by fixed， I mean independent of the time T。And why， well， there's a few reasons。

 but you the first reason is just， you know you can't allow these sequences。

 you can't maximize over you know someone who does something different on the different days。

 you're going to get no nontrivial advice from the theory about what kind of online algorithm you should use okay。

Good， good question， right。So right， so we'd like to get close to this right so we'd like our regret to be as small as possible。

 We'd love it， for example， to be zero or maybe even negative。

 that'd be great but as the regret gets really big。

 it means our algorithm is doing poorly with respect to this benchmark。Okay， so why this benchmark。

 so that be a good question。You know， where does this come from？ And in some ways， you know。It'll be。

 you know， the sort of means will justify， the ends will justify the means in the sense that by looking at this benchmark。

 we'll be able to really sort of focus on some cool algorithms that have a lot of other applications。

 So， first of all， you know， this one， as we'll see， is basically achievable。

 You actually can have an algorithm that competes with this benchmark。And secondly。

 you a lot of algorithms don't compete with this benchmark okay so it's not trivial to get this number close to this number。

 but if you have a sufficiently clever algorithm， you can do it so that's a win for the theory it's sort of a framework which sort of guided us to an interesting algorithm for this problem that we might not have come up with that we might not have come up with otherwise。

 and then the other reason why sort of justified is even if you can compete with this weaker benchmark that's sufficient for the applications I mentioned in linear programming and a game theory。

Okay。So any questions so the goal is going to be to design an algorithm so that the regret is small。

 ideally close to zero。Okay。And again， just for， I want to emphasize that you when we design our own algorithm。

 we are perfectly allowed to choose different actions on each day。

 but in the benchmark and the left term， we're thinking about the best fixed action in hindsight。

All right， so I said that even you know， getting this regret close to 0， it's not trivial。

 So let me show you more concretely what I mean。So first of all。

You really need randomization to have any hope of getting the regret to be small。

So deterministic algorithms， not good enough。And I think most people， you know。

 when they first start trying to think about how they might， you know what should an algorithm do。

 I think you'd probably start with a deterministic algorithm。

 I actually think probably a lot of people would start with what's called follow the leader。

So what is this so you're at day 17， you have no idea what the rewards of the different actions are going to be all you know is what happened in the first 16 days okay？

Instead of a natural heuristic would say， well， which action has been the best historically。

 meaning summed over those 16 days has the highest cumulative reward。Let's pick that one。 Okay。

 So that's the follow the leader algorithm。 That's a deterministic algorithm。 Okay。

 So given the past， you put all your eggs in one basket and you play the best action。

But the claim is not just follow the leader， but any deterministic algorithm can at least in the worst case。

 suffer severe regrets。Even again， even with two actions。And if you think about it。

 and now this sort of unfairness of the game is really evident， right。

 So suppose it's a deterministic algorithm and I want to adversarialally feed your reward vectors where you do badly。

RightSo day 17， I know what your algorithm is gonna to do。 It's a deterministic， right。

 And I've got the code， right， So I'll just， on whatever you're gonna pick， I'll give you reward 0。

 and then I'll give all the other actions which you're not taking。 Re one。😊，Okay。

So if there are only two actions， for example， I'm going to ensure that your deterministic algorithm gets a total reward of0。

 gets zero every day， but every day I'm giving one of the actions a one， so one of the two actions。

 one of the two fixed actions will get at least t over two total reward in hindsight。

For a regret of capital T over two。So adversary can force。Our algorithm equals zero。While opt。

 and so now when I'm writing Opt， I mean our new benchmark and our benchmark for the rest of the lecture。

 the left hand side here。Well opt is at least t over  two。Okay。

So that's the second barrier so it's not yet clear if this is possible。But we know if it is possible。

 it can only be possible with a randomized algorithm。Questions about that？

did these negative one ones turn into zero ones？Well。

 I just I happen to use a special case of the reward vectors where I only make use of0 and1。

So when I did the first， you know just for sort of variety， when I did this argument。

 I used minus ones and ones， when I did this argument I did zeros and ones。

 I thought that would be the clearest， but you can make the same point with any two different numbers really。

Other questions？Okay。So the final limitation， the final lower bound。

So the first limitation motivated this weaker benchmark of the best fixed action。

 the second barrier says we need to consider randomization。

 so this third one says that even with this benchmark and with randomization。

 this cannot be zero there's still going to be some non-trivial regret。

 no matter how smart your randomized algorithm is。And so this is going to show that you can't do better。

No matter what online algorithm you use。Then square root。Of login expected regret。Okay。

So remember that we're thinking about randomized algorithms。

 so the expectation here is over the corn flips of the algorithm。Now， so okay。

 so how should you think about this， How should you think about the square root t log n。

 well you know maybe maybe think of n as small and t as large for the moment， at least。

 and notice that know for the deterministic algorithms， we were seeing a regret of t over 2。Okay。

 so basically， every single time step you are accumulating nontrivi regret。So， you know。

 this is sort of a bummer。 you know， we'd love to get regret 0。

 but at least this is a lot smaller than t over2。 So this is only growing like root T。

 the square root of the number of time steps， whereas for the deterministic algorithms。

 it can grow linearly with the number of time stepss okay。So it's not you know。

 so this is not a deal breaker， this is just just something we need to be aware of。

 but it doesn't rule out any kind of good solution。All right， so let me just say。

I'm not going to prove this formally。But let me just kind of tell you why it's true。So again。

 we're going to sort of play the role of an adversary so you fix your arbitrarily support but online randomized algorithm。

And so now actually， as an adversary， we're also just for fun。

 we're going to flip our own random coins。And in each time step， we're going to hand the algorithm。

 either the reward vector minus11 or the reward vector 1 minus1， chosen equally likely， 50，50。

So aver series randomizes independently every time step。Allright。

So if the adversary chose the reward vector at random in this way， what is the expected payoff。

 the expected reward that your algorithm gets in a given time step。It's zero， right。

 and it doesn't matter what action you pick。 It doesn't matter what your algorithm is。

If you pick the first action， you're equally likely to get1 or minus1， so expect to zero。

 same thing if you pick action2。So the adversarary just flips coins like this to pick reward vectors。

 ensures that however smart your algorithm is， the expected total reward is zero。Okay。All right。

 so that wouldn't be a problem unless the best fixed action in hindsight was better than  zero。

But actually it is。The expected value of opt to here the expectation is over the choice of these reward vectors。

Is。A small constant times square root of teeth and again， opt here refers to this left hand side。

Okay。So again， there's two actions， so it's just the best of the two actions。So why is this true。

 So this follows from sort of elementary probability that you've all taken， although again。

 I'm not going to go through the details。So if you flip capital T coins， fair coin。Obviously。

 you expect to get T over two heads。 That's the expectation。

 but there's also this standard deviation， which for flipping T coins is about root T。

So you actually expect the number of heads to be something like t plus root T or t minus root。

That's what you're expecting to see。So。Whichever of those two。

Heads or tails came up more times came up like t plus root t times that corresponds to an action for these reward vectors。

 which in hindsight would give you total reward like two root t if you have t plus root t heads so two plus root t ones on the first action but only t minus root T heads on the second action then if you always play heads you're going to be getting you know like the。

So basically， you're going to be adding two routine， total reward。Okay。

So that's where this root T comes from， it just comes from the standard deviation of a binomial random variable。

And you can do the same trick with many actions and if you do the same trick with many actions。

 this is what you get， you pick up an extra square root log of the number of actions factor。

And so again， that was just for intuition， I went through this argument。So any questions about that？

So this is the final line in the sands so we know no matter how smart we are。

 even if we use randomization， even if we use the best fixed action in hindsight。

 this is the best case scenario for the expected regret。

 the extent to which our total reward can be close to the benchmark。Okay。And what's cool？

And it's the point of the rest of this lecture。there's actually a simple online algorithm。

That meets exactly this bound。Okay。With expected regrets。Oh of Ru T login。and actually。

 the hidden constant here is two， as you'll see， so not it's actually very， very reasonable constant。

And again， let me emphasize the expectation here is over the coin flips of the algorithm。

 okay so this is a worst case guarantee， no matter how the adversary chooses the reward sequence。

On average over the coin flips in the algorithm， this will be your regret。At most。

It may be easier to interpret this guarantee if I phrase it in a different but equivalent way。

So suppose I define the regret as this sort of sum over all of the time steps。

 You can also ask about the time averaged regret， which just means dividing all of that by capital T。

 Okay， multiplying by one over capital T。 So that's like the average rate that you're accumulating regret per time step。

 okay。So if your aggregate regret is like rootee。Well， in the time average version。

 we divide that by T。 So we get a one over root T。 Okay， so more precisely。

 we get a root log n over root T。Okay。So， and then we could ask。

 how long does the time horizon have to be， how long do we have to play this game before we're only accumulating regret at an average of like epsilon per time step。

 where epsilon is some parameter of our choosing。And if you plug in the numbers， this is simple。

 I'll let you do it offline。This is what you get。Time average regret at most epsilon。After O。

Of log n epsilon squared steps。And again， the cost in here。

 if you plug in the numbers is just going to be equal to four， okay？So right think about it， I mean。

 so like if you only play this game once。Then there's nothing you can do， right， So you might。

 you know， incur expected regret， certainly like one half or something。

 If you only play the game once。 So the hope is just that as you play more and more。

 you have some hope of like the regret not just keeping a half over and over and over again。

And that's exactly what this is saying。 This says whatever average per time step regret you're interested in。

 if you play the game long enough using the algorithm about to show you。

 you can actually achieve that regret， most epsilon。I also want to sort of emphasize。

 you know this is a pretty small number actually， So this is sort of really appealingly fast convergence one might say to the no regret guarantee。

 this is really not that many iterations unless n is super。

 super big or epsilon is pretty small Okay so from modest epsilon and even very large n。

 this is a surprisingly small number of iterations to be able to get this get this guarantee。Okay。

All right， so any questions about that？So what you should understand now is just sort of the statement of the theorem。

 I haven't told you the algorithm and you know the corollary you should see how the corollary fall from the theorem and you should understand the sense in which this is the best we could have hoped for Okay that we should be very pleased to have an algorithm meeting meeting this lower bound。

 So any questions about all that stuff。So then let me tell you about the algorithm and prove the theorem。

 show you the analysis。So the algorithm is based on two principles。

Both of which should strike you as very reasonable。

So the first principle is just like when we were talking about follow the leader。

somehow all you have to go on when you're making a decision is the past performance of each action。

 you in effect that's sort of all you know。And so it's natural to let that guide you with what you're going to choose today。

 Now we know we can't be deterministic， we have to hedge， we have to randomize。But still。

 it's awfully tempting， you know， So， I mean， obviously。

 one thing you could do is just pick uniformly at random。

 But the hope is you could do something better than that。

 And so if something has performed better than something else in the past。

 it's natural to want to play that with higher probability。 Okay。

 so somehow the probability of choosing an action should be。

 increasing with its performance in the past。😊，So that's the first principle。And in fact。

 actually many ways of formalizing that principle will give you regret that is sublinear in capital T。

 okay？But if you really want this optimal bound a square rootity you log n。

 the second principle you need is you need to aggressively punish bad actions by punish。 I mean。

 decrease the probability with which you're going to play it。

 Okay So if you notice that some action is sort of worse than on average， the other actions。

 you want to be decreasing probability on that action in effect exponentially。

 as it keeps doing more and more poorly。 so that's the second principle。

 Its really aggressively decreasing probability on poorly performing actions。Okay。

 so let's see how this actually gets implemented。So this algorithm has a lot of names actually。

 like I said， this stuff has been rediscovered several times。

 I'm going to go with the most common name in theoretical computer science。

 which is multiplicative weights or the multiplicative weights update algorithm in machine learning it's often called hedge and it's closely related to the randomized weighted majority algorithm in machine learning for those of you that know some ML。

Okay。So multiulative weights， MW。So initialization。So we're going to maintain no surprise。

 a await for each action。Initially one。What does the weight of an action mean in some sense it's the credibility of this action based on its past performance so we're going to track a weight for every action and the bigger weight is going to roughly mean that this action has done well in the past。

All right， so initially we don't know anything， so we give all the actions the same weight。

So now I have to say what the algorithm does at each time step T as a function of the first t minus1 reward vectors。

So we're going to do is we're going to choose。At A A。With probability proportional。To wait。Okay。

So at any given time there's going to be weights。They're not going to sum to one necessarily。

 but I can get a probability distribution just by sort of choosing an action with probability proportional to the weight。

 so if the weights sum up to 20， I just divide through all the weights by 20。

 that gives me a distribution from which I sample my action。Okay。All right。

 so that says given the weights， how do I pick an action。

 obviously it's randomized as if we know it needs to be。And so the question is， OK。

 so how do the weights evolve over time？So after you choose your distribution randomly。

And you're given after the fact， you're told what the reward of each of your actions would have been。

This is the weight update step。Okay。And so this is going to be the formula that we're going to use。

The weight of an action that you're going to use next time step。Well。

 it's the weight of the action at the current time step multiplied by some factor。

 so that's the multita weight update part。So it's multiplied by what， well。

 it's going to be one plus eta。Time is the reward of this action at time step T。

 I'll tell you more of8 is a parameter， I'll say more about it in a second okay。For now。

 you can just think of Ada as being like 0。1 or 001。And that's the entire algorithm。Okay。

 so that's a method of way to Ab。This is the algorithm that actually has optimal regret that achieves this best possible bound。

 with square root t log n。Okay。So any questions just about the code， have clear on the algorithm？

Obviously， this would be very simple to implement。RightSo you know。

 ignoring like bit complexity issues， each time step， you just have to do a linear amount of work。

 Okay， you just have to update the weight of each action。 So it's a very。

Simple lightweight algorithm。So let's talk about Ada。So here is a parameter。

 we'll choose it later when we have some guidance about what we want it to be。

 But let me just ask you。 So suppose I took Eda to B 0。What would this algorithm do each time step？

Namely。Yeah， so you do the same thing， which would be wet。嗯。

Take connection action with probability proportion。Right。Exactly right， exactly right。

So every time step， if8 is 0， this would just pick an action uniformly random。

 so it's doing no learning。In effect， okay， so8 is sometimes called the learning rate。

 with the learning rate of 0。Then you you always select uniformly。Now as Ada gets bigger。

 so if 8D is positive。Then what do we see， We see that the higher reward that this action took。

 the more we updated to wait。On the other hand， remember， the rewards could be negative。

 so if the reward is less than zero， this is going to actually result in the weight decreasing。Okay。

So every action will always have a non negative weight and it'll go up and after any time step where it had a positive reward and it'll go down after any time step that had a negative reward。

And if you think about Ada as getting pretty big is like approaching one or something like that。

 this is sort of doing something like follow the leader。 okay。

 it's somehow like paying a lot of attention to the past performance of an action。

 It's not exactly the same as follow the leader， but intuitively as Ada gets bigger。

 know you're being more rash to sort of change， you know perhaps dramatically the weight on an action as a function of how it did just yesterday。

Okay。So A in general is a parameter to interpolate between these two extremes。

 just no learning at all and kind of， you know， very kind of aggressive learning。Okay。Right。

 so let me just say the only thing we need to know for the analysis is that we're going to pick this。

To be between zero and one half。Chose a writer。Okay。As I was preparing my notes。

 I realized my As look a lot like threes。So if you ever see something looks like a three。

 it's going to be an Eda， so I'll just forbid myself from writing the actual threes on the board this lecture。

Okay。So any questions for do the analysis？So the analysis is pretty interesting。

 so the algorithm is very straightforward。 analysis is less straightforward。 okay。

 we're going to have to do some thinking to get the analysis right。Any questions for that？

So what makes this analysis sort of challenging， It's not that bad。

 I'm going to give you the whole proof in the next， know， maybe 20 minutes or so。

 but why is it nontrivial。And if you think about it， actually。

Well the theorem is stating it seems to be you know being it's successfully comparing two things which seem to have nothing to do with each other right so what's our protagonist。

 what we care about is our algorithm， the multiplicative weights algorithm。

 and we care about the expected reward it's going to accumulate okay that's what we care about。

 what are we comparing it against we're comparing it's against the reward of the best fixed action in hindsight。

Okay。Like what do those two things have to do with each other？It's really not clear， actually。

 they just seem like totally different objects， like the trajectory of this one kind of randomized algorithm。

 and then the best thing in hindsight。So that's the challenge is sort of how do you get the two sides of the theorem in the same room？

And so there's really just one very simple trick， but in my opinion。

 it's sort of the inspired idea of the analysis。Which is to introduce an intermediate quantity。

 which we're going to be able to then relate to each of the two things we care about。 Okay， opt。

 the best fixed action in hindsight and the multi of weights guarantee。

So the intermediate quantity we're going to look at。

Is just the sum of the weights of the actions as multipl of weights proceeds。

So some over the actions。Of the weight of an action at  time T。Okay。

So this will be an important quantity for us。And don't forget that。

 you know every time there's a time step， the weights change。

 so therefore this capital gamma is changing as well。

It would be a good question to ask where would this come from。

 right so the idea of having an intermediate quantity to relate two different things which don't have an obvious connection。

 that's sort of a very general idea。 It's worth're sort of remembering。

 but it still sort of you know leaves you with a task of figuring out what is this intermediate quantity。

 And so how would anyone ever guess this。And in some sense。

 you want to have some part of the proof which is really leveraging the way the multiulative weights algorithm has been defined and so in particular the weight update step and so the one reason you might sort of think about using this intermediate quantity is that and we'll see this in detail in a second。

 you can really track very precisely how this particular quantity evolves as a function of the rewards enjoyed by multiplative weights。

 so in other words we're going to show that this capital gamma is big if and only if multiplicative weights did really well。

Okay。Then we're going to have to prove that opt can only be bad if capital gama is small。

 so opt can only be right， so that's what we're going to show。So let me try to make that precise。

 So the claim is that this is sort of defined so that we can track its evolution carefully and related to the gains enjoyed by multiplicative weights。

 So why is that true。So how does gam tea evolve？Over time。So again， just to be clear。

 so we're going to have two parts of the proof which we'll then combine the first part。

 we're connecting this to the performance of our algorithm of multipl of weights。

 and the second part will connect this to optt。So for now the goal is to somehow。

Have a relationship between。Capital gamma and the rewards of multi bigger weights。

So a little notation just to make it simpler。So for a given time step T。

Let's think about how much we expect to get with the multiple weights algorithm。

So it's just going to be。So just by the definition of expectation， we just look at the probability。

The multiple the weight chooses a。Times the reward that you will get by choosing A at time T。

 so's definition of the expectation。And。Remember， the motive of weights chooses actions proportional to their current weights？

So this equals。Some over AA。Does anyone see how to express this in terms of other notation that's on the board？

So it should be at time T。Do you see what gamma has to do with anything？Right， exactly right。So this。

Is W the current weights over the sum of the weights？

Because this is just a normalizing factor when you pick proportional to the weights。So。

Let me pull this one over gamma at front。And we get this。And we're going to call this little gamer。

Okay。So little gamma， remember， is just shorthand for what we get at day T and multiplude of weights。

 so what we're trying to do， we're trying to lower bound the sum of the gamma teas。

Some of the gama T is what multipl of weights gets total， we want that to be big。All right。

 so any questions so far， this is just some notation。

 I still haven't fulfilled the promise of actually relating this intermediate quantity capital gamma to the multipl of weight rewards。

 that is to some of the little gammas。A right。There's a question down here， by the way。

 did it get answered？Cool。All right， so back to the question。

 how does capital gamaT evolve over time？Well。Let's look at time step T plus one and relate it to what value it had at the previous day at time T。

So by definition， this is just the sum of the weights。Okay。

We can certainly express the weights of day t plus one in terms of the weights of dayt right that's exactly what the update step gives us。

So this is just equal to sum over a。WTA times 1 plus ata reward of a times T。

So just by definition of the weights。And if you stare at it a little bit。

 I'll walk you through this in a second。But this is actually exactly equal to。

Gamma t times 1 plus eta little gamma T。Okay。So again。

 this may be sort of a little hard to see in real time， so let's just take the two terms separately。

 so let's first just take this term。Okay so take the one， forget about this。There。

 we just have sum of the weights at day T。 right So that's the gamma T factor。What about this term？

Well， this is going to be8ta times some of the weights times the rewards。And if we look over here。

 we notice that actually the rewards enjoyed by multipleude weights is just that same。

Dot product of the weights with the rewards of the actions。

 except with the normalizing factor of1 over gamma T so in other words。

This term is exactly the same as the circle term， except with an extra ada and missing a capital gamma。

 and so that gives us this。Okay。And all these are equations who have done know we've lost nothing so far。

So this is what I meant when I said， how would you ever think to you know study the sum of the weights。

 this is a pretty appealing calculation， and this really leverages the exact form of the multiplicative weights algorithm。

 Okay so this gives you this kind of really intuitive understanding。 So what does this say。

This says in a time step where， remember， gamma is the expected reward of multiude weights at dayT。

So if day T， the algorithm is likely to get a big reward。

 that means capital game is going to go up for the next time step， conversely。

 if multitude of weights if there's going be negative， say multi weights doesn't do very well。

 then this lecture should be smaller at the next time step。Okay， so very loosely， you know。

 at the end of the day， after these capital T time steps， if。Capital gamma is big。

 presumably be the reason is because the little gammas are big because the algorithm actually got a lot of reward over time。

 and we'll see that's really true。O。Good。So。One more step， just for convenience。

So if this is all exact， I've made no estimates， we're actually going to make use of a weaker statement just because it's kind of more convenient for us。

So。We're going to use an upper bound on this term。Which is e to the Eda。Gamity。

So the claim is that this。Is the most e to the Ada gate？Why is that true？Well。

 get proof by a Taylor expansion if you really felt like it。

 but this is the kind of thing you can just plot and convince yourself of。Right so。

If you look at the line。1 plus x。And you look at the graph。I you to the X。Yeah， yeah。

 got the slope wrong。Also，1 plus x。And then right e to the x， it looks like that。So everywhere。

For all real values of x， e to the x dominates 1 plus x。

 doesn't matter if x is positive or negative or what？

So we're free to upper bound this by e to the a of gamma T， which gives us this。Why did I do that？

Okay， so why was that convenient， Well， you know this equation relates how gamma evolves with one time step。

Now， if you think about how it evolves over multiple time steps。

 we're just going to keep getting multiplied by these successive terms，mma1 plus a of gamma t。

And so by switching to the exponential form， those now become a sum in the exponent。So。

 and this will complete the first step。Consider the sum of weights at the very end of the algorithm after all T time steps have expired。

What do we have？Well。It's whatever the sum of the weights was at the beginning of the algorithm。

Times what it changes by。And it changes by it most e to the eta， oops。

 there should be a product there。Heatated the A a gammate。Okay。So we show that at every time step。

It goes up by at most e to the a at a gamma T， and so this is just accumulated over all of the time stepss。

What is this， was that number？So this going to be n， right， everything stretch of the way to1。

And so does n action， so that's going to be n。So this is going to be equal to n times e。

 and this is exactly why we did that estimate over there。S t equal1 the capital T。Ada gamate。Okay。

And this is the culmination。Of step one of proof。Alright。So again， remember。

 what was it we were trying to do？We introduced sum of the weights to relate it to the two things that we actually care about。

 and in this part， we're relating it to the performance of multiplative weights。

 Notice this will be clear if I write the Eta outside。Notice。This。

Is the performance of multiative weights so we actually really care about this number and we've now related it via a fairly simple formula to this intermediate quantity。

 some of the weights at the end of the multiulative weights algorithm。

 so that's success of a relatively simple relationship between one of the things we care about and the intermediate quantity。

😊，Questions about that。So there's a second step， but it's a bit shorter。Any questions about step one？

So the action item now is to relate the sum of the weights to the other thing we care about。

The best fixed action in hindsight。Okay。And。Here， we're just going to use a very crude estimate。

 Okay， so what's our goal， Our goal is to say that the only way opts could be good。

 could be high is if capital gamma is big。 And then by part one， we sort of think， oh。

 that should probably mean multiplicative weights is good too。So。We're just going to use。The idea。

That if optt is good， i。e。 is a good fixed action。Then it's got to imply that our intermediate quantity。

sum of the weights is pretty big。Okay。And the reason this is going to be true is just because the weight of this one really good action。

 single handedly lower bounds to the sum of the weights of all of the actions。 Okay。

 so it is going to be a This is a crude part。はい。So in more detail。So Op is going to denote。嗯。

The total reward of the best fixed action in hindsight。

And we're going to call the best fixed action in hindsight a star。How do we relateO？

Two the sum of the weights， two capital gamma capital T。Well。Weights are always not negative。

 They can go up， They can go down but they're always not negative。 So certainly some of the weights。

Is lower bounded。By the final weight。Of this allegedly great action， a star。Okay。

So this should be trivial， this is just one of the terms of that sum。

And so now we're going to use how these weights evolve。

Over the course of the multi weights algorithm。Okay。So what's the final weight of a star？

Well it's just the initial weight of a star。Times the accumulated multiplicative updates that you ever saw on A star。

嗯。So one plus eda。RRT of A star。Okay。So that's again。

 just by the definition of the update rule that we're using。What is this here？Yeah， this is one。

Did you forget about that？All right， so this is also good or we're making progress so what are we trying to do。

 we're trying to relate the sum of the weights at the end of the algorithm toO。

 what is opt some of the rewards of a star here we're seeing the reward of a star。Okay。

 I guess it's not summed。 That's sort of annoying。 again。

 we really care about the sum of the rewards of A star。

 Here we have this product of these like one plus whatever terms。

So how would the product turn into a sum well sure would have been nice if this was like E to the reward of A star。

 then all of a sudden in the exponent we get the sum of the rewards of A star， which is what we want。

So the first thing one might think of is， well， okay， cool。

 why don't we just actually use exactly the same trick we did in part one？

Let's just replace this by e to the eta r star of a star， sorry， Rt of a star。So like。

Why can't we just replace this with E to the Eda？RRT of a star， analogous to step one。

So the reason that doesn't work is because we can't have our cake and eat it too okay so we already use this inequality once to sort of say that the exponential is above the line。

 but now remember we're trying to prove what we're trying to prove。

 we're trying to prove a lower bound on capital gamma。So that's not going to work。Any clear on that？

So the previous inequality。This inequality is not good。On the other hand， again。

 if you just go back and look at that same figure。You say， well。You know，1 plus x and e to the x。

 if you're around  zero。They're very close to the same number。

 You should be able to kind of switch really nearlyly between the two for x close to zero。

So that's what we're going to do。Yeah， me put this here。So how do we make that precise？All right。

We're going to use a tailor expansion， that's a good way to sort of rewrite one function in terms of another。

So the Taylor expansion we care about is really of the form 1 plus x， but let me just do it this way。

 Let me actually work with log 1 plus X， and then we'll take the exponent again later。So， you know。

I'm sure you studied this freshman year these Taylor series， but in practice。

 you kind of forget them and you look them up on Wikipedia when you need them。

So this is what it says。X minus x squared over  two。Plus x cubed over3 minus x to the fourth over4。

 plus and so on。And of course， now I have to confess a previous lie of mine has been exposed。

I promise I never write a three on the board。Okay， but these are the only two threes I'm going to write all lecture。

 I promise。Okay。So。But it's sort of annoying having all these terms。 And remember。

 what we're trying to do we're trying to have a lower bound。 Okay。

 we want a lower bound on the pink circled quantity。 Okay。

 so we want to turn this Taylor expansion which is exact。

 and we want to have an underestimate of log 1 plus x。So how do you do that， well。

 what we're going to do is we're just going to subtract another copy of x squared over2。

Okay so thats only makes it smaller。And then we're just going to ignore all of these terms。Okay。

 and so the claim is that gives us an。Lower bound， at least provided x is sufficiently close to zero。

Okay。Why is that true？ Well， okay， so we subtracted something and then we sort of stopped subtracting a bunch of other stuff。

 What do we subtract， you know， whatever， Okay， so maybe x。

 who knows what x is x is like you know something。 So what we're subtracting here is like say 0。

1 so we subtract an extra 01。If x is the most half， then this x cubed term。

 this in magnitude will be at most 0。05。 this x is the fourth term in magnitude will be at most 0。

025 and so on。 so all this will just be a geometric sum upper bounded some of the magnitudes by what we already subtracted so we subtract something and the stuff we don't subtract is dominated what we subtracted。

And so here we're really using it's important that we use the fact that x is。Is most to half。

For the geometric sum argument。And this is exactly why we capped Ada at a half。

 this is the part where it comes up。All right， so it's fine that if you didn't totally follow that in real time。

 I'm sure you get the gist of what the argument is and you can check the details offline if you want。

So what's the upshot？Let's do this here， actually。So the upshot continuing this inequality。

Gamma t plus one。呃。Is at least。So we have that same product。

 but now we're going to put in our lower bound。 So remember， what was the lower bound。 So for log。

Of1 plus x。So for log of 1 plus x， the lower end was e to the minus x squared。

 we're going to take both of those to the exponential， so this will become a 1 plus x。

 this will become an e to the x minus x squared。What is our X？This is our X。Remember。

 we scaled so that the rewards are between minus1 and1。 and remember that Ada。

 I promised you would be at most to half。So our x's are almost a half in magnitude。

 so our estimate applies。And what do we get， So this is going to be。1。To the Ada Rt。Of a star。

Likeikes。Room here。去去去。So E to the Eda。RRT A star minus。A is squared。RRT， A star。Sorry， squared。Okay。

 so remember， the lower bound was e to the x minus x squared。 Here's the x。 Here's the minus。

 here's the x squared。Okay， and so now why did we do this， This is exactly what we wanted， right。

 so what's this thing we care about， We care about the total reward of the best fixed action。

 That's exactly the sum of these。 Those are now in this exponent。 So this product becomes a sum。

 which is exactly what we want。This， frankly， is kind of annoying。This Eta reward squared。

 it's not totally clear what to do with that。 What we have going for us is that because this is an Eta squared and Eta small。

 hopefully this is just slo。 we can kind of do something crude with。 again， that's actually true。

So for this， I'm just going to use the fact that because all the rewards are between minus1 and1。

 all the squared rewards are at most one。So that' what we're going to use in the following on quality。

So E to the eda。Some over the days of the rewards of the optimal action， a star。Minus eta squared。

Capital T。Okay。So the Eta squared is from here， each squared reward is a one。

 so aggregating over the capital t terms that winds up being bounded above by capital T so by subtracting the maximum possible value that it could be。

 I get an underestimate on the quantity that we care about。All right。So now all we got to do。

Is we going to combine this and we combine this？Gammas are intermediary。

This is one of the two numbers we care about， this is opt。And this is the other number we care about。

 this is the multitude of weights。Summer awards。All right， and we're almost done。So by one and two。

So now we're just going to chain our two inequalities together。

So we're trying to lower bound how well multitative weight does。

So we're going to start with the term， which involves multiplative weights， rewards。

We prove that this is at most gamut， the final sum of the weights。And then in the second part。

 we proved that this is at most。E to the8da。Some over T of a Stars rewards。Minus8ta squared t。Okay。

And now we have no further use。For gamma。So the whole point of this intermediate quantity was to get a relationship between multiplative weights and opt。

 and we've done that。So now we just simplify， so now we just sort of take logs and let the dust settle。

So we're going to take a natural log on both sides， so this will become a log n。

 this will become eta times the sum of the multipl of weight rewards。

 this will become eta times optt minus eta squared t。So dividing through by Eta。

And moving this to the other side。What do we get get？The multi of weight reward。Is it least？Ot minus。

A to T。Minus login over。Okay。So again， this board is just kind of algebra。

 this should be very straightforward to check if it's not clear in real time。

 the interesting part was the hard part was proving these two inequalities。

 connecting these tworelated， seemingly unrelated quantities。Now。

 the dust is settled and we see what we get， and actually what we get is very interpretable， okay。

So this is sort of the holy grail。 This is the best fix in the hindsight。

 this is what we're trying to do as well as。 and we have two error terms。 one error term is big。

 when a is big， the other error term is big， when8 is small。So what does it mean when8 is small。

8 is small is a slow learning rate， so you're going to stay really uniform for a while but then you should hopefully home in on what the best action is So when8 is small you have this kind of overhead error。

Because you're doing basically uniform for the first bunch of time steps。

But then sort the average per time step regret in this term is small。On the other hand。

 if8 is really big， a very aggressive learning rate。

 you're not going to have a lot of overhead figuring things out at the beginning。

 but you'll never get it quite right， Okay because you you're sort so floing around so aggressively。

So that's what those two error terms correspond to。Now， for our purposes。Remember。

 AA was a free parameter。All we need about Eda is that it is the most half， okay？

But we can set it to be whatever we want。And know， when you have a couple terms。

 error terms say with the same parameters， usually what you want to do is set the parameters to balance the two error terms。

So here， if you set Ada。To be。Square root of log n over T。Then in fact。

 each of these becomes root T times root log n。So the combined error is two times root T。

Natural log of event。And that completes the proof。Okay。So that's a fairly major result。

 that's why I went ahead and did the fullproof。So the Mo bit of weights algorithm， is just this。

 maintain a weight for every reaction。Let it evolve in this way。

 it achieve the best possible regret of any randomized online algorithm。And again。

I think it might be easier to remember。Rather than trying to remember this。O of root T log n。

 expected regret。 Don't forget about the time average version。 Okay。

 so suppose you want per step regret at most like 0。05。

 This gives you a recipe of how long you have to play the game before your per step regret actually is that low。

 Okay， namely， it's four log n over epsilon squared where n is the number of actions。All right。

 so any questions about the multipl of weight analysis？

The rest of the lecture is going to be about an application of this。Questions。

So what I'm going to do。To conclude the lecture is I'm going to give you a second proof of the Minmax theorem。

So we approved the Min Max theorem last lecture。As a consequence of strong duality so strong duality。

 we didn't really fully prove， we sort of give a handway proof sketch。

 but assuming strong duality we deduced the miniax theorem。

 I now want to show you how just multiplic of weights and the guarantee we just proved for it also can be used to deduce the miniax theorem so let's actually give you a full complete proof of the miniax theorem。

So Min Max were visited。Recall what it says。So let me write it in。Mattrix vector form。

I'll remind you what all these mean in a second。So we're back in the domain now of two player zero sum games。

 A two player zero sum game is specified by a matrix， capital A。With M rows and columns。

 the row player picks a row column player picks a column。

 the entry of a matrix is the payoff to the row player and the negative payoff of the column player。

 so if you like the payment from the column player to the row player。What the Min Maxax theorem said。

 it said， well， if players play optimally and are allowed to randomize。

 it actually doesn't matter whether you go first or whether you go second。

So the left term here is what happens if the row player goes first？

So the row player does the best thing I can。Under the assumption that the column player will respond optimally。

 and similarly here， this is where the column player goes first and the row player goes second。

 X here is a probability distribution over the rows Y or distribution over the columns。Okay。

So we saw how this is implied。By LP duality。How would you use the existence of this multi of weights algorithm to prove this。

 It sort of an algorithmic proof。So here's what you do。So fix your favorite epsilon。

 we're going to let epsilon go to zero at the end of the proof。And now， so to be clear， I mean。

 we're just proving。You know， this statement。 Okay， so in the proof。

 we're going to be running multi of weights。 Okay， but we're not， know， it's just for the analysis。

's just for the proof。 Okay， So in our minds。We imagine the following game being played。

So a time1 up to t， capital T， which is going to be four log n of Repson squared。

We're going to imagine as if the row and the column player。Okay chooseose a day T。

 a mixed strategy using the multiplicative weights algorithm。 so each player has their own copy。

 own private copy of multiplative weights。 Multiative weights tells you how to pick a distribution of actions。

 So just think of the row and column player is using that algorithm to figure out what mixed strategy they're going to play on a given day。

So R Col players。Independently choose。Mix strategies， I'll call them PT and QT。

V multiplicative weights。Now， if you're a little confused， that makes sense。

 right because there's sort of a type check error at the moment。 What does this mean， right。

 think about like the interaction loop with multiple of weights， right， So you say what should I do。

 and it tells you， And then you tell it how all the options did yesterday。

 And you say what should I do tomorrow， And then it tells you and so on。

 So multiple weights is expecting you to feed in these reward vectors。

So somehow for this to make sense， I need to say what those reward vectors are。Okay。So。

But you define them in a very natural way。So I want you to imagine the following， again。

 this is all in our heads so we can define this experiment however we want for the proof。

Imagine that， you know， after day T。The row and the column player announced to each other what they played。

 Okay， So first， they just sort of independently choose randomly， according to P， according to Q。

 And then afterwards，' like， by the way， here's the distribution I used。

 And they tell each other this， okay。So now you're the row player。

Right and you know what the column player did yesterday。

 You actually know what the expected payoff of each of your strategies was yesterday。

so if you know the column player is putting 50% on the first column， 25% on the second column。

 25% of the third column， you can just compute the expected payoff of each of the rows。

 given that strategy by the column player。So those are going to be the reward vectors that we feed in the multiplative weights。

So for the row player。Define the reward vector。By AqT。Okay。So remember Q。

 this is a distribution of our columns， so this is just going to be the vector listing the expected payoffs of each row。

 given the distribution Q chosen by the column player。And then similarly。For the columnlin player。

Used to find it analogously。So it's going to be minus remember the A encodes negative payoff for the column player。

This is going to be the strategy used by the row player at Tom T。

And so PT transpose times a is just going to be the expected payoff of each column to the column player。

 given what the row player did at D T。All right。So many questions about that。

 so what I want you to understand at this point is I want you to agree that this is kind of a well defined thought experiment。

If we wanted to， we really could think about a row in a column player choosing mixed strategies in this game。

You knowOne strategy per day using multiative weights in this way。So it's not clear why I did this。

But you agree it's a well defined thought experiment。All right。Good。So we need a little notation。

Let X hat be kind of the average row strategy that the row player played over all the days。

So some over equal to capital T of PT。Similarly， y hat is the average column strategy。Okay。And。

I'm going to note by V。The time averaged expected payoff of the row player， given how they played。

Okay， so this is what I mean by time average， I'm going to look at each of the capital T days of the day up and look be average payoff。

What is PT transpose A Q transpose， This is the expected payoff earned by the row player on day T。

 Okay， remember x transpose A Y， that's always the expected payoff of the row player When the row player chooses x。

 the column player chooses Y。 So this is just the time averaged expected payoff of the row player。

In this thought experiment。Okay， good。So any questions so far？

So it's just a short argument now to show how the multiplative weights guarantee。

Implies them in max theorem。Alright， so how's it go。Ch。Well。

 think about things from the row players' perspective。Okay。What does multipleative weights guarantee。

 it says that the expected payoff earned by this player because it was using this algorithm is going to be within epsilon of the best fixed action in hindsight。

So if you're the row player， the best fixed action in hindsight is just a row。

So what Moluude weight says is。You know，The expected payoff of the row player。

Whi was generating the PTs using multiple of weights。

 that's going to be at least as good up to epsilon as the expected payoff if you played one row over and over and over again of a fixed row I。

Ch。So by the multi of weights guarantee。And notice that I chose capital T so that the first step regret would be down to epsilon。

What do we get？So V is how well the row player actually did using multiple weights。And。Up to Epsilon。

 it did as well as it could have with any fixed action。So what would a fixed action look like？

It would look like。You deterministically play。 So by the way， there's a horrible notation conflict。

 which I never figure out how to avoid in this lecture。 So capital T here， it means transpose。

And here it means the time horizon。 I always I just don't know how to fix this really。

 So hopefully it'll be clear from context so。So again， remember。

 this is how well the row player did actually using multi weights。 And by the guarantee。

 it's within epsilon of how well it could have done doing a single thing。

 a single fixed action at all time steps。 So what would that mean。

 it would mean it would choose some row I and play that deterministically every time step。

 so E I just denotes the if basis vector， This corresponds to deterministically chosen row I。Okay。

And this is true for all rose pie。All right。So this is what multiplicative weights guarantees the row player。

 in some sense， if you're playing a game over and over again。

 this is why you might want to use multiplative weights to tell you how to randomize。

Is the guarantee you get。 so any questions about that。

 can everyone sort of map this onto the multiple weight guarantee？

So this is the multipleude weights payoff， this is a fixed actions payoff。Okay， so now。What's cool。

That actually means。That the expected path of the row player。Is up to epsilon。As good。Right， oh yeah。

So what's the point， Okay， so now this no longer depends on the day T。 Okay。

 So if you look at this expression on the right hand side。

The only symbol that depends on the day little T is the column player's payoff。

So we're going to bring this part， which is independent a little T outside。

 then we'll just be averaging over the column player playoffs and recall that Y hat denotes the time average of the column player payoffs。

So let me just write。Independent of T。Good。So in other words， this is just equal to。AIDI transpose。

Wops why hat？Minus epsilon。Okay。For all Rose eye。So this is just rewriting the same thing。

 you do as well as any fixed action。And the claim is actually。

 this means you're doing up to epsilon as well as any probability distribution。So max over x。

X X transpose a Y hat。Yep。The one over t so that's。 shoot， sorry。

These are supposed to be time averages。Oh boy， okay。All right。Does that answer the question。Okay。

 so this is what we get for the row player， the expected payoff it gets by doing multiple of weights is as good as any distribution it could have used against the average strategy used by the column player。

And if you apply the same thing to the column player。What you get is that。V， remember。

 this is the negative payoff of the column player。So the columnlin players are trying to make this as small as possible。

So just by a symmetric argument， the X becomes the next hat。The y half becomes a y。And it's again。

So again， remember the column player wants this to be as small as possible。

 and so multiude of weights says actually the column player does as well as anything it could have done against X hat up to an epsilon error。

And again， this is just the same argument as this with the roles of the players reversed。

So if you put these two together。What you find at the end of the day。Is that？

Max x means y x transpose a y。Is at least。The expected payoff for the rules reversed。

Up to two epsilon。Okay so amount of time so I'm sort of not doing this in detail。

 but trust me you just plug these two together what you find is that the minm inequality holds in the opposite direction of the obvious one remember the obvious direction says that going first is only worse so this we immediately know is that most this。

We've reversed the inequality with a two epsilon error。So if we just let epsilon go to zero。

 that implies that actually the row player can do just as well going first as it could going second。

 that's the in next step。