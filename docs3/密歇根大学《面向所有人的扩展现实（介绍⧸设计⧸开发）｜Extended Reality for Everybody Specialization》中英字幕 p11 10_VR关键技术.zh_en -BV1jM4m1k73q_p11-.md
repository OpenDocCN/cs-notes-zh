# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p11 10_VR关键技术.zh_en -BV1jM4m1k73q_p11-

![](img/86580ea11bf31deae5c165a75914432d_0.png)

![](img/86580ea11bf31deae5c165a75914432d_1.png)

In this segment， we're gonna look at virtual reality technologies。 Now。

 there is a lot of technologies out there。 and what I want to do in this segment is actually look at some of the key ingredients。

 So what does it take to create this immersion， this feeling of presence。

 some of the concepts we talked about earlier， So what does it take in terms of technologies。😊。

So we are going to look at virtual reality technologies and a few of the enabling ones from 360 photos and videos to steeroscopic displays。

 a rendering for HI， we are also going to look at caves or a cave。

 which is in a recursive acronym for a cave automatic virtual environment。

We're going to learn about three degrees of freedom versus6 degrees of tracking or three do versus6 of。

 We're going to learn about outside in and inside out tracking the idea of putting sensors into the environment and actually embedding these sensors into the devices that we put on our body。

We're going to learn about hand tracking， as I think that hand tracking is a technology that is rapidly improving and now becoming standard in a lot of VR devices。

Finally， so not to just keep it entirely visual， I thought it is also important to incorporate spatial audio。

Alright， so now let's look at these in a little bit more detail。

 So what you can see here is that in this 360 video， I have agency。

 I have control because it was recorded in 360。 It was captured all around the camera， and I can。

 I can choose to look at Michael or。😊，Not next， we're gonna look at stereoscopic displays。

 So the concept of rendering a different view， a slightly different view for each eye。

 Theres a little shift between the pupils。 and that little shift then creates a depth view for our eyes。

 So it's actually quite cool。 So here we have the cardboard Vr displays source code。

 this has really a few demos that I think are cool。

 So here we see an example of a rotating cube and and that is just 3D。

 Okay So we're just looking at within 3D。 But now I'm going to start the stereoscopic view here。

 The stereoscopic display。 And now what it does is it creates a rendering for each eye left eye right eye。

 has a tiny little shift between these eyes。 And this is has to do with the interpopular distance。

 the IPD。 and there is something that can be adjusted on some headsets as well。😊。



![](img/86580ea11bf31deae5c165a75914432d_3.png)

![](img/86580ea11bf31deae5c165a75914432d_4.png)

And so basically we're not seeing two cursors and two cubes， actually when you put this on your face。

 you actually then perceive depth， you see one cursor， if it's done well。

 it gives you really this illusion of depth， and that is the whole key behind stereoscopic displays。

And this is really the main thing behind carddboard。

 So remember carddboard phone goes inside and then we actually have a rendering for H with these barrel distortions。

Left eye， right eye。Okay， and yeah， and then we perceive it like this， like you see in the video。



![](img/86580ea11bf31deae5c165a75914432d_6.png)

Rendering for each eye。Cool， so that was that。 And I think that is really a first important thing。

 Yeah So we're creating this immersive view， if you will。

 a rendering for H I that gives you then a sense of depth。 And we are starting to see things。

 and we are starting to call this a virtual reality，3。

60 photos and videos by and in themselves are not virtual reality。

 They're often associated with virtual reality， but they only become a virtual reality。

 when we see them through a stereoscopic viewer like the cardboard with a rendering for H I。

 because then our head movement can be tracked just the rotation， not normally the position。

 so we cannot actually walk inside 3，60 photos and videos， But we are starting to get control。

 We are gaining some agency over some of the content， at least in terms of rotation。😊。

My next example is a little bit different。 It's a different display technology。

 It also creates a virtual reality display， but in this case。

 you're actually stepping inside what is called a cave automatic virtual environment inside a cave。

And here I'm showing it based on the example that a colleague of mine at the University of Michigan gave to me so Ted Hall。

 he is in our my then and he shows one of the applications he was working on for some of the researchers that allows him to explore a memmoth and look at it in 3D。

What was really impressive here is how the view is rendered just for him。

 he wears these funny antennas and there is some tracking system an optti track system in the room that actually tracks these antennas and allows him to actually walk around and if you look at the video one more time you will see how the view seems to be like somehow distorted and overlayid and that is the effect that is being created to give him a depth sense so these will shift further away the further the virtual content is away from him and they will be coming more overlapping the closer the eomist to him。

And when you go to the movies and watch a 3D movie， you can also， you know。

 you put on your glasses that they give you。 But then sometimes you probably take them off because you're tired or not and or you just be like。

 hey， let's look at this from a VR perspective。 So these 3D glasses are actually counteracting the shift。

 and they're putting it together in front of you。 So usually some kind of shutter display that quickly。

 So can be active or passive。 but some kind of shutter display that then shows you just a image for the left eye and then the image for the right eye。

 And then this is such a high frequency that you don't even notice。

 And it'll create a 3D image for you that you perceive as depth。😊。

So let's look at actually head tracking and also controller tracking， if you will。

 so we have virtual reality motion controllers， they can be tracked in three degrees of freedom or six degrees of freedom。

So let's look at this in a little bit more detail。 So3 degrees of freedom like the cardboard looks like this。

 Okay， and then we can actually track along the X。 So pitch， we can track along y ya。

 but just rotation， and we can track around along Z， but just again， rotation。 So raw。

 you cannot actually move along these axes。 but you can rotate your head。 So this is me in cardboard。

 And so this is。😊，Page。Yaw en roll， if you will。This is just three degrees of freedom。

 and if you can actually also adjust your position。So the second example here is the hollow kit。

 The one that I had earlier， right？ And so it's a device wrapper just like cardboard。

 but a little different for AR。 So phone goes inside。

 we can see through And if we expose the camera we can actually do some tracking。

 and we can do positional tracking。 So now in addition to head roll pitch and yaw。

 we can also actually determine whether the device moves along the Z axis along the X X and along the Y axis。

 we can do this through a few techniques， tracking techniques like slam， okay。

 which is simaneous localization and mapping of the device in 3D space。

 these are some computer algorithms that actually work based off the camera feed。

 and allow us to determine some kind of motion。😊，Opttical flow， if you will。

 opticalical flow would be computing a vector as I move the device this way。

And we are actually producing a vector from here to there， where， if you will。

 what happens with the camera feed， all the pixels actually shift to the right。 Okay， and that way。

 we can actually figure out that the device moved to the left。 Now， that is what I'm showing here。😊。

In this illustration。This is 60 degrees of freedom。 So we have also positional changes plus minus x。

Positional changes along the Y axiss and positional changes along the Z axis now we actually do have position and orientation and we refer to this as6 degrees of freedom tracking。



![](img/86580ea11bf31deae5c165a75914432d_8.png)

Again， with this kind of tracking， you can actually walk around in a 3D space。

 you can not just look around like with 360 video， but you can actually then move around and actually like this gives you really a lot of agency in the content。

 and that's then when it becomes to when it starts to become hard for designers and developers that have to design for that agency。

😊，So here I have an example of the Ocus goal， the Oculus Go is technically a three degrees of freedom hitset。

It comes with a 3Der freedom controller。 That controller will always be on the right down there。

 and we can figure out its rotation， but we cannot figure out where it actually moves in 3D space。

 So it is really a little limited but you can already do quite a bit just by being able to look around and rotate the controller if we use this laser interaction here。

 this laser controller， laser pointer interaction。 you can reach objects at a distance。

 and you actually do have quite a bit of controller already over the virtual reality content。😊。



![](img/86580ea11bf31deae5c165a75914432d_10.png)

Alright， so here we actually do have the go。 That's the controller I just showed。 and that's the go。

 the device that goes on your head。 Okay， and it is 3 degrees of freedom。 Okay。

 so no travel just rotation and the same for the controller。

 So just a little bit of a pointing device， but whether I have it here or there doesn't make a difference。

 really， the difference is rotation。😊，And so this makes really for quite some differences in terms of how you design and develop。

 and then also how you can use virtual reality applications。

 We're gonna learn more about this in other segments of the MOoc。😊。

So when it comes to 6 degrees of freedom， a very good way to demonstrate this is through the archcus quest。

 So you usually draw a boundary and then you can walk inside those bounds and that's then supposed to be kind of like a save zone and with 6 degrees of freedom both for the controller and for the head I can now actually walk around and move the controller in 3D space and I'll be tracked all the time。

 and that is really quite cool。 So this was 3 degrees of freedom with a 6 degrees of freedom tracking for both the head and the controller。

And now we're going to talk about outside in and inside out tracking。So in a nutshell。

 the difference between outside in tracking is that you have some sensors in the environment that are pointed towards you and they track you as you move around in a certain area that is covered by these sensors。

Inside al tracking means you actually have those centers inbuilt into the device。

 the cameras are actually inside the device， and I'm going to show you two examples here。

So my first example here for outside in tracking is actually the original Ocus。

 the original acuulus required sensors to be placed on a table usually in front of you。

So these sensors here were actually pointing towards you。

And then they are creating a sensor field and they can see you in this range。

 and you have to make sure that these sensors are overlapping。

 So there's some triangulation happening。 and what they're actually looking for is light patterns emitted from the controller and also from the headset。

So my second example is the Oculus Rift S， which is basically the new version of the rift。

 it actually has the cameras inbuilt into the device。Now。

 this makes it possible to actually do both the head tracking and also tracking the controllers in six degrees of freedom without any external sensors。

So the cameras are on the device and basically this is the field of view that these cameras have。

 I mean， it's an approximation。 it's not absolutely correct here。

 And you can see that the controllers are actually captured this way。 In fact。

 theoculus riffft as and the quest even they also have additional cameras on the side。

 So even when you have the controllers next to the device or even below the device。

 the device can still see the controllers。

![](img/86580ea11bf31deae5c165a75914432d_12.png)

This is actually quite an advancement over outside in tracking。

 So when you had these stands on the table， they could only see so and so far。

 and usually the table would occlude things。 So as you were doing things below the table。

 you couldn't be tracked anymore。 Now， with inside out tracking。

 you actually have these sensors on on the device。 And so anything that is visible。

 So in a certain area around them can be tracked。 So when you put your hands behind your back。

 obviously， this will not work。 But。😊，But that's fine。

So here I have an example of the HCC vi with outside in a form of outside in tracking。

 It's technically not absolutely correct， but this is what it usually looks like。

 you have a sensor in the environment and then the controller here is coming towards the sensor and it's being tracked in six degrees of freedom。

So here's an example of me demonstrating the Rift S and I often do this。

 so I'm pointing out the different cameras on the device and I am explaining how the rift S can actually see has cameras on top downwards to the left and right and front。

And has a really good field of view for these cameras to actually track。

 And I'm making some comparisons to the Ocus Rift original sensor stands that you see in the back。

 So let's talk about hand tracking。 Hand tracking now has actually become a standard on the latest generation of VR devices。

 I'm going introduce you to hand tracking in two steps。 First。

 I'll show you what this used to be like with a device called the leap motion， which I have here。

 So the leap motion is a USB tethered device that would be mounted on top of the headset。

 And it creates a field of view， a window in which you can actually do hand tracking。

 So I'm going to show you this first。 And then I'm going to show you how hand tracking actually works on the Oculus quiz。

 which we have there。 And now it's essentially inbuilt。 So built into these devices。😊。

So this is the motion。 It's really not very big and creates this window here。

Then I can actually see my hands nicely articulated。



![](img/86580ea11bf31deae5c165a75914432d_14.png)

So， in this example， I'm just like。Moving my hands up and down。 and I can actually draw， if you will。

嗯。With left and right hand were all the fingers。So this is kind of cool。

Like first person kind of you。And this is like from the app。 So looking down。

I'm facing device from the side。嗯。This is kind of like makes sense。 So in this example。

 I'm gonna show。

![](img/86580ea11bf31deae5c165a75914432d_16.png)

Oculus hand tracking。 So here on the settings in the device， we do have。Hands and controllers。

 and you can see hand tracking and auto enabling hand tracking is actually toggled to on so switched on now that means I can just put down my controllers。

 look at my hands。Look at my hands。 and there they are。And I'm going to do pass through。

 So you see what I'm looking at。 So here are my hands and I'm going go back into VR and it's nicely mapped。

It's relatively accurate， it feels pretty good， I am touching their correct fingers。

And this would actually be a gesture， so it lights up， becomes active。

 and what we're going to do is well， we can like scroll and we can scroll sideways as well。

So we're going to close this and can scroll sideways。😔，And it feels relatively good。

 You can see the rendering of my hand。 It still seems relatively accurate。And yeah。

 so let's scroll up and down with this pinched to drag gesture。 And one thing that is a little bit。

If an app doesn't support hand tracking， like here， this is the browser so I can actually browse。

With hand tracking。Most normal websites would work。

 But then when you go on look at whether this now works in aframe， then at this stage。

 I have to disappoint。 you。 have to grab the controllers。

 So you're gonna do the path through controllers over there。're gonna grab them。

And we're going to go into the VR immersive view， there we go， there it is。

So hand tracking and aframe per default doesn't work yet。

 But this is probably gonna happen very soon。 Just not at the time of this recording。

 I'm gonna exit out with the Oculus button。And this concludes my little demo of hand tracking and controllers so you can actually seamlessly go back and forth between hand。

 hands and controllers， pick up the controllers and press a button and there they are again。And。

Give it a little bit of rest， and then look at your。

Hence give it a bit of time for the recognition to work。

So we do have hand tracking now built into these devices。

 and I talked about VR gloves earlier and the reasons I don't have them。

 but the point of VR gloves is not necessarily the tracking of the hands。

 is actually the creation of the haptic sensation so that you actually feel like you're touching something that can only be accomplished through some tricks by actually mapping the physical to the virtual environment so that。

 for example， you are perceiving in VR a surface here and just happens to be also your desk that you are touching And if you can create these kinds of nice overlays between the physical and the virtual。

 you actually do get a sensation of physical feedback even without varying additional things like gloves and whatnot。

So most of my examples were actually visual， So what does it take to create a virtual reality and virtual reality is predominantly visual。

 So in that sense， it's not wrong。 however， a very， very。

 very important part of creating immersion is actually the audio around the user So my last example with focus on spatial audio and here I could have chosen many examples。

 one that I like is actually tiltilbrush and I want to show it to you in two ways。

 first without sound and then with sound。😊。

![](img/86580ea11bf31deae5c165a75914432d_18.png)

嗯。

![](img/86580ea11bf31deae5c165a75914432d_20.png)

![](img/86580ea11bf31deae5c165a75914432d_21.png)

![](img/86580ea11bf31deae5c165a75914432d_22.png)

So now we have seen the main ingredients of virtual reality。

 both on the visual side and then on the tracking side。

 So stereoscopic views or alternatively creating like a cave like monitor wall sizeized displays around the user So inside a virtual reality headset。

 if you will or for the headset， we talked about stereoscopic views。

 We've learned a little bit about interactions and also hand tracking。

 And then spatial or positional audio as well。 So these together actually create a rich set of sensations。

 And this is really what you want to accomplish。 so that your users feel immersed in virtual reality。

 The close things， I'm gonna revisit beataber and we're gonna look at it from the perspective of all these kinds of technologies that we've just learned about。

😊，So in terms of the VR technologies that we've just learned about。

 Beabber really actually chooses those， it creates a stereoscopic display through the headset。

 it supports 6 degrees of freedom tracking which is really necessary you need to be able to move in space and also it does work actually with both outside in an inside out tracking but the example that I show you here is using the Oculus Rift S with inside out tracking and。



![](img/86580ea11bf31deae5c165a75914432d_24.png)

🎼Yeah， so I have to follow these directions when slicing oops and we should have used the other。

Saavor but that way， you'll see what happens when things go wrong， avoid those。And then。🎼Just blue。

🎼No， red。And this one you can cut into any direction。🎼And。The synchronous cuts are funny。

But I do like it when you get to slice like crazy like this。

And now comes my favorite part of the song。🎼How。🎼哎你哎当当当。🎼Right。🎼Got any。

And you made one mistake so far， but it's okay。🎼You not pearl。Right。

🎼To be careful that I don't hit the cable， in case。They don't want it to disconnect again。🎼And down。

对。😊，🎼And this one， I was finding funny my day turn around。

And then you have to do that the last minute of changes。And this one is cool， size， size。🎼1万。



![](img/86580ea11bf31deae5c165a75914432d_26.png)