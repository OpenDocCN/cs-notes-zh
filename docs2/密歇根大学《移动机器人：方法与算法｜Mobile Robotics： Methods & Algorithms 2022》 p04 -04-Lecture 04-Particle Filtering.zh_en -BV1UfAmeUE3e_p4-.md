# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p04 -04-Lecture 04-Particle Filtering.zh_en -BV1UfAmeUE3e_p4-

In this lecture we're going to talk about particleig filtering。

 particleig filtering is the second idea underlineization or uncertainty propagation methods that we explored。



![](img/9fd459256195d8893a552a6c061a55b7_1.png)

![](img/9fd459256195d8893a552a6c061a55b7_2.png)

In particular， were talking about a class of nonlinear processes and。

Meeauring models together they form and a linear systems。These systems are ubiquitous。

 Theyre everywhere。 It's not basically。Studied in isolation。

 This is typically the real problem we deal with。 They are。 They are not linear。

 They are complicated systems。You could to help your imagination。 you can imagine it。

Autonomous flying taxi。 It's a very complicated system。Now。

 maybe you're modeling just the motion of this vehicle， and then that forms this nonlinear system。

But you could， could have multiple such non nonlinear systems to model different aspects of this w。

 right。Or now， autonomous racing cars are becoming popular。嗯。So there are many examples of them。

 So in general， we discussed about multiplicative noise。

Additive noise because it was important in the context of column and filtering。It would make。

Calculation easier if the noise was additive。But here， we typically。

 we talk about a general class of nonlinear systems。With noise。The most general case。

 which is multiple cadium noise。

![](img/9fd459256195d8893a552a6c061a55b7_4.png)

![](img/9fd459256195d8893a552a6c061a55b7_5.png)

So again， our motivation here， what was our motivation。We're going to talk about the technicalities。

 and what。To do basically for solving certain problems。

 But our motivation was that given a system and certain models。

We wanted to solve some state estimation tasks， right， These tasks could be。Tracking， localization。

Some sort of perception tasks， maybe it's coupled with planning and navigation。 So altogether。

 that was our motivation。 So this is the third method we're going to learn。

To answer this central question that if I have a probability distribution。

 given that there is no perfect actuator in sensors。In reality。

 and I have to deal with distributions and uncertainties。

 If I have a belief over my quantity of interest。And I need to send this belief。Recursively。

 every time through that nonlinear model。How can I do that。In general， there is no exact formula。

 unlike the linear case。So we came up with two ideas we talked about。

Linearization analytical methods using Tayloror expansion that LED to the extended column filter。

 There was another idea。 It was derivative free。 It was based on deterministic sampling。

 and that LED to the uncented column filter。So we learned already two methods for linear state estimation。

Today， we are going to talk about a third idea。This third one。Is based on。

The idea of random sampling， if we can generate random numbers in a computer。

And we can create many hypotheses to simulate。The evolution or many hypothesis that can probably distribution basically evolve to over time。

 Then maybe we can track multiple hypothesises， and then。

Find out which one is more likely as we roll out and obtain more observations。

 That's basically the idea。 Okay， so the concept is very intuitive and simple。

 We we use a computer to simulate。Track the evolution of the posterior。

And use the measurements meant to weight them and then see which one will be likely。

 It won't be one of them， Usually multiple of them。

But at least we can track them with certain weights。 That's basically the idea。

And the math is really just to back and make sure。Everything will be in place。 They won't fall apart。

 It will converge to。Something correct， right？So the general idea that is very old from 50s and 60s。

When we had computers， then we could draw random samples。Samples are examples， right。

 These are different examples。That in this context， we call them particles。Right。

So each particle is an example or a hypothesis。 So Monte Carlo Method is a bigger class of。Basically。

 techniques， they're all based on random sampling and simulationimage。

I shared some background with you。 It's good to discuss it outside of lecture， but well think。

It will eat the lecture time， and we won't be able to talk about the robotics aspects of it as much as we want。

 but that's Monte Carlo integration。 I have an integral。 I want to approximate it。

 We can use Monte Carlo， which is based on random sampling。It's fun to implement。

 These algorithms are typically easier to implement。Then。

The previous classes of problems that were somewhat less digestible because you have algebra。

You need to be careful about the derivations and not making any mistakes。So in general， they are。

Easier to implement。Another nice properties of。This classical problem is that it can deal with。

 We'll see nonlinear posterior multimodal posteriors。

 So a more complicated common filter was tracking。A Gauss in distribution for us。

We were very limited in the type of posterior that we're trying to estimate， okay。

So the Monte Carlo methods are basically simulation based method。 However。

 we're going to talk about a more special case of Monte Carlo methods。

 namely sequential Monte Carlo methods， SM C。😊，Because。The data that we have arrived sequentially。

In time， right， And we want to process it reccursively。 Were still in that frame workco base filter。

Although this method can be more general， and I'll point out when we reduce it to filtering。

In today's lecture。So this is the context we're covering your third idea。

Which is not from the same family of methods。 It's no longer basically an algebraic filter。

 like a common filter。So observations arrive sequentially。 That's important for us。

That's what the sequential aspects of this method will enable us to。

Implemented in real time on a robot。Otherwise， it will be offline。

 You have data and you maybe run your simulation to infer some。

Interesting value or quantity that you want that won't correspond to real time。Basically， algorithms。

We can deal with non Gaussian， high dimensionality and non nonlinearity， okay。Now， when you。

See these features in a problem。Then you might want to start thinking about this method。

Because as soon as you read N Gaussian， well， you might want to look into the problem and see how。

Nang Gaussian， a little sced。 Maybe it's okay， right。

If you're lucky enough to have access to some data and see the behavior of the system。

If it's really multimodal， is， it's。At one point， in one place in the data space。

 Another point is just completely in a different space。 is it just jumping behavior。

Then maybe a common filter might not be the best choice for tracking because it will not be able to deal with it。

 This change of mode in the behavior。Can it happen in robotics？ Yes， that's a very common problem。

 So you。It's called kidnapped robot problem is。We used to have this。

 I think we still have this robot cop challenge， Robs would play。So I could in teams， right。

 or it just a robot exploring。And then you come and lift the robot and put it somewhere else。

First for any reason， the robots lost or maybe you just want to reinitialize it。

But the poor robot has no idea you did that。Its trying to track。The robot thinks it's here。

 You move the robot to the the other side of the room。It might never happen。

 or it might take a very long time that the robot can recover from a sequence of observation。

 What just happened。That's the kidnap robot problem。

 So part of your filters because they can track multiple。Our propes。

It's more likely the party affiliate they can recognize that， and basically。

Shift the mass of the estimate to not a more likely hypothesis。

 which might be the other side of the room， okay。So basically。

When analytical solution is not possible and you're dealing with a highly non nonlinear multimodal systems。

 you might want to think about。Partdial filtering。There's a price to pay， obviously。

It cannot be just gain， but we'll talk about it later。Now， to avoid a misconception。

 although it's called particle filtering。Now， you know filter is a technical term we use。

It can be used both for smoothing and filtering。I had a question about the slide。啊。

So the second point that's made there。The posteror distribution being updated as data。

So this is where。So you have a above where your sampling rate from your measurements aren't as frequent as B。

他知道当时。I would frequently can be probably your dynamic。

 so you're not getting data as frequently as you're moving。How does is this work？

You have like gaps in your。Let me see if I understand the question you're asking if I。

 because we want to run。This filter， as data becomes available， reccursively。

I think your question is that what if data that I'm receiving is not that frequent？What will happen？

My answer is that that's not basically a problem of this method because it can happen to all。

 all the other methods， too。If you do not have data or observations。You cannot basically， correct。

Your belief。So you have two options。 You either need to resort to assumptions， right。

Model is some sort of assumptions because it's imperfect。 You're assuming that's the behavior， right。

 It might be a good model。 It can be a good assumption， right。That music works well in practice。

Or you need observations， and ideally， you need both， which we use both of them in base filtering。

 right， Now， if you don't have observations as you， you're continuing with assumptions。

 models to propagate for a long time， you might expect at some point， sooner or later。

 this will the filter will become degenerate。But the amount of information that is giving you is so low that's not useful anymore。

 okay。So， that。We assume we have a sequence of data observations。 And that's usually in practice。

 not a problem， because。嗯。Imagine a robot or autonomous systems。 You have a variety of sensors。

 If the sensors are properly receptive， like IMU encoders， right。

 some signals that are not perceptual measurements from the environment。

You always have a continuous stream of them at a very high frequency， can be kilohertz。Right。

 unless the sensor fails。You will have the signal。If it's perceptual data， for example， cameras。

 Liar， radar。They come at a lower frequency， but they have higher bandwidth。So the spatial sensors。

A point cloud Liar can have 100000 points， or a streic camera can give you 300000 points。

And they come at maybe 10 Hz，30 Hz。Maybe 60 Hz。Will will never be kilohers at this point， at least。

So it's often the case that we have more data to process。Then we can't。 So we might drop frames。

 you might it down sampling。And all sort of hacks， too。

Get some sort of observation that you can actually process with an available time budget， right。

So your concern is valid and it's very important conceptually。 But in practice。

 the challenge is at this point， the challenge is often the opposite。You have more data to deal with。

Okay。Which motivated that's a good question， because that motivated a lot of people to work on dedicated sensors with internal chips。

 for example， too。Maybe a camera should have a processor to do certain image processing like edge detection。

 maybe segmentation。Ca if you want to do all of them on the perception computer of the robot。

 we just can't handle。The amount of computations that it takes， right。

So future sensors might become smarter and smarter， smart sensors。

Or you sell a robot that maybe comes with this localization built in， right。

So it can be used for both。Filtering and smoothing。 is anybody here。Remembering。

What was the difference。The difference between filtering and smoothing。That there any use。

Data after time T to infer time T data and smoothing is used sequentially data after time T to infer。

Yes， so the filtering uses the data to current time。

Whether we make certain assumptions like Marco or not。

 it uses data opt to now to estimate this state at the current time step。Not the history。

 not the past， not the future， right。The smoothing approach。

It tries to estimate the entire trajectory。 Use all the data to estimate the entire history。

Up to now。In a sense， we can use data in the future to correct the past estimates， right？

It can be done offline， can be batch。 You can do it。

 The question came up on P of can we do it in a sliding window。 Yes， that's perfectly fine。

 You can have a fixed like a smoother。 This is a sliding window moving in time。

Not the entire history， but maybe。10 seconds。Instead of just the current step， right？

So that's the difference。 And if we had prediction， right， prediction was about making。

Infer or predicting value in the future。Based on all you know right now。Okay， some。Background。

 we will need this deelta function today。So you might remember it from。

One of your physics course courses or some courses in math that。

We talked about chronicrona Delta as a discrete version of。Delta function。

 the D deelta function is a continuous version。 It has a very strange definition that。

Around a certain point is infinity。And then0， everywhere else。And by definition。

 when you in in integrate this function， it gives you one， right。Now， of course。

 it doesn't make sense to integrate infinity， but that's just a definition of the deelta function。

 Okay， so you can think about it as。Basically。If it's centered around a， it doesn't have to be 0。

So all the infinite math just centered at one point， right。Basically， that's what it's saying。Now。

 if you think about it as。A probability measure。 then you can think about it as a mass function that you're just centering all the probability mass at one location。

Okay。That that concept is important for us for the approximation that we will make。Soon。Now。

 one interesting property of Delta function is that it breaks the integral。That means， if you。

Multiply by function and then the integral because it's 0 everywhere else， right。

It ends up summation。 It ends up being just the evaluation of your function at that particular point。

 a。It's also called evaluation functional in analysis。 So it can evaluate your function at a point。

Or you could think about this as some sort of expectation， right， If your density is Delta。

 you're taking expectation with respect to Delta， it just evaluate your。

Variable function or whatever it is， okay。Okay， so this is。What we need to talk about。

A perfect Monte Carlo sampling。😊，What I mean is。If you want to have an ideal case， right。

 if we could have anything we wanted， what would be the framework。

This is the framework that we're going to talk about it。 Per Monte Carlo sampling。

So it's important to understand the ideal case， and then we see what's missing。And this。

 and then we will see if we can come up with an idea to compensate for the missing part。Okay。

 that's our approach here。Now， suppose。You know， that posterio is given to you。Right。

And we can draw samples。 IID samples。 So IID samples are。Independently and identically distributed。

Meaning， the samples are independent， right， You don't use one to draw the other one。

They are independent events。They have the same distribution， identically distributed。

 They have the same。They confirm the same distribution that has the same mean and variance， right。

So we call them IID。So when you hear when you hear party， it's the same thing as examples。

 hypothesises， random samples， right。You can put in a set。 Now， notation is a little complicated。

 but you remember time and steps were like this， right， This was basically a set of x 0。

 X 1 all the way to X K。For each particle， we're using some。Index as a super group， okay。

So we have n of them， right， This set here， is's basically。It's a compact way to write an examples。

 when I write。They say why， I。It doesn't matter where。Basically subscript was superscript。

 I equals 1 to n。 this means y1。Whyan， okay？It takes less of space if you write it like that。

So we have， imagine you have the posterior。 You can draw N IID particles， random samples。😊。

We can define an empirical estimate of this distribution， using。

Delta masses placed at every IID example， right？So if you。

 this is just a notation to emphasize that the mass of the probability is placed around these。

I OD samples。所以。The proba is placed around these samples。The total mass is just some of them。Okay。

Because Delta is giving you。And。In terms of a probability mass， we integrate， right gives you one。

And you have N of them。You need to divide it by n， right。Because this will be n by over n equals one。

As a discrete probability， right？Does that make sense， Everybody is following。

I'm going to draw an example。Make sure we have。An understanding of the starting point。

Imagine we have。AComp posterior distribution。We know it。Wdraw。Not only we know it。

 and we can draw random samples for it， right。Imagine you draw random numbers， and。Well。

 around the mos， you should get more， right。That's how it works。 because the density。

 the P D F is assigning a relative。Basically， likelihood or value to each。Event。

When the peak is higher。That means it's more likely that that happens。

Just like when it's Gaussian you get more samples， wherever the mass is concentrated。So。

To make sure that notion is respected， we should get something like this。Now， place an equal mass。

 right？On each of these examples。We have N of them。What is the probability of each sample。1 over n。

 right。And this deelta notation is telling me where to're located us。Don't worry too much about them。

Notation， right？So Delta is telling you where it's located following that idea that delta of x minus a means it's centered at an A。

So the mass is centered around these samples。If you weigh them equally。Why equally。

Because theyre II D， right， We have independent events。 We don't have any preference over one。

Or the other， Let's just rate them equally。 one over n。 We have n of them that will add up to one。

 That's our probability mass function。Approximateinated using， essentially。嗯。

Instead of independent events。So。To summarize， if you know the postereior， if you can draw samples。

 you can do this approximation。 That's not a problem， okay。Why we do this？ Well。

 because even if you know the true posterior taking the expectation of a function to calculate an integral like this。

 right。It might not be easy because in general， it's difficult。We can't just integrate anything。

Arbitrary， it might be very challenging to calculate it in closed form。 However。

 when you place the mass over these deelta functions。When we integrate it。What happens？First of all。

 it will break the integral， right？We only need to evaluate the function at these IID samples。

 That's good news。😊，Second， because of the linearity of the integral in this sum。

 we just need to basically value the integral independently for each of the terms in this summation。

Because the integral love。X plus y， right。Let's integral of x plus integral of y。嗯。

You don't have to write them together。Now the delta will break the integral。We evaluate the function。

 and we。We have。This one over hand， because we know we would need to normalize it。

 The probability needs to add up to one。 That's why we're doing this， okay。Otherwise。

 it will depend right， the value of the integral will depend on how many examples you draw。

 We don't want death， right， You should gate。You should get ideally。

 your intuition should say that probably that we should maybe get better answers if I have000 IID samples than 100。

 right。But also， I should get roughly the same answer within some error bounds。

The value of the integral shouldn't double because I'm drawing half of the samples or twice of the samples。

So that's why we need to normalize it。So， the trick。

That we did enables us to evaluate this expectation。😊，Basically， that's the idea。 And， of course。

 you can apply to any function。 This method is a way to integrate， calculate expectations。Not。

Specific to this framework。This is related to Monte Carlo integration。Now。

 the estimate of that integral is unbiased。 that's very important。Meaning。And the limit。

 as you draw infinite number of。Samples almost surely will converge to the true value of the integral。

With probability of one， I definitely will converge to the true value。

That's the law of large numbers。If you repeat something more often。

Its more likely it gets closer to the true event。 right， That's the law。

 large numbers in the statistics。Now， why it's unbied， Because when you write。

 write down the definition of the variance， which is the expected value of。

X is squared for random variable minus mu squared。 remember that？Right， we had this before。

 So write down and define it to be this whatever variance。You want to name it。

We have to assume this is bounded because otherwise， it breaks down the framework， right。

 assuminging the posterior variance is bounded。Then we can talk about sample variance。

Because the examples are IID， right。All of them comes from the same distribution。 Therefore。

 all of them， they have the same variance。Therefore， when you talk about the sample variance。

You get this。Clean formula。This follows。 This is the same sample mean variance idea we talked about in your homework。

Right， there's a population。Sample is a subset of that。

Which behaves like the larger population when people do survey， right？

So what's the average income of American， right。Not know。 There are 300 million。

 Do they call all of them。Probably not。Maybe they ask a million of them， try to。

Spread it around as much as they can。Different demographics and locations and all the variables experts know。

 right。That's a sample。Basically， estimate sample mean。Is the income， for example， that tell you。

I don't know。 what is it is a 20K。60 k。100 k。They tell you maybe 60 K。

 but then what is the sample variance， right？What if。The estimate is here。

But the dispersion is the interval。That these numbers come from it's so large。That in reality。

 if you take an example out， it's unlikely to be close to that mean mean because mean is a hypothetic hypothetical situation。

 right。I always wondered who's average American。 Then I realized one day， that's not a real person。

That's what when statisticians talk about。It's not a real person。

 It's just a concept that does not exist in reality。 That's the mean， reality。

Could be somewhere here， right？Now， so it's important when this interval is large。

It's less trustworthy， right， If it' is small， it's better。Okay， now this is called。Sample variance。

Sample variances。Is the standard deviation of。A variance of the sample mean。

And what happens when N goes to infinity。 I mean， if you ask。The entire population。Right。

Every possible person who lives in America， then。There is no variance for the sample。

 because that is the true average。So that this concept is very important。

 The sample variance is the variance of sample mean。

Because sample mean is a representative of the entire population， not the population itself。

So when it goes to infinity， this goes to 0。 We nail down the。Mean exactly。

Which means it converges to the true value， right。That's why it's unbiased。Following this。

 sample variance of the mean。You had that question？这其实。Am I going too fast？Elibeth。Once。making。都会。

The eye。The question is， what is this eye here， right。I'm using So you。

 you remember the the sub was for time， right。I'm using。Superscript to track these。Random ID。

 random samples， the particles。So I have particle 1， particle 2， particle N。I need to track them。

So in， in another sense， to give you more， basically intuition is that in common filtering。

 we were tracking only one particle。A single hypothesis。You can think about this filter as。

Essentially。Running a lot of common filters， right？Roughly， not。There is a。上串。有。

So with this notation， I'm emphasizing that the mass of this probability is centered around these IID samples。

 right？Just just matching the deelta notation we had， Delta。Yeah， you don't need to overthink it。

You could write it the other way as well。Right， just emphasizing the mass is centered around these points。

 not everywhere else。给。Can you explain the left hand side of this equation。Who's talking？H。😊。

It's from Zoom Oh， from Zoom， I thought it's future you talking to you。😊。

That's not the right question。Okay， so let's hear the question on Zoom。

So can you explain more about the left hand side of this equation。

 I'm a little confused about the notation like in front of inside this。

You guys are very uncomfortable。How about this。Yeah， yeah， it's better。You're free to。

 Now I'm following standard notations from references that I give you。嗯。

But I' I don't think that's important。So that posterior is over still your random variable， right。

It's just placed over these random samples。Is that basically。An answer to your concern。Yeah， I guess。

 So， so on the right hand side， the Dlta function。呃。The center at London。At random points。Each。

 each term is placed around。One example， but we have。Delta of x minus x1 plus delta of x minus x 2。

Plus， delta of x。Minus x n， right？So we have n of them。If you integrate。This empirical distribution。

 what will happen。If you integrate P of N。This will give you n， because。If you integrate Delta。

 I will give you one。Now， I don't want that because the density should add up to one。Right。

 one of the axioms of probabilityba is that when you integrate。It should add up to one。

So I add a normalizing constant here。To make sure it will add up to one。可啊。Then。We have。

 This is called an empirical estimate of this distribution。Okay。Now， you might not need to do this。

 Obviously， this is an approximation， right， But within this framework。

 this is a good idea to build our method。 Okay， of course， we're losing something by。

Deretizing the distribution。So before you mention that。いけ的き。

I'm going to call and filter at lunch at times。So does that mean that we should think of particles instead of？

Pot masses at。Are they point distributions？Yes， they are。An event， right？Each particle is now。

 the question is， should we assume each particle is basically a distribution？We。

Consider a posterio that describes the entire sample， okay。

When you're talking about individual particles， the evolution of。That event， right。

 the way it rolls out as you collect data。You could imagine it as if youre running one column filter。

That will not describe the entire。Set， it is just about that single particle， right。If you do。

 if you want to describe the entire sample， then you need to talk about。

 let's say you're trying to aine and covariance。 and you talk about the mixture of these little Gaussians。

So you can build the posterior。 So this posterior is much more powerful。 It's describing。

All of these。Partticicles， right。We're not going to make it that complicated。

 but that basically that's the idea in fast Islam。 When they did part a filtering Islam。

For landmarks， to tracking with them with EkeF。And then for the robot you're running a particle filter。

 you can combine them。But we won't do it today， we' just about particle your filtering。Profesor。

 I have one more question。Is there another question？Yes。

 this is from zoom as well Can I see the previous slide？You would like to see the previous slide。

 okay。

![](img/9fd459256195d8893a552a6c061a55b7_7.png)

In the blue that you've drawn， you have。Probability of x from zero to K。

 does that mean there are K probability distribution functions here？No， the question is。

 and we right。Probability of x。Well， yes and no。 When you write the probability of x from time 0 to k。

 We mean their joint distribution， right， Of course， they have marginal distributions， too。

 because you're saying that do we have K different densities。Yes， you can talk about their marginals。

 but， I mean， their joint density。It's the same as same notation we used before。

This will be their joint distribution， okay。You can marginalize。

 then you will have K different densities。Okay， so let's continue。And the last point。

 if you're estimation enthusiast and you like central limit theorem。

 you can show that if the variance is bounded。In the limit， this random variable here。

 square root of n。Times。The error， basically， between estimating the true value。In distribution。

 it will converge to。Dis Gaussian distribution，0 mean。With the true variance。

The central limit theorem holds here。就是没事。function of I。爬生。Which one is constant？

This is a true value。I of F is the true value of this integral。Right。This is。I of F。

 if you could truly evaluate it。If you could evaluate this integral， given a function F。

And a density posterior density P， What would you get， right。This eye， right， That's。

 that's just the。Value we get out of this integral。Well， because we can't calculate this。In general。

Right。If we could。You can throw away everything， basically。If you can't。

 you need an idea to integrate， right。So that's why we talk about this approximation。

S than is like assembling and。Like npoints from it correct。So shouldn and will do that。

The number of actual points is of communityity。Okay are kick and from next week capital。annual。

Let me understand your question。 We're not sampling from data set。

 We're sampling from a true posterior that we assume we know it。Right。This is not about data set， or。

This is a hypothetical situation that we know the true posterior and we can draw samples。

 Then we are able to approximate this integral and evaluate it。 And in the limit。

 as you draw more samples， it will converge to the true value。 That's the takeaway， right。😊。

This much we can do right now。 So we can write a loop in the computer， not very hard to code。

 draw our samples。You have access to your function。 We can evaluate this function， right。

 And we assume we can draw samples。 Then you are able to approximate this integral。



![](img/9fd459256195d8893a552a6c061a55b7_9.png)

对。So we can estimate any quantity。There is no limitation。

And what type of function we're dealing with。Im wondering， is there a rule？In general。

How like to know。还是可以。Thank hear examples。There you go。So the question is， is there a rule。

 tell me how many samples I should take， that would be too good to be true。Right。

And the answer is no， the better， the more the mirror。If we knew that。

 then why would we need engineers， Any could do it on the street。Your judgment。Is important， right？

To set that number of samples。Not too low， we will become degenerate。Not too high。 maybe be overkill。

 maybe with less samples， you're getting already good results， right。

So it depends on a lot of things。 Do you care。In a length that youre estimating in kilometers。

 an error of the order of one centimeter， probably not。Right。

 so real problems usually give you more intuition。 What sort of thresholds you can choose。

 especially if they have physical meaning。 It makes it super easy to judge。Now。

 the very important fact is that the rate of convergence is independent of the integral dimension。

 It doesn't matter how high dimensional is this integral your function。

 As long as you can draw some samples， you evaluate the same。Basically。

Averaging of your function evaluation。 That's very important。

 because any other numerical integration method。Basically。

The convergence rate will decrease as the dimension of the integral increases。

 That's the curse of dimensionality。 As the dimensionality of the space goes higher。



![](img/9fd459256195d8893a552a6c061a55b7_11.png)

A lot of math methods basically， become。Slower and it slower。

And that's a very big limitation in practice。Do you know any other numerical integration method。

You might have seen。Some other methods， maybe。

![](img/9fd459256195d8893a552a6c061a55b7_13.png)

Qudator， right。The Riman integration， the simplest one。 You have a bunch of rectangles， right。Now。

 those rectangles。In 3D， they become cube。In and dimensional。

 that's a hyper grid that you need to loop over。So you keep adding nested loops。Right。

 that that the complexity grows。Explanatally。So this method is not deterministic based it's based on random sampling。

All right， that's all good and nice。 What's the problem？You are all sold。

With the silly assumption that I made in the beginning。Yeah。ただけす。这是一当。Time in efficient。 No。

 there's a bigger problem， much bigger problem。Right， we don't know the posterior。If we knew it。

 the problem basically would have been solved to begin with， right。So that's the problem。

So if you know the posterior， you could draw a sample， you can evaluate it。 But the problem is。

 of course， you don't know the posterior to begin with。So that's the problem we are facing with here。

If you knew where your robot is， exactly， why would you run a localization algorithm。

You just know it。嗯。So。We need a new idea。To。Bypass that problem。There are many methods for。Basically。

 bypassing data then。We won't talk about all of them here。

 We talk about one of them in particular that is important to us for this sequential。

Monte Carlo method， and it's called importance sampling。Here's the idea。I do not know the firsteror。

Therefore。Even if I could， I cannot draw samples because I don't know it。Define。

A new distribution that we know it。Anything that you know。

Call it importance sampling distribution or proposal distribution。However。

 we need to make an assumption that if。This is P。My proposal distribution support， right。

Covers the true posterior。So， we need that otherwise。If you work with this。Basically。

 the hypothesis that you will generate using this proposal distribution as a surrogate。

For the troupop a stereo。It will never， basically cover。Everything， right that's。

That's the reason why we wanted to cover。And their answer is that， we don't know。

If you will cover in practice or not。Okay， again， if you knew the postereo。

There's a lot of thing we could do， so。Another basically design choice or judgment that we need to make。

Okay。So we need that。 So when you read that the support of this pi should include support of P。

 that's the reason because when you generate hypothesis samples。

Then there is no chance to cover this area。 and that's not good。

That includes our possible operating point。So put it in the form of。So。Equs。First of all。

 you remember。This part。This was the integral we wanted to calculate， right？

The expected value of the function with respect to the true posterior。Can I divide it by this。

Basically， this integral here。Well， this adds up to one， right？There's no problem adding that。

And that might remind you some formula for center of mass and some sort of weighted averaging， right。

And it is like that。那。We propose。To define。Wait。That is the ratio of true posterior over the proposal distribution。

If you do that， then you can replace it。Through a streor with the weight times the proposal distribution。

 right。Which what this is what we get。 So that's the crazy line that you see in the beginning。

 It follows from this， right， Take the integral all divided by one。

 which is the sum over the posterior。 define a weight。😊，To be the ratio of。

True posterior over the proposal distribution， then substituted into this equation。And that's what。

You get。So we have not done anything besides just manipulating terms。However。

 we know that we can approximate that integral。Now， F times W just is another function， right。

 And I know pi， I can draw samples from it。Using what we learned from that Monte Carlo approximation。

Now， I can evaluate both of these integral， which lead to basically the numerator。

It's the an sum over F times W。 and the denominator is。Basically， sum of the weights as a function。

On top of that， let's take this basically denominator and normalize all the weights， right？

To make it cleaner。We're going to normalize all the weight。This W Tilda。

And we get this interesting equation。So it sounds like。If I replace。

The troop post stereo with a proposed distribution， they the。Uniform， basically approximation。

 will change to a weighted sum。And that way。Depends on the proportion of the true posterior and the proposal distribution。

This is interesting。But it's not sufficient for recurive a state estimation。So。

 we're going to continue。So the checkpoint here is that if I replace the throughos stereor。With。

A distribution that I know。 I can approximate the integral using weighted sum now。And these weights。

Basically。Depend on the ratio of。The trueop posterior and the proposal distribution。ItStill not good。

 We need to continue， okay。Allright， so let's factor this proposal distribution with no approximation。

This is， basically。Changeopability， right， if you appear of。X and Y， given Z。Spear x。

Even the fine P of。Y， given X and Z， right， that's all I'm doing， first line。so。

This is x0 to k -1 and x K。 Basically， this is the joint distribution for。These two variables。So。

 we get。Probability of X K， given。Everything else， times。The probability of the other one， given。

Everything else。Now， the reason we drop。Z K， right， This is k -1。Because data is coming sequentially。

 and the causal。Right。Effect in in our models。That we consider we drop the future data。Now。

 let's do the same thing for the new。For really， at time a step came minus is1。

 You get exactly the same thing。 You keep repeating that at some point， you reach to。The prior。

And you have factors successfully all。These X， J。Terms to be conditioned on。The trajectory。

Acept that point， J， right。Or basically up to that point， right。Up to the point J。

 times step J and the data up to that point。So we can factor this distribution exactly。

 We are just using the chain ruler probability， right， We， we did not。Approximateimate anything。

What were the weights？The weights were the distribution of the troop post steior and the proposal distribution。

We managed to factor。Pie like this。How about we factor the tro postereior as well。Now。

 this is exactly equivalent of what we didnt。The upper part。P of。X，k。What about this term？Now。

 you know from Bees rule that you can write this as。

And then you can make all those markov assumptions。

 G up the right redundancies based on the mark of assumption。This will give you。

What you see on the slide。Okay。So no， no magic。 These are all follows from all the assumptions we talked about。

 the chain rule， bay rule。But I do encourage you to go through it one time because it can be confusing。

 There a lot of。Terms。And it can be intimidating。But they all follow from some basic manipulation of terms。

So we can factor the posterior like that。And if you basically divide them， right。

Sounds like I can get a recursative formula that。Because this first part， right， this first part。

If you divide them， right， that's just the way that time is  step K-1。The more interesting part。原来。

How about we basically drop this term and make it proportional。That's a very hard time to calculate。

 We have no idea how to do it。咁。Well， that's we what we know is' a normalizing constant， right。

It does not depend on x。 So let's drop that。 And instead of exactness。

 let's say the weight that time is step K is proportional to the weight that time is step K -1。

Which follows from。This term here， one divided by this term 2， right， one divided by2。

And the more interesting part is that now the numerator here divided by this。Term here。

 that's what we get。 Alright， so now we have， it's got very messy。

 but we have a recursive formula for。The weight。We needed that。 Otherwise， there is no way forward。

But we managed to turn the weight calculation reccursively in the sense that if I know the previous weights。

There are some terms。That are familiar。These terms。What was this term and what was this。

I'm gonna add a you here。 So you remember it， but it doesn't matter。We know these models。

 That's our likelihood。 and that's the motion model， right。And we， of course。

 we know the proposal distribution。This is really nice。 Now。

 we know all the terms in this recursive formula。😊，按。If we start at time 0。

We just need to initialize the weights， right， Sounds like now it will work。Because in the beginning。

 we initialize the ways maybe uniformly。 That's what you did in your circular world with base filter。

 I have no idea where to put the mask。 Maybe let's just distribute it uniformly。Then next time。

 based on observations and motions and the proposal distribution。

 we can update the weight reccursively in time。😊，And then we will have the weights。

 and then we can evaluate that integral， okay。So that's the idea of important sampling。Plus。

 this reccursive。Weight calculation。So， they recursive。Calculation is actually called S I S。

 Its a sequential， important sampling。 important sampling itself was not sequential。

 So this is called S I S。Or sequential importance。Sampling。Well。

 I know it was a little of a headache。

![](img/9fd459256195d8893a552a6c061a55b7_15.png)

But I think it's very important to match that concept and intuition with these equations。

 because that's what you will implement。

![](img/9fd459256195d8893a552a6c061a55b7_17.png)

It's those kind of thing。Like I guess the reason I went to。

Was because we didn't know the actual distribution so we said， okay。

 what's was the distribution for it， but how do we know that proposal was representative very good question is that。

We thought that we don't。 we know that we don't know the truth of stereo。

 And then we said that let's propose a distribution。Another question is。

 how do you know that's a good proposal， right。In general， we don't know。For a specific problem。

 the expert knowledge or domain knowledge can help us to choose the good。Proposal。

 which we will do it now for robotics， right。But keep in mind that when somebody from statistics or math background is developing a method。

They like to keep it as general as possible， right。

This is us that we want to make it specific for ourselves。

There are people in other fields making different design choices。Using the same methods。

So that's why you see this generality。But， of course， we。

Generic methods often don't work well for us。 We need。

To adopt them in a way that we can specialize them for our application。

 And that's what we're gonna do。Now， first simplification is that in filtering。

We do not need to track history。First thing to do。We delayed this simplification until now。

 that was without simplification。 Let's drop the history using that markov assumption that we had in the filtering。

And keep it just。To be conditioned on the previous state by assuming that we have all the knowledge in the previous state。

So that's the posterior， right， Do you recognize the posterior。Pi X，k。嗯对。

So some well we can write this as well。Right。So that's the posterior。

We're going to make it even more。Basically， special。The special case is that。

When the important sampling in distribution or the proposal distribution。

Is the prior or the motion model， The motion model that we use for prediction in a more general context is called the prior。

Right， because that helps you to。Basically predict where you are。

 gives you a prior before you observe where you are。Imagine we set this distribution。

That's our design choice， right。We can choose anything。One of these。

Particular choices is interesting。 If you choose the motion model and keep it to be。

Your motion model。Then what happens is that。Well， there's no。This was Z。In general。

 but I'm choosing it to be my motion model， right？So if they are the same in the recursive wage formula that we。

Calculate that。 Then I can simplify these too。That's very nice。 My recursive formula is now。😊。

It's really simple。That means that what evaluate your likelihood model。

 the sensor model add the weight to the previous weight。Just rely on observations。

 What draw your samples from your motion model。 It makes sense for the robot， because。If you。

Have a model that describes the motion of your platform with some noise。

You can generate different noise， maybe realizations。 and then。

Simulate how the robot might move forward。And that's a really good set of prior proposal， right？

Given that you are here。 and then maybe with some drift。

 you might end up here or here or here or here， but not the other side of the room， right。

For another particle， given that the， the particle is the other side of the room， samee thing。

 it will move around that area。You won't move here if the proposal distribution is your motion model。

Okay。So， that particular。So we， it leads to two algorithms。 If you don't make that simplification。

 that will give you S I S particle filter， sequential importance sampling particle filter。

 This is a generic particle filter。Basically， to simulate， you start with a set of。State。And wait。

Now， if the state is， let's say a 2D。Robot with orientation， X includes。

Your 2D coordinates an orientation， right， That' your state vector。The weight is scalar。

 It's a weight for that particle。Initially， you start with maybe an empty set or uniform initialization。

Sample from proposal distribution。Update the weights， right。This is empty set for K， right。

 And then add the updated particles。For all of them。And then you're done， okay。

That's called S I S particle filter。So in three lines， that's the algorithm。

What's wrong with it is that。You start with a set of particles， and you keep。Evaluating weight。

 right。So you draw samples。You weigh them。So each time， based on your previous。Particle， right。

You draw a sample and you update that。 so it will move based on your proposal distribution。

 the particle will move， and then you wait it。Based on this complicated formula。

 So what will happen is that。As time increases， this distribution。Will become more and moreke。

At some point， it reduces to just one particle with nonze weight after a few iterations。喂。

Because if particles are spread around and most of them are unlikely， maybe。

 and they're moving around。Right。This randomness in the behavior makes it very possible that a lot of times you get low weights。

 right。The sequence of low weight multiplication will basically reduce the weight to 0。

And at some point， you will have basically。One particle， we can simulate this。 This will happen。

 And that's the degeneration problem， okay。So basically randomly moving a bunch of particles around and reweighting them。

Unless you can generate unlimited number of particles will no good。For us。

This is known as a degeneracy problem。To fix the degeneracy problem。

 an idea was introduced that's called resampling。So， reseling is。An idea to fix this。

Which we will talk about it in a bit。For degenerationacy， there is a measure。

You can define an effective number of particles using this quantity1 over some of the square of the weight。

In two extreme cases。If all the particles in the beginning， right， they have uniform weights。Right。

You get one over。Some of。Which is。And over n is squared， right， This will give you n。

 So if all the particles have the same weight， basically。

 the effective number of particles is all over。You want all of them。

If the entire distribution mass is placed on single particle。Which means all of them are 0。

 except one of them。 The effective number particle is one。And that's what will happen。

Two extreme cases of。This basically formula will help you to monitor the degeneracy of the filter。嗯。

Somebody is sleeping in the front row。We're done with degen C。You're going to talk about reling。

 Are you awake。Sample。Emoverishment。Basically， there's a new problem。But we。

 we're not going to fix that。 We just ignore it。 So reampling reduces the effect of degeneracy。

 That's the idea。And the idea is。Pick the particles with higher weights。

And replicate them and get rid of particles with lower weights。This way。

 you can use a limited number of particles， a limited amount of resources to to run the simulation for a much longer time。

Because you get rid of unlikely hypothesises and reproduce more likely ones。Okay。

Does that sound like a good idea？一个摄上。应该。The位置。For example， in updates step。

 some particles remain await zero。And sometimes maybe they can be updateded to not zero zero number so why should wait。

Recent。Or if they wait。 So the question is why。This is a problem。

 Even though the particle weight is almost 0， maybe I see a good observation suddenly and。

Now I can come back， right， Can a particle come back。 That's your question。Well。

 if the weight is roughly， let's say one times 10 times minus 16。And you add a bunch of。

 I don't know。 Your weight is even really high，10， right。

Your updated weight will be something like this。Right。You need way more than one。

Good observation to come back。Right。So one of them will survive because basically。

 your filter should wait。One of them higher。Right， because your filter is not wading the particles in an absolute sense。

 It's relative to all other hypothesises。One of them will get higher weight based on the proposal。

And then when they go lower ways for a couple of iterations。It's very difficult to recover from that。

什么名字啊？哇。One single vertical dominate。Yes。I ocean and there is no chance for us。Rere。Yes。

 there's no chance to recover。 But the reason there's no chance because there's no mechanism in the in the algorithm to recover。

 The algorithm is not trying to fix that。 It's just。Proroppaating particles and invaing them， right。

There's nothing in the algorithm to deal with that problem。

So now we want to augment the algorithm with some method to deal with that。

 And that's the resembling。Now， these ideas are very。

 You can play with the code examples to replicate them。 It's not difficult。

So the reampling idea is good， but there' is a fundamental problem。 And that's。

The problem of loss of diversity， because if。So， basically， if you。

You start from a set of equally likely particles， right。And then we propagate them over time。

And then re reweight them， right， Maybe this one has a lower weight。 now a lower weight。Now。

 we're saying that， well， these are not very likely。 I'm just gonna end them here， right。Now。

 I'm going to make， maybe。Two of this guy， one of this guy。Through of this guy。And the。

 we get a fresh start equally weighted， right。They do it again。Maybe this time。

 this is not very likely。Maybe very likely。Maybe not like。 And then say。

 I'm going to kill these two as well， these three。So now， this should give me。What's the problem。

 But keep rembling。At some point， we're tracking a fixed number of particles， right here。

5 At some point， all the hypothesis are originated from the。From from one parent。

That's obviously against the idea of running multiple alternative。Mypo。

So that we can model multimodal distribution。So that's the fundamental problem that is introduced by。

Resampling and called sample impoverishment。 So there are two problems， right， degeneracy。

Introduced by S I S and sample impoverishment， introduced by reampling。 But we're not gonna fix that。

 Its not good tuning。We'll make it work， but this problem is there。そこ革水ズの。theseute those efforts。

As we。你可ず那个成分。So that我 time一。If you example all the samples。The question is。

 can we make the number of particles adaptive， That means maybe initially more particles as you move forward less or vice versa。

 Yes， there are many variations of the algorithms， including your textbook。

You can use K L virginence and some other methods to adapt the number of particles。

 Probably in the beginning， you want more particles。

That you're trying to Buhist describe or initialize。The filter， right。

Once you are around the most likely hypothesis。Maybe you just need a smaller number of samples to track。

You can。We， we， were not talking here about different variants of the algorithm， right。

 because once you know the core algorithm， you can make a lot of。

 it's easy to understand the different variations of it。

But that that was a good idea And our papers published and that idea。Around 2003。

So you're very unfortunate that。That idea is published already。Okay。

 so a generic particle of your filter with the sampling will become like this。

Start with this another particle。Choose a degenerate， basically resembling threshold empirically。

 I don't know，1 N over 3 or n over 5。 Maybe it's a good number。

Trrow a sample from proposal distribution， update the weights， normalize your weights。Add them to。

Add that particle to the set at time is the K。Calculate the measure of degeneracy。

 If the measure of degeneracy is less than that threshold。Which was n over three。Run rembling。

Get rid of some particles， replicate some of them。After re， all the weights are also normalized。

Its a fresh start， their uniform。So this way， we can always track。Set of more likely particles。

It's a very。Basically。嗯。Can't find a good word。 But you have to be careful because too much re will make the filter again。

 degenerate， right。But if you don't do it at all， it makes it digital。

 You need to find a sweet spot for your problem， by tuning。For robotics。

 that's what we're going to do。 So maybe this is what we want to remember， right。

So the previous one is important because you read some papers。

 they're proposing something more complicated， maybe using sensor models and other ideas， right？

But first time， when you want to implement for your problem， particle of your filter。

Probably you want to try this。The difference is that draw samples from your motion model and update the weights by just multiplying them by。

Your likelihood。So unlike common filtering， when we had some algebraic equations to update。Basically。

 the posterior parameters， right， mean and covariance。Here。

 we literally evaluate that likelihood that lets say Scsian， right。

 You get a value of that P D F and multiplied by the weight。 So the posterior is characterized by a。

Histogram。And these are with these weights。 you can visualize it that every step。

 you can visualize a histogram， right。And。These weights， maybe they show you something like this。

 right。When you debug your algorithm， it's a good idea， too。Visualize the histogram each time。 C。

 monitor it。As you tune it。Using the weights is。So reampling eliminates particles with low weights。

And multi， multiplies particles with high wavess。The particles with high weights are selected many times。

 and that will lead to the loss of diversity， which is the loss of alternative hypothesis。

In the filter。Depending how complicated and nonlinear your problem is。

That can cause a serious problem。And if it's not causing a serious problem。

 this this loss of hypothesis。Maybe you could solve it with the common filter already， right。

 That's a sign that。Maybe it's not that nonlinear。So this is a resembling algorithm。

 it's called low variance。I just covered a basic idea。Now you see here。So you basically start with。

Calculating the cumulative sum of all the weights， right， you enter the algorithm。

 get all the weight， add them up。In a cuummulative way， right？

This will give you this cumulative distribution function， CF。Okay。They will get this W， right， C。

And then this is from 0 to1。 This is the CF， right。And you get something like， you have one，2。

All the way to end。And then you get some weights like this， depending how。

How much of the mass is located on that particular particle， right， it will occupy some of this。CDf。

So this algorithm is using just one random number。And systematically。

Replates particles with higher weights。 There uniform number number between 0 and one over n。

Because you have N particles。That's the uniform distribution over individual particles。

Then for all the particles。Try to traverse this CF。With that one n fraction at a time。First time it。

 this is 0 because I equals one， right？ So we're working with whatever random number we got here。So。

 if you is。So we are for particle we're processing particle J， right。So if U is bigger than。

The weight of that particle。We pass， right， If that random number is bigger than the weight。

 cumulative weight of that particle， we pass。Until we find a particle here。Let's say here， right。

Basically， here。That the rate。Maybe you are here now， you， right。

 until the weight is higher than this variable。 So first time。

 what it means that if the particle's weight is less than that uniform， ignore it， right。

Ignore all the particles。Until you find a particle that cumulatively is above that。Uniform initially。

 right？And when you do find that particle。Replace particle I with J， right。

And set the weight of that particle to uniform。Next time。Increment you， basically。With。

So basically one over n， right， But because it's using the initial random number， you don't。

 you want to work with that one random number。 You don't want it to be exactly one over n， right。So。

 you is。R plus。I minus-1 over n。Now， you increase it next time you repeat it。 When you repeat this。

 next time you're somewhere here， maybe， right， And maybe you ignore this particle here。And here。

 and now you want to replicate this10th particle。So what happens is that as。This reling。

 traversing the C D F， some of the particles。That have low weight。They make a little change。

Humulatively， with respect to the previous index， right， Therefore。

 when you increment with one over n， it will ignore them。

Because that one over n is bigger than a small increase in the cumulative way。 That's the idea。And。

In this process。It could be the case that this wild loop is。True。Basically， false。For several times。

 right， So what happens maybe for particle 3，4 and 5。You just replicate particle free。

That's what will happen， okay？So that's the idea of low variance resembling。

It is usually helpful to write it。 If you have time， we can go over it。

 You can write it with maybe five particles and see how it goes。By the way。

 you have it in my previous lectures that I shared， somebody asked。For previous years recording。

But the number of。Watches with。0。That was very sad。It was good for me to see what I said last year。

Thanks for whoever asked。Well， let's say， let's look at the examples。

 So let's look at the the same target tracking example。 We have a linear model。For the measurement。

And the motion model is still linear because we don't know anything about the target， we assume。

The same previous position from the target at time and step K is1 plus some noise。And we assume。

Basically， W K is a Gaussian with 0 mean。And covariance QK， you see here。

And this one is also a normal distribution。With zero mean and covariance R。So this is the。

 this is for， this is the variance for the range measurement， and this is for bearing。

Pearing is the relative angle。To the sensor。To the y axis here。So we run that particle your filter。

Which is called S IR。That part filter that for robotics we covered。

 it's called S IR sample importance reling。 you sample for a motion model。

We update the importance weights using the likelihood of the sensor model。And then you do reampling。

So the cycle is a sample importance with sampling。We don't want to resample every time。

 So we added a threshold。To only resemble when。The filter is becoming degenerate， in a sense that。

Wes are very low。The mass is becoming concentrated on one particle。So you can see that it's a filter。

 of course， there are some jitters， but you can solve the same problem。Now。

 you probably bored at this time with this example。So let's also estimate the velocity of the target。

This is a good practice for you to go and do it and change the previous common filters。

 try to estimate the velocity as well。 You need to augment your state with。The target velocity。

For x and Y。Now， I'm assuming a constant velocity motion model for the target。 I'm assuming that。

Basically， X K。1 is xj minus 1。V is the velocity。Times Delta t， right？The constant velocity model。

 it says that。Your velocity over time， Delta T is constant。I see no surprise。 That's good。

 Thats That's the assumption previously was constant。Position assumption， right。

 I was assuming the target is not moving。Over time， deelta T。I'm moving it one derivative higher。

 I'm assuming that velocity is not changing。 which is a better assumption， right？

 You could go one more higher。 say， well， constant acceleration assumption。

 maybe then you need to integrate this twice。Which if you have IM U。

 then you can do that on the object that is moving， if you can measure it。

Then the input is the acceleration。 you can include。A better model here for velocity integration。

So in any case， when you write this in a matrix form now your discrete time system matrix is like this。

 which is identity times position， right。Plus， deelta t times。The velocity， okay？

So the state is now not just position。I'm be usinging the notation using X again， but。

I think you get， you get the idea。 You could， I could use P， maybe。X is。P and B。

So we're using the same。Data， I want to estimate the velocity as well。And we can do it。

So now we track the target。 We also estimate the velocity。For。Is coordinate。

How do you know the velocity is correct。Can we just add on limited variables and see。What happens？

You just like take the first derivative of the actual position。That's a good idea。

 You're saying that well power about we numerically， maybe we take the derivative of this plot。

 right？See if it matches that。 and it should， because we integrated that velocity to get position。

 right。So that that's a good way to check。 Well， it is correct because we the position is correct。

 right。However。This one is fine。 But in general， when you augment your system， right。

 you need to check the observability。 So make sure with the same amount of information measurements you can。

😊，Estimate more variables。But position and velocity are very natural， too。Include always， right。

So you have my code as usual， for math 11 Python。And。We can summarize。

So we learned a new filter today。 It's based on random sampling。 It's called particleig filter。😊。

I bothered you with some of the derivations in case you're interested。

But the outcome was that the algorithm， S IR， particle of your filter。Now。

 we want to use this for robot localization， right。

Now that we learned this filter in future lectures。

 we will use this algorithm to solve the robot localization problem。It can deal with。Nogaussian。

Online estimation problems。We can deal a global uncertainty。 Global uncertainty means。In this room。

 again， you want to localize。 You have no idea where the robot is located initially。

Or at some point in time， that's the kidnap robot problem。These algorithms are very general。You can。

Tackle a very broad range of problems， not just robotics and。Localization。Now。

 the price to pay is the inefficiency in some application domains。

 If your state is high dimensional and you need to draw samples。You need more。Hypotheis， because。

High dimensional spaces are very empty。 If you have 20 dimensions。

 and now you're drawing random samples。in each direction。

 you can basically move in in infinite number of ways， right， if it continues。

So you need more samples。 And that might become inefficient。

Given that we don't track infinite number of hypothesises， okay。But when you can use it。

 it works very well。So that's all for today。The related readings are Chapter 4 of probabilistic robotics。

 It talks about nonpometric filters。 By the way， this is a nonpometric filter。As opposed to。

The parametric filter， such as common filters。Can anybody say why it's nonprometric？

There are no parameters。Yes me。It just that point weight your particle。That's correct。

 There is no parameter to model the posterior。We just track。A bunch of weight。

 statistical information， relationship for the posterio。So， it is nonpometric。

There is a statistical relationship that models。Input output。

So chapterpt 4 and this chapter 1 from one of the books that I basically shared with you。

This is one of my favorite。 It's really good to read。

 Chapter 1 talks about this sequential Monte Carlo in practice。😊，So that's it for today。

 And let's see if you have questions。

![](img/9fd459256195d8893a552a6c061a55b7_19.png)