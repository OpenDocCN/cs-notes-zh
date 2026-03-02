# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p06 -06-Lecture 06-Matrix Lie Groups for Robotics I.zh_en -BV1UfAmeUE3e_p6-

In this lecture。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_1.png)

We will talk about matrix Lee groups。 Lee is the name of the mathematician surface Lee。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_3.png)

We studied them。So it's not lie。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_5.png)

And。Let's see why do we need to talk about this。 This is probably a topic that。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_7.png)

It it's first time you're coming across it in this general way。A mind to ask， well。

 can be just skip everything and do。Use simple tools。Surehow you can。You might。Be O for now。

 But your knowledge will be something like 20 years behind。In the current mainstream literature。

2 to 30 years behind。Give it 10 more years， and you will be completely irrelevant。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_9.png)

To the community。So you don't want that。Now， you don't want to be。The mathematician here。

 But you want to know the concepts， why we need them。

And why in certain applications are they are preferred tools to you to be used， okay。

Some motivations that are more practical， hard to learn features that are invariant to image rotations。

 All of us conceptually can relate to this idea that。If we want to classify this cat photos as cat。

We will not be probably misled by the orientation of the image， right？

It doesn't matter if it's upside down， still。Recognize this is a cat photo。Now， what is it that？



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_11.png)

Makes it so easy for us to。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_13.png)

Be agnostic to the rotation， to the rotation of this image。

W it's so difficult for a computer that people need to do This particular example is related to deep learning and machine learning。

 They need to do data augmentation。 Consider all different orientations of the image to expand your data set。

 and of course， you can't consider all of them because they're infinite。Possible orientation。

 just like the circle， right。So you cannot generate infinite。Examples。

By just creating different variations of the same data， that sounds very naive and inefficient。

 and it is。So the modern way to look at this problem is through the lens of symmetry。

And it boils down to the fact that you want your features to be。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_15.png)

Ecovariant for regression， meaning to have the same orientation as the input or invariant。

 meaning to be independent of the orientation of the image。 if you can accomplish that。

Then you have a classifier for yourself that is agnostic to the orientation of the this cat cat image。

 right。So it is a very powerful idea， and it boils down to exploiting the symmetry。😊，Okay。Now。

 you can think about it in 3D。For point cloud。We like that， as well。If we want do place recognition。

 we probably want to have features。That are not widely changing based on what view we we are looking at。

 let's say， shopping mall， right。We want to recognize the place。

 no matter what view we're looking at。So it might seem to be related to the computer vision or machine learning。

 but ultimately we need it for robot vision and perception as well。So they。

 and it is nice that all of them they get tied together within this concept of exploitding symmetry。

😊，Now， for something like this that is continuous symmetry， you can rotate the image continuously。

As as small as you want， right， around the circle。We need a mathematical framework that describes that efficiently as well。

 And that's the topic of legal groups。 Li groups， again。

 are the best tools we have for studying continuous symmetries of。Different spaces here。

 it's a 2D space in 3D， it's a 3D space。Another example。That。

We will deal with it in robot estate estimation， in this courses。

How to model a rigid motion of an object or articulated robot。

We covered this a little in rigid body lecture。So league groups。

 matrix league groups in particular are the bigger umbrella of that rigid body。Basically。

Lecture that we cover。 this is a superet of that topic。

But we are particularly interested in rotation and。Translation， rigid body motion。

What about 3D reconstruction using a monocular camera。Computer vision and graphics。

 you have a monocular camera。What's the problem with a monocular camera？No death， right？

You have a camera and then no depth。 You can take as many images as you want。You will never。

Observe the depth。So what's the consequence of that for something like structure from motion。

Which is a related topic to s。 You want to。Reconstruct the scene using a series of images。Well if。

 if you don't have the depth， you won't have the scale。Now， is the scale a constant。

 I that the case that you can just。Model the whole scene and then multiplied by some number。

That would be still nice in terms of that's not the case。

 The scale is a parameter that will vary for every time you're solving the problem to reconstruct the scene。

 So there is a bigger league group than rigid body。

 which has one additional dimension that has the scaling。

 That's called similarity transformations in computer vision that is used for monocular vision。

 That's also a league group。So it does not preserve a distance between two points。

 because the ambiguity in the depth， it will rescale the scene each time。Eventually。

 you won't have the actual scale， but at least relative to each other。

 if the scene is reconstructed correctly。 That's important。What about IM U， every phone we buy。

 every laptop， every。Maybe not laptop yet。 Every tablet， every robot comes with an IMU。And Im U mean。

 refers to。In airfield measurement unit is a sensor。That combines。A gyroscope， an electronerometer。

Usually， also it comes with a magnetometer。But a minimal setup is having a gyroscope and an aelerometer。

How do you model an IU？How do you integrate it。Which you might be surprised， but it。

The question that for。30 plus years， people basically starting boil down to how do you integrate。

How do you model and integrate IMU sensor correctly。If you can only do that。

 you solve the dead reckoning problem。 And that's what you will see in theveni lecture。

So it is just basically correct way of integrating。And by correct。

 we mean understanding the space that these natural quantities that we measure like angular velocity and linear velocity and accelerationation are basically living there and then modeling them as。

Similar as we can to the way they behave in nature。Okay，It won't be perfect。

 but we can capture the underlying principle in an ideal or deterministic setup， at least。

That that's a pre requisite。For having a model that performs better。

 we still have to deal with uncertainty。So， all of these。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_17.png)

We'll make。Study， the study of league groups， a very compelling area。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_19.png)

Now that the topic itself is vast its。Basically a area of research in mathematics and physics as well。

We want to cover the part of it that we care about。So we， we talk about matrix groups， league groups。

 First， let's review what is a group。We mean group as a technical term， in a mathematical sense。

So when we say group， we're referring to a group of objects as said。That satisfies certain。

Properties。One of them is closure。A group。Consists of some elements， let's say， G and H。

 whatever they are。And a binary operation， let's use do。 You can use。Any。

I don't know any symbol that you like， right， It doesn't matter。 If you're a computer programmer。

 you're used to this idea。 I have an operator。 I'll just define it。

You can define the product to be your plus， right in a computer。That's not a problem。

 So you have an operator that it's binary because it takes two group elements and it will do something。

Now， whatever you do， the results must belong to the group again。

You cannot go outside using that operation。 That's the cosure property。

You might guess why we don't add rotation matrix now because it's a group， you want to stay there。

 If you add them， you'll end up outside of the group so we must multiply them。

So you can confirm this more abstract like algebra construct。 Then you have to follow these rules。

It might not help your imagination to visualize， but。

Abstract algebraa structure will give us a set of rules that we can just follow。

 and things will work out。The second one is associivity。 That means。The order。Is。Not important。

 And in the sense that。Not shifting them to left and right necessarily。 But if you multiply G。By H。

 and then by L is the same thing as first calculating H times L and then。From the same direction。

 which is right here。For h times L。Multiplying them by G from the right side。

Every group comes with an identity element， an identity element。

Is an element of the group such that you can multiply from。It sighed， and it will not change。

The result， it will reproduces， it will reproduce the same element。The last one they investverse。

 every group must have an inverse。And the definition of the inverse is that whether you multiply it from left or right。

 it will give you the identity element。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_21.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_22.png)

Now， you are familiar with these constructs。 Let's verify these two groups。

 a group of real numbers with。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_24.png)

The operation to be the addition。Confused about your definition。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_26.png)

In linear algebra， for example， we say that I。Eleement where。Uultly it by another element。

 you get that second element map， whereas this equality looks like commutivity。Yeah。

 it's the same thing。 You get E times G。 Maybe I should have。You get your element back， right？

It's a mapping from each element to itself。 You won't change this solution。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_28.png)

I is it。Equaling Z， a requirement for it big。😊。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_30.png)

I' filling the identity appropriate。Yes。Or it just something element。咁你佢哋。As far as we are concerned。

 yes， I actually can't think of an example if that's the case。 But。

 but what we mean is that it must reproduce the same result。

 especially we talk about matrix legals ends up being identity matrix。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_32.png)

Time some。Mattriix a。Right。It must give you the same element。The different。对，没有。比要准。

What's the difference between a group and field， That's a very good question。

 we don't wish to talk about it here。But feel a little more。Sophisticated， you can have。

Scalar multiplication。Additionally， right vector spaces are fields。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_34.png)

Now， I know you're curious， we don't want to go that way。That's like off road。So the best way is to。

Learn what we need for what to do and then grow it from there if you're interested， right。Well。

 let's quickly verify。If a。And， B。Are real numbers， right。

We already know that a plus B is also a real number。

We know A times B is also a real number just to verify both groups。So， there is a closure。

Like two plus three。Two times three。We also know that A plus B plus C。

It's the same thing as A plus B plus C。Same holds for。The other group。

The identity element of real numbers with the addition is。0。

 so a plus 0 is the same thing as 0 plus a， right。Wch is， of course， a。

For the multiplicative group is1 times a equals a times 1。Now， the example might seem trivial。

 but it is really the same concept we can apply to matrices。instead of one。

 we're working with arrays， it's an identity matrix， right。This association hopefully will help you。

 too。You know， remove some of the uncertainties that might you might face when you see。

Matrix version of some of the identities。What about the inverse element for。The additive group。

 we have。The negative sign， right？Which will give you， of course， the identity element。

For the multiplicative group， we have。The reciprocal of the element。

 which will give you the high identity element， right。Now， back to your question and field。

 you combine both of these， you will get up。Fd， you can do both of them， right。

But these concepts are abstract and it can generalize it to many different types of operations and objects。

We care about real numbers， matrices。And that will give us already a lot to work with。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_36.png)

So when we say group， we are going to assume we have these properties and we are not going to violate them。

 right？

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_38.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_39.png)

That's important。Now we can talk about a matrix group。So when I say matrix group now。

You can think about。These properties， so the matrix will have those four properties。 on top of that。

 it's a groupru that its elements are matrices。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_41.png)

They're not real numbers。In addition to。Having matrices in a group。

We also mean these mates are invertible。 So when we say matrix group。

 these are mates that are invertible。Okay。Now， the inverse of a matrix is only defined for a square matrix。

 So by definition definition， it ends up being a group of matrices that are， let's say， for R N。

 right。And dimensional。Group is going to be an n by n matrix that is invertable。

 itss determinant is not 0。But in general， all the matrices you can imagine。We could work with our。

 let's say， M by N。 These are rectangular matrices， right。We're not going to work with all of them。

 we just work with the square ones that are invertible。That's our setup。 This group has a name。

It's called general Line groups。 This is the biggest group you can get for matrix groups。

This is the biggest one。All square matrices that are inverable。

So M is a set of matrices that are real number。 For example，1，2，3，4。Belongs to。M2 here。

 This is a two by two matrix。 This real means that。Each of the entries belong to。

The field of real numbers。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_43.png)

Could we drop this？ Yes， we could wipe do people write it。Because we could have matrices over。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_45.png)

Complex numbers， too， each entry of the matrix could be a complex number。

 We won't work with complex numbers here。Well， those are very important as well in。

We can't use it in robotics too， but I think it's easier to work with real numbers。In physics。

 that's very common In quantum mechanics and physics。Fortagonal groups， it's over complex numbers。

 They use complex numbers。You could make it even more complicated。Its entry could come from。

The field of quaernions， each of these numbers could be a quartertion itself。 That's also possible。

We keep everything as nice as possible。 real numbers。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_47.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_48.png)

So let's add more structure。 So last time we start from a bottom up approach that we talked about coordinates。

 We talked about deriving2D rotation，3D rotation， and then looking into the properties of them because it was a direct direct cosine matrix。

We said these are orthogonal。 The determinant is one。 It shouldn't change the volume and all of that。

 Now， this is the top down。Approach。We talked about the biggest possible matrix group we could have。

Let's add more。Structure and then make it more special。So the first one is the group of。

I find transformations。You already know， and a fine transformation takes a vector。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_50.png)

Applies the linear map。Plus， a translation。And the trick we learned last time is that if we form our matrices into this form。

The linear part， the translation。Add a row of zeros， as many as you need。

Depending on the number of columns of a。And then add a single one for your translation。

This is called a group of and dimensional a fine。Transformations。Now， for every vector in our N。

 if we append the vector with one。We can get the action of the fine group。Con R N。

 So this is technically when a matrix is multiplied by vector。 That's the action of that group。

On that vector space。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_52.png)

This is the group。This is the vector space。Which is our usual Euclidean space。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_54.png)

This is the action。Okay。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_56.png)

We use left action matrixes multiplied from left to the vector。 You could talk about right action。

 too。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_58.png)

Why would we wanted to finance？Second。Theres one incentive here。Why the question is， why do we want？

To。Construct this matrix such that we have 0 and1 here。

Or like mean because you can rewrite your matrix。Re writeite it since that you。まテ。

So what is the alternative idea？But if you just had。还有。Tell me I'll write it。

 Like we're open to alternative ideas。 as long as it works， it's okay。

 if you just had the first you have A。A。And then you are give me most plan to buy that。

Still multi playing by x1。This is。Let me write it like this。So the question is。We can write this。

 A and T。This is n by n， n by one。And。By n plus one， right。嗯。So did multiplication make sense？Right？

Can I inver this？Well， you violated the condition that。We had a group of matrices。

 We needed inverse element。Yeah， see。You got disqualified already。 So you cannot break those rules。

 That's why you set some ground rules。 And if you can't break them。 you have to follow them。Now。

 calculation wise， this is not。Wrong。Maybe in your code， you're doing this。Because， you know。

 we we will get the same answer， right。And that's not a problem， but。Stucurally。

 you can prescribe this as。The general value of dealing with this group， right？

So we cannot talk about inverse rectangangleular matrix。And that will be a problem。

So those zero and ones， we're just filling the gaps。It makes sense。That satisfies those conditions。

 right。Either way， you get the same results when you multiply them。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_60.png)

So the fine group is very general， right， include。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_62.png)

Scaling， rotation。Translation。Sar any sort of distortions you might have with that shear。

You could think about。Translation as a matrix group， too， This is so general that covers also。

If you talk about our N。In addition， right， we could talk about the vector space of our N。

 Euclidean space。And。Former group。Using addition。We could use a matrix group， in particular。

 a fine group and just set the linear transformation as the identity always。😊，All you're doing。

 you're just translating。 So it is covering that case as well。So it generalizes that to a much。

Bigger class of transformations， okay。So this is the group of translations。And in particular。

 it's very nice in robot kinematics because we can always multiply matrices。

 whether we're translating or rotating。 And that makes it very convenient， for example。

 to model forward kinematics or inverse kinematics。😊。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_64.png)

All right， so we have the fine transformation。Let's go back to the general linear group。

 construct another group。Suppose。Reform is set。Which ends up being a group that。

All the matrices are part of the general linear group。 that means they are square and inverable。

But also， they satisfy this constraint。This was the constraint for a rotation matrix， right。

 an autogonal matrix。An autogonal matrix， its inverse， is its transpose。

Because when you multiply two mates， you're really taking the dot product of each row with the columns of the second matrix。

 and when these dot products will give you。0，1。If they're corresponding。

 let's say row and column and 0， that means that。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_66.png)

Columns。Basically， a rows are perpendical at each other， oragonal。On top of that， when you get one。

 that means they're normalized， so it's auto normalmal。So this condition。

Will give us the autogonal group。These are rotations and reflections。Because the only way you can。

Apploy a linear transformation to an object。Without scaling it or distorting the object and preserving the distance between two points。

What are they there you can rotate it， you can reflect it。Through an axis， you get。Do you have。

Other ideas how you can do that？Let us know if you come up with。Anything。我的。三当。Yes。

 because a transport is the inverse of the matrix。 This is a property of。Otgonal groups。

We're talkinggon all matrices that。If you might have seen it in linear algebra Q R factorization。

 for example， or graam schmid process。You can get a set of linearly independent vectors。Creating。

Orren't a normal matrix。Okay。Then you get this property， this is more e special， it's a square。

So it works， works both ways。 You can talk about A， A transpose， A transpose a。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_68.png)

Either way， you get identity matrix of size N， whereas if Q is in in Q R。

 if it's a rectangular matrix， you write it from。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_70.png)

One particular direction that makes sense。So this is the samegonal matrix that you might have seen in linear algebra。

 So I'm going to drop the matrix multiplication as the group operation。 So you can just write。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_72.png)

Your mates next to each other。 It is understood that this is a matrix multiplication。

I have a question for the closure。Only位的。劳就会培训和规审。Yes， you cannot add a plus B。 if you have A and B。

 both of them are part of this orthogonagonal group。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_74.png)

B。Or a fine matrix。确。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_76.png)

雷声。Okay， your question is in the， we have the addition。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_78.png)

My answer is， we do not。We did a trick so that when you multiply matrices。

 we can do addition translation。You still need to multiply。These mates， right。

 because let's say this matrix B， right？You're just multiplying B by this vector y。

There is no addition。Of course， inside the matrix multiplication you have。Addition。

 but that's just the rule for matrix multiplication。That's our group operation。

 Were allowed it to do that。So that。Maybe unusual path is that when we start from algebra construct。

 the rules are very rigid。 You cannot break them。 whereas the bottom up was more intuitive。

Then you start asking these questions， can I add them what will happen， right？

Then you have to show case by case that， well， is it allowed it to do that or is's not。

Whereas this weight that is top down。The rules are very rigid。 You cannot just break them。

I know it might not be satisfying， but。It works well。嗯。Calculation wise。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_80.png)

But we're trying to cover both sides as much as we can。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_82.png)

All right， one observation here is that the autoagonal group。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_84.png)

Is。Giving us A， A transpose equals the identity matrix。 Take the determinant of。

The both sides of this inequ is equality， this equality and。What we get。

 we get the ten minus a squared equals1。Okay。Transpose is a matrix if it does not change its transpose。

It's a determinant。So we have two options。 Take this square root。 You can either have plus 1 or -1。

So， we end up with two。Set of matrices， those。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_86.png)

Who have。To set up orthoagonal matrices。 These are all orthogonal matrices。

 But there's a group of them。 They have theyre determinant to be plus  one。 There's another group。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_88.png)

The determinant is negative one。Now， they cannot be combined because these are。Separate groups。

 they have nothing in intersection。So we learned that this autoagonal group is a thisjo union union of。

These transformations。Now we know physically that these are rotations and these are reflections。

Using that。Somewhat advanced justification that the determinant is the volume。

Of the subspace is spanned by the columns of our transformation。

 and the negative signs will mirror the volume。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_90.png)

That is interesting。 The group is not。Connected。Theill is a group。But it has。Two basically， subsets。

呃。Anddepend of each other。So that intersection is。The empty set。

 and this is precisely what constitute you reflections and rotation matrices。

 These are two set of transformations。Of particular interest is。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_92.png)

A special autotgonal group。 whenever you see a special， usually when we say the determinant is。

Plus one， right。 So in this language of matrix group， when you see S。That means。

We're talking about matrices that have transformation of one。

We're not talking about it as another group， a special linear group。These are also。

Matririces that they have detertaminant one。Takeect the general linear group， right。

 separate the ones that they have themin of one。 you get a special linear group。

This group covers the spacetime transformation in physics。You can have。For dimensional space。

You have time like Victor of。This is velocity of y。 you have time。 you have X。

 This is a four dimensional space。Then using a special linear group in physics， they model。The space。

Time transformations。Meaning objects that move。Faster， closer to the speed of light， the experience。

Some sort of deformation， right？If they move is slower。

And all of that is relative in special relativity， unrelated to this topic。 But anyway。

 they use this group in physics。😊，You will be surprised that I actually。

Read some work on the visual cortex modeling。And if you replace the speed of， and what。

 what was the outcome is if you replace the speed of light with the maximum capacity that your perception system can handle。

Then you can actually model。Space time， a version of whatever we do with these transformations。

Because， for example， if a car is moving too fast， you're just not gonna be able to。Perceive that。

 It's just too fast with your eyes。For your visual cortex as。

The analog that's basically equivalent of the speed of light。Of course。

 objects don't move with the speed of light here。But when you lay out that setup。

 then you can have a spatial temporal modeling in your vision systems。 and that's very interesting。

So the temporal aspects of it is a convolution across time because it's motion blurlar in images。

 for example。The spatial version of it。Is basically whatever you move in through this space。

And both of them。Happen in images。Okay。So， that's a。Pretty cool topic in 3D computer vision。

I do not think it's covered like that， but。It would be cool to talk about it like that。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_94.png)

We are going to talk about。S。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_96.png)

Now， why do we need to talk about S， O N， Okay， we're back to rigid body motion。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_98.png)

One。Particular reason to study these groups is that。

We want to talk about the isoomeries of ancient space。Now， what is an isometry？



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_100.png)

An isometric is a bijection is a transformation that is one to one and on two。And it preserves。

Some distance。You can think about just usual Euclidean distance。You have two points。

This transformation takes these points， and transform them into。Some other points in this space。

But when you take the distance of these two transform points。It's the same distance。

We had before the transformation。 This is called an isoometry。 F is an isoometry here。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_102.png)

Now， going with the notion of the Euclidean distance for rigid bodies。

 this sounds like our definition of rigid body。 We defined it。Any more。Physical way。

My rigid body is a set of particles。 their distance。

 The distance between any two particle particles should remain， must remain。Fixed。

As I move into space。So when you hear isometry， it's talking about the same topic。 Now。

 if it's a linear isometry， we know that linear transformation fit the origin。However， you can have。

Translation as well， then it's not linear。We know very well that translation。Right。

Will not change the distance between two points。 if I translate。2 points to another。

Location in this space， the distance is the same。So translation， we saw it last time。

 It is not a linear transformation， but it is an isometry。So， rotation。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_104.png)

And translation together， they form。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_106.png)

Direct ismetricries。Reflections are called indirect isometries or proper isometries。

 improper isoomeres。 These are all the names。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_108.png)

You read in the literature。Now， what is S O N physically。I know it's hard to。Visualize these sets。

 When you talk about algebraic sets， although algebra makes calculation easier。

But for a particular case of S， O N， it's not very difficult to imagine。

 So a special orthotagonal group of dimension N is a simultaneous rotation of N perpendicular planes。

 In 3D， you have three planes。Just like here。Each plan is defined by normal。

When you rotate these three planes simultaneously。At the same time。This motion is described by。

S or three。But whatever we talked about is general for any dimension。Of course。

 were most interested in 3D。What about S04。Help me visualize it。So for S03。We。

Know that we can rotate in。3e。Independent ways。Which is。Pick every， I'm gonna call this E1， E2。A3。

 right？So take any two。Unit vectors。It will form a plane for you， right， And then you can rotate。

Using the other vector， which is normal to that plane。So we have three ways to rotate。

You can do a quick check。Because。The first。Time， I want to rotate。

 I have three options to choose from these bases。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_110.png)

The next one to compliment it， right。And form the plane。

 I have two options because one of them is chosen already。And the last time。I have。One option。

However， the order I choose。These vectors is redundant because if I choose first and second。

 it's the same as second and first。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_112.png)

So divided by two， you get three ways to rotate for S or four， you have four times。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_114.png)

Three times two times one。That's a lot of way to rotate。Is this correct？12。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_116.png)

24。Is this correct。It is not。We'll see why。喂微电话啲。I made it up， you believed me。

There are six ways to rotate in SO4。But so I was wondering， so you say。Simultaneous ver。I you I。あせ。

Are you that this is different from a traditional way of rotating？First。

 you rotate around like B1 and then you rotate around me。That's a very good question。

 So when I say simultaneous rotation， do I mean。Independently about each of one， no。

 I mean simultaneously。Think about all three planes， together。And all the different ways。

 you can rotate them。That is the fundamental difference with thinking about them as independent way of rotating about。

 let's say E1， E2， E 3。Thinking about them as decoupled rotations。Will cause a problem。

Which we will see more about it， as we。Explore more in thevari cave lecture。

So it's different from other。It is different from oil angle， right。

 So the motivating example for the invariant state estimation is that。Choose Oer angles。

 derive the aerodynamics。Linear eyes， see what you get。Then， use。This method。Drive dynamics。

 linear aerodynamic linearize。You'll get a matrix。 that is constant。So it's completely different。

 So that's。There is a fundamental difference when we do the calculations that will come be convincing enough to use them。

Conceptually， I think you pointed out a very good difference that you need to think about them simultaneously。

And when you start working with Le Al Jabras。Each of them will give you a basis。

 and we combine them before turning them into a rotation matrix。

 whereas when you use all your angles， you turn each of them independently to a rotation matrix and then combine them。

 right。That's not a good way to do it。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_118.png)

なは。Its location。It's no freeze。I don't think I understood a question， you mean？



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_120.png)

就开开会贴开会贴快。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_122.png)

でので。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_124.png)

Oh， your question is， why did we define？A special otagonal group to be。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_126.png)

This O N plus。Why not？I mean you could use this name， Then I would choose a different name。

 That's okay。Okay， so what's the meaning behind this plus that makes it important。

 because these are rotation matrices as we derived last time。

These are autotagonal matrices that act as linear transformation that will not。

Change the distance between any two points and a rigid body。When apply to your coordinate frame。And。

The appropriate dimension that they are meant to act on， right， As so  three acts on 3D vectors。

 And so N acts on n vectors。What they do， they rotate your frame altogether。X， Y， Z acts together。

 right， not separately。They will remain autogonal。And normal。Okay。

This is the property of this subset， which has the determinant of one。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_128.png)

It is only sufficient to build one example， use the one that has the determinant of negative one and see what happens。

 right。You will see immediately that it will not satisfy。This property， because it will mirror it。

And we know we don't want that， right， We already know that we don't want to meter。

 We want to continuously rotate。Our objects， that's how sensors move in this space。

I hope that's convincing。Nummerical examples can can help to see the differences。And I will give you。

Some of that maybe on Piazza notes。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_130.png)

And in homework。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_132.png)

So the name is convention， but the reason was what we talked about。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_134.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_135.png)

Talked about isoimeries。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_137.png)

So important group that。Captures the isometry of。The Euclidean space is the special。😊。

Euclideian group。Now you know that if you drop S。This is a Euclidean group that probably。

 this is just。Any transformation。So it's not rotation。 What should it be。

But we could say general linear。Or it could be other groups too， right？

So special Euclidean group A is definitely a rotation matrix。 T is just a usual translation。😊。

And our rotations are based on the right hand rule。We。Don't work with left hand convention， right。

 Your right hand thumb along the axis of the rotation。 bend your fingers。

 That's the positive direction of rotation。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_139.png)

So we are back to the group of rigid body transformation。

 So how many of you are members of this important society。

There's a lot of material and discussions online。I encourage you to read some of them。Okay。

 I see some hands。That's what people see in the recorded lecture。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_141.png)

So really in Michigan。They have members。If you see this at home， I made that up。

See people usually say in lectures。You can always say it， even if you don't see any hands。

Because you don't know what I'm seeing behind you。So this is。Now， if you're not a member。

 you should be very excited about this next topic。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_143.png)

So you can't complain。 Now we're talking about。Care of the spaces。And just a little bit， not。

Too much because then it will become a differential geometry course。It will be off topic again。

So a manifold。Is。Any card。Shape， surface， such as this circle。That we can chop it often into。Pieces。

 and we can flatten each piece， in other words， locally。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_145.png)

You can treat this as a Euclidean space。 here， a real line， right。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_147.png)

You can chop the circle， flatten it， and think about it as just。Realign， and in particular。

 for circles， we do that all the time。 we just treat angles as。Just a real number。

 Maybe we just wrap sometimes to make sure it's whipping。Minus pi and pi。So for us。

 this is the manifold， no sharp edges。 Everything is smooth and nice。No square， right？



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_149.png)

So's called it smooth man。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_151.png)

Why this is important。 Well， because all the calculus we have it's for Euclidean space。

 If you can look at a surface。It's just the surface in 3D space that you can visualize。

If you look at it locally and you describe it to be flat。For maybe a small region。

 then we can apply our calculus to that area。And then maybe we move to。From here to this area。

 And then you switch to maybe a different。Neighborhood。

So you might need to talk about different coordinates。For each region， it might not be the same。

 but they must agree on the overlapping part and smoothly varying， right。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_153.png)

So these are called coordinate charts， and all their angles are one type of。Chars。

 they don't cover the whole space。Just part of it。In particular， that singularity that pops up is。

The part that is missed， no matter what configuration of oular angles you choose。

 you miss that singularity。With different charts， the singularity might move to different。

Value for your old PR。 But nevertheless， it's there。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_155.png)

So， this is。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_157.png)

A manifold， you're familiar with。Sppeear， maybe， right， the surface of the planet。

We ignore all the mountains and oceans。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_159.png)

Just think about it as。The sphere。This is a manifold。The Euclidean space itself， is a manifold。

It's a flat space， R three。This shape is called Taurrus。You have one circle like this。

And then you have a second circle like this。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_161.png)

To move that circle。Around the other circle， you get a shape is's called tous。That's also a manifold。

So mathematicians are crazy about doing calculation。

These are spaces because they find flatter spaces boring。We don't we。

We like them a lot because we can make money。From flat to spaces。

So we want to make sure things remain as flat as possible。 We can do usual。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_163.png)

Calculations。To do that， we need to talk about a tangentous space。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_165.png)

To understand the geometry of。A surface。Which is the topic of Rimanian geometry。

We need to talk about tangent space and tangent vectors。Imagine this is a surface。

You can think about this as R3。 So the entire R 3 is your ambient space， just like this classroom。

Then there is the surface。Sumver floating。Clearly， this is not the entire space。

 The ambient space is so much larger。 This is just a piece of the space。

 It is a subset of this classroom。😊，If it's curved。I can't bend it so much。

Then you can talk about a particular point。And this surface。Because it is curve。If you consider any。

Smooth trajectory that is living on this surface， right？It's like a pattern。Tattoed on your arm。

 right。It doesn't live in the amben space。 It is living on that surface， this trajectory， Okay。

 it cannot come off because that's where it lives。At a particular point。

We can talk about maybe a tangent vector。If you parameterize them。

 curve and you can talk about derivative， maybe you can talk about velocity。But anyway。

 you can just attach。A bunch of vectors like this。How many of them you can attach。

Different magnitudes， different directions。In this particular case， how many。去。2。I just did one， two。

3，4， five， six。Have some faith in my drawings。Okay， usually is usually one or infinite in math。

 If it's not unique， then you can go as high as you want。 So infinite， this is， this is。

 in particular。 This is just the R 2 plane， right。😊。

You can think about it as our two plane attached to this point。So all the possible tangent vectors。

Vellocity vectors。Are in this plane， different directions， different magnitude。

So collect all of these vectors， which is our two here。Name。

That to be the tangent space at a particular point X。 So M is my。Manifold the surface。

T means this tangent。 X is。At what point now， for the Euclidean space。

 when you talk about the tangentous space at a particular point。It's the same thing everywhere。

 because it's flat。But for surfaces， it matters where if you choose a different。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_167.png)

Point， when you have to talk about where you are in that space， that matters。

You said that you're able to。先在经年。万点。Deine the a。Because when you take the derivative with gamma。

 you get one doctor。And so it seems like we need another path along that surface to define a side detector。

OkaySo your question is that。Just knowing that I can have a point。

And tangent vector is enough to talk about this tangent space。I saying that。Just having one point。

Sees like not。一个是比如说。Can I talk about a tangent vector to。The circle， at this point。You cannot have。

spaces in our。We can have any。Well， in this case， the tangent space is the real line， right。

 My vectors can have positive and negative directions in different magnitudes。

They are orthotgonal through the center， but that's not important。That's what defines the。Tangent。

 right。In this case， also， we know it's tangent。 that means。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_169.png)

What it means。You can paraize the surface。 You can talk about the tangent vector， right。

Or you can see it in the ambous space and talk about the gradient that will be the normal vector。

 That will give you the tangents plane to a surface， right， from multivaried calculus。

 We know we can calculate that。Then you will have a plane that is tangent to the surface at that particular point。

If you only have a single path。You a single group。Oh。So let me see if I understand。

 You're saying that if I just have this path。Will that generate this tangent space at a particular point？

I'm saying that won't， unless you've got two paths。I think so others like other。

I'm saying that you need two vectors here the point。可以，一天就翻一翻。Yes。Was his answer good。

 I want to make sure it was recorded。What did you say？系大 think啊你系。ルだけ。啊，他长这呃。对。Yeah。

So if we have a point and a vector。Can we， we need two vectors to construct the normal。

 That's your point。But， I'm saying that。All of these tangent vectors。 So I have more than two。

You have。去装或。No， no for the same path， I can have different velocities at that point。

One time you're going with1 meter per second， next time you're going。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_171.png)

2 meters per second at different direction， that's already two vectors， right？

When my options are unlimited。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_173.png)

So， and we need that because the object that is moving the camera。Can rotate。

In around about three axis and can move in three different directions at any velocity。

Vtertually any velocity at any point in time。So the tangent space， at one point， considers all such。

Vlocities。But the point of this figure。 So does that answer your concern that how to construct this tangent space。

 which is， which is not something were trying to do here。

The shape is just saying that there is a tangent space。

 all these vectors are living it that constructs the tangent， it later for a particular group。

 we want to construct them。Yeah， that's good enough for now。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_175.png)

So that's one of the tricky topics based in experience， tangent space。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_177.png)

But if you limit yourself to surfaces in 3D space， it works just fine。 That's exactly what it means。

Now， the dimension of a manifold。Is the dimension of its tangentous space。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_179.png)

We have two examples here。In particular， the dimension of the tangent space of this surface is。2。

You can also relate to this idea that you need。Two parameters， maybe， let's say。

X 1 and x 2 to be somewhere on this curve of the space。 These two points are not the same as。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_181.png)

Ambientous space， because this point in our3。Obviously， have x 1， x 2， x3。I'm going to use different。

Numbers。Symbols。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_183.png)

It is somewhere in that ambient space， but on the surface， you can parameterize it with two numbers。

This dimension is captured nicely by the tangent space。Which is two for circle。It's one。

 If you know the angle， you know where you are in the circle。

 So the dimension of this manifold is one， even though it's embedded into。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_185.png)

R two plain。So the ambientous space here is。R2， right？



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_187.png)

So this concept is， why do we need this？

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_189.png)

Now， we need this because。We talked about from a somewhat dry algebraic path about matrices。

But when we reach to。The topic of Lee algebra， we need this geometric intuition to talk about。

 to define the Lee algebra。And。You have a question。Yeah yeah， I was wondering is your。

Is your a manifold dimension？Always going to be。One less thing your space definition or other。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_191.png)

I don't think so， we did not write it that way。Otherwise， I would write。 So's always one lesson。

You mean， the ambient space。Yeah。No， because you can embed the circle in the 3D space too。Can have。

I mean， these are things that you read in math books， right， engineers don't fool around with。

These examples， but you can embed the circle in in just a 3D space。 Now， the ambient space is R 3。

 The circle is the same as still。It's one dimensional。So no。

 their concise definition is that talking about the tangent space because you want it to be always true。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_193.png)

Right。But it's a good。Good example。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_195.png)

Back to matrices。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_197.png)

Now， algebraic objects will not necessarily give you a geometry。

We're going to claim that matrices are geometric objects as well， matrix groups。Because if you have。

At2 by two matrix of real numbers。You can easily arrange them in。A four vector， right？



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_199.png)

And then you can work in a four dimensional space。 Now， you might not do that。

Do this operation or for whatever reason you're comfortable to work with this two by two arrangements。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_201.png)

But， there is a clear。It's called isomorphism。You can go back and forth without losing anything。

So you can think about your two by two matrix。As。Our 4。Now， your matrix has some constraints。

It's not all of them。Maybe you're working with orthoagonal groups， right， So it's not going to be。

The entire。Let's say our4。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_203.png)

It's more like this surface。 So your matrix group， we do not know the shape of all of them for some of them。

 It's easy to guess or talk about them， but not necessarily for all of them。

It's more like this because the constraint in the definition of the matrix group will form。

A subset of that ambience space。Because otherwise， it would end up being just the Euclidean of space。

 not the matrix group。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_205.png)

Okay。In particular， I'm talking about this a transpo a equals the identity。

How can you have a3 by three matrix，9 numbers。Flatten your matrix and call it a nine dimensional space by ignoring these constraints。

If you only go after those nine vectors that also satisfy this constraint when you arrange them into a matrix。

You clearly needs to pick a subset of those9 vectors。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_207.png)

So in that sense， we can convince ourselves that matrices are。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_209.png)

Geometric objects， because they are a subset of some Euclidean space。Now。

 you can also prove that they are very nice objects because of this multiplication， invertability。

All the operations are smooth。You won't end up with any singularities in this case of matrix groups。

So we do get a smooth manifold。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_211.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_212.png)

I can give you reference for proof。 We are not so much interested in that。

 but they are nice geometric objects as well。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_214.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_215.png)

Now。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_217.png)

If that's the case。Now I can talk about the tangent space of a matrix group。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_219.png)

We just defined the tangent space。I'm just using more sophisticated notation here。

But all I'm saying is that the tangent space， if I have a subset of a Euclidean space， G。

Its tangent space， at a particular point。It's the set of all。Initial velocities， these vectors。

 we call it B。For a path that goes through that point。Precisely the shape that I have。It's manifold。

I have a path。 This is gamma。 This is G。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_221.png)

Take your path， this path goes through G。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_223.png)

Define a neighborhood here。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_225.png)

Within that small neighborhood of that point。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_227.png)

I want this path to be smooth， differentiable in the sense that if you have two。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_229.png)

Basically。Entries to parameterize this curve。 I want them to be differentiable in the sense of usual real calculus。

 You can take derivative。 You can work with them without facing any problem。Now。

 within this interval， this point is my 0， right， I just define it。

 I parameterize this curve to be like this。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_231.png)

When gamma is 0。When gam gamma evaluate at 0， it goes through that。Point G。

Then you can talk about it derivative at that point。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_233.png)

All the possible velocities you can have。My pen from here is going to this point， right。

 at a particular point。What are the set of velocities it can have， whatever it can have。

That forms the tangent space。At this point。Why we justt don't talk about。

Vellocities in the Euclidean space。Well， because we want to work with rotation as well。

Rotation is not a flat of space。So the tang spaces。All the functions of。交了。

Gamma prime is the velocity。追审单位。But at a particular point。

 because as as soon as you move a little bit along the path， you're no longer in that tangent space。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_235.png)

That makes that's the reason calculation in care spaces is challenging。

You need the notion of covariant derivative to deal with。Moving along a curve。

Talking about the derivative of a function。 But for the tangent of space at this particular point。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_237.png)

Right， you have your。Playing。All the velocities。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_239.png)

At that point。Now， we parameterize gamma with T。 T varies between just minus epsilon and epsilon。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_241.png)

Such that when t equals 0， we are at that point。Right。

This is the same thing that you might have seen in your calculus course in when you parameterize a line or surface。

With the T， right。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_243.png)

So that's the general definition of the tangentous space。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_245.png)

Now， we're ready to。Tell you the truth about。Lee algebra。Lee algebra。Of a matrixtri group。

It's just a tangent space at the identity。Okay。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_247.png)

You might ask why the identity element。There is a very simple reason because all groups have the identity element。

You don't want to go back and then figure out。How to change the rules for every group。

 All groups have the identity element。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_249.png)

You can use， you see different notations。It doesn't matter。And this。

Cathic symbol usually is used for Le algebras。So the tangent space at the identity is a algebra。

 which is a vector space。Space of all these initial velocities。As we will see。

 gyroscope will give you angular velocity。 That angular velocity is in the Le algebra of S O3。😊。

It is naturally modeled in data space。When you integrate that。

 you're just basically integrating gyroscope data to track the orientation。It is naturally。

Modeling that for us。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_251.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_252.png)

So we can talk about the Le algebra of every particular matrix group。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_254.png)

This is the part that。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_256.png)

M need to practice。Your homeworks and piazza。Of course， I give you the solution。

 but you want to go through them。For general linear group， it's very easy to prove。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_258.png)

And we show that the Le algebrabra of。The general linear group is basically all the end by end matrices。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_260.png)

With no constraint， they can be also。Singular。AndThe logic is that take a path。

 that gamma that we talked about to be identity plus T times。A， A is some n by n matrix。

Possibility singular。Now， clearly。This path goes through the identity。Thishich is what we want。

 right， We talk about Lee algebra。 All the path that we talk about should go through the identity。

The derivative of gamma is。Basically， a， right， But also， when you evaluate it at。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_262.png)

0， it's a。The derivative is， with respect to T。Which is easy to take。 T is just a scalar。

Prometertor like time。Now， the logic is that。If you。Assume this integral is small。

Then the determinant of。Gmma at 。0。It's one because gamma 0 is identity。Okay。

As you change T to be a little bigger or smaller within this small interval。

 the determinant will change smoothly because the determinant is a continuous function。

It cannot just change widely。 It will。 It will change a little by little as you change T a little by little。

That shows that if you constrain this interval to be small enough。

Because the result that we get in gamma defined by identity plus t times a end up being invertable。

 The determin is non0。 Therefore， gamma is。Indeed， in the general linear group。For all tea。

 in that interval。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_264.png)

Now， if a is the velocity that can be any matrix that is generating this path that belongs to that group。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_266.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_267.png)

Then a must be also in the Le algebrabra of general linear group。Okay。

So you need to play with these logics a little bit to convince yourself that。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_269.png)

This is the shape of this。Lee algebra， what is interesting about it。Nothing， because。

All the matrices， even singular。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_271.png)

So let's move on from this group。What about SON？

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_273.png)

Let's define something more familiar， maybe。This is my path。So， I know that。Rotation times。

 rotationt transfers must be。The identity matrix。If I take the derivative of。

The rotation matrix with respect to T。And then I evaluated that the。Identity T equals 0。

My path goes through the identity at T 0， right。So when I evaluate that。

 this becomes R dot at 0 plus。R dot transpose at 0 equals 0 because the derivative of the other side。

 the identity matrix is 0。Now， I can also say that。My initial velocity is some， some matrix a。

Whatever， that's the initial condition。I化。I talking about previous slide， Let's finish this。

Oh different from。It is。 I'm just assuming there is a path。 It goes through the identity。

With this initial velocity， we don't know what's the good path。 That's the question。We're on the。

 we will be on the quest to find that。It ends up being matrix exponential， but。We will talk about it。

So therefore， this will give me a。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_275.png)

Plus， a transports equals 0。 So I learned that if I。

Differentfferiate the constraint of the autogonal group。It will give me another constraint on。

Their velocities。Vectctorors in the tangent space。 Now， what are the matrices that。

When you transpose them。You get the same negative of the same matrix back。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_277.png)

Is there a general rule for these matrices？There is excsisymmetric matrices， right。

Imagine a squy matrix matrix of matrix of。Usual。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_279.png)

嗯。Perfectly aligned， but this is the angleular velocity， sssymmetric。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_281.png)

Matrix that we can use。Now， if you transport this matrix。It is symmetric。The one changed。

After aagonal1s， because it's sysymmetric， the negative signs will also move。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_283.png)

So， we will get。A trans is negative of a。So all， we learned that all the。

Marices in the Le Aljebra of S， O， N， or in particular， S O 3， are exclusive matrix matrices。

So well just learn the structure of the algebra of rotation matrices。Okay。

And that's because it's a rotation group， then the velocity is also called angular velocity。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_285.png)

You can， of course， write this in a。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_287.png)

Vectctor 2， but the Le algebra formula within a matrix basis is。What we see here。都通的是32G。

guaranteeant to the second。Well， I。Differentiated this with respect to T。で。So。R8 times R transpose T。

 and they not' sure what。You're talking about this。Identity， this is the identity matrix。

 Oh I before。Yeah， for， for the autogonal for S O N， we had these constraints that。

R R transpose must be the identity， right。I'm differentiating that constraint。

 and that will tell me about the structure of its tangent space。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_289.png)

I was good。 I didn't know this。Yeah。工察的ね。So side second ask。哦。My bad。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_291.png)

No S。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_293.png)

There is no S in this slide。 There is one here。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_295.png)

All right。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_297.png)

Now， now we can go back to that mess that we made for how many ways we can rotate。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_299.png)

And it still is good to think about how many ways we can rotate in our four， six ways。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_301.png)

The dimension of S， O N is n times n minus1 divided by 2 y。

 The dimension of the manifold or our group is the dimension of its tangent space or Li algebra。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_303.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_304.png)

We know， the Le algebra of S， O N are exclusive matrix matrices of dimension N。

These are symmetric matrices with diagonal entries to be zeros， right。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_306.png)

And n by n a square matrix has an n by n， square matrix has N a square。Enterries。

All the diagonal terms are 0。It is also symmetric。If you know half of it， you know the other half。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_308.png)

So we learned that the dimension of S O N is n times n minus1 times 2 for3， we get。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_310.png)

This， which is。3e。For4， we get。6。So in four dimensional。Spaces you can rotate in six ways。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_312.png)

Whi again， you can write down E1， E2。E，3， E 4。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_314.png)

To rotate about an axis you need。A plain。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_316.png)

Right，You need two of these vectors to define。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_318.png)

That plane。For the first vector， you have four option。 for the second vector， you have three option。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_320.png)

You just chose one of them， right？Oh， that's the reason why。

But then also you can out that the order is not important。

Because one and three is the same as3 and one。It gives you the same plane。

So you can dig into it like this as well。 but it's really weird because。You have four directions。

 but you can rotate in six ways。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_322.png)

Imagine a theme park。Like that。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_324.png)

Sounds abstract。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_326.png)

Okay， so let's see。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_328.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_329.png)

What about the tangent space at other points？The identity is nice。 It will tell us a lot。

About our matrix group。 But we want to also know what is the tangent space at another point。

 not the identity。Right， if it this is my 0，0，0 rotation， what if I'm like this， right。

What is the shape of the tangent space at that point？



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_331.png)

It's a fair question to ask。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_333.png)

So， the answer is。What makes Li nice is that。You just need to do a left translation。

For the vector space as a whole to move it to。Another point， Another words。

 the set of all possible velocities won't change。 You canstill。

Rotate with the same type of velocity you wanted， whether you're here or whether you're at this configuration or at this configuration。

 So that won't change。 And mathematically， that's captured by a left translation， meaning。

If you rotate your S O。3 by R， you get the tangent space。Of S or3， this is a small。oh。

 so you get the tangent space at R。 So as a whole， all possible velocities。

 you're just rotating the whole of space。 We're not talking about the individual velocity。

 That's a whole different story。What is the equivalent of individual particular velocity that we have at this point on a different tang space where the space as a whole just needs a rotation。

Okay。That's why you might hear that the say legal groups， tangent spaces are all e Murphyic。

They all the same。 They look the same up to a left translation of the group itself。Very equivalent。

 And that's very nice and powerful。So if you have your angular velocity， A。You use the rotation。

 right， That's what you do。To know your anglengular velocity from the sensor frame。

 right that you measure。With respect to a fixed frame on the robot that you might be tracking。

 you need that rotation。To rotate your vector。That's what we're talking about。It's notや。

We know that demo。也在这。Given the definition of M。で。Yeah， that you say that。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_335.png)

We don't。We guess we need to find out。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_337.png)

What does the text say if It even been？Or with the exponential， it is， then later we should see why。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_339.png)

Well now， I didn't go through this part， but the question is。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_341.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_342.png)

To generate this result， we assumed a path。And knowing that path lie in the group。

Why that's the case。You do need to prove that path that lies。In a group。Here。

 I'm giving you an answer。 If you take any path like this with the exponential of the matrix。

 it will。You might wonder why。It's coming up。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_344.png)

Soon。Which is now next slide， why？Now， if you know the path it's the exponential of the matrix。

That will tell you that all tangsent spaces are the same， up to a transformation。Left translation。

 And physically， we know that。Based on our experience， working with velocity vectors。

We just rotate them。 and we want to change the frame。Now， what's the best path or what。

 what is it that qualifies that exponential path。A conceptual way to think about that is。Like this。

If you。Or at the identity， which I'm showing it here by eye。You have one tangent of space。

Then imagine youre at a different point。The X。We can， of course。

 talk about the tangent space at the other point。If you take the derivative of any path that goes。

Through X， X dot will be in the tangent space of。The group， at that point。

So it belongs to that tangent space。Now， these are。Transformations。

 we know the difference between the identity and x。It's just a transformation by matrix。

If you multiply。Your vector here。By that transformation from。Left or right， you choose。

This must map your vector， right， translated。To the identity。

 So you will get another vector at the identity。 It won't be the same vector， whatever it is。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_346.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_347.png)

The velocity， right， of the end effector， when you rotate it with respect to the base frame of your manipulator。

 it won't be the same。But it is another vector map using some rotation。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_349.png)

Now， we know that， of course， this is also。Some other vector C， but not the same as Xt。

Because this in the tangentous space of the identity is， of course， part of the Lee algebra。

Whathy iss the tendency。And space。Because we just translated by X inverse。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_351.png)

X inverse times x gives me the identity， right？Imagine now a vector that is。

In the tangent space of X。Then this should be should give me another vector Q C or A。

 whatever notation you want to use。That is in the tangent space of。The group had the identity。

Just like rotating a vector， right。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_353.png)

You have a frame。You have a vector V。And then you have a base frame。This is your identity。

Your moving frame。What is the velocity in the。Inertial frame， identity。And this is。I don't know。

 you know some rotation and translation with respect to that moving frame。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_355.png)

There will be some other。Vctor。U， now U is rotated version of V。Or depending how you have it。

 you Yes， U is the rotated version of V。Depending how you define the rotation， right。

 based on inverse of it or not。I'm talking about the same thing。So x start equals x times。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_357.png)

M see。I might have used。I need to use our inverse here。 So this makes sense。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_359.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_360.png)

Now， this observation is true for all league groups， because。It follows the same rule of。

Vectctors and matrix transformations。So， we arrive at。A fundamental result that。For any legal group。

 you have。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_362.png)

A first order。Matrix differential equation。If you've had a course in linear differential equations。

You can solve this。 This is。Solve using。An initial condition。So， X， T is。X 0。Times， me too。X。

 T is x0 times。Exponential of。次。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_364.png)

The velocity。You might have seen it for vectors。 It works for matrices， as well。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_366.png)

So you get a fundamental result that describes the kinematics of all lead groups。

 You get a first order differential equations。 We know the solution to the differential equation is using matrix exponential。

 So that's why it's the must。Natural path， you might call it best。 It's not unique。

 There are other ways to do it。This is a very natural way to do it for league groups。For example。

 for S E 3， the Le Albra is the ssisymmetric matrix C and a vector V。

When you do the left translation， it's just rotating your velocities。Translation will have no effect。

We will work with this extensively if it doesn't make sense now。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_368.png)

So， that tells us。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_370.png)

That matrix exponential is the right path。Because that's the correct way to integrate that differential equation。

 You can do Euler approximation and other approximation for the solution。

But the exponential of a matrix considers all of them。In particular。

 the series for exponential of matrix is。This infinite sum。In that matrix。

 it converges for all matrices using。You can find a proof in analysis books。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_372.png)

Using sub multiplicative norms of matrices， you can prove that this is convergent for all matrices。

 So theres no。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_374.png)

Challenge for calculations of this。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_376.png)

And。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_378.png)

So for legal groups， when we talk about an initial velocity that is in the Lee algebra and a path。

You will always have this path。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_380.png)

For a velocity， whatever it might be， you can generate a path gamma of T using this exponential of T times a。

So a will change。 The path will change。 We will get different。Path。But also。

 you know that if you differentiate。The exponential of a matrix will commute with。

That matrix from left and right。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_382.png)

It's easy to prove， to prove。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_384.png)

I can give you another reason why the exponential is the best。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_386.png)

Way to define a path。Take。Is chisymmetric matrix。Calculate this term。 Take the determinant。

Is not one。Add the second term， you gets closer to one。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_388.png)

At the third term， a fourth term， it gets closer。 after fourth or fifth， it's almost one。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_390.png)

So these are different ways。That we could move with the same velocity。To put us in the。

And the path that we want to be in the， in the group。Which one is the best。

 Which one I should choose squared。Sine， cosine。How about all of them。If if you combine all of them。

 right。It will give you infinite series。 If you do it in this particular way with the coefficient。

 it will convertverse to the exponential。So this is same idea that。You have。

Exponential definition of。Limit the definition of the exponential functions。

How many ways you can push this。Point on that tension space forward。To move along that path。

There are many ways， there are infinite ways。How about compound all of them that will correspond to the exponential function。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_392.png)

So first order like this is a one particular choice。

 If you consider all possible ways you could move using that initial velocity corresponds to the exponential functions。

 because in the limit。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_394.png)

The combination of all of them， the compound of all of them will give you the exponential function。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_396.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_397.png)

So， I think we should。Stop here。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_399.png)

We want to answer the question that how to map the velocity from。

A specific vector of velocity from one tang space to another。For that， we cannot do it yet。

 We need a joint map。

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_401.png)

So next time well talk about the adjoint map。But what I want to do， I want to。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_403.png)

Go through some derivations and handwriting。So take a look at the examples， For example。

 the cross product of thetry。 So you can make it a little more interesting by doing hand handwriting。



![](img/420e799f23e81498b3e7c3b8b2f8e6ac_405.png)

![](img/420e799f23e81498b3e7c3b8b2f8e6ac_406.png)