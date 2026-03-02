# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p03 -03-Lecture 03-Nonlinear Kalman Filtering.zh_en -BV1UfAmeUE3e_p3-

Welcome to the third lecture of Mumbai robototics。Today's topic is an nonlinear calm filtering。

 That's the continuation of the previous lecture。And base filter and linear common filtering。And。

Today， we will see two methods for nonlinear filtering。By the end of this lecture。

 you hopefully you're convinced。These are good ideas to solve some problems。

 Some of the problems that we come across， but most importantly。

You should be able to answer the question that why we need something like extended common filter。

As opposed to the common filter itself， if you're not convinced。Why and when。

You should use the nonlinear version。And what's the core question that leads to the development of that nonlinear filter。

 You should ask it。Right， we should reiterate why I want you to be convinced when you walk outside of this。

 then there shouldn't be any confusion when you should go with extend common filter。

 when you should go with a carman filter。Okay。So we talked about the base。

Dynamic based network as a graphical way to show the causal relationship between variables and how they how the state X evolves over time。

We also pointed out that in a graphical modeling course。

 you learn these graphs are super useful because we can model conditional independence。

 In other words， if you write down the joint probability distribution of all of these variables。😊。

There are so many terms。To deal with， if you factorize it using the chain rule。

But if you have this graph， it encodes the conditional independence。And the product of these。

 basically。Factorized probabilities that we see here。 It forms a joint distribution。

 So that's the motivation for graphical modeling。 And that can be a topic。On its own。

So we just used to motivate the structure of the problem here。So the shaded variables are known。

 Z is given。 The arrow was showing that it is being at that particular location that causes the robot to。

 for example， take an image or。The point cloud the scan。

And motion command moves the healthierer robot to transition from one estate。To another。

So we could write down。The probability of。X T， given。X， T minus-1。And U T -1。Sorry， you。T， right？

So conceptually， what this tells us is that a probabilistic model that。

Helps the state to transition from。Time is step T-1 or K -1。

 We're talking about discrete time steps to time is step K using a non deterministic command。Right。

 you signal， for example， move forward。For a Delta T of。0。1 seconds， right。

 The robot will move forward as much as it can。And then maybe you have a model to know predict where the robot will be。

 But because there is no perfect actctuator in the real world。And there are so many， for example。

 the carpet， or maybe there's a bump， right， as the robot is moving with wheels。

It won't be perfectly at the place that your model will tell you。 So necessarily。

 you will deal with some noise or。A region for possible location that the robot can end up。

 And that motivates the probabilistic model for that。So the noise will capture that。

 It's supposed to capture that。Basically， region that we hypothesize the robot will be。

 So that's the probabilistic motion model。For the measurement。I should write it here。

We have a likelihood model that uses mark of property that it， it is shown in this。Graphal model。

 because。When you condition a variable on the parent node or all the nodes that are pointing to that node。

 it becomes independent of all other nodes。That's the same thing as the Markov assumption。

So that's the likelihood and sensor model。So in the state estimation problem， we want to。

Our goal is to estimate the posterior over the variable x， given observations and control inputs。

 Z and U。The specific way you attempt to estimate x or derive a probability distribution over the posterior leads to different methods。

You can have common filtered。 You can have part of get filtered。 You can have。Basing in France。

Or generally speaking， that can be。Clasified under the topic of inference， right？

The specific way you want to do inference is a little independent of。

This general notion of what is given what we want， okay？

We're talking about a filtering aspects of inference。 That means we don't track the history。 We only。

Estimate at any time the state at the current time step， okay。

So the base field there in the previous。Lecture we went through the deris of this。 It leads to。

This prediction model， and。Observation model。The prediction model showed up in the marginalization step。

Where where we can use the previous belief。Which was the definition of posterior at time is step T-1。

To predict the posterior， the belief at time is step T。Then we could use the base rule。

To use our likelihood and belief as prior。To do a correction。The particular model that we used。

Last time。It took the form of。至。F。T -1。B times u。Plus， some noise， right。This is a linear。

Realization of this probabilistic model。So there is a deterministic part。

And there is a stochastic part。If you drop the noise。The model is deterministic。

Because we assume that command U is determinist。 You can't assume command is noisy as well。

But you can decouple it into a new noise term， and then。Name it again， W， right。That's okay。

 We can deal with that case as well。So previously， we were dealing with linear systems。

And the likelihood model， the linear version of this was Z equals H。Xt plus some noise。Okay。

The reason。This is probabilistic。Or stochastic is because of the noise。Not because of the model。

 right？The same model without noise， is deterministic。

Because whatever is the realization of x will give you 1 z。Whereas if you have noise。

 the noise follows a distribution at every time it can have a different realization。Okay。

that still why。I understand that the belief is a prediction。

 so we want to use this probability of the X state given the previous state and the input。

 but if you was about belief of x t minus one， why is that there？Why these term shows appear。

2 questions。 So you have two questions。 One is why the belief X T -1 shows up here。The second one is。

Why there is an integral。So， the integral is。I answered the。One that I can here first。

If you have a probability the distribution， marginal distribution of x。

Or maybe I use a notation that is similar to that。 If you have joint distribution of X T and t minus-1。

Sorry。The marginal distribution of X T。Equals。According to the law of total law of probability marginalization rule。

Suming over or integrating over。The joint distribution。Of。X T and X T -1。 Of course。

 it can be any other variable， but we're interested in a recursive。

So we look into the joint distribution of X T and the previous system。So this is true。

 And you don't need any particular model。 This just follows from the laws of probability。

 You can integrate out any variable。If you specifically want to evaluate this integral， of course。

 it can be hard。 It depends what is。The model for P。For example， if it's linear， if it's Gaussian。

 we can evaluate this integral exactly。Which makes it very efficient。If it's more complicated。

 you might not be able to do that， then you have to do it numerically。It can be more intensive。

 computationally speaking。No。ButOne more question。This is point of continue。What if is。It's crazy。

I'll answer that in a bit，Just to finish this， you can also write this as。

Using the change rule of probabilities， you can write this as。Conditional distribution of X T。

Give an X T -1 times P of X T -1。I'm dropping all the extra terms。 you and previous observations。

 right。You could include all of those。Now， now you can see this term here as。Again。

 I'm simplifying your notation so I can quickly make a point。This is your previous belief， right。

 this recursive form。Pps up here。Because we see the marginal distribution of x at time T。

As a joint that。Was the integration over the joints， right？And this is， of course。

 your transition model。So hopefully， that answer。Both of them， right。Okay。It's a good pra。 I。

 I encourage you to derive it one more one time for yourself and maybe let us know in piazza and that that can。

😊，Perhaps， help to。Internalize it or memorize it。Now， another question was why you。

 Why do you write integral， what if it's discrete。That's not a problem。 You can change this to some。

 okay。It is still true。It's just when it's continues。 We're talking about densities。

 Gaussian distributions are。Continuous。Dsities。If you're working for with probability mass functions。

 those are discrete。 So we need to write the discrete time equivalent of。

 which is discrete equivalent of the probability rules。 and those are。Using summation。

Instead of the integral。Does that answer your question？So whenever you see an integral。

 you can think about it， I could write it as sum。Because that's for the discrete case。

So part of the course is as we move forward， we will explore more of these motion models and observation models。

For different examples and problems。But it is more convenient to talk about a class of problems and an algorithm that can be applied to a class of problems。

If the class of motion models and observation models are linear with additive noise。

Then we can talk about。The column filter。 Then that's the algorithm or filter that we can apply to a class of problems。

That is scalable， because then as soon as that problem fits into that category， we know what's the。

Mettter to use to solve。So it's a matter of efficiency and organizing our methods for different problems。

And of course， this is a part of your specific knowledge， as。An engineer。When you face a problem。

 you can decide what to use and you're familiar with that too。So again， this is a summary。

We have a stream of observations， and。Motion data or action data。

 we have a known model likelihood and a transition model。

We want to estimate the state of the dynamical system。Which is the posterior or belief。Over X。

And you could put it an algorithm， the literal。Implementation of that， as we pointed out。

 is the mark of localization in that circular world that you're implementing。So today。

 we want to talk about a neo class of problems。Now， the model is no longer。Linear。

Which happens to be a lot of time for a lot of interesting problems we want to solve。

So the process model can be。So， instead of。F X， K。-1 plus B U。By the way， this F and B。

 they can be time varying。But， they're linear。Theres no， it can be a linear time varying system。

 that's also。Allow it。 You just have a different F And B matrix。Or Im mixing up should be F And G。

 Or sometimes people use A And B。 It doesn't matter。So it's not like that。 It's just。

Whatever linear combination of xing U。And when I say linear， if it's linear。If y equals F of x。

 if it's a linear map。You can write it as this， right。Or， in other words。Alpha。Y 1 plus meta。

Y 2 equals f of alpha x 1 plus beta x 2。This is a property of a linear map。 If it's nonlinear。

 you're not gonna。Have this structure carried over to the output。Which makes it in general。

 difficult to know what to expect。Okay，And but depending where you are in the domain。

 the behavior of the linear model can change as well。Which makes it super challenge。

 It depends on your operating point。If your robot is moving fast， you might get a different behavior。

 If your robot is moving slow or turning， you might get a different behavior then。

You can expect different level of accuracy and performance from your algorithm， based on your。

Mod of operation。So the process model is nonlinear。 The measurement model is also nonlinear。

A nice case still is that when the noise is additive。Right。You have a deterministic。

 nonlinear model with additive noise。Same for the measurement model。

A more general case that also includes this additive noise is when the noise is also multiplicative。

You cannot decooule the process plus some noisester。 Maybe it's somehow mixed up into nonlinearities。

For example， you have a。Log or cosine。 And that somehow noises。Mixed up here， right。

It's not decoupled from the entire process， it's somewhere inside。But this， of course。

 includes the additive part as well， okay。So in this case， your nonlinear process is a function of。

Two vectors，1 is the state。1 is the noise。It's like a multivariate function。

 But all of these can be vectors。 They' are not the scalrs。

So that's what we mean when we talk about non nonlinearity。Is this process is still Markov。

You're nodding somebody raising hand。Maybe yes， because we don't have any power。

Time states in the market。Partly true。 You're saying yes， because。

We only need the state from the previous time of step。 What about the noise distribution。

 Does it matter。What if the noise correlates everything with the。Origin， initial time。

Its the fact that they only。死定。The correct time。So you rely， you're relying on the notation。

 but the notation can be misleading because。Maybe this comes from a distribution that relates all of them。

 So it's a colored noise。 that means。It does have auto correlation。Okay。So， yes。Because。Yes。

 that's true that we rely on the previous time in step x k minus1。

But if you remember last time we said a process can be linear is called Markov。 It's。

 if it's excited by。😊，A white noise。So the noise needs to be 0 mean white noise damage means it doesn't have any other correlation。

 okay。Otherwise， because of the noise。You do track the history。As you move forward。

 everything is getting correlated， okay。The same thing was in the。Yes。

 that's true for linear cases as well， right？So the Markovian part is not about linearity or nonlinearity。

But it is， it is no longer linear Gaussian or Gaus Markov， because。We you start with a Gaussian。

 but it is not linear。It doesn't。Unless you have a special way to， exactly。

Have the transformed distribution on the other side， right， And it happens to be Gaussian。

 Even won you cannot say that that's Gaus's Markov process。So that structure is lost， in a sense。

But it is still memory lesson Markov， because。Of the assumption we put on the noise。Okay。

So one central question that really the main question in this lecture。I have a nonlinear map。

 No nonlinear function， and I。Want to send this， send a probability distribution。From its domain。

To its range。How can I do that？I know how to do this。Let's say for Gaussian distribution。

 And if the model is an a fine model or linear model。Why， because。

That's the problem you're dealing with with assignments and all the questions。And piazza。

 because basically， the Gaussian distribution is completely described by its first two moments。

the covariance is the central moment。But using the characteristic functions of that probability distribution。

 you can prove that。Through an refine map， you can still exactly have the first。Two moments。

And that describes your Gaussian。So it suffices to propagate exactly mean and covariance。

 If you can do that。Then you have the exact propagation。Now， the problem is when the。

 the map is nonlinear。 you go ahead and you want to take the mean and maybe。

rite down the definition of the covariance。 and you expand the terms。

 You end up with nonlinearities that you're not sure what to do， okay。That's what I literally mean。

 You write it down， you try to do it and you get it stuck。 You don't know what to do。

You cannot derive a closed form formula。So that's the problem。嗯。Not a problem for us。

 This is an important problem in physics， too。They maybe in particle physics， for example， they。

 you track distributions。 Maybe you have an nonlinear partial differential equations and。

You want to propagate it over time。 You're not able to do it exactly。 What， what's the solution。

So does this make sense。There's a distribution here。 maybe it's Gaussian。

There is a nonlinear function。F is a mapping from some domain to some range。This non linearity can。

Perhaps makes this distribution to be like this， right。Or maybe make it like this。

Whatever it might be， again， based on different region of domain， this nonlinear function。

We don't talk about one nonlinear model， anything that you can imagine。

So then the output is not something that we can guess， necessarily。So that's the problem。

We're looking for ideas to。Reecttify this problem。Simple ideas that we can still。

Keep the track of this recursive estimation。There are some ideas， linearize it。That's true。

990% of time in engineering， we arrive everything， okay。It's not specific to this class， this topic。

 this area of work。We love to linearize。Everything in engineering。Basically， when you're out of idea。

 linearize it。Okay， that's your default state。You can still get paid。If you do that。

Nobody will complain， just say it was then linear， I linearized it around the operating point。

It sounds good。 And you get paid。Which is that extended common filter。Okay。Sampling from the domain。

Any sort of approximation method， That's true。Basically。

 you can come up with any method that can solve this particular problem。

 Then you can build a filter around it， okay。It's not limited to these three， but these three。

Covers a really wide range of ideas that we have in literature。

There are a couple of more newer ideas。Out of scope of this lecture。

 but I might mention it in the end。So three key ideas related to us。Linearize it。

 How do we linearize。 Well， that's the Taylor's theorem。 If you have an analytic function。

Meaning that your function。Is differentiable。For infinite number of times。

If a function has all its derivative for an infinite number of times。

 you can write down the tail expansion。 That means write down your function。

Around some point that you want。Not necessarily0， can be any point。

Using its derivatives up to some order。When you go higher order， of course， it becomes nonlinear。

 But if you only keep the first part， that's the linear part。 the first derivative。Okay。

That's the linearization。The function should be more。我这个比一下。Well。

 the only condition for under function is that it needs to be analytic。

 That means its derivatives must exist， so it must be differentiable。

Not in the modern sense of deep learning。It was a tweet that it used to be that。

Differentiability mean that left and right derivatives exist。 You get the same answer。 Now。

 it means that there is there hasn't been a Python package implemented for it。

To give you the derivative。So I don't mean that I mean it in the classical calculus sense。

You write down the definition of the derivative， the left and right limits。Give you the same answer。

 right？This function at。0 is not right， differentiable because the slope as you reach。To this point。

0。Changes suddenly depends on what direction you're arriving， right。They disagree。

 and that's a problem。A differentiable function， no matter what direction you approach that point。

 you get the same answer for the slope。That's a nice property。 That's a smoothness property。

 basically。So we want the functions to be continuous and smooth。Roughly， no sharp edges。Right。

We don't want it to be like this， right。Thiscontiity。Then。So under some regularity conditions。

Nice settings。 you can linearize。The second idea that has been extremely successful is called on center transform。

😊，The name does not mean anything。It's not mean to。Don't think about it。 It doesn't mean anything。

 It's just a random name。It is deterministic sampling。 You generate a set of samples based on。

At the feministic rule， it' not random。And then you use those samples， too。

Approximateated distribution and a Gaussian distribution。And the outside， a range of the function。

The third idea， which is known under the Monte Carlo methods， is based on random sampling。

Using computers， now we can generate。See the random numbers。So you can generate many random。

Numbers or samples in the domain of the function。And then send them through the function to the range。

 the output。And then you have a lot of samples in the range。 And then basically。

 you have built the histogram in the outside， right。So it's a way of generating histogram in depth。

Domain， and then getting another histogram in there。Red。So I have maybe Gaussian。Initially， right？

Send it through。Thissfunction。Maybe the functions give you something like this， right。

And next time it's not Gaussian anymore。 You're dealing with this one， right？And。

 you just keep evolving this。Through this nonlinearity， each time。就诶。When you were saying。

 this be monthly parallel。How libraries laser that computers。The question is。

 is there any problem that the computers cannot generate exactly random numbers。

 You need to pick a seat， and then。They' pseudo random numbers。No， we ignore that。

We just assume that they're random。Or because we get good results in practice。

Then we don't look back。 If we ignore something， and then。Your method doesn't work。

 Obviously you need to go back。And see if that's the root of the problem。 But because。

We get satisfactory results in practice。 We ignored it。啊。大家最近都。前后来。

The bottle is a pretty s this would take part of an observation。So I guess like。

After you have a bottle in why。Are you assuming that your samplingpl is？Why啊。

It like where when you get like a new sample。And we're that sort been set out now like running through the model。

下色灰。Almost like a test set。So your question is。Were assuming that this histogram is。Set of samples。

 It is covering the actual distribution， right， We have enough samples。 and that's true。

 That's a problem。We're going to talk about it soon in part of your filtering。But that's。

 that's an assumption that。Or at least it's a problem in practice。 I we need to make sure。

We have enough sample to cover the space。And you might not know how in practice， okay？

So these three ideas for solving this problem， this challenge， leads to different methods。

When you use linearizations that goes under the name of。Extended comma filter。

So we come up with an idea to solve this problem。 And then we go back and basically fix the original common filter to get a new algorithm。

 right。Excuse me for。So。What do you mean by how do you map believe distribution product noinate or function？

I think for extended common various in To。And the last two methods are。7。They can be non nonlinear。

According to give them maybe the。没什么都题。So the first method should。放。I'm sure your question is。

Why we have this problem here， right。Let me break down your questions。 Let's focus on the first one。

 You're saying that。If we linearize， then why that's a problem， right， Well。

 the problem disappears after we linearize before that， that's a problem。Right。You forgot。

Where we were。First， we had no idea we had anline problem。 Then we linearized。 Then。

 as we will see soon， the problem will disappear。And then we have to do this linearization again and again。

 right。You're right in a sense that we're going to deal with linear models in the end， but。

That's the remedy。 That's not how it was。0月是。变の。没す。How to compute。在继前。In a sense， yes。

 so the question is， when we talk about propagations of a belief through a map。

Are we talking about integration。Yes， that's a really good point。 And that's。How I could start。

The reason I don't start from there because it can get more confusing。

 but generally the problem is that you have a nonlinear function。

And then you haveline or you have a distribution， whatever it is。What you want to do。

You want to calculate this。The moments of this map， right。The first moments。According to that。

 distribution is the integral。Of this。The second moment， you need to raise it to the power。

 the third moment。 Now， if the distribution needs four or five moments to characterize it， right。

You need to take a lot of integrals。There's a good chance。

So the land of the integraltes you can calculate exactly or much bigger。

Much is much smaller than the land of the integral that you cannot evaluate exactly， okay。

So this is the core problem。 Typically， you want to get expected value。

Or moments of nonlinear map with respect to distribution。If you can do that。

 then you can build some algorithms， okay。So in the broader range。Of these ideas。

 if you look at the inference or a lot of machine learning methods， that's what they want to do。

 okay。And Monte Carlo methods is another is a way to approximate these integral。So， yes。

 a lot of problem arises from integration。 We want to integrate。 We don't know how to do it。

Nummerical integration is at the core of a lot of these ideas。Now。

 the integral is apps when it's linear and Gaussian because。We have an exact result。

 You don't see the integrals。So can we understand like this？For example。There's no。

Ineg integral in power during sampling and re sampling。

There is so the question is there's no integral in the sampling methods。There is， I'll point out。

Where you can think about it as integration， Basically， when you have a weighted sum。

 that's an integral。I'll point out。Later。So the linearization method。

 we're going to talk about the extended karma filter first。😊，Extended。Because， well。

 it's the extension of the linear column filter。To。Non nonlinear models。

Suppose we have a function that maps from R N to R M。

Not the same number of input and output necessarily。 But， of course， if it's your transition model。

 maps X。K minus-1 to X K。 So the input output dimensions are the same。Okay， but generally。

From R N to R M。If you write down the Tayloror expansion and only keep the linear terms。

So don't keep the higher。Order terms， right。You have higher order tens， drop them。

What you have is the function evaluated at the operating point， let's say a plus basically。

 this is your Jacobbian， right。The Jacobian or the derivative of your function with respect to the variable you want。

Evaluated at that point。So it's no longer variable。 You evaluate the Jacoban。 It's。

 it's a matrix in general。If it's a single variable， of course， it's just the scalar。

If it maps a vector to scalar， you have gradients， right， If it maps from vector to vector。

 then it's a Jacobian。We'll talk more about in optimization again， but。

You've seen these ideas most likely before。 Now， you rearrange this by keeping the variable X， right。

And just keep everything。That is。Not variable。Ultimately， this will give you some vector X 0， right。

X 0 is not variable。Your Jacobubian evaluation is F， and x is the variable。 Now， this is an a。

 When you linearize， so you can always do that。If the function again， is analytic。You get a fine。

 and we know how to propagate。A gas in distribution through an refine fine mat。So。

 the problem is solved。By this method。Just a reminder。

 if it's up in a fine map and you have a Gaussian。You have。This formula。Now， however。

 to evaluate the mean， you don't have to use the linearized version。 You， You could just use the。

Function。But for the covariance， you have no other choice。So really。

 what the reason we linearize it is for the covariance is' not for the mean， because for the mean。

 you can just evaluate the function。That's easy。就 do。All right。

 so let's go back to the column filter algorithm。So we don't have to go through the driverss because we had an algorithm for the linear case。

We're reducing the nonlinear case with a linearization idea。Through the linear case。

 So we're going to modify that algorithm。And then we're going to talk about whether we lose。

It cannot be。That we are approximately and we don't lose anything。There must be some。

Consequences here。So， we linearize。The process。Around the current mean。For the belief。You。

When you think about it in general for multiplicative noise。

 you also need to linearize your process with respect noise because that's another vector that is input。

Okay。If it's additive， of course， we get the identity map。That's a nice case。Right。

So if you have Fx plus w。The partial derivative of this with respect to W。His identity， because。Well。

 this part doesn't depend on Do， right， But if it's inside。So when you see it like this。

 there's no need to panic。 It's just one more Jacobian to calculate。Because， well。

 it's just another input， right。In other words。The Tayloror expansion of the function， F of x and y。

You need to evaluate that for both of them。If you have 10 variables。Keep going， right？

So whatever number of inputs you have， you need to consider all of them。

Whir Jacobubin is already doing that because x is a vector， you could write it for x1， x2， x3。

 and so on。But we want to distinguish the state from noise。

 So that's why we are separating like this。For the sensor model， do the same thing。

Notice the operating point is changed。We do it after。Prediction， potentially。

 you want to linearize your observation model as the as the predicted。State。

That's supposed to be a little better， right。Pick the best linearization point you have at any time。

It is possible to come up with other choices as well。 But these are。

Obous choices you can come up with。Same thing for the observation model。

 You can linearize it with respect to the noise if the noise is multipld。

So let's see how we can modify the algorithm。First step。 So the input is the mean and covariance。

Of the belief at time is step K -1。We need the action and the measurement， as the input。

Use the nonlinear process model to predict the mean。To propagate the covariance。

 use the linearized model。Again， W WK can be identity。If。Noise is。Adddiitive， right。

So you're just going to see Q。Use the predicted mean in line 3。To predict the measurement。

And calculate the innovation。If you remember previously， this was h times mu okay。Right。

 now we're using nonlinear map。Calculate the innovation covariance。S。Again， we can be。Identity。

 if noise， is additive。Carlin Ga。Common gain is。The cross covariance of your predicted state and the measurement times。

In， inverse of the innovation covariance。Think about it for a moment。

 If the noise covariance of your sensor is very large， that means your sensor。Is。What。

Accurate or precise。我个。Theverse covari is called precision matrix for the same reason， right。

 So it's。If the covariance is large， that means your sensor is imprecise。

Because you can have a very good sensor。 Sorry， you have a sensor that。Its very accurate， right。

But as you repeat。This， it has a lot of noise around that。Accurate measurements that you can get。

 That means if you take thousand00 measurements and then take the sample mean。

 it gives you the correct answer。 It's not， let's say， it's not biased， right。However。

 if it's biased and not accurate， because each time that bias will appear in some way。

You you take the sample mean。That won't be a good value to work with。

 So that's why it's very important to compensate the bias of the sensor。A flying or online。

If the sensor is。Emphasize。I mean， in the limits， you can get correct answers from that sensor。

Which you will see， I think in your homework， too， you have an example of that。But because a lot。

 there， there's a lot of uncertainty。When you get one measurement。You are not sure where it is。

 but somewhere within that covariance， eipoid。So the amount of information that you add each time will be reduced。

Inverse of covariance is the precision matrix or the information matrix， large covariance。

Small inverse， right。Small amount of information entering the filter。So this time will be small。

Sorry， this time will be big S inverse will be small， right。Is that correct。It a small， big noise。

Small。Innovation， information。Small innovation information， a small filter gain。

 The filter will not trust that measurement too much。

To correct your predicted state suddenly by big amount。 Ill do it a little by little。 You。

 You will need to collect a lot of observations to gradually see that the filter is。

Howpefully converging to the correct value if your sensor is unbiased。

You don't face any other problem。So you cant make sense of these terms。 They are very intuitive。

Despite their unfriendly。Look。You can give a lot of them， a lot of meaning to them。

So if you have a very good sensor， possibly expensive。Maybe with one or two observations。

 you can quickly convert。So the linear update rule updating the covariances， they're all the same。

 We don't change anything， except H is again， linearized model。

So that will give us the extended columnman filter。If you can implement a linear common filter。

And you have a way to get the Jacobuban of the map。 maybe by hand。

 maybe you need use a symbolic package in Matlab Python， Julia， you don't have to do it by hand。

 or maybe you use automatic differentiation and get it numerically。

There are a lot of packages that can do that for you。Somehow you will get these Jacobbs。

 then you should be able to modify that linear common filter to have an extended common filter。Okay。

So it's no harder than。The previous case， except you need to handle these derivatives， okay。

Analytic formulas for the derivatives， of course， will make it faster。

 If you have a closed form evaluations of these Jacobubbians。 if the model is simple。

 it's very beneficial for real time applications。😊，If it's too complicated。

And still you can get good performance， maybe you can try to use automatic differentiation。

And by the way automatic differentiation in Julia is just one line。

 you import the package and define your functions， and then you get it。It's not。

Something that you might be worried about it， right？There are very nice libraries at this point。

To handle automatic differentiation。I'm actually not sure if Matlab has that， but Python definitely。

Supports that Julia supports us as well。 There are libraries for C++ as well。Sure。

So do you have any questions so far。So we linearize only one time for F right。Good question。 Que is。

 do we linearize one time forever。No， you linearize。

 maybe you linearize to get the formula if it's analytical or close form。

 but every time you start running this loop， you have to evaluate your Jacobubians。Because youre。

Linearization point will change。M K-1 next time that you enter the algorithm is the previous mu K。

So that's a very good point。Reeval。These terms that you see above here， each time。

So you have my example code for this。Problem and also a class of EKF that will basically take these analytical Jacobkuians from you。

 and it will re-evalu at each time inside。Take a look how I implemented that class。It should clarify。

This question。So let's revisit the target tracking example。 There's a 2D target。

We know their own ship position。Fix that the origin。This time we make it a little more realistic。

 The sensor is giving you a range and bearing。😊，The angle， relative to， let's say， forward looking。

And then， range。We do have physical sensors， like radar to get。This sort of measurements。Or camera。

 A camera will give you just the angle， right， You don't have a depth。

 But maybe if it's a depth camera， you get depth and angle。So the state is， again，2D。

Position of the target in the plane。So basically， we're tracking X Y。And。2D plane。Okay。

We need a geometric relationship between the state and the quantity we actually measure。

 the quantity we measure Z。You can think about it as range and angle。The range is， obviously。

The Euclidean。This sense this。Unfriendly notation， I'm using。 I could use it like this， but。It means。

Basically， I mean， x。K1， X， K2。Okay。So take the Euclidean。This sense of your state。

 this will give you R， right， the range。And the angle with respect to the y axis will be that a tangent to。

Okay， so now we have our measurement model that relates the state to predict the measurement。

It is clearly nonlinear。Because of the square。Squared variables， a square root or tangent2。

The prediction is the same。 We do not have a model for how the target is moving。

 So my transition model basically is X， K。Equals x k minus-1。That's it。F is the identity。 G is 0。

There is a noise。 but when you evaluate the mean， the noise is 0 mean， okay。

That's why you get this transition model。So in this particular example。

 the transition model is actually linear。You do not need to change that part。

 but the observation part is nonlinear。 overall leads to an extended column filter still。

 because part of it is nonlinear。You can evaluate the Jacobubian of the measurement model。

It's not very difficult。 You will get this matrix。Again， you can use software。

 You don't have to do it by hand， if you're lazy。Then。It's the same。Old common filter。

 you just update H every time based on where you are。So using range and bearing。

 the filter can actually track a 2D Cartesian coordinates of this target。

 This is a more realistic problem for tracking a single target target。

So look at the example code in MALlab or Python。Let me know if you have any questions I am Piazza。

Let's summarize。So this filter is still very efficient， just like linear commona filter。

You can run it in polynomial time。In terms of your。Measurement and estate dimensionality。

Carman Fieldter typically runs it。At the quadratic rate。Because matrix multiplication is。

For square matrices is cubic。As bad as matrix inversion。Now。

 efficient libraries can bring it down to two point。Three or something， right？But nominal。

Computation complexity at worst is cubic because matrices that we use is H and K are rectangular。

 They're not actually square matrices。Going by the bigger dimension， you will get quadratic cost。

 So common filter can run at a quadratic cost。So， if you have a million。

Variables in your state vector， this will now scale。But if you have 100， sure thats。

 that will be fine， probably。Not optimal， why。Previously， the linear common filter was optimal。

 We said it's the best you get。Even if the noise is not Gaussian。 and if， in fact。

 the noise is Gaussian， that's the optimal filter for linear systems。

Why their theoretical result is lost。It's no longer optimal。Because it's non linear linearized。

 we made an approximation as a result of that approximation。

You cannot claim that we maintain the theoretical results。Is there。It。the。在哪我。The question is。

 is there a way to characterize maybe some bounds or some relationship between the error。

And the filter performance。That's always good to do， if you're approximating。I'm afraid。

 not something that I'm aware of it。Probably because you need to talk talk about a class of particular class of nonlinear models。

If you're claiming for every possible and linear models。That's probably not possible to drive around。

In the invariant kman filtering， we will see that there are some models that are linear， exponential。

 In exponential coordinates， they become linear。So then， then we。Get some of the lost。

Properties back。That is a big motivation， Why to use。That coordinate system。So in general， no。

 it's not optimal。 Or people tell you， my algorithm is subopmal。 That's just a nice way to say。

 it's not optimal。So when you hear suboptimal， converted is not optimal。

Unless they give you a lower bound， right， my algorithm is suboptimal and lower bounded by this error。

Probability of error。I time we stated and today， we stated that a linear home filter is optimal。

Do we show that。We definitely didn't show it in the lecture。That's。

That goes back to the proof of the filter， right。In the sense of minimum minus square error estimator。

 that's the best filter we get。For the class of systems that are for the class of estimators that are first unbiased。

Right， second or linear。So they get best linear unbied est blue。

That follows form a theorem is called Gaus Markov Theorem， which applies to Lisa' squares as well。

And because common filter with linearist scores are the same， that's one way to show it。

We did not go through that。 If you're interested， that's a good conversation to have， maybe。

On Piazza or office hours。But to clarify， the question is。

 how can we show that common filter is optimal linear filter， Then we need to look into proofs for。

The class of estimators that this filter tries to compete with。But the topic is blue。

 best linear unbiased estimator。An unbiased estimator in expectation。Let's say， will。

Converge to some true value to the true value， right。If it's not。It converges to something plus。

Something else。It is obviously biased， right。The unbiased means this is 0。

There are biased estimators that can perform better。So this filter can divert。 That's one problem。

 If your nonlinearities are severe at the current operating point。

 depending on the behavior of your models。The filter can potentially diverge。However。

 in practice for a lot of problem， this works really well。

 despite violating all the theoretical results。So， that is why it's very。Is widely adopted and used。

Because of good performance in practice。But again， there are robustness concerns depending on the particular problem you solve。

So one of them is， for example， a s。You do EKF is landlam with a lot of landmarks。

That's a concern because if you do wrong data association。

To assign a detected landmark to the wrong previously seen landmark， then the filter can diverge。

 You're injecting outliers。Wrong information to the estimator。

And EKF is very brittle with respect to that， because you linearize。It's a filter。 You move on。

 You never look back to correct that， right。You just reccursively linearize and move forward in time。

 and you never go back to correct previous approximations。That's the reason。

There is no chance to go back and correct it。 So when the outlier enters the filter。

 it can lead to divergence。More on that， then。Slam。还是非常好。Yeah。

 because your function can be maybe like this， right， It's not too bad。But if it's like this。Your。

Slope changes widely as you move a little bit， right， basically。Think about it this way。

For a small change in the input。What is the deelta the change in the output， If it's small to small。

That's good。Okay。If it's deelta in the input is a small， you perrb the function a little bit。

 the output changes a lot， that's concerning。In controlled theory， that's the topic of a stability。

Okay。Robustness means that these changes are for the bounded input。

The deelta in the input If it's bounded， the output is also bounded。If， it won't go to infinity。

 again in control theory， you call it robustness。You are sure that your system won't blow up。

For some regions that you make a delta change in the input， and then suddenly。The system breaks down。

 right， That's robustness。 We are talking about more related to the stability。

Because if the delta in the output is large， it will not。 The linear model is unable to。

Capture the behavior of your model。It's not sufficient。 So that then。You can expect results won't be。

Satisfactory， right？Does that answer your。Question。

Linear model with larger slope and small change in the input will give you。Podenttiialally。

Large variation， right。When the slope is becoming vertical。So why is that？第三单。Oh。

 why that causes a problem？Okay， so the reason。Is because。

The slope here maybe is some line like this。Right。You move a little bit， right。And。

This is not a good。Now， suddenly， maybe the line is like this， right。

The deelta in the X direction is a small， but the deelta， the change in the slope in the y direction。

 is very large。电话。Sorry， can you repeat it。I I think I。You can diverge。いらせた。

Towards the from a region with a high slope tour region with a small slope。

And then the bigger concern is that， well， this is one time we' keep doing it in a loop， right。

You do it a few times。 These approximation errors will get accumulated quickly。

That eventually might lead to divergence。Now， I'm not saying maybe one time the little error or maybe。

You get lucky， right？The accumulation of these nonlinearities and approximations can。

Lead to divergence。诶。So I'm not a controlled theorist， I'm not bothering you with。Delta Epsilom。

Stuff。Keeping it more practical。But this this is also a dual old problem of control。

 This is estimation， but still you can think about those stability and continuity conditions。

For your estimator。Okay， next topic is un centered transfer。Second idea。Well， the idea is。Like this。

 compute a set of samples。We call these samples sigma points。Why， because probably。

 because we use sigma for covariance， these are points generated from the sigma。

Then people decided to call a stigma point。That's my guess。Never verified it。What doesn't matter。

 Some samples， these are deterministic。Well see why。 Then each sample comes with a weight。

And then we transform these。Point through a nonlinear map。Such as G。

Once we have our samples in the range of this linear map。

We approximate the Gaussian distribution using weighted sample mean and weighted sample covariance formulas。

Basically， that's the。Steps we will follow。Now， you could come up with many ways to choose these sigma points。

 This sounds like a very reasonable way， because covariance is。PSD， and。If it's not degenerate。

 you can factorize it using a Cho S heat factorization。

The choice key factorization will give you an upper triangle R matrix L。Sorry。

 a lower triangular matrix L。Right。All the terms above the diagonal are zeros。And L transpose。

 obviously， will be upper triangular。Then we generate， and then we also scale this with some factor。

 We call it L prime。 So N。These are just numbers， right。N is the number of sigma points。

 And Kappa is just a tunenable scalar。So the first stigma point is your mean。

Mean is sounds like an important point to consider。Then we generate。To and。

Samples like this around the mean。We generate a bunch of。Vctorors。

Then we add and subtract them to the mean。 How do we do that using this L。

 the scaled version of L L prime。L I， this is L 1， L2， L I。This is L N。Or L prime。If this is L prime。

These L eyess are the columns of this scaled Choliki。Factor， okay？In the first note I gave you。

 you will see how we can convert the sphere into an ellipse。😊，From points that are on a unit circle。

 you can use this ChS factor to transform them。 This is a equivalent of a rotation and scaling geometrically speaking to an ese from a circle。

 That is why。When we use the columns， we get。Different dimensions in a space。To move。The me。

This is purely motivated by the geometry of。How this covariance is scaling your standard， let's say。

 circular or sphere into an e。And then we have a bunch of weights。 They'll talk about it in a minute。

 in a minute。We valid the sample mean。Using these weights。Related to your question and integral。

 basically， this is the。Expected value of G of x with respects to some probability， right？



![](img/3622f0a958765cda3649ac8fe3ac64d2_1.png)

If you have some samples。

![](img/3622f0a958765cda3649ac8fe3ac64d2_3.png)

You can approximate this using。Awated some。There are many methods for numerical approximation。

If your distribution is Gaussian。You want to do this for any nonlinear map。 Gas Hermit， for example。

 is is a good algorithm。Monte Carlo is another one。 In anyway， you can approximate this using。

Some weights and evaluations of your。放下。This is how numerical you can approximate。

 Now the question is what are the weights right and different algorithms for numerical integration？

You have different ways of finding these weights。So it is a form of integration or calculating expected value。

For the covariance， now we can evaluate a weighted sample covariance for our 2 n plus 1。

 because I starts from 0， right。Up to 2 n， we have  two n plus one samples。 The first one was mean。

We get N。Sigma points by adding the columns of gilesky factor， right。Covariness is n by n。

 You have n columns Add each column to the mean。 you get n sigma points。Also subtract them。

 you get another n sigma points。So you get the covariance as well。

The cleanest way that I like is in the state estimation book， how to get these weights。

There are older references。YouCan be more complicated。 You can have multiple parameters。

 but this is very clean。 You have one parameter。 just set。 and you can always start with two。Right。

 super。Convenient。So， the first weight is。Different from all other weight。

 But notice that this adds up to one。Right。So it's normalized some of old weights。Is one。

So only the first weight is different for the meat。More on on this topic you can read here。

In a textbook。Okay， so。That's how you do it。 So you get another Gaussian distribution propagated through your function。

It is deterministic， because these samples。Follow from。Rules here。It is not random。

 If you repeat this process for the same covariance。And mean you get the same answer， right。

 as you repeat it， it， it， it won't change the solution。 So it is deterministic。

 whereas later we will see in the Monte Carlo， your samples are random。 if you repeat that。

You don't get the same specific values for each term。

 but the hope is if you have the because the law of large numbers， probably get similar。

 more or less similar results overall。that's why it's deterministic。One tricky part。

If the noise is additive。You only need to。So if the noise is。Like this。Or。If the noise is additive。

 you can just do this and center transform forward in a linear part。

And then you add the covariance of。Noise。Later to that way that basically sample covarinance that be calculated。

Because obviously， W is added to the range of this function， right， So it's already。And the range。

However， if the noise is multiplicative。For any reason。

The solution will be a little more complicated。What you need to do， you need to stack them。

Into a bigger vector。And it your N is no longer the dimensionality of the state。

 It's the dimensionality of the state plus noise。So if it's 10 and 10， you get 20， right。

So you need to generate more sigma points because now you're augmenting the state with noise。Now。

 you don't have to literally do this， but you need to think about it that way as a distribution。

So you have X K。W K distributed according to some stacked mean。Which is。M UK K and 0， right。

 Your noise is 0 mean。In this context， it's a white noise。And then， create a block diagonal。

Covariance， okay， so generate your sigma points using this。Augmented system。

Then you send both the noise samples and state samples to the range， and then calculate the。

Sample mean and sample covariance。So， that's the trick when。The noise is multiplicative。However。

 because the algorithm will look very ugly。The algorithm on my slide is for the additive noises。Okay。

When you implement， you will come across this case as well。Example， now we have the range N。

So it's just a coordinates， not the range of bearing example。

 So this is a mapping from polar coordinates to the Cartesian coordinates。 It's a simple example。

So you have。For the point， right， you have rotation angle， and then you have x point。

So x is R cosine of theta。 Y is r times sine theta。We're working with a specific mean and covariance。

 right。We won。 And this is mine and year， basically。Map。And。Thiss orange。Theta distributed。

 according to。Mean and covariance that you see here。So， I want to propagate。This distribution。

From one coordinate。System to another coordinate system。However。

 there is an uncertainty that I need to map。 Otherwise， you would just evaluate this function。

So in the polar coordinate。Aron赛ta。If we were just straight and flatten the angle。

 you look at it as a。There's an access here。The distribution looks like this。 You have， I mean。

And these are sigma points， right。So you can see that we。A particular parameter copper 2。

 which is good for gaussian distributions。The sigma point， what they're doing geometrically。

 they're really getting the corners of this eipoid， which makes sense。

 You don't want to just do the mean。Select a bunch of points around this episode。

Send this shape through the nonlinear map， see what happens the other side。

 and then use that shape to app Gaussian。Previous， in the extended common filter。

 we were just working with the mean。So， that。This。Intuitively， you can expect this method to be。

Please is slightly better。 Sounds like a better idea。So when you map it。

 to the Cartesian coordinates。It is interesting that。

The weight that sample mean is not aligned with the mean that you actually evaluate。

Your function in the E KF， The mean is just the evaluation of the nonlinear。Model。

 which is this point here， however。The uncertainty transplant tells you， don't work with that。

 work with this linearization point， right。So this point。Is basically。

When you evaluate this function using this mean， right。Does that make sense。Plug in 1。

5 and pi over 6 to this R N。Theta function。They'll give you one x and Y。

 This will be this blue point here。Okay。Now， go through the uncented transform process to evaluate this mean。

This guy， right？When you evaluate this。What the sample mean from the uncented transform。

It will give you another point。Just here。Now， this is not too bad。 This is a nice example。

 So they're very close。They can be far。So you get different results as a result of this process of deterministic sampling。

And the way these points around the covariance are distributed， you can also see。

 And this episode is a 95% confidence。Region。ですか。You mean by just for goal。ース。

The question is in AK of why we just evaluate the mean by plugging it into the function。

My question would be， what else do you recommend us to do。What's the alternative？So。一天是发给。嗯。

So we just ask。So you're saying instead of a nonlinear function， use the linearized version。

 so that's even worse。You're replacing the exact nonlinear process model using an approximation。

 At the very least， for the mean， we could use the exact process model， right。It's。

So the part that you're thinking that， well， maybe that's not the best idea， right， That's true。

 But then there will be another algorithm。B K F as is。That's how we we we call it。 right。

 That's how we understand it。It is true that with different ideas， we can improve it。

 That's not necessarily the best way of doing it。So the alternative ideas will lead to different algorithms。

 such as the uncended transform， right。But when you talk about Ek with somebody， that's what。We mean。

Okay。So what's the difference between。B。H once the fresh。These two。So blue。Is here。Blue is。X equals。

R cosine of theta， which is 1。5 times cosines of pi over 6。Y equals r time sine of theta。

Willll give you。Hi， over 6。That will give you the。Blue point， even though I wrote it with red。Right。

The other one。The result of the uned transform。You need to generate sigma points。So the ski factor。

 right？Using the telesky factor。 and then calculate the weight it sample me。

 That will give you this point here。This point is quite directly。Well， you need to。

 I think you're confused about the algorithms。 maybe there is a。

 let's say there's a black box method that will do it for you。 It will give you this point， right。

My point is that it's not the same thing as you calculate this。This part is clear， right。

There is a magic box that will give you this point。This magic。Is on center transform。

It is not the same as evaluating this。 That's my point。 Now。

 you might want to know what's inside the magic box。 That's the uncented transform。

It could be other methods， too。The on central form。点呢。The first signal。Just。Mean， right you。

You got to write， then first one is this point， but also you have all the other points。And then。

 take。The weighted average of all these points， with their corresponding weights。Right。

That will give you this red circle。Yeah， maybe this is a better way to visualize。

Riding their weights。I think this is a better way to show it。所以下这的咋。I you probably label。Is。

What subject。In the meeting。Yes， every black dot here is a sigma point。

 including the mean itself that has gone through the nonlinear map。

Then we have to approximate this Gaussian。Using the sample mean and sample covariance。

 but because they don't have uniform weights， we use the weight that sample mean and sample weight the sample covariance。

Does that make sense I see。And so。Geneenative from。

On the right hand side you've got this ellipse and it's a little bit confusing because we showed that。

We can't move a Gasian through mountain。And so where does the that look？So the question is。

We talked about the fact that we cannot propagate a Gaussian exactly through a nonlinear map。

And that's true。 This is not exact。We're just。Appximating a Gaussian。In the X， Y domain。

 instead of R and theta。As we will see moving forward。Which is， I'm here。

 I'm just saying that 95% confidence eoid damage is if you draw 1 hundred0 samples。

95 of them will be inside this。Eps， right？Now。If you make distribution a little complicated in the sense that the orientation。

 the angle will will cause。Maybe this distribution becomes narrow like this。Now， when you。

Propaate many random samples， which is really the Monte Carlo way of doing it。

 You see this shape here， right， Ban shape。This is the true distribution。

At least the true distribution have something to do with this shape。

We are approximating using the Gaussian。 In fact， it's not like it at all。

That was just the nice example， the first one， right？So it could be that it works well。

 It could be that it's completely。Of in， the sense of the mass is covering a much larger space than the actual distribution。

Yeah。我す。The meaning of the left side plot set through people set to transfer。Yeah。

 the circle red in the middle is the mean that you get out of on center transform。

 which is the beed average of all these black dots， sigma points。Yeah。

There only chance we adding what increasing the sit point will make the gossipian fit more well upon this kind on sheet？

We question， is there any chance that we increase the number of sigma points。

 and then we can model some。Complicate the shapes like this。No， because。

How are you going to model this using an ese， This is just a different shape。

We will see that in the exponential coordinates， we can model this exactly。

This is a still Gaussian in the exponential coordinates。

There is a choice of coordinates that will make it Gauss。 but in general， the answer is no。

We're just doing the best we can with a Gaian， right。You were a little disappointed。

But this was a really good idea。And it still is。It is very efficient。

 So it's not going to solve everything， but。At least it's better than just linearizing。

 using the mean。Progress is incremental。 We cannot solve。You know， everything advanced。

So the point here is that。matrix is2 by2， we can only samplep by two plus one points you get more。

 you can come up with different ideas。That's just the standard way that was， you know， published。

 People documented that。Maybe if youd like to come up with a better idea。

 you can do research and publish that as well。Then we will use it。😊，搞先。Driion we2。他包的。Well。

 because we're in the context of karma filtering， we want to estimate mean and covariance， right。

 It isn't nonlinear karma filtering。 I'm not talking about。

Any inference in the context of carbon and filtering， we want to track mean and covariance。So。

That will give us a Gaussian distribution。Right。So very quickly， but these are really good questions。

 Let's continue them， right， Let's continue the conversation and。Pアza。Great questions。

So that filter is slightly different because now we need to work with sigma points。

 But go through it， with the core of it is that basically you apply and set and transform one time for a prediction。

 right。To send。Your previous belief through the process model。

And then you can generate a new set of sigma points using predicted mean and covariance。

 use that to predict a measurement using the nonlinear measurement model。

 using these new sigma points， calculate innovations using this predicted measurement innovation and cross covariance。

Because were not working with analytical。Driative of the measurement model H。We need to。Also。

 calculate the cross covariance， the cross covariance。Is that term。That you see。

RightIn the probabilistic driverss， there are cross terms。

 This is the cross covariance of the measurement and the state。But this comes for free。

 If you look at the on center transform class。And the UKF class that I implemented。

 you already have it。 This comes for free。 It's just between your state and the measurements。Again。

 the noise is additive。To keep the algorithm。Cling。Calculate the filter gain。

Update rule and covariance update。 Covariance update it looks different， but it's equivalent of。

Previous equations。You can just expand it and see。That you can。Get the other equations from it。Now。

 why。So you can implement this for the same target tracking example。

So the same problem that you apply E KF， you can also apply UF。Because you have the models。

 they're not nonlinear。You get to choose which one， right。Now， for simple problems。

 the performance will be very similar。Check the sample code。This filter is also very efficient。

Its typically within the same computational complexity class as Ike。

 but it is slightly slower because you generate more samples。Just。

 instead of just mean you're working with more number of points。 It is slightly slower。

 but not so much。By a constant factor， maybe。You get better linearization。On top of that。

It's derivative free。 This filter is derivative free。 You do not need to calculate derivatives。

 It's nice。If you implement it。As a generic。Basically， method code。

You can apply to a lot of problems。Without calculating the derivative。 So that's nice。As you same。

 same true。For this filter， too， it's not optimal because that polar coordinate is already is giving it away。

 Imagine more complicated examples what can happen。よ啲。So也 it。Is。More precise。Easier to implement。

bettertter。Yeah。The question is， if UKF potentially is better than EKF。

Why would somebody with the right， in the right mind use Zke。Not in an exact words。Well。

 E KF came first。 You need to look at it in a historical context， first of all。

It wasn't that UK was sitting around and somebody said， well， I have a new idea。 Let's do E。 No。

 people。It was comma filtered， then extended comma filter， then uncented comma filter。Theres enough。

 I don't know， five，10 years， maybe。Difference， so that's why another thing is that E KF is potentially faster。

 Maybe you do have really good。Models， and you can drive the Jacobkuians。

And it can be potentially fast。 but generally， yes， if。You want to make sure this will work better。

 Maybe you can go with UK。In again， in the invariant kman filter。Using the exponential coordinates。

 to see that we can get constant Jacobubians。Well， then it doesn't make sense to use UF。

Maybe it does。 Maybe you can get a slightly better performance， but if you're Jacobians。

After linearization in certain coordinates。Transformation becomes linear。 That a lot looks like。

Linear column filter， right， So that modiv basis is still to use that。

 So that's a class of error estate E KF。 instead of linearizing the model itself directly。

Calculate the error dynamics and then linearize the error， because covariance is。Basically。

 centralized。Moments， right。You may as well centralize it around the true states。

 And when you do that for certain problems， the aerodynamic becomes independent of your estate。

That's a little confusing now。But there is a magical relationship that sometimes you get， and。

That will be the topic of future lectures。 Then still， Ekeev。

Is a really good choice because also it works really well on， on the robot。

There is a UK version of that as well。 I have not implemented that。

But you should be able to do it if you want to。After we talk about it。

So that e cave that I told you we can run it at， let's say 2 kiloHz，2000000 times in one second。

 this loop will repeat on a let's say， legged robot。That's a lot of iterations， right？

And the state includes position， orientation， velocity， gyroscope biases。Acceleroerometer biases。

 foot position。So 3，3，3，9。15，18， at least 18。Or 21 variables。So。

 but I think the short answer is the timing。Right。So a lot of time you get similar results。

 better approximation for nonlinear models。No Jacoban needed， slightly slower。Sampling。

Becomes inefficient。As your state dimension will grow。EKF does not have that problem， right。

So you can read more under linear common filtering。 But what I gave you is basically a digest of。

Both books。And other literatures。So that's it for today。

Next time we will talk about particle filtering。嗯。啊。



![](img/3622f0a958765cda3649ac8fe3ac64d2_5.png)

![](img/3622f0a958765cda3649ac8fe3ac64d2_6.png)

其实我他是。