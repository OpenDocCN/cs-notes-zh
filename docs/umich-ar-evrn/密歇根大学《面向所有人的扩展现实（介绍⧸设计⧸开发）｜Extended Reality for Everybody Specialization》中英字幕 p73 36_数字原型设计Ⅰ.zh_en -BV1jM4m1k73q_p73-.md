# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p73 36_数字原型设计Ⅰ.zh_en -BV1jM4m1k73q_p73-

![](img/ab019d05be96b622be2846eac465176a_0.png)

![](img/ab019d05be96b622be2846eac465176a_1.png)

So we're still talking about designing XR experiences。

 but we're moving into digital prototyping space。 And what I'm gonna to do in this segment is really focus on。

 well， how do we take， for example， our storyboards that we created on paper or our physical prototypes。

 How do we take them to the next level in terms of fidelity。 How do we take it into digital。

 And I'm gonna talk about a few techniques in digital prototyping up to the point of actually doing it in immersive authoring using AR and VR devices。

So let's watch a quick video of what I'm talking about。

He is now moving around the object and capturing the Plato figure。

The information will be live streamed back to the editor where the video is available immediately。

He is now access to an additional resource in the collect pane。

 which he can preview in the capture pane on the right and could actually recapture if necessary。

In this case， the designer is however satisfied。 And all he needs to do is actually drag and drop the Plato model capture into his AR scene。

He's enabling the marker tracking， and inserting the object。He's enabling the market trackingre。

And he can immediately preview the object above the marker。

 He disabled the digital marker representation。 And now he's showcasing how。

Proray R renders perspective frames， depending on camera movement。

This gives him a first sense of the air interface he wanted to create with pro in this case。

 in less than two minutes。Now this is just one way of prototyping things and it's something that I've come up in research and it's not exactly the kinds of tools that you have available as a product。

So more generally speaking， what does the X tools landscape look like as a little bit of a reminder。

 we obviously have digital and immersive authoring。 So we have existing tools here。

 and I just give some examples。 keep in mind that some of these examples are current examples。

 And we don't know yet whether the tool that I list here is still around tomorrow。

 So we have digital and immersive authoring。 We have web based development。

 So this is this whole idea of building on the Web Xr specification。

 and then we have tools like a frame that I've talked about earlier。😊。

We can do a kind of cross platform development approach。 Well， popular choices are unity and unreal。

 These are these game engines that I talked about earlier that are usually combined with some kind of AR。

 VR software development kit or SDK from popular vendors like Acus Vive， Microsoft。

You can also specifically target devices and do native development。

 so this is the fourth approach the fourth big category of tools you could choose a particular SDK like the cardboard。

 Os or wife SDK to develop for these specific types of platforms and devices。

So this is the overall landscape and as you can tell， some of them actually require programming。

 some of these tools like Unity Un with the software development kits or native development actually do require quite a lot of experience and programming background。

So。What are these approaches good for， I think the digital and immersive authoring tools that I want to introduce you to are good for storyboarding。

 but then there are limited， there's limited support for interactions。 So you can do a few things。

 But you will very quickly realize there's not so much you can do after initial prototyping。

 So after that， you need to choose one of these three possible paths through the web cross platform or native。

 So the Web based approach， I think is very good for X apps that have some basic interactions。

 sometimes it still feels a little unfinished with current Web Xr approaches。

 if you compare to a unity or unreal experience。 So these would be in the cross platform development approach。

😊，These are actually good for full fledged X R apps。 They， they're really visually stunning。

 sometime， sometimes you can really create really nicely looking experiences there。

 But I also think they， the， the cost is pretty high。

 The learning these tools usually comes with a very high learning curve。😊。

Depending on the path and the background， remember， I talked about path to being an Xile creator。

 If you have a game dev background， unity and unreal feel very natural to you。 But if you're coming。

 if you're like me and coming more like from a web dev background， it'll。

 it'll be a little harder for you to pick up those tools quickly。Finally。

 the native development approach is actually good for， again。

 full flged XR apps and exploiting platform specific or device specific features， even。

 So in some sense， it's like the best experience you can create。

 But the issue is that you kind of like locked in with a particular wise platform of vendor and that is limits the experience。

 It limits the the the numbers of users that you can reach。😊。

So now let's really talk about just digital and immersive authoring。 So digital prototyping。

 I want to do it the same way as I did it for physical prototyping。 Again。

 we're thinking about low fidelity to high fidelity。

 and keep in mind the digital prototyping should be closer to high fidelity like the experience should be closer to the final thing that we imagine。

 And then again， there are methods that I want to tell you about that some of them are easier And some of them are harder。

 So how does it how does it actually work for digital prototyping。 So digital authoring。

 which is a specific set of tools that allow you to create things through visual authoring。

 It's like using an editor， click and play in some sense。

 and then you can run these experience often directly on an AR device， for example。

 show you some of these tools。Immersive authoring is actually。

 it really means that you're working in AR or in VR。

 So the way you interact with the content at this level is quite different。

 You're really immersed in VR or in AR and the tools need to translate a little bit。

 So you imagine that with immersive authoring， you're really going inside VR or A。

 you're putting on your head and then obviously the interactions change you need to think about oh。

 the user doesn't actually see the real world anymore。

 how do they interact with the objects in physical space and so immersive authoring is really but you're really testing as you're designing it。

 So it's actually quite an interesting way of prototyping。

 and I'll show you some of the tools in that space in both cases。

 with digital authoring and immersive authoring is really subject to the limitations of what you can prototype with these tools。

 So if you're moving into the other ones that I talked about the other approaches where based development。

 crossplform development with unity or unreal or native development specifically for some of the software development kits for some。



![](img/ab019d05be96b622be2846eac465176a_3.png)

The ARVR devices that we have out there。Then you're moving slowly。

 but definitely into that space where it becomes a lot harder to do。

 But you also can create a lot of richer experiences。 So you're moving towards high fidelity。

 but also， it is hard。 Now， I wouldn't actually。😊，Say that all of this is digital prototyping。

 When I use the word digital prototyping， I want to draw I want to draw the boundary here around from digital authoring tools。

 these kick and play tools through immersive authoring。

 doing things in Ar or Vr as opposed to just 3D on a laptop or desktop and then web based development and just scratching a little bit of crossplat here because I think the unity and the unreal editor。

 as long as you do not have to write your own scripts for interactions。

 I still think of them as a tool for prototyping。 So I still that's what I wanted to that's what I wanted to illustrate by drawing the circle and the boundaries that way。

 now let's zoom into this circle of prototyping tools。

 and I want to start with digital authoring tools for Vr。 And unlike what you might expect。

 I've selected Amazon Sumarian and unity but just the unity editor part of it。

 I don't refer to unity as the bigger game engine and the whole platform with C sharp and scripting and all that。

 just as a visual authoring tool。😊，I think it is a very popular choice。

 A lot of people prototype directly in unity。 So what does what does it mean。

 what it can you do with these digital authoring tools， Well most of them support visual authoring。

 So using a mouse and a keyboard and navigating with you know first person shooter kinds of experiences with WSD and those kinds of things。

 I give you an into to that later。 But they support visual authoring of 3D scene graphs。

 So essentially hierarchies of 3D objects。 And then they also do support VR previews。

 So often it's just a matter of quickly connecting your VR device or going through some deployment method to actually quickly deploy to this quest here and then previewing that thing that you just created and being happy if you did it right。

 But the workflow is really like using the desktop putting on a VR AR device and and testing it that way。

😊，And alluding to other tools here， Imersive authoring would give you the advantage that you do everything in ARVR。

😊，But just staying with digital authoring tools。 so you can do basic interactions without programming。

 you can actually you have usually access to basic interactions like the user looking at things or the user clicking things with a VR controller or touching things on their phone。

Those things are usually available in these tools。 You can also do some more advanced interactions。

 but this is hard， Sometimes you may add specific toolkits to it。 like for example。

 unity has the Excel interactions toolkit or Microsoft is working on the mixed reality toolkit there is also a virtual reality toolkit VrtK So if you add these kinds of libraries to it。

 you may get away without having to write love your code but yeah， to do advanced interactions。

 There is usually in no way around writing code。 So the next group of tools is digital authoring tools for AR。

 So how does AR differ well， there's a different set of tools out here and they differ in that they actually support visual authoring of either Macab based or Mac less AR apps we learn more about what that means but in the Macab based scenario all you would do is actually use one of the markers that they usually have and hold it up in front of the camera and then use this for tracking so。

The way I would interact with it is using my。By phone against the marker and then prototyping this way。

So you can do this with the default markers that are provided like the astronaut I just showed you。

 or you can also create custom markers in later stages of the prototyping experience。

 I would often just use default markers to begin with because they track really well。

 The SDKs work well with them。 And then custom markers is something when you w to advance into the prototyping stage and maybe building something more like a minimum viable product that gives it a specific theme。

The last characteristic of digital authoring tools for AR is that they typically enable augmented reality previews。

 either through some kind of software that you download onto your computer or I have like inbuil into the prototyping tool like in the case of lens Studio here。

 So we call this an emulator or some kind of sending it to device usually requires to connect the AR device。

 maybe a smartphone via UB to the computer and quickly deploy to it for testing So as I was talking about these digital authoring tools。

 I was also pointing out some of their limitations and what makes it cumbersome when it comes to actually working with AR VR you often have to deploy to device to actually get a preview because existing emulators or existing previews are often not good enough。

So this is where immersive authoring tools really have an advantage and play an important role。

 Again， I would distinguish between immersive authoring tools for VR and AR here I show you two for VR。

 So the two examples I wanted to give here is Google blockslocks and Archchisquill。

 So they are both immersive authoring tools for VR。 imagine that I've done these prototypes。

 these digital prototypes that you see here。 I've done them while I was in a VR headset。😊。

And in one case， I was working with primitive shapes and I was working on a chair in Google blockslocks。

 You may not be able to see it， but that was the idea I' try to create a 3D model because I needed it for my furniture placement application。

 and I wanted to do immersively in VR even though the final experience maybe in AR。

 these immersive authoring tools for Vr are a good way of prototyping 3D objects that finally end up in an AR or a VR experience It really doesn't matter。

 But using Vr to prototype and at the bottom， you see Oculus quill。

 which is more like a 3D sketching tool for VR it's similar to tiltbrush。

 which you have seen in other segments of this specialization and what is interesting about quill is that they actually move the entire authoring environment。

 kind of like reminds you of flash or micromedia director if you've ever worked with these tools where can do keyframebased animations。

 and you can actually do the same in VR and that's something I still have to learn。😊。

A little bit more it's actually quite tedious to use the tools in VR。 But in principle。

 these immersive authoring tools for VR enable visual authoring， but in 3D， right， you do it in VR。

 So that's quite different from digital authoring in itself。😊，How is it different， Well。

 they make it possible to edit while at the same time you're previewing it in VR。

 So the whole time you are in VR。 and that is quite a different experience。

 I would say that the overall tool support of existing immersive authoring tools。

 is really with a focus on 3D modeling， there is support for animation and some kind of scripting in some of these tools。

 but really， since you're doing it in Vr， you really don't want to have a keyboard and write code。

 and stepwise animation， even if it's key framebased and intelligent in some sense。

 is still relatively tedious。 So I think these tools are best used for doing some kind of 3D modeling and previsization for example。

 of the 3D models you have later or the environment that the user will be using。

 and that's where these tools are really good。😊。

![](img/ab019d05be96b622be2846eac465176a_5.png)

![](img/ab019d05be96b622be2846eac465176a_6.png)

They typically actually support export to common 3D model formats。 So this is actually quite useful。

 In fact， Google blockslocks here that you can see actually you can share directly to Google Poly。

 And in that case， you can find lots of 3D models online that other people have created with these immersive authoring tools。

 You can see them as inspiration or like to push yourselves a little bit。

 There are really people who are really skilled with it。 Sketchfab as an online platform。

 well people actually share the 3D models for free。

 some of which may have been created with some of these immersive authoring tools， Often， however。

 they actually use professional 3D modeling software。😊。



![](img/ab019d05be96b622be2846eac465176a_8.png)

And。And Google Stch or 3D warehouse is the other kind of platform that is often used for sharing these kinds of models。

Okay， let's look at immersive authoring tools for A。 So there is a set of tools emerging。

 for example， Apple's reality composer that you can run directly on your iPad or Adobearrow。

 So what you do with many of them as you use your tablet as your viewfinder。

 a tablet that has AR capabilities。 And then you can also do immersive authoring。

 you're not as immersed as in VR。 But you can actually make use a physical space and walk around and zoom these objects here that I show you on the left。

 I did the same example in both of these， I just actually placed a 3D model in my office。

 And so Apple's reality composer as one example。😊，Adobearrow is another。

 So what do these tools actually do， Well they enable visual authoring of 3D content in augmented reality。

They make it possible for you to edit these experiences as you are creating them and you're previewing them at the same time。

 So you don't actually have to do something on a laptop or desktop and then deploy to your device。

 No you're working directly on these AR devices。 And in this case。

 you also design specifically usually for the environment that you're in。

 So the examples I showed here on the left while not particularly tied to these specific environment。

 I just place cubes in there。 often when you do immersive authoring with these kinds of tools。

 you really want to do it in the environment that you're designing for when you're using these tools for AR。

😊，The existing tools provide relatively basic support for interactive behaviors。

 any kind of advanced fancy gestures or any kind of， oh。

 let's just use this speech command or whatnot， those kinds of things would still require programming。

 there's often not support for that， but you do have locationbased triggers。 So， for example。

 as you're going towards an object or clicking a virtual object or bringing some kind of marker into the view。

 all of these kinds of things would be supported， usually without programming。

Some of these tools also actually support exporting to WebExR so that you can actually then continue editing the experiences you have prototyped this way in a tool like a frame which we are using in this MOC specializations。



![](img/ab019d05be96b622be2846eac465176a_10.png)

So here I'm showing Apple reality composer， I have a very simple scene and just have an object。

 a cube in there that I can author digitally so I can rotate and scale。Actually， both of all。

 but also the object。うん。So rotation and basically have access to all the transform tools here scanning as well。

 But so this is just digitally。 But what I actually want to do is immersive authoring。

 So I'm actually going go into AR。 So you scanning the environment very quickly。

 that places the object in the world。 And now I can look at it and author it。Immersively， so here。

 basically。Go to change the way it looks。To Matt to maybe some kind of interesting reflections as the properties going to go down quickly to let you see this a little bit better。

 how this might look。 or we're going to go for this kind of car paint look。Or aluminumin。

And can basically play around until we are happy with it。

 Not too much we can do with this simple 3D object。

 There are other ways of actually bringing in other kinds of 3D models。

 but I just wanted to show very quickly how we can do immersive authoring on an iPad and AR as well。

😊，So this was a quick overview of the first set of tools in digital prototyping specifically as it relates to digital authoring tools and immersive authoring tools。

 and in another video I look into more detail into aframe and unity as some of the other tools you may be using for digital prototyping as well。



![](img/ab019d05be96b622be2846eac465176a_12.png)

![](img/ab019d05be96b622be2846eac465176a_13.png)