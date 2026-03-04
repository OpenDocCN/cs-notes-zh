# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p17 16_VR与AR对比分析.zh_en -BV1jM4m1k73q_p17-

![](img/373afc5c5994b3470dae5ee94f2ce225_0.png)

![](img/373afc5c5994b3470dae5ee94f2ce225_1.png)

In this video I'm going to present well some ideas towards an Xile decision tree。

 we've just been introduced to VR and AR， both the concepts and the technologies in a little bit more detail and as you will experience if you're working in this space people will ask you for your advice on which technology to choose when and why。

And now I happen to be somebody who has been working on a lot of projects already and I have kind of like developed some intuition towards when to use AR and when to use VR and maybe when not to use either of them and this is something that I'd like you to develop as well。

 so the idea for this lecture is to give you a decision tree。😊，Now， it's not that simple。

 I've been thinking a lot about how to best teach this and what is this decision tree。😊，And well。

 here is a version of this decision tree。So the whole idea behind this lecture is to be able to answer some of these questions。

 the ones that you have to ask yourself when you engage in a new project。

Should it be VR or AR or is neither a good idea？What kind of AR。

 VR display and tracking technologies should we choose？

What are the benefits of each and what are the challenges and what are the limitations？

Which types of platforms and devices should we support？This is not straightforward。

 this is an increasingly complex and diverse technology landscape。

 if you remember looking at this together with me， it is really quite diverse。And finally。

 which tools should we use and then both for design and development。

 there's a number of tools out there， there's actually so many tools out there。

 it is quite difficult to well maintain an overview of you're in the space and then for somebody new to this space。

 it's even worse。So when it comes to the question of whether to do VR or AR。

 we already have some advice from very experienced people like Mark Binghurst， for example。

So he says VR is ideal if there is lots of visual elements and I agree with him there。

 3D spatial interaction that makes a lot of sense， if there is physical manipulation。

 then he says procedural learning but I wanted to talk about interaction at infinite resolution。

So let's think about this for a second Okay， so here I have the quest and one of the controllers。

So lots of visual elements that makes sense， right， We like going in there and it makes us feel like。

 wow， we can see so much content， even though as you know。

 some of the Vr displays are smartphone based essentially the screen real estate that we have is not larger。

 but because of the agency in autonomy and this idea of really being able to look around and immerse ourselves with this content。

 even walk through it and then interact with it spatially in 3D that really makes the Vr quite a platform for these kinds of experiences。

 this is really where it is ideal。 physical manipulation that makes a lot of sense。

 Now we even have hand tracking。😊，Even though， I mean， unless this content like。

 I'm not sure whether wantanna rotate cubes and chas and whatever， like with my hands。

I mean it looks cool a minority report， but frankly it is not ergonomic and it's not really the most usable experience in that way anyway。

 we can do a lot with these controllers so that's fine so physical manipulation if you will or direct manipulation is definitely something that I can see as well and then I said interaction at infinite scale。

😊，Now， when it comes to AR， there's usually some relationship between this virtual content and the real world that we see now in VR we don't actually have that connection to the real world。

 and so I say interaction at In scale because we can make something super large and still kind of comprehended and see it despite the limited screen real estate that we actually have just because of how free we are with moving around in the space and looking at it。

😊，And so yeah， that actually then enables interaction at really， really large scale。

 we can also make something super tiny and super small and then still interact with it。

 And so I think that is where virtual reality is really fascinating。😊，On the other hand。

 AR is ideal if there are some visual elements， not obviously everything visual and virtual because then it would be VR3 spatial interaction and physical manipulation are just as good with AR。

 if not better。And then interaction is either at one to one scale。

 so between the virtual content and the real world it really fits in there like life size content or less larger than one to one scale usually doesn't make it all obious because of the limited field of view that we usually have。

 so it's not as immersive as we can do it with occluded displays like the Ocus Que。😊。

And so that's why I say interaction， not an infinite resolution， but at one to one scale。

 I think this is where it is really interesting because you get a sense for what like when I buy furniture。

 I want to really have one to one scale I want to make sure it actually fits in here and that's where I think AR is really good Now VR wouldn't be a good idea for furniture placement if I'm in this room。

 it doesn't make a lot of sense to not see the room。

 So one to one scale is I think the best application of AR at least in this example。😊。

On the other hand， if you're looking at when things are not ideal。

 So VR is not ideal if there are many nonvis elements。 Yeah， what do you actually show to users。

 Is it a white or black screen mostly that do you show， Well， you think about it。

Lots of text to read or input and both reading and input are very cumbersome and tiring， actually。

 even with some of the best input methods that we have now， including speech。😊。

It's also not idea if there is a need for haptic feedback and this is something that Mark Bdinghurst。

 and I also agree on， I would just say based on the fact that unless there is some kind of mapping between the virtual content in the physical world。

 any need for haptic feedback usually requires some additional user instrumentation or some additional device like blowing air at the user or something to produce this kind of haptic feedback and these devices require a lot of calibration and need to be instrumented and installed very carefully so usually not ideal。

And then if there is a need for connecting with the real world， then this is really a case for AR。

 not for VR， so keep this in mind。And then AR， on the other hand。

 is not ideal if there is also many non- visualual elements。

 although I do think that AR experiences can work， that I'm mostly audio based。

 we haven't seen so many examples of that。When there is lots of text to read or input。

 it's also not good with AR。And unless you have， for example， character recognition。

 like I can write on a sheet of paper and that would be captured automatically in AR and then I can process it further。

 that is actually exciting and in fact something we're working on at the moment。

When there is a need for hap big feedback， I would also say AR is not ideal unless there is actually a connection with the real world。

So you can map， obviously， if you're interacting with the real physical world around you。

 then I think it's fine。 if， if that AR application is really designed for that space。

 you basically have haptic feedback。😊，When it comes to haptic feedback。

 I like some of the design choices the Hollands2 made。 so for example。

 now when you're opening a start menu， you're looking at your wrist and then you're actually touching there so you have like this self actuated kind of force feedback because you're touching same with this gesture it gives you some resistance as you're touching the thumb so I think that's quite smart。

 So we're using our own body to provide haptic feedback I think that's very interesting and that's where actually AR can work。

Finally， if there is no connection to the real world around you。

 then really this is not a case for AR， I think you should look at a VR instead。

 so before we really come to our decision tree， let's first review what kinds of technology choices we actually have。

 what options do we have before we make any decisions。😊，Well， obviously， on the display side。

 I've introduced you to a few different types of displays from headmon to room size。

AR displays are a variety handheld， head wornor， spatials or projective or monitor based。

 we covered those。 we also talked about tracking three degrees of freedom versus the 6 degrees of freedom。

 it discussed about outside in and inside out we understand head tracking and eye gaze I mean so head gaze is really like most VR unless the device actually has built in eye tracking or you extended it with an eye tracker it actually really just tracks your your head and so if your application needs eye tracking。

 then you have to think about that how do you actually provide that support。And then。Well。

 you can also think about what other things to track。 Obviously， you have controllers。

 And in some devices like the Acus Que， you have hand tracking built in。

You may choose things like need Mo as I showed you earlier。

 so that you can attach to the VR headset and then provide a form of hand tracking as well。

On the A side， you have to think about on the A side。

 one of the most important decisions you have to make is whether you want to do market based or Mark less AR。

 It really has a number of technological implications。

 And then you have to think about how much of the real world around you， Do you have to understand。

 So is plane detection sufficient or do you need 3D spatial mesh。

 This usually requires a little more advanced technologies。

 sometimes even additional types of cameras， including depth cameras， like we have with the key neck。

 the Hollolens or the real sense。And whether you need to track physical objects。

 it's something you also have to think about， So either you train the system beforehand。

 you attach markers to those physical objects or you use some specific machine learning based libraries that allow you to detect some physical objects。

And there are actually additional considerations。 So I simplified a little bit。 But as you can see。

 lots of choices to be made。😊，So these are the technologies considered by themselves for each AR and VR and how do they actually translate through different kinds of platforms and devices if you're using off the shelf devices。

 So obviously on the VR side， we can choose between something that is phone based like cardboard。

 which is really on the low end up to something like maybe the latest Rift S quest。

Oculus Que 2 coming on soon at the time of this recording。

 So these are some of the most advanced virtual reality head monitor displays that we have。

 You could also look into caves， but I just left that out for now。So for AR， we can do the same。

 We can rank the technologies， rank order the technologies and from the low end spectrum to the high end spectrum。

 So I would put markerbased， usually on the phone or some kind of webcam based applications on the left marks if I'm thinking on the phone。

 It's kind of like medium end and then on the high end。

 I would put wearable AR So head monitor displays with 6 degrees of freedom So the holens on the magic leap。

 This is probably also the understanding that you have at this stage。

 And this is what I would expect if I ask you how do how would you rank order the following devices。

 And then I give you in some random order。 like Windows mixix。

 the as go and then hoends and smartphone。So the technology landscape is even larger。

 I said need I said we need to pick tools so we can pick tools from the more design oriented。

 so 360 authoring， there may be a little bit of 3D immersive authoring。

 so working directly in VR or then using more like development tools that are listed down here。

So then on the A side we can also look at libraries that are more dedicated to specific types of tracking like marker based。

 body based tracking libraries and tools here， we can also look into immersive authoring so these I would say this is where I would draw the line maybe this is more designer oriented tools。

And then more the developer arent the tools。 So AR Foundation。

 external interaction for the toolkit for Unity， AR Cor Air kit or MRTK and some other like。

Some other solutions as well， so these are obviously down here really the frameworks for development and of there other tools that will help us in the earlier stages of design many times they actually target designers。



![](img/373afc5c5994b3470dae5ee94f2ce225_3.png)

![](img/373afc5c5994b3470dae5ee94f2ce225_4.png)