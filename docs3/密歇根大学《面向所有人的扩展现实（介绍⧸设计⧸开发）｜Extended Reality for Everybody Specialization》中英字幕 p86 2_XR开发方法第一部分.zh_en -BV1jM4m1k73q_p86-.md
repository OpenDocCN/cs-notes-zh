# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p86 2_XR开发方法第一部分.zh_en -BV1jM4m1k73q_p86-

![](img/9c9ee115cb57be2eb4a8d6cd28b81505_0.png)

![](img/9c9ee115cb57be2eb4a8d6cd28b81505_1.png)

In this course， we're going to talk about XR development before we really get started。

 we're going to explore different alternatives and different routes to being an XR creator。

I'm going to introduce you to three platforms or tools， if you will， Webex are unity and Un。

 Those are the three big options that we're going to cover throughout this course。

I have a lot of experience with Web XR and Aframe， so aframe is our web based approach and that leads us into Web XR and then unity you may have heard of。

 so a lot of people that talk about XR swear on unity。And then unreal， I mean。

 if you've played some games and you've heard of epic games。

 unreal is really the tool that was and is behind many of the games that are being created by epic games。

 And so it's actually really a powerful tool。 So we're going to explore all these three throughout the course。

 most of my experience is， as I say， with unity。😊，And a frame， at least at this stage。

 but I'm always learning， and that's also the point of this whole course， right。

 we're going to learn more about XR development together。So I'm going to show you an overview first。

 so the X process and this is something that I've talked about also in the second course more focused on design so might be a little bit of a repetition if you have you know taken this course before。

😊，But so in that other course， we're going to talk a lot more about need finding and brainstorming as really one of the first big steps that we have to do as part of the Excel process。

And we also really heavily emphasize storyboarding and prototyping。

 the whole second course was really focused on that。Now， in this third course， as part of the XMOoc。

 we are focused on development and testing。 That is really our goal here in our whole focus of this course。

 So we're going to be a bit more technical。And we also normally as part of the X process well when we're done with development we need to figure out how to get this stuff to the user so let's call this deployment and you know you would probably think you're done then but actually you know this is where a lot of the work really actually just gets you started in the form of analytics you want to find out whether what you have actually makes sense so this is not the first time you do user testing okay don't get me wrong by that time you should have already done user testing In fact we do user testing we involve users。

😊，Throughout， okay， in each of these steps I' introduced to do various techniques。

 even down to paper prototyping and testing， even at this second step。

And development and testing also should and can involve users as much as possible。So。

The analytics part is something that I'll talk about at the end of this course as part of some of the more advanced techniques throughoutout the course。

 we're really here。 This is us。 This is all we're going to do if you think about it and there's so much to talk about。

Things you should do first， and I say this you know as a piece of advice。

 but also like what that means given where we are in the process， so you should have a plan。

 a project plan， you should have defined your approach and I'll tell you a little bit more about the development approach in this lecture。

😊，And there should be milestones defined and you should have roles。

 usually it is probably more than one person working on an X project。

 But if it's just you then well good luck no I mean that's pretty cool。

 I've done a lot of projects just by myself as well it's totally doable you also should have done some sketching So both high-lel and detailed sketches you should have fleshed out your ideas you should have a better idea of the personas So who are the people we are actually designing for and who we are not designing for and then usually what we do is part of a more user experience and interaction design oriental process we do story mos maps we identify the goals and tasks that we want to support I know talking to you now as developers。

 you probably primarily think in terms of features what kinds of features should I develop What should I implement How do I implement those I usually like to think in terms of goals I want to support So uses goals and then what are their tasks and activities and that then inform the features。

😊，And actually to learn more about the features， we usually do prototyping into rounds physical and digital and again。

 this was the focus of the second course， so we will revisit elements but not too much in this course。

😊，Okay。Again， well， it seems like I'm advertising。 it's having course a lot， but I really。

 really believe in this， and you should trust me on that one。 So there is。

 it is really significant that you do these physical and digital prototypes firsthand。😊。

And and before you do any kind of major development。

 so here you see from our Pokemon Go kind of workshop starting out on paper and then quickly using this template。

 that's 360 paper template to then prototype this way。

 and then we've also worked on tools to quickly digitize content。And this is an example of that。

So these physical and digital prototypes， I would say they're quick and dirty。

 but they're really useful to explore interactions。

They're important to get initial use user feedback。

 You can actually involve users already at this stage， and you should think of AR VR as an option。

 So nobody says it has to be in AR of VR solutions。 So you really want to avoid premature commitment。

 On the other hand， if you feel like Xr approach is the right thing。

 then these prototypes will definitely also tell you more about the technical requirements and help you device those。

 So what we should also understand throughout and Ive really talked about this again。

 more in the second course But we are going to approach development also in stages from low fidelity to high fidelity。

 So we're gonna work with placeholder content。 You can do this additional tools。

 We work with 3D primitives。 like here， this sphere in the back the box and the cylinder。

 So those guys。😊，And then you would polish your content usually this is some kind of fancy 3D model and then we're gonna to actually add support for implicit and explicit interactions。

 I've introduced those terms before So implicit interactions are mostly kind of like camera based so that would mean here this is relatively simple and a 3d of freedom headset like cardboard not too many things you can do you do have a button and I would call this an explicit interaction the user is actually targeting something and then explicit clicking Now we do gaze on a lot of things as we gaze around so these are all implicit interactions if you dwell on something or fuse in on something I would then call this an explicit interaction and this is the example I'm going to give here So let's assume the user is gazing onto this object and then they're like staying there we call thisfuse that actually triggers a click event。

And well， we've just changed the 3D model the appearance somehow we've manipulated it。

So I would recommend that you start on the Loify end， you plan out scenes with placeholder content。

 and then you can bring in some of the more， well， the nicer 3D models and the content that you need。

 including audio and all those kinds of things。And then only then we are actually doing interactions。

 Now the way I say it here， it sounds like very sequential。 a lot of this is really iterative。

 So development and testing so this is a figure I've shown in the second course as well。

 so here we see the three kind of big approaches that we're going to talk about Web Xr when I say Web Xr it's will be a little confusing sometimes are really specifically referred to the Web Xr specification so it's really an upcoming standard。

😊，And sometimes we just use WebEx as a term to loose refer to doing AIV other things on the web。

So speaking of doing AR via things on the web， I think aframe is a really cool tool for that。

 And that's the one that I've chosen。 So I think of aframe as the tool to do Web XR throughout this course。

 we also gonna do unity and Unal in this course。 I have more experience with unity。

 I just must honestly say that。 but I have been practicing my Unal skills through a learning group in our lab that was really cool organized by one of my students。

 Alan， he did a really good job and then also we have actually attended a few workshops by epic themselves。

 So they have been very supportive of us here at Michigan。 anyway， so with unity。

 you can do things like Steam VR， which is crossplform VR development。

 So crossplform means you can reach all those guys Ocus and Vive and others Val and the index and other kinds of headets that don't always list here。

😊，You can also do AR development。 So AR foundation。

 which is kind of like a crossplatform thing above A kit and AR core。

 Okay so native SDks are like when you're good at mobile development， for example。

 then these are the specific SDK you target Oululus directly or you target vive the HTC vi directly or you target AR kit directly or you target AR core directly。

 So A Foundation specific to unity。 and then MRtK。 So mix reality toolkit is really one of the toolkis that I've been playing around with a lot recently。

 it allows me to do both mobile AR and then also Hollolens development。

 So I'm really fond of the Hollens1 and the Hollens 2 actually quite a bit。

 And so that gives us an overview of how you could do development and then testing。

 So each of these actually then come with specific tools for testing So in aframe， for example。

 there's an inspector that helps you a little bit unity Un。 obviously have。😊。

Consults and a lot of notifications and additional tools。

 and then don't get me even started on Android Studio or Swift and Xcode if you're doing。

 for example， AR。 there's a lot of develop a tool support in there as well and you probably know that better。

 if you are choosing this route， I can't help you， you probably know better and maybe you are actually too advanced for this course。



![](img/9c9ee115cb57be2eb4a8d6cd28b81505_3.png)

![](img/9c9ee115cb57be2eb4a8d6cd28b81505_4.png)