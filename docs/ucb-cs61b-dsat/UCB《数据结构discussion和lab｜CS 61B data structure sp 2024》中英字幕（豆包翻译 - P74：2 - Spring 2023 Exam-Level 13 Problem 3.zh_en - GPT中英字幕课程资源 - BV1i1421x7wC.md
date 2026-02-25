# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P74：2 - Spring 2023 Exam-Level 13 Problem 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

That's what makes you good。Everyone， this is the CS 61 B fall 2022 exam preptel walkthrough and I'm Sherry in this part I'll be going over question three bears and beds。

Just like I said in the previous videos I'm a little bit sick this week so I might start coughing please bear with me and sorry if it's annoying as an overview oh yeah so let's just move into the problem and as an overview the goal we're trying to accomplish here is basically we want to match a couple bears to a couple beds and specifically we want to make sure that the relative ordering of our bears and beds is the same。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_1.png)

And one constraint that we're given in the problem is that it has to run an O of n log n on average。

And just for an example of what we're trying to do。

 lets at let's look at this example here for reference this throughout this problem。

 I'm going to refer to bears with a capital B and beds with a lowercase B just so we can distinguish them a little bit easier so for example。

 if you have this setup here we have bears A BC D and beds A BC D and each of them has like a specific size that doesn't really mean anything other than the ordering that they should be in so in this setup I want to pair bear A with bed C because they have the same size bear B with bed A bear C with bed B and bear D with bed B。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_3.png)

![](img/8fd3fdc57047824aa07b0609ec7c85e8_4.png)

![](img/8fd3fdc57047824aa07b0609ec7c85e8_5.png)

One immediate hint that we should notice is that the algorithm should run an O of n log n on average and the sort that we know that runs an O of n log n on average is Quick sort。

 so this tells us that we should probably just be running like a small modification on Quick sort。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_7.png)

![](img/8fd3fdc57047824aa07b0609ec7c85e8_8.png)

As a note， we can't just like sort the bears and sort the beds and then match them up because we're not allowed to compare beds to each other or bears to each other。

 so we can't just compare items to each other so we can't really sort the two arrays except by comparing bears to beds or beds to bears。

So let's see an example of how this will work。

![](img/8fd3fdc57047824aa07b0609ec7c85e8_10.png)

The general idea is that we're going to use the bears array to kind of pivot the beds array and then we're going to pick a pivot in the beds array to pivot the bears array。

 so we're kind of using the arrays to pivot each other and do the quick sort around instead of comparing the items directly to each other。

This might sound a little bit vague， so let's actually go through a physical example just on the four bears and beds that I've shown here。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_12.png)

So we're going to have five substance algorithm， the first step is we're going to choose a random pivot bear。

 so let's just say for the sake of argument that we picked bear B， it could be any other bear。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_14.png)

And we're going to use this bear bear be to pivot the beds array around the bear。

 So we're going to pivot the beds into beds that are less than bear be。

 the bed that is equal to bear be and the beds that are larger than B。 So， for example。

 using this array above， we can see that bear。

![](img/8fd3fdc57047824aa07b0609ec7c85e8_16.png)

![](img/8fd3fdc57047824aa07b0609ec7c85e8_17.png)

A is equal to bear， sorry B A is equal to bear B， and then beds B and D are less than B and B C is greater than bear B。

 So we're going to partition our range to three parts。 the ones are less than bear B。

 the ones are equal to bear B and the ones are greater than bear B。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_19.png)

![](img/8fd3fdc57047824aa07b0609ec7c85e8_20.png)

And now we know which pivot in the bed array corresponds to our bear。

 because remember each bear has a corresponding bed。

 so we can kind of say that these are two equal pivots。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_22.png)

So we're going to take the equal pivot bed A， and then we're going to kind of do the reverse of what we just did。

 We're going to use this pivot。To basically split our bears array into the correct parts。😡。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_24.png)

So using bed A， we're going to compare it to every bear in the bear array。

 and then we're going to pivot around bed A。

![](img/8fd3fdc57047824aa07b0609ec7c85e8_26.png)

![](img/8fd3fdc57047824aa07b0609ec7c85e8_27.png)

So we're going to end up with Bears B and C， which are less than bear A。Var B。

 which is equal to bed a and ver a， which is greater than ver a bed a。 So if we look at this。

 just to remind you of what the numbers are， we're going to have the ones that are smaller。

 which are these two。

![](img/8fd3fdc57047824aa07b0609ec7c85e8_29.png)

The ones that are equal， which is this one and the one that is greater， which is this one。

 And so that corresponds to our pivoted array down here。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_31.png)

And then we're going to recurse on each half of the array。

 so all the ones that are less than our pivots。

![](img/8fd3fdc57047824aa07b0609ec7c85e8_33.png)

We're going to recurse and just run the same algorithm again and same for all the ones that are greater。

 we're going to reurse and we're going to run it again。 So if remember for Quick sort。

 we also do something similar， we split it into less。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_35.png)

![](img/8fd3fdc57047824aa07b0609ec7c85e8_36.png)

Equal。Greater。😊，And then we recurse on less。And greater。 So that's exactly what we're doing here。

 except we're using the bears to pivot the beds and then we're using the beds to pivot the bears。

 So to analyze this， we're basically doing quick sort except we're doing it on kind of two arrays at once。

 So this is still going be O of n log n on average because it's just the runtime of quick sort。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_38.png)

![](img/8fd3fdc57047824aa07b0609ec7c85e8_39.png)

![](img/8fd3fdc57047824aa07b0609ec7c85e8_40.png)

That's it for this problem and my tip for sorting algorithm design questions is that usually the runtime is a really good indicator of what you need to do so for example in this problem we saw that it was O of n log n on average which is a huge hint that we use Quick sort this is something that you comply to basically any algorithm design question so keep an out for that and good luck in the rest of 61b。



![](img/8fd3fdc57047824aa07b0609ec7c85e8_42.png)

![](img/8fd3fdc57047824aa07b0609ec7c85e8_43.png)