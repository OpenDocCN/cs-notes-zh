# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p02 -02-(Lecture 2_ Instance-Optimal Geometric Algorithms).zh_en -BV1yqVzzqEQ5_p2-

So this whole lecture is going to be about instance optimality。

 a concept we introduced the beginning at the end of last lecture。

 so I'm going to be covering one result， really just the easiest result from a really nice paper。

Which came out about five years ago。So it was in the Fox conference。

 F OCS that's sort of one of the two major annual conferences in theoretical computer science and there's a bunch of results in here。

 I'm going to show you the easiest one but that's already going to suffice to sort of prove the main point which is that sort of amazingly for fundamental problems。

 at least a few of them， instance optimal algorithms actually exist which is kind of amazing and in this case it's even an algorithm which is from the mid80s because it's an algorithm everybody already new and loved and it turned out it satisfies this very strong instance optimality guarantee okay。

So what's the problem that we're going to study， The problem is called the 2D maxima problem。

So this is a classic problem in computational geometry。So we're given as input points in the plane。

Okay， so N walls denote the number of。Points that were given as part of the input。

It's not really important， but just for simplicity， assume that all of the coordinates are distinct。

 so we're never going to worry about ties。So that's the input， what's the output？

So a quick definition。So one input point y dominates。Another one， X。If both of Y's coordinates。

 the x coordinate and the y coordinate， I apologize for the overloading of notation are strictly bigger than that of x。

 Okay so both coordinates are strictly bigger。 It's northeast of x。Okay。

And the computational problem is given the input points output all of the undominated points。

 Those are called the maxa。Those of you who have taken a little economics may also think of this as the Pareto optimal points。

 if you like。 Another way to just think about it geometrically is it's sort of the northeastern frontier of the point set。

K， you can imagine maybe these。Youive have a big point set and only has， say three maxima。

These three points。Theyre regions of domination， if you will。Is everything strictly to the southwest？

So if all the other points are the points set。Why in these regions of domination？

Then these are the three maxima okay。So that's the goal。 You're given all any of these points。

 identify the three or however many there are maximum。So questions about that problem。

 statement clear。So I'm going to show you a cool algorithm for this problem and then kind of an amazingly strong guarantee about that algorithm's running time。

Okay， so。We're just going to be focusing on the number of comparisons that the algorithm makes。

So remember， we have from last time we have this sort of generic notation about just the performance measure of an algorithm。

 So you want to think about it， like when you study comparison based sorting。

 we're just going to be counting the number of comparisons that the algorithm makes。 Okay。

 so the only way it can access the coordinates of points is through comparison。

 So we're not allowed to do anything like， say a radix sort or something like that。

So a number of comparisons。That algorithm A requires to correctly solve the problem specified by the input Z。

 Okay， so we want to make this as small as possible。 when algorithms for which this is low。

And in fact， we want an algorithm which is really sort of uncontroversially as good as possible。

So the goal is an instances optimal algorithm。And I'm going to remind you what this means。

 I'm going to remind you of the version that includes the two relaxations that we concluded last class with。

So there should be。 so we allow sort of a constant factor gap。

Between our protagonist and some competitor algorithm。So there exists a constant C。So that。

 but here's the really strong part。For every single input Z。And for all algorithms。

 or at least for all natural algorithms， recall that was one of the relaxations we discussed on Monday。

So for all natural algorithms B。The algorithm A's cost， meaning its number of comparisons。

 is no more than that of B， or at least no more up to a constant factor。Okay。

So this is what we're looking for。嗯。So the constant here。

 C is independent of both the algorithm B and the input Z。

 You want to think is C is just something like 2 or 4。And again。

 I want to emphasize and the homework will reinforce this point for lots of problems。

 There is no instance， optimal algorithm。 Okay It's just too strong and nothing satisfies it。 Okay。

 so it's kind of amazing it even exists。 let alone that it's a nice algorithm that we can actually analyze in a lecture。

 okay。All right， so。Proving instance optimality for an algorithm involves really two different tasks。

 So first of all， for your protagonist algorithm， A。

 you need to prove an upper bound for every single input。 Okay an input by input upper bound。

 Secondly， for every alternative algorithm， B， you have to prove a lower bound。

 saying it's not too much better than this algorithm A。So a prerequisite is， you know。

 for the upper bound of your protagonist algorithm， you need a really tight analysis。

 You need to say something a positive result， a guarantee。

 which is much stronger than merely saying for some worst input Z。 The running time is the most bh。

 So we really need a much more fine grained analysis of the performance of the algorithm。

 And that's going to be really the meats of this lecture。

 I won't have time to say too much about the lower bound side。 but I'll make a couple comments。

So a prerequisite to instance optimality is just a very tight upper bound on the performance of a single algorithm。

 and then the other part is a matching lower bound。All right， so any questions， Otherwise。

 I'm ready to tell you about the algorithm。It's clear what problem we're talking about and what we want。

So let me tell you about the algorithm that actually will achieve this guarantee。

It's a divide and conquer algorithm， very elegant。By Kirkpatrick in Siidel of 1985。Okay。

 so we'll just call this the KS algorithm。So we're given a point set。 So again。

 it's divide and conquer recursive algorithm。 Okay So there's going to be a base case。

 and there's going to be recursive calls。And our job is to identify every single maximum point。

 every single undominated point。So for the base case， if there's a most one input point。Then clearly。

 that point is undominated， okay。U。So we're going to add the single point to the output。Okay。

 so one point， data sets are easy， of course。

![](img/0a6490d0606d11311bf873fc8a9bc296_1.png)

Now， so how does the recursion work， How does the divide work？So。

Let me illustrate this with a picture as we go along。So we're going to split the point set into two。

And the way we're gonna to do it is natural enough。 We're going to look at a median point。Okay。

 so that should be familiar from quick sort of。 What have you。 Of course。

 median is only in a single dimension。 And here we have two dimensions。

 So we're just going to pick one of the two dimensions。 Let's say the X coordinate。

 And we're going to split the data set。AroAround the point with a median x coordinate。

So now we have a left。Part of the data and the right part of the data set。

And you should know from your studying undergraduate algorithms what is required to compute the median。

Of end things。What running time is sufficient for that。 Linear time。 good。

's so for the deterministic version， that's this famous algorithm with five authors。

 four of whom return the award winners， right you know that So Blum， Floyd， Prat。

 who's the exception， Re and Ta。Yeah， so。So yeah， so you can do that in layer number comparisons。

 so that's good。Now。Oops， I said no ties。So now what we're going to do is for on the right hand side。

We're going to look at the point that has the biggest y coordinate。So， a Q。Have the max Y coordinate。

On the right hand side。And we're going to add Q to the output。So I guess implicitly in there， then。

 there's a claim， which is that。Q， whatever it is， whatever the point set is， it has to be a maximum。

Okay。So it better not be dominated by anything else， otherwise this algorithm is now incorrect。Okay。

 so why is it a maximum。 Well， if it's not a maximum it's dominated by something。

 who is going to dominate it。 Well， no one on the left side because their x coordinate is smaller。

 But then this guy's the highest y coordinate on the right side。

 So no one on the right side can dominate it either， okay。So no worries。

 that's a rightfully declared maximum。And suddenly you say， well， okay， if Q is a maximum。

Let's take a further linear amount of time， scan the point set and delete both Q。

 but also anything that it dominates。So we're just going throw those out。

 We don't have to worry about them。So we know they're not going to be maximuma they're dominated in particular by Q。

So delete Q。And everything it dominates。And now recurss。 both on the left hand side。

And on the right hand side。So that's the algorithm。Any questions just about what it does？

I certainly owe you a couple things。 I owe you a proof that it's correct。

 and I owe you a detailed discussion about his running time。 I'll tell you about both of those。

 Any questions before that。All rightep。You know， just simply keep a sorted list of the points in X and Y direction。

 And then we will have to view the medium in the next。Okay， so this is a good question。

 So I I was a little。 I haven't really told you what we're shooting for as far as running time。 Okay。

 And so that makes it right。 So so what you suggest is let's sort and not just keep doing repeated medians。

 So we're definitely going be stuck with n log N time。 right if we do any sorting subberines。

 And we actually want to do better than n log N time。At least on some inputs。

That's not something I give you a heads up on。 Okay， I'm going to tell you that now。 So ultimately。

 I mean， the exact running time guarantee is a little technical to state。 by the time we get there。

 you'll understand it， but I'm not going just pull out of a hat beginning a lecture。

 but it's going to be better than in login。And so that's why just sorting something and losing analog up front is not something we want to do。

 It's a good question。Other questions？有。So why dot you get to expectation the？

Why don't you think that the haers why copy it。Yeah， okay， you could do that。

 and then what do you do？And then。And then you。H the away， I the point 80 days and re。

And recurs one sore。就出来关 you do。Right， so I mean， if you pick， if you just pick Q first。

 there's no guarantee you'll get a balance split of the point set。

So it's not even clear you'll get an analog log N type running time without the meeting computation。

And that segues actually nicely into， I guess I should tell you the correctness first， actually。

Maybe you think correctness is obvious， but I don't think it's totally obvious。

 it's worth a couple of points of discussion。So。First of all。

 one thing that's obvious is all deletions。Are justified。But so at the end of the day。

 this algorithm is going to output some subset of the input point set。

 and it's declaring that these are all maxa， right。Now， anything which a dozen output。

 which got deleted along the way， No worries， right， We explicitly had in our hand a point Q。

 which dominate any point that we deleted。 So the only concern is that we output a point that we claim is a maximum when it's not。

 So that's what we have to prove。Well。It may seem like we've already proved this， we said， look。

This Q point was a maxima， right， It can't be dominated by anything on the left and can't be dominated by anything on the right because it had the highest wide coordinate。

 But remember， this is a recursive call So we've already recursed a bunch of times in a given recursive call。

 we have a subset of the point set。 Okay， we started with a million points。 Now we have 10000。

 And what I argued is among these 10000 remaining points。 Q has to be maximal。

 It's not dominated by any of the 10000 left。 But what about all the other million points。

 in the original point set。 Okay， I need to argue that none of those dominate Q either。

 So that's why I need to argue something。All right， so what we've already argued is Q maximal。U。

With respect to Q at time of removal。Okay。So that's what we argued along the way。

 But what about with respect to the original point set。 Well。

 the claim is that this algorithm has the property that it will never。

 through deletions or through recursion， turn a point which is not maximal into one that is。Okay。

 so that never happens and then it willll be done， all right？So why is that？So first。

 let's look at the right side。 claim is a maxima。Of the right hand side。Are also maxa。Of QL。

And this is sort of the relatively trivial statement。 Right So again， what does it mean that。

 you know， So if you're a maximum on the right hand side， what does that mean。

 It means you're not dominated by anybody on the right hand side。

 So The only worry is that you're dominated by someone on the left hand side。

 But everyone on the left hand side is smaller X coordinates。 So they can't dominate you。 Okay。

 so that's just because we split it into the two。 Okay。

 the right hand side somehow automatically dominates the left and the X coordinate。

But what about the opposite， That's where we should be worried。

 And here's where we use the fact that we do pruning，So the claim is after pruning。

Max the maximum of the remaining points on the left side。Are also a maxa of the original point set。

Okay。So why is that true， Well， So you know， if you're a maximum on the left hand side。

 you're not dominated by anybody on the left。 So the only worry is that you're dominated by somebody on the right。

But if you have survived to this point。Then it means you weren't deleted by Q。

 Q had the highest coordinate on the right hand side。 So by virtue of your survival。

 your Y coordinate is even higher than that of Q。 Okay， and Q is the highest on the right hand side。

 Okay， so after pruning， everybody in the left has a Y coordinate higher than everybody on the right。

 So theyre all maxa， okay。So you only delete non maxima。

 You never turn a non maximal point into a maximal point。

 And whatever you output is maximal at that time to done。

 Take it output something if and only if it's maximal。Questions about correctness。

 is there any issue of two points of the same coordinate？Like I I assumed no ties for convenience。

 Yeah， otherwise， you sort of do some usual stuff。 You have to define what you mean dominate and then you have to tweak the algorithm。

 et cetera。 Okay， but just think no ties。O。Other questions。So the runtime discussion will be longer。

Although we we'll be able to very quickly understand that it's at least a pretty good algorithm。

 It'll take as longer to understand， is it really an instance optimal algorithm。So， firstt of all。

 I hope it's straightforward for you all to see that the running time certainly isn't any worse than O N log N。

 It's certainly not any slower than say a merge sort， okay。

It's exactly the same recurrence as merge sort。 It is two recursive calls by virtue of the median computation。

 Each recursive call is on a data set of at most half the size as the original one。

 maybe much less because of the pruning step。 It's certainly no more than half the size and the work done outside of the recursive calls is linear。

 All you do is the median computation， which is linear number comparisons plus the pruning step。

 which is another linear number， Sam recurrence， Sam result and login。So on the homework。

 I ask you to show。That if you don't try to do a refined running time analysis。

 you just try to think about the worst case。Then there are indeed inputs。

 there are indeed point sets for which this algorithm will use omega of n log n comparisons So in that sense。

 this n log n bound is tight in the worst case。So what we want， but that's not good enough。

 for an instance， optimal bound。Because there are certainly other point sets that are much。

 much easier。Like， consider a point set where there's only one。Maximum point。

So there's a ton of points。But actually， there's a single point that has both the highest x coordinate and the highest y coordinate。

So think about what this algorithm will do if you feed at this point set。

Well in the very first recursive call， it'll identify the upper right corner as the Q。

 so that's on the right hand side of the data set that has the max Y coordinate， that's its Q。

 it prunes， boom， the whole data set wiped out， exterminated， so it stops。So that's linear time。Okay。

 so this algorithm does not run an n log n time on every single input。

 There are inputs where it runs in n log N。 There are inputs where it runs an n。

 it can vary in between the two， okay。Now， keep in mind what we're trying to prove with an instance optimality result。

 we're trying to prove that this algorithm， input by input is as fast。

 as frugal with comparisons as any other algorithm。

Okay so to prove it's as good as any other algorithm input by input at the very least。

 we need to have a tight up to constant factors， upper bound on how well it does input by input。

 okay that's a prerequisite for having a matching lower bound for an arbitrary algorithm is at least we have to understand how well it's doing and we don't yet input by input okay。

So what we understand is that there are easy point sets and that there are hard point sets。

 and we want to have a parameterized upper bound in the number of comparisons。

 which is large if it's a hard point set and small if it's an easy point set。Okay。So。

 let me show you kind of the。A sort of relatively old idea for improving。

 we're going need to do two steps。Let me tell you the first step first， which is pretty simple。So。

Again， I'll leave this as an exercise that shows up on homework one。

You can improve the running time upper bound of n log n to N log H。You should be asking me what is H？

So by the way， that's an n， that's an H。は。So we' H equals the number of maximo。

IE the size of the output， So n is the size of the input。 H is the size of the output。

 So these are sometimes called output sensitive algorithms on that particular point set， H is one。

 So the statement is something we already knew that the algorithm runs in linear time on that particular point set。

 but more generally whenever there's a constant size output。

 then the Kirk Patrick' side algorithm runs in linear time。Okay。So what's the intuition？

So this is not a complete proof， but this is sort of a big hint of how you might do the exercise。

So consider all the recursive calls of recursion level J。Okay。

 so I want you to have in mind the usual recursion tree at the root is the outermost call。

 it's two children or it's two recursive calls and then fourth the next level8 at the next level and so on。

 so think about level J of this recursion tree with at most two of the J recursive calls。Notice。

 recall the Kirkpat Saideel algorithm， it finds this point Q and it adds it to the output before it does the recursion。

 so this is important。 Every single recursive call of Kirkpat Saidideel identifies a point to add to the output okay。

So if at recursion level J， you have two to the J recursive calls。

 those are adding two to the J maxima to the output。And if there's only H maxima to be output。

 then this recursion level can't grow higher than log H because there aren't more than H maxima to contribute。

 okay？And the recursion， the work per recursion level is linear， just like it is in say merge sort。

So identify two to the J maxima。So the max recursion level at most luggage。Okay。

 and linear work per level。 The reason that isn't quite a proof is this is sort of assuming that the recursion tree is balanced。

 So really， actually， after the pruning， some of these recursive calls will just be empty。

So it's actually kind of a potentially jagged recursion tree， but really this is the worst case。

 and that's what I want you to think about as part of the exercise。All right。

 so that's the statement。 So this notice so what have we done。

 We took a coar worst case bound of n log N parameterized only by the input size。

And now we have a refined upper bound， which is parameterized by both the input and the output size and N H。

 Sometimes these are the same。Sometimes this is much better depending on the input， depending on H。

Now， it turns out this， So， of course， this is tight in the worst case。

 because this is tight in the worst case。 Also on the homework。

 you're going to learn that this is not that sometimes we can do even better。 Okay。

 so there are instances where H is big and you yet Kirkpatrick sideel still runs in linear time。

 So this analog log H still does not give us a fine grainined enough upper bound to argue that we're instance by instance。

 input by input doing as well as possible。 So that's the next and major and final step of the analysis。

So it's in the spirit of this finer grain parameterorization。

 but we're even going to get more detailed than we have up to this point。So any questions？

 I it clear what we're doing and why？Okay。Right right。And also， I want you to remember the algorithm。

 this entire lecture is exactly the same。 Okay， it's always the Kirk Patrick Saidell algorithm。

 All it's doing is shop into a two with a median prune and Mercur。

 That's the algorithm the whole time。 We're working harder as analysts to prove better and better things about this fixed algorithm。

 but the algorithm is always the same and very elegant， just a few lines of Python。😊，Okay。So。

The final bound， the still more refined bound。对。All right， so this actually， is like I said。

 this actually takes a little bit of work even the state。

 but it'll be intuitive once we think about it a little bit。So consider an input point set。可。

And so again， remember， this is just a thought experiment。 This is not the algorithm。

 We're just trying to analyze the algorithm。So the point set has some maxima。

And any point set has what's called a staircase。Which is what you think it would be， right。

 So the max are of this northeastern frontier。 So you just draw zigzags。Between between the maximum。

So because these are maxima， all of the points set lies below this staircase。

 If you poked up to the other side of the staircase， you yourself would be an undominated point。

All right， so that's the staircase， this blue zigzag。So now to state this refinement of N log H。

Suppose we partition， okay， So there are n points here in S N points。

 Suppose we partition them into K groups， okay。So we have K groups， partition of S。So that either。

So that for let's see， for every eye for each group。Either S is just a single ten。

 it's a single point that's allowed， or if this is a group of points。

Then the group of points should be contained in a box。That's underneath the staircase。Okay。

So this is a possible SI。Okay， so if I can enclose a group of points with a box so that the box under the staircase。

 that's allowed。嗯。So trivially， one of these always exists because if nothing else。

 I could just put each point into its own S I。 Okay， I could just have all singletons， right。

 But in general， depending on the point set， there may be lots of ways to partition it in this way。

 okay。All right， so why， why this definition， What's the point。 So remember what we're trying to do。

 right， We have this intuitive understanding that there's harder point sets and easier point sets。

 And here's the point。 The point is， if you can sneak a whole bunch of distinct points into a single box like this。

 that's suggestive that it's kind of an easier point set。Because basically。

 if we think about the pruning that happens in Kipatrick Sidel。

 if we just identify like that one maximum point there and one fell swoop。

 we' kill off this whole box s subbi。Okay， so what you should think about is if we can partition the point set so that we have few groups and that the groups are really big。

 that's like an easier point set。 at the very least， you know。

 at the very least is one algorithm we're talking about。

 We might expect this algorithm to run faster。 And that's all we're focusing on now。

 Let's just get a really tight analysis ofpat Sael。 Why does it sometimes it be faster than in log n。

 because it makes progress during pruning， when does pruning save you a lot。

 Well' when you have boxes like this。 So that's where this definition comes from。

 and we'll actually prove a theorem that says that。

 basically the fewer of these boxes and the bigger these boxes are the faster the run time of Kipatrick sideel。

 Okay El， don't you always need H boxes Why don't you always need H boxes to enclose all the points。

Put that maximum maximum can't be in else sure， right， so I'll show you the exact formula。

 The exact formula of what our running time is as a function of the boxes is a little complicated。

 So it turns out even though so the running time is going to be better than just linear in the boxes。

 So it's also going to depend on the box size， basically。It's a good question。Yeah。

 but certainly right one canonical thing to think about is just you know having each of the maximum on its own partition and then doing something else with the stuff under the staircase。

 that's a good picture to a mental model to have Yeah to be correct correct So that's another reason why you might just want to think of picking off the max sort of one at a time。

So the， the claim， actually， is if you have a box like this。

 you can find a point on the staircase that dominates it。

 The way to see that is start at the northeast corner。Go north。Then go east。

And because you only went north and east from the northeast corner。

 that one point will kill off that whole box。We're not actually going to use that fact。

 that's sort of just a way to think about it。 So by virtue of being under the staircase。

 you're sort of easy to eliminate。You find mean， you could find a subset of points that's not a box under the staircase where you need multiple points to kill it off。

With a box， there's sort of a single witness of its non maximality。new。No， not at all。No。

 of course not。I mean， because you could always take the all Singletons partition， for example。

 right？So in some sense， we're going want the best partition。

 So let me go ahead and state the theorem。O。So here's what's actually true。

So whats here so here's the， the upshot is that the best， in a sense， I'll make precise here。

 the best partition of this type actually fully characterizes the running time of the Kirkpat Sael algorithm。

 Okay， in the following sense。It's a theorem and this is。So the algorithms from '85。

 but this particular analysis is from the Shaee etal paper， from Fox09。For every point set。

The atpatrick Sael algorithm。Uses。Bgo。So for a fixed partition of this form。

This is the function we're going to look at， so we sum over the boxes in the partition。

So if it was just this， it would be kind of silly， right。

 because we know that sum of the cardinities sum to N， okay。So but in addition。Whoops， that's wrong。

We look at。N over the size of the points。In the group。

And this is actually an upper bound on the running time of Kirkpat side dell for every single partition of this form。

 So in particular， the best upper bound， the minimum this of this quantity over all partitions is an upper bound on the running time of the algorithm。

 so men。So by legal， I just mean a partition of this form。So these are called legal partitions。Okay。

So that's the claim。 That's the theorem。 So just to get a quick feel for this。

 we argue that whatever the point it is。Right so I also remember。

 we'll also remember this is a complicated expression。 Remember。

 we never have to evaluate this in the algorithm。 Okay， the algorithm is just these like three lines。

 Okay， so this is just to characterize the running time。 Now， you know。

 we know that the algorithm is n log n， even in the worst case。 And that's easy to read off this。

 So what partition would give you an n log N here。か。Singleton points， right。

 So then you have n terms。 This is one， and this is log n。 So you get n times log n，On the homework。

 I'm going to ask you to I ask you to prove that this is always the most N log H。

 Okay so it's a canononic way to choose S that gives you the N log H bound。

 And I to ask you to prove that sometimes this is better than N log H。Oh that's true。All right。

 so any questions about that？Other than how you prove it， which I'll tell you about next。Okay。

All right。So， proof。Right， so exercise always at most N log H。 So it is。 It is an improvement。

 It's a strict improvement。 Okay， there's infinite families of point sets where N log H is super linear。

 but this is actually linear time。All right， so here's I're going to do。So this says， basically。

 this is equivalent to saying， you show me your favorite legal partition and I'll show you a corresponding upper bound on the running time of the Kirk Patrick saidll algorithmth。

 I'm going to show up bound for every possible legal partition。 Therefore， it holds for the minimum。

 So fix your favorite one。Okay。So S1 through SK is a legal partition each。

Each subset is either a single point or it all fits in a box that's strictly underneath the staircase。

And basically， the proof is sort of a super clever way of accounting for all of the comparisons that get done over all of the entire recursion tree。

 okay。So what I want to do is I want to think about a fixed level of the recursion tree。

 so there's it most two to the J recursive calls at this level of the recursion tree。

And so one thing that we sort already discussed is that the total work。

 the total number of comparisons done at this level is linear in the number of points that remain at this level。

 Okay， So so just we have it most two to the J recursive calls， maybe fewer。

 maybe someone that being emptyied because of the pruning。Okay。

Because we always split the data set in two， right。

 so no point appears in more than one recursive call。 So at a given level。

 that's sort of a partition of the remaining points， okay。And in each subroutine， we do linear work。

 so summ over all of the problems at level J， it's linear work in the total number of points that still exist at this level。

Okay。So number of comparisons。Linear in number of remaining points。Okay。Now。

 if our prunings aren't doing anything， then know we're gonna to have basically a linear number of points at every recursion level。

 And we're going to get the n log n。 So what we're trying to say is look look。

 the reason we're going be faster on some inputs is because the pruning is making really aggressive progress。

 So that's we have to quantify in the proof of this theorem。 And we somehow have to link。

 the speed at which we prune points against the existence of these legal partitions。

 that's sort of know the intuitions up there， the defitions are up there。

 But what do they have to do with each other。 Okay so that's the point of this proof。

 It's really saying， this partition measures the rapidity that which you prune these points away。

 And if you remember the original motivation of the box， it shouldn't suit too shocking。

 a box under at least in principle， any box under the staircase can be prune with a single identification of a maximum point。

Because we're sort of hoping those connect。Good， so。So remember， we have this legal partition。

Pick your favorite box。 Okay， so I'm just going to basically eventually prove this by summing over the boxes。

 So pick your favorite S sub I。Allright， so let's think about。 So。

 you know S I originally had whatever。 Maybe it had 10000 points at the beginning of the algorithm。

 Okay， some subset of the points。And， you know， as the recursive algorithm proceeds and we go recursion level to recursion level。

 prunings are happening all over the place。 And， you know。

 maybe some of the points from S I start getting pruned away。

 we're sort of hoping that they all get pruned away in one fell swoop， But that might not happen。

 because maybe the algorithm identifies some other maxa first。 So for a while。

 there's maybe 10000 points。 know， then maybe there's you know，9000 and 6000， etc cea。 Okay。

 so we're going to watch sort of how fast S I goes from 10000 to eventually0。And we want to look at。

 you know how many points from S I are still surviving at a given recursion level J。

 Can we want an upper bound。 That's a function of J。 we want to say that as the algorithm proceeds。

 less and less of these points still remain。 Okay， so I'm gonna give you right。

 So the first claim is just clearly。嗯。Right， so we want to say how many points are left？

And I'm going to give you two different upper bounds and how many points are left at level J。

 First one， totally trivial， but is actually， we really need it。So obviously。The worst case。

 all of the points are left at a given recursion level。And at early on recursion levels。

 that's all we're going to be able to say， right， So certainly like at the top of the tree。

 all the points really do remain。 Okay， and if there aren't that many points in this box and we haven't done much recursion。

 we haven't that much pruning for all we know they're still there。But once J gets big。

 as we're deep in the recursion tree， after lots of pruning has happened。

 we can start saying nontrivial things about how much of S subba is left。Okay。

And that's the key question。Also， in addition to this trivial upper bound of just the cardinality。

For all J， so for all recursion levels。The claim is SI contributes。At most。

 the original number of points n over。Two to the j。Okay。So this I have to prove to you， Okay。

 this is not obvious。 Okay， this is you know， one of the more interesting parts to this whole analysis。

 But I just want to point out sort of the high level what we're doing。 Okay。

 so let me just keep in mind the whole big picture。

 So we're trying to analyze the total amount of recursion amount of comparisons done by this algorithm。

 And I'm going argue box by box。 So you gave me a partition。

 I'm looking at a single box S sub I that has like 10000 points， All。

And I want to argue that we didn't do too many comparisons just on these points。Okay。

And now we're looking at two different upper bounds。 Right。 So the point is， like。

 we're going to argue recursion level by recursion level。

 And we have two upper bounds on how much of S sub I remains。Think of S as having 10000 points。

 Think of the original points that is being like a million。 So in the early recursion levels。

 this upper bound is certainly tighter， certainly smaller than this one。 Okay。

 this is like a million， Then it's half a million， and it's a quarter million and so on。

 Where this is 10000。 at some point， once J gets sufficiently large。

 This upper bound is going to start being superior to that one。

And we really need both of those upper bounds to get the tight analysis。So， in fact。

 let me prove to you。So the proof of the key claim is going to take an argument。

 but if you just take this key claim on faith， we're pretty much done。好这。So why？

So suppose this is true。 Suppose the key print is true。

 So we have these two different upper bounds on the surviving points from S sub I。

So over all the recursion levels。The contribution of S sub I。To the number of comparisons。Is it most？

All right， well， for a while， we just use this upper bound。At some points， this upper bound kicks in。

Okay， so basically， there's going to be some J where the cardinality of S sub I is equal to n over 2 to the J。

At that point， we're indifferent between the two upper bounds。 At the next recursion level。

 this stays the same that gets cut in half。 So this upper bound is going to be like cardioal vestify over 2。

And then this is going to keep improving by a factor two for each subsequent level。

So we have Carinal SSI a bunch of times。Plus cardal of S sub I over 2 plus cardinal of S sub I over 4 and so on all the way down to one。

 Once J is log n， this is just one。Okay。So the 64000 question then is how many of these things are there。

 right， So this is a telescoping sum， these last terms s subi over  two plus over 4 plus of8。

 So that's just basically the same as yet one more term of the form Car of S subi。So really。

 this right hand side is just the cardinality best subai or 10。

000 times the number of terms of this form。So how big does J have to be before these two upper bounds are equal。

 well this starts at n， we're cutting by 2， we wait till we get to the Caride of S sub I。

 also known as log base 2 of n over Car of S sub I。

So that's how many times you use the trivialvia upper bound。

 and then the key claim upper bound just takes care of the rest。

So the total contribution just of the box S sub I is the coordinate of S sub I times this log term。

 You'll recognize that from the sum。 The total amount of work is just the work done on all the points。

 So we just sum over all the boxes， and that gives us the upper bound and the legal partition was arbitrary。

 So it holds for everyone。 So it holds for the minimum。So questions on why。

 if we prove the key claim， then we're actually done with the whole ho。

 We actually have the full theorem。've reduced， I claim I've reduced the theorem to the key claim。

 Any questions about that reduction。Okay。So。Onward。Proof of Ke cln。So fix J， right。

 So this upper bound is parameterd by J。 It says whatever your box， whatever your S。

 I don't care what the original size was。 just whatever's left at level J is at most the original points of size n over2 to the J。

So Vix Jay。We'm going to break this proof into two steps。So first of all。So fast forward。

To recursion level J。And when we got to talk about who's left， who are the survivors of S subbi。

 So the first claim is that all of S subbi's remaining points。Are sandwiched。An x coordinate。

Let me draw you a picture， actually， can you redraw this picture a little bit。

So here's what I want you to have in mind。So there's all the maxima of the original point set。

And we've fast forwarded to some midpoint of the algorithm。

 so we've identified some but not all of the maxima at this stage。

 right so maybe we've identified that and we've identified that and we haven't found these other five maxa yet。

We're focusing on some S subI so some box。对。So maybe this is our box。Under the staircase okay。

So the claim is that all of SI's remaining points are wedged， sandwiched and ex coordinate。

Between two adjacents。Maximma， so far。Okay。By maxa so far， again。

 we're in the midpoint of the algorithm。 by maximum so far。

 I just mean the subset of points of the algorithms identified so far as maxima， sum but all of them。

 by adjacent， I just mean ones that are consecutive and x coordinate。

So that's the first claim so that all of the survivors from SI are wedged horizontally in between two maximum we've already identified。

And the second thing， and if we prove1 and 2， we're certainly done。

Is that if you tell me that at recursion level J， there's a bunch of points wedge next coordinate between two successive maxa。

 There can only be N over two to the J of them。Independent of whether they came from a box or not。

 I'm just going to argue that， you know， if I just zoom in between two consecutive maximum you found so far。

 there can't be that many points。 And most Nitive J。So does everyone see that just trivially。

 if I prove one and I prove two， then we prove the key clt。

 and therefore we're done with the theorem。O。So if somethings confusing， that just means， you know。

 something's illegible。 Okay， so it's trivial that one in2 implies the key claim。

 So if you don't see it， tell me。Or if you can't， or if it's illegible， tell me， as always。

 I guess I forgot the blanket disclaimer in lecture number one。

 So I'm sort of infamous for my handwriting。 Feel free to clarify as often。 I'll never get angry。

 I promise。 if you ask for clarifications， so。I'm under no delusions about the legibility。All right。

 so approve one and two。Good， so neither， neither ones， they're both they're both bite sized。

 Don't worry。Yeah， okay， so we reduced the key claim to proving one， app two。

I'll leave you the picture。All right， so yeah， these are both bite sized。Proof of one。All right。呃。

Take your box。 Take the right hand side boundary。And look at the two maxims so far that bracket it。

 Okay， and you can take one or both to be plus minus infinity if there aren't any to the left or and to the right。

But so in this picture， this guy's going to be- remember， we look at the right hand side。

So this is going to be our P and Q。So at PQ。The maxos so far。On either side。

Of right hand side of box。O。So the claim is that if you look at the points that still remain from SI that haven't been pruned yet。

They all have x coordinate strictly between that of P and that of Q。

So one of these statements is totally trivial。Right Q， by definition。

 we picked to be to the right of the box。 So obviously， everything in this box。

 whether it's an original one or a remaining point is to the left of Q。

So why is everything that remains in the box to the right of P。

So here's where we use that the box is under the staircase。 Okay。

 so no point of S sub I that's to the left of P。Can also be above P。

Because that would drag the box above the staircase。Okay。

 so anything in the box that's to the left with P has to be below P cannot be above P。

 If There's above P。 We violate the staircase condition。 That's where we use it。Oh， well。

 if everything to the left of P is also below P。 Those things got slaughtered when we detected P。

Okay， remember when we do P， we delete everything that it dominates。

 so everything to the left to P would just be delete it。

So that's why the remaining points of S sub I have to be wedged between P and Q。All。

 so that's the proof of one。Prot 2。Is also simple。 This is really just because of our repeated median computations。

 frankly。So。Our level J recursive calls。Partition， the partition。 what's left of S。

To the stuff that hasn't been pruned away。Into at most， two to the J。Non empty buckets。

Of size at most and over2 to the J。RightI mean， so for the simplicity。

 think for a moment as if there was never any pruning ever。Okay， then what are we doing。

 We're just doing like median by x coordinate， recur， recursive medians by x coordinate and so on。

 So there we're getting like exactly two to the J buckets。 each of size。

 essentially exactly n over2 to the J。So the pruning can just mean fewer recursive calls and fewer size per recursive call。

 That's all， okay。So whatever happens， we have a most two just focus on the non empty recursive calls。

Each has size of most n two of the J points。So we can kind of visualize。The point set。

 So these yellow lines are meant to be the X coordinates of the medians that we've been finding recursively。

And。These all have these populations。Therere a most n over two of the J。And now， remember。

 what we observed， every time you have a non empty recursive call。

 it's definitely going find a median。 right。 Remember we computed this queue。 We said。

 look at the right hand side。 Look at the max Y coordinate。 That's a median。 that goes in the output。

 So that's a maximum That's a maximum。 Ex me。 That goes in the output， okay。😊。

So we have these at most two of the J recursive calls， each of size at most two of the J。

 And each one is going to say， hey， here's the median。 I'm going to contribute。

To the final point set。Okay。So after the level J recursive call is complete。

 all of these blue circles are maxa so far。O。So any group of points wedged between two successive maxima。

 they can only be members of two adjacent buckets in X coordinate。

 and each of these buckets has at most n over two to the J points。

So once these blue guys have been added to the output。

 I can squeeze it most twice times N over two to the J points in between them because each of these groups only had n over2 to the J points。

So it's really basically the same as just saying a bunch of repeated medians break things down into N over two to the J。

 plus an extra factor two， because you might be on the left side of the bucket or the right side of the bucket。

So that's the proof of two。So just because of the recur of medians。

 there's no way there's that many points wedged in between two successive maxa。That proves the claim。

 which says that for every box， we have a upper bound as a function of the recursion level of how many are left。

 And again， remember， we had that mildly nasty sum combining the two upper bounds。

 which said each box contributes at most。Its size。Times log of n over the cardinality of S sub I。

Summing this over the boxes gives us the claimed theorem。All right。Questions。我れ。Is the left of all。

Found X so。 Yeah， so then define P， the x coordinate of P to just be minus infinity。

Same thing about Q。YeahSo if you need to take either， so I didn't really， know I glossed over this。

 but the whole proof works， if you define the x coordinates to be minus or plus infinity as needed。

Other questions？Alright， so needless to say， this is a much more detailed and finegrained understanding of the performance of an algorithm than we're sort of used to aspiring toward or certainly used to achieving。

 Okay， So this is much stronger than just saying some algorithm， you know。

 has a tight worst case running bound of en log N。 We can now really kind of say input by input。

 We have a really good understanding of how fast this particular algorithm will run。 Okay。

 so this is a theme that Ill develop further in the next couple of weeks。

 just this point of parameterizing analysis。 you know。

 what are good parameter is you should use and so forth。😊，For instance， optimality。

 this parameterization is actually just kind of one step of the journey。 It's really just kind of。

 you know， a prerequisite for what we really want， which is an optimality state。

So don't forget the distinction between， on the one hand， computational problems。

 And then on the other hand， specific algorithms。 So for a given problem， namely， given an input。

 accomplish some goal， there's many different algorithms you can use to solve it。 Okay。

 we want the best one in some sense of best。What I just did is I specified a specific algorithm。

 Kirk Patrick Saidll， It was pretty。 It was nice。And we got a very detailed understanding of this one algorithm。

 but who is to say that there aren't better algorithms out there？Okay。And sort of amazingly。

 there's a strong sense in which there aren't。 And again。

 that's something very unusual about this problem。 If there's time。

 I'll conclude with some comments about know what it is about this problem that seems to enable this strong optimality result。

So now I want to talk a little bit about a lower bound。Okay， and here， I won't really have time。

 to prove anything， but I do want to have a。Honest discussion about it。

So what we already accomplished is already quite ambitious。 Okay。

 this very kind of tight parameterization of the running time of a single algorithm。

 We want to be really， really ambitious。😊，We might want to say there is no algorithm that can do better on any input than the Krkpatrick saidll algorithm。

Okay， so matching lower bound。For every input Z。Every correct algorithm。That would be really amazing。

Okay， so rarely in life， can you sort of so unequivocally give somebody advice about what algorithm to use to solve a problem。

 than if you have something like this。And so again， as I sort of alluded to last time。

 this is actually so strong。 It's almost always false。 The way I've stated this。

So let me explain why there is no such lower bound， the way I've written this to be proven。

So here's the problem。So fix and input Z。Okay， so notice what we're what we're striving to do。

 We're striving to do something kind of amazing， which says， no matter what the input is。

 this is the best algorithm。 That's what we're trying to say。 a very unusual statement。😊。

No matter what the input is。Okay， well， let's I fix in and put Z。Okay。The problem is， you know。

 what about algorithms that kind of， you know， are designed， tailored to solve Z。

 that in effect of memorize the solution to Z in advance。 Let me show you what I mean。

 It's very simple to describe。Here's an algorithm。Step 1。It checks if the input is indeed Z。O。

If it is。Even a broken clock is right twice a day， at least back in the analog days。

It outputs the correct answer。So first of all， notice this can be done in linear time。

 I should have said， so you have this point set hardwired into the algorithm。

Okay you just read the input one pass， and you can check if it's the one that you're hardwired for。

If it is。Then you just output the maxima， which you've memorized。 It'ss hard coded in the algorithm。

That's also requires the most linear time to output the solution。Now， I did say， you know， I said。

 you know， I only want to compete with correct algorithms。Allright， so if it's not going to be Z。

 but it's not Z， then this is definitely not correct。

But we can just default to your favorite correct algorithm。Let's say just add insult。

 the injury we'll use Kirkpat's said don。な。Yeah。Right。So this algorithm。Is correct on every input。

And on one particular input Z， it does run in linear time。And as we discussed， as I alluded to。

 there are inputs for which Kirkpat Sidell does not run in linear time。

 It can take n log n on summit inputs， okay。So there are inputs on which this sort of memorization based algorithm beats K Patrick Sael by a log factor。

 a super constant factor。 So in that sense， this lower bound cannot exist。

So but as also told you the solution。嗯。Which is rather than worry about kind of crazy algorithms that you'd never use。

 like based on memorization， let's only try to say that we do as well as any algorithm you might conceivably use。

Now you have to define that， which is not always so easy that this paper includes a very elegant way to sort of essentially define natural algorithms。

 which I want to tell you about。Okay。So in what sense is Kirkpat Saidel a natural algorithm for this problem and this memorization based algorithm。

 an unnatural algorithm。 I mean， I encourage you to think about that off the line。

 It's actually a little tricky to try to， you know。

 get the guts to write down a mathematical definition that sort of separates them in a nice way。

Here's what we're going to do all right， so we're going to observe。That if you look at the analysis。

 if you look at our running time upper bound of Kipat Saidell。

It's totally irrelevant what order the point set S is presented to us in。

 so the entire analysis is about an unordered set of points S。If you think about it， you know。

 if you really encode that as an input of endpoints。

 you have to choose one of the n factorial permutations of which order you specify into the algorithm。

 Our analysis， of course， doesn't care which one， Who cares。ItDoesn't matter。

 Same look around either way。What about this？Memorization based algorithm。

So it has some input in mind， and again， input includes a specification of which is point number one。

 which is point number two， which is point number three， et cetera。And if you think about it。

 we actually use the ordering to argue that step one is linear time。We were sort of， okay。

 we have this hardwired input in our brain， we do a linear pass of the input。

 we just check bit by bit that they're exactly the same。

What if we gave the memorization based algorithm， sort of the input it has hardwired in sprain。

 but scrambled in the wrong order。How to know？They can't check bit by bit。 right。

 It's going to fail that test。 I guess it could sort。The input。

 and then check if it matches what it's hardwired for。 But then sorting takes en log in。

So all of a sudden this isn't a problem that this runs it's not running in linear time anymore。Okay。

So that's the idea here。 Okay， we're going to ask that algorithms you know， sort of have to not。

 in some sense， the analysis should not depend on the ordering of the point set only on the unored set of points。

 Okay， that's the intuition。Andy， could memorization What do you mean， memor then check it Yeah。

 So you're passing out of the comparison based model。 Yeah， so I'll have some comments on this。

 But I mean， if you go beyond the comparison based model。

 we kind of don't have any lower bounds on any algorithms at all so。

So unless you prove a linear time up or bound， it's to be in sense optimal。Yeah。So yeah。

 so really the comparison model is important just you know。

 because instance optimality has as part of it， a nontri lower bound。Okay， so fix， observe。

The chaosS analysis。Independent of ordering。O。All right， so。Here's another theorem。

In thisshani Barbe Chan paperper。I'm going to sort of do this termem injustice in two ways。

 first of all， I'm going to state it impre， although I will explain what the precise statement is。

 second of all， I'm not going to prove it， although I maybe mention maybe a sentence about it but it's a very cool result。

Basically， what it says is that every。Natural algorithm in the sense of an order。

 oblivious algorithm。Needs。At least。That entropy type expression of the best legal partition。

Comparisons。For every input。So they really do prove that。

 This is exactly the upper bound we had in theorem that I did prove for you。

 So they really do prove exactly this。 Okay， with the modification natural in front of algorithm。

 where natural means， in some sense， not tailored to the ordering of the points。

 So it really is up to a constant factor。 The constants hidden in the O and omega notation as good on every input as every order oblivious algorithm。

😊，Okay very cool。Allright， so first of all， this isn't a formal statement because I haven't defined order oblivious。

And indeed， again， it's really not so clear。How to define that， Okay， So they。

 they allied that problem in a very nice way。 They actually prove a stronger statement than this。

 Here's what they prove。 They say， actually。Consider any algorithm at all， possiblyibly unnatural。

 possibly this algorithm。Okay。Here's what I'm going to do。 I'm going to take a point set S unordered。

 Okay， so this is defined just for an unordered point set。

Now I'm going to run your algorithm for a worst case ordering of the point set。Okay。

 I'm going to look at the largest runtime your algorithm ever incurs over any of the n factorial orderings。

 Okay， and that's we're going to call your runtime on this point set。 Okay， actually。

 the lower bound even works for a random ordering。 But think of it as like an adversarial ordering。

So you take an arbitrary algorithm A can be crazy。 You examine its worst case running time on a point set over orderings。

 and the claim is that worst case over orderings running time has to be at least this unaudered point set by unordered point set。

So they never actually define this。 They don't really restrict the algorithm。

 They just analyze things a little bit differently。So that's what they do。呃。

So that's the formal statement。As far as the prove。The proof is pretty nice， I mean。

 if I was willing to spend about 45 minutes of lecture on the lower bound。

 I could prove it to you because I don't want you to be too frightened of it if you're curious。

 I encourage you to look at the paper。That said， I'm not going to cover it。There's two approaches。

There's accounting argument and there's an adversary argument。

Both are interesting and both have reasonably some kind of intuition。

The counting argument works as follows。 It says， well， look， you know。

 your algorithm has to be correct。 O， no matter what。

So anything that you claim is not a maximum point。 You must have intuitively proved to yourself that is not a maximum。

 And the way you do that is you identify some other point that dominates it。 Okay。

 so somehow implicit in your correctness should be。

 if you like a witness in the sense of nondeterministic qua time or NP。

Implicit in your correctness is some certificate of correctness in the flavor of， you know。

 for each point that you deleted something that it dominates it。 And know。

 if you think back to the intuition of these boxes， you know。

 these boxes are things that basically a single point connect act as the witness for all of them。

 you should say， oh， maybe there's some connection between how many bits you need to encode these proofs and these legal partitions。

 And there is。 And they prove that。 And so in fact， you know， more or less。

 they show this is kind of a bit length needed to encode proofs of correctness。

 So that's the first idea。 The second idea is adversarial。

And so here this is sort of a separate way to prove the same thing， but it's also very nice。You say。

 basically， well， so remember， sort we get to devise a bad ordering of the points for this algorithm。

 Okay， so we fix a point set。 We agree on a point set。 You give me your possibly crazy algorithm。

 Now I simulate your algorithm。 And I wait till you make a comparison And whenever you make a comparison。

 only at that point， do I sort of decide something about what the ordering of the points is going to be。

 And I'm going to adversarally unveil the input to you to sort of adaptively hide the maxima from your algorithm。

 Okay so that can also be made precise to prove this lower bound on any algorithm okay。

So those are the ways， you know it's not like I said， it would take me a while。

 I think it would take me 45 minutes to prove it to make that precise， but it can be done and again。

 if you're interested， know I think many of you are totally capable of understanding those proofs。

And I guess， the final comments just sort of takeaways about instance optimality。

So you'll see a few more examples on the homework where you actually can get instance optimal algorithms。

 the two big challenges。 So first of all， one， sometimes they don't exist and the homework will also show you examples。

 Second， as we were discussing with Andy， sometimes it's just going to be impossible to prove instance optimality。

 even if you probably have it， especially if it's a running time application。

 you may have learned in your complexity classes， we basically are unable to prove lower bounds。

 forgetget about separating P versus N。 we're not even able to prove the kind of like know problems in N can't be solved in near linear time。

 that kind of stuff。 So we're kind of stuck with problems that are very close to linear time like these around the N log N range。

 And even here， we have to use comparisonbased models。

One final comment is is we only did the easiest results from this paper。

 They also have results about maximum three dimensions。 They also have results about convex holes。

 which is a even more fundamental problem。 And again。

 they get instant optity results for nice divide concrete algorithms both in 2D and 3D。 Next week。

 more about parameterizations。 See you then。