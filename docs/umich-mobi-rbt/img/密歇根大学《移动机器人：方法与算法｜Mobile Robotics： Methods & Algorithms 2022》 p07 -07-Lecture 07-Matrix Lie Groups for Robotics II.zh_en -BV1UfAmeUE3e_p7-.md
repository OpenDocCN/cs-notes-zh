# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p07 -07-Lecture 07-Matrix Lie Groups for Robotics II.zh_en -BV1UfAmeUE3e_p7-

![](img/35782c0e92314b8798e9163c28e50aec_0.png)

Just。2 points。 last time there was a typo。 I fixed two typos。 One was the question about。

The identity element， which obviously should give you the group element。

I re upload the slides when I fix the type of。 So make sure you always get the latest。Version。

 you can see the date that I upload them。And in this example， I forgot to exclude the0。 Obviously。

 we can't divide by 0。 We should exclude it。So the group makes sense。With that。



![](img/35782c0e92314b8798e9163c28e50aec_2.png)

We're going to continue where we left。Last time。And that was。



![](img/35782c0e92314b8798e9163c28e50aec_4.png)

On the topic of a joint。I'm going to switch to writing， but I joint came up then。

I asked the question that if I have。The velocity in one frame， moving frame。

 Then how can I have the velocity in the fixed frame。You know it already for maybe a vector？

We can rotate it。That's not good enough。Because if you move and rotate at the same time。

 the rotation will generate linear velocity。 We know that from physics。

That if we rotate about a center of rotation， that angular motion for points that are farther from that center will generate。

Greatter linear velocity。So just rotating or just translating is not the same as rotating and translating at the same time。

 That's a little more complicated。So we need a generalized framework。

To automate everything and that joint will do it will' see。



![](img/35782c0e92314b8798e9163c28e50aec_6.png)

![](img/35782c0e92314b8798e9163c28e50aec_7.png)

And the second part is this figure is really good， and it is the truth。

But it's also very demanding to understand， because it's relying on differential geometric。Concepts。

These are not topics that most people have background in in engineering。 So it's。

A lot difficulty to imagine。Manipulating some algebra terms and making sense of them might be easier。

 So I'm going to try to do it for S O3 to convince you that。This is true。

But then we also argue that it is general and true for any matrix leaks。



![](img/35782c0e92314b8798e9163c28e50aec_9.png)

Let's switch to。

![](img/35782c0e92314b8798e9163c28e50aec_11.png)

And writing。

![](img/35782c0e92314b8798e9163c28e50aec_13.png)

I'm going to start with。The Lealzebra of S3， what does it look like？We said that this is a group。

Of all matrices。These are。Let's say three by three matrices。Such that。When you transfer the matrix。

You get the negative of the same matrix。Now， the only matrices that can satisfy this property are excuse symmetric matrices。

That's correct， Its03。 Thank you。you're learning。That's good。So， that's all three。

Special orthogonal group。Ex givesy matrix matrix。 I'm going to use omega。

 This is a very convenient notation， because we。Associated with angleular velocity from physics。

So if I have a vector omega。Of angle or velocity。I can write it。As this vector， as we are used to it。

This is。A three vector。You have three real numbers， will give us a three vector door。

We associate this with a rate of， the rate of rotation about。Access1， axis 2， axis 3， okay。

And we can think about。The 3D space， E 1， E 2， E 3。And you might know from linear algebra。

 the reason I use1，2 3 because we don't have enough alphabets if I go X， Y， Z。

And I'm talking about S3。We have to talk about three more dimensions。

 If I work with high dimensional spaces that we don't do， then we we're out of alphabets。 So 1，2，3，4。

5，6， is easier to work with。But these are the familiar X， Y， Z， okay， you could use X，Y Z as well。

Now we introduce a new notation。Call it veg。TheWedge notation。It has a。Hat。

Sometimes people put it in the middle。 It doesn't matter。This notation， you can。

Think about it as pointing up。 It's an expansion。It turns this vector into a matrix。

But not any matrix， it arranges。Omega 1，2，3 into exc matrix matrix。 so diagonal is0。If have omega 3。

 negative of omega 2。Negative of omega3。0。And0。So， in S03。All the matrices， they look like this。

Whatever you pick from that said。That it has this structure。But the number， the value of omega 1。

2 and 3 will be different。 that shows a different angular velocity。Now。

 this is very convenient to use， because。When talk about matrices。

We're gonna call it as part of S O3。 When it's a vector。 It's just R 3。

 You can obviously go back and forth without losing anything。

 It's just a matter of what you want to do。 You want to work with vectors or matrices。

 As we will see， both are important， and we need both of them。Now。

 sometimes we might abuse the notation if it's clear from the context， maybe the notation is dropped。

 I try not to do that。Because it will be confusing。But sometimes from the context。

 it's obvious that it must be a matrix。 It cannot be a vector。So pay attention to that as well。

 but I try not to abuse the notation。You can define the opposite of this as well， as called V。

Such that when you have omega hat。Which is， at this point， is。Basically。It's a matrix。

 You can call it S。Now， what。V notation does， is that。It moves it back to。A vector。

You might have a function。 It takes the matrix。 It reads。Element。1，2， right。To3。And maybe three。One。

 and then put it in a vector for you and return it。 So you don't lose anything。

 You can go back and forth。 you'll see it in my code。You can call this an isomorphism。

 that means there's a one to one mapping。 you don't lose anything。 It's just a matter of convenience。

So V is the opposite of wedge。And they are quite a standard in robotics。All right。

We learned a new notation。I'm going to point out that。I can be compose。

The ssymmetricsymmetric matrix into the sum of three independent。Matrices。

And the way I'm going to do that。We'm going to define G1。To be。0ero，1。0，0。0，1。Negative one。Now。

 this is equivalentval of my standard basis in。Are three， which I would write。1，0，0。

Why we will see you soon。If it's a matrix， we can have a vector。

 The basis should be a matrix as well。 So that this G1 will。Play the same role for us。

It's called usually a generator。 or we can call it a algebra basis。We can have。G2。

 that you can guess， it will be 0，0。Negative 1，0，0，0，1。So it's about the second one。

And this is a equivalent to。The standard basis for the second axis。I'm going to define G3。Now。

 it's easy to see that。This omega that we have。On top is。The scalar omega1 multiplied by G1 plus。

Scalar omega2 multiplied by G2。Plus， omega 3 multiplied by G3。

This is a equivalentval of working in R 3 and writing mega as a vector。Is。Omega 1， e1 plus。

Omega 2 e2 plus omega 3， E3。So we're gonna make ourselves comfortable with this。

 Sometimes we want to work with matrices， sometimes with。Vectctorors。For S E3。

 we will have six of them。G1， G2， G3， G4， G5， G6， because 3 degrees of freedom for the rotation。

 And then we will have three degrees of freedom for the translation。

 The S E 3 is a6 dimensional space。 The rigid body has6 degrees of freedom。 You understand that。

In 3D space。 So we need six independent direction in the space。

 These directions in the matrix spaces。Will be modeled using these generators。

So I'm going to give you a surprising observation。 And then we will talk about how to drive it。

 When we talk about the ad joint， we' will show where it comes from。I will define。First of all。

 you know that we can。Multiply E1。By E2 using the cross product。So the topic is。Maybe I should use。

A new page。Do you know cross product， but you probably don't know。Lee bracket。E1 cross E2。

 What do we get。A3。So the cross product will give a new vector that is autogonal to the other two vectors。

And these are unit vectors， so we're just really changing direction。Also。

 if we change the order of the cross product。Be real。Theygate the sign the direction。

It doesn't change the magnitude， but it will。 it does change the direction。So we can have E1 cross。

I'll just use this one example now。I'm going to define。This notation。See。

 we can start from defining something and show that it makes sense。

A lot of time textbooks do that as well because it's just convenient。

 but it leaves you to the question of where it comes from。It's nice to know where it comes from。

We'm going to define it here， hopefully in this lecture， when we talk about the ad join。

 then we show where it comes from。This will be G1 times G2 minus G2。Times G1， this will give you G3。

This is just a simple matrix multiplication。 G1 is a matrix。 G2 is a matrix。 Multiply them。

Sotoptract。The opposite multiplication， G2 minus G1。See what you get。You will get G3。

So that's the equivalent。This is a equivalentber2。Cross product， using these matrix spaces。

I wanted you to be more surprised， but that's okay。Isn't it cool？You can。

Deefine a new way of doing cross product， using matrix multiplication。And so with the same thing we。

G2， coa G1。That's a great question。 If this is the same as the cross product， does it。

Follow the same rule of。It's called anti commutivity。Meaning， if we change the order。

 do we get the negative sign。 Yes， we do。 If you do G2 and G1。Then we will get negative of G3。

So remembering the cross product formula is very painful。

 but this matrix multiplication to me is easier。We're not replacing anything。 but this is。

 if we're working with matrix spaces。We don't need to go to that vector version to do a cross product。

 We， we are doing。 We can do it in the。Mattrix form。 This is called Lee bracket。 Now。

 this is more general because the cross product is for 3D。 We don't have cross product for。

For dimensional， in the sense that we know and we work with it。

There is a generalization of that using exterior algebra， but that's not what we typically work with。

The Lib a， however， is true for any dimension。You can work in any dimension。Of the league group。

 and you still have the lead bracket， which is performing that operation for you。

That means it takes two direction in the space。And it gives you a direction that is autogonal to the other two。

Okay，This is very interesting because you can get a four dimensional space， grab two of the basis。

 and then you get a direction that is independent of the other two。😊，In higher dimensional spaces。

 do you have to。Multiply more than two matrices together。No， your matrices are just bigger。Your。

G mates。Are different because it's not just three by three。If it's n， it will be n by n。

So this is called Lee bracket。This is not a control course。

 but lead bracket is equivalentval of lead derivative in control for lead groups。

 you can do a lot of things with it。It's， it's a form of taking actually a derivative。就啲。

We're dealing in four dimensional space。Do you want how through个。112机。Of course sorry， G1。

 how G2 get G3， and then we simply do G2 come G3 to get。The question is， if it's four dimensional。

 what would we get， My answer would be write down， see what you get。

You have four standard bases form the generators。You will need a4 by four equisisymmetric matrix。

See what that looks like。Decompose it into four independent matrices。

 that you can sum them up and get the same vector， then use their liver， then。Pick two bases。

 then use Lee bracket to generate the other ones。So these bases are not unique in the sense that you。

 we could work with other bases in 3D instead of the standard basiss。These are now unique。

 You can generate。 You can used other types of。Basis， you can work with a negative of them， right。

That's another problem。 In physics， in fact， they complexify them。These bases to have complex number。

 but we don't do that。So anyway， this is the equivalent to the clock cross product。

 We'll see later why。And。It's called。The Lee brackets。

And notice that the result is always in the Lee algebra。You pick two elements of the Lee algebra。

 You calculate the Lee bracket。 The outcome is always part of the Lee algebra， again。Is this closed。

应该其实改个月。There。今晚关车个调。But if there are more than three like four。

 would we know what we need to combine together for the other。By말 one。过。So your question is。

 if we work with more than three dimensions， how do we know， how do we know how many we need？

How many bases we need。没。In question few basis。Well。

 we have to write it down and then see what we get。There is no point of guessing。 Yes。

 maybe we define one and 2 and get another one。 you call it third。Maybe you get another one。

 called it fourth。 I could call the first one here， third。It doesn't make any difference。

 It's just the naming convention， right？Well， we， we are focused on 3D。 So don't worry about it。

 Just know that。This is a very general framework。 You will work with。Hard dimensions as well。

So maybe not physically， but if you're working with some sort of data that might be high dimensional。

 you can actually rotate it so it might come up。In data science and mission learning。Possibly。

Allright， so now were going back to。The constraint we have for the rotation matrices， I want to。

Talk about the differential equation that is intrinsic to each league group。And that means。

Talking about。At art art transse。Equals。S omega cube， right。But also， are。

Transpos are dot equals some omega cube。I'm going to call this。S。And we're going to call this one B。

For the reason。We will discover。We want to understand this， why。It's like this。So。

 we're going to start with。The constraint that we have， we know that for S O 3。4。Any。

Rotation matrix in S 03。We have。Our transpose times r equals the identity。We also have r times。

 r transpose equals the identity matrix。So the rotation matrix is an autoagonal matrix。

Because it's the direct cosine of three perpendicular axises。When we move the axis。

 that's from the rigid body lecture。 and we project them again to the original axis。

 we do not change。The right angle between our axis。So any two dot product should be one。

 if it's the same vector。Then we have our our transpose。

And any dot product for two vectors that are autotagonal， will be 0。

That's where we get this constraint。So what we do， we will differentiate。This property。So。

 if we differentiate。This property， with respect to time。We get。A transs。Our do transpose， R plus。

Our transports are dark。And the right hand side is 0。 Our do is the time derivative up。

The rotation matrix。Whatever it is， we don't know。But， we know that。

We can have a rate of rotation if the rotation is time variant。That means a rotation has 9 elements。

 A 3 by3 matrix。 Our dot is a matrix that it has 9。Time derivative version of that。

So it has nine elements。It's not necessarily schsymmetric because you have to take time derivative of each term。

Whatever it is， we don't know， but it's a range of change of that rotation matrix。

So from this constraint， we can conclude that。So， we can conclude that。If you get a rotation matrix。

AndAnd you take its time derivative and multiply it by left from our transpos。

The same rotation matrix。It will give you a matrix。Such that。When you transpose it。

 you get a negative matrix。 We know that this this must be a exclusives matrix matrix。

So we know that our transse times are dark。Is a exclusivesymmetric matrix。

 Although our dart is not together they are。Now， if it's a schisymmetric matrix， then， of course。

 it belongs to one of it will be one of the elements of the Le algebra。 It's O3。So。

 that tells us that。The result will be in the algebra。If we do the other way for。Are our transports。

We can carry out this similar calculation， we get r dots， R transpose。Plus。Are our do transpose？

Again， we get a property that if you multiply the same R dot from the right side this time by art transranpose。

Again， it's the ssymmetric matrix。 So no matter from what side we multiplied by the transpose of the rotation。

We get a ssymmetric matrix。So algebra， this follows from。The constraint of the orthotagonal group。

Gemetrically， it has that complicated reason that。Which were mapping translating terms on the tangent space。

Where we are to the identity。And the Le algebra is a place where we get ekusymmetric interests。

So without just using algebra， we know that the result will be asymmetric matrix。Now。

 what we want to do， we want to make sense of this。 Which one is。Which， in the sense that。

I have two options。I need to pick one to work with。

 And under what condition I should choose which one。Once we know that。Then everything will be clear。

So the first one that I'm going to。Right is。R transpose are dot equals omega cube。Now。

 we know that if we have。A frame of reference。A， and I have another frame of reference。B。

The rotation that。Describes the orientation of frame B。

With respect to frame A that we saw in the rigid body transformation。It can transform。

Coordinates of a point in frame B。To be in frame A， in fact。

 that's how we derived the rotation matrix。 That was the derivation that。

Be followed to say this property is true， and the matrix we get for the change of coordinates will transform a point。

From。A moving frame， let's say to the second frame， to the base frame or fixed frame。

Or from body frame B to a fixed frame。What if I have。A vector。B。And that's。The difference between。

Two points in frame B， I call it P and Q。And I have a vector， V。It's a deelta。Between two points。

Okay。So we can have。Two points。And then you get the delta， you get a vector。 What about vectors。

 Can I also rotate vectors。So that let's say my velocity vectors in frame B to be described in frame A。

We can show that this is possible， because if we。Multiply。Both size by rotation。So our times P。

In frame B。Will， give me。A point in frame A。 The second one will give me a point， also in frame A。

This is just the equivalentval of that delta。Whatever it is。It's the same thing as。

Multiplying rotation directly to that deelta， because this is a linear map， obviously， will work。

It's the property of a linear map when you apply to individual terms。If you add them up。

You can directly apply the rotation to the output。So what we learn is that。佢。We， a vector。

In frame A is a rotated version of a vector in frame。B。So we just verify that this is true。

 So we know that if we have a vector and we rotate it。It will change the frame of reference。

There's a question and Lee bracketett， I'll get back to that when we talk about it again。

All right so。Let's make sense of what we have here。

 I'm going to write this as multiply both sides by rotation。We get。R dot equals R。欧mega。Now， this。

 of course， is's the same thing as we have in the first line。 This follows from the constraint。

 however。If I had to think in them in the。Mindset of frames。If omega is。In the body frame。

And if I multiply this by。A rotation that describes。The relationship。

 the orientation of frame B in terms of frame A， the results should be another vector that is in frame A。

So I know physically on the right hand side， I am just。

Transforming the angle of velocity with respect to my fixed to be in the fixed frame， right。

 So that means that I measure the rate of rotation in the body frame。

Which is what we physically are capable of doing it， because the。

Vellocity in the body frame is independent of your inertial frame。

 You can pick a coordinate here or the other side of the room。

 Your acceleroerometer or angleng gyroscope on the phone will read the same quantity。 Phically。

 of course， the gyroscope doesn't give a name that where is your coordinate。 right。

 That's just not relevant to the sensor。So we can read it in the body frame。

 iss an independent of inertial frame。 We can rotate it to be。In the fixed frame。

Which I should use S from now on because that's called。A spatial frame， which is a fixed frame。

It's the same thing as initial frame。Initial frames don't accelerate。

Fras relative to each other accelerate。 We're in trouble。And it's very common assumption in physics。

But for us， this is a fixed frame。 B is attached to the robot and is moving。this is。Body frame。

Your robot。Or sensor。So because of that， I may use S here。So， we learned that。The rate of rotation。

The rate of rotation matrix。Is described by the rotation matrix times。The angleular velocity。Now。

 we need to work with a matrix， because。The left hand side is a 3 by3 matrix。

 The right hand side must be a matrix， as well。This looks a little misleading because once you have translation。

 it won't be just rotation。But for rotation groups。This works。

If you were 20 on what it means to take that derivative。R with%。

So the question is what does it mean to take the derivative of the rotation matrix with respect to time？

Imagine you have。So we just showed that that property holds。

 and that describes the rate of rotation matrix。 I'm not going。I'm going to back to it。

So your rotation matrix， maybe is 2D。And maybe your angle is changing with time。

So we know that time derivative of。This angularous break time is something like theta dot。

What is the derivative of a matrix。It is easier than what you imagine。 So we just need to take。

The derivative。Element wise。You could flatten your matrix and treat it as a vector and then do it element wise as well。

Now， when you differentiate cosine， for， for example。

 you get theta dot times sine of theta or negative， whatever it is， right。

 We don't want to look into it。It's too scary。So。You just leave it at that。 right， So whatever it is。

 you can take the derivative。 It is some messy。Matrix of time derivatives of angles。

 And sometimes if you wish to look at it in some coordinates。

Maybe oiler angles or something similar to that。But it's a three by three。

Matrix of time derivatives of these individual rotation termss。Okay。

Because each column will describe。The rate of rotation of the， let's say。

 first axis with respect to the first axis， Second axis and the third axis。

 The second column will describe the rate of rotation of the second axis with respect to first。

 second， and third， and so on。So， we know that the。If we measure the velocity。

 anglengular velocity in the body frame。We can make sense of this。Property here that we drive。And。

It is the differential equation of the Li group。And， in fact， we can solve it。

 given given an initial condition， we can solve this。Assuming。

 let's say a deelta T time and this velocity is constant， we can integrate it。

 we will end up being a matrix exponential。This follows from homogeneous linear differential equations that are separable。

Just the hint that you will write。Like this。Now， you integrate from both sides。

Divative divided by the variable itself， right， when it's a derivative of the logarithm。

You can integrate both sides。Then take the exponential of both both sides。

The exponential will pop out， that's why we see it。You plug in the initial value。

 then you figure out the constant。Then for a Delta T time， what you get is that。

Between time and step， let's say K and K plus1， we get k。Plus， one。

R K plus 1 is R K times matrix exponential of。我们个。Delpha T。

This is the correct rule of integration for this matrix group。Not adding two matrices， because。

The exponential of omega deelta T will be ultimately， a deelta rotation matrix。Let delete。

This important remark here。And if you don't remember these ODs， that's okay。

 I can share references with you。But。That's a very elementary type of differential equation。

 and we can solve it。All right， so that's an integration rule。Which is， basically。

The rotation at the next time of step， if you discretize it using a Delta T time and assuming0 order hold。

 that means the input， the velocity during that Delta T is constant， is not changing。Otherwise。

 you have to integrate。Based on whatever rule it it's following that we don't know。So in practice。

 it's very common to assume zero order hold。That means your signal is like this for each。

Delta T is constant。First order hold means。It's linearly increasing。 You can do that， too。

 but it will be。Somewhat unnecessarily complicated， because something like a gyroscope。

Works operates at a very high frequency。This deel will be very small。Like 500 heads。

Hundred heads at at the minimum， but can be000 heads。So the Dlta T will be 1 milliseconds。

 for example。はい。反整嘅话。To equation。It's the nature that。I it because。我是。The first。そて。No。

 this is this follows from our linear differential equation。Topic。So you have。X do equals x。

Let's say a times x。We can separate this by writing Xdot。Over x equals a。

Now we can integrate both sides with respect to time。Because this differential equation is separable。

We can separate all the x variables。One side。All the other terms to the other side。

What is the derivative what is the function that is derivative is x dot over x。Lock。

So that will gave us。Log of。Absolute value of x because the domain must be positive。

This will give you。Now， if you don't assume a constant， you have to leave it at that。 right。

 If you don't assume a is constant or whatever it is， maybe it's a function of time。

You just have to leave it to be like that。Maybe it has a function， you integrate， you get a constant。

 anyway， you can relax the log。By taking the exponential。

 you take the exponential from both sides and get rid of the。Absolute value to contain old solutions。

 And you can get x equals exponential of。There will be a constant here as well， because。

When you integrate， there will be a constant， right， this constant comes from initial value。

That we might start from an initial rotation。 Maybe it's identity， right， We start， for example。

 from the identity。 That's where we start the localization， maybe。And then we want to track。

 So that's how we can integrate rotation as we read gyroscope data。Okay。

 so we are relying on the math here that we can solve this。Nummerary equation。Because。

That integration is。How do we get？The numerical results， the integral of a。Or A DT from。

0 to deelta T。 If a is constant。It will be。A times t from 0 to Delta T is a deelta T。嗯。That's。

That's exactly what I did here。It's assuming。Constant velocity that we will assume a lot。

In future lectures。You will see this input times deelta T。Okay。

So we get rotation at times k plus 1 equals rotation at times k times some delta rotation。

This exponential has a closed form formula for this group。 We don't have to talk about it。

 but it's a formula that you can use it。It's a good topic for Piazza。这事。でさしおみさは。我工贝。ベてさ。真。

What do you mean locally constant？zero order。The de。ま。That's such a good frequency。

 so that's like for each time step the velocity。Right， I mean。

 in the body frame is constant because if you drive a term in general， with respect to another frame。

Maybe some other interactions are going on， right？So， the velocity。In the body frame。

 we assume is fixed。 It's an assumption that。Within a very tiny fraction of time。

 my sensor readings are constant because the sensor is digital。 anyway， we have a fixed frequency。

And then we get omega at time T1， and then we get omega at time T2。

 And then the difference is 1 millisecond， maybe。Or 10 milliseconds。What's happening in between？

One of the obvious ways are let's say it's the same thing。

Somebody else say let's increase it linearly， somehow。Maybe you propose to。

Take a square root of that。You can do that。Probably nobody will listen to you but。That's an idea。

Yeah， so zero constant velocity is the standard assumption。Hi excusee me。后ome嘅 b。Itす。Directly from。

Sensor， yeah， we read it directly from the sensor。by art。So， it's。We get it from。你可一下。Yeah。

Oomega behavior is a function。That rotation major。あせ争。So omega B hat。Should not be。Some brand。原则还就说。

It isかです。The question is， rotation and angle of velocity are coupled because we have the equation that it's relating these two。

 meaning。The angle of velocity cannot be anything if I know the rotation， right。

And rotation cannot be anything。 If I know the angle of velocityla， that's true。However。

 this is a very nice differential equation。 I can separate the variables from to to size of the equation and directly integrate。

 We cannot， in general， integrate differential equations， because。

Might be a nonlinear or not separable。 In this case， we can。

 and we can integrate to know that relationship。And。

Tms of a time difference equation instead of differential equation， because for digital systems。

 we don't want to work with this。 We want to work with the time difference equation。

That's how you will code。 You don't code R dot。 You code R plus one equals R K times some matrix。

So the coupling is true， but because they can separate them。

 we can solve solve it and get the time difference equation， which is desirable for digital systems。

诶。So this is the correct way to discretize。Matrix groups。You will get an exponential。Now。

 we need to make sense of it the， the other relationship， right， So we covered one side。

 So now we know what it means to have。R transpose times our dot equals omega。

Alge rightly now we can make sense of it and physically we know what it means。However， we have。

By the way， I don't want you to， you know， you don't have to go read the whole differential equation book。

Just because you don't remember that。We're taking it for granted， maybe you remember。

 maybe you don't， you can refresh it if you want to。

Where there are some limited results that we we need to use， okay。So don't be hard on yourself。

If you。Did didn't take your differential equation course seriously in undergrad。It's okay。 we， we。

Use just some results。So what about the other one， This looks a little。Different because。

Now we have our dot， our transpose equals。Omega question mark hat。 What frame of reference。

We should talk about here。it cannot be the same thing， right。Because。

You multiply a matrix from left and right。 in general， you don't get the same answer。

Matrix multiplication is not commutative。And the rotation in 3D。

 it is not commuticative unlike rotation in the plane in 2D。In 2D， if you just rotate about one axis。

 it makes sense is they're the same。But about three axis， is a whole different story。

It becomes noncommutative。 So we know that algebraically， this cannot be the same angular velocity。

It doesn't make sense because。The order is changed。And when we write， our that equals。

This omega question mark times。R。I'm going to use。A magic formula here that we will prove shortly。

And that is。This property。Now， I'm going to go back here and write。A do。Equals R， omega。Ha our。

Which will give me。Where do I get？I need to。So what do I need， I need。Are our transs here。

So our R transpose is the identity。 I'm gonna to just add and。Subtract。

 which is multiplying by theverse。So I get R。 and， of course， we can change R to R transpose。

We will get R transpose omegaqku our。Just R。And we get r transpose omega this。

hole matrix will be sked， right？Our transpose or inverse is just another matrix。 We can always。

Substituted to get this relationship。So， what I will get is。Our transpose。Some of my go。As a vector。

By the way， this is a matrix， this is a vector， now you know， right？That's why it's a vector。

 you multiply it by the rotation from left， and then you make it a Q matrix in that relationship。

Okay， so what we can say about this one。So we have compared this to the previous equation where we had。

R dot equals r omega in the body frame， right？So together， we can say that。A transpose。

This omega should be。Omega in the body frame。Right。And therefore， we learned that this is， in fact。

 omega in the spatial frame。Because I am rotating my vector in the body frame。

 using a rotation that is describing the orientation of the moving frame， the body frame。

Respect to some other frame。We get to choose， but let's say it's a spatial frame。So if this is。

The rotation about body frame is the spatial frame。 Then we learned that。

One side is the velocity in the body frame。 The other side of the differential equation that also comes with the matrix group describes the velocity in the spatial frame。

So depending on what， which one you want to work with。You can choose your。Equation。

You have a question？第二嗯。I'mm confused to how we go。lying with our。関係です。

M a vector bar transpose omega into AS cube。From here on。Using this relationship that we will prove。

Shortly。Now， given that relationship， you follow what we're doing， okay， so we have to approve that。

If that's true， this conclusion is true， right？How do I improve that Oomega series？그 다 키。

Anger of her lot take。How do we prove that omega is the actual angular velocity。

 What is an actual angularla Mr。欧omega B。我明白毕。I mean。我没告。to be out pro。So。Oomega b is define finance。

Oh， so you mean what makes us think that S O3， the algebra corresponds physically to。

The angle of velocity。Well， we have verified this festival experimentally。Right，It works in practice。

 but also it is a model that describes orientation。It is the time derivative of rotation。

So what what justifies using a rotation matrix or oiler angles。

It's just the fact that it describes the rotation between frame， and we can derive it。Now。

 rate of change of that is the angleular velocity， because。The integration of that is the rotation。

So the angleular velocity is just a velocity for rotational movement， right， It follows from that。

So it's from Exp。Both experiments and theory。We're talking about the rotation of a frame， right？

What do you call the rate of that rotation？There were the rate of fabric。えす。A matrix。

 and it belongs to matrixtri group。And it is also。Yeah。

 we can only say that it is belong to S of three。 I'm going to make it simpler。 Let's say I have。

I have a circle here， then you have a car。And I'm not very good at drawing。

You are going around this circle。And it has an angle of。Feed at any time。

With respect to your horizontal axis。What do you call the rate of change of this angle。你叫落。

We could call it angular velocity。 I mean， we're not in love with names。That's what people call it。

So angle， angle or velocity， position， linear velocity or velocity。I mean。

 digging deeper than that is is too philosophical。But。This is from in physics， at least this much we。

Understand， right？Can you summarize for me what we？Absolutely， so we want to summarize what we did。

You got， did you get your answer。Think about it and then pose a question on Piazza。

 maybe but this is what we're doing exactly。Okay。All right， so。What did we do？

We said that we have a constraint in the autoagonal group。 If we differentiate it。

 we get two relationship， relationship 1。Is telling us that。Or dot or transpose equals。

Some angular velocity matrix。Exquisymmetric matrix。If we calculate our transpose R。

 we get another angular velocity matrix。We wanted to make a physical sense of them so we don't make mistakes when we implement。

These equations for calculations。So we started with one of them。And before that。

 we showed that our transpose our dot or our dot our transpose。Is excusesymmetric matrix， right。

 We first showed that in this page。Then we started from the first one， and showed that。

Because we get our dot equals R omega in this case。And if omega is in the body frame。

 the rotated version of that must be。The angular velocity in the spatial frame and the fixed frame。

 This is as simple as。Rotating your vector from frame B to frame A， okay。

And I'm sure you've done it many times to be here。You do exams， right？

should have solved some physics problem。So that's basically as simple as that。Now。

 if that's the case。Then it makes sense， because。At rate， which we integrate the rotation。

Is the rate we read the angular velocity in the body frame。And accumulated。喂。

Adding it to the previous rotation， which we could solve it to get this time difference equation。

 right。This integration rule， which is a discrete time equivalent of that differential equation。

So r times omega makes sense， however， when we look at the second equation。

 we have no idea what is omegaq times R。What does it mean to multiply the rotation from the right side。

 That's a little strange dose us。To make sense of that。

 we use this property that we're going I'm going to prove now。Once we're done with this part。

And that will give us。So we start from here， we go down。We have to use it。The property here。

So what we learn is that we can form this equation to be in this shape that r dot equals r times。

Some excuse symmetric matrix， but it's the。Our transpose times。Omega， in some frame。

Version of the Angular velocity， right？Now， compare this with the previous equation that we had。

 r dot equals r omega。They must agree。 otherwise something is wrong， right。You cannot have。

A two differential equations。 They look exactly the same。

 And then they give you two different answers。Conceptually， that's wrong。 Mamatically。

 that's also not correct， because。嗯。There is E theorum that the solution to the differential equation is unique。

 at least locally， is always unique。That's a fundamental result in ODE。

So then the term here inside this must。B。Equal。To the previous case that we had。Okay。

When we set them equal to be equal。And then multiply both firm left side by R transpose。

We arrive at the relation between omega at the body frame。Omega that we measure in the body frame。

Respect to。The same angleular velocity in another frame， which is our fixed frame。

And that is just described by a rotation between the two frames。So then we learned that， if you。

Basically。Integrate this equation now that r dot equals。R。Right， it will be like this。

If we integrate this using the same logic，0 order hold， constant velocity， Delta T time。

 We get R K plus 1 equals。Now the exponential is on the left side。Now， you read。In literature that。

We choose this。Integration or retraction rule from left or right， right， Both are correct。

 But they have different meaning when it when the exponential is in the left。It means the argument。

 the velocity that you have there is in the spatial frame。Now if you're doing an optimization。

 you might not care because who cares。It's doing something inside。 and then ultimately。

 willll give you a solution。 But when we're doing filtering。And directly dealing with these terms。

For maybe uncertainty propagation， then we need to be aware of。

Which bond you're choosing And which whatever you choose， you just need to stick to it。

 You cannot just change them arbitrarily。So that's。Basically， concludes。This part。

 I'm going to prove。The property that we used。Which you will be pleased that you will be pleased to learn that that's just the a joint property。



![](img/35782c0e92314b8798e9163c28e50aec_15.png)

For S O3， it ends up being like that。But when people don't want to talk legal。 Of course， that's。

Then we talked about cross product and other things。So， we want to。Prove。

That R omega Q R transpos equals。Omega times r times omega is cube。 And then as a reminder。

This is an S3。

![](img/35782c0e92314b8798e9163c28e50aec_17.png)

嗯。And。Oomega as a vector， is a three vector。So to prove this， we start from。First imagine。

 let's say A is。Any vector in R 3。Some， some vector。Did I tell you that。For a and。B in R 3。

A cross B is the same thing as you make exclusive matrix matrix and multiply that matrix by B。

I'm guessing you've seen it maybe in the past。But a cross product can be done using matrix multiplication。

We can prove it if we have time， we can get back to it。

 but the proof is just using direct calculation。Get A and B，2 vectors。 Get the cross product。

 See what you get。 Put it in a excssymmetric matrix multiplied by B。 If you get the same answer。😊。

That's the proof。If not， we will give your money back。对。😊，Its true。 I guarantee。This is true。

So the proof is direct calculation。Trick， I leave it for you。I can post it on Piazza， too， I think。

I should have it from last year's Piazza。Okay。R。So now， if that's the case。

 I can turn our omega cubed to just the vector。ACross a， okay？

Then I'm going to do R omega cross R R transpose a because our R transpose is the identity。

Then we say our times。We factor R。So we just proved that。From first side and the second side。

And a was any vectors。 So this is true for all vectors。Then the two sides must be true in general。

 So we get。This property。That holds for rotation matrices， and。Excusesymmetric matrices。

So that supports our previous driverss。Now， what if we have。Rotation and translation。

Very proof could you on type。terms。Your question is for。This part。ます。Oh， this part is。

This follows directly from here。Multiply both sides by R from the right side。Then， our dot is omega。

And the spatial frame times R。You have very good memory。

We were holding that for all time I was talking about this proof。You deserve a plus。

But we don't give classes here。So， okay。What can we say when we have translation。

 You can guess that it will get really nasty。And I hate these equations when you have something plus something cross。

 always hated that。Even when I didn't know league groups。If you want something that is clean。

 you just multiply a matrix y matrix or a vector。Don't ask me， what does it mean？

We learn one time what it means， but later we don't want to think about it。That's my philosophy。

That will make it automotive。 You understand what it's doing。

But we don't want to be involved in the level of mechanics of it。What is getting， I don't know。

 multiplied by something。But when we look at the matrices， we know。This is what we want to do。

And they higher level。So that， this is what we are after。What about rotation and translation？

So maybe you can。Imagine that at this time， I have angular velocity。And maybe also linear velocity。

And there's nothing wrong with stacking them。Into a vector。That is six dimensional。

This is just bookkeeping。 We can stack it in six vector。We're not changing them。

So what is the equivalent of that relationship we had with？Rotation matrices that when we。

Multiply rotation by omega。 We get something， another omega。In particular。

 body frame and a spatial frame。So what is the matrixx here？when Im multiplied by this six vector。

You will give me。Something like that。If this。Is the velocity in the body frame？

It will give me the twist。 This is called。Twistt， and we usually show it with。To see。

The Greek letter。But you can choose any other letter too。

So what is the matrix that when we multiply it by the twist， it will map it from the body velocity。

 from the body frame to the inertial frame。Now， you might think that that's just a rotation。Well。

 that's not correct， because。It is only true。 if you're only moving。Using a linear velocity。

 then that's a rotation。Maybe there is a fixed rotation between your frames， right？

That's basically mapping a vector from body frame to the inertial frame。 However。

 if you're also rotating and there's a rate of change for the rotation。

So the matrix that describes the rotation between two frames。E is evolving over time。

And that will result in。Some change in your linear velocity。Maybe I can convince you like this that。

Again， this is from freshman physics， physics mechanics that。You have。I have two points。You remember。

 we arrived at this relation。I chose a different。Let's see。The velocity of point。P in frame A。

I'm giving you the final results， because I think。It's better to spend time for other topics than driving this。

If you have two frames。A and B， the linear velocity of a point in frame A。

If you write it according to the， the point in frame B。

Is that the same linear velocity of point in frame B plus？The rotational。Vellocity of。This is。

This is basically V equals V B plus omega cross r， right？Oh， that's right。Thank you。

So you know it from this form that omega cross R。 So if you rotate and move。

 the rotational movement will contribute to your linear velocity。 That's just。In fact。

From physical observations and derives of the linear velocity between two frames。

 So it is not that simple。 This matrix will not be just a block diagonal of two rotations。

There is a term cross cross term after the eagonal term that takes the angular velocity and include its contribution to the linear velocity when it exists。

Okay， so we we have an intuition about this。 But again， we're after a general way of deriving this。

 we're not interested in。This way of manipulating terms。So that's。The topic of。Conjugation。

And matrix。Similarity。So what is a matrix similarity？Suppose I have。2 frames。E1， E2。And a point here。

 and I have another frame， E1 prime， and E。Two prime。And I know a transformation。And。

E 1 and E 2 to be a。 That's some matrix， whatever it is。 It takes a point x， and that。

Coordinate frame gives them me a why。Maybe rotates it， maybe scale it， whatever it is。

And I know our transformation。That is doing the same operation， but it is in the other frame。

 How can I find a relationship between these two matrices？Meaning。

 if I know the transformation that takes me from one frame to the other frame。

 can I map A to T and vice versa。This。Leads to。Matrix similarity。



![](img/35782c0e92314b8798e9163c28e50aec_19.png)

Not suppose。We have。Y equals P inverse。Why prime。Meaning P or P inverses is a relationship between is a transformation between the two frames。

Similarly， I can map X prime。So we have y equals a X。 So therefore， we have。

P inverse y prime equals A P inverse。X。And then y primes equal， y prime equals。PA A P inverse x。

Next prime。But y prime also equals t times x prime。 Therefore， we learn that。T equals P， A。

 P inverse。 This is the formula for change of basis in linear algebra。 You have a transformation。

 linear transformation in one coordinate frame。 you change your coordinate。

 You want to know what's that matrix。You need the relative transformation between the two frame to do change of basis。

Okay。Maybe you know the calibration of your Liar with to IMU。

 and then we want to know the same calibration。Transformation in the camera frame。

Well you need to know these relationships to do similarity transformation。

 It comes up in sensor calibration extensively。A could be any linear transformation， any matrix。

And Y， and S。be to。R to the party。S， I can understand。X is a point in this frame E1 and E2 x is。

Maybe we can think about it x1， x2。Why is。Y1， y2。 So obviously A will be 2 by 2。

 but this can be any dimension。Any vector space？As long as a is a linear transformation， is a matrix。

So， P is。P is rotation major。P is the transformation that describes。This difference。In other words。

 a。Equals P。Invest E prime。And E is E1 and E2。Or a prime equals p times z。It is， of course。

 an inverable transformation。You can think about rotation images， if that helps。啊H是可这E。To un name。

So以。Well you can have translation too， it doesn't have to be rotation。

You can think about the rigid body， right。That's probably the transformation you will come across a rigid body。

Rotation and translation。So this is called asymmetric similarity。

 where this map is also called conjugation in math。Question is。

 can we label X and Y in destroy drawinging？Yeah， why not we can have。X， we can have Y。嗯。No， no。

 right， no， x Y or not， the coordinate is at one point。So， a。Times x will give us y， right？

There are only so many letters I have to。Cheose something。Okay， so。

Now we know what is a matrix similarity？So when we see it。We will recognize it。So I'm going to。

Continue from。

![](img/35782c0e92314b8798e9163c28e50aec_21.png)

![](img/35782c0e92314b8798e9163c28e50aec_22.png)

![](img/35782c0e92314b8798e9163c28e50aec_23.png)

All right， so all these are stories now when I show you this slide， you know what I'm talking about。

You need to know all of that。 Then I'm going throw at you a conjugation map。And then I drop a line。

 a remark that noticed similarity transformation。Okay。All right。

So a map that here is a group element。G is a group element， rigid biotransform。

 A is another rigid bio transformationform。Calculate G times a times inverse。

 this is called a conjugation map。Take the derivative of conjugation map with respect to the middle part by assuming this rigid body transformation or rotation B。

Goes through the identity。That means if we parameterize it with some tea。At this point。

 you know that。We can have B of T to be。Exponential of T times B。 We just showed that this is true。

When you have a velocity in the Le algebra。This exponentiation shows up naturally and is the result of integrating。

Vellocity into the transformation。So if B is a path like this。It goes through the identity。

 meaning at zero， we will get exponential of zero， which is the identity matrix。

When you differentiate it， you get。B times exponential of T B。

 which is the same thing as exponential of T B times B。

 because the exponential of a matrix commute with。The matrix。Evaluate B prime at zero， what you get。

B。So take the derivative of the conjugation map at the identity when t is 0 with respect to the middle part you get。

This property， G， real rigid bio transformationformation times B times G inverse。

B is in the Lee algebra。 G is in the group。Does this make sense。

 Can we multiply rigid a rotation by angular velocity or a rigid body transformation by its equivalent velocity that we didn't talk about it？

Yes， every league group。X。Acts on itself， just like you can multiply rotation by a vector。

 You can always multiply the transformation of the legal group by its only algebra。 You。

 at the very least， you have that。 You can always do that。😊，So this always true。 makes sense。

 You can do the multiplication。 This is called the adjoint map。 However， this is not。

Giving us the matrix， this is a group。Version of that。We want to find the matrix。

My slides are not moving。Too stressed。So what we're going to do。First。

 how do we find a matrix version of this？Byhy just directly expanding this multiplication and see what we get。

Reearringing it into a matrix。That's what we do。And I have the derivations for 2D and 3D。To write it。

 but if there is no time to share it with you， but it is a direct calculation of some matrices。

You just need to read it。And see that it's true。We take one more derivative with respect to A to G。

It was something interesting。 we will see something interesting。



![](img/35782c0e92314b8798e9163c28e50aec_25.png)

That's my desktop。

![](img/35782c0e92314b8798e9163c28e50aec_27.png)

![](img/35782c0e92314b8798e9163c28e50aec_28.png)

是。All。Take the derivative of G。Or a， whatever you want to call it。If you have。A， B， A inverse， right。

Now， first time we took the derivative derivative with spec to B。 But you can also， once we have A。

 B， A inverse， we can talk about。A path for a。Exactly in the same way。

 Initial velocity A exponential parameterized by T。 that T is a scalar time。

 That's why it's called one parameter group。 Although it's not a group， that's just a name for it。😊。

They call it one parameter group that exponential of T because using a scalar T。

 we can generate the Judesic， the path that lives。Under the group。

So when you take the derivative of the adjo。With respect to A， you get the lead bracket。

So the Lib a is coming from differentiating the conjugregation twice。The proof is your exercise。

 It's not very difficult。 You need to find out what's the derivative of a matrix inverse。

There is a formula for it。 If you use that， you can get this result。If you ask it on piazza。

 I will help you to drive it， but if you don't， I won't give it to you。

So the lead bracket is what we defined previously。It is related to the joint and conjugation。

Mathematically， conjugation is the failure of the group to commute because if the group is commuticative。

This will be simply B。 You can just shift temps。 but for matrices， you cannot shift temps。

The a joint is the failure of the group to commute。Along a particular direction， B。

A vector in the Lee algebra。Because if it's commutative， then the adjo is identity。

 That's why for Ehian spaces you don't see a joint because it's the identity。It is there。

 but you just don't see it because。The space is flat， It's commutative。 It's always the identity。

Again， mathematically， the league group is the failure of the group to commute。In direction of。A。

 as you start moving in the other direction， B， right you're moving along a direction。

 you want to move， you want to change direction， how noncomuticative is your group is captured by Lee bracket。

That's what satisfies mathematician for。More geometric method。 This is the leaderer。

 So that failure to commute。Is basically a form of a derivative。

 The rate of change of a vector field A with respect to。B， which is the lead derivative。But for us。

We don't use Lee bracket。March。As far as I remember， but the joint is very important。

 That ends up being the matrix similarity change of basis for us。

 Why it is important because as we move into space。

 we are at a particular point in terms of rotation and translation。However。

 we want to track everything in the Le algebra because that's the vector space at the identity we want to work with。

In particular， we want to track the covariance and uncertainty at the tangent space in the tangent space add the identity。

 So the joint will help us to map everything from wherever we are to the identity to carry out all the calculation using algebra in a vector space。

 just like you're working in our N。😊，And then when it shows up again。

 that means sometimes it's necessary to go back to make sure we are always doing calculation correctly。

 because if you are using matrices in different paces and you combine them， obviously。

 the calculation won't be correct。 So I the joint them make makes make sure。

These transformations are done correctly and automatically。That's what we will get out of it。

But it is that matrix similarity。So I have a quote for the cross product that you can check。

And we had this question in the chat that。Is。A cross B。Equals。This， and that is true， we have it。

I might have this in my longer version of the slides that I shared with you。

It was just the fact that people would look at me。So what， so I removed it。No， somebody is asking。So。

 William， I hope you got your answer。If you're still there。

So that's where the Lee bracket comes from。Notice that we' are doing everything we can to just do algebra matrix multiplication。

That is nice。 We're not working with。Any complicated geometry。First se， and that's。

That is a big motivation。Now， one question。That comes up is the exponential of x and y。

 if they are a scalar is， of course， exponential of x plus y。 but if we are working with matrices。

This is not true。You cannot just add two matrices。 You can try if it fails for one example。Obviously。

 it's not true in general。This is only true， if your mates。Two matrixes commute。

 if they don't commute。You cannot just take the exponential and then add them。Now， the question is。

 what is？What is。Thank you， Raentov。Because the exponential of x is ultimately a group element。

You take the exponential of the matrix。X from the L algebra。 And then you get a matrix， let's say。

 rotation or rigid body transformation。 You do the same thing for y。Ultimately。

 you have two matrices of this form。R1， r2。Now， what is the equivalent of。The result in the algebra。

 What is this Z that will give me this outcome in the left side。So the answer to that is the B， C。

 H formula。 Baker Baker Campbell House so formula。 There is no simple answer for that。 That's。

 that's infinite。This infinite series。Which only the first two terms are what we thought it would be。

If they are commutative。If two vector feels commute。The Lee algebra terms， the Lee bracket will be0。

That's why it was the failure of the terms to commute。You can test。Go back to。Those examples， why。

 because the crossproduct of a vector by itself or any parallel vector is 0， You just can't do that。

 that's the reason。So it will disappear if they are。Communicative。

What is interesting about this is that you can have equivalent of matrix multiplication in the group。

By just manipulating terms in the Le algebra。That's very magical， because。

We are just doing Lib bracket operation nested Libbraia， this goes。Infinitely nested。Yet， we get。2。

Do something that is the equivalent element of a group operation。

 This correspondence is not an accident。 And， in fact， this is a property of league groups。

L groups are generalization of matrix group， but whatever we talked about are true for league groups。

 not all league groups are matrix groups。But the ones that we work with are matrix legals。

And that means there is a one to one correspondence between Lee algebra and the group of these matrixrices that are nonlinear。

 We just have to multiply them。This is nice。 We can work with a vector space。😊。

To carry out calculations that will help us to。Capture whatever problem we want to solve in the league group。

And that's what exactly we want to do in filtering and state estimation。

So that one to one correspondence is a result of the Baker Campbell House store formula。

 although there is no clean formula to do that。But we will use that series for linearization。

Some useful league groups by now， you know， S O3， S E3。This S E K3。

 you can keep adding next time I'll talk about it。 You can keep adding vector spaces for IM U。

 we will add position and velocity。 So you get S E2，3。Not just rigid body transformation。

 which is rotation and position。 We will also add velocity。For Islam， you can add landmarks。

Thats for legged robots， you can add contacts。 This group is very interesting。Same three。

 we talked about it is a generalization of。Ass eatery with the scaling。

So next time we can finally talk about motion of a robot， if I have a robot。

 it operates an S2 and I want to calculate the oometry by propaganda and covariance， what can I do。

 We can do it of course in 3D as well。

![](img/35782c0e92314b8798e9163c28e50aec_30.png)

So hopefully， we can talk about some sensors and how we can。

