# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P45：45_05_07_7-交互式图像分割-时长-21-13.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。 One of the reasons that image and video segmentation is studies so much in image processing is because of its relevance to multiple applications from the movie industry to medical imaging。

 as we're going to see in the last week of this class。

 The other reason that theres so many studies in this area is because image and video processing is intrinsically a very difficult problem。

 And what we are going to do in this video lecture is basically introduce the concept of interactive image segmentation。

 We're going to let the user help us to do the image segmentation。

 So that's basically the topic of this lecture， interactive image segmentation。

Let me show you a couple of examples， extreme examples of the difficulty of image segmentation。

This is a really nice image。 If you haven't seen it before， it looks nothing strange to you。

 It's just basically a drawing of a forest。 Now， if you look very carefully and invite you to do that。

 you start seeing faces in this image， faces that are camouflage， for example， we see a face here。

 I hope you can see it。 their eyes， nose， a mouth。😊，Here， there is anotherer face here。 Once again。

 the eyes， the nose and the mouth。There is another face， camouflage here， eyes， nose， mouth。

There's a profile face here， the eyes， the nose， and the mouth。 There is actually a lot of images。

 If you stare at this image for some time， you're going to start discover more and more faces that pop out from this image。

 Now， this is a really challenging image segmentation problem to segment out the faces。

 It becomes easier if I tell the algorithm more or less the location of those faces。

 So then the algorithm might be able to find the eyes in those locations。

Let's see yet another example you are working to post the video and observe this image for longer if you wish to discover more and more faces。

 Let's look at the next example。Another very interesting drawing。We see a tree。Here。

We see houses in the back。 We see a lady。Now， if you stare at this image and in particular。

 if you take a bit of distance from the screen and sometimes if you kind of close your eyes to blur a bit the image。

 you may actually find that there is a face here。The lady becomes the nose here。

 part of the buildings basically become the eyes。So once again。

 how can we tell the image segmentation algorithm to segment this very。

 very difficult image in particular， how can we tell the algorithm if we are interested in the tree。

 are we interested in the face， are we interested in the nose or the lady， what is foreground。

 what's background to illustrate what's foreground， what's background that is a very。

 very difficult problem， Let's use this famous image， We actually see here。



![](img/19c5c92d35a0b77206b0fb37d60fe95a_1.png)

2 profiles，1。2。I hope you can also see if you look at the white region， we see actually a glass。

So what is for us for grant， the profile or the class it's very hard for the algorithm in the computer to understand what is that we are interesting。

 what's interesting in the image for us。 So one way of doing that is let's the user。

Tell us what's for， what's background。 Let us use the user， Basically。

 which is the real client of this and the one that is interested in the segmentation。

 Let us use the user to give us a bit of information about the image and the way to do that。



![](img/19c5c92d35a0b77206b0fb37d60fe95a_3.png)

That we are going to exploit。 is' basically we're going to ask the user。

To mark very simple scribblels， the user is going to come and just scribblel。

 Here is a straight line， but just can be any mark in the image as we are going to see later and say。

 you know， I want to call this background。Another script said， I want to call this foreground。

 Now go and segment it。

![](img/19c5c92d35a0b77206b0fb37d60fe95a_5.png)

So that's all what we are going to ask from the user at this stage， we might ask more later on。



![](img/19c5c92d35a0b77206b0fb37d60fe95a_7.png)

Once， of course， we segment it out， we can do different things like putting new images in the background。

But it's very important that we are going to get help from the user。

 We shouldn't be asking a lot of help。 We shouldn't be asking the user to go around and basically completely mark the boundary of the object then there is not much left for the computer to do and that's very tedious which is still done sometimes but it' very tedious work for the user we want very little interaction that can help us a lot。

 How can we exploit this crs。 so I'm going to illustrate that I'm going to tell you a particular pipeline to exploit this。

 but the underlying ideas are very common in multiple multiple techniques for image segmentation that you can find in the literature。

So the user has given us hints of what's foreground。Doug， we see here。And what's background。

 we can basically go and look at all the pixels that the user has marked as foreground。

 We can draw the inogram。 We can draw the distribution of those pixels。

We can do basically the same for the background。 So we end up with a distribution of foreground。

 We end up with a distribution of background。 Very often。

 the background has much more variability than the foreground。 Now， if you now give me a pixel。

I can compute what's the probability of being in the foreground。

 what's the probability of being in the background from these distributions that the user mark once again。

 all what I'm using are the pixels that the user mark as foreground and the pixels that the user mark as background。

We can actually normalize this。 So here we use C to stand for the vector in color space。

 It can be RGB， red green blue， It can be other color space。 It doesn't matter。

 It's whatever are the colors just under the scribbles that the user has marked。And again。

 we have these distributions。And we can compute the probability of a pixel being forground or back。

 which is just the probability of being foreground， and we normalize by both foran or background。So。

 for example， a pixel that was marked by the user as being foreground。

 it will have a very high probability that pixel value。basicallysically once again。

 this is just a particular illustration， the basic idea is that we use the distribution of the foreground and the distribution of the background to tell the computer you know。

 pixels that are similar to the colors that the user has mark as forground。

You should try to call them forground。Pixs that are similar to the color of what the user has Mark's background。

 you should try to call them background。So now we have kind of an idea of what to call foreground。

 what to call background。If we just take basically this formula and withdraw that。

 we' are going to get this， which is already a very interesting segmentation just by looking this exercise and looking at this image。

 we can almost find the object of interest basically what the user told us is the object of interest。

 which is the cut。Now there is something interesting to observe here。 So the higher the value here。

 the more probability of being foreground based on what the user told us。

 So why do you think that these eyes are basically very dark。

 meaning have very high probability of being background and very low probability of being foreground。

 And that's because theyre very dark and look Also here， we have very dark pixels。

 So if we just look at the pixels that the user has marked。

 that's not enough information for us because they might be inside the object of interest。

 some pixels that look as the background。 So we need to do a bit more。 What can we do。

 Let's just see that next。

![](img/19c5c92d35a0b77206b0fb37d60fe95a_9.png)

What we're going to do is we're going to basically try to find。

All the pixels in the image compare them with the probability of being foreground and the probability of being background。

 And then we are going to make a decision how we are going to do that comparison using something which is called jodesic。

Distance， and this is something that you basically do every day when you go to work。

 when you go in your house from your room to the kitchen， you're basically traveling a path。

 and you're going to try to travel all the time， the path of minimal effort。

 So if you want to go from your room to the kitchen and you don't want to you want to get there as fast as possible。

 you go in the shortest path。 Now sometimes that path has an obstacle。 So for example， a wall。

 you cannot go through the wall， you have to go around the wall。

 So if you draw a map of your office or your house。

 there are certain regions that are very easy to go through certain regions that are much harder to go through。

 So when youre going to go from one point to another， you might not be able to go an a straight line。

 for example， if there is a wall。We're going to have to basically go around it and the basic idea is that every region in the path has a weight and that weight we're going to call it w。

 What we're going to do is we're going to go to every pixel in the image。

 and we're going to compute the minimal path to the foreground scribble the minimal path to the background scribble。

Once we have that， we're going to decide if it's for of background。

 according to which path is shorter。So I have to tell you， what are we going to use as w。Before that。

 let me just make a remark that this can be computed very fast， actually in linear time。

Visiting every pixel of the image only once， you can compute the。Distance， the path， basically。

 this formula to the for and to the background。 So this is not very difficult computation。

 This is based on extensions of techniques that are called diasra techniques。

 and they are very standard techniques in graph theory。

 and we're going to discuss them a bit more next week when we talk about partial differential equations。

 For now， all what I want you to know。Is that this computation of what's the minimal effort from traveling from a pixel to any one of these scribblels。

With a weight that I'm going to define in a second， that minimal effort can be computed extremely。

 extremely fast。 Okay， basically can be done in real time。

 So what's w which is computed thanks to describeribbles the distribution of colors。

 So that's what we are going to use， We're basically going to use。



![](img/19c5c92d35a0b77206b0fb37d60fe95a_11.png)

That probability that which has computed。And what we are going to think is the following。

If from the pixel I'm sitting， go into the scribble。

The probability of being fore grown doesn't change too much。

That means that I'm probably a foreground p。If I can keep going from myself。

To the forgr scribble and the probability of forground doesn't change， meaning the gradient。

Doesn't change。 Remember， gradient is the difference between consecutive pixels。

In the direction of the path。 So this is the curve。 So I'm going to travel the curve。

 I'm going to basically go from every place。In the image。To a sc it。I'm going to look for a path。

 and I'm going to say， iss my probability of being for changing a lot around this path。

 If it's changing a lot， I'm going to pay a big price。 If it's not changing a lot。

I'm going to pay a small price。 Then I can take another path。I'm going to see which path。

Is shorter with this weight。And I'm going to do the same for another point。In the script。

I'm going to basically do that for every point in the scribblel。

 so I'm computing to every single point in the scribble What's the path where my probability of beam foground is smaller then I have to do basically the same for the scribbles。

Of background。 So for this pixelel， I'm going to say， what's the probability。

 what's the cost of getting to the background。 And then I'm going to compare them。So in pictures。

 when we do this computation， which again， can be done extremely fast。We have these crbbles。

This was the probability we computed before， this image。

This is an image where the colors blue means low， red means large， same here， basically blue。

 going to red。 We are basically going from small to large。

 We are basically saying that every pixel here has a very large distance basically to the foreground。

 But pixels here has very low distance to the foreground。 and the inverse here。

 So I want to repeat that once again。 We first computed the probability based on the color distributions。

That the user has marked for us。Then we say， okay， and I'm going to just use a figure to illustrate that。

 We basically say， from every pixel。

![](img/19c5c92d35a0b77206b0fb37d60fe95a_13.png)

In the image。Let's just compute curves。That start at the pixel。 finish a dec scribble。

 And let's see what's the cost of travelling that curve。 And the cost is given。By this function。

The less it changes， the probability of being for。The lower the cost。

We do the same to the background。For every pixel。 And then we say。

Is it cheaper for you to get to the foreground scriva？

That it is for you to get to the background scril， then I call you a forground pixel。

If it's the other way around， I call you a background pixel very easy。

 all the computations are done computing this minimal effort curve going by the image only once once you have done that for every pixel。

 basically you draw the boundary。Of the probability of being by grand or foreground and you get your very。

 very nice segmentation。Relatively simple algorithm。Now we can do a bit more。

This was based on scribbles that were marked somewhere。 So there was a foregground scribble here。

 and there were a few。Background scbbles around。But now we have a first estimate of where our boundary between foreground and background should be。

 We can exploit that in a second stage， which is fully automatic。 And the basic idea is very simple。

 Okay， let's just go back。

![](img/19c5c92d35a0b77206b0fb37d60fe95a_15.png)

This was what our first estimate was。They just move inside the object a bit。😡。

And let's move outside the object a bit in a fully automatic fashion。And we can call this now。

A for grand Scri。Not the one that we mark before， we call this one now。

 which is automatically computed， we call it a foreground scribble。

 and we call this a background scribble。And I can do my algorithm once again。

 but I can do the estimation of the probability of being foreg。Now based on a scribble。

 which is very， very close to the boundary， so it probably has better information about where that boundary should be and actually moreover。

 we can actually do that locally。If I want to refine this boundary。

 I can only look at this crribble and this piece of this crribble compute my probability。

And refine it。Then go into a different region and also only use that to refine this and so on so I can travel around my first estimate。

 get new estimates of what should be foreground and what should be background and get a really。

 really， very accurate segmentation from that。 So we run twice the algorithm。 First。

 we let the user help us to find this distribution。 Second。

 we let the initial stage to tell us how to compute that distribution。 and then we get a really。

 really nice segmentation。 as you can see， we can basically get very accurate at the boundary very。

 basically we get the hairs and we get really， really good results with that。



![](img/19c5c92d35a0b77206b0fb37d60fe95a_17.png)

![](img/19c5c92d35a0b77206b0fb37d60fe95a_18.png)

So let me give you a few examples of this and we see them basically here。

 we have in every row examples and we can see this crbble。

This is the binary segmentation and then as we already talk。

 I can put it in a different background here are basically different images， different images。

 so basically every row has a different example， It's very important when you do any image process algorithm that works for a lot of data。

 you don't want to design an algorithm that works for only one type of data。

 you want to be as global as possible unless you have a very particular application in mind and then it's always important to show that it works for a large variety of images。

Now， you may wonder what happens？Do I need the user to be an expert。

 Do I need the user to basically be。You know， have complete knowledge of the algorithms and mark these scribbles exactly where they should be to give me the hints。

 Of course， if that's needed， then this algorithm is not very useful。

 We want the user to basically work with the algorithm in a very relaxed fashion。

 So here is just an example that these type of algorithms are normally very robust。

 So we have the same image and very different foreground scribbles， The blues。😊。

And very different background ss the greens。 And we see that basically the results are the same。

 You see the boundary between foreground and background being basically identical in all the images。

 So we want really the user to be very， very friendly with the images。

 and the algorithm not to ask too much of the user actually。

 it has very little is basically all what the algorithm ask is the user to say。

 please mark me foreground and basically go and please mark me background。

 I used the different colors in my pen done in the image， but the message is very clear。

 So this is an example of interactive image segmentation The user has help us。

We're going to see a couple of additional videos， one。

 we're basically going to be running this inside Adobe Photoshop， one of the examples。

 the other we're going to do interactive video segmentation in one of the next videos and it's one of the basically algorithms inside one of Adobe's products that I'm going to give you details about this so I see in the next videos Thank you very much。

