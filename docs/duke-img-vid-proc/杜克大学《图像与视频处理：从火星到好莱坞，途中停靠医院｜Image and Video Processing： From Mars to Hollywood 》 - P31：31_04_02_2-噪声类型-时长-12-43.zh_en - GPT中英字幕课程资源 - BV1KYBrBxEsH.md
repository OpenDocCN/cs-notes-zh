# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P31：31_04_02_2-噪声类型-时长-12-43.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

![](img/b1fab9d8340d100acfd91331dea1e75f_0.png)

Let us now discuss the different types of noise that we can have in an image or a video。



![](img/b1fab9d8340d100acfd91331dea1e75f_2.png)

And normally， the way we do that is we basically define what's the probability of the noise taking certain value。

 remember we're talking about adding noise to the image as we discussed in the previous video。

 So let's start with Gaussian noise。And I'm going to write down the formula for it。

 So the probability of a certain value， This is a function that you have probably seen a large number of times already is one over。

Square root of two pi。Sigma， that's basically we are getting there the standard deviation of the noise。

The exponent of minuss。C， minus。The average。We see it here， the average of the noise。Square。

 that's very important， divided by two sigma square the variance of the noise。

 So this is the formula for Gaussian noise， and we see its function here。

Now you might ask yourself are there any real systems then let's say when I take an image。

 what I see is additive Gaussian noise and unfortunately is not actually there is not real physical systems that produce Gaussian noise。

 So why is this such an important noise。 This is probably the most use noise model in most of image and video processing systems for a couple of reasons one of them because mathematically is very easy to work with。

And we are going to see that later during these few weeks of image and video processing classes。

And also because it's a good approximation to other types of noise。

 especially when we look at small regions of the image or small regions of pixel values。

 so it's a very powerful and you're going to see most of the literature in image and video processing addressing Gaussian noise and once again here we have the mean。

 the average and here we have the variance of of the noise。 Okay， so that's Gaussian。



![](img/b1fab9d8340d100acfd91331dea1e75f_4.png)

![](img/b1fab9d8340d100acfd91331dea1e75f_5.png)

Now let's just talk about really noise in contrast with Gaussian。

 this actually doess appear in real physical systems， and lets just write a formula for it。

 it's a bit longer， but bear with me， so the probability of a certain value。

We're going to decompose it in two parts。 One is2 over B。 there is a few parameters， as we see here。

2 over B。Z， minus a。E minus。Z minus a。Square as we had for the Gaussian。Over be。Now。

 that's the value that the function assumes if the。



![](img/b1fab9d8340d100acfd91331dea1e75f_7.png)

Is greater equal than a。And it's actually 0。If C is less。Or equal picture， basically， less than。



![](img/b1fab9d8340d100acfd91331dea1e75f_9.png)

Okay， so it looks like a complicated formula。 It has this quadratic exponential the same as in the Gaussian is' multiplied by this and there is two parameters B and a and let me write down two important things before I describe you examples of the ra really noise one is the average is not hard to compute that the average this is a plus square root of pi B over4 So that's the average of the signal if we have that type of noise and。



![](img/b1fab9d8340d100acfd91331dea1e75f_11.png)

![](img/b1fab9d8340d100acfd91331dea1e75f_12.png)

![](img/b1fab9d8340d100acfd91331dea1e75f_13.png)

The variances。Of the signal， of the sigma of the signal。 I apologize is B 4 minus。5。Over 4。 Okay。

 so these are for you， just formulas and， you， simple models of the noise。 Now。

 these noise normally is used to model， for example。

 noise in certain areas of magnetic resonance imaging。

 So in contrast with the Gaussian noise that is extremely good for us to basically。

Do some math and do some nice restoration， but it's not really appearing in real physical devices。

 This is a good model for real physical devices， as I say， for example。

 a magnetic resonance is also used in underwater imaging。

 so there are many disciplines that basically the reallyli is a very。

 very good model for that for basically the noise appearing in those devices。

Let' just you have the gamma noise here， the formula， Let's just talk about the exponential noise。

In the exponential noise。 So once again， lets you start by writing the formula。



![](img/b1fab9d8340d100acfd91331dea1e75f_15.png)

The probability of Z。Of basically a certain value of the noise。Is once again。

 and this is going to be very important in a second。 E to the is a E to the minus a Z。运事。Is positive。

0irra。Wendy is negative。So basically the rail noise was nonsymmetric， but the exponential。

 basically there is no noise， Basically there is no negative values of noise。

 and that's a very important property once again。The average， not hard to compute， is one over a。

And then sigma square is one over a square， and you can have different numbers here。

 depending on your scaling。 A is just as scaling。 So this is an exponential noise。

Another popular noise， but I'm going to discuss the when can we see this exponential noise。

 actually when I describe next the uniform noise， So let me just first write the formulas for the uniform noise ask you a couple of questions about that and then explain where is that we actually see this type of noise。

 So let's just write the formula for the uniform noise。

 the uniform noise is basically saying that there is noise of exactly the same value between these two no noise outside and once you are inside all the noise has basically is uniform as as the name say so the probability。

第一思。Once again， one over B minus a。If you are in this interval。

 So basically a less equal than C less equal than B 0， if you are outside。Of the interval。

So I'm going to write other， they say you are outside of the intervalt。

So uniform inside the interval0 outside of the interval。 So let me ask you a question。

 What's the average for this noise， So look at this picture。

 Or if you want do the math on the side and tell me what's the average of this noise。 Okay。

 I'm going to give you in the quiz a number of possibilities。

 I'm going to respond to that in just one second。So what's the average here， Very easy to compute。

The average here is。A plus B。Divided by two。So that's the average。 So if I'm adding uniform noise。

 that's the average of my noise。 Okay， and how much is sigma square。



![](img/b1fab9d8340d100acfd91331dea1e75f_17.png)

You're gonna have that as one of your homework as one of your quizzes for， for week 4。No。😡。

When do we see this type of noise， For example， this is a very good model， Actually。

 both of them are good models for quantization noise。 Okay。

 so if you remember in the mostly in the first week。

 but also in the second week when we discuss image compression。

 we talk about quantization and the basic idea and quantization is that we had a range。Of values。

 And we represented it by a quantized value。 Let's say， the point in the middle。

So when you actually obtain this value， you actually represent it with a point in the middle。

 so you're making this noise。If you get this value。You are making these noise。

And that type of noise very often is model as uniform noise。Inside this interval。

 there's no noise outside that interval because when you' are quantizing， you define an interval。

 and then you define basically the representative of that interval。

 So Uni noise is a model for quantization noise， and that teaches us something new a new concept。

 noise sometimes comes from the device let's say the sensors in our cameras。

 noise sometimes comes because of an operation that we do to images。

 and Uni noise is a good model to this quantization operation。 Exp noise。

 Sometimes is also used as a good model for this。😊，Quantization。

 but is also the type of noise or error when we do predictive coding。 Remember in predictive coding。

 we were trying to predict a pixel， let's say， from its surrounding pixels。

So what's the value of this pixel if I tell you all this， That's what we did for predictive coding。

 The error of that prediction is normally model as an exponential error or an exponential noise。

 for example the JPs standard， which is basically used in the Mars rovers uses these model for the error of the predictive coding。

 So very interesting， these are really， really useful。Before I go to this。

 we see these are useful to model， for example， operations that we do in images。

 this is very useful to model real sensor noise。 This is a very useful mathematical model to develop algorithms。

 so each one of them has its own virtues and values。Lastly， I want to talk about impulse noise。

 and I can write down the formulas for this。 But let me explain it with the picture is much easier。

 The basic idea on this type of noise， which is also called salt and pepper noise。

 is that with certain probability， you change the pixel completely to a new value and with certain other probability。

 you change it to a different value。 For example， with certain I go over the image and with certain probability。

 I change a pixel， let's say to white。 And with other probability， I change the pixel。

 let's say to black。 And that's why it's called salt and pepper。 If I change it to white。

 that's called salt。 And if I change it to black。 That's called pepper。

 So we go over the image and we change pixels with a given probability。

 It's very different than these types of noise。 the Gaussian noise will affect every pixel in the image。

 The salt and pepper will affect some more some not。 But when it affects it affects all of them。😊。

In the same in the same fashion turns them either white or turns them black with a different probability。

 So it's a different characteristics。 You can think about this noise， for example。

 a noise to model when the probability is very low。 actually sensor defect。

 if one part one pixel in your camera is actually a burn。 for example， you don't get signal there。

 So that's kind of a pepper noise。 It might be black。 So with。



![](img/b1fab9d8340d100acfd91331dea1e75f_19.png)

![](img/b1fab9d8340d100acfd91331dea1e75f_20.png)

Hopefully， very low probability if your camera is a good camera， you get a pixel which is black。

 and that's a pepper noise okay。So these are very， very useful noise that we can see。 Now。

 what we're going to see next is how do we estimate these types of noise。

 That's going to be very important。 It's going to be the topic of one of the forthcoming videos。

 See you next。 Thank you。😊。

![](img/b1fab9d8340d100acfd91331dea1e75f_22.png)