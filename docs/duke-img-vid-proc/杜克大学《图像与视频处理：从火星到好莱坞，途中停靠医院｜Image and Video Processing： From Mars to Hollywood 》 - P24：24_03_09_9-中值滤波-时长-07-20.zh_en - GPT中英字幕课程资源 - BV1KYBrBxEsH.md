# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P24：24_03_09_9-中值滤波-时长-07-20.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Coming back to local filters， there is another extremely important and extremely popular local filter。

 which is called the medium filter， which we are going to describe next。

 and is's a gray filter because it doesn't really blur edges。

 And although it's a very classical filter is still very useful today。 So let's observe it。

Before we actually describe it， let's see what it happens with a real image。

 We have here an image that has been contaminated with what's called salt and pepper noise。

 Next week， we are actually going to describe different models of noise a bit better。

 but salt and pepper is noise that basically is very strong noise individually added at different pixels。

We see it here。 This is the result of the local mean filter。

 what we have seen in the previous videos， just local averaging。 in this case， a 3 by 3。

 you might be able to observe there is some reduction of noise。

 but not really too much reduction of noise。Here， on the other hand。

 is the result of a 3 by 3 medium filter。 And we see a great result。 We don't see blaring。😊。

And we actually see that a lot of the noise has been reduced。

 We could reduce much more noise with a local mean filter， a local average。 If we go beyond 3 by 3。

 we might go 5 by 5，9 by9。 Remember， by averaging， we are reducing the noise by square of the number of pixels that we are averaging。

 as we saw in the previous videos。 But if we enlarge the neighborhood。

 we also saw that we are going to start to blur a lot of the details。 On the other hand。

 keeping a three by three neighborhood， we still get extremely good denoing with the medium filter。

 So what's the medium filter。 Very simple。What we do is we actually take。

 let's say if we are working in a three by three neighborhood。



![](img/65c77a865396135258f3904c69a9c5d5_1.png)

We basically order the pixels， so we。

![](img/65c77a865396135258f3904c69a9c5d5_3.png)

Basically， order them from the smallest to the largest， and we pick the one in the middle。



![](img/65c77a865396135258f3904c69a9c5d5_5.png)

![](img/65c77a865396135258f3904c69a9c5d5_6.png)

Okay， so we start putting all the pixels in order。 We pick the one in the middle。

 This is an operation we actually learned in elementary school。 and it's an extremely powerful。

 replace it by the one in the middle。 So， for example， if you have。😊。



![](img/65c77a865396135258f3904c69a9c5d5_8.png)

![](img/65c77a865396135258f3904c69a9c5d5_9.png)

![](img/65c77a865396135258f3904c69a9c5d5_10.png)

Pixs， which looked like this。 And one of the pixels， is very noisy。



![](img/65c77a865396135258f3904c69a9c5d5_12.png)

When you order them。

![](img/65c77a865396135258f3904c69a9c5d5_14.png)

This one is going to be replaced by one of these values。 They equal， So it's going to be replaced。

 It's going to go down。 Okay， so the noise is clean， completely clean without blaring。

 as we have seen for Gaussian filtering or for mean filtering。 It's a very。

 very simple filter you order and you pick the one in the middle。

 you order from the smallest to the largest。 you pick the one in the middle。

 And then you move to the next window。 So you basically take a three by three window。

 then you move to the next window， the next window， the next window。

 and you get this extremely simple filter， the medium filter。

 Before I show you additional examples of the medium filter in real time。

 we are gonna actually run matlab to do that， let me just give you one very interesting property of the medium filter。



![](img/65c77a865396135258f3904c69a9c5d5_16.png)

![](img/65c77a865396135258f3904c69a9c5d5_17.png)

![](img/65c77a865396135258f3904c69a9c5d5_18.png)

![](img/65c77a865396135258f3904c69a9c5d5_19.png)

![](img/65c77a865396135258f3904c69a9c5d5_20.png)

![](img/65c77a865396135258f3904c69a9c5d5_21.png)

![](img/65c77a865396135258f3904c69a9c5d5_22.png)

![](img/65c77a865396135258f3904c69a9c5d5_23.png)

![](img/65c77a865396135258f3904c69a9c5d5_24.png)

![](img/65c77a865396135258f3904c69a9c5d5_25.png)

We saw in a couple of videos ago that the average filter is reducing this 8 minus AI。



![](img/65c77a865396135258f3904c69a9c5d5_27.png)

![](img/65c77a865396135258f3904c69a9c5d5_28.png)

Square， we say the average is the value of a that reduces that minimizes this。

 and I'm summing over all the pixels。 So I'm going to ask you a question。

 can we represent the medium filtering。

![](img/65c77a865396135258f3904c69a9c5d5_30.png)

![](img/65c77a865396135258f3904c69a9c5d5_31.png)

![](img/65c77a865396135258f3904c69a9c5d5_32.png)

In a form like this， a different function， maybe sum of certain function。



![](img/65c77a865396135258f3904c69a9c5d5_34.png)

![](img/65c77a865396135258f3904c69a9c5d5_35.png)

Of a minus AI。Can we do that， Just think for a while and tell me， yes or no。

 if you know the answer of that。

![](img/65c77a865396135258f3904c69a9c5d5_37.png)

![](img/65c77a865396135258f3904c69a9c5d5_38.png)

So what's the answer to this question， Very interesting this。



![](img/65c77a865396135258f3904c69a9c5d5_40.png)

Is the mean。

![](img/65c77a865396135258f3904c69a9c5d5_42.png)

The value of a that minimizes。The square error is the mean。 What's the median。



![](img/65c77a865396135258f3904c69a9c5d5_44.png)

你咩点。

![](img/65c77a865396135258f3904c69a9c5d5_46.png)

Is the value。

![](img/65c77a865396135258f3904c69a9c5d5_48.png)

That minimizes the absolute。 There is no square here。 It's just the absolute difference。

 It's extremely interesting that by replacing this square by basically nothing。 just absolute value。

 we get the medium once again， you can prove this it's a bit more a difficult proof。

 because when we discuss how to prove this。 we say。

 just take derivatives make the derivative equal to0。

 and you're going to find that a is the average of all the AIs here。

 you're not allowed to take derivative because at0。

 the absolute value cannot have doesn't have a derivative。 So the proof is a bit more delicate。

 but I'm sure that you can do it as a bonus exercise。 Don't worry too much about that for now。

 you can believe me that if you don't want to do the proof by yourself that the result of minimizing this is the medium field。



![](img/65c77a865396135258f3904c69a9c5d5_50.png)

![](img/65c77a865396135258f3904c69a9c5d5_51.png)

![](img/65c77a865396135258f3904c69a9c5d5_52.png)

![](img/65c77a865396135258f3904c69a9c5d5_53.png)

![](img/65c77a865396135258f3904c69a9c5d5_54.png)

![](img/65c77a865396135258f3904c69a9c5d5_55.png)

![](img/65c77a865396135258f3904c69a9c5d5_56.png)

![](img/65c77a865396135258f3904c69a9c5d5_57.png)

![](img/65c77a865396135258f3904c69a9c5d5_58.png)

![](img/65c77a865396135258f3904c69a9c5d5_59.png)

![](img/65c77a865396135258f3904c69a9c5d5_60.png)

![](img/65c77a865396135258f3904c69a9c5d5_61.png)

An extremely interesting operation for those that are familiar with the area of robot statistics。



![](img/65c77a865396135258f3904c69a9c5d5_63.png)

This is a square error which is not very robust。 And that's why it's blurlarring。



![](img/65c77a865396135258f3904c69a9c5d5_65.png)

This is a much more robust error。 And that's why it's able to completely eliminate noise like salt and pepper noise without blaring the rest of the image。

 The last interest in property， I want to mention about the median is in the average。

 The result doesn't have to be one of the pixels。 So， for example， if you' are averaging  one and 2。

 you get 1。5 is not one is not2。

![](img/65c77a865396135258f3904c69a9c5d5_67.png)

![](img/65c77a865396135258f3904c69a9c5d5_68.png)

![](img/65c77a865396135258f3904c69a9c5d5_69.png)

![](img/65c77a865396135258f3904c69a9c5d5_70.png)

![](img/65c77a865396135258f3904c69a9c5d5_71.png)

![](img/65c77a865396135258f3904c69a9c5d5_72.png)

Okay， when you're averaging， let's say a by when you're computing the average of a three by3 and you're replacing the middle pixel by the average。

 you might be replacing the pixel by a value that doesn't show up not in the three by three window maybe not even in the whole image once again。

 the average bit of one and2 is 1。5。 a new value On the other hand。

 when you're doing the medium filtering， youre always replacing by one of the values that already exists in the three by three window。

 so you're not producing new pixel values and that's part of what's happening here and that's a very interesting property by itself。

 there is no novelty， there is no new values， only those that are already familiar in the neighborhood of the pixel that you' are replacing the pixel with the medium Now now that we know about the medium now that we know some of the interesting。



![](img/65c77a865396135258f3904c69a9c5d5_74.png)

![](img/65c77a865396135258f3904c69a9c5d5_75.png)

![](img/65c77a865396135258f3904c69a9c5d5_76.png)

![](img/65c77a865396135258f3904c69a9c5d5_77.png)

![](img/65c77a865396135258f3904c69a9c5d5_78.png)

![](img/65c77a865396135258f3904c69a9c5d5_79.png)

![](img/65c77a865396135258f3904c69a9c5d5_80.png)

![](img/65c77a865396135258f3904c69a9c5d5_81.png)

![](img/65c77a865396135258f3904c69a9c5d5_82.png)

![](img/65c77a865396135258f3904c69a9c5d5_83.png)

![](img/65c77a865396135258f3904c69a9c5d5_84.png)

![](img/65c77a865396135258f3904c69a9c5d5_85.png)

Properties of the medium。 Lets just see a few additional examples of the medium filter in action。



![](img/65c77a865396135258f3904c69a9c5d5_87.png)

Let's see that in the next video。 Thank you。

![](img/65c77a865396135258f3904c69a9c5d5_89.png)