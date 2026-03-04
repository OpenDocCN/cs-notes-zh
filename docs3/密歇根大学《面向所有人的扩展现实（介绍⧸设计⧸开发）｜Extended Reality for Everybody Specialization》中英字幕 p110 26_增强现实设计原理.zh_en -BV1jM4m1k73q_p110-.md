# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p110 26_增强现实设计原理.zh_en -BV1jM4m1k73q_p110-

![](img/a365f5d636c40d97ac278e3c1f871fb7_0.png)

![](img/a365f5d636c40d97ac278e3c1f871fb7_1.png)

In this lecture， we're going to talk about designing an augmented reality。

 So not the virtual reality， but an augmented reality。

 So the whole point is that we need to start thinking about how to translate and transfer our knowledge from designing for virtual reality。

 How does it actually translate to augmented reality。

 There's a lot of things that are in common between AR and VR。 And so in this lecture。

 I assume that you know about VR。 So my previous lectures on Vr design。

And we can then focus on what's really different and special with augmented reality。

So we're gonna to have a case study here as well。 So our case study is done in unity。

 Its actually it was an independent study that I did with my student whos now a PhD student with me Schar Rajara and we explored an AR well educationbased simulation keptless law of planetary motion and we actually visualized all three laws and we doing it with markerbased AR。

 So here on paper you don't really see it exactly but the paper functions as a marker。

 It also has information about the law and we're using it in very interesting ways。

 So it's really a nice I think in my opinion， it's a nice use of Mac-based AR。

 It's designed for tabletop scale and we also have a mark less version of it。

 So now I'm going to give you a quick overview of each of the projects showing you some of the interactions that we have implemented so。

😊，と？In our case study， we're going to learn about Macbase design with Lahoria。

Here you see all three laws。 This is the first law on paper。

 And then we have you're using a smartphone。 So we have essentially you're holding the phone above the paper。

 and then you can interact with paper， just like we did switch to a different law here。

And you can also then manipulate some of the parameters for each of the laws through the smartphone。

 So you actually have an interface on the smartphone and what I'm showing right now is actually what you see on the screen。

 you can tap the simulation to pause it， for example。

 and then you can tap again to continue playing it。

Keep in mind that the user is holding the phone above the paper and using the paper as a marker and what is fascinating about markerbase A are is actually how you have control。

 very easy control over where the AR experience takes place， the scale of the AR experience。

 depending on how large you print the marker and how you design for the markers。

And it can actually be really cool。 Like， you can see how these planets are now floating。😊，On paper。

 and I'm analyzing a little bit some of the alignment issues we have with paper。 But that's fine。

 I mean， it is a， it is a still relatively robust market tracking solution before foia that we're using here。

😊，And it works actually， quite nicely。So we are also going to learn about a Macs AR version using AR foundation。

In the project， interestingly， we started with this version first。

 but the way we're going to learn about AR in this course is through looking at MAA based first and then MA S AR。

What you can see here， if you compare it in terms of the interaction design。

 there's no more paper now it's its Mac less。 so you can place it wherever。

 I still place it on the tabletop in my example。 But then we had to think about how do we actually transition between the loss。

 you can't transition between paper anymore。 So we actually brought up this tabbed interface and Sta and I regret a little bit that vertical design of that tab in a tabbed interface but in retro you know retrospectively we feel like we should have maybe designed this a little bit differently because。

We felt like， it's not so easy to keep everything in view。 But then when I demo it。

 like the way I demo it here， Does't it look cool。 I think it's pretty cool。😊。

So we're actually going to learn in this lecture about the differences in AR experiences。

 not just in this lecture， actually in this whole week， focused on AR。

 So we're going spend time on Macerbased A， where the user actually uses a fidu like a often physically printed out marker on paper and that marker is then the portal into the AR world。

 We're going to learn about Macca less AR。 So using the device as a lens into the AR world。

 And the device then does the hard work of actually doing environmental understanding and figuring out where it is establishing the 3D coordinate space。

 So the system and the frame to really understand how it moves through 3D space。😊。

And we're also going to learn about why the first two。

 at least in our case studies are focused on mobile AR。

 And I think those are the ones that are very accessible to you。

 if you have a smartphone that is AR capable supports AK and AR core or just markers using the webcam the other real camera on the smartphone。

 we're also going learn about headw AR。 So I'm going to show you some examples of the Hollolens too。

 I realize that you may not have access to that device。

 but I still think it's very interesting because in the next few years we can hope at least that the cost will drop and you will be able to use head1 AR。

 So seeing the AR world directly and always and that is interesting。

So think about all the evil episodes in Black Mi， if you watch that show， yes， anyway。

So here's a quick overview of how Macer based of mine reality actually works。

 So you're putting up a marker like this hero marker here。 This is based on air toolkit。

 And so it is a default Fi。 You can train your own custom markers。 you can customize。

 you can even randomize in some of the toolkits out there。 So beforeia， for example。

 which we're gonna spend some time with you can actually generate markers。😊。

You always have this kind of trade off between planning with the environment and optimizing for tracking。

 So these markers， for example， have to be designed in a specific way。

 The black borders are important。 and we're gonna learn about all this。

And then what happens is as the user brings in their smartphone here。

 like I'm showing this in in a second as the user brings in you know。

 holdss the phone above the marker or brings the marker into the view of the phone。

 we actually then see a few interactions going on and we have the when the marker is found。

 we can visualize， we can track it and we can visualize any content that was designed for that marker。

 So we show the marker content when it was found when the marker was found。 when the marker was lost。

 then normally we would hide the marker based content， Otherwise， it'll look weird。

 if you just leave it。😊，Floating unless you have a transition to Mac S AR。

 which is called extended tracking。 So switch from Macbase to Macs。

 And that's an option that you have if the user has a smartphone that supports， for example。

 Air core Air kit。 So inia extended tracking is， is relatively easy to implement。

So here's an example of me just doing just that so I'm actually using this slide and this is something that if you go to some of our examples which I'm going to share with you then you can also just do that and try that out we also have content where I'm going a little bit more into how to implement these kinds of things as part of the honest track So if you're really interested in doing this I have some follow along lectures there in the as part of the main track I'm going to keep it relatively straightforward just focused on an overview So we're also going to learn about Ma less augmented reality So Macs augmented reality works a little bit differently what you see here is actually visualized planes these were detected and we're going to learn about this in detail how surface or plane detection works it's a very primitive form of environmental understanding we learn about more advanced forms of environmental understanding as well So environmental understanding is required to detect physical objects in plays then virtual objects in the environment we're going to learn about plane detection。

We're gonna learn about spatial mapping。 So spatial mapping usually usually uses some form of depth sensing。

 So you may have additional cameras for that it can to some extent， be done with just software。

 So software based augmented reality。 So AR core and A kit are actually getting really good at doing spatial mapping as opposed to hololenens。

 which actually has real depth cameras。 so we're gonna learn a little bit about this。

 And then the use of obviously understanding the 3D geometry is that we can， for example。

 render occlusions。 So then we can make virtualcon of disappeared if it if it shouldn't be visible。

 So if there' as a physical object in the way。😊，But here's a very simple example of using environment understanding。

And then there are some more advanced aspects， like as I said， occlusion or light estimation。

 Like if you wanted that content to really fit in blend in nicely and not stand out like the way it does。

 obviously， it's an abstract shape。 but it could be some kind of trophy or I don't know if somebody ever gives me a metal。

 it could be an air metal。 then that would blend in there。

 if we actually adapt for the lighting conditions in this specific area。 So we need light estimation。

 And that's something we're gonna not touch on too much。

 It's just something I want you to be aware of。 So there are actually two things in in for example。

 an A foundation that you can control for is actually on the specific platforms an A core and A kit So on smart based platforms are actually quite advanced there。

 So they can control for ambient intensity。 So apply average lighting to an object。

 and also color temperature。 And so actually use white balance to color correct the object。

 And I'm not really showing this in the screenshot。 So what is actually happening here。😊。

I'm going to show you quickly the demo。 So I'm just going go here again to my desk。Place the object。

 This is one of the A Foundation samples that I was just running here。 Well。

 I was proudly deploying it to my phone。 Quite an intense process to do this in unity。😊。

And then run it。 And then you have basic interactions。 This is part of the X interactions Tookit。

 There is also now native integration in unity。And then you can like， move things around， scale。

 rotate。 And you have support for all that。 And the planes that are being detected by constantly scanning the environment in the background。

 That is the environmental understanding。 It's limited to horizontal and and vertical surface at this stage。

Allow you to place these objects in the world。So we're gonna learn about marker based and Macs。

 We're gonna compare it。 really， what changes is in terms of the environment content and the interactions really change。

 so we're gonna learn about this。 but at the highest level。

 obviously environment is limited when it comes to marker based experiences。

 you actually don't actually have an understanding of the environment。

 youre designing around that marker and the user can play that marker whatever they want to。

 Macs is obviously you're trying to get a read on the environment and that is interesting。

 that allows you more mobile， You don't always have to keep a marker in view。

 So it enables larger scale in terms of environment。😊，Then content， I mean。

 something to think about is like how big should the content be appearing when it is relative to a marker and then when it's like in in the world rather than tabletop。

 if you can also do Macs tabletop experience， but it's more common to do MacS and then room scale experiences。

And so that actually has an impact on on the layout of the content release and the scale and actually the amount of content you can you can show because for Macerbase they are at any time。

 the marker needs to stay in view unless you have external tracking。

 And that's when you start blurring these things。 and interactions。

 you can obviously have more implicit interactions with the marker。 So I mean。

 maybe the explicit part is the user has to place it somewhere。 But then the app just runs。

 or you could have more explicit markbase interactions really asking the user to bring things into view to show specific parts of the interface。

 So in our K law example， we learn about switching between the laws actually bringing in a different sheet of paper。

And then for Macs AR， we're also going to learn about differences in interactions。 Obviously。

 it could be touch based。 It could also be if it's head one AR， it could be gesture and speech。

 And so we're going to learn about these considerations as well。So think about this example。

 I'm gonna show you throughout examples of Macca based AR。

 So that's the tabletop experience that I was talking about。

 And then this is like the room scale AR foundations example。 So this is A R J S， Web X R based。

 And we're gonna learn about this。And I'm going show you examples here as well。

 So we have specific lectures focused on Mac based and Mac S AR。

 We're also going learn about the difference between handheld AR and head one AR。

 So I'm going bring out my heartlands to， I'm going show you a really cool。 Well。

 relatively abstract， but cube example。 I built this relatively last minute。

 I thought I had this idea of how to continue this thread of interactions throughout the lectures。

 I hope you like it。😊，It was Well， was not too difficult to implement using the mixed reality toolkit thanks to Microsoft was relatively easy to implement on the Hols。

 too。

![](img/a365f5d636c40d97ac278e3c1f871fb7_3.png)

And here's my example。So we're gonna move some cubes here。

 And the cool thing now is because we have advanced environmental understanding these cubes and they have physics。

 So I gave them physics。 They are rigid body objects and they use gravity。

 And so then they actually can land on the world。 You also just saw occlusion。 right。

 This table here is actually occlu the virtual content。

 And I'm visualizing the spatial mesh all the time。

 The blue stuff here is the read of the device on the environment。 And then I can do。

 we're gonna learn about these interactions。 We're gonna learn about near and far manipulation。

 both for Vr and for AR here。 This is AR。 I was just doing a far manipulation using that cube。😊。

And we're gonna learn about all these things。 So it's gonna be very cool and very interesting。

 And looking forward to teaching you about A。 We are also gonna think about design issues。

 So this is really the red thread throughout the X very important to me when it comes to A R really。

 we need to think about the social and the ethical concerns。

 there are significant ones because these applications really depend on camera access。

 kind of like 247 camera access。 need to see anything and everything in order to make sense of the environment。

 you know where I'm going with this， you get it， Yes， so there are significant concerns。

 If you don't care， that's fine。 But you are gonna capture other people and they may actually care。😊。



![](img/a365f5d636c40d97ac278e3c1f871fb7_5.png)

We have to think about， at least since we cannot do too much about accessibility at the moment。

 in equity is an issue。 Smart based， they are as available to a lot of people in the western world。

 But if I did this whole lecture just based on Hollands。

 I was one like how many people would actually， I mean， you would probably enjoy it。

 But it would be disappoint because you couldn't do it for yourself unless you have access to such a device。

 So equity and these devices are very expensive。 So equity is really an issue。

And we're going talk about that a little bit throughout the course。

 I reallyt need to make sure that I mentioned these design issues because in the next few lectures。

 we're going to go deep on the technical and the development side。

 And that's always when you forget to talk about these important high level issues。

 including privacy and security。And this is something that I'll come back in week4。

 So in the last parts of this MOO。 But really in the first course as part of the XOoc。

 that one that is supposed to lay the foundation。 These are really， really important issues。

 and and so I just wanted to make sure again that I'll bring them up。

 I know as a little bit of a weakness， because we are so focused on the technology in this course。

 we don't have enough time to talk about these issues。

 but please in your design and development activities， we always consider these issues。

 They should just like， you know， they shouldn't they shouldn't be an afterthought。

 They should be built into any and every decision you make as part of the development process。



![](img/a365f5d636c40d97ac278e3c1f871fb7_7.png)

You get it。 Allright。 So I'm looking forward to teaching you more about AR， Macbase， Macs， headboard。

😊。

![](img/a365f5d636c40d97ac278e3c1f871fb7_9.png)

![](img/a365f5d636c40d97ac278e3c1f871fb7_10.png)