# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p08 -08-Lecture 08-Robot Motion & Uncertainty Propagation.zh_en -BV1UfAmeUE3e_p8-

Welcome to lecture 8。 We will continue on。The topic of matrix Ligorous。

 but we will put it in the context of robot motion in this lecture。Let's see。Where to start。

So I I will be writing like last time。So we can get engaged into the des and some of the equations that。

They might not be so relatable if you just see them in the slides。 So I will be writing them down。



![](img/fed2b48271a9206517f6f64152c9748e_1.png)

Okay。

![](img/fed2b48271a9206517f6f64152c9748e_3.png)

嗯。

![](img/fed2b48271a9206517f6f64152c9748e_5.png)

So， today's topic is on。Robot motion in exponential coordinates。

And I will be relating this to signals that you read from the robot， not just talking about it。



![](img/fed2b48271a9206517f6f64152c9748e_7.png)

In the abstract way。Let me。Insert a photo。

![](img/fed2b48271a9206517f6f64152c9748e_9.png)

Who knows what's this robot？Maybe you have it at home。You bought it and you get disappointed。

It wasn't cleaning as good as you thought。 I fell for that。And I can' get my money back。

So this is the famous roomba and。The base was actually used to build a robotics platform。

 called Tlebot。There waster but one。 The base was Roomat。 Then there was Tlebo 2。

It was something else a Korean company made something similar。 But。

 regardless of the Mcchanics design。It's a ground robot。 It's supposed to move。嗯能。

Even a flat surface， it has two wheels。And it can move forward and rotate。 Okay。

 So that's how it operates。What we want to see is how to model the motion of this robot for state estimation and perception tasks。

 not necessarily for control。 And I will point out the differences and what we can ignore for perception。

If you don't want to be too picky and you just want to track the motion。So this is Roomba。

 So don't buy it yet。And it's also so noisy。Every time it starts working automatically。

 I'll just shut it off because it's just too noisy。So what's in the bottom？You probably know。Now。

 we can ignore all the。Vacuuming part。What I'm talking about is about。The wheels。

How the robot can move becomes a mobile platform in the environment。Of course。

 we want to accomplish some tasks， too。In this case， the robot is vacuuming。

 or maybe you have a camera you want to。Monitor baby， right that。That's a reasonable。Application。

 people put a camera in baby's room， too。Make sure the baby is safe。Well。

 you can have a mobile version of that， too。So， the wheels are。Like this。Now。

 my my question for you is that how can you move and rotate using just two wheels？

That can only rotate about a fixed axis。The wheels don't rotate。

 There's no yaw or a steering like a car like Waill。 They're just static wheels and rotate。

How can the robot move and rotate。And is that possible？It is， yeah。

If the wheels move at different speeds。It causes the robot to rotate。If they move。Perfectly。

At the same。Vlicy。Speed。Then the robot will move forward。Now。

 how accurately you can command a robot to move with that velocity。And track a reference trajectory。

 That's the problem of trajectory， planning and control。In a control course for robotics。

 the concern is that I have a reference trajectory and reference velocity。

 I want the robot with a particular physics and configuration and actuation to track that。

So that whatever is the framework I can accomplish some task and move around。That's not our concern。

 Our concern is that the robot is moving。We will ignore the cause of motion。

 which could be that controller or planner， or it could be that somebody manually driving the robot。

 Now， given the commands for the motion， I want to estimate。The trajectory of the robot。

That reckoning track its trajectory ormetry， right。

 And then later put it in the context of localization。

 If I have observations from a camera and other sensors。

So this is the problem of a state estimation and perception。So we can ignore the cause of the motion。

 And because of that， kinematics models are very common because in kinematics。We do not care about。

The cause of the motion， whereas in kinetics， the dynamics when the mass and inertia are involved。

We do care about the cause of the motion， force and torques that apply to the robot。Okay。

 so in a lot of models that you see for a state estimation， we。Very much like to ignore that model。

 the mass and inertia。Why， because。Those are very uncertain parameters。

They're very platform specific。 They will change quickly if you load their robot or。

If the robot is in a way that its movement can change the center of mass， right。

 you can rapidly change the inertia。 So there are a lot of concern that are very important for control。

But for state estimation。We can have the luxury of just ignoring them and then come up with other ideas。

 One such idea is this add an IM U。 You might talk about it later in future lectures。

Which the idea is called strap down， Str an9 U on the robot and bypass its dynamics。

Because the IMU gives the acceleration。An angleular velocity rate of change。

 Then we can track the robot。Basically， without knowing its actual dynamics。

 So we are concerned about the dynamics of that tiny sensor attached to the robot。Okay。

You can do that with airplanes。 It works。Because they are moving together。

 If you know where the sensor is located， Obviously， you know where the airplane is locate located。

So there is really no need to have a team of people sitting down and modeling the dynamics of that airplane。

With very accurately。Now， however， I'm not saying that for particular application。

 you might not be able to use the model。To make。Your algorithms better。

 That could be a research topic for a particular application。

 But for generic methods that we talk about here， we tend to bypass that model。But today。

 we will talk about a first order model， something that takes velocity。

So we can think about the model of this robot as。Something that looks like。This picture， I have。

Some reference frame。Then there's a robot。With some， I'm drawing the wheels on the side， but。

You get the idea。They have some。This stands， let's call this。B。They can move with some velocity。

And then we can have。A frame that is attached to the robot。

And then maybe this robot has some angle Theta with the。Horizontal reference frame。

 world frame or fixed frame。That we would like to track with respect to that frame。Now。

 this wheel probably has some。Radius。It's fixed。Sparly around。Although it's not， but you assume some。

Average radius， just like gears。 when you design mechanical gears。 We have holes。

 but you have some patterns。But you assume a nominal radius for calculation。Of design。

 a stress analysis or whatever。Else you want to do。So we have a radius。

 And this wheel is moving with some linear velocity of the right wheel。😊。

And this is caused by the angle or velocity of the right will。 So the motor is a D C motor。

That rotates the wheel， right， and。The linear velocity。

Is caused by the rotation of the wheel times that radius。So。The velocity of the right wheel is。

Real radius times。Anngular velocity。This is 2D In 3D， you have。All that cross nonsense and。

Complication。For the left wheel， you write something similar。Now。

 what is the velocity that we get for。The entire robot， the frame that is attached to the body。

Is experiencing some linear velocity and angular velocity as an， as a consequence of these。😊。

Roations and linear movements of the wheels。Well， in this case， it's。

Somewhat trivial to model the velocity that a robot moves forward。

It's the average velocity that both fields are moving forward。It's the middle point， right。

Two points are moving。 And then the middle point is moving with the average of。

The velocities on both sides， right。Because if one of them moves like this， the other like this。

 it's a rigid body。 The middle point is in between。So， you can interpolate。

So if you move your frame to。A place that is not symmetric。

 You can interpolate to find out what's the equation。 But that's not really the concern for us here。

 The angular velocity will be。The right velocity minus left velocity divided by。The distance。

So the deelta in velocityity of two wheels。Divided by。The distance between these two vectors。

Is what is causing the robot to。Or half of it。Is it this sense or half of it。Somebody help。

So there's a deelta velocity。 The difference， the net difference will be on one of the wheels， right。

Let's say it's positive。 The robot is rotating。Counterclockwise。

That means the right velocity is bigger than the left。

If it's causing it to rotate about the center of this frame， then should be half of it。Oops。还要这是。

So in any case。It is always possible to talk about a linear an angular velocity that this frame that is attached to the body of the robot is moving。

That's the point here。Regardless of where this velocity comes from， we can work with that。

 We treat that as a measurement。In practice， you， of course， care how to get that。

And that's important。But our formulation starts from where we have this velocity。So， we call this。

Twist and twist。Is a vector of angular velocity， and。Linear velocity。 I mean。2D plane。We have。出。

Directions for for the two directions for the velocity， right， forward and lateral。And then rotation。

So twist is a 3 by one vector。I'm just stacking that。

 We'll see what will be the consequence of stacking the linear velocity。First， it doesn't matter。

 You， You can choose。But once you decide， stick to that， don't change it。

Halfway through manipulations of terms。So， one。Remark that I need to tell you。

Its about the non hoomic constraint。Of this robot， in this case。



![](img/fed2b48271a9206517f6f64152c9748e_11.png)

嗯。Too much。

![](img/fed2b48271a9206517f6f64152c9748e_13.png)

For my computer to handle。

![](img/fed2b48271a9206517f6f64152c9748e_15.png)

Who knows what's a nonharomic constraint？えすね。可保险。Can I explain what is B？

V1 and V2 is a vector of velocity。 It's a linear velocity that the robot is moving。 V X and V Y。

But I named my body frame E1 and E2。You could name it X and Y。So what is a non hoomic constraint。

这能力是多长时间？Or more generally， you can't just translate in any direction you want at any time。

So physically， we can't just move laterally， right？You can't just command a robot to move sideways。

 That's just not how it works。It needs to move forward， and rotate。Now。

 that doesn't mean you can't go to places in the plane。 It's， it's controllable。

You can control the robot to go wherever you want what。

You have some constraints on the trajectory that you can follow and。Execute。It's not arbitrary。Now。

 the theoretical reason for that is because there are sometimes because of the configuration of the robot。

 there are constraints and the velocity that we cannot integrate。

Those constraints directly as part of the equations of motion of the robot。

Those are non hoomic constraints。 and they are very important if you want to control the robot。

You can't just command anything。It's inconsistent with the physics of the robot。However。

We can ignore that。Because we are not commanding the robot。 We are estimating where the robot is。

 The command was executed already。So we can make our life easier and think about it as。

A rigid body that can move around。 and based on particular velocity， that is， of course。

 respecting that constraint， because the robot is executing that velocity。

 If you're trying to track the location of the robot， pose of the robot。

So that's why you see in estimation， we can work with models that are not necessarily causal。

You cannot do that in control。So that's one difference。 It's good to be aware of it。

 And that's the reason we can drop it。We collect what's happening。And then we're trying to estimate。

The Po。It's not the same as the robot is trying to。Ignore the constraints and execute the command。

 okay。The duality between control and estimation should be clear。At this point。

So what is the non hoomic constraints in this case？So， the velocity。Projected。

Along the first axis projected to the horizontal axis， right。Is it the other way。

 So the robot cannot move this way， right in this direction。How would you write this。So part of the。

Velocity that gets projected to that line， is redundant。So if you have a velocity。

That is pointing in some direction。If this is the projection of that velocity in。Bedline。

And we're not going to dig into it specifically， but this constraint will。Be always there。每一个人。货比。

Can you point out why so I can fix it？Suppose the left fuel is not moving at all and it' zero。

And so c it's a rigided body。You're right。 Yeah， so the net。

Velocity will rotate about the other wheel。That's what I had， then I doubted myself。Okay。

So I do not need to update my notes。That's good。So you got the argument was that I was wrong because if there ever a Delta。

And the other wheel is relatively stationary。That becomes the center of rotation。4을8。

Oomega is the same angle。That's right。 The angleular velocity and acceleration of all points in a rigid body are the same。

They experience the same。Rotational movement。They do not experience the same linear movement。

The farther they are from the center of the rotation。

The linear velocity and linear acceleration will be higher。有き調。在这个。的。What I mean by V1 and V2 are。

These velocities。Now， V， too， will be always， for this particular robot。

 If you read the velocity from the wheel encoders， the V 210 will be always 0。😊。

It just doesn't exist。In general， that's not true， why。Well。

 the obvious answer is because that's just how。The robot is， it can move literallyally。

If it's another platform。Or even for this one， what are the problems with just reading the velocity from the encoders。

Use red。Yeah， if I lift a robot。As an extreme case of the slip slipage that you talked about。

 I left a robot。And then you go as fast as you can。You just keep integrating velocities。

It's got nothing to do with the interaction with the environment。

 because the reason the robot is moving is because of the friction force。On the wheel。

 which causes the forward motion。So that's a problem and it's a big problem。

So you need to assume an ideal interaction with the environment for this model to。

Give you a good result。 And that's the problem。 That's whydimetry usings this method is very inaccurate。

For the non no con。We said it's an expression。Do you want to B2， but is it？

I thought my idea was that we can do more on too。です。Right， in the body frame。

That's what we should write， right， I think I need to talk about global velocities if you want to write it like this。

Is that right。So in the body frame， we are talking about V2 being 0。 We can't move。

You could write it in the reference frame。 Then you need to bring in the rotation。We。

 we don't want to。Divevert the lecture to that。 But if you're talking about control， then。

That comes up， and then becomes very important。So in any case， we have。The twist。

 the linear velocity and angular velocity。 And now， you know。

 it might not be the best source of information for tracking， but。

It's a good model because you could get this from a camera。 What if you have a depth camera。

 and then you read。😊，Body velocity from。An attached camera。

That won't be too bad because that's how you move。 the flow of。Deth， then。Image， the vision data。

Is related to the egomotion of the robot。Regardless of what robot is going through。

 even if the robot is flying， that， that works， that's accurate。It has other problems。

 Maybe it's dark， maybe the environment is featured less。

Maybe it's hard to track and estimate visual。 Those are different challenges。

But that can be another source of。Getting the body velocity。So in this picture， for example。

 the carpet is a problem。 The robot is going on a bump。 We assume it's flat。 The engagement with the。

Carpet is。Different from that heart surface And that。

 So there are all sort of noise and inaccursis in the model。I was'm curious still。

So why is it that we？😊，Followinglow。K1 and B2。The body frame is supposed to be footprint because if you're doing your around the。

Whatbal brain for doing around bikeframe， like you said， E two will always be zero。😊。



![](img/fed2b48271a9206517f6f64152c9748e_17.png)

But it it's in the global brain and need too。Excellent question， that's why I have this meme ready。

I anticipated somebody will ask this。

![](img/fed2b48271a9206517f6f64152c9748e_19.png)

。So I took my time。Prepare this。 So the question is。

Why don't you use global coordinates like a normal human being。And you keep pushing us to use。

These body frames and V1 V2 exponential coordinates， right。So， I think。

You're ready to hear the truth。The robot motion is in exponential coordinate， as we will see。

And I'll have to go through the equation。 You see a deep reason why。But also。

 the robot as a physical being。Or an animal moving。

Does not have any understanding of the global frame。

 all the interaction with the universe with the environment is in the body frame。

Everything is in the body frame and how the robot is moving。It's a fiction to。Right is。这。

Assume that there is a reference and everything in the universe is tracked with respect to that reference。

Right， it is convenient for us in engineering。Now， looking at the problem in a more canonical way that is working with the body attached frame。

Which leads to twist。And then we know S， E 2 and S。Or two are naturally。

Related to that sort of velocity， the Lee algebra。Then we see that we can come up with models that。

Are more accurate when describing the motion of the robot。And， in a sense， are easier to work with。

So， the goal that。I won。To achieve in this lecture is that at the end of this lecture。

 we have a formula for propagating uncertainty of this motion。Do it in the global frame。

 It will be a nonlinear problem。You need to linearize， use one of those three ideas。

Whereas when we do it in the exponential coordinates， it looks like a linear case。

So it's exponentially linear。So it becomes very easy as if you're working with a linear systems in some other coordinates。

So it makes it the right choice。For modeling， right。So the truth is it's just the right thing to dos。

Naturally modeling the problem。Now， those nonlinearities are very nasty in 3D。

 If you model the kinematics and dynamics。ブリの。Yeah， it。It makes the models really。

 really complicated。Unnecessarily。Because nobody cares about your world frame， right。

I guess Im just thinking of thatde。Translate。All thanks。YourP， you welcome to room。We have this this。

You know， state of okay， you know， like there's this corner。We do have thes care time。

 so we have left them right。They also have these。年合同认。I should say like。

So that's something thing that。Also have been in these kinematic problems like robotics or exactly。

The global tracking with respect to the global reference， you mean。Really。I guess， like。

Like micro ver approach。Find me where you are。And。So your question is， when， well。

 when we want to localize， we do need to track with respect to a reference。 Yes。

 we will localize with respect to a global frame。But the way we track and integrate， it is。

Incremental movements of this body frame。So we want to do it right in the body frame and then accumulate it with respect to a global frame。

 We do that。I do not say that。We should track。Everything， relatively。

But the accumulation of these deelta terms in the body frame makes it very easy。For。

It makes it easier to write down the equations， to code it。Once you。

 you have a grasp of the power of this linearity in the exponential coordinate。So。

 let's continue with。2D rigid body。 So our robot is a 2D rigid body。and。We talked about S， O，3。

So you can already guess that we can have also S E2， S O2。So S， O2 is just a rotation in one plane。

 One of the three planes of that S O3。 S O3 was the simultaneous rotation of。3 perpendicular plane。

 S， O2。Is the rotation of one plane。You can pick X， Y， then Z is normal。

 That's very common to work with。Z to be the height。 And then we have our 2 D X， Y plane。

So these are two by two matrices such that again。The transpose is the negative of the matrix。

So everything we establish。Before， it's true。We're just changing the dimension and makes it very convenient。

So in this case， it's。Simple and maybe odd that omega is just a real number， But omega hat is a 2D。

Skire matrix。So omega is just a single number。That's the angleular velocity about。The Z axis。

 normal to the plane。And this is in S， or2。Now there is another group。Its E2。

Which is a mixture of rotation and translation。So instead of just angle of velocity， we want to have。

Angular velocity and linear velocity。 But linear velocity。It's just the usual linear movement。

The way we。Formed a fine groups， we can just add a vector to track。The linear velocityloc。

 So it's just a clever way of ironanging it into。This matrix。And。This is an S， or2。

And we is in our two。So V is your familiar linear velocity vector。This must be very important。

 This must be0。Because in homogeneous coordinates vectors。Had 0。Because we can add them。

 And then if there is one， it will get awkward， we get。2 for the homogeneous coordinates。

So we are defining to see hat。To be this。Overloaded notation。



![](img/fed2b48271a9206517f6f64152c9748e_21.png)

It will be okay。Because， you know。This is in， let's say， S2。Or three will be exactly the same。

 Your sysymmetric matrix is， of course，3 by3。Now， it's not a source of confusion。

 but it's an overloaded notation。It's not exactly ssymmetricsymmetric。Okay， but because you know。

 this is part of the rigid body group， that's how we arrange the school notation。

The hat or wedge notation。So，This is the Le Al algebrabra of S， E 2。S。

 E2 matrices are in form of rotation， position。Arage in。In this case， a 3 by 3 matrix。For 3D。

 it's 4 by4 matrix。Okay， so it's just a 2D，2 by 2 rotation in the plane and a 2D translation。

So there's a comment in chat， I don't know if it's directed to me or not。

You might want to clarify harsh， if it's for me。That was it。So。

 that was in response to like when you asked about hoomic or non hoomics， so that's old。Okay。

 so you were just commenting on the nonhaami constraint part。Yeah， okay， thanks。All right， so。

I will talk about the process in。S E2 will be exactly the same for S E 3。 In fact。

 it will be very similar for any dimension。But we care about 2D and 3D。So a deterministic process。

In the discreteet time。It can be。De finded like this。So your next pose。Is the previous pose。

Multiplied by。A deelta pose。That the robot moves。 This is the discretization of that differential equation that we talked about it in previous lectures。

You can define this to be some process model。In a sense， this is the easiest way for the groups。

 matrix league groups。You can have other types of processes as well。Now， if you have。

A control input command。 that is a twist。And it belongs to。S， E2。

 then you can think about this Delta motion， capital U。To be the exponential of this。

You in the Lee algebra at times。Salm deelta T。Basically， integrated to give you a deelta pose。

And exponential is the matrix exponential。And theellta T。Depending on your sampling time。It's some。

Time at K plus 1 minus T K。Small， very small， usually。10 milliseconds，1 milliseconds。

10 milliseconds on 0，00 milliseconds。Think for encoders。

 you can think of it as1 millisecond because encoders work。Opererate at very high frequency，000，2000。

Thats。Then we want to talk about。About a noisy version of this。Maybe I should write it here。

So this is deterministic because there is no uncertainty or noise。

Now we are ready to define noise in a way that we can handle it using this exponentiation。

The noisy process。Is。Very similar。instead of capital U。

 you could directly write the exponential as well。 I'm just emphasizing that this is a deelta motion。

That' very accumulating。So the noisy process will have some noise。In the Lee algebra。We are。

Aware of how to define。Let's say you zero mean by calcium noise in a vector space。If。WK。Is。

A vector such that is。A 0 mean white Gaussian noise with 0 mean a3 vector， and some。

3 by three covariance。We know this。 This is just usual。Statistics in R N vector spaces。

What is interesting is that we can。Think about this noise as a per version of some twist。

In the Lee algebra。Then we put it in the matrix spaces using this wedge。

And then you take the expon of that。 This will give you a perturbation as a pose in the group。

 which is nonlinear。If we directly work with。Opposed in the group。That's very difficult。

 That's not nonlinear。Because you have all the interaction of these rotation and pose。

It's too complicated。This is a very clean way to define the noise。So， W。Hat or wagedge is in。S E2。

So we just learned how to define。Noise terms， analog to what we were doing with linear systems in linear column filter for matrix lead groups。

So the rest of the lecture is。To derive。An equation for the error so that I can also propagate the covariance。

Because if you。Have。Your process model， you can just multiply them and track the pose。

What we want to do， we want to attract the covariance as we move。That's important。

That will give us the uncertainty of。Motion of the robot having rotation and translation at the same time。

 That's the problem。So， I'm going to define。The left。Invariant。Eror。Writing it in red for you。

 the left invariant error。Is defined as。Exponential of some equivalent error in the Lee algebra。

Because of。Lee correspondence theoryorem。In league groups， for every Le algebra element。

 When you take the exponential， there is a group element。

 That also follows from the fact that solution to the first order differential equation。

Always exist locally。So when we talk about the error as opposed。This ada。

There's always a term in the Lee algebra。 You can take the exponential of that to get that。

 whatever it might be。Now， there is a inverse map。 This is called log map。 We don't need it yet。

We can take the log， which is a matrix logar。It would pick the post to。That element。

 but we don't need it yet。Now， we define this error to be。The inverse of the troop post。Multiped by。

Some estimate of that true pose。Is that reasonable。I cannot subtract two matrices。

 I only need multiply them。When the pose will show the perfect。Orientation and location of the robot。

When this error will give me the identity matrix。Because that means the true rotation and the true pose。

So this is a equivalentval of subtracting two vectors for the error。For matrices。

 we have to do it like this。We only allowed it to perform matrix multiplication。Now。

 why it's left imvariant。It is left invariant， because。If you have。Another group element。Let's say。

 for。Now， this is true for any league groups， but I am writing it for S2 here。For any。

Other element in the league group。You can have。Left translation of both terms。

So transform both terms from the left side by a group transformation。

Rotate and translate them somewhere。Whatever might be。Then， compute the error。You will get。

The same error。 So this definition of the error is independent of where you are。

 no matter where you are， the error。Is always like this。

 It's independent of we moving the reference to somewhere else in the group。 This is nice。Good。

Change your reference。 It won't change the solution。

As you might expect that from a consistent algorithm。

You can do it for the next time in future lectures。 we will talk about it more。

 You can have a writing variant definition， as well。Then x inverse is on the right side。

He said this shows that what。To translation。It is invariant to the left translation by another group element。

 So it's invariant under the group transformation。Is it the error。Yeah， the errorda， the error this。

This term is invariant。When I translated。X inverse， and。X bar， it didn't change the error。

X bar is something like your mu in Carine filter。Its an estimate of the true post。Whereas。X itself。

 is the ground truth。嗯，So you want意。Qu。 and you know that。Don't you already know the truth？超 you。

To that ex reverse not more than true acts。The question is how would you compute the error？

If you don't know the ground truth。One answer is that we're going to derive a filter that even though you don't know that ground truth。

It will behave in a way that it will always converge to that。The arrow will converge to 0。

 That's the magic。The next answer is that what is the ground truth。 you don't know。

 Maybe you collect using motion capture， and then you want to evaluate your algorithm。

You could evaluate it。If you want to define an error using your pose， you can use this term。

Yeah your questions。The账片OK。WK health。Should it be within S3， because it's。BecauseWK are。

The question is， should WK wedge here？Be in S E 3。No， S E3 is a six dimensional space。

 Your vector would be in R 6 because you have3 for angular velocity and  three for linear velocity for S E 2。

We have one rotation。About the Z access。 And then we have two terms for translation。

 So it's a three dimensional。Problem。Movement of a rigid body in 2 D plane has three degrees of freedom。

Right， it comes from there。And the second question is。How did how to derive the red。The parent。

He is repeating。This term。I did not derive it。 I defined it。I defined。对。I want to talk about it now。

That's a good question。 I want to talk about。So I'm going translate your question。

 Your question is that why this is the right way of defining the error。Deep on， you're asking this。

And Im， that's what I'm going to talk about now。 if you bear with me。

Because I could define it and say because I said so。That would damage our friendship。

So I'm gonna talk about a little why this is the right way of doing it。But if you're writing a paper。

 you can start from defining， you don't want to go forever。

To talk about why this is the right definition in a。6 page paper。 It takes  two page 2。Explain that。

 right？So you read a paper or document that is short。 say， will define the error like this。

And that that's what you get。There's no space for explaining it。We need。

 we need more time and space to elaborate on that。Now， why。This is。The correct way。

To define the error？And we got try we will try to answer this question。So， x is。Rotation， position。

Average in a matrix。X inverse， as you know by now， is R transpose。

Negative of our transpose times the position。Because when you multiply them， you get the identity。

Now， I'm going to tell you that。First。Rotating。Sorry， first translating。And then， rotating。Will'。

 give you。This matrix。Because you would multiply this to a vector， right。

 That means you're translating the vector first。And then whatever is the result。

 you're rotating the vector。First。Translate。Then rotate。Whereas if you first。Roate。And then。

 translate。You get the pose that we have as part of the rigid body group。

 So the rigid body is telling you that。First， align your heading and then move。

This is not the same as first moved and then alone yourself。

You end up completely in a different pose。 They're just not the same。

 So first rotating and then translating is not the same thing as first。Translating and then rotating。

And Al Bly， we can see that。Because we know that they are the heading。

Will basically guide us to a different place。 That matters a lot。Now。

 what is the consequence of this for the definition of the error。

Because if we do not care about this structure， this group of proposes are defined and interactive。

The way these post terms interact with each other， right。If we don't care about that structure。

 we might end up with an error definition that is inconsistent。That's the root of the problem。

So you can， for example， you can also multiply。Rotation， rotation。Times position。

 which is first translate， then rotate。 You can multiply it by a vector x。What you get is。

Something like this。In fact rotation， that means you first move and then rotate everything。

Whereas the way rigid body transformation。Is defined as a mix of a rotation and a translation。This。

 this means。Rotate。Then， translate。So they're not the same。Now， for case。1。The error will be。

Inverse of the true poet。And inverting this is not difficult。 It's the inverse of two。

Theupupd rotation and translation， and you flip the order。

 universal translation gets a negative sign。An inverse of a rotation is just its transport。

Within that bigger matrix。So what。We get what the definition of the error is。Al right， so this time。

Is basically。And they multiply them， and they multiply both termss， you get。The results I showed。

So the rotation part seems okay。It's that inverse of the rotation times。Estimated rotation， or bar。

And the translation part is something。 we'll see。What it means。Now， for the second case。

Which is the way we defined it。 And that's。Something we call it the correct way。

The position ends up being。Different。Now， what what does it mean。We cant factor our transpose。

 Then we get。Position estimate minus true position。Now， the position estimate minus。

The true position。It's relatable。 Something with respect to some reference is a delta of position error。

However。In what frame。We are looking at the error is important。

When we define the left invariant error to be。X inverse x bar。This means。

According to the composition rule of rotation and poses。This means。

To have this error delta in the body frame。Because theyre multiplying。

The true value ins from the left side。Right。In the same way that you buy this idea that if I have a pose using those frames。

I can multiply a deelta pose to track。Well， if you multiply。Both sides by inverse。

It will give you this deelta motion。That is the definition of this error。So to be in the body frame。

 this our transpose for the deelta position is necessary。 Otherwise， it won't be。

 We need to compensate。This rotation to move it to the body frame。 So geometrically makes sense。

 whereas the other way。It is moving your。Estimate to the body frame。

 but keeping the true value in the。Global reference。Now， subtracting these two。

It's problematic because they are not defined in the same frame of reference。Right。

 if you want to subtract two vectors， you want them to be in the same reference。Coordinate system。

Are you thinking that that more？One specific crank to another specific crank or like。

Yes everybody there。Ask that question， but。I'm not understanding how you know that like。

This result means that we're in the body frame。Oh， that goes to the previous lectures。When we。

When I showed that。So the question is， how do we know this is in the body frame？

 If you remember in the in the last lecture， we elaborated why。The equation of。This type。

The angular velocities in the body frame， right， and why。For this one。

 the anglengular velocity is in the spatial frame or fixed frame。

 So this is the topic of the previous lecture。😊，Which， of course， this。

Angngular velocity that if you integrate it， right。

 it would give you exponential of this omega Delta T， Delta movement。Equals。R K。Inverse times。

 R k plus1。Or transpose because it's the rotation。For this one， we get。RK plus one times。RK invest。

 This was in the spatial frame。 This was the topic of the previous lecture。

So multiply the invest by from the left。 you're getting this delta in the body frame。

In the discrete time sense， this Delta movement is happening in the body frame。

If you multiply it from the right side。This deelta movement is happening in the fixed frame。 Now。

 if you start working with the inverse of poses， you need to flip this definition because we're working with the pose directly。

With respect to some fixed frame， if you start tracking everything with respect to the body frame。

 that means you're working with the inver。The pose， then you have to obviously flip this。

You can ignore。If you didn't follow that， that means you have no business with the inverse of the poll。

You can just stick to what we talk about here。So geometrically。

 this is consistent with the framework we've been constructing so far。We understand what it means。

 in terms of。Frames and movement of these frames。Now， in the literature。People。Of course。

 they didn't define that。 I want to first。You know， translate or rotate。

 Nobody thought about it that way。That would be still good。Because you're still thinking about that。

Group。As。A coupled way in the sense that the rotation acts on the translation as you move。

A more natural way that we would think about it is that， well， I have the translation。

 and I'm going to define the translation error， right。This is just。His story for later。

I have the translation， So I'm going to define my。Translation error to be。

I don't know whatever you want or P bar minus P doesn't matter。

Then I'm going to define my rotation error to be maybe something like this。So what happens is that。

If we get it right， it's。Pty should be P， but anyway。

So what happens is that the rotation part is correct。As if you just work with SO3 or S O2。However。

 the translation error does depend on the rotation， it's not independent of that as we see。

 because we need to map this delta translation in the global frame。

 or fixed frame through the body frame。If we're going with the definition of the error to be the left imvariant。

If you think about it in a decoupled way， this destroys the structure of the group and error。

 And this leads to。Terrible consequences for state estimation and filtering。

 which is a topic of the next。Two lectures， maybe。So this is more natural， and it's not unusual。

 That's how we would think about it。 If you just think about translation and error。

But these error are not decoupled。 You need to think about it as a group。

There is a mathematical reason for that because S E 3 is a semi direct product of rotation and translation。

If you think about it as a direct product， as a Cartesian product of two sets。

 then it breaks down destruction。But physically。That's what they thought。And。It works。

 but it breaks the structure， and we lose some of the very nice properties that we can get for。

State estimation。So this is。A teaser for next time。So I'm going to drive。The error term。

So the error was exponential of。Somely algebra term。With the left invariant definition。

This is the error。Seen in the body frame。My。Estimate。

My true value is basically the estimate times sum error。I multiply。Both sides by x from left。

And then from left， I multiplied them by inverse of this exponential。反 then。

The property of the matrix exponential is that the inverse gives you the negative of the argument。

So the true value is the estimate times sum error。 That's reasonable。The discrete time process。

Once we substitute the true value with the noisy version。With the。E or 10， we get。X。

 k plus one bar times。Its error term equals。X， K bar times。In moneyney。 can you reshare the screen。

 Oh Okay， is it good now。 no， yeah， it's good now。Thank you。That's good。 You're following。Times。

Your Delta movement， and then times the noise tab。So， something weird here。

That we need to deal with is that look at all these terms here。

And I need to shift terms to left and right to collect all the noise and error in one side。

And all the。Good parts like X square， U that I know what they are in one place。 However。

 I cannot do that because the matrix multiplication is noncomuticative。

A times B is not the same as B times A。 I cannot。Arbitrarily shift terms。So。We need。To shift。

The error terms。To。One side。That's fair。The ad joint comes in。

So they had joined the group definition for some。Lee algebra element was X。C hat x inverse。

We can write this in。A matrix form that hopefully， we drive with。Later。

So a matrix multiplied by the twist。 Take the wedge。 We want it to be this。For now， assume。

 you know this matrix。 Later， we have to derive it for each group。So it is a matrix that you know。

Now， take the exponential of both sides。The matrix， exponential。

For the conjugation will be like this。So， most of this most of the properties of the matrix exponential。

Are easy to prove。 You just expand the series and then fact terms， you show this is true。

You should practice。To prove this terms。Or you can Google and read it on Wikipedia。

 or you can ask us， we can。Share references with you。So from here。

 we get a first property that if I multiply both sides by x。I get。Exponential of。At Jo times， Cas。

Hat times x equals exponential of。You see had times。Sorry X here。So if I want to move。This X。

From left to the right， you can。You need to add。They are joint。To be multiplied。Buy your twist。Now。

 we know this story。 This is a changer basis。 You're changing sides。The way you're transforming。

 you need a change your basis。 So this is automatically， is's taking care of that。

 It is easier to just do it algebraically and derive the equations。

You don't want to think about it every time。Although you should think about it at one time。

To convince yourself。Here。This is a group version of that。 It's a function that takes the。

 takes the twist。 You can。You choose if your function wants to take a vector or。

The Lee algebra version of it。You could program it in your function to map it the way you like。我是这份。

The first one is， like f of x。This one is like。A times x。

So the first one is talking about a linear map as a function。

The second one is saying that my linear map has a matrix representation， a matrix A times a vector。

We're gonna work with this form vector， you can ignore。The other one。

Now this goes back to the fact that not all league groups are matrix groups。

 the first one is true for all of them。I mean， then the first line that I don't know what that symbol was called would that to trim have the wedge operator since your operating。

This。They're on the right side does。But if you give see a joy like。

Something like a a vector then vector as So assume for now a joining is a matrix we know we have to derive it。

 We don't know what it looks like， but we know it's a matrix。Because it's linear。

 and we can prove using properties of linear map。 this is linear。Yeah had two properties， right？

For a linear map。It。Leaves the linear combination of two vectors。Unchanged。

We can show that the adjoint satisfies that。So we， we're gonna get back to that joint。

 Let me write the properties of。Shifting terms。So if you move your eggs to。From。

The left side of the exponential to the right side， you can。 You need to add the edge jump。

 You can remember it like this。Right。那。Start from。The line before that， and 10。Turn x into。X inverse。

Because x inverse is ultimately another group term。You will get x inverse。X， right？

This gives us the second property， which means multiply both sides from the left side by x。

Then x times exponential of。A joint of x inverse times Q C is exponential of。You C times x。

 So if you want to move。X from the right side behind the exponential。You need to add the a joint。

But the inverse of x。 So the way you can remember it， you move forward add the a joint with x。

 If you move backward to the left。If moving to the right is your positive direction。

Then you have x inverse。Just just the way to remember it。Or you don't have to remember。 you can just。

Look it up。So we using the definition of the a join， it sounds like we can shift terms。

To the left and right。 And that will help us to。Write down the equation to be。X， bar K。U。

Negative of the adjoin。U inverse k times c。Times the noise term。 So what I did。i。

Shifted this U to here。Because I'm moving it。Behind the exponential。

 I will add the adjoin of the U inverse。So， I'm using the second。Property。

Here I use the second property。Now， it looks like。When we compare this with the deterministic case。

 which is， which is just x plus one times X K times u。

We have a relationship between the error at time K plus  one and the error at time K。And the noise。

 of course。So this will tell us that。Exponential of。The error。At this time is the exponential of。

Some function of。The error time K。Times。Noise。This is nice。But one big problem。

I have two matrix exponential。 How can I combine them to derive a easy to work with relationship。

 We can't talk about the covariance like this。This is all messed up。

We have three matrix exponentials， two of them getting multiplied。It's a nightmare to work with。

So the question is。好。Comine。2 exponential。Tms。So， we can。Work in the Lee algebra。

 Why in the Le algebra。Because the noise was defined in the Lee algebra。

That's where we want to manipulate。Eror as we accumulate uncertainty caused。Wide the noise。Right。

 so that's the source。 We want to be at the source where the noise is defined。Now。

 the answer to death。Is。And BCchH series。北。The good。So， the B，C， H series。

Will help us to approximate that。Baker Campbell Housedf series。So this is a series that tries to。

Answer this question that exponential of。X。Times exponential or y equals exponential。Of Z。

What is the value of Z。Right， if you want to combine to matrix exponential， what's the value of Z。

 If there's theres scalar， it's just some of them。 If they're matrices， it's not。

And you can easily verify that with bunch of examples。 You see that's just not true。

 So we need an equation。 So one major result in this to answer this question is due to。

B hair campbell and House stuff。So we get an infinite series。That says z is x plus y。

 So the first two terms are actually some of the matrices。And by the way， x。

 Y and z are in some le algebra。S， E2， S， O，3。Whatever you want。And then， the rest is。

Based on Lee bracket。And this goes on infinite tariffs。Which is not nice to work with。

there's a lot of the body of literature in this。People try to model it， solve it。

But that's for mathematicians。For engineers， were gonna say if two terms are small。

 errors are supposed to be small， right。We we're going to come up with some approximation using this。

To solve our problem。If。Both。啊。Of these two terms are。Small。Then we can say that the exponential of。

2。The algebra elements， matrices。It is approximately exponential of some of them。Plus。

 some higher order terms。This is approximation。 They must be small。 if they're not small。

 the error will grow。 There are so many terms we're dropping。

If one of them is small and the other one is not， we can still make an approximation。

 thats that will come up in。Point cloud registration， Islam postgraph。We'll talk about it later。

But for now， if both them are small。Sounds like we can get away。With this approximation。

 by just adding them。So we're operating in a small error regime。 That's。

 that's basically the assumption。So。Going back。We can summarize that。Exponential of。搜索。

The error at this time， which was the exponential of。Negative of。I joined UK in Paris。

Times the error at times is step K。Time's nice term。Using that approximation。

We say that the error as a vector。In the Lee algebra。Equals。The previous error。There's a matrix here。

Using the adjoint of U inverse times the error at the previous time step plus。Or minus minus。Noise。

 This is nice。 This is like a linear。Proropagation， formula。And call on filtering。

If the noise is zero in white Gaussian， take the covariance from both sides。

The covariance and time is step K plus one is。I joined。

The view emverse times covariance covariance at times step K times at joint of。

You investigate transpose。Plus， the covariance of noise。So the uncertainty propagation。

 the first order， uncertainty propagation for。Rigidd body transformations can be done in the linear Li algebra。

Using this equation。So we accumulate poses as we move。

We track the uncertainty in the algebra when seen as a vector space using this formula。

So what it means is that， the uncertainty grows based on。Noise。And the relative motion。

This is a very beautiful result because it doesn't matter where the robot is located。

 It is independent of your actual orientation and position in the space。 The uncertainty only grows。

 according to how relatively you move。😊，This is very relatable， because。

That's how we expect the movement to be。Right， the relative motion motion from here to here is the same thing if I'm here and moving。

 if all things are equal。For this experiment。This formalized respecting that。

That the uncertainty grows based on the relative motion and the noise。 Now。

 the noise is defined in the Le algebra。 What the a joint is doing。You move the deelta pose U。

Their joint is doing a change of basis。Here for the covariance。Because it's a matrix。

Or here is a mapping， because。That's how we map matrices is moving back to covariance from where you ended up based on that deelta pose back to the Lee algebra。

 so you can add them。Then the resulting covariance at this time will be， again， in the Lee algebra。

So you move， it maps back to the Lee algebra。Which is the tangent identity。 When you move Delta Po U。

You are at tangent space at you， not the identity。 So we'll map back to the Le algebra。

 and then you accumulate the uncertainty。So this is the meaning behind this。 if you do it。

Using the right invariant definition will be different。Then we have to map the noise to where we are。

 And you will see that。 You can do it as a。Exercise。The covariance is always where we are。

 We have to map the noise to where we are， from the Le algebra。So with that intuition。

 you can derive the writing variant case and see what happens。

So that's the insight from this equation。We're going to be defining what small means。There。

This class will always have。Small， so the question is， are we going to define the small。

Like in physics， they say any angle beyond 6 degrees is infinity， right。F。And optics， I think。

That's the definition。 So a small rotation， a small error imposition， not the absolute rotation。

The difference between。Where we are and the true traies。

Which is also a motivation for the invariant common filtering that we will see that。

There is a result using this， this framework that no matter how far you are from the true trajectory。

You can still derive the error to be independent of where you are。

 That's because of the symmetry of this space。 So the notion of how a small big will disappear because it doesn't matter。

This， this。Model， it fits into that narrative as well。

 You can Once you learn that invariant estimation framework， you can redo this to show that this is。

This can be done exactly。Although we are approximating right now because we are not aware of that result。

So， the truth is。It is independent of how small。But the truth for now， is that。I don't know。

5 degrees，10 degrees。It's like， I can't do it at mask。Test， see if it works。

 If the robot doesn't break down， it's good enough。 sell it， take your money。

 You'll improve the product when you hear a complaint。Yeah。Quious。This is nice。And the四。

What's the relationship between sigma。And the noise。The noise。Figma is the covariance of the post。

Covariance of the pose X， K。 Now， the covariance is the centralized moment。So by definition。

 the covariance is。Something like this。Right。We can only do it if you think about it as a vector。嗯。

If you。Write the twist as a matrix。 It won't work because it's complicated。

What's the difference between。对。Well， EKF is。Linearizing with respect to any coordinates。

It's agnostic to。What coordinates youre operating in。

This framework is very specific to the exponential coordinates。

It's claiming that to linearize in the exponential coordinates， This is a good way to do it。

 It gives you clean results。 So it's more specific。Then the idea of Taylor。Linearization， expansion。

However， as we will see， most of the problems that we want to solve， it actually falls。

Into this category。So， although it's more limited。Application wise。 it's， it's better for us。

To do it this way。Does that make sense because we work with rigid bodies all the time for s localization。

 mapping。State estimation oometry。If you're， I don't know， you're estimating the。Battery capacity。

 I don't know if， but exponential coordinate is come in， maybe they do， maybe they don't。

So it's not useless。 either of them， you might come across a problem that you need to use that AkeF。

Are you cave。We will formalize it next time in the columnman filtering using these coordinates。

That should clarify。So last question is。What is a joint。For rotation， we know that our。

Omega R inverse。Which is the definition of the a joint。The group element times。Lee Alze。

 a man in the vet form。Ts the group element inverse。For the rotation。

 last time we showed that this will be。So， we learned that for。Rotation groups of any dimension。

 the adjoin， in fact， is the rotation itself。And this is true for all otagonal groups。

Which the group is orthotagonal I joined is the group element。So that's easy。

We proved this term last time。B this property last time。four。The rigid body。We have RP0，1。

You have the twist。And we have the grouping bear。So we just need to put in the work and calculate it。

There is nobody out there we can ask。So。For each group， you just do this。

 expand it and see how you can collect it in a matrix。

You can imagine at some point you might have a table， right All of these are given。

Like your love plus transform， for example。Yeah。You need that in verse one。Oh， we don't。Thank you。

So you multiply them， this is what we get。So， the rotation part remains。Unchan。

But because the rotation acts on the translation， the translation part。

Will be something we need to see。Now， one property of， if this is for。Excusey matrix matrices。

 bomb properties that I can。Change the order。And。Ngate the town by shifting。P to the left。

To be the verge。But across。This is what we can get。You can arrange this in a matrix。

 You can verify that this will， in fact。Give you the desired。Results。

Which means two sides of the equality are the same。Which we learned that they had joined。诶。R 0。

P wedge。好。哦。W is if the rotation is3 by3， the are joined for S E3 will be a 6 by6 matrix that can act on twist as a6 vector。

So this is a way to do that change of basis with for a vector。

 If you write twist as in the which form a matrix， the change of basis for a matrix needs a conjugation。

So if we work with a vector， we can turn the adjoint into a matrix。Now。

 the consequence of having omega here is。First is that this term is。And the bottom appears to be。

In the bottom row， because it needs to be multiplied by omega。If you choose V to B on top。

 this cross then will go to the other side。 So it doesn't matter based on what order you choose。

 you can get。A different version of a joint。K。You can try。

 I'll post this on Piazza for both driverss。So that's basically the ajo matrix。Now。

 what is interesting about this， This generalizes the idea that if I'm rotating and moving the linear velocity。

Is。The rotated version of whatever linear velocity I have， right， which is this。R times v。But also。

Whatever is the equivalent of my angular velocity in the fixed frame， which is R omega。

Then I have this R cross omega in the spatial frame。 So your。

Which is basically cross our omega in the body frame plus R V in the body frame。 So your velocity。

In the spatial frame。Is R cross omega plus V in the spatial frame。 This is doing that for you。

 automatically。It' all in the matrix。 It's all in the I joint map。 So， in fact， in robot kinematics。

In forward kinematics。And differential kines， you learn that if you want to map。

The angleular and linear velocity from one frame to another frame。You can do it using that joint map。

Not just the rotation。 If you drop this cluster， you ignoring the fact fact that rotating about a center causes linear。

Vellocity。so it is captured in this framework。The familiar formulas from physics。

So I'm going end this lecture by。Pointing you to。Now， to look at these code examples。

You are ready to look into what I've done。You should be able to follow and answer questions then。

So what you want to do， you want to propagate the uncertainties in the Lee algebra。

 do a Monte Carlo version of that， which will give you this point cloud， as you did in your homework。

 too。Then using the exponential map， you can also see the covariance that is done linear on the group。

If done in the exponential coordinates， you can。Nicely captured that linearity。Right， the。

 the Le algebracovariance is flat。 When you take the exponential map， it makes it curved。

This is known as。But not a distribution。And then there is a paper in robotics that says Madna distribution is Gaussian。

So this is actually Gaussian in the right coordinate frame。So you know。

 it's a good paper if you can goof around with the name。It's the rule of thumb。Okay。

 so that's the for today。And next time we will explore state estimation using these coordinates。



![](img/fed2b48271a9206517f6f64152c9748e_23.png)