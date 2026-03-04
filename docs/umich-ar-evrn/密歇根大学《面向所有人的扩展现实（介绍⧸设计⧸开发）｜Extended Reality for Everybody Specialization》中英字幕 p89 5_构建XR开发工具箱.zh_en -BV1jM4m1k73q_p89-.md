# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p89 5_构建XR开发工具箱.zh_en -BV1jM4m1k73q_p89-

![](img/2e1d1af95b377b1b9e1ce70d872eece1_0.png)

![](img/2e1d1af95b377b1b9e1ce70d872eece1_1.png)

In this lecture， we're going start building our Xr development toolbox。

 My whole goal with this course is to well enable you to learn more about VR and AR technologies by building directly against these technologies and I don't want you to do this like from scratch actually there are lots of tools and toolkits out there that actually make it easier for us And so one of the first important things we have to accomplish is getting a better overview of the space And so this lecture。

 I'm going talk a little bit about the platforms and the toolkits that we have available I'm going show you some examples and and then I'm actually going to talk to you more about what it means to have a toolbox。

 So what I think are the main ingredients。 what are all the things we should put in our toolbox and what are in fact。

 the things we're gonna learn about in more detail throughout the MOOC levels I would say we are covering three platforms。

 So Webex are as a platform unity。😊，And unreal。 So WebexR is an evolving and I hope soon to be fully adopted standard that brings web AR and VR to browsers。

 Okay so basically using the web as an implementation platform and delivery platform for AR VR applications it quite cool。

 And we're going to spend quite some time in WebexR。

 we're going to use aframe as one way to program against Web XR， if you will。 And with Web XR。

 you can reach a number of devices and that I'm going to talk about that next。😊，Unity。

 pretty popular choice， lots of market share makes sense to learn more about unity This is not a unity course though I mean we are learning about unity to learn about ARVR but if you really want to learn about unity you should really go to the Unity website and they have lots of resources there the same for unrealal So the way I cover unrealal here at this stage is like I want to know about unreal I want to know that it's actually has increasing and really getting better at support for ARVR and actually in some ways I would sometimes give it the edge。

Over unity， especially when it comes to immersive authoring。

 it's really nicely integrated the VR support in the editor straightforward。

 So I show you examples of that。 And for the rest of this course。

 I probably spend more time talking about Web XR and unity I just wanted to make sure that our friends from Unreal know。

 we appreciate them and we are hoping for more collaboration and opportunities to do more with Un。

 I think it's a really great platform。 So let's start with a first overview of X platforms and toolkits。

 so I'm gonna map and the following， I'm gonna map a lot of the toolkits that we have available to the different platforms。

 First， we need to distinguish between Vr and AR。 So on the VR side。 we have a number of platforms。

 I'm just going to read them out for now， but I'm gonna have more examples and make it here。

 So aframes team Vr mix reality toolkit Xr interaction and Ocus and5 SDks。

 these are obviously the native SDks from the vendors。 XR interaction as part of unity。😊。

MTK Mi reality Tookit is from Microsoft and works both for Windows Mi reality platforms and Hollolins。

 but also has other support and we're going to learn about that steamVR。

 very popular virtual reality platform and Tookit， well let's say Tookit that abstracts nicely from various VR devices including AcuLs and Vive and then on the AR side we need to distinguish between MacAbased and MacAsAR and so we have AR JS as a webbased approach to MacA-based augmented reality and then Buforia。

 a popular MacAbased AR library for Unity。Mar a less AR。

 we actually have it looks like we have a lot more support there。

 let's say it's been evolving and there a lot of initial support。

 obviously AR Ki and A corere are really powerful platforms on the web we have aframe again has an AR module so that works relatively well I'll clarify on the relatively part AR Foundation and XI interaction are again two things that are built into Unity AR Foundation abstracts from AR kit and AR corere and actually has pretty good support whenever these come out with new features。

 So the Apple platform or the Google platform it doesn't take too long before it makes it into the AR Foundation as part of Unity mixed reality Tookit really started out as hollowlo toolkit。

 so it's no wonder it's here because it used to be focused on HolloLens and then expanded support to Windowsm reality So the whole VR platform of Microsoft and now it actually also。

Tends into A Ki and Air corereps。 So it's becoming a relatively universal platform。

 and then XR interaction is really the X interaction side of unity。

 Both VR and A support and AR support integrates with the AR Foundation。

So what I'm going to do now is I was just going through this very quickly to give you this first overview。

 but now we're gonna look at each of these in a little bit more detail。

 I'm going map them to the platform and I'm going show you which of the devices you can reach at least at this stage。

 So first up is a frame Aframe is a toolkit based on 3GS。

 and then the web and actually integrates with Webex R。 And with aframe。

 which started out really mostly as a Web Vr toolkit you have support across the board for all VR headsets that I've listed here。

And then when it comes to AR， well， you don't actually have support in Aframe directly for MacA based AR via the webcam。

 but you can use ARJS for that， I'm going to show you in a second。And then on the Mac less AR side。

 I would say there is actually the best support right now。

 Aframems AR module works with AR core on Chrome， so that is that is it but with Firefox for I you can actually get it to work。

 there's a Web Xr viewer you get it to work on Acade。 So therefore I。

 but not you can't actually reach it out of the standard browser so that is a little sad at the moment。

 and then it does work on Hollands like can when you configure the browser on Hollands with a few flags。

 you get it to work， but it's not really great support either。So here's an example of aframe。

 This is what it looks like。 It's one of their standard scenes。

 So it's like the standard essence of aframe is the hello WebBR example。

 It has a few primitive shapes in there。 You can see a little bit of light and shadow。

 and then what I put in here is teleportation controls。 So there are components for that。

 and you see a controller model for each of the controllers and that's also customizable I'm using actually laser controls here。

 So you have a raycast coming out。 and that way you can actually start interacting with these objects by pointing at them。

 I do visual appearance changes here just to illustrate that。 and that was a first example。 So Ags。

 as I said， is then on top of aframe and really targets just markerbased we have the webcam markerbased A okay。

😊，So let's look at it what I do here is actually I bring back the same scene we just had I just scale it down a little bit and I'll attach it to the marker and so we're going to learn more about marker based and Marker SR in the specific lectures focused on those but this is just to get an overview and ARJS is based on JS AR Tookit and that is AR Tookit and that's why we see the heroro marker there as one of the examples we're also going to learn more about how to use custom markers and how to design markers for different kinds of markerbased toolkits。

I would never underestimate mark-based AR。 don't think of it as outdated。

 that's actually very powerful for prototyping。 Like look at the flexibility that I have here。

 this could be a specific user interface element if I want to figure out what's the right orientation or scale for it。

 I could quickly prototype this with markers and do an interesting form of immersive authoring using markers。

 It is one of my messages I want to convey through this course so don't think of marker-based AR is dead think of it as a very powerful and useful tool。

 especially for quickly prototyping and developing things。 So SteBR。

 I said it's pretty popular so it works with unity and you can reach a number of VR headsets。

 As5 and Windowsm reality while you'll notice this is a little bit more complex example seen here I'm going jump around to a few different locations and I'm going to try out some of the behaviors at all of these toolkits。

We have example scenes where they show off the interactions， the interactions。

 the support for interactions is really what we are after with in Tookit。

 obviously we want to have support to reach a wide variety of devices but we also want to get off the shelf support for like controllerbased interactions bouncy behaviors here everybody needs a flower grenade bam and you know remote control so I'm going to show you this is quite funny I'm going to jump over there come on okay here we go I'm going to pick up this remote control。

😊，This brings together a few interactions in one。 So now with my virtual reality controller。

 I hold a virtual other controller because that hand is my virtual reality controller。

 It's the steam VR hand， the red one。 And I can now play with his car So it's driving around and it's quite cool。

 and now I really have to show you the that's the you know。😊。

You can get me to use any toolkit as long as you give me a bow and an arrow。

And and and I'm their deal。 So I do like SteamBR。 I've used it in my class。

 at least in one of the years。 and the students did do a really good job。 actually。

 the documentation was fairly poor， I must say。But and I'm going to miss that one。

An example seen like this allows you to quickly learn and adopt if you have a little bit more time that you have spent with the tools like Unity and Unreal mixed reality Tookit。

 we are now entering augmented reality for a bit。 So mixed reality toolkit works pretty well with unity and then it works very well with Hollolens。

 and then it does have support for VR and also a little bit of smartphone based AR。

 So actually relatively growing and broad support。 It does also come。

 There's a mixed reality Tookit version for Unre。 I don't know exactly how advanced it is and how how it compares to the Unity1 I've mostly work with I've actually only worked with Unity1。

So I like mixed reality Tookit， especially when you get to play with it with a Hollolen too。

 this is the hand interactions example here， it's just pretty cool and the way this works is as an example scene bringing together various behaviors and actually what they do very nicely is they're putting all these different widgets next to each other and so you can compare play a little bit of the piano here and so you can compare what these toolkits actually feel like and what their support is。

And I think that is pretty cool。 And you'll see more of this in other parts of this MOoc。 And also。

 when we talk about A， we're going have one lecture dedicated on moving from handhel to head one AR。

 And I'll show you a few more or lens examples there as well。 Otherwise。

 I assume you have access to smart phone or。😊，Otherwise， markerbased AR。

 I think if you are becoming or if you're already a unity fan Vhoria might be a good choice for you Markerbased AR via the webcam and a little bit of support for A core and Aircade and also Hollens so that you can actually combine on the Hollands markerbased AR with the Hollens and then you can switch over to extended tracking It's a concept we learn about seamless switch from Markerbase to Mac less AR。

 So I'm going to show you one of the examples with Vhoria here is as the image targets example So it actually would work。

 and I'll show you this at the end of this video it would work with Mo image targets。

 you can actually get this to work。 Each of these markers here as represented by these images。

 have a 3D object associated to it and the drone。 So the second one is the one that's animated as I run it I connect my webcam here let's run this and I'm gonna hold a marker against the webcam and when。



![](img/2e1d1af95b377b1b9e1ce70d872eece1_3.png)

It comes。Rety visible， the lighting conditions are a little poor right now。

 I'm using a lot of light so that you can see me， but that doesn't work so well with market tracking。

AndBut it does look okay， this astronaut does fairly well on this marker。

 I'm going to try to get the drone to show up here， so the drone is animated。

That looked a little dangerous， but the astronaut has just disappeared。 So that's cool。

 And this drone is animated， as I said。 And we don't have to just have it fixed there above the marker。

 It could actually fly around a little bit more。 So A Foundation I want to cover that next is a platform based on and actually integrated built into unity。

 So it abstracts nicely from Air Cor Air Ki and also has support for Hollolens。

 I'm going to show you one of their samples。 It is actually the X interactions sample combined with A Foundation。

😊，And then you can place objects and can move them when you tap them after you tap them。

 you can then drag them and scale them。 but you are limited to these planes。

 So I have to figure out a way to get to the lower plane。

 and here I can actually then reach the other plane。 So that's pretty cool。

 X interaction is the latest addition to unity and it does work with both AR and VR。

 So since I just showed you an AR example because it was X interaction combined with AR Foundation。

 I'm going to show you the VR example that they have in AR foundation。

 So this is me teleporting and teleportation is something we learn about when we learn more about virtual reality。

 it allows you to travel larger virtual spaces in a constrained physical space that you have or may have。

 And then here you can see a few of their what they call complex grab and。

 I really want to pick up this little I don't know what it is  Lama。And yeah， it looks interesting。

 So that was the first overview a round trip through some of these toolkis。

 so that we get a better understanding of the platforms and the toolkits and how do they work together。

 And this mapping will evolve。 That is the current mental model。

 It's good to have this as a start and the starting point。 And yeah。

 we're gonna expand more on how to learn about。😊，And build our A VR toolbox。

 And that's what I'm gonna focus on in the next。 We're gonna learn how to move and jump， actually。

 from 2D to 3D。 So3 objects and transforms working with 3D models，3 interactions。 Okay。

 so that's the basics。 that's our entrance into VR。 This is actually not VR yet。

 So then we're gonna design for VR。 we have to think about the environment， we need to build a world。

 And then as we do that， we need to think about lines， shadows， animations， spatial sounds。

 not just the visual keep that in mind。 I would say then we enter the space of being a little bit more well immersive。

 but it's initial。 So it's still basic VR interactions。 So traveling。

 We're gonna learn about object selection。 So picking things。😊，And gaze， gesture and speech input。

 Now， speech input， I don't do too much， but there is support。And advanced VR interactions， really。

 we talk about menu design， a lot of placement， more like placement。

 because the actual menu design and the actual design patterns for menu design。

 which we already need for selection。 But then we're also gonna to talk about manipulation。

 so collision detection is one thing。 And then obviously also you need to really apply transforms。

 depending on how you move the controllers or your hands。

 And we're gonna to learn about physics and particle systems along the way。

 I think all these things together would make you a little bit of an expert in Vr just having at least this foundation。

 These are the things that you would be dealing with in VR。 And we're gonna have a case study。

 really really happy that we have this case study。 It's about a zoo a night safari experience。

 well learn about。😊，How to travel in there， how to visit different areas of this zoo。

 The zoo was modeled， but not done in collaboration。 It was modeled after the Detroit zoo。

The Detroit Zoo has very high values when it comes to animal welfare， so。

We have a petting and feeding petting zoo and a feeding area。

 and that is something that is a no no in the reality。 But in virtually we can do these things。

 And the cool thing about our case studies is there。 done with me but not by me。

 they're actually done by students who have worked with me who have learned actually from my courses and doing independent studies and all kinds of things。

 So here we go building your AI toolbox。 that's the other thing that we're really gonna want to accomplish in this course。

 Okay so we're going do this in the following。 So we're gonna make a jump from V to AR。

 So all the AR portions assume that you have done the V portion。 So don't skip ahead。

 Okay we're going cover types of AR displays。 we're going mostly do smartphones。 So handheld。

 but then we're also going to talk about head worn a little bit， but no exercises there。

 at least not for now。😊，Registration， tracking and calibration。

 we're going to talk about those things。 they come through。

 but these are more like that the toolki takes care of for you。

 So you don't actually have to concern yourself too much with it。

 and then we're going to learn about mapping physical to virtual objects。

 This is something basically tracking object recognition and tracking。 So designing for AR。

 then we're gonna learn about motion tracking， really how that works。

 environmental understanding spatial mapping and also semantic scene understanding。

 we're gonna talk about that light estimation we're going to talk about it a little bit that the support for light estimation is growing。

 So light estimation would allow you to render to estimate light at the location where the virtual content is in relative to to the physical world and then adjust the lighting so that it blends in better。

 We're going to learn about markerbased AR。 So we're gonna to learn about marker- based design interactions and then also going from marker based to mark less。

And we're gonna do more Ma less AR。 So Mar less design a little bit more on the interactions there。

 although they can be fairly similar if you're using the right toolkits。

 And so you could even build one solution and then target both Mac based AR and Mac S AR。

 we're gonna to learn about going from handheld AR。 So from the smartphone to head to the Hollands。



![](img/2e1d1af95b377b1b9e1ce70d872eece1_5.png)

And as I just said， we can actually design an app like this one， this is our second case study。

 this is also done by a student of mine Shata Rajaram and she's been she's been really productive in her independent study she did this in a little bit less than five weeks she put this whole project together and we're going to do a Mark Le version of this takes a little bit of way of the fun。

 I must say but it's still a really cool solution in fact we built this one first。

We built the Macless AR version first is something we're going to talk about。

 What's the right order in which to explore these things。

 The goal of this project is to actually bring AR into the classroom。

 and we wanted to use meaningful examples from education。

 but it was still a technological exploration。 it's pretty it's pretty pretty cool if you don't have to worry about the marker。

 sometimes， but as we could see with the paperbased version。

 it can also be very powerful to actually have a marker printed on paper。

 and then also make use of the paper。 Well， I hope you enjoy this little overview。

 And this is what it means to have a toolbox。 and at the end of this course。 My goal is。😊。

For you to feel really comfortable having this overview of the space。

 So you should just be able to just talk about it like I just did here and knowing which toolkit。

 what does it do， what's the support， which platform does it work on what's the current support for Webex are which browser does it not work there do I need Firefox。

 does it work in Safari which by the way， at this stage doesn't Apple， Apple。

 Apple So thanks for joining me in this journey And I hope this was the first good overview that was useful to you。



![](img/2e1d1af95b377b1b9e1ce70d872eece1_7.png)

![](img/2e1d1af95b377b1b9e1ce70d872eece1_8.png)