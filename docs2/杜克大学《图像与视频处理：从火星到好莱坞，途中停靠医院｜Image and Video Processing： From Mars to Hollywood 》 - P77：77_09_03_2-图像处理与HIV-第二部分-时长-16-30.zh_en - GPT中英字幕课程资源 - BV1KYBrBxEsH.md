# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P77：77_09_03_2-图像处理与HIV-第二部分-时长-16-30.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

That was our first step。 Now， we get a lot of these volumes。

 So we basically go into our three dimensional data that we got from the toograms。 We found。

 So we have the three dimensional data。We go and look for all the areas with the virus and we segment out those spikes or envelopes。

Sometimes that's that done by hand。 Basically， somebody goes and places a box around each one of them。

 Sometimes you can do that automatically， if you have a model of what more or less you expect。

 Then you travel around your image with that model and you do at distance at every place and if the distance is small。

 you say， oh， it looks like there is one of these envelopes here。

 It's very similar to what we do with it with non localal means in no localal means。

 we were looking for similar patches， now the patch is a model that you have。 and with it。

 you go wrong。 So either one of those ways， either manual or with this semi automatic。

 you get this volumes。 These volumes can be like100 by 100 by 100 pixels representing basically the envelope inside this spike that we have。

 Now， remember， this are noisy。 They're not all the same。 We need to。Rorove them。

 we need to align them。 And that's what we are going to basically do。We are going to align them。

 first。😡，And they're still very noisy， so the alignment is not going to be great because you're trying to align things that are very。

 very noisy， but it's a good step you can actually only if you want align those that are basically put a very。

 very high threshold and very high level of confidence in the alignment。

 you say I'm going to align them only dose that basically after I align the distance is almost0。

 they're almost identical。 So then I have more confidence that I have done good alignment。

 Once again， alignment is you start and just rotate them until the distance that we show in the previous lines becomes the smallest possible。

😊，Once you have them align， then classification becomes a bit easier。 So you say， okay。

 now I have them all aligned。 I have them all in a common space。

 Now I want to group them to try to only put in the same group those envelopes that basically have the same three dimensional shape。

 And there are many ways of doing this classification or clustering that we need there。

 But let me just illustrate to you one example。 So you have all of them align。

 And now you have the distance， the distance that basically LED you to the smallest。😊。

Rot the the smallest alignment rotation。 So you have， you align them， you rotate them。

 you align them， You have the distance。 And now you basically， how do you group them。

 You group all of them， So you pick one and you say， hey， bring me all my friends。

 Who are my friends Don't have very small distance to me。 That's one group。

 Then you pick another one and say， bring me all my friends And who are your friends those that I got very small distance。

 So you basically group them once you group。If you did everything right。

 you can basically average them。 And we know that the average will reduce the noise。

 That's what we talked before。 We explained when we were doing image denoing。

 So you can kind of dennoise them a tiny bit。 And after you denno them a tiny bit。 You can say， hey。

 let's try to align them again。 Now they are a bit more clean images。

 So we're going align them again。 We're going to cluster again。 We're going align them again。

 and we're going to cluster them again。 And you repeat that for a number of iterations until you are satisfy either the things are not changing too much or basically。

 you say this is the best I can do。 So I'm going stick with that。 And that's a process。😊。

With the final distance， we do alignment， clustering， alignment， clustering。

 and the big thing here once again and we're going to come again and again to that is we have a lot of these small boxes。



![](img/fe310f503c1282afc83c590799d1c819_1.png)

Now， I want to reiterate to you all this is done in three dimensions。 This 100 by 100 by 100 cubes。

 We have like 4000 of them。 Sometimes we have 10，20000 of them。 So a lot of computations。

 We need to align everybody with everybody。 We need to compare everybody to everybody。

 We need to do that many， many times。You can speed up these using different basically tricks。

 one is for this particular case going to Fourier domain。

 normally these things are implemented in GPUs and very。

 very efficient implementations to make them run in hours and not in weeks。

So that's why we have the more challenging， the most challenging part computationally is this alignment part because we have to basically try all these angles。

 and that's normally done in the Fourier domain for these type of examples， as we say。

 because of the missing wedge and because of the speed。Now， you have an algorithm。

You develop this image processing algorithm and you're going to use it to detect the three dimensional shape of the envelope in the HIV virus。

But then you say to yourself。How do I know if my algorithm works。

Nobody has ever seen the envelope at the resolution that I want to see it。 So how can I validate？

 And this is very important when you're talking about medical imaging。

 because you don't want to make mistake。 and mislead， let's say。

 a complete vaccine development because you made a computational mistake。

 So what you do in most image processing， But in particular。

 when you're talking with medical imaging is you go slow。 first。

 you start from what are called phantoms you create three dimension shapes that look like viruses from your prior knowledge。

You add noise， you project them， you make missing wedges。

 so you make them like they were acquiring the microscope and you run your algorithm for that。

 you know the ground truth because you created it， you hope to reconstruct until you don't finish that you don't move on so you solve this。

 you say great， I put different structures， Phantoms I created， I rotate a noise， add missing wedge。

 I got them back， I'm happy。The next step， because it's almost impossible to do a perfect simulation of everything that is going in the microscope is you take particles that for some reason。

 we know their structure。 maybe because they are larger than the HIVs。

 maybe because they are more reach， and they could be acquired with other technologies。

 and one of them is what's called the grow E， the G E G R O E。 So you go into your microscope。

 you put growel， you run your algorithm， you get the 3D shape that everybody knows is the right shape。

 You say okay， this is as much validation as I can do。 now I'm ready to do HIV。

 Even here you can do a lot of validation， for example， you can take this 4000 samples。

 and drop 500 of them， do your computations， then drop a different 500 at random。

 do your computations and you。😊，To get very similar results。

 So still here you have to do a lot of validation， but this is a regular progress。 Phantoms， no data。

 and then you go into the unknown， which is the HIV。 Remember。

 we're looking for these tiny spikes here and which are we're talking about basically armsstrs。

 that's basically the sizes that we are talking。Now。

 let me reiterate to you why this is so important in this schematic。

These are what we have been seeing。 Let me show that again， this is。Basically。

 a true example from this cryiotmography， one slice。



![](img/fe310f503c1282afc83c590799d1c819_3.png)

And now， this is a schematic of that。Now， as I say when it goes and tries to latch itself into the membrane。

 it actually tries to basically grab from something which is called a CD4 here and then the virus has this two components that are the Gp120。

 basically this red and the Gp41 this blue and it's like。

 you could think maybe as a flower that is opening and then trying to latch into the CD4 and once again it's very important to understand how this confirmation is latching how is contacting how is' basically managing to grab the CD4 and are there any changes happening when that's。

Going on。 Now， this has been very， very elusive。 It's very， very hard to find。

 But this is the importance。 Again， we have this schematic this latching。

 this contact is critical for the virus to go into the host cell。

 So that's a very important step here。And we work I was lucky to work on this with people at NIH at the National Institutes of Health。

 And I'm going to show you some results of this and much more research has been done on this area。

 but this is important and enough to illustrate the example for this image processing class。

 and normally what you do is you basically half the virus in different states。

 and then you try to look at this 3D shape in different states。

And for the particular examples I'm going to show to you。

 we have 400 viruses from then we got 4000 of these spikes and envelopes under different states。

 so what's called agan with a B12 complex and with other complexes， so just different states。

 we want to concentrate on the image process in part。



![](img/fe310f503c1282afc83c590799d1c819_5.png)

This is what you see， this is your raw data， you put the virus， you did the cryiomography。

 you basically put all the tilt together， this is what you see and you say oh boy。

 what am I going to do with that？But you remember that you just develop an algorithm that is working for other things。

 so you plug your algorithm into that， you start， you find the envelopes， you do the alignment。

 classification alignment， classification， and then you start seeing progress。

 you start from basically this is kind of the very beginning。 nothing looks okay。



![](img/fe310f503c1282afc83c590799d1c819_7.png)

If you align things which are completely non， if you average things which are completely non align。

 you just get balls， you know， it' just everything going in every direction。

Then things start getting better， better， better， better， better， better， things start to appear。

 and you know you start seeing shapes， you didn't see anything and after iterations you start seeing shapes because you are progressively improving your alignment。

 improving your classification and then we know that if we average things that are the same。

 the noise goes down and then we can get the shapes that we wanted。So we go from this。

 which kind of has it there so we can see them here and that's where you go and you either automatically manually。

 as we say you pick all these particles and then you can get your reconstruction。

This is actually obtained from the tomography and what we really want。

 So we are starting to see the 3D。 This is just one of these。

 It doesn't have to be exactly this one that is one of them。

 you see that and you see the envelopes and basically you average and classify those envelopes。

 and here's what you see。 you have the membrane that you were expecting。

 and I'm going to just run this。

![](img/fe310f503c1282afc83c590799d1c819_9.png)

Video。And this is the shape。 This is the envelope。That you were looking for。

 And then you tried to feed pieces that， for other reasons are known。 And you see， oh。

 this is one of my validations。 Nobody has seen this in its entire composition。

 but they have seen pieces of them。 So let's just try to bring them and see if we can basically feed them properly。

 So this。Is the envelopes that you see here， how you go from here to here， smart image processing。

Once you have done that you can start doing the biology and this is what the people from biology teach us that is the important part。

 why are we doing this， they come and explain because now I can look at the HIV envelope under different states and basically see that their shapes are different。

Under different states。 And then you can start making biological conclusions about that and say under certain conform。

 this is what happened under different state when it's actually latching into the CD4 iss changing shape。

 And that's extremely important for the vaccine development people， And then the interaction starts。

 and then they ask you more image processing questions。 and then you try to address that。

 And that's why we basically is illustrate here with this schematic that basically there is a change in shape。

 a change in conform when there is CD4 binding， and that's why we illustrate here with this change in the arms。

 kind of an opening。 And you can see this with image processing。

 You couldn't see that with your naked eye。 This is one of the really exciting areas where image processing actually helps you see something you could。

😊。

![](img/fe310f503c1282afc83c590799d1c819_11.png)

Before when we talked， for example， about activity classification that was to do in the computer something that the human knows how to do here is to do something that the human cannot do。

 We cannot see the 3D shape just from those projections or from those tomography 3D reconstructions We need to do this image processing。

I hope you had fun。 This is an exciting area， and this is just the tip of the iceberg of research in image processing and viruses and microscopy。

 But it's an illustrative example about the power of image processing to solve real progress。

 We're going to see more in the next video。 Looking forward to seeing you then。 Thank you。😊。



![](img/fe310f503c1282afc83c590799d1c819_13.png)