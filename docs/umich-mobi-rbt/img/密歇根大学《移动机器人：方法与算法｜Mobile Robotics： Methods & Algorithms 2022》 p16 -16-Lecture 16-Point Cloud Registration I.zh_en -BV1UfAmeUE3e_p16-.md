# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p16 -16-Lecture 16-Point Cloud Registration I.zh_en -BV1UfAmeUE3e_p16-

![](img/238dc488346d7aa00dd36d0f3fb69aa9_0.png)

Welcome to the first lecture on Point cloud registration， today's lecture is sponsored by Guinness。

I wish if you hear me， please reach out。😊，We have no sponsor。😊，But。For a change。

 we're changing to green。

![](img/238dc488346d7aa00dd36d0f3fb69aa9_2.png)

All right， very exciting topic。 It's a very interesting。Problem， a lot of people work on it。

 I have worked on it， and it's always fun to try and solve a point cloud registration problem or any type of registration problem in perception。

😊，In this lecture， we particularly focus on。A point cloud that we might。

Receive from different types of sensors。And these sensors can be。RGBD cameras， RGBD cameras are。

A type of depth cameras that will give us 3D points， depth of a point。

 as well as the familiar RGB image that we see。 So for every RGB value， we have a depth value。

 And this one to one correspondences makes it very nice because。😊，Ideally， we get a dense depth map。

 In practice， there are missing values。 There are noisy values。

These cameras are very good for indoors。 There are a few instances for outdoors。

 but the range is limited to usually 10 m。In practice， maybe5 or 6 mters。

 and illumination and sunlight can affect their performance significantly because they have to shoot。

They have to project light for sensing the depth。 These are active sensors in terms of depth sensing。

The very。Popular data set。It's not very new。 It's been 10 years， maybe。It's been around。 It's called。

To U M or to RGBD data。 This is from University of Munich。

There's a collection of sequences of RGB data， and this is a common benchmark for s and visual damage in this area。

You see an example of I N。Reconstructed scene， another newer data set is EthH3D。

They just said this is a slam and a stereo benchmark。You see， for example。

 this is a playground sequence in the middle。 You get the sunlight。

 This eumination can affect the appearance， the image。Significantly。

 and that makes it very challenging to track， detect features if it's feature based。

Or even register in the direct sense when we directly use the pixel values。

 which is a topic that we cover after point cloud registration。For the stereo camera。

 you we usually have left and right images and。We come up with an algorithm， too。Recover。

Depth value of a pixel。 It's a topic in computer vision how to recover the depth。

 But if you see a scene from two different views。And if you know that the relative transformation between camera lenses。

 in this case， just the baseline。Then we can recover the depth。It can be noisy in practice。

 There are a lot of methods for solving this problem。 One famous method is Elass。

This is a library for getting depth from。To pair， a pair of images。 So once you have the depth。

 this is effectively similar to RGBD sensing， although it's passive because you get the depth from two images as opposed to projecting infrar red light。

But altogether， you can think about them as depth cameras where you have color and points。

As measurements。So a lot of algorithms for they ignore where。This point cloud comes from。

You assume you have a measurement of that sort， and then you formulate your problem。Okay。

You can go to。

![](img/238dc488346d7aa00dd36d0f3fb69aa9_4.png)

Their website。

![](img/238dc488346d7aa00dd36d0f3fb69aa9_6.png)

![](img/238dc488346d7aa00dd36d0f3fb69aa9_7.png)

You can see a cool 3D registration。

![](img/238dc488346d7aa00dd36d0f3fb69aa9_9.png)

Example based on different methods。So historically， that's why in computer vision。

 they also call solving this problem a structure from motion。

Structure from motion is very similar to Islam。We， we want to recover the structure from the motion of the camera。

 Either in Islam slam， we might。Use。Features and other measurements that are not necessarily from camera。

 And we might target to recover the trajectory。Although we could just。

 we could aim to recover the treaty reconstruction of the scene as well。

So structure from motion is a little more specific。

 And it's referring to regional reconstruction using cameras。 this is now visualized using。

Probably one of the methods here。 You see the gap in the middle。When I choose the ground truth。

 you see it's complete。As much as it can be。And these discs。Not 100% sure， but it must be cful。

Some sort of disk surface patches that you。Create locally。

 and then the collection of that will reconstruct the surface for you。Let me close this。

Another type of sensor that we see a lot is Lidar Lidar。Unlike camera is an active sensor。

 it uses light beam and time of flight measurement to。😊，Measure the range。So it's an active sensor。

It works。 even if the scene is dark， it does not work with。The light in the environment。

And we don't have typically color， although we get something that is called intensity and that intensity is the reflectivity of the material that。

The lidA is getting lighter beam is getting reflected on。If the material is dark。

It tends to observe the light。If the material is bright。Then。It tends to reflect the light。

 So the reflectivity will be low and high respectively。

 This is negatively correlated with the intensity of the pixels we see in the camera。

So we have a data here in Michigan， NCLT， University of Michigan， North Camp。

 long term vision and wider data。You have LiIDar measurements across the campus。And。

I think a omni directional camera。The ground truth is actually constructed by。Taking sequences of。

Data from different runs on different days and accumulating them into， you can see here。

A giant graph that vertically you can imagine its time， right。You go different days， and then you。

I also established loop closures for different days， for different locations。

Then they processed this offline， and that generated the ground truth。

 The accurate trajectory that you see when it's overlaid on。The Google map。

 So this was from Professor Eustace's lab。In perceptual robotics lab here in Michigan。

And the data that is available online， you can download it。Another newer data set。

With the same flavor， its collected in Korea。By Professor Ian Kim's group。It's similar。

 but the platform is new， maybe five years，10 years difference in。The time they collected the data。

Lesson 10。And the city is different。 This is Korea。 So it's not like Michigan campus。

 So if you like to look at different style of urban areas， this is a good data set。

So if you can register Liar point clouds， you can reconstruct the scene。

 So that's one good motivation。 you can localize。 You can track。Or at least it can be part of。

A perception system or a s system， is point cloud tracking。



![](img/238dc488346d7aa00dd36d0f3fb69aa9_11.png)

So what is a registration problem， A registration problem refers to。

Finding the geometric relationship between two sets of data。 in this context。

 data typically comes from a sensor。Such as lightA or depth camera。

It can come from remote sensing or aerial imagery。 That's also possible。It can be 2D images。

 That's also the type of registration， image registration。 But in general。

 we want to find the geometric constraint or relationship and that。Is usually a transformation。Now。

 in the context of robotics， usually。We receive a point cloud。

 and then we want to register to maybe another point cloud from a previous time step or maybe a map that you're tracking。

 So it can be point cloud to point cloud as in the sense of frame to frame or it can be point cloud or frame to map registration。

 So anything is possible in this context， depending on。

Different ideas and frameworks that you might want to build。 but at the end of the day。

 you are registering two set of points for finding that rigid body transformation in this context。

So you can categorize the algorithms in。Several。Directions。

 one is the resolution of the registration。 Some algorithms try to。

Find the transformation in a rough sense。 It's a course registration problem。

 And these are usually good when we want to get something quickly， maybe as a prior or。

Some rough idea to solve a problem。 That does not require。

We very accurate registration for reconstruction。For example， for place recognition。

 I might be it might be sufficient to detect it the same place。

Roughly recover what's the geometric relationship of the image that you observed maybe one hour ago and the different view of the same area that you are observing now。

 What's the transformation of camera between two cameras at these two different times。Maybe it's。

5 centimeters off， maybe that's not a problem。There's no reason to。

Aim for solving that in one pass of frame to frame registration。Fine algorithms， on the other hand。

 try to。Really get accurate reconstruction。 When you visualize。

 you really want to points that truly supposed to match。Be aligned correctly。 For example。

 if there's a wall， you don't want the wall to be intersecting。 It needs to be。Perfectly aligned。

 So that's the goal of fund registration algorithm。Regardless of how well they can achieve that。

 that's the aim in this category。Now， when you get data， there are two。Ideas。Which was the case in。

Filtering as well。 One idea is called direct， Direct methods， use raw observations。For example。

 part of your filter could consume。The point cloud from widerer to localized。

Indirect methods use features。 For example， a common filter needed features。To localize。

It was not working with。APo cloud directly rate rates in the occupancy map。If you look confused。

 go back and try to localize using E filter with the occupancy。You can， but。It's very unusual。

 And you need to work with features that are not very distinguishable。

So when you solve data association， all the features are the same。 They're just points。

 It's so easy to make mistakes。So indirect method， we mean features that are。Ideally invariant。

 in some sense， for example， sift。Or self or orb。These features tend to have some properties。

 such as scale invariance or rotation invariance。These properties will help us to。

 when we observe the same scene from different views， we detect the same features。

That will assist the registration。example of creating。What will be the example of a scaling？

Scaling variance， because the camera。The monocular camera， when you see an image。

Depending how far you are， the building， for example， or car can be very small or very large。

And when you extract feature， you don't want， for example， a corner of an object。

To depend on data scale， how far you are at the end of the day， it's the corner of some object。

 You want to re detecttect it。I could see what could be a feature which is rotation in the。我买过。

Sft is。Scaling variant。And it's one of the most successful handcrafted features。So today。

 people like to learn features automatically。 And that's what they try to do in deep learning。

Before deep learning， the features were handcrafted using some。Sequence of mathematical operation。

 For example， you could take the gradient， take the。Laplian of the Hessian or some other ideas。

 Laplaceian of the Gaussian， sorry and。Some other methods to work with the direction of the gradient。

 the magnitude， maybe and。A combination of them to。Detect the salient part of the image。

With the goal that you can reobserve it， because if you can't reobserve it。

Then you do not know the association。And we will see why that's important。The local and global。

 some solve， some algorithms find a local solution。And that's what we talk about today。

There are other algorithms that can solve the problem globally。But usually。

 aren' there certain assumptions and。Given setup up， they can do that。

And the trade off usually is that how fast you can solve it。 Some algorithms are real time。 Ideally。

 this should be real time。If it's global and it's too slow， it will limit。

The applicability of the method for any real time operation。

So let's formalize the point cloud registration problem。We have a set of 3D points。

 and these points have three coordinates。Isn't the pre space？Every X， I has。3。Coords。

The action of a rigid body。We define it to be this way。This is not new。

A rigid body transformation rotates the point and then translates the point。 Now。

 the reason I'm using that because。The points are not in homogeneous coordinates to just keep the notation。

Consistent， we do this otherwise。You know by now that we have to。

Work with homogeneous coordinates if we're supposed to do matrix multiplication。But ultimately。

 this will give us。R。X plus p。So the geometric constraint that we talk about it is， in fact。

An element of the S E 3 group， or the rotation part is an element of S O3。

 and the translation is just the 3D。Rector。So this transformation is the parameter that we want to estimate。

 If we know this parameter， the registration is solved。

 And it turns out this parameter is an element of a league group。 It's not。Just a vector。

When we formulate the problem， then there will be an optimization on L group。

We define two point clouds。 The first one is called the target point cloud。

 The target point cloud is considered to be in a fixed reference frame。

This is a point cloud that is the fixed frame， and we want to align to it。The second point cloud。

 we call it the source point point cloud。 The source point cloud is the point cloud that we apply to transformation。

Such that， after rotating and translating its points。8ight。Is aligned to the target point cloud。Okay。

And we are after this transformation。With this setup。We can talk about。We。

Maybe one of the most famous algorithm in this area。I had a quick question about the two trends。

For example， we have a robot。It helpsps you with scans。Collecting。Like lightar information。

It's a task of making sure that he's subsequent。The scan aligns with each other the same as aligning into a fixed frame or there subsequent things where I pose one。

 I get a scan， I want to match that with the one that I get a post to and then finally I want to make sure that。

Scans that matched together finally aligned。Your question is that are we also concerned with？

A sequence of registration and then making sure the trajectory is consistent。 We are not。

 We are just talking about aligning two set of points。

This can be a building block of that s framework that you're describing。

We are just focused on this specific module on club registration。I was going to ask you。超解。本事啊。

I don't know。I'm just asking if this is like a localization， my problem， or is it a mapping analyst？

The question is if this is a localization problem or the mapping problem。That's not all we call it。

 But if you want to cast it in one of these two ideas， because in localization。

 the map is given you're after the post in mapping the。Projectory is given。

 We want to reconstruct the scene。I would say we're localizing because we're trying to find this relative motion。

It is possible to。Get something that you call it lighter odametry or visual odametry or ourGdatry by accumulating the sequence of。

Registration and rigid body transformation that we recover。But it will be odatry。

 because there is drift。Unless every single registration you do is perfect。

It is impossible in practice。 It will be an ometry and needs to be combined with other techniques in the context of Islam。

But because we might get odatry out of it， you could。Classified in the localization category。

 the point clouds are given。As measurements。So first idea that it's good to learn as。

A fundamental method that is very common in literature。So you know how it works and。

When you see its variant。You know， the foundations of it。

 You can focus on the little idea that maybe is trying to extend this method。

So the main idea is that。Step one， find the association between two sets of points。And step 2。

 given the associations， solve some sort of optimization problem， too。Find the transformation。 Now。

 the question for you is that， why do we need to find the association。I have。Two set of points。

I want to register them。There's a rigid body transformation that perhaps aligns。

This part with this part， maybe。Okay。Now， whether you solve for T or inverse of T is not very important。

Is it because we assume that there's？share。association for。

Kind of support that assumption that we made to the common structure。

Allign points that share features。Because there is an underlying structure here that these point clouds share。

 That's true。 If there is no underlying shared structure， there is nothing to register， right。

 But why do we need to associate points with points。

The association means that I want to know what is the corresponding point。Here。And let's say。

 so target point cloud。With another point。And the source point cloud。

Because if you're trying to solve for say。Tranform。在会时间。Yeah。About the transformation interest。Well。

 the question is more basic that do we know what corresponds to what here？

The sensor is giving me a point cloud。 I move。 I get another point cloud。We don't。

So there is no way to know what point corresponds to another set of points。

Some prohibit of the symmetry。There may be some problems with the association of the shop。

Symmetry can cause problem as well， but ignoring everything here。

We do not know what point corresponds to another point。 Now， if you do not know that。

 how do you formulate a residual for the optimization to begin with。You do not know。

How to define a distance metric， You can only calculate the distance。

Between two objects that you know， you want to measure the distance between these two objects。

The sensor will now tell you this。 The sensor only gives you point cloud， you move。

 you have another point cloud。Now， if you do， let's say a nice setup。

 you can simulate that if you do know。The perfect correspondence is between two set of points。

 and they have nice overlap。You can solve the problem in closed form。 And that's the。

Historical solution is called Hors method。If you。Nan。Asciation， I will give you。Is skiping it here。

 if you're interested。I'll describe the method outside of the lecture。

 but the idea is that centralize this point cloud around the mean。

 calculate the cross covariance matrix between the two point clouds。That will give you。

Because you have。And by three。And the other point color is also n by three。

 so knowing the association means that you have exactly the same number of points in the source and exactly the same number of points in the target。

And then you calculate， let's say， a cross covariance matrix M， it's going to be3 by3。

Do a SVD factorization， and you can recover the rotation matrix。 Once you recover the rotation。

 you go after recovering the translation by registering the mean。

 So that's historically the closed form solution。And。We come to real life。

 We don't know the association。Then was then ICP came along。So two set points might have。

Different number of points。 Let's say N1 and N 2。So at the step that we。Associate these points。

 we search for。Nearest neighbors。Basically， given current transformation guess。

So for every point in the target， I will try to find one association， closest point。

At that iteration。Then that will lead to having the exact same number of points in two clouds because I ignore the rest。

 I only keep the associated points。Given the association。Then， I can。Formly， theyre residual。

 define some distance metric， and then minimize it。

And the obvious distance metric is just the Euclidean distance between two points。

So that's why we call it iterative closest point。 Now。

 this is not going to recover the transformation。 So we iterate。 We repeat this。

Until hopefully fully it will convert。On with perfectly。系电嘅。Very good question。 How do we get。

The initial guess， we don't know。Rely on your engineering intuition。If you have another sensor。

Like I am you， maybe an ometry， you can。 But if you just have the camera。Identity， right。Now。

 a lot of time when people get results on these trajectories because they're sequential。

 they use the previous registration result to initialize the next one。

So you always correcting a delta and you go forward in time。But at the very beginning。

 you start from the identity because you don't know。The solution。So what makes it easier in practice。

 you can use a lot of ideas。 but if you isolate a problem。

It's very challenging because you do not know a good initial guess if the problem is nonlinear。So。

 step 1。Apply the transformation， which in the beginning， it will be the identity。

 if you absolutely have no idea。What the transformation might be。

Find this means find the nearest neighbor index， right， once you。Search at this point。

 they don't necessarily have the same number of points， but you find a set of associations。That now。

Using these indices， you can find have the correspondences。 Then you can define the residual。

And the obvious option here is to solve at least the squares problem。However。

 at least the squares aren't S E3。 That is why we had to go through it last time。

The performance will be very poor。 if you do it on。Using Ouler angles。

 And that's where you get in PC L， Pla Library。 And I'll show you what's the difference。

If you do it in legal group， if you don't do it。So the sum is over associated point。 Now。

 you find the optimal solution。Then you go back next time。This T is no longer identity， right。

 It's just some T1。You move the source point cloud a little based on the guess then you。

Sve for the nearest neighbor again。So every time you update the transformation。

 these nearest neighbors said， will change。So by nomi， is this correct initially or？

Anytime along the way。 And that's very dangerous because you might just fall into local minima。

 The symmetry could be a problem if there are similar parts that the point cloud can get trapped。

So altogether， this works usually for。With the assumption that the difference between  two point clause is not so large。

This method works。Now， in this same， in this。です。Basic version of it。

We don't usually implement this version of it，We've worked with something called GICP that's more common。

But you cannot expect too much from it。 If the transformation is large， this is a local solver。超。そ。

二せてこ。Step one， finding the association， solving the association between two set points。This eye。

 the set of indices。So I know later for in terms of， let's say， this residual。

Which points firm target and source to call。To evaluate this residual。Right。Then。

 I'm going to tell you。A method for solving the association。Obviously。

 don't want to do exhaustive search。You do。You don。You're a computer scientist。

Or maybe exactly a computer scientist implement exhaustive said。When they're lazy。

And tell other people thant do it。So how do we calculate this using the Gaussneotone， right？

We can use the Gaussne method to solve this problem。Or Lebemarqu。What do we need。

 We just need to calculate the gradient。Do remember the last part of the previous lecture？

How do we get the gradient？It's not very difficult， we。

Because we're dealing with rigid body transformation。There's no T plus Delta T， right。Zli T。

Exponential of Delta T。Now， in the context of optimization， you're welcome to。Use both。

Left and right。But stick to one， pick one and just be consistent。

 Don't derive the Jacobkui using left or right。 And then later in your algorithm。

 you're integrating using the other one。 that that's not。Recommen that， you might come back say， oh。

 look， it's working。It's not correct， obviously。So we can use some simple algebra to derive the Jacobian。

 and there's no need for calculus。Perterrb iss easier to do it from the left， perter。

 the transformation in the residual what we get is。The target point。For a single residual term。

 for two associated points is the target point minus the transformation times the source point cloud。

Do a first order approximation of the exponential map， which is one plus。You you see hat。

And then just multiply them。 The first part is the identity。 You get the transformation times。

 the source point cloud back tab will give you the residual。That you see here。Whatever is left。

 that's supposed to be。Which is here。Some first order。Term， caused by that perturbation。Right。

 in the same sense of。Taylor expansion， you can call it the Jacobubian。 But here， we're using。

TheFirst order approximation of the exponential map。 I'm also defining Z to be。For simplicity。

 the transformation time is the source pointin cloud。So now this is， of course。

 not something we want to work with because the matrix is the variable。The non part is the vector。

 We should flip the。Order， therefore， the Jacoban is the knownun part。

All we need to do is find a matrix when we multipied it by the twist as a vector。

Gives the same result as the left and side。To see what matrix will produce the same result。Tist is。

Some is0 three part， sy matrix matrix， and a translation part。

Multiply this matrix by a vector that the action of it will give you， of course。This， right。

We have a negative sign。 it's going to be negative of。Pe skill times Z。Mineus rh。

 rh is the translation。Are you used to omega and V， maybe It's the same thing。Well， you know that。A。

Sc B is negative of B， S A。Right。So the negative sign will disappear here。The translation remains。

And。We have the Jacobian。 So it's just the rearing。 And you can。

 you can formalize it in state estimation book。 There is an operation。Like this。

 there's always build map。Solve this problem for you。

 You'll have a formula of going back to the Jacobubbian like I'm doing it。 But if you don't remember。

 it's just a direct calculation to see what's the matrix。Alright， so we have the Jacoban。

 and you have everything to implement a Gaussuter algorithm。

I'm seeing your confidence is leaving the room。What's the question， Which part of it is confusing。

I have a question for the today。你看三照来看。When。Yes。Which step is confusing。

 we'll just go there and continue。Re fast line here。Okay。So I am saying that negative of。

You you see had times Z。Equals negative of。FeQ， Road 0，0。Times Z， now。

 because I'm not working with homogeneous。 I'm just defining this action to be。

But isn it that4 by call？It is。 That's why I defined that action of T on a3 vector to be R Z plus P。

If we would work with homogeneous coordinate， it would be， but that's just the row of zeros。

 It's redundant， yeah。Now， you， you well， yeah， you， you can work with homogeneous coordinates。

 but you will get extra zeros。I am。Working with three vectors。Here， right， So this dot。

 I'm defining it to be in the same fashion as T times Z。That's why I'm not putting a dot here in R。

 because art is 3 by 3。And z is 3 by one。So then we don't need the dot。Right。So， you can。

Just get rid of everything here。Now， just like the way you implemented the invariant columnman filter in your code。

 you can manage the calculations。In different ways。Now， is it clear now？So Jacobubbian is。

 and and remember， Z is t times。The source point cloud， right？

So the Jacobubian does depend on the transformation。 each time we have to reevalu it。

At every iteration。So how do we get the nearest neighbor points？A particular algorithm that。

Is used in practice is。Called K D3。 K D3 is a data structure that partitions the space into different regions。

And it allows you to。Search for nearest neighbor or query the nearest neighbor in。

Log n as opposed to linearly searching exhaustively over all possible combinations。

And linear is going up like this， right。The log。It's so much better。

As the number of data points grows， you will see the advantage of this login。

So the library for that is called Flan， this is a very one of the common libraries。

It has a very efficient。Implementation for fast approximate US neighbors。 It's not exact。

 It's approximation， but it works very well in practice。

A nice headather Roly Libr in C++ is none ofL。That you can get it from the Gi page of professor。

Blanco。He is the developer of MRRPT， the Open source C++ library for robotics。

Lots of good algorithms in that library。So this is a header only library。

 So it's very easy to include it in your package。 and you can just load it， and。

Use it for nearest' neighbor search。Similarly， in Matla， Python， Julia， you can find libraries to。

Solve this problem。If you want to read more about it， you can go to point cloud library。

 There's a documentation here。 You can look into the Kd3。AI that they provide。So what we do。

 basically， you construct。They cater to reusing。Let's say your target point cloud and then for every source point cloud you have to query。

They close this point。Or the other way around。Probably you wantan to construct it for your source point cloud。

 if you're doing it in sequence， because next time your source will be maybe the target。Wait。

 we want to reuse it。 Which one we should do if you have。Frame one。2，3。You have target source。

 target source， target source。And next time you。Your source becomes the target， the new target。

 right if。They're sequential。So you can do it for both， right， but you save one of them each time。

So every time you only need to construct with one of them。

So let's visualize in a cartoon how this ICP is working and why。

It might not be the best method in practice。 Imagine I have a blue point cloud。

 This is my fixed point cloud， and yellow is the one that I'm moving。

I need to find the nearest neighbor。Gemetrically， now nearest's neighbor is also with to some distance metric。

 It doesn't have to be with to Euclidean distance。But that is， of course， the obvious choice。

 and that's what we do in ICP。If you go with the Euclidean distance。

This blue is the nearest neighbor to all of these points。So the residual is a value that。

Such that all of those points get matched to that single point。

At this current transformation that we have。And maybe you have some other associations。

So we get closer。After solving the transformation， right， we move the source point cloud。

Then we solve for the association again。This time。Maybe these two are getting matched and the other two are getting matched to a single point again。

Remove。And you can guess the rest。So it was working， but。Now， imagine this point lot has 100。

000 points， 10，000 points， and it's a very complicated shape。

These associations are not reliable at all。The way it's getting。They're getting matched。

And they can guide the optimization the search to。Any direction that is impossible for us to guess。

So G， ICP tries to make this better。 There are some other algorithms in between， but I'm just。

Moving to。The myist than something that you might implement in practice。And it is used in practice。

So we want to work with a probabilistic model。Consider。H。Range measurement from your point cloud。

To be noisy。Assume。tinyin covariance for that point。 For example， the Liar point cloud。Usually have。

 if the lighter is good， you might get 5。Standard deviation of 5 cm， something like that。

steerory camera is going to be very large。 The farther you go， the。Point clouds can make a wave。

That looks makes everything distorted。But let's say， we assume some。Noise distribution。And by that。

 we mean the actual measurement， right， Master of the time is within that。

Covariance eps that the noise distribution is describing。A Gaussian notes。Now， what we want to do。

 we want to。Come up with an idea that describes the structure of the environment better。

 So there is an assumption that if I am registering in a room like this and there are walls。

There is no need to assume that this can be a curve surface。If I know this is a flat surface。

 how can I geometrically describe this？So it turns out if you。Do the nearest neighbor search。

 And let's say you pick 20 nearest neighbor of a point， right。And nearest neighbor of a point。

And then you can calculate the empirical covariance， the sample covariance for that point。

So that point itself is the mean。 And with this empirical covariance， you are。

Describing the local shape。Of the Point Club。Whatever that ellipse is covering。To make it flat。

We need to make this covariance almost degenerate because from 3D， it needs to become a plane。

And the the direction that is normal to the plane。It's supposed to。Be very small。Now， why。

 Because there's an assumption that there is a flat wall， therefore， one of these。

Eigenvalues of the covariance must be much smallerer than the other ones。

So due to eigen decomposition for the covariance。This is a。3 by three， diagonal matrix  of。Ienvalues。

And set the smallvari， set the covariance that corresponds to。

The normal direction to a very small value。For example，1 E。-3，1 e minus-6。

Now this is the smallest eigenvalue。 That's how you know it。Usually。

 linear algebra methods sort the ionigenvalues for you。

We'll go through one example code I'll show you。The first one， if it， if that's the case。

 the first one is the one you want to。Set to a smaller， smaller value。

 So no matter what shape you get from the empirical covariance， you make it degenerate like this。

And the effect of that is that instead of point to point matching。We are matching。Individual。

Tiny Gaussian distribution to the Gaussian distribution。And this way of making them almost flat。

So as a result of that。The local shape。Is。Better describe， because the point is not able。

 It just doesn't have the capability of describing。The shape。

By its very definition is's just the point。Now。We always avoid associating this vertical wall with the horizontal wall if we can describe this the structure to be this way。

And that's， that's why this is a more。Powerful method， right。

 So this covariance is with a slide in a way that obviously， when it's vertical。

The distance is large between these two covariances， and the distance will be。Will be what？

And my heart nervous is distance。A weight that distance by the inverse of the covariance between two Gaussian distribution。

The notation you see is usually like this， although this is not。Universally accepted。

 But in a lot of robotics and perception papers， you see this。This means r transpose sigma inverse。

Right， so。Pay attention to this inverse。Sometimes people also defined it using。Don't know。

 maybe it's an optimal control problem。 They tell you this is our transpo QR。So。

Pay attention but be flexible。 This is by up to definition。So in this lecture。

 we defined a way to be the inverse of the covariance。So this is a weighted norm。

 it's no longer a euclidean norm。Yeah why。T确。Making this kind of assumption。

I still don't get why I will provide this kind。The question is， why do we need to assume？

That this is a good shape。And the answer is， we have no reason。 That's just the choice that。

In a structured environment， we think that's a good。 This is a good idea。

 because when you have a wall。You don't want the measurements that are coming from that wall to move in the direction ortagonal to the wall。

They should just slide within that plane that they're supposed to be。This assumption。

Is reasonable If you assume the environment is like that。 If you go to uninstructd environment， this。

 this assumption。It's not clear。 It will do so much for you。And you won't。But on roads， for example。

 in the city， urban area， it still is a good assumption。

Because of the buildings and broader structures。So what are the samples of this back？

She guess wait how accurate the sample？年播的。Consider。The question is。

 what's the region to consider for computing this empirical covariance？That。

 that depends on many things， including。How much time you have for calculations？

You don't want to go too far because then that will make the covariance too large。

It's supposed to be a neighborhood。 But if the point cloud density is not high enough。

 that makes it very challenging because the neighbors are far。And that。

Creates a covariance for a large region。 That's not reliable， so。Given。

I'm saying a reasonable density， but something that then visually you look at it。

 it describes the shape of the environment。Maybe 16，20。24。

 something like that might be a good choice。Number of points in the Kd3。

 you want to query how many points you want， right。You probably also want to query within a range。

Not to be too far。You don't want two points to。 You don't want one point to be。

This on this wall and the right wall and the other one on the left。

 even if they are the nearest neighbor。That's not the goal here。来。这个的意思不变定。啊。M this意。

Can you repeat the question？应该是可以。Next page。That previous page。So the covariance here is。

The sample covariance。We're clear on that part。 we find the nearest neighbors。

Ignoring all the technicalities and challenges in practice。 let's say we can do it。And。

I am saying that we can do an e decomposition of。Find the iigenvalue of the covariance。Right。

 covariance is a symmetric。Positive semi defite matrix。 so eigenvalue are either positive or 0。

In any case， you can， because it's symmetric， you can solve the een。Decomposition problem。

So this lambda will be Lada 1， Lada 2， lambda 3。Now，Again。

 because there is an assumption that we are dealing with a structured environment， therefore。

There must be a direction。The this covariance is。Inflated much less than the other directions。Right。

If the assumption is satisfied in practice， therefore。

 the smallest eigenvalue will be the this direction。

Because the eigenvalue will recover the some principal directions for you， right。

Then find the smallest eigenvalue and set it to even a smaller to make it make sure it's almost flat。

Make the normal direction to be almost flat。Then the covariance will。Shrink like this。

And you can leave the other ones to one or。Something arbitrary or whatever they are。One。

 obviously depending on the scale of the problem could mean。Something like meters or。知道。Smallest。

Right。It's not as digig value。So this are is distribution to go to the desks you showed in the second？

Thedi in the second slide for the environmental reconstruction。嗯。😊，Not exactly that。

Trey reconstructionconstruct and we showed with disks。 Those are called ceals。That's a。

Type of map representation is not。Well， in the literature is its independent of this context。

There's no reason to tie them together。That's just defining a local patches of surface。

For visualization。But this is a way that we describe。source。So in this scenario。

 or at least in this figure。We do this for both point clouds independently。We'll see it in the code。

calculatedulatingです。Every step， want the inverse just reduced to the inverse of that window up？

So we've actually this will speeded up there。Yeah， if， if we're going that way， that's right。

 we can invert the matrix more efficiently if you want to reuse calculations。

Because if you can decompose the matrix， you can just operate on the eigenvalues， right。So。Now。

 GICP has a probabilistic notion behind it。And in that sense， it。

It's really solving a maximum likelihood problem。 The residual， which is。The difference。

Between your target point， minus transform source point。First of all， we assume that。Each point。

Is distributed with some。I'm abusing the notation a little because I'm not using the mean here。Right。

This must be， of course， the mean。With some mean value and some。Covariance。Similarly。

The source point cloud is following a mean value。 The mean is just the 3D points What you get from the point cloud。

The covariance is what we just described。 So for every point。We need to evaluate that。

Hand doesn't write。I didn't know you can lock the tube。Okay。Stop it。当上面。What is going on。

My finger words。嗯。So the source point cloud。Also has。I have an idea。

 let's close it and open it again。

![](img/238dc488346d7aa00dd36d0f3fb69aa9_13.png)

It's the best idea we have in。

![](img/238dc488346d7aa00dd36d0f3fb69aa9_15.png)

Software assistance so far。

![](img/238dc488346d7aa00dd36d0f3fb69aa9_17.png)

So similarly， the source point Club will have a covariance， the residual is the difference。



![](img/238dc488346d7aa00dd36d0f3fb69aa9_19.png)

嗯， tell you。Kicks me out。呵呵。😊，So the difference is。Now。

 this residual is the difference between two points that are normally distributed。

 What is the distribution of the residual。Yeah， because we can show that the mean is whatever you see。

 the residual itself， right。Its the difference between。Basically。

 the residual is an a function of these two points。Right， so。

Mean of the residual is the target point minus t times the source point。

 the covariance of the residual。 Well， if you calculate the covariance of both sides will be the covariance of the target point。

Because。Reume。Sour and target points are independent measurements。 So if they're independent。

 it will be the covariance of。The target point。Plus。

 the mapped version of the covariance of the source point， because the source point is， of course。R。

It's not cooperating。Maybe we do need to lock it。On Dboard。

 the tool lock essentially like keeps it selected throughout your writing。I don't know what you said。

 but it helped me， it's fixed。I liked it too。 and it's working。 Thank you。😊，So。

 I totally misunderstood。The meaning of that luck。Allright， so。

You only know the value of a privilege when you lose it。We。

Transformation part is something like this and。哪位。At this point， this is very easy for us。

 We know that this is an a transformation of a Gaian distribution。 It will be。Art， sigma。

 are transpoposedse。And the translation part will not contribute to the covariance。

So the residual of every matched point also follows。And independent for the K term， right， Not all。

 all residuals are not correlated。 They're independent。So every residual will have a mean。

 which is we see here。And a covariance， we define it as C。Now， because this is Gaussian。

Multivariate gaussian distribution。Which you have exponential of。Negative of。1 half。

X minus muu transpose sigma inverse x minus muu。Right。What happens if you take negative log of this？

Now， if you want to maximize this likelihood， this residual distribution。

Which describes how likely is these 2。 cloud to be matched， if the transformation is correct。

 it will be peaked。Right。The Gaussian distribution， that distance will be small。 Therefore。

 the exponential gets peaked。 And that's the maximum likelihood problem in its statistics。

No but it is so much easier to work with the log of it because it will behave better when you optimize it。

Because the log is monotonically increasing function。

 we will not change the solution of the optimization problem。Now， we don't want to maximize。

 Usually we want to minimize。That's the guess。Basically a customary thing to do。

 negative to turn the maxization to the minimization。

So the maximum likelihood problem for a Gaussian distribution is the same thing as。

The least a squares problem。 If you take the negative log of it。So they're the same thing。

The probabilistic notion of least the squares is the maximum likelihood。However。

 maximum likelihood problem is more general。 The likelihood need not to be。A Gaussian distribution。

 If it's Gaussian distribution， it corresponds to the least the squares problem。

So that's why you see that we can just write all these terms。Of course。

 the residual is conditioning all the given data。 You can write it like that。

Take the negative log of it。 Ultimately， we are solving this。AtLeasase the squares problem。

 The only difference is that the distance metric is changed。Right。

The distance metric is no longer the Euclidean distance。

 This is a Mahalloous distance between two points。In other words。

 the distance is weighted by the covariance。Which in this sense， is calculated。Using this formula。

So we know at this point that that's a better formulation。 and this probabilistic notion。

Helps not to trust points just based on Euclidean distance。

 but also taking the uncertainty and the shape。Arada point into account。You solve this。G ICP on S 3。

 This is a simple problem collected using a Kinect camera。 You can access data。 It's a Matlab help。

 It's a room。 You have the Kinect。 You see the。Knda here that。The panda is。Fortunately。

 reconstructed correctly and。That's how， you know it's correct。 right， You look at the scene。

Quallititatively， you see that it's reconstruct。 This is called a qualitative evaluation of the method。

 Quaitly， you need to know the ground truth transformation and see what's the error You somehow with some metrics。

 we can evaluate the error。So just evaluating quantitatively。

Might not be satisfying because at the end of the day， you want to see。

What does the small error mean， Is it correct， or iss just the number is a small。

 but the walls are not aligned。So it's important to show both of them。

So the iterative closest point is very common in robotics。That's also known as point to point ICP。

Theres the next version of death， instead of。Well came earlier。 That's called point to plane。

 The point of plane assumes that。Around each point， you assume a flat plane。

And take the distance of a point to that plane instead of point to point。

That's one level better and its still sometimes we use it and a lot of methods that solve the problem globally work with point to plane distance because when you switch to the GICP cost function。

Because the covariances changes the weight of the distance changes as the transformation changes。

It makes it very difficult to。Salver within the context of global solvers that we see in the literature。

 That's why they aim for a point to plane。ICB。So generalized ICP is what we talked about。

 So the year is， see， these are from 90s， 2009， GICP was published。

There is another class of problem called NDT， normal distribution transform。

 These are also interesting methods that they vize the whole scene。And。Within each boxel。

 there' is a Gaussian distribution， normal distribution。

And the overall cost function is trying to match this distribution without solving for association。

So what it is。When it was published， it was novel in that sense。

 and is was trying to bypass that association part。ItSometimes it works well， sometimes it does not。

But this is also an interesting category of methods。Next time I'll talk about。

A continuous registration method that will generalize。In theory。

 is generalizing all of these methods。 You can't reduce it to any of them。

So you have all sort of extensions， that tons of papers that you can search。

 They usually build on some of these basic ideas。What are the challenges？

Crespondences within two points。 Po point clouds are unknown。 That's a big challenge。

Usually need a good initial guest to find a good local minimum。

Partial and unknown overlap are also very。Important challenges。

 because when you observe a scene and move。There is a part of these two point clause that they overlap。

Then there is another part for each point cloud that they have nothing to do with each other。

And we do not know what's the inlier process， the part that they match an outlier process。

 the part that they don't。Solving that。Problem can substantially improve the performance。But again。

 that's something that it's a question of whether you should solve that or you find a method that can handle it。

Right right是。It's not clear。Which one we should do first。There are some recent methods。

 They estimate the overlap。Predtor is a paper that uses deep learning to estimate the overlapping part of two input point clouds。

 But deep learning methods are usually。Consume a smaller point cloud。 They work with。

Thousand points or a few thousand points。We can handle a lot more， using non deep learning methods。

They use use a lot of memory in deep learning， but。Hopefully， as we go forward， we can。Now。

 bring both of them into together。 and then you。And also use less memory。But also。

 these algorithms that they don't use deep learning are general。Up to。Some tuning their general。

 with deep learning also relies on your training data。

They're having difficulties to generalize to data sets that they haven't seen。

Another challenge is that they work on a lot of data set that are designed for computer vision challenges。

 object level。An airplane and a car。 This is very different from a scene that a robot is seeing。嗯。

It seems that。There's a lot more work to do to extend A And D most successful algorithm to the actual robot perception problems。

That's unfortunate， right， unfortunately。The best performing algorithms of computer vision leaderboard are usually are not directly。

Applicable to robot vision and perception problem。Sensors have limited field of view。 They are noisy。

And。Some other things that you will know if you work on the problem。

So if the problem is a smaller scale and offline processing is possible， you can， of course。

 try many initial guesses。Let the algorithm run for a long time。

Or you can formulate a problem to simultaneously solve for a permutation matrix that describes the association between two set points。

Ultimately， it's a reordering of two set of points so that they correspond to each other。

 So you can solve for a permutation matrix。Which is going to be an n by n perm mutationut matrix。

And is the number of points。And the rigid body transformation。Now。

 you might not know what permutation matrices form as discrete。No， form a subgroup of。

This great subgroup of S， O， N。A type of rotations， but。They're more particular。In their entries。

Don't describe a continuous rotation of an object， discrete。Change of configuration。

 such as exchanging rows of matrices and。Columns of a matrix。

That's why you have for a permutation matrix P transpose P is identity。 This is an autoagonal matrix。

A perermutation matrix is always constructed from the identity matrix。

by changing its rows and columns。A particular example of solving the problem globally is go ICP。

This uses branch and bond method for。Optimization， and it is。Slow。

But users point to plain this dense metric to solve the problem。And it's a rough。

 it's a course registration， it's not going to solve the fine registration problem for you。Okay。

 so if you want to put everything into an in an algorithm， you can write it like this。

Get the initial guess。 get the target point cloud and the source point cloud while not converged。

Solve the nearest neighbor search。Minimize the cost function and find the optimal transformation。

If the distance between the newly calculated transformation and the previous transformation is less than a。

In epsilon， you can assume that there is no change in the transformation。

 You're at the local minimum。Then it's converged， and you can return it。 So there are two loops。

 One loop is the outer loop that you see to see if there is any change in the transformation as we iterate。

And， of course， this optimization itself is iterating each time， right， So you have two nested loops。



![](img/238dc488346d7aa00dd36d0f3fb69aa9_21.png)

So this is the code that I'm giving you。 I implemented this for you。And you can see that。In line。

8ight and9。I'm just squeezing them。I'm just getting the points， 3D points。So in line 10 and 11。

 I'm constructing a Kd3 data structure。Don't worry about the syntax。Just think about it as。

Some pseudo code。 Now It is an actual code， but don't worry about the syntax。In line 14 and 15。

 for every covariance。This C is not a matrix。 It's this。Ary of covariance is for every point。

I'm calculating the local covariances using nearest neighbor。

And my initial guess in line 18 is the identity in line 19。I start with the initial guess。

I do have some thresholds for the convergence。And I do have a maximum iteration in line 26。

There is no guarantee for convergence。It might。Take a very long time。Depending on the problem。

 So while not converged and the iteration is less than the maximum number of iteration。

Move the source point cloud in line 31。To 34， I'm first rotating them and then translating them。 Now。

 I'm doing it all at。 right， There are a bunch of points。I'm applying a tree by3 rotation。

 That's why it's multiplied from the right side， by transpose。Instead of writing a loop。

 I'm doing it all at once。In line 37， find the nearest neighbor between the target and the current source。

Now， this is something that we didn't talk about it in line  30，40 to 42 in ICP algorithm。And GICP。

 when we do the nearest neighbor search。Because points can be still very far from each other。

 We use a maximum distance threshold to。Remove points that the distance。

 the distance exceed that threshold。 We consider them as。Outliers。The problem is， of course。

 what is that this distance， if it's arbitrary。For every problem will be different。

 which better idea is to use M estimation， as we will do it。

Let the robust solver ignore those instead of setting a hard threshold， because initially。

 the distance is large。 But who knows maybe they are。In lawyers。

 we're just ignoring them because based on the current transformation guess， they are far。

And that's not a good assumption。So that's why you see survived indices。

 not all the nearest neighbors indices。Then I'm solving a gas neton here。

 I'm implementing my own solver。 I'm not using。Another library。

So what I'm doing I'm calculating the Jacobubian and solving a linear system in line  54。

 and then integrating in line 56。Now， the Jacoban is only 6 by6 because we're only solving a system of six。

Varis。Although there are many roles。But if you add them up， you can form。

A6 by six system of equations。As your normal equations。Right。So the normal equations will be 6 by 6。

Alright， the rest is the Gauss newutton。 and then we check the distance。 So for the distance。

 it'll come up。 You see that I'm taking the log of。

The difference between two rigid body transformations。You see the Jacoban。Line 104。

 this is what I drive in the slide。And this is the covariance part。For every covariance， I'm taking。

S nearests neighbor。Because this is slow in math lab。And when I get the eigenvalue in line 121。

Because the eigenvalue are ordered， the first one is the smallest one。I said that to E。

Wch is defined in line 114。Set the other one to one， and then reconstruct the covariance。

Using V and the nude eigenvalues。

![](img/238dc488346d7aa00dd36d0f3fb69aa9_23.png)

Okay， so that's。See that this algorithm， you have explicit code how you actually implement this。

So what is the distance metric， We're working with rigid body transformation， The distance is。

 of course， one transformation times the inverse of the other one。You can take the Lee logar。

 which is the lock。Mattrix log。If you want to see the individual rotation and translation distances。

 you can look into。T times T to inverse。 What you will see is that the rotation is。As usual。

 our1 times R transpose。We take the log， and then we to make it a vector and then take the norm of it。

 This will be a misalignment angle。However， at this stands。Does depend on the error in the rotation。

A lot of。Paper in the literature to tell you this。Which is not correct if you're solving for rigid bio transformationformation。

 but sometimes because the benchmark is。Giving you this。

 you have no choice because you cannot compare with other methods if you don't do it。

So you might do that， and I've done it。Not proud of it， but。Because the benchmark is like that。

 you have to do it。 So keep the method comparable。 But the true translation distance is this one。

 which comes from。The matrix， you just look at it， that's what it looks like。

You should notice from the filtering lectures。First， rotating and translating is not the same as。

First， translating and then rotating。Now， we talked about the robust estimator that we can use。

 For example， the kche loss function。 this will。At。

A nice property that we can softly ignore outliers instead of setting a hard threshold that。

Everything beyond beyond 1。5 M should be ignored。 That's2。In some sense， too conservative。

 even though the robust estimator is supposed to be conservative itself。

 So there are many options that Kohi loss in particular is the one that you see it's。

More harshly penalizing large residuals with respect to the other ones。

Alpha is a value that the method start moving sub linearly。This hyperparameter alpha。

That's why we tune it to see where we want to。Bend this quadratic loss。

So that it ignores large residuals， because large residuals will have large gradient。

And that will bias dominate all the good terms。That have small residual。嗯。

Do you have a question honor？没有。So the new cost function is using a weighted distance based on local covariances。

We also wrap it around the N M estimator。We're really putting everything we have on the table。

To make sure we can fix it。 And it is so much better。 This is， and we solve it on S T 3。 So that's。😊。

It gives you a nice algorithm to work with。Now， you can do all the association and calculations on GPU that should make it much faster and CPU might be slow。

For large point clubs。Can you remind us？The maximum likelihood top type estimator was a generalization of maximum likelihood that instead of log。

 we could wrap the cost function around any kernel。So the residual is。

Or the cost function is the norm weighted norm of the residual， right。We wrap this around a kernelel。

Or robust function， such as this one。But what all of them they have in common， that instead of。

No loss that moves quited radicalically， right， as the gradient grows。

The role of this robust loss function is to。At some point， start bending the quadratic。Los。

Because when the residual is large。In the least the squares problem， we talked about it， that。

The gradient of the objective function is Jacobbian transpose times the residual。

The gradient will be very large。 The outlier， by definition， does not agree with the model。

 this distance were calculating。This will dominate。All the good data in lives。You don't want that。

This last function helps us to ignore。Reduce the effect of them， right， instead of。

Having this effect， it has a much smaller effect。So without making a decision， softly。

 we're ignoring outliers， and that's very desired。As opposed to setting threshold。

 making a decision that I'm going ignore this set of points and the optimization。So very quickly。

 theres an extension of this method that you have open source software for it。

 It's called semantic ICP。 If you have semantic information， how can you leverage it in。This method。

 the idea is that if you know the labels in。A pointin cloud。

 you should be able to improve the data association。

Because points from sidewalk should be matched with points from sidewalk。That seems to reduce。

The domain of association substantially， if I know these labels。And these days。

 it is possible to get。This sort of segmented point clouds。So the idea is simple。

The points are labeled by their category in the scene。Therefore， if I want to。Move the sensor。

 the lidar and match to set of。Cgorized or segmented point cloud。I do not need to match。

Points that do not belong to the same category。However。And then。So you see points with similar color。

 There's no ambiguity。 These two should not be matched， right。

 because they don't have the same label。However， in practice， probably the labels are not perfect。

They're coming out of a softm function that they have some probabilities。

One idea that we did is that， well， let's delay the decision， Use the probabilities。And。

What happens is that that leads to an extension of。This G ICP， to a framework that。Hads two steps。

 expectation and maximization expectation is。When we softly recover the association。

 instead of one to one， we do many to many。Find several points in the neighborhood that are possibly associated and weight them by their categories。

 and。Information that comes from segmentation。And then maximization is step。

Just solve the maximum likelihood problem， as usual。

 So E M or expectation maximization is a general framework。 And that's what we are applying to。

The problem here。 So what happens is that。I skipped the driverss here。I share the paper with you。

Ultimately， instead of having n terms。We have。And。Small ans begin。

 because if we are associating every residual。With and other residuals， right， small N。Then。

 for example， instead of 100 terms or thousand00 terms， suddenly we will have 5000 terms。

 So it is a more expensive problem， this semantic ICP。And in the expectation part。

 we calculate the weight。 So not every residual。Has the same weight importance。

Especially if they don't belong to the same semantic category predicted by， let's say。

 a neural network。If they both come from。The road， then this weight is high。 If they're not。

 it should be very low， weighted down。And that。Les to a small modification of G ICP that has this expectation maximization step。

Other than that， the algorithm is very similar。 Now， you run this on some benchmarks like Kity。

 You can see substantial improvement。 This is the initial。

This is the distance between the ground truth and the initial guess。

And this is a distance between the final solution。You want this to。Not to be like this。

Because the final distance。With the gruous an estimated is large when it's a line。

You want it to be lower。Its easier plot to understand。The CDF plot versus error。Now， the G ICP。

 when you solve it on S。E3， you can see for the rotation part is doing very well。 this dashed line。

Yeah。For the translation， not so much yet。The other G ICP， the orange one。

 is from Point Cloud Library。It is using oiler angles。So with all our angles， you get。

The performance is much lower。Then solving on。A league。With the semantic ICP。

 you can see the translation part is also improved。It is difficult to recover。 if we don't know。

If both are from the wall， right， and there's no label， there's no reason to move them。

 whereas these weights can tell you to move points。Even， if geometrically， they're similar。Okay。

 that semantic space。Has its own。Notion of this stance， which helps to guide the transformation。Now。

 you have the Open 3D is another nice library to work with this in this area。

 Check these three links， PCL， Open 3D， and the semantic ICP and G ICP S 3 are both available in C plus plus。

The implementation is available here。Some readings。And that's it for today。



![](img/238dc488346d7aa00dd36d0f3fb69aa9_25.png)