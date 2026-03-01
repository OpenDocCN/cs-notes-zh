# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P43：43_05_05_5-大津分割法与演示-时长-14-25.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back， We has spent a couple of videos talking about edges and how important it is to compute edges in order to obtain image segmentation In this video。

 were going to present Otu's method。Ou basically looks at the histogram of the image。

 It looks at the pixel values and looks at the property that in order to obtain segments。

 we need kind of uniform pixel values。 So it's not looking at edges It's looking at the regions inside the segments that we want to segment out the objects that we want to segment out。

 Let's look at the basic underlying idea behind alsou what motivates this algorithm。

 and then we're going to explain how it works。If we look at this image of a fingerprint。

 we plot the histogram and the histogram is what's called bymod。 A lot of pixels values are here。

 which is basically a lot of the fingerprint and a lot of pixel values are here。

 which is basically the background， very clear two modes in the histogram。

 So this is a multimod histogram， and the basic idea is that if we threshold here。

 we can obtain a very simple segmentation， which is separate the fingerprint marks from the background by a simple threshold because we have this bymod distribution。

 also is going to help us to find basically the threshold in an automatic fashion。 Now， of course。

 not all the time， images are as nicely distributed as this one。



![](img/022b5644748f06f00a912210a790b3c4_1.png)

Let us look at this very simple example here we have a binary image。

 so we have still bimod distribution， but two delta functions。If we add a little bit of noise。

 then we're going to still get。 So this is Gaussian noise。

 We are still going to get two modalities and also is going to be able to， without any problem。

 Os method is going to be able to segment this out with no problem。 It's going to find the threshold。

 Now， if we add much more noise。 The variance is about five times going from here to here。 Now。

 the histogram is much more distributed。 We don't have this multimodality。 And。



![](img/022b5644748f06f00a912210a790b3c4_3.png)

Ou is not gonna Os method。 Its gonna not going to be able to find a nice threshold。

 I haven't explained to you the method yet， but if we apply the method to this image because of this distribution。

 This is what we are going get。 We are not going to be able to segment it out。 But， of course。

 at this time， fifth week in image processing， we're not really scared of noise。

 We see a noise image， we can denno it。 if we denno。 we might be able to get back in this case。

 we get back to this bymod distribution。 And in O automatic threshold algorithm is's going to be able to segment it back。

 So it's a very powerful technique， as we're gonna see， this is a simple image to illustrate idea。

 So what is the method trying to do。 The method is trying to find a threshold。

 such that the in class variability is very small。 So we want to find a threshold here。

 Such that the variance。On each one of the classes is as small as possible。

 So the class is as compact as possible。 and the method starts from the Instagram。

 There is no special relationship here。 So we lost the special relationship。

 So regions that have similar pixel values that are in completely different positions in the image。

 we kind of be merge in the Instagram and then Ous algorithm is going to treat them as the same。

 So we're going to see later on other algorithms that take into account the special relationship between the pixels。

 but this doesn't。😊，The basic idea is very simple。 We need to minimize the weighted within class variances。

 We assume two classes， and we need to minimize the weighted within class variances。

 So what's that class variance。 is defined here。 T is going to be the threshold。

 That's the threshold we are looking for。 It's going to be if we have a regular image。

 it's going to be some value between 0 and 2，55。And this is the value were trying to minimize for。

 and let me define each one of these variables here， although they're pretty clear。

So this is basically the probability of each one of the classes。 P is what we get from the Instagram。

 We start from the Instagram。 We have a probability for every pixel value。

 So we compute the Instagram and we normalize it。 So it's a probability as we have taught a few weeks before。

 and then we have we go from one to T。 that's where we put the threshold or from T plus1 to the end of the the largest pixel value 255 and then we get the probability for class 1 the probability for class2。

 then we simply get the min for class 1 and for class 2。

 and then we also get the variance for class 1 and the variance for class 2。

 and in such a way we obtain the weighted within class variance which is here。

 and that's where we want to minimize once again this measurement basically。

That's the compactness of the classes， if we put the threshold in the wrong place。

 there's going to be large variance for one of the classes， and we don't want that。

 So that's what we need to optimize。 That's what O's algorithm does now。

How to implement this One way is extremely trivial。 You just try it。 You go for t equal 0。

 You compute this， not hard， and then you compute this value。

 You do the same for one to everything up to 255。 You remember which one was the the lowest。

 you keep that threshold and you're done。 that by itself will already be very fast， very efficient。

 very fast。 If you do some algebra， you can actually find out very simple algebra。

 just plug in the formulas from the previous slide here。 and you can find out that。This。

 which is the total variance of the image， is basically the sum of the within class and the between class variance。

 Now， this is， of course， constant。 It doesn't depend on the threshold。 The image is just one image。

 and the variance of that image is constant。 So we want to minimize this。 This is constant。

 This is equivalent to maximizing this。Now， the probabilities and the means basically are very。

 very easy to update as we move the threshold in a very simple recursive formula。

 which is you know add one more， add one more when we are moving the threshold。

 So basically these can be computed very efficiently in a recursive fashion as we go from， let's say。

 t equal 10 to 11 1213， we basically keep adding here， and then very fast， we compute。

 we once again run from 0 to 255 on the Ts， the difference is that computing these cannot be done explicitly in a recursive fashion but this can be done explicitly in a recursive fashion where the t plus one depends on the T in a very simple formula。

 it is you means and probabilities。😊，Very simple。 you keep you keep adding and you get to the result。

 So very simple， either if you use the direct computation or if you use the recursive computation。

 you run through all the possible values of T， you pick the one that either minimizes these or maximizes these and you're done。



![](img/022b5644748f06f00a912210a790b3c4_5.png)

So。Before I show you some examples inside Matlav， I want to tell you something。

If you have a non uniform background， like in this image， then also is not going to help。

 Alsos is not going to help because you might have a binary distribution。Like withdraw here。

 But then because of the bias of the background， this will not be a basic binary bymod type of distribution。

 So I just explain you how to do Ous algorithm in the whole image。

 You can also do it in blocks of the image。To try to get rid of the problem with basically a non uniform background。

 And then you're going to get a different threshold for every single one of the region。

 Or if you want， you can actually do what's called a moving window。 You can just do it here。Sorry。

 let me just get the pen。 You do it here， Then you do it in another window like this。

 And then you basically。Do it。In another window like this， and then you can， for example。

 if you want， you can average the thresholds that you get in the overlapping windows or you can create a function of the thresholds。

 So once again， as in many of the other algorithms that I have explain。

 there's the underlying concept which is to separate the images to minimize that within variances that we just explain now。

 that concept you can implement in many different fashions in the whole image in blocks。

 overlapping blocks， non overlapping blocks， you know。

 there's a lot of art and basically depending on the application， what to apply。 once you do it。

 for example， as here， if you do it globally， let me just erase thenotation。

 So it's easier if you do also in the whole image， this is what you're going to get。

This is very dark。So I got confused with the letters in the distribution and in the optimization。

 And then it basically the threshold put it together with the letters and the writing has been。

 It's basically gone。 Now， if you do it with a moving window， you get this beautiful result back。

 once again， extremely extremely simple。 All what we are doing is to segment out the letters here。

 We are computing thresholds。 We move a window， which is smooth regions。😊，Remove it。

And we are computing thresholds with the formulas that I just explained to you。 Now。

 let's see an application of these running inside module。



![](img/022b5644748f06f00a912210a790b3c4_7.png)

In order to illustrate Otu's method inside Madlaav。

 the first thing we have to do always is to load the image。 So here we have we are loading the image。

 This is this operation。The next operation is what actually does the computation of the optimal threshold。

 the Ous algorithm that we has described， that' this operation in Madla。

 that it gives us the level gives us the value of the optimal threshold。

 And then we are basically going to threshold the image following that value。

 So let's see the results of all these operations。😊。



![](img/022b5644748f06f00a912210a790b3c4_9.png)

We have link here， and let me just move the window so we can observe them better。



![](img/022b5644748f06f00a912210a790b3c4_11.png)

This is the image。This is the Instagram。 Now， you're expert in Au's method。

 So the moment you see this Instagram， you say， wow， that's great。 I can do a pretty decent job。

 if I just compute that optimal threshold that should be around here。

 And that's a result of threshold in the image with that optimal threshold。 It looks pretty nice。

 Remember， no special information。 So， for example。

 you might be able to see a few pixels here that were included as part of the background。 Of course。

 with any type of smoothing， you will get rid and will get a very。

 very nice white object inside here。 here， things are a bit different。 And that's because as you see。

 this part of the coin is relatively dark。 almost as dark as the background。

 or basically as dark as the background。 And that's why it was included as part of the background。

 situation might have been different if we do。😊，Ous method in a local window or some other variant of Ous method。

 but the idea is very clear for most of the image which which with a simple threshold we get a very nice segmentation and that threshold we don't need to specify by hand Ous method automatically computes for us so let's go back to the slides and we finish this video Thank you。



![](img/022b5644748f06f00a912210a790b3c4_13.png)

In this video， we have seen another classical standard。

 very simple and very powerful image segmentation algorithm。 Unfortunately， not all the images are。😊。

Easy enough for auto to segment or for the half transform to segment。

 And we're going to need more advanced techniques to be able to handle them。

 And that's going to be the topic of the future videos in this week。

 I'm looking forward to seeing you in them。 I'm having a lot of fun。

 and I hope that you are having to。 Thank you。😊。