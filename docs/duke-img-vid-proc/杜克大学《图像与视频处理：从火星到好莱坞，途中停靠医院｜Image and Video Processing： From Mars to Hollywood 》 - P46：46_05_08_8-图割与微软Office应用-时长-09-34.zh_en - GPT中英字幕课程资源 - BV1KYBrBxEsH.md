# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P46：46_05_08_8-图割与微软Office应用-时长-09-34.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back In this video， I want to describe a very important technique for image and also video segmentation and other image processing techniques。

 And that's what is called graph cats as we see here。

 And I'm going to illustrate that with a very simple figure。

 And then we're going to provide some examples。 So what is graph cats。

 Let's start from a simple image。😊。

![](img/d4f093f8b9b1f27a541ad09c4f380121_1.png)

White and black， and the basic idea of graph cuts is to borrow tools from graph theory to partition this image into foreground and background。



![](img/d4f093f8b9b1f27a541ad09c4f380121_3.png)

So we're going to tilt the image just for the sake of illustration。

 and we're going to take one line across the image as we see here。



![](img/d4f093f8b9b1f27a541ad09c4f380121_5.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_6.png)

So we take one line and basically we are going to represent that line here。

 Every pixel is going to be a node on a graph that we are going to build in just a second。

 So these represent pixels in a very coarse fashion just to illustrate every pixel one node。



![](img/d4f093f8b9b1f27a541ad09c4f380121_8.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_9.png)

In the image。

![](img/d4f093f8b9b1f27a541ad09c4f380121_11.png)

And now we're going to add two nodes， one which we call the sink。

 and that's going to be represent background pixels。



![](img/d4f093f8b9b1f27a541ad09c4f380121_13.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_14.png)

And the other is going to be the source。 And that's going to be representing the foreground pixels。

 Once again， we have for every pixel in the image and node， So there will be a lot of notes here。

 You can think about a graph that is planar。

![](img/d4f093f8b9b1f27a541ad09c4f380121_16.png)

In for those images and then you can think about basically putting a source and a sink。

 so we have a lot of here we have a lot of basically planar nodes and we have a node on the top and a node on the bottom So now we have the node on the graph on the graph we need now to construct the edges。

 How do we connect these nodes。

![](img/d4f093f8b9b1f27a541ad09c4f380121_18.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_19.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_20.png)

First of all， how do we connect every node representing a pixel to the foreground source and to the background seek？



![](img/d4f093f8b9b1f27a541ad09c4f380121_22.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_23.png)

And the basic idea is that we connect them with some measurement of the probability of the node。

 meaning the pixel being background or beam foreground So for every pixel in the image。

 we got a node and we look at that node and somehow we say what's your probability of being foreground and we connect that to the source with the weight related to that probability。

 That's the weight of the edge， And then we ask what's your probability of being background and we use that probability to connect to define the weight of the edge that connects to the background sync。

 how can we can compute those probabilitybabilities。



![](img/d4f093f8b9b1f27a541ad09c4f380121_25.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_26.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_27.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_28.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_29.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_30.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_31.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_32.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_33.png)

For example， as we saw in the previous video， if we are in an interactive system。

 we can get them from the scris， exactly as we saw in the previous video。

 you can use information of the surrounding pixels。

 So that's very open and is part of the design of the algorithm。 But the simplest is。

 as we saw in the previous video to use information from the scris。

 So now we have connected every node， meaning every pixel to the source and to the background sink。

 Next， we need to connect the pixels among themselves。😊。



![](img/d4f093f8b9b1f27a541ad09c4f380121_35.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_36.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_37.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_38.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_39.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_40.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_41.png)

So， we're going to also construct。Adgeges connecting pixels among themselves in particular。

 we are only going to connect to the neighboring pixels， meaning the neighboring nodes。

 So the one on your right， the one above you below you on your left。 Maybe diagonals。

 We talk very early on in this class about four neighborhood and a neighborhood we will probably use only one of those。

 And now the question is， what's the weight on this edges。 And I want you to think for a second。

 Why would you put here， has to be something that helps you in the segmentation。

 So why don't you think for a second and write it in the inline quiz that I'm presenting and tell me what do you think should be there。

 The weights。

![](img/d4f093f8b9b1f27a541ad09c4f380121_43.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_44.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_45.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_46.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_47.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_48.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_49.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_50.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_51.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_52.png)

Thank you very much for thinking about the question I just asked。

 The weights have to be basically something that promotes pixels that are very similar to stay together。

 to stay in the same segment and pixels that are very different。



![](img/d4f093f8b9b1f27a541ad09c4f380121_54.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_55.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_56.png)

Promotes them to become different segments for Gr and background。 For example。

 we could put weights that are proportional to the gradient。

 We can put weights that are proportional to the difference of pixel values or the difference of the pixel values in the neighborhood of the pixel。

 So anything that will promote similar pixels， and we have to define similarity depending on the application。

 anything that promotes similar pixels to stay together and different pixels to become a part for Gr and background。

 Once we have constructed the whole graph， Then we call graph theory。

 and we are going to partition that graph。 So we are going to create what's called a mean cat。

 That's a cat with minimal effort， minimal price。 and is going to try to cut for Gr from notes that are very weak。

 So this。

![](img/d4f093f8b9b1f27a541ad09c4f380121_58.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_59.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_60.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_61.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_62.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_63.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_64.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_65.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_66.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_67.png)

A high probability of being background， low of being for。

 so the graph cut is going to try to cut it out， cut it out is going to try to go once we are on the plane of the nodes that correspond to the pixel values is going to try to go through edges that basically we told the algorithm that those edges are connecting pixels that are very different and it probably should be in different regions。

 so it's going to try to cut weak edges because it's going to add the price the cut pace is the addition of the weights。



![](img/d4f093f8b9b1f27a541ad09c4f380121_69.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_70.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_71.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_72.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_73.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_74.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_75.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_76.png)

Offf the edges， it's cutting through。 So it's going to try to cut through weak edges in that。

 and in that way， it's going to separate the forground from the background。



![](img/d4f093f8b9b1f27a541ad09c4f380121_78.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_79.png)

Now， there are good techniques to do that and that can achieve this in polynomial times。

 So there are very efficient ways to solve this mean cut problem。 And by that。

 we got the separation between the foreground and the background。

 This technique can be actually extended to multiple objects in the image。

 not just foreground and background and other type of input data。

 but it's easier to illustrate when we think about just one source and one sink。

 meaning foreground and background separate。 So two steps， basically， one is construct the graph。

 Second step， produce the mean cut。 This second step。



![](img/d4f093f8b9b1f27a541ad09c4f380121_81.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_82.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_83.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_84.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_85.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_86.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_87.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_88.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_89.png)

Basically， very good algorithms in graph theory the first step of constructing the graph is where the image processing information comes into the graph。



![](img/d4f093f8b9b1f27a541ad09c4f380121_91.png)

![](img/d4f093f8b9b1f27a541ad09c4f380121_92.png)

Lets just illustrate a few examples。

![](img/d4f093f8b9b1f27a541ad09c4f380121_94.png)

So here we see examples where basically in the examples I'm showing their borrowrow。

 as I say at the very beginning from the crab cut technique that provides kind of a scribble in the background and here we see the segmentation。

A second example here and a third example here， and once again， this can be run very， very fast。

 and here I'm going to illustrate a very nice example and application of this。

 So we go into one picture of this trip and segment it out。And put it。In the large picture。

 And then you do the same。For the next one。Segment it out using the technique I just explained and go and put it in the picture。

 and then you repeat it。For the other ones。And you end up having a new image that is basically a composite of multiple images through this cut and paste。

 I think it's a very nice example and a very nice application of this。

Interactive type of image segmentation in this particular case through graphcas。

 which is a particular implementation， a very smart technique related to this minimal cut or this graphcas technique。

What I want to conclude is by explaining to you that this type of technique actually is incorporated in Microsoft Office。

 So this is very modern image processing that， as we have seen in other examples。

 and we are going to see in future examples， actually right after this video this techniques get into some of the very popular pieces of software that many people use。

 Thank you very much。 See you in the next video。