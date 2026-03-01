# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P27：27_03_12_12-演示：反锐化掩模-时长-03-10.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。 We' are going to be using once again Madlaav to illustrate what we just learned about Anho masking and a few additional operations。

 so let's go into that。First， we're going to read an image one of the images that come with the matla package。

 Then we are going to add salt and pepper noise。 We see here 0。09。

 meaning that about 9% of the pixels in the image are going to be contaminated by salt。

 white or pepper， meaning black noise。After that， we are going to apply to the noisy image。

 medium filtering。 And we see that operation here。 and then we' are going to load the original image。

Then I see image。The medium filter result， meaning the dennos image。

 the difference between these two as one possibility of An masking and also a stretch Instagram。

 And we're going to see and discuss each one of these more。

 So let's just first load all the five images and see what happens。

 I'm going to move them around so we can look at all of them at once。



![](img/1ee08ce69453cc40f8388000a8de8b49_1.png)

![](img/1ee08ce69453cc40f8388000a8de8b49_2.png)

So。

![](img/1ee08ce69453cc40f8388000a8de8b49_4.png)

This is once again， we see here first the original image。

Then we see the salt and pepper noise when the background is white， we can see the black dots。

 basically the pepper， when the background is dark， when the background is dark。

 we can see the white dots， the salt。Here we see the result of applying a 3 by3 medium filter to this image。

 and we see that we managed to clean the noise and we managed to clean pretty much the whole image。

 Of course， we have some blaring， not a lot， but some blurlaring produced by the medium filter。

 So it's not exactly the original image is kind of a b version of it。

Which means that if we take now the difference between these two images， we're going to get this。

 which is mostly the edges， the basically sharp boundaries。In this image。

This image is a bit too dark and therefore what we do is as we know， we can stretch the Instagram。

 and in this case， we just square the pixel values。

 and by that we are stretching the Instagram and we see here the results。

 So here is basically the difference between the original the medium filter of the noisy image That's that and we have stretched it。

Now， observe that we don't see edges because of the noise。

 Those would be spurious edges won't be real edges in the original image。

 And that basically happens because we have apply a medium filter before producing this difference。

 And that's actually great because the medium filter managed to get rid of the noise and therefore managed to get rid of the possibility of having spurious edges。

 So in this example， we see a lot of the things that we have learned。 We see salt and pepper noise。

Result of medium filter， the difference producing the most important edges and an Instagram stretching to be able to observe those edges in a much nicer way。

 Thank you very much and see you in the next video。

