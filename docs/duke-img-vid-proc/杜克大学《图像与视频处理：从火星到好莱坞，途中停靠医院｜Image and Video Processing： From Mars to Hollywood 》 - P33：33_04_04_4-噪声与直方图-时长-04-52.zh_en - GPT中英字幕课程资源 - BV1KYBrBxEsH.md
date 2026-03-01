# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P33：33_04_04_4-噪声与直方图-时长-04-52.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Now that we are experts on noise。 Let's see what happens to the histogram of an image when we add noise to it for that。

 we are going to use a very simple example。 We see here an image that has only three regions and then only three values。

 So if we were to draw the histogram of this image， we will see a different heights。

 But we actually see only three basically deta functions， one that stands for the black region。



![](img/211f4511a348e99eff4590bd407d8dfb_1.png)

One that stands for the gray region and one that stands for this lighter region。

 and the height of this depends on the area of each one of the regions。

 So when we add noise with each one of this distribution， How is this isagon going change。

 It's going to change from this three delta function to something。 And let's see what happens。



![](img/211f4511a348e99eff4590bd407d8dfb_3.png)

So here we see three examples already。In the first example。

 we took the original image and we added Gaussian noise。

This is the type of probability distribution of the noise， and we actually see it reflected here。

It's very clearly there are kind of three Gaussian distributions。 This is going to be very important。

 It's going to help us to estimate the noise if we're only given the image。

 as we are going to see in an next video。Here we see a shape which is very similar to the shape of the railing noise。

It's kind of tilted， and then it goes down。Almost like a Gaussian， slightly different。 So clearly。

 the shapes here are very different。 For example， this is kind of symmetric。 This is not。 Remember。

 these are probability distribution functions for the noise。

 So we are not expecting to see a perfect function。 This is all in probability。

 And here we see the gamma noise。 Once again， a shape very similar around each one of the pixel values。

 a shape that is very similar to the actual probability distribution function。

 So these are the three of them。 They just continue seeing some additional examples。

I'm going to ask you now question。Which noise do you think we added here to the original image。

 So this is how the basic image looks after we add a noise。 Which one of these6。

You think we have added here。 Please give me an answer to that。

I think it's not very hard to get to the answer if we just compare the shapes。 once again， remember。

If we only had the original image， we had kind of。3 delta functions with different heights representing the black。

 the gray and the white regions。 And now we see very clearly exponential functions。

 So it was this noise。Okay， we cannot not see that from the image itself。

 It's very hard to see is this Gaussian is this exponential， is Israeli。

 You have to really be trained to observe than just from the image。

 but it's much easier from the Instagram。 So now that we are really experts。

 I'm going to ask you again， what's the noise here。Please give me an answer。

 Just think for a second and give me an answer。Once again， this was the original histogram。

 and now we actually see kind of uniform distributions， So we see clearly that this is the noise。

 It's basically around the area of the original histogram we see flat regions。

 So this is the type of noise。 Now， please note that in this image。

 the same type of noise was added all around the image。Otherwise， for example。

 if we add gaussian noise。Inside this region and uniform noise to everything else。

 we will see actually a Gaussian here and uniform in the other two。

 So we will see combinations of these distributions。 Finally， this is the salt and pepper。

 salt and pepper actually is not hard in general to recognize from the original image。

 We see the black dots or the Y dots。 But I also want to illustrate that in the histogram。

 the histogram stays with kind of delta functions。 But of course， if there was no black。

 then we be a new delta function at black， Or if there was black。

 it will be a larger and basically a taller delta function there and the same for white。

 So we can see from the histograms， what actually happens。 Sometimes， and therefore。

 we can use the histograms to estimate the type of noise and to estimate the parameters of the noise as we're gonna see in the next video。

 Thank you。