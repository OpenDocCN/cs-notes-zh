# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P62：62_07_03_3-偏微分方程与修复-时长-21-59-可选休息点-13-31.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。Let us now describe the first imaging painting model。

 That is going to base be based on partial differential equations that we learned the last week。

 But again， this is going to be self content。 We're going to understand exactly what kind of partial differential equation are we going to use。



![](img/73cdf426e97fb939bdbadf5e626a7759_1.png)

When we talk about imaging painting， we talk about the following。 We have an image。Here。

 and we have a region where we want to change the content of the image。 In this case。

 is the cable here。 Some's going to provide us this。

Imageaging painting includes the topic where we basically have these two inputs into the system。

 We are not going to detect。 this is a very subjective。

 very often a very subjective topic about what is that we want to change。

 Maybe somebody wants to change the shoes。 In this case， we want to change this。

 Now how we detect this， we talk a lot about segmentation。

 So we can segment out objects and those are the regions of missing information。

 We are going to call them origin to be in painted with these two images。

 we want to make basically in this case， the cable disappear。 we want to im paint in these regions。

And the first topic we are going to discuss is how do we im paint with reach with information from the surrounding regions。

 we are not going to take information from very far away。

 We are only going to use information from the surrounding regions， So we get two images。

 the original image and an image which is a binary mask of the representing the regions that we want to im paint。



![](img/73cdf426e97fb939bdbadf5e626a7759_3.png)

When I personally started working on image in painting with my group。

 we visited a professional resttorator， a professional curator at the Minneapolis Institute of Arts。

 and we asked this person how do you im paint， how do you restore and it's very interesting because they were doing it the way that children draw and here is the illustration。

 we have a region to be im and we have the image？So they first continue the boundaries of the regions。

 so if there is a boundary here going inside the region to be painted。

 so then they continue the boundary inside the same way that a child will basically draw the outlines of the objects。

Then they complete the color， so first they continue the boundaries。

 then they propagate the colors inside the region， and then lastly they normally add kind of noise because paintings and in this case was a professional restator of paintings don't look fl so you have to kind of add this granularity to make it look more natural。

And we' are going to talk about this First we're going to talk about these two steps。

 then we are going to discuss a bit about this step。

 which there are many techniques to do that as well。

 So remember there's kind of a continuation of the geometry basically the boundary and then filling with the colors it's like if this is water。

 we are going to let the water flow into the region but because we have the boundary is going to actually the right water is going to flow into the right regions。

Now， the job is to design a partial differential equation that emulates this process。



![](img/73cdf426e97fb939bdbadf5e626a7759_5.png)

And here it is。So we have basically the image outside and we have a region of missing information inside and we want to propagate the information from outside in the way we are going to do that is with this equation。

 this is the first component of image painting with partial differential equations。

So what's happening here？😡，Is the information that we want properly。I'm not telling you yet。

 what is that information。So， is the information。That we want to propagate。An end。

I's the direction that we're propagating that information。

So N is a direction that we're doing the propagation。 Now， look what happens here。

 We have gradient L， meaning the change of L。Inner product with M equals 0。 This is a change of L。

And it's projected because of the inner product into to n the direction of propagation。

 And we want it to be equal to 0。 So this is， of course， a vector is the gradient of information。

 So we have a vector。And we want that vector to be perpendicular to the direction that we are propagate and so this is going to be the gradient of L and this is going to be the direction。

 we want them to be basically perpendicular in the sense that we want to propagate information L in such a way that does not change。

 it does not change in the direction of the propagation。

 that's exactly what it means propagating information。

I move it in the direction that is constant along that direction。

 that's what this equation is basically telling us that L。

 the information is constant in the direction of propagation constant along these directions Now how do we solve this with partial differential equations assume that the image is I。



![](img/73cdf426e97fb939bdbadf5e626a7759_7.png)

Now we have this and we want to deform the image。 We want to change the image。

 This is a partial differential equation in such a way that at the end we get this equal to 0。

 we have seen how to do that when we were talking about O larange equations when we want something to be equal to0。

 How do I deform the image in order to accomplish that， Let's think for a second， how to do that。

 remember last week， How do we do that。😊，Very simple。We basically do this。

 let me just go back one second。

![](img/73cdf426e97fb939bdbadf5e626a7759_9.png)

We basically do this。We make the image。Change。In time， according to what we want。

Now when this doesn't change anymore， meaning at steady state， we get this equal to0。

 that's a definition of steady state， no more change actually the computer when it very little change we can stop when this is ideally zero。

 we got what we wanted。L。Constant in the direction of propagation。

 So thiss actually a very simple trick。 Every time you want to do something like a。Equal0。

 whatever is a。 Some information of the image， you do the I。地铁。Equal a。

 and you run that to steady state， that's basically what we did for the oil larangerange。

So this is the basic equation for this type of imaging in painting Now we haven't finished I have to tell you what's L and what's n what's the information that we want to propagate and in which direction do we want to propagate and there' is a lot of art here so I'm just giving you examples I'm teaching you the concepts and these are examples that are already very powerful but you can come with different examples。

😡。

![](img/73cdf426e97fb939bdbadf5e626a7759_11.png)

Now， let me start by the information。We want this propagation to be smooth。

 We don't want to see a big jump inside the region that we are in painting。 If we see a big jump。

 we're going to notice that。 So we want it to be smooth。

 So it has to be anything that represents basically smoothness in the image。

 and one of the things that represent smoothness is the lapblian of the image。

 The second derivative of the image represents smoothness。Now。Why not the first derivative？

Wait a second。 And you're going to understand why， because the first derivative is also a representation of this smoothness。

 Now， in which direction are we going to propagate。

 And now we go back to what we learn from professional restators。 They say， continue edges。Now。

 we know that if we have an edge。The gradient of the image is perpendicular to the edge。

 we learned that way last week， so we are going to want to propagate along the edges。

 which means that we have to take the perpendicular to the gradient。

 so n is the perpendicular to the gradient as written here or we can write that n is basically the gradient。

But the perpendicular to it so that's important thing here that we want to continue edges and then for that we have to go perpendicular to the gradient and that basically also explains why we cannot take the first derivative of L because if we were to put L。

Equal to the first derivative。 let's say the gradient。 these two guys are always0。

 So I'm not solving anything because the gradient and its perpendicular are always0。 And I wanted。

 basically， to go kind of。Constant in that direction。 This is not enough。

 There is also another reason why， okay， this is always perpendicular It's not very good。

 although remember we're taking the gradient of L。 but the other reason is because we want two things to be smooth inside。

 we want to continue the gray values inside to be smooth。

 we also want to continue the boundaries to be smooth inside。

 So we need higher order of the result this， not only because these two guys are perpendicular。

 and then there's not enough information， even if we take the gradient of L。

 which is what actually in painting is propagating。 we want to go a bit higher order。

 So we get even more smoothness。 And as I say， the laplaian is one of the simplest measures of smoothness。

 So we get smoothness in the isoal direction or。Perpendicular to the gradient or on the level lines direction。

 And that basically gives us our equation。

![](img/73cdf426e97fb939bdbadf5e626a7759_13.png)

So， we have。对。Change of L。And this is the normal is the perpendicular to the gradient。

 What we're gonna get at the end of this when we get to steady state when this becomes zero。

 we basically get that the lapplian became constant along the edges and we have propagated the lapplian along the edges。

 That's what basically this basic equation makes。 And once again you just discretize it in the computer and you run it and you get image painting。

 you get propagation from outside in。 every differential equation has to have boundary conditions。

 So if this is my image and this is my region to be in painting， what do I assume here。

 and as boundary conditions for this type of equation It's a bit of a strange equation。

 it has three derivatives two because of the lapplian， one more because of the gradient， remember。😊。

We talked about this in the past， but the laplaian is the second derivative ri of the image。

In one direction plus the second derivative of the image in the other direction。

 and then we take the gradient of this， and we get a third derivative。

 So we're considering both gray values and edges in the boundary and those are smoothly propagating inside。

 thanks to basically having the laplaian here。 And these are， as we talk。

 the level lines of the image， the iso faults， the regions of directions of edges。

 These are very simple but very， very interesting equation。😊，Let us see some examples。



![](img/73cdf426e97fb939bdbadf5e626a7759_15.png)

So always when you do image processing start with very simple examples to see what's happening and here is a very simple example white is the region that needs to be im painteded and you can see here that there is a very smooth continuation really。

 really nice as smooth continuation it continues the boundary is nice。

 it of course continues the colors black and gray， but even more important it really completes the circle it doesn't know that there is a circle there it just goes in the normal direction。

😊，Perpendicular to a normal direction in the edge direction。 Remember。

 the gradient is in this direction。 The perpendicular to the gradient is in this direction。

 So it's going and it's。Fillling in inside the region propagating information in that direction。

 really， really nice result， Of course， if it works only and artificial images it's not very good。

 hopefully it works only also on real data Here is an example what is being impated the letters。



![](img/73cdf426e97fb939bdbadf5e626a7759_17.png)

We wrote on top of this image this is a nice image of New Orleans and we draw we basically rot on top and boom the letters are gone。

 so the region to be are all these letters and we go inside and we make the letters disappear we are propagating information from outside in so hard to see here and now you get a very nice image where we invented the information that is covered by the letters based on information that is surrounding the letters。

 very nice result I think。Here is another example of basically an image that has deterios and degradation。

 the red are the images， the regions that we are gonna im paint。

 Sometimes you mark regions that are a bit larger than the actual missing information look here is very thing you do it a bit larger。

 It's like giving an impulse。 So this is propagating from outside in。

 you start from a bit farther away。 It helps you come to move even more smooth as we want。

 and here are the results。 and it looks pretty good。

 sometimes you might see a tiny error here because it's covering a lot of the eye of this glare。

 So it's very difficult to invent information when there is nothing in the surrounding area that hints but one needs to be basically put in。

 but of course you get an extremely good at least initial result looks almost excellent and then a professional resttorator。

😊，UingDifferent programs might basically be able to go and repair only that tiny region if needed to。

Sometimes there is no need for that。 Here is the original one。 We have already seen it。

 A person is jumping with a cable。 Now the cable is gone， and now you see a zooming region。

 once again， look how nice the socks continue。Very nice continuation of this straight edge。

 because that's what we wanted。 We were continuing edges。 That's exactly what we wanted。

 And that's exactly what this type of algorithm does。😊，So on our example， just a special effect。

 let's just look at what's happening here。And basically they're all gone。

 I'm going to just show you that again， there are people in the boat and they're all gone。

 we're basically im painting what's basically being covered by the people sitting on the boat and basically they're all gone again in painting means modifying an image in a form that is then nondetectable at least by the regular consumer。

Here is another example。Of we have scratches and how the scratches are gone。 Basically。

 we we basically remove those scratches。 We im paint in the information from the surrounding areas and again。

 looks very nice， looks very natural as it was before it was all scratch。Now， there is one example。

 and this is the last example I want to show in this video where it's actually not very hard to detect the regions that need to be imp。

 In all the previous examples， we basically the user defines somehow the regions。 Now。

 this is an example， for example， of wireless transmission of images。 remember。

 images are transmitted are stored using JpeEC。 JPG works in blocks。

 What happens is if when you're transmittedting an image。 There is a signal drop， for example。

 on the cell phone。 So kind of a block gets drop。 Now， signal drops are not very hard to detect。

 and basically。You you have no signal and you detected it Okay， so when there is a drop， you can say。

 hey， I'm basically going to recover that block by imaging painting。

 and that's what we are simulating here。And this is the original。

 And all these blocks that you see here basically are drop signal， simulation of drop signal。

 You see that there's no signal。 You plug that into in painting， and then。Boom。

 you reconstruct your image。 Let me show you that again。 you basically see signal drop。

And you reconstruct so basically you might have a better cellular foam。

 a cellular foam that detects signal drop in images and boom does imaging painting。

 This is still JP still the person that is sending it to you doesn't know that the signal might drop at receiver and you see a signal drop。

 This actually can help even compression， you can drop on purpose some of the blockss because we know how to recover them with imaging painting and in that way you basically improve the compression ratio。

 some blockss are very easy to recover and then you can actually not even send them or not even store them makes the reconstruction a bit more computationally expensive that makes the compression possibly much higher So this is the last example from this video。

 but there's one thing I haven't told you and that was on purpose just to keep you wander a bit。

I gave you an equation of image painting， but here we have three colors。How do we do that？

How do we go from that equation that I gave you before， two colors。 Remember。

 the equation was something like。I T equal gradient。O La pla and the eye。Inner product。Braiant。H。

Ppende。So。You can basically do this for each one of the channels。

 let's say in red green blue or in any other color space。

 or you could think about extending these to color images to vectors。

 We know the concept of gradient for color vectors and we can basically define a laplaian for color vectors as well so both possibilities exist you can treat every color independently or you can try to and use definition of vectorial things for these every component here laplaian and gradient in vectorial fashion all the examples I show you every color is treated independently so this is an example of image in painting with partial differential equations。

Next video I'm going to show you an example of imaging painting with variational formulations that we learned last week。

 very simple variational formulation that will lead us to also a very nice imaging painting technique based on the same colors of propagation and boundaries I'm looking forward to seeing you in the next video Thank you。

