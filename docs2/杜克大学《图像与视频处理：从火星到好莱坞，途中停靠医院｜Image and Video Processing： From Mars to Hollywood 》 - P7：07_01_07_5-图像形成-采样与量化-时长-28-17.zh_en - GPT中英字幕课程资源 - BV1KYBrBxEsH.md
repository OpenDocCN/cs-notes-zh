# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P7：07_01_07_5-图像形成-采样与量化-时长-28-17.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

We're going to now talk about how an image is representing the computer。

 how a color image is representing in the computer。

 and how a video is representing in the computer and the very important concepts of sampling and representation and quantization。



![](img/c705bf9a26be1286adf52a82793b77bb_1.png)

It's always very good to have in mind the images that we normally take with our cameras。

 but please remember what we see here and we took a few videos ago that images that we are familiar with。

 it's just a very small part of the spectrum of images that we can acquire at different wavelengths and with different modalities and the concepts of sampling and quantization are relevant for basically all of those modalities we always going to have to sample。

 we are always going to have to quantize but again it's good to have in mind when we talk about these different ideas how they apply to the images that we are most familiar with which are the images from our own digital cameras。

So the basic idea is just follows。We basically have light。Basically， reflecting。On the objects。

 and the light is reflected on the objects， goes into the camera。

And what we have are sensors in the camera。As we can see here， remember， in our eyes。

 we have the retina and the retina hard cons and roads。 Those were the sensors in digital cameras。

 we have sensors exactly the same way as we have sensors in our eyes。

 So this is just one example of a sensor。 The energy is coming in。 there filters。 and then basically。

 the energy is acquired and is transmitted。 So the energy sense and transmitted。 And normally。

 what we're going to have on a regular camera is the two dimensional。😊，Aray of these sensors。

 So each one of these is going be one of these。And normally they are arranged in a square or rectangular fashion as we see it here。

 So we have actually kind of a discrete number。 And that's when we go and by each cameras。

 we hear that this is about 1000 by 1000。 It means actually we're going talk a bit more about that in a second。

 it means that we have 1000 sensors in this direction， 1000 sensors in this direction。

 So a total of 1000 square sensors。 So once again， light is reflecting objects is projected into the camera and it sense by the camera。

 but all the process has a step of thisization。Some of you might be more familiar than others with these。

 those of you that took classes in digital signal processing and are aware of A2D converters。

 this will be very simple and very familiar to you。

 but let's just review it for those that are not so familiar with the concepts。



![](img/c705bf9a26be1286adf52a82793b77bb_3.png)

So we see here the light。Represented here。Is reflected from the object。

And it goes into the sensing device。 Think about your digital cameras。So this is a blown up。

Of what we have back here。It looks。 the object is continuous space。 Everything is continuous。

 but we actually get a discrete representation of that object。

 and the disctization applies in two different directions。 One is a spatial discretization。😊。

So we have a discrete number of sensors here and basically the light。

 One of the simplest modes is that we integrate each one of these integrates delight light arriving to it。

 So that's a disctization in the space。 There's also this critictization in the amplitude。

 We are not going to be able to capture every single level of grade every single level that is reflected from the object。

 but we're going to have to discretize it as well。 So let's see， let's talk a bit more about that。😊。

This is the object， as we actually see。And let's just look at one line。Across this object。

 So we see that there it has different values。 It goes from white to gray。

 So let's just now draw the profile， which is what we see here。 So it's very light。White。

 and then it becomes a bit dark。 And if we see here。

 let me just erase this so we can basically see it more clearly。

If we go around I'm going to just mark it here， if we go around， we see that it's going for white。

 then it's dark， then it just becomes brighter a bit and goes down again and then it's white again。

 So it has kind of this profile。High is white， then it goes dark and then goes up down。

 and it becomes white again。 Of course， it's not perfect。 It has a noise。

 even when we go and buy paint and paint a wall， basically， we think that it exactly the same color。

 Basically actually not。 It has in small variations which are represented here。So again。

 there are two processes happening here。 One is sampling。

 We are going to basically look at the values at certain discrete interval。

 We are not going to have the values all around。 We' are going to have it at certain interval。Okay。

 that's one disctization。 The second disctization is we're not going to be able to represent every single possible value here。

 We're going to basically just represent a few of them。 We're going to round them。

 So let's just give an example。 a very simple illustration。 of how can we round。

Let's say that we see the value，17。5。So basically， we see that this is the value that is representing a particular gray value here。

So how can we round this， One way is just to truncate it like this。And then basically say， you know。

 I know that what came into the sensor is 17。5， but actually I' going to represent it by 17。Okay。

So there are more ways of doing this and we're going to talk in detail about quantization。

 this is sampling and discretization in this direction of the gray values is called quantization we could also consider。

 for example， if we had 17。5 as before， we could actually divide it by 2。Take this and multiply by2。

So basically if we divide by2， then we round， and then we multiply by 2。

 and I'm going to just ask you as a very simple exercise， what's this value？

And what will happen if instead dividediding by2。We basically， for example， divide by 4。

Round down and then multiply by 4。안 한 거는。Have you think about this is a simple。Arithmetic operation。

 we' are going to discuss a lot about this particular operation in the chapter on quantization。

But to recap， we have two ways of sampling。 One is the two basic ways of thisization。

 One is sampling in the special domain， and the other is quantization in the gray values。

 So the basic idea is that while we have。Started from a continuous object。

That basically lives in the whole space and has multiple gray values end up with a discrete object that has disc discretization both in the spatial domain and also in the gray values。

The whole idea of good digital cameras is to have a dense enough sampling here and very。

 very fine level of quantization。 So we don't notice that everything is discrete。

 but it's actually it is discrete。 So we have pixel values。 each one of these。😊，It's called a pixel。

This comes from。Picture。Element。And is the note as pixel。And actually I'm going to just。

 if you want to Google or you want to search on the web be I'm going to just。

 you might find it entertaining to find out who basically was the first person to use the term Pix it actually a very famous statistician。

 and you can have fun looking for that on the internet。Or discuss about that on in the blockss。

 when you find out about that。 So every one of these is discrete。

 both in space and is discrete also in its great values。 And that's how we get pixels。

 And once again， the more we have。Of this。 and the more we have of the levels。

 the better the image it is。 So regular images will be， for example。256。By 256 spatial domain。

 That will means that it will have 256 square pixels， and maybe it's represented by。8 bits。

So every pixel is represented by a bits， which means that it can have。

 it can represent 256 different gray values， and we' are going to see how important this is。

 both the spatial disctization and the quantization of gray values are extremely important。

We can have better images。We， let me just go back。We are going to have， for example。

 we might have an image that has instead of 256 by 256， it might have 5，12。By 5，12。And still。

256 levels。 So it's going to take more memory to save that image。

 but it's going to have a better quality。😊，And once again， when you're buying digital cameras。

 they normally tell you a lot about this number。 how many pixels it has。

 And that tells you how fine the sampling is。 We want a lot of pixels。

 So there are so close to each other that we can actually believe that is a continuous domain and the same at the level of the gray values。

 So once again， when each one of these is a pixel and is represented by gray values。😊，Now。

 this is a black and white image。 We actually in our cameras， we have color images。

Color images are represented by three of these images， one for red。1 for green。And one for blue。

So basically the cameras acquire， I'm going to explain a bit more about that in a second。

 acquire three images， one represents the blue colors， how much blue there is in the scene。

 thearrow represents the green and the other represents the red and this is called red。Green。

And blue。 So you often going to hear images which are R， G and B。

I should make one comment about this。 most low end to medium end consumer cameras。

 they actually don't really capture full two dimensional arrays。For each one of the colors。

 So we would like to have。Each one。Red。Green。I blue。That that's why we would like to have a red。

Green。And' blue。That would be the ideal scenario， and the more expensive cameras actually do that。

 basically they capture three full images。Most consumer cameras， if you buy a low and digital camera。

Actually， there's something slightly different。 something that is called mosaic。

And the basic idea is that it captured the pixels。With inter living in the colors， we capture a red。

A green， a red， a green and so on。 And here it will capture。A red here。 A blue。Blue。Red and so on。

 So the next one will be red， green， red， green。 the next one will be。Blue， red。Blue。Right。

So actually it's not having the triple amount of pixels， is's actually having one pixel red。

 one green， one red， one green from this。 we' are going to have to interpolate and that we are going to learn how to do those things in the third and fourth week weeks in this class we are going to have to go because to represent a full color image at every pixel we' are going have to go red。

 green and blue So we do have the red。 we're going to have to create somehow the green and blue and that's done from the neighboring pixels here we have the green。

 we are going to have to create the red and the blue。

 so we are going to have to complete the three channels to be able to see a color image。

When you buy digital cameras， they actually normally tell you。The size on this。

 which is the size after they have done that interpolation， although they as as I say。

 the regular consumer images capture this， so they actually capture one third of the data that they tell you that they are given to you。

 that the data they tell you they are given to you has been interpolated from what has been captured。

So we have discrete images。 We have a red， green and blue channels。

We're going to think about them as red， green and blue。

 so we already went from this representation to the interpolated， by the way this is called mosaic。

So that's how color images are created。 Now how are videos。

 So this is how you have a color in your an image in your computer， you have three channels。

 three arrays of two dimensional discrete values， one for red， one for green， one for blue。

 So what happened with videos。Videos basically repeat this。 So one image has red。Green and blue。

 And what happened in video， you have multiple of these。 For example。

 for one second of video in in some of the formats， you're going to have 30 of these。

So you only have 30 times。R G and blue。And each one of these remember is one of these two dimension structures。

 So basically， if you are having， if you want to have one second of video in your computer。

 you have 30。Times three images， 30 images in one second and three because you have three colors。

 so in one second you're going to have 90 images of this type to represent one second of video。



![](img/c705bf9a26be1286adf52a82793b77bb_5.png)

And， of course，90 images。 So let's say，90 images at a resolution of 5，12。Times 5，12。一。And 8 beats。H。

 so this is。What you need to represent at relatively low resolution。

 this is not very high resolution， this is pretty standard。

 but basically this is what you're going to need to represent one second of a video in your computer。

By the way， instead of saying that it's three times a bits， three times because we have RGB。

 sometimes people will say that our resolution is 24 Bs。

 So we use 24 Bs to represent basically a pixel。OkaySo this is how you have if you go now to a computer that knows how to deal a program that knows how to deal with images。

 you're going to see basically twodimensional discrete arrays as many as seconds or frames you have in your image each one of these 30 is called a frame and you have 30 of these in a second or 30 images when we talk about still images we talk normally about images when we talk about videos each one of these we call it a frame。

So this is how your images are represented， let's just look a bit more about how important and what are the effects of your resolution in space and your resolution in gray values。

 meaning how many pixel you' are going to have and what are the gray values that you're going to use for them。

So this is again the same type of representation。 This is how one color of one image or one color of one frame is represented。

 If you have the letter D， then these pixels are0 when we have8 bits。Normally，0 is black。

And one or 256，255 actually is white。So if you are going with a bits， you can go from 0 to 255。

0 is black， 255 is white， sometimes the 255 is called1 if you want to talk about the integral between0 and 1。

 so although you see this，Actually， in the computer is represented by a bunch of zeros for the black region。

 then let's say that this region is in the middle of the gray value。

 It will be an equivalent of a 128 value or a 0。5 value。 So we see here 0。5。

 and then  one for basically the whites。 So this。Is your。

Discrete representation of this image in the computer。Okay， at every pixel。

 you have a discrete value。

![](img/c705bf9a26be1286adf52a82793b77bb_7.png)

Now， sometimes one of the things that happen is because you have only 256。

Different levels that you can use， sometimes your image is too bright and you might not be able to represent the small variations in brightness there。

 remember the human visual system can basically adapt to multiple level to multiple levels of brightness。

 but not all of them at the same time， the same for an image， we can capture many， many levels。

 maybe 256， but if we have to deal with a very dark region and a very light region at the same time。

 we are in trouble。And sometimes the very small variations in this light region we are not going to be able to capture。

 and that's called saturation， so it's going to look all white。Because it all got to the 255。

 maybe it was above 255s。 It wanted to be above255 because it was very bright。

 So that happens very often we take images and sometimes we see what's called specities or very strong reflections and it looks wide。

 it looks very， very light， and that's because the image the sensor has saturated。

 So this explains now you know why that is happening。 you have a discrete amount of levels。

 a discrete amount of values to represent your image。

 and this went above and beyond what you can represent with that discrete amount of values。



![](img/c705bf9a26be1286adf52a82793b77bb_9.png)

So again， to these criticizations， one in space and one in gray values， and look what happened。

What's the effect and you know that because if you have digital a camera or if you see images on the web on the internet。

 you see images a different resolution so if you were to use a lot of pixels。You might see this。

 So this means that you have something which is very， very fine。A lot of pizzas。

And that looks really nice。 On the other hand， if you have something which is much more。😊，Course。

 less dense。 So you have less pixels。 You're going to see something like this。

 And it's very clear to see， for example， how you know， this line is very nicely represented here。

 is not so nicely represented here。 you can see various easily the small numbers here。

 not so easy see here。Look at these numbers here。 They are not so clear here。

 So here we only have changed this patient resolution。 We have not changed the number of gray values。

Still， let's say we have 256。 So each one of these is represented with 256。

 and each one of these is representative of 256， but we are not able basically to represent so fine detail with this as we are with this。

 And you can think about once again， if I want to draw a profile。



![](img/c705bf9a26be1286adf52a82793b77bb_11.png)

If you want to represent something that has this profile of gray value。

And you actually wan to discretize that。If you do it very coarse。

 you' are not going to be able to detect that there is a smooth variation in the gray values。

 but if on the other hand， you're able to put many more layers。

You're going to be able to capture its value at many， many points。Instead of just add a few。

 let me just use a different color。Just as a few。Values， if you do a course disctization。

 and that's why this image doesn't look as nice as this one because this capture what was going on at a very coarse level。

In the discretization， in the space discretization。Now。

 similar things happen if you basically do a very co disctization of the gray values。

 So let's just start。And once again， we are not changing the number of pixels。

 All these four images and the four images that are going to come next have exactly the same number of pixels。

 Okay， so actually， it's written here。 It has 452。 I'm going to just make it larger。Times 3，74。

 all the images。But the first image is displayed with a bits， meaning 256 values。

So I'm going to just write it。 Maybe I'm going to just say it here。 The first is 256。

 And we actually see it very， very smooth and very， very nice。Here we only use 7 bits。

Or1 hundred twenty8 values。So， basically。The value 0 and1 becomes 0。2 and 3， become 2。4 and 5。

 become 4。Okay， the easiest way to do that is you take every value here。 let's say a value。

You divide by two。You take basically the closest integer from below and you multiply it again by  two。

 Okay， so， for example， it's the value of this image。Was it。You divide by 2。You take。Divide by2。

 basic divide， sorry， divide by2。That4， okay， you multiply by 2。You got8 again。

 No problem with that pixelel value。 Okay， but what happened， let's just do that here。

 What happened if you have 9， you divide by2。That's 4 and a half。

 I have to take the closest integer from below。 That's 4。I multipied by2， and it became 8。

 So a 9 was transformeding into an 8。And that basically reduces the range and reduces the quality of the image。

This becomes even worse。If we go into this region where we are actually only using 64 different values。

 So that's equivalent basically to dividing by 4。Then truncating and multiplying by4。

 And that means that you're going to start talking about basically， if you have only 64。

 every four values are represented with one number。 So 0，12 3， they all become 0，4，5，6，7。

 They all become 4， and so on。 And then you can keep going。And this is only represented with 32。

 so I hope that you are starting to see that equality is deteriorating。 in particular。

 if you look at lines here， you start to see what's called false contours。

 you see these lines that theyre not clear here。 there is a smooth transition here。

 but here you see these false contours。And that's created because of these jumps that I mentioned to you。

 So if you were going basically 1，2，3，4， it's actually youre going to when you start taking very。

 very few gray values。 you're going to go0，00，0，4。 you're going to jump into that value and that's because you are basically have much less resources to represent the different gray values。

 You're just going into an even more extreme case and we keep going down here basically we use only 16 and now I think that you're going to be able to see。

The false counterours， very clearly。Here we go basically only to eight values。

There's only eight numbers to represent everything that is happening in this picture。

 and that's very a very strong quantization here there is basically only four。

 and here is very only two。In this very extreme case， everything that was below 128 became 0。

 became black。 Everything that was above 1，28 became2，55 white。 And then you see a very， very。

Porol quality data。Okay， so that's how the special quantization and the gray value， special sampling。

 sorry， and the gray value quantization affect you。 The more you have of samples。

 the better quality it is， the more you have。The possibility of represent many， many。

 many small variations in great values， the better it is， of course。

 the more memory it takes into your computer。 And that's going to be the subject of our compression unit。



![](img/c705bf9a26be1286adf52a82793b77bb_13.png)

So now we know how images are representing in the computer that represent as two dimensional arrays。

 gray level images are represented by one。Color images are represented by three， red。

 green and blue V are represented by multiples of them。 let's say 30 a second。

 Sometimes it's only 24 depending on the standard that that we have but there are multiple of those images and as we say we call them frames and we know that everything is discrete。

 so we have sampling and quantization an image in a computer is nothing else now that the two dimensionsal array of discrete values。



![](img/c705bf9a26be1286adf52a82793b77bb_15.png)

Thank you。😊。