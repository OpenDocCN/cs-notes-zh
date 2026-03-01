# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p10 -10-Lecture 10-Invariant Kalman Filtering II.zh_en -BV1UfAmeUE3e_p10-

Welcome to the second lecture on invariant state estimation。

We covered the deris and some examples of avari extended kman filter in the last lecture。

We want to continue our conversation on。More examples， but a very interesting sensor。C。I am you。

Innitiallyial measurement unit。We want to see how we can。Model this。

And how it fits into this invariant state estimation framework。In the previous lecture。

 we gave an example of a right invariant EkeF for a robot that was moving and observing some landmarks。

This time， I will give you an example of a left invari E care。Which will use。

The IMU for prediction or propagation。And a GPS for correction。

And then you will see an another example of。A sensor that fits into the invariant observation model。

And then it will make more sense to you why we call them left or right。 That's just。

Because it makes sense when we write down the observation model。

 that's a natural way to talk about the innovations。 and then。

Manage the order of multiplications in therivations of the error update equation。

So I will be writing down。But we get back to the slide。In the end。

So the sensor we want to model is called。Inertial。Measurement。Unit。I am you。

So that was the picture of it。 It's a small sensor。 You have it in your smartphone as well。

There are many variations of it， but at the very basic form of it， it comes with a gyroscope。

 a gyroscope measures the rate of rotation。In the sensor frame。

 in the frame that is attached to the sensor and a linear accelerometer。

 The linear accelerometer measures the linear acceleration， the movement。Of。Again， the sensor。

 the frame that is attached to the sensor。Now how we build these sensors。

 that's just a topic of mekatroonic sensor design， that's very important。

Better sensors enabled better algorithms and performance。 But that's not what we want to talk about。

 We want to talk about mathematical modeling and algorithms that will use that sensor。

And typically the sensor has a better if the sensor has a better accuracy。

 it will be more expensive as you expect。The one that you have in your phone is probably cheap because they want a mass produce。

And it doesn't make sense to put an IMU that costs $100000。Into a phone。But maybe for a spaceship。

 it makes sense。Because we don't want to lose the ship， right？

So we have a gyroscope an accelerometer。 It can come with a magneto that measures the local magnetic field of whatever place you are。

😊，If you do have a magnetic map of the planet。Then you can use it as a reference， and。

Have a fixed reference system that's called northeast down。

 Sometimes if we know the magnetic field of the earth。Then， we can。

Basically have a global referencing system。That's very challenging to use indoor because all the structures and all the devices that we have will change that field。

But typically， if you're outdoor， it is good。 and that can be used to provide。A reference。 Otherwise。

 your heading is always unobservable。Sometimes the sensor also comes with a barmeter that measures the pressure。

Right， we won't talk about magnet that I'm borrowing。 We talk about a gyroscope， and。

The acceleroerometer。 So the state variables。R。Rotation。Which is an element of S03。

 It's a rotation matrix。We have。Velocity。This is a linear velocity of。The sensor。

If the sensor is attached to the robot rigidly， of course， it's also the velocity of the robot。

In the sensor frame， with respect to some frame that we will define。Then we have position。

She is also at3 vector。You can put everything into。A tuple or topple。And then， call it。State tuil。

 Why Til。If you want to be really picky with the notation， sometimes you see people use set notation。

Set doesn't have order。TL， you can arrange objects like rotation in a vector because we can't put them in a vector。

 obviously。Rotation is a matrix。But there is a mathematical notation for it。 And that's the tuple。

 Tple preserves the order of the objects。 A set does not preserve the order。

But it is understood if you write it as a set as well， but this is the better way to write it。

So this is our state。4。Using this sensor。Preserving the order。We to preserve the order。

 So the question is， doesnt matter if we put P first or V first。 It doesn't matter。

 But once you choose an order in the columns of matrices that we will write down。

 you can't change it halfway through。The columnman filter will just break down if you arbitrarily change。

Order。So。Fix the convention you prefer and then stick to it。 Don't change it。After that。

What are the inputs。Or。Measurements。Yeah。So we have angular velocity。This is。Again。

 it's three vector of rate of rotation about。Body fixed frame。 But you can also talk about。

Itscussymmetric matrix that is in the Le algebra of SO3。And then， we have linear。Accelation。

Which is the linear acceleration in the body fixed frame。Measured by the sensor。

Signals that we directly read from the sensor。Physics will give us this as the sensor operates。

Now we may define。A vector of。Inputs。By just a stacking angleular velocity and linear acceleration。

And this will be obviously a6 vector。So， you is。Directly。Measured。Bye。And I am you。

And maybe it's important to point out that it's measured by an IMU in。The body frame。Now。

 why we need to include the velocity。You might have this question。

Can we just include the rotation and position。 Is that possible。

Not if you want to have a first order I needE。我哋。Not if we want to have a first order， O D E。

Do you mean because the acceleration is the second order， a second derivative of the position。

 If you want to have a cascade integration of these first order differential equations。

We need to include exactly like you said。All the derivatives up to。1 before the input。

Then we can have this cascade of integration。 So the sensor is giving us the acceleration。

 One integration should give us。😊，The velocity and other integration will give us the position。

So naturally， the velocity shows up here。Rightです。because the sensor is giving measuring the second derivative of the position。

Luckily， the gyroscope is measuring the first derivative。Of the rotation， it is not angular。

Accelation。Why luckily？Clearly， not because we don't like math。Right。可。

Closer to the thing that you actually want。Exactly， very good point。

 So because now we're talking about a perfect situation， No noise。

 deteristic model to understand the property of this process， Then we will add noise。

 Then we have to talk about。What will happen and what should we do when we have biases because。

For example， the axes of your aelerometer are not perfectly perpendicular due to manufacturing errors。

The thermal noise can affect the sensor performance。Or we can expand， right。

 we can have different level of a strain。It's not perfectly in the laboratory situation that they tested and reported the noise parameters。

All of these。Many unknown factors that can cause error。

 And we are not modeling them because our model is。Fptturing the essence of it， but not。

All the little。Enterac C that exists in nature。The more you integrate a signal。

The more you accumulate， the faster you accumulate。Eror。So if you have to integrate one time。

That's much better than integrating twice。So quited radically。

 you will grow the error if you integrate twice。 And thats so the error can grow exponentially。

If you integrate more times。So， we do like to have。Measurements that are directly close to the state。

But we are also limited， But what， what we know and what we can build to work with the physics of the。

Problem。Okay。And that's one of the big challenges of IM U。 You get acceleration。

 you have to integrate twice。 The position will drift significantly。😊。

So that brings us to the question that what is the best way to model this sensor。Spoiler alert。

 there is a league group。That will model that。Let's talk about。It's somewhat exotic。

Matrix league group。This is similar to S3。But we will add more vector spaces。

We will add velocity and position。Now， you can have two positions， three positions。

 depending on what you do。 So you can have as many vector spaces as you want。 We will work with two。

This group is called the group of double direct isometric of。The Euclidean space here。

 three dimensional Euclidean space， because if you remember rigid body motion was the isometry of the 3D space。

 and isometry was a transformation that would preserve。Distance， distance between two points。

 any two points。So because we have two columns now related to。The translational part。

 we call it a group of double direct isometricries。So this is。A grew of。Double direct is of。

Are three。What is the dimension of this group is the dimension is。The dimension of its le algebra。

 as we will see now it's nine。3，4 rotation，3，4 translation， and 3，4 velocity。

So matrices in this group， they look like。This， you have。Rotation， velocity and position。

We have rows of one by3。0eros。We get 1，0，0，1。It doesn't matter if you like to put position first or velocity。

Again。You can choose and just stick to。This is an element of。S E。3， using what S E 2，3。

 or however you want to read it。There's no short pretty name for this。Whatever you want to call it。

And we can add more columns。 You have to grow the dimension of this matrix。 Now is 5 by 5。

 if you add。One more， for any reason。For example， for legged robot。

 we add contact points so you can add more columns。 This will grow。 If you add one more。

 it will be 6 by 6。被注明。2， because。This two is related to1，2。S E 3 has only one translational column。

A vector space。This one has two。It's hard to come up with a better notation， I think。

That's probably the most compact notation。And3 is 4。R 3。So the Le algebrabra of this group。Is。

The space of vectors， you can think about it as a generalized version of twist。So we might have that。

Terms that we use， and we just call it twist sometimes， but from the context。

 you know that it's not just position and rotation。Again， we choose our， our order。

Which first one is something like omega as usual， for rotation。This will be for velocity。

 and this will be for position。This is a nine vector。So we have。Rotation。Yeah。Now。

 depending what you're doing and you're talking about the continuous time or discrete time。

 you need to be obviously careful about the meaning of it。This vector can be angular velocity。

 But if you're working with a discrete model and its angular velocity time times Delta T。

There is a deelta angle。Similarly。For velocity， it can have an acceleration meaning。

 but if it's a discrete model。It's acceleration times Delta T。 It's like a deelta velocity。Okay。

But in the continuous time version， it is the derivative of。The quantity you see in the state matrix。

Now。One， nice。Reason to work with this group is that you can check it will satisfy all the properties of matrix Lee groups。

Everything we talked about established will be true。You can just use whatever we did。

 that differential equation that is first order propagation。We will。

 we won't work with that equation， but。That holds。And everything we talked about for matrix loop groups。

It is true for this group， as well。Now， the vegge notation。

We need to define another overloaded notation， but that should not be a source of confusion because this is a9 vector。

When you code it， it's not a six vector。 so it will never be the same input。

We have this chryisymmetric part for the rotation。Then we have the velocity part。

And then we have the position part。And then we get old。0eros。You could call this。

The Lee algebra of this S E23。So you can visually verify it's very similar to S E 3。

Whatever you expect to see， you can see here is's just。Growing based on the extra vector space。

And similar to all other league groups， we have。The fact that。For every element of this group。

 there is an element in the Lee algebra that when that when you take the exponential matrix exponential of that。

It corresponds to a group element。What about the ajoint map？Now， we derived the a joint map for S。

 O3 and S E 3。You can follow the exact same process。A little more calculation。

 you can derive the at joint matrix for this group。If you do that， it will look like this。Now。

 the joint depends on the order of。Angular velocity position， velocity， right？

So based on the order that I chose， the matrix will look like this。 The diagonal is all。Rotation。

You get velocitylocity Q times R。Then we have positionq times R。Then we have 0。

And then we have rotation。So they are joined is。The 9 by 9 matrix。It belongs to。9 by 9 matrices。

The meaning of the Ijo， what it does for us， everything is the same。

We want to map this twist or generalized version of the velocity。From one point to another point。

Maybe we want to map the covariance。Everything we did， we can just use the ad jointint map。 In fact。

 if you want to propagate that covariance for。That oometry， if the motion is in this group。

 you use the exact same equation。 You will not change anything。 You don't need to derive it。

So all the derivations are general already and valid。

So now you start seeing that why this is convenient。

You do not need to redo therivations and calculations for new problems。And eventually。

 this could be just a library that you can't you don't even need to look into it。

It will do it for you， right？So， now that we have。A matrix league group to define our state。

To be an element of that group， now we can talk about the process model。嗯。Now I want to talk about。

The continuous time。 I am you。Process model。I'm going to first write it without matrices。

 Then we will arrange it into a matrix。We know already for a gyroscope。

That the derivative of the rotation matrix。You could call it our dot。Is rotation times。

The scssymmetric matrix of angular velocities。And I， I'm using now the subscript P， because。

I want to emphasize that these variables are evolving with time。

And the input that we read from the gyroscope is also variable with time。

What about the velocity term， We can talk about that the time derivative of the velocity。By the way。

 I am talking about。Rotation， position and velocity of the sensor with respect to a world frame。

So I'm tracking。The sensor pose and velocity with respect to a fixed world or global frame。

That you can choose where it is。 Initially， it can be where you start。

 Then you want to track with respect to that frame。

So this rotation is a rotation that will transform a vector or a point in the body frame。

To the word frame， okay。And for the velocity。It is possible to talk about the velocity of a body frame in the body frame or the velocity of the body frame in the word frame。

 It matters which frame of reference we talk about the velocity， the observer。Frame is important。

So the time derivative of the velocity in the world。

 velocity of the body frame with respect to the world frame。Is you can call it V dot。To do that。

 we need to rotate。The acceleration that we read。To be aligned with the global frame。And then。

 we need to。Compensate the gravity， because the I M U。

 the ael acceleroerometer that we have in the IM U will return a measurement that measures the gravity。

 If you leave your IM U on the desk。It will not return 0，0，0， even if it's perfectly aligned。

And in an ideal case， it will give you。0，0。And some acceleration for the gravity。Right。

And the acceleration that the IMU senses it will be positive。😊。

It thinks that the sensor is moving up。Because the gravity is pulling the sensor down。

The reaction to the reaction to that force is going up。So physically， the sensor is thinking that。

A force is moving the sensor up。 the， the reaction of that。So that's why you read a positive value。

 if disease is up in your frame of reference， then we include a negative value for the gravity to zero out。

That gravity term。All it depends。 You can， if G is。0，0。Negative of。Some value you can still add。

 So when you actually implement it， you need to be careful。 But plus minus， it doesn't matter。

 It depends how you define the gravity。It's a constant。Rector。It's so。这边。

Do help the orient the sensor。So if it's upside down with the important they are be your。

If the sensor is upside down。It will change the sign。

But because we also track the orientation of the sensor， we rotate it back。So in the equation。

 we rotate back to be aligned with the global frame that we want to track。We respect that。Right。That。

 that's， that's exactly the problem， right， The sensor can move in all sorts of。Configuration。

 and that's going to be a nightmare。If we don't know。

How it's oriented with respect to the global frame。So knowing this rotation is very important。

 otherwise you cannot compensate the gravity。We'll be always there。

 and we cannot integrate gravity the gravity， because。The sensor is sitting here。 You integrate。

And you will be moving super fast with this amount of acceleration， whereas you expect to get 0。

Just double check。呢度比集前。情法律。We all outrighted them。I'll write that in a bit。即。Coreト。

Before I write down what they mean， we have also the derivative of。The position。

 which is simply the velocity。So the time derivative of the position in the。Position of the sensor。

With respect to a word frame， is's just。The velocity。And then the derivative of the velocity。

 because its's acceleration， It gets coupled with with what we read from the sensor。So， our。V and P。

R。Rotation。Eocity。And。Position of the body frame or。I am U frame。We justpect to。The war Frank。

So that means I may fix。A world frame。And then， I can move。In any way that I want。

I want to integrate this model， to know。The orientation。

 the velocity and position of the sensor in the world frame。 That's my observing frame。You can。

 of course， talk about。The body velocity of the IM U in in the body frame。 that's possible。

You can talk about the rotation of the word frame， as seen in the body frame。

So that depends on the problem and what we want to do。

 But the typical standard convention in robotics is。

Track your sensor robot with respect to some fixed frame。Again， I understand in aerospace。

 they usually track。嗯。The rotation of the world in the body frame。 So this inverse of that。

 But that's not a problem。 You can just。Define the state to B transpose of the rotation。

 and then work with。Drive a filter that works with that。 That's not a problem， okay。

Now let's put this in a matrix。We have three equations。

That describes the time evolution of our estate variables。

These are first order differential equations。Soeleb。X。At time T， B R T。BT and PT in a matrix。

And I'm I'm not writing anymore。 This is one by3。 It's understood。 if that's a rotation。

You just need to fill in with zeroes。In a way that makes sense。This is an element of S E23。

Then the time derivative of x。You take the element wise derivative of this matrix right for rotation。

 you have R dot for V， you have V dot for P， you have P dot。

 Now we know the equation from the above substituted into the matrix。And we get。This relationship。

And the time derivative of constant values， those bonds is obviously0。

So I am just substituting the equations from above。Into the matrix。Now。

 we can define this matrix to be。Our deterministic。Process model。

This is a process model on league group。It is not like， what we。

Had before this is this one is the simplest way you can get。 It's the kinematic model。

That naturally comes with any legal group。 In a sense， it's a constant velocity model。

Native to each league group。For this does not describe the IM U because the rotation part it does。

Velocity。Part， it doesn't， because。The IMU。APart of the acceleration need needs to。

Be compensated with the gravity。So there was a question on chat that why this twist is a nine vector。

I'm not sure if you got your answer， but I repeat that the twist now it's a9 vector because the group has9 dimension。

 We want to track position， velocity and rotation。In 3D space， rotation has three dimensions。

 velocity。 We have three axis。 We have three dimension for the velocity。

 and we have three dimension for the position。 If you stack them into a vector。😊，In the Le algebra。

 that will give you a 9 vector。That's why this is9。By one。So。This。Does't。Describe。And I am you。

It is true， but it doesn't describe the IMU。Okay。Now， what is interesting is that。

 that's your exercise to plug in into the group a fine property。

What you will observe is that this process model satisfies the group I fine property。

And a group of find property was。This property here。

All you need to do you need to calculate direct calculation。

 perform the direct calculation of both sides and show that they are the same。Then you know。

 it is group I fine。And then you have。The exact equation for the errorero dynamics。And at that time。

 you know that you can derive a log linear aerodynamics。



![](img/24fe3a0227db5de3ddef09b31ec592bb_1.png)

That was fu， too。

![](img/24fe3a0227db5de3ddef09b31ec592bb_3.png)

Now， this is surprising because。Why。You're not amused that I am you。Has a log linear。Arerodynamic。

That means that we can。In a deterministic case。If we want to propagate a covariance。

You can do it exactly。Despite the fact that this model is nonlinear。Right。This is not a。

I'm afraid it won't be recorded again， so I'm going to remove it。



![](img/24fe3a0227db5de3ddef09b31ec592bb_5.png)

![](img/24fe3a0227db5de3ddef09b31ec592bb_6.png)

So you know what happened， I touched something that was working properly and then it stopped working。

That's the first rule of engineering， do not touch something that is working。

It will stop working and you cannot fix it。So that's the lesson from today。 And besides that。

 the IM view is also log linear。没有。I hate to tell you that in the literature。

 they will tell you this is a nonlinear。 You can't do it。 You have to linearize。 It's messy。

Probably in other courses you will take， they'll tell you this is then linear。And now you know。

 that's just not true。Now， I do not recommend getting physical， but know that。

What you hear is not the fullest story。 There is a choice of coordinates that will make the error propagation exact。

 And this is the log linear property using this theorem。



![](img/24fe3a0227db5de3ddef09b31ec592bb_8.png)

So in the deterministic case， right， then we will have introduced noise and bias terms that theoretical results are lost。

 but still， it's better than not using it。 It works very well in practice。

So this means we can integrate。The IMU dynamics， exactly。No approximation。

And if you have a covariance， second order。Eror。Uncertainty， we can propagate that exactly as well。

So this process model satisfies。Remarked。You can verify that。The process model。

Or better to say the deterministic。And if subscribe you just to emphasize。There is some。

 there is an input somewhere。You can drop it that it doesn't matter。

 We're just emphasizing that there is an input to this process。Satisfies。The group a fine property。

So if that's the case with everything we learned， the first thing you want to do is to derive。

They log linear error dynamics。And that will be the a matrix。

Because if you remember for implementing the invariant。Extended column filter。

We need a process model that satisfies the group of fine property。Then we derive。

They like linear error dynamics matrix A， And then we need a measurement model that fits into one of the left or right invariant models from that model。

 we derive the measurement Jacob N H matrix。 then we know everything to implement it。

 And if you have a library that is already taking them as the input as input。

Then you're done at that point。 You can just run your filter。So four elements。And given the model。

 your job is only to drive two matrices。Then you know everything and possibly tuning noise。

 of course。まて。A short。This does not represent。Yeah。Explain a repeat a little bit。我在。

So for League Group SO3， so the question is， why did I write this？I could just not say it。

Sometimes we say more， and then we're in trouble。So。Now， I'm trying to answer。The question。

 because I wrote too much。So for league groups， S， O3。You， you would。Just right。Where should I write。

For league group S 3， you would just write R dot equals R omega cube。 Now。

 R is entirely the group element。And omega is the element of the Li algebra。

 And this differential equation comes with the L group directly。For S E 3。This is S03。

This is as eatery。We could also write this。In this form， and we used it for。

The constant velocity motion model in the robot localization example。Now。

 you might think that it's always going to be like that。 Therefore， for this group。

 we also write this。 And then we call it a day。 But no， that's not the case。

 This is just the simplest process model that comes with the legal group。

 It is the constant velocity model。 because if we assume this twist is constant over a Delta T。

 And we're just integrating that。 However， I M U is giving us。Secondary with of。The position。

Then there is that gravity。 So the model ends up being different。

 We cannot work with this model directly。So it's a little bit more complicated。 Now。

 the processes on legal can be。As complicated as you want。

 it can be so nonlinear that it doesn't satisfy a group of fine property and we don't get anything nice from them。

But fortunately， for this sensor， it does satisfy。So it gives you hope。

 There are a lot of things in nature that are nice。 We just need to。Look at them from。The right lens。

 in a sense。Did that answer your question？You you have question？Yeah， I saying。In the literature。By。

I think that says that， oh， you can handle I use。does that mean that？啊。That is。Wade of modeling IMU。

Is only fairly recently。Yeah， so the point is， you're asking that why the collective。

Wisdom of the literature is not emphasizing that you can integrate this exactly。By that， I mean。

 the majority of them， especially if they're older than 2000。171615。You don't see that。

 And after that， it takes a while until people adopt it。 So there's a。Small body of literature。

 They do use the model。But it takes a while until kill everybody。Aoppt it。It is because exactly。

 it's new。So then we want to talk about。Log。Linear。Maybe first。Right invariant。Aerodynamic。

So we expect after writing the la nonlinearar aerodynamics。That the first theorem。Provise。

The structure of it。And linearizing it， we expect to get。

A matrix that describes the evolution of the error in the Lee algebra。Now。

 we do not need to start every time from scratch。 We are after。This matrix。

So well have to write down the errorerodynamic and then do the first order approximation of the exponential map。

 D the all all the higher order terms。And what we will will be left is this matrix。

You can do it for the。Right  error。Or you can do it for。The left。

Each one will give you a different matrix。

![](img/24fe3a0227db5de3ddef09b31ec592bb_10.png)

So， they're right。Matrix。Will be like this。 I skippped the calculation。 This is something。

It is available in references that I will point out in the end， you can look into that。

But it's good for you to carry out the calculation。 It is just direct calculation。What you will get。

Its surprisingly。A constant matrix。Which， as it was promised by the theorem， the error evolution。

 given an initial condition from this， for this O D， it is independent of your state estimate。

So the matrix A does not depend on the estimate of R， P or V。It is constant。Hence。

 the error propagation， given an initial condition， is exact。It says9 by9。And。

You can derive the left invari。ButThe equation is similar。But you will get a different a matrix。

Because we start from a left invariant definition of the error in the group。That will lead to。

Another matrix。That we use superscript R and L to emphasize this is for left and writing variant in cases。

A will。Do you like this？So， as we can see。It is still independent of the state estimates。 However。

 it does depend on。The input。Readings of IM U。But that's not a problem。

These are readings of the IMU that you read directly from the sensor。

These are not the state variables that we need to estimate。

So depending on what type of filter you're building， you pick。The matrix that is appropriate。

We will be working with the left im variant。E KF this time。 So we have to pick。

The second matrix that I wrote。Now， let's add。The noise term to readings of the IM U， because。

The perfect model that we discussed， obviously， does not exist。



![](img/24fe3a0227db5de3ddef09b31ec592bb_12.png)

In real world。So now we're going to talk about。The noisy process。For the noisy process。

We have the gyroscope。Readings。So what we read from the gyroscope is some noisy version of。

The true angular velocity。Plus。Some noise。 So it is our choice to model the imperfection of。

The sensor readings， with an additive。White Gaussian noise。Are you here。

Addditive white Gaussian process。Because it's a continuous time。You like to call it the process。

It's different from that discrete time noise that you use。

 you write down multivariate normal distribution。For the axelerometer， we have。A similar logic。

They corrupted。Noise corrupted readings of the acceleration。Is some true value plus。Anotherno them。

So this is exactly。What we talked about， it's an additive。Wide Gaussian noise。That it has zero mean。

 it has no auto correlation。It's。Continuous time version has a constant power spectrum。

 So the signal power is constant。 That's the meaning of it。 In the discrete time version。

The covariance that we get is completely determined by the signal at that time。There's nothing new。

 that's exactly how we built our command filter。Okay。Now are we going to write down。

The noisy version of the equations of the IM U， which will give you a new insight as well。

 Why we define。The noise in that particular way。In the process model， its out。

 pops out out of the equation naturally。So， our doc is。Rotation。Now， if the true value， right。

 if the noisy version of。The signal is the true value plus noise。

Then the true value that we want to replace in the deter termministic case will be。

The noisy versionrgin， minus noise。That's why you see the noise is subtracted。

But because it's 0 mean， it will not have any particular effect if you add it or subtract it。

And the covariance is positive anyway。So the reason for subtracting the noise is what I wrote。

Now you can distribute the rotation to。The angle of velocity and the noise that's。

That's like a factored version of it right now。If you have a cross product， right。

If you have R A across R B， you can write it as R。Times a cross B。So it is still simple。

 It doesn't cause any。Challenge that we cannot。Sove。For the position。We don't have noise。

We add noise at the source。 We do not add noise arbitrarily to。

The natural relationship that we understand between state variables， the noise。

Is initiated from the source。 The source is where， where we read the signals。Namely here。

 the acceleration and the angular velocity。Now， if we put this in to。Our matrix。

We get the noisy or stochastic version of。The previous process model that we derived。

Theres nothing new here。 I'm just arranging the equations into a matrix。

And I'm separating the part that corresponds to the。

Previously derived the feministic process model and the noise。 So we can see。

What are the different terms。We have， at the end。And then you can define this to be。

Your previous process model。Minine is state。Times and noisetown。 So that's why。

In the previous lecture， we defined a noise to be the process model plus state time some noise。Again。

 plus minus is not very important here， because。The noise has a zero mean。I be。State itself。

 during prediction。There is no noise we just use the process model。Here， we also defined。

A bigger noise vector， that includes。The gyer noise。

Aelerometer noise and 0 for deposit position equation。So this is also a nine vector。

Just like our generalized twist。And the matrix you see above is the Q version of is the weight version of。

This noise。So we have the noisy process model for the IMV as well。We。

Are ready to form the propagation step of。The filter。So given an IM U， now you know how to model it。

 you can integrate and propagate the state。There's a lot more to consider。

But you know where to start。But if you have bias stamps。Which you definitely have。

Bs in your accelerometer， acceleration readings andrope gyroscopes， angular velocity readings。

Those biasins are very important to correctly estimate and compensate。

And they can slowly vary over time。 They don't have to be constant， because。The way you move。

The magnitude of the signal， the temperature of the environment。

All these factors can cause the biasts to。Slowly vary。

 slowly because relative to the state variables。They're not changing as fast。

But they're not completely constant。So you're not going to derive the biased version in your homework。

 you also work with a nonbiased model for the gyroscope。But again。

 in the reference that I will point out， you can see how you can augment the bias。

 Then you have to subtract the bias from this anglengular velocity and acceleration。

And also include two more equations for。Estimating。A6 vector。

3 bias stem for the angular velocity and three bias stem for the acceleration。

And then you will have a bigger a matrix that include。

That considers the error propagation for the bias as well。 Now， when you include the bias terms。

Your a matrix is no longer state independent。 Unfortunately， when you add the bias。

 it breaks the symmetry and。😔，Then you will see rotation and state variables in the matrix。

But in practice， it。The filter still works very well。 It's an imperfect。

Invariant filter relative to the ideal case that we derived it。

But the performance still is much better than alternatives。So still is the preferred。

Method for state estimation。Can you scroll back up to the end're just showing confused about how this。

because it seems like the bottom row is just zero， but it should be v subt。

Your question is how this matrix can be explore。Yeah。Because X。X is。RVP。0，0，1，0，0，1。

So the x dot will be r dot V dot p dot0。0。Take the element wise。Time derivative。 Now。

 our dot is what we have in the above in the equation here。Just substitute them。Into the X dot。Right。

And the rest is just left over from。Noise。That we collected into a estate matrix times。

A noise metrics。So。This is a little different from last time。

 I did not tell you that there would be a process model with this structure of noise。

We justify the noise modeling from where we read gyroscope signals and aonmeter signals。

 and that led to this structure of the noise。Which hopefully will convince you that。

It's one way to integrate noise into the process model。

 but it is natural because it's showing up here。So now we want to talk about the left invariant。ekf。

Proropagation， because we want to build a left invariant。Failter for。I am U GPS。Sensor fusion。

And propagation is the same as prediction。Discussed this before。

So if you remember the left invariant。EF。As I may。Use the summary in the slides。

There's a propagation step。And then there is an updated step。If you know。A。And8。

Given that we know the process， model N。The observation model。

 we know everything to implement this filter。So I'm going to talk about the propagation first。

And then the one one problem we have to solve is that this is continuous time。

 We need to discretize it。That needs to be done。 And that's。A little involved process。

 but we can do it。Exactly。If we assume a zero order hold for。The signal signal for the signals。

 the acceleration and the angleular velocity。 That means over a Delta T sampling time。

 there constant， then we can exactly integrate。So， we have。Time derivative evolve。This is state。

evolves based on this process。So the propagated state， you just get your state estimate matrix。

Send it through this process model。 And then you。Have your state at the next step。

 not using this because we have to discretize it。 But generally。

 you just use this process model to evolve your。Mean， mean value for the state matrix。

For the covariance， we have。This continues time， equivalent equivalentvalentov。

Eror propagation that I want to talk about it a little bit。Now。

 where this comes from is not necessarily our concern。 but I want to give you a quick。

And convincing proof， maybe that。You feel more comfortable when you see this line。So this is。

Continuous time。Vs enough。Something like this。Fe is the state transition matrix prediction。

 so this could tie version of。My system matrix。Now。

 to see why this is a continuous time version of that。A simple logic is to。Follow these steps。

 Consider。We have a linear。Continuous time linear models with additive noise。

When you discretize this model， you get something。Like this time difference equation。

 that well have some transition matrix。Plus， some discrete time noise。

And the covariance that we are used to implement in our code。Evolves using this form。

From time step K to time step。K plus one。Now， we know that。From linear systems theory to disctize。

It continues time dynamics。Essential， we need to integrate。

If we integrate that differential equations over a delta t time。We are discretizing。

If you can do it exactly， that's perfect。 if you can't。Then we have to resort to approximation。

The most famous approximation is the oiluler。Dcrtization。

We just tell you the approximated derivative with deelta of that variable over Delta t。

And then see what you get。 That's your。Oer approximation。For these。Vctor equations。

 we know that the discretization。Based on previous lectures。

 we know it ends up having a matrix exponential。So this great time version of。

The system matrix is the exponential of。Continuous time。

 state matrix system matrix times sum deelta T。Imagine we do a first order approximation of this。

 It will be identity plus A T times deelta T。Which we do， if we cannot exactly。Derrive this。

 And if the exponential of a matrix is too costly for any reason for you to evaluate it。

 this is a good approximation。If we lose something， of course， we lose a lot。But。

Depending on the application， it could be a good approximation。Now， let's。

Substitute this approximation back to the covariance propagation equation。This will give us。P。

 K plus  one equals to。Identity plus a times deelta T times P， K。

Times identity plus A times delta T transpose。And I'm going。

Say that this is the approximation of the continuous version of Q times Delta T。

 So everything I have here here。Is a first order approximation of。The continuous time model。Now。

 expand。The matrix multiplication。What we will get well get P， K plus A T， P K times deelta T plus。

PK T transpose times deelta T。What I'm going to do， I'm gonna to drop the second order10。

 There will be a Delta T squared because Delta T is assumed to be small。Where after linearization。

 we dropped the second order term that has deelta T squared。Then we get Q T times deelta T。

Rearrange this to get。P K plus 1 minus PK times delta T。Maybe I write it。On the next page。

You can already recognize。Equation now。As Delta T approaches 0。

This time difference equation approaches the continuous time evolution because the continuous time equation is an instantaneous。

Vsion of time difference equation。Then。Essentially， if you talk about the limit of the left and side。

So， the limit。Of this site will be。He does。So。皮자。Time T。Then we have to replace everything with。

Be a time tea， because。T approach to 0。 It's no longer a delta。Then we derive。

A special version of a matrix ricard equation， which is equivalent of continuous time。

 equivalent of the discrete time covariance propagation。So a lot of time you see this without。

Any particular de， because it's too famous。But this is one easy way to know where it comes from。

The rii equation has more terms， but if you zero out some of them。This is part of it。

In kman filtering， usually when they say ricardi equation， they mean the。

Proropagation and correction together will give you a long。嗯。

Matrix differential time difference equation or differential equation。That's called Rikadi equation。

But this is a version of that， too。In control， if this side is0， it's also called the Aanov equation。

It has something similar to this instruction。All right， in any case we。Give you a reason why。

I will write it that way。Now I'm going to switch back to the slides。All right， so we。

Talked about the initial measurement unit。We know how to model the noise and we know how to talk about its continuous time。

Process model。We can write down the noisy process model for the IMU。

And we know this model in the deterministic case satisfies the group of fine property。

Well we're not going to go through the integration because you need to just look at it。

 see it's done。In the reference that I will share， what you will get。

 assuming a zero order hold for the IM U signals。 you get the exact。Integration， so the first term。

 some new notation， the gamma 0 is just the exponential。Map。Because when you we write it as。

Power series， then we integrated。We want to give them new names。 We start from gamma  zero。

 and then we call it gamma 1 gamma2 as we integrate it。

 It just naturally shows up when we try to integrate the equations。So there is a gamma one here。

 when we integrate。The velocity。For the part that is related to rotating the acceleration。

For the position， we integrate。The acceleration twice， there is a gamma too， which is， again。

 the integration of。The exponential map， twice。What you used to see， probably。Not having these terms。

However， this shows that。The exact integration。Has some extra term for updating the rotation。

Before you。Rotate the acceleration vector because the sensor is not just accelerating。

 Its also rotating。 So that rotation instantaneous angular velocity will cause the rotation to change。

 So that change is reflect， reflected here in this term。 So you can set it to the identity。

 if you like， because often。😊，Theelta T for IM U is very small。So this term will。

 will be very close to。0， maybe Delta T is a small， and you're not moving super fast。Then its okay。

 It's our almost identity。But it is interesting to see that。The actual model is more complicated。

 than it has coupling of angular velocity and acceleration。So in any case， this is。Somewhat familiar。

Constant acceleration model， right， because if you。Get rid of the rotation and gravity。

 You know this from physics。Now there's a one half into gamma tube， so this will be one half。Okay。

So to not be intimidated by these gamma functions。They are given to you in closed form。

So you can calculate gamma 0， gamma 1 and gamma 2。And there is a。

Powover series for the general case of M。So gamma 0 is simply the exponential map。

 Gamma 1 is also called the left Jacoban of S O3。You don't have to use it now later in optimization。

 we We talk about loggmap and Jacobkuians。But it's Jacobban， in the sense。

 we derive that Eer rate matrix。You choose a coordinate。

 and then there is a matrix that relates the rate of change of angles between two frames based on a particular parameterization。

So the name is related to something like that。So， we。Have the discretizations。

 if you're interested in deris， I'll share the reference with you。If not。Just use it。

We are talking about a world centric stateestimator。

 We track the state with respect to a world frame。If you work with the right invari。

 this is the matrix based on the last lecture we know the noise will have this particular form。

In the left invari， this is the matrix。If you talk about robot centric estate estimator， we have to。

And where the state。This will flip the correspondences of right and left invari matrices with the state variable。

You can do calculations and you can show them。So now we're ready to talk about an IMU GPS left invari Ekeev。

 so a robot is equipped with an IMU and a global positioning system。Which will give you。

Some latitude and longitude in， in。The world， based on the satellites。It's usually very noisy。

 You have up to 10 meters error， maybe。Because we have an IMU。

 it is very natural to talk about the state as an element of S E to3 group。For the prediction step。

 our choice is to use。Decrtize the IMU model to predict。For the correction step。

 we want to use the GPS。And then we will see what is the observation model for the GPS。

So we're gonna model a word centric left invariant。Cllman filter， we know this state matrix。

The state transition matrixes the exponential map of。A times some sampling time。

It turns out that you can calculate this exactly。So， the exact discritization。

Of the state transition matrix is also available。And。You'll just get a bunch of garbage。

 If you have bias， there's a lot of tans。You don't want to look at it。You just want to code it。

Or find somebody else to code it for you and use it。But it is exact some integrals you can calculate。

And by the way， some of the integrals， you can just use software。It's just the usual integration。

 you don't have to do it by hand。You can use Mathlab or Mathematic or any symbolic math engine。So。

 the。Proropagation step is out of the way， right， We have the state transition matrixs。

 and we can just propagate the covariance， and we have the discretized process model。

 We can just evaluate。The process model to transition the state at times step K to k plus one。Now。

 we know that the GPS， after some calculation， we can convert the latitude and longitude to some position。

So what we read from the GPS is really。The position。When we arrange it into a matrix。

 because our estate is like this。It makes sense to have a vector B。To zero out rotation and velocity。

And we have zero for the other terms， such that。This is what we get。

So it's really just the measurement。Is。Directly observing the position。

When we write it in a matrix form。It gives this。For。

 then we recognize that this was the left imvariant observation model。

So based on this definition of the state matrix， it naturally fits into the left invariant observation model。

If you invert the state。Work with x inverses。 It won't be the case， right then。

Because then you will have R transpose P。In the state。But in any case， that's why we chose。

To work with the left matrix here。就呢个。ぱでし。啊对。Using。Up there that you will get more precise。

Are more accurate measurements using。😊，IM U plus the GPS system and just the GPS measurements。

Question is， is the goal here to show that using left a left invariant common filter。

 we get more accurate measurement， absolutelysutely not。

 The filter will not make your measurements more accurate。 This statement is not correct， right。

That the， that the IMU。Coupled with GPS。啊，可以行。It is a sensor fusion framework， right？

We want to combine data from multiple sources to make our estimate about some variable better。

The minimum we need is usually two or an assumption and two。

 like a constant velocity assumption and a sensor。Better to have two sensors。

IM U is naturally good sensor for prediction， because we can。Estimate position， velocity orientation。

GPS is noisy。 If you can track with IM U and correct with GPS in an ideal setup。

 this will work perfectly。But I'll talk about the problems in practice。In your homework。

 you are using acceleration for correction， gyroscope for propagation。

 So that should tell you that this is not the only way to look at it。 depending on the problem。

 we can make different decisions of。How to propagate， how to correct。

It's just some sensors are very suitable for propagation， like gyroscope。

Accelation can be used for both as we see。So the GPS is naturally leftyvari observation models。

All we need to do。If you go back to my recipe for the left invariant filter。

We need to solve this equation so that we find H。 and the way we do it， you just directly calculate。

The wedge version of。Our generalized twist will be this matrix we have here。We know the B matrix。

Multiple item， you'll get the vector here。Make this a matrix times。Twist。

It ends up being the matrix you see。Get rid of zeros。If you wish to work with a reduced version。

 you can always have a projection matrix to a model to get rid of all the zeros that are redundant。

So the Jacobuban is constant。It doesn't matter where you are。

 The corrections are independent of your state estimate， which is nice。So that's。

 that's the end of this example。 You're ready to implement it。 Now。

 if you simulate some data and this nice， this obviously will work perfectly。In reality。

 what are the problems？Let's list challenges that。You sit down， you w to actually build this filter。

 and then you。Will face the list of challenges。Depending on your c update speed。The feed。

Like I sent you the integral。That can be a problem。 The interval that we receive signals。

 maybe the GPS signals are too intermittent。 they're not。Available on a reliable basis。Now。

 that's the problem for getting。Enough correction。But it's not so much of a structural model for the problem for the models。

 but it is an important problem。Bs， we， we need to include the bias。

 You can't just integrate between two GPS data， which might come at。10 heads， maybe。For 100 headtz。

 And I used at maybe thousand00 headtz。Without bias estimation， it will drift。

I assume your GPS and IMU are perfectly co located。So there might be， there might be a need for。

Some data processing that your GPS positions are in the frame of your GPS sensor。

 wherever it is installed on your vehicle， the IMU is probably somewhere else。Now。

 the rule of thumb is that you want to bring in everything into the frame that gives you higher order derivatives。

Because to map the linear acceleration to another frame。

 you will end up needing angular acceleration that we do not have。

Whereas to map the position to the IMU frame。We can do it with some rigid body transformation。

So your rule of thumb is that your IMU frame is your base frame for a state submission。

Or a slam or whatever you do。If there is a。Diffence between where the sensor。

 the IM U is located on the GPS。 We need to know their relative posts。Probably it's rigid。

 they're not moving。So we need to know the calibration。Both。

Then you need to map your position measurement to the IMU frame。And if you do it correctly。

 then you run this up correction。And howfully it will work。

Another problem is tuning the noise covariance might be difficult because the GPS data is very jumpy。

We'll jump all over the place， but whereas I am you likes to track continuously， obviously。所以。

Might work。But it also depends。 what is your expectation。 Are you expecting。

10 centm accuracy or expecting 5 m accuracy。So depending on what are the requirements。

Of your localization， this might be good or not。But it is certainly good for initialization。

 GPS will tell you where you are。So many questions。You， you asked more questions。

And this gives you into GPS。GPS only corrects the position。And he is。Well， maybe， maybe it's a。

Maybe you have a module that gives you velocity as well。 but yeah， you can use it if that's the case。

Oh， you don't correct the orientation because there is no measurement for the orientation。However。

 the orientation is correlated with the。Position and velocity in the process model。

 When you correct the position。The filter gain， the column gain， will correct all the variables。

 So that's why it's important that in the process model， the variables must get correlated。

If you add a variable and it doesn't get correlated and the observation has got nothing to do with it。

You will never correct that variable。Yeah。Yes data。对意。think for civilians， GPS is。10 up to 10 m。

 something like that，10 m accuracy。For military is more， but we don't have access to that。

It's like a meter， maybe。喂。还ま。ction。那 see。Its actuallyRight right， so I mean。

 you're not going to use it indoors， obviously。But maybe on highway。嗯。You are also， I don't know。

 if you go to Hong Kong or New York， Manhattan。嗯。You go wrong to the wrong direction。 If you use GPS。

 It's always wrong， right。Because you have this multipathing and shadowing and what not from the signals that your phone receives。

It's not reliable。So there is a place probably this is useful。 It's not completely useless for。

 I think for。Airplanes probably good。It works well probably for aerial applications。

For cars is not enough， for ground vehicless， this is not enough。



![](img/24fe3a0227db5de3ddef09b31ec592bb_14.png)

But just an example。 Now， one question to answer before we finish is that。

If you have left and right filters， can you convert。Halfway through the calculations。 Yes， you can。

 using the joint， you can。Map the left invariant arrow to the right invariant。 Therefore。

 you can have。A relationship between your left invariant and right invariant covariance。

 So you can always map them。Now， if you don't have。Bers and。

And the linear reality that makes the filter depends on the state， this is exact。

We do have bias because you do it depend on the state estimate。It's imperfect。

 but it's possible to map， for example， you want to do right invariant correction。

 then you want to do left invariant correction。You can do that。

And then you want to go back to the maybe writing variant。So that's also possible。

 and the joint will help us to do that。So some process models naturally evolve on legal groups。

 And this filter is an error estate。Carllman filter and League group and is naturally suitable for those problems。

Despite the fact we violate all the theoretical results for noise and bias。Add。

It works very well in practice。 This is the preferred method。It has excellent consistency。

 You don't get spur correlation across different coordinates。 This is something that in。

Other versions of columnman filter you get spur correlation can make your unobservable state observable。

 and that's very undesirable because。The filter becomes over confidentfident over something that is not supposed to be observable。



![](img/24fe3a0227db5de3ddef09b31ec592bb_16.png)