# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p104 20_VR对象选择与操作第一部分.zh_en -BV1jM4m1k73q_p104-

![](img/27128c0cb66e91a5f53fc90bf40be04e_0.png)

![](img/27128c0cb66e91a5f53fc90bf40be04e_1.png)

Welcome to this lecture on object selection and manipulation。 So in virtual reality。

 So that's what we're gonna to do。 I have the controller here。

 and I thought this would be a good way to illustrate what we're going to be talking about So let's say there's some virtual content in front of me and how do I actually like select select it。

 So do I want to reach through I it enough to point at it do I have a laser pointer coming out So these are some of the things well talk about。

 And then object manipulation is let's say there's a virtual cube in front of me。

 How can I pick it up。 What can I do with it， like do I grab it， can I like rotate it。

 Can I use a second controller to for example， scale it。

 So these are some of the kind of like it's like pitch to zoom just with controllers So how do we enable this。

 What are good interaction techniques for that。 And I'm just going introduce you to very basic ones here。

 There's much more to we learned about we want to be able to select things in VR and we want to be able to manipulate the virtual world and that actually both of these。

😊，Really increase the immersion， like enabling your users to be able to do something with the content。

It actually increases this feeling of presence of being there and immersion as well。

 So here is our example。 the zoo， you've seen it before。 it's our case study。

 it's our virtual reality case study。 I have broad back one of the menu items so it's similar to the previous scene for that extra focused on menus and navigation and virtual reality now just want to focus on really this idea of selecting objects。

 What you see here is actually me pointing at these objects and I added collliiders around them actually visualizing it's like a debug feature for the physics so that I used to illustrate that these are all active areas and as my ray caster like the laser that is coming out。

 I'm using aframe laser controls here coming out of my controller as the ray hits it we can detect this and this is hit testing。

😊，And then we have like a little bit of interaction here， I mean just using the torch。

 but what we could do is actually have each of these animals play a sound or something as you point at them or change their visual appearance。

 like have them look at you， trigger some kind of animations in these models so we could do a lot more advanced things obviously but each of these would take some time and we focused our energy elsewhere。

So you can see how it works with the array casting and how I can hit some objects so the ray doesn't seem to go through them and then other objects just like the ray just shoot right through them。

 the objects don't seem to care and that has to do with collliers So this idea of really telling the virtual reality Well the system behind it which of these objects we should test we should check for hit testing should we do this against all objects in the scene that could be computationally quite expensive。

And so that's something to pay attention to。 If you wanted some of you could make this a little bit more expive。

 right， some of these animals could react and others could just don't care or something so you could play around with this。

 theres specific techniques。 If you want to build on our zoo in your own examples。

 that project is actually also available and we can actually also use it So have like I have examples where just have one of the characters like this giraffe and then we also have this entire zoo。

 I also have all the steps of this project available。 It is our case study。

 So as part of the honest track， we will be looking at this a little bit more。

 now comes the coup part。

![](img/27128c0cb66e91a5f53fc90bf40be04e_3.png)

The petting zoo。 So I should say one important thing here。 I said it's modeled after the Detroit Zoo。

 but this is completely fictional。 So virtual reality。 In fact， the Detroit zoo has very high values。

 and feeding is actually not an option。Animal welfare。

 you talk to them and animal welfare is obviously the number one priority。

 So this would this is one of the reasons why virtual reality is cool because we can do things。

 but I don't want us to suggest that the Detroit zoo would have a petting area or a feeding area。

 anyway， let's focus on what's going on here as a technological case study。So I have to find coiders。

 You can see them they are visible now around the banana， pretty big banana， and I can pick it up。

 and we can detect collision between them。 The coiders are actually box shape。

 They are not very good approximations of this banana。

And so we could do that a little bit better with mesh colidos and unity， for example。

 But in in Webex are， well， theres actually， there are ways you can， you can configure it。

 but it's a little bit harder。Yeah， so I'm just making the point here that when we throw things over there。

 we have physics。 so you could see how we determine the velocity of the objects based on previous basic frames and how the controller moved in each of these frames。

 So we're building velocity we're building speed。 and then we continue animating the object even when the controller release it it so that gives the sense of you throwing that object。

 But then because it has physics， it needs to land on something。

 And so we put a virtual plane underneath so that these objects don't fall into like into whatever is down there otherwise。

 it's endless actually。So that's important， so physics and combining physics with object manipulation actually makes some really realistic virtual reality experiences。

Lots of cool examples， and I think I would always consider adding physics to an experience like this。

 otherwise the objects would just be floating in the air。And and that's good， for example。

 for prototyping and kind of sketching activities。 that makes sense you don't want everything to drop。

 You actually want a sketch mid air。 but for our zoo， we wanted it to be a little bit more realistic。

😊，So I think I've covered most of it。 There's an original video where I really do talk through all the aspects of the zoo。

 but I want to move on in our lecture。 and I want to talk about virtual reality interactions。

 we have a broad range of interactions。 If you really zoom out at the highest level。

 we can distinguish between travel。 So that's a form of an interaction in VR。

 And that can happen explicitly and implicitly， we have object selection。

 So picking objects in the world。 And we have object manipulation。

 So modifying objects manipulating them in the virtual world。😊。

And we're going to focus on the latter too， because previously in the lecture focused on navigation。

 And many as we talked extensively about travel。 So let's focus on object selection and object manipulation。

So when it comes to object selection， we can distinguish between far selection and near selection。

 Actually， these apply both to manipulation as well。

 but I'm just going to focus on the first step before we manipulate anything we need to select it。

 Okay so let's think about it this way。 And so for far selection or manipulation later on。

 we use ray casting and hit testing for object selection。

 I'm going demonstrate this in a video and for near， we have to do a little bit differently。

 So we actually define coiders around， for example。

 the virtual reality controller or your hands for a hand trackingbased examples。😊。

And as you kind of like collide， so you're like intersecting in a virtual object。

 that's when we do collision detection and that's when we then trigger the selection。 So yeah。

 I show a raycaster example。 This is the typical raycaster coming out of a controller for example。

 and as we intersect with that cube。 we would could render it differently change the appearance gives and visual feedback。

So basically we could do continuous hit testing and I'll visualize this on this plane。

Me pointing somewhere on this plane， we do continuously find the intersection point。

And so for example， as the user then like triggers， clicks the controller or taps the screen。

 and we could find that intersection point so tapping the screen in AR。

 this gray surface could be a detected plane from the environment and then we would place an object。

 for example， at this。Intersection point。So that was ray casting and hit testing so the combination of again。

 let me use the controller like shooting a array into the world and then determining which of the objects it hits and we actually really get the intersection point and that's where I've spawned that sphere and so that can be very useful for all kinds of applications including travel but really if you just want to figure out which of the menu items you。

 for example select that's also the same technique。So we're going to look at collision detection。

 So ray casting and hit testing is what we do for far manipulation or far selection and for near selection and near manipulation。

 we really have to approach it differently。 So we're doing collision detection。 Allright。

 so here we have an example with coiders。I show the coiders around the hands。

And so I also show colliders around the plane down there and also the box。

 and so now I'm going to teleport over to the box to show you a little bit of an example。

 So as I reach into this box you can see I'll reach into the box we actually detect that kind of collision so there is a spherepher collider around the hand。

 so it's not like the actual fingertips or anything like that， it's actually a bit more sensitive。

 and as those collliiders collide。We detect a hover， essentially。

And so then I can start interacting with the object。

 I've kind of like hovered it so I've selected it and so that works with either hand or both hands。

 and I'll render a little bit of visual feedback。 So the colider of the box you can see a little bit maybe now it's a little bit better。

 you can see the outline there and also this is obviously an object that is standing on as surface right now So we have physics for that as well。



![](img/27128c0cb66e91a5f53fc90bf40be04e_5.png)

![](img/27128c0cb66e91a5f53fc90bf40be04e_6.png)

![](img/27128c0cb66e91a5f53fc90bf40be04e_7.png)

So the two main building blocks Okay we have raycasting for far selection and we do collision detections so really defining coliiders around well our hands or the controller in this example I was using a virtual reality controller but I was showing a hand model and so we define a colllider around it as it enters a virtual object we can detect this and yeah so there are this idea of collliiders is really。

 really fundamental when it comes to implementation so in both actually in all these systems So in Webex are which is aframebased which is 3JS based for all the interactions you define colliders per default we have box in sphere collliers there's also this idea of an AABB colider and that's the one that was using here so that's something that you could use in aframe and yeah there's also this super hands library which then defines all of this stuff and that's my example in the collision detection。

I was using super hands， and that's for VR collision detection。 It's pretty cool。

 And you have a number of options there。 you can actually really manipulate the scene then。

 So that's when we're going to look at next manipulation。



![](img/27128c0cb66e91a5f53fc90bf40be04e_9.png)