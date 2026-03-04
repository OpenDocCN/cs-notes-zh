# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p122 38_AR场景构建实践.zh_en -BV1jM4m1k73q_p122-

![](img/1dee341278ec3786a53cb2ab54a24b1c_0.png)

![](img/1dee341278ec3786a53cb2ab54a24b1c_1.png)

In this video， I'm going give an overview and an introduction to our augmented reality scene exercise。

 So this is the exercise where you take your previous 3D scene or virtual reality scene。

 which I hope you have completed at this stage。😊，And actually create augment reality versions of those scenes。

 You just have to do one of them。 And but you have so many options。

 So you could go for a A R GS marker based approach。

 So using a frame you could go for unity and use vhoria and use some of these markers。

 you could design your own markers and create a nice marker based experience。😊，You can also。

 if you have an AR core enabled phone like this is the Pix 4， then you could you could do Macas。

 if you feel like you want to do head one AR。 That is a possible。

 That's a possibility as part of the exercise。 you could do it in in many different ways。

 So obviously， if you do have access to a device like the Hollens too。 that's that's pretty cool。

 that would make it well， that would mean that unity in unreal or really good development environments for the Hollens。

 so I would say that would be a way to go， if you are staying with web based。

 So you can you can do so Webex R， you could do hollow kit。 So this is the phone goes inside there。

 It's like a cardboard。 so an AR。😊，An AI carddboard， if you will。 So phone goes in there and。

Camera needs to be exposed。嗯。In order to do MAA tracking or do MAA S AR。

 and in this case you would view it like this and you need to do a stereososcopic rendering。Now。

 that is the tricky part in a frame， for example， the way they distinguish between AI and VR is VR is theoscopic view and A R is just normal view。

 And then 3，60 would work if you wanted to really use the hollowo kit or。Cardboard。

 You could also use cardboard。嗯。You could use the cardboard and cut out a portion。

So that the camera is exposed。There are cardboards where the camera is already exposed in this case。

 I have to make sure that。Kind of like this。 I cut this out for a different phone I believe。

 and so I would have to adapt this a little further。 it's important that the camera is exposed。

 as I say， because you want to do augmented variety and so you're basically showing on the screen the camera feed so that gives you kind of like a see through that turns it into glasses if you will obviously because of the where the camera is positioned。

 you have a little bit of an offset and so you will notice that as you walk around with something like this。

I do have code where we can render an aframe scene for each eye and therefore do a stereoscopic view as a basis for AR as well。

 so I will share this。And it's a not really how aframe is designed， but it's possible。

 so that means we can really approach this exercise and do it with any of the platforms that we have that we are targeting with this MOC。

 so WebExR， unity or Un， and you can do both handheld AR。

 so with a smartphone or a tablet like an iPad。And。Or head1 AR。 So lots of possibilities。

 I'll go over the specifics of the exercise in terms of a task description。So your A scene。

 create an A scene an aframe or unity or unreal。 So please use one of these platforms and tools。

 Aframe is our tool of choice for Webex R。 keep it to Webex are unity are unreal that way we're making sure that we're all learning similar things and can help each other as well。

 your first step would be to add an AR module or plugin and a lot of these in unity and unreal。

 you have to make sure that you have to write plugins installed and have them activated in aframe It depends if you do a Macbase A are。

 you would have to add the ARj as module if that's how you think about it or' an additional library that you have to add。

And。That way you get access to an AR camera and then maybe an AR session。

 So that's how this usually works。 And then you should be able to view it in AR。

 So if you're using Macbased AR， that means you can just stick to a webcam that you have connected to your computer laptop and do it this way。

 So it would usually just mean that you hold up inbu four， for example。

 you would hold up the marker to this camera and I've shown examples of this the other way to go about it is in for example。

 using Ags， you could develop against the computer here and but then run it on your phone very easy。

 just like use code pen or glitch and run it on the phone to go to the correct glitch me URL or to the code pen debug view that's important。

 So you have a full screen view of the scene And then you can bring the marker into the view of the phone and then。

You would have the AR experience。That would be marker based and mark less， obviously no marker。

 So that would be the task。 So you adapt the 3D scene that you had or Vr scene。

 depending on which you choose as a starting point for AR。

 So that usually means you're probably gonna play around with scale， maybe with layout。

 making sure that when you have objects for example， you're designing relative to a marker like this。

 you need to print this out。 you choose the size of the marker。 And then obviously this is your unit。

 So marker size is one in a frame。 So scale 1，11 would just fit right on top of this marker as I've shown in the lecture。

 So you pay attention to these things。 you need to keep the marker in view。 So if I do it like this。

 It's obviously not gonna be recognized。 So I do these little pockets at the back of my papers that can hold it up nicely to the camera or I can also like place it on a wall like I don't know。

It or like just put it down flat。 so we can do all these things and then bring the phone in。

 and then we have an AR experience so。You may need to adapt it further because you definitely need to keep the marker in view for Marker SR。

 you don't have to worry so much about it。😊，Then in the next step。

 I want you to actually think more about like。How does this。

 How could this fit in better blend more with the environment。

 So make it more in augmentation rather than something that really stands out。

 We want to make sure that it fades in nicely blends in nicely with the environment in some tools。

 you may have object blending so that does some kind of occlusion rendering for free or removes fades out part of the object as a form of occlusion。

 but it's a little bit different。 So the Webex are model viewer version， for example。

 is a good example that shows you that。 I don't think it's the tool but that we should be using here。

 I think you want to go beyond that。 So I didn't suggest that you should use model viewer。

So you want to play with a light。 and another way that I want you to think about is another way to make objects fit in with the environment is by thinking about sound。

 adding adding sound， spatial sound。 that is a nice way of transitioning。😊。

Think how they think about how they they， for example， do cats in a movie。

 They often play the voice of the actor already before they show the actor and that is a nice transition。

 and this principle in some sense， allows you to do a nice blending。

 and that's something you could play around with you could pick up some environmental sounds and also add them to your AI experience。

 obviously you can come up with with new sounds as well。

 Think about background sounds to blend this more。 if the idea is to turn this here into a zoo which we did。

 then just having a little bit of background rainforest or whatever I think we chose rainforest sound。

 it gave us some nice bird sound that changed the experience completely。

 And I don't know it made it more believable。 it didn't change much visually， obviously。

 when I did the AI。😊，I'm going to show you this， but just having that sound in the background really made a little bit of a difference。

 So consider that。And optionally， make the 3D objects interactable。 I mean， so I'm saying fuse， tab。

 drag， etc cetera。 So that would be mobile phone base。fuse would be like if you're having， if you。

 if you add a cursor to your scene and then you would dwell on an object and then you would fuse。

AndSo， basically， if you're using a。Cardboard， somehow like cut out on the phone inside。

 and you're using it in an AR fashion。 Then you could still use a cursor like this。

 you do have on the Hollolen and on the Hollens 1， you kind of like tab where the the action is triggered where you're looking。

 So you're using gaze， your head gaze， not eye gaze。

 head gaze to determine where you're clicking and then you just activating that gesture。 Now。

 in some sense， you could do this。 You could save the $3000 whatever dollars it is for the Hollens and just do it with cardboard。

 It's not gonna be the same experience。 Trust me， but you have a button here and you can simulate something like this。

 so that one day you may deploy it to the Hollens1。 Hollens2。😊。

Which I have here is obviously a different story， has fully articulated finger and hand tracking。

 actually two hands， no problem。 and yeah， you don't actually really have a cursor usually in front you have cursors at the endpoint of the ray coming out of your hands。

 So the interaction modalities。And the interaction techniques differ quite a bit between devices and AR。

 but you can work on this exercise， and you can make it a head one AR solution if you want。

 even with the cardboard。 if not the hollow kit。 So this guy， yeah， so you have flexibility。

I'll provide some links to some of these if they are still available。

 the hollow kit was sold out recently。I'll try another approach。

 so that would be the fifth step here and I think if you have the equipment。

 let's say you've started Macbase and you have the equipment so that means you can do Macer as say are。

 I would like you to try this out。Even if you have a more advanced A core or A kit capable smartphone。

 let's say you would learn a lot from transforming this Mis approach into a Mar-based approach。

 just like we did in our case study。 I'll come back to that in a second。

 So the expected results of this exercise would be that you actually have a better sense of scale and perspective now in AR。

 So that's different from VR。That you create this AR experience in layers。

 So you're thinking about four mid background。 but you're thinking about it a little bit differently。

 So in V， I almost said the same things。 but four midden background here means really aspects of the environment that you want to blend with。

 So this room around me think about what is in the foreground in this room really depends on your location。

 obviously， so in wherever you are trying the AR experience。

 And so think about how do you want to blend in and think about the color the distance， okay。

 so this room is， for example， not very big。 And so you should really pay attention to dimensions。

 So if you put like if you're in this room and youre putting an object 5 me away。

 that would mean it's like outside this room and that's what you saw in my first steps when I was first running it with AR foundation and I placed the object further away。

 it didn't feel right， the Bur memorial tower seemed。😊，To not wasn't in the room with me。 Now。

 I didn't have occlusion rendering。 So I couldn't tell like the ws。

 it should have been occluded by the ws， but they， that that Air Foundation deployed the when the way I deployed。

 I didn't have that。And so you adjust the scale so that you bring the objects closer to you。

 and that's something that you will have to play around with。S and layers。

 And also then supporting interactions。 And the way interactions work is different in Mac based and Mac S AR。

 So also depends on form factor， As I said， whether you're wearing the device or holding the device or handheld versus headwn。

 And that's something I discussed in more detail in my lectures。

 So please refer to some of the information there。 And I'm gonna just go over bring back this。Okay。

Un closer。So that sound is important that you can hear that sound initially that sets the atmosphere that actually determines。

That I feel like， okay， that is a big aspect of making me feel like I'm looking at animals in a zoo。

 And then otherwise， it's a markbased AR experience。

 And what you see here is obviously I brought like the case study and I adapted parts of it from VR to A。

 So it is possible。 I had to play a lot with scale。

 I did get rid of some of the animals or remove the environment。 obviously， no need for controllers。

 to theportation scripts， nothing like that。 So I could simplify quite a bit。

 But even then I had to pay attention to performance。 So environment has to go。

 running a video feed the whole time on o phones。 It's gonna make them warm at some stage。

 they're gonna throttle。 They're gonna get too hot。 And then the performance goes down。

 I hope you don't have to observe this。 It's not gonna explode anything。

 but performance is gonna be really bad。😊，And here we have a Mar less version of the zoo。

And that's something I showed in the lecture， so in a little bit more detail。

 but obviously it's pretty cool。Running an experience Mars gives you a lot of flexibility。

 So here Ill just like go down there and visit the animals that now living on my carpet。

 and it's cute with animals。 maybe wouldn't be so cool if you had other content。 But in the zoo case。

 it worked pretty well。 And so I was just playing around。 as I was shooting this scene。

 I was wondering， what's the best way to fit this blend this into the would blend it in with the environment。

 And I I tried table first tabletop AR。 And even with Mars。 and then I didn't I didn't feel right。

 And so I went down on the carpet。 And I thought I was pretty cool。

 And that's why I would like my users to to experience the zoo。 And that's how I did it。😊。

But obviously， it would be totally fine if you took a smaller scale， So smaller scope， actually。

 And here I'm showing you just one animal in AR with the marker。 You've seen this before。

 So this is something that I think would be a great start。

 And then you can start exploring how you wna you wantna present it。

 Maybe you can even hide the marker。 So I could actually put a white plane on top。

 I just have this really nice white surface here。 So I could hide the marker rather than actually show the digital rendering of the marker that was just for debugging purposes。

😊，And so here I'm gonna to show you the marker less AR version， so。This part is just 3，60。 Okay。

 so this is just using the tryosco Excel。 mean I have to go into the AMMO and A frame。

 I'll show you that。 And then in this case， we can place we choosing a。Place where we。

 we do some heat testing to figure out where we wanna put the object and then it's in there。 And now。

 since it's marker less， I don't have to keep any marker in view。

 Sometimes you do see some issues with tracking just like now it shifted。

And that's something that happens sometimes， especially as you hold up the device or go in areas that are not as well lit hold up the device against vertical surfaces。

 And you can see how at least in this room that I'm using here， the the walls are just very monotone。

 There's not much on the walls。 I cleared it a little bit out。 So the more you have on the walls。

 the easier the more robust the tracking will be the more features can be detected。

 So that's something to keep in mind。

![](img/1dee341278ec3786a53cb2ab54a24b1c_3.png)

So as I was talking about VR experiences and content and interactions as go into VR experiences I I said。

 when it comes to immersive， you almost fill all this out。 And then obviously express interactions。

 you do a lot of controller or hand based interactions and then maybe speech and voice。

 So how does it look for markca based A are。 So marker based A。

 I think those experience are usually simpler。 So you do see3 models maybe animations。

 lights and shadows。 Yes， maybe some kind of heads up display， usually not so much about menus。😊。

Most Mac based AI experiences use a cursor， so that is easier for interactions。

 at least the aframe ones， let's say。You do have issues with clicking。 I'll show you this。

 It doesn't work as well。 There's an issue in deep down in AR G I talk to the developers。

 So that's something we'll figure out。 we can actually just work around。

 We cannot fix it so I would recommend you using the cursor for a mark-based AR experience or really putting a radical in the front。

 And then in the front of the user。 And that's like the gaze that they would use to interact with objects similar to how this is done on Holloends one。

And then you support imp interactions。 You could use location， obviously， like where you are。

 You don't actually have to use explicit GPS location。

And but it is done often by mark based experiences。

 You could use time of day as a variable to determine whether the scene should be dark or not that would be interesting how it blends in with the environment with with some of the Macs frameworks we can do more。

 we can actually do light estimation。Obviously， you need a fidu。

 So yeah you can do the pretty fine one。 So when you're doing like an A G S1。

 make sure you're using a decent size， make sure that you're cutting it out。

 leaving some white gaps around it So you can hold it。 This black border is significant as important。

 the beforeia markers with unity are much more。 let's say robust so you can hold it like this。

 It would still be， well， that might be a little tricky now。

 but you can occlude a significant portion of this marker。 and it would still be detected。😊。

Issues in my examples are the light conditions here that are optimized for videos。

 so you can see me well， but they don't work very well when I'm actually using markerbase A。

 There's a lot of reflection on the paper。 And that then makes it hard for the camera to detect anything。

 So that's something to play around with。 I have more tips on marker based and Mar S AR with Webex R So please look at those lectures。

 if you feel like that's the way you want to go for Bforia and unity is's relatively straightforward。

 and you could also do custom the random generator random marker generators or you could also do your own custom ones。

 if you if you add them to the image database in in Bhoria unreal。

 I haven't done mark based AR and unreal。 I don't know how it's possible。 I don't know that。

Before I works with Unreal last time I checked it did not。 So I don't think that's an option。

 So if you're doing unrealreal， then you're going Mac a less。

 that means A core and A kit or the hololens。 if you have that， yeah。

 or obviously magicly or unrealre or whatever other AR device might be available。 Apple class。

 maybe so that would be interesting。Although it's unlikely that it'll work with unreal。

 So given the current situation。 So here， let's talk about Mac S A R， so。

3D models and lights and overall， a much more complex environment。 And， in fact。

 you have light estimation。 So you would normally use environmental features。 So I mean。

 both the geometries or spatial mesh or mapping maybe even the semantic layers。

 So whether or not you're looking at a chair or window you can do in some of the So an AR kit。

 you can do this relatively seamlessly AR core is adding support for semantic classification。

 So that should be available。 maybe when you're trying this。 And then on Hollos。

 you also already have seen classification。😊，So you could do that。 And then physics， I think。

 is pretty standard with Mar S AR。 So my cubes example on the Hols。

 I just throw cubes on the spatial mesh， and then they kind of like bounce off in the the match is nicely what with what happens in physical in the。

 So it maps nicely from the virtual to the physical environment。

 And so it feels like I'm throwing cubes into my studio here。 spatial sound。

 It's a good way to make it a more believable AR and market AR experience。

 It would probably do something around hand tracking or touchscreen。

 So gesture speech and voice is something that becomes more more popular， especially head wornor。😊。

AR and smartphone。 So Macs， AR and a smartphone。 you don't see。

 you don't see a lot of speech and voice on handhel， but Marcuss and headw you do。 it's interesting。

 And these things may shift a little bit。 but this is my current analysis。



![](img/1dee341278ec3786a53cb2ab54a24b1c_5.png)

And so this brings me to the end of the introduction。Essentially， this is the beginning， right。

 This is not， this is not the， the end。 This is the beginning of the exercise。

 So I hope you learn a lot as a lot of options you have in there。 We had to keep it very flexible。😊。

This is a very quickly moving space。 Most of the information I just provided should still be accurate。

 Maybe there is a new a new update to a frame or unity and unreal。 But I mean。

 you can refer to my mark based and Mars AR experiences lectures。 I'll go over the main steps。

 Please refer to the first steps in each of the platforms I show how to go from 3D to VR to AR all in one video for each of the platforms。

 So that should be your startingyling point。 and then finally， please。😊。

Talk to each other and help each other。 I would use the firms。

 submit things in the galleries if you have issues。As a last resort。

 you can obviously also reach out to the course operations team that finally eventually probably will get hold of me and I should also be able to provide some input。

 I'd be curious to know if there's something really going wrong。

 but we' have done these exercises for a while now in my classes and yeah。

 so obviously this is not a step bystep exercise。 this is how you create and Macbased AR experience with this tool。

 No that's on you to do this。 I guide you through the process。 I think if you follow my approach。

 which is relatively universal goes across all the platforms。 it works in the same fashion。

 just the tools are slightly different。 you will actually you're gonna actually get really good at developing AR experiences。

 there's many more advanced things on top of that。 so overall， and the grand scheme of things。

 this is still introductory。 but I think。😊，You should feel very proud if you get to seeing things in AR。

 be it Mark based or markets， that is really not a big deal。

 I do think you would learn the most but trying out both if you have access to these technologies。

 So good luck and don't forget the peer review also introduce it to the peer review and how that would work and you're almost there。

 you've almost at this point， almost completed the honest track and this course that is a really great achievement。

 This is the technical course that we have here。 and not too much step bystep guidance。

 you have to fill in a lot of the gaps and I appreciate it。

 I do think that you learn a lot by doing these things yourself and looking up things youll become a much more independent developer that way。

If you're getting lost along the way again， don't reach， don't hesitate to reach out。

 Don't reach out。 I'm sorry， don't reach out。 Don't ask me。 No， you should。

 you should ask your peers。 That's the number one address。 And then if， if， if you're all stuck。

 then I'll try to to help us move forward。 but I've， I've seen good success among my students。

 So I think you'll， you'll manage。And I'll， I'll see you in the peer review at some stage， hopefully。



![](img/1dee341278ec3786a53cb2ab54a24b1c_7.png)

![](img/1dee341278ec3786a53cb2ab54a24b1c_8.png)