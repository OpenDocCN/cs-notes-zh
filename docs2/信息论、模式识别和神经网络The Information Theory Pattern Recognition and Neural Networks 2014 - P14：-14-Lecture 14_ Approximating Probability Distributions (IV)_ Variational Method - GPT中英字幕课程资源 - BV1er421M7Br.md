# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P14：-14-Lecture 14_ Approximating Probability Distributions (IV)_ Variational Method - GPT中英字幕课程资源 - BV1er421M7Br

![](img/f1163c99811566e9ac00776fb809beea_0.png)

Welcome to Leture 14。 Today's lecture is about variational methods。😊。

We've been talking about methods for dealing with complicated probability distributions。

 We may have nasty probability distributions because we are doing inference。

 and our posterior distribution is nasty。 We may also have nasty probability distributions for other reasons。

 Maybe we work on physics。And in the lectures， we've discussed Monte Carlo methods。

And now we're going to discuss variational methods。

 which are two possible ways of dealing with nasty but somewhat tractable distributions。

Here's the overview of all the chapters in the textbook that we've been looking at for the lectures so far。

 And I should emphasize that there's some additional reading。 I'd encourage you to do。

 There's a very short chapter on Laplace's method， which is another way of dealing with nasty distributions。

 where you approximate the nasty distribution by Gaussian。

 And I'll just leave that as a piece of reading for you。And from time to time。

 I will refer to icing models。 So it's a good idea to have read the chapter on icing models as well。

 though not essential。So here's the websites for the book and for the course。

And the idea of variational methods works like this。The assumption， just as in Monte Carlo methods。

 is that there is a nasty red distribution called P。And P。

Is something that we can compute within a normalizing constant。

 So it's got the form E to the minus E of X， and we are able to compute E of x。😊。

And in variational methods， our assumption is that E of X is a fairly simple function。

 but not quite simple enough for us to be able to actually answer the questions of interest。

 which are things like expected values of functions under P。

So what's the idea of variational methods？ Well， we introduce a simpler green distribution that we call Q。

And we parameterize that simpler distribution in some way。

So Q is intended to be simple enough that we can evaluate expectations and interesting things under Q。

And we make it adjustable， and then we adjust the parameters of Q so that it is as close as possible by some metric to P。

 So we adjust these parameters Theta to get the best approximation。

 And a very important question is gonna be， how do we define best。

 Once we found that best approximation。😊，We'll call the optimized parameters， Theta star。

Then we can approximate the expected value of a function phi that we are interested in by the expected value under Q。

Right， so that's the， the big picture。You could think of this as getting away from introducing random numbers。

 with Monte Carlo methods。 we said， oh， please difficult。

 but let's use some random numbers and some clever ideas and jump around in X space in some way。

 And you might have thought， well， that's a bit inelegan。 Why do I need to have extra random numbers。

 In addition to the data that I've gathered for my inference problem。

 It doesn't seem logical to need random numbers to answer my inference question。

And so variational methods are an approach that says， yes， you don't actually need random numbers。

 You can do this instead， well。Whether it works well is， is an open question。

 I'm going to describe to you。How we do this。So we need an objective function that measures how close Q is to P and。

There's various ideas for how to measure closeness of distributions to each other。

And two that we have already come across are the Quebec Live blur divergences between P and Q。

 which you can write two different ways round。 So you can have this average under Q of log Q over P or the average under P of log P over Q。

 And these are both measures of distance between P and Q。

That have the property that when P and Q are equal， D comes out to be 0。

 and you can't get any smaller than that。 So these are both minimized if Q can actually perfectly match P。

Now， we must remember that the X we're talking about is a very high dimensional thing。

 So these sums over X that we have here are not necessarily easy to do。 A moment ago。

 we already agreed that P is difficult。 We can't accurately represent averages for example。

 the sum over or X of 5 x times P of X is a difficult thing。

 So why should we think that we can do anything with these， these K Ls。Before I。

Continue with that thought。 Let's just look at an example。 So you understand how these K Ls work。

 So here's a very， very simple， nasty red distribution， which is non uniform。

 It's got a third a third a third， and epsilon probability on four discrete points in in its space and Q is a simpler distribution。

 which is uniform a quarter on all four places。 So I'd like you to quickly work out and discuss with each other。

What's the Kbec liabr divergence each way round。 So if you work out the first one and the second one。

 which of them is biggest and roughly how big there are they。 So please talk to your neighbor now。

Okay， let's have some votes。 So on the board， we've got Q P first and then P Q is second。

 So let's have votes for which one is bigger， I the first one bigger or is it smaller or do you not know votes for I don't know。

 I haven't had enough time。Okay， votes for the first one is bigger than the second。Okay。

 lots of votes for that And votes for， it's smaller。 No votes for that。 Grand。 Okay。

 and that is correct。 So well done。I've written them the other way around for no particular reason。

 here the。Distance measured this way round is about log 4 over 3。

Whereas if you have Q on the outside， Q goes and lums in and puts quarter of its probability mass on a place where P says no way that's got tiny。

 tiny probability， and it gets strongly penalised for doing that。



![](img/f1163c99811566e9ac00776fb809beea_2.png)

So。When it top up。When you to up Q log  Q over P， you get this one over epsilon。

 which is very large and。That。Bad news， if you like， if。

 if this is your measure of closeness and that says Q is a very long way from P。

I'll put quotes on that， cause。Is it bad news， I don't know it it。

It depends on what we're trying to do。But。Is at least big。

So something to be aware of if we use this sort of objective function。

To measure closeness is if P is a complicated thing， Oh， sorry。

A complicated thing that in some places goes to 0。 And if we approximate it by。

A green thing that is nonze in places where P。Is actually 0 or very， very close to 0。

 This will be deemed a bad approximation。You get a very strong penalty。

 So if we optimize this objective function。The sort of thing you might expect to have happen。

In this case， would be that the green thing says， oh， I mustn't put a foot wrong。

I'll make sure that I don't put any mass in places where P is 0。

 So you'll end up with approximations that look like this。 That's the sort of thing that happens。

 If you use some Q。Lolog。over P。On the other hand， if you use some P of log P over Q as your objective function。

Then。It's the other way around that you don't want to make the mistake of。

Failing to put mass in a place where P has got mass。 And so if you use。This objective。

Assuming you could compute it。This would lead to you。

Taking a acid distribution like this and maybe approximating it with something extremely broad to make sure you've captured all the little。

Little blips that he has got。Okay。So it's good to understand the objective functions we're talking about。

Now。The first one， some of P log P over Q involves summing。A moderately nasty thing。

Under a nasty distribution P， let's just rewrite it。With color。So we have a sum overall x of P。Log。

He over。And given that finding the expected value of a function under P is difficult。

 it seems very unlikely that we're gonna be able to find the expected value of this function under P。

Alright， so even if we want to evaluate this one， it's probably not on。

We won't be able to evaluate it。So let's give up on that straight away and look at the other one。

So if we look at D K，L， Q， P。This involves a sum of Q log， Q。

 all of which is is nice and is under our control。 And then we have the one little bit of a nastiness。

 the red bit。😊，Is here。And everything else is green or white。嗯。We could write this as。A sum over x。

Q of x。 Let's color it green this time。Times the energy。

Using the definition that P of x is E to the minus E of x。On Z。

 where Z is an interesting number that we don't know。So I've pulled out the E from here。

What else do we have， We'll have a Z， please。So there's log base E of。Red Z。

And then what's left over is the entropy of Q， which I'll call。Hq of x。We can give that a green。Tins。

So is this hopeless as well， Is it impossible to evaluate this， Well。

 this is the average of a function under Q。 And maybe that is on。 Maybe we can do it。 It's E。

 but it hasn't got a P in it。 It's only got an E。Alright， so maybe that's okay。This。

 we would love to know。But from the point of view of adjusting cu to try and make this thing as small as possible。

 this log' Z is just a constant。 It doesn't have any Q dependence。 So we don't know this。

 but it doesn't matter。In fact， not only does it not matter， but maybe by minimizing this thing。

 we might be able to find out what it is。And finally， this thing is entirely green。

 It's the entropy of a distribution queue that we can control。 And we can say， yeah。

 Q is allowed to have the following form only。 and maybe we can constrain Q so that we can evaluate this。

 So I'll put a green tick for that。😊，So this objective function out of the two I've listed。

It's promising。 Maybe we can evaluate it。And if we rearrange what's on the board。

And focus on the two terms that haveve got ticks。So this one here。And this one here。

We can define an objective function that's made up of those two。

 And that's what I've put on the computer screen。 It's called the variation of free energy。

 It depends on the adjustable parameters。Of Q。 And， by definition， is the average。

Of the interesting energy function and the Q。Minus。Some of you love you。The entropy。Of Q。

 And the theta dependence in here is that。This distribution to。Depends on Theta。

 Theta is our description of how we adjust it。Right， and this thing has a name。

 It's called the variational free energy。And because of where this came from。

And because of the fact that this thing here。Is。Positive。It is a true statement that。

F total of theta。Is lower bounded by。Minus log， Z。So if we succeed in minimizing the variation of free energy。

 we will have also minimized the K L between Q And P and the objective function that pops out of that minimization。

 If we can evaluate the variation of free energy at the optimum is a bound on log Z。

 So we'll for free， be getting something interesting out。😊，Okay。

So the variational methods I'll talk to you about today are entirely based on this objective function。

 There are other variational methods as well。 but that's all I'm going to do today。

So let's look at some examples now so you can see how this works。

Can we evaluate this variation of free energy， Well， for some problems， for some red energies， E。

 the answer is， yes， you can， as long as you can straight in Q to have an appropriately simple form。

😊，So let's go through two examples。The first example I'll do is the good old Gaussian distribution。

Inference of thereof。So hopefully， you remember this distribution。And。

discussionscussions of the inference problem。

![](img/f1163c99811566e9ac00776fb809beea_4.png)

So the assumption is that there's a normal distribution with parameters mu sigma squared。

 It's given rise to some data X。And。We now want to infer mu and sigma。So， the red distribution。

Is the inference of。New and the variance。And we've looked at that before。

And if this is the mu axis and if this is the sigma。Squared axis。

 what the nasty red distribution looks like。Is something a bit like that？

A distribution that has the property that any slice through it in this direction。

Is a normal distribution。Sorry， I didn't rule those very well。

And all of those are centered on the same place。 In spite of what it looks like。

 they're all centered on X bar。Theample mean。So。Let's read it。Okay。

 so all three slices through are normal distributions。And slices in this direction are。

Gamma distributions。Maximum of the posterior。Under the assumptions that we had earlier in the course is at a place called。

Sigma is。Set to Sigma N， the Sigma N button on your calculator。However。

 if we marginalized over all of these gamma distributions， the projection all of all of those onto。

This axis。Is a gamma distribution that has a peak。At a larger value of sigma。Clled。Sigma and -1。Okay。

 so this is a very simple distribution。And we're going to pretend were。

Challed enough by it that we want a variational method。

So what we will now do is introduce a variational approximation。Where the inference。

 which is a posterior distribution on mu and sigma squared， given the data。

Is going to be approximated by a simpler distribution Q。And how much do we want to constrain it。

 What form shall we constrain it to have， Well， I'm going to constrain it very little indeed。

 I'm just going to constrain it to be。A separable distribution， a function of mu。And。A function。

I'll stigma square。So that's the constraint I'll apply。And then we can ask the question。 Now。

 if we write down F twiddle。And minimize it。 What happens。So here's what happens。嗯嗯。Mmmmmmmm。Okay。

 we have temporarily lost display。

![](img/f1163c99811566e9ac00776fb809beea_6.png)

Okay。So there's the red distribution。 That's an accurate contour plot of it。

 And if you now kick off with any distribution Q of this separable form。And then you say。

 let's alternately update the mu dependent function and then the sigma dependent function and alternately update them and see what happens。

 The answer is straight away， when you optimize the mu dependent one， the mu dependent thing says。

 I want to be a Gaussian please。😊，And。So you can do that。

 And then if you update the segment dependent 1， it'll say， I want to be a gamma distribution。

 please。And then he can ask the mu dependent one， what do you want to do now。 And it says， of course。

 I want to be a Gaussian， but he will change his parameters。

 And then you ask the sigma dependent one， what you want to do so we can do this sort of。

alterating update approach to the optimization of F。 What I'm doing is。Optimizing F twiddle。

 the variation of free energy with respect to the distribution Q U， and then with respect to Q sigma。

 And then we can alternate and iterate。 And when you run that to convergence。

You end up with an optimized Q distribution。 That is a normal。And an optimized sigma distribution。

 That is a gamma， and。The optimized distribution over mu is a normal distribution centerd on X bar。

 Of course， what， what else could it possibly be。But its width isn't the same as this slice through here。

 It's a bit fatter。And the optimized distribution for Sigma。Doesn't have its maximum at Sigma N。

 It's actually got it at Sigma n -1。So this is a case where we constrain the distribution to be wrong in a fairly simple way。

 Ma it separable is a fairly standard thing to do。And then you end up with the optimized distribution。

 having the sort of properties that we kind of want。 It's not the case。

 If you marginalize out mu that you get the correct posterior。

 The true posterior over mu is actually a student distribution。

 It's a mixture of all of those Gaussians。 So we haven't magically sort of got around the。

 the fundamental problem。 The true posterior。 when you marginalize it is a slightly nasty mixture of Gaussians。

Nevertheless， it's got the right sort of properties。 So if， if you ask， what's。

 what's its mean and what's its's characteristic with， it's got the right characteristic width。Okay。

 so that was example number one。 Any questions about。About that。



![](img/f1163c99811566e9ac00776fb809beea_8.png)

Example number 2 is the spin system， which we've discussed on and off in the past。

So a spin system has couplings。J between the spins， which are binary variables。And。

Spin systems can display all sorts of exciting properties。So， the nasty red distribution。Is。

B of x is E to the minus。Beer timess and energy。Noz。

Notice the addition because we're doing physics of a temperature parameter or a coldness parameter beta。

 which multiplies the energy upstairs。And it makes the Z beta dependent。

 The way the free energy responds to that is we shove in。A beater hair。

And then the free energy depends both on theater。And bitter。Okay。

 and then the free energy is always abound on Z of beta。

 So now you can pick any beta and do the variation free energy minimization for that particular problem。

Okay， and the spin system is。Energy of x is minus- a half some。Overall， pairs of spins。X， M， X， N。

Waied by。JMN。And then there may be local fields applying to each of the spins。Like this。

 And the exodes live in。-1 plus1。To a power N。 So the X lives on the corners of a hyper cube。

And the reason this is a nasty problem is because of this term here。

 the fact that there are couplings between pairs of spins is what makes it a nasty red thing。

If only it were the case that we didn't have these coupling terms。

 then it would be a simple distribution， because this isn't nasty。

 This just says the energy is a sum of terms， one for each spin。

 And that means when you exponate that， that the spins are independent from each other if we only had this term。

 So wouldn't it be nice if the distribution look like that。 That motates saying， well。

 let's go ahead and declare our approximating distribution to be simple。

 let's declare it to have the form。Q of x is。A normalized version of E to the sum over N A N。X， and。

So now in this approximating distribution， each of the spins has just got its own personal applied field that favors it being up or down。

 depending on the sign of A M。 So this is a separatepar distribution and very easy to work with。

Just to emphasize that it's separable， I can write this as a product from one to end of an individual。

Distribution for the n spin alone。Just like a moment ago， we said。

 let's pretend the distribution over Mu in Sigma squared gets approximated by a separable product of distributions。

 So the parameters in this case are these A Ns。 This is。

The thing I was generally calling Theta is the set of all of these A Ns。嗯。And。

Just to write this one other way。This is E to the A N。Ex then。

So because it's a separable distribution， it's easy to evaluate its entropy。And it's not。

Trivially obvious， but we can easily evaluate the expected value of the energy。

 even though the energy's got couplings in it。Let's go to this screen now to talk through this。

 The screen shows the approximating distribution in green on the second equation。问。

And the third equation writes our Bta F twiddle， and I've coloured it all green and red so we can keep track of what's what。

And you see， we've got a simple entropy。 that's just the entropy of a separable distribution。

 So that right hand green term is easy。 The only nastiness comes in the from the red terms where we look at the average value of the couplings。

Under the distribution Q。So we now go down to the next equation In parentheses。

 we've got the expected value of the energy。And。To get the coupling。Terms contribution。

 We just need to know the sum overall M and N of JM N times the average value of X bar M times the average value of x bar N。

 because Q is separable。That。Simple step is true。So now all you need to know to evaluate the energy is。

 well， what's the mean value of each of the spins。Under queue。Alright。

 And then you can tot up all of your n squared contributions for each of the。

 the the pairs of possible couplings。So we can evaluate the variation of free energy。

 And when you look at this and you say， how do I adjust it with respect to Theta， Remember。

 Theta here is the set of biases， A for the individual spins。And what effect do those have。

 Will they change what the probability of a spin being up is。

 which changes the mean value of that spin。 So Q， N here is my name for the probability of one of the spins being up。

 The n spin being up。 and X bar N is the mean value of the spin。

 They are trivially related to each other。 draw a little rough。嗯。So。Is。

Q for being in the state plus one。Here's Q for being in the state， -1。And。X。

B n is just the sum of Q plus 1。Plus， -1 times  Q -1。So X bar is linearly related to the Q。

For example， I can write this as Q。Minus。One my cute。Which is。记住。マイナ1。All right。Okay。

So the adjustable parameters are A or Q or X bar equivalently。 Theyre。

 they're just interchangeable ways of describing what we're going to adjust。

If you minimize with respect to that set of n adjustable things。

 the n degrees of freedom that cures got。You find that the optimum satisfies these two equations。

 which you can again solve by iterating them。 The first equation says that you can work out a by looking at all the mean states of your neighbors。

 So if you are the empty spin， you go and look at。All your neighbors states。 and you say， well， how。

 how vish are you， You to them all up。 And that tells you what your A should be。

And then your a is related to your X bar through X bar is tanch of a。That's。

Just yet another relationship I could have written down of this type here。



![](img/f1163c99811566e9ac00776fb809beea_10.png)

Comes from having an E to the plus 1 and an E to the -1。 That's where。Taniness comes from。Okay。

So I didn't want to labor through the derivation of this on， on the board。 It's all in the book。

 If you want to look at it more carefully。What's the overall message。

We can take a reasonably nasty distribution that has lots of complicated properties。

 We can approximate it by a separable distribution。

 Then we can minimize the variation of free energy， and the update equations look like this。

 Add up your local， averaged field from your neighbors and set yourself into a state that spits out your。

 your average response to that applied field。😊，Okay， and you get all your spins to do that。And。

If you iterate those equations， you get to a minimum of the variation of free energy。

 Let's do this now for an example of a two spin system。So on the board， I'll just talk through。

How this two spin system works。Okay。So here is the incredibly nasty distribution。

The spin system has two spins， X1 and X 2， and each of them is in the state plus -1。

And the energy is minus x1 times x 2。All right。That's it。

 So the connection to what we've just been doing is it's the spin system with just two spins。

X1 and X2。And they are coupled with a coupling of strength J。 That is equal to one。Right。

 spin systems don't get much simpler than this。So we variational free energy。

Repeating the derivation we've just been through for the general case of asilience spins is beta times X1 bar。

Ps x2 bar minus。The entropy of Q1。Minus the entropy。Of Q2。 And these are ens base。一。Okay。

That's the equation。 What does this actually look like， Well。

 let's just draw its state space with x1 being -1 or1 and x 2 being  -1 or1。The real distribution。

 assuming J is positive。Favors them both being in the same state as each other。

 So the real distribution in red。Has。Maybe a bit more mass。Plus 1 plus 1 and -1。

-1 and a bit less on the off diagonals。 So that's the real distribution。

 In't it nasty and complicated。And where。Coping with this terrible complexity of this nasty thing。

 which actually， in truth， just requires two numbers to describe it。

 namely how much matters here and how much it is there。 Were nevertheless。

 approximating this distribution by a green thing。 And the green thing says， oh。

 I want a separable approximation， please。 So I'm gonna have a Q1 that puts a mass on。😊。

This and this and maybe a Q2 that puts some mass on here and here。

 And there's two adjustable parameters， which is what's the bias of Q1 and what's the bias of Q2。

And if you multiply together a Q distribution that， for example， could put more weight on plus one。

For each of them， if you multiply those two with by each other。

 then the Q distribution you'll end up with will put most of its mass on this corner。

 A very small amount on this corner and a middling amount on this one。On this one。You with me。

And we're free to wander around in。Q1。Q2 space。Where Q1 is， say， the value of this thing。

 How much mass is getting on plus one here。 And Q2 is。

How much mass does the second spin put onto it being in the plus one， plus one state。

 And as we wander around in Q1 and Q2， we can plot。The variation free energy。And I will now。



![](img/f1163c99811566e9ac00776fb809beea_12.png)

Do that for you。嗯。And I'm doing this as we very beta。 So this sequence of plots。

Starting with beta very small， which means high temperature。And going to large beer。

 which means very cold temperatures。 So I've got to a very cold temperature。 Beta is now 2。

And you can see what the free energy looks like。 And the answer is that it's got。2 minima。

 These two axes are Q1， Q2。 and I've shown exactly the same function twice over。

 but different views And with a contour pot in one case。

 So with the contours projected onto the base on the right hand side。

 So hopefully you can see what's going on。😊，So what's happening。A。High beta， which means。

High coldness or low temperature。The free energy。Has got minima。Here。And here。

So that's when beta is too。At the other extreme。Let's go back again。 Light down， please。Reip。Okay。

 I've gone halfway here， and I'll go a bit further，Okay， here's the high temperature end of things。

 So I've taken beta down to low 。4。And now， you see that。The minimum of the variation for energy。

It's here。Alright， and as we go between those two extremes。Beta going from0 。4 up to 2。

 There's a place where a transition happens in what F looks like。ready，3，21 pop there。

Where that figure of 8 contour appears。Alright， one more time，Okay， do you want to see it again。

So we start with a single minimum， and then at beta equals one pop， the figure of 8 pairs。

 and we have two mini。Alright， coming back down， there's a figure of 8。

 and it vanishes there at B equals 1。Okay。So if I summarize where the mini are by showing the value of both Q1 and Q2 on this axis。

 and I'll put a star on it there，ca I'm gonna。Show where the optima are。At very high temperature。

The optimum。Is。At。Q1 and Q2， both equal to a half。So this is half yeah。

And then the transition happens when beta is1。And it goes， pop。And then we have something like this。

 We have a choice。 You can go either way to the top right or the bottom left minimum。Okay。

So what do we think of that。Some people。Get， I think， distracted by the concept of phase transitions。

And whenever they see a bifurcation， a transition from they say。 Oh， goodness be a face transition。

 Isn't that wonderful。😊，And I think that's a mistaken way of responding to the world。The truth is。

 we're trying to approximate this red distribution as we change the temperature。

Between very high temperatures。At high temperatures， the distribution looks like this。

 and you can hardly see。That these two guys here are actually a little bit fatter than these two here。

And at very low temperatures。You end up with a world that looks like this。With all the mass。

On the diagonal and very little hair。And as you go through different values of beta from this world of high temperature to this world of low temperature。

The true red system doesn't have a phase transition。 It just。

 its distribution just changes from being this to this to this。 and it's completely continuous。

And the fact that this approximation that we've introduced has a transition in it， has a bifurcation。

Shouldn't， I think， be a cause for excitement to say， oh。

 isn't that wonderful that it's got a phase transition。 It's not a phase transition。

 It's just a transition。 It's a bifurcation， and it happens to happen at a temperature of one。

 which might look a bit like this。😊，And it's a transition。From。

Insisting on approximating distributions that look a bit like this by saying， well。

 I'm just gonna approximate it by a uniform distribution。And then once you get above that point。

 then it goes pop。 and it says， I'm going to approximate a distribution that looks rather like this。

By。That distribution that puts almost all the mass on here and a little bit on here。

 little bit on here and almost nothing at all。On that。

So I feel fairly sanguine about whether this is a useful approximation or not。

 It's mathematically nice， and it's good to be familiar with it because this sort of thing crops up a lot。

😊，嗯。But I'd like to emphasize that real system in red doesn't have a phase transition。

 and this transition that the green system has at this point here。Yes， it's a bifurcation。

But it's not a phase transition。 A phase transition is a much more interesting phenomenon where the variance of the energy diverges and all sorts of exciting phenomena occur。

😊，Now， we could go through another example， which is。

The spin system with couplings between lots of neighbors。And if the couplings are all identical。

If they're all equal to， say， plus one between a spin and its neighbors。

 And if all spins have the same number of neighbors， then actually。

 we've just done the entire calculation here。 It comes out exactly the same。

 The only change would be if you've got two neighbors， then you put a factor of two in here。

 If you've got four neighbors， you put a factor of four in here。

 And this whole calculation we've just gone through。 And this graph that we've just plotted。

 tell you what will happen for a system with N spins as well。

I'm mentioning that just to emphasize that the real， in the real world， Well。

 I'll call it the real world in the world of systems with lots and lots of spins， with N spins。

Where N is very large， you can get phase transitions。And the icing model， for example。

 is a system where you couple to your four neighbors and the icing model， as we saw last time。

 does have a phase transition。This is what happens when you use the variational method to approximate it。

 I just emphasized that what has happened was not a phase transition。

 and it didn't happen because the underlying system had a phase transition。

 So we should be very skeptical about people who say， oh， look at my wonderful variational method。

 which I've applied to the icing model and look it has a phase transition because it hasn't。Okay。

Why am I saying all this？ Well， I think there's a。This method， this variational method。

It's quite widely used。 and it's got a name。 And this is a question for physicists in the audience Main。

 So the question is， have you seen these equations before here。

 I've just written down again the equations that I derived for the general spin system。

And what we've gone through here is a special case where all the J's are equal to a single number。

Have you seen these equations before and what was it called， yes。

It's called meanfield theory or the meanfield approximation。

 So that's what it says on the next slide。And often， when it's derived。

 people are not clear on the derivation。 It's just， well， let's do this。 Let's do this。 Likes。

 let's now take the mean of this。 And if you're lucky， it may be well explained。 But for certainly。

 the first time I encountered meanfield theory。

![](img/f1163c99811566e9ac00776fb809beea_14.png)

It just seemed like a， a sequence of。Arbitrary approximations。It also goes by various other names。

 It's sometimes called cur vice theory， at least in the Cambridge thermodynamics course。

And occasionally， you may hear people calling about talking about the Feynman trick as well。

Or the fineman bogoli above。Approxiation。So these are all names for the same thing。

 And what I've shown you here is。A derivation of mean field theory。

By writing down a variation of free energy and then minimizing it。

 And I like this way of deriving mean field theory because it's very clear what the objective function is。

 It's clear what you're doing。 and it does motivate other generalizations。

 So just to finish this little sermon。😊，Why do I like。The variational free energy view。

Of mean field theory。I love it。Because one， it's got a clear objective function from which you can then derive。

The equations。So that's nice， because maybe you need to memorize less。

 You just memorize the objective function， and everything can be derived。😊，It is generalizable。

 You could， in principle， choose。More complex， approximating distributions， Q。

And then you could generalize your。Varational methods。As long as you can evaluate it and optimize。

After it all。And the third reason for loving this view here is it shows that when you do meanfield theory。

 you are actually getting a bound on Zed。So it shows that these meanfield methods。Give。Abound。On Zed。

 which is an interesting thing to be able to compute。Okay， that's。Meanfield theory。

 And that's variational methods。And that is the end of the lecture。

My plan is that the next lecture will be an introduction to neural networks。And then。

We'll probably spend two lectures on neural networks。 And maybe in the second lecture。

 also wrap up with a little discussion of state of the art error correcting codes。

 Are there any questions on this lecture。Okay， thanks very much。

