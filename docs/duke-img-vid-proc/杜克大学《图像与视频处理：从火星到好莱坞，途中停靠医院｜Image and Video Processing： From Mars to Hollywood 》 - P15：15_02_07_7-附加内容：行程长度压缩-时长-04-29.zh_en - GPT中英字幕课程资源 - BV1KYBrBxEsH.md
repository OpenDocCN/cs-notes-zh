# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P15：15_02_07_7-附加内容：行程长度压缩-时长-04-29.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Let us now complete the week on image and video compression by just a very brief description of rank length coding rank length coding is very useful for normally when we when encode binary images。

 So let's just draw a binary image。

![](img/1b96848400d120a365e2f3fbb7842122_1.png)

And then will help us to illustrate that。 Lets assume we have an object here。 that has a certain。

Great value。And we only have two gray values。 Let's say，100 in the background。嗯。200 here。Okay。

 so we already have seen that we， if we do a smart representation of our image。

 we're going to be able to compress a lot。 A smart representation means let's give to half encoding very nice distributions。

 very simple things。 and hopefully less than we will get by encoding the whole image。 So of course。

 we could encode this image by saying many times 100 for the first row。

 Sam for the second row and so on and so on。 And imagine that this is， you know。



![](img/1b96848400d120a365e2f3fbb7842122_3.png)

听首声。By 10000 image。So we're going to say 10，000 times 100， and we keep going。

A smarter way is basically to do the following。To say， okay。

 let's just count how many times there is the value of 100。

Let's discount how many times there is the value 200 and let's count then after that。

 how many times there is again the value 100 Basically discount we don't have to do if we know that there is only one transition。

So we count this。 And let's say that there is basically 3000 times。3000 times。The value 100。

 So instead of encoding 3000 times100， we encode this value。

And then let's assume that there is a thousand times。Again， the value 200。 So we。P。3000。

Then we put 1000， and we're done。 If we assume that there was only one object， one transition。

 If not， we can keep going。 So by two numbers， we have encoded the whole row。

 And then we go to the next one and we do the same。

 And this is called rang length coding because ebaia encode the run of equal numbers。

 we actually indirectly have seen that in JpeEC already when we were in the transform domain。Of Jbeg。

And a by 8。I'm just drawing a part of this， and I say to you。

 I explained to you that when everything becomes0， there is a code that says end of block。

 that's basically encoding by basically one number， everything that is going to happen to the end。

 and that's a basic idea of rank length coding again。

 very useful for images in particular for basically geometric images。

Binary images and indirectly was used Jpe， but is very popular here。

 And even if we have more than one object。And another object here， we basically encode the runs。

 we say how many times there is 100， how many times 200， how many times again， 100。

 how many times again，200 or any other value if needed。

 we encode the value and how many times it appears。 and with that。

 we basically compress a lot these very， very simple images that otherwise will take us at very。

 very long codes to represent。 And as before we could just encode these numbers as they are。

 we could plug them in into halfmancoding and basically compress them even further。



![](img/1b96848400d120a365e2f3fbb7842122_5.png)

![](img/1b96848400d120a365e2f3fbb7842122_6.png)

With this， we basically complete the week on image and video compression， and now we have images。

 now we can receive images from every place we can compress。 We can store next week。

 We're gonna start to process them。 And what happens when basically。

 our images are not us they don't look as nice as I wanted them to look。

 So that's what starts next week。 See you next week。 Thank you。😊。



![](img/1b96848400d120a365e2f3fbb7842122_8.png)

![](img/1b96848400d120a365e2f3fbb7842122_9.png)