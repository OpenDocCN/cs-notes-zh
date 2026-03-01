# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P3：03_01_03_1-什么是图像与视频处理-第二部分.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Welcome back to the image and video processing class。 In the previous video。

 we saw a number of examples that show what image and video processing can do for us。 Now。

 we are going to see a few additional examples。 We' are going to start again from consumer images。

 images of the type that you are familiar with。 And then we are going to move to a couple of examples of medical imaging。

 an area where image and video processing has been extremely successful and a very important area by itself。

So once again， a couple of additional examples on consumer images and videos。



![](img/60ef599f3145751c519d8bd3857c6235_1.png)

So this is a very interesting example of what。Video processing can do for us。

 Let's just watch these movies for a second。 So here we have two kids。

In one video and took it in another video doing exactly the same activity。

 We want the computer to automatically identify that although these are very different people。

 very different backgrounds。😊，In completely different jumping gear and a house one and no house in the other in the background。

 we want to make sure the computer understands that in spite of all those different things。

 the activity is the same activity。 keeps jumping。 We want the computer to actually be able to say that that activity is very different than this one。

Which is actually a person playing with a ball。 But this particular one should be identified to be exactly the same And this other one。

 which is another person playing with a football。 So we want the computer to automatically classify these videos for us based on what activity is happening in the videos。



![](img/60ef599f3145751c519d8bd3857c6235_3.png)

Let's just see another very interesting example。 I'm going to play this video in a second。

 if you see different frames。Surrounding the person So green and red。

 that will mean that a computer has identified that basically。

 the person is doing a different activity。 If you see exactly the same color of the frame。

 So maybe both green or both red means that a computer has automatically identified that a person is actually doing the same activity or the same type of activity。

 So let's watch this movie。So different colors， that means different activities and now same colors。

 meaning same activities。And one more example。In this case。

 we actually have three different persons at three different rows。

 and we have on the left the ground truth that happens very often in this type of problems in image and video processing where you know what you expect so you can verify if your algorithms are working properly on the right。

 we actually have the actual result of the algorithm and once again。

 if you see frames of the same color means that in spite the fact that the people are different people the computer has identified that they're doing exactly same activity。

 If you see different frames， different colors means the computer has identified they're doing different activities So they just watch the movie。

So look， the three of them are green and out this moved to yellow。

 which means that the computer understood that the person changed his or her own activity。

 moved from running to jumping。So that's everything that we want the computer to do for us to identify what's happening in the images。

Sometimes we actually want much simpler things。 For example， here。

 we might just want this very poorly。Acquire image to become this very nice image。

 This is something that happens to us all the time。 We take an image that is not。

 It doesn't look as good as we want it to look。 For example， this， this is an extreme case。

 We are going to understand what happened actually in this image。

 and we want to automatically after we have taken the image。

 We don't want to go back and take again that image。

 We actually want the computer to automatically for us。 give us a very nice image。

These are just examples of things that we are familiar with。 A more complicated example is here。

 yet another movie that basically what we want is to be able to identify everything that is happening in the movie。

 This is sometimes called computer vision and not image processing。

 although the two areas are closely really， really closely related。

 And we're going to discuss that during the next coming weeks。

All this has been about consumer imaging。Image and video processing， in particular， image processing。

 but also a bit more in these recent days and recent years。

 video processing is extremely important in medical and biological images。

 And let me give you a couple of examples that are very exciting applications where image and video processing can actually make a tremendous impact in society and health。

😊。

![](img/60ef599f3145751c519d8bd3857c6235_5.png)

So this is a particular application。 We're going to talk about this application actually the last week of the class。

 and this is a particular application that is related to neurosurgery。

 I'm going to describe this application again， as I say in the last week of this class。

 but the basic idea is that the neurosurgeon implants。In the brain。

 an electrode and sends some excitation to that electrode， and this is extremely important for many。

 many problems like Parkinson， tremor， depression or other problems。

But a fundamental problem is that a neurosurgeon needs to see inside the brain。

Needs to know where he or she is going inside the brain。 And in order to do that， we are actually。

 in order to know where to implant the electrode and where exactly。To go。

 the neurosurgeon will take images of our inside of the brain through MRI C or other disciplines and try to get a map。

 try to get basically what we see from Google Maps or from other images。

 they want to know have a map from inside our brain。

 So they want to be able to map everything that is happening in our brain here。

 So one of the areas that they want to implant the electrode。We find it here。

So is these fancy and beautiful in color images that you see here is a combination of multiple modalities that are used to look inside our brain that are put together with techniques that we are going to discuss。

 and then you can create these beautiful images that localized and also tell you how different parts of the brain are actually connected。

Once you do that， you can actually map， as I mentioned。

 you can actually map the brain and understand these are actually electrodes that were implanted。

 and you can localize where exactly is the electrode touching in the brain。

 So it's really seen inside our head。 and a lot of image processing needs to go behind this to make this possible。

 And as I say， this is a very exciting area because the contribution of doing image processing here is tremendous。

Similarly， we can look at HIV research again， we' are going to discuss this more at the end the last week of class。

 were going to have an entire lecture about this particular problem and the image processing challenges so this is basically a virus and this is a schematic of an HIV virus and for reasons that we are going to discuss later。

We need to identify the actual shape of this。 This is schematic。 You might say wisely so difficult。

 I'm going to show you that in just a second。

![](img/60ef599f3145751c519d8bd3857c6235_7.png)

The basic idea is that。We need to be able to identify that what has just marked to you looks like this。

 This is a three dimensional rendering of exactly that what's marked in the picture as the Gp120 and the G P 41。

 So that's what's called the envelope。 And that's a very important part of the virus that the virus uses to basically。

Large into the next cell。 And identifying that shape is， is very， very important。

What's behind the scenes。 So why is this so difficult。

 Because actually what you get is images like this。 And basically。

 this is what the schematic of what I showed you before。 And these are these small envelopes。

I show you before。Okay， and from images like this one。

You need to be able to do reconstructions like the ones I'm showing you now。Okay。

 so this is basic science that has a tremendous potential contribution。

Into the development of vaccines or the understanding of different viruses。Finally。

 sometimes image processing， as we thought that it can help neurosurgery can help other kinds of surgery to make them safer。

 This is a particular application where it's important to understand where thesophagus is。

So cardiac ablation， which is a very common surgery when it's done it avoids basically touching it and maybe damaging it。

 so once again narrow application of image processing which we are going to discuss during this week we are going to discuss different type of applications we are going to touch on some of them we won't be able to touch on all the medical imaging applications out there。

 but we're going to touch enough to give you an idea of why image processing is so important in the area of medical imaging and biological。

デた。So to conclude， we have in these two videos we have seen a large number of examples。

Conference scientific data from Mars to consumer videos and images。

 like in the movies or like images that we take with our own cameras all the way to medical imaging。

 and we are going to discuss during the next nine weeks starting with this week。

 the basic techniques that we need to be able to achieve all what which has seen that we want or we need to do with images。

So， see you in the next video。