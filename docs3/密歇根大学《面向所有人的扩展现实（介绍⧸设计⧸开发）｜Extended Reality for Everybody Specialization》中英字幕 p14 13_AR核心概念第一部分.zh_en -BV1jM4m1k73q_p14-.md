# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p14 13_AR核心概念第一部分.zh_en -BV1jM4m1k73q_p14-

![](img/e9fa6a78fc0dfcc555fbc0f72162cad5_0.png)

![](img/e9fa6a78fc0dfcc555fbc0f72162cad5_1.png)

So now let's talk about some of the key concepts。 I will feature augmentation and mediation。

 I will talk about strong AR and weak AR， So I will distinguish those two two terms that maybe you have heard of they very popular amaca based and Macca less AR and in fact。

 I do think there's value in each so don't think of them as one superseding the other。

So after MacA based and Mac SAR we will be becoming a little bit more technical and I'll introduce you to well acronyms here。

 SlamM and ViO， so Slam simultaneous localization and mapping it's really this idea of the device figuring out both building a map of the 3D space and then finding its location within that 3D space so it's 3D position。

And Bi， which is really visual inertial oometry， is this idea of using both the camera and the inertial measurement unit of your smartphone。

 so the gyroscope in Xelmeters and trying to figure out how the phone actually moves through 3D space。

So these are some key concepts that I thought I would introduce you to because they are actually really quite important for MAA S AR。

 and then I'm going to talk about tracking and registration and the field of view and plane detection and object recognition because these are some of the things we can do based on some of the algorithms and techniques I'll introduce earlier。

So let's focus on augmentation and mediation first。

Augmentation is really this idea of bringing in virtual content as an overlay onto the real world。

 So here I drew my own variation of migram's reality virtual Al continuums。

 So from reality to virtual reality。And I drew in augmented reality。

 I drew in augmented virtual reality， and I also drew in mixed reality。

 So augmentation is really the amount of virtual content that you overlay over the real world at some stage。

 maybe roughly here is when it's mostly virtual content and not so much real world more and then virtual reality we say is when you actually don't see the real world anymore it replaces the reality around you。

This is a simplification， obviously now mediation is really along this spectrum。

 So the more virtual content I bring in， the more I could actually mediate how you perceive the world。

😊，So it is important to not just think about augmented reality as adding virtual objects into your of view。

 I mean， this is what we most commonly do。 but there's also an idea of diminished reality。

 So it can actually remove objects or have the world around you appear completely differently。

 So black mirror， if you will。 And this is when it becomes extremely exciting。

 but also very dangerous。 So augmentation always sounds like adding something and mediation really。😊。

Emphases the fact that we can mediate how you perceive your surroundings。

 and we will see more and more of these things in the future when we're starting to see ads in augmented reality。

 for example， and you should be aware of that concept。 So just to give a few more examples。

 on the augmentation side。 So typical examples are information overlays。

 any kind of spatially anchored objects， virtual objects that are like spatially anchored and appear like as if they were part of the real world。

 this idea of hologram illusion that I mentioned earlier。😊，Spatial audio。

 So even without anything visual， it could also be we could also talk about augmented reality if it is an audio that still you know abides by the rules of these three characteristics from before。

 So you're just listening to background music on your on your phone that doesn't actually it's not spatial audio。

 But if that spatial audio reacted how if they were like a virtual audio source in in the room。

 then we would actually talk about augmented reality as well。 most commonly， however。

 augmented reality is kind of like visual， but don't forget about the audio as well。😊。

On the mediation side， I have beautification。 Now that is nice right So think of all the Snapchat filters that make you look better and more beautiful I should have used one of those or those that make you look younger which I think in my case。

 would be an example of diminished reality So apart from Snapchat filters and diminished reality。

 as I said， you could for example， remove objects around me like the shelf behind me just gone and replace it with something else。

 So we're really starting to mediate and manipulate the perception of the world around us again。

 this is black mirror material， if you will。😊，And then this leads to this idea of dark patterns in the design oriented path of this X MOoc。

 I will talk more about some of these tag dark patterns and really when it comes to design ethics as well。

The next concept I wanted to talk about is strong AR and also weak A。 So this actually。

 I can illustrate quite nicely here on this graph。 So where do you think strong AR is going to be along this graph。

 It's not here because we would then not talk about AR anymore。 So it's roughly here。

 So weak A is there and strong A is there。 So weak A is like really what what Google Glass。

 I would say。It it shows some content overlay on the real world。

 but it doesn't actually really register it in 3D。And so strong A is really like all those things that I talked about earlier。

 So here strong A， highly accurate tracking。Full semantic understanding。

 We really understand the world around us。 It supports natural or as they say with the Hollands to instinctual interaction。

Wwhichch is an interesting concept and head mounted AR display is really strong AR。

 these are examples of strong AR and when I look at something and it has a noble or imprecise tracking like Pokemon Go for example is' definitely weak AR。

It has no knowledge of the environment。 that's something that they are improving now in the process of improving Canttic。

 actually。Acquired 60 AI， which was really all about reconstructing the environment so。

It will be better。 And then nowhere mostly implicit interaction。 So implicit。

 really mostly camera based interaction。 that feels kind of like weak A are just looking around。

 It doesn't actually feel like augment reality to many people。And a handheld AR display。

 a smartphone where realistically， where realistically， the only AR。

 it just functions as a lens as a virtual lens into as a lens into this virtual world and everything else around you is the real world。

 So it's like really not a lot of virtual content that you can see at any one time。

 So unless it's like really well done in terms of like the size of the content。

 It really fits that maybe tabletop AR experience。😊，You would。

 if you compare it to a headset based AR， able to consider it as more as of a weak AR experience。

Next， I'm gonna talk about Mac based versus Mac S A R。

 We're gonna look at an example of me using the Hols 1。

 I'm going use this photo as a basis for a few illustrations here。



![](img/e9fa6a78fc0dfcc555fbc0f72162cad5_3.png)

![](img/e9fa6a78fc0dfcc555fbc0f72162cad5_4.png)

And I'll show you MacAbased AR。 so I'm drawing in a coordinate system because it's something I'll need for some of the examples I'll talk about。

 So you're really out of my head basically the camera of the Hol is one of the main cameras。

 you actually see the Z Xs So me walking forward would increase Z or backward decrease Z now that depends obviously on what kind of coordinate system it is。

 left handed or right- handeded but let should say we're using a left- handed one here and then X and y now keep in mind that the y I mean we don't know actually from which perspective this is rendered。

 but one thing that I should say in this illustration when you move your head。

Like when you move your head like this or like that， that doesn't bend the Y X accordingly。

 This is something that I've seen with a lot of my students。 It causes some confusion。 No。

 the Y is always like upwards。 Okay， so whether I have my head like this。 Y is still like this。

 It doesn't go with the head that's why we actually have a magnetmeter and a gyroscope and those kinds of things in these devices so that they know where up and down is。

 So keep that in mind。And then I have the markca here。 So I use the example of the hero marker。

So it's like basically this kind of marker and then me looking with a Holloland at that marker。

 So that's what I'm kind of like illustrating here。

 And so as I look at this marker with a device or with an app that actually uses marker based tracking what will happen is okay。

 I'll start out at this location of 01。6 usually I mean， I'm a little higher than 1。

6 but the device initially thinks maybe 1。6。And。And then did from that。

 it establishes coordinate system， and then it figures out， okay。

 so the marker is really roughly from here。s the Z is an increase of 50 centimeters。

 So we update this。 it's a little bit lower than my head position。 So maybe 10 centimeters。

 although that might be a little bit of an exaggeration here and a little bit to the left and the marker is a little bit to the left。

And so because we can establish this coordinate frame here。

 we can also understand how the macroer that we are seeing now。

 we can actually figure out it's there。And so most importantly。

 the app would then use algorithms that are trained on this marker。

 So the computer is trained on this。 And if this marker is like further away from the camera。

 it's like smaller than this original one to one scale that it was trained on or when it's closer to the camera。

 then obviously it appears larger。 And if it's like somehow distorted at an angle。

 the camera can figure that out as well because it was trained on this marker。

Now I don't really illustrate all that here。 The most important thing is that there is a marker。

 We call this a fiduo because it's in the view of the camera。

 it's actually visible to both the user and the camera usually sometimes markers are designed to blend a little bit more into the environment。

 but often when we prototype and design things and using things like A toolkit based technologies like ARJS。

 for example， we used these kinds of hero markers。So they are quite popular。

 So now marker less AR obviously gets rid of the marker。 How do we do that？ Well。

 the device kind of like as it moves through 3D space， it actually finds its own markers。

 if there were something like this。 let's say I have a hero marker poster in my room。

 but I don't actually treat it as a marker and the device looks at this and builds like little feature points。

 This is by the way， also how it works based off a marker。 But in this case。

 the device finds salient pixels that it see like finds like interesting points。

 like let's say you are the computer for a second。 and you have to figure out how the camera if it were moving how it moved So you would pick a few points behind me maybe like the colored pens there。

 maybe you know the those or you like the red shelf and you're looking at specific like corners of that red shelf you're doing some kind of edge detection to figure out how do these pixels move between frames and this is really how marker tracking actually works。

😊，can if you don't have a pretty fine marker that we are trained on。

 you can use a combination of things like also the position and the pose of like the orientation of the camera and then it all sums up and you can figure out how this device。

 what we actually want to find out is how the device moves through space or how the marker comes closer to the camera。

And we can do both with some of the techniques that I'll talk about in the next few slides。

 So one concept that is often associated with augmented reality is this idea of scale of an augmented reality experience。

 and the popular type of scale is a tabletop experience。

 especially popular with Macer-based AR because what you often do is you have a marker right in front of you put on a tabletop Mark S A。

 you could also do obviously just relative to a tabletop and then the user wouldn't be seated。

 and that is a form of scale。 It's a very popular scale。 Now， with Mac S AR。

 we can actually be more free。 We don't have to place multiple markers in the room to figure out where the user is。

 Keep in mind that the device always needs to see these markers in order to understand how it moves through 3D space when it comes to marker-based AR。

So now with MacA SerR， we can find our own little features in the environment。

 let's call these key points。😊，And we can track them。

 and so we actually enable a much larger scale up to the extent that we can actually make the whole world augmented reality。

 and that is something that is currently being worked on through something called the AR Cloud and this idea of mapping the entire space in real world。

 sometimes with through games like games with a purpose like the idea of extending Pokemon Go now and using all these Pokemon Go players to map out the world for us。



![](img/e9fa6a78fc0dfcc555fbc0f72162cad5_6.png)

So it will be interesting to see who will own this data and how the data is actually being used in the future。

But we can essentially enable world scale AR applications as well。

 the most popular I would say MarkS is around the room and Markerbase is usually around the tabletop。

 although that is not a complete mental model， but it' like a very popular way to think about these kinds of AR experiences。



![](img/e9fa6a78fc0dfcc555fbc0f72162cad5_8.png)

![](img/e9fa6a78fc0dfcc555fbc0f72162cad5_9.png)