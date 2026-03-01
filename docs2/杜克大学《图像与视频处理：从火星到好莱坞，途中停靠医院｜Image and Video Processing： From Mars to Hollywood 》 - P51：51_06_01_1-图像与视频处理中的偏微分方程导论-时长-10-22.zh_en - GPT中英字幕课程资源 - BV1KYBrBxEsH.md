# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P51：51_06_01_1-图像与视频处理中的偏微分方程导论-时长-10-22.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello， it's great to have you back。 This is week 6。 and the topic of this week is。😊。

Partial differential equations。In image processing， some of you might remember。

 Some of you might know what partial differential equations are。

 Some of you might not remember when you stated that maybe a long time ago。

 maybe just a few years ago。 But don't worry， as every other week。

 this is going to be a very self contained week。 Before I give you a bit more of details about what we are going to learn this week。

 Let me try to explain to you what do we mean by partial differential equations。

 What is kind of this new area。Relatively new area in image processing。

 but certainly new for us in this class。 So far， we have been considering images as discrete objects in the computer。

 If we look， for example， at the steel image。 We already talk it looks continuous to us。

 that actually is a collection of pixels。 So its a discrete two dimensionmensal array of pixels。

 as we have represented here， now they are so close to each other。 we already talk about resolution。

 they are so close to each other， that it looks like a continuous image， But actually。

 it is a discrete object is representing the computer as a discrete object。

 The same happened with movies。😊，We already know that movies are discrete objects。

 The look continues to us like this movie that we are watching here because the sampling in time is basically very fast。

 And that's why our perception。😊，Perceives this as a continuous object。

 But we already know that this is a discrete object，30 frames per second，24 frames per second。

 So images and videos are discrete， both in space。In time and also at the grade levels。

 the look continues to us but they're discrete objects。

 Now that leads us to what we have been doing most of these five previous weeks using tools from discrete representations from discrete mathematics because we have discrete objects in the computer。

So what's different when we start talking about partial differential equations？

What's different is that we' are going to start considering continuous objects。

 So when we consider discrete objects， the way images and videos are represented in the computers。

 we see， for example sums。 we never saw the sign of an integral， we always talk about sums。

 we talk about discrete operations。 Also every time we saw kind of a continuous object a derivative。

 which is a tool from calculus， it's a continuous object， then we immediately discretize it。

 remember we talk about， for example， it derivative。Divative in the direction and we say okay。

 let's do plus1 a minus1 here， so immediately we redefine its discrete counterpart because we want to be in discrete world。

 we want to be in a discrete space。The area of partial differential equations says。

 forget about that。 The area of partial differential equations has a completely different approach and says images are continuous objects。



![](img/dc4507291c86ddfc7ee9570489786d3f_1.png)

Don't treat them as discrete objects anymore， that just an artifact of computer representations。

 treat them as continuous objects。

![](img/dc4507291c86ddfc7ee9570489786d3f_3.png)

And then you basically are going to be talking about image processing as iterations of infinitesimal operators。

 things that happen a very， very small scale， we iterate them and when we are itating them actually we get this partial differential equations that once again if you don't remember exactly what they are。

 we're going to explain that in the next video， don't worry about that the key concept is here。

Images are not discrete objects。 Images are continuous。

 so go and develop all your algorithms like you're in continuous domain。

Treat images as continuous objects and then you can do partial differential equations。

 you can also differential geometry tools that are from continuous mathematics。

 all of a sudden they're valid， they are powerful for basically discrete image processing。

 but then you ask yourself Wait a second you develop them。

 but my images are still discrete objects in my computer but here comes to the rescue numerical analysis。

 numerical analysis is exactly the area that says how do I implement continuous algorithms。

 how do I implement continuous mathematics in discrete domains like a computer so you go and develop algorithms with tools of continuous mathematics and then numerical analysis comes to the rescue once we need to implement。

Those algorithms in the computer。 So it's kind of a different paradigm。 It's not better。

 it's not worse， It's different than the paradigm that we were used to before when we consider images from the very beginning as discrete objects now。



![](img/dc4507291c86ddfc7ee9570489786d3f_5.png)

Why。😡，Why is this happening now？What's going on， why do we move from this from this completely discrete that basically if we look historically has mostly dominated image and video processing for years and years until basically about 10 years ago and of course there are a number of reasons why these continuous tools appear in image processing。

 once is computers became more powerful and then numerical algorithms to implement this continuous math that were impossible to have in a computer became actually doable in even small and personal computers。

 Of course every new tools can because some people move into the area and we should never forget about the influence of people so a lot of people in the last 10 years or so that were interested in continuous mathematics also became interested in image processing。

And they brought their tools， their expertise into image processing。 Now were going to see， as I say。

 we're going to see examples I'm going to provide you the background。 but why is it bringing to us。

 It's going to bring a number of things， It brings new concepts。It brings accuracy。

 this is a very important thing because we are in continuous domain and then we implement by numerical algorithms。

 the accuracy will depend on the implementation not on the design of the algorithm。

 the algorithm is design in the continuous domain， so there is no intrinsic accuracy。

 depending how much I'm willing to invest。Computational resources， for example。

 in the implementation that will determine the actual accuracy of the algorithm。

 It's not intrinsic to the algorithm。 When I define a derivative。As plus minus plus 1，-1， I'm done。

 I have defined the accuracy of my algorithm。 Now， if I define in the continuous domain and then say。

Do the derivative the best you can。 I leave the door open to very high accuracy techniques。

Another thing that was brought that we are not going to discuss a lot in this class and certainly not in this week is very formal analysis。

 A lot of the techniques that came from the area of partial differential equations。

 to image processing have very formal analysis， you can prove theorems。

 you can prove that while you're doing is right， even before you're going and。

Implementing the algorithm。 So it's one of the most mathematical areas in image and video processing。

 I'm not saying it's the only one， but it's one of the most mathematical areas。



![](img/dc4507291c86ddfc7ee9570489786d3f_7.png)

And the consequences of this is that partial differential equation tools brought a lot of state of the algorithms。

 but I think one of the most important things and I want to leave you before we go into details with this。

Take home message is that there are new tools and new books in the bookshelf。

 so when you bring a new theory into an area， you say， okay。

 all these new frameworks are now allowed。And it's always good to have more tools to solve real problems as we are going to see during this week and a bit next week。

 So what we're going to do this week is I'm going to give you the tools to understand the underlying and the simplest possible tools to understand the area of partial differential equations in image processing we're going to filter in examples that is going to show you to understand remember last week we discuss active contours that's one example of the use of partial differential equations in image processing as we' are going to see very soon in one of the future videos and we're also going to talk next week about imaging painting and some of the algorithms we are going to describe there are based on partial differential equations As I said is one of the most mathematical areas that we are going to discuss during these nine weeks of classes in image and video processing but there's nothing to worry because I'm going to introduce you to the basic。

Concepts and the basic tools that you need to understand。

The fundamental concepts behind this area of partial differential equations in image processing。

 and we're going to start learning about those concepts right in the next video。 Thank you。



![](img/dc4507291c86ddfc7ee9570489786d3f_9.png)