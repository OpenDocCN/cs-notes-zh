# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p106 22_WebXR基础VR开发.zh_en -BV1jM4m1k73q_p106-

![](img/04166cf832cf3cd5409b884aa894351f_0.png)

![](img/04166cf832cf3cd5409b884aa894351f_1.png)

Welcome everybody to this lecture on basic virtual reality experiences in Web Xr。

 So we're gonna to use a frame。 and this is gonna be a little bit more hands on。

 you can see I'm already kind of like almost ready to jump into VR so for the majority of this lecture。

 I'm going to be using the Ocus Rift S it's connected to my computer very quick setup。

 I can just jump into VR on the computer and get the controllers and show you things。

 So that's important。 but keep in mind， even if you don't have this headset。

 cardboard with the smartphone would be a possibility for the majority of examples in this lecture。

 if not all of them， I think all of them。 Andll I'll say later if that's not true。

 the problem with that is I would always have to switch to the smartphone type in the URL and run it and I'm going I'm going avoid that just in the interest of time。

 and I can just run things quickly， but they would work in the。😊，Okay， so keep that in mind。

 not going to show anything beyond cardboard in this lecture。

So I have like a starting point for us here where I kind of like want to be at the end is this final example。

 So I'm going to show you my starting point is this and my where I want to be is actually final HTMLM so this is where I want to be。



![](img/04166cf832cf3cd5409b884aa894351f_3.png)

![](img/04166cf832cf3cd5409b884aa894351f_4.png)

In the end and then I want to be able to just like go into VR and now I'm actually in VR but for you to see this。

 I'm going to show you the Ochius mirror that I have here and now you can see I have the giraffe I actually have the controllers in front of me and I will have teleportation in there so I can actually teleport around I'm not gonna get up and all that in this lecture but I could essentially walk around。

 take different angles and look at the giraffe and there's my giraffe and I can go back。



![](img/04166cf832cf3cd5409b884aa894351f_6.png)

![](img/04166cf832cf3cd5409b884aa894351f_7.png)

I can also like， be underneath， and then。I just had to do this kind of turn because I。

 although I'm on a swivel chair。It would be dangerous at some stage。Cool， so that's my setup。

 so the mirror here so that you can see things。I am using Firefox so that I can actually jump directly into VR。

 I'm going to actually do this project here and I'm going to share this with you later。

 This is part of my XMO Gitch project and I'm just going go back to our starting point I'm going build this scene for you just so you know this is what it looks like right now just a little giraffe in there and we can already go into VR I'm just going escape quickly reload the scene So this is our starting point okay so all I have so far is a giraffe that I got with Google Poly。



![](img/04166cf832cf3cd5409b884aa894351f_9.png)

![](img/04166cf832cf3cd5409b884aa894351f_10.png)

And a plane。 and I put it on a green background。 And I just showed you where we want to be。

 So this is our starting point so far， not too much in this code here。



![](img/04166cf832cf3cd5409b884aa894351f_12.png)

So I'm calling it basic VR， I'm using aframe the latest at this stage。

 I'm sure they're working on a new one already。 I have the Google Poly load component in here so I can actually get my Google Poly my Google Poly that I'm using is a giraffe It's actually from Google here I specified the Pol ID I have to use an API key would be great if you weren't using this one otherwise I will get into trouble I've already kind of like figured out positioning rotation and scale otherwise it's too big and in fact I'm actually going to make it probably a little bit bigger for some of the VR examples on end I'm going to change it and make it smaller again for AR that's not gonna to happen I guess。

And so we have a plane。 We have a green sky。

![](img/04166cf832cf3cd5409b884aa894351f_14.png)

That's our starting point。Anytime we can go VR won't render here， but renders here。

 I don't know why this is the case it's just recently anyway in this example。No controllers。 Okay。

 no controllers。Not rendering yet。 We're going to get the controllers in there。

 And so we're going to make it a VR scene。 So right now， it's just a 3D scene。



![](img/04166cf832cf3cd5409b884aa894351f_16.png)

And I'm going reload this very quickly。 So just the 3D scene。

 And so the first thing we're gonna do is I showed you where we want to be。

 So we don't have to do that。 We're gonna look at。 So we're gonna do a basic VR experience。 Okay。

 so 3D model， we have。 maybe animation。 Maybe I'll do that。

 Maybe I'll rotate it or something's stupid。 Well see lights and shadows。 They are already there。

 I'll show you and。😊，Usually you would have some kind of like cursa based interaction。

 so what I would mean here is the carddboard cursa so anyway。First things first， make it a VR scene。

 So I have on code pen。 I have a template for us。 So that's this one here。

 And it doesn't contain CS or jascript。 So I'm just gonna go full screen on that doesn't look too impressive。

 actually has a little bit of interactions that already work also just with the mouse。

 It's actually quite a few things going on here。 And actually run it in VR。 Yes。

 so we're gonna go full screen。 I don't wantna actually close this。 I should keep that in mind。

 So this is the VR scene。 And now it it has support for controllers。 It actually has laser control。

 So this template is a really cool starting point。 And on one of the controllers。

 If I remember correctly， Yes， here， I put on the grip button。

 So not the trigger button because trigger is to click。😊。



![](img/04166cf832cf3cd5409b884aa894351f_18.png)

![](img/04166cf832cf3cd5409b884aa894351f_19.png)

And grip is at least on my  acularulus right now。 and you may have to adjust a little bit the button configurations。

 but this would allow me to teleport。 And I can point at things here with my laser controls。

 So what I'm gonna get from this example is the， well， later I'm gonna to get the teleport controls。



![](img/04166cf832cf3cd5409b884aa894351f_21.png)

But I said， we're going to do cardboard compatible stuff only。So， then。I am going to get。

Not too much， actually。

![](img/04166cf832cf3cd5409b884aa894351f_23.png)

I'm going to get the hands。So I have them。They wouldn't show on。

 So this is like that part that just co it paste into my scene。 So I get the camera rig。

 I explained that in lecture， get left hand， right hand。 we have laser controls left and right。

 we're gonna have a mix in here。Later， I'm gonna do that part later。

 That would actually give us the functionality for the teleporting Im doing it via mix in。

But so right now， when I download load my scene again。



![](img/04166cf832cf3cd5409b884aa894351f_25.png)

I'm going to go into VR and I'm going to show you in here。Going to go full screen。Set this up。

 Then I should be able to see my controllers。 Okay， I actually have laser controls now。And they are。

嗯。Interssecting with anything and everything they see right now。



![](img/04166cf832cf3cd5409b884aa894351f_27.png)

And so that is a little bit of an issue。And I'm going to fix this by。When I have a raycaster。

 that would have been the mix and would have done that。 I' gonna fix that later。 Okay。

 so the main point is these hands wouldn't actually show up on cardboard。 for cardboard。

 We should probably have a cursor。 I'm gonna get that too。

 So actually have a different template for cardboard。 And I'm going get to that one at the end。

 So the first thing I wanted to talk about is actually animations right， So we have a 3D model。

 According to our checklist， we have the 3D model I just use a Google Po。

 and then we're gonna to do animations。 So let's look at my animations example here。 So no CSS。

 no jascript。 How am I doing this。 A lot of things are going on。 In fact。

 we can also look at this in Vr。 Let me just make sure that only one of these is actually in Vr Im to see animations are there。

 And this is what it looks like for me now in Vr。 And yeah， this is。



![](img/04166cf832cf3cd5409b884aa894351f_29.png)

![](img/04166cf832cf3cd5409b884aa894351f_30.png)

![](img/04166cf832cf3cd5409b884aa894351f_31.png)

![](img/04166cf832cf3cd5409b884aa894351f_32.png)

![](img/04166cf832cf3cd5409b884aa894351f_33.png)

![](img/04166cf832cf3cd5409b884aa894351f_34.png)

Go to adjust the。

![](img/04166cf832cf3cd5409b884aa894351f_36.png)

Settings a little bit。 This is。Yeah。So it's a disco。 club。 Yeah， So this is interesting。

 I just put everything together here just to show how animations work。

 And there's obviously a lot of stuff going on。 So let me see that I can grab animations。😊。



![](img/04166cf832cf3cd5409b884aa894351f_38.png)

So here， look at this。 I was gonna cancel。 One of the animations does rotation。 So on the on the box。

 there's a lot of stuff going on。 Some of the other things are doing scale。

 and we can also just actually do position。 So I'm gonna grab one of these as an example for me。

 And I'm going add that into my scene。

![](img/04166cf832cf3cd5409b884aa894351f_40.png)

We're gonna to animate the giraffe。 Okay， so here I'm gonna。

You can that's how you can use my examples and learn from them。

 So this one now wouldn't be a cool one。 would just like rotate this giraffe in a very weird way。



![](img/04166cf832cf3cd5409b884aa894351f_42.png)

You can see where the people is and yeah I actually went on I guess so we're going to do property rotation is very weird what I'm going to do is I'm just going to do a 360 around the y and then it would be a little bit less weird but it's still weird what I do there。

😊。

![](img/04166cf832cf3cd5409b884aa894351f_44.png)

![](img/04166cf832cf3cd5409b884aa894351f_45.png)

![](img/04166cf832cf3cd5409b884aa894351f_46.png)

Rotation 3，6，0，0。 Oh， we have。 Okay， we have a different starting rotation。

 We should keep that in mind。 So we need the-90。 We need to left leave that one。 Otherwise。

 the model wouldn't be right。 And so it's， it's， this is now alternate。 we don't want that。

 So we're gonna not do alternate。 Were just gonna。

![](img/04166cf832cf3cd5409b884aa894351f_48.png)

![](img/04166cf832cf3cd5409b884aa894351f_49.png)

![](img/04166cf832cf3cd5409b884aa894351f_50.png)

Keep looping。So if I reload this one again， it'll just like go in circles。 It should go in circles。

But it will actually then reset， okay， so this is a little bit。



![](img/04166cf832cf3cd5409b884aa894351f_52.png)

Un cool。It goes from -90 to 360， So it should go to。没呀。We almost need to have two。

So I can start from 0， and then this one would be better。 So then it's， it starts like this way。

 And we can also like， have the。

![](img/04166cf832cf3cd5409b884aa894351f_54.png)

![](img/04166cf832cf3cd5409b884aa894351f_55.png)

In terms of animations， there's a few things。 but I'm just going to quickly open aframe animation。



![](img/04166cf832cf3cd5409b884aa894351f_57.png)

As an as an example in here。 and one of the things I'm looking for is obviously that this is where you can find all the information that you need。

 One of the things I want to find is the easing function。 And then here it says easing。

 and I'm gonna do linear。 So easing linear， I'm just gonna add that here。Easing linear。

And then it'll look a little less weird。 It'll be smooth。 It'll just always continue moving， moving。

 moving and。

![](img/04166cf832cf3cd5409b884aa894351f_59.png)

We can see it in。VR as well。 And now I have a giraffe。Thatd keeps like rotating。

 but I't I don't want that。

![](img/04166cf832cf3cd5409b884aa894351f_61.png)

嗯。I mean， what we could do is a little bit left， right just to have a little bit of movement。

And so if we started from。Can have a little bit of subtle movement if we want to。 So we just。

 I think this was 90。And。And then， we can do。92 just to have it moving a little bit。

Let me see how that looks。 So， oh， this is now the back。 Okay， we need-90 to move it to the front。

 and then-95。Over 3。5 seconds， Let's see what this effect looks like。 Obviously。

 this is a little bit of experimentation and。

![](img/04166cf832cf3cd5409b884aa894351f_63.png)

![](img/04166cf832cf3cd5409b884aa894351f_64.png)

嗯。And now I'm going to do alternate。 So I'm gonna， I'm going to go from。Minus。88。To。-95。

 And I'm gonna do the alternate。

![](img/04166cf832cf3cd5409b884aa894351f_66.png)

Direction， so then it moves a little bit， and it'll look like。Hey， this， this is Israel off。

 and it's moving it a little bit， okay。

![](img/04166cf832cf3cd5409b884aa894351f_68.png)

So， and maybe you don't， maybe you want the easing。There are other easing functions。

 Let's see what other easing functions we have。Is in quad。Sign。E in bag。Let's do elastic。

Easing out elastic。 So let's copy this one。 Let's see what that feels like。

 So something to play around with， obviously is part of the animations。 and'm probably。



![](img/04166cf832cf3cd5409b884aa894351f_70.png)

Already spending too much time。

![](img/04166cf832cf3cd5409b884aa894351f_72.png)

I mean， it looks a little， let's test it in VR。 Yeah， so pull screen again，ra。😊。



![](img/04166cf832cf3cd5409b884aa894351f_74.png)

![](img/04166cf832cf3cd5409b884aa894351f_75.png)

This is just so you can see see that you can see what I see。And yeah， I mean。



![](img/04166cf832cf3cd5409b884aa894351f_77.png)

It's， obviously。Not too crazy， but it's better。😊，It's much better than the rotation before。

 What do you think， Okay， so I'm gonna actually move on。 We have animation now。 So。

 and I said we have VR。 we actually have the controllers in there。 We're gonna have lights。 Okay。

 so my light demo is another starting point here。 So we're done with animations for now。😊。



![](img/04166cf832cf3cd5409b884aa894351f_79.png)

This is my light demo。 Okay， and actually， I have the C S S I use mostly for this toolbar down there。

 and also the jascript。 So all we need to see is。😊，The light in here。 So we have two lights in here。

 We have an ambient light called a light and a directional light called D light。

 And so here I can actually make it pretty dark or just reset。 So this is the original ambient light。

 I could also change the ambient light in this demo to blue， for example。

 And then there is a directional light here。😊，It's always hard to see where it is so I can go into the inspector and zoom out a little bit。

 so the directional light is actually here and the emmbient light is usually at the 000 directional light is that's a default light inserted by aframe so at one so it's actually usually behind the camera that's interesting at the height of one meter and then a little bit to the left。

So it's shining and you can see， I mean， maybe this is how it it's going to shine to the center。

 okay？So it's going down to the center。 if you move it further away。

This is going to change things a little bit。So you can play with it here in。The inspector。

 But keep in mind， you playing with the inspector doesn't update the code。

 You can see how it shines to 0，0。 So obviously， if you， for example， if you move the box out。

 this will also。Look a little different。 I thought it would look a little different。嗯。

So let's just move the light。Toight is always gonna be at0。And okay。

 so we're gonna go back to the scene。 And let's say。

 so you can play around with this A frame lights example here。 I'm gonna get my own lights。

 So I'm actually going to take both。 These are the default lights。

 But since I want to change the lights a little bit in my scene。😊。



![](img/04166cf832cf3cd5409b884aa894351f_81.png)

![](img/04166cf832cf3cd5409b884aa894351f_82.png)

I'm going to just get them in here。AndYou have the sky， it's pretty green。

What are we going to do a night safari， What do you think， I mean， we wanted to do a night safari。

Cas shadow。Why is this the attribute name of cash must be lowercase， Yeah， okay。诶。です。

It's interesting that this actually works。😔，I doubt that this is correct。 But okay， fine。

 We just leave it the way it is。 I mean， Im， I'm programme this some time ago。 So maybe。

 maybe it is fine。 So let's see what we just have。 So now we have。 This is the same light as before。

 So no change， oops。😊。

![](img/04166cf832cf3cd5409b884aa894351f_84.png)

![](img/04166cf832cf3cd5409b884aa894351f_85.png)

![](img/04166cf832cf3cd5409b884aa894351f_86.png)

Yes。

![](img/04166cf832cf3cd5409b884aa894351f_88.png)

Okay， let's close the template。 We are。Going to get actually the teleport controls later。

 But let's just focus on one so that I don't always do the mistakes。 I'm going to reset here。

 So this is our light。

![](img/04166cf832cf3cd5409b884aa894351f_90.png)

And I'm gonna adjust it now a little bit。 So ambient light， let's say we make it a little bit darker。

 So 7，7，7。

![](img/04166cf832cf3cd5409b884aa894351f_92.png)

And。

![](img/04166cf832cf3cd5409b884aa894351f_94.png)

So that would make the whole scene darker。 Okay， you can see how。How the giraffe is now。



![](img/04166cf832cf3cd5409b884aa894351f_96.png)

Yeah。Could actually make it even darker。

![](img/04166cf832cf3cd5409b884aa894351f_98.png)

So then we can later have the torch light， if you wanted to。



![](img/04166cf832cf3cd5409b884aa894351f_100.png)

Okay， so pretty dark now。 And we can also change this ambient light， maybe to 88，8 and position。Yeah。

I would like it to be actually more like from the right。 I'm gonna put everything at 1，1，1。

 So I'm gonna have it more like from the run it。

![](img/04166cf832cf3cd5409b884aa894351f_102.png)

And。

![](img/04166cf832cf3cd5409b884aa894351f_104.png)

What I could do is actually I can change it to a spotlight。AndMaybe it's just called spot。 I forgot。

 Let's see a frame。Documentation light。An ambient directional hemisphere spot。 So then type spot。

 So it's not called spotlight。 It's just called spot。



![](img/04166cf832cf3cd5409b884aa894351f_106.png)

And so now we have。A little bit of， it's a little bit here。



![](img/04166cf832cf3cd5409b884aa894351f_108.png)

But I。And so my giraffe is at minus5。And so therefore the light， we can have a target。Element。

 the spot should point to。Okay， so we're gonna give it a target。Target。Girrae。



![](img/04166cf832cf3cd5409b884aa894351f_110.png)

It has that I D。 So let's see whether that kind of like。Changes anything。 Does't change too much。



![](img/04166cf832cf3cd5409b884aa894351f_112.png)

I'm going to have it actually higher， so。And I'm also gonna have it roughly， like， more like above。



![](img/04166cf832cf3cd5409b884aa894351f_114.png)

That giraffe， but maybe at minus three。And so maybe that changes things a little bit， not too much。

 but it's probably shining on its back now。Okay， time for the inspector。So what did I do。

 Where is my。Tiectctional light， so it is prove shining。Add the giraffe。But。That's interesting。

Not to， oh， I guess actually， the intensity is not very。You can see a little bit of it。

 but the intensity is not very great。 So angle。Maybe we can make it a larger angle， okay。

 leave it at 60。嗯。Since I made it a spot that we should probably make it bright and。

Put it roughly there。 and now we are talking， okay， and then intensity， I'm going to make it 0，9。嗯。0。

7。And maybe make it more like a spotlight。 Okay， so maybe just 20。And。0，7，5。Okay。

 how would that look。So then when we are here in the beginning， this is interesting。Potentially。

I like it。 So I'm going inspect the scene again。 What do I do。

 So I put it roughly And what load position。

![](img/04166cf832cf3cd5409b884aa894351f_116.png)

So。It's3 minus1，7， so we're going to copy this more or less。嗯。Copy everything。

 So I'm just gonna copy。 So technically， you could do it you could really do it step by step。

 I know it's a little bit。So three， we can remember this and this one。

 if I really wanted to have it like this exactly。Then。This is where I have it right now。

 I'm going to round it up a little bit。And here I'm also going run it up a little bit。

 Soll leave it there。 I said F of F angle， I put to 20。And。Intensity color。

 FFF can we change that intensity 7，5。

![](img/04166cf832cf3cd5409b884aa894351f_118.png)

Let's see。 that's reload。 And there it is the way it was， okay， we have light animation。

 we have light。 good cool。 Okay， we're good。 do I have the mirror。 No， always forget the mirror。

 I'm sorry。

![](img/04166cf832cf3cd5409b884aa894351f_120.png)

![](img/04166cf832cf3cd5409b884aa894351f_121.png)

I'm not used to developing with the mirror in the background， but here we go and there is our mirror。

 And yeah， for me it looks already quite cool。 So in my shadow example you see lot of the a lot of the stuff that is actually the theory behind the shadows and you actually see where the light is coming from here。

 there is actually a shadow camera that I show。

![](img/04166cf832cf3cd5409b884aa894351f_123.png)

![](img/04166cf832cf3cd5409b884aa894351f_124.png)

And if we go into the see inspector， zoom out a little bit。

 then you have that pretty nice view and the light that is the the directional light is the one with the shadow。

 So this is the directional light。 I should have named it here。 But if I move it up。

You can see how it does change a little bit the light on the scene。

And it always shines at the center。 So I'm gonna actually。It's a little crowded in here， so that me。

Give it a little bit more。Like this。 Okay， and so now as we kind of like go by。

You can really see how it changes a little with the light。

 I always like to play with light and shadow。 Also， I was just looking at the light。

 Look at the shadows now。 So you see how the shadows are obviously moving left to right。😊。

And so obviously， if we animated this。If we animated this， this spotlight。

 that could also be very interesting。 Okay， let's see that we get some shadows in here。

 So we have cast shadow。

![](img/04166cf832cf3cd5409b884aa894351f_126.png)

![](img/04166cf832cf3cd5409b884aa894351f_127.png)

And truee。And let me see， I'm still not sure that I'm doing this the right way， so close this。



![](img/04166cf832cf3cd5409b884aa894351f_129.png)

I focus on the left there。Acu is getting heavy。Okay， so here we have the。Yeah。

 this is probably the way we should do this with a shadow camera。 I'm just going to do it this way。

 This is the directional light。 and this cast shadow seems wrong。



![](img/04166cf832cf3cd5409b884aa894351f_131.png)

For the amb light anyway， Embient light cast shadowow。 I don't know what this is。

 I don't think this is right。 Does ambient light actually cast shadowow， so。嗯。小ello。Ambient。

 so we recommend to have amb night such that shadowed areas are not fully black。诶。Like。

 I feel like ambient light cannot cast shadow because it's just like， lighting the whole scene。

Coning shadows， so light types that support shadows are points， but directional ha ha。



![](img/04166cf832cf3cd5409b884aa894351f_133.png)

Good， so I don't know this must have been you know the previous Michael anyway。

 so new Michael obviously knows a little bit better。😊。



![](img/04166cf832cf3cd5409b884aa894351f_135.png)

So for the light， we can， we can do it like this the way I had it here。

 but I'm actually going do it slightly differently。 So I'm going to copy this whole thing。

Write it a little bit differently。 It's going to be the same functionality。

 Just we are using the whole light component。 So I'm going to use an entity。

And it's going to be the same thing。 I'm going make it a spotlight， Ca shadow true angle is 20。

 so we're going to do that here。 angle 20 position all that we're going to leave intensity is actually going to be 0。

5，7，5 and color we're going use put that in here。Yeah。So have to rewrite this a little bit。

 And now this is gonna be my light component。 Okay。

 so everything light is now in one thing rather than having like a million of these properties。

 all I do here is specify everything light as this light component and the target。

It's also part of light。 and so this is an entity now， not a light anymore。

 and then we just have a position。 And so here I say target G run。And then we are cool。

And from time to time， you could do format this file and see what it does。

 It does break things into different lines。 So that makes it sometimes it breaks it up like crazy。

And。So I don't actually like this。 I'm just going to undo this。

 I just wanted to show you it's possible。 so here we can have the light in the next line。

 maybe a little bit like this。诶。You're gonna move the position app， so。

So now I'm getting crazy in terms of coding。 But okay， here we go loading our scene。

And we'm gonna show you in。 There is。

![](img/04166cf832cf3cd5409b884aa894351f_137.png)

Our spotlight， you can see it now with the。With the shadow on， but。



![](img/04166cf832cf3cd5409b884aa894351f_139.png)

With a shadow camera on。 But the problem that we have。Cash shadow， shadowow camera is visible。

I'm going to sort this a little bit differently angle。AndT， so。

The problem is we don't actually receive shadow， I believe on the plane。

 so we're going to do that plane here， if we add shadow here， it should receive the shadow。



![](img/04166cf832cf3cd5409b884aa894351f_141.png)

And。Yeah， since we have the spotlight like that。Maybe this doesn't work it。

 There could also be a problem with this model。

![](img/04166cf832cf3cd5409b884aa894351f_143.png)

But I do， okay， let me let me debug this。 So I'm going to bring this in here。



![](img/04166cf832cf3cd5409b884aa894351f_145.png)

And why is this not working here， that's everything that willul go wrong can go wrong。

 here is the light。

![](img/04166cf832cf3cd5409b884aa894351f_147.png)

![](img/04166cf832cf3cd5409b884aa894351f_148.png)

If we change the light， it doesn't change anything to the shadow。

I'm going to make this plane just a little larger， so。嗯。1 by ten。No， I don't actually see。

I don't actually see any shadow。Oh， the model may not have shadow， okay， we actually。



![](img/04166cf832cf3cd5409b884aa894351f_150.png)

Yeah， alright。 So that is well， this could happen to you， too， right， happens do the best。

 So here gonna have shadow for that model。 And then yeah， you see it。 You see it。 Okay。

 we have shadow。 Alright， perfect。😊。

![](img/04166cf832cf3cd5409b884aa894351f_152.png)

![](img/04166cf832cf3cd5409b884aa894351f_153.png)

So， and the shadow is also moving。 But for the purposes of our demonstration。

 we're gonna actually increase the size of the plane。 Give a little more space。 Oops。

 that would be crazy。 So 10。 Now here we go。

![](img/04166cf832cf3cd5409b884aa894351f_155.png)

嗯。

![](img/04166cf832cf3cd5409b884aa894351f_157.png)

That looks interesting。 I'm going to move it a little bit backwards， so。Minus， okay。

 I made it a little bit too。I think this is。ない？So。Allright。

 and then I'm going to move it a little bit backwards to minus。



![](img/04166cf832cf3cd5409b884aa894351f_159.png)

6ix。And that moves the plane a little bit like that。No。

 suddenly loading takes a little bit of time here， but。That's okay。

 So now I'm actually kind of like happy。 Actually， I'm gonna to make it a little larger。



![](img/04166cf832cf3cd5409b884aa894351f_161.png)

Sorry， alright， so， you know， so that we have like， okay， you can， isn't that's a great little scene。

 Alright， we have R G Ra。 It's moving。 It's more like a circus now right， it feels like。😊。



![](img/04166cf832cf3cd5409b884aa894351f_163.png)

![](img/04166cf832cf3cd5409b884aa894351f_164.png)

Yes， cicus。 all right， cool。 So we have light。😊，Yes， so we where are we。 We have lights shadows。

 Tara Tara Tara， and we have cursor。 So shadow， I have like one really cool example seen here where I combine some of these。

 Maybe that's a good starting point for you。 And I wanted to show it to you because。😊。



![](img/04166cf832cf3cd5409b884aa894351f_166.png)

It does look nice。 It's a beautiful little ball in the ocean scene。😊，And。

And that combines some of the things it also adds fog， something I haven't covered。

 animations has an ocean component。 So a couple more things。 it also does look great in VR。

 So here it is。

![](img/04166cf832cf3cd5409b884aa894351f_168.png)

AndFor me to enjoy。Yeah， it is cool。I'm just looking at it right now。



![](img/04166cf832cf3cd5409b884aa894351f_170.png)

Alright， so this example also may be a good reference for you。 So the URL is here。

 and I'm going to provide all these little references for you so。

I'm going to show the carddboard template as the last thing because obviously， I mean。

 we will probably interact with our G at some stage。

 and I'm going to give it an environment component later。

I'm just going to show you a few of the cardboard things so that we。Can do carpet as well。

 So I'm going to get rid of theoculus rift。 We're starting to get heavy。Anyway， and。

It also always does funny things to my hair， but that's just how it is。Cardboard。 Okay， so template。

 heres the template。 If you wanted to get some of these things working in cardboard。

 then this is the。

![](img/04166cf832cf3cd5409b884aa894351f_172.png)

Tempate for that。 Okay， I made it a really big VR button。 It has a cursor， and that cursor fuses。

 And then I don't know whether I have interactions。 I don't have any interactions。

 It just fuses on things that it hits。And I'm hiding the AR button。

 and I'm showing the VR button in large。And so， you can。Go to this URL， which is slash D bug。

 So if I type this into my phone。

![](img/04166cf832cf3cd5409b884aa894351f_174.png)

I'm gonna allow VR。 If I type this into my phone， C DP， N， I， O， M labeling， Dbug， and then V V， O。

 O， O， J。Which is going to take me a while。 this would run in my cardboard。

And it's also compatible with， let me see that I'm done here， also compatible with the rift。



![](img/04166cf832cf3cd5409b884aa894351f_176.png)

It's kind of like you can develop for the rift and then also make sure that things are working。



![](img/04166cf832cf3cd5409b884aa894351f_178.png)

This having a cursor and rift is a little， is a little unusual。So that's something to keep in mind。

 but the template does work。 And I'm going to show you how this would work in cardboard。

 I'm going to press the VR button here。

![](img/04166cf832cf3cd5409b884aa894351f_180.png)

![](img/04166cf832cf3cd5409b884aa894351f_181.png)

And。Oh， yeah。 we have to go into the debug。 I forgot。 So we're gonna go into the debug mode。

 Otherwise it won't do this VR button。

![](img/04166cf832cf3cd5409b884aa894351f_183.png)

And。Now， pressing the VR button。

![](img/04166cf832cf3cd5409b884aa894351f_185.png)

Actually， it launches it in VR and I closed this。And I can see it in VR has afuse。

 but we don't actually have interactions yet。 just have a cursor for now so we can start looking at things that is the cardboard template。



![](img/04166cf832cf3cd5409b884aa894351f_187.png)

It does actually have an animation for the cursor。 I'm just like looking here at the code。

 So animation for the cursor， that's what we have。And then， we don't actually have anything。

Do we have any events at？IJust looking。

![](img/04166cf832cf3cd5409b884aa894351f_189.png)

AndTing to hit this thing。Okay， I don't have the event said。嗯。



![](img/04166cf832cf3cd5409b884aa894351f_191.png)

So I could grab this cursor。And。Can I add that to my scene as well。 So here is my project。



![](img/04166cf832cf3cd5409b884aa894351f_193.png)

I'm going to add that cursor。 It should be inside my camera。 So inside my head。

 it's something to keep in mind。 And this cursor， I would only use when it is a。

3 degrees of freedom headsets。 So no controllers。 And I could fact find that out this Java script。



![](img/04166cf832cf3cd5409b884aa894351f_195.png)

I'm just going to reload my example， and then now we have a cursor it's in the camera。

And in fuses on the object。And。What I could do is that when， when you click this object。



![](img/04166cf832cf3cd5409b884aa894351f_197.png)

Maybe we could do the spotlight on and off。How we're going do that。 Okay， we're gonna do that。 Okay。

 we're gonna do that。 Thiss the last thing I're going do。38 minutes in okay。You you still there？

Bunny is starting to drink things。Let's say when we have a on the we have an event set in here， no。

I'm going to get the event set component。And just so that I don't have to do too much JavaScript。

And I'm just gonna check。 Did I have events in my final cheater for No， I have other things in there。

 So it seems like this is something I didn't want to do， But I'm just gonna improvise here。 Alright。

 so we have event set somewhere in my code pen examples as well。 Let's just see that we find it。

 Go to my dashboard event set component。

![](img/04166cf832cf3cd5409b884aa894351f_199.png)

![](img/04166cf832cf3cd5409b884aa894351f_200.png)

![](img/04166cf832cf3cd5409b884aa894351f_201.png)

This one， and that has the right URL。 that's the one that I need。

I'm going to explain in a second why this is something that I want right now。

 I'm going to add a cursor to we have a cursor in the scene。cursor in here。

 And we can also have a cursor ray origin mouse。In here we can have both， this is good for debugging。

And。Then I can click things directly。 and then I'm gonna have， we have an animation。

And I'm going to have an events set。R said。We're going to have click， so that's my event。And then。

We're gonna to do them click。We're going to make it。I'm going to hide it。And they actually。

 let's see whether this works。 Okay， so reload， click and that hides the giraffe。



![](img/04166cf832cf3cd5409b884aa894351f_203.png)

![](img/04166cf832cf3cd5409b884aa894351f_204.png)

And now it's gone， isn't that sad？So。We are。嗯。What could be cool for our scene。 So actually。

 I wanted to do that spotlight on and off。 so we can actually do。😊，Target spot。

 and we can give it at what it's called Delight， actually， not spot。It's not directional light。

 so it's just called spots since it's not the directional light anymore。



![](img/04166cf832cf3cd5409b884aa894351f_206.png)

And so now when we click this。

![](img/04166cf832cf3cd5409b884aa894351f_208.png)

Okay， target is。Let me see this might be。

![](img/04166cf832cf3cd5409b884aa894351f_210.png)

Target like this。Because we're not changing the property， but okay。

 So we cannot switch it on anymore。 Well， that's fine。 Okay， I mean。

 we continue actually making this also like on and off anyway。 So what I wanted to show now is， okay。

 we have this。 We have the。

![](img/04166cf832cf3cd5409b884aa894351f_212.png)

![](img/04166cf832cf3cd5409b884aa894351f_213.png)

We have the cardboard thing in there。 Also， I'm going to just quickly get my CSS。

 So I have a really big cardboard button。

![](img/04166cf832cf3cd5409b884aa894351f_215.png)

It's justre going to make things easier， so I'm going to do that。



![](img/04166cf832cf3cd5409b884aa894351f_217.png)

I'm going to add that to my little example here。 And so I'm just going to make it compatible with cardboard。

 Also， by the way， I should show this so you can click this directly， okay。



![](img/04166cf832cf3cd5409b884aa894351f_219.png)

Or you can do fuse。 So I'm just like waiting。 And then that's the same thing。

 So this is why this is going work with cardboard。

![](img/04166cf832cf3cd5409b884aa894351f_221.png)

And。Yes， so I'm going to add the CSS here。スタyle。AndJust that stuff。



![](img/04166cf832cf3cd5409b884aa894351f_223.png)

So then this is just gonna make this button really big。 Okay。

 now we're gonna go to my basic project here in the camera on the phone。

 So I'm gonna actually type in a different URL。 So we're gonna do。HttP is。Okay。嗯。X R， MuC which me。

So， slash， we are。Slash basic。Then another slash， and that runs the scene。



![](img/04166cf832cf3cd5409b884aa894351f_225.png)

Loads it。 I have it here， it's quite cute already， and I'm going to put it in my cardboard and press the VR button and it goes into VR。

and。I can now look around。 I could also hide the shadow light。 but anyway in the shadow camera。

 And then when I fuse p， light this off。

![](img/04166cf832cf3cd5409b884aa894351f_227.png)

Okay， we kind turn it on， but that is fine， so we've done it basic VR。

With a little bit of interaction cursor basede。 and the next one， the more im mersciful。

 I'm going to do the actual VR controllers okay。In the next episode， we're going to use these。

 All right， so that's it little bit of a walkthrough， didn't always like。

 wasn't always very smooth when I wanted to transition to show you things and then the archist viewer。

 so please forgive me。😊，But yeah， I think in the next few lectures， I'll be better。

 but the A1 is gonna be a little tricky。 So let's see how how I'm gonna do there。

 Hope this was useful。And I'm gonna share the project with you。 Didn't turn out to be the final。

 final thing yet。 So we're gonna do it in the immersive part。 We're gonna add teleport controls。

Going to walk around a little bit。And。That light， spotlight thing。

Maybe we're going to remove that I don't know yet， whether we're going to keep it。 let's see。 Okay。

 See you in the next one。

![](img/04166cf832cf3cd5409b884aa894351f_229.png)

![](img/04166cf832cf3cd5409b884aa894351f_230.png)