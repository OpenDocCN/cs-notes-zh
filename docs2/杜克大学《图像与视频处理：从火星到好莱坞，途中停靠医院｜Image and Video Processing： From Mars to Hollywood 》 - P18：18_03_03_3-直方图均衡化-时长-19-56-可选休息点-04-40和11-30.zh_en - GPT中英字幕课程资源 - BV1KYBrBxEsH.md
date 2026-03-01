# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P18：18_03_03_3-直方图均衡化-时长-19-56-可选休息点-04-40和11-30.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back to our image and video processing class In the previous video we saw on real time isst equalization。

 We saw how it improves the image and how we managed to get a non uniformform Instagram and make it a uniform Instagram。

 So let's see in detail how we do that。 I'm going show you exactly the math behind that。

 And you will see how simple it is。 you will be able to go right away and program that in your own computer if you wish to do so。

 So let's just dive into it。

![](img/499aeea51b9aff472aa57ad351ba05aa_1.png)

So first of all， let's just go again and talk about Instagramograms Here we see a very dark image and here we see the Instagram as we see most of the distribution of the pixels value of the pixel values are in the low end of the Instagram。

 there's not a lot of bright values and we see that the Instagram basically there the count of pixels there is very。

 very low here we see the other way around a very bright image and most of the count is in the high part of the Instagram so there is not a lot of pixels with low values。

Here we see Canite gray， low contrast image， and then we see that the pixels are actually concentrated in the middle。

 Well here we see an image that looks much nicer。 These are all the same images。

 but this looks much nicer。 And we have canite uniform distribution。

 We are occupying the whole space of pixel values， more or less uniformly。

 and then the image looks much， much nicer。So we want to be able to learn how to go from a distribution like this。

To a distribution like this。 And again， as I say， it's a very， very simple operation。

 as we're going to see in just a minute。

![](img/499aeea51b9aff472aa57ad351ba05aa_3.png)

So our goal is to go from a given distribution to a uniform distribution。

 assuming that our pixel values can go from 0 to L minus1， for example。

 standard L is 256 so we can go from 0 dark to 255， very bright or white。

And we want to get a uniform distribution。 So basically the probability。

 or if we don't normalize the count， but let' just think normalize is just easier。

 The probability is one over L -1。 That's basically the probability of having a pixel achieve that gray value。

 So we want to go from this。To this， that's basically our goal。In order to achieve that。

 what we needs to find a transform that takes basically the pixel values of the original image and transforms them to pixel values of a different image。

 So having an image。I need， basically。To decide for every pixel in the image。

 I want to see its value， and I want to transform it to exactly the same place。

 but with a new value and remember so far we are only making decisions based on the pixel value。

 not on the neighborhood， just on the value， the value 7， we need to decide what we transform72。

 regardless of what are the pixel values around it。

So we need a transform that takes us from any pixel value to a new pixel value in such a way that we get a uniform distribution。

 There's gonna to be one requirement of this transform。

 and we're going to make an increasing transform。 And the reason is we don't want to reverse pixel values。

 So we want this to be a monotonic increasing transform。 If 7 goes to 10，8 should go to a value。

 at least 10 maybe above 10， but we don't want 8 to go below 10。

 and then we actually kind of flip the content of the image。

 and that's not the intention of histogram Qization。

 So we're going to have increasing functions and finding these function is our goal。 Now。

 sometimes we have strictly monotonic increasing functions that every pixel values goes to a different pixel value。

 Sometimes we have an increasing function。 It monotonic。

 but some of the pixel value might end up with。T target。

 And we will see that that will happen in instualization。 in particular。

 when we work with discrete images and discrete pixel values。

 So we are going to end up with a transform of this style and not a transform of this style。

 That's basically a problem with istualization in discrete computers by something that we must have。

 We cannot avoid， as were going to see next。

![](img/499aeea51b9aff472aa57ad351ba05aa_5.png)

So how do we achieve this。

![](img/499aeea51b9aff472aa57ad351ba05aa_7.png)

The basic idea is very simple。 we can think about an Instagram as basically a distribution S。



![](img/499aeea51b9aff472aa57ad351ba05aa_9.png)

So this is where you need a little bit of background in probability， but don't worry。

 because even if you don't have that background， I think it's going to be almost selfexplanatory what I show next。

 So we have a distribution， the Instagram is nothing less than a distribution What's the probability of a given pixel value。

We have， we want to obtain a new one。 We actually have the current one。So basically， we have a new。

 a different distribution。And remember， what we are looking is for a map。From our。To s。

 we are looking for this transform。 So it turns out this is a basic result of probability that if we have such a map。

 then the relationship between these two distribution is as follows。This is the relationship。

 So the new probability distribution is the old probability distribution times the absolute value of this derivative。

That's a well known result from probability distribution and it's all what you need to understand the rest of the derivation。

So let us assume for a second， and I'm going to prove you that this is the transform that we are looking for。

Let's assume for a second that this is my transform。So S is a transform， So from any pixel value。

 I will get a new pixel value。And let's write it as L-1。Times， the integral。From0 to R。

 and I'm going to explain the actual interpretation of what I'm writing in a second of the current Instagramogram or current probability distribution。

PW， D W。 So what am I doing here I'm basically integrating the mass。

 the number of pixels that achieve a given gray value from0 to R。

And then I'm doing this because I'm using probability functions。 So I'm normalized between0 1。

 and I want to get back gray values。 So let's look again at the transform。

 You count if we are in a discrete space， you're going to count if you want to know。

To which pixel value should I transform the value R equals 7， you count how many pixels are at0。

 how many at one at 2 and 3 and so on until 7， and that gives you the transform I have to prove to you that this is the right transform to do histogram equalization。

 so let us do that。In order to do that， I'm going to compute this derivative。

 and the basic idea is very simple。 So we are going to actually do D S。D R。

 now we have the explicit transform here so we can compute this derivative is basically。D of T， R。DR。

 and we have here the expression。So it's the derivative。

According to R of this expression that we have here。E -1。Times stay integral。From 0。To our。PR。

D video。The w。I apologize that the lines， the rows are going one on top of the other。

 but I think it's very clear。 So we need to compute this derivative。If you remember basic calculus。

 this is a constant， So it will go out Okay， and then the derivative of this integral is what's inside the integral。

 So this is equal。To L -1。Times， and I'm going to write this here in the next line。P。😊，A。2。

So we obtain that the derivative of s according to r is L minus-1 times the probability basically the original intogram。

 Now what we are going to do I'm going to raise this in a second but what we are going to do is basically include this here and see what happens so I'm going to pla this in here。

 but look what we have here we have Dr Ds and I have here Ds Dr。

 so we need to invert that it will be one over this。

 and I hope that you can see what's going to happen So let's see actually what's going to happen。

Again， we have。P。The new probability that we are looking。Is the all probability。D R， D， S。

 absolute value。We computed the RDS just a second ago。 So this is PR。2。

The absolute value of one over。L， -1。That was our word normalization。BR2。Now。

 probabilities are positive。And this is positive， certainly positive because L is greater than one。

 so I can get rid of the absolute value。 And then I see that these will basically cancel with this。

 And I got one over l -1。 And that's exactly what I wanted。😊。

Exactly what I wanted is to have a uniform。 a constant probability distribution for my new image。

 Okay， so once again， I'm going to write again what's actually the the actual transform is。

Which is a map of R。Is L -1。They integral from0 to r of the original probability distribution function。

Or Instagram。So it's a very simple function， you go and you count how many pixels have a value up to R。

 and that's your transform。Very， very simple operation is basically a one line code in almost any programming language。

 and that will achieve as istogram equalization。 So let's see this in action。



![](img/499aeea51b9aff472aa57ad351ba05aa_11.png)

First， let's just take basically an artificial example where we have eight different values here。

 this is count， so we have 790 pixels that have values 0。



![](img/499aeea51b9aff472aa57ad351ba05aa_13.png)

1023 pixels that have value 1 and so on。 And we just transform this into a probability。

 and because we have been working with probabilities。

 and this is the probability that we are going to get。

 We plug that into the formula that I'll just show you。 And this is what we are going to get。

 So first of all。This is the original istogram PR。 This is the distribution that we have。

 If you plug that into the formula， which I show this is going to be the transform。 No。

 it's going to be monotonic。 And we know that because we are integrating。

 And let me just write that again， the basic operation was to integrate from0 to R。

 So the more I integrate because what I have in here is positive。It's clearly an increasing function。

 I'm only adding more and more positive numbers， so it have to be positive。

So it's an increasing function and what it tells me tells me that0 goes to this number。

 one goes to this number and so on， so it becomes a very， very simple map。

 and this is going to be the new Instagram。Now， you may wonder it looks more uniform。

 and one of the things that happens because we are working with discrete data。

 we are working with images in the computer， we are going to have to run numbers。 So， for example。

 the 4。2 will become 4。 So we end up actually with less。

Picks than we have here because these ones at the end will merge into the same integer number。

 And that's a price we play we pay for working with discrete images。 We cannot represent 6。7 and 6。

8 will both become， although the formula tells us they should go to different numbers。

 They will both become， let's say，7。In a similar fashion， let me ask the following question。

 which I'm going to ask you to think for a second and then respond to me。

Let's just look at an Instagram。That has the following form。It has only two different pixel values。

These two。Doesn't matter what exactly are the values here。

 but this is the original distribution of pixel values。 There are only two values in the image。

 This is a binary image with only two different colors， two different pixel values。

 And I'm going to ask you， what's the relationship between the map for a pixel value here。

And a pixel value here。 So let's just call this a。 Let's just call this B。

 And I'm asking you the relationship between T。安提。B。Are they equal， Are there different。

 Is T A greater than T B， Is T A less than T B， So as think for a second and give me your answer。

 and I'm going to come back right away and give you the explanation for the correct answer。

So let's look at what is the correct answer。Remember what we are doing in istogram Qization is we are integrating okay。

 so I ask you once the relationship between these two are equal less or greater we know first of all that TBb should be greater or equal than T because we have a monotonically increasing function。

But let's look a bit more in detail what happened。This actually is going to integrate the whole mass up to here。

 so basically it's going to integrate only this。Here is going to integrate everything up to B。

 but there is no new mass between A and B。 Since there is no new mass。 then what happens is that T。

Would be equal to T。B。And as an extra exercise， you can think about what's going to be actually the transform for this one and what's going to be the transform for this particular one。

 And it's basically related to the average on the image。 Just to that as an exercise on the side。

 But this is very important illustration that basically the transform that we are looking for。

 even before we have to round or quantize because we are working with discrete images。

 even before that， it's not strictly monotononic。 They might be more than one。

Values that end up with the same transform。 You can， of course。

 say we don't really care too much about that because in the original image。

 there were no pixels with。Initial gray value A。 And that's correct。

 But I want to show this both to illustrate that the transform does not have to be monotonically strictly monotonically increasing。

 has to be monotonically increasing， but not strictly。

 and also to illustrate once again that all what istualization is doing is basically counting the number of pixels up to the value that you want to map。

 So I'm counting the value， the number of pixels up to a。 And then the number of pixels up to B。

So after this exercise let's just see a few additional examples。

 we of course saw examples with the online demo， but let's illustrate one more example which I think is very useful and going back to the images that we started。

 this was dark， This is what's happening after istoamization and the Instagram looks much nicer than before。

 so let's just look at the map， This is the map。

![](img/499aeea51b9aff472aa57ad351ba05aa_15.png)

Pixs value from here。 get map to here。 Okay， so this is my R， and this is my S。And look at the map。

 the map basically is very， it has a very， very high slope because it's trying to very fast map very dark pixels to brighter pixels。

 so it has a very， very sharp slope。Let's look， for example， at this one。

This one was pretty good to start from。It hasn't changed a lot。 And actually， this is the map。

It's almost a unit slope， a map in the diagonal， there's almost no changes in the pixel values。

And similar interpretations for the other two maps。

 This one actually needed needs to darken the pixels。 And we see that in the corresponding map。

 that basically， look what happens here。 And this one needed to stretch the pixels。 Remember。

 they were in the middle。 It needs to stretch them。

 And we actually observe that here is basically stretching the pixels from the middle。

 They were all around here to start from。 and it's going to stretch them。

 And we see that it's actually occupies the whole range from。This， which was the very big。

 very narrow band that it occupies the original instogram with very low contrast。

 It's actually mapped now to the whole spectrum from0 to 255 and we see that in the map as well and of course we end up with images that are very similar regardless of where we started because these images actually were created from these images from an original。

 let's say this one just by changing the contrast and then after we equalize them。

 they look much closer， and that's a technical issues very often to make images that werere taking under different conditions look much more similar。

 we equalize the in and the same time we are making the images look much more similar and then we can compare between them in a much more friendly fashion。

So this is basically ist equalization。 What we are going to do next in the next video is Instagram transform。

 What happened if I don't want to equalize an Instagram。

 I want to transform it to an Instagramsogram that I know is going be very good for my image。

 We're going to see that in the next very short video。 There is also a very， very simple operation。

 Thank you。😊。

![](img/499aeea51b9aff472aa57ad351ba05aa_17.png)