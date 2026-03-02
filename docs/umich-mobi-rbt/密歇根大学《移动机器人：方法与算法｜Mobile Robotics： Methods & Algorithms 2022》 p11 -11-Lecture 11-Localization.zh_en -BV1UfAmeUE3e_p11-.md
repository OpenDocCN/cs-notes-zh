# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p11 -11-Lecture 11-Localization.zh_en -BV1UfAmeUE3e_p11-

![](img/b33a3b43cb433c1304132c1d5f51b845_0.png)

Hello。We will talk about localization today。 This lecture is。Somewhat the second phase of the course。

 we covered the state estimation topics in the first 10 lectures。We laid out。

Several algorithms that today you will see that we can apply them to a problem。Da。

We will face in robotics， and we will look。 we will look。 We will be looking after。

Methods to solve the problem。 And we we want to discuss。

What we can do and how we can apply the knowledge we gaineded so far to this particular problem。

 This is a topic of localization。

![](img/b33a3b43cb433c1304132c1d5f51b845_2.png)

After that， we will study mapping， and then we will study how to do both of them at the same time。

 simultaneous localization and mapping is。

![](img/b33a3b43cb433c1304132c1d5f51b845_4.png)

So localization is。One of the fundamental problems in robotics。

Because if the robot doesn't know where it is located。In a lot of practical problems， it's almost。

Inefficient or impractical to plan。 Usually there's a need for some sort of。Looccalization。

 whether it's relative， local or global。We need some knowledge of。Robot location to plan and act。

Based on that。For example， if you want to grab an object， you might need to know。

The relative position of that object with respect to that arm that is going to grab it。

If you know it perfectly， then it's hot， then it makes it so much easier to reach out。

 If you know it with some small uncertainty， then still you can plan and grab the object。

 you want to navigate from point A to B。 if you know where you are and you will be able to know where you will be at any time in the future。

😊，You just plan， maybe avoid obstacles and stop when you reach。The destination。

So this is a very important， and。Old problem。 the setup。

In localization it is such that that we are given a map of the environment。We have。

Perfect knowledge of the environment， in some ways。

Based on how you know the environment and how you model it， we might need to use。

Different algorithms。But as a very。Abstract idea， a map。

 which is a representation of surrounding of the robot。 We have that knowledge。

Then we have a sequence of measurements， data。 The robot moves。

 Maybe we collect data from motion of the robot， but also。

 we can collect a sequence of data from cameras， lighter， range finders。Maybe radar， Wifi signals。

 any sort of data that comes sequentially to the robot。 And we might leverage that for。

State estimation。So the overall problem is that we collect some sort of data as we move。

 and we want to solve an inference problem， which is finding the location of the robot。

We're going to look into state estimation algorithms。Which estimation is one aspect of inference。

So typically， you have data。 You want to infer quantity。 state estimation algorithms are。

One way of doing that and very efficient。 Why they're attractive。

 Because we're gonna see this fits well into that base framework formula。Data cons sequentially。

 we can run the filter reccursively。 We don't need to store the entire history。

And we can track the robot location。So it makes them very attractive for a lot of robotics application because data arrives sequentially。

 and we wish to estimate some quantities here， the robot position and heading。😊。

S pose is the combination of position， location。Like X， Y， Z。And heading orientation。

So when we say pose， we mean。Position and orientation。But sometimes we informally say position。

 we mean maybe both。So what are the problems， One problem is。Tracking。

 if we want to know at any time where we are， then we need to track。

Another problem is that if we don't know where we are in the beginning。

Then we have to solve a problem called global localization。Which is a bigger challenge because。

That initial condition that we。Said we assume it's given in， in an algorithm， like a common filter。

Well， that corresponds to where we are initially。 What if we don't know that。

So then that becomes an important problem。That we call it global localization because we want to search globally where we are。

What if we know where we are and we're tracking， and then maybe。For some reason。

 the robot loses the tracking or we lift the robot and put it somewhere else。Or for any reason。

 the algorithm is interrupted。 And then we want to recover again。This is typically called the kidnap。



![](img/b33a3b43cb433c1304132c1d5f51b845_6.png)

Robot problem。So tracking。Global localization。And recover event。

The localization is somehow interrupted。

![](img/b33a3b43cb433c1304132c1d5f51b845_8.png)

Now， this is a setup for the localization problem that we want to talk about， for example， here。



![](img/b33a3b43cb433c1304132c1d5f51b845_10.png)

You see an image of robot dogs。 These are little dogs made by Sunny。 used to be in Rob Cup。

 There was a league They play football and compete。Later， it was replaced by now human a robot。

 It's a little。Human aid robot。Bippedal robot they play。Soer and a team。

And I used to work in a team as an undergrad and later master student in robot Cup first Re。

 robot League， and then。The next generation of this。 But the problem appeared here， right。

 So you want punch of robot move in this field。And they you need to score goals。Now， maybe you。

 theres a lot there are a lot of problems to coordinate。 maybe pass the ball， detectectable。

 track ball， shoot， detect on players。The opposite side， you take your on goal， the other side。

 you don't want to score on goal thats。Obviously not gonna help anybody in the team。So。Now。

 if you make it look to be similar to a human soccer field。It's very difficult， because。

Around the field， there are people。 There are ads。 There are a lot of distractions there are。

Photographers and a lot of people。And then the goals from both sides are identical。There's a net。

 there are white posts。And the field is also symmetric because both sides are similar。

Which is a problem。 If you're getting observations and you're in a symmetrical environment， how how。

The algorithm is supposed to know。Which side is correct， because both sides are correct。

 They agree with the data。So they simplify the problem。 How about we add some landmarks。

With different pattern。

![](img/b33a3b43cb433c1304132c1d5f51b845_12.png)

If the camera can detect them， now we have landmarks with unique Is。You can name it。

 maybe in your map， in your code， you say1，2， three。So on。Now， you need to computer a vision。

Algorithm to detect this post and maybe analyze the color。And then tell you， well， the green is up。

And pink is。In the bottom， and there may be this from what I coded， this is landmark number one。

 And because the number of landmarks are limited， maybe。6， then。You can search exhaustively even。

 that's fine。Which is not scalable。 If you're dealing with thousands of landmarks。

 you need better algorithms。So， you。And you know the dimension mention of the map， right the。

The documents of the competition will tell you the exact dimensions of maybe size of this。The lines。

So you know a layout of the field， you know the size。

So even if you have a monocular camera and you detect lines on the field。

 you can match it to a model。Which is very helpful。So we know the environment and clearly。

 the environment here is in form of。Landmarks， because seeing。Just the playing field in the middle。

 or moving objects。This doesn't seem to be very helpful。

For localizing ourselves with respect to fixed references， landmarks。Okay。For example。

 if you set this point to be your 0，0， right。Then you localize everything with respect to some frames here。

And you know， exact location of。Your landmark， this is X 3， Y 3。Or x1， y1。 it's clear to see。

So you know the map。As long as you can detect these landmarks online。

And you can get some sort of measurement。 for example。

 the robot needs to know that what is the range？And if this is the heading of the robot。

 what is this。Rangnge and angle。 If you can get the range and bearing。That's a lot of information。

And if you somehow can track the robot motion， maybe from legs， maybe from IM U。

Maybe if you don't have any sense or some assumption。

Then this is similar to running prediction correction， prediction correction。

Sounds like we can use any of the filters we started。

So each robot can run a cell localization algorithm in the field。그次라。I we can see one or two。

At the same thing so that do store we of the other landmarks and then。

Do something I can do your hair。就定第二点他在注。your question is。

 if we detect two more than one landmark at the same time， what do we do。

So we can't use all information at the same time。The field of view of the camera is limited。Now。

 this is。Not dependent on the algorithm。 This is the technicality of when you actually deal with a particular setup that is given In this example。

 the camera has a limited field of view。 So it is not possible to see the entire field。At any time。

And the landmark， maybe your algorithm， can detect。This one。Right。Maybe not。 Maybe it's too far。

 So it depends。 Let's say you can。Let's say these days you have a deep neural network and it will nail it down for you。

 right， Ra and bearing of all the landmarks。It's is possible。 You can do it。So then。Rg。

Sequential or batch update that was in the homework。So that was the objective of the homework that。

You had an object， you had two cameras。And you implemented it。2 or three filters。

And the problem was that should we use sequential updates or batch updates。Both are possible。

It's not like any of them is wrong。Btch is better because you're using the entire information at one time to correct the state。

 whereas if you do sequential updates。When you update the first time。

 the second time the linearization point is changed。Depending if that's。

 that's battery like the linearization point or worses， it can go either way。

Whereas batch will help you to。

![](img/b33a3b43cb433c1304132c1d5f51b845_14.png)

Incorporate all the information at once， and then you're done。 Sos ideally， you do batch update。



![](img/b33a3b43cb433c1304132c1d5f51b845_16.png)

So we need to do something like turning our heads to see the other。Maybe in this case。

That 벌어 그 터 내 되는데。Yeah， so you can zoom out， zoom in and out as much as you want， right。

 in a particular s。Maybe I put the dog on a car as well， then。You can go infinite levels up。

Nest that。Mechanism to make it complicated。But， but the idea is that there is a way to get these constraints。

 relative measurements， which is important Thats the part you need to process signals。

There's a signal processing part and you get measurements。

So we are not so much concerned about the signal processing part。

 although we talk about it a little bit。We assume somehow we can get the measurements。And。

Because for different problems， we should look into it how we should do that。Is there any of you？

That mark number。三号。If we want to have the whole return。Equation。

 that means that our network number is going to be more than our。So is there anything want？

The question is， is there minimum number of landmarks for this problem that we should observe。

 And the answer is， yes， you need a minimum number of landmarks to make your state observable。

 That's why we had the observability analysis in the invariant extended common filter lecture When we showed that when you only observe one landmark。

Rain and bearing， X， Y。And your state is position and heading。

 it will not make the orientation observable。So， you need at least two landmarks。At any time， to。

Run a correction that will make your entire state observable。Now， when the filters are nonlinear。

 it's not that trivial to run observability analysis。 You can do local observability analysis。

But that' also very complicated。You need to take the derivative of vector fields。

 lead derivative of these process models and measurement models and look into that。

 and that is only valid locally。It's not globally。 So it's very difficult。

 And that's why you don't see it。A lot in robotics literature， because it's not linear anyway。

Whereas working with the exponential coordinates provided a setup that at least in an ideal case。

 we see if it makes the state observable or not。Because we had。Linear error models。

So it is important。Generally， the more the better。Assuming your。Information processing。Method。

 your state estimator your inference method is consistent and。It will not， you know。

 use data to make it worse。If it's mathematically， sound。Information cannot hurt。 He makes it better。

 Now， in practice， you might have outliers and all sort of things that maybe your algorithm is not designed to deal with that。

So there's a theoretical side and practical side to it。But theoretically， the more information。

The better the estimate。So again， that becomes case by case。 What is your state。

Maybe it's good for 2D。 Maybe the same measurement is not good if you want to estimated 3D pose。

So we need to look into it case by case。So this is the localization setup and problem。

It can be any mobile robot moving maybe in this building or inside a building。

If you can detect landmarks， for example， April tags are very。Famous and popular。

Developed here in Michigan by Professor Ed Olson。Those tags。

You can print them and attach them to the walls。And the camera can detect the tag。

 can decode the I of the tag。 And using a single image can also tell you the relative pose of the landmark。

And there's a lightar tag version of that。Developed here by one of our previous students in Michigan。

 Bruceus Hunk。 He made a lie Liar tag version of that。 You detect that tag in a Liar en3y。

Itll decod it for you。 and it will give you relative pop。

 So if you put a bunch of these tags around the environment， you can。Basically， solve localization。

Now， it is more exciting not to do that， but it is a solution。

 Maybe you want it for maybe a room that you can calibrate or maybe a building for particular service that that solves the problem and。

😊，It's not very invasive。 It can be a good solution， depending on the application。

But adding all those tags on highway。In the entire country， it doesn't sound like a。Compelling idea。

Then people go around， kick the tag。You have to continuously maintain the infrastructure， as well。

Yes。So name four methods to solve this problem before we move on。At least four methods。

I questions somebody。Well， based on what I described。Call for ideas， Me that we learned so far。

 and we can solve this problem。Otherwise， I will end the lecture here because we need to go back and talk about previous topics again。

The linear columnma filter。So A KF extended carmen filter， UKF uncented carmen filter。

You said particleigal filter？Invariant extended column filter。

So at least we have four methods to solve this。Is there any other way。TV。Well yeah。

 all sorts of e caves you can do。😊，Beyond that， is there any other idea？被次标准。Base filter。

 But these are all implementation of base filter。We can also use Lisa squares。

 nonlinear Lisa squares to solve this problem。You can do it offline as a batch， or。

That's not good enough。 We want to do it incrementally。 And that's what we will learn in Islam。

 because in Islam。The filtering is more specific。When we keep the history。And look at it。

In the structure of。Linearized， basically least the squares or even graphical model。

 It possesses a particular structure that is a sparse。And it's interesting。So when we solve this s。

 we look into least the squares formulation。 Now， we know already that you verify in your homeworks that in the linear case。

Linear common filter。And least the squares are the same。

And the linear common filter and map estimation， maximum posterior estimation using two Gaussian also is the same。

 So they are equivalent。 However， at least this square problem is much more general。😊。

Then a column and filtering。And when the problem isn't nonlinear， this equivalentvalence is not so。

Trivial。Because you don't get the same answer。So we could do recursive listed squares。

Or we will learn an idea called incremental smoothing and mapping Iand。

That is also applicable to this problem。So when we learn Islam later。

 that doesn't mean that we cannot solve localization problem。 Of course， we can。

 That's just the special version of。😊，Slap， part of the information map is given。



![](img/b33a3b43cb433c1304132c1d5f51b845_18.png)

So at this point。You are not so much concerned about。The tools we will use。Rather。

 you you're concerned about the problem and the setup。

 and then you choose the right tool to solve the problem。We can talk about。

We extent that kman filter， depending on the motion model。

Which you can separate in your implementation。 The way we implement it in the examples and homework is that you can have an abstraction that you have an extended common filter class that takes the model as the input。

So you can change the model。 It's not tied to a particular Jacobkuian or motion model that you might see。

 This is just an example。Same thing for other methods and filters。Now。

 suppose there is a particular motion model that。Works with X， Y， theta， position and heading。

This is a notation now in probabilistic robotics book。Because the slides match。

Chapter 7 and8 of herbabilistic robotics books。So the motion model is called G。

It's Jacobian capital G。With respect to the state X。Because the noise is。Mulipplicationicative。

 there is a Jacobbian with respect to noise， But because the noise is added to the input and the formulation in the book。

The book is taking the derivative respect to the input。

You get the same answer if you take the derivative with respect to noise。

 because it's assumed it is the input that is noisy。She doesn't make any difference。

This will give you the same thing as。Now， this is。No。

 so you can assume the input is noisy and take the derivative with respect to the input again。

 gives the same result as。The derivative with respect to the noise。Now。

 something you can do clever things like this， maybe your motion nodes。

Covariance is not aesthetic static。 Maybe the faster you move and turn。

 these variances should be higher with some。Up to tuning coefficient coefficients。

So one idea is it is heuristic， it's not coming from。Any particular principle， as far as I know。

 But it is a good idea because you're saying that if I， my variance for。The input。

Which this is for a differential wheel。Robot， it can move forward and it can turn， right。

So the inputs are moving forward and turning。So you need a two by two covariance。

 The idea is that if you move。Faster。The variances will be higher with some linear combination of these two。

So in the prediction step， we calculate the predicted state， and then we update the covariance。Now。

 because we have。Multipicative noise， the Jacobian of the motion model with respect to the noise or the input here。

It's not the identity。 So we get this V。M times V transpose。

This is the same familiar yard column filtering prediction step。

So you don't really need to be worried about the common filtering part。 This， that's the same。

 You need to be worried about。The model part。What is your motion model， What is your sensor。Yeah。

 alpha 1。Al of 4。Punable。Promitives。User defined parameterss。Maybe your vehicle is。You know， big。

 small。Depending how。It moves。 Maybe you need to tune them if you're going to choose this model。

Maybe you choose a constant you get the same answer to， depends on the problem。

 So you need to look into it。

![](img/b33a3b43cb433c1304132c1d5f51b845_20.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_21.png)

Then we also get maybe range and。Bearing。Relative angle measurements。Now。

 after the signal processing part is done， we were left with some geometric constraints。

 and that's the range and relative angle of the landmark。

With respect to where the robot is observing that landmark。So， the measurement is。Range。And。

The notation is phi。Rinja Bering。It's a two by one。Vectctor， the state is a 3 by one vector。Now。

 of course， you know by now that the state is actually on S E2。

 If you're going to implement an invariant extended carbon filter， you will look into S E2。

But if you want to implement a traditional extended common filter or uncented common filter。

 you can work with X Y and heading Theta angle。 We need to be careful to。

Wrap the angle between minus pi and pi whenever you take anglengular differences or adding angles。

You don't want it to。Go beyond that interval。So the Jacobkuan will be。To by。3e。

So that we have this linearized model。And the rest is。Now， I use R here。 So here is Q， right。

 But again， you can use any naming。That you want。So this is the familiar extended common filter correction。

So nothing is different here。So that's it， when you have the measurements and you know how the robot is moving。

You implement your model， and then。Pass it to this filter。And then hopefully， you can localize。

Things you will need。 What are they。Based on your experience so far。

 with the extended commara filter。Imagine you're actually going to implement this under robot。

It cannot be this simple。You mentioned from theor。You you need to read measurements。

 So the timing of these signals and make sure there's no delay when you're reading data。

 or at least the latency is minimal。 That's important。

So you will need to set up a pipeline when you do the data acquisition。Processing them。

 getting the measurement。Until it's within your state estimator loop that you're processing。So。

 that's some。These are some challenges for real time implementations。

 You will need tuning based on the problem。The world， the real world， is too messy that we can。

Dive an exact noise covariance and say that's what's happening exactly in reality。

 That's just not possible。And。You need an initial guess。

That sounds like a deal breaker for the algorithm。If you don't know where you are roughly。

 there is a good chance the algorithm cannot track because。If it's too far。

You are always dealing with an inconsistent situation。

All the innovations that you calculate are just so wrong， they're not adding correct information。好。

So。What question that turning。And selecting the noise， for example。Or these sort of common filters。

If we know the environment in which a two wheel build have like the example of the room but it's going to be operating within。



![](img/b33a3b43cb433c1304132c1d5f51b845_23.png)

Predictable environment in general。When you start going into highly varied or highly dynamic areas。

You were。Noise associated with your action or the noise associated with your motion can't be something where you can test out into the field work before again and then deploy into actual action because。

There。The it's too varied accordingly。There's just too much going on and too much dynamic。

But the environment's very dynamic。In those scenarios。

Are there any methods where adaptive covariance or adaptive methods can be employed？

On top of the common filter or is that something that is commonly used in fieldwork Okay so your question is that if we're going to operate in an environment that is possibly dynamic and will affect these measurements。

 we won't be able to collect data and look at the data offline。

And come up somehow with an estimate of the covariance。

Because we could tune it offline on data and then use it online。But if it's dynamic。

 we need some adaptation。Now， that's a natural idea to adapt these measurement and motion covariances online。

 but it is also very challenging。There is no clean method that I point you to that。

 There are recent work。 So it falls into the research area。

Theres some recent works that they used deep learning to estimate。These covariance。 Now。

 this is an old idea。 It's not new based on motion modes。 We would like to change motion models。

 We would like to tune these parameters online。 The question is， how to do it。

One recent idea is use some computational frameworks like deep learning that can create some sort of memory and。

We can leverage a lot of history to。Correlate what we see with something we've seen in the past。

 Therefore， we infer some covariance that hopefully will be good。Now， there is no guarantee。

These are just。Engineering ideas。So it will be a challenge， and if you're building a product。

 that will be your challenge。As an engineer。

![](img/b33a3b43cb433c1304132c1d5f51b845_25.png)

First thing is based on what you just said。If you're already using deep learning it。



![](img/b33a3b43cb433c1304132c1d5f51b845_27.png)

So， why do。Or like machine learning， so why would you bother using the common film？

Use machine learning itself。对。And then my second question is for the Cal filter right so one drawback at that is that you need at least some reasonable additional gifts。

😊，My question is， is that all？😊，I that you would say implement a。

Particle filter for like initialization， calibration。

 and then to develop an initial gas and then switch to。A tab filter。Ex because it's more。

So your first question is that。If deep learning can recover the covariances。

 maybe deep learning can also recover the post， then what's the point of using a common filter。

I can answer this many ways。But。I guess the the must straightforward is that please do it When it's available。

 we will forget about this， right， So that's。That's the reality。

 because if you come up with algorithm and it's online and people can download on the robot。

 and it just works。Of course， everybody will use that。So somebody has to get it done。

If it only works for your example and it doesn't work for somebody else， that's the problem。

 How much effort we will need to put into get it working。Now。

 it's not impossible because deep learning is also ultimately it'。Another framework for inference。

 it takes data。 it will give you some estimate，In a sense， ist aline， more general versions of this。

It doesn't possess any。You know， nice properties and linear cases that we have because those。

 there are guarantees。But we are dealing with nonlinear cases at this point。However。

 there is an invariant extended common filter that。It does have convergence， guarantee。

Forward the deterministic case of these problems。So then。

There is a problem that we know how to solve it exactly。 And now you're proposing that。

I have a method that potentially can solve it。There's no guarantee， but probably will work。So。

It's a battle。 right， It's an ongoing debate。Now， you can solve visual autotry these days with even self supervisy learning。

It's very helpful for tracking。You can。One application that I like is。

Imagine you have a neural network， something like。Trained encoders on imagenet。Data set。

You're trained on a lot of images， and you have really good features。

 and you find tunening in environment such as this building。😊。

So when you see one or a sequence of images， you know where you are globally。That can create。

A global an indoor GPS for you。Right。That's very attractive。The problem is that， at the moment。

The best we could do is that it's supervised。 So you do need some data collection and label for images that you need。

 You see to know the post。 Then you can solve it， so。

The problem with learning is that it's only attractive and scalable。

If it's generalizable and if it can be done in a selfsvised way。

Besides the moment you can do something like learning。

I can use it within one one of these filters to make it better。So， it's not。

Contrary to what a lot of people think is's not necessarily replacing anything here。

It's just improving your signal processing part。So the way ICD planning is is a signal processing module。

This is after that。 we're dealing with measurements。

 So deep learning can provide measurements and give you better。Signal processing algorithms。

Imagine you can track with relative pose。Well， that solves the problem of emotion model。

And your motion model is somewhat linear in the sense of exponential coordinates because you're just directly getting Delta poles。

It is that constant velocity motion model。So that's good。

And you imagine your global position and indoor also telling you where you are each time。Well。

 my measurements are also directly observing my state。So an invariant extended common filter。

Can easily use。That data， if they're consistent， to give you a very nice estimate with covariance。

 with uncertainty， because getting the uncertainty out of their learning is a problem， too。

There are methods to do it。 But again， it's， it's just too hard。

 You need somebody who spends five years and become an expert。So that person can solve the problem。

Not a good way to train a lot of engineers。 So thats answer to question one。

Just think about it more in a compliment way， not。In a radical way that one will replace the other one。

Usually， that's not the case。The second question， can we run a particle filter？ Yes。

 that's we're going to talk about that。 Can we combine them？ Yes， we can。

You can come up with a lot of ideas in practice to make them better。

 We're talking about the canonical。Basic cases here。So heres an example of comma filter。

 extended columna filter。The visualization that you see is just。

Visualizing contribution of different ten for you。If it helps some people to。C。Each part。

 as an independent。Covariance， so at time is step t minus-1， we are here。Read some。

Covariance at time is step P -1。Then the robot moves to a predicted state。At this location。

 an orientation。And you can see that different terms will contribute differently。 Ultimately。

 we get this。Proroppaated covariance， It is now bigger， because as we move。

The covariance gets only propagated because they're injecting noise from the motion。

So that's the idea of prediction step。The rest is just talking about different tuning of alpha values。

 of course， will give you different。Outputs。So this is what's going on in the prediction step。

 So if you only keep predicting， because there is no rule that says that you can only predict once and then correct once。

It it also depends on the frequency you're observing data。So we can relate to this idea that。

Obviously， if you just keep predicting， you're going get lost at some point。

The uncertainty will become too large at this， at some point。So， it's always good to have。

Measurements for correction at a reasonably high frequency with respect to your desired accuracy。



![](img/b33a3b43cb433c1304132c1d5f51b845_29.png)

Now， when you get observations。There are two cases。 One is。The range variance is。

Large bearing is a small。The range is small， bearing is small， so。We are at a predicted state here。

 with some covariance。This is the real robot。The censor。Now， the nice thing about the sensor is that。

 of course， it's attached to the real robot。So， the relative measurements。Or causal。

 they match the reality。So we get this measurement Z。This is covariance。Predicted covariance。Now。

 when we correct。This is an X y。This is in R and bearing。In the measurement of space。

 we can talk about the innovation and innovation covariance。 Remember， the innovation was。😊。

The difference between。Measurement and predicted measurement。Or in this case， it's nonlinear。So。

 then we get this。Value， because here we have Z hat。And then maybe here， we have Z。And S， now， again。

 you have different contributions from different terms。But ultimately。

 you have an innovation covariance。So the innovation process is。A normal distribution。That 0 mean。

With。The covariance， that is the innovation covariance。 Or you can say my measurement is distributed。

Cented around the predicted measurement。And。With covariance S。Same thing。

So this is what we're dealing with in the correctionist stuff。

 So the larger the this innovation covariance， when you invert it， it will become smaller。

 The smaller is the filter gain。Because the common gain is。Predicted sigma H transpose as inverse。

The first part， this is cross covari between the state and the measurement as we drive it。

In the linear case。And S inverse is the precision or information matrix from the innovation process if。

It's large。 That means the noise in the measurement is large。

We are also very uncertain about where we are。When you invert it， it becomes a small。

 So the filter gains us a small because we do not trust this measurement a lot。

So it takes a long time you correct the state。So a small innovation covariance， a large filter game。



![](img/b33a3b43cb433c1304132c1d5f51b845_31.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_32.png)

So when we run the correction， we。First， we were here。And then we do correction。

 and maybe we move closer to the real robot。That's the idea， right？

This is happening at online at at very reccursively at very usually， very high frequency。



![](img/b33a3b43cb433c1304132c1d5f51b845_34.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_35.png)

Now， let's say the robot that starts from。

![](img/b33a3b43cb433c1304132c1d5f51b845_37.png)

Here。The dash line is the ground truth， it's the true robot。

The solid line with a white circle is our estimate。And at any time。

 the robot might observe some landmarks。 So the robot is moving。 Were predicting。

 and then we are observing landmarks and correcting。 If you visualize this sequence of localization。

You will see something like。This figure。So we're tracking。 we're not solving global localization。

 If roughly we know where we are， we can track the robot。Using an extended column filter。Now。

 if you see enough landmarks， you can。Traed global localizations。 It's not that reckoning。

 It's not relative。But again， knowing where we are roughly。Initially。

It's not that reckoning because we see landmarks that are fixing the environment globally。Right。

 if I know 2，3，3 landmarks， I can triangle it。But this filter is doing that recarsly for us。Right。

The light。Ellippsesar predicted covariance at any time。And the dark ones are， after correction。



![](img/b33a3b43cb433c1304132c1d5f51b845_39.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_40.png)

So this is an example when the sensor。Observations are。



![](img/b33a3b43cb433c1304132c1d5f51b845_42.png)

Accurate， right？It matters what is the sensor noise， covariance。And， I mean。

 it matters not necessarily in your code。 It matters what for the actual sensor。

 It is an accurate hardware that you're using to process。And the algorithm。

 together with the hardware to give you measurements or not， because what you tune。

 you're tuning to match that。Not that whatever you tune， it makes the hardware better。



![](img/b33a3b43cb433c1304132c1d5f51b845_44.png)

If it's less accurate。It's only reasonable that after correction， right， the innovation， again。

 covariance will be larger。 The filter gain will be smaller when the filter again is a smaller。

The corrective covariance is also。Shrinks less， so it remains larger。If you get more measurements。

Then， you can。Maybe you can shrink it to the desired。Accuracy。

 so that goes back to that homework that maybe you have a sensor that is less accurate。

 but it operates at a higher frequency。At a given Delta T。

 And then maybe you can get a better estimate with a consistent algorithm。

There's a turret prayed off。Now， what is the， yeah， of course， we can compare it with ground truth。

If you're designing your algorithm to make sure it's working。In real applications， we don't know。

 of course， the ground truth。 if we knew it。We didn't need this algorithm to begin with。

But when you design your method， you need some sort of benchmark and ground truths to make sure it's working。

Now， what's the。Accuracy， we can target for the localization。What is the right。Accuracy。

 error level for localization。0。I like your optimism， but that does not exist in real world。

Anything more practical for engineers like me？Exactly， it depends on the application。

 You there's no need to。Make a universal localizer。With。Micro precision。Accuracy。

So see the requirements， your application and see what level of accuracy is good。

 Sometimes1 meter error is not too bad。If it's enough to know you're roughly where you are。

Sometimes1 millimeter too much。

![](img/b33a3b43cb433c1304132c1d5f51b845_46.png)

So it depends what you want to do。

![](img/b33a3b43cb433c1304132c1d5f51b845_48.png)

Now we can do the exact same process with UF， the algorithm is exactly what we talked about because the noise multi caative。

Now， you know that we should augment the state。Then， propagate the sigma points。

So the UKF part and centered common filter part is the same。

We just augment the state with zero vectors because noise is0 mean。And when we generate sigma points。

We also sample from the noise by creating a block diagonal covariance of the state and the noise。

These are。Square root。Notation， this is your child key factor。So in the prediction。

 we generate the sigma points， and then we calculate the。

W did sample mean and way did sample covariance？In the correction step。



![](img/b33a3b43cb433c1304132c1d5f51b845_50.png)

第。Generate the sigma point。To predict the measurements。And。Calculate the innovation covariance。

 the cross covariance and run the correction， exactly as we had in the。

Uncented common filter algorithm。So again， this is an application of this filter to this problem。



![](img/b33a3b43cb433c1304132c1d5f51b845_52.png)

Now， for。Seeing what's going on in the uncented common filter。

 we use the idea of the uncented transform for uncertainty propagation。

As opposed to linearization using tailored expansion and analytical method。

We have deterministic samples that are， our sigma points。Depending on that tunable parameters。

 you choose different sigma points based on columns of your scale choiceis V。Factor。

So when you predict， you have basically。U T -1， and your covariance。At time t minus1。

The prediction will give you。And Uvari。As the output of the uncented transform。

With different parameters and different inputs that can take any shape， of course。



![](img/b33a3b43cb433c1304132c1d5f51b845_54.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_55.png)

The correction step。It is also similar。Because we generate sigma points to predict the measurement。

 we can talk about。These samples in。Their measurement is space。Then we can also talk about。

Innovation Covariance， predicted measurement。Maybe the real measurement。



![](img/b33a3b43cb433c1304132c1d5f51b845_57.png)

Then we ran the correction。And hopefully， the covariance。Will get smaller。

And then we get closer to the true popes。 So that's what we're hoping to get here。

So compared to the extended common filter， there are less individual tend to look at because it's a sampling based method。

 You draw this aministic sample， and you get weighted sample。

W did mean and way did sample mean and sample covariance。



![](img/b33a3b43cb433c1304132c1d5f51b845_59.png)

Now， you can solve the same problem。If the setup is basic， probably get the same answer。

 maybe UKF works better in some cases。But a lot of time， we might get similar results。

But it is attractive that it is derivative free。 You don't need to。Derived the Jacobkuians。



![](img/b33a3b43cb433c1304132c1d5f51b845_61.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_62.png)

Now this goes back to the topic of predicting the covariance， of course none of these two can。

Model that exponential， banana shape covariance。Only。We can do it in the exponential coordinates。



![](img/b33a3b43cb433c1304132c1d5f51b845_64.png)

Now， in your homework on localization， it is based on robot operating system。 so you will。

Run a simulated map with some landmarks you will implement。We give you the setup。

 you will fill in the algorithms for extended Carman filter， uncented carman filter。

Invariant extended columnma filter and particleig filter。

So you get to implement all of them and compare them。

So the lesson also is that once you learn a set of tools， you can apply to many problems。

Loalization is one of them。It's very important we're covering it。

But once you do research or work somewhere。See if the problem set up is reasonable for a tool that。

 you know， then probably you can apply that tool。As opposed to mixing the tool with the setup of the problem to come up with a complicated algorithm that is tied to that particular problem。

That makes it confusing because。What are the other options， right？Whereas this way。

 you can just change the tool and see what you get。

 if you're going to talk about part of your filter now。Now， you might expect this to be。

A better choice， than it is。Because。It is multimodal。

 It can track multiple hypothees at the same time。 This is the filter that can solve the global localization problem。

😊，This is just a cartoon with some visualization to see。What's going on with some？

Useful sequence of getting measurements， prediction， running motion prediction and re samplingling。

 So initially， let's say we live in this。😊，One dimensional world。

 just like your circular world example。In your homework。1 or two。Anybody remembers？너body셨어요。

You never looked back。He as soon as you press submit。I'm done with this。I don't blame you。

It gets more fun when we move forward。😊，Always basic。Parts are。Harder。When you go to actual problems。

 it gets fun。But you can have more fun， if you know。

You have fair knowledge of basic ideas because then you can get creative， like somebody was saying。

 can I mix embar cave and Part filter or E cavefe and part filter， yes。

 because he knows both of them。Now， he comes up with an idea that to get best of both for this problem。



![](img/b33a3b43cb433c1304132c1d5f51b845_66.png)

So initially， we don't know where we are， a reasonable choice here to start with a uniform distribution。

So I'm just going to randomly spread the particles。 These are particles。1。Looccalization problem。

So the robot only moves along this。S axis。There are three doors。Somehow。

 the robot can detect the door。There is a sensor that will tell you， there is a door。

And that's our measurement。And we can somehow。Know when the robot moves to have a motion model for that。



![](img/b33a3b43cb433c1304132c1d5f51b845_68.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_69.png)

So let's say first， we get a measurement。 we are next to a door。This will raise。The probability。

 the weight of all the particles。That are near these doors， because when for each particle。

 we go and calculate。The predicted measurement。Which we're assuming there is a way for each particle。

Somehow you predict based on the map that is given to you， where is the door。

Now that can be just a distance， right。You have a map， you just know the distance to the door。

 The sensor is telling you another distance。 you get the delelta。

So this will give you the innovation， right， Z minus E hat。

 And this is a normal distribution with0 mean and sum。Covariance， I don't know。Now。

 one thing is that in common filter， this is the innovation process。 In particle filter， of course。

 we don't calculate that innovation。So， we go with the。Sensor noise。Covariance。

It resembles that that innovation process， but we don't have the full。Innovation covariance。However。

 we continue this。In particle of your filter， it is always better to use noise parameters that are larger than the actual noise values。

Because you want to let the filter to explore a little more， not to collapse into some。

A few single points。So it's a better idea to use larger noise values。

Then you would use for a common filter。In any case。

 we run the update because we receive the measurement that raises the weight for these。Particleles。

 because they're close to a door。And clearly， we cannot distinguish。Three doors。

 They look the same to us。That's why we raised the weight。



![](img/b33a3b43cb433c1304132c1d5f51b845_71.png)

Or all three。Now， in this case， two things can happen if you。Bront prediction， What happens。

The prediction acts like a convolution。 This integral will shift everything。Forward。

 based on your model。Which moves everything。1 Delta forward。 This is here now。And then。

 if you do reseling。Remember if you remember， after reling， we normalize the weights。

We have a fresh start。So all the weights are equal now。But we have more mass at these three points。

To see how the motion is helping us to。Recover the position next time。 Without a motion。

 we would not be able to distinguish。Bth in three doors。



![](img/b33a3b43cb433c1304132c1d5f51b845_73.png)

Now， if we get another correction。What happens at the other two。Very likely， hypothesis。

There is no door。 So the particles are that are located at the other two。

Dense are part of the histogram that we're showing here。They're not going to get higher ratess。

 There's one of them。That is dist stillilled close to a door。

So two observation and one motion in between。Now， help help us to globally recover the。

Location of the robot。 So we just solved the global localization problem。

 We didn't know where the robot is located initially。Now， of course。

 some particles will get higher weight。But， that's nowhere near。The mass that is gathered in。

Near the second door。

![](img/b33a3b43cb433c1304132c1d5f51b845_75.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_76.png)

And then maybe you move again and then do re samplingling and。Now we're tracking the robot。Somehow。

 we need to extract the robot codes。 You might get the sample mean of all particles。

Sometimes it's good。 Sometimes it's not。 Maybe you do clustering。And they work with the。

Clluster that has the higher number of particles。There are different ideas how to extract。

The robot pose。 The simplest one is just take the mean， sample me。



![](img/b33a3b43cb433c1304132c1d5f51b845_78.png)

Counor。请。

![](img/b33a3b43cb433c1304132c1d5f51b845_80.png)

发tion for的3情。Yes，好。错。我会茶。He set up just the one that occurred。

So the question is why every time you get a measurement？Their likelihood model。

 or validity of observation given the state。Is giving us peaks around three doors。

Because there is a data association ambiguity here in this problem， we don't know。The I D for doors。

But， we have them map。The map is known。But we don't know the I for the door。

 If you knew the idea of the door， you're done first time you observed the door。

That's a much nicer problem。You don't know the I D， right。If these two doors。

They're not exactly identical， but let's say they're identical。 How do you know。

This is door number one， that's door number two， especially that you're observing them relatively。

 you don't know your global heading and location。That's why。I say the sensing model is different。

Use this kind of automation which localize。見たりま。Yeah。

 you can think about it like that mark of localization when there was a grid of likelihood， too。

Combined with the belief over your Greek world， right。Or you can think about it this way。Imagine。

 for every point here。I go ahead and evaluate this probability。Which is a。

Normal distribution with mean。And some covariance。This is the output of that Pf。

When you evaluate the probability density function， it will give you a likelihood value。

If you do it for every single point， it will be peaked around。 You get gausss around the doors。

Anywhere else， the distance probably is too large depending on what covariance you choose。

In this case， the variance because it's one dimensional。Does that make sense， yeah。However。

 this is as we talked in。The mark of localization and particle filtering。Lecttures。

The Mark of localization was this just the introduction of the base filter for Gr World。

It is very memory inefficient。We don't want to go ahead and evaluate。

The likelihood for every single point in the state， If this is 2D， this is already too large。

If it's 3D， that's just impossible。You're going to spend all your computation on just evaluating the likelihood model。

 So what we want to do， we want to evaluate it。At places when we place hypothesis。

 and that's what the particleing filter does。 It is memory efficient in the sense that。

It tracks a fixed set of hypothesis， as opposed to evaluating our hypothesis for every grid in the world。



![](img/b33a3b43cb433c1304132c1d5f51b845_82.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_83.png)

This is an example of global localization from Perbabilistic robotics book。



![](img/b33a3b43cb433c1304132c1d5f51b845_85.png)

Imagine this is， I think this is maybe a museum map。It's also。Somewhat symmetric。About this axis。

So initially， they're just populating the map。This is an occupancy Greek map。It's given to us。

This is。Free。This gray area， maybe。Occuped。Unn。Later in the mapping lecture。

 we will learn how to build these maps。 But for now。The map is given。We populate the map。

Maybe uniformly with particles。

![](img/b33a3b43cb433c1304132c1d5f51b845_87.png)

Now， we know that in the motion model phase of the particle filter。

 we sample from the noise and then we evaluate the motion model for each particle。

That will respect the model or the sensor data we have。

 whether that's oometry from encoders from IMU or anything else。But， also。It do it。

 So in a stochastic way， you draw sample from noise。

 and then that generates a hypothesis with the way it moves the particle。 But it don't。

 It doesn't move them。You know， uniformly or too random。There will be centered around。

The way the robot moves。 And that's usually better。 In any case， as the robot moves。

 the particles's veil is spread out to get propagated。Why is the red dot in the previous light？



![](img/b33a3b43cb433c1304132c1d5f51b845_89.png)

In the。

![](img/b33a3b43cb433c1304132c1d5f51b845_91.png)

The red dots are these are。Partticicles。We need to initialize。Somewhat uniformly in the places。

That the robot can be。Now， although you see some here。

 but the robot cannot be here and cannot be here。But it can be here。

So we place hypothesis in three grids of the mouth。Finally we are in the S2。Sage screen how。Right。

 the heading is also possibly they have different headings， right， It's not like。

Here is two days easy。 You can just draw some random heading from between。



![](img/b33a3b43cb433c1304132c1d5f51b845_93.png)

Zero and 360。Minus pi pi。If you want to do it on S3 that you can。

Then you draw noise in the Lee algebra。 Then you take the exponential map。

 and then you integrate based on。The integration rule， which is。Imagine the pose is an S E2。

And you read some。Velocity。From。Which is the body velocity in。

The body frame moving forward and turning。From your real encode。This is in the Lee algebra。

 Then you can say that my motion model is like this。This is what you。W is。Some0 mean。

White Gaussian noise。So there are noise and pertuurrb this。Input。Then you take the exponential map。

This will cause the particle to。Now， in it， if you visualize it， you can get the banana shape。

You can' become curve because you take the exponential。 but in the Le algebra。It's just the vector。

3 vector。You'd have to take the bridge here。Before adding it。That's how we can have this。

Type of models with lead group integrated into the particle field。

 You can do the same thing with IM U。Inside the particle filter。So it's pretty straightforward。

 It's not。You don't seem to agree completely with me。Where is the disagreement？

I'm just thinking about。这都。Yeah。I guess。Complicated when you go to 3D， maybe for 2D。

 I think you can do that。It's not a problem。I think especially for 2D localization in particle of filter。

 that's not a problem。 You can just。Dr our noise for the angle。S， O3。

This is more principle in a sense， it's easier。With IMU。Definitely。

 you want to use the model for the IM U because that the sensor is。Best model with that。

 as far as we know。

![](img/b33a3b43cb433c1304132c1d5f51b845_95.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_96.png)

Now， you might have some proximity sensor of range finders。This is infrared。

Beam that measures time of flight to an obstacle， and it gives you a range， distance to an obstacle。

Now if you collect data。You do get something like this that。Initially， it。

 it behaves like an exponential distribution， roughly。Then there's a Gaussian part。There's also some。

 uniform part。Noise， then you have the maximum range。Distribution。You can talk about。

 as you can read it in Chapter 6， of probabilistic robotics book。

 You can talk about a mixture model for。The range finder sensors， then you can collect data。

 optimize and estimate these parameters。Or you can just use a Gausstian in practice and tune the parameters。

And that's what I would do。If doesn't work， then think about something more complicated。The it works。

Just take your money and be happy。来。So sonar uses sound acoustic signals。与。It's not as accurate as。

Laser light， using light for。Measuring range。And the consequence of that is that the Gaussians you get from ultrasound signals。

 it's more。Spread out。 the distribution is wider。Now， when you can use ultrasound acoustic signals。

 and you cannot use。Laser， can you think of an example。Itwater underwater navigation， perfect。

Because the infrared。Portion of light will get observed very quickly， underwater。

And current sensors that we have， they operate based on the infrared range of the light。

There was some ideas using blue parts of light for underwater lightar。

 but I am not sure if there is there is a sensor that we can purchase。At this point。

But there are ideas people work on how to build new sensors that they work in different environments。

So sonars are very useful for underwater navigation。And can。Contrast to。Laterer。

 sound signals can propagate in any medium。As long as there is a medium。So they work underwater。

What do you you correct。第个第二个。Water just rates for glass。把。

Would the by it or laser sensors will be affected。You mean in what type of environment you said？Fggy。

 foggy， yeah。No， that's， that's a problem。 So if， if you're operating。

 let's say a driving car is operating in a snowy， foggy， rainy。They li up。Measurements can。

Include many artifacts。 They can be reflected。There are a lot of problems。

There was a PhD faces here in Michigan， the work part of the work was about removing outliers caused by snow in lighter measurements for self driving cars。

So there are many challenges， and there are just research problems people work on， but。

It is a problem。 if it's foggy。Liider might not be very good。 camera， obviously。

Cannot detect the long range。What can we do？Rer。Radar can penetrate into。Fuck。But they're different。

 right， It's not like it's going to replace Liar。 radardar points are very sparse。Compared to Liar。

So it makes sense to have radar on self driving cars。 That's why some of them， they do include them。

There are some radars that are ground penetrating radar。

There are some Islam work in that area as well from CMU from Professor Michael Case Group I saw。

Ground penetrating radar Bork and Islam。 That a very interesting tool。



![](img/b33a3b43cb433c1304132c1d5f51b845_98.png)

So lot to explore here。 But we're talking about a simple range find finder， no fuck。No， snow。

 right' inside the museum。People may walk。So there is some randomness。

 But as long as we're not surrounded by people。Corrupting all the measurements。

We have fair amount of robustness to small motions in the environment。Given that， we know the map。

And we reobser a lot of areas again。

![](img/b33a3b43cb433c1304132c1d5f51b845_100.png)

So， we。Initialize。

![](img/b33a3b43cb433c1304132c1d5f51b845_102.png)

The range finder is detecting， maybe with。Hundred，300。

500 beams around the robot with some fixed resolution。 The laser shoots this beam。

 and measures the distance。That this will give us range and bearing because relative to where the sensor is attached on the robot。

 a single beam has a fixed angle relative to。The robot body frame。Sensor frame。

So we measure the range， we know the angle for that beam， then we get range and bearing measurements。

This blue。Right， so some of them they will hit the max range。Some of them will hit。They obstacles。

And some of them will go through。The wall， probably there was a glass。

The laser can go through the glass。Anything transparent。

You're just not going to observe that as as an obstacle。That's the problem too。



![](img/b33a3b43cb433c1304132c1d5f51b845_104.png)

So we get the measurements。 So for every measurement。We need to predict the range。

 How do we predict the range。 So given the particle position。

So every particle is a hypothesis of the robot pole。We do ray tracing。 We know the sensor model。

 We know how many beams we have。NowYou might choose to use all of them or maybe a subset of them。

We ratece in the map that we know until we hit an obstacle。

 This will give me a predicted measurement。For maybe。An actual measurement here。Then I can evaluate。

呃。PD， F， like this。Or the rank。Now， maybe I do this for bearing as well， and multiply them。

Or maybe you make it multi barrier。Some freedom to how to model this。

 So you need you can predict the measurement， and then you do it for all the weights。

 You assume maybe each beam is independent。So that overall， likelihood is the product of all of them。

So now you have a likelihood for the entire。Scan。Then we can run the importance。

Sampling in part of the particle filter， we can add update the weights。

So this is the observation part at this point， the particles do not have similar weights。



![](img/b33a3b43cb433c1304132c1d5f51b845_106.png)

Once we run the reseling。

![](img/b33a3b43cb433c1304132c1d5f51b845_108.png)

The particles with with higher weight will be replicated。



![](img/b33a3b43cb433c1304132c1d5f51b845_110.png)

Then， we move。We observe something again。

![](img/b33a3b43cb433c1304132c1d5f51b845_112.png)

Repeat the process。

![](img/b33a3b43cb433c1304132c1d5f51b845_114.png)

Another reling。

![](img/b33a3b43cb433c1304132c1d5f51b845_116.png)

Now， there is a good chance the robot is here at this point。But maybe he's here， too。

 And there are some other particles around。Now that's not a bad thing。

 You want to keep some particles around。 You don't want to immediately collapse into a single particle。

As long as you can crack your fair amount of mass around where the actual robot is。

 you want some particles to be spread around。So you can solve that kidney robot problem。

 If you move the robot， if some particles are exploring。And they're not around。

Where you where the robots actually is， when you move the robot。

 then maybe those particles can get higher weights and you can recover。

That's how you can solve the kidnap robot problem。By。

Letting some of the some maybe a smaller portion of particles to explore。

And not just be allocated to track the robot。

![](img/b33a3b43cb433c1304132c1d5f51b845_118.png)

So we solve the global localization problem from here， usually we can track。

 the part of your filter will track it for you， which you can switch to a common filter if you want。

But。There is a problem of getting lost again， as well。

Let me see if I understand part of your filters are。Determin deterministic。也后还有。Oh。

 so you mean if we want to recover the robot pose， visually， we can see it。

 but that doesn't mean we actually have a number。Right， we can get the first。

 We have a set of samples。 we can get the Ex me， sample mean。Be careful if it's an angle。

Make sure you wrap it， you can also get sample covariance。Any to。You can get higher moments as well。

If you know what to do with them。可 the。What sort of application we can use higher moments？

I don't know any specific application that you can use higher moments。 that is。

An algorithm that we frequently implement。But I do know that。

There are some recent advancess that we can up to an arbitrary moment with certain classroom nonlinear。

Functions， we can propagate the distribution exactly。Using solving semidefinite programming。Now。

 one idea that we had， it's not done。 But one idea was that what is the generalization of a common filter。

 If you have two moments， if I have a filter that I can up to。10 moments，20 moments。

 whatever you choose， I can do prediction exactly and correction。That's a new filter。

We haven't done it。 I don't know if it will work better or not。But it is a research idea because。

The higher you go， you can capture the nonlinearity。The Gaussianity is is the standard。

 because this is symmetric。No skewness， the third moment will model the skeness。

So if you manage to model higher order moments， then you can capture multimodal distributions as well。

There are some work that you can recover modes of a distribution。

Bu against solving a semi deffinite program。 If you're interested， I can share some。papers with you。

Or maybe you're the one you want' to solve it。Then give me a call。



![](img/b33a3b43cb433c1304132c1d5f51b845_120.png)

So measurements， again， weight update， resembling。

![](img/b33a3b43cb433c1304132c1d5f51b845_122.png)

We're tracking at this point， right， It's localized。



![](img/b33a3b43cb433c1304132c1d5f51b845_124.png)

And。

![](img/b33a3b43cb433c1304132c1d5f51b845_126.png)

Everybody is happy。So this is an algorithm that actually works very well in practice。

 This is the goal the standard of robot localization for this type of setup 2D。It's。

Simple to implement， it works really well in practice。

So that's why party filters I was so popular for。Localization。



![](img/b33a3b43cb433c1304132c1d5f51b845_128.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_129.png)

This robot is kept going。

![](img/b33a3b43cb433c1304132c1d5f51b845_131.png)

So。Sounds like that part of your filter can solve this problem here easily。Now。

 one problem on this robot dog was that。The processor was super weak。

It wasn't like this a smartphone。 This is a monster now。The processor was really， really weak。

 just running a particle filter or running a computer vision algorithm and a particle of filter could easily consume all your resources。

😊，So it wasn't that easy， as easy as just knowing the algorithm and knowing what to do。

 you solved the problem。Today， that's not a problem， because I think。This type of algorithms。

You can easily run it on smartphone。Or a small， embedded computer。

And that's what makes them interesting， because compared to something like deep neural network。

 even if the neural network can solve it， you need a GP。😊，We can run this on small processors。

They're cheap。They reduce the cost of building a product。

So they are still very attractive because you can run them on virtually any computer without demanding computational resources。

What about their goals do you think？What should we do so that we don't score our goals At some point。

 they made the they remove the color of the goals。Every year。

 the problem would become more complicated。So about the time that I was about to leave in the last year or so was that both。

Gals are now white， just like a regular goalpost。For the now robots。Walking platforms。

Then if you had a chance to win because some teams could score on goalss more than you do。

Sometimes that's how you win。And you get the certificate。😊，And that's your achievement。

So there are a lot of ups and downs in life。

![](img/b33a3b43cb433c1304132c1d5f51b845_133.png)

To summarize， so now you should have。You have a question？よ怖。没说完。In the middle of the map。

 which covariance that。first Sig covers is the whole。If your initial covariance is large enough。

 it may work。So the question is， what happens if the initialization is very far from where the robot is。

Can a large initial covariance help to help recovering。Theose。Maybe， maybe not。

The idea is that if the initial covariance is large enough to include the ground truth。

 there is a good chance we can recover。The reason I say maybe because now， maybe this map is a small。



![](img/b33a3b43cb433c1304132c1d5f51b845_135.png)

Maybe it works here。But generally， that's not an idea to recommend because how large do we want to make the covariance。

 Infinite， is not very practical。In larger scale domains outdoor， that's not very practical。

If the initial covariance， however， is tight。M certainly， we won't be able to recover。

 or it takes a long time。To eventually recover， and a lot of estimates along the way are just not correct because the filter is overconfident。

We're just nowhere near the actual。Pose， right？So depending on the situation， we might。

 it might work。

![](img/b33a3b43cb433c1304132c1d5f51b845_137.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_138.png)

So these problems are- now we have discussed properties of particle filters。

It summarizemarizes that as well。 But this problem of 2D localization is low dimensional。

 If you go to 3D and problems that are high higher dimensional。

 it becomes inefficient to draw samples and do these particle propagations as well。

So that is a challenge。 That's why。A lot of。Today is the slam methods in 3D， they use optimization。

Because optimization， just like。That column filtering。It is basically single hypothesis。

 You solve at least of squares。 You get a point estimate。 You get just mean value。

Maybe you do some approximation using the。Hestian and we recovered the covariance as well。

 but that's about it。Just to give you an example， I am you。How many samples do you need to draw？

The inputs you have， you have the noisy acceleration。You have the noisy gyroada。That's already6。

Maybe you have the bias for。Accelation， too。Or maybe you have the bias for gyro 2。That's 12 now。So。

Will this work。It will work， but you should see dependinging on the problem。

 how many particles you need to use until you can solve the problem。

So that some groups in the final projects have this idea to use particle filter and IM U。

Within the context of Islam s， and that's a good idea to explode。Now。

 one idea that I can help you with that is called。And the broader class of inference。

 it's got Mark of chain Monte Carlo。It's not sequential。 One idea for。

Drawing samples more efficiently is called Gis sampling。So what you do。

You make it conditional sampling。 First， maybe you sample from。One block of the input。You fix that。

 and then you sample from the other one。This way， you condition the part of the state and the other part and makes it。

More interesting because you don't have to throw away all the samples。 Gi sampling allows us to。

Keep all the samples。 Otherwise， you have to reject some of the samples in the context of Monte Carlo。

Sampling。YouAgain， what's happening these things？Gifs sampling。

 So this is something that we should discuss outside of the lecture for your project。

It might come handy if you're working on this problem， not related to this localization。So it might。

 the problem might become highly dimensional。 And then as you explore。

You're just wasting a lot of resources for randomly walking around。



![](img/b33a3b43cb433c1304132c1d5f51b845_140.png)

![](img/b33a3b43cb433c1304132c1d5f51b845_141.png)

And if you are dealing with the 2D localization。Please use this。It's pretty good， and。

Usually solves your problem。ニバイム。

![](img/b33a3b43cb433c1304132c1d5f51b845_143.png)

The question is， what do I mean by non parametric filter？Because we track a bunch of samples。

A histogram of the posterior。We do not have a parametric model。Like column filter。

 we have this mean and sigma。 Our goal is to estimate these parameters。In part of your filter。

 there is no such a thing， the relationship between observations， the inputs， data。

 and the outputs are modeled statistically using a set of samples。That's why we call it nonpromonory。

When you have。Some sort of parameters to describe that relationship。Then it's parametric。说的先生活的。

Can you repeat。Question is， don't we use parameters from the measurement model of the particle filters？

It's about the posterior。 It's not about。The parameters， of course。

 you have parameters for a lot of places。It depends how you。Characterize the posterior。Right。

All nonparmetric model models also have parameters。

 Usually we call them hyperparameters because they're not the parameters that are describing the posterior。

 but maybe some aspects like the measurement noise， maybe。So when you hear the term hyperparameter。

 they refer to。That type of parameters。The question just about the。뭐티 Carllo。

Do those relate at all to how we use a particle filter or is that it because a particle filter already uses？

No， Gi sampling is for MCMC。 I am giving you MCMC example codess on canvas。

It's not related to part of your filter。 This is something that I can teach you outside of the。

Lecture is not really the topic of the class。But。I think we can leverage this idea。

In your Part filter slam using IMU。If some groups are going that way。Just the suggestion。

So I'm going to end a lecture。Because that's the end of the time。And。I'll see you。



![](img/b33a3b43cb433c1304132c1d5f51b845_145.png)

Next Tuesday。