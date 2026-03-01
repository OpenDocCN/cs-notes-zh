# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P22：22_03_07_7-非局部均值-时长-07-27.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

As we just saw local averaging has some very interesting mathematical properties。

 It's a very simple operation as well， and is very useful as we saw a few examples before。

 but we have also observed that it can blur the information in the image， it can blur the ages。

So how do we solve that？ We have a number of different directions to go。

 One is to basically replace this local averaging by a different local operation。

 and we're going to see that very soon。 The other is we might ask ourselves。

 are we only limited to average in the local neighborhood。 Maybe we can do a smarter average。

 remember that averaging is like a heat flow。 So shall we basically average between a very hot pixel and a very cold pixel。

 or shall we try only to average between pixels that are similar and try to stop aver in pixels that are very different。

 and that's a very interesting concept that can actually be implementing a very very variety of ways in a very different number of directions。

 But let's just explain one which is extremely elegant In part is elegant because it's very simple。

 and it's actually called non-local means。 instead of looking at averages in the local neighborhood。

're going。Look at the averages in the whole image。 Let's see why we can do that and how we do that。

TD is very simple。 Let's us observe this image。We actually see that images have repetition。

 sometimes these are called self similarities， so for example， if we look at this local neighborhood。

 it's very similar to this local neighborhood and very similar to this local neighborhood。

We also observe that here， this local neighborhood is very similar to this local neighborhood。

 Even similar to this， they are far away， but they are very similar， the same here。

So before we were thinking about averaging only pixels inside here。

 maybe we should actually average neighborhoods that are similar。

 maybe we should average these three so we can replace these pixel by certain relationship with others。

 but we should not mix these with these because the local neighborhoods are very different。

So the basic idea of non local means or non local averaging is to try to average。

 try to enjoy the properties of averaging but not restrict that to a local neighborhood so why are we doing that and how are we doing that？

So， the basic idea is that。If we assume that these are identical things， identical structures。

 but maybe with different noise， let's see the effects of that。

 Let's assume that we have a certain pixel。 Let's call it P。 That's what we observe。

Is the clean pixel。Plus， some noise。But the noise basically is a random variable。

 so it's always slightly different。 So we observe the pixel a number of times。

 we observe one with a certain noise。We observe it again。Sme pixel。But with3 different noise。

And we can observe it multiple times。 Let's say that we observe this n times。Always the same pixel。

 but with different realizations of the noise。If we average all these。

 we can easily show these are basic properties of signal analysis that the noise goes down proportional to the square of the number of times that we average。

 so we are averaging always the same pixel。 the noise is the random variable。

 and basically the noise goes down proportional to n square。

 the more we average the more we reduce noise， Of course。

 it's very important that we always average exactly the same pixel。

 the noise is the only thing that changes， So this is one of the motivations of nonlocal means。

 to say， okay， maybe I can find repeated structures that are identical or at least very similar。

 the noise is different all around and I can reduce that noise by averaging。Just because of this。

 and the basic idea， then， is to look for similar neighborhoods first。And average them。

 So if I want to replace this pixel。In the center here， I look at the neighborhood。

 I look for similar neighborhoods， and I replace the pixel by the center。

 By the average of the center of the similar neighborhoods。And how do I find similar neighborhoods。

 So there is a whole literature on non localal means that basically includes two parts。

 How do I find similar neighborhoods， That's the first part。 Once I found them。

 How do I average them， Do I weighted average them。

 do I compute a different relationship between them。 But once again。

 the simplest for both options is。Look for neighborhoods by comparing， let's say。

 the mean square error between them and make sure that is very small。That's a very。

 very simple operation。 You go around the image， you look at neighborhoods。

 let's say 3 by3 or5 by5 or7 by 7。And you say， okay， who is similar to this， you go over around。

 you find a set of them， you can include all of them。 you can include just the most similar ones。

Once you find them， you go into the center of every neighborhood and let's say you average that and you replace the pixel by the average。

Then， if you want to actually。Clean a pixel that is here。

 you look for similar pixel similar neighborhoods to what's surrounding that pixel。

 you go around the image， you find a few and you replace this pixel by the average of the centers of all the similar neighborhoods。

 Once again， this is just one example， you could look for similar neighborhoods in a different fashion。

 you could actually once you find them instead of doing average do weighted average or do other functions。

 but the concept is always the same。Instead of just averaging instead of averaging around the neighborhood to replace this pixel。

 we basically look all around the image for similar neighborhoods with some measure of similarity and once we find them。

 we combine them and in such a way we dennoice the pixel based on the concept I just explained this is an extremely similar operation once again。

 basically in one or two common lines in MAla， for example。

 you can actually perform this operation and extremely extremely powerful and has opened a lot of research。

 very modern research in image processing basically in the last couple of years。

What we are going to do next is I'm going to actually run some of these examples on real images。

 I'm going to be doing this on real time。 So see you in the next video for that。

