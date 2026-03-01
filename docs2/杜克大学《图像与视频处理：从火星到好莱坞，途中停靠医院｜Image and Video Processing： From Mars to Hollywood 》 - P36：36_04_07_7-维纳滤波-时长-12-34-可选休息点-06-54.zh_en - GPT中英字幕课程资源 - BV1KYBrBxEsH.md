# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P36：36_04_07_7-维纳滤波-时长-12-34-可选休息点-06-54.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

![](img/3ae48d188608780e5f0380dc866ed73a_0.png)

Hello and welcome back。 We are going to be talking now about vi filtering。

So we have to remember our basic degradation model that we see here。 We have， again， a filter。

 basically blaring motion blur de focuscus as we have talked。

 and we have the noise and we discuss a lot about noise， and then we observe this。

 and we want to reconstruct an image from our observation。

 And we're going to design a filter here called V filtering that basically is going to help us to get a very。

 very good restoration under certain conditions。 The basic idea of ven filtering is that we want to minimize the mean square error between the reconstruction and the original signal。

 So I'm going to write the mean square error is basically the expectation。off。

The square of the error between the original signal。And the reconstructed signal。

And we have talked a lot about this type of error in the past。We have to square it and here it is。

 So it's the expectation of the square of the error。 Now you may wonder。

 but I don't know the original signal。 That's the whole point of doing restoration is just getting back to something which is like the original signal without knowing it。

 but we have an expectation here。 so we don't need to know the original signal。

 we just need to know some statistical characterization of the original signal。

 Now it's not hard to show that the filter to put here that we minimize this well get the following form。

 So basically the Fourier。

![](img/3ae48d188608780e5f0380dc866ed73a_2.png)

![](img/3ae48d188608780e5f0380dc866ed73a_3.png)

Transform of the reconstruction。Of the reconstructed signal。Will be。

 And I'm gonna write it down and explain what I'm writing。Is the conjugate of the filter。

The complex conjuggate of the Fourier transform of the filter that we have estimated。

 as we have described in the previous videos。Divided by， basically， the magnitude。

Of this filter that we have estimated。 So this is the degradation filter plus。The power spectrum。

And don't worry。If you don't know exactly what that means， or if you forgot。

 I'm going to remind you in a second， the power spectrum of the noise。Divided by the power spectrum。

Of the signal。And all this， multiplying our。Observation。So， this。Is the winner filter。

It's a filter that is multiplying our observation to obtain the reconstruction。 And， of course。

 we have to invert this， the inverse Fourier to get the basic estimation。 So once again。

 what is this。Doing this is minimizing the mean square error。

 I have to explain to you or remind you what are these concepts， But before that。

 if you want to know how do I get from wanting to minimize the mean square error to this expression。

 It's actually not hard。 you can find a full derivation， for example。

 in this Wikipedia page it's truly not hard， you just write almost basically you write the definition of the mean square error。

 the expectation and we know that we need to take derivatives when we are trying to minimize a function and you very fast are'm going to get to this。

So let's just explain again， this expression。Here is， once again。

 the complex conjugate of your Fourier response of the degradation filter。

 Here is basically the magnitude square， Nothing other than that。 And here， as I say。

 this is the power spectrum。 So of the noise and the power spectrum of your original signal or the signal class。

 The power spectrum is basically the magnitude。Of the Fourier transform of the correlation function。

 So you have F F has a correlation function， You take the Fourier transform of that and you compute the magnitude of that。

 and that's the power spectrum of the signal。 and the same for the noise。 You take the noise。

 You compute the correlation of the noise。 You take the Fourier transform。 You compute the magnitude。

 That's a power spectrum。 So you don't need to know the function。 You need to know the noise。

 the exact function or the exact noise。 You need to know some statistical characterization of that。

 So this is the ideal。Vinner filter。 And， of course。

 you need to know this in order to be able to actually implement it。So most of the time。

 there is a very simple trick that is done instead of estimating this。 This is basically replaced。

 and I'm going to just use a different color。This。All this expression。

 which is difficult to estimate unless you know a lot of statistical characterizations of your signal。

 this is basically replaced by a constant。Pretty surprising。

 isnsn't it a very complicated thing is replaced by a constant。 So I don't use this anymore。

 I basically go。And replace this。By a constant。 And then all I have to estimate is one number。

Assuming， of course， that I have already estimated the degradation。

 basically the operation that produced the degradation like the Gaussian or like the filter that produces motion blur。

So very simple operation， a very simple filter with only one unknown that can be estimated in a number of ways。

 but we are not going to discuss that。 Now， is's basically similar to the way of that we needed to estimate the variance of the Gaussian or how much motion blur There in an image。



![](img/3ae48d188608780e5f0380dc866ed73a_5.png)

It looks very similar the basically to the inverse filter。 Remember。

 in the inverse filter all well we did is we actually took the degraded image。

 meaning the observation， and we divide it by basically the Fourier transform of H。

 basically this h that we see here。 And here is slightly different， similar but different。

 and that slightly difference is critical as we are going to see in an x examples。

So let's just look at these images。 We have seen this image before， this is the original image。

 and this is basically the result of turbulence on that image and as we know and we discussed before is model basically with a Gaussian filter。

This is the result of inverse filtering。 So we basically take the Gaussian filter。

 We take the Fourier transform。And we divide this image。 Basically， its Fourier transform。

 we divide it by the Fourier transform of the Gaussian。And then we reconstruct。

 So this is nothing else than taking this image。Taking its for。And dividing it。

 But by the Fourier transform。Of佛gasian。And then inverting the Fourier of the result。 and it'。

 I would say， quite a bad result。And we know why we are dividing。

 although the Gaussian never goes to 0， It gets very small values。

 And that basically is enhancing a lot。 and is making our reconstruction very， very nonstable。

On the other hand， this is the result of the venner filtering。 I think， is outstanding result。

So is basically， what we just saw in the previous slide。

 we basically the filter instead of being one over the Gaussian。 as here， the filter basically is。

They conjugate。Over age square。Plus。A constant。That's the filter that we apply to this image。

 We don't apply one over the Gaussian。Or one over age。

We apply this filter and we get a significantly better result。

 and the result here is illustrated with basically almost try an error。

 We basically try the best possible K knowing in the original， it just for pedagogic reasons。

 basically to show you how great we can get a result with venner filtering if we estimate this constant。

So to show you that this is not just not all one example that it can do great。

 let just show a second example of an image that we have seen before。Here we have an image。

It's basically the book。 It's the cover of the book that we have been using but just in black and white。

It has motion。 We have seen that already， so it has motion blur， and then we add to it noise。

And then we apply we know exactly motion blur。 So we computed exactly the filter。

 and we apply inverse filter。 And this is what we get。 So once again。

 going from here to here is the result of taking this image and filtering with an inverse filter one over age。

 and I'm not including the problems that might happen because I need to estimate age。

 I'm actually putting the exact age that I use to create this image。

 And the result is close to a disaster basically， for the same reasons。

As we saw in the previous example。This is the result of ven filtering。 Okay， once again。

This is why we are applying here。And again， we use the best constant that we could use against for pedagogic reasons to illustrate the power of the innerner filtering。

Now。😡，You probably see here the blur and you might see also the noise here we actually take one order magnitude to the less noise。

 same blur， same motion blur， and again we apply the inverse filter and we apply the venner and again。

 this is a really， really bad Basically what we are recovering here is the motion。

 We are not able to recover anything else， but venner filtering is doing outstanding job。

If we reduce the noise even further， actually five orders of magnitude。

 I don't think you can see any noise。 if you compare this to this。

 Basically is the noise is so small that they say the dominant degradation here is the motion blur。

 This is the inverse filter。 Now is much better， but still not great。 Again。

 this is nothing else than an inverse filter。 they apply to the to the。Bre and noisy image。

 And this is the result of venner filter。 So this column is always inverse。 This column is always。

Vinner filtering and just different levels of noise here。 And I think we got the perfect result。

Why it's perfect because as I say in this example in this kind of artificial pedagogic example。

 we didn't have to estimate H， we know exactly H and also we estimate the best possible k。

 but this illustrates how this filter is extremely powerful once we estimate the degradation filter or the motion blur in this case and the constant and still Vner inverse filter。

 sorry here， even if we know exactly H， it just doesn't do a good job。

 so I hope I convince you that Vner filtering is a very simple operation and it can be extremely extremely powerful。

So by this we conclude winner filtering and in the next video we are going to just basically conclude the unit on restoration。

 Thank you very much。