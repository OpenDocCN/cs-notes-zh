# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p18 -18-Lecture 18-RGB-D Visual Odometry.zh_en -BV1UfAmeUE3e_p18-

In this lecture we will cover RGBD visualotometry。We're going to see how we can use。A type of camera。

From the category of depth camera， that gives you RGB measurements in form of images and depth images。

In form of another image that tells you what's the depth， the distance of each pixel。

From the camera lens。And then together， we can。Basically。

 construct the point cloud that has color information。We want to use。

 We want to see how we can use this camera to reconstruct a scene。And to do that。Basically。

 we need to。Tracrack the camera poses over time。So that's the context of visual geometrytry。

 It can be done with monococular camera， or。Sttereo camera or RGVD camera。

I'm going to use an example from。TUM data set for RGBD Islam。



![](img/4d49fb9518c86c3c314522327c25e9a0_1.png)

I made up。Well， first of all。This is a room。 You see this teddy bear。There are a lot of sequences。

 but this particular sequence， it goes around the teddy bear。 We want to reconstruct the bear。And。

As you can see， the image is blurred， and that's the problem because this camera。

 this particular camera has a rolling shutter。As the camera is moving。

 the shutter is also moving to capture the scene， and that causes motion blur， which is。Best。

 as far as we know， it's understood as convolution along a time channel。So that causes motion blur。

And consequently， that will。Cause difficulty for registering this image with the next one to find out what's the camera pose。

We do have cameras with global shutter， and obviously that's preferred because they capture the entire image at one instance。

And that。You don't see motion blur as much as you see here。And this is an example of the depth image。

 the depth image。You do need a scale to know the actual metric value。But based on the image。

 you can tell that。Very steady arm。Can you tell that？So this is Teddy， it's closer to the camera。

 so the darker value is closer to the camera。The brighter pixels are。Fday。Is this perfect？

Can you see？It's hard to see in class， I think， because of the life。

But this is far from imp perfectf because some of the pixels are missing the boundaries。

 the edges of some shapes， for example。You can see this is a laptop here。With this shape。Is not。

Exactly like what we see in the image and that's a problem。

Time is not all pixels come with accurate depth， or sometimes we're dealing with missing depth values。



![](img/4d49fb9518c86c3c314522327c25e9a0_3.png)

So this is the video， thiss a gift image that playing all the images recorded by the camera。

 This is how the camera is moving in the room。This is the six degrees of freedom movement。

 the camera can roll， can pitch can ya， there's the XY Z movement。We see we can zoom in， zoom out。

And all of these motions can be done at the same time。So the faster you move。

 more motion blur you see， and it becomes harder to register。

 the more overlap you have between consecutive images that makes the problem easier because we're solving for the smaller motion as you move faster。

 that makes it more challenging。And sometimes becomes impossible to track。

 which might we might rely on complementary sensors for。Estimating the camera motion。

While we're registering images， for example， modern cameras come with IMU。

 you can use IMU to fuse that with image information to get visual inertial autometry。9 another。

Point that you might notice is that。Although， theres someone standing there。

 the environment is aesthetic。 If the objects are moving and the camera is also moving。

 that will make the problem even harder because。We do not have any knowledge of object movements。

And we do not know the knowledge of camera movement。 We need one of them。To be a reference。

 to estimate the other one， if both are unknown， that makes it very challenging。

So we can track objects in the camera frame as it moves。But that will be relative。

One idea is that if you can' detect the dynamic。Part of the image， and remove it。

Then maybe you can work with the static part to solve the problem。 That's somewhat an obvious idea。

 discard dynamic information。And more challenging will be。

 how can you actually use the dynamics of the scene to make your tracking better。

 But that's a much harder problem to solve。Now the depth。Video that you see here。

Is for the same images。However the camera that we buy。

Has two different sensors for getting the RGB data and depths data。

 And these two sensors are not necessarily perfectly co located。

So these two sensors are somewhere on the camera， and these images are not perfectly。Reecttified。

 they're not in the same frame。We will not dive into。How to do this low level signal processing。

Luckily， when you buy these sort of cameras， usually they come with drivers。

 The driver usually develop with。By the manufacturer。By people， such as yourself。

 they just sit down and。Build a driver and make it open source usually so we can use it。

 It could be a Ro package， LCCM package or some other softwares that you can run。On your OSs。

Then what we get， we get registered， depth and image data。 First of all， they're synchronized。

 They might not be synchronized necessarily。Imagine the frequency of RGB sensor is different from death sensors。

Once we register them。Then we can get synced， depth and RGB images。

And potentially with some intrinsic calibration that comes from factory， you can get point clouds。

 and if necessary， we might need to recalibrate the camera， intrinsic parameters of the camera。Okay。

 but when you。Want to deal with a problem for the first time。

 you can use one of the data sets that usually come with calibration parameters and all the preprocessing。

 using some tools that are provided。 So that's a good way to focus on the algorithmic side of it。

 And later you can look into those parts if you're interested。



![](img/4d49fb9518c86c3c314522327c25e9a0_5.png)

With that， let's start。See how we can together a formulated problem。

The way I want to formulate the problem is using nine nonlinear Lisa squares。

No nonlinear because we will see it ends up being nonlinear。

And we'll try to come up with ideas and see how we can formulate at least squares problem that。

Finds this camera pose。By aligning two consecutive images。 So in some sense。

Frame to frame R GBB registration。 It's similar to point cloud registration。

Because we could work with point cloud directly， and we could， in fact。

 use previous methods that I discussed。That we can integrate color and point cloud。

The RKH S registration。Ida came after this。 What we talk about is something that was published before that。

But also， the。Objective function that we derive today is important because something that is called photometric loss function。

When next time we talk about the slam， when I show you an edge in the graph， we say， for example。

 this is a photometric factor。Then you know what to think about this。Lecture is a building block。

 iss an edge in， maybe a graph。That we used for formulating a s problem。So， let's start with。

The problem of。I think this is lecture。18， and we will talk about。Frame to frame for short。RGb。

The registration。Or you could think about。Of this idea as。RGBD， visual otry。Now。

 the visualtry does not need to be just one frame to another frame。

We could work with a sequence of frames， and that's usually how it's done。

 That's called a sliding window optimization。Or we could just。Maintain the entire history。

Similar to s。 But when it's o， that means that there is no global loop closure。 There's no。

History tracking that globally， we go after a long time。

 We come back to a place and know that's the same place。 And we try to remove drift。

When we have that， that's s， simultaneous localization and mapping。

 If you're working with a sliding window。And rely on。Local constraints to improve your。

Estimate over window of time， that's usually called oometry。

So frame to frame registration is the building block It's the simplest way of solving that otry problem。

 if it's necessary to learn it， then you can build on it by solving many of these frame to frame at the same time。

 over a window of time and the window slides over time， right， you add new frames。

 you ignore old frames。That's the idea。So， we。

![](img/4d49fb9518c86c3c314522327c25e9a0_7.png)

S you some examples of this camera。So a lot of you probably have seen Microsoft Kinect。

 maybe you played。The Xbox。That was the first one we were using for RGBD Islam。

It wasn't built for robotics， but。Smart people could make a driver for Linux。

 Then we could run it in Linux。 And thats， that's how。RGBD perception。Research is started。

So that's the importance of having the hardware， actually having the sensor the hardware so we can collect data and then solve problems。

Causes huge progress， because suddenly now people can。Bring in a lot of ideas that we might know。

To reality。So it was enabled by having sensors。Maybe the most recent one。



![](img/4d49fb9518c86c3c314522327c25e9a0_9.png)

I think it was discontinued， unfortunately， but。We should see。



![](img/4d49fb9518c86c3c314522327c25e9a0_11.png)

Different companies making different versions of this。

This was an RGBD camera by Intel that comes with an IMU inside。

And you see it on a lot of robots these days。They use this camera because it is a small。

 it's relatively cheap。And works well， although it's good for indoor， if you use it for outdoor。

You can do。You can solve the problem for short range 5 to 10 meters。

 but the point cloud will become noisy as。We will see that brightness。

 constancy assumption will be violated。 We' will talk about it。Okay， this。

Page is filled with motivation now。Somebody was askingMotivate mode before。Talking about math。

I am dedicating one page to motivation。I hope。That satisfies you so the camera。

Our algorithms are somewhat agnostic of what brand of sensor you will buy。We're going to assume。

The data is processed， we have synced RGB and depth。Images， plus， we know the calibration。

 intrinsic calibration of the camera so that we can。😊，Project。

3D points and the image using the projection model of the camera， because if it's not calibrated。

 that projection will be inaccurate。Then。The model won won't capture what we see in reality。

As good as we hope。So the camera gives RGB and。Death images。Where to start。

 Where do you think we should start for。Formulating the problem。Day one， you started your job。

Your supervisor gives you a camera。And ask you to。See what you can do with this。

We want to see if this line of work is promising for the robot。And you know。

 not nonlinearly the squares from this course。What would you do。

I don't want to write it for you all the way。 We want to make it a case of study based on what we learned。

Are you trying to define the models？We need a model。 We need a constraint。

 We need some sort of constraints that relate this pose that we are interested。To estimate。

Shows up somewhere that we can minimize some sort of distance， some sort of residual cost， right。

 That's the key。Once we have that， we can just go ahead and define at least the squares problem by some of maybe squared versions of that。

Re죠。So we need， we need a model。 Then we need to define。A residual for the optimization。

 a cost function。It's a good place to start is。Lay out what we have。What's the goal？

Tracking the camera pose temporarily。The goal is。Our objective is。Frack。The camera up。Pose。Temporly。

 by temporal， I mean， we we are dealing with sequential images。

And we're going to focus on these simplest case， because if you can't solve that。

 there's really no point。Making it more involved。So we're going to collect some data from camera。

Maybe if I add the images， we can。See what we can do。I're roughly the same size。All right。

 so what we have， we're going to focus on。T1 and T2， a time is step1， I have one image。

And it's understood that it has depth image as well。 We know we have that。And a time and step，2。

 I have。Another image。You could call this image number one， and maybe this is image number two。Now。

 what I want to know is。How。The camera moved。In 3D。

So that it observed the second image at time of step T2。Now， that parameter， we have。

From our previous knowledge， we know that this six degrees of freedom motion that can have rotation and translation is necessarily an illegal。

 and that's SE3。So we immediately recognize that the parameter that we want to estimate。Is not。

Just a typical vector。 It's a matrix。It's an element of a matrix league group。

And we're talking about the camera， maybe。Right， it's moving from time to step T to time of step。

T 12， T2。Now， from the documentation of the sensor， I'm going to assume you read。

Those just like you read the entire hundred0 pages of IMU。Documents that I gave you in homework for。

I talked with a couple of students and they know every word of that document， so I trust。

You read this one too。So we have a camera projection model。For this， this particular intel camera。

 you can find it on Github。 There's a repository。That's also compatible with。

 So if you buy the camera， you can just run the ro package and you can just stream data in RVs。

It's pretty straightforward， too。See the data where the rest of it is our job。

Camera projection model is provided。So suppose there is a。Now。

 this is something that you might have learned in your undergrad computer vision course if you took your computer vision course in。

Graate school， they might have covered this。 It's a geometric model that。When you see a point in 3D。

 it tells you a model that projected onto the image plane。If you have not seen it before。

 that's not a problem， you can imagine this is a given model for this sensor。

So the models tells us that if I have a point such as P， X， Y， Z。This is a point in。3D space。

I can project。This point too。Pixels， you and we are pixels。

So my projection function pi will take this point。And。UV will be like this。

The focal point of the camera。Fcal distance of the camera along X。Times。The value of。

The coordinate of the point along x direction divided by z。Plus。Some。

This stands from the center of the image。And I'll tell you why we need C X and C， Y。 Now。

 the focal length of the camera along Y x is， it might be different。 Pixels need not be squares。

 Maybe pixels are rectangles。That's just the piece of information you need from manufacturers。

But when you calibrate camera， typically you can solve for different values of FX and FY。So， F。

Y times y divided by z plus C。Why。Now you can write this in a decoupled way。

 there's a calibration matrix usually named K。And then you have your treaty point divided by Z。

 So this is， is this。 And you've seen this。 I believe you've seen this in homework。3。When。

YouThere had two cameras。 There was an object。 You wanted to estimate the position of the object。

 So this was the model。 Is this model linear or non nonlinear。No nonlinear。 why， why is it nonlinear。

Because we have division by Z。 that makes it linear。So that's our this is two by one。

 this is a two by one vector。To make it clear， we have。It is common to use。

Coordinate frame like this in computer vision。 when you have one axis。

Along the height started from the top of the image， top left corner。

The positive directions are pointing down and to the right。Typically this is you。And this is we。

If this is center of the image。Then， we will need this。See values to reference it with the spec to。

The origin that we chose to be the corner of the image， not the center of the image。

So there's Cx and C Y for that。So we have the model， what's next？Looking for ideas。

While you're thinking， I'm going to make another simplification。 So RGB image has。Three channels。

 red， green， blue。We could。Try to use each color as a separate measurement。

Or before relening in this context is what you see in literature。Typically。

 the image is converted to gray scale。Then that combines all three channels into one channel。

 and then we work with intensity values。So that makes the problem a little simpler。

But when you use deep planning， you can just。Give all three channels as the input。

There's no need for combining them。So following what we read in the literature。

Images are converted to。Gray scale images。Now the simplest way to convert the color image to RGB is just。

Sund them up and divide them by3。But better models exist， and they use different weighting for RGB。

RightBut if you use open C or any other software。Or library。Probably you have access to。

A function to do it for you。Alright， so now we have。Intensity， I'm using I again for intensity。

 but also， it stands for the image。From image1 to image 2。What's the constraint here， I。

 I need to define my。Constraint so that I can measure error。 If you cannot measure error。

 you cannot minimize it。 If we cannot minimize error， there's no objective function to estimate。

The variable that you're interested in。So we can work with something that we can measure。

Could it treat me that any course money？到，这些。Any sort of transformation that we have。いです。The cameras。

Transformation， so if we're traveling a single point on the image。Then we can track the air。

Is projected from one to another， that a difference can then be whatever projection。

the image plane can then be translated to the motion of the camera。That makes sense。

 so you're saying that。Well， first of all， we should think about these intensity values as。

Measurements。We just have a lot of measurements。 This。

 that's why perceptual sensor sensors like light or camera are high bandwidth。

 The amount of data we get。Is extremely higher than something like I am U， which is a。Just a signal。

 1 d signal for each dimension。Against time。So， for。For example， this can be。3，20 by 2，40。Image。

It is a reasonable size to work with。 but that's pretty small。 We can get probably H images from。

V camera。But there will be probably too many pixels to work with that。

It takes longer to process them。So that's already more than 600000。Pixels。

 that's a lot of measurements for one time step。So the constraint that you pointed out pointed out is that if the camera moves。

 the environment is static， can I assume that what I see should be similar to what I observed before。

 there's just changing the viewpoint and if this post can capture that I should see the same pixels again。

And exactly， that's what we're going to assume。And。The assumption is called brightness constancy。

It's important when you model， you list your assumptions， if your assumptions are not clear。That。

Leavs others to wonder。What's the scope of your model when it's valid， when it's not valid。

 The model is not valid when assumptions are violated。

And that's how you can explain when something doesn't work well in practice。

You go back and look at your assumptions。Hopefully。

 your assumptions are reasonable and reflect your model。 Then see if they are violated。

 If they're violated， you can explain。Probably that's why。Your performance is not very good。

 So the assumption is。Called。AndThe brightness constancy is saying that if you move a little bit。

 not， not a lot。Under small movements。The intensity values。Of the corresponding pixels are the same。

So， that gives us。A way to reobserve this one pixel again in the next frame。 Therefore。

 now we can talk about their difference。If I minimize the difference between pixels that are reobed。

The the post that describes that。Animization， the best， That's my solution。 So that's the idea。Now。

 this assumption is easily violated， right？Is there a typo。No。You should be kind and tell me。

English is not my first language。Okay，If the camera moves。You know， a lot this。

Assumption is easily violated。 What's another case The assumption is violated。

There's a very obvious case that。You should be very careful when you use this method。

And look whether that that environmental condition exists or not。Variation and lighting。

 elimination change。 That's right。 So that's why it's so hard to use。A method like this。Outdoors。

Maybe it's a sunny day， the way you move， you might see glare in the image。

And that it can destroy everything When it's cloudy in uniform， the sky light is uniform then。

Slam metal shine。When when the sky shines， the slam methods are under the weather。😊，So， that's。

So when you see a data set， it's a cloudy day， you know。They knew。You get best paper award。

It even works outdoor。So that's a little sad because it might work sometimes it might not if it's violated。

We like to have methods for robot perception， that。They work under general condition that can change。

So that's， that's a。Exential limitation we have in robot perception。

And we're trying to make algorithms better to。Work in different situations。Such as that。 Okay。

 so assuming this is true。By the way， how can I read the pixel value when。I know a Pixel coordinates。

Imagine I have。This pixel here。What is its intensity。So I have my 3y point。There is a 3D point。

And I use the camera projection model that will give me a pixel。I'm going to call this。Maybe。Point I。

You I， We I。I'm asking you what is。Intensity of。Or maybe you call it like this UI VI。It is a scalar。

 yes， it's certainly。It's just a real number， and it's a positive number， because。

Clor Valley are positive。Pa is the real real number。 Or sometimes people show it like this。

How can I access this intensity value？ですよ。Ds into here。Yeah。How can I implement it。出一。

IsDo you have it saved like such that the center isn't the same frame him as U Yeah。

 I have this in memory， it's saved。In whatever way you want。该。I guess I'm not understanding。So so。

Trivial that。 you， you're not even considering it。 So you read it from the memory， right。

 So that's what you do。 So there is no。Function， there's no relationship。It's distorting your memory。

 and you read it after memory based on index value。 And that's okay for this method。

In the previous lecture， RKHS。It's exactly addressing this problem that there is no model that is describing these relationship between these intensity values and the point in treaty。

And that kernel density estimation that you saw is the weighted sum of labels。

 It is defining a function。It's a model。 It's analytical model that is describing the relationship between this P and 3D。

And this intensity， your color values。So in this context， that model does not exist。Something that。

You can go back in。Now compare these two， in this case， we just read it from the memory。 that's fine。

That's what we do。Which， by the way， we're limited by the resolution of the image and data。

 It is not continuous。 It is discrete， although we have a lot of pixels in。It works well in practice。

So I'm going to need to define the residual now。See if I have。See if I observe the point in。Remember。

 we have the depth value。 We have the points in 3D for the RGBD。Camera。If I observe the point in。

Let me write it first。So I'm seeing a point in image 1 in 3D。And of course。

 I can read for every point。 you can。 likewise， you can read the pixel value because for RGBD cameras。

 there's one to one correspondences。 We have one to one correspondences between。😊。

Points in 3D and pixel in images。So whether you know UMV or P in 3D。

 you can read the intensity value from your memory。So I see the point in image1， then I see。

The point again in image 2。The relationship that relates these two points is that if I。Transform。

The point in image 2。Using this rigid body transformation。And then。

 if I projected onto the image  too。I should get an intensity that is similar to what I had in image 1。

 I think it's strictly speaking， we should write。Right。But again， this。

 this part is constant because it doesn't depend on the transformation。You just know it。

 it's a value， it's a scalar value。See the point in frame2。 transform it。 sorry， See the point in。

Frame one， transform it to frame 2， projected onto the image 2。 read the pixel value。

 intensity value on image 2， subtract it from the corresponding intensity value of the point we transform in image1。

 That's the residual。Could we do it the other way， see the point in frame2， transform it to frame 1。

And projected to image。Onto image 1， yes， we could。 There's really no difference。 You。

 You need to choose one。At least in frame to frame， there's really no difference。

 You' estimating T or T inverse。In any case， it's a rigid body transformation。

 and the optimizer does not care。Which one you're trying to solve for？

Maybe if you're doing a sliding window or a slam， maybe you care about the order。But anyway。

 it will be similar to this case。So the action of。Rid body transformation on a 3D point。

 because I'm not making the points to be in homogeneous coordinates。 I'm not app one to X， Y， Z。

 So I'm using this dot value to。

![](img/4d49fb9518c86c3c314522327c25e9a0_13.png)

Be find。Action of T on P， which is rotate and then translate。And my parameter。

The decision variable of the optimization is。An element of Se E。3。

So how many of these residuals I have？60000。Let's say this is the image size。

You're probably better than me and arithmetic。Multiply them and see what you get。More than 600，000。

 right？So the vector of residual is super long。It's unbelievably long if you w to use all images。

If it's。HD image。What is it 101080 times。700 or something。New TVs are 8K。

So there is an idea in computer vision called。Image pyramid。So， when they have。Historically。

 when they have。High resolution images。This problem is not convex。four。Several reasons， first of all。

 the rigid body transformation has a constraints because R transs R must be identity。

That makes the problem constrained。 Now， when we do it on legalru。

 we do a trick using that exponential map to integrate。 We ignore the constraint。

But that gives us a local solution。The intensity values， if you visualize， right。

TheL escape of the residual objective function is not convex。 It's not going be nice。

Qudratic function that you find the minimum。 No， there are will many local minimum。

And then the bigger is the image， the resolution。 when it's higher。

 you get more of these local minimums。She makes it even harder sometimes。

High resolution makes the problem harder to solve。So the idea of image permit is that start from a very coarse resolution when the image is coarse。

 the resolution is very low。You roughly know where you want to go， because all those tiny。

Minimma will disappear。 You're gonna focus on the deepest。

Minimal available in the image and the cost function。So do the registration in。A course level， which。

 of course， you need to decide how many levels you want to。Perform。

Use that solution to initialize the nextus step。 Now， you're around at minimum that。Is hopefully。

 better than。A lot of bad local mini model you see in the higher resolution image。

 then solve it again。 move to the next step， next step。So， you repeat this。

Solving the same problem maybe 10 times， five times。Using this idea of image permit。

So the same problem just changed the image resolution。So obviously。

 it will make it a load if you have to solve it 10 times instead of one time。

That's a factor to consider。But it will improve your performance substantially。

 because it will guide。The course version roughly will do course registration will guide the problem to a deeper minimum。

The if。High resolution part will try to， you know， minimize the error around that。The minimum。

So that's a very established idea， and you find it in computer vision textbooks as well。Again。

 linking it to the previous lecture， RKEHS registration。

There is no need to solve the problem multiple times because of the continuity， the kernel bandwidth。

 that length the scale of the Gaussian kernel that you saw。 When you change that kernel。

 you remember that。Picture that when L was large on Tarus， we had a convex problem as we decreased L。

We got a lot of local minimum， right？ So the idea of image pyramid relates to that bandwidth。

In the sense that using the bandwidth， you can continuously control moving along that pyramid within one optimization。

 At any time， you can move along that pyramid， wherever you want。It's just hard to know how to move。

But you're able to do that in one optimization。 So that's another powerful。Feature of that method。



![](img/4d49fb9518c86c3c314522327c25e9a0_15.png)

So this is image pyramid， it's important to know that。

Sometimes people use it and just write a line and you read it in the paper so you know what it means。

In terms of like the。第二次。呃这这个。而0这。I computation now or is it a matter of just like optimizing the input resolution into your system。

 I guess I guess is it more hardware design problem or software design？The image resolution。Yeah。

 so in terms of what we're doing。Design。さ这个。But it's like down。No， the image， their hardware。

 The question is， is this a hardware problem or algorithmic problem。

 The hardware is can give you very high resolution image， We just。Algorithmically。

 if we attempt to solve this problem using full resolution image。

 you might think you're going to get better result。Because the software is local， your result might。

You're worse。Because。The gas near them will find the local minimum。Based on where you start。

 whether that's a good answer or not， depends where you start。When。You look for a course version。

 Jan。 Well， it will make it faster initially， right。

Then a lot of those subtle minimum will disappear。As if you have a surface with a lot of up and down。

 right？And if you get rid of high frequency， part of the signal， you're left with a nice。Surface。

 right， So you first go to where it's deep in terms of the loss function。

 And then you go back to the high resolution surface。To do the fine registration。

 So it's an algorithmic problem。 If you have a global solver。YouYou could use that。

 but typically global solve are slower anyway， if you go for a high resolution image。

It won't be probably real time。So ongoing challenge。然。

how do I reconcile that with this because we are using one to1 correspondences to make the risk？

Right， good question。 There's a question that last time we had a double sum， it was association free。

How do we know how to subtract which I2 from I1， right。So， the answer is that。When。Well。

 from image one， right， you have all these points。Right， you start from the first one。 again。

 you know the point in 3D because。It's RGBD camera。So you read the intensity value。

 and that gives you the this term for I1， right Now， when you transform it and project it。

You get the coordinate。On image 2， you just。You do need probably do rounding because indices are discrete。

 right。Based on the projected value， find the closest index。Or sometimes people take a neighborhood。

We say， it makes it。More complicated because now every residual becomes end residual based on how many not neighbor you choose。

 But anyway， if you pick one。Coordinate that is the projection here。

We round it and read that pixel value from I2。 So this is also another idea that is called projective data association In literature。

 this is known as projective data association。So you just need to project。

 and then you solve the association by reading the。Pixel coordinates。え均。no。

Create the automation masters。Will we use the RGB or intensity value to do what？你要就说这个。

We don't know the transformation， we。At any time， at any duration of the optimization。

 given the current guests， we have to do this association。 So they are not necessarily correct。

But hopefully， every time we move a little closer to the correct association。Yeah。

 that's the problem， too， that's a good point。Whatever is the guess， this difference is not。

 They're not necessarily the same pixel， right， even if there is a perfect match。😊。

In image one and two。Right。Okay。这证任意思是吧？Geiametric consistency with pixels。

Sounds like you're just not， the closest intensity。In the corresponding image to。在 그三。

The question is， is there any geometric constraint because we only use？

Something that is called photometric loss function。What we build is called。Photometric。Lost function。

 So we do not。Perform registration in treaty， that's all we have。And this formulation。Again。

 in the previous lecture， it is in 3D。 There is a geometric relationship that can capture a collusion better。

For the metric， obviously is in the image， it suffers from occlusion， it is in 2D。Nevertheless。

 it is a very powerful。Forermulation。It gives us already a lot。

So we're ready to formulate the first problem。The optimal transformation is the transformation。

That minimizes。Some of squared of these residual。 and this is at least the squares formulation of the problem。

Why least the squares， Because that's。The simplistic and order solver that we know。

And it will give us a solution。Are we done？把4万人去。Why is the。Few times a few times， this isn't PA。

Thats a size pre vector。Like it seems like we're applying eye to P。W should be。That's why in Z。

 not UV。清到咩嘅。Like what are the info， what is actually TIs？Isn't that a X， Y， Z It is。 It is PI is X。

 Y， Z Oh， we're finding it for each pixel Well， for each pixel， we have P right So here we have。

Right， this is something one time you go， if you go through the code or implement it。You。

 there is no other way to do it。 So that's when you read the data。You see that， well。

 there is UI and VI， right？But it's also corresponding PI because。

The inverse of that projection model will give you the 3D point。 However。

 to get that you need the depth value Z， the RGBD camera will give you Z。 So because you know Z。

 you recover X and Y in metric scale。So then you have X， I， Y， I， Z I。 So this is given， right？

And then we read the pixel。 So basically， when you store in memory， you have U I V I。

 That's a pixel value。 Then you have X， Y， Z for that pixel， and then you have the intensity。😊。

Depending on which one you want， you just read that。From your data structure。

So we have the first formulation of the problem。And I expect more from you at this point， because。

I tell you better than this。What's the problem？Sa it again。Do we need constraints。 No。

 we have the last function。Can we do better？Or is this all we can do。I mean。

 I guess one problem is that you're kind of disceing that the corresponds are。

There's probably just a small of print images。There could be small overlap， even if it's big。

 there is a non overlapping part， so that's a good point。No matter what， when we move。

 there's going to be a non overlapping part， no matter how small between two images。

And that can be easily half of the image。So as we read this intensity and we evaluate the loss function。

 they're not supposed to match exactly。 And， in fact， they can be very large if。At any it it。

 if a transformation is。Not。Near the solution， the difference can be very large。

And we're dealing with a quadratic。Bss function。 What happens when。

The residual for some of the pixel is very large。They're not。They don't match。 They're not。

 basically。Conrespond to each other。I see you shaking your head， but that doesn't solve the problem。

What should we do？So you acknowledge that this is a problem。

 It's going to be a very large residual for。Certain。Right。You were almost there。Yes。

 M estimation lost。So how about we make this a robust list of squares。 It's always better。

 It's always， It's always。Giving you something better than。Not having it， right？99。99% of the time。

So when you have it， make it robust。Usually， we don't lose anything。

 but you do need to tune that hyperparameter。And you can do it on some sample。

Frames is not very difficult。So， let's do。M estimation。We're gonna create an M estimator。Aka。Robust。

When you add your in your paper。Increase your chance of acceptance， 50%。

And that's a small section when you add an MSD me。Trust me， it works。So we have many options。

 but we learned about khi loss function。Let's say that's the example we use。

So the new problem will be。Okay。Should have readed in here as well。We're solving。

 optimizing over T and T belongs to this set or group SE3。So there。Robust kernelnel。

This is the robust。Clonnel or norm。For example。This is a。Cochi。Loss function。How to solve this。

The previous one we could solve using Gauss Newton or。Leeven Bemarqut。And we already learned that。

The difference that will make when it's on league group。Well， we need to drive the Jacoban。

You've seen some examples， we can do that。And then the integration rule will be different。

 We have to use the exponential map to integrate the transformation。

 So we covered that in the optimization lecture。But this is no。

 this is no longer at least a square problem because now it's wrapped around。Another loss function。

And。It's not at least the square problem。How can we solve this？While you think about it。

 there's a comment in chat that we can identify landmarks in two images。Matt is saying that， and。

So I'm going to take this comment as an opportunity to explain the difference between direct and indirect methods。

We are not extracting landmarks or features from the image。You could extract orb features。

 si features， surf features。😊，Using deep learning to extract features。

 there would be an indirect method， indirect methods。Abstract the image into a set of features。

The set of measurements， instead of more than 600000， will be substantially smaller。

 Maybe you have 1 hundred0 images，100 features。But the quality of features will be higher。

But you have to。Discard a lot of information to work with those high quality features。

Direct method consume the raw data。 We are directly using pixels。

 So we're using a lot of lower quality features in some sense。 And these are pixel values。Well。

 we use a lot of them。All of them here。And that's called direct methodted。

We are directly working with the camera images。So that there was an error that。

It was a lot of debate。 Which one is good。Indirectect methods are。

Better when the transformation is large。Indirect methods are also very good for。

Solving nont registration problems。But in particular， in。Loop closure when we detect the same place。

 we see the same place from a completely different angle。

It's challenging for direct methods to solve the registration problem because the initial transformation is very large。

Whereas indirect methods can solve that an example of that system is orbitlam that uses bagub binary wars。

To extract features， detect the loop closure， and then use features and Rinsack to。

Come up with a rough registration of very far frames。And then in the back end。

 the graph optimization will solve the s problem。 Direct methods are not very good at。

Solving that problem。But when you are dealing with small movements sequentially。

 which is the case for temporarily tracking。They tend to be very powerful。 They very robust。

Indirect methods， if the environment is featured less。Well， the algorithm is doomed to fail。

 Imagine its' uniform。 It's so grass。 so snow， so。Like a planetary data set。

 a helicopter from NASA is flying over Mars aside。Internet， there was a video， right。

 And the la is just so uniform that you just don't have。Features。Or features are very unreliable。

 You might detect， might not。Now， direct methods work well in that situation， and as you move。

 you use all the pixels to track the camera image。And you can combine them as well。

 They are hybrid methods。Such as SVO to combine them。

This particular method that we talk about is called DVO。Direct visualtry or dense visualtry。

So direct methods can be also dense or semid。We're talking about dance。Direct method here。

 We're using an entire image。You can also sub sampleample。

 maybe extract edges or some better high gradient pixels in the image， for example。

Then you can work with a semid direct method。An example of direct semid method is direct sparsetry。

 DS SO。That's an example of that。But that uses a sliding window optimization。

 it's not frame to frame。So that's the story of direct， indirect features， pixels。

Dance and semi dance。So how to solve this。Keep talking。You refresh your memory。

We need an answer here， we're not going to move on。to。Wheres。Right， that's a good idea。

 what was the name of it， we had an algorithm for it？I R L S， yes。Together， we figured it out。

So convert this to weight at list of squares when weights will depend on the residual。

Update them every time。 We had an algorithm。 We called it iteratively revaed at least the squares。

 I R L S。 I'm not gonna repeat it here because you're gonna get bored， but。You know where to look。

If you want to solve this， using IRLS。So we can。Yeah。Solve this。Problem。Using I R L S。はい、これ。Now。

 I do give you some note for the I have it from previousS driving the Jacoban。

For the sake of your mental health。I'm not going to drive it in class。

But it's really just the mechanical。Procedures that chain rule。

Get the derivative of the projection model。 Then you have the action of the rigid body under point per tubit derived the Jacobuban。

 We， we did it in the optimization lecture。So the Jacoban will be a product of multiple steps， right。

So。leaveve it at that。And that's the beauty of if you have a library that gives you this solver。

 you can。Learn how to construct your problem， and。Give it to that solver， to solve it for you。

 And that's usually。Good way to save time and speed up your progress。And in fact， you can do that。

 You can use。Something called。Serious solveva。This is a solver for Na nonlinear Lisa square problem。

 It does provide。Robust。Carels， it has other solvers as well， like conjugate gradient。

 gradient descent， and so on。So bo question。What， when we formulate this problem。Given that we have。

A lot of point， somebody calculates what's the 240 times 320。 So we have a number。How many？

 What's the size of the normal equation we need to solve， Is this problem larger scaled。Or not。It is。

What's the size of the problem。The linear system that we need to solve。So suppose we valid the。

We convert the problem into a weighted。Lease the squares， right， It will be R transpose some W R。Now。

 of course， we're solvinglving over T。Again， this， the W depends on。The residual and is irless。

 but for one step， it is a weighted least the squares。Now， if you calculate the。This is probably。

Some matrix。Let's say we calculate the Jacobubian for one residual term right， for just two pixels。

And that will be。What's the dimension of this。What's the mapping of the last function。

 The mapping is from the rigid value transformation。Tist。The parameter that we will solve。

 the delelta will be twist， right。We integrated using exponential map。 Tist has six dimensions。

And the loss function， the residual， in this case， is actually。Scalar。

 it could be a vector in least the squares， but here is' just intensity。So the。Jubian is。1 by 6。

 right， Okay， So it's a mapping from the variable to the residual。Whatever is the space of residual。

Because you're residual。As a function of twos， right， when you perturbrate。

 it will be linearized based on some。Jaubian。Plus。Some。Constant， right， something like that。6 by one。

1 by 6。If you。Larize it， you will get this model from Taylor expansion。

Or other techniques for driving the Jacobkuan。right。If that's the case。This is。

Shes essentially a square root of this weight。Times。Partial derivative evolve。Ressideual times。

With respect to twist， so this is a 1 by six。Matrix or a row vector。If I stack all of them。

That will give me the entire Jacoban for the problem。 And that's。Eiwaang。Let's say， a 2。诶。嗯。

And by six。And is。2 40 times 320。That's a very， very long tall。Jaku and， but fortunately。

 the number of columns are actually not very large。 So the variables。

That we're solving are there only6。Prameter it makes it the six vector。So if you construct。

The normal equation。It will be。A transpose A。You probably have。

We need some square root of that weight here for the residual as well， but。But anyway， this is。Now。

What is it？Is it a still larger scale？So it's only a six by six system of equations。

 it's actually very easy to solve。And we don't even need to store that long matrix。 We can。

Process every pixel and then sum up this AI trans times a。So 6 by one times1 by 6，6 by 6。

 And then keep adding them。s that's how it will become inverable， otherwise。For a single pixel。

 it will be obviously low rank because。It's6 by one times1 by6。So when we sum over all pixel cellss。

 if you have enough pixels， it will make it invertible。 That's how， you know。

 you have enough measurements。And then we can basically， you can define this to be。E。Cos D。So。

 we only solve。The six by six system of linear equations。So。It's very fast。 It this part。

 It does not take a long time at all。That's good news。

 That's how you can make this with low resolution image。 You can make this real time。So， that's how。

We can wrap up the。I are less sal， because。Now， you know what's going on inside every time inside。

 you update the weight， solve a 6 by6 system of equations， update the transformation。

Do it again until。Some maximum number of iterations or convergence。

Now I have one last question for you before I finish。嗯。That's when we have other senses。 What if。

You want to combine other source of information such as IMU。

 or maybe you have post tracking from another sensor。Maybe you get。I don't know eithermetry or。

Maybe you have prior over your pose。 You want to add it to。This problem， what can you do？

Sensor fusion， not just using the LGBD camera。 What can you do if you have other sources of information。

你一个。We can use an EKF。Probably， but that's very painful。 We have to。

We need to track two poses in this state。And we have to drive all the filter equations。Correctly。

It's going to become possible， but it's going to be more complicated。But the problem with filtering。

 which is next time we want to talk about it， is that once you linearize。

 you can never go back in time and correct it。We're after。

Now that we're dealing with more sensors and more sources of information。

 We're after something more modular， something more flexible。

 We can go back in time and correct past mistakes and linearizations。😊，Previous beliefs。

Get integrated。Const。装。As we get new measurements， we can add more constraints。 By constraints。

 you mean constraint， problem or extra objective， making it multi objective。I think冇 keep。Yeah， so。

That's a good observation。 A sensor that we used was ourGBD camera， and as a result。

 we derived a residual， a measurement model and error an error definition that allowed us to solve a optimizationization problem。

In the context of Islam， we're going call this a factor。Right。In fact， graph。This is a factor。

 So a factor will be an edge in the graph that connects two nodes。

 and that edge represents this residual。So everything we talked about can be one edge in that graph。

So， next time we。Want to answer this question。Using。Facto graphs。Or。Graph slot。Okay。

Then we're going to talk about。Different nodes and different edges， right， This is your maybe。Camera。

The camera is getting bigger as you move。Forward in time。That's not what we're doing here。

It's the same camera。It's called a special relativity。You move fast objects。Landth can differ。

They get longer if they move and wave。From you or closer to you。

You will know when you see the object。So then you have， well， in that context and you have。

 let's say， the first transformation， the second transformation and the third one first the first one。

 maybe it is。Maybe you don't know。 Maybe it is identity， right， maybe some prior。

Or maybe you do know， that's whatever knowledge you have。You can consider that。This will be。

For example， our photometric。Factor。And what it is。

 is's the same problem that we just talked about it。So's a building block of this graph。 Now。

 we're going to solve many of them at the same time。 So we're gonna assemble a giant。

Now nonlinear list a square problem and then solve it at the same time。



![](img/4d49fb9518c86c3c314522327c25e9a0_17.png)

For all the variables。 So that will allow us to make this modular。Now， if you have another sensor。

 you can easily。Add more edges。And maybe this is your IMU。Okay。This is good。 This is a scalable。

 It is too hard probably to manipulate by keep adding objectives and driving the equations。 Again。

 This will allow us to implement in library。Take data in a modular way。And potentially， automate。

How we solve it。 And this is done already。 And that's why we have。GTM library。

Now G2O can also solve that GTM。Probably has more sensor models。And solvers， GTM in particular has。I。

 Sam。Sover。That solver allows us to solve the problem incrementally online because we don't want to solve the problem from scratch every time we want to reuse past solutions。

To update。The small amount that we just add to the graph。 So that's also available in this library。

So again， the message is that。What you read as factor is this measurement model。

And that's what you implement in your homework 7。You're really working with the library to enter data。

You already know。The meaning behind it。出具证不是。Do each of these nodes imply like temporal temporal oral coation。

我てさ。Is that not？So for each， for each of the。Do the notes have to be temporal？No。

 that's a good question。 The question is that now there are notes that。

I'm writing here when this' rough figure， I have T， maybe 0， right。Wan。And two。We were asking that。

 can we have a note， for example， at time。12。That will get connected to。This note。Absolutely。

 and that's Luke closure。 That's why。This framework is so flexible。 Now。

 the constraint between T 1 and T 2， obviously， is' not going to be IM U。

We did not continuously move from。T1 to T12， there is a sequence in data from IMU that we need to incorporate temporal in the graph。

What we can have here is knowledge from place recognition。Reobserving maybe the same features。

 Reobserving the same place， so。It's a topic on its own， but it is possible。 And that's。

 that's precisely why this framework allows us to solve Islam。 We can。Add not only temporal。

Correrelated data。But also non temporal correlated that allows us to remove drift。

 There is no way to remove drift from the trajectory without having this。Non consecutive。

Ege in the graph。That makes it a s without this node。Without this non consecutive node。

It is just the oometry。With this is Islam。So that's a very good question。

And that's what we're going talk about next time。 So that's the next two lectures we're going to talk about s。

So we will focus on building a framework。 The edges can come from typically variety of sensors。

 And that' that's why it is sensor fusion because you can have different sources of information。

So that's the end of this lecture。 see some。Questions， so the number of times is 76。76000。800。

 not 600000。I wish I could go back in time and fix that and that's a problem。

That's exactly what happens in filtering。The mistake was made， and we can never fix it。And that's a。

Con of a causal。Data processing and control， everything is causal。In the smoothing framework。

 it can be non causalusled when you go back in time。You can change， use future to correct path。

 And that makes it non causalusal， and that's okay for perception and estimation。Okay。

 so we end the lecture。But I will answer。Questions on。Chaharath and in class， if you have any。

Thank you。