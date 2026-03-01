# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P2：02_01_02_1-什么是图像与视频处理-第一部分.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。 As I just mentioned in the previous video。

 we're going to now see a few examples of image and video processing。

 That's going to help us to understand basically what is image and video processing。

 and it's also going to provide a few examples of the material that we are going to learn during these nine weeks。

 So let's dive right in。 And we are going to start with an example on scientific images。

 Sc images are images that are taken with the scientific goal。

 we want to do some science with those images。 And there is probably no better example that images from Mars。

 So we are all very excited when we get images from the NASA JPL expedition to Mars。

 These are really cool images and we are seeing something that we have never seen before。 Now。

 these images take a lot of space in the computer in the Mars rovers。

 They actually take a long time to transmit to Earth because they are very， very large。

 So NASA and JPL。😊，Had to implement something inside the Mars rovers。

 something which is called image compression to preserve the information。

 but try to make that occupy less space。 So it's faster to transmit。 We're going to learn。

 we're actually going to learn the algorithm that is implemented inside the Mars rovers。

 I was lucky enough that one of my algorithms was selected to be implemented in the Mars rover。

 So we're going to learn it pretty much in detail。But of course。

 this is not the only example you know about image compression if you use a digital camera。

 most digital cameras today use image compression if you're looking images over the web。

 you're basically using。Image compression， actually， when you're watching this video。

 this video is being compressed before it's uploaded to the web so you can enjoy it。

 So we're basically doing image and video compression all the time。

 So that's one example that in your daily life， you're already seeing image and video compression。

 There's another very important example and comes in the movies。 If you go to the movies。😊。

Youre probably have seen。 you might not be aware， but you have seen image and video compression。

 Let me give you an example。 So here we have an image。 This is basically one frame of a video。

 It's a very famous video。 And what we very famous movie。 And while we see here。

 these are two consecutive frame。 So one coming right after the other。

 And we see here that the actor is basically holding a glass。😊。



![](img/f51a23881bdb1139b3e53a63a29e8a14_1.png)

And right after is holding a plate。 That's very surprising how he switched a glass to a plane。

 That's actually to a plate。 That's actually a mistake in the movie。

 Here is another example that we basically see the camera。

 the camera man is in the picture Of course， the director didn't want the cameraman in the picture。

 but it is。 And actually， if you saw the movies when they just come out and you pay attention to them。

 you actually might have been able to see the cameraman or to see these mistake。

 there's actually mistakes in almost all the movies and there's a website that shows them。

 And basically after that， you go and see basically the DVD or different verses of the movie。

 These repairs。 these mistakes were repaired。 and how the repair with something which is called image and video in painting。

 and we're going to learn about that。 But let's see a few additional examples because。😊。



![](img/f51a23881bdb1139b3e53a63a29e8a14_3.png)

Sometimes we need to repair images and videos， not just for the movies。So for example。

 here is a picture that looks perfectly fine to us。 It's actually a picture of styling。

 And so here we have styling。😊，We see nothing wrong with this picture。

 The only problem with this picture， this is not an original picture。

 This is a picture that was im painted by hand， because actually。



![](img/f51a23881bdb1139b3e53a63a29e8a14_5.png)

What really happened was this。 This is the real picture。 There was another person here。😊。

That the picture was retouched。 In this time， it was done long time ago。 It was done by hand。

 It was retouched so that the person is no longer in the picture。 But actually， today。

 we're going to learn how to do that with basically computer techniques。

 Let's the other examples because this is very exciting。 And also。

 there is a website which we provide those details in in the class webage that provides a lot of examples like this。

 This is really a fine area。 So here is a friend of a multipyython movie。 And as you see。

 the scratches are being made disappear。 So sometimes you have a very nice image that somebody is scratching it。

 and you want to make those scratches disappear。 What you are seeing now is a simulation of a real image processing algorithm that is making that scratch slowly disappear。

 And that's going to be part of what we are going to learn。

 We talk about image compression that's going to be about the。😊，Second week of this class。

Imaging painting and video painting is coming towards the second half of the class。

 Let's see more examples。Here we see a perfectly nice video。😊。

This is one of my former students Kar walking in front of the library at the University of Minnesota。

Doesn't look to us anything strange in this video。

![](img/f51a23881bdb1139b3e53a63a29e8a14_7.png)

Only that this was the actual video。Actually， Kear's wife was walking in front of him， but we apply。

Image and video processing algorithms to make her disappear from the video。

 Sometimes we want to get special effects in videos。 So this is an example of special effects。

 We actually start from a black and white movie， And we see here a few frames of that black and white movie。

 We provide a few hints of some color that we want to add to the video。

 and here is the automatic result， just from hints， actually， in this case， in just one frame。

 We get a colorized movie。 So it's like we're in painting。

 but we're im painting colors into the movie。 Just another special effect。 special effects all over。

 And you need a lot of image and video processing to do them。 So here is another example。

 Let me run it first。 So it's easier for me to explain the special effect。 At first， you see。

 kind of blurry。 This looks like a blurry video。 But look what's gonna happen。😊。

We actually have the players。Actually， are sharp。The movie was blurry。 The background was blurry。

 but not the players。 So let me just try to run it again so we can see that even better。

So it's blurry but the players are not and we have to do video processing to be able to get that special effect Here is yet another example of special effect I'm going to run it and you're going to see basically immediately what type of special effects we mean here。

We see that the movie is running， but basically the girl delayed in the movie is actually being repeated。

 Okay， and so it's very easy to observe that here we see repetitions of what's happening。

 And that's a very special effect。 that is used a lot in the movie industry。

 especially sometimes for marketing and advertising。

 Let me show you yet in another example of some really， really really interesting special effects。

 And this is here。 So this is a movie。😊，Once again， we ran that movie looks really nice。😊。

But actually， after we finished that movie， we might actually w to change the background。

 So here is the same movie with a different background。😊，Wow， this is a lot of work。

 as we are going to see， the basic idea is that we are going to have to be able to segment out this person。

 That's a foreground。 That's what we want to keep in the movie。 We're going to have to find it。

 We're going to have to extract it from the movie and put it in a new background。 That's a really。

 really fun thing to do。 I'm going to run this again。😊，Here is。One movie。

Same movie with a different background。 We're gonna learn about week5， what how to do that。

 how to extract objects from still images or from movies。 and actually。

 this type of things show up in commercial products in this case I'm showing you a screenshot of what's called after effectsect is one of Adobe's products。

 and we actually in collaboration with Adobe and one of my former students。

 we develop what I just show you， which are techniques to extract objects。

 So we can basically put them in new backgrounds。 And I'm going to explain you exactly as many details as I can provide in a relatively short video。

 I'm going to show you how this is done inside after effectsect in Adobe。

 some of the underlying technology that appears there。

 So these are just some examples of image and video processing。

 We started from image compression the NASA rovers。Have to have image compression。

 your digital cameras have to have image compression。

 The video that you're watching now has to be compressed before it's uploaded to the web。

 and we're going to see in the first week of class why。

 why images occupy so much information in the second week we're going learn how to compress them。

 we also saw special effects like imaging painting which we're going to see towards the second half of the class。

 and we saw special effects like segmentation and changing background and that we're gonna to see around week5。

 So a lot of really exciting application。 Some of them you are very familiar from the movies from your digital cameras。

 Some of them you actually see every day， but you're not really aware that they're happening and I'm going to help you to basically understand that they're actually happening behind the scenes。

 And while we're going to do in the next movie， we're going to give a few additional examples to further motivate you the importance。

😊，Of image and video processing and also how much fun it is to understand what's happening behind the scenes with images and videos。

 We're also going to talk in the next video a few examples of medical imaging。

 an extremely important area in image and video processing。

 So I'm looking forward to seeing you in next video。 Thank you。😊。

