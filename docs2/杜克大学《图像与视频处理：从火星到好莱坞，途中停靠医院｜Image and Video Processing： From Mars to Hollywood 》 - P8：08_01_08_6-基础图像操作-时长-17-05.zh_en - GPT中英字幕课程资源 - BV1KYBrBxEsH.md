# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P8：08_01_08_6-基础图像操作-时长-17-05.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

![](img/99e246638ae04d6fd06959fa809460ae_0.png)

Now that we have images in the computer represent us。

We learned in the previous video discrete two dimensional arrays。 Basically。

 we started from a continuous picture。And we finish with her。To dimension discrete grid array。

 now we can start doing operations on these images there in our computer there are just two dimensional arrays of pixels。

 we can do very different types of operations to do the kind of things that we saw in the first couple of videos in this class。

During the next few weeks， we're going to learn very sophisticated operations。

 but let's start with just a few very simple ones that they're very simple。

 but they' are extremely useful， and they will tell us how we actually can manipulate images and you can go into your computer and do any of the examples that I'm going to show in the next few slides in just a few minutes or even less if you have a programs like Madla that are natural to work with two dimensionmensal arrays。

Once we have a two dimension array， one of the things that we can start talking is about neighborhoods。

 so remember we have a two dimension array。And we are talking about pixels。 So this is a pixel。

 And I can ask， who are the neighbors of this pixel。

 And there are two types of standard neighborhoods that are taken in image processing。

 One is called a four neighborhood。And only these four are considered。 And that's basically。

 you can only go north， south， east or west。 So just a four neighborhood。

 There is another very popular。That is。A neighborhood。 And you probably already guess how it works。

 So if I'm here， the neighbors， the a neighbors of this pixel are all the pixels around it。

 So you can go north and south， east and west as before。

 But you can also go like northeast and start going diagonal。So for example。

 if I look at this image here， this pixel。In a four neighborhood relationship is not a neighbor of this one。

 So these two ones are not neighbors。Because I cannot go diagonal in a fourth neighborhood relationship。

 in an a neighborhood relationship， they are neighbors。And that， of course。

 translates also to group of pixels。 So these group of pixels。

Has an a neighborhood relationship with this one because there is a one here and a one diagonal。

 and I'm allowed to go diagonal。Okay，Now， if I were to talk about fourth neighborhood。

 I will say that this group of ones。I's not neighbor of this group of ones because from this one。

 I can only go south。 I don't see anybody from this group any onces。

 I can go right is I don't see anybody。 So basically depending on how we define neighborhood in this discrete space。

 what kind of operations we can do。 and we're going to see that that's very important。

 This is the most common neighborhood today use in most modern image processing。

 but it's important to be aware of this type of neighborhood。

 especially when we're going to be doing segmentation and things like that。

 we're also going to later on when we talk about the last week， we're going to talk about 3D images。

 So not images that have gray values on the plane like here where every pixel it has a gray value but we're going to talk about volumetric images where every point in the volume。

 those are going to be called voxels have gray values and the neighborhood relationships are。

Very important there， for example， in medical images。

 to decide that this organ is neighbor to this organ。

 we're going to have to define the neighborhood relationships and the same when we're going to do segmentation。

So neighborhoods are important， but now that we have two dimensional arrays。

 we can do simple operations between two dimensional arrays。 for example， we can add them。

 remember every point。So if I look at this image， every point here has a value。

 so I can take that image and add to a second image so I can take image1。And add it to image 2。

 That means that I take。And' drawing a small image in purple on purpose， this is a 3 by3 image。

I'm going to take the value here and add it to the value here。

 So if here it's a 7 and here it's a 10， I'm going to get a result which is 17。

 Then I go to the next pixel， and I do the same。 So simple addition of images。

 That's an extremely important operation by itself。 very simple。 So here we see that operation。

 We basically have。😊，NASA took images multiple images of the same galaxy。 multiple times。

 they go once and again and take more and more and more images。 The images are very noisy。

 but all the images are aligned so they don't move the camera。 and nothing is moving。

 they take one after the other。 and then they start adding them。 when they add the images。

 when they add the images， they start getting clear and clear。 So here they basically added5。

Then they added 10， so on until they got 100 images， so they did I1 plus I2100 times。

 so they have 100 images of this galaxy and they added them together and what happens is the image starts becoming clearer and clearer because the image has noise the image is always the actual sin is always the same sin。

 the noise is the one that changes is that changes and when you add all those images you are adding the same number plus the noise that is random and then the noise gets reduced and when we talk about special denoicing and how to do image enhancement and we're going to discuss this very。

 very in detail， but the basic idea is that we can simply add these two dimensional array to do a number of interesting operations。

We can do other things Basically， we can also mask them。

 We can subtract them so we can have an image。Like this。And our image like this。

 let's say two variations of the same scene， but taken under different conditions。

 And then we take the difference between them。 And look。

 the difference shows something that might be very， very important for the doctor。

 And this is just an enhance that we are going to talk about this， how we enhance images。

 for example， by changing the gray value distributions to make them more clear。 So in this case。

 we take we took。I won。Ii， too。 And we basically did， I1 minus。I， too。

Sometimes we take the absolute value if we don't care about design sign。

 and sometimes we just basically shift all the pixels so the negative value becomes0。And once again。

 a very simple operation that can have tremendous value。

That we can also do logic operations in images so we can have basically an image A and an image B and do A U B。

 So basically we。Let's say that this is all 255， the rest is0 B again it's all 255 so we get the union of them。

 we get the intersection， all the pixels that both objects have 255 or y values。 So again。

 think about any type of operations that you could do with two dimensionsal arrays in your computer。

 you can start doing with images now that we know that there are nothing else in the computer than two dimensional arrays。



![](img/99e246638ae04d6fd06959fa809460ae_2.png)

We can also basically take the inverse of an image。

 and the basic idea is that this remember was zero， very black。The brightest point。2，55。

And then we can actually invert it。 We can make the0 go to 255 and the 255 go to0。

 It will be a map like this。If this is the input。

![](img/99e246638ae04d6fd06959fa809460ae_4.png)

And this is the output。It will be something like this。A0 goes to 255，255 goes to 0。

 So we invert the image， and then we can。Using that， we can find some interesting things。

 and that might be easier to observe certain objects in the image in the invertted image that it was in the original image。

 Again， a simple operation with the array that we have representing our images in the computer。

We can also do different spatial。 So this was adding images， so I take an image。

 I take another image， I added it， or I invert an image。But we can do more sophisticated things。

 we can actually take a pixel in the image and replace it by the average of its neighbors。Now。

 remember， I have to define what are neighbors。 Okay。

 so let's consider at8 neighborhood as we talked before。

So I can take this pixel and replace it by the average of everybody， including itself。

So we just sum all the pixel values。We divide by 9， and we replace that pixel by that result。Okay。😊。

And this is the original image。 We do that for every single one of the pixels。

 So we go to this pixel。I'm going to market it here。 We go to its。E neighborhood。

 and we replace the value of the pixel by the pixels by the average of the pixels around。

 then we go to the next pixel。And we do the same。 There would be overlapping。

I'm going to just use a different color here。So。This one。Will use this。This， this， this， this， this。

 this， and this。While the blue 1。Has used this one， this one， this one。 So it's on8 neighborhood。

Okay， so there is overlapping because we are shifting one pixel at a time。

 And then we do that for every single pixel and in the image。

 you are very welcome to try this exercise。 And this is what we get。 We remove the noise。

 but we also get a very blurry image。😊，And we're going to see why that happens。

 This is a very useful image processing application in some cases。

 we are actually going to learn how to do this so we actually take neighborhoods but they are sophisticated neighborhoods in the sense that they understand when there is a big change and they don't go to the other side so we are going to basically maybe end up averaging only these six instead of always averaging nine values。



![](img/99e246638ae04d6fd06959fa809460ae_6.png)

But this is a very simple operation。 every pixel replaced by a linear combination， in this case。

 an average of the pixels around it。The other thing that can happen to images is they can be transformed。

 and we can do very different type of transformations。 We can。 So if this is my image。

 we can do nothing to it。We can actually scale it， just make it larger， We can rotate。

 We can shift it or translate many， many operations so we can take that array and move it。

 We can take that array and rotate it We can take that array and scale it Again。

 these are all two dimensionmensal arrays in the computer so we can do any of these operations and here is what will happen so we are going to rotate the image。



![](img/99e246638ae04d6fd06959fa809460ae_8.png)

![](img/99e246638ae04d6fd06959fa809460ae_9.png)

So we take this T， we rotate the whole image。 But when we see a rotation of the T。

 and here is a zoom in on the edge。 And this illustrates， again， the issues with this gratization。

 So when I have a straight line。In a discrete image。And the trade land goes here。He looks very nice。

But when they straight line， as it happens here。Goes around。

Go diagonal it gets kind of truncated like we see here and the more pixels we have。

 the less we are going to notice this， but now we are discussing just the possibility of rotation。

 the possibility of different operations on images。



![](img/99e246638ae04d6fd06959fa809460ae_11.png)

And here is the full example。I want you to basically look at this。 So this is my original image。

 We rotate it。We can rotate it back。It looks perfect to us， although it has some differences。

 this is the difference between these two images。

![](img/99e246638ae04d6fd06959fa809460ae_13.png)

Okay， so if I were to write down what happened here， I had an image。I rotated it。艾卑斯隔你。

Took this result， which is this。And rotated it。In the opposite direction and obtain this。

 and then I subtracted these two。 basically I subed I。From this one。 So this is I。

 this is the rotation。 This is the inverse rotation to the result， and this is the abstraction。

 And the reason we have differences is because of this sampling。

 this discretization of the space that we discussed in the previous video。

Theres one more thing that we can do on images and we're going to basically discuss this next week when we talk about we talk about compression。

 we can actually do transforms to images and those of you that already took DSP classes know that one of the transform that we can do is a Fourier transform so we have an image We do a Fourier transform of E and that's going to be very important in compression we are not going to do Fourier we're going to do what's called discrete cosine and transform。



![](img/99e246638ae04d6fd06959fa809460ae_15.png)

So this is an image。

![](img/99e246638ae04d6fd06959fa809460ae_17.png)

And we are doing a Fourier transform of it。This is the Fourier transform。And now， you see noise。

So where can filter in the Fourier domain， and I haven't discussed。Any。

Background in signal processing as Fourier， we are not going need a lot of feed。

 I'm going to discuss at every week。 the background that we need for that week。

 and we are not going to do a lot of Fourier。 So if you haven't I mean。

 we can do a lot of image processing without knowing Fourier transform。

 So if you haven't taken any DSP class don't worry we are gonna be able to do everything but this slide without knowing Fourier。

 So don't worry about that。 But those of you that are familiar with Fourier and you will see that I can filter this。

 for example， this filter。 and then return。 So I do a transform。I fit there and I come back。

 and I get a very clean image。So once again， those of you that are familiar with basic signal processing and Fourier transform。

 this is nothing else than a Fourier filter for those of you that are not familiar just think that I took the image。

I took that two dimensional array， and I transformed it into a different two dimensional array。

 I did some manipulations there， and I came back， and I got a very clean image back。And once again。

 this is only to illustrate that what we are doing here is operating with two dimensional arrays。

 where at every point we have a value that represents the blindness or the color in that particular location or in that pixel。

So now we know we have images as representing the computer now。



![](img/99e246638ae04d6fd06959fa809460ae_19.png)

We have seen already that we want to have a lot of pixel， we want to have a lot of gray values。

 and that's going to take a lot of space and we're going to see in the next videos for the next week about compression。

 which is how do we deal with that large amount of data that we need to have very good image quality Thank you。

