# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p116 32_无标记AR开发第二部分.zh_en -BV1jM4m1k73q_p116-

![](img/52cfd54d1c22cc85478969a06a7a8130_0.png)

![](img/52cfd54d1c22cc85478969a06a7a8130_1.png)

Coming back to our case study， I wna look at the case study again and talk a little bit more about marker based interactions。

 So actually marker less interactions。 So these were the ones we had as mark in the marker based version。

 And then in the marker less， they are the same， but they change a little bit how we have implemented them。

 So we have placing， but not placing the marker， but picking a plane。😊，So that's the first step。

 So placing means you're， you're moving the device and be rendering an indicator。

 we're rendering an indicator here， a yellow indicator。 That's just one way to do it。

 And then once the user has picked where to place it。

 then the interface actually appears at this very position。

so basically establishing the 3D coordinate system that we can start pointing at the at the content。

 And it appears the tracking kicks in， the Macs tracking kicks in。

 So we don't have to pay attention to keeping anything in view。

 If we move the device this way or that way we obviously don't see the virtual content anymore because it is rendered。

 It's anchored there。 It's like fixed in the world in in in real in the real world。

 And that's how the whole AI experience works。 But we can point at it。

If if I were to point around the device。 So behind the device。

 let's say I really feel like I want to point into into the virtual world with peoples segmentation。

 which doesn't work on AR core， but it works on the iPad if we were to enable this。

 We could actually point at the virtual content and occlude parts of it with our fingers。

 I've tried this out。 is not perfect， but it does even work down to the fingers to some extent。

 So it it it will require somewhat much training and depends how you define the thresholds for the segmentation。

 but very soon we'll be able to seamlessly interact with virtual content we can point at it directly in the physical world and still occlude it perfectly。

Tapping so you can just tap on the content。 what you cannot do right now。

 at least in our implementation is reach behind the device and do like behind the device interactions actually tapping。

 if you did hand tracking。 That's something I'll show you more with the Hollands right now。

 the current state of implementation。 These are all different kinds of technologies that are sometimes available and sometimes not。

 So A core doesn't support a hand tracking。 And so we had to use lean touch so basically doing on on screen on device touch interactions。

 multitouch interactions。 We also have dragging a drag and drop as before。

So what does that mean in terms of Macs AR applications。 So， yes。

 it is really targeted more high end devices。 It's not the super high end。 So it's not like， I mean。

 obviously， Macs AR is also what what what works， what powers the holens。

 And so that would be very high end devices。 But let's just say relatively high end because now you're targeting smartphone based generation that is 2017 or later。

 And yes， most of us upgraded our phones。 but not everybody can afford this。 So think about that。😊。

That we don't actually， if you're designing a solution and you you're picking Mac S AR。

 it does have a significant impact on who you can reach。 Also， if you're then looking at Webex R。

 Webex R is like super experimental right now and doing Mac best AR is is kind of fine。

 But the interactions work pretty poorly in A R Gs with So a frame based， It's not exactly Webex R。

 but building building on the Webex R specification， we are building。

 we right now as I was developing some of my demos we get hit testing into these now。

 So we have hit testing in there now so that we can actually。😊。

Determine when you going to show you this when you when you obviously like you have the plane detected and now you want to place the content。

 you are extending array ray into the scene from that point on on the screen。

 into the into the scene and detecting where hits the surface。

 And this is where the where the content will appear。 This is called hit testing。

 we covered this ray casting and hit testing in the virtual reality lecture。

 and that applies here as well。 And it just applies to the physical world and approximated and represented by virtual planes and surfaces。

So yeah， we have basic support for that。And actually rendering content on top of the AR scene。

 So that's called Do overlays and Webex R。 that requires is this experimental it didn't work。

 I couldn't implement it nicely。 And so it was a bit sad。 But you know， in a few months。

 it's gonna be available。 And you won't even had I not talked about it here wouldn you wouldn't even have noticed。

 So I just dated the lecture， but that's just fine because if you were expecting to see something cooler than if you've seen cooler demos recently。

 I'm showing you the latest stuff I can do right now as I'm recording this。

 And but the world moves on。 And in a few months， I expect to be able to do cooler demos even。

And still， I would say。Mar or less A applications， especially when you think about accessibility。

 like really like think about it， we can do， especially with a holo lens。

 where we we have even more advanced spatial AR， not spatial A。

 That's actually the wrong term spatial mapping in these devices。

 And then we can do semantic scene understanding on top of that。

 so we can actually understand what we're looking at。😊。

That is valuable information that we can give to， for example， people with special needs。

 if then the main challenge becomes the user experience design。

 If you figured out the classification and all that and doing it undvised rather than offing to the cloud。

 again， interesting， interesting times。 So seen understanding。

 I think will be and even more important A application。

 also that you can actually start annotating things like these common repair scenarios relatively boring from my perspective。

 But I understand， yes， so everybody wants to repair things remotely or do tele telemedicine remotely and it's always good to have somebody who can give you instructions by sketching into into your like before your chalk styleland remote interactions like Skype。

 you can then sketch into the world remotely。 And then it appears for the user here。

 So these kinds of that require spatial mapping and scene understanding。

 I think that's like where you really。😊，We Michaelel S AR and some of these advanced techniques。

Ultimately， I think right now， these techniques will allow you to implement more believable experiences。

 not realistic。 I wouldn't say like we don't we don not actually there that we can actually really blend the the world seamlessly。

 the virtual and the physical world， we can make a believable occlusion rendering。

 as I was showing in some of the examples is key to that。 And then light estimation， which I。

 I had an example from Air core in the foundations lectures。

 So as part of the first course in this X MO specialization。😊，But yeah。

 so that light estimation stuff isn't really well used yet in current applications。

 if it is more used， then we will actually have more believable experience。

 So less to do when it comes to the suspension of thisbelief。😊。



![](img/52cfd54d1c22cc85478969a06a7a8130_3.png)

All right。As before， I'm gonna bring back our zoo。 I just love that zoo。

 So we learned a lot about AR through Keplla's laws。 but here is the zoo again。😊。

So we can actually learn， we can actually apply the things we've learned for VR also to Macca S A R。

 So you could bring in one animal like this giraffe。

 And if you compare this to the Maca based experience， now I can actually have a life size。

 a room size。 Here it is。😊，I mean， it's not high Poly。

 This is a actually done with Google blockslocks， and it's done by Poly。 It's like on Poly。

 you can get this giffe。 It's for free。 It's public domain。 That's why I'm allowed to show it here。

And you can actually place it there。And yeah， it's pretty， it's pretty cool。 you can go closer。

 If this were more detailed content， it would be nicer。 Obviously。

 you could explore high polygon stuff。 So you could actually look at it in more detail。

 My giraffe is pretty simple。 The one that we have here。😊。



![](img/52cfd54d1c22cc85478969a06a7a8130_5.png)

But this is pretty cool。And we can。 And now this is gonna be fun。 I wanted to show you this， okay。😊。

So for this  one， I was really going on the floor and I was bringing back all the animals。

 And I'm going down onto the zoo。 Here we go。And you see some of the animals how they are like really。

 wellow， really， you see some issues with the tracking。 like when you're having content of this size。

 content that size， but the scale is still pretty big， right， I'm almost doing the entire room。

 But so the， the tracking isn't perfect。 It doesn't seem as stable。

 If I were to run this whole thing on the holen。It would work even better。 And I must say。

 obviously some of the lighting conditions weren't probably ideal for A core， but that's what I mean。

 not realistic， at least not photorealistic， but believable， at least to some extent， meaningful。

 I could really explore this zoo。 Now I could in my mind and develop this mental model of where these animals are in the virtual reality zoo。

 And then I was since I didn't change the spatial layout。

 I knew roughly what that means for how this maps onto the physical world here。

 And it' just a fun experience。 and obviously having some key animals like these giraffes and zebras。

 they really are because they are so visible， they're like visual cues。

 they really help the user orient。 And that's something you could build into your own experiences as well。

 as you're designing something So yes， so that is now my Mac' A version and even reallyvisited some of the elements from the VR portion。

 So keep in mind。 So hit testing and raycasting really still plays。😊。

Ro all the things you've learned a lot about basic 3D scenes， geometry mesh。

 all the things we did in the first week， the things we did in the second week focus on VR still。

 you need to carry this with you because then it's easier for you to learn about AR。

 And we learn about marker based and marker less A。 So these things all kind of relate to each other。

 And in the end， that's when it comes to really making thoughtful decisions。

 Now you have a relatively complete toolbox。 one thing we're gonna look at is marker less AR and then comparing actually handheld versus head。

 So we're gonna look a little more at thes super high end。

 if you will range of devices have a lecture on that。 I wanted to cover that as well。😊，But yeah。

 with this， there's a lot of things you can do in the honest track。

 So take a look at that if we wanted to learn more about how to implement Markbase， Mark less AR。

 And now would be a good time to， to check out that content。 I really make it hopefully accessible。

 sharing projects with you and trying to maintain it so that you can do things with unity and with Webex are。

 And that's gonna be a challenge to actually maintain it over the next few months。 and if not years。

 So let's see how that goes。😊，Yes， so I'll see you in the next segment。



![](img/52cfd54d1c22cc85478969a06a7a8130_7.png)