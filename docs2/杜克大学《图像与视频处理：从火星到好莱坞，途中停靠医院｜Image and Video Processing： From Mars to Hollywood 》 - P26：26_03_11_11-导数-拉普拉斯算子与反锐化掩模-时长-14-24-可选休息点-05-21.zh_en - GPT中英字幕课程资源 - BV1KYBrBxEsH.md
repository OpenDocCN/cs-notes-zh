# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P26：26_03_11_11-导数-拉普拉斯算子与反锐化掩模-时长-14-24-可选休息点-05-21.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

![](img/cccbefd12bac87e399ca35be2988cba1_0.png)

Hello and welcome back to our image and video processing class。

We have seen very interesting effects that we can obtain in images just by doing these very。

 very simple local neighborhood operations， let's use this video to see a couple of additional ones in particular we're going to talk about derivatives how we implement those derivatives with local neighborhoods and what important are how important are those derivatives to do very。

 very interesting effects in images， so let's dive into that。Here we have a picture。

 It's a one dimensional image that has flat ramp， flat and a very， very sharp jump and flat again。

 And let's see what happens when we take the derivatives of this。 I have drawn this here。

 But before that， you might ask yourself， derivatives。 That's a continuous operation。

 How can we implement that in our computer。 There are many， many ways of doing that。

 But let me illustrate a very simple one。If I want to take the derivative。Of an image。

In the next direction。I can basically write that in discrete fashion as F。

Add the pixel X plus1 minus F。Ex。Very simple。 I just sub two consecutive pixels。

 If I want to write the neighborhood operation。Let's say in a3 by3， that will mean fx plus 1。

 I have a1 here， minus fx， I have a minus1 here， and every place else is 0。

So that's basically how I represent that。 I get a one dimensional derivative in the direction。

 Similarlyly， I can get a one dimensional derivative in the y direction。

 So we see here the simulated values of this ramp， flat jump and flat。 So we start with flat6。

 we have a decreasing ramp。Flat one。 And then a big jump。

The first derivative is this first row that we see here。

 Very easy to compute following this operation。We have actually a couple of zeros because there is no derivative。

 The values are constant。 Then basically， we have a -1-1。

 That means that the pixel values are decreasing in jumps in constant jumps of one。 It's negative。

 So they are decreasing。 And then once again， we have flat。

And then there is a big jump here when we do 6-1， we're going to get 5 and then it flattens out again。

 so we already see that considering the first derivative， we can understand that， for example。

 there is a ramp as smooth decline of pixel values， and then there's a big jump。

 very interesting with a derivative we can detect jumps as we expected。

Then we can take actually the second derivative。 And once again。

 we can write an explicit formula and a mask for the second derivative。

 So we are going to do the second derivative of our image once again in the next direction。

And once again， there are many ways of implementing this second derivative。

 but one of them is to take F。At the express one。Minus a。Adds -1， and subtract。Two times。哎。

At the actual P。 And that's once again very simple to do with our ubiquitous。3 by three。

 now we have a minus2 here， a1 and a1 on each one of the sides representing these two。

 and then we have0。Every place else。And。If we do that。

 so that's kind of an additional derivative to the first derivative。 It's a very simple exercise。

 We are have to take derivatives of these。 We could directly。

Apply these to the original one if we want， but it's easier just to take you know continuous pixels abstractions to the next one。

 And we see jumps when there are big changes。 So 0 -0， it's 0， for example， -1。- -1， once again0。

 But when there are changes， we see a jump。 We see one here。We see another here。

 So the second derivative very clearly marks when there are big changes in our image。

 and that's extremely powerful。 We are detecting big changes by doing derivatives which are at least in their simplest fashion implemented with masks like this one。

 So let's just continue with this and see some of the examples in a second。

Here are different masks that compute different types of derivatives。 So I'm going to ask you。

 look at this mask， for example， and tell me， what is this mask actually computing。

Is it computing the third derivative， for example， in the x direction。

 is it computing the third derivative in the y direction or is it computing the sum of the derivatives in the first derivatives in the x and y directions。

 or is it computing the sum of the second derivatives in the x and the second derivative in the y direction？

An interesting property。 So what is this mask implementing。

I thought that that wasn't too hard for you， so I gave you that as an exercise。

 but I just write it down。This is actually computing the sum of the second derivative in the x direction and the second derivative in the y direction。

 So this is computing the second derivative of F。嗯。In the direction， plus the second derivative。驳位。

Of F， I apologize。In the y direction， and that's basically we know either from the previous slide because we can compute the second derivative in x and the second derivative in y and add them。

 and we actually know that that's basically F。At X plus  one。Mus f。At x-1。-2 F。An x。

And I'm not writing the why because they haven't changed。 It should be it why， why and why。And plus。

 so this was x。 And now were going to do Y thats。

![](img/cccbefd12bac87e399ca35be2988cba1_2.png)

诶。At Y plus 1。Plus a。At y -1。- two times。哎。At y。 And once again， all these are for a constant x。

 So all these。R， for a constant y。And all these are for a constant x。 When we add them， we get this。

 And this is actually。What's called the lapplaceian of F。

 And we briefly talk about this when we were talking about the relationships between averaging and the Gaussian filtering and the heat equation。

 So this is what's called the lapplaceian of the image is the sum of the second derivatives in the x。

 and in the y direction。 This are different implementations of the lapplaceian here， for example。

 we make the difference even stronger We stretch it。 and we are going to see the effects of that。

 The basic idea is that in the surrounding basically， we have one sign and in the pixel。

 we have a different sign。 and we are basic computing in that way， second derivatives。

 just different implementations of this type of second derivatives。

 So what are the effects of this in an image。 Very interesting。Here we see。An image。Of the moon。

What we see next in this image is the lapplian is the second derivative index the direction plus second derivative in the y direction。

 and we actually see it implemented with this。Here we basically just stretch it。

 Remember we know how to modify Instagrams， so we are stretching it。

And what we are doing next is we are adding this。To this。So we basically take an image。

Takes thelalaian。We stretch it， and then we add them， and we get this image。

 which you can observe That a bit sharper。 Basically， some of the details are much more clear。

In this image， then there were in this image。Now we can actually make those details even more clear by computing a applaian that takes in contrast with only a -4 a minus8 since it actually stretches the differences even more。

 The process will be the same。 We take the image。We compute the laplaian with this at every pixel。

 so every pixel is replaced by minus its own value and plus the values of the surrounding pixels and in that we add to the original image and look we have a very sharp rendering of this image you see a lot of details here that were very blurry here。

Very simple operation image plus its laplaian gives us a very， very nice effect。😊。



![](img/cccbefd12bac87e399ca35be2988cba1_4.png)

Many， many of these combinations can be done。 And here we see another example for a different image。

Again， an image that looks a bit blurry。We see once again， it's lapplian。 It might be hard to notice。

 All what we have done from here to here is once again to take second derivatives。

 And then we add them and look how much sharper。This image is than this one。Much， much sharper image。

 we can see a lot of the details that were not very clear here by a very simple operation of adding the image to its lapplian。

 and here we see basically what's called the Sopo edges that are basically a different way of computing these derivatives。

So very interesting effects in images by combining derivatives with the image in different directions。

 additions of derivatives， very， very interesting effects。



![](img/cccbefd12bac87e399ca35be2988cba1_6.png)

One of those effects is what's called un sharpharp masking。 It's a very， very famous concept， very。

 very simple。 It's called an。Sharp。Msking， we have it here。 The idea is very simple。

 You take the image。And you smooth it out。 For example， how can we smooth an image。

We already know many ways of doing that。One of them is by doing local averages。

 so that corresponds to a mask produce all ones。And you know， one over9， just to basically normalize。

We do that， and then we sub the original minus the blurir image。

 Now what's the mask corresponding to the original image。Very simple。A mask。That does nothing。

Has a one here and a0。Every place at。So original image is this mask， B image is this mask。

 we take the differences， so it's this mask minus this。We produce this。Remember signs。

 So if I sub from this， this， I will get that0 in the middle， and I will get。Basically。

 I won't get a zero if I normalize， but I will basically get。89， if I do the normalization。

 but a positive number， and every place else， I will get minus19th， a negative number。

 That's kind of a derivative as we saw before， kind of an implementation of derivatives in the horizontal and vertical direction combined。

We take that result and we add it to the original image。And look what we have。

 we basically are enhancing the boundaries， as we have seen in the previous examples that basically things become sharper because。

What we managed to do with the blaring was reduce the boundaries。 And then when we add that back。

 we get sharper boundaries and a very sharp image。 And that's what that's called unharp masking。

 a very simple operation and very powerful as well。



![](img/cccbefd12bac87e399ca35be2988cba1_8.png)

So I want to conclude this video in actually in the next video by showing you once again inside Matlaav how we play with these type of operations of smoothing adding images。

 very simple operations that produce very interesting effects in our images。

 so see you in the next video with the Matlave demonstration。



![](img/cccbefd12bac87e399ca35be2988cba1_10.png)