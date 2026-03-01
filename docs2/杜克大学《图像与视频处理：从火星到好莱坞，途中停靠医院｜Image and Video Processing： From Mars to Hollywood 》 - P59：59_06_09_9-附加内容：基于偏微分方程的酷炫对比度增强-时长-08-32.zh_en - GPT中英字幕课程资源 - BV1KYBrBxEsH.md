# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P59：59_06_09_9-附加内容：基于偏微分方程的酷炫对比度增强-时长-08-32.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。I want to give you an example of a very particular and important application of partial differential equations and variational formulations in image processing。

 and this will put together some of the concepts that we have just learned in a very。

 very simple fashion。 So what we are going to do is we're going to do is modification with partial differential equations。

 We know how to do Instagram modification。 We have learned that a few weeks ago。 Now。

 I'm going to show you how to do that with partial differential equations。



![](img/89f6ec07b6f129f8cf70676e7effc745_1.png)

The basic idea is， as we always do with partial differential equations。

 we want to deform the image towards a certain goal。 In particular， now。

 we want to change the contrast。 We want to deform the image in such a way that improves the contrast and we can start thinking about how to do that。

 if we understand partial differential equations。 We want to stretch the gray values of the image。



![](img/89f6ec07b6f129f8cf70676e7effc745_3.png)

Now， how we're going to do that in this particular case。

 we're going back into Instagram modification。 We know how to do that。

 We learned that it's just a simple map that we learned a few weeks ago。

 So here is how you do it with a partial differential equation as an illustration。

Here is the partial differential equation。 You're going to deform the image。

According to its own pixel value at the given pixel minus the number of pixels that are greater than you。

 So you have an image。You're sitting at a certain pixel and say， how am'm going to change this pixel。

 very simple， you look at your own value， you look at how many values are above you。

 and you deform yourself。According to that， to the difference between both of them。

Now why is this doing Instagram modification very simple， remember what we talk？Normally。

 you deform the image equal to your goal。 Now， when you get to steady state this。Becomes0。

So the image becomes equal， the pixel value of the image becomes equal to the number of pixel values above your own value。

 and this is exactly if you go back to your notes on istogram modification。

 this is exactly istogram Qization。😊，So this is a very interesting way to achieve ist Qization instead of doing a lookup table。

 as we learn， we just slowly deform the image towards it。Now， you may ask yourself。

 why do I have to implement a partial differential equation that is computationally more expensive than just doing that look at the table。

 There is a couple of reasons， One， pedagogically， I'm giving you this as an example of。

A partial differential equation， achieving something that we want to achieve like exactly the condition for istogramization。

Now， there is another reason you might stop this deformation at any moment。In Instagram equalization。

 you do the map。 There is no intermediate solution。 If that was too much contrast。

 then you are in trouble。 There is no way either no way back， either the original image or that here。

 you can start stretching your Instagram start moving towards Instagram equalization。

 but you can stop before you finished that if you are already satisfied with the result or even if that result is better than going all the way to Instagram equalization。

 So those are examples of why you might want to do a partial differential equation instead of a lookup table。

 Now， of course。In the same way that you can do partial differential equations。

 you can try to do this contrast enhancement by solving a variational problem。

And here is an example of such a variational problem。 Again。

 the art here is for you to start putting terms in the variational problem that will help you to achieve your goal。

 So here is one term。 Remember， what we try is to optimize for this is basically to minimize or to maximize in this case to minimize this energy。

 So this is a term that normally you put in these kind of things。

 And here I'm assuming the images between0 and1。 It has been normalized。

 So the pixel values are between0 and1。 You say， you know， I want the image to be nice。

 I don't want it just to be too far away from the average gray values and that you achieve by this。

On the other hand， you want contrast。So here is the contrast。

 You don't want the pixel values all to be together。 If I don't have this term。

 if I remove this term， the solution of this is a constant value equal to half。

 all the pixels values are in the middle altogether。 That's not what I wanted。

 I want them to be nicely distributed as expressed here。

 but I also want to contrast a note that we have a minus sign here。

 And because I want to encourage pixel values to get far away。 Now， I don't want them to go crazy。

 far away。 And that's why you add other type of terms。 Now we have integrals here。

 which is where do I count these。 Do I count it all around the image。

Now there is also part of your game。 You can say， hey。

 I'm going to just ask for this contrast in certain regions of the image so you can do the integral only for certain regions of the image。

 or you can say I'm going ask for these contrast only for certain ranges of pixel values。

 So you can actually become very creative in designing this variational formulation。

 the same for these direct Pds。 something that you couldn't do when you had the lookup table。

 It was like one to one from here to here， there is nothing in between here it gives you a lot of flexibility to become very very creative。

 So let's see some results of this。

![](img/89f6ec07b6f129f8cf70676e7effc745_5.png)

Here we have two examples。Contrast enhancement here。 Now， the interesting thing here。

 you might notice that basically this is kind of localize。 Every region kind of moved by itself。

 and there are no mixing of the regions。 and this was achieved by playing with those Instagram boundaries with those integration boundaries。

 sorry， and making sure that things that have similar pixel values or in this case。

 exactly the same pixel values can of move together。

 So here is an example of an artificial image to illustrate how these variational formulations can give you contrast enhancement that preserves the shapes of the image。

 And here is another example of a natural image。😊，I hope you can appreciate that through the video that this is a very dark image and here you have much vivid colors and much nicer looking image and these two examples are achieved with these PDds or variational formulations those are two different and one gives you some capabilities the other gives you and our capabilities and playing with the integral limits and playing with the terms inside the integraltes。

 you can start achieving that kind of application that you want for this type of contrast enhancement So I hope you enjoy these example。

 it illustrates both the concept of PDds that we can almost achieve any condition than we want if we run the PDd to steady state and also it illustrates how we can design variational formulations for an extremely important application that is contrast enhancement。

😊，Thank you very much， looking forward to seeing you in the future videos。



![](img/89f6ec07b6f129f8cf70676e7effc745_7.png)