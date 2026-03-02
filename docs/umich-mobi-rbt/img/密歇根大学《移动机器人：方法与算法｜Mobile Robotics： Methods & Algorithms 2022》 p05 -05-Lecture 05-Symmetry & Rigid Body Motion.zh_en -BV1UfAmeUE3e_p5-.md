# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p05 -05-Lecture 05-Symmetry & Rigid Body Motion.zh_en -BV1UfAmeUE3e_p5-

So in this lecture， we will talk about rigid body transformations。When we start from scratch。

 we want to talk about linear transformations。And we want to touch on the topic of symmetry。And。

I'm going to talk about a little how symmetry relates to these transformations。

I don't assume you have any backgrounds， but we， I'm assuming that you know， a matrix， a vector。

And I know a lot of you know about rotations in 2D and 3D。That background， obviously。

 will help us to。We a better understanding。But I'm going to start from basic and then we make it gradually formal。

In today's lecture， we focus on rigidary transformations。

 which are a class of transformation that are very helpful for us in robotics。😊，In the next lecture。

We。Generalize them。 And also。Basically， locate them in a bigger land of methods that that's called matrix league groups。

So， first。What is a linear transformation？So a linear transformation is。Any map。That。Preserved。

Two operations。Vector addition and vector multiplication by a scalar。

 These two are properties of vector spaces。If you have a map。That act。And a vector space。

 that means a t vector gives you another vector。If you。

Apply that map to the linear combination of any two vectors from that space。

 The linear combination means。Multiply them by a scalar and add them up， right？

It will preserve that structure。Those maps are called linearar。For example。

 if you have a map such as T。Act on a vector， such as a。You see here that。If we multily A by C。

As of vectorctor C is a scalar。And then apply the transformation。 It's the same thing。

 And as applying the transformation on a and then multiplying by the scalar， you get the same result。

 That's the property of a linear map。Or if you add two vectors， right。

It will preserve this structure。It's the same thing as individually applying the transformation to these vectors and then adding them up。

You can write them together as well。 that if you apply to， say， alpha times a plus beta。

Times B is the same as alpha times。T of a plus beta times T of。B。

So this is called a linear combination。Alpha beta R。Real numbers。A And B。Some vectors。

The dimension is not important， R， N。So what is interesting about linear maps。

Do you find anything interesting here？Or you find it boring。It mightight be boring。

 but you will be pleased。If any problem possess this is structure will make your life very easy。

So this transformation， transformations that are linear， they fix the origin。

It will not move the zero vector to vector another vector or another point。So if you pass0。

 you will get0。A map。That the function or map that takes。So when I say map， I mean a function。Right？

So， a function that。Take something and gives you the same argument。Is is fixing that value。

 It's called the fixed point of that function， right， So the transformation。That is linear。

 It fixes the origin。This is very important。 That means that when you apply this transformation to vectors。

 it won't shift the space。This is a property of linear mass， because if。Let's say alpha beta are 0。

 right。0ero is part of the vector space。And it will give you zero again。

So this is true for all linear transformations。Now， you can verify this quickly in Julia numerically。

 if you define a matrix 2 vectors， A and B。The scalar， you can add them up。

 then apply the transformation T， right， which is a  two by two matrix。T here is a 2 by two matrix。

Now linear maps， they don't have to be informed of a matrix。

 but you can have a matrix representation for a linear map。Okay。

Or you can do it individually and you get the same answer。As expected。You could。

 I know this is very trivial， but you can consider this as a crash course on Julie as well。

You see how easy it is to write the code。Now， unfortunately， I need to clear my writing when I move。

Because。It's the static on the screen， okay， it's not like my slides。

So you can verify this numerically， and。You get the same answers， whether you。

Do your operation of linear combination before or after。Now。

 what are the examples of linear transformations？Scaling。You get an object， get a vector。Scale it。

 make it twice。Of the initial size。Is it scaling a continuous map or discrete。

You can gradually scale something， right， with any factor that you want is it is continuous。

You can assume a linear number that is controlling the scale of an object。Right。

 so it is a continuous map in that sense。 Reffction， however， is discrete because。You。

Have an object you assume。A line， right， and you calculate the reflection， with respect to this line。

 it will move。The object the other side of the axis of reflection， right。

 it is not a continuous movement。But nevertheless， is。A linear map。There are other examples as well。

 rotationtation is one of the most important ones that we want to study。 Rotations are linear maps。

So if the linear map fixes the origin， is translation a linear map？It is。😊，Does the translation。

Fix the origin。So translation map means that it takes a vector x array， takes a vector x。

And that gives you x plus a。Okay。So if you have0， it'll map it to0 plus a。

So it will actually shift the origin。Right these are called。Linear varieties or a fine。

Transformations， they're parallel， right？That's very similar。

 but it is a parallel version of what you had before。

 So these are called a fine maps that we will see。So the translation is not。

 We can intuitively relate to this idea that the translation is not a linear map。

By the strict definition of the linear map that it needs to preserve the linear combination， right？

Now， you can also。Check the math that。If T is a translation。

 meaning it takes a vector and adds another vector T。Well， we can check if T is applied to a plus B。

 you'll get a plus B plus T。But if you apply T to A and B。Separately， and then。Get the results。

 You're actually adding a plus D plus B plus T。 You get two times。T here。

So it fails to satisfy one of them。 That's enough to disqualify。

The transformation to be a linear map。You can check the other one as well。In fact。

 it fails to satisfy both of them。So the translation is not a linear map because it does not。

Satisfy these two properties。Now， is the identity matrix a linear map。This is the identity matrix。

Let's say three by three。Is this a linear map。Yes， because if you can apply it。

 it satisfies all the properties weve talked about， it fixes the origin as well。Okay。Quシ？

Are there matrices that are not？Question， are there matrices that are not linear maps。

So a matrix is a linear map， right？Now， it depends how much constraint you want to put there。

 It might not be an invariable。Matris， right？But it is linear because a matrix is a mapping from one vector space to another。

In general， if it's。Rectangleular matrix， right。The columns of the matrix， right。

 will span a vector space。But basically， span。At least the subspace， right？

There is a mapping from one vector space to another。 So it is a linear map okay。However， you。

 you don't need matrices to talk about linear maps。 Matririces are very convenient。

Is very are very convenient objects to。Talk about linear maps。 And that's what we will do。

So let's check the scaling how can we。Without any， you know， formal discussion。

 how can we come up with a scaling。Transformation as a matrix。Here's an idea。 take a matrix。As。S 0，0。

 right， S is some real number。 multiply this by any vector X， Y。

This will give you S times x S times y。S， X， Y。We could have different factor， a scale for x and y。

So a scaling matrix looks like this。 It is a diagonal matrix。With some scaling factor。

If you have after aagonal termss， it will cause shear。Right，You can stretch objects。Okay。

 so you can visualize this。Again， just the warm up， you can code in Julia and test。Some examples。

Define your matrix。 Define your vector。You apply this transformation in the scales your。

Vectctor to be twice as big as the， The red is twice as big as the。Blue one。A question。

 a philosophical question。 Are we scaling the vector or are we scaling this entire space。

In this case， I'm scaling the vector， right？But I could just make the scale of the。

An entire plane to be half of what it was that would make that would make my vector to be much bigger。

 right。So this is ekin that transformation can be passive and active。Activism。That's what we do。

 We transform the object。ButIt's also very common to think about the transformation as a passive transformation。

As if I'm rescaling the entire plane， these objects live on。Those would be an example from where you。

S the。Oh space。Well， it depends if you want。 Well the question is， what would be the an。

 an example of， let's say using passive instead of active。

 It depends you want to work with the inverse of that transformation or the transformation itself。

 It's very common in aerospace to work with the inverse of a rotation matrix。

 which we will see later。As we move forward， that's basically modeling。

The problem in the frame that is attached to the airplane， aircraft。Basically。

 you assume you are the center of the world， right， Everything is rotating around you。Which。

 in a sense， is true。 That's how we operate。 We don't care about a coordinate it's attached to a corner。

Right。The way I see the award， I am the center， and everything is relative to me。So it makes sense。

 That's how you can imagine a bird is。Probably perceiving。As as it' flying。

 it's very reasonable to do that。I use the direct， you know， the， the active version。

 and it's very common in robotics to use the rotation itself relative to a fixed or inertial coordinate frame。

It's。A little is matter of taste how you prefer， but sometimes it does matter。

 because if you want to build a map， for example， to be a global map。

 probably you want to build that map with respect to some origin fixed coordinates， right。

But maybe you want to make a robot centric map， a region around the robot as the vehicle is moving。

 you just want to track that part of the map。 You don't want to map the whole world。

 You just care about maybe 20 m around the vehicle。 that's very reasonable for a lot of applications。

And it's very efficient。Does it ever have？Do what to say。后被告把。第如话你。You use。but for the robot itself。

I all use passive。Your question， I'm trying to understand。

 you're asking if I have a robot man manipator， and then I have a frame attached to the end effect。

 And there's a base frame。Look as like a plane， right。Yeah， well I get。

As in you're not sore about where。And other but those still really。是。让 by。呃。

Parts of the right do have a road。The robot can stay in place。Thats my private door。这一块。

And the robot actually moves。You care where the robot is。

Rather all those with inspection market andmigrant。😊，发生。And that was a good example。

 If you have a robot arm， the robot is moving， You want to open the door。

 Do you care to have the relative pose of the handle。Or a doorknob with respect to the arm wristst。

Or with respect to some fixed inertial frame for the manipulator。Probably in the。Arm wrist， right？

But everything is possible。 These are just。The change of coordinates and transformation。

 as we will see， is's a body frame， inertial frame， and you can go back and forth。

So it's a choice that we can make。And in an ideal case， we can go back and forth。 There's no problem。

先好。which is fine， you can also do it all that and it's the same。Yeah， thank you， Aerospaces。Folth。

Don't like me。I'm changing the convention， so。So the scale is one form of transformation。

 You can apply to a vector。 It will give you another vector。Rotation。I can do the same operation。

 using a matrix。I'm defining a 2D rotation matrix here。Using the familiar equation that。

I trust you've seen it before。Co sign up the。Mine is sign of theo。And。The second row。

 So I take a vector， the blue vector。The rotation acts on this vector V。

 or I'm applying the rotation matrix to this vector V。 I get another vector U。And it is rotated。

 and I'm rotating it by 45 degrees。Okay。45 degrees。Counterclock white。Right。

 so the rotation is around the Z axis pointing up。If you rotate it with the negative of this angle。

 obviously goes down， right？It rotates clockwise。We go through it。

 but you already know that the inverse of this。Rotation is。The negative of that angle， right？

It's the rotation that will cancel it if you apply it again。So this is also a linear map。

 I know you see sine and cosine， where it doesn't matter when you evaluate it for a particular angle。

 you just have a matrix of numeric values。 So it is a matrix。 It's a linear map。Right。

So it is not a good idea to write this sign on cosine multiplied by a symbolic vector and then call it an nonlinear function。

That's not a correct way to look at it。When you think about it as a linear map， as a matrix。

Now it is a linear map， a matrix is an appropriate tool to look at it。We put it in a matrix。

It is a linear map。Why you see sine and cosine we'll see in a bit。

So if you multiply the rotation by vector。The first row obviously gets multiplied by the vector as a column。

Or the another way you can think about matrix vector multiplication is that。

You get weighted some of the matrix columns。Using your vectors coordinates。是。

This is the second way of multiplying matrices， in particular， matrix and vector。

You can see it from here， right， You can just separate them and then factor V 1 and factor V2。

So this is essentially multiply v1 by the first column and then plus v2 by the second column。

 This will give you the same result。What is interesting about it is that。As if we。

 these are some new。Basis vector， right？Intuitively， you can think about。

These two new vectors that are now using sine and cosine as。Two new basis vectors。

Can we derive the rotation matrix using this idea， and that' that's what we're going to do。

So let's dive into the rotation。So the rotation is a circular movement of an object。

 You can see there's an sphere here， there is an axis。You can rotate about that axis。

How many number of rotations do we have， let's say for thispher a 3D object。Infinite。Why infinite。

Yes。You can be any number， right， You might choose an arbitrary angle or axis for your rotation。

 And that can。Basically。Constitute infinite number of configurations for this object to rotate in the space。

So it is a continuum。 It's， it's a continuous way of moving object。嗯。

But it is also a particular way of moving the object。 It's it's only rotating it。Alright。

 let's drive the 2D rotation matrix。 I don't know if this is how you learned it。

But this is a good way to derive the 2D rotation matrix。Suppose we have the 2D plane。

 We work with our。Standard basis， E1 and E2 for R2。These are the standard basis of R two。

The code is just reproducing the plots I'm using。Now， imagine I take the these two standard bases。

 the blue axis。 I'm gonna rotate it together with。Together as a rigid object， I not changing the。

Their perpendicular nature， right， together and rotating them to。Become these。Red vectors。

 And then let's call them E1 for I and E2 prime。So， a。

Prime and E2 prime are rotated by an angle of theta。Okay。Now， what is the linear map that will send。

The blue set of vectors to the red set of vectors。That sounds like to be a rotation matrix。

So we want to find what does it look like。So， one way to。Think about this problem is that。

Write down the coordinates of。The transformed red axis in terms of the original， the fixed axis。

And by that， I mean。What is。The coordinates of this vector with respect to the initial horizontal and vertical axis。

 right。Now these are unit vectors， so there is no length。So all we need to do is think about。

Their projection， right， which is a cosine。And sine of theta for E1 prime。For the second one。

 it ends up being。Because this angle is datata， right？So the first one is negative of sine of theta。

 The second one is。Cosine of the。So we got E1 prime and E E2 prime in terms of。That initial。

Coordinate frame。These are also called direction cosine vectors。Okay。

Because all you do you take the projection using Tg and then you find out the coordinates of the transform。

嗯。Ortagonal auto normalmal frame。Now， the trick is now you， we need to ask the question that。

If I have a back door， we。And we is。Reten in terms of the red coordinates E1 prime and E2 prime。

What is the equivalent of that vector， Let's call it V prime。In terms of the blue coordinates。

Obviously， we want prime and V to prime。 They cannot be the same thing， right。

 because I'm using a different set of basis to hold this equality。And I know it's the same vector。

 right， The vector is the same in the plane。 I am just changing the frame that I'm observing that vector。

😊，RightThere's got to be some relationship that helps me to relate these two observers together。

 And that is my rotation matrix。Because the vector is fixed in the plane。 And I am not changing that。

 I just want to observe it from different。Frank。imagineag two people， right， looking at an object。

 You say it's 1 m away。 Your friend says it's 2 m away。And maybe there's a relationship between。

You and your friend， right？So that's the observer frame or frame of reference。 Now。

 when you use this property that。These two must be equal。 What we learned is that。

We just substitute E1 prime and E2 prime， right， and expand it。We learned that。This relationship。

 basically。Is captured by what you see here。So we1 prime is v1 times cosine of theta minus v2 times sine of theta。

 Similarlyly， you have an expression for v2 prime。 Now。

 let's reararrange it in a matrix that is multiplied by a vector。 We want and V2， right。

 What's left is the rotation matrix。 So that's how we can prove。That， indeed。

 the 2D rotation matrix admit this representation。As a way of changing your observing frame。

For an object that lives in the plane and is not basically moving， right？

So we get our rotation matrix。Now， this way of， you might notice from linear systems course。

 this way of mixing。Basically。A systems response across different bases， right， and adding them up。

Is a property of linear systems。 If they're not linear。

 you can't do that because the outcome won't be as simple as。The same linear combination。

This is called superposition。And it's the property of linear maps。Okay， so。呢个咧。

Can we call this change of basis？It is for your vector， right。

 but change of basis for a matrix is different。Because you might express your matrix transformation in one。

Reference frame， and then you want to change it in another reference frame， right？For example。

 you have。A camera， you observe an object， and maybe you have a lidar on the robot。

 and you want to see the object。In the frame， in the reference frame of the lidar。

So you need to know the relative transformation between your camera and Liar and then do a change of coordinates to。

Basically， get that。Object now， if that object。I mean， in a mathematical sense， it's a matrix。

 the change of reference。 It looks like a conjugation。 It's not just a matrix vector multiplication。

 right。But for your vector， you will do it。We see in legal lecture that。

The ad joint map will do the change of basis for you。By the way， that motivates the calibration。

 right， because you might want to relate。Different observations or combine them for a state estimation in one common frame。

 you do need calibration between different sensors on the robot。In an ideal setup， we。

 we might assume。They're co located， right。But it must certainly not because they're physical objects。

 right， Maybe the IM U is here。 Maybe the camera is here。

That might cause some error in your estimation if you do not count for that， okay。

I think we talk about right。Canandre later。 But you know that already。

 your thumb is along the axis of rotation， right， And when you bend your fingers。

Ssuming you all can bend it like me。This is how you rotate。Right， use right hand， right。

 Don't use left hand。 That will change the convention。That's the positive direction。

Let's talk about circle group。What is common between that2D rotation matrix and the circle。

Asking the question in a better way。What is the set of transformations。

That when you apply to this circle。It will leave it unchanged。 And by that。

 I mean you close your eyes， I transform this circle somehow， you open your eyes。

You think nothing has changed？You will not recognize any changes， right？

What is the set of all transformations。That lead to that behavior。Iose of 360 degrees。3，60 degrees。

 What if。So your guess is 360。 What if I rotated 5 degrees？Will you notice？On this particular stick。

 you don't。 if I have。Let's say。I put a landmark here。 You're right， right， this object。

 you will notice because if I rotate it 60 degrees， this will move here。

But I'm talking about the smooth circle， There is no。difference at different points， right。

So it's a circle like this。Ignore all all their numbers and red and blue。Drawings。

If you represent the rotation。I'm change that a little bit。

 You're saying that the transformation should not scale。

Because if the circle becomes bigger or smaller， you will notice， right。

So one condition under transformation or one constraint on the transformation that we definitely want is that it should not scale。

Not making it smaller， not making it bigger。 Pre the distance within any two points。

And that is called a rigid transformation。Okay， which we will see it leads to the determinant of the rotation matrix being one。

Don't scale it， don't reshape， don't deform the object。So don't do。Don' to scale。

So we know that the scaling， although it's a linear transformation， is not part of that。

Group that we're talking about。So any rotation will give us the answer， right。

Rotation about the center of this circle。 If you close your eyes。

 no matter what's the angle amount of rotation。I can rotate this circle。 You open your eyes。

 You won't notice it's just the same circle。 It leaves the space unchanged。Now。

This is the same thing as。A 2D plane， right。The 2D plane or just realign， right， realign。Is infinite。

 It goes from negative infinity to positive infinity。If you close your eyes and I shift this line。

1 unit。With whatever。Basically metric。Forward or back for。 you won't notice because it's infinite。

 right， It's like a wallpaper pattern。In a sense， that's also a symmetry of that space because it leaves the space unchanged。

So we say that。2D rotations are。Forming this， they formed the symmetry group of the circle。Right。

These are continuous symmetry of the circle。Because when you。Rotate the circle。

You get the same shape。They are identical。This is a concept of symmetry in math。

And it's heavily used in physics。 Now， league groups。Are the best。

Mathematical way we have to describe continuous symmetries。That's why we are interested in studying。

 That's why in physics。They use them， okay。at this point。

 it's the best tool we have in mathematics to study continuous symmetryries of。Different spaces。

What about。Sear。This is 2D。 Let's make it 3D。 What about the sphere。If it's a smooth， you know。

 no color， no pattern， just uniform。ItSpear in 3D。You can rotate it in 3D in any way。

 around the center of that。Sear， right。So the3 rotation group will form the symmetry group of that sphere。

Again， because the test is close your eyes， you apply。

Any of the transformation from that symmetry group， you open your eyes。You will not know。

Nothing has changed。So， that's why。These matrix groups or legal groups are very important because they capture very fundamental structure about the geometry。

That we use them for manipulating coordinate frames and moving objects。 And in robotics。

 it just pops up naturally because you have joints， arms， articulation， different sensors。

 You're modeling the geometry to build map or estimating the trajectories。

 It's a very natural tool to。😊，Use， and as we go forward。Hopefully。

 you get a feeling how it's connected to maybe other methods that you've seen。Now， for circles。

 one interesting observation is that。If you know a little about complex numbers。

 because the unit circle is basically。A group of old units complex。Numbers。Right。

The complex number is x plus IY。If all of them have magnitude of1， that forms。A circle。Why， because。

This， this is the equation for the circle， right。没有。You。n the oiler identity。

I shared the proof this morning with you。In case。You want to know where it comes from。

It's very easy to prove。 But the exponential of I times theta equals。

Cosine of theta plus I sine of theta in a complex plane。

 you can imagine this is actually modeling all the points on this circle， right。

And the complex plan for you。Now， what is interesting is that。

This is a equivalentval of our 2D rotation matrix。 This is no different。 You just。

 if you choose to work with complex numbers， you need complex numbers， right？It acts as。

Rotating your vectors。When you multiply it。But we we used to using 2D。Rotation matrices。

Very important observation here is that adding angles。That we see here。は。So adding these angles。

Conorresponds to multiplying。2。Conative rotations。Is this by chance。

 Is this where Are we up to something。And absolutely， this is what we're going to generalize。

 You have an angle and you can do algebra。There is an exponation。 You get to multiply。There is one。

 to1 correspondences here。When we generalize these to higher dimensions。

 then we're gonna talk about tang spaces and Lee algebras because maybe maybe it's just not。

 it's not just one angle。 Maybe it's in 3D。 Maybe you need three angles for rotation in 3D。

 Then you see that when we add these angles in。A vector space that we're going to name it Li algebra。

It will correspond to multiplying rotation matrices in。

Some space of rotation matrices that will be3 by3， okay。

So this observation holds in higher dimensions。Now， in this case。The order is not important。

 and we will see the order becomes important when we go to higher dimensions。Because this is a scale。

 it's not a matrix。 Marices are not commutative。 We can't just change the order。The way you want。

 we need to follow some more rules。But this， this is very important because it doesn't matter how you choose to work with a rotation。

 whether you want to use UniiCcle or 2D rotations。 these are a equivalentval。

 and the fact that we can do algebra instead of。Multiplying here scalers were later matrices。

It's very important again， because when we can do algebra。

 usually we can solve the problems much more efficiently。We are good at doing algebra。

 whereas working with。Perhaps geometry will require a lot more knowledge。 and will be harder。Okay。

So on the surface， some of the tools we using might look difficult， but actually。

It is a simple way of running the calculations because we use linear algebra。

We reduce the geometry to algebra。So that's the takeaway from here。 And remember the exponential map。

For a scale layer later， we will have matrix exponential。

Anaous to what you see here for exponentiation。Now，3D rotations。You probably know this。

 You can name it roll pitchach， ya， right？How can we drive this role is。

Usually forward looking access， right？Peach is。basicallys。Bending forward and backward。

And your is usually about the vertical axis。Or in。Aerospace is very common to work with downward。

Basically， Z axis， is's also very common in computer vision for camera。

 we usually assume Z axis is pointing。 Now， we actually assume Z axis is pointing towards the lens of the camera。

So you might see different convention and different setup。But that's not a concern。

 We can always map。Any setup up to the setup that we want to work with。Now。

 how to derive the 3D vector， can we do what we did for the 2D case in this case。And the answer is。

 yes， you can assume that we have。Our standard basis for art 3。And。You have an orthoormal frame。

Let's say we want to rotate it about the third axis。So when you rotate about an axis。

 it will leave the axis unchanged。We can all relate to that。So the third axis won't change。Because。

That's what will happen， right in playing， you're just rotating the other two axisxes。And。

We write down， as before。They condition that if I have a vector。And it must in， in the new。Basically。

 according to the new set of basis， if it takes this form， why is it equivalent using the old basis。

Then you can solve for it， then you can arrange it in a matrix。

 and that will give you the rotation matrix about the Z axis。Again。

 the columns are called direction cosine vectors as well。

That's one way a lot of books to start from there and tell you。

Arrange the direction cosine made vectors， and that will give you a matrix。

 that's called a rotation matrix。But this is， this starts a little before that。

Gives you a little more information where it comes from。Now。

 your exercise is to prove for Y and X using the same process。

So these are familiar rotation matrices about X， Y， z， right？Its in a sense， it's trivial to drive。

 If you don't remember， you can just drive it。Or you can Google。So a fine transformation。

 what is linear， what is a fine？And a fine transformation is a combination of a linear transformation and a translation。

So although translations weren't linear near map， but they're very important。

We care about translation as a map a lot， because that's how objects move。ok。

So the objects in general can rotate and move， and that can happen at the same time。So。

 the general form is that。Apply a linear map， plus。A translation。This is called the A transformation。

Of the point or vector。Now， you can have many types of a fine transformations because you can have many types of linear transformations。

 But of particular importance for us is a class of。Rotation and translation。

 basically using any real vector。 These are rigid body transformations。

Rgit because they preserve the distance between any two points on on the object。

Whi is what you expect， right？If you want to come up with a model that describes this motion。

You already know that。There's nothing。Different about this object at this point in the space or this point。

So this model will respect as structure。This example is。え。Now， T is a three vector。T is like X 1。

 x 2， x 3。Or。T1。Now， your question is if it is， it is constant。

Well it can be if it's the transformation that is given， its constant。In general。

 it can be any number， right？Maybe it's given and you want to transform a point。

 maybe a set of points is given， and we want to find a transformation， so it depends。

In point cloud registration topic， that's the problem。 I have 3 set points。

 I want to find this linear map。 It is a fine transformation that aligns these two point clouds。

 How can I do that， right？ Then we're gonna see how we can formulate an optimization to solve for that。

So if I have a pyramid。Or any other objects。 This is an example。And I。Rotated about the X axis。

 and then translated using。Now， this constant translation vector。

What I will get is that it is rotated and then translated。So the rotation is for 45。Prerees。

 and the translation is using T。Now， question， will you get the same answer if。Instead of R X plus T。

First， we translate， and then we rotate。You're saying no， somebody says yes， stand up。

And leave the room。Well， a very quick。Let's say you hate intuition， and。Visualization， you just say。

 well， this is not the same， right。You don't have to think about it， and that's perfectly fine。

But let's see。You have this pen。Right。How is the translation？Is in this case， is saying to move。

Forward in this direction，05 in this direction，075 and1。Now， the problem is when you rotate， right。

This frame is rotating。And now， you。Move in another direction。Whereas if you move。And rotate。

 you end up at a different place。You might say， well， what I meant。Keep the frame fixed， right。

But the way this transformation works， it works with the frame that is attached to the body， right。

 This model does not work。With some fixed frame that you want to keep it fixed， you can't do that。

 But the way this transformation works。It will rotate the body， and then it will move the body。

So rotating and translating is not the same as translating。And then， rotating。It took 20 years。

To fix this。And robotics。So which is the standard for up field？Which one we should do？

When we will define the S3 group。You don't need to track this。 It will rotate and translate。

 It will rotate first and translate。 So because the fine transformation is defined this way。

 A rotation， and then a translation。So in the context of invariant coalman filtering。

 we will see that。The way you define the error。It will change。

Everything in the duration of the filter。 if you don't， if， if you don't respect this structure。

You lose a very nice property that can render some problems linear in some coordinates。

Whereas if you respect the fact that rotation and translation。Basically。

 the order matters in rotation and translation。Then for a certain class of problem。

 you can still have a filter that behaves like a linear columnman filter， right。

That's basically what we will talk about in invariant kman filtering。

We need to build some more knowledge on the matrix group。 and then you will see why。

The definition of the error will lead to that property。So this is very important。



![](img/17ec0d263d44e09d2f826072475ed2bc_1.png)

So this is a good way to end this part。Now， if you meet somebody。

 you want to tell the person how you make money。

![](img/17ec0d263d44e09d2f826072475ed2bc_3.png)

This is how you want to tell your story。

![](img/17ec0d263d44e09d2f826072475ed2bc_5.png)

Not the ad again。Ads are not supported by me。 I am not making money out of these ads。

It's a good way to show others how you make a living。So what's what's going on here。

 There is a legged robot， Cassie。There are a bunch of sensors。 you see what the robot is seeing。

 the image that you see。It's a video recorded on the robot。

It's shaking a lot because the robot is walking。And there's a Liar。

 What you see is the Lidar point cloud accumulated for about maybe 10 seconds。Now。

 the lidar is a spinning。10 times in one second， the lidar is a spinning。

And the robot is also moving。So to see a consistent map of this building， a staircase， for example。

 that you're looking at。We need to know how the robot is moving in the space。

 So we not only compensate this。10 times per second packet that we get into one point cloud。

 But also， we bring all the point clouds into a common frame。Otherwise， the first one。

 you see the table is here， you move。 And then the next one， the table is moving as well because。

YouYou always observe the world in your sensor frame。Whereas the map needs a common frame。

So that when we do trajectory estimation， we can。Compensate that motion and then reconstruct the environment。



![](img/17ec0d263d44e09d2f826072475ed2bc_7.png)

And the way it works， it's basically a rigid body transformation。 right。

 We track the rotation and translation of the robot。And we get this map。So。You can do a lot of。

Interesting things with rigid bodies。

![](img/17ec0d263d44e09d2f826072475ed2bc_9.png)

Yeah， what's the LiDA color match？Let's see。It's intensity probably because so the question is。

 what is the color map now， you can choose the color map when you visualize usually。Sometimes。

 we use height。But you can see now， the ground is red。But the ground is also green， right。

 So it's not high。 So I think it's the intensity。 the lidar。On top of a range。

That is with respect to other sensors like the theoryic camera is very accurate。

Maybe 5 cm or 10 centimetersm。Noise， you get。On top of the range。

 it will return a metric intensity between 0 and 1， usually。

That is a measure of the reflectivity of the material。If the material is shiny。

The intensity value will be higher。If it's dark， it's most likely willll absorb。The light。

 the infrar red basically beam that the light are shooting。Then you get less。Intensity。

And this is usually negatively correlated with what。

 with the intensity that you get from camera image。 So the camera is a passive sensor。😊。

It's not shooting any beam to observe the scene。A lighter is active。It shoots a beam。

Here's the time of flight， right。For the light。To measure。

 how long does it take for the beam to go and come back。

And then you can count the speed of light is constant。And then you calculate the range。

You're not sure the speed of life。It's constant。It's constant here on earth。

There also something further。Where someone was walking。Good point。ItSeemed like it was tracking。やてます。

YeahYeah， good point。 I wanted to talk about this part。 but I forgot。 So part of the video。

 you see somebody。Walks， right in front of the robot。Because we just observe a snapshot of the world。

 the scene， and then accumulate them。

![](img/17ec0d263d44e09d2f826072475ed2bc_11.png)

We get。Accumulated traces of dynamic objects in the map。If this is a highly dynamic scene。

The map will be clouded with these。Basically， traces。But the problem is。

If the map is aesthetic static， you think that's an obstacle， whereas it's not。

 because the object is moved。It will limit the capability of the robot to plan and operate in that environment significantly if the environment is highly dynamic。

So that is a challenge and is a problem if your mapping algorithm is assuming the world is aesthetic。

And that motivates the problem of dynamic mapping。 Build a map that can handle dynamic situation。

 which is one of good research topics that a lot of people work on it。 Well that because of this。

First thing that。喂那 is。I mean last。Other that are actually seeking to build a 2D map。下下。

a lot of thatccup occupants a agreed map，😊，We did the update UG area to filter out。

And is there like a version of。And it's like we3 structure like this。There is。

 and I will show that in the mapping lecture。Coming up in the future。

So the question was that some people。They improve， right， It's not something that people didn't know。

 Obviously， they run the map on the robot。 Maybe they tune some parameters to be a little robust to it by。

You know， if you reob by， by reobserving the same area。To be more tolerant to that situation。

 the question was， is there any algorithm for 3D。And there are some。And。We work on one algorithm。

 and we are building more。And I've seen a couple of more publications came out in the past few years of doing that。

So I'll try to give an overview of those algorithms。And a mapping lecture。But remember this。

 this is the motivation。 You you see these traces of dynamic objects。

 If you assume the world is aesthetic static。Okay， so let's switch to。



![](img/17ec0d263d44e09d2f826072475ed2bc_13.png)

这是。Let' switch to the slides。All right。Rgiid body rigidgi body motion， rigid motion of an object。

 we just talked about it。It preserves a distance between any two points on that object。

The study of robot kinematics and dynamics。And control。Typically。

It's tightly integrated with this topic。It's so important that a lot of methods in kinematic。

 dynamics and control。Are just purely based on geometry， understanding。The behavior of objects。

 the way they move。Now， you have an idea of what is a rigid object。

 But if you want to give it a formal definition， you can think about。

As think about it as a collection of basically particles such that the distance between any two particles。

Remains fixed。You can take this as a definition， and that regardless of any external forces or how the object is moving。

We also know that the rigid motion is a continuous movement because we can continuously rotate and translate。

It can be infinitely small。Or large。Although rotation will look back， right？If you rotate 360。

You come back to the same place。But obviously， you can do many rounds。In that sense。

 we can have infinite rotation。So， we。We're going to think about two reference frames。 One is called。

The inertial frame， the inertial frame is a frame that。It's fixed。Or you can call it。Sppatial frame。

 this is fixed。And then you have a body frame， the body frame is attached to the object。

It is moving with the object。This is moving。Now， if a frame is called a and it's fixed。

 if a frame is moving， it's called B。If we attach。Coordinate framed to。These points， A and B。

In the same way， we drive the rotation matrixes。 If you construct this direction cosine matrix。

This will give you the rotation。Mait tricks。That relates frame B， moving frame to frame A。

 in a sense。It describes the movement， the rotational movement of frame B， relative to frame A。

Because it changes based on the angle as it moves。It described basically， the motion， continuously。

This is called a rotational motion in R3。Now， as a summary again， the familiar rotation matrices are。

Rotation about x， Y， and Z axis。Typically， you can combine them using some convention。

 These are called oiluler angles。You have。How many，24。A lot of combinations of that。

Because you can have。Z， Y， X， you can have X， Y， Z。 You can have Z， Y， Z。X， Y， X。I'm not a fan。

 and I don't use it， but。This is very。Come on to choose one of them and then work with them。 Now， Z。

 Y X is very standard to use。And the way it works。Is that you multiply R， Z， R， Y， and R x。

And I'll give you a new rotation matrix that describes all three rotations at the same time。

So you have。Rotation about Z。 We call it ya。 You have rotation about the。Y axis， we call it pitch。

 and you have a role。So three independent rotation， and you can combine them to get a bigger matrix。

And you can imagine how nasty will become after multiplying these three matrices。

 lots of sine and cosine。Now you do that， and at a particular angle， beta equals pi over 2。

You get a gimb of luck。What happens is that。Your ya and roll corresponds to the same rotation。

 It's a singularity， because。It doesn't matter as long as whichever you change， right。

 it changes the matrix。In the same way。And that's the problem。And you can't fix it。

NowYou can change the coordinates， but then you just move the singularity to a different point。

But it's always there， right？ So there's no way you can fix this with。Coordinate。

This is a topological problem of this space。The Gimbmb lock， is this a real problem， Yes， it is。

Go to Wikipedia。 You can read about it。In Apollo 11 mission， it happened， the moon landing mission。

You can read the history。They had redundancy to。Basically。Control this。

 But they decided not to add the fourth。Gamll。To。Basically， reduce some weight。

 That's the history you can read。 But it happened instead of。Giving the warning at 85 degrees。

 it gave warning at。70 degrees， it locked the system that had to do something manually。

 as we read here。So it happened in the real world。There' are some gimbal jokes。

 you can read about it。And laughing you' private。Setting。But I'm going to tell you。

 I'm going to tell you， what's the topological problem。Now， the problem in a simple word is that。

You have an axis of rotation， right？You you have an angle of rotation。Whatever axis you choose， E。

If you rotate。For 1 A D， right， pi。Then it doesn't matter if the axis is。

 let's say e or negative of E。Because if you rotate。1，80， I can show it in my hand。

 It's the same thing as you change the axis and do 180 from the other direction。

 Both of them correspond to the same rotation。So the fact that their representation is not unique。

It causes this problem。So there is a particular orientation that is not unique。

When you choose a coordinates like Oer angles， it shows up in terms of that singularity。

 at particular angle， then。You lose the degree of freedom。You cannot control the system， right。

 because your role。And you are doing the same thing。 You're not able to control the system。

 That can be very dangerous， if you。Are dealing with safety， critical systems。So mathematically。

 this is the reason。We're not going to fix it。 It's just， that's how it is。The space of。3D rotations。

 This is how it is。 Now， however， you cant， you can use unit quaernions for every。Rotation matrix。

There is a plus minus unit quaernion。So the Quaernians don't have this problem。

By the still you have plus minus。So you have two for each rotation。

As we will see in the context of Le Albra， the Le Al algebra of Quatans is the same as rotation matrices。

 So they are very similar in that sense。 But if we work with quaanes， they don't have this。

Singularity problem。 That's why they。Are used in most of the state of the art， state estimator。

 especially in aerospace industry。So you get Cortanan column and filter。Usually when you buy an IMU。

 it comes with an orientation estimator that runs a quotian kman filter。InQutan's art generalization。

 I told you about this complex number。Quernians are， basically。

Generalization of 2D complex numbers to。A four dimensional space。Just like this had to be unit。

 right， This had this。Needs to be a unit cartoonion。 Otherwise， it's not a rotation。Okay。Obviously。

 will the scale。It is a little scary how this IJK corresponds to 3D rotation。But that's how it is。

So we're going to work with。3D matrices。 I think they are more approachable。But。

You're welcome to use Quatanions， too。So the property of rotation matrix is。That， because。It's。

Constructed using the basically projection onto。The fixed frame。Its a direction cosine matrix。

 and both coordinate frames are basically orthoormal。 The axes are autoagonal。

And each axis is also normalized。So property of orthoagonal matrix is that。It is。

Its inverse is its transpose。So because of that。Best is from linearni algebra。That。

Theverse of R will be its transpose， because it's an autoagonal matrix。AndYou can verify that。

 whatever rotation you pick， make。It's transpoposed， multiply them。

 You will get their identity matrix。Now， we also know that the inverse of a matrix。

Commutees with the matrix itself， always。And it is unique。Now， take the determinant from both sides。

Which is the determinant of。The product， right。The determinant of the transpose。

Other matrix is the same as the determinant of the matrix itself。

And the determinant of the identity matrix is one。So we learned at the demin square。Of R equals one。

 therefore。The determinant of the rotation， the matrix that is formed this way can be plus  -1。Now。

 out of these two choices， that next lecture， we'll talk about it more。Plus，1 is rotation。

in-1 is a reflection。嗯。Because now， if this。Determinant is the volume that your matrix spans， right。

 It's the volume。Of the vector space。Is the volume of the subspace is span by the columns of your matrix。

That's the determinant。If it's not one， youre scaling。Obviously， we don't want that。Now。

 if the determinant is negative1， you're mirroring that volume。That corresponds to the reflection。

More on this。Next time。So you can give， give them a name。 Sounds like its a very important。

They have some important constraints。 Let's give them a name。The name we use is called S03。

We'll see why later。 But they call， they are called special orthogonal group of dimension 3。

 because these are3 by 3 matrices， therefore。R 3。These are all。Inverible。

 this general linear means they're invertible。These are invertible matrices， such that。

Their inverse are the transports， right， and the determinant is one。

So every configuration of a rigid body that is freely rotating。

Can be identified using a unique rotation matrix。Okay。Now， to avoid a confusion。

 this rotation matrix span is3 by 3。There's no singularity here。

It is when you choose the coordinates to model all of them， right？Because you can think about。

For every configuration， there is a matrix。That has nine numbers， right？That is perfectly fine。

Is there any。存在点。So， matrix is inverable if its determinant is not zero。We say a matrix is。

 we say a inverse exists。If。And only if。Its determinant is not 0。

All the columns are linearly independent。Because the inverse formula has one over the ten， right。

I'll talk about the general linear group next time as well。

 but it means all the square matrices that are invertible。Of a particular size。

So we want to work with nice objects，Singularities。这个。Yes， you're right， this should be three。Now。

 how do you combine these matrices？Well， it turns out to get the rotation of frame C relative to B。

We know how to construct that， right？Using the direction crsine matrix。Or the method。

 we learned how to derive it。You can have another matrix that is the orientation of frame B relative to A to combine them。

You can multiply them。So the common frame that is in the middle basically goes away。

 Then you get the rotation of frame C relative to frame A。Now， you might ask。Why don't you add them。

 right？Maybe there is。Something in your mind that wants you to add them。

 But the problem is when you add them， the result might not。Be a valid rotation matrix。That group。

That we will formalize the idea of group next time。This group is not closed under addition。

 If you add to rotation matrices， then the result might not be part of this group。 Therefore。

 it won't be a valid rotation matrix。 But as long as you multiply them。

You're always inside this group。 It is closed under matrix multiplication。

So that's the reason we don't add rotation matrices。Because the result can be a wrong matrix。You can。

 of course， prove this， right， derive。B relative to C derives A B relative， C relative to B。

 derive B relative to A， multiply them， but also derive directly C relative to A。

 If you get the same answer， then that's the proof。 You need to multiply them。

Rotation about the same axis commute just like the rotation in plane。Right， the2D rotation。

 If it's about the same axis， the order。Basically， it's not important can。Change the order。

 in general， That's not true because the matrix multiplication is noncommutative。

That means two matrices commute if a times b equals b times a， right， but we know that in general。

 this is just not true for matrices， so you can't do that。

So don't change the order in general unless you are confident that this is about the same axis。

 And it's a very。Particular situation that you're doing calculation。 also， don't add them。Okay， we。

Now talk about a generalization of that to rigid body motion， meaning we want to rotate。

But we also want to translate。So the complete rigid motion is described by rotation and a translation。

We call we're calling it G here。So this object， this frame， they are no longer co located， right。

It rotates and moves away from。The fixed frame。This was our fixed frame， our inertial frame。

 this was the body frame。Which is that that's how it is， right。

 maybe the robot that starts from here。This is your。0，0，0 for the map， right， the origin。

And then as the sensor is moving on the robot， that's the body frame is moving。And。

Localization problem is basically finding these transformations as the robot is moving。

That's the localization problem。Now， just like rotation groups， we have another group。

 this group is called a special Euclan group。It consists of a translation。

 which is a 3D translation vector。And a rotation matrix。And when it acts on。Or three， you get。

Rotation times your point plus a translation。So it first rotates the vector。

 and then it adds the translation。Now， were a little lazy to remember this like this and track it so we're going to invent something new。

So let's create a new set of coordinates called it homogeneous representation。

 instead of for every vector。This is not a cartoonion。 just I used Q before。 This is just a point。

 right。For every point， instead of R 3， let's make it four dimensional and add add。1 to the end。

 right。So for every point in 3D space at one。Well make it a four vector。Now， if you take a delta of。

 let's say Q 2 minus Q1。This will give you a vector， right。

 displacement vector that the bottom part will be 0。 And that's okay， right。Because it's a vector。

 but this is a point。So for points， we have this one。 If you take the delta。

 then it we get 0 in the in the bottom。This is the homogeneous coordinate。Now。

 the rules are that sums and differences of vectors or vectors because you have zeros in the bottom。

The sum of a vector and a point is a point because the vector is just translating the point。

That's okay。You get one plus zero。Right a vector is a carrier。 It moves one point to another point。

That's what it's supposed to do。The difference between two points take the delta。 That's a vector。

 It shows the displacement from。One point to another。You cannot add two points。

 It doesn't have any meaning because then you get one plus one in the bottom row。

 And that's just not defined， right， So to move a vector， to move a point， you need a vector， not。

 not another point。The point is， just。A fixed object。So that， these are the rules， not。

Very difficult to use in practice。Now， the advantage of this definition is that now we can average this applying transformation into a matrix that is now 4 by4。

 this bottom row 0，0，0， and 1。So r is 3 by 3 right， and p is 3 by 1。Now， when we multiply this by。

A point。That queue we had， right。You will get R。Q plus P。And one。

So you don't need to remember when when we use the matrix form。

 it will follow directly from the way we arrange them。That's one advantage of using these matrices。

So that's why we make the homogeneous coordinates。 It's very convenient。

When you multiply what happens， you multiply two rigid body transformations。You get。

A sequence of rotations， right。We first rotate the second vector， right， second point。

To align it with the first frame。 and then we add the translation of the first frame。Now。

 this is all happening automatically。 It's all automated。You have these numerical matrices。

 you multiply them in a computer。 It tracks it everything for you。

You do not need to track them manually。But the meaning behind it is that。 So it。

 it handles this orientation and translation order automatically for you。And just a reminder that。

It two times。 H1 is not。The same as H1 times H。 you can multiply and you see that you will get different results。

How do you Now， the inverse of the rotation was the transpose。 What about this one。

Because I have good intuition and I make a guess， and I'm going to tell you， this is the inverse。

How do you prove it， We'll multiply them if you get the identity， That's the answer。

Because the inverse is unique， right， If it exists， it is unique。Basically， multiply。

These two matrices， if we get identity， or that is the correct answer。

You can try this if you're feeling lucky in exam。Yeah。Guess an answer。But try it at your own expense。

You will not get extra grade， because you guessed。So one thing we want to do that you typically don't see it in a course on kinematics or dynamics and robotics。

Did you cover some of the。Topics we talked about。But in the context of mobile robotics。

 we want to also model probabilities and uncertainty using。Rid body motion。

And that's an important topic for us， because later we want to do a state estimation over。

A rigidd body。Rotation and translation。So basically。

 that dominates this rigid body motion dominates the topic of point registration， localization， s。

 because our movements are always。A rigid body motion。Okay。Now， one thing we will learn is that。

These matrix groups， like rotation and rigid body transformation。

They come with a built in coordinate system。 And that's very nice。

 They give you an intrinsic coordinate system， attached to the body frame。😊。

It is called exponential coordinates。 It is similar to that angle that was in the exponential of the oiluler formula。

 but it is generalized to higher dimensions。Now， for a lot of problem that involves。

Protation and translation， you get a distribution that when you do Monte Carlo propagation。

 you get a distribution that looks like a banana。 It is nonlinear。

Similar to that polar coordinates example， right。Now we understand that when you model them in the exponential coordinates。

 they are linear and Gaussian。So that covers。A fair portion of problems that we thought they are nonlinear。

They are。Basically， linear exponential。So in the exponential coordinate， are， they are linear。

 not that directly。 They are linear， right。So that means using an exponential map， you can go。To。

That the space that we were adding the angles， right。

 The all the work you want in that nice vector space that looks like usual。😊。

You clean in a space that we work on。I think you can come back to the。Now， linear space。

 where this rotation and transformations are。 And that's what you get， because you can model。

 for example， this flat Gaussian in the。Exponential coordinate。 And then。

You can map it back to the nonlinear map， the nonlinear covariance。Okay。

A covariance matrix can't be bent like this because matrix is linear。ItThis through this。

Exponentiation that we can go back and forth。Between this linearity。And。A linear， exponential model。

And that's Le algebra。 So you have example codes here， but this is just to motivate。

There's much more into these groups。So next time we talk about。Lgue groups。As I said。

 they are the best tools we have to study。These objects and symmetries of continuous symmetries of the spaces。

 And they come with the coordinates that we will use for。Solving a lot of problems in this course。

You can take a look at codes to generate these plots。For curve covariance propagation。

Some of the topics that I covered。You can read them in chapter 6。This is also a very nice book。

That uses legal group for。Kinematics and dynamics。

![](img/17ec0d263d44e09d2f826072475ed2bc_15.png)

So that's it for today。