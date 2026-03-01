# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P20：20_03_05_5-局部邻域操作导论-时长-06-46.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

When we were talking about istogram modification， either equalization or matching。

 we were replacing the gray value of a pixel only based on its actual gray value。

 and we weren't looking at the surrounding area of the image What we're going to do next is we're going to do spatial operations So we're going to basically replace the pixel value at a given pixel depending on what's happening around the pixel。

 So there's going to be influence of the neighborhood。 So if we have a complete image。

 we're going to look at a pixel and we see here magnifications of that， or let's just observe here。

 we're going to decide what to replace the pixel value here with depending on what's happening around it。

 So it's not going to be any more just okay， I decide how am I going to change depending on my own pixel value。

 we're going to decide how this pixel is going to change depending on neighborhood pixels。



![](img/6ff7e3d36e489cf8b0352276ce3eb10a_1.png)

And the simplest of those operations is basically averaging。

 So we are going to replace the pixel here by the average of， let's say。

 a three by three neighborhood around it。Of course， we have to normalize。

 So if we are averaging nine pixels， we have to divide by9。 We can also do weighted averages。

 so we can average in the sense that yourself， the pixel itself， weights 4。

 and those that are in four neighborhood。 Remember we talk about4 and 8 neighborhood structures。

 those that are in four， will count double and those that are in theagonal， which is count single。

 and then we basically align in 16 things1 plus2 3 plus one is 4 plus2 is6 and so on。

 So we will have to normalize by 16。 So this is just an average。 This is a weighted average。

 Let's see the effects of this。 in a real image。

![](img/6ff7e3d36e489cf8b0352276ce3eb10a_3.png)

What we have here is an image and this is a good image because it has structures of different sizes and what we are going to see for each one of these other images is the local average and we take neighborhoods of different sizes we go from3 to 13 so this is 35。

9，15 and 35 so we go from 3 to 35。The the larger the neighborhood。

 the more pixels we are averaging and we see the effect of that here。 When we average by3。

 we don't see much of a change。 There is some change here， in the fine structure。

 But let's just jump to the 35。 So this is a window of 35， a neighborhood of 35。

 And we see that a lot of things get blur， And I'm going to explain a second。

 why give you the intuition behind that。 So a lot of the structure gets blurd。

 If we are using a neighborhood of only 15， Le things get blur。 We see that here， for example。

 this is much easier to distinguish the bars here than it is here。

 And that depends on the distance between the objects。 So why are we getting blur because here。

 for example， this point。Imagine that we have a 35 by 35 window around it。

 so we end up averaging the black of the pixel。With the gray around it。

 And then it gets a bit brighter。 So this was very dark， black。 This is bright。

 And if we are averaging pixels around it， the average basically goes up for this pixel。

 And when we are averaging here， because some of the pixels in the neighbor in the neighborhood are dark。

 the average here。 We basically go down。 And then we are clear in this blurring effect。

 Let me just illustrate with that one dimensional function。If I'm basically averaging this。With this。

And this， clearly， the pixel value of this goes down because of the effect of this。

 So this will be replaced by something。Around here。This one。

If I'm averaging with this one and maybe with a pixel here， then it goes slightly up。

And then this perfectly sharp profile becomes a bit of a smooth。

Profied because I'm averaging things on the side。 We're going to see later towards the second part of this course how to basically average without creating this blurring effect。

 But this is just to illustrate a very simple operation。

 which is local averaging and how neighbors and basically the size of the neighbors affect what's happening on the pixel。

 Now， you might wonder， is this operation important。 Yes， it is。

 although it's going to blur the basic ideas that we are not going to average with a window size of 35。

 We need to design window sizes that are appropriate for the particular problem。 For example。

 if we have this image and we want to get rid of some of the very small objects in the image。

 maybe their noise or maybe their basically stars or particles that we don't care about them too much。

 then we can do a local filter。Of this image， in this case， it was used a 15 by 15 image。

 We're blaring the image， but we're somehow getting rid of these small particles。

 So a small particle here will be basically average with a lot of black pixels around it。

 And then its value will go so much down so much close to0， then when I threshold。

 I get basically only the regions of interest， the larger and the very bright regions。

 So we first blur and then we threshold， and we got rid of all these。

 which we consider noise and we only get the really important objects in the scene。

 So this very simple operation is very powerful for tasks like this。 More interesting。

 This very simple averaging operation has really interesting mathematical properties that I'm going to explain next。

 and those are important because they're going to help us to develop。



![](img/6ff7e3d36e489cf8b0352276ce3eb10a_5.png)

Other type of averaging operations that， for example， do not blur edges。

 And we're going to do that explanation of the mathematical properties and relationships that this simple averaging has with other structures in an next video。

 Thank you。

![](img/6ff7e3d36e489cf8b0352276ce3eb10a_7.png)