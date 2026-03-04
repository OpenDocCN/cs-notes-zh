# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p14 -14-(Lecture 14_ Smoothed Analysis of Pareto Curves).zh_en -BV1yqVzzqEQ5_p14-

So this is going to be our probably penultimate lecture on smooth analysis。

 so where you have adversarial input except slightly perturbtive by nature and you want to prove positive results under only those relatively weak assumptions about the amount of randomness in the data and so the application of smooth analysis we're going to discuss today is to something called Pareto curves。

 and so let me open the lecture by explaining one reason why you might care about Pareto curves。

 namely， it turns out there are some pretty neat algorithms where the running time is actually governed by the size of a particular Pareto curve。

So let me remind you about the Napsack problem， which I hope you've all seen before。

So this is a well known NP completete problem。So the input consists of n items。

Each of which has two positive parameters， a value and a weight or a size。So there's values。

 V went up to Vn。And I'm going to call them weights， They're often called sizes。And then finally。

 there's a Napsackack capacity。Capital W。看。And the goal is simple enough。

You want to take as many items as possible， so you want to maximize the value。

So you're going to pick a subset S of items。You want the total value to be as high as possible。

 The constraint is that the item should fit in yournapsack。

 That is the sum of the weights in the set that you choose should be a most capital W。

 the Napsack capacity。Sure。So that's an abstractpsack problem。When you first saw this。

 you may have been told some hokey story about a burglar。

 you know who wants to sort of put a bunch of items in their knapsack and make away with as much loot as possible。

 but it's actually a very fundamental problem whenever you have a limited amount of a resource and you want to use it in the optimal way that's pretty much annapsack problem Okay so it comes up all the time。

All right。I'm going to tell you about a Knapsack algorithm that you probably haven't seen before。

And to tell you about it， I need to talk about Pareto curves。

So consider two different subsets of items of an Apppsack instance。S and T。

We'll say that subset of items S dominates another one T。If。On the one hand， you get more value。

From S。But on the other hand。The total weight consumed。By the items in S， is it most that of T。Okay。

So items have two parameters。 So there's two axes along which you could measure the quality of a solution。

 how much value do you get and how much of the knapsack it picks up。 So S dominates T。

 if it's better simultaneously， according to both metrics， both more value and smaller weight。

So clearly， you know， S basically renders T moot。 right。

 There's really no reason to ever think about the feasible solution T。 It's just， you know。

 you'd always want to use S instead step， okay。And the Pareto curve， then。

Is just a set of undominated solutions。Okay， so you might want to think about。

Drawing a graph where you have the total weight。On the X axis。The total value。On the y axis。

And basically， if you're dominated， it means there's a point to the northwest of you。 Okay。

 there's something that has both less weight and higher value。

 And if there's nothing to the northwest of you， then you're undominated。

So respecting a Pareto curve to look something like this。

And maybe these would be two points that are dominated。 Okay。

 there's a point to the northwest of each of these。

you've actually seen this concept before in this class， it's been a little while。

 but in lecture number two， we talked about 2D maximuma。

 where were given points in the plane and we wanted to compute the undominated points exactly the same thing。

 The only difference in the picture is that it's reflected around the Y axis because of the way we're labeling things this lecture okay。

So that's it。 It's just the same thing as saying if you plotted the total value and total weights of every subset of items。

 you'd just be looking for the maxima of those two to the endpoints。 Okay， that's the Pareto curve。

Any questions about that？Okay。So let me tell you about an algorithm。An abstract algorithm。

 which you probably haven't seen before。But that is useful。 It's practically useful。

 It just happens to be sort of underrepresented in undergraduate classes and textbooks。

So Napsack algorithm。So step one。I'm just going to state it at a high level。

 I'll leave the detailed implementation to homework 7， generate the Braidto curve。Okay。

 so enumerate all of the undominated solutions。And then， amongst those。Just find the one。

That has the highest weight that gets as close to filling annapsack as possible。 or rather。

 among everything that fits in the knapsack in the prato curve。

 just picked the one with the highest value。So return。Max value。Solution。In the Prato curve。

With weight at most， capital W。Notice that the prato curve doesn't reference the Napsack capacity capital W Okay。

 so the preto curve depends only on the Vs and the Ws。 Once you then know the Napsstack capacity。

 it's of obvious which one you want to pluck out， right。

 you throw out everything that doesn't fit among those that are left。

 You take the one with the highest value，All right， so it's clearly correct。Okay。

The only issue would be by restricting yourself to。 So these are called Pareto optimal solutions。

 Get points in the Pareto curve。 I'll use the word Pareto optimal over and over again， this lecture。

So the only thing to prove is that there's no loss of generality restricting yourself to Pareto optimal solutions。

 But that's obvious by the definition of being dominated。 But if something's dominated。

 you can throw it out。 It's no big deal。 You're definitely not throwing it out an optimal solution。

So。Correctness then is clear。 So what about the running time。 I mean， it is an MP complete problem。

 after all。So at am。The way you want to do it。And so， the thing I want to emphasize here is this。

 there's no explicit dynamic programming in this algorithm。

 And my guess is every Dstack algorithm you've ever seen， and you may have even seen more than one。

 They always have explicit dynamic programming。 And here you don't。

So the way to do this is you want to generate a sequence of Pareto curves。

Corresponding to prefixes of the items。 So you order the items in an arbitrary way。

 You first generate the Pareto curve of none of of the first zero items。 That's just the empty set。

 Then the Pareto curve of the first item， the preto curve of just the first two items。

 first three items， and so forth。And I'll let you think about a little bit offline this week。

 but once you've computed the Pareto curve of the first i items。

 it's conceptually very straightforward to then compute the preto curve of the first i plus one items。

 okay。So， to implement。Iter really generates。I'll call them the PCIs。Where PCI equals Paretto curve。

Of the first eye items。Okay。And what'll ask you to prove on the homework。

Is that you can implement this algorithm in time proportional to the sizes of the Pareto curves。

So basically， I mean， the hint is to generate the I plus1 cradto curve from the Ih1。

 turns out all you need to do。 Basically what you want to do is you want to keep the crreadto curves sorted。

 sorted by weight， let's say。And then to get the next one。

 you just make two copies of the current preto curve， one without item I plus1。

 one with item I plus1， and then it just boils down to merging two sorted lists。

 which of course we can do in linear time in the size of the lists。So homework。Can implement。

In big O of。The sum of the sizes of these pareto curves。The mic was zero up to n。

 so that's straightforward。 Okay， it'd be easy to do a lecture。

 but I just want to make sure you understand this algorithm。

 I'm going to ask you to just write the details as part of homework。Okay。So again。

 I want to emphasize this is， I mean， it's annapsack algorithm。 You know， it's really。

 it's not a dynamic programming algorithm。 it's not explicitly， okay。So is it any good？

how should we interpret this running time， Okay， so what some of the peri curve sizes。

 Is that good or is that bad。Well， it depends。So let's start with the good news。

The first piece of good news。So if we think about this quantity， so how big could this be okay？Well。

Let's just put a factor of n up front right away for the n plus1 sum ends， okay。

And now let's just focus on a single Brato curve。 Like， let's say the last Brato curve， okay。So。

And let's think about various upper bounds。 We could state for how big a prato curve could be。

So certainly， in the worst case， it's all possible solutions of which there are two to the n， okay。

So we'll put a2 of the in there。And again， it's an impbeably problem。

 we are expecting to see some kind of exponent somewhere in the worst case。 Now。

 when you study dynamic programming algorithms for NapsSAC。

 you always assume that either the values are integers or the weights or integers because you have to write down this table and you have to have columns which correspond to the possible different values or the possible different weights that sub optimal solutions to subproms could have。

And so then you get running times， which depend on either the largest weight or the largest value。

 depending on whether you're assuming weights are integral or values are integral。

So let's think about now this algorithm under this analogous assumption。

 So let's suppose the weights were all integers。 Okay， and that the biggest weight was W Max。Okay。

What I want you to notice is， I raced the。Definition of domination。

But if you have two different solutions with exactly the same weight。Okay。

 you're going to throw one of them out。Either they're both exactly the same。

 and then it doesn't matter。 you just keep one or one as a higher value。

 and you throw out the one with a smaller value。So in other words， as you generate these pato curves。

 always discarding dominated solutions at every single step。

 you will retain at most one solution for each distinct total weight。Okay。

If weights are integers at most W max， the number of distinct total weights of subsets you'll ever see is n times W max。

So if W Max is small， then youre like， say W max is just like 10。 Okay。

 and the number of items is 100。 You're never gonna remember more than 3000 different items。 Okay。

 everything else will be dominated by something already in the set。So without changing the algorithm。

 okay， so without actually changing the algorithm to make use to this assumption that weights are integers。

 we can just automatically say that its running time is up bounded。By n times W max。Okay。

Because again， that's the maximum number of distinct weights you'll ever see of different feasible solutions。

Exactly the same reasoning applies to the same algorithm if the values are integers。

 given two different feasible solutions with equal value， one has smaller weights。

 and that's the only one you're going to bother to keep the one with higher weight is dominated then you'll throw it out so if the values are all at most VX。

 the number of distinct solutions you need to keep around is at most n times of V maxax。

 everything else will be dominated。So for this same algorithm， we can also write down。

And times of V max。So what's cool about this is not only do we not do explicit dynamic programming。

 but we don't need to write down a different algorithm tailored separately for the case of integer values or integer weights。

 This common algorithm just automatically achieves the best of both of those cases。 So like in 161。

 when I teach it normally I do one of the dynamic programming algorithms in lecture。

 And then I ask usually in the final exam for students to figure out the other one。

 but it's a different algorithm， It has exactly the same sort of template。

 but it's really not the same algorithm。 you write down a different table。😊，All right。

 So that's cool。 So that's the first reason I'm teaching you this algorithm is just because I think it' it's sort of a neat underrepresented algorithm。

😊，The main reason I'm teaching it to you is because actually。

 this has a very good smooth complexity as well。 Okay And so that that's the main point。

I do want to point out。I I ask you to work this out on homework。That in the worst case。Indeed。

 we can have。The size of a Paretto curve can be exponential。In the number of items。 Okay。

 so it can be the case， in the worst case that none of the possible feasible solution。

 none of the possible sub of items dominate the other ones。 They could all be incomparable。 Okay。

 so I'll ask you to think that through。So in the worst case。

 we're not going get a better upper bound。 but I'm going to show you that if we have a smooth instance。

 then we actually get a polynomial bound。 Okay， and that's the main point of the lecture。All right。

 so any questions？All right， let me tell you， let me state formally the ban theorem。

So this is from '07。There were some。Weaker results known earlier。So for smooth instances。

 and I'll explain what I mean by that， it basically means the same thing as last lecture when we were talking about TSB。

So for smooth instances。The expected size。 So again， in the worst case。

 the prato curve can have exponential size， but the expected。Size is only quadratic in it。

That's what we're going to prove。 Sigma， as usual， is some measure of a size of the perturbation。

 And again， we are expecting some dependence on one of sigma because we know in the worst case。

 these things are exponential。Okay。So by linear of expectations， then。

This is just n cubed over signal。So the expected running time of thenpsack algorithm。

Is O of N cubed over Sigma。And that's actually pretty cool because， I mean。

 this isn' an N complete problem， actually， right， So I'm giving you a polynomial time algorithm for an N complete problem。

😊，The the rub， of course， being is not polynomial time in the worst case。

 but it's expected polynomial time， assuming inputs are drawn from any distribution。

 which isly diffuse in the same sense as on Monday。So that's kind of neat because now。

 for the first time， smooth analysis is really telling us something。

 not just about the performance of a single algorithm。

 but it's really telling us something interesting about a computational problem。 Okay， so remember。

 computational problem is defined independent of any algorithm。 That's like the Napsack algorithm。

 And then you can discuss the performance of particular algorithms。

 And the complexity of a problem is basically the best algorithm for the problem。😊，So it's， I mean。

 even forgetting about this very natural algorithm， it's just amazing。

 there's any algorithm that has polynomial smooth complexity for this MP complete problem。 I mean。

 now we sort of understand why， but this is sort of an interesting insight。

 I feel that smooth analysis gives us。 This also corroborates well with sort of empirically Napssack is indeed one of the easiest in practice of all of the MP complete problems。

 So it does seem reasonable that theory would give us a result like this。😊，OK。支。Yeah， and good。Good。

Right， and because， oh， yeah， the other thing I want to say is so homework。This upper bound is。

 in fact optimal or is tight。Okay， so I'm only going to ask you to prove it when Sigma is constant。

 So I'll just ask you to prove a lower bound of n squared in an average case model。

 but the exponent in the end here is indeed correct。 So it's also satisfying。

Do you see that kind of performance in practice we got the practice like to the6 hour That's a good question。

 I mean， so this this is going to be， I think you pick up this n squared even for the uniform distribution if memory serves。

 So this should this should match empirical performance up to constant factors。 And I mean。

 I'll show you the whole analysis。 So the constant factors are not are not overly large。

So I haven't explicitly seen an empirical study， but just the mathematical results are so sharp here。

You'd expect empirical performance to hew to it fairly closely。Yeah， it's a good question。

 So have all the smooth analyses I'm going to show you just like a you know， quantitative level。

 This one's the most satisfying。 This one we we're really going to feel like we nailed the problem in today's lecture。

 which is great。😊，Other questions。O。So perturbation model， let me just be clear on this。

So one thing that's interesting is actually remember these two parameters is the values and the weights。

 the values were' not going to smooth at all。 Okay so the values can just be picked worse case by an adversary。

OkaySo the VIs are adversarial。And the Napsack capacity is also。

 I guess we're generalizing Pareto curve， so we don't have a Napstack capacity。

And then the weights are smooth。So each WI。So the weight of the item is drawn。

 according to a density function。Let's think of these as just in 01。

 That's without loss of generality。 We'll just scale them。 so real numbers in 0，1。

 The weights we'll also think of as being in 0，1。And the definition is exactly the same as last time。

Wherever the only thing we assume about the distributions is that they're not too spiky。

 so the density function at a given point is at almost one over sigma， where sigma is this parameter。

So again， you can think of this as the area of the support。

You can think of it as a lower bound on the amount of the unit interval that the density function has to be supported on。

Okay， at least sigma。I to do this other way。dvers you can you can， yep， so you can flip them as well。

Yeah。So what's important is just that one of them is random and that's all you need。Yeah。Okay。

 so this is really exact， I mean， in some sense it's even simpler than Monday because Monday。

 remember we were dealing with points in the plane。

 we were talking about the local search algorithmcroms for TSP。

 and so this is the same now we have one coordinate instead of two coordinates Okay so otherwise it's exactly the same。

And again， what's cool about this is really， you know we don't care if this is uniform， exponential。

 truncated Gaussian， whatever， okay so there's really no dependence on the analysis on some parametric form of the distribution so we don't have to assume Gaussian。

 so that's very nice。Because I think it's easy to believe that， know， data has randomness in it。

 It's harder to believe any particular model of that randomness。

 So these are really exactly the kind of theorems I think we should aspire to。Okay。Good。

So everyone ready， we're going start talking about the proof of this theorem or how we're going to do it。

So I'm going to sort of gradually。You know， I'm going to start with just trying to help you think about the analysis in the right way。

 And then we're going to slowly you know， add the necessary complexity to actually prove the theorem。

So here's the picture I want you to have in mind。So， let N。Be the number of Pareto optimal solutions。

I。e。 the population in the Pareto curve。 This is what we want to prove and expectation is at most that。

 Okay， so we want an upper bound on capital N。And。I want you to think about a table？

Basically just kind of a discretized picture of what I just erased here。

So we have these two to the n subsets of the items。 Okay， and we're looking at their values。

 and we're looking at their weights。 Remember， actually for any subset of the items。

 we actually know their value exactly。 Okay， and it's just their weights are random。 All right。

 so this is a random variable because the weights are random。

And so the total weight of a subset of items varies anywhere from 0 to n。 remember。

 we're now assuming weights are between0 and 1。And the values also think of as between 0 and n。

And we want to count how many Pareto optimal things show up here。And it's going to be convenient。

To break this square into slices。Of with epsilon。Okay。What is Epsilon。

 Epsilon is a parameter that we're going to choose for convenience in our proof。 Okay。

 so Epsilon is not part of the input。 Epsilon is just going to be internal to our proof。

So we're going to break。The weight range。0 n into tiny slices。 Think of epsilon as very small。

Of with epsilon。So there's n over epsilon slices。Okay。And what we're doing here for convenience。

Is we're going to choose epsilon So small。That the probability is essentially 0 that you're going to see two Pato optimal solutions in the same slice。

 Okay， so think of that being like a doubly exponential number of slices or something like this。

 And then it's just going be a merely exponential number at most of subsets showing up here。

 So there's no way or almost no way you'll get two in a common slice。

 So what we want to do is instead of counting the number of points with multiplicity。

 We just want to kind of count without multiplicity。

 So we just want to know how many slices at at least one resident。And yeah， this is just。

 this is just it simifies， It simplifies what we have to do。 That's why we're doing it。Small enough。

 so that we have essentially zero probability。Of greater than one preto optimal。Solution and a slice。

Okay。And again， remember what the picture is going to look like。 So the undominated points。

 basically nothing should be to the northwest。So it's going to look something like this。

RightSo each of these preto optimal points these red points is going to be in some slice。And。

In the number of pretty optimal solutions。Given that epsilon is so small is basically just the number of occupied slices。

Okay。So that's what we want to do。 We have these slices。

 There's some probability that it has an occupant， there's N of epsilon slices。

 we want to say the probability that a given slice has an occupant is small。Right。

 so let me just mention right now。 I mean， Epsilon is not going to appear in our final bound。 Okay。

 in our final calculations， Epsilon will just cancel out。 That's why we don't care what the value is。

 And we can make this assumption without any harm。Okay， so what's the plan？So ultimately。

 we need to upper bound capital N， or rather it's。Expectation。

 And we know n can be big in the worst case。 It could be two of the little n in the worst case。

 So We need to use the fact that the weights are random。 that the instance is smooth。

And it's not really clear how to directly apply the smooth hypothesis to capital N directly。

There's just like too many moving parts。 Okay， so given feasible solution。

 it might or might not be preto optimal， its value is fixed， but itss weights random。

 So whether it's preto optimal or not， whether it's dominated by someone else or not。

 it depends on the coin flips for its own weights。 So items， right， So think about just like items 4。

7 and 10。O，The subset of items 4，7 and 10 might or might not become a pre to optimal solution after we flip the coins。

What does it depend on， What certainly depends on the random weights of 4，7 and 10。

 The smaller these weights are， the more likely this thing is to be a paretal optimal solution。Right。

 it's going to be better。 its value is fixed， the smaller the weight， the better the thing is。

 the more likely it's to optimal。 But actually， it doesn't just depend on 4，7 and 10， right。Like。

 we also care about whether it's dominated by other solutions， right。

 So it's also more likely to be preto optimal if other solutions have high weights。Okay。

And so then the question is like， okay， this one is' 4，7 and 10。 This other thing is 4，12 and 14。

 And then you got to know who dominates who。 And then， of course。

 there's an exponential number of other things that might dominate you just to kind quickly gets out of hand。

 Okay， so we have going for us is that waits are random It's just capital N is too much of a mess to really make direct use of it。

 Okay So what we have to do in the proof is we have to decompose capital N。

 so we have we have to have ways of counting preto optimal solutions or perhaps over counting preto optimal solutions。

Until we can finally actually use in a useful way this hypothesis the rates are random。

 And if you think about it， we were actually basically doing that exact same thing on Monday。

 although it wasn't quite maybe didn't seem quite as complicated。 But again。

 the whole point of the proof was to sort of zoom in on a relevant。

 bad event and define it just so So that it was very easy to use the smooth hypothesis。

 So what we did on Monday， We were worried about bad swaps。 swaps that don't make much progress。

 So we fixed a particular swap， meaning these four points。 So that was good。

 We zoomed in on these four points。 we actually zoomed in on a linear combination to get rid of those absolute values。

 and then we conditioned on 7 of the8 relevant coordinates。

 and all of a sudden it got really easy We had this relevant event that this thing landed in this interval。

 We had this one remaining random thing， which was a single coordinate of a single point。

 And at that point we just said， dude， it's random。 it's very diffuse。 It has a low density。

 So the chance that this thing lies in this fixed interval is small。 So really the whole。😊。

The proof was building up to this effectively almost trivial application of the smooth hypothesis。

 Okay so that's what we have to do again today。 Okay and at the very end of today's lecture。

 we'll find ourselves in a position where we can just very easily use the fact that the weights are random。

 It's going to take us a couple steps to get there because n is such a mess， okay。😊，All right。

 so that's the plan。So what I want to do first is I want to do kind of a baby version of the proof。

 So what I'm going to say for the next， maybe 10，15 minutes。

 we're not actually going to use directly， but we're going to build on it， to do the full proof。

 Okay， So think of this is kind of the scaffolding， which will refine for the， for the proof proper。

Okay， so warm up。So think about a slice boundary and I call it tea。So maybe it's like right here。

Okay， so T is just some number， some multiple of epsilon between 0 and n。Okay。Now， intuitively。

 what we're going to do is we're going to look eastward from T。 Okay。

 We're going to look to the right。And we're going say， you know。

 what's the first Pareto optimal point， the first red point that we see to the right of capital T okay。

And basically， if it's in the slice immediately after T between T and T plus epsilon。

 we're intuitively going to charge that preetto optimal solution to this slice boundary T。 Okay。

 so put differently every red point， every perietto optimal solution。

 we're going to charge it to the slice boundary immediately to its left。 Okay。

 and then we're going to count up the number of slice boundaries that have these red points right next to them。

 okay。So how do we say that a little more formally。So。What we do first is we look to the left。 Okay。

 so basically we're trying to we're going to have notation。

 which basically talks about these two points。 Okay。

 the preto optimalal points immediately to the left of T to the right of T。

So PT is going to be to the left。So max value solution， so the highest point。

 the northernmost point to the left of T。Okay， so in this picture。

 that would be that red point there。 That's PT T， okay。

And then V T is going to be its value or its height， okay。Now。

 PT T is random because a given subset of items 4，7 and 10。

 It might or might not have weight at most tea， depending on how the coin flips show up for the weights。

Given PT T condition on PT T， its value is then fixed， right Because remember。

 the values are are not random。 Val are just given， okay。Okay。And so now we do as we say。

 let's find the next Pareto optimal point looking to the right。 And， of course。

 as we go to the right， the weight is only increasing。 So whatever the next Pato optimal point is。

 it has to have strictly higher value。 otherwise would be dominated by the previous one。

So we're looking east。 and then， of course， we have to be looking north if we're staying on the Pareto curve。

So， ST。Right and so then right so ST is the Min weight solution。

 so the first one we find looking right， looking eastward。With value。Bigger than Dt。Okay。

So this would just be right。So think of that as PT， and this as ST。Now， remember。

 we're trying to compute capital n， we're trying to calculate the number of pre optimal solutions。

 and here's how I'm going to decompose that messy sum。Like I said， we're just going to look boundary。

 slice boundary by slice boundary。 And we're only going to count something when it's in immediately next slice。

 Okay， So N T is just an indicator random variable。One， if when we look eastward and find S T。

 it's in the first possible slice between T and T plus epsilon。 If it's further down0， okay。

 it's going to get charged to some other slice boundary later。So， one。If weight of S T。

Is in the first possible slice， Tt plus epsilon or zero otherwise？So that's all the notation。Alright。

And again， for this warm up， I'm doing something which if you can survive the notation。

 I think is pretty easy to see。But the point is is we'll use a slightly more complicated version of this argument to actually prove the theory。

 and I want to just sort of get you used to the flavor of argument before we do the full blown thing。

Okay， so warm up claim。So again， what are we trying to accomplish， There's capital N。

 We don't know how to analyze that。 We're trying to break it down into simple parts that hopefully we can analyze。

 So I want to say that these ends sub T's are a legitimate decomposition of capital N， okay。

So I want to say that if we sum up all of these indicator random variables。Slices tea and tea。

Then we capture all of the preto optimal points。 This actually holds with the quality for this warmlemma。

 We don't need that。 We just need to be make sure we're not under counting， okay。O。

So this is pretty much know， true by notation。 but let me go through it just to so that the notation sticks。

So proof。So suppose S。Is on the Pareto curve。Okay， this is with Pro one， by the way。

So these are both random variables， the number of preto optimalmal points。

 and whether or not there's a point in this slice T T plus epsilon because the weight it's random。

Okay， so suppose we have a pretty optimal solution that is suppose S contributes to the right hand side。

 We just have to show that S also contributes to the left hand side，So。

And we sort of talked through this。Since S is Pareto optimal。Since its weight is bigger than tea。

 and so in particular， its weight is bigger than that of piece of tea。This value。

 its value better be bigger than P of Ts。 Okay， Otherwise， S of T would be dominated by P of T。

 By definition， S of Ts to the right。 So it has to be above。So。ち。Value。Is greater than v sub T。

And then remember， we're going to assume for the rest of the proof that every slice has at most one peral optimal point because we've chosen epsilon so small。

So since there's the most one。Prato optimaltiimum solution per slice。

The claim is that S has to be equal to S subt。Okay。So we started with something on the Pto curve。

 We're calling it capital S， okay。Oops， I forgot to tell you what T is。呃T一锅。

Slice boundary to the left。Okay。So in the definitions， I started with T。

 and then I made all these definitions。 Now， I'm we're starting with some point of the Pareto curve。

 S， It's just somewhere has some weight has some value。I'm defining T to be the slice boundary。

 immediately to the left。And then I'm arguing that in the sum on the left hand side。

 we are counting this preto optimal solution。 We're counting it through an n of T。Why is that true。

 Well， so what is S sub T， Let's remember what Nt is one， if and only if。S sub T。

 which is the minimum weight solution。 Okay， with value bigger than v sub T。 So in other words。

 the first periodto optimal point when you look right。 So N sub T is one， if and only if that first。

P optimalum solution further to the right lands in the slice boundary。 Okay， but that is true。

 just by definition， right So T is chosen to be the slice boundary immediately to the left of S。

 So n sub T for that value of T will be one Okay， because S of T is there And we're not doing any undercounting because every slice has only one occupant。

 Only one period of optimal solution。So again， this is。

 this is sort of if this feels close to e vaccuuous， you're right。 Okay。

 but the next version is going to be actually pretty subtle。

 but it'll follow exactly the same kind of template。So again。

 just to summarize really what we're doing， we're saying， well rather than count these directly。

 let's just charge each preto the existence of each preto optimalmal point to the boundary immediately to the left and count those instead。

In this way。All right， now， unfortunately， so this reduces upper bound in the size of the Pato curve to upper bounding the expectation on the left。

 I。e。 upper bounding， the probability of these indicator events and sub T。So what does ends of T say。

 Okay， so ends of T is the probability that， one of these proto often solutions lands in this particular slice。

But again， that's a little complicated to understand。

 right And the reason it's complicated to understand is that a lot of different possible solutions after the coins get flipped might are eligible to land in this slice T T plus epsilon。

So we'd love to say something like fix a sliced tea T plus epsilon。It's very low probability。

 Anything will wind up here and then just sum up over all the slices and be done。

And the issue is there's sort of two to the n possible subsets of items out there。And you know。

 what if a lot of them have unperturbed weight really close to T and thus have a legitimate shot of winding up with total weight in this sliced tea T plus epsilon？

Then that's a lot of different events that could happen that are all bad。

 And it's hard to get a handle on that。 Intuitively。

 it seems unlikely that all all these exponential number of different subsets could simultaneously be Pareto optimal while landing in the slice。

 But it's a little hard to figure out how to tease that out。 Okay。

 But so that's what we're going to do by decomposing this sum even further。 Okay， Basically。

 we get at that issue。All right， so any questions about sort of the warm up version？Okay。Good。

Then let's refine this。So here's the real proof。So we're going to have similar definitions to this。

 just a little bit extra complexity。All right， it's a proof of the real theorem。

That the Paretto curve is the most n squared over sigma and expectation。So some definitions。

So T is as before slice boundary， but now in addition。

 we're going to parameterize by an item Okay so before we were basically charging the presence of a proto optimalmal solution to the boundary slice immediately to the left。

 now we're going to be charging it to a combination of that same boundary slice T plus an item and I'll show you what the item is in a second。

Allright， so define。All right， so before PT was you look left and you see the first pre optimalim solution that you find？

So now it's going to be a little bit different。It's going to be the max value solution。

 So we look left and we look up， but we restrict attention to solutions that exclude this item I。

So first of all。Wai is it most tea， so we're looking left。But， it does not。Include item I。Okay。

So PIT so remember， before you define PT is just the max value solution looking left。O，So P。

 I T may or may not equal P T。 So if you， if you just optimize value looking to the left。

Maybe you get lucky and the optimal solution doesn't include I anyways。

 And then it's also optimal for this problem。 On the other hand。

 maybe you get a strictly smaller value solution by adding this constraint that you're not allowed to contain I。

 Okay， so P I T may or may not be the same thing as P T was before。O。So VIT is the value。

Of PIT as before。Now， the analog of S T is again going to be sneaky。

So this is where last time we sort of looked to the right of T and we just found the first Pato optimal solution。

 Now we're going to restrict attention to solutions that include item I。

So we look at the Min weight solution。So as far to the left as possible。Such that。

The value is bigger than our target， VIT。And2。It includes item I。O。Probably you're wondering。

 you know， where did this come from， Why are we doing this， I mean， so at the end of the proof。

 you'll see how cleanly we're able to apply the assumption that the weights are perturbed。

 So the way you'd come up with this is you'd say， okay。

 I know what I want the end of the proof to look like。

 I know I want some very clean application of the perturbation。

 and then you would back out what kind of event you actually can apply it so cleanly。

 That's I think the only way you would really come to these sneaky definitions。😊，2。And now。

Previously， we were charging preto optimal solutions to the boundary to the left。

 and now we're going to charge it to a combination of a boundary and to an item。

So NT is an indicator random variable。And it's one same thing as before。 if the weights。Of SIT。

Is in the slice T T plus epsilon。0ero otherwise。Okay。So any questions parsing the definitions？

It's a subtle set of definitions，So， for example， unlike last time。

 it might actually be the case that， well， never mind。 that's not relevant for the proof。

 So I'll skip it， okay。So for P， I T， we exclude item I for S I T， we include item I。 That's。

 that's the key point。 That's the key twist from last time。Now， instead of the warmup claim。

We're going to prove that we again have a legitimate counting or rather overcounting of the Pareto curve。

 okay？So if we sum over the slices tea and over the item's I。

I claim that we get an upper bound on the freto curve。 And here， quality doesn't hold。

 Okay here we really are going to be overcounting。 but that's fine。

 We just want an upper bound on capital N。Okay。So let me prove the claim to you。

And then once we have the claim， it'll be reasonably straightforward to finish the proof。

And the reason it's going to be straightforward is because these N I Ts are actually something we can reason about directly。

 given our smooth hypothesis。Okay， so again， the high level proof， you know。

 the proof plan is the same as before。We just want to say consider any Pareto optimal solution。

 So it contributes to the right hand side。 We just have to show that it contributes to the left hand side as well。

 That is we just have to exhibit a choice of T and a choice of I so that that N I T is equal to one。

 Okay and more， that for each distinct Pareto optimal solution。

 we identify a difference pair I T that accounts for its contribution okay。So。

So it's enough to show that。For each pureto optimum solution， S。

So the T is going to be chosen the same as before。T is just going to be the boundary right to the left of S。

So we just want to show that there exists in item I。Such that S equals SIT。

The only thing to remember when I write that down is S I T is just this thing that the N I T is counting whether or not it's there or not。

 Okay， so N I T just says that， you know， some solution defined in some way shows up in the sliced T T plus epsilon。

 okay。Again， we're assuming that each slice has only one preto optimalmal solution。

 so we're not going to charge more than once， so for a given T there's only one possible preto optimalmal solution that will point to T as being responsible for it。

 and we just have to exhibit an item I so that indeed we are charging that preto optimalum solution to this pair I and T。

Okay。All right， good。So here's how we do it。And it's a refinement of the proof that we had last time。

So first of all。So we have our S。It's right next to T。So with the first step。

 let's just do what we did last time， look to the left。

Find the first part of optimal solution you see looking westward， call that piece of tea。

So piece of tea。Is just the highest。Nly， the max value。Solution。To the left。

 so with weighted most tea。And we denote its value by v sub T。Okay。

So it's the same thing as it was before， piece of tea。Now。S， because it's preto optimalmal。

 and because it has higher weight than PT， S has strictly more value than PT。Okay。Therefore。

 there's got to be at least one item。Which is in S， but not in P of T。 It's got more value。

 There's got to be some item， which is the reason it has more value。 Okay， it's not some subset of。

PT。Any one of those items is going to serve as our magic item I。Okay。So since S is preto optimal。

With weight bigger than tea in particular， weight bigger than piece of tea。

Value of S is bigger than the value of PT。And so there exists an I。That lies in S。

But not in piece of tea。Okay。系。So。So remember， we started with the Pareto optimal solution S。

 How did we choose T， That was the boundary just to the left。 How did we choose I。

 We picked an arbitrary item in the Pareto optimalmal solution S and not in the next Pareto optimal solution looking west。

 looking left。So given S， we chose I， we chose T。We're going to show that for that choice of INT。

 indeed。The indicator of random variable N I T counts the proto optimal solution capital S。

 And that's just what we needed。 We just needed to show that， look， for each choice of I and T。

 we're counting whether or not something exists。 And we just wanted to show that everything on the right hand side is covered by somebody in the lefthand side。

 So we could taken an S。 I've shown you the I。 I've shown you the T。

 All I have to argue is that N I T equals  one。Alright， so for such an eye， I claim the following。

So first of all。I claim that PT T and P， I T are the same。 Now， what are these things。

 I know you've forgotten。Alright， so P T， that's just this。 Okay， we looked westward。

 We found the highest point we could find， okay。What was P。 I T， So that says， oh， by the way。

 I also force you to exclude I。Okay， so this is the thing that might or may not have been equal to P T。

 It depends Okay， whether or not the optimal solution with weight at most T needed I or not。

We've chosen I， so that。The optimal solution to the left doesn't contain it。Okay。

So this restricted optimization problem， P， I T， so the max value thing excluding I is actually the same as the max value solution unrestricted。

That's my choice of I。Okay。So that doesn't matter， excluding I or not。 we get the same thing。Then。

 of course， it means that the values are the same。Because it's just the same set of items。

 items just have some value so you get the same set of items。So， that means。

When we think about the definition of SIT， which I'll remind you of what it is in a second。

It doesn't matter whether I write V I T or VT here。 It's the same number。Now， I claim that。In fact。

S I T， the thing that N I T is counting。 Okay， S I T just equals S。

 the preto optimal solution with which we began。 Okay， If I can argue 3， we're done Okay。

 because then they really says this preto optimalum solution is accounted for in the indicator random variable N I T。

So why is this true， Okay， well， let's remember what the definition of this is。 Okay。

 so what is this thing doing。So SIT says， okay。Find the minimum weight solution whose value exceeds some threshold。

 Okay， in this case， the threshold is just the value of PT T。 Okay， So in other words， and then also。

 it has to include item I。O。Now， again， by our choice of the item I。

 when we look right to max to minimize weight， it doesn't matter whether we insist on including I or not。

 we chose I to be an item that the optimal solution includes anyways， even in the unrestricted case。

 okay。So that means， and this is just like in the warmup claim then。

So you look at right So so now you're basically looking to the right of T。

 you're looking for the first pro optimalmal solution that you can find。

 It doesn't matter whether you're forced to include I or not forced to include I And there is S sitting there in the first available slice between T and T plus epsilon and that's exactly what's triggers this event。

 what triggers this event is looking to the right。 Do you see what you're looking for in the first available slice。

 or do you see it further more to the right。 Okay S is right there in the first available slice。

 We chose T to be the immediately to the left of it， So S， because of S is presence。

 because it's equal to S I T， this will be equal to one。So， therefore。NIT is equal to one。Alright。So。

That's why it works。It feels like I think it's going to be a loose bound。

We're going to be over counting S like many times for each item Ab right。

 So it could be off by a factor of up to little n。Yeah。I completely agree。Although like I said。

 at the end of the day， the bound we get is tight， so it will overcount in some cases。

 but overall it only matters by a constant factor。All right。

 so that's sort of a so there's two very clever parts of the proof that interface together。

 you've seen one of them， this fact that if you look to the right and you look to the left and you choose this eye carefully。

 you can get away with imposing these extra constraints you can impose the constraint that you exclude the item when you look left。

 you impose the constraint that you do include it when you look right and it actually doesn't change the optimization problems if you choose the item I just so if you choose it to be something that's in the right the sort of easternmost preto optimal solution and not in the one on the west。

Now， why is that useful， thatll become clear in a second。All right， so having proved that。

We can now forget about it。And the point is， given that this claim is true。

 it reduces upper bounding the size of the prato curve。To upper bounding。

 the expected die of the left hand side。嗯。And by linear of expectation。

 that just means we need to understand the individual expected values of the N I Ts。 Now。

 the N I Ts are indicator random variables。 So really。

 what we need to understand is the probability that a given N I T equals 1。All right， so to finish。

By linear of expectation， we just need to prove。That the expected value of NT is at most。

Epsilon over Sigma。For all I。Let me ask you。How many different such random variables do we have。

How many choices do we have for I。明白。N items， right， So N choices for I。

 How many choices for T do you remember。It's been a long time。N over epsilon。

 right So we had the total weight range from 0 to n split up into multiples of epsilon， okay。

So there's n squared over epsilon terms on the left hand side。Okay。

So if we prove an upper bound of epsilon over sigma for each。

 then that gives us a bound at the end of n squared over sigma。Since end times and Repson。

Choices for IT。OK。So as promised， the epsilons are just going to cancel。Okay看。

Does Evan agree with that？If we can prove this for every single I T， just by linear of expectation。

 we got our n squared over Sigma bound。So I。e， we want to prove that the probability。That。

NIT equals one， also known as that。SIT is in T T+ epsilon。Is the most epsilon over sigma。Okay。

All right。So S I T is wherever it is， or may or may not be in the slice T T plus epsilon。

 Let's figure out the probability that it is in fact， in that very slice。All right。 And now。

 basically， all the work we've done so far has been in service of making this last step easy。Okay。So。

Fix I& T。And we're going ahead go ahead and condition。On all of the items weights。

Except for the weight of the I item。Okay， so we have n items。 All of them have random weights。

We're going to leave just this one residual random weight。 The other n -1 will fix。

 So we're going to prove the stronger statement。Of an upper bound on this probability for every possible fixed setting of the weights other than I。

 In other words， the item I alone has enough randomness to allow us to prove that this bad event is unlikely。

This is very similar to what we did last lecture， when we had these eight coordinates and we fixed seven of them and the eighth one was enough randomness to have the probability of a bad swap be small。

 Okay So again， so we're just we're boiling it down to just a single random thing。好的。Now。

Here's where things get really nice。 Okay， here's where sort of the genius of this proof really starts shining through。

The only thing that remains random is the weight of WI。Allright。So I claim that actually then。

Even though it seems like S I T is a crazy， complicated definition， actually。

 this event's super easy to understand。 Okay， with everything fixed， except for eyes weight。

So let's just go through step by step。 How is S IT defined。

 So the first thing we do is we look to the left of T。And we say。

 what's the optimal solution that excludes I， the max value solution that excludes I？

So this is optimizing only over solutions where I is not a member。

I is the only thing that's random at this point。 Okay， so we have fixed values。

 We have fixed weights。 Okay， so we know exactly which solution P I T is at this point。

 I it's deterministic。So PiT is fixed。And that's because that's by its definition。

 And this is now you're seeing why we defined it this way。

The reason we wanted to exclude is because we wanted these to be just deterministic。And so therefore。

 also， VIT is fixed。Okay， so the values are always deterministic。 So once you know the items。

 you know the value。 Okay， So P' is just a set。 V is just a number。Now let's look at SIT， okay？

So what do we know about SIT？So for S I T， it says， well。

 we are only going to consider solutions that have sufficiently high value。 Okay。

 but V I T is fixed as deterministic and values are deterministic。

 So we know exactly which subsets of items have value strictly bigger than V I T。Okay。Moreover。

For solutions that include I。Now， it's true that we don't know exactly what the total weight of one of these solutions is。

 right， because eye is still random。Maybe it's 17， maybe it's 23， who knows？On the other hand。

 think about taking all the solutions that include I。And sorting them by weight， or put differently。

 just think about the relative order and total weight of everybody that includes I。Okay。

This ordering， total ordering on solutions that include I， we know completely at this point， okay？

And that's because there is only one item， which is random。 That's item I。 It might be 17。

 It might be 23。 It might be 47， but it's 17 or 23 or 47 for everybody。

 Okay so we look at the solutions that include I。 We look at their total weight for stuff that doesn't include I。

 We sort them in that order。 That's still their relative order once we put I back in。

 Okay because it has the same value for everybody。So four solutions that include I。

The ordering by weight。Is fixed。Okay。So what do you think？SI T， is there any randomness left in S IT？

Think about it。 Think about it for take 60 seconds to think about this。 Okay。

 I'm just asking about which。 So remember， S I T is a set of items。 It's something like items 4。

7 and 10， okay。And I'm asking， at this stage， is there any uncertainty left in in what the set S I T of items is。

Who votes， yes。Who wrote and no。Okay。And I guess it was a good question。 There's some disagreement。

So let's try to argue why just in terms of the set SIT。

 why it's actually completely fixed at this point， where there's actually no uncertainty about what the set SIT is。

All right， so first of all， who's eligible to be a set。Of S I T。 So you've got to have item I。 Okay。

 that's deterministic。 You give me a set of items。 I know whether eyes in it or not。

You have to have total value， at least VIT， okay。We argued that V I T was known。 Okay。

 that's just a number，1024， whatever。And， of course， the values for all of the items are just no。

 they're not random at all。 Okay， so you show me， So given that this is just some number。

 you give me a set， I know whether or not it satisfies this condition or not。 Okay。

 so the feasible solutions， if you will， the subsets of items that satisfy constraints 1 and 2。

 is fixed。Moreover。Their ordering by weight is also fixed。

 We don't know this is what this is what we don't know。

 We don't know exactly what the total weight of a given subset is。

 but we do know its's total weight modulo item I。 And that's enough to know the relative ordering。

And so what is S I T， it says amongst all of the subsets which satisfy properties 1 and 2。

 which is some deterministic list。 Find me the one with the smallest weight。 Okay。

 and that's the property only of the relative ordering by weight。Okay说。

So this is where things glue together just beautifully。

 so conditioned on all weights other than the I1， we know exactly which item set is S I T。😊。

So SIT is fixed。Okay。So what is unknown， only its weights。Which has the form X plus WI。Its random。

Okay， so capital X here denotes the sum of the weights of all of the items other than I in S I T。

 Okay， so that's fixed。 And then there's the random weight of W Y。Okay， so， O。

 now what was the event， Okay， so the original event was the probability that some random subset falls in some slice。

 okay。呃。I see。But I guess I should say the value of。Anyways， yeah， you know what I mean， Okay。

 so that the weight of that lies in a slice T T plus epsilon。Weight of S。

And so initially when we look at this event， what seems so intimidating is not so much you know the randomness in the weights。

 but rather the randomness in who SIT is right so we have this elaborate labyrinth of definitions leading up to some crazy definition of what ST was。

 that's what seems scary Like how do you know whether this is items 4，7 and 10 or at 6。

7 and 12 or whatever And what we're actually saying is actually at this point we know what the set of items is And moreover。

 there's just one random weight left。So， of course， if you tell me that。

 if you tell me exactly which items these are and the only question is whether it lies the total weight lies in this interval or not。

 now it's exactly set up。 It's exactly in the wheelhouse of our smooth analysis assumption。

 right This weight is random。 The density on any given point is at most one over sigma。

There's a lid big measure only epsilon in this interval。

 so integrating over all of the different values for the weight of item I that would send the total weight of SIT into that interval。

 we get at most epsilon times1 over sigma。So。Since F X。Atmost one over sigma for all x by assumption。

The probability is at most， the interval width。Times the density， epsilon over sigma。

So that's the proof。Okay。And so again， I mean， it's really a masterful。

 sort of a master class in how to， cleverly organize the accounting or overcounting of something。

In a way that you break it down into these little pieces。 So for each little piece。

 it's actually very easy to relate it to the randomness assumption on the input that you have。 Okay。

 So like I said， I don't think it's an accident that there were some weaker versions of these results proved first。

 This wasn't sort of the first proof that people working in the field came up with。

 This is more kind of the proof from the book after they understood it really， really well。

I the final comment。 So this was just fornapsackack。

 So there were effectively two linear objective functions。

 you were talking about the weights and you were talking about the values。

 So just in the past few years。 So since the last time I taught this class。

 there's been some very impressive followup works where they talk about higher dimensions。

 So you can talk about crto curves， of course， not just in two dimensions。

 but in multiple dimensions。 So now one point would dominate another。

 if it's better in every one of deco coordinates。 So you're undominated if for each other point。

 you're better than it in at least one coordinate。And so there。

 so what happens is you get and you get that the preto curves get bigger with the dimensions。

 exponentially in the dimensions。 but at least n is still polynomial。

 So if you have D linear objectives， here we had N squared over sigma。

 And there the upper bounds become Everything just gets raised by D。

 So it's N to the 2 D over sigma to the D And it's known that that's close to tight。

 So you need the sigma to the D dependence and it's known you need n to the D dependence。

 So the only gap is between N to the D and N to the 2D。So that's， you know。

 so there was a paper by Mort and O'donnell in Stock 2011。

 There was a paper by Roglin and a coauthor in Stock 2012。 So this is stuff that you know。

 people are just doing some very impressive new results just over the past few years on exactly this problem。

 Okay but this is kind of， you know， if you just wanted to know one result in the field sort of in this subfield。

 I think this would be the one about Pato curves and squared over Sigma。Any questions？

So Monday will be our probably our final smooth analysis lecture。

 and that will be just really about one theorem。 That's a very cool theorem。

 which is more in the spirit of complexity of algorithm。

 So really understanding properties of problems rather than properties of algorithms。

 And it's in some sense， a generalization of thisnapssack results。

 So we're going to study problems which are solvable and pseudoponomial time。

 So that's a generalization of Napsack， which is solable and pseudo polynomial time。

 And we're going to show that within a certain class。

 whenever you have a pseudo polylynoial time algorithm。

 you automatically have polynomial smooth complexity。 And not only that， but there's also a converse。

 So if you have polynomial smooth complexity， then you're also solvable and pseudoponomial time。

 So it's almost like a novel type of complexity class solvable and pseudonomial time equals solvable in smooth polynomial time。

 So that'll be Monday。 Have a good weekend。😊。