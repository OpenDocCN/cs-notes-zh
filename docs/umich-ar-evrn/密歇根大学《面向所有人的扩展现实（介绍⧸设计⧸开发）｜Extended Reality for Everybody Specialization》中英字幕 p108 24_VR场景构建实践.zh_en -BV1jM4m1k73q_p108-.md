# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p108 24_VR场景构建实践.zh_en -BV1jM4m1k73q_p108-

![](img/d43d9b345fb1d6d5099257241773b71b_0.png)

![](img/d43d9b345fb1d6d5099257241773b71b_1.png)

In this video， I'm going to go over some of the steps as part of our honest track exercises in which we're going to create a virtual reality scene。

 So the starting point is still the 3D scene from the last module。 So really that was important。

 and obviously you will potentially make refinements and definitely adaptations of that 3D scene as you're entering the VR space。

 but I would recommend that you first complete the 3D exercise following my method。

 and then you're taking on this one。 even though you might be very eager can't wait to make it into VR I understand it is a fascinating world for this exercise。

 you do need some equipment。 So you will be able to get away with cardboard and your phone like your phone goes inside。

 So that would be a way to do it， I wanted to make sure that the majority the vast majority of learners can at least do this。

 So that means that some of the steps in the exercise I mark as optional they may not。

Be feasible if you only have three degrees of freedom。

Obviously if you are a lucky one and have something like this or even more modern than what I have here。

 I mean right now this is the latest the rift S and I have the quest as well in the background so then you can do quite a bit more and if you are in that league of devices then you can consider working with unity or unreal and if you are cardboard。

 most of my students in my class work with cardboard。

 so my residential program and we can create cool things that way too and you can notice I come back to this idea but we've cut out this part so we can also do augmented reality with the cardboard。

😊，When Ill talk about this when we're doing the AR exercises。

 so can you can do this even if you don't have some of the other devices and you could even just well I do think it would be great if you were actually to see it in VR。

 So a sterreoscopic view I think makes the difference。

 So that would be a good way to go about it and you should aim for that。

 if you don't have VR equipment at all。 you will be able to simulate things in 360。

 So it's like you're like looking into the scene。 and it's like a little bit of a magic window。

 it just doesn't have 60 degrees of freedom。 It's just like you rotating around a spot。That is 360。

 Okay， so that's not virtual reality。 So don't confuse those。 I do mean 3D virtual reality。

 stereoscopic view would be ideal So you have it on on your head， you should mount it on your head。

 that would be the goal， but again， if you don't have access to some of the equipment we will accept you you're doing a demo video or taking a few screenshots with running it on the phone or yeah。

 on the phone， I guess would be the way to do it then。So here I have the task description。

 So this is your VR scene。 create a virtual reality scene in a frame or unity or unreal。

 Please refer to my first steps in each of these to get a better sense for how you would do it。

 I mean， by this point， you should have made your choice because you did a 3D scene already or you should definitely have done the 3D scene。

And so I'm assuming you have that 3D scene and so from that 3D scene。

 what you would now do is as a first step is actually add a camera rig to the 3D scene。

 So an XR camera or a camera rig an aframes， an XR camera in unity when you're using the XR。

 sorry the VR plugin。And the goal would be to view it in VR。

 which obviously requires a virtual reality headset。 And as you're viewing it in VR。

 it'll allow you to make adaptations because scale is most likely not gonna work。

 So adapt the 3D scene for virtual reality。 Think about scale。

 you most likely have to scale things up rather than down just to get the proportions。

 especially as you're standing up And if you're having like a 6 degrees of freedom headset。

 So you're fully tracked in 3D space and you're getting up like in my example with a giraffe that I showed earlier。

 you really want to get the scale ride， you also want to get the layout。

 and think about that whether that needs to be adapted， how much travel do you do you want。

 how big should the virtual reality be， I mean， you maybe feel like wow， now we have more space。

 even if you that's that's the funny thing。 even if you're just looking at your smartphone。

 let's say in 3D， and then you're putting it in。you feel like wow， I suddenly have so much space。

 but if you think about it， it's still the same screen right it's not more space。

 it's just like the way we perceive things and obviously having this agency around your head really makes you feel like oh wow now I really can do something with this scale the user is like think about some visual cues to guide users where they should look and yeah。

 so let's go back to the exercise。😊，So make it moremersive then I would like you to really add an environment or terrain。

 You can do rocks and trees and everything in unity and unreal。 you can do that as well。

 It'll look amazing。 It'll take a little bit of time， but it'll look amazing。 And if you enjoy this。

 why don't you just go for this。😊，And in Aframe， you can use an environment component and configure it in different ways that would be the easiest way to do it。

 you could also go there and work with templates in aframe so those could be copy pasted basically instantiateated at different locations。

 but you could use templates to create for example。

 little forest areas or something like that if you wanted to do your own little trees or compositions of3D models。

Lights and sounds are very， very important， and they will make it a lot more immersive。

 So please consider adding additional lights and definitely also sound。😊。

AndO you should support travel。 This is a virtual reality world and you can do this via a menu Now this will require a little bit of digging into unity in well an aframe yes。

 so there are no standard widgets and unity you have the canvas。

 either the canvas approach or using a widget libraries so Steam VR has examples。

 mixed reality Tookit has examples X interactions is using。In AR Foundation。

 I've seen standard examples just using the canvas。 I haven't have I seen VR menus in X interaction。

 Maybe they have that。 I'm not sure it's something for you to figure out。

 X interaction as native to unity。 and then the other toolkis I just mentioned。

 they would be very popular platforms。 they allow you to do menus， you will find examples。

 teleportation So they have teleportation hotspots and areas。

 all of these toolkits and aframe would have a teleportation component。

 So that would be actually relatively easy。 but you need a controller。

 you need a VR headset in a controller。 So that's why I make it optional。

 And then also object manipulation。 And you can think about near and file manipulation。

 as I showed in my exercises in each of these toolkits have examples for this。

 And so it would be a great way for you to explore this in aframe。

 it would require obviously raycasting。 you can use laser controls and respond to click events。

 I'll talk about that。 So as I said， I'll provide more tips and tricks for aframe。

Just because I think it is potentially the one platform that a lot of us can easily well access over the web。

 And since we're learning online。 and we don't have to download Unity and all that in parallel。

 But obviously， unity and Unal will lead to excellent results。 And it just require a lot more time。

 good bandwidth。 So the amount of hourss I spend downloading things in unreal is amazing。

 but it usually looks great afterwards。 And just， you know。

 creating a relatively simple project is several hundred MB。

 And then the1 I'll show at the end of this course， mission A R iss only 13 GB。 So that is a lot。

 if that is a lot。 So。😊，And yeah， object manipulation would be cool too。

 And so the whole idea of this exercise is obviously。😊，I'll， I'll push you because I want you。

 if you follow this approach， I want you to， Well， you will explore actually。

 a systematic method to create a V R scene that includes all the basics。 So it's immersive。

Supports travel and supports object manipulation and if you have a menu or manipulation you also have selections。

 so we have all the basic ingredients that I' talked about in the lectures。Overall。

 you would definitely develop a better sense for scale and perspective in VR。

 So that's something to that will just happen you need to adapt from your 3D scene。

 I'm pretty sure you learn how to create a VR experience in layers。

 So really I would like as you make it more immersive。 you would probably think about parallax。

 And so things should happen in the distance in the background in the Midgown in the foreground and don't just design the foreground。

 really design in layers， just like Disney movies are composed in layers it's gonna to make a big difference。

 So at least have a skybox， maybe something in the distance。

Maybe have a few birds or something in there， just like something in the mid to background in addition to the foreground。

Sport interactions for travel， object selection and manipulation。

 that would be like if you have all that that means you have a virtual reality， you can。

 you can walk in there， you can， you can explore things， you can pick up things。

 you can manipulate things。 So that's potentially what you would want and。😊。



![](img/d43d9b345fb1d6d5099257241773b71b_3.png)

Yeah， the one thing I would say at this stage， usually my students are like super excited。

 they want to create a super cool game or something。 It's gonna be very difficult。

 And the problem with games is that usually you spend ages figuring out game mechanics and those kinds of things。

 So， I mean， if you have a game idea in mind， focus on one or two interactions and。😊，And that's it。

 So don't no need to do this whole game here， although it would obviously。

Push the envelope quite a bit。 But yeah， no need。 Okay， so I wanted to say that。

And I wanted to come back to our case study。 So obviously。

 our case study was a great example of a very complex virtual reality。 So my student carer。

 she actually spent hours building this。So don't be trick this。

 even though this may not look like a Disney production， it's not。 So in terms of quality。

 this is actually relatively high quality for。For a frame。

 we could have tweaked a lot more Kara said herself。 She would have liked to do this or that。

 But overall， it's a cool。 It's a cool experience experience。 It's a zoo。 And we have travel here。

 So I can go to these different areas， also plan it out。 I started with primitives。

 The whole scene started with primitives。 So the 3D scene was the first step。😊。

And now we have travel and we can then also do object selection and manipulation。

 which which we implemented in this petting area and where you can feed the animals virtually So this is only possible in virtual reality it told you the zoo is modeled after the Detroit zoo。

 but only superficially modeled and the values of the Detroit zoo dictate。

That animal welfare is the most important part。 And so you don't actually get that close to animals normallyminee。

 but in virtual reality。We can implement that， you see。Quite an advanced scene。 So this is。



![](img/d43d9b345fb1d6d5099257241773b71b_5.png)

SeveralSeveral hours of hard work of a student who has previously completed。My course。

 so keep that in mind。 And here we now actually finally grab a banana， come on。Let's grab the banana。

 and。And you go to the other side， and。Feed the animal。

 So this is object manipulation with super hands and aframe， something I'll talk about as well。

 later， how to do this， as I'll tell you about immersive VR experiences。

So that brings me to this overview of XR experiences。

 and so I laid this out previously in some other parts of the XOoc。

 So when we're talking about XR experiences， we have all these kinds of content。

And we should distinguish between explicit interactions and implicit interactions。

 And so a basic VR experience， which is really just the goal here， would entail a 3D model。

 maybe multiple 3D models and maybe animations， lights and shadows， which you get for free。😊。

Initially， but you should consider adding additional lights and also playing with shadow。

And if you're talking conboard。So， here。A common way to interact is have a cursor in the middle of the screen。

And that way would be a common way to point and navigate。 So that's a cursor。

 So that's a basic VR experience。 And then as we make this transition into an immersive VR experience。

 you can see there's actually quite a lot more things going on。

 So I do think a fully immersive VR experience includes all these things here on the left and an environment。

 physics， ideally。😊，Sppatial sound， very important to make it immersive and menus and hs as you're creating more so heads of displays as you're creating more complex environments。

 and so immersive your experiences usually have these， you don't have to necessarily have that。

As you go increasing immersiveness。 So this would be way of increasing immersiveness。

 And then also the interactions are a lot more interactions with the controller or a hand in VR or speech and voice。

 And so you can prototype speech and voice interactions with some of the toolki。

But it's not a big thing。 Usually you add additional libraries。 So an aframe。

 there's a speech component which uses feature recognitions。 So that's kind of okay。

 but you often have to repeat yourself。 And maybe I'll include an example of that。

 But it's definitely in my code pen libraries somewhere。

 And then controller and hand interactions are really。

 really popular when it comes to immersive VR experiences。 So the the majority of interactions。

 however， are controller based。 So usually with a one or two controllers and you provide support for the different buttons。

 the trigger button， the grip button。 and obviously。

 it depends on what kind of VR hardware you are using and whether you have one or two controllers and whether it's three degrees of freedom or 6 degrees of freedom controllers。



![](img/d43d9b345fb1d6d5099257241773b71b_7.png)

On cardboard， keep in mind that you can do interactions， you have a button here。

 but you can also do exp interactions like dwelling， so that means likefuse。

 you'll trigger the fuse interaction as you like hold on onto an object that is an exp interaction and so that would count and even with cardboard。

You can create immersive VR experiences。 don't of don't think of basic is just cardboard and immersive is some of these advanced headsets。

 No， you can put in the energy you do need and okay。

 smartphone for for the cardboard if you wanted to do something with particle systems。Yeah， and that。

 that would be。That would be required。 so you might be limited a little bit in in terms of hardware。

 and that's fine。 That's why a lot of these steps are actually optional。

 and just to show you what you could do to really make it an immersive VR experience。

And so I hope you learn a lot again， you can choose the tools so Webex are unity or unreal or all in for you to be used and you probably have made your choice as you did the 3D scene。

 but if you feel like hey， I want to try a different tool， maybe do that first， I wouldn't recommend。

 I mean if you want to complete this quickly， I wouldn't recommend trying out different topics or different 3D scene however。

 I must tell you that。My students in my residential class。

 they usually do everything with both the unity and A frame。

 and we are also going to add more stuff about Unal and my course。

And while it may be a little repetitive， I， from my perspective。

 see a lot of cool variety and when the same scene is done with the same tools。

 it's very interesting for me to see the differences。So I find that kind of parallel prototyping。

 I find that fascinating， you can really see the differences between some of these scenes。

In any case， it depends， obviously I'd like you to stick around and push yourselves and you know learn a lot more about VR than just making it quickly through the exercises。

But if you w to complete it this week， then keep it simple and treat it as a starting point。

 maybe something you can iterate on afterwards。 next module would be。

 So the next part of the honest track would be focused on AR already。

 I won't push you any further as part of the VR portion here。 but we're gonna look at AR as well。

 And that's gonna be interesting and challenging。 And but that should complete the picture that way you have a good overview。

 So good luck。And I look forward to seeing things submitted to the gallery in the forums。

 if you have questions here and there， don't hesitate to reach out。

 Also don't forget at the end there will be a peer review so。😊，You know。

 get these materials in shape， Think about what will you submit， I it the Is this the thing。

 Is this the ERRC and are you proud of it， Do you think youll get good feedback。Anyway。

 the tone will be fair and constructive and nice， I really want to make sure that you're getting good feedback and helpful feedback and so we want to be nice to each other so don't be too hard。

Don't go to hard on each other and yeah， so good luck。And I'll you in the， well。

 I'll see in the lectures again， but also in the next module of the honor track， hopefully。



![](img/d43d9b345fb1d6d5099257241773b71b_9.png)

![](img/d43d9b345fb1d6d5099257241773b71b_10.png)