# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P19：19_03_04_4-直方图匹配-时长-08-31.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Let us now present a very simple extension of istogram Qization， which is called isstogram matching。

 So let's just illustrate the problem。

![](img/8a1e92a04d19604469431e8828ed9813_1.png)

We saw before ist equalization where we take any Instagramt any pixel distribution and we match it to something which is as uniform as possible。

 But imagine that we have this pixel distribution， which is the one we have seen before。

 and somebody comes and tells us this is your target。 I don't want to do an equalization。

 I want you to finish with an Instagram which is as close as possible to this one。

So the idea is as before， were going to have to find a map。Which is written here。 This is the map。

That we have been doing before。A map such that from here from this distribution。

 we can go to as close as possible to this one in this case。

In the way that I'm going to describe in a second， what we are going to obtain is this。

 which is very similar， not exactly， but very， very similar。

 we already saw in the previous video that we cannot always get exactly the specify Instagram in the previous video was equalized but we can get very close to it。

 And this is what we see here。 So how do we do that， You already have all the tools to do that。

 Let me illustrate how。We start from。The distribution of the current image。

Whatever that distribution is， it's the image that is given to you。

You know how to map that to a uniform distribution。Okay。😊，Now， you are giving。A desire distribution。

You know how to map this desired distribution， the target distribution。Also。

To a uniform distribution。Therefore， if you know how to go from here to here and from here to here。

 if you invert this。You know how to go。All the path。 that is the desired path。

 So you're going to map a pixel value from here to here。 Then you're going to ask， okay。

 where is this pixel coming from， This pixel value coming from when I want to go here。

 and you just invert that So you basically have one map another map。

 and you just invert that second map。 So let's say that pixel value number。

 a pixel with a gray value 7 goes to 10 here。Then you ask， okay。

 who from here what pixel value went to 10 and somebody， you know this map tells you 15。

 So you end up going from 7 to 10。 and inverse of 10 is 15。 So you went from 7 to 15。

 And that's how you basically get an Instagram matching。 just by doing Instagram equalization。

 now you know how to match any two desire distributions。

 There is one caveat as we saw in the previous video， the maps don't have to be one to 1。

 So maybe there is more than one pixel value here that ends up at the same pixel value there。

 So when you go from 7， let's say to。10。Maybe there is 15 from here， goes to 10。And maybe also 20。

Goes to 10， so。Am I going to map 7 to 15， or I'm going to map 7 to 20。

 You're going to have to make a decision。 The most common decision is to pick the one that is closest to the original。

 So you do the less deformation of the pixel values of the image。

 But you can make other decisions as long as those decisions are consistent。

 And as long as those decisions guarantee that you end up with an increasing in function。

 Remember that we don't want to flip pixel values。 So once again， you do two istogram qualifications。

 You invert one of them。 And then you basically obtain isstogram matching。

 So let's see how that works。

![](img/8a1e92a04d19604469431e8828ed9813_3.png)

This is a particular example。 We have a very dark image here， and we see that in the Instagram。

 mostly dark values are used。 so it's hard for us to see what's going on here because it's very。

 very dark。If we do inst equalization， we get a two bright image。 as we see here。

 This is actually the mapping， the Tr mapping that we always are looking for。

 And this is going to be the new Instagram， And we see both from the Instagram and from the actual image that is way too bright。

 So we haven't achieved what we really wanted， which is a nicer looking image that we can actually observe the different regions of that image。

😊。

![](img/8a1e92a04d19604469431e8828ed9813_5.png)

![](img/8a1e92a04d19604469431e8828ed9813_6.png)

If instead of that， we do hist matching。 So somebody comes and tells us。

 I know that this is the distribution that is going to be great for my image。 Then what we do is。

 again， we go from the original。Dbut to equalization， we go from this distribution。

The new distribution here， we go to equalization， which is going to be this map。We invert that map。

 which is going to be this。And then we go in two steps from the original isstogram to the equalize one。

 from the equalize one through the inverse map to the new pixel value。

 and we get this distribution which gives us this image which looks much nicer than this one and it also help us to look at some of its details so we basically got istogram matching by doing twice istogram equalization once direct and the other we has inverted and again if we have ambiguities which is make a decision by using。

 for example， the pixel value closests to the one that we started in the original image so you got two for the price of one。

 if you know how to do isstogram equalization you know how to do istogram matching。Of course。

 there is a big art in designing your target Instagram， and that's very application dependent。

 Let's just mention one last thing about ist equalization or is matching。So far。

 we consider the whole image and we say let's just look at the whole image。

 Let's look at the distribution and let's match those pixel distributions to a new distribution。

 either an equalization or a specified distribution。 you can do the same operations locally。 So。

 for example， if we take this and we do iss global istogram equalization， we are going to get this。

Sometimes it looks a bit better， but there is a compromise。

 I only have 256 pixel values to distribute for my whole image。

 So I might not be able to do a very strong contrast at the same time here and here。

 So the way to solve this is to basically consider regions and say。Let's just do ist equalization。

 for example， of this region。And let's do isst Qization。Of this region。

 they can actually be overlapping， and we are going to treat each region independently。

 And maybe by doing that， I can basically improve the contrast in every region in the image when there is a large variability。

 like in this particular image。 This is a result of that。 And I want you， for example。

 to concentrate on this region。How it's very hard to see the details here。

They don't look much better here， but they do look much better here。Now， in this region。

 there is not a lot of details。The global did manage to do a good job， but not in this region。

 Global istogram equalization or global istogram matching is a compromise between everything that we see in the image。

 We can try to overcome at least partially that compromise by doing this local operation。

 and now we see that you can get details here。 We can also get details here。

 So in the different regions of the image， they have very different pixel values。

 and we can still do basically a istogram stretching and get much better contrast in the different regions。



![](img/8a1e92a04d19604469431e8828ed9813_8.png)

By this， we basically conclude our unit， our portion on Instagram equalization and Instagram matching。

 a very simple operation and very useful。 See you in the next video。 Thank you。



![](img/8a1e92a04d19604469431e8828ed9813_10.png)