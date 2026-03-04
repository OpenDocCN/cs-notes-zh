# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p91 7_从2D到3D的跨越第二部分.zh_en -BV1jM4m1k73q_p91-

![](img/8b47a3409ba841a697d59134e048b11d_0.png)

![](img/8b47a3409ba841a697d59134e048b11d_1.png)

So I'm now entering the second portion of this lecture more or less。

 I want to talk more about 3D models and also a little bit more about materials and what it really takes to make things appear in 3D and then later in VR and AR scale is pretty important you will see this throughout it comes back to us。

 it haunts us。The scale of 3D models and pivot points and all those kinds of things to control their orientation and that's just something that always causes issues for my students so hopefully we can prevent those if I tell you about those issues early。

So here we go， 3D primitives。 So here's an example。That is just the standard a frame scene you see a。

Box， ace sphere and a cylinder。And what we can do as we're entering a little bit more 3D modeling。

 one way to do 3D modeling is a constructive solid geometry。😊。

And obviously you can still see this sphere here， but I'm using this sphere to cut out a well。

 a spherical shape out of the box and the cylinder。

 and if you do this a lot of times in different interesting ways， you can actually do3 modeling。😊。

So I think as an AIVR developer， it would be great if you had the skills of a 3D artist。

 but I think a lot of us don't and we actually we need to understand though how 3D models work。

 so 3D models consist of geometry， mesh and skin， so this would include the vertex positions the normals。

 so orientation， the faces， the texture coordinates。😊，So this is let's say the layout okay。

 and then the design， let's say that's the material okay you have a shader that renders it and can apply different effects can also be used for post processing there's a lot of cool stuff going on there and then we have bump normal and other kinds of maps or environmental maps these can be applied to the 3D models in order to not have too many additional vertices。

And still give it a detail， it's a simulation of detail like a bump map。

So textures are the other thing， right， so these are the image sprites that are attached or like wrapped around the 3D models。

And then you can find 3D models online that are rigged。

 so they have a skeleton inside and they are animated。 So for that。

 the rig consists of bones and then the animations of poses and keyframes most of the time you will have to deal with different kinds of 3D file formats when you're working with 3D models。

 So GlTf is really the common kind of like a standard format on the web So keep that in mind when you work with unT。

 however， it's FBx。 and then we have Qadada or digital acid exchange DE as a still popular file format。

 you will see export to Qada or DE quite a bit and then OBJ and MTL material is kind of very early on file format is still popular kind of like most tools well be able to export to OBj。

 but then the material needs to be exported separately as an MTL and then the textures come usually in JP。

G so you actually then have like three kinds of things you have to keep track of GLTFs can be packaged into GLB files that's something that I often do for my aframe examples it's pretty cool so I'm already bring it here into an aframe scene so we have the bunny in there and if you're using a prospective camera the one that I introduced earlier to you we can rotate we can use look controls and rotate and beginning this camera for free in aframe So if we wanted to bring in multiple 3D models here is an example we have the bunnies still there this as a hamster and I didn't create this hamster this hamster actually I found on sketchtfab and it's been a regular visitor to my lectures rather Laina created this and share it as public domain So finding and creating 3D models I would say should always try to find。



![](img/8b47a3409ba841a697d59134e048b11d_3.png)

3D models unless you are a 3D artist and you are good with modeling。

 so places to find 3D models include Skettb， Google Poly。SketchU 3D warehouse。

 Clara AO and Adobe Mcamo， That's where Elvis is from。

 I'm going to show you Adobe Mimo and Sketch Fab。And programs to create three models。

 which are out of scope for this course are blender， Tkercade， Maya，3D Mac。

 Cma4 D and lots of other ones here， I'm going to show you the hamster。



![](img/8b47a3409ba841a697d59134e048b11d_5.png)

![](img/8b47a3409ba841a697d59134e048b11d_6.png)

This is a little video on understanding 3D models。 So we're gonna zoom into this hamster。

 And so it comes with animations。 Actually， what we're looking at right now is a sketcht fab model。

 So it's hosted on the Sketch fab platform。 It can be downloaded。In different ways。

And it was created by La Ruina。 So at least that is the name is's up there。

 It's obviously available under the Creative Commons。

 So let's look at how this hamster is actually done internally。 So first， I'm showing you the rig。

 It's pretty interesting。 So these are the bones in there to get this guy to walk and animate。

 And here I'm showing the hamster as it is embedded。

 So exported from Sketch forb and then uploaded and hosted and embedded in an a frame scene。

 And I call this the hamster。And I gave it a little bit。

 I put on a path and walk around a little bit。 And， and here I shown an example of Adobe Mczemo。

 an example for animating 3D models。And here I have bigvegas and I'm looking for the animation that lets him fly。

 I want him to fly across the city。 I want to turn him into a little bit of a Superman。

 But before that I'm going to show you obviously， lots of really important other animations are available to us。

 dancing，Different kinds of dancing。 And so Zmo is really a tool that allows you to apply different kinds of animations to an available set of characters。

And so you can preview some of these animations。And then you can actually adjust and control various parameters for each of these so this is him jumping down and here it is finally。

 we have him flying， I was really looking for this one and it is fun， it was super cool。

And I like some of the parameters you have， you can change his awareness so he really looks more around so Exmo is a tool I would invite you to play with and I've seen some of my students create really cool scenes this way if your main goal is to all you want to do is just view 3D models and then I can point you to model viewer。

You don't have to go through all the effort of doing aframe your unity or whatnot。

 So model viewer is a pretty customizable jascript library and lots of things you can do and configure。

 but the example that I wanted to focus on is the one with WebexR。

 So the model viewer can actually be run on the phone as I show here。

 and they have a Webexr demo and I think that's a pretty cool one。

 so you can preview different furniture。 It's based on a Shopify example contributed to model viewer。

And you can bring in a chair like this into the 3D space to do a little bit of the initial tracking by moving a phone around。

 letting the phone read the demeter of the room。do plane detection。 And there we go。

 We have it in the room， and you can customize it a little bit， at least change the。

The scale of the objects and bring in different kinds of objects like this model terrain。

So that was a lot of 3D stuff。 I said making the jump from 2D to 3D。

 and I showed along the way was actually 360。 I think 360 can be very powerful。

 especially for prototyping。 a 3D scenes。 And then especially for VR。

 I think it' it's a very good way to do things。 So I wanted to show you a little bit。

 I wanted to explore a little bit with you how to go from 360 to 3D。 So if you have a 360 camera。

 like the one that I'm using here。 Then you can take a picture。

 a photo of a 360 photo to be precise of my lab， for example， This one is the one that Max took And。

😊，Then it can be， this is an inquiryry。This is an e rec angular format。

 so you can see some of these distortions， but then it's kind of like has two fish islandss the cameras or one fish islands。

 the other fish are ends and then stitched。On the side can be stitched together so you can actually wrap it around the sphere。

 render it from the inside of that sphere。 And then so the the back side， if you will。

 And that would then give you this little planet view。 Here's an example of that photo。

 this 360 photo in a frame。 So now we can actually look around。 Hey， Max， how's it going。

And could then also go into VR using that button。In the right browser。

 And here is a version of my lab that is actually based on a 3D model。

 And so I'm going to open this as well in the browser in aframe and now we can look around and well it doesn't log exactly the same。

 Obviously this is a simpler 3D model but we can walk around and we can adjust our perspective。

 That's something that you cannot do in a 360 photo without very weird distortions。

 So this is how you would enter my lab and then I have a number of screens on the walls and lots of equipment in here that we haven't modeled and so this is a 3D version of the lab。

 Now I wanted us to compare 3D and 360。 Okay so characteristics of 3D on the lab。

 So 3 objects have with height and depth that's very important。



![](img/8b47a3409ba841a697d59134e048b11d_8.png)

![](img/8b47a3409ba841a697d59134e048b11d_9.png)

3 objects are positioned along X， Y and Z Xs and three objects react to light cast shadows and actually can be interactive。

 Now， 360 is not 3D。 okay it's actually represented in 2D there's a projection function that projects it from angler to spherical format and then if you map that then onto the sphere then it gives you this illusion of depth。

 but there is no depth。 So 360 has no depth， meaning you can't really walk inside and 360 photos and videos are quite immersive。

 I would say and can be interactive。 you can do that by bringing in some kind of like image maps。

 if you will， for 360 so defining areas in there that arecticable a lot of tools do that like Google tool creator is one of those that where you can do these kinds of things so。



![](img/8b47a3409ba841a697d59134e048b11d_11.png)

360 isn't really a focus of this course， but I wanted to show you a comparison here that's going to just jump right in there。



![](img/8b47a3409ba841a697d59134e048b11d_13.png)

And here is a 360 photo in the background。 and I have the lab model on top， at least to some extent。

 really hard to get these perspectives to really map， so screen to screen。

Wdow to window couldn't do that， but what I can show you is when I walk inside that 360 s sphere。

 I'm turning it into this tiny planet view and because we don't have depth but inside this room I can really comfortably walk to the window to that window and because we have a perspective camera it actually adjusts the perspective nicely so thanks Max for helping us give this little demo showing the differences between 360 and 3D。



![](img/8b47a3409ba841a697d59134e048b11d_15.png)

![](img/8b47a3409ba841a697d59134e048b11d_16.png)

So let's go back to the slides and。This is actually where I wanted us to be， so right on time。

And pretty longer than some of the other extras， but quite fundamental。

 So what you should keep in mind is that 2D layout and 3D geometry thats that's the terms that we should use。

 So when it comes to transforms， that's the term we use to control position。

 rotation and scale of objects in both 2D and 3D。😊。

And left versus righthand coordinate systems I talked about this。

 I think we need a little bit more time to really notice and fully realize the differences。

 That's cool。 2D design versus 3D material， right So languagewise materials enhancements of texture mapping。

 So really actually a lot more to learn about materials。 I didn't go very deep here。

 if you're really into creating really nice virtual reality scenes。

 there's so much more to be learned about， for example， physically based rendering。😊。

And 3D models versus 360 photos。 Who wins。 Well， the 3D models when it comes to depth in detail。

 but 360 photos can help you really quickly prototype you don't have to be a 3D artist。

 lots of ways to get 3D models。 I covered a few platforms that you can download from Sketchab。

 for example， and at O example，360 photos are really great placeholder for 3D models of the environment。

 and so before you start modeling the lab like we did， I would just do a 360 photo。

 and you could see how quickly this allows you to approximate roughly the 3D space that you have available。

 But again， 360 photos are essentially 2D representations and they don't actually have depth。😊。



![](img/8b47a3409ba841a697d59134e048b11d_18.png)

So。I hope this was a useful lecture。 hope we made this jump from 20 to 3D together and you're starting to feel a bit more confident。

 join the honest track and play around with some of the exercise I have for you there where you're building a 3D scene based on whatever you feel like you can recreate your favorite movie scene or book scene that you had in mind in your imagination and you can actually play a bit around with 3D in Web Xr or unity of an aframe or unity or unreal even And I think this would be a great starting point so that we can then learn more about VR and then AR in the following weeks。

 So I hope this set us up and set us on a good path to exploring more about these interesting worlds AR and VR。

😊。

![](img/8b47a3409ba841a697d59134e048b11d_20.png)