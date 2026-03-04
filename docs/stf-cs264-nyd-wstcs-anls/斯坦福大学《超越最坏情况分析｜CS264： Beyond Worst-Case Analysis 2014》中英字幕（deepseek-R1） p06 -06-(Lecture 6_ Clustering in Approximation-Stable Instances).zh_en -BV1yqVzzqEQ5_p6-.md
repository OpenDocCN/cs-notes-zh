# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p06 -06-(Lecture 6_ Clustering in Approximation-Stable Instances).zh_en -BV1yqVzzqEQ5_p6-

Today we're going to begin a series of lectures on clusterings。

 So this is one of the motivating problems that I mentioned back in the very first lecture Inally。

 the goal was to somehow find meaningful clusterings and the hope is that in instances that we care about where meaningful clusterings exist。

 we can have novel algorithms that exploit the structure that the existence of those clusterings implies。

 So today we're going to talk about results from a paper of Balk and Blum and Gupta there's actually been an explosion of work on this topic over the past five years we'll be serving not all of it。

 but some of the rest of it over the next couple lectures as well。

 but this is the one that we'll focus on today。So we're going to be thinking about metric spaces。

 Okay， so meaning points that have a notion of distance between them。

So the computational problem is going to be defined by an endpoint metric space。

So those are said capital X， these are the points。And then there's a distance function， D。Okay。

 so D assigns a non negative real number to every pair from X。 So， for example， maybe X。

 Maybe that's a bunch of images。 Maybe D is some function you've concocted。

 which says how similar or dissimilar to images are。 Okay， So remember， in the metric space。

 the really， the key property is the triangle and the quality。

Which just says that the shortest distance between any two points is a straight line。

So adding an intermediary stop Z between x and y can only make things take longer。

So we'll use the tringlineequ several times in today's lecture the other things are just at symmetric so the distance from x to y is the same as the distance from y to X。

 and then usually you say that the distance is zero if and only if the two objects are identical that's not really going to be important so tringlineality is really the thing to remember okay。

All right。How do we formalize this idea of finding meaningful clusterings， You know。

 when you talk about algorithms， you talk about optimization， sometimes their're objective functions。

 their optimization problems， which you can take very literally。

 So sometimes really the problem you're trying to solve for the company is to figure out like the minimum cost way of accomplishing some task over a set of feasible ways of doing it。

 And then you literally care about that objective function value。

Then there are other problems by clustering。Where the goal is more qualitative。

 you more want coherent groupings of points that make sense right so you want to throw in a bunch of images to an algorithm and you want it to tell you which are the cats and which are the dogs。

 you want to throw in a bunch of proteins and you want it to correctly tell you you wanted to group these proteins by their function so that's not really there's not a numerical objective function that you might obviously define for that problem。

 or rather there's several you could try。So the point here。So the goal is qualitative。

I'm not going to write it down again since it's right here。Compute meaningful clusterings。

 And if you approach this problem， as many people do by positing an objective function。

 positing an optimization problem， and then solving it。

 you care about the solution to that problem only in as much as it comes back with a meaningful clustering。

 you do not care about the objective function value of the solution per se， you could care less。

 Conversely， if you solve it optimally， and the optimal clustering under the objective function is meaningless。

 you don't care。 Okay， does you know good。 Basically。

 that would just tell you that you phrased the wrong question okay。So。

How are you going to grapple with this？So how can we have some kind of theory which strives to find these meaningful clusterings。

 Well here's the first assumption。We're going to assume that， along with this metric space。

 which we know， there is something which we don't know， namely a target clustering or a ground truth。

So we're going to assume that this exists， we don't know what it is， and we'd like to find it。

 given this distance information。Okay， so that's the first major assumption，All right。Again。

 for example， you really want。 Maybe there is some division into cats and dogs， Pro by function。

 etc cetera。 And really， historically， in pure optimization， this isn't so much how people think。

 right， So， so one of the contributions of Balk and B and Gupta， they weren't the first to do this。

 But theyre really kind of highlighted this point。 know， which is， look， in other fields。

 There are these notions of ground truth。 Let's try that in the sort of formal theory of algorithms and see if we get interesting questions。

 And we do。So。So the goal then。As we want an algorithm， a polynomial time algorithm。

That approximately ideally， we'd love to recover this exactly。 realisticistally。

 we're going to try to recover it approximately。So that's what we want。Now。For us for an algorithm。

 have any hope。Of accomplishing this goal， there have to be some clues in the input。

 There to be some relationship between the input that you're given and what the ground truth clustering is。

 right If it's just some secret that has nothing to do with the input。

 you're not going to be able to just guess it out of thin air。

 So we need to then introduce a relationship between what the input looks like and what the ground truth clustering is。

 So the big assumption or like the key definition is a formal link between these two。

So I'll state it informally first。So the assumption is going to be that every near optimal clustering。

 And here， when I say near optimal， I mean， in the sense of some objective function。

 and I'll tell you the objective function in a second。So with respect to an objective。ok。

So every near optimal clustering。Is close to the target。

In the sense that it clusters the points in almost exactly the same way。Okay。

So what the assumption is saying， it's saying if you compute a clustering， which is numerically。

 according to some objective function， almost as good as the ground truth clustering。

 then that implies that structurally it is also almost as good as the ground truth clustering。

 so approximation of a numerical objective implies approximation in the structural sense。

 the classification sense so that's an assumption。One way to think about this or a very cartoonish way to think about this。

As we somehow want the right answer to stick out， we don't want there to be any kind of， you know。

 Second best alternatives that might confuse us too badly。

 So if you really just think about sort of plotting a single function。And again， this is。

This is just a cartoon。 But you somehow imagine that different points on the X axis are structurally similar。

And you imagine that this is some objective function that we want to maximize。Well， clearly。

 the highest this gets is right here。But importantly， the only way you can get close to the maximum。

 so say anywhere above this curve。Is to be somewhere in the domain。

 which is close to the maximum point。There is no， for example。

 local maximum that's almost as good very far away from the global maximum， okay。

 there are other local maximum， but they're kind of quite a bit worse than the global maximum。

So this is one way you can like just in a very cartoonish way， think about this。

 So if you get close to the maximum， you get close。In value， you get close to the optimal in。O。

So that's the idea。 All right， Yeah， So the target You know， it actually doesn't matter。

 but it should be， I mean， so it's not going to matter。 go ahead and think of it that way。

 And we'll actually just explicitly assume it。 But it's really for ease of exposition。

 So think of the target as being the optimal for optimization problem。

Something like clustering in cats and dogs， it seems like yourre like the optimal is。

Like not so much better than all the other solutions。

 like if you' off by one cat or two cats or three cats。Okay it kind of。That's a good comment。

 Excel comment。 So that's why， so， I mean， so certainly right。

 So if you take this is exactly why we want to have all these approximations。

 It's an excellent comment， which is if you take the best clustering。

 and then I just kind of move it a little bit， it's still gonna be a great clustering。

 It's also still gonna to have a great numerical objective function value for reasonable objective functions。

 So a different way of saying it is So it's clear that you So a stronger statement would be。

 you know， you have one optimal clustering numerically and nothing else is even close to it numerically you'd love to just say。

 oh， as long as you you get you have this huge gap。 And your argument is showing that's too strong。

 if you take an optimal clustering and you perturb a little bit。

 you're going get something which is almost as good。

 So that's why we need to kind say the only way you can be almost as good is through that kind of perturbation process。

 the only in your optimal solutions or small perturbations of what we want。

 as opposed to taking the optimal solution doing some massive rearrangement of everything and then getting something almost as good。

 That's exactly what we want to exclude。😊，支。So。This is not math yet。 So first of all。

 this definition only makes sense once you've you know settled on an objective function。

 So we're going to use one of this standard clustering objective functions。

 There are analogous results for other objective function， other popular ones as well。 Okay。

 but for this lecture， we're just going to。Focus on one of them。

 which is called the K median objective。Basically， the K meeting objective is the sum of the nearest neighbor distances okay。

 so we're going to be picking K clusters， each cluster has a center。

 every point gets assigned to its nearest neighbor cluster。

 and then we just add up the resulting nearest neighbor distances we want that to be as small as possible。

So， formally。The goal。Is we choose a set。S of K centers。

 so these are points from the metric space that we now designate specially as centers。

And then we look at the rest of the points or we look at all of the points。

 and we look at the sum of the nearest neighbor distances。 so for a given x。

 I look at the minimum over all of the centers。Of the distance between x and that center。

So this is the objective function。You want to choose S。

 You want to choose these K centers so that if everybody's assigned to centers in the obvious way。

 by shortest distance， then the sum of the distances as small as possible。

So we want these like tightly knit clusters。So we want all these distances to be small。

 that means they're these tiny little clumps。So this is not there is no sort of unique batch clustering objective function。

 but this is definitely amongst the top two or three most commonly used ones。

So if you're a fan of Kas instead， you can also derive results。 know， the details are different。

 but the same theory can be executed for something like the Ka' objective function。

So any questions so far？All right， so let's continue making this idea precise。

That numerical approximation of now we know the K median objective function。

 we want to translate to structural approximation。So here's the formal statement of the key definition。

That of being C epsilon stable。So we say that a given target clustering， okay。

 so we have a metric space。We have a target clustering。

 We're thinking about the Canadiandian objective。 And we say that the target clustering。

Is C epsilon stable？If。Here's C here is at least one。If every C approximate。Okay clustering。

Meaning every solution to this problem where the objective function value is no more than a C times the minimum possible。

Every see approximate K clustering。Agrees with the target。

On almost all of the points and the a1 minus epsilon fraction。Okay。

 so I'll also occasionally say this is an epsilon accurate。Coster。你看。So one quick detail。

🎼So if I just give you， So a K clustering just means a partition of the points set into K groups。

 Okay， that's what I mean by K clustering。 I should say。 So for this whole lecture。

 we're gonna to be thinking of K， the number of clusters is known。 Okay。

 which one often doesnt practice。 Perhaps you have domain knowledge。

 which So you have a guess of what K should be。 You're looking for really just two groups。

 or and again， this is done in practice a lot。 You just run an algorithm for many different choices of K and see which one give you the best results。

 you basically do it 20 times and look at which one seems the most sensible。

 So think of K as known throughout this lecture。Okay。So one detail is。

 so what does it mean that two K clusterings classify the points in almost the same way。

 so suppose that give you one group of k clusters and another group of K clusters。

So if you think about it where you're like okay let's match them up。

 let's find the correspondence so that they agree as much as possible so you basically find a matching between these this partition into K groups and this partition into K groups and if two clusters are matched。

 you get one point for each data point which is in common to both of those clusters so you basically just take the correspondence between the two sets of k groups that maximizes the number of commonly classified points so that's what I mean by correctly classifying one minus epsilon fraction there's a way to associate the clusters in the first clustering the clusters and the second clusterings。

 say labeling them one through K so that for one minus epsilon fraction of the points it gets exactly the same label in both of the two clusters。

So that's what I formally mean by being Epsilon actor。Good。So。Quick question。

So does this definition or this requirement， does it get more or less stringent as I increase C。Mo。

So as I increase C， there are more and more clusterings that have to satisfy this epsilon accuracy condition so there's more three approximate clusterings and there are two approximate clusterings。

 So I'm insisting on this condition for more and more things。

 How about as I bring epsilon up does the definition get more or less stringent。Less。

 right because you can misclassify more things。So it's harder。

 sort of instances are less likely to satisfy this definition。

 the more you ratchet up see and the sort of more you ratchet down epsilon。

Any other questions about that？So I hope you see the correspondence， right？

This is the numerical closeness， and this is the structural closeness。

In an instance may or may not satisfy this property， we're positing， I'll say more about this。

 we're pousiting that hopefully real world instances have this property。

 the ones that we would like to solve， and secondly。

 instances that satisfy this property are somehow easier than worst case instances。

 that's sort of the high level high level points。All right。So one question is， you know。

 to what extent is this a reasonable。Definition， a reasonable condition。Oh yeah。

 I should give you some parameters you might want to think of these as representing。So， you know。

 these are just generic。 You can everything we say today。

 you can instantiate with whatever values you want。

 I always like to keep concrete instantis in my mind when I'm in a lecture like this。C。

 maybe think of C as 1。1。 so you're talking about 10% numerical error， clusterings。Think of Epsilon。

 I actually want you to think of epsilon as quite small。 Okay。

 I actually want you to think of epsilon as going to 0 as the point set goes to infinity。

 So if there's end points， think of epsilon as like one over root n。Okay。

 so misclassifying an epsilon fraction of the points。

 That means misclassifying epsilon times n points。 So if epsil is one of a root n。

 that's misclassifying a root end points。 If ends a million。

 it means I allow you to misclassify 1000 points。So those are the numbers you want to might want to keep in mind。

 C1。1， n equal 1000， and then epsilon equal1 over 1000。O。

So to what extent is this definition reasonable， to what extent is this definition useful？

So the first question might just be， you know， do you expect real data to satisfy this condition Okay and there's sort of different interpretations of that question。

 So first， you know， for a lot of parameter values， this is a pretty strong condition， actually。

 and we we'll sort of exploit that as we go through the lecture。

 So you if you mean do we expect real data to literally satisfy exactly this definition。

 Yeah maybe not maybe not complete。What's worse if you wanted to criticize it is， you know。

 you're not going to be able to check if a given data set meets this condition or not。

Because it's referencing these optimal solutions， which I'll say more about this in a second。

 which is NP hard to compute。Okay， so there's a strong analogy here with the recoverable value for independent sets we talked about Monday。

 The parameter there， the condition there was basically saying the optimal independent set should have low degrees because we didn't know what the optimal independent set was。

 So it's sort of a faithbased analysis。 We're just saying， well。

 whenever the instance has this property。 And maybe for other instances as well。 But certainly。

 whenever the instance has this property， well do well。

So those are some criticisms is that taken literally it's pretty strong。

And you can't really check it。 Now， on the other hand， and it's several things in its defense。 Okay。

 again， like the recoverable value， there is at least some kind of plausible narrative about why real instances might at least be kind of nudging in the direction of a condition like this。

 Okay， so what would it mean if this is false。 Okay。

 for something doesn't have the stability property。

 It means you can have it two structurally very different clusterings that give you basically the same objective function value。

And the claim is that probably wasn't the kind of clustering instance you were hoping to set up and solve。

 right， If you're trying to classify cats and dogs and， you know， there's a 10% of the cats。

 which if you put with the dogs and then conversely， temperature of the dogs should with the cats。

 And that's just as good an objective clustering according to your objective function as the perfect classification of cats and dogs。

 you probably screwed up the problem formulation or your data is quite noisy。

 Okay so that's sort of the know， plausibility argument。 when this fails。

It doesn't really gel with our intuition about kind of the， you know。

Target clustering that we have in mind in our clustering formulations。

The other thing I want to mention is， just like with a recoverable value for whatever criticisms it has。

 at the end of the day， it naturally LED us to design this completely new algorithm。

 this algorithm where we took the random permutation， and then we sort of have this forest。

 and then we computed exactly in the forest。 No one had ever thought of that algorithm before。

It's not， it's not。 I'm not going argue you need the recoverable value to come up with that algorithm。

 but it definitely LED people to a new algorithm that that seems potentially useful for a 50 year old problem。

 So remember， at the end of the day， the way to evaluate， some kind of condition like this。

 as you say， does it help us， first of all， understand existing algorithms better。

 We won't really do that with this definition。 Second of all。

 does it guide you to potentially useful algorithmic ideas。 And in that sense。

 I'll try to convince you that this this has been a good definition。So those are。

 that's the sort of merits and demerits of this， I think， on the reasonableness access。Okay， so。

What should we be shooting for？What would be an interesting result？

About recovering clusterings in C epsilon stable instances。 Well， let me show you what's easy to do。

So suppose。You have just off the shelf， I suppose you just sort of Googled K media approximation algorithms and checked out。

 you know some nice algorithms people designed in the 90s and last decade that run in polynomial time。

 because there' is an MP hard problem， I'll say more about that in a second。

 but so there are algorithms that run in polynomial time are guaranteed to output a solution that's at most C times this then the minimum possible for reasonable constant C C like three even a little bit less。

So if you run one of these algorithms。So suppose you run a C approximation algorithm。So again。

 this means guaranteed to always produce a solution no more than C times as costly as the optimum。

If you run such an algorithm。On a C epsilon stable instance。Well， then。

By the definition of C epsilon stability， you're going to get back almost the target cluster。 Okay。

 just by definition。 Okay， we've assumed that all such solutions in this instance。

 are epsilon accurate。So yields。An epsilon accurate cluster。Okay。

So think of C as like three for this state。So that's a general purpose algorithm， okay。

 it gives you a three approximation whether it's a stable instance or not。

It just so happens that if you input a stable instance。

 you get this very nice interpretation of what it does。So for this， we don't have to do anything。

This is really just a reinterpretation of known results。

So if we really want to say that this definition led us to come up with new algorithms in the spirit of the recoverable value。

What seems like the interesting。What's kind of would be interesting would be to get。

 would be to recover。Target clusterings for even smaller values of C。

Then what general purpose approximation algorithms can。And there is hope。

That specialized algorithms tailored to stable instances could go beyond general purpose algorithms because there are barriers to how well you can approximate k median on worst case instances。

It is known。For comedian。To be NP hard。To approximate。Better than one plus2 over E。Where here E is 2。

718， et cetera。O。So this is probably something like 2。7。4。Or something。sorryrry， 1。74。Okay。

It's not known how to get 1。74。 when you get pretty close。 Okay， it is known how to get 2。

7 or something like that。11 plus root 3， if you must know， is what's known on the upper bound side。

 okay。But to the point is， if you say， well， you know， so remember。The bigger C is。

 the more stringent the assumption。 Okay， so there's going to be instances which are 1。

5 epsilon stable for somebody of epsilon and are not too common epsilon stable。Okay。

And if you're only 1。5 epsilon stable， this basically says， you're out of luck。

There will never be general purpose camedian instances so that itll guarantee recovery of your target cluster。

 your stability condition just isn't strong enough。

So using general purpose algorithms gets stuck at 1。74。So if we want to be able to recover below 1。

74， we need necessarily， unless we're going to prove people equal NP P。

 we need to develop algorithms that are just they have to be new， okay。

 they have to be tailored to take advantage of whatever special about stable instances okay。

And again， we had analog on Monday where we had this recoverable value。

 we had the randomized greedy algorithm。 It got a constant of one。

 It was no better than one to beat one。 we had to come up with a new algorithm。

 I ever seen exactly the same thing unfold here。Okay， so that's the goal。

So that's what we want to do this lecture。Okay。Okay。

And I'll show you that we can actually do this for arbitrarily small， fixed constants C。

 as long as n is going to infinity， and epsilon is going to 0 with n。 Okay so we can get， you know。

 we can do 1。1， for example， which there's no way you can do it via general purpose algorithm。Okay。

So that's the， that's the really good news。2。So any questions about what we're trying to do？

So it's pretty much like agnosastic of excellence。Good question。The answer is subtle。

 so I'll answer that explicitly， but let me get there。Yeah。Good， right， So in our minds。

 we're thinking that， you know， we're only operating on these stable instances。

 the hope why we might do better。 Well， if there's a meaningful clustering， presumably。

 that means there's extra structure in the instance。

 maybe we can detect it in algorithm and exploit it to do better general。

 then on worst case instances。 That's what we're hoping is true。I want to just digress briefly。

To compare and contrast what we're doing right now and what we're doing in this lecture with the parameter analysis I was talking about in the last couple of lectures。

It's similar， but there there's a slight difference， especially in just kind of mindset。

That I want to be clear about。So for parameterized analysis， think as a canonical example。

 our discussion of LRU and when we parameterized page requests by the locality and then gave a page fault rate upper bound that was parameterized by the locality。

So。The L U algorithm， we didn't need to define that locality measure to come up with the LU algorithm。

 Okay， people came with the L U algorithm a long， long， long time ago， and that parameter was。

 you know， it is like 10 years old， okay。So you can't say that the LRU algorithm is in any way depends on that parameter or is tailored to that parameter。

 okay， the LRU more like the algorithm more so it's clearly well defined and correct on every single page request sequence。

 it just sort of auto tunes to whatever degree of locality the page request sequence has。

In other words， the parameter that alphas sub FFK， we used it only in the analysis of the algorithm。

 not in its description or its design。Today will be different， okay。

I've defined a property I've posited a possible property of real world data。

 Okay but we're actually going to design an algorithm。

 which we basically probably would never have come up with。 had we not written down this definition。

 Okay， so there's a sense， an informal sense in which the algorithm will'll discuss today。

 really is explicitly exploiting structure and data。

 rather than being well defined everywhere in sort of auto tuunning to any structure that there might happen to be in data。

So with parameterized analysis。I talked about how it's basically like a projection of the input space onto a line。

Where the line indicates the easiness or difficulty of the input。

 and then does you just have whatever performance you have as a function of that parameter。

And really， a few of the algorithms we're going to see now， including today。

 this is a little bit overstating， but it's almost as if。

We have the instances that satisfy whatever condition we have in mind， C Epsilon stability。

We're going to analyze our algorithm。Only here。Okay， so our mindset is like。

 our responsibility as an algorithm designer is only to do a good job on the instances that meet this definition。

 because we're thinking of these as the important instances。And for the other instances。

 basically we're allowed to se fault。In effect， I mean， the algorithm will be much， you know。

 will behave much better than that。 But in our mind， we think， you know。

 if you gave us something else， you violated the promise that this was all I had to do。

 So all bets are off about the execution of my algorithm。 And indeed。

 these are actually often called promise problems in complexity theory for that reason， okay。

So that's a real shift in mindset。 All right we'reulating we're articulating structure of wear world data not to explain empirical performance of some algorithm。

 but rather to exploit explicitly an algorithm we're going to design。So is it from。改ずでテ究。

An instant has to table。Right， so that was the discussion over here。 So no。

 clearly not because it references the optimal solution。

So just like for the recoverable value on Monday， that was an unshckable condition in polymo time because it was talking about the optimal solution。

Our algorithm。 So kind of bad Good。 So here's the good news。 So here's the good news。

 So the good news。 you're right， this point is worth making explicitly。

 So we have this kind of faith based belief， in effect that the world looks like this。

 that these are the instances we're responsible for。 Now。

 suppose we can actually determine whether our algorithm succeeded or failed。

 And that's actually going to depend on the algorithm and depend on the problem。

 But the easy case is when we can tell whether or not we succeeded or failed。 All right。

 So we run the algorithm， in an instance。😊，We don't know whether or not it satisfied the promise。

But either our algorithm works， and we're happy。Or it's seg faults。

 And then we know that it was not one of those inputs。

 because we guaranteed correct good performance on all of those inputs。

As out that's an employer problem。Well， but we're not deciding it either way。 We might work well。

 despite the fact that the input does not satisfy that condition。But the point is。

 we'll work well on only a superet of what we've proved。So yeah。So it works out in our favor。

So again， this is， this is in many problems and many that will see， this is a very fruitful approach。

 Okay， it's really， you get a lot of mileage out of defining conditions like this。

 explicitly designing algorithms that make use of them。

 improving guarantees on the subset of instances where the membership， you cannot check。

 I just want everyone to be totally clear on that there are these sort of。😊。

I don't even know if I want to call them drawbacks。

 but just there's things you should be aware of about the approach。 Okay， but like I said。

 the ends can justify the means。 Okay， if you get better understanding about algorithms or new algorithmic ideas。

 it was a worthy exercise， whatever the flaws， okay。Good。Alright， so。

I'll leave that there for a second。So that's the goal。 I'm going to show you an algorithm。

That recovers the target clustering up to epsilon。Basically， no matter how small C is。

 C should be bigger than1， think of it as again， 1。1。As one typical value。All right。

So before I describe anything about the algorithm， I want to examine some consequences of this stability assumption we're making about our input。

 Okay， so here's， here's the thing， right， There's a stability condition。 We're assuming it's true。

 but we can't check it。 So we need to somehow build a bridge between this uncheckable condition and stuff that are pulling on the time algorithm can actually make use of。

So what we're going to do is we're actually going to examine logical consequences of the condition。

 which our algorithm can notice， clues about what these unknown optimal clusters are。

 So let me give you some preliminaries about what that structure is。

 Then we'll talk about how the algorithm can make use of them。All right。So。

Consider a stable instance。I hope you'll permit me a change of variable， C will become1 plus alpha。

 so c was at least one alpha is at least zero。And for simplicity。

 this is a slightly stronger requirement than over here。

 But I'm going to assume in addition that the numerically optimal clustering。

Is the target clustering。 Okay， on the homework， I'll ask you to explain why that basically doesn't matter。

 Okay It's just an epsilon versus two epsilon kind of kind of issue。 So assume。The target clustering。

Is optimal。And assume that the optimal objective function value， I'm just going to denote it OPT。

 okay？So remember what the K median objective function looked like。

 There is this sum over all of the points。Of a distance between a point and its nearest neighbor。

 Okay， so the objective function is the sum of n distances。 This is the sum of n distances。

So a typical distance is going to be opt over n if there's n points，All right。So a couple claims。

 pretty easy claims。So we want to say that stability buys us stuff。

So it means there have to be nice properties about the input metric X comm D。So first of all。

The claim is that。Most points。Are very close to their center。 Okay， so again。

 we're not doing an algorithm。 We're just doing analysis。 Okay。

 so thinking our minds about this optimal clustering of the points and fix it。

 We're just talking about what that has to look like， okay。So in that optimal clustering。

Most of the points。Are close to their center。What do I mean by close。 I mean。

 not too much more than a typical distance。So what's a typical distance。 Well。

 opt is the sum of n distances。 So one of those distances is opt over n。

 So not too much bigger than the average distance opt over n。Okay。So the distance between x。

It's closest center。 And again， remember， this means in the optimal clustering that we're thinking about in our head right now。

 closest center in the opt。So that should be not too big。

That's the optimal distance and will' allow it to blow up a little bit。对。Alpha over5 epsilon。

So that's the first nice thing。 So most points are pretty close to their centers relative to the average distance。

Secondly。Most points are actually much closer。To their center， then to their second best center。

So in the optimalum clustering， there's sort of an obvious best cluster for almost every point。

So the distance between x and its second closest center。And it's close to center。

 the one it's actually assigned to。It's not too big。Or sorry， know this is sorry。

 a lower bound on this， so it's much closer to its closest。to its second closest， meaning。

Strictly more。Then a typical distance times a constant factor。Allffolam。Okay。

So the picture you want to have in mind。Is that typical points in the optimal clustering have to look like this。

here's a point x。This is the center， this is near a center， the center gets assigned to an opt。

 so should be， this is short。If x is close， satisfy condition1。

 and then pick your favorite other center。Actually be very far from。Cpro。Okay。

So this should be long in the well separated case。So everybody's not everybody。

 but almost everybody's really close。Relatively speaking to their own center and really far away from the second closest center。

And of course， it's easy to think of point sets where this wouldn't be true。

 So we're already seeing how the stability of property is giving us highly nontri structure。In fact。

 if you believe this， basically what this is saying is that。This optimal clustering is kind of。

 really stands out。Really， you just have all of these different kind of far apart clumps。

 plus some small fraction of outliers。So it's really just saying it's kind of an obvious clustering。

 plus a few allies。 That's the interpretation。O。So is this statement clear， I'll prove this to you。

 proofs we' not hard。But where did the five come from。Where did the five come from？ Well， you know。

 it's a definition I can do whatever I want。 so I can put in a five if I want。

 The five will show up in claim2。There'll be a few claims yeah。

 so it's a good question at the moment， you know you should just think of it as you know， I mean。

 even when we prove one， it's clear we want to blow this up by some constant factor and the question is what should it be and when we you're actually doing this proof if you're like。

 oh well what else do I need What other part of the proof is pushing back and then you kind of put those together and the number pops out so。

Yeah， that's a fair question。 For the moment， it's a rabbit I pulled out of the hat。说完毕完毕。Okay。

 so proof of one。So one is one's pretty much trivial。

This is just what you could call this averaging or Markovs inequality。 Suppose one was false。

 So don't forget。 Don't forget what opt is。 Opt is the sum of n different distances， okay。

So what do we have here。 So here， we're talking about some of those distances right that make up opt。

 right， And if more than 5 epsilon over alpha N werere bigger than that。Well。

 then the sum of all of those， the5 epsilon over alpha would cancel the alpha over5 epsilon。

 that n cancels that n。 The sum of just merely these particular distances would be strictly bigger than not。

 but that's crazy。Because after was all of the distances。So if this was false。

 I'd just show you that subset of distances that's too big， can't happen it。So there's a reason why。

 you know， we have the N alphapha epsilon here，5。 and then we have the reciprocal here。

 It's exactly the same thing。Marco's inequality， averageaging。All right， proof of 2。

 its a little more interesting。So again， let's go by contradiction。So suppose otherwise that is。

Suppose even strictly more than epsilon end points failed to be well separated。 Okay。

 And remember if you're not well separated， it means this inequality holds the other direction。 Okay。

 it means your second second closest and closest centers are not to you're sort of relatively indifferent between your closest and second closest。

So we， we need to have a contradiction。 So obviously the contradict is our stability。Assumption。

So start with the optimal clustering。Again， remember， this is just just in the proof。 Okay。

 so we there is some optimal clustering。 Start with it。Take the points which are not well separated。

Okay， so these are points where they don't care a lot。

 whether they go to their first closest or second closest center。 So just reclassify them。 Okay。

 so I'm going to take opt。 I'm going to modify it a little bit。 Actually， I'm going modify it a lot。

 but the objective function won't change much。 So that violates the stability condition， okay。

So specifically you start with the off clustering， reassign。The strictly greater than Epsilon N。

Non well separated points。To their respective second closest centers。So what does that yield？

You know，And so when I say， you know， I hope it's clear。

 when I say reassign a point to a different center。

 that's the same thing as just sort of giving it a different label。

 If you're thinking more from like a classification perspective。 Okay。

 so I just label them with the second closest label。

So what does that give is it gives us a new clustering？Okay。

 so it disagrees with the optimal one on strictly more than an epsilon fraction by design。

 I took more than an epsilon fraction。 and I reassign them。 Okay， so it's different。

And how much does the objective go up by？Well， it's a most the old objective。

 and I started with the optimal clustering， plus whatever the extra cost is by having these stupid reassignments and。

How much is that？So I reassigned basically epsilon end points and the cost per point。Was Eps， sorry。

 opt over N。Alpha over epsilon， also known as。One plus alpha optt。O。But that violates stability。

G stabilityability says that if you're within a one plus alpha factor for the numericalic objective。

 you have to be with an epsilon structurally。 And I just showed you that that's not true that that fails。

 okay。So that's prove of two。2 questions about that。Right。

 so this this is the definition which gets violated at the end of the proof right there。

 do we need to worry about whether there's a way to relay the Excel question。

 So there's a subtle point which I'm intentionally skipping over， but is necessary for the proof。

 So recall that we had this digression or this detail which said how do you actually give two partitions into groups。

 how do you define their distance and you match them in the best way and then to maximize the number of agreements and then you look at how many disagreements there are？

So implicit in this proof of two， I'm assuming that when I take the o clustering and then I move some stuff around。

 I'm thinking in my head about the correspondence where we just take the same copies of the clusters and match them with themselves。

And the rest of the group has to argue there's no better way to have the two sets of K clusters correspond。

 that will give me even fewer， even fewer agreements or disagreements。 Ex me。

 So it's true and there'll be details in the notes， but it's a subtle point。 Okay， yeah， excellent。

Good。Okay， so what all right so。去去去。One and two imply。That they're att most。Bi。Bad points。

Where a bad point means。Either you're not close。Or you're not well separated。Okay。

 so a good point satisfies both one and 2。 A bad point fails。 at least one， possibly both。

So the number of bad points， Well， theres the most5 epsilon n over half of these the most epsilent n of those。

So B is just going to be defined as that sum。And there's most this many bad points。Okay。

So there's a lot of parameters floating around。 So maybe you want to go。

 maybe you should go back and plug in some numbers， So I said， you， think of n as a million。

 Epsilon as one over root n or one over 1000。 So then this would be 1000。Think of alpha as 0。1。

 remember says think of C is 1。1。 So alpha is 01。 So this is like 50。 So that gives us as like 50000。

Okay， out of a million points。 So this says5% of the points are bad。95% are good。All right。

So now we can start talking about the algorithm。So the algorithm has two steps。

 plus sort of an optional。Third step， which we'll talk about if there's time。So。

I guess before I mention this step again， keep in mind what， you know。

 really what's we're looking for here are sort of general algorithmic ideas that might be useful。

 Okay， and both step 1 and step  two are， you know。

 I think nice ideas about how you might approach this problem。 So the first step is going to be。

 we're going to define a graph just based on distance thresholdholding and look at the properties of that graph。

So what's the threshold？So set tau， that's going to be the threshold。Well。

 we're going to say this to be something。But the bottom line is we're going to form the graph。

So remember what we started with。 We started with a metric。 Okay。

 so you can sort of think of that as like a complete graph with numbers on the edges。

 namely the distances。 Now， we're just going to be looking at a graph undirected。 Okay。

 so there's no numbers。Simpler object。So form G， so the vertices are just the points in the metric space。

 but not all edges will be there。And edges are just going to denote nearby points。 Okay。

 namely distance at most ta。So I should tell you what Tau is。嗯。So Tau is basically going to be。

Twice what this is。sent。You don't know what often。Yep， that's an excellent comment。

 but I'm going to define it that way anyways for the moment。ち。I'm sure we get this right。

After we're in。2 alpha。Over five epsilon。So to relate this to the properties in one and two。So close。

 notice this is just doubleness。So close basically means the distance between a point in its center and the optimal clustering。

Is it most town over two？Whereas well separated。Means that the distance。

Between the first and the second。Cllosest centers。Well， this is just that。

 but with an extra two fits added， so we just reverse that。

 it' is going to be strictly bigger than five/ halfs tau。Okay。So if we knew how to compute Tu。嗯。

Then there's this very simple definition， okay？So ta would just double our threshold for closeness。

 Or if you're like， it's two fifths， our threshold for being well separated。Okay。

 so now on the justifiable complaints。How would you ever implement this algorithm？Certainly。

 at the very least we don't know ops。You might prefer to have a version of this algorithm where you didn't assume that you knew alpha or Epsilon either。

 you think about it。So the stability property is unshckable。

 even if you knew which alpha and epsilon you were looking for。

So you might just want out them that works well， no matter what alpha and epsilon are。

 at least in reasonable ranges。And so this is the only part in the algorithm where the algorithm actually references any of those three parameters。

 optt or alpha or epsilon。So what it really needs to know is。

The relevant parameter here is really this。Okay。The algorithm wishes it knows。

So there's actually a simple trick that works in lots of different contexts when there's sort of one parameter。

 it would be really useful if you knew， but you don't。Which is you just try a bunch of values for it。

We sort of already talked about this with the number of clusters K。

 So often you talk about K as if it was know， given came down from heaven， you know what I mean。

 but really， you try a bunch of possibilities in practice。 Same thing here。 All right， So basically。

 and you'll work out the details for this for homework 3。 They're not， they're not very hard。

 You just try a bunch of values of tau and in some sense， pick the best one。Okay。

One thing to notice is that we only care about tau in as much as it defines the graph G。Okay。

 and Tau is just this threshold on distances that we're using。

There's only n choose2 different distances in this metric space。 Okay， so really。

 there's just n choose2 relevant values of tau。 And as you go from small to large。

 the graph G will go from empty to complete。Okay， so you're basically just going to keep adding edges to G。

 waiting for something magical to happen。 And we're going to analyze the rest of this algorithm for the correct value of this parameter where something magical will happen。

😊，你看。Was that clear？So you can reduce the case of knowing opt to the case of not knowing opt just by。

Repeated doubling in effect。And that's a good thing to remember。

 That shows over and over and over again。 right， So when you're designing an algorithm。

 if you could say， well， if only a little birderie would tell me this one number。

Then I'm off to the races。 That's actually usually excellent progress。 Okay。

 it's a good thing to remember。O。So that's step one。So again， for the rest of the lecture。

 we're just going to assume that tau literally is this number，Good。Now， what are we hoping？So。

 remember。We have this assumption。 We have these optimal clusters， C star1 through C star K。

 We have no idea what they are， okay。This graph we can compute。

 So now we have our hands on something。 So we're really hoping that there are big clues about those hidden optimal clusters。

 the C star eyes in structures we can detect N G。Okay， so that's what we now need to understand。

 To what extent does。The stability property about the metric space give us detectable signatures of them in G。

So now let's switch back from the algorithm to the analysis of the algorithm。

And try to understand what things look like。After step 1。Then there'll be step two。

After we realized we need a little more work。All right。So claim one。Claim1 is about good points。

 Remember， a point is good if it is both close， meaning within tau over 2。

Of its center in the optimal clustering and well separated。

 meaning at least five/ half cowu between its closest and second closest centers。So here's the claim。

The claim is N G。There are cliques which correspond to the optimal clusters C star1 through C star K。

Okay。So in some sense， these hidden clusters show up。NG in a nice way。

So the claim is all good points。Within a single C star I。

 C star I means the if cluster in the optimalal cluster， which exists， but we don't know it。

For a clique， N G。So take 30 seconds to think about this， about why this is true。

So are we actually using the， do we need to use the full hypothesis that these points are good or only one of the two properties？

Only closeness matters here， actually。 O So why is this true， This is true。

 just by the triline equality。So take two points that are good and in the same cluster C star I because they're good。

 they're close。So each is within tau over two。Of their center， so by the trianglelineequality。

The distance to each other is at most of some of the distances to the center。So DXY is at most help。

So that means they get an edge in G。that was true for an arbitrary pair of points that are good in the same center C star I。

 Okay， so you have a clique。All right， so have you made any progress。

 We have reduced this problem we wanted to solve to finding cliques。😊，Ohoops。Cleek's a hard problem。

 It's the same as independent set。 We're talking about that last lecture。

 It's a really a hard problem。 On the hand， this， I mean， this G。

 this is very far from a worst case instance of clique。Right。

 so we're hoping there's more structure there that makes these cleaiques unusually easy to find。

 I mean， in the best case， we kind of wish this graph would just fall into K different pieces。

 And then the cliques would just sort of be there waiting for us on a silver platter。 Okay。

 It's not quite true。 But claim 2 is going to say。And claim twos where the five comes from。

So claim two is going to say。while the graph G doesn't fall apart。

These different cliques can only be connected through kind of relatively sparse structures。

So the claim is if x， y are good and indifferent。Optimal clusters。So in distinct。C star I， C star J。

Wed love to say there's no path between them at all。

 right because then their clts would be in different connected components。

 and that would be relatively obvious for us。 But we can say that if they're connected by a path。

 the path has to be pretty long。 It has to be at least three hops in G。This is sort of a clever cl。

So X， Y distance， not in the metric space， but just in the sense of shortest pass in the graph。

Is at least。Three hops。So take 30 seconds to think about this。 This one is not as obvious。

 This one is a little little trickier。And if it suits you， feel free to。

Exchange ideas with your neighbor for a little bit。A picture is good， pictures are good for this。

Okay。就。But hearing is way not。我咁快。这。欢 not。Yeah。M。Allright， so here's， here's why that's true。Okay。

So take your points， X and Y。 So don't forget the hypothesis。

 X and Y are in distinct optimal clusters， and both points are good。 Actually， one of them。

 we just need to be close， the other one we just need to be well separated， but whatever。

 They're both good。So start with X。And so Y is in a different cluster。

 Let's C2 denote the center of Y's cluster。So if x is well separated and it is by assumption。

 the difference in distances between x in its center。And X and C2， this other center。

 has to be at least five hals over town，Now， the distance from x to its center is at least 0。

 So the distance between x and C 2 has to be at least that separation gap。 Okay，5 halfs tau。

 X is far from C 2。Why on the other hand？Well， C2 is Y center。And why is good？ So why is close。

 So why is it within just tau over two。Of C2。So now we use the trianglegon quality yet again。So。

 this is because。X well separated。This is because why close。

And so the triality implies that the distance between x and y。

Is at least the distance between x and C2 minus the distance between sorry， C2 and y。

So just add this to both sides to see why it's the trianglelineality。So wanted。ちちち。Yes。

 that's what I wanted， yep good。Bigger than two town。Okay。

So because just by virtue of x being far from C2 and y being close to C2 x and y has to be pretty far apart。

 bigger than two tau， every edge and G represents distance of a most tau。

 so every path of at most two hops by trigonality again represents distance of a most two tau。

 so if their distances strictly more than two tau， any path between them has to have at least three hops。

So a picture of G is now emerging。So what we've got is we've got the。

You've got like the good points of C1， that's a clique。Good points of C2， that's a clique。

Good points of C3， that's another cl。Then you' got these sort of hangers on these bad points， okay。

So。You know， bad points could look like this。And so on。They can even annoyingly， sort of connect。

Difference of these cliques of good points together。Okay。

The only caveat is that this is kind of elongated structures that connect the two cliques。

Every path here has to be at least three hops。So that's what we know G looks like following step one of the algorithm。

All right。Okay， so。What we were hoping was that the cliques would just sort of fall apart and be obvious。

And so there's going be a step 2， which takes a graph like this is input。

 There's another simple filtering step。that's going to sever these long chains without destroying the cleeiques。

 And at that point， Ill just highlight the cliques in a totally obvious way。

So that's the point of step two。All right， so。For simplicity。

I'm going to make an additional assumption。About the target clustering。Okay。

This will make my life easier and we'll be able to derive stronger results under this assumption。

I'm going to assume that every cluster in the target clustering is big。What do I mean by big， I mean。

 it's going to have at least two B plus two points。 B is the number of bad points。

 That's the formula for it。So the numbers we were plugging in and is a million Epsilon 1 over 1000 alpha equal 。

1。 There were 50000 bad points。 So that's going to be about 100000。 Okay， it's going to be about 10%。

 So it's a clustering problem with those numbers where every cluster has at least 10% of the points。

 which you know， is going to be true in some interesting applications。

It means these are most 10 clusters， but again， often you're looking for a small number of clusters。

That said， you know， certainly， one would also want results without this assumption。

 And there are some。 I'm not going present them。 You have to work a little bit harder。

 Not so much on the algorithm。 The algorithm is quite similar， but the analysis is harder。 And also。

 the constant factors are somewhat worse。 Okay， but there are results without this assumption。

 I want you to know that。 Okay，re the， they're in the paper。And I might put them in the notes。

 as well。O。So let me describe step 2 now。Step 2 is just going to be to throw out some edges of G。

 Okay， so we got G just by thresholding a tau。 Now we're going， and this， again， I think。

 is a very nice idea。 We're going to only retain edges where the endpoints have lots of common neighbors。

So we got a very simple， nice idea to throw out some of the edges of a graph。

So the vertex set is the same， the edge set is a subset。So。X， Y is an F， if and only if。

It has to be an E。And， at least。Be neighbors in common。All right， where B is， again。

 are upper bound on the number of bad points。Okay。 I should have said。By virtue of having。

 so under this large clustering assumption， by virtue of having at least two B plus two points in each cluster。

 and therere being in most B points in total， Clearly。

 each cluster has at least B plus two good points。So in every cluster。

 the good points outnumber the bad points， that's sort of the immediate。

Payoff of this large cluster assumption。All right， so is the second step of the algorithm clear？

Do you look at look at each edge， look at his endpoints， count the number common neighbors。

 and a threshold on that statistic at B。Again， really simple。All right， I about some more claims。

So claim3。Claim three is that the cls survive。Okay so G has these cleaiques。

 So remember what the cliques are for each optimal clusters， C star I， we look at the good points。

 and now we know there's at least B plus two good points。We had a cl on them in G。

 I claim none of those edges get deleted in H。The cliques survive。Why， well， again。

 the cluster has at least B plus two points， good points。

 That's what the big cluster assumption gives us。 So they're in a clique of size B plus 2。

So for any two of those vertices， they have B neighbors in common。

 namely the B other vertic good points in that cl。And that's true for every edge of the clickique。

So the cliques don't go away。It's good。Now， why is it？That we severed all those chains。

Is there a question or。I is it2 b plus2 if' saying B plus2 the plus2。This is the definition。

 So this is the assumption。 saying could you have done it with less。No。No。

 although it hasn't shown up yet。Yeah。Okay， it's another sort of rabbit out of the hat。

 but it's clear why I'm using you know， ballpark2 B， probably。So， what's plus 1-1 among friends。

But yeah， no it's not it is actually chosen with care He's asking why you aren't using ballpar B like B plus two would work for this claim。

 right？Yeah no。No， you're worried about them all being bad， right， All those points being bad。

 or there be bad points floating around the world。So。Let's try of keep going the proof。

So don't forget claim 2。 We're going really use claim2 right now。 Okay。

 so claim 2 says if you have good points in different clusters。

All of the paths between them have to be three hops， minimum。Okay。Thats we'm racing right now。

So three hot paths， at least between good points and different clusters。

 I claim all those paths get sundered。When me do this。Common neighbor trick。So why is that true？

So claim four。So no paths。Between good points。In different clusters。And clusters are the optimal。

 the target clustering。Sir吧。So， proof。So think about two good points in different clusters。O。Cster I。

C Stj。O。We want to say that every X， Y path loses an edge。Okay， that's what I to improve。

So every path， the sureest the path could be。Would be three hops。Okay。This is by claim2。

X and Y are good， they're in different clusters。On a three odd path like this。

That vertex has to be bad。And that vertex has to be bad。Okay。Otherwise。

That you'd have a too hot path between。2 good points in different clusters。 more generally。

 if you have a longer path。You're going to have an edge in the middle of that path somewhere that looks like this。

Good。So the claim is this edge。Will not survive。What does it mean it won't survive？

It means that so that's if and only if it's two bad endpoints。Do not have be common neighbors？

So what could the common neighbors be？Well， this bad vertex。Okay， I might have some neighbors。

 which are good points。Those have to be in C Arri。Okay。

This vertex might have some good points that are neighbors， but they have to be in C star J。Okay。

 if this had any in C star J or that had any C star I。

 that would give us a two hub path between good points in different clusters。

 We don't have any such paths。So if the first vertices， good neighbors are only from star I。

 the other them's only from C star J， they have no good points in common。

Their only common neighbors are bad points。There's only be such points。

And these villains are two of them。 actually， right。

 So they have the most B minus two neighbors in common。 that's below where we were thresholdholding。

 poof， edges gone。So that's true for every path in good points，So， summarizing。Only only bad。

Common neighbors， of which they can be at most two。So I can delete it。Okay。Questions about that。

Alright， so step 1 kept the cliques and at least made them only connected by long， stringy bits。

And the second step。Severs all the stringy bits。Do I want this？And now we're home for。Now。

 exactly what we wanted to have happen happens。 Okay， there were these clusters。

 We have no idea what they were。 right， No clue。 But we can certainly。

 you know form this graph based on distance thresholdholding。 We have the metric。 that's easy enough。

 We could certainly take that graph and do operations on it。

 like count like count neighbors and delete more edges。 And then if， oh， wow。

 there's only like K big pieces in this graph now。 Connect the components。

 I guess those are the optimal clusters。 right So we just completely highlighted them through these simple graph processing subrouts。

😊，So summarizing。So， this graph H。It has precisely K。Connected components。Of sufficiently large size。

Okay， with at least B plus two vertices。It might have some small connectedine components。

 Those can only be bad points。 Okay， remember， we have these K cliques on at least B plus two points。

 right， We've got all of those。 We have no path between any two of them。 right， So that gives us。

K cadentic components， each of size at least b plus 2。Right。

We might have kinetic components of only bad points， but there's only B bad points total。

 So we're not going to get fooled。 Those kinetic components have most B points。 So put differently。

 sort the kinetic components by size。 The top K all have size at least B plus 2。

 Each of them contains the good points of one of the optimal clusters。

 Everything below that has size at most B。 Those are entirely bad points。 That's what we get in H。

 what H has to look like。O。So。Now we're responsible for outputting a K clustering。So what do you do。

 well， obviously these K big components should be the K clusters。There's these little tiny。

 bad point clusters that just， you know， merge them in arbitrarily。 We're just gonna。

 we're just going to be wrong All the bad points。So we get all the good points right， the bad points。

 who knows？So we don't get something which is epsilon accurate after step 2， but we do get。

Something which is， let's see。Epsilon1 plus5 over alpha。Accurate。Okay。

So we get something which at least， you know。Is something？So I promise you Epsilent accurate。

 I just want to， I'm going tell you what step 3 is for the analysis because it's so cute。

 It's just very cool。 for the analysis， you can look at the notes。😊，So the goal is to take these。

 So we've now computed a clustering。 So if alpha is like 01， this is like 50 epsilon， okay。

So instead of missing 1000 points， we're missing 50000 points out of a million。 Okay。

 but let me show you a simple trick to get it down from 500050000 back to 1000。So step three。

So in parallel。Here's what all the points do。 Okay so you've computed。After step two。

 we have our tentative clustering， C1 hat through CK hat。Where all but 50，000 points are correct。Now。

 each of the million points。In parallel says， well， let me look at the K clusters that got computed。

 Okay， and I'm just going to reassign myself to the cluster of points that I feel the most kinship with that I'm closest to okay。

Now， that's not totally well defined yet， because what we know what the distance between two points are。

 but what's the distance between one point and a cluster， a set of points。

So here's how the points going to reason about it。 It's going to look at the median distance。

Between itself and all of the points in cluster C had I。

It's going it's going to define that as its distance to that cluster， okay。

It looks at the K clusters， looks at which of the K is closest to。

 and reassigns itself if necessary to that cluster。And you do that in parallel for all X。

 So you don't do it sequentially。 You do this simultaneously with the original sea hat eyes for all X。

So I'm going just say reclassify。By median distances。So it doesn't take long。 It takes five minutes。

 but I don't have five minutes。 So in the notes。You can see how。Classifies。哦。But the。

And most epsilon in。Non well separated points。So what this step three does is it takes the points which you used to be getting wrong because they were not close。

 but were well separated， and it now gets to those right in this median distance。

Is there any questions about that？So you said we had to I guess the part of the value of Ta like from the N to。

Well， that's the most naive wound of doing it。Sure， but how， how do we like argue what that。

 Like for each， for each value， get some output。 Yeah， so the details are sort in the homework。

 But basically， you want to wait until this happens。So this will happen at some point。

You should think through about why it happens early。You might still be happy。

But this is sort of the stopping condition you're looking for， something like this。Okay。

 we got this number also。You know what the numbers in terms of time？B， you mean or this， yeah。Yeah。

 I mean， to be honest， the way I usually think about this model is you know Epsilon。

 you know alpha and you don't know opt。 and you're kind of searching for opt。

 That's maybe the simplest way to。 That's the way I'm gonna to phrase it on the homework。

Other questions？Have a good weekend。 More on clustering next week。

