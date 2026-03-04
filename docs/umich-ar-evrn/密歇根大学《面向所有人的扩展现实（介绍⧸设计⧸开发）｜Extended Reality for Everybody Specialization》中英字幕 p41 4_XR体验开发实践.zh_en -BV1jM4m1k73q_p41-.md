# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p41 4_XR体验开发实践.zh_en -BV1jM4m1k73q_p41-

![](img/d3ff1ad9a57163dda7710fed3fb62ff7_0.png)

![](img/d3ff1ad9a57163dda7710fed3fb62ff7_1.png)

Okay and so from these examples， what have we just seen So we basically created this lion King experience and I made the analogy to filmmaking and we have done storyboarding。

 We have done physical prototyping and we have done the digital prototypes。 And at this stage。

 what you just saw we could call the minimum viable product， the MVP。 and this。

 you would now need to take further and do another few iterations on it。

 and we are entering this space of actually developing X experiences。

 And so when I think of developing X experiences， I want to distinguish two types of experiences。

 So one is relatively basic。 but even that one involves already a few components。

 you have to decide between AR and Vr， you usually put some kind of 3D characters in there。

 maybe an existing 3D model。 and you do have to have at least a directional light and ambient light in order to see anything in this scene。

 So this kind of basic experience， that's like a single X design I can do this。😊。

Mostly composed the scene。If you look at a more complex example here。

 so let's say we're bringing a custom 3D model， maybe it's rigged and hand comes with animations。

 maybe a few additional light sources。And then also sound。

And so this I would now call an advanced X experience and if you wanted to create something like this。

 you really need to jump into different role as an X designer。

 so the custom model you would actually more or less need to be a 3D artist so creating a 3D model and maybe animations。

 you can do this in some existing tools you can do this for example。

 partially in unity and unreal really can do some basic modeling and model editing at least。

 but you would normally really jump into a different kind of tool more geared towards 3D artist and it's quite different in terms of how X authoring works。

But then as an extra designer， you could still do the lights and make sure that the materials of your 3D models are properly done。

 And that's where I think most of the issues actually happen when you download and use free 3D models there's a couple of issues there。

 they usually come at very different scales at the origin in these models isn't always really said in the uniform way。

 So it's not center it's not the vintage point or anything like that or at the bottom center or all the things that would make sense no it's like really somewhere off。

 So what we had to do， for example， when we composed our scenes that you just saw from free 3D models。

 we did pride rock ourselves。 but a lot of the animals were just like borrowed from Google Poly and they are for free and you can use those models。

But then you still have to pay attention to scale and the other big thing。

 the other big issue is really the material and that the models have the right settings so that they properly reflect light and so as an Excel designer you would have to go in and fix a lot of these things。

And then sound。 So I mean we had some issues with sound。

 So you would want to maybe have all these animals make some sounds。

 as lot of background music and sound。 and maybe the soundtrack would have really added a lot to that experience here we couldn't do this for copyright reasons but you could imagine getting a bunch of free sounds and you could experiment with that as well。

 And then we did script the animations。 I mean， there's different ways and different tools。

 So the portion with the stick breaking bit part we did that in unity with the animation editors there。

 but a lot of the animations you saw that looked very crude。

 they were actually scripted in aframe So basically using a combination of ja and HTML and it's not the best way to do these kinds of animations So now that I've established the basic and advanced X experience。

 what does it actually mean in terms of content and interactions So when you break it down an X experience really into the content elements。

To the core ingredients， we're talking about 3D models and animations， lights and shadows。

 environment， so the terrain and all these things around physics， spatial sound。

 maybe menus and heads up display。And as I said， we distinguish explicit and implicit interactions。

 so explicit interactions like the cursor， so usually the head gaze or could be the eye gaze as well。

 some kind of reticle that shows us according to the surface that we're pointing and it gives us that feedback。

A controller like a Vr controller or any kind of hand movement， speech or voice。

 So these are the speech or voice commands。 So these are examples of explicit interactions。

 and then implicit interactions， a lot of camera based movement， as I said。

 but also could be things like the GPS location。 So where you are in the world that could tell us a time zone and that could actually impact how we render things for example。

 We're gonna bring in this idea of fiduial markers。

 So that is something that happens a lot of AR experience。

 fiduial means like it's visible to the camera。 It's some kind of Qr code or some kind of version of a marker usually printed on paper that we want to track。

 and that tells the camera basically its relationship to that 3D content establishes coordinate system。

 and that is oftentimes just an implicit interaction。 the marker in itself。

 although I do think there's a lot of value and marker based prototyping。

 normally in the final user experience， the marker is just something that you have to have there to establish that coordinate system。

 It doesn't usually play a big role。 And then。Environmental features could also trigger implicitly some kind of interaction。

 so basically bringing a physical object into a view or you're looking at a sofa if you're doing a furniture placement application。

 for example。These are examples of content and interactions。

 And now let's look at how for different types of XR experiences。

 we're going to distinguish between VR， basic and VR advanced or immersively。

And then we're going to look at marker based and Mar S AR。 What does that mean。

 How much of this do we actually need to fill in。 So in terms of like a basic VR experience you can achieve and accomplish with a few 3D models。

 you often it's just one and maybe some light and shadows and cursor。

 so cardboard based kind of interactions。And then a more immersive VR experience would really you know check a few more elements here so definitely in addition to light and shadows。

 you really have more of an environment， a virtual environment and maybe physics in there and maybe sound and that sound is spatial。

 maybe means of navigation through menus and some kind of heads up display。

 you may have more controller-based interaction， more handbased interaction and maybe access to speech and voice commands and this additional set of interaction that is supported if you go back to the basic and then compare to the more immersive experience on the interaction sidere really increasing a lot more on the explicit interaction side。

Let's look at AR。 So in AR we need to distinguish between Macerbased AR and MacAs AR and I'm not so much focused on handheld versus head one。

 although I must say that most head one ones are Macs and the handheld ones really depends on whether your smartphone supports things like AR core Air kit and then we would actually be able to support Macs AR experiences some people think of Macerbase as being inferior to Macs just because you have to have in marker and MacAS really means that the system computationally finds its own features so build its own markers and that's something we've established in the previous course。

But here I'm just going give you some examples， So let's look at MarkAb。

 which is almost like a basic VR experience。 You usually maybe have some kind of menu on a handheld at least we may use GPS location and we definitely need to use the marker so the Fiduial here gets a big check mark and then a MacA less experience。

 well you don't have to have the fiduial but usually you're closer to a more immersive。

 so least Macs AR experiences are often a lot richer just because MAAs means the platform gives you access to at least a little bit of the environment through surfaces and the are normals So the orientation of the surface。

 and then if you're working on a more advanced device that has actually spatial mapping and depth sensing and all these kinds of things you may get a better read on the environment and then you can do a lot more things like physics so you can throw virtual objects into the environment and those kinds of things could actually be done in a mark less AR experience if you have access to。

These these advanced sensors。

![](img/d3ff1ad9a57163dda7710fed3fb62ff7_3.png)

So this concludes our tour of what doing XR involves and at this stage I was looking a little bit both into the design aspects of it。

 but then we were also so with the wire framing and the storyboarding and then doing the physical and the digital prototyping and then we were also talking a little bit about what goes on when it comes to the development side of things and breaking down basic and advanced AR VR experiences。

 and then also connecting to some of these technologies。

 Now this part was really designed to be an overview。 we didn't go too deep in each of these aspects。

 but that what this course， that's what this course is for。

 So we're going to really explore each of the aspects going further on the design side and then we also have the course more focused on development that really looks at those aspects as well。

So I hope you got a good first sense of what doing X are involves just based on this example。

 I would invite you to take a look at the making of the real lion。

 It's actually gonna be a really cool and inspiring example and maybe something that gets you into the mood for the rest of this course。

 It's a lot of exciting things that will happen and that we'll learn about。 And Im。

 I'm so glad to be able to share this stuff with you。😊。



![](img/d3ff1ad9a57163dda7710fed3fb62ff7_5.png)

![](img/d3ff1ad9a57163dda7710fed3fb62ff7_6.png)