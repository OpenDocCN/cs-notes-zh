# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P13：-13-Lecture 13_ Approximating Probability Distributions (III)_ Monte Carlo Metho - GPT中英字幕课程资源 - BV1er421M7Br

![](img/4933f91728b622bab4e4337dd6cb95cf_0.png)

Let's recap where we're up to in the course and what the relevant reading in the textbook is。

We've done a load of information theory， data compression and OCchannel coding we're now into the inferenceprints and data modeling part of the course。

The relevant chapters are shown here， Chapters 20 and52 on clustering and stuff Monte Carlo methods。

 Chapters 59，30 is32。Varial methods coming up in the next lecture， Chapter 33。

 I'd like to highlight some additional reading， which covers material we won't do in lectures。

 but it's a good thing to do as part of the course。

 I encourage you to read a very short chapter called Fs method， Chapter 27。

 And in order to understand this lecture。 And the next one， fully。

 you may want to read about icing models in Chapter 31。 If you're not already familiar with them。

There's also a whole bunch of recommended exercises on the website and some of them are on the screen now you may enjoy doing those。

 I certainly think if you want to fully understand them material。

 then doing the exercises is a key part of this course。 The course website is there。

 The books's website is there and。

![](img/4933f91728b622bab4e4337dd6cb95cf_2.png)

We're in the middle of talking about Monte Carlo methods。In the last lecture， we introduced some。

Basic standard Monte Carlo methods。And the rules of the game are that we are interested in。

A red distribution called P。 It's red because it's a bit nasty。



![](img/4933f91728b622bab4e4337dd6cb95cf_4.png)

It's not。Utterly nasty， we can compute it， so we can write it as E to the minus。E of x。On Zed。

 and we have got a computer program that can。Evaluate this thing for any。Value of X。

 X being a sort of high dimensional thing whose properties we're interested in under this distribution。

 So the rules of the game are we can evaluate。咦。😊，But not Z。 we don't know Z。 Z would be of interest。

 We'd like to know that， and we often give up on Z because it's so hard to know it。

And the problems we're focusing on are problems one and two。Problem one says。Give me some samples。

X R that come from P。Problem 2 says。Either by solving problem one or in some other way。

 please tell me the expected value of some functions I'm interested in under a nasty red distribution。

 so I want to know the average value of phi。Which is some function I'm interested in。

That's the average under the nasty red distribution of the function。

 and there might be several such functions by that we want to know the average value of。We can use。

Solutions to problem one to answer problem two， because we can just say， well。

 here's an estimator or。This expected value， we can estimate。That。By。sumuming up。

By at the random samples that you got from the distribution。

And look at the empirical average as high。So， that's。A possible way of using。Problem 1 to solve。

 problem 2。And sometimes today， the nasty red distribution will be the P of a spin system。

 So one example I mentioned in the last lecture is maybe we're interested in nanomagnets。

And we have a spin system with an energy E。That depends on the couplings J。And。The energy system。

 the energy of a spin system。Is。A sum of a load of。Waitage。Cross terms between pairs of spins。

And there may also be local fields H and at each of the littlepins， and where X here is。

An n dimensionsal binary vector。So that's an example。

Of a problem we might want to solve the sort of things you might want to know for your nanomagnet are what is its average energy。

 what's the fluctuations in its energy， which you can get if you know the mean squared energy and the mean energy。

 what's its mean magnetization， which is the average of the spins or。

Maybe what's its mean squared magnetization。 And we might be interested in the entropy of it。

 which is the average of log1 over P。So those are a bunch of things we might want to know。

For a nano magnet。 And you probably want to want to know all of those at a range of temperature so we can pop in a parameter beta。

Like this， that multiplies the energy。 And then we've got an normalizing constant that now depends on。

The inverse temperature theta。Is。Call inverse temperature。

So those are examples of things you might want to know。

And I emphasize last time when we do Monte Carlo methods。

 we are not trying to find the most probable state of a system。 so we're not trying to minimize P。

We would only be imposly doing that if we set the temperature。

 the inverse temperature to a very large value。 It makes the system very cold。

 then it will hopefully be finding its ground state。 but that's not the goal of a Monte power method。

 We're not trying to in。 We're interested in sampling from this whole distribution。

 seeing what a few samples from its typical。Look like。

 and we're not trying to visit the whole of its typical text because the size of its typical set will easily be bigger than the number of electrons in the universe raised to a very large power。

Okay， so that's the rules of the game and an example of what we're doing and last time we discussed important sampling。

 rejection sampling。Give sampling and the metropolis method。

 The metropolis method is actually a very general catch all because many of the other methods are examples of metropolis methods。

 So when I say the metropolis method today， I'm quite helpful in using it a shorthand for。

A metropolis method with a simple proposal distribution of the type that I showed in the little show。

Let's repeat that little show now just to remind you what we were doing。

 So we had a nasty probability distribution in red， and we had functions whose average values。

IfYou you're interested in。And we looked at simple sampling from a uniform distribution and then reweighting points。

 we looked at sampling from a different distribution which we could draw samples from shown in green。

 the easy distribution Q， then you reweight the points， so this was called important sampling。

 you reweight the five values to take account of having used the wrong distribution and we did that for a variety of distribution called Q。

Then we looked at。Rejection sampling， which is a way of perfectly sampling from the red distribution by throwing away some of the samples you drew from the green distribution。

And rejectioning sampling doesn't work if you do it wrong。

 and it's also very difficult to do in high dimensions。

Often a viable technique in small numbers of dimensions， especially one dimension。

 and there are high dimensional methods such as gib sampling。

 which can use rejection sampling as a component to make them go with the rejection sampling being used in one dimension at a time。

Then we got onto the metropolis method。And my example for the metropolis method was。

We have a continuous space and the nasty distribution is shown in red and we introduce a green distribution which varies with the current state or whatever your current state is。

 we plot， for example， a little Gaussian on that current state and we have a skinny Gaussian whose w isn't necessarily related to properties of the red distribution at all and it doesn't have to be。

So you pick any queuee you want， and then there's a rule when you draw from that queue for either accepting or rejecting that that proposal and we toddled around。

And。The rejections lead to points piling up in the places where P is big。

 So if there weren't any rejections， you'd just be doing a random walk under the green distributions little steps that the rejections cause us to end up with sample。

 but actually that' little often to come from the red distribution。

And there's a theorem that for almost any green distribution cube。啊。Asymptotically。

 the metropolis method will given sufficiently long running time。

 give you a sample at time tea that comes from the bread distribution。However。

 that asymptotic time could be extremely extremely long if you've made a poor choice of。Q。

So that was a metropolis method。

![](img/4933f91728b622bab4e4337dd6cb95cf_6.png)

I also showed you Gib sampling， I won't recap the Gibbs demo now。

But there's a little picture of it here， which involved updating one variable at a time from its conditional distribution to give something that that had the nice property。

But it doesn't have any parameters in it， unlike the metropolis method that I showed you。

 which had to have， you had to pick a few distribution。 It had you had to choose a step size。

 a typical width of your few distribution and that might be quite an important parameter。

 Gi something doesn't have any parameters， which is nice。

 It doesn't mean that Gi sampling is fantastic， but at least you don't have to tune it。Okay。

What we're going to do now is。Focus in a bit on these simple methods。

 especially the metropolis method that we've just been looking at。

 and we're going to criticize it so that we are motivated to do the advanced methods。So。

Here are the problems with the standard monarlo methods。

 especially the metropolis method that I described to you so far。 First。

 it gets around by a random walk and random walk can be very slow。

 I'll go into more detail on that in a moment second。

The metropolis method I showed you has got a step size to it。

 And the results that you get are actually very sensitive to the choice of step size。

 If you choose the tiny step size， your random war problems sketch much worse。

 If you use two biggest step size， then typically， you'll get nowhere very slowly。

So you have to tune it carefully and it would be great to have methods that don't need that sort of careful tuning。

To get good results。Finally。I told you a theorem that says asymptotically this thing will converge。

 but there's no way of telling that these standard methods。 or have they converged。

 You can run a whole load of diagnostics that you really don't get any guarantee of conversionverence。

And we're going to look at solutions of all three of these problems today。

 we're going to discuss more efficient methods that reduce random war behavior。

 we're going to discuss a method called slice sampling that has no tunable parameters or well it does still have some tunable parameters。

 but the critical sensitivity to those parameters is taken away。And finally。

 I'll discuss an amazing thing called exact sampling。

Whi is a method that effectively runs the chain for an infinite time。

 even though it only uses a finite amount of computer time。

 so it knows when to stop because it has run for an infinite time。



![](img/4933f91728b622bab4e4337dd6cb95cf_8.png)

Brilliant。So let's talk about random work behavior。I want to look at a simple。

 a really simple example。Just to。Run home and。What the challenge of random work behavior is。



![](img/4933f91728b622bab4e4337dd6cb95cf_10.png)

So here we have。A little demo。Which is for the following to problem。



![](img/4933f91728b622bab4e4337dd6cb95cf_12.png)

Tub the lights again。Thanks。So for the toy world。The red distribution。Unormalized is。Wong。

In a bunch of places and0 in a bunch of others。 The X itself lives in the set of all integers。

And it's1 whenever x is in this subset of the several inches，0，1，2，3， dot dot dot 20。

And it's  zero otherwise。 Okay， so that's the nasty distribution。

Which if you're very good at plottting grass in your head。Look like this。

And we're going to pretend that we can't draw directly from that distribution and to help us。

 we're going to introduce a simpler distribution that we can draw from because we do have access to a fair coin and we could toss a fair coin。

And we're going to make a proposal。To move from the current place X to a new place X prime。

In this way。we're going to flip the coin and it's going to come up 50。

50 and if it comes up heads well say let's move left。And if it comes up。Taleles will say。

 let's move right one unit。So this is an example of a nasty distribution。

Which if we actually knew how wide this was， we would realize it's roughly 20 wide。

 so capital L is going to be my name for the long length scale or a distribution and the steps that were taking here。

I'll call steps of size 1。 So I'm giving a name to my。Step sized parameter， epsilon。

 And I'm saying it's warm here。Okay， what do I mean by L， well。

 it's something like the distance from one typical point in the typical set to another typical point。



![](img/4933f91728b622bab4e4337dd6cb95cf_14.png)

Something like that。You could argue maybe that or else should be 10 or。4のま。It's all ballpark numbers。

So here are some questions about this chain。I'll just set it going you can imagine if this lecture theatre is 20 meters wide。

 I could perform this for you now by tossing the coin and either moving to the right or to the left and those proposed moves when you use the mecropolis method will always in fact be accepted if I'm in the middle of the lecture theatre because the probability ratio between any two adjacent places。

 P star and P star is one and the Q ratio is always going to be one because you put a 50% chance of coming back from that but when I actually get to the wall if we propose。

Moving to the right， then that will be forbidden。And you'll get an acceptance probability of zero in those cases。

So there's the first 20 steps on the screen。Of this chain starting from the middle I started off at at an arbitraryry place。

 x is 10， I think is where I started it and you can see it went。And that's 20 iterations。

 so here are some questions for you to discuss。

![](img/4933f91728b622bab4e4337dd6cb95cf_16.png)

First and warm。Roughly。How long will it take until this chain generate a good sample from P。好。

To his chain。Generates。A good。Sample from pay。And I haven't really defined who good。

 but I'd just like you to turn to your neighbour， and。Answer the question anyway。

 this is the real world people don't。Defing things completely precisely。

So how long is it going to have to run for？And if you're struggling with that question。

 here's another question which is perhaps more precise。

 How long do you think it's going to be roughly until。We hit。A。Wa， one wall， little the other。

And question three， how long until we。How long do you think it'll be until we've hit both ball？Okay。

 questions 2 and 3 are precise questions。 I'm asking you for a probability distribution。

 and you can compute it if you want。 I'd like you to roughly tell me what that probability distribution is。

 How long until we hit one wall， how long until we hit two。

 And then you could have a think about whether those。Questions are relevant to question one。

 how long do you need to run the chain for starting from， say， x equal 10？

Until you think you're getting a good。How good friend about your that。So chat your neighbors。



![](img/4933f91728b622bab4e4337dd6cb95cf_18.png)

Okay， any thoughts on any of these questions。Yeah。Okay， which question are you answering？嗯m。😊，Okay。

 so to get a good sample from P， you're saying it has to have a chance of。

 of getting quite a long way。 And that's going to be quite a rare thing that it manages to go a long way。

 So your suggestion was。Once it's made about 10 unlikely things happened happened。

 then maybe we will have got there and so what is half of the 10， that's about one in a thousand。

 isn't it， so you're saying after about a thousand steps what you're saying then you think might it might be doing All right。

Because about 10 unlikely things need happen。 Okay， that's an interesting frame of thought。

 And it may well be in the right book。 Any other ways of。Answering any of these questions。Anyone。Yes。

Okay。Okay， so you're saying if we've had long enough to hit a wall。

 then it's probably long enough be a good sample。 Allright， so how long is it until we hit a wall。

 since you think this is the way times answer question why。About 100 steps。 Why about 100。Grand。

So the distance you go， the typical distance you've gone is something like the square root。

Of the number of time steps for a random walk。 But let's confirm that statement。 So even though。

It only takes 10 steps in principle to reach a wall。 You'd be。

 That would be quite unlikely to happen。 And you only need 31 steps in principle if you go that way put 10 steps。

 then this paper21 steps， you will have。

![](img/4933f91728b622bab4e4337dd6cb95cf_20.png)

Mi did both walls。 So you only need 31 steps， but we're actually expecting to take about 100 steps to get to one wall。

 And then if you want to get all the way from there to the other wall， maybe properly。

Maybe another 400， 500 to have a chance of getting back。So let's， let's go through the reasoning。

 So let's define the distance that the random walk will have gone。

To the deelta x is a sum of all the steps we make。So after a time， capital T。

The distance we've gone a theriine capital P is a sum of our load of steps， S T in each of the Ss。

Is either plus one。Or -1， Or it could be 0 if we do a rejection and stay where we are。

But to start with。We're in the middle of the lecture theatre。 We're not doing any rejections。

 So let's actually neglect the walls to make life。Easy， and just get a rough answer。

And then the steps are all either plus minus one variables。And we're interested in。

The variance of Delta X。The Delta X says how far we've gone we're interested in。

How wide that distribution is。 If we look at the variance of delve x。

 which is the average value of delta x squared。Delta x is a sum of independent random variables。

 and so variances add。 So the variance of deelta x is the sum of the variances。

Of the individual steps。If you take a single step that's either plus one or minus-1。

 it means squared value is one squared， which is one， So all of these things are1。And so。

 the variance。Of Delta X is T。Okay。So， if you want。The typical distance you've gone。To be al square。

Then， you need。To run this chain for time。L on。Epsilon squared。

 I've thrown in an epsilon just to show you how this is scaling in general in general。

In this particular case， epsilon is one， these steps were of size1。

 So when I said what the mean squared step size was， this is t epsilon squared。

So for this to equal L squared， you need your T to be l on at one squared。Allright。

 so that's a nasty scaling。 It's scaling quadraically with the ratio of the size of your space for the size of the steps you're taking in the space。

 So the exact， for this example。We're expecting either 100 or 400 or something like that to be the answer to question。

2 and question 3。And then the answer to question one is maybe one of those， it's not quite clear。

Which， so let's keep running the chain。So after 40 iterations， that's where we're up to。

60 iterations。80 iterations and upper 100 iterations。We have reached a war。

 So in this particular run，100 was a very good guess。And we keep on going。

keep on bonking against the wall。 And whenever we buned against the wall。

 we stayed in the current place， we proposed to move to the right。

 but we weren't allowed to we keep on going。 And that's 200 iterations，2，202，40，2，60，2，80 were back。

 hitting the same wall。300。400，440， okay， and then we've gone and we've proposed to move after 480 iterations。

 so unreasonably in agreement with what you said，100 to reach the first one million extra of 400 to reach the other ball。

So that。Rule of thumb back of envelope method has got us what looks like quite a good estimate and we keep on running and we come back and we hit that wall again and again and again。

And then， maybe。400 iterations later were still over at that wall， and then we'd have a run of。

Progressed to the other side and 900 was another 400 iterations。The 500。

 we were back hitting the first spot。Okay。So that's what happens when you run this chain。So it takes。

Thousands of iterations to get good independent points。

And one other way of visualizing this is to imagine making a histogram of where we have been during this simulation。

 So here's the histogram after 40 iterations after 80 after 120 I'm just stacking it up。

 So this is for the simulation we just did。

![](img/4933f91728b622bab4e4337dd6cb95cf_22.png)

So after 400 iterations， 500， we managed to hit both walls。

 but still our histogram of where we've actually been is quite pigalty， pigty and uneven。

So this is the point at which you might say， I've actually got one decent independent sample from this。

After about 500 iterations or so。Okay。So that's the histogram。

 I'm not saying that when you run a metropolis method like this。

 you should throw away all of the point bar one。 you should just be aware when you collect those thousand points that really the effective number of independent samples you've got after running it for 1。

200 iterations is probably only one or two because you've only just gone past twice 500。Okay。

So that's the random war problem。And。We can analyze this a little bit more。嗯。Another way of。

Looking at this is。To make for ourselves the transition probability matrix。

Which I've shown here multiplied by 100。 So for the chain that we're running here。

 it's got 21 possible states and the transition probabilities。 If you're。

 if you're in a particular state， you read out a column and it shows youve got a 5050 chance of either going up one or them one。

If you're in the end state， you've got a 5050 chance of staying where you are for moving down on。

Okay， so that's the change。And。We can now。For this fantastically simple problem。

 we can actually answer question warm really quite precisely we can say well for any particular duration。

 what's the probability distribution of where you will have got to if you start from x equals 10 at time0。

And you can answer that question for any starting position。

 And we can plot the probability dispute of where you will have actually got to。So。

This is the answer to after zero steps。 What's your probability distribution。 The answer is。

 whether you're either in location 10 or you're in location 17， if that was where you started。

 And I'm going to show in yellow and blue， those two。Distributions。

 so we're starting out with a probability one of being in state 10。

Or probably warm of being in state 17。 That's about two starting conditions。 And then after one step。

You're either in these 50，50 in these two yellow places or you're 550 in the two blue places。

Are you with me， any questions？Okay， so after two stats， this is your distribution。After three steps。

 that's your distribution。And you'll recognize this as one of those1，331 things out of the。

But Pacals tri。After four steps， it's this1，4，6，4，1， except the blue distribution。Is 1，4，6，4。

 and then the one has got nudged one step to the left， because if you try to go to 21。

 you will have been forbidden and you will have come back one step。 So those are both 14 6，4，1。

 but the right hand， one in blue is a little bit squished。Right right。

 that's the next row of Pascal's triangle， except that the right hand side now something a bit skeery is happening。

After six iterations， after seven。We're up to distributions that look like this。

 and now I'm going to stop every 25。So that's up to 25 steps and this very jagged picture in yellow is showing you that if you start from 10 after 25 steps。

 you're still quite unlikely to have hit a wall at all and given that you've made an odd number of tosses you are very likely to be in an odd location。

 there's only a few even faces that you have any chance of being in。So after 50 iterations。

It hasn't changed much if you started in 17， you're still very likely to be at the right hand side。

 if you start in the middle， you're more likely to be in the middle than it at the edges and you're very unlikely to be in locations。

9 and 11， so on the next step on when the time is 51。

 you're quite likely to be in location 9 and 11 and you're very unlikely to be in location location 10。

 So it've still got this memory of odd and even because it only loses its odd and even memory whenever it bumps into a wall。

Okay， 75 iterations。100 iterations。 So if you said you think 100 is enough。

 you might look at this graph now and actually think again because if you run it for 100 iteration。

 you say every time I'll just run it for 10 iteration and stop and then I'll go back to 10 and run it again。

From the middle and do another run and man back 10 and do another round。

 And those will all be good samples， but actually。It largely going to be even， aren't they。

 you're not going to get the right fraction of odd numbers from that。So 100 isn't quite long enough。

Even if you start in the middle at 10。And definitely it's not long enough if you start at 17 because you've got a much lower chance than uniform of being in box zero after 100 steps。

 keep going 125，50，175。200s。Okay， it's getting pretty uniform now， so the rough。Statement that， yeah。

 you could be pretty much anywhere after 200。Or after what did we say 400 of where we really were convinced is becoming fairly true now。

 But there's still some wiglyss there。 So we're more likely to be in odd states and yellow。

And that a little bit on。 Now we will likely be an even state just by a little bit。

 So it really hasn't forgotten the initial condition yet。 we keep on going300 steps，3 to5，3537，5。

 and now once you've gone for 400 steps， you can hardly see on the screen the difference between the yellow and the blue。

 So in that sense， you've almost forgotten your initial condition to a precision of I don't know。

 one part and 100 in these probability distribution。

 and you keep on going and the difference gets smaller and and after 500 steps。

 you can scarcely see the difference between those at all。

 and you can scarcely see the difference between between of two of them and the flat distribution which is the nasty red things that were meant be same。

Okay。Good。Any questions about this so far？So the general message we've got is if you make steps of size epsilon。

And if the distribution you're dealing with has got a characteristic length scale of L in those same units。

A random walk method is going to take at least L on expsilon squared steps to get around it may be worse because there might be other properties。

 you know this red distribution might have some nasty canyons in it places that are difficult to get across then you'll have to run it for even longer so this number that we've got T is L on expson squared is just a bound it's a lower bound on how long you might have to run one of these methods for。

Everything I've shown you here is in one dimension。 Let's just make clear how it relates to。

Higher dimensional problems。 in a typical。Problem。If say it's an inference problem that you're working on。

 and if all of these things called X are unknown parameters that are being determined by data。😡。

Then in the real world， typically， you have quite a lot of data and you have quite a lot of unknown parameters。

And so theyre nasty red distribution。May look more like this。It may be two dimensional。

 it may be even 2000 dimensional。And it'll have some long length scale and some length scale that are perhaps a bit shorter。

So。In general， you might have。This is again， a cartoon of the real situation。

There might be gamma dimensions， gamma for G or good， which means well determined dimensions。

 gamma dimensions。Where the length scale is， let's say， L。And then there might be K minus gamma。

 other dimensions。In which the length scale is much larger。

AndThese would be the poorly determined parameters。 This is the total number of parameters。

 The dimensionality of x is K K minus gamma dimensions are poorly determined by the data。

 You haven't pinned them down yet。And gamma are well determined by the data。

So this is your effective number of parameters or your number of degrees of freedom。啊。

The number of welldemin parameters。And if you know， give yourself a step size， epsilon。

You could imagine E Salon。Being。As small as L or smaller。

 so you could use as your step size for your metropolis method。

Something that big with a tiny needed leftilon。Or， you could use something。I think。

Or could you do something？Just think。So you've got freedom when you're designing your metropolis thing to have expsilon be any size you want。

 You， you pick that。Prameter， what's going to happen now well？

If all your steps are accepted and you just do around the walk。

 then it's still the case that the typical distance you will have gone。😡。

After two steps is growing as a square root of t。And it's going to take you。

At least El on Epson squared steps to get around from one independent point in the distribution to another effectively independent point。

 So you need at least。E on at1 squared stands。Toge。A fresh， independent point。

A fresh independence sample。So that pushes you to say， well， I want epsilon to be really big then。

 So the El on epsilon is as small as possible So this。Fact here， which is true。He's saying。

 let's make it on as big as we can。However。If you make epsilon really big and make as big as L。

 for example， Big L。😡，Then what's going to actually happen Well。

 if you are in the typical set and you make a proposal from this big green sphere here。

Which remember。Is。Gamma dimensionional， effectively， the whole space is K dimensional。

And gamma of those dimensions take us off this pancake。

 There's a thin pancake with a width of only little else。And then so in many of those dimensions。

 we'll be falling off the pancake。What that means is the probability of making an acceptable loop move if Epson is big is going to be the ratio of。

Thisball game。t2。F volume。And that's bad news。Let's just think about that。诶。

You use an epsilon that's significantly bigger than little L， the little X scale。

 Then the probability of making an accepted move。Is tiny。It's。In all of the long dimensions。

 you don't need to worry， you're very unlikely to fall off the pancake， but in the short dimensions。

The chance of staying on the pancake is tiny， it's going to be the volume of the pancake。In。

In the in the subspace pattern of the pancake， you've got that length raised of the power gamma。

 which is the number of dimensions。That go off the pancake。

 and then you divide that by the volume of the sphere that you're drawing from。 So this is。

The probability of making an accepted move。And that is the ratio of。L。

 the little length over your step size epsilon raised to possibly quite a big number gamma。

 the number of wellde parameters parameters， which could easily be00。

This is a disaster if you make x one big。In fact， if you make it bigger than little L at all。

 So essentially， there's a constraint that。You can't。Go ahead。Epsilon， greater than L。It's bad news。

Because。Even though you wanted to， in order to reduce your random walk properties。

He wanted to go here。You'll actually end up with a chain that just sits still and makes proposals proposal。

 and all of those are rejected。Except for。A very， very small chance of finally making a proposal that makes a nice big hop and take you somewhere acceptable。

 But it would happen so rarely that you don't actually want to be here。So， in practice。The feasible。

So of sensible。Fs of epsilon。啊。A rats。And obviously， you don't want to make it unnecessarily small。

Actually， this is where you want to be。You want to somehow know what the smallest length scale of your distribution is。

 And then that's roughly what you want your step size X1 to be。

 If you're using a metropolis method with some simple proposal distribution like assterical gas。

So in practice， people using those sort of。Metropolis methods。Well then find。

That their optimal expson is roughly the smallest length scale。

And when they run their metropolis method with that smallest length scale as their step size， then。

They will find。That they're accepting roughly 50% of the proposals。 So the。

Resulting optimal acceptance probability。Is roughly a half， possibly a little bit bigger than a half。

 but not a million miles from a half。Okay。So I've spent ages talking about random walks。

And now what we want to do is reveal some ways of getting rid of these random work problems。

What we've shown here is we've got two issues。 One is that we have random war behavior。

 We would like cunning methods that don't get around by random war that persist instead。

 that persist in going in a particular direction in some way such that you're still asymptotically drawing right。

 drawing from the right distribution。But。😡，You keep going on a short time scale in a consistent direction。

So that's goal number one and goal number two is it's a pain in the neck to have to carefully tune these step sizes if you don't know what the shortest length scale of your problem is。

 it will really pay off for you to find that out because if you use a step size that's too big you'll actually be running a simulation that will do nothing a lot of the time。

And if you make it too small， you're wasting time quadraically badly。

 so it would be brilliant to have methods that didn't require this special， sensitive。

 careful tuning we must have a robust method that is self tuning that automatically chooses the right step size in a way that is valid。

 not using any sort of hack。So， let's now。Address both of those。



![](img/4933f91728b622bab4e4337dd6cb95cf_24.png)

I is。So we have zipped through all of these pictures here。



![](img/4933f91728b622bab4e4337dd6cb95cf_26.png)

And。Were now。Talking about deficient Monte Carlo methods。

And the first efficient method we'll talk about is called Hamiltonian Monte Carlo。

And Hamilton in Monte Carlo is something you can do if you've got yourself a Monte Carlo method。

Which is like the metropolis method we were just discussing。 So it's in a continuous state space。

 and it's one where you're perhaps used to making small proposals of small moves using。

 say a gasussian distribution for problems of that type， you may be able to use。

The Hamiltonian Monte Carlo method。This is how it works let's。I the relevant demo。Look， so。

I'll show you， first。

![](img/4933f91728b622bab4e4337dd6cb95cf_28.png)

A problem。Here's the problem。It's actually a Gaussian distribution。 So we know all about Gaussian。

 and I'm going to pretend that we don't know how how to sample from it。

 So I'm attempting to sample from the nasty reddish orange Gaussian distribution。

 which is a highly correlated Gaussian distribution in two dimensions。

And I've started from an initial condition that doesn't lie in the typical set and I'm using the metropolis method making little spherical green proposals。

 spherical proposals centered on the current point and off we go and go steps up but step in each time we propose a new place in blue and we either accept or rejected almost all of these proposals have been except at least the ones you're seeing how。

 I guess there were an equal number of proposal going uphill away from the typical set that those got rejected and I didn't have to show those on the screen so you can't see the rejection。

So that was after， I don't know，20 or post steps， and we run it for another 20 or post steps。

And that's what we've got to do。 I went for another 20 or so step。 and we've got there。

 another 20 or so， and we're there， another 20 or so and we're there。

 which is sort of where we were a moment ago。 So we now are spending lots of computer time making little steps。

😊，And not getting very far。 we a little run of progress there maybe and now we sit still again and what paint right？

Okay， so that's an example world。No。Let me describe to you how the。Hamiltonian， Monte Carlo。

Methhood works。Hamiltonian Monte Carlo。Has got two names， actually。

It's either called Hamiltonaltonian Mucallo。Or in the old days。

 it used to be called hybrid Mon Carello。Or that I won't go into。

 So the modern name for it is Hamiltonian。Montic Carlo。

 but if you see hyp people talking about hybrid Monte Carlo， it's exactly the same thing。

Here's the cheaty way that this works。 We're imagining that we've got a nasty distribution that we are finding very difficult to draw samples from。

And what we're going to do。Is we're going to take this difficult。

 high dimensional problem and we're going to say， all right。

 let's make the dimensionality twice as big。And let's define a new distribution。

Over x and a new thing called P。Which is going to be called the momentum。

So we'll make the problem twice as big as in dimensionality and we'll define the joint distribution of x and P to be。

The visual nasty distribution we first thought of on x multiplied by。A simple distribution。

 E to the minus half。Pacequa。On M。For the momentum variable。Appropriately。Normalize。Zed。我们慢走。

So we make the problem space twice as big。And we say， okay。

 you find it difficult to sample from this distribution。

 Why don't you try and solve this problem instead？It's twice as big and it's not obvious why this should help at all。

Well， the neat thing we've now done is。You can think of this probability distribution as being e to the minus an energy function。

Which you can think of as a potential energy in Xspace。For us， we've got a kinetic energy term。

 half P squared。OnM。Or normal。And this right-hand side here is sort of familiar if you're thinking of your system as a physical system with a potential energy and a kinetic energy。

 and we know all about such systems， we know Newton's laws and Newton's laws are a way of getting around on a total energy function like this in a way that conserves energy。

So here's the trick， we define an augmented problem that's twice as big。

That opens up to us a whole load of new moves we can do。 We can move around。

On services of constant total energy by using Newton's laws。

What does the real world do in order to sample from nasty distributions like this。

 whether it uses Newton's laws and maybe if we're trying to simulate it at a particular temperature。

 we have some sort of interaction with a heat back。

And because these momentum variables have a very simple distribution。

 we know how to redraw them from a distribution corresponding to a heat bat distribution。

 so every now and then we can have the momentum variables interact with a heat bat。

So that's like what the real world， the real world uses Newton's laws to make X move around and Newton's laws say the X dot is basically something to do with your momentum so you go in the direction of your momentum。

And P dot is something to do with the force。 So your P dot is。The derivative of the。

 the energy with respect to X。I won't bother putting in exact minus signs but this is Newton's laws。

 you keep going in the direct of velocity。And this is E from M。 Act， you look at the force。

 which is the derivative of the energy with respect to your state space variables。

 and you make the momentum change in that direction。 You accelerate in the direction of the force。

All right。In detail。What Hamiltontonian Monte Carlo does。

Is more complicated than what I just said because you actually need a practical computer algorithm to simulate Newton's laws。

But the rough idea is this one simulate Newton's laws。

And we'll admit that we're actually doing that approximately。

 but we're going to fix up the approximate mass。By a clever。P step。

Or reject rule that checks on what's happened to the change in energy。The change in the total energy。

Of your little simulation。And step 3 is。Randomize。The momentum。P。

 by drawing it from the correct distribution E to the minus half。Pleaseace， glad。好 end。

And you repeat。So the rough idea is Newton's laws randomized momentum。

 Newton's laws randomized momentum， and you run Newton's laws for a time。

 and that can be an arbitrary。Time， and that's one of the tunenable parameters you will still have to adjust。

 Your simulation will involve little step sizes because you have to actually do， I don't know。

 leapfrog method or something like that。 And you have to choose little steps of time。

 So it still has parameters which are going to be pains in the neck。

But during the Newtons World bits， you're going to be moving a long way。

 And I'll show you that for this whole problem。To make this whole thing work。

 we accept or reject every one of those Newton's law simulations。 and based on the change in energy。

 If the energy goes up during a simulation， you say， for， that shouldn't really have happened。

 but total energy should have stayed constant， maybe I'll reject。

 and you flip a coin to determine whether you reject if the energy goes down， you say， well。

 that shouldn't have happened either， but I'll accept it anyway because that's the way it actually worked。

 All the details are in the book。So let's go ahead and show you that happening。

And so we're going to start from the same start point。嗯。

And I can do this a few times so you get to see the flavor。Of this。So here's what we did。

 We started from the same start point shown by the White arrow。

 and I used Newton's laws with it quite a。Large time step so that when we started from this place miles from the typical step。

 Remember， this is a quadratic basin here that we're dealing with。 So it's got very。

 very steep when we're at the place shown by the White arrow。

 So there's a matter of force taking a down hill it。

 We go whoosh right the way across the valley and out the far side on the first first step And then the momentum is turning around。

 It's saying， no， no， go back the other way。 And after the second step， we turned around on momentum。

 we're going back， and we go to the yellow place after what is it。

1 also of these little steps of Newtonian simulation and we thought， okay。

 check what's happened to the energy and the answer is well it went down and up and down and sorry the total energy hasn't changed。

 The potential energy has gone way up and down。 the kinetic energy has gone way up and down the total energy hasn't changed very much and we accept this move and so we've gone all the way from the white arrow to the yellow thing which you might think isn't much progress。

 but at least you could see there was some persistentence we sort of kept on going and we actually went so far that we turned around and came back so。

We persisted in lots of different directions。Okay， big golf accepted and we run again。And。

Now we've gone z and we've gone way over there so we've easily gone much further than the total length scale of this problem if you integrate up our pedometer。

So we're making these huge long hops。 and we happen to have gone downhill just a little bit， as well。

嗯。Do another run， remember when we randomize momentum if it just happens to be the case that we've gone downhill at the end of one of these things。

 it' a lower place than where we started， we'll still have the same total energy。

 but because we've gone downhill， we have a matter of momentum when you do step three that says randomizing momentum。

That means your momentum will get calmed down， you'll suddenly lose the load of the energy because you draw from the correct distribution instead of this massive high speed speed this high speed you've got。

 to chuck that away and say， hey， give me a fresh speed of order one。So let's watch that happen。

 Okay， you see now we're not going so fast。And we end up at a lower place and we accept。

AndFrom there， we randomize P again and off we go and we're there。 We randomize P again。 we go there。

 We randomized P again。 and now look what's going to happen。

 We happen to be in this is showing a contour of energy for one or two or something like that。

 So this really shows the typical set， which is where we ought to be。

 So will we ever hop outside significantly outside the orange contour again， Well。

 hopefully not for a while， we randomized momentum。 And now we're there。

 and we haven't gone very far。 have we what did us out。 that say we were going to persist。

 Well let's try again We just happened to go a very short distance。

 randomized the momentum off we go。We're going。Quite a long way。Pranandomized again。

We don't go very far。 randomomized again。 very far。 And then whoosh。

 let and go right at the far side。 So sometimes when the momentum just happens to be pointing the right way。

 we do these massive long moves that take us right the way along the typical step。Okay。

 randomize the momentum again。We do some jiggling around up at that corner。Otherwise again。

 we've gone a little bit further up the valley。Now we come back again。And randomomized again。

 randomized again。But see how we're making much faster progress around than the standard metropolis method。

 just to ram that home， let's go back to metropolis method and start from a place in the typical set。

So whats strong on。Okay， so we start in a typical fit， and now we're using the metropolis method。

And every one of these little new blue boxes is created by proposing a random little change。

 and then we evaluate the new energy in that location。

The amount of computer time it takes to make a little step and find the energy in that new location is about the same as the amount of work it takes if you're using Newton's laws and you make a single little step of simulating。

This sort of thing， a little change in position in talking into the velocity and then a little bit of responding to the force because computing the force takes the same amount of computer time as working out the energy。

Allright， so I'm being fair here。 Each of these little blue squares in the metropolis method takes the same amount of computer time as one of the little squares in the Hamiltonian Monte Carlo。

 so。So each of these bushes that we're making is taking the same amount period time。

 and it will take。L over epsilon squared time to actually get from n to end of this distribution。

If we go back and start from exactly the same place with Hamilton and Monte Carlo。Right not there。

 not there， yeah。From here， Okay， then with the same amount of computer time as those， what was it。

 20 or so little blue steps that we were doing before， we get all the way to the yellow place。

 and then we same amount of computer time again， we' got all the way back。And that again。

 we've gone right to the far end of the。So。I hope this makes clear I'm not cheating。

 it really is the case， Hamiltonian Monte Carlo， if it's been appropriately soon。

 can massively reduce your random behavior。But it has a whole load of extra parameters you have to fat around with。

 So we may not be completely in love with it。

![](img/4933f91728b622bab4e4337dd6cb95cf_30.png)

Now， let's move on to another concept called over relaxationation。

The idea of over relaxationation is that it can be applied to give something problems。Gift sampling。

 remember， doesn't have any。Tunable parameters， you just draw from the condition of distribution of each variable one at a time。

And it doesn't have any obvious way of including momentum in it。

 so how can we get persistence to happen？Well。The idea that a cha called Adler came up with。

Its called over relaxationation。Sir。Whereas。And standard gi sampling。

You work out the conditional distribution of the variable。

You work out the conditional distribution of one of the variables condition conditional on all the others。

So， standard dip sampling。With a nasty distribution that could like this。It's takes a slice。

And says what is the conditional distribution of one variable condition on the others and wherever you are at the moment you just make a fresh grar from that distribution。

The idea of over relaxationation is。If your current position is actually here。

 then youre at this point。Then in some cunning way。

 you deliberately draw not from the correct conditional distribution。

 but from a distribution that's somehow biased to the opposite side。Of the mode。

The details are in the book， and there's two ways of doing this。1 is。

If the conditional distribution that you're talking about is a Gasian。

You draw from a Gaussian that is squished and on the far side of the real gassian。

So there's a simple， squishy rule that says squish it down and flip it the opposite side。

And you can prove that asymptically， you'll end up doing the right thing。So， Adler's method。

Which I'll say you now。It's a very simple method。For the case where all the conditional distributions。

Auggasians。And you might say， well， how can it possibly be interesting if all your conditional distributions are Gaussian。

 doesn't that mean that the distribution you're working with is a very simple distribution？Well， no。

 not necessarily。 there do exist interesting distributions。

 all of whose conditional distributions are Gaussian。

 yet the joint distribution is very difficult to sample from。

 So this is an interesting capability to have。So let me show you Adler's method on the Gaussian distribution。

So we've done Hamilton in Mongalow and this is what Gib sampling looks like。



![](img/4933f91728b622bab4e4337dd6cb95cf_32.png)

For the same problem。 So it's exactly the same Gaussian we were just playing with with Hamiltoniltonian and Monte Carlo。

 if you use Gib sampling， there's no parameters at all。

 but the typical steps you take when you draw from the conditional distribution this way or the conditional distribution this way。

Because those two directions are the axes， the typical step to always be of a we。Similar to the W。

The thin width of the green distribution。 So you're never going to be taking sta size Big out。

 They're always going to be staized little out。Which is。

Which means that you've got a random work problem， it's going to take you。

Big L on little L squared time to get an independent sample using gi sampling。So Adler's method。

 that says。Instead。That we draw。Deliberately from the opposite side of the distribution in one way。

 And then we go to the other variable， and we draw from the opposite side of its distribution。

The net result is shown here in red， so you can see we roughly run along the conour with a little bit of wobble up and down the contour。

 If we zoom in on this， I'll show you the individual steps so。This is showing to。

 I forget which way time went。 It's all reversible anyway。

 Let's imagine that we started from the bottom left here。We started a little bit。

Above the green contour at the very bottom left。 And then weve flipped across to the opposite side。

 still a little bit above the green contour。And then we split the opposite again above。

C across and across and across。 And that means we persistently go。

 And if you look at every other position， that's what the red line is showing you。

 you wander along the contour in this two dimensional problem。

And you can do this in higher dimensions and for many problems it turns out that the adler method does reduce your random work behavior and there are various ways of revealing the improvement in performance and one is to invent some simple statistics to keep track of and look at the fluctuations in those statistics and if the autocorrelation time is very short for a statistic then that's an indication that the method is a good fast method that it's mixing quickly so here's a quantity x1 the two variables called x 1 and x2 but here's x1 wandering around under a regular old gib sampling shown and that's in orange then in red iss the overalation version of x1 and you can just eyeball those and you can say yeah x1 is definitely moving around。

Faster under the Adler method。And another quantity you can look at is x1 squared and under gi sampling。

 it takes ages to get around from being in the middle to being at one of the extremes。In contrast。

 the aom method。X1 squared is going up and down much faster。

So that's a crude indication that at least on this to problem。

 the aler method is better for those statistics， at least。

So that's over relaxationexation for conditional distributions that are Gaussians and you might say。

 well that's not going to help me because my problem doesn't involve any conditional distribution for the Gaussian。

 I'm far more interesting than that。

![](img/4933f91728b622bab4e4337dd6cb95cf_34.png)

And there's good news for you， even if you are an interesting person。

 you can still do over relaxation。

![](img/4933f91728b622bab4e4337dd6cb95cf_36.png)

Using another method， and it's called ordered over relaxationexation。

An ordered over relaxationation was invented by Raford Neal。And it works like this。

Imagine that you are doing Gib sampling and you have got a method which will draw you。A new point。

From this。Conditional distribution here， so you're at a current point。Yeah。

And you have got the capability because you're doing G sampling to draw one new point from this conditional distribution。

Well， do now draw K times from that distribution。So you draw pay times。And。

That gives you a whole bunch of points that might look like。This。All right。

make it tiny bit more interesting。 let's put another。uple啊。Right。

 what have I shown up showing in the case K is 7？They've drawn seven green points and the total set of points we have here is a set of eight points。

 including the one that we're currently at。And the audit over method says， okay， now count across 1。

2， three， four， five。Gman 8， you're at the third point。

 Please go to the third one from the other end。So you go to the stick point in this case。

Wherever you are， you go to the point that the opposite one in the queue。All right。

 and that means if you're way over on the left hand side， if you were。

 if the white dot was actually number one in the list， you would have gone the past time。

But this is something that can be done for any real value variable。

And it's preferably correct and valid， and in practice。

 a good value of k might be something like 20 or so。

And the additional work to get 20 drawers from this distribution is quite often not much extra work at all。

 for example， if you have to use adaptive rejection sampling。

 if you were using a rejection sampling method to draw the first of these points in green often adaptive rejection sampling has the property that you can get another K minus one points at almost no cost at all。

 all of the work was consumed in getting the first point。

 then the other ones are free so this can be a very。

 very cheap method and it may well improve your random work behavior。There's no absolute guarantee。

 but it's definitely worth trying and there's a piece of software out there called bugs。

Which means these an inference using Gib sampling and bugs has been around for about 15 or 20 years now。

And it's a way of implementing give sampling for a whole。Feat of different models。

 you specify the model using a simple declarative language and then it figures out how to run the Gibbb sampling for you。

 and I'm pretty sure that the versions of bugs that are out there now have all got ordered over relaxation built into them so you can get this speed up for free or you can at least test it out and see if it does give you a speed up using bugs。

Okay。We've been going for an hour。 shall we just carry on with the advanced methods show。

 Does anyone need a break。Okay， let's keep going， so I've shown you over relaxation。

And now I'd like to move on to this question of dependence on parameters。So。The vanilla。



![](img/4933f91728b622bab4e4337dd6cb95cf_38.png)

Metropolis method we were talking about used a Gaussian distribution with some width。

 and the width of that distribution was crucially important。 We wanted it to be as big as possible。

 and no bigger。When we use Hamiltonian and Monte Carlo， there are similar step size parameters。

Gib sampling doesn't have any parameters， which means that maybe we like it。

But give sampling only works if you've got a problem where you know how to draw from the conditional distribution here。

 and it may be that you're in a world where you just haven't got a clue how to do that。

 Your energy function itself too complicated。 You can evaluate it。

 but you can't draw from the conditional distribution。

It would be nice to have a method that automatically discovers for itself the right depth size。😊。

And that's what slice sampling does。S。We will now discuss。Shy something。

Slice sampling was invented by two people。Mainly breath meal。And John skilllling。

And it's a very elegant。Amazingly simple looking way of solving the problem。 It looks so simple。

 You could imagine a school child inventing it Haley。 And you might say， oh， it's too simple。

 It can't possibly work。So let me show you。

![](img/4933f91728b622bab4e4337dd6cb95cf_40.png)

Slice something。And。I'll do it first for。This good old red one dimensional distribution。

 The idea of slice sampling is you can do it in many dimension by doing one dimension at a time。

 just like give sampling。 it's a method a bit like give sampling。

 you pick a single dimension to work in or a single direction。

 It could be any direction you want in your in your continuous state space and you。

Use the method that I'm going to describe in that one dimension。And then repeat in other dimensions。

So here's our goess。回考。And that's the red distribution。And we have a current location。

But you'll call Xt。And I'm now going to describe to you how we get to the next location。

 which we call xt plus1。And it's going to be quite a few steps， so。Don't hold your breath。First。

At the current location， X T。We evaluate P star， so this is a graph of P star。And we evaluate each。V。

We draw a point uniformly between 0 and p star of x。

And we can think of that as picking a point on this telegraph pole。Then。Wereate。A horizontal object。

Of which。W。Where W is going to be a step size parameter of the slice sampling method。

 whose value we don't care about very much， Because the whole thing is going to be robust to it。

 But this is our guess of what a good step size might be。

We make a little object like this in this little green thing。

Its height is determined by the height of white dot and its offset is chosen randomly uniformly from all possible offsets from the two little ends of this green pole are either aligned with the white dot this way or that way and you pick uniformly from all of those possibilities so we pick。

A uniform choice of this little horizontal strut going off the telegraph pole。All right。

 that was step 2。Step three is you check to see。At those two places。What's the value of P star there？

And most value star there。And if。This value of P star is above。The green line， which it is， you say。

 oh， whoops。That's not far enough。 Let's make an additional step of size W。And then check。

And you keep on stepping out until when you check at that。Pce。Are we above peace？

And the answer here was already yes， we're above， so we stopped stepping out in this direction。

In this direction。We had to step out once and then we got to check， yes， we're above， and so we stop。

And by that process， we've now created a wider green object。

 So this is called the stepping out phase。Then。The next thing we do。

Is we draw uniformly from the green line that weve just created。

 So you pick any point at all on the green line。Which could be， for example。Here。

And this is our candidate that we're possibly going to end up calling X T plus one。

 but we do have to check one more thing， namely。If you look there。

Does that point lie above the red curve。And if it doesn't。We're okay。

 If it does lie above the red curve， we say， whoops， that's no good， sorry。And in this case。

 it does lie above the red curve so we say， sorry， that's no good。And。

To make things run a bit faster， you can optionally wipe out all of the green stuff that lies beyond this rejected point。

Away from it in the sense of away from the white dot that we decided。Okay。So we。

Proposed a point on the green line。We drew one that was above the red curve and we rejected it。

 and now we said， okay， try again， keep drawing from this same green line until you get one that lies below and maybe improbably you might get this。

Over here。In which case now you say no， that's rejected because it。Lying above the red curve too。

 notice we're having to do lots of evaluations of P star in this method。

And so we chuck away this little bit of green hair。

Not now this green thing is really quite a snug fit around the red curve。 So next time we draw。

 it's going to be very unlikely that we're going to miss this time。

 So we draw once more and we draw stay here。And。That lies below the red curve。Y， get that hand。

And we say， parade， you're accepted and we have now moved from there。To that。

And we're done that one it。And then you wipe everything that you've done here。

 except you do keep track of this value of P star， is that going to be useful for you？And you repeat。

The process。Okay， let's do it on the computer for lights sound， please。So we're at a location。

And we draw a vertical point。 and I've shown it in yellow。 We create a green thing of with W。

 It looks as if it's centreed on the yellow thing。 but that's just coincidence。

 It was picked at random。Now， we check are the green endpoints outside above the the red curve。

 They're not。 So we step out with one on left， step out once， and it's done。

 the one on the right have to step out twice。 Now you draw in blue， a new point from the green line。

And that is underneath the red curve。And so we accept it and we're done。Press start。

 draw a point uniformly on the purple line， there it is。Make a thing of with W， step out。Daw from it。

And that lies below the red curve， so we're done。Notice how each time when we're done for this problem。

 which has a P that's a vaguely sort of convex bump。

 we're moving right away from one side to the other side of the distribution。

Let's throw from this purple line。 Now we've drawn something high up because this is a place where P is big。

 So it's possible for the green strut to be high up。 Now we're not going to go so far。

 are we because we step out。And。When we draw from the green thing。

 we can't go right over into the right hand side at all， those are going to be rejected。

That got so notice how we automatically sort of stayed in the place with the narrow peak。

Because it stepped out a shorter distance。And now we've got a low one will possibly go quite a long way。

There's another low one。 We go quite a long way。 Oh， that was our first rejection。

 We made a blue point。 It was above the red line。 So we say no to that。 We should say try again。

Please try that。 that get projected。By again。And that gets accepted。 Okay。

 so that was five steps of slide sampling。 Now， I let it run for 100 iterations or so。

 And you can see it doing its thing。Okay， that was 25 samples。

 and you can associate each of the acceptances with a point underneath the curve and the way you prove the theorem that says slice sampling does the right thing is you prove that it leaves this distribution under the curve invariant。

So that's the proof technique。So that was slice sampling for the nasty distribution in red。

 and I think it looks more exciting and it's more incredible that it really works。

If we do it for a more。Oatward looking distribution that might look like。This。Okay。

 so there in red is an exciting distribution。And let's do slice sampling on it。



![](img/4933f91728b622bab4e4337dd6cb95cf_42.png)

Right， off we go。So there's a yellow thing。To step out。Now， are we done。

 do we need to step out further on the left， clearly yes。We're still under the red tur on the right。

 not clear Okay we did that green point was just below the red so we've stepped out like that now when we draw a point on the green line there's only a fairly small chance it will be accepted there's lots of places that are above the red so for example。

 is above the red line so we' rejected and we say nope。

 can't go there and we shrink in towards the yellow point。

Now we make another draw from the green line。And that gets accepted。

 So we stayed at home in that one piece。Now we do the vertical thing。Make a crosst， step out。

Draw a blue pipe。 Not we've hop from one peak to another。 And we could have done that。

 no matter how low the valley is。 So this is a method that can make lucky leaps across very， very。

Nasty valleys in tea or you know in of energy landscape， very big hills could have been in the way。

 and yet we can travel across them。Okay， so we've gone from one peak to another。 And now， oh。

 look where that yellow point came。 It's really， really low。 That was quite an unusually low point。

 So now when we do the stepping out thing， we're going to get a very broad green thing。

 when we draw from that。😊，We the right。有low光。St out some more please on the left。 Thank you。

For a blue point。 Okay， now we pop back。 So we're hopping between these different peaks。

How we keep going。And that's our first five point。 And if we run it for longer。

You can see how it's visiting all of the people。Well， not quite all of them yet。嗯。

So that's slice sampling。And it's a pretty cool idea。

 and Radford Neil and have both published free software that implements this method。And it's very。

 very general。 All you need is the ability to evaluate the red function where you are。

A really nice thing to notice about slide sampling is it never ends up rejecting the overall proposal it worked and worked and worked and worked and works。

 And in the end， you've got somewhere and that somewhere will be different from where you started from So in contrast to standard metropolis methods where you might do a huge amount of Hamiltonian Montelo simulation dynamics momentum that says reject and you just throw it all away and you haven't made any progress at all here you always will move possibly a very small distance。

 but that may be the right thing to do because maybe you're dealing with a very small typical set。



![](img/4933f91728b622bab4e4337dd6cb95cf_44.png)

So it never rejects and another beauty of size sampling is this step size is W is not a crucial parameter if your w is accidentally 10 times as big as it needs to be。

 well it doesn't matter。 it only takes a very small number of blue points to shrink down through that shrinkage process to the correct width。

And if your w is too small， it only takes a small number of these stepping out operations which proceed linearly from your overly small green thing。

 only a small number of stepouts will be required to encompass the width of the red distribution。

So W isn't crucial。 It's still a good idea to tune it。

 but you don't have a catastrophic failure if you get your W too small or too large。

And slice sampling does have the property that typically you will make a step。

That is as big as the width of the peak that you're dealing with。

 So it is the final step is of roughly the optimal size。Okay。That's life sampling。

And now what I'd like to finish with today is talking about exact sampling。

So how long do you need to run a Monte Carlo method for？I'm going to tell you。

What feels to me like really quite an amazing breakthrough of the Monte Carlo community For decades。

 the answer to this question。 How long do I need to run it for was well， how long the be stringing。

 you don't really know you just yeah you get a bit of fear you made some diagnostic so you get a sort of la answer for the question how long should I run it for and you always felt dissatisfied Well。

 there was a breakthrough and it happened in approximately 1996 with the invention of methods that are full I call them exact sampling they're also known as perfect sampling and there's a whole family of different perfect sampling methods and I'm going to describe to the easiest one to explain there's probably many tens of papers on thispro now。

 maybe even hundreds。So。How long should we run the simulation for？Well。

Exact sampling is based on the idea that you should run it for an infinite long time because then you're fine。

How long。Infinitely long。With answer。And you might say， okay。

 that sounds like a lot of computer time， but here's the beauty of it。

You can establish the outcome of an infinitely long computer simulation。

With a finite amount of computer time。And we're going to run the simulation from the path。

From infinitely long in the past。Up to。The present。So how does that help？But let me explain。

Let's imagine that this is the state space of。Your simulation。And for simplicity， for concrete。

 let's imagine， we're talking about the lecturer flipping the coin to determine whether he goes right or left in the lecture theatre that is 20 paces wide。

 So the state space。Go like this。And now what I'm asking you to imagine is that an infinite time ago。

A little army of 21。Lecturers。All started off。At time mind synfinity。And。The 21 different locations。

 and every one of them then started running the Monte Carlo simulation of the metropolis algorithm。

So imagine that that happened and imagine that they used the same random numbers。So。

The random numbers。For all of them are shown here。 And the first one was heads， tail， heads， had。

 had， tails， tails， tail heads。And pick。And for any time。

 we imagine we can consult a little encyclopedia of outcomes。 And we can say at time -1732。

 what was it， And the answer might be hexed。 And we can move the right to say tale。

 whenever you come back to thiss like the feededer and say， tell again， what was the outcome at -1，7。

32， it will tell you text。All right， so all of them are going along。😡，And。So here's one of them。And。

If。Inな谁。Is there any way I can figure out？Where one of these is。At this time。

Without actually having to start at time minus infinity。Could you do that？Well， maybe it could。

 because。Let's say you don't know where。Any of them got to at time minus-1732。

Except that you do know that。They must have been either in this state or this state or this state or this state。

 So there's actually 21 possible states they could have been in at this time。And if you now。

 without knowing which of those is true， if you run all 21 of them forward in time and say， well。

 let's just see now what would have happened for each of those 21 hypotheses。

And so you can try all 21 of them and run them forward。Just from this time。Up to the present。

And if all of these end up sort of going， colliding with walls and that sort of thing it such a way that all 21。

End up with here。Then it must be the case that all 21 of these guys have ended up here。

 even though you don't know where they were at this point。😡，So this is the trick。The trick is。Some。

Marupane。Monte Carlo simulations have the property that they do coalesce in time。

So if you take all of the state space at time -1，7，3，2。And run it forward。

 maybe you'll find that all gazillion or 21， however many there are。

Of these states will have coalesced into a single state。

Which then proved that if you had actually run this for an infiniteprint time。

You would have come somewhere here， it doesn't matter where and you would have ended up in this point。

 which therefore is where you would have got to by running this thing in a long time。

So what's the exact sampling method， the exact sampling method says。Pick a time into the past。

Whatever，100 steps back，500 steps back， pick whatever you want。 It doesn't matter。

 So we go back 100 steps。Now， simulate forward in time every single initial condition。

That you could have been at。100 times steps ago。Or if you can get away with it。

 simulate fewer than that， because maybe you don't need to simulate all of them。

 simulate them all forward in time and。😡，If they reach。Different points。

Note that they're all using the same。Random coin flipses each other。 So here's the random numbers。

So they're all using the same random numbers， that means that if two of them do get into the same state as each other at some point。

 they will remain in lockstep thereafter。Therefore you find at time zero。

Is that they are in several states。 you say， okay， bummer， but we're not done yet。 We go back。

Further， maybe。200 in the pass and repeat the operation。And see if these guys。

By the time we go forward。I've coalesced， and if they haven't， you go back further than time。

Maybe just 400， you keep on going that until they have all coalescce。

And then you follow them along and you see where they all ended。

 and then you can declare that this state is where you would have got to if you'd run it for an infant。

So that's the method and it's very expensive in general because you have to simulate 21 initial conditions or in general sort of 2 to the n where n is a big number。

But if you're really， really， really cuning， you can establish that they have all coalesced without actually stimulating all of them。

😡，And for the special case of the 21 lecturers， you actually only need to simulate the rightmost lecturer and the leftmost lecturer。

 And you see if those end up sitting on top of each other。

 And if they are sitting on top of each other， then all the intermediate lecturers must have coalesced with the two of them as well。

 And that's the general idea of most exact sampling methods。So you have some way of ordering。

The state space。 And then you have the highest state and the lowest state。

 And you simulate the two of them forward。And then if they have coalesced。Then at time0。

You've got yourself a perfect sample。 If you haven't。

 you just go back further using exactly the same random numbers and you take the highest state and the lower state and simulate them forward。

 And you have to do very careful poofs to prove it is valid。

I'm going to show you some beautiful examples of this map。So， the first example。

Is to draw a random tiling of a hexagon。So here's a hexagon and it' been tiled with red。

Blue and green lozenges。The lozenges can have three orientations。

 and they're shown by the three different colors。And you can think of this also not only as a tiling of a hexagon with those lozenges。

 you can also think of it as filling a brick yard with cubicle bricks。And the task is。

 please give me a random tiling of the hexagon， a perfectly random tiling of the hexagon。

And so you invent a Markov chain， which you can think of as。

Adding and removing bricks from the brickyard And you say， oh dear。

 how long do I need to add and remove bricks from the brickyard And the answer is going to be well。

 we'll do it for infinitely long， but we only need to simulate a finite amount of time to establish that the completely full brickyard and completely empty brickyard would both have ended up in the same state。

 Let's do it。So on the left we have the empty brick guard and on the right we have the full brick yard and they're simulated forward in time and it didn't work out so we go back from 128 steps to 256 steps in the past we run it forward and they're coalesce so we keep going and there is a perfect tiling of the heion。

And so that's how long it took it took， in this case。

 it took us 256 units of computer eye to get the answer。嗯。And。We go。Do it again。128 stepss。

Assn't coalescce， go back to 256。So this is using a different。

 fresh set of random numbers that I defined all the way into the past。 Has it coalesced。

 Ha it coalesced， Yes， just at the last moment it coalesced。Good again。128 cents。Has it careescce？No。

 so we go back to。256 steps into the pass。And it's coalesced now。 and it keep keep on going。

 N B note that， you do not give out the answer when they have coalesced because coalescence occurs in unusual states。

 like when two electrodes are both right next to each other at the left hand side and the coin says go left。

 Then now we've coalesed。 and that happens in very unusual states。

 So the answer isn't when the coalescence happens， it's the answer at time 0。

 which you find by continuing simulation。All right， do you want to see any more of those。

 I'll give you one more。Occasionally， it takes。More than 2506 steps from the past。但。When I said that。

 that just for this particular size of hexagon。Running this particular algorithm。Okay。

 it's coalescce boom and there's another tiling for free and you might say who cares about tilings Well。

 I'm not sure what this is useful for， but these tilings are actually very beautiful things and through this work on exact sampling of tilings。

😊，Some discoveries were made。So。Here is a perfect piling using those three lozenges of a bigger hexagon。

And here is a perfect tiling of an even bigger hexagon。And when you look at that。

 you might start to say， is something happening？Is there a perfect circle appearing？And the edge。

 it's frozen， all the tiles are red up toward a perimmeterome and they're all yellow in that corner and there's this sort of Arctic circle phenomenon of the freezingezing of the tile into of a particular orientation in the corner。

And they conjectured on the basis of this work on randomly generated tilings。

 maybe a random tiling of the hexagon has the property for very large hexagons that it's got a circular edge beyond which it's frozen with very high probability。

 And they proved that theorem。 So this was a theorem that was discovered thanks to exact sampling。

The final example I want to show you is to do with icing models。

The icing model is a favourite toy world of the statistical physicists。And。

If you went back before 1996。And ask people， oh goodness me this very interesting icing model that I've heard about here it can do phase transition。

 it's a bit of a model for the melting of ice and that sort of thing， it's got critical phenomena。

 it does interesting fluctuations when it melts。😊，Tell me。

 I want to simulate it with the monocol matter。 How long can I should I simulate it for？

 I want to make a really good typical sample， People have said the b on answer， oh， I don't know。

 it's hard。 it's difficult。 You have this phenomenaal， critical slowing down so that near the。

phase transition， you have to simulate it for a very long time and no one really knows how long to simulate it for。

嗯。In 96， this exact sampling community made a breakthrough and for me it's a bit comparable to the breakthrough in superconductivity when I was an undergraduate in year one they said。

 hey， here's superconductivity， look we've got some liquid heum and we'll make some things levitate。

And then two years later， came back into the same lecture data。 And they said， hey。

 there's been a breakthrough。 We've got high temperature superductorss and they got out liquid nitrogen。

 and there many things to levitate。 So there's been this massive transformation in what they could do。

😊，And a similar breakthrough has happened with icing models， which means that。It's now possible。

To show a sample。Of an icing model。 And to say this is a perfect sample at the critical temperature。

 the melting temperature of the icing model。So just to introduce you to icing models。

 the icing model is a spin system where every spin is either up or down and it's coupled to its immediate neighbor so it likes to be the same state as its immediate neighbors。

 but on the other hand it it's got a temperature so it sort of has a tendency to not do the same as its neighbors necessarily in a very high temperature that that' always be random so what's it look like here's a standard metropolis method here it is at low temperature you can see it's all white with a tiny bit of blue。

Or it could be。Or white with a tiny bit of blue。Or it could be。

Well white Jordan and orberry is trying to make its mind up， it wants to be all white or all blue。

 low temperatures， but high temperatures， it's just especially mess。Low temperatures。

 immediate temperatures， spec were a bitlobby， a bit blobby。 high temperatures very， very specly。

And if you lower the temperature it's getting all sort of blobby， blobby on lots of blank scales。

 which is an interesting phenomenon that these things have so these long clusters。

And then below a certain temperature。It all turns into a single colour eventually。

 But when you're using thetros method， it's like watching paintry for it to lose the one of the。 say。

 how I'm go。 I'm going to be all blue with just a little bit for white。

 There are other algorithms you can use， which are much quicker at flipping between the all blue and the all white states。

So this is as if we're in the pre1996 state and someone saying oh how long are I run it for I'm at a critical temperature I'm really interested you know I know the critical temperature is here or wherever it is I want to get a perfect sample but I don't know how long to run it for I want to get a perfect sample for a really big spin system because it's only for really big spin systems that I can measure how big these different length scales are and find the re clusters and so forth。

😊，So that's the challenge。And the exact sampling community。

Came up with a method of solving this just a little bit more introduction to theicing model I mentioned the critical temperature as you crank which way to this go。

 the temperature is going to figure to the right or cranking up the temperature。

And what happens to the energy is the hotter you make it the more energy you've got。

 but the fluctuations in energy， the standard deviation of the energy is shown on this second graph bottom layer。

And you can see that at a temperature of 2。3 or so。

 the fluctuations in the energy get really quite big compared with what they are at other temperatures。

 so there's something wacky going on at the temperature of 2。

3 and that's the melting from the mainly all blue or all white state into a much more specky clustery sort of state。

The average magnetization， which is how much all blue or all white。

 the mean squared magnetization is shown in graph C。

 which is the top right hand one and at very low temperatures it's very， very magnetized。

 it's almost always entirely nearly entirely blue on the entirely white And as you get to the critical temperature suddenly it becomes sort of 5050 and very。

 very blotchy。Okay， so that's what icing models look like and。Here is a。

 I forget how big this thing is， roughly 800 by 800 pixel。Iing model at its critical temperature。

And I'm going to show you a computer program that will make another of these perfect samples for you right now。

So this is a piece of software written by。Prop and Wilson。

 who are two of the heroes of exact sampling， and I'm in the start at running now。And here it goes。

 It's running from the past to the present。 And that little diagram top right is showing what's happening to the the top most。

State and the bottom mode state。 And it's done。 So it had to go 32 steps back into the past for the particular simulation method it was using。

 And what we're visualizing here is not the state of the icing model。

 but the state of a more general system called the random cluster model。

 which is a set of points with edges that are either present or not present between adjacent points。

And。We can then take all of those edges， and we could show which things are connected to each other and color them different colors。

 which identifyentifies the clusters by their colors， and then we can。

Randomly take each cluster and either make it black or white。

 And that gives us a perfect sample from an icing model。So there you are。

 I've just done it in front of your eyes， I have created a perfect sample on this extremely large icing model and it doesn't take very long。

 it's one of the beauties of this method。So。On the screen here。

 it won't look necessarily very good on the video。 So just for the benefit of people watching on the video。

 I'm zooming in now in the top， top left hand corner so you can see a bit more of what this would look like if you were seeing this full resolution。

 The full resolution version is on the website。Okay in summary what have we done today we've talked a lot about random work behavior and how you would love to get rid of it。

 I've shown you some efficient methods for reducing random work behavior。

 I've shown you some methods for getting rid of the sensitivity to critical step size parameters and I've shown you a little bit about exact sampling。

There are some other issues with Montete Carlo methods。 The last lecture， someone said。

 how do you find the normalizing constant， And that's a crucial question， We would love to know Z。

 the normalizing constant for many of these problems。

 and there is an enormous literature on very complicated and cunning methods for trying to evaluate Z using Monte Carlo methods。

 So here's some words from that literature。 thermomodynamic integration is a general concept。

Meths that find normalizing constants， reversal Mark Mark， Marklo， acceptance ratio method。

 umbrella sampling。Tempered transitions， anneed important sampling and linked important sampling。

 all of which were invented by Bradford Neal。The reason it's so difficult to get the normalizing constant is visualized with a cartoon here。

Imagine that you've got a lake and the lake has got a depth and the depth of the lake is called Pestar and imagine you've got some capability to move your boat around on the lake no matter how deep the lake is and you might be trying to draw uniformly distributed plankform samples from the lake。

Let's imagine that you have actually sold that that you've now got the capability to call up a random point in the lake。

 random in the sense of uniformly chosen from the whole volume of the lake and you can go to that point and say。

 okay， give me some plankton from there and tell me how deep the lake is at this。

If you keep on calling on that capability in your complicated lake。

 complete with canyons and so forth， you will be able to go to randomly chosen points in the volume of water and you can find out how deep the lake is at those。

Now just have a think about that capability。 You go to all of those points and you measure how deep the lake is。

Does that tell you how much water is in the lake， Does it tell you the volume of the lake。No。

 because you could be in a lake that's twice as wide and twice as wide in both dimensions and all of those measurements。

Would look just the same if you just imagine stretching the， the map of the lake in both financials。

 You would get just the same depth measurements of all of those places。 So the。

 the ability to perfectly sample from the volume of the lake doesn't give you any information about the volume itself。

 And that's why it's so difficult to get Z because Z is the amount of water in the lake。

 So you have to use other methods that look at sequences of probability distributions。

Trying to tie yourself to a distribution that you understand and where you know the volume。

 and then you go from that by a sequence of steps to the real distribution of interest and in that way with a lot of cu。

 you can deuce set。So that's all I wanted to say about Adv Pu Carlo。 Are there any questions。



![](img/4933f91728b622bab4e4337dd6cb95cf_46.png)

Yeah。Okay， so the question is， is x a one dimensional variable in slice sampling and the answer is。

The problem that you are solving may be many dimensional。

If you want to solve a manydial problem with slice sampling， then what you would do。Is。

You take your current location。And you pick a direction to slice in。 It could be any， any direction。

As long as your method for choosing the direction doesn't depend on the current location。

You pick a direction and then you say， all right， let's define x to be。

The distance along this direction。 And then you operate slice sampling along that line。

 And so you'll move。 And eventually， you'll pick a blue point。Which is your new point hat。

And then you pick another direction at random， maybe。Like this。

 and you slice something along there and you go evaluate evaluate to have shrink down bump and you get your next。

So that's how you would use slice sampling。 It's a lot like gib sampling。

 which goes along the axes This act is。But slice sampling。

 you can use any method to choose the direction。Okay。Yeah。Began。Okay。So the question is。

 can you apply exact sampling to continuous valued parameter space？And the answer is， yes。

 you have to be very cunning， but it is possible to solve。

Some continuous problems using the exact sampling method。

So the critical thing you need is some way of achieving coalescence。

 even though you've got an infinite number of possible values at one parameter。

 you need to have a chain that has the property that sometimes all of those in。

All of the points in this continuum coalesce onto a single particular value。

 and you can design chains that have that property。 And once you've got that coalescence property。

 then it's possible to to do exact sampling using coupling in the past。

 It's not easy there isn't a huge literature just saying， oh， yes。

 we can do Bayesian inference with exact sampling。 That's that's not been achieved。Is it possible。

Anyth else？Okay， thanks very much。

![](img/4933f91728b622bab4e4337dd6cb95cf_48.png)