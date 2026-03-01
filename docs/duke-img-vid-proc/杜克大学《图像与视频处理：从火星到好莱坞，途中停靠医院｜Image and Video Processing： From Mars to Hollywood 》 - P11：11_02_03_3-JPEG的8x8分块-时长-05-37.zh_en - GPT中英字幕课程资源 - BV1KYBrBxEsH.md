# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P11：11_02_03_3-JPEG的8x8分块-时长-05-37.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Now that we have finished the back end of image compression。

 the symbol coding that we do with Halfman coding in the example I presented。

 let's go to the front end of image compression， Basically what we are going to describe in this video is this part。

 so let's just start with this component。

![](img/edb4b8fcf2d0beeb55dfbe02ba13a0d1_1.png)

![](img/edb4b8fcf2d0beeb55dfbe02ba13a0d1_2.png)

What we have is an image。And the first thing that a JPG dash or a loss transfer compression dash is device the image。



![](img/edb4b8fcf2d0beeb55dfbe02ba13a0d1_4.png)

Into blocks。Each one of these blocks has an。By n pixels， and we' are going to talk。

 we are going to give examples of what's the value of n， but just to give you an idea。

 JPg uses 8 by8。So basically JEC codes almost independently every 8 by8 block of the image。

 These are none of a lapping blocks。 So here are 8， then 8， then 8， then 8 okay。

And we go all the way。 And there are techniques what to do if your image width is not a multiple of8 and so on。

 So don't worry about that。 For the moment， those are just technical details。

 So we take an end by N block。 and we're gonna encode each one of those N by8，8 by8 blocks。

 And as I say， they're encoded almost independently。Now， this is what you do with one image。

 But this is if you only have a black and white image。 What happen if I have an R GB image。

 So JP is what's colorblind。 JP doesn't know how to deal with color。 The standard itself。

 but there are some assumptions that are made。 Originally。

 what you could do is you just take the red。 Remember。

 every channel is a two dimensional array of pixels。 So the red looks like this。

 You divide a red in 8 by8 blocks and youll encode the red。 you do the same with the green。

 You do the same with the blue。 And that's perfectly legitimate。 Now， normally， there is。Basically。

 a lot of correlation between the channels。 So what basically JPEC does is self coding RGB。

It goes into what's called why。C， B。C R， I'm going to tell you in a second how to do that。

 But these are instead of three channels， RGB， it has three channels which are Y， C， B and C， R。

 This is aluminance。Channel， which is basically what you will see if you have a black and white TV or a black and white monitor。

 you will get a color image， but you will only see basically the black and white component。

 the luminance component of it。 And these are the colors。



![](img/edb4b8fcf2d0beeb55dfbe02ba13a0d1_6.png)

Okay， and this is a very simple transform。 This is actually done by a three by3。Mas。

So you basically are going to have your why。CB。C， R as a column。



![](img/edb4b8fcf2d0beeb55dfbe02ba13a0d1_8.png)

You have a three by three matrix here，3 by3。And you。Have your RG B。Values。

 so the y is a linear combination of the RGB。 The CPR is a linear combination。The C B。

 a linear combination and the C R another。 And this matrix is invertible。

 So once you decode the Y CCR， you multiply by the inverse of this matrix and you get back the RGB。

 So the very first thing that JPg does， it takes your color image。Multipies it by a matrix。

 So basically， every pixel， let's say 100，150，200。You multiply by the coefficients here。

 this is a constant matrix that is given is very well known。

 it appears all over if you just Google YCBCR， you're going to get the values of this matrix。

So it goes over every single pixel of the image and transforms it from red， green。

 blue arrays into Y C R arrays。 Once again， two dimensional arrays where every pixel Na of being an RGB is a Y CCR。

 So it has those and then going called each one of these arrays independently。

 So let's look at why it will go into Y。And it will divide it in8 by8 blocks。Okay。

 and that's all what's going to do。 And then it's going to take each one of these eight by8 blocks and iss going to encode them。

 as I say almost independently， but for the sake of this presentation。

 we are going to consider them independently。 So it's going to encode a lot of8 by8 small images。

And how is going to do that is going to do that with a discrete cosine transform， a transform。

 then a quantization， and then a symbol encoding， as we have seen so many times with the diagram of JPEC。

So now we have an 8 by8 block and all what we need to think about now is that we have a small8 by8 image。

