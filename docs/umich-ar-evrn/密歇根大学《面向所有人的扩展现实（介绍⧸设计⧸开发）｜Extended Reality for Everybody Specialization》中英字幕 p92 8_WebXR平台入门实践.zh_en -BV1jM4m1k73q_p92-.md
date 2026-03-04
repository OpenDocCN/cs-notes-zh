# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p92 8_WebXR平台入门实践.zh_en -BV1jM4m1k73q_p92-

![](img/7a2f83583c2eb552671755264b5cf7e4_0.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_1.png)

In this video I'm going to provide an overview of aframe as the tool of choice to develop WebExR scenes I've already established what WebExR is and I've talked about aframe previously。

 but in the Excel development oriented lecture，But in this video。

 I really want to show you how you can use aframe to create VR and AR scenes。

 how to run them out of the browser on a desktop in a VR headset like the RiftS here that I'm going to use or actually deploy it to your phone and I'm going to use an AO core smartphone。

 so Aframe is based on 3GS and WebGL。And so 3JS is a popular graphics library。

 It's actually a webGl library on top of the web。 I've talked about this before。

 And so it allows aframe to render 3D scenes。 and so what aframe now does it actually introduces new H tag for 3 scenes。

 they all start with an a dash A scene a box， A a cylinder or a camera or a entity。

 it comes with an inspector。 I'm gonna to quickly talk about the inspector。

 You should not forget about the inspector。 It's not like an editor really like an unity or an unreal。

 but it's an inspector and it makes things a little easier and you can use it to explore different kinds of scene compositions and and then copy pastse the values into your code so that would be a way to go about it。

 Aframe has asset management So supports images， videos。

 audio and 3 models since it's webbased GLT3 models the preferred format。

 It does support OBj and MtL， but that's a little outdated and。

Other formats like FBX could be loaded with aframe extras comes with loaders。

 So 3Gs actually implements a variety of loaders and they can be exposed to to aframe and that's what the Aframe Xs。

 for example， does。 So library on top then it follows the ES architecture entity component system architecture So has many open source components we're gonna actually I'm gonna give you a little bit of an overview when we're talking about Vr and also AR I'm gonna introduce you to lots of little building blocks because I do think that if you choose the Webex R route。

 which I think is very cool。 you're gonna need more help finding these things。

 So I put all these things together。 if you choose unity Unre。

 there are lots of good resources out there it's very professional you won't need as much help when it comes to finding things So I'll focus my efforts on providing you help with the Webexr approach。

 It's also the approach that really like It's a crossplatform Xr approach。Good。

 so here's the hello world scene in aframe。 It's a hello web Vr。 I think they used to call it。

 I just call it hello world in aframe。 And here is what that scene looks like。

 So it's an a scene box via cylinder and plane。 here's the inspector that I mentioned。

 which I think is very， very useful。 it's not so powerful， but it's useful。

 so you can bring it up when you press in an aframe scene and you press control I。

 and I do this from time to time in in my instructions。

 and it has like these transform controls from 3Js。 So you can actually obviously move things around。

 translate so you can also rotate and scale。 And then you can manage components。

 And most of the editing you will do in editor like on code pen or a glitch。

 I suspect we're also going talk about those kinds of environments for setup。

 So these things cannot be stored directly。 it's an inspector。 just like a web web developer tools。😊。

In Chrome or Firefox are there are also inspectors you can export。

 you can save there's a safe save up there or copy paste to clipboard。 those things are are possible。

 but well， I think it takes a little bit of time to develop your workflow。

 but you have a lot of similar features to。A smaller subset。

 but those features are similar to the unitary and Un editor。

So I was talking about aframe development environment。

 So one thing we should consider is how are you going to work on these things and you see me use a combination of glitch or codepen or Github。

 So I would say glitch is really like you're going there you can launch an editor it's going to load and this case I've actually just like linked the aframe example and and I'm gonna do this in a bit。

 but you can just like show it next to the code and this is the scene and this is the text and you can then you know remakeix and take it from there。

 So it's pretty cool。 now codepen is very similar。 I mean in many ways。

 I would say there is a difference。 So important difference is with glitch you're actually really hosting things in in a well it's running its own node Gs server on virtually the projects。

😊。

![](img/7a2f83583c2eb552671755264b5cf7e4_3.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_4.png)

I have a mind for us not going to be that difficult the most difficult part is how do you host assets like what do you do there because these platforms have a little bit of restrictions but you can actually do a little bit of asset management there so I'll show you code pen very quickly so code pen here this is my aframe template and code pen I'm pretty active。



![](img/7a2f83583c2eb552671755264b5cf7e4_6.png)

Pro it says just means I pay for this。 so I can help my students。

 And so this is the aframem template we just saw before is the code on the left。

 that's a little bit of documentation。 I usually have that I actually have lots of examples on code pin So the profile here as my cute little winter scene。

 I don't think it works anymore。 Aram has updated recently。 So it looks good in this screenshot。

 but if if you open it it's probably gonna be sad。 I'm gonna show you the Star Trek one is one of the early ones that I've created the hamster。

 I'm gonna show you that a little bit。 let's look for example the Star Trek scene。

 So code pen it's like similar to glitch also has like an editor。 The focus here， I mean。

 it can change the view and all that。 I leave this up to you to figure these things out。

 it can do different layouts， move these things around and you can set up whether it should always update or not when you're typing heres a lot of things to play with but I suspect you will you。

😊。

![](img/7a2f83583c2eb552671755264b5cf7e4_8.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_9.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_10.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_11.png)

I have some fun coding here and GitHub， if you're a little pro， sure， why not。

 but then I can't help you。I mean， I could， but it's it's a little bit outco for this lecture。

 So Github， I just say custom。 Okay， so I wanted to talk about a frame and VR。

 So a frame development would be in one of those tools。 So I usually use code pen or glitch。

 whichs directly hosted。 allows me to go on a different device computer。

 whatever so would also work with AR。 It just go type in the URLs glitch is even a little better for code pen。

 you need to view the debug page in in the browser。 So that's something to keep in mind。

 then you're running it in a browser。 So a Webex are compatible browser， for example， on the desktop。

 So I will use Firefox in my example in the following。😊，And then you're using a VR device。

 so I'm going to use the as rift as that I have here next to me。 So I'm going jump in there。

 I'm going to spend like 10 minutes really going over all the the basics I'm gonna to use glitch。

 and my goal is to really get into VR。 So let's let's get started。

 so start here with the aframe website and we want to look at the hello by VR example。

 It is a scene that we will see a lot's the standard aframe scene And so well。

 it does seem a little different from normal webcon and now the whole thing seems to be draggable and that's correct because what you can actually do here is we can drag the camera So this is controlled this is look controls。

 and these look controls allow us to take a different perspective on the scene。

 Were actually rendering the perspective from a perspective camera。

 something I'll talk about in later segments。

![](img/7a2f83583c2eb552671755264b5cf7e4_13.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_14.png)

Well， and the other thing we can do is fly around this scene。

 I say fly around and actually is more like walking around in this case， flying is not enabled。

 but we can use W S。To go forward and backward so we can use W A SD to actually navigate around and we combine it with the mouse。

 we can actually fly around or walk around， as I said。And take a look at the scene。

 There's nothing else in the scene。 It's really just these basic 3D objects。 you might think。

 but there's something。That is obviously quite fundamental to the scene。And that is the light。

 So we do have shadow here。 and so let's inspect this scene a little bit。With the visual inspector。

 you can do this right on this aframe IO website so you can go into the visual inspector you can press control Alt I。

 at least on Windows computers and so I can now use my mouse wheel and drag with the right mouse and then drag with the left mouse that changes rotation drag with the right mouse that changes basically the position of the camera and the mouse wheel gives me control over the Z axis of the camera Now this camera though is actually not the camera of the scene the camera of the scene is here so we can actually draw that。

In and so we can see this is the camera of the scene。

 One thing I'm going to do is this is an inspector， but it's also a little bit of an editor。

 so I'm going to change the background color here to black so we can inspect this scene a little bit better。

Okay。So as I ahead heres the camera。 And you can see how it's looking at the scene。

 and we can actually change the position of the camera。

 We could go further back and a little higher and maybe a little bit to the left。

 So I'm now changing the。coordinateords here through the gizmos that we have。

But we can also do this over here so I can drag left or right as I start。

 I need to start clicking while I'm in the field。 So I'm gonna do it for Y up。Down up。Town。

 so you can practice this a little bit。 And then Z， Z is never really clear how to move the mouse。

 It's always inverse of what you would believe should happen。

 So smaller coordinates means actually further into the scene。 So further away from the camera。

 you might say。And we were just moving the camera。 So in this case， that's just how it is。 Allright。

 we can also change a little bit the rotation。Now， rotation doesn't actually have an effect when you look at the scene because。

We have look controls enabled。On this。On this camera。 So we would need to disable it。



![](img/7a2f83583c2eb552671755264b5cf7e4_16.png)

In order to be able to do what I had in mind。 So now if you go back into the scene， you see。

 you get a slightly different angle onto the camera and。



![](img/7a2f83583c2eb552671755264b5cf7e4_18.png)

So I'm going to rotate again a little bit differently。

And so now we would be looking more to the left。 And I'm going to look another down as well。

 So now if we're going back to the scene， we would look down and so。



![](img/7a2f83583c2eb552671755264b5cf7e4_20.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_21.png)

But we want the user to have control over the camera so we can just ignore the rotation。

 we can just set it back to 00，0 the way it was。And the camera is usually at 01。 sorry，1。

6 and 0 is a normal camera position。 This is where you are initially1。6 on the Y axis is used know。

 it's the standard height of a user 1。6 m So that's just like how it is。 So I said there is oops。

 I wish they were an easy way to undo。 but we just like set rotation back to0。 I didn't want that。

 So now we're gonna actually go into lights。 So one thing you notice here is that there is a light that I have opened。

 It is actually an ambient light。 We can show you the type。



![](img/7a2f83583c2eb552671755264b5cf7e4_23.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_24.png)

So ambient light really doesn't do much other than like giving this scene a little bit of a light and it's independent where that position of the light is it doesn't matter。

 but the intensity matters so we can change the intensity。

 you can see how the scene brightens up a little bit there， can go a little bit inside here。And。

Were down and it's pretty dark。There is still an additional light。

 which is why you can actually see something even at zero intensity and that additional light is a directional light。

 So now that is the light that is responsible for casting the shadows。

 and you can see this as I'm adjusting the light position a little bit。😊，Now。

 I'm dragging the camera rather than the light， so。Let me drag this position a little bit。

You can see how it changes， how it casts the shadow differently， So that's all pretty cool。

And so that's a quick overview of aframe and we just changed it。

 So in I'm kind of using the Chrome browser and then Chrome we don't actually have support for a VR yet。

 so that VR button is just going give us a full screen view So if you if you don't actually have it running correctly later in exercises if it doesn't go into VR。

 then obviously either your VR headset is not connected properly or not you're not using Firefox。

 So I'm going quit this one。 I'm going to go into Firefox， I have Firefox here as well。

 So I'm going to go into Firefox。

![](img/7a2f83583c2eb552671755264b5cf7e4_26.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_27.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_28.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_29.png)

And this is the original scene。 So this is the same scene and in Firefox。And now here in Firefox。

 what I'm going to do is so we're going to go into the screen here。 I'm going to press VR。 And now。

 as I put down my headset。It is beautiful。 you can see a render for H eye and I was just checking what you are seeing it's pretty cool。

 Now， this scene doesn't actually support controllers yet。 we， we'll add support for all that later。

 but it is cool。 We are in a web browser， we are actually looking at web content。

 And then when that web content actually embeds VR content。 we can we can seamlessly switch to it。

 Now that is pretty cool。 and its a puts us into a unique position where we can actually mix traditional 2D web design and web development with advanced。

 I would say A VR content creation。 So that was me giving a little bit of an overview of aframe and VR portions of it and using the rift S that I have here。

 So that's VR okay and now we're gonna do AR。 So what does it look like for。😊，So。

So I'm going show you here we have a frame development environment as before。

 and then you're switching actually to mobile so you cannot use it on the same desktop， same browser。

 You actually have to run it in in AR unless you're doing a marka based AR then you can actually run it with a webcam on a desktop。

 I'm gonna just jump right into the demo and I'll see you afterwards with a few concluding remarks。

 And so what I've done now is I'm actually like in Firefox。

 So I have both the source and the scene there。

![](img/7a2f83583c2eb552671755264b5cf7e4_31.png)

And。So I'm going to change this to。We're going to start making some changes here。So zero。

 so this is now black， right， So if we're going to get this notification here every time。

 so I'm just going to accept， yes， we can run this in VR and I'm going to accept it for this site。



![](img/7a2f83583c2eb552671755264b5cf7e4_33.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_34.png)

And so then so this kind of like editing and switching back and forth is maybe not ideal。

 So let's say we're going to do a series of smaller edits。

 So what I'm going to do is actually I'm going to have this next to my code here。And。

We're going to hide this on the left， so now we have a little bit more space。

And so we're going to do not too many changes， I would say。

 We're going to give it a little bit more of。诶。Different color。 I like sky blue。

 Sky blue is a nice color。 And now what we're gonna do is we're gonna change a little bit the position。

 So we have。X， Y and Z here， so we're going to go down a little bit on the y。

 so we're going to create a little bit of a distance here。Between the objects， okay？

And then we're going move out that cube a little bit。 So moving out that cube means we're increasing。

 we're decreasing the x even more。 So let's say to-1。5。

 So now it moves out a little bit more and the cylinder。

 we're going move a little bit more to the right。 So the yellow cylinder。 So we're just gonna 1。5。

 So now it looks like we are splitting a little bit the scene。And therefore。

 what we're gonna do is on the sphere。 We're gonna do both a little bit up。 So just 2。50。25 up。

 That didn't change too much。 Let's do。1，7，5。 So it's definitely a bit more visible。

 not too much still。 So let's just go a whole point up， okay。

And we're also gonna go a little bit more backwards。

 So it looked like we were spreading out these elements a little bit。 Obviously， the perception。

 the perception differences in terms of when， when you change depth not so。

 not so high unless you really make a significant change。 Now it's really far away。 Okay。

 so I didn't want that， I'm just gonna bring it back and you see the updates here on the right the whole time here。

 we're gonna basically just press our via button。 I'm not looking at the scene。😊，And it's quite cool。

 It looks like， wow， it has changed quite a bit。 Now。

 the shadow from the sphere is more or less gone。😊，So， that's a。

That's just because the plane isn't long enough。And we can inspect why that is a little bit。

 So I'm going to quickly reload so that。I actually escape here， not reload。 Reloading。

 Reloading is actually hot。 Now， that is， that is the cool thing。

 Let me show you this while I am in VR。 So I'm gonna quickly jump back into the headset。😊。

So if we now make changes， let's say we're still finding。

 we're still trying to find the right color for the background。

 I'm just gonna make this a different blue。 I can see this right in the headset。

 And so that is just just really powerful。 The last thing I wanted to show is what this would look like in AR now。

 So for AR， we can leave the background， let's say we we' give gonna give it a green。

 and I'm gonna escape here。 So what does this， what do I mean by this screen。 So this。

 all you see in this green is like our green screen now。

 And this will actually be replaced by the camera feed。 I press this。😊。



![](img/7a2f83583c2eb552671755264b5cf7e4_36.png)

In new window， I get this domain this URL here。 So， and there is our scene in AR。

 So here we're going to explore it a little bit more。



![](img/7a2f83583c2eb552671755264b5cf7e4_38.png)

And。Now it seems weird， right， It's like why is this not？Reacting like it should。

 You're going closer， and it seems so。So weird， it seems to be floating。

And this has to do with the simple fact that our dimensions are。Really， really big。

 So that we are talking about these objects being 5 m away。 And thats。

 that really breaks the illusion。So one way to do this would be we change all the positions。Here。

 and then the scale and all that。 But what I'm actually going to do is we're gonna grab this into an entity。

This whole thing is going be into a different entity。 And I'm just gonna。

Show you a quickly how this works。 And let we just going to scale this down to really， like， small。

Okay， now that's now baby size ish。So it's one fourth of the dimension， so it means。

Because some things are up to 5 m away。 One fourth of that is actually then still a meter away。 And。

 well， we're gonna make it even smaller than let's do 15%。So every distance， every size is now 15%。

Which also means it's actually more like on the floor。So we're going bring that entity up to。

 let's say， a comfortable height， so 1。2 meters floating in front of us it reallys it didn't change too much in this 360 view but now when we go into AR things should appear a little bit smaller and now it feels like oh this is so cool we can explore it we can get closer to it。

 these objects still appear pretty big but that's because they are now so much closer they were a little bit of tracking issues for a sec。

😊。

![](img/7a2f83583c2eb552671755264b5cf7e4_40.png)

But it does look pretty cool。 And now we are looking at our a frame scene。😊，Basically， live。

 All right， So this was our little。A frame demo， we've covered a lot of ground。

 and we're gonna to explore aframe quite a bit throughout this MOOocC。

 I think it's quite an accessible way for us。 and it is easy。

 easier for us to learn about ARVR if we already have a little bit of web design。

 web development background。 I'm also going to cover unity and unreal。

 And so we're going to learn quite a bit on actually doing ARVR。 and in this case， development。

 so really。😊，What some people might call programming。 Okay， so don't be scared。ll， it'll be fine。

 We'll， we'll figure it out。

![](img/7a2f83583c2eb552671755264b5cf7e4_42.png)