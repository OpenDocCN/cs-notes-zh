# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p103 19_VR界面导航设计第二部分.zh_en -BV1jM4m1k73q_p103-

![](img/f48cb12d635029e43f308a1ccad5ee2e_0.png)

![](img/f48cb12d635029e43f308a1ccad5ee2e_1.png)

So we have completed the menu part and now we're going look at navigation。 So navigation。

 I would say at the highest level， and that's something that I was taught by Mark Binghurst and actually 3D user interfaces book from Doug Bowman and colleagues is actually a nice and nice book。

 So at the highest level we can distinguish in terms of navigation。

 travel Travel is the motor component of the viewpoint motion。

 So the teleportation part and then wayfining， which is actually when the user makes decisions about where to go considering all the options。

 So it's a cognitive component of viewpoint decision making。😊。

We're actually gonna focus on travel okay I'm not going to talk about any of the psychological stuff wayfinding very interesting research in this space while I was at ETH Du。

 I was working with a group a little bit that was really looking at airport navigation through different kinds of virtual reality simulation and models That was very interesting but we don't talk about this we talk about just strictly travel here so travel we obviously have menus as a way to travel。

 We did this in the zoo extensively teleportation and that can be controller triggered or it can also be menu triggered but what I mean here is like there is a teleportation ray coming out of your controller and it shows you where you will land。

So that's what I mean by teleportation and then walking， obviously you can walk。

 I mean on a six degrees of freedom headset it's very good if it's with inside out trackingrek or if you have a dedicated area for an HTC vibe and really then you can walk within some of the lighthouse stations that you can set up。

😊，And there's obviously this idea of redirected walking and redirected walking adds a shift function。

 some kind of gain function that actually adds it propels this like mouse acceleration， if you will。

 while you're moving like this in space and maybe I mean most acceleration would work with acceleration。

 your most because it wouldn't be a one to month it would already be kind of like here And so we can apply this gain function idea also for redirected walking and that allows you to travel larger virtual distances in smaller physical spaces。

 that's one way to put it。 I'm going get back to this idea of redirected walking。

 It's not the focus of this lecture。 And it's very research。

 So we're going to look at it later when we talk about advanced techniques in the last week of this course。

😊，So let's focus on the ones in the middle of teleportation and walking。

 So I'm going to give you quite an extensive demo here on VR travel。😊。

And I want you to just watch this and learn。 I'm going through a few of the things and even including implementation。

 Allright， this is my virtual reality travel demo。 So I have a camera here。

 I'm not going to change the orientation。 I'm just going to change the position。

 So I'm basically going forward which decreases the Z。

 This is righthand coordinate system here in aframe。



![](img/f48cb12d635029e43f308a1ccad5ee2e_3.png)

And going backwards increases the Z。 Okay， so if I go back roughly to 0。If I now go to the left。

 it decreases the x。 if I go to the right， it increases the x。

I can also fly in this demo so I can take like 3 m above。

And I can also fly backwards to see the scene differently。

And I'm actually printing out the wel position， that's how I've configured it right now。

And that is because I also want to show you teleporting。

 so I'm going to go into VR now and there we are， so I'm going to get up actually so sitting seated I'm like 120 high it says。



![](img/f48cb12d635029e43f308a1ccad5ee2e_5.png)

But getting up， I'm actually at 164。And。So I'm making a little bit of a room here。

And I'm going to pick up the controllers。Just so that I have them。All right， so same deal right。

 me leaning in decreases the Z further， me stepping backwards。

 increases the Z and gives me a different perspective obviously the on the scene and then leaning to the left and leaning to the right。

 you get the deal and me squatting down actually changes the y2 by like1 meter and。Normal height。

 standing height for me is I don't know， apparently 165。Alright。

 and now I actually also have teleporting。 so if I teleport over there。

 it's going to change my X and a little bit my Z。 So not as much my Z because Z goes this way。

But if I go like diagonally like this， it's going to change my Z quite a bit。

 And now I can hop around in this world。And then have to turn around now。

 I'm going to go back to roughly where I was。 so you can see how the。Z changes。

And this is where we were initially， this is roughly our starting position is roughly here。

This is the teleport demo。And keep in mind that I'm printing out the world position。 the normally。

 this camera has a local position inside the rig。And I'm not showing the rig right now。

 and the rig is something that we actually take with us。 So as we teleport。

 we take we take the controllers with us and also the camera as well。 So we're wrapping around this。

Both the head and the controller。As part of the camera rig。

 I'm going to show you this quickly in the code。 I'm just going get out of a VR1 sec。



![](img/f48cb12d635029e43f308a1ccad5ee2e_7.png)

So we're going to go back into the code here。

![](img/f48cb12d635029e43f308a1ccad5ee2e_9.png)

Kind of re out the scenes， so it doesn't look that weird。And we are。Looking。

 this is what I was talking about。 So we're going go into the rig。 So the rig is defined down here。

The rig wraps around everything， and it has a head inside。 that's our camera。

And then the left and right controller。And if we didn't have the left and right controller。

Inside the rig， I'm going to show you this。 It's going to be very awkward。

 But this's the best way to actually demonstrate this。 If I now run it in VR。

She're going to do one sick。

![](img/f48cb12d635029e43f308a1ccad5ee2e_11.png)

Just putting the headset back on my head。you're now running it in VR。Everything is weird。

 the controllers actually stay where I am。But I'm like teleporting somewhere else， just the camera。

 and the controllers are still over there。 Okay， so that's why we need to have the rig so that we can actually take the controllers with us。



![](img/f48cb12d635029e43f308a1ccad5ee2e_13.png)

As we tele apart in VR。I hope that demonstrates this a little bit。

 I'm going to undo this change so that future users will not be confused。



![](img/f48cb12d635029e43f308a1ccad5ee2e_15.png)

And that。So this was my little aframe we are travel demo I had some fun putting this together and there is more of this kind of content so I share the code with you you see the link down there that code。

 especially if you're working in the honest track part of the effort here is actually to share a lot of examples with you that I've actually developed myself over the years as I was teaching Webex are in aframe so there's a lot of。

 I think useful snippets of code that when you plug it into your projects you can actually build at least students have done this in the past and my courses build really cool。

 adapt my code and build really cool experiences or use it as a starting point I mean obviously there did a lot more than just use my code So what I just showed you in this demo as a quick recap is I talked about this camera array okay so let's say we are picking on new location this is the teleportation array that I was talking about。

😊。

![](img/f48cb12d635029e43f308a1ccad5ee2e_17.png)

And then we have actually defined this rig around us。

 So this is the camera rig that includes your virtual cameras or the a camera or the camera entity in a frame。

 and unity would be a main camera or an X camera and in unreal a similar concept。

 Also the controllers a part of this rig。 So basically。

 it's an entity that contains the head with a camera and the left and the right hand controller。

 and now we are choosing our location and as we travel there。

 the rig actually moves and were teleporting over there， we're going over there。

 And that takes not only the camera there， but also the controller。

 So rather than just moving the camera。 we are actually moving the entire rig。 So as we travel。

 we also then take the controllers with us。 Otherwise， the controllers would， as I showed。

 it would just take where they are at the previous location。

 So it's important that we use this rig for travel inside the V scene。😊。

So my last example here that's going to be a cool one， I think is based on halflife Alex。

 So halflflife L is a really cool game。 I'm not going to play too much here。

 I went into a portion where it is safe to show something of this virtual world and I actually did have to clear the scene a little bit were a few let's say things in the way of my demonstration。

 So I cleared it up nicely and then I wanted to give you this Vr travel demo So what it shows is in the realm of teleportation walking and mens。

 it doesn't actually concern so much redirected walking。

 So it's really like an example of a combination of these techniques and some form that is redirected walking in there。

 but it's not really the traditional form。 So you actually see four different types of navigation or travel that are implemented there。

 blink shift continuous head and continuous hand。 That's what they call it。

 So blinking means you're beaming towards the target。 It's like。😊。

shifting is you're zooming towards the target， so the difference is that you are actually like you can see a little bit the virtual thats coming towards you and when you blink they actually for a tiny split second fade to black and then move you there and fade in again。

😊，So that's the difference between blink and shift。 and then there are two other interesting methods。

 I still haven't really figured out how to how to feel good about them。 So in one example。

 you will walk where you are pointing。 So if you're pointing this way。

 independent of where you're looking， that's where you'll be walking。

 And the other example is you're just using the controller to trigger with the thumbtick。

 but you are walking wherever you're looking。😊。

![](img/f48cb12d635029e43f308a1ccad5ee2e_19.png)

And so。Watch as I actually demonstrate this is actually quite a fun demo。😊。

So one of the things I find interesting in， in half life， Alex is how they。

How they've implemented different ways of actually walking。

So the typical way is some kind of teleportation， but that is kind of also cool because they figure out whether you can jump somewhere or not and then also visualize how you would land and this part is cool because it does some kind of checking。

Whether this is a legal move or not。Can also not go too far， and so have to go multiple times。

 Can go behind the fence， for example。But it could end up there and can explore a little bit。

 you can jump up there。And then that's it。 You're not supposed to go there。 Okay。

 so that's teleporting， and it's actually really well done。 So I'm going to show you blink movement。

 teleport to destinations with a brief screen fade， the most comfortable movement time。

Then I'm going to show you a shift movement， teleported destinations with a fast linear movement。

And I'm going to show you move con based on your head orientation。 That is the continuous movement。

So basically looking where you're going。 And then I'm going show you move continuously based on hand orientation。

 I'm going to show you。A different movement。The shift movement。It's still kind of teleparting。

But it it， it， it takes you there。 It doesn't fade out。 It just like warps you there， so。

This is still okay for me。 So I don't feel any emotion sickness。

 some people may already feel some motion sickness。So。

And I'm not sure what it looks like for you on camera， but probably。

You get a little bit sick when I do this too often。 So this is the shift movement。

 And then we have a different。We have continuous。 And so the idea is that I look where I want to go and I press the controller forward。

That allows you to explore the world， but it is because I'm not personally moving。 I mean。

 it gets a little bit better if I like do stuff like this， but it's actually。Creating some kind of。

Mo signals， effect， just for me， the prop exception is like weird。

 Like my body doesn't believe it's walking。And I don't even know which which direction Im looking。

 I'm still looking your way。 Okay， that's fine。So。But basically where you're looking is where you're going。

And。Im not sure it would be nice to know a little bit more of the statistics。

 I wonder how popular this movement style is when I watch people play this online。

 they actually do this quite a bit。 So in this last movement style you're moving where your hand is pointing so。

You're going to the left or to the right。And so you have a little bit of proper perception because the body is doing something。

 but we don't normally navigate this way。 so this is going forward， this is going backward。

 backwards。And it just， it feels a little bit like if you were a Superman。

Then maybe it would be cool， but it just like I don't think that this is a very popular style。

 So this was my overview of menus and navigation。 there's obviously a lot more to be to be learned about menus but navigation was。

 I think the travel techniques we covered at least the basics menus， it was a little abstract。

 I wanted to keep it conceptual there is a lot of evolution when it comes to menu design。

 It's like with a web。 it's like really evolving quickly。

 what are good ways of designing these virtual menus。

 but whatever you see come out over the next few years。

 it'll probably roughly fit into these four categories of fixedig had and then attached to some kind of body parts。

 So the controller or your a part of your hand like I put the menu relative to the risk I was tricking tracking as part of hand tracking that was just has just become available。

So I think overall conceptually we're like in a good shape now and while there might be specific and some really cool new menu designs in the future。

We have covered them here and you should be able to classify them at least。Thanks for watching。



![](img/f48cb12d635029e43f308a1ccad5ee2e_21.png)

![](img/f48cb12d635029e43f308a1ccad5ee2e_22.png)