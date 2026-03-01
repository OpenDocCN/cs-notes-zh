# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p20 -20-Lecture 20-SLAM II.zh_en -BV1UfAmeUE3e_p20-

![](img/4de610c6b7f673d5f41955feaf1c8db4_0.png)

Welcome to the second lecture on a slam。 Today， we're going to cover Gph slam。



![](img/4de610c6b7f673d5f41955feaf1c8db4_2.png)

And we go through these objectives。 We want to understand the s as dynamic base network。

 factor graphs and lease squares and show their equivalancy under certain conditions。

We want to talk about the maximum of posttoity solution to Islam。

And how it ends up being in a nonlinear least dis square problem。

The topic also will enable you to read papers and understand literature。

 This is a core knowledge in literature in Islam。 A lot of new ideas are built。😊。



![](img/4de610c6b7f673d5f41955feaf1c8db4_4.png)

On fundamental ideas that we talk about today。And notation that we will use is weighted norm。

 I'm going to define it now。 So later， when we use it， you're familiar with it。

You're familiar with the Euclidean norm。 A particular notation is when the norm has。Some weight。

This weight is typically it can be a covariance matrix。

 then therefore the weight is in terms of inverse of the covariance。Be careful sometimes in control。

 the weighted norm is defined using the matrix itself。

 not necessarily the inverse of it in this context。

 we're talking about the inverse of the covariance as the weight， which is the information matrix。

Now。One thing that is possible to do is it's always possible to convert this weighted norm into unweighted norm by bringing the weight inside。

The norm。If you factor the covariance using a Chilesky factorization because it's symmetric and positive definite。

Then you get the choice key factor or L and sigma inverse will be。

L transpose inverse times L inverse。 And from linear algebra。

 we know that a times B inverse is B inverse times a inverse。And the notation， a superscript。

 negative P。It's just。A way to show that this is the inverse of a transse or the transpose of a inverse。

 They're the same。So， given this。Background， we can write down the norm。

Plug in the troll key factorization of the covariance。

Then we can see that the new basically vector inside the norm becomes Chiless key factor in various times。

The vector inside the inside of the norm。Therefore。

 this is a equivalent to the Euclidean norm when we weight the residual or the vector inside of the norm with the inverse of the chke factor of the weight matrix。

Now， the previous one would lead to a weighted least squares problem。 But if you apply the weights。

 this is just the standard least squares problem with no weights。So that's a remark。

For this notation， now we're going to start。Writing our problem。So typically。

 we're going to work with。A set of variables， these are state variables can be position。

 pose orientation。Position and velocity and or any other variable in general。

 just like a state estimation。So the notation x。You are familiar with this。

Subscript0 column K means a set of all variables from time step 0。Until time is step， K。Likewise。

 we can define the same notation for the measurements。This notation is a joint。

It's a set of variables。 It's not just one variable。Therefore， when we write。P of。X comma Z。

 we mean joint distribution of all of these variables， not just two variables。Okay。

 this is a set of a lot of random variables， x 0 to x K and z1 to Z K。So we can use。The sub。

And because this is a joint distribution of many variables， we can just separate。

The first measurement like this， and we can do that for any of the variables。The goal is to， again。

 come up with a recursive term to find the joint distribution from previous time step so we can factorize them。

We did something similar in the base filtering here we are keeping the history。

 the entire trajectory。So if we do that， we can factorize this probability。By writing P of Z， K， X。

02 k and z 1，2， k-1。And then the other part will be joined probably the of x0 to k。Coma。1，2 k。

 minus-1。For a mark of assumption。We know that the first part will be。P of Z， K， even。X，k。

Given the knowledge of。The state at time is step K。 We do not need a history。

 That was the mark of assumption。So we can drop all the terms that will not add extra information。

 assuming the knowledge。Is captured entirely in X K。Which is familiar。To us。

 this is the measurement model。 This is the likelihood model。Times， probably the of。Now。

 I'm going to separate。X K from this joint distribution。What I guess。

 I will get the likelihood model。Time， again， I'm going to factorize this。So one more time。

 we can apply。The mark of assumption。Given the state at time is step K -1。

 we do not need the rest of the variables。Of course。

 you also recognize this is just a joint distribution at the previous time step。So altogether。

 we will have。The likelihood model。Times。A transition model， which we recognizes as the motion model。

 whether you show you explicitly or not， there's a non input there。 We could keep you as well。

 It just makes it。Busier， so for simplicity， were dropping you。Times， the previous。

Po stior or joint distribution。So repeat this for the new。

Joint distribution at time step K minus-1 until you reached。X 0。If you repeat this process。

You can factorize this into a prior term because at time is still 0， there's nothing to condition on。

Multiplied。Bye。This factorized form of the joint distribution。Where at every time a step， I。We have。

Our motion model times。The likelihood model。And this is， of course， the same joint distribution。

 So we can factorize the joint distribution into these modules。

 And each module is our likelihood and motion model。 We know how to model them。

 We've done it in filtering and。😊，And。Previous lectures in the slam， we talked about them。

So if you want to show this graphically。Using this directed graph， this is called。A directed graph。

 or。Dynamic base network。It is dynamic because。The arrows are showing time evolution in the graph。

 This is now the static。 It is always possible to show this graph with an equivalent undirected graph。

 And that's also possible。 That is known as Marco Randdomfield。That we don't talk about it much， but。

That's another way to。Visualize it。 So the factorization we did， we did in the previous。Page。

Lead to this。Dynamic。Byase network。So that's the cuvalancy of this probabilistic factorization and the graphical model representation。

 When you see this figure， it means the same thing exactly as the read joint distribution factorized in the way I wrote。

They show exactly the same knowledge。给了03。How they would show time and evolution。

The arrows show time evolution in the sense that you are at position X2。 given motion command。

 you go to position X 3。Right， P of X。No， given right。 So we let's talk about X 1 and X 2， P of。

Example。P of x 2， given x1， right。This is a transition model from x1 to x2。And time moves forward。

 So the arrow show shows the direction we move。 The arrow from Z to X to Z means that given that we are at position。

Or the state X1， this is the cause of observing Z1。work。Clearly。

 we observe z1 at the same time instead there by x1， right。Z 2 is not caused by x1。

 That's the knowledge we see in this graph。 And this is called conditional independence。So given any。

Parent， given a set of parent nodes for any node， that node is independent of the rest of the graph。

Yeah。He said that this graph was same thing as。こ现在没た。You met Sarah。公で。How long is。抛实嘅起住。

I'm having trouble understanding how that。I implied by this。So the question is。

 how this product of a probabilities corresponds to this graph。

 This is the topic of a probabilistic graphical model。 It a course on its own。

As much as we talked about mobile robotics， we could just suspend the whole semester talk about graphical models。

And probably not even one semester。 So you can have two courses。

 and it's available online from Stanford。The part that we need is just showing the equivalentvalence of of these formulation when you read it in the papers。

Very。Generally describing it， the goal of graphical model is to describe。

 as we will talk about it throughout the lecture， is to describe the conditional independence relationship between all these random variables without this structure of the graph。

 the joint probability distribution of all the variables we showed。😊，It would never be。

Like to factorized one。The general case， when we have the joint distribution of x 0 to x K and Z 1 to Z。

 K， it can be anything。 We are not allowed to drop nodes。Unless we make assumptions。

Which we did Markov assumption。It is much easier to encode that sort of assumptions into a graphical representation。

 When we visualize it， equivalent of that mark of assumption。It precisely。

 it is captured precisely by the  errors we have， and we don't have。

The fact that we have arrows from x 0 to x 1， x1 to x 2。

And the rule that we read the graph is that given the parent node。

 the node is independent of the rest of the graph。Then we have probability of x 2 given x1 and not probability of x 2 given x1 and Z1。

 because x 1 is the parent node of x2。There is no other arrow that is pointing towards x2。 Therefore。

 x2 is independent of the rest of the variables。This breaks down the joint probability very easily into the product of terms that we wrote down Without this structure。

 iss impossible。And more traditional way is to。Do what we did for。

Robot motion model will be factorized manually by。Making assumptions and dropping terms， right？

Arguably， that's more involved than just visualizing the relationship between variables。

 So ultimately。When you see this graph， you know how to factorize the joint distribution。

For this particular factorization， this is the graph structure。Okay。

This makes it very modular and scalable for modeling。知道了。一开给他。一。Because there is noarrow。治安人。

We need to be careful， the conditional independence。

This was background probability we does not imply independence。

The fact that x2 is given x1 is independent of Z1 does not mean that x2 is independent of Z1。

Of course， we use X 1 to estimate x Z 1 to estimate x1， and that will affect。Next，2。

So the conditional independence is encoded in this graph that does not employ independence。Okay。

But conditional independence is enough to factorize the joint distribution to smaller terms that then we can model。

More practically， at any time of step， the robot captures an image and that image is related to that pose。

 not the pose at future time step。The image clearly depends on where the camera is oriented at that particular time。

Okay， so these are some examples of terms we can read from the graph。 Again。

 this is a bigger context。 Gal models。 there are different ways to。

Infer variables are different methods。We are interested in a particular assumption that will lead to nonlinear least squares。

 because that will give us a fast solution， at least locally， a fast solution。We're gonna make。

Assumption。So， the assumption is。Gauian noise model。And by that， we mean。We have a transition model。

 emotion model。X， I is modeled using。Some function that describes the motion of the robot。

 That can be an IM U or。A physical model for the robot， or kinematics model。Some input， plus some。

Noise。And the noise。As usual。Is a 0 mean。Gausian noise。

White Gaussian noise uncorrelated with itself across time。So the probability of X I given X I minus1。

 or we can make it more explicit by adding U I。Is proportional to。

A multivariate gaps in distribution dropping the normalizing constant。

 We can just talk about the exponential part。 That is one half of。The weighted norm。

Of the difference between the model and the output of the model。Waited bye。The noise covariance。

In other words。The motion model is distributed according to this multiviate Gaussian because the noise is distributed according to this。

Model， the difference between X， I and F of X I -1 and U I is the noise。 Therefore， that difference。

Which we expected to be centered around 0。 if the model is correctly。

Transitioning our state from time is step I -1 to I。

It is described by zero mean Gaussian distribution， weighted by this covariance。Of the noise。

Likewise。The way we model。Our measurement is。Having in linear measurement model。Htro X I。

Such that the noises。0 mean wide Gaussian noise。So the likelihood model is the probability of。Z。

 I given X， I。And that is proportional to the exponential of negative one half of。And norm waited by。

The model， minus。The measurement。So this is a particular way of modeling assumption， but。Hopefully。

 you are convinced that we get a lot of。Good results by this Gaussian assumption。

 although it does not。So all the problems， but usually tends to give。

Nice results to work with in practice， and leads to efficiency。So under this assumption。Now we can。

Work with more specific models。 These probabilities in general can be anything。

 but now we have a specific model for them， these exponential terms。So next topic is。

We're not going to use that dynamic based network。 There is a better way to model graphical models。

Historically， you will see the directed graph in literature， so it's important you recognize it。

But a better way to model。These probabilistic models is using factor graphs。

Factor graphs are a very general way to model pbabilistic。Problems。In fact。

 you do not need to think of them as probabilities。Any more。

 but it is related if you want to talk about probabilities。So I'm gonna to start with an example。

 Let's say， I have。This graph。And I'm going to convert this to an equivalentval factor graph。

 A factor graph is a graph that。Has two types of notes。 Factors are shown by。

Usually black square or circles。They're connected to the second type of node that these are variables。

And the factors describes the relationship between variables。Unlike the previous graph。

 this graph is not directed。So this is a modeling。Framework， it is more general than。Slam。

 slam is one particular type of problem we are modeling using this framework。

So in the context of factor graphs， we are talking about factors or potentials。If I。

Define some potential functions。Or factors， I'm going to call this fee。0 of x 0。 This is a function。

That is clearly placing a prior over x0。I'm going to call these binary factors， maybe。

Between x variables as psi。We have another one here。So this function is the same。

 but the inputs are different。 We have x 0 and x1。 Then we have another one of that type of function that describes the relationship between X 1 and x2。

Then maybe you have another type。 we call it alpha。

 And that describes x1 relationship between X 1 and Z 1。Maybe another one here， X 2， and。Z，2。Now。

 what makes factor graphs nice is that the joint distribution of all the variables you see in the graph。

It is simply。Captured by the product of all the factors。So once you have the factor graph。

 you just simply multiply all the factors。 and that's。

The joint distribution that makes it extremely simple to work with。

So the modularity of this framework makes it very attractive。This continues。 We have alpha X 1。

 Z1 times alpha x 2， and。Z 2。So as you can see。The prior factor。

Can be considered as proportional to the probability distribution we had over x 0。

This function that describes the relationship between X I -1 and X I。

Is proportional to our motion model。So the factor that is connecting to。State variables。

Is the transition model or motion model。The factor that describes the relationship between X I and Z is the likelihood。

So we have this equivalancy， and the choice that we work with factor graph is。

Just a matter of simplicity。It is easier to show all the factors。

 And the joint distribution is just a product of of the factors that makes it very modular and suitable for。

Implementing a library， like G TS。To add a new type of factor。

 we just need to add that type of measurement model。Once we build this graph。

 it is clear how to describe the whole problem， and that can be automated。

So these are the motivation about this particular choice of modeling， although they are equivalent。

So， to summarize。8。Factor is。A censor。Or measurement model。Graphal model。Or modeling。

He's an easy way。wo。Describe conditional。Independence。And that will enable us to。Right。

 the joint distribution。Because the posterior is a joint distribution of all those variables。

 It is very complicated。 We need better modeling tools to make it scalable and less painful to。

Track individual terms and how to combine information from multiple sources of sensors。

And this seems to be。A good framework that gives us a lot of。Nice to work。 features。

Nice to work with features。Now， given it that we can write down the joint distribution。

 we can talk about。Maximum of a stereary distributionion。In one of your early homeworks。

 you became familiar with the concept of maximum likelihood。

 which we maximize the likelihood to estimate the parameter。And max posterior， when we have prior。

 then we maximize the posterior。So then we have likelihood and the prior。

So when we have the posterior， of course， we， the posterior is proportional to the likelihood times a prior。

We are Bayes rule。It seems to be the maximum of postsiary is the right choice for。

Describing an optimization problem devil。Estimate the parameter here， the trajectory。

Of the state variables， given data。So one way to solve this is using。Map estimation。

So we want to have the entire trajectory。Of the robot。By maximizing。The posterior。

Which is the same thing as maximizing the joint distribution。And this is equal to。Minimizing。

Negative。Log of。The joint distribution。 So log is。monotonically increasing function。

 it will not change the solution of the optimization problem。

Negative sign will make the maximization a minimization problem。And in particular。

 this log will cancel the exponential terms。 So we'll make it。I started to work with。

And the equivalentvalency of maximizing the posterior and joint distribution， because joint is。

Basically。The P of x given Z is joint divided by the marginal probability of。



![](img/4de610c6b7f673d5f41955feaf1c8db4_6.png)

Z。But Z does not P of Z does not depend on X， so it will disappear。So I'll add a remark here。

So now this is our framework。 We can model the problem。

 We can add as many information as we want across time to model this trajectory from a variety of sensors。

 as long as we define the factors。Then we formed a joint distribution。

Then we formulate an optimization problem。If you leave it at this stage， it is too generic。

 Of course， it is a general optimization problem up to modeling the factors and probabilities。

A particular attractive choice is the Gaussian assumption we made that will make all the factors to be an exponential function。

The log will cancel the exponential， and we will end up with。N an linear leads the squares problem。

 Then we know how to solve it using Gaus Neton or 11 Mcmarqua。

So that will lead to at least the squares Islam s。So I'm going to write this in this page。

So now we have。A general framework。4 sensor。Fusion。So the optimal solution is obtained by。Minimizing。

Negative。Log off the joint distribution。And we know the joint distribution is。

Factorize whether we do it。Mannually or constructed graph， we get the same result。

 We know the joint distribution is factorized。As the product of the prior。Times。

All the transition models， motion models。Maybe we have。A of them。Times。All the likelihood terms。Now。

 I'm choosing different indices because we what if we don't have measurement at a particular time step。

 but we have motion model。 They don't have to。Be exactly at the same number。So I'， I'm also using。

X J I。So Y X J I， suppose Z J is a landmark index with J。I need to index to know what pose。

Is connected to what landmark。That will allows me to。

 that will allow me to when I construct Jacobkuian and I know what Ro and color I'm working with。

 So this is a relationship between what pose and what landmark。So let's。Break down individual termss。

 Lo of the prior。Negative log of the prior will be。

Proportal to because we're dropping that normalizing constant。1 half of。

Whatever prior we are placing over。A variable。So x0 is the prior， right？X is the variable。

Sorry x0 is the variable at times to0。 x is whatever priority we place for that time。

It's a negative log of。The motion model。Is proportional to one half of。

Enor squared of the motion model。Minus X i。So， this is adding。Temporal constraint。

We's been two variables。In consecutive time steps。The last one。

 the log of the negative log of the likelihood。Is proportional to one half of。

Normal squared of the measurement model。And with that， we。Can write down our problem as again。

 minimizing。Negative。Log of the joint distribution。Of all the terms that we calculated。

 because log of x times y is log of x plus log of y。 So log， we can the exponential， but also。It。

Conver the product to some。This is a multi objective， not linear， at least a square problem。Yeah。

 I'm listen。I'll explain it in a bit。So we reduce the general formulation to a problem that we actually know how to solve with。

Whether you solve it yourself， you find it after the She solver， this is a multi objective。

 least to squares problem。We can set it up and solve， find a local solution to。A a problem。

So one question is why the prior is。Like that。 Well， that means that we had。

P of x to be proportional to the exponential of。Negative one half of。X minus x 0 squared some。Prior。

 I'm treating x as a given measurement here。Because x0 is part of the state variable。If you remember。

 we had x0 to k。You could use different variables， not X， if it's confusing。What should use？

Withs a lack of creativity。Go for X。Alright， we use X for the entire state。 right。

 That's another good idea， too。Use eggs。Help me out。That's worse。X hat is worse than。😊，How about。

Some。A。Whatever is there。Mean value whatever is the main value of the prior you want to。Said 0。

 it can be 0 in the。slam problem。It's 0， right， So I'm just gonna fix this， and。Yep， Matt。你 say嘅过。

It seems like you said that it was a another。Its like thisす。The state that we're trying to pass。

This is the state。Well， there is a true state， but this is the state that we want to estimate given measurements。

 Z and some prior。Prior is just to anchor the graph， it can be。0， unless for a particular problem。

 you have some sort of knowledge about it。So x0 is。With no。Now x0 is a variable。

 but we place it prior to essentially make it knownun。

When you set zero with a tiny covariance as a prior。

 you're really say to the optimizes that don't change this much。

 maybe changes from zero a little bit。But if the covariance is really tight。

 it's not going to change much。 So that will anchor the graph， make the problem well defined。

 Otherwise， again， we have the same problem of everything is relative。

So it's not measurement in that sense， but it could be。

 maybe it is coming from another source of information。So there's note。

Framework wise is no limitation。 In practice， we make it known by an arbitrary value。

So the question that is。WithNo subscripts。The state。Right。

 X with no subsequent was basically the entire。Trajectory。

So that state is the entire trajectory and by trajectory。I mean， it can be at any time a step。

 position， orientation， velocity， biasts。Landmarks。Anything we want to estimate。And， of course。

 we assume we have enough information to estimate all of that。

 You can just arbitraryrbit add state variables if we don't。

Inject enough information or factors into the graph。

So that's the story of factor graphs and least the squares of s。 So this is a recurring theme in。

Literature， there are tons of papers and problems。 This is the framework you see。

 Once you understand this， reading these papers is very easy。 You can， In fact。

 you can skip that part。 You can just go to what is the single novel idea that you want to talk about。

Whether that's overwhelming or underwhelming， then you can judge the paper to be good or not。直接。我。

A is some non fixed value for the prior。0， you can set it to  zero in your homework 7。

 you set it to zero， right。Yeah。在一。I I good for the。Yes， it's a value that anchors the graph。

Forceces x， basically， you're saying that keep x 0 within this confidence of sigma 0 around this value a and the tighter you make this sigma。

The less you allow the optimization to explore other possibilities， right？it stay like an initial。は0。

It is prioror his initial guess， because after optimization， it won't be exactly 8。Probably。でぜし。

なりましょう。Financial guests， but we just used A to replace X with no sub。

 but we also just said was this state。So can be done。 Well， that was a mistake。

 I shouldn't have used X because x was the trajectory。That was a notation mistake。

I fixed it by replacing x with some other letter， such as a。So maybe I write a remark here。A is。

The mean。Prior。And。Many problems。Example。Homework 7。B。Can set。A equal to 0。

0 for pose means identity for the rotation， and。0ero for the position。무。It is。The question is。

 is this the global or some reference frame？It is exactly that。If there is no knowledge the global。

 the inertial frame is zero is wherever we start。If you do have a knowledge that， for example。

 you want to work with northeast down from a magnetometer or some sort of reference that you prefer to use that。

Then。You do want to force that to be your reference frame。

Because everything else needs to be estimated relative to that frame now。A rotation of 30 degrees。

 about Z。Or X， right。Might become 60 degrees because for whatever reason。

 your initial frame is different。But the relative relationship remains the same。

 That's the beauty of it。 The factors describes a relative constraint。No matter what you choose。

 the relative information is the same。

![](img/4de610c6b7f673d5f41955feaf1c8db4_8.png)

He。So now we're gonna go into。This was the general framework。 Now， we're going to go over an example。

 an example that we can also construct the least squares problem， the linear system， the Jacobubian。

And see。Why？The matrix the Jacobkuban ends up being a spot。That's the goal。

I'm going to use a simple example， the variables are dummy， it's like a single variant。Factor。

 whatever devil already shows you why it's like that。 the pi dimension the problem has。

This sparssity will grow， but you get a lot more zeros。So that's， that's the idea。

And that's a good thing。The number of non zeros。Does not grow exponentially with the dimension or the factors we add to the graph。

Alright， so now we're going to look into。The example， as if we are given a graph。

 we want to solve this problem using listed square inference。Or estimation。Let me draw the graph。

 We have a factor graph。X 0。X 1。X 2。Next three， and I'm going to add a loop closure。对。Connect。X 3。

To my initial variable。So we're dealing with mini。Low dimensional Islam problem here。

So the factors are a prior factor。We have a factor between node 0 and1。We have another factor。

Between one and 2， another between 2 and 3。And another factor between node 0 and 3。

 The fact that I'm using P。That means all of them are the same type。

 I'm not changing on the notation。 That means this is the same type of measurement model。For example。

 it's a pose graph that we had。All of these models are relative poses。So let's make our way up to。

At least the square problem first。I do have X hat here。But it's x0 hat。 That's a good problem。

We of defining the mean。

![](img/4de610c6b7f673d5f41955feaf1c8db4_10.png)

Should we go back and fix it。

![](img/4de610c6b7f673d5f41955feaf1c8db4_12.png)

That's an example of smoothing。This is the mean value of the distribution。



![](img/4de610c6b7f673d5f41955feaf1c8db4_14.png)

You were right。I thought you're saying about X。Had no subscribe。Meu would work， too。

When you stand here， usually lose something like 70% of your。Knowledge and creativity。That's a fact。

I highly recommend you trying teaching。

![](img/4de610c6b7f673d5f41955feaf1c8db4_16.png)

We should fix here， right？Okay。

![](img/4de610c6b7f673d5f41955feaf1c8db4_18.png)

So what are the models， we made it clear already that these models are for us gaussian distributions。

 exponential factors。So， the prior is。Exponential one half of negative of。Now。

 it doesn't matter is it it's x 0 hat minus x 0 or。The other way around， because it's a norm。

Which is proportional to。The probability distribution。We're going to use now making it more specific。

 These are specific models。 It's not F4 H。My models are linear。So， my transition model is。

Between any node I J， because I am also describing P 0，3。Is X J minus X I minus u。I J。

 So there is an input that when we added to。X I， it will give us X J。 That's the model。

And this is proportional to。A model that describes。The transition from X， I to X J， given U I J。

RightSo you could imagine we had maybe some measurements。

 and then we processed that to get a relative pose between x0 prior and x3。And I。Is。Smaller than J。

Because that's what we see in the graph。So my X J equals f of X， I and U I J plus。Some noise。

And the noise。Distributed according to a zero mean white Gaussian noise with covariance。Sigma I J。

The residual。we can define is the difference between。Two sides of this equality。In other words。

 when you isolate the noise。What's left the other side， That's your residual。

Because you want it to be0。 If it's not， that's the error we want to minimize。

So xj minus f of X I and U I J。야。

![](img/4de610c6b7f673d5f41955feaf1c8db4_20.png)

What's the next step， we're going to write a map problem。So the maximum fori problem。Is。

Done by minimizing the negative log of the joint distribution。Now， this sigma is sum。

 The other one is the covariance again。Probably it's better to use a different notation。

Let's change this to。How about capital W？If you're taking notes， you hate me。

Because you have to go back and change it。That's why I never take notes myself。

That solves the problem。

![](img/4de610c6b7f673d5f41955feaf1c8db4_22.png)

Wait to see how things will roll out。And at some point， I'll make my mind what to write。



![](img/4de610c6b7f673d5f41955feaf1c8db4_24.png)

All right， so but yeah， so the point is that this sigma here is the summation notation。

Please do not get confused with。The covariance。Alright。

So we already learned how to convert this into a。An unweighted version。Which will be one half of。

So let key factor inverse。Ofp the weight matrix。And。For the other one。

 also the chillless key factor to invest。Inverse of the C C factor of the covariance matrix WIJ。

And now the nerves are not weighted， these are just Euclidean norms。So we define this to be。

One half of some prior residual。Plus， some of。All I J residuals。But we could just write one half of。

Some overall。And this is K。And K here is 0。0ero one。1，2，2，3。And0，3。

So there is a need for tracking these indices in a key。Variable， That's why in GTM， you have keys。

That's a map data structure that maps iss a hash table that maps between variables and these indices。

Quite painful to track。 But once it's automated in a library， it's nice to。Just use it。



![](img/4de610c6b7f673d5f41955feaf1c8db4_26.png)

And then， this will be。At least the squares problem。



![](img/4de610c6b7f673d5f41955feaf1c8db4_28.png)

So the math problem is。The solution to the map problem is by minimizing。

This quadratic cost function that we can solve we know is at least squares problem。So。

This is the art， right？ We had a general problem under certain assumptions。

 We reduced it to a problem that we can。Efficiiently solve it using a local solver。

It is a local solve。 You experience that in your homework。 if the initialization is not good。

The solveware can only do so much for you。 So it's important to have good initialization。

 not just for one variable， for the entire trajectory for all the variables， because。

The variable is not just x 0， or X K。It's every state at every time step that we are considering in this problem。

 We have to initialize all of them。So once you or' the nextus there。

 once you have a least squares problem， and leasta squares problem。What's， what's the next step？保钱。

The first step to the Cski factorization， did we just convert to really these squares？那一会。

So the question is。How do we convert the weight that least the squares to。Unweighted。

That was the remark。

![](img/4de610c6b7f673d5f41955feaf1c8db4_30.png)

I made here。呃，就是198年9月。You could work with the way that list of squares， I find it easier to。

Converted to bring the weight inside the residual， makes it cleaner。

And then once you're processing individual attempts， you just compute the child key factors。And then。

You wait them。Before assembling the Jacoban。So once you have a linearly the square problem。

Next step is to。Linearize it。Because once we linearize it。

 we can solve the linear sub problemm in Gas Newton and for that we need。

The Jacobian and the right hand side of the linear system。

Because then that will lead to the normal equations。So we continue in our example。

 and now we're going to derive。The Jacobubian。So we don't linearize the quadratic term because it least the squares。

 we linearize the residual。Right， we。Go ahead and write down the residual for the prior is L inverse。

Times x。Minus its。Mean。So if it's not weighted， it's just the identity， but if it's weighted。

 the weight matrix is the derivative。For other factors， we have。L I J inverse times X J minus。X， I。

Minus U Ij。Now， because X J and X I are both variables。

 we have to talk about the derivative with respect to X I and the derivative with respect to Xj。

 It's not just one variable。So the derivative of。This residual with respect to the first variable。

 X is negative of e bursts IJ。And the derivative with respect to the second variable X J is。

The positive of L inverse IJ。Also。It will make it easier later to assemble this in。A matrix form。

So it's the same thing， this will make it easier to construct the Jacobkuan。

We were initially talking about formula。呃。We said that the order doesn't matter because it's in the north。

 so it doesn't matter if you have onetracting the other。When we start linearizing。由是。Doesn't matter。

aliens don't like your question。This is a sign from God's。So we have this right。

 So you get you get a negative sign difference in the Jacobian， but in the right hand side。

You also have a different sign。 So as long as you keep it consistent， it's fine。Yes。

 you will change the sign， but also the residual have a different sign。

You get sine change on both sides of normal equations。So， it doesn't matter。

As long as you don't change it halfway through。Which is a message in all everything we do here。

Stick to something and then keep it consistent throughout the process。あいです。sorry。Necessary。Well。

 UIJ is measurement。It's sort of a given value。 It will be the right hand side of the equation。

 It's not my variable。That's why。Yes， you could。Make this vector longer。

 The reason I'm doing it because it will come handy later。Otherwise。

 you have to think too hard how to assemble the Jacobkuban you'll see now。Right。

There is no particular reason then。Helping us to know how to place the Thames inside the Jacobkuan matrix。

是か。In this example， you can think of these as a scalar， but they could be vectors too。

You could think of them as vectors。Of any dimension。

That's why I'm writing it in matrixtri from El inverse and keeping the order as if they're matrices。

Basically this is an RN example， it's not on legal group。Once you master this， the next step is。Well。

 these Jacobkubs are a little more complicated because I have to linearize。

Using exponential function and variables that are in the algebra， right。

But that's a whole different story that we covered it。Un list the square is on legal group。

So we want to assemble。A。X equals B。I write it5 by4。

 but of course this could be blockwise if these are not the scals right5 is five blocks and four is four blockss depending on the dimension of each variable if it's 3D position。

 x0 has three columns itself。If it says 60 pose， 3D pose。It has six columns。So it's a simple example。

 there's already a lot of structure to learn from this Jacobuban。You notice any pattern。S sports。

The matrix is the sports， there are a lot of zeros。

These zeros are exactly the ages or factors that are not available within variables。

X1 is not connected to。X 2 and x3。In row， the second row， right？In the second row， for example。

 this is one of the factors。 so factors are rows， these are observations， variables are columns。

 this is a Jacoban in second row， that's one of the factors that we see。

 This is a factor that connects x1 to x0。Any other variable that is not in the factor will get 0 because the derivative is 0。

With respect to those variables。If you have many more variable。

 these zeros will be very long so that this matrix will be always the sparse because the graph is not fully connected。

Okay， and it's never be fully connected because there's just so many variables。

 not everything but everything is connected across time。The prior。

 the prior factor is the type of factor that connects。Provide information solely for one variable。

 The first row is only saying that the。Directly， what is the value of x0， which is the mean value。

 So that's just the equality that is telling you the value of x0 is x hat 0。

The last column that is row， that's the loop closure factor。And it loop closure。

 unlike the other factors， factor 2，3 and 4， which has a staircase like。Pattern。

So any motion model is connecting to consecutive variables。Which one of them is negative。

 One of them is positive with some， whatever。Jaubban or coician they might have。

So this structure will repeat itself。 And especially if it's the same model。

 This is a repeating block for the Jacobubbian of the motion model or that factor。

So assembling this large Jacobkuan is also modular once you know the models。

We can just fill in based on this pattern。The last row。

It's a connection between the first variable and the last variable。 Anything else in between is 0。

There's a different type of pattern we see。So little closure as well。Cas fill in in the Jacoban。

For variables that are not。Next to each other。Now， if the problem in this case is linear in this example。

 if the problem is truly linear， this is the linear algebra view of exactly the same graph。

Under the assumption that the noise was Gaussian。This matrix and linear algebra is equivalent of that graphical model。

 So they're the same thing。Right，But if it's not linear。

 this is a local representation of that because we linearize。Don't think I'm quite caught that。

 are you saying that because it's a linear system， this structure will the exact same。保这价面。

So this example， we're going through a particular example here。The models are linear。

The Jacobubbians are all constant。 If the covariances are constant。The Cho key factors are constant。

 So a is a fixed matrix。If the motion model or factors here would be nonlinear。We had to。

Reeval the Jacobkuban at every tu， right？So in particular， this is a linear square problem。

 It's not not linear to keep it。Simple as a toy problem。Now， if the。Factors are linear。

So the factor graph or the graphical model of any form we had。

 it is a equivalent of solving a linear system of equations。Which is nice。We know how to do it。

 Alge is the way to solve the problem。 right， We know exactly how to do it and very efficiently。

Under assumption， again， the factors are exponential factors， Gaussian factors。

If the factors are nonlinear， this algebraic。Representation as linear system is just a low hole。

Representation of that factor graph based on current guests we have for the trajectory， right。

I guess also like actually， I guess if the system was linear to you the noise is multily needed。

 we could also like do we also say that way？Like the same water gation still gation So your question is。

 what if the noise is multiplative， or， we chose to model the noise as additive exactly because it simplifies the problem like this。

That would make it more complicated。Because then obviously。

 there's a need for linearization if the noise is multipld。So this is a nicest case。

 as good as it gets。诶。Is there any chance that？You can if the loop closure or any factor is connecting three variables。

 then three of these columns will be non0。Pレ to calculate。Yeah。

Any variable that exists in the factor。It will have a derivative。If not， then you get 0。

And the factors are local， right， I mean， even a factor that is connecting three variables is somewhat rare in the literature。

 You can have it。But it's typically binary and urary。So because of that， for every row。

 you get nonze for the columns of those two variables， or if it's a prior。

 that's one variable and everything else is zero， and that makes it super sparse。



![](img/4de610c6b7f673d5f41955feaf1c8db4_32.png)

Which makes it super fast as all。So this。It's a sparse。 So if we do。As far as。Here you are。

So you do not want to use a generic factorization because。

That generic library will ruin the sparsity will treat zeros as any real number。 You won't gain any。

Performance。So if we use a sparse factorization library， then a。Equals Q R。Q。A X equals Q R X equals。

B。Q transpose Q R X equals Q transpose B。So re。This is R is an upper triangle or matrix。

 We have back substitution。So that's how we solve s using Ellicis squares solvent。So in GTA。

 what you're going through in your homework 7。We build。The graph。Given。Laterer。

So we do not implement a solver because it is already implemented。

And you have a range of solvers to choose。And it will do list squares。

 now linear least square is on legal group for you。Once you get familiar with the library。

 you can change。Different settings to do different ways of integration， but。

It is nice to have something like this because your focus is on building the graph and this whole process of building the graph and solving it is the backend。

😊，If you remember the front end was the messy part。

 you have to process all the data and then come up with these factors and measurements。

Once you have all of them， you just construct the graph and solve it。



![](img/4de610c6b7f673d5f41955feaf1c8db4_34.png)

So that's the story of graphl and how we solve the problem。That's the end of lecture for slam。

