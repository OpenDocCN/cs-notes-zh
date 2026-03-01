# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P39：39_05_01_1-图像分割导论-时长-04-17.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome to week 5 of our image and video processing class。

 This is a very fun and exciting week for a number of reasons。 First of all。

 image and video segmentation is a fun topic， as were gonna see in the videos during this week。

 Second， because during this week， we're gonna to be transitioning from the fundamental material to the more advanced material。

 The fundamental material is as we talk， that material that is used every day。

 and you cannot take a class in image processing without knowing it。

 The more advanced material is material that has been developed in the recent years and is' also extremely useful。

😊，And as were going see， it actually often forms parts of very important products today in industry for image and video post processing。

 So let's just get into image segmentation。 As I say， it's going to be a lot of fun。

 But what is image segmentation。 We should basically， first of all， try to answer that question。

 and were going answer that question with a few examples in image segmentation。

 the basic idea is that we want to separate objects。

 we want to call different objects by different names depending on some properties of those objects。

 So for example， here we have a cat and we want to make sure that we find the boundary of this cat and we can separate the cat here from its background。

 So here we have the cat and here we have the background。

 So we manage to separate objects in the image。

![](img/9f713f47da2316f577ff8367f34383ea_1.png)

![](img/9f713f47da2316f577ff8367f34383ea_2.png)

Sometimes the user is going help us to do that。 For example， the user can mark。

 this is my foreground。 This is what I care。 the objects I care。 This is the background。

 the objects I don't care just two very simple marks。

 And from that we basically need to develop a technique that will basically extract the horses from the background。

 and sometimes this type of segmentation is called foreground background separation。 once we do that。

 we can， for example， change the background something that is done very very often in the movie industry changing background of different scenes as we're gonna to see in a second。

 So this is kind of foreground background separation。



![](img/9f713f47da2316f577ff8367f34383ea_4.png)

![](img/9f713f47da2316f577ff8367f34383ea_5.png)

Sometimes what we actually need is to label everything that happens in the image。

 So to find regions in this image， which is an image of neurons taken with a technique called electromicscopy that we are going to discuss later in this in the last week of this class。

We have， as I say， images of neurons from electromicscopy and ideas that we want to label every pixel。

According to the class that that pixel belongs to， so basically we are coloring the image we're saying all these region should have the same label。

 it belongs to the same class， the same type of object the same type of tissue so we are not subtracting for for from background we're basically labeling every single region of the image。

 and we get all these segments and then we can do analysis。 Finally。

 we also have the same problems in video and we see that here and this is a video that we already saw at the very beginning of the class。



![](img/9f713f47da2316f577ff8367f34383ea_7.png)

Let's just basically， run it。We have the video。And we have。A similar video。

 but with a different background for doing that， we had to extract。The main object here。

From the video。 So we are able to produce a different background for that。 And basically。

 this is what's behind a very important component of one of Adobe's products called After effects。

 And we're going learn that。 We're going learn exactly what's the underlying technology for basically the video segmentation in after effects。

 So these are just some examples。 Now， what we have to do is learn how we solve all these very interesting image and video segmentation problems。

 And we're going to do that exactly starting in the next video。 See you then Thank you。😊。

