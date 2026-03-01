# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p25 -25-Guest  Lecture - Equivariant Learning for Robotic 3D Perception.zh_en -BV1UfAmeUE3e_p25-

![](img/341d491193bced69bdabd83e2e7622b1_0.png)

嗯。Hello everyone， this is my pleasure to introduce Mingk Ju Mink has been here with us in Michigan he's one of the smart people that I I'd be fortunate to work with。

 he always keep me on my toes but the problems he solves today is going to talk about equivarian learning for robotic 3D perception。

ok， so。Hello， everyone。 I'm Ming Hanzhu， and I've been in Michigan for quite a few years， actually。

 when Mo was giving his first iteration of the mobile robotics class。

 I I was one one of his students。 So it's， it's a great pleasure to come back to this class and give you a guest lecture on this。

😊，It's that great all know me。So I'll get started。

![](img/341d491193bced69bdabd83e2e7622b1_2.png)

Can you see the slides in presentational？😊，Okay， cool。

So today the topic of this talk would be equivalent learning for robotic 3D perception。😊。

So basically， we are talking about a type of learning framework and especially in the context of robotics。

 in robotic perception。😊。

![](img/341d491193bced69bdabd83e2e7622b1_4.png)

So let us start with。Robotic applications so we are all in this mobile robotics class and I think we are okay we have several a lot of robotic applications in our mind。

 for example， to name a few object manipulation， which is basically you have a robot arm or hand to grasp and manipulate objects。

 a typical robotic task。😊，Or indoor navigation， we have a robot and we want you to move around in an indoor environment。

 which is also like a there exist even existing commercial products on this。😊。

And autonoomy drivingiving， which has been a very hot field for quite a few years and we all know it's a very challenging task and it also can be viewed as a robotic task like a robot navigating in the outdoor scenario in a very complicated environment。

And for all these tasks，3D perception is an essential part for it。😊。

It basically enables the robot to understand the3D environment， and more importantly。

 it prepares the robot to interact with the real world entities in the3 world。😊，Therefore。

 superior perception for robotics applications actually have two very important characteristics。😊。

The first is safety critical because the robot is designed to be interact to interact with the real world。

 therefore， the arrow in the perception can have catastrophic outcome。On the other hand。

 the computational power for a robot on board is typically limited。

 therefore the perception algorithm is also resource sensitive。

 we cannot put a huge model like like requiring hundreds of GPUs to put it on a single robot。😊。

Therefore， these two characteristics of 3D perception for robots poses two requirements on the perception algorithms。

😊，The first is having predictable behavior from the perception algorithm is very important。

On the other hand， the efficiency is also very important。😊。

And here let us start with the first point by predictable behavior。

 we specifically mean we want the perception algorithm to give predictable outcome under various environmental changes。

So。So here let's break this out and see what composes the environment changes that a robot can face in the real world。

Here， I basically put them into two categories。😡，The first is different entities。

 and the second is different observations。So for the first category， different entities。

 what does that mean， basically， for example。😊，For a perception algorithm to recognize a chair。

There are a lot of chairs， like different shapes， different styles。And each of them。

 we want the perception algorithm to reconc them。So there are all kinds of chairs and we want the model to deal with them robustly。

Also， for example， these are the bizarre view of some indoor environments in the open source data set。

 also of course， there are numerous different layout of indoor environments。😊，Similarly。

 for the outdoor environments， like the road layout， the environment can also vary drastically。

These are all different entities in this context。However， on the other hand。

 a lot of the environmental changes are coming from different observations of the same entity。

 the same object。😊，For example， here， if you view a chair from different point of view。

 the appearance can vary drastically。And the second figure is a tree。

 You view it from different pulses and the appearance can change a lot。

 Similarlyly for out for the for the auto driving application， the。

 the vehicle appearance can change。Although it is the same vehicle when it's at different distance to you。

 the appearance can change a lot。So how do we deal with all these environmental changes？😊，Today。

Most models basically deal with them in the same way。

 we just use their large enough differently models。And design in a very good way。

 and then we actually deal with all the different entities in different observations。😊。

We deal with them in the same way。 We just use a model to recognize each of them。😡，However。

 there is a natural question to ask。😊，Since the different observations are typically， for example。

 for the same object。😊，Then can we only learn once for the different observations of the same object？

That is， if a model can recognize the intrinsic property of an object， we know that it is it。

 no matter what it appears to look like。Then。嗯。What benefit will they bring us？And how do we do this？

So here can we do this， can we learn once for different observations of the same object。

 actually we can， and the answer is to leverage the symmetry。

 that is if we even the model can capture the underlying symmetry of all the different observations of the same object。

😊，This can provide us huge benefit。That is if we put this symmetry。

 we deal with all the symmetries in the symmetry preserving models。😊。

It can help us to yield predictable behavior for all these observations because the model knows that it is the same thing。

 no matter what it appears like。Therefore， it adds a robustness to the perception system。

On the other hand， remember that efficiency is also a very important part of robotic perception algorithms。

And since now we can deal with all the different observations as one as the common object。

 now we can preserve the model capacity to actually learn different entities。😊。

And this can reduce the demand on the model capacity to actually grasp the environmental changes in the real world。

So here we say that we want to deal with the underlying symmetry in the environment using the symmetry preserving models。

 or in other words we call them equivalentval models， so what are they？

Here I will give a brief overview of what this equivalent models means。Basically。

 equivariance is a property would use describe a function， the function。

 if the function preserves the symmetry to some group of transformation G。

 then we say that this function is equivariant to the group G。In other words。

the order of applying the transformation and applying the function does not matter。

 you can exchange them。Here， the circle notation here denotes the functional composition。

 so basically。😊，7。😊，Composed with fine。Is equivalent to5 composs T。

 That means these two operations are interchangeable。

AThe most famous example for equivaris in learning is the convolutional neural networks。

 They are known to be translation equivalent。 So what does that mean。Basically top。

 you can see there's a figure of a cat。😊，Now， and then we have a， for example。

 some segmentation model file。 And if it's a convol network。

 then the file model is translation equivalent。 It means that。

The the order of applying the segmentation model and applying the translation。

Does not matter you can either move the cat to another place in the image and apply the C model。

 or you can apply the C model first to obtain a segmented mask and then apply a transformation。

 the result are are equivalent。😊，This is because convolutional networks are translation equilibrium。

😊，We can see that this property enables。A very important benefit。

 that is generalization over the translational variations of the images。

The model does not does not lu each the cat at every position of the image separately instead。

You learn to segment the cat in one image， and then you move around the cat to arbitrary positions。

 the model automatically generalize and knows how to segment the cat。😊。

So this is a benefit of equiant in learning that we all are very familiar with today。😊，However。

 CNNNs are only equivalentant to translations。 They are not so they are not equivalent to rotations。

For example， here， if we look at image of a city's B view and now you rotate the image。😊。

You can see that the output feature map from a convolutional neural network not only goes through a rotation。

😊，But the content of the features learned from the image is also changed。Therefore， we know that。

The translation， that the adaptation of the input image is not equivalent。

To the translation of the output fisherman， instead， the fisherman actually the content is changed。

Therefore， actually the network cannot learn reliable reference stations when the input goes through these rotational transformations。

So that's a bad thing。And here is where the equilibrium models comes into the picture。Actually。

 we can develop an equivalent network that enables the SO2， the planner rotational equivariance。😊。

And with a equilibrium model， you can see that input when the input image goes through a rotational change。

 actually the output feature map also goes through the exact same rotational change and the content of the feature map is unchanged。

 is stable。😊，And here it enables the network to learn reliable and robust representations from the rotated images。

And equivariant networks extends the idea of translational equivariance to more general transformations and of course it can go beyond SO2 equivariance。

 it can go to SE2 SO3 or S3 and we know that they correspond to like the 2D rigid body transformation and 3D rotation and rigid body transformations。

😊，So imagine if we have a model that is that can learn the learn to be equivalent to the S3。

 for example， the3D rigid body transformations then。😊，Here。

 given two views of the same like living room。Under post changes。

The network knows that they exactly correspond to the same。Layout the same living room。

 It will not be confused by the post changes。In caused by the observer's movement。

And this can be very useful for navigation， for example。😊。

So this is a big picture of what equiant models are。😡，And in this talk。

 I will present you how we can construct such equilibrium models。Actually。

 the Iate models can be constructed from various network architectures that today typical deep learning a community uses。

 for example， the multilayer perception， convolution neural networks。

 transformers and graph neural networks。We can make all of them equilibrium with certain techniques。

And today we were mostly focusing on the top two， the MLLP and CNN cases since they're relatively simple and we intend this talk to be educational so we will introduce some relatively simple examples of such equivalent models based on MLLP and CNN and we will introduce very cool applications。

 the work done by us in our lab and also by other labs。

 because this is to give you a broader view of what the community is working on in this equivalent learning for robotics in this field。

😊，And to make it and also， we will keep the math simple today to just give you a a taste of what these models looks like and what they can do。

 But we will not go into very complicated math details。 But actually。

 this field can be very much heavy because this equivalent equivalent model development and theoretical backgrounds actually can。

😊，Become very can actually require a lot of work。In both the math and the engineering part。

But today it will keep it simple。So let's first look at MLP。嗯。

Without actually introducing a lot of the theoretical backgrounds。

 we will focusing on a very representative recent work called vector neuro， which is a。

Multti layerer perception work， but it is made equilibrium to three dimensional rotations。

And this work can be applied on point Cloud feature learning。

 and it has been applied in various robotic tasks， including point cloud registration。

 object manipulation and sM systems。There are probably more coming out。

So I will be introducing this framework to you now。

So vector neurons can be regarded as a S3 equi MLP。

 so we will compare it to what a conventional MLP looks like。At conventional MLP。

 we take point at as an example， this is one of the earliest and simplest yet still very powerful when called learning framework。

😊，So for a point net。Given a input point cloud of it can be regarded a matrix of n by3。

 So every row is a point。And basically， these different rectangles represent the features for the single point。

So basically for a pointnet， it maps the point feature a three dimensional vector to a C1 dimensional vector like it could be longer and then it maps to some other dimensions。

😊，And so every point is mapped to a deep feature independently。With C N dimension at the end。

 And then， and then we apply， theres a， there's a pulling layer to summarize or to basically to get an overview of all the points features to get a single feature vector representing the feature of the whole point cloud。

Pretty straightforward， this is what a point there looks like。😊，And a vector neuron。

lookss very similar。Expect that except that the feature of every point previously is a M by c matrix or it's one by c vector now the feature of every point is actually a c1 by3 or c by3。

 it addeds another added another dimension of three dimension of three of size three。😊。

So every point。Spature is now a C by three matrix。 That's the only difference between poignnet and vectors on the high level。

And why this can be a rotational equivalent network is because notice that there is a three dimension three length three dimension at the end of every feature。

 therefore both the input n by three。😊，Imput point cloud and the output C by3 feature。😊。

They can all be acted on by a rotational matrix， a three by three metrics in the input and in the output。

And on a high level， this is what enables the vector neuron to be a rotational equivalentvalant word。

😊，I'll break this up step by step and show you how this is achieved。😊。

The first step is called F initialization。😊，呃，4A。Basically to map a point an XY z to a feature for a conventional MP point that it is very straightforward basically it just by matrix modification。

 given a three dimensional vector you multiply that by by some c by three matrix then youll get a C dimensional vector this is pretty straightforward。

😊，For vector neuron is a little bit different， given a vector x Y z。

 it first actually takes the neighborhood of this point， for example。

 in this figure there are five neighboring points so actually we stack the offset vector of this neighborhood and then we get a m by3 matrix for every point。

 so now you can see that the feature for a point is now augmented to another with an extra dimension previously a vector now is a matrix。

😊，And then similarly， as the conventional MLP， we apply a weight matrix matrix modification on the left to map it to some hidden。

Fishature damage hidden feature dimensions。 say by3。

So basically there a feature theres a slight difference between conventional mapping and vector neurons is basically there is a step involving neighboring points to lift the dimension of each point feature from one dimensional to two dimension。

😊，That's the only difference。After this， actually later parts are pretty straightforward。

 for example， the linear layer for vector neuron is very similar to the conventional MLP linear layer。

 which is matrix multiplication。😊，For a point in that。

The linear layer is by multiplying the matrix on the left to map a feature vector to another dimension。

And for vector neuron， it is done in the exact same way。

 except that every point the feature has a extra dimension at the end。 However。

 it is not affected by the by the matrix modification。

 because the width matrix modification is on the left。

 therefore it is the function is of the exact same form。

 except that the output and input has a one more dimension。

And we can check that such a layer is actually rotationally covalant。😊，Remember， the equis。

The the definition of equivariance is just that the transformation and the function is exchangeable。

 the order is exchangeable and here we have the transformation denoted by a rotational matrix multi on the right and the function is a width matrix multi on the left。

😊，Therefore， it's very easy to see that。😊，Apping the applying the function first and applying the rotation。

😊，Is equivalent to applying the rotation first and then apply the function because they all correspond to multiplication on the left and right respectively and they do not affect each other so these two operations are equivalent therefore this layer is S three barrier。

And also we can show that the nonlinear layer of the vector neuron is also rotational equilibriumvari。

😊，So here the example is re， the simplest and widely used nu nonlinearator in any deep neural networks。

For conventional MP， I think we it's very simple。 It's just the max of this number and 0。

 This is what A does。😊，And for a vector neural， it is a vector rise version of Relu。Basically。

 it first。Estimates a canonical direction K， which is a  one by3 vector。

And then it will truncate every feature， every vector that is that is that is on the other side of this canonic direction。

 and every feature vector that is on the same side with with in the close direction as the canonic direction will be kept unchanged。

 So basically the this this this vector as value is just lifting this truncation to the to a higher domain to the 3D domain and use a hyperplan to represent the zero point。

😊，And every vector on the one side of the hyperplan is kept unchanged and on the other side of the hyperplan is projected to the hyperplan。

 which is the truncation。And it's also very easy to see that this operation is also rotational equilibriumvariant because。

😊，呃。Because， because the whole operation can be viewed as if， if you apply a rotation on the input。

 it can be the the rotation can be put out of the equation to the right。 and therefore。

 it is actually equivalent to apply the rotation on the output of this non nonlinear layers。

So this is how this non lily layers is also made verition。😊，Alsoso。😊。

Theveary is also permutation invariant。This is because the maxpoing and average polling。

 they are both permutation invarily。The idea is basically that you can see that since every point in the  vector neuron is processed independently。

😊，So the order of you stacking the different point does not matter because at the end。

 always take the max or you take the average。 Therefore。

 the order of all these elements does not matter will not affect the final outcome。 Therefore。

 this vector neuro。 When you apply a pullinging at the end， the output is permutation variable。

So with all this property。What can we do？So this is a very nice network architecture。

 So what can we make use out of it， We know that it is rotational equivariant and we know it is permutation invariant when we apply a poorly。

 So what can we make use out of it。😊，And here， so this is what we can do。😊，嚟。Consider 2。 club。

the first point cloud is P and the other point cloud is P prime。

 which is a rotated copy of the point called P with random permutation where the R is a rotation and the M matrix is the permutation matrix。

And we know that we do we do not know the point ofized correspondence between P prime and P。

 because we do not know what M is。 We just know that they are rotated point cloud。

 but we do not have point to point correspondences。However。Due to the equivalent。

Feature and equi property and theation invari property。

 what we know that is that the output of such vector neural network。

 the SO3 equivalent encoder will give us the final result that is related by a single rotational matrix。

😊，That is the FP prime equals to FPR。So now this has a very nice property because。😡。

This given these two measures relatedd by R， I think we learned in this class that we can apply SVD。

😊，On these two feature metrics。To obtain the final rotation， that is。

 we can conduct a point cloud registration， but not in the Euclidean space in， but in the。

Deep feature space， because the features are related by a rotational matrix。

And this is over work that we in our lab， we built a。

Poin cloud registration work based on this nice property。And how do we do this。

 I think everyone will all learn how to solve for the optimal rotation。

 given a equation Q prime equal to Q R。😊，It's just that the Q prime and Q are not point cloud。

 but to pseudo point cloud that lives in the deep feature space。😊。

So we can we can first calculate across covariance matrix and then use the singular validity compositionposition and then have to calculate the optimal rotation that best aligns the two pseudo point path。

 which are actually deep features。😊，And this strategy is very beautiful because now we do not need to solve for the correspondences between the 2 point plus P and P point。

😊，Remember， we do not know the correspondence between the point cloud。

 but now the tip features are automatically corresponded。 They are related by a rotation R。

 but there's no permutation metrics involved。😊，Therefore。

 we avoid the need of finding correspondence between all the points。And in practice。

 we know that P prime may not exactly be a rotated copy of the other print called。

 but they may be corrupted by noise。😊，So therefore。

 we also train a decoder to train an occupancy decoder to make the future more robust to noise。😊。

And will also apply a loss on the estimate rotation from SVD to encourage the network to find the rotation that actually correspond to the ground truth rotation that we want between the two point clouds。

And what's that strategy。Because it is correspondence free and the SVD is a provides a close form solution。

 Therefore， we can actually conduct a point call registration that is independent of the initialization error。

😊，Here is a figure that of the registration performance。

in the Mo F 40 is a object CAAD model data set， and we can sample point clouds from the object data。

 and then we rotate the point clouds to different by certain degrees and then we apply different methods to solve for the rotation and our method can actually achieve。

Consistent and very accurate。Registration， regardless of the initialization there。

So this is what we can do with this equivalent features。

 it enables us to solve the registration task in the deep feature space。😊。

In a very simple architecture。And this SO3 equivalent features provided by Vept neuro also have other applications。

😊，By other labs， both have done very cool works。 Here are two examples of them。

The first is after manipulation。So here that task is that there's an object， for example。

 a mark and a robot arm or a robot hand。😊，And then the the task is that we show the robot how to grasp grasp an object several times。

😊，In some pose， and then in test time， we ask the robot to grasp the unsm object in out of distribution pose。

 which is to grasp the marks that are uneen before in unsm pose as well。And here。

 actually the SO3 equivalent features helps because the graspping point can be tracked very reliably。

😊，Under post changes， given the SO3 convert feature field。Let us just say， in training you。

You actually mark the grasping point of a point cloud。And then in test time。

 when the point cloud goes through some rotations。😊。

The network can track the grasping point reliably because the features is rotationally equivalent。

 therefore the features also rotates along with the point cloud so that the grasping point can still be tracked on the pulse of the object that is oneen in the training。

And also， another application is S。😊，Here， this work， the new Se work。

 constructed an object sllan architecture。That is。In the map constructed by slan。

 the objects are not represented as point clouds， they're represented as SO3 equivarian features。

And because we know that the S3 conversionvari features can go through the same rotation as the Euclidean space twin cloud。

 therefore， these features can be fused into the s post graph optimization。😊。

So this is also a very cool word that makes use of such rotational uvari features。Yeah， so so here I。

Introduced a network is that is S3 variantant based on MLP and I showed how this can be used in robotics applications do you have any questions so far and I think I can also take questions in the middle。

If not， Ill continue。There's one question in chat， has there been any interest in using SE3 invariant features for place recognition from this similar viewpoint？

That's a recent work Cyia I think yes， I can just quickly say yes。

 it will come up I think actually I will more right right right just a very good point question almost like a question that I will arrange someone to ask in the middle of the presentation。

But yeah， but I actually sure。 So here actually， this question raises two very important observations。

 The one is the network we introduced so far is a S03 covariant feature。

 It is not equivalentvarient to translations。😊，Which is the limitation。

 So that's why you see the applications are mostly on objects。

And the other side is like for place recognition for from these similar viewpoints。

 so for place recognition that is dealing with points a pointhouse that is larger than object。😊。

And that that's why we are moving from the MLLP the vector neural world to a convolutional structure that I will introduce in a minute。

 because that enables to do deal with a larger point cloud that also presents translational variances。

😊，So so so so yeah exactly and that's what I'm going to Mininghan to clarifyify I did not pay anyone to ask any specific gos organic's not by me。

Great， yeah。So that means that means the students of this classes is great， yeah。

 asking great questions， yeah。😊，So。So yeah， so let's come to the second part that is convolutional neural networks。

 they can also be made equivalent and as I just said they can actually augment the S03 equis to more general equivaris。

 for example S3 that also enables to do more complicated tasks as showed be。😊。

So before I go into the how we can make equi convolutions and we need a little bit background knowledge on the concept of groups。

😊，So basically， we use groups to describe the transformations in robotics。

 all the transformations are actually belong to some groups。😊。

A group in math is actually a set of elements， and the set of elements is also encrypted with a binary operator。

Satisfying the four actionss。 That is closeness， asciivity， identity and inverse。Basically。

 these are very。Easy to understand。Axioms， basically， for example。

 the closeness basically means that if you take two elements in the set and you apply a binary operator between them。

 the output will also be an element in the set。😊，And the identity basically means that there is identity element in the set so that when this identity。

 when it is operated on with another element， the return will be the same element with unchanged。

 So that is what this identity means。And examples are very simple， for example。😊。

Integers or real numbers， they when they are equipped with additional operator plus it is a translational group。

 basically just add and subtract the numbers and they correspond to you move the。

 for example in a R2 plan this translation translational group is basically just to move the image contents around in the image plan So this is this is what this is a very simple example of a group。

😊，And then we also have S， O2， S， O 3， S E to S C 3。

 the rotations and rigid transformations in 2D and 3D space。 And they are all groups because。

 you know， you apply to rotations together。 The output is also rotation。

 You apply to rigid transformations together。 The output is also transformation。

 So they this is just what groups are。😊，The reason that we want to introduce the concept of groups is that they allow us to generalize the idea of convolutional neural networks。

Two eco versions。So a conventional convolution is basically given two functions。

 One is F is the input featureisher map Des the kernel or the filter。

 They are all functions from a Euclidean orange space， mapping into some number。😊。

And the convolution between this two between the function and filter is just to in take an integral over the R space with a with a translation on the function。

 So basically it's an integral integration over the over over the R。

 The output of this convolution is also a function defined on R N mapping to a number。

 So this is what a conversion conversionvolution look like。😊，And by the， by from the last line。

 we know that R N， the UKan space is also a group。Equiated with the plus model plus operator。

 So R N is a group。 Therefore， we can generalize this R N just two groups to any groups。

 So then well have group convol。😊，Basically， just to replace every RN such set to G。

 which is the group that we care about or the set of transformations we desire the equivalent property from。

So now the function and the kernel filter are both from G to R and the convolution is also integral over the domain G and the output featureer map is also a function from G to R Comp with the conventional convolution。

 A group convolution just lifted the domain for the input function filter function in output function and the convolutional operation。

And this G can be RN， then it maps back to their conventional conversion or SO to S to S3。

For example， we can consider a S U T S E2 case。 It is S O2 times R 2。

 And here because we are doing convolution and they need， they actually need a discretization。

 We not discretize the S O 2 rotation to490 degree rotations。 Thats 0 pi over 2 pi and。And three。

3 over two。 So basically these are the four rotations discretized in the S2 space。And in this case。

 actually， what we will see is that the。😊，Function， the deficer map originally。

 its a iss defined on the R2 space。And now if we augment that to the groups of S E2。

 it will be a the the the the function function input fishisher map will be defined on R or R2 times 4。

This four element correspond to the four element in the C4， which a discretization of S O2。

 So basically we augmented the domain。 The fisher map is now larger。

 The value now lives not only on a point in R2 but also on a point in the C4 dimension。

So this is what a group convol will look like。 The domain is lifted。😊，And because of this。

 by plugging different G， we can enable different kind of equivariance。 For example。

 I give you some application of using S E2 equiant on images。The2D translation and the rotations。

 for example， digit classification， when you rotate the digit on the M data set。

 a network can reliably recognize the digit。😊，Because it is equivalent to the rotations。Now。

 so it may not be a very funny or interesting application， so there are more complicated ones。

 for example， upset action in aerial images。😊，Because when you take images from the sky。

 the object detection tasks in such data， a very important characteristic is that the objects it can be of arbitrary orientations and in such applications。

 the rotational equivariance can help the network to reliably detect the。😊。

Optticics on the ground in different orientations。Also。

 it can be applied in an image keypoint detection。Here。

 a model is given two images that is rotate copy of each other。 And because of this S2 equivariance。

 the network can reliably。Detect the key point and actually corresponds them very well because the network knows that the。

 the features from these oriented key points will be the exactly the same as the。

Of the key point before the before the rotation。And also we can take Se3 and go to3D space and it can be applied on point cloud applications。

😊，So here are two The first is a object post estimationary reconstruction task basically given a point cloud of the object and put maybe in the in the 3D world。

 now a network can detect the object and estimate a pulse and reconstruct the full shape of the object。

😊，On the arbitrary post changes。Also， another work is RGBD 3D object detection。

 which is in the indoor environment because the object can be placed in arbitrary rotations。

 so a equivalent network can detect the object and estimate its orientation very reliably because of the equi features。

😊，For example， so here is a， here is the example of a rotating chair how the how it can be dealt with from the use using the e model。

 And there is a even cooler。😊，Demonstration on their website。

 So this is also a work from another lab， which I found very interesting。 So here。

 basically the reference the left shows the ground truth， buning boxes and the， the。

 the chair that is rotated。😊，And for a non baseline。

 the rotation will cause the network to to be confused。

 It does not know It will regard every rotated chair as a completely different。Scenario。

 so the detection result is not consistent。 However， if the model is exant。

 you can see that the detection。Result is very consistent。

 and the rotated chair can also be reliably estimate detected with the orientation also estimated reliable。

😊，So this is how these group can be applied on more complicated tasks。😊。

By plugging in different kinds of G into the Google Compvolution network。Any questions so far？

Great I'll continue I ask a question this generalization is very nice the the older solution is data augmentation right but nothivarian methods。

Do data augmentation for all possibility which blow up the size of training sets substantially right you comment a little on。

This factor and。When data augmentation outperforms maybe equivarian models。

 or do we still need data augmentation with equivarian models why if we do？Okay， so first。

 if we compare data augmentation and and and equivariance。 So so actually。

 this comparison is what is part of the answer， Basically。

 because the non equivalent baseline is trained with data augmentation on rotations。

But you can see that the result is still not as good as e models。

 because the data orientation can only like like like like train the network and force the network to learn each instances。

 each rotation is， each different views。😊，Separately。

 but the evari model can actually deal with them and by design。 So by design， the network is。

 is designed to know that the different rotations are actually of the same object。Therefore。

 it is much easier to learn and learn more reliable representation。However， it。

 it do we still need data， actually， yes， because the group convolutions。

 as actually you can see in the previous example， it is we need a discretization on the group。😊。

Therefore， disctization will create gaps in between the disctizations。

 We still need data limitationss to fill the gaps。 However。

 because the now we are just filling the local gaps。

 the smaller gaps between each discretization interval。

 that is much easier for the network to to learn。😊，Okay， I'll continue then。 Thank you。Sure。So， next。

I show that actually， so while this group conclusionvol can have various applications and a lot of success。

 there are some limitations on this group， CNNN architectures。😊，It's mainly about efficiency。

So we can see that the group evolution lift the domain from some RN to a larger domain。

 the group space， a more general domain。😊，It actually will cause the computational class to increase。

 Here is a visualization of this。Here I show the conventional CNN and group CNN in the left and right columns。

And the top row is what an element look like， for example， in R3， a point in R3 just a point。

 I use a search to denote it。😊，But now in groups a twin does not not only have a location。

 it only it also have all of orientations， for example。😊，Now， at a point， if we use， for example。

 use these four directions to discretize the S O3， then at every point。It is a point。

Composed with all the four directions。That will create a problem when we apply the convol。

 because when we do a convolution， a point is we'll exchange information with neighboring points。

In the 3D space for conventional C， for example， here。This point has four neighbors。

 so it will communicate information with these four neighbors do four operations with the neighbors。

However， for a group conclusionvol， if every point has four orientations and every point has these four orientations。

 therefore， we will communicate the information from this point to the neighboring point。😊。

There will be much， much more connections that needs to build communications。And every。

 you can see every curve here is a curve is a curve connecting the orientation of one point to another orientation of another point。

And this can cause a lot of computational cost due to the domain lifting issue。

Especially when the group is large， for example， S E3 is larger than S O3 is larger than S E2。

 but when when we go up the dimension deal with the 3D problems。

 this computational cost overhead can become a problem。😊，Therefore。

 one of our work in our lab is to improve the efficiency of groups in。😊。

Our method is to develop the quotient space convolution。So the quotient space without I would not。

 I I will explain what is quotient space in next slide。 But the overall idea is just。

 you can see that the quotient space is denoted as G divided by H。😊，So as typical division。

 we all know， this division will make the final results smaller。😊。

So the key thing we need to know is just that the G over edge is a space that is much smaller than the original G。

 And because we are working on a smaller space， the convolution can be more efficient。

 So that's the overall idea。😊，And G over ash is the thing we call potion space。

 it's basically by dividing a larger space by a smaller space。

 dividing a larger group by a smaller group， and we take the pottion out of it。

So we actually developed a。Pocean space convolution for point cloud processing。A in our recent work。

But actually， the quot space convol， this whole idea。

 the theoretical foundation is actually already built in previous literature。

 but we bring this property and apply this idea on the point called learning in our world。😊，就。

So here I will explain to you what is a quotient space in the S S3 space so basically you can see that we are working on S3 covariance and we are taking the smaller group H S S2。

 which is the circular rotation on the plane and the quotient space is S2 times r3。

 which is S2 is the sphere space here I'll explain what actually it means。😊，So basically， SO3。😊。

It's a group of3 rotations。 It can be understand as all the rotations of the ball。

And every rotation of a ball can be specified by a rotational axis and the angle around this axis。😊。

And by taking the portion of this SO3 rotation by the planner rotation。

 it's basically to group all the rotations over the same axis as a single point。😊，The now。

The quotient space can be represented by other points on the sphere。

So now by removing one degree like that is the rotation around this axis， we go from six dimension。

 six degree of freedom to five degree of freedom， so this is a smaller space。😊。

So that's why we say the sp is a quotient space of SO3 over S2。😊，And in practice。

 we work on discretized the setup， as we just mentioned， therefore the ball。

 E or3 can be discretized as the ball sphere， the ball can be discretized as a poliian。😊。

Here we are using an xo hydrogenedron with 12 vertices。So the rotation。

 the S3 rotational group can be discretized into the rotation of the polyhedron that keep。😊。

Keep all the vertices unchanged。So it can be counted by counting the number of vertices times the number of edges connected to each vertex。

The by rotating the， by rotating the。Polyhm by such angles， it will result in the same polyhm。

 like you can you cannot tell the rotation if all the points are colored the same。

And the quotion space， which is the ball now is just the vertices of this poly， and for the a。

 there are 12 versetics on this shape。😊，So you can see that。😊。

This quotient operation will take the SO3 group， the discretized SO3 group from 60 elements。

To 12 elements， which represent the 12 veres on thepoli。So this is why this operation。

 this strategy can help us。Rereserve safe computation。

And we actually can show that by working on the only 12 dimensional features。

 we can still recover the 60 rotations of thepoli。😊，And this is bio permutation。So， basically。

If you if we order these 12 vertices in a certain way。

 we can put them flatten them into a vector and every rotation of the poly will result in a different permutation of the vector。

And therefore， actually， all the 60 rotations will result in 60 different permutations of the 12 vertices。

 Therefore， even our feature map is only of 12 elements。

 they can represent 60 rotations by taking the perutations of them。😊。

And actually here we show that this strategy brings very huge。Savings on the computational cost。

There are three tasks we presented here。There are from two dataset sets。

 one is a Mo 40 which is the object dataset with 3D cap models which we mentioned before。

 and the other is 3D mesh， which is data with real scans of indoor scenarios and the three tasks we experimented here is the post estimation of the objects's reclassification of the objects and the key point matching in the indoor scenario。

😊，And we compare with a baseline that is a S3 equivalentant group C applied on point clouds。

By applying this potion conversion strategy。We can bring down the memory consumption to just a fraction of it while bring up the speed in both training and inference to multiple times。

 Here the， the slash is training versus testing。 So you can see that in both training and testing。

 such a strategy can bring huge computational benefit。😊，And with this improved efficiency。😊。

We can apply this E3 equivariant learning to large larger scale point cloud and here we are talking about the Liar data。

 they scan the outdoor environment and they can be of a huge number and because of the efficiency improvement。

 we can now apply this equivalent models on this huge data for example。

 here is a place recognition work。😊，It's done by one of our labmate， Cynthia。In a recent word。

Actually， it's 2022， but because the publication is 2023。

 so actually it's the last year coreal paper。😊，So the idea， the place recognition。

 probably we've also learned this in the mobile robotic class。

 it's also called loop closure in action。😊，Which is basically when the robot comes to the same place。

 you know that it is the same place， therefore you can associate the observations together to correct drift and build a more consistent map。

😊，And this recognition can be done from images or La point cloud。😊。

But you can see that lighter based pressure recognition can be more robust to lighting and weather changes here Oh the left figure is a snow。

😊，It's a snowy weather with a daylight environment。

 and the right figure is with no snow and captured during the evening。

 And can see that you can see that the images can vary a lot。 However。

 the point cloud capture in the two scenario are very similar。

 So this actually is very helpful for robust place recognition。😊。

Then we applied the SC3 equivalent learning on this problem。That is by using this E2N。

 the method we just presented， the efficient S3 point convol， we can extract reliable descriptor。

On the Lila point cloud viewed from different poses。And here is a visualization of the result。

 Here you can see that the point cloud goes through different。😊，Rotations and translations。

And the right two figures are the features extracted from the point cloud。

 The horizontal axis is just the is you basically a 1 by 20256 vector。

 And we just plot the vector as a， as as a curve。You can see that。For an nonvariant model。

 the global descriptor can vary a lot when the model when the point call is transformed， however。

 from the Ivariant model， because the network is S3 Ivariant。

 you can extract a very stable descriptor of this point cloud under post changes。

I saw a question there's a question in chat asking if having Se3 Ivarian learning makes the LiDarR based scan robust。

Yeah， I think so I think that's so the light scan is just still scan like the lighter we do not deal with the data。

 the data is given， but the feature is learned from the LaD scans。😊。

Will be more robust under the post changes because of the equivalent property。

 the network can learn more reliable descriptors from the point cloud lightar scans that is under different viewpoint changes。

你 hope I answer your question。Yeah。对。So and also we also have another work also done recently。

 that is a panoptic segmentation on Lila point call。😊，So this task is more a semantic。

 a computer vision task that is to take sequential light scans taken by a vehicle， for example。

 a dragon vehicle， and then the target is to provide per point semantic classes and a temporal consistent per point instance ID。

😊，So it's basically a combination of sematictic segmentation， instant segmentation and object track。

 altogether， this is a。😊，Mo task task。嗯 on来了 point头。And in our experiment。

 we also show that the E2PN， this equivalent learning enable more accurate object segmentation tracking。

 benefiting the overall antic segmentation。😊，So in summary。

 we introduced how to learn equivalent features from some typical network architectures。 Here。

 we introduced MLB and CNN。😊，And actually， there are also other ways， like even based on M。

 there are other implementations and a lot of very good work in this field。

 And we did not introduce the， for example， the group the the graph。😊。

Neer networks and transformers today， but they are also equivalent counterparts of them in with different applications。

But even only with these two natural examples we've shown a lot of applications in robotics here I draw axisxus the left is a geometric application。

 the right is semantic application， and we can see that for example。

 the registration and the place recognition there on the geometric side to enable us to learn robust geometric descriptors from the environment。

😊，And on the right hand side， it's the semantic。Point of view， it can also enable us to， for example。

 better optimization， better panop segment。😊，It means that the equi learning。

 although the equivari is a geometric idea， but because we can separate the geometric variations。

 the post changes， variations out from the learning。 Therefore， it also benefits the semantic。😊。

Ficature learning for a neural network， therefore， it can benefit both geometric tasks and semantic tasks。

And also there's somewhere in the middle， actually somewhere is in the middle when we compare or combine the geometric tasks and sematic tasks。

 it can bring us even。😊，More interesting applications， for example。

 the object slam and the grasping work， I think they're very interesting because when when you actually。

😊，Combine the robust geometric learning and also combine the semantic learning that is you can segment the objects and you know that the same type of objects can have similar feature descriptors。

 therefore when we combine the geometric and semantic power， combine them together。

 they can be used to build large and useful robotic systems。And this is also。

 I think there's a lot of room to explore how we can combine this merits altogether。So。

What's next from what we already have today， What can we， where can we go like in the future。

 So here I come back to the figure I show at the beginning of this presentation。 That is。

 we want to treat the different observations and different effects differently。

 Like we can using these equivalent models we can preserve the symmetry so that we can deal with the different observations。

😊，Reliably with predictable behavior so that we can save the model capacity to actually learn the different entities。

😊，Therefore， a natural way that we want to pursue is want to expand the range of the cases that the symmetry preserving models can deal with。

In this way， more variations of the environment can be deal with in the principled way。

 and we can reduce the potential number of size of data and size of the model to deal with the other variations。

 for example， different entities。So for example， other group sym。😊，And today。

 we mostly talked about the rigidab transformations in 2G and 3D rotation and translations。

 But there are others， for example。😊，Homography， which is the projection of the 3D transformations in 2D。

Here an example is that here we show it， for example， the dig 3。

 All the variations on the right hand side， you can you can imagine that as rotating the three in 3D space and then map it to the 2D image。

 and this will cause like these variations on the 2D space cannot be explained by translations or rotations。

😊，Can we deal with this， if we can deal with these kind of symmetries。

 that probably can enable even more robust visual learning in from image to 3D perceptions？😊，Also。

 approximate equiance。This is to say， because the data are actually usually corrupted by noise and also occlusions。

 all these factors can result in the data that does not fully obey the equivariance。

 it is only approximately equivari。In this way， how do we deal with these situations？

And recover the equivariance or make use of the approximate equivariance without So。

 so when the when the exact equivariance relation is broken。

 can we still make use of this approximate symmetry in our models。And the third point， for example。

 is discover the symmetries from data today our models are mostly we define the symmetries that we want we design from the model。

 and we apply that to the design situation We know that the network will be equivalent to this kind of transmissions。

 However， this may not always be the case， we sometimes we may want to learn the symmetries from the data itself instead of designing that beforehand。

😊，And there are already existing work in this direction。

 but I think there are still a lot of opportunities in this field。😊，Also， so。

Since we are robotic researchers， so can we find more ways to integrate the symmetries in robotic applications。

 I think that's even more possibilities to explore。In this direction。Yeah。

 and here is all the figures that I borrow， all the visualizations I borrow from other paper。

 So here is a acknowledgecknowments to to all these papers， yeah。😊，So do you have any questions？😊。

So this is all my presentation today and all questions are welcome。Thank you。Thank you， Meon。

What a great talk。Let's see if you have any questions。爱民航。I have a question。

 I have a question for the ocean space you mentioned， okay。

How do you come come up with the idea that to divide it by。S， O2， rather than other。

Rather than other space like S， just just S space。IsSo how how do we come up with this idea Yeah。

 why do you why do you have the quotient space of S03 divided by S O2？Like like the choice。

 why we the choice， Okay， so actually， this is a pretty intuitive idea， so actually。😊，It's。

 it's right。 it's correct that we can choose differently。 Actually。

 this idea will also work like if you use different subgroups。

And you calculate the quotient and you can use that as a as a space to do convolutional here。

 the idea of using the quotient space of S2 is is actually pretty because this choice is intuitive。

Basically， because if you look at the ball and the。The idea is that。

TheTo describe the symmetry of the ball， we do not need the， we only need the ball itself。

 We do not need the ball and the rotations around the ball。Yeah， so that's the idea。 So basically。

 because if you want to， So if you look at this， for example， this poly poly。

The human can tell the post or the orientation of this poly by looking at this poly itself， right。

 by looking at， for example， here， Well looking at all the。Colors of these vertices。

 you can tell which orientation it is if you always the if you。

 if you if you will now define the top as the purple color。

 And now you just just need to find the purple color and the surrounding number colors to to determine the pulse of the。

😊，Ppoliolitician。So that's all we need。 We do not need all the 60 elements。 That is。

 we do not need to rotate the6， rotate it 60 times to tell which one is actually the poly。

 We only need to look at the vertices。 So that's just the starting point of why we want to do this quot representation。

 That is because we actually can tell the rotations by looking at the vertices of the poly。 Yeah。

 yeah， Yeah， it makes sense。 Thank you。 Yeah， Thank you。😊。

I have caution about the correspondence free paper you did。

So you use the decoder to handles the noise， right？

So is it decoder remove up on some noise of the pictures or just use。To generate the occupus field。

Because if you have a noise point call， then there should be a features features from noise。Yes。

 you're right， exactly。Exactly， so the decoder is used to help the help the feature to be more robust noise。

So the idea is， you're right that if the， if the input。

 because the input now is just is' not exactly equal to right。 There's a， there is a error。

 There's a some noise。 And then this noise will be brought into the feature space because of equivalent property。

😊，So in this way， there's no way that the fi will be exactly。😊，Yeah。

 so how do you handle those features， Yes， however。

 you know that although the equivalent exact equi cannot be achieved。

Because of this current property， actually， because there's input noise。

 it must be brought into the feature space。 However， the features can still be learned。 that is。

 it is not necessary that this guitar will be mapped into this figure。😊。

Like like we only this only constrain that they will relate by a rotation。😊。

But it's not restricting how the mapping should be。 And we know that different such mapping。

 like like if if this mapping is is maps to a very symmetric。呃。Slo point。

 that is where you cannot tell the orientations， then the the solution。

Can be can be affected more by the noise。 However， if you， if you can。

Encourage the network to learn the ph space that that that is that that preserves more of the。😊。

Aientation information。Then even with a noise， the difference between the estimated rotation。

And the groundous rotation can be made smaller。So decoder is not relevant to the SVD optimization。No。

 it's not okay。It is to basically help shape the feature mapping。be a more useful one。I。Thank you。😊。

是。All right， maybe we have time for one more question。I don't see any in chat。嗯 yeah。

I have one location about qualityian space。Okay， yeah， maybe I didt understand that。Perfectly。

 but so at we need to describe for one。Pos to for rotations， right。呃， could you pay question。

So we have2 features。Yeah， well for one feature， we do we need to discretize for the rotations that we give Yeah。

 we did discretize the rotation to 60。Which is all the rotational symmetries of this poly。

You mean for。啊。After we have a2 of pictures in a Qquiian place。Do we describe for one features。

For five nots like we did in a。Oh， do you mean， do do we。

 do we actually discretize the S O2 rotations to five rotations。😊，No from。

I think if I understand Dong Yang Seng， in the beginning you said for every translation。

 we augmented the circle features that you disretize。In this case。

 also every point will have these 12 rotations， right？Yes， yes， so every point。

Because it's as0 three times R3， my understanding is that they'll have this rotation like。Yeah。

 question correctly。 That's what you ask right， Yeah， that's correct。

 So if we describe from the polyhe purchase to。我听辛苦。嗯。😊，I maybe。

I don't know how makes the completion efficiency it would be described twice。For rotation。

So basically before， so if you were using a group convol。

 then every point or the point cloud is rotated 60 times or the filter， for example。

 the kernel filter is rotated 60 times when applying a filter and with this crucial representation。

 we are just rotating the filter or the point cloud 12 times。😊，哦，系先。Okay。

And from the 12 times rotation， although we are only rotating the future 12 times。

 but the output featureer can be used to discretize or to to distinguish 60 rotations。

 That's the idea。😊，I行。Thank you yeah， sure。Maybe's a good place to stop， thank you Minghan。



![](img/341d491193bced69bdabd83e2e7622b1_6.png)

Thank you。😊，Great talk and thanks everyone for attending the lecture。I will stop the recording。



![](img/341d491193bced69bdabd83e2e7622b1_8.png)