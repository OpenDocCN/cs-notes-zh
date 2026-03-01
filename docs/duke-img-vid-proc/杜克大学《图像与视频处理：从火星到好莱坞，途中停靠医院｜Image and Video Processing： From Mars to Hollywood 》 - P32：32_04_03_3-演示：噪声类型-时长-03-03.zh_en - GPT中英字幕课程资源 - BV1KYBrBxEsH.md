# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P32：32_04_03_3-演示：噪声类型-时长-03-03.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。 We're going to benefit once again from Madla to learn a few of the examples of different types of noise that we have learned in the previous video。

😊。

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_1.png)

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_2.png)

Let us， first of all， as we already know how to do that， load an image。

 This is one other image that comes with a Madla package。 This in particular is our color image RGB。

 So we are going to first transform it into a black and white image。

 We are basically only going to be paying attention to the luminance component of the image。

 That's this operation that we see here。 Then we are going to add Gaussian noise。

 That's what we see here。 So Gaussian means we are going to add Gaussian noise to this image。

 And that Gaussian noise is going to have a variance of two。



![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_4.png)

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_5.png)

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_6.png)

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_7.png)

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_8.png)

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_9.png)

Then were going to add salt and pepper noise with 2%。

 meaning 2% of the pixels in the image eye are going to be changed to either black or white。

 according to the definition of salt and pepper noise。

 and then we are actually going to add 20% of salt and pepper noise。 So that's this image。

 And now what we are going to do is we are going to load all the images， the original color image。

 the black and white version of that image， the gaussian noise。

 the 2% salt and pepper noise and the 20% salt and pepper noise。 So let's just see what happens。



![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_11.png)

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_12.png)

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_13.png)

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_14.png)

![](img/9e1ecfd1b56a0beb3cd4c88233b1fc0c_15.png)

Once again， we are basically loading all the images。

And I'm going to move them so we can look at them better。

 but I think you managed to see some of that already。So there is a lot of images here。

And let's see first the original image， this is the RGB， the color image that we load first。

 I'm going to remove that so we don't have so many images on the screen。Here is the original image。

Here is the result of adding the Gaussian noise。 The first observation you can see is that basically there is noise all around the image。

 So this is Gaussian noise。 Every pixel has some noise， according to the Gaussian distribution。

Contrary to that， we see here the 2 per cent salt and pepper noise。

 Some of the pixels of the image have been affected。 only 2 per cent of them。 Now。

 once they' are affected， they become either completely white or completely black。

 as we see that here， finally。We see what happens when we have 20% of noise。

 So you see a lot of pixels that basically became either black or white。 once again。

 compared to only 2% and compare to the Gaussian noise that is affecting all the pixels。 And finally。

 let's just look again at this nice original image。 So these are different types of noise。

 Gaussian noise and salt and pepper noise and basically different densities of noise for salt and pepper。

 We could also have play with different variances for the Gaussian noise。

 But I think that this is sufficient to illustrate the concept of these types of noise。

 Thank you very much and see in the next video。