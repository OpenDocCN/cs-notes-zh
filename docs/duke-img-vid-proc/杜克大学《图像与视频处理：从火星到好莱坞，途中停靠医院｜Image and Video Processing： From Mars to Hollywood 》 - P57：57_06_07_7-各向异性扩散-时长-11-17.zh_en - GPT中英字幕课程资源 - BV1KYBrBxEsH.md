# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P57：57_06_07_7-各向异性扩散-时长-11-17.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。 We're going to now give an example of calculus of variations use in image processing。

 And these are the techniques which I saw in the previous video。

 Let's apply them to image processing now， and we're going to do that with one of the most famous equations。



![](img/bf312c7d570b5d62c18f99f2763b1fe8_1.png)

In image processing in the area of partial differential equations， in image processing。

 And that's anisotropic diffusion。 What is that。If you remember when we discuss about Gaussian filtering and averaging images。

 we talk that those were like diffusion of the pixel values all across the image what was happening is that we obtained blaring because if there were edges basically we were averaging across edges we were letting the pixels values across edges to be basically mixed up and that's what we obtain blaring and that was isotropic smoothing it was just going all around it didn't matter if it had boundaries or not boundaries what anisotroppic smoothing or anisotropic diffusion is trying to do it's going to try to average pixel value pixel values only on the right side of the object on the right side of the edge on the correct object so。

valuess here are going to be average among themselves to basically denno or enhance the image pixelix values here are going to be basically mixed among themselves。

 How do we do that， We do that with equations， partial differential equations as we see here。

 before we look at the equations， Let's just look at the images， This is an original image。



![](img/bf312c7d570b5d62c18f99f2763b1fe8_3.png)

And if we do。Basically， Gaussian smoothing or averaging。 we know that we're going to blur。

 We blur across the boundaries because it's just mixing pixels from different objects。

 And that's what we see here。On the other hand， if we try not to blur， try not to mix。

 we only mix pixels on the same side of the boundary without going in this direction。

 then we get a much sharper。 we still see that we have removed noise inside the object inside the gray matter of this MRI picture of the brain。

 We see that this much smoother， but we are still preserving the boundaries very， very nicely。

 The difference between these two。 is here we have what we have marked here with red background is isotropic diffusion heat equation。

 we actually already talk about it。 but we are going derive it in the next slide using calculus of variations。

 here， we have add isotropic Before we take the second derivative， which is a divergence。

 I have to basically remind you that the lapplian。Of the image。Is the divergence。Of the gradient。

And we already defined the gradient and the divergence in the previous slides。

 So before we take it as here。We introduce a function in between here。

 This is a very similar function as the one that we use for active conours is， for example。

 one over the gradient， we're going to see that in the next slide' a function is going to say wait a second。

 don't diffuse if there is a strong gradient stop the diffusion。

 and that's why there is diffusion in certain directions when there is not a strong gradient and there is no diffusion or reduced diffusion where there is a strong gradient meaning across edges and that's where we get very sharp boundaries we preserve them while at the same time regularizing inside the objects and that's what we want。

 These equations are a result of calculu of variations。

So if we basically define any function of the gradient so here。

This is what we saw the last time that we were basically taking functions of U。Or derivatives of you。

And basically， the gradient is the derivative。Of the image and row here takes the role of F。

 So we take any function of the magnitude of the gradient。 If we compute the O larangerange。

 this is what we get。 that's the Olarangee of that equation。

 If we follow exactly the formula that we show in the previous video。

 And remember the partial differential equation is obtained by the forming the image equal to the O larangerange。

 And then when this doesn't change anymore， we have solved the O larangerange。

 and we have obtained maybe only local， but at least we obtain a minimizer of this functional。

 So once again， this is just by doing the Oer lagrangerange that we learned in the previous video。

 Let's just pick a couple of examples of this row function to show how nice this is。 For example。

 let us consider row。お？Both。A。To be a。Square。So here I'm trying to minimize。

The magnitude of the gradient。Square。And then the o branch。 So if row of a is a squared。

 then row prime is2 a。Okay， so instead of row prime， I have to put two times whatever is inside row。

 which is the gradient。Okay， so basically I have here。 And then the oil lagrangee that I get is。

The earlier branch equation is I T。 This is this。Equal the divergence。Of ro prime。Basically， to a。

 let me ignore the two。 It's just a scale。 So a。That will mean。Replace the gradient。

 a is taking basic deposition of the gradient， the absolute the magnet of the gradient， sorry。

And this is。This part。 So this part stays。And this part is robe pride。Now these two cancel。

 and I got divergence。Of basically， the gradient。And this is the laplaian。For this function。

 the O larangerange is basically the heat flow， and that's isotropic。

 that's basically smoothing it in an isotropic fashion。Okay， so that's。

The O larangee of the square of the absolute value of the magnitude， we get the regular heat flow。

 the isotropicff diffusion all around let's just pick another example that is really really really interesting。

Lets just speak， for example， a function that basically role。Of a。Equal a。Okay， just itself。

 we could take the absolute value of8， let me just leave that technicality aside for a second。Then。

 row prime。Is one。Okay， so I'm basically going to try to minimize。The absolute value of the granite。

Not the gradient square， the absolute value of the gradient without putting it to the square。

 And then what do I get as the O larange equation of that， So row prime is now a constant。

 So I got divergence。Of gradient。Normalize。By the graduate。So I didn't get any the heat flow。

 I got this normalization factor that is saying wait a second if the gradient is very high。

 you are one over the gradient so slow down and try to preserve those edges so this is one example of anisotropic diffusion。

 it's actually called the total variation。Total。Variation。That's basically the name of this equation。

And now I want you to think for a second。What is this We learned it a couple of videos ago。

 This is curvature of the level lines of the image I。

 we actually use it as a generic function we use it phi in that case or phi we use this in that case。

 Now this is the curvature of every level line of the image so we are basically considering the image as a surface and we are deforming the image we are doing an isotroppic diffusion of the image in such a way that basically it's moving according to the curvature of the level lines and that's getting us an isotropic diffusion。

 this is an extremely interesting connection。 we talk about curve evolution we talk about curvature type of motion。

 This is a curvature type of motion that basically the image is moving。

Based on curvature of the level lines and that's we don't really care about the level lines or we didn' derive this equation from the level lines。

 we derive it from the oil larangee of the total variation that we connected between both of them。

 moving according to curvature type of equations and moving curvature of the level lines and moving according to the oil lagrangee。

 the curvature of what the curvature of the level lines of the image。

 a very interesting connection between。

![](img/bf312c7d570b5d62c18f99f2763b1fe8_5.png)

Cave evolution， level set and calculus of variation。 And that gives us a very。

 very nice equation for an isotroppic diffusion。And this basically is one of the most famous examples of the use of calculus of variations in image processing。

 What's left in this week is to conclude the week in the next video with a bit more of active contours。

 one of the main clients of curve evolution and calculus of variations as we have discussed in the past。

 and as we are going to see in the next video。 Thank you very much， I'm looking forward to that。

 Thank you。😊。