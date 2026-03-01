# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P76：76_09_02_2-图像处理与HIV-第一部分-时长-23-51-可选休息点-12-37和18.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back In this video were going to be talking about image processing in a very particular application in medical imaging。

 and this is image processing for virus understanding and in particular to understand the shape of the HIV virus。



![](img/a3f983a95d988345b9ccedd80b46562d_1.png)

This actually brings a lot of challenges， as we are going to see。

 We're going to have to talk about many， many topics。In image processing。

 including image acquisition， and let's start with that。



![](img/a3f983a95d988345b9ccedd80b46562d_3.png)

There are many ways to acquire images and before we do that。

 we have to understand one of the basic things is the size of the structure that we are trying to acquire。

 and here we see a scale of very different structures and depending on what is that we want to acquire what type of technology we are going to be using to acquire that data。

 and of course we're used to light， we're used to cameras。

 basically light reflecting from objects and then giving us a picture。

 but depending on the size of the objects and scale。

 we might need different modalities for image acquisition。During this video。

 we are interested in viruses， and then we are going to be talking about nanometers or Arstrngs scales。

 and in particular， what we are going to use is not light。

 we are going to use electrons to acquire our image because we are at a very， very small scale again。

 in the orders of nanometers and armsstrngs。

![](img/a3f983a95d988345b9ccedd80b46562d_5.png)

Now let me just tell you why we are interested in something very small in the HIV virus and I hope this diagram。

 although a bit complicated， I think it illustrates a lot of the challenges that we are going to have and why is this so important what I'm going to explain next So here we have an HIV virus remember we're talking again。

 maybe 100 Armstrong you know just very， very small structures and here basically we have the host cell So basically the virus is trying to latch into this host。

And in order to do that， it uses things here， which are called envelope or spikes。

 and then they go and try to latch here， as is shown these diagram and then basically transmission goes into the host cell。

 So we are interested in these virus， and in particular。

 and this might surprise you and it will surprise you even more when you see the images。

 we are interested in this basically in these envelopes or spikes they're call envelopes and often they're just written as EV and once again。

 because that's what the HIV is using to latch itself into the membrane of the host cell。

 And if we understand that structure， we might be able to stop and to block that connection。

And hopefully， stop transmission。That's what we w to get。 Now we are at those small scales。 remember。

 And then what we need to use is not light。 We won't be able with light to get to that scale。

 We use electrodes。 and here is a diagram。 Now， once again， your used to basically light。

 So light comes reflects in objects like me。 and then regular cameras like the video camera that is recording right now captures the reflection。

😊，In transmission electron microscopy， Basically， we have the specimen。

 we basically have a specimen with HIV， for example， but other specimens are possible as well。

 microscopyies used all over for biological research。 electrons basically go。

 It's like you throw electrons into the specimen。 and you see， and you let them just go through。

 Basically， you capture the image you capture the image of the specimen by measuring how the electrons go through。

 And we see that in this diagram。 there is a lens。 And there is the image plane that's where things basically get captured。

 This is a picture。Of this device， the high end devices are not very cheap。

 They can cost millions of dollars， so this is not something that you carry one with you like a regular digital camera。

Once again， the issues electrons are heating the specimen basically。

 and then they go through and we capture them。 So for us it's a different way of creating images。

 but important way is that we can create images for these particles that are very， very， very。

 very small。So that's electron microscopy， and here is an image of what you will get from electron microscopy。

Now， remember， have always in mind， this is what we saw in the previous diagram。

 this is what we are looking for。One projection of that。 So you took this electron microscopy。

 and you basically threw electrons， and you have one projection of that。

 And that's basically what you have here。 So this。Is this。Doesn't look very nice。

 but we are going to have to deal with that。 And we are actually going to change the modality a little bit。

 But it's not that it doesn't look very nice because the instrument is not very good or the person that was taking the image is not very good in doing that。

 This is actually extremely good quality for this technology。 And we need this technology。

 because we want to get this very tiny， very， very tiny elements。

 So we are going have to deal with this。 Before I do that， before I show you how to do that。

 This is the beauty of image processing that we are going to be able to deal with this。

 Let me just talk a bit more about tomography。😊，Instead of just taking。

Putting the specimen and just taking one view what you do in tomography is you rotate the specimen。

 So let me just show you this here。 So you have the specimen。

 and then you rotate it and you rotate it。 and you take multiple images of this rotation。

 and that's what's called tomography。Now， what do I mean by cryo， Okay， first of all。

 we now know what's electron。 instead of electron microscopy， we say electron tomography。

 because we have multiple projections， cryo is because with the specimen before we put here we freeze it at cryo temperatures。

 Now， this technique helps to reduce radiation。 This is very important。 when light is hitting me。

 you can take as many pictures as you want of me。 I'm not going get hurt by that。

 When you throw electrons at a specimen， you're hurting the specimen， you're changing it。

 So you're changing the shape of what you're trying to understand the shape of。

 And this is very dangerous。 So this technique of cryon electron tomography helps to reduce the radiation of that and also helps you to obtain three dimensionmenal information because you have multiple multiple tilts。

 So that's basically what we do and。😊，Let's see images in a second。

 but we are doing cryoelectron tomography。

![](img/a3f983a95d988345b9ccedd80b46562d_7.png)

This is just one of those images。 Again， remember。We are interested in this kind of stuff。

 And actually， we are interested in these spikes。 You might be able to see some of them there。😊。

But that's why we want to get the three dimensional shape of that。 They are very。

 very tiny and as we see， very， very noisy。 So here's where you get the call to image processing。

And just to say once again， what kind of data we have， we got tilts。 Basically， we had the specimen。

 We rotate。 we throw the electrons at it， we get one projection。 We do a different rotation。

 we get a different projection。 a different rotation， a different projection。

 Then we put them together， and we get the three dimensions。

 So I'm going to always show you slices of this because most of the time I'm going to show you 3D when we get the reconstruction。

 But remember， this is supposed to represent this。 and we obtain it。 So here was the specimen， very。

 very tiny。 And here is the image in the computer。 Now the image processing starts with putting all these projections together to get the 3D。

Normally， although they are alternatives， that's done with what's called fiducis。 So you basically。

Bed in the specimen golf particles。And then you have a gold particle， let's say this pink。

And then you know where the gold particle is in every single of the projections and then you align the images based on those gold particles。

 So you throw a few and then you put them together。

 and that helps you to stack the images and to basically get the 3D in the computer of the real three dimensional virus。

 Now there is one thing that I want to explain here when you are doing the projection。

You can see this is very thin。😡，So I'm illustrating it much wider。 We're talking about a very。

 very thing。 So you do cryo micro cryottmography or cryo microscopy。

 You have a very thin slice at cryoempers。 So if I do the projection that I'm going to try to throw electrons from here。

 you're not going to get a lot because it's very， very thin。 So look at my hand now。

 it's okay to have electrons going like this。 but not going like this。 Okay。

 so if I have something very very thin， I can just do this。 remember。

Rotating the specimen is like rotating the race， so I can have raised here。

 but not raised here and maybe also not raised there。 So we actually don't have the full 180 degrees。

 we normally out of the 180 degrees。 we might basically miss here。 30 degrees。

 and another 30 degrees there。 And that's called a missing wedge。 So as we are going to see。

 yet another problem。 We actually don't have all the data we wanted to have because of this missing wedge。

But now were about to get into the image processing。 We acquire the data。

 We align the projections using gold particles most of the time。

 and now it's time to find those viruses and find those envelopes。



![](img/a3f983a95d988345b9ccedd80b46562d_9.png)

Now， this is what you see。 You have a line， and this is what you see。 Remember。

 this is the schematic。Of what we're looking for。But these are slices of these 3D that we just have done。

Now。Do you see here the envelopes or the spikes， No， you don't see them。

 This is where we need image processing。 We have extremely noisy data。 We have the missing wedge。

 We have tons of problems。Are we going to be able to reconstruct this 3D， I'm going to show you that。

 yes， the answer is yes， up to certain accuracy， of course。Again。

 these are just slices on the 3D volume that was reconstructed with cryotmography。

This is why we have。 This is the process that we have。

We had basically a virus or a structure inside a specimen。 We took multiple projections。

 Look how I represented here the missing wedge we didn't take the hole around projections。

 We basically have missing wedge here so we took that and we kind of get a noisy version in this 3D volume。

But there is one thing which is very important。 We get multiple copies of this。 As we have seen。

 let me show you that again。 We might have multiple copies。 You see one。

 You see another one coming here。 I'm going to show you more。 We have multiple copies。Of。This。

And we also have multiple copies of this。 And that's why we are going to exploit with image processing。

We are going to exploit that We have not one very noisy example， but multiple， very noisy examples。

 So hopefully we can extract them。Put them together。And get the three dimensions that we want。

 Remember one thing。When we talk about image denoicing。

 we already discussed that if you have multiple copies of the same object with random noise added。

 one of the best things you can do for denoing is add all those multiple copies。

If the noise has zeroromin and is random， then it would just cancel each other That basically was the concept behind nonlocal means。

 It's also the concept behind just local averaging。

 you basically one average things that are repetitions of the same and that will help you to eliminate the noise。

 remember if you average 10， the variance of the noise goes down by the square of that， So10。

 the more you average the more you manage to the noise。So that's great。

 But what's the challenge here， multiple challenges。 These images are very noisy。😊，The spikes。

 the envelopes here。And rotate it。We have to align them before we average them。 Otherwise。

 it will be a mess。 Okay， if you average this with this。😡，You， let's say these two vectors。

 you get something like this， nothing to do with any of them。 So you have to first align them。

 And I'm going to illustrate that in one of the next slides。 So you have to align them。 And also。

 are they identical copies。 Maybe there are multiple different structures， maybe slightly different。

 but still different。 So we're going to have to rotate。

 align them group only those that are the same。 And only after we do all that。

 then we are allowed to average。

![](img/a3f983a95d988345b9ccedd80b46562d_11.png)

So here is the problem。 Let me illustrate that to you。 let's say that we have three thingss。

 as we see here，1，2，3。 Now let's simulate cryoelectron tomography for this。

We basically get multiple copies of each one。 That's a good part。We get multiple copies of each one。

Very noisy。 Okay， that's not so good。 The multiple copies is good。 The noise is not very good。

 but we have to deal with that。We get them rotated。 That's also not very good。

 but we are going to have to deal with that。 And then we get the missing wedge。Okay， so。

 and of course， we don't have the originals。This is what we have。 So somebody gave you this。

Very noisy data with missing data。 The missing wedge didn't give you in the columns。

 They are all unorganized。 So you have to be able from them。

 You have to be able to group the ones that came from basically the same building。Here。

 we have to be able to group back。Here you have to rotate back and all that from this noisy data with a lot of missing information。

 If we have 30 degrees missing， we have 60 degrees missing out of 180。

 That's a lot of missing information。 and that's represented here。

 So this holes is a realistic proportion。 You have these group line， do everything。

 and hopefully after you're done， of course， you're doing all the rotations。

 all the groupings and everything together， hopefully you are able to recontrive back the virus or the images as we represent here。

 So imagine that you take multiple cameras of the same thing。

 and but you include the cameras in a random fashion。 and you add a lot of noise。

 So now you have multiple pictures of the same scene。 And now somebody comes and say， hey。

 give me back the shape of that building。 Very challenging， but。😊。



![](img/a3f983a95d988345b9ccedd80b46562d_13.png)

Hopefully doable because you have multiple copies。So what are some of the challenges that we have here。

 we have very low SNR， we have this problem with alignments and missing data。

 and we need a lot of data to remove the noise and basically we are going to have computational challenges。

So let's see how we address each one of these challenges。In part together， in part， separate。

 And this is a very tough problem。 But I think you're going to get happy to see the kind of results that we can get。

 So let's get into that。😊，The first thing we have to do is define a distance。

 remember we want to align these projections or these three dimensional shapes。

 but with missing information with the missing wedge and with noise so how do I design going back to the images into the projections of the buildings。

 how do I design when these two are aligned or they are not aligned I need to basically define a distance and we take any two images we look at two projections or two three dimensions depending where are we working and how do I know if these two are aligned or not that's the first thing we need to do basically to define a distance we are going to allow the images to rotate and also translate later on and we want to be able to say hey。

 keep rotating keep rot stop that's where you are aligned so。

To define that distance between two images with。Robustness to noise。 and with the missing wedge。

 So let's illustrate that that's the first step every time that we need to align images。

 How do I design when they are already aligned。So we have one image here。

 which I represent as a one dimensioned signal Here we have this one dimensioned signal。

And we represent it here， but we don't have the whole signal。 We actually have the missing wedge。

 so we only have the signal in certain parts of it。Now we have another signal， and also for it。

 we have the missing weight， very important。We basically don't have the missing wedge in the same place。

 Remember， these particles were rotated。So the missing wedge is kind of fixed for a particular acquisition。

 but the particles are all rotated， so with respect to them。

 the missing wedge is all the time in a different position Now you actually know where the missing wedge is or you can guess it either you know from the instrument or you kind of guess it because there is a lack of signal to noise there。

 and these are basically the two images that we need to basically decide a distance between them。

We wish to have them like here complete， but we only have portions of them。

 and the only place where we can compare them is when we have portions of both。

 So here we have information for the first one。 but there is no information for the second one。

 here we had for the second one， No for the first one。

 So the only place where we can compare is when we have information for both of them。

 So we can take a distance。 Eucide distance or any distance that you think is appropriate。

 but we need to only consider places where both of them are available。

 and that's represented by this product。 So these and these are basically square binary signals。

 one I have a signal0。 I don't have a signal。 and I can only look at places where both of them are one。

 So I have signals for both of them。 And again you can just take。Go， basically。

Almost any type of metric that you wish and illustrating here with just euclidean type of distances and this is going to be kind of your distance。

 you take the difference between the images but you only consider where both of them are available and of course you have to normalize by the amount of energy that you have per signal and that's basically written here。

 that's standard always this distance will depend on how much overlap you found and we need to basically normalized for that So that's the distance that we are going to use to illustrate the examples in the next few slides Now this distance actually is not too hard to compute you can actually compute in the Fourier domain we haven't discussed in this course too much about Fourier for those that have a background in signal process。



![](img/a3f983a95d988345b9ccedd80b46562d_15.png)

You know what Fourier is but we did talk about DCCT that is cosine transform so basically you take the signals go into a different domain in the Fourier domain and in that domain you do this calculation it's very convenient to do that for computational reasons it's also very convenient to do that there because it's very easy to represent the wedge。

 the missing information there so we have this distance which is a Euclidean distance but weighted for the regions where we have common information。



![](img/a3f983a95d988345b9ccedd80b46562d_17.png)

![](img/a3f983a95d988345b9ccedd80b46562d_18.png)