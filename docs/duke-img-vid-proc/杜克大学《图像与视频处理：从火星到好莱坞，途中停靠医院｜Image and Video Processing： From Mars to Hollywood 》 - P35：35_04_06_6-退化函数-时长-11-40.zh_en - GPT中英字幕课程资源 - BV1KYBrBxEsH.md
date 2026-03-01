# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P35：35_04_06_6-退化函数-时长-11-40.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back to our image and video processing class。

 We're going to continue with image restoration。 and so far we have dealt a lot with the noise。

 So let's us now work with the filtering component。

 So let's us remember that this is the complete model of degradation that we are talking about。

 we are talking about filtering the image。 And then adding noise。 And so far。

 we have considered that there was no filtering of just noise。 in general， what we have here。

 as we have seen before is G X Y。

![](img/e6d34f71d66be959a48b9590307a1295_1.png)

The observed image is equal to F。XY。Convolution with age。X， y。Plus， the noise。Which。

 as we discussed before， is a random variable that we add noise to the image。

And we have seen how to try to estimate a noise。 Now lets us discuss how to try to estimate this blaring function in general color blaring function。

 this age， this is much harder than estimating the noise。 but before we discuss that。

 why is this important， let me just illustrate it as a very。

 very simple formula why this is important。 And for that。

 let's assume for a second that we don't have any noise。 So basically there is no noise。

We' are going to take the Fourier transform of this， and the Fourier is G of U V。结果诶。Of U V times。

Age。

![](img/e6d34f71d66be959a48b9590307a1295_3.png)

Of U V。 So for those that are familiar with Fourier transform。

 this is very clear for those that are not。 just bear with me for a moment。In Fourier。

 the convolution becomes a product。 So basically， we have transformed our image into a different domain where the convolution became a product。

 And now， look what we have， we want to estimate the original image So we divide。 So we say， okay。

 very good if。U V is equal to the observation。Basically， decor the decoratedgrade image。

Divided by the filter。So if we manage to estimate the filter。 oh， very easy。

 we take the observed image。 We do a Fourier transform。

 We do a Fourier transform of the estimated filter。 We divide one by the other。

 We got the original image。 Actually， it's Fourier transform。 We inver it。 We get the image back。

 This is what's called inverse filtering。 It has some fundamental problems in particular because there is no guarantee。

That is H UV is always different than0， actually for realistic scenarios。

 it has either some zeros or is very close to0 for some values of U。OrV。

 But the general idea is very， very good that we basically。

 if we have knowledge about this degradation function， then we can try to invert it。

 And that's very cool。 That means that we want to try to estimate it。 As I say， estimating it very。

 very hard， much harder than estimate the noise。 So let's see some examples where we can actually estimate it。

 And also some examples of what type of H functions do we have in reality。😊，For example。

 one thing that happens is， as I mentioned earlier this week， is what's called blurlaring。

 Blaring means that I basically observing an image。That is the result of my original image。Convolve。

 let's say， with a Gaussian function。With serrain。Uncertain variance or standard deviation。

And we already saw the general function of a Gaussian。

 basically this exponential with a quadratic exponential function。

 we saw it when were discussing noise， Basically it blurs my image。 Now。

 if you know that there is a Gaussian function that is affecting your observation。

 So this will be my observation， this will be my G。If you know that G is the result of F。

With a Gaussian filter。 And you also know that the F was actually a dot， a delta function。

 Just a point that in that case， for example， that very trivial case。

 you can actually estimate the blurlarring that actually not very hard because a simple property of the convolution says that basically if F is a delta function。

That is convolved。With置。Then we get G。 So basically， this is actually the Gaussian。

 So a very simple case that we can actually estimate our age function for the particular case。

That we have a Gaussian filtering。 Now， this might sound a bit ridiculous at first。 I say。

 how do I know that there was a dot， that there was a delta function in my image， It actually。

 it's not so ridiculous because we can use this to calibrate the system。

 If we know that our camera is blurlaring。 Then I can put artificially。

 an image that has a deelta function。 And then I estimate my blurlaring。

 So this is very useful to do calibration to do estimation of how the camera is behaving Very important。

 Now， I'm going tell you something else that will further enhance the knowledge and the concept why this is a hard function。

A hard function to estimate F convolution G is equal to G convolution F。

 So you might wonder is F my original image， so was my original image of delta am I blaring a Gaussian or was my original image a Gaussian am I blaring a delta which means no blaring so there is a lot of basic ambiguity here that we don't know which one is what and that's yet another challenge that we have when were trying to estimate the filtering function。

And normally， what you do is you assume models for the image and models for the filtering。

 but this is just to illustrate how hard this problem is。

So this is an example where we can estimate Gaussian actually， as I say。

 is very important for blaring is also a model that is very frequently used for turbulence。

 so here is an image which is courtesy of NASA and it appears in the book that we are using so far and here we have basically the same image under different levels of turbulence。



![](img/e6d34f71d66be959a48b9590307a1295_5.png)

From more turbulence to less turbulence。 So at least you can observe here the blurring effect。

 and very often turbulence is modeled with a Gaussian filter。 So it's a very， very important。

 We discuss that Gaussian noise distributions are very important mathematically。

 although they don't appear really in real physical scenarios very often， Gaussian。

 smoothing Gaussian filtering actually is a very realistic model For a lot of things that are happening in physical cameras。

The other type of blaring that appears a lot is what's called motion blaring。

 And the basic idea of motion blaring is that when you're taking a picture。If the object is moving。

 pictures are taken by integrating the light that comes into the sensor。

 So if the object is moving during your integration time， basically you get a blurry picture。

 And that's illustrated here before I write down the formulas。 So in this case。

 is basically a simulation of instead of moving the object， we move the camera。

 And the basic idea is going back to our GF functions， basically your G function。

That we are observing is actually the integral。From 0 to T。

 that's a time of integration of your camera of。Your image。At x， But the point x is moving。

 So I can call that function of motion。 Let's say x of T。To write down that， basically。

 it's moving and it's also moving。In the y direction， Y of T。



![](img/e6d34f71d66be959a48b9590307a1295_7.png)

And I integrating over tea。Okay， so basically what I'm doing here is I'm not taking one image。

 It's like I taking multiple images and'mm adding them and what I see is the result。

 this actually was simulated by taking this image here， shifting it， let's say to the right。

Just by a tiny bit， shifting it again， shifting it again， and then adding that。

 That's what this operation is doing is basically adding images and its own shifts。

 and this is our observation。 Now if we take if we do the math and we take the Fourier transform in both flies and we use properties of the Fourier transform。

 then we can also write this in the form that we have seen before G equal H。

So also this translation is actually a filter， and I'm not going to do that。

 but you're more than welcome to do that as an exercise， a very simple exercise。

 If you' are familiar with basic concepts in Fourier transform， you basically just， as I say。

 take the Fourier in both sides and use properties of translation and you get this filter。

 which of course， will depend on the velocities so you could imagine that if the object is not moving at all。

 there is no blurring if the object is moving a lot， there is much more blurlarring。

 So this filter will depend on this velocities。And once again。

 the question will be just to show how hard it is。 How do I estimate from this。Both my image。

A my blaring effects， Certainly not a trivial thing to do。

 even if I knew that the result is a result of motion bluring。

 the concept is that from the sum of multiple images， you have to estimate  one。 Okay。

 so that's certainly not a trivial concept。 If I give you the number 5。

And I tell you the sum of two numbers。There's no way for you to know which two numbers I added。

 unless I give you more information about that。 And we're going to discuss this more when we talk in a few weeks in more advanced topics in image restoration when we come back to this topic using different tools like sparse modeling and tools like that。

 This is just to illustrate that is a hard problem and an extremely important problem。

 Sple models like Gaussian debling motion。 Gaussian bluring。 sorry。

 debllaring is the operation of inverting it。 motion blur are very， very important。

 and we need to be able to invert them to go back to our original， very， very sharp image。

 What we are going to do next is basically we are going see one way of doing that。

 And that's called a venner filtering。 That is one way of inverting a filter and inverting noise。

 And we are going to see that in the next video。 See you soon。 Thank you。



![](img/e6d34f71d66be959a48b9590307a1295_9.png)