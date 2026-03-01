# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P14：14_02_06_6-JPEG-LS与MPEG-时长-19-32-可选休息点-13-45.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

While JPEC is the most important image compression algorithm and as we discussed before。

 probably the most important image processing algorithm overall。

 there are other techniques for image and video compression which are very important。

 and I want to describe the basic underlying concepts behind two of them。

 One is JPs and there is MEC JPs basically permits us to compress lossless basically without any loss of information preserving exactly the pixelix value at every single pixel in the image。

 and NEC is the one that we use to compress video， and you probably have M in your mobile phones as well。

 and you have seen videos on the Internet that are compressed with MEC。

 So let's describe the underlying concept between these two very important image and videoing image and video compression techniques as well。

 and we' are going start with JPs concepts basically。



![](img/b344462aa1edc7730c6f520f649367d5_1.png)

And the idea behind that is whats called predictive。Losless compression。So for comparison。

 I left here the basic diagram that we have seen so many times already for JP Ls。

 While this is the basic diagram for predictive coding and the basic idea of predictive coding is very。

 very simple。 It's even simpler than the idea of JpeEC。

 And let's just illustrate that with an example。They just draw a small portion of an image。

And in predictive coding， the first thing that we have to define is an order。

 We are going to compress one pixel after another。 And let's say that we define what's called the roster order that we basically go from left to right and win code。

The first row， then we code the second row。 and we keep going。

 So let's say that we have encoded everything。 And now we need to encode this pixel。

 The idea of predictive coding is to guess to predict the value of this pixel based only on the past。

 we cannot predict it based on the future， because the decoder doesn't know the future。

The decor has only receive。All these pixels。So we could， for example， say， okay。

 I'm going to guess I'm going to predict that the value of this pixel is identical to the value of the previous pixel。

And then what we do is after we do the prediction， we basically compute the error between my prediction and the actual value。

 and what we encode， let's say with halfmancoding here is the error。

 And the decoder basically is going emulate what the encoder is doing。 is's basically going say。

 okay， and'm going to do the same prediction that you did。 I know the past exactly as you know it。

 and I'm going to predict that this pixel is this value。

 So the encoder and decoder talk with each other。 they're using exactly the same prediction strategy。

 So I predicted this one。 and you gave me the error。

 I basically add to my prediction the error and I have this pixel value。

 And then I continue to the next pixel， I do exactly the same process。

 And the basic idea is that if you are very good at predicting this error is going very close to0 all the time。

 It's not going have。Any possible value is going have values around 0。

And that's exactly if you remember what encoders like halfmancoding likes to have values that appear a lot。

 so we can give a very short code to them and some values。 once in a while。

 you're going to make a big mistake in your prediction。 don't worry。

 because you're going to encode the error。 And basically when by encoing the error。

 you're going to have lossless compression。 So once in a while， you make a big mistake。

Then Hafman will use a larger code for that mistake。 But because that happens once in a while。

 it won't be so problematic and you're going to be able to still compress。

 So a lot of the art in predictive， lossless compression is in deciding in decidinging your predictor。

 such that the error is as small as possible all the time， hopefully0。 If you're great in predicting。

 it's going to be always0 and is going to be able to compress a lot。

 But at least it's going to be very， very close to0。 if you're doing smart predictors。

 And then the decoder is going to just do a very， very simple decoding。 So know that overall。

 the structure of a predictive， lossless compression technique is a bit simpler than in one of JpeEC。

 Of course， it's not going be able to achieve as much compression， but it's going to be lossless。

 which is very important。 So let's just illustrate a couple of possible。



![](img/b344462aa1edc7730c6f520f649367d5_3.png)

Predicctorors。So， we have our image。嗯。We're going to basically draw predictors again。

 Let's assume that all these have been encoded。And let's just consider now that what I want to do is predict。

This picture。So one thing I can do is predict it based on the past。Just on this pixel。

 So I can say that I predict this to be F。Of x-1。Why。And then if I'm the encoder。

 I'm going to take actual F of x Y。 I'm going to sub。 So my error at this pixel will be。If。Of x -1。

Wai。us1。X， y。And this is what I'm going to basically save。Through halfman coding。

 And then once again， the decoder is going to emulate my predictor is going to say， oh。

 you predicted this。 You gave me an error。 I add the error to my prediction。 I get this pixel value。

 Very， very simple operation。 in particular for the decoder is a is a really。

 really simple operation。So one possible predictor is just to use the past。

 another is basically to use the two previous pixels。

 let's say an average of the three two previous pixels。Some other predictors， like， for example。

 JP L S will actually consider a bit more will basically。

Try to use be a bit smarter and maybe use all this region。 say， okay。

 why only to use the one on the left， Maybe I can also use the one on top of you and the one basically diagonal and you can do normal combinations of them。

 as I say， you could， if you were to use these two。 You could basically average them。

 You can also average。These three， actually JPs does a bit more elaborated technique。

 So JPs is the standard for lossless image compression is actually the algorithm that is in the Mars rovers。

 One of the algorithms that that are in the Mars rovers for image compression is JPs and it does a bit smarter。

 It tries to find basically where edges are in the image， but it's also a very simple。 remember。

 compression has to be simple in order to become a standard so that everybody can implement them and they can run very fast。

 and we have seen that concept appear already in JPEC it also appears in JPs。

 and it will appear as well in E。So you could use this region。Basically， you could use， as I say。

 the whole past。You could basically say， I'm gonna why to use only these pixel。

 Maybe if I have encoded already， if I'm in the middle of a very large image。I could basically use。

My whole bus。fasス data。All the way to hear the problem is that if you do that。

 you're going to have to remember a lot of pixels， it's going to take a lot of memory。

 If you just use everything in the past， it's just too much。 So JPs as most modern predictive。

 lossless compression techniques， just use maybe the previous row at most two rows before。

 but not much more than that， otherwise， as I say， becomes too complex and too much memory。

So that's basically the idea of predictive coding。 Now。

 let's see how effective this is with just a very simple image。 So this is a nice image。



![](img/b344462aa1edc7730c6f520f649367d5_5.png)

From Earth， taken from outer space。 And this is the distribution。 Remember， we talk about istograms。

 This is the distribution of pixel values。Okay， so you see half my might like this because there is basically some concentration of pixel values around 150。

 but there's still a very， very wide distribution。 Now。

 if we do predictive coding with one of the predictors I just mentioned。 So we go roster。Like this。

 And then at every point。We basically predict the value based on some very small neighborhood around that value。

Then， the error。Is distributed as here。So we predict we compute the error。

 as I showed in the previous slide， and we plot the distribution of the error。

 the Instagram and look how nice it is。It's a smart predictor and it's a relatively nice image。

 And then we basically get a strong concentration around0。 And you can observe here。

 a plot of the prediction error。 and as expected when there are big changes。😊。

Your prediction doesn't know that a change is about to happen。

 So that's where you make most of the mistakes in regions that are relatively uniform。

 you don't make a lot of mistakes。 So that's why you get a lot of zeros。 And okay， once in a while。

 there's a big change。 you make a mistake。 and half money is going to take more bits to represent that prediction error。

 but that happens once in a while。 So most of your errors of the prediction are very small。

 and that's really， really good。 So that's basically the underlying idea of J Ps or any predictive lossless。

Encoder or compression。

![](img/b344462aa1edc7730c6f520f649367d5_7.png)

Now， you can add quantization as well in a predictive。



![](img/b344462aa1edc7730c6f520f649367d5_9.png)

Coding or in a predictive image compression technique。

 So basically you quantize the error the same way that we saw how to quantize transform coefficients。

 you quantize the error and with that you can achieve more compression you can actually have control on how much error。

 So if you are allowing plus minus1 pixel value of error of quantization in your error。

 then you know that your reconstructed image will differ will differ from the original image only by plus minus1 gray value So you can have a lot of control because you're not working the transform domain you're working on the image domain and that's also part of Jps that you can add quantization to your errors and basically the decoder will receive a quantized error and will reproduce a pixel that has a small variation compared to the original pixel。

 One very important thing。To have in mind is that when you introduce quantization。

 you have to do your prediction based on the quant。Error， so。Let's just do。

The same drawing that we had before。If we are going to predict this pixel。Based on this one。

 then remember the decoder is going only have the quantize version of that。

 after it has reconstructed a quantize error。 So at the encoder。

 you have to also emulate what the decoder is doing and consider only the quantize version of your pixel。

 If you were to predict based on the original version。

 then youre predicting based on something that the decoder doesn't have。

 and that's why it's the quantize value that enters the area of the predictor in this drawing。

 That is something to have in mind in case you are designing a basically a predictive loss a predictive。

 lossless and lossy image compression。 If you want to add quantization。 remember。

 you cannot use anything in image compression that the decoder doesn't have as an encoder。

 you have only。You are only allowed to use things that the decoder is going to see。 Otherwise。

 this basically is not a symmetric system and in one work。

 So that's just the only thing to have in mind。 And as I say j this includes a quantization。

 So this is the basic underlying idea of lossless。Predictive calling or。Loss it。

 but with control loss。Now， that's not the only way that we can do prediction。



![](img/b344462aa1edc7730c6f520f649367d5_11.png)

And basically， MpeEC， which is the standard for video compression， is also based on prediction。

 But now I have actually multiple frames。 So remember， in video， we have， let's say。

30 frames a second。 So in order to predict， for example。😊。



![](img/b344462aa1edc7730c6f520f649367d5_13.png)

This frame。I can use past frames。To predict it。 And the basic idea is very simple。

 if I'm filming a scene that is completely static， then every frame will be identical to the previous frame。

 An Npe is trying to take advantage of that。 iss trying to say， okay。

 let's just look at a region in an image。 And let's see if that region is basic constant。

 And you can do it in multiple fashions， and we are not going to discuss all the details behind Npeig。

 But for example， you can actually say， okay， I'm going to see if this region here。

 If there is a similar region。Around it。 It doesn't have to be exactly at the same place。

 It can be around it。 It's going to basically look for similar regions in previous frames。

 maybe only one frame， maybe only in three frames before me。

 it's going to look for similar regions and it's going basically also try to encode only the error。

 So it's going to do prediction in time。 Okay， and it's a very， very simple idea。

 And that works extremely well。 we know that M actually compresses a lot。 Thanks to the fact that。

 for example， this is a good example， The only thing that is moving in this video is me。

 The whole background is constant。 So if you pick blocks in the background。

 you're gonna to find in previous frames， basically identical blocks。

 And then the prediction error will be0。 And that's great for the encoder。😊。



![](img/b344462aa1edc7730c6f520f649367d5_15.png)

So here is an example with basically we have the same image that we had before but basically we have two frames of that image。

 one and2， and we do a very simple prediction here， which basically we say， okay。

 the second image is identical to the first image， If there is not a lot of motion we see that prediction is really。

 really good。 most of the time is0。 As we have seen before for the spatial predictionor。

 This is a temporal predictor。Once again， every pixel here is predicted as to be identical to the pixel in the same position in the previous image。

 we can be smarter， we can look for that pixel in a region around it and then we are going encode both the value and the offset so did I find it to the left or did I find it downwards but here it was the simplest possible thing just basically exactly in the same position and this is the difference and this is the distribution of the error so basically if I know this frame I'm going to be able to reproduce this frame very very efficiently by copying the previous frame and adding this image which is the error image。

Copying the previous frame is free because I already have it。 The decoder already has it。

And compressing this， because it's so concentrated on0 is really。

 really very efficient with techniques like Haman coldy。 I add these two images。 I get this one。

 and then I continue to the next frame。And， of course， if there is a lot of motion。

The error image won't be as simple， but hopefully will be simple enough that Haman can take advantages of it。



![](img/b344462aa1edc7730c6f520f649367d5_17.png)

And this is the basic block diagram。Of empe or video compression techniques is very similar to what we have seen for Jpeg。

 He basically has a DC quantation variable length coding like halfman。

 It only has this additional component here， which is basically encoding the prediction in time。

 So is the one that takes care of doing this motion estimation and saying， okay。

 I want to take this block from a region in the past。

 but the basic structure is the same structure plus this that takes into account that I'm not compressing just one image and basically compressing multiple frames。

And many of them are very similar。 So once again， predictive coding here actually is a combination between the techniques that we have seen for JpeEC and the techniques that we have seen for predictive coding。

 Both together produce M。

![](img/b344462aa1edc7730c6f520f649367d5_19.png)

With this， we basically have concluded the basic underlying concepts of image and video compression。

 so we have discussed JPEEC， we have discussed JPECS， and we have discussed NPEC， with transform。

 with its predictive coding， with quantization， with basically halfman coding。

 the whole building blocks of compression which is what we basically use daily in image and video processing。



![](img/b344462aa1edc7730c6f520f649367d5_21.png)

In the next video， which is going to be a bonus video， if you have time， I recommend you to watch it。

 I'm going to describe very briefly what's called rang length coding just to complete the picture。

 But if you don't have time， you can just skip that video and next week go into the next unit。

 Thank you very much。

![](img/b344462aa1edc7730c6f520f649367d5_23.png)