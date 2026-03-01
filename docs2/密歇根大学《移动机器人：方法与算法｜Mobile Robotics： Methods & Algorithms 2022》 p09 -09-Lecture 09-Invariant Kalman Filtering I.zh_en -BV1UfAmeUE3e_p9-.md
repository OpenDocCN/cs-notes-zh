# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p09 -09-Lecture 09-Invariant Kalman Filtering I.zh_en -BV1UfAmeUE3e_p9-

In this lecture， we talk about the invariant kman filter using what we built so far。

We want to talk about a filtering method that uses exponential coordinates。

 This is a filter from the family of symmetry， preserving observers。It respects the structure。

 the geometry of the space。 It doesn't break the symmetry。

 and that leads to interesting properties that we will study and try to understand today。

So this is a my for the course， this lecture and the next one。This is the last。Topic on the filters。

 Basically， we covered a bunch of filters that you can use for state estimation tasks。

And that should give you a good set of tools for a variety of engineering problems。Not just robotics。

 and not just。A particular application that we might use， maybe localization。But in general。

 it will be very useful for your career。After that， we will focus on。Cameras， point clouds， s。

 RGBD cameras。And some other problems that is more related to perceiving the environment。

 mapping and so on， okay。So I try to highlight some of the topics that we covered and not to repeat them so we can focus on the main ideas related to a particular method that we want to learn。

So I do not intend to repeat some of their reminders in depth。Throughout this lecture。Now。

 the motivation in general is。For people to study these type of problems and do research on it。

It's because a large class of systems， when you study them using matrix league groups。

They exhibit natural symmetries。We've seen some of it， Some of the calculations are more intuitive。

 in some sense。And error propagation， last time we observed that I was。In particular， simpler。

 it was similar to linear error propagation。Once we derive the result， it was easy。 The process。

 of course。Was a little demanding depending on how much background you have in that area。Now。

 the theory of invariant observer design is about。They arriving in a state estimator。

That is imvariant under。Group transformation。 That means the error does not change when we transform it using a group matrix to another point。

Meaning rotating it or translating it or rotating and translating it at the same time。

That should not， in principle， change the。Behavior of the filter。And the goal is to capturing。

 to capture that in a mathematically sound way。 And we can see it in our calculation。

So there is a clear objective why we go through。The math。And one。

 if we want to summarize one fundamental result is that。There is a choice of coordinate。

That will lead。To at trivial aerodynamic。The question is， what is that choice。For certain problems。

 that we will see what type of problems。That choice is the exponential coordinates， okay。

So it's not for。Any problem for a class of problems， But that class of problem， the problems。

 It happens to be。Very frequently occurring in robotics， A lot of sensors that we use。

 a lot of problems that we study fit。Into that class of problems。So that makes it very useful for us。

Now， we talked about the error modeling。 last time we learned that。

If we're working with a matrix group， the correct way to define the error is using inverse of a matrix and matrix multiplication。

So that the result， which is an error in terms of in of a matrix。First of all。

 be part of the group because the error will be a group element。Whereas if you add or subtract。

 it won't be because it。Violates the group。Ros for operation and closure。Now， here is a。

Graph that shows what happens when。We respect that structure。 And what happens when we don't。

The true。Proropagation here， which is a 2D。Planin with orientation。You can think about it as。

3D or 2D， but we're looking at it from the top view。So the true Monte Carlo propagation is the green。

That means we draw random samples and then evaluate the process as the robot moves。

The robot is moving forward。We get this banana shape。Covariance or distribution。

For the possible locations of。We're robot。Now， when you we use a right invari A F to do the same propagation。

It's almost exactly capturing that shape。As if we're not losing anything。

Whereas the typical way to do it， which was called Coernian EkeF。Was to。

Model the rotation correctly using quaernions， or you could do it using S O3。That's not a problem。

 And then they find the translation error separately， using just a delta。Now。

 when you decouple these two and you ignore the action of rotation under translation as the robot is moving and rotating。

That leads to。Not being able to capture this， basically No linearity correctly。

Although just for the rotation is correct， but when it's combined with。Translation and velocity。

 it can。It can lead to inconsistency and bad performance。

 but there is a area that they might overlap。 And this filter， of course， works well if。

This effect is a small。Small rotation， small error， good initialization。

 These are cases that we might not see this。But we are aware of this limitation when we decouple the translation orientation。

Another example you see in the bottom is。These circles， imagine you start from a location。

Somewhere here。Your eyes are closed。I turn you。Around several times。 And you have no idea。

What is your direction？Well， you know where you are。Wherever you are， that's your initial position。

 where you have no idea what direction you're moving if you start walking。Now， you start walking。

And you move forward。In terms of translation。You roughly know how much you're walking。

Some small error， maybe， but that's。Not a problem。 You can count your steps and you know how much you move forward。

What about your orientation？3，60 possibility， right， You could be anywhere。Let's say。

Youre starting from here， you move this much。I'm just visualizing it at a particular time step。

 but of course。It's growing continuously。You could be anywhere， that's。

Not possible to know unless you open your eyes or somehow you get。

A measurement that tells you that maybe you're facing。Somewhat this area。

 And then that will reduce your uncertainty。Immediately， just to this part。Right。

So we get rid of all the uncertainty。 And that's basically what column filtering is doing。

 You're tracking a posterior distribution。 When you get measurement。

 this measurement will cut through the uncertainty and leaves a mass。For the posterior， that is。

More likely， given the prior and given。There are evidence， the observation。

So that's basically the essence of this sensor fusion and common filter。 Collect data，fuse it。

 make it better， make the estimate or post stereo better。Now， however。How do you model this circle？

You can't model it using this filter。What it will do for you， if you decouple the， the error。

You'll have to track。A dense covariance for the whole of space。Right， and at some point。

Because you're thinking about orientation and translation as just different。Directions， right。

 you define your error。 You're not able to decouple the correlation。Across your dimensions。

This filter is not respect。The fact that uncertainty that is caused by your young angle yell must remain along that direction。

Should not be propagated through the other dimensions if it's not related to them。Okay。

 it's as simple as that。 You get a spurious correlation across different dimensions， which is。

 in a sense， is inconsistency。And that correlation， it will grow and makes everything uncertain。

 It's not just your orientation。 It's actually where you are。It can be anywhere here， right？

And do it in long enough， This e is so big that it's useless。So。With something like。

The invariant columnman filter， we can。Propaate uncertainty consistently along a particular dimension that we are。

Lacking observation。Okay，That's the power of this filter。

 So the rest of the lecture is to just nail down some equation of math and algebra so we can implement this。

This is why we need this。 This is the problem it will solve for us。而020。This is the。The question is。

 is there any weakness。Of course， there is。But relative to the previous filters。No。

Because it is a generalization of。Those filters。Now， again， this is if you are working。

And a problem that state evolves on a matrix league group。

And satisfies certain properties that we're going to talk about it。 Then it doesn't have。

Any weakness， relatively speaking， as if， if you use。A typical EKF or quatian EkeF okay。

But with respect to a broader idea of inference。 Yes， of course， it's a specific method for。

Estimation。It is a particular assumption how the update rule should be。 And in a sense， it。

 it's like extended common filter， right， extended common filter cannot do what particle of your filter does。

That doesn't render that algorithm useless。It is good for a certain。Application， right？

Given the right context， it does not have。Weakness。AnEx of。去定。说下。Inver。24年。You're saying。

 should this be。Both， we're going to talk about it。 you have two options。The first equation made。

That's what we're going to talk about。Please be patient。

But you're seeing the output and it makes you super curious， right。です。The differential equation here。

This is a result， so。Thanks for pointing it out that the outcome is that the error in。The group here。

 which is now nonlinear。Is captured by a group element， something like this。You can。Reellate this to。

Aly algebra element， using exponential。Map。And this is just a Lee algebra element。 And you can。

 of course， think about it as a vector now today。😊，When I write exponential。What I mean is。

Ca see hat， right？Previous， you've seen that。 It should not be confusing just to keep it simpler。

 Otherwise， it makes the writing no busy。It's understood that this is the exponential of a matrix。

 And once you pass this vector， you need to make take the hat of it and then take the exponential map。

RightIn your implementation， you can handle this。Therefore， with agreement， you can drop it。

To keep things simpler。anyway， the error。Will follow a log linear in logarithmic。Sense。

 because we need to take the log of this exponential map。Will thought will be governed。

Only by an autonomous differential equation， given an initial condition。

 we can recover the error at any time in the future exactly。 And then we're gonna see。Why and how。

Let's start with a motivating example。Now， consider a linear。Time invariant system， and L T I system。

In form of this data space representation， you have a system matrix a。And the input matrix B。

The system is deterministic。 There is no noise。A and B are our model。We know them。

And time imvariant means they are fixed。 They don't vary with time， although they can。

That's not a big problem。Define the error。To be the difference between the true。State X。

And the estimate of x， x bar。Which for the estimated state X bar， we get this dynamics， right。

 true X will be， of course， replaced by the estimate。 And then that's how we can。

Talk about their imperfect system。Now， the time derivative of the error is x dot minus x bar dot。

If we substitute。The respective。Equations from here。We end up with。Just the matrix a times the error。

 So this is interesting， because。The time derivative of the error for linear， theministic。

 linear time invari systems is only a function of the error itself， given an initial error。

An initial condition， This is an O D matrix， O D。We can recover the error at any time， exactly。

Using the solution of this。Different equations。A is constant， so we can just write it like this。

 If it's time variantant， then we have to integrate。 You can talk about the Delta T。

 assume it's fixed during a Delta T。So this observation is true for linear systems。

 And that's very attractive。 That's what makes linear systems so attractive。

The linear common filter covariance calculations are independent of the state。In fact。

 they can be done offline。嗯。Be deployed online。 That's what people used to do， when computational。

Basically， resources were really limited。On hardware。Now， the error propagation。

 the lesson we learn is that the error propagation is independent of the system trajectory。

 the state estimate this is。The true， this is the estimated trajectory of the system as it evolves over time。

Which is a vector itself， or it can be a matrix later。And the true system trajectory is x of T。

Why this is useful。general。He。Yes， so you're saying the error has a general equation and we can recover that at any time。

 Now， what is the consequence of that。For our algorithm。Something like a linear common filter。

Aaron moves in algebra then。说吧。way that error。あす。Simr， something simpler。What if my estimate x bar。

It is。Far from X。The true estimate， the true trajectory。 What if my estimate is not so good。

Or my initialization is not so good。At some point， the filter is。

Not giving a so good answer is just far what happens to the error。

Will that affect the error evolution in the next step。It does not。 that's very。

 that's a very powerful。Consequence， because no matter how far from the true trajectory。

The error will evolve independent of that。 And hopefully under some regularity conditions。

 we will convertverge to 0， okay。And that's， that's what we were after for this invariant column filter。

I guess。I guess I'm understanding how the error property。a consistent trajectory。if we。

I think I'm confusing him with this。being。Independent from the trajectory versus the error propagation meeting。

you're saying， what is the relationship between the error being independent of the system trajectory。

 meaning we don't see X here。And the propagation， the propagation is just solving this equation。

Forward in time。So the solution of this differential equation forward in time is the propagation。

Which is that we call it prediction in in。The callman filter algorithm。

 we call it the prediction state。 Proagation is another name for that step。Okay。

 solving forward in time without any correction。So because the covariance is just expand if we predict or propagate。

Unless you get a measurement， right， it won't shrink。

Does it assume that your initial error estimate has to be fairly accurate because if you don't。

 then your income will be， it's always opposite。Does this mean the initial error？

Condition must be accurate， no。It can be anything。Given any。Initial error， this result holds， right。

So that's。Not limited to that。And。Somebody asked， is Xdo。Time derivative。 Yes， when I write。

That means it's the time derivative。I do not have any control over which one I write， so。

When it's dark， it's the same as the。Over Dt。So that observation is something that we wish to replicate for a nonlinear observer。

And that's what we will see。Now， let's continue。To motivate this further， and。For example。

 or an example that will contrast it even more， Consider the 3D orientation estimation。

 we have an IM U inertial measurement unit sensor。But we are just looking at its gyroscope。

 This sensor is attached to the robot or the rigid body， as it moves。

You can read directly the angular velocity measurements of the sensor。It will tell you the rate of。

Rotation about。This frame that you see here attached to the sensor， X， Y， Z， as it moves。

 So it's always in the body frame， physics。Can only give us。The measurements in the body frame。Now。

 let's say using your undergrad knowledge， you learn Oer angles。You know how to model rotation。

And you want to model a process dynamics。For the gyroscope。Now， the goal is to。First of all。

 define your parameters。 Our parameters are。Olier angles， I'm using Q here。 You could use other。

Notation。Ro。Pitch。Yeah。This is Z by X， by you could use any other convention。 It doesn't matter。

So I have a sequence of three independent rotations。If I choose to work with this convention。Z， Y x。

The product of three of them will give me a rotation matrix about。Three aes。Now。

 the goal is to derive the rate of change of these oiler angles， roll Pr。

Which is not in the body frame。It is with respect to my。Iner shieldiel frame， fixed frame。

A world frame。I want to relate the rate of change of these oiler angles to the angleular velocity that I read from the sensor。

 Then I can integrate it， okay。Now， this is the same thing as when I say R dot equals R omega。

This is， indeed， the gyroscope process model。However。

 if you are parameterizing your rotation using all your angles or any other parameterization that you choose。

Then， of course， you're interested to know。The time derivative of these parameters， with respect to。

The angular velocity， right， So it is a choice for。Parameization of the rotation here。

And all their angles。Basically， provide。The convenience of parameterizing the rotation using three numbers。

 angles。Because your rotation is completely captured by them， right。

 So we work with the time derivative of the parameters。Notation place， does that that represent the。

You know， it is a matrix that。Well， you don't know how to get it。

And I'm gonna tell you how although I'm not gonna derive it。 I shared on piazza today。

Code and references how to get this。 And I have a line that should be clear how to do it。

You should be able to reproduce it in。Less than a minute in Matlab。

But it takes a little more to think about it。So there is a matrix that is called。Ouler。

 angle rate matrix。What it does， it relate relates the rate of the angular velocity to the rate of the earlier angle。

 In a sense， it is a Jacobcuban， right， So it is a Jacobcan that relates velocity in some coordinates to another。

😊，That's what it's doing。 It's just more specific。 It has a more specific name。So it is a Jacobian。

And。The chosen coordinates。Z， Y， X， roll pictureia。Now， how to derive this matrix， I we。

 we've done the calculation。 This is the solution。Which does depend on Royal PI itself。

You remember that。The angleular velocity in the body frame。

 It is forpose of the rotation times are do， which is exactly what I wrote here。😊，We establish this。

Well， if that's the case。From。The chain rule in calculus， we know that to evaluate。

 to evaluate the time derivative of R。I can talk about its derivative。

With respect to some intermediate parameters， times。Time derivative of。Those parameters。

 That's what we're doing。Now， however， R is a matrix， right。To take the derivative。

We go through all its entries。 So you will get a double summ， right， Three rows， three columns。

9 elements。So this I J is for going through all entries of R。Now， for each of the entries。

 we need to calculate this with respect to three parameters。 So you get a third sum。Okay。

Which basically， we need to add， add them up， right。

 derivatives for each entry of the matrix for roll P up。

You w to know the rate of change of your matrix entry， with its spec。To all the parameters。

 these are coupled， right。So we had to add the effect for a linear Jacobubban term。To appear for us。

 Now， this will give you a matrix。 I name it E inverse。 That's just。What I do。

 because I want to call E， the matrix。To be the one that when I multiply by the angle of velocity。

 it will give me Q dot。Otherwise it， it's， it's。It doesn't have to be im in this direction， right。

So in a sense， it is the Jacoban of。MOf basically the angleular velocity in this particular choice of coordinates。

So in any case， this is our process model。We can derive it。Now， this。

 this way of doing it is nice because it doesn't matter you choose Z， Y， Z， X， Y， X。

Any other choice of coordinate， this is true。Whatever you use to parameter your rotation。

 you can use this formula to get this Jacobubian。If you do choose your exponential coordinates。

 that' will give you。Something called group Jacobubbin。Because it's intrinsic to the group。Alright。

 so we get the process model。 What happens if I。And there is a library here as well。

 You can go to this link。It's already implemented for you。You can just clone。This rippo and。Use it。

Now， what happens if I define a delta that is the difference between Q。And an estimate of Q。Eror。

 I'm defining the error term。For the oiler angles。This will give me some。Arero dynamics。But probably。

 it won't be nice because the a matrix， that， the E matrix。Was not。Constant or linear。

It was nonlinear。So terms get coupled because of thelineity it's not that easy as factoring the matrix。

Multiply by the error。So I get an aerodynamic that is nonlinear。I'll leave it to you。

To make an attempt to drive it， And I will help you to write it down， if you're stuck。

If you do the calculations。And then you linearize with respect to。The error term。

Just like a tailor expansion， with respect to the variable that we're interested to build a linear model around this。

You will get this matrix。 Let's call it A。Now， the problem is this matrix is a function of the input。

But that's not a problem。This is the input。And。This state estimate。That does not。Mach。Our vision of。

Being similar to the linear system。 So wherever you are to propagate， to integrate。This Oer angles。

 using gyroscope data， you do need to have an estimate of the global orientation of the object。

If that estimate is not correct， that will affect your integration as you move forward。

 If it's not correct。Meaning that its， theres a delta that is large enough。

Because estimate is is never the true value， usually until unless it converges。

 But if the delta is large。Each time you integrate， this matrix is becoming more wrong。Right。

Wrong estimate。Wrong。Proagation。Wrong propagation。More wrong estimate。More wrong estimate。

 more wrong。Proroppaation， so it creates a positive feedback loop。

Depending on how severe it might be， that that's the reason the filter might diverge。Okay。

 so it's very important to initialize it correctly and have a reasonably correct estimate of the state。

 depending on the problem。So this is the core of the problem。

The linearization of the errorero dynamics， it does depend on the errors as on the state estimate。

And this creates a positive feedback loop。Now， let's look at the same problem。Through the lens of。

Lgo groups。Now， consider a process dynamics， process model that evolves in a group。

 You've seen it before。 We worked with。This type of models， but it can be， in general。

 more complicated models as well。So x is an element of the group。 X bar is the estimate。

To define the error。We can multiply。The error from left or right by the universeverse of the true state。

Now， for Euclidean case。It doesn't really matter because it's just a negative of the same error。

And especially if you want to calculate the covariance， it doesn't matter at all， because。

It's a quadratic term。 The negative sign will disappear。For matrices。You will get different results。

It won't be the same covariance。So that leads to two options， left and right。

Now it doesn't matter so much。 Sometimes it makes sense to use left， right。

 That's not something to be worried about。But it does matter to stick to one， and。

Go through that convention for the problem。Okay， not inconsistently switching between left and right equations。

 Other than that， it's not a source of concern。Okay， so。

That leads to the definition of the left and right invariant error。

 last time we defined the left invariant error。 This is the same thing。Define the error to be。

The estimate times。Inverse of the true state。If you。Forran each。Pair。Both of them。

 with another group element， like L。From the right side。It will disappear。

It leaves the error invariant。Because you have X bar T， L， L inverse X， X bar。Right。

So this R means it's rightvariant。Now you do it from the left side。

 When you multiply from L from the left， you get the same property。So we call it left imvari。

So we have two options。Notice that L can be any group element。It's not。

It's true across all possible transformations。These are left and right， invariant error definitions。

We have two main theorems。 The first one that we try to understand。And it's somewhat。

Straightfor to prove。Is that。For what class of functions。We get。And aero dynamics。

That only depends on the error， and not。The state estimate。If it depends on the input， it's okay。

Because input is something you read from the sensor， and you know it。 It's the command。

The important part is the state estimate， something that we do not know。

So the question is for what class of functions or process models。Evolving an league group。

We get an aerodynamic that is like this。You do not see X。Now， working backward from here。

You can show that the process model。 This is a continuous time process model must satisfy this right and side property。

And proof。That I encourage you to make an attempt is that。

Substitute the definition of the writing variant。Right。Now， take the time derivative。

 It's the product。 It's the time derivative of the first one plus times the second one。Plus。

 the first one times the time derivative read it with the second one。

 You need to deal with the of a matrix。 But that's okay。 You have， you have a formula for that。Now。

 you know that X star is F of U， right。Substitute the process model into that equation。

You will arrive at some。A bunch of terms。Now， the key is that if this is。True for。

Let's say x1 and x2。Or。If this is true for design up。For X 1 and X 2。

 it's true for any group element。 Once you arrive at that point。

 you substitute one of them with the identity， right， because that's very nice。

 If it's true for any group element， let's pick one of them to be identity。

And then you will arrive at this。So I don't intend to spend the lecture time for proving that。

 but that's a good topic to go through it。What is nice about it is that for。

The process model that satisfies this property and is really just plugging in and checking if it does later。

give you a process model。 You plug in here if it satisfies it is。 If it's not， it's not。

We get aerodynamics。That is already defined。It is completely defined by the process model itself。

The error and the process model at the identity。So it's really headache free。Calculation。

 using the result of the theoryorem， you have the errorerodynamic If the process model is group are fine。

For the left， you get another equation。Okay。This is called autonomous error。

Dynamics theory in the work of。Bahu and Bonaelle， they proved。

These two theoriesors and published the invariant extended common filter paper。

I shared the journal link with you。 It's published on IP transaction and automatic control。

If you like to do research， these are good topics to go through and learn the proofs。Otherwise。

 using the result is fine。Now we're going to talk about the second theorem。

 this is for the general matrix league group is not trivial to prove。It has some involved steps。

For S03， rotation group is actually straightforward and I'll prove it for you。

But it is true for all matrix league groups。So this is called the log linear property of the error。

The property that we were after， that the error evolved independent of the state estimate。

Let's define。This to be。A vector version of the Lee algebra element， right。

So a is a matrix that whatever is the dimension of the L algebra will be a square system matrix。

If it's S， E。3， a will be 6 by 6。Because the twist is a six dimensional vector。Okay。So，4。S E 3。

The dimension of。The Le algebra is。6ix。is which is the dimension of that group。

For a rigid body in treaty。Now， the theorem is telling us that。If we have。

Let's say the right invariant  error you could pick left as well。

Between two trajectories that possibly far apart。If an initial condition is given。

Such that from the initial error in the Le algebra using the exponential map。

 we can recover the initial nonlinear error。Then， for any time。N E T forward in time。

 we can exactly recover the nonlinear error using time evolution of the error in the Lee algebra and the time evolution of the error in the Lee algebra。

Is governed by this。Autonomous differential equation。 It doesn。 It only depends on Q C T。

 It does not depend on T。Or other tank。So it's very powerful， powerful。

 in the sense that given an initial condition， we can exactly recover in a linear error。

 that's what exactly we were able to do for the linear system。😊，Which was actually exponential。

Of the system matrix。 So it is actually very similar to that。Right。

Some of you don't believe me from your。From the look you're giving me。I'm talking about this term。

 What is the difference you see is just another vector。A is a matrix。Now you you， you should ask。

 where you get a。And if that's exact， right？And that's that's basically。

The main result of the theorem is that you can get an A。And it is exact the linearization。

And we're gonna show it for S O3。So， there is a choice of。Coordinate system。Formatics league groups。

 that gives us。This autonomous。Different equation for error evolution。Okay。A reminder， you know。

 by now， we established that the differential equation of a legal group。It's something like this。

And this is true for all league groups。 We have that。

And this will give us a kinematic equation of motion。And SO3 happens to model the gyroscope。

This is a little formalized version of that。 This is in differential geometry。

 this is called a push forward map。 That is why when I draw that shape。

We could move from one tangent space to another tangent space。

That is through a push forward map that helps us to translate terms from one tangentous space to another。

 And for lead groups in the ends up being just。The group element itself。So that's beyond。

The scope of this lecture。 But what we care about is that what we established that。

The differential equation for each group has this form。Could you' going sort of hitting again why is？

The error in the last。MGT与。It's not defined yet。Yes。Error。No。

 this is this is independent of the previous slide。I'm just saying。For every league group。

 we have this differential equation。Sa a reminder。Becauseuse I'm going to use it。Here。Okay。

 now let's revisit that example。That we covered using oiler angles， using。

The exponential coordinates of S，03。Same problem。 There's a gyroscope。 We read angular velocity。

From the sensor。If the state evolves as a matrix as an element of S03。

 the dynamics is basically R dot equals。R omega is q。嗯。

These are direct measurements we're reading from the sensor。So what is your。

 this is your homework for， by the way， attitude estimation。

 I'm going to give you real data from an IU， the exact picture I showed you。

It just collected in the lab。And。You need to estimate the orientation of the sensor， why。

Integrating the gyroscope and then using the accelerometer to correct it。

It's a baby attitude estimation problem。 It won't give you the final。

 nice output that you get when you buy an IMU。But it's a building block of that。

 You will need to do more。Like using magnetometer and maybe calibration。

 including the bias terms and all of that。But once you can solve the basic version of that is。

 is so much easier to build on that。 So that's your homework for。All right。

 let's start from the definition of。They left invari an error。I'm choosing left。

Because it will give us something that you can see if I choose right。

 the errorero dynamics will be 0。 It's just so simple that it is a little boring。

So to not to get that 0。I'm using the left invarian example。

The start from the definition of the error。And take the derivative。

De takeect the derivative of the error。Some direct calculations will give you。So， this is our。

The transpose。 And then we know our do is。Our omega， we substituted it。Then again。

 we know this is the error definition。 We arrive at this line。And then define it to be G。

 It is a function of。The error， the left invariant error。And the angular velocity。

 It does not depend。On the estimate。So it is this particular choice of the state and error variable yields。

An autonomous error dynamics already。Now let's linearize it。And the way we linearize it。

 it is actually easier because you don't have to go through。

Calculating the derivatives and taking the Jacobubbians。So we just replace。

The nonlinear error with an exponential of the Le Albra error。

 the vector space that we want to work with。And then do a first order approximation of the exponential map。

 It is a series。 Just keep the first。Two terms。 The first one is the identity。

 The second is the variable。And drop everything else。 This is called。

A first order approximation now substituted to the aerodynamic that we just arrived。

 They just arrived， which was。Exponential of sea and。Omega。Carry on the calculations。

 the time derivative of the identity plus。You see， obviously。This will be 0。In this line。

 I'm using the property that you see here。We directly recognize that。This is the Lib bracket。Of。

You C n omega。4our。3D rotation，3D rotation group。The leap bracket was the cross product。

 so we can actually make it easier。 The Lib bracket of A M B is the cross product of A M B。

 and then take the hat again。To make it a matrix。So if you use this property。We actually arrive at。

That's there。Now， apply。The V operator to both sides to make them a vector。

To make each side of vector， then we get。The linearized aerodynamics in the Lee algebra。

And the a matrix here is actually the negative of omega s。 It is independent of the state。

 but it does depend on the angleular velocity readings from the sensor。 But again。

 that's okay because。That's something that we read from the physics of the problem。

So that's an example of that matrix， A。What's the natural question to ask？What do we lose？

I just told you to lean your eyes and it said， okay。I mean， maybe we lose something。

 then if one make it。Exact， right。Now， notice that this is nice and we can work with this。

But it only replicates the linear system， if it's exact。If it's not。

 it's just maybe a nicer framework to work with。 It does not hold any theoretical properties。

Now we're going to show that this is exact， although we linearized。The magic of that theorem。

 Second theorem is that。The higher order terms will vanish。Now we're going prove it。

 prove that this is exact。Now， consider the initial error。As we discussed。Now， make a guess。

That this is the solution of。The aerodynamic。So I'm gonna make a guess that， given the initial error。

The nonlinear error at any time is R transpose times。The initial error times。2。

How do we know this is a solution？Let's take the derivative of the。This candidate。

When you take the derivative of this， you replicate the aerodynamics。 therefore。

 this is the solution to that differential equation。

Given the existence and local existence and uniqueness of the solution to O Ds。

From that result in math。So that's， that's， that's a correct guess。Now， starting from here。

 let's replace the nonlinear error with the exponential of the Lee algebra error。

We recognize this is the adjoint property。 So it will be the exponential of our transpose K C 0。

So the error at， the error in the Lee algebra any time is completely described by the initial error in the Lee algebra。

 It is just。The R transpoposed version of that。Now， let's differentiate this。Tm here。What we get is。

A dot transports。Our dot is our omega， substituted into。The equation。

 the transpose will change the order。 The transpose of the scsimatic matrix will add a negative。

 and we recover that。Lg linear equation。So we just recovered the same equation that we arrived at by linearization。

Starting from the exact solution of the aerodynamic。So。We just proved that we did not lose anything。

By the previous linearization。That is very surprising。 That's not something。We expect。

That's why it took a long time to。See this result in the literature in this explicit way。So。

 that's very interesting， that。We can integrate the gyroscope data。

 and we can propagate the error independent of the orientation estimate。That sounds nice。Given that。

 we。Solve the atitive estimation problem frequently。

Pretty much on every platform that we have an I M U。 we， we solve attitude estimation。By the way。

 the oiluler make rate matrix if you go back。There is a particular。Angel， when pitch is 90 degree。

 make the Jacoban singular。And that is a problem， too。We don't have that problem here。

So that singularity is also taking care of it here。So Genion is asking。

 does that mean for common filter， the a matrix makes the system globally stable。

In a state estimation， we're concerned with observability。We will see if the system is observable。

You can， however， of course。Look at the linear system and talk about the stability， as well。Now。

 that is true that you don't want an error that when you integrate， obviously explode。

If it's unstable。But the matrix exponential is convergent for all matrices。Right。So no matter what。

 this will converge to a matrix in the group。So we don't have。That particular concern， in this case。

So it is a very nice framework。 You don't face any unexpected。Unusual problem。Rightright， so。

So this was all true for deterministic systems。Although it's very useful。

 we need to bring in the noise tab。When you bring in the noise term， the theoretical result is lost。

Those theories no longer hold for the stochastic process。However。

The performance in practices is still very good。Right， even though noise。

Will corrupt that the the theoretical result。 Still， this is a preferred method in practice。

 We don't lose that much that we fall back onto the previous methods。

So it turns out that the right way to define for a continuous time model。The noise ceies like this。

 we add。The system made three times。A noise step。 This is not omega。 This is。Noise。We can show that。

There is an equivalent model for the aerodynamic when you introduce the noise into the process。

 and it shows up like this for the right invariant。There's an a joint that is coupled with the noise。

And that depends on the state estimates。So to map the noise where we are or back to the Lee algebra。

 we do need to know where。We are currently located。So that's unfortunately。

 that shows up for mapping the noise。But the good news is is that it does not。

Show up is still for mapping。Covariance of the process model itself。And that's good。

 That that's the bigger problem。And for the left invariant part， we get。This aerodynamics。

So this is what we will be working with because we do need to introduce noise in practice。Now。

 this was all about the process models。 Now we want to talk about the observation models。

What is a class of equivalent observation models that will work。Nicely with， within this framework。

There are two definitions that will help us to。Create that filter that we're after。

The left invariant observation model must have this form， your measurements。Which is a vector。

Because the state as a matrix times。A vector。That is constant。And we define it， we pick it。

 You'll see in examples， what to be。Plus， noise。The right ingredientvari is your measurement。

Equals the inverse of the X times B plus B。 Now， you might think this is very， again。

Limiting what it is not。 This， this coverss。A lot of problems that we're interested。Solving them。So。

 this is structure。Must be true for the observation model。 It cannot be just any nonlinear。 Now。

 a remark is that if your process model does not satisfy， there's a question for you。

 If the process model does not satisfy the group of property。Or。

The observation model does not fit into any of these two categories。What what will happen？

Can be still。Use this filter that you haven't seen yet。Somebody saying， no。No。Yes， we can。It's just。

Not analogous to that linear error propagation anymore。 It is just nonlinear。Cllman filter on lis。

Because we do need to linearize to。Build something like EKF， extended carbon filter。

But you don't get any surprising result from your linearization， because。

It doesn't possess the structure we need。So does it disqualify the problem from。Basically。

Being used in the state estimation is just the filter will be nonlinear in the sense that the extended common filter was just。

An approximation。To a nonlinear problem。Okay。Now， to show that something like the extended column and filter will converge and will be stable。

 you need a whole bunch of assumptions and lists of eigenvalues for all the terms。

And that is proven by Professor Griesel here。Sometime in 90s。A few years after I was born。呵。😊。

We don't have to go that far back。But in practice for us， the problem is that we don't know。

 Those assumptions are hard to satisfy， But theoretically are very important。 and， in fact。

 I think something similar is used to show that this。Invariant extended k filter will also converge。

So you need to show that the eigenvalues are bounded。 and they' not going to blow up。

For the systems that we were studying。Alright， so we're gonna build two filters。

 left invariant and right invariant， left left invariant propagation。

Uses this model for the process model。We use exactly what we have。You plug in the mean， the estimate。

 right， And then you get。The time evolution， we will disc discretize it later。

 and that will give us the。Typical time difference equation that you expect to see。

The state at K plus  one is。Evaluation of the state at times step care using the process model。Now。

 we have a recipe to get the errorerodynamic。For the noisy model。

We know the aerodynamic is like this。 We will linearize this， to。Find a。

 So the whole story for the propagation of prediction step。Is to find this a matrix。That's it。

 That's all you need to do。Once you have it， you can propagate the covariance。

Using the error equation。Now， there is a time， the continuous time。

Evolution equation for the covariance。 This comes from the study of something like L Q， R or L Q， E。

 optimal control and linear linear control and estimation。

It is a more special form of the matrix ricard equation。We're not going to drive it， but。

So we can use all of the nice results from linear systems here。 That's what we're doing。

Because the Lee algebra is。Just the Euclidean space， is a vector space。

So all those results are valid。This is a。Contiguous time version of that。

 you are probably used to seeing the discrete time version of it。What about the correction step。

 the correction step。We need to do a little more work。Do you remember。

 what was the correctionous step of the linear kman filter？

If I use this notation of plus for the correction， right？And T K is just to show that。

 because the process was continuous。The correction is actually discrete because observations arrive at discrete time steps。

 whereas the process model is just a continuous differential equation。

To keep the notation consistent， you see that we use T sub K。That means， the particular time is step。

In time。And T to emphasize that x is evolving with time。 So that's the meaning of this notation。So。

 for。The linear carbon filter we had。A linear correction formula。The result。

That was possible to prove it from multiple ways， consistently would give us this formula that。

You can find an optimal filter gain when it's multiplied by the innovation。

Will add a correction to the previous estimate or the predicted estimate。And the innovation was。

 what was the innovation？The measurement。Minus。Your predicted measurement。Using the sensor model。

So that was the innovation。Now， what is the equivalent of this linear update rule for a matrix league group。

It is this exponential form。Because。We had it for。If you remember for propagation。

 we were doing this。This was the exact integration。 If during Delta T， omega is。Constant。

So this is a natural way to accumulate。Update。For matrix groups， using matrix multiplication。

Why exponential， Well， because they update。The innovation will be in the Lee algebra， as we'll see。

And we need to take the exponential of it to convert it into a delta of a matrix。

 and then accumulate it。In this case， it will be a deelta rotation。So， what we realized is that。

This observation model。Is in a vector space This is。A vector。The innovation is in the Lee algebra。

 It is not on the group。That's。What is going on now， you might say that Y we see X here。

This is different from the process model， because X here is acting on a vector。

 It's like rotating it or moving it。This is not the same as X getting evolved。Over time。

 with a process model。Okay， so there's no dynamics in X。 It's just moving some constant vector B。

That's allowed that we can do that， as we will see， that won't cause a problem。

So analogous to that model， we have the exponential update。Multiply both sides by。The true state。

That will lead to。The error after correction and the error before correction， right？

Because we are at one particular time， a slice。Be for an after correction。Okay。

 so the only complicated term is the exponential term。Now， the innovation term。

Can be replicated here by substituting。The equation that we had for。

The left invariant observation model was like this， right， just substituted into the equation。

That's what you get。No。The first part。This is the inverse of the error。Times B。You have a minus B。

And then some x bar inverse times v will just be there。Larize。

 use the first order approximation of the exponential map。Directly calculate。

 drop anything that is taken order and above。 That means when you get。

This term multiplied by another of itself or noise， D them。 You only keep the first order。

 That's the meaning of linearization。The direct calculation will give you this update。

Rule for the error。L is， by the way， L is。Filter gain。I'm calling it L， because。Reserving K for some。

Mdified version of it。So， and by the way， the innovation is this term here。I'm gonna delete。

All the mess I met。This is the innovation。 If y is x。B。X inverse y minus B is the innovation。

Just like when Z was H times x。Z minus Hx was the innovation。

You need to redefine it because noise has a zero mean。White Gaussian distribution。And you can。

 I don't know。 You could define this。To be the innovation。

So we do what we can based on the rules that we have to follow， which is a matrix multiplication。

So this is nice。 We have。😊，Update。An update rule for the error， as we obtain measurements。Now。

 we only derive this once。You will never drive it again， right， when you want to use it。

We're just doing it one time。Now， remember， for the process model。

 we only needed to find the a matrix。That was our job for the correction， It turns out that。

We can make a recipe that if you find the age matrix using。This equation。You're done。

 you can just implement the filter， okay？So I simplified it for you。Now I give you the algorithm。

 This is the recipe。 Find a， find H。 You're ready to implement the imvariant columnman filter。

So the usage somewhat is straightforward。The path is involved。So if we know the observation。

The error update rule， based on the observation。Which we derived it。On the previous page。

We need to keep all the  error terms in in the form of vectors。Because this one has a wedge， right。

 times B。Reine。A matrix age， when you multiply it by。This vector。

Of the era in the Le Al will be equivalent of this to see whichdge。Or had times B。

How to get it in practice， You need to write it write it down， expand it and see what you get。

We have an example。For the left invariant model， use this or the right invari， it will be similar。

 but it has a negative sign。 So You need to be careful。If it's the left invariant or the rightvari。

So once you define。H， you can substitute it into the equation。And you get。The final form。And in fact。

 this will give you that numerically stable equation for covariance update that we had， right。Now。

 this should be familiar for you。You have it in a linear column and filter。Or E KF。

 after linearization。And N here is the noise covariance。Now， the way I'm getting it up。

 I'm taking the covariance of both sides。Take the covariance of the both sides， then。You arrive。

At the update equation for the covariance of the state。So does this also follow the same idea of？

From the updates that we are conditioning。The state honor measurements and their joint the。Goshian。

 does this follow that same step that we use for the Gaussian filters work？Its， yeah。

 the question is this is the same way to drive the previous case。It is。 But in this particular case。

 it's easier to work like this because we work with matrices。It will make it complicated。

You could use this method to derive the previous column filter。However， you。

The reason I avoided in the commonman filtering lecture to derive the filter like this is。

You need to prove that。That equation for the filter gain is the optimal gain。And it's not hard。 You。

 you minimize， you solve an optimization problem by minimizing the trace of the covariance or the error。

And or minimum minus squared error。 And then you show that that's the optimal filter game。

And you arrive with the same result。In this case， because we're working on a matrix group。

 it's easier to manipulate terms algebra Bly。And I don't。 I'm not going to prove the gain。

 I'll just refer， refer to the common filtering theory that。

We know what's the optimal gain in a vector space。You see algebraic does mean by for example。

 taking the covariance of both sides and that gives us P from our Algeic manipulation means everything that I'm doing here。

 multiplying matrices by vectors， matrices by matrices， inverting a matrix， adding terms。😊。

It's not geometric， right？Thank you。Can you repeat it Y， L， T， K。Why do we have this L here。

So the question is， why do we have this L here。Because if we don't have it。

 we are just integrating the error。We want to have a filter gain， just like。Right。

 if you remove the filter gain from common filter。We'll just have to add the innovation。Yeah。

 so this L is like the filter gain。So this is similar to K times new， right。 Now。

 once you go through the implementation， you realize why。And I might have it later。

There are some bunch of zeroes and stuff that you need to remove。Because of。

Multiplying these matrices。 andm reserving K for。The final， clean version of the filter game。

But it is， in the end， it's just the notation。So the filter gain times the innovation。

 We integrated or added using the exponential term。So to summarize the left invariant filter。

Has a process model， has a differential equation for the covariance。

Which we will discretize in practice to use。And there is an update rule。

That uses the measurement model to define the innovation。And a filter gain。To update the covariance。

And the state。 now， the filter gain。It is the same equation as in the linear carbon filtering。

Your covariance times。Measurement Jacobbian transpose times the inverse of the innovation matrix。

 and innovation is exactly the same formula。So the equations are the same。What about the rightvari。

Same idea。 You just need to。 the process model won't change， whether it's left or right。

 you work with the same。 You pick the right invariant error process。We will have to work with that。

And that has a different form。And then your equations will be like this。The first part is the same。

 the second part。Hasn't a joint them。Now， although it looks the same。

 but these matrices are not the same， The covariance of the left invariant filter。

 it is not the same as the right invariant filter。There is a way to map them。Transform them to one。

Another。But they are not the same。 You need to be careful。Not combining them carelessly。

Because ultimately， they are in a different reference frame。 One is the body， One is the world。

You won't get the same values in， in the entries of the matrix。Now。

 we follow the same ideas for the update part。I save you the headache。 And then the summary is。

Do the same thing for the process model。You have a propagation for the covariance。

Although it's a different matrix， it has， for the most part， a similar form。Correction is the same。

 however， in the writingvari， the exponential is。On the left side。

Or we can think about it as a state estimate is on the right side。Whereas the previous one。

The order was。Spped， now， this is this should not be surprising because we have two options for defining the error。

And based on that， you get to see the exponential on one side。And because of that。

 the right invari is like this。 However， we can give it meaning。

The innovation in the right invariant filter is in the spatial frame。 It's in the。Worlds Frank。

The innovation in the left invariant filter is in the body frame。Gemetrically， that's。

However we're doing it？If you work with the inverse of the matrix as your state。

 you need to flip the。F what I said。If instead of the rotation。

 you're estimating the inverse of the rotation that it is perfectly fine to do。😊，Thenan。

The left invariant innovation will be in the spatial frame， right。

 So so you get four different forms based on whether you work with the state or the inverse of the state。

 and each of them has these two forms。And it's not really important。Which one you choose？

SomeSome forms are naturally better for some problems。All right， so that's。

Think we can stop after this example， because I want to spend next lecture。

Talking about IMU and how to combine IMU and GPS， maybe in a left invariant filter。

And we don't have time。 I want to dive into。The equations in。Peace。Not rushing through them。

So a velocity motion model。Consider a robot moving in  D or 3D， The state evolves on S， E2 or。S A 3。

Just like the gyroscope。We can have the differential equation of the league group。

E now we're working with the twist， rotation and translation。So U is the input， which is a vector of。

Angular velocity or and linear velocity。It is a three vector。 if it's S E2， and it's a6 vector。

 if it's S E 3。The first question， okay， if you want to solve this problem， then you。

 you need to answer that。 is this process model group， I find。Let's find up。

So we have this process model。The group I find property was telling us that these two。Must be equal。

So plugging x1 times x2 into the equation， we get x1 times x2 times。You。

A valid the right hand side of the group of fine property。Which was this form。

F of x 1 times x2 plus x1 times F of x 2 minus x1 times the process model at the identity times x 2。

Carry on the calculations， simplify。You do get the same answer。

 so the two sides of the equality are the same。 Therefore， the system is group I5。Now。

 if the system is group of5， let's pick a right invariant filter here。

I know the aerodynamics already Pick the aerodynamics。It has this form。To find a。

 you don't need to work with the noisy aerodynamics， right， because that part is the same。

 It just has a noise。So pick the aerodynamics。You get 0。Which is what exactly what you get。

 If you go back to the gyroscope example and do it with the right invariant error， you get 0。

So for a native differential equation of the legal group， when you do right invariant。Calculation。

 you get zero。So it means that the error， the error in the Lee algebra evolves。

Based on this differential equation， the time evolution of the error is 0。Therefore， a is 0。

That's as good as it gets。Could you explain？同我。Waste on the equations that we。Had from the theorem。

 Theorem 1 was giving us the error equation。And the way to prove it is that start from the definition of the error to be right or left。

 take the derivative。And then， see。What is the class of function that satisfies that。

 which gives you the error。Group of fine property。And then the error equation ends up being like this。

 so。It's not something we choose。 It happens because of the definition of the error。

It's not something that you can imagine， easily。嗯。Define the error correctly。 Look for that property。

 You get this result。I guess I'm trying to get what the physical intuition。そう。よいせです。

Fra and then the left is within the body frame。嗯。So the air being。

The rate of change in air being zero in the world frame。While it's not in the body frame is。

I guess where kind of the mismatch is happening。We've got grasping the intuition between。

The rate of change of the error is。0。I have to think about it myself as well。

 The right invariant the。The error is like this， right。So the error is seen in the world frame。

The a spatial frame。The equation is saying that your error evolution。Basically zero。

 It doesn't evolve with time。 It's constant。Right。Well， that means that。

When you integrate that deterministic process。It doesn't add any error。If you have an initial error。

 it will stayed there forever。Right。Which is a result that something like 20 years ago。

 people knew in Islam in Ikeev Islam。 You initialize the robot with some uncertainty that will never disappear。

That's very surprising。This， I think。Based on your question。

 I this means that if you have any uncertainty， won't disappear， but it doesn't add anything to it。

Later， when we have noise， we will add the noise， of course。But just mere integration of the。

Control input。It。Does not grow the error。Which is nice moving in the group。It's free game。

I forgot that this was a deterministic system。That's why's where yeah。私の。

We do have the noisy equation in the common filter。But to get to find the a matrix。

 you can work with the deterministic model。So the problem is， the robot is。Moving in this map。

I just simulated something very simple， the robot starts here。Goes around。Back to the first spot。

We have a bunch of landmarks。It is， of course， stimulation。 You can control how much of the。

 how many you see， how many at the time， What is the frequency and all of that。

But the robot at any time maybe sees a landmark。The map is given。 This is just a localization。

The robot has a prior map knowing what's the exact location of these landmarks in the map。

So the equation of motion in S E 2 is what we just discussed。We have the twist。

 and then we integrate to know how the robot is moving。

Then we want to implement a writing Bar and EKF to localize the robot。Maybe I show you。Videos first。

So this is just the propagation step， prediction step。No， no correction， no observation。

 The robot moves around。And of course， it's just。Drifting， because。



![](img/8b0360f9e70e82a083177db9ac0792ff_1.png)

There' is noise。To the noise bill。So， the input。That the robot get。It's not perfect， right。

 That's that will make it。Juter around at some point point。

 it will get lost unless it receives observations。

![](img/8b0360f9e70e82a083177db9ac0792ff_3.png)

So when it gets some observations， it gets to correct it。Position and orientation。Now。

 the observations are very limited。 as you see， I'm not throwing a lot of observations if you。Get2。

3 observations at a very high frequency。

![](img/8b0360f9e70e82a083177db9ac0792ff_5.png)

Basically， it's perfect。 So the reason I'm not doing that because it will be so good that you don't see the covariance。

 So I'm cutting down on the observation so you can see the covariance grows as the robot moves in the prediction step and it shrinks when you get an observation。

😊，In practice， you want high frequency observations。Much as possible。

 because that makes the filter works better。

![](img/8b0360f9e70e82a083177db9ac0792ff_7.png)

So， back to。

![](img/8b0360f9e70e82a083177db9ac0792ff_9.png)

And you have， you have the code for this。 You， you can go through it。

So we have the rotation and position。Once we discretize the equations， the first part is。

she be familiar？Integration rule on legal group。Previous state times， exponential of the twist。Now。

 the aerodynamic is。0， so the a matrix is 0。From discritization of the linear system。

 I think a while ago， I shared the link。 but if you don't remember， I can reshare it。

If you have a continuous time system， there' is a way to discretize it。

 You need to take a bunch of integrals。In this case。Well。

 the transition matrix of the system is basically exponential of integral of A， D， T。

You can approximate it for a Delta T。For sampling time。If assuming a is constant。

But in this particular case， a is constant all all the time。So for a Delta T time， this is。

A very easy discretization， and it is， in fact， the identity because a is zero。So， plug it to。

The discrete version of the propagation equation for the covariance。

ThenThis is not different from a linear common filter。It a state， you had F sigma。F transs， right。

 This， I'm just using different notation。 This is， this is your F。Because it's the right invariant。

 if you go back to the equations， you need to use the a joint to map the noise。

Because noise is defined in the Lee algebra。You have to map it where you are。And naturally。

 the ad jointt shows up。And the algebra calculations。So the covariance is propagated like that。

 which ends up being the previous covariance plus some noise term。Which makes the covariance to grow。

Now， when youre given a continuous time process model and noise that covariance is called the noise density is not the same thing as the discrete times。

 discrete time noise covariance， a simple way to discretize the noise。

Density covariance is matrix is。Using the state。Transition matrix。

To map it and times theelta T again， follows from the sctization of linear systems。

And we can approximate it like this。Right。So use this equation if。You're lazy， and it's usually good。

And you do need usually to tune it。Right， in your assignment， that's the problem。

 You don't know the noise。Even if the data sheet is telling you。

If you run a robot in cold and warm weather， that's， that's very different from。

The numbers you reading from laboratory。Callibration。What about the correction？Now。

 this is new to you。The correction is。A right imvariant。That's why we chose a writing variant filter。

Because you know that the observation。对。Let's say this。 Why is it。

Measurement of the landmark location， X Y， right。It's something like this。Right。

 if I have a 2D robot。Landmark from the map。And this is a robot。Position。

 so the measurement model for this type of problem in localization Islam is that。Well。

 you know where the landmark。Is in the map。That's。That by the way， vector B。It's constant。

 M is given。 I know it。It's hard coded in my algorithm。Now， when I see that landmark。

The difference from the landmark and the robot position。

 that's the vector that will connect the robot to the landmark， right。Rotated。With our transpose。

To be in the body frame。That's what your sensor is actually seeing。The sensor will see a relative。

Position。Rang or bearing or XY， whatever you want to calculate。So the sensor will not observe。

 of course。Local position of the landmark。Now， we average this into a matrix like this。

And then we recognize that， well， this is x inverse。We call this B。So we call B。

 whatever is constant and is convenient。 It makes this equation to。Match the rightvari。Plus。

 some noise。 I need to append 0 to。Make sense of the dimension。

And I'm working with homogeneous coordinates。 So I have these。Wan。Appended into the vectors。

So the observation is naturally right invariant， and it does have a very simple geometric meaning。

Although when you look at it like this。Might be a little obscure。So。For the correction。

 we need to find age。For the right invariant， you do have a negative sign。

Expand the twist in the Lee algebra， carry on the calculations， Try to separate it into the vector。

 Whatever is left， That's your。H。It's usually calculated like this。Okay。

 expand it and then find the matrix edge that satisfies this equation。Notice that。

We have a row of zeros。So there's gonna be a bunch of zeros and oneands to match the dimensions of these noise and vectors and matrices。

You need to implement it， and get a。Feeling about it。You can do better by getting rid of those。

Someha in implementation。Or you can just be inefficient。Track longer or bigger matrices。

One important problem。 Now， we are able to do observability analysis just using linear systems theory for a problem that was thought to be nonlinear because of the rotation。

 And this was not possible。😊，So the observability analysis in the Lee algebra， using the。

Meeasurement model。Before form the Grian using。The measurement， Jacoban and。

Which is a constant matrix and system transition matrix。 And it's a constant。

 It is clear that the first column is a linear combination of the second and third。

 The angleular velocity was the first column。 first dimension of the state。

So the rotation is not observable by just observing one landmark。

You will never make it observable by just getting one landmark and correcting sequentially。So。

 let's make an attempt， and。Collect two landmarks， and run correction。

With two measurements at one time。When you do that， you need to stack your measurements for。

This particular measuring model， you need to make a block diagonal matrices， stack B and B。

Two measurements。When you do that。You can see that the Gramian is full rank。

 The state is observable for we two landmarks。Orientation is observable。 now。

 You can try it in 3D to see what happens。 How many landmarks you need。

If the robot was a quadruptor moving in 3D， you wanted to localize。Is it 1，2，3。

You can do it exactly like this。So take a look at the code。

That will replicate what you saw in the video。And。That's the end of today's lecture next time we'll talk about。

IMU， an I am U GPS filter。And revisit some of some other examples。



![](img/8b0360f9e70e82a083177db9ac0792ff_11.png)