# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p02 -02-Lecture 02-Bayes Filters-Kalman Filtering.zh_en -BV1UfAmeUE3e_p2-

This lecture is about base filters， and column filtering。



![](img/c7622a63198f9727bc5ca0932e3d62a6_1.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_2.png)

We're going to start where we left off last time。And that was basically talking about this example to motivate a recursive framework。

 perbabilistic framework to do inference。 Now inference is a much broader idea of using information to inferair equality。

To know the knowledge of a variable or a quantity that you don't directly observe。

 you want to run this inference algorithm。 There are many ways to do inference。

 estimationstimation is one aspect of inference。And in particular， reccursive。

Estimation is very attractive for roboticists， because the data is always sequential。 It's always。

There is a hardware real time system operating。 And I can read data from a camera， maybe。Encodes。

 real encoders of a robot。And I'd like to use data as I collect them to make my knowledge of some variables better。

Now， this this variable state can be anything， but if it's too abstract for you。

Because mathematically， we don't care what the physical quantity of that variable is。

 But if it's too abstract， you can think about the robot position， orientation， velocity。

 maybe some calibration parameters of the system。A lot of time。

 that's our state because we want to do localization and mapping。And solve these tasks。

So that's really the problem。 And the recursive aspects of it is interesting because whatever I did last time。

I use it as my initial knowledge or prior。 Then I get the new information。

 I want to do something to make it better and then move forward in time。

So this reccursative aspects of it is very efficient to run。And a real robot。As opposed to that。

 you can do batch。In France or estimation， maybe you collect all the data from somewhere data set or robot。

 And then you want to process it offline all at once。 As you expect。

 you might get better results because you can see everything。To figure out。

Whatever variable you're after。But that will necessarily be offline or delayed， because。

To improve a variable in the past。To use the knowledge in the future that should be delayed。

 You do not have access to that necessarily at that particular time in the past。

So that's part of the note that I wrote for you。 So historically， there are three。Ideas， one is。

Filtering， one is smoothing。The last one is prediction。

Filtering means that you want to get the knowledge and talk about。

Your variable at this particular time， not the past， not the future。 Right now， you want to know。

 for example， your position。And the filter will track that variable at every time a step。Now。

 sometimes we use filter in。Informal conversation as well to refer to all of them。

 but filter technically means you are only estimating your variable at the current time step。

You do not keep the history。That's why you see base filter， columnman filter， particle filter。

 So that filter。Technically， is referring to that。It is intentional that you see that。

The other part that you might consider a window of time or entire history。As you collect more data。

 maybe you want to go back in time and correct those。 And in fact， you can do that。

 And that's how a lot of modern Islam systems work。That's called a smoothing。

 which is typically an optimization method， smoothing because a filter might jitter because of the noise。

 but a but a smoothing and optimization。Has the chance to give you much smoother results by。

 basically。Looking at the bigger window of time。Of data。

So we are not talking about the smoothing yet。 And so this is all about filtering。

And the prediction aspect of， of course， is you want to predict something。And that's。



![](img/c7622a63198f9727bc5ca0932e3d62a6_4.png)

Use a lot of machine learning， sometimes else in robotics。 You have a model。

 You want to predict something。That you have not seen。 And you have simple examples for this。

 For example， a radio signal that youre receiving and listening that necessarily needs to do some sort of filtering because you don't care what was said 10 seconds ago。

 You want to hear the word right now and then move forward。If you read a text， its。

 it's written hastily。 you can't figure out what to read。

 Maybe you look at the word before and after to figure out。The word that you cannot recognize。

 That's an example of a smoothing and how brain brain can do that。 I throw a ball at you。

 and you want to grab it。 You have to predict the trajectory。So as you look at it， you are thinking。

 where is the next。Location， and you want to move there。

 You don't want to move where the ball is right now because you understand that this is a dynamic situation。

And you need to move to the future。Possible future location of that ball。So we， we are doing that。

 A lot of these algorithms that you see is compatible with how we operate。So for this example。

 you have a robot。 It's a very simplified example to just make the point。

Why this framework is reasonable？There is a camera。 Imagine you have an algorithm。

 image processing algorithm。 It can detect the door is open or not。That's given to us。

To collect observations。 So the robot， look at the environment。 The door is open。

You can obtain a measurement Z。Using the camera。We want to know what is the probability。

And the sensor， obviously， is no easy。It's not going to tell you 100% is open with some error and noise。

 willll tell you it's open， meaning。If you collect  hundred0 measurements of an open door。

 it's not going to tell you it's open  hundred0 times。

 maybe 70 times it will tell you it's open 30 times it's actually wrong， right。

So it's not a certain measurement。 There are uncertainty。

 and that uncertainty is modeled using a probability distribution。

So we want to know what is the probability that the door is open， given a measurement。



![](img/c7622a63198f9727bc5ca0932e3d62a6_6.png)

And。It's important to notice that。You can think about it， of course。

 probability of the door being open， given Z， the measurement or the probability of Z given the door is open。

But they are not the same thing， one is causal， one is diagnostic。The reality is that the door。

 for example， here in this situation is open。That is the reason your camera can observe that the door is open。

 So that's the cause of information。 And it's usually easier to obtain because if you have a sense or you can sense what is happening in reality。

Right， assuming the sensor is。Faithful， correct， sometimes unbiased， and all of that。

Like a temperature sensor， right， And needs to be some degrees here that you can sense that。

It's caused by that。 That's easier to obtain。 That's related to sensing mechatronic aspects of the work and having sensors。

 The diagnostic part is the inference and estimation part， because you cannot directly observe that。

 You need to get the measurement， what you can measure。And then do inference。

 If you cannot measure something。There is a good chance you can do in friends。

Becauseuse you need to get information from somewhere。So the causal information is what we work on。

 It's usually easier to obtain。Based on our sensors。

Then we can use Bayes rule to relate the diagnostic probability， which is the posterior。2。

Their likelihood。This was postereior。This is likelihood。P of Z， given the door is open。

So we can then in what is the probability of the door being open。Now， for that。We do need model。

 It's not。Clear how to evaluate those probabilities。So。Somebody needs to give you the model。

 Let's say there's a manufacturer。 you buy the sensor， and it comes with a catalog。

 It's telling you that's how it works。Right。Now， we're very used to a traditional way of sensing。

 You buy IM U read the data sheet， But you can think about a modern sensor or a camera coming with a chip doing some neural network。

 detecting something， right， And maybe they do some lab tests and tell you what's the uncertainty of that。

 These are。Modern type of sensing that。We expect to CB see some of them cameras coming with a slam and visualometry。

 for example， on board。So it's not at this point very unrealistic to think about that。

So the manufacturer is telling you that the probability of Z。Senses that the door is open。

Given that the door is open it 0。6。The probability of the door being open， and。

When the door is not actually open， it's closed。The sign means not。Which means it's closed。

So the state is a binary variable。 The door can be either closed or open。Only two states， right。

 It's not continuous。That's 0。3。And you can see that likelihood does not need to add up to one。

 That's not necessary。 When you write the base rule， the denominator。



![](img/c7622a63198f9727bc5ca0932e3d62a6_8.png)

This time。Willll make sure everything will add up to one because P of Z， the denominator。

 we talked about this。 And always the sum over。The numerator。Which in this case。

 is easy to calculate because the state is binary。 You only have two situations。In general。

It is extremely difficult to calculate this。Normalizing constant。

So the likelihood does not need to be normalized。You do not need to be worried about that。



![](img/c7622a63198f9727bc5ca0932e3d62a6_10.png)

The prior knowledge。These are related to homeworks that you're working on。

 so hopefully it will clear some of those。When you don't have any information， use noninative。

Prior meaning。The probability of the door being opened or closed。 Both of them are equal。Now。

 it needs to add up to one So 0。5 for each of them。If you have four condition， then。

Pot25 for each of them。If you have 10。1。

![](img/c7622a63198f9727bc5ca0932e3d62a6_12.png)

Now we write down the bee rule。We obtain a measurement that the door。

Our hypothesis is that the door is open。 We， We collect a measurement， right。That indicates。

The door is open。We have our prior。The denominator is the sum over the numerator。

You plug in the numbers。 obtaining a measurement raises the probability that the door is open。

 It will not make it hundred00%。But it's better than 50，50。 Now。

 you' are more certain that the door is open。So that's the idea of a probabilistic framework。

 You work with chances， probabilities。These are not decisions。 These are how。

 what is the chance for probability that the door being opened。Its higher than not being open。

 But that doesn't mean is。Definitely open， right？If it's deterministic， it's going to be 0 on1。

 is's a decision。

![](img/c7622a63198f9727bc5ca0932e3d62a6_14.png)

Now， you will ask probably a natural question that that's great。 One time update。

Probably I'm gonna collect one more， one more after that。How can I combine evidence。

N times arbitrary arbitrary times， right， number of times you。Should be able to do that。

 otherwise the framework is not good enough。That's。What we expect。



![](img/c7622a63198f9727bc5ca0932e3d62a6_16.png)

Because this can works， let's say，30 frames per second。 In one second。

 you want to combine 30 evidence obtained from the sensor。In one hour。A lot of them。



![](img/c7622a63198f9727bc5ca0932e3d62a6_18.png)

So we want to do reccursive。 So that's the idea of recursive。 use that previous probability。

 combine new evidence， get a new probability。

![](img/c7622a63198f9727bc5ca0932e3d62a6_20.png)

A lot of assumptions that you see。R。They are questionable， right， So， first of all。

There's no such a thing that you cannot question assumption just because somebody made an assumption does it make。

 It doesn't make it the absolute truth。But the problem is。

 sometimes you make assumptions so you can carry out some calculations。If you assume nothing。

The terms are so generic that you can't do anything。With different assumptions。

 it you probably can derive different algorithms。Right。

The linear common filter has certain assumptions。 Partic filter has different assumptions。

You can think about both of them as base filter with different setup modeling choices and assumptions。

 they give you different algorithms， right。

![](img/c7622a63198f9727bc5ca0932e3d62a6_22.png)

So one particular assumption that is very important for us is the mark of assumption。

Marov is the name of a mathematician。Who studied these processes， it's named after him。

And the parameter X notice is not dynamic。 This is a simple example later when we do localization in s。

 the state is also dynamic。 It evolves over time。 Here， X is a parameter， meaning。

Its time evolution either is so slow relative to the state。That you can ignore it。

 or it's actually constant。Then we call it a parametermeter。So you we write down the base rule。

 If you write down the base rule。And another notation is that when I write P of， let's say Z。1， to。3。

This means the joint probability of Z1， Z2。And the three。

 iss just a compact way because it can be so many of them。 It's a sequence。 It can be very long。

So it's a joint probability。Each of them is a random variable because it's the same type of measurement。

We just use the same notation， but we index it with time。

So the basee rule tells us right down the likelihood。Here。Keep one of them the end， right。

Leave the all the other variables。 That's Bayes rule with prior condition， if you have。P of x。

Condition and on。Y n。😔，Z， you can write it as。P of Z， given X and Y。P of Y， given y， P of X， given y。

And P of Z given by， so that。Given knowledge is just a stage there。 you can。Keep it。You can prove it。

 not very difficult。To prove this。And。So in particular。

 we keep all the measurements up to time in step n -1 as prior knowledge。 And we work with Z N。

So that's the base rule。 So the mark of assumption says that。Z N， the measurements。Z N。

 the measurement the N is independent of all the previous measurements。 If， you know。

 the value of a state of the parameter。In other words。

 the measurements are conditionally independent， given the knowledge of the state。

That's the assumption。What does it mean， It means that if。You are here， and。You have a camera？

Take a measurement man， take an image。Right。You have a hypothesis where you are。Next time。

 when I'm here and take an image。

![](img/c7622a63198f9727bc5ca0932e3d62a6_24.png)

I also have an hypothesis where I am， right， It is the same position that I'm tracking。

 These two images you can assume they're conditionally independent because you know where you are。



![](img/c7622a63198f9727bc5ca0932e3d62a6_26.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_27.png)

If you don't assume the knowledge of where you are。

 then they are not independent because you can imagine we have overlap。In your images。

Now you might argue that that's not true， they're not even conditionally independent。Maybe。

 but then you have to deal with a more complicated model。Okay。

 so this makes our deris very simple when we make this assumption。



![](img/c7622a63198f9727bc5ca0932e3d62a6_29.png)

你都是体。か。Does this brush fighter？

![](img/c7622a63198f9727bc5ca0932e3d62a6_31.png)

Yeah， the camera was just。You know。Real world example。 This sensor is an abstract idea。

 can be anything， can be Lidar。And other type of sensors we use。Or it can't be just data。

 It doesn't have to be physical。You know， data we read from sensor。



![](img/c7622a63198f9727bc5ca0932e3d62a6_33.png)

To make it。Well it'll formalize， this leads to the mark of property。

 The mark of property states that the future is in the independent of the past。

 given the knowledge of the current time。So your future is independent of the past。

If the present is known。Any stochastic process that satisfies this property is called Markov process。

Processses usually for continuous time， sequence。Is usually。At this great time process。

Technically speaking。So what does it mean， What's the implication of this assumption。

It is a very bold statement that future is independent of the past。 If you know everything about now。

In some sense， it' a strong assumption， because。You can argue that maybe that's just not true。

Can somebody mention why it might not be true？And in like a real world。移到没有。present。Start to。

To measuresure every。You might not know。Everything about present。

 Well what if you know everything about present？Can you think of a problem now？

Everything about the president。The white weather。So if everything from the present is not connected to the past and that's good。

 the assumption is satisfied。We're in good shape。Suppose it is connected。

 and we were making this assumption。That's the。Downside， right。Let me some ideas from chat。

Without knowing everything about。The present also tell you everything about the past。Oh， no。

If you know the value of the。Of a stock today， does it tell you the value of the stock in the entire history。

 Not at all。I guess it doesn't show you any。Pointing in the right direction。Pattern of the past。

It reminds us。Paent recognition and machine learning。Maybe it's the temporal locality。

Can you repeat it， maybe it is a temporal locality that you're talking about。

The the temporal locality of the。Of the of the events。We get a sense of。

We get a sense of temporal locality。From that from this Marov assumption。If not， the entire history。

We get a sense of， I miss that that word， temporal locality。你个申诉。Yeah， temporal temporal locality。

 a sense of value。 Yeah， that's also， I think iss good and relevant。 temporal value now。



![](img/c7622a63198f9727bc5ca0932e3d62a6_35.png)

I'm going to。Explain it this way。 You can think about it。 Maybe you come up。 This is like。

 this is on a philosophical level， but also is's practical。First of all， technically。

 Markov processes are called。Memory less。Systems。These are called memory less systems。

The fact that you forget the past。And rely on all the knowledge from。The present now。

 because that means that there is no memory。Now， you can have different orders of marketer assumption。

 You can have second order， third order， n order， that means。Not just now。

 maybe you consider the last steps， the last three。But eventually， you forget after some time。

 So that's， that makes these systems memory less。😊，That's not how we operate。

 Biological systems operate。 We have memory。What is the purpose of memory。佢要四啊。Your memory。快啥花式。

Has a stin put byologic ones and zeros and thats its my。😊，That that's a good point。 say。

 can't you say your memory is part of the knowledge in the current state。

 and that's what this assumption is basically telling us。Assume that。 I then you're okay to use them。

 But in reality， it is much more complicated。 the entire history of。Some experience， right。

 It is not accumulated in certain。Quanttiifiable， maybe。Values。嗯。

That you can have a lossless recovery of everything， right， That's just not。How it is。

 But that's a good point。 that justifies this assumption。那。The purpose of memory。Somebodys saying。

 avoid future mistake。Yes， but under the。Positive side is to assist。

Future planning and decision making。RightThe purpose of memory for a system is to make better decisions in the future。

Which is， in some， avoiding mistakes。 But it's more than that。 You want to plan for。

Being in a better state， in some sense， whatever is your objective and task。

 that memory is supposed to assist with that。That's how we use our experience and memory in real life。

 So they lack that aspect， which is the current research going on。 It's not a topic。

 We're gonna talk about it Now。 We do not know what's the natural or canonical way to make systems to add memory to the system。

 There are。😊，Challenges on many levels。Conceptual modeling， the actual implementation。

 How are you going store it on the computer， how are you going access it。

Attractability and a lot of problems。But roughly。Speaking。

 you can think about these computational models like neural network that can' accumulate data and provide some sort of memory for you。

So you can store knowledge and then use it in a much more efficient way online。

So that's one interesting insight。

![](img/c7622a63198f9727bc5ca0932e3d62a6_37.png)

So， that。We move on from that。 So we are working with memoryless systems。These systems do not have。

Memory， we use Markov assumptions。Now， when you do make the mark of assumption。

 when you write your posterior as。Using the bayes rule。Then Z N is， of course， independent of all。

Other variables because x is given。😊，However， it's not independent of all other variables。

If x is not given。So that assumption does not work here because x is not given。But， this is。

This marginal。Likelihood or the evidence does not depend on。X。

 so I define it as a normalizing constant for this step。Did you see it here。

So what were left sounds like we're left with a new。



![](img/c7622a63198f9727bc5ca0932e3d62a6_39.png)

Probability that looks like the posterior is just for the previous time step。

 Then you can repeat this process。 Keep doing it。

![](img/c7622a63198f9727bc5ca0932e3d62a6_41.png)

And then you end up with a lot of normalizing constants， right？

This notation is the same thing as the definition。So what happens because of the markov property。

 you can factorize。All their steps into individual likelihood models。

Given some prior for the parameters。 So you can actually accumulate all this knowledge。

Using this property， it breaks down this scary conditional probability that we do not know what to do with it。

😰，Depends on history into。Product of individual likelihood terms， sensor models。

That is why we make that assumption。

![](img/c7622a63198f9727bc5ca0932e3d62a6_43.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_44.png)

A useful way to think about this process of moving and sensing in this base filter framework is the dynamic Bayesian network。

If you have graphical。Models， knowledge， you should be able to read this。 If not。

 we can have an informal conversation。 So the idea is that for each node in this graph， first of all。

 if it's gray。Like this， this is given， right， I know this。This is also given。If it's。

White here is not shaded。 It's wanted。Now， the idea is that。Given the parent notes。That variable。

 for example， here， this one。If I know these two， it becomes。Conditionally。

 becomes independent of the rest of the graph。This graph is useful because it encodes the conditional independence in our modeling。

 This is a way of modeling probabilistic。Basically， this is a。Pbilistic way of modeling your problem。

So at time of step T-1， I have my action or motion command。And perceptual measurement Z。

Then I have my state x T minus-1。Therefore。X T -1 is independent of the motion command at the next step。

NowYou can relate to that because， this actually matches the causal。嗯。Systems， right。

 and the causal systems， you don't use future commands to move the robot。

 You move the use the command for right now to move your robot。 It affects that particular state。

So all the control systems， the systems they used if they follow this causal principle。So。

 that's relatable。And at any particular time， you basically。Rely on these two variables。 But。

 of course， also the。Knowledge of your previous posterior。Okay。SoWhats the。Direction。

Diction of the arrows are。HowWe move forward in time for the state。

This is a directed graphical model。 You can have undirected graphical models， too。

You can have a equivalentval of this that is undirected。The direction is the causal relationship。

 It is the command that makes。That affects your state。

 the fact that you are at the state ex at this pose。Position， right。It gives you this measurement。

From the environment。And the fact that you are here and this command sends you to the next time step here。

These arrows are the direction of。Cause and effect。Okay。嗯。



![](img/c7622a63198f9727bc5ca0932e3d62a6_46.png)

So each one is a time slice。We're just moving forward in time。



![](img/c7622a63198f9727bc5ca0932e3d62a6_48.png)

Now in the state estimation framework， that we're studying here。We call the state X。

Now of course we can choose any other letter is。It's become very common。

So there's a good chance you read a paper， another book。 They use the same notation。

So the state is X。The measurement observation is Z。 U is usually， it can be measurement。

 but it's usually propriceptive。 It's the motion command or something like wheel encoder data or IM U signals。

😊，It's not。Mes to be measurement from the environment。Like an image or a scan of lighter。

But in general， you can think about this as data。Right。It doesn't have to be like this。

So the goal is to find this posterior， given data， tell me the knowledge of the state。

 That's what we want。The recursive base filter， what it does， we define the belief this is。

The definition of the belief， it is the posterior。Over X T， it's a filtering。

 So we only care about X T and not X1 to T， right。That would make it a smoothing framework because we're working with the entire history。

So the posterior is the probability of X T， given data。All their measurements， all their commands。

We call that belief at time X T， at time T。

![](img/c7622a63198f9727bc5ca0932e3d62a6_50.png)

We write the base rule。Just like before。And we separate Z at time T from the rest of the measurements。



![](img/c7622a63198f9727bc5ca0932e3d62a6_52.png)

And then we have the prior。Frombe rule。

![](img/c7622a63198f9727bc5ca0932e3d62a6_54.png)

We can see that we can apply the mark of assumption to the likelihood， because X。

 T is given that we do not need。Data。The history assumed to be available in the knowledge of the present state。

So that's the mark of assumption。 It simplifies our model。Now。

What is the probability of a state at time T conditioned on。

All the motion commands and all the measurements up to the previous time step。That looks tricky。

Because。Our goal is to arrive at a term that shows a recursive pattern。It gives us the previous。

Time steps calculation， that's our goal， right？That doesn't look appealing to work with。 However。

 you can write this as。P of X give。P of X， given y。You can write this as。

Using marginalization or the law of total probability， you can write this as P of X and Z。Given why。

Right。And then this is， of course， P of x。G Z and y。P of。Z given y， right。

 So write it as a joint of X T。And X T -1。 And then use the chain ruler probability。

To break the joint into two terms。And then you integrate over X T -1。

And this whole thing is basically what you see here， but just。

Wtiding it as if before we integrate out X T -1。So the advantage of writing it that way is that。

You can recognize that。

![](img/c7622a63198f9727bc5ca0932e3d62a6_56.png)

If I know。X at t -1， I do not need again。Observation， so。This will results in this term。

 The probability of transitioning from the state at time X T -1 to the state at time T。

 given the motion command。That's very intuitive。 And that's our motion model。

 That's called a probabilistic motion model。For every configuration and sensors and robots。

 we need to come up with a model， right， but this gives us an abstract idea of a probabilistic motion model。

Now， we're still left with another term。What is probability of x at t minus1 given all the measurements？

After that time。And all the motion commands up to that time， plus。

Motion command at one future time step。It is a causal system， right， It cannot be like that。So。

 we drop。Based on that diagram， we can drop that。Commanander time P。

It will not change in the filtering setup。The location of your robot， time T -1。

 It will not change just because you move the robot faster next time，That's just not possible。Yeah。

It is possible if you record data and you're trying to process that flow all at once。

Because you can look at after and before and make adjustment right。 But in reality。

 in a physical worldd， as， as it's rolling out， that's just not possible。

And this looks very appealing because now you have a likelihood sensor model， emotion model。

And you might recognize this as the belief at time step。T minus bonds that we have accomplished。

What we wanted， we created a recursive pattern here。



![](img/c7622a63198f9727bc5ca0932e3d62a6_58.png)

So。

![](img/c7622a63198f9727bc5ca0932e3d62a6_60.png)

Here。如此。The two is step。

![](img/c7622a63198f9727bc5ca0932e3d62a6_62.png)

嗯。Two steps that we see in the base filter， predict correct。Predict with motion model。

 which is equivalent of taking the expectation of your probabilistic motion model with respect to your previous belief。

There are so many ways to think about this。 You can think about it as the convolution of these two terms。

It's just sending you to making a prediction in the future。Expected value or。

It's just the marginalization of basically xt minus1。Well that corresponds to the prediction step。

 predict， correct。

![](img/c7622a63198f9727bc5ca0932e3d62a6_64.png)

And this is recursive。

![](img/c7622a63198f9727bc5ca0932e3d62a6_66.png)

In the sense that。Each time when I want to predict the belief at the next time of step。

 I use the belief at the previous time of step。I know this day that time is 50-1。

 I know my motion command。I predict， then I go and use basees rule to correct or update。

So the predicted belief is my prior at this point。Now， you might ask。

 what if I don't have motion commands and I cannot predict。Well， that's okay。

 Just use the belief itself。At the previous time， you step as your prior， right。That's okay。

 but this is more general because if you can make predicts， that should make it better， right？

If you know that if you have some velocity commands， you predict that。Half a second from now。

 the robot will be here， right， That's a good prediction and the corrections job will be easier to just correct the deelta error in your prediction。

However， it's okay if you don't have。 and it's also okay to do multiple predictions。

And one correction or one prediction， multiple corrections in for us， in reality。

 that depends on the frequencies your sensors are operating。Maybe for every two predictions。

 you get one correction from your sensor。So there's a lot of flexibility。

The way you want to implement this。This is just a very high level idea。One more。

Remark is that we do not。 We know these models， right， although it's abstract here。

 these are given models。And a practical problem。We exactly know what are these models。 Now。

 when I say we know maybe you the one needs to model it。But。

The model is supposed to be there for it to work。It does not work if you do not have the model。

So hopefully this will clear up。The base。Filter framework。

 This is also the idea of motionbabilistic motion model and probabilistic sensor model。先 then。

Future lectures。We're going to talk about these models and different filters。

 So You're going to see them again and again in different algorithms。



![](img/c7622a63198f9727bc5ca0932e3d62a6_68.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_69.png)

To summarize in。The context of base filter， is three of observations， Z。

And you from time 1 to T are given。Your sensor model and motion model are given。Different names。

Action model， transition model。Measurement model or sensor model。 They mean the same thing。Or。

Sometimes， we call observation model。Thankme thing。Same as measurement。What we want。

 we want this state of a dynamical system。It's not necessarily parameter。 It can evolve over time。

 Its value is not fixed。However， it can， it can be。Fix， that's the special case。

And we want the posterior at each time step。

![](img/c7622a63198f9727bc5ca0932e3d62a6_71.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_72.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_73.png)

Then you can have an algorithm， you can call it base filter。

It tells you that for all state variables predict。And then， correct or update。Now。

 the literal implementation of this。Let's say for localization， it's called Mark of localization。

That is the example you see。The example code that I gave you mat 11 Python， you have 10 cells。

 The robot is moving。 There is a likelihood of sensing。

And then you want to do this prediction and correction。

It's very important to go through it because the loop that you predict is actually very complicated because for every。

 you need to update the probability of every grid in the world。

So this literal implementation is called Markov localization。It's too generic。

 You cannot discretize the whole world。It's super， super memory inefficient。But it's a very good。

 constructive example to expose yourself to。The generic idea of this where you literally work with probability numbers instead of other models。

In your assignment， you have a circular work， right， The robot will。Start from somewhere。

 do a circle， and then come back。So this will work if you're truly working with that simple space environment。

But the reality of robotricization is a 6 degrees of freedom，3，4 position，3，4 orientation。

 These are continuous。Like an airplane or drone can move into space。

You do not want to discretize the world。 You probably want to track。

The particular object that you want to track， that's more efficient。And that's what。

Cman filter and particle filter will do for you。

![](img/c7622a63198f9727bc5ca0932e3d62a6_75.png)

So that generic framework has many realizations， the base filter。

It can give you common filter or information filter。

 It's just a different parameterization of normal distribution that will give you the information filter。

We won't talk about it much， but it's。Hisytorically。

 it was important because it was more efficient to implement it on digital computers。In that sense。

 inverse of covariance that we call information matrix or precision matrix is additive。

So you could just add collect accumulate information like that。 It was very efficient to implement。

 but。These days， I'm not sure。Our computers are for now too good。For something like this。

But it depends on a particular application you might be interested， but for， for。In case。

 we work with comma filter form。Now the extension of that to when the models are nonlinear。

 it will give us the extended column filter， uncented column filter， particleig filter， and so on。

Now， why we get these different models because we make different modeling choices for the probabilities。

 for the motion model， for the sensor models， with different assumptions and models。

 we get different filters。Some of them are linear。 Some of them are nonlinear。 Some of them are。

Unimmodal， Uniimmodal distribution has one mode。A multimodal distribution has multiple modes。

The Gaussian distribution is Uniimmodal。A multimodal distribution is much harder to work with。

 because。Whenver you start， you probably。Working locally with that around that particular mode。

It is difficult to track the whole landscape of multiple。

Hypothesis that that distribution models for you。 Okay， part of your filter can do that。

And we will see how that will help in robot localization。



![](img/c7622a63198f9727bc5ca0932e3d62a6_77.png)

These are the filter as we cover。

![](img/c7622a63198f9727bc5ca0932e3d62a6_79.png)

If you're interested that is there anything beyond this， there is。It's more recent。

 It's more research。 It's not in the curriculum。There are。

Optimization based methods where you work with moments。

 and you can actually propagate up to arbitrary moments through any and linear。Methods， that's。

Certain regularities and conditions。 but you can do that。We're not talking about it。

There's a learning based version of that called normalizing flows。You start from some probability。

 it can model any complicated distribution for you。Through a sequence of nonlinear transformations。

That's more like a data or even version of that。But these， those are very news。

 It's good for doing research in the lab。 These are the standard topics that you want to learn。

For the first time。

![](img/c7622a63198f9727bc5ca0932e3d62a6_81.png)

So the landscape is much scarier。Then this。But you will see what what a broad range of problems we can just solve with these filters。

It will enable us to do so much already。

![](img/c7622a63198f9727bc5ca0932e3d62a6_83.png)

There's a question in chat， are there modes of that distribution？Our sensing modalities。No。

 they are not。 Senensing modalities are。Let's say I have vision。 I have earring。 It can taste。

 They can smell。 I can touch。These are called sensing modalities。Robots can have camera。Encoder。

 Im U。Any other sensors that you can think of it。Because they measure or sense a different mode in a sense。

 that observation is not the same as an image， for example， that you get from an IMU。

The acceleration that you sense。That model that I discussed is related to this is slide the noise。

 What is the noise distribution in your model， That can be Gaussian。 It can be multimodal。

And let's see how。Different one noise assumption， one particular noise assumption will lead to the linear common filter。

So linear， when we talk about linear。I'm using K now for discrete time steps。

 The previous ones were T， but they also， they are also discrete。So when I say linear， I mean。

 in the state of space representation。Let's say， like this。

It's a linear state space representation model， linear system。X is a vector。Right， of any dimension。

 a is your。System matrix。U is the control input。Motion command。

 we assume it's known and deterministic。So， you can be。Different dimension M。

The system can be under actuated， over actuated， fully actuated， whatever it is。

 That's motion command。And B should， obviously， map。From。R M to R N， so you can add them。

So this is what I mean by linear model， right。Any course on automatic control in your undergrad linear systems。

 you should have seen this。And if youve now I shared some links for a state space representation。

 If you have linear algebra knowledge， you still you should be able to follow。

 These are just vector matrix， time difference equations， vector matrix。Multulipplications。Linear。

System。So the observation will be also linear。That means that you have a model for your sensor。

If you know your state using a linear model， you can predict or。Tell you， what's the observation。

So they。Is from。Sensor， this is or why in control system they show。

 that's the feedback loop that you get from。In the control diagram。This part is the model for death。

This can be linear。 This can be now linear。Depends on the sensor and the physics。

HowHow complicated we we are willing to model it。So。Linear dynamics。

Which helps us to make that prediction， predict motion and linear observation model for sensing。

So the this great time random process is called a white noise。If it has this property。

 if it's not autocor。If it does not have correlation with itself across time。明玲。

The only way you get non zero out of this expectation， this is a zero mean。White Gaussian noise。

When you write down the definition of the covariance， because it's zero mean， you only see。

The random variable， not its mean。You only get queue， some。Possibly time varying covariance。

Only if k equals J is delta， chronicrona delta。

![](img/c7622a63198f9727bc5ca0932e3d62a6_85.png)

It means that it only。It's only nonze if J and K are the same。



![](img/c7622a63198f9727bc5ca0932e3d62a6_87.png)

So that means the noise does not have auto correlation。



![](img/c7622a63198f9727bc5ca0932e3d62a6_89.png)

Now， a state of a dynamic system excited by white noise。It's called a discrete time markov process。

 or a mark of sequence。So you have a deterministic model。Linear like that， or。

You can have you here as well or nonlinear， right， The nonlinear version of that model will be。

Like this。 Now， because this is deterministic and known， you can just drop it。It is somewhere there。

 but it's not important。So a deterministic dynamic system does not have noise， right？

Make it a stochastic by adding noise。 But what type of noise， if it's a white noise。

 it makes it a markov sequence if it's discrete time。

So it's a very special type of stochastic process。If it's however linear。

Excited by white Gaussian noise。Its called a Gaus Markov process。

Assuming the initial condition is Gaussian。Because of the linearity。It will remain Gaussian。

 That's how you practiced。What is the fine transformation of a Gaussian distribution， right。

 It will remain Gaussian。That's why we needed that。So， if it's linear。

Or could be a fine because that B times you add some a fine term， right。So it doesn't matter。

So because of the linearity， if the initial noise is Gaussian。

 it it will remain Gaussian because of the whiteness of the noise， it will， it is。Markov。

 because across time， these。Distributions don't get correlated。

There is the memory when you propagate， you're done。

 Next step only depends that the noise at that time step entering the system。

So that's the assumption we're making。This is not， I'm not saying the realities like that， right。

 This is our way of modeling。The problem。我哋睇。Excited。Its adding noise。

 that meanss exciting system with noise， right。You're injecting noise to the system。It a desk。

 I'm exciting to know， iss it vibration， right。We could be heating something。

 an electronic device your heating is。You're adding noise， right。

That's signal that entering in the system will excite the system。

You might remember from undergrad O D E class， that。You have this。Hmogeneous differential equation。

You can add a sign。Excitation， the other side， right。

To make a non homogeneous and excited with some force。To go back and forth， right？

They weren't deterministic。 They weren't a stochastic， right， If these terms become a stochastic。

 it makes it a stochastic differentially equation。More like a grad course on a stochastic system。

You don't usually see it in undergrad。 So this is what I mean。

 But we are working with discrete time systems。 So these are continuous time， differential equations。

We'll see some of it we try to quickly discretize it for you。

So you don't see much of the continuous time models。All right， so linearity and Gaussianity。

Of the noise， together with a Markov assumption， gives us Gas Markov。



![](img/c7622a63198f9727bc5ca0932e3d62a6_91.png)

Process。So the linear common filter assumptions start like this。

The state Xk evolves according to a linear dynamic equation。The input is knownun。

The additive process noise。It is 0， mean。Gapsian noise， meaning it's anchor related。Across time。

And the covariance of the noise is also known。That's the。

Dynamics of the system and linear common filter。 Or when I say column filter， it does mean linear。哎。

Their measurement model is also known。As a linear function of the state variable。Again， the noises。

Additive white， Gaussian noise，0 mean un related。With noncovariance。

This is basically as good as it gets。One is step more than that。 The noises already。



![](img/c7622a63198f9727bc5ca0932e3d62a6_93.png)

Too complicated。

![](img/c7622a63198f9727bc5ca0932e3d62a6_95.png)

The initial aesthetic is also assumed to be known。 It's a random variable with the known mean and a known covariance is given。

That covariance is the initial uncertainty because it's the scale that describes where what's the uncertainty region for that mean value。

 okay？The other on top of that initial estate and noise tend， all of them are mutually uncorrelated。

 There is no such a thing that your measurement noise is correlated with your motion noise。And。

Initial noises correlated with one of them。None of that， all uncorrelated。

They don't have correlation with with。Their own evolution， which is autocorlation。

They don't also have any cross correlation， so no other correlation， no cross correlation。



![](img/c7622a63198f9727bc5ca0932e3d62a6_97.png)

We get all of that。 We can summarize it。 You can write it in a math form。Initial condition。

Initial covariance， zero mean noise。Noncovariances， and all of them are uncorrelated。



![](img/c7622a63198f9727bc5ca0932e3d62a6_99.png)

Now， if you get all of that。Then you can go ahead and formulate your estimator。

 There are many ways to do that。One popular one is formulate the cost function and try to find the optimal。

Filter for that。And。Well， the very commonman himself is formulated as linear。

Its LQ E linear quadratic estimation。So the classic paper hero is L Q R and L Q E。

 You have linear quadratic regulator for control。 If there's a linear system， what's the feedback。

For the optimal control。Minimizing a quadratic custom， right。

 Then you have linear quadratic estimation， which is the dual problem of that or estimation。

In my note， you see， okay， do we have the all noise noise assumptions form joint probabilities of X T。

 X T -1。Use the marginalization rule of。Gauussians， you get your prediction model。

Write down the joint distribution of your state and the measurement do the conditioning。

 again you have the formula for that。That will give you the corrections。That's much simpler。

So the cycle goes like this， state and measurement prediction。Or time updates。

Then you have a state update or correction。That's where you use the measurement from sensor。



![](img/c7622a63198f9727bc5ca0932e3d62a6_101.png)

It's best observed probably in an algorithm because that's actually you will implement。So。

 the product of。That knowledge of math。And formulating assumptions， derivations。

 it will lead to set of equations。 And then we organize them into an algorithm。

Then we look at the algorithm and you can implement it on a computer， digital system。

That's why this algorithm is very important。If you do not need to know where it comes from。

 you can still use it。Some algorithms maybe use AS star for planning， right but。

Or maybe use RRT for planning， but。Maybe you don't care for now where it comes from。

 but you're happy to use it。 That's the algorithm It works。 Its tested。And survive the test of time。

 This is one of those algorithms。So that's perfectly fine。

 but I encourage you to go through the des as well。So， the filter。It is recursive， remember。

 it's a base filter framework。We call this filter parametric。What's the。

 what's the parametric and nonparmetric， What does it mean。

What is a parametric model and what is a nonparmetric model。哎非。とでさ結。原到司。That's correct。

You're saying parametric model are based on some coefficients or parameterss。 For example。

 the fact that you're saying。嗯。Z equals H X。 Well， H is a parameter， right， It's a model。

 There is a clear。Relationship between input and output of this function。

Pramits rise with some variables。F of X equals。X is squared from4 plus B X plus one， right。



![](img/c7622a63198f9727bc5ca0932e3d62a6_103.png)

It's a polynomial。 It's a parametric model。 If you want to model some。



![](img/c7622a63198f9727bc5ca0932e3d62a6_105.png)

Event or parameter with this polynomial。 your job is to find the value of A and B。

Find the parameters for care feeding， for example。Nonpermetric， There is no。

Such a thing as parameter。 the relationship between input and output， usually is model。

 We are some statistical relationship。Maybe you have。Samples in part of your filter， you will see。

We have a histogram that describes the output。It's not exactly parameterized with a model。

But we do have a histogram that describes it。That's why part of the filter is nonper。Now， here。

 the model is Gaussian， but it is ultimately parameterized with a mean。

 and the posterior is parameterized with a mean mu and a covariance。 These two are parameters。

That we try to reccursively update in this filter。That is why。

All we need to do is to update the mean anchorcovariance as the output。



![](img/c7622a63198f9727bc5ca0932e3d62a6_107.png)

Okay。So the algorithm takes the previous belief parameters， mu and sigma。

And the action and measurement。And it will give you。The belief at the next time is step。

So the next time you pass this belief。As the initial guess， right？

So there is a question that we have queue here as well。Subscript K doesn't mean that Q will change。

 yes。Do we need to change it in practice。It depends， maybe you fix it。Right。

 maybe you pick something and fix it， see if it works。Then we don't bother with changing it。

But generally can be time varying， meaning at every time a step， it can change。

Does this mean that the。叫机。Q is the covariance of the noise。我 that。Well， we don't know。

 You might know it from somewherer， but we don't necessarily know you might tune it。

If there's an actual sensor， you have a data sheet。You might read it from that。

 but there are also a lot of unmoded things in that sensor itself。

So it's not that you do hand calculation exactly。 and then you nail the noise covariance， right。

You probably need to tune it。So historically important unable parameters like Q&R。

But in the probabilistic frame where you can think about it as a noise covariance。

So this a model is's given， right。It's the same question that you tell me。

 how do you know your sensor model is linear， Well， maybe it's not， right。

 That's the model we're working with。So predict the mean。Predict the covariance。

This is your measurement prediction， right， Use the predicted mean for the state and the sensor model to predict the measurement。

Then take the difference between measurement。And the predicted measurement。

 that will give you a very important term called innovation。

Innovation is the amount of novelty entering the filter。

If your model could exactly predict that measurement， right。There is no difference。

 There is no novelty entering the filter。You're good， right。Your prediction is 100% correct。

 matches the sensing。Ptice is not like that， but in an ideal extreme case。

 you see that innovation will be0。Then you can calculate the innovation covariance。

This is what we call the filter gain， or the common gain。Now， we name this， right。

 if you see the derivations， there is no S and K， right， There just giant。Mattrix vector。

Calculations， you just pick some of them and name them。SK。To make it look pretty。

And easier to implement。So the update rule or the correction is a linear update rule。That tells you。

 take the mean， predicted mean plus a filter gain times the innovation， the novelty。

 So the novelty that enters the filter multiplied by gain。

Is the amount that you will change your predicted state here。

That will give you the update of the state。And then you have a formula from again， the I。

 how to update。The covariance based on the filter game。You can use this formula here。

But it's better to use the second one。 This is。This will be numerically stable， because。

You're adding to。Qudratic terms。You won't make your covariance numerically negative， definite。

Because of the error in numerical calculations okay。So that's how you implement the common filter。



![](img/c7622a63198f9727bc5ca0932e3d62a6_109.png)

I have。Done that for you。We got to。The target tracking folder， MatTLb or Python。



![](img/c7622a63198f9727bc5ca0932e3d62a6_111.png)

You see。It won't look good here because this editor won't recognize the code。But。

I have given you a class。That's， this is common filter。 All you need to do。

 you need to define what are these matrices， H， A。Noise parameters。 So basically， you define what。

Whatever the filter expects you to give， initial condition， models。Noise parameters， right？

And then a cycle that will operate。It's fixed for any problem。 That's the same thing。

So different problem will change your model。And take forever now。



![](img/c7622a63198f9727bc5ca0932e3d62a6_113.png)

I give up。So this is the。Class file。 and then this example， K of single target。

This is what I'm gonna show you now。 Okay， so I'll leave it to you to go through the code。

It's a simple code。 It's meant to be educational。

![](img/c7622a63198f9727bc5ca0932e3d62a6_115.png)

But that will help to internalize what we talked about today。



![](img/c7622a63198f9727bc5ca0932e3d62a6_117.png)

So one example， there is a single target moving in a 2D plane。It's a target。 We want to track。

 We have our own ship。Position。That's our origin。 We fix that， right。

 We assume we know our own shape position。Or you can assume it's the stationary at the origin。

We get noisy observations of the target， but we directly observe the2D coordinates X。

 Y of the targets。It's a very simple problem。What we want to do， We want to。

Filter this noisy observation and track the target over time。So what I need is the system matrix。

 the input matrix for my prediction， I need the measurement model H， I need noise covariance。

For the motion model。 and I need noise covariance for the sensor model。

So if you know that these parameterss， then you can go ahead and。Implement your filter。

This is not a good idea to hard code it， right， You implement your filter and then change these as the input。

 because if you hard code it， then you have to。Write the core of the algorithm each time for a new problem。

 too。 That's not a wise way to。Implemented。

![](img/c7622a63198f9727bc5ca0932e3d62a6_119.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_120.png)

So the ground truth is that a smooth red curve。And the common filter output is this black curve that is filtering。

 again， it's very。Simple。Just to warm up。An ideal linear 2D target tracking tracking problem。ok。



![](img/c7622a63198f9727bc5ca0932e3d62a6_122.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_123.png)

How can we make this a little more complicated。 You'll see next time that I'm going to change it to。

嗯。Rang and bearing。That that's become a little more realistic because you're not going to observe X Y location of the target。

But if you have。Let's say， radar。I mean， that's what people do historicallyly。 You have radar。

 Maybe want to track airplanes。Radar will give you maybe range， sometimes range rate。 And then。

 you know， theyre bearing the angle you installed your。

Rang sensing system relative to some fixed coordinates。So you actually get range and bearing。Now。

 if you go about modeling your sensor using that range and bearing， it's a polar coordinates。

If you want to know the Cartesian coordinates it ends up being nonlinear because you have。

Sine and cosine， whatever， right？So then we're going to use that example for the extended column filter and uncented column filter。

So you will see this again。

![](img/c7622a63198f9727bc5ca0932e3d62a6_125.png)

So blue is the origin again。

![](img/c7622a63198f9727bc5ca0932e3d62a6_127.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_128.png)

Can you think of places that common filter is used？For state estimation。Real world。

Estimating high temperatures。estimating。H。Temperatures。Typically， you can estimate any temperature。

 but something a little more exciting， maybe。😊，The pollution the shape se。Seggue。Yeah。

 that's a good one。 Segue。 How do you know your。Orientation， right， You need an observer。

The signals that you collect are very noisy。 So attitude estimation in general。

 if you have a gyroscope， an actualerometer IM U， They use it in airplane as well。

 They use it in cars。😊，You use it in。Seggue and a lot of toys can use it as well。

 your phone has a gyroscope and accelerometer。For the direction and orientation。

 So the problem of estimating the attitude， the orientation in 3D。

That is very interesting and efficiently solved using a common filter observer。 Thats， however。

 it's best solved using a more advanced version of that。

 That's your homework for invariant common filtering。😊，And rockets。Spaceships。

They use it extensively for attitudeitude estimation， again， state estimation。Temperature is good。

 Maybe you are designing a regulator， or some。Air conditioning system， right。

 you want to filter some signals。But there's multiple sensors observed some state。

So that's a very good question。 The question is， if you have multiple sensors。

 can you use them in one filter， Yes， you can。Assuming these sensors are compatible。

 That means that maybe。Its several copies of the same sensor， or maybe。

You have models that somehow they measure the same estate， right， assuming that's the case。

You can run the correction， maybe multiple times。If they are not synced。

You can track the time of stamp and follow the time of stamp。Run whatever you get。

 Maybe it's time to predict， predict。 You get a measurement， run the correction for that sensor。

 You get another measurement。 run the correction。 Maybe you predict again， right。

 The order is not important when you implement。 So what you found， the robot it。呃。It is like that。

Now we have a synced version of it as well， but it's really not necessarily sync。

The prediction and correction， because you just process data as it arrives。Do whatever we want。

 prediction， multiple prediction， multiple correction， multiple senses。So that。You don't need。Now。

 unless you want to show some observability criteria， right。

 to do theoretical analysis and a lot of practical problems。That's not necessary。

 Probably if by experience， you might know those's are good sensors to mix or not。

But related to linear systems， especially if it's linear。

 you can run observability analysis to know that is the state observable。Using。

The measurements we're collecting。If it's not， you won't be able to estimate it。Okay。

So that's the same thing you formed the Grian matrix for observability， check the rank。Right。

If it's full rank， it's observable， if it's not。You need to do something。 That means， you might need。

More measurement at that time。Or that's just to not the right setup。

 So well have an example of that in invari common filtering。



![](img/c7622a63198f9727bc5ca0932e3d62a6_130.png)

So the overview is that under the Gaussian assumption。For the initial estate。

And all noise entering the system。 The carbon filter is your optimal。

Minimum minus square state estimator， Min minus square error state estimator。

So it is optimal in this sense。If you change your optimality criteria。What it might not be。So。

This is the Gaussian case that gives you the optimality。In the sense of minimum minus square error。

If they're not Gasian， however。For the class of linear minimum。Minni square error estimator。

 this is the best you get。You won't be able to get anything better。Okay， this is the。This is blue。

 best linear onbied estimator you can get。But again， in the sense of linear。

Minimum minus square error estimation。 Now， you might wonder。



![](img/c7622a63198f9727bc5ca0932e3d62a6_132.png)

What is。

![](img/c7622a63198f9727bc5ca0932e3d62a6_134.png)

Minimum minus square error。If you don't like it， you can keep your ears。 That's okay。



![](img/c7622a63198f9727bc5ca0932e3d62a6_136.png)

You won't lose anything， if you're curious。Now these are class of estim， very successful。

 widely used。In engineering。What we do， we want to estimate the quantity。This X hat。

 We want to estimate。X， so x hat is an  estimate of x。 X is a true value。 X hat is the estimate。

The way we formulate the problem is that。X had minus x。Is the error。

 The difference between the estimate and the true value， we call it the error。

So x had minus x is squared， that's the error squared。Take the expected value。That's the。

Mean squared error。 Okay， Setic expectation average is over。Different values of the error。

And they minimize that。To get the minimum such a。Mean square error。Right。

For that particular value of x hat estimate。 So the argument of that。

 this quantity will give you minimum minus square error。 However。

 we also conditioned on data because without data。Well， you might make assumptions。

 but generally speaking， you need data to rely on that for making an estimation。

 These are observations， motion commands or whatever。You can collect。So， the solution is。In fact。

So basically， this is the estimator， right， You don't need。Anything more。Now。

 maybe you have a finalr number of。Examples， you turn the integral of the expectation to some。

 and then you run an optimization。To solve this， maybe， if it's linear， you can solve it exactly。

 And that will give you something like common filter for recursive estimation。

If you want to do it in batch， then you can get least squares。Okay。

The common filter analyze the squares in the linear case。Are the same。But however。

 at least the square problem is more general。Common filter is a little more specific。

Style of estimation。Now， the solution of minimum minus squared or is the conditional mean。

 It's interesting that if you can get the conditional。Mean of x with respect to the。

For stereo P of X given Z， that will be your solution。If you can calculate it。Which again。

 we can for common filter， that's what we do。How do we know that？ Well， take the error。

 the objective function， write the necessary condition for optimality。

 That means take the first derivative， set it to be 0。

Find a critical point of the objective function。But the derivative of this is expected value twice of。

The error。The expectation is linear。 The estimate is not random。 The true value is random。

 It goes inside。From here， you learned that。X hat is the conditional mean。

Of x with respect to the posterior distribution。Those are just nice to know。

Extra connection between minimum minus square or estimation and column filtering。In fact。

 this is one way to drive the filter。 You minimize the trace of the covariance。

 That's equivalent of this error term。

![](img/c7622a63198f9727bc5ca0932e3d62a6_138.png)

I leave the questions for Piazza。

![](img/c7622a63198f9727bc5ca0932e3d62a6_140.png)

And。

![](img/c7622a63198f9727bc5ca0932e3d62a6_142.png)

Let's talk about the limitation of the common filter。Well， everything we did， all the assumptions。

 all the modeling。Can be broken in reality， if the model is not nonlinear。

Either process or the measurement model。If the control input is unknown or there are motion modes。

Basically， changes。This filter can break down。 You won't be able to solve the problem。

So then nonlinearity is clear because if it's not linear， you won't get the results we discussed。

 okay。Next time， well。Come up with some remedies， too。Fix that problem。More changes。

 Imagine you're tracking your airplane， and then airplane suddenly goes to the right instead of moving constant velocity。

 Your motion model completely becomes wrong。

![](img/c7622a63198f9727bc5ca0932e3d62a6_144.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_145.png)

You just can't track。And you don't know， because how do you know。

How objects around you are moving if they're controlled by others。You're not gonna have a sensor。

Sends you signals that this is how I'm moving。Okay。

Same thing for objects moving on highway for self driving cars。

 which makes the multi object tracking problem very difficult。Now， multi object tracking。

 meaning data association， uncertainty。 if you're tracking multiple objects。

Associating measurements to the correct state variable is a challenge。In object tracking or in a s。

 if you're tracking landmarks， that's historically a problem in Eke of Islam。

ultimately makes it less popular。One of the reasons。It's less desirable。

So data association means that you receive a measurement。

 you want to associate it to one of the state variables you're tracking。You need some sort of。

 in this framework， you need some sort of a statistical test。

To know what's the most likely association。If that goes wrong， it can break down the filter。

 the filter it can divertge because you're adding wrong information to the filter。Outliers。

 basically。Now， we did assume the noise terms are either correlated or un or cross。

We assume they're not either correlated or cross correlated。 So if they are。

You will end up with a different filter if you want to derive a filter that's like that。

Which won't be as attractive as this algorithm that we talked about。Okay。



![](img/c7622a63198f9727bc5ca0932e3d62a6_147.png)

That's it for today。 and for reading for today and the future lecture。

 I recommend looking into chapter 2 and three of the probabilistic robotics book。

 three and four of state estimation book。These two lecture notes are good as well。

So that's the end of this lecture。And I'll see you on。Thursday。

But I'm here if you have any questions。

![](img/c7622a63198f9727bc5ca0932e3d62a6_149.png)

![](img/c7622a63198f9727bc5ca0932e3d62a6_150.png)