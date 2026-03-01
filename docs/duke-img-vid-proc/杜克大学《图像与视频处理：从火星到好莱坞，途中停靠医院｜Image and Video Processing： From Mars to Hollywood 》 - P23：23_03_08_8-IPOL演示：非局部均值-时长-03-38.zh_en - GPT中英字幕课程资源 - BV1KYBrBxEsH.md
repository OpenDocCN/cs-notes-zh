# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P23：23_03_08_8-IPOL演示：非局部均值-时长-03-38.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。 Now that we know the underlying framework of non local meanss。

 Let's just demo it in real time。 No local meanss denoing works using the resources in the image processing online journal。

 This is a website that I have provided a link in the web page for this class。

 is a journal that has a lot of online algorithms for image processing。

And I strongly suggest that you visit it if you want to play with a lot of the state of the art in image processing。

 so the journal has first the full description of the algorithm。

 it has also code that you can download and use in your own computer。

 but also has an online demo and that's what we are going to do next。You can upload your own images。

 or you can basically use images already available on the website just to illustrate and to help you understand the algorithm better。

 So let's just pick this image， for example。And it's here。 and we're going to run the algorithm。

 we' are going to add some noise to the image。To see how。No local means will dennoice that。

 And we are going to ask it to run。 So now it's running。 We see this。

 This algorithm can be made run very fast， but now is's running on the server and is's running on an implementation that is not optimize for that。

 But here we have the result。 So we see let's just illustrate the details。

 We see here is thenoisy image。 Basically the original image with the added noise。

 And now we see the denno image。Again， this is the noise image。 This is the denno image。

 and this is the original。 So we see that there are differences。

 but certainly the deno image is much better than the noisy image。

 and we can actually see the difference between the denno image and the original image。 Once again。

 this is the noise image。 the deno image， the original image。And the difference， they just。

Run with a different image。 So let's just select a new input here and we can pick a different image。

 for example， these dies。

![](img/010afde6322764a65e21250a79dc7d8a_1.png)

And we can pick a different level of noise。 and just put a lot of noise to see what happens here。

 and let just run it。

![](img/010afde6322764a65e21250a79dc7d8a_3.png)

Once again， while this is running， remember， the goal of inloc means is to look for regions， say。

 okay， if I want to denno this region， I'm going to look for similar regions around and average them。

 The larger the noise。 the more the algorithm will take because it's going to try to average more and more patches to help us reduce the noise if the noise even further。

 So here is， again， the noise image the algorithm has finished。



![](img/010afde6322764a65e21250a79dc7d8a_5.png)

![](img/010afde6322764a65e21250a79dc7d8a_6.png)

This is a noisy， This is a denoisy image。This is original。And this is the difference。

 So we think it has done a very， very good job。In denoing this image。Noisy denois。Noisy。 the noise。

Original image。And the difference， this image doesn't have a lot of texture。

 And that's why these type of algorithms work really， really well。 when there is a lot of texture。

 the algorithm still works very well。 But for every deno image， denoing algorithm。



![](img/010afde6322764a65e21250a79dc7d8a_8.png)

Dealing with texture is a bit more difficult。So let's just conclude this by showing this once again。

 noisy， deno， original and difference。 And once again。

 you can just go into the ipo dot I website and play with this or any other algorithm that is available there。

 And you can upload your own images and see how it works。 Thank you and see in the next video。

