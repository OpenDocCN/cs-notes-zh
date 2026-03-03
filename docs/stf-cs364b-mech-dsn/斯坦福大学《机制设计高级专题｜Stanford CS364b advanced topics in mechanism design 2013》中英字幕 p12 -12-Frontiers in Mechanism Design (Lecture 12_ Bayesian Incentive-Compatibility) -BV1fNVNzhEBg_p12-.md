# 斯坦福大学《机制设计高级专题｜Stanford CS364b advanced topics in mechanism design 2013》中英字幕 p12 -12-Frontiers in Mechanism Design (Lecture 12_ Bayesian Incentive-Compatibility) -BV1fNVNzhEBg_p12-

So let's do the proof。 Le 2， then limit 3。So again just to remind you， so what's the notation。

 so we've run the shrinking mechanism to completion。

 so these bidders have these sets of items that they're going after。

 those are shrinking over time and at the end of the algorithm。

 S hat I is the smallest it ever got at the end。And we're defining opt hat as if I maximize welfare。

 but I insist that you only give bitter I items from S hat I how high can you make that welfare okay？

And then some extra notation， W hat are going to be the bidders that actually get a bundle they want an optt hat with a winner eye getting a bundle they want T hat I。

 which again by definition has to be a subset of S hat I， the only ones they're allowed to get。

And the proof factors to things， first of all， it just says， well， at least， you know。

 if the original problem was we could only give people items from S Ha I。

 how well are we doing with respect to that benchmark。

 And then Le 3 says actually that benchmark isn't too far away from the one we really really care about the actual maximum welfare。

Okay， so proof of lemma2。So here's where intuitively。

 we're going to use the fact that we're simulating the greedy algorithm to argue that our allocation is reasonable。

So let's just fix an iteration R。So I should say each of proof the proof of limit two and the proof limit three。

 each have sort of one- neither one is long， but each has one kind of sneaky point，So。Right。

 so fixed iteration R。Let Elbar denote the dropouts。Decineration。Okay。

 so these are the people we're not getting welfare from。

 So we have to argue that sum of the values in these loser sets is not too big。

And we want to do that using the fact that the greedy algorithm is reasonable。

So here's where we use the behavioral assumption。Well， we use a few of them。 But remember。

 we had this third behavioral assumption， which said， if。

You get to the point of you can either shrink or pass and not shrinking is going to result in you getting kicked out of the auction。

 and shrinking would potentially let you would let you get allocated and greedy。 You're gonna shrink。

 Okay， Why not？ Why would you just not shrink when it's going to get you kicked out。

So consider someone who drops out this iteration。Okay， what has to be true？

So what has to be true is that you didn't have the capability of shrinking to become a winner。 Okay。

 so you dropped out。 I mean， you lost， you didn't double your bid。So in particular。

 there's no way of shrinking to enforce you winning。And so which means in particular， okay。

So what am I saying， so in greedy。When greedy reaches。Some I and L sub R。Oh。Subsets of S sub I。

That I might want。Okay， remember， I has its preferred bundles and in general， S I。 So again。

 maybe S sub I is like 10 different items。 and there's these various bundles of size 2 to 4 in there that bitter I would be happy to have。

 It has to be the case that every single one of those bundles conflicts with something that greedy is already committed to。

Because if there was some bundle that I wanted， which doesn't conflict with what greedy already committed to。

 then by the behavioral assumption， it would shrink。

 it would shrink to one of those and not get kicked out。All subsets of S I that I wants。

Including T hat I。 So that's， again， the items that so in the event that I is a winner in this optimal solution。

 and it gets the item T hat I， that one in particular is also blocked by things that greedity have already chosen。

And so， this implies that。The greedily computed。Set， which remembers new is what I'm calling that。

And so as you do the greedy computation， you're adding bidders to new。So the greedily computed new。

Is equivalent。To the。Output of the greedy algorithm。This is the sneaky part。With the following sets。

So when I， when I run the greedy algorithm， what am I really running the greedy algorithm with。

 I'm running it with these S subs。 Okay， and I'm going to do this sneaky thing， which basically says。

 well。You know， for the bidders that get rejected by greedy， okay。

 I rejected them because I thought their S I was too big。Okay。

But then I gave the bidder the option to shrink if it wanted。

And the only reason the bidder wouldn't shrink is because if everything it could shrink to would also be rejected by greedy。

Okay， so I'm running the greedy algorithm。 I see this set of 10 items that conflict with stuff that have already allocated。

 So on the greedy algorithm。 I reject this bitter， But actually， something stronger is true。

 given the behavioral assumption。 Okay， any of the subsets of items that this bidder might have wanted。

 Okay， so the bidder might have shrunk to just four items。 But even there。

 that would conflict with stuff greedy is already allocated to。 If not， it would shrink。Okay。

So what I'm trying to say is imagine。 So we ran the greedy algorithm with a certain collection of sets。

 the Ss。 And so what I'm saying is， I'm gonna， as a thought experiment。

 imagine running it again with a different， smaller collection of sets。

 And my claim is that the output' is going be exactly the same。😊。

And that's going to be useful for me arguing that agree is a good approximation。So in the real world。

 in the actual a， I run greedy。 I go through the bidders in this order from high bids to low bids。

 I consider their S sub Is， and I reject the Ss that don't fit。Okay。But。

 but consider this alternative universe where for one of these bidders that got rejected。

 its actual set wasn't actually S sub I。 It was something smaller。O。

 something smaller than it wanted。 O， The point is this greedy algorithm still would have rejected that bitterder。

Okay， because even the smaller set would conflict， conflicts with items have already given away。

 How do I know that it conflicts with items have already given away， Well， if it didn't。

 then by the behavioral assumption， this bidder would have shrunk to the thing。 Okay。

 and I would have accepted it。 So again， for the purposes of analysis。

 I can imagine as if the bidders that got rejected。

 actually declared these small bundles that they want。So that's what I'm doing here。So I'm saying。

 you know， the actual output of the greedy algorithm with the real sets。

 the S sub Is is exactly the same as the output of the greedy algorithm。

Where I leave everybody the same。Except for the bidders that I'm rejecting that the optimal gets credit for。

 which bidders are those， well the bidders are rejector L sub R。

 the bidders the opt gets credit for is exactly W hat， so for any bidder an LC sub R and W hat。

I'm going to pretend as if its bundle was not S sub。

 but was actually the bundle of items it gets in the optimal solution， okay。

Greedy would run exactly the same。 It would still reject this person。

 The output would be exactly the same。 But my approximation guarantee is going to look better if I think about the algorithm on the right hand side。

 okay。So that's the sneaky part in this in the proof of lemma 2。Right。

 so we know greedy output something that's as good as any other feasible solution or know。

 within a D factor。And if I look at these bidders that are winners in the optimal solution and I look at their bundles。

 their bundles have to be just joint because they're simultaneous winners in the optimal solution。

So T had I。So in fact， all of the winners in W had are justjoint， but in particular。

 the ones that dropped out in iteration are。Of algorithm。A dis joint， so this is a feasible solution。

Chen。So now by greedy。 So now we finally use the fact that we're running the greedy algorithm。

So the output of our greedy algorithm is just all the bidders that one in our auction and their bids。

And by the guarantee we began the lecture with with a factor D loss。

This is at least as large as the sum for any other feasible solution。

 this is the feasible solution we're going to use。Okay。Now， all right。

 So because these bidders drop out in this iteration， what do we know， right， So， well。

 one one of our behavioral assumptions is that you don't drop out until you're asked a bit above your value。

So if these guys are about to drop out， it means their bid is almost as high as their value。

 guys at least half their value if they drop out in this iteration。

So this is again by one of our behavioral assumptions。Sorry， that should be a V。是。

So this is the first thing， Any questions about that？So this is just， we envision running greedy。

 not in the way we actually run greedy， but with these smaller sets that doesn't actually change the output of the greedy algorithm。

 and then with respect to a collection of these that are a feasible solution。

 we can lower bound how well we do with respect to how well that feasible solution would have done okay。

All right， so。嗯。Good。All right， so let's see。So this is the some of the bids of the output of our greedy algorithm in this one iteration R。

By construction， something I've enforced in this shrinking mechanism is that first of all。

 in a given iteration， whatever you compute with the greedy algorithm。

 if it's not better than the last iteration， then you throw out the new greedy computation and inherit the previous one。

 And if you think about it， that means every single iteration of this auction has a better allocation than the previous one so sum of the bids of your winners is only increasing over the course of this auction。

So if this is the sum of our bids right now with the conclusion of our greedy algorithm。

 the sum of the bids of our final allocation is at least as large at the end of the shrinking auction。

So it end。Of the shrinking auction， some of the bids is at least this and hence at least this。

And by our behavioral assumption， bids are always a lower bound on the values。

 Like you're never going to stay in after the bid exceeds your value。 So the sum of the welfare。

 sorry， the welfare at the end of the。At the end of the auction。There's at least this amount。

And this is true。For every iteration R。Okay。Have with me。O。

So all I did is I put a few things on the left here that were even bigger。

 So the some of the bids of the auction keeps getting bigger and bigger and bigger。

 and the welfare is， at least some of the bids。And that's where ititeration are。

So now let's sum this inequality over all capital art iterations。

So if I sum this over all capital art iterations， I get everybody who ever dropped out。 Okay。

 and who also won。 Okay， so of all the winners of W hat， I get everybody who ever dropped out。

 if I sum this over all iterations or R。And right， and so the people who didn't drop out are winners in our auction。

 So I can just add that in again on both sides。And so R so again。

 just there's capital R inequalities of this type。 I'm just adding them up。

 and then I'm throwing in all of the people who want in both auction。To get this。

Is at least1 over 2D。Some over all of the winner。O。And this is just opt。So that's number two。

Any questions about that？The thing， the thing worth pointing out is how the third behavioral assumption that people shrink when they have no other options is what allowed us to apply the D approximation for the greedy algorithm in this part of the proof。

 That's kind of the only part of this proof that's important。

The first two behavioral assumptions just basically let us say we can exchange bids and values。

 basically just says people are being truthful up to a factor of 2。On their values。

So the third one is used here。O。Then， let's。Let's just do limit3。So let me remind you what limit3 is。

 so in limit3， we say we don't throw out too much welfare by restricting people to just the final sets S hat I。

 so the miscoordination is bounded by how much the damage is。So。

What we're trying to prove here is that。Opt hat， well， it is going to be smaller than opt。

It's not going to be too much smaller than opt。Again again， capital R is the number of iterations。

 This is the real maximum welfare。 This is maximum welfare。

 If people are only allowed to get items from their final sets as hat I。Okay。So why is this true。

So let F subbar。Be the。First time shrinkers。And iteration R。

So we recall that from a bidder's perspective， there's this phase in the auction where you've never shrunk and your set is all goods。

 Okay， none are ruled out。 And then at some point for the first time。

 you commit to a set of at most de goods。So I'm saying what R。

 consider in R the bidders that shrink for the first time in this iteration are。Now。

 there'll be some bitterders that maybe never shrink。 They just get， know they just。

 never actually shrink and they just lose in the auction at the end of the day， okay。So， F 0。

Is the non shrinkers。So here's， here's the really sneaky point in the proof of Lima 3。 this is nice。

So observation。Consider two different bidders。That shnk for the first time。In the same iteration R。

Okay。The claim is that the bundles that they shrink to in this iteration have to be disjoint。

So here I'm only claiming that their bundles at the end of the auction are disjoint。

 but something stronger is true， actually。So if you look at it。When you shrink the first time。Okay。

 let's look at what has to happen， right， So initially your SI is just all goods。

To be eligible to shrink。The subset T I you provide me has to satisfy several criteria。

 has to have size at most D。And it has to be disjoint from the bundles I've already allocated in this iteration。

Okay。So if you don't ham you're good at that type， it doesn't count as shrinking。So to shrink。

 you have to be able to avoid the bitterders that have already been allocated by the greedy algorithm in this iteration。

So if two different bidders successfully shrink for the first time in exactly the same iteration。

 which everyone was second， had to shrink to a bundle disjoint than the first one because the first one's already been allocated。

So in iteration R， their bundles have to be disjoint if theyre both shrunk。 and then， of course。

 bundles will only decrease。 So they're disjoint at the end of the algorithm。So that's really cool。

 All， So each iteration goes by。 There's some set of bidders that shrinks for the first time of this iteration。

 And therere a legitimate partition of the items。 No overlaps between first time shrinkers in a common iteration。

😊，Okay， good。So now we're pretty much done with WB， the winners。And the real optimal solution。

so these guys have S I equal U。So， claim。So okay， actually the simpler one is this， right。Remember。

 Op hat is sort of the max revenue you can get if you only give people items from their final sets S hat I。

Well， what did you say in the given iteration R， all of the first time shrinkers form a partition or no goods are in common。

 so you can actually simultaneously allocate to the entire collection F sub R。

 a first time shrinkers of iteration R。Okay。So that means one feasible solution determining opt hat is just to have every all the first time shrinkers from FR being winners。

Of course you could possibly probably do better， but this is one feasible solution。

So this is for all R。It's also the case。If you look at the people who never shrank。

And you look at the ones that。Are winners， right， So these are somehow the easy guys。 F sub 0， right。

 So they never shrank。 So you're literally allowed to give them any item at all。 right。

 So in this case， youre restricted optimization， you're not restricted。 You can just do whatever。

 And so for these bidders， you can basically just copy opt。Okay。

So if you look at the nonshers who win in the optimal solution because they're in the optimal solution。

 they also have to be disjoint， so they're also a legitimate feasible solution for the restricted problem。

And so then。If you just add these up。On the left hand side， you get r plus1。Times the restricted opt。

And then over here you get something which is a super set of the winners in the real optimal solution。

 right W， the winners in the real optimal solution， here we pick up the nonshers。

 here we pick up all of the shrinkers， whether they're in the optimalti or not。So this is at least。

So that's number3。So again， remember capital R is the iteration count and that's log V max。

 so we lose one log v max and lemma 3 and then we lose the d times log v max and lemma 2 so putting them together。

 we get the loss of d times log squared V max。So we don't know what bidders are going to do。

 We don't know when they're going to double。 We don't know when they're going to shrink。

 but under minimal conditions， you get an approximation for this problem。

 We don't know how to get with the D signal。So questions about that？So。Like I said。

 it' would be cool to have more mechanisms of this flavor。Right now we don't。All right。

 so what we're going to talk about next is a much more sort of standard notion of relaxed incentive compatibility。

Baasian incentive compatibility。And today， we're mostly going to spend time just kind of laying the groundwork。

 So stuff I could have covered in 364 A， but decided not to， decided to postpone till now。

So at a high level， the idea okay。 So so if we want to move beyond dominant strategies and sort of slight relaxations。

 like I just showed you， like this is really key conceptual problem， which which comes up， which is。

 you know， when there isn't an obvious thing to do and when your best response depends on what other players are doing。

 how do you compare the different options。 So how do you reason about how to respond to other players actions when you don't know what people are doing。

So the solution to Bayesian incentive compatbilities is we're going to assume prior。 Okay。

 so as a bidder， the assumption will be that you don't know exactly what people want。

 Like you don't know their valuations， but you least know a distribution over what people want。

 For example， their valuations。And if you assume you know both a distribution over evaluations and you also assume you know strategies。

 mappings from valuations to actions， then you can think about best responding to the distribution over actions that you face。

 And then you can have an equilibrium concept and a corresponding notion of incentive compatibility。

So let me elaborate。So the general setup is pretty much。 So the first few things I'm going to say。

 we already discussed formally when I talked about X post incentive compatibility。

 X post Nash equilibriumlibria， way back in lecture 1。So。Each player has。

What's called the type space。 Just think of types as being valuations。 Okay， for this class。

 same thing。So this is the private stuff where you don't know。Okay， so capital T sub I， you know。

 these are all the possible preferences a bidder might have。And then。

 but you don't know which one they are。And then there's an action space。For example， bids。Now。

 we've been talking so much about direct revelation mechanisms。

 one sometimes forgets that these two things could in general be different， right。

 So in something like you know， just a second price auction， both of these are the same。

 valuations and bids both have exactly are drawn from exactly the same set。

When we were talking about indirect mechanisms， asending as。

 that was a case where the action space was way bigger than the type space。

 right So we talked a little bit about how the action space is very rich in indirect auctions。

 And that's why you sometimes have to settle for x post and compatibility。

 not dominant strategy and set of compatibility。 Remember there it was iterative。

 So what you do next could depend on the entire history of actions。 And so in particular。

 we saw that there are ways that bidders could behave that were inconsistent with any valuation。

 So actions that didn't really correspond to a private valuation。

 So that was a case where there are way more actions than there were types。

 The next part of the course was going to be the opposite。

 We're gonna be looking at as where the action space is very small and you don't even have enough。

 don't you don't have the means of communicating your full valuation。

 So maybe you have two to the in private sets， but it'll ask you for only M numbers。

 So when we talk about the price of anarchy you have simple as。 AI will be much smaller than T。

So for direct revelation mechanisms， these are the same set。And a strategy just specifies， you know。

 as a function of what you want， what are you going to do。

 was just the mapping from types to actions。And these can also be randomized。

 These can be a mixed strategy。 So I really should write distributions over actions here。Okay。

So what are some examples。 So when we're talking about X post incentive compatibility。

 we were talking about sincere bidding being an example strategy。

 which would just say every time you're given a query，'ll ignore the history and just， you know。

 tell the truth with respect to your evaluation。Direct revelation。

 That would be an example of a strategy。Yeah。So direct revelation just corresponds to sitting sigma。

I of T equal to TI。Okay， so just truthfully reporting your private information。OK。So now， right。

So the relaxed notion of incentive compatibility rests on a relaxed solution concept。

 equilibrium concept。Which for the first time in this course involves a prior。So in 3，64 a。

 we did talk about priors in revenue maximization。 But that was a little different because that were really only using the prior to measure the performance of an auction。

 Okay， so something like， you know， Myson's second price auction with a reserve。

 We talked about the expected revenue of the auction。 But were always talking about d mechanisms。

 Second price auction with a reserve。 It's still a dominant strategy to report your true valuation。

 You're not reasoning about what other people are doing。 so that's the difference here。

 The prior a should be used by bidders in deciding whether to take action A or action B。

So common prior。So there's some common knowledge publicly known。Distribution。Capital F。

On the type space， or evaluation space。So we think of bitterders types or bitters valuations as being drawn by nature。

 say， from a distribution。We're mostly only going to talk about the special case where F is a product distribution。

So that is where if I tell you something about one person's type。

 it tells you nothing about anyone else's type， doesn't change your conditional distribution for other people。

It's not， you know， the general correlated case is interesting and relevant for lots of applications。

 but it's there's a lot of pathologies that come up and you allow correlated distributions。

 So for a lot of the analysis， you just wind up learning a lot more by focusing on the product case。

 the prior the。The independent case。Okay， so。So what's a Bays Nash equilibrium？

So based the base national equilibrium just says， you know， every bidder based on what it knows。

 based on its information at the time is behaving optimally。 Okay， So then the question is， okay。

 so what is， what does a bidder know at a moment is taking an action。And so the assumption。

 I'm going to write it down formally。 But okay， so what do you know as a bidder。 Okay。

 you know the distribution over types。Okay。You know your own type， you know your own valuation。 Okay。

 so at the time you're choosing what to bid， you know what you're willing to pay。

And then the assumption is also going to be here that， you know， players strategies。

 this is the same thing as the X post national equilibrium。

So I'm not going to assume that I know someone else's evaluation。

 but I'm going to assume that I know they're mapping from their valuation to their action。Okay。

 so if I knew what they wanted， then I would know what they what they're doing。可。So。

A strategy profile。Sigma 1 of the sigma n is the Bayes National equilibrium。If。For all I。

And valuations V I。 So this is the moment in which I is reasoning about what its sort of best decisions are。

It should be that。The action that a strategy tells it to take。Maximizes。Ayes expected utility。Okay。

So what is his expectation over？So it's reasoning as if other players types。We're drawn。From F。

Conditioned on VI。So if types are independent， then conditioning does nothing， right。

 So I learn my value。 I learn I'm willing to pay 10 bucks。 Okay。

 so if the model is that the types are independent， then， you know， it doesn't matter。

 It doesn't tell me anything about other people's distribution。 If it's correlated。

 then I'm going to update on that information。 Okay。

 I look at the conditional distribution of those types given my own。So I'm gonna， in my reasoning。

 I'll think of V minus I as being drawn from this distribution。 And then。

 and then I will assume that others play according to the strategies， in the strategy profile。Okay。

So assuming others play。Sigma minus I V minus I。Okay。

So the fact that I know a distribution over others' valuations and I know their strategies。

 I'm then faced with a corresponding distribution over actions。

 and I can reason about my best responses with respect to that action distribution。All right。

 so I'll do an example in a second。 Let me just sort of compare and contrast this to the other equilibrium notions we saw for games of incomplete information。

So x post Nash equilibrium。Was stronger， more stringent。 In particular。

 We didn't have a prior when we defined exposedos N equilibrium。 We didn't need one。

 So Exp post N equilibrium， we were saying that the action。

That I' is about to take should maximize its just utility。Assuming nothing about V minus I。

 V minus I was arbitrary， assuming only that other players play according to the strategies。

 Sigma minus I。 For example， sincere bidding is the best response。

 assuming only that other players bid sincerely， whatever their evaluations might be。

So Xos Na equilibrium said， you know， valuation profile by valuation profile。

 this is the best thing to do given sigma。 here we're saying on average over the v minus I。

 this action is the best thing to do。 Of course， that only makes sense with a prior。

Even stronger than next post NA equilibrium is dominant strategy equilibrium。And that says。

What your strategy is telling you to do is a best response， no matter what other actions people take。

 whether or not they're of the form sigma I v minus I？So for Xpost na equilibrium。

 you at least have a notion that there are these strategies that people are using。

 you don't know the input， but at least you know the mapping， dominant strategy equilibrium。

 all you don't even know that， you just say whatever the possible action might be。

 this is what I want to be doing。So for direct revelation mechanisms， as we discuss those coincide。

 but when you have these richer action spaces， sometimes you can be exposed。

 you can exposed national equilibrium， which are not dominant strategy equilibrium。

So that's the key idea here， best responding with respect to the distribution of reactions that you face。

 given all of your information。Okay， so let's， let's get much more concrete。So for example。

Let's just look at a first price auction。Two bidders。ID distributions。uniformform 01。Okay。

I may have made you do this as homework last quarter。 I forget， but let's just review， anyways。Okay。

 so this is a product prior。First price auction， no dominant strategies。

So the claim is that bidding half your value is a base national equilibrium in this setup。So， good。

And so the Bayes natural equilibrium depends on the setup。so if instead of two bidders。

 there were n bidders， then you would multiply your value by n minus1 over n。

So as the number of bidders increases， the amount by which you would shade your bid is getting less and less and less as it gets more competitive。

 your bid will drift closer to your value。If even with two bidders， I change the distribution。

 that would change the base na equilibrium。 Okay， would look different。 be some other function。

All right。So proof。Consider EG player one。It's obviously symmetric。

So we have to show that no matter what player one's valuation is。

 bidding half its value is the best thing for it。So， fix V1。So we said that， you know。

 from a bitter's perspective， when you're reasoning about what to do。

 given a distribution of others' values and knowledge of their strategy。

 it gives you a distribution of actions。 So in this context， even though Bi 2 in its mind。

 it's playing deterministically。 If I'm bitter1， it's like it's acting randomly。 right。

 So nature draws this value V2， uniformly from 0，1。 and whatever that is。

 I know it's bidding half its value。 So to me， I just see this bid B2， which is uniform in 0，1 half。

And that's what I reason about with how to bid back。So， fix V1。B2 is distributed。Like zero1 half。

And this is， again， because， you know， we're thinking of the strategy profile as known when we do these computations。

Okay， so expected。Utility。Of a bid B。Biwen。Well， it's just how much money。

 what would be your utility if you won。Times the probability that you win。So this obviously。

 is you bid high。 remember's the first price auction。 So that's why， you know。

 this is your value and you pay what you bid when you win， okay， first price auction。

So this is obviously getting smaller and smaller。 The higher you bid。

 And this is obviously getting bigger and bigger， the more you bid。 Okay。

 so we're sort of looking for the optimal trade off between those two。

So what's the probability that we win？Well， so this is just the probability of that our bit is bigger。

And thinking of B1 is fixed and B2 is random。呃。So B2 is half of V2's valuation。

So this is just the probability that V2。Is less than double what we bid。Which in turn。

 because V2 is uniform 01， this is just 2 be1 or can't be bigger than one。Okay。If you think about it。

 it's sort of obvious， like， why would you ever bid more than a half。

 given the other person's maximum bid is a half。 So let's just think of B1 as being a most a half。

And so， then。So again， we're thinking so B1 is the variable we're solving for。

So the expected utility， v1 minus B1。Times 2， B1。Is uniquely maximized。At B1 equals v1 over 2。Okay。

 which is what we wanted。So it's just once you guess these things， then you just check them。Okay。

So that's an example of a Bays Nash equilibrium。So just looking ahead a little bit， so you could ask。

 I mean， just so to preview some stuff。So you can say， okay， so what's the expected revenue， I mean。

 you might want to ask questions in auction design。

 you might want to ask questions like which is better or first price auction or a second price auction。

 Does one make more money than the other。So， you know， you could start just with a simple example。

 you know， which is better。 first or second price auction。So in the first price auction。

 the good news is is the money you make is the higher bid。Whereas in a second price auction。

 the money you make is the lower bid。So that would seem to favor the first price auction。

 you get the higher the two bids。On the， like in the second B auction， they're going to be truthful。

Right so in the second rise auction， your expected revenue is just the actual value of the is just the second highest is the smaller valuation。

 Okay， which is the same as small， the smaller bit。

So if you have two valuations drawn uniform from 01。

 then the expected minimum of those two samples is a third。Okay。And a first price option， right。

 so now you get your revenue is the expected higher bid。But the bids are only half the value。

 So your expected revenue was one half times the higher value。

And the maximum of two IID samples from uniform 01 is2 thirds。

So your expected revenue is one/ half times two thirds， also a third。Okay so second price a。

 first price auction doesn't matter， you get a third either way。

So the more aggressive pricing in the first price auction is canceled out by the less aggressive bidding by the bidders。

And we'll see that's actually a completely generic property。

 So basically any two options whose allocations are the same in equilibrium have exactly the same expected revenue。

 That's known as the revenue equivalentvalence principle。

It's not really kind of going to be the main point of what we're discussing but。You know。

 seemed worth mentioning。Okay， so questions。 So that's kind of just some very， just some basics。

About Bay's National equilibrium。All right， so。One way to think about what we were shooting for in the previous parts of the class is we wanted mechanisms with good equilibrium。

 you know， equilibrium with Ne optimalmal welfare， where the equilibrium we can find ourselves to were these very strong ones。

 dominantant strategy equilibrium exposed Nash equilibrium。 So now we just want the same thing。

 mechanisms with good equilibrium。 where equilibrium notion is based Nash equilibrium。 Okay。

 which is a weaker notions。 So it should be easier to get positive results。So a new goal。Design。

 simple or poly time mechanisms。So in the simplest case， it an allocation rule X， a payment rule P。

Such that there exists a bays Nash equilibrium to the sum prior in the background。

So Bayes natural equilibrium， Sigma1 up to sigma N。With near optimal revenue。O。And so now。

 when we have a prior， when we talk about things like near optimal revenue。

 just like when we talked about revenue maximization last quarter。

 we're going to measure the expected welfare of an auction。

 just like we measured expected revenue of auctions in Myathton's theory last quarter。So。嗯。

So basically， we just want to say the performance of our mechanism。

Is almost as good as the performance of some optimal solution。So。

The optimal solution is just opt welfare。For the valuations V， so again， the input is random。

 the valuation profile V is random drawn from the prior for a given valuation profile。

 there's some maximum possible revenue， so we're just looking at the average maximum possible revenue over that prior distribution。

And then our protagonist is some mechanism and some bayes na equilibrium in that mechanism， okay？

So so in this context。We're just going to look at the contribution to the welfare by each of the bidders I。

And then。Their value for whatever allocation they get。Okay。So what do we do here。

 we draw the evaluation profile from random， We look at the strategies employed， like for example。

 the bids， this could be a first price auction， So this would be you draw these random valuations。

 this would be you look at the bids given bidders valuations this would say look at the allocation defined by those bids and then this just says look at the welfare of that allocation and this just says average how well you're doing over all the possible inputs okay。

So this is our new mechanism design goal， and we want mechanisms that have good bayes nacha where this is what good means。

Okay。Al right。So。One thing that makes our lives a little simpler。

That also made our lives simpler in the decentit case， is we have a revelation principle。

It's a little less satisfying。In the Bayes Nash equilibrium case， but we'll still use it。

At least for a little while。So the claim is， if oh， the claim is， oh， if this is what you want， well。

 then forget about sigmas。 Okay， so a very special kind of strategy is the direct revelation strategy。

 Okay， which is just， oh， if my value is V I， I just report V I。 Okay， that's a really simple sigma。

😊，And so the claim is， whenever you can get a statement of this form with any mechanism with any Bayes National equilibrium。

 then there also exists a mechanism of this form where it's just direct revelation and the Bayes National equilibrium is truth telling。

So that lots of generality。Can restrict。To direct revelation。Mechanisms。

And requires a sigma of V equal V。And so， you know， once。

 at least once I wrote down this sort of relatively complicated formula for an arbitrary mechanism。

 an arbitrary basis equilibrium。 Henceforth， at least for this， you know， the next couple lectures。

 there will be no sigma。 It will just be understood that Sigma is the identity function。

 People are just doing direct revelation。So the proof of this revelation principle is the same one as the other。

 So I'll leave it as。As an optional exercise， so I'll just say similar simulation argument。

So you know， remember the way the Re principle works， you know。

 if you have some mechanism and you have some equilibrium in it， you put a wrapper around it。

 and then you just ask bitterders， well you know， tell me what your actual valuation is。

 and I'll just play an equilibrium on your behalf in the old mechanism。

So like in the first price auction example， it would be you'd put a wrapper around the first price auction and you'd say tell me what your actual value is。

 tell me your willingness to pay and then you would just promise to bid half of that in an actual first price auction inside the simulation Okay so bidders just truth tell and then the sort of intermediate layer implements the basees NA equilibrium。

Good。And so this is what's called。And so as far as so we've had D E， these are bigic mechanisms。

 Bayesian incentive compatible。Okay， direct revelation is a based N equilibrium with respect to the prior。

So the new set of goals is big mechanisms that are simple in polynomial time and have welfare as close to optimal as possible。

I want to mention a caveat of the revelation principle。The Bays Nash version。Which is， you may lose。

The simplicity。In various senses of the word。Of the original mechanism。Let me give you two examples。

 so one example will be very relevant for the next part of the course。

 so I mentioned we're starting next week or the week after we'll start looking at options where the action space。

 the bid space is way smaller than the type space， so you might have some very rich sub modular evaluation for example。

 but'll only ask you for say like M numbers， not two of the M numbers。And so then if you。

 but whatever， you could have a base natural equilibrium in that kind of mechanism。

 But then if you apply the revelation principle， it says， okay。

 now tell me all of your two to the M numbers。 and I'll just bid on your behalf in this original mechanism that just has very small communication。

So that's silly。 I mean， that sort of defeats the whole point of designing mechanisms with low communication。

 So we'll ignore the revelation principle in part 4 of the course for that reason。

Here's a second example。So last quarter of the 364 a。

 we very briefly mentioned the notion of prior independent auction。

 So the context was we were talking about revenue maximization。

 We sort of complained that optimal options depend on the prior。And so we asked。

 could we ever have single auctions which are almost optimal for a ranger prior simultaneously？

And we did something called the Bule Cpper algorithm， which showed how you could。

So if you apply the Re principle in a Bayes Nash setting。

 you can take something that is prior independent， and then this will give you back something which is not prior independent。

For example， think about a first price auction。Okay。

For me to write down the description of a first price auction。

 I do not need to know any distribution。Okay， I just say winner pays its bit。

 that's the whole description。 So it's a prior independent a in that sense。But as we discussed。

 the actual Bayes Nash equilibrium of the first price auction。Does depend on the distribution。

 So it's somehow like the bitterder's problem to sort of deal with the distribution and figure out the equilibrium。

 It's not the mechanism designer's problem。And the revelation principle will kind of flip that。

 right， So I said， if you apply the revelation principle to the first price auction， what happens。

 basically， the mechanism will now say， tell me your true value and I'll bid half your value。

But when I， I'm， how do I know to bid half your value， it must be that I know the distribution。

 I know the right thing in the Bayesastic equilibrium is to bid half my value。

So if you apply the revelation principle， the first price auction。

 you take something which is prior independent and turn it into something which is not。

 and often that's not what you want okay。But at least for the time being， next。

 for the rest of today and for the next lecture， we are going to focus on just these truth telling being a based national equilibrium。

行。All right。Any questions。So， the new goals。For the moment。BIC。The opt welfare。Simple polyt。

And the hope is， we can do much better than with DS S I C。Okay。

 but I haven't given you any evidence about that yet。And so as usual， you know。

 getting all of one through  three is only harder than getting2 and three alone。

 So the holy grail would be whatever we know how to get for2 and 3 alone， we can add in number one。

Okay， and we just get it for free。 And actually， we sort of have results like that。 Okay。

 and that's what I want to spend the rest of the today today a little bit about。

 And then all of the next lecture talking about basically。

 black box reductions that take solutions that solve just 2 and 3。😊，And then output。

 so just take a good approximation algorithm and output a good B approximation mechanism。

 It has been some really nice successes in just the last three to four years about those kinds of results。

So， holy Gil。Given a good approximation algorithm。For two plus3。Extend to a bit。Mechanism for free。

And so once we see these results， it'll be clear， you can get much more sweep and positive results with baesian acidtic compatible compatible mechanisms than you can for die mechanisms。

We did we have nothing。 I mean， the discussion at the beginning of today。

 the separations for some modular evaluations was meant to indicate， you know， we do not。

 not only do we not have this， we cannot have this for dominant strategy incentive compatibility。

 Okay， so it's a real separation between the two flavors of incentive compatibility。Okay。All right。

 so。If we， if this holy grail was going to be provable， how would we go about it。

 What would be the plant。 Well， so here would be if we were really lucky， his would be really lucky。

I if literally。You know， any allocation rule， just， you know。

 so give me your favorite approximation algorithm。 I'll just define suitable payments so that I get a big mechanism。

 In other words， what would be really easy is if every single allocation rule suddenly was implementable in the Bayesian sense。

So the first question we have to understand。 And again。

 this is totally parallels work we did with dominant strategy mechanisms。

When can an allocation rule X？When is it implementable？

So this is the first thing we have to understand。And so， this is。This is well understood。

 I want to keep things simple today。So I want to assume。For today。

That we're all interested in single parameter problems。嗯。So let me remind you what that means。

So that means the allocation rule is very simple。It means basically there's just stuff。

 there's sort of one commodity， and the allocation is just how much stuff a given bidder gets。Okay。

 so the allocation rule just spits out single dimensional non negative numbers and then the utility of a bitter I is just defined as its value per unit of stuff。

 This is its only private parameter。Times the amount of stuff it gets， minus whatever it has to pay。

你承认。So we have not。Been had the luxury of working on single parameter problems much of this quarter。

Of the last quarter， most of what we did was single parameter。Okay。Alright， yeah， also。

I don't want to mess around with any correlated priors。 So F is a product。Prior。

So that's what I want to talk about for the rest of today。Allright， so。

We did this once before in the context of dominant strategy mechanisms。

And we had something called Myerson's lemma， which explained exactly which allocation rules X can be turned into DI mechanisms。

 It was exactly the allocation rules that were monotone。 So for every fixed bid or I。

 for every fixed reports of V minus I by others， the amount of stuff you get should be increasing in what you bid。

So there's a。Extended Myerson's Lemo。I mean， this is， in fact， the version that Myerson proved。

But we need more the greater generality now。And so this is something totally analogous。

 The only difference is going to be instead of obsessing over these allocation rules for every single fixed V minus I。

 we're only going to look at what are called interim allocation rules。

 That is we're only going to average over the amount of stuff you get Averaging over the V minus I of the others。

So。So this is a definition。So an allocation rule the way we've normally been thinking about the way it's normally defined。

 it takes as inputs。A bid from everybody。 right， So think of it just like a second price auction。

 something like that。 right So the allocation will takes a value from everybody so that you know whether I is the highest or not。

 whether it wins or it loses okay。So when you have a prior， when you have an F。

 we can define an interim allocation rule。Which takes his input only the bit of bitter eye。

And then average is over everybody else。Okay。So like in a second price option。

 this says if you bid 10， what's the probability that you win？When I draw other bids at random。

 sometimes you'll win， sometimes you won't。 This will be between 0 and 1。

 And it's the fraction that you win。 And then something like a second price auction。 Obviously。

 the more you bid， the more frequently you'll be the highest。

 the more frequently you'll be the winner。So that's called the interim allocationloc rule。All。

 so by definition。So you average。And so again， you， I'm omitting the strategies。

 I'm always thinking about just the truth telling equilibrium。

And so I just look at the expected amount of stuff you get。OK。So this is what we're given。

 this is the allocation rule， this is the induced interim allocation rule。 okay。

 that takes only one argument， and then it just pads it out by averaging over the v minus I。看。Okay。

And you know， so just like with randomized mechanisms here again。

 we're gonna be thinking of risk neutral bidders that only care about their expected utility。

 And if you think about it， like from my perspective， this is all I really cares about。 know。

 So I just want to know in a single item option， how frequently will I win， It be 60%，70%。 What。

 I don't really if I'm risk neutral， I don't care about the distribution leading to that ultimate winning probability。

 I just care about the winning probability。 That's what this is just cuts to the chase。

 If you bid this how frequently will you win。O。So， right， So what does thelemma say， So this， again。

 will characterize allocation rules or actually more precisely interim allocation rules that are implementable that can be lifted into a big mechanism。

 okay。So， then。There exists。Okay。A Bayesian incentive compatible mechanism， X P。 again。

 we're given X。 The question is， is there a payment rule P so that it's a Bayesian incentive compatible mechanism。

If and only if。The interim allocation rule， this is meant to be the interim。

It's only write it this way。X I VI。Non decreasing。For all I。So that's the first part of thelemma。

So this again， is characterizing which allocation rules。

Can be made based in compatibleat in which cannot not。 Okay。

 The characterization depends only on the interim rules， because， again。

 that's all the bidders care about。Okay， so two different mechanisms that have exactly the same inter allocationloc rule。

 Either they can both be made B， I C or they both can't be made B。

 I C because the utilities faced by the bidders are the same， whichever one you use。Okay。

 so how does this compare to the original Mas limo。When we want a dominant strategy in seatibility。

 the original one said something very similar。 The difference was as it said for every I。

 for every V I， for every V minus I。The allocation that I gets is non decreasing in its bid。Okay。

 so it was point wise over the valuations of the other bidders。 Here。

 we're just saying your allocation should go up on average over the V minus I。So certainly。

 if you are monotone in the sense of the in the D6 sense， your monotone in the sense。 Okay。

 so if the allocation only goes up for every single v minus I it's certainly true。

 on average over V minus- I。 But the converse， you know， you could imagine cases where it's not true。

 Okay， where this is more permissive。Which is what we want。

 but really hoping there'll be a richer space of mechanisms so that we can get more positive results。

 That's the whole point of this exercise。Alright， so this is clear。We should be happy with this。

 I mean， this is something， you know， this feels like， you know， something we can use。

 You know what I mean so。😊，All right。So interim allocational monoity is necessary and sufficient for big implementability。

 And in this case， again， there's a payment formula。 I mean。

 we're not really going talk about revenue maximization until maybe the last week。

 So this isn't so relevant， but just。For completeness。

 the point is that given the interim allocation rule， the expected payments are uniquely defined。

 This is the same thing we had last quarter。 Okay， the allocation rule uniquely determines payments here。

 it's exactly the same thing。 Its uniquely determines payments up to their expectation。 or sorry。

 it uniquely determines expectations of payments。So in this case。

 if it is monotone in the interim rules。P must satisfy。The expected payments that a bidder makes。

 and again， notice， you know this is all that a bidder cares about。

 just wants to know know what's the expected payment it makes for a given action。

So this has to be equal to exactly the value， times sum formula。That's really all that matters。

This is the same formula。嗯。That we had in the dominant strategy tank part of the case。 Again。

 the only difference is last quarter， we had a V minus I。

Instead of having an expectation overview a minus I， that's the only difference。Okay。

The proof is very similar to the De case。 I'm not going to do it here。 Okay， so basically。

 all of you could just go back to the notes for the De case and rework it for the。

 for the bit case here。But as the statement makes sense。Any questions about what it says？And again。

 so why should you be interested， the point is。You know。

 something we've been facing all along this quarter is， you know， okay。

 you have some great idea for a mechanism。 Is it actually instead of compatible。

 How do you actually prove that。Okay， it's like with all this multi parameter stuff in part 2。Yeah。

 we had no idea。 We had to just all we did were sort of variants of VCG because we had no tools for sort of asserting the mechanisms for incentive compatibleat。

 So the point is， you know， this， we're back in the single parameter world。

 But now we have sort of again， you know， something we can imagine using。

 We can imagine writing down a mechanism and being like， look， everything is monotone。 Irgo。

 This is a ba c compatible mechanism。 Irgo， Here's our positive result。

 Okay So that's why you should care about this。All right。Alright。

 so what I want to do in my remaining time is kind of， So like I said，'s。

 what's cool here is we're gonna get some really sweeping， positive results that really say for。

 you know。😊，Lots of problems， you get one for free， okay？So in the rest of my time today。

 I kind of want to you know， set up the methodology by which we'll prove those sweeping positive statements Okay the details will wait till next week。

Okay。So， oh， right。 So just one obvious corollary。So the really amazing thing perhaps would have been is if actually。

 you know instead of part one。It had just said。You know， for every， for every inter allocation rule。

 monotone or not， there exists a big mechanism X comma P， right， then we'd be done。

 If it were true that any allocation rule could be made a mechanism， then you know。

 we'd have the sweeping positive statements that we want。 It would be just be sort of trivial。

 You design a good approximation algorithm。 There's someone used allocation rule。

 If I had some theorem that just automatically gave me the payments under no further assumptions。

 I'd be done。So while this is good news in that it gives us a very clean understanding of what's implementable and what's not。

 not everything is implementable。 Okay， so again， if you take like some crazy allocation。

 will like the second highest bidder always wins， you know。

 that's not going to be monotone for almost any distribution you might think about。😊，So again。

 it says only special approximation algorithms are going to be able to be fed into the extended Marison'slemma and extended to mechanisms。

 Okay， so we somehow need to figure out how do we design approximation algorithms that are monotone in this interim sense。

😊，So not all allocation rules。Are implementable。So really， as for a sweeping positive result。

 we're hoping for something that says， like， if there is any alpha approximation algorithm。

 then there exists an alpha。 There also exists an alpha approximation algorithm。

 which is monotone in the sense and therefore implementable。And just quickly。

 the reason that's not totally crazy。Is remember， kind of every， like with elasticity。

 everybody's on the same side。 We want to maximize welfare。

So we want to give stuff to the people with the highest valuations。What does monoicity say。

 it kind of says the higher someone's value， the more stuff they should get。

So these seem like very well aligned， Well maximization and monoicity。 And in fact。

 if you do exact welfare maximization， as we know well， your monotone， even multi parameter of V C G。

 works perfectly well。So it's not crazy to hope even for approximation algorithms。

 maybe if it's not monotone， you can monoetize it， maybe even make it better along the way and then get a corresponding mechanism。

So that's sort of the paradigm we're gonna be， we're gonna be exploring。So。

What I want you to think about for the moment。So suppose we have a decent approximation algorithm for some。

 say， MP Hard welfare and maximization problem， but that' single parameter。For example。

 the canonical one that I used last quarter was Napsack。Okay， so imagine you have these bidders。

And they're a single parameter they just want to win。

And the constraint you have on which bidders you're allowed to allocate to。

 they all have some public size， okay so some bidders have size one， some bidders have size two。

 some have size three。And the feasibility constraint is that if you look at the bidders that you allocate items to。

 the sum of their sizes has to be bounded by some capacity， you know， like 10 or 20 or whatever。

 Okay So that's the Napsack welfare maximization， That's the Napsack problem。

 So with the valuations corresponding to the weights， the prizes。So that's NP hard。 So VC G。

 you know， you can't polynomial time。 And so what we did last quarter is we said， well。

 let's look at approximation algorithms and let's make the monotone。 greededy was monotone already。

 So that was a two approximation。 And then I gave you homework， which said， you know。

 the one minus epsilon approximation is not monotone。

 And then the homework asked you to tweak it so that it was monotone。 Okay。

 so that's the kind of problem I want you to have in mind right now。 Okay， single parameter。

 but N hard。 So we need to do with approximation algorithms。Okay。

So let X be the induced allocation rule。Okay， so you have some NAPS auristic。

 you run it on some valuation profile， and it tells you who wins and who loses。

 and that gives you an allocation rule。Allright， so if。The interim rules。

 And suppose there's some distribution。 Okay， so we're in the Bayesian world。

 So there's some common prior F。So the interim rules are defined with respect to that distribution。

 If the interim rules are monotone。Then of course， we're done。that's the happy case。

 you have a heuristic for which with respect to the distributions。

 you have monotone interim allocation rules， you apply the extended Marison's Lemma。

 you have your payment rule， you have your big mechanism。Okay， you're done。So， that's the happy case。

And the question is， is there some generic way of taking non monotone approximation algorithms。

 allocation rules and making the monotone。Okay， a monetizer。That's what we want。And again。

 it's not crazy because somehow， you know， nonmontononicities are kind of only hurting you with a welfare。

 Okay， for some reason， you're giving a smaller value more allocation than a larger value。

 That's what it means to not be a monotone。So inverting non monoity should sort of help with both your welfare and with the incentives。

So we're going to be able to do this。And so I'm going to sort of tell you the high level approach。

Now。And then。More details next week。So here's how we do this。It's very clever， actually。

So we're given an allocation rule， it's like some approximation algorithm。

And we know our common prior capital F。And we're going to design polynomial time algorithms。

 which I'll call resampers。One for each bidder， so n is the number of bidders。

So what are these resampers？These are going to take。

Evaluation of a bidder and remap it to a possibly different valuation。Okay。

And then we're going to feed these new valuations into the approximation algorithm。

So here's the way it looks。So heres here's the approximation algorithm。Okay， so this is what not。

 we're thinking of this as not being monotone， so this is unsuitable for direct implementation in a big mechanism。

And now we need some sort of sanitizer。So you want to have an algorithm B。

hich at the end of the day will be monotone。And the resampers。Sit here。Okay。

 so we take the original evaluation profile。We feed it into the resampers， so this is a value。

 one per bidter。This is one algorithm per bidter。 It remaps valuation VI to a different valuation R I of VI。

We feed the remapped valuations。Into the original approximation algorithm。

And it's not all clear why we should， why this could work， but wouldn't it be cool if。

So then we run the algorithm on the remapped valuations， reampled valuations。

Wouldnt it be cool is if even with a non monotone A。If we could。

 if we could design a suitable pre processingces step。Resulting in the algorithm being monotone。

Resulting in an algorithm that we can then。Plug into the extended Marson's limo。Okay。

 I guess we want this to。So if this is out for prox。

We want this to be also alpha or close to alpha approximate。O。

So this is called the black box reduction。Yeah。And it's a black box reduction in the sense that it doesn't look at the guts of how a is implemented。

 Okay does， as we'll see， it does actually need to know some information about a。

 I'll be specific about that。 But， I mean， the general scheme， the point is， given any A。

 I'm going to show you how you can design ours so that the combined algorithm is exactly what you want。

 A good approximation that is monotone。Okay。I guess now that I think about it。 I mean。

 the the Levee Swmi algorithm， which we worked so hard on last week。

 also had this flavor a little bit。 So remember， you know， first， we said， forget incentives。

Let's just show that there exists a good approximation algorithm， polynoial time 1 plus epsilon。

Then we kind of showed just by virtue of the existence of a good approximation algorithm。

 we could solve a linear program that sort of smeared the error of that approximation algorithm exactly equally out over all allocations。

 And that was our scaling algorithm， which then gave us the incentives， the decent properties。

 So here again， we're taking we're saying you know first。

 just forget incentives focus on showing that there exists a good poll auto approximation algorithm。

 And then we'll have some right So in Levy Swwami was the back end here it's a front end that takes care of the incentive part。

Okay。So that's the dream。Okay。All right， so。What would be the best case scenario？For these resampers。

 okay， what properties would we want them to have？嗯。All right。 Well， we sort of want to be。

 we want them to be kind of under the hood。 We want them to be sneaky in the sense that a bidder doesn't notice that every resampled are the bitters。

Okay。So distributions。Unchange。Meaning that with the original valuation， VI is drawn from F。

 I want it to be the case that even after resampling。The distribution is exactly the same。Okay上。

So one bonus about doing it this way is it means we can apply all of these。 you know。

 we can design the resampling algorithms in parallel。 Okay， rather than sort of sequentially。 Okay。

 we can just apply them all independently。Okay， so the other thing。

 we want to not screw up the welfare guarantee of the given approximation algorithm A。

So we want the resampers to be welfare improving。So， the expected。Welfare of A。

 given the rempped valuations。Should be at least the expected welfare。Originally。So remember。

 by assumption， this is an alpha approximation algorithm。

 so this is within an alpha as large as it could possibly be。

And so we're going to have this composed algorithm or composed A， which is at least as good。

 so it'll also be an alpha approximation algorithm。And then， three。

Our new induced allocation rule with this front end of the Rs。So， the new algorithm B。

Which applies R first and then applies A。We want this to induce。Monione， interim allocation rules。

Okay。So if we can do this and have the distributions and have the resampers be polynomial time。

 then we're good to go。Okay。So we're given an alpha approximation algorithm。

 this says that the big black box B is an alpha approximation algorithm。

 this says that it's monotone。And therefore， the extent of Marison's lima applies， okay。

And so in fact， there do exist such resampers。Okay。So let me， let me wet your appetite。

 And this is what I'll， I'll finish with。Kin of which your appetite was just sort of a representative special case。

 Okay， so it's a very special case， but。You know。Get your intuition pointed in the right direction as far as how these constructions work。

So warm up。So let's remember。 So， okay， so， so what's the goal， So The goal here is to design。

These algorithms， these Rs， these mappings from valuations to valuations。

 that's what we're trying to construct。And what we're given is we're given。Black box access to a。

 we' given So an allocation rule X in the form of the algorithm A。

And we're given the prior capital F。Okay。So the warm up is going to be where capital F is super simple。

Okay， so let's just assume F is uniform on some finite set that were given explicitly。Okay。

So let's just assume each FiI。Hiss uniform。On Mpoint。Okay。

So let me explain then how we're going to define R sub I。So notice， so property one。

 first our sub says okay。Property 1 says the distribution should be unchanged。 Okay。

 so the input distribution is uniform over these endpoints。 So R sub I just remaps things。

 So it's again， uniform among endpoints。 So you can actually think of sort of R sub I as a matching。

 if you like， or a byjection。So this is the input valuation。And again。

 the input is uniform over impossible possible values。There's some output valuation。

 The distribution should be exactly the same。 so this is going to be some that means this has to be some bijection。

Right，You can't You can't map anyone twice because it would double the probability of that value。

 It would change the distribution。 Okay， so think of the sort of。

Feaible solutions for R subI is being perfect matchings in a biparttheite graph。

So let's call the possible， all right， so uniform endpoint， let's call them。T 1。Up to TM。

So these are just the possible valuations that I could have。没有。哎。

What I want you to do is I want you to， okay， so we have this algorithm A， you know。

 like a map auristic， something like that。And。We have this。 We have this prior F。

And what I want to do， all right， and the induced de will X。So now I want to say， okay。

 as given these various possible things I could bid， given my various values。

 what's my winning probability in the algorithm A。 Okay， let's just write that down。So。

 consider the interim。Allocs， again， just think of these as being like winning probabilities averaged over phi minus I。

行。So this just says， if I report my lowest valuation， what's my winning probability。

 If I report my highest valuation， what's my winning probability。

 That's what all of these numbers are， okay。Now， if x is a monotone allocation rule。

 which is the happy case， where we don't have any work to do， if x is a monotone allocation rule。

 then this is just an increasing or non decreasinging sequence of numbers。Right。

And if it's not a mono allocation row， then this is not sorted。 then's some inversions。

So here's how I'm going to define the perfect matching or the bijection or the resampling。

 however you want to think of it。So for each。Input。Okay。Here's how we remap。It's very simple。Okay。

So we have these impossible evaluations from low to high。

 We have these impossible inter allocationlocs， which are not necessarily sorted from low to high。

So when we're given the Jith smallest valuation。We just match it with the J smallest of the possible allocation probabilities。

That's it。So it it R IF TJ。To be equal to， maybe more precise。So basically， given。

 say the J's smallest number here。I look at the Js smallest number here。

And I look at the type TL or sorry， the valuation T subL that's receiving that Js smallest allocation probability in this list。

Where X， I， T， L。Is the J's smallest allocation probability？For example。

 I suppose X is actually monotone。Then R is a very simple function。Right。

Otherwise the identity function effects is already monotone。RightBecause the bottom was distorted。

 Okay， so the Jaith。Declaration goes with with the J allocation probability。On the other hand。

 when there's inversions in the allocation probabilities， I'm sort of fixing them。Right。

 so for example， what if just the first two are reversed。 Okay， so what if， you know。

 with the lowest valuation， you have allocation， you have winning probability 2% and with the second lowest allocation probability。

 you actually have even worse allocation probability 1%。Well， then this is just going to say， oh。

 well， you know what， the resampler， or I says， oh， if it's the lowest valuation。

 let's actually sort of misreport it to be the second lowest valuation to ensure we actually do get the smallest possible allocation probability。

And then to make up for it， when we actually see the second smallest valuation。

 then we do the opposite。 Okay， we match that back to the 2% allocation probability。

So is the definition clear？Just literally at all you do。 just sort this small to high。 And then。

 in effect， you sort these low to high。 And then that's your matching okay。All right。Good。

 so what are the properties？So first of all， RI is uniform。Sorry。Let's just say。

Output distribution equals uniform。Just like the input distribution。

 That's because each of these values is matched to exactly。One of these。

The composition of the reesesampler。And the original allocation rule is now a monotone allocation rule。

And this is by construction。 I defined arsenalized。 so this would be true。Okay。

So remember I match explicitly match the JFs smallest valuation to the JFs smallest allocation probability。

So that's by construction。And then finally， I claim the expected welfare。V I。Times Xi。Of I。

Only goes up。Okay。And the reason is exactly the same reason why， like in sponsored search。

 you rank by bid to maximize welfare。 Okay， So if you have a bunch of allocation probabilities going from low to high and you have a bunch of potential values from low to high and you want to maximize the sum of the products。

 some of the V I X Ls。 What you want to do is just greedily match the highest value to the highest allocation probability。

 Okay to trivial exchange argument。So these are essentially the same three deerta we had over here。

Okay。So let me tell you the one place I'm cheating and then the two places we'd like to sort of extend this result。

 this will be the topic of next lecture。The place I'm cheating。

Or that requires some discussion is where did these come from， Where did I get these numbers。

How do I know the winning probability of a bidder when it bids something。Okay。

 so the way I'm thinking about this is I'm not given these numbers explicitly。

 what I' I'm giving basically a piece of code， which is someone's heuristic Knasack。

Okay so I'm giving that black box A。So the first question is， how do I compute？These x's。

 the allocation probability， is given only black box access to A。 So that's where I'm cheating。

As far as extensions， the obvious one is to look at know， both non uniform discrete distributions。

 but also continuous distributions， but then also to go beyond the single parameter setting to the multi parametera setting。

 Okay， so see you next week。