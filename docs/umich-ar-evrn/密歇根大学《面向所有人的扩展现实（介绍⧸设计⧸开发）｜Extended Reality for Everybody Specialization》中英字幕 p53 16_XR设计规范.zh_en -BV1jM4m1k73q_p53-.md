# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p53 16_XR设计规范.zh_en -BV1jM4m1k73q_p53-

![](img/22531beb44a8594ed2700a63f66081eb_0.png)

![](img/22531beb44a8594ed2700a63f66081eb_1.png)

So X design guidelines is a really， really important topic and the problem that we have right now is that Ex design is really a moving target。

 so many new kinds of devices coming out and some of them are changing really the way we interact now that we have hand tracking available and eye tracking as input on both AR and VR devices。

 it is very interesting where this leads in terms of design evolution。😊。

And so I really struggled a little bit when I wanted to put this lecture together here。

 I was hoping and that I can share something practical and really wanted to have concrete guidelines as much as possible。

And I've looked at all the guidelines that are out there。

 and we're going to review some of them here as well。

But the issue is really that there is no perfect guidelines out there， so。

The moral of the story and the essence of the message here in the end is that you just have to try it out and you have to think from the perspective of a user。

 not just design and implement the things that you think are easy as a designer。

 know you really have to look at is what is meaningful what is useful。

 usable and also consider long term use and well， hopefully develop an intuition over time。

And that allows you to determine whether something is a good or a bad design。But yeah。

 that's just like my perspective。 I've still tried to put together a few guidelines for us to get started and we can use these guidelines to review each other's designs throughout the course and but think of it really as a source a starting point a source of guidelines that can evolve hopefully over time and that's really how design works So we're still in this part of the course where we're more on the design thinking side So what's the best way to learn about Ex design So I think it's actually studying design guidelines。

 So what is the knowledge that is out there and which of these guidelines are really like something we have to adhere to and which of these we can bend to potentially innovate in design we need to learn how to critique existing designs and actually that critique will really involve a lot of constructive criticism and suggestions for improvement a lot of this should be based on。

😊，Lance as much as possible， should be objective。 And finally。

 we want to be able to create our own design。 So I'd say in all of these。Efforts。

 it's really important to learn about guidelines。 So when we have a look around。

 there are actually quite a few guidelines out there。

 And I think we can distinguish them into like four types of guidelines or sources。

 those by vendors that I think are mostly platform driven。 those by designers。

 The good thing about those is that they're really user oriented。

 and they're coming more from a human computer interaction perspective。😊。

Then there are those created by practitioners， so really experience based not necessarily with scientific rigor and that's why I would draw the line to those established by researchers usually empirically derived to some kind of lab-based user studies and controlled experiments and so there are all those guidelines out there and I'll provide references to some of the promising examples。

In this video， I'm going review a few of the vendorbased guidelines。

 and then I'm going to share some of my own experience and insights。

 and we're going to actually go in a little trip as part of a recent experience where I went to a remote conference。

 IE virtual reality conference。 And so I thought it's actually quite cool to look at how researchers and designers implement current virtual worlds。

 for example， to support something like a remote conference attend。

 And so we're going to look at that。 And that's one of the examples I have here as well。

 So let's look at a few guidelines first。 I picked Oculus guidelines。 mostly focused on Vr。

 then I picked some from Google。 Theyre focused on AR core。 And so a handheld AR。

 And then I was also looking at other sources， Apple Microsoft。😊。

And and then Mozilla and so the Apple and the Microsoft ones are actually quite good。

 but for coped reasons cannot show them here， I'll link them and I added the Mozilla ones because they are really in the realm of Web XR and this idea of bridging multiple devices and platforms。

 They're a little bit more technical as well， but I think。😊，Together， comprehensively。

 quite a nice set of guidelines driven by vendors and device creators。

 and then also open standards initiatives and institutions like Mozilla。

 So the first example we're going to look at is here from the Oculus guidelines。

 And so I I browsed and selected my device first。 let's say I'm going to develop for the Oculus Que。

 And they're going to tell you a little bit about how rendering works， how streoscopic images work。

 And then。😊，It says things like don't occlude the screen with the hD that makes a lot of sense and don't draw hud elements behind scene elements。

 So these are some really good tips in this sometimes happens by accident。

 And then I think we're entering a very practical portion here where it talks about basically the field of view and how vision works and both the horizontal So the horizontal field of view and the vertical field of view that we have and where we see best and what's really a good area。

 And then I think those guidelines focused on hand tracking are really a part where the Ochius guidelines stand out。

 So let's focus on these a little bit and explore them in more depth。

So here you see a concept video of how the app store might work where you're exploring one of the games like Me Saber here using hand interaction。

And then they're talking a little bit about the principles behind。Hand based interaction。

And they're using terms that I like， obviously informed by Don Norman。

 So affordances signifies and feedback some of the core design principles that we often teach。

 or at least hear about when it comes to user experience and interaction design。For example。

 then talking about how to constrain inputs to improve usability。 so the degrees of freedom。

 which can actually be very useful， but sometimes you don't want to move objects along all axes and talking about some of those things。

 also sending this reminder that hands aren't controllers。

 And so you should design differently for hands as you if you previously did。

 controller based VR interaction。 then there's quite a few things you need to adapt。

And really cool illustrations here。 So overall quite a few helpful tips and very useful illustrations talking about both their principles and interaction styles and then also talking about user interface components really bringing it down from the theory to the practice and then specifically for the Oculus platform。

 which I think is pretty useful even though it is obviously vendor driven and platform driven。😊。

Many of these things could still translate to other platforms， as well。

So our next example is augmented reality guidelines from Google AR core。

 I really like those because really useful illustrations and to the point telling us a little bit about how AR core works and how to you think about environmental limitations both in terms of like obstacles that could be there for users and also where where the platform has trouble actually detecting and recognizing different types of surfaces so sometimes to do with lighting or reflection really that makes it hard and then a few practical tips regarding how to design an AR experience。

 are you designing for tabletop are you designing for a room scale or a world scale experience。😊。

And then ideas of how to promote interactions and communicate where interactions can take place。

 So surface detection and visualizing surfaces， then also adapting to the available play area。

 talking about how to promote。Well， how to promote users exploration and potentially having fun。

 talking about different types of movement and how you actually have control a little bit through visual cues。

 you really have， even though obviously AR and VR are really about agency and giving autonomy to users as a designer。

 you still have a lot of influence over how users move and interact。

 and you can drive that through visual cues and audio cues。

And you can also combine these in useful ways to address accessibility issues。And as I said。

 safety and comfort is really at the core of most guidelines。

 And what I like here about some of the ones from Google is that they illustrate really to the point like what are the things you want to avoid don't have people move backwards。

 for example， and talking about realism and how to achieve more realism through modeling。

 texturing and then material design really good tips。

 also for Xr designers who don't necessarily have a 3D design and modeling background cool examples。

 in comparison。 So really quite useful reference here in terms of design guidelines and to the point。

 Our next example is a specification and some guidelines around Web Xr In this case。

 authored and edited by Mozilla。😊，And so the Web XR specification is still evolving and even when you look at this draft you will still find portions that are unwritten but really useful for illustrations around how tracking works。

 how headsetsets for VR works， theoscopy and designing for virtual reality and physical risks。

 so motion sickness or virtual reality sickness they call it here and physical risks。

And earlier versions of these guidelines had really concrete values in terms of like。

 where you should place， for example， text and。Really emphasizing the fact that you shouldn't move the virtual camera unless the user really wants it and then thinking about fading in and out to or blurring the periphery in order to reduce emotion sickness。

What I really like about this document here is the approach it takes towards crossplatform and thinking about both AR and VR。

 and then coming down to basically what's common which is virtual cameras and how you manipulate the view and how you can basically achieve kinds of effects that are similar to filmmaking with good illustrations so it actually helps us understand a lot of the material better。

 so I think this is a unique aspect to some of these guidelines。A little technical。

 maybe for the taste of some designers， but overall。

 I'd say pretty good and still evolving guidelines helpful for crosspl， webbased AR and VR。

 So this is gonna be a very useful resource for us in the future as well。

 So these were just three examples one from Oculus focused on Vr and one from Google AR core focused on smartphonebased handheld AR Mars in this case。

 and then also an example from Mozilla， which is really at this intersection of platforms and focused more on the Web XR standard as I said a little bit more technical。

 So just reviewing these guidelines。 we can see a lot of the interesting challenges that there are right now about these guidelines。

 these were all relatively practical and to the point examples。

 I've seen a lot more vague guidelines。 So here's the trouble that I have with a lot of the X design。

yGuideline。And again， keep in mind that I showed some really good examples here。

 So I'm not critiquing those specifically at the core。

 We really don't have established best practices。 They are actually really rapidly evolving still Xr design is still a moving target。

 lots to still learn about it。 there's a lot of research and design going on in the space。

 we only have very slowly emerging if at all， design patterns。

 and then those patterns really often change with a new OS update。

 I've seen this with Oululus multiple times for example。

 and then we already have major differences between device platforms。

 So even when you look at Vr devices and compare Oculus and V guidelines or when you look at AR guidelines and look at the Apple ones and the Google ones for A kit and A core。

 you really see quite a big gap and major differences between some of these platforms。

 So not only between AR and Vr as platforms， but also between different vendors and providers at the core。

 however。I agree that obviously designing for comfort and safety is really important。

So I would say there is a problem still with scoping guidelines， just in the examples I shared。

 some of them were quite technical， So the Oculus and the Mozilla ones and the ones from Apple and the ones from Google were a little bit more high level。

 like keep the user safe and comfortable。That's not。 I mean， they then went into some of the detail。

 So as a， this more like a principle than a guideline。

And so overall it's a little tricky at the moment to figure out really what's the best way to scope and present guidelines。

 Many of them are to application or device or vendor specific。

 So in the absence of a lot of really clear and established guidelines I would just say that the best guidelines come from learning by doing and it is really important that you test your designs early and often and learn from your own mistakes。

 realize that you made a mistake when you test it with users。

And then I think at the core it's still important to mind that the differences between VR and AR。

 so really designing a virtual world， but still taking care of the physical world and then augmenting enhancing the virtual world with AR and maybe less of a focus on the differences between specific devices and vendors in the end。

 we really need to figure out what are the good things to do in VR and what are the good things to do in AR and what should we really avoid。



![](img/22531beb44a8594ed2700a63f66081eb_3.png)

![](img/22531beb44a8594ed2700a63f66081eb_4.png)