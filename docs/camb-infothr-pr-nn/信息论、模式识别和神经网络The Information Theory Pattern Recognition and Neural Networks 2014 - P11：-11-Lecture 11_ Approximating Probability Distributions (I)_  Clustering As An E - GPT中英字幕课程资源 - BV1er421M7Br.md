# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P11：-11-Lecture 11_ Approximating Probability Distributions (I)_  Clustering As An E - GPT中英字幕课程资源 - BV1er421M7Br

![](img/29153839c431185041f07526c6ac7fc5_0.png)

Welcome to Le 11。Weve been。Talk about information theory。And then we moved on to inference。

 and we're discussing in a moment， different ways of doing proistic modelling。

I want to remind you where the website for the course is and the website for the free book。

And just to tell you a little bit about where we're going now where。In the next lecture。

 I' going to start talking about Monte Carlo methods。

 And here's a little encyclopedia of interesting Monte Carlo methods that we will go through。Okay。

And that's Saturday going to be chopped into two lectures， lectures 12 and 13。

And as a motivation for being interested in those Monte Carlo methods。

 I'm going to talk to day about。Clustering as an example of an inference problem。

 I'll give other motivations as well。 You don't have to have a lecture clustering to motivate Montetic Carlo methods。

 But if I just gave you it as an abstract concept， it might feel a little dry。

 So we'll talk about clustering today。

![](img/29153839c431185041f07526c6ac7fc5_2.png)

And。Clluuttering can be thought of as an inference problem。

 a lot like the inference problem we studied in the last lecture， where we said。I've got some decays。

 I want to know what the exponential is。 What's the length here。

 So this was an inference problem with one parameter， and we that。A probabilistic approach。

 a Bayesian approach。 We also asked a second question。

 what if we think these decays might come from a mixture of two exponentials。

 And we treated that as an inference problem also， and we did exhaustive enumeration of all the hypotheses that could account for the data。

We made a stack of pancakes with each pancake being a set of hypotheses about what the two exponential lengths were。

 and all the different pancakes had different assignments of the points to the two。Exponentials。

Made a slip last time I didn't mention that for the computer demo I did。

 I actually changed the rules of the game a little bit。

 my computer demo had the window going not from1 to 20， but from 0 to 5 so said didn't have a window。

 so that's just to correct the record。Of course， we can make compute programs that can handle the finite window case as well。



![](img/29153839c431185041f07526c6ac7fc5_4.png)

So now we're about to discuss clustering， and I want to kick off with a little exercise。

 which is an information theory a noisy channel。Question。😡，And it goes like this。

 We've got a channel with an input that you could set to one or two。



![](img/29153839c431185041f07526c6ac7fc5_6.png)

And then what comes out of the channel is a real number。 Y。

 And the probability distribution of y is Gaussian around either mean  one or mean 2。

 depending which input you put in。 So this is a noisy channel。And。

If you want to know about the capacity of such a channel， you can read the book。 But today。

 we're just going to ask a simple question， which is。



![](img/29153839c431185041f07526c6ac7fc5_8.png)

You use this channel。The prior probabilities。Of the two possible values of x are pi 1 and pi 2。

 The channel is used once out pops y。What is the posterior probability。The X was warm。



![](img/29153839c431185041f07526c6ac7fc5_10.png)

So， please。Look at the probability here that wrong。As a function of y。

 And I'd like it in the form of one over one plus E to the minus something。

 Have a chat your neighbour。

![](img/29153839c431185041f07526c6ac7fc5_12.png)

![](img/29153839c431185041f07526c6ac7fc5_13.png)

Okay。So how do we solve inference problems， we write down bases theorem。That's not controversial。

Yeah。The posterior probability of x and y is the probability。

Like an x times the prior probability of x having that value。Dvied by the sun overall。

The two possible values。For x。She。And when you rearrange that into the form of1 over complex plus e to minus a of y。

 where a is my name for。Everything that you get there。A of Y。Is I could write it out Long hand。

 Here's the long hand version。She。Yeah。Okay。So the Piwaan and the Pyan Piiu have got surped up as an additive。

Log of a high ratio， and the。1 over square root of two pi sigma squares have all canceled out。

 so we didnt need those。 we just have a difference of two squares is the interesting wide dependent bit。

 And if you want to be elegant， you can remember how differences of two squares worked。嗯。

A squared minus B squared is a minus speed times Z plus B。And that gets suit。

To an elegant way of writing this。Yeah。That looks come。So， a。

As a function of y is some sort of a linear function like this or a linear function like this。

 depending on the sign of。the lo fire of got that。way I drew M1 and M2 M1 smaller than M2。

 So it actually looks like this。 This is a。Why。And a is a measure of。

How much the hypothesis x equals1 is the winner relative to the alternative that x equals 2。

 So it's a winner to the left。 and it's a loser to the right。 unsurprisingly。

 they're just redrawing these two。U。Yes。The posterior probability that x is1。

 given y looks something like this。Yeah。Something like that。

 that's what you get when you put the straight line through the 1 over1 plus to the minus bar function。

And this is the place where the two probability denities are equal。

And I've offset this a little bit so that 5050 is here。And why is it offset， Well。

 Because pi 1 and pi 2 might not be。Which if I wanted T2， were both。Equal。

 if it were 5050 probability probability， then this sigmy thing would go through half as exactly this。

With。Having pi 1 knot with pi 2 adds an earth。Slis this thing。chlororite。Okay， any questions？

Well this。So if I tell you I'm going to use this channel， then the output of the channel。😡。

Why is a real number whose probability distribution is a mixture。哦。Your gassians。

That's what be of why。Looks like or depending on P1 to pi2， it might look like。来。🤢，Okay。Okay。

What it looked like。I want my two。Becauseal。So why do we care about mixtures of Gaussians？

We might be working on channels and channel might have an output that has a gas distribution。

And you might be interested in understanding that channel。 alternative。

 we could be talking about clustering and one way of thinking about clustering is many clustering algorithms actually correspond to inferences of where the Gaussians are。

 assuming that the data does come from a mixture of Gaussians。

 so that's what we're going to play with now。 I'm going to show you some clustering algorithms。

And will see how they actually correspond to。Inferences to do with mixturees of rats。

So here's some real data just to remind you what we might actually be talking about if we were doing real clustering。

 these are。Frequency， time， lots of speech， said V。Sound spectrum evolving in time。

 just got a beautiful structure with this sort of finegrained comb structure。

 There's a harmonics of the fundamental that the voice is producing。And this is great。

Gloopy movement of power going to in you change which value you're producing。 And when he goes。

spectrumSo you can render speech as a picture and then you want to recognize which picture goes with which that's what babies do when they they learn when they pick up language they're basically listening to these utterances coming out and they start spotting that things look the same as each other and they discover the clusters that we keep on using the same words。

Over and over。So I'm going to show you an algorithm called K means clustering。

The word K stands for the number K， the number of means you've got。 So it's bit of a silly name。

 It's like calling calculus。Differentiation with respect to X， so let's get ourselves。😊，Win there。

 that's a good one。So let me show you the Ca meanss algorithm。



![](img/29153839c431185041f07526c6ac7fc5_15.png)

。Okay。His out workss。The set here is， we assume。We've got some data， and the data is real valued。And。

As an example， maybe we're making an automatic vegetable sorting facility。And。

So I'm now going to use。X1 and x 2 to be some of the real numbers that are coming in。

 It's a change of notation from。A moment ago。 So what we measure is x1 and x2 and maybe a whole bunch of other dimensions。

And these are measurements made by our automated vegetable measuring machinery。

So maybe act 1 is reflectance。At 600 nanoms。And maybe x 2 is。

Electricity of the vegetable and might have mass and various other things。

 and so there'll be carrots and there'll be potatoes。In different clusters。

 we want to automatically discover the clusters and as each vegetable comes along。

 say which cluster we think。It's1。Okay。So here's how RK means our algorithm。Attacks this problem。

We take all the data we've seen so far。Which lives in X1。Cl to space。

And we plop down into this world。Two objects or K objects， sorry。I'm going to draw two。

Shown by these red los。And we call these meanss。I'll call the mean one and mean two and initially。

You just s down anywhere you like。So we have an initialization sta where we plop down two me。

So we initialize K means。And。Okay， it K going from one to K。Rom。That's step one。Step 2 is。We assign。

Each of these data points。よし。And。是。The nearest。没异议。嗯。And when I say assign。

 what I mean by assignment is。As follows， we decline a distance that measures how close you are。

And the distance here。Is going to be half。嗯。M K minus。Square。

 so I'm going to use a quadratic distance。And that's the distance。The tree。Mk and。XAnd if you like。

 would be a long， long name poverty again。F。So we assign each point to the thing that it's nearest true。

And that means let drop。Ofpend。Through that， whoops wasn intended to exactly hit a eight point。嗯。

Then。All of these points are closest to Mrer two， and all of these are closest to me number one。

As it happens。Another way of saying what's happened when we've assigned them is we could introduce things called responsibilities。

And we can define how responsible the case me is for the nth point。By saying， well。

 if that end point is closest to me， then I'm responsible for it。

 and I get a one for the responsibility， and otherwise I get zero responsibility。😡。

So I'm not saying anything new here， I'm just giving you a new piece of notation， the responsibility。

It's one if Mk is the gl。😡，没有。去。Exan。0。Otherwise。Or to put it yet another way。Responsibility is one。

If。🤢，Okay。Minimizes。WithRespect to Kate。对。So。Yes。Okay。So it'll not too confusing。All right。

 so that's the second step。 we assign everyone。Let's go ahead and do this on the screen with an example。

 so I'll grab some data。 here's some points shown in green。And let's press a， have slight struggle。

And now we slap in some means， How any do we want。 I'll slap in2。So it plop them in at random。

 and one of them is coloured orange， and one of them is coloured green in circles。

 And then we assign the points we say， who are you closest to。And I've had on the assignment chair。

 Step， and I've shown that by colour。 So I've coloured every date to like orange of its closest to Mr。

 Orange and green his closest sister， Mr。 Green。Step 3。We update the means。

And the update step works like this， you move the mean number one to the mean of the data points it's responsible for。

😡，So。M1 or M K in general， get set to the sum of all of the points that it's responsible for。

Divided by the number of points that is responsible for。

 And you can write that as the sum of responsibility and K。

Divided by the sum of all the responsibilities。Cain was summing over。All the N。Da once。Happy。

 so I'm just。Telling you the mean gets set to the mean of the things it's responsible for a natural way of writing at houseer。

方咩啦。Okay。So lights down again。😡，And let's do it。 So we update。

The mean in orange and the mean in green to be the mean of those two have now done that for you。

 And then we repeat。 So we iterate that algorithm。 We go back to。2， said。Go to tune and repeat。

Until nothing happens any more。 So what we do again， we assign。Is the assignment step。Now we。

Update the means。Okay。And now we repeat， we assigns what。And now we update。And now we assign。

Re updates。When assign， when we update， when we assign， when we update。

 and now nothing is happening any more because the assignment and updates how stable we've reached a stable state where the assignments don't change。

 and the update doesn't change anything。Okay， we do it again。Two means， toss a minute at random。

 assign， update， assign， update， assign， update， assign， update。Okay。Busters， assign， update， assign。

 update， assign， update。So perhaps Ka means clusterstering and you can choose four means if you want and toss in four means at random in sign。

 and update a sign， update a sign， update a sign， update。So now we found four clusters in the data。

 isnn't it wonderful？Oh， I'm not sure if it is。 You can do whatever you want and something happens。

 Let's assign4。 let's set K to 4 again。Clss in four means， assign update， assign sign。Update。

 all right， assign， update， assign， update。 Oh， it's time the same for alleged clusters。

Let's try four again。Pluss in the means。Iitialize。Assign update， assign， update， assign update。は5。

And there is stabilized。Good again。Notice that gray orange boundary over there， dodgy Han。

Something you may be starting to feel already is I'm not sure I like camembians。

 but it's interesting， isn't it？😡，Counman， assign。Update， assigned， update the。Oh， look。

 it's come up with a different way of resolving those two guys that used to be at the gray red border。

 which is now the gray blue border。Again， full means。Oh that's yet another answer。

Lots of messages coming through here。 You can run Ks。 It'll find some clusters for you。

 It will give you a stable end state， but the end state depends on the random initialization。

And maybe some end states happen more often than others。

 but that doesn't necessarily prove that they're。For anyway。Okay。So。That K means。

 let's switch to a different data set and see if we can make ourselves。Like K meanss。

 even less than we do at the moment， Kmes is already quietly quite a widely used algorithm incident。



![](img/29153839c431185041f07526c6ac7fc5_17.png)

It's popular。So let's pick some different data set。 So let's look at this guy。



![](img/29153839c431185041f07526c6ac7fc5_19.png)

So here's some data I made， which if you ask a human， they might say， yes， I can see two clusters。

So you say，haha， we have a clustering algorithm， So let's run K means and say that there are two means。

 put them in at random， assign， update， assign， update， assign update。嗯。What do we think of that？

Not quite what we had in mind， right？😡，Lets let's try again two means whatop， flip， flip， flip， flip。

 aha， we found another answer， but it is still。The green guy has gone and grabbed a few guys。

 which we really wanted to be in the carrot cluster。

So we're exploring some defects of this algorithm， it isn't really doing what the human would have done given this data set。

 try one more time， two clusters， b flip， b flip， flip， b flip， okay。

 now this time grabbed one from the top three from the bottom。😡，But that into Greenland。Okay。

 that's not quite ideal， is it？U。We can always try using more means， you could say， oh。

 let's have seven instead and throw in seven at random and go assign， update， assign， update， assign。

 update， assign， update。And they say， oh， yes， wonderful。Oh， is it wonderful， I don't know。

 Maybe there were only two clusters there。But it's come out with 7， because we told it to。

And it's still gonna to put one of them into the yellow cluster in the bottom there。

 which probably we didn't really want to have in yellow。 Okay， so Kaine clearly has some defects。

 but it's got a sort of elegant beauty and simplicity to it。

 Just you do stuff and it ends up finding clusters。 And that that has to be useful。

 So what shall we look at next。 Let's switch data set one more time。😊。



![](img/29153839c431185041f07526c6ac7fc5_21.png)

And I' show you。This one。

![](img/29153839c431185041f07526c6ac7fc5_23.png)

呃。Okay， so ask a human how many clusters are there in this data set。Anyone。2。In advance on two。

 and I'll think one。Okay， so off we go， let's try and find two clusters with K means， Okay。

 so all we've got some lucky there and are you assigned。Alex promisinging， update， assign， update。

 assign sign， update， assign sign， update， the sign， update， the sign。Beautiful。

 we found the two clusters。Okay， can do it again to put the a phone and it finds another incorrect way。

😊，And another。我间。So close， so it's not stable。Okay， so it's not giving us the answer we want。

 but it's not a million miles from what we want。 It's got the spirit of a useful clustering algorithm。

 How can we improve it？😡，What if you normalize coordinates， Okay。

 so what does normal coordinates mean？Take the data and stretch it before you give it to the stupid algorithm。

😡，All right， so。You imagine doing that？But both both of these axes actually roughly go from  zero to 10。

 so it's already roughly normal。

![](img/29153839c431185041f07526c6ac7fc5_25.png)

instead of complying with you and giving you your normalized data， I'll just say， well。

 I'll switch the data hat。ItsThe one that looks like。That， okay。

Well that's zero in 10 and that's zero and 10。Can Imobilize。And it's still going to break。

 maybe not quite as badly as this one broke。Let's not hack around with the data。

 Let's have a different attitude instead of saying hack。😡，Tweet， tweak， modify the algorithm。

 Let's give it an interpretation。Because actually， it's doing a perfect job of a well defined probabilistic activity。

 Naly， if you think of this death。😊，This distance， as being。

The thing that appears in the each of the minus half。Yeah。In Augustian。

It's already got factor path in it， so it's this thing here。

What this algorithm is actually doing is it corresponds to。Assuming that the data comes from。

A mixture of K gassians。They all have。The same variance as each other。So his interpretation。

 we're assuming that there cave asians。Bull with the same。Varariance。

 and that's the same in all directions。So it's a spherical gas unit， if you like。Yeah。

And then the final assumption is that they all have the same prior probability pi 1 equals pi2。Hi。

And then the algorithm that we're running here is a。Greedy algorithm that is what the definition。

 maybe I'll。Dfinine precisely what it's doing in in due course。

 But it's coming up with a hypothesis about the assignment of。The points to those different clusters。

And it's then doing the obvious thing with the means， namely setting them to the data means。

 which is finding us local。Maximum a posteror maximum a posteri ori probability interpretation of the data。

 So canine means is roughly。A。M A P， maximum a postusterary。Algorithm。That adjusts。

The assignment variables， which we could call。KN。So the hypothesistheses of which point？

Which cluster the end point came from。And adjust all the Ms。So as to maximize。They was from。Of the。

Assignments and the means。So that's an interpretation of it。😡，And given that interpretation。

We can now have some fun because we can say， well maybe I don't want to make those assumptions。

 maybe I can change them。 I get， I can get myself a new algorithm that will be a better algorithm because it corresponds to a different set of assumptions that I actually want to make。

😊，And maybe we can also not only change these assumptions here， 1，2，3。

But maybe we can change this algorithm and say， well。

 I don't actually want to know the most probable hypothesis given the data。

 maybe I'm interested in something a bit more representative of what's probable， what's credible。😡，嗯。

Ca even if。私し？The data really do come from two identical Gasians。

With equal cry probabilities and you。Try putting the means in the right places， Sa ha ha。

I will put me in one hair and mean two hair， which is where they really belong。

 If then put your divider in。And you allocate all of these guys。

ToClas 2 and all of these to class one。Now what happens when you run the update step？

What's the mean of this shaded blob？In the right place is it， I mean， to。 it gets nice to the right。

 right， because we've lost this tail here and we've gained an extra tail here of double。

So it'll actually bump over a little bit to the right。

So even in the case where all these assumptions are true， the MA algorithm。

Ends up because it's very firm about the allocation。 It ends up putting the means in the wrong place。

So。We don't quite like this because MA isn't like what we want to do。😡。

So let's fix all of these things， let's modify the algorithm。😡，And the next step we're going to take。

Is cold。うそ。K means algorithm， and we're going to show version one of the algorithm。

And it starts in the same way by initializing the K means at random。And。We set。Cace。Pmeter。

Beta to an arbitrary value。 Beta is now going to come in when we change our assignment rule。

The assignment rule， instead of being hard， is going to be soft。😡，So he signed。Like。This。

We're going to say R and K， the responsibility is。So in contrast to setting K to the minimum。

The K that minimizes the distance。 we're going to do a soft min。

 So we're going to do this E to the minus beta。Distance from M K。这X。

Divided by the sum overtake pride。Of each to minus eachta。Distance from。Hey cryingry。Yes。And。

So what are we doing， We're rattling through。All the possible ks and saying， okay。

 how close do you feel by this E the minus B to B measure。And。

If you feel like you're the closest all the means， then you'll end up with the biggest responsibility。

 but you won't get one anymore。 You'll get 99% or 83% or something。 So it's like this。

Responsibility here， But you would obtain ones and zeros only if you set beta to infinity and beta make it very large。

 Then you reproduce the old hard kine algorithm。Okay， so that's our new definition of B。

Responsibility。And instead of minimizing。All we can say we're doing is。Soft men。

And you might recognize that this looks a lot like what we did in the question at the beginning of this lecture。

So it's not the yaish thing to do， is it？I made the mistake there。Wiping out the update rule。

 the update rule mean K。Its just the same。So there's no change。the update rule。

 you just weight each point by how responsible you feel for it。

 so you're softly responsible for all the points。😡，And。You say。

 what's the mean of all the part I'm responsible for， but you wait them by responsibility。😡，Okay。No。

If we do that。We have to pick a value of beta。 So we've sort of made a bit of progress。

 but we've got a new parameter beta end。嗯。Les。Just try setting it to arbitrary values。



![](img/29153839c431185041f07526c6ac7fc5_27.png)

So to kick off with， let's take these old data points that we had before。

And how many meetings would you like， Shall we tossedss in。Or they full？Okay。

 we pick a value of beta， and I'm representing beta by the radius of a circle because one thing you would have missed。

 I'm sure is that。With thisG here。Being off of something might something square。If you take D。

 and imagine。Putting a divided by sickness square。That it looks a lot like。

Whats the exponential of a Gaussian。 So this beta。You can think of as being won over。

A standard deviation。 Thanks， so that's its meaning in this probabilistic interpretation that we've been working on。

 So I'm showing now four means that have slap down at random。

 And I'm showing you how big beer is by showing you circles centreed on each of the meats。

And now we run the soft algorithm。 It goes a sign， update， assign， update， So sign。

And I'm showing you the color if the assignment is very strongly in favor of one me。

 and if it shows a pale blue， that means that the point is really sure it's not clear who it's been assigned to I've just got a threshold there for the color to kick in and you have to be I don't know。

 70% responsible or something like that。Great， updates。Assign。Update， assign。Update， assign， update。

Sign sign。It's it could be a bit like watching paint dry soft algorithm sign update sign update sign。

Shey， what's happened。We put in four means， but now is decided only once two。

People could raise their hand and say， oh， hallelujah。

 we've got a null algorithm that automatically discovers how many clusters there are。

 but I hope you're a bit more skeptical than that。It's just an algorithm。

 it's doing something and yes， we gave it four means and it's only chosen too for this particular value of beta we could try again phone。

😡，是。Okay， so it's done the same again for that value of Peterta。

 but it didn't have to do that because we didn't have to give it that value of Peterta。



![](img/29153839c431185041f07526c6ac7fc5_29.png)

嗯。嗯。I put in 9 clusters last。Okay， what I was meaning to do was to change different values of datata。

嗯。So go back to the same hour。

![](img/29153839c431185041f07526c6ac7fc5_31.png)

我去发少下。

![](img/29153839c431185041f07526c6ac7fc5_33.png)

Okay。So， real。Pluss in four means。But now what I'm going to do is run the algorithm for a sequence of different values of beta。

 So I'll start with big values of beta。 And then when it settled down a bit。

 I'll just change beta with smaller values， so。How。A means unstarting， Big meter。

I've said it the wrong way out。I'm starting with big standard deviation。 so it's all beta， sorry。

Starting with big standard deviation。 and then gradually reducing the standard deviation， every。

 I don't know， how many iterations。 these few iterations， I'll just。

Change the sound deviation version。 So it's smaller。

 give things a nudge in and keep on running the algorithm。

 And I'm not going to press anymore more for assigning up like。 It's just going to。Run itself。

 I think。系。

![](img/29153839c431185041f07526c6ac7fc5_35.png)

お山。Okay， try again。

![](img/29153839c431185041f07526c6ac7fc5_37.png)

Yes。6。对。是 for。不是。No中了。被后回复。可了。Off we go， four means and。All right。

 so that was a very large standard deviation， and they're all converging on one place。

 So it's saying I at that standard deviation， if you like， I only want one cluster。Right。Alffra。

So now we reduce the standard deviation a little bit。And we assign it update。

 they can assign it update move。Co of them have popped apart now。

 You keep on reducing the s deviationvation。 Now， it's another pair of popped apart。

 and now it settled down with four clusters in their reasonably state。

And we'll go smaller and smaller standard of deviation snap。And it doesn't change。

Should do that again？Okay， so there we have soft play meanss。And it's an algorithm。

And it not an interpretation。The interpretation is。

 we're assuming that there's a mixture of scoassians that all have the same sigma。

 but now we're controlling that。

![](img/29153839c431185041f07526c6ac7fc5_39.png)

The prime probabilities are all the same， still。Because we haven't introduced any parameters corresponding to different weights of gasussians。

And it's not an MEP algorithm anymore because we're doing soft assignments。

 so we fixed this problem here if we gave it a perfect mixture of two Gasians。

 you could check which you want。😡，It will assign them and if you get sigma right。

 if you have the correct value of sigma。😡，Then it will assign them in just the right soft way using that sigmoid function that we found at the beginning of the lecture。

 and then when you do the mean update， the means will actually end up in the right place as assuming that you have the right value of sigma。

 so that's nice， it at least works on this type problem。

And what we can do as we vary sigma with this Soka means version1 is you can run through a sequence of hypotheses of what the standard deviationvation sigma is and see then what the best setting of the means is。

 So now it's not an MA algorithm anymore maximizing the probability with respect to all of these things。

 rather it' it's actually a maximum marginal likelihood algorithm that's just optimizing where the means go。

Assuming that you've got the right value of Sigma。So we're making a bit of progress。

 We've slightly modified the assumptions。 And， of course， it's still not going to work well on。

Problems of。The type we had here。 So if you've got。The lozenges。



![](img/29153839c431185041f07526c6ac7fc5_41.png)

And you say， I'm going to use soft gay means。I'm going to toss in two means well。

You can see what's happening is doing a soft assignment and it's taking forever。

 it's like watching paint dry and gradually it comes up with a stupid answer because we haven't changed the assumption which we wanted to change。

Namely， we want to believe that。The Gasians might have different widths in the two directions。

 Then we'll be able to do Mr。 Lozenge。So， what we can do is。Progress to soft plain means。主是证。

So lights on again。

![](img/29153839c431185041f07526c6ac7fc5_43.png)

Soft k means algorithm version 2。Doesn't just update the means。



![](img/29153839c431185041f07526c6ac7fc5_45.png)

It also updates。Varances。And we're going to redefine what the distance is so that we've got a sensible。

Dedepend。嗯。So we've got an axis dependence in there。 So I'm going to have a sigma for each dimension。

 So instead of having a stiffness the， we'll have。Every cluster。Sigma。Okay。

Will have for each of these dimensions， which I haven't even given a name to， I。

I goes from one to the number of dimensions we're living in。After I。

We're going to have sigma variables for each of those dimensions。

 and they're going to be different for every single cluster。

 So now we're allowing ourselves in terms of our interpretation to have。

Gussians that might look like。This， this。Al right， so we toss in Sigmas and then we need an update rule that says what we want to do with the Sigmas。

And。So the update rule for Socom means version two is going to say， well。

 let's look at the variance of all the applying design responsible。说。Yes。Using my mean。

The value I have at the moment。And we'll do that just on the I dimension。And divide by。

Some of it are replied time of for。That's a sensible looking variance update rule， isn't it。

 You might say， oh， I want a minus1 down here to take account distributed freedom or something。

 but I don't think I've got that in my algorithm。Okay， so there's a variance update rule。

And we just run the same algorithm with the assignment now being the。

Appropriate modification of this Bta D thing so that it's actually got all the different variances in it。

 So it's due to the。Minus。啊。Some overall dimensions distance squared over the corresponding between parents。

Yes。So that stuff came means version two， and let's play with it。

So what we're going to say is we want access aligned Gaussians。And incidentally。

 I'm going to have the pies changing as well， so。

![](img/29153839c431185041f07526c6ac7fc5_47.png)

嗯。Willll initialize the pi used to some sort of value。 We'll have a bunch of things called pi K。

 which you can think of as the weights of the Gasians， how heavy they are。



![](img/29153839c431185041f07526c6ac7fc5_49.png)

The assignment rule is going to be the same， except will tossin IKs in here。Now， we've got。

A pi dependent algorithm and the update rule for the Pis will be that you look at how many points have been assigned to you。

So how many am I responsible for？And。You update your weight to say， well。

 I'm responsible for that fraction， then thank you very much。Right。So let's do that。

 Let's do it first with。The lozenges data。

![](img/29153839c431185041f07526c6ac7fc5_51.png)

Yop。Good， again， two means。She means you。It means。You means。不是。

So now it's not looking quite so stupid， is it？Okay， let's try another day say oh。

 let's try four means just so that we don't feel too complacent。

 So you give it four means and it goes and finds for plus now。It was 7。And。Okay。

 I think it went a bit singular， maybe what are the means exactly on a date Michael or something that's good。

So still bad things can happen。Yeahep。So garbage in garbage out， you tell it you want four means。

 it'll find you a hypothesis of four means， but everything that we're doing now does have a firm probabilistic interpretation。

 Something we're going to discuss in two lectures times is variational methods and this algorithm here is actually a variational method for fitting it's sort of called an EM algorithm for fitting this hypothesis that there are。

K axiss aligned Gasians， it's a very principled algorithm for fitting that hypothesis to the data。So。

 let's change dataset set。

![](img/29153839c431185041f07526c6ac7fc5_53.png)

It's changed to little and large。

![](img/29153839c431185041f07526c6ac7fc5_55.png)

嗯。有没有。How many means would you like， Should we start with two。Oops， I do a like thing。Okay。

 two means。Thatk you， isn't it？Oh。Okay。So to get off onto top Mr。 Orange's cluster。

 it has to first get very stretched out， it imagines to come up with this completely wrong hypothesis it's a very wide k and then it can go and guzzled them up and become narrow。

😊，You can imagine having data sets where there is a good hypothesis。

 but the algorithm doesn't actually find it because it's basically doing an optimization and it might be difficult to find the good minimum。

It may have got stuck there or maybe it was on a saddle and it just took so long and like I gave well。

And you can give it5 means and。And it comes up with don I off。ItThank you for。收。

It's still a sort of arbitrary algorithm because you can pick any value of K you like。

 but at least all of the pis and sigmas and means are now being automatically handled。And。

I did mention a moment ago when the whole screen， something went like blue。

 a hypothesis for what happened in that case was that one of the data points had been completely。

Taken over by a single meme。And then what happens well。If we're using this update， rule here。

AndIf you feel very responsible for click point and no one else is responsible。

 then you'll keep on updating the variance and saying， oh， look。

 what a small variance I can have for this one point but I'm responsible for。

 And your mean will be very close to your later point can get closer and closer and your variance becomes absolutely enormous。

 And so no one else is ever going to be responsible for this point anymore because you predict it so well。

 And so your variance blows out。 And then that's why the screen goes blue because I don't have anything to prevent the variance is from going to0。

 If the algorithm that now。 So this isn't。The end of the story of bstering。

 It can do kind of odd things。 I'll puts in 7 beans again。See what happens。

The green thing is wandering off this screen， presumably because there's a dated point outside it。

The wind。后来呀。So given the defect I just described that it's possible for one mean curve sit on one point and have its variant go to zero and the whole thing lows up with this infinitely fantastic explanation throughout one data point。

 it's surprisingly a robust algorithm that that sort of defect happens very rarely and there's an enthusiastic community of people out there using So K means version2 for all sorts of data modeling problems。

 there's a big literature， an algorithm called Autoclass was written about 20 years which is So K means version2 and it was used on all sorts of problems and they had a fantastic time discovering automatically clusters in all sorts of data sets including astronomical data sets and they made some genuine new discoveries of phenomena that hadn't been noticed before。

Okay， so。That's of came means， and。So your question is。

 in what sense is this an optimization algorithm， I that the question， Okay。

 the answer is when we've done the variational methods lecture。😡。



![](img/29153839c431185041f07526c6ac7fc5_57.png)

Then we'll be able to answer the question of what's actually being optimized here。

 So I'll leave it as a vague thing。 that does。 It's not at all obvious。

 I just wrote down an algorithm， does sign up there to sign up there sign up。

 Why should it converge at all？ You could imagine such an algorithm going round around in circles and never settling down on that。

It does actually optimize and objective function， which is called a variation of free energy。

So it has an objective function， and that objective function has got an interpretation which will become clear in。

In two lectures time。Are there any other questions about？Austlia this much。Yeah。Okay。

 so the question is， what if the data is on a ring or some other type of data that's not well described by a mix Gaussians？

😡，So data on a ring。Might look like that。 And if you say please clutter that for me， well。

 that's what you've asked to have done。 And if you use SoK means。

 the interpretation of what you're doing is you're using K Gasians that are no longer spherical。

 their axis aligned and they don't have the same sigmas but they are access aligned Gasians and maybe the weights aren't equal to each other anymore。

 but that's the interpretation of what you're doing and it's not surprising if you give data that doesn't look like mix Gasians that well something will happen and you might not be very satisfied with the answer。

 So you could play with this algorithm。 It's very easy to code up or you can download by version of this。

From the net。 And what will happen with a data set like this is you might get。

If you gave it seven clusters， it might plotp land seven garussians in some way like that。

So you will get an answer， which is。😡，In some sense。

 the best way of explaining this data or one of the best ways of explaining this data。

 assuming that it is a mixture of 7 gaussians or however many you pick。

The algorithm won't tell you that was a stupid hypothesis。

 I could have come up with a better model because that's artificial intelligence。

 and so that's still an open problem to have。Universal algorithm will just look at data and come up with an interesting explanation of it。

And it's good to understand So clusteruttering as a first step to head off towards the。

A solution you'd really like， which is an algorithm that can discover low dimensional explanations for a data。

That's something we could get to in this course， maybe into lecture 20 or so。

 to start talking about algorithms for discovering low dimensional underlying explanations for high dimensional data。

Yeah。Great， so the question is， could you change the metric？

So here we've been using each of the minus half distancecing thing， and that motivated the algorithm。

 if you like， that assumption that it Se Gasian motivated the metric and gave us this algorithm and you could pick any distribution you like。

So instead of each the minus glass squared， you could have each of the minus and invent your own shape。

And then all you're going to need， assuming this is a parameterized thing with something like a mu lurking around it and maybe something like a sigma lurking in it。

You can use that as your assignment step， so you can just plug it in here。😡。

And then you' going to need to get for yourself。A new update rule。

 which tells you what to do with your parameters of that new model。

 Because probably if you've changed this from being something squared to something else。

Then this update rule won't be the right update rule anymore。 so the do parameters。So yes， you can。

 and what people actually do。😡，I'm not that up to date with the clustering community to hear what they're doing。

 but I can imagine that people might say， oh， yes， I like to use a tea distribution instead of Gaussians because I believe in heavy tailed clusters。

So you use a T， and then you need the right update rule for updating the parameters of a T distribution。

😡，The T itself is a mixture of Gaussians all having the same mean but different variances。

 So that's something that would be fairly easy to write down。

 And if you read the variational interpretation of this whole thing。

 that will give you a framework in which you can take any hypothesis you want and then figure out an algorithm that will optimize a variational free energy in just the same way that this does as well。

Okay。In the next lecture， we'll discuss Montetic Carlo methods using this and some other problems as motivations for why we want Monte Carlo methods。

Thanks。

![](img/29153839c431185041f07526c6ac7fc5_59.png)