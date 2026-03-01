# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P9：09_02_01_1-压缩的原理与方法-时长-14-16.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back to our image and video processing class。 This is our second week of class。

 and we are going to talk about image and video compression。

 which is probably one of the most successful areas of image and video processing。

 compressionion issues all around and is actually an enabling technology， as we are going to see。

 If you have some background in information theory or previous background in signal processing。

 Some of the topics in this unit will be easier for you。😊。

But if you don't have background in those areas， don't worry because the units is going be self contained。

 and I'm going to teach you about the concepts that you need from those areas of information theory and signal processing so we can basically understand how image compression。

 JpeEC NpeG and our technologies work。 So let's start by illustrating why do we need image compression。

 This is not too hard to explain。 So let's just do some numbers。

Let's just think that we have an image that has 1000。P000 pixels。

 We know this actually in today's standards is actually a what we call a low resolution image。

 but they just use it for the sake of some numbering。And lets us assume that we need a bits。

 as is normally standard a bits to represent each one of the colors。

 which means that we need 20 bits per pixel， so we have an array which is 1000 by 100 and20 bits to represent the three colors。

So this is one image and if we are doing video， its just one frame。

 we actually need 30 of these to get one second of video。We get 60 of these。

To get one minute of video。And then we have to multiply by 1，20。

To get basically about two hours of a regular movie。 So what's this， this。

 The result of this is a very large number。Very， very large number。

And you can do offline the computation but you're going to basically agree。

 there is a very large number， even for a relatively low resolution image。

So if we only have one image， we still have a very large number here。

And we won't be able to basically save a lot of these images in our cell phones or in our computers if we don't do compression。

 so the moment we start talking about images and video， we immediately get very。

 very large numbers and that's why we need image compression。We need to make。

Possible to save those images， to save those videos without occupying so many bits in our computer or in our cell phone。

 So that's the reason we need， basically image and video compression。



![](img/9b34464a3921fe9165c735452795a5bc_1.png)

The question is， why can we do image and video compression， And there are many reasons。

 And we're going to talk about many of them。 So one of the reasons is what normally is called called redundancy。

 And that's one of the first things that we are going to see that not every pixel value is equal。

 Some pixel values appear more。 Some pixel values appear less。 As we can see this image。

 There is a lot of the gray values representing in this star。 and only a few。

Representing these white lines and maybe none representing certain colors。

 So we actually see that there is 1，2，3，4 colors here。 So if this is represented with a bits。

 it's kind have ways to use a bits 256 possibilities to just to represent4。

 So we're going to exploit that。There is another reason that we can do compression and the reason is a lot of redundancy。

 and this is illustrated in this image。So let's assume that one of these lines has a constant gray value。

 Lets just say128 for the sake of the example。 And let's imagine that this line is very， very long。

 Let's assume 10000 pixel。So there are two ways， at least two extreme ways to basically represent this One is to 10000 times。

 say 128 that will take us 10000 bytes or 10，000 times 8 bits。 So we are going to say 1，28，128，128。

128 for 10，000 times。That looks like a lot of waste。On the other hand， if I say。Starting here， I say。

10000 times1，28。So I just give a number that says how many times I'm going to repeat 128。

That's much smaller amount of memory to save that。 I need to save the 128， which is the pixel value。

 And I need to save the 10000。 The number of times that that 1，28 appears。

 And that's certainly much less just saving those two numbers than 10000 times saving 1，28。😊。

So this is an extreme case， but a very important。 And this happens often in in images that we have uniform regions and basically some geometric coherence in the image that we can exploit to do compression。

 So that's the second reason we can do compression。 And that also happens by the way in video。

 as we are going to see。 The third reason we can do compression is right here。This is a flat image。

 constant value。 So basically， there is a lot of irrelevant information in images。

 There is a lot of information that we actually don't care to save or we don't care to save in a slightly different fashion。

 for example， if this is 128， maybe I don't care if I tell you 127。

 and or maybe I don't care of it at all。 So I might not care about it。 exact value。

 I might not care too much about the information at all。

 So there is a lot of unnecessary information information which is irrelevant。

 So these are the three reasons that we can compress。 and we're going to exploit all these reasons。

 and then we're going to get very large amounts of compression。



![](img/9b34464a3921fe9165c735452795a5bc_3.png)

There is a lot of compression， as I say in the literature and part of the success of image compression is that it became standard。

 and that's very important because if I save an image in my digital camera。

 I want every computer to be able to read it， I want to email it to my friends and colleagues and I want them to be able to read it。

 So the way I save my image has to be compatible with the way that others read it。

And that's why there are so many basically compression standards in steel images。

 These are three of the most popular。 Of course， you know a lot about Jpeg。

 JPEC is what they say most digital cameras use， and it's gonna be basically the way that we are gonna teach a lot of the image processing image compression in the next hour or so there is JPs。

 which that's what's called a lossless compression。 So exactly what you see is what you compressed。

 So in that case， there is no irrelevant information。 Everything will be compressed。

 And there is the new standard Jpeg 2000。 So we're gonna to talk a lot about Jpeg and JPs。 in video。

 there is also standards。 So once again， when I take a video。

 save it on my phone and send it to my friends。 I want them to be able to read it So that。

 they need to know how I did my compression。 And of course。

 the most common ones are the impact family， although there are other。Techniques as listed here。

 So it's kind of a two size straight image and video compression has been so successful that it made it to standards that everybody uses the same techniques。

 And the fact that everybody uses the same techniques also made it very。

 very successful and very popular。 Now， digital camera manufacturers can with confidence basically use JpeEC because they know that everybody will be able to read it。

 And that's why they are comfortably using。😊，General image compression techniques that exploit all the types of issues that I mentioned a couple of slides ago work as follows。

 There is， so you start from the image。And there is a mapper。

 So we take this array that we talk in the previous week of。

 let's say 1000 by 100 points and we transform it in a way that is more friendly to compression。

 and we're going to talk about these maps。 Some of these maps are going to be related to Fourier transforms。

 it's actually a constantline transform。 Some of these maps are going to be actually in the spatial domain。

 just looking at neighbor neighboring pixels。 We're going to talk about that。Then after that mapping。

 which basically brings the image into a space friendly to compression。There is quantization。

 We have already talked about quantantization。 Quaantization is the main step that introduces error that introduces something that helps the compression。

 but limits me from being able to reconstruct exactly the damage。 So， for example。

 we might have a pixel value， as we saw last time about 17。😊。

And my quantization technique might say that I need to divide by 2。And basically， rounded。

To the closest integer from below and then multiply by two something that we talked last time。

 So I will end up with reconstructing instead of 17。 I will reconstruct 16。

 So I introduce error by doing quantization and we're going to describe some of the best techniques to do quantization and actually also the quantization that is used in Jpe which is basically。

Of the type I just wrote here。The last part is。The symbol and。 Okay， I have done my。

 I have done my mapping。 I have done my quantization。

 Now I have a value in my hand that I need to transmit。

 and I want the receiver on the other side to get exactly that number。

 That's where information theory comes into play because information theory tells us how to do this very。

 very efficiently。 both in computational time and to achieve compression。

 This is the one that is going basically exploit the redundancy that there is in the image from the point of view of using some pixel values more than others。

 And we are actually going start from this。 that basically says now I have done everything I need to do to my image。

 I want you to store or to transmit that pixel。Then once you have compressed the image。

 you basically have a file with a compression that's the encoder。

 the one that takes the image and compresses it。 the decoder will basically decode the symbol。

It won't do basically a quantization because the quantization is done at the encoder。

 if I reverse it， for example， multiplying back by2。

 and then it will do the inverse of the map and it will give you an image that might be the exact image if this is a lossless compression with no error or it might be an approximation of the image very often an approximation that we cannot with our naked eyes actually realize the difference。

 So it will be a great approximation like in JPEC or NEC。

So that's basically the whole steps and this also explains why we need standards If I use certain mapper。

 the decoder needs to understand the mapper so he can he or she can invert it and I need to explain to the decoder the symbols coding that I use so the decoder can do the reverse of that symbol code。

JPG is an example of this， and as I say， we are going to basically explain how JP works。

JaPC takes an image。And divide divides it in sub images， meaning it will take。

A whole image and will divide it in blocks。In particular， these blocks are going to be 8 by 8 pixels。

 and we're going to see why is that。Then data transform。

 This is the mapping which is talk in this case， can be a discrete。Couseline transform。

And we are going to explicitly talk about it write down the formulas and explain why this is a transform that is used。

 It's going to do quantization of the type I just mentioned basically JPEC is going to divide by a number and basically around it and it's going to divide by different numbers there' is going to be some adaptation that we' are going to explain and then once it has done that it's going to do that symbol and code which is halfman code which we're going to explain as well。

 but this is all what is done in JPEEC and you're going to see one of the optional homeworks I give you for the end of this unit is's actually to implement JPEEC in your computer is's not very hard as we're going to see and that's part of the reasons this algorithm is so successful。

The decoder is going to decode this， is going to do the inverse transform of the DCity is going to put the blocks one next to each other and it's going to show you the image。

and we're going to talk， this is done for one color。

 we' are going to also talk how the different colors the RGB are basically exploited。

 also by basically using some redundancy between the colors。

 we can actually get even more compression。So JPEC is basically an example of the prototype of the techniques of image compression with a mapping。

That is this part。A quantation and a symbolium color。

So and a very successful example of this technique。



![](img/9b34464a3921fe9165c735452795a5bc_5.png)

So I think it's time now to basically go and talk about each one of these blocks in detail。



![](img/9b34464a3921fe9165c735452795a5bc_7.png)