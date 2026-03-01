# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P58：58_06_08_8-主动轮廓-时长-16-57-可选休息点-06-23.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。 We have been talking so much about active conours during this week as one of the examples of the use of partial differential equations in image processing that I want to conclude the week with a bit more of details Now that we know all the background material that we need。

 We know curve evolution level sets， calculus of variations， differential geometry。

 We have all those concepts that we learn this week。

 Let's put them together in one of the active contours type of techniques。

 So let's just discuss that a bit more。We normally talk first about edge detection。 Now。

 edge detection basically only talks about local changes。

 So it's basically giving us places where there is a big change in the image。

 And because sometimes we compute edges with gradients， for example， Comp the gradient of the image。

Then at every location， we might have the strength of the edge。

 which is the absolute value of this or the magnitude of this。 We might have the。

 basically the direction of the edges。 Remember that the normal to the level sets is in this direction。

 So basically， if we have an object。This is the level line and then the gradient is perpendicular to it。

 so we also get the direction of the edges which are in this direction。

 so we get a lot of information， but all that information is local。 As we see in this picture。

 The goal of active cons as well as other techniques， for example。

 was also the goal of graph cuts is to integrate those local measurements。

 if we look at this picture， for example， that we see local representation of edges。

 there is some basically spread around edges。 but if we look carefully。

 it looks like there is an object here。 and probably another object here。

 So there is some relationship between the local edges。

 and that's what active cons is going to track， try to capture。

 Let's just see that that's what we want to do I want to run that again。

 we basically want to integrate this local measurements of image changes。

And that's what active contours does exactly in the way I just show it。

 it just curves that move with equations that we have seen and we' are going to discuss again curves that move towards those local edges。

 so active contours basically starts from an image。

The first thing you do is you have to compute edges。 You have to do these local computations。

 There is a lot of art in how to compute those edges。 but that's always the first step。

 So you end up with an image that has kind of information about the local characteristics of the image。

 and often when we talk about active contours。 we talk about this function。 So we smooth a the image。

 and that we know by this time we' are in the six week， we know images are noisy。

 And very often we have to just clean the noise a bit。

 we take the gradients as indicator of the local edges。

 this is just to make sure that we don't divide divide by0 So we basically take one over a regularized gradient or one over the gradients of a regularized image。

 and that gives us kind of an indicator function of where should edges be。If they。

 if there are edges， this is very high。 So one over is very small。 once we have that。

 then the active contours have to go and integrate that。 Now。

 where is the active contours equations that I showed you before。 And I'm going to show you again。

Coming from one of the things is that what is a curve， What is an ice curve。

 An ice curve is a curve that goes around areas where this image that is basically this one is very low。

 Remember， once again， gradients， very high one over gradients， very small。 So I want to find curves。

That travel around regions。That this image is very small and this is represented here。

 I basically am integrating over the image G， and I want that integral to be very small。

 That will be my curve for the active contour。 So this is a function of G。

 and I'm looking for the curve that minimizes that function。

 We know what how to do that that's calculus of variations。 we are looking for a curve。

 That's a function。 that minimizes this。 So we plug G in here。 and we do calculus of variations。

 and we get an equation for the active conours。 that's basically the whole trick。 So once again。

 we do the local h indicator。 we are looking for curves that are what I call curves of minimal effort or shortest path in this space。

We do calculus of variation and we get a curve theform that moves the curve towards the minima of this function again。

 sometimes just a local minima we move it towards the minima of that function and those are curves that are traveling around low values of G which means traveling around edges and that's basically how we get the equation for active cons let's see that equation again before that I want to show you just one example think is a nice example in ultrasound。

 those green curves our original curves and deform according to the equation that we obtain from the Olarangerange towards the red curve the red curve is sitting in a place where if I integrate if I sum g all around it is low certainly much lower than the initial one。



![](img/a47aa6ebffbbe8d66283d1cc7f090123_1.png)

![](img/a47aa6ebffbbe8d66283d1cc7f090123_2.png)

That's what the calculus of variations gave me， that deformation。So let's talk about this function G。

The function G。I'm going to just draw some graphs here。 It's basically。This is an image。

 It's a very simple binary image。 These are the edges of the image。Let's look at a profile。

 This is almost binary。 It looks in the screen as binary。 The profile， when I travel here。

 he goes up and down。 So it's about this。Now， when you compute edges in this image。

 you're going to get basically。High values around these regions。 And then if you do these。

 those are going to be low values。 And we know that remember。

 and we're gonna to see the equation again。 Remember， first of all。

 we want to travel in regions of low G because where we are doing the integral of G。

 So we want to go around regions with low G as we see here。 that's one thing。 And remember。

 we want this G to be very small， because we want the curve when it's evolving to stop at the boundaries。

 we don't want it to continue evolving。 So that's one very important concept。

 And that's what we get from taking this G function。

 this potential function to be a function of the gradient and inverse function of the gradient。

 Now when we do the the basically the Oular branch or the calculus of variations of this。



![](img/a47aa6ebffbbe8d66283d1cc7f090123_4.png)

We got this equation。That we see here。 This is the equation that I show you a number of times to be basically the equation of the calculus of variation。

 So this is the equation。That is minimizing。This is a curve evolution。 The curve is evolving。

 We have seen this a number of times already， and， of course。

 this is implemented with the level sets。 And I show you in one of the previous videos at the end。

 a slide with this equation in the level sets framework with an implicit function fee。

 So this is the equation that is basically the gradient descent or the equation that basically minimizes this。

 which is also called a jodesic curve。 It's a curve of minimal weight。

 and those sometimes are called jodesic curves。😊，Now we already saw in the previous slide this function and this is the function that gives us basically this what we see here。

 Now it comes out from the minimization of this Also this term what this term is doing。

 look there is a gradient of the potential function， not a gradient of the image。

 a gradient of the potential function and those are represented here by this green lines。

 So it's not only that G gets very close to0 and it's going to try to stop the evolution。

 remember if we don't have G this is curvature motion and it shrinks it to a point。

This will try to stop the evolution， but if we don't have an ideal edge， this will never be zero。

 then it will slow down， but it won't stop。 It will come here and it will kind of move because G is not0 yet it will just maybe move around or maybe even jump over if G is not not really a very low and the curvature wins。

😡，So this other term that once again comes natural from the calculus of variations is。

Basically pushing the curve towards the gradient of G， this green arrows。 So it' saying， okay。

 but I'm going to trap you because I have this term that is not going to let you go away。

 So this is kind of an extra ve。 And once again， this part is because， remember。

 when we have velocities that are not perpendicular to the curve。

 All while we curve is the perpendicular or the normal component。

 And this is what this operation does。 It projects it to the normal component。

 So we have a stopping term that says。Come to me， come very smoothly to me because you have curvature here。

 and we all the curvature motion smootheth the curve。Stop when you get close to edges。

 or at least slow down。 And this term traps you is pushing you because it's a gradient of this function。

 So it's pushing you So you get stuck there。 So that's basically what the active contours or in particular。

 the jodesic active contours， Sometimes they're also called a geometric active contours because it has this curvature and a lot of geometric components of the curve。

 This is what these jodesic active contours are doing are minimizing this energy this geodesic energy are trying to find curves of minimal distance。

 minimal weighted distance with weight G and they do that by doing calculus of variations。

 getting into this curve evolution and implemented it in the level sets framework。

 So everything together that we have learned during this week is in this。Jdesic， active counters。



![](img/a47aa6ebffbbe8d66283d1cc7f090123_6.png)

Now， that was just an example。 basically in1 D。 What happens in today D is basically the same。

 It was an illustration in1 D。 And what happens here is we take the image with smooth。

 your compute edges。 Let me just show you that again。You compute edges。

 local edges based on this function， and then you basically evolve a curve。

 You can start from a curve， for example， that surrounds the object。

 you just do some initial condition， you can start with multiple curves。 Remember。

 we implement this with level sets。 We don't care about topology。

 So you can start with multiple curves or you can start with a curve around curves inside。

 just let them evolve。 and when they evolve， boom， they get into the integration And if you see that。

 and I'm going just show you that once again。The initial curve has much more energy。

 So if I go and integrate。😊，G for the initial curve。

 it's much larger than if I integrate G for the curve that we obtain at the end of the process。

 And that's the goal of this curve evolution once again， implemented in the level sets framework。

 So this joydesic opttic contours are used a lot。 This is another interesting example。

 I'm going to run it a couple of times that we start basically from multiple curves。

 Let them evolve with。

![](img/a47aa6ebffbbe8d66283d1cc7f090123_8.png)

A function of G。 and basically we see that it attaches itself to the boundaries。

 So look at the number five starts only from these two contours and it evolves to detect these red line is detecting the numbers and we see the same here。

 basically we start from a bunch of contours and they evolve and they get integrated to find the boundaries。

 we went from the image to a G function from it we did a curve evolution using level sets and we get these solutions。

 you can basically observe a number of different things here and get， you know as I say before。

 this is level sets。 So you can play very freely with the initial conditions。So this is one example。

 and active counterours have been extended to surfaces。

 So they are called active surfaces or minimal surfaces。

 And here we see examples from gray matter segmentation in MRI。 So it's use a lot。

 as were going to discuss during the last week of this class It used a lot in medical imaging。

 This is one example in 3D。 This is another example in 3D of finding very。

 very tubular type of structures。All these different examples use different G functions that are basically adapted to the problem。

 We talk about one over the gradient。 Sometimes we have much more information about the type of images that we are using。

 And then the art is in the design of that G function that will help the contour or the surface to get basically attracted to the correct boundaries to the correct regions。

So by this we are ending week six。 This has been a week where we learned a lot of mathematical concepts in order to be able to do things like active contours a dysotroppic diffusion。

 and there are many more applications of partial differential equations in image and video processing。

 I just illustrated a few， and I gave you some of the underlying theory。 it was， as I say。

 probably the most mathematical oriented。😊，Week in this class， it's certainly these six weeks。

 but it's also going to be the most mathematical， basically busy week of the whole class。

 We're going to use PD is also next week when we talk about imaging painting as an our example。

 But as I say， every week is self-con。 So when you come to next week。

 of course you you're already an expert in this area。 So it's going be easier for you。

 but I'm going to just talk about those equations。 The ones that we use。

Next week and next week is not going be as mathematical as this week。 It's just gonna use those PD。

 And they're gonna to be very intuitive to understand。 Imaging painting is a lot of fun。

 and it has a lot of relationship with biology。 And we're gonna talk about that next week。 Thank you。

 I hope you have fun。 I know it was a hard week with a lot of math。 but that's very useful math。

 So I'm very happy I was， I had the chance to teach you about it。 Thank you。 See you next week。😊。



![](img/a47aa6ebffbbe8d66283d1cc7f090123_10.png)