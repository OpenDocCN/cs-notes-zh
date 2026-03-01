# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P12：12_02_04_4-离散余弦变换(DCT)-时长-25-32-可选休息点-12-13.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Now that we have。The8 by8 blocks for each one of the planes， the YCBCR。

 we are ready to go into the forward transform。 So the first thing we need to understand is why are we going to do a forward transform。

Let us explain， first of all， how do we measure the error that we create in images when we are doing compression。

 if we are doing a loss compression。And the basic idea is that error is measured with what's called the min square error。

 MSE。Or。Min。Where儿。Error。And is computed as following the main square error， the M C。

Is equal to one over the number of pixels。That's just a normalization with some。Over all， the pixels。

And what we do is we basically compute the square of the error。 We have。

 We are going to have the reconstructed image。 Let's call it F。Reconstructed。Mus the original image。

Square， we go over every single pixel。 So we're going to do F。

 So let's say that the original F was 100， and we reconstructed 98。 So we have the difference is2。

 We square it is 4。 and we do that for every single pixel with sum that we normalize that by the number of pixels。

 And most of the time because we have square here。We take a square root there。

 So it's called a root means square error。 That's how we measure the error。 Now。

 why are we going to do a transform。Let's imagine that we take remember。

 we are talking n by n blocks now in general， we are talking8 by8， but we're talking n by n。

 So we have n by n。Pixels， because we're working on each one of the blocks independently。

 Imagine that。Although these are n by N 64 pixel， I'm going to transmit only one。

 I'm going just give you the option to transmit only one of them。

 So if we take just a regular image and we transmit only one。

 we're going to get that tremendous error。That we might be able to do a transform。

Into a different8 by8， the transform has to be reversible。 I should be able to go back。

And we do this transform。 We have new8 by8， and maybe in that transform domain。

 we can take only the first one and still do a reasonable job。

 It turns out that there is a transform that allow us to do that。

 and that's called a Kauna life transform。That transform has something very particular。

You go into that transform domain I'm going to write down in a second why do I mean by a transform。

 but think it's nothing else than a multiplication by a matrix， nothing else than that。

 so I have my8 by8， I do something I go into a new8 by8 block or8 by8 image。

And then if what I did is a Kaunan lo transform that's also sentence written as K L T。

 Kaunan lo transform。The foundamine that domain。If I take the first of those。

 just the first out of the 64， and I compute the mean square error。 Remember。

 I basically did a reconstruction with only one。 So I take my image。 I do a car load transform。

 I remove 63 of the coefficients。 I come back and I compute the mean square error。

 I got the smallest possible mean square error。 I could have got them with only one。

Basically coefficient， just transmitting only one。If I want three。

 I can do actually exactly the same and the interesting part with the coonal law transform is not only that with one I get the best error。

 but actually that one is the first one so you go you have 64， you go into a new 64。

 you pick the first one that's the best you can do if you're only allowed to use one coefficient if you're allowed to use three you pick the first three。

So it's a great transform but it has only one major problem。

The problem of this transform is that this image dependent。 I don't know how to do it。

 So I told you it's gonna to be a matrix multiplication。

 but I don't know the coefficients of the matrix until I don't see the image。

 You give me the image or you give me some information about the image。

 Then I will be able to compute the coefficients of that matrix。 And that's not very practical。

 It's very slow。 And also I cannot do things on the fly as things can。

 So to replace that we can what's called a discrete cosine transform。

 which is what is actually use in JpeEC。 So let's just write down the equations for the discrete cosine transform。

 And we are going understand a bit more of what a transform is。

 But let's keep in our mind that what we actually want is a kunal lo transform。

 What the krona lo is doing is decocorreating the image， is putting a lot of information。

 The first coefficient。😊，And a bit more of information in the second。

 which is independent of the first and so on in such a way that if we want to compute the mean squarer。

 we are optimal。But we're going to be subopim with the discrete cause and transform。

 but it's going to have a fixed matrix， fixed coefficient。 So it's universal。

 we're going to be able to use it for every image without having to recompute it。

So what is a transfer。The idea is very simple。 We have an image， and we can call this image。

 Let's say F X， Y。 And this is a transform。 Were going to go into a new domain。T you。F。Okay。

 and those of you that are familiar with Fourier， Fourier is one of the transformed。So。

 we're gonna to sum。Over all， the pixels in our image， remember。We basically half n。

 So we are going to go from 0 to n -1。We're gonna go from0。To n -1。

And we are going to take our image F。And multiply。By transform。Quffific。This is what。Will become。

 I have to give you the formulas for what are these numbers for density city for the discrete cosine transform this。

Will be completely image dependent for the currentnal life will not only depend on the positions you are。

 it will actually depend on the actual gray values on the actual statistics of your image。

 So this is a transform I sum over x and Y， which means that x and y will basically disappear after my summation。

 And again a new image， which is， again，8 by8 or n by N。 So this is n。By end。

 and it's just in a transform domain。And you can write this in matrix notation。 Now， of course。

 a transform is only useful if you actually can invert it。

 It won't be very nice that you give me an image。 I go into a transform domain that then visually。

 Ill understand what's going on there。 So there' is also an inverse formula。 so I can get back。😊，X。

 Y， it will be the sum。From U equals 0。2 and -1。This time。From v equals 0。

To and -1 of now my transform coefficients T。U V， and then the inverse of the transform。

 which we are going to write sometimes is equal to r， sometimes it's not x y。有。V。So I take an image。

I do this operation。 I get a new image in a transform domain， and then I go and inver it。

 That's a transform。So to specify the transform， I basically have to tell you what are these guys。

 what's R and what's S， And once again， it's not hard to see。

 And you can just do this as an optional homework to write these in the matrix。Notation， it's not。

 not hard at all。 So I need to specify these two guys。 These two functions， R and S， which， as I say。

 ideally， to minimize the mean square error to be optimal。

 We would like it to be the krona life transform， but we can't。 So we are going to use the DC。

 which I'm going to write next。So what's DC city。In the density city。安儿。Es。Y。

 U and V is actually equal to S。E。Wai。U and V。 And this is actually equal to some normalization coefficients。

Alpha you。I发。Oh， this we and these we are the same。 I apologize。

EFor just writing two different wayss。Cosine。Of the following。Two times。X plus  one。You。Pe。

Over two times n。 this is the size。Times。Cosine exactly the same， but for the other coordinate。2， y。

2， y plus 1 V pi。Over to n。That's a general formulation。 And I have to basically write for you。

 what's this。 It's just a normalization。It's very common in this type of transforms that is square root of one over n。



![](img/027ce3d77dca8cde82d71e43eb122935_1.png)

For U equals 0。And a square root of2 over n。For you。Different than0。So here it is。 I just gave you。

The formulas for thisity or the discrete cosine transform， those that are familiar with Fourier。

 This is basically the the basically the the real part of a Fourier transform。 it's almost that part。

 So once again， the forward transform and the backwards transform are exactly the same formulas。

Very nice because you need to build one piece of software or one piece of hardware to do both the forward and the backward。

 and then it's just a cosine transform Okay so it's the cosine here and the cosine here and these are just normalization coefficients。

This is the discrete cosine transform。 Okay， let's just see it。What I wanna see。

 I wanna show you these functions。These are the mattresses that will multiply your image。

 as we have seen in the previous slide in order to get the transform。So here you see actually。

 in this case， just to make our illustration easy， we use n equal4。



![](img/027ce3d77dca8cde82d71e43eb122935_3.png)

So these are each one of the bases If I go back to the formulas and basically I put u equals 0 v equals0。

 I get a cosine which is a function of only x and y the formulas were functions of U v X and y。

 but now I fix U and v I make both of them equals0， I get a formula of x and y。

 I get actually a4 by4 image which will be this。If I basically fix v equal 1 and you equal 0。

 I get this。And so on。 So， basically， this。R and S are nothing else than what's called basis functions。

 and what we're trying to do is we're trying to decompose our small N by N image into the linear combination of these basis functions。

So if your image is flat。It's gonna have your tea。U V。It's going to only be non0 for this。

 If your image has a lot of variations， you're going to have coefficients also for T。3，3。

 So each one of the T UVs tells you how much of this type of component。You have。Okay， so basically。

 you have represented your end by image into a linear combination of these type of images。

 The important part is that these images are constant again， in the coronal life， they won't be。

And that's very difficult to have a very efficient hardware implementation to be able to do that in real time。

 here， this basis is fixed。 You give me an image。 I'm going to represent it as a linear combination of these basiss。

And T U V tells me how much of each one of these。I have in my image in my tiny N by a image。

 so that's a transform， basically nothing else than going into coefficients that tell us how much of each one of these components。

 so I decompose my image into these components， which are kind of frequency components。

 you see that there is more variation as I increase V。

 and as I increase U in the vertical or horizontal direction。

There's one thing I haven't told you I say， okay， I can't do a Carronnal loF transform。

 I cannot compute basis for a Carronnal loF because it's too expensive。

 Then I go and do a discrete cosine transform。 Why a discrete cosine transform。

 Why not a Fourier transform or any other transform a Hadammer transform there are many transforms out there。

So there is a couple of reasons why we use the densityity， one of them。

Is that although I want to do a coona life transform， I need to do a DCCT。

 it turns out that the DCCT is for particular cases actually exactly equal to the coona life transform。

Those particular cases are where the image is what's called Markovviian。

 So a pixel depends basically on the pixel next to it in a very particular form。 and again。

 the pixel next to the pixel next to it。 So those are images that are called Markovian。

So if you assume something about your image， you can show that the Karonal life transform ends up being the DCCT。

 so at the end， it is a constant basis like we see here。

 that's one reason and to basically decide to use the DCCT。



![](img/027ce3d77dca8cde82d71e43eb122935_5.png)

The other reason that we use the DCCT。Is because of the following， remember。That I'm working。

From the whole image， I'm basically having。And by end。Blocks， okay， so one may wonder why not to use。

 for example， a Fourier transform。If we go back into the theory of Fourier transform。

 when you do a discrete Fourier transform， you are making an underlying assumption of periodicity。

 so you're basically assuming that your image repeats itself。As we can see here。So， this。

Comes back here。And this comes back here。 Okay， so there is a repetition of your image。

That's the underlying mathematical assumption， to be able， to。Formerally。

 do a Fourier transform of this8 by8 block and here I'm drawing just one line of the8 by8 block。

 but the same assumption basic goes in the other direction and then in the two dimensional。Now， this。

 this basically means that when your block ends， you're expecting the pixel in the next block to basically be identical to the pixel that it was here。

Okay， so you expect this block to basically repeat。Here and repeats here。

 that's your underlying assumption。It's not very。Probable that the pixel that was here is the same pixel value that was here。

 not even close in an8 by8 block， maybe。On the other hand。

Dity assumes a different type of periodicity。 Basically densityity assumes that at the boundary。

 you have mirror symmetry。 So basically your image basically repeats， but it kind of falls。

So the assumption says， okay， I'm assuming that the pixel here is similar to the pixel here right next to it。

Not that the pixel is identical to the one that comes eight pixels later。

 but just the pixel right next to it。 And that's a much more reasonable assumption。

 So those are the two of the main reasons why we use the density。

 one is because for certain types of images， the densityity is the Caral life。

 The other is because the periodicity， The type of periodicity assumption is much more applicable to images where we started by this n by n or8 by8 blocks。

😊，So now we have the DCCT， we started with an image we divided n by N blocks。

 we do a transform into a discrete cosine transform where every coefficient tells us how much of these basis are we using。



![](img/027ce3d77dca8cde82d71e43eb122935_7.png)

I keep talking about 8 by 8， how we came to8 by 8。 Actually。

 there was a lot of studies before JPEC was defined to get to 8 by 8。

 But let me just illustrate what happens here。This is an image that basically we took the whole image in this case we don divide。

 this is already a block of that image Lina that we talked before。

We did a discrete cosine transform of this entire block。And we took 25% of the coefficients。

 So we took basically only one quarter of the coefficients。And we made everybody else zero。

 and then we did the inverse。 And that's a result that we got。 We have introduced error。

 And remember basically the DCc is what's going to try to do。

 it's going to try to bring us into a domain that introducing error basically killing some of the coefficients。

 making them zero or making errors on them won't be as noticeable。 But in this case。

 we did it very simple， we just took 25% of the D city coefficients。

 which ones is's going to be very clear soon， but just imagine that we took the one quarter of the basically largest coefficients。

Now， first we did it for the whole image here we actually took only two by two blocks。

So we went here and we did divide in two by two blocks。

 and we did a densityity of every two by two and we took 25。

Percent sos basically ended up with only one， and we came back。 And you see this very。

 very annoying blocking artifact。Then we did the same for four by4， and we did the same for8 by8。

 and we see that basically it gets better and better。So you might wonder， okay，2 by2 is too little。

 but why to stop at a by8， Why not to go to 16 by 16 and 32 by 32 and you know why not to just do the DC for the entire image。

 There's a couple of reasons for that。 One is computational。

The basically is cheaper to do multiple small DCCs than one large DCc。

 So if you have a let's say a 16 by 16 image， I rather do 48 by8 DC Cs than doing just116 by 16 DCc that's one of the reasons Another reason is this magic approximation of DCC to the Caruna Lo。

 I say that happens under certain conditions a Markovviian condition。

 if you' are in a small region at 8 by8 block， that condition that Markovviian condition will probably apply。

 but if you are on a very large image。The whole image won't have a Markovian condition。

 So basically in small regions you expect that assumption to hold。

 but it doesn't hold in large regions。 And it's not hard to see that if you're just， let's say。

 looking at me right now， you see that there is a lot of correlation here。

 more or less the same gray values。 But if you actually start moving away and you say。

 is there a correlation between the pixel value here and the pixel value here that are very far away。

 there is actually no correlation， I can actually change my shirt And without prior information。

 So there is no correlation when you get far away in your image pixels that are far away。

 basically star being decorrelated。 So you need to get to a compromise。 on one side。

 you want very small blocks because。You want a big computation very efficient。 on， On the other hand。

 basically， you don't want。2 small blocks because you get into into this problem of not having enough information in the block enough correlation to be able to decorrelate with the transform。

 And if you get to two large blocks， you start paying computation and you start paying that you violated the assumptions for which the DC is good。

 So a by8 is a good compromise that I say was was was significantly studied and it got into a very。

 very good compromise。 And that's what used today for JPEC。So。To conclude this part of the DCCT。

 I just want to show you once again this image Lina and these are just two different cases but don't worry about that for the moment here basically we took8 by8 ps。

We did a densityity， and we kept 12。5 per of the coefficients。And then， we came back。

Not really quantization， which is going to be our next step。

 Just a densityity and the inverse densityity。 And it looks pretty good。

 That means it's just when we just look for the first time at the image。😊。

We actually have achieved compression because we only kept 12。

5% of the pixels and we got an image which looks almost identical to the original one。

 and that's because we did that in the DCCT domain。

If we were to actually throw basically a lot of pixels here and keep only 12。5%。

 we will not be able to get this quality of the image。

 This is just the error between the original and the reconstructed。 And as you see。

 it's relatively small error。 So this is pretty good compression by nothing else than doing aity。

Basically， removing a lot of the coefficients and coming back。



![](img/027ce3d77dca8cde82d71e43eb122935_9.png)

So now we have the front end and we have the back end what's missing is the middle I in the DCCT domain。

 can I achieve even more compression by doing quantization in a smart fashion and that's going to be the subject of our next video clip。



![](img/027ce3d77dca8cde82d71e43eb122935_11.png)