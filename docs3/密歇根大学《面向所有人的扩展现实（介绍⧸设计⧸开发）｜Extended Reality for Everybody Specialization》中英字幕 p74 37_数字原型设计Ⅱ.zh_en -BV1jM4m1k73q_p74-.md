# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p74 37_数字原型设计Ⅱ.zh_en -BV1jM4m1k73q_p74-

![](img/ce57daaeebef3d06c38c69cbebc6b0b8_0.png)

![](img/ce57daaeebef3d06c38c69cbebc6b0b8_1.png)

Digital prototyping tool， we are still in the designing X experience segment。

 and I have talked about digital prototyping space already。

 where we're starting from digital authoring tools into immersive authoring tools where you work directly in AR or VR rather than on a desktop computer。

And then I say there is also web based development。

 cross platform development and native development。Which usually require programming。 And。

 but people who are experienced with these tools would still consider them at least portions of it as digital prototyping。

 So I want to talk about two specific tools here that we're actually using in this M mooc specialization。

A frame as the example of webbased development， which we are using is based on the Web XR standard。

 and aframe is really a tool that I want you to play a little bit around with。

 you may actually like it if you have a web dev or web design background。Unity is like unreal。

 a very powerful tool usually requires some time to actually learn it。

 Unity comes with an editor where you can do a lot of things just like clicking and playing。

 And they actually do have good documentation。😊，You can do quite a few things in unity without actually having to program。

 And so that's why I've selected these two tools as examples that still fall into what I would call digital prototyping for A and VR。

 So let's start with aframe。 Aram is based on 3Gs and WebGL。 This is the technology stack。

 that actually is important information to some people out there。

 what it means is like within the HTML 5 web standard。

 we actually have a new element that is called the canvas。

 That canvas is essentially like a graphics context that you can render 2D content into or 3D content。

 And when we talk about Web GL， we actually usually mean 3D content rendering 3D content into the web。

A frame also gives you a new set of HTML tags。 All of these tags actually start with a dash like a scene。

 a box， a cylinder， lots of tags that are then translated to specific entities。

 We call them entities in 3D， so you can actually create 3D scenes， but you're writing HTMLl code。

Ara has an inspector。 This is not an editor。 Keep that in mind。

 so it allows you to inspect the scene and look under the hood and find out where the light is and why this animation isn't working。

 for example， Aram has asset management。 in this case。

 you bring in typical resources from the web like images， videos and then also sounds。

 but then aframe also has set for asset 3D model loaders。

 and this is a good way of bringing in common 3D model file formats。😊。

And I list out two more features of aframe。 One is the ES architecture。

 ES stands for entity component system。 and that's something that we'll look into more detail later。

 It's really relevant for programming。 Just keep in mind for now that you will find lots of components out there。

 The ES， the entity components systems。 lots of open source components out there that you can plug into your aframe code They give you access to Vr controllers。

 they give you access to kinds of certain kinds of 3D models and certain behaviors。

 So it's a very plug and play kind of architecture。

 that's what I'd like you to think of aframe at the moment。 And it actually supports crossplatform。

 both AR and Vr。 So crossplatform X。😊，Here I have an example of a 360 photo that my former postdoc Max actually took in the lab and I can just like zoom into different areas of this photo。

 so it looks a little。More normal。There we have， for example。

 the clock and there we actually have some sketches we were working on Proto AR XDAR and 360 MR at the time and 360MR them was called 360 anywhere and these all became papers so if you look at this photo it is actually a 360 photo of the lab so you can see some of these distortions it is basically in accurate angular map and accurate angular format this photo was taken with the 360 camera。

 a theta V from Rico and it actually has two fish Islands and then it stitches at the end it stitches basically the photo together and I'm going to show you how we can use this photo for prototyping digitally with a frame and with unity。

Al here we have the aframe scene so I'm using the 360 photo from before and I'm mapping it onto the sky that allows me to basically look around already and then I'm also mapping it onto the sphere here as part of my example so I'm trying to create this virtual reality where there's this interesting curious looking sphere here and so the way I haveve done it is I've basically uploaded this photo that we took the 360 photo and I linked it as an asset so I'm using code pen here and it shows the code on the left basically the body of our HTML document and then I'm using aframe so to my a scene。

 link the asset to the sphere and define the sky in both cases I'm linking the lab。As a texture。

 so basically my 36 photo becomes a texture of both the sky and the background and then our 3D object here at the foreground。

The last thing I did was actually playing around with the material。

 so really making sure that this looks like interesting by playing a little bit around with the madness and the roughness so I can adjust actually some of these here and actually preview it immediately。

😊，In there and metalness and roughness is always something that I think as a concept it's clear。

 but what so basically they determine how metalness how metallic an object is and how rough it is and that then actually gives you a different kind of reflection here so the light will be reflected differently。

😊，So I understand that as a concept but it's really hard to really get it right and so before we so let's say I'm cool with this I'm going to preview this in VR quickly so I have my oculus rift as here I'm just going to put it on my head and so I'm working in Firefs and I can see a preview so I'm kind of happy with the composition of the scene。

 maybe that fear could be a little bit more at a different location but that's something we can fix later and I can also adjust other parameters in the inspector so I can just go in here into the scene。

😊，Edit my sphere a little bit， maybe give it a bit more space。

 so the code becomes less relevant right now because I'm using the inspector and I'm going to go to the material and play a little bit just with the Madness。

And then also with the roughness。There's a lot of things we can play around with。

Maybe I'm like happy with this and I'll leave it like that and go back to the scene and I could copy paste these values now into the document here on the left if I'm truly happy。

 but I can continue iterrating previewing in VR going through that whole process until I'm really happy with how things look in VR。

 and so I have a combination of digital and immersive prototyping here using aframe。😊。

So Unity has been out there for a while now。 it's actually growing out of the game development community。

 Unity was originally a game engine and it still is。

 but it has grown as a platform with significant support for XR， both AR and VR。😊，So as a result。

 Unity nowadays has integrated support from many X platforms。 For example，buhoria。

 which is a mark based AR library， is now actually part of unity and ships with unity。

 but you can also add lots of other SDKs into unity and there is increasing support inside unity built into unity so that you have to install less on top of unity。

One of the things that I particularly like about Unity is its powerful 3D scene editor。

 There's actually a lot of things you can do in this editor。

 you get immediate previews and I'll show you just the basics in a few seconds。

 but imagine that you can actually create real experiences and edit them in 3D on a laptop or a desktop。

 so you often get a sense of what it may look like。😊，In AR or VR。

 although most often you still need deploy to these devices to actually figure it out or use like an emulator。

 So Unity also provides increasing support for kinds of emulators and has asset management and actually an asset store。

 which is different from other tools I've talked about so far where you have to like one is the tool and the other is like you try to find 3D models on the web with unity。

 you actually do a lot through their assets store and you can actually download libraries and add packages to unity or find 3D models And like I said with aframe Unity basically supports all kinds of ARVr devices out there。

 many vendors。 If not all the vendors provide a unity SDK that you can download so you can develop against their platform and hardware using unity。



![](img/ce57daaeebef3d06c38c69cbebc6b0b8_3.png)

Alright and here we have the same scene in unity basically working with a few objects I have started out with the 360 photo imported it and created this sphere and then mapped that material map that photo onto the sphere and that generates this material Now this material I can play around with this a little bit more as I adjust some of the parameters like the metalness or this is more interesting this smoothness the smoothness gives this interesting effect of the light source being reflected so that's that light and we can actually rotate that to change a little bit where the light essentially hits this sphere and can create a more interesting looking effect this way Now one thing that I'm not exactly happy it is the position relative to the camera so I can either move the camera a little bit。

To the right or move the sphere a little bit to the left。

 which I think that's what I'm going to do I going to move it a little bit the to the left。

 So now if I press play we're using an X rig already so the camera has already been converted to the XR rig using unitys X plugin so I just press play and I have theocchius on my head。

The rift as I'm using here looking at the sphere， and I kind of like the position and it gives a relatively。

Good reflection of max， and it's just interesting where it's floating。

So I'm kind of happy with the result， and we also mapped that 360 photo。😊。

Also into the environment so we basically changed the rendering settings here so a couple of ways I could do this。

 but I chose to do it this way I basically replaced the normal skybox which is this one with our 360 photo and。

That gave me that effect。And。Well not a big effect。

 but one thing we could do is we could further edit this material as well so for example。

 if I'm not exactly happy with the current rotation I could rotate this a little bit differently so I can change。

The default rotation but then I would also need to adjust the settings on the sphere so basically also rotate rotate the sphere I could make it a little bit brighter if I wanted so maybe that's maybe that's cool and I'm going to trade it one last time in VR and start prototyping this way and I'm fairly happy with what it looks like now it's maybe a little overexposed so but that's fine we could continue play with this the point of this last part is that we can actually why we are prototyping。

For VR here using VR techniques and basically。You could be anywhere and then report you into the lab。

 you might as well be in the lab and we're actually prototyping effectively an AR scene and well you can do this while being in the lab。



![](img/ce57daaeebef3d06c38c69cbebc6b0b8_5.png)

Or you can do this anywhere based on a 360 photo that you previously took of the location and I think that is a very powerful way of prototyping XR applications very quickly and if you're good and skilled and unity which will dedicate a larger part of the development oriented course as part of this XMOC。

 we want to dedicate that to being better at unity essentially and you can create those prototypes very quickly and I consider the Unity editor a powerful tool for prototyping as well。



![](img/ce57daaeebef3d06c38c69cbebc6b0b8_7.png)

![](img/ce57daaeebef3d06c38c69cbebc6b0b8_8.png)