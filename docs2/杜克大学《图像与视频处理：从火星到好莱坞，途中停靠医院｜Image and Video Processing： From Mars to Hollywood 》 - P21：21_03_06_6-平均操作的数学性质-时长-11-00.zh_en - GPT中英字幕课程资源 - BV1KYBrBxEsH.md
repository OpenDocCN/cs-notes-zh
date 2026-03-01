# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P21：21_03_06_6-平均操作的数学性质-时长-11-00.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Let us just present some very interesting， very simple and very interesting at the same time properties of meme filtering basically local averaging。

 let's go right ahead into that。

![](img/3594721c8c1d34e81b7285278db1f42a_1.png)

嗯。So you see here the title averaging Gaussian filter and heat flow。

 And we're going to explain all of them。 But I just start with something very simple with a very simple exercise。

 Let's assume I give you three numbers one。2。And 3。And I'm asking you the following question。

 I'm asking you to find a number a。Such that a-1。Square。Plus。A minus-2 square。Plus。

A-3 square is as small as possible。Find that number and I'm going to basically ask you if you need to do a lot of computations。

 I'm going to ask you to say no， I don't know how to do this fast so youre basically gonna to have the following options to say no。

 I don't know how to do that immediately or fast or yes and then so one is going be no there is going to be yes。

 if you know how to do it very fast very fast I mean in your head with basically no pencil nothing。

 you can say yes0。Yes。2。Yes。4， okay， let's see if you know the answer to that。Okay。

 let's explain the answer is。2。How do I know that Because it's the average of these three numbers。

The smallest number that will minimize this sum is the average of these numbers。

 This is a very interesting property that in general， reaches as follows。



![](img/3594721c8c1d34e81b7285278db1f42a_3.png)

If I give you a set of numbers。Which are， let's call them A I， A sub I。

 And I'm asking you to find the number a such that the sum for every I of a minus A I。Square。

Is as small as possible。The result of this is the average of a， so。The number I'm looking。

Is the average of all the numbers that I have， so you basically sum the numbers and divide by the total number of AIs that you have。

It's actually all very hard to prove that if you remember some of your calculus very early calculus。

 so you basically define this as a。And。😊，And you take the derivative of this with respect to a。

 you make that derivative equal to 0。 and going to find the result is basically the average。

So this is very interesting when we are taking in an image。Let's say a three by three average。

 I'm replacing this by the average of all the nine numbers here。

 What I'm actually doing is I'm replacing this pixel value by the number that minimizes the square error。

 Okay， so this is kind of the means square error。 Remember。

 we talk about that when we were doing compression。

 A very simple operation once again that you can prove just by taking derivatives。

 So that's one interesting characteristic of the mean。😊，When we are doing image processing。

 we are basically finding the value that replaces that。 This is going to be very interesting。

 We're going to see in a few videos ahead that by replacing this way of measuring the error。

 we can get other substitutions of this。 So this is one of the properties that are very interesting of averaging。

 Let's look at the different property。

![](img/3594721c8c1d34e81b7285278db1f42a_5.png)

So once again， remember that what we are doing is averaging。



![](img/3594721c8c1d34e81b7285278db1f42a_7.png)

In a window， it can be3 by3，5 by5。10 by 10， its just a window。

 So what we are actually doing here is convolution for those that have a bit of background in signal processing。

 that wouldn't be surprised。 but I'm going to be basically explaining。

ACan a slightly different operation for convolution。

 So the basic idea is what we are doing is we are taking our image。X， y。And we are convlving it。

With a filter。And let's just conve it with what's called a Gaussian filter， just a Gaussian function。

That has。Average0。And some variance。And remember， a Gaussian function looks something like this。

M came is one of the most simple functions we know。 So that's a weighted average。

 So in a discrete fashion， we will basically， instead of just putting 1，1，1 every place。

 we will basically replace by the weights provided by the Gaussian。 So that gives us。

Another function， which we're going to call X， Y sigma。

Because depends on the variance of the Gaussian this function。

So we could actually take a regular average， but it's nice or its more elegant if I explain this with the Gaussian filter。

 so what we are doing is we are doing a weighted average。

 we are replacing the pixel by a weighted average around it。That's all what we are doing。No。😡。

This function is very interesting。 once again， x Y sigma because depends on the variance of the Gaussian。

So let's just write something interesting here。 You might remember what's called the heat flow。

 If not， I'm going to explain it to you。 I'm going to just write it down and explain it to you。

 So we're going to write， and I'm going to use the same notation on purpose。 So I'm going to write。



![](img/3594721c8c1d34e81b7285278db1f42a_9.png)

That。The function F。Its changing in time。So I'm going to write the derivative。

 changing in time according to what's called the Laplaceian of F。

Which is equal to the second derivative of F。With respect to X。Plus， the second derivative of earth。

With respect to why。So the image is changing according to the Lalaian。

 So I basically look at the change in the x direction。I do the second derivative。

 look at the change in the wide direction， second derivative so double the change and basically this is the heat flow and if you remember some basic properties of the heat flow it basically talks about diffusion so you have heat in a room and the heat diffuses in the room if everything is isotropic。

 nothing can stop it， it diffuses according to this equation。Now， why did I write this。

Because the Gaussian filter actually satisfies this equation。

It's actually something very interesting。And exactly actually depends on the time。

 So the more you let this diffuse is equivalent to having a larger sigma， a larger variance。

 So once again。

![](img/3594721c8c1d34e81b7285278db1f42a_11.png)

The result of doing this local averaging with the Gaussian filtering is equivalent to the result of taking the image。

 thinking like the pixel values， the gray values are hit and let it run according to the heat flow。

 which is this， and those are equivalent operations。



![](img/3594721c8c1d34e81b7285278db1f42a_13.png)

![](img/3594721c8c1d34e81b7285278db1f42a_14.png)

So if I let it run for certain time， once again， the pixel values are hit。

 It's running for certain time。 That's equivalent to picking in a certain variance that depends exactly on the time。

 and applying a Gaussian filter to the image。 So the pixel values are diffusing in the same way as the heat flow is diffusing Hi。

 Those two are basically equivalent thing。

![](img/3594721c8c1d34e81b7285278db1f42a_16.png)

![](img/3594721c8c1d34e81b7285278db1f42a_17.png)

Once again， it's not very hard to prove that。 And if you want to do an interesting exercise。

Replace F by this expression。So basically， take the derivatives， don't do derivatives according to T。

 do derivatives according to sigma。 and here do derivatives according to x and to y。

 and you're going to find that this。Satisfies this equation。

And that's because of derivatives a linear， so this is a linear operation and if you're not very familiar to how to do that。

 just consider that as an extra exercise for those that want to go a bit deeper in the math for this particular video。



![](img/3594721c8c1d34e81b7285278db1f42a_19.png)

![](img/3594721c8c1d34e81b7285278db1f42a_20.png)

And now， why is this interesting is because， as we're going to see in a few。Weks ahead。

 somebody might ask， okay， now you just told me that local image processing is related to heat flow。

Maybe I can design a different equation here that will do other interesting things into image processing。

 And we're going to see that that's possible。 And again。

 that's going to be a bit mathematically more advanced and is going to happen in a few weeks。

 So we have seen a couple of interesting properties of this local averaging。

 One is that its kind of computing the means the value that minimizes the means square error in the region。

 And the second that there is an equivalence between pixel values and hit。

 and what this local averaging is doing is diffusing the pixel values。

 And that's why also is bluring the image。 If you remember。

 we saw that it's blurring it because it's diffusing them。 And we know that， again。

 that happens with heat if you start with。Hot in one place and cold in the other。

 the heat flow will diffuse the heat， and will become more uniform。 Of course。

 if you wait for a long time， which is equivalent using a very large variance。

 What we get is basically the mean value。So you're going to basically get the average in the whole image。

 So once again， a couple of interesting properties about the local averaging next。

 we're going to see a different type of local operation that will actually help us not to blur the edges。

 See you in the next video。 Thank you。

![](img/3594721c8c1d34e81b7285278db1f42a_22.png)